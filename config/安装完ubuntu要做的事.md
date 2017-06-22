##安装完ubuntu要做的事

####清理系统

1. 删除libreoffice
	libreoffice虽然是开源的，但是Java写出来的office执行效率实在不敢恭维，装完系统后果断删掉

	sudo apt-get remove libreoffice-common


2. 删除Amazon的链接
	sudo apt-get remove unity-webapps-common
    sudo apt-get remove unity-lens-shopping


3. 删掉基本不用的自带软件（用的时候再装也来得及）
	sudo apt-get remove thunderbird totem rhythmbox empathy brasero simple-scan gnome-mahjongg aisleriot gnome-mines cheese transmission-common gnome-orca webbrowser-app gnome-sudoku  landscape-client-ui-install

	sudo apt-get remove onboard deja-dup

这样系统就基本上干净了。


####设置时间使用UTC
	sudo vim /etc/default/rcS
	将UTC=no改为UTC=yes

####更新系统
	sudo apt-get update&&sudo apt-get upgrade

####Numix 主题
    sudo add-apt-repository ppa:numix/ppa
    sudo apt-get update
    sudo apt-get install numix-gtk-theme numix-icon-theme numix-icon-theme-circle numix-wallpaper-saucy
    sudo apt-get install numix-gtk-theme

####安装软件
1. 安装Vim

	sudo apt-get install vim
	可以下载配置:https://github.com/ma6174/vim

2. 安装wps

	sudo apt-get install wps-office

3. 安装git

	sudo apt-get install git

4. 安装CMake

    sudo apt-get install cmake

5. 安装经典菜单指示器

	sudo add-apt-repository ppa:diesch/testing
	sudo apt-get update
	sudo apt-get install classicmenu-indicator

6. 安装系统指示器SysPeek

	sudo add-apt-repository ppa:nilarimogard/webupd8
	sudo apt-get update
	sudo apt-get install syspeek

7. Compizconfig设置管理器
	sudo apt-get install compizconfig-settings-manager

8. Unity-Tweak

	sudo apt-get install unity-tweak-tool

9. ubuntu-tweak

	sudo apt-get install ubuntu-tweak

10. Preload 一款通过预加载方式来提高性能的工具

	sudo apt-get install preload

11. WizNote为知笔记

	sudo add-apt-repository ppa:wiznote-team
	sudo apt-get update
	sudo apt-get install wiznote

12. 安装adobe-flash播放器
    sudo apt-get install flashplugin-installer

13. 安装新立得软件包管理器
    sudo apt-get install synaptic

14. 右键终端
    sudo apt-get install nautilus-open-terminal

15. 字体管理器
    sudo apt-get install font-manager

16. 文件搜索工具
    sudo apt-get install catfish
    
17. chm阅读器
    sudo apt-get install xchm
    chmsee：http://kr.archive.ubuntu.com/ubuntu/pool/universe/c/chmsee/chmsee_1.3.0-2ubuntu2_amd64.deb
    
####c++ 开发环境
1. 安装源码编译环境
	
	sudo apt-get install build-essential
    
2. 安装C/C++帮助文档
	
	sudo apt-get install manpages-dev                         #C API
    sudo apt-get install manpages-posix                       #posix function
    sudo apt-get install manpages-posix-dev                   #posix develop documents
    sudo apt-get install libstdc++6-4.3-doc                   #C++ API

3. gedit插件 gedit虽然不作开发用，但是有时候要看下代码

    sudo apt-get install gedit-plugins
    sudo apt-get install gedit-dev
    sudo apt-get install gedit-developer-plugins
    sudo apt-get install gedit-source-code-browser-plugin



如果在VMware虚拟机中需要安装vmware-tools
sudo apt-get install open-vm-toolbox
sudo apt-get install kubuntu-desktop




