---
title: "CentOS基于Docker安装Chemex  IT 资产管理系统"
date: 2023-07-20 21:23:53
link: https://www.cklist.cn/?p=470
categories: [Linux]
---

# CentOS基于Docker安装Chemex  IT 资产管理系统

## 简介

咖啡壶（Chemex）是一个轻量的、现代设计风格的 ICT 资产管理系统。得益于 [Laravel](https://gitee.com/link?target=https%3A%2F%2Flaravel.com%2F) 框架以及 [Dcat Admin](https://gitee.com/link?target=https%3A%2F%2Fdcatadmin.com) 开发平台，使其具备了优雅、简洁的优秀体验。 咖啡壶（Chemex） 是完全免费且开源的，任何人都可以无限制的修改代码以及部署服务，这对于很多想要对ICT资产做信息化管理的中小型企业来说，是一个很好的选择：低廉的成本换回的是高效的管理方案，同时又有健康的生态提供支持。

相关详情请移到官方 [celaraze/chemex - 码云 - 开源中国 (gitee.com)](https://gitee.com/celaraze/chemex)

**安装前建议把Navicat Premium 16安装上**

1.CentOS 安装Docker

yum install yum-utils

yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

yum install -y docker-ce

![](images/wp-content_uploads_2023_07_image-37-1024x735.png)

输入 docker -v 看看是否安装成功

![](images/wp-content_uploads_2023_07_image-38-1024x735.png)

输入 systemctl status docker  查看Docker是否在运行 返回 Active: inactive (dead)就没有启动

输入 systemctl start docker 启动Docker

再输入 systemctl status docker 返回以下这样 正常运行中

![](images/wp-content_uploads_2023_07_image-39-1024x735.png)

2.安装MySQL数据库

docker run -d  --name Mysql --restart=always  -p 3306:3306 --privileged=true -e MYSQL_ROOT_PASSWORD=123456  mysql

MYSQL_ROOT_PASSWORD=123456   123456为数据库用户root的密码 实际过程请使用强密码

命令会下载MySQL镜像并创建运行一个容器.过程快慢看自家网络了

![](images/wp-content_uploads_2023_07_image-40-1024x735.png)

![](images/wp-content_uploads_2023_07_image-41-1024x735.png)

出现这串数字容器已经运行了。输入docker ps 查看容器是否运行，显示UP正常

![](images/wp-content_uploads_2023_07_image-42-1024x735.png)

输入

```
firewall-cmd  --zone=public --query-port=3306/tcp
```

看看防火墙开放3306端口有没有返回NO 证明没有开

![](images/wp-content_uploads_2023_07_image-43-1024x735.png)

输入

```
firewall-cmd --zone=public --add-port=3306/tcp --permanent
```

开放3306

再接着输入

```
firewall-cmd --reload
```

重启防火墙

![](images/wp-content_uploads_2023_07_image-44-1024x735.png)

可以再输入多次

```
firewall-cmd --zone=public --query-port=3306/tcp
```

查看开放了没有

![](images/wp-content_uploads_2023_07_image-45-1024x735.png)

打开 Navicat Premium 16 连接看看

连接名---随意

主机---CentOS 的IP

端口---默认3306

用户---默认root

密码---MYSQL_ROOT_PASSWORD的值

![](images/wp-content_uploads_2023_07_image-46-1024x559.png)

保存后双击左边的 如果绿色已经连接成功了.

![](images/wp-content_uploads_2023_07_image-47-1024x559.png)

3.拉取Chemex镜像并运行

首先下载配置文件[ .env](https://www.123pan.com/s/4b1tVv-jo9Ih.html) 修改并上传到CentOS上 把

DB_HOST 改为你主机IP

DB_USERNAME  DB_PASSWORD  按你实际修改保存

![](images/wp-content_uploads_2023_07_image-49-1024x623.png)

在 FinalShell 以下位置新建一个文件夹为chemex并将刚才修改后的文件上传到这个文件夹上.

![](images/wp-content_uploads_2023_07_image-48-1024x735.png)

然后右击文件重新命名把 .example 删除

![](images/wp-content_uploads_2023_07_image-50-1024x735.png)

输入以下代码 正常拉取中

docker run -itd --name chemex --restart=always -p 8000:8000 -v /chemex/.env:/var/www/html/laravel/.env celaraze/chemex:latest

![](images/wp-content_uploads_2023_07_image-51-1024x735.png)

下载完成

![](images/wp-content_uploads_2023_07_image-52-1024x735.png)

输入以下代码 进入容器

docker exec -it chemex /bin/bash

 php artisan chemex:install

![](images/wp-content_uploads_2023_07_image-53-1024x735.png)

显示这样就安装完成成了.

继续输入以下几个命令

php artisan cache:clear

chmod 777 -R public

chmod 777 -R storage

chmod 777 -R bootstrap

chown www-data -R storage

![](images/wp-content_uploads_2023_07_image-54-1024x735.png)

![](images/wp-content_uploads_2023_07_image-55-1024x735.png)

到止在浏览器打开 iP:8000就可以打开系统了

![](images/wp-content_uploads_2023_07_image-56-1024x531.png)