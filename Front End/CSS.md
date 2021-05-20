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
+ 清除浮动的方式：
  - 父级div定义height
  - 最后一个浮动元素后加空div标签，并添加样式clear:both
  - 包含浮动元素的父标签添加样式overflow为hidden或auto
  - 父级div定义zoom

### 设置元素浮动后，该元素的display值是多少
+ 自动变成inline-block

### 使用CSS预处理器吗？
+ `Less、Sass`

### CSS优化、提高性能的方法有哪些
+ 避免过度约束
+ 避免后代选择符
+ 避免链式选择符
+ 使用紧凑的语法
+ 尽可能精简规则
+ 避免!important，可以选择其它选择器
+ 语义化命名的规范

### 浏览器是怎么解析CSS选择器的？
+ CSS选择器的解析是从右向左解析的。若从左向右的匹配，发现不符合规则，需要进行回溯，会损失很多性能。若从右向左匹配，先找到所有的最右节点，对于每一个节点，向上寻找父节点直到找到根元素或满足条件的匹配规则，则结束这个分支的遍历。两种匹配规则的性能差别很大，是因为从右向左的匹配在第一步就筛选掉了大量的不符合条件的最右节点（叶子节点），而从左向右的匹配规则的性能都浪费在了失败的查找上面。而在CSS解析完毕后，需要将解析的结果与DOM Tree的内容一起进行分析建立一棵Render Tree，最终用来绘图。在建立Render Tree时（webkit中的Attachment过程），浏览器就要为每个DOM Tree中的元素根据CSS的解析结果（Style Rules）来确定生成怎样的Render Tree。

### 在网页中应该使用奇数还是偶数字体？为什么呢？
+ 使用偶数字体。偶数字号相对更容易和web设计的其它部分构成比例关系。Windows自带的点阵宋体（中易宋体）从Vista开始只提供12、14、16px这三个大小的点阵，而13、15、17px时用的是小一号的点。（即每个字占的空间大了1 px 但点阵没变），于是略显稀疏

### margin和padding分别适合什么场景使用？
+ 何时使用margin：
  - 需要在border外侧添加空白
  - 空白处不需要背景色
  - 上下相连的两个盒子之间的空白，需要相互抵消时
+ 何时使用padding
  - 需要在border内侧添加空白
  - 空白处需要背景颜色
  - 上下相连的两个盒子的空白，希望为两者之和

### 元素竖向的百分比设定是相对于容器的高度吗？
+ 当按百分比设定一个元素的宽度时，它是相对于父容器的宽度计算的，但是，对于一些表示竖向距离的属性，例如padding-top、padding-bottom、margin-top、margin-bottom等，当按百分比设定它们时，依据的也是父容器的宽度，而不是高度。

### 全屏滚动的原理是什么？用到了CSS的哪些属性？
+ 原理：有点类似于轮播，整体的元素一直排列下去，假设有5个需要展示的全屏页面，那么高度的500%，只是展示100%，剩下的可以通过transform进行y轴定位，也可以通过margin-top实现
+ overflow: hidden; transition: all 1000ms ease;
  
### 什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE?
+ 响应式网站设计是一个网站能够兼容多个终端，而不是为每一个终端做一个特定的版本
+ 基本原理是通过媒体查询检测不同的设备屏幕尺寸做处理
+ 页面头部必需有mea声明的viewport`<meta name=’viewport’ content=”width=device-width, initial-scale=1. maximum-scale=1,user-scalable=no”>
`
### 视差滚动效果？
+ 视差滚动通过在网页向下滚动的时候，控制背景的移动速度比前景的移动速度慢来创建出令人惊叹的3D效果。
  - CSS实现：开发时间短、性能和开发效率比较好，缺点是不能兼容到低版本的浏览器
  - jQuery实现：通过控制不同层滚动速度，计算每一层的时间，控制滚动效果。能兼容到各个版本，效果可控性好。开发起来对制作者要求高。
  - 插件实现方式：parallax-scrolling，兼容性十分好

### ::before和::after中双冒号和单冒号有什么区别？解释一下这2个伪元素的作用
+ 单冒号(:)用于CSS含糊，双冒号(::)用于CSS3伪元素
+ ::before就是以一个子元素的存在，定义在元素主体内容之前的一个伪元素。并不存在于dom之中，只存在在页面之中。
+ :before和:after这两个伪元素，是在CSS2.1里新出现的。起初，伪元素的前缀使用的是单冒号语法，但随着Web的进化，在CSS3的规范里，伪元素的语法被修改成使用双冒号，成为::before ::after

### 你对line-height是如何理解的？
+ 行高是指一行文字的高度，具体说是两行文字间基线的距离。CSS中起高度作用的是height和line-height，没有定义height属性，最终其表现作用一定是line-height
+ 单行文本垂直居中：把line-height值设置为height一样大小的值可以实现单行文字的垂直居中，其实也可以把height删除。
+ 多行文本垂直剧中：需要设置display属性设置为inline-block;

### 怎么让Chrome支持小于12px的文字？
+ 使用transform的scale属性

### 让页面里的字体变清晰，变细用CSS怎么做？
-webkit-font-smoothing在window系统下没有起作用，但是在IOS设备上起作用-webkit-font-smoothing: antialiased是最佳的，灰度平滑。

### position: fixed在anfroid下无效怎么处理
`<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no"/>
`

### 如果需要手动写动画，你认为最小时间间隔是多久，为什么？
+ 多数显示器默认频率是60H，即1秒刷新60次，所以理论上最小间隔为1/60*1000ms = 16.7ms

### li与li之间有看不见的空白间隔是什么原因引起的？有什么解决办法？
+ 行框的排列会受到中间空白（回车空格）等的影响，因为空格也属于字符，这些空白也会被应用样式，占据空间，所以会有间隔，把字符大小设为0，就没有空格了。
+ 解决方法
  - 可以将li代码全部写在一排
  - 浮动li中float: left
  - 在ul中用font-size: 0（谷歌不支持）；可以使用letter-space: -3px

### display: inline-block什么时候会显示间隙？
+ 有空格的时候
+ margin正值的时候
+ 使用font-size时候

### 有一个高度自适应的div，里面有两个div，一个高度100px，希望另一个填满剩下的高度？
+ 外层div使用position: relative；高度要求自适应的div使用position: absolute;top: 100px;bottom: 0; left: 0;

### png、jpg、gif这些图片格式解释一下，分别什么时候用。有没有了解过webp？
+ png是便携式网络图片是一种无损数据压缩位图文件格式优点是：压缩比高，色彩好。大多数地方都可以用。
+ jpg是一种针对相片使用的一种失真压缩方法，是一种破坏性的压缩，在色调及颜色平滑变化做的不错。在www上，被用来储存和传输照片的格式。
+ gif是一种位图文件格式，以8位色重现真色彩的图像。可以实现动画效果
+ webp格式是谷歌在2010年推出的图片格式，压缩率只有jpg的2/3，大小比png小了45%。缺点是压缩的时间更久了，兼容性不好，目前谷歌和opera支持。

### style标签写在body后与body前有什么区别？









