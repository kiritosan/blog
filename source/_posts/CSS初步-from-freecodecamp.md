---
title: CSS初步 from freecodecamp
date: 2021-03-02 11:16:44
tags:
- 前端
---

CSS 层叠样式表
html表示网页结构
css丰富网页样式

## CSS应用方式

### 1.作为标签的属性

```html
<h2 style="color:green">用标签属性改变字体颜色</h2>
```

<h2 style="color:green">用标签属性改变字体颜色</h2>

> 在页面中使用CSS样式有以下几种方法：行内样式、内嵌式、链接式和导入式。
> 行内样式
> 行内样式就是直接把CSS代码添加到HTML的标记中，即作为HTML标记的属性标记存在。通过这种方法，可以很简单地对某个元素单独定义样式。 ---https://www.w3cschool.cn/eyv2f3/wydv1qbh.html"

### 2.head里面的style标签

在head里面添加style标签改变页面样式

```html
<style>
</style>
```

在style标签里面用CSS选择器选定要改变的元素

```html
<!-- 标签选择器 -->
<style>
  h2 {
    color: red;
  }
</style>
```

```html
<!-- 类选择器 -->
<style>
  .blue-text {
    color: blue;
  }
</style>
```

```html
<!-- id选择器 -->
<style>
  #cat-photo-element {
    background-color: green;
  }
</style>
```

```html
<!-- [attr=value]（属性=值）属性选择器 -->
<style>
/* 让所有type属性值为radio的元素加入 margin（外边距）做出改变 */
  [type='radio'] {
  margin: 20px 0px 20px 0px;
  }
</style>

```

### 3.外部的.css文件

使用行内样式直接对要进行改动的元素进行样式修改，使用别的方式为了能够对需要改变的元素进行专门改变就需要用定位器找到具体要修改的位置。使用其他方式的优势在于能够一个样式同时施予多个对象/元素，即可以复用。

需要注意的是，使用id选择器时，不可以复用，只能改变一个元素。原因是虽然id不唯一时css也能起作用，但id的唯一性却是在实际写网页时候的要求。

```html
<!-- https://zhidao.baidu.com/question/206705727.html -->
ID就像身份证号 每人只有一个，而且不会重复
class 就像你的姓名 可能会有很多人和一样的名字
ID权重比高，定位很快速
所以经常用ID用在JS效果层 和网页整体模块
另外告诉你 H1和相同ID一样 一个网页中只有一个H1和N个不同名的ID 别用很多个
```

## css数值的单位

绝对单位和相对单位

绝对有px（像素） in（英寸）和mm（厘米）

相对有em 或者 rem(root em)

## css的继承

body元素下的元素继承body的样式

继承有优先级 在style里 Id选择器优先于class选择器优先于标签选择器

ID属性样式覆盖类样式覆盖标签选择器样式

行内样式优先于选择器样式

使用important可以覆盖所有样式

使用例

```css
.brown-text {
  color: brown !important;
}
```

优先级: 标签声明 < CSS类声明顺序 < ID属性样式 < 行内样式 < !important



一个HTML元素是可以叠加多个CSS类，给一个元素多个CSS类只需要在多个类名之间加入空格即可；

```html
<!-- 类的摆放顺序不影响css样式权重 最后用哪个类的样式取决于最后一个定义的样式属于哪个类
因为css代码从上到下执行 下方代码会覆盖上方代码-->
<div class="class1 class2"></div>
```

## css变量

声明变量

```css
--penguin-skinCSS = gray；
```

使用变量

```css
background： var(--penguin-skin);
```

css变量的回退值

当变量无法获取到值时，浏览器有一个可回退的值可用，并且可以保证有效显示。并非提升兼容性的作用，在IE下回退不会生效。也就是说解决不了兼容性的问题。

例子

```css
background: var(--penguin-skin, black);
```

## 兼容问题

使用css很大可能会遇到兼容问题，一个好的解决办法是在可能不被识别的样式上方加入基础样式。这样低版本浏览器会自动忽略最新的样式使用基础样式，而新版本浏览器会用新的样式覆盖旧的样式。

```css
/* :root是一个伪类（pseudo-class）选择器，它会直接匹配HTML文档（document）中的根元素，即html元素； */
:root {
--red-color = red;
}

.red-box {
    /* 解决兼容问题的方法是在上面加入基础属性 */
    background: red;
    /* 在这里加入回退方案并不能如愿解决兼容问题，因为回退并非解决兼容问题的方案，回退不能被旧版本浏览器识别。回退解决的问题是请求的变量值丢失时的处理方法。 */
    background: var(--red-color);
}

```

## css变量的继承以及全局局部变量

:root伪类选择器中声明变量，则变量可以全局使用

在一个类选择器中声明变量，则变量可以在这个类选择器和其所有子节点中被调用，其他位置无法调用，位局部变量

全局变量想在局部特殊化怎么办？

只需要在局部重新声明该变量即可

