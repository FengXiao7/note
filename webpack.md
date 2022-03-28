# 参考：

[(91 封私信 / 81 条消息) webpack - 收藏夹 - 知乎 (zhihu.com)](https://www.zhihu.com/collection/792122958)

官网：

[概念 | webpack 中文文档 (docschina.org)](https://webpack.docschina.org/concepts/)

进阶：

[玩转 webpack (geekbang.org)](https://time.geekbang.org/course/intro/100028901)

# 说明：

## 1.webpack

**webpack** 是一个用于现代 JavaScript 应用程序的 静态模块打包工具。

### 我的见解：

我感觉现阶段我还没有达到可以自定义脚手架的地步，而且我的项目基本上都没有打包上线这个流程……而且如果只是使用的话，感觉只需要了解如何配置就行了。为以后的深入学习做准备吧。



传统MVC项目用不上，现在单页开发都cli脚手架工具生成，深度集成webpack配置，也不需要自己配置。基本上用不太到

但想了解原理，创建自己的脚手架，定义一些特色化设置，webpack还是必须要学的。



还有其他的打包工具，如vite，gulp，rollup等等，所以了解一下打包的原理还是很重要的



## 2.版本

老师教学用的版本，最好下载对应版本，免去了很多兼容性问题。5+版本多看官网文档吧

```json
"devDependencies": {
    "@babel/core": "^7.8.4",
    "@babel/polyfill": "^7.8.3",
    "@babel/preset-env": "^7.8.4",
    "add-asset-html-webpack-plugin": "^3.1.3",
    "babel": "^6.23.0",
    "babel-loader": "^8.0.6",
    "core-js": "^3.6.4",
    "css-loader": "^3.4.2",
    "eslint": "^6.8.0",
    "eslint-config-airbnb-base": "^14.0.0",
    "eslint-loader": "^3.0.3",
    "eslint-plugin-import": "^2.20.1",
    "file-loader": "^5.0.2",
    "html-loader": "^0.5.5",
    "html-webpack-plugin": "^3.2.0",
    "less": "^3.11.1",
    "less-loader": "^5.0.0",
    "mini-css-extract-plugin": "^0.9.0",
    "optimize-css-assets-webpack-plugin": "^5.0.3",
    "postcss-loader": "^3.0.0",
    "postcss-preset-env": "^6.7.0",
    "style-loader": "^1.1.3",
    "terser-webpack-plugin": "^2.3.5",
    "thread-loader": "^2.1.3",
    "url-loader": "^3.0.0",
    "webpack": "^4.41.6",
    "webpack-cli": "^3.3.11",
    "webpack-dev-server": "^3.10.3",
    "workbox-webpack-plugin": "^5.0.0"
  },
  "dependencies": {
    "jquery": "^3.4.1"
  },
```

## 

# 视频：

[尚硅谷新版Webpack5实战教程(从入门到精通)_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1e7411j7T5?spm_id_from=333.999.0.0)

# 资料:

b友分享

https://pan.baidu.com/s/1JxvXF8EyG9TSNLqkc98YzQ

提取码：i5qc

# 1.webpack初体验：

## 安装：



老师先全局安装了npm i webpack webpack-cli -g

然后又局部安装npm i webpack webpack-cli -D

推荐安装老师版本，我安装最新版本有很多错。

package.json如下：

```json
{
  "name": "webpack_test",
  "version": "1.0.0",
  "description": "测试",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "webpack": "^4.41.6",
    "webpack-cli": "^3.3.11"
  }
}
```



## 使用：

![image-20220323201858315](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323201858315.png)

```js
/*
  index.js: webpack入口起点文件

  1. 运行指令：
    开发环境：webpack ./src/index.js -o ./build/built.js --mode=development
      webpack会以 ./src/index.js 为入口文件开始打包，打包后输出到 ./build/built.js
      整体打包环境，是开发环境
    生产环境：webpack ./src/index.js -o ./build/built.js --mode=production
      webpack会以 ./src/index.js 为入口文件开始打包，打包后输出到 ./build/built.js
      整体打包环境，是生产环境
*/
// import './index.css';

import data from './data.json';
console.log(data);

function add(x, y) {
  return x + y;
}

console.log(add(1, 2));


```

开发环境：

![image-20220323200217175](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323200217175.png)

开发环境打包的build.js很长，里面的代码看不懂……

生产环境：

![image-20220323200506420](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323200506420.png)

生产环境打包的build.js把我们的代码进行了压缩

注意我们每次更新了代码，都需要重新打包。

## 测试：

用一个html引入打包好的built.js。

可以正确显示，但是不能显示css样式

![image-20220323202236532](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323202236532.png)

## 结论：

1. webpack能处理js/json资源，不能处理css/img等其他资源

2. 生产环境和开发环境将ES6模块化编译成浏览器能识别的模块化~

3. 生产环境比开发环境多一个压缩js代码。

   





# 2.webpack开发环境配置

## 2.1打包样式资源：

### webpack.config.js：

```js
/*
  webpack.config.js  webpack的配置文件
    作用: 指示 webpack 干哪些活（当你运行 webpack 指令时，会加载里面的配置）

    所有构建工具都是基于nodejs平台运行的~模块化默认采用commonjs。
*/

// resolve用来拼接绝对路径的方法
const { resolve } = require('path');

module.exports = {
  // webpack配置
  // 入口起点
  entry: './src/index.js',
  // 输出
  output: {
    // 输出文件名
    filename: 'built.js',
    // 输出路径
    // __dirname nodejs的变量，代表当前文件的目录绝对路径
    path: resolve(__dirname, 'build')
  },
  // loader的配置
  module: {
    rules: [
      // 详细loader配置
      // 不同文件必须配置不同loader处理
      {
          //第一组配置css文件
        // 匹配哪些文件
        test: /\.css$/,
        // 使用哪些loader进行处理
        use: [
          // use数组中loader执行顺序：从右到左，从下到上 依次执行.一定不要随意改变顺序！！！
          // 创建style标签，将js中的样式资源插入进行，添加到head中生效
          'style-loader',
          // 将css文件变成commonjs模块加载js中，里面内容是样式字符串
          'css-loader'
        ]
      },
      {
          //第二组配置less文件
        test: /\.less$/,
        use: [
          'style-loader',
          'css-loader',
          // 将less文件编译成css文件
          // 需要下载 less-loader和less
          'less-loader'
        ]
      }
    ]
  },
  // plugins的配置
  plugins: [
    // 详细plugins的配置
  ],
  // 模式
  mode: 'development', // 开发模式
  // mode: 'production'
}

```

![image-20220323212241438](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220323212241438.png)

### 需注意：

#### 1.css-loader和style-loader

这两个的顺序一定不要写反了，先有css-loader后有style-loader比较符合逻辑。所以style-loader写在前面，

css-loader写在后面，因为是从后往前执行的。

<div style="color: red">多个loader用use，一个用loader。</div>

#### 2.配置的npm包太多

我们在根目录下初始化npm，下载老师资料时，没注意到，只要package.json。注意根目录下npm i后再运行。

本节需要的几个包：css-loader，less-loader，style-loder

#### 3.webpack.config.js

直接运行webpack指令就行，里面有个nodejs path路径模块，我以前常用path.join()，注意path.resolve这个方法

传送门：

[path.join与path.resolve的区别你知道吗？ - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/250661603)

## 2.2打包html：

![image-20220324111954688](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324111954688.png)

### webpack.config.js：

```js
/*
  loader: 1. 下载   2. 使用（配置loader）
  plugins: 1. 下载  2. 引入  3. 使用
*/
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      // loader的配置
    ]
  },
  plugins: [
    // plugins的配置
    // html-webpack-plugin
    // 功能：默认会创建一个空的HTML，自动引入打包输出的所有资源（JS/CSS）
    // 需求：需要有结构的HTML文件
    new HtmlWebpackPlugin({
      // 复制 './src/index.html' 文件，并自动引入打包输出的所有资源（JS/CSS）
      template: './src/index.html'
    })
  ],
  mode: 'development'
};

```



### 生成的html：

相比于模板html多了行

```html
<script type="text/javascript" src="built.js"></script>
```

![image-20220324111608374](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324111608374.png)



### 需注意：

#### 1.打包html：

注意用的是插件，不是module

## 2.3打包图片：

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.less$/,
        // 要使用多个loader处理用use
        use: ['style-loader', 'css-loader', 'less-loader']
      },
      {
        // 问题：默认处理不了html中img图片
        // 处理图片资源
        test: /\.(jpg|png|gif)$/,
        // 使用一个loader
        // 下载 url-loader file-loader
        loader: 'url-loader',
        options: {
          // 图片大小小于8kb，就会被base64处理
          // 优点: 减少请求数量（减轻服务器压力）
          // 缺点：图片体积会更大（文件请求速度更慢）
          limit: 8 * 1024,
          // 问题：因为url-loader默认使用es6模块化解析，而html-loader引入图片是commonjs
          // 解析时会出问题：[object Module]
          // 解决：关闭url-loader的es6模块化，使用commonjs解析
          esModule: false,
          // 给图片进行重命名
          // [hash:10]取图片的hash的前10位
          // [ext]取文件原来扩展名
          name: '[hash:10].[ext]'
        }
      },
      {
        test: /\.html$/,
        // 处理html文件的img图片（负责引入img，从而能被url-loader进行处理）
        loader: 'html-loader'
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development'
};

```



![image-20220324115025064](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324115025064.png)

![image-20220324114821715](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324114821715.png)

### 需注意：

#### 1.新版写法

老师这些问题在新版本5中都有解决方案，不用写这么繁琐。

[webpack 中文文档 (docschina.org)](https://webpack.docschina.org/guides/asset-modules#root)

#### 2.rules

<div style="color: red">经测试rules数组里面的对象可以调换位置，但是对象里面的use不能随意调换loader顺序</div>

#### 3.不同位置的img

样式里面引入的图片，和html中的img标签的图片有不同的处理方式

#### 4.url-loader依赖file-loader



## 2.4打包其他资源：

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      },
      // 打包其他资源(除了html/js/css资源以外的资源)
      {
        // 排除css/js/html资源
        exclude: /\.(css|js|html|less)$/,
        loader: 'file-loader',
        options: {
          name: '[hash:10].[ext]'
        }
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development'
};

```

![image-20220324120432641](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324120432641.png)

index.js引入iconfont.css，iconfont.css引入了其他格式的iconfont

### 需注意：

#### 1.新版本

5版本不用loader:'file-loader'用type：'asset'"

#### 2.用排除法打包其他资源



## 2.5devServer：

### webpack.config.js：



```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      },
      // 打包其他资源(除了html/js/css资源以外的资源)
      {
        // 排除css/js/html资源
        exclude: /\.(css|js|html|less)$/,
        loader: 'file-loader',
        options: {
          name: '[hash:10].[ext]'
        }
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development',

  // 开发服务器 devServer：用来自动化（自动编译，自动打开浏览器，自动刷新浏览器~~）
  // 特点：只会在内存中编译打包，不会有任何输出
  // 启动devServer指令为：npx webpack-dev-server
  devServer: {
    // 项目构建后路径
    contentBase: resolve(__dirname, 'build'),
    // 启动gzip压缩
    compress: true,
    // 端口号
    port: 3000,
    // 自动打开浏览器
    open: true
  }
};

```



### 需注意：

#### 1.5+版本问题

新版本webpack指令是npx webpack server

报contentBase属性无效，解决：在webpack5中的contentBase那句改为：static: { directory: resolve(__dirname, "build"),}

或者直接注释掉用npx webpack server启动

#### 2.devServer

就是用于热更新的和nodemon差不多，webpack指令变为npx webpack-dev-server

#### 3.热更新

webpack5 需要添加 target: 'web' 配置

target:'web'跟mode同级,放在mode:'developmment'后面就行了



## 2.6总结：

### webpack.config.js：

```js
/*
  开发环境配置：能让代码运行
    运行项目指令：
      webpack 会将打包结果输出出去
      npx webpack-dev-server 只会在内存中编译打包，没有输出
*/

const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      // loader的配置
      {
        // 处理less资源
        test: /\.less$/,
        use: ['style-loader', 'css-loader', 'less-loader']
      },
      {
        // 处理css资源
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      },
      {
        // 处理图片资源
        test: /\.(jpg|png|gif)$/,
        loader: 'url-loader',
        options: {
          limit: 8 * 1024,
          name: '[hash:10].[ext]',
          // 关闭es6模块化
          esModule: false,
          outputPath: 'imgs'
        }
      },
      {
        // 处理html中img资源
        test: /\.html$/,
        loader: 'html-loader'
      },
      {
        // 处理其他资源
        exclude: /\.(html|js|css|less|jpg|png|gif)/,
        loader: 'file-loader',
        options: {
          name: '[hash:10].[ext]',
          outputPath: 'media'
        }
      }
    ]
  },
  plugins: [
    // plugins的配置
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development',
  devServer: {
    contentBase: resolve(__dirname, 'build'),
    compress: true,
    port: 3000,
    open: true
  }
};

```

![image-20220324123519374](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324123519374.png)

### 需注意：

#### 1.webpack和npx webpack-dev-server

webpack 会将打包结果输出出去。也就是说他会根据outputPath把你的那些资源创建出来，适合最终上线时使用。
npx webpack-dev-server 只会在内存中编译打包，没有输出。就是说不会像webpack指令那样创建出对应资源，

而在内存进行，适合测试时使用。

#### 2.outputPath

可以指定创建出来的资源路径

# 3.webpack生产环境配置

## 3.1提取css成单独文件：

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          // 创建style标签，将样式放入
          // 'style-loader', 
          // 这个loader取代style-loader。作用：提取js中的css成单独文件
          MiniCssExtractPlugin.loader,
          // 将css文件整合到js文件中
          'css-loader'
        ]
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    }),
    new MiniCssExtractPlugin({
      // 对输出的css文件进行重命名
      filename: 'css/built.css'
    })
  ],
  mode: 'development'
};

