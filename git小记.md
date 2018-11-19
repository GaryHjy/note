
修改设置  
$ git config --global user.name "Your Name"  
$ git config --global user.email "email@example.com"

创建空目录  
$ mkdir learngit  
$ cd learngit  
$ pwd  

git init  
初始化一个Git仓库，将目录变成Git可以管理的仓库。其目录下会多了个.git的目录（默认为隐藏的，ls -ah命令可以显示）

git add <file>   
添加文件到仓库（类似于加入暂存夹）  

git commit -m "注释"  
将文件提交到仓库，"注释"就是做标记，方便查找  

git status  
查看当前仓库的状态，哪些文件做了修改。  

git diff <file>  
如果git status告诉你有文件被修改过，git diff查看修改内容。  

git log  
查看提交历史。  

git reflog  
查看命令历史 

git log --pretty==oneline  
精简输出的信息  

git reset --hard HEAD^  
回退到上一个版本。

git reset --hard <commit_id>  
回退到指定id的版本

git diff HEAD -- <file>  
查看工作区和版本库里面最新版本的区别  

git checkout -- <file> 
把<file>文件在工作区的修改全部撤销。  
1.如果<file>工作区做了修改，直接运行git checkout -- <file>撤销  
2.如果<file>工作区做了修改并添加到了暂存区，先运行git reset HEAD  <file>,再运行git checkout -- <file>撤销  

git rm <file>  
删除一个文件  

ssh-keygen -t rsa -C "youremail@example.com"  
一直回车，在用户主目录会生成.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

git remote add origin git@github.com:github-name/repo-name.git  
关联远程库  

git push -u origin master  
第一次推送master分支的所有内容。  
我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

git push origin master  
推送最新修改

git clone git@github.com:path/github-name.git  
克隆一个本地库

git branch  
查看分支  

git branch <name>  
创建分支  

git checkout <name>  
切换分支  

git checkout -b <name>  
创建+切换分支   

git merge <name>  
合并某分支到当前分支  

git branch -d <name>  
删除分支  

git log --graph  
查看分支合并图  

git log --graph --pretty=oneline --abbrev-commit  
查看分支合并图（精简）  

git merge --no-ff -m "注释" <name>  
因为合并要创建一个新的commit，所以加上-m参数，把commit描述写进去 
--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并 

git stash  
将当前分支的工作现场“储藏”起来。  

git stash pop  
恢复当前分支的工作现场，并把stash的内容删除  

git stash apply  
git stash drop  
恢复当前分支的工作现场  
把stash的内容删除  

git stash list  
查看stash的内容  

git branch -D <name>  
强行删除分支。用于丢弃一个没有被合并过的分支。  

git remote  
查看远程库的信息  

git remote -v  
查看远程库更详细的信息,如果没有推送权限，就看不到push的地址。  

git push origin <branch-name > 
推送分支,如果推送失败，先用git pull抓取远程的新提交  

git pull  
抓取远程的新提交  

git checkout -b branch-name origin/branch-name  
在本地创建和远程分支对应的分支，本地和远程分支的名称最好一致  

git branch --set-upstream branch-name origin/branch-name  
建立本地分支和远程分支的关联  