## 使用媒体查询在特定情况改变变量数值

```css
<style>
    :root {
        --penguin-size: 300px;
    }

    @media (max-width: 350px) {
        :root{
            --penguin-size: 200px;
        }
    }



</style>
```

## css能修改的样式

### 文字操作

文字颜色

```css
/* 颜色指定方式：单词、HEX(Hexadecimal、十六进制)、RGB */
h2 {
  color: ;
}
```

用HEX表示颜色时，用#加六个十六进制数字表示。
前两位表示红色的数值，中间两位表示绿色的数值，最后两位表示蓝色的数值。

Hex颜色码可以缩写

红色的Hex颜色码为 #FF0000 可以被缩写为 #F00

各给每一个颜色一个数值

使用RGB表示颜色时，用rgb(0,0,0);表示，数值范围位0-255

HEX和RGB能表示颜色的数量是相同的


文字大小

```css
h2 {
  font-size: ;
}
```

字体

```css
h2 {
  font-family: sans-serif;
}
```

可以引入使用谷歌字体，以Lobster字体为例

```html
<!-- 在head的meta里面加入如下内容 -->
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
```

```css
/* 字体名不含空格则可以不用双引号，字体名有空格必须要用双引号 */
h2 {
  font-family: Lobster;
}
```

通用语法

```css
/* GENERIC_NAME为备用字体，如果因为网络或其他原因找不到首选字体就会加载备用字体 */
h2 {
  font-family: FAMILY_NAME, GENERIC_NAME;
}
```

### 图片操作

图片尺寸

```css
<style>
  .larger-image {
    width: 500px;
  }
</style>
```

图片边框的颜色宽度样式弧度

```css
<style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
/* 边框弧度可以用pixel定义，也可以用百分比定义 */
    border-radius: 10px;
    border-radius: 50%;
  }
</style>
```

一行快速定义大小颜色样式

```css
/* 顺序能变吗? */
<style>
  .thin-red-border {
    border: 5px red solid;
  }
</style>
```

### 元素通用操作

设定元素背景颜色

```css
.green-background {
  background-color: green;
}
```

设定元素内外边距及边框(边距可以是负数)

HTML的元素基本上都是一个个像积木一样的正方形盒子组成的。

在网页版式设计过程中，调整内外边距以及边框是最常用的方法，用来调整元素间的空隙。图像如下图所示：

![边框图](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/%E8%BE%B9%E6%A1%86%E5%9B%BE.png)

上图中，蓝色区块为内容，往外依次是内边距、边框、外边距。

一个元素的margin(外边距)，控制这个元素与周围元素之间的空间；

一个盒子的content内容区域在没有给宽高的情况，会根据浏览器窗口大小适应。

盒子的总宽高 = content宽高 + padding + border + margin。

假设现在浏览器窗口的宽度是1000px，再假设有一个盒子可以填满这个浏览器宽度。这个时候盒子的content宽度就是:

```css
1000 - margin*2 (左右的margin外边距) - border*2(左右的border边框) - padding*2(左右的padding内边距) = 内容的px。
```

内容区域的大小始终受到margin，border和padding的总额影响
我们看到的盒子大小是盒子边框的大小，而不是盒子内容的大小。

这里引申盒模型的内容：
<!-- 不是很懂 -->
分两种:标准盒模型和IE盒模型

盒模型：标准盒模型

盒子宽度 = 内容的宽度

盒子高度 = 内容的高度

其他间距都是额外加入的，会影响盒子总体呈现的宽高

```css
如果不希望使用盒子的padding的时候影响盒子总体大小，我们就要把盒子变成IE盒模型

在盒子的CSS中添加box-sizing: border-box
```

盒模型：IE盒模型

盒子宽度 = border + padding + 内容的宽度

盒子高度 = border + padding + 内容的高度

盒子的框高包含了边框和内边距，所以整体的盒子高度不受padding和border影响。

```css
.box {
/* 内边距 边框 外边距 */

    padding: 20px;
    border: 5px;
    margin: 20px;
}
```

```css
.box{
/* 单独给每一个边缘不同的内外边距； */

    padding-top: 20px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 20px;

    margin-top: 20px;
    margin-right: 20px;
    margin-bottom: 20px;
    margin-left: 20px;
}
```

```css
.box {
/* 使用顺时针语法指定元素内外边距 上右下左 */

    padding: 10px 20px 10px 20px;
    margin: 10px 20px 10px 20px;
}
```

```css
/* 其他语法： */

/* 应用于四个边 */
padding: 1em;

/* 垂直方向| 水平方向*/
padding: 5% 10%;

/* 顶部| 水平方向| 底部*/
padding: 1em 2em 2em; 

/* 顶部| 右边| 底部| 左边*/
padding: 2px 1em 0 1em;
```

参考链接：

<https://www.freecodecamp.org/>

<https://juejin.cn/post/6844904161050378248>

<https://juejin.cn/post/6850418109867081742>