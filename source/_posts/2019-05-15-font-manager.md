---
layout: post
title: 字体管理软件（Font Manager）
author: 贺斌
categories: 网络管理
tags:
 - 机房管理
 - 字体管理
 - Font
 - C/S
---


一款字体管理软件。采用C/S架构，可以从自行部署的字体服务器下载安装字体到本机；同时可对本机已安装字体进行管理；适合局域网批量安装部署字体。

## 1. 管理本机字体

对已安装在本机的字体进行管理。可预览或卸载本机的字体。

<img src="/images/FontManager1.png" alt="已安装字体" />

## 2. 从网络字体库安装字体

<img src="/images/FontManager.png" alt="网络字体库" />

## 3. 字体文件夹

<img src="/images/FontManager3.png" alt="字体文件夹" />

### 3.1 从字体文件夹安装字体

打开本机或UNC路径下的字体文件夹，可进行预览字体，批量安装字体，卸载字体等操作。

### 3.2 部署网络字体库

打开字体文件夹后，`导出字体信息文件`并命名为`default.xml`，然后将`default.xml`文件和字体文件夹中的所有字体文件一起存放到Web服务器的虚拟目录（比如：`/FontManager/`）下，即完成建立网络字体库。

修改 FontManager.exe 目录下 `FontManager.ini` 文件的配置信息。将 `[FontNet]` 下的 `WebServiceURL` 属性的值设置为 `http://[Web服务器IP地址]/FontManager/` 。
