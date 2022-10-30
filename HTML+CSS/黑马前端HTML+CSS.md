# 源码：

https://gitee.com/xiaoqiang001/html_css_material.git

# 视频：

[黑马程序员pink老师前端入门教程，零基础必看的h5(html5)+css3+移动端前端视频教程_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV14J4114768?p=1)

# 疑问：

## 1.Grid

Grid布局：(这部分pink老师没讲，看阮老师的博客)

[CSS Grid 网格布局教程 - 阮一峰的网络日志 (ruanyifeng.com)](https://www.ruanyifeng.com/blog/2019/03/grid-layout-tutorial.html)

## 2.BFC？

## 3.第九天第10条

## 4.字体图标

## 5.3D导航栏

## 6.旋转木马

# 需要注意的地方：

## 1.px ex em % rem这些单位区别

## 2.rgba(0, 0, 0, .3)，red,#fff等颜色的写法注意事项

## 3.浏览器设置67%页面大小好切图。（本机显示屏1920*1200）

传送门：

[(27条消息) “截图尺寸和浏览器CSS像素设置不一样”解决方法_雾里看花花里看雾的博客-CSDN博客_网页截图像素与实际像素不一致](https://blog.csdn.net/qq_43779149/article/details/108508493)

因为我的系统缩放设置的是150%，所以会有这个问题。调整浏览器缩放为67%即可

## 5.多行文本溢出显示省略号后台怎么实现呢？见高阶技巧第6点

## 6.案例两面旋转的盒子,为什么一进来会有闪烁？

## 7.一般手机上的网址，在前面加个m就行

京东的例子

[多快好省，购物上京东！ (jd.com)](https://m.jd.com/)

[京东(JD.COM)-正品低价、品质保障、配送及时、轻松购物！](https://www.jd.com/)

## 8.vscode使用easyLess插件，算术时必须加上()

详见

[(24条消息) 解决VScode安装Easy less之后，计算式子不显示结果的问题_BreezeChasingDrizzle的博客-CSDN博客](https://blog.csdn.net/weixin_44032178/article/details/113626421)

## 9.关于苏宁首页banner和ad部分的一个bug(已解决)

bug:只能显示ad部分的一个gif

解决方案：我使用的浏览器安装了一个拦截广告的插件，把我们的图片拦截了，关闭插件即可

详见[(24条消息) 记录一个关于广告拦截器带来的坑 - “Failed to load resource: net::ERR_BLOCKED_BY_CLIENT”_默默的菜鸟--的博客-CSDN博客](https://blog.csdn.net/qq_34160679/article/details/86493847)

## 10.开发者模式下，手机端F12怎么拖动啊？

# PS操作： 

## 1.缩放固定图片比例    

Alt+Ctrl+I

用于多倍精灵图

## 2.显示参考线，矩阵大小等信息

F8

## 3.点击视图里面可以清除参考线

# HTML，CSS基础干货：

## 1.单行文字垂直居中

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>单行文字垂直居中</title>
    <style>
        /* 
            让文字的行高等于盒子的宽度即可实现垂直居中
            即让height=line-height
        */
        div {
            width: 200px;
            height: 40px;
            background-color: pink;
            line-height: 40px;
        }
    </style>
</head>

<body>
    <div>我要居中</div>
</body>

</html>
```

​               原理：        https://www.bilibili.com/video/BV14J4114768?p=114  2:20秒

![image-20221027150304915](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027150304915.png)

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/60.png)

![image-20221027150710418](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027150710418.png)

## 2.五彩导航栏案例:

![image-20220307230226417](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220307230226417.png)

```JS
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>综合案例-五彩导航</title>
    <style>
        .nav a {
            display: inline-block;
            width: 120px;
            height: 58px;
            background-color: pink;
            text-align: center;
            line-height: 48px;
            color: #fff;
            text-decoration: none;
        }

        .nav .bg1 {
            background: url(images/bg1.png) no-repeat;
        }

        .nav .bg1:hover {
            background-image: url(images/bg11.png);
        }

        .nav .bg2 {
            background: url(images/bg2.png) no-repeat;
        }

        .nav .bg2:hover {
            background-image: url(images/bg22.png);
        }
    </style>
</head>

<body>
    <div class="nav">
        <a href="#" class="bg1">五彩导航</a>
        <a href="#" class="bg2">五彩导航</a>
        <a href="#">五彩导航</a>
        <a href="#">五彩导航</a>
        <a href="#">五彩导航</a>
    </div>
</body>

</html>
```



## 3.字体复合属性

![image-20220307232741424](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220307232741424.png)

### 行高写法

见第7点小点行高的继承

### 字体样式

font-family如果有多个，优先适配第一个，没有就找下一个，以此类推

![image-20221027132246719](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027132246719.png)

## 4.背景复合写法

![image-20220307232843267](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220307232843267.png)



<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027152644428.png" style="zoom:50%;" />

固定背景图

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027152851444.png" style="zoom:50%;" />

透明背景

```css
div {
            width: 300px;
            height: 300px;
            /* background-color: black; */
            /* background: rgba(0, 0, 0, 0.3); */
            /* RGB分别为3原色，都为0那么颜色为黑，最后一个是alpha通道。1就是不透明度为100% */
            background: rgba(0, 0, 0, .3);
        }
```



## 5.复合选择器



![image-20220309130455989](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309130455989.png)

伪类选择器优先级：10

### 链接伪类选择器

```html
 <style>
        /* 1.未访问的链接 a:link  把没有点击过的(访问过的)链接选出来 */
        a:link {
            color: #333;
            text-decoration: none;
        }

        /*2. a:visited 选择点击过的(访问过的)链接 */
        a:visited {
            color: orange;
        }

        /*3. a:hover 选择鼠标经过的那个链接 */
        a:hover {
            color: skyblue;
        }

        /* 4. a:active 选择的是我们鼠标正在按下还没有弹起鼠标的那个链接 */
        a:active {
            color: green;
        }
        /* 
            1.为了确保生效，请按照LVHA的循顺序声明：link-:visited -:hover-:active。
            2.记忆法：love hate 或者 lv 包包hao。  
         */
    </style>
```



### :focus选择器

![image-20221027142342388](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027142342388.png)

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/293.gif)

## 6.块，行内，行内块元素

传送门：[一次性搞懂行内元素和块级元素的区别 - 掘金 (juejin.cn)](https://juejin.cn/post/6964644611822190622)

### 块元素：

![image-20220309130630409](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309130630409.png)

### 行内元素：

**伪元素属于行内元素**

![image-20220309130657961](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309130657961.png)

### 行内块元素：

<a href="#juedui">锚点：绝对定位和固定定位的特殊属性</a>

![image-20220309130726554](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309130726554.png)

### 总结：

![image-20220309130545944](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309130545944.png)

## 7.层叠性和继承性

### 层叠性

![image-20221027162940092](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027162940092.png)

### 继承性

![image-20221027163048916](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027163048916.png)

### 行高的继承

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>行高的继承</title>
    <style>
        body {
            color: pink;
            /* font: 12px/24px 'Microsoft YaHei'; */
            font: 12px/1.5 'Microsoft YaHei';
        }
        div {
            /* 子元素继承了父元素 body 的行高 1.5 */
            /* 这个1.5 就是当前元素文字大小 font-size 的1.5倍   所以当前div 的行高就是21像素 */
            font-size: 14px; 
        }
        p {
            /* 1.5 * 16 =  24 当前的行高 */
            font-size: 16px;
        }
        /* li 么有手动指定文字大小  则会继承父亲的 文字大小  body 12px 所以 li 的文字大小为 12px 
        
        当前li 的行高就是  12 * 1.5  =  18
        */
    </style>
</head>
<body>
    <div>粉红色的回忆</div>
    <p>粉红色的回忆</p>
    <ul>
        <li>我没有指定文字大小</li>
    </ul>
</body>
</html>
```

## 8.优先级和样式表位置

### 样式表位置

![image-20221027160710121](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027160710121.png)

[(27条消息) CSS三种样式表（内部样式表、行内样式表、 外部样式表）_hello_dashen的博客-CSDN博客_行内样式](https://blog.csdn.net/weixin_42235173/article/details/91040811)

### 权重

-  权重是有4组数字组成,但是**不会有进位**。 

- 可以理解为类选择器永远大于元素选择器, id选择器永远大于类选择器,以此类推.. 
-  等级判断从左向右，如果某一位数值相同，则判断下一位数值。 
- 可以简单记忆法:  通配符和继承权重为0, 标签选择器为1,类(伪类)选择器为 10, id选择器 100, 行内样式表为 1000, !important 无穷大. 
- **继承的权重是0， 如果该元素没有直接选中，不管父元素权重多高，子元素得到的权重都是 0。** 

下图pink>purple>green>red

**!important>行内样式>id选择器>class选择器**

![image-20220307233817276](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220307233817276.png)

### 继承



![image-20220307234331191](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220307234331191.png)



### 权重叠加:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>权重的叠加</title>
    <style>
       /* 复合选择器会有权重叠加的问题 */
       /* 权重虽然会叠加,但是永远不会有进位 */
       /* ul li 权重  0,0,0,1 + 0,0,0,1  =  0,0,0,2     2 */
        ul li {
            color: green;
        }
        /* li 的权重是 0,0,0,1    1 */
        li {
            color: red;
        }
        /* .nav li  权重    0,0,1,0  +  0,0,0,1  =  0,0,1,1    11 */
        .nav li {
            color: pink;
        }
    </style>
</head>
<body>
    <ul class="nav">
        <li>大猪蹄子</li>
        <li>大肘子</li>
        <li>猪尾巴</li>
    </ul>
</body>
</html>
```

## 9.盒子模型

![image-20220307235829783](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220307235829783.png)

### border：

![image-20221027162617400](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027162617400.png)

#### 边框样式

![image-20221027162650899](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027162650899.png)

#### 边框复合写法

![image-20221027162747186](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027162747186.png)

#### 边框影响盒子大小

<span style="color: red">边框会影响盒子实际大小！</span>

```html
<style>
        /* 我们需要一个200*200的盒子, 但是这个盒子有10像素的红色边框 */
        div {
            width: 180px;
            height: 180px;
            background-color: pink;
            border: 10px solid red;
        }
    </style>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027163639413.png" alt="image-20221027163639413" style="zoom:50%;" />

### padding:

#### 概念

<span style="color: red">padding是在盒子里面的！表示内容到边框的距离。也会影响盒子大小</span>

<img src="C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221027164000783.png" alt="image-20221027164000783" style="zoom:50%;" />

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027164135821.png" alt="image-20221027164135821" style="zoom:50%;" />

#### 写法

边框，padding,margin都是这样的

![image-20220308104131221](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220308104131221.png)

也有带方向的

```css
		   padding-left: 5px;
            padding-top: 5px;
            padding-bottom: 5px;
            padding-right: 5px;
```



#### padding应用-新浪导航

可以练练

![image-20220308105003129](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220308105003129.png)

#### padding不撑开盒子的情况

<span style="color: red">如果盒子本身没有指定宽度或高度，则此时padding不会撑大盒子。</span>

##### 案例1:

```css
 h1 {
        /* 如果写上宽度，那么h1会比body宽60px。不写宽度就没事，padding只会撑开高度 */
           width: 100%;
           height: 200px;
           background-color: pink;
           /* 这里只改变高度，没有撑开宽度 */
           padding: 30px;
       }
```

下图我写了宽度，可以看到h1宽度>body宽度，多了60px，也就是padding值*2

比body宽度大，自然也就会出现横向滚轮

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/294.gif" style="zoom:50%;" />

##### 案例2：

位置关系是div包住p，两个都是块元素。

下图最开始把p的高度去掉，可以看到p的高度就是60px（2个padding）,也就是蓝色部分，这个时候还可以看见div的紫色

但是一旦把p的高度填上去，瞬间就是100+60了。padding撑开了盒子高度，完全看不见div的紫色了，只有p的蓝色



![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/295.gif)

### margin:

margin代表盒子与盒子之间的距离。已经在边框外面了。实际上是不属于盒子的一部分

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027180004024.png" alt="image-20221027180004024" style="zoom:50%;" />

#### 	margin应用：让块级盒子居中

![image-20220308111844028](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220308111844028.png)

auto:让浏览器自己选择一个合适的外边距。有时，在一些特殊情况下，该值可以使元素居中。

传送门：[margin: auto 的魔法世界 - 掘金 (juejin.cn)](https://juejin.cn/post/6913857621850062856#comment)

行内元素或者行内块元素水平居中给其父元素添加 text-align:center 即可,像下边这样

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>行内元素/行内块元素水平居中对齐</title>
    <style>
      .header {
          width: 900px;
          height: 200px;
          background-color: pink;
          margin: 100px auto;
          text-align: center;
      }
      /* 行内元素或者行内块元素水平居中给其父元素添加 text-align:center 即可 */
    </style>
</head>
<body>
    <div class="header">
        <span>里面的文字</span>
    </div>
    <div class="header">
        <img src="down.jpg" alt="">
    </div>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027181304984.png" alt="image-20221027181304984" style="zoom:50%;" />

#### 外边距合并问题：

两个兄弟元素实际上相隔200px，不是300px。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>外边距合并-相邻块级元素垂直外边距合并</title>
    <style>
        .damao, .ermao {
            width: 200px;
            height: 200px;
            background-color: pink;
        }
        .damao {
            margin-bottom: 100px;
        }
        .ermao {
            margin-top: 200px;
        }
    </style>
</head>
<body>
    <div class="damao">大毛</div>
    <div class="ermao">二毛</div>
</body>
</html>
```

![image-20220308120235821](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220308120235821.png)

#### 解决塌陷问题

问题描述：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .father{
            height: 400px;
            width: 400px;
            background-color: pink;
            margin-top: 50px;
        }
        .son{
            height: 200px;
            width: 200px;
            background-color: purple;
            /* margin-top: 100px; */
        }
    </style>
</head>

<body>
    <div class="father">
        <div class="son"></div>
    </div>
</body>

</html>
```

![image-20220308113721645](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220308113721645.png)

![image-20221027184141141](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027184141141.png)

解决办法:

<center class="half">
    <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220308114001717.png" width="300"/>
    <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220308114132193.png" width="300"/>
</center>
常用第三种方法

这个其实就是BFC的应用之一喔

### 综合案例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>综合案例-产品模块</title>
    <style>
      * {
          margin: 0;
          padding: 0;
      }
      body {
          background-color: #f5f5f5;
      }
      a {
          color: #333;
          text-decoration: none;
      }
      .box {
          width: 298px;
          height: 415px;
          background-color:#fff;
          /* 让块级的盒子水平居中对齐 */
          margin: 100px auto;
      }
      .box img {
          /* 图片的宽度和父亲一样宽 */
          width: 100%;
      }
      .review {
          height: 70px;
          font-size: 14px;
          /* 因为这个段落没有 width属性 所有 padding不会撑开盒子的宽度 */
          padding: 0 28px;
          margin-top: 30px;
      }
      .appraise {
          font-size: 12px;
          color: #b0b0b0;
          margin-top: 20px;
          padding: 0 28px;
      }
      .info {
          font-size: 14px;
          margin-top: 15px;
          padding: 0 28px;
      }
      .info h4 {
          display: inline-block;
          font-weight: 400;
        
      }
      .info span {
          color: #ff6700;    
      }
      .info em {
          /*不让文字倾斜*/
          font-style: normal;
          color: #ebe4e0;
          margin: 0 6px 0 15px;
      }
    </style>
</head>
<body>
    <div class="box">
        <img src="images/img.jpg" alt="">
        <p class="review">快递牛，整体不错蓝牙可以说秒连。红米给力</p>
        <div class="appraise">来自于 117384232 的评价</div>
        <div class="info">
               <h4> <a href="#">Redmi AirDots真无线蓝...</a></h4>
               <em>|</em>
               <span> 99.9元</span>
        </div>
    </div>
</body>
</html>
```

效果：

![image-20220309223701570](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309223701570.png)

## 10.圆框

**border-radius**就是这些圆的半径大小

所以border-radius不能超过矩形较短一条边的一半

![image-20220423192414911](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220423192414911.png)

![image-20220309132205208](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309132205208.png)

案例：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>圆角边框常用写法</title>
    <style>
        /* 必须是正方形才行 */
        .yuanxing {
            width: 200px;
            height: 200px;
            background-color: pink;
            /* border-radius: 100px; */
            /* 50% 就是宽度和高度的一半  等价于 100px */
            border-radius: 50%;
        }

        .juxing {
            width: 300px;
            height: 100px;
            background-color: pink;
            /* 圆角矩形设置为高度的一半 */
            border-radius: 50px;
        }
        /* 这种不是很常用 */
        .radius {
            width: 200px;
            height: 200px;
            /* border-radius: 10px 20px 30px 40px; */
            /* border-radius: 10px 40px; */
            border-top-left-radius: 20px;
            background-color: pink;
        }
    </style>
</head>

<body>
    1. 圆形的做法:
    <div class="yuanxing"></div>
    2. 圆角矩形的做法:
    <div class="juxing"></div>
    3. 可以设置不同的圆角:
    <div class="radius"></div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027195804795.png" alt="image-20221027195804795" style="zoom:50%;" />

## 11.盒子阴影

![image-20220309133011308](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309133011308.png)

这个写好前两个属性，然后在浏览器上调就行

案例：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>盒子阴影</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            margin: 100px auto;

            /* box-shadow: 10px 10px; */
        }

        div:hover {
            box-shadow: 10px 10px 10px -4px rgba(0, 0, 0, .3);
        }

        /* 原先盒子没有影子,当我们鼠标经过盒子就添加阴影效果 */
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

![image-20220309133446616](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309133446616.png)

类似的还有文字阴影，但用的比较少

![image-20220309133708683](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309133708683.png)

## 12.浮动

### 标准流

![image-20221027201102077](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027201102077.png)

**网页布局第一准则：多个块级元素纵向排列找标准流，多个块级元素横向排列找浮动。** 

### 特性1：

![image-20220312125027003](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312125027003.png)

案例：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>浮动特性1</title>
    <style>
        /* 设置了浮动（float）的元素会：
        1. 脱离标准普通流的控制（浮）移动到指定位置（动）。
        2.浮动的盒子不在保留原先的位置 */
        .box1 {
            float: left;
            width: 200px;
            height: 200px;
            background-color: pink;
        }

        .box2 {
            width: 300px;
            height: 300px;
            background-color: rgb(0, 153, 255);
        }
    </style>
</head>

<body>
    <div class="box1">浮动的盒子</div>
    <div class="box2">标准流的盒子</div>
</body>

</html>
```

效果：这个就是脱标

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309135124793.png" alt="image-20220309135124793" style="zoom:50%;" />



<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027201345590.png" alt="image-20221027201345590" style="zoom:50%;" />

### 特性2：

![image-20220309135535675](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309135535675.png)

![image-20220312125235456](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312125235456.png)

### 特性3：

![image-20220309140203587](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309140203587.png)

案例：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>浮动的元素具有行内块元素特点</title>
    <style>
        /* 任何元素都可以浮动。不管原先是什么模式的元素，添加浮动之后具有行内块元素相似的特性。 */
        span,
        div {
            float: left;
            width: 200px;
            height: 100px;
            background-color: pink;
        }

        /* 如果行内元素有了浮动,则不需要转换块级\行内块元素就可以直接给高度和宽度 */
        a {
            float: right;
            height: 200px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <span>1</span>
    <span>2</span>

    <div>div</div>
    <a>ppppppp</a>
</body>

</html>
```

![image-20220309140313266](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309140313266.png)

### 常用策略：

**浮动元素经常和标准流父级搭配使用**

![image-20220309140558755](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309140558755.png)

案例：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>浮动元素搭配标准流父盒子1</title>
    <style>
        
        .box {
            width: 1200px;
            height: 460px;
            background-color: pink;
            margin: 0 auto;
        }
		/*左右浮动盒子大小，高度和父盒子一样，宽度相加和父亲一样*/
        .left {
            float: left;
            width: 230px;
            height: 460px;
            background-color: purple;
        }

        .right {
            float: left;
            width: 970px;
            height: 460px;
            background-color: skyblue;
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="left">左侧</div>
        <div class="right">右侧</div>
    </div>
</body>

</html>
```

效果：

若果右侧的蓝块不打上浮动，就会脱标

![image-20220309140747314](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309140747314.png)

### 布局案例：

**网页布局第二准侧. 先设置盒子的大小, 之后设置盒子的位置.** 

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>浮动布局练习3</title>
    <style>
        .box {
            width: 1226px;
            height: 615px;
            background-color: pink;
            margin: 0 auto;
        }

        .left {
            float: left;
            width: 234px;
            height: 615px;
            background-color: purple;
        }

        .right {
            float: left;
            width: 992px;
            height: 615px;
            background-color: skyblue;
        }

        .right>div {
            float: left;
            width: 234px;
            height: 300px;
            background-color: pink;
            margin-left: 14px;
            margin-bottom: 14px;
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="left">左青龙</div>
        <div class="right">
            <div>1</div>
            <div>2</div>
            <div>3</div>
            <div>4</div>
            <div>5</div>
            <div>6</div>
            <div>7</div>
            <div>8</div>
        </div>
    </div>
</body>

</html>
```

![image-20220309145620927](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309145620927.png)

![image-20221027203849207](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027203849207.png)

### 清除浮动：

#### 引入：

我们前面浮动元素有一个标准流的父元素, 他们有一个共同的特点,都是有高度的. 
但是, 所有的父盒子都必须有高度吗?  
理想中的状态, 让子盒子撑开父亲.  有多少孩子,我父盒子就有多高. 
但是不给父盒子高度会有问题吗?..... 

![image-20220309151729707](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309151729707.png)

就是因为我们不方便给父元素高度，又需要子元素浮动。这个时候就需要清除浮动了。

![image-20220309151506983](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309151506983.png)

#### 本质：

 1.清除浮动的本质是清除浮动元素造成的影响 
 2.**如果父盒子本身有高度，则不需要清除浮动** 
 3.清除浮动之后，父级就会根据浮动的子盒子自动检测高度。父级有了高度，就不会影响下面的标准流了 

#### 清除浮动方法：

##### 1.额外标签法(不推荐)

隔墙法, 就是在最后一个浮动的子元素后面添加一个额外标签, 添加 清除浮动样式. 

注意这个额外标签必须是块元素

实际工作可能会遇到,但是不常用 



```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>清除浮动之额外标签法</title>
    <style>
        .box {
            width: 800px;
            border: 1px solid blue;
            margin: 0 auto;
        }

        .damao {
            float: left;
            width: 300px;
            height: 200px;
            background-color: purple;
        }

        .ermao {
            float: left;
            width: 200px;
            height: 200px;
            background-color: pink;
        }

        .footer {
            height: 200px;
            background-color: black;
        }
		/*添加样式*/
        .clear {
            clear: both;
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="damao">大毛</div>
        <div class="ermao">二毛</div>
        <div class="ermao">二毛</div>
        <div class="ermao">二毛</div>
        <div class="ermao">二毛</div>
        <div class="clear"></div>
        <!-- 这个新增的盒子要求必须是块级元素不能是行内元素 -->
        <!-- <span class="clear"></span> -->
    </div>
    <div class="footer"></div>

</body>

</html>
```

![image-20220309152342277](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309152342277.png)

##### 2.父级添加 overflow 

可以给父级添加 **overflow** 属性，将其属性值设置为 hidden、 auto 或 scroll 。 

在此不详细解释。

这个其实就是**BFC**的应用之一喔

子不教,父之过,注意是给父元素添加代码 

 优点：代码简洁 
 缺点：无法显示溢出的部分 

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>为什么需要清除浮动</title>
    <style>
        .box {
            /* 清除浮动 */
            overflow: hidden;
            width: 800px;
            border: 1px solid blue;
            margin: 0 auto;
        }

        .damao {
            float: left;
            width: 300px;
            height: 200px;
            background-color: purple;
        }

        .ermao {
            float: left;
            width: 200px;
            height: 200px;
            background-color: pink;
        }

        .footer {
            height: 200px;
            background-color: black;
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="damao">大毛</div>
        <div class="ermao">二毛</div>
    </div>
    <div class="footer"></div>

</body>

</html>
```

##### 3.伪元素清除浮动

相当于用css添加了一个块元素，和法一有异曲同工之妙。见HTML和CSS新增属性第5点

![image-20220309153440205](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309153440205.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>伪元素清除浮动</title>
    <style>
        .clearfix:after {
            content: "";
            display: block;
            height: 0;
            clear: both;
            visibility: hidden;
        }

        .clearfix {
            /* IE6、7 专有 */
            *zoom: 1;
        }

        .box {
            width: 800px;
            border: 1px solid blue;
            margin: 0 auto;
        }

        .damao {
            float: left;
            width: 300px;
            height: 200px;
            background-color: purple;
        }

        .ermao {
            float: left;
            width: 200px;
            height: 200px;
            background-color: pink;
        }

        .footer {
            height: 200px;
            background-color: black;
        }
    </style>
</head>

<body>
    <div class="box clearfix">
        <div class="damao">大毛</div>
        <div class="ermao">二毛</div>
    </div>
    <div class="footer"></div>

</body>

</html>
```

##### 4.双伪元素清除浮动

这个相当于法三，但又在前面加了一个看不见的盒子。见HTML和CSS新增属性第5点

![image-20220309225436048](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309225436048.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>伪元素清除浮动</title>
    <style>
        .clearfix:before,
        .clearfix:after {
            content: "";
            display: table;
        }

        .clearfix:after {
            clear: both;
        }

        .clearfix {
            *zoom: 1;
        }

        .box {
            width: 800px;
            border: 1px solid blue;
            margin: 0 auto;
        }

        .damao {
            float: left;
            width: 300px;
            height: 200px;
            background-color: purple;
        }

        .ermao {
            float: left;
            width: 200px;
            height: 200px;
            background-color: pink;
        }

        .footer {
            height: 200px;
            background-color: black;
        }
    </style>
</head>

<body>
    <div class="box clearfix">
        <div class="damao">大毛</div>
        <div class="ermao">二毛</div>
    </div>
    <div class="footer"></div>

</body>

</html>
```

#### 清除浮动总结：

![image-20220309225756947](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220309225756947.png)

我们目前晓得有这些方法就行，不用死记硬背，用的时候复制过来就行。

:after和::after区别

[:before和::before以及:after和::after的区别 - 掘金 (juejin.cn)](https://juejin.cn/post/7090447984411803656)

## 13.PS切图

### 1.图层切图

![image-20220312142115456](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312142115456.png)

### 2.切片切图

![image-20220312144047689](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312144047689.png)

### 3.插件

用cutterman切图



## 14.边框复合写法

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>边框的复合写法</title>
    <style>
     div {
            width: 300px;
            height: 200px;
            /* border-width: 5px;
            border-style: solid;
            border-color: pink; */
            /* 边框的复合写法 简写:  */
            /* border: 5px solid pink; */
            /* 上边框 */
            border-top: 5px solid pink;
            /* 下边框 */
            border-bottom: 10px dashed purple;
        }
    </style>
</head>
<body>
    <div></div>
</body>
</html>
```



## 15.学成在线案例

### css书写顺序：

![image-20221027233515695](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027233515695.png)

### 整体布局思路：

![image-20220312150259592](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312150259592.png)

### 1.确认版心

```css
/* 有w样式的就是一行一行的标准流，宽度都很宽，就是版心 */
.w{
    width: 1200px;
    margin: auto;
}
```

### 2.头部制作

![image-20220312153414751](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312153414751.png)

#### logo：

html:

```html
<div class="header w">
        <div class="logo">
            <img src="images/logo.png" alt="">
        </div>
    </div>
```

css:

```css
.header{
    height: 42px;
    background-color: pink;
    /* 注意层叠性，覆盖w的margin */
    margin: 30px auto;
}
.header .logo{
    width: 194px;
    height: 42px;
    background-color: blue;
}
```

效果：

![image-20220312153551119](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312153551119.png)

#### 导航栏：

![image-20220312155033210](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312155033210.png)

html:

```html
<!-- 导航栏 -->
        <div class="nav">
            <ul>
                <li><a href="">首页</a></li>
                <li><a href="">课程</a></li>
                <li><a href="">职业规划</a></li>
            </ul>
        </div>
```

css：

```css
/* 导航栏 */
.nav{
    float: left;
    margin-left: 60px;
}
.nav ul li{
    float: left;
    margin: 0 15px;
}
.nav ul li a{
    display: block;
    height: 42px;
    padding: 0 10px;
    line-height: 42px;
    font-size:18px;
    color:#050505;
}
.nav ul li a:hover{
    border-bottom: 2px solid #00a4ff;
    color: #00a4ff;
}
```

效果：

![image-20220312161558949](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312161558949.png)

#### 搜索框：

html:

```html
<!-- 搜索框 -->
        <div class="search">
            <input type="text" value="输入关键词">
            <button></button>
        </div>
```



```css
.search{
    float: left;
    height: 42px;
    width: 411px;
    background-color: skyblue;
    margin-left: 45px;
}
.search input{
    float: left;
    /* 避免撑开盒子  345+15=360 */
    width: 345px;
    height: 40px;
    /* 不要撑开盒子 40+1*2=42px */
    border: 1px solid #00a4ff;
    /* 不要右边框 */
    border-right: 0;
    padding-left: 15px;
    color: #bfbfbf;
    font-size: 14px;
}
.search button{
    float: left;
    /* input宽度345+15+1=361   我们宽度不能超过50  不然总和361+50就超过父亲宽度411了 */
    width: 50px;
    height: 42px;
    /*取消按钮默认边框  */
    border: 0;
    background-image: url(images/search.png);
}
```

注意这里我们给button和input都添加了左浮动，这是因为input和button都是行内块元素，放在一行会有缝隙。

(见第6点)，如果不加float宽度就有问题，button会掉下来。

效果：

![image-20220312165026596](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312165026596.png)

#### 用户：

```html
<!-- 用户 -->
        <div class="user">
            <img src="images/user.png" alt="">
            我是FCX
        </div>
```

```css
.user{
    float: right;
    line-height: 42px;
    font-size: 14px;
    color: #666;
}
```

![image-20220312171100858](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312171100858.png)

我们以后再考虑头像和文字居中的问题

### 3.banner制作

![image-20220312172817532](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312172817532.png)

#### 版心：

```html
<!-- Banner -->
    <div class="banner">
        <div class="w"></div>
    </div>
```

```css
/* banner */
.banner{
    height: 419px;
    background-color: #1c036c;
}
.banner .w{
    height: 419px;
    background-image: url(images/banner2.png);
}

```

![image-20220312172605304](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220312172605304.png)

背景和图片背景色刚好一样

#### 左侧导航栏：

```html
<!-- Banner -->
    <div class="banner">
        <div class="w">
            <div class="subnav">
                <ul>
                    <li><a href="">前端开发<span>&gt;</span></a></li>
                    <li><a href="">后端开发<span>&gt;</span></a></li>
                    <li><a href="">移动开发<span>&gt;</span></a></li>
                    <li><a href="">人工智能<span>&gt;</span></a></li>
                    <li><a href="">商业预测<span>&gt;</span></a></li>
                    <li><a href="">云计算&大数据<span>&gt;</span></a></li>
                    <li><a href="">运维&从测试<span>&gt;</span></a></li>
                    <li><a href="">UI设计<span>&gt;</span></a></li>
                    <li><a href="">产品<span>&gt;</span></a></li>
                </ul>
            </div>
        </div>
    </div>
```



```css
/* 左导航 */
.subnav{
    float: left;
    height: 419px;
    width: 189px;
    /* 设置背景透明度 */
    background-color: rgba(0, 0, 0, 0.3);
}
.subnav ul li{
    height: 45px;
    line-height: 45px;   
    padding-left: 19px; 
}
.subnav ul li a{
    font-size: 14px;
    color: #fff;
}
/* 大于括号 */
.subnav ul li a span{
    float: right;
}
.subnav ul a:hover{
    color: #00b4ff;
}
```

![image-20220313130000535](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313130000535.png)

#### 右侧课程：

![image-20220313133906842](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313133906842.png)

```css
/* 右侧课程 */
.course{
    float: right;
    width: 229px;
    height: 302px;
    background-color: #fff;
    /* 这个地方没有出现塌陷，是加了浮动的原因 */
    margin-top: 51px;
}
.course h2{
    height: 48px;
    background-color: #9bceea;
    text-align: center;
    line-height: 48px;
    font-size: 18px;
    color: #fff;
}
.courseList{
    padding: 0 20px;
}
.courseList ul li{
    padding: 15px 0;
    border-bottom: 1px solid #eaeaea;
}
.courseList a{
    display: block;
    height: 39px;
    text-align: center;
    line-height: 39px;
    color: #00a4ff;
    font-size: 16px;
    border: 2px solid #22b0ff;
}
.courseList ul li h4{
    font-size: 16px;
    color: #4e4e4e;
}
.courseList ul li p{
    font-size: 12px;
    color: #acacac;
}
```

![image-20220313133954309](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313133954309.png)

### 4.精品推荐模块：

![image-20220313134057397](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313134057397.png)

```html
<!-- 精品推荐 -->
    <div class="goods w">
        <h4>精品推荐</h4>
        <ul>
            <li><a href="">JQuery</a></li>
            <li><a href="">Spark</a></li>
            <li><a href="">MySQL</a></li>
            <li><a href="">JavaWeb</a></li>
            <li><a href="">Python</a></li>
            <li><a href="">C++</a></li>
        </ul>
        <a href="">修改兴趣</a>
    </div>
```



```css
/* 精品推荐 */
.goods{
    height: 60px;
    margin-top: 8px;
    background-color: #fff;
    /* 让所有子盒子继承行高 */
    line-height: 60px;
    /* 盒子阴影 */
    box-shadow: 1px 2px 6px 1px rgba(0, 0, 0, 0.3);
}
.goods h4{
    float: left;
    margin-left: 32px;
    font-size: 16px;
    color: #00a4ff;
}
.goods ul{
    float: left;
}
.goods ul li{
    float: left;
}
.goods ul li a{
    padding: 0 30px;
    color: #050505;
    border-left: 1px solid #bfbfbf;
}
.goods>a{
    float: right;
    margin-right: 26px;
    color: #00a4ff;
}
```

![image-20220313142556589](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313142556589.png)

### 5.精品推荐大模块：

![image-20220313142801237](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313142801237.png)



![image-20220313152137126](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313152137126.png)

```css
/* 把父元素宽度扩展到一排足以装下5个盒子 */
/* 1225=(230+15)*5 */
.box-bd ul{
    width: 1225px;
}
.box-bd ul li{
    float: left;
    margin-right: 15px;
    margin-bottom: 15px;
    width: 230px;
    height: 271px;
    background-color: #ffffff;
}
.box-bd ul li a img{
    /* 让图片完全撑开 */
    width: 100%;
}
.box-bd ul li a h4{
    margin: 26px 20px 20px 22px;
    font-size: 14px;
    color: #050505;
}
.box-bd ul li a p{
    margin: 20px 20px 27px 22px;
    font-size: 12px;
    color: #999999;
}
.box-bd ul li a p span{
    color: #ff7c2d;
}
```

![image-20220313152300456](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313152300456.png)

![image-20220313152452653](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313152452653.png)

### 6.职位模块：

（这个模块是我自己写的，不怎么会取名字）

![image-20220313172716018](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313172716018.png)

![image-20220313173010389](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313173010389.png)

块级元素居中详见：[【css系列】六种实现元素水平居中方法 - saucxs - 博客园 (cnblogs.com)](https://www.cnblogs.com/chengxs/p/11231906.html)

我用的是第二种方法

```css
/* 职位1模块 */
.position-1{
    margin-top: 20px;
    background-color: #f3f5f7;
}
/* 头部 */
.position-1-hd{
    /*居中父元素*/
    text-align: center;
    line-height: 60px;
}
.position-1-hd h3{
    float: left;
    margin-left: 32px;
    font-size: 16px;
    color: #494949;
}
.position-1-hd ul{
    /*然后子块元素变成行内块元素，已实现居中的目的*/
    
    display: inline-block;
}
.position-1-hd ul li{
    float: left;
    padding: 0 35px;
}
.position-1-hd ul li a{
    float: left;
    font-size: 16px;
    color: #a5a5a5;
}
.position-1-hd ul li a:hover{
    color: #00a4ff;
}
.position-1-hd>a{
    float: right;
    margin-right: 26px;
    font-size: 12px;
    color: #a5a5a5;
}
/* 底部 */
.position-1-bd{
    height: 392px;
}
/* 底部左侧 */
.position-1-bd-left{
    float: left;
}
/* 底部顶部 */
.position-1-bd-top{
    width: 957px;
    height: 100px;
    float: right;
    background-image: url(images/position-1-bd-top.png);
}
/* 底部底部 */
.position-1-bd-bd{
    float: right;
    width: 957px;
    height: 268px;
    margin-top: 9px;
}
.position-1-bd-bd ul li{
    float: left;
    margin-left: 8px;
    width: 231px;
    background-color: #fff;
}
.position-1-bd-bd ul li a h4{
    margin: 26px 20px 20px 22px;
    font-size: 14px;
    color: #050505;
}
.position-1-bd-bd ul li a p{
    margin: 20px 20px 27px 22px;
    font-size: 12px;
    color: #999999;
}
.position-1-bd-bd ul li a p span{
    color: #ff7c2d;
}
```

![image-20220313173320913](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313173320913.png)

### 7.底部模块：

![image-20220313161436509](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313161436509.png)

![image-20220313191359951](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313191359951.png)

```css
/* 底部 */
.footer{
    height: 418px;
    background-color: #f3f5f7;
}
.footer .w{
    padding-top: 35px;
}
.copyright{
    float: left;
}

.copyright img{
    margin: 32px 0 25px 19px;
}
.copyright p{
    margin-left: 19px;
    font-size: 12px;
    color:#666666
}
.copyright a{
    display: block;
    width: 119px;
    height: 36px;
    margin-top: 17px;
    margin-left: 19px;
    text-align: center;
    line-height: 36px;
    font-size: 16px;
    color: #00a4ff;
    border: 1px solid #00a4ff;
}
.links {
    float: right;
}
.links dl {
    float: left;
    margin-left: 100px;
}
.links dl dt {
    font-size: 16px;
    color: #333;
    margin-bottom: 5px;
}
.links dl dd a {
    color: #333;
    font-size: 12px;
}

```

![image-20220313191422167](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313191422167.png)

## 16.定位

传送门：（阮老师讲的很棒）

[CSS 定位详解 - 阮一峰的网络日志 (ruanyifeng.com)](https://www.ruanyifeng.com/blog/2019/11/css-position.html)

![image-20221027235946894](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221027235946894.png)

position与float同时使用的坑

[position 与 float 同时使用 - 简书 (jianshu.com)](https://www.jianshu.com/p/dbb7447d3ceb)

![image-20221028003513569](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028003513569.png)

为什么需要定位？

![image-20220313193048259](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313193048259.png)

![image-20220313193417293](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313193417293.png)

如果一个盒子既有left属性也有right属性，则默认会执行 left属性 同理  top  bottom  会执行 top 

### 静态定位static（了解）:

![image-20220313193608345](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313193608345.png)

### 相对定位relative：

![image-20220313193645616](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313193645616.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>相对定位</title>
    <style>
        .box1 {
            position: relative;
            top: 100px;
            left: 100px;
            width: 200px;
            height: 200px;
            background-color: pink;
        }
        .box2 {
            width: 200px;
            height: 200px;
            background-color: deeppink;
        }
    </style>
</head>
<body>
    <div class="box1">

    </div>
    <div class="box2">

    </div>
    
</body>
</html>
```

![image-20220313194255540](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313194255540.png)

### 绝对定位absolute:

![image-20220313195035951](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313195035951.png)

**注意绝对定位原来的位置会被占有，这和相对定位不同**

### 子绝父相：

![image-20220313195739797](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313195739797.png)

我们拿学成在线案例举例子

![image-20220313201019283](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313201019283.png)

![image-20220313200903838](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313200903838.png)

![image-20220313223905822](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313223905822.png)

### 固定定位fix：

![image-20220313201218048](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313201218048.png)

#### 固定定位小技巧-固定到版心右侧:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>固定定位小技巧-固定到版心右侧</title>
    <style>
        .w {
            width: 800px;
            height: 1400px;
            background-color: pink;
            margin: 0 auto;
        }
        .fixed {
            position: fixed;
            /* 1. 走浏览器宽度的一半 */
            left: 50%;
            /* 2. 利用margin 走版心盒子宽度的一半距离 */
            margin-left: 405px;
            width: 50px;
            height: 150px;
            background-color: skyblue;
        }
    </style>
</head>
<body>
    <div class="fixed"></div>
    <div class="w">版心盒子 800像素</div>
  
</body>
</html>
```

![image-20220313201657035](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313201657035.png)

### 粘性定位(了解)：

就是滚动一段时间要跟着移动，但是移动到一定位置，再滚动就不动了

![image-20220313201902547](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313201902547.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>粘性定位</title>
    <style>
        body {
            height: 3000px;
        }
        .nav {
            /* 粘性定位 */
            position: sticky;
            /* 滚动至顶，就不再移动 */
            top: 0;
            width: 800px;
            height: 50px;
            background-color: pink;
            margin: 100px auto;
        }
    </style>
</head>
<body>
    <div class="nav">我是导航栏</div>
</body>
</html>
```

### 总结:

![image-20220313202353721](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313202353721.png)

### 有关定位的扩展：

#### 重叠显示问题：

![image-20220313224342792](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313224342792.png)

<center>
    <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028001424578.png" alt="image-20221028001424578" style="zoom:50%;" />
    <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028001459093.png" alt="image-20221028001459093" style="zoom:50%;" />
</center>





#### 有定位的盒子如何居中？

![image-20220313225306980](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313225306980.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>绝对定位水平垂直居中</title>
    <style>
        .box {
            position: absolute;
            width: 200px;
            height: 200px;
            /* 1. left 走 50%  父容器宽度的一半 */
            left: 50%;
            top: 50%;
            /* 2. margin 负值 往左边走 自己盒子宽度的一半 */
            /* 垂直类似 */
            margin-left: -100px;
            margin-top: -100px;
            background-color: pink;
            /* 就不要使用这个居中了 */
            /* margin: auto; */
        }
    </style>
</head>
<body>
    <div class="box"></div>
</body>
</html>
```

![image-20220313225021485](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313225021485.png)

#### 特殊属性：

##### 1.改变了行内元素和块级元素

<a name="juedui">目的地</a>

就是变成行内块元素性质

![image-20220313225337184](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313225337184.png)

下图span粉块也能设置宽高，div蓝块没有占一行了

<center>
    <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028002850819.png" alt="image-20221028002850819" style="zoom:50%;" />
    <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028002752996.png" alt="image-20221028002752996" style="zoom:50%;" />
</center>





##### 2.不触发外边距塌陷问题

![image-20220313225501728](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313225501728.png)

##### 3.绝对和固定定位完全脱标

浮动不会压住下方文字和图片

![image-20220313225535798](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313225535798.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>定位会完全压住标准流盒子内容</title>
    <style>
        .box {
            /* 1.浮动的元素不会压住下面标准流的文字 */
            /* float: left; */
            /* 2. 绝对定位（固定定位） 会压住下面标准流所有的内容。 */
            position: absolute;
            width: 150px;
            height: 150px;
            background-color: pink;
        }
    </style>
</head>
<body>
    <div class="box"></div>
    <p>阁下何不同风起，扶摇直上九万里</p>
</body>
</html>
```

定位完全压住了，但浮动不会

![image-20220313225734675](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313225734675.png)

### 定位案例轮播图：

![image-20220313230032397](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313230032397.png)

![image-20220313230106552](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313230106552.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>淘宝轮播图做法</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        li {
            list-style: none;
        }

        .tb-promo {
            position: relative;
            width: 520px;
            height: 280px;
            background-color: pink;
            margin: 100px auto;
        }

        .tb-promo img {
            width: 520px;
            height: 280px;
        }

        /* 并集选择器可以集体声明相同的样式 */
        .prev,
        .next {
            position: absolute;
            /* 绝对定位的盒子垂直居中 */
            top: 50%;
            margin-top: -15px;
            /* 加了绝对定位的盒子可以直接设置高度和宽度 */
            width: 20px;
            height: 30px;
            background: rgba(0, 0, 0, .3);
            text-align: center;
            line-height: 30px;
            color: #fff;
            text-decoration: none;
        }

        .prev {
            left: 0;
            /* border-radius: 15px; */
            border-top-right-radius: 15px;
            border-bottom-right-radius: 15px;
        }

        .next {
            /* 如果一个盒子既有left属性也有right属性，则默认会执行 left属性 同理  top  bottom  会执行 top */
            right: 0;
            /* border-radius: 15px; */
            border-top-left-radius: 15px;
            border-bottom-left-radius: 15px;
        }
        .promo-nav {
            position: absolute;
            bottom: 15px;
            left: 50%;
            margin-left: -35px;
            width: 70px;
            height: 13px;
            /* background-color: pink; */
            background: rgba(255,255,255, .3);
            border-radius: 7px;
        }
        .promo-nav li {
            float: left;
            width: 8px;
            height: 8px;
            background-color: #fff;
            border-radius: 50%;
            margin: 3px;
        }
        /* 不要忘记选择器权重的问题 */
       .promo-nav .selected {
            background-color: #ff5000;
        }
    </style>
</head>

<body>
    <div class="tb-promo">
        <img src="images/tb.jpg" alt="">
        <!-- 左侧按钮箭头 -->
        <a href="#" class="prev"> &lt; </a>
        <!-- 右侧按钮箭头 -->
        <a href="#" class="next"> &gt; </a>
        <!-- 小圆点 -->
        <ul class="promo-nav">
            <li class="selected"></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>
    </div>
</body>

</html>
```

![image-20220313231933812](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313231933812.png)

## 17.元素的显示与隐藏：

![image-20220313233034988](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313233034988.png)

### display:

![image-20220313233110639](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313233110639.png)

### visibility:

![image-20220313233230334](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313233230334.png)

**隐藏后会占用原来位置，和display不同**

### overflow溢出：

![image-20220313233320336](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313233320336.png)

可以试一下

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>显示隐藏元素之overflow</title>
    <style>
        .peppa {
            /* overflow: visible; */
            /* overflow: hidden; */
            /* scroll 溢出的部分显示滚动条  不溢出也显示滚动条 */
            /* overflow: scroll; */
            /* auto 溢出的时候才显示滚动条 不溢出不显示滚动条 */
            overflow: auto;
            width: 200px;
            height: 200px;
            border: 3px solid pink;
            margin: 100px auto;
        }
    </style>
</head>

<body>
    <div class="peppa">
        这个世界上除了PC还有FC、SFC、MD、PS、N64、NGC、SS、DC、PS2、PSP、GBA、GBASP、NDS、3DS、PS3、
        PSvita、XBOX、XBOX360、PS4、Wii、NS、XBOXone、PS5、XSX等等这个世界上除了马化腾还有
        William Higginbotham、宫崎英高、小岛秀夫、三上真司、阪口博信、宫本茂、神谷英树、上田文人、
        Will Wright、Sid Meier、Alexey Pajitnov、John D. Carmack、Gabe Newell等这个
        世界上除了腾讯等不生产游戏的搬运商以外还有Clover Studio、Blizzard Entertainment、
        Electronic Arts、NEXON、Nintendo、Rockstar、Ubisoft、KONAMI、CAPCOM、Naughty
         Dog、SCE Santa Monica Studio、SEGA、SNK、Valve、KOEI、CDPR、Paradox Interactive、
         Namco、BANDAI、BANDAINAMCO、Square、 Enix、Square Enix等
    </div>

</body>

</html>
```

- 没有加overflow的情况：<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028004925501.png" alt="image-20221028004925501" style="zoom:25%;" />
- overflow: visible(没啥区别)<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028004925501.png" alt="image-20221028004925501" style="zoom:25%;" />
- overflow: hidden<img src="C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20221028005129265.png" alt="image-20221028005129265" style="zoom:25%;" />
- overflow: scroll<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028005155821.png" alt="image-20221028005155821" style="zoom:25%;" />
- overflow: auto<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028005248721.png" alt="image-20221028005248721" style="zoom:25%;" />

### 遮罩层案例：

![image-20220313235612759](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220313235612759.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>仿土豆网显示隐藏遮罩案例</title>
    <style>
        .tudou {
            position: relative;
            width: 444px;
            height: 320px;
            background-color: pink;
            margin: 30px auto;
        }

        .tudou img {
            width: 100%;
            height: 100%;
        }

        .mask {
            /* 隐藏遮罩层 */
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            /*背景的复合写法不要忘了*/
            background: rgba(0, 0, 0, .4) url(images/arr.png) no-repeat center;
        }

        /* 当我们鼠标经过了 土豆这个盒子，就让里面遮罩层显示出来 */
        .tudou:hover .mask {
            /* 而是显示元素 */
            display: block;
        }
    </style>
</head>

<body>
    <div class="tudou">
        <div class="mask"></div>
        <img src="images/tudou.jpg" alt="">
    </div>
</body>

</html>
```

效果就不展示了

# 高阶技巧：

## 1.精灵图

就是把小图合成大图

![image-20220314000218766](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314000218766.png)

就是把这个大图挪一下，挪到只要小图的位置就可以了

往上移动和往左移动为正

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314132250886.png)

### 名字案例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            padding: 0;
            margin: 0;
        }
        .f{
            float: left;
            display: block;
            width: 94px;
            height: 111px;
            background: url(images/abcd.jpg) no-repeat 0px -139px;
        }
        .e{ 
            float: left;
            display: block;
            width: 99px;
            height: 109px;
            background: url(images/abcd.jpg) no-repeat -482px -7px;
        }
        .n{ 
            float: left;
            display: block;
            width: 116px;
            height: 115px;
            background: url(images/abcd.jpg) no-repeat -253px -274px;
        }
        .g{ 
            float: left;
            display: block;
            width: 108px;
            height: 112px;
            background: url(images/abcd.jpg) no-repeat -96px -139px;
        }
    </style>
</head>
<body>
    <span class="f"></span>
    <span class="e"></span>
    <span class="n"></span>
    <span class="g"></span>
</body>
</html>
```

效果：我的姓

![image-20220314135608340](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314135608340.png)

使用技巧：

![image-20220314135801344](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314135801344.png)

## 2.字体图标

![image-20220314140430202](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314140430202.png)

简单的图标用字体图标，复杂的还是用精灵图

![image-20220314140506472](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314140506472.png)

具体使用看这里：

[黑马程序员pink老师前端入门教程，零基础必看的h5(html5)+css3+移动端前端视频教程_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV14J4114768?p=257&spm_id_from=pageDriver)

追加图标：

[黑马程序员pink老师前端入门教程，零基础必看的h5(html5)+css3+移动端前端视频教程_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV14J4114768?p=258&spm_id_from=pageDriver)

之前做项目也用到了阿里的图标看这里：

[尚硅谷VUE项目实战，前端项目-尚品汇(大型\重磅)_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Vf4y1T7bw?p=50&spm_id_from=pageDriver)24分10秒

## 3.三角形

就是给一个高和宽都是0的盒子，靠调整边框颜色画三角形

![image-20220314145002392](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314145002392.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS 三角制作</title>
    <style>
        /*我推荐用box1的这种方法画比较直观，border用熟练了再采用box2的画法*/
        .box1 {
            width: 0;
            height: 0;
            /* border: 10px solid pink; */
            border-top: 10px solid pink;
            border-right: 10px solid red;
            border-bottom: 10px solid blue;
            border-left: 10px solid green;
        }
        .box2 {
            width: 0;
            height: 0;
            border: 50px solid transparent;
            border-left-color: pink;
            margin: 100px auto;
        }
        .jd {
            position: relative;
            width: 120px;
            height: 249px;
            background-color: pink;
        }
        .jd span {
            position: absolute;
            right: 15px;
            top: -10px;
            width: 0;
            height: 0;
            /* 为了照顾兼容性 */
            line-height: 0;  
            font-size: 0;
            border: 5px solid transparent;
            border-bottom-color: pink;
        }
    </style>
</head>
<body>
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="jd">
        <span></span>
    </div>
</body>
</html>
```



![image-20220314144830310](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314144830310.png)

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS 三角制作</title>
    <style>
        .box1 {
            width: 0;
            height: 0;
            /* border: 10px solid pink; */
            border-top: 10px solid pink;
            border-right: 10px solid red;
            border-bottom: 10px solid blue;
            border-left: 10px solid green;
        }
        .box2 {
            width: 0;
            height: 0;
            border: 50px solid transparent;
            border-left-color: pink;
            margin: 100px auto;
        }
        .jd {
            position: relative;
            width: 120px;
            height: 249px;
            background-color: pink;
        }
        .jd span {
            position: absolute;
            right: 15px;
            top: -10px;
            width: 0;
            height: 0;
            /* 为了照顾兼容性 */
            line-height: 0;  
            font-size: 0;
            border: 5px solid transparent;
            border-bottom-color: pink;
        }
    </style>
</head>
<body>
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="jd">
        <span></span>
    </div>
</body>
</html>

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }
        /* 子绝父相 */
        .box {
            position: relative;
            width: 200px;
            height: 400px;
            background-color: skyblue;
            margin: 0 auto;
        }

        .box1 {
            position: absolute;
            width: 0;
            height: 0;
            top: 180px;
            left: 100%;
            border: 20px solid transparent;
            border-left-color: pink;
        }
        /* 可以调整边框画不同的三角形 */
        .box2{
            width: 0;
            height: 0;
            border-top: 50px solid skyblue;
            border-bottom: 50px solid skyblue;
            border-left: 100px solid red;
            border-right: 100px solid red;

        }
    </style>
</head>

<body>
    <div class="box">
        <div class="box1"></div>
    </div>

    <div class="box2"></div>

</body>

</html>
```

![image-20220314144922942](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314144922942.png)

## 4.界面样式：

### 鼠标样式：

![image-20220314145409514](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314145409514.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>用户界面样式-鼠标样式</title>
</head>
<body>
    <ul>
        <li style="cursor: default;">我是默认的小白鼠标样式</li>
        <li style="cursor: pointer;">我是鼠标小手样式</li>
        <li style="cursor: move;">我是鼠标移动样式</li>
        <li style="cursor: text;">我是鼠标文本样式</li>
        <li style="cursor: not-allowed;">我是鼠标禁止样式</li>
    </ul>
</body>
</html>
```

### 表单轮廓，文本域防拖拽：

表单轮廓，就是在input框输入内容时，边框会变色。

文本域防拖拽就是不让用户用鼠标自由缩放文本域大小

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>用户界面样式-表单轮廓和防止拖拽文本域</title>
    <style>
        
        input, textarea {
            /* 取消表单轮廓 */
            outline: none;
        }
        textarea {
            /* 防止拖拽文本域 */
            resize: none;
        }
    </style>
</head>
<body>
    <!-- 1. 取消表单轮廓 -->
    <input type="text">
    <!-- 2. 防止拖拽文本域 -->
    <textarea name="" id="" cols="30" rows="10"></textarea>

    
</body>
</html>
```

## 5.vertical-align 属性应用 

### 图片、表单和文字对齐：

注意只针对于行内元素和行内块元素

![image-20220314150634017](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314150634017.png)

![image-20220314150701567](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314150701567.png)

![image-20220314150724171](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314150724171.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>利用vertical-align实现图片文字垂直居中对齐</title>
    <style>
        img {
            /* vertical-align: bottom; */
            /* 让图片和文字垂直居中 */
            vertical-align: middle;
            /* vertical-align: top; */
        }
        textarea {
            vertical-align: middle;
        }
    </style>
</head>
<body>
    <img src="images/ldh.jpg" alt="">  pink老师是刘德华

    <br>
    <textarea name="" id="" cols="30" rows="10"></textarea> 请您留言
</body>
</html>
```

![image-20220314150821662](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314150821662.png)

### 解决图片底部默认空白缝隙问题 ：

![image-20220314151543802](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314151543802.png)

## 6.溢出的文字省略号显示

### 单行文本溢出显示省略号：

![image-20220314152700870](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314152700870.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>单行文本溢出显示省略号</title>
    <style>
        div {
            width: 150px;
            height: 80px;
            background-color: pink;
            margin: 100px auto;
            /* 这个单词的意思是如果文字显示不开自动换行 */
            /* white-space: normal; */
            /* 1.这个单词的意思是如果文字显示不开也必须强制一行内显示 */
            white-space: nowrap;
            /* 2.溢出的部分隐藏起来 */
            overflow: hidden;
            /* 3. 文字溢出的时候用省略号来显示 */
            text-overflow: ellipsis;
        }
    </style>
</head>
<body>
    <div>
        啥也不说，此处省略一万字777777777777777777777777777777777777777777777777777777777777777777777
    </div>
</body>
</html>
```

- 文字显示不开也必须强制一行内显示white-space: nowrap<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028012909524.png" alt="image-20221028012909524" style="zoom: 50%;" />
- 溢出的部分隐藏起来 overflow:hidden<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028013018260.png" alt="image-20221028013018260" style="zoom:50%;" />
- 文字溢出的时候用省略号来显示 text-overflow: ellipsis

<span style="color: red">这个要结合前两个属性来使用！</span>

[【ellipsis】什么意思_英语ellipsis的翻译_音标_读音_用法_例句_在线翻译_有道词典 (youdao.com)](https://dict.youdao.com/search?q=ellipsis&keyfrom=new-fanyi.smartResult)

[text-overflow - CSS（层叠样式表） | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-overflow#尝试一下)

![image-20221028013732090](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028013732090.png)

![image-20221028013942599](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028013942599.png)

### 多行文本溢出显示省略号：

![image-20220314152812779](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314152812779.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>多行文本溢出显示省略号</title>
    <style>
        div {
            width: 150px;
            height: 65px;
            background-color: pink;
            margin: 100px auto;
            overflow: hidden;
            text-overflow: ellipsis;
            /* 弹性伸缩盒子模型显示 */
            display: -webkit-box;
            /* 限制在一个块元素显示的文本的行数 */
            -webkit-line-clamp: 3;
            /* 设置或检索伸缩盒对象的子元素的排列方式 */
            -webkit-box-orient: vertical;
        }
    </style>
</head>

<body>
    <div>
        啥也不说，此处省略一万字,啥也不说，此处省略一万字此处省略一万字
    </div>
</body>

</html>
```

![image-20220314153012161](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314153012161.png)

## 7.常见布局技巧

### margin负值运用:

![image-20220314160134006](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314160134006.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>margin负值的巧妙运用</title>
    <style>
        ul li {
            position: relative;
            float: left;
            list-style: none;
            width: 150px;
            height: 200px;
            border: 1px solid red;
            margin-left: -1px;
        }

        /* ul li:hover {
           1. 如果盒子没有定位，则鼠标经过添加相对定位即可
        position: relative;
        border: 1px solid blue;

       } */
        ul li:hover {
            /* 2.如果li都有定位，则利用 z-index提高层级 */
            z-index: 1;
            border: 1px solid blue;
        }
    </style>
</head>

<body>
    <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
    </ul>
</body>

</html>
```

![image-20220314161039013](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314161039013.png)

### 文字围绕浮动元素的妙用:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>文字围绕浮动元素的妙用</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        .box {
            width: 300px;
            height: 70px;
            background-color: pink;
            margin: 0 auto;
            padding: 5px;
        }
        .pic {
            float: left;
            width: 120px;
            height: 60px;
            margin-right: 5px;
        }
        .pic img {
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="pic">
            <img src="images/img.png" alt="">
        </div>
        <p>【集锦】热身赛-巴西0-1秘鲁 内马尔替补两人血染赛场</p>
    </div>
</body>
</html>
```

![image-20220314161729012](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314161729012.png)

### 直角三角形：

其实根据这个边框大小和颜色，已经可以画任意等腰三角形（直角三角形用两个等腰的拼接即可）了，不要去背，换个方向一下就绕晕了。自己在浏览器上调一下就会了，重要的是知道把高宽设为0，然后调整边框画三角形这种思想。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            padding: 0;
            margin: 0;
        }
        ul li{
            list-style: none;
            float: left;
            margin-left: 20px;
        }
        /* 直接颜色一样，这样容易理解，但是代码量多 */
        .box{
            height: 0;
            width: 0;
            border-top: 50px solid skyblue;
            border-right: 100px solid red;
            border-bottom: 50px solid red;
            border-left: 100px solid plum;
        }
        .box1{
            height: 0;
            width: 0;
            border-top: 200px solid skyblue;
            border-right: 100px solid red;
            border-bottom: 200px solid red;
            border-left: 100px solid plum;
        }
        .box2{
            width: 0;
            height: 0;
            /* 把上边框宽度调大 */
            /* border-top: 100px solid transparent;
            border-right: 50px solid skyblue; */
            /* 左边和下边的边框宽度设置为0 */
            /* border-bottom: 0 solid blue;
            border-left: 0 solid green; */
           /* 1.只保留右边的边框有颜色 */
           border-color: transparent red transparent transparent;
            /* 2. 样式都是solid */
            border-style: solid;
            /* 3. 上边框宽度要大， 右边框 宽度稍小， 其余的边框该为 0 */
            border-width: 100px 50px 0 0 ;
        }
        .box3{
            width: 190px;
            height: 40px;
            margin-top: 30px;
            line-height: 40px;
            text-align: center;
            border: 1px solid red;
            font-weight: 700;
        }
        .high{
            position: relative;
            width: 60%;
            float: left;
            background-color: red;
        }
        i{
            position: absolute;
            top: 0;
            left: 114px;
            width: 0;
            height: 0;
            border-top: 20px solid red;
            border-right: 10px solid transparent;
            border-bottom: 20px solid transparent;
            border-left: 10px solid red;
        }
        .low{
            font-size: 12px;
            color: gray;
            text-decoration: line-through;
        }
    </style>
</head>
<body>
    <ul>
        <li class="box"></li>
        <li class="box1"></li>
        <li class="box2"></li>
        <li class="box3">
            <span class="high">
                ￥9000
                <i></i> 
            </span>
            <span class="low">￥9999</span>
        </li>
    </ul>
</body>
</html>
```

![image-20220314182912443](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314182912443.png)

## 8.初始化css

京东css初始化：

```css
/* 把我们所有标签的内外边距清零 */
* {
    margin: 0;
    padding: 0
}
/* em 和 i 斜体的文字不倾斜 */
em,
i {
    font-style: normal
}
/* 去掉li 的小圆点 */
li {
    list-style: none
}

img {
    /* border 0 照顾低版本浏览器 如果 图片外面包含了链接会有边框的问题 */
    border: 0;
    /* 取消图片底侧有空白缝隙的问题 */
    vertical-align: middle
}

button {
    /* 当我们鼠标经过button 按钮的时候，鼠标变成小手 */
    cursor: pointer
}
/*a标签取消下划线*/
a {
    color: #666;
    text-decoration: none
}

a:hover {
    color: #c81623
}

button,
input {
    /* "\5B8B\4F53" 就是宋体的意思 这样浏览器兼容性比较好 */
    font-family: Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif
}

body {
    /* CSS3 抗锯齿形 让文字显示的更加清晰 */
    -webkit-font-smoothing: antialiased;
    background-color: #fff;
    /*继承行高*/
    font: 12px/1.5 Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif;
    color: #666
}

.hide,
.none {
    display: none
}
/* 清除浮动 */
.clearfix:after {
    visibility: hidden;
    clear: both;
    display: block;
    content: ".";
    height: 0
}

.clearfix {
    *zoom: 1
}
```

# HTML5和CSS3新增属性：

![image-20220314184840560](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314184840560.png)

## 1.新增语义标签

传送门：

[不要一直用啦！语义化标签了解下？ - 掘金 (juejin.cn)](https://juejin.cn/post/7021448274431180831)

不怎么看好，还是喜欢用div+class命名的方式。看评论区知真

缺点：

- 有些标签可能还不知道就已经过时了
- 很多语义标签自带样式，而这些样式我们并不需要，所以还要先取消默认样式。
- 现代网页已经不再是按照书籍排版的结构来的，很多页面元素并不容易明确应该使用哪个语义标签。

![image-20220314184921747](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314184921747.png)

![image-20220314184947767](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314184947767.png)

## 2.新增多媒体标签

属性太多了，记不住也很正常，用的时候去查就行

### video：

![image-20220314190309453](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314190309453.png)

![image-20220314190133024](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314190133024.png)

### audio:

![image-20220314190622724](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314190622724.png)

![image-20220314190646148](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314190646148.png)

### 总结：

![image-20220314190839352](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314190839352.png)

## 3.新增input类型

![image-20220314191336657](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314191336657.png)

## 4.新增表单属性

![image-20220314191759882](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314191759882.png)

## 5.新增选择器

### 	属性选择器：

![image-20220314192328474](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314192328474.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS3新增属性选择器</title>
    <style>
        /* 必须是input 但是同时具有 value这个属性 选择这个元素  [] */
        /* input[value] {
            color:pink;
        } */
        /* 只选择 type =text 文本框的input 选取出来 */
        input[type=text] {
            color: pink;
        }
        /* 选择首先是div 然后 具有class属性 并且属性值 必须是 icon开头的这些元素 */
        div[class^=icon] {
            color: red;
        }
        section[class$=data] {
            color: blue;
        }
        div.icon1 {
            color: skyblue;
        }
        /* 类选择器和属性选择器 伪类选择器 权重都是 10 */
    </style>
</head>
<body>
    <!-- 1. 利用属性选择器就可以不用借助于类或者id选择器 -->
    <!-- <input type="text" value="请输入用户名">
    <input type="text"> -->
    <!-- 2. 属性选择器还可以选择属性=值的某些元素 重点务必掌握的 -->
    <input type="text" name="" id="">
    <input type="password" name="" id="">
    <!-- 3. 属性选择器可以选择属性值开头的某些元素 -->
    <div class="icon1">小图标1</div>
    <div class="icon2">小图标2</div>
    <div class="icon3">小图标3</div>
    <div class="icon4">小图标4</div>
    <div>我是打酱油的</div>
    <!-- 4. 属性选择器可以选择属性值结尾的某些元素 -->
    <section class="icon1-data">我是安其拉</section>
    <section class="icon2-data">我是哥斯拉</section>
    <section class="icon3-ico">哪我是谁</section>

</body>
</html>
```

### 结构伪类选择器:

**n是第n个，只能正整数**

![image-20220314192926899](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314192926899.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS3新增结构伪类选择器</title>
    <style>
        /* 1. 选择ul里面的第一个孩子 小li */
        ul li:first-child {
            background-color: pink;
        }
        /* 2. 选择ul里面的最后一个孩子 小li */
        ul li:last-child {
            background-color: pink;
        }
         /* 3. 选择ul里面的第2个孩子 小li */
         ul li:nth-child(2) {
            background-color: skyblue;
        }
        ul li:nth-child(6) {
            background-color: skyblue;
        }
    </style>
</head>
<body>
    <ul>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ul>
</body>
</html>
```

![image-20221028123425147](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028123425147.png)

![image-20220314192950146](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314192950146.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS3新增结构伪类选择器-nth-child</title>
    <style>
        /* 1.把所有的偶数 even的孩子选出来 */
        ul li:nth-child(even) {
            background-color: #ccc;
        }

        /* 2.把所有的奇数 odd的孩子选出来 */
        ul li:nth-child(odd) {
            background-color: gray;
        }
        /* 3.nth-child(n) 从0开始 每次加1 往后面计算  这里面必须是n 不能是其他的字母 选择了所有的孩子*/
        /* ol li:nth-child(n) {
            background-color: pink;
        } */
        /* 4.nth-child(2n)母选择了所有的偶数孩子 等价于 even*/
         /* ol li:nth-child(2n) {
            background-color: pink;
        } */
        /* 5.选择所有奇数等价于，odd */
        /* ol li:nth-child(2n+1) {
            background-color: skyblue;
        }  */
        /* 6.第3个开始，包含第3个 */
        /* ol li:nth-child(n+3) {
            background-color: pink;
        } */
        /* 7.前3个，包含第3个 */
        ol li:nth-child(-n+3) {
            background-color: pink;
        }
    </style>
</head>

<body>
    <ul>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ul>
    <ol>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ol>
</body>

</html>
```

要注意下E:nth-child(n)和E:nth-of-type(n)的区别!

![image-20220314193607716](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314193607716.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS3新增选择器nth-type-of</title>
    <style>
        ul li:first-of-type {
            background-color: pink;
        }
        ul li:last-of-type {
            background-color: pink;
        }
        ul li:nth-of-type(even) {
            background-color: skyblue;
        }
        /* nth-child 会把所有的盒子都排列序号 */
        /* 执行的时候首先看  :nth-child(1) 之后回去看 前面 div */

        section div:nth-child(1) {
            background-color: red;
        }
         /* nth-of-type 会把指定元素的盒子排列序号 */
        /* 执行的时候首先看  div指定的元素  之后回去看 :nth-of-type(1) 第几个孩子 */
        section div:nth-of-type(1) {
            background-color: blue;
        }
    </style>
</head>

<body>
    <ul>
        <li>我是第1个孩子</li>
        <li>我是第2个孩子</li>
        <li>我是第3个孩子</li>
        <li>我是第4个孩子</li>
        <li>我是第5个孩子</li>
        <li>我是第6个孩子</li>
        <li>我是第7个孩子</li>
        <li>我是第8个孩子</li>
    </ul>
    <!-- 区别 -->
    <section>
        <p>光头强</p>
        <div>熊大</div>
        <div>熊二</div>
    </section>
</body>

</html>
```

![image-20220315142624360](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315142624360.png)

#### 总结：

![image-20220314193718493](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314193718493.png)

### 伪元素选择器：

**伪元素属于行内元素**

设置高宽当然无效。注意不要和以前的伪类搞混了

**伪元素属于子元素**，我们常常使用子绝父相来定位

**:after和::after区别**

[:before和::before以及:after和::after的区别 - 掘金 (juejin.cn)](https://juejin.cn/post/7090447984411803656)

![image-20220314194439802](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314194439802.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>伪元素选择器before和after</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
        }
        /* div::before 权重是2 */
        div::before {
            /* 这个content是必须要写的 */
            /* display: inline-block; */
            /* 高度，宽度不起作用，想起作用转换类型 */
            content: '我';
            /* width: 30px;
            height: 40px;
            background-color: purple; */
        }
        div::after {
            content: '小猪佩奇';
        }
    </style>
</head>
<body>
    <div>
        是
    </div>
</body>
</html>
```

![image-20220314194551128](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220314194551128.png)

#### 应用:

之前写的土豆遮罩层案例：

```css
/* 当我们鼠标经过了 土豆这个盒子，就让里面before遮罩层显示出来 */ 
.tudou:hover::before { 
    /* 而是显示元素 */ 
    display: block; 
} 

```

#### 清除浮动：

![image-20220315153159128](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315153159128.png)

![image-20220315153213065](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315153213065.png)

#### 引入字体图标：

iconfont的官网写的很好，以前我都是用他家的cdn引入的。下面简单介绍下本地文件引入。

![image-20221028134534336](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028134534336.png)

解压后官方说的很清楚

![image-20221028134703056](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028134703056.png)

打开css文件就可以看见伪元素的运用

![image-20221028134824190](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028134824190.png)

直接使用即可。注意这里用到了**子绝父相**，而且图标还是垂直居中的。之前有讲过**定位盒子如何居中**。

因为字体大小是16px，我们top：50%后，再往上平移自身高度一半即8px即可

<center>
   <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028135703122.png" alt="image-20221028135703122" style="zoom:50%;" />
    <img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028135724958.png" alt="image-20221028135724958" style="zoom:50%;" />
</center>





## 6.盒子模型

以前我们，给一个盒子加上border或者padding都会撑大盒子，如果想保证盒子原来的大小。就需要减去多出来的宽度，非常麻烦。CSS3我们可以方便地解决这个问题

![image-20220315153647024](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315153647024.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS3盒子模型</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        div {
            width: 200px;
            height: 200px;
            margin-bottom: 10px;
            background-color: pink;
            border: 20px solid red;
            padding: 15px;
            /* 默认的 */
            box-sizing: content-box;
        }
        p {
            width: 200px;
            height: 200px;
            background-color: pink;
            border: 20px solid red;
            padding: 15px;
            /* css3 盒子模型  盒子最终的大小就是 width  200 的大小 */
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <div>
        小猪乔治
    </div>
    <p>
        小猪佩奇
    </p>
</body>
</html>
```

![image-20221028141228137](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028141228137.png)

## 7.CSS3新增的其他属性

### filter:

就是Adobe里面的**高斯模糊**

![image-20220315154526464](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315154526464.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>图片模糊处理filter</title>
    <style>
        img {
            /* blur是一个函数 小括号里面数值越大，图片越模糊 注意数值要加px单位 */
            filter: blur(15px);
        }
        img:hover {
            filter: blur(0);
        }
    </style>
</head>
<body>
   <img src="images/pink.jpg" alt="">
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315154700291.png" alt="image-20220315154700291" style="zoom:50%;" />

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315154736128.png" alt="image-20220315154736128" style="zoom:50%;" />

### calc:

注意运算符旁必须要有空格。**这个会引起回流！**

![image-20220315154805107](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315154805107.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS3属性calc函数</title>
    <style>
        .father {
            width: 300px;
            height: 200px;
            background-color: pink;
        }
        .son {
            /* width: 150px; */
            /* width: calc(150px + 30px); */
            width: calc(100% - 30px);
            height: 30px;
            background-color: skyblue;
        }
    </style>
</head>
<body>
    <!-- 需求我们的子盒子宽度永远比父盒子小30像素 -->
    <div class="father">
        <div class="son"></div>
    </div>
</body>
</html>
```

### 过渡(transition)：

就是AE和PR里面的**关键帧动画**啦~区别就是我们要自己写，AE里面直接打关键帧即可。

**过渡transition配合转化transform**可以做很多关键帧动画

过渡（transition)是CSS3中具有颠覆性的特征之一，我们可以在不使用 Flash 动画或 
JavaScript 的情况下，当元素从一种样式变换为另一种样式时为元素添加效果。 

过渡动画： 是从一个状态 渐渐的过渡到另外一个状态 
可以让我们页面更好看，更动感十足，虽然 低版本浏览器不支持（ie9以下版本） 但是不会影响页面布局。 

我们现在经常和 :hover 一起 搭配使用。

![image-20220315160133333](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315160133333.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS3 过渡效果</title>
    <style>
       div {
            width: 200px;
            height: 100px;
            background-color: pink;
            /* transition: 变化的属性 花费时间 运动曲线 何时开始; */
            transition: width .5s ease 0s, height .5s ease 0s;
            /* 如果想要写多个属性，利用逗号进行分割 */
            /* transition: width .5s, height .5s; */
            /* 如果想要多个属性都变化，属性写all就可以了 */
            /* transition: height .5s ease 1s; */
            /* 谁做过渡，给谁加 */
            /* transition: all 0.5s; */
        }
        div:hover {
            width: 400px;
            height: 200px;
            background-color: skyblue;
        }
    </style>
</head>
<body>
    <div></div>
</body>
</html>
```

关键帧0s开始，0.5秒结束。变换属性有宽度从200变成400，高度从100变成200px

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/1.gif)

#### 进度条案例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 400px;
            height: 50px;
            margin: 100px auto;
            border: 2px solid red;
            border-radius: 25px;
        }
        .box2{
            width: 50%;
            height: 100%;
            background-color: red;
            border-radius: 25px;
            /* 谁做过渡给谁加 */
            transition: width 1s ;
        }
        .box1:hover .box2{
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="box1">
        <div class="box2"></div>
    </div>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/2.gif" style="zoom: 100%"></img>

#### 图片淡入淡出案例：

（自己写的，很丑）

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }

        .box1 {
            position: relative;
            width: 500px;
            height: 500px;
            background-color: red;
        }

        .box1 img:first-child {
            position: absolute;
            top: 70px;
            transition: left 1s;
        }

        .box1 img:last-child {
            position: absolute;
            top: 120px;
            left: -500px;
            transition: left 1s;
        }

        .box1:hover img:first-child {
            left: -500px;
        }

        .box1:hover img:last-child {
            left: 20px;
        }
    </style>
</head>

<body>
    <div class="box1">
        <img src="images/pink.jpg" alt="">
        <img src="images/tudou.jpg" alt="">
    </div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/3.gif" style="zoom: 100%"></img>

## 8.CSS3 2D转化transform

### translate移动

这个就是关键帧动画列的位置属性

对行内元素无效

![image-20220315173645315](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315173645315.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /*清理默认属性*/
        *{
            margin: 0;
            padding: 0;
        }
        /* 移动盒子的位置： 定位   盒子的外边距  2d转换移动 */    
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            /* x就是x轴上移动位置 y 就是y轴上移动位置 中间用逗号分隔*/
            /* transform: translate(x, y); */
            /* transform: translate(100px, 100px); */
            /* 1. 我们如果只移动x坐标,两种写法 */
            /* transform: translate(100px, 0); */
            /* transform: translateX(100px); */
            /* 2. 我们如果只移动y坐标，两种写法 */
            /* transform: translate(0, 100px); */
            /* transform: translateY(100px); */
        }
        
        div:first-child {
            transform: translate(30px, 30px);
        }
        
        .last{
            background-color: purple;
        }
    </style>
</head>

<body>
    <div></div>
    <div class="last"></div></div>
</body>

</html>
```

看左上角这个点，x和y轴上的距离比较清晰

![image-20221028145055423](https://picture-feng.oss-cn-chengdu.aliyuncs.com/my%20life/image-20221028145055423.png)

#### 子盒子居中：

其实和margin是一个道理，不过这样写平移就不用写具体一半的数值了~

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            position: relative;
            width: 500px;
            height: 500px;
            background-color: pink;
            /* 1. 我们tranlate里面的参数是可以用 % */
            /* 2. 如果里面的参数是 % 移动的距离是 盒子自身的宽度或者高度来对比的 */
            /* 这里的 50% 就是 50px 因为盒子的宽度是 100px */
            /* transform: translateX(50%); */
        }
        
        p {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 200px;
            height: 200px;
            background-color: purple;
            /* margin-top: -100px;
            margin-left: -100px; */
            /* translate(-50%, -50%)  盒子往上走自己高度的一半   */
            transform: translate(-50%, -50%);
        }
        
        span {
            /* translate 对于行内元素是无效的 */
            transform: translate(300px, 300px);
        }
    </style>
</head>

<body>
    <div>
        <p></p>
    </div>
    <span>123</span>
</body>

</html>
```

![image-20220315175147535](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315175147535.png)

### rotate旋转

![image-20220315175643018](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315175643018.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        img {
            width: 150px;
            /* 顺时针旋转45度 */
            /* transform: rotate(45deg); */
            border-radius: 50%;
            border: 5px solid pink;
            /* 过渡写到本身上，谁做动画给谁加 */
            transition: all 0.3s;
        }
        /* 转360度 */
        img:hover {
            transform: rotate(360deg);
        }
    </style>
</head>

<body>
    <img src="media/pic.jpg" alt="">
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/4.gif" style="zoom: 100%"></img>

#### 小三角旋转案例：



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div{
            position: relative;
            width: 600px;
            height: 40px;
            border: 2px solid rgb(174, 214, 230);
            margin: 100px auto;
        }
        /*小三角是边框做出来的*/
        div::after{
            position: absolute;
            content: "";
            right: 10px;
            top:10px;
            width: 20px;
            height: 20px;
            border-right: 2px solid black;
            border-bottom: 2px solid black;
            transform: rotate(45deg);
            transition: all 0.5s;
        }
        div:hover::after{
            transform: rotate(225deg);
        }
    </style>
</head>
<body>
    <div></div>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/5.gif" style="zoom: 100%"></img>

#### transform-origin设置旋转中心点：

就是AE里面的锚点啦~

![image-20220315190712030](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315190712030.png)

这个中心点设置还是相对于左上角

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            margin: 100px auto;
            transition: all 1s;
            /* 1.可以跟方位名词 */
            /* transform-origin: left bottom; */
            /* 2. 默认的是 50%  50%  等价于 center  center */
            /* 3. 可以是px 像素 */
            transform-origin: 50px 50px;
        }
        
        div:hover {
            transform: rotate(360deg);
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/6.gif" style="zoom: 100%"></img>

#### 案例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div{
            /*初始状态隐藏伪元素*/
            overflow: hidden;
            width: 200px;
            height: 200px;
            margin: 200px auto;
            background-color: rgb(197, 219, 228);
        }
        div::before{
            content: "冯小7";
            /* 伪元素属于行内元素，一定要转化才能设置高宽 */
            display: block;
            width: 100%;
            height: 100%;
            background-color: skyblue;
            transform-origin: left bottom;
            /*初始状态旋转180*/
            transform: rotate(180deg);
            transition: all 0.8s;
        }
        div:hover::before{
            transform: rotate(0deg);
        }
    </style>
</head>
<body>
    <div></div>
</body>
</html>
```

开始是180度旋转，hover以后是回到0度旋转

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/7.gif" style="zoom: 100%"></img>

### scale缩放

![image-20220315193317586](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315193317586.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            margin: 100px auto;
            /*scale也可以设置中心点*/
            /* transform-origin: left bottom; */
        }
        
        div:hover {
            /* 1. 里面写的数字不跟单位 就是倍数的意思 1 就是1倍  2就是 2倍 */
            /* transform: scale(x, y); */
            /* transform: scale(2, 2); */
            /* 2. 修改了宽度为原来的2倍  高度 不变 */
            /* transform: scale(2, 1); */
            /* 3. 等比例缩放 同时修改宽度和高度，我们有简单的写法  以下是 宽度修改了2倍，高度默认和第一个参数一样*/
            /* transform: scale(2); */
            /* 4. 我们可以进行缩小  小于1 就是缩放 */
            /* transform: scale(0.5, 0.5); */
            /* transform: scale(0.5); */
            /* 5. scale 的优势之处： 不会影响其他的盒子 而且可以设置缩放的中心点*/
            /* width: 300px;
            height: 300px; */
            transform: scale(2);
        }
    </style>
</head>

<body>
    <div></div>
    123123
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/8.gif" style="zoom: 100%"></img>

#### 缩放图片案例：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            overflow: hidden;
            float: left;
            margin: 10px;
        }
        
        div img {
            transition: all .4s;
        }
        
        div img:hover {
            transform: scale(1.1);
        }
    </style>
</head>

<body>
    <div>
        <a href="#"><img src="media/scale.jpg" alt=""></a>
    </div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/9.gif" style="zoom: 100%"></img>

### 2D转换复合写法：

<span style="color: red">一定要注意顺序问题！</span>

![image-20220315194628282](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315194628282.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            margin: 100px auto;
            width: 200px;
            height: 200px;
            background-color: pink;
            transition: all .5s;
        }
        
        div:hover {
            /* transform: rotate(180deg) translate(150px, 50px); */
            /* 我们同时有位移和其他属性，我们需要把位移放到最前面 */
            transform: translate(150px, 50px) rotate(180deg) scale(1.2);
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/10.gif" style="zoom: 100%"></img>

### 总结：

![image-20220315195151428](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315195151428.png)

## 9.CSS3 动画

这个就是正宗的关键帧动画了

### 基本使用：

![image-20220315195638626](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315195638626.png)

![image-20220315195702623](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315195702623.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* 我们想页面一打开，一个盒子就从左边走到右边 */
        /* 1. 定义动画 */
        
        @keyframes move {
            /* 开始状态 */
            0% {
                transform: translateX(0px);
            }
            /* 结束状态 */
            100% {
                transform: translateX(1000px);
            }
        }
        
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            /* 2. 调用动画 */
            /* 动画名称 */
            animation-name: move;
            /* 持续时间 */
            animation-duration: 2s;
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/11.gif" style="zoom: 100%"></img>

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* from to 等价于  0% 和  100% */
        /* @keyframes move {
            from {
                transform: translate(0, 0);
            }
            to {
                transform: translate(1000px, 0);
            }
        } */
        /* 动画序列 */
        /* 1. 可以做多个状态的变化 keyframe 关键帧 */
        /* 2. 里面的百分比要是整数 */
        /* 3. 里面的百分比就是 总的时间（我们这个案例10s）的划分 25% * 10  =  2.5s */
        
        @keyframes move {
            0% {
                transform: translate(0, 0);
            }
            25% {
                transform: translate(1000px, 0)
            }
            50% {
                transform: translate(1000px, 500px);
            }
            75% {
                transform: translate(0, 500px);
            }
            100% {
                transform: translate(0, 0);
            }
        }
        
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
            animation-name: move;
            animation-duration: 3s;
        }
    </style>
</head>

<body>
    <div>

    </div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/12.gif" style="zoom: 100%"></img>

### 常用属性：

![image-20220315200534790](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315200534790.png)

![image-20220315201421109](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315201421109.png)

### 热点图案例：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            background-color: #333;
        }
        
        .map {
            position: relative;
            width: 747px;
            height: 616px;
            background: url(media/map.png) no-repeat;
            margin: 0 auto;
        }
        
        .city {
            position: absolute;
            top: 227px;
            right: 193px;
            color: #fff;
        }
        
        .tb {
            top: 500px;
            right: 80px;
        }
        
        .dotted {
            width: 8px;
            height: 8px;
            background-color: #09f;
            border-radius: 50%;
        }
        
        .city div[class^="pulse"] {
            /* 保证我们小波纹在父盒子里面水平垂直居中 放大之后就会中心向四周发散 */
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 8px;
            height: 8px;
            /*用盒子阴影来做*/
            box-shadow: 0 0 12px #009dfd;
            border-radius: 50%;
            /*匀速无限运动*/
            animation: pulse 1.2s linear infinite;
        }
        /*错开时间*/
        .city div.pulse2 {
            animation-delay: 0.4s;
        }
        
        .city div.pulse3 {
            animation-delay: 0.8s;
        }
        
        @keyframes pulse {
            0% {}
            70% {
                /*0-70%，高宽变大，变为不透明*/
                /* transform: scale(5);  我们不要用scale 因为他会让 阴影变大*/
                width: 40px;
                height: 40px;
                opacity: 1;
            }
            100% {
                /*70%-100%，高宽变更大，变为透明*/
                width: 70px;
                height: 70px;
                opacity: 0;
            }
        }
    </style>
</head>

<body>
    <div class="map">
        <div class="city">
            <div class="dotted"></div>
            <div class="pulse1"></div>
            <div class="pulse2"></div>
            <div class="pulse3"></div>
        </div>
        <div class="city tb">
            <div class="dotted"></div>
            <div class="pulse1"></div>
            <div class="pulse2"></div>
            <div class="pulse3"></div>
        </div>
    </div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/13.gif" style="zoom: 100%"></img>

### 速度曲线细节：

步长调节

![image-20220315205629069](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220315205629069.png)

#### 案例1文字依次出现：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div{
            overflow: hidden;
            margin: 100px auto;
            height: 30px;
            white-space: nowrap;
            background-color: pink;
            font-size: 20px;
            animation: w 4s steps(9) forwards;
        }
        @keyframes w{
            0%{
                width: 0;
            }
            100%{
                width: 180px;
            }

        }
    </style>
</head>
<body>
    <div>我是一个姓冯的学生</div>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/14.gif" style="zoom: 100%"></img>

#### 案例2奔跑的北极熊：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body{
            background-color: #ccc;
        }
        div{
            position: absolute;
            width: 200px;
            height: 100px;
            background: url(media/bear.png) no-repeat;
            /* 我们元素可以添加多个动画， 用逗号分隔 */
            animation: run .8s steps(8) infinite forwards,move 2s linear forwards
        }
        /*这是熊奔跑的动画*/
        @keyframes run{
            0%{
                background-position: 0 0;
            }
            100%{
                /*这里使用的是背景方位，精灵图有用到*/
                background-position: -1600px 0;
            }
        }
        /*这是熊移动的动画*/
        @keyframes move{
            0%{
                left:0px
            }
            100%{
                /* 跑到画面中央，再减去半个身位 */
                left: 50%;
                transform: translateX(-50%);
            }
        }
    </style>
</head>
<body>
    <div></div>
</body>
</html>
```

原图 8帧

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/bear.png" style="zoom: 100%"></img>

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/15.gif" style="zoom: 100%"></img>

## 10.CSS3 3D变换

稍微详细点的文章……

传送门：[好吧，CSS3 3D transform变换，不过如此！ « 张鑫旭-鑫空间-鑫生活 (zhangxinxu.com)](https://www.zhangxinxu.com/wordpress/2012/09/css3-3d-transform-perspective-animate-transition/)

![image-20220316100250996](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316100250996.png)

### 3D位移translate3d

![image-20220316100605324](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316100605324.png)



#### 透视perspective

透视就是人的眼睛到屏幕的距离。**我们把屏幕固定，改变透视就是改变人眼到屏幕的距离，translateZ就是改变物体的位置**

![image-20220316101118053](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316101118053.png)

注意透视不一定要写在父盒子上，也可以写在自己身上。两种写法有差异。

见[好吧，CSS3 3D transform变换，不过如此！ « 张鑫旭-鑫空间-鑫生活 (zhangxinxu.com)](https://www.zhangxinxu.com/wordpress/2012/09/css3-3d-transform-perspective-animate-transition/)第6点

### perspective-origin

写法和transform-origin一样，就是改变锚点

透视越小相当于眼睛离屏幕越近，看到的物体越大

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            /* 透视写到被观察元素的父盒子上面 */
            perspective: 200px;
        }
        
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            /* transform: translateX(100px);
            transform: translateY(100px); */
            /* transform: translateX(100px) translateY(100px) translateZ(100px); */
            /* 1. translateZ 沿着Z轴移动 */
            /* 2. translateZ 后面的单位我们一般跟px */
            /* 3. translateZ(100px) 向外移动100px （向我们的眼睛来移动的） */
            /* 4. 3D移动有简写的方法 */
            /* transform: translate3d(x,y,z); */
            /* transform: translate3d(100px, 100px, 100px); */
            /* 5. xyz是不能省略的，如果没有就写0 */
            transform: translate3d(400px, 100px, 100px);
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

#### translateZ

就是物体距离屏幕的距离，透视是人眼距离屏幕的距离。屏幕是固定的，想象移动物体就行

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            perspective: 500px;
        }
        
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            margin: 300px auto;
            animation: change 4s linear forwards;
        }
        @keyframes change{
            /* 一开始，图像很小.相当于物体在屏幕外了 */
            0%{
                transform: translateZ(-300px);
            }
            /* 100%时。物体离我们眼睛更近了，图像也就变大了 */
            /* 如果超过透视的500px，就相当于物体直接贴在眼睛上，占满全屏 */
            100%{
                transform: translateZ(300px);
            }
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

我这个截屏只是截了一部分，没有截全屏幕

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/16.gif" style="zoom: 100%"></img>

### 3D旋转rotate3d

![image-20220316103915607](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316103915607.png)

#### rotateX

4指就是正方向

![image-20220316104006587](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316104006587.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            perspective: 300px;
        }
        
        img {
            display: block;
            margin: 100px auto;
            transition: all 1s;
        }
        
        img:hover {
            transform: rotateX(45deg);
        }
    </style>
</head>

<body>
    <img src="media/pig.jpg" alt="">
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/17.gif" style="zoom: 100%"></img>

#### rotateY

![image-20220316104313033](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316104313033.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            perspective: 500px;
        }
        
        img {
            display: block;
            margin: 100px auto;
            transition: all 1s;
        }
        
        img:hover {
            transform: rotateY(45deg);
        }
    </style>
</head>

<body>
    <img src="media/pig.jpg" alt="">
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/18.gif" style="zoom: 100%"></img>

#### rotateZ

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            perspective: 500px;
        }
        
        img {
            display: block;
            margin: 100px auto;
            transition: all 1s;
        }
        
        img:hover {
            transform: rotateZ(180deg);
            /* transform: rotate3d(x,y,z,deg); */
            /* transform: rotate3d(1, 0, 0, 45deg); */
            /* transform: rotate3d(0, 1, 0, 45deg); */
            /* transform: rotate3d(1, 1, 0, 45deg); */
        }
    </style>
</head>

<body>
    <img src="media/pig.jpg" alt="">
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/19.gif" style="zoom: 100%"></img>

#### rotate3d

![image-20220316105002743](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316105002743.png)

#### 3D呈现transform-style

![image-20220316105831815](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316105831815.png)



```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            perspective: 500px;
        }
        
        .box {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 100px auto;
            transition: all 2s;
            /* 让子元素保持3d立体空间环境 */
            transform-style: preserve-3d;
        }
        
        .box:hover {
            transform: rotateY(60deg);
        }
        
        .box div {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: pink;
        }
        
        .box div:last-child {
            background-color: purple;
            transform: rotateX(60deg);
        }
    </style>
</head>

<body>
    <div class="box">
        <div></div>
        <div></div>
    </div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/20.gif" style="zoom: 100%"></img>

### 案例，两面旋转的盒子：

![image-20220316111826381](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316111826381.png)

![image-20220316111859740](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316111859740.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        body {
            perspective: 400px;
        }
        
        .box {
            position: relative;
            width: 300px;
            height: 300px;
            margin: 100px auto;
            transition: all .4s;
            /* 让背面的紫色盒子保留立体空间 给父级添加的 */
            transform-style: preserve-3d;
        }
        
        .box:hover {
            /* 让大盒子翻转，把后面的盒子显示出来 */
            transform: rotateY(180deg);
        }
        /*初始化*/
        .front,
        .back {
            position: absolute;
            /* backface-visibility:hidden; */
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            font-size: 30px;
            color: #fff;
            text-align: center;
            line-height: 300px;
        }
        
        .front {
            background-color: pink;
            /* 这行代码，让正面的盒子往上挪一点盖住后面的盒子 */
            transform:translateZ(1px);
        }
        
        .back {
            background-color: purple;
            /* 让后边的盒子绕Y旋转，让它转到正面盒子的背面，直接贴贴 */
            transform: rotateY(180deg);
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="front">我是FengXiao7</div>
        <div class="back">我喜欢看电影</div>
    </div>
</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/21.gif" style="zoom: 100%"></img>

### 案例，3D导航栏：

![image-20220316122953155](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316122953155.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            padding: 0;
            margin: 0;
        }
        ul{
            margin: 100px auto;
        }
        ul li{
            margin: 0 5px;
            width: 200px;
            height: 35px;
            list-style: none;
            /* 给box旋转也需要透视。干脆给li加 透视，让里面的子盒子都有透视效果 */
            perspective: 500px;
        }
        .box{
            position: relative;
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            transition: all .5s;
        }
        /* 底面变正面 */
        .box:hover{
            cursor: pointer;
            transform: rotateX(90deg);
        }
        /* 初始化 */
        .front,
        .bottom{
            position: absolute;
            left:0;
            top: 0;
            height: 100%;
            width: 100%;
            font-size: 20px;
            line-height: 35px;
            text-align: center;
        }
        .front{
            background-color: rgb(10, 170, 233);
            /* 把正面往前平移 */
            transform: translateZ(17.5px);
        }
        .bottom{
            /* display: none; */
            background-color: skyblue;
            /* rotateX(-90deg)向前扑倒90度,相当于完全朝下*/
            /*translateY(50%) 往下平移盒子高度的一半，此时front面就和bottom面完全垂直了，就像笔记本电脑一样*/
            /* 一定要先平移，再旋转 */
            transform: translateY(17.5px) rotateX(-90deg) 
        }
        

    </style>
</head>
<body>
    <ul>
        <li>
            <div class="box">
                <div class="front">我是FengXiao7</div>
                <div class="bottom">我喜欢看电影</div>
            </div>
        </li>
        <li>
            <div class="box">
                <div class="front">我是FengXiao7</div>
                <div class="bottom">我喜欢看电影</div>
            </div>
        </li>
        <li>
            <div class="box">
                <div class="front">我是FengXiao7</div>
                <div class="bottom">我喜欢看电影</div>
            </div>
        </li>
        <li>
            <div class="box">
                <div class="front">我是FengXiao7</div>
                <div class="bottom">我喜欢看电影</div>
            </div>
        </li>
        <li>
            <div class="box">
                <div class="front">我是FengXiao7</div>
                <div class="bottom">我喜欢看电影</div>
            </div>
        </li>
        <li>
            <div class="box">
                <div class="front">我是FengXiao7</div>
                <div class="bottom">我喜欢看电影</div>
            </div>
        </li>
        <li>
            <div class="box">
                <div class="front">我是FengXiao7</div>
                <div class="bottom">我喜欢看电影</div>
            </div>
        </li>
    </ul>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/22.gif" style="zoom: 100%"></img>

### 案例，旋转木马：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            padding: 0;
            margin: 0;
        }
        /* section也要转，视距写在body上 */
        body{
            perspective: 1000px;
        }
        section{
            position: relative;
            margin: 200px auto;
            width: 300px;
            height: 200px;
            transform-style: preserve-3d;
            background: url(media/pig.jpg) no-repeat;
            /* 36s匀速一圈 */
            animation: rotate 36s linear infinite;
        }
        /* 鼠标悬浮暂停动画 */
        section:hover{
            animation-play-state: paused;
        }
        @keyframes rotate{
            0%{
                transform: rotateY(0deg);
            }
            100%{
                transform: rotateY(360deg);
            }
        }
        section div {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url(media/dog.jpg) no-repeat;
        }
        section div:nth-child(1){
            transform: rotateY(0deg) translateZ(300px);
        }
        section div:nth-child(2) {
              /* 先旋转好了,再移动距离 */
            transform: rotateY(60deg) translateZ(300px);
        }
        /* 6张图，每次转60度 */
        section div:nth-child(3) {
            transform: rotateY(120deg) translateZ(300px);
        }
        section div:nth-child(4) {
            transform: rotateY(180deg) translateZ(300px);
        }
        section div:nth-child(5) {
            transform: rotateY(240deg) translateZ(300px);
        }
        section div:nth-child(6) {
            transform: rotateY(300deg) translateZ(300px);
        }
    </style>
</head>
<body>
    <section>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </section>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/23.gif" style="zoom: 100%"></img>

## 11.浏览器私有前缀

![image-20220316133925800](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316133925800.png)

# 移动端基础：

## 基础说明：

![image-20220316134403085](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316134403085.png)

![image-20220316134938947](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316134938947.png)

## 视口：

### 布局视口：

![image-20220316135247814](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316135247814.png)

### 视觉视口：

![image-20220316135419392](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316135419392.png)

### 理想视口：

![image-20220316135502522](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316135502522.png)

### 总结：

![image-20220316135529978](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316135529978.png)

### meta视口标签：

![image-20220316135754241](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316135754241.png)

![image-20220316140028479](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316140028479.png)

标准写法都这样写

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0,maximum-scale=1.0, minimum-scale=1.0, user-scalable=no">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>

<body>
    黑马程序员
</body>

</html>
```

## 二倍图：

### 物理像素和物理像素比：

手机物理像素比如果为2，那么开发PC的1px就是手机的2个像素

![image-20220316140522023](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316140522023.png)

![image-20220316140905768](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316140905768.png)

### 多倍图：

![image-20220316141318399](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316141318399.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* 我们需要一个50*50像素（css像素）的图片 直接放到我们的iphone8 里面会放大2倍  100* 100 就会模糊 */
        /* 我们采取的是 放一个 100* 100 图片  然后手动的把这个图片 缩小为 50* 50 （css像素） */
        /* 我们准备的图片 比我们实际需要的大小 大2倍，这就方式就是 2倍图 */
        
        img:nth-child(2) {
            width: 50px;
            height: 50px;
        }
    </style>
</head>

<body>
    <!-- 模糊的 -->
    <img src="images/apple50.jpg" alt="">
    <!-- 我们采取2倍图 -->
    <img src="images/apple100.jpg" alt="">
</body>

</html>
```

![image-20220316141806496](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316141806496.png)

## 背景图缩放：

![image-20220316142615330](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316142615330.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            width: 500px;
            height: 500px;
            border: 2px solid red;
            background: url(images/dog.jpg) no-repeat;
            /* background-size: 图片的宽度 图片的高度; */
            /* background-size: 500px 200px; */
            /* 1.只写一个参数 肯定是宽度 高度省略了  会等比例缩放 */
            /* background-size: 500px; */
            /* 2. 里面的单位可以跟%  相对于父盒子来说的 */
            /* background-size: 50%; */
            /* 3. cover 等比例拉伸 要完全覆盖div盒子  可能有部分背景图片显示不全 */
            /* background-size: cover; */
            /* 4. contain 高度和宽度等比例拉伸 当宽度 或者高度 铺满div盒子就不再进行拉伸了 可能有部分空白区域 */
            background-size: contain;
        }
    </style>
</head>

<body>
    <div></div>
    <p></p>
</body>

</html>
```

![image-20220316142413466](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316142413466.png)

![image-20220316142442507](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316142442507.png)

### 案例，背景图片二倍图：

相当于把原来100*100的背景图，缩放到50x50大小。然后用户在手机上(有视网膜屏幕)，又可以把它放大为100x100大小

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>

    <style>
        /* 1. 我们有一个 50 * 50的盒子需要一个背景图片，但是根据分析这个图片还是要准备2倍， 100*100 */
        /* 2. 我们需要把这个图片缩放一半，也就是 50*50  background-size*/
        
        div {
            width: 50px;
            height: 50px;
            border: 1px solid red;
            background: url(images/apple100.jpg) no-repeat;
            background-size: 50px 50px;
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

![image-20220316143308583](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316143308583.png)

![image-20220316143339534](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316143339534.png)

## 移动端页面选择：

### 单独移动端页面(主流)

![image-20220316143537819](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316143537819.png)

### 响应式兼容移动端

![image-20220316143714512](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316143714512.png)

## 移动端技术解决方案：

![image-20220316143853683](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316143853683.png)

![image-20220316144009864](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316144009864.png)

![image-20220316144312304](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316144312304.png)

![image-20220316144425625](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316144425625.png)

## 流式布局(百分比布局)：

![image-20220316144927320](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316144927320.png)

### 京东移动端案例：

#### 1.设置视口标签以及引入初始化样式

![image-20220316145843998](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316145843998.png)

#### 2.头部制作

```html
<header class="app">
        <ul>
            <li>
                <img src="images/close.png" alt="">
            </li>
            <li>
                <img src="images/logo.png" alt="">
            </li>
            <li>打开京东App，购物更轻松</li>
            <li>立即打开</li>
        </ul>
    </header>
```

```css
.app{
    height: 45px;
}
.app ul li{
    float: left;
    height: 45px;
    line-height: 45px;
    background-color: #333333;
    text-align: center;
    color: #fff;
}
.app ul li:nth-child(1){
    width: 8%;
}
.app ul li:nth-child(1) img{
    width: 10px;
}
.app ul li:nth-child(2){
    width: 10%;
}
.app ul li:nth-child(2) img {
    width: 30px;
    /*图片默认和文字基线居中，改回和中线居中*/
    vertical-align: middle;
}
.app ul li:nth-child(3){
    width: 57%;
}
.app ul li:nth-child(4){
    width: 25%;
    background-color: #F63515;
}
```

![image-20220316152444412](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316152444412.png)

#### 3.搜索栏制作

##### 框架：

```html
<!-- 搜索 -->
    <div class="search-wrap">
        <div class="search-btn"></div>
        <div class="search"></div>
        <div class="search-login"></div>
    </div>
```



```css
/* 搜索 */
.search-wrap{
    position: relative;
    height: 44px;
    /*这个地方用于解决塌陷问题*/
    overflow: hidden;
}
.search-btn{
    position: absolute;
    left: 0;
    top: 0;
    width: 40px;
    height: 44px;
    background-color: skyblue;
}
.search-login{
    position: absolute;
    right: 0;
    top: 0;
    width: 40px;
    height: 44px;
    background-color: skyblue;
}
/*搜索框完全撑开*/
.search{
    height: 30px;
    background-color: pink;
    margin: 0 50px;
    margin-top: 7px;
    border-radius: 15px;
}
```

![image-20220316183830149](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316183830149.png)

##### 填充：

```html
 <!-- 搜索 -->
    <div class="search-wrap">
        <!-- 三横图片 -->
        <div class="search-btn"></div>
        <!-- 搜索栏 -->
        <div class="search">
            <!-- JD logo -->
            <div class="jd-icon"></div>
            <!-- 放大镜 -->
            <div class="sou"></div>
        </div>
        <div class="search-login">登录</div>
    </div>
```



```css
/* 搜索 */
.search-wrap{
    position: relative;
    height: 44px;
    /*这个地方用于解决塌陷问题*/
    overflow: hidden;
}
.search-btn{
    position: absolute;
    left: 0;
    top: 0;
    width: 40px;
    height: 44px;
}
/*三横图片*/
.search-btn::before{
    content: "";
    display: block;
    width: 20px;
    height: 18px;
    background: url(../images/s-btn.png);
    /* 缩放 */
    background-size: 20px 18px;
    margin: 14px 0 0 15px;
}
/*登录*/
.search-login{
    position: absolute;
    right: 0;
    top: 0;
    width: 40px;
    height: 44px;
    line-height: 44px;
    text-align: center;
    color: #fff;
}
/*搜索框不给宽度，流式布局*/
.search{
    position: relative;
    height: 30px;
    background-color: #fff;
    margin: 0 50px;
    margin-top: 7px;
    border-radius: 15px;
}
/*JD logo*/
.jd-icon{
    position: absolute;
    width: 20px;
    height: 15px;
    top: 7px;
    left: 13px;
    background: url(../images/jd.png);
    background-size: 20px 15px;
}
/*JD logo旁边的小竖线*/
.jd-icon::after{
    position: absolute;
    display: block;
    content: "";
    width: 1px;
    height: 15px;
    top: 0px;
    right: -10px;
    background-color: #ccc;
}
/*放大镜图标，用的是2倍精灵图*/
.sou{
    position: absolute;
    width: 18px;
    height: 15px;
    top: 8px;
    left: 50px;
    background: url(../images/jd-sprites.png) no-repeat -81px 0;
    /* 缩放为原来精灵图宽度的一半，高度自适应 */
    background-size: 200px;
}
```



尤其注意放大镜用的是二倍精灵图，后期会大量使用

![image-20220316192632099](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316192632099.png)

![image-20220316192405109](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316192405109.png)

#### 4.滑动图

```html
<!-- 主体内容部分 -->
    <div class="main-content">
        <!-- 滑动图 -->
        <div class="slider">
            <img src="upload/banner.dpg" alt="">
        </div>
    </div>
```

需要把搜索栏模块变成固定定位，这样滑动图就可以占据搜索栏的位置了，而且向下滑动搜索栏也可以一直存在。

```css
/* 搜索 */
.search-wrap {
    /*改为固定定位*/
    position: fixed;
    /*这个地方用于解决塌陷问题*/
    overflow: hidden;
    width: 100%;
    height: 44px;
    min-width: 320px;
    max-width: 640px;
}
```



```css
/* 滑动图 */
.slider img {
    width: 100%;
}
```

![image-20220316193819480](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316193819480.png)

#### 5.品牌日

```html
<!-- 小家电品牌日 -->
        <div class="brand">
            <div>
                <a href="#">
                    <img src="upload/pic11.dpg" alt="">
                </a>
            </div>
            <div>
                <a href="#">
                    <img src="upload/pic22.dpg" alt="">
                </a>

            </div>
            <div>
                <a href="#">
                    <img src="upload/pic33.dpg" alt="">
                </a>
            </div>
        </div>
```

```css
/* 品牌日 */
.brand {
    overflow: hidden;
    border-radius: 10px 10px 0 0;
}
/*3张图片横向排列拼接*/
.brand div{
    float: left;
    width: 33.33%;
}
.brand div img{
    width: 100%;
}
```

![image-20220316195506897](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316195506897.png)

#### 6.nav导航栏

![image-20220316200753986](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316200753986.png)

```css
/* nav导航栏 */
nav a{
    float: left;
    width: 20%;
    text-align: center;
}
nav a img{
    width: 40px;
    margin: 10px 0;
}

nav span{
    display: block;
}
```

![image-20220316200824169](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316200824169.png)

##### 图片格式DPG,webp

![image-20220316200015751](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316200015751.png)

#### 7.新闻模块

```html
		<!-- 新闻模块 -->
        <div class="news">
            <a href="#">
                <img src="upload/new1.dpg" alt="">
            </a>
            <a href="#">
                <img src="upload/new2.dpg" alt="">
            </a>
            <a href="#">
                <img src="upload/new3.dpg" alt="">
            </a>
        </div>
```



```css
/* 新闻模块 */
.news a{
    float: left;
    /* 不用减边框了 */
    box-sizing: border-box;
}
.news a:nth-child(1){
    width: 50%;
}
/* 从第二个a开始数 */
.news a:nth-child(n+2){
    width: 25%;
    border-left: 1px solid #ccc;
}
.news img{
    width: 100%;
}
```

![image-20220316201737772](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316201737772.png)

## 移动端flex布局：

阮老师的教程：

[Flex 布局教程：语法篇 - 阮一峰的网络日志 (ruanyifeng.com)](https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

网友demo：

https://github.com/JailBreakC/flex-box-demo

推荐玩游戏：

[弹性框青蛙 - 学习CSS弹性框的游戏 (flexboxfroggy.com)](https://flexboxfroggy.com/)

![image-20220316202319963](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316202319963.png)

### 原理：

![image-20220316202722302](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316202722302.png)

![image-20220316202833427](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316202833427.png)

### 父项属性：

![image-20220316202954362](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316202954362.png)

#### flex-direction设置主轴方向:

![image-20220316203043903](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316203043903.png)

![image-20220316203134262](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316203134262.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            /* 给父级添加flex属性 */
            display: flex;
            width: 800px;
            height: 300px;
            background-color: pink;
            /* 默认的主轴是 x 轴 行 row  那么y轴就是侧轴喽 */
            /* 我们的元素是跟着主轴来排列的 */
            /* flex-direction: row; */
            /* 简单了解 翻转 */
            /* flex-direction: row-reverse; */
            /* 我们可以把我们的主轴设置为 y轴 那么 x 轴就成了侧轴 */
            flex-direction: column;
        }
        
        div span {
            width: 150px;
            height: 100px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <div>
        <span>1</span>
        <span>2</span>
        <span>3</span>
    </div>
</body>

</html>
```

![image-20220316203413025](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316203413025.png)

#### justify-content定义子项在主轴上的对齐方式:

还有一个

- `baseline`: 项目的第一行文字的基线对齐。

![image-20220316203524921](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316203524921.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            display: flex;
            width: 800px;
            height: 300px;
            background-color: pink;
            /* 默认的主轴是 x 轴 row */
            flex-direction: row;
            /* justify-content: 是设置主轴上子元素的排列方式 */
            /* justify-content: flex-start; */
            /* justify-content: flex-end; */
            /* 让我们子元素居中对齐 */
            /* justify-content: center; */
            /* 平分剩余空间 */
            /* justify-content: space-around; */
            /* 先两边贴边， 在分配剩余的空间 */
            justify-content: space-between;
        }
        
        div span {
            width: 150px;
            height: 100px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <div>
        <span>1</span>
        <span>2</span>
        <span>3</span>
        <span>4</span>
    </div>
</body>

</html>
```

![image-20220316204112737](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316204112737.png)

#### flex-wrap设置子元素是否换行：

![image-20220316204413236](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316204413236.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            display: flex;
            width: 600px;
            height: 400px;
            background-color: pink;
            /* flex布局中，默认的子元素是不换行的， 如果装不开，会缩小子元素的宽度，放到父元素里面  */
            /* flex-wrap: nowrap; */
            flex-wrap: wrap;
        }
        
        div span {
            width: 150px;
            height: 100px;
            background-color: purple;
            color: #fff;
            margin: 10px;
        }
    </style>
</head>

<body>
    <div>
        <span>1</span>
        <span>2</span>
        <span>3</span>
        <span>4</span>
        <span>5</span>
    </div>
</body>

</html>
```

![image-20220316204603652](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316204603652.png)

![image-20220316204735773](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316204735773.png)

#### align-items定义子项在侧轴上的对齐方式(单行)

**注意只适用于单行！**

![image-20220316204847880](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316204847880.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            display: flex;
            width: 800px;
            height: 400px;
            background-color: pink;
            /* 默认的主轴是 x 轴 row */
            flex-direction: row;
            justify-content: center;
            /* 我们需要一个侧轴居中 */
            /* 拉伸，但是子盒子不要给高度 */
            align-items: stretch;
            /* align-items: center; */
            /* align-content: center; */
        }
        
        div span {
            width: 150px;
            /* height: 100px; */
            background-color: purple;
            color: #fff;
            margin: 10px;
        }
    </style>
</head>

<body>
    <div>
        <span>1</span>
        <span>2</span>
        <span>3</span>
    </div>
</body>

</html>
```

![image-20220316205539013](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316205539013.png)

![image-20220316205723859](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316205723859.png)

#### align-content（设置侧轴子项排列方式）(多行)

**注意在单行的情况下是没用的！**也就是说当flex-wrap为nowrap就不起左右

![image-20220316205943270](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316205943270.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            display: flex;
            width: 800px;
            height: 400px;
            background-color: pink;
            /* 换行 */
            flex-wrap: wrap;
            /* 因为有了换行，此时我们侧轴上控制子元素的对齐方式我们用 align-content */
            /* align-content: flex-start; */
            /* align-content: center; */
            /* align-content: space-between; */
            align-content: space-around;
        }
        
        div span {
            width: 150px;
            height: 100px;
            background-color: purple;
            color: #fff;
            margin: 10px;
        }
    </style>
</head>

<body>
    <div>
        <span>1</span>
        <span>2</span>
        <span>3</span>
        <span>4</span>
        <span>5</span>
        <span>6</span>
    </div>
</body>

</html>
```

![image-20220316210613437](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316210613437.png)

#### align-content与align-items区别

![image-20220316210422748](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220316210422748.png)

#### flex-flow（flex-direction和flex-wrap的复合属性）:

![image-20220317105927017](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317105927017.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            display: flex;
            width: 600px;
            height: 300px;
            background-color: pink;
            /* flex-direction: column;
            flex-wrap: wrap; */
            /* 把设置主轴方向和是否换行（换列）简写 */
            flex-flow: column wrap;
        }
        
        div span {
            width: 150px;
            height: 100px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <div>
        <span>1</span>
        <span>2</span>
        <span>3</span>
        <span>4</span>
        <span>5</span>
    </div>
</body>

</html>
```

![image-20220317110108266](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317110108266.png)

### 子项属性：

![image-20220317110346746](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317110346746.png)

#### flex子项占的份数：

![image-20220320125307452](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320125307452.png)

![image-20220317111020953](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317111020953.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* 我们在section里面写之前京东流失布局的搜索栏案例 */
        section {
            display: flex;
            width: 60%;
            height: 150px;
            background-color: pink;
            margin: 0 auto;
        }
        /* 第一个盒子定死 */
        section div:nth-child(1) {
            width: 100px;
            height: 150px;
            background-color: red;
        }
        /* 第二个盒子是搜索框，自适应。然后它吃一份 */
        section div:nth-child(2) {
            flex: 1;
            background-color: green;
        }
        /* 第三个盒子定死 */
        section div:nth-child(3) {
            width: 100px;
            height: 150px;
            background-color: blue;
        }
        
        
        p {
            display: flex;
            width: 60%;
            height: 150px;
            background-color: pink;
            margin: 100px auto;
        }
        /* 每个span都吃一份 */
        p span {
            flex: 1;
        }
        /* 但是第二个span吃两份 */
        p span:nth-child(2) {
            flex: 2;
            background-color: purple;
        }
    </style>
</head>

<body>
    <section>
        <div></div>
        <div></div>
        <div></div>
    </section>
    <p>
        <span>1</span>
        <span>2</span>
        <span>3</span>
    </p>
</body>

</html>
```

![image-20220317111435972](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317111435972.png)

#### align-self控制子项自己在侧轴的排列方式：

![image-20220320125403025](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320125403025.png)

![image-20220317111903174](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317111903174.png)

#### order定义子项的排列顺序：

![image-20220317112026189](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317112026189.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            display: flex;
            width: 80%;
            height: 300px;
            background-color: pink;
            /* 让三个子盒子沿着侧轴底侧对齐 */
            /* align-items: flex-end; */
            /* 我们想只让3号盒子下来底侧 */
        }
        
        div span {
            width: 150px;
            height: 100px;
            background-color: skyblue;
            margin-right: 5px;
        }
        /* 让2号盒子排在1号盒子前边 */
        div span:nth-child(2) {
            /* 默认是0   -1比0小所以在前面 */
            order: -1;
        }
        /* 只让三号盒子在侧轴上倒排，相当于掉了下来 */
        div span:nth-child(3) {
            align-self: flex-end;
        }
    </style>
</head>

<body>
    <div>
        <span>1</span>
        <span>2</span>
        <span>3</span>
    </div>
</body>

</html>
```

![image-20220317112349343](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317112349343.png)

#### flex-grow子项放大比例:

![image-20220320124248362](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320124248362.png)

#### flex-shrink子项缩小比例：

![image-20220320124528117](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320124528117.png)

#### flex-basis：

![image-20220320125105599](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320125105599.png)

### 携程网首页案例：

我们采用单独移动端页面，flex布局实现

最终效果：

![image-20220317155311412](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317155311412.png)

![image-20220317113006351](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317113006351.png)

#### 1.初始化

```css
body {
    max-width: 540px;
    min-width: 320px;
    margin: 0 auto;
    font: normal 14px/1.5 Tahoma, "Lucida Grande", Verdana, "Microsoft Yahei", STXihei, hei;
    color: #000;
    background: #f2f2f2;
    overflow-x: hidden;
    -webkit-tap-highlight-color: transparent;
}

ul {
    list-style: none;
    margin: 0;
    padding: 0;
}

a {
    text-decoration: none;
    color: #222;
}

div {
    box-sizing: border-box;
}



```

#### 2.搜索栏

##### 布局：

```html
<!-- 搜索模块 -->
    <div class="search-index">
        
    </div>
```

```css
/* 搜索模块 */
.search-index{
    /* 固定定位跟父级没有关系 它以屏幕为准 */
    position: fixed;
    top: 0;
    /* left和translateX搭配实现居中
        详见"有定位的盒子如何居中？"这一节
    */
    left: 50%;
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
    /* 固定的盒子应该有宽度 */
    width: 100%;
    height: 44px;
    min-width: 320px;
    max-width: 540px;
    background-color: skyblue;
}
```

![image-20220317114933107](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317114933107.png)

##### 填充：

```html
<!-- 搜索模块 -->
    <div class="search-index">
        <div class="search">搜索:目的地/酒店/景点/航班号</div>
        <a href="#" class="user">我 的</a>
    </div>
```

```css
/* 搜索模块 */
.search-index{
    display: flex;
    /* 固定定位跟父级没有关系 它以屏幕为准 */
    position: fixed;
    top: 0;
    /* left和translateX搭配实现居中
        详见"有定位的盒子如何居中？"这一节
    */
    left: 50%;
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
    /* 固定的盒子应该有宽度 */
    width: 100%;
    height: 44px;
    min-width: 320px;
    max-width: 540px;
    /* 防止滑动时，其他盒子把它盖住。有背景色就不怕 */
    background-color: #F6F6F6;
    border-top: 1px solid #ccc;
    border-bottom: 1px solid #ccc;
}
/* 搜索栏  动态缩放宽度*/
.search{
    position: relative;
    flex: 1;
    height: 26px;
    /* 这里垂直居中是26-(1*2)即2个边框高度 */
    /* 因为用到了CSS3的border-box模型 */
    line-height: 24px;
    padding-left: 25px;
    margin: 5px 0px;
    font-size: 12px;
    color: #666;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 1px 1px 3px 1px rgb(0 0 0 / 30%);
    /* background-color: pink; */
}
/* 伪元素插图 */
.search::before{
    content: "";
    position: absolute;
    width: 15px;
    height: 15px;
    top: 5px;
    left: 5px;
    /* 二倍精灵图 */
    background: url(../images/sprite.png) no-repeat -59px -279px;
    background-size: 104px;
}
/* 用户  是定死大小的*/
.user{
    position: relative;
    padding-top: 24px;
    width: 44px;
    height: 44px;
    font-size: 12px;
    text-align: center;
    color: #2eaae0;
    /* background-color: skyblue; */
}
/* 伪元素插图 */
.user::before{
    position: absolute;
    content: "";
    display: block;
    top: 2px;
    left: 10px;
    width: 25px;
    height: 25px;
    /* 二倍精灵图 */
    background: url(../images/sprite.png) no-repeat -58px -193px;
    background-size: 104px;
}
```

![image-20220317123145734](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317123145734.png)

#### 3.焦点图

```html
<!-- 焦点图 -->
    <div class="focus">
        <img src="upload/focus.jpg" alt="">
    </div>
```

```css
/* 焦点图 */
.focus{
    padding-top: 44px;
}
.focus img{
    width: 100%;
}
```

![image-20220317155801545](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317155801545.png)

#### 4.局部导航栏

##### flex居中技巧：

![image-20220317161122964](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317161122964.png)

```html
<!-- 局部导航栏 -->
    <ul class="local-nav">
        <li>
            <a href="#" title="景点·玩乐">
                <span class="local-nav-icon-icon1"></span>
                <span>景点·玩乐</span>
            </a>
        </li>
        <li>
            <a href="#" title="景点·玩乐">
                <span class="local-nav-icon-icon2"></span>
                <span>景点·玩乐</span>
            </a>
        </li>
        <li>
            <a href="#" title="景点·玩乐">
                <span class="local-nav-icon-icon3"></span>
                <span>景点·玩乐</span>
            </a>
        </li>
        <li>
            <a href="#" title="景点·玩乐">
                <span class="local-nav-icon-icon4"></span>
                <span>景点·玩乐</span>
            </a>
        </li>
        <li>
            <a href="#" title="景点·玩乐">
                <span class="local-nav-icon-icon5"></span>
                <span>景点·玩乐</span>
            </a>
        </li>
    </ul>
```



```css
/* 导航栏 */
.local-nav{
    display: flex;
    height: 64px;
    background-color: #fff;
    border-radius: 8px;
}
.local-nav li{
    flex: 1;
}
.local-nav a{
    display: flex;
    flex-direction: column;
    /* 侧轴居中对齐 因为是单行 */
    align-items: center;
    margin-top: 8px;
    font-size: 12px;
    /* background-color: skyblue; */
}
.local-nav li [class^="local-nav-icon"]{
    width: 32px;
    height: 32px;
    /* background-color: pink; */
    /* 二倍精灵图 */
    background: url(../images/localnav_bg.png) no-repeat 0 0;
    background-size: 32px;
}
/*权重和上边一样，就近原则覆盖掉*/
.local-nav li .local-nav-icon-icon2{
    background-position: 0 -32px;
}
.local-nav li .local-nav-icon-icon3{
    background-position: 0 -64px;
}
.local-nav li .local-nav-icon-icon4{
    background-position: 0 -96px;
}
.local-nav li .local-nav-icon-icon5{
    background-position: 0 -128px;
}
```

![image-20220317162913501](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317162913501.png)

#### 5.主导航栏

##### 布局：

![image-20220317165127941](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317165127941.png)

```css
/* 主导航栏nav */
nav{
    display: flex;
    height: 270px;
    justify-content: space-between;
    flex-direction: column;
    background-color: skyblue;
}
/* 主导航栏，有3个分栏nav-common */
.nav-common{
    display: flex;
    height: 88px;
    justify-content: space-between;
    background-color: pink;
}
/* 每个nav-common 又分成3个更小分栏,其中左侧分栏nav-items1不再分了 */
/* 中间和右边各自占一个nav-items2 */
.nav-items1{
    flex:1;
    background-color: yellow;
}
.nav-items2{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex:1;
    background-color: yellow;
}
/* 每个nav-items2又可以上下平均分成两块nav-items3*/
.nav-items3{
    display: block;
    flex: 1;
    background-color: red;
}
```

![image-20220317165146154](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317165146154.png)

##### 填充：

html和上边一样

```css
/* 主导航栏nav */
nav{
    display: flex;
    height: 270px;
    margin-top: 4px;
    justify-content: space-between;
    flex-direction: column;
    /* background-color: skyblue; */
}
/* 主导航栏，有3个分栏nav-common */
.nav-common{
    display: flex;
    height: 88px;
    justify-content: space-between;
}
.nav-common:nth-child(1){
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
    /* 渐变色 */
    background: -webkit-linear-gradient(left, #FA5A55, #FA994D);
}
.nav-common:nth-child(2){
    background: -webkit-linear-gradient(left, #4B90ED, #53BCED);
}
.nav-common:nth-child(3){
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
    background: -webkit-linear-gradient(left, #34C2A9, #6CD559);
}
/* 每个nav-common 又分成3个更小分栏,其中左侧分栏nav-items1不再分了 */
/* 中间和右边各自占一个nav-items2 */
.nav-items1{
    display: flex;
    flex:1;
    /*这里用到了局部导航栏里居中文字的手法 */
    flex-direction: column;
    /* 不要忘了方位名词写法 */
    /*三倍图*/
    background: url(../images/hotel.png) no-repeat bottom center;
    background-size: 121px;
}
.nav-items1 a{
    padding-top: 13px;
    text-align: center;
    font-size: 14px;
    color: #fff;
    /* 文字阴影 */
    text-shadow: 1px 1px rgba(0, 0, 0, .2);
}
.nav-items2{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex:1;
}
/* 每个nav-items2又可以上下平均分成两块nav-items3*/
.nav-items3{
    flex: 1;
    line-height: 44px;
    text-align: center;
    font-size: 14px;
    color: #fff;
    text-shadow: 1px 1px rgba(0, 0, 0, .2);
    /*每个nav-items3都给个左边框*/
    border-left: 1px solid #fff;
}
.nav-items3:nth-child(1){
    /*第一个nav-items3给个下边框*/
    border-bottom: 1px solid #fff;
}
```

![image-20220317171136449](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317171136449.png)

### 插播背景色线性渐变效果:

![image-20220317172632111](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317172632111.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            width: 600px;
            height: 200px;
            /* 背景渐变必须添加浏览器私有前缀 */
            /* background: -webkit-linear-gradient(left, red, blue); */
            /*不写方向默认top到bottom*/
            /* background: -webkit-linear-gradient(red, blue); */
            background: -webkit-linear-gradient(top left, red, blue);
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

![image-20220317172316998](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317172316998.png)

6.侧导航栏

这部分和局部导航栏很像，只不过多个换行。

![image-20220317174211583](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317174211583.png)

```css
/* 侧导航栏 */
.subnav-entry{
    display: flex;
    border-radius: 8px;
    background-color: #fff;
    margin: 0 4px;
    flex-wrap: wrap;
    padding: 5px 0;
}
.subnav-entry li{
    /* 相对于父盒子来说可以写百分比 */
    flex: 20%;
}
.subnav-entry a{
    display: flex;
    flex-direction: column;
    align-items: center;
}
.subnav-entry-icon{
    width: 28px;
    height: 28px;
    margin-top: 8px;
    background: url(../images/subnav-bg.png) no-repeat;
    background-size: 28px;
}
```

![image-20220317174317752](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317174317752.png)

#### 6.销售模块

![image-20220317191746306](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317191746306.png)

```css
/* 销售模块 */
.sales-box{
    border-top: 1px solid #bbb;
    background-color: #fff;
    margin: 4px;
}
.sales-hd{
    position: relative;
    height: 44px;
    border-bottom: 1px solid #ccc;
}
/* 这个地方主要用于搜索引擎优化 */
.sales-hd h2 {
    position: relative;
    text-indent: -999px;
    overflow: hidden;
}
/* 图片还是放在伪元素里，还是是二倍图 */
.sales-hd h2::after {
    /* 这里用子绝父相调整位置 */
    position: absolute;
    top: 5px;
    left: 8px;
    content: "";
    width: 79px;
    height: 15px;
    background: url(../images/hot.png) no-repeat 0 -20px;
    background-size: 79px;
}
/* a为行内元素 */
/*more不用给大小，用文字撑开就行*/
.more {
    position: absolute;
    right: 5px;
    top: 0px;
    background: -webkit-linear-gradient(left, #FF506C, #FF6BC6);
    border-radius: 15px;
    padding: 3px 20px 3px 10px;
    color: #fff;
}
/* 这里面的小三角，我们还是用边框做 */
/* 详见小三角旋转案例 */
.more::after {
    content: "";
    position: absolute;
    top: 9px;
    right: 9px;
    width: 7px;
    height: 7px;
    border-top: 2px solid #fff;
    border-right: 2px solid #fff;
    transform: rotate(45deg);
}
.row {
    display: flex;
}

.row a {
    flex: 1;
    border-bottom: 1px solid #eee;
}

.row a:nth-child(1) {
    border-right: 1px solid #eee;
}

.row a img {
    width: 100%;
}
```

![image-20220317191857143](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317191857143.png)

## 移动端rem布局

### 1.rem单位

![image-20220317192927404](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317192927404.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        html {
            font-size: 15px;
        }
        div {
            font-size: 12px;
            width: 15rem;
            height: 15rem;
            background-color: purple;
        }
        p {
            /* 1. em相对于父元素 的字体大小来说的 */
            /* width: 10em;
            height: 10em; */
            /* 2. rem 相对于 html元素 字体大小来说的 */
            width: 10rem;
            height: 10rem;
            background-color: pink;
            /* 3.rem的优点就是可以通过修改html里面的文字大小来改变页面中元素的大小可以整体控制 */
        }
    </style>
</head>

<body>
    <div>
        <p></p>
    </div>

</body>

</html>
```

![image-20220317193041293](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317193041293.png)

### 2.媒体查询

![image-20220317193258227](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317193258227.png)

#### 语法规范：

![image-20220317193430169](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317193430169.png)

##### mediatype类型：

![image-20220317193519768](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317193519768.png)

##### 关键字：

![image-20220317193629991](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317193629991.png)

##### 媒体类型：

![image-20220317193657351](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317193657351.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* 这句话的意思就是： 在我们屏幕上 并且 最大的宽度是 800像素 设置我们想要的样式 */
        /* max-width 小于等于800 */
        /* 媒体查询可以根据不同的屏幕尺寸在改变不同的样式 */
        
        @media screen and (max-width: 800px) {
            body {
                background-color: pink;
            }
        }
        
        @media screen and (max-width: 500px) {
            body {
                background-color: purple;
            }
        }
    </style>
</head>

<body>

</body>

</html>
```

小于500紫色，500-800粉色，800以上无色

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/24.gif" style="zoom: 100%"></img>

#### 案例：

![image-20220317194510765](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317194510765.png)

![image-20220317195622548](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317195622548.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* 1. 媒体查询一般按照从大到小或者 从小到大的顺序来 */
        /* 2. 小于540px 页面的背景颜色变为蓝色 */
        
        @media screen and (max-width: 539px) {
            body {
                background-color: blue;
            }
        }
        /* 3. 540 ~ 970 我们的页面颜色改为 绿色 */
        /* @media screen and (min-width: 540px) and (max-width: 969px) {
            body {
                background-color: green;
            }
        } */
        
        @media screen and (min-width: 540px) {
            body {
                background-color: green;
            }
        }
        /* 4. 大于等于970 我们页面的颜色改为 红色 */
        
        @media screen and (min-width: 970px) {
            body {
                background-color: red;
            }
        }
        /* 5. screen 还有 and 必须带上不能省略的 */
        /* 6. 我们的数字后面必须跟单位  970px   这个 px 不能省略的 */
    </style>
</head>

<body>

</body>

</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/25.gif" style="zoom: 100%"></img>

### 3.媒体查询+rem实现元素动态大小变化

![image-20220317195857260](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317195857260.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* html {
            font-size: 100px;
        } */
        /* 从小到大的顺序 */
        @media screen and (min-width:320px) {
            html{
                font-size: 50px;
            }
        }
        @media screen and (min-width:640px) {
            html{
                font-size: 100px;
            }
        }
        .top{
            margin: 50x auto;
            height: 1rem;
            font-size: 0.5rem;
            background-color: skyblue;   
        }
    </style>
</head>
<body>
    <div class="top">购物车</div>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/26.gif" style="zoom: 100%"></img>

### 4.引入资源

![image-20220317201333590](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317201333590.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        /* 当我们屏幕大于等于 640px以上的，我们让div 一行显示2个 */
        /* 当我们屏幕小于640 我们让div一行显示一个 */
        /* 一个建议： 我们媒体查询最好的方法是从小到大 */
        /* 引入资源就是 针对于不同的屏幕尺寸 调用不同的css文件 */
    </style>
    <link rel="stylesheet" href="style320.css" media="screen and (min-width: 320px)">
    <link rel="stylesheet" href="style640.css" media="screen and (min-width: 640px)">
</head>

<body>
    <div>1</div>
    <div>2</div>
</body>

</html>
```

```css
/*style320.css*/
div {
    width: 100%;
    height: 100px;
}

div:nth-child(1) {
    background-color: pink;
}

div:nth-child(2) {
    background-color: purple;
}
```

```css
/*style640.css*/
div {
    float: left;
    width: 50%;
    height: 100px;
}

div:nth-child(1) {
    background-color: pink;
}

div:nth-child(2) {
    background-color: purple;
}
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/27.gif" style="zoom: 100%"></img>

### 5.less：

#### css弊端：

![image-20220317202100426](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317202100426.png)

#### 基本使用：

Less是一门CSS预处理语言，它扩展了CSS的动态属性

![image-20220317202259752](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317202259752.png)

##### Less变量：

![image-20220317202613452](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317202613452.png)

```less
// 定义一个粉色的变量
@color: pink;  
// 错误的变量名  @1color   @color~@#
// 变量名区分大小写  @color  和  @Color 是两个不同的变量
// 定义了一个 字体为14像素的变量
@font14: 14px;
body {
    background-color: @color;
}
div {
    color: @color;
    font-size: @font14;
}
a {
    font-size: @font14;
}

```

##### Less编译：

![image-20220317202934918](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317202934918.png)

##### Easy LESS插件：

装一个插件吧。装了以后，写less保存后，会自动生成对应同名的css文件

![image-20220317203001937](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317203001937.png)

##### Less嵌套：

![image-20220317203749487](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317203749487.png)

![image-20220317203803219](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317203803219.png)

```less
.header {
    width: 200px;
    height: 200px;
    background-color: pink;
    // 1. less嵌套 子元素的样式直接写到父元素里面就好了
    a {
        color: red;
        // 2. 如果有伪类、交集选择器、 伪元素选择器 我们内层选择器的前面需要加&
        &:hover {
            color: blue;
        }
    }
}
.nav {
    .logo {
        color: green;
    }
    &::before {
        content: "";
    }
}
```

##### Less运算：

![image-20220317204122126](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317204122126.png)

![image-20220317204447887](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317204447887.png)

```less
@baseFont: 50px;
html {
    font-size: @baseFont;
}
@border: 5px + 5;
div {
    width: 200px - 50;
    height: (200px + 50px ) * 2;
    border: @border solid red;
    background-color: #666 - #222;
}
img {
    width: 82rem / @baseFont;
    height: 82rem / @baseFont;
}
// 1. 我们运算符的左右两侧必须敲一个空格隔开
// 2. 两个数参与运算  如果只有一个数有单位，则最后的结果就以这个单位为准
// 3. 两个数参与运算，如果2个数都有单位，而且不一样的单位 最后的结果以第一个单位为准

```

### 6.rem适配方案

![image-20220317204721265](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317204721265.png)

![image-20220317204812979](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317204812979.png)

![image-20220317204924016](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317204924016.png)

#### 适配方案1：

![image-20220317205112295](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317205112295.png)

![image-20220317205327051](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317205327051.png)

![image-20220317205810512](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220317205810512.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        @media screen and (min-width: 320px) {
            html {
                font-size: 21.33px;
            }
        }
        
        @media screen and (min-width: 750px) {
            html {
                font-size: 50px;
            }
        }
        
        div {
            width: 2rem;
            height: 2rem;
            background-color: pink;
        }
        /* 1. 首先我们选一套标准尺寸 750为准 
        2. 我们用屏幕尺寸 除以 我们划分的份数 得到了 html 里面的文字大小 但是我们知道不同屏幕下得到的文字大小是不一样的 */
        /* 3. 页面元素的rem值 =  页面元素在 750像素的下px值 / html 里面的文字大小 */
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

### 7.苏宁首页案例：

#### 1.common.less制作：

![image-20220318102232496](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318102232496.png)

```less
// 设置常见的屏幕尺寸 修改里面的html文字大小
a {
    text-decoration: none;
}
// 一定要写到最上面
html {
    font-size: 50px;
}
// 我们此次定义的划分的份数 为 15
@no: 15;
// 320
@media screen and (min-width: 320px) {
    html {
        font-size: (320px / @no);
    }
}
// 360
@media screen and (min-width: 360px) {
    html {
        font-size: (360px / @no);
    }
}
// 375 iphone 678
@media screen and (min-width: 375px) {
    html {
        font-size: (375px / @no);
    }
}

// 384
@media screen and (min-width: 384px) {
    html {
        font-size: (384px / @no);
    }
}

// 400
@media screen and (min-width: 400px) {
    html {
        font-size: (400px / @no);
    }
}
// 414
@media screen and (min-width: 414px) {
    html {
        font-size: (414px / @no);
    }
}
// 424
@media screen and (min-width: 424px) {
    html {
        font-size: (424px / @no);
    }
}

// 480
@media screen and (min-width: 480px) {
    html {
        font-size: (480px / @no);
    }
}

// 540
@media screen and (min-width: 540px) {
    html {
        font-size: (540px / @no);
    }
}
// 720
@media screen and (min-width: 720px) {
    html {
        font-size: (720px / @no);
    }
}

// 750
@media screen and (min-width: 750px) {
    html {
        font-size: (750px / @no);
    }
}


```

#### 2.导入样式：

![image-20220318103333183](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318103333183.png)

新建index.less导入common（可以不写后缀）

ctrl+s后，index.css里面就有common.css的内容了(在装了easy lessc插件的前提下)

```less
// 首页的样式less文件
@import "common";
// @import 导入的意思 可以把一个样式文件导入到另外一个样式文件里面
// link 是把一个 样式文件引入到 html页面里面
```

html引入时只需要导入index.css就行

#### 3.顶部搜索栏：

##### 布局：

```html
<!-- 顶部搜索框 -->
    <div class="search-content">
        <a href="#" class="classify">1</a>
        <div class="search">2</div>
        <a href="#" class="login">3</a>
    </div>
```

```less
// 页面元素rem计算公式： 页面元素的px / html 字体大小 50
// search-content
@baseFont: 50;
.search-content{
    display: flex;
    position: fixed;
    top: 0px;
    left: 50%;
    transform: translateX(-50%);
    width: 15rem;
    height: (88rem / @baseFont);
    background-color: #FFC001;
    .classify{
        width: (44rem / @baseFont);
        height: (70rem / @baseFont);
        background-color: pink;
    }
    .search{
        flex: 1;
        background-color: skyblue;
    }
    .login{
        width: (75rem / @baseFont);
        height: (70rem / @baseFont);
        background-color: red;
    }
}
```

![image-20220318114228952](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318114228952.png)

##### 填充：

```html
<!-- 顶部搜索框 -->
    <div class="search-content">
        <a href="#" class="classify"></a>
        <div class="search">
            <form action="">
                <input type="search" value="厨卫保暖季 哒哒哒">
            </form>
        </div>
        <a href="#" class="login">登录</a>
    </div>
```

```less
//新版本easyLess要求必须用()括起来计算式子
.search-content{
    display: flex;
    position: fixed;
    top: 0px;
    left: 50%;
    transform: translateX(-50%);
    width: 15rem;
    height: (88rem / @baseFont);
    background-color: #FFC001;
    .classify{
        width: (44rem / @baseFont);
        height: (70rem / @baseFont);
        // background-color: pink;
        margin: (11rem / @baseFont) (25rem / @baseFont) (7rem / @baseFont) (24rem / @baseFont);
        background: url(../images/classify.png) no-repeat;
        // 背景缩放
        background-size: (44rem / @baseFont) (70rem / @baseFont);
    }
    .search{
        flex: 1;
        // background-color: skyblue;
        input {
            // 去除input获取焦点时，边框变色
            outline: none;
            width: 100%;
            // 去除input边框
            border: 0;
            height: (66rem / @baseFont);
            border-radius: (33rem / @baseFont);
            background-color:#FFF2CC;
            margin-top: (12rem / @baseFont);
            font-size: (25rem / @baseFont);
            padding-left: (55rem / @baseFont);
            color: #757575;
        }
        
    }
    .login{
        width: (75rem / @baseFont);
        height: (70rem / @baseFont);
        line-height: (70rem / @baseFont);
        margin: (10rem / @baseFont);
        // background-color: red;
        font-size: (25rem / @baseFont);
        text-align: center;
        color: #fff;
    }
}
```

#### 4.banner和ad部分

```html
<!-- banner部分 -->
     <div class="banner">
        <img src="upload/banner.gif" alt="">
    </div>
    <!-- 广告部分 -->
    <div class="ad">
        <a href="#"><img src="upload/ad1.gif" alt=""></a>
        <a href="#"><img src="upload/ad2.gif" alt=""></a>
        <a href="#"><img src="upload/ad3.gif" alt=""></a>
    </div>
```

```less
// banner
.banner {
    width: (750rem / @baseFont);
    height: (368rem / @baseFont);
    img {
        width: 100%;
        height: 100%;
    }
}
// ad 3张图片平凑而成，有bug。见需要注意的地方第九点
.ad {
    display: flex;
    a {
        flex: 1;
        img {
            width: 100%;
        }
    }
}
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/28.gif" style="zoom: 100%"></img>

#### 5.nav导航栏部分

![image-20220318124226922](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318124226922.png)

```less
// nav
nav {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
    width: (750rem / @baseFont);
    //我们这里还是采用flex居中对齐的技巧
    a {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: (150rem / @baseFont);
        height: (140rem / @baseFont);
        img {
            width: (82rem / @baseFont);
            height: (82rem / @baseFont);
        }
        span {
            margin-top: (10rem / @baseFont);
            font-size: (25rem / @baseFont);
            color: #333;
        }
    }
}
```

![image-20220318124243795](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318124243795.png)

### 适配方案2：flexible.js+rem

![image-20220318131925655](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318131925655.png)

#### 安装插件：px to rem & rpx (cssrem)

![image-20220318134244474](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318134244474.png)

#### 基础搭建：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, user-scalable=no,initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">

    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="css/normalize.css">
    <link rel="stylesheet" href="css/index.css">
    <!-- 引入我们的flexible.js 文件 -->
    <script src="js/flexible.js"></script>
    <title>Document</title>
</head>

<body>
    <div class="search-content">
        
    </div>
</body>

</html>
```



```css
body {
    min-width: 320px;
    max-width: 750px;
    /* flexible 给我们划分了 10 等份 */
    width: 10rem;
    margin: 0 auto;
    line-height: 1.5;
    font-family: Arial, Helvetica;
    background: #f2f2f2;
}

a {
    text-decoration: none;
    font-size: .333333rem;
}

/* 如果我们的屏幕超过了 750px  
那么我们就按照 750设计稿来走 不会让我们页面超过750px */

@media screen and (min-width: 750px) {
    /*因为flexable.js权重更高，我们增大权重即可*/
    html {
        font-size: 75px!important;
    }
}

.search-content {
    display: flex;
    position: fixed;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 10rem;
    height: 1.173333rem;
    background-color: #FFC001;
}

```

#### 完善：

```html
<div class="search-content">
        <a href="#" class="classify"></a>
        <div class="search">
            <form action="">
                <input type="search" value="rem适配方案2很开心哦">
            </form>
        </div>
        <a href="#" class="login">登录</a>
    </div>
```



```css
.search-content {
    display: flex;
    position: fixed;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 10rem;
    height: 1.173333rem;
    background-color: #FFC001;
}
.classify {
    width: .586667rem;
    height: .933333rem;
    margin: .146667rem .333333rem .133333rem;
    background: url(../images/classify.png) no-repeat;
    background-size: .586667rem .933333rem;
}

.search {
    flex: 1;
}

.search input {
    outline: none;
    border: 0;
    width: 100%;
    height: .88rem;
    font-size: .333333rem;
    background-color: #FFF2CC;
    margin-top: .133333rem;
    border-radius: .44rem;
    color: #757575;
    padding-left: .733333rem;
}

.login {
    width: 1rem;
    height: .933333rem;
    margin: .133333rem;
    color: #fff;
    text-align: center;
    line-height: .933333rem;
    font-size: .333333rem;
}

```

![image-20220318135400640](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220318135400640.png)

### 两种适配方案对比

#### less+rem+媒体查询+(插件easyLess)：

需要自己写很多媒体查询，变化需要到一定范围内才可以看见。比如屏幕320px-360px样式大小不会改变。

但是less逻辑性很强，便于后期维护。

#### flexable.js+rem+（插件cssrem）

这种方案样式大小随页面大小而改动。需要自己修改cssroot基准，如果有额外需求，比如超过750px的屏幕，一律

为750px，还是要自己写媒体查询的。二个就是虽然自己写的很爽，但是很难维护

## bootstrap响应式布局：

[Bootstrap中文网 (bootcss.com)](https://www.bootcss.com/)

![image-20220320135109951](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320135109951.png)

![image-20220320135450800](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320135450800.png)

### 响应式导航：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            padding: 0;
            margin: 0;
        }
        li{
            list-style: none;
        }
        .container{
            width: 750px;
            background-color: pink;
            margin: 0 auto;
        }
        .container ul li{
            float: left;
            height: 30px;
            width: calc(750px / 9);
            background-color: skyblue;
        }
        @media screen and (max-width:767px) {
            .container{
                width: 100%;
            }
            .container ul li{
                width: 33.33%;
            }
        }

    </style>
</head>
<body>
    <div class="container">
        <ul>
            <li>导航栏</li>
            <li>导航栏</li>
            <li>导航栏</li>
            <li>导航栏</li>
            <li>导航栏</li>
            <li>导航栏</li>
            <li>导航栏</li>
            <li>导航栏</li>
            <li>导航栏</li>
        </ul>
    </div>
</body>
</html>
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/66.gif" style="zoom: 100%"></img>

### 布局容器：

![image-20220320142607051](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320142607051.png)

### 栅格系统：![image-20220320142939524](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220320142939524.png)

# 品优购

## 1.ico图标

转化工具

[制作ico图标 | 在线ico图标转换工具 方便制作favicon.ico - 比特虫 - Bitbug.net](https://www.bitbug.net/)

## 2.SEO优化

### title

![image-20220510235811367](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220510235811367.png)

![image-20220510235916567](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220510235916567.png)

### description

![image-20220510235941561](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220510235941561.png)

### keywords

![image-20220511000208444](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220511000208444.png)

![image-20220511000147093](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220511000147093.png)

## 3.LOGO SEO优化



![image-20220511000351493](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220511000351493.png)

![image-20220511000435995](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220511000435995.png)
