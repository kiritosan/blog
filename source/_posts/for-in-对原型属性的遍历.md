---
title: for in 对原型属性的遍历
date: 2021-11-22 21:42:27
tags:
- js
---
# for in
for in 遍历对象会导致对象原型上的可遍历对象也被遍历。
可以使用Object原型上的hasOwnProperty方法来将不是对象自身的属性过滤掉。


[JavaScript秘密花园](https://bonsaiden.github.io/JavaScript-Garden/zh/#object.forinloop)