---
title: git版本控制工具——进阶
date: 2018-11-1 8:41:55
tags: git
categories: git
---

好了，初级学好了  就学一下进阶 ，毕竟靠初级还说不上懂git.

<!--more-->

前边学的是创建本地仓库：git init;

仓库添加文件：git add . ;

仓库提交文件：git commit -m "   ";

现在开始进阶

### 查看修改内容

git status  //查看上次提交后的所有文件中哪些已经被修改

git diff   // 查看具体修改了哪些内容，如果只想看其中一个，后加文件路径和文件名



### 撤销未提交的修改

git checkout 文件路径/文件名   //这种撤销只能撤销未添加的修改

如果要撤销已经添加的修改，可以先撤销添加，即先：

git reset HEAD 文件路径/文件名，然后再 git checkout 文件路径/文件名

### 查看提交记录

git log

当提交记录特别多的时候，可以只查看其中一条记录

git log a51bd7e2fc81da0890428359710aa8c0bedeaa0a -1

如果要查看这个提交具体修改了什么，可以使用

git log a51bd7e2fc81da0890428359710aa8c0bedeaa0a -1 -p





好了  以上 就是进阶教程 

现在修改代码什么的已经无忧喽！！！！！！！！！

可进可退。
