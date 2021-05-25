## JavaScript

### 什么是JavaScript
+ JavaScript是一种脚本，一门编程语言，它可以在网页上实现复杂的功能，网页展现给你的不再是简单的静态信息，而是实时的内容更新，交互式的地图，2D/3D动画，滚动播放的视频等等。
+ JavasCript分成三大部分：`ECMAScript、BOM、DOM`
+ 引入的两种方式：
```javascript
        // 1.外部js文件
    <script src="index.js"></script>
        // 2.内嵌,后面插入的script标签可以访问到前面的script标签的变量
    <script>
        var a = 123;
    </script>
```

### 基本语法
+ 变量声明规则
  - 变量名必须以英文名字、`_`、`$`开头
  - 变量名可以包括英文名字、`_`、`$`
  - 不能使用系统的关键字或保留字作为变量名
```javascript
    var _a;
    var $a;
    var a$;
    var a_;

    // 变量赋值
    好 = '帅';
    console.log(好);
    
    // 变量声明和变量赋值
    var a = 123;
    console.log(a);
```

+ 变量提升
```javascript
    console.log(a);
    var a = 123;
    console.log(a);
```

### 数据类型
+ 原始值（栈数据）：Number、String、Boolean、undefined、null，且原始值不可改变
```javascript
    var num = 123;  // number
    var str = '';   // string
    var bol = true; // Boolean
    var und = undefined;    // undefined

    // 原始值不可改变
    var a = 123;
    var b = a;
    a = 234;
    console.log(b);
    console.log(a);
```
+ 引用值（堆数据）：Array、Object、Function、data、RegExp
```javascript
    var arr = [];   // 数组
    var obj = {}    // 对象
    var data = new Date();  // 日期对象
    var reg = new RegExp(); // 正则

    // 引用值可以改变
    var arr = [1, 2, 3 4];
    var arr1 = arr;
    arr.push(5);
    console.log(arr);
    console.log(arr1);
```

### js计算运算符，自左向右计算
+ 加号运算符
  - 数字类型的值加上数据等于String类型
  - 数字类型的值加上undeinfed、NaN等于NaN（number类型）
  - 任何类型的值加上函数、正则、日期对象、字符串类型的值，等于拼接的值，等于拼接的值，数据除外（string类型）
  - 任何类型的数据值加上数组，都等于类型的值本身（string类型）

+ 减号运算符
  - NaN || undefined || function () {} || new RegExp() || {} 减去任何数据类型的值都为NaN，类型为number

### js比较运算符
+ 大于（>）、小于（<）、大于等于（>=）、小于等于（<=）、等于（==）、非等于（!=）、绝对等于（===）、绝对不等于（!==）
+ 字符串的比较，比的是ASCII码（七位二进制00000000）
+ false不等于null、undefined等于null、NaN不等于任何数
```javascript
     var a = "a" > "b";
	  var a = 1 > 2;
      var a = 1 < 2;
      var a = "1" < "8";
      var a = 1 > 2 > false;
      var a = 1 <  2 > false;

        a = undefined == null;	
        a = null < true;
        a = null < Infinity;
        a = false < true;	
        a = true < Infinity;
```

### js逻辑运算符，"&&"、"||"、"!"
+ &&（与）运算符：表达式从左往右开始排除，如果表达式中有假值就返回这个表达式的值，不会再往后面走，如果全是真值，就返回最后的一个值
```javascript
      var a = 1 && 2;
          a = 1 && 2 + 2; 
          a = 0 && 2 + 2;
          a = 1 && 1 && 8; 
```

+ ||（或）运算符：表达式中从左往右开始排除，如果有真值就返回这个表达式的值，不会再往后面看，如果是假值，就返回最后一个值
```javascript
    var num = 1 || 3;
    var num = 0 || 3;
    var num = 0 || false;
    var num = 0 || false || 1;
```
+ !运算符：先转换为布尔值再取反，假值有六个：`undefined、null、NaN、0、''、false`
```javascript
    var a = undefined || null || NaN || false || '' || 0
    var a = !123;
    var a = !'';
    var a = !!"";
    var a = true;  a != a; 
```

