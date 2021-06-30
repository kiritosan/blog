---
title: mysql学习记录
date: 2021-06-30 20:19:03
tags:
- 数据库
---
## 命令

<!-- 展示现有的数据库 -->
show databases;

<!-- 创建数据库 -->
create database crashcourse;

<!-- 使用数据库 -->
use crashcourse

<!--  -->
show tables;

<!--  -->
show columns form sakuraaccess_tokens

<!--  -->
source C:\\Users\\dell\\Desktop\\tmp\\create.sql


## 出错解决参考

1. 不能创建数据库

https://blog.csdn.net/qq_30938705/article/details/87857386

https://blog.csdn.net/weixin_43622863/article/details/87907886

解决方法：使用mysql -h localhost -u root -p链接数据库，要点是使用root账户，直接输入mysql的话是匿名账户
## 参考：mysql必知必会