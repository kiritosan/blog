---
title: promise 的 then 何时执行
date: 2022-04-19 22:54:10
tags:
---

## 结论
promise的then方法同步执行（主线程执行）
new promise(fn)  主线程执行
new promise(fn).then(onFullfilled) 中then执行了才会返回对象来满足后面的调用 所以then也是在主线程执行 但是onFullfilled并不是在主线程执行
onFullfilled会被fullFiled函数包裹起来 当满足执行条件的时候，放入微队列
```javascript
let fulfilled = () => {
        try{
          const result = onFulfilled(self.value); // 承前
          return result instanceof MyPromise? result.then(resolve, reject) : resolve(result); //启后
        }catch(err){
          reject(err)
        }
      }
```
fullFiled函数做两件事情：1. 执行onFullfilled 2. 根据onFullfilled返回值的类型做不同操作：(值：resolve(值),promise对象：promise对象.then(resolve, reject))
而resolve产生两个效果：1. promise状态改变，promise值确定 2. 执行promise对象的回调列表

回调列表当promise为pending时候，then会将fullFiled传给promise对象的回调列表



new Promise((resolve)=>setTimeout(()=>resolve(3),3000)).then(val=>{console.log(val+1)}).then(val=>{console.log(val+1)})

1. 首先promise对象生成，状态未决
2. 调用对象的then方法，发现对象未决，会将fullFiled传给promise对象的回调列表 然后生成一个promise对象（每个promise对象生成默认是pending，只有resolve或reject后状态才会改变）
3. 生成的新的promise对象执行then方法，由于新对象状态未决，所以会将fullFiled传给新promise对象的回调列表 然后生成promise对象
异步开始：
1. 当第一个promise状态已决（执行resolve方法），那么就会将回调列表中的fullfiled函数放入微队列 然后执行同步任务
2. 执行到微队列，执行fullfiled函数，然后1执行onFullfilled，2resolve会使得对象已决，并且会触发新promise（中间的）的回调函数列表里的函数，将回调函数列表中的fullfiled函数放入微队列 然后执行同步任务
3. 再次执行到微队列，执行fullfiled函数，然后1执行onFullfilled，2resolve使得最后一个promise对象已决，由于是最后一个对象，没有回调列表，所以执行结束

表象：
new Promise同步执行（所以必定返回一个promise对象） 给new Promise传入的executor同步执行
.then同步执行（所以才能生成一个promise对象使得链式调用成为可能）
.then里面的函数异步执行 依次放入微队列
不管第一个promise的状态如何，紧接着的.then都会将传入的函数放入微队列，然后执行下面的同步代码
等到再次执行到微队列里面的函数，该函数执行完后则会将下一个.then里的函数放入微队列

分析步骤：
（明确new Promise 和 后面的then都会按顺序从左往右同步执行完）
首先executor同步执行
然后看executor里的resolve或reject何时执行（即promise状态何时改变）
resolve或reject何时执行，何时将紧跟着（重要！）的then里面的函数放入微队列 （如果then的时候已经是已决将函数放入微队列 promise是pending状态不对then里面的函数做任何操作，只要是已决状态就放入微队列，不管是then执行时就是已决还是之后变成已决）
等到再次执行该函数时，将下一个then里面的函数放入微队列
结束

简化：
只有promise对象状态变成不是pending的状态，才将next里的函数放入微队列

## 顺序
```javascript
new Promise(r => r(11))
.then(r11 => {
  console.log('r11', r11);
  return r11 + 1;
})
.then(r12 => {
  console.log('r12', r12);
  return r12 + 1;
})
.then(r13 => {
  console.log('r13', r13);
});
```
看开始执行的顺序new Promise要早于传入的executor，但是看结束执行顺序的话executor要先结束然后才生成了promise对象

delete----- then函数生成的promise一定是未决的，因为then里面的函数执行的同时才会执行resolve或reject，而then里面函数不是放在回调队列里（promise未决）就是放在微队列里（promies已决），不会立马执行。 -----delete 实际上返回的是已决的

then里面函数返回的值会成为then生成的promise已决的值


## Refs

https://www.cnblogs.com/smile-fanyin/p/14622432.html
https://blog.csdn.net/z591102/article/details/107203838 //一步一步分析
https://juejin.cn/post/6883121706123132936
https://zh.javascript.info/microtask-queue