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

## 将网格划分为区域模板

通过使用grid-template-areas将部分网格合成为一个有名字的区域（area）

```CSS
<--!每个单词代表一个网格单元格，每对引号代表一行 除了自定义标签之外还可以使用点（.）来表示一个空单元格-->
grid-template-areas: "header header header" "advert content content" "footer footer footer";
```

## 使用 grid-area 属性将项目放置在网格区域中

在为网格添加区域模板后，通过对网格项使用 grid-area属性，属性值设定为定义区域的名称，将元素放入相应的区域。

```CSS
    grid-area:footer;
```

## 使用 grid-area 创建区域模板

网格中没有定义区域模板的情况下可以用grid-area直接创建区域模板

```CSS
item1 { grid-area: 1/1/2/4; }

<--!顺序为grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;-->

```

## 使用 repeat 函数减少重复

```CSS
<--!先重复次数 后重复值-->
grid-template-rows: repeat(100, 60px);
grid-template-columns: repeat(2, 1fr 60px) 20px;
<--!等价于grid-template-columns: 1fr 60px 1fr 60px 20px;-->
```

## 使用 minmax 函数限制项目大小

grid-template-columns和grid-template-rows可以使用内置函数minmax在网格容器改变大小时限制网格项的大小

```CSS
<--!通过 grid-template-columns 添加两列，第一列宽度为 100px，第二列宽度最小值是 50px，最大值是 200px。-->
grid-template-columns: 100px minmax(50px, 200px);
```

## 使用 auto-fill 创建弹性布局

repeat函数有自动填充(auto-fill)的功能，能够根据容器的大小，尽可能多地放入指定大小的行或列。

```CSS
<--!下面的代码效果是：首先，列的宽度会随容器大小改变。其次，只要容器宽度不足以插入一个宽为 60px 的列，当前行的所有列就都会一直拉伸。**注意：**如果容器宽度不足以将所有网格项放在同一行，余下的网格项将会移至新的一行。-->
grid-template-columns: repeat(auto-fill, minmax(60px, 1fr));
```

## 使用 auto-fit 创建弹性布局

auto-fit 效果几乎和 auto-fill 一样。 不同点仅在于，当容器的大小大于各网格项之和时，auto-fill 会持续地在一端放入空行或空列，这样就会使所有网格项挤到另一边；而 auto-fit 则不会在一端放入空行或空列，而是会将所有网格项拉伸至合适的大小。

```CSS
<--!和上面代码效果一起放在一起比较好理解-->
grid-template-columns: repeat(auto-fit, minmax(60px, 1fr));
```

## 使用媒体查询创建响应式布局

```CSS
  @media (min-width: 400px){
    .container{
      grid-template-areas:

        "header header"
        "advert content"
        "footer footer";

    }
  }
```

## 在网格中创建网格

由于将元素转换为网格只会影响其子元素（direct descendants），所以把某个子元素设置为网格，就会得到一个嵌套的网格。

```CSS
  .item3 {
    background: PaleTurquoise;
    grid-area: content;
    display: grid;
    grid-template-columns: auto 1fr;
  }
```

完