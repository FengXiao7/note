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
​					4.内联样式，要用style={{key:value}}的形式去写。（第一个括号是引入JS的，第二个括号是对象）
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

## 1.字符串形式的refs

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



## 2.回调形式的refs

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

## 3.回调形式refs调用次数问题

官网说明：https://zh-hans.reactjs.org/docs/refs-and-the-dom.html?#caveats-with-callback-refs

![image-20220401212227425](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401212227425.png)

### bug展示：

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

### 解决方案：(不解决也行)

使用内绑定的函数

![image-20220401212431454](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401212431454.png)
