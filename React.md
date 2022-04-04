# 版本：

笔记里提到的：

使用的所谓旧版☞v16.8.4

所谓新版☞v17.0.1

2022年3月，官方已更新至18.0.0，笔记里不会涉及到最新版内容。

如果涉及到，我会在后续添加新的笔记内容

# 资料：

b友分享

https://pan.baidu.com/s/1hS746pu37B78glu5u-TaPw 

提取码：1dz2

# 官网：

[React 官方中文文档 – 用于构建用户界面的 JavaScript 库 (reactjs.org)](https://zh-hans.reactjs.org/)

脚手架：（无中文）

[Create React App (create-react-app.dev)](https://create-react-app.dev/)

路由：

[React Router: Declarative Routing for React.js (docschina.org)](https://react-router.docschina.org/)

# react_basic:

## 1.hello react:

引入核心库，多了React。引入react-dom，多了ReactDOM

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>hello_react</title>
</head>
<body>
	<!-- 准备好一个“容器” -->
	<div id="test"></div>
	<!-- 注意引入顺序！ -->
	<!-- 引入react核心库 -->
	<script type="text/javascript" src="../js/react.development.js"></script>
	<!-- 引入react-dom，用于支持react操作DOM -->
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	<!-- 引入babel，用于将jsx转为js -->
	<script type="text/javascript" src="../js/babel.min.js"></script>

	<!-- 里面是JSX代码 -->
	<script type="text/babel" > /* 此处一定要写babel */
		//1.创建虚拟DOM
		const VDOM = <h1>Hello,React</h1> /* 此处一定不要写引号，因为不是字符串 */
		//2.渲染虚拟DOM到页面
		ReactDOM.render(VDOM,document.getElementById('test'))
	</script>
</body>
</html>
```

## 2.虚拟DOM的两种创建方式

不用JS，因为嵌套标签写起来很麻烦。用JSX创建dom就很方便。但是最终JSX还是会被Babel转换为JS

### JSX：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>1_使用jsx创建虚拟DOM</title>
</head>
<body>
	<div id="test"></div>

	<script type="text/javascript" src="../js/react.development.js"></script>
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	<script type="text/javascript" src="../js/babel.min.js"></script>

	<script type="text/babel" > /* 此处一定要写babel */
		const VDOM = (  /* 此处一定不要写引号，因为不是字符串 */
			<h1 id="title">
				<span>Hello,React</span>
			</h1>
		)
		ReactDOM.render(VDOM,document.getElementById('test'))
	</script>
</body>
</html>
```

### JS：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>2_使用js创建虚拟DOM</title>
</head>
<body>
	<div id="test"></div>

	<script type="text/javascript" src="../js/react.development.js"></script>
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	
	<script type="text/javascript" > 
        //可以不用Bable了，因为没用JSX。不需要转换了
		//1.创建虚拟DOM         标签名，   标签属性，       标签内容
const VDOM = React.createElement('h1',{id:'title'},React.createElement('span',{},'Hello,React'))
		//2.渲染虚拟DOM到页面
		ReactDOM.render(VDOM,document.getElementById('test'))
	</script>
</body>
</html>
```

### 虚拟dom和真实dom：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>3_虚拟DOM与真实DOM</title>
</head>
<body>
	<div id="test"></div>
	<div id="demo"></div>

	<script type="text/javascript" src="../js/react.development.js"></script>
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	<script type="text/javascript" src="../js/babel.min.js"></script>

	<script type="text/babel">
		const VDOM = (  
			<h1 id="title">
				<span>Hello,React</span>
			</h1>
		)
		ReactDOM.render(VDOM,document.getElementById('test'))

		const TDOM = document.getElementById('demo')
		console.log('虚拟DOM',VDOM);
		console.dir(TDOM)
	</script>
</body>
</html>
```

​		关于虚拟DOM：
​			1.本质是Object类型的对象（一般对象）
​			2.虚拟DOM比较“轻”，真实DOM比较“重”，因为虚拟DOM是React内部在用，无需真实DOM上那么多的属性。
​			3.虚拟DOM最终会被React转化为真实DOM，呈现在页面上。

## 3.JSX语法规则

```js
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>jsx语法规则</title>
	<style>
		.title{
			background-color: orange;
			width: 200px;
		}
	</style>
</head>
<body>
	<div id="test"></div>

	<script type="text/javascript" src="../js/react.development.js"></script>
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	<script type="text/javascript" src="../js/babel.min.js"></script>

	<script type="text/babel" >
		const myId = 'aTgUiGu'
		const myData = 'HeLlo,rEaCt'

		//1.创建虚拟DOM
		const VDOM = (
			<div>
				<h2 className="title" id={myId.toLowerCase()}>
					<span style={{color:'white',fontSize:'29px'}}>{myData.toLowerCase()}</span>
				</h2>
				<h2 className="title" id={myId.toUpperCase()}>
					<span style={{color:'white',fontSize:'29px'}}>{myData.toLowerCase()}</span>
				</h2>
				<input type="text"/>
			</div>
		)
		//2.渲染虚拟DOM到页面
		ReactDOM.render(VDOM,document.getElementById('test'))

	</script>
</body>
</html>
```

![image-20220330162942493](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220330162942493.png)			

jsx语法规则：
​					1.定义虚拟DOM时，不要写引号。
​					2.标签中混入JS表达式时要用{}。
​					3.样式的类名指定不要用class，要用className。 (为了和js的class类区分)
4.内联样式，要用style={{key:value}}的形式去写。（第一个括号是引入JS的，第二个括号是对象，里面用逗号分开）
​					5.只有一个根标签
​					6.标签必须闭合
​					7.标签首字母
​						(1).若小写字母开头，则将该标签转为html中同名元素，若html中无该标签对应的同名元素，则报错。
​						(2).若大写字母开头，react会以为这是一个组件， react就去渲染对应的组件，若组件没有定义，则报错。

## 4.JSX小练习

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>

    <div id="app"></div>

    <script type="text/javascript" src="../js/react.development.js"></script>
    <script type="text/javascript" src="../js/react-dom.development.js"></script>
    <script type="text/javascript" src="../js/babel.min.js"></script>

    <script type="text/babel">
        const data = ['Angular', 'React', 'Vue']
        const VDOM =
            <div>
                <h1>前端js框架列表</h1>
                <ul>
                    {
                        data.map(function (item,index) {
                            return <li key={index}>{item}</li>
                        })
                    }
                </ul>
            </div>
        ReactDOM.render(VDOM, document.getElementById("app"))
    </script>
</body>

</html>
```

注意要给每个li一个key。

![image-20220329211616964](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220329211616964.png)



我们的JSX写JS表达式要用{}

一定注意区分：【js语句(代码)】与【js表达式】

​          1.表达式：一个表达式会产生一个值，可以放在任何一个需要值的地方

​                下面这些都是表达式：

​                    (1). a

​                    (2). a+b

​                    (3). demo(1)

​                    (4). arr.map() 

​                    (5). function test () {}

​          2.语句(代码)：

​                下面这些都是语句(代码)：

​                    (1).if(){}

​                    (2).for(){}

​                    (3).switch(){case:xxxx}

## 5.定义组件

### 函数式组件：

```jsx
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>1_函数式组件</title>
</head>
<body>
	<div id="test"></div>
	
	<script type="text/javascript" src="../js/react.development.js"></script>
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	<script type="text/javascript" src="../js/babel.min.js"></script>

	<script type="text/babel">
		//1.创建函数式组件
		function MyComponent(){
			console.log(this); //此处的this是undefined，因为babel编译后开启了严格模式
			return <h2>我是用函数定义的组件(适用于【简单组件】的定义)</h2>
		}
		//2.渲染组件到页面
		ReactDOM.render(<MyComponent/>,document.getElementById('test'))
		/* 
			执行了ReactDOM.render(<MyComponent/>.......之后，发生了什么？
					1.React解析组件标签，找到了MyComponent组件。
					2.发现组件是使用函数定义的，随后调用该函数，将返回的虚拟DOM转为真实DOM，随后呈现在页面
		*/
	</script>
</body>
</html>
```

### 类式组件：

```js
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>2_类式组件</title>
</head>
<body>
	<div id="test"></div>
	
	<script type="text/javascript" src="../js/react.development.js"></script>
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	<script type="text/javascript" src="../js/babel.min.js"></script>

	<script type="text/babel">
		//1.创建类式组件
		class MyComponent extends React.Component {
			render(){
				//render是放在哪里的？—— MyComponent的原型对象上，供实例使用。
				//render中的this是谁？—— MyComponent的实例对象 <=> MyComponent组件实例对象。
				console.log('render中的this:',this);
				return <h2>我是用类定义的组件(适用于【复杂组件】的定义)</h2>
			}
		}
		//2.渲染组件到页面
		ReactDOM.render(<MyComponent/>,document.getElementById('test'))
		/* 
        执行了ReactDOM.render(<MyComponent/>.......之后，发生了什么？
            1.React解析组件标签，找到了MyComponent组件。
            2.发现组件是使用类定义的，随后new出来该类的实例，并通过该实例调用到原型上的render方法。
            3.将render返回的虚拟DOM转为真实DOM，随后呈现在页面中。
		*/
	</script>
</body>
</html>
```

![image-20220401152119971](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401152119971.png)





<div style="color: red;font-size: 23px">只有类式组件才有这三大属性喔，后期用hooks函数式组件也可以玩这三大属性</div>

## 6.组件实例三大属性之一----state

**有状态的组件（复杂组件）**

目前我们要成功运行这个例子，需要用到很多目前我们还没用过的写法，后面我们会一一解释

### 1.繁琐写法：

```js
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>state</title>
</head>
<body>
	<div id="test"></div>
	
	<script type="text/javascript" src="../js/react.development.js"></script>
	<script type="text/javascript" src="../js/react-dom.development.js"></script>
	<script type="text/javascript" src="../js/babel.min.js"></script>

	<script type="text/babel">
		class Weather extends React.Component{
			
			//构造器调用几次？ ———— 1次
			constructor(props){
				console.log('constructor');
				super(props)
				//初始化状态
				this.state = {isHot:false,wind:'微风'}
				//解决changeWeather中this指向问题
				//拿着原型上的changeWeather生成一个新的changeWeather_1挂载到实例自身上
				this.changeWeather_1 = this.changeWeather.bind(this)
			}
			//构造器主要干两件事，一是初始化state状态，二是改变this指向



			//render调用几次？ ———— 1+n次 1是初始化的那次 n是状态更新的次数
			render(){
				console.log('render');
				//读取状态
				const {isHot,wind} = this.state
				//  onClick注意大小写  调用实例上的changeWeather_1 注意不要写（）
				return <h1 onClick={this.changeWeather_1}>今天天气很{isHot ? '炎热' : '凉爽'}，{wind}</h1>
			}

			


			//changeWeather调用几次？ ———— 点几次调几次
			changeWeather(){
				//changeWeather放在哪里？ ———— Weather的原型对象上，供实例使用
				//由于changeWeather是作为onClick的回调，所以不是通过实例调用的，是直接调用
				//类中的方法默认开启了局部的严格模式，所以changeWeather中的this为undefined.
				//没开严格模式，this就是window
				
				console.log('changeWeather');
				//获取原来的isHot值
				const isHot = this.state.isHot
				//严重注意：状态必须通过setState进行更新,且更新是一种合并，不是替换。
				//这个setState是React.Component上的，通过原型链找到
				this.setState({isHot:!isHot})

				//严重注意：状态(state)不可直接更改，下面这行就是直接更改！！！
				//this.state.isHot = !isHot //这是错误的写法
			}
		}
		//我们写了<Weather/>，React会帮我们创建一个Weather类的实例
		ReactDOM.render(<Weather/>,document.getElementById('test'))
				
	</script>
</body>
</html>
```

精简代码：

```js
class Weather extends React.Component {
            constructor(props) {
                console.log('constructor');
                super(props)
                this.state = { isHot: true }
                this.changWeather_1=this.changWeather.bind(this)
            }
            render() {
                console.log('render');
                const { isHot } = this
                return <h1 onClick={this.changWeather_1}>今天天气很{isHot ? "热" : "冷"}</h1>
            }
            changWeather(){
                console.log('changeWeather');
                const isHot = this.state.isHot
                this.setState({isHot:!isHot})
            }
        }
        ReactDOM.render(<Weather />, document.querySelector(".app"))
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/84.gif" style="zoom: 100%"></img>

### 2.精简写法：

其实主要就是用了类字段

传送门：[Class 字段](https://zh.javascript.info/class#class-zi-duan)

```js
class Weather extends React.Component{
			//初始化状态
			state = {isHot:false,wind:'微风'}
			render(){
				const {isHot,wind} = this.state
				return <h1 onClick={this.changeWeather}>今天天气很{isHot ? '炎热' : '凉爽'}，{wind}</h1>
			}
			//自定义方法————要用赋值语句的形式+箭头函数(因为箭头函数会往外找this)
			changeWeather = ()=>{
				const isHot = this.state.isHot
				this.setState({isHot:!isHot})
			}
		}
		//2.渲染组件到页面
		ReactDOM.render(<Weather/>,document.getElementById('test'))
```

### 总结：

1. state是组件对象最重要的属性, 值是对象(可以包含多个key-value的组合)

2. 组件被称为"状态机", 通过更新组件的state来更新对应的页面显示(重新渲染组件)

   3.组件中render方法中的this为组件实例对象

4. 组件自定义的方法中this为undefined，如何解决？

   4.1强制绑定this: 通过函数对象的bind()

​	   4.2箭头函数

   5.状态数据，不能直接修改或更新。需要使用setState(这个函数在React.Component上)，这种修改是合并不是替换

## 7.三大属性之一-----props

理解：

1. 每个组件对象都会有props(properties的简写)属性

2. 组件标签的所有属性都保存在props中

 作用

1. 通过标签属性从组件外向组件内传递变化的数据

2. 注意: 组件内部不要修改props数据

### 1.基本使用：

```js
		class Person extends React.Component{
			render(){
				// console.log(this);
				const {name,age,sex} = this.props
				return (
					<ul>
						<li>姓名：{name}</li>
						<li>性别：{sex}</li>
						<li>年龄：{age+1}</li>
					</ul>
				)
			}
		}
		//渲染组件到页面
		ReactDOM.render(<Person name="jerry" age={19}  sex="男"/>,document.getElementById('test1'))
		ReactDOM.render(<Person name="tom" age={18} sex="女"/>,document.getElementById('test2'))

		const p = {name:'老刘',age:18,sex:'女'}
// console.log('@',...p);  
//这个地方的{...p} 这个{}可不是什么复制对象，它就是JSX里面写JS用到的代码分隔符
// 标签里面我们相当于写的是 ...p，直接把对象展开。在一般环境下会报错，但在这里Babel+React不会
//但是只在标签里使用才有这种效果，直接console.log('@',...p);  不会输出任何东西
// ReactDOM.render(<Person name={p.name} age={p.age} sex={p.sex}/>,document.getElementById('test3'))
		ReactDOM.render(<Person {...p}/>,document.getElementById('test3'))
```

![image-20220401193804228](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401193804228.png)

### 2.限制props：

我们要额外引入一个库来限制props

摘自官网：

![image-20220401201852689](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401201852689.png)

```js
class Person extends React.Component{
			render(){
				const {name,age,sex} = this.props
                //props是只读的
				//this.props.name = 'jack' //此行代码会报错，因为props是只读的
				return (
					<ul>
						<li>姓名：{name}</li>
						<li>性别：{sex}</li>
						<li>年龄：{age+1}</li>
					</ul>
				)
			}
		}
		//对标签属性进行类型、必要性的限制
		Person.propTypes = {
			name:PropTypes.string.isRequired, //限制name必传，且为字符串
			sex:PropTypes.string,//限制sex为字符串
			age:PropTypes.number,//限制age为数值
			speak:PropTypes.func,//限制speak为函数
		}
		//指定默认标签属性值
		Person.defaultProps = {
			sex:'男',//sex默认值为男
			age:18 //age默认值为18
		}
		ReactDOM.render(<Person name={100} speak={speak}/>,document.getElementById('test1'))
		ReactDOM.render(<Person name="tom" age={18} sex="女"/>,document.getElementById('test2'))

		const p = {name:'老刘',age:18,sex:'女'}
		ReactDOM.render(<Person {...p}/>,document.getElementById('test3'))

		function speak(){
			console.log('我说话了');
		}
```

![image-20220401195901028](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401195901028.png)



官方文档：[使用 PropTypes 进行类型检查 – React (reactjs.org)](https://zh-hans.reactjs.org/docs/typechecking-with-proptypes.html#gatsby-focus-wrapper)

### 3.简写方式：

就是用静态属性，把解构优化一下

传送门：[静态属性和静态方法](https://zh.javascript.info/static-properties-methods)

```js
//创建组件
		class Person extends React.Component{
			//对标签属性进行类型、必要性的限制
			static propTypes = {
				name:PropTypes.string.isRequired, //限制name必传，且为字符串
				sex:PropTypes.string,//限制sex为字符串
				age:PropTypes.number,//限制age为数值
			}

			//指定默认标签属性值
			static defaultProps = {
				sex:'男',//sex默认值为男
				age:18 //age默认值为18
			}
			
			render(){
				const {name,age,sex} = this.props
				return (
					<ul>
						<li>姓名：{name}</li>
						<li>性别：{sex}</li>
						<li>年龄：{age+1}</li>
					</ul>
				)
			}
		}

		//渲染组件到页面
		ReactDOM.render(<Person name="jerry"/>,document.getElementById('test1'))
```

### 4.关于构造器

```js
			constructor(props){
				//构造器是否接收props，是否传递给super，取决于：是否希望在构造器中通过this访问props
				//不希望那就不用写构造器了
				super(props)
				console.log('constructor',this.props);
			}
```

官网写的很清楚：https://zh-hans.reactjs.org/docs/react-component.html#constructor

### 5.函数式组件使用props

目前我们只能在函数式组件里面用三大属性的props，后期可以通过hooks用其余两个。

函数式组件有一个参数，就是props

官网：https://zh-hans.reactjs.org/docs/react-component.html#constructor

限制props，以前怎么写现在就怎么写，都是挂载到原型上

```js
		function Person (props){
			const {name,age,sex} = props
			return (
					<ul>
						<li>姓名：{name}</li>
						<li>性别：{sex}</li>
						<li>年龄：{age}</li>
					</ul>
				)
		}
		Person.propTypes = {
			name:PropTypes.string.isRequired, //限制name必传，且为字符串
			sex:PropTypes.string,//限制sex为字符串
			age:PropTypes.number,//限制age为数值
		}

		//指定默认标签属性值
		Person.defaultProps = {
			sex:'男',//sex默认值为男
			age:18 //age默认值为18
		}
		//渲染组件到页面
		ReactDOM.render(<Person name="jerry"/>,document.getElementById('test1'))
```

## 8.三大属性之一-----refs

组件内的标签可以定义ref属性来标识自己，和vue里的用法差不多

官方建议不要过度使用refs

https://zh-hans.reactjs.org/docs/refs-and-the-dom.html#dont-overuse-refs

### 1.字符串形式的refs

官方即将弃用，有效率问题，具体看官网github讨论区

https://zh-hans.reactjs.org/docs/refs-and-the-dom.html?#legacy-api-string-refs

```js

		class Demo extends React.Component{
			//展示左侧输入框的数据
			showData = ()=>{
				//input1是真实dom
				const {input1} = this.refs
				alert(input1.value)
			}
			//展示右侧输入框的数据
			showData2 = ()=>{
				const {input2} = this.refs
				alert(input2.value)
			}
			render(){
				//打印一下实例对象，看看refs
				console.log(this);
				return(
					<div>
						<input ref="input1" type="text" placeholder="点击按钮提示数据"/>&nbsp;
                    	  <button onClick={this.showData}>点我提示左侧的数据</button>&nbsp;
              <input ref="input2" onBlur={this.showData2} type="text" placeholder="失去焦点提示数据"/>
					</div>
				)
			}
		}
		//渲染组件到页面
		ReactDOM.render(<Demo a="1" b="2"/>,document.getElementById('test'))
```

打印结果：

![image-20220401203211963](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401203211963.png)



### 2.回调形式的refs

```js
//创建组件
		class Demo extends React.Component{
			//展示左侧输入框的数据
			showData = ()=>{
				//直接从this上取就行了
				const {input1} = this
				alert(input1.value)
			}
			//展示右侧输入框的数据
			showData2 = ()=>{
				const {input2} = this
				alert(input2.value)
			}
			render(){
				return(
					<div>
     //把ref当前所处的节点(就是参数currentNode，这个箭头函数写的比较精简)挂载在实例自身上，并取名为input1
						<input ref={currentNode => this.input1 = currentNode } type="text" placeholder="点击按钮提示数据"/>&nbsp;
						<button onClick={this.showData}>点我提示左侧的数据</button>&nbsp;
						<input onBlur={this.showData2} ref={c => this.input2 = c } type="text" placeholder="失去焦点提示数据"/>&nbsp;
					</div>
				)
			}
		}
		//渲染组件到页面
		ReactDOM.render(<Demo a="1" b="2"/>,document.getElementById('test'))
```

### 3.回调形式refs调用次数问题

官网说明：https://zh-hans.reactjs.org/docs/refs-and-the-dom.html?#caveats-with-callback-refs

![image-20220401212227425](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401212227425.png)

#### bug展示：

```js
 class Weather extends React.Component {

            state = { isHot: false }

            showInfo = () =>{
                alert(this.input1.value)
            }

            changeWeather = () => {
                const { isHot } = this.state
                // console.log(this);
                this.setState({ isHot: !isHot })
            }

            render() {
                return (
                    <div>
                        <h2>今天天气很{this.state.isHot ? '炎热' : '凉爽'}</h2>
						//注意回调函数的内容
                        <input type="text" ref={c=>{this.input1=c;console.log("hello",c); }}/><br/>
                        <button onClick={this.showInfo}>点我显示信息</button>
                        <button onClick={this.changeWeather}>点我切换天气</button>
                    </div>
                )
            }
        }

        ReactDOM.render(<Weather />, document.getElementById("app"))
```

我们切换天气，改变了state里的isHot。触发官网说的那个bug

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/85.gif" style="zoom: 100%"></img>

#### 解决方案：(不解决也行)

使用内绑定的函数

![image-20220401212431454](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401212431454.png)

### 4.createRef()

官方推荐使用，写的时候用几个ref就得创建几个容器

```js
class Demo extends React.Component{
			/* 
				React.createRef调用后可以返回一个容器，该容器可以存储被ref所标识的节点,该容器是“专人专用”的
			 */
			myRef = React.createRef()
			myRef2 = React.createRef()
			//展示左侧输入框的数据
			showData = ()=>{
				// alert(this.myRef.current.value);
				console.log(this.myRef);
			}
			//展示右侧输入框的数据
			showData2 = ()=>{
				// alert(this.myRef2.current.value);
				console.log(this.myRef2);
			}
			render(){
				return(
					<div>
						<input ref={this.myRef} type="text" placeholder="点击按钮提示数据"/>&nbsp;
						<button onClick={this.showData}>点我提示左侧的数据</button>&nbsp;
						<input onBlur={this.showData2} ref={this.myRef2} type="text" placeholder="失去焦点提示数据"/>&nbsp;
					</div>
				)
			}
		}
```

![image-20220402123552373](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402123552373.png)

## 9.React中的事件处理

```js
class Demo extends React.Component{
			//创建ref容器
			myRef = React.createRef()
			myRef2 = React.createRef()

			//展示左侧输入框的数据
			showData = (event)=>{
				console.log(event.target);
				alert(this.myRef.current.value);
			}

			//展示右侧输入框的数据
			//发生事件的元素正好是操作的元素就可以不用写ref，直接在target里拿就行
			showData2 = (event)=>{
				alert(event.target.value);
			}

			render(){
				return(
					<div>
						<input ref={this.myRef} type="text" placeholder="点击按钮提示数据"/>&nbsp;
						<button onClick={this.showData}>点我提示左侧的数据</button>&nbsp;
						<input onBlur={this.showData2} type="text" placeholder="失去焦点提示数据"/>&nbsp;
					</div>
				)
			}
		}
```

​				(1).通过onXxx属性指定事件处理函数(注意大小写)
​						a.React使用的是自定义(合成)事件, 而不是使用的原生DOM事件 —————— 为了更好的兼容性
​						b.React中的事件是通过事件委托方式处理的(委托给组件最外层的元素) ————————为了高效
​				(2).通过event.target得到发生事件的DOM元素对象 ——————————不要过度使用ref
​			

## 10.React收集表单数据案例

### 非受控组件：

```js
class Login extends React.Component{
			handleSubmit = (event)=>{
				event.preventDefault() //阻止表单提交
				const {username,password} = this
				alert(`你输入的用户名是：${username.value},你输入的密码是：${password.value}`)
			}
			render(){
				return(
					<form onSubmit={this.handleSubmit}>
						用户名：<input ref={c => this.username = c} type="text" name="username"/>
						密码：<input ref={c => this.password = c} type="password" name="password"/>
						<button>登录</button>
					</form>
				)
			}
		}
```



### 受控组件：

```js
class Login extends React.Component{

			//初始化状态
			state = {
				username:'', //用户名
				password:'' //密码
			}

			//保存用户名到状态中
			saveUsername = (event)=>{
				this.setState({username:event.target.value})
			}

			//保存密码到状态中
			savePassword = (event)=>{
				this.setState({password:event.target.value})
			}

			//表单提交的回调
			handleSubmit = (event)=>{
				event.preventDefault() //阻止表单提交
				const {username,password} = this.state
				alert(`你输入的用户名是：${username},你输入的密码是：${password}`)
			}

			render(){
				return(
					<form onSubmit={this.handleSubmit}>
						用户名：<input onChange={this.saveUsername} type="text" name="username"/>
						密码：<input onChange={this.savePassword} type="password" name="password"/>
						<button>登录</button>
					</form>
				)
			}
		}
```

两个组件实现功能是一样的。

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/86.gif" style="zoom: 100%"></img>

非受控组件简单理解：现用现取(我们的例子用ref取)，用了很多ref所以不好，建议使用受控组件

https://zh-hans.reactjs.org/docs/refs-and-the-dom.html#dont-overuse-refs

受控组件简单理解：页面里所有输入类型的dom(我们的例子是input)，随着我们的输入，react可以维护它的状态，用的时候直接从state取出来。其实就是vue里面的v-model双向数据绑定

## 11.优化我们的表单案例

### 1.高阶函数和函数柯里化

```js
/* 
					高阶函数：如果一个函数符合下面2个规范中的任何一个，那该函数就是高阶函数。
									1.若A函数，接收的参数是一个函数，那么A就可以称之为高阶函数。
									2.若A函数，调用的返回值依然是一个函数，那么A就可以称之为高阶函数。
									常见的高阶函数有：Promise、setTimeout、arr.map()等等

					函数的柯里化：通过函数调用继续返回函数的方式，实现多次接收参数最后统一处理的函数编码形式。 
						function sum(a){
							return(b)=>{
								return (c)=>{
									return a+b+c
								}
							}
						}
					*/
```



```js
class Login extends React.Component{
			//初始化状态
			state = {
				username:'', //用户名
				password:'' //密码
			}

			//保存表单数据到状态中
			saveFormData = (dataType)=>{
				return (event)=>{
					this.setState({[dataType]:event.target.value})
				}
			}

			//表单提交的回调
			handleSubmit = (event)=>{
				event.preventDefault() //阻止表单提交
				const {username,password} = this.state
				alert(`你输入的用户名是：${username},你输入的密码是：${password}`)
			}
			render(){
				return(
					<form onSubmit={this.handleSubmit}>
						用户名：<input onChange={this.saveFormData('username')} type="text" name="username"/>
						密码：<input onChange={this.saveFormData('password')} type="password" name="password"/>
						<button>登录</button>
					</form>
				)
			}
		}
```

[dataType]这种对象键的写法不要忘了喔，这叫计算属性

传送门：[计算属性](https://zh.javascript.info/object#ji-suan-shu-xing)

我们使用onChange触发同一个函数，该函数返回一个函数作为我们onChange的回调

### 2.不使用高阶函数的写法

```js
class Login extends React.Component{
			//初始化状态
			state = {
				username:'', //用户名
				password:'' //密码
			}

			//保存表单数据到状态中
			saveFormData = (dataType,event)=>{
				this.setState({[dataType]:event.target.value})
			}

			//表单提交的回调
			handleSubmit = (event)=>{
				event.preventDefault() //阻止表单提交
				const {username,password} = this.state
				alert(`你输入的用户名是：${username},你输入的密码是：${password}`)
			}
			render(){
				return(
					<form onSubmit={this.handleSubmit}>
						用户名：<input onChange={event => this.saveFormData('username',event) } type="text" name="username"/>
						密码：<input onChange={event => this.saveFormData('password',event) } type="password" name="password"/>
						<button>登录</button>
					</form>
				)
			}
		}
```

onChange触发函数回调，这个回调函数调用了saveFormData函数并且传递两个参数（dataType,event）



**这两种写法实际生产中都使用的挺多的**

## 12.组件的生命周期

1. 组件从创建到死亡它会经历一些特定的阶段。

2. React组件中包含一系列勾子函数(生命周期回调函数), 会在特定的时刻调用。

3. 我们在定义组件时，会在特定的生命周期回调函数中，做特定的工作。

### 1.引出组件的生命周期

```js
class Life extends React.Component{

			state = {opacity:1}

			death = ()=>{
				//卸载组件
				ReactDOM.unmountComponentAtNode(document.getElementById('test'))
			}

			//组件挂完毕
			componentDidMount(){
				
				this.timer = setInterval(() => {
					//获取原状态
					let {opacity} = this.state
					//减小0.1注意精度问题
					opacity=(opacity-0.1).toFixed(2)
					if(opacity <= 0) opacity = 1
					console.log(opacity);
					//设置新的透明度
					this.setState({opacity})
				}, 200);
			}

			//组件将要卸载
			componentWillUnmount(){
				//清除定时器
				clearInterval(this.timer)
			}

			//初始化渲染、状态更新之后
			render(){
				console.log('render');
				return(
					<div>
						<h2 style={{opacity:this.state.opacity}}>React学不会怎么办？</h2>
						<button onClick={this.death}>不活了</button>
					</div>
				)
			}
		}
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/87.gif" style="zoom: 100%"></img>

### 2.旧版本生命周期

![image-20220402182133224](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402182133224.png)

#### 1.组件挂载时

```js
			//构造器
			constructor(props){
				console.log('Count---constructor');
				super(props)
				//初始化状态
				this.state = {count:0}
			}

			//组件将要挂载的钩子
			componentWillMount(){
				console.log('Count---componentWillMount');
			}

			//组件挂载完毕的钩子
			componentDidMount(){
				console.log('Count---componentDidMount');
				console.log("\n");
			}
```

![image-20220402164626326](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402164626326.png)

#### 2.执行setState

##### 阀门没有返回值：

![image-20220402165609621](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402165609621.png)

##### 阀门return false：

##### ![image-20220402170007947](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402170007947.png)

##### 阀门return true：

![image-20220402170443677](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402170443677.png)

#### 3.强制更新

![image-20220402171505644](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402171505644.png)

#### 4.组件接收新的props

```js
//父组件A
		class A extends React.Component{
			//初始化状态
			state = {carName:'奔驰'}

			changeCar = ()=>{
				this.setState({carName:'奥拓'})
			}

			render(){
				return(
					<div>
						<div>我是A组件</div>
						<button onClick={this.changeCar}>换车</button>
						<B carName={this.state.carName}/>
					</div>
				)
			}
		}
		
		//子组件B
		class B extends React.Component{
			//组件将要接收新的props的钩子
			componentWillReceiveProps(props){
				console.log('B---componentWillReceiveProps',props);
			}

			//控制组件更新的“阀门”
			shouldComponentUpdate(){
				console.log('B---shouldComponentUpdate');
				return true
			}
			//组件将要更新的钩子
			componentWillUpdate(){
				console.log('B---componentWillUpdate');
			}

			//组件更新完毕的钩子
			componentDidUpdate(){
				console.log('B---componentDidUpdate');
				console.log("\n");
			}

			render(){
				console.log('B---render');
				return(
					<div>我是B组件，接收到的车是:{this.props.carName}</div>
				)
			}
		}
		
		//渲染组件
		ReactDOM.render(<A/>,document.getElementById('test'))
```

![image-20220402173907344](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402173907344.png)

页面挂载完毕时，是没有调用componentWillReceiveProps的

<span style="color: red">这个钩子，它只是在收到新的props时才调用。</span>所以第一次没有调用，要换车才调用

#### 5.卸载组件

这个很简单

组件将要卸载时触发componentWillUnmount，而我们使用ReactDOM.unmountComponentAtNode（节点）卸载组件。

这部分在引出组件生命周期那个案例中就写的很清楚。

![image-20220402174332479](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402174332479.png)

### 3.新版本生命周期

和旧版本一样，还是render，componentDidUpdate，componentDidMount最常用

![image-20220402195425221](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402195425221.png)

#### 1.新旧对比

UNSAFE_

![image-20220402182609284](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402182609284.png)

#### 2.新增生命周期函数getDerivedStateFromProps

意为从props获得派生的state

官网说明：https://zh-hans.reactjs.org/docs/react-component.html#static-getderivedstatefromprops

此函数使用率极低，它适用于state 的值在任何时候都取决于 props的情况。我们不做过多讲解

#### 3.新增生命周期函数getSnapshotBeforeUpdate

意为从更新前获取快照。

官网说明：https://zh-hans.reactjs.org/docs/react-component.html#getsnapshotbeforeupdate

此函数使用率也很低……

它适用于更新前可以给componentDidUpdate传递一些东西

#### 4.补充说明componentDidUpdate

这个生命周期函数，有三个参数，分别为prevProps, prevState（上一次的props和上一次的state）以及getSnapshotBeforeUpdate传递过来的东西

## 13._DOM的Diffing算法

推荐文章：[【React】组件的生命周期 - 虚拟DOM - DOM Diffing算法 - 掘金 (juejin.cn)](https://juejin.cn/post/7015766065183621156)

  官方说明：https://zh-hans.reactjs.org/docs/reconciliation.html#the-diffing-algorithm

```js
	/*
   经典面试题:
      1). react/vue中的key有什么作用？（key的内部原理是什么？）
      2). 为什么遍历列表时，key最好不要用index?
      
	1. 虚拟DOM中key的作用：
		1). 简单的说: key是虚拟DOM对象的标识, 在更新显示时key起着极其重要的作用。

		2). 详细的说: 当状态中的数据发生变化时，react会根据【新数据】生成【新的虚拟DOM】, 
		随后React进行【新虚拟DOM】与【旧虚拟DOM】的diff比较，比较规则如下：

			a. 旧虚拟DOM中找到了与新虚拟DOM相同的key：
				(1).若虚拟DOM中内容没变, 直接使用之前的真实DOM
				(2).若虚拟DOM中内容变了, 则生成新的真实DOM，随后替换掉页面中之前的真实DOM

			b. 旧虚拟DOM中未找到与新虚拟DOM相同的key:
				根据数据创建新的真实DOM，随后渲染到到页面
									
	2. 用index作为key可能会引发的问题：
		1. 若对数据进行：逆序添加、逆序删除等破坏顺序操作:
			会产生没有必要的真实DOM更新 ==> 界面效果没问题, 但效率低。

		2. 如果结构中还包含输入类的DOM：
			会产生错误DOM更新 ==> 界面有问题。
												
		3. 注意！如果不存在对数据的逆序添加、逆序删除等破坏顺序操作，仅用于渲染列表用于展示，使用index作为key			是没有问题的。
					
	3. 开发中如何选择key?:
		1.最好使用每条数据的唯一标识作为key, 比如id、手机号、身份证号、学号等唯一值。
		2.如果确定只是简单的展示数据，用index也是可以的。
   */
```



```js
/* 
		慢动作回放----使用index索引值作为key

			初始数据：
					{id:1,name:'小张',age:18},
					{id:2,name:'小李',age:19},
			初始的虚拟DOM：
					<li key=0>小张---18<input type="text"/></li>
					<li key=1>小李---19<input type="text"/></li>

			更新后的数据：
					{id:3,name:'小王',age:20},
					{id:1,name:'小张',age:18},
					{id:2,name:'小李',age:19},
			更新数据后的虚拟DOM：
					<li key=0>小王---20<input type="text"/></li>
					<li key=1>小张---18<input type="text"/></li>
					<li key=2>小李---19<input type="text"/></li>

			此时会对比新的虚拟DOM和初始的虚拟DOM，找到key一样的，发现里面的内容变了，就会
			生成新的真实DOM，随后替换掉页面中之前的真实DOM。我们会发现此前已经存在的小张
			和小李，还是会更新，显然效率极低。而我们使用唯一标识作为key，就不会有这种问题。
			当然如果我们把小王加到数组末尾也不会有这种问题。所以说用index作为key，不一定会
			有问题，慎用。
	-----------------------------------------------------------------

	慢动作回放----使用id唯一标识作为key

			初始数据：
					{id:1,name:'小张',age:18},
					{id:2,name:'小李',age:19},
			初始的虚拟DOM：
					<li key=1>小张---18<input type="text"/></li>
					<li key=2>小李---19<input type="text"/></li>

			更新后的数据：
					{id:3,name:'小王',age:20},
					{id:1,name:'小张',age:18},
					{id:2,name:'小李',age:19},
			更新数据后的虚拟DOM：
					<li key=3>小王---20<input type="text"/></li>
					<li key=1>小张---18<input type="text"/></li>
					<li key=2>小李---19<input type="text"/></li>

			对比的时候只会更新小王

	 */
```

```jsx
class Person extends React.Component{
		state = {
			persons:[
				{id:1,name:'小张',age:18},
				{id:2,name:'小李',age:19},
			]
		}
		add = ()=>{
			const {persons} = this.state
			const p = {id:persons.length+1,name:'小王',age:20}
			this.setState({persons:[p,...persons]})
		}
		render(){
			return (
				<div>
					<h2>展示人员信息</h2>
					<button onClick={this.add}>添加一个小王</button>
					<h3>使用index（索引值）作为key</h3>
					<ul>
						{
							this.state.persons.map((personObj,index)=>{
           return <li key={index}>{personObj.name}---{personObj.age}<input type="text"/></li>
							})
						}
					</ul>
					<hr/>
					<hr/>
					<h3>使用id（数据的唯一标识）作为key</h3>
					<ul>
						{
							this.state.persons.map((personObj)=>{
		return <li key={personObj.id}>{personObj.name}---{personObj.age}<input type="text"/></li>
							})
						}
					</ul>
				</div>
			)
		}
	}
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/88.gif" style="zoom: 100%"></img>

# react_staging:

安装：[尚硅谷React技术全家桶全套完整版（零基础入门到精通/男神天禹老师亲授）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1wy4y1D7JT?p=49&spm_id_from=pageDriver)   13min15s

我git下来的，只需要yarn install即可

## 1.脚手架文件介绍：

脚手架默认帮我们配置了很多文件，但大部分我们都不是很需要使用，除非有特定的业务场景。

最重要的就是index.html,App.js,index.js

### 概览：

 public ---- 静态资源文件夹

​          favicon.icon ------ 网站页签图标

​          **index.html --------** **主页面**

​          logo192.png ------- logo图

​          logo512.png ------- logo图

​          manifest.json ----- 应用加壳的配置文件

​          robots.txt -------- 爬虫协议文件

src ---- 源码文件夹

​          App.css -------- App组件的样式

​          **App.js --------- App****组件**

​          App.test.js ---- 用于给App做测试

​          index.css ------ 样式

​          **index.js -------** **入口文件**

​          logo.svg ------- logo图

​          reportWebVitals.js

​                 --- 页面性能分析文件(需要web-vitals库的支持)

​          setupTests.js

​                 ---- 组件单元测试的文件(需要jest-dom库的支持)

### public:

详细见：https://www.bilibili.com/video/BV1wy4y1D7JT?p=50

```js
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="utf-8" />
	<!-- %PUBLIC_URL%代表public文件夹的路径 -->
	<link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
	<!-- 开启理想视口，用于做移动端网页的适配 -->
	<meta name="viewport" content="width=device-width, initial-scale=1" />
	<!-- 用于配置浏览器页签+地址栏的颜色(仅支持安卓手机浏览器) -->
	<meta name="theme-color" content="red" />
	<meta name="description" content="Web site created using create-react-app" />
	<!-- 用于指定网页添加到手机主屏幕后的图标 -->
	<link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
	<!-- 应用加壳时的配置文件 -->
	<!-- 就是把网页加壳变成.apk文件 -->
	<link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
	<title>React App</title>
</head>

<body>
	<!-- 若llq不支持js则展示标签中的内容 -->
	<noscript>You need to enable JavaScript to run this app.</noscript>
	<div id="root"></div>
</body>

</html>
```

### src：

https://www.bilibili.com/video/BV1wy4y1D7JT?p=51

### 说明：

默认启动端口是3000，我在之前学习webpack缓存时使用了该端口，最好换一个。

传送门：

[(25条消息) React脚手架启动修改默认端口号_杀猪刀-墨林的博客-CSDN博客_react 脚手架如何修改端口](https://blog.csdn.net/qq_38948398/article/details/88573111)

## 2.TOODO_List案例：

### 概览：

![image-20220403194013867](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403194013867.png)

### 1.添加item

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/89.gif" style="zoom: 100%"></img>



![image-20220403194528703](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403194528703.png)

![image-20220403194916290](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403194916290.png)

把todos跟新后，List遍历自然多了一个item

### 2.鼠标滑动显示删除按钮

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/90.gif" style="zoom: 100%"></img>

![image-20220403195824206](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403195824206.png)

### 3.更新勾选栏状态

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/91.gif" style="zoom: 100%"></img>

我们修改item里面勾选栏的状态，需要更新todos的值，但todos在App里面。App和item相当于爷孙关系（中间隔了个父亲list）。我们目前还是父给子用props传函数的形式实现组件之间的通讯，后续会有更好的方法

![image-20220403201051874](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403201051874.png)

注意这里面{...todo}的写法，我们之前在props那一章有过介绍

![image-20220403201254398](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403201254398.png)

![image-20220403201731817](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403201731817.png)

### 4.删除item

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/92.gif" style="zoom: 100%"></img>

这部分逻辑和第3点：更新勾选栏状态很像。都是通过List当中间商。这里我就只截App的图了

![image-20220403204003019](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403204003019.png)

还可以用confirm优化一下用户体验，注意要加window不然会报错

![image-20220403204540542](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403204540542.png)

然后就是关于删除数组元素性能问题

传送门：

[比较 javascript 中 filter 和 splice 删除数组的性能 | 木头的博客 (mutoe.com)](https://blog.mutoe.com/2019/compare-filter-vs-splice-in-javascript/)

### 5.全选/全不选/删除已选中

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/93.gif" style="zoom: 100%"></img>

![image-20220403213912541](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403213912541.png)

![image-20220403214237065](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403214237065.png)

### 总结：

1.拆分组件、实现静态组件，注意：className、style的写法

 2.动态初始化列表，如何确定将数据放在哪个组件的state中？

​          ——某个组件使用：放在其自身的state中

​          ——某些组件使用：放在他们共同的父组件state中（官方称此操作为：状态提升）

 3.关于父子之间通信：

​        1.【父组件】给【子组件】传递数据：通过props传递

​        2.【子组件】给【父组件】传递数据：通过props传递，要求父提前给子传递一个函数

 4.注意defaultChecked 和 checked的区别，类似的还有：defaultValue 和 value

 5.状态在哪里，操作状态的方法就在哪里

## 3.配置代理服务器

传送门：

（这个是脚手架的官网喔，没有中文）

官网：[Proxying API Requests in Development | Create React App (create-react-app.dev)](https://create-react-app.dev/docs/proxying-api-requests-in-development/#configuring-the-proxy-manually)

摘自官网：

> **注意：**您无需在任何地方导入此文件。当您启动开发服务器时，它会自动注册。

> **注意：**此文件仅支持 Node 的 JavaScript 语法。确保仅使用支持的语言功能（即不支持 Flow、ES 模块等）。
>
> 就是CJS语法

![image-20220404145412990](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404145412990.png)

```js
//这个包react脚手架已经下载好了
const proxy = require('http-proxy-middleware')

module.exports = function(app){
	app.use(
		proxy('/api1',{ //遇见/api1前缀的请求，就会触发该代理配置
			target:'http://localhost:5000', //请求转发给谁
			changeOrigin:true,//控制服务器收到的请求头中Host的值
			pathRewrite:{'^/api1':''} //重写请求路径(必须)，就是把/api1置空
		}),
		proxy('/api2',{
			target:'http://localhost:5001',
			changeOrigin:true,
			pathRewrite:{'^/api2':''}
		}),
	)
}
```

### react脚手架配置代理总结

（这个总结是老师自己写的，我自己添加了一些信息，我的是9000端口，老师用的是3000）

#### 方法一

> 在package.json中追加如下配置

```json
"proxy":"http://localhost:5000"
```

说明：

1. 优点：配置简单，前端请求资源时可以不加任何前缀。
2. 缺点：不能配置多个代理。
3. 工作方式：上述方式配置代理，当请求了3000不存在的资源时，那么该请求会转发给5000 （优先匹配前端资源）



#### 方法二

1. 第一步：创建代理配置文件

   ```
   在src下创建配置文件：src/setupProxy.js
   ```

2. 编写setupProxy.js配置具体代理规则：

   ```js
   const proxy = require('http-proxy-middleware')
   
   module.exports = function(app) {
     app.use(
       proxy('/api1', {  //api1是需要转发的请求(所有带有/api1前缀的请求都会转发给5000)
         target: 'http://localhost:5000', //配置转发目标地址(能返回数据的服务器地址)
         changeOrigin: true, //控制服务器接收到的请求头中host字段的值
         /*
          changeOrigin设置为true时，服务器收到的请求头中的host为：localhost:5000
          changeOrigin设置为false时，服务器收到的请求头中的host为：localhost:3000
          changeOrigin默认值为false，但我们一般将changeOrigin值设为true
         */
         pathRewrite: {'^/api1': ''} //去除请求前缀，保证交给后台服务器的是正常请求地址(必须配置)
       }),
         //可以配置多个代理
       proxy('/api2', { 
         target: 'http://localhost:5001',
         changeOrigin: true,
         pathRewrite: {'^/api2': ''}
       })
     )
   }
   ```

说明：

1. 优点：可以配置多个代理，可以灵活的控制请求是否走代理。
2. 缺点：配置繁琐，前端请求资源时必须加前缀。

## 4.gitHub搜索案例：

老师为演示配置代理服务器的又写了个案例，没什么新东西，和之前学习的vue的那个案例一样，我就没有自己敲了。

我在这里简单介绍一下这个案例：

### 简单写写：

只有两个组件List和Search

设置代理：

![image-20220404170753328](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404170753328.png)

搜索成功：

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/94.gif" style="zoom: 100%"></img>

搜索失败：（我改了源码，把url故意拼错）

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/95.gif" style="zoom: 100%"></img>

![image-20220404165855969](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404165855969.png)

![image-20220404170319251](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404170319251.png)

![image-20220404170705194](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404170705194.png)



React里面好像不怎么容易实现类似v-show这样的功能，最终用的是连续的三元运算符？解决。

传送门：[多个 ‘?’](https://zh.javascript.info/ifelse#duo-ge)

总结：

### 消息订阅与发布：

[mroderick/PubSubJS: Dependency free publish/subscribe for JavaScript (github.com)](https://github.com/mroderick/PubSubJS)

消息订阅与发布，组件通信的另一种方式，可以实现任意两个组件的通信。

还是以gitHub搜素案例为例

![image-20220404173038415](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404173038415.png)

![image-20220404173141909](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404173141909.png)

![image-20220404173254691](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404173254691.png)

### fetch：

使用率很低，因为兼容性不好，旧浏览器需要垫片才能用，但是是原生的，内部不使用XmlHttpRequest对象发送请求。

传送门：[网络请求 (javascript.info)](https://zh.javascript.info/network)

老师这里讲的很基础。

原生未优化的

```js
 		fetch(`/api1/search/users2?q=${keyWord}`).then(
			response => {
				console.log('联系服务器成功了');
				return response.json()
			},
			error => {
				console.log('联系服务器失败了',error);
                //这里返回pending状态的Promise，中断链
                //如果没这个return的话，默认return undefined，undefined是非Promise类型
                //所以会返回一个resolved的Promise，value为undefined
				return new Promise(()=>{})
			}
		).then(
			response => {console.log('获取数据成功了',response);},
			error => {console.log('获取数据失败了',error);}
		) 
```

拿个catch兜底也行

```js
fetch(`/api1/search/users2?q=${keyWord}`).then(
			response => {
				console.log('联系服务器成功了');
				return response.json()
			},
		).then(
			response => {console.log('获取数据成功了',response);},
		).catch(
    		error => console.log('获取数据失败了',error)
		)
```

使用try-catch+async+await优化

外侧最近一个函数加一个async

```js
		try {
			const response= await fetch(`/api1/search/users2?q=${keyWord}`)
			const data = await response.json()
			console.log(data);
			//PubSub.publish('atguigu',{isLoading:false,users:data.items})
		} catch (error) {
			console.log('请求出错',error);
			//PubSub.publish('atguigu',{isLoading:false,err:error.message})
		}
```

### 总结：

	1.设计状态时要考虑全面，例如带有网络请求的组件，要考虑请求失败怎么办。
	2.ES6小知识点：解构赋值+重命名
				let obj = {a:{b:1}}
				const {a} = obj; //传统解构赋值
				const {a:{b}} = obj; //连续解构赋值
				const {a:{b:value}} = obj; //连续解构赋值+重命名
	3.消息订阅与发布机制
				1.先订阅，再发布（理解：有一种隔空对话的感觉）
				2.适用于任意组件间通信
				3.要在组件的componentWillUnmount中取消订阅
	4.fetch发送请求（关注分离的设计思想）
				try {
					const response= await fetch(`/api1/search/users2?q=${keyWord}`)
					const data = await response.json()
					console.log(data);
				} catch (error) {
					console.log('请求出错',error);
				}

## 5.路由

### 路由的基本使用：

路由这个概念不用多说，已经很熟悉了。重点介绍一下在React中使用路由。

传送门：[React Router: Declarative Routing for React.js (docschina.org)](https://react-router.docschina.org/)

我们学习WEB路由。

老师的版本是5，后续也会讲6版本。

```js
"react-router-dom": "^5.2.0"
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/96.gif" style="zoom: 100%"></img>

![image-20220404211821353](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404211821353.png)

![image-20220404211615982](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404211615982.png)

![image-20220404211707813](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404211707813.png)

![image-20220404212027227](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404212027227.png)

#### 总结：

 		1.明确好界面中的导航区、展示区
 		2.导航区的a标签改为Link标签
 					<Link to="/xxxxx">Demo</Link>
 		3.展示区写Route标签进行路径的匹配
 					<Route path='/xxxx' component={Demo}/>
 		4.<App>的最外侧包裹了一个<BrowserRouter>或<HashRouter>

目前我们不过多探讨<BrowserRouter>或<HashRouter>的区别

### 路由组件和一般组件的区别：

		1.写法不同：
					一般组件：<Demo/>
					路由组件：<Route path="/demo" component={Demo}/>
		2.存放位置不同：
					一般组件：components
					路由组件：pages
		3.接收到的props不同：
					一般组件：写组件标签时传递了什么，就能收到什么
					路由组件：接收到三个固定的属性
					(这里列出我们最常使用的属性)
										history:
													go: ƒ go(n)
													goBack: ƒ goBack()
													goForward: ƒ goForward()
													push: ƒ push(path, state)
													replace: ƒ replace(path, state)
										location:
													pathname: "/about"
													search: ""
													state: undefined
										match:
													params: {}
													path: "/about"
													url: "/about"

### NavLink与封装NavLink：

NavLink可以实现路由链接的高亮，通过activeClassName指定样式名

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/97.gif" style="zoom: 100%"></img>

![image-20220404214454757](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404214454757.png)

![image-20220404214551689](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220404214551689.png)
