#### Date对象

##### getTime() => 记录当前创建的时间

```js
        var firstTime = new Date();
        for(var i = 0; i < 100000000; i ++) {}
        var lastTime = new Date();
        console.log(lastTime - firstTime);
```

##### 封装函数，打印当前是何年何月何日何时，几分几秒。

```js
function myData() {
            var  data = new Date();
            var month = data.getMonth();
            return data.getFullYear() + '年' +  ++ month  + '月' + data.getDate() + '日' + data.getHours() + '时' + data.getMinutes() + '分' + data.getSeconds() + '秒';
}
            
```

#### js定时器

##### setInterval(function() {}, 1000);定时器，意思是1000毫秒执行一次这个函数

```js
var timer = 1000;
setInterval(function () {
          console.log('a');
}, timer);
```

##### 测试定时器到底准不准

```js
var firstTime = new Date().getTime();
        setInterval(function() {
          var lastTime = new Date().getTime();
          console.log(lastTime - firstTime);
          firstTime = lastTime;

}, 1000)
```

##### clearInterval();终止

``` js
		var i = 0;
        var timer = setInterval(function () {
          console.log(i ++);
          if(i > 10) {
            clearInterval(timer);
          }
        }, 10)
```

##### setTimeout();正真的定时器,隔了一段时间后再执行（起推迟作用），并且只执行一次

```js
setTimeout(function () {
          console.log('a');
        }, 1000)
```

##### clearTimeout();清除setTimeout();让他停止执行

```
var timer = setTimeout(function () {
        		console.log('a');
            }, 1000) 
clearTimeout(timer);
```

##### setInterval();setTimeout();clearInterval();clearTimeout();这四个都是全局对象，都是window上的方法，内部函数this指向window

```js
setInterval('console.log("a")', 1000);
```

##### 计时器，到三分钟停止