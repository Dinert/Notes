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
+ 该布局模型的目的是提供一种更加高效的方式来对容器中的条目进行布局、对齐和分配空间。在传统的布局方式中，block布局是把块在垂直方向从上到下依次排列的，而inline布局则是在水平方向来排列。弹性盒布局并没有这样内在的方向限制，可以由开发人员自由操作






