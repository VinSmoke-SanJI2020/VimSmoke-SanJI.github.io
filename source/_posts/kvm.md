---
title: kvm
author: 麦锡华
top: false
cover: true
toc: true
mathjax: false
abbrlink: 20886
date: 2021-01-28 17:03:25
img:
coverImg:
password:
summary:
keywords:
tags:
categories:
---

本篇文章是对于虚拟化技术的总结:grin:

<!-- more -->

![](https://cdn.jsdelivr.net/gh/VinSmoke-SanJI2020/images//IMAGES/kvm.webp)



- ##### 虚拟化概述

计算机虚拟化技术涵盖了多种技术，它包括硬件平台、操作系统、存储、以及网络等。

简单来说，虚拟机技术就是在单台主机上可以虚拟多个虚拟主机。

我们可以在这些虚拟主机上运行不同的操作系统平台。





- ##### 虚拟化技术的优点 

{% blockquote %}

虚拟化技术的出现可以节约大量的硬件资源与能源消耗，降低资金成本，资源调度更加灵活，提高效率

虚拟化现在已经是每个企业必有的项目。

{% endblockquote %}



- ##### 虚拟化原理

{% blockquote %}

虚拟化技术通过Hypervisor动态模拟与分配计算机硬件资源给虚拟机操作系统（Guest OS），由于Hypervisor可以模拟多个硬件资源给多个Guest OS，因此对Guest OS而言，就像运行在独立、真实的硬件资源上一样

{% endblockquote %}



- ##### 虚拟化分类

{% blockquote %}

硬件虚拟化 

一台物理计算机虚拟出多台逻辑计算机，其CPU、内存可分配给多台虚拟机

软件虚拟化

一个http软件支持多个网站、桌面虚拟化

{% endblockquote %}



- ##### 什么是虚拟机 ？

{% blockquote %}

通过软件平台模拟出的计算机

  对最终用户来说，感受不到与物理计算机的差异

  根据虚拟化程度不同，所需的修改也不同

{% endblockquote %}



- ##### 虚拟化实现程度	

{% blockquote %}

- 完全虚拟化 ，Full Virtualization

  虚拟化软件虚拟出一台计算机的全部组件，都是假的 ！客户机的操作系统代码几乎不做修改。

  缺点：效率低下

  原因：虚拟机的CPU并不具备真正的运算能力，需要先把请求交由虚拟化软件打上虚拟化标识，这才能把请求交由真实主机的CPU来运算。真实主机的CPU根据虚拟化标识，把运算结果再交由给虚拟化软件，虚拟化软件再交由给虚拟机的CPU

- 半虚拟化 ，Para Virtualization

  虚拟化软件虚拟出除CPU外的一台计算机的全部组件

  缺点：管理员必须读懂计算机底层源码才能实现，因而兼容性差

  原因：因为是使用真实主机的CPU，当虚拟机发送请求给真实主机的CPU之前，需要表明自己，即告诉真实主机的CPU：我是虚拟机的请求（给请求打个虚拟化标识）。真实主机的CPU根据虚拟化标识，把运算结果直接交由给虚拟机

- 硬件辅助虚拟化 ，Hardware-Assisted Virtualization

  虚拟化软件虚拟出一台计算机的全部组件，都是假的 ！ 目前最主流的用法

  将实现虚拟化技术的部分功能硬件化，这里主要指 Intel/AMD等CPU支持

  CPU支持虚拟指令集（识别虚拟化的指令），主要作用：能识别虚拟机发送过来的请求

{% endblockquote %}

- ##### 在Linux中查看是否开启虚拟化功能







