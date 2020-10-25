#### JSON是一种传输数据的格式（以对象为样板，本质上就是对象，但用途有区别，对象就是本地用的，json是用来传输的）

2、JSON.parse(); string — > json 

3、JSON.stringify(); json — > string

```
      var obj = {
        "name": 'deng',
        "age": 123
      }
      var obj1 = {
        name: 'deng',
        age: 123
      }
      
      console.log(JSON.stringify(obj1))
```

绘制dom树，符合深度优先（纵向）原则，比如先看head → title → meta →body → div → strong → span。

#### 异步加载js

js是单线程的，会阻断HTML，css加载（因为js会修改html和css一起加载会乱），所以是同步加载js。先下载js，再下载HTML和css。常规来说js是同步加载的，所以我们讲讲js异步加载的情况

 一、js加载的缺点：加载工具方法没必要阻塞文档，过渡js加载会影响页面效率，一旦网速不好，那么整个网站将等待js加载而不进行后续渲染等工作。 

二、有些工具方法需要按需加载，用到再加载，不用不加载。

 三、javascript 异步加载的三种方案

 1、defer 异步加载，但要等到dom文档全部解析完（dom树生成完）才会被执行。只有IE9以下能用。
dom文档全部解析完，不代表整个页面加载完 

2、async 异步加载，加载完就执行，async只能加载外部脚本，不能把js写在script 标签里。ie9以上可以用，w3c标准

##### 判断一个网页加载完成

script.readyState = “loading”;    最开始的值

script.readyState = 'complete'   “complete”;或者“leaded”表示加载完成

```
        function loadScript(url, callback) {
          var script = document.createElement('script');
          if(script.readyState) {
            script.onreadystatechange = function () {
              if(script.readyState == "complete" || script.readyState == 'loaded') {
                callback();
              }
            }
          }else{
            script.onload = function () {
              callback();
            }
          }
          script.src = url;
          document.head.appendChild(script);
        }
        
        loadScript("index.js", function () {
          test();
        })
```

#### js加载时间线（可以理解成浏览器加载时间线)

##### js加载时间线（可以理解成浏览器加载时间线)

js时间线步骤（创建document对象==>文档解析完==>文档解析完加载完执行完）

1、创建Document对象，开始解析web页面。解析HTML元素和他们的文本内容后添加Element对象和Text节点到文档中。这个阶段document.readyState = 'loading'。

2、遇到link外部css，创建线程，进行异步加载，并继续解析文档。

 3、遇到script外部js，并且没有设置async、defer，浏览器同步加载，并阻塞，等待js加载完成并执行该脚本，然后继续解析文档。 

4、遇到script外部js，并且设置有async、defer，浏览器创建线程异步加载，并继续解析文档。

对于async属性的脚本，脚本加载完成后立即执行。（异步禁止使用document.write()，因为当你整个文档解析到差不多，再调用document.write()，会把之前所有的文档流都清空，用它里面的文档代替）

5、遇到img等（带有src），先正常解析dom结构，然后浏览器异步加载src，并继续解析文档。 看到标签直接生产dom树，不用等着img加载完src。

6、当文档解析完成（domTree建立完毕，不是加载完毕），document.readyState = 'interactive'。

7、文档解析完成后，所有设置有defer的脚本会按照顺序执行。（注意与async的不同,但同样禁止使用document.write()）;

8、document对象触发DOMContentLoaded事件，这也标志着程序执行从同步脚本执行阶段，转化为事件驱动阶段。

9、当所有async的脚本加载完成并执行后、img等加载完成后（页面所有的都执行加载完之后），document.readyState = 'complete'，window对象触发load事件。

10、从此，以异步响应方式处理用户输入、网络事件等。

##### window.onload会等整个页面加载完才执行，消除文档流（把自己script删了）

```
     <div style="width: 100px;height: 100px;background-color: red"></div>
     window.onload = function() {
        document.write('a')
      }
```

##### 判断是否加载完毕

```
      console.log(document.readyState);
      
      document.onreadystatechange = function () {
        console.log(document.readyState);
      }

      document.addEventListener('DOMContentLoaded', function () {
        console.log('a')
      }, false)
```

