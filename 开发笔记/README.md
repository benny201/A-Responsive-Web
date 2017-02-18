# 开发笔记

## webStrom快捷操作
* 快速补全
* 多光标
* 模版，etc
* [快捷操作参考](http://blog.csdn.net/haoshidai/article/details/50810980)

### 多光标
Double-click Ctrl (Windows or UNIX)/Alt(OS X) and press up or down arrow keys.



## webkit
WebKit 是一个开源的浏览器引擎，与之相对应的引擎有Gecko（Mozilla Firefox 等使用）和Trident（也称MSHTML，IE 使用）。

## Three key tech in responsive design
* flexible grid layout
* flexible image
* meida queries

## advantages
* work load
* time

### 微信
* 微信采用的是X5内核，与qq浏览器一样



## princeple of responsive design
* progeressive enhancement 渐进增强
* graceful degradation 优雅降级
* 断点的选择: ex. 0 - 480 / 481 - 800 / 801 - ?

## HTML
### robot.txt
* 提供爬虫范围

### human.txt
* 开发者信息

### IE兼容模式
```HTML
<meta http-equiv="x-ua-compatible" content="ie=edge">
content ＝ 模仿某个模式的行为
ie ＝ edge ： 强制用最新的ie浏览器模式rendering页面
```
### IE的条件注释
筛选IE浏览器
```HTML
<!--[if lte/lt/gt/gte IE8]> -> 如果小于等于／小于／大于／大于等于 IE8， 则执行条件注释中的内容。
<p></p>
<![endif]-->
```



### HTML标签
* `<header>` ： 页眉
* `<footer>` ： 页脚
* `<nav>` : 可看作一个特殊的section
* `<article>` : 也可看作一个特殊的section
* `<section>` : 区块
* `<span>`: 没有具体语义，起修饰作用

## CSS

### media query

#### css2中
* media ＝ "print"
* media = "screen"

#### css3
* @meida all and A and B ...
* not/and/only/or
* , = or
* only: 兼容旧浏览器
```HTML
旧浏览器中，只会解释成，
media ＝ "only"
```
##### attribute
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

### CSS resets
引入resets为了统一不同浏览器的默认样式。

### Normalize.css
替代CSS resets的存在，但是与CSS resets有一定的差异

### 文字颜色
* 一般文字颜色会降低黑色对比度，显得更雅致，一般使用`#222`黑

### px,em,rem
* px: 像素，中文字体一般12px
* em: 相对长度，父元素的font-size
```CSS
具有继承特点，一直往上找，直到找到为止，如果没有设置font－size，浏览器会有一个默认的em设置：1em ＝ 16px
```
* rem： 相对长度，但是只根据html节点的font-size，比em安全
* font-size: 62.5% -> 1 rem = 10px
* font-size: 100% -> 1rem = 16px
* rem/em布局有利于用户调节字体大小

### ::selection
* 设置选中文字后的各种属性，例如背景颜色

### 清楚浮动
* float会产生高度塌陷, 使得高度为0
* overflow清除浮动
* 或者让父容器也同样浮动
* 最好的方法：使用伪元素after
```CSS
.clearfic:after {
    content: ".";
    display: block; 让生成的元素以块级显示，占满剩余空间。
    height: 0; 避免破坏原有高度。
    clear: both; 清除浮动
    visibility: hidden;
}
只有clear:both;是为了清除浮动的

更优雅的写法：

.clearfix:before,
.clearfix:after {
    content: " ";
    display: table;
}

.clearfix: after {
    clear: both;
}

这种写法可以防止空白崩溃。
```
* 触发BFC就可以清除浮动。

### :active seletor
The :active selector is used to select and style the active link.
A link becomes active when you click on it.

### :hover seletor
The :hover selector is used to select elements when you mouse over them.

### ::before & ::after
The ::before selector inserts something before the content of each selected element(s).

Use the content property to specify the content to insert.

Use the ::after selector to insert something after the content.


### display
* inline-block: 在一行显示
* inline
* block: Displays an element as a block element (like `<p>`)
* table: 此元素会作为块级表格来显示（类似 <table>），表格前后带有换行符。
```CSS
block元素的特点是：
　　总是在新行上开始；
　　高度，行高以及顶和底边距都可控制；
　　宽度缺省是它的容器的100%，除非设定一个宽度
　　<div>, <p>, <h1>, <form>, <ul> 和 <li>是块元素的例子。

display:inline就是将元素显示为行内元素.

　　inline元素的特点是：
　　和其他元素都在一行上；
　　高，行高及顶和底边距不可改变；
　　宽度就是它的文字或图片的宽度，不可改变。
　　<span>, <a>, <label>, <input>, <img>, <strong> 和<em>是inline元素的例子。

display:inline-block将对象呈递为内联对象，但是对象的内容作为块对象呈递。旁边的内联对象会被呈递在同一行内，允许空格。
    准确地说，应用此特性的元素呈现为内联对象，周围元素保持在同一行，但可以设置宽度和高度地块元素的属性
```

### box-sizing
```CSS
box-sizing属性可以为三个值之一：content-box（default），border-box，padding-box。

content-box，border和padding不计算入width之内

padding-box，padding计算入width内

border-box，border和padding计算入width之内，其实就是怪异模式了
```


### text-overflow
* The text-overflow property specifies how overflowed content that is not displayed should be signaled to the user.
```CSS
clip: Default value. Clips the text
ellipsis: Render an ellipsis ("...") to represent clipped text
```


### cursor: not-allowed
* The cursor indicates that the requested action will not be executed

### border-radius
* The border-radius property is used to add rounded corners to an element.

### child seletor
```CSS
header .top .tel,
    header .top ul li:nth-child(3),
    header .top ul li:nth-child(4) {
        display: none;
    }
```

### 普通selector
* E
* .class
* #id
* E F： 子元素
* E > F：只能选直系子元素，不包括孙子元素
* E + F: 相邻元素
* E ~ F:

### 属性选择器
* E[attr]：所有拥有该attribute的元素
* E[attr="value"]：对应值
* E[attr^="value"]：以value开头的
* E[attr$="value"]：以value结尾
* E[attr*="value"]：只要包含value
* E[attr~="value"]：以空格分开的词汇，有包含value的
* E[attr|="value"]：以value 开头的，以及以value－开头的

### 伪类和伪元素选择器
* :link, ;visited, :active, :focus
* :nth-child(可以用表达式：2n－> 2, 4, 6, etc...),nth-last-child()
* first-child, last-child
* nth-of-type(): 先找p类型，再往下数
* :only-child
* :only-of-type
* :not()：可嵌套别的元素

### device pixel ratio
* 一般设备都为1
* retina屏幕为2