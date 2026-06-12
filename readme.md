# 主要学习怎么使用git

## git工具理解
首先git是一个分布式的文件管理工具。它可以一个人玩，也可以团队协作。

## 基础玩法
~~~
先初始化git环境
安装git
设置作者

可以用 git init <文件名> 在本目录初始化工作区
这就是本地仓库，这样就可以本地做git的文件管理了。

git add . #把文件提交到**暂存区**
git commit -m "这是第一次提交" # 把文件提交到本地仓库管理中
git log --oneline # 查看历史提交记录

git restore <文件名> # 撤销还未add 的文件
git restore --staged <文件名> ## 撤销已经add,未commit 的文件
git reset --hard <commit-hash> # 回退到指定版本

git branch #查看分支

git checkout -b <新分支> #创建并选择新分支，与svn不一样的是，不会创建新文件夹。是在本来文件上做管理。

git checkout <分支名> #选择分支

git merge <分支名> #合并分支至本分支

git branch -d <分支名> #删除选定分支


~~~

## 进阶玩法
github 远程分支<https://github.com/lisan-com/git-test.git> 克隆下来代码，只获取最新代码，不提交。
获取后的代码，进行二次开发。
使用远程分支<http://lisan@192.168.110.9:4004/r/test/git-test.git> 进行管理。

~~~
#克隆远端代码，把水果摊升级为水果档口
git clone https://github.com/lisan-com/git-test.git 水果档口

#重命名github的远端分支已做区分

git remote rename origin upstream

# 添加私有服务器为主源服务器 origin
git remote add origin http://lisan@192.168.110.9/r/test/git/git-test.git

# 此时你可以查看本地的远程
git remote -v #可以看到有两个远程

# origin 用来日常管理
# upstream 主要用来拉取

# 首次推送变更文件至 origin
git push -u origin master

~~~

### 日常场景

~~~
1.在本地写完功能提交团队
git add .
git commit -m "提交私有服务器"
git push origh master # 推送至指定服务器，指定分支

2.github 服务器项目更新了，需要同步更新，合并文件

git fetch upstream # 获取最新代码

git merge upstream/master #合并代码至本分支，有冲突手动解决后，再commit

git push origin master # 推送代码至私有服务器


~~~

## 通过这些操作可以双轨运行。