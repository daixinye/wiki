# 作用域、闭包、this

## this

```
var fn = function(one, two){
    console.log(one, two);
}
var r={}, g={}, b={}, y={};

r.method = fn;

r.method(); // this=r, one=undefined, two=undefined
fn(g,b);  // Global, g, b
fn.call(r, g, b); // r, g, b
r.method.call(y, g, b); // y, g, b

setTimeout(fn, 1000); // this的值不确定，undefined, undefined
setTimeout(r.method, 1000); // this的值不确定（跟r无关），undefined,undefined
setTimeout(function(){
    r.method(); // r, undefined, undefined 
    },1000); 

console.log(one); // Referrence Error
console.log(this); // Global
```



