		简介—W3C标准—IE9以下不支持

CSS3是CSS2的升级版本，3只是版本号，它在CSS2.1的基础上增加了很多强大的新功能。 目前主流浏览器**chrome**、**safari**、**firefox**、**opera**、甚至360都已经支持了CSS3大部分功能了，**IE10**以后也开始全面支持CSS3了。

##### border-radius圆角边框属性

```
    .parent{
      height: 100px;
      width: 100px;
      background-color: red;  
      border-radius: 50px 50px 0 0;
    }
```

##### box-shadow边框阴影属性

``` 
.parent{
  width: 100px;
  height: 100px;
  box-shadow:4px 2px 6px 2px #f00, -1px -1px 6px 3px #000, 5px 1px 5px 2px #33cc00 inset;
}
```

##### border-image为边框应用图片

```
    .parent{
      width: 100px;
      height: 100px;
      border: 20px red solid;
      border-image: url(http://img.mukewang.com/52e22a1c0001406e03040221.jpg) 50 stretch;
    }
```

##### CSS3颜色 颜色之RGBA

```
    .parent{
      width: 100px;
      height: 100px;
      background-color: rgba(255, 255, 255, 0.5);
    }
```

##### CSS3颜色 渐变色彩 **Gradient** 分为**线性渐变(linear)**和**径向渐变(radial)**

```
    .parent{
      width: 100px;
      height: 100px;
      background-image: linear-gradient(to top left, red, blue);
    }
```

##### CSS3文字与字体 text-overflow 与 word-wrap

```
    .parent{
      width: 100px;
      text-overflow: ellipsis;
      overflow: hidden;
      white-space: nowrap;
    }
```

##### CSS3文字与字体 嵌入字体@font-face

```
    @font-face{
      font-family: "MOOC Font";
      src: url("http://www.imooc.com/Amaranth-BoldItalic.otf");
    }
    .parent{
      width: 100px;
      font-family: 'MOOC Font';
    }
```

##### CSS3文字与字体 文本阴影text-shadow

```
    .parent{
      width: 100px;
      text-shadow: 2px 2px 2px red;
    }
```

##### 背景图片的原始起始位置background-origin，需和背景no-repeat配合使用，否则无效

```
    .parent{
      width: 300px;
      height: 300px;
      border: 20px solid rgba(255, 0, 0, 0.5);
      padding: 20px;
      background: url(1.jpg) no-repeat;
      background-origin: content-box;
    }
```

##### CSS3背景 background-clip背景图片做适当的**裁剪**以适应实际需要

```
    .parent{
      width: 300px;
      height: 300px;
          border: 20px solid rgba(255, 0, 0, 0.5);
      padding: 20px;
      background: url(1.jpg) no-repeat;
      background-clip: content-box;
    }

```

##### CSS3背景 background-size，以**长度值**或**百分比**显示，还可以通过**cover**和contain

```
    .parent{
      width: 300px;
      height: 300px;
      background: url(1.jpg) no-repeat;
      background-size: 100% 100%;
    }
```

##### CSS3背景 multiple backgrounds

```
    .parent {
        width: 300px;
        height: 140px;
        border: 1px solid #999;
        background:url(http://static.mukewang.com/static/img/logo_index.png) no-repeat 0 0 / 75% 55%,
                  url(http://static.mukewang.com/static/img/logo_index.png) no-repeat right bottom/ 50% 40%;

    }
```

##### CSS3导航栏

```
    body{
      background: #ebebeb;
    }

    .nav{
      width: 560px;
      height: 50px;
      font: bold 0/50px Arial;
      text-align: center;
      margin: 40px auto 0;
      background-color: #f65f57;
      border-radius: 10px;
      box-shadow: 0px 8px 0px #900;
    }
    .nav a{
      display: inline-block;
      -webkit-transition: all 0.2s ease-in;
      -moz-transition: all 0.2s ease-in;
      -ms-transition: all 0.2s ease-in;
      -o-transition: all 0.2s ease-in;
      transition: all 0.2s ease-in;
    }

    .nav a:hover{
      -webkit-transform: rotate(10deg);
      -moz-transform: rotate(10deg);
      -o-transform: rotate(10deg);
      -ms-transform: rotate(10deg);
      transform: rotate(10deg);
    }

    .nav li{
      position: relative;
      display: inline-block;
      padding: 0 16px;
      font-size: 13px; 
      text-shadow: 1px 2px 4px rgba(0, 0, 0, 0.5);
      list-style: none outside none; 
    }

    .nav li::before, .nav li::after{
      content: "";
      position: absolute;
      top: 14px;
      height: 25px;
      width: 1px;
    }

    .nav li::after {
      right: 0;
      background: -moz-linear-gradient(top, rgba(255, 255, 255, 0), rgba(255, 255, 255, .2) 50%, rgba(255, 255, 255, 0));
      background: -ms-linear-gradient(top, rgba(255, 255, 255, 0), rgba(255, 255, 255, .2) 50%, rgba(255, 255, 255, 0));
      background: -webkit-linear-gradient(top, rgba(255, 255, 255, 0), rgba(255, 255, 255, .2) 50%, rgba(255, 255, 255, 0));
      background: -o-linear-gradient(top, rgba(255, 255, 255, 0), rgba(255, 255, 255, .2) 50%, rgba(255, 255, 255, 0));
          background: linear-gradient(top, rgba(255, 255, 255, 0), rgba(255, 255, 255, .2) 50%, rgba(255, 255, 255, 0));
    }
    .nav li::before {
      left: 0;
      background: -moz-linear-gradient(top, #ff625a, #9e3e3a 50%, #ff625a);
      background: -webkit-linear-gradient(top, #ff625a, #9e3e3a 50%, #ff625a);
      background: -o-linear-gradient(top, #ff625a, #9e3e3a 50%, #ff625a);
      background: -ms-linear-gradient(top, #ff625a, #9e3e3a 50%, #ff625a);
      background: linear-gradient(top, #ff625a, #9e3e3a 50%, #ff625a);
    }
	.nav li:first-child::after{
      background: none;
    }
    .nav li:last-child::before{
      background: none;
    }
    .nav a, .nav a:hover{
      color: #fff;
    }
	<ul class="nav">
    	<li><a href="">Home</a></li>
    	<li><a href="">About Me</a></li>
    	<li><a href="">Portfolio</a></li>
    	<li><a href="">Blog</a></li>
    	<li><a href="">Resources</a></li>
    	<li><a href="">Contact Me</a></li>
	</ul>	
```