```

### 需注意：

#### 1.css

我们这个插件是吧css代码抽离出来合成一个新的css，不同于以前吧css写进built.js

![image-20220324163431164](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324163431164.png)

#### 2.插件

这个插件不用style-loader，有自己专属的loader



## 3.2css兼容性处理

我们都知道，一些css新属性有些浏览器不兼容，这个时候就需要添加前缀了。webpack打包时如何生成前缀呢？

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');

// 设置nodejs环境变量
// process.env.NODE_ENV = 'development';

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          MiniCssExtractPlugin.loader,
          'css-loader',
          /*
            css兼容性处理：postcss --> postcss-loader postcss-preset-env

            帮postcss找到package.json中browserslist里面的配置，通过配置加载指定的css兼容性样式

            "browserslist": {
              // 开发环境 --> 设置node环境变量：process.env.NODE_ENV = development
              "development": [
                "last 1 chrome version",
                "last 1 firefox version",
                "last 1 safari version"
              ],
              // 生产环境：默认是看生产环境
              "production": [
                ">0.2%",
                "not dead",
                "not op_mini all"
              ]
            }
          */
          // 使用loader的默认配置
          // 'postcss-loader',
          // 修改loader的配置
          {
            loader: 'postcss-loader',
            options: {
              ident: 'postcss',
              plugins: () => [
                // postcss的插件
                require('postcss-preset-env')()
              ]
            }
          }
        ]
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    }),
    new MiniCssExtractPlugin({
      filename: 'css/built.css'
    })
  ],
  mode: 'development'
};

```

