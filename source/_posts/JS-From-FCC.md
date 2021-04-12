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

    // Setup
    function testNotEqual(val) {
    if (val!=99) { // Change this line
        return "Not Equal";
    }
    return "Equal";
    }

    testNotEqual(10);

## Comparison with the Strict Inequality Operator

    // Setup
    function testStrictNotEqual(val) {
    if (val!==17) { // Change this line
        return "Not Equal";
    }
    return "Equal";
    }

    testStrictNotEqual(10);

## Comparison with the Greater Than Operator

    function testGreaterThan(val) {
    if (val>100) {  // Change this line
        return "Over 100";
    }

    if (val>10) {  // Change this line
        return "Over 10";
    }

    return "10 or Under";
    }

    testGreaterThan(10);

## Comparison with the Greater Than Or Equal To Operator

    function testGreaterOrEqual(val) {
    if (val>=20) {  // Change this line
        return "20 or Over";
    }

    if (val>=10) {  // Change this line
        return "10 or Over";
    }

    return "Less than 10";
    }

    testGreaterOrEqual(10);

## Comparison with the Less Than Operator

    function testLessThan(val) {
    if (val<25) {  // Change this line
        return "Under 25";
    }

    if (val<55) {  // Change this line
        return "Under 55";
    }

    return "55 or Over";
    }

    testLessThan(10);

## Comparison with the Less Than Or Equal To Operator

    function testLessOrEqual(val) {
    if (val<=12) {  // Change this line
        return "Smaller Than or Equal to 12";
    }

    if (val<=24) {  // Change this line
        return "Smaller Than or Equal to 24";
    }

    return "More Than 24";
    }

    testLessOrEqual(10);

## Comparisons with the Logical And Operator

    function testLogicalAnd(val) {
    // Only change code below this line

    if (val>=25 && val<=50) {
        return "Yes";
        }

    // Only change code above this line
    return "No";
    }

    testLogicalAnd(10);

## Comparisons with the Logical Or Operator

    function testLogicalOr(val) {
    // Only change code below this line

    if (val<10 || val>20) {
        return "Outside";
    }

    // Only change code above this line
    return "Inside";
    }

    testLogicalOr(15);

## Introducing Else Statements

    function testElse(val) {
    var result = "";
    // Only change code below this line

    if (val > 5) {
        result = "Bigger than 5";
    }

    else {
        result = "5 or Smaller";
    }

    // Only change code above this line
    return result;
    }

    testElse(4);

## Introducing Else If Statements

    function testElseIf(val) {
    if (val > 10) {
        return "Greater than 10";
    }

    else if (val < 5) {
        return "Smaller than 5";
    }
    else{
        return "Between 5 and 10";
    }
    }

    testElseIf(7);

## Logical Order in If Else Statements

    function orderMyLogic(val) {
    if (val < 5) {
        return "Less than 5";
    } else if (val < 10) {
        return "Less than 10";
    } else {
        return "Greater than or equal to 10";
    }
    }

    orderMyLogic(7);

## Chaining If Else Statements

    function testSize(num) {
    // Only change code below this line
    if (num < 5) {
        return 'Tiny';
    } else if (num < 10) {
        return 'Small';
    } else if (num < 15) {
        return 'Medium';
    } else if (num < 20) {
        return 'Large';
    } else {
        return 'Huge';
    }

    // Only change code above this line
    }

    testSize(7);

## Golf Code

    var names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];
    function golfScore(par, strokes) {
    // Only change code below this line
    if (strokes===1) {
        return names[0];
    }else if(strokes <= par - 2	) {
        return names[1];
    }else if(strokes === par - 1	) {
        return names[2];
        }else if(strokes === par) {
        return names[3];
        }else if(strokes === par + 1) {
        return names[4];
        }else if(strokes === par + 2) {
        return names[5];
        }else if (strokes>= par + 3){
        return names[6];
        }

    // Only change code above this line
    }

    golfScore(5, 4);

## Selecting from Many Options with Switch Statements

    function caseInSwitch(val) {
    var answer = "";
    // Only change code below this line


    switch(val) {
        case 1:
        console.log("alpha");
        answer = 'alpha';
        break;
        case 2:
        console.log("beta");
        answer = 'beta';
        break;
        case 3:
        console.log("gamma");
        answer = 'gamma';
        break;
        case 4:
        console.log("delta");
        answer = 'delta';
        break;
    }


    // Only change code above this line
    return answer;
    }

    caseInSwitch(1);

