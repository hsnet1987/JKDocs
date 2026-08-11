---
title: "Windows下部署CAT 一站式 IT 运维管理平台"
date: 2023-12-18 17:50:09
link: https://www.cklist.cn/?p=702
categories: [Windows]
---

# Windows下部署CAT 一站式 IT 运维管理平台

来一杯咖啡与茶，为 IT 运维从业者减轻管理负担，提升管理效率，从繁重无序的工作中解压出来，利用剩余时间多喝一杯休息一下。 这是一个专为 IT 运维从业者打造的一站式解决方案平台，包含资产管理、工单、工作流、仓储等功能模块。 ❤ 感谢各位支持。CAT 提倡与各位使用者、开发者一起创建健康生态，让本项目变的更好，欢迎提供 PR 贡献。

以win10+小皮面板 部署CAT 一站式 IT 运维管理平台

下载所需软件包

小皮面板 [小皮面板(phpstudy) - 让天下没有难配的服务器环境！ (xp.cn)](https://www.xp.cn/)

PHP [PHP For Windows: Binaries and sources Releases](https://windows.php.net/download#php-8.3)

Git [Git - Downloading Package (git-scm.com)](https://git-scm.com/download/win)

composer 安装器 [https://getcomposer.org/Composer-Setup.exe](https://getcomposer.org/Composer-Setup.exe)

![](images/wp-content_uploads_2023_12_image-98-1024x576.png)

![](images/wp-content_uploads_2023_12_image-99-1024x576.png)

![](images/wp-content_uploads_2023_12_image-100-1024x576.png)

小皮面板，Git默认下一步安装即可。配置php环境变量

找到小皮的安装目录把下载好的php8.3.0解压出来并重新命名为php8.3.0nts.进入php8.3.0nts重命名php.ini-development为php.ini并打开php.ini 全局查找 extension_dir = "ext" 把ext替换成 E:\phpstudy_pro\Extensions\php\php8.3.0nts\ext  并且把前面的;去掉

![](images/wp-content_uploads_2023_12_image-101-1024x576.png)

![](images/wp-content_uploads_2023_12_image-102-1024x576.png)

添加扩展全局查找 ;extension=curl 把  curl  fileinfo  gd  intl  mbstring  mysqli  openssl  pdo_mysql  sockets zip opcache 前面的；去掉保存退出

![](images/wp-content_uploads_2023_12_image-103-1024x576.png)

![](images/wp-content_uploads_2023_12_image-104-1024x576.png)

安装composer把下载的Composer-Setup双击打开只需以下设置其他默认下一步即可

![](images/wp-content_uploads_2023_12_image-105-1024x576.png)

![](images/wp-content_uploads_2023_12_image-106-1024x576.png)

把php加到电脑变量上打开我的电脑属性-高级系统属性

![](images/wp-content_uploads_2023_12_image-107-1024x576.png)

验证一下php git composer是否正常，打开cmd 输入 php -v 回车  git -v回车 composer -v回车，返回以下画面就正常了.

![](images/wp-content_uploads_2023_12_image-108-1024x576.png)

![](images/wp-content_uploads_2023_12_image-109-1024x576.png)

打开小皮面板 把默认的网站删除，修改数据库root密码

![](images/wp-content_uploads_2023_12_image-116-1024x576.png)

打开cmd拉取代码。我这里以E盘www为目录CD到E盘www文件夹` cd  /d E:/www`  再输入` `

`git clone https://github.com/celaraze/cat.git`

![](images/wp-content_uploads_2023_12_image-110-1024x576.png)

打开E:\www\cat 复制粘贴.env.example为.env  用记事本打开编辑数据库，我以MySQL配置 把默认sqlite前面加上# 把MySQL前面的#删除，保存退出。

![](images/wp-content_uploads_2023_12_image-111-1024x576.png)

![](images/wp-content_uploads_2023_12_image-112-1024x576.png)

回到cmd界面安装依赖输入` cd cat` 回车 再输入 `composer install`

![](images/wp-content_uploads_2023_12_image-113-1024x576.png)

显示以下界面就说明安装依赖完成

![](images/wp-content_uploads_2023_12_image-114-1024x576.png)

再次执行数据迁移` php artisan cat:install`

![](images/wp-content_uploads_2023_12_image-115-1024x576.png)

新建网站。注意以下几点.设置 伪静态

![](images/wp-content_uploads_2023_12_image-117-1024x576.png)

![](images/wp-content_uploads_2023_12_image-118-1024x576.png)

打nginx配置文件路径如下，并把加入去保存退出，回到小皮面板重启一下nginx服务

```
location ~* \.(jpg|jpeg|gif|png|webp|svg|woff|woff2|ttf|css|js|ico|xml)$ {
        try_files $uri /index.php?$query_string;
        access_log off;
        log_not_found off;
        expires 14d;
    }
```

![](images/wp-content_uploads_2023_12_image-119-1024x576.png)

浏览器打开http://127.0.0.1即可登录 默认用户 admin@localhost.com  密码 admin

![](images/wp-content_uploads_2023_12_image-120-1024x576.png)

![](images/wp-content_uploads_2023_12_image-121-1024x576.png)