对应的packjson的browserslist

```js
"browserslist": {
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ],
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ]
  },
```

![image-20220324180528639](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324180528639.png)



### 需注意：

#### 1.兼容问题

报错的是插件版本接口不支持，在最外层文件夹执行npm i postcss-loader@3.0.0 -D 安装固定版本插件就没有报错了

如果出现unknown property 'plugins'错误，说明你的版本比课件版本高太多了，具体配置详见postcss-loader文档，需要改很多地方

#### 2.browserslist

这个browserslist老师没有具体讲如何配置，说是让自己在github上搜搜看……

## 3.3压缩css

就是把css代码压缩成人类看不懂的样子，删空格换行注释啊这些。

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const OptimizeCssAssetsWebpackPlugin = require('optimize-css-assets-webpack-plugin')

// 设置nodejs环境变量
// process.env.NODE_ENV = 'development';

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          MiniCssExtractPlugin.loader,
          'css-loader',
          {
            loader: 'postcss-loader',
            options: {
              ident: 'postcss',
              plugins: () => [
                // postcss的插件
                require('postcss-preset-env')()
              ]
            }
          }
        ]
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    }),
    new MiniCssExtractPlugin({
      filename: 'css/built.css'
    }),
    // 压缩css
    new OptimizeCssAssetsWebpackPlugin()
  ],
  mode: 'development'
};

