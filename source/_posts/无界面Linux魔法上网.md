---
title: 无界面Linux魔法上网
date: 2021-04-23 03:59:27
tags:
---
## Shadowsocks或者V2ray

### 安装v2ray

[一键安装脚本](https://github.com/v2fly/fhs-install-v2ray/blob/master/README.zh-Hans-CN.md)

安装

```bash
sudo su
bash <(curl -L https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh)
```

配置

```bash
# 修改config.json文件为v2ray配置
# config.json位于usr/local/etc/v2ray/config.json
记录 Sock5 代理的端口和地址 例如：127.0.0.1:10808
```

!注意：改变v2ray的config文件后要重启v2ray服务
service v2ray restart


## Sock5 代理

### proxychains4

[源码](https://github.com/rofl0r/proxychains-ng)

编译安装

```bash
./configure
make -j
sudo make install
```

配置

```bash
# 创建文件夹
mkdir ~/.proxychains
# 创建文件
vi ~/.proxychains/proxychains.conf
```

文件的内容

```bash
strict_chain
proxy_dns
remote_dns_subnet 224
tcp_read_time_out 15000
tcp_connect_time_out 8000
localnet 127.0.0.0/255.0.0.0
quiet_mode

[ProxyList]
# 此处的端口值要设置成与v2ray配置文件相同的值
socks5  127.0.0.1 10808
```

## 使用

```bash
proxychains4 bash
```

## Configuration

proxychains looks for configuration in the following order:

SOCKS5 proxy port in environment variable ${PROXYCHAINS_SOCKS5} (if set, no further configuration will be searched)

file listed in environment variable ${PROXYCHAINS_CONF_FILE} or provided as a -f argument to proxychains script or binary.

./proxychains.conf

$(HOME)/.proxychains/proxychains.conf

/etc/proxychains.conf

see more in /etc/proxychains.conf

参考：

https://ry.huaji.store/2020/08/Linux-magic-network/

https://medium.com/@xiaoqinglin2018/mac-osx-%E4%BD%BF%E7%94%A8proxychains-ng-91ba61472fdf

https://github.com/haad/proxychains