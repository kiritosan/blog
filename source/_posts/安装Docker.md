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

