# Git 命令速查表

## git设置
	$> git config --list #查看本地git设置
	$> git config --global credential.helper store      #记住用户名和密码 只要输入一次就可以自动记住了
	$> git config --global core.quotepath false         #core.quotepath设为false的话，就不会对0x80以上的字符进行quote。中文显示正常
    $> git config --global gui.encoding utf-8           #设置git gui的界面编码
    $> git config --global i18n.commitencoding utf-8    #commit log 提交时使用 utf-8 编码，可避免服务器上乱码，同时与linux上的提交保持一致！
    $> git config --global i18n.logoutputencoding gbk   #使得在 $ git log 时将 utf-8 编码转换成 gbk 编码，解决Msys bash中git log 乱码。
    $> export LESSCHARSET=utf-8                         #使得 git log 可以正常显示中文（配合i18n.logoutputencoding = gbk)，在 /etc/profile 中添加

## AutoCRLF
	$> git config --global core.autocrlf true  #提交时转换为LF，检出时转换为CRLF 
	$> git config --global core.autocrlf input #提交时转换为LF，检出时不转换
	$> git config --global core.autocrlf false #提交检出均不转换
	
## 创建版本库

    $> git clone <url> #克隆远程版本库
    $> git init #初始化本地版本库

## 修改和提交

    $> git status #查看状态
    $> git diff #查看变更内容
    $> git add . #跟踪所有改动过的文件
    $> git add <file> #跟踪指定的文件
    $> git mv <old> <new> #文件改名
    $> git rm <file> #删除文件
    $> git rm --cached <file> #停止跟踪文件但不删除
    $> git commit -m “commit message” #提交所有更新过的文件
    $> git commit --amend #修改最后一次提交

## 查看提交历史

    $> git log #查看提交历史
    $> git log -p <file> #查看指定文件的提交历史
    $> git blame <file> #以列表方式查看指定文件的提交历史

## 撤消

    $> git reset --hard HEAD #撤消工作目录中所有未提交文件的修改内容
    $> git checkout HEAD <file> #撤消指定的未提交文件的修改内容
    $> git revert <commit> #撤消指定的提交

## 分支与标签

    $> git branch #显示所有本地分支
    $> git checkout <branch/tag> #切换到指定分支或标签
    $> git branch <new-branch> #创建新分支
    $> git branch -d <branch> #删除本地分支
    $> git tag #列出所有本地标签
    $> git tag <tagname> #基于最新提交创建标签
    $> git tag -d <tagname> #删除标签

## 合并与衍合

    $> git merge <branch> #合并指定分支到当前分支
    $> git rebase <branch> #衍合指定分支到当前分支

## 远程操作

    $> git remote -v #查看远程版本库信息
    $> git remote show <remote> #查看指定远程版本库信息
    $> git remote add <remote> <url> #添加远程版本库
    $> git fetch <remote> #从远程库获取代码
    $> git pull <remote> <branch> #下载代码及快速合并
    $> git push <remote> <branch> #上传代码及快速合并
    $> git push <remote> :<branch/tag-name> #删除远程分支或标签
    $> git push --tags #上传所有标签
    
## 创建本地代码仓库
假设，当前的开发目录叫"~/projects"，而坚果云路径为"~/gidir"，进行如下操作：

	$> cd ~/projects
    $> git init            （注释：初始化git repository）
    $> git add .
    $> git commit -m “first commit”

    $> mkdir -p ~/gidir/project.git  （注释：在本地目录中创建bare git repository）
    $> cd ~/gidir/project.git
    $> git init –bare

    $> cd ~/project   （注释：push代码到本地目录中）
    $> git remote add orig ~/gidir/project.git
    $> git push orig master

### 定期运行GC(垃圾回收），减少文件数目和节约空间

	$> cd ~/gidir
	$> git gc



## git技巧集合

### git 放弃本地修改 强制更新

	$> git fetch --all
	$> git reset --hard origin/master
	
### git 重置 source 分支-恢复历史版本

	$> git reset --hard 6afc28  # 恢复版本号为6afc289029828c6bed876f2ea54d98c03b77bfde  不加 --hard表示不覆盖本地修改

### git add 撤消
	如果是撤销所有的已经add的文件:
	$> git reset HEAD .

	如果是撤销某个文件或文件夹：
	$> git reset HEAD -filename

### git 强制 push 更新远程分支

	$> git push origin source -f
	
### git 备份当前的分支到 backup_commit

	$> git tag backup_commit
	
### git 代码冲突解决
	$> git stash
	$> git pull
	$> git stash pop
	然后可以使用Git diff -w +文件名 来确认代码自动合并的情况.


## git学习网址

* [git-scm官网文档](http://git-scm.com/book/zh/v2)
* [廖雪峰的官方网站-Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)