---
title: Promise
date: 2021-12-14 20:38:43
tags:
- 前端
---
## 简易实现+链式调用（值唯一）+状态+延迟机制

```javascript
class Promise {
    constructor(executor){
        // executor(this.resolve.bind(this)) 用函數定義式需要綁定this react藉鑒的方法
        executor(this.resolve)
    }
    // 回調函數數組
    cb = []
    state = 'pending'
    value = null
    // then
    then(onFullfilled) {
        if (this.state === 'pending') {
            this.cb.push(onFullfilled)
        } else {
            onFullfilled(this.value) // 解決狀態 則函數可以直接運行
        }
        return this // 重要 鏈式調用初步
    }
    // resolve 用函數表達式和箭頭函數就不用bind了
    // 在函數里用了this就要小心了 這裏想讓this是promise實例 有兩種方法 一種硬綁定bind 一種箭頭函數
    resolve = (value) => {
        if (this.state === 'pending') {
            this.state === 'fullfilled'
        }
        this.value = value // 存值
        this.cb.forEach(fn => fn(value)) // 執行
    }
}

let p = new Promise((resolve) => {
    setTimeout(() => {
        resolve(3)
    }, 1000);
})

p.then((value) => {
    console.log(value)
})
```



## ref
https://mp.weixin.qq.com/s/UNzYgpnKzmW6bAapYxnXRQ

https://mp.weixin.qq.com/s?__biz=MzI4NjY4MTU5Nw==&mid=2247486706&idx=2&sn=9434eb4f5ea43e46de70a6486afbffbf&chksm=ebd87c60dcaff57669d389cf114a993b15df789b1b14fe1f4c89e38d304d79489dc5394e9296&cur_album_id=1500522652875194368&scene=189#wechat_redirect