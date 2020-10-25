# Ajax

#### AJAX是与服务器在不重新加载整个页面的情况下更新部分网页的艺术

##### GET基本使用方式

```
    window.onload = function (ev) {
        var btn = document.getElementsByTagName('button')[0];
        btn.onclick= function (ev1) {
            //1.创建一个异步对象
            var xmlhttp = new XMLHttpRequest();
            // 2.设置请求方式和请求地址
            // 传三个参数
            // method: 请求的类型：GET或POST
            // url: 文件在服务器上的位置
            // async: true(异步)或false(同步)
            xmlhttp.open("GET", "PHP.php", true);
            // 3.发送请求
            xmlhttp.send();
            // 4.监听状态的变化
             xmlhttp.onreadystatechange = function () {
                 /*
                  0: 请求未初始化
                  1: 服务器连接已建立
                  2: 请求已接收
                  3: 请求处理中
                  4: 请求已完成，且响应已就绪
                 */
                 if(xmlhttp.readyState === 4) {
                     // 判断是否请求成功
                     if(xmlhttp.status >= 200 && xmlhttp.status < 300 || xmlhttp.status === 304) {
                         // 5.处理返回的结果
                         console.log('返回数据成功');
                     }else{
                         console.log('没有接收到服务器的数据');
                     }
                 }
             }

        }
    }
```

##### GET兼容IE的写法

```
    window.onload = function (ev) {
        var btn = document.getElementsByTagName('button')[0];
        btn.onclick= function (ev1) {
            // 创建一个异步对象 兼容IE
            var xhr;
            if(window.XMLHttpRequest) {
                xhr = new XMLHttpRequest();
            }else{
                xhr = new ActiveXObject("Microsoft.XMLHTTP");
            }
            // 在IE浏览器中，通过Ajax发送get请求只能发送一次，状态改变后不会改变
            // 设置请求的地址和方式
            xhr.open("GET", 'PHP.text?t'+(new Date().getTime()), true);
            // 发送请求
            xhr.send();
            // 监听状态的变化
            xhr.onreadystatechange = function (ev2) {
                // 监听最后一个状态
                if(xhr.readyState === 4) {
                    // 判断状态码的数值
                    if(xhr.status >= 200 && xhr.status < 300 || xhr.status === 304) {
                        console.log(xhr.responseText);
                    }else{
                        console.log("请求失败");
                    }
                }
            }
        }
    }

```

##### GET完整封装

```
         function obj2str(obj) {
                obj.t = new Date().getTime();
                var res = [];
                for(var prop in obj) {
                    // 在url中是不可以出现中文的，encodeURIComponent可以把中文转码
                    res.push(encodeURIComponent(prop) + "=" + encodeURIComponent(obj[prop]));
                }
                return res.join("&");
            }
        // 封装Ajax
        function ajax(url, obj, timeout, success, error) {
            // 将对象转换为字符串
            var str = obj2str(obj);
            // 创建一个异步对象 兼容IE
            var xmlhttp;
            if(window.XMLHttpRequest) {
                xmlhttp = new XMLHttpRequest();
            }else{
                xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
            }
            // 在IE浏览器中，通过Ajax发送get请求只能发送一次，状态改变后不会改变
            // 设置请求的地址和方式
            xmlhttp.open("GET", url+"?"+str, true);
            // 发送请求
            xmlhttp.send();
            // 监听状态的变化
            xmlhttp.onreadystatechange = function () {
                // 监听最后一个状态
                if(xmlhttp.readyState === 4) {
                    clearInterval(timer);
                    // 判断状态码的数值
                    if(xmlhttp.status >= 200 && xmlhttp.status < 300 || xmlhttp.status === 304) {
                       success(xmlhttp);
                    }else{
                        error(xmlhttp);
                    }
                }
            }
            //判断外界是否传入了超时的时间
            if(timeout) {
                timer = setInterval(function () {
                    console.log("中断请求");
                    xmlhttp.abort();
                    clearInterval(timer);
                }, timeout)
            }
        }
```

##### POST基本

