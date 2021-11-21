---
title: Promise
date: 2021-11-21 17:46:20
tags:
- js
---
# 期约

执行new Promise(()=>())会返回一个Promise对象

使用构造函数必须传入一个executor函数，否则会报错

执行Promise.resolve()静态方法也会返回一个Promise对象

执行Promise.catch()静态方法也会返回一个Promise对象

执行Promise.prototype.then()也会返回一个Promise对象

如果then()里面不传参数的话，会默认为then((x) => {x})，会返回上一个Promise的值来传入Promise.resolve()来包装成一个新的Promise()，但这个Promise与上个Promise的值是相同的。

Promise可以链式调用原因：Promise原型的then方法返回的是一个Promise对象，实现过程为将onResolved的返回值传入Promise.resolve()从而将这个值包装成一个Promise来支持链式调用。
onResolved是then()里的第一个位置的函数。
then()里可以接受两个函数参数,第一个是onResolved,另一个是onRejected。

```javascript
new Promise((resolve, reject) => {
    reject()
}).then(null, () => {
    console.log('A')
}).then(() => {
    console.log('B')
}).then(() => {
    console.log('C')
}).catch(() => {
    console.log('D')
})
```

以上代码不会输入D，因为catch()不会执行
在执行到console.log('c')后，返回了一个fulfilled的Promise对象，这个对象应当被onResolved函数处理，而catch()里面接收onRejected函数，所以这个Promise对象不会传到catch()函数里，而是会作为一个输出输出到控制台。

```javascript
new Promise((resolve, reject) => {
    reject();
}).then(null, () => {
    console.log('A')})

new Promise((resolve, reject) => {
    reject();
}).catch(() => {
    console.log('A')})
```
以上两段代码效果相同，catch方法只接收onReject()函数参数，而then函数可以分别接收onResolve()和onReject()两个函数参数。

基于onResolve()和onReject()最终都会有Promise的返回值，处理的逻辑也是一样的，都是将两个函数的返回值作为参数传递给Promise.resolve()

即在then()和catch()里，在调用完onResolve()或onReject()函数获得返回值之后，都会将这个返回值传入Promise.resolve()中从而返回一个Promise从而来链式调用。

不同的只是then()可以接受onResolve()onReject()两个函数，而catch()只可以接受onReject()一个函数。

## ref

[深入理解Promise](https://bubuzou.com/2020/10/22/promise/)