## Adding a Default Option in Switch Statements

    function switchOfStuff(val) {
    var answer = "";
    // Only change code below this line
    switch (val) {
        case 'a':
        answer = "apple";
        break;
        case 'b':
        answer = "bird";
        break;
        case 'c':
        answer = "cat";
        break;

        default:
        answer = "stuff";
        break;
    }


    // Only change code above this line
    return answer;
    }

    switchOfStuff(1);

## Multiple Identical Options in Switch Statements

    function sequentialSizes(val) {
    var answer = "";
    // Only change code below this line
    switch(val) {
        case 1:
        case 2:
        case 3:
        answer = "Low";
        break;
        case 4:
        case 5:
        case 6:
        answer = "Mid";
        break;
        case 7:
        case 8:
        case 9:
        answer = "High";
        break;
    }


    // Only change code above this line
    return answer;
    }

    sequentialSizes(1);

## Replacing If Else Chains with Switch

    function chainToSwitch(val) {
    var answer = "";

    switch(val) {
        case "bob":
        answer = "Marley";
        break;
        case 42:
        answer = "The Answer";
        break;
        case 1:
        answer = "There is no #1";
        break;
        case 99:
        answer = "Missed me by this much!";
        break;
        case 7:
        answer = "Ate Nine";
        break;
    }

    // Only change code above this line
    return answer;
    }

    chainToSwitch(7);

### 疑问：break；有什么作用

## Returning Boolean Values from Functions

Sometimes people use an if/else statement to do a comparison, like this:

function isEqual(a,b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}

But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:

function isEqual(a,b) {
  return a === b;
}

    function isLess(a, b) {
    // Only change code below this line

        return a < b;

    // Only change code above this line
    }

    isLess(10, 15);

## Return Early Pattern for Functions

When a return statement is reached, the execution of the current function stops and control returns to the calling location.

Example

function myFun() {
  console.log("Hello");
  return "World";
  console.log("byebye")
}
myFun();

The above will display the string Hello in the console, and return the string World. The string byebye will never display in the console, because the function exits at the return statement.

    // Setup
    function abTest(a, b) {
    // Only change code below this line
    if (a<0 || b<0){
        return undefined;
    }

    // Only change code above this line

    return Math.round(Math.pow(Math.sqrt(a) + Math.sqrt(b), 2));
    }

    abTest(2,2);

## Counting Cards

二十一点

    var count = 0;

    function cc(card) {
    // Only change code below this line
      switch(card){
        case 2:
        case 3:
        case 4:
        case 5:
        case 6:
          count+=1;
          break;

        case 7:
        case 8:
        case 9:
          count+=0;
        break;

        case 10:
        case 'J':
        case 'Q':
        case 'K':
        case 'A':
         count -=1;
          break;
       
      }
      //根据count结果进行判断
      if (count>0){  
         return count +" Bet";
      }else if(count<=0){
        return count +" Hold";
      }

    // Only change code above this line
    }

    cc(2); cc(3); cc(7); cc('K'); cc('A');

## Build JavaScript Objects

    var myDog = {
    // Only change code below this line
    "name": "Whiskers",
    "legs": 4,
    "tails": 1,
    "friends": ["Water", "Dogs"]

    // Only change code above this line
    };

## Accessing Object Properties with Dot Notation

    // Setup
    var testObj = {
    "hat": "ballcap",
    "shirt": "jersey",
    "shoes": "cleats"
    };

    // Only change code below this line

    var hatValue = testObj.hat;      // Change this line
    var shirtValue = testObj.shirt;    // Change this line

## Accessing Object Properties with Bracket Notation

当属性有空格的时候,需要使用中括号调取,属性也需要用引号引起来(好像本来就需要引起来)

    // Setup
    var testObj = {
    "an entree": "hamburger",
    "my side": "veggies",
    "the drink": "water"
    };

    // Only change code below this line

    var entreeValue = testObj["an entree"];   // Change this line
    var drinkValue = testObj["the drink"];    // Change this line

## Accessing Object Properties with Variables

    // Setup
    var testObj = {
    12: "Namath",
    16: "Montana",
    19: "Unitas"
    };

    // Only change code below this line

    var playerNumber = 16;       // Change this line
    var player = testObj[playerNumber];   // Change this line

