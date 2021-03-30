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

## Use Bracket Notation to Find the Nth-to-Last Character in a String

    var lastName = "Lovelace";
    var lastLetterOfLastName = lastName[lastName.length-2];

## Word Blanks

    a = b+' '+c+' '+d;

## Store Multiple Values in one Variable using JavaScript Arrays

    l = ["string",12];

## Nest one Array within Another Array

    var myArray = [["Bulls", 23], ["White Sox", 45]];

## Access Array Data with Indexes

    // Setup
    var myArray = [50,60,70];
    // Only change code below this line
    var myData = myArray[0];

## Modify Array Data With Indexes

    // Setup
    var myArray = [18,64,99];

    // Only change code below this line
    myArray[0] = 45;

## Access Multi-Dimensional Arrays With Indexes

    // Setup
    var myArray = [[1,2,3], [4,5,6], [7,8,9], [[10,11,12], 13, 14]];

    // Only change code below this line
    var myData = myArray[2][1];

## Manipulate Arrays With push()

    // Setup
    var myArray = [["John", 23], ["cat", 2]];

    // Only change code below this line
    myArray.push(["dog", 3])

## Manipulate Arrays With pop()

.pop() is used to pop a value off of the end of an array.

.pop() removes the last element from an array and returns that element.

    // Setup
    var myArray = [["John", 23], ["cat", 2]];

    // Only change code below this line
    var removedFromMyArray = myArray.pop();

## Manipulate Arrays With shift()

it removes the first element instead of the last.

    // Setup
    var myArray = [["John", 23], ["dog", 3]];

    // Only change code below this line
    var removedFromMyArray = myArray.shift();

## Manipulate Arrays With unshift()

unshift elements to the beginning of an array i.e. add elements in front of the array.

.unshift() works exactly like .push(), but instead of adding the element at the end of the array, unshift() adds the element at the beginning of the array.

push()将新数据加到后面,unshift加到前面

    // Setup
    var myArray = [["John", 23], ["dog", 3]];
    myArray.shift();

    // Only change code below this line
    myArray.unshift(["Paul",35]);

## Shopping List

    var myList = [["Chocolate Bar", 15],["Chocolate Bar", 15],["Chocolate Bar", 15],["Chocolate Bar", 15],["Chocolate Bar", 15]];

## Write Reusable JavaScript with Functions

    function reusableFunction () {
    console.log("Hi World");
    }

    reusableFunction();

## Passing Values to Functions with Arguments

    function functionWithArgs(param1, param2) {
    console.log(param1+param2);
    }

    functionWithArgs(1,2);

## Global Scope and Functions

// Declare the myGlobal variable below this line
var myGlobal = 10;

function fun1() {
  // Assign 5 to oopsGlobal Here
  oopsGlobal = 5;
}

// Only change code above this line

    function fun2() {
    var output = "";
    if (typeof myGlobal != "undefined") {
        output += "myGlobal: " + myGlobal;
    }
    if (typeof oopsGlobal != "undefined") {
        output += " oopsGlobal: " + oopsGlobal;
    }
    console.log(output);
    }

Variables which are used without the var keyword are automatically created in the global scope.

声明变量时即使是在函数内部,如果不用var的话也会是全局变量

## Local Scope and Functions

    function myLocalScope() {

    // Only change code below this line
    var myVar = "foo";
    console.log('inside myLocalScope', myVar);
    }
    myLocalScope();

    // Run and check the console
    // myVar is not defined outside of myLocalScope
    console.log('outside myLocalScope', myVar);

## Global vs. Local Scope in Functions

It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

本地变量、全局变量同时存在时，本地变量优先

    // Setup
    var outerWear = "T-Shirt";

    function myOutfit() {
    // Only change code below this line
    var outerWear = "sweater";
    // Only change code above this line
    return outerWear;
    }

    myOutfit();

## Return a Value from a Function with Return

    function timesFive(num) {
    return num * 5;
    }
    var answer = timesFive(5);

## Understanding Undefined Value returned from a Function

函数内部不使用return函数返回值的时候，会返回undefined值。

    var sum = 0;
    function addSum(num) {
    sum = sum + num;
    }
    addSum(3);

addSum is a function without a return statement. The function will change the global sum variable but the returned value of the function is undefined.

addSum函数改变全局变量sum的值，因为前面没有用var声明

    // Setup
    var sum = 0;

    function addThree() {
    sum = sum + 3;
    }

    // Only change code below this line
    function addFive() {
    sum = sum + 5;
    }
    // Only change code above this line

    addThree();
    addFive();

## Assignment with a Returned Value

    // Setup
    var processed = 0;

    function processArg(num) {
    return (num + 3) / 5;
    }

    // Only change code below this line
    var processed = processArg(7);

## Stand in Line

Write a function nextInLine which takes an array (arr) and a number (item) as arguments.

Add the number to the end of the array, then remove the first element of the array.

    function nextInLine(arr, item) {
    // Only change code below this line
    //这里要先加item再将arr第一个值传给item，反过来不行
    arr.push(item);
    item = arr.shift();

    return item;
    // Only change code above this line
    

    }

    // Setup
    var testArr = [1,2,3,4,5];

    // Display code
    console.log("Before: " + JSON.stringify(testArr));
    console.log(nextInLine(testArr, 6));
    console.log("After: " + JSON.stringify(testArr));

## Understanding Boolean Values

    function welcomeToBooleans() {

    // Only change code below this line

    return true; // Change this line

    // Only change code above this line
    }

They are basically little on-off switches, where true is on and false is off. These two states are mutually exclusive.

## Use Conditional Logic with If Statements

    function trueOrFalse(wasThatTrue) {
    // Only change code below this line
    if (wasThatTrue) {
        return "Yes, that was true";
    }
    return "No, that was false";


    // Only change code above this line

    }

## Comparison with the Equality Operator

In order for JavaScript to compare two different data types (for example, numbers and strings), it must convert one type to another. This is known as Type Coercion. Once it does, however, it can compare terms as follows:

1   ==  1
1   ==  2
1   == '1'
"3" ==  3

In order, these expressions would evaluate to true, false, true, and true.

JS在进行不同数据类型比较时，会进行类型的转换

    // Setup
    function testEqual(val) {
    if (val == 12) { // Change this line
        return "Equal";
    }
    return "Not Equal";
    }

    testEqual(10);

## Comparison with the Strict Equality Operator

Strict equality (===) is the counterpart to the equality operator (==). However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.

使用===时数据类型不会转换

3 ===  3
3 === '3'

These conditions would return true and false respectively.

In the second example, 3 is a Number type and '3' is a String type.

    // Setup
    function testStrict(val) {
    if (val===7) { // Change this line
        return "Equal";
    }
    return "Not Equal";
    }

    testStrict(10);

## Practice comparing different values

Note: In JavaScript, you can determine the type of a variable or a value with the typeof operator, as follows:

typeof 3

typeof '3'

typeof 3 returns the string number, and typeof '3' returns the string string.

JS中可以使用typeof  判定数据类型

    // Setup
    function compareEquality(a, b) {
    if (a === b) { // Change this line
        return "Equal";
    }
    return "Not Equal";
    }

    compareEquality(10, "10");

## Comparison with the Inequality Operator


