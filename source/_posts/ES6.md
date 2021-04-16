---
title: ES6
date: 2021-04-16 06:21:06
tags:
---
## 探索 var 和 let 关键字之间的差异

```Javascript
let catName;
let quote;
function catTalk() {
  "use strict";

  catName = "Oliver";
  quote = catName + " says Meow!";

}
catTalk();
```

## 比较 var 和 let 关键字的作用域

```Javascript
function checkScope() {
  let i = 'function scope';
  if (true) {
    let i = 'block scope';
    console.log('Block scope i is: ', i);
  }
  console.log('Function scope i is: ', i);
  return i;
}
```

## 用 const 关键字声明只读变量

function printManyTimes(str) {

```Javascript
  // 只修改这一行下面的代码

  const SENTENCE = str + " is cool!";
  for (let i = 0; i < str.length; i+=2) {
    console.log(SENTENCE);
  }

  // 只修改这一行上面的代码

}
printManyTimes("freeCodeCamp");
```

## 