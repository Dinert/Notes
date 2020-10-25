# Jquery原理

#### jQuery的基本结构

```
	    // jQuery的原理
        // 1.jQuery的本质是一个闭包，立即执行函数
        // 2.jQuery为什么要使用闭包来实现
            // 为了避免多个框架的冲突
        // 3.jQuery如何让外界访问内部定义的变量     
            // window.xxx = xxx
        // 4.jQuery为什么要给自己传递一个参数
            // 为了方便后期压缩代码
            // 为了提升查找的效率
        // 5.jQuery为什么要给自己接收一个undefined参数 
            // 为了方便后期压缩代码
            // IE9以下的浏览器undefined可以被修改，为了保证内部使用的undefined不被修改，所以需要接收一个正确的undefined
        (function (window, undefined) {
                var njQuery = function () {
                    return new njQuery.prototype.init()
                }
                njQuery.prototype = {
                    constructor: njQuery
                }
                njQuery.prototype.init.prototype = njQuery.prototype; 
                window.njQuery = window.$ = njQuery
        })(window)
```

#### jQuery的入口函数测试

```
    // 传入 null "" null undefined NaN 0 false
    // 返回空的jQuery对象
    // console.log($())
    // console.log($(''))
    // console.log($(null))
    // console.log($(undefined))
    // console.log($(NaN))
    // console.log($(0))
    // console.log($(false))

    // 2传入html片段
    // 会将创建好的DOM元素存储到jQuery对象中返回
    // console.log($('<p>1</p><p>2</p><p>3</p>'))

    // 3传入选择器
    // 将会找到指定元素存储到jQuery对象中返回
    // console.log($('li'))

    // 4传入数组
    // 会将数组依次存储到jQuery对象中返回
    // console.log($([1, 2, 3, 4, 5]))

    // 5传入伪数组
    // var arr2 = {0: 'a', 1: 'b', 2: 'c', length: 3}
    // console.log($(arr2))

    // 6传入对象
    // var obj = {name: 'ppp', age: '18'}
    // console.log($(obj))

    // 7传入函数
    // function Person() {}
    // console.log($(Person))
    // console.log($(new Person));

    // 8传入DOM元素
    // console.log($(document.createElement('ul')))

    // 9传入基本的数据类型
    // console.log($(123))
    // console.log($(true))
    // console.log($('str'))
    
    
     // jQuery原型上的核心方法和属性
    // 1、jquery 获取版本号
    // 2、selector 实例默认的选择器取值
    // 3、length 实例默认的长度
    // 4、push 给实例添加新元素
    // 5、sort 对实例中的元素进行排序
    // 6、按照指定下标指定数量删除元素，也可以替换删除元素
    // 6、toArray 把实例转换为数组返回
    // 7、get 获取指定下标的元素，获取的是原生DOM

    // 8、eq获取指定下标的元素，获取的是jQuery类型的实例对象
    // console.log($('div').eq(0))
    // 9、first获取实例的第一个元素，是jQuery类型的实例对象
    // console.log($('div').first())
    // 10、last获取实例的最后一个元素，是jQuery类型的实例对象
    // console.log($('div').last())

    // 11、each遍历实例，把遍历到的数据传给回调使用
    // var arr = [1, 3, 5, 7, 9]
    // var obj1 = {'0': 'a', '1': 'b', '2': 'c', length: 3}
    // var obj2 = {name: 'pppp', 'age': 22}
    // njQuery.each(arr, function (key, value) {
        
    //     console.log(key, value) 
    //     console.log(this)
    // })
    // $(arr).each(function (key, value) {
    //     console.log(key, value)
    // })
    // 12、map 遍历实例，把遍历到的数据传给回调使用，然后把回调的返回值
    // var res =njQuery.map(arr, function (value, key) {
    //     if(key === 2) {
    //         return value;
    //     }
    // })
    // console.log(res)
    
    // DOM操作:
    // empty ===> 清空指定元素中的所有内容
    // remove ==> 删除所有的元素或指定元素
    // html  ==> 设置所有元素的内容,获取第一个元素的内容
    // text ==> 设置所有元素的文本内容,获取所有元素的文本内容
    // appendTo ==> 将元素添加到指定元素内部的最后
    // append ==> 将元素添加到指定元素内部的最后
    // prependTo ==> 将元素添加到指定元素内部的最前面
    // prepend ==> 将元素添加到指定元素内部的最前面
    // insertAfter ==> 将元素添加到指定元素外部的后面
    // after ==> 将元素添加到指定元素外部的后面
    // insertBefore ==> 将元素添加到指定元素外部的前面
    // before ==> 将元素添加到指定元素外部的前面 
    // replaceAll ==> 将新的指定元素替换为指定元素
    //replaceWith ==> 将指定元素替换为新的指定元素
    
    // 属性操作:
    // attr() 设置或者获取元素的属性节点值
    // prop() 设置或者获取元素的属性值
    // css() 设置获取样式
    // val()  获取设置value的值
    // hasClass() 判断元素中是否包含指定类
    // addClass() 给元素添加一个或多个指定的类
    // removeClass() 删除元素中一个或多个指定的类
    // toggleClass() 有则删除,没有则添加
   
    // on绑定事件
    // 指定元素绑定多个相同类型的件事件或者多个不同类型的事件，先按不同类型的事件顺序触发，再按绑定的先后顺序。
    // var btn = document.getElementsByTagName('button')[0];
    // off移除事件
    // 不传参，移除指定元素所有类型的事件
    // 传递两个参数，移除指定元素指定类型的事件
```

####    代码片段实现

```
(function (window, undefined) {
    var pjQuery = function (selector) {
        return new pjQuery.prototype.init(selector);
    }
    pjQuery.prototype = {
        constructor: pjQuery,
        // 代码片段类型处理
        init: function (selector) {
            if(!selector) {
                return this
            }else if(typeof(selector) === 'string') {
                if(selector.charAt(0) === '<' && selector.charAt(selector.length - 1) === '>' && selector.length >= '3') {
                    // 创建一个节点
                    var temp = document.createElement('div');
                    // 把节点放到div中
                    temp.innerHTML = selector;
                    [].push.apply(this, temp.children)
                    return this;
                }
            }
        }
    }
    pjQuery.prototype.init.prototype = pjQuery.prototype
    window.pjQuery = window.$ = pjQuery
})(window)
```

#### 工具方法抽取