##### 属性选择器

```
    a[class^='column'] {
      background-color: red;
    }
    a[href$='doc'] {
      background-color: green;
    }
    a[title*='box'] {
      background-color: blue;
    }


<a href="##" class="columnNews">我的背景想变成红色</a>
<a href="##" class="columnVideo">我的背景想变成红色</a>
    <a href="##" class="columnAboutUs">我的背景想变成红色</a><br/>
<a href="1.doc">我的背景想变成绿色</a>
<a href="2.doc">我的背景想变成绿色</a><br/>
<a href="##" title="this is a box">我的背景想变成蓝色</a>
<a href="##" title="box1">我的背景想变成蓝色</a>
<a href="##" title="there is two boxs">我的背景想变成蓝色</a>
```

##### 结构性伪类选择器—root => html元素

```
   :root{
     background: #ebebeb;
   }
```

##### CSS3 结构性伪类选择器—not，`:not`选择器称为否定选择器

```
   	div:not([id="footer"]){
  		background: red;
	}
    <div id="head">页头</div>
    <div id="page">页体</div>
    <div id="footer">页脚</div>
```

##### CSS3 结构性伪类选择器—empty => 用来选择没有任何内容的元素

```
    div:empty{
      min-height: 30px;
      border: 1px red solid;
    }
    <div>我这里有内容</div>
    <div> <!-- 我这里有一个空格 --></div>
    <div></div><!-- 我这里任何内容都没有 -->
```

#####  CSS3 结构性伪类选择器—target => 用来匹配文档(页面)的url的某个标志符的目标元素

```
    #brand:target p{
      background-color: orange;
      color: white;
    }
    <div class="menuSection" id="brand">
        <h2><a href="#brand" >Brand</a></h2>
        <p>content for Brand</p>
    </div>
```

##### CSS3 结构性伪类选择器—first-child => 选择父元素的第一个子元素

```
    ul > li:first-child{
      background-color: red;
    }
     <ul>
          <li><a href="##">Link1</a></li>
          <li><a href="##">Link2</a></li>
          <li><a href="##">Link3</a></li>
     </ul>
```

##### CSS3 结构性伪类选择器—last-child =>  选择父元素的最后一个子元素

```
    ul > li:last-child{
      background-color: red;
    }
      <ul>
          <li><a href="##">Link1</a></li>
          <li><a href="##">Link2</a></li>
          <li><a href="##">Link3</a></li>
      </ul>
```

##### CSS3 结构性伪类选择器—nth-child(n) =>选择父元素下一个或多个子元素

```
    ol > li:nth-child(2n+1){
      background-color: red;
    }
     <ol>
          <li>item1</li>
          <li>item2</li>
          <li>item3</li>
          <li>item4</li>
          <li>item5</li>
          <li>item6</li>
          <li>item7</li>
          <li>item8</li>
          <li>item9</li>
          <li>item10</li>
     </ol>
```

##### CSS3 结构性伪类选择器—nth-last-child(n) =>选择父元素下的一个或多个子元素，从后往前

```
    ol > li:nth-last-child(5){
      background-color: red;
    }
      <ol>
          <li>item1</li>
          <li>item2</li>
          <li>item3</li>
          <li>item4</li>
          <li>item5</li>
          <li>item6</li>
          <li>item7</li>
          <li>item8</li>
          <li>item9</li>
          <li>item10</li>
      </ol>
```

##### CSS3 first-of-type选择器  => 选择父元素下指定标签的第一个元素

```
    .wrapper > div:first-of-type{
      min-height: 30px;
      background-color: green;
    }
      <div class="wrapper">
          <p>我是第一个段落</p>
          <p>我是第二个段落</p>
          <div>我是第一个Div元素</div>
          <div>我是第二个Div元素</div>
          <p>我是第三个段落</p>
          <p>我是第四个段落</p>
          <div>我是第三个Div元素</div>
          <div>我是第四个Div元素</div>
      </div>
```

