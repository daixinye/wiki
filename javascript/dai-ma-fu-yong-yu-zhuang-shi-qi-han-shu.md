# 代码复用与装饰器函数

## 代码复用的问题

```
var foo = {color:'red'};
var bar = {color:'green'};
```

这段代码中我们生成了两个属性相似的对象，每次生成一个类似的对象都需要重新写一遍代码。

## 装饰器函数

### 添加属性

```
// lib.js
var fn = function(obj,color){
    obj.color = color;
    return obj;
}

// app.js
var foo = fn({},'red');
var bar = fn({},'green');
```

我们可以通过一个装饰器函数，来解决生成类似对象的问题。

装饰器函数的作用，就是给某个已拥有某些功能的对象添加属性。这里我们传入了一个空的对象，通过fn函数来对这个空对象进行”装饰“（添加属性）。

### 添加方法

#### 浪费内存

```
// lib.js
var fn = function(obj,color){
    obj.color = color;
    obj.printColor = function(){
        console.log(this.color);
    }
    
    return obj;
}

// app.js
var foo = fn({},'red');
foo.printColor(); // red
var bar = fn({},'green');
bar.printColor(); // green
```

上述添加方法的方式，优点是具有良好的封装性，但是最大的问题是每次调用装饰器函数都会在内存中生成一个新的`printColor函数`。在对象比较多的情况下，就容易浪费内存。

#### 更多的缺点

```
// lib.js
var fn = function(obj,color){
    obj.color = color;
    obj.printColor = printColor;
    return obj;
}

var printColor = function(){
    console.log(this.printColor);
}

// app.js
var foo = fn({},'red');
foo.printColor(); // red
var bar = fn({},'green');
bar.printColor(); // green
```

上述添加方法的方式，尽管解决了内存占用的问题，但是失去了良好的封装性。

除此之外，如果添加的方法比较多，每次都需要在fn中对函数进行绑定，效率很低。

```
// lib.js
var fn = function(obj,color){
    obj.color = color;
    obj.method_1 = method_1;
    obj.method_2 = method_2;
    // ...
    obj.method_1000 = method_3;
    
    return obj;
}

var method_1 = function(){ //... };
var method_2 = function(){ //... };
// ...
var method_1000 = function(){ //... };
```

#### 把方法都装在一起

在把方法都装进`methods`中，通过遍历的方式可以把任意数量的方法绑定到`obj`上。

```
// lib.js
var fn = function(obj,color){
    obj.color = color;
    
    extend(obj,methods); // extend()代表把methods中的属性复制到obj中，注意它并不是原生的函数
    
    return obj;
}

var methods = {
    method_1:function(){ //... },
    method_2:function(){ //... },
    // ...
    method_1000:function(){ //... }
};
```

#### 借助Function对象的属性

`methods`与`fn`之间没有一个非常明显的联系，为此我们可以利用`Function对象`的属性来解决。

```
// lib.js
var fn = function(obj,color){
    obj.color = color;
    
    extend(obj, fn.methods);
    
    return obj;
}

fn.methods = {
    method_1:function(){ //... },
    method_2:function(){ //... },
    // ...
    method_1000:function(){ //... }
}
```



