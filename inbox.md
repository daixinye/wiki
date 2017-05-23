## 多行表达式前（后）需要加分号

```
;(function(foo){
    //do something
})(foo)
```

不加分号会被当做函数调用进行处理

```
(funcion(foo){
    // do something
})(foo)

(function(bar){
    // do something
})(bar)

// 等同于

func1(foo)(func2)(bar);
```

多行的表达式，尤其是圆括号括起来的匿名函数，一定要在最后加上分号。

```
(function(foo)){
    // do something    
}(foo);
```

在模块开发当中最好在最前面也加上分号，以防止别的模块开发者不写分号。

```
;(function(foo){})(foo){
    // do something
}(foo);
```

## iOS 9.2 版本以上CSS transform 动画显示不正常的问题

当一个元素盒子完全在屏幕外时，元素的 transform 动画不正常。

可以通过在动画开始时强制浏览器进行重排的方式 hack 这个问题。

比如在动画的最后加上margin-top: 1px; 之类（引起浏览器重排）的。



