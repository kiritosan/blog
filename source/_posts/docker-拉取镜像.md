---
title: docker 拉取镜像
date: 2022-05-01 08:56:59
tags:
---

https://hub.docker.com/layers/node/library/node/12-slim/images/sha256-b8922ead40512613bedabb3a930b3a8069dae988f50c30b3b06cd81a469f095f?context=explore

上面是docker的node:12-slim官方镜像
可以看到官方页面有一个一步步的清单

这个清单并不是虽然和自己写的DockerFile文件很相似，但是并不是
请先以为这个是DockerFile让我误认为push镜像是把自己的DockerFile上传上去了，然后别的docker拉取的时候拿到一个DockerFile照着做，但是转念一想，这样的话自己复制的一些文件在别的机器上没有，别的机器不可能把不存在的文件复制到容器里

所以，官方页面的清单是制作镜像的步骤，而拉取镜像拉取的是最终版的镜像

## build

下面是自己打包镜像的过程

首先写一份DockerFile文件，这个文件告诉docker怎么打包镜像

然后执行build命令，docker开始按照DockerFile打包

DockerFile有几个步骤，就会有几个层，每层生成完了都会缓存下来，下次build如果没有变动直接用缓存的内容

## push

构建完成之后push到dockerhub上，这个过程是将自己构建完的最终镜像上传上去，而不是把每个layer上传上去，只不过上传自己最终镜像的同时将打包的步骤也上传上去。另外，官网展示的打包的步骤并不是和自己写的DockerFile内容完全一致，而是会把FROM的镜像的打包过程展开，完全展示从开始到最后的每一步（即每一层）。
DockerFile描述自己想要的打包过程，而官网将docker从开始到最后每一层在做什么都展示出来

而这个只是展示作用，等拉取这个镜像的时候并不会按这个步骤本机再走一次（走也走不通），而是直接拉取最终镜像

最终的镜像不是单个文件，而是多层文件，dockerfile每一个指令就会形成一层。
构建时，一层层构建，构建出来的所有层组合起来为最终镜像
拉取时，拉取所有层，这些层都是构建完的，不需要再构建

构建相当于造多个零件
拉取相当于取多个零件
但是层之间关系是前后依赖的，后面的层依赖前面的层，不是简单拼合到一起的关系

> 镜像构建时，会一层层构建，前一层是后一层的基础。每一层构建完就不会再发生改变，后一层上的任何改变只发生在自己这一层

## 分层

拉取的时候会发现会下载多个文件，而不是一个，这是因为docker用了分层的思想

> 镜像构建时，会一层层构建，前一层是后一层的基础。每一层构建完就不会再发生改变，后一层上的任何改变只发生在自己这一层。

https://yeasy.gitbook.io/docker_practice/basic_concept/image

```s
# docker build -t dockerwillem/hight-js:latest .

Sending build context to Docker daemon  22.57MB
Step 1/9 : FROM node:12-slim
 ---> 9b792ac6810e
Step 2/9 : RUN apt-get update -qq     && apt-get install --yes --no-install-recommends         nginx git     && rm -rf /var/lib/apt/lists/*
 ---> Using cache
 ---> 2c43ad1bcd01
Step 3/9 : WORKDIR /var/www/html
 ---> Using cache
 ---> 59cc801dfb98
Step 4/9 : COPY package*.json /var/www/html/
 ---> Using cache
 ---> db23f459c896
Step 5/9 : RUN npm install
 ---> Using cache
 ---> fd765858b0e9
Step 6/9 : COPY . .
 ---> Using cache
 ---> 26c48f02fb45
Step 7/9 : RUN node tools/build.js :common
 ---> Using cache
 ---> f3128d8aaaf0
Step 8/9 : EXPOSE 80
 ---> Using cache
 ---> d70a38af9a47
Step 9/9 : CMD ["nginx", "-g", "daemon off;"]
 ---> Using cache
 ---> 8827e23ceb7f
Successfully built 8827e23ceb7f
Successfully tagged dockerwillem/hight-js:latest
```
