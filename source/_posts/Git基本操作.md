title: Git基本操作
date: 2023-02-13 16:10:15
categories:
tags:

---

## 远程操作
git clone [仓库地址]
拷贝一个Git仓库到本地

git merge [本地分支名]
将两个分支的内容进行合并

git rebase [本地分支名]
将两个分支的内容进行合并

git branch 
查看本地仓库分支和远程仓库分支

git remote add [shortname] [url]
添加远程版本库

git fetch
用于从远程获取代码库

git checkout [本地分支名]
切换本地分支

git pull [远程分支名]:[本地分支名]
从远程获取代码并合并到本地版本

git pull [远程分支名]:
如果远程分支是与当前分支合并，则冒号后面的部分可以省略。

git push origin HEAD -- force
强退至远程

## 创建仓库提交
git init
初始化仓库

git add .
添加当前目录下的所有文件到暂存区

git status
查看上次提交之后是否有对文件进行再次修改

git commit -m
将暂存区内容添加到本地仓库中

git push <远程主机名> <本地分支名>:<远程分支名>
将本地分支版本上传到远程并合并

git push <远程主机名> <本地分支名>
如果本地分支名与远程分支名相同，则可以省略冒号

## 回退版本
git reset --hard HEAD 
回退到上个版本

git reset --hard HEAD~n
回退到前n次提交之前

git reset --hard commit_id
进到指定的commit


---