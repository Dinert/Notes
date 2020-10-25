# Jquery

## jQuery是什么？



![img](https:////upload-images.jianshu.io/upload_images/647982-7db39e6f1bf9c026.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/422/format/webp)



- jQuery是一款优秀的JavaScript库，从命名可以看出jQuery最主要的用途是用来做查询（jQuery=js+Query）.
- 在jQuery官方Logo下方还有一个副标题（write less, do more）, 体现了jQuery除了查询以外,还能让我们对HTML文档遍历和操作、事件处理、动画以及Ajax变得更加简单
- ![img](https://upload-images.jianshu.io/upload_images/647982-534499becbe5cc2c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

- [1.x](https://link.jianshu.com?t=https%3A%2F%2Fcode.jquery.com%2F)：兼容ie678，但相对其它版本文件较大，官方只做BUG维护，功能不再新增，最终版本：1.12.4 (2016年5月20日).
- [2.x](https://link.jianshu.com?t=https%3A%2F%2Fcode.jquery.com%2F)：不兼容ie678，相对1.x文件较小，官方只做BUG维护，功能不再新增，最终版本：2.2.4 (2016年5月20日)
- [3.x](https://link.jianshu.com?t=https%3A%2F%2Fcode.jquery.com%2F)：不兼容ie678，只支持最新的浏览器，很多老的jQuery插件不支持这个版本，相对1.x文件较小，提供不包含Ajax/动画API版本。
- 应该选择几点几版本jQuery?
  - 查看百度网页源码使用1.x
  - 查看腾讯网页源码使用1.x
  - 查看京东网页源码使用1.x
  - 综上所述学习1.x,选择1.x
- 应该使用开发板还是生产版?
  - 开发板: 所有代码没有经过压缩,体积更大(200-300KB)
  - 生产版:所有代码经过压缩,提及更小(30-40KB)
  - 初学者为了更好的理解jQuery编码时使用开发板,项目上线时为了提升访问速度使用生产版

... ...

### 如何使用jQuery？

- 下载jQuery库 
  - 下载地址: [http://code.jquery.com/](https://link.jianshu.com?t=http%3A%2F%2Fcode.jquery.com%2F) 
- 引入下载的jQuery库

```
<head>
    <meta charset="UTF-8">
    <title>01-初识jQuery</title>
    <script src="code/js/jquery-1.12.4.js"></script>
</head>
```

- 编写jQuery代码

```
<script>
    $(document).ready(function () {
      // 所有jQuery代码写在这里面
         alert("hello LNJ");
    });
</script>
```

### jQuery的入口函数

#### Jquery函数的4种写法

```
	$(document).ready(function (ev) {});  //1
```

```
	 jQuery(document).ready(function (ev) {}); //2
```

```
    $(function () {}) //3
```

```js
	Jquery(function () {}) //4
```

#### 同一个函数可以多次调用

```
	$(document).ready(function (ev) {
       console.log('a')
    });
    $(document).ready(function (ev) {
       console.log('b')
    });
```

#### 解决框架中有$符号的冲突，释放$的使用权

##### 注意点：释放操作必须在编写其它jQuery代码之前，释放之后就不能再使用$，改为使用jQuery

```
  	// 释放$
  	jQuery.noConflict(); 
```

#### 自定义一个访问符号

```
//自定义
var nj = jQuery.noConflict() 
jQuery(function () {
	alert('hello word')
})
```

#### Jquery的核心函数（$()）

##### 可以接收函数、字符串、字符串选择器、代码片段、接收DOM元素

```
    // 接收一个函数
    $(function () {
        // 字符串
        console.log('aaa')
        // 字符串选择器
        var $box1 = $('.box1');
        var $box2 = $('#box2');
        //代码片段
        var $p = $("<p>我是p标签</p>");
        console.log($	p);
        // DOM元素
        var span = document.getElementsByTagName('span')[0]
        console.log(span);
        var $span = $(span);
        console.log($span);
        
    })
```

##### JQuery对象是一个类数组：类数组有length，且有索引值

##### jQuery的静态方法和实例方法

```
    function Demo() {

    }
    // 静态方法
    Demo.static = function () {
        console.log('static')
    }
    Demo.staticMethod()
    // 实例方法
    Demo.prototype.instance = function () {
        console.log('instance')
    }
    var demo = new Demo()
    demo.instanceMethod()
```

#### jQuery的静态方法

##### 开始代码

```
        // 数组
        var arr = [1, 2, 3, 4, 5]
        // 类数组
        var arr2 = {
            '0' : "1",
            '1' : "2",
            "2" : "3",
            length: 3,
            push: Array.prototype.push
        }
        // 对象
        var obj = {name: 'ppp', age: '18'}
        // 函数
        var fn = function () {}
        // window对象
        var w = window;
        //两端有空格字符串的字符
        var str = '   obj   ';
```

#### jQuery的each()方法

##### 可以遍历类数组和数组，返回值的是当前遍历的数组，不能手动更改返回值

```
	   var a = $.each(arr, function (value, index) {
            console.log(value, index)
            return 123;
        })
        // 遍历类数组
        $.each(obj, function (value, index) {
            console.log(value, index)
        })
```

#### jQuery的map()方法

##### 可以遍历数组和类数组，默认的返回值是空数组，可以手动更改返回值

```
		var a = $.map(arr, function (value, index) {
            console.log(index, value);
            return index + value
        })
        console.log(a)
        // // 遍历类数组
        $.map(obj, function (value, index, array) {
            console.log(index, value, array)
        })
```

#### jQuery的trim()方法

##### 去除字符串两端的空格

```
		var res = $.trim(str)
        console.log('111'+str+'1111')
        console.log('111'+res+'1111')
```

#### jQuery的静态方法

##### 判断传入的对象是不是window对象

```
	var a = window;
	console.log(a);
```

##### isArray()方法,判断传入的值是否是真数组

```
		var a = [];
        console.log($.isArray(a))
```

##### isFunction()方法，判断传入的值是否是函数

```
    	var a = function () {}
    	console.log($.isFunction(a));
```

##### jQuery的holdReady()方法(理解)

###### 作用：点击时才触发jquery的函数

```
    var btn = document.getElementsByTagName('button')[0];
    //当btn点击后    
    btn.onclick = function () {
    	//开始执行holdReady函数
        $.holdReady(false)
    }
    暂停holdReady入口函数
    $.holdReady(true);
    $(function () {
        console.log('a')
    })
```

#### jQuery的内容选择器，

##### :empty 选择即没有文本内容，也没有子元素的指定元素

##### :parent 选择有文本内容或者有子元素的指定元素

##### :contains(text), 选择有包含文本内容的指定元素

##### :has(selector),  选择包含子元素的指定元素

```
        var $div = $("div:empty")
        var $div = $("div:parent")
        var $div = $("div:contains('1')");
        var $div = $('div:has("span")');
        console.log($div)
```

#### jQuery的属性和属性节点，dom元素上才有的

##### jQuery的attr()方法

##### 获取和设置元素属性值

```
		 // 获取所有span元素，只能返回第一个span元素的属性值
        console.log($('span').attr("name"))
        // 设置元素的属性值，可以全部设置
        console.log($('span').attr('class', 'demo'))
```

#### jQuery的removeAttr()方法

##### 删除元素属性值

```
        // 删除指一个属性值
        // $('span').removeAttr('class')
        // 删除多个属性值
        // $('span').removeAttr('class name')
```

#### jQuery的prop()方法 ，具有true和false上的属性节点使用

##### 获取和设置元素属性值

```
        // 获取指定的所有元素,只能返回第一个span元素的指定属性值
        // console.log($('span').prop('class'))
        // 设置指定元素的属性值,可设置多个
        // console.log($('span').prop('class', '111'))
```

#### jQuery的removeprop()方法 具有true和false上的属性节点使用

##### 删除元素的属性值

```
        // 删除一个属性值
        // console.log($('span').removeProp('class'));
        // 删除多个属性值
        // console.log($('span').removeProp('class name'));
```

#### jQuery的attr和prop的小练习

##### 点击切换图片地址

```
       // 点击切换图片
        var btn = document.getElementsByTagName('button')[0];   
        btn.onclick = function () {
            // 获取input输入框的内容
            var input = document.getElementsByTagName('input')[0];
            var value = input.value;
            //设置好切换的value
            $('img').attr('src', value)
        }
```

#### jQuery类的操作方法

#####  添加类方法 addClass()

##### 删除类方法 removeClass()

##### 切换类方法 toggleClass()

```
var btn = document.getElementsByTagName('button');
        btn[0].onclick = function () {
            // 添加一个类
            $("div").addClass("add");
            // 添加多个类
            $('div').addClass('add2');
        }
        btn[1].onclick = function () {
            // 删除一个类
            $('div').removeClass('add'); 
            // 删除多个类
            $('div').removeClass('add add2');
        }
        btn[2].onclick = function () {
            // 切换一个类
            $('div').toggleClass('add');
            // 切换多个类
            $('div').toggleClass('add add2');
        }
```

#### jQuery文本值操作方法

##### html()方法

##### text()方法

##### val()方法

```
        btn[0].onclick = function () {
            // 设置html
            $('div').html("<p>我是段落</p>")
        }
        btn[1].onclick = function () {
            // 获取html
            console.log($('div').html())
        }
        btn[2].onclick = function () {
            // 设置文本值
            $('div').text("我是段落")
        }
        btn[3].onclick = function () {
            // 获取文本值
            console.log($('div').text())
        }
        btn[4].onclick = function () {
            // 设置value值
            $('input').val('请输入内容')
        }
        btn[5].onclick = function () {
            // 获取value值
            console.log($('input').val())
        }
```

#### jQuery操作CSS样式方法

#####  样式操作方法css()

```
        $('div').css('width', '100px')
        $('div').css('height', '100px')
        $('div').css('background-color', 'blue')
        // 链式调用，链式操作如果大于三步，建议分开
        $('div').css('width', '100px').css('height', '100px').css('background-color', 'red');
        // 批量设置
        $('div').css({
            width: '100px',
            height: '100px',
            background: 'gray'
        })
        // 获取css样式值
        console.log($('div').css('width'))
```

#### jQuery操作尺寸和位置的方法

##### width()方法

##### innerWidth()方法

##### outerWidth()方法

```
        btn[0].onclick = function () {
            // 获取元素宽度
            console.log($('.father').width())
            // 获取元素宽度+左右内边距  
            console.log($('.father').innerWidth())
            //获取元素宽度+左右内边距+左右边框宽度
            console.log($('.father').outerWidth())
            // 获取元素距离文档的位置
            console.log($('.son').offset().left)
            // 获取元素距离定位元素的偏移,不能设置
            console.log($('.son').position().left);
        }
        btn[1].onclick = function () {
            // 设置元素的宽度
            $('.father').width('200px');
            //设置元素的总宽度-左右内边距
            $('.father').innerWidth('200px');
            // 设置元素的总宽度-左右内边距-左右边框
            $('.father').outerWidth('200px');
            // 设置元素距离文档的位置
            $('.son').offset({
                left: 10
            })
        }
```

#### jQuery的scrollTop()方法掌握

```
        // scrollTop方法
        btn[0].onclick = function () {
            // 获取元素滚动的位置
            console.log($('.scroll').scrollTop());
            // 获取网页滚动的位置，兼容ie。ie使用body
            console.log($('html').scrollTop() || $('body').scrollTop())
        }
        btn[1].onclick = function () {
            // 设置元素滚动的位置
            $('.scroll').scrollTop(300)
            // 设置网页滚动的位置,兼容ie.ie使用body
            $('html, body').scrollTop(100)
        }
```

#### jQuery的事件绑定

```
        // 第一种,建议使用.部分js事件没有添加
        $('button').click(function () {
            alert('hello world')
        })
        // 同一个元素可以绑定多个不同类型的事件
        $('button').click(function () {
            console.log('a')
        })
        $('button').click(function () {
            console.log('b')
        })
        // 第二种,不建议使用!所有js事件都可以添加
        $("button").on("click", function () {
            alert('hello world')
        })
        // 同一个元素可以绑定多个不同类型的事件
        $('button').on('click', function () {
            console.log('a')
        })
        $('button').on('mouseover', function () {
            console.log('b')	
        })
```

#### jQuery的事件解除绑定

```
        function test() {
            console.log('a')
        }
        function test2() {
            console.log('b')
        }
        $('button').click(test)
        $('button').on('click', test2)
        $('button').mouseenter(function () {
            console.log('c')
        })
        $('button').mouseleave(function () {
            console.log('d')
        })
        // 解除一个
        $('button').off('mouseenter')
        // 解除指定类型的指定事件
        $('button').off('click', test1)
        // 解除所有
        $('button').off()
```

#### jQuery的事件冒泡和默认行为

```
$('.father').on('click', function (event) {
            console.log('father');
        //     // 阻止事件冒泡
        //     // 第一种
            return false;
        //     // 第二种
            event.stopPropagation()
        })
        $(document).click(function () {
            console.log('document')
        })
        $('a').click(function (event) {
            console.log('弹出注册框');
            // 阻止默认事件
            // 第一种
            return false;
            // 第二种
            event.preventDefault();
        })
```

#### jQuery事件自动触发

```
		$('a').click(function () {
            console.log('a')
        })
        // 事件自动触发
        // 第一种
        // 会触发事件冒泡
        $('.father').trigger('click');
        // 会触发默认行为
        $("input[type='submit']").trigger('click');
        // a标签必须在里面包含一层元素，事件自动触发才会有效
        $('a > span').trigger('click');
        
        // 第二种
        // 不会触发事件冒泡
        $('.father').triggerHandler('click');
        // 不会触发默认行为
        $("input[type='submit']").triggerHandler('click');
        $('a').triggerHandler('click');
        
        //如果想用trigger触发a的事件且触发a的默认行为的解决方法
        <a href="www.baidu.com"><span>百度</span></a>
        $("span").click(function () {});
        $("span").trigger("click");
```

#### jQuery的自定义事件

```
        // 事件必须是通过on绑定的
        // 事件必须通过trigger来触发
        $('.father').on('myClick', function () {
            console.log('a')
        })
        $('.father').trigger('myClick')
```

#### jQuery事件命名空间

```
        // 事件必须是通过on绑定的
        // 必须通过trigger触发事件
        // 父级元素相同的命名空间的事件也会被子元素的事件触发，不相同不触发
        $('.father').on('click.p', function () {
            console.log('a')
        })
        $('.father').on('click.d', function () {
            console.log('b')
        });
        $(document).on('click', function () {
        	console.log('a');
    	});
        $(document).on('click.p', function () {
            console.log('a');
        });
        $('.father').trigger('click.p')
        $('.father').trigger('click.d')
```

#### jQuery事件委托

```
       // 事件的委托
        $('button').on('click', function () {
            $('ul').append('<li>我是新增的li</li>');
        })
        $('ul').delegate('li', "click", function () {
            console.log($(this).html())
        })
```

#### jQuery移入移出事件

```
		// 移入移出事件
        // 第一种，子元素被移入移出会触发父元素事件
        $(".father").on('mouseover', function () {
            console.log('mouseover')
        })
        $(".father").on('mouseout', function () {
            console.log('mouseout')
        })
        // 第二种，子元素被移入移出不会触发父元素事件
        $('.father').on('mouseenter', function () {
            console.log('mouseenter')
        })
        $('.father').on('mouseleave', function () {
            console.log('mouseleave')
        })
        // 第三种，子元素被移入移出不会触发父元素事件
        // 移入移出效果
        $('.father').hover(function () {
            console.log('移入移出')
        });
        $('.father').hover(function () {
            console.log('移入')
        }, function () {
            console.log('移出')
        })
```

#### jQuery的显示隐藏动画

```
        // 显示和隐藏动画
       $('button').eq(0).on('click', function () {
           // 显示
           $('div').show(1000, function () {
                // 动画结束后调用
                console.log('aaa')
           })
       })
       $('button').eq(1).on('click', function () {
            // 隐藏
            $('div').hide(1000, function () {
                //动画结束后调用
                console.log('bbb')
            })
       })
       $('button').eq(2).on('click', function () {
            // 切换
            $('div').toggle(1000, function () {
                //动画切换后调用
                console.log('ccc')
            })
       })
```

#### jQuery的展开和收起动画

```
        // 展开和收起动画
        $('button').eq(0).on('click', function () {
            // 展开
            $('div').slideDown(1000, function () {
                // 展开完成
                console.log('展开完成')
            });
        })
        $('button').eq(1).on('click', function () {
            // 收起
            $('div').slideUp(1000, function () {
                //收起完成
                console.log('收起')
            })
        })
        $('button').eq(2).on('click', function () {
            //展开和收起
            $('div').slideToggle(1000, function () {
                //展开收起完毕
                console.log('展开收起完毕')
            })
        })
```

#### jQuery淡入淡出动画

```
        // 淡入和淡出动画
        $('button').eq(0).on('click', function () {
            //淡入
            $('div').fadeIn(1000,function () {
                console.log('淡入完毕')
            })
        })
        $('button').eq(1).on('click', function () {
            //淡出
            $('div').fadeOut(1000, function () {
                console.log('淡出完毕')
            })
        })
        $('button').eq(2).on('click', function () {
            // 切换
            $('div').fadeToggle(1000, function () {
                console.log('切换完毕')
            })
        })
        $('button').eq(3).on('click', function () {
            // 淡入透明值自定义
            $('div').fadeTo(1000, .5, function () {
                console.log('淡入到完毕')
            })
        })
```

#### jQuery自定义动画

第一个参数：接收一个对象，可以在对象中修改属性

第二个参数：指定动画时长

第三个参数：指定动画节奏，默认就是swing

第四个参数：动画执行完毕之后的回调函数

```
	    $('button').eq(0).on('click', function () {
            //操作属性
            // $('.one').animate({width: 500}, 1000, function () {
            //     console.log('动画执行完毕')
            // })
            $('.one').animate({width: 500}, 1000, 'linear', function () {
                console.log('动画执行完毕')
            })
        })
        $('button').eq(1).on('click', function () {
            //累加属性
            $('.one').animate({width: '+=500'}, 1000, function () {
                console.log('动画执行完毕')
            })
        })
        $('button').eq(2).on('click', function () {
            // 关键字
           $('.one').animate({width: 'toggle'}, 1000, function () {
               console.log('over')
           })
        })
```

#### jQuery的stop和delay方法

```
 		$('button').eq(1).on('click', function () {
            // 立即停止当前动画,继执行后续动画
            $('.one').stop();
            $('.one').stop(false)
            $('.one').stop(false, false)
            // 立即停止当前和后续所有的动画
            $('div').stop(true);
            $('div').stop(true, false)
            // 立即完成当前的，继续执行后续动画
            $('div').stop(false, true)
            // 立即完成当前的，并且停止后续所有动画
            $('div').stop(true, true)
            //delay方法，延迟执行 
            $('div').animate({width: 200}, 1000).delay(1000).animate({height: 200});
        });
```

#### jQuery中添加节点的方法

```
        $('button').on('click', function () {
            // 创建节点
            var $li = $("<li>新增的li</li>")
            // 添加节点到指定元素内的最后
            // 第一种
            $('ul').append($li)
            //第二种
            $li.appendTo('ul')
            // 添加节点到指定元素内的首位
            // 第一种
            $('ul').prepend($li)
            $li.prependTo('ul')
            // 添加节点到指定元素的后一位
            // 第一种
            $('div').after($li)
            // 第二种
            $li.insertAfter('div');
            // 添加节点到指定元素的前一位
            // 第一种
            $('div').before($li)
            // 第二种
            $li.insertBefore('div');
        })
```

#### jQuery删除节点的方法

```
        //删除节点的方法 
        $('button').on('click', function () {
            // 删除
            // 指定元素
            // 第一种
            $('div').remove();
            // 第二种
            $('div').detach()
            // 指定元素下的节点
            $('div').empty();
            // 指定元素的指定节点
            // 第一种
            $('li').detach('.item')
            // 第二种
            $('li').remove('.item')
        })
```

#### 替换节点的方法

```
        //替换节点的方法 
        $('button').on('click', function () {
            // 新建节点
            var $h6 = $('<h6>我是h6</h6>')
            // 替换所有指定元素的指定节点
            // 第一种
            $('div').replaceWith($h6)
            // 第二种
            $h6.replaceAll('div')
        })
```

#### 复制节点的方法

```
        //复制节点的方法
        $('button').eq(0).on('click', function () {
            // 浅复制，不会复制元素的事件
            var $li = $("ul li:first").clone(false)
            // 添加节点
            $('ul').append($li)
        })
        $('button').eq(1).on('click', function () {
            // 深复制，会复制元素的事件
            var $li = $("ul li:first").clone(true)
            // 添加节点
            $('ul').append($li)
        })
        $('li').on('click', function () {
            console.log('a  ')
        })
```

​	

