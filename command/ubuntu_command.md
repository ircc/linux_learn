#ubuntu常用命令

###安装卸载软件
安装：sudo apt-get install softname
卸载：sudo apt-get remove --purge softname
    --purge 选项表示彻底删除改软件和相关文件

###wine 软件
删除:sudo dpkg -r  wine-qqintl

    
###关机重启命令知识。

####重启命令：
* reboot
* shutdown -r now 立刻重启(root用户使用)
* shutdown -r 10 过10分钟自动重启(root用户使用)
* shutdown -r 20:35 在时间为20:35时候重启(root用户使用)

如果是通过shutdown命令设置重启的话，可以用shutdown -c命令取消重启

####关机命令：
* halt   立刻关机
* poweroff 立刻关机
* shutdown -h now 立刻关机(root用户使用)
* shutdown -h 10 10分钟后自动关机

如果是通过shutdown命令设置关机的话，可以用shutdown -c命令取消重启


###Ubuntu系统清理
* sudo apt-get autoclean                                 清理已卸载软件的安装包
* sudo apt-get clean                                     清理未卸载软件的安装包
* sudo apt-get autoremove                                清理系统不再需要的孤立的软件包
* sudo deborphan | xargs sudo apt-get -y remove --purge  清理孤立的库文件