```

![image-20220324181527139](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324181527139.png)

### 需注意：

#### 1.有新插件

css-minimizer-webpack-plugin官网推荐

[CssMinimizerWebpackPlugin | webpack 中文文档 (docschina.org)](https://webpack.docschina.org/plugins/css-minimizer-webpack-plugin/#root)







## 3.4js语法检查



### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      /*
        语法检查： eslint-loader  eslint
          注意：只检查自己写的源代码，第三方的库是不用检查的
          设置检查规则：
            package.json中eslintConfig中设置~
              "eslintConfig": {
                "extends": "airbnb-base"
              }
            airbnb --> eslint-config-airbnb-base  eslint-plugin-import eslint
      */
      {
        test: /\.js$/,
        // 不检查node_modules，不然一片红……
        exclude: /node_modules/,
        loader: 'eslint-loader',
        options: {
          // 自动修复eslint的错误,不开就不修复
          fix: true
        }
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development'
};

```

相应的package.json

```js
"eslintConfig": {
    "extends": "airbnb-base",
    "env": {
      "browser": true
    }
  },
```



### 需注意：

#### 1.有新插件

webpack5 eslint-loader将很快被弃用，请改用此插件eslint-webpack-plugin

[EslintWebpackPlugin | webpack 中文文档 (docschina.org)](https://webpack.docschina.org/plugins/eslint-webpack-plugin/#root)

#### 2.评价

我的评价是不如格式化文档，以前就很烦eslint这个东西。



## 3.5js兼容性处理

把let，箭头函数啊这些东西转成es5规范的。但是高级点的比如promise这些就必须用其他包转换了

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      /*
        js兼容性处理：babel-loader @babel/core 
          1. 基本js兼容性处理 --> @babel/preset-env
            问题：只能转换基本语法，如promise高级语法不能转换
          2. 全部js兼容性处理 --> @babel/polyfill  
            问题：我只要解决部分兼容性问题，但是将所有兼容性代码全部引入，体积太大了~
          3. 需要做兼容性处理的就做：按需加载  --> core-js
      */  
      {
        test: /\.js$/,
        exclude: /node_modules/,
        loader: 'babel-loader',
        options: {
          // 预设：指示babel做怎么样的兼容性处理
          presets: [
            [
              '@babel/preset-env',
              {
                // 按需加载
                useBuiltIns: 'usage',
                // 指定core-js版本
                corejs: {
                  version: 3
                },
                // 指定兼容性做到哪个版本浏览器
                targets: {
                  chrome: '60',
                  firefox: '60',
                  ie: '9',
                  safari: '10',
                  edge: '17'
                }
              }
            ]
          ]
        }
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development'
};

```

### 需注意：

#### 1.正确搭配

建议core-js针对性兼容，搭配基本兼容使用。babel/polyfill 就不用了

#### 2.评价

IE21年6月15日将正式弃用，春天来了！但是还是了解下js兼容问题

## 3.6压缩js和html

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html',
      // 压缩html代码
      minify: {
        // 移除空格
        collapseWhitespace: true,
        // 移除注释
        removeComments: true
      }
    })
  ],
  // 生产环境下会自动压缩js代码
  mode: 'production'
};

```



### 需注意：

#### 1.压缩html

新版本直接调成production模式不经会自动压缩js，也可以压缩html，不用配置。

#### 2.html兼容性

这个没办法，不认识就是不认识

## 总结：

### webpack.config.js：

```js
const { resolve } = require('path');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const OptimizeCssAssetsWebpackPlugin = require('optimize-css-assets-webpack-plugin');
const HtmlWebpackPlugin = require('html-webpack-plugin');

// 定义nodejs环境变量：决定使用browserslist的哪个环境
process.env.NODE_ENV = 'production';

// 复用loader
const commonCssLoader = [
  MiniCssExtractPlugin.loader,
  'css-loader',
  {
    // 还需要在package.json中定义browserslist
    loader: 'postcss-loader',
    options: {
      ident: 'postcss',
      plugins: () => [require('postcss-preset-env')()]
    }
  }
];

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [...commonCssLoader]
      },
      {
        test: /\.less$/,
        use: [...commonCssLoader, 'less-loader']
      },
      /*
        正常来讲，一个文件只能被一个loader处理。
        当一个文件要被多个loader处理，那么一定要指定loader执行的先后顺序：
          先执行eslint 在执行babel
      */
      {
        // 在package.json中eslintConfig --> airbnb
        test: /\.js$/,
        exclude: /node_modules/,
        // 优先执行
        enforce: 'pre',
        loader: 'eslint-loader',
        options: {
          fix: true
        }
      },
      {
        test: /\.js$/,
        exclude: /node_modules/,
        loader: 'babel-loader',
        options: {
          presets: [
            [
              '@babel/preset-env',
              {
                useBuiltIns: 'usage',
                corejs: {version: 3},
                targets: {
                  chrome: '60',
                  firefox: '50'
                }
              }
            ]
          ]
        }
      },
      {
        test: /\.(jpg|png|gif)/,
        loader: 'url-loader',
        options: {
          limit: 8 * 1024,
          name: '[hash:10].[ext]',
          outputPath: 'imgs',
          esModule: false
        }
      },
      {
        test: /\.html$/,
        loader: 'html-loader'
      },
      {
        exclude: /\.(js|css|less|html|jpg|png|gif)/,
        loader: 'file-loader',
        options: {
          outputPath: 'media'
        }
      }
    ]
  },
  plugins: [
    new MiniCssExtractPlugin({
      filename: 'css/built.css'
    }),
    new OptimizeCssAssetsWebpackPlugin(),
    new HtmlWebpackPlugin({
      template: './src/index.html',
      minify: {
        collapseWhitespace: true,
        removeComments: true
      }
    })
  ],
  mode: 'production'
};

```

package.json

```js
"browserslist": {
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ],
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ]
  },
  "eslintConfig": {
    "extends": "airbnb-base",
    "env": {
      "browser": true
    }
  },


```



### 需注意：

#### 1.css兼容性

该配置文件可以兼容less，因为经less-loader处理，less转变为css。但需要注意书写顺序，而且由于兼容css和兼容less

有相同的配置模块，所以可以提取出去，用spread语法导入就行

#### 2.js语法检查和js兼容性

正常来讲，一个文件只能被一个loader处理。当一个文件要被多个loader处理，那么一定要指定loader执行的先后顺序：
先执行eslint 再执行babel是比较合适的。我们可以在rules里面优先执行eslint这条rule

```js
{
        // 在package.json中eslintConfig --> airbnb
        test: /\.js$/,
        exclude: /node_modules/,
        // 优先执行
        enforce: 'pre',
        loader: 'eslint-loader',
        options: {
          fix: true
        }
},
```

传送门：暂无解答。之前测过和test书写顺序无关

[(1) Webpack module rules ， rules 中有多个test的时候，是什么执行顺序，为什么呢？ - SegmentFault 思否](https://segmentfault.com/q/1010000041128317)

# 4.webpack优化环境配置

## 预览：

### webpack性能优化
* 开发环境性能优化
* 生产环境性能优化

### 开发环境性能优化

* 优化打包构建速度
  * HMR
* 优化代码调试
  * source-map

### 生产环境性能优化
* 优化打包构建速度
  * oneOf
  * babel缓存
  * 多进程打包
  * externals
  * dll
* 优化代码运行的性能
  * 缓存(hash-chunkhash-contenthash)
  * tree shaking
  * code split
  * 懒加载/预加载
  * pwa

## 4.1HMR

### webpack.config.js：

```js
/*
  HMR: hot module replacement 热模块替换 / 模块热替换
    作用：一个模块发生变化，只会重新打包这一个模块（而不是打包所有模块） 
      极大提升构建速度
      
      样式文件：可以使用HMR功能：因为style-loader内部实现了~
      js文件：默认不能使用HMR功能 --> 需要修改js代码，添加支持HMR功能的代码
        注意：HMR功能对js的处理，只能处理非入口js文件的其他文件。
      html文件: 默认不能使用HMR功能.同时会导致问题：html文件不能热更新了~ （不用做HMR功能）
        解决：修改entry入口，将html文件引入
*/

const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: ['./src/js/index.js', './src/index.html'],
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      // loader的配置
      {
        // 处理less资源
        test: /\.less$/,
        use: ['style-loader', 'css-loader', 'less-loader']
      },
      {
        // 处理css资源
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      },
      {
        // 处理图片资源
        test: /\.(jpg|png|gif)$/,
        loader: 'url-loader',
        options: {
          limit: 8 * 1024,
          name: '[hash:10].[ext]',
          // 关闭es6模块化
          esModule: false,
          outputPath: 'imgs'
        }
      },
      {
        // 处理html中img资源
        test: /\.html$/,
        loader: 'html-loader'
      },
      {
        // 处理其他资源
        exclude: /\.(html|js|css|less|jpg|png|gif)/,
        loader: 'file-loader',
        options: {
          name: '[hash:10].[ext]',
          outputPath: 'media'
        }
      }
    ]
  },
  plugins: [
    // plugins的配置
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development',
  devServer: {
    contentBase: resolve(__dirname, 'build'),
    compress: true,
    port: 3000,
    open: true,
    // 开启HMR功能
    // 当修改了webpack配置，新配置要想生效，必须重新webpack服务
    hot: true
  }
};

```

### index.js:

```js
// 引入
import print from './print';
import '../css/iconfont.css';
import '../css/index.less';

console.log('index.js文件被加载了~');

print();

function add(x, y) {
  return x + y;
}

console.log(add(1, 3));

if (module.hot) {
  // 一旦 module.hot 为true，说明开启了HMR功能。 --> 让HMR功能代码生效
  module.hot.accept('./print.js', function() {
    // 方法会监听 print.js 文件的变化，一旦发生变化，其他模块不会重新打包构建。
    // 会执行后面的回调函数
    print();
  });
}

```

### print.js:

```js
console.log('print.js被加载了~');

function print() {
  const content = 'hello print';
  console.log(content);
}

export default print;

```

修改prints代码：

![image-20220325135700964](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220325135700964.png)



### 需注意：

#### 1.新版本

新版本已经自动嵌入热更新功能

[webpack 中文文档 (docschina.org)](https://webpack.docschina.org/plugins/mini-css-extract-plugin#hot-module-reloading-hmr)

#### 2.css和html不需要HMR

详见注释

#### 3.此法只针对非入口js文件



## 4.2source-map

就是方便调试debug

### webpack.config.js：

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: ['./src/js/index.js', './src/index.html'],
  output: {
    filename: 'js/built.js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.less$/,
        use: ['style-loader', 'css-loader', 'less-loader']
      },
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      },
      {
        test: /\.(jpg|png|gif)$/,
        loader: 'url-loader',
        options: {
          limit: 8 * 1024,
          name: '[hash:10].[ext]',
          esModule: false,
          outputPath: 'imgs'
        }
      },
      {
        test: /\.html$/,
        loader: 'html-loader'
      },
      {
        exclude: /\.(html|js|css|less|jpg|png|gif)/,
        loader: 'file-loader',
        options: {
          name: '[hash:10].[ext]',
          outputPath: 'media'
        }
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html'
    })
  ],
  mode: 'development',
  devServer: {
    contentBase: resolve(__dirname, 'build'),
    compress: true,
    port: 3000,
    open: true,
    hot: true
  },
    //配置很少，内容很多
  devtool: 'eval-source-map'
};

