---
title: linux后台下载文件
date: 2021-04-23 08:11:24
tags:
- linux
---
## 以续传方式后台下载单个文件

```bash
wget -bc https://github.91chifun.workers.dev/https://github.com//python-poetry/poetry/releases/download/1.1.6/poetry-1.1.6-linux.tar.gz
```

## 查看下载进度

```bash
tail -f wget-log
```

## 参考：

http://blog.chinaunix.net/uid-20639775-id-154579.html
