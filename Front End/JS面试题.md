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
JSO中对象通过{}来标识，一个{}代表一个对象，如{"Areald: "}










