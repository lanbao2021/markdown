* [Linux为何物？](#linux为何物)
* [Linux的诞生历史](#linux的诞生历史)
* [Linux重要人物L/K/D/S/B/T](#linux重要人物lkdsbt)
* [学习Linux的路线](#学习linux的路线)
* [tty, terminal, console的概念🔗](#tty-terminal-console的概念)
* [命令解析器shell](#命令解析器shell)
* [Linux哲学](#linux哲学)
* [Linux目录结构](#linux目录结构)
* [绝对路径/相对路径./](#绝对路径相对路径)
* [快捷键T/TT/C/D/A/E/U !!](#快捷键tttcdaeu-)
* [常用命令](#常用命令)
  * [ls/cd/pwd/mkdir/rm/cp/mv/ln](#lscdpwdmkdirrmcpmvln)
  * [touch/cat/more/head/tail](#touchcatmoreheadtail)
  * [ps/top/kill/killall/bg/fg](#pstopkillkillallbgfg)
  * [tar cf/xf czf/xzf cjf/xjf](#tar-cfxf-czfxzf-cjfxjf)
  * [gzip](#gzip)
  * [ping/whois/dig/wget](#pingwhoisdigwget)
  * [date/cal/uptime/w/whoami/finger/df/du](#datecaluptimewwhoamifingerdfdu)
  * [uname/free](#unamefree)
  * [grep搜索 && 管道与grep](#grep搜索--管道与grep)
  * [./configure make dpkg rpm](#configure-make-dpkg-rpm)
  * [使用man时的搜索、翻页](#使用man时的搜索翻页)
  * [whoami/adduser/groups/su/usermod](#whoamiaddusergroupssuusermod)
* [通配符 * ? { } [ ] [^]](#通配符-------)
* [查看Linux文件属性、权限](#查看linux文件属性权限)
* [变更文件所有者、权限](#变更文件所有者权限)
* [软链接和硬链接](#软链接和硬链接)
* [Linux中的环境变量🔗](#linux中的环境变量)
  * [变量和环境变量的概念](#变量和环境变量的概念)
  * [定义局部、全局环境变量](#定义局部全局环境变量)
  * [局部环境变量与全局环境变量的特性](#局部环境变量与全局环境变量的特性)
  * [/etc/bashrc .bashrc .profile](#etcbashrc-bashrc-profile)
  * [环境变量PATH](#环境变量path)
* [test GitHub](#test-github)

参考：https://www.lanqiao.cn/courses/1

## Linux为何物？

  
  一种操作系统OS（Operate System）
  

![20220209151303](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220209151303.png)

  

## Linux的诞生历史

  Linus嫌弃UNIX太贵，在廉价的MINIX基础上开发了Linux

## Linux重要人物L/K/D/S/B/T

* Linus

* Ken Thompson 和 Dennis Ritchie：C 语言之父和 UNIX 之父
  
* Stallman：著名黑客，GNU 创始人
  > 开发了 Emacs、gcc、bash shell

  
* Bill Joy：BSD 开发者
  > BSD是伯克利软件套件，是类UNIX操作系统中的一个分支的总称

* Tanenbaum：Minix 开发者

## 学习Linux的路线

![20220209152837](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220209152837.png)

## tty, terminal, console的概念[🔗](https://www.zhihu.com/question/21711307/answer/2231006377)

![20220209155022](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220209155022.png)

## 命令解析器shell

  有“壳”就有核，即UNIX/Linux内核

  常见的shell：bash, zsh, xfce

```bash
cat /etc/shells # 查看当前系统已安装的shell
```

## Linux哲学

没有结果就是最好的结果

一切皆文件

## Linux目录结构

![20220209195252](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220209195252.png)

## 绝对路径/相对路径./

绝对路径：从根目录 `/` 开始

## 快捷键T/TT/C/D/A/E/U !!

*  `Tab` auto full command
*  `Tab Tab` show all possible full command
*  `CTRL + C` stop command
*  `CTRL + D` the same as `exit`
*  `CTRL + A` line ahead
*  `CTRL + E` line end
*  `CTRL + U` delete command in the line
*  `!!` repeat last command
*  ⬆️⬇️

## 常用命令

### ls/cd/pwd/mkdir/rm/cp/mv/ln

```bash
ls
ls -al
cd dir
cd  # you don't have to carry '~'
pwd
mkdir dir
rm file
rm -r dir
rm -f file
rm -rf dir
cp file1 file2
cp -r dir1 dir2
mv file1 file2 # rename
mv file dir  # move
ln -s file link # symbolic link 
```

### touch/cat/more/head/tail

```bash
touch file
cat file
cat -n file
cat > file # stdin to file
more file
head file
tail file # just see the last 10 lines.
tail -f file # see from the last 10 lines.

```

### ps/top/kill/killall/bg/fg

```bash
ps # current active processes
top # all processes
kill pid
killall proc # kill all processes named 'proc'
bg # list stop or back processes
fg # recent processes to front
fg n # job n to front
```

### tar cf/xf czf/xzf cjf/xjf

```bash
tar cf file.tar files # file.tar contains files
tar xf file.tar # extract from .tar
tar czf file.tar.gz files # compress using Gzip
tar xzf file.tar.gz # extract frome .tar.gz
tar cjf file.tar.bz2 files # compress using Bzip2
tar xjf file.tar.bz2 # extract from .tar.bz2
```

### gzip

```bash
gzip file # compress file and rename as file.gz
gzip -d file.gz # decompress file.gz
```

### ping/whois/dig/wget

```bash
ping host
whois domain
dig domain
dig -x host
wget file
wget -c file # stop can resume
```

### date/cal/uptime/w/whoami/finger/df/du

```bash
date
cal
uptime
w
whoami
finger user
df
du
```

### uname/free

### grep搜索 && 管道与grep

```bash
grep pattern files
grep -r pattern dir # recursion search
command | grep pattern # search the output of command
```

### ./configure make dpkg rpm

```bash
./configure
make
make install 
dpkg -i pkg.deb
rpm -Uvh pkg.rpm
```

### 使用man时的搜索、翻页

`man ls` # 获取帮助

* /word，向后搜索word
* n下一个，shift+n上一个
* space翻页
* enter滚动一行

### whoami/adduser/groups/su/usermod

```bash
whoami # get the username
who am i # more details
sudo adduser lilei 
su lilei # change user
su - lilei # change user and PATH & DIR
groups lilei # get the groups lilei belong to 
sudo usermod -G sudo lilei # add lilei to the group of 'sudo'
sudo deluser lilei --remove--home # deep delete lilei user 
sudo groupdel lilei # delete group 'lilei'(it should be empty with no users)
```

su = substitute user

## 通配符 * ? { } [ ] [^]

  + `touch file_{1..10}.txt`
  + `ls *.txt`
  + `ls file_?.txt`
  + `ls file_[123]`
  + `ls file_[^123]`
  + `ls file_[0-3]`
  + `ls file_{1, 3, 5}`

## 查看Linux文件属性、权限

`ls -al` 显示隐藏文件+详细信息
`ls -lh` 显示文件大小+详细信息

![20220209180817](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220209180817.png)

![20220209191730](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220209191730.png)

## 变更文件所有者、权限

`sudo chown lan filename` 变更所有者

 > chown = change owener

`sudo chmod 777 filename` 变更文件权限的数字法

> chmod = change mode

 
 `777 = 111 + 111 + 111 = rwx + rwx + rwx`

 `666 = 110 + 110 + 110 = rw- + rw- + rw-`

`sudo chmod ugo+rwx filename` 变更文件权限的加法
`sudo chmod ugo-w filename` 变更文件权限的减法

> u=user , g=group, o=others

## 软链接和硬链接

硬链接类似于python中的引用计数器，只有计数器为零这个文件(inode)才是真正消失了

软链接就是一个快捷方式

## Linux中的环境变量[🔗](https://blog.csdn.net/reliveIT/article/details/45224575)

### 变量和环境变量的概念

环境变量是指在**shell**中能使用的变量，之所以多加‘环境’二字是为了与普通程序中的变量区别开来，环境变量通常用**大写**的变量名，如： `PATH`

![20220209230817](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220209230817.png)

注：这里的shell在Windows中就是cmd，因为很多应用程序都需要通过shell命令去调用系统的各种功能，环境变量的存在使得这种调用很方便

### 定义局部、全局环境变量

```bash
tmp="local var" # 局部环境变量，注意等号周围不能有空格
echo $tmp # $表示引用，echo返回后面的变量值

export tmp="global var" # 用export定义的则是全局环境变量
```

### 局部环境变量与全局环境变量的特性

**证明1**，全局环境变量在当前shell进程及其开启的子shell进程可用，父shell进程不可用，并且子shell进程是copy父进程的环境变量，因此子shell进程对其环境变量的修改不会对父shell进程产生影响

通过2个shell脚本来证明

父shell进程执行的命令：father.sh

```bash
#!/bin/bash 
# 第一行指定使用哪种shell命令解释器
# father.sh
export tmp="father var"
sh son.sh # fork调用
echo $tmp # 虽然子shell进程修改了tmp但是不影响
```

子shell进程执行的命令：son.sh

```bash
#!/bin/bash
# 第一行指定使用哪种shell命令解释器
# son.sh
echo $tmp # 输出的是父shell进程中的tmp, 'father var'
tmp="son var" # 修改从父shell进程copy的环境变量
```

-----

**证明2**，局部变量当前shell进程可用，父shell进程和子shell进程都不可用

通过2个shell脚本来证明

父shell进程执行的命令：father.sh

```bash
#!/bin/bash 
# 第一行指定使用哪种shell命令解释器
# father.sh
tmp="father var"
echo "father.sh输出tmp的值：$tmp" # 当前shell进程能正常访问
sh son.sh # fork调用
echo "father.sh输出tmp的值：$tmp" # 父shell进程无法访问子 shell进程定义的环境变量
```

子shell进程执行的命令：son.sh

```bash
#!/bin/bash
# 第一行指定使用哪种shell命令解释器
# son.sh
echo "son.sh输出tmp的值：$tmp" # 子shell进程不能正常访问父进程定义的局部环境变量
tmp="son var" # 子shell进程定义局部环境变量
```

注：开启子进程的方式有fork, source, exec，具体看参考链接[🔗](https://blog.csdn.net/reliveIT/article/details/45224575)

### /etc/bashrc .bashrc .profile

这些是存放环境变量的地方

`/etc/profile` 和 `/etc/bashrc` 是系统级的，有个性化需求咱没必要去动它，主要修改 `home` 目录下的 `.bashrc` 和 `.profile` 就行，其中 `.profile` 的作用范围比 `.bashrc` 更大一点， `.bashrc` 是指 `bash` 这种 `shell` 使用的环境变量配置文件，如果你用的是 `zsh` （MacOS默认shell）就没有 `.bashrc` 这个文件，这个时候怎么办呢？手动创建 `.bashrc, .zshrc, .profile` 然后进行修改，修改完保存后如果要立即生效记得使用一下 `source` 命令

### 环境变量PATH

`PATH` 中不同路径用 `:` 分隔开

![20220210004635](https://cdn.jsdelivr.net/gh/lanbao2021/PicGo-img/20220210004635.png)

直接输 `ls` 能执行命令就是因为 `PATH` 中有 `/usr/bin` 目录，而 `ls` 的可执行文件在 `/usr/bin` 中（一般是软链接）

当我们自己写的程序也想要实现这种效果时就需要利用到 `软链接` 和 `环境变量PATH` 了，下面来举一个例子

①查看PATH环境变量，选一个当前用户有访问权限的

如： `/usr/local/bin`

②写好你的脚本文件 run.sh

假设其所在路径为： `~/test/run.sh`

③做一个软链接到PATH包含的目录

如： `ln -s ~/test/run.sh /usr/local/bin/run`

④用 `alias` 定义一个别名

先用 `alias` 命令看看有没重名

检查没问题就执行 `alias run="sh run"`

这样就可以在任意位置执行 `run` 命令跑你的脚本文件 `run.sh` 了

**注**：alias的效力仅及于该次登入的操作。若要每次登入是即自动设好别名，可在.profile或.zshrc等环境变量配置文件中设定指令的别名

## test GitHub