/*
  source-map: 一种 提供源代码到构建后代码映射 技术 （如果构建后代码出错了，通过映射可以追踪源代码错误）

    [inline-|hidden-|eval-][nosources-][cheap-[module-]]source-map

    source-map：外部
      错误代码准确信息 和 源代码的错误位置
    inline-source-map：内联
      只生成一个内联source-map
      错误代码准确信息 和 源代码的错误位置
    hidden-source-map：外部
      错误代码错误原因，但是没有错误位置
      不能追踪源代码错误，只能提示到构建后代码的错误位置
    eval-source-map：内联
      每一个文件都生成对应的source-map，都在eval
      错误代码准确信息 和 源代码的错误位置
    nosources-source-map：外部
      错误代码准确信息, 但是没有任何源代码信息
    cheap-source-map：外部
      错误代码准确信息 和 源代码的错误位置 
      只能精确的行
    cheap-module-source-map：外部
      错误代码准确信息 和 源代码的错误位置 
      module会将loader的source map加入

    内联 和 外部的区别：1. 外部生成了文件，内联没有 2. 内联构建速度更快

    开发环境：速度快，调试更友好
      速度快(eval>inline>cheap>...)
        eval-cheap-souce-map
        eval-source-map
      调试更友好  
        souce-map
        cheap-module-souce-map
        cheap-souce-map

      --> eval-source-map  / eval-cheap-module-souce-map

    生产环境：源代码要不要隐藏? 调试要不要更友好
      内联会让代码体积变大，所以在生产环境不用内联
      nosources-source-map 全部隐藏
      hidden-source-map 只隐藏源代码，会提示构建后代码错误信息

      --> source-map / cheap-module-souce-map
*/

