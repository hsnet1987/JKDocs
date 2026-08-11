---
title: "Ubuntu 安装宝塔面板"
date: 2022-11-26 01:16:21
link: https://www.cklist.cn/?p=199
categories: [Linux]
---

# Ubuntu 安装宝塔面板

首先用SSH工具连接你的ubuntu服务器 我用的是FinalShell

![](images/wp-content_uploads_2022_11_image-117-1024x680.png)

输入  sudo -i 来提升为root权限 再次输入密码  注意 密码不显示

![](images/wp-content_uploads_2022_11_image-118-1024x680.png)

在ssh输入 以下命令 回车

> wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && sudo bash install.sh ed8484bec

![](images/wp-content_uploads_2022_11_image-119-1024x680.png)

期间会让你选择是否安装 输入 Y

![](images/wp-content_uploads_2022_11_image-120-1024x680.png)

这会让他跑完数据下载 速度 取决你网络速度和服务器性能

![](images/wp-content_uploads_2022_11_image-121-1024x680.png)

直到出现以下画面 宝塔就安装成功了

![](images/wp-content_uploads_2022_11_image-122-1024x680.png)

用浏览打开内网显示URL,如果是外网请在防火墙放行8888端口

![](images/wp-content_uploads_2022_11_image-123-1024x559.png)

国内宝塔登录要绑定手机号码和账号没有的请自行注册 输入账号密码

![](images/wp-content_uploads_2022_11_image-124-1024x559.png)

宝塔面板安装完成