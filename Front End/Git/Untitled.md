# GIT命令

#### 添加、修改、删除以及查看本地git的用户名和邮箱

##### 添加

```
$ git config --global user.name "yourName"
$ git config --global user.email "your@email.com"
```

##### 修改

```
//覆盖
$ git config --global user.name "yourName"
$ git config --global user.email "your@email.com"
//替换
$  git config --global --replace-all user.name "yourName" 
$  git config --global --replace-all user.email "your@email.com"
```

##### 删除

```
$ git config --global --unset user.name "yourName"
$ git config --global --unset user.email "your@email.com"
```

##### 查看

```
//查看所有
$ git config --list
//查看指定
$ git config user.name
$ git config user.email
```

##### 克隆

```
git clone '项目地址'
```

