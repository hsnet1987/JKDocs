---
title: "群晖Docker部署Chemex IT资产管理系统"
date: 2023-07-20 10:14:11
link: https://www.cklist.cn/?p=425
categories: [NAS]
---

# 群晖Docker部署Chemex IT资产管理系统

咖啡壶（Chemex）是一个轻量的、现代设计风格的 ICT 资产管理系统。得益于 [Laravel](https://gitee.com/link?target=https%3A%2F%2Flaravel.com%2F) 框架以及 [Dcat Admin](https://gitee.com/link?target=https%3A%2F%2Fdcatadmin.com) 开发平台，使其具备了优雅、简洁的优秀体验。 咖啡壶（Chemex） 是完全免费且开源的，任何人都可以无限制的修改代码以及部署服务，这对于很多想要对ICT资产做信息化管理的中小型企业来说，是一个很好的选择：低廉的成本换回的是高效的管理方案，同时又有健康的生态提供支持。

相关文档请到官方 [chemex: 🔥 chemex 是高颜值的开源信息化资产管理系统。 (gitee.com)](https://gitee.com/celaraze/chemex)

安装前建议你们把Navicat Premium 16安装上

![](images/wp-content_uploads_2023_07_image-33-1024x559.png)

打开Shell 把NAS连接上 首先拉取MySQL数据镜像.我个人喜欢用FinalShell 输入sudo -i 输入一下当前用户密码换成root用户

拉取MySQL

docker pull mysql

![](images/wp-content_uploads_2023_07_image-3-1024x735.png)

创建一个数据库输入 以下命令

docker run -itd --name Mysql --restart=always -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456  mysql

注：-e MYSQL_ROOT_PASSWORD=123456   123456为root密码真实请换成自定强密码组合

![](images/wp-content_uploads_2023_07_image-4-1024x735.png)

出现一串随机数证明已经创建成功。我们打开Navicat Premium 16看看能不能连上，左上角 连接-MysSQL

![](images/wp-content_uploads_2023_07_image-5-1024x576.png)

![](images/wp-content_uploads_2023_07_image-6-1024x559.png)

连接名---- 随意你喜欢就行

主机----NAS群晖IP

端口----默认3306 如果你改其他的请写你改的

用户--root

密码---- MYSQL_ROOT_PASSWORD 里的密码

![](images/wp-content_uploads_2023_07_image-7.png)

保存后 双击看看能不能连接上 如果变成绿色证明是正常的连接的 可以继续下一步.

![](images/wp-content_uploads_2023_07_image-8.png)

![](images/wp-content_uploads_2023_07_image-9-1024x559.png)

回到FinalShell 拉取chemex镜像

docker pull celaraze/chemex:latest

![](images/wp-content_uploads_2023_07_image-10-1024x735.png)

下载配置文件 .evn 可在我这下载  [env](https://www.123pan.com/s/4b1tVv-Lo9Ih.html)

把文件用TXT打开修改数据库连接配置

DB_HOST----你群晖IP

DB_USERNAME---数据库用户 默认root

DB_PASSWORD---创建时的mysql里MYSQL_ROOT_PASSWORD密码

![](images/wp-content_uploads_2023_07_image-11-1024x597.png)

保存上传到群晖上 在docker文件夹下创建一个文件夹名为chemex再把修改好的.env.example上传上去

![](images/wp-content_uploads_2023_07_image-12-1024x531.png)

右击文件名-重新命名 把.example删除

![](images/wp-content_uploads_2023_07_image-13-1024x531.png)

在群晖上打开docker面板  新建 接下直接看图吧

![](images/wp-content_uploads_2023_07_image-15-1024x531.png)

![](images/wp-content_uploads_2023_07_image-16-1024x531.png)

![](images/wp-content_uploads_2023_07_image-17-1024x531.png)

![](images/wp-content_uploads_2023_07_image-18-1024x531.png)

![](images/wp-content_uploads_2023_07_image-19-1024x531.png)

![](images/wp-content_uploads_2023_07_image-20-1024x531.png)

![](images/wp-content_uploads_2023_07_image-21-1024x531.png)

装载路径  /var/www/html/laravel/.env

![](images/wp-content_uploads_2023_07_image-22-1024x531.png)

![](images/wp-content_uploads_2023_07_image-23-1024x531.png)

![](images/wp-content_uploads_2023_07_image-24-1024x531.png)

回到FinalShell 输入 Chemex C大写

docker exec -it Chemex /bin/bash

![](images/wp-content_uploads_2023_07_image-25-1024x735.png)

再输入  提示输入Y回车

php artisan chemex:install

![](images/wp-content_uploads_2023_07_image-26-1024x735.png)

![](images/wp-content_uploads_2023_07_image-27-1024x735.png)

在上面再输入

php artisan cache:clear

然后在浏览器输入 NAS的IP：8000就可以了

![](images/wp-content_uploads_2023_07_image-29-1024x516.png)

在使用过程中你会发现上传图片会失败，那是目录没有给权限

![](images/wp-content_uploads_2023_07_image-30-1024x516.png)

进用容器内输入以下命令即可

chmod -R 755 public

![](images/wp-content_uploads_2023_07_image-31-1024x735.png)

![](images/wp-content_uploads_2023_07_image-32-1024x516.png)

会发现已经正常了.到此项目已经部署完成.