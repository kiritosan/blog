---
title: Applied Accessibility From FCC
date: 2021-03-08 23:23:27
tags:
- 前端
---



img加上alt属性

图片有文字描述时 仍需要alt属性，但可以留空 alt=''

每个页面只能有一个h1

使用headings标签时候要和语义相对应，并注意h1 h2 h3的上下级关系，不能只根据大小随意使用

可以使用css调整h2和h4的相对大小



html5添加了许多语义标签

```html
main, header, footer, nav, article, section
```

article修饰独立文章

section修饰相同主题的一些类内容

article和section可以互相嵌套

内容与内容之间没有联系用div

<div> - groups content <section> - groups related content <article> - groups independent, self-contained content

header不同于head 放在body中

`header` shares the embedded landmark feature you saw with `main`, allowing assistive technologies to quickly navigate to that content.



nav 导航标签

之前用div包裹的导航列表用nav替换



footer标签

页脚用footer标签包裹



```
header` and `nav`, the `footer都可以让assistive devices快速定位
```

footer常常用来包裹版权信息与相关文档的链接  

html5新增audio标签

```html
<audio controls>
	<source src='https://s3.amazonaws.com/freecodecamp/screen-reader.mp3' type="audio/mpeg">
</audio>
```

<audio controls>
	<source src='https://s3.amazonaws.com/freecodecamp/screen-reader.mp3' type="audio/mpeg">
</audio>

`figcaption` 和 `figure` 标签

div -> p

figure -> figcaption



label标签和for属性 for属性赋予id的值

```html
    <form>
      <p>Sign up to receive Camper Cat's blog posts by email here!</p>


      <label for = "email">Email:</label>
      <input type="text" id="email" name="email">


      <input type="submit" name="submit" value="Submit">
    </form>
```



**radio buttons** often come in a group where the user must choose one



fieldset和legend标签

fieldset标签把radio buttons都包裹到一块来语义化表示这些选项是一组的

legend表示问题



div > p,input,label

fieldset > legend,input,label

```html
<fieldset>
    <legend>What level ninja are you?</legend>
    <input id="newbie" type="radio" name="levels" value="newbie">
    <label for="newbie">Newbie Kitten</label><br>
    <input id="intermediate" type="radio" name="levels" value="intermediate">
    <label for="intermediate">Developing Student</label><br>
    <input id="master" type="radio" name="levels" value="master">
    <label for="master">Master</label>
</fieldset>
```

表单一般都有input标签，其属性type表示什么样的input会被创建出来

html5中新加了type = "date"  老式浏览器会显示为type="text"

```html
<label for="pickdate">Preferred Date:</label>
<input type="date" id="pickdate" name="date">
```



html5中引入了带有datetime属性的time标签使得日期规范化、标准化 以供asistant devices访问

```html
<time datetime = "2016-09-15">Thursday, September 15<sup>th</sup></time>
```



CSS is used to position the **screen reader-only elements** off the visual area of the browser window.

css通过改变.sr-only里面的东西使得一些元素变得不可见

```
  <style>
  .sr-only {
    position:absolute  ;
    left:-10000px ;
    width: 1px ;
    height:1px  ;
    top: auto;
    overflow: hidden;
  }
  </style>
```



The Web Content Accessibility Guidelines (WCAG) recommend at least a 4.5 to 1 contrast ratio for normal text. 

The ratio is calculated by comparing the relative luminance values of two colors.

This ranges from 1:1 for the same color, or no contrast, to 21:1 for white against black, the strongest contrast. 

**Sufficient** 的定义↑

数值可以从网上找工具计算

前景色和背景色对比度高可以使字更容易辨识

```html
<!--6:1-->
  body {
    color: #636363;
    background-color: #FFF;
  }
  </style>
<!--1.5:1 对比度太低--> 
  <style>
  body {
    color: #D3D3D3;
    background-color: #FFF;
  }
  </style>    

```



visual design中使用颜色时有两个需要注意的点：一、颜色不能作为传达重要信息的唯一方式( screen reader users看不到)二、前景色背景色对比度合适，可以让色盲用户区分出来

在实践中，调整对比度使其接近4.5:1的方法为shading(adding black to)  the darker color和tinting(adding white to) the lighter color

In practice, the 4.5:1 contrast ratio can be reached by shading (adding black to) the darker color and tinting (adding white to) the lighter color. Darker shades on the color wheel are considered to be shades of blues, violets, magentas, and reds, whereas lighter tinted colors are oranges, yellows, greens, and blue-greens.

色盲有很多种类 其中最常见的是降低对绿色的识别能力，比如相似的两种绿色当前景色和背景色时，很难识别

色轮上相邻的颜色即为close colors相似的颜色 在传达重要信息时，要避免这样



**Give Links Meaning by Using Descriptive Link Text**

使用描述性链接文本描述链接的意思

Having a list of "click here" or "read more" links isn't helpful. Instead, you should use brief but descriptive text within the `a` tags to provide more meaning for these users.

点击和更多不能很好的传达意思 应该用简短但是能清晰表明意思的文本替换

```html
<p><a href="">Click here</a> for information about batteries</p>

<!--修改后-->

<p>Click here for <a href="">information about batteries</a></p>
```



html有accesskey属性 html5中可以任何元素都有这个属性，但是有交互的标签的accesskey属性更有用

`accesskey`  = " `g` "(for Garfield)  " `c` "(for Chuck Norris).



tabindex属性

表格链接天然接收焦点定位 但像a，div标签等别的标签可以指定tabindex="0"来获得焦点

A negative `tabindex` value (typically -1) indicates that an element is focusable, but is not reachable by the keyboard.

```html
<head>
  <style>
  p:focus {
    background-color: yellow;
  }
  </style>
</head>
<body>
  <header>
    <h1>Ninja Survey</h1>
  </header>
  <section>
    <p tabindex = "0">Instructions: Fill in ALL your information then click <b>Submit</b></p>
  </section>
  <footer>
  </footer>
</body>
```

通过将tablindex的数值设定的多少决定获得焦点的优先级  设置时需谨慎，根据需要设置

```html
  <form>
    <label for="search">Search:</label>


    <input type="search" name="search" id="search" tabindex="1">
    <input type="submit" name="submit" value="Submit" id="submit" tabindex="2">


  </form>
```



完



