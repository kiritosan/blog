---
title: CSS Flexbox
date: 2021-03-12 13:09:42
tags:
- 前端

---

## **Use display: flex to Position Two Boxes**

通过display: flex; 使用flexbox布局

## **Add Flex Superpowers to the Tweet Embed**

通过在需要的地方加入display:flex将其变成flexbox布局

## **Use the flex-direction Property to Make a Row**

翻转行

```css
<style>
  #box-container {
    display: flex;
    height: 500px;
    flex-direction:row-reverse;
  }
</style>

属性值 row-reverse column-reverse
```

**Note:** The default value for the `flex-direction` property is `row`.

## **Apply the flex-direction Property to Create Rows in the Tweet Embed**

要求:Add the CSS property `flex-direction` to both the `header` and `footer` and set the value to `row`.

header和footer设置格式后其子节点都会继承flexbox布局，设置flex-derection:row;之后header和footer及其子节点都会水平居中

## **Use the flex-direction Property to Make a Column**

```css
  #box-container {
    display: flex;
    height: 500px;
    flex-direction:column;
  }
```

## **Apply the flex-direction Property to Create a Column in the Tweet Embed**

```css
  header .profile-name {
    display: flex;
    flex-direction:column;
    margin-left: 10px;
  }
```

## **Align Elements Using the justify-content Property**

![](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/Here%20is%20a%20useful%20image%20showing%20a%20row%20to%20illustrate%20the%20concepts%20below.png)

flex元素的排列方向被叫做main axis 主轴 对于row来说是一条水平线，column是一条垂直线。

```css
justify-content: center;
flex-start
flex-end
space-between
space-around
space-evenly



  #box-container {
    background: gray;
    display: flex;
    height: 500px;
    justify-content:center;
  }
```

## **Use the justify-content Property in the Tweet Embed**

```css
  header .profile-name {
    display: flex;
    flex-direction: column;
    justify-content:center;
    margin-left: 10px;
```

## **Align Elements Using the align-items Property**

flex containers的align-items属性也可以进行元素的位置调整，通过cross axis进行调整

cross axis 指和main axis相反的方向

align-items调整row时候的上下位置和column时候的左右位置

```css
align-items:

flex-start
flex-end
center
stretch
baseline
```

```css
  #box-container {
    background: gray;
    display: flex;
    height: 500px;
    align-items:center;
  }
```

## **Use the align-items Property in the Tweet Embed**

```css
  header .follow-btn {
    display: flex;
    align-items:center;
    margin: 0 0 0 auto;
  }
```

## **Use the flex-wrap Property to Wrap a Row or Column**

使用flex-wrap将flex item分割成多行或多列

默认情况下flex container将所有flexitem放在一起

比如一个row总是在一条线上

```css
flex-wrap:
nowrap
wrap
wrap-reverse


#box-container {
    background: gray;
    display: flex;
    height: 100%;
    flex-wrap:wrap;
  }
```

**Use the flex-shrink Property to Shrink Items**

上面都是通过对flex container进行作用进而影响下面的flex item

也有对flex item直接作用的属性，例如flex-shrink

```css
flex-shrink:
数值 数值越大，缩小的越厉害

  #box-1 {
    background-color: dodgerblue;
    width: 100%;
    height: 200px;
    flex-shrink:1;
  }

  #box-2 {
    background-color: orangered;
    width: 100%;
    height: 200px;
    flex-shrink:2;
  }
```

## **Use the flex-grow Property to Expand Items**

```css
<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-grow:1;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    flex-grow:2;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

flex-grow是和flex-shrink相对的属性

## **Use the flex-basis Property to Set the Initial Size of an Item**

```css
单位可以用px, em, %, etc


<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-basis:10em;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    flex-basis:20em;
  }
</style>
```
