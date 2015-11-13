##sudo安装设置
    apt-get install sudo
安装后，就可以给你的帐号设置管理员权限了
    vim /etc/sudoers

##VMware tools
    sudo apt-get install make
    sudo apt-get install gcc
    sudo aptitude install linux-headers-`uname -r`

##配置locales
dpkg-reconfigure locales

##增加ll支持
    ~/.bashrc 文件里加一句 alias ll='ls -l' 
##增加add-apt-repository支持

sudo apt-get install python-software-properties 
sudo apt-get install software-properties-common

##快捷键
gnome-terminal


#
### testing
deb http://mirrors.ustc.edu.cn/debian testing main contrib non-free
deb-src http://mirrors.ustc.edu.cn/debian testing main contrib non-free
deb http://mirrors.ustc.edu.cn/debian testing-proposed-updates main contrib non-free
deb-src http://mirrors.ustc.edu.cn/debian testing-proposed-updates main contrib non-free
deb http://mirrors.ustc.edu.cn/debian testing-updates main contrib non-free
deb-src http://mirrors.ustc.edu.cn/debian testing-updates main contrib non-free

### Debian Volatile
deb http://volatile.debian.org/debian-volatile/ lenny/volatile main contrib non-free
deb http://archive.debian.org/debian-archive/debian lenny main contrib non-free
deb http://archive.debian.org/debian-archive/debian-security lenny/updates main contrib non-free
deb http://archive.debian.org/debian-archive/debian-volatile lenny/volatile main contrib non-free

###Key
gpg --keyserver subkeys.pgp.net --recv-keys KEY_ID

##构建自己的debian软件包仓库 
http://blog.csdn.net/shendl/article/details/7934877