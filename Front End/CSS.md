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








