---
title: 安装Docker
date: 2021-04-23 07:26:32
tags:
- linux
---
## 检查是否安装过docker

```bash
yum list installed | grep docker
```

## 安装docker

```bash
yum -y install docker
```

## 启动docker

```bash
systemctl start docker
```

## 查看docker服务状态

```bash
systemctl status docker
```

## 使用

### 拉取image

docker pull zhengfan2014/yesbot

image存放位置

cd /var/lib/docker

参考：https://www.cnblogs.com/Rightsec/p/10222950.html

### 查询images

```bash
# 注意复数
docker images
```

### 运行images

```bash
docker run docker.io/zhengfan2014/yesbot
```

### 停止正在运行的images

```bash
docker stop [imageName]
```

服务类image运行后不会自动关闭。可以执行docker stop imageName停止。

参考：

https://blog.csdn.net/China_110/article/details/84447349