### dom结构树代表的是一系列的继承关系

![](https://img-blog.csdnimg.cn/20190213115110889.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hkcTE3NDU=,size_16,color_FFFFFF,t_70)

#### document——>HTMLDocument——>Document.prototype

```js
Document.prototype.abc = 'abc'
console.log(document.abc);
```

#### DOM基本操作

###### .getElementById方法定义在Document.prototype上，即Element节点上不能使用

###### getElementsByName方法定义在HTMLDocument.prototype上，即非html中的document以外不能使用(xml document,Element)

###### getElementsByTagName方法定义在HTMLDocument.prototype上，即非html中的document以外不能使用(xml document,Element)

##### HTMLDocument.prototype定义了一些常用的属性，body和head,分别指代HTML文档中的body、head标签

```
document.body
document.head
```

##### 6.getElementsByClassName、querySelectorAll、querySelector在Document,Element类中均有定义

##### 1.遍历元素节点树，要求不能用children属性（在原型链上编程）高级方法：打印树形结构

##### 2.封装函数，返回元素e的第n层祖先元素

##### 3.封装函数，返回元素e的第n个兄弟节点，n为正，返回后面的兄弟节点，n为负，返回前面的，n为0，返回自己。

##### 4.自己封装()方法，不可用children属性

#### DOM的增方法

##### document.createElement();增加或	元素节点

```js
var div = document.createElement('div');
```

##### document.createTextNode();  创建文本节点

```js
var text = document.createTextNode('134');
```

##### document.createComment(); 创建注释节点

```js
var comment = document.createComment('我是一个注释');
```

##### document.createDocumentFragment();  创建文档碎片节点

```js
var Fragment = document.createDocumentFragment('创建文档碎片节点');
```

#### DOM的插入方法—剪切操作，可以理解成push

##### appendChild    在元素中的最后面插入元素

```
          var div = document.createElement('div');
          document.body.appendChild(div);
          var text = document.createTextNode('我是一个文本节点');
          var comment = document.createComment('我是一个注释');
          var span = document.createElement('span');
          
          div.appendChild(text);
          div.appendChild(comment);
          div.appendChild(span);
```

##### insertBefore(a, b)    把元素插入到指定元素的前面

```
		var div = document.getElementsByTagName('div')[0];
        var span = document.getElementsByTagName('span')[0];
        var strong = document.createElement('strong');
        div.insertBefore(strong, span);
```

#### DOM的删除方法—剪切操作

##### removeChild()   剪切指定元素下的指定元素

```
		var div = document.getElementsByTagName('div')[0];
        var span = document.getElementsByTagName('span')[0];
        var strong = document.createElement('strong');
        var i = document.createElement('i');
        div.insertBefore(strong, span);
        div.insertBefore(i, strong);
        
        var i = div.removeChild(i);
```

##### remove()  删除自身

```
		var div = document.getElementsByTagName('div')[0];
        var span = document.getElementsByTagName('span')[0];
        var strong = document.createElement('strong');
        var i = document.createElement('i');
        div.insertBefore(strong, span);
        div.insertBefore(i, strong);
        
        var i = i.remove()
```

#### DOM的替换方法—用新的new去替换origin

##### replaceChild(new, origin)

```
		var div = document.getElementsByTagName('div')[0];
        var span = document.getElementsByTagName('span')[0];
        var strong = document.createElement('strong');
        var i = document.createElement('i');
        div.insertBefore(strong, span);
        div.insertBefore(i, strong);

        var p = document.createElement('p');
        div.replaceChild(p, strong);
```

#### Element节点的一些属性

##### innerHTML => 可读、可取、可写

```js
var div = document.getElementsByTagName('div')[0];
div.innerHTML = 12344;
```

##### innerText =>  可取，可赋值（老版本火狐不兼容）/textContent（ 火狐使用这个老版本IE不好使）

```js
var div = document.getElementsByTagName('div')[0];
div.innerText = '你好吗';
```

#### Element节点的一些方法

##### setAttribute()，设置属性值

```
#only{
      background-color: orange;
      font-size: 20px;
      color: white;
    }
<div> </div>
var div = document.getElementsByTagName('div')[0];
div.setAttribute('class', 'demo')
div.setAttribute('id', 'only');
```

##### 1、给三个标签，让他们行间有一个属性this-name

```
		var bodyChild = document.body.children;
        for(var i = 0, len = bodyChild.length; i < len; i ++) {
                  bodyChild[i].setAttribute('this-name', bodyChild[i].nodeName);
        }
```

##### 2、请编写一段JavaScript脚本生成下面这段DOM结构。要求：使用标准的DOM方法或属性

```
      <div class="example">
        <p class="slogan">你很帅</p>
      </div>
```

##### 3、封装函数insertAfter()；功能类似insertBefore();

##### 将目标节点内部的节点顺序，逆序

```
<div> <a></a><em></em></div>
```

#####  4、封装 remove(); 使得 child.remove()直接可以销毁自身 