```
(function (window, undefined) {
    var pjQuery = function (selector) {
        return new pjQuery.prototype.init(selector);
    }
    pjQuery.prototype = {
        constructor: pjQuery,
        // 代码片段类型处理
        init: function (selector) {

            // 解决代码片断开头和结尾有没有空格
            selector = pjQuery.trim(selector)
            // 判断传入的值是不是错误的
            if(!selector) {
                return this
            }else if(pjQuery.isString(selector)) {
                if(pjQuery.isHTML(selector)) {
                    // 创建一个节点，把所有的DOM元素放进去
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    [].push.apply(this, temp.children)
                    return this;
                }
            }
        }
    }
    pjQuery.trim = function (str) {
        if(str.trim) {
            return str.trim()
        }else{
            return str.replace(/^\s+|\s+$/g, "");
        }
    }
    pjQuery.isHTML = function (str) {
        return str = str.charAt(0) === '<' && str.charAt(str.length - 1) === '>' && str.length >= '3'
    }
    pjQuery.isString = function (str) {
        return typeof(str) === 'string';
    }
    pjQuery.prototype.init.prototype = pjQuery.prototype
    window.pjQuery = window.$ = pjQuery
})(window)
```

#### 代码片段优化

```
(function (window, undefined) {
    var pjQuery = function (selector) {
        return new pjQuery.prototype.init(selector);
    }
    pjQuery.prototype = {
        constructor: pjQuery,
        // 代码片段类型处理
        init: function (selector) {

            // 解决代码片断开头和结尾有没有空格
            selector = pjQuery.trim(selector)
            // 判断传入的值是不是错误的
            if(!selector) {
                return this
            }else if(pjQuery.isString(selector)) {
                if(pjQuery.isHTML(selector)) {
                    // 创建一个节点，把所有的DOM元素放进去
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    [].push.apply(this, temp.children)
                    return this;
                }
            }
        }
    }
    // 工具方法抽取
    pjQuery.trim = function (str) {
        if(str.trim) {
            return str.trim()
        }else{
            return str.replace(/^\s+|\s+$/g, "");
        }
    }
    pjQuery.isHTML = function (str) {
        return str = str.charAt(0) === '<' && str.charAt(str.length - 1) === '>' && str.length >= '3'
    }
    pjQuery.isString = function (str) {
        return typeof(str) === 'string';
    }
    pjQuery.prototype.init.prototype = pjQuery.prototype
    window.pjQuery = window.$ = pjQuery
})(window)
```

#### 真伪数组转换

```
    // 真数组转换为伪数组
    window.onload = function (ev) {
        // 真转伪
        var arr = [1, 2, 3, 4, 5];
        var obj = {};
        [].push.apply(obj, arr)
        console.log(obj)
        // 伪转真 兼容ie8
        var obj = {"0": 'ppp', "1": '18', '2': 'male', length: 3}
        var arr = [].slice.call(obj)
        console.log(arr)
    }
```

#### 数组的处理

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }

    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)

            if(!selector) {
                return this;
                // 判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    return selector;
                }
            }
        }
    }
    njQuery.isString = function (str) {
        return typeof(str) === 'string'
    }
    njQuery.isHTML = function (str) {   
        return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
    } 
    njQuery.trim = function (str) {
        // 判断传入的值不是字符串
        if(!njQuery.isString(str)) {
            return str;
        }
        // 判断是否有trim方法
        if(str.trim) {
            return str.trim();
        }else{
            return str.replace(/^\s+|\s+$/g, "");
        }
    }
    njQuery.isObject = function (sele) {
        return typeof(sele) === 'object'
    }
    njQuery.isWindow = function (sele) {
        return sele === window
    }
    njQuery.isArray = function (sele) {
        if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
            return true
        }
        return false;
    }
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery

})(window)
```

#### 其它类型的处理

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    // return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
            return this;
        }
    }
    njQuery.isString = function (str) {
        return typeof(str) === 'string'
    }
    njQuery.isHTML = function (str) {   
        return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
    } 
    njQuery.trim = function (str) {
        // 判断传入的值不是字符串
        if(!njQuery.isString(str)) {
            return str;
        }
        // 判断是否有trim方法
        if(str.trim) {
            return str.trim();
        }else{
            return str.replace(/^\s+|\s+$/g, "");
        }
    }
    njQuery.isObject = function (sele) {
        return typeof(sele) === 'object'
    }
    njQuery.isWindow = function (sele) {
        return sele === window
    }
    njQuery.isArray = function (sele) {
        if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
            return true
        }
        return false;
    }
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)
  
```

#### extend方法

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
            }else if(njQuery.isFunction(selector)) {
                console.log('我是方法')
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    // return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
            return this;
        }
    }
    njQuery.extend = njQuery.prototype.extend = function (obj) {
        for(var key in obj) {
            this[key] = obj[key];
        }
    }

    njQuery.extend({
        isString : function (str) {
            return typeof(str) === 'string'
        },
        isHTML : function (str) {   
            return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
        },
        trim : function (str) {
            // 判断传入的值不是字符串
            if(!njQuery.isString(str)) {
                return str;
            }
            // 判断是否有trim方法
            if(str.trim) {
                return str.trim();
            }else{
                return str.replace(/^\s+|\s+$/g, "");
            }
        },
        isObject : function (sele) {
            return typeof(sele) === 'object'
        },
        isWindow : function (sele) {
            return sele === window
        },
        isArray : function (sele) {
            if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
                return true
            }
            return false;
        },
        isFunction : function (sele) {
            return typeof(sele) === "function"
        }
    })
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)	
```

#### 函数处理

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
                // 判断是否是函数           
            }else if(njQuery.isFunction(selector)) {
                njQuery.ready(selector)
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
        }
    }
    njQuery.extend = njQuery.prototype.extend = function (obj) {
        for(var key in obj) {
            this[key] = obj[key];
        }
    }

    njQuery.extend({
        isString : function (str) {
            return typeof(str) === 'string'
        },
        isHTML : function (str) {   
            return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
        },
        trim : function (str) {
            // 判断传入的值不是字符串
            if(!njQuery.isString(str)) {
                return str;
            }
            // 判断是否有trim方法
            if(str.trim) {
                return str.trim();
            }else{
                return str.replace(/^\s+|\s+$/g, "");
            }
        },
        isObject : function (sele) {
            return typeof(sele) === 'object'
        },
        isWindow : function (sele) {
            return sele === window
        },
        isArray : function (sele) {
            if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
                return true
            }
            return false;
        },
        isFunction : function (sele) {
            return typeof(sele) === "function"
        },
        ready: function (fn) {
            // 判断DOM是否加载完毕
            if(document.readyState == "complete") {
                fn();
            }else if(document.addEventListener){
                document.addEventListener('DOMContentLoaded', function () {
                    fn()
                })
            }else{
                document.attachEvent("onreadystatechange", function () {
                    if(document.readyState === 'complete') {
                        fn();
                    }
                })
            }
        
        }
    })
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)
  

```

