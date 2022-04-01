---
title: 事件循环（node和浏览器）
date: 2022-04-01 14:42:52
tags:
---
## node
基于 libUV（有自己的实现）

timer
i/o callbacks
idle, prepare
poll
check
close callbacks

四个宏队列（上二 下二）
Timers Queue
IO Callbacks Queue
Check Queue
Close Callbacks Queue
两个微队列（nextTick Queue, Other Micro Queue)

先执行微队列
微队列中先nextTick Queue,后Other Micro Queue
微队列一旦执行就执行完
后宏队列
宏队列按顺序，先timer队列，然后从上到下依次进行，每执行完一个宏任务，就检查两个微任务队列中是否有任务，有就执行，微队列执行完后接着按顺序执行宏任务队列的宏任务。


## 浏览器
html5标准 （各浏览器有自己的实现）

执行script脚本
同步任务放到执行栈执行，异步任务中宏任务被发送给浏览器的webapi（别的线程），完成后回调函数放到宏队列，微任务放到微任务队列。
当脚本执行完毕，首先检查微任务队列是否有任务，有就执行，当微任务队列所有任务执行完毕，检查宏任务队列是否有任务，有任务就取出放到执行栈执行，执行完毕然后检查微任务队列是否有任务。
每次从宏任务队列中取出一个任务执行，执行完毕后执行微任务队列中的所有任务后再次检查宏队列中是否有任务并执行。

一个宏队列
一个微队列

## ref

https://segmentfault.com/a/1190000016278115