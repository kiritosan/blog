---
title: 远程jupyter notebook
date: 2021-05-03 09:02:23
tags:
---
https://jupyter.readthedocs.io/en/latest/install/notebook-classic.html

pip3 install --upgrade pip

pip3 install jupyter

https://jupyter-notebook.readthedocs.io/en/latest/public_server.html#notebook-server-security

jupyter notebook --generate-config

第一次启动会提醒设置新密码

不能修改的话可能是因为设置里面的--NotebookApp.allow_password_change=False

重置或设置密码

jupyter notebook password