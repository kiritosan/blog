---
title: 手写promise
date: 2021-12-09 16:38:38
tags:
- 前端
---

```javascript
const PENDING = 'pending'; // 状态
const FULLFILLED = 'fullfilled';
const REJECTED = 'rejected';

function Promise(executor) {
  this.onFullfilled = [];
  this.onRejected = [];
  let _this = this;
  this.state = PENDING;
  this.value = undefined; // 成功时取得的值
  this.reason = undefined; // 失败原因
  function resolve(value) { // resolve作用:在promise未决时,1.改变状态为fullfilled,2.赋值,3.将onfullfilled放入微任务队列(此处为直接执行,没有放入微任务队列)
    if (_this.state === PENDING) { // 状态仅能改变一次
      _this.state = FULLFILLED;
      _this.value = value;
      _this.onFullfilled.forEach(fn => fn(value)); // 不能模拟推入微任务队列 这里直接执行
    }
  }
  function reject(reason) {
    if (_this.state === PENDING) {
      _this.state = REJECTED;
      _this.reason = reason;
      _this.onRejected.forEach(fn => fn(reason));

    }
  }
  executor(resolve, reject); // 同步执行传入的回调函数
}

Promise.prototype.then = function(onFullfilled, onRejected){ // then方法 没有进入微任务队列,直接进行的执行
  if (this.state === FULLFILLED) {
    typeof onFullfilled === 'function' && onFullfilled(this.value); // 直接执行,实际不会直接执行,而是放入微任务队列,等同步队列执行完后再执行
  }
  if (this.state === REJECTED) {
    typeof onRejected === 'function' && onRejected(this.reason);
  }
  if (this.state === PENDING) {
    typeof onFullfilled === 'function' && this.onFullfilled.push(onFullfilled);
    typeof onRejected === 'function' && this.onRejected.push(onRejected);
  }

  let _this = this;
  onFullfilled = typeof onFullfilled === 'function' ? onFullfilled : value => value;
  onRejected = typeof onRejected === 'function' ? onRejected : reason => {throw reason};

  function resolvePromise(promise2, x, resolve, reject) {
    if (promise2 === x) {
      reject(new TypeError('Chaining cycle'));
    }
    if (x !== null && (typeof x === 'object') || typeof x === 'function') {
      let used;
      try {
        let then = x.then;
        if (typeof then === 'function') {
          then.call(x, (y)=>{
            if (used) return;
            used = true;
            resolvePromise(promise2, x, resolve, reject);
          }, (r) => {
            if (used) return;
            used = true;
            reject(r);
          })
        } else {
          if (used) return;
          used = true;
          resolve(x);
        }
      } catch (error) {
        if (used) return;          
        used = true;
        reject(error);
      }
    } else {
      resolve(x);
    }
  }


  let promise2 = new Promise((resolve, reject)=>{
    if (_this.state === FULLFILLED) {
      setTimeout(() => {
        try {
          let x = onFullfilled(_this.value);
          resolvePromise(promise2, x, resolve, reject);    
        } catch (error) {
          reject(error);
        }
        
      });
      
    }else if (_this.state === REJECTED) {
      setTimeout(() => {
        try {
          let x = onRejected(_this.reason);
          resolvePromise(promise2, x, resolve, reject);
        } catch (error) {
          reject(error);
        }
      });
    }else if (_this.state === PENDING) {
      
      _this.onFullfilled.push(()=>{
        setTimeout(() => {
          try {
            let x = onFullfilled(_this.value);
            resolvePromise(promise2, x, resolve, reject);
            
          } catch (error) {
            reject(error);
          }
        });
      })
      _this.onRejected.push(()=>{
        setTimeout(() => {
          try {
            let x = onRejected(_this.reason);
            resolvePromise(promise2, x, resolve, reject)
            
          } catch (error) {
            reject(error);
          } 
        });
      })
    }
  })
  return promise2;
};
```

## ref
https://zhuanlan.zhihu.com/p/144058361