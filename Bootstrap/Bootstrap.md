# Bootstrap

#### 基本模板

```
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@3.3.7/dist/css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim 和 Respond.js 是为了让 IE8 支持 HTML5 元素和媒体查询（media queries）功能 -->
    <!-- 警告：通过 file:// 协议（就是直接将 html 页面拖拽到浏览器中）访问页面时 Respond.js 不起作用 -->
    <!--[if lt IE 9]>
      <script src="https://cdn.jsdelivr.net/npm/html5shiv@3.7.3/dist/html5shiv.min.js"></script>
      <script src="https://cdn.jsdelivr.net/npm/respond.js@1.4.2/dest/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <h1>你好，世界！</h1>

    <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
    <script src="https://cdn.jsdelivr.net/npm/jquery@1.12.4/dist/jquery.min.js"></script>
    <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@3.3.7/dist/js/bootstrap.min.js"></script>
  </body>
</html>
```

#### 设置字体的大小

```
            <!-- h1 -->
            <div class="h1">Bootstrap标题一</div>      
            <!-- h2 -->
            <div class="h2">Bootstrap标题二</div>
            <!-- h3 -->
            <div class="h3">Bootstrap标题三</div>
            <!-- h4 -->
            <div class="h4">Bootstrap标题四</div>
            <!-- h5 -->
            <div class="h5">Bootstrap标题五</div>
            <!-- h6 -->
            <div class="h6">Bootstrap标题六</div>
```

#### 副标题

##### 注意：当标题是（h1~h3）时，small副标题的大小是当前字体大小的65%

##### 			当标题是（h4~h6）时，small副标题的大小是当前字体大小的75%

```
<h1>孤儿院无私奉献30年<small>一曲人性的赞歌</small></h1>
```

#### 强调内容  (.lead)

```
<p class="lead">这部分内容需要特别的强调，我和别人长得不一样</p>
```

#### 强调相关的类

##### （.text-muted）:提示，使用浅灰色（#999）

##### （.text-primay）:提示，使用蓝色（#428bca）

##### （.text-success）:提示，使用绿色（#3c763d）

##### （.text-info）:通知信息，使用浅蓝色（#31708f）

##### （.text-warning）警告，使用黄色（#8a6d3b）

##### （.text-danger）危险，使用褐色（#a94442）

```
            <!-- 文本强调的类 -->
            <!-- 提示 -->
            <div class="text-muted">提示效果</div>
            <!-- 主要 -->
            <div class="text-primary">主要</div>
            <!-- 成功 -->
            <div class="text-success">成功</div>
            <!-- 通知 -->
            <div class="text-info">通知</div>
            <!-- 警告 -->
            <div class="text-warning">警告</div>
            <!-- 危险 -->
            <div class="text-danger">危险</div>
```

#### 文本对齐风格

##### （.text-left）:左对齐

##### （.text-right）:右对齐

##### （.text-center）:居中对齐

##### （.text-justify）:两端对齐

```
            <!-- 文本对齐风格 -->
            <!-- 左 -->
            <div class="text-left">左</div>
            <!-- 右 -->
            <div class="text-right">右</div>
            <!-- 居中 -->
            <div class="text-center">居中</div>
            <!-- 两端 -->
            <div class="text-justify">两端</div>
```

#### 去点列表

##### (.list-unstyled)

```
            <ul class="list-unstyled">
                <li>1</li>
                <li>2</li>
                <li>3</li>
                <li>4</li>
                <li>5</li>
            </ul>
```

#### 内联列表

##### (.list-inline)

```
        <ul class="list-inline">
            <li>北京</li>
            <li>上海</li>
            <li>南京</li>
            <li>厦门</li>
        </ul>
```

#### 定义列表

```
        <dl>
            <dt>北京</dt>
            <dd>北京是中国的首都，是政治文化集中地</dd>
            <dt>上海</dt>
            <dd>上海号称东方的巴黎</dd>
        </dl>
```

#### 水平定义列表

##### （.di-horizontal）

```
    <dl class="dl-horizontal">
        <dt>标题一</dt>
        <dd>描述内容</dd>
        <dt>标题二</dt>
        <dd>描述内容</dd>
    </dl>
```

#### 代码风格

```
 	<!-- 第一种 -->
    <code>fdafdas</code>
    <!-- 第二种 -->
    <pre>dafdas</pre>
    <!-- 第三种  -->
    <kbd>fdarkjq</kbd>
```

#### 自定义代码块

##### （.pre-scrollable）

```
    <!-- 控制代码块的高度 -->
    <pre class="pre-scrollable">
            <ol>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
                <li>....</li>
            </ol>
    </pre>
```

#### 表格

##### （.table）基础表格

##### （.table .table-striped）斑马表格

##### （.table .table-bordered）带边框的表格

##### （.table .table-striped .table-hover）鼠标悬浮高亮表格

##### （.table table-condensed）紧凑型表格

##### （.table-responsive > .table) 响应式表格

```
    <!-- 基础表格 -->
    <table class="table">
        <thead>
            <tr>
                <th>表格标题</th>
                <th>表格标题</th>
                <th>表格标题</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>表格单元格</td>
                <td>表格单元格</td>
                <td>表格单元格</td>
            </tr>
        </tbody>
    </table>
    <!-- 斑马线表格 -->
    <table class="table table-striped">
        <thead>
            <tr>
                <th>表格标题</th>
                <th>表格标题</th>
                <th>表格标题</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>表格内容</td>
                <td>表格内容</td>
                <td>表格内容</td>
            </tr>
        </tbody>
    </table>
    <!-- 带边框的表格 -->
    <table class="table table-bordered">
        <thead>
            <tr>
                <th>表格标题</th>
                <th>表格标题</th>
                <th>表格标题</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>表格内容</td>
                <td>表格内容</td>
                <td>表格内容</td>
            </tr>
        </tbody>
    </table>
    <!-- 鼠标悬浮高亮表格 -->
    <table class="table table-striped table-hover">
        <thead>
            <tr>
                <th>表格标题</th>
                <th>表格标题</th>
                <th>表格标题</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>表格内容</td>
                <td>表格内容</td>
                <td>表格内容</td>
            </tr>
            <tr>
                <td>表格内容</td>
                <td>表格内容</td>
                <td>表格内容</td>
            </tr>
            <tr>
                <td>表格内容</td>
                <td>表格内容</td>
                <td>表格内容</td>
            </tr>
        </tbody>
    </table>
    <!-- 紧凑型表格 -->
    <table class="table table-condensed">
        <thead>
            <tr>
                <th>表格标题</th>
                <th>表格标题</th>
                <th>表格标题</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>表格内容</td>
                <td>表格内容</td>
                <td>表格内容</td>
            </tr>
            <tr>
                <td>表格内容</td>
                <td>表格内容</td>
                <td>表格内容</td>
            </tr>
        </tbody>
    </table>
    <!-- 响应式表格 -->
    <div class="table-responsive">
        <table class="table">
            <thead>
                <tr>
                    <th>表格标题</th>
                    <th>表格标题</th>
                    <th>表格标题</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>表格内容</td>
                    <td>表格内容</td>
                    <td>表格内容</td>
                </tr>
            </tbody>
        </table>
    </div>
```

#### 表格行的类

##### （.active）表示活动

##### （.success）表示成功或正确

##### （.info）表示中立的信息或行为

##### （.warning）表示警告

##### （.danger）表示危险	

```
    <table class="table table-bordered table-hover">
        <thead>
            <tr>
                <th>类名</th>
                <th>描述</th>
            </tr>
        </thead>
        <tbody>
            <tr class="active">
                <td>active</td>
                <td>表示当前活动的信息</td>
            </tr>
            <tr class="success">
                <td>success</td>
                <td>表示成功或正确</td>
            </tr>
            <tr class="info">
                <td>.info</td>
                <td>表示中立的信息或行为</td>
            </tr>
            <tr class="warning">
                <td>.warning</td>
                <td>表示警告，需要特别注意</td>
            </tr>
            <tr class="danger">
                <td>.danger</td>
                <td>表示危险或者可能是错误的行为</td>
            </tr>
        </tbody>
    </table>
```

#### 基础表单

##### role="form"

```
<form role="form">
  <div class="form-group">
    <label for="exampleInputEmail1">邮箱：</label>
    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="请输入您的邮箱地址">
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">密码</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="请输入您的邮箱密码">
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> 记住密码
    </label>
  </div>
  <button type="submit" class="btn btn-default">进入邮箱</button>
</form>	
```