#### jQuery原型上的属性和方法

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
                // 判断是否是函数           
            }else if(njQuery.isFunction(selector)) {
                njQuery.ready(selector)
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
        },
        // 获取jq的版本号
        jquery: "1.1.0",
        // 实例默认的选择器取值
        selector: "",
        // 实例默认的长度
        length: 0,
        // 找到数组的push方法
        // 冒号前面的push将由njQuery对象调用
        // 相当于[].push.apply(this);
        push: [].push,
        sort: [].sort,
        splice: [].splice,
        toArray: function () {
            return [].slice.call(this)
        },
        get: function (num) {
            // 没有传递参数
            if(arguments.length === 0) {
                return this.toArray()
            }else if(num > 0) {
                return this[num]
            }else{
                return this[this.length + num];
            }
        }

    }
    njQuery.extend = njQuery.prototype.extend = function (obj) {
        for(var key in obj) {
            this[key] = obj[key];
        }
    }

    njQuery.extend({
        isString : function (str) {
            return typeof(str) === 'string'
        },
        isHTML : function (str) {   
            return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
        },
        trim : function (str) {
            // 判断传入的值不是字符串
            if(!njQuery.isString(str)) {
                return str;
            }
            // 判断是否有trim方法
            if(str.trim) {
                return str.trim();
            }else{
                return str.replace(/^\s+|\s+$/g, "");
            }
        },
        isObject : function (sele) {
            return typeof(sele) === 'object'
        },
        isWindow : function (sele) {
            return sele === window
        },
        isArray : function (sele) {
            if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
                return true
            }
            return false;
        },
        isFunction : function (sele) {
            return typeof(sele) === "function"
        },
        ready: function (fn) {
            // 判断DOM是否加载完毕
            if(document.readyState == "complete") {
                fn();
            }else if(document.addEventListener){
                document.addEventListener('DOMContentLoaded', function () {
                    fn()
                })
            }else{
                document.attachEvent("onreadystatechange", function () {
                    if(document.readyState === 'complete') {
                        fn();
                    }
                })
            }
        
        }
    })
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)
```

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
                // 判断是否是函数           
            }else if(njQuery.isFunction(selector)) {
                njQuery.ready(selector)
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
        },
        // 获取jq的版本号
        jquery: "1.1.0",
        // 实例默认的选择器取值
        selector: "",
        // 实例默认的长度
        length: 0,
        // 找到数组的push方法
        // 冒号前面的push将由njQuery对象调用
        // 相当于[].push.apply(this);
        push: [].push,
        sort: [].sort,
        splice: [].splice,
        toArray: function () {
            return [].slice.call(this)
        },
        get: function (num) {
            // 没有传递参数
            if(arguments.length === 0) {
                return this.toArray()
            }else if(num >= 0) {
                return this[num]
            }else{
                return this[this.length + num];
            }
        },
        eq: function (num) {
            //没有传递参数
            if(arguments.length === 0) {
                return new njQuery;
            }else{
                return njQuery(this.get(num));
            }
        },
        first: function () {
            return this.eq(0)
        },
        last: function (num) {
            return this.eq(-1)
        },
        each: function (fn) {
            njQuery.each(this, fn);
        }

    }
    njQuery.extend = njQuery.prototype.extend = function (obj) {
        for(var key in obj) {
            this[key] = obj[key];
        }
    }

    njQuery.extend({
        isString : function (str) {
            return typeof(str) === 'string'
        },
        isHTML : function (str) {   
            return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
        },
        trim : function (str) {
            // 判断传入的值不是字符串
            if(!njQuery.isString(str)) {
                return str;
            }
            // 判断是否有trim方法
            if(str.trim) {
                return str.trim();
            }else{
                return str.replace(/^\s+|\s+$/g, "");
            }
        },
        isObject : function (sele) {
            return typeof(sele) === 'object'
        },
        isWindow : function (sele) {
            return sele === window
        },
        isArray : function (sele) {
            if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
                return true
            }
            return false;
        },
        isFunction : function (sele) {
            return typeof(sele) === "function"
        },
        ready: function (fn) {
            // 判断DOM是否加载完毕
            if(document.readyState == "complete") {
                fn();
            }else if(document.addEventListener){
                document.addEventListener('DOMContentLoaded', function () {
                    fn()
                })
            }else{
                document.attachEvent("onreadystatechange", function () {
                    if(document.readyState === 'complete') {
                        fn();
                    }
                })
            }
        },
        each: function (obj, fn) {
            // 判断是否是数组
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                   var res = fn.call(obj[i], i, obj[i]);
                   if(res === true) {
                       continue;
                   }else if(res === false){
                       break;
                   }
                }
            // 判断是否是对象
            }else if(njQuery.isObject(obj)) {
                for(var prop in obj) {
                    var res = fn.call(obj[prop], prop, obj[prop]);
                    if(res === true) {
                        continue;
                    }else if(res === false){
                        break;
                    }
                }
            }
        },
        map: function (obj, fn) {
            var res = [];
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                    var temp = fn(obj[i], i);
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }else if(njQuery.isObject(obj)) {
                for(var key in obj) {
                    var temp = fn(obj[key], key)
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }
            return res;
        }
    })
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)
```