##### CSS3 last-of-type选择器 => 选择父元素下指定标签的最后一个元素

```
    .wrapper > div:last-of-type{
      background: orange;
    }
       <div class="wrapper">
          <div>我是第一个Div元素</div>
          <div>我是第二个Div元素</div>
          <div>我是第三个Div元素</div>
          <p>我是第一个段落</p>
          <p>我是第二个段落</p>
          <p>我是第三个段落</p>
      </div>
```



##### CSS3 nth-of-type(n)选择器 => 选择父元素下指定标签的n个元素

```
    .wrapper > div:nth-of-type(n){
      min-height: 30px;
      background-color: green;
    }
     <div class="wrapper">
          <div>我是一个Div元素</div>
          <p>我是一个段落元素</p>
          <div>我是一个Div元素</div>
          <p>我是一个段落</p>
          <div>我是一个Div元素</div>
          <p>我是一个段落</p>
          <div>我是一个Div元素</div>
          <p>我是一个段落</p>
          <div>我是一个Div元素</div>
          <p>我是一个段落</p>
          <div>我是一个Div元素</div>
          <p>我是一个段落</p>
          <div>我是一个Div元素</div>
          <p>我是一个段落</p>
          <div>我是一个Div元素</div>
          <p>我是一个段落</p>
     </div>
```

##### CSS3 nth-last-of-type(n)选择器 =>选择父元素下指定标签的n个元素，从尾到头

```
    .wrapper > p:nth-last-of-type(1){
      background: orange;
    }
      <div class="wrapper">
          <p>我是第一个段落</p>
          <p>我是第二个段落</p>
          <p>我是第三个段落</p>
          <p>我是第四个段落</p>
          <p>我是第五个段落</p>
          <div>我是一个Div元素</div>
          <p>我是第六个段落</p>
          <p>我是第七个段落</p>
      </div>
```

##### CSS3 only-child选择器 => 选择父元素下指定标签并且只有一个的元素

```
    li:only-child{
      background-color: orange;
    }
     <ul>
       <li>item1</li>
       <li>item2</li>
       <li>item3</li>  
     </ul>
     <ul>
       <li>item</li>
     </ul>
```

##### CSS3 only-of-type选择器 => 选择父元素下指定标签并且只出现一次的元素

```
    p:only-of-type{
      background-color: orange;
    }
      <div class="wrapper">
        <p>我是一个段落</p>
      </div>
      
      <div class="wrapper">
        <div>我是一个Div元素</div>
        <p>我是一个段落</p>
        <div>我是一个Div元素</div>
        <p>fd</p>
      </div>
```

##### CSS3选择器 :enabled选择器   

##### CSS3选择器 :disabled选择器

##### CSS3选择器 :checked选择器	

##### CSS3选择器 ::selection选择器 => 点击鼠标突出显示

##### CSS3选择器 :read-only选择器 =>	指定处于只读状态元素的样式

##### CSS3选择器 :read-write选择器 => 指定处于非只读状态时的样式

```
		<form action="#">
				<div>
					<label for="name">姓名:</label>
					<input type="text" name="name" id="name" placeholder="大漠" />
				</div>
				<div>
					<label for="address">地址:</label>
					<input type="text" name="address" id="address" placeholder="中国上海" readonly="readonly" />
				</div>
				<div>
					<label for="comment">评论：</label>
					<textarea name="comment" id="" cols="30" rows="10" readonly="readonly"></textarea>
				</div>
				<div>
            <label for="name">Text Input:</label>
            <input type="text" name="name" id="name" placeholder="可用输入框"  />
          </div>
           <div>
            <label for="name">Text Input:</label>
            <input type="text" name="name" id="name" placeholder="禁用输入框"  						disabled="disabled" />
					</div>
					<div class="wrapper">
							<div class="box">
								<input type="radio" checked="checked"  id="boy" name="1" /><span></span>
							</div>
							<label for="boy">男</label>
						</div>
						
						<div class="wrapper">
								<div class="box">
								<input type="radio"  id="girl" name="1"  /><span></span>
							</div>
							<label for="girl">女</label>
						</div>
						<div>
								<label for="name">姓名:</label>
								<input type="text" name="name" id="name" placeholder="大漠" />
							</div>
							<div>
								<label for="address">地址:</label>
								<input type="text" name="address" id="address" placeholder="中国上海" readonly="readonly" />
							</div>
							<div>
								<label for="comment">评论：</label>
								<textarea name="comment" id="" cols="30" rows="10" readonly="readonly"></textarea>
							</div>
		</form>
```



##### CSS3选择器 ::before和::after =>给元素的前面或后面插入内容

