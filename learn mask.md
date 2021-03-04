# git学习笔记

## 创建版本库

设置自己的仓库

```shell
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"

```

第一步创建一个空目录

```shell
$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit

```

通过git init命令把这个目录变成Git可以管理的仓库：

```shell
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```

创建一个文件添加到版本库

```shell
$ vi readme.txt
Git is a version control system.
Git is free software.

$ git add readme.txt
$ git commit -m "wrote a readme file"
[master (root-commit) eaadf4e] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
```

git commit命令，-m后面输入的是本次提交的说明

### 总结

初始化一个Git仓库，使用git init命令。

添加文件到Git仓库，分两步：

使用命令git add <file>，注意，可反复多次使用，添加多个文件；
使用命令git commit -m <message>，完成。

为什么Git添加文件需要add，commit一共两步呢？因为commit可以一次提交很多文件，所以你可以多次add不同的文

## 时光机穿梭

### 版本回退

HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

### 工作区和暂存区

1. 工作区(Working Directory)

    当前的工作目录，比如learn就是一个工作区

2. 版本库(Repository)

    工作区有一个隐藏的目录`.git`,不算工作区，是Git的版本库

    Git版本库里存了很多东西，其中最重要的就是称为**stage(或者叫index)的暂存区**

    ![learngit](./images/stage.jepg)

- 使用命令`git add`就是把工作区修改过的文件添加git版本库的暂存区

- 使用命令`git commit`提交更改，就是把暂存区的所以内容提交到当前分支

- 创建Git版本库时，Git自动为我们创建了唯一一个master分支，所以，现在，git commit就是往master分支上提交更改

- 使用`git status`可以查看当前的状态