```
            // 创建一个异步对象 兼容IE
            var xhr;
            if(window.XMLHttpRequest) {
                xhr = new XMLHttpRequest();
            }else{
                xhr = new ActiveXObject("Microsoft.XMLHTTP");
            }
            // 在IE浏览器中，通过Ajax发送get请求只能发送一次，状态改变后不会改变
            // 设置请求的地址和方式
            xhr.open("POST", 'PHP.php', true);
            // 注意点：以下代码必须放到open和send之间
            xhr.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
            // 发送请求
            xhr.send("userName=zs&userPwd=321");
            // 监听状态的变化
            xhr.onreadystatechange = function () {
                // 监听最后一个状态
                if(xhr.readyState === 4) {
                    // 判断状态码的数值
                    if(xhr.status >= 200 && xhr.status < 300 || xhr.status === 304) {
                        console.log(xhr.responseText);
                    }else{
                        console.log("请求失败");
                    }
                }
            }
```

##### POST封装

```
 function obj2str(obj) {
                obj.t = new Date().getTime();
                var res = [];
                for(var prop in obj) {
                    // 在url中是不可以出现中文的，encodeURIComponent可以把中文转码
                    res.push(encodeURIComponent(prop) + "=" + encodeURIComponent(obj[prop]));
                }
                return res.join("&");
            }
            // 封装Ajax
            function ajax(type, url, obj, timeout, success, error) {
                // 将对象转换为字符串
                var str = obj2str(obj);
                // 创建一个异步对象 兼容IE
                var xmlhttp;
                if(window.XMLHttpRequest) {
                    xmlhttp = new XMLHttpRequest();
                }else{
                    xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
                }
                if(type === "GET") {
                    // 在IE浏览器中，通过Ajax发送get请求只能发送一次，状态改变后不会改变
                    // 设置请求的地址和方式
                    xmlhttp.open(type, url+"?"+str, true);
                    // 发送请求
                    xmlhttp.send();
                    // 监听状态的变化
                }else if(type === "POST") {
                    xmlhttp.open(type, url, true);
                    // 注意点：以下代码必须放到open和send之间
                    xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
                    // 发送请求
                    xmlhttp.send(str);
                }
                xmlhttp.onreadystatechange = function () {
                    // 监听最后一个状态
                    if(xmlhttp.readyState === 4) {
                        clearInterval(timer);
                        // 判断状态码的数值
                        if(xmlhttp.status >= 200 && xmlhttp.status < 300 || xmlhttp.status === 304) {
                            success(xmlhttp);
                        }else{
                            error(xmlhttp);
                        }
                    }
                }
                //判断外界是否传入了超时的时间
                if(timeout) {
                    timer = setInterval(function () {
                        console.log("中断请求");
                        xmlhttp.abort();
                        clearInterval(timer);
                    }, timeout)
                }
            }
```

##### jQuery封装

```
function obj2str(data) {
    data.t = new Date().getTime();
    var res = [];
    for(var prop in data) {
        // 在url中是不可以出现中文的，encodeURIComponent可以把中文转码
        res.push(encodeURIComponent(prop) + "=" + encodeURIComponent(data[prop]));
    }
    return res.join("&");
}
// 封装Ajax
function ajax(option) {
    // 将对象转换为字符串
    var str = obj2str(option.data);
    // 创建一个异步对象 兼容IE
    var xmlhttp;
    if(window.XMLHttpRequest) {
        xmlhttp = new XMLHttpRequest();
    }else{
        xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
    }
    if(option.type.toLowerCase() === "get") {
        // 在IE浏览器中，通过Ajax发送get请求只能发送一次，状态改变后不会改变
        // 设置请求的地址和方式
        xmlhttp.open(option.type, option.url+"?"+str, true);
        // 发送请求
        xmlhttp.send();
        // 监听状态的变化
    }else if(option.type === "POST") {
        xmlhttp.open(option.type, option.url, true);
        // 注意点：以下代码必须放到open和send之间
        xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
        // 发送请求
        xmlhttp.send(str);
    }

    xmlhttp.onreadystatechange = function () {
        // 监听最后一个状态
        if(xmlhttp.readyState === 4) {
            clearInterval(timer);
            // 判断状态码的数值
            if(xmlhttp.status >= 200 && xmlhttp.status < 300 || xmlhttp.status === 304) {
                option.success(xmlhttp);
            }else{
                option.error(xmlhttp);
            }
        }
    }
    //判断外界是否传入了超时的时间
    if(option.timeout) {
        timer = setInterval(function () {
            console.log("中断请求");
            xmlhttp.abort();
            clearInterval(timer);
        }, option.timeout)
    }
}
```

##### xml

```

```

