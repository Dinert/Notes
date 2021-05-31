### jQuery使用建议
+ 尽量减少对dom元素的访问和操作
+ 尽量避免给dom元素绑定多个相同类型的事件处理函数，可以将多个相同类型事件处理函数合并到一个处理函数，通过数据状态来处理分支
+ 尽量避免使用toggle事件

### Ajax使用
+ 异步，就是向服务器发送请求的时候，我们不必等待结果，而是可以同时做其它的事情，等到有了结果它自己会根据设定进行后续操作，与此同时，页面是不会发生整页刷新的，提高了用户体验。
```js
    var xhr = new XMLHttpRequest(); // 创建异步调用对象
    xhr.open('get', 'aaa.php', false);  // 创建Http请求（方法、URL、是否异步）
    xhr.onreadystatechange = getData;                 //  设置响应HTTP请求状态变化的函数
    xhr.send(data); // 发送http请求
```
+ 页面初次加载时，尽量在web服务器一次性输出所有相关的数据，只有在页面加载完成之后中，用户进行操作时采用ajax进行交互。
+ 同步ajax在IE上会产生页面假死的问题，所以建议采用异步ajax
+ 尽量减少ajax请求次数
+ ajax安全问题，对于敏感数据在服务器端处理，避免在客户端处理过滤。对于关键业务逻辑代码也必须放在服务端处理。


### JavaScript有几种类型的值？你能画一下他们的内存图吗？
+ 基本数据类型存储在栈中，引用数据类型（对象）存储在堆中，指针放在栈中
+ 原始数据类型直接存储在栈中的简单数据段，占据空间小，大小固定，属性被频繁使用数据，所有放入栈中存储
+ 引用数据类型存储在堆中的对象，占据空间大、大小不固定，如果存储在栈中，将会影响程序运行的性能
+ 引用数据类型在栈中存储了指针，该指针指向堆中该实体的起始地址，当解释器寻找引用值时，会首先检索其在栈中的地址，取得地址后从堆中获得实体。

### 栈和堆的区别？
+ 栈：由编译器自动分配释放，存放函数的参数值，局部变量等。
+ 堆：一般由程序员分配释放，若程序员不释放，程序结束时可能由操作系统释放。

### JavaScript创建对象的几种方式
```js
    var obj = {}
    var obj = new Object();
```

### JavaScript实现继承的几种方式
+ 原型链
```js
    Grand.prototype.lastName = 'Deng';
    function Grand() {}
    var grand = new Grand();
    Father.prototype = grand;
    function Father() {}
    var father = new Father();
    Son.prototype = father;
    function Son() {}
```

+ 借用构造函数，call、apply
```js
    function Person(name) {
        this.name = name;
    }
    function Student(sex) {
        this.sex = sex;
    }
    function Inherit(name, sex) {
        Person.call(this, name);
        Student.apply(this, [sex]);
    }
    var inherit = new Inherit('ppp', 'male');
```

+ 共享原型
```js
    Father.prototype.name = 'Deng';
    function Father() {}
    function Son() {}
    function Inherit(Target, Origin) {
        Target.prototype = Origin.prototype;
    }
    inherit(Son, Father);
    var father = new Father();
    var son = new Son();
```

+ 圣杯模式
```js
    function Inherit(Target, Origin) {
        function F() {}
        F.prototype = Origin.prototype;
        Target.prototype = new F();
        Target.prototype.constructor = Target;
        Target.prototype.uber = Origin.prototype;
    }
    Father.prototype.name = 'Deng';
    function Father() {}
    function Son() {}
    Inherit(Son, Father);
    var father = new Father();
    var son = new Son();
```

### JavaScript作用域链
+ 作用域链的原理和原型链很类似，如果这个变量在自己的作用域中没有，那么它会寻找父级的，直到最顶层。
+ 注意：Js没有块级作用域，若要形成块级作用域，可通过`(function () {}())`立即执行的形式实现

### 谈谈this的理解
+ 全局的`this`指向`window`,即`this === window`
+ 函数和立即执行函数里的`this`指向`window`
+ 构造函数里面的`this`，谁调用`this`就指向谁
+ 对象里的`this`指自身，谁调用`this`就指向谁

