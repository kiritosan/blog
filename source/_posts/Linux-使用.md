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

## 显示操作系统有关信息

```bash
# 显示操作系统的发行版号
uname -r
# 显示系统名、节点名称、操作系统的发行版号、内核版本等等（内核信息）
uname -a
# 查看已安装的centos版本信息
cat /proc/version
# 查看版本当前操作系统发行信息
cat /etc/issue
或
cat /etc/centos-release
```

参考：https://www.cnblogs.com/shigfdengys/p/11297731.html

## 更新

```bash
# 升级所有包同时也升级软件和系统内核
yum -y update

```

```bash
# 只升级所有包，不升级软件和系统内核
yum -y upgrade
```

参考：https://blog.csdn.net/weixin_41709748/article/details/81537561

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

& 放到任务最后放到进行后台执行

nohup 让程序始终在后台执行，即使关闭当前的终端也执行

nohup ./go-cqhttp &

查看nohup.out日志

tail -fn 50 nohup.out

退出时输入exit退出可以保证后台运行，直接点终端的叉号不行。

## 任务前后台切换

1. Ctrl+z 暂停任务/进程/程序

2. bg %[number]把程序放到后台运行

3. fg %[number]把程序调到前台运行

4. 使用 kill 命令终止后台运行的程序


## 查看后台运行任务

jobs -l 当前终端，别的终端或者新建一个终端就看不到了

ps -ef 通用

参考链接：

https://www.cnblogs.com/huanghuanghui/p/9708350.html

https://www.linuxprobe.com/run-linuxcommand-backend.html

https://www.cnblogs.com/cfas/p/9348880.html

https://blog.csdn.net/JsongNeu/article/details/90345747

## 端口被占用解决办法

1. 使用 lsof -i:[端口号] 命令找到占用端口的任务

2. kill PID 结束任务

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

## 安装Git

sudo yum install -y git

## python3安装

腾讯云轻量服务器自带python3

## python包管理工具下载


## 安装v2ray

https://github.com/v2fly/fhs-install-v2ray/blob/master/README.zh-Hans-CN.md

输入命令：

```bash
sudo su
bash <(curl -L https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh)
```

