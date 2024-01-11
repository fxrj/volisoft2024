---
layout: post
title: 机房计时管理系统
author: 贺斌
date: 2020-02-06 16:30:21
img: /images/featureImages/机房计时管理系统.jpg
categories: 网络管理
tags:
 - 机房管理
 - 上机计时
 - C/S
 - 分布式
---

机房计时控制管理软件采用C/S架构，客户端程序和计时统计服务使用Delphi 10.2开发，服务器端使用Apache 2.4.39 + MySQL 5.7.26数据库 + php 7.3.4，通信协议http，数据交换格式JSON。

<img src="/images/机房计时管理系统-系统架构.png" alt="机房计时管理系统" />

## 主要功能

- C/S架构，计时客户端采用轻量化设计； 
- 客户端自动记录用户上机时间，并对用户上机行为进行管理； 
- 采用HTTP+JSON方式进行客户端与服务器端通讯； 
- 后台管理程序提供用户、部门、主机、客户端的管理功能； 
- 对主机使用情况进行统计汇总，可按用户、部门、主机进行统计分析； 
- 操作简单，安全可靠、运行效率高、易维护。

## 系统截图

`客户端登录：`
<img src="/images/机房计时管理系统-客户端登录.png" alt="机房计时管理系统-客户端登录" />

`客户端状态：`
<img src="/images/机房计时管理系统-客户端状态.png" alt="机房计时管理系统-客户端状态" />

`按账号统计：`
<img src="/images/机房计时管理系统-按账号统计.png" alt="机房计时管理系统-按账号统计" />

`按部门统计：`
<img src="/images/机房计时管理系统-按部门统计.png" alt="机房计时管理系统-按部门统计" />

`按主机统计：`
<img src="/images/机房计时管理系统-按主机统计.png" alt="机房计时管理系统-按主机统计" />

## 论文

[论文《电视台非编机房计时管理系统的设计与应用》][论文地址]


[论文地址]:https://kns.cnki.net/kcms/detail/detail.aspx?dbcode=CJFD&dbname=CJFDLAST2021&filename=DSZM202110015&uniplatform=NZKPT&v=nsPYJJIzNwanzm74g-0HCBpIHnohTHTIqfcgS4h1qJAqgndFxr56264ngJwxJh6i