```



### 需注意：

#### 1.传送门

[深入浅出之 Source Map - 掘金 (juejin.cn)](https://juejin.cn/post/7023537118454480904)

阮老师教程好早啊

[JavaScript Source Map 详解 - 阮一峰的网络日志 (ruanyifeng.com)](https://www.ruanyifeng.com/blog/2013/01/javascript_source_map.html)



## 4.3oneof

### webpack.config.js：

![image-20220325160857432](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220325160857432.png)



### 需注意：

#### 1.传送门

官网：https://webpack.docschina.org/configuration/module#ruleoneof

[(1) webpack优化系列-oneOf - SegmentFault 思否](https://segmentfault.com/a/1190000022413668)

## 4.4缓存

### webpack.config.js：

```js
const { resolve } = require('path');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const OptimizeCssAssetsWebpackPlugin = require('optimize-css-assets-webpack-plugin');
const HtmlWebpackPlugin = require('html-webpack-plugin');

/*
  缓存：
    babel缓存
      cacheDirectory: true
      --> 让第二次打包构建速度更快
    文件资源缓存
      hash: 每次wepack构建时会生成一个唯一的hash值。
        问题: 因为js和css同时使用一个hash值。
          如果重新打包，会导致所有缓存失效。（可能我却只改动一个文件）
      chunkhash：根据chunk生成的hash值。如果打包来源于同一个chunk，那么hash值就一样
        问题: js和css的hash值还是一样的
          因为css是在js中被引入的，所以同属于一个chunk
      contenthash: 根据文件的内容生成hash值。不同文件hash值一定不一样。只要文件内容没变，hash值就不会变    
      --> 让代码上线运行缓存更好使用
*/

// 定义nodejs环境变量：决定使用browserslist的哪个环境
process.env.NODE_ENV = 'production';

// 复用loader
const commonCssLoader = [
  MiniCssExtractPlugin.loader,
  'css-loader',
  {
    // 还需要在package.json中定义browserslist
    loader: 'postcss-loader',
    options: {
      ident: 'postcss',
      plugins: () => [require('postcss-preset-env')()]
    }
  }
];

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.[contenthash:10].js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        // 在package.json中eslintConfig --> airbnb
        test: /\.js$/,
        exclude: /node_modules/,
        // 优先执行
        enforce: 'pre',
        loader: 'eslint-loader',
        options: {
          fix: true
        }
      },
      {
        // 以下loader只会匹配一个
        // 注意：不能有两个配置处理同一种类型文件
        oneOf: [
          {
            test: /\.css$/,
            use: [...commonCssLoader]
          },
          {
            test: /\.less$/,
            use: [...commonCssLoader, 'less-loader']
          },
          /*
            正常来讲，一个文件只能被一个loader处理。
            当一个文件要被多个loader处理，那么一定要指定loader执行的先后顺序：
              先执行eslint 在执行babel
          */
          {
            test: /\.js$/,
            exclude: /node_modules/,
            loader: 'babel-loader',
            options: {
              presets: [
                [
                  '@babel/preset-env',
                  {
                    useBuiltIns: 'usage',
                    corejs: { version: 3 },
                    targets: {
                      chrome: '60',
                      firefox: '50'
                    }
                  }
                ]
              ],
              // 开启babel缓存
              // 第二次构建时，会读取之前的缓存
              cacheDirectory: true
            }
          },
          {
            test: /\.(jpg|png|gif)/,
            loader: 'url-loader',
            options: {
              limit: 8 * 1024,
              name: '[hash:10].[ext]',
              outputPath: 'imgs',
              esModule: false
            }
          },
          {
            test: /\.html$/,
            loader: 'html-loader'
          },
          {
            exclude: /\.(js|css|less|html|jpg|png|gif)/,
            loader: 'file-loader',
            options: {
              outputPath: 'media'
            }
          }
        ]
      }
    ]
  },
  plugins: [
    new MiniCssExtractPlugin({
      filename: 'css/built.[contenthash:10].css'
    }),
    new OptimizeCssAssetsWebpackPlugin(),
    new HtmlWebpackPlugin({
      template: './src/index.html',
      minify: {
        collapseWhitespace: true,
        removeComments: true
      }
    })
  ],
  mode: 'production',
  devtool: 'source-map'
};

