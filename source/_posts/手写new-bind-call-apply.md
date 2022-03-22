---
title: '手写new, bind, call, apply'
date: 2022-03-22 22:36:25
tags:
---
## myNew
```javascript
function myNew(constructor, ...args) {
    let obj = {}
    obj.__proto__ = constructor.Protorype
    constructor.call(obj, ...args)
    return obj
}
```
## myBind
```javascript
Function.prototype.myBind = function(obj=window, ...outerArgs){
    let _this = this
    return function(...innerArgs){
        _this.call(obj, ...outerArgs.concat(innerArgs)) // call接收的是多个参数 apply接收的是数组
    }
}
```



## myCall
```javascript
Function.prototype.myCall = function(obj=window, ...args){
    obj.f = this
    const res = obj.f(...args)
    delete obj.f
    return res
}

```
## myApply
```javascript
Function.prototype.myApply = function(obj=window, args){ // apply传入数组
    obj.f = this
    const res = obj.f(...args)
    delete obj.f
    return res
}
```

## ref

[【前端面试】new, bind, call, apply 手写](https://zhuanlan.zhihu.com/p/268640216)

