---
title: Hexo + Vervel 免费搭建个人博客
date: 2021-01-27 19:30:36
tags:blog

---

# 本文记录使用Hexo和Vercel搭建个人博客时的过程以及一些问题



虽然以前也多多少少折腾过一些个人博客，也都是照着网上的一些教程一步一步做完了，但都是搭出来个博客的样子，没有进行个人博客最重要的内容的创作。

这次偶然间得知到Vercel这个平台，于是又开始建立自己的博客，来分享自己日常工作生活中的一些感悟。

因为有过之前github pages的经验，这次搭建过程不是非常困难，但是也遇到了不少问题。

由于先前的折腾，一些环境在我的电脑里面已经配置好了，比如Node.Js，Hexo-Cli等等。

接下来，我将以回忆的方式将搭建过程逐步写出来。

以下内容都是个人的理解，内容偏口语化，有可能会有错误，欢迎指教。

##  准备工作

### [Hexo](https://hexo.io/zh-cn/)

hexo是一个博客框架，不同于wordpress，它是一个生成静态博客的框架。个人理解wordpress和hexo的动态静态的区别类似编程语言中的脚本语言(比如Python)与编译语言(比如Java,C)的区别。

### [Github](https://github.com/)

github是一个代码托管平台，也是一个开源社区，我们可以将自己本地的代码上传到自己的公有仓库，这样大家就都可以查看并添加自己的想法进去，实现一个项目的可持续发展。

### [Vercel](https://vercel.com/)

Vercel个人理解相当于远程自动执行的个人电脑，使用hexo写文章并发布时一般需要先在本地运行hexo g生成静态页面，然后推送到github。而使用Vercel的话，不需要在本地生成hexo静态页面，只需将hexo的内容推送到github，vercel就会自动响应，生成静态页面并展示。

### 域名(可选)

这是我第二次花钱买域名，第一次是一年前在腾讯云花一块钱买的，到期之后续费要六七十，就放弃了，买的时候也没想要长久持有。当初是因为学生优惠买了一年的阿里云主机，于是顺势买了域名。阿里云主机到期后，域名也就没有续费。

在之前就是用免费域名了，记得曾经注册过一个.tk域名，免费域名麻烦的地方在于不稳定，不知道什么时候就会被回收。

这次是从[namesilo](https://www.namesilo.com/)买的.top域名，价格比较便宜，打算长期持有。

ataraxia.top这个个人域名来源于古希腊的一种哲学思想。

[Ataraxia](https://en.wikipedia.org/wiki/Ataraxia/)

## 原理

![image-20210127204635787.png](https://i.loli.net/2021/01/27/OqDxzovR7EmGwZK.png)

### 1. 用hexo在本地写好文章后推送到github

### 2. vercel监控到github改动

### 3. vercel重新部署页面

## 正题

终于到了正式开始的时候了，首先我们需要注册github和vercel的账号，具体过程不在赘述。

有了账号之后打开vercel网站

![image-20210203230848006.png](https://i.loli.net/2021/02/04/qZYonQfdrmOxCWT.png)



在主页点击New Project新建项目

![image-20210203231020014.png](https://i.loli.net/2021/02/04/PZnX6DkUILYKS7j.png)

然后点击右边Clone Template板块的Browse All Templates，找到Hexo点击进入到下一个页面。

![image-20210203231248697](https://i.loli.net/2021/02/04/1Vi7EGyorfqZPUw.png)

现在点击下面的Select，上面是团队版，需要付费使用。

![image-20210203231518221.png](https://i.loli.net/2021/02/04/5rwXAOjThYainy3.png)

接下来到了创建Git仓库并自动导入Hexo模版的流程，选择下面的Github。

![image-20210203231723811.png](https://i.loli.net/2021/02/04/3RtuhCiDYPqVX62.png)

选择之后应该会出现一个绑定github的页面，绑定即可，绑定后应该就是这个界面，点击Continue。

下面的复选框的选上的话就会创建一个私有的库，github现在可以免费创建私有库。

![image-20210203232234001.png](https://i.loli.net/2021/02/04/jOoQfmXpRLHMizx.png)

最上面的PROJECT NAME可以改成自己想取的项目名字，我这里就保持原样，然后点击Deploy，下面那两个倒三角先不用管。

![image-20210203232632537](https://i.loli.net/2021/02/04/YwSCU6RmabtZ2pG.png)

然后就会是这个页面，这个页面的意思是首先vercel会在github上面创建一个你命名的仓库，然后拉取hexo模板，这个时候github仓库上面就有了hexo框架(对应左边)，再然后vercel开始执行hexo的部署命令，生成静态博客文件并在网页上显示。(对应右边)

![image-20210203233044785.png](https://i.loli.net/2021/02/04/vnJATiSMpuKYgah.png)

部署成功后是这个效果，可以点击Visit查看，此时vercel会自动给网站绑定一个二级域名。

![image-20210203233209726.png](https://i.loli.net/2021/02/04/eHDsJKEGAF1IRM7.png)

这个就是我刚刚被分配给的二级域名。顺带一提，vercel部署成功后github还会发送一封邮件进行提示。

![image-20210203233259001.png](https://i.loli.net/2021/02/04/fYnlB4aQEcURAGS.png)

恭喜你，个人博客搭建成功！

搭建完成后需要的就是内容创做了，写完东西之后怎么提交，从哪里写，这就涉及到了使用git和github的知识了，等下一篇再说。