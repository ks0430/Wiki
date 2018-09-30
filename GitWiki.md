---
typora-copy-images-to: ./Images
---

# GitWiki

> Git is a [free and open source](https://git-scm.com/about/free-and-open-source) distributed version control system designed to handle everything from small to very large projects with speed and efficiency.



## Global Settings

**Download links:**

[Windows版本的GIT下载](https://git-scm.com/download/win)

安装完毕后，任意地方右键，Git bash here ，配置用户信息，输入如下格式代码：

```shell
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

 检查配置信息：

```shell
$ git config --list
```



## Version Commit

**现在开始创建GIT仓库并管理你的版本**

在需要管理的项目根目录处，右键Git bash here，输入命令行：

```shell
$ git init
```

添加需要跟踪的文件，进入暂存区：

```shell
git add . 
```

将暂存区文件提交到仓库，归档当前版本：

```shell
git commit -m "版本V1.0.0 测试版发布"
```

### --amend 修补提交

若提交后又做了修改，却不想再提交新版本，则可以进行修补提交。

用法：

```
git add. 
git commit --amend
```

提交修改至缓存区后，使用参数--amend。上一次提交将被修改。

## Status Check

检查当前文件状态：

```shell
git status
```



## Branch

创建一个分支：

```shell
$ git branch testing
```

查看提交历史与分支情况：

```shell
$ git log --oneline --decorate
```

会显示如下图所示



分支切换

```shell
$ git checkout testing
```

将头指针切换到新分支上，提交历史会在新分支上继续下去。



项目分叉历史

```shell
$ git log --oneline --decorate --graph --all
```



## Git Aliases

Git 也提供了配置别名的功能，例如可以将 `git status` 简写为 `git st` 。对于查看分叉历史很有帮助，有几种方式设置别名

### 命令行设定

效果是全局的，在这台电脑下所有git仓库都适用。例如将status简写为st：

```shell
$ git config --global alias.st status
```

多个命令重写为一个单词：

```shell
$ git config --global alias.unstage 'reset HEAD'
```

### Config 配置文件

配置 Git 的时候，加上 `--global` 是针对当前用户起作用的，如果不加，那只针对当前的仓库起作用。

#### 项目的Config文件

针对当前仓库的配置文件在项目目录下的 `.git/config` 中。修改alias只针对当前Repo生效。

```shell
$ cat .git/config 
[core]
    repositoryformatversion = 0
    filemode = true
    bare = false
    logallrefupdates = true
    ignorecase = true
    precomposeunicode = true
[remote "origin"]
    url = git@github.com:michaelliao/learngit.git
    fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
    remote = origin
    merge = refs/heads/master
[alias]
    last = log -1
```

#### 全局的Config文件

全局的config文件在用户目录下，对于当前git用户生效。路径为 `~/.gitconfig`

