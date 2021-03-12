---
title: Responsive Web Design Principles
date: 2021-03-12 11:02:41
tags:
- 前端
---

f

Media Queries

根据屏幕大小不同进行不同的css渲染

```css
@media (max-width: 100px) { /* CSS Rules */ }
@media (min-height: 350px) { /* CSS Rules */ }



<style>
  p {
    font-size: 20px;
  }

  /* Only change code below this line */
  @media (max-height: 800px) { 
    p {
      font-size: 10px;
    }
  }
  /* Only change code above this line */
</style>
```



**Make an Image Responsive**

给图片加上响应

```css
img {
  max-width: 100%;
  height: auto;
}
max-width为100%保证图片在容器中能够完全显示
height为auto保证图片原始比例不变
```



**Use a Retina Image for Higher Resolution Displays**

根据屏幕的像素密度不同 同一张图片可能在不同显示器上面显示效果不能，可能在有的显示器上面会看到像素点

最简单的使图片能够在高分辨率显示器上正确显示的方式是将图片原始宽高都变为原来的一半

```css
<style>
    img {
      height: 100px;
      width: 100px;
    }
</style>
```



**Make Typography Responsive**

viewport为打开的浏览器窗口

1vh是当前viewport高度的1%

1vw是当前viewport宽度的1%

vmin改变小边的比例

vmax改变大边的比例

[参考](https://blog.csdn.net/l13620804253/article/details/53436868)

```css
<style>
 h2 {
   width:80vw;
 }
 p {
   width:75vmin;
 }
</style>
```



完