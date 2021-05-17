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
  - 选择每个p元素是其父级的第一个p元素：`:first-of-type`
  - 选择每个p元素是其父级的最后一个p元素：`:last-of-type`
  - 选择只有当p元素是其父级的第一个子级样式：`p:nth-child`
  - 选择只有当p元素是其父级的最后一个子级样式：`p:nth-child`
  - 选择每个



