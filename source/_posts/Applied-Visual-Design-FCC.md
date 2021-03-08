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

```css
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



```css
repeating-linear-gradient(
      45deg,
      yellow 0px,
      yellow 40px,
      black 40px,
      black 80px
    )
```

背景的url()函数

```css
<style>
  body {
    background:url("https://cdn-media-1.freecodecamp.org/imgr/MJAkxbh.png")
  }
</style>
```

transform参数改变元素大小为原来的数倍

```css
#ball2 {
  left: 65%;
  transform: scale(1.5);
}
```

移到元素上面改变元素大小 :hover

```css
div:hover {
  transform: scale(1.1)
}
```

transform属性的skewX函数把举行变成平行四边形 相对应的有skewY函数

```css
  #bottom {
    background-color: blue;
    transform: skewX(24deg);
  }
```

蓝月亮

```css
<style>
  .center {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100px;
    height: 100px;
    background-color: transparent;
    border-radius: 50%;
    box-shadow: 25px 10px 0px 0px blue;
  }

</style>
```

画一个心:heart:

transform的rotate()

::before  ::after

```css
<style>
  .heart {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: pink;
    height: 50px;
    width: 50px;
    transform: rotate(-45deg);
  }
  .heart::after {
    background-color: pink;
    content: "";
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: 0px;
    left: 25px;
  }
  .heart::before {
    content: '';
    background-color: pink;
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: -25px;
    left: 0px;
  }
</style>
<div class="heart"></div>
```

动画

动画属性(总共八个)和帧

animation property

```css
<style>
  div {
    height: 40px;
    width: 70%;
    background: black;
    margin: 50px auto;
    border-radius: 5px;
  }

  #rect {
    animation-name: rainbow;
    animation-duration: 4s;

  }

@keyframes rainbow {
  0% {
    background-color: blue;
  }
  50%{
    background-color: green;
  }
  100% {
    background-color: yellow;
  }
}



</style>
<div id="rect"></div>
```

改变悬浮到元素上时的颜色

```css
<style>
  button {
    border-radius: 5px;
    color: white;
    background-color: #0F5897;
    padding: 5px 10px 8px 10px;
  }

  button:hover {
    animation-name: background-color;
    animation-duration: 500ms;
  }
  
  @keyframes background-color {
    100% {
      background-color: #4791d0;
    }
  }

</style>

<button>Register</button>
```

通过改变动画填充模式使悬浮颜色变得持久

```css
#放置到:hover里
animation-fill-mode: forwards;
```

使用@keyframes里面的top和left参数移动元素

```css
<style>
  div {
    height: 40px;
    width: 70%;
    background: black;
    margin: 50px auto;
    border-radius: 5px;
    position: relative;
  }

  #rect {
    animation-name: rainbow;
    animation-duration: 4s;
  }

  @keyframes rainbow {
    0% {
      background-color: blue;
      top: 0px;
      left:0px;
    }
    50% {
      background-color: green;
      top: 50px;
      left:25px;
    }
    100% {
      background-color: yellow;
      top: 0px;
      left:-25px;
    }
  }
</style>

<div id="rect"></div>
```