```
    .box h3{
      text-align: center;
      position: relative;
      top: 80px;
    }
    .box{
      width: 70%;
      height: 200px;
      background: #fff;
      margin: 40px auto;
    }
    .effect{
      position: relative;
      -webkit-box-shadow: 0 1px 4px rgba(0, 0, 0, .3), 0 0 40 rgba(0, 0, 0, .1) inset;
      -moz-box-shadow: 0 1px 4px rgba(0, 0, 0, .3), 0 0 40 rgba(0, 0, 0, .1) inset;
      box-shadow: 0 1px 4px rgba(0, 0, 0, .3),  0 0 40px rgba(0, 0, 0, 0.1) inset;
    }
    .effect::before, .effect::after{
      content: "";
      position: absolute;
      z-index: -1;
      -webkit-box-shadow: 0 0 20px rgba(0, 0, 0, .8);
      -moz-box-shadow: 0 0 20px rgba(0, 0, 0, .8);
      box-shadow: 0 0 20px rgba(0, 0, 0, .8);
      top: 50%;
      bottom: 0;
      left: 10px;
      right: 10px;
      border-radius: 100px / 10px;
    }
    
     <div class="box effect">
         <h3>Shadow Effect </h3>
     </div>
```

##### CSS3变形--旋转 rotate()

``` js
     .wrapper{
       width: 300px;
       height: 200px;
       position: absolute;
       top: 0;
       right: 0;
       bottom: 0;
       left: 0;
       margin: auto;
     }
     .wrapper div{
        width: 300px;
        height: 200px;
        line-height: 200px;
        text-align: center;
        background: green;
        color: #fff;
        -webkit-transform: rotate(-20deg);
        -moz-transform: rotate(-20deg);
        transform:rotate(-20deg);
      }
      .wrapper span {
        display:block;
      -webkit-transform: rotate(20deg);
      -moz-transform: rotate(20deg);
        transform:rotate(20deg);
      }
      
      <div class="wrapper">
 		<div><span>我不想旋转(^_^)</span></div>
      </div>
```

##### CSS3中的变形--扭曲 skew()

```
    .wrapper{
      width: 300px;
      height: 100px;
      border: 2px dotted red;
      margin: 30px auto;
    }

    .wrapper div{
      width: 300px;
      height: 100px;
      line-height: 100px;
      text-align: center;
      color: #fff;
      background: orange;
      -webkit-transform: skew(45deg);
      -moz-transform: skew(45deg);
      transform: skew(45deg);
    }

    .wrapper span{
      display: block;
      -webkit-transform: skew(-45deg); 
      -moz-transform: skew(-45deg); 
      transform:skew(-45deg);
    }
    
    
    <div class="wrapper">
      <div><span>我不想被扭曲(^_^)</span></div>
    </div>
```

##### CSS3中的变形--缩放 scale()

```
    .wrapper {
      width: 200px;
      height: 200px;
      border: 2px dashed red;
      margin: 100px auto;
    }

    .wrapper div {
      width: 200px;
      height: 200px;
      line-height: 200px;
      background: orange;
      text-align: center;
      color: #fff;
    }

    .wrapper div:hover {
      opacity: .5;
      -webkit-transform: scale(0.8);
      -moz-transform: scale(0.8);
      transform: scale(0.8);
    }
    
      <div class="wrapper">
          <div>我将缩小0.8</div>
      </div>
```

##### CSS3中的变形--位移 translate()

```
    .wrapper {
      padding: 20px;
      background: orange;
      color: #fff;
      position: absolute;
      top: 50%;
      left: 50%;
      border-radius: 5px;
      -webkit-transform: translate(-50%, -50%);
      -moz-transform: translate(-50%, -50%);
      transform: translate(-50%, -50%);
    }
   <div class="wrapper">
      我不知道我的宽度和高是多少，我要实现水平垂直居中
    </div>
```

##### CSS3中的变形--矩阵 matrix()

```
.wrapper {
  width: 300px;
  height: 200px;
  border: 2px dotted red;
  margin: 40px auto;
}

.wrapper div {
  width:300px;
  height: 200px;
  background: orange;
  transform: matrix(1,0,0,1,100,100);
}

<div class="wrapper">
  <div></div>
</div>
```

##### CSS3中的变形--原点 transform-origin

```
.wrapper {
  width: 400px;
  height: 100px;
  border: 2px dotted red;
  margin: 20px auto; 
  text-align: center;
  line-height: 100px;
}
.wrapper div {
  background: orange;
  color: #fff;
  -webkit-transform: skew(15deg);
  -moz-transform: skew(15deg);
  transform: skew(15deg);
  -webkit-transform-origin: top right;
  -moz-transform-origin: top right;
  transform-origin: top right;
}

<div class="wrapper">
  <div>我修改原点之后在进行15度的扭曲</div>
</div>
```

##### CSS3中的动画--过渡属性 transition-property=> 指定过渡或动态模拟的CSS属性

```
div {
  width: 200px;
  height: 200px;
  background: red;
  margin: 20px auto;
  -webkit-transition-property: width;
  transition-property: width;
  -webkit-transition-duration:.5s;
  transition-duration:.5s;
  -webkit-transition-timing-function: ease-in;
  transition-timing-function: ease-in;
  -webkit-transition-delay: .18s;
  	transition-delay:.18s;
}
div:hover {
  width: 400px;
}

<div></div>
```

##### CSS3中的动画--过渡所需时间 transition-duration

```
div {
  width: 300px;
  height: 200px;
  background-color: orange;
  margin: 20px auto;
  -webkit-transition-property: height;
  transition-property: height;
  -webkit-transition-duration: 1s;
  transition-duration: 1s;
  -webkit-transition-timing-function: ease-out;
  transition-timing-function: ease-out;
  -webkit-transition-delay: .2s;
  transition-delay: .2s;
}
div:hover {
  height: 100px;
}
```