### if语句if、else if
```javascript
    var scroe = parseInt(window.prompt('input'));
    if(scroe > 90 && scroe <= 100) {
        console.log('优秀');
    }else if(scroe > 80 && scroe <= 90) {
        console.log('良好');
    }else if(scroe > 70 && scroe <= 80) {
        console.log('良');
    }else if(scroe > 60 && scroe <= 70) {
        console.log('及格');
    }else{
        console.log('你不是我教的');
    }
```

### for循环
```javascript
    var count = 0;
    for(var i = 0; i < 10; i ++) {
        count += i;
    }
    console.log(count);
```

### while循环
```javascript
    var i = 0;
    var count = 0;
    while(i < 10) {
        count += i;
        i ++;
    }
    console.log(count);
```

### switch分支语句
```javascript
    var date = window.prompt('input');
    switch(date) {
        case 'monday':
            console.log('working');
            break;
        case 'tuesday':
            console.log('working');
            break;
        case 'wednesday':
            console.log('working');
            break;
        case 'thursday':
            console.log('working');
            break;
        case 'friday':
            console.log('working');
            break;
        case 'Saturday':
            console.log('relaxing');
            break;
        case 'Sunday':
            console.log('relaxing');
            break;
        default: 
            console.log('working');
            break;
    }
```

### typeof类型检测，可以检测六种类型值
+ Number、string、boolean、undefined、object、function
```javascript
    var num = typeof 123;
        num = typeof '';
        num = typeof [];
        num = typeof undefined;
        num = typeof true;
        num = typeof function () {}
    console.log(num);
```

### 显示类型转换
+ 转换成Number类型：`Number()`
```javascript
    var num = Number('123');
        num = Number(true);
        num = Number(false);
        num = Number(null);
        num = Number(undefined);
        num = Number('abc');
        num = Number('123abc');
    console.log(num);
```

+ 把括号里面的数值转换成整数，number类型radix取值范围(2- 36), 把2进制作为radix转换为指定进制：`parseInt(string, radix)`
```javascript
    var num = parseInt('123');
        num = parseInt(true);
        num = parseInt(false);
        num = parseInt(123.9);
        num = parseInt(10, 16);
        num = parseInt(3, 2);
        num = parseInt('b', 16);
        num = parseInt('123abc');
        num = parseInt('100px');
    console.log(typeof num + "：" + num);
```

+ parseFloat从数字位开始从左往右排除，除了第一个点以外的非数字类位截止，返回前面的数：`parseIntFloat(string)`
```javascript
    var num = parseFloat('100.2');
        num = parseFloat('100.234');
        num = parseFloat('100.322.431');
        num = parseFloat('100.2abc');
    console.log(typeof num + '：' + num);
```

+  想把谁转换成字符，就写成target.toString(); 注：null和undefined没有toString方法
```javascript
    var demo = 123;
    var num = demo.toString(8);
    console.log(num);
```

+ 把里面的值转化成布尔值false或true：`Boolean()`
```javascript
    var num = Boolean('');
    var num = Boolean('123');
    console.log(typeof num + "：" + num);
```

+ 把括号里面的数放到Number转换出来再和NaN对比：`isNaN()`
```javascript
    console.log(isNaN(NaN));
    console.log(isNaN('123'));
    console.log(isNaN('abc'));
    console.log(isNaN(null));
    console.log(isNaN(undefined));
```

### 隐式类型转换
+ ++/--（加加减减）、+/-（一元正负）
+ 转换不成数字，也会转换成数字类型，因为里面隐式的调用了一个number
```javascript
    var a = '1';
        a ++;
        a --;
    console.log(a + '：' + typeof(a));
```

