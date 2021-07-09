---
title: git版本控制工具——初级
date: 2018-10-31 14:08:55
tags: git
categories: git
---

git 版本控制工具，因为自己已经开了一个小型的应用程序，下来就是迭代更新，但更新的时候如果出问题了怎么办呢？不小心删掉了代码怎么办？使用git ，给你梁静茹的勇气。

<!--more-->

既然是初级  ，只要知道这几个就好

1. 安装Git 

   百度直接搜Git,ok?

2. 创建代码仓库

   找到git bash 打开

   //这是配置你的身份

   git config --global user.name "用户名"

   git config --global user.email " 邮箱名 "



   //创建代码仓库,在项目目录之下执行

   ==git init==

   如果在目录下生成.git文件夹即为创建成功。

   如果删除.git文件夹即为删除仓库。

3. 提交本地代码

   提交使用add和commit命令

   ==git add +文件名==    //添加单个文件

   ==git add .==     //添加目录下所有文件

   ==git commit -m "First commit."== //执行提交操作，引号内为描述



   ok!!!!!!!!!!!!

   初级就这些内容 ，下来更新 进阶。
