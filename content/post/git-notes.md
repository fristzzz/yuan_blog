---
title: git notes
date: 2023-03-02 18:47:21
categories: 
    - coding
tags:
---

以前没怎么用git，也就clone，push，add，commit这些，最近两个电脑同步笔记，要用不少git操作。发现以前看的全忘光了，再重新复习一下。

---

# 分支内操作

## 创建仓库, 提交修改



`git init` 在当前目录创建仓库
`git init filename` 在指定目录下创建仓库

`git add .` 将修改添加到暂存区
`git status` 可以查看仓库状态，git会告诉你暂存区有无修改正在等待提交
`git commit -m "some describe"` 将暂存区的所有修改提交到分支，-m参数为日志内容，linux下用单引号，windows下用双引号

如果`git status`告诉你有文件被修改过，用`git diff`可以查看修改内容。


## 版本回退



### 回退

`git log` 可以查看提交日志(commitment log) 
`git log --pretty=oneline` 查看精简版，只有id和提交信息


回退到上一个版本： `git reset --hard HEAD^` 其中 `HEAD^` 即上一个版本
上上个版本为 `HEAD^^`

### 撤销回退

如果回退之后想要撤销回退，使用 `git reflog` 查看head记录
并用 `git reset --hard <id>` 来回到之前的版本

## 撤销修改



- `git checkout -- <filename>` 可以丢弃工作区的修改
	- 如果文件自修改后还没有被放到暂存区，撤销修改就回到和版本库一样的状态
	- 如果文件已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态
总之，就是让这个文件回到最近一次 `git commit` 或者 `git add` 的状态

- `git reset HEAD <filename>` 可以把暂存区的修改回退到工作区， HEAD表示最新的版本

# 远程仓库

## 创建秘钥

`ssh-keygen -t rsa -C "example@email.com"`
默认目录：`~/.ssh/`
其中 `id_rsa` 是私钥， `id_rsa.pub` 是公钥
打开github，添加ssh秘钥。复制 `id_rsa.pub` 内容到key中。

> 添加完秘钥还不能push的，要把https:改成git:

## 添加远程仓库

`git remote add origin git@github.com:xxx/xxx.git`
远程库的名字就是origin，这是git默认的叫法
`git push -u origin master`
第一次推送加上-u参数可以把本地的master和远程的master分支关联起来，在以后的push或pull的时候就可以简化命令

## 删除远程库

`git remote rm <name>`

# 分支管理

## 创建与合并分支

`git checkout -b dev` 创建分支
-b 表示创建并切换，相当于
```git
git branch dev
git checkout dev
```

`git branch` 查看当前分支

把dev上的修改合并到master上：
```
git checkout master
git merge dev 
```
`git merge` 用于合并指定分支到当前分支。
`git branch -d dev` 删除分支

`git switch xxx` 也可以切换分支
`git switch -c xxx` 创建并切换

`git log --graph` 查看分支合并图

合并分支时，加上 `--no-ff` 参数就可以用普通模式合并，合并后的历史有分支，能看出曾经做过合并，而 `fast forward` 合并就看不出来曾经做过合并。
