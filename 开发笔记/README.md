# 开发笔记

## webkit
WebKit 是一个开源的浏览器引擎，与之相对应的引擎有Gecko（Mozilla Firefox 等使用）和Trident（也称MSHTML，IE 使用）。

## Three key tech in responsive design
* flexible grid layout
* flexible image
* meida queries

## advantages
* work load
* time

## 微信
* 微信采用的是X5内核，与qq浏览器一样

## media query

### css2中
* media ＝ "print"
* media = "screen"

### css3
* @meida all and A and B ...
* not/and/only/or
* , = or
* only: 兼容旧浏览器
```HTML
旧浏览器中，只会解释成，
media ＝ "only"
```
#### attribute
* width
* heigth
* orientation
* color
* device-width
* device-height
* max- / min -

### view port视口
* 与device screen不一样
* 布局视口: 先用较大的分辨率将网页加载，缩放不改变布局视口
* 可视视口: 在moblie上呈现出来的大小，用户的行为自行修改
* 理想视口: 在一个设备上最佳尺寸。
```HTML
<meta name = "viewport" content = "width = device-width"/>
这句话表明，网页布局将以理想视口进行布局,可以不通过缩放进行展示web
```
* 应用实例
```HTML
百度中：
<meta name = "viewport" content = "width = device-width,
minimum-scale = 1.0,
maximun-scale = 1.0,
user-scalable = no"/>
讲显示比例设置成1，禁用了用户的缩放功能。
```

## princeple of responsive design
* progeressive enhancement 渐进增强
* graceful degradation 优雅降级
* 断点的选择: ex. 0 - 480 / 481 - 800 / 801 - ?