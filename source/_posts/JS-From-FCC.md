---
title: JS From FCC
date: 2021-03-29 08:18:53
tags:
---

## 注释

一行//

多行/**/

## 变量

数据类型：undefined, null, boolean, string, symbol, bigint, number, object

var let const var是es5的语法 es6时代建议用let

## 赋值

    a=3

## 将变量的值赋给其它变量

    b=a

## 用赋值初始化变量

    var a=9
    let a=9
    const a=9

## 理解未初始化变量

声明变量不初始化，则其值为undefined，不可参与数字计算，不能和其它字符串融合

## JS区分变量大小写

## 数字运算+-*/

## Increment a Number with JavaScript

使用++运算符

i++; 等价于 i = i + 1;

## Decrement a Number with JavaScript

使用--运算符

i--; 等价于 i = i - 1;

## 用JS创造十进制变量

    var ourDecimal = 5.7;

## 用JS让两个十进制数字相乘

    var product = 2.0 * 2.5;

## 用JS让两个十进制数字相除

    var quotient = 0.0 / 2.0;

## 求余数

    var remainder = 11 % 3;

## Compound Assignment With Augmented Addition

    myVar = myVar + 5; 等价于 myVar += 5；

## Compound Assignment With Augmented Subtraction

    -=

## Compound Assignment With Augmented Multiplication

    *=

## Compound Assignment With Augmented Multiplication

    /=

## 声明字符串变量

    var myFirstName  = "your name";
    var myLastName   = "your name";

## 转义字符\

var myStr = "I am a \"double quoted\" string inside \"double quotes\".";

## Quoting Strings with Single Quotes

JS单引号双引号作用相同

可以通过单双复用避免使用转义字符

    var myStr = '<a href="http://www.example.com" target="_blank">Link</a>';

## Escape Sequences in Strings
         
|Code    |	Output         |
|  ----  | ----            |
|\'	     |  single quote   |
|\"	     |  double quote   |
|\\	     |  backslash      |
|\n	     |  newline        |
|\r	     |  carriage return|
|\t	     |  tab            |
|\b	     |  word boundary  |
|\f	     |  form feed      |

    var myStr= 'FirstLine\n\t\\SecondLine\nThirdLine'; // Change this line

## Concatenating Strings with Plus Operator

    'My name is Alan,' + ' I concatenate.'

## Concatenating Strings with the Plus Equals Operator

    +=
    var ourStr = "I come first. ";
    ourStr += "I come second.";

## 使用变量构造字符串

    var myName='aac';
    var myStr='My name is '+myName+' and I am well!';

## Appending Variables to Strings

    var someAdjective='normal.';
    var myStr = "Learning to code is ";
    myStr += someAdjective;

## 得到字符串长度

使用length属性得到字符串长度

    var lastNameLength = 0;
    var lastName = "Lovelace";

    lastNameLength = lastName.length;

## Use Bracket Notation to Find the First Character in a String

    firstLetterOfLastName = lastName[0]

## Understand String Immutability

字符串变量一经创造不能被改变(alter)

    var myStr = "Bob";
    myStr[0] = "J";

此时Bob不会变成Job

虽然字符串不能改变（alter），但是能够通过赋值方法改变（change）

## Use Bracket Notation to Find the Nth Character in a String

## Use Bracket Notation to Find the Last Character in a String

    var lastName = "Lovelace";
    var lastLetterOfLastName = lastName[lastName.length-1];



