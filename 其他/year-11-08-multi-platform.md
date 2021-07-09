---
title: 主流开发，跨平台技术探究
date: 2018-11-08 08:24:16
tags: multi_platform
categories: multi_platform
---

探究原因：当前android app无法运行于ios设备之上

探究目的：寻找解决ios用户无法运行android app的方案

<!--more-->

##  前言

开始之前两点讲明白：

1. 目前没有一种技术可以实现一套代码实现在android上和ios上运行
2. 只有一种技术针对ios系统，android系统分别进行开发。
3. 学习和选用一种语言，对开发者的影响很大，不是想学就ok的，或者给你资源就ok的，乱点技能点，会导致开发者技能平庸，干什么都是半桶水。毕竟要做好，入门1年，精通需要5年...。
4. 技术需要考虑前景，难度,人员补充，面向的对象，物理条件，技术条件,开发成本。

## 正文

**方案一：WEB APP**

该模式通常由“HTML5云网站+APP应用客户端”两部份构成,APP应用客户端只需安装应用的框架部份，而应用的数据则是每次打开APP的时候，去云端取数据呈现给手机用户.

个人总结：体检查，

webapp是生存在浏览器里的应用，所以只能运行在浏览器里，宿主是浏览器，不再是操作系统。资源一般都在网络上。说的根本点就是一个触屏版的网站。

前景：差		人员补充：容易

难度：小			面向的对象：快速开发，已有window平台网页

开发物理条件：开发window，测试ios，window，android

主要技术条件：h5+css+js

开发成本：低，周期短

android的移植ios难度：无

推荐阅读：https://www.zhihu.com/search?type=content&q=web+app



**方案二：Hybrid app**

即利用了原生APP的开发技术还应用了HTML5开发技术，是原生和HTML5技术的混合应用。混合比例不限。

个人总结：基本的UI和功能等使用原生，数据的展示等使用h5，可以使用设备底层硬件

前景：好          人员补充：中等    生态：无统一生态，

难度：中           面向的对象：需要更新维护快

物理条件：开发需要mac os  +windows，测试需要ios和android

技术条件：ios中级及以上+android中级及以上+HTML+CSS+JS+java+swift

开发成本：中，周期中

android的移植ios难度:中等

目前app：支付宝，美团，微信等均采用

推荐阅读：https://blog.csdn.net/jingwen3699/article/details/68922945

**方案三：React Native**

出世近5年？

跨平台解决方案：

React Native产出的并不是“网页应用”， 或者说“HTML5应用”，又或者“混合应用”。 最终产品是一个真正的移动应用，从使用感受上和用Objective-C或Java编写的应用相比几乎是无法区分的。 React Native所使用的基础UI组件和原生应用完全一致。 你要做的就是把这些基础组件使用JavaScript和React的方式组合起来。

----摘自https://reactnative.cn/官方网站

前景：目前看好		人员补充：难

难度：高            面向对象：学习一门语言，同时开发ios和android的人

物理条件：开发需要windows,mac os ,测试需要：ios,android

技术条件上：jsx+react+es6+想了解React Native构建的还需要学习nodejs。封装原生组件还需要学习 java，object-c，swift， 也就是需要学习Android和ios原生开发。设计到通讯原理还需要了解C++。

开发成本:低，周期中

android的移植ios难度:低，几乎95%的代码不需要改动，

目前app:便利蜂

推荐阅读

**方案四:flutter**

使用dart语言，出世近两年？

同React Native，问题是

推荐阅读：http://www.cocoachina.com/programmer/20180802/24418.html

**方案五： android和ios单独开发**

**方案六：Xamarin**

Xamarin是一个跨平台的移动应用开发框架，由微软基于Mono（一个免费的开源.NET框架），使用C＃创建本地应用。这一点上很符合公司，但最大最大的问题，怎么学习，出现问题了问谁？没有一个高度活跃的社区。国内生态巨差，但据说国外还是有一些的。

推荐：

Xamarin的价值到底在哪儿？ - TalkingData的回答 - 知乎
https://www.zhihu.com/question/36914471/answer/520782019

## 总结

想要实现ios用户和android用户都能使用，除了webapp都必须要开发两个应用，开发ios端的必须要有苹果笔记本，使用Xcode学习swift。开发android端的必须要有androidstudio或者eclipse，使用java或者kolin。不同之处，只是在于要更改多少代码的问题。



如果原生来开发app，几乎都要更改

如果混合编程来开发app，更改部分,看原生和web的比例。

如果使用React Native 等来开发，改动小。

原生是基础。



















