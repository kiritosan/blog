---
title: 安装poetry
date: 2021-04-23 07:57:41
tags:
---
因在线安装要下载70M，而且因为网络问题速度慢并且没有进度条，多次下载都已失败告终，遂采用离线方式安装。

## 离线安装poetry

1. 将 https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py 这个python 脚本存储到本地，比如存储为 get-poetry.py

2. 在 https://github.com/python-poetry/poetry/releases 下载对应平台的 realse 版本，比如 1.1.6 的  linux 版本 poetry-1.1.6-linux.tar.gz

3. 运行 python get-poetry.py --file poetry-1.1.4-win32.tar.gz

4. 配置环境变量

```bash
# 打开文件
vi $HOME/.profile
```

```bash
# 在文件中添加如下内容后，命令行模式:wq 保存退出文件
export PATH=$PATH:/Users/[用户名]/.poetry/bin
```

```bash
# 执行如下命令
source .bash_profile
```

```bash
# 测试是否安装配置成功
poetry --version
```

参考链接：

https://juejin.cn/post/6844904083464126472

https://python-poetry.org/docs/

[离线安装](https://blog.csdn.net/daihaoxin/article/details/109262807)

[配置](https://blog.csdn.net/daihaoxin/article/details/109262807)