+ 加号（+）、乘号（*）、除号（/）
  - 当加号两侧有一个是字符串，就用调用string，把两个都变成字符串
  ```javascript
    var a = 'a' + 1;
    console.log(a + " : " + typeof a);
  ```
  - 乘（*）和模（%）都会转换成number
  ```javascript
    var a = '1' * 1;
        a = 'abc' * 1;
    console.log(typeof a + "：" + a);
  ```

+ 小于（<）、大于（>）、小于等于（<=）、大于等于（>=）
```javascript
    var a = 1 == '1';
        a = 1 == true;
        a = undefined == 0;
        a = undefined < 0;
        a = undefined > 0;
        a = null > 0;
        a = null < 0;
        a = null == 0;
        a = null == undefined;
        a = NaN == NaN;
        console.log(typeof a + " : " + a);
```

+ 不发生类型转换===（绝对等于）和!==（绝对不等于）
```javascript
   var a = 1 === "1";
        a = 1 === 1;
       a = 1 !== "1";
       a = NaN === NaN;
    console.log(typeof(a) + ' : ' + a);
```

### 函数
+ 函数名必须以英文名字、`_`、`$`开头
+ 函数名可以包括英文名字、`_`、`$`
+ 不能使用系统的关键字或保留字作为变量名
+ 普通函数使用小驼峰写法，构造函数使用大驼峰写法
```javascript
    function test() {}
    var test = function () {}
    var test = function test() {}
```
+ 组成形式：
  - 形参：指的是函数function sum(a, b) {} 括号里面的a和b
  - 实参：指的是调用时用的参数sum(1, 2);
  - 天生不定参，形参可以比实参多，实参可以比形参多
```javascript
    function sum(a, b) {
        var c = a + b;
    }
    sum(1, 2);
```

+ 函数中的arguments（实参列表）
```javascript
    function sum(a, b) {
        console.log(arguments);
        console.log(sum.length);
        console.log(arguments.length);
    }
    sum(1,2);
```

+ 实参和形参的映射关系
  - 实参和形参相同，相互影响
  ```javascript
    function test(a, b) {
        arguments[0] = 123;
        console.log(a);
        b = 1234;
        console.log(arguments[1]);
    } 
    test(1, 2);
  ```

  - 形参大于实参，不影响
  ```javascript
    function test(a, b) {
        arguments[1] = 3;
        console.log(b);
        b = 4;
        console.log(b);
    }
    test(1);
  ```

  - 返回值return有终止函数，返回数值的作用
  ```javascript
    function test() {
        return 123;
        console.log('a');
    }
    test();
  ```

+ 函数的作用域
 - 函数声明整体提升：函数不管写到哪里，都会被提到逻辑的最前面。所以不管在哪里调用，本质上都是在后面调用
 - 彼此独立的区间不能相互访问，里面的可以访问外面的变量，外面的不能用里面的变量
 - js运行三部分：语法解析 => 预编译 => 解释执行

+ 函数的预编译
 - 创建AO对象
 - 找形参和变量声明，将变量和形参名作为AO属性名，值为undefined
 - 将实参值和形参统一（把实参值传到形参里）
 - 在函数体里面找函数声明，值赋予函数体
 ```javascript
    test();
    function test(a, b) {
        console.log(a);
        c = 0;
        var c;
        a = 3;
        b = 2;
        console.log(b);
        function b() {}
        function d() {}
        console.log(b);
    }
    test(1);
 ```

 ```javascript
    function test(a, b) {
        console.log(a);
        console.log(b);
        var b = 234;
        console.log(b);
        a = 123;
        console.log(a);
        function a() {}
        var a;
        b = 234;
        var b = function () {}
        console.log(a);
        console.log(b);
    }
    test(1);
 ```

