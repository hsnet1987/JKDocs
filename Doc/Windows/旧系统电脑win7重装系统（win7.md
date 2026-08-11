---
title: "旧系统电脑Win7重装系统（Win7)"
date: 2023-06-27 09:51:59
link: https://www.cklist.cn/?p=401
categories: [Windows]
---

# 旧系统电脑Win7重装系统（Win7)

首先制作U盘启动并设置U盘第一启动项.请参考

[Ventoy新一代多系统启动U盘解决方案](https://www.cklist.cn/?p=126)

**前提：资料数据请备份到各大云盘或者移动硬盘上**.

![](images/wp-content_uploads_2023_06_image.png)

选择第一个 启动

![](images/wp-content_uploads_2023_06_image-1.png)

双击打开 分区工具

![](images/wp-content_uploads_2023_06_image-2.png)

在硬盘右击如下图  删除所有分区

![](images/wp-content_uploads_2023_06_image-3.png)

注意如果硬盘显示GPT格式请转换成MBR格式

![](images/wp-content_uploads_2023_06_image-4.png)

然后点击保存

![](images/wp-content_uploads_2023_06_image-5.png)

关闭软件。也可以参考

[PE下安装纯版Windows系统 ](https://www.cklist.cn/?p=225)

然后打开 WinNTSetup （提前复制到U盘上）

![](images/wp-content_uploads_2023_06_image-6.png)

注意软件三个灯 全绿色证明 正常的

![](images/wp-content_uploads_2023_06_image-7.png)

1.选择win7 安装包（可以直接选择win7压缩包）

2.选择安装硬盘位置。也就是刚才删除分区那个硬盘

3.跟2一致即可

![](images/wp-content_uploads_2023_06_image-8.png)

如果找不到刚才删除分区的硬盘请再次打开分区工具

![](images/wp-content_uploads_2023_06_image-9.png)

![](images/wp-content_uploads_2023_06_image-10.png)

其他默认  直接确定就可以了

![](images/wp-content_uploads_2023_06_image-11.png)

保存

![](images/wp-content_uploads_2023_06_image-12.png)

格式化会分配一个盘符 我      这里显示C盘  关闭软件  回到WinNTSetup软件上把2 3选择C

![](images/wp-content_uploads_2023_06_image-13.png)

版本号 请选择 win7 旗舰版

确定无误就可以开始安装

![](images/wp-content_uploads_2023_06_image-14.png)

等待读条

![](images/wp-content_uploads_2023_06_image-15.png)

完成后 请不要重启 请不要重启 请不要重启

![](images/wp-content_uploads_2023_06_image-16.png)

关掉所有窗口.打开USB3&SRS工具

![](images/wp-content_uploads_2023_06_image-17.png)

把这几个驱动离线导入

![](images/wp-content_uploads_2023_06_image-18.png)

完成后 就可以重启安装Win7了.