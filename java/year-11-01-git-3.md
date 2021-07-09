---
title: git版本控制工具——高级
date: 2018-11-01 09:13:59
tags: git
categories: git
---

学习完了进阶，即将迎来高级，都已经迈过了一只脚，另一只脚也来吧。

<!--more-->

初级，建立仓库，添加，提交。

进阶，查看修改，撤销修改，以及查看提交记录

高级呢？往下看

## 分支

分支就是在现有代码的基础上开辟一个分叉口，使得代码可以在主干线和分支线同时进行开发，且相互之间不会影响。

git branch version1.0   //创建分支verison1.0

git branch  //查看有哪些分支

git checkout version1.0  //切换到分支version1.0

因为分支2不会影响分支1

所以有时候要让同步时

git checkout master

git merge version1.0

就可以让version1.0分支上修改并提交的内容合并到master主干上。但有时候会有代码冲突哦。



这下版本更替就没问题了，就是app更新的问题了哦



