### this

##### 全局里的this指向window,即 this == window

```
    var a = 1322;
    console.log(this.a);
    console.log(window.a);
    console.log(this === window);
```

##### 函数和立即执行函数里面的this指向window

```js 
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
			}())
```

##### 构造函数里面的this，谁调用this就指向谁

```
			Person.prototype = {
				name: 'BMW',
				sayName: function () {
					console.log(this.name);
					console.log(this);
				}
			}
			function Person() {
				this.name = 'Merze'
			}
			var person = new Person();
			console.log(person.sayName())
			console.log(Person.prototype.sayName())
```

##### 对象的this指向自身，谁调用this就指向谁

```
			var obj = {
				name: function () {
					console.log(this);
				},
				age: 18,
				sayAge: function () {
					console.log(this.age);
				}
			}
```

##### 例

```
var name = '222';
        var a = {
          name: '111',
          say: function () {
            console.log(this.name);
          }
        }
        var fun = a.say;
        fun();
        a.say();

        var b = {
          name: '333',
          say: function(fun) {
            fun();
          }
        }
        b.say(a.say);
        b.say = a.say;
        b.say();
```

