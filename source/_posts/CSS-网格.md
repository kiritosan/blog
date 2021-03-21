---
title: CSS 网格
date: 2021-03-21 09:20:13
tags:
---

## 创建第一个 CSS 网格

将display属性的值变为grid，HTML就变成了一个网格容器。

在 CSS 网格中，父元素称为容器（container） 子元素称为项（items）

```CSS
display:grid;
```

## 使用 grid-template-columns 添加多列

```CSS
<--!几个值就是几列，值为宽度-->
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```

## 使用 grid-template-rows 添加多行

```CSS
<--!grid-template-rows为网格添加多行-->
  .container {
    display: grid;
    grid-template-columns: 100px 100px 100px;

    grid-template-rows: 50px 50px;

```

## 使用 CSS 网格单位来更改列和行的大小

grid-template-columns: auto 50px 10% 2fr 1fr;
可以使用绝对单位（如 px）或相对单位（如 em）来定义行或列的大小

fr：设置列或行占剩余空间的比例

auto：设置列宽或行高自动等于它的内容的宽度或高度

%：将列或行调整为它的容器宽度或高度的百分比

grid-template-columns: auto 50px 10% 2fr 1fr;

## 使用 grid-column-gap 创建多列之间的间距

    grid-column-gap: 20px;

## 使用 grid-row-gap 创建多行之间的间距

grid-row-gap:5px;

## 使用 grid-gap 为网格添加间距

grid-gap的值分别为行间隔和列间隔

grid-gap: 10px 20px;

## 使用 grid-column 来控制空间大小

以上都是对网格容器的属性的修改以及应用。
在网格中，假想的水平线和垂直线被称为线（lines）。 这些线在网格的左上角从 1 开始编号，垂直线向右、水平线向下累加计数。

一个 3x3 网格的线条：


![grid网格](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/grid%E7%BD%91%E6%A0%BC.png)

使用grid-column属性的加上网格线的起止编号定义元素在网格中列的起始和结束的位置。

grid-column: 1 / 3;

## 使用 grid-row 来控制空间大小

    grid-row: 2 / 4 ;

## 使用 justify-self 水平对齐项目

start：使内容在单元格左侧对齐

center：使内容在单元格居中对齐

end：使内容在单元格右侧对齐

```CSS
<--!默认为stretch-->

  .item2 {
    justify-self: center;
  }
```

## 使用 align-self 垂直对齐项目

```CSS
  .item3 {
    align-self:end;
  }
```

## 使用 justify-items 水平对齐所有项目

```CSS
<--!在container中设置justify-items来控制所有的元素水平对齐方式-->
  .container {
    justify-items: center;
  }
```

## 使用 align-items 垂直对齐所有项目

```CSS
    align-items: end;
```

## 