##### CSS3中的动画--过渡函数 transition-timing-function

```
div {
  width: 200px;
  height: 200px;
  background-color: orange;
  margin: 20px auto;
  border-radius: 100%;
  -webkit-transition-property: -webkit-border-radius;
  transition-property: border-radius;
  -webkit-transition-duration: 1s;
  transition-duration: 1s;
  -webkit-transition-timing-function: linear;
  transition-timing-function: linear;
  -webkit-transition-delay: .2s;
  transition-delay: .2s;
}
div:hover {
  border-radius: 0px;
}
```

##### CSS3中的动画--过渡延迟时间 transition-delay

```
.wrapper {
  width: 400px;
  height: 200px;
  margin: 20px auto;
  border: 2px dotted red;
  position:relative;
}

.wrapper div {
  padding: 15px 20px;
  color: #fff;
  background-color: orange;
  position: absolute;
  top: 50%;
  left:50%;
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
  -webkit-transition: all .5s ease-in .2s;
  transition: all .5s ease-in .2s;
}

.wrapper div:hover {
  background-color: red;
  border-radius: 10px;
}

      <div class="wrapper">
          <div>鼠标放到我的身上来</div>
      </div>
```

##### CSS3 Keyframes介绍

```
  @keyframes changeColor{
    0%{
      background-color: red;
    }
    20%{
      background-color: blue;
    }
    40%{
      background-color: orange;
    }
    60%{
      background-color: green;
    }
    80%{
      background-color: yellow;
    }
    100%{
      background-color: purple;
    }
  }

  div{
    width: 300px;
    height: 200px;
    background-color: red;
    color: #fff;
    margin: 20px auto;
  }
  div:hover{
    animation: changeColor 5s ease-out .2s;
  }

    <div>鼠标移到我身上</div>

```

##### CSS3中调用动画-animation-name=>这个属性是调用的动画名

```
  @keyframes around {
    0% {
      transform: translateX(0);
    }

    25% {
      transform: translateX(180px);
    }

    50% {
      transform: translate(180px, 180px);
    }

    75% {
      transform: translate(0, 180px);
    }

    100% {
      transform: translateY(0);
    }
  }
  div{
    width: 200px;
    height: 200px;
    border: 1px solid red;
    margin: 20px auto;
  }

  div span {
    display: inline-block;
    width: 20px;
    height: 20px;
    background: orange;
    border-radius: 100%;
    animation: around;
    animation-duration: 10s;
    animation-timing-function: ease;
    animation-delay: 1s;
    animation-iteration-count: infinite;
  }
  
  <div><span></span></div>
```

##### CSS3中设置动画播放时间-animation-duration

```
@keyframes changeColor {
  from {
    background: red;
  }
  to {
    background:green;
  }
}
div {
  width: 200px;
  height: 200px;
  background: red;
  text-align:center;
  margin: 20px auto;
  line-height: 200px;
  color: #fff;
}
div:hover {
  animation-name: changeColor;
  animation-duration: 5s;
  animation-timing-function: ease-out;
  animation-delay: .1s;
}

<div>Hover Me</div>
```

##### CSS3中设置动画播放方式-animation-timing-function

```
@keyframes move {
  0%{
    transform: translate(0);
  }
  15%{
    transform: translate(100px,180px);
  }
  30%{
    transform: translate(150px,0);
  }
  45%{
    transform: translate(250px,180px);
  }
  60%{
    transform:translate(300px,0);
  }
  75%{
    transform: translate(450px,180px);
  }
  100%{
    transfrom: translate(480px,0);
  }
}
div {
  width: 500px;
  height: 200px;
  border: 1px solid red;
  margin: 20px auto;
}
div span {
  display: inline-block;
  width: 20px;
  height: 20px;
  background: green;
  border-radius: 100%;
  animation-name:move;
  animation-duration: 10s;
  animation-timing-function:ease;
  animation-delay:.1s;
  animation-iteration-count:infinite;
}
<div><span></span></div>
```

##### CSS3中设置动画开始播放的时间-animation-delay

```
  @keyframes move {
  0%{
    transform: translate(0);
  }
  15%{
    transform: translate(100px,180px);
  }
  30%{
    transform: translate(150px,0);
  }
  45%{
    transform: translate(250px,180px);
  }
  60%{
    transform:translate(300px,0);
  }
  75%{
    transform: translate(450px,180px);
  }
  100%{
    transfrom: translate(480px,0);
  }
}
div {
  width: 500px;
  height: 200px;
  border: 1px solid red;
  margin: 20px auto;
}
div span {
  display: inline-block;
  width: 20px;
  height: 20px;
  background: green;
  border-radius: 100%;
  animation-name:move;
  animation-duration: 10s;
  animation-timing-function:ease;
  animation-delay:3s;
  animation-iteration-count:infinite;
}

    <div><span></span></div>
```

##### CSS3中设置动画播放次数-animation-iteration-count

