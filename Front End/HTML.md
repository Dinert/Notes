# HTML

## 什么是HTML?
HTML是用来描述网页的一种语言。
+ **HTML**指的是超文本标记语言 **（Header Text Markup Language）**    
+ **HTML**不是一种编程语言，而是一种**标记语言**
+ 标记语言是一套标记标签
+ HTML使用标记标签来描述网页

## HTML标签
HTML标记标签通常被称为HTML标签（HTML Tag）
+ HTML标签是由尖括号包围的关键词，比如`<html>`
+ HTML标签通常是成对出现的，比如`<b>` 和 `</b>`
+ 标签对中的第一个标签是开始标签，第二个标签是结束标签
+ 开始和结束标签也被称为开放标签和闭合标签

## HTML文档
HTML = 网页
Web浏览器的作用是读取HTML文档，并以网页的形式显示。浏览器会识别.html(.htm)后缀结尾的文件并解析成显示的内容

## HTML元素
+ HTML元素以开始标签起始
+ HTML元素以结束标签终止
+ 元素的内容是开始标签与结束标签之间的内容
+ 某些HTML元素具有空内容（empty content）
+ 空元素在开始标签中进行关闭（以开始标签的结束而结束）
+ 大多数HTML元素可拥有属性

## HTML属性
HTML可以拥有属性
属性总是以名称/值对的形式出现，比如：name="Value"
```html
<a href="https://www.baidu.com"></a>
```

## 面试题
### DOCTYPE有什么作用？标准模式与混杂模式如何区分？它们有何意义
+ 告诉浏览器使用哪个版本的HTML规范来渲染文档
+ DOCTYPE不存在或形式不正确会导致HTML文档以混杂模式呈现
+ 标准模式以浏览器支持的最高标准执行;混杂模式中页面是一种向后兼容的方式显示

### HTML5为什么只需要写`<!DOCTYPE HTML>?`
+ HTML5不基于SGML(Standard Generalized Markup Language 标准通用标记语言)，因此不需要对DTD进行引用，但是需要DOCTYPE来规范行为。

### 内联元素有哪些？块级元素有哪些？空(void)元素有哪些？
+ 内联元素：a、span、b、strong、em
+ 块级元素：p、div、ul、li、ol、h1-h6
+ 空元素：br、hr、img、link、meta

### 页面导入样式时，使用link和@import有什么区别
+ link是xhtml标签，除了加载CSS外，还可以定义RSS等其它事务。@import属性CSS范畴，只能加载CSS
+ link引用CSS时候，页面载入时同时加载。@import需要在页面完全加载以后加载，而且@import被引用的CSS会等到引用它的CSS文件被加载完才加载
+ link是xhtml标签，无兼容问题。@import是CSS2.1提出来的，低版本的浏览器不支持
+ link支持使用javascript控制去改变样式，而@import不支持
+ link方式的样式的权重高于@import的权重
+ import在html使用时候需要`<style type="text/css"></style>`标签

+ @import导入CSS文件会等到文档加载完后再加载CSS样式表。因此，在页面DOM加载完成到CSS导入完成之间会有一段时间页面上的内容是没有样式的。
+ 解决办法：使用link标签加载CSS样式文件。因为link是顺序加载的，这样页面会等到CSS下载完之后再下载HTML文件，这样先布局好，就不会出现闪烁问题。
### 介绍一下你对浏览器内核的理解？
+ 主要分成两部分：渲染引擎和JS引擎
+ 渲染引擎：负责取得网页的内容（XTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器。
+ JS引擎：解析和执行javascript来实现网页的动态效果。
+ 最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。
### 常见的浏览器内核有哪些？
+ IE: Trident
+ Chrom: Webkit
+ Opear: Presto
+ FirFox Mozilla: Geckos
### HTML5有哪些新特性，移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分HTML和HTML5
+ 语义化标签、增强型表单、DOM扩展、原生播放、媒体元素等
+ 移除的元素：basefont、big、center、font、s、strike、tt、u、frame、frameset、noframes
+ 区分：DOCTYPE声明的方式是区分重要因素，根据新增加的结构、元素、功能来区分。
### 简述一下你对HTML语义化的理解？
+ 去掉样式的时候能够让页面呈现出清晰的结构
+ 有利于SEO和搜索引擎建立良好沟通，有助于爬虫爬取更多的信息，爬虫依赖于标签来确定上下文和各个关键字的权重。
+ 方便其它设备解析
+ 便于团队开发和维护，语义化根据可读性。
### HTML5的文件离线储存怎么使用，工作原理是什么？
+ 在线情况下，浏览器发现HTML头部有manifest属性，它会请求manifest文件，如果是第一次访问，那么浏览器就会根据manifest文件的内容下载相应的资源，并进行离线存储。如果已经访问过并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面。然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不会做任何操作，如果文件改变了，那么就会重新下载文件中的资源，并且进行离线存储。
```html 
<html manifest='cache.manifest'>
```
+ 在cache.mainifest文件中编写离线存储的资源
```txt 
    CACHE MANIFEST
#v0.11
CACHE:
js/app.js
css/style.css
NETWORK:
Resourse/logo.png
FALLBACK:
```
### cookies，sessionStorage和localStorage的区别？
+ 共同点：都是保存在浏览器端，且是同源的。
+ 区别：
  - cookies是为了标识用户身份而存储在用户本地终端上的数据，始终在同源http请求中携带，即cookies在浏览器和服务器间来回传递，而sessionstorage和localstorage不会自动把数据发给服务器，仅在本地保存。
  - 存储大小的限制不同。cookie保存的数据很小，不能超过4k，而sessionstorage和localstorage保存的数据大，可达到5M。
  - 数据的有效期不同。cookie在设置的cookie过期时间之前一直有效，即使窗口或者浏览关闭。sessionstorage仅在浏览器窗口关闭之前有效。localstorage始终有效，窗口和浏览器关闭也一直保存，用作长久数据保存。
  - 作用域不同。cookie与localstorage在所有的同源窗口都是共享。sessionstorag不在不同的浏览器间共享

