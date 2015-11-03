#托管GitHub

##SSH密钥配置
###生成SSH Key

在本地客户端通过命令行直接生产SSH Key， 不输密码一路回车

	$ ssh-keygen -C 'xxxxxxx@qq.com' -t rsa

在～/.ssh/下生成两个密钥id_rsa，id_rsa.pub

	id_rsa，私钥
	id_rsa.pub　公钥，这个要保存Git server上，作为访问Git server的权限。

###添加公钥
登陆github系统。
点击右上角的Edit your profile---> Settings--->SSH keys ---> add keys，把你本地生成id_rsa.pub的密钥复制到里面（key文本框中）， 点击 add key 就ok了。

###测试连接是否成功，

在git bash中执行以下命令完成： 

    ssh -T git@github.com

###配置      
####必须配置项

第一个要配置的是你个人的用户名称和电子邮件地址。这两条配置很重要，每次 Git 提交时都会引用这两条信息，说明是谁提交了更新，所以会随更新内容一起被永久纳入历史记录：

    $ git config --global user.name "Ircc"                  //配置用户名
    $ git config --global user.email happyhaoyun@qq.com     //配置邮箱
    $ git config --global credential.helper store           //记住用户名和密码 只要输入一次就可以自动记住了
    $ git config --global core.editor gvim                  //配置文本编辑器
    
    $ git config --list                                     //查看配置信息

####中文乱码解决

    $ git config --global core.quotepath false           //core.quotepath设为false的话，就不会对0x80以上的字符进行quote。中文显示正常
    --$ git config --global gui.encoding utf-8           //设置git gui的界面编码
    --$ git config --global i18n.commitencoding utf-8    //commit log 提交时使用 utf-8 编码，可避免服务器上乱码，同时与linux上的提交保持一致！
    --$ git config --global i18n.logoutputencoding gbk   //使得在 $ git log 时将 utf-8 编码转换成 gbk 编码，解决Msys bash中git log 乱码。
    --$ export LESSCHARSET=utf-8                         //使得 git log 可以正常显示中文（配合i18n.logoutputencoding = gbk)，在 /etc/profile 中添加

    
    
##版本测试

###从github上下拉代码到本地
    $ git clone https://github.com/Ircc/test.git
    
###将改动的地方添加到版本管理器 .代表所有文件
    $ git add . 
    $ git add -A
         
###提交到本地的版本控制库里，
    $ git  commit -m "changes log"   //引号里面changes log是你对本次提交的说明信息。
    
###将你本地的仓库提交到你的github账号里
    $ git push -u origin master     //将你本地的仓库提交到你的github账号里
    $ git pull origin master        //先把远程服务器github上面的文件拉下来

    
##常用git命令集合
    $ git init            //初始化
    $ git log             //显示版本日志
    $ git status          //查询状态
    & git diff            //比较差异
    & git revert          //反转撤销提交







      

      
      
      
      
      
      
      
      
      
      
      
      