# Git 最简协作
[[_TOC_]]

##  背景  

一个项目如果只有一名开发者，那么根本不会涉及到协同的问题。但是，随着我们开发的软件功能越来越全、要求越来越高。又分为前端、后端，又有很多不同的功能需要分团队开发。团队成员越来越多，成员之间的协同就需要受到重视。否则，协同上的短板很容易成为挖坑和填坑的过程。  

好的协同需要好的工具，更需要好的流程。Git是目前应用比较广泛的协同开发工具。本文就以Git为例来介绍协同开发的过程。

开始前，需要记住这几个概念
- working directory（working tree） 当前工作区，你对代码/文件的任何修改, 都会记录在工作区内. 它的版本比暂存区的还要新, 添加追踪后, 暂存区的版本会跟工作区的版本一致
- index（staged area） 暂存区，暂存区的版本会比本地代码库的版本新, 是你待提交的版本, 提交之后, 本地代码库的版本会跟暂存区的版本一致
- remote  远程版本库, 也就是 Gitlab 上的仓库
- repository  本地代码库, 是你本地的代码仓库


##  操作
### 第一次协作
1. 打开 Terminal
2. 进入空文件夹
	- 找一个操作方便的空文件夹
	- 命令：** `【|】`   + 文件夹地址**
3. clone repository
	- 把远程仓库克隆 （下载）到本地
	- 命令：**git clone+ 远程仓库地址**
	- 此命令默认 clone master 和 branches
	- 分支隐藏
	- 但用命令：**git checkout 分支名称**，可以切换到隐藏分支中

![](https://tva1.sinaimg.cn/large/007S8ZIlly1ghjr0caj91j31iu0nyaei.jpg)

4. （可选）单独克隆分支，避免分支切换混乱
	- 命令：git clone -b <指定分支名> <远程仓库地址> <文档名>
	- 如果不指定文档名，文档名默认为远程仓库名称
5. 创建分支
	- 命令：**git branch 分支名称**
	- 自己的功能分支
	- 每个成员负责的项目部分在此分支进行 git 活动

### 日常协作
1. 打开 Terminal
2. 进入本地仓库
	- 命令：** `【|】`   本地仓库地址**
3. 切换到自己的功能分支
	- 命令：**git checkout 分支名称**

👀 接下来两个模块是完整动作，每次打包进行，顺序不能错，步骤不能少 👀

#### 创建文件夹或文件
1. 创建
	- 命令：**touch 文件名.后缀**
2. （可选）编辑器编辑完成后，保存
3. 添加到暂存区
	- 命令：**git add 文件名**
4. 提交
	- 命令：**git commit -m "提交信息"**
	- 由暂存区提交到本地仓库 git commit -m “提交信息”，由暂存区提交到本地仓库
5. 上传
	- 命令：**git push**

#### 删除文件夹或文件
1. 删除
	- 命令：**git rm 文件名**  将删除的文件添加到暂存区
2. 添加到暂存区
	- 命令：**git add 文件名**
3. 提交
	- 命令：**git commit -m "提交信息"**
	- 由暂存区提交到本地仓库 git commit -m “提交信息”，由暂存区提交到本地仓库
4. 上传
	- 命令：**git push**

💡删除文件后记得提交

## Ref
- [Git remove a file from a branch, keep it in the master - Stack Overflow](https://stackoverflow.com/questions/37422221/git-remove-a-file-from-a-branch-keep-it-in-the-master)
- [Wiki 创建指南](https://gitlab.com/101camp/10py/tasks/-/wikis/HandBooks/HbUsageWiki)
- [Git 使用全景](https://gitlab.com/101camp/10py/tasks/-/wikis/How2/How2UseGit)
- [HbUsageWiki · Wiki · 101Camp / 10py / tasks · GitLab](https://gitlab.com/101camp/10py/tasks/-/wikis/HandBooks/HbUsageWiki)

## ChangeLog
- 210330 14:37 0.1h Reina 从 [[我们的 Git 协同流程 · GitLab](https://gitlab.com/101camp/10py/tasks/-/issues/39) 迁移至 GitHub
- 200817 18:31 0.5h Reina fix typo
- 200808 21:52 0.5h Reina init