---
title: js继承
date: 2022-03-29 13:29:19
tags:
---

es5继承的方式有很多种变种,但总体而言都是根据两种衍生出来的.
这两种是通过SuperType.call(this, ...args)进行的构造函数继承
以及通过SubType.prototype = 父类实例/父类原型/纯净父类实例(Object.create(SuperType.protorype))进行的原型链继承

构造函数继承调用了父类的函数体,得到了父类的属性和方法
原型链继承链接了子类和父类的原型(直接或间接):
1. 其中直接指向new SuperType()构造的实例间接链接,但父类的实例的属性会被共享
2. 指向父类原型SuperType.prototype,子类实例的隐式原型不能显示出父类是谁,因为SuperType.prototype显示为{...},而只有new SuperType()才会显示为SuperType{...}
3. 指向父类纯净实例能够显示出父类是谁 Object.create(SuperType.protorype)返回一个由父类原型构造出的实例,这个实例和1中的实例不同,不会有多余的属性和方法

通过原型链继承继承父类的属性和方法,通过原型链继承链接到父类从而继承父类原型的属性和方法

##ref

https://blog.csdn.net/chen34_11/article/details/108656116