```

### 需注意：

#### 1.使用

我们在创建资源文件后缀前添加hash值就行

这个和之前给图片打包，重命名图片很像

```js
output: {
    filename: 'js/built.[contenthash:10].js',
    path: resolve(__dirname, 'build')
  },
```

```js
new MiniCssExtractPlugin({
      filename: 'css/built.[contenthash:10].css'
    }),
```

#### 2.注意3个hash之间的区别

详见注释

传送门：

[webpack中的hash、chunkhash、contenthash分别是什么 - 掘金 (juejin.cn)](https://juejin.cn/post/6844903935812059144)

## 4.5tree shaking

树摇：在应用程序中去除没有使用的代码(就是那些灰色的，定义了但是没有使用的,还有那些不可达的代码)，使代码的体积更小

```js
/*
  tree shaking：去除无用代码
    前提：1. 必须使用ES6模块化  2. 开启production环境
    作用: 减少代码体积

    在package.json中配置 
      "sideEffects": false 所有代码都没有副作用（都可以进行tree shaking）
        问题：可能会把css / @babel/polyfill （副作用）文件干掉
        解决方案：
      "sideEffects": ["*.css", "*.less"]
*/
```



### 需注意：

#### 1.在package.json里配置！

#### 2.传送门

就是依赖于ES6静态模块

通俗：

[带你深度理解到底什么是Tree-sharking（一） - 掘金 (juejin.cn)](https://juejin.cn/post/6936867649729069086)

深入：

[Webpack 原理系列九：Tree-Shaking 实现原理 - 掘金 (juejin.cn)](https://juejin.cn/post/7002410645316436004#comment)

官方：

[Tree Shaking | webpack 中文文档 (docschina.org)](https://webpack.docschina.org/guides/tree-shaking/)

## 4.6code split

代码分割：就是说我们打包后不是生成一个bundle(built.js)嘛，我们想让它分割成几个js。这样做有很多好处，

比如可以按需加载，而不是加载包含所有内容的单个包。比如还可以并行运行多个js。

### demo1：

entry里面配一个入口，就生成一个bundle文件

配两个入口，就生成两个bundle文件(output里面配置输出文件名)

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  // 单入口
  // entry: './src/js/index.js',
  entry: {
    // 多入口：最终输出两个个bundle
    index: './src/js/index.js',
    test: './src/js/test.js'
  },
  output: {
    // [name]：取文件名
    filename: 'js/[name].[contenthash:10].js',
    path: resolve(__dirname, 'build')
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html',
      minify: {
        collapseWhitespace: true,
        removeComments: true
      }
    })
  ],
  mode: 'production'
};

```

### demo2：

单入口文件+配置optimization:将node_modules中代码单独打包一个chunk最终输出

多入口文件+配置optimization：自动分析多入口chunk中，有没有公共的文件。如果有会打包成单独一个chunk

(这里公共文件有限制的，太小就不单独打包了)

```js
const { resolve } = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  // 单入口
  // entry: './src/js/index.js',
  entry: {
    index: './src/js/index.js',
    test: './src/js/test.js'
  },
  output: {
    // [name]：取文件名
    filename: 'js/[name].[contenthash:10].js',
    path: resolve(__dirname, 'build')
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html',
      minify: {
        collapseWhitespace: true,
        removeComments: true
      }
    })
  ],
  /*
  	单入口情况下
    1. 可以将node_modules中代码单独打包一个chunk最终输出
    在多入口的情况下：
    2. 自动分析多入口chunk中，有没有公共的文件。如果有会打包成单独一个chunk
    (只有大于30kb的时候才会分割，不然无效)
  */
  optimization: {
    splitChunks: {
      chunks: 'all'
    }
  },
  mode: 'production'
};

  
```

大一点的项目一般就用cdn了，但是项目如果部署在内网的话也用不了cdn，就可以用这种方案了

### demo3：

单入口+配置optimization：将node_modules中代码单独打包一个chunk最终输出(demo2的第一种情况)

我们如果想在此基础上单独打包我们写的代码，需要在想额外打包的代码里面添加一些动态import

index.js:(单入口文件)

```js
function sum(...args) {
  return args.reduce((p, c) => p + c, 0);
}

/*
  通过js代码，让某个文件被单独打包成一个chunk
  import动态导入语法：能将某个文件单独打包   ES10支持
*/
import(/* webpackChunkName: 'test' */'./test')
  .then(({ mul, count }) => {
    // 文件加载成功~
    // eslint-disable-next-line
    console.log(mul(2, 5));
  })
  .catch(() => {
    // eslint-disable-next-line
    console.log('文件加载失败~');
  });

// eslint-disable-next-line
console.log(sum(1, 2, 3, 4));

```

test.js:（想单独打包的代码）

```js

export function mul(x, y) {
  return x * y;
}

export function count(x, y) {
  return x - y;
}

```

这个注释在vue路由懒加载里面也有用到，都叫他魔法注释