#### 水平表单

##### (.form-horizontal)

```
        <form class="form-horizontal" role="form">
                <div class="form-group">
                  <label for="inputEmail3" class="col-sm-2 control-label">邮箱</label>
                  <div class="col-sm-10">
                    <input type="email" class="form-control" id="inputEmail3" placeholder="请输入您的邮箱地址">
                  </div>
                </div>
                <div class="form-group">
                  <label for="inputPassword3" class="col-sm-2 control-label">密码</label>
                  <div class="col-sm-10">
                    <input type="password" class="form-control" id="inputPassword3" placeholder="请输入您的邮箱密码">
                  </div>
                </div>
                <div class="form-group">
                  <div class="col-sm-offset-2 col-sm-10">
                    <div class="checkbox">
                      <label>
                        <input type="checkbox"> 记住密码
                      </label>
                    </div>
                  </div>
                </div>
                <div class="form-group">
                  <div class="col-sm-offset-2 col-sm-10">
                    <button type="submit" class="btn btn-default">进入邮箱</button>
                  </div>
                </div>
        </form>
```

#### 内联表单

##### (.form-inline)

```
        <form class="form-inline" role="form">
            <div class="form-group">
                <label for="exampleInputEmail2" class="sr-only">邮箱</label>
                <input type="email" class="form-control" id="exampleInputEmail2" placeholder="请输入您的邮箱地址">
            </div>
            <div class="form-group">
                <label for="exampleInputPassword2" class="sr-only">密码</label>
                <input type="password" class="form-control" id="exampleInputPassword2" placeholder="请输您的邮箱密码">
            </div>
            <div class="checkbox">
                <label>
                    <input type="checkbox">记住密码
                </label>
            </div>
            <button type="submit" class="btn btn-default">进入邮箱</button>
        </form>
```

#### 表单控件（输入框）

##### (.form-control)

```
        <form role="form" class="form-inline">
            <div class="form-group">
                <input type="email" class="form-control" placeholder="Enter email">
                <input type="username" class="form-control" placeholder="username">
            </div>
        </form>
```

#### 表单控件（下拉选择框）

##### (.form-control)

```
    <div class="form-group">
        <select class="form-control">
            <option value="">踢足球</option>
            <option value="">游泳</option>
            <option value="">慢跑</option>
            <option value="">跳舞</option>
        </select>
    </div>
    <div class="form-group">
        <select class="form-control" multiple>
                <option value="">踢足球</option>
                <option value="">游泳</option>
                <option value="">慢跑</option>
                <option value="">跳舞</option>
        </select>
    </div>
```

#### 表单控件（文本域textarea）

##### （.form-control）

```
    <form rol="form">
        <div class="form-group">
            <textarea class="form-control" rows="3"></textarea>
        </div>
    </form>
```

#### 表单控件（复选框checkbox和单选 按扭radio）

```
    <form rol="form">
        <!-- 复选框 -->
        <h3>案例1</h3>
        <div class="checkbox">
            <label>
                <input type="checkbox" value="">
                记住密码
            </label>
        </div>
        <!-- 单选按扭 -->
        <div class="radio">
            <label>
                <input type="radio" name="optionRadios" id="optionsRadios" value="love">喜欢
            </label>
        </div>
        <div class="radio">
            <label>
                <input type="radio" name="optionRadios" id="optionsRadios1" value="hate">不喜欢
            </label> 
        </div>
    </form>
```

#### 表单控件（复选框和单选按扭水平排列）

##### （.radio-inline）: 水平排列

```
    <!-- 复选框和单选按扭水平排列 -->
    <form role="form">
            <label class="radio-inline">
                <input type="radio" value="option1" name="sex">男性
            </label>
            <label class="radio-inline">
                <input type="radio" value="option2" name="sex">女性
            </label>
            <label class="radio-inline">
                <input type="radio" value="option3" name="sex">中性
            </label>
    </form>
```

#### 表单控件（按扭）

##### （.btn）：默认按扭

##### （.btn-primary） ：主

##### （.btn-info） ：信息

##### （.btn-success）：成功

##### （.btn-warning）：警告

##### （.btn-danger）：危险

##### （.btn-inverse）：替代深灰色的按扭

```
    <!-- 表单控件（按扭） -->
    <!-- 默认按扭 -->
    <button class="btn">Default</button>
    <!-- 主 -->
    <button class="btn btn-primary">Primary</button>
    <!-- 信息 -->
    <button class="btn btn-info">Info</button>
    <!-- 成功 -->
    <button class="btn btn-success">success</button>
    <!-- 警告 -->
    <button class="btn btn-warning">warning</button>
    <!-- 危险 -->
    <button class="btn btn-danger">danger</button>
    <!-- 替代深灰色按扭,不做语义化使用 -->
    <button class="btn btn-inverse">inverse</button>
```

#### 表单控件状态（焦点状态）

##### （.input-lg）

```
   <form role="form" class="form-horizontal">
            <div class="form-group">
                <div class="col-xs-6">
                    <input class="form-control input-lg" type="text" placeholder="不是焦点状态下效果">
                </div>
                <div class="col-xs-6">
                    <input class="form-control input-lg" type="text" placeholder="焦点点状态下效果">
                </div>
            </div>
        </form>
```

#### 表单控件状态（禁用状态）

##### disabled ：属性

##### fieldset标签

```
  <form role="form" class="form-horizontal">
         <div class="form-group">
             <div class="col-xs-6">
                 <input type="text" class="form-control input-lg" placeholder="不是焦点下状态">
             </div>
             <!-- 禁用的表单 -->
             <div class="col-xs-6">
                 <input type="text" class="form-control input-lg" id="disabledInput" placeholder="表单已被禁用,不可输入" disabled>
             </div>
         </div>
     </form>
     <form role="form">
         <fieldset disabled>
             <!-- 禁用的输入框 -->
             <div class="form-group">
                 <label for="disabledTextInput">禁用的输入框</label>
                 <input type="text" id="disabledTextInput" class="form-control" placeholder="禁止输入">
             </div>
             <!-- 禁用的下拉框 -->
             <div class="form-group">
                 <label for="disableSelect">禁用的下拉框</label>
                 <select id="disableSelect" class="form-control">
                     <option value="">不可选择</option>
                 </select>
             </div>
             <!-- 禁用的复选框 -->
             <div class="checkbox">
                 <label for="">
                     <input type="checkbox"> 无法选择
                 </label>
             </div>
             <!-- 禁用的提交按扭   -->
             <button type="submit" class="btn btn-primary">提交</button>

             <legend>
                 <input type="text" class="form-control" placeholder="我没被禁用">
             </legend>
         </fieldset>
     </form>
```

#### 表单控件状态（验证状态）

```
    <!-- 不带图标的状态 -->
    <form role="form">
        <div class="form-group has-success">
            <label for="inputSuccess1" class="control-label">成功状态</label>
            <input type="text" class="form-control" id="cootrol-label" placeholder="成功状态">
        </div>

        <div class="form-group has-warning">
            <label for="inputWarning1" class="control-label">警告状态</label>
            <input type="text" class="form-control" id="inputWarning1" placeholder="警告状态">
        </div>
        
        <div class="form-group has-error">
            <label for="inputError1" class="control-label">错误状态</label>
            <input type="text" class="form-control" id="inputError1" placeholder="错误状态">
        </div>
    </form>
    <!-- 带图标的状态 -->
    <form role="form">
        <div class="from-group has-success has-feedback">
            <label for="inputSuccess1" class="control-label">成功状态</label>
            <input type="text" class="form-control" id="inputSuccess1" placeholder="成功状态">
            <span class="glyphicon glyphicon-ok form-control-feedback"></span>
        </div>
        <div class="form-group has-warning has-feedback">
            <label for="inputWarning1" class="control-label">警告状态</label>
            <input type="text" class="form-control" id="inputWarning1" placeholder="警告状态">
            <span class="glyphicon glyphicon-warning-sign form-control-feedback"></span>
        </div>
        <div class="form-group has-error has-feedback">
            <label for="inputError1" class="control-label">错误状态</label>
            <input type="text" class="form-control" id="inputError1" placeholder="错误状态">
            <span class="glyphicon glyphicon-remove form-control-feedback"></span>
        </div>
    </form>
```

#### 表单提示信息

