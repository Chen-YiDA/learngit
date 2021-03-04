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