```
@keyframes move {
  0%{
    transform: translate(0);
  }
  15%{
    transform: translate(100px,180px);
  }
  30%{
    transform: translate(150px,0);
  }
  45%{
    transform: translate(250px,180px);
  }
  60%{
    transform:translate(300px,0);
  }
  75%{
    transform: translate(450px,180px);
  }
  100%{
    transfrom: translate(480px,0);
  }
}

div {
  width: 500px;
  height: 200px;
  border: 1px solid red;
  margin: 20px auto;
}
div span {
  display: inline-block;
  width: 20px;
  height: 20px;
  background: green;
  border-radius: 100%;
  animation-name:move;
  animation-duration: 2s;
  animation-timing-function:ease;
  animation-delay:.1s;
  animation-iteration-count:3;
}
<div><span></span></div>	
```

##### CSS3中设置动画播放方向-animation-direction

```
@keyframes move {
  0%{
    transform: translateY(90px);
  }
  15%{
    transform: translate(90px,90px);
  }
  30%{
    transform: translate(180px,90px);
  }
  45%{
    transform: translate(90px,90px);
  }
  60%{
    transform: translate(90px,0);
  }
  75%{
    transform: translate(90px,90px);
  }
  90%{
    transform: translate(90px,180px);
  }
  100%{
    transform: translate(90px,90px);
  }
}

div {
  width: 200px;
  height: 200px;
  border: 1px solid red;
  margin: 20px auto;
}
span {
  display: inline-block;
  width: 20px;
  height: 20px;
  background: orange;
  transform: translateY(90px);
  animation-name: move;
  animation-duration: 10s;
  animation-timing-function: ease-in;
  animation-delay: 3s;
  animation-iteration-count:infinite;
  animation-direction: alternate;
}

<div><span></span></div>
```

##### CSS3中设置动画的播放状态-animation-play-state

```
@keyframes move {
  0%{
    transform: translateY(90px);
  }
  15%{
    transform: translate(90px,90px);
  }
  30%{
    transform: translate(180px,90px);
  }
  45%{
    transform: translate(90px,90px);
  }
  60%{
    transform: translate(90px,0);
  }
  75%{
    transform: translate(90px,90px);
  }
  90%{
    transform: translate(90px,180px);
  }
  100%{
    transform: translate(90px,90px);
  }
}

div {
  width: 200px;
  height: 200px;
  border: 1px solid red;
  margin: 20px auto;
}
span {
  display: inline-block;
  width: 20px;
  height: 20px;
  background: orange;
  transform: translateY(90px);
  animation-name: move;
  animation-duration: 10s;
  animation-timing-function: ease-in;
  animation-delay: .2s;
  animation-iteration-count:infinite;
  animation-direction:alternate;
  animation-play-state:paused;
}
div:hover span{
  animation-play-state: running;
}

<div><span></span></div>
```

##### CSS3中设置动画时间外属性—animation-fill-mode

```
@keyframes redToBlue{
  from{
    background: red;
  }
  20%{
      background:green;
  }
  40%{
      background:lime;
  }
  60%{
      background:yellow;
  }
  to{
    background:blue;
  }
}

div {
  width: 200px;
  height: 200px;
  background: red;
  margin: 20px auto;
  animation-name:redToBlue;
  animation-duration: 5s;
  animation-timing-function: ease;
  animation-delay: 1s;
  animation-fill-mode: both; 
}
```

##### CSS3 多列布局模块—Columns 

```
		.columns {
			width: 500px;
			padding: 5px;
			border: 1px solid green;
			margin: 20px auto;
			-webkit-columns: 150px 3;
			-moz-columns: 150px 3;
			-o-columns: 150px 3;
			-ms-columns: 150px 3;
			columns: 150px 3;
		}

<div class="columns">
				<h2>我要分列显示</h2>
				<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
				<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
	 </div>
```

##### CSS3 多列布局定义元素列宽—column-width

```
    <div class="columns">
      <h2>我要分列显示</h2>
      <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
      <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
      <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
    </div>

.columns {
  padding: 5px;
  border: 1px solid green;
  width: 900px;
  margin: 20px auto;
  
  -webkit-column-width:200px;
  -o-column-width:200px;
  -ms-column-width:200px;
  -moz-column-width:200px;
  column-width:200px;
  
  -webkit-column-count:3;
  -moz-column-count:3;
  -o-column-count:3;
  -ms-column-count:3;
  column-count:3;
}
```

##### CSS3 多列布局，元素指定想要的列数和允许的最大列数—column-count

```
<div class="columns">
  <h2>我要分列显示</h2>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
</div>

.columns {
  padding: 5px;
  border: 1px solid green;
  width: 600px;
  margin: 20px auto;
  
  -webkit-column-count: 2;
  -moz-column-count: 2;
  -o-column-count: 2;
  -ms-column-count: 2;
  column-count: 2;
}
```

##### CSS3 列间距column-gap—设置列与列之间的间距

```
<div class="columns">
  <h2>我要分列显示</h2>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
</div>

.columns {
  padding: 5px;
  border: 1px solid green;
  width: 900px;
  margin: 20px auto;
  
  -webkit-column-count:3;
  -moz-column-count:3;
  -o-column-count:3;
  -ms-column-count:3;
  column-count:3;
  
  -webkit-column-gap: 3em;
  -moz-column-gap: 3em;
  -o-column-gap: 3em;
  -ms-column-gap: 3em;
  column-gap: 3em;
}
```

