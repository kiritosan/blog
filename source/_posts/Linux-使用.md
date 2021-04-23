---
title: Linux 使用
date: 2021-04-22 12:07:36
tags:
---
## 创建帐号

```bash
[root@Ubuntu:~]# useradd -m HongXunPan -s /bin/bash
[root@Ubuntu:~]# passwd HongXunPan
New password:
Retype new password:
passwd: password updated successfully
```

## 将新创建的帐号加入超级用户组

adduser Willem sudo//centOS下不可行

centOS下赋予root权限

方法1：修改/etc/sudoers文件

找到\#\# Allows people in group wheel to run all commands

usermod -g root Willem

方法2：修改/etc/sudoers文件

找到\#\# Allow root to run any commands anywhere

在下面添加用户

方法3：修改/etc/passwd文件

参考：

https://www.jianshu.com/p/4be52ce4cb91

https://www.cnblogs.com/yanglang/p/10767919.html

## 下载文件

wget

## 解压与压缩

解压缩命令：

tar -zxvf 压缩文件名.tar.gz

压缩命令：

tar -zcvf 压缩文件名 .tar.gz 被压缩文件名

## 移动文件

```bash
mv ./* ./go-cqhttp
```

## 创建文件夹

mkdir derectory

注意：在同一位置不能创建同名文件夹，在有go-cqhttp文件存在的情况下，不能创建go-cqhttp文件夹。

## 使用VIM打开编辑和保存文件

打开：

vi + 文件名

编辑：

输入i或a进入可编辑状态

保存：

按esc返回命令模式，输入:切换到最后一行模式

可以通过按X进行保存，X命令可以保存已编辑的文件

也可以用wq保存

## CentOS 下安装w3m

## 后台运行程序

nohup ./go-cqhttp &

查看nohup.out日志

tail -fn 50 nohup.out

退出时输入exit退出可以保证后台运行，直接点终端的叉号不行。

## 查看后台运行任务

jobs -l 当前终端

ps -ef 通用

参考链接：

https://www.cnblogs.com/huanghuanghui/p/9708350.html

https://www.linuxprobe.com/run-linuxcommand-backend.html

https://www.cnblogs.com/cfas/p/9348880.html

https://blog.csdn.net/JsongNeu/article/details/90345747

## 安装 ffmpeg

CentOS

```bash
yum install -y epel-release

rpm -v --import http://li.nux.ro/download/nux/RPM-GPG-KEY-nux.ro
rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm

yum install ffmpeg ffmpeg-devel
```

## 清空当前目录的所有文件

进入要删除的目录内部

输入sudo rm -rf *