### iframe框架有哪些优缺点
+ 优点：
  - iframe能够原封不动的把嵌入的网页展现出来。
  - 如果有多个网页引用iframe，那么你只需要修改iframe的内容，就可以实现调用的每一个页面内容的更改，方便快捷。
  - 网页如果为了统一风格，头部和版本都是一样的，就可以写成一个页面，用iframe来嵌套，可以增加代码的可重用。
  - 如果遇到加载缓慢的第三方内容如图标和广告，这些问题可以由iframe来解决。
+ 缺点：
  - 搜索引擎的爬虫程序无法解读这种页面
  - 框架结构中出现各种滚动条
  - 使用框架结构时，保证设置正确的导航链接
  - iframe页面会增加服务器的http请求

### label的作用是什么？是怎么用的？
+ label标签用来定义表单控件间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。label中有两个属性是非常有用的，for和accesskey
+ for属性功能：表示label标签要绑定的HTML元素，你点击这个标签的时候，所绑定的元素将获取焦点。
```html 
<label for='inputbox'><input id='inputbox' type='text'/></label>  
```
+ accesskey属性功能：表示访问label标签所绑定的元素的热键，当按下热键，所绑定的元素将获取焦点。
  ```html 
    <label for='inputbox' accesskey='n'>姓名：<input id="inputbox" type="text"></label>
  ```
### HTML5的form如何关闭自动完成功能？
+ HTML的输入框可以拥有自动完成的功能，当你往输入框输入内容的时候，浏览器会从你以前的同名输入框的历史记录中查找出类似的内容并列在输入框下面，这样就不用全部输入进去了，直接选择列表中的项目就可以了。但有时候我们希望关闭输入框的自动完成功能，例如当用户输入内容的时候，我们希望使用AJAX技术从数据库搜索并列举而不是在用户的历史记录中搜索。
+ 方法
  - 在IE的internet选项菜单中的自动完成里面设置
  - 设置form输入框的autocomplete为on或者off来开启或关闭输入框的自动完成功能

### 如何实现浏览器内多个标签页之间的通信？
+ WebSocket SharedWorker
+ 也可以调用localstorage、cookies等本地存储方式。

### WebSocket如何兼容低浏览器？
+ Adobe Flash Socket ActiveX HTMLFile(IE)基于multipart编码发送XHR基于长轮询的XHR
+ 引用WebSocket.js这个文件来兼容低版本浏览器。
### 页面可见性（Page Visibility）API可以有哪些用途？
+ 通过visibility state的值检测页面当前是否可见，以及打开网页的时间
+ 在页面被切换到其它后台进程时，自动暂停音乐或视频的播放。
### 如何在页面上实现一个圆形的可点击区域？
+ map+area或者svg
+ border-radius
+ 纯js实现，一个点不在圆上的算法

### 实现不使用border画出1px高的线，在不同浏览器的Quirks mode和CSS Compat模式下都能保持同一效果
```html
<div style="height:1px;overflow:hidden;background:red"></div>
```

### 网页验证码是干嘛的，是为了解决什么安全问题？
+ 区分用户是计算机还是人的程序 
+ 防止恶意破解密码、刷票、论坛灌水

### title标题与h1的区别、b与strong的区别、i与em的区别？
+ title属性没有明确意义，只表示标题。h1表示层次明确的标题，对页面信息的抓取也有很大的影响
+ strong标明重点内容，证明加强含义。b是无意义的视觉表示 
+ em表示强调文本。i是斜体，是无意义的视觉表示
### 元素的alt和title有什么异同
+ title是图片在滑动经过时显示的信息
+ alt是图片在src没有填写时替代显示的信息

