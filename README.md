# setsail
myFirstRepository

2015-12-28
yacc -d grammar.y
make: yacc: Command not found
Run the following command on your terminal to install bison, yacc executables and configurations.yacc comes along with bison
Also you need byacc for a full functional yacc
sudo apt-get install bison -y
sudo apt-get install byacc -y

fatal error: netinet/sctp.h: No such file or directory
下载lksctp-tools-1.0.16.tar.gz软件包并安装。

W: Not using locking for read only lock file /var/lib/dpkg/lock
E: Unable to write to /var/cache/apt/
E: The package lists or status file could not be parsed or opened.

2015-12-29
./bootstrap: line 4: libtoolize: command not found
安装libtool*  在重新执行 就ok了

./bootstrap: line 5: aclocal: command not found
autogen.sh脚本依赖于autoreconf来调用autoconf，automake，aclocal和其它相关工具，
丢失的aclocal是automake包的一部分，因此，要修复该错误，请安装以下包
在Debian，Ubuntu或Linux Mint上：
$ sudo apt-get install automake
在CentOS，Fedora或RHEL上：
$ sudo yum install automake
ubuntu下安装ccmake
sudo apt-get install cmake-curses-gui

Makefile:76: recipe for target 'all' failed


buildinfo.sh: 13: buildinfo.sh: svn: not found
buildinfo.sh: 1: buildinfo.sh: svnversion: not found
apt-get install subversion

2016-01-04
安装openssl，make install时出现
cms.pod around line 457: Expected text after =item, not a number
……
解决方法：sudo rm -f /usr/bin/pod2man

