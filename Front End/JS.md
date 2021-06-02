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

    - 深度克隆
    ```javascript
        function deepClone(origin, target) {
            var target = target || {},
                toStr = Object.prototype.toString,
                arrStr = '[Object Array]';
                for(var prop in origin) {
                    if(origin.hasOwnProperty(prop)) {
                        if(origin[prop] !== "null" && typeof origin[prop] === 'object') {
                            if(toStr.call(origin[prop]) === arrStr) {
                                target[prop] = [];
                            }else {
                                target[prop] = {}
                            }
                            deepClone(origin[prop], target[prop]);
                        }else {
                            target[prop] = origin[prop];
                        }
                    }
                }
            return target;
        }
    ```

### 数组
  + 定义
  ```javascript
    var arr = []
    var arr1 = new Array(6);
  ```

  + 数组的读和写：不可溢出读，可以溢出写
  ```javascript
    var arr = [1, 2];
    console.log(arr[2]);

    var arr = [1, 2];
        arr[2] = 3;
    console.log(arr);
  ```

  + 数组常用的方法
    - 可改变原数组
    - 反转：`reverse`
    - 在最后一位添加值：`push`
    - 把最后一位剪切出去：`pop`
    - 从第一位开始加值：`unshift`
    - 减掉开始第一位的值：`shift`
    - 从第几位开始，截取多少长度，添加新数据：`splice`
    - 给数组排序：`sort`
    ```javascript
        var arr = [1, 2, 3, 4, 5, 6];
        arr.reverse();
        arr.push(7);
        arr.pop();
        arr.unshift(-1, 0);
        arr.splice(6, 0, 7, 8, 9);

        arr.sort(function (a, b) {
            return a - b;
        });
    ```

    - 不改变原数组
    - 数组连接：`concat`
    - 把数组当做字符串展示：`toString`
    - 从该位开始截取，截取到该位：`slice`
    - 括号里面需要字符串，不使用就默认用逗号连接：`join`
    - 拆分方法：`split`
    ```javascript
        var arr = [1, 2, 3, 4, 5, 6];
        var arr1 = [7,8];
        var arr2 = arr.concat(arr1);
        console.log(arr2);

        var arr = [1, 2, 3, 4, 5, 6];
        var arr1 = arr.toString();
        console.log(arr1);

        var arr = [1, 2, 3, 4, 5, 6];
        var arr1 = arr.slice();
        var arr2 = arr.slice(3);
        var arr3 = arr.slice(3, 6);
        console.log(arr1);

        var arr = [1, 2, 3, 4, 5, 6];
        var arr1 = arr.join('-');
            arr2 = arr1.split('-');
            arr2 = arr1.split('4');
        console.log(arr2);
    ```

### 类数组
  + 可以利用属性名模拟数组的特性
  + 可以动态的增长legth属性
  + 如果强行让类数组调用push方法，则会根据length属性值的位置进行属性的扩充
  ```javascript
    function test() {
        console.log(arguments.length);
        arguments.push(7);
    }
    test(1, 2, 4, 5, 5);
  ```
  
  + 类数组的基本形态
  ```javascript
    var obj = {
        '0': 'a',
        '1': 'b',
        '2': 'c',
        length: 3,
        push: Array.prototype.push
    }
    obj.push('d');
  ```

  + 类数组的完整形态
  ```javascript
    var obj = {
        '0': 'a',
        '1': 'b',
        '2': 'c',
        length: 3,
        push: Array.prototype.push,
        splice: Array.prototype.splice
    }
    obj.push('d');
  ```

  + obj输出是？
  ```javascript
    var obj = {
        '2': 'a',
        '3': 'b',
        length: 2,
        push: Array.prototype.push
    }
    obj.push('c');
    obj.push('d');
    console.log(obj);
  ```

  + `forEach`方法：只能遍历数组，不能遍历类数组
  ```javascript
    var arr = [1, 2, 3, 4, 5];
    arr.forEach(function (value, index) {
        console.log(value);
        console.log(index);
    });
  ```

  + `map`方法：只能遍历数组，不能遍历类数组
  ```javascript
    var arr = [1, 2, 3, 4, 5];
    arr.map(function (value, index, array) {
        console.log(value);
        console.log(index);
        console.log(array);
    });
  ```

