##sudo��װ����
    apt-get install sudo
��װ�󣬾Ϳ��Ը�����ʺ����ù���ԱȨ����
    vim /etc/sudoers

##VMware tools
    sudo apt-get install make
    sudo apt-get install gcc
    sudo aptitude install linux-headers-`uname -r`

##����locales
dpkg-reconfigure locales

##����ll֧��
    ~/.bashrc �ļ����һ�� alias ll='ls -l' 
##����add-apt-repository֧��

sudo apt-get install python-software-properties 
sudo apt-get install software-properties-common

##��ݼ�
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

##�����Լ���debian������ֿ� 
http://blog.csdn.net/shendl/article/details/7934877