## Updating Object Properties

改变属性值的两种方法

    // Setup
    var myDog = {
    "name": "Coder",
    "legs": 4,
    "tails": 1,
    "friends": ["freeCodeCamp Campers"]
    };

    // Only change code below this line
    myDog.name = "Happy Coder";
    myDog["name"] = "Happy Coder";

## Add New Properties to a JavaScript Object

    // Setup
    var myDog = {
    "name": "Happy Coder",
    "legs": 4,
    "tails": 1,
    "friends": ["freeCodeCamp Campers"]
    };

    // Only change code below this line
    myDog.bark = "woof";
    myDog["bark"] = "woof";

## Delete Properties from a JavaScript Object

    // Setup
    var myDog = {
    "name": "Happy Coder",
    "legs": 4,
    "tails": 1,
    "friends": ["freeCodeCamp Campers"],
    "bark": "woof"
    };

    // Only change code below this line

    delete myDog.tails;

## Using Objects for Lookups

更改前

    // Setup
    function phoneticLookup(val) {
    var result = "";

    // Only change code below this line
    switch(val) {
        case "alpha":
        result = "Adams";
        break;
        case "bravo":
        result = "Boston";
        break;
        case "charlie":
        result = "Chicago";
        break;
        case "delta":
        result = "Denver";
        break;
        case "echo":
        result = "Easy";
        break;
        case "foxtrot":
        result = "Frank";
    }

    // Only change code above this line
    return result;
    }

    phoneticLookup("charlie");

更改后

    // Setup
    function phoneticLookup(val) {
    var result = "";

    // Only change code below this line
        var lookup = {
        "alpha": "Adams",
        "bravo": "Boston",
        "charlie": "Chicago",
        "delta": "Denver",
        "echo": "Easy",
        "foxtrot": "Frank"
        };
        //这里用点通不过检验,不知道原因
        result = lookup[val];
    // Only change code above this line
    return result;
    }

    phoneticLookup("charlie");

## Testing Objects for Properties

用.hasOwnProperty(propname)检验函数是否有当前属性,返回值为true或false

    function checkObj(obj, checkProp) {
    // Only change code below this line
    if (obj.hasOwnProperty(checkProp)){
        return obj[checkProp];
    }else{
        return "Not Found";
    }
    // Only change code above this line
    }

## Manipulating Complex Objects

    //这是一个array,里面包含了一个object

    var ourMusic = [
    {
        "artist": "Daft Punk",
        "title": "Homework",
        "release_year": 1997,
        "formats": [ 
        "CD", 
        "Cassette", 
        "LP"
        ],
        "gold": true
    }
    ];

    var myMusic = [
    {
        "artist": "Billy Joel",
        "title": "Piano Man",
        "release_year": 1973,
        "formats": [
        "CD",
        "8T",
        "LP"
        ],
        "gold": true
    },
    // Add a record here
    {
        "artist": "Billy Joel",
        "title": "Piano Man",
        "release_year": 1973,
        "formats": [
        "CD",
        "8T",
        "LP"
        ],
        "gold": true
    }
    ];

## Accessing Nested Objects

    // Setup
    var myStorage = {
    "car": {
        "inside": {
        "glove box": "maps",
        "passenger seat": "crumbs"
        },
        "outside": {
        "trunk": "jack"
        }
    }
    };

// 这里不能用myStorage.car["inside"]["glove box"]

    var gloveBoxContents = myStorage.car.inside["glove box"]; // Change this line

## Accessing Nested Arrays

    // Setup
    var myPlants = [
    {
        type: "flowers",
        list: [
        "rose",
        "tulip",
        "dandelion"
        ]
    },
    {
        type: "trees",
        list: [
        "fir",
        "pine",
        "birch"
        ]
    }
    ];

    // Only change code below this line

    var secondTree = myPlants[1].list[1]; // Change this line

## Record Collection*