[路由懒加载 | Vue Router (vuejs.org)](https://router.vuejs.org/zh/guide/advanced/lazy-loading.html#把组件按组分块)

传送门：

[Webpack实战（八）：教你搞懂webpack如果实现代码分片（code splitting） - 掘金 (juejin.cn)](https://juejin.cn/post/6844904053735063565#heading-2)



## 4.7懒加载和预加载

预加载简单来说就是将所有所需的资源提前请求加载到本地，这样后面在需要用到时就直接从缓存取资源。

懒加载使用动态引入即可解决，预加载再配置一个webpackPrefetch: true就行

index.js:（入口）

```js
console.log('index.js文件被加载了~');

// import { mul } from './test';

document.getElementById('btn').onclick = function() {
  // 懒加载~：当文件需要使用时才加载~
  // 预加载 prefetch：会在使用之前，提前加载js文件 
  // 正常加载可以认为是并行加载（同一时间加载多个文件）  
  // 预加载 prefetch：等其他资源加载完毕，浏览器空闲了，再偷偷加载资源
  import(/* webpackChunkName: 'test', webpackPrefetch: true */'./test').then(({ mul }) => {
    console.log(mul(4, 5));
  });
};

```

### 传送门：

官网

[懒加载 | webpack 中文文档 (docschina.org)](https://webpack.docschina.org/guides/lazy-loading/)

## 4.8PWA

就是让你没有网也能浏览一些内容

### webpack.config.js：

```js
const { resolve } = require('path');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const OptimizeCssAssetsWebpackPlugin = require('optimize-css-assets-webpack-plugin');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const WorkboxWebpackPlugin = require('workbox-webpack-plugin');

/*
  PWA: 渐进式网络开发应用程序(离线可访问)
    workbox --> workbox-webpack-plugin
*/

// 定义nodejs环境变量：决定使用browserslist的哪个环境
process.env.NODE_ENV = 'production';

// 复用loader
const commonCssLoader = [
  MiniCssExtractPlugin.loader,
  'css-loader',
  {
    // 还需要在package.json中定义browserslist
    loader: 'postcss-loader',
    options: {
      ident: 'postcss',
      plugins: () => [require('postcss-preset-env')()]
    }
  }
];

module.exports = {
  entry: './src/js/index.js',
  output: {
    filename: 'js/built.[contenthash:10].js',
    path: resolve(__dirname, 'build')
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        // 优先执行
        enforce: 'pre',
        loader: 'eslint-loader',
        options: {
          fix: true
        }
      },
      {
        oneOf: [
          {
            test: /\.css$/,
            use: [...commonCssLoader]
          },
          {
            test: /\.less$/,
            use: [...commonCssLoader, 'less-loader']
          },
          {
            test: /\.js$/,
            exclude: /node_modules/,
            loader: 'babel-loader',
            options: {
              presets: [
                [
                  '@babel/preset-env',
                  {
                    useBuiltIns: 'usage',
                    corejs: { version: 3 },
                    targets: {
                      chrome: '60',
                      firefox: '50'
                    }
                  }
                ]
              ],
              cacheDirectory: true
            }
          },
          {
            test: /\.(jpg|png|gif)/,
            loader: 'url-loader',
            options: {
              limit: 8 * 1024,
              name: '[hash:10].[ext]',
              outputPath: 'imgs',
              esModule: false
            }
          },
          {
            test: /\.html$/,
            loader: 'html-loader'
          },
          {
            exclude: /\.(js|css|less|html|jpg|png|gif)/,
            loader: 'file-loader',
            options: {
              outputPath: 'media'
            }
          }
        ]
      }
    ]
  },
  plugins: [
    new MiniCssExtractPlugin({
      filename: 'css/built.[contenthash:10].css'
    }),
    new OptimizeCssAssetsWebpackPlugin(),
    new HtmlWebpackPlugin({
      template: './src/index.html',
      minify: {
        collapseWhitespace: true,
        removeComments: true
      }
    }),
    new WorkboxWebpackPlugin.GenerateSW({
      /*
        1. 帮助serviceworker快速启动
        2. 删除旧的 serviceworker

        生成一个 serviceworker 配置文件~
      */
      clientsClaim: true,
      skipWaiting: true
    })
  ],
  mode: 'production',
  devtool: 'source-map'
};

```

index.js

```js
import { mul } from './test';
import '../css/index.css';

function sum(...args) {
  return args.reduce((p, c) => p + c, 0);
}

// eslint-disable-next-line
console.log(mul(2, 3));
// eslint-disable-next-line
console.log(sum(1, 2, 3, 4));

/*
  1. eslint不认识 window、navigator全局变量
  如果使用eslint需要改配置
    解决：需要修改package.json中eslintConfig配置
      "env": {
        "browser": true // 支持浏览器端全局变量
      }
   2. sw代码必须运行在服务器上
      --> nodejs
      -->
        npm i serve -g
        serve -s build 启动服务器，将build目录下所有资源作为静态资源暴露出去
*/
// 注册serviceWorker
// 处理兼容性问题
if ('serviceWorker' in navigator) {
  window.addEventListener('load', () => {
    navigator.serviceWorker
      .register('/service-worker.js')
      .then(() => {
        console.log('sw注册成功了~');
      })
      .catch(() => {
        console.log('sw注册失败了~');
      });
  });
}

```

![image-20220327152408269](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327152408269.png)

### 需注意：

#### 1.serve

npm i serve -g

serve -s build 启动服务器，将build目录下所有资源作为静态资源暴露出去

其实用vscode 插件live server也可以达到类似效果。但我测试servicework时，只有前者成功了

#### 2.传送门：

官网

[渐进式网络应用程序 | webpack 中文文档 (docschina.org)](https://webpack.docschina.org/guides/progressive-web-application/#registering-our-service-worker)

了解下：

好像国内PWA不如小程序火呢

[面试官：请你实现一个PWA 我：😭 - 掘金 (juejin.cn)](https://juejin.cn/post/6844904052166230030)
