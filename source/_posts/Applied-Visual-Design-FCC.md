---
title: Applied Visual Design -FCC
date: 2021-03-02 16:50:10
tags:
- 前端

---

## strong

## u

## em 放在p标签里面

## s

## hr 单标签

## rgba()

## padding

## font-size

## box-shadow

```CSS
 #thumbnail {

 	box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);

 }
```

## 图片和文本块的opacity属性

## text-transform

​	uppercase

## font-size

## font-weight

## line-height



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

## 绝对位置

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

## 补色

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

## 调整颜色色调

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

## 背景的url()函数

```css
<style>
  body {
    background:url("https://cdn-media-1.freecodecamp.org/imgr/MJAkxbh.png")
  }
</style>
```

## transform参数改变元素大小为原来的数倍

```css
#ball2 {
  left: 65%;
  transform: scale(1.5);
}
```

## 移到元素上面改变元素大小 :hover

```css
div:hover {
  transform: scale(1.1)
}
```

## transform属性的skewX函数把举行变成平行四边形 相对应的有skewY函数

```css
  #bottom {
    background-color: blue;
    transform: skewX(24deg);
  }
```

## 蓝月亮

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

## 画一个心:heart:

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

## 动画

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

## 改变悬浮到元素上时的颜色

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

## 通过改变动画填充模式使悬浮颜色变得持久

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

## opacity属性

```css
<style>

  #ball {
    width: 70px;
    height: 70px;
    margin: 50px auto;
    position: fixed;
    left: 20%;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: fade;
    animation-duration: 3s;
  }

  @keyframes fade {
    50% {
      left: 60%;
      opacity:0.1;
    }
  }

</style>

<div id="ball"></div>
```

## animation-iteration-count属性设为infinite使球无限跳动

```css
<style>

  #ball {
    width: 100px;
    height: 100px;
    margin: 50px auto;
    position: relative;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: bounce;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }

  @keyframes bounce{
    0% {
      top: 0px;
    }
    50% {
      top: 249px;
      width: 130px;
      height: 70px;
    }
    100% {
      top: 0px;
    }
  }
</style>
<div id="ball"></div>
```

## 让心永恒跳动

```css
<style>
  .back {
    position: fixed;
    padding: 0;
    margin: 0;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: white;
    animation-name: backdiv;
    animation-duration: 1s;
    animation-iteration-count:infinite;
  }

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
    animation-name: beat;
    animation-duration: 1s;
    animation-iteration-count:infinite;
  }
  .heart:after {
    background-color: pink;
    content: "";
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: 0px;
    left: 25px;
  }
  .heart:before {
    background-color: pink;
    content: "";
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: -25px;
    left: 0px;
  }

  @keyframes backdiv {
    50% {
      background: #ffe6f2;
    }
  }

  @keyframes beat {
    0% {
      transform: scale(1) rotate(-45deg);
    }
    50% {
      transform: scale(0.6) rotate(-45deg);
    }
  }

</style>
<div class="back"></div>
<div class="heart"></div>
```

## 改变@keyframe里面的百分比使得两颗星星跳动频率不一致

```css
<style>
  .stars {
    background-color: white;
    height: 30px;
    width: 30px;
    border-radius: 50%;
    animation-iteration-count: infinite;
  }

  .star-1 {
    margin-top: 15%;
    margin-left: 60%;
    animation-name: twinkle-1;
    animation-duration: 1s;
  }

  .star-2 {
    margin-top: 25%;
    margin-left: 25%;
    animation-name: twinkle-2;
    animation-duration: 1s;
  }

  @keyframes twinkle-1 {
    50% {
      transform: scale(0.5);
      opacity: 0.5;
    }
  }

  @keyframes twinkle-2 {
    20% {
      transform: scale(0.5);
      opacity: 0.5;
    }
  }

  #back {
    position: fixed;
    padding: 0;
    margin: 0;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(black, #000099, #66c2ff, #ffcccc, #ffeee6);
  }
</style>

<div id="back"></div>
<div class="star-1 stars"></div>
<div class="star-2 stars"></div>
```

## 通过修改animation-duration修改三颗星星的频率

```css
<style>
  .stars {
    background-color: white;
    height: 30px;
    width: 30px;
    border-radius: 50%;
    animation-iteration-count: infinite;
  }

  .star-1 {
    margin-top: 15%;
    margin-left: 60%;
    animation-duration: 1s;
    animation-name: twinkle;
  }

  .star-2 {
    margin-top: 25%;
    margin-left: 25%;
    animation-duration: 0.9s;
    animation-name: twinkle;
  }

  .star-3 {
    margin-top: 10%;
    margin-left: 50%;
    animation-duration: 1.1s;
    animation-name: twinkle;
  }

  @keyframes twinkle {
    20% {
      transform: scale(0.5);
      opacity: 0.5;
    }
  }

  #back {
    position: fixed;
    padding: 0;
    margin: 0;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(black, #000099, #66c2ff, #ffcccc, #ffeee6);
  }
</style>

<div id="back"></div>
<div class="star-1 stars"></div>
<div class="star-2 stars"></div>
<div class="star-3 stars"></div>
```

## 修改animation-timing-function为linear和ease-out更改运动的加速度

```css
<style>

  .balls {
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #ball1 {
    left:27%;
    animation-timing-function:linear;
  }
  #ball2 {
    left:56%;
    animation-timing-function:ease-out;
  }

  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }

</style>

<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```

## cubic-bezier函数 控制运动方式 从00开始到11结束

```css
animation-timing-function:cubic-bezier(0.25, 0.25, 0.75, 0.75);

<style>
  .balls{
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 27%;
    animation-timing-function: cubic-bezier(0,0,0.58,1);
  }
  #blue {
    background: blue;
    left: 56%;
    animation-timing-function: ease-out;
  }
  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>
<div class="balls" id= "red"></div>
<div class="balls" id= "blue"></div>
```

```css
<style>
  .balls {
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    top: 60%;
    animation-name: jump;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 25%;
    animation-timing-function: linear;
  }
  #blue {
    background: blue;
    left: 50%;
    animation-timing-function: ease-out;
  }
  #green {
    background: green;
    left: 75%;
    animation-timing-function: cubic-bezier(0.311, 0.441, 0.444, 1.649);
  }

  @keyframes jump {
    50% {
      top: 10%;
    }
  }
</style>
<div class="balls" id="red"></div>
<div class="balls" id="blue"></div>
<div class="balls" id="green"></div>
```



结束