### this指向
  + 全局里的this指向window，即 this === window
  ```javascript
    var a = 1322;
    console.log(this.a);
    console.log(window.a);
    console.log(this === window);
  ```

  + 函数和立即执行函数里面的this指向window
  ```javascript
    function test() {
        this.a = 1234;
        console.log(this.a);
        console.log(window.a);
    }
    test();
    (function () {
        this.a = 123;
        console.log(this.a);
        console.log(window.a);
    }());
  ```

  + 构造函数里面的this，谁调用this就指向谁
  ```javascript
    Person.prototype = {
        name: 'BMW',
        sayName: function () {
            console.log(this.name);
        }
    }
    function Person() {
        this.name = 'Merze'
    }
    var person = new Person();
    console.log(person.sayName());
    connsole.log(Person.prototype.sayName());
  ```

  + 对象的this指向自身，谁调用this就指向谁
  ```javascript
    var obj = {
        name: function ()  {
            console.log(this);
        },
        age: 18,
        sayAge: function () {
            console.log(this.age);
        }
    }
  ```

### ES5
  + `try ...catch`
  + `try catch`正常执行，没有错误时catch里不会输入，如果发生错误会停止后面代码的运行，报错信息会传入到catch里面并且不影响try catch外面的代码
  ```javascript
    try{
        console.log('a');
        console.log('b');
        console.log('c');
    }catch(e) {
        console.log('e');
        console.log(e.name + " : " + e.message);
    }
    console.log('d');
  ```

  + 报错的六种值信息
    - eval()的使用与定义不一致：`eval()`
    - 数值越界：`RangeError`
    - 非法或不能识别的引用数值：`ReferenceError`
    - 发生语法解析错误：`SyntaxError`
    - 操作数类型错误：`TypeError`
    - URI处理函数使用不当：`URIError`

  + es5.0严格模式
    - es5.0严格模式是指es3.0和es5.0产生冲突部分就是用es5.0，否则应用es3.0,不再兼容es3的一些不规则语法。使用全新的es5规范。
    - 两种用法：全局严格模式，局部函数内严格模式（推荐）  
    ```javascript
        'use strict'
        function test() {
            console.log(arguments.callee);
        }
        test();
        function demo() {
            'use strict'
            console.log(arguments.callee);
        }
        demo();
    ```

  + with可以改变作用域链
    - 括号里面的代码会按照正常顺序执行，但是如果在括号里面添加了对象，就会把对象当做with要执行的代码体的作用域链的最顶端。es5语法不支持
    ```javascript
        var obj = {
            name: 'obj'
        }
        with(obj) {
            console.log(name);
        }
    ```
  
  + eval能把字符串当成代码来执行，不建议使用。eval是魔鬼，因为会改变作用域链
  ```javascript
    'use strict';
    var a = 123;
    eval('console.log()')
  ```  

  + es5.0严格模式中：变量赋值前必须声明，局部this必须被赋值，拒绝重复属性和参数
  ```javascript
    'use strict'
    function test() {
        var a = b = 123;
        console.log(this);
    }
    test();

    function test(name, name) {
        console.log(name);
    }
    test(1, 2);
  ```

