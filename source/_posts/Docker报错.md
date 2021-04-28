---
title: Docker报错
date: 2021-04-28 05:35:11
tags:
- Docker报错
---
WARNING: IPv4 forwarding is disabled. Networking will not work.

## 解决方法

```bash
# 切换到root用户 将配置写入到配置文件
echo "net.ipv4.ip_forward=1" >> /usr/lib/sysctl.d/00-system.conf
# 重启network和docker服务
systemctl restart network && systemctl restart docker
```

参考：

https://www.cnblogs.com/leffss/p/11345956.html

https://blog.csdn.net/yjk13703623757/article/details/68939183