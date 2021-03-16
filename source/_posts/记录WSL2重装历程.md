---
title: 记录WSL2重装历程
date: 2021-03-16 03:08:34
tags:
- 杂谈
---
由于之前安装HomeBrew的一些问题，导致运行wsl2终端时一直会有错误提示，最近终于重装了一次wsl2。

## 一、重装步骤
1.打开Windows设置点击应用

2.搜索ubuntu并点击高级选项
![搜索ubuntu](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/%E6%90%9C%E7%B4%A2ubuntu.png)

3.点击重置
![](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/%E7%82%B9%E5%87%BB%E9%87%8D%E7%BD%AE.png)

注意：重置之后wsl2中的所有数据都会消失，重要数据需要提前备份

这样不管是点击之前的windows terminal还是点击wsl2子系统都会没有反应了

解决方法是到windos应用商店找到对应的wsl子系统点击安装

安装完成之后需要重新配置系统环境

## 二、重装后的环境配置

由于我在用hexo更新博客，所以nodejs和hexo是必要的，
于是重新安装它们。

### 1.安装nodejs

```bash
sudo apt install nodejs 
```

安装过程中出现了问题，报错信息：```Unable to locate package nodejs```

原因：刚安装wsl2还没更新软件源

解决方法：输入```sudo apt-get update```，更新软件源

### 2.安装hexo-cli

此时安装完nodejs，npm应该默认也安装完了，但是此时我输入npm却报错

提示```-bash: /mnt/c/Program Files/nodejs/npm: /bin/sh^M: bad interpreter: No such file or directory```

由于不熟悉linux系统，所以不知道怎么解决，网上搜了半天也没有成功。

于是改用yarn安装hexo-cli：```yarn global add hexo-cli```

安装完成后进入到hexo博客目录，发现hexo-cli又用不了，但是奇怪的是返回上一级目录却能使用，网上看到有人也有这种情况，但没能解决我的问题，遂放弃。

结果折腾的半天本地环境反而不能用了。

三、最后解决手段

暂时放弃本地环境，选用之前偶然发现的gitpod。