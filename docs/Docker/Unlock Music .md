# Docker Unlock Music 解锁音乐格式，享受自由聆听

![](images/image.png)

## 简介

Docker 镜像，解锁音乐格式，享受自由聆听。

## 镜像

- 镜像地址：https://hub.docker.com/r/hsnet1987/unlock-music

## 支持的格式

- QQ 音乐 (.qmc0/.qmc2/.qmc3/.qmcflac/.qmcogg/.tkm)
- Moo 音乐格式 (.bkcmp3/.bkcflac/…)
- QQ 音乐 Tm 格式 (.tm0/.tm2/.tm3/.tm6)
- QQ 音乐新格式 (.mflac/.mgg/.mflac0/.mgg1/.mggl)
- QQ 音乐海外版JOOX Music (.ofl_en)
- 网易云音乐格式 (.ncm)
- 虾米音乐格式 (.xm)
- 酷我音乐格式 (.kwm)
- 酷狗音乐格式 (.kgm/.vpr)
- Android 版喜马拉雅文件格式 (.x2m/.x3m)
- 咪咕音乐格式 (.mg3d)

## 使用方法

1. 安装 Docker  
2. 运行以下命令


```bash
docker run -itd –restart=always -p 3000:80 –name Music hsnet1987/unlock-music
```

3. 访问 http://localhost:3000 即可

## 参考

- [Docker 安装](https://www.docker.com/get-started)
- [Docker 镜像](https://hub.docker.com/r/hsnet1987/unlock-music)
- [Github 项目](https://github.com/hsnet1987/unlock-music)

## 鸣谢

- [Unlock Music](https://github.com/ix64/unlock-music)
- [Docker](https://www.docker.com/)
- [Docker Hub](https://hub.docker.com/)
- [Github](https://github.com/)
- [Github Actions](https://github.com/features/actions)
- [Github Pages](https://pages.github.com/)
- [Github Actions](https://github.com/features/actions)

