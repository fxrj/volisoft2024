---
layout: post
title: 多媒体展示系统
author: 贺斌
date: 2014-03-29 16:30:21
img: /images/featureImages/多媒体展示系统.jpg
categories: 多媒体
tags:
 - 多媒体
 - 信息发布
 - 播控
 - C/S
 - 分布式
---


多媒体展示系统是一种以信息输出播放为目的，以信息发布传递为主导的软件系统。它通过将文本，图片，动画，视频，音频有机组合，实时的形成一段段连续的画面，并通过现有的各种显示设备，播放给人们观看，向人们传达各种宣传信息。它采用了C/S结构，主从式体系，借助于现有的通讯网络，将信息传送到网络内的任何地方并播放输出。

## 1、系统架构
我们的展示系统是通过内部局域网管理分布在网络上的各个播放终端。系统采用一台电脑控制多台播放终端机，每台终端机连接一个或多个液晶电视的工作方式。

<img src="/images/飞翔多媒体展示系统-SystemArchitecture.png" alt="多媒体展示系统 系统架构" />

## 2、系统构成
我们的展示系统由后台管理服务端、网络平台、播放客户端和显示终端四部分组成。其中后台管理服务端、播放客户端由我们的软件构成。 后台管理服务端包括播放配置程序、播放控制程序和播放同步程序；播放客户端就是一台安装我们播放软件的小型电脑，分为 Linux 系统和 Windows 系统两类。

<img src="/images/飞翔多媒体展示系统-运行图.png" alt="多媒体展示系统 运行图" />

### 2.1 播放配置程序

对各个播放客户端进行远程监控和管理。能够监视播放客户端当前的工作状态和播放列表，管理所有媒体项，编辑播放列表。

<img src="/images/飞翔多媒体展示系统-PlayConfig_Main.png" alt="多媒体展示系统 播放配置程序" />

<img src="/images/飞翔多媒体展示系统-PlayConfig_MediaManager.png" alt="媒体项管理" />

<img src="/images/飞翔多媒体展示系统-PlayConfig_PlaylistManager.png" alt="播放列表管理" />

<img src="/images/飞翔多媒体展示系统-PlayConfig_PlaylistDetail.png" alt="编辑播放列表" />

### 2.2 播放控制服务

对各个播放客户端进行播放控制的后台服务。

<img src="/images/飞翔多媒体展示系统-PlayCtrlSrv_Main.png" alt="多媒体展示系统 运行图" />

### 2.3 播放同步服务

对各个播放客户端进行媒体项同步的后台服务。可以将播放的媒体项从服务器同步到客户端本地磁盘，降低对网络带宽的占用。

<img src="/images/飞翔多媒体展示系统-PlaySyncSrv_Main.png" alt="多媒体展示系统 运行图" />

### 2.4 播放器

运行在各个播放客户端，负责按照播放列表播放相应的媒体项。播放客户端目前包括 Linux 和 Windows 两类。

<img src="/images/飞翔多媒体展示系统-RPi_Client.jpg" alt="RPi 客户端" />

---

[原网站内容《飞翔多媒体展示系统》][MediaDisplaySys]


[MediaDisplaySys]: /images/飞翔多媒体展示系统.png
