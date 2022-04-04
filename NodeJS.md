# 说明：

老师讲的都很基础，基本上都是教你怎么用，讲原理的部分很少。

老师在后面给了一个 “大事件”项目的开发文档：

day6后半部分，day7，day8都是在开发这个项目的配套api。这里不再记录相关笔记

可以直接去这个网址看一下开发历程，极为详细

[Headline - api_server_ev (escook.cn)](http://escook.cn:8088/#/)



然后就是多ctrl+f在本文中搜索传送门，多看看

# 官网：[Node.js (nodejs.org)](https://nodejs.org/zh-cn/)

没有中文……

# 中文社区：

[CNode：Node.js专业中文社区 (cnodejs.org)](https://cnodejs.org/)

# 配套资料：

[2022最新版黑马程序员前端学习路线图_免费高速下载|百度网盘-分享无限制 (baidu.com)](https://pan.baidu.com/s/15yVOafBdEz3VU6hvYCOsYA#list/path=%2F)

![image-20220321120528124](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321120528124.png)

解压密码：1234

day5很大，因为老师在里面装了几个mysql的安装包……

# 视频：

[黑马程序员Node.js全套入门教程，nodejs最新教程含es6模块化+npm+express+webpack+promise等_Nodejs实战案例详解_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1a34y167AZ?spm_id_from=333.337.search-card.all.click)

# 本机版本：

nodejs

![image-20220320160758467](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320160758467.png)

npm

![image-20220321120134623](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321120134623.png)

express

```js
{
  "dependencies": {
    "express": "^4.17.1"
  }
}
```

# npm包：

## 时间相关：

moment,dayjs

## 查看切换镜像源（全局）：

nrm，安装使用失败……

解决办法

[解决：npm中 下载速度慢 和（无法将“nrm”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保路径正确， 然后再试一次）。 - 八英里 - 博客园 (cnblogs.com)](https://www.cnblogs.com/deepalley/p/10854204.html)

常用：

nrm ls					显示可选镜像

nrm use 镜像名				切换镜像

## nodejs热部署（全局）：

nodemon

[nodemon - npm (npmjs.com)](https://www.npmjs.com/package/nodemon)

常用：

输入    nodemon + 需启动的js文件

可实现热部署nodejs



## 卸载node_modules(全局)：

 rimraf

常用：

在node_modules的上级目录上输入

 rimraf node_modules

即可删除node_modules

参考：

[删除node_modules - 窈窕淑女 - 博客园 (cnblogs.com)](https://www.cnblogs.com/veraNotes/p/12161332.html)

## cors

## mysql

## express-session

添加session支持

## jsonwebtoken 

用于生成 JWT 字符串

## express-jwt 

用于将 JWT 字符串解析还原成 JSON 对象

## 加密相关：

[2. 登录注册 - api_server_ev (escook.cn)](http://escook.cn:8088/#/mds/2.login_reg?id=_233-对密码进行加密处理)

bcryptjs

- 加密之后的密码，**无法被逆向破解**
- 同一明文密码多次加密，得到的**加密结果各不相同**，保证了安全性

md5

## 优化表单数据验证：

[2. 登录注册 - api_server_ev (escook.cn)](http://escook.cn:8088/#/mds/2.login_reg?id=_25-优化表单数据验证)

老师根据joi自己写的包

安装 `@hapi/joi` 包，为表单中携带的每个数据项，定义验证规则：

安装 `@escook/express-joi` 中间件，来实现自动对表单数据进行验证的功能：



# 第一天：

## 1.nodejs简介：

Node.js 是一个基于 Chrome V8 引擎的 JavaScript 运行环境。

![image-20220320160418011](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320160418011.png)

① 浏览器是 JavaScript 的前端运行环境。
② Node.js 是 JavaScript 的后端运行环境。
③ **Node.js 中无法调用 DOM 和 BOM 等**
**浏览器内置 API。**

## 2.nodejs可以做什么？

Node.js 作为一个 JavaScript 的运行环境，仅仅提供了基础的功能和 API。然而，基于 Node.js 提供的这些基础能，很多强大的工具和框架如雨后春笋，层出不穷，所以学会了 Node.js ，可以让前端程序员胜任更多的工作和岗位：

① 基于 Express 框架（http://www.expressjs.com.cn/），可以快速构建 Web 应用
② 基于 Electron 框架（https://electronjs.org/），可以构建跨平台的桌面应用
③ 基于 restify 框架（http://restify.com/），可以快速构建 API 接口项目
④ 读写和操作数据库、创建实用的命令行工具辅助前端开发、etc...

总之：Node.js 是大前端时代的“大宝剑”，有了 Node.js 这个超级 buff 的加持，前端程序员的行业竞争力会越来越强！

## 3.终端常用：

按住shift键同时右键鼠标，快速进入powershell

文件目录前输入cmd，快速进入cmd

我们在终端使用node + js文件可以运行js文件

在 Windows 的 powershell 或 cmd 终端中，我们可以通过如下快捷键，来提高终端的操作效率：
① 使用 ↑ 键，可以快速定位到上一次执行的命令
② 使用 tab 键，能够快速补全路径
③ 使用 esc 键，能够快速清空当前已输入的命令
④ 输入 cls 命令，可以清空终端

## 4.fs 文件系统模块：

![image-20220320161836432](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320161836432.png)

### 读文件：

![image-20220320161933512](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320161933512.png)

```js
const fs=require("fs")

fs.readFile('./files/1.txt',"utf8",function(err, dataStr,c){
    console.log(err);
    console.log("---------------");
      // 如果读取失败，则 err 的值为 错误对象，dataStr 的值为 undefined
    console.log(dataStr);
    console.log("---------------");
    console.log(c);
})
```

成功的情况：

![image-20220320162546035](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320162546035.png)

### 写文件：

![image-20220320162838919](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320162838919.png)

```js
const fs = require("fs")
fs.writeFile("./files/3.txt","Hello 世界","utf8",function(err,b){
    if (err) {
        return console.log('文件写入失败！' + err.message)
      }
      console.log(b);
    console.log('文件写入成功！')
})
```

![image-20220320163343303](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320163343303.png)

### 案例：

![image-20220320164810245](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320164810245.png)

核心实现步骤
① 导入需要的 fs 文件系统模块
② 使用 fs.readFile() 方法，读取素材目录下的 成绩.txt 文件
③ 判断文件是否读取失败
④ 文件读取成功后，处理成绩数据
⑤ 将处理完成的成绩数据，调用 fs.writeFile() 方法，写入到新文件 成绩-ok.txt 中

```js
const fs = require("fs")
fs.readFile("../素材/成绩.txt","utf8",function(error,data){
    // console.log(data);
    if (error) {
        return console.log('读取文件失败！' + err.message);
    }
    let oldData = data.split(" ");
    let newData = [];
    oldData.forEach((item)=>{
        newData.push(item.replace("=",":"))
    })
    //有坑，必须转化为字符串才能写
    let str=newData.join("\r\n")
    fs.writeFile("./files/4.txt",str,"utf8",function(error){
        if (error) {
            return console.log('写入文件失败！' + err.message)
          }
          console.log('成绩写入成功！')
    })
})
```

![image-20220320164715850](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320164715850.png)

![image-20220320164755073](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320164755073.png)

### 路径动态拼接的问题：

在使用 fs 模块操作文件时，如果提供的操作路径是以 ./ 或 ../ 开头的相对路径时，很容易出现路径动态拼接错误的问题。

原因：代码在运行的时候，会以执行 node 命令时所处的目录，动态拼接出被操作文件的完整路径。

解决方案：在使用 fs 模块操作文件时，直接提供完整的路径，不要提供 ./ 或 ../ 开头的相对路径，从而防止路径动态拼接的问题。

```js
const fs = require('fs')

// 出现路径拼接错误的问题，是因为提供了 ./ 或 ../ 开头的相对路径
// 如果要解决这个问题，可以直接提供一个完整的文件存放路径就行
/* fs.readFile('./files/1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
}) */

// 移植性非常差、不利于维护
/* fs.readFile('C:\\Users\\escook\\Desktop\\Node.js基础\\day1\\code\\files\\1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
}) */

// __dirname 表示当前文件所处的目录
// console.log(__dirname)

fs.readFile(__dirname + '/files/1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
})

```

##  5.path 路径模块:

path 模块是 Node.js 官方提供的、用来处理路径的模块。它提供了一系列的方法和属性，用来满足用户对路径的处理
需求。

例如：
 	path.join() 方法，用来将多个路径片段拼接成一个完整的路径字符串
	 path.basename() 方法，用来从路径字符串中，将文件名解析出来
如果要在 JavaScript 代码中，使用 path 模块来处理路径，则需要使用如下的方式先导入它：

```js
const path = require('path')
```

### path.join()拼接路径:

![image-20220320170213105](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320170213105.png)

```js
const path = require('path')
const fs = require('fs')

// 注意：  ../ 会抵消前面的路径
// const pathStr = path.join('/a', '/b/c', '../../', './d', 'e')
// console.log(pathStr)  // \a\b\d\e

// fs.readFile(__dirname + '/files/1.txt')

fs.readFile(path.join(__dirname, './files/1.txt'), 'utf8', function(err, dataStr) {
  if (err) {
    return console.log(err.message)
  }
  console.log(dataStr)
})

```

### path.basename()获取文件名：

![image-20220320170156411](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320170156411.png)

![image-20220320170248904](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320170248904.png)

### path.extname()获取扩展名:

![image-20220320170408941](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320170408941.png)

![image-20220320170530528](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320170530528.png)

## 6.时钟案例：

![image-20220320171149138](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320171149138.png)

### 步骤：

① 创建两个正则表达式，分别用来匹配 <style> 和 <script> 标签
② 使用 fs 模块，读取需要被处理的 HTML 文件
③ 自定义 resolveCSS 方法，来写入 index.css 样式文件
④ 自定义 resolveJS 方法，来写入 index.js 脚本文件
⑤ 自定义 resolveHTML 方法，来写入 index.html 文件





1.注意正则表达式的调用方法，返回数组的第一项要把标签用空项替换掉。

2.感觉老师这3个函数可以封装成一个的

3.fs.writeFile() 方法只能用来创建文件，不能用来创建路径

4.重复调用 fs.writeFile() 写入同一个文件，新写入的内容会覆盖之前的旧内容。

```js
// 1.1 导入 fs 模块
const fs = require('fs')
// 1.2 导入 path 模块
const path = require('path')

// 1.3 定义正则表达式，分别匹配 <style></style> 和 <script></script> 标签
const regStyle = /<style>[\s\S]*<\/style>/
const regScript = /<script>[\s\S]*<\/script>/

// 2.1 调用 fs.readFile() 方法读取文件
fs.readFile(path.join(__dirname, '../素材/index.html'), 'utf8', function(err, dataStr) {
  // 2.2 读取 HTML 文件失败
  if (err) return console.log('读取HTML文件失败！' + err.message)
  // 2.3 读取文件成功后，调用对应的三个方法，分别拆解出 css, js, html 文件
  resolveCSS(dataStr)
  resolveJS(dataStr)
  resolveHTML(dataStr)
})

// 3.1 定义处理 css 样式的方法
function resolveCSS(htmlStr) {
  // 3.2 使用正则提取需要的内容
  const r1 = regStyle.exec(htmlStr)
  // 3.3 将提取出来的样式字符串，进行字符串的 replace 替换操作
  const newCSS = r1[0].replace('<style>', '').replace('</style>', '')
  // 3.4 调用 fs.writeFile() 方法，将提取的样式，写入到 clock 目录中 index.css 的文件里面
  fs.writeFile(path.join(__dirname, './clock/index.css'), newCSS, function(err) {
    if (err) return console.log('写入 CSS 样式失败！' + err.message)
    console.log('写入样式文件成功！')
  })
}

// 4.1 定义处理 js 脚本的方法
function resolveJS(htmlStr) {
  // 4.2 通过正则，提取对应的 <script></script> 标签内容
  const r2 = regScript.exec(htmlStr)
  // 4.3 将提取出来的内容，做进一步的处理
  const newJS = r2[0].replace('<script>', '').replace('</script>', '')
  // 4.4 将处理的结果，写入到 clock 目录中的 index.js 文件里面
  fs.writeFile(path.join(__dirname, './clock/index.js'), newJS, function(err) {
    if (err) return console.log('写入 JavaScript 脚本失败！' + err.message)
    console.log('写入 JS 脚本成功！')
  })
}

// 5.1 定义处理 HTML 结构的方法
function resolveHTML(htmlStr) {
  // 5.2 将字符串调用 replace 方法，把内嵌的 style 和 script 标签，替换为外联的 link 和 script 标签
  const newHTML = htmlStr.replace(regStyle, '<link rel="stylesheet" href="./index.css" />').replace(regScript, '<script src="./index.js"></script>')
  // 5.3 写入 index.html 这个文件
  fs.writeFile(path.join(__dirname, './clock/index.html'), newHTML, function(err) {
    if (err) return console.log('写入 HTML 文件失败！' + err.message)
    console.log('写入 HTML 页面成功！')
  })
}

```

### 效果：

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/67.gif" style="zoom: 100%"></img>

## 需注意：

### 1.__dirname 表示当前文件所处的目录path

### 2.path.join（）中   ../ 会抵消前面的路径

### 3.有时间的话研究研究时钟案例源码吧，虽然和nodejs没多大关系

### 4.时钟案例老师调用正则表达式的方法，以前没怎么用过

https://zh.javascript.info/regexp-methods#regexpexecstr

### 5.了解下path.resolve方法，webpack里面常用

传送门：

[path.join与path.resolve的区别你知道吗？ - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/250661603)



# 第二天：

## http模块：

![image-20220320173048523](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320173048523.png)

![image-20220320173314743](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320173314743.png)

### 1.创建web服务器基本步骤：

![image-20220320173746593](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320173746593.png)

#### 导入http模块：

![image-20220320174222386](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320174222386.png)

#### 创建 web 服务器实例：

![image-20220320174254376](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320174254376.png)

#### 为服务器实例绑定 request 事件：

![image-20220320174325263](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320174325263.png)

#### 启动服务器：

![image-20220320174339941](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320174339941.png)



```js
const http = require("http")

const server = http.createServer()

server.on("request",function(req,resp){
    console.log("触发请求");
})

server.listen("8080",()=>{
    console.log("服务器成功启动在http://127.0.0.1:8080");
})
```

![image-20220320175008924](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320175008924.png)



### 2.请求和响应：

![image-20220320175126397](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320175126397.png)

![image-20220320175147023](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320175147023.png)

```js
const http = require('http')
const server = http.createServer()
// req 是请求对象，包含了与客户端相关的数据和属性
server.on('request', (req, res) => {
  // req.url 是客户端请求的 URL 地址
  const url = req.url
  // req.method 是客户端请求的 method 类型
  const method = req.method
  const str = `Your request url is ${url}, and request method is ${method}`
  console.log(str)
  // 调用 res.end() 方法，向客户端响应一些内容
  res.end(str)
})
server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})

```

用apipost测试

![image-20220320180203112](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320180203112.png)

![image-20220320180912224](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320180912224.png)



#### 中文乱码问题：

这个解决乱码问题的方法和java的一模一样

![image-20220320175228206](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320175228206.png)

```js
res.setHeader('Content-Type', 'text/html; charset=utf-8')
```



### 3.根据不同的 url 响应不同的 html 内容:

```js
server.on('request', (req, res) => {
  // 1. 获取请求的 url 地址
  const url = req.url
  // 2. 设置默认的响应内容为 404 Not found
  let content = '<h1>404 Not found!</h1>'
  // 3. 判断用户请求的是否为 / 或 /index.html 首页
  // 4. 判断用户请求的是否为 /about.html 关于页面
  if (url === '/' || url === '/index.html') {
    content = '<h1>首页</h1>'
  } else if (url === '/about.html') {
    content = '<h1>关于页面</h1>'
  }
  // 5. 设置 Content-Type 响应头，防止中文乱码
  res.setHeader('Content-Type', 'text/html; charset=utf-8')
  // 6. 使用 res.end() 把内容响应给客户端
  res.end(content)
})
```

![image-20220320191104661](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320191104661.png)

![image-20220320191127320](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320191127320.png)

![image-20220320191045299](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320191045299.png)

### 4.案例：实现 clock 时钟的 web 服务器:

![image-20220320191505243](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320191505243.png)

```js
const fs = require("fs");
const path = require("path")
const http = require("http")

const server = http.createServer()

server.on('request',(req,res)=>{
    //这句话没注释掉，会得不到css样式
    // res.setHeader('Content-Type', 'text/html; charset=utf-8')
    let url = req.url
    let fpath=''
    if(url==='/'){
        fpath=path.join(__dirname,'./clock/index.html')
    }else{
        fpath=path.join(__dirname,'/clock',url)
    }
    console.log(fpath);
    fs.readFile(fpath,"utf8",function(err,dataStr){
        if(err){
            return res.end("404")
        }
        res.end(dataStr)
    })
})

server.listen(80,()=>{
    console.log("服务器已在http://127.0.0.1启动");
})
```

![image-20220320193906789](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320193906789.png)

![image-20220320193953306](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320193953306.png)



## 模块化：

### 1.模块化的基本概念：

模块化是指解决一个复杂问题时，自顶向下逐层把系统划分成若干模块的过程。对于整个系统来说，模块是可组
合、分解和更换的单元。

编程领域中的模块化，就是遵守固定的规则，把一个大文件拆成独立并互相依赖的多个小模块。
把代码进行模块化拆分的好处：
① 提高了代码的复用性
② 提高了代码的可维护性
③ 可以实现按需加载

### 2.分类：

![image-20220320194333223](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320194333223.png)

require()里面可以不写后缀js

![image-20220320194438277](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320194438277.png)

### 3.模块作用域：

![image-20220320194641963](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320194641963.png)

### 4.向外共享模块作用域中的成员：

#### module：

```js
console.log(module)
```

![image-20220320195311355](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320195311355.png)

#### module.exports：

![image-20220320195420617](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320195420617.png)

我们在module.exports里添加很多自定义属性

```js
// 在一个自定义模块中，默认情况下， module.exports = {}

const age = 20

// 向 module.exports 对象上挂载 username 属性
module.exports.username = 'zs'
// 向 module.exports 对象上挂载 sayHello 方法
module.exports.sayHello = function() {
  console.log('Hello!')
}
module.exports.age = age

```

访问一下

```js
// 在外界使用 require 导入一个自定义模块的时候，得到的成员，
// 就是 那个模块中，通过 module.exports 指向的那个对象
const m = require('./11.自定义模块')

console.log(m)
```

![image-20220320200003723](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320200003723.png)

##### 指向新对象：

```js
// 在一个自定义模块中，默认情况下， module.exports = {}

const age = 20

// 向 module.exports 对象上挂载 username 属性
module.exports.username = 'zs'
// 向 module.exports 对象上挂载 sayHello 方法
module.exports.sayHello = function() {
  console.log('Hello!')
}
module.exports.age = age

// 让 module.exports 指向一个全新的对象
module.exports = {
  nickname: '小黑',
  sayHi() {
    console.log('Hi!')
  }
}

```

使用 require() 方法导入模块时，导入的结果，**永远以 module.exports 指向的对象为准**。

![image-20220320200121927](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320200121927.png)

#### exports：

![image-20220320200352630](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320200352630.png)

```js
// console.log(exports)
// console.log(module.exports)

// console.log(exports === module.exports)  true

const username = 'zs'

module.exports.username = username
exports.age = 20
exports.sayHello = function() {
  console.log('大家好！')
}

// 最终，向外共享的结果，永远都是 module.exports 所指向的对象

```

打印一下

![image-20220320200520229](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320200520229.png)

#### exports和module.exports使用误区：

尽量只使用两者之一

![image-20220320201001316](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320201001316.png)

![image-20220321101653521](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321101653521.png)

![image-20220321101813323](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321101813323.png)

### 5.模块化规范：

![image-20220320201212546](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320201212546.png)

## 需注意：

### 1.停止服务器ctrl+c

### 2.在实际应用中，URL 中的 80 端口可以被省略。

### 3.path.join()里面的路径加不加点的问题

### 4.案例：实现 clock 时钟的 web 服务器。设置响应头为啥获取不到css样式了？

只有是html文件的时候 才加上res.setHeader("Content-Type", "text/html; charset=utf-8");

可以看到发送了4个请求

![image-20220320193653213](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320193653213.png)

# 第三天：

## npm与包：

不同于 Node.js 中的内置模块与自定义模块，包是由第三方个人或团队开发出来的，免费供所有人使用。

注意：Node.js 中的包都是免费且开源的，不需要付费即可免费下载使用。



![image-20220320201443703](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320201443703.png)



国外有一家 IT 公司，叫做 npm, Inc. 这家公司旗下有一个非常著名的网站： https://www.npmjs.com/ ，它是全球最
大的包共享平台，你可以从这个网站上搜索到任何你需要的包，只要你有足够的耐心！
到目前位置，全球约 1100 多万的开发人员，通过这个包共享平台，开发并共享了超过 120 多万个包 供我们使用。
npm, Inc. 公司提供了一个地址为 https://registry.npmjs.org/ 的服务器，来对外共享所有的包，我们可以从这个服务
器上下载自己所需要的包。
注意：
1.从 https://www.npmjs.com/ 网站上搜索自己所需要的包
2.从 https://registry.npmjs.org/ 服务器上下载自己需要的包

![image-20220320201641337](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320201641337.png)

### 0.初始化：

npm init -y

这个-y就是不断yes的意思，会初始化一个默认package.json文件

### 1.安装包：

![image-20220320202542058](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320202542058.png)

![image-20220320202927184](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320202927184.png)

### 2.安装指定版本包：

默认情况下，使用 npm install 命令安装包的时候，会自动安装最新版本的包。如果需要安装指定版本的包，可以在包
名之后，通过 @ 符号指定具体的版本

![image-20220320203606298](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320203606298.png)

### 3.包管理文件：

#### package.json：

npm 规定，在项目根目录中，必须提供一个叫做 package.json 的包管理配置文件。用来记录与项目有关的一些配置
信息。例如：
1.项目的名称、版本号、描述等

2.项目中都用到了哪些包

3.哪些包只在开发期间会用到

4.那些包在开发和部署时都需要用到

![image-20220320204112557](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320204112557.png)

![image-20220320204132426](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320204132426.png)

#### dependencies:

![image-20220320204446669](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320204446669.png)

#### 一次性安装所有的包:

![image-20220320204655701](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320204655701.png)

![image-20220320204711017](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320204711017.png)

#### 卸载包:

![image-20220320204742796](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320204742796.png)

##### 补充：

 用rimraf可以安全删除node_modules文件夹

[删除node_modules - 窈窕淑女 - 博客园 (cnblogs.com)](https://www.cnblogs.com/veraNotes/p/12161332.html)

经测试，只需保留package.json文件，进行npm install命令安装就可以，会自动生成package-lock.json文件

#### devDependencies :

![image-20220320204843666](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320204843666.png)

### 4.解决下包速度慢的问题：

在使用 npm 下包的时候，默认从国外的 https://registry.npmjs.org/ 服务器进行下载，此时，网络数据的传输需要经
过漫长的海底光缆，因此下包速度会很慢。

#### 淘宝镜像：

![image-20220320205117641](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320205117641.png)

![image-20220320205206380](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320205206380.png)

```
npm config get registry
npm config set registry=https://registry.npm.taobao.org/
```

#### nrm:

下载使用失败……

![image-20220320205554044](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320205554044.png)

![image-20220321104006685](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321104006685.png)

### 5.包的分类：

#### 项目包：

![image-20220321104112779](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321104112779.png)

#### 全局包：

![image-20220321104154671](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321104154671.png)

### 6.规范的包结构：

![image-20220321105233625](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321105233625.png)

[404 | Yarn (yarnpkg.com)](https://classic.yarnpkg.com/zh-Hans/docs/package-json)

网站挂了

### 7.开发属于自己的包：

![image-20220321110052378](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321110052378.png)

![image-20220321111058486](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321111058486.png)

这两个功能都很简单，就不展示了

![image-20220321110129201](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321110129201.png)

https://www.jianshu.com/p/86251523e898

也挂了

![image-20220321110036590](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321110036590.png)

#### 

#### package.json:

```js
{
  "name": "itheima-tools-fx7",
  "version": "1.1.0",
  "main": "index.js",
  "description": "提供了格式化时间、HTMLEscape相关的功能 by-fx7",
  "keywords": [
    "itheima",
    "dateFormat",
    "escape"
  ],
  "license": "ISC"
}
```



#### index.js:

```js
// 这是包的入口文件

const date = require('./src/dateFormat')
const escape = require('./src/htmlEscape')

// 向外暴露需要的成员
module.exports = {
  ...date,
  ...escape
}

```

#### README.md:

~~~markdown
## 安装
```
npm install itheima-tools
```

## 导入
```js
const itheima = require('itheima-tools')
```

## 格式化时间
```js
// 调用 dateFormat 对时间进行格式化
const dtStr = itheima.dateFormat(new Date())
// 结果  2020-04-03 17:20:58
console.log(dtStr)
```

## 转义 HTML 中的特殊字符
```js
// 带转换的 HTML 字符串
const htmlStr = '<h1 title="abc">这是h1标签<span>123&nbsp;</span></h1>'
// 调用 htmlEscape 方法进行转换
const str = itheima.htmlEscape(htmlStr)
// 转换的结果 &lt;h1 title=&quot;abc&quot;&gt;这是h1标签&lt;span&gt;123&amp;nbsp;&lt;/span&gt;&lt;/h1&gt;
console.log(str)
```

## 还原 HTML 中的特殊字符
```js
// 待还原的 HTML 字符串
const str2 = itheima.htmlUnEscape(str)
// 输出的结果 <h1 title="abc">这是h1标签<span>123&nbsp;</span></h1>
console.log(str2)
```

## 开源协议
ISC
~~~

#### 测试：

```js

//这个地方，我们没写全地址 完整的应该是require('./itheima-tools/index')
//node会在itheima-tools文件夹下找到package.json文件，在里面找main对应的文件
const itheima = require('./itheima-tools')


// 格式化时间的功能
const dtStr = itheima.dateFormat(new Date())
console.log(dtStr)
console.log('-----------')



```

![image-20220321111658107](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321111658107.png)

### 8.发布包：

#### 注册账号：

![image-20220321112953427](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321112953427.png)

#### 登录账号：

![image-20220321113102382](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321113102382.png)

![image-20220321113459566](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321113459566.png)

#### 把包发布到npm上：

![image-20220321113649033](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321113649033.png)

![image-20220321113627313](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321113627313.png)

![image-20220321113849418](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321113849418.png)

#### 删除包：

npm unpublish 包名 --force

![image-20220321113951813](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321113951813.png)

![image-20220321114215851](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321114215851.png)

![image-20220321114149316](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321114149316.png)

## 模块的加载机制：

### 1.优先从缓存中加载：

![image-20220321114610541](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321114610541.png)

#### 测试：

04文件：

```js
require('./03.自定义模块')
require('./03.自定义模块')
require('./03.自定义模块')
```

03文件：

```js
console.log('ok')

```

![image-20220321115529105](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321115529105.png)

### 2.内置模块加载：

![image-20220321114643839](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321114643839.png)

### 3.自定义模块加载：

![image-20220321115027097](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321115027097.png)

之前不用写全的原因就是这个

### 4.第三方模块加载：

![image-20220321115415335](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321115415335.png)

### 5.目录作为模块：

![image-20220321115736030](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321115736030.png)

## 需注意：

### 1.npm全局包和nodejs全局包？

这两个有什么不一样的地方吗？

![image-20220321104643711](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321104643711.png)

![image-20220321104736832](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321104736832.png)

### 2.更新包？

虽然老师没讲，但我还是想知道如何更新发布的包

参考

[npm学习（七）之如何发布包、更新发布包、删除发布包 - 坤嬷嬷 - 博客园 (cnblogs.com)](https://www.cnblogs.com/kunmomo/p/11221786.html)

好像改改，然后重新发布就行了……

# 第四天：

## 初识Express：

### 1.简介：

![image-20220321122305964](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321122305964.png)

[Express - 基于 Node.js 平台的 web 应用开发框架 - Express 中文文档 | Express 中文网 (expressjs.com.cn)](https://www.expressjs.com.cn/)

![image-20220321122813684](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321122813684.png)

![image-20220321122840127](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321122840127.png)

### 2.安装：

![image-20220321123222637](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321123222637.png)

我安装在了整个项目根目录下

![image-20220321123310128](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321123310128.png)

### 3.基本使用：

#### 创建服务器：

```js
// 1. 导入 express
const express = require("express")
// 2. 创建 web 服务器
const server = express()
// 3. 启动 web 服务器
server.listen("80",()=>{
    console.log("服务器启动成功   https://127.0.0.1");
})
```

![image-20220321133216956](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321133216956.png)

#### 测试get和post：

```js
//测试get和post
server.get("/user",function(req,res){
    // 调用 express 提供的 res.send() 方法，向客户端响应一个 JSON 对象
  res.send({ name: 'zs', age: 20, gender: '男' })
})
server.post('/user', (req, res) => {
    // 调用 express 提供的 res.send() 方法，向客户端响应一个 文本字符串
    res.send('请求成功')
})
```

![image-20220321133811615](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321133811615.png)

![image-20220321133643679](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321133643679.png)

#### 获取 URL 中携带的查询参数:

![image-20220321134456173](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321134456173.png)

```js
//测试获取 URL 中携带的查询参数
server.get("/",function(req,res){
    // 注意：默认情况下，req.query 是一个空对象
    console.log(req.query);
    res.send(req.query)
})
```

![image-20220321134341582](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321134341582.png)

![image-20220321134324646](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321134324646.png)

#### 获取 URL 中的动态参数：

![image-20220321134533775](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321134533775.png)

```js
//测试获取 URL 中的动态参数
server.get('/user/:id/:username', (req, res) => {
    // req.params 是动态匹配到的 URL 参数，默认也是一个空对象
    console.log(req.params)
    res.send(req.params)
})
```

![image-20220321135009610](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321135009610.png)

![image-20220321135054631](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321135054631.png)

#### 托管静态资源：

![image-20220321135705861](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321135705861.png)

##### 托管多个静态资源目录：

![image-20220321135838712](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321135838712.png)

```js
const express = require("express")
const server = express()

server.listen("80",function(){
    console.log("服务器启动成功   https://127.0.0.1");
})

//启动顺序clock>files
//如果有同名文件只会访问顺序靠前的
//但是两个资源确实都是加载了的
server.use(express.static("./clock"))
server.use(express.static("./files"))
```

![image-20220321141137351](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321141137351.png)

![image-20220321141212557](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321141212557.png)

![image-20220321141243711](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321141243711.png)

##### 挂载路径前缀：

![image-20220321141313358](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321141313358.png)

#### nodemon：

就是用来热部署的

![image-20220321141636654](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321141636654.png)

![image-20220321141818777](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321141818777.png)

![image-20220321141832458](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321141832458.png)

### 4.Express 路由：

![image-20220321142528863](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321142528863.png)

#### 路由匹配过程：

![image-20220321142714401](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321142714401.png)

#### 模块化路由：

![image-20220321142758002](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321142758002.png)

##### 创建路由模块：

![image-20220321143226556](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321143226556.png)

##### 注册路由模块：

![image-20220321143238402](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321143238402.png)

##### 为路由模块添加前缀:

![image-20220321143347499](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321143347499.png)

##### 案例：

03.js：

```js
const express = require("express")
//创建路由对象
const router = express.Router()
//挂载路由
router.get("/list",function(req,res){
    res.send("get:list")
})
router.post("/list",function(req,res){
    res.send("post:list")
})
//向外导出路由
module.exports = router
//下面这个好像不行
// exports.router = router
```

02.js:

```js
const express = require("express")
const server = express()
//导入路由模块
const router = require("./03")

//注册路由模块
// server.use(router)
//也可以添加前缀
server.use("/api",router)

server.listen("80",function(){
    console.log('http://127.0.0.1')
})

```

![image-20220321144711497](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321144711497.png)

![image-20220321144757611](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321144757611.png)

### 5.Express 中间件：

#### 概念：

有点像后端的filter,listener这些

![image-20220321145526531](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321145526531.png)

![image-20220321145544139](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321145544139.png)

![image-20220321145630310](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321145630310.png)

![image-20220321145922192](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321145922192.png)

![image-20220321145942410](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321145942410.png)

#### 初体验：

##### 定义&全局中间件：

![image-20220321150122434](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321150122434.png)

![image-20220321150227172](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321150227172.png)

![image-20220321151153271](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321151153271.png)

```js
const express = require('express')
const app = express()

// // 定义一个最简单的中间件函数
// const mw = function (req, res, next) {
//   console.log('这是最简单的中间件函数')
//   // 把流转关系，转交给下一个中间件或路由
//   next()
// }

// // 将 mw 注册为全局生效的中间件
// app.use(mw)

// 这是定义全局中间件的简化形式
app.use((req, res, next) => {
  console.log('这是最简单的中间件函数')
  next()
})

app.get('/', (req, res) => {
  console.log('调用了 / 这个路由')
  res.send('Home page.')
})
app.get('/user', (req, res) => {
  console.log('调用了 /user 这个路由')
  res.send('User page.')
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})

```

通过apipost依次调用/和/user

![image-20220321151041717](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321151041717.png)

我又测试了一个不存在的接口，没有显示中间件函数的内容

##### 体会中间件作用：

![image-20220321151318221](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321151318221.png)

```js
const express = require('express')
const app = express()

// 这是定义全局中间件的简化形式
app.use((req, res, next) => {
  // 获取到请求到达服务器的时间
  const time = Date.now()
  // 为 req 对象，挂载自定义属性，从而把时间共享给后面的所有路由
  req.startTime = time
  next()
})

app.get('/', (req, res) => {
  res.send('Home page.' + req.startTime)
})
app.get('/user', (req, res) => {
  res.send('User page.' + req.startTime)
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})

```

![image-20220321151719680](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321151719680.png)

![image-20220321151741615](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321151741615.png)

##### 局部生效的中间件:

![image-20220321151845274](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321151845274.png)

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 定义中间件函数
const mw1 = (req, res, next) => {
  res.send('调用了局部生效的中间件')
  next()
}

// 2. 创建路由
app.get('/', mw1, (req, res) => {
  res.send('Home page.')
})
app.get('/user', (req, res) => {
  res.send('User page.')
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})

```

res.send('Home page.')这个应该被覆盖掉了

![image-20220321152052316](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321152052316.png)

![image-20220321152114302](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321152114302.png)

##### 多个中间件：

###### 多个全局中间件：

![image-20220321152346102](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321152346102.png)

###### 多个局部中间件：

![image-20220321152407134](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321152407134.png)

##### 注意事项:

![image-20220321152529509](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321152529509.png)

#### 中间件分类：

![image-20220321152744329](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321152744329.png)

##### 应用级别&路由级别中间件：

只是个概念而已，晓得有这个东西就行

![image-20220321160535647](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321160535647.png)

![image-20220321160602120](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321160602120.png)

##### 错误级别中间件：

![image-20220321160754873](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321160754873.png)

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 定义路由
app.get('/', (req, res) => {
  // 1.1 人为的制造错误
  throw new Error('服务器内部发生了错误！')
  res.send('Home page.')
})

// 2. 定义错误级别的中间件，捕获整个项目的异常错误，从而防止程序的崩溃
//写在路由后面
//这个同时也是个全局中间件
app.use((err, req, res, next) => {
  console.log('发生了错误！' + err.message)
  res.send('Error：' + err.message)
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})

```

![image-20220321161122045](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321161122045.png)

##### Express内置的中间件：

![image-20220321161525940](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321161525940.png)

###### express.json():

```js
const express = require('express')
const server = express()

server.use(express.json())

server.post("/user",function(req,res){
    console.log(req.body)
    res.send('ok')
})

server.listen(80, function () {
   console.log('Express server running at http://127.0.0.1')
})
```

![image-20220321164151515](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321164151515.png)

![image-20220321164040860](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321164040860.png)

###### express.urlencoded({ extended: false }):

```js
const express = require('express')
const server = express()

server.use(express.urlencoded({ extended: false }))

server.post("/user",function(req,res){
    console.log(req.body)
    res.send('ok')
})

server.listen(80, function () {
   console.log('Express server running at http://127.0.0.1')
})
```

![image-20220321165002509](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321165002509.png)

![image-20220321164927304](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321164927304.png)

##### 第三方中间件：

body-parser

![image-20220321170037023](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321170037023.png)

#### 案例：

##### data事件和end事件：

这部分是nodejs原生就有的，不是express独有的。类似request事件

客户端发送数据触发data事件

![image-20220321172143008](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321172143008.png)

数据接收完后，触发end事件

![image-20220321172154906](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321172154906.png)

```js
const express = require('express')
const server = express()

//这是一个全局中间件,处理表单数据
server.use(function(req,res,next){

    let str = ''
    req.on("data",(chunk)=>{
        str +=chunk
        console.log(chunk,"chunk里的数据");
    })

    req.on("end",()=>{
        console.log(str);
    })
})


server.listen(80, function () {
   console.log('Express server running at http://127.0.0.1')
})
```

没有加next()

所以没有响应

![image-20220321173259835](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321173259835.png)

##### querystring：

![image-20220321174241009](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321174241009.png)

```js
//已经弃用querystring,官方文档建议用URLSearchParams，但我不知道用法……
//弹幕大神提醒我用qs
const qs = require("qs")


//这是一个全局中间件,处理表单数据
server.use(function(req,res,next){

    let str = ''
    req.on("data",(chunk)=>{
        str +=chunk
        console.log(chunk,"chunk里的数据");
    })

    req.on("end",()=>{
        console.log(qs.parse(str));        
    })
})
```

![image-20220321175109733](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321175109733.png)

##### req.body:

![image-20220321175728972](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321175728972.png)

```js
//这是一个全局中间件,处理表单数据
server.use(function(req,res,next){

    let str = ''
    req.on("data",(chunk)=>{
        str +=chunk
        // console.log(chunk,"chunk里的数据");
    })

    req.on("end",()=>{
        req.body=qs.parse(str)
        //放行为啥在这里呢？    
        next()
    })

})

server.post("/user",function(req,res){
    res.send(req.body)
})
```

![image-20220321181633484](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321181633484.png)

##### 封装成模块：

![image-20220321181748440](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321181748440.png)

这个就是不用中间件简写形式，写成完整的函数，再用module.exports暴露出去你写的中间件函数。

主程序里面接收下就行了

```js
// 1. 导入自己封装的中间件模块
const customBodyParser = require('./14.custom-body-parser')
// 2. 将自定义的中间件函数，注册为全局可用的中间件
server.use(customBodyParser)
```

### 6.使用 Express 写接口:

核心思路就是主程序写一个服务器，再用router写api接口，主程序导入api即可。

#### 小案例：

只演示了get，其他请求一个道理。

##### 主程序：(15.js)

```js
const express = require('express')
const server = express()
//引入api路由
const router = require("./16")
//注册路由，这里添加了前缀
//请求的时候一定不要忘了前缀api
server.use("/api",router)

server.listen(80, function () {
   console.log('Express server running at http://127.0.0.1')
})
```

##### api路由:(16.js)

```js
const express = require('express')
const router = express.Router()

//编写接口
router.get("/get",function(req,res){
    console.log(req.query);
    res.send({
        status: 0, // 0 表示处理成功，1 表示处理失败
        msg: 'api/get 请求成功！', // 状态的描述
        data: req.query, // 需要响应给客户端的数据
    })
})

//导出
module.exports = router


```



![image-20220322131132868](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322131132868.png)

#### 请求跨域问题：

协议，域名，端口不同都会有跨域问题

传送门：

[面试官问《你是如何解决跨域的》想知道点什么？ - 掘金 (juejin.cn)](https://juejin.cn/post/7067711812535320612)

![image-20220322132305403](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322132305403.png)

##### 使用cors中间件解决：

![image-20220322134228488](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322134228488.png)

使用jquery封装好的ajax测试，因为打开的是本机html，协议都不同，所以绝对会有跨域问题

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <script src="https://cdn.staticfile.org/jquery/3.4.1/jquery.min.js"></script>
  </head>
  <body>
    <button id="btnGET">GET</button>
    <button id="btnPOST">POST</button>
    <!-- <button id="btnDelete">DELETE</button>
    <button id="btnJSONP">JSONP</button> -->

    <script>
      $(function () {
        // 1. 测试GET接口
        $('#btnGET').on('click', function () {
          $.ajax({
            type: 'GET',
            url: 'http://127.0.0.1/api/get',
            data: { name: 'zs', age: 20 },
            success: function (res) {
              console.log(res)
            },
          })
        })
        // 2. 测试POST接口
        $('#btnPOST').on('click', function () {
          $.ajax({
            type: 'POST',
            url: 'http://127.0.0.1/api/post',
            data: { bookname: '水浒传', author: '施耐庵' },
            success: function (res) {
              console.log(res)
            },
          })
        })
      })
    </script>
  </body>
</html>

```



主程序：

api就不展示了

```js
const express = require('express')
const server = express()
// 一定要在路由之前，配置 cors 这个中间件，从而解决接口跨域的问题
const cors = require('cors')
server.use(cors())

const router = require("./16")
server.use("/api",router)

server.listen(80, function () {
   console.log('Express server running at http://127.0.0.1')
})
```

轻松解决：

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/68.gif" style="zoom: 100%"></img>

##### 原理：

![image-20220322134914764](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322134914764.png)



![image-20220322134937020](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322134937020.png)

###### 相关响应头：

想限制特定网址访问？

![image-20220322135537970](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322135537970.png)

![image-20220322135709120](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322135709120.png)

想发送额外请求头信息？

![image-20220322135937169](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322135937169.png)

想使用其他请求方法？

![image-20220322140021062](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322140021062.png)

##### cors请求分类：

客户端在请求 CORS 接口时，根据请求方式和请求头的不同，可以将 CORS 的请求分为两大类，分别是：
① 简单请求
② 预检请求

###### 简单请求：

![image-20220322140608743](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322140608743.png)

###### 预检请求：

就是简单请求的对立面

![image-20220322140642876](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322140642876.png)

###### 二者区别：

![image-20220322141013626](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322141013626.png)

我们测试一个delete请求，确实发送了两次，而且预检请求大小为0

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/69.gif" style="zoom: 100%"></img>

##### JSONP:

用cors是主流

![image-20220322142219606](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322142219606.png)

![image-20220322142313812](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322142313812.png)



![image-20220322143106628](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322143106628.png)



测试json代码

```js
// 4. 为 JSONP 按钮绑定点击事件处理函数
        $('#btnJSONP').on('click', function () {
          $.ajax({
            type: 'GET',
            url: 'http://127.0.0.1/api/jsonp',
            dataType: 'jsonp',
            success: function (res) {
              console.log(res)
            },
          })
        })
```

主程序：

```js
// 必须在配置 cors 中间件之前，配置 JSONP 的接口
server.get('/api/jsonp', (req, res) => {
    // TODO: 定义 JSONP 接口具体的实现过程
    // 1. 得到函数的名称
    const funcName = req.query.callback
    // 2. 定义要发送到客户端的数据对象
    const data = { name: 'zs', age: 22 }
    // 3. 拼接出一个函数的调用
    const scriptStr = `${funcName}(${JSON.stringify(data)})`
    // 4. 把拼接的字符串，响应给客户端
    res.send(scriptStr)
})
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/70.gif" style="zoom: 100%"></img>

script请求就是加载资源，遇到函数调用字符串，本地下载后就会执行，callback函数逻辑在客户端代码中，服务器这块只管返回函数调用

## 需注意：

### 1.导出路由区别？

exports.router = router 和 module.exports = router

按理说应该没啥区别，可是只有module.exports = router才能正常运行

exports.router的报错信息：

TypeError: Router.use() requires a middleware function but got a Object

![image-20220321145250241](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220321145250241.png)

### 2.res.send()

具体看五级标题：局部生效的中间件:

好像会把接口里面的res.send覆盖掉，不确定

而且这个res.send()执行完以后，有时候还是会执行后面的代码，这一点必须深究。

### 3.application/x-www-form-urlencoded

具体在六级标题  express.urlencoded({ extended: false }):

这种post正文格式没怎么使用过

### 4.URLSearchParams还有qs用法

五级标题querystring：

### 5.req.body？

[node.js取参四种方法req.body,req.params,req.param,req.body - 你怕黑暗么 - 博客园 (cnblogs.com)](https://www.cnblogs.com/jkingdom/p/8065202.html)

博客中提到的body-parser已经被内置的express.urlencoded替代

### 6.中间件里面next()和req的end事件触发时机？

五级标题req.body

### 7.cors解决跨域问题原理？

讲的不是很清楚……想深入了解

传松门：[跨域资源共享 CORS 详解 - 阮一峰的网络日志 (ruanyifeng.com)](https://www.ruanyifeng.com/blog/2016/04/cors.html)

[面试官问《你是如何解决跨域的》想知道点什么？ - 掘金 (juejin.cn)](https://juejin.cn/post/7067711812535320612)

### 8.预检请求？

以前没怎么用过，多了解了解

### 9.JSONP?

虽然不怎么用，但还是了解了解

# 第五天：

## 数据库操作：

老师演示用的是MySQL,可视化软件是SQLServer.这部分太熟了，就跳了。

我用的数据库是之前一个数据库的克隆数据库,测试表结构如下，有几个表是需要这个表当外键的，当由于是克隆品，

没必要关心这些的。但是以后真正上线，还是要管管的

![image-20220322165937473](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322165937473.png)

![image-20220322171715427](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322171715427.png)

直接来到nodeJs如何操作数据库



![image-20220322163909921](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322163909921.png)

### 连接数据库：

![image-20220322191211362](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322191211362.png)

![image-20220322164841212](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322164841212.png)

![image-20220322164955362](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322164955362.png)

```js
const mysql = require("mysql")
const db = mysql.createPool({
    host: 'localhost',//不用写接口 写ip地址就行
    user: 'root',
    password: 'Plm098765',
    database: 'test_nodejs'
})

db.query("select 1",function(err,results){
    if(err){
        return console.log(err.message);
    }
    console.log(results);
})
```

![image-20220322164930484](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322164930484.png)

### 查询数据：

```js
db.query("select * from user",function(err,results){
    if(err){
        return console.log(err.message);
    }
    console.log(results);
})
```

![image-20220322170303044](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322170303044.png)

### 插入数据：

（由于我用的是nodemon,所以一保存就会插入数据，会导致冲突，注意下）

```js
db.query(insert_sql,[user.userName,user.userPassword],function(err,results){
    if(err){
        return console.log(err.message);
    }
    //判断影响行数
    if(results.affectedRows===1){
        console.log(results,"插入数据成功");
    }
})
```

![image-20220322171825117](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322171825117.png)





![image-20220322171325533](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322171325533.png)

#### 简洁写法：

```js
const user = {userName:"小冯_3",userPassword:"1"}
const insert_sql = 'insert into user set ?'

db.query(insert_sql,user,function(err,results){
    if(err){
        return console.log(err.message);
    }
    //判断影响行数
    if(results.affectedRows===1){
        console.log(results,"插入数据成功");
    }
})
```

![image-20220322173252877](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322173252877.png)

![image-20220322173129014](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322173129014.png)

后面的就不演示了

### 修改数据：

![image-20220322173420705](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322173420705.png)

#### 简洁写法：

![image-20220322173445059](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322173445059.png)

### 删除数据：

![image-20220322173527071](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322173527071.png)

#### 标记删除：

![image-20220322173553228](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322173553228.png)

## 需注意：

### 1.关于这个安装的mysql模块

有没有类似Mybatis，MybatisPlus的框架呢？sql语句变多后，管理还是很麻烦啊

# 第六天

## web开发模式：

目前主流的 Web 开发模式有两种，分别是：
① 基于服务端渲染的传统 Web 开发模式
② 基于前后端分离的新型 Web 开发模式

更多：

[(91 封私信 / 80 条消息) 到底什么才是服务端渲染？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/379563505)

### 服务端渲染：

![image-20220322175758843](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322175758843.png)

![image-20220322175830145](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322175830145.png)

### 前后端分离：

前后端分离的概念：前后端分离的开发模式，依赖于 Ajax 技术的广泛应用。简而言之，前后端分离的 Web 开发模式，
就是后端只负责提供 API 接口，前端使用 Ajax 调用接口的开发模式。

![image-20220322175914606](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322175914606.png)

### 如何选择？

![image-20220322175941687](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322175941687.png)

## 身份认证：

![image-20220322180032279](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322180032279.png)

身份认证的目的，是为了确认当前所声称为某种身份的用户，确实是所声称的用户。例如，你去找快递员取快递，你要怎
么证明这份快递是你的。
在互联网项目开发中，如何对用户的身份进行认证，是一个值得深入探讨的问题。例如，如何才能保证网站不会错误的将
“马云的存款数额”显示到“马化腾的账户”上

![image-20220322180230208](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322180230208.png)



### Session认证：

#### http协议的无状态性：

![image-20220322180519513](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322180519513.png)

![image-20220322180546851](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322180546851.png)

#### cookie：

Cookie 是存储在用户浏览器中的一段不超过 4 KB 的字符串。它由一个名称（Name）、一个值（Value）和其它几个用
于控制 Cookie 有效期、安全性、使用范围的可选属性组成。
不同域名下的 Cookie 各自独立，每当客户端发起请求时，会自动把当前域名下所有未过期的 Cookie 一同发送到服务器。
Cookie的几大特性：
① 自动发送
② 域名独立
③ 过期时限
④ 4KB 限制

![image-20220322181808422](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322181808422.png)

![image-20220322181833792](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322181833792.png)

#### 原理：

![image-20220322181856526](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322181856526.png)

![image-20220322182040962](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322182040962.png)

#### express-session 中间件：

![image-20220322191742138](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322191742138.png)

![image-20220322191804838](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322191804838.png)

![image-20220322192447029](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322192447029.png)

![image-20220322193515870](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322193515870.png)

![image-20220322193534663](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322193534663.png)

#### 案例：

这里把接口放在一起了，有点乱

```js
const express = require('express')
const server = express()

//请配置 Session 中间件
const session = require('express-session')
server.use(
    session({
        secret: 'FengXiao7',  
        resave: false,              //固定写法
        saveUninitialized: true,    //固定写法
    })
)

server.use(express.static("./pages"))
server.use(express.urlencoded({ extended: false }))

//登录接口
server.post("/api/login", function (req, res) {
    //注意这里的username和password要和前端name匹配！！！
    if (req.body.username !== 'Admin' || req.body.password !== "123456") {
        return res.send({ status: 1, msg: '登录失败' })
    }
    // 登录成功后的用户信息，保存到 Session 中
    // 只有成功配置了 express-session 这个中间件之后，才能够通过 req 点出来 session 这个属性
    req.session.user = req.body // 用户的信息
    req.session.islogin = true // 用户的登录状态

    res.send({ status: 0, msg: '登录成功' })
})
//获取用户信息接口
server.get('/api/username', (req, res) => {
    // 从 Session 中获取用户的名称，响应给客户端
    if (!req.session.islogin) {
        return res.send({ status: 1, msg: 'fail' })
    }
    res.send({
        status: 0,
        msg: 'success',
        username: req.session.user.username,
    })
})
// 退出登录的接口
server.post('/api/logout', (req, res) => {
    //清空 Session 信息
    req.session.destroy()
    res.send({
        status: 0,
        msg: '退出登录成功',
    })
})

server.listen(80, function () {
    console.log('Express server running at http://127.0.0.1')
})
```

两个静态页面：

index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>后台主页</title>
  <script src="./jquery.js"></script>
</head>

<body>
  <h1>首页</h1>

  <button id="btnLogout">退出登录</button>

  <script>
    $(function () {

      // 页面加载完成后，自动发起请求，获取用户姓名
      $.get('/api/username', function (res) {
        // status 为 0 表示获取用户名称成功；否则表示获取用户名称失败！
        if (res.status !== 0) {
          alert('您尚未登录，请登录后再执行此操作！')
          location.href = './login.html'
        } else {
          alert('欢迎您：' + res.username)
        }
      })

      // 点击按钮退出登录
      $('#btnLogout').on('click', function () {
        // 发起 POST 请求，退出登录
        $.post('/api/logout', function (res) {
          if (res.status === 0) {
            // 如果 status 为 0，则表示退出成功，重新跳转到登录页面
            location.href = './login.html'
          }
        })
      })
    })
  </script>
</body>

</html>
```

login.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>登录页面</title>
  <script src="./jquery.js"></script>
</head>

<body>
  <!-- 登录表单 -->
  <form id="form1">
    <div>账号：<input type="text" name="username" autocomplete="off" /></div>
    <div>密码：<input type="password" name="password" /></div>
    <button>登录</button>
  </form>

  <script>
    $(function () {
      // 监听表单的提交事件
      $('#form1').on('submit', function (e) {
        // 阻止默认提交行为
        e.preventDefault()
        // 发起 POST 登录请求
        $.post('/api/login', $(this).serialize(), function (res) {
          // status 为 0 表示登录成功；否则表示登录失败！
          if (res.status === 0) {
            location.href = './index.html'
          } else {
            alert('登录失败！')
          }
        })
      })
    })
  </script>
</body>

</html>
```

##### 直接登录首页：

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/71.gif" style="zoom: 100%"></img>

##### 输入错误账号密码：

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/72.gif" style="zoom: 100%"></img>

##### 输入正确账号密码：

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/73.gif" style="zoom: 100%"></img>

##### 退出登录：

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/74.gif" style="zoom: 100%"></img>

### JWT认证：

JWT（英文全称：JSON Web Token）是目前最流行的跨域认证解决方案。

![image-20220322203433351](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322203433351.png)

#### 原理：

#### ![image-20220322203634559](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322203634559.png)

#### 组成：

![image-20220322203700961](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322203700961.png)

![image-20220322203823506](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322203823506.png)

![image-20220322203914435](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322203914435.png)

#### 在 Express 中使用 JWT：

![image-20220322204224411](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322204224411.png)

![image-20220322204604884](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322204604884.png)

![image-20220322205950751](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322205950751.png)

![image-20220322210009437](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220322210009437.png)

客户端请求时需要请求头添加Authorization字段，值为：Bearer+token

[(91 封私信 / 80 条消息) bearer token到底是什么？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/305585277/answer/551377366)

高版本需要新加算法配置项

```js
server.use(expressJWT({ secret: secretKey, algorithms: ['HS256'] }).unless({ path: [/^\/api\//] }))
```

![image-20220323125925894](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323125925894.png)

**在比较高的版本里面user被替换成了auth**

![image-20220323133227402](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323133227402.png)

#### 案例：

```js
const express = require('express')
const server = express()

const secretKey = "fengxiao7"
// JSON =》JWT 
const jwt = require("jsonwebtoken")
// JWT =》JSON 
const expressJWT = require('express-jwt')
const cors = require("cors")

server.use(cors())
server.use(express.urlencoded({ extended: false }))
// 只要配置成功了 express-jwt 这个中间件，就可以把解析出来的用户信息，挂载到 req.user 属性上 //以api开头的接口不需要权限
server.use(expressJWT({ secret: secretKey, algorithms: ['HS256'] }).unless({ path: [/^\/api\//] }))



//登录接口                                                                            
server.post("/api/login", function (req, res) {
    const userinfo = req.body
    if (userinfo.username !== 'admin' || userinfo.password !== '000000') {
        return res.send({
            status: 400,
            message: '登录失败！',
        })
    }

    // 登录成功之后，调用 jwt.sign() 方法生成 JWT 字符串。并通过 token 属性发送给客户端
    // 参数1：用户的信息对象(不要把密码写进去了)
    // 参数2：加密的秘钥
    // 参数3：配置对象，可以配置当前 token 的有效期。我的是200s过期
    const tokenStr = jwt.sign({ username: userinfo.username }, secretKey, { expiresIn: '300s' })
    res.send({
        status: 200,
        message: '登录成功！',
        token: tokenStr,
    })

})


// // 获取用户信息接口(有权限)
server.get('/admin/getinfo', function (req, res) {
    //这个req.user是expressJWT配置成功时，在我们使用带权限的接口时帮我们添加的
    // 使用 req.user 获取用户信息，并使用 data 属性将用户信息发送给客户端
    console.log(req.user)
    res.send({
        status: 200,
        message: '获取用户信息成功！',
        data: req.user, 
    })
})

//错误中间件，记住要放在所有路由后面
server.use((err, req, res, next) => {
    // 这次错误是由 token 解析失败导致的
    if (err.name === 'UnauthorizedError') {
      return res.send({
        status: 401,
        message: '无效的token',
      })
    }
    res.send({
      status: 500,
      message: '未知的错误',
    })
  })

server.listen(80, function () {
    console.log('Express server running at http://127.0.0.1')
})
```



##### 登录失败和登录成功：(无权限，成功生成JWT字符串)

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/75.gif" style="zoom: 100%"></img>

##### admin/getinfo（有权限，获取解密后的username）：

注意发送请求时，一定要添加请求头Authorization字段，值为：Bearer+token

客户端请求时需要请求头添加Authorization字段，值为：Bearer+jwt字符串



![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/76.gif)

![image-20220323135922609](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323135922609.png)

## 需注意：

### 1.有机会学习学习SEO吧

### 2.再深度了解一下session和cookie的关系吧

### 3.$(this).serialize()？

session案例中的login.html

### 4.JWT前端一定要记住写好响应头！

http://escook.cn:8088/#/)





