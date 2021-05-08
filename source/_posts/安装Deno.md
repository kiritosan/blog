---
title: 安装Deno
date: 2021-05-08 03:22:29
tags:
- 前端
---
## 安装命令

```bash
curl -fsSL https://x.deno.js.cn/install.sh | sh
```

## 手动设置 DENO_INSTALL 变量，并把 Deno 执行路径手动添加到 PATH

```bash
Deno 已经成功安装
可执行文件位置为 /home/Willem/.deno/bin/deno
您需要手动将 Deno 目录添加到 $HOME/.bash_profile (或者其它类似目录)
  export DENO_INSTALL="/home/Willem/.deno"
  export PATH="$DENO_INSTALL/bin:$PATH"
```

## 输入deno

```bash
# 提示如下
deno: /usr/lib64/libstdc++.so.6: version `GLIBCXX_3.4.21' not found (required by deno)
deno: /usr/lib64/libc.so.6: version `GLIBC_2.18' not found (required by deno)
```

## deno不支持CentOs7

卸载deno

## 链接：

https://zhuanlan.zhihu.com/p/140787128?from_voters_page=true

https://stackoverflow.com/questions/55156942/deno-on-centos-7-glibc-2-18-not-found