# 跨域方法小结

## 产生背景

为了防止跨站请求伪造（CSRF，Cross-site request forgery）攻击，浏览器引入了同源策略（SOP，Same-Origin Policy）来提高安全性。

同源策略指的是，只要在同一域名（domain或ip）、同一端口、同一协议下才能互相获取资源。

一个域名A的网页可以获取域名B的静态资源（如CSS文件、图片等），但是不能直接发起AJAX（Asynchronous JavaScript and XML）请求。

## JS跨域

### JSONP

原理：通过动态插入JS脚本的方式来实现跨域。

该方法适合跨域获取JSON类型的数据。缺点是只支持GET方式。

### document.domain

原理：通过修改两个同一一级域名不同二级域名页面（如example.com与a.example）的`document.domain`来实现跨域。`document.domain`只能修改为自身或者高一级的父域名。

该方法适用于同父域名下的跨域问题。

### window.name

原理：window对象的name属性有一个特征，即在一个窗口（window）的生命周期下，窗口载入的所有页面都共享一个`window.name`，故我们可以通过插入一个外部页面的iframe，通过JS修改`window.name`，再将`window.location`改为同源的页面，来访问`window.name`的值进行跨域。

该方法的缺点是需要额外的同源页面，同时不同浏览器对window.name的大小也有一定的限制。

### window.postMessage

原理：`window.postMessage(message, targetOrigin)`，是HTML5新引进的特性，可以用来向同源或者不同源的window对象发送消息。插入一个iframe，获取`iframe.contentWindow`，然后使用`postMessage`发送消息，在iframe预先设置`onmessage`的处理函数，即可获取跨域的数据。

该方法适用于处理多页面通信以及与iframe之间的消息传递。

## 服务端

### 反向代理

原理：通过将外部资源映射成内部的地址，再通过代理服务器去获取真实的资源，然后返回给浏览器，避免在浏览器端进行跨域操作。

> 反向代理，代理的是服务器，客户端只需要知道代理服务器上的资源URL地址即可，而不关心资源的真正URL。例如负载均衡就会用到反向代理。
>
> 正向代理，则是代理客户端，客户端需要知道资源的实际URL，通过告诉代理服务器真正的资源URL所在的位置，让代理服务器去获取后返还给客户端。例如翻墙工具就是正向代理。

### CORS

浏览器发送一个带有`Origin`首部字段的HTTP请求，表明请求的来源。服务器的响应头中包含`Access-Control-Allow-Origin`表明允许哪些域名的请求。一旦不匹配则拒绝访问。通常设置为`Access-Control-Allow-Origin: *`可以允许任意域名跨域请求该服务器上的资源。

