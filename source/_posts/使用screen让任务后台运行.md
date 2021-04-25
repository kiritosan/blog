---
title: 使用screen让任务后台运行
date: 2021-04-25 08:36:23
tags:
- linux
---
## 创建screen

```bash
screen -S go-cqhttp
```

## 挂起窗口

```bash
# 按住ctrl不放，分别按下a，d
组合键 Ctrl + a ,d
```

## 查看screen

```bash
screen -ls
```

## 重新进入之前创建的screen

```bash
# id由screen -ls命令获得
screen -r [id]
```