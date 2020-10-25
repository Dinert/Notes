## 深入理解Css属性的margin	

### 可改变容器的尺寸

##### 1、可视尺寸-clientWidth（标准）

##### 2、占据尺寸-outerWidth（不存在）！但jQuery存在这样的方法

#### margin与可视尺寸

##### 1、适用于没有设定width/height的普通block水平元素

##### 2、只适用于水平方向尺寸

##### 3、一侧定宽的自适应布局

```
<div class="box">
        <div class="left">
            <img src="1.jpg" alt="">
        </div>
        <div class="right">
            我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我
        </div>
    </div>
```

#### margin与占据尺寸

##### 1、block/inline-blocki水平元素均适用

##### 2、与没有设定width/height值无关

##### 3、适用于水平方向和垂直方向

##### 4、滚动容器内上下留白

```
    <div class="box" style="height: 200px;overflow: auto;">
        <img src="1.jpg" alt="" class="box-img" style="padding: 50px 0; margin: 50px 0;">
    </div>
```

#### margin与百分比单位

##### 1、普通元素百分比

###### 1.普通元素的百分比margin都是相对于容器的宽度计算的

```
<div style="background-color: red;">
    <img src="1.jpg" alt="" style="margin: 10%;">
</div>
```

##### 2、绝对定位元素百分比

###### 1.绝对定位元素的百分比margin是相对于第一个定位祖先元素（relative/absolute/fixed）的宽度计算的

```
<div style="background-color: red;">
    <img src="1.jpg" alt="" style="position: absolute; margin: 10%;">
</div>
```

##### 3、宽高2:1自适应矩形

```
<div style="background-color: olive;width: 400px;height: 200px;">
    <div style="margin: 50%; background-color: #ccc;"></div>
</div>
```

#### 正确看待margin重叠

##### 1、margin重叠的特性

###### 1.block水平元素（不包括float和absolute元素）

###### 2.不考虑writing-mode，只发生在垂直方向（margin-top/margin-bottom）

##### 1、相邻的兄弟元素重叠

```
    <p style="margin: 10px 0;background-color: #ccc;">第一行</p>
    <p style="margin: 10px 0;background-color: #ccc;">第二行</p>	
```

##### 2、父级和第一个/最后一个子元素

```
<div style="background-color: red; margin-top: 10px;">
     <div style="margin-top: 10px;">son</div>
</div>

<div style="background-color: red;">
     <div style="margin-top: 10px;">son</div>
</div>

<div style="background-color: red; margin-top: 10px;">
     <div>son</div>
</div>
```

#### 父子margin重叠的其它条件

##### 1、父元素非块状格式上下文元素

##### 2、父元素没有border-top设置

##### 3、父元素没有padding-top值

##### 4、父元素和第一个子元素之间没有inline元素分隔

#### margin重叠口诀

##### 1.正正取大值

##### 2.正负值相加

##### 3.负负最负值

#### margin重叠的意义

##### 1、连续段落或列表之类，如果没有margin重叠，首尾项间距会和其它兄弟标签1:2关系，排版不自然；

##### 2、web中任何地方嵌套或直接放入任何裸div，都不会影响原来的布局

### 理解Css中的margin: auto

```
<div style="width: 200px; background-color: red; margin-left: 100px;margin-right: auto;">文本</div>
```

##### 图片为何不居中

```
<img src="1.jpg" alt="" style="width: 200px; display: block; margin: 0 auto;">
```

##### 为何无法垂直居中

```
<div style="height: 100px; width: 500px; margin: auto 0;background-color: red;">我是文字</div>
```

##### absolute与margin居中

```
    <div style="position: relative; height: 400px; background-color: #ccc;">
        <div style="position: absolute;top: 0;right: 0;bottom: 0;left: 0;background-color: red; width: 100px;height: 100px;margin: auto;">哈哈哈</div>
    </div>     
```

### margin失效

##### 1、inline水平元素的垂直margin无效

###### 1.非替换元素，例如：不是img元素

###### 2.正常书写模式

```
<span style="margin: 20px;">inline元素</span>
```

##### 2、margin重叠

##### 3、display: table-cell/table-row等

```
<span style="display: table; margin: 20px;">13412</span>
```

##### 4、绝对定位元素非定位方位的margin值“无效”

##### 5、鞭长莫及的元素无效

```
<img src="1.jpg" alt="" style="width: 200px;float: left;">
<div style="margin-left: 100px;">我是文字</div>
```

