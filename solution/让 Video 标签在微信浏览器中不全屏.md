# 让 Video 标签在微信浏览器中不全屏
## 背景
\<video\> 在微信浏览器中，默认以全屏播放的方式打开，但是在某些场景下我们希望视频能以内联的方式进行播放。

## 解决方案
在微信浏览器中，添加 x5-video-player-type=“h5” 属性。在 iOS 下还需要添加 playsinline 和 webkit-playsinline=“true” 两个属性。
``
<video id="video" src="movie.mp4" playsinline webkit-playsinline="true" x5-video-player-type="h5"></video>
``
## 参考
[http://itakeo.com/blog/2016/07/07/videoinline/][1]
[http://itakeo.com/blog/2017/01/12/wxvideo/][2]
[https://x5.tencent.com/tbs/guide/video.html][3]

[1]:	http://itakeo.com/blog/2016/07/07/videoinline/
[2]:	http://itakeo.com/blog/2017/01/12/wxvideo/
[3]:	https://x5.tencent.com/tbs/guide/video.html