+ 全局的预编译
 - 生成了一个GO的对象window
 - 任何变量，如果变量未经声明就赋值，此变量就为全局对象（就是window）所有
 - 一切声明的全局变量，全是window的属性，window应是全局的域
 - 找形参和变量声明，将变量和形参名作为GO属性名，值为undefined
 - 在函数体里面找函数声明，值赋予函数体 
 ```javascript
    function test() {
        var a = b = 123;
        console.log(window.b);
    }
    test();
 ```

 ```javascript
    function test(test) {
        console.log(test);
        var test = 234;
        console.log(test);
        function test() {}
    }
    test(1);
    var test = 123;
 ```

 ```javascript
    global = 100;
    function fn() {
        console.log(global);
        global = 200;
        console.log(global);
        var global = 300;
    }
    fn();
    var global;
 ```

 ```javascript
    function test() {
        console.log(b);
        if(a) {
            var b = 100;
        }
        c = 234;
        console.log(c);
    }
    var a;
    test();
    a = 10;
    console.log(c);
 ```

 ```javascript
    function bar() {
        return foo;
        foo = 10;
        function foo() {}
        var foo = 11;
    }
    console.log(bar());

    console.log(bar());
    function bar() {
        foo = 10;
        function foo() {}
        var foo = 11;
        return foo;
    }
 ```

 ```javascript
    a = 100;
    function demo(e) {
        function e() {}
        arguments[0] = 2;
        console.log(e);
        if(a) {
            var b = 123;
            function c() {}
        }
        var c;
        a = 10;
        var a;
        console.log(b);
        f = 123;
        console.log(c);
        console.log(a);
    }
    var a;
    demo(1);
    console.log(a);
    console.log(f);
 ```

 ```javascript
    var str = false + 1;
    console.log(str);
    var demo = false == 1;
    console.log(demo);
    if(typeof a && -true + (undefined) + '') {
        console.log('基础扎实');
    }
    if(11 + '11' * 2 == 33) {
        console.log('基础扎实');
    }
    !!' ' + !!'' - !!false || console.log('你觉得能打印吗?');
 ```

 + 作用域精解
   - 每个javascript函数都是一个对象，对象中有些属性我们可以访问，但有些不可以，这些属性仅供javascript引擎存取，[[scope]]就是其中一个。[[scope]]指的就是我们所说的作用域，其中存储运行期上下文的集合。
   - 作用域链：[[scope]]中所存储的执行期上下文对象的集合，这个集合呈链式链接，我们把链式链接叫做作用域链。
   - 运行期上下文：当函数在执行的前一刻，会创建一个称为执行期上下文的内部对象。一个执行期上下文定义了一个函数执行时的环境，函数每次执行时对应的执行上下文都是独一无二的。所以多次调用一个函数会导致创建多个执行上下文，当函数执行完毕，执行上下文被销毁。
   - 查找变量：在哪个函数里面查找变量，就从哪个函数作用域链的顶端依次向下查找。函数类对象，我们能访问test.name
   ```javascript
    function a() {
        function b() {
            var bb = 234;
            aa = 0;
        }
        var aa = 123;
        b();
        console.log(aa);
    }
    var global = 100;
    a();
   ```