### eval是做什么的
+ 它的功能是把对应的字符串解析成JS代码并运行。
+ 避免使用eval，不安全，非常耗性能（2次，一次解析成js语句，一次执行）。

### 什么是window对象？什么是document对象
+ window对象代表浏览器中打开的一个窗口。document对象代表整个html文档。实际上，document对象是window对象的一个属性。

### null，undefined的区别
+ `null`表示一个对象被定义了，但存放了空指针，转换为数值时为0
+ `undefined`表示声明的变量未初始化，转换为数值时为`NaN`

### 关于事件，IE与火狐的事件机制有什么区别？如何阻止冒泡
+ IE为事件冒泡，Firefox同时支持事件捕获和事件冒泡。但并非所有浏览器都支持事件捕获。jQuery中使用`event.stopPropagation()`方法可阻止冒泡;旧IE`event.cacelBubble = true`

### 什么是闭包，为什么要用它？
+ 闭包指的是一个函数可以访问另一个函数作用域中变量。常见的构造方法，是在一个函数内部定义另外一个函数。内部函数可以引用外层的变量。外层变量不会被垃圾回收机制回收
+ 优点：避免全局变量污染，缺点：容易造成内存泄漏
```js
    function makeFunc() {
        var name = 0;
        function displayName() {
            name ++;
            console.log(name);
        }
        return displayName;
    }
    var myFunc = makeFunc();
    myFunc();
    myFunc();
```

### JavaScript代码中的`use strict`是什么意思？使用它区别什么？
+ 严格模式
+ 消除js不合理，不严谨的地方，减少怪异行为
+ 消除代码不运行的不安全之处
+ 提高编译器的效率，增加运行速度
+ 为未来的js新版本做铺垫

### 如何判断一个对象是否属于某个类
`A instance Object`

### new 操作符具体干了什么呢？
+ 创建一个空对象，并且`this`变量引用该对象，同时还继承了该对象的原型
+ 属性和方法被加入到`this`引用的对象中
+ 新创建的对象由`this`所引用，并且最后隐式的返回`this`

### JavaScript中，执行对象查找时，永远不会去查找原型的函数？
+ Object.hasOwnProperty(proName)：是用来判断一个对象是否有你给出名称的属性。不过需要注意的是，此方法无法检查该对象的原型链中是否具有该属性，该属性必须是对象本身的一个成员。

### 对JSON的了解
+ JSO中对象通过{}来标识，一个{}代表一个对象，如{"Areald": "123"}，对象的值是键值对的形式(key: value).JSON是js的一个严格的子集，一种轻量级的数据交换格式，类似于xml。数据格式简单易于读写，占用带宽小。
+ 解析JSON字符串把JSON字符串变成JavaScript值或对象：`JSON.parse(obj)`
+ 将一个JavaScript值（对象或者数组）转换为一个JSON字符串：`JSON.stringify(obj)`

### JS延迟加载的方式有哪些？
+ 延迟脚本。立即下载，但延迟执行（延迟到整个页面都解析完毕后再运行），按照脚本出现的先后顺序执行：`defer`
+ 异步脚本。下载完立即执行，但不保证按照脚本出现的先后顺序执行。：`async`

### 同步和异步的区别
+ 同步的概念在操作系统中：不同进程协同完成某项工作而先后次序调整（通过阻塞、唤醒等方式），同步强调的是顺序性，谁先谁后。异步不存在顺序性
+ 同步：浏览器访问服务器，用户看到页面刷新，重新发请求，等请求完，页面刷新，新内容出现，用户看到新内容之后进行下一步操作。
+ 异步：浏览器访问服务器请求，用户正常操作，浏览器在后端进行请求。等请求完。页面刷新，新内容也会出现，用户看到新内容。

### 什么是跨域问题，如何解决跨域问题？
+ 跨域是指一个域下的文档或脚本去试图去请求另一个域下的资源，这里跨域是广义的。

### 页面编码和被请求的资源编码如果不致如何处理？
+ 若请求的资源编码，如外引js文件编码与页面编码不同。可根据外引资源编码方式定义为charset="utf-8"或"gbk"。

