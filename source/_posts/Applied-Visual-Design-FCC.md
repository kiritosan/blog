---
title: Applied Visual Design -FCC
date: 2021-03-02 16:50:10
tags:
- 前端

---

j

strong

u

em 放在p标签里面

s

hr 单标签

rgba()

padding

font-size



box-shadow

 \#thumbnail {

 	box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);

 }

图片和文本块的opacity属性

text-transform

​	uppercase

font-size

font-weight

line-height



```css
a:hover {
  color: red;
}
```



```css
p {
  position: relative;
  bottom: 10px;
}
```



**CSS Offsets**

绝对位置

position: absolute;

position: fixed;



float

  \#left {

   float: left;

   width: 50%;

  }

position: absolute | relative | fixed | sticky

  z-index: 2;

数值越大越高



  margin: auto;

元素自动居中



补色



primary colors

RGB

secondary colors

Mixing two primary colors creates the secondary colors cyan (G + B), magenta (R + B) and yellow (R + G).

Tertiary colors

Tertiary colors are the result of combining a primary color with one of its secondary color neighbors.



split-complementary color scheme

| Color     | Hex     |
| :-------- | ------- |
| orange    | #FF7F00 |
| cyan      | #00FFFF |
| raspberry | #FF007F |

色板上面的相反颜色(补色)并列放置给人对比强烈的印象



调整颜色色调

颜色的特征有hue, saturation, and lightness色调 饱和度 亮度

css引入了 hsl() hsl中色调使用色轮，而不是光谱 颜色的角度是一个0到360之间的数值

饱和度是颜色中的灰色的数值，饱和度100%没有灰色，饱和度0%都是灰色

亮度是颜色中白色和黑色的量，0%全是黑色 100%全是白色，50%为正常颜色

通过调整hsl中的s和l值更改颜色的色调



background color 的linear-gradient(90deg, red, yellow, rgb(204, 204, 255))函数设置线性颜色渐变

background: linear-gradient(35deg, #CCFFFF , #FFCCCC);

```html
<style>
  div {
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin: 50px auto;
    background: linear-gradient(35deg, #CCFFFF  , #FFCCCC);
  }

</style>

<div></div>
```