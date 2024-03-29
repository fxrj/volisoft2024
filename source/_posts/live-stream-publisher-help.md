---
layout: post
title: 多路推流软件（Live Stream Publisher）说明书
date: 2022-03-01
author: 贺斌
tags: 
 - 推流
 - 直播
 - 流媒体
 - SRT
 - RTMP
 - ffmpeg
 - B/S
categories: 流媒体
hidden: true
---

多路推流软件，支持视频流的多路分发，实现拉取rtmp、rtsp、srt、hls、hdl视频流后再通过rtmp、srt协议推流到其他流媒体服务器。实现对推流任务的管理、调度，支持服务器集群以容纳更多的推流任务。基于ffmpeg开发，拉取视频流后将视音频数据二次封装后推流，不进行重新编码，降低CPU使用率。

## 1	安装部署

Live Stream Publisher多路推流软件是一款运行在Windows操作系统上的视频流推流软件，实现把一路视频流分发到多个视频直播平台。支持单机版运行和网络版运行两种运行模式。

### 1.1	单机版的安装

支持绿色安装，直接解压压缩包，运行LiveStreamPublisher.exe。未注册版本只能添加一个推流任务。

### 1.2	网络版的安装部署

通过Live Stream Publisher + Web服务的方式实现网络版。建议使用Windows Server操作系统。

#### 1.2.1	Live Stream Publisher

支持绿色安装，直接解压压缩包，运行LiveStreamPublisher.exe。软件需要注册为增强版，开启内置http api接口，默认端口8082。

#### 1.2.2	Web 服务

通过 phpstudy pro 提供的Apache、PHP功能作为Web服务器提供远程管理功能，同时作为代理服务器与Live Stream Publisher的api接口进行数据交互。建议http端口：8080。

> 管理地址：http://[服务器主机IP地址]:8080/LiveStreamPublisher/
> 管理员：admin，初始密码：admin

#### 1.2.3	防火墙

Web远程管理功能需要在Windows防火墙开放8080端口（Apache http 端口）。


## 2	使用指南

本使用指南适用于单机版和网络版。

### 2.1	推流任务管理

新建、修改、删除推流任务。

- `任务名`：推流任务的名称，便于识别，不允许重复。
- `源地址`：支持rtmp、rtsp、srt、hls、hdl视频流。
- `发布地址`：支持rtmp、srt视频流。
- `手动推流`：勾选后，只能手动开始或停止推流；不勾选，可以使定时自动推流。
- `重复`：不勾选“手动推流”，可以设置每周的哪些天的什么时间段开始推流和结束。不勾选周日——周六，可以设定一个具体的时间段开始推流和结束。
 
![单机版新建推流任务](/images/live-stream-publisher/add-task-1.png)

![网络版新建推流任务](/images/live-stream-publisher/add-task-2.png)

### 2.2	开始/停止推流

在单机版主界面中，选中一条推流任务。通过【推流】菜单下的【开始推流/停止】命令启动或停止推流任务，或通过右键菜单实现。
 
![单机版主界面](/images/live-stream-publisher/main1.png)

在Web页面中，选中一条推流任务。点击任务栏上的【开始推流/停止】按钮启动或停止推流任务。
 
![网络版主页面](/images/live-stream-publisher/main2.png)

### 2.3	用户管理

设置网络版远程登录时的用户及其权限。通过【工具】菜单下【用户管理】命令打开。
注意：服务器端运行的Live Stream Recorder不需要登录，直接以admin运行。

![用户管理](/images/live-stream-publisher/user-manage.png)
 
可以为每个用户设置最大推流任务数。最大任务数为0时，表示不做限制。

### 2.4	设置

通过【工具】菜单下【设置】命令打开设置窗口。

- `推流失败后尝试次数`：当推流出错时，尝试再次推流的总次数。当达到尝试次数时，会停止该推流任务。
- `全局最大任务数`：Live Stream Publisher 所能添加的推流任务上限。全部账号的总任务数不能超过该数值。每个账号的最大任务数受此数值限制。
- `http 服务端口`：Live Stream Publisher 内置http api服务的端口。

![用户管理](/images/live-stream-publisher/option.png)
 
### 2.5	日志

通过日志可以了解当前任务运行的详细情况。日志包括3类：主日志、推流任务日志、http api 日志。这些日志位于程序安装目录下的Log目录内。

#### 2.5.1	主日志

通过【任务】菜单下【主日志】命令打开主日志窗口。主日志记录程序开始录制、停止录制等主要信息。

#### 2.5.2	推流任务日志

主界面中，选中一条正在推流的任务。通过【推流】菜单下的【日志】命令打开推流任务日志窗口，或通过右键菜单打开。推流任务日志记录ffmpeg运行的输出信息。

对于推流进程异常出错，导致任务不能正常结束的情况，推流日志窗口提供了“结束进程”功能。

![推流任务日志](/images/live-stream-publisher/log.png)
 
#### 2.5.3	http api 日志

通过【工具】菜单下【HTTP Server】命令打开日志窗口。日志记录所有接口的调用信息。

### 2.6	推流详情

主界面中，选中一条正在推流的任务。通过【推流】菜单下的【推流详情】命令打开推流详情窗口，或通过右键菜单打开。

![推流任务日志](/images/live-stream-publisher/publish-detail.png)

### 2.7	信号预览

在单机版主界面中，选中一条推流任务。通过【推流】菜单下的【预览】命令可以播放源地址视频流的内容，或通过右键菜单实现。
 
![单机版信号预览窗口](/images/live-stream-publisher/player1.png)

在Web页面中，选中一条推流任务。点击任务栏上的【信号预览】按钮可以播放源地址视频流的内容。
 
![网络版信号预览窗口](/images/live-stream-publisher/player2.png)


