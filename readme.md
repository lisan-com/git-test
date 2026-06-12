# 主要学习怎么使用git

## git工具理解
首先git是一个分布式的文件管理工具。它可以一个人玩，也可以团队协作。
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

# 进阶玩法
github 远程分支<https://github.com/lisan-com/git-test.git> 克隆下来代码，只获取最新代码，不提交。
获取后的代码，进行二次开发。
使用远程分支<http://lisan@192.168.110.9:4004/r/test/git-test.git> 进行管理。
