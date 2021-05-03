---
title: 远程jupyter notebook
date: 2021-05-03 09:02:23
tags:
---
## 安装

https://jupyter.readthedocs.io/en/latest/install/notebook-classic.html

pip3 install --upgrade pip

pip3 install jupyter

## 设置远程

https://jupyter-notebook.readthedocs.io/en/latest/public_server.html#notebook-server-security

jupyter notebook --generate-config

第一次启动会提醒设置新密码

不能修改的话可能是因为设置里面的--NotebookApp.allow_password_change=False

重置或设置密码

jupyter notebook password

### 设置哈希密码

```python
from notebook.auth import passwd
passwd()
```

### 设置公钥和私钥进行加密通讯

使用openssl创建为期一年的钥匙

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout mykey.key -out mycert.pem

### 最精简设置

```python
# Set options for certfile, ip, password, and toggle off
# browser auto-opening
c.NotebookApp.certfile = u'/absolute/path/to/your/certificate/mycert.pem'
c.NotebookApp.keyfile = u'/absolute/path/to/your/certificate/mykey.key'
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
c.NotebookApp.password = u'sha1:bcd259ccf...<your hashed password here>'
c.NotebookApp.open_browser = False

# It is a good idea to set a known, fixed port for server access
c.NotebookApp.port = 9999
```

### 用screen创建新窗口运行

jupyter notebook

## 遗留问题

自己创建的公钥和私钥不被浏览器识别，会显示不安全

官方文档里有[用Let’s Encrypt消除不安全标识的方法](https://jupyter-notebook.readthedocs.io/en/latest/public_server.html#using-let-s-encrypt)，个人没有需要所以没有进一步配置