```
    <!-- 样式一 -->
    <form role="form">
        <div class="form-group has-success has-feedback">
            <label class="control-label" for="inputSuccess1">成功状态</label>
            <input type="text" class="form-control" id="inputSuccess" placeholder="成功状态">
            <span class="help-block">你输入的信息是正确的</span>
            <span class="glyphicon glyphicon-ok form-control-feedback"></span>
        </div>
        <div class="form-group has-warning has-feedback">
            <label for="inputWarning1" class="control-label">警告状态</label>
            <input type="text" id="inputWarning1" class="form-control" placeholder="警告状态">
            <span class="help-block">请输入正确的信息</span>
            <span class="glyphicon glyphicon-warning-sign form-control-feedback"></span>
        </div>
        <div class="form-group has-error has-feedback">
            <label for="inputError1" class="control-label">错误状态</label>
            <input type="text" id="inputError1" class="form-control" placeholder="错误状态">
            <span class="help-block">你输入的信息是错误的</span>
            <span class="glyphicon glyphicon-remove form-control-feedback"></span>
        </div>
    </form>
    <!-- 样式二 -->
    <form role="form">
        <div class="form-group">
            <label for="inputSuccess1" class="control-label"></label>
            <div class="rows">
                <div class="col-xs-6">
                    <input type="text" class="form-control" id="inputSuccess1" placeholder="成功状态">
                </div>
                <span class="help-block col-xs-6">你输入的信息是正确的</span>
            </div>
        </div>
    </form>	
```

#### 按扭

```
    <!-- 按扭 -->
    <!-- 基础按扭 -->
    <button class="btn" type="button">基础按扭.btn</button>
    <!-- 默认按扭 -->
    <button class="btn btn-default" type="button">默认按扭</button>
    <!-- 主要按扭 -->
    <button class="btn btn-primary" type="button">主要按扭</button>
    <!-- 成功按扭 -->
    <button class="btn btn-success" type="button">成功按扭</button>
    <!-- 信息按扭 -->
    <button class="btn btn-info" type="button">信息按扭</button>
    <!-- 警告按扭 -->
    <button class="btn btn-warning" type="button">警告按扭</button>
    <!-- 危险按扭 -->
    <button class="btn btn-danger" type="button">危险按扭</button>
    <!-- 链接按扭 -->
    <button class="btn btn-link" type="button">链接按扭</button>
```

#### 按扭大小

##### （.btn-lg）: 大型按扭

##### （.btn-sm）: 小型按扭

##### （.btn-xs）: 超小型按扭

```
    <!-- 按扭大小 -->
    <!-- 正常按扭 -->
    <button class="btn btn-primary">正常按扭</button>
    <!-- 大型按扭 -->
    <button class="btn btn-primary btn-lg" type="button">大型按扭</button>
    <!-- 小型按扭 -->
    <button class="btn btn-primary btn-sm" type="button">小型按扭</button>
    <!-- 超小型按扭 -->
    <button class="btn btn-primary btn-xs" type="button">超小型按扭</button>
```

#### 块状按扭

##### （.btn-block）：块状按扭

```
    <!-- 块状按扭 -->
    <button class="btn btn-primary btn-lg btn-block">大型按扭</button>
    <button class="btn btn-primary btn-block">正常按扭</button>
    <button class="btn btn-primary btn-sm btn-block">小型按扭</button>
    <button class="btn btn-primary btn-xs btn-block">超小型按扭</button>
```

#### 按钮禁用状态

##### （.btn-disabled）：按扭禁用

```
    <!-- 按扭禁用 -->
    <!-- 第一种 -->
    <button disabled="disabled" type="button" class="btn btn-primary btn-block">禁用</button>
    <!-- 第二种 -->
    <button type="button" class="btn btn-primary disabled btn-block">禁用</button>
```

#### 图像

##### （.img-reponsive）：响应式图片，主要针对于响应式设计

##### （.img-rounded）：圆角图片

##### （.img-circle）： 圆形图片

##### （.img-thumbnail）：缩略图片

```
    <!-- 图像 -->
    <div class="container">
        <div class="row">
            <div class="col-sm-4">
                <img alt="150x150" src="http://e.hiphotos.baidu.com/image/h%3D300/sign=ab436e58aeec08fa390015a769ef3d4d/b17eca8065380cd7cd63680aaf44ad34588281dc.jpg" alt="">
                <div>默认图片</div>
            </div>
            <div class="col-sm-4">
                <img class="img-rounded" alt="150x150" src="http://e.hiphotos.baidu.com/image/h%3D300/sign=ab436e58aeec08fa390015a769ef3d4d/b17eca8065380cd7cd63680aaf44ad34588281dc.jpg" alt="">
                <div>圆角图片</div>
            </div>
            <div class="col-sm-4">
                <img class="img-circle" alt="150x150" src="http://e.hiphotos.baidu.com/image/h%3D300/sign=ab436e58aeec08fa390015a769ef3d4d/b17eca8065380cd7cd63680aaf44ad34588281dc.jpg" alt="">
                <div>圆形图片</div>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-6">
                <img class="img-thumbnail" src="http://e.hiphotos.baidu.com/image/h%3D300/sign=ab436e58aeec08fa390015a769ef3d4d/b17eca8065380cd7cd63680aaf44ad34588281dc.jpg" alt="">
                <div>缩略图</div>
            </div>
            <div class="col-sm-6">
                <img class="img-responsive" src="http://e.hiphotos.baidu.com/image/h%3D300/sign=ab436e58aeec08fa390015a769ef3d4d/b17eca8065380cd7cd63680aaf44ad34588281dc.jpg" alt="">
                <div>响应式图片</div>
            </div>
        </div>
    </div>
```

#### 图标

##### （.glyphicon）

```
    <!-- 图标 -->
    <span class="glyphicon glyphicon-search"></span>
    <span class="glyphicon glyphicon-asterisk"></span>
    <span class="glyphicon glyphicon-plus"></span>
    <span class="glyphicon glyphicon-cloud"></span>
    <span class="glyphicon glyphicon-heart"></span>
```

#### 网格系统

##### 实现原理

```
        <div class="container">
            <div class="row">
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
            </div>
            <div class="row">
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
            </div>
            <div class="row">
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
                <div class="col-md-1">.col-md-1</div>
            </div>
        </div>
```

##### 工作原理

###### 1、数据行(.row)必须包含在容器（.container）中，以便为其赋予合适的对齐方式和内距(padding)。

###### 2、在行(.row)中可以添加列(.column)，但列数之和不能超过平分的总列数。

```
<div class="container">
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-8">.col-md-8</div>
  </div>
  <div class="row">
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4">.col-md-4</div>
    <div class="col-md-4">.col-md-4</div>
  </div>
  <div class="row">
    <div class="col-md-3">.col-md-3</div>
    <div class="col-md-6">.col-md-6</div>
    <div class="col-md-3">.col-md-3</div>
  </div>
  <div class="row">
      <div class="col-md-3">.col-md-3</div>
      <div class="col-md-6">.col-md-6</div>
      <div class="col-md-5">.col-md-5</div>
  </div>
</div>
```

##### 基本用法

```
    <div class="container">
        <div class="row">
            <div class="col-md-4">.col-md-4</div>
            <div class="col-md-8">.col-md-8</div>
        </div>
        <div class="row">
            <div class="col-md-4">.col-md-4</div>
            <div class="col-md-4">.col-md-4</div>
            <div class="col-md-4">.col-md-4</div>
        </div>
        <div class="row">
            <div class="col-md-3">.col-md-3</div>
            <div class="col-md-6">.col-md-6</div>
            <div class="col-md-3">.col-md-3</div>
        </div>
    </div>
```

##### 列偏移

##### （.col-md-offset-1）偏移一个网格

```
    <div class="container">
        <div class="row">
            <div class="col-md-2">.col-md-2</div>
            <div class="col-md-2 col-md-offset-1">.col-md-2</div>
            <div class="col-md-2 col-md-offset-1">.col-md-2</div>
            <div class="col-md-3 col-md-offset-1">.col-md-3</div>
        </div>
    </div>
```

##### 列排序

##### （.col-md-push-8）：向右偏移8个网格

##### （.col-md-pull-4）：向左偏移4个网格

```
    <div class="container">
        <div class="row">
            <!-- 向右偏移4个网格 -->
            <div class="col-md-8 col-md-push-4">.col-md-8</div>
            <!-- 向左偏移8个网格 -->
            <div class="col-md-4 col-md-pull-8">.col-md-4</div>
        </div>
    </div>
```

##### 列的嵌套

