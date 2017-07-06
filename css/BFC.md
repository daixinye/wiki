# BFC

## 触发 BFC 的方法

### 1、float

float 属性不为 none 时，即如果一个元素是浮动元素，那么它就是一个 BFC 。

* float: left;
* float: right;

### 2、overflow

overflow 属性不为 visible 时，即 overflow 为auto、scroll、hidden 时会形成一个 BFC 。

* overflow: hidden;
* overflow: scroll;
* overflow: auto; 

### 3、display

display 属性为 table-cell、table-caption 或 inline-block 时也会触发 BFC。

* display: table-cell;
* display: table-caption;
* display: inline-block;

### 4、position

position 属性不为 relative 或 static 时，即 postion 为 absolute、fixed 时也会触发 BFC 。

* position: relative;
* position: fixed;

## BFC 的作用



