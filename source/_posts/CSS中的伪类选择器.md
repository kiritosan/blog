---
title: CSS中的伪类选择器
date: 2021-04-10 01:39:36
tags:
- 前端
---
## 伪类选择器

伪：假的，不存在的

伪类选择器：假的，不存在的元素的选择器；对元素特定的状态的选择器，对元素特定状态生效

常见伪类：

a:hover

a:link

由于a:visited涉及用户隐私，所以只能改变color，不能改变背景颜色

a:visited

a:active

## 伪元素

表示元素中的特殊位置

p:first-letter
p:first-line
p:before
p:after

伪类和伪元素都是用来表示文档树以外的"元素"。

[力扣](https://leetcode-cn.com/circle/discuss/B56jUg/)

## 扩展

### 属性选择器

p[title]{}
p[title="Hello"]{}
<!-- 选择title属性值开头为Hel的元素 -->
p[title^="Hel"]{}

### 兄弟元素选择器

span + p{}

span ~ p{}

## 参考：

[bilibili](https://www.bilibili.com/video/BV1sW411T78k?p=28)
