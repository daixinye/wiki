# 事件监听

## 常见事件类型

* Form events: 如 submit
* Focus events: 如 blur, focus, change
* Input devices events: 如 keyup, keypress, mouseover, mousemove, mouseleave
* View events: 如 scroll, resize

## 事件监听三要素

* the target element to listen to，监听对象
* the event we want to react to，监听事件
* the actions to take in response，回调函数

## 基础示例

```
$('div.foo button').on('click',function(){
    $(this).remove();
})
```

## 更多用法

```
// 传递事件对象
$('div.foo button).on('click',function(event){
    $(event.target).remove(); // event.target 事件目标的页面元素
})
```

```
// 阻止默认行为
$('div.foo a).on('click',function(event){
    event.preventDefault();
    console.log('the link you clicked will not work');
})
```

### event

* event.keyCode，用来了解按下的是哪个键
* event.pageX, event.pageY，用来了解点击发生的坐标位置
* event.type，用来了解发生的事件

## 参考

[MDN: Events Catagory](https://developer.mozilla.org/en-US/docs/Web/Events#Categories)

[jQuery: Event Object](https://api.jquery.com/category/events/event-object/)

[jQuery: event.targer](https://api.jquery.com/event.target/)

[W3C: Dom Level-3 Event](https://www.w3.org/TR/DOM-Level-3-Events/)