##### CSS3 列表边框column-rule =>定义列与列之间的**边框宽度、边框样式**和**边框颜色**

```
<div class="columns">
  <h2>我要分列显示</h2>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
  <p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
</div>

.columns {
  padding: 5px;
  border: 1px solid green;
  width: 900px;
  margin: 20px auto;
  
  -webkit-column-count:3;
  -moz-column-count:3;
  -o-column-count:3;
  -ms-column-count:3;
  column-count:3;
  
  -webkit-column-gap: 2em;
  -moz-column-gap: 2em;
  -o-column-gap: 2em;
  -ms-column-gap: 2em;
  column-gap: 2em;
  
  -webkit-column-rule: 2px solid gray;
  -moz-column-rule: 2px solid gray;
  -o-column-rule: 2px solid gray;
  -ms-column-rule: 2px solid gray;
          column-rule: 2px solid gray;
}
```

##### CSS3 跨列设置column-span

```
	<div class="columns">
		<h2>我要分列显示</h2>
		<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout
			Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
		<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout
			Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
		<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout
			Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
		<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout
			Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
		<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout
			Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
		<p>为了能在Web页面中方便实现类似报纸、杂志那种多列排版的布局，W3C特意给CSS3增加了一个多列布局模块（CSS Multi Column Layout
			Module）。它主要应用在文本的多列布局方面。对于文本的多列布局，我想大家并不陌生，因为报纸和杂志上我们随处可见，这种布局在报纸和杂志上都使用了几十年了，但需要在Web页面上实现文本的多列布局，正如下图所示。</p>
	</div>
	
			.columns {
			padding: 5px;
			border: 1px solid green;
			width: 900px;
			margin: 20px auto;

			-webkit-column-count: 3;
			-moz-column-count: 3;
			-o-column-count: 3;
			-ms-column-count: 3;
			column-count: 3;

			-webkit-column-gap: 2em;
			-moz-column-gap: 2em;
			-o-column-gap: 2em;
			-ms-column-gap: 2em;
			column-gap: 2em;

			-webkit-column-rule: 3px gray solid;
			-moz-column-rule: 3px gray solid;
			-o-column-rule: 3px gray solid;
			-ms-column-rule: 3px gray solid;
			column-rule: 3px gray solid;
		}
		h2 {
			background: green;
			padding: 10px;
			color: #fff;
		}
		h2,
		p:nth-last-child(2n){
			-webkit-column-span: all;
			-moz-column-span: all;
			-o-column-span: all;
			-ms-column-span: all;
			column-span: all;
			background-color: red;
		}
```

##### CSS3 盒子模型—W3C标准盒模型

```
外盒尺寸计算（元素空间尺寸）

element空间高度＝内容高度＋内距＋边框＋外距

element空间宽度＝内容宽度＋内距＋边框＋外距

内盒尺寸计算（元素大小）

element高度＝内容高度＋内距＋边框（height为内容高度）

element宽度＝内容宽度＋内距＋边框（width为内容宽度）
```

**2.IE传统下盒模型（IE6以下，不包含IE6版本或”QuirksMode下IE5.5+”）**

```
外盒尺寸计算（元素空间尺寸）

element空间高度＝内容高度＋外距（height包含了元素内容宽度、边框、内距）

element宽间宽度＝内容宽度＋外距（width包含了元素内容宽度、边框、内距）

内盒尺寸计算（元素大小）

element高度＝内容高度（height包含了元素内容宽度、边框、内距）

element宽度＝内容宽度（width包含了元素内容宽度、边框、内距）
```

##### CSS3 伸缩布局

```
	html,body{
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		height: 100%;
	}
	div{
		width: 100px;
		height: 100px;
		background-color: red;
	}
	
	<div></div>
```

##### Media Queries——媒体类型（一）

在CSS2中常碰到的就是all(全部)、screen(屏幕)、print(页面打印或打印预览模式)

|   **值**   | **设备类型**                                     |
| :--------: | ------------------------------------------------ |
|    All     | 所有设备                                         |
|  Braille   | 盲人用点字法触觉回馈设备                         |
|  Embossed  | 盲文打印机                                       |
|  Handheld  | 便携设备                                         |
|   Print    | 打印用纸或打印预览视图                           |
| Projection | 各种投影设备                                     |
|   Screen   | 电脑显示器                                       |
|   Speech   | 语音或音频合成器                                 |
|     Tv     | 电视机类型设备                                   |
|    Tty     | 使用固定密度字母栅格的媒介，比如电传打字机和终端 |

##### media queries——媒体类型（二）

```
	<link rel="stylesheet" href="index.css" media='screen'>
	<link rel="stylesheet" href="index.css" media='Print'>
	<link rel="stylesheet" href="index.css" media='All'>
	
	@import url(index.css) all;
	@import url(index.css) screen;
	@import url(index.css) print;
	@media screen{
			body{
				background-color: rgba(255, 0, 0, .5);
			}
		}
	@media screen and (max-width: 600px) {
			@keyframes changeColor {
				from{background-color: white;}
				to{background-color: red;}
			}

			body{
				animation: changeColor 2s ease .2s infinite alternate;
			}
		}
	@media screen and (min-width: 1000px) {
			@keyframes changeColor{
				from{background-color: white}
				to{background-color: blue}
			}
			body{
				animation: changeColor 2s ease .2s infinite alternate;
			}
		}
	@media screen and (min-width: 601px) and (max-width: 999px) {
			@keyframes changeColor{
				from{background-color: white}
				to{background-color: yellow}
			}
			body{
				animation: changeColor 2s ease .2 infinite alternate;
			}
		} 
```

