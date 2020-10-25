# LESS

###### LESS是一个CSS预处理器，可以为网站启用可自定义，可管理和可重用的样式表。 LESS是一种动态样式表语言，扩展了CSS的功能。 LESS也是跨浏览器友好。

###### CSS预处理器是一种脚本语言，可扩展CSS并将其编译为常规CSS语法，以便可以通过Web浏览器读取。 它提供诸如变量，函数， mixins 和操作等功能，可以构建动态CSS。

#### 注释

###### 以//开头的注释，不会被编译到CSS文件中，以/**/包裹的注释会被编译到CSS文件中

#### LESS的变量声明

##### 属性值的变量声明和取值

###### 使用@来申明一个变量：@pink: pink;  

```
@Height: 200px;
@bg: #ccc;
.wrap{
    height: @Height;
    background-color: @bg;
}
```

##### 选择器的属性声明和取值

###### 作为选择器和属性名：#@{selector的值}的形式！名称为（语法糖）

```
@hName: height;
@bg: background-color;
@{selector}: .wrap;
@{selector}{
    @{hName}: 20px;
    @{bg}: red;
}
```

###### 作为URL：@{url}

##### 变量的延迟加载	

###### 变量的延迟加载，在同一级的作用域下变量全部加载完才编译

```
.wrap{
    @Height: 30px;
    height: @Height;
    @Height: 20px;
    background-color: red;
}
```

##### 嵌套规则和&(平级)使用

```
.wrap{
    height: 20px;
    position: relative;
    .inner{
        position: absolute;
        background-color: red;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        &:hover {
            background-color: blue;
        }
    }
}
```

#### Less的混合

##### 定义一个全局样式，需要的时候调用(类似于Js的函数)

##### 普通混合：会把内容编译到CSS文件中

```
.center{
    position: absolute;
    background-color: red;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}
.wrap{
    height: 20px;
    position: relative;
    .inner{
        .center;
    }
    .inner2{
        .center;
    }
}
```

##### 不带输出的混合：不会把内容编译到CSS文件中

```
.center(){
    position: absolute;
    background-color: red;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}
.wrap{
    height: 20px;
    position: relative;
    .inner{
        .center;
    }
    .inner2{
        .center;
    }
}
```

##### 带参数的混合

```
.center(@top, @left, @bgColor){
    position: absolute;
    background-color: @bgColor;
    top: @top;
    left: @left;
    width: 100px;
    height: 100px;
}
.wrap{
    height: 20px;
    position: relative;
    .inner{
        .center(100px, 100px, red);
    }
    .inner2{
        .center(100px, 220px, blue);
    }
}
```

##### 带参数并且有默认值的混合

```
.center(@top: 100px, @left: 100px, @bgColor: red){
    position: absolute;
    background-color: @bgColor;
    top: @top;
    left: @left;
    width: 100px;
    height: 100px;
}
.wrap{
    height: 20px;
    position: relative;
    .inner{
        .center();
    }
    .inner2{
        .center(100px, 220px, blue);
    }
}
```

##### 命名参数

```
.center(@top: 100px, @left: 100px, @bgColor: red){
    position: absolute;
    background-color: @bgColor;
    top: @top;
    left: @left;
    width: 100px;
    height: 100px;
}
.wrap{
    height: 20px;
    position: relative;
    .inner{
        .center(@bgColor: #000);
    }
    .inner2{
        .center(100px, 220px, blue);
    }
}
```

##### 匹配模式：实现三角形

```
@import './triangle.less';
.wrap .sjx{
    .triangle(B, 40px, blue);
}
//三角形
.triangle(@_, @www, @cccc) {
    width: 0px;
    height: 0px;
    overflow: hidden;
}

.triangle(B, @w, @c){
    border-width: @w;
    border-color: @c transparent transparent transparent;
    border-style: solid dashed dashed dashed;
}
.triangle(R, @w, @c){
    border-width: @w;
    border-color: transparent @c transparent transparent;
    border-style: dashed solid dashed dashed;
}
.triangle(T, @w, @c){
    border-width: @w;
    border-color: transparent  transparent @c transparent;
    border-style: dashed dashed solid dashed;
}
.triangle(L, @w, @c){
    border-width: @w;
    border-color: transparent  transparent transparent @c;
    border-style: dashed dashed dashed solid;
}
```

##### argument

```
.border(@1, @2, @3){
    border: @arguments;
    width: 20px;
    height: 20px;
}
.wrap{
    .border(1px, red, solid);
}
```

#### LESS的运算

###### 在less进行运算时，只需要一个属性值带单位，如果有多个属性值带不同的单位，取第一个值的单位

```
.border(){
    width: 10px + 20px;
    height: 10px + 10rem;
    background-color: red;
}
.wrap{
    .border();
}
```

##### 继承

```
.juzhong{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
}
.center(@w, @h, @c) {
    width: @w;
    height: @h;
    background-color: @c;
}
.wrap{
    position: relative;
    width: 400px;
    height: 400px;
    border: 1px red solid;
    margin: 0 auto;
    .child{
        &:extend(.juzhong);
        &:nth-child(1) {
            .center(200px, 200px, blue);
        }
        &:nth-last-child(1){
            .center(100px, 100px, red);
        }
    }
}
```

#### LESS的避免编译

```
*{
    margin: 0;
    padding: ~"calc(0)";
} 
```

