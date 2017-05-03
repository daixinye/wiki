# 基础操作小结

## Canvas 标签

```
<canvas id="canvas" width="400" height="400"></canvas>
```

## 坐标系

```
(0,0)                (x,0)
    ┏━━━━━━━━━━━━━━━━ 
    ┃
    ┃
    ┃
    ┃
    ┃
    ┃
    ┃
(0,y)
```

## 获取上下文

```
var canvas = document.querySelecotr('#canvas');
var ctx = canvas.getContext('2d');

```

## 画图片及保存图片

```
var img = new Image();
img.src = 'demo.jpg';
img.onload = function(){
    ctx.drawImage(img,0,0,ctx.width,ctx.height);
    var saveImg = ctx.toDataURL();
    window.open(saveImg);
}
```

## 画笔颜色

```
ctx.fillStyle = 'red';
ctx.strokeStyle = '#fff';
```

## 画矩形

```
ctx.fillRect(0,0,ctx.width,ctx.height); // 实心
ctx.strokeRect(0,0,ctx.width,ctx.height); // 空心
```

## 清除画布

```
ctx.clearRect(0,0,ctx.width,ctx.height);
```

## 路径

```
ctx.beginPath();
ctx.moveTo(0,0);
ctx.LineTo(50,50;
ctx.LineTo(0,50);
ctx.LineTo(0,0);
ctx.fill();
//ctx.stroke();
```

## 缩放、旋转、平移

```
ctx.scale(2,3);
ctx.rotate(90 * (Math.PI / 180));
ctx.translate(100,200);
```

## 保存和恢复画布状态

```
ctx.fillStyle = 'blue';
ctx.fillRect(0,0,20,20);
ctx.save();

ctx.fillStyle = 'red';
ctx.fillRect(20,20,20,20);

ctx.restore();
ctx.fillRect(40,40,20,20);
```

## 文本

注意：文本的坐标原点在左下角。

使用居中时，原点在文本中点下方。

```
ctx.font = '36px Impact';
ctx.lineWidth = 3;
ctx.textAligh = 'center';
ctx.fillStyle = '#fff';
ctx.fillText('Canvas', 0, 36);

ctx.strokeStyle = '#000';
ctx.strokeText('Canvas', 0 ,36);
```



