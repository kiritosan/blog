---
title: Linux 下部署一个公主连结 qq 群聊机器人
date: 2021-04-24 03:03:37
tags:
- linux
- bot
---
链接：https://cn.pcrbot.com/deploy-a-priconne-bot-on-linux/

## 命令

```bash
yum -y update
yum -y groupinstall "Development tools"
yum -y install wget zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gcc* libffi-devel make git vim screen
```