# Hybrid

## 什么是Hybrid

### Hybrid 出现的历史原因

* 2013年起移动互联网的兴起导致App开发的需求日益高涨。
* 2014年 H5 的发布，使得 Web 能够实现更多功能。
* 在产品需要快速迭代、抢占市场的大背景下，开发 iOS 和 Android 原生应用的时间成本和劳动成本都非常高。
* 随着 iOS 和 Android 两大阵营对 H5 的支持日益完善，H5 足以实现大多数的需求。
* 为了利用 Web 应用低成本、高效率、跨成本等诸多优点，出现了使用 Web 和 Native 混合进行开发的模式。

### Hybrid 的分类

App 应用从实现机制上来区分，主要分为三类：

1. Native 应用：使用原生语言的应用，能够调用所有底层接口，交互体验最好。
2. Web App 应用：使用纯 Web 开发的应用，通过浏览器访问，~~只能调用部分系统接口~~，交互体验最差。
3. Hybrid 应用：
   1. 以 WebView 作为用户界面层，以 JavaScript 为基本逻辑通过与中间件通讯、访问底层 API ，进行应用开发。
   2. 使用非官方语言的工具，打包成原生应用的方式开发。
   3. 基于原生应用的架构，在部分功能中嵌入 WebView 。WebView 负责对界面的渲染，同时也可以访问底层的 API 以实现特定的功能。
   4. 通过 JavaScript 引擎管理和渲染 native 视图，将 JavaScript 代码渲染成原生组件，调用原生 API 与用户进行交互。（ReactNative、Weex）

### Hybrid 的优势

* 开发效率高
* 开发成本低
* 跨平台
* 快速迭代，无需发布版本即可修复Bug

总结来说，Hybrid 是既保持了对原生API的完整掌控，同时可以在特定功能下节省跨平台开发成本、提升效率。

### Hybrid 的劣势

* 容易造成性能问题，不适用于依赖原生 API 和游戏开发的需求。
* 永远保持最新带来的低版本机型的适配问题，包括调用底层 API 和对 H5 的支持方面。
* 需要实现 Native 与 H5 之间的通信机制
* 交互体验不如原生页面，需要尽可能仿制原生应用的体验

总结来说，Web 只能替代、辅助一部分功能，无法取代原生开发的主导地位。

## Hybrid 实现

### Native 与 前端之间的关系

### Hybrid 实现常见的问题

## 小结

## 参考

[http://www.cnblogs.com/yexiaochai/p/4921635.html](http://www.cnblogs.com/yexiaochai/p/4921635.html)

[http://ued.ctrip.com/blog/translation-hybrid-mobile-application-provide-native-web-technology-experience.html](http://ued.ctrip.com/blog/translation-hybrid-mobile-application-provide-native-web-technology-experience.html)