[ 88%] Generating src/configparser/MMEConfig.c
CMakeFiles/mme.dir/build.make:54: recipe for target 'src/configparser/MMEConfig.c' failed
make[2]: *** [src/configparser/MMEConfig.c] Error 1
CMakeFiles/Makefile2:275: recipe for target 'CMakeFiles/mme.dir/all' failed
make[1]: *** [CMakeFiles/mme.dir/all] Error 2
Makefile:76: recipe for target 'all' failed
make: *** [all] Error 2
需要安装asn1c
下载地址：http://lionet.info/asn1c/compiler.html
在CMakeLists.txt中有说明
tools/configparser/genparser.sh
安装后asn1c -h没有 -gen-APER选项
把在tools/configparser/下生成的 *.c文件拷贝到src/configparser/目录下
把在tools/configparser/下生成的 *.h文件拷贝到include/configparser/目录下
注释掉CMakeLists.txt中有关MMEConfig.c的相关行后出现
undefined reference to `asn_DEF_MMEConfig'
是因为在/src/configparser下没有生成MMEConfig.c文件。

buildinfo.sh: 13: buildinfo.sh: svn: not found
buildinfo.sh: 1: buildinfo.sh: svnversion: not found
安装subversion
 subversion相关软件下载 http://www.tigris.org/servlets/NewsItemView?newsItemID=1940

安装subversion时出现configure: error: APR could not be located. Please use the --with-apr option.
./configure --with-apr=/usr/local/apr

Unable to init server: Could not connect: Connection refused
(wireshark:1617): Gtk-WARNING **: cannot open display:
安装Xmanager
2016-01-14
Debian下安装apache2
#apt-get install apache2
#apache2ctl -k start时出现：apache2: Could not reliably determine the server's fully qualified domain name, using 127.0.1.1 for ServerName
需要在目录/etc/apache2/下新建httpd.conf文件，并在此文件中加入ServerName 127.0.0.1:80，之后在本目录下的apache2.conf文件中添加Include httpd.conf
启动：sudo apache2ctl -k start
停止：sudo apache2ctl -k stop
重新启动：sudo apache2ctl -k restart

2016-01-15
Connecting to 192.168.16.108:22...
Could not connect to '192.168.16.108' (port 22): Connection failed.
sudo apt-get install openssh-server
sudo /etc/init.d/ssh restart
ps aux | grep ssh

wget http://www.linuxvirtualserver.org/software/kernel-2.6/ipvsadm-1.26.tar.gz(获得ipvsadm)
安装ipvsadm-1.26时出现如下错误1：
In file included from libipvs.h:13:0,
                 from libipvs.c:23:
ip_vs.h:15:29: fatal error: netlink/netlink.h: 没有那个文件或目录
apt-get install libpopt-dev
apt-get install libnl-dev (此时会附带安装libnl)
如果是CentOS应该是
yum install libpopt-devel
yum install libnl-devel

安装ipvsadm-1.26时出现如下错误2:
ipvsadm.o: In function `parse_options':
/home/qizhongwei/install_softwares/ipvsadm-1.26/ipvsadm.c:432: undefined reference to `poptGetContext'
……
collect2: ld returned 1 exit status
make: *** [ipvsadm] Error 1
安装popt-1.7.tar.gz

安装popt-1.7时会出现：
checking for GNU xgettext... configure: error:
  *** GNU gettext is required. The latest version
  *** is always available from ftp://ftp.gnu.org/gnu/gettext/.
apt-get install gettext

2016-01-20
scripts/kconfig/lxdialog/dialog.h:38:20: fatal error: curses.h: No such file or directory
apt-get install libncurses5-dev

2016-01-25
在CentOS下通过yum install wireshark后不能运行
因为wireshark包本身只包含文本工具，这样无法使用wireshark和图形界面，但是提供了抓包的基本功能。wireshark-gnome才提供wireshark(UI)工具，其依赖于wireshark RPM。
所以需要安装wireshark-gnome
yum install wireshark-gnome

2016-01-27
The following packages have unmet dependencies: ……
run 'apt-get -f install' to correct

2016-01-28
Ubuntu显示”device not managed”
打开文件/NetworkManager/NetworkManager.conf文件，将其中的managed=false改为managed=true，然后执行 service network-manager restart

2016-07-11
ubuntu 显示networking disabled 解决办法
第一步，先把网络停掉
sudo service network-manager stop
第二步，清理对应的网络状态文件
sudo rm /var/lib/NetworkManager/NetworkManager.state
第三步，启动网络即可
sudo service network-manager start



2016-03-16
安装libzdb时在运行 ./configure 时出现如下问题：
checking for library containing sqlite3_open... no
解决方法:sudo apt-get install libsqlite3-dev

2016-06-17
-- Check for working CXX compiler: CMAKE_CXX_COMPILER-NOTFOUND 
CMake Error: your CXX compiler: "CMAKE_CXX_COMPILER-NOTFOUND" was not found. Please set CMAKE_CXX_COMPILER to a valid compiler path or name. 

解决:
1. 安装g++：
sudo apt-get install g++

2. 设置编译器路径：
cmake -D CMAKE_CXX_COMPILER="g++" CMAKE -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX:PATH="/usr/local" .

2016-06-29
Filesystem in Read-only mode (Raspberry Pi)
按照网上的修复文件系统：
fsck -y /dev/mmcbkl0p5
重启无果。
mount -o remount rw /
执行后，文件系统正常了，马上更新了系统，可是重启还是老样子。
解决问题
现象是升级系统后或，出现的这个情况。
Just in /boot/cmdline.txt, add rw just before rootwait.
Well done.
https://archlinuxarm.org/forum/viewtopic.php?f=31&t=8321

2016-07-09
No Route to Host from  slave/10.21.0.231 to master:18025
防火墙的问题，需要关闭防火墙：service iptables stop

2016-08-18
Linux统计/监控工具SAR
sudo apt-get install sysstat

2016-10-11
用 ssh 命令连接服务器之后，如果一段时间不操作，再次进入 Terminal 时会有一段时间没有响应，然后就出现错误提示：
Write failed: Broken pipe
只能重新用 ssh 命令进行连接。
解决方法
方法一：如果您有多台服务器，不想在每台服务器上设置，只需在客户端的 ~/.ssh/ 文件夹中添加 config 文件，并添加下面的配置：
ServerAliveInterval 60
方法二：如果您有多个人管理服务器，不想在每个客户端进行设置，只需在服务器的 /etc/ssh/sshd_config 中添加如下的配置：
ClientAliveInterval 60
方法三：如果您只想让当前的 ssh 保持连接，可以使用以下的命令：
$ ssh -o ServerAliveInterval=60 user@sshserver

2016-10-11
添加用户
useradd -m -g users -d /home/raspbx raspbx

重新安装ssh
sudo apt-get --reinstall install openssh-server openssh-client

