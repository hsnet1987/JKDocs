---
title: "NAS群晖Docker部署QBittorrent下载器"
date: 2022-12-17 21:39:06
link: https://www.cklist.cn/?p=307
categories: [NAS]
---

# NAS群晖Docker部署QBittorrent下载器

打开文件管理器File Station 在docker文件夹新建一个文件夹qBittorrent

![](images/wp-content_uploads_2022_12_image-34-1024x529.png)

打开docker管理器-注册表 右上角搜索 qBittorrent 下载打一个

![](images/wp-content_uploads_2022_12_image-35-1024x529.png)

下载好 在映像中找到 linuxserver/qbittorrent 双击

![](images/wp-content_uploads_2022_12_image-36-1024x529.png)

网络可以用Bridge也可以选择host都可以.我以Bridge网络设置为例

![](images/wp-content_uploads_2022_12_image-37-1024x529.png)

把这两个都勾选上，至于容器名称你喜欢写什么都可以

![](images/wp-content_uploads_2022_12_image-38-1024x529.png)

设置映射端口 只把容器8080的改为固定就行  我选择一样  容器的8080不能改 本地端口你可以改你喜欢的就可以

![](images/wp-content_uploads_2022_12_image-39-1024x529.png)

设置映射文件夹 把一开始的新建的

![](images/wp-content_uploads_2022_12_image-40-1024x529.png)

第一个配置文件夹  第二个 下载目录  qBittorrent 的下载默认 为 /downloads

![](images/wp-content_uploads_2022_12_image-41-1024x529.png)

到这个就默认就行

![](images/wp-content_uploads_2022_12_image-42-1024x529.png)

返回容器 看看是否正常运行

![](images/wp-content_uploads_2022_12_image-43-1024x529.png)

浏览器输入  群晖IP：8080  默认用户admin 密码 adminadmin

![](images/wp-content_uploads_2022_12_image-44-1024x539.png)

登录进去后 在这里改成中文

![](images/wp-content_uploads_2022_12_image-45-1024x529.png)

qBittorrent 就安装完成.