```
    <div class="container">
        <div class="row">
            <div class="col-md-8">
                <div class="row">
                    <div class="col-md-8">.col-md-8</div>
                    <div class="col-md-4">.col-md-4</div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="row">
                    <div class="col-md-9">.col-md-9</div>
                    <div class="col-md-3">.col-md-3</div>
                </div>
            </div>
        </div>
    </div>
```

#### 下拉菜单

##### 基本用法

```
    <!-- 基本用法 -->
    <div class="dropdown">
        <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
            下拉菜单
            <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" role="menu" arial-labelledby="dropdownMenu1">
            <li role="presentation">
                <a href="#" role="menuitem" tabindex="-1">下拉菜单项</a>
            </li>
            <li role="presentation">
                <a href="#" role="menuitem" tabindex="-1">下拉菜单项</a>
            </li>
            <li role="presentation">
                <a href="#" role="menuitem" tabindex="-1">下拉菜单项</a>
            </li>
            <li role="presentation">
                <a href="#" role="menuitem" tabindex="-1">下拉菜单项</a>
            </li>
        </ul>
    </div>
```

##### 下拉菜单（下拉菜单分隔线）

```
    <!-- 下拉分隔线 -->
    <div class="dropdown">
        <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
            食物
            <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" role="menu" aria-labelledby="dropdownMenu1">
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">苹果</a></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">香蕉</a></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">梨</a></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">桃</a></li>
            <li role="presentation" class="divider"></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">芹菜</a></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">萝卜</a></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">茄子</a></li>
            <li role="presentation" class="divider"></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">米饭</a></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">馒头</a></li>
            <li role="presentation"><a href="#" tabindex="-1" role="menuitem">面条</a></li>
        </ul>
    </div>
```

##### 下拉菜单（菜单标题）

```
    <!-- 下拉菜单（菜单标题） -->
    <div class="dropdown">
        <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
            食物
            <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" role="menu" aria-labelledby=""> 
            <li role="prentation" class="dropdown-header">水果</li>
            <li role="prentstation"><a href="#" role="menuitem" tabindex="-1">苹果</a></li>
            <li role="prentstation"><a href="#" role="menuitem" tabindex="-1">香蕉</a></li>
            <li role="prentstation"><a href="#" role="menuitem" tabindex="-1">梨</a></li>
            <li role="prentstation"><a href="#" role="menuitem" tabindex="-1">桃</a></li>
            <li role="prentstation" class="divider"></li>
            <li role="prentation" class="dropdown-header">蔬菜</li>
            <li role="prentation"><a href="#" role="menuitem"tabindex="-1">芹菜</a></li>
            <li role="prentation"><a href="#" role="menuitem"tabindex="-1">萝卜</a></li>
            <li role="prentation"><a href="#" role="menuitem"tabindex="-1">茄子</a></li>
            <li role="presentation" class="divider"></li>
            <li role="presentation" class="dropdown-header">主食</li>
            <li role="prentation"><a href="#" role="menuitem" tabindex="-1">米饭</a></li>
            <li role="prentation"><a href="#" role="menuitem" tabindex="-1">馒头</a></li>
            <li role="prentation"><a href="#" role="menuitem" tabindex="-1">面条</a></li>
        </ul>
    </div>
```

##### 下拉菜单（对齐方式）

##### （.pull-right）||（.dropdown-menu-right）右对齐

##### （.dropdown-menu-left）左对齐

```
    <div class="dropdown" style="margin-left: 100px;">
        <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown">
            食物
            <span class="caret"></span>
        </button>
        <ul class="dropdown-menu dropdown-menu-right" role="menu" aria-labelledby="dropdownMenu1">
            <li role="presentation" class="dropdown-header">水果</li>
            <li role="presentation"><a href="#" role="menuitem" tabindex="-1">苹果</a></li>
            <li role="presentation"><a href="#" role="menuitem" tabindex="-1">香蕉</a></li>
            <li role="presentation"><a href="#" role="menuitem" tabindex="-1">梨</a></li>
            <li role="presentation" class="divider"></li>
            <li role="presentation" class="dropdown-header">蔬菜</li>
            <li role="presentation"><a href="#" role="menuitem" tabindex="-1">芹菜</a></li>
            <li role="presentation"><a href="#" role="menuitem" tabindex="-1">萝卜</a></li>
            <li role="presentation"><a href="#" role='menuitem' tabindex="-1">茄子</a></li>
        </ul>
    </div>
```

#### 按扭

##### 按扭组

```
        <div class="btn-group">
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-search"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-zoom-in"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-zoom-out"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-download"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-upload"></span></button>
        </div>
```

##### 按扭工具栏

```
    <div class="btn-toolbar">
        <div class="btn-group btn-group-lg">
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-align-left"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-align-center"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-align-right"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-align-justify"></span></button>
        </div>
        <div class="btn-group">
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-indent-left"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-indent-right"></span></button>
        </div>
        <div class="btn-group btn-group-sm">
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-font"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-bold"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-italic"></span></button>
        </div>
        <div class="btn-group btn-group-xs">
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-text-height"></span></button>
            <button class="btn btn-default" type="button"><span class="glyphicon glyphicon-text-width"></span></button>
        </div>
    </div>
```

##### 嵌套（水平分组）

```
    <div class="btn-group">
        <button class="btn btn-default" type="button">首页</button>
        <div class="btn-group">
            <div class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">
                产品展示
                <span class="caret"></span>
            </div>
            <ul class="dropdown-menu">
                    <li><a href="#">收割机</a></li>
                    <li><a href="#">电动机</a></li>
                    <li><a href="#">拖拉机</a></li>
                    <li><a href="#">电动车</a></li>
            </ul>
        </div>
        <button class="btn btn-default" type="button">案例分析</button>
        <button class="btn btn-default" type="button">联系我们</button>
        <button class="btn btn-default" type="button">关于我们</button>
    </div>
```

##### 嵌套垂直（垂直分组）

```
    <div class="btn-group-vertical">
        <button class="btn btn-default" type="button">首页</button>
        <div class="btn-group">
            <button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">
                关于我们
                <span class="caret"></span>
            </button>
            <ul class="dropdown-menu">
                <li><a href="#">收割机</a></li>
                <li><a href="#">电动机</a></li>
                <li><a href="#">拖拉机</a></li>
                <li><a href="#">电动车</a></li>
            </ul>
        </div>
        <button class="btn btn-default" type="button">案例分析</button>
        <button class="btn btn-default" type="button">联系我们</button>
        <button class="btn btn-default" type="button">关于我们</button>
    </div>
```

##### 等分按扭	

```
    <div class="wrap">
        <div class="btn-group btn-group-justified">
            <a href="#" class="btn btn-default">首页</a>
            <a href="#" class="btn btn-default">产品展示</a>
            <a href="#" class="btn btn-default">案例分析</a>
            <a href="#" class="btn btn-default">新闻中心</a>
            <a href="#" class="btn btn-default">商务中心</a>
            <a href="#" class="btn btn-default">服务平台</a>
        </div>
    </div>

```

##### 按扭下拉菜单 

```
    <div class="btn-group">
        <button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">
            按扭下拉菜单
            <span class="caret"></span>
        </button>
        <ul class="dropdown-menu">
            <li><a href="#">按扭下拉菜单项</a></li>
            <li><a href="#">按扭下拉菜单项</a></li>
            <li><a href="#">按扭下拉菜单项</a></li>
            <li><a href="#">按扭下拉菜单项</a></li>
        </ul>
    </div>
```

##### 按扭的向下向上三角形

##### （.dropup）：向上

```
    <div class="btn-group dropup">
        <button class="btn btn-default dropdown-toggle" data-toggle="dropdown" type="button">
            按扭下拉菜单
            <span class="caret"></span>
        </button>
        <ul class="dropdown-menu">
            <li><a href="#">按扭下拉菜单项</a></li>
            <li><a href="#">按扭下拉菜单项</a></li>
            <li><a href="#">按扭下拉菜单项</a></li>
            <li><a href="#">按扭下拉菜单项  </a></li>
        </ul>
    </div>
```

#### 导航

##### 基础样式

```
    <ul class="nav nav-tabs">
        <li><a href="#">Home</a></li>
        <li><a href="#">CSS3</a></li>
        <li><a href="#">Less</a></li>
        <li><a href="#">jQuery</a></li>
        <li><a href="#">Responsive</a></li>
    </ul>
```

##### 标签形tabs导航

```
    <ul class="nav nav-tabs">
        <li class="active"><a href="#">商品介绍</a></li>
        <li><a href="#">规格参数</a></li>
        <li><a href="#">商品评价</a></li>
        <li><a href="#">售后保证</a></li>
        <li  class="disabled"><a href="#">Responsive</a></li>
    </ul>
```