#### jqueryDOM操作相关方法

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    // 对象方法
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
                // 判断是否是函数           
            }else if(njQuery.isFunction(selector)) {
                njQuery.ready(selector)
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
        },
        // 获取jq的版本号
        jquery: "1.1.0",
        // 实例默认的选择器取值
        selector: "",
        // 实例默认的长度
        length: 0,
        // 找到数组的push方法
        // 冒号前面的push将由njQuery对象调用
        // 相当于[].push.apply(this);
        push: [].push,
        sort: [].sort,
        splice: [].splice,
        toArray: function () {
            return [].slice.call(this)
        },
        get: function (num) {
            // 没有传递参数
            if(arguments.length === 0) {
                return this.toArray()
            }else if(num >= 0) {
                return this[num]
            }else{
                return this[this.length + num];
            }
        },
        eq: function (num) {
            //没有传递参数
            if(arguments.length === 0) {
                return new njQuery;
            }else{
                return njQuery(this.get(num));
            }
        },
        first: function () {
            return this.eq(0)
        },
        last: function (num) {
            return this.eq(-1)
        },
        each: function (fn) {
            njQuery.each(this, fn);
        }

    }
    njQuery.extend = njQuery.prototype.extend = function (obj) {
        for(var key in obj) {
            this[key] = obj[key];
        }
    }
    // 工具方法
    njQuery.extend({
        isString : function (str) {
            return typeof(str) === 'string'
        },
        isHTML : function (str) {   
            return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
        },
        trim : function (str) {
            // 判断传入的值不是字符串
            if(!njQuery.isString(str)) {
                return str;
            }
            // 判断是否有trim方法
            if(str.trim) {
                return str.trim();
            }else{
                return str.replace(/^\s+|\s+$/g, "");
            }
        },
        isObject : function (sele) {
            return typeof(sele) === 'object'
        },
        isWindow : function (sele) {
            return sele === window
        },
        isArray : function (sele) {
            if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
                return true
            }
            return false;
        },
        isFunction : function (sele) {
            return typeof(sele) === "function"
        },
        ready: function (fn) {
            // 判断DOM是否加载完毕
            if(document.readyState == "complete") {
                fn();
            }else if(document.addEventListener){
                document.addEventListener('DOMContentLoaded', function () {
                    fn()
                })
            }else{
                document.attachEvent("onreadystatechange", function () {
                    if(document.readyState === 'complete') {
                        fn();
                    }
                })
            }
        },
        each: function (obj, fn) {
            // 判断是否是数组
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                   var res = fn.call(obj[i], i, obj[i]);
                   if(res === true) {
                       continue;
                   }else if(res === false){
                       break;
                   }
                }
            // 判断是否是对象
            }else if(njQuery.isObject(obj)) {
                for(var prop in obj) {
                    var res = fn.call(obj[prop], prop, obj[prop]);
                    if(res === true) {
                        continue;
                    }else if(res === false){
                        break;
                    }
                }
            }
        },
        map: function (obj, fn) {
            var res = [];
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                    var temp = fn(obj[i], i);
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }else if(njQuery.isObject(obj)) {
                for(var key in obj) {
                    var temp = fn(obj[key], key)
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }
            return res;
        }
    })
    // DOM操作方法
    njQuery.prototype.extend({
        empty: function () {
            // 遍历所有找到的元素
            this.each(function (key, value) {
                value.innerHTML = "";
            })
            // 返回this,方便链式编程
            return this;
        },
        remove: function (sele) {
            if(arguments.length === 0) {
                // 遍历所有找到的元素
                this.each(function (key, value) {
                    // 根据遍历到的元素找到对应的父元素
                    var parent = value.parentNode;
                    // 通过父元素删除指定的元素
                    parent.removeChild(value);
                })
                return this;
            }else{
                var $this = this;
                // 根据传入的选择器找到对应的元素
                $(sele).each(function (key, value) {
                    var type = value.tagName;
                    $this.each(function (k, v) {
                        var t = v.tagName;
                        if(t === type) {
                            // 根据遍历到的元素找到对应的父元素
                            var parent = value.parentNode;
                            // 通过父元素删除指定的元素
                            parent.removeChild(value);
                        }
                    })
                })
                // 遍历找到的元素,获取对应的类型
                // 遍历指定的元素
                // 获取指定元素的类型
                // 判断找到元素的类型和指定元素的类型
            }
        },
        html: function (content) {
            if(arguments.length === 0) {
                return this[0].innerHTML
            }else{
                this.each(function (key, value) {
                    value.innerHTML = content;
                })
            }
        },
        text: function (content) {
            if(arguments.length === 0) {
                var res = ''
                 this.each(function (key, value) {
                    res += value.innerText;
                })
                return res;
            }else{
                this.each(function (key, value) {
                    value.innerText = content;
                })
                return this;
            }
        },
        appendTo: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    value.appendChild(v);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    value.appendChild(temp);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        prependTo: function (sele) {  
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    value.insertBefore(v, value.firstChild);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    value.insertBefore(temp, value.firstChild);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        append: function (sele) {
            if(njQuery.isString(sele)) {
                this[0].innerHTML += sele;
            }else{
                $(sele).appendTo(this);
            }
            return this;
        },
        prepend: function (sele) {
            if(njQuery.isString(sele)) {
                this[0].innerHTML = sele + this[0].innerHTML;
            }else{
                $(sele).prependTo(this);
            }
            return this;
        },
        insertBefore: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            var parent = value.parentNode;
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    parent.insertBefore(v, value);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    parent.insertBefore(temp, value);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        replaceAll: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            var parent = value.parentNode;
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 1.将元素插入到指定元素的前面
                    $(v).insertBefore(value);
                    // 2.将指定的元素删除
                    $(value).remove();
                    res.push(v)
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    // 1.将元素插入到指定元素的前面
                    $(temp).insertBefore(value);
                    // 2.将指定的元素删除
                    $(value).remove();
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);  
        }
    })
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)
```

#### 属性操作相关方法

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    // 对象方法
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
                // 判断是否是函数           
            }else if(njQuery.isFunction(selector)) {
                njQuery.ready(selector)
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
        },
        // 获取jq的版本号
        jquery: "1.1.0",
        // 实例默认的选择器取值
        selector: "",
        // 实例默认的长度
        length: 0,
        // 找到数组的push方法
        // 冒号前面的push将由njQuery对象调用
        // 相当于[].push.apply(this);
        push: [].push,
        sort: [].sort,
        splice: [].splice,
        toArray: function () {
            return [].slice.call(this)
        },
        get: function (num) {
            // 没有传递参数
            if(arguments.length === 0) {
                return this.toArray()
            }else if(num >= 0) {
                return this[num]
            }else{
                return this[this.length + num];
            }
        },
        eq: function (num) {
            //没有传递参数
            if(arguments.length === 0) {
                return new njQuery;
            }else{
                return njQuery(this.get(num));
            }
        },
        first: function () {
            return this.eq(0)
        },
        last: function (num) {
            return this.eq(-1)
        },
        each: function (fn) {
            njQuery.each(this, fn);
        }

    }
    njQuery.extend = njQuery.prototype.extend = function (obj) {
        for(var key in obj) {
            this[key] = obj[key];
        }
    }
    // 工具方法
    njQuery.extend({
        isString : function (str) {
            return typeof(str) === 'string'
        },
        isHTML : function (str) {   
            return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
        },
        trim : function (str) {
            // 判断传入的值不是字符串
            if(!njQuery.isString(str)) {
                return str;
            }
            // 判断是否有trim方法
            if(str.trim) {
                return str.trim();
            }else{
                return str.replace(/^\s+|\s+$/g, "");
            }
        },
        isObject : function (sele) {
            return typeof(sele) === 'object'
        },
        isWindow : function (sele) {
            return sele === window
        },
        isArray : function (sele) {
            if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
                return true
            }
            return false;
        },
        isFunction : function (sele) {
            return typeof(sele) === "function"
        },
        ready: function (fn) {
            // 判断DOM是否加载完毕
            if(document.readyState == "complete") {
                fn();
            }else if(document.addEventListener){
                document.addEventListener('DOMContentLoaded', function () {
                    fn()
                })
            }else{
                document.attachEvent("onreadystatechange", function () {
                    if(document.readyState === 'complete') {
                        fn();
                    }
                })
            }
        },
        each: function (obj, fn) {
            // 判断是否是数组
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                   var res = fn.call(obj[i], i, obj[i]);
                   if(res === true) {
                       continue;
                   }else if(res === false){
                       break;
                   }
                }
            // 判断是否是对象
            }else if(njQuery.isObject(obj)) {
                for(var prop in obj) {
                    var res = fn.call(obj[prop], prop, obj[prop]);
                    if(res === true) {
                        continue;
                    }else if(res === false){
                        break;
                    }
                }
            }
        },
        map: function (obj, fn) {
            var res = [];
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                    var temp = fn(obj[i], i);
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }else if(njQuery.isObject(obj)) {
                for(var key in obj) {
                    var temp = fn(obj[key], key)
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }
            return res;
        },
        getStyle: function (elem, prop) {
            if(window.getComputedStyle) {
                return window.getComputedStyle(elem, null)[prop];
            }else{
                return elem.currentStyle[prop];
            }
        }
    })
    // DOM操作方法
    njQuery.prototype.extend({
        empty: function () {
            // 遍历所有找到的元素
            this.each(function (key, value) {
                value.innerHTML = "";
            })
            // 返回this,方便链式编程
            return this;
        },
        remove: function (sele) {
            if(arguments.length === 0) {
                // 遍历所有找到的元素
                this.each(function (key, value) {
                    // 根据遍历到的元素找到对应的父元素
                    var parent = value.parentNode;
                    // 通过父元素删除指定的元素
                    parent.removeChild(value);
                })
                return this;
            }else{
                var $this = this;
                // 根据传入的选择器找到对应的元素
                $(sele).each(function (key, value) {
                    var type = value.tagName;
                    $this.each(function (k, v) {
                        var t = v.tagName;
                        if(t === type) {
                            // 根据遍历到的元素找到对应的父元素
                            var parent = value.parentNode;
                            // 通过父元素删除指定的元素
                            parent.removeChild(value);
                        }
                    })
                })
                // 遍历找到的元素,获取对应的类型
                // 遍历指定的元素
                // 获取指定元素的类型
                // 判断找到元素的类型和指定元素的类型
            }
        },
        html: function (content) {
            if(arguments.length === 0) {
                return this[0].innerHTML
            }else{
                this.each(function (key, value) {
                    value.innerHTML = content;
                })
            }
        },
        text: function (content) {
            if(arguments.length === 0) {
                var res = ''
                 this.each(function (key, value) {
                    res += value.innerText;
                })
                return res;
            }else{
                this.each(function (key, value) {
                    value.innerText = content;
                })
                return this;
            }
        },
        appendTo: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    value.appendChild(v);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    value.appendChild(temp);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        prependTo: function (sele) {  
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    value.insertBefore(v, value.firstChild);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    value.insertBefore(temp, value.firstChild);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        append: function (sele) {
            if(njQuery.isString(sele)) {
                this[0].innerHTML += sele;
            }else{
                $(sele).appendTo(this);
            }
            return this;
        },
        prepend: function (sele) {
            if(njQuery.isString(sele)) {
                this[0].innerHTML = sele + this[0].innerHTML;
            }else{
                $(sele).prependTo(this);
            }
            return this;
        },
        insertBefore: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            var parent = value.parentNode;
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    parent.insertBefore(v, value);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    parent.insertBefore(temp, value);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        replaceAll: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            var parent = value.parentNode;
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 1.将元素插入到指定元素的前面
                    $(v).insertBefore(value);
                    // 2.将指定的元素删除
                    $(value).remove();
                    res.push(v)
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    // 1.将元素插入到指定元素的前面
                    $(temp).insertBefore(value);
                    // 2.将指定的元素删除
                    $(value).remove();
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);  
        }
    })
    // 属性相关方法
    njQuery.prototype.extend({
        attr: function (attr, value) {
            // 1.判断是否是字符串
            if(njQuery.isString(attr)) {
                // 判断是一个字符串还是两个字符串
                if(arguments.length === 1) {
                    return this[0].getAttribute(attr)
                }else{
                    this.each(function (key, ele) {
                        ele.setAttribute(attr, value);
                    })
                }
                // 2.判断是否是对象
            }else if(njQuery.isObject(attr)) {
                var $this = this
                // 遍历取出所有属性节点的名称和对应的值
                $.each(attr, function (key, value) {
                    // 遍历取出所有的元素
                    $this.each(function (k, ele) {
                        ele.setAttribute(key, value);
                    })
                })
            }
            return this;
        },
        prop: function (attr, value) {
            // 1.判断是否是字符串
            if(njQuery.isString(attr)) {
                // 判断是一个字符串还是两个字符串
                if(arguments.length === 1) {
                    return this[0][attr]
                }else{
                    this.each(function (key, ele) {
                        ele[attr] = value
                    })
                }
                // 2.判断是否是对象
            }else if(njQuery.isObject(attr)) {
                var $this = this
                // 遍历取出所有属性节点的名称和对应的值
                $.each(attr, function (key, value) {
                    // 遍历取出所有的元素
                    $this.each(function (k, ele) {
                        ele[key] = value
                    })
                })
            }
            return this;
        },
        css: function (attr, value) {
            // 1.判断是否是字符串
            if(njQuery.isString(attr)) {
                // 判断是一个字符串还是两个字符串
                if(arguments.length === 1) {
                    return njQuery.getStyle(this[0], attr);
                }else{
                    this.each(function (key, ele) {
                        ele.style[attr] = value;
                    })
                }
                // 2.判断是否是对象
            }else if(njQuery.isObject(attr)) {
                var $this = this;
                // 遍历取出所有属性节点的名称和对应的值
                $.each(attr, function (key, value) {
                    // 遍历取出所有的元素
                    $this.each(function (k, ele) {
                        ele.style[key] = value;
                    })
                })
            }
            return this;
        },
        val: function (content) {
            if(arguments.length === 0) {
                return this[0].value
            }else{
                this.each(function (key, ele) {
                    ele.value = content;
                })
                return this;
            }
        },
        hasClass: function (name) {
            var flag = false;
            if(arguments.length === 0) {
                return flag;
            }else{
                this.each(function (key, ele) {
                    // 1.获取元素中class保存的值
                    var className = " " + ele.className + " ";
                    // 给指定字符串的前后也加上空格
                    name = " " + name + " ";
                    // 通过indexOf判断是否包含指定的字符串
                    if(className.indexOf(name) != -1) {
                        flag = true;
                        return false;
                    }
                })
                return flag;
            }
        },
        addClass: function (name) {
            if(arguments.length === 0) {
                return this;
            }
            // 1.对传入的类名分割
            var names = name.split(" ")
            // 2.遍历取出所有的元素
            this.each(function (key, ele) {
                // 3.遍历数组取出每一个类名
                $.each(names, function (k, value) {
                    // 4.判断指定元素中是否包含指定的类名
                    if(!$(ele).hasClass(value)) {
                        ele.className = ele.className + ' ' + value
                    }
                })
            })
            return this; 
        },
        removeClass: function (name) {
            if(arguments.length === 0) {
                this.each(function (key, ele) {
                    ele.className = ''
                })
            }else{
                // 1.对传入的类名分割
                var names = name.split(" ")
                // 2.遍历取出所有的元素
                this.each(function (key, ele) {
                    // 3.遍历数组取出每一个类名
                    $.each(names, function (k, value) {
                        // 4.判断指定元素中是否包含指定的类名
                        if($(ele).hasClass(value)) {
                            ele.className = (" " + ele.className+ " ").replace(" " + value + " ", '')
                        }
                    })
                })
            }
            return this;
        },
        toggleClass: function (name) {
            if(arguments.length === 0) {
                this.removeClass();
            }else{
                 // 1.对传入的类名分割
                var names = name.split(" ")
                // 2.遍历取出所有的元素
                this.each(function (key, ele) {
                    // 3.遍历数组取出每一个类名
                    $.each(names, function (k, value) {
                        // 4.判断指定元素中是否包含指定的类名
                        if($(ele).hasClass(value)) {
                        //删除
                        $(ele).removeClass(value)
                        }else{
                        //添加
                        $(ele).addClass(value);
                        }
                    })
                })
            }
             return this;
        } 
    });
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)
```

