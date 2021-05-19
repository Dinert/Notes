## CSS

### 什么是CSS?
+ CSS指的是层叠样式表
+ CSS描述了如何在屏幕、纸张或其它媒体上显示HTML元素

### CSS语法
+ CSS规则集（rule-set）由选择器和声明块组成：
![css](https://www.w3school.com.cn/i/css/selector.gif)

### CSS选择器
+ 通配符选择器：`*`
+ id选择器：`#id`
+ class选择器：`.class`
+ 标签选择器：`div`
+ 属性选择器：
  - 选择所有带有name属性的元素：`[name]`
  - 选择所有name=value的元素：`[name='value']`
  - 选择所有name中包含value的元素：`[name*='value']`
  - 选择所有name中开头为value的元素：`[name^=value]`
  - 选择所有name中结尾为value的元素：`[name$=value]`

+ 分组选择器：`div,p`
+ 后代选择器：`div span`
+ 直接后代选择器：`div > span`
+ 相邻兄弟选择器：`div+span`
+ 兄弟选择器：`div~span`

+ 伪类选择器
  - 选择只有当p元素是其父级的第一个子级样式：`p:first-child`
  - 选择只有当p元素是其父级的最后一个子级样式：`p:last-child`
  - 选择每个p元素是其父级的第一个p元素：`:first-of-type`
  - 选择每个p元素是其父级的最后一个p元素：`:last-of-type`
  - 选择每个p元素是其父级的第一个子元素：`p:nth-child(1)`
  - 选择每个p元素是其父级的最后一个子元素：`p:nth-last-child(1)`
  - 选择每个p元素是其父级的第一个p元素：`p:nth-of-type(1)`
  - 选择每个p元素是其父级的最后一个p元素：`p:nth-last-of-type(1)`

  - 选择所有未访问链接：`:link`
  - 选择所有访问过的链接：`:visited`
  - 选择活动链接: `:active`
  - 选择鼠标在链接上面时：`:hover`
  - 选择具有焦点的元素：`:focus`
  - 选择当前活动的元素：`:target`
  - 选择每一个禁用的元素：`:disabled`
  - 选择每一个启用的元素：`:enabled`
  - 选择设置了require属性的元素：`:required`
  - 选择没有任何子集的元素（包括文本节点）：`:empty`

+ 伪元素选择器
  - 在元素前面插入内容：`:before`
  - 在元素后面插件内容：`:after`

## 面试题
### 介绍一下标准的CSS的盒模型？与低版本IE的盒子 
+ 标准盒子模型：width = (content) + border + padding + margin;
+ IE盒子模型：width = (content + padding + border) + margin;

### box-sizing属性？
+ 用来控制元素的盒模型的解析模式，默认为content-box
  - content-box：W3C的标准盒子模型，设置元素的height/width属性指的是content部分的高/宽
  - border-box: IE传统盒子模型。设置元素的height/width属性指的是border + padding + border部分的高/宽

### CSS选择器有哪些？哪些属性可以继承？
+ CSS选择器：Id选择器(#id)、类选择器(.class)、标签选择器(div、p)、相邻选择器(h1 + p)、子选择器(ul > li)、后代选择器(li a)、通配符选择器(*)、属性选择器([name="value"])、伪类选择器(:hover)、伪元素选择器(::before、::after)
+ 可继承的属性：color、text-align、line-height、font-family
+ 不可继承的样式：border、padding、margin、width、height、position

### CSS优先级算法如何计算？
+ 元素选择器：1
+ class选择器、属性选择器：10
+ id选择器：100
+ 内联写法：1000
  - !import声明的样式优先级最高，如果冲突再进行计算
  - 如果优先级相同，则选择最后出现的样式
  - 继承得到的样式优先级最低

### CSS3新增伪类有哪些？
+ 选择每个p元素是其父级的第一个p元素：`:first-of-type`
+ 选择每个p元素是其父级的最后一个p元素：`:last-of-type`
+ 选择每一个禁用的元素：`:disabled`
+ 选择每一个启用的元素：`:enabled`
+ 选择每一个选中的元素：`:checked`

### 水平垂直居中元素
+ 1.margin + position
```CSS
  .box{
    width: 200px;
    height: 200px;
    position: absolute;
    top: 50%;
    left: 50%;
    margin-top: -100px;
    margin-left: -100px;
  }
```
+ 2.position + translate
```css
  .box{
    width: 200px;
    height: 200px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
```
+ 3.position + margin: auto
```css
  .box{
    width: 200px;
    height: 200px;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    margin: auto;
  }
```
+ 4.flex布局
```css
  .wrap{
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .wrap   .box{
    width: 200px;
    height: 200px;
  }
```
+ 5.flex + margin
```css
  .wrap{
    display: flex;
  }
  .wrap .box{
    width: 200px;
    height: 200px;
    margin: auto;
  }
```

### display有哪些值？说明他们的作用
+ 内联（默认）：`inline`
+ 隐藏：`none`
+ 块显示：`block`
+ 表格显示：`table`
+ 项目列表：`list-item`
+ 内联块：`inline-block`

### positon有哪些值？
+ 按照正常文档流进行排列：`static`
+ 相对定位，不脱离文档流，参考自身静态位置通过top,bottom,left,right定位: `relative`
+ 绝对定位，参考距其最近一个不为static的父级元素通过top,bottom,left,right定位：`absolute`
+ 参照html根元素进行定位：`fixed`

### CSS3有哪些新特性？
+ RGBA和透明度
+ background-image、background-repeat、background-size
+ 文字阴影：`text-shadow`
+ 圆角：`border-radius`
+ 边框图片：`border-image`
+ 盒阴影：`box-shadow`
+ 媒体查询`@media`

### 请解释一下CSS3的flexbox（弹性盒布局模型），以及适用场景？
+ 该布局模型的目的是提供一种更加高效的方式来对容器中的条目进行布局、对齐和分配空间。在传统的布局方式中，block布局是把块在垂直方向从上到下依次排列的，而inline布局则是在水平方向来排列。弹性盒布局并没有这样内在的方向限制，可以由开发人员自由操作。
+ 适用场景：弹性布局适合于移动前端开发，在Android和ios上也完美支持。

### 用纯CSS创建一个三角形的原理是什么？
```css
  .box{
    width: 0;
    height: 0;
    border-top: 40px solid transparent;
    border-left: 40px solid transparent;
    border-right: 40px solid transparent;
    border-bottom: 40px solid #FF0000;
  }
```

### 常见的兼容性问题？
+ 不同浏览器的标签默认的margin和padding不一样
+ 上下margin重合问题，相邻两个div的margin-top、margin-bottom会重合
+ 鼠标的手势：FireFox的cursor属性不支持hand，但是支持pointer，IE两个都支持，所以为了兼容都用point
+ 图片会有下边的间隙

### 为什么要初始化CSS样式？
+ 因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间页面的显示差异。

### CSS里的visibility属性有个collapse属性值？在不同浏览器下有什么区别？
+ 当一个元素的visibility属性被设置成collapse值后，对于一般元素，它的表现跟hidden是一样的。
+ chrome中，使用collapse值和使用hidden没有区别。
+ firefox、opera和IE，使用collapse值和使用display: none没有什么区别

### display:none与visibility: hidden的区别？
+ display: none不显示对应的元素，在文档布局中不再分配空间（回流 + 重绘）
+ visibility: hidden 隐藏对应元素，在文档布局仍保留原来的空间（重绘）

### 对BFC规范（块级格式化上下文：block formatting context）的理解？
+ 具有BFC特性的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素，并且BFC具有普通容器所没有的一些特性
+ 触发BFC
  - body根元素
  - 浮动元素：float除none以外的值
  - 绝对定位元素：position(absolute、fixed)
  - display为inline-block、table-cells、flex
  - overflow除了visible以外的值（hidden、auto、scroll）

### 为什么会出现浮动和什么时候需要清除浮动？清除浮动的方式？
+ 浮动元素碰到包含它的边框或者浮动元素的边框停留。由于浮动元素不在文档流中，所以文档流的块框表现得就像浮动框不存在一样。浮动元素会漂浮在文档流的块框上。
+ 浮动带来的问题
  - 父元素的高度无法被撑开，影响与父元素同级的元素
  - 与浮动元素同级的非浮动元素（内联元素）会跟随其后
  - 若非第一个元素浮动，则该元素之前的元素也需要浮动，否则会影响页面显示的结构