[CSDN解决方案](https://blog.csdn.net/weixin_30391339/article/details/98212760)

注：**复制粘贴之后仍然未能通过**

### 失败案

    // Setup
    var collection = {
    2548: {
        albumTitle: 'Slippery When Wet',
        artist: 'Bon Jovi',
        tracks: ['Let It Rock', 'You Give Love a Bad Name']
    },
    2468: {
        albumTitle: '1999',
        artist: 'Prince',
        tracks: ['1999', 'Little Red Corvette']
    },
    1245: {
        artist: 'Robert Palmer',
        tracks: []
    },
    5439: {
        albumTitle: 'ABBA Gold'
    }
    };

    // Only change code below this line
    function updateRecords(object, id, prop, value) {
    //有tracks时
    if (object['tracks']){
        object[id][tracks] += prop;
    }else{
        //没有tracks 但输入tracks时 添加
        if (prop == 'tracks'){
        object[id][tracks] = value;
        }else{
        //没有tracks 输入不是tracks时 若数值为空则删除属性
        if(value==""){
            delete object[id][prop];
            //若有数值则添加
        }else{
            object[id][prop] = value;
        }
        }

    }
    return object;
    }

    updateRecords(collection, 5439, 'artist', 'ABBA');

### 总结

搞清楚前后顺序很重要，'//没有tracks 输入不是tracks时 若数值为空则删除属性' 删除属性应该是大前提，把这个方法放到条件里面后就不能对这个条件之外的情况下起作用了。

## while 循环

通过一个 while 循环，把从 5 到 0（包括 5 和 0） 的值添加到 myArray 中。

```JavaScript
// 设置
var myArray = [];


// 只修改这一行下面的代码
var i = 5;
while(i >= 0) {
  myArray.push(i);
  i--;
}
```

## for 循环

```JavaScript
// 设置
var myArray = [];

// 只修改这一行下面的代码
for (var i = 1; i <= 5; i++) {
  myArray.push(i)
}
```

## 使用 For 循环遍历数组的奇数

```JavaScript
// 设置
var myArray = [];

// 只修改这一行下面的代码

for (var i = 1; i <= 9; i+= 2) {
  myArray.push(i)
}
```

## 使用 For 循环反向遍历数组

```JavaScript
// 设置
var myArray = [];

// 只修改这一行下面的代码
for (var i = 9; i > 0; i -= 2) {
  myArray.push(i);
}
```

## 使用 For 循环遍历数组

```JavaScript
// 设置
var myArr = [ 2, 3, 4, 5, 6];

// 只修改这一行下面的代码
var total = 0;
for (var i = 0; i < myArr.length; i++) {
   console.log(myArr[i]);
   total = total + myArr[i];
}
```

## 循环嵌套

```JavaScript
function multiplyAll(arr) {
  var product = 1;
  // 只修改这一行下面的代码
  for (var i=0; i < arr.length; i++) {
    for (var j=0; j < arr[i].length; j++) {
      console.log(arr[i][j]);
      product = product * arr[i][j];
  }
}
  // 只修改这一行上面的代码
  return product;
}

multiplyAll([[1,2],[3,4],[5,6,7]]);
```

## do...while 循环

```JavaScript
// 设置
var myArray = [];
var i = 10;

// 只修改这一行下面的代码
var myArray = [];
var i = 10;
do {
  myArray.push(i);
  i++;
} while (i < 11);
```

## 使用递归代替循环*

暂时搁置

## 资料查找*

[流程图](https://www.processon.com/view/link/6073e31463768912ae52751f)

初案

```javascript
// 设置
var contacts = [
    {
        "firstName": "Akira",
        "lastName": "Laine",
        "number": "0543236543",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstName": "Harry",
        "lastName": "Potter",
        "number": "0994372684",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstName": "Sherlock",
        "lastName": "Holmes",
        "number": "0487345643",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstName": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["JavaScript", "Gaming", "Foxes"]
    }
];


function lookUpProfile(name, prop){
// 设置
var contacts = [
    {
        "firstName": "Akira",
        "lastName": "Laine",
        "number": "0543236543",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstName": "Harry",
        "lastName": "Potter",
        "number": "0994372684",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstName": "Sherlock",
        "lastName": "Holmes",
        "number": "0487345643",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstName": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["JavaScript", "Gaming", "Foxes"]
    }
];


function lookUpProfile(name, prop){
// 只修改这一行下面的代码
    names = [];
    for (i=0;i<contacts.length;i++) {
        names.push(coantacs[i]["firstName"]);
    }
    for (var realname in names) {
        if (realname == name){
            return contacts[i][prop];
        }
    }else {
        return "No such contact";
    }
// 只修改这一行上面的代码

lookUpProfile("Akira", "likes");
```

## 