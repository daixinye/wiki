# 个人开发代码规范

主要针对JavaScript

## 写分号？

尽管JavaScript有ASI机制，但是其他主流语言都需要写分号。

为了“兼容”其他语言的编码习惯和良好的可读性，**规定写分号**。

## 事件相关命名？

事件名需加前缀 on，默认情况下采用驼峰命名法。如 onClick，onChange 等。

处理事件的函数需以 handler 结尾，如 clickHandler，changeHandler 等。

