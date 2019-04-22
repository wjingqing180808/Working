

## 1.安装

1. 下载window git

   ​	doanload:<https://git-scm.com/downloads>

2. 配置用户信息

   #git config --global user.name "wenjq"	--配置用户

   #git config --global user.email "wjingqing168@163.com"	--配置邮箱

   #git config --list 	--查看当前配置

​	

## 2.git仓库

- 初始化版本库

  #git init

- 添加文件到版本库

  #git add filename

  #git commit -m "create new filename"

- 查看仓库状态

  #git status

  

  



## 3.配置用户信息

- 配置用户名称

​	#git config --global user.name "wenjingqing"

- 配置用户邮箱

  #git config --global user.email "wjingqing@168@163.com"  

- 检测用户配置信息

  #git config --list

  

  

4.版本回退

​	#git log  --查看提交历史

​	#git reset --hard commit_id --回退版本

​	#git reflog --命令历史





## 5.工作区与暂存区

- 工作区:电脑里能看到的目录

- 暂存区:Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支`master`，以及指向`master`的一个指针叫`HEAD`

- 文件往Git版本库添加

  第一步是用`git add`把文件添加进去，实际上就是把文件修改添加到暂存区；

  第二步是用`git commit`提交更改，实际上就是把暂存区的所有内容提交到当前分支。

  因为我们创建Git版本库时，Git自动为我们创建了唯一一个`master`分支，所以，现在，`git commit`就是往`master`分支上提交更改。

  你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改

  



## 4.管理修改

- 工作区提交到暂存区撤销

  #git reset HEAD filename

- 丢弃工作区修改

  #git checkout -- filename

  

## 5.删除文件

- 从版本库中删除该文件，那就用命令`git rm`删掉，并且`git commit`

  #git rm filename 

  #git commit -m "delete filename"

- 从工作区删除文件，恢复版本区最新版本

  #git checkout -- filename



## 6.远程仓库

```
本地Git仓库和GitHub仓库之间的传输是通过SSH加密的， 创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有`id_rsa`和`id_rsa.pub`这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key
  #ssh-keygen -t rsa -C "wjingqing168@163.com"

登陆GitHub，打开“Account settings”，“SSH Keys”页面：然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴`id_rsa.pub`文件的内容：验证ssh 连接远程github
  #ssh -T git@github.com
```



### 6.1添加远程仓库

```
#git remote add origin git@github.com:michaelliao/learngit.git --本地仓库推送到github仓库
#git push -u origin master
	--由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
#git push origin master --本地推送

小结:
要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；
关联后，使用命令git push -u origin master第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；
```



### 6.2从远程仓库克隆

```
#git clone git@github.com:michaelliao/gitskills.git -- 克隆一个本地库
小结：
要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone命令克隆。
Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。
```



## 7.分支管理

### 7.1创建与合并分支

```
#git branch --查看分支
#git branch name --创建分支
#git checkout name --切换分支
#git checkout -b name --创建+切换分支
#git merge name --合并某分支到当前分支
#git branch -d name --删除分支

```

### 7.2解决冲突

```
# git log --graph --pretty=oneline --abbrev-commit --分支合并情况
```

​	











