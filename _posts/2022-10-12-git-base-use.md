---
layout: post
title: Git基本命令
categories: [git]
description: Git基本命令
keywords: git
---
# Git 基本使用

#### 1. git 结构

![bg2015120901](https://i.loli.net/2021/11/11/VSxpb13r9IAlCLo.png)

* Workspace：工作区
* Index / Stage：暂存区
* Repository：仓库区（或本地仓库）
* Remote：远程仓库

#### 2. 文件状态变化周期

![image-20211111130823477](https://i.loli.net/2021/11/11/xC8XqMWerJSizp5.png)

* Untracked：未被跟踪的文件(新增的文件)，在idea中显示为红色
* Unmodified: 未作修改的文件，在idea中显示为白色
* Modified：作出修改的文件，在idea中显示为蓝色
* Staged：已经存入缓存区的文件，包括新增且add的文件以及修改的文件

#### 3. git 常用命令

~~~java
// 克隆仓库
git clone [url]
url:仓库地址
//将一个文件转变为一个git仓库，需要在该文件夹下执行
git init
//将 单个文件/某个文件夹 新建的文件加入暂存区
git add [文件名/目录]
//显示工作区及暂存区域中不同状态的文件
git status
//查看差异
git diff  //工作环境与暂存区
git diff --staged // 暂存区与最后提交
git diff master branchB  //master和branchB
//提交代码
git commit //将暂存区的代码提交到本地repo
git commit --amend //将上一次的提交信息进行修改，并在此次同时提交
//将文件移出暂存区
git reset Head [fileName]  //将Head指针上的分支中存在的file移出暂存区
git checkout -- [fileName] //放弃移出暂存区的文件的修改
//新建分支
git branch test //当前分支新建一个test分支
//切换分支
git checkout test //切换到test分支
git checkout -b test //当前分支新建一个test分支，并切换到test分支
//合并分支
git merge hotfix //将hotfix合并到当前分支
//删除hotfix分支
git branch -d hotfix
//获取分支列表
git branch //表明当前在master分支
  iss53
* master
  testing
//所有分支的最后一次提交
git branch -v
  iss53 93b412c fix javascript issue
* master 7a98805 Merge branch 'iss53'
  testing 782fd34 add scott to the author list in the readmes
//查看需要合并的分支
git branch --no-merged
//查看已经合并的分支
git branch --merged
//查看尚未合并到master的分支
git branch --no-merged master
//贮藏不想提交的工作
git stash
git stash push
//查看贮藏的文件
git stash list
//应用贮藏文件
git stash apply
git stash apply stash@{0}//应用单个贮藏
//从贮藏创建一个分支
git stash branch [branchname]
//项目同步
git fetch [remote] //同步项目的所有信息
//指定远程项目的情况下拉取数据
git pull
//推送到远程项目
git push orgin master  //将 master 分支推送到 origin 服务器
//拣选
git cherry-pick [versionNumber] //选取某个版本号的提交到当前分支
~~~

#### 点此开始Git学习：[开始Git](https://oschina.gitee.io/learn-git-branching/)

#### 点此阿里云盘下载Pro Git：[下载 Pro Git](https://www.aliyundrive.com/s/2s22GaXT21n)