##### 圆角形Pills导航栏

```
    <ul class="nav nav-pills">
        <li class="active"><a href="#">商品介绍</a></li>
        <li><a href="#">规格参数</a></li>
        <li><a href="#">商品评价</a></li>
        <li><a href="#">售后保证</a></li>
        <li class="disabled"><a href="#">Responsive</a></li>
    </ul>
```

##### 垂直堆叠的导航栏

##### （.nav-stacked）

```
    <ul class="nav nav-pills nav-stacked">
        <li class="active"><a href="#">商品介绍</a></li>
        <li><a href="#">规格参数</a></li>
        <li><a href="#">商品评价</a></li>
        <li><a href="#">售后保证</a></li>
    </ul>
```

##### 自适应导航栏

##### （.nav-justified）：自适应导航栏

```
    <ul class="nav nav-tabs nav-pills nav-justified">
        <li class="active"><a href="#">Home</a></li>
        <li><a href="#">CSS3</a></li>
        <li><a href="#">Sass</a></li>
        <li><a href="#">jQuery</a></li>
        <li><a href="#">Responsive</a></li>
    </ul>
```

##### 导航加下拉菜单（二级导航）

```
    <ul class="nav nav-pills">
        <li class="active"><a href="#">首页</a></li>
        <li class="dropdown">
            <a href="#" class="dropdown-toggle" data-toggle="dropdown">
                教程
                <span class="caret"></span>
            </a>
            <ul class="dropdown-menu">
                <li><a href="#">CSS3</a></li>
                <li><a href="#">Sass</a></li>
                <li class="divider"></li>
                <li><a href="#">jQuery</a></li>
                <li><a href="#">Responsive</a></li>
            </ul>
        </li>
        <li><a href="#">关于我们</a></li>
    </ul>
```

##### 面包屑式导航

##### （.breadcrumb）

```
    <ol class="breadcrumb">
        <li><a href="#">首页</a></li>
        <li><a href="#">名师简介</a></li>
        <li class="active">大漠</li>
    </ol>
```

#### 导航条

##### 导航条基础（.navbar）

```

    <div class="navbar navbar-default" role="navigation">
        <ul class="nav navbar-nav">
            <li class="active"><a href="#">网站首页</a></li>
            <li><a href="#">系列教程</a></li>
            <li><a href="#">名师介绍</a></li>
            <li><a href="#">成功案例</a></li>
            <li><a href="#">关于我们</a></li>
        </ul>
    </div>
    <div class="navbar navbar-default" role="navigation">
        <div class="navbar-header">
            <a href="#" class="navbar-brand">慕课网</a>
        </div>
        <ul class="nav navbar-nav">
            <li class="active"><a href="#">网站首页</a></li>
            <li class="dropdown">
                <a href="#" data-toggle="dropdown" class="dropdown-toggle">
                    系列教程
                    <span class="caret"></span>
                </a>
                <ul class="dropdown-menu">
                    <li><a href="#">CSS3</a></li>
                    <li><a href="#">JavaScript</a></li>
                    <li class="disabled"><a href="#">PHP</a></li>
                </ul>
            </li>
            <li><a href="#">名师介绍</a></li>
            <li><a href="#">成功案例</a></li>
            <li><a href="#">关于我们</a></li>
        </ul>
    </div>
    <form action="#" class="navbar-form navbar-left" rol="search">
        <div class="form-group">
            <input type="text" class="form-control" placeholder="请输入关键词">
        </div>
        <button type="submit" class="btn btn-default">搜索</button>
    </form>
```

##### 基础导航条

```
    <div class="navbar navbar-default" role="navigation">
        <ul class="nav navbar-nav">
            <li class="active"><a href="#">网站首页</a></li>
            <li><a href="#">系列教程</a></li>
            <li><a href="#">名师介绍</a></li>
            <li><a href="#">成功案例</a></li>
            <li><a href="#">关于我们</a></li>
        </ul>
    </div>
```

##### 导航条添加标题、二级菜单及状态

```
    <!-- 导航条 -->
    <div class="navbar navbar-default" role="navigation">
        <!-- 标题 -->
        <div class="navbar-header">
            <a href="##" class="navbar-brand">慕课网</a>
        </div>
        <!-- 内容 -->
        <ul class="nav navbar-nav">
            <li class="active"><a href="#">网站首页</a></li>
            <!-- 二级导航栏 -->
            <li class="dropdown">
                <!-- 标题 -->
                <a href="##" data-toggle="dropdown" class="dropdown-toggle">
                    系列教程
                    <span class="caret"></span>
                </a>
                <!-- 内容 -->
                <ul class="dropdown-menu">
                    <li><a href="#">CSS3</a></li>
                    <li><a href="#">JavaScript</a></li>
                    <li class="disabled"><a href="#">PHP</a></li>
                </ul>
            </li>
            <li><a href="#">名师介绍</a></li>
            <li><a href="#">成功案例</a></li>
            <li><a href="#">关于我们</a></li>
        </ul>
    </div>

```

##### 带表单的导航条

```
    <!-- 导航条 -->
    <div class="navbar navbar-default" role="navigation">
        <!-- 头部导航条 -->
        <div class="navbar-header">
            <a href="##" class="navbar-brand">慕课网</a>&#12288;&#12288;
        </div>
        <ul class="nav navbar-nav">
            <li><a href="#">网站首页</a></li>
            <li class="active"><a href="#">名师介绍</a></li>
            <li><a href="#">成功案例</a></li>
            <li class="dropdown">
                <a href="#" data-toggle="dropdown" class="dropdown-toggle">
                    关于我们
                    <span class="caret"></span>
                </a>
                <ul class="dropdown-menu">
                    <li><a href="#">CSS3</a></li>
                    <li><a href="#">JavaScript</a></li>
                    <li class="disabled"><a href="#">PHP</a></li>
                </ul>
            </li>
        </ul>
        <!-- 右侧搜索表单 -->
        <form action="##" class="navbar-form navbar-right" rol="search">
            <div class="form-group">
                <input type="text" class="form-control" placeholder="请输入关键词">
            </div>
            <button class="btn btn-default" type="submit">搜索</button>
        </form>
    </div>
```

##### 导航条中的按钮、文本和链接

```
    <div class="navbar navbar-default" role="navigation">
        <div class="navbar-header">
            <a href="" class="navbar-brand">慕课网</a>
        </div>
        <Ul class="nav navbar-nav">
            <li><a href="" class="navbar-text">Navbar Text</a></li>
            <li><a href="" class="navbar-text">Navbar Text</a></li>
            <li><a href="" class="navbar-text">Navbar Text</a></li>
        </Ul>
    </div>
    <div class="navbar navbar-default" role="navigation">
        <div class="navbar-header">
            <a href="" class="navbar-brand">慕课网</a>
        </div>
        <div class="nav navbar-nav">
            <a href="" class="navbar-text">Navbar Text</a>
            <a href="" class="navbar-text">Navbar Text</a>
            <a href="" class="navbar-text">Navbar Text</a>
        </div>

    </div>
```

##### 固定导航条

```
    <div class="navbar navbar-default navbar-fixed-top" role="navigation">
        <div class="navbar-header">
            <a href="##" class="navbar-brand">慕课网</a>
        </div>
        <ul class="nav navbar-nav">
            <li class="active"><a href="#">网站首页</a></li>
            <li><a href="#">名师介绍</a></li>
            <li><a href="#">成功案例</a></li>
            <li><a href="#">关于我们</a></li>
        </ul>
    </div>
    <div class="content">我是内容</div>
    <div class="navbar navbar-default navbar-fixed-bottom" role="navigation">
        <div class="navbar-header">
            <a href="#" class="navbar-brand">慕课网</a>
        </div>
        <ul class="nav navbar-nav">
            <li class="active"><a href="##">网站首页</a></li>
            <li><a href="#">系列教程</a></li>
            <li><a href="#">名师介绍</a></li>
            <li><a href="#">成功案例</a></li>
            <li><a href="#">关于我们</a></li>
        </ul>
    </div>
    <p>网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容。</p>
<p>网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容。</p>
<p>网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容。</p>
<p>网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容。</p>
<p>网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容。</p>
<p>网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容。</p>
<p>网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容，网页正文内容。</p>
```

##### 响应式导航条

