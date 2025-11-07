# All in SSL - SSL证书全流程管理工具

## 1. 简介

一站式SSL证书生命周期管理解决方案 | 支持Let's Encrypt | 多平台部署 | 自动化运维

## 📌 项目亮点

🔑 一站式SSL证书申请/续期/管理 </br>
✅ 全自动证书申请/续期 </br>
🔐 自动化运维 </br>
🌐 多平台部署（CDN/面板/云存储）</br>
🔔 证书过期监控 </br>
🛡️ 安全入口保护 </br>
📊 可视化证书管理 


## 🚀 快速开始

极速安装

```bash
curl -sSO http://download.allinssl.com/install_allinssl.sh && bash install_allinssl.sh allinssl
```

Docker安装

```bash
docker run -itd \
  --name allinssl \
  -p 7979:8888 \
  -v /www/allinssl/data:/www/allinssl/data \
  -e ALLINSSL_USER=allinssl \
  -e ALLINSSL_PWD=allinssldocker \
  -e ALLINSSL_URL=allinssl \
  -e TZ=Asia/Shanghai \
  hsnet1987/allinssl:TAG(版本号比如 1.0.4 ）
  ```

## 源码编译安装
如需自行编译，请确保已安装Go 1.23+环境：
```bash
git clone https://github.com/allinssl/allinssl.git
cd allinssl
go mod tidy
go build -o allinssl cmd/main.go
./allinssl start
```

## 二进制文件安装
1. 打开 [releases 下载页面](https://github.com/allinssl/allinssl/releases)
2. 下载最新版本的二进制文件
3. 解压缩文件，并通过终端或者CMD进入解压目录
4. 获取登陆地址，账号和密码
   - 账号和登陆地址：
    - Linux: `./allinssl 15`
    - Windows: `.\allinssl 15`
  - 密码：
    - Linux: `./allinssl 6`
    - Windows: `.\allinssl 6`
5. 运行可执行文件启动服务，请保持终端打开，或者自行配置进程守护
   - Linux: 执行 `./allinssl start`
   - Windows: 终端进入到解压目录，执行 `.\allinssl start`
6. 访问 `http://your-server-ip:port/安全入口`，使用账号和密码登录
7. 更多命令行操作请参考 [命令行操作](#💻-命令行操作)


## 💻 命令行操作

```bash
# 基本操作
allinssl 1: 启动服务 🚀
allinssl 2: 停止服务 ⛔
allinssl 3: 重启服务 🔄
allinssl 4: 修改安全入口 🔐
allinssl 5: 修改用户名 👤
allinssl 6: 修改密码 🔑
allinssl 7: 修改端口 🔧

# Web服务管理
allinssl 8: 关闭web服务 🌐➖
allinssl 9: 开启web服务 🌐➕
allinssl 10: 重启web服务 🌐🔄

# 后台任务管理
allinssl 11: 关闭后台自动调度 📻⛔
allinssl 12: 开启后台自动调度 📻✅
allinssl 13: 重启后台自动调度 📻🔄

# 系统管理
allinssl 14: 关闭https 🔓
allinssl 15: 获取面板地址 📋
allinssl 16: 更新ALLinSSL到最新版本（文件覆盖安装） 🔄⬆️
allinssl 17: 卸载ALLinSSL 🗑️
```

## 首次配置
1. 访问 `http://your-server-ip:port/安全入口`
2. 添加DNS提供商和主机提供商凭证 ☁️
3. 创建工作流

[完整安装文档](https://allinssl.com/guide/getting-started.html)