+ 闭包
  - 当内部函数被保存到外部时，将会生成闭包。闭包会导致原有的作用链不释放，造成内存泄露。
  ```javascript
    function a() {
        function b(){
            var bbb = 234;
            console.log(aaa);
        }
        var aaa = 123;
        return b;
    }
    var global = 100;
    var demo = a();
    demo();
  ```

  - 但凡是内部的函数被保存到外部，一定生成闭包
  ```javascript
    function a() {
        var num = 100;
        function b() {
            num ++;
            console.log(num);
        }
        return b;
    }
    var demo = a();
    demo();
    demo();
  ```

  - 在数组内打印10个函数，产生闭包
  ```javascript
    function test() {
        var arr = []
        for(var i = 0; i < 10; i ++) {
            arr[i] = function () {
                return i;
            }
        }
        return arr;
    }
    var myArr = test();
    for(var j = 0; j < 10; j ++) {
        console.log(myArr[j]);
    }
  ```

  - 解决方法
  ```javascript
    function test() {
        var arr = [];
        for(var i = 0; i < 10; i ++) {
            (function (j) {
                arr[j] = function () {
                    return j;
                }
            }(i))
        }
        return arr;
    } 
    var myArr = test();
    for(var j = 0; j < 10; j ++) {
        console.log(myArr[j]);
    }
  ```

  - 实现公有变量，函数累加器
  ```javascript
    function add() {
        var count = 0;
        function demo() {
            count ++;
            console.log(count);
        }
        return demo;
    }
    var myAdd = add();
    myAdd();
  ```

  - 可以用做缓存（存储结构）
  ```javascript
    function test() {
        var num = 100;
        function a() {
            num ++;
            console.log(num);
        }

        function b() {
            num --;
            console.log(num);
        }
        return [a, b];
    }
    var myArr = test();
    myArr[0]();
    myArr[1]();
  ```

  - 缓存的应用，对象里面可以用属性和方法
  ```javascript
    function eater() {
        var foo = '';
        var obj = {
            eat: function () {
                console.log('I am eating' + foo);
                foo = '';
            },
            push: function(myFoot) {
                foo = myFoot;
            }
        }
        return obj;
    }
    var eater1 = eater();
    eater1.push('banner');
    eater1.eat();
  ```

  - 属性私有化
  ```javascript
    function Peng() {
        var preparWife = 'xiaozhange';
        this.changePreparWife = function () {
            console.log(preparWife);
        }
    }
    var Peng = new Peng();
  ```

  - 防止污染全局，适用于模块化开发
  ```javascript
    var init = (function () {
        var name = 'abc';
        function callName() {
            console.log(name);
        }
        return function () {
            callName();
        }
    }());
  ```

+ 立即执行函数
  - 定义：此类函数没有声明，在一次执行过后即释放（被销毁）
  - 适合做初始化工作，针对初始化功能的函数
  - 只想让它执行一次的函数
  - 立即报告的函数也有参数，也有返回值，有预编译
  ```javascript
    (function () {} ())
    (function () {})()
    +function () {}()
    -function () {}()
    !function () {}()
    var test = function () {console.log('a');}()
  ```

+ 构造函数
  - 必须用new这个操作符，才能构造出对象
  - 构造函数必须要按照大驼峰式命名规则，但凡是构造函数就要大写
  ```javascript
    function Test() {}
    var test = new Test();
  ```

  - 每个构造函数构造出来都是独一无二的，函数名相同，但彼此独立
  ```javascript
    function Car() {
        this.name = 'BMW';
    }
    var car = new Car();
    var car1 = new Car();
    console.log(car === car1);
  ```

  - 在函数体最前面隐式的加上`var this = {}`空对象
  - 执行`this.xxx = xxx;`
  - 隐式的返回 `return this;`
  ```javascript
    function Student(name) {
        this.name = {
            ccc: 'b'
        }
    }
    var student = new Student({ccc: '22222'});
  ```

+ 原型
  - 原型是`function`对象的一个属性，它定义了构造函数制造出的对象的公共祖先。通过构造函数产生的对象，可以继承该原型的属性和方法，原型也是对象。
  ```javascript
    Person.prototype.name = 'hehe';
    function Person() {}
    var person = new Person();
    var person1 = new Person();
  ```

  - 利用原型特点和概念，可以提取共有属性
  ```javascript
    Car.prototype.carName = 'BMW';
    // 简写
    Car.prototype = {carName: 'BMW'}
    function Car() {this.carName = 'BMW'}
    var car = new Car();
  ```

  - 原型上属性增删改查：通过对象后代必原型链的属性是不行的，只会在当前对象修改属性，并新增一个属性
  ```javascript
    Person.prototype.lastName = 'Deng';
    function Person(name) {
        this.name = name;
    }
    var person = new Person('xuming');
    person.lastName = 'james';
  ```

  - 对象如何查看原型 ==> 隐式属性 __proto__
  ```javascript
    function Car() {}
    var car = new Car();
    console.log(Car.prototype);
    console.log(car.__proto__);
  ```

  - 对象如何查看对象的构造函数 ==> `constructor`
  ```javascript
    function Car() {}
    var car = new Car();
    console.log(car.constructor);
  ```

  - constructor可以被人工手动更改
  ```javascript
    var Person = function () {}
    Car.prototype = {
        constructor: Person
    }
    function Car() {}
    var car = new Car();
    console.log(car.constructor);
  ```
