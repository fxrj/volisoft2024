---
layout: post
title: VCF Encoding 2.0
author: 贺斌
date: 2013-03-04 16:30:21
img: /images/featureImages/VCFEncoding.jpg
categories: 办公
tags:
 - VCF
 - VCard
 - 飞翔通讯录
 - 飞翔通讯录网络版
---

　　飞翔 VCF 文件编码转换器，又名VCF Encoding。该软件设计的初衷是为了解决飞翔通讯录导入 VCF 文件出现的乱码问题。但是自2008年发布以来，软件获得了广大需要解决 VCF 名片乱码问题的用户的喜爱，之后根据用户反馈有多次升级。但是2010年之后，由于作者本人的原因，该软件长久没有更新。

　　2013年新年过后，作者重写了 VCF Encoding 的源代码，使其全面支持 VCard 2.1、3.0 标准，解决了 Unicode、UTF-8、UTF-7、ANSI、Big-endian Unicode 编码问题，支持对嵌入图片和声音资源的解析，支持对 VCF 名片的拆分和合并。目前对大多数的乱码问题都已经有效解决。VCF Encoding 又与大家见面了，她依然是免费的、绿色的、小巧的一款软件，是一款基于 Volisoft 技术值得信赖的产品。软件开发过程中，占用了和妻子在一起的美好时光，感谢她的理解和支持。

　　运行 VCFEncoding.exe 启动飞翔 VCF 文件编码转换器(VCF Encoding)，如下图。

![VCFEncoding主界面](/images/VCFEncoding_main.png)

## 1、添加 VCF 文件
　　点击工具栏 VCFEncoding_添加VCF文件 图标，选择需要重新编码的 VCF 文件，会打开『选择文件编码』对话框。如下图。

![VCFEncoding_选择VCF文件编码](/images/VCFEncoding_add_vcf_file.png)

　　软件会自动识别文件的编码格式，但是对于有些软件导出的 VCF 文件也会存在识别不正确的情况，用户可以尝试选择其他的编码，直到预览界面不显示乱码为止。提示：支持通过从资源管理器向VCF文件列表拖拽的方式添加 VCF 文件。

　　添加需要重新编码的 VCF 文件后，软件界面如下图所示。

![VCFEncoding_主界面](/images/VCFEncoding_main2.png)

　　只要添加 VCF 文件时，选择的编码正确，软件都会正确显示其中的名片内容。如果在选择编码时显示的无乱码，但在主界面中显示乱码，可以尝试在该名片文件上点击右键，选择取消『强制转码』，一般可以解决该问题。如果问题依然存在，请及时联系我们。

　　如果 VCF 名片中包含有图片或声音嵌入资源，软件会显示其内容。双击资源图标可以将嵌入资源导出。

![VCFEncoding_导出资源](/images/VCFEncoding_main3.png)

## 2、输出 VCF 文件
　　点击工具栏 VCFEncoding_输出VCF文件 图标，可以将添加的 VCF 文件重新编码后输出。如下图。

![VCFEncoding_输出VCF文件界面](/images/VCFEncoding_export_vcf.png)

　　输出范围：全部 VCF 文件 —— 添加的全部 VCF 文件；选中的 VCF 文件 —— VCF 文件列表中选中的文件。
　　文件类型：输出的结果，是全部名片在一个 VCF 文件中，还是每一个名片对应一个 VCF 文件。
　　文件编码：输出文件采用的编码类型。
　　VCF 版本：输出文件中的名片采用的版本。
　　输出文件/输出目录：输出结果存放的文件或目录。

　　进行基本的设置后（一般采用默认设置可以支持大多数设备和软件），点击『输出』按钮，开始输出 VCF 名片。如下图。

![VCFEncoding_输出VCF文件结果](/images/VCFEncoding_export_vcf2.png)

　　至此，完成了 VCF 文件的重新编码。

　　`提示：支持通过从名片列表向资源管理器拖拽的方式快速输出 VCF 文件（采用默认设置）。`