```
    <div class="navbar navbar-default" role="navigation">
        <div class="navbar-header">
            <!-- 收缩的内容 -->
            <button class="navbar-toggle" type="button" data-toggle="collapse" data-target=".navbar-responsive-collapse">
                <span class="sr-only">Toggle Navigation</span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
            </button>
            <!-- 确保无论是宽屏还是窄屏，navbar-brand都显示 -->
            <a href="#" class="navbar-brand">慕课网</a>
        </div>
        <!-- 宽屏的内容 -->
        <div class="collapse navbar-collapse navbar-responsive-collapse">
            <ul class="nav navbar-nav">
                <li class="active"><a href="#">网站首页</a></li>
                <li><a href="#">系列教程</a></li>
                <li><a href="#">名师介绍</a></li>
                <li><a href="#">成功案例</a></li>
                <li><a href="#">关于我们</a></li>
            </ul>
        </div>
    </div>
```

##### 反色导航条

```
    <div class="navbar navbar-inverse" role="navigation">
        <div class="navbar-header">
            <a href="###" class="navbar-brand">慕课网</a>
        </div>
        <ul class="nav navbar-nav">
            <li class="active"><a href="#">首页</a></li>
            <li><a href="##">教程</a></li>
            <li><a href="##">关于我们</a></li>
        </ul>
    </div>
```

##### 分页导航（带页码的分页导航）

```
    <ul class="pagination pagination-lg">
        <li><a href="#">&laquo;第一页</a></li>
        <li><a href="#">11</a></li>
        <li><a href="#">12</a></li>
        <li class="active"><a href="#">13</a></li>
        <li><a href="#">15</a></li>
        <li><a href="#">16</a></li>
    </ul>
    <ul class="pagination pagination">
        <li><a href="##">&laquo;第一页</a></li>
        <li><a href="#">11</a></li>
        <li><a href="#">12</a></li>
        <li class="active"><a href="#">13</a></li>
        <li><a href="#">15</a></li>
        <li><a href="#">16</a></li>
    </ul>
    <ul class="pagination pagination-sm">
        <li><a href="##">&laquo;第一页</a></li>
        <li><a href="#">11</a></li>
        <li><a href="#">12</a></li>
        <li class="active"><a href="#">13</a></li>
        <li><a href="#">15</a></li>
        <li><a href="#">16</a></li>
    </ul>
```

##### 分页导航（翻页分页导航）

```
    <!-- 分页导航 -->
    <ul class="pager">
        <li><a href="#">&laquo;上一页</a></li>
        <li><a href="#">下一页&laquo;</a></li>
    </ul>
    <!-- 左右对齐 -->
    <ul class="pager">
        <li class="previous"><a href="#">&laquo;上一页</a></li>
        <li class="next"><a href="#">下一页&laquo;</a></li>
    </ul>
    <!-- 禁止状态 -->
    <ul class="pager">
        <li class="disabled"><span>&laquo;上一页</span></li>
        <li><a href="#">下一页&raquo;</a></li>
    </ul>
```

##### 标签 

```
    <!-- 默认标签 -->
    <h3>Example heading <span class="label label-default">New</span></h3>
    <!-- 主要标签 -->
    <span class="label label-primary">主要标签</span>
    <!-- 成功标签 -->
    <span class="label label-success">成功标签</span>
    <!-- 信息标签 -->
    <span class="label label-info">信息标签</span>
    <!-- 警告标签 -->
    <span class="label label-warning">警告标签</span>
    <!-- 错误标签 -->
    <span class="label label-danger">错误标签</span>
```

##### 徽章

```
    <a href="#">Index <span class="badge">42</span></a>
    <div class="navbar navbar-default" role="navigation">
        <div class="navbar-header">
            <a href="##" class="navbar-brand">慕课网</a>
        </div>
        <ul class="nav navbar-nav">
            <li class="active"><a href="##">网站首页</a></li>
            <li><a href="##">系列教程</a></li>
            <li><a href="##">名师介绍</a></li>
            <li><a href="##">成功案例<span class="badge">23</span></a></li>
            <li>关于我们</li>
        </ul>
    </div>
    <ul class="nav nav-pills">
        <li class="active"><a href="#">Home <span class="badge">42</span></a></li>
        <li><a href="#">Profile</a></li>
        <li><a href="#">Messages <span class="badge">3</span></a></li>
    </ul>
    <br>
    <ul class="nav nav-pills nav-stacked" style="max-width: 260px;">
        <li class="active">
            <a href="##">
                <span class="badge pull-right">42</span>
                Home
            </a>
        </li>
        <li><a href="#">Profile</a></li>
        <li>
            <a href="#">
                <span class="badge pull-right">3</span>
                Messages
            </a>
        </li>
    </ul>
    <!-- 按扭徽章 -->
    <button class="btn btn-primary" type="button">
        Messages <span class="badge">4</span>
    </button>
```

#### 其他内置组件

##### 缩略图

```
    <div class="container">
        <div class="row">
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
            </div>
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
            </div>
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
            </div>
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
            </div>
        </div>
    </div>
    
    //复杂
       <div class="container">
        <div class="row">
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
                <div class="caption">
                    <h3>Bootstrap框架系列教程</h3>
                    <p>Bootstrap框架是一个优秀的前端框，就算您是一位后端程序员或者你是一位不懂设计的前端人员，你也能依赖于Bootstrap制作做优美的网站...</p>
                    <a href="##" class="btn btn-primary">开始学习</a>
                    <a href="##" class="btn btn-primary">正在学习</a>
                </div>
            </div>
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
                <div class="caption">
                    <h3>Bootstrap框架系列教程</h3>
                    <p>Bootstrap框架是一个优秀的前端框，就算您是一位后端程序员或者你是一位不懂设计的前端人员，你也能依赖于Bootstrap制作做优美的网站...</p>
                    <a href="##" class="btn btn-primary">开始学习</a>
                    <a href="##" class="btn btn-primary">正在学习</a>
                </div>
            </div>
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
                <div class="caption">
                    <h3>Bootstrap框架系列教程</h3>
                    <p>Bootstrap框架是一个优秀的前端框，就算您是一位后端程序员或者你是一位不懂设计的前端人员，你也能依赖于Bootstrap制作做优美的网站...</p>
                    <a href="##" class="btn btn-primary">开始学习</a>
                    <a href="##" class="btn btn-primary">正在学习</a>
                </div>
            </div>
            <div class="col-xs-6 col-md-3">
                <a href="#" class="thumbnail">
                    <img src="http://img.mukewang.com/5418eac00001bf4a06550366.jpg" alt="" style="height: 180px; width: 100%; display: block;">
                </a>
                <div class="caption">
                    <h3>Bootstrap框架系列教程</h3>
                    <p>Bootstrap框架是一个优秀的前端框，就算您是一位后端程序员或者你是一位不懂设计的前端人员，你也能依赖于Bootstrap制作做优美的网站...</p>
                    <a href="##" class="btn btn-primary">开始学习</a>
                    <a href="##" class="btn btn-primary">正在学习</a>
                </div>
            </div>
        </div>
    </div>
```

#### 警示框

```
    <h2>默认警示框</h2>
    <div class="alert alert-success" role="alert">恭喜您操作成功</div>
    <div class="alert alert-info" role="alert">请输入正确的密码</div>
    <div class="alert alert-warning" role="alert">您已操作失败两次，还有一次机会</div>
    <div class="alert alert-danger" role="alert">对不起，您输入的密码有误</div>
    <h2>可关闭的警示框</h2>
    <div class="alert alert-success" role="alert"><button class="close" type="button" data-dismiss="alert">&times;</button>成功</div>
    <div class="alert alert-info" role="alert"><button class="close" type="button" data-dismiss="alert">&times;</button>请输入正确的密码</div>
    <div class="alert alert-warning" role="alert"><button class="close" type="button" data-dismiss="alert">&times;</button>您已操作失败两次，还有一次机会</div>
    <div class="alert alert-danger" role="alert"><button class="close" type="button" data-dismiss="alert">&times;</button>对不起，您输入的密码有误</div>
    <h2>警示框的链接</h2>
    <div class="alert alert-success" role="alert">
        <strong>WellDon</strong>
        This
        <a href="##" class="alert-link">this important alert message</a>
    </div>
    <div class="alert alert-info" role="alert">
        <strong>WellDon</strong>
        This
        <a href="##" class="alert-link">this important alert message</a>
    </div>
    <div class="alert alert-warning" role="alert">
        <strong>WellDon</strong>
        This
        <a href="##" class="alert-link">this important alert message</a>
    </div>
    <div class="alert alert-danger" role="alert">
        <strong>WellDon</strong>
        This
        <a href="##" class="alert-link">this important alert message</a>
    </div>
```