### 模块化开发怎么做？
+ 模块化开发指的是在解决某一个复杂问题或者一系列问题时，依照一种分类的思维把问题进行系统性的分解。模块化是一种将复杂系统分解为代码结构更合理，可维护性更高的模块方式。对于软件行业：系统被分解为一组高内聚，低耦合的模块。
+ 定义封装的模块
+ 定义新模块对其它模块的依赖
+ 可对其它模块的引入支持。在JavaScript中出现了一些非传统模块开发方式的规范。CommonJs、AMD、CMD等。AMD是异步模块定义，所有的模块将被异步加载，模块加载不影响后边语句运行。

### AMD、CMD规范区别
+ AMD是RequireJs在推广过程中对模块定义的规范化产出。CMD是SeaJS在推广过程中对模块定义的规范化产出。
+ 对于依赖的模块，AMD是提前执行，CMD是延迟执行。不过RequireJS从2.0开始，也改成可以延迟执行（根据写法不同，处理方式不同）
+ CMD推崇依赖就近，AMD推崇依赖前置。
+ AMD的API默认是一个当多个用，CMD的API严格区分，推崇职责单一。
```js
    // CMD
    define(function (require, exports, module) {
        var a = require('./a');
        a.doSomethin();
        var b = require('./b');
        b.doSomething();
    });

    // AMD
    defind(['./a', './b'], function (a, b) {    // 依赖必须一开始就写好
        a.doSomething();
        b.doSomething();
    });
```

### requireJS的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何缓存的？）
+ 核心是js的加载模块，通过正则匹配模块以及模块的依赖关系，保证文件加载的先后顺序，根据文件的路径对加载过的文件做了缓存。

### call和apply
+ call（）方法和apply（）方法的作用相同，改变this指向，区别在于接收参数的方式不同。call传递的参数必须逐个列举出来，apply（）时，传递给函数的是参数数组。

### 谈一谈你对ECMAScript6的了解

### document.write和innerHTML的区别
+ document.write()重绘整个页面，innertHTML重绘页面的一部分

### 回流与重绘
+ 当渲染树中的一部分（或全部）因为元素的规模尺寸，布局，隐藏等改变而需要重新构建。这就称为回流(reflow)。每个页面至少需要一次回流，就是在页面第一次加载的时候。在回流的时候，浏览器会使渲染树中受到影响的部分失效，并重新构造这部分渲染树。完成回流后，浏览器会重新绘制受影响的部分到屏幕中，该过程称为重绘。

### DOM操作
+ 创建新节点
```js
    createDocumentFragment(); // 创建一个DOM片段
    createElement();    // 创建一个具体的元素
    createTextNode();   // 创建一个文本节点
```
+ 添加、移除、替换、插入
```js
    appendChild();
    removeChild();
    replaceChild();
    insertBefore(); // 在已有的子节点前插入一个新的子节点
```

+ 查找
```js
    getElementsByTagName();   // 通过标签名称
    getElementsByName();    // 通过元素的Name属性值
    getElementById();   // 通过元素ID，唯一性
```

### 数组对象有哪些原生方法，列举一下
+ `pop`、`push`、`shift`、`unshift`、`splice`、`reverse`、`sort`、`concat`、`join`、`slice`、`toString`、`indexOf`、`lastIndexOf`、`reduce`、`reduceRight`、`forEach`、`map`、`filter`、`every`、`some`

### 哪些操作会造成内存泄漏
+ 全局变量、闭包、DOM清空或删除时、事件未清除、子元素存在引用

### 什么是Cookie隔离？
+ 通过使用多个非主要域名来请求静态文件，如果静态文件都放在主哉名下，那静态文件请求的时候带有的cookie的数据提交给server是非常浪费的，还不如隔离开。因为cookie有域的限制，因为不能跨域提交请求，故使用非主要域名的时候，请求头中就不会带有cookie数据，这样可以降低请求头的大小，降低请求时间，从而达到降低整体请求延时的目的。同时这种方式不会将cookie传入server，也减少了server对cookie的处理分析环节，提高了server的http请求的解析速度。

### 响应事件











