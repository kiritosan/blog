---
title: css布局学习记录
date: 2021-04-15 01:28:56
tags:
- 前端
---
## 学习源

https://zh.learnlayout.com/

## display属性

css中通过display来控制元素的布局

大多数的元素默认布局有两种块状和行内,于是元素被分成块状元素和行内元素

div 是一个标准的块级元素。单独占据一行。

span 是一个标准的行内元素。可以放在一行内部。

display:none可以用来在不铲除元素的情况下隐藏元素

这种情况和visibility: hidden不一样，后者是隐形，前者是消失。区别在于使用后元素是否占据空间。

元素类型可以改写

常见的例子是：把 li 元素修改成 inline，制作成水平菜单。

[display的值](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

## [position](https://zh.learnlayout.com/position.html)

position属性的默认值是static，不会被特殊定位。在文档流（normal flow）中正常显示。

关于文档流和文本流的参考：

https://www.w3.org/TR/CSS21/visuren.html

https://blog.csdn.net/qq_40421277/article/details/79687268

这篇csdn里面说的float脱离文档流不准确。

https://www.zhihu.com/question/21911352

表面上看，float脱离了“文档流”，没有脱离“文本流”

实际上，根据英文文档上面解释的意思,当元素浮动的时候,会先遵循“Normal flow”的规则，然后尽可能的向俩边靠。所以float并不是会脱离文档流，反而是依赖于文档流。

> 至于文本流，我自己还没有看到这种解释的。在“Normal flow”中，BFC规则中，文本会围绕在浮动元素旁边。出现了这种现象，可能国人就自定义了“文本流”这种东西。

https://segmentfault.com/a/1190000012425858







