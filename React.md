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

```html
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

```html
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

```html
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
			和小李，还是会更新，显然效率极低。而我们使用唯一标识作为key，就不会有这种问题
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

```js
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

安装：[尚硅谷React技术全家桶全套完整版（零基础入门到精通/男神天禹老师亲授）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1wy4y1D7JT?p=49&spm_id_from=pageDriver)