+ 原型链
  - 如何构成原型链
  ```javascript
    Grand.prototype.lastName = 'Deng';
    function Grand() {}
    var grand = new Grand();
    Father.prototype = grand;
    function Father() {}
    var father = new Father();
    Son.prototype =father;
    function Son() {}
    var son = new Son();
  ```

  - 原型链上属性的增删改查
  ```javascript
    Grand.prototype.lastName = 'Deng';
    function Grand() {}
    var grand = new Grand();
    Father.prototype = grand;
    function Father() {
        this.name = 'xuming';
        this.fortune = {
            card1: 'visa'
        }
    }
    var father = new Father();
    Son.prototype = father;
    function Son() {
        this.hobbit = 'smoke';
    }
    var son = new Son();
    son.fortune.card2 = 'master';
    console.log(son.fortune);
    console.log(father.fortune);
  ```

  - Object.create（原型）
  - 绝大多数对象最终都会继承自Object.prototype
  - Object.create()在括号里面只能放null或者Object，其余会报错
  ```javascript
    var obj = {name: 'sunny', age: 123};
    var obj1 = Object.create(obj);
    Person.prototype.name = 'sunny';
    function Person() {}
    var person = Object.create(Person);
    console.log(person.prototype);
    console.log(Person.prototype);
  ```

  - toString的重写
  ```javascript 
    Object.prototype.toString;
    Array.prototype.toString;
    Number.prototype.toString;
    String.prototype.toString;
    Boolean.prototype.toString;

    Number.prototype.toString = function () {
        return 1234;
    }
    ```

    - document.write会隐式的调用toString方法，其实打印的是toString的结果
    ```javascript
        var obj = Object.create(null);
        obj.toString = function () {
            return '13231';
        }
        document.write(obj);
    ```

    - arguments.callee指向函数的引用（函数自身）
    ```javascript
        function test() {
            console.log(arguments.callee);
            function a() {
                console.log(arguments.callee);
            }
            a();
        }
        test();
    ```

    - caller指谁调用的环境
    ```javascript
        function test() {
            demo();
        }

        function demo() {
            console.log(demo.caller);
        }
        test();
    ```

+ 继承的四种方式
    - 传统形式：原型链
    ```javascript
        Grand.prototype.lastName = 'Deng';
        function Grand() {}
        var grand = new Grand();
        Father.prototype = grand;
        function Father() {}
        var father = new Father();
        Son.prototype = father;
        function Son() {}
    ```

    - 借用构造函数，call、apply
    ```javascript
        function Person(name) {
            this.name = name;
        }
        function Student(sex) {
            this.sex = sex;
        }
        function inherit(name, sex) {
            Person.call(this, name);
            Student.apply(this, [sex]);
        }
        var inherit = new inherit('ppp', 'male');
    ```

    - 共享原型
    ```javascript
        Father.prototype.name = 'Deng';
        function Father() {}
        function Son() {}

        function inherit(Target, Orgin) {
            Target.prototype = Origin.prototype;
        }
        inherit(Son, Father);
        var father = new Father();
        var son = new Son();
    ```
      
    - 圣杯模式
    ```javascript
        function inherit(Target, Origin) {
            function F() {}
            F.prototype = Origin.prototype;
            Target.prototype = new F();
            Target.prototype.constructor = Target;
            Target.prototype.uber = Origin.prototype;
        }
        Father.prototype.name = 'Deng';
        function Father() {}
        function Son() {}
        inherit(Son, Father);
        var father = new Father();
        var son = new Son();
    ```

  


  
