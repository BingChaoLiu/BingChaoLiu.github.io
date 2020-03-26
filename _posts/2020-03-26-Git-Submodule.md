---
layout: post
title:  "Git Submodule"
date:   2020-03-26 00:16:00
categories: Git
tags: 原创
author: 渐层鱼骨刺
---

## 概述

项目分为多个模块，每个模块有各自的`git`仓库。如何保证各个项目模块的独立，以及版本的统一（Tag标记）。git给出的解决方案是使用**子模块** 。

> 子模块允许你将一个 Git 仓库作为另一个 Git 仓库的子目录。 它能让你将另一个仓库克隆到自己的项目中，同时还保持提交的独立。





## 开始使用

### 添加子模块

将一个已存在的Git仓库添加为正在工作的仓库`A`的子模块，可以使用命令：`git submodule add <url> <path>`

```
$ git submodule add git@192.168.1.239:NewLauncher/gulf.git gulf
Cloning into 'gulf'...
remote: Counting objects: 11, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 11 (delta 0), reused 11 (delta 0)
Unpacking objects: 100% (11/11), done.
Checking connectivity... done.
```

以上代码会在当前模块创建`gulf`目录并将远程仓库的代码克隆到该仓库。<path>可以根据实际需求设置，若不填写该值，默认为当前目录。

如果此时执行`git status`命令，会出现以下结果：

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   .gitmodules
	new file:   gulf
```

- `.gitmodule`

`A`仓库的根目录生成`.gitmodule`文件，该配置文件保存了项目 URL 与已经拉取的本地目录之间的映射：

```
[submodule "gulf"]
   path = gulf
   url = git@192.168.1.239:NewLauncher/gulf.git
```

如果有多个子模块，该文件中就会有多条记录。 要重点注意的是，该文件也像 `.gitignore` 文件一样受到（通过）版本控制。 它会和该项目的其他部分一同被拉取推送。

- `commit id` 映射文件

新生成的`gulf`文件映射的是当前`gulf`代码最新的`commit id`。仓库代码正是通过此文件映射到子模块的指定`commit id`。

代码提交到远程仓库可看到映射文件的展示方式：

![](https://picture-group.oss-cn-hangzhou.aliyuncs.com/img/git_submodule_origin.png)



### 配置子模块

子模块添加后，子模块中的代码处于指定commit id的游离分支，为了确保切换到指定的分支，需执行以下操作：

- `git config -f .gitmodules submodule.gulf.branch master`

  >  于`.gitmodule`文件会生成分支配置项。

- `git submodule foreach -q --recursive 'git checkout $(git config -f $toplevel/.gitmodules submodule.$name.branch || echo master)'`

  >  批量切换子模块到指定分支。

### 模块更新

当子模块有已修改的代码，或者有最新的提交时，在主模块使用`git status` 会提示出来，若修改需要维护，请及时上传最新映射文件。

![](https://picture-group.oss-cn-hangzhou.aliyuncs.com/img/git_submodule_modify.png)

- `new commits`子模块中有新的提交
- `modified content`子模块中有新的修改，并未提交

### 克隆包含子模块的项目

通常情况下我们使用Git克隆项目的操作是：`git clone <url>`，如果我们要克隆的项目中含有子模块使用之前按的命令后的文件目录中虽然有子模块的目录但是目录为空文件夹。含有子模块的项目初始化完整命令如下：

1. `git clone <url>` 克隆主模块项目
2. `git submodule init` 初始化本地配置文件
3. `git submodule update` 从该项目中抓取所有数据并检出父项目中列出的合适的提交

现在子模块目录是处在和之前提交时相同的状态了。

**more easy ...**

如果给 `git clone` 命令传递 `--recurse-submodules` 选项，它就会自动初始化并更新仓库中的每一个子模块， 包括可能存在的嵌套子模块。

> ```console
> git clone --recurse-submodules <url>
> ```

如果已经克隆了项目但是忘记带参数抓取子模块，可以使用

> ```console
>  git submodule update --init --recursive
> ```

### 子模块遍历->批量操作

`foreach` 子模块命令，它能在每一个子模块中运行任意命令。 

- `git submodule foreach 'git stash'` 保存所有子模块进度
- `git submodule foreach 'git checkout -b A'` 所有子模块创建切换分支
- `git submodule foreach 'git tag name'` 所有子模块`Tag`标记

## 总结

>  仓库级联且保持提交独立，选它！

