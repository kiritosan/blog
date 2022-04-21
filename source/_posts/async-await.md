---
title: async await
date: 2022-04-21 13:01:46
tags:
---
```javascript
async function fun(){
    let a = await 1;
    let b = await new Promise((resolve,reject)=>{
        setTimeout(function(){
            resolve('setTimeout')
        },3000)
    })
    let c = await function(){
        return 'function'
    }()
    console.log(a,b,c)
}
fun(); // 3秒后输出： 1 "setTimeout" "function"
```


两者为promise的语法糖

## async
将返回的值包裹成一个promise对象

## await
await将后面的表达式用new Promise包裹，然后把await所在行前面的和await所在行下面的放到这个newPromise的then函数里

当promise已决，则立马将await后面的代码放入微队列（因为这些代码放入了then里面）

当promise未决，则先将await后面的代码存储到一个回调列表中，当promise的值确定，将await后面的代码推入到微队列里，保证执行到await后面的代码的时候可以得到promise的值