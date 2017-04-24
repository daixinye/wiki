# 跨域方法小结

## 产生背景

为了防止跨站请求伪造（CSRF，Cross-site request forgery）攻击，浏览器引入了同源策略（SOP，Same-Origin Policy）来提高安全性。

同源策略指的是，只要在同一域名（domain或ip）、同一端口、同一协议下才能互相获取资源。

一个域名A的网页可以获取域名B的静态资源，但是不能发起AJAX（Asynchronous JavaScript and XML）请求。

## JS跨域

### JSONP

### document.domain

### window.name

### window.postMessage

## 服务端

### 反向代理

### CORS



