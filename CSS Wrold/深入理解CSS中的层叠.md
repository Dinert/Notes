# CSS世界的层叠规则

###### "层叠规则"，指的是网页中的元素发生层叠时的表现规则，意思指DOM元素渲染时在视觉上的呈现规则。

#### 1.理解CSS世界的层叠上下文和层叠水平

##### 1.1什么是层叠上下文

###### 	层叠上下文是一个概念，如果一个元素含有层叠上下文，我们可以理解为这个元素在z轴上就高人一等

![](C:\Users\彭\AppData\Roaming\Typora\typora-user-images\image-20200414202405870.png)

##### 1.2什么是层叠水平

###### 	层叠水平决定了同一个层叠上下文中元素在Z轴的显示顺序

#### 2.理解元素的层叠顺序

###### （1）位于最下面的background/border特指层叠上下文元素的边框和背景色，每一个层叠顺序规则仅适用于当前层叠上下文元素的小世界

###### （2）inline水平盒子指的的包括inline/inline-block/inline-table元素的”层叠顺序“，它们都是同等级别的

###### （3）单纯从层叠水平上看，z-index:0和z-index: auto是可以看成是一样的！实际上，两者在层叠上下文领域有着根本性的差异。

![image-20200414202617817](C:\Users\彭\AppData\Roaming\Typora\typora-user-images\image-20200414202617817.png)(C:\Users\彭\AppData\Roaming\Typora\typora-user-images\image-20200414202540867.png)

#### 3. 层叠上下文的创建

##### 3.1根层叠上下文

###### 根层叠上下文指的是页面根元素，也即是html元素，页面中所有的元素一定处于至少一个层叠结界中

##### 3.2定位元素与传统层叠上下文

###### 当position值为relative/absolute/fixed声明的定位元素，当其z-index值不是auto的时候，会创建层叠上下文

```
  <div style="position:relative;z-index:auto;">
    <img src="1.jpg" alt="" style="position:absolute;z-index: 2;">
  </div>
  <div style="position:relatie;z-index:auto;">
    <img src="2.jpg" style="position: absolute; z-index: 1;" alt="">
  </div>
```

##### 3.3CSS与新时代的层叠上下文

###### （1）元素为flex布局元素（父元素 display: flex | inline-flex），同时z-index值不是auto。

###### （2）元素的opacity值不是1

###### （3）元素的transform值不是none。

###### （4）元素mix-blend-mode值不是normal

###### （5）元素的filter值不是none

###### （6）元素的isolation值是isolate

###### （7）元素的will-change属性值为上面2-6的任意一个（如will—change: opacity）

#### 4.层叠上下文与层叠顺序

###### （1）如果层叠上下文元素不依赖z-index数值，其层叠顺序是z-index: auto，可看成z-index: 0级别

###### （2）如果层叠上下文元素依赖z-index数值，则其层叠顺序与z-index值决定

```
    <img src="1.jpg" alt="" style="position: relative;">
    <img src="2.jpg" alt="" style="transform: scale(1); margin-top: -20px;">
    
    <img src="2.jpg" alt="" style="transform: scale(1);">
    <img src="1.jpg" alt="" style="position: relative; margin-top: -20px;">
```

#### 5.z-index负值深入理解

##### 1.可访问性隐藏

```
<style>
  .box{
    background-color: blue;
    /* transform: scale(1); */
  }
  .box > img{
    position: relative;
    z-index: -1;
    right: -50px;
  }
</style>

<body>
    <div class="box">
      <img src="1.jpg" alt="">
    </div>
</body>
```

#### 6.层叠上下文的特性

##### 层叠上下文的层叠水平要比普通元素高

##### 层叠上下文可以嵌套，内部层叠上下文及其所有子元素均受制于外部的层叠上下文。

##### 每个层叠上下文和兄弟无比独立，也就是说，当进行层叠变化或渲染的时候，只需要考虑后代元素

##### 每个层叠上下文都是自成体系的，当元素发生层叠的时候，整个元素被认为是在父层叠上下文的层叠顺序中

#### 7.层叠准则，当元素发生层叠时，其覆盖关系遵循下面两条准则

###### （1）谁大谁上：当具有明显的层叠水平标识z-index属性值时，在同一个层叠上下文领域，层叠水平值大的那个覆盖小的那个

###### （2）后来居上：当元素的层叠水平一致、层叠顺序相同的时候，在DOM流中处于后面的元素会覆盖前面的元素

#### 8.z-index ”不犯二“准则

###### （1）对于非浮层元素，避免设置z-index值，z-index值最好不要超过2。

###### （2）可以尝试用元素原生的层叠顺序进行层级控制
