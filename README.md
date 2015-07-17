# test
just a test repo

安装git

$ git config --global user.name "xxx"
$ git config --global user.email "xxx@sohu-inc.com"
$ mkdir learngit
$ cd learngit
$ pwd
$ git init 
vi readme.txt
Git is a version control system.
Git is free software.
git add readme.txt
git commit -m "wrote a readme file"
修改readme.txt内容
git status命令看看结果
$ git diff readme.txt 
git add readme.txt
git status
git commit -m "add distributed"
git status
$ git log查看更改记录 或者git log --pretty=oneline
退回上一版本
$ git reset --hard HEAD^
退回未来的某一版本
$ git reset --hard 83f143
查看命令和commit id
$ git reflog
git checkout -- readme.txt可以丢弃工作区的修改(例如撤销误删除)
用命令git reset HEAD file可以把暂存区的修改撤销掉,重新放回工作区
删除文件
$ git rm test.txt
$ git commit -m "remove test.txt"

创建SSH Key：
$ ssh-keygen -t rsa -C "xxx@sohu-inc.com"
$ cat ~/.ssh/id_rsa.pub 查看公钥

添加远程仓库
git remote add origin git@c.xxx.git
把本地库的所有内容推送到远程库上：$ git push -u origin master
用命令git clone克隆一个本地库到当前目录：
$ git clone git@c.xxx.git

创建dev分支并切换到dev分支：$ git checkout -b dev 	（$ git branch dev    	$ git checkout dev）
用git branch命令查看当前分支
切换到主分支：$ git checkout master
git merge命令用于合并指定分支到当前分支 $ git merge dev  		可查看历史的合并（禁用快速合并）：git merge --no-ff -m "merge with no-ff" dev
删除dev分支:  $ git branch -d dev
git branch -D <name>强行删除
查看分支的合并情况：
$ git log --graph --pretty=oneline --abbrev-commit

储藏现场工作：$ git stash   恢复现场：  git stash pop
查看远程库详细信息：git remote -v

hosts文件就在C:\Windows\system32\drivers\etc\hosts下

多人协作的工作模式通常是这样：

首先，可以试图用git push origin branch-name推送自己的修改；

如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

如果合并有冲突，则解决冲突，并在本地提交；

没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！

可以通过创建~/.gitignore_global并添加到git全局配置以减少每层目录的规则重复定义。
使用命令git config --global core.excludesfile ~/.gitignore_global 即可


.gitignore_global文件范例
复制代码
复制代码
# Compiled source #  
###################  
*.com  
*.class  
*.dll  
*.exe  
*.o  
*.so  
  
# Packages #  
############  
# it's better to unpack these files and commit the raw source  
# git has its own built in compression methods  
*.7z  
*.dmg  
*.gz  
*.iso  
*.jar  
*.rar  
*.tar  
*.zip  
  
# Logs and databases #  
######################  
*.log  
*.sql  
*.sqlite  
  
# OS generated files #  
######################  
.DS_Store  
.DS_Store?  
._*  
.Spotlight-V100  
.Trashes  
Icon?  
ehthumbs.db  
Thumbs.db  
run.sh