#### 进度条

```
  <h4>基本进度条</h4>
    <div class="progress">
        <div class="progress-bar" style="width: 40%"></div>
    </div>
    <h4>彩色进度条</h4>
    <div class="progress">
        <div class="progress-bar progress-bar-success" style="width: 40%"></div>
    </div>
    <div class="progress">
        <div class="progress-bar progress-bar-info" style="width: 40%;"></div>
    </div>
    <div class="progress">
        <div class="progress-bar progress-bar-warning" style="width: 40%"></div>
    </div>
    <div class="progress">
        <div class="progress-bar progress-bar-danger" style="width: 40%"></div>
    </div>
    <h4>条纹进度条</h4>
    <div class="progress progress-striped">
        <div class="progress-bar progress-bar-success" style="width: 40%"></div>
    </div>
    <div class="progress progress-striped">
        <div class="progress-bar progress-bar-info" style="width: 40%"></div>
    </div>
    <div class="progress progress-striped">
        <div class="progress-bar progress-bar-warning" style="width: 40%"></div>
    </div>
    <div class="progress progress-striped">
        <div class="progress-bar progress-bar-danger" style="width: 40%;"></div>
    </div>
    <h4>动态条纹进度条</h4>
    <div class="progress progress-striped active">
        <div class="progress-bar progress-bar-success" style="width: 40%;"></div>
    </div>
    <div class="progress progress-striped active">
        <div class="progress-bar progress-bar-info" style="width: 40%;"></div>
    </div>
    <div class="progress progress-striped active">
        <div class="progress-bar progress-bar-warning" style="width: 40%;"></div>
    </div>
    <div class="progress progress-striped active">
        <div class="progress-bar progress-bar-danger" style="width: 40%;"></div>
    </div>
    <h4>层叠进度条</h4>
    <div class="progress">
        <div class="progress-bar progress-bar-success" style="width: 20%"></div>
        <div class="progress-bar progress-bar-info" style="width: 20%;"></div>
        <div class="progress-bar progress-bar-warning" style="width: 20%;"></div>
        <div class="progress-bar progress-bar-danger" style="width: 20%;"></div>
    </div>
    <h4>不良效果层叠进度条</h4>
    <div class="progress">
        <div class="progress-bar progress-bar-success" style="width: 20%;"></div>
        <div class="progress-bar progress-bar-info" style="width: 40%;"></div>
        <div class="progress-bar progress-bar-warning" style="width: 30%;"></div>
        <div class="progress-bar progress-bar-danger" style="width: 40%;"></div>
    </div>
    <h4>层叠条纹进度条</h4>
    <div class="progress">
        <div class="progress-bar progress-bar-success progress-bar-striped" style="width:20%"></div>    
        <div class="progress-bar progress-bar-info progress-bar-striped" style="width:20%"></div>    
        <div class="progress-bar progress-bar-warning progress-bar-striped" style="width:20%"></div>    
        <div class="progress-bar progress-bar-danger progress-bar-striped" style="width:20%"></div>    
    </div>
    <h4>带label的进度条</h4>
    <div class="progress">
        <div class="progress-bar progress-bar-success" role="progressbar" style="width: 20%;" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100">20%</div>
    </div>
    <div class="progress">
            <div class="progress-bar progress-bar-info" role="progressbar" style="width: 70%;" aria-valuenow="70" aria-valuemin="0" aria-valuemax="100">70%;</div>
    </div>
    <div class="progress">
        <div class="progress-bar progress-bar-warning" role="progressbar" style="width: 50%;" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">50%</div>
    </div>
    <div class="progress">
        <div class="progress-bar progress-bar-danger" role="progressbar" style="width: 30%;" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100">30%</div>
    </div>
    <h4>带Label的进度条2</h4>
    <div class="progress">
        <div class="progress-bar progress-bar-success" role="progressbar" style="width: 0%;" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100">0%</div>
    </div>
```

#### 媒体对象

```
 <!-- 媒体对象 -->
            <div class="media">
                <a href="#" class="pull-left">
                    <img class="media-object" src="http://img.mukewang.com/52e1d29d000161fe06000338-300-170.jpg" alt="" >
                </a>
                <div class="media-body">
                    <h4 class="media-heading">系列：十天精通CSS3</h4>
                    <div>全方位深刻详解CSS3模块知识，经典案例分析，代码同步调试，让网页穿上绚丽装备！</div>
                </div>
            </div>
            <!-- 对象媒体的嵌套 -->
            <div class="media">
                <a href="###" class="pull-left">
                    <img src="http://img.mukewang.com/52e1d29d000161fe06000338-300-170.jpg" alt="" class="media-object">
                </a>
                <div class="meida-body">
                    <h4>系列：十天精通CSS3</h4>
                    <div>我是W3cplus站长大漠，我在写Bootstrap框中的媒体对象测试用例</div>
                    <div class="media">
                        <a href="#" class="pull-left">
                            <img src="http://tp2.sinaimg.cn/3306361973/50/22875318196/0" alt="" class="media-object">
                        </a>
                        <div class="media-body">
                            <h4>慕课网</h4>
                            <div>大漠写的《玩转Bootstrap》系列教程即将会在慕课网上发布</div>
                            <div class="media">
                                <a href="##" class="pull-left">
                                    <img src="http://tp4.sinaimg.cn/1167075935/50/22838101204/1" alt="" class="media-object">
                                </a>
                                <div class="media-body">
                                    <h4>W3cplus</h4>
                                    <div>W3cplus站上还有很多教程....</div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!-- 媒体对象的列表 -->
            <ul class="media-list">
                <li class="media">
                    <a href="###" class="pull-left">
                        <img src="http://tp2.sinaimg.cn/3306361973/50/22875318196/0" alt="" class="media-object">
                    </a>
                    <div class="media-body">
                        <h4>我是大漠</h4>
                        <div>我是W3cplus站长大漠，我在写Bootstrap框中的媒体对象测试用例我是W3cplus站长大漠，我在写Bootstrap框中的媒体对象测试用例</div>
                    </div>
                </li>
                <li class="media">
                    <a href="###" class="pull-left">
                        <img class="media-object" src="http://tp4.sinaimg.cn/1167075935/50/22838101204/1" alt="">
                    </a>
                    <div class="media-body">
                        <h4>我是大漠</h4>
                        <div>我是W3cplus站长大漠，我在写Bootstrap框中的媒体对象测试用例我是W3cplus站长大漠，我在写Bootstrap框中的媒体对象测试用例</div>
                    </div>
                </li>
                <li class="media">
                    <a href="###" class="pull-left">
                        <img class="media-object" src="http://tp4.sinaimg.cn/1167075935/50/22838101204/1" alt="">
                    </a>
                    <div class="media-body">
                        <h4>我是大漠</h4>
                        <div>我是W3cplus站长大漠，我在写Bootstrap框中的媒体对象测试用例我是W3cplus站长大漠，我在写Bootstrap框中的媒体对象测试用例</div>
                    </div>
                </li>
            </ul>

```

#### 列表组

```
    <!-- 基础列表组 -->
    <ul class="list-group">
        <li class="list-group-item">揭开CSS3的面纱</li>
        <li class="list-group-item">CSS3选择器</li>
        <li class="list-group-item">CSS3边框</li>
        <li class="list-group-item">CSS3背景</li>
        <li class="list-group-item">CSS3文本</li>
    </ul>
    <!-- 带徽章的列表组 -->
    <ul class="list-group">
        <li class="list-group-item"><span class="badge">13</span>揭开CSS3的面纱</li>
        <li class="list-group-item"><span class="badge">654</span>CSS3边框</li>
        <li class="list-group-item"><span class="badge">5161</span>CSS3背景</li>
        <li class="list-group-item"><span class="badge">5161</span>CSS3文本</li>
    </ul>
    <!-- 带链接的列表组 -->
    <ul class="list-group">
        <li class="list-group-item"><a href="##">揭开CSS3的面纱</a></li>
        <li class="list-group-item"><a href="##">CSS3选择器</a></li>
        <li class="list-group-item"><a href="##">CSS3边框</a></li>
        <li class="list-group-item"><a href="##">CSS3背景</a></li>
        <li class="list-group-item"><a href="##">CSS3文本</a></li>
    </ul>
    <!-- 自定义列表组 -->
    <div class="list-group">
        <a href="##" class="list-group-item">
            <h4 class="list-group-item-heading">图解CSS3</h4>
            <p class="list-group-item-text">详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性...</p>
        </a>
        <a href="###" class="list-group-item">
            <h4 class="list-group-item-heading">Sass中国</h4>
            <p class="list-group-item-text">致力于为中国开发者提供最全面，最具影响力，最前沿的Sass相关技术与教程...</p>
        </a>
    </div>
    <!-- 组合列表项的状态  -->
    <div class="list-group">
        <a href="##" class="list-group-item active"><span class="badge">5902</span>图解CSS3</a>
        <a href="##" class="list-group-item"><span class="badge">15902</span>W3cplus</a>
        <a href="##" class="list-group-item disabled"> <span class="badge">854651</span>Sass中国</a>
    </div>
    <!-- 多彩列表组 -->
    <div class="list-group">
        <a href="##" class="list-group-item active"><span class="badge">5902</span>图解CSS3</a>
        <a href="##" class="list-group-item list-group-item-success"><span class="badge">515</span>W3cplus</a>
        <a href="##" class="list-group-item list-group-item-info"><span class="badge">10</span>慕课网</a>
        <a href="##" class="list-group-item list-group-item-warning"><span class="badge">0</span>Sass中国</a>
        <a href="##" class="list-group-item list-group-item-danger"><span class="badge">902</span>Mobile教程</a>
    </div>
```

