---
title: HTML基础总结-freecodecamp
date: 2021-03-01 15:49:22
tags:
- 前端 
---

## 在freecodecamp学到的HTML总结

因为html标准一直在不断变化之中，所以在html的前面要声明文档类型

```html
<!DOCTYPE html>
```

html发展到了html5，新添加了main，header，footer等标签使得网页结构更加清晰。

DIV是html之中最常见的标签，全称为dividion.

标签分为单标签和双标签，单标签如img。

有实体，本身就是一个对象的标签为单标签，单标签有实体可以用双标签修饰，如图片可以用a嵌套。

作为属性存在，用来修饰实体而存在的以双标签的形式存在。

head body main footer 表示页面的结构

ul全称为unordered list

ol全称为ordered list

a全称为anchor href 可以外链可以内链(添加相应id)可以死链#(死链用于占位，之后再添加链接)

img src alt

p h1

ul

ol

form为表单，在表单里面添加input和button 有action属性

input type(text/radio/checkbox) placeholder[占位字符] name[提交给服务器的前半数据] value[提交给服务器的后半数据] checked[默认勾选]

button type(submit)

可以用lable标签将input和字符串封装为一个组件

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://bit.ly/fcc-relaxing-cat" alt="A cute orange cat lying on its back."></a>

  <div>
    <p>Things cats love:</p>
    <ul>
      <li>cat nip</li>
      <li>laser pointers</li>
      <li>lasagna</li>
    </ul>
    <p>Top 3 things cats hate:</p>
    <ol>
      <li>flea treatment</li>
      <li>thunder</li>
      <li>other cats</li>
    </ol>
  </div>

  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label><input type="checkbox" name="personality" checked> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
