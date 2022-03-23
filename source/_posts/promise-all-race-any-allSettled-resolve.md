---
title: promise all race any allSettled resolve reject
date: 2022-03-23 19:45:46
tags:
- 前端
---
## all

```javascript
Promise.MyAll = function (promises) {
  let arr = [],
    count = 0
  return new Promise((resolve, reject) => {
    promises.forEach((item, i) => {
      Promise.resolve(item).then(res => {
        arr[i] = res
        count += 1
        if (count === promises.length) resolve(arr)
      }, reject)
    })
  })
}
```

## race

```javascript
Promise.MyRace = function (promises) {
  return new Promise((resolve, reject) => {
    // 这里不需要使用索引，只要能循环出每一项就行
    for (const item of promises) {
      Promise.resolve(item).then(resolve, reject)
    }
  })
}
```

## any

```javascript
Promise.MyAny = function (promises) {
  let arr = [],
    count = 0
  return new Promise((resolve, reject) => {
    promises.forEach((item, i) => {
      Promise.resolve(item).then(resolve, err => {
        arr[i] = { status: 'rejected', val: err }
        count += 1
        if (count === promises.length) reject(new Error('没有promise成功'))
      })
    })
  })
}
```

## allSettled

```javascript
Promise.MyAllSettled = function (promises) {
  let arr = [],
    count = 0
  return new Promise((resolve, reject) => {
    promises.forEach((item, i) => {
      Promise.resolve(item).then(res => {
        arr[i] = { status: 'fulfilled', val: res }
        count += 1
        if (count === promises.length) resolve(arr)
      }, (err) => {
        arr[i] = { status: 'rejected', val: err }
        count += 1
        if (count === promises.length) resolve(arr)
      })
    })
  })
}
```

```javascript
Promise.MyAllSettled = function (promises) {
  let arr = [],
    count = 0
  return new Promise((resolve, reject) => {
    const processResult = (res, index, status) => {
      arr[index] = { status: status, val: res }
      count += 1
      if (count === promises.length) resolve(arr)
    }

    promises.forEach((item, i) => {
      Promise.resolve(item).then(res => {
        processResult(res, i, 'fulfilled')
      }, err => {
        processResult(err, i, 'rejected')
      })
    })
  })
}
```

## reject

```javascript
Promise.myReject = function (value) {
  return new Promise((_, reject) => {
    reject(value)
  })
}
```

## ref
https://juejin.cn/post/7069805387490263047

https://juejin.cn/post/7038371452084551694