### ES6
  + 块级作用域，用let的方式声明一个变量
  ```javascript
    if(true) {
        let a = 123;
        let b = 234;
    }
    console.log(a);
    console.log(b);
  ```

  + 恒量const，只能赋一次值！
  ```javascript
    const arr = []
    console.log(arr);
          arr = {}
  ```

  + 解构数组
  ```javascript
    function breakfast() {
        return ['apple', 'Tea', 'orange'];
    }
    var temp = breakfast(),
        dessert = temp[0],
        drink = temp[1],
        fruit = temp[2];
    console.log(dessert, drink, fruit);

    function breakfast() {
        return ['apple', 'Tea', 'orange'];
    }
    let [dessert, Tea, fruit] = breakfast();
    console.log(dessert, Tea, fruit);
  ```

  + 解构对象
  ```javascript
    function breakfast() {
        return {dessert: 'apple', drink: 'Tea', fruit: 'apple'}
    }
    let {dessert: dessert, drink: drink, fruit: fruit} = breakfast();

    function breakfast() {
        return {dessert: 'apple', drink: 'Tea', fruit: 'banner'}
    }
    let {dessert, drink, fruit} = breakfast();
    console.log(dessert, drink, fruit);
  ```

  + 模板字符串，字符串的连接
  ```javascript
    let dessert = 'apple';
        drink = 'tea';
    let breakfast = `今天的早餐是${dessert} 与 ${drink} !`;
    console.log(breakfast);
  ```

  + 带标签的模板字符串
  ```javascript
    let dessert = 'apple',
        drink = 'tea';
    let breakfast = kitchen`今天的早餐是${dessert} 与 ${drink} !`;

    function kitchen(strings, ...values) {
        console.log(strings);
        console.log(values);
        let result = '';
        for(var i = 0; i < values.length; i ++) {
            result += strings[i];
            result += values[i];
        }
        result += strings[strings.length - 1];
        return result;
    }
    console.log(breakfast);
  ```

  + 判断字符串里是不是以xxx开头的
  ```javascript
    let dessert = 'apple';
        drink = 'tea';
    let breakfast = `今天的早餐是 ${dessert} 与 ${drink} !`;
    console.log(breakfast.startsWith('今天'));
  ```

  + 判断字符串里不是不以xxx结尾的
  ```javascript
    let dessert = 'apple';
        drink = 'tea';
    let breakfast = `今天的早餐是 ${dessert} 与 ${drink} !`;
    console.log(breakfast.endsWith('tea !'));
  ```

  + 判断字符串里有没有xxx字符串
  ```javascript
    let dessert = 'apple';
    let drink = 'tea';
    let breakfast = `今天的早餐是 ${dessert} 与 ${drink} !`;
    console.log(breakfast.includes('apple'));
  ```

  + 函数的默认参数值
  ```javascript
    function breakfast(dessert = 'apple', drink = 'tea') {
        return `${dessert} ${drink}`;
    }
    console.log(breakfast());
  ```

  + 点点点（...）展开操作符
  ```js
    let fruits = ['apple', 'banner'];
    let foods = ['orange', ...fruits];
    console.log(fruits);
    console.log(...fruits);
    console.log(foods);
  ```

  + 点点点（...）操作符
  ```js
    function breakfast(dessert, drink, ...foods) {
        console.log(dessert, drink, ...foods);
    }
    breakfast('apple', 'tea', 'banner', 'orange');
  ```

  + 解构函数的参数对象
  ```js
    function breakfast(dessert, drink {location, restaurant} = {}) {
        console.log(dessert, drink, location, restaurant);
    }
    breakfast('apple', 'Milk', {location: '广东', restaurant: '董小姐'});
  ```

  + 箭头函数
  ```js
    let breakfast = dessert = dessert;
    let breakfast = (dessert, drink) => dessert + drink;
    let 
  ```

  + 对象表达式
  ```js
    let dessert = 'apple';
    let drink = 'tea';
    let food = {
        dessert,
        drink,
        breakfast() {
            return `${dessert} ${drink}`
        }
    }
    console.log(food);
    console.log(food.breakfast());
  ```

  + 对象两个值是否相等`Object.is()`
  ```js
    console.log(Object.is(NaN, NaN));
    console.log(Object.is(+0, -0));
    console.log(Object.is(null, undefined));
  ```

  + 把对象的值复制到另一个对象里
  ```js
    let breakfast = {}
    Object.assign(breakfast, {
        drink: 'tea'
    });
    console.log(breakfast);
  ```

  + 设置对象的prototype
  ```js
    let breakfast = {
        getDrink() {
            return 'tea'
        }
    }
    let dinner = {
        getDrink() {
            return 'beer'
        }
    }
    let sunday = Object.create(breakfast);
    console.log(sunday.getDrink());
    console.log(Object.getPrototypeOf(sunday) === breakfast);
    Object.setPrototypeOf(sunday, dinner);
    console.log(sunday.getDrink());
    console.log(Object.getPrototypeOf(sunday) === dinner);
  ```

  + __设置对象的proto__
  ```js
    let breakfast = {
        getDrink() {
            return 'tea'
        }
    }
    let dinner = {
        getDrink() {
            return 'beer'
        }
    }

    let sunday = {
        __proto__: breakfast
    }
    console.log(sunday.getDrink());
    console.log(Object.getPrototypeOf(sunday) === breakfast);
    sunday.__proto__ = dinner;
    console.log(sunday.getDrink());
    console.log(Object.getPrototypeOf(sunday) === dinner);
  ```

  + super
  ```js
    let breakfast = {
        getDrink() {
            return 'tea';
        }
    }
    let sunday = {
        __proto__: breakfast,
        getDrink() {
            return super.getDrink() + 'beer';
        }
    }
    console.log(sunday.getDrink());
    console.log(Object.getPrototypeOf(sunday) === breakfast);
  ```

  + 迭代器（Iterators）
  ```js
    function chef(foods) {
        let i = 0;
        return {
            next() {
                let done = (i >= foods.length);
                let value = !done ? foods[i ++ ] : undefined;
                return {
                    value,
                    done
                }
            }
        }
    }
    var wanghao = chef(['apple', 'orange']);
    console.log(wanghao.next());
    console.log(wanghao.next());
    console.log(wanghao.next());
  ```

  + 生成迭代器（Generators）
  ```js
    function* chef() {
        yield 'apple';
        yield 'banner';
    }
    let wanghao = chef();
    console.log(wanghao.next());
	console.log(wanghao.next());
	console.log(wanghao.next());
    function* chef(foods) {
        for(var i = 0; i < foods.length; i ++) {
            yield foods[i];
        }
    }
    let wanghao = chef(['apple', 'tea']);
    console.log(wanghao.next());
    console.log(wanghao.next());
    console.log(wanghao.next());
  ```

  + Class类
  ```js
    class Chef {
        constructor(food) {
            this.food = food;
        }
        cook() {
            console.log(this.food);
        }
    }
    let chef = new Chef('apple');
    chef.cook();
  ```

  + get与set
  ```js
    class Chef{
        constructor(food) {
            this.food = food;
            this.dish = []
        }
        get menu() {
            return this.dish;
        }
        set menu(dish) {
            this.dish.push(dish);
        }
        cook() {
            console.log(this.food);
        }
    }
    let chef = new Chef();
    console.log(chef.menu = 'tea');
    console.log(chef.menu = 'beer');
    console.log(chef.menu);
  ```

  + static
  ```js
    class Chef{
        static cook(food) {
            console.log(food);
        }
    }
    Chef.cook('apple');
  ```

  + 继承
  ```js
    class Person {
        constructor(name, birthday) {
            this.name = name;
            this.birthday = birthday
        }

        intro() {
            return `${this.name} ${this.birthday}`
        }
    }

    class Chef extends Person{
        constructor(name, birthday) {
            super(name, birthday);
        }
        intro() {
            return `${this.name} ${this.birthday}`
        }
    }

    class Chef extends Person{
        constructor(name, birthday) {
            super(name, birthday);
        }
    }
    let chef = new Chef('ppp', '1998-10-29');
    console.log(chef.intro());
  ```

  + Set
  ```js
    let dessert = new Set();
    console.log(dessert);
    dessesrt.add('apple');
    dessert.add('tea');
    console.log(dessert);
    console.log(dessert.size);
    console.log(dessert.has('apple'));
    dessert.delete('apple');
    console.log(dessert);
    dessert.forEach(dessert => {
        console.log(dessert);
    });
    dessert.clear();
    console.log(dessert);
  ```

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
+ 鼠标点击某个对象：`onclick`
+ 获取焦点：`onfocus`
+ 失去焦点：`onblus`
+ 鼠标被按下：`onmousedown`

