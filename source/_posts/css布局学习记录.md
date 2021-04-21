---
title: css布局学习记录
date: 2021-04-15 01:28:56
tags:
- 前端
---
## 学习源

https://zh.learnlayout.com/

## display属性

display属性配置浏览器渲染元素的方式，每种元素有其默认的渲染方式（display值）

css中通过display来控制元素的布局

大多数的元素默认布局有两种块状和行内,于是元素被分成块状元素和行内元素

div 是一个标准的块级元素。单独占据一行。

span 是一个标准的行内元素。可以放在一行内部。

display:none可以用来在不铲除元素的情况下隐藏元素

这种情况和visibility: hidden不一样，后者是隐形，前者是消失。区别在于使用后元素是否占据空间。

元素类型可以改写

常见的例子是：把 li 元素修改成 inline，制作成水平菜单。

[display的值](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

## box-sizing属性

```CSS
* {
  -webkit-box-sizing: border-box;
     -moz-box-sizing: border-box;
          box-sizing: border-box;
}
```

设置之后元素的内边距和边框不再会增加它的宽度。

## [position](https://zh.learnlayout.com/position.html)属性

### static

position属性的默认值是static，不会被特殊定位。在文档流（normal flow）中正常显示。

**除了static以外的所有值赋予元素后,元素就都变成了posioned元素**

关于文档流和文本流的参考：

https://www.w3.org/TR/CSS21/visuren.html

https://blog.csdn.net/qq_40421277/article/details/79687268

这篇csdn里面说的float脱离文档流不准确。

https://www.zhihu.com/question/21911352

表面上看，float脱离了“文档流”，没有脱离“文本流”

实际上，根据英文文档上面解释的意思,当元素浮动的时候,会先遵循“Normal flow”的规则，然后尽可能的向俩边靠。所以float并不是会脱离文档流，反而是依赖于文档流。

> 至于文本流，我自己还没有看到这种解释的。在“Normal flow”中，BFC规则中，文本会围绕在浮动元素旁边。出现了这种现象，可能国人就自定义了“文本流”这种东西。

https://segmentfault.com/a/1190000012425858

### relative

表现和static一样，不过可以使用top 、 right 、 bottom 和 left属性改变relative positioned元素的位置，并且别的元素的位置不会改变。

relative和元素开始的static状态相对

### fixed

根据视窗定位

移动浏览器对 fixed 的支持很差

### absolute

absolute根据最近的“positioned”祖先元素确定其位置,没有的话，相对body元素定位

absolute对于祖先元素绝对,absolute没有和relative放在一起的原因是虽然这两个单词词义相反,但在css用法上面却没有什么联系,反而和fixed有一定联系(一个根据视窗定位,一个根据祖先元素定位)

如果你使用了一个固定定位的页眉或页脚，确保有足够的空间来显示它们！我在 body 上面加了 margin-bottom 。

## float属性

```CSS
img {
  float: right;
  margin: 0 0 1em 1em;
}
```

Float 可用于实现文字环绕图片

在使用浮动控制图片时,可能会出现图片脱离元素容器的情况,可以通过清除浮动(清除浮动)解决

```CSS
.clearfix {
  overflow: auto;
}
```

[clearfix](https://stackoverflow.com/questions/211383/what-methods-of-clearfix-can-i-use)

## clear属性

clear用于控制浮动

https://zh.learnlayout.com/clear.html

## 百分比宽度布局

百分比是一种相对于包含块的计量单位。可以通过百分比布局使得图片宽度始终是容器宽度的50%

```CSS
article img {
  float: right;
  width: 50%;
}
```

## 响应式设计与[媒体查询](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

使用百分比宽度来布局，然后在浏览器变窄到无法容纳侧边栏中的菜单时，把布局显示成一列

```CSS
@media (min-width:600px) {
  nav {
    float: left;
    width: 25%;
  }
  section {
    margin-left: 25%;
  }
}
@media (max-width:599px) {
  nav li {
    display: inline;
  }
}
```

一些响应式布局做的好的网站:

https://mediaqueri.es/

使用 meta viewport 之后可以让你的布局在移动浏览器上显示的更好。

https://dev.opera.com/articles/an-introduction-to-meta-viewport-and-viewport/

## 创建很多网格来铺满浏览器的实现方式

### 困难的方式（使用浮动）

```CSS
.box {
  float: left;
  width: 200px;
  height: 100px;
  margin: 1em;
}
.after-box {
  clear: left;
}
```
### 容易的方式（使用 inline-block）
```CSS
.box2 {
  display: inline-block;
  width: 200px;
  height: 100px;
  margin: 1em;
}
```

在使用inline-block时需要注意一些问题:

1. vertical-align 属性会影响到 inline-block 元素，你可能会把它的值设置为 top 。
2. 你需要设置每一列的宽度
3. 如果HTML源代码中元素之间有空格，那么列与列之间会产生空隙

```CSS
nav {
  display: inline-block;
  vertical-align: top;
  width: 25%;
}
.column {
  display: inline-block;
  vertical-align: top;
  width: 75%;
}
```

## 实现文字的多列布局

```CSS
.three-column {
  padding: 1em;
  -moz-column-count: 3;
  -moz-column-gap: 1em;
  -webkit-column-count: 3;
  -webkit-column-gap: 1em;
  column-count: 3;
  column-gap: 1em;
}
```

CSS columns是很新的标准，所以你需要使用前缀，并且它不被IE9及以下和Opera Mini支持。

[支持程度](https://quirksmode.org/css/columns/)

## flexbox布局模式

[辨别flexbox版本](https://css-tricks.com/old-flexbox-and-new-flexbox/)

display: flex的为当前版本

[最新flexbox资料]https://bocoup.com/blog/dive-into-flexbox

https://zh.learnlayout.com/flexbox.html

## 浏览器开发者模式

在开发者模式下，可以通过分别按下ctrl、shift、alt来控制数值变化的幅度。

完