##### Responsive设计（一）

##### 1.流体网格

流体网格是一个简单的网格系统，这种网格设计参考了流体设计中的网格系统，将每个网格格子使用百分比单位来控制网格大小。这种网格系统最大的好处是让你的网格大小随时根据屏幕尺寸大小做出相对应的比例缩放。

##### 2.弹性图片

弹性图片指的是不给图片设置固定尺寸，而是根据流体网格进行缩放，用于适应各种网格的尺寸。而实现方法是比较简单，一句代码就能搞定的事情。

##### 3.媒体查询

媒体查询在CSS3中得到了强大的扩展。使用这个属性可以让你的设计根据用户终端设备适配对应的样式。这也是响应式设计中最为关键的。可以说Responsive设计离开了Medial Queries就失去了他生存的意义。简单的说媒体查询可以根据设备的尺寸，查询出适配的样式。Responsive设计最关注的就是：根据用户的使用设备的当前宽度，你的Web页面将加载一个备用的样式，实现特定的页面风格。

##### 4.屏幕分辨率

屏幕分辨简单点说就是用户显示器的分辨率，深一点说，屏幕分辨率指的是用户使用的设备浏览您的Web页面时的显示屏幕的分辨率，比如说智能手机浏览器、移动电脑浏览器、平板电脑浏览器和桌面浏览器的分辨率。Responsive设计利用Media Queries属性针对浏览器使用的分辨率来适配对应的CSS样式。因此屏幕分辨率在Responsive设计中是一个很重要的东西，因为只有知道Web页面要在哪种分辨率下显示何种效果，才能调用对应的样式。

##### 5.主要断点

主要断点，在Web开发中是一个新词，但对于Responsive设计中是一个很重要的一部分。简单的描述就是，设备宽度的临界点。在Media Queries中，其中媒体特性“min-width”和“max-width”对应的属性值就是响应式设计中的断点值。简单点说，就是使用主要断点和次要断点，创建媒体查询的条件。而每个断点会对应调用一个样式文件（或者样式代码）

##### Responsive布局技巧

##### 在Responsive布局中，可以毫无保留的丢弃：

第一， 尽量少用无关紧要的div；

第二，不要使用内联元素（inline）；

第三，尽量少用JS或flash；

第四，丢弃没用的绝对定位和浮动样式；

第五，摒弃任何冗余结构和不使用100%设置

##### 有哪些东东能帮助Responsive确定更好的布局呢

第一，使用HTML5 Doctype和相关指南；

第二，重置好你的样式（reset.css）；

第三，一个简单的有语义的核心布局；

第四，给重要的网页元素使用简单的技巧，比如导航菜单之类元素。

##### Responsive设计——meta标签

```
        <meta name='viewport' ="">
<meta name='viewport' content="width=device-width, initial-scale=1.0">
```

![	](http://img.mukewang.com/53660f2c0001190005270386.jpg)

##### Responsive设计——不同设备的分辨率设置

##### 1.1024px显屏

```
@media screen and (max-width: 1024px) {

}
```

##### 2.800px显屏

```
@media screen and (max-width: 800px) {

}
```

##### 3.640px显屏

```
@media screen and (max-width: 640px) {
	
}
```

##### 4.ipad横板显屏

```
@media screen and (max-device-width: 1024px) and (orientation: landscape) {

}
```

##### 5.ipad竖板显屏

```
@media screen and (max-device-width: 768px) and (orientation: portrait) {

}	
```

##### 6.iphone和Smartphones

```
@media screen and (min-device-width: 320px) and (max-device-width: 480px) {
	
}
```



```
	.wrapper{
		width: 100%;
		background: green;
		max-width: 980px;
		overflow: hidden;
		margin-left: auto;
		margin-right: auto;
	}
	.left{
		float: left;
		width: 20%;
		background: orange;
		min-height: 100px;
	}
	.content{
		float: right;
		width: 78%;
		background-color: blue;
		min-height: 100px;
	}
	@media (max-width: 800px) {
		.wrapper{
			min-width: 400px;
			width: 98%;
			margin-left: 1%;
			margin-right: 1%;
		}
		.left{
			float: none;
			width: 100%;
		}
		.content{
			float: none;
			width: 100%;
		}
	}
```

##### 自由缩放属性—resize

```
	div{
		width: 100px;
		height: 100px;
		background-color: red;
		overflow: hidden;
		resize: both;
	}

```

##### CSS3外轮廓属性—outline

```
	div{
		width: 100px;
		height: 100px;
		outline: 1px red solid;
	}

```

##### CSS生成内容—content

| **功能** | **功能说明**                                                 |
| -------- | ------------------------------------------------------------ |
| none     | 不生成任何内容                                               |
| attr     | 插入标签属性值                                               |
| url      | 使用指定的绝对或相对地址插入一个外部资源（图像，声频，视频或浏览器支持的其他任何资源） |
| string   | 插入字符串                                                   |