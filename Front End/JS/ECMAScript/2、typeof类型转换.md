#### typeof类型检测，可以检测六种类型值
###### number、string、boolean、undefined、object、function

```
		var num = 123;   
        var num = NaN; 
        var num = Infinity; 

        var num = "";

        var num = {};   
        var num = [];   
        var num = null; 

        var num = undefined; 

        var num = function () {}
		console.log(typeof(num));
```
##### 显示类型转换
###### false || null || '' || []转换变成0
```
	    var num = Number('123');
        var num = Number(true);
        var num = Number(false);
        var num = Number(null);

        var num = Number(undefined);
        var num = Number('abc');
        var num = Number('123abc');

        var num = '-123';
        console.log(num);
```
##### parseInt(string, radix)	

###### 把括号里面的数值转换成整数，number类型radix取值范围(2- 36), 把2进制作为radix转换为指定进制

```
		var num = parseInt('123');
        var num = parseInt(true);
        var num = parseInt(false);
        var num = parseInt(123.9);
        var num = parseInt(10, 16);
        var num = parseInt(3, 2);
        var num = parseInt('b', 16);
        var num = parseInt('123abc');
        var num = parseInt('100px');
		
		console.log(typeof(num) + “ : ” + num);
```
##### parseIntFloat(string)转换成浮点数字，就是正常小数
###### parseFloat从数字位开始从左往右排除，除了第一个点以外的非数字类位截止，返回前面的数

```
		var num = parseFloat('100.2');
        var num = parseFloat('100.234');
        var num = parseFloat("100.322.431")
        var num = parseFloat('100.2abc')

		console.log( typeof(num) + " : " + num);
```
##### toString
###### 想把谁转换成字符串，就写成target.toString(); 注：null和undefined没有toString方法

```
		var demo = 123;
        var demo = undefined; 
        var demo = null;
        var num = demo.toString();
		console.log(num);
		
		var demo = 10;
        var num = demo.toString(8);
		console.log(num);
```
######  给你一个二进制的数，转换成十六进制，是先从二进制到十进制再到十六进制

```
	  var demo = 10000;
      var test = parseInt(demo, 2);
      var num = test.toString(16);

	  console.log(typeof(num) + " : " + num);
```
##### String(mix)，转换成字符串，写什么都成字符串


```
var num = String(1234);
var num = String(undefined);

console.log(typeof(num) + " : " + num);
```
##### Boolean()，把里面的值转化成布尔值false或true

```
var num = Boolean("");
var num = Boolean('213');

console.log(typeof(num) + " : " + num);
```
##### 隐式类型转换
###### 隐式类型转换包括isNaN(），++ ， --，+/-(一元正负)，+，*，%，&&，||，！，<，>，<=，>=，==，!=

##### isNaN()
###### isNaN把括号里面的数放到Number转换出来再和NaN对比

```
	  console.log(isNaN(NaN));
      console.log(isNaN('123'));
      console.log(isNaN('abc'));
      console.log(isNaN(null));
      console.log(isNaN(undefined));
```
##### ++/--（加加减减） +/-（一元正负）

###### 转换不成数字，也会转换成数字类型的，因为里面隐式的调用了一个number

```
var a = '123';
         a ++;
        a = 'abc';
        a ++; 
        console.log(a + " : " + typeof(a));

var a = +'abc';
console.log(a + " : " + typeof(a));       
```
##### 加号（+）、乘号（*）、除号（/）
###### 当加号两侧有一个是字符串，就用调用string，把两个都变成字符串

```
var a = 'a' + 1;
console.log(a + " : " + typeof(a));
```
*和% 乘和模都会转换成number

```
var a = '1' * 1;
var a = "abc" * 1;
console.log(typeof(a) + " : " + a);
```
###### < > <= >=

```
        var a = 1 == '1';
        var a = 1 == true;
        a = undefined == 0;
        a = undefined < 0;
        a = undefined > 0;
        a = null > 0;
        a = null < 0;
        a = null == 0;
        a = null == undefined;
        a = NaN == NaN;
        
		console.log(typeof(a) + " : " + a);
```
##### 不发生类型转换 ===（绝对等于 ）和绝对不等于(!= =)

```
	    var a = 1 === "1";
         a = 1 === 1;
         a = 1 !== "1";
         a = NaN === NaN;
		console.log(typeof(a) + ' : ' + a);
```
有一种特殊情况，当且仅当把未定义的变量放到console.log(typeof(a));里面就访问，不报错，返回undefined

```
console.log(typeof(a));
console.log(typeof typeof(a) + " : " +  typeof(a));
```
###### 练习

``` js
    a = isNaN('fdsa');
    a = isNaN(undefined);
    a = isNaN(NaN);
    a = isNaN(Infinity);
    alert(typeof (a));
    alert(typeof (undefined));
    alert(typeof (NaN));
    alert(typeof (null));
    var a = "123abc";
    alert(typeof (+a));
    alert(typeof (!!a));
    alert(typeof (a + ""));
    alert(1 == "1");
    alert(NaN == NaN);
    alert(NaN == undefined);
    alert("11" + 11);
    alert(1 === "1");
    alert(parseInt("123abc")); 
```