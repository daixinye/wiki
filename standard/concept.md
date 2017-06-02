# 概念

## 语句与表达式

### 语句（statements）

* if 语句
* while 语句 / do-while 语句 / for 语句 / for-in 语句
* label 语句
* break 语句 / continue 语句
* with 语句
* continue 语句

语句，也叫**流控制语句，**通常使用一个或多个**关键字**来完成给定任务，是由分号分割的句子或命令。语句可以被理解为程序的一个**“行为”**，一个程序是由若干个**“行为”**组成的。

### 表达式（expressions）

表达式是由运算符构成，并运算产生结果的语法结构。表达式与语句不同，表达式会产生一个**值**，可以被放在任何一个需要赋值的地方。下面这些都是**表达式**：

* 3 + 1
* 3 + x
* myValue
* add\(1,2\)

### 表达式语句

如果在表达式后面加一个分号分隔符，这就被称为表达式语句，表明“只有表达式，而没有其他语法元素的语句”。

#### 匿名函数

```
function(){}; // Syntax Error
(function(){}); // 返回一个匿名函数
(function(){})(); // 立即调用返回匿名函数的运算结果
```

#### 非匿名函数

```
function foo() {}; // 非匿名函数表达式（函数声明），不能被立即调用
var bar = function foo(){}; // bar 能够在外部访问，foo 只能在函数内部访问（用于递归）
```

### 函数和方法的区别

函数 function ，一般用于面向过程开发。

方法 method，则是用于面向对象开发中的对象。

在 Java 中只有方法，C 中只有函数，而 C++ 取决于是不是在类中。

对于 JavaScript 来说，function 代表了一个由语句组成的代码块，用于完成特定的功能（面向过程）。method 则是 “对象的function”，即如果一个 function 通过 obj 点操作符来进行调用，那么这个 function 就可以被称作（对象的）方法。

参考：

[http://www.cnblogs.com/moltboy/archive/2013/04/24/3040450.html](http://www.cnblogs.com/moltboy/archive/2013/04/24/3040450.html)

