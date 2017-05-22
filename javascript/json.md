# JSON

## JSON.parse\(\)

> JSON.parse\( text\[, reviver\] \)

* text : 要被解析成 JavaScript 值的字符串

* reviver : 规定原始值如何被解析改造的函数

### reviver 函数

解析值本身以及它所包含的值，从里向外调用去调用 `reviver` 函数。属性名和属性值会作为参数传入 `reviver` 中，如果 `reviver` 返回 `undefined` ，那么当前属性就会从对象中删除；如果返回其他值，返回值就会作为当前属性新的属性值。

注意，遍历到顶层时，传入 `reviver` 函数的是空字符串和当前对象，即`{"" : 修改过的解析值 }`。这是个特例，需要特别注意。

所以 `reviver` 函数有基本两种种用法：

1、删除特定属性

```
var str = '{"a":1, "b":2}';

// 将属性值置为 undefined 删除属性
var json = JSON.parse(str,function(key, value){
    return key == 'a' ? undefined : value;
})

console.log(json); // {b:2}
```

2、修改特定属性的值

```
var str = '{"a":1, "b":2}';

var json = JSON.parse(str, function(key, value){
    return key == 'a' ? value * 2 : value;
})

console.log(json); // {a:2, b:4}
```

## JSON.stringify\(\)

> JSON.stringify value\[, replacer\[, space \]\] \)

* value : 要被转换成 JSON 字符串的值
* replacer : 规定如何转换和处理值的属性
* space : 指定缩进用的空白字符串

### replacer 参数

#### 传入函数

返回 `undefined` 代表不输出该属性；输出其他（包括 `null` ）都会替代原来的属性值输出。

```
function replacer(key, value) {
  if (typeof value === "string") {
    return undefined;
  }
  return value;
}

var foo = {foundation: "Mozilla", model: "box", week: 45, transport: "car", month: 7};
var jsonString = JSON.stringify(foo, replacer);

console.log(jsonString); // {"week":45,"month":7}
```

#### 传入数组

根据属性名指定哪些属性会被输出。

```
var foo = {foundation: "Mozilla", model: "box", week: 45, transport: "car", month: 7};
var jsonString = JSON.stringify(foo, ['week','model']);

console.log(jsonString); // {"week":45,"model":"box"}
```

#### 传入 `undefined` 或 `null`

输出所有的属性。

```
var foo = {foundation: "Mozilla", model: "box", week: 45, transport: "car", month: 7};
var jsonString = JSON.stringify(foo, null);

console.log(jsonString); // {"foundation":"Mozilla","model":"box","week":45,"transport":"car","month":7}
```

### space 参数

指定缩进用的空白字符串，用于美化输出。

如果参数是数字，就代表有多少空格，上限是10；

如果参数是字符串，则为该字符串的前10个字母；

如果参数没有提供，就意味着没有空格。

除此之外，也可以传入转义字符（ `\t` ）来用 tab 进行缩进。

## 参考

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/JSON/parse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/JSON/stringify](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)

