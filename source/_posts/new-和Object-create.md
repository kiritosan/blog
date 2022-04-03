---
title: new 和Object.create
date: 2022-04-03 09:59:58
tags:
---
js中定义一个函数，会自动生成一个这个函数对应的显示原型对象
这个对象会有一个constructor属性和一个隐式原型属性
例如：
function A(){}
定义函数A后会有一个A.prototype
此时，如果new 和Object.create(A.prototype) 都会生成一个A类型的对象
控制台会显示 A{}

但是如果将A原型的构造函数属性变成别的函数，情况就不同了
function B(){}
A.prototype.constructor = B
此时，通过new A()生成的对象是A{}
但是，通过Object.create(A.prototype)生成的对象确是B{}

可见，Object.create属性通过constructor的值决定对象类型的显示


总结：

定义构造函数，生成一个构造函数的原型，函数根据这个原型构造对象
这个原型有隐式原型属性和constructor属性
其中，new 构造函数生成的对象会指向构造函数的原型，这个对象的类型由构造函数的命名来决定，而不由原型的constructor属性值来决定
Object.create(构造函数.prototype)会根据原型直接生成一个对象，这个对象的类型根据构造函数的constructor的值来决定，生成的对象指向构造函数的原型
```javascript
funciton A(){}
funciton B(){}
A.prototype.constructor = B
new A()
Object.create(A.prototype)
```
此时得到的两个对象
一个是 A {}
一个是 B {}

但是指向的都是同一个原型 A.prototype 这个原型的construcor值为B