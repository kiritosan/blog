---
title: 给博客添加站点地图sitemap
date: 2021-02-08 11:25:28
tag: 

---





## 什么是站点地图

站点地图，Sitemap 是一个形式为xml或html的文件

### 谷歌爬虫抓取网站的方式:	[Google 搜索的工作方式  | Google 搜索中心  | Google Developers](https://developers.google.com/search/docs/beginner/how-search-works)

#### 抓取

抓取是指 [Googlebot](https://developers.google.com/search/docs/advanced/crawling/googlebot) 访问要添加到 Google 索引中的新网页和更新后的网页的过程。

我们使用大量计算机提取（或“抓取”）网络上的数十亿个网页。执行抓取任务的程序叫做 Googlebot（也称为漫游器或“蜘蛛”程序）。Googlebot 使用算法流程确定要抓取的网站、抓取频率以及要从每个网站抓取的网页数量。

#### 编入索引

Googlebot 会处理它抓取的每个网页，以便了解每个网页的内容。这包括处理文字内容、关键内容标记和属性，例如 `<title>` 标记和 Alt 属性、图片、视频等。Googlebot 可处理多种类型的内容，但并不是所有类型的内容都能处理。例如，我们无法处理某些富媒体文件的内容。

请注意，Google 不会将包含 [noindex 指令](https://developers.google.com/search/docs/advanced/crawling/block-indexing)（标头或标记）的网页编入索引。但前提是 Google 必须能够看到该指令；如果网页被 [robots.txt 文件](https://developers.google.com/search/docs/advanced/robots/intro)、登录页或其他设备屏蔽了，那么即使 Google 并未访问该网页，也可能会将其编入索引！

#### 呈现（和排名）

用户输入查询时，我们的机器会在索引中搜索匹配网页，并返回我们认为与用户搜索最相关的结果。相关性是由数百个因素决定的，我们一直在努力改进算法。Google 在选择结果和对其进行排名时会考虑用户体验，因此请务必确保您的网页能[快速加载](https://developers.google.com/speed/)且[适合移动设备](https://developers.google.com/search/mobile-sites)。

想更加详细了解请点击下面的链接：

[Google 搜索的工作方式 | 概览](https://www.google.com/search/howsearchworks/)

## 有什么作用

通过添加Sitemap可以更好的使爬虫抓取网站

## 添加站点地图Sitemap

进入到博客根目录

在终端输入如下命令(安装自动生成sitemap插件)

```
npm install hexo-generator-sitemap --save #给谷歌看
npm install hexo-generator-baidu-sitemap --save #给百度看
```

结束。

## 测试是否添加成功

在浏览器地址栏输入**域名/sitemap.xml**和**域名/baidusitemap.xml**

![image-20210208120338078.png](https://i.loli.net/2021/02/08/Ho5ThKVIq37GyRg.png)

## 将站点地图提交到谷歌

谷歌给站长提供了一个工具：

https://search.google.com/search-console

在里面添加网站后会是下面这种效果

![image-20210208115910684.png](https://i.loli.net/2021/02/08/RSGHLVnDOXlZ1qh.png)

点击位于侧边栏的站点地图，然后添加自己的适用于谷歌的sitemap地图，提交

![image-20210208120109518.png](https://i.loli.net/2021/02/08/JdTBCSPqDRFZXV8.png)

提交之后需要等待一段时间生效。