#### 面板

```
    <!-- 基础面板 -->
    <div class="panel panel-default">
        <div class="panel-body">我是一个基础面板，带有默认主题样式风格</div>
    </div>
    <!-- 有头尾的面板 -->
    <div class="panel panel-default">
        <div class="panel-heading">图解CSS3</div>
        <div class="panel-body">详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</div>
        <div class="panel-footer">作者：大漠</div>
    </div>
    <!-- 彩色面板 -->
    <div class="panel panel-primary">
        <div class="panel-heading">图解CSS3</div>
        <div class="panel-body">详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</div>
        <div class="panel-footer">作者：大漠</div>
    </div>
    <div class="panel panel-success">
        <div class="panel-heading">图解CSS3</div>
        <div class="panel-body">详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</div>
        <div class="panel-footer">作者：大漠</div>
    </div>
    <div class="panel panel-info">
        <div class="panel-heading">图解CSS3</div>
        <div class="panel-body">详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</div>
        <div class="panel-footer">作者：大漠</div>
    </div>
    <div class="panel panel-warning">
        <div class="panel-heading">图解CSS3</div>
        <div class="parel-body">详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</div>
        <div class="panel-footer">作者：大漠</div>
    </div>
    <div class="panel panel-danger">
        <div class="panel-heading">图解CSS3</div>
        <div class="parel-body">详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</div>
        <div class="panel-footer">作者：大漠</div>
    </div>
    <!-- 面板中嵌套表格一 -->
    <div class="panel panel-default">
        <div class="panel-heading">图解CSS3</div>
        <div class="panel-body">
            <p>详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</p>
            <table class="table table-bordered">
                <thead>
                    <tr>
                        <th>#</th>
                        <th>我的书</th>
                        <th>发布时间</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>1</td>
                        <td>《图解CSS3》</td>
                        <td>2014-07-10</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div class="panel-footer">作者大漠</div>
    </div>
    <!-- 面板中嵌套表格二 -->
    <div class="panel panel-default">
        <div class="panel-heading">图解CSS3</div>
        <div class="panel-body">
            <p>详细讲解了选择器、边框、背景、文本、颜色、盒模型、伸缩布局盒模型、多列布局、渐变、过渡、动画、媒体、响应Web设计、Web字体等主题下涵盖的所有CSS3新特性</p>
        </div>
            <table class="table table-bordered">
                <thead>
                    <tr>
                        <th>#</th>
                        <th>我的书</th>
                        <th>发布时间</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>1</td>
                        <td>《图解CSS3》</td>
                        <td>2014-07-10</td>
                    </tr>
                </tbody>
            </table>
        <div class="panel-footer">作者：大漠</div>
    </div>
```

#### JavaScript插件

```
单独导入
动画过渡：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-transition.js"></script>
模态弹窗：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-modal.js"></script>
下拉菜单：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-dropdown.js"></script>
滚动侦测：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-scrollspy.js"></script>
选项卡：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-tab.js"></script>
提示框：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-tooltop.js"></script>
弹出框：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-popover.js"></script>
警告框：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-alert.js"></script>
按扭：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-button.js"></script>
折叠/手风琴：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-collapse.js"></script>
图片轮播Carousel：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-carousel.js"></script>
自动定位浮标Affix：<script src="http://cdn.bootcss.com/bootstrap/2.3.1/js/bootstrap-affix.js"></script>

一次性导入
<script src="http://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/js/bootstrap.min.js"></script> 
```

```
 <button class="btn btn-primary" type="button">点击</button>

    自动弹窗
    <div class="modal show">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal">
                        <span aria-hidden="true">&times;</span>
                        <span class="sr-only">Close</span>
                    </button>
                    <h4 class="modal-title">模态弹出窗标题</h4>
                </div>
                <div class="modal-body">
                    <p>模态弹出窗标题</p>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                    <button type="button" class="btn btn-primary">保存</button>
                </div>
            </div>
        </div>
    </div> 
     通过data-target触发 
     <button class="btn btn-primary" data-toggle="modal" data-target="#mymodal-data" type="button">通过data-target触发</button>
    <div class="modal" id="mymodal-data" tabindex="-1"  role="dialog" aria-labelledby="mySmallModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal">
                        <span aria-hidden="true">&times;</span>
                        <span class="sr-only">Close</span>
                    </button>
                    <h4 class="modal-title">模态弹出窗标题</h4>
                </div>
                <div class="modal-body">
                    <p>模态弹出窗主体内容</p>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                    <button type="button" class="btn btn-primary">保存</button>
                </div>
            </div>
        </div>
    </div> 
     <button class="btn btn-primary" type="button" data-toggle="modal" data-target=".bs-example-modal-lg">大的模态弹出框</button>
    <div class="modal fade bs-example-modal-lg" tabindex="-1" role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal">
                        <span aria-hidden="true">&times;</span>
                        <span class="sr-only">Close</span>
                    </button>
                    <h4 class="modal-title">模态弹出窗标题</h4>
                </div>
                <div class="modal-body">
                    <p>模态弹出窗主体内容</p>
                </div>
                <div class="modal-footer">
                    <button class="btn btn-default" type="button" data-dismiss="modal">关闭</button>
                    <button type="button" class="btn btn-primary">保存</button>
                </div>
            </div>
        </div>
    </div>
    <button class="btn btn-primary" type="button" data-toggle="modal" data-target=".bs-example-modal-sm">小的模态弹出框</button>
    <div class="modal fade bs-example-modal-sm" tabindex="-1" role="dialog" aria-labelledby="mySmallModalLabel" arial-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal">
                        <span aria-hidden="true">&times;</span>
                        <span class="sr-only">Close</span>
                    </button>
                    <h4>模态弹出窗标题</h4>
                </div>
                <div class="modal-body">
                    <p>模态弹出窗主体内容</p>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                    <button type="button" class="btn btn-primary">保存</button>
                </div>
            </div>
        </div>
    </div> 
     通过href属性触发 
    <a data-toggle="modal" data-target="#mymodal-link" class="btn btn-primary">通过链接href属性触发</a>
    <div class="modal" tabindex="-1" role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true" id="mymodal-link">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal">
                        <span aria-hidden="true">&times;</span>
                        <span class="sr-only">Close</span>
                    </button>
                    <h4>模态弹出窗标题</h4>
                </div>
                <div class="modal-body">
                    <p>模态弹出窗主体内容</p>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                    <button type="button" class="btn btn-primary">保存</button>
                </div>
            </div>
        </div>
    </div>
     通过data-target触发 
    <button type="button" data-backdrop="static" data-keyboard="false" class="btn btn-primary" data-toggle="modal" data-target="#mymodal-data">通过data-target触发</button>
    <div class="modal fade" id="mymodal-data" tabindex="-1" role="dialog" aria-labelledby="mySmallModallabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal">
                        <span aria-hidden="true">&times;</span>
                        <span class="sr-only">Close</span>
                    </button>
                    <h4 class="modal-title">模态弹出窗标题</h4>
                </div>  
                <div class="modal-body">
                    <p>模态弹出窗主体内容</p>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-default" data-dismiss="modal">关闭</button>
                    <button type="button" class="btn btn-primary">保存</button>
                </div>
            </div>
        </div>
    </div>
```