#### 事件操作方法

```
(function (window, undefined) {
    var njQuery = function (selector) {
        return new njQuery.prototype.init(selector) 
    }
    // 对象方法
    njQuery.prototype = {
        constructor: njQuery,
        init: function (selector) {
            // 去除字符串两端的空格
            selector = njQuery.trim(selector)
                // 1.判断值是false
            if(!selector) {
                return this;
                // 判断是否是函数           
            }else if(njQuery.isFunction(selector)) {
                njQuery.ready(selector)
                // 2.判断是否是字符串
            }else if(njQuery.isString(selector)) {
                // 判断是否是代码片段
                if(njQuery.isHTML(selector)) {
                    // 根据代码片段创建所有的元素
                    var temp = document.createElement('div');
                    temp.innerHTML = selector;
                    // 将创建好的一级元素添加到jQuery当中
                    [].push.apply(this, temp.children)
                    // 返回
                    // return this;
                }else{
                    // 根据传入的选择器找到对应的元素
                    var res = document.querySelectorAll(selector);
                    // 将找到的元素添加到jQuery上
                    [].push.apply(this, res)
                    // 返回
                    // return this;
                }
                // 3.数组
            }else if(njQuery.isArray(selector)) {
                // 真数组
                if(({}).toString.apply(selector) == "[object Array]") {
                    // 返回
                    [].push.apply(this, selector)
                    // return this;
                    // 伪数组
                }else{
                    // 伪转真
                    var arr = [].slice.apply(selector);
                    // 真转伪
                    [].push.apply(this, arr)
                    // 返回
                    return this;
                }
                // 4.除上述类型以外
            }else{
                this[0] = selector;
                this.length = 1;
                return this;
            }
        },
        // 获取jq的版本号
        jquery: "1.1.0",
        // 实例默认的选择器取值
        selector: "",
        // 实例默认的长度
        length: 0,
        // 找到数组的push方法
        // 冒号前面的push将由njQuery对象调用
        // 相当于[].push.apply(this);
        push: [].push,
        sort: [].sort,
        splice: [].splice,
        toArray: function () {
            return [].slice.call(this)
        },
        get: function (num) {
            // 没有传递参数
            if(arguments.length === 0) {
                return this.toArray()
            }else if(num >= 0) {
                return this[num]
            }else{
                return this[this.length + num];
            }
        },
        eq: function (num) {
            //没有传递参数
            if(arguments.length === 0) {
                return new njQuery;
            }else{
                return njQuery(this.get(num));
            }
        },
        first: function () {
            return this.eq(0)
        },
        last: function (num) {
            return this.eq(-1)
        },
        each: function (fn) {
            njQuery.each(this, fn);
        }

    }
    njQuery.extend = njQuery.prototype.extend = function (obj) {
        for(var key in obj) {
            this[key] = obj[key];
        }
    }
    // 工具方法
    njQuery.extend({
        isString : function (str) {
            return typeof(str) === 'string'
        },
        isHTML : function (str) {   
            return str = str.charAt(0) == '<' && str.charAt(str.length - 1) === '>' && str.length >= 3
        },
        trim : function (str) {
            // 判断传入的值不是字符串
            if(!njQuery.isString(str)) {
                return str;
            }
            // 判断是否有trim方法
            if(str.trim) {
                return str.trim();
            }else{
                return str.replace(/^\s+|\s+$/g, "");
            }
        },
        isObject : function (sele) {
            return typeof(sele) === 'object'
        },
        isWindow : function (sele) {
            return sele === window
        },
        isArray : function (sele) {
            if(njQuery.isObject(sele) && !njQuery.isWindow(sele) && "length" in sele) {
                return true
            }
            return false;
        },
        isFunction : function (sele) {
            return typeof(sele) === "function"
        },
        ready: function (fn) {
            // 判断DOM是否加载完毕
            if(document.readyState == "complete") {
                fn();
            }else if(document.addEventListener){
                document.addEventListener('DOMContentLoaded', function () {
                    fn()
                })
            }else{
                document.attachEvent("onreadystatechange", function () {
                    if(document.readyState === 'complete') {
                        fn();
                    }
                })
            }
        },
        each: function (obj, fn) {
            // 判断是否是数组
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                   var res = fn.call(obj[i], i, obj[i]);
                   if(res === true) {
                       continue;
                   }else if(res === false){
                       break;
                   }
                }
            // 判断是否是对象
            }else if(njQuery.isObject(obj)) {
                for(var prop in obj) {
                    var res = fn.call(obj[prop], prop, obj[prop]);
                    if(res === true) {
                        continue;
                    }else if(res === false){
                        break;
                    }
                }
            }
        },
        map: function (obj, fn) {
            var res = [];
            if(njQuery.isArray(obj)) {
                for(var i = 0; i < obj.length; i ++) {
                    var temp = fn(obj[i], i);
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }else if(njQuery.isObject(obj)) {
                for(var key in obj) {
                    var temp = fn(obj[key], key)
                    if(temp) {  
                        res.push(temp);
                    }
                }
            }
            return res;
        },
        getStyle: function (elem, prop) {
            if(window.getComputedStyle) {
                return window.getComputedStyle(elem, null)[prop];
            }else{
                return elem.currentStyle[prop];
            }
        },
        addEvent: function(elem, type, handle) {
            if(elem.addEventListener) {
                elem.addEventListener(type, handle, false);
            }else if(elem.onclick) {
                elem['on' + type] = handle
            }else{
                elem.attachEvent('on' + type, handle)
            }
        }
    })
    // DOM操作方法
    njQuery.prototype.extend({
        empty: function () {
            // 遍历所有找到的元素
            this.each(function (key, value) {
                value.innerHTML = "";
            })
            // 返回this,方便链式编程
            return this;
        },
        remove: function (sele) {
            if(arguments.length === 0) {
                // 遍历所有找到的元素
                this.each(function (key, value) {
                    // 根据遍历到的元素找到对应的父元素
                    var parent = value.parentNode;
                    // 通过父元素删除指定的元素
                    parent.removeChild(value);
                })
                return this;
            }else{
                var $this = this;
                // 根据传入的选择器找到对应的元素
                $(sele).each(function (key, value) {
                    var type = value.tagName;
                    $this.each(function (k, v) {
                        var t = v.tagName;
                        if(t === type) {
                            // 根据遍历到的元素找到对应的父元素
                            var parent = value.parentNode;
                            // 通过父元素删除指定的元素
                            parent.removeChild(value);
                        }
                    })
                })
                // 遍历找到的元素,获取对应的类型
                // 遍历指定的元素
                // 获取指定元素的类型
                // 判断找到元素的类型和指定元素的类型
            }
        },
        html: function (content) {
            if(arguments.length === 0) {
                return this[0].innerHTML
            }else{
                this.each(function (key, value) {
                    value.innerHTML = content;
                })
            }
        },
        text: function (content) {
            if(arguments.length === 0) {
                var res = ''
                 this.each(function (key, value) {
                    res += value.innerText;
                })
                return res;
            }else{
                this.each(function (key, value) {
                    value.innerText = content;
                })
                return this;
            }
        },
        appendTo: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    value.appendChild(v);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    value.appendChild(temp);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        prependTo: function (sele) {  
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    value.insertBefore(v, value.firstChild);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    value.insertBefore(temp, value.firstChild);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        append: function (sele) {
            if(njQuery.isString(sele)) {
                this[0].innerHTML += sele;
            }else{
                $(sele).appendTo(this);
            }
            return this;
        },
        prepend: function (sele) {
            if(njQuery.isString(sele)) {
                this[0].innerHTML = sele + this[0].innerHTML;
            }else{
                $(sele).prependTo(this);
            }
            return this;
        },
        insertBefore: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            var parent = value.parentNode;
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 直接添加
                    parent.insertBefore(v, value);
                    res.push(v);
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    parent.insertBefore(temp, value);
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);
        },
        replaceAll: function (sele) {
            // 统一把传入的数据转换为jQuery对象
            var $target = $(sele);
            var $this = this;
            var res = [];
        //  遍历取出所有指定的元素的元素
        $.each($target, function (key, value) {
            var parent = value.parentNode;
            // 遍历取出所有指定的元素的元素
            $this.each(function (k, v) {
                if(key === 0) {
                    // 1.将元素插入到指定元素的前面
                    $(v).insertBefore(value);
                    // 2.将指定的元素删除
                    $(value).remove();
                    res.push(v)
                }else{
                    // 先拷贝再添加
                    var temp = v.cloneNode(true);
                    // 1.将元素插入到指定元素的前面
                    $(temp).insertBefore(value);
                    // 2.将指定的元素删除
                    $(value).remove();
                    res.push(v);
                }   
            })
        })
        // 返回所有添加的元素
        return $(res);  
        },
        clone: function (deep) {
            var res = [];
            //判断是否是深复制
            if(deep) {
                //深复制
                this.each(function (key, ele) {
                    var temp = ele.cloneNode(true);
                    // 遍历元素中的eventsCache对象
                    njQuery.each(ele.eventsCache, function (name, array) {
                        //遍历事件对应的数组
                        njQuery.each(array, function (index, method) {
                            //给复制的元素添加事件
                            $(temp).on(name, method);
                        })
                    })
                    res.push(temp); 
                })
                return $(res);
            }else{
                //浅复制
                this.each(function (key, ele) {
                    var temp = ele.cloneNode(true);
                    res.push(temp); 
                })
                return $(res);
            }
        }
    })
    // 属性相关方法
    njQuery.prototype.extend({
        attr: function (attr, value) {
            // 1.判断是否是字符串
            if(njQuery.isString(attr)) {
                // 判断是一个字符串还是两个字符串
                if(arguments.length === 1) {
                    return this[0].getAttribute(attr)
                }else{
                    this.each(function (key, ele) {
                        ele.setAttribute(attr, value);
                    })
                }
                // 2.判断是否是对象
            }else if(njQuery.isObject(attr)) {
                var $this = this
                // 遍历取出所有属性节点的名称和对应的值
                $.each(attr, function (key, value) {
                    // 遍历取出所有的元素
                    $this.each(function (k, ele) {
                        ele.setAttribute(key, value);
                    })
                })
            }
            return this;
        },
        prop: function (attr, value) {
            // 1.判断是否是字符串
            if(njQuery.isString(attr)) {
                // 判断是一个字符串还是两个字符串
                if(arguments.length === 1) {
                    return this[0][attr]
                }else{
                    this.each(function (key, ele) {
                        ele[attr] = value
                    })
                }
                // 2.判断是否是对象
            }else if(njQuery.isObject(attr)) {
                var $this = this
                // 遍历取出所有属性节点的名称和对应的值
                $.each(attr, function (key, value) {
                    // 遍历取出所有的元素
                    $this.each(function (k, ele) {
                        ele[key] = value
                    })
                })
            }
            return this;
        },
        css: function (attr, value) {
            // 1.判断是否是字符串
            if(njQuery.isString(attr)) {
                // 判断是一个字符串还是两个字符串
                if(arguments.length === 1) {
                    return njQuery.getStyle(this[0], attr);
                }else{
                    this.each(function (key, ele) {
                        ele.style[attr] = value;
                    })
                }
                // 2.判断是否是对象
            }else if(njQuery.isObject(attr)) {
                var $this = this;
                // 遍历取出所有属性节点的名称和对应的值
                $.each(attr, function (key, value) {
                    // 遍历取出所有的元素
                    $this.each(function (k, ele) {
                        ele.style[key] = value;
                    })
                })
            }
            return this;
        },
        val: function (content) {
            if(arguments.length === 0) {
                return this[0].value
            }else{
                this.each(function (key, ele) {
                    ele.value = content;
                })
                return this;
            }
        },
        hasClass: function (name) {
            var flag = false;
            if(arguments.length === 0) {
                return flag;
            }else{
                this.each(function (key, ele) {
                    // 1.获取元素中class保存的值
                    var className = " " + ele.className + " ";
                    // 给指定字符串的前后也加上空格
                    name = " " + name + " ";
                    // 通过indexOf判断是否包含指定的字符串
                    if(className.indexOf(name) != -1) {
                        flag = true;
                        return false;
                    }
                })
                return flag;
            }
        },
        addClass: function (name) {
            if(arguments.length === 0) {
                return this;
            }
            // 1.对传入的类名分割
            var names = name.split(" ")
            // 2.遍历取出所有的元素
            this.each(function (key, ele) {
                // 3.遍历数组取出每一个类名
                $.each(names, function (k, value) {
                    // 4.判断指定元素中是否包含指定的类名
                    if(!$(ele).hasClass(value)) {
                        ele.className = ele.className + ' ' + value
                    }
                })
            })
            return this; 
        },
        removeClass: function (name) {
            if(arguments.length === 0) {
                this.each(function (key, ele) {
                    ele.className = ''
                })
            }else{
                // 1.对传入的类名分割
                var names = name.split(" ")
                // 2.遍历取出所有的元素
                this.each(function (key, ele) {
                    // 3.遍历数组取出每一个类名
                    $.each(names, function (k, value) {
                        // 4.判断指定元素中是否包含指定的类名
                        if($(ele).hasClass(value)) {
                            ele.className = (" " + ele.className+ " ").replace(" " + value + " ", '')
                        }
                    })
                })
            }
            return this;
        },
        toggleClass: function (name) {
            if(arguments.length === 0) {
                this.removeClass();
            }else{
                 // 1.对传入的类名分割
                var names = name.split(" ")
                // 2.遍历取出所有的元素
                this.each(function (key, ele) {
                    // 3.遍历数组取出每一个类名
                    $.each(names, function (k, value) {
                        // 4.判断指定元素中是否包含指定的类名
                        if($(ele).hasClass(value)) {
                        //删除
                        $(ele).removeClass(value)
                        }else{
                        //添加
                        $(ele).addClass(value);
                        }
                    })
                })
            }
             return this;
        } 
    });
    //事件操作相关方法
    njQuery.prototype.extend({
        on: function (name, callBack) {
            // 1.遍历取出所有的元素
            this.each(function (key, ele) {
                // 2.判断当前元素中是否有保存所有事件的对象
                if(!ele.eventsCache) {
                    ele.eventsCache = {}
                }
                // 3.判断对象中有没有对应类型的数组 
                if(!ele.eventsCache[name]) {
                    ele.eventsCache[name] = []
                    // 4.将回调函数添加到数组中
                    ele.eventsCache[name].push(callBack);
                    // 5.添加对应类型的事件
                    njQuery.addEvent(ele, name, function () {
                        njQuery.each(ele.eventsCache[name], function (k, method) {
                            method();
                        })
                    });
                }else{
                    ele.eventsCache[name].push(callBack);
                }
            })
        },
        off: function (name, callBack) {
            // 1.判断是否没有传入参数
            if(arguments.length === 0) {
                this.each(function (key, ele) {
                    ele.eventsCache = {}
                })
            // 2.判断传入了一个参数
            }else if(arguments.length == 1) {
                this.each(function (key, ele) {
                    ele.eventsCache[name] = {}
                })
                // 3.判断是否传入了两个参数
            }else if(arguments.length == 2){
                this.each(function (key, ele) {
                    njQuery.each(ele.eventsCache[name], function (index, method) {
                        // 判断当前遍历到的方法和传入的方法是否相同
                        if(method === callBack) {
                            ele.eventsCache[name].splice(index, 1);
                        }
                    })
                })
            }
        }
    })
    njQuery.prototype.init.prototype = njQuery.prototype
    window.njQuery = window.$ = njQuery
})(window)
```

