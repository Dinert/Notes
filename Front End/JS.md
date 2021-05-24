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






  
