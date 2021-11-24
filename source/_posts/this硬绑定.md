---
title: this硬绑定
date: 2021-11-24 13:46:33
tags:
- js
---
## this

```javascript
function foo() {
	console.log( this.a );
}

var obj = {
	a: 2
};

var bar = function() {
	foo.call( obj );
};

bar(); // 2
setTimeout( bar, 100 ); // 2

// `bar` hard binds `foo`'s `this` to `obj`
// so that it cannot be overriden
bar.call( window ); // 2
```

包装函数bar可能被任何人调用(使得bar的this指向任何人)，但其被调用时强制使其内部函数foo被obj调用（使得foo的this一直指向obj）

es5就有了内置的bind方法提供强制绑定的功能
```javascript
let bar = foo.bind(obj);
```

即时函数的参数列表里面不写形参，在调用参数的时候也能传递参数，并且这些参数会被存在arguments中，只是因为没有写形参名称所以不能用名字取得这些参数，但是可以从arguments中得到这些参数。

```javascript
function foo(el) {
	console.log( el, this.id );
}

var obj = {
	id: "awesome"
};

// use `obj` as `this` for `foo(..)` calls
[1, 2, 3].forEach( foo, obj ); // 1 awesome  2 awesome  3 awesome
```

有的内置函数有一个专门的参数用来执行this是谁

this指向的4种规则

- this绑定
  -  默认绑定 非严格模式下独立函数调用，this指向全局对象window；严格模式下，this指向undefined
  -  隐式绑定 Implicitly Lost 需要考虑隐式绑定丢失的情况
  -  显式绑定
    -  Hard Binding ```javascirpt foo.call(obj)```
	-  API Call "Contexts" ```javascirpt [1, 2, 3].forEach( foo, obj );```
  -  new Binding this指向构造函数构造的实例

四种规则有优先级，当四种规则同时适用时，使用优先级高的，默认绑定优先级最低。

箭头函数：es6新增箭头函数，不适用上面的4条规则，箭头函数采用来自封闭（函数或全局）作用域的this绑定。

var a = 2;意思就是给window添加一个属性a=2，两者是等价的


[You Don't Know JS: this & Object Prototypes
Chapter 2: this All Makes Sense Now!](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/this%20%26%20object%20prototypes/ch2.md#implicit-binding)
  