### flash和js通过什么类如何交互？
+ Flash提供了ExternalInterface接口与JavaScript通信，ExternalInterface有两个方法，call和addCallback，call的作用是让Flash调用js里的方法，addCallback是用来注册flash函数让js调用

### Flash与Ajax各自的优缺点？
+ Flash：适合处理多媒体、矢量图形、访问机器。但对CSS、处理文本不足，不容易被搜索。
+ Ajax：对CSS、文本支持很好，但对多媒体、矢量图形、访问机器不足

### 有效的JavaScript变量定义规则
+ 第一个字符必须是一个字母、下划线（_）或一个美元符号（$）;其它字符可以是字母、下划线、美元字符或数字。

### XML与JSON的区别？
+ 数据体积方面。JSON相对XML来讲，数据的体积更小，传递的速度更快些。
+ 数据交互方面。JSON与JavaScript的交互更加方便，更容易解析处理，更好的数据交互
+ 数据描述方面。JSON对数据的描述性比XML较差
+ 传输速度方面。JSON的速度要远远快于XML

### HTML与XML的区别？
+ XML用来传输和存储数据，HTML用来显示数据
+ XML使用的标签不用预先定义
+ XML标签必须成对出现
+ XML对大小写敏感
+ XML中空格不会被删减
+ XML中所有特殊符号必须用编码表示
+ XML中的图片必须有文字说明

