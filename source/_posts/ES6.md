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

## 改变一个用 const 声明的数组

对象（包括数组和函数）在使用 const 声明的时候依然是可变的。 使用 const 来声明只会保证变量不会被重新赋值。

```Javascript
const s = [5, 6, 7];
// 下面的赋值无效
s = [1, 2, 3];
// 改变单个数字有效
s[2] = 45;
console.log(s);
```

```Javascript
const s = [5, 7, 2];
function editInPlace() {
  // 只修改这一行下面的代码

  // 使用 s = [2, 5, 7] 将无效
  s[0] = 2;
  s[1] = 5;
  s[2] = 7;
  // 只修改这一行上面的代码
}
editInPlace();
```

## 防止对象改变

```Javascript
function freezeObj() {
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  // 只修改这一行下面的代码
  Object.freeze(MATH_CONSTANTS)

  // 只修改这一行上面的代码
  try {
    MATH_CONSTANTS.PI = 99;
  } catch(ex) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();
```

## 使用箭头函数编写简洁的匿名函数

语法:

```Javascript
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
```

```Javascript

const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```

```Javascript
const myFunc = () => "value";
```

```Javascript
const magic = () => new Date();
```

## 编写带参数的箭头函数

```Javascript
const myConcat = (arr1, arr2) => arr1.concat(arr2);

console.log(myConcat([1, 2], [3, 4, 5]));
```

## 设置函数的默认参数

```Javascript
// 只修改这一行下面的代码
const increment = (number, value=1) => number + value;
// 只修改这一行上面的代码
```

## 将 rest 操作符与函数参数一起使用

```Javascript
const sum = (...args) => {
  return args.reduce((a, b) => a + b, 0);
}
```

## 使用 spread 运算符展开数组项

