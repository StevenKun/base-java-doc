---
title: git版本控制工具——终极
date: 2018-11-01 09:44:47
tags: git
categories: git
---

你以为初级，进阶，高级就完成了吗？还有我定义的终极呢，嘻嘻

<!--more-->

初级的目标是：提交，添加修改

进阶的目标是：查看更改，查看提交记录，撤销未提交修改

高级的目标是：分支

终极的目标是：与远程版本库协作



这个需要注册github，然后创建一个远程版本仓库，复制仓库的url

## 远程版本库克隆到本地

在android项目目录中打开git bash ,执行

git clone https://github.com/StevenKun/ShoppingCart.git 

URL为仓库的URL

然后可以看到目录中出现了仓库的文件夹，将仓库里的文件夹内容复制到android studio创建项目文件夹里边， 有相同的替换掉，ok

## 本地的修改同步到远程版本库

git push origin master  //origin指定的是远程版本库的git地址，                             master指的是同步到哪个分支上；



## 远程版本库上的修改同步到本地

主要有fetch,和pull两种操作

1. fetch

   git fetch origin master //将远程版本库代码同步到本地,存放在origin/master分支上

   git diff origin/master //查看远程仓库里修改了哪一些

   git merge origin/master //将origin/master上的修改合并到主分支

2. full

   git pull origin master //相当于同时执行了fetch 和merge命令



## 总结

git的基本用法就是这些。

真心好用哦 ，这下终于知道android studio里的代码为什么都是绿色的啦 。

下来再看git的一些相关文档也就可以看懂了，这就入门了。

