### 渐进增加与优雅降级
+ 渐进增强：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进，达到更好的用户体验。
+ 优雅降级：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容

### Web Worker和Web Socket？
+ Web Socket：在一个单独的持久连接上提供全双工、双向的通信。使用自定义的协议，同源策略对Web socket不适用。
+ Web worker：运行在后台的JavaScript，不影响页面的性能。
+ 创建worker：var worker = new Worker(url);
+ 向worker发送数据：worker.postMessage(data);
+ 接收worker返回的数据：worker.onmessage;
+ 终止一个worker的执行：worker.terminate();

### Js垃圾回收机制？
+ 标记清除：这个算法把"对象"是否不再需要"简化定义为"对象是否可以获得。假定设置一个叫做根的对象。定期的，垃圾回收器将从根开始，找所有从根开始引用的对象，然后找这些对象引用的对象。从根开始，垃圾回收器将找到所有可以获得的对象和所有不能获得的对象。
+ 引用计数：此算法把"对象是否不再需要"简化定义为"对象有没有其它对象引用到它。如果没有引用引用指向该对象（零引用），对象将被垃圾回收机制回收。该算法有个限制：无法处理循环引用。两个对象被创建，并互相引用，形成了一个循环。它们被调用之后不会离开函数作用域，所以它们已经没有用了，可以被回收了。然而，引用计数算法考虑到它们互相都有至少一次引用，所以它们兴会被回收

### web应用从服务器主动推送data到客户端的方式？
+ JavaScript数据推送：commet（基于http长连接的服务器推送技术）。基于web socket的推送：SSE（server-send Event）

### 如何删除一个cookie？
+ 将cookie的失效时间设置为过去的时间
```js
    document.cookie = 'user='+ encodeURIComponent('name') + ';expires='+ new Date(0);
```
+ 将系统时间设置为当前时间往前一点
```js
    var data = new Date();
    date.setDate(date.getDate()-1);
```

### attribute与property的区别？
+ attribute是dom元素在文档中作为html标签拥有的属性
+ property是dom元素在js中作为对象拥有的属性。
+ 所以，对于html的标准属性来说，attribute和property是同步的，是会自动更新的。但对于定义属性，他们不同步。

### Ajax请求的页面历史记录状态问题
+ 通过location.hash记录状态，让浏览器记录Ajax请求时页面状态的变化
+ 通过HTML5的history.pushstate，来实现浏览器地址栏的无刷新改变








  
