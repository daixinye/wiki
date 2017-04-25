# jQuery基础操作小结

## 元素选择

### 获取元素

```
// $(selector)
$('div.foo');

// $(element)
$('div.foo').on('click',function(){
    $(this).slideUp();
})
```

遍历元素

```
// 父元素
$('div.foo').parent();

// 祖先元素
$('div.foo').parents();

// 子元素
$('div.foo').children();

// 后代元素
$('div.foo').find();

// 兄弟元素
$('div.foo').sibling();
```

## DOM操作

### 添加or删除class

```
$('div.foo').toggleClass('bar');
```

修改or获取属性

```
$('div.foo a').attr('href','#1');
$('div.foo a').attr('href'); // #1
```

修改or获取CSS

```
$('div.foo').css('font-size','20px');
$('div.foo').css('font-size'); // 20px
```

获取内容

```
$('div.foo').html(); // 完整的HTML代码
$('div.foo').text(); // 去掉HTML标签后的文本
$('div.foo input').val(); // 获取输入的值
```

移除

```
$('div.foo').remove();
```



