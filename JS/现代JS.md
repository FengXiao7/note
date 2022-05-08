# 说明：

1.此笔记记录我对电子书现代 JavaScript 教程学习情况。电子书中记录了很多新特性，不乏ES2020里面的新特性。且保持更新，很值得深入阅读多次阅读。



2.我在每个三级标题下都标注了连接，方便查看原文。



3.有些难以理解的地方，我都写的有自己的理解。实在不行还有传送门，但详细说明还是看原文好。还有些极其少见的用法，我个人感觉没有必要掌握。



4.这是JS教程，不要死记硬背，要深度理解，忘记了回来再查查看看就行。写在这上面的笔记，我在阅读时一定是理解了，才会写上去。（不理解的有特殊说明）所以以后回顾时，遇见不理解的地方，多回笔记里看看。

5.有些地方写的晦涩难懂，也不要着急，看看博客会好很多。

传送门：[Issues · mqyqingfeng/Blog (github.com)](https://github.com/mqyqingfeng/Blog/labels/深入系列)





中文网址：[现代 JavaScript 教程](https://zh.javascript.info/)

github：[The Modern JavaScript Tutorial (github.com)](https://github.com/javascript-tutorial)

# 较难理解的地方

### 1.对象 — 原始值转换

[对象 — 原始值转换](https://zh.javascript.info/object-toprimitive)

### 7.变量作用域，闭包 

[变量作用域，闭包](https://zh.javascript.info/closure)

传送门：

[我从来不理解JavaScript闭包，直到有人这样向我解释它 - 掘金 (juejin.cn)](https://juejin.cn/post/6844903858636849159#heading-6)

### 8.装饰器，fun.call,fun.apply 

[装饰器模式和转发，call/apply](https://zh.javascript.info/call-apply-decorators)

文中举的装饰器的例子难以理解，后面的文章作者也举了很多装饰器的例子，多看看还是能理解

[任务](https://zh.javascript.info/call-apply-decorators#tasks)

习题里面的防抖装饰器，还有节流装饰器都写得很好，值得收藏。尤其是节流装饰器很值得深究

### 9.函数对象，NFE

[函数对象，NFE (javascript.info)](https://zh.javascript.info/function-object)

里面提到的自定义属性和闭包的选择，还用length属性用于内省/运行时检查很难理解。

两道习题也很难完成

### 10.在没有上下文的情况下，绑定参数

[在没有上下文情况下的 partial](https://zh.javascript.info/bind#zai-mei-you-shang-xia-wen-qing-kuang-xia-de-partial)

多看看还是可以理解

### 10.模块在浏览器中的特定功能

https://zh.javascript.info/modules-intro#liu-lan-qi-te-ding-gong-neng

### 11.导入导出

语法变体有点多

https://zh.javascript.info/import-export

### 12.关于this

推荐文章，传送门：

[this、apply、call、bind - 掘金 (juejin.cn)](https://juejin.cn/post/6844903496253177863)

**this 永远指向最后调用它的那个对象**

**所有的对象方法都将当前对象作为 `this`**

**箭头函数的 this 始终指向函数定义时的 this，而非执行时。**，箭头函数需要记着这句话：“箭头函数中没有 this 绑定，必须通过查找作用域链来决定其值，如果箭头函数被非箭头函数包含，则 this 绑定的是最近一层非箭头函数的 this，否则，this 为 undefined”。

作为一个函数调用（就是作为一个函数调用的，没有挂载在任何对象上，所以对于没有挂载在任何对象上的函数，在非严格模式下 this 就是指向 window 的）

**匿名函数的 this 永远指向 window**



### 13.关于原型

[原型，继承](https://zh.javascript.info/prototypes)

看的时候觉得还行，很容易理解，但主要还是用的不是很多，很容易遗忘。

### 14.关于类

[类](https://zh.javascript.info/classes)

内容很多，有的地方作者挖的很深，常看常理解

### 15.一个继承习题

[类扩展自对象？](https://zh.javascript.info/static-properties-methods#lei-kuo-zhan-zi-dui-xiang)

这个习题，解析拓展的内容很绕

### 16.包装异常

[包装异常](https://zh.javascript.info/custom-errors#bao-zhuang-yi-chang)

### 17.原生DOM操作

它的所有习题对我而言，都很难。因为自己用js框架的时间和UI组件库的时间要多得多，写框架和UI库的应该要经常用吧

能把下面这10个题做会，就算通关了。

[任务](https://zh.javascript.info/modifying-document#tasks)



# 疑问：

## 1.构造器的一个习题

[创建 new Calculator](https://zh.javascript.info/constructor-new#chuang-jian-newcalculator)

题很简单，想知道在构造器里如何实现判断read()方法执行过没，如果没有执行，自动执行read()。

这样外部没有调用calculator.read()，也可正常运行sum()和mul()了

## 2.任意数量的括号求和

这个习题确实做不来

[任意数量的括号求和](https://zh.javascript.info/function-object#ren-yi-shu-liang-de-kuo-hao-qiu-he)

# JavaScript 编程语言

## 2.JavaScript基础知识

### 2.1HelloWorld

https://zh.javascript.info/hello-world

![image-20220328085516625](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328085516625.png)

### 2.5数据类型

https://zh.javascript.info/types

#### 1.Number

Infinity

```js
alert( 1 / 0 ); // Infinity
```

```JS
alert( Infinity ); // Infinity
```

NaN

```js
alert( "not a number" / 2 ); // NaN，这样的除法是错误的
```

```js
alert( NaN + 1 ); // NaN
alert( 3 * NaN ); // NaN
alert( "not a number" / 2 - 1 ); // NaN
```

<div style="color: red">所以，如果在数学表达式中有一个 NaN，会被传播到最终结果（只有一个例外：NaN ** 0 结果为 1）</div>

#### 2.BigInt

在 JavaScript 中，“number” 类型无法表示大于 `(253-1)`（即 `9007199254740991`），或小于 `-(253-1)` 的整数。这是其内部表示形式导致的技术限制。

```js
// 尾部的 "n" 表示这是一个 BigInt 类型
const bigInt = 1234567890123456789012345678901234567890n;
```

#### 3.String

![image-20220328090903501](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328090903501.png)

```js
let name = "John";

// 嵌入一个变量
alert( `Hello, ${name}!` ); // Hello, John!

// 嵌入一个表达式
alert( `the result is ${1 + 2}` ); // the result is 3
```

#### 4.总结

JavaScript 中有八种基本的数据类型（译注：前七种为基本数据类型，也称为原始类型，而 `object` 为复杂数据类型）。

- `number` 用于任何类型的数字：整数或浮点数，在 `±(253-1)` 范围内的整数。
- `bigint` 用于任意长度的整数。
- `string` 用于字符串：一个字符串可以包含 0 个或多个字符，所以没有单独的单字符类型。
- `boolean` 用于 `true` 和 `false`。
- `null` 用于未知的值 —— 只有一个 `null` 值的独立类型。
- `undefined` 用于未定义的值 —— 只有一个 `undefined` 值的独立类型。
- `symbol` 用于唯一的标识符。
- `object` 用于更复杂的数据结构。

坑：

```js
typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```

![image-20220328091534315](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328091534315.png)

### 2.6交互

https://zh.javascript.info/alert-prompt-confirm

#### 1.prompt

![image-20220327204219358](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327204219358.png)

访问者可以在提示输入栏中输入一些内容，然后按“确定”键。然后我们在 `result` 中获取该文本。或者他们可以按取消键或按 Esc 键取消输入，然后我们得到 `null` 作为 `result`。

`prompt` 将返回用户在 `input` 框内输入的文本，如果用户取消了输入，则返回 `null`。

#### 2.confirm

![image-20220327204320763](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327204320763.png)

### 2.7类型转换

https://zh.javascript.info/type-conversions

#### 1.数字型类型转换

![image-20220328091934826](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328091934826.png)

```js
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN（从字符串“读取”数字，读到 "z" 时出现错误）
alert( Number(true) );        // 1
alert( Number(false) );       // 0
```

#### 2.布尔类型转换

转换规则如下：

- 直观上为“空”的值（如 `0`、空字符串、`null`、`undefined` 和 `NaN`）将变为 `false`。
- 其他值变成 `true`。
- ![image-20220328092118881](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328092118881.png)

### 2.8基础运算符，数学

https://zh.javascript.info/operators

#### 1.数字转化，一元运算符+

加号 `+` 有两种形式。一种是上面我们刚刚讨论的二元运算符，还有一种是一元运算符。

一元运算符加号，或者说，加号 `+` 应用于单个值，对数字没有任何作用。但是如果运算元不是数字，加号 `+` 则会将其转化为数字。



```js
// 对数字无效
let x = 1;
alert( +x ); // 1

let y = -2;
alert( +y ); // -2

// 转化非数字
alert( +true ); // 1
alert( +"" );   // 0
```

它的效果和 `Number(...)` 相同，但是更加简短。

#### 2.自增自减

![image-20220328092825164](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328092825164.png)

#### 3.逗号运算符

逗号运算符能让我们处理多个语句，使用 `,` 将它们分开。每个语句都运行了，但是只有最后的语句的结果会被返回。

举个例子：

```javascript
let a = (1 + 2, 3 + 4);

alert( a ); // 7（3 + 4 的结果）
```

#### 习题：

https://zh.javascript.info/operators#lei-xing-zhuan-huan  巨坑

### 2.9值的比较

https://zh.javascript.info/comparison

#### 1.不同类型的比较

![image-20220328093435061](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328093435061.png)

#### 2.对 null 和 undefined 进行比较

从没见过这么多坑……

[对 null 和 undefined 进行比较](https://zh.javascript.info/comparison#dui-null-he-undefined-jin-hang-bi-jiao)

#### 习题：

坑坑坑！

https://zh.javascript.info/comparison#zhi-de-bi-jiao

### 2.10 if与？

https://zh.javascript.info/ifelse

#### 1.多个？

```js
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

alert( message );
```

可能很难一下子看出发生了什么。但经过仔细观察，我们可以看到它只是一个普通的检查序列。

1. 第一个问号检查 `age < 3`。
2. 如果为真 — 返回 `'Hi, baby!'`。否则，会继续执行冒号 `":"` 后的表达式，检查 `age < 18`。
3. 如果为真 — 返回 `'Hello!'`。否则，会继续执行下一个冒号 `":"` 后的表达式，检查 `age < 100`。
4. 如果为真 — 返回 `'Greetings!'`。否则，会继续执行最后一个冒号 `":"` 后面的表达式，返回 `'What an unusual age!'`。

这是使用 `if..else` 实现上面的逻辑的写法：

```js
if (age < 3) {
  message = 'Hi, baby!';
} else if (age < 18) {
  message = 'Hello!';
} else if (age < 100) {
  message = 'Greetings!';
} else {
  message = 'What an unusual age!';
}
```

### 2.11逻辑运算符

https://zh.javascript.info/logical-operators

#### 1.或运算寻找第一个真值

```js
alert( 1 || 0 ); // 1（1 是真值）

alert( null || 1 ); // 1（1 是第一个真值）
alert( null || 0 || 1 ); // 1（第一个真值）

alert( undefined || null || 0 ); // 0（都是假值，返回最后一个值）
```

```js
let firstName = "";
let lastName = "";
let nickName = "SuperCoder";

alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
```

#### 2.与运算寻找第一个假值

换句话说，与运算返回第一个假值，如果没有假值就返回最后一个值。

```js
// 如果第一个操作数是真值，
// 与运算返回第二个操作数：
alert( 1 && 0 ); // 0
alert( 1 && 5 ); // 5

// 如果第一个操作数是假值，
// 与运算将直接返回它。第二个操作数会被忽略
alert( null && 5 ); // null
alert( 0 && "no matter what" ); // 0
```

#### 3.非

逻辑非运算符接受一个参数，并按如下运作：

1. 将操作数转化为布尔类型：`true/false`。

2. 返回相反的值。

   ![image-20220328094915500](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328094915500.png)

#### 习题：

看看就行，平时也不会用到这种绕死人的写法

https://zh.javascript.info/logical-operators#tasks

### 2.12空值合并运算符

(ES2020)看原文完事了

https://zh.javascript.info/nullish-coalescing-operator

#### 1.简介

空值合并运算符（nullish coalescing operator）的写法为两个问号 `??`。

由于它对待 `null` 和 `undefined` 的方式类似，所以在本文中我们将使用一个特殊的术语对其进行表示。我们将值既不是 `null` 也不是 `undefined` 的表达式称为“已定义的（defined）”。

`a ?? b` 的结果是：

- 如果 `a` 是已定义的，则结果为 `a`，
- 如果 `a` 不是已定义的，则结果为 `b`。

#### 2.与||比较

![image-20220328095721198](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328095721198.png)

### 2.13循环

https://zh.javascript.info/while-for

#### 1.do…while” 循环

![image-20220328100720721](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328100720721.png)

#### 2.继续下一次迭代

`continue` 指令是 `break` 的“轻量版”。它不会停掉整个循环。而是停止当前这一次迭代，并强制启动新一轮循环（如果条件允许的话）。

如果我们完成了当前的迭代，并且希望继续执行下一次迭代，我们就可以使用它。

下面这个循环使用 `continue` 来只输出奇数：

```js
for (let i = 0; i < 10; i++) {

  //如果为真，跳过循环体的剩余部分。
  if (i % 2 == 0) continue;

  alert(i); // 1，然后 3，5，7，9
}
```

#### 3.break/continue 标签

之前根本没有用过这种写法……

[break/continue 标签](https://zh.javascript.info/while-for#breakcontinue-biao-qian)

### 2.14switch

https://zh.javascript.info/switch

用switch频率较低，但想用的时候，又经常忘记写法

### 2.15函数

https://zh.javascript.info/function-basics

#### 1.外部变量

只有在没有局部变量的情况下才会使用外部变量。

如果在函数内部声明了同名变量，那么函数会 **遮蔽** 外部变量。例如，在下面的代码中，函数使用局部的 `userName`，而外部变量被忽略：

```js
let userName = 'John';

function showMessage() {
  let userName = "Bob"; // 声明一个局部变量

  let message = 'Hello, ' + userName; // Bob
  alert(message);
}

// 函数会创建并使用它自己的 userName
showMessage();

alert( userName ); // John，未被更改，函数没有访问外部变量。
```

#### 2.默认值

```js
function showMessage(from, text = "no text given") {
  alert( from + ": " + text );
}

showMessage("Ann"); // Ann: no text given
```

### 2.16函数表达式

https://zh.javascript.info/function-expressions

#### 1.回调函数

```js
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

function showOk() {
  alert( "You agreed." );
}

function showCancel() {
  alert( "You canceled the execution." );
}

// 用法：函数 showOk 和 showCancel 被作为参数传入到 ask
ask("Do you agree?", showOk, showCancel);
```

`ask` 的两个参数值 `showOk` 和 `showCancel` 可以被称为 **回调函数** 或简称 **回调**。

主要思想是我们传递一个函数，并期望在稍后必要时将其“回调”。在我们的例子中，`showOk` 是回答 “yes” 的回调，`showCancel` 是回答 “no” 的回调。

我们可以用函数表达式对同样的函数进行大幅简写：

```js
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);
```

#### 2.函数表达式和函数声明

**函数声明**：在主代码流中声明为单独的语句的函数。

```js
// 函数声明
function sum(a, b) {
  return a + b;
}
```

**函数表达式**：在一个表达式中或另一个语法结构中创建的函数。下面这个函数是在赋值表达式 `=` 右侧创建的：

```js
// 函数表达式
let sum = function(a, b) {
  return a + b;
};
```

<div style="color: red">函数表达式是在代码执行到达时被创建，并且仅从那一刻起可用。</div>

```js
sayHi("John"); // error!

let sayHi = function(name) {  // (*) no magic any more
  alert( `Hello, ${name}` );
};
```

<div style="color: red">在函数声明被定义之前，它就可以被调用。</div>

```js
sayHi("John"); // Hello, John

function sayHi(name) {
  alert( `Hello, ${name}` );
}
```

**因为在进入全局上下文时，首先处理函数声明，再处理变量声明。**



函数声明的另外一个特殊的功能是它们的块级作用域。

<div style="color: red">严格模式下，当一个函数声明在一个代码块内时，它在该代码块内的任何位置都是可见的。但在代码块外不可见。</div>

想象一下我们需要依赖于在代码运行过程中获得的变量 `age` 声明一个函数 `welcome()`。并且我们计划在之后的某个时间使用它。

函数声明：

```js
let age = 16; // 拿 16 作为例子

if (age < 18) {
  welcome();               // \   (运行)
                           //  |
  function welcome() {     //  |
    alert("Hello!");       //  |  函数声明在声明它的代码块内任意位置都可用
  }                        //  |
                           //  |
  welcome();               // /   (运行)

} else {

  function welcome() {
    alert("Greetings!");
  }
}

// 在这里，我们在花括号外部调用函数，我们看不到它们内部的函数声明。


welcome(); // Error: welcome is not defined
```

函数表达式：

```js
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  function() { alert("Hello!"); } :
  function() { alert("Greetings!"); };

welcome(); // 现在可以了
```



## 4.Object（对象）：基础知识

### 4.1对象

https://zh.javascript.info/object

#### 1.方括号

和‘.’一个意思

```js
let user = {};

// 设置
user["likes birds"] = true;

// 读取
alert(user["likes birds"]); // true

// 删除
delete user["likes birds"];
```

还可以动态操作key

```js
let user = {
  name: "John",
  age: 30
};

let key = prompt("What do you want to know about the user?", "name");

// 访问变量
alert( user[key] ); // John（如果输入 "name"） //30(如果输入 "age")
```

方括号比点符号更强大。它允许任何属性名和变量，但写起来也更加麻烦。

所以，大部分时间里，当属性名是已知且简单的时候，就使用点符号。如果我们需要一些更复杂的内容，那么就用方括号。

#### 2.属性名称限制

属性命名没有限制。属性名可以是任何字符串或者 symbol

其他类型会被自动地转换为字符串。

例如，当数字 `0` 被用作对象的属性的键时，会被转换为字符串 `"0"`：

```js
let obj = {
  0: "test" // 等同于 "0": "test"
};

// 都会输出相同的属性（数字 0 被转为字符串 "0"）
alert( obj["0"] ); // test
alert( obj[0] ); // test (相同的属性)
```

#### 3.属性存在性测试，“in” 操作符

https://zh.javascript.info/object#shu-xing-cun-zai-xing-ce-shi-in-cao-zuo-fu

```js
let user = {};

alert( user.noSuchProperty === undefined ); // true 意思是没有这个属性
```

in

```js
let user = { name: "John", age: 30 };

alert( "age" in user ); // true，user.age 存在
alert( "blabla" in user ); // false，user.blabla 不存在。
```

请注意，`in` 的左边必须是 **属性名**。通常是一个带引号的字符串。

如果我们省略引号，就意味着左边是一个变量，它应该包含要判断的实际属性名。例如：

```js
let user = { age: 30 };

let key = "age";
alert( key in user ); // true，属性 "age" 存在
```

为何会有 `in` 运算符呢？与 `undefined` 进行比较来判断还不够吗？

确实，大部分情况下与 `undefined` 进行比较来判断就可以了。但有一个例外情况，这种比对方式会有问题，但 `in` 运算符的判断结果仍是对的。

那就是属性存在，但存储的值是 `undefined` 的时候：

```js
let obj = {
  test: undefined
};

alert( obj.test ); // 显示 undefined，所以属性不存在？

alert( "test" in obj ); // true，属性存在！
```

#### 4.for...in循环

（通常也不会把数字当键吧……）

键顺序问题：

```js
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};
//整数属性会被进行排序，其他属性则按照创建的顺序显示
for(let code in codes) {
  alert(code); // 1, 41, 44, 49
}
```



```js
let user = {
  name: "John",
  surname: "Smith"
};
user.age = 25; // 增加一个

// 非整数属性是按照创建的顺序来排列的
for (let prop in user) {
  alert( prop ); // name, surname, age
}
```



### 4.2对象引用和复制

[对象引用和复制 (javascript.info)](https://zh.javascript.info/object-copy)

#### 1.通过引用来比较

```js
let user = { name: 'John' };

let admin = user;

admin.name = 'Pete'; // 通过 "admin" 引用来修改

alert(user.name); // 'Pete'，修改能通过 "user" 引用看到
```

![image-20220327210259201](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327210259201.png)

#### 2.克隆与合并，Object.assign

##### 浅拷贝：

创建一个新对象，这个对象有着原始对象属性值的一份精确拷贝。如果属性是基本类型，拷贝的就是基本类型的值，如果属性是引用类型，拷贝的就是内存地址 ，所以如果其中一个对象改变了这个地址，就会影响到另一个对象。

![image-20220327210524987](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327210524987.png)

```js
let user = { name: "John" };

let permissions1 = { canView: true };
let permissions2 = { canEdit: true };

// 将 permissions1 和 permissions2 中的所有属性都拷贝到 user 中
Object.assign(user, permissions1, permissions2);

// 现在 user = { name: "John", canView: true, canEdit: true }
```

如果被拷贝的属性的属性名已经存在，那么它会被覆盖：

```js
let user = { name: "John" };

Object.assign(user, { name: "Pete" });

alert(user.name); // 现在 user = { name: "Pete" }
```

简单克隆：

```js
let user = {
  name: "John",
  age: 30
};

let clone = Object.assign({}, user);
```

<div style="color: red">user和clone指向不同的引用</div>

```
let clone = Object.create(Object.getPrototypeOf(obj), Object.getOwnPropertyDescriptors(obj));
```



##### 深拷贝：

将一个对象从内存中完整的拷贝一份出来,从堆内存中开辟一个新的区域存放新对象,且修改新对象不会影响原对象

```js
let user = {
  name: "John",
  sizes: {
    height: 182,
    width: 50
  }
};

let clone = Object.assign({}, user);

alert( user.sizes === clone.sizes ); // true，同一个对象

// user 和 clone 分享同一个 sizes
user.sizes.width++;       // 通过其中一个改变属性值
alert(clone.sizes.width); // 51，能从另外一个看到变更的结果
```

![image-20220327211522942](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327211522942.png)

##### 传送门：

[如何写出一个惊艳面试官的深拷贝? - 掘金 (juejin.cn)](https://juejin.cn/post/6844903929705136141)

### 4.3垃圾回收

https://zh.javascript.info/garbage-collection

传世经典，快看原文

### 4.4对象方法，this

[对象方法，"this"](https://zh.javascript.info/object-methods)

#### 1.方法简写

```js
// 这些对象作用一样

user = {
  sayHi: function() {
    alert("Hello");
  }
};

// 方法简写看起来更好，对吧？
let user = {
  sayHi() { // 与 "sayHi: function(){...}" 一样
    alert("Hello");
  }
};
```

#### 2.this不受限制

```js
let user = { name: "John" };
let admin = { name: "Admin" };

function sayHi() {
  alert( this.name );
}

// 在两个对象中使用相同的函数
user.f = sayHi;
admin.f = sayHi;

// 这两个调用有不同的 this 值
// 函数内部的 "this" 是“点符号前面”的那个对象
user.f(); // John（this == user）
admin.f(); // Admin（this == admin）

admin['f'](); // Admin（使用点符号或方括号语法来访问这个方法，都没有关系。）
```

#### 3.箭头函数没有this

箭头函数有些特别：它们没有自己的 `this`。如果我们在这样的函数中引用 `this`，`this` 值取决于外部“正常的”函数。

举个例子，这里的 `arrow()` 使用的 `this` 来自于外部的 `user.sayHi()` 方法：

```js
let user = {
  firstName: "Ilya",
  sayHi() {
    let arrow = () => alert(this.firstName);
    arrow();
  }
};

user.sayHi(); // Ilya
```

#### 习题：

1.[在对象字面量中使用 "this"](https://zh.javascript.info/object-methods#zai-dui-xiang-zi-mian-liang-zhong-shi-yong-this)

### 4.5构造器和操作符"new"

[构造器和操作符 "new" (javascript.info)](https://zh.javascript.info/constructor-new)

#### 1.构造函数

构造函数在技术上是常规函数。不过有两个约定：

1. 它们的命名以大写字母开头。
2. 它们只能由 `"new"` 操作符来执行。

```js
function User(name) {
  this.name = name;
  this.isAdmin = false;
}

let user = new User("Jack");

alert(user.name); // Jack
alert(user.isAdmin); // false
```

当一个函数被使用 `new` 操作符执行时，它按照以下步骤：

1. 一个新的空对象被创建并分配给 `this`。
2. 函数体执行。通常它会修改 `this`，为其添加新的属性。
3. 返回 `this` 的值。

换句话说，`new User(...)` 做的就是类似的事情：

```js
function User(name) {
  // this = {};（隐式创建）

  // 添加属性到 this
  this.name = name;
  this.isAdmin = false;

  // return this;（隐式返回）
}
```

new function（）

```js
// 创建一个函数并立即使用 new 调用它
let user = new function() {
  this.name = "John";
  this.isAdmin = false;

  // ……用于用户创建的其他代码
  // 也许是复杂的逻辑和语句
  // 局部变量等
};
```

这个构造函数不能被再次调用，因为它不保存在任何地方，只是被创建和调用。因此，这个技巧旨在封装构建单个对象的代码，而无需将来重用。

#### 2.构造器模式测试：new.target

（极少使用）

在一个函数内部，我们可以使用 `new.target` 属性来检查它是否被使用 `new` 进行调用了。

对于常规调用，它为 undefined，对于使用 `new` 的调用，则等于该函数：

```js
function User() {
  alert(new.target);
}

// 不带 "new"：
User(); // undefined

// 带 "new"：
new User(); // function User { ... }
```

#### 3.构造器的return

（一般都不写的，可以看看）

[构造器的 return](https://zh.javascript.info/constructor-new#gou-zao-qi-de-return)

如果有 `return` 语句，那么规则就简单了：

- 如果 `return` 返回的是一个对象，则返回这个对象，而不是 `this`。
- 如果 `return` 返回的是一个原始类型，则忽略。

<div style="color: red">换句话说，带有对象的 `return` 返回该对象，在所有其他情况下返回 `this`。</div>



#### 习题：

1.题很简单，想知道在构造器里如何实现判断read()方法执行过没，如果没有执行，自动执行read()

[创建 new Calculator](https://zh.javascript.info/constructor-new#chuang-jian-newcalculator)

### 4.6 可选链?.

（ES2020）看原文就完事了

[可选链 "?."](https://zh.javascript.info/optional-chaining)

### 4.7Symbol类型

（ES2015）

[Symbol 类型](https://zh.javascript.info/symbol)

### 4.8对象-原始值转化

[对象 — 原始值转换](https://zh.javascript.info/object-toprimitive)

#### 我的见解：

就是说涉及到对象转换到其他数据类型，有三种方法

1.Symbol.toPrimitive优先级较高  ES6新增的

2.toString和valueOf()优先级较低

toString和valueOf()两者的优先级根据对象转换的类型不同，也会有细微差别

三种方法都是内置的，当然也可以自定义设置



然后转换的其他数据类型也可以分三类，string，number，defalut。



- `toString` 方法返回一个字符串 。
- `valueOf` 方法返回对象自身。

```js
let str = "hello",n = 123,bool = true;
let user = {
    age: 18,
    name: "Tom"
}
let array = [str,n,bool,user]

console.log(typeof(str.toString())+ "_"+ str.toString())        
console.log(typeof(n.toString())+"_"+n.toString()  )           
console.log(typeof(bool.toString())+"_"+bool.toString())        
console.log(typeof(user.toString())+"_"+user.toString())       
console.log(typeof(array.toString())+"_"+array.toString())        

console.log("--------------------------");

console.log(typeof(str.valueOf())+"_"+str.valueOf())           
console.log(typeof(n.valueOf())+"_"+n.valueOf())                
console.log(typeof(bool.valueOf())+"_"+bool.valueOf())          
console.log(typeof(user.valueOf())+"_"+user.valueOf())          
console.log(typeof(array.valueOf())+"_"+array.valueOf())          

console.log("--------------------------");

console.log(str.valueOf() === str) 
console.log(n.valueOf() === n) 
console.log(bool.valueOf() === bool)
console.log(user.valueOf() === user) 
console.log(array.valueOf() === array) 


```

![image-20220328160236916](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328160236916.png)

## 5.数据类型：

### 5.2数字类型：

[数字类型](https://zh.javascript.info/number)

#### 我的见解：

内含进制转换，四舍五入，不精确的计算，NaN，infinty，从字符串提取数字等等内容繁多，推荐看原文。

<div style="color: red">记住涉及到小数时，慎用相等性检查</div>

知道有这些个东西就行，用的时候再查。

![image-20220328165603544](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328165603544.png)

### 5.3.字符串

[字符串](https://zh.javascript.info/string)

知道有这些个东西就行，用的时候再查。

![image-20220328165500453](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328165500453.png)

### 5.4数组

[数组 (javascript.info)](https://zh.javascript.info/array)

数组是对象

![image-20220328171054082](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328171054082.png)

#### 习题：

[在数组上下文调用](https://zh.javascript.info/array#zai-shu-zu-shang-xia-wen-tiao-yong)  很容易想错

### 5.5数组方法

由于工作中使用的比较多，详细记录一下

[数组方法](https://zh.javascript.info/array-methods)

#### 1.添加或删除数组元素

pop,push,shift,unshift就不说了。

##### splice：

```js
arr.splice(start[, deleteCount, elem1, ..., elemN])
```

它从索引 `start` 开始修改 `arr`：删除 `deleteCount` 个元素并在当前位置插入 `elem1, ..., elemN`。最后返回已被删除元素的数组。

```js
let arr = ["I", "study", "JavaScript"];

arr.splice(1, 1); // 从索引 1 开始删除 1 个元素

alert( arr ); // ["I", "JavaScript"]
```

可替换

```js
let arr = ["I", "study", "JavaScript", "right", "now"];

// 删除数组的前三项，并使用其他内容代替它们
arr.splice(0, 3, "Let's", "dance");

alert( arr ) // 现在 ["Let's", "dance", "right", "now"]
```

返回值为删除的元素

```js
let arr = ["I", "study", "JavaScript", "right", "now"];

// 删除前两个元素
let removed = arr.splice(0, 2);

alert( removed ); // "I", "study" <-- 被从数组中删除了的元素
```

不删除，直接插入

```js
let arr = ["I", "study", "JavaScript"];

// 从索引 2 开始
// 删除 0 个元素
// 然后插入 "complex" 和 "language"
arr.splice(2, 0, "complex", "language");

alert( arr ); // "I", "study", "complex", "language", "JavaScript"
```

允许负索引

```js
let arr = [1, 2, 5];

// 从索引 -1（尾端前一位）
// 删除 0 个元素，
// 然后插入 3 和 4
arr.splice(-1, 0, 3, 4);

alert( arr ); // 1,2,3,4,5
```

##### slice：

它会返回一个新数组，将所有从索引 `start` 到 `end`（不包括 `end`）的数组项复制到一个新的数组。`start` 和 `end` 都可以是负数，在这种情况下，从末尾计算索引。

```js
arr.slice([start], [end])
```

```js
let arr = ["t", "e", "s", "t"];

alert( arr.slice(1, 3) ); // e,s（复制从位置 1 到位置 3 的元素）

alert( arr.slice(-2) ); // s,t（复制从位置 -2 到尾端的元素）
```

##### concat:

```javascript
arr.concat(arg1, arg2...)
```

它接受任意数量的参数 —— 数组或值都可以。

结果是一个包含来自于 `arr`，然后是 `arg1`，`arg2` 的元素的新数组。

如果参数 `argN` 是一个数组，那么其中的所有元素都会被复制。否则，将复制参数本身。

```js
let arr = [1, 2];

// create an array from: arr and [3,4]
alert( arr.concat([3, 4]) ); // 1,2,3,4

// create an array from: arr and [3,4] and [5,6]
alert( arr.concat([3, 4], [5, 6]) ); // 1,2,3,4,5,6

// create an array from: arr and [3,4], then add values 5 and 6
alert( arr.concat([3, 4], 5, 6) ); // 1,2,3,4,5,6
```

#### 2.遍历forEach

forEach方法允许为数组的每个元素都运行一个函数。该函数的结果（如果它有返回）会被抛弃和忽略。

语法：

```javascript
arr.forEach(function(item, index, array) {
  // ... do something with item
});
```

```js
["老王", "小张", "吴老二"].forEach((item, index, array) => {
    console.log(`${item} is at index ${index} in ${array}`);
});
```

![image-20220328175846095](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328175846095.png)

#### 3.在数组中搜索

##### indexOf,includes:

[arr.indexOf](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)、[arr.lastIndexOf](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf) 和 [arr.includes](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) 方法与字符串操作具有相同的语法，并且作用基本上也与字符串的方法相同，只不过这里是对数组元素而不是字符进行操作：

- `arr.indexOf(item, from)` 从索引 `from` 开始搜索 `item`，如果找到则返回索引，否则返回 `-1`。
- `arr.lastIndexOf(item, from)` —— 和上面相同，只是从右向左搜索。
- `arr.includes(item, from)` —— 从索引 `from` 开始搜索 `item`，如果找到则返回 `true`（译注：如果没找到，则返回 `false`）。

```js
let arr = [1, 0, false];

alert( arr.indexOf(0) ); // 1
alert( arr.indexOf(false) ); // 2
alert( arr.indexOf(null) ); // -1

alert( arr.includes(1) ); // true
```

##### find,findIndex:

和forEach形式上很像，但是find有返回值，而且通常不会一直迭代

```js
let result = arr.find(function(item, index, array) {
  // 如果返回 true，则返回 item 并停止迭代
  // 对于假值（falsy）的情况，则返回 undefined
});
```

寻找id为1的user

```js
let users = [
  {id: 1, name: "John"},
  {id: 2, name: "Pete"},
  {id: 3, name: "Mary"}
];

let user = users.find(item => item.id == 1);

alert(user.name); // John
```

注意在这个例子中，我们传给了 `find` 一个单参数函数 `item => item.id == 1`。这很典型，并且 `find` 方法的其他参数很少使用。

[arr.findIndex](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex) 方法（与 `arr.find` 方法）基本上是一样的，但它返回找到元素的索引，而不是元素本身。并且在未找到任何内容时返回 `-1`。

##### filter：

`find` 方法搜索的是使函数返回 `true` 的第一个（单个）元素。

如果需要匹配的有很多，我们可以使用 [arr.filter(fn)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)。

语法与 `find` 大致相同，但是 `filter` 返回的是所有匹配元素组成的数组：

```javascript
let results = arr.filter(function(item, index, array) {
  // 如果 true item 被 push 到 results，迭代继续
  // 如果什么都没找到，则返回空数组
});
```

```js
let users = [
  {id: 1, name: "John"},
  {id: 2, name: "Pete"},
  {id: 3, name: "Mary"}
];

// 返回前两个用户的数组
let someUsers = users.filter(item => item.id < 3);

alert(someUsers.length); // 2
```

#### 4.转换数组：

##### map:

arr.map 方法是最有用和经常使用的方法之一。

它对数组的每个元素都调用函数，并返回结果数组。

语法：

```js
let result = arr.map(function(item, index, array) {
  // 返回新值而不是当前元素
})
```

```js
let array_1=["老王", "小张", "吴老二"]
let array_2=array_1.map(item => item+'，我爱你！')
console.log(array_1);
console.log(array_2);
```

![image-20220328181949675](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328181949675.png)

##### sort：

[arr.sort](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) 方法对数组进行 **原位（in-place）** 排序，更改元素的顺序。(译注：原位是指在此数组内，而非生成一个新数组。)

它还返回排序后的数组，但是返回值通常会被忽略，因为修改了 `arr` 本身。

```js
let arr = [ 1, 2, 15 ];

// 该方法重新排列 arr 的内容
arr.sort();

alert( arr );  // 1, 15, 2
```

<div style="color: red">默认以字符串排序</div>

自定义如何排序，需要传递一个函数做sort的参数，该函数有两个参数代表比较的两个值。

这两个值就是数组里的两项。

```js
function compare(a, b) {
  if (a > b) return 1; // 如果第一个值比第二个值大
  if (a == b) return 0; // 如果两个值相等
  if (a < b) return -1; // 如果第一个值比第二个值小
}
```

`arr.sort(fn)` 方法实现了通用的排序算法。我们不需要关心它的内部工作原理（大多数情况下都是经过 [快速排序](https://en.wikipedia.org/wiki/Quicksort) 或 [Timsort](https://en.wikipedia.org/wiki/Timsort) 算法优化的）。它将遍历数组，使用提供的函数比较其元素并对其重新排序，我们所需要的就是提供执行比较的函数 `fn`。



实际上，比较函数只需要返回一个正数表示“大于”，一个负数表示“小于”。

通过这个原理我们可以编写更短的函数：

```javascript
let arr = [ 1, 2, 15 ];

arr.sort(function(a, b) { return a - b; });

alert(arr);  // 1, 2, 15
```

```js
arr.sort( (a, b) => a - b );
```

##### reverse:

[arr.reverse](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse) 方法用于颠倒 `arr` 中元素的顺序。会改变原数组

例如：

```javascript
let arr = [1, 2, 3, 4, 5];
arr.reverse();

alert( arr ); // 5,4,3,2,1
```

##### split和join：

str.split通过给定的字符将字符串分割

```js
let names = 'Bilbo, Gandalf, Nazgul';

let arr = names.split(', ');

for (let name of arr) {
  alert( `A message to ${name}.` ); // A message to Bilbo（和其他名字）
}
```

`split` 方法有一个可选的第二个数字参数 —— 对数组长度的限制。如果提供了，那么额外的元素会被忽略。但实际上它很少使用：

```javascript
let arr = 'Bilbo, Gandalf, Nazgul, Saruman'.split(', ', 2);

alert(arr); // Bilbo, Gandalf
```

调用带有空参数 `s` 的 `split(s)`，会将字符串拆分为字母数组：

```javascript
let str = "test";

alert( str.split('') ); // t,e,s,t
```

[arr.join(glue)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Array/join) 与 `split` 相反。它会在它们之间创建一串由 `glue` 粘合的 `arr` 项。

例如：

```javascript
let arr = ['Bilbo', 'Gandalf', 'Nazgul'];

let str = arr.join(';'); // 使用分号 ; 将数组粘合成字符串

alert( str ); // Bilbo;Gandalf;Nazgul
```

##### reduce/reduceRight:

这部分推荐看原文。

https://zh.javascript.info/array-methods#reducereduceright

传送门：[25个你不得不知道的数组reduce高级用法 - 掘金 (juejin.cn)](https://juejin.cn/post/6844904063729926152)

[Reduce 和 Transduce 的含义 - 阮一峰的网络日志 (ruanyifeng.com)](https://www.ruanyifeng.com/blog/2017/03/reduce_transduce.html)

我在这里想演示一下[25个你不得不知道的数组reduce高级用法 - 掘金 (juejin.cn)](https://juejin.cn/post/6844904063729926152)用到的但初看不容易理解的几个方法

###### 1.替代Reverse

```js
function Reverse(arr = []) {
    return arr.reduceRight((t, v) => (t.push(v), t), []);
}

```

作者用了逗号运算符，它会执行t.push(v)，但只返回t

写成普通函数就像这样：

```js
function Reverse(arr = [1, 2, 3, 4, 5]) {
    return arr.reduceRight(function (t, v) {
        t.push(v)
        return t
    }, []);
}
```

而且注意reduceRight是从右到左遍历

###### 2.替代map（用map更好）

作者原写法是b，我写了个c方便理解。

...就是spread展开，不要不认识了

```js
const arr = [0, 1, 2, 3];

// 代替map：[0, 2, 4, 6]
const a = arr.map(v => v * 2);
const b = arr.reduce((t, v) => [...t, v * 2], []);

const c = arr.reduce(function(t,v){
     console.log([...t, v * 2]);
    return [...t, v * 2]
},[])
console.log("---------------");

console.log(a);
console.log(b);
console.log(c);

```

![image-20220328212335990](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220328212335990.png)

#### 5.thisArg

[大多数方法都支持 “thisArg”](https://zh.javascript.info/array-methods#da-duo-shu-fang-fa-du-zhi-chi-thisarg)

在函数运行时指定的 this 值，但一般大家都习惯用箭头函数了

### 5.6Iterable object（可迭代对象）

[Iterable object（可迭代对象）](https://zh.javascript.info/iterable)

#### 1.Symbol.iterator

为了让 `range` 对象可迭代（也就让 `for..of` 可以运行）我们需要为对象添加一个名为 `Symbol.iterator` 的方法（一个专门用于使对象可迭代的内建 symbol）。

1. 当 `for..of` 循环启动时，它会调用这个方法（如果没找到，就会报错）。这个方法必须返回一个 **迭代器（iterator）** —— 一个有 `next` 方法的对象。
2. 从此开始，`for..of` **仅适用于这个被返回的对象**。
3. 当 `for..of` 循环希望取得下一个数值，它就调用这个对象的 `next()` 方法。
4. `next()` 方法返回的结果的格式必须是 `{done: Boolean, value: any}`，当 `done=true` 时，表示循环结束，否则 `value` 是下一个值。

```js
let range = {
  from: 1,
  to: 5
};

// 1. for..of 调用首先会调用这个：
range[Symbol.iterator] = function() {

  // ……它返回迭代器对象（iterator object）：
  // 2. 接下来，for..of 仅与下面的迭代器对象一起工作，要求它提供下一个值
  return {
    current: this.from,
    last: this.to,

    // 3. next() 在 for..of 的每一轮循环迭代中被调用
    next() {
      // 4. 它将会返回 {done:.., value :...} 格式的对象
      if (this.current <= this.last) {
        return { done: false, value: this.current++ };
      } else {
        return { done: true };
      }
    }
  };
};

// 现在它可以运行了！
for (let num of range) {
  alert(num); // 1, 然后是 2, 3, 4, 5
}
```

#### 2.可迭代（iterable）和类数组（array-like）

这两个官方术语看起来差不多，但其实大不相同。请确保你能够充分理解它们的含义，以免造成混淆。

- **Iterable** 如上所述，是实现了 `Symbol.iterator` 方法的对象。
- **Array-like** 是有索引和 `length` 属性的对象，所以它们看起来很像数组。

可迭代对象和类数组对象通常都 **不是数组**，它们没有 `push` 和 `pop` 等方法。如果我们有一个这样的对象，并想像数组那样操作它，那就非常不方便。例如，我们想使用数组方法操作 `range`，应该如何实现呢？

就是用Array.from

#### 3.Array.from

[Array.from](https://zh.javascript.info/iterable#arrayfrom)

内容较多，推荐看原文

### 5.7Map和set

[Map and Set（映射和集合）](https://zh.javascript.info/map-set)

#### 1.Map

<div style="color: red;font-size: 20px">相同的键会被后面的键覆盖</div>

**Map 可以使用对象作为键。**

例如：

```javascript
let john = { name: "John" };

// 存储每个用户的来访次数
let visitsCountMap = new Map();

// john 是 Map 中的键
visitsCountMap.set(john, 123);

alert( visitsCountMap.get(john) ); // 123
```



```js
let john = { name: "John" };
let ben = { name: "Ben" };

let visitsCountObj = {}; // 尝试使用对象

visitsCountObj[ben] = 234; // 尝试将对象 ben 用作键
visitsCountObj[john] = 123; // 尝试将对象 john 用作键，但我们会发现使用对象 ben 作为键存下的值会被替换掉

console.log(visitsCountObj);
```

![image-20220329140057508](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220329140057508.png)

链式调用

```js
map.set('1', 'str1')
  .set(1, 'num1')
  .set(true, 'bool1');
```



#### 2.对象和map互转

当创建一个 `Map` 后，我们可以传入一个带有键值对的数组（或其它可迭代对象）来进行初始化，如下所示：

对象先转数组就可以转map了，map也可先转数组再转对象

```javascript
// 键值对 [key, value] 数组
let map = new Map([
  ['1',  'str1'],
  [1,    'num1'],
  [true, 'bool1']
]);

alert( map.get('1') ); // str1
```

[Object.entries：从对象创建 Map](https://zh.javascript.info/map-set#objectentries-cong-dui-xiang-chuang-jian-map)

[Object.fromEntries：从 Map 创建对象](https://zh.javascript.info/map-set#objectfromentries-cong-map-chuang-jian-dui-xiang)

#### 3.Set

`Set` 是一个特殊的类型集合 —— “值的集合”（没有键），它的每一个值只能出现一次。

它的主要方法如下：

- `new Set(iterable)` —— 创建一个 `set`，如果提供了一个 `iterable` 对象（通常是数组），将会从数组里面复制值到 `set` 中。
- `set.add(value)` —— 添加一个值，返回 set 本身
- `set.delete(value)` —— 删除值，如果 `value` 在这个方法调用的时候存在则返回 `true` ，否则返回 `false`。
- `set.has(value)` —— 如果 `value` 在 set 中，返回 `true`，否则返回 `false`。
- `set.clear()` —— 清空 set。
- `set.size` —— 返回元素个数。

#### 4.Set迭代

我们可以使用 `for..of` 或 `forEach` 来遍历 Set：

```javascript
let set = new Set(["oranges", "apples", "bananas"]);

for (let value of set) alert(value);

// 与 forEach 相同：
set.forEach((value, valueAgain, set) => {
  alert(value);
});
```

注意一件有趣的事儿。`forEach` 的回调函数有三个参数：一个 `value`，然后是 **同一个值** `valueAgain`，最后是目标对象。没错，同一个值在参数里出现了两次。

`forEach` 的回调函数有三个参数，是为了与 `Map` 兼容。当然，这看起来确实有些奇怪。但是这对在特定情况下轻松地用 `Set` 代替 `Map` 很有帮助，反之亦然。

`Map` 中用于迭代的方法在 `Set` 中也同样支持：

- `set.keys()` —— 遍历并返回所有的值（returns an iterable object for values），
- `set.values()` —— 与 `set.keys()` 作用相同，这是为了兼容 `Map`，
- `set.entries()` —— 遍历并返回所有的实体（returns an iterable object for entries）`[value, value]`，它的存在也是为了兼容 `Map`。

#### 习题：

[过滤字谜（anagrams）](https://zh.javascript.info/map-set#guo-lv-zi-mi-anagrams)

我的做法，有瑕疵，不能保留原始数据不满足要求。

```JS
let arr = ["nap", "teachers", "cheaters", "PAN", "ear", "era", "hectares"];

    function aclean(arr){
      //用map改造原数组
      let array=arr.map((item)=>item.toLowerCase().split('').sort().join(''))
      return Array.from(new Set(array))
    }
    alert(aclean(arr));
```

### 5.8WeakMap and WeakSet（弱映射和弱集合）

[WeakMap and WeakSet（弱映射和弱集合）](https://zh.javascript.info/weakmap-weakset)

#### 1.WeakMap

`WeakMap` 和 `Map` 的第一个不同点就是，`WeakMap` 的键必须是对象，不能是原始值：

```javascript
let weakMap = new WeakMap();

let obj = {};

weakMap.set(obj, "ok"); // 正常工作（以对象作为键）

// 不能使用字符串作为键
weakMap.set("test", "Whoops"); // Error，因为 "test" 不是一个对象
```

`WeakMap` 只有以下的方法：

- `weakMap.get(key)`
- `weakMap.set(key, value)`
- `weakMap.delete(key)`
- `weakMap.has(key)`

现在，如果我们在 weakMap 中使用一个对象作为键，并且没有其他对这个对象的引用 —— 该对象将会被从内存（和map）中自动清除。

```javascript
let john = { name: "John" };

let weakMap = new WeakMap();
weakMap.set(john, "...");

john = null; // 覆盖引用

// john 被从内存中删除了！
```

#### 2.WeakSet

传送门：[10分钟讲明白WeakSet和WeakMap的弱引用 - 掘金 (juejin.cn)](https://juejin.cn/post/7041574685363945479)

#### 3.总结

`WeakMap` 是类似于 `Map` 的集合，它仅允许对象作为键，并且一旦通过其他方式无法访问它们，便会将它们与其关联值一同删除。

`WeakSet` 是类似于 `Set` 的集合，它仅存储对象，并且一旦通过其他方式无法访问它们，便会将其删除。

它们的主要优点是它们对对象是弱引用，所以被它们引用的对象很容易地被垃圾收集器移除。

这是以不支持 `clear`、`size`、`keys`、`values` 等作为代价换来的……

`WeakMap` 和 `WeakSet` 被用作“主要”对象存储之外的“辅助”数据结构。一旦将对象从主存储器中删除，如果该对象仅被用作 `WeakMap` 或 `WeakSet` 的键，那么它将被自动清除。



### 5.9Object.keys，values，entries

#### 1.对象和数组转换

[转换对象](https://zh.javascript.info/keys-values-entries#zhuan-huan-dui-xiang)

### 5.10解构赋值

[解构赋值](https://zh.javascript.info/destructuring-assignment)

#### 1.数组解构：

##### 交换两变量:

```JS
let guest = "Jane";
let admin = "Pete";

// 让我们来交换变量的值：使得 guest = Pete，admin = Jane
[guest, admin] = [admin, guest];

alert(`${guest} ${admin}`); // Pete Jane（成功交换！）
```

交换多个变量，也是可以的(let c=3;必须打分号)

```js
let a=1
let b=2
let c=3;
[a,b,c]=[c,a,b]
console.log(a);
console.log(b);
console.log(c);
```



##### 其余的‘...’：

我们还想收集其余的数组项 —— 我们可以使用三个点 "..." 来再加一个参数以获取“其余”数组项：

```js

let [name1, name2, ...rest] = ["Julius", "Caesar", "Consul", "of the Roman Republic"];

// rest 是包含从第三项开始的其余数组项的数组
alert(rest[0]); // Consul
alert(rest[1]); // of the Roman Republic
alert(rest.length); // 2
```

还有一种用法是智能函数参数https://zh.javascript.info/destructuring-assignment#zhi-neng-han-shu-can-shu

##### 默认值：

我们想要一个“默认”值给未赋值的变量，我们可以使用 `=` 来提供：

```javascript
// 默认值
let [name = "Guest", surname = "Anonymous"] = ["Julius"];

alert(name);    // Julius（来自数组的值）
alert(surname); // Anonymous（默认值被使用了）
```

##### 忽略逗号：

数组中不想要的元素也可以通过添加额外的逗号来把它丢弃：

```javascript
// 不需要第二个元素
let [firstName, , title] = ["Julius", "Caesar", "Consul", "of the Roman Republic"];

alert( title ); // Consul
```

#### 2.对象解构

##### 基本语法：

```javascript
let {var1, var2} = {var1:…, var2:…}
```

在等号右侧应该有一个已经存在的对象，我们想把它拆分到变量中。等号左侧包含了对象相应属性的一个类对象“模式（pattern）”。在最简单的情况下，等号左侧的就是 `{...}` 中的变量名列表。

举个例子：

```javascript
let options = {
  title: "Menu",
  width: 100,
  height: 200
};

let {title, width, height} = options;

alert(title);  // Menu
alert(width);  // 100
alert(height); // 200
```

##### 顺序不重要：

```js
// 改变 let {...} 中元素的顺序
let {height, width, title} = { title: "Menu", height: 200, width: 100 }
```

##### 设置变量：

```js
let options = {
  title: "Menu",
  width: 100,
  height: 200
};

// { sourceProperty: targetVariable }
let {width: w, height: h, title} = options;

// width -> w
// height -> h
// title -> title

alert(title);  // Menu
alert(w);      // 100
alert(h);      // 200
```

##### 设置默认值：

```js
let options = {
  title: "Menu"
};

let {width = 100, height = 200, title} = options;

alert(title);  // Menu
alert(width);  // 100
alert(height); // 200
```

##### 剩余模式：

```js
let options = {
  title: "Menu",
  height: 200,
  width: 100
};

// title = 名为 title 的属性
// rest = 存有剩余属性的对象
let {title, ...rest} = options;

// 现在 title="Menu", rest={height: 200, width: 100}
alert(rest.height);  // 200
alert(rest.width);   // 100
```

##### 需注意：

就像数组或函数参数一样，默认值可以是任意表达式甚至可以是函数调用。

<div style="color: red">它们只会在未提供对应的值时才会被计算/调用。</div>

```js
let options = {
  title: "Menu"
};

let {width = prompt("width?"), title = prompt("title?")} = options;

alert(title);  // Menu  不会执行prompt("title?")，因为title已经有值了
alert(width);  // (prompt 的返回值)
```

<div style="color: red">不使用 `let` 时的陷阱</div>

在上面的示例中，变量都是在赋值中通过正确方式声明的：`let {…} = {…}`。当然，我们也可以使用已有的变量，而不用 `let`，但这里有一个陷阱。

以下代码无法正常运行：

```javascript
let title, width, height;

// 这一行发生了错误
{title, width, height} = {title: "Menu", width: 200, height: 100};
```

问题在于 JavaScript 把主代码流（即不在其他表达式中）的 `{...}` 当做一个代码块。这样的代码块可以用于对语句分组，如下所示：

```javascript
{
  // 一个代码块
  let message = "Hello";
  // ...
  alert( message );
}
```

因此，这里 JavaScript 假定我们有一个代码块，这就是报错的原因。我们需要解构它。

为了告诉 JavaScript 这不是一个代码块，我们可以把整个赋值表达式用括号 `(...)` 包起来：

```javascript
let title, width, height;

// 现在就可以了
({title, width, height} = {title: "Menu", width: 200, height: 100});

alert( title ); // Menu
```

#### 3.函数参数使用解构赋值

参数太多，用对象传递，使用解构赋值，参数解构十分清晰

```js
let options = {
  title: "My menu",
  items: ["Item1", "Item2"]
};

function showMenu({
  title = "Untitled",
  width: w = 100,  // width goes to w
  height: h = 200, // height goes to h
  items: [item1, item2] // items first element goes to item1, second to item2
}) {
  alert( `${title} ${w} ${h}` ); // My Menu 100 200
  alert( item1 ); // Item1
  alert( item2 ); // Item2
}

showMenu(options);
```



#### 习题：

[最高薪资](https://zh.javascript.info/destructuring-assignment#zui-gao-xin-zi)

### 5.11.日期和时间

[日期和时间](https://zh.javascript.info/date)

api很多，推荐看原文，都是干货。

#### 习题:

##### [某月的最后一天？](https://zh.javascript.info/date#mou-yue-de-zui-hou-yi-tian)

写一个函数 `getLastDayOfMonth(year, month)` 返回 month 月的最后一天。有时候是 30，有时是 31，甚至在二月的时候会是 28/29。

参数：

- `year` —— 四位数的年份，比如 2012。
- `month` —— 月份，从 0 到 11。

举个例子，`getLastDayOfMonth(2012, 1) = 29`（闰年，二月）

我的代码，和答案一个意思

```JS
<script>
    // let date = new Date(2015, 0, 2);

    // getLastDayOfMonth(2012, 1) = 29
    getLastDayOfMonth(2012, 1)

    function getLastDayOfMonth(year,month){
      //把日期加一个月,有自动校准，不用担心12月的情况
      let date1=new Date(year,month+1)
      // 天数最小可以设置为 1，所以这里设置的是上一月的最后一天
      date1.setDate(0)
      return date1.getDate();
    }
  </script>
```



##### [今天过去了多少秒？](https://zh.javascript.info/date#jin-tian-guo-qu-le-duo-shao-miao)

写一个函数 `getSecondsToday()`，返回今天已经过去了多少秒？

例如：如果现在是 `10:00 am`，并且没有夏令时转换，那么：

```javascript
getSecondsToday() == 36000 // (3600 * 10)
```

该函数应该在任意一天都能正确运行。那意味着，它不应具有“今天”的硬编码值。

我的是答案的第二种解法

```JS
 getSecondsToday()
    function getSecondsToday(){
      let date=new Date()
     
      console.log(date.getHours()*3600+date.getMinutes()*60+date.getSeconds());
    }
```



##### [距离明天还有多少秒？](https://zh.javascript.info/date#ju-li-ming-tian-huan-you-duo-shao-miao)

写一个函数 `getSecondsToTomorrow()`，返回距离明天的秒数。

例如，现在是 `23:00`，那么：

```javascript
getSecondsToTomorrow() == 3600
```

P.S. 该函数应该在任意一天都能正确运行。那意味着，它不应具有“今天”的硬编码值。

我的是答案的第一种解法

```JS
 getSecondsToTomorrow()
    function getSecondsToTomorrow(){
      let date=new Date()
      let date1=new Date(date.getFullYear(),date.getMonth(),date.getDate()+1)
      console.log((date1-date)/1000);
    }
```

##### [格式化相对日期](https://zh.javascript.info/date#ge-shi-hua-xiang-dui-ri-qi)

写一个函数 `formatDate(date)`，能够对 `date` 进行如下格式化：

- 如果 `date` 距离现在不到 1 秒，输出 `"right now"`。
- 否则，如果 `date` 距离现在不到 1 分钟，输出 `"n sec. ago"`。
- 否则，如果不到 1 小时，输出 `"m min. ago"`。
- 否则，以 `"DD.MM.YY HH:mm"` 格式输出完整日期。即：`"day.month.year hours:minutes"`，全部以两位数格式表示，例如：`31.12.16 10:00`。

举个例子：

```javascript
alert( formatDate(new Date(new Date - 1)) ); // "right now"

alert( formatDate(new Date(new Date - 30 * 1000)) ); // "30 sec. ago"

alert( formatDate(new Date(new Date - 5 * 60 * 1000)) ); // "5 min. ago"

// 昨天的日期，例如 31.12.16 20:00
alert( formatDate(new Date(new Date - 86400 * 1000)) );
```

我的这个不是很严谨，要注意取整

```JS
	formatDate(new Date(new Date - 1)); // "right now"

    formatDate(new Date(new Date - 30 * 1000)); // "30 sec. ago"

    formatDate(new Date(new Date - 5 * 60 * 1000)); // "5 min. ago"

    // 昨天的日期，例如 31.12.16 20:00
    formatDate(new Date(new Date - 86400 * 1000));
    function formatDate(date) {
      let now = Date.now() / 1000
      let sec = date.getTime() / 1000
      let cha = now - sec
      if (cha <= 1) {
        console.log("right now");
      } else if (cha > 1 && cha <= 60) {
        console.log(cha + " sec. ago");
      } else if (cha > 60 && cha <= 3600) {
        console.log(cha / 60 + " min. ago");
      } else {
        console.log(date.getDate() + "." + (+date.getMonth()+1) + "." + date.getFullYear() + " " + date.getHours() + ":" + date.getMinutes() + ".");
      }
```

### 5.12JSON 方法，toJSON

[JSON 方法，toJSON](https://zh.javascript.info/json)

#### 1.JSON.stringfy

```js
let student = {
  name: 'John',
  age: 30,
  isAdmin: false,
  courses: ['html', 'css', 'js'],
  wife: null
};

let json = JSON.stringify(student);

alert(typeof json); // we've got a string!

alert(json);
/* JSON 编码的对象：
{
  "name": "John",
  "age": 30,
  "isAdmin": false,
  "courses": ["html", "css", "js"],
  "wife": null
}
*/
```

##### 需注意：

- 字符串使用双引号。JSON 中没有单引号或反引号。所以 `'John'` 被转换为 `"John"`。
- 对象属性名称也是双引号的。这是强制性的。所以 `age:30` 被转换成 `"age":30`。



JSON 是语言无关的纯数据规范，因此一些特定于 JavaScript 的对象属性会被 `JSON.stringify` 跳过。

即：

- 函数属性（方法）。
- Symbol 类型的键和值。
- 存储 `undefined` 的属性。

```js
let user = {
  sayHi() { // 被忽略
    alert("Hello");
  },
  [Symbol("id")]: 123, // 被忽略
  something: undefined // 被忽略
};

alert( JSON.stringify(user) ); // {}（空对象）
```

<div style="color: red">JSON支持嵌套对象转换，不支持循环引用</div>

```js
let room = {
  number: 23
};

let meetup = {
  title: "Conference",
  participants: ["john", "ann"]
};

meetup.place = room;       // meetup 引用了 room
room.occupiedBy = meetup; // room 引用了 meetup

JSON.stringify(meetup); // Error: Converting circular structure to JSON
```

#### 2.replacer

就是说我们可以利用第二个replacer参数，分析并替换/跳过整个对象。感觉实际工作中应该用的不多吧

`JSON.stringify` 的完整语法是：

```javascript
let json = JSON.stringify(value[, replacer, space])
```

- value

  要编码的值。

- replacer

  要编码的属性数组或映射函数 `function(key, value)`。

- space

  用于格式化的空格数量

如果我们传递一个属性数组给它，那么只有这些属性会被编码。

例如：

```javascript
let room = {
  number: 23
};

let meetup = {
  title: "Conference",
  participants: [{name: "John"}, {name: "Alice"}],
  place: room // meetup 引用了 room
};

room.occupiedBy = meetup; // room 引用了 meetup

alert( JSON.stringify(meetup, ['title', 'participants']) );
// {"title":"Conference","participants":[{},{}]}
```

这里我们可能过于严格了。属性列表应用于了整个对象结构。所以 `participants` 是空的，因为 `name` 不在列表中。

让我们包含除了会导致循环引用的 `room.occupiedBy` 之外的所有属性：

```javascript
let room = {
  number: 23
};

let meetup = {
  title: "Conference",
  participants: [{name: "John"}, {name: "Alice"}],
  place: room // meetup 引用了 room
};

room.occupiedBy = meetup; // room 引用了 meetup

alert( JSON.stringify(meetup, ['title', 'participants', 'place', 'name', 'number']) );
/*
{
  "title":"Conference",
  "participants":[{"name":"John"},{"name":"Alice"}],
  "place":{"number":23}
}
*/
```

我们可以使用一个函数代替数组作为 replacer。

该函数会为每个 (key,value) 对调用并返回“已替换”的值，该值将替换原有的值。如果值被跳过了，则为 undefined。

在我们的例子中，我们可以为 occupiedBy 以外的所有内容按原样返回 value。为了 occupiedBy，下面的代码返回 undefined：

```js
let room = {
  number: 23
};

let meetup = {
  title: "Conference",
  participants: [{name: "John"}, {name: "Alice"}],
  place: room // meetup 引用了 room
};

room.occupiedBy = meetup; // room 引用了 meetup

alert( JSON.stringify(meetup, function replacer(key, value) {
  alert(`${key}: ${value}`);
  return (key == 'occupiedBy') ? undefined : value;
}));

/* key:value pairs that come to replacer:
:             [object Object]
title:        Conference
participants: [object Object],[object Object]
0:            [object Object]
name:         John
1:            [object Object]
name:         Alice
place:        [object Object]
number:       23
occupiedBy: [object Object]
```

请注意 `replacer` 函数会获取每个键/值对，包括嵌套对象和数组项。它被递归地应用。`replacer` 中的 `this` 的值是包含当前属性的对象。

第一个调用很特别。它是使用特殊的“包装对象”制作的：`{"": meetup}`。换句话说，第一个 `(key, value)` 对的键是空的，并且该值是整个目标对象。这就是上面的示例中第一行是 `":[object Object]"` 的原因。

这个理念是为了给 `replacer` 提供尽可能多的功能：如果有必要，它有机会分析并替换/跳过整个对象。

#### 3.自定义toJSON

像 `toString` 进行字符串转换，对象也可以提供 `toJSON` 方法来进行 JSON 转换。如果可用，`JSON.stringify` 会自动调用它。

```js
let room = {
  number: 23,
  toJSON() {
    return this.number;
  }
};

let meetup = {
  title: "Conference",
  room
};

alert( JSON.stringify(room) ); // 23

alert( JSON.stringify(meetup) );
/*
  {
    "title":"Conference",
    "room": 23
  }
*/
```

#### 4.JSON.parse

用于解码 JSON 字符串

```javascript
let value = JSON.parse(str, [reviver]);
```

- str

  要解析的 JSON 字符串。

- reviver

  可选的函数 function(key,value)，该函数将为每个 `(key, value)` 对调用，并可以对值进行转换。

```js
let userData = '{ "name": "John", "age": 35, "isAdmin": false, "friends": [0,1,2,3] }';

let user = JSON.parse(userData);

alert( user.friends[1] ); // 1
```

使用reviver分析JSON字符串

```js
let schedule = `{
  "meetups": [
    {"title":"Conference","date":"2017-11-30T12:00:00.000Z"},
    {"title":"Birthday","date":"2017-04-18T12:00:00.000Z"}
  ]
}`;

schedule = JSON.parse(schedule, function(key, value) {
  if (key == 'date') return new Date(value);
  return value;
});

alert( schedule.meetups[1].date.getDate() ); // 正常运行了！
```

#### 习题：

很好的题目值得搜藏

[排除反向引用](https://zh.javascript.info/json#pai-chu-fan-xiang-yin-yong)

## 6.函数进阶内容

### 6.2Rest 参数与 Spread 语法

[Rest 参数与 Spread 语法](https://zh.javascript.info/rest-parameters-spread)

#### 1.Rest参数

Rest 参数可以通过使用三个点 `...` 并在后面跟着包含剩余参数的数组名称，来将它们包含在函数定义中。这些点的字面意思是“将剩余参数收集到一个数组中”。

```js
function sumAll(...args) { // 数组名为 args
  let sum = 0;

  for (let arg of args) sum += arg;

  return sum;
}

alert( sumAll(1) ); // 1
alert( sumAll(1, 2) ); // 3
alert( sumAll(1, 2, 3) ); // 6
```

搭配可视参数使用

```js
function showName(firstName, lastName, ...titles) {
  alert( firstName + ' ' + lastName ); // Julius Caesar

  // 剩余的参数被放入 titles 数组中
  // i.e. titles = ["Consul", "Imperator"]
  alert( titles[0] ); // Consul
  alert( titles[1] ); // Imperator
  alert( titles.length ); // 2
}

showName("Julius", "Caesar", "Consul", "Imperator");
```

<div style="color: red">Rest 参数必须放到参数列表的末尾</div>

Rest 参数会收集剩余的所有参数，因此下面这种用法没有意义，并且会导致错误：

```javascript
function f(arg1, ...rest, arg2) { // arg2 在 ...rest 后面？！
  // error
}
```

#### 2.arguments变量

有一个名为 arguments 的特殊的类数组对象，该对象按参数索引包含所有参数。

例如：

```js


function showName() {
  alert( arguments.length );
  alert( arguments[0] );
  alert( arguments[1] );

  // 它是可遍历的
  // for(let arg of arguments) alert(arg);
}

// 依次显示：2，Julius，Caesar
showName("Julius", "Caesar");

// 依次显示：1，Ilya，undefined（没有第二个参数）
showName("Ilya");
```

在过去，JavaScript 中没有 rest 参数，而使用 `arguments` 是获取函数所有参数的唯一方法。现在它仍然有效，我们可以在一些老代码里找到它。

但缺点是，尽管 `arguments` 是一个类数组，也是可迭代对象，但它终究不是数组。它不支持数组方法，因此我们不能调用 `arguments.map(...)` 等方法。

此外，它始终包含所有参数，我们不能像使用 rest 参数那样只截取入参的一部分。

因此，当我们需要这些功能时，最好使用 rest 参数。

<div style="color: red">箭头函数是没有 "arguments"</div>

#### 3.Spread语法

当在函数调用中使用 `...arr` 时，它会把可迭代对象 `arr` “展开”到参数列表中。

以 `Math.max` 为例：

```javascript
let arr = [3, 5, 1];

alert( Math.max(...arr) ); // 5（spread 语法把数组转换为参数列表）
```

我们还可以通过这种方式传递多个可迭代对象：

```javascript
let arr1 = [1, -2, 3, 4];
let arr2 = [8, 3, -8, 1];

alert( Math.max(...arr1, ...arr2) ); // 8
```

我们甚至还可以将 spread 语法与常规值结合使用：

```javascript
let arr1 = [1, -2, 3, 4];
let arr2 = [8, 3, -8, 1];

alert( Math.max(1, ...arr1, 2, ...arr2, 25) ); // 25
```

并且，我们还可以使用 spread 语法来合并数组：

```javascript
let arr = [3, 5, 1];
let arr2 = [8, 9, 15];

let merged = [0, ...arr, 2, ...arr2];

alert(merged); // 0,3,5,1,2,8,9,15（0，然后是 arr，然后是 2，然后是 arr2）
```

Spread 语法内部使用了迭代器来收集元素，与 `for..of` 的方式相同。

```js
let str = "Hello";

alert( [...str] ); // H,e,l,l,o
```

注意和Array.from的区别

`Array.from(obj)` 和 `[...obj]` 存在一个细微的差别：

- `Array.from` 适用于类数组对象也适用于可迭代对象。
- Spread 语法只适用于可迭代对象。

### 6.3变量作用域，闭包

[变量作用域，闭包](https://zh.javascript.info/closure)

#### 1.代码块

如果在代码块 `{...}` 内声明了一个变量，那么这个变量只在该代码块内可见。

例如：

```javascript
{
  // 使用在代码块外不可见的局部变量做一些工作

  let message = "Hello"; // 只在此代码块内可见

  alert(message); // Hello
}

alert(message); // Error: message is not defined
```

隔离代码

```js
{
  // 显示 message
  let message = "Hello";
  alert(message);
}

{
  // 显示另一个 message
  let message = "Goodbye";
  alert(message);
}
```

对于 `if`，`for` 和 `while` 等，在 `{...}` 中声明的变量也仅在内部可见：

if

```javascript
if (true) {
  let phrase = "Hello!";

  alert(phrase); // Hello!
}

alert(phrase); // Error, no such variable!
```

循环

```js
for (let i = 0; i < 3; i++) {
  // 变量 i 仅在这个 for 循环的内部可见
  alert(i); // 0，然后是 1，然后是 2
}

alert(i); // Error, no such variable
```

#### 2.后续

文章写的太难懂了，推荐文章

[我从来不理解JavaScript闭包，直到有人这样向我解释它 - 掘金 (juejin.cn)](https://juejin.cn/post/6844903858636849159#heading-6)

我将永远记住闭包的方法是通过背包的类比。当一个函数被创建并传递或从另一个函数返回时，它会携带一个背包。背包中是函数声明时作用域内的所有变量。



### 6.4旧时的var

[旧时的 "var"](https://zh.javascript.info/var)

#### 1.var没有块级作用域

if：

```js
if (true) {
  var test = true; // 使用 "var" 而不是 "let"
}

alert(test); // true，变量在 if 结束后仍存在
```

循环：

```js
for (var i = 0; i < 10; i++) {
  var one = 1;
  // ...
}

alert(i);   // 10，"i" 在循环结束后仍可见，它是一个全局变量
alert(one); // 1，"one" 在循环结束后仍可见，它是一个全局变量
```

如果一个代码块位于函数内部，那么 `var` 声明的变量的作用域将为函数作用域：

```javascript
function sayHi() {
  if (true) {
    var phrase = "Hello";
  }

  alert(phrase); // 能正常工作
}

sayHi();
alert(phrase); // ReferenceError: phrase is not defined
```

#### 2.重复声明

使用 `var`，我们可以重复声明一个变量，不管多少次都行。如果我们对一个已经声明的变量使用 `var`，这条新的声明语句会被忽略：

```javascript
var user = "Pete";

var user = "John"; // 这个 "var" 无效（因为变量已经声明过了）
// ……不会触发错误

alert(user); // John
```

#### 3.变量提升

`var` 声明的变量会在函数开头被定义，与它在代码中定义的位置无关

```javascript
function sayHi() {
  phrase = "Hello";

  alert(phrase);

  var phrase;
}
sayHi();
```

……从技术上讲，它与下面这种情况是一样的（`var phrase` 被上移至函数开头）：

```javascript
function sayHi() {
  var phrase;

  phrase = "Hello";

  alert(phrase);
}
sayHi();
```

……甚至与这种情况也一样（记住，代码块是会被忽略的）：

```javascript
function sayHi() {
  phrase = "Hello"; // (*)

  if (false) {
    var phrase;
  }

  alert(phrase);
}
sayHi();
```

人们将这种行为称为“提升”（英文为 “hoisting” 或 “raising”），因为所有的 `var` 都被“提升”到了函数的顶部。

所以，在上面的例子中，`if (false)` 分支永远都不会执行，但没关系，它里面的 `var` 在函数刚开始时就被处理了，所以在执行 `(*)` 那行代码时，变量是存在的。

**声明会被提升，但是赋值不会。**

我们最好用例子来说明：

```javascript
function sayHi() {
  alert(phrase);

  var phrase = "Hello";
}

sayHi();
```

`var phrase = "Hello"` 这行代码包含两个行为：

1. 使用 `var` 声明变量
2. 使用 `=` 给变量赋值。

声明在函数刚开始执行的时候（“提升”）就被处理了，但是赋值操作始终是在它出现的地方才起作用。所以这段代码实际上是这样工作的：

```javascript
function sayHi() {
  var phrase; // 在函数刚开始时进行变量声明

  alert(phrase); // undefined

  phrase = "Hello"; // ……赋值 — 当程序执行到这一行时。
}

sayHi();
```

#### 4.IIFE

就是立即执行函数

在之前，JavaScript 中只有 `var` 这一种声明变量的方式，并且这种方式声明的变量没有块级作用域，程序员们就发明了一种模仿块级作用域的方法。这种方法被称为“立即调用函数表达式”（immediately-invoked function expressions，IIFE）。

如今，我们不应该再使用 IIFE 了，但是你可以在旧脚本中找到它们。

IIFE 看起来像这样：

```javascript
(function() {

  var message = "Hello";

  alert(message); // Hello

})();
```

这里，创建了一个函数表达式并立即调用。因此，代码立即执行并拥有了自己的私有变量。

函数表达式被括号 `(function {...})` 包裹起来，因为当 JavaScript 引擎在主代码中遇到 `"function"` 时，它会把它当成一个函数声明的开始。但函数声明必须有一个函数名，所以这样的代码会导致错误：

```javascript
// 尝试声明并立即调用一个函数
function() { // <-- SyntaxError: Function statements require a function name

  var message = "Hello";

  alert(message); // Hello

}();
```

即使我们说：“好吧，那我们加一个名称吧”，但它仍然不工作，因为 JavaScript 不允许立即调用函数声明：

```javascript
// 下面的括号会导致语法错误
function go() {

}(); // <-- 不能立即调用函数声明
```

因此，需要使用圆括号把该函数表达式包起来，以告诉 JavaScript，这个函数是在另一个表达式的上下文中创建的，因此它是一个函数表达式：它不需要函数名，可以立即调用。

除了使用括号，还有其他方式可以告诉 JavaScript 在这我们指的是函数表达式：

```javascript
// 创建 IIFE 的方法

(function() {
  alert("Parentheses around the function");
})();

(function() {
  alert("Parentheses around the whole thing");
}());

!function() {
  alert("Bitwise NOT operator starts the expression");
}();

+function() {
  alert("Unary plus starts the expression");
}();
```

在上面的所有情况中，我们都声明了一个函数表达式并立即运行它。请再注意一下：如今我们没有理由来编写这样的代码。

### 6.6函数对象，NFE

#### name属性：

（感觉没什么用）

一个函数的名字可以通过属性 “name” 来访问：

```javascript
function sayHi() {
  alert("Hi");
}

alert(sayHi.name); // sayHi
```

名称赋值的逻辑很智能。即使函数被创建时没有名字，名称赋值的逻辑也能给它赋予一个正确的名字，然后进行赋值：

```javascript
let sayHi = function() {
  alert("Hi");
};

alert(sayHi.name); // sayHi（有名字！）
```

#### length属性：

内建属性 “length”，它返回函数入参的个数，比如：

```javascript
function f1(a) {}
function f2(a, b) {}
function many(a, b, ...more) {}

alert(f1.length); // 1
alert(f2.length); // 2
alert(many.length); // 2
```

#### 自定义属性：

我们添加了 `counter` 属性，用来跟踪总的调用次数：

```javascript
function sayHi() {
  alert("Hi");

  // 计算调用次数
  sayHi.counter++;
}
sayHi.counter = 0; // 初始值

sayHi(); // Hi
sayHi(); // Hi

alert( `Called ${sayHi.counter} times` ); // Called 2 times
```

<div style="color: red">属性不是变量</div>



被赋值给函数的属性，比如 `sayHi.counter = 0`，**不会** 在函数内定义一个局部变量 `counter`。换句话说，属性 `counter` 和变量 `let counter` 是毫不相关的两个东西。

我们可以把函数当作对象，在它里面存储属性，但是这对它的执行没有任何影响。变量不是函数属性，反之亦然。它们之间是平行的。

### 6.7new Function语法

["new Function" 语法](https://zh.javascript.info/new-function)

#### 1.new Function

创建函数的语法：

```javascript
let func = new Function ([arg1, arg2, ...argN], functionBody);
```

该函数是通过使用参数 `arg1...argN` 和给定的 `functionBody` 创建的。

下面这个例子可以帮助你理解创建语法。这是一个带有两个参数的函数：

```javascript
let sum = new Function('a', 'b', 'return a + b');

alert( sum(1, 2) ); // 3
```

这里有一个没有参数的函数，只有函数体：

```javascript
let sayHi = new Function('alert("Hello")');

sayHi(); // Hello
```

与我们已知的其他方法相比，这种方法最大的不同在于，它实际上是通过运行时通过参数传递过来的字符串创建的。

#### 2.闭包

使用 `new Function` 创建一个函数，那么该函数的 `[[Environment]]` 并不指向当前的词法环境，而是指向全局环境。

因此，此类函数无法访问外部（outer）变量，只能访问全局变量。

```javascript
function getFunc() {
  let value = "test";

  let func = new Function('alert(value)');

  return func;
}

getFunc()(); // error: value is not defined  因为没有一个叫value的全局变量
```

将其与常规行为进行比较：

```javascript
function getFunc() {
  let value = "test";

  let func = function() { alert(value); };

  return func;
}

getFunc()(); // "test"，从 getFunc 的词法环境中获取的
```

由于历史原因，参数也可以按逗号分隔符的形式给出。

以下三种声明的含义相同：

```javascript
new Function('a', 'b', 'return a + b'); // 基础语法
new Function('a,b', 'return a + b'); // 逗号分隔
new Function('a , b', 'return a + b'); // 逗号和空格分隔
```

### 6.8setTimeOut,setInterval

[调度：setTimeout 和 setInterval](https://zh.javascript.info/settimeout-setinterval)

#### 1.setTimeOut

`setTimeout` 允许我们将函数推迟到一段时间间隔之后再执行。

语法：

```javascript
let timerId = setTimeout(func|code, [delay], [arg1], [arg2], ...)
```

参数说明：

- `func|code`

  想要执行的函数或代码字符串。 一般传入的都是函数。由于某些历史原因，支持传入代码字符串，但是不建议这样做。

- `delay`

  执行前的延时，以毫秒为单位（1000 毫秒 = 1 秒），默认值是 0；

- `arg1`，`arg2`…

  要传入被执行函数（或代码字符串）的参数列表（IE9 以下不支持）

例如，在下面这个示例中，`sayHi()` 方法会在 1 秒后执行：

```javascript
function sayHi() {
  alert('Hello');
}

setTimeout(sayHi, 1000);
```

带参数的情况：

```javascript
function sayHi(phrase, who) {
  alert( phrase + ', ' + who );
}

setTimeout(sayHi, 1000, "Hello", "John"); // Hello, John
```

如果第一个参数位传入的是字符串，JavaScript 会自动为其创建一个函数。

所以这么写也是可以的：

```javascript
setTimeout("alert('Hello')", 1000);
```

但是，不建议使用字符串，我们可以使用箭头函数代替它们，如下所示：

```javascript
setTimeout(() => alert('Hello'), 1000);
```

##### 取消调度：

`setTimeout` 在调用时会返回一个“定时器标识符（timer identifier）”，在我们的例子中是 `timerId`，我们可以使用它来取消执行。

取消调度的语法：

```javascript
let timerId = setTimeout(...);
clearTimeout(timerId);
```

在下面的代码中，我们对一个函数进行了调度，紧接着取消了这次调度（中途反悔了）。所以最后什么也没发生：

```javascript
let timerId = setTimeout(() => alert("never happens"), 1000);
alert(timerId); // 定时器标识符

clearTimeout(timerId);
alert(timerId); // 还是这个标识符（并没有因为调度被取消了而变成 null）
```

返回值`timerId`是一个正整数，表示定时器的编号。这个值可以传递给[`clearTimeout()`](https://developer.mozilla.org/zh-CN/docs/Web/API/clearTimeout)来取消该定时器。

#### 2.setInterval

`setInterval` 方法和 `setTimeout` 的语法相同：

```javascript
let timerId = setInterval(func|code, [delay], [arg1], [arg2], ...)
```

所有参数的意义也是相同的。不过与 `setTimeout` 只执行一次不同，`setInterval` 是每间隔给定的时间周期性执行。

想要阻止后续调用，我们需要调用 `clearInterval(timerId)`。

下面的例子将每间隔 2 秒就会输出一条消息。5 秒之后，输出停止：

```javascript
// 每 2 秒重复一次
let timerId = setInterval(() => alert('tick'), 2000);

// 5 秒之后停止
setTimeout(() => { clearInterval(timerId); alert('stop'); }, 5000);
```

#### 3.嵌套的setTimeOut

周期性调度有两种方式。

一种是使用 `setInterval`，另外一种就是嵌套的 `setTimeout`，就像这样：

```javascript
/** instead of:
let timerId = setInterval(() => alert('tick'), 2000);
*/

let timerId = setTimeout(function tick() {
  alert('tick');
  timerId = setTimeout(tick, 2000); // (*)
}, 2000);
```

上面这个 `setTimeout` 在当前这一次函数执行完时 `(*)` 立即调度下一次调用。

嵌套的 `setTimeout` 要比 `setInterval` 灵活得多。采用这种方式可以根据当前执行结果来调度下一次调用，因此下一次调用可以与当前这一次不同。

<div style="color: red">嵌套的 `setTimeout` 能够精确地设置两次执行之间的延时，而 `setInterval` 却不能。</div>

下面来比较这两个代码片段。第一个使用的是 `setInterval`：

```javascript
let i = 1;
setInterval(function() {
  func(i++);
}, 100);
```

看起来，每隔100ms执行一次i++，实际上i++本身也会消耗一部分间隔时间。所以**使用 `setInterval` 时，`func` 函数的实际调用间隔要比代码中设定的时间间隔要短！**也可能出现这种情况，就是 `func` 的执行所花费的时间比我们预期的时间更长，并且超出了 100 毫秒。

​		在这种情况下，JavaScript 引擎会等待 `func` 执行完成，然后检查调度程序，如果时间到了，则 **立即** 再次执行它。极端情况下，如果函数每次执行时间都超过 `delay` 设置的时间，那么每次调用之间将完全没有停顿。



第二个使用的是嵌套的 `setTimeout`：

```javascript
let i = 1;
setTimeout(function run() {
  func(i++);
  setTimeout(run, 100);
}, 100);
```

**嵌套的 `setTimeout` 就能确保延时的固定（这里是 100 毫秒）。**

这是因为下一次调用是在前一次调用完成时再调度的。

#### 4.零延时的setTimeOut

这儿有一种特殊的用法：`setTimeout(func, 0)`，或者仅仅是 `setTimeout(func)`。这样调度可以让 `func` 尽快执行。但是只有在当前正在执行的脚本执行完成后，调度程序才会调用它。也就是说，该函数被调度在当前脚本执行完成“之后”立即执行。

例如，下面这段代码会先输出 “Hello”，然后立即输出 “World”：

```javascript
setTimeout(() => alert("World"));

alert("Hello");
```

第一行代码“将调用安排到日程（calendar）0 毫秒处”。但是调度程序只有在当前脚本执行完毕时才会去“检查日程”，所以先输出 `"Hello"`，然后才输出 `"World"`。

![image-20220331123451961](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220331123451961.png)

### 6.9装饰器模式和转发，call/apply

[装饰器模式和转发，call/apply](https://zh.javascript.info/call-apply-decorators)

文中提到的装饰器模式，举的例子有点难理解，推荐看原文

#### 1.func.call

有一个特殊的内建函数方法 [func.call(context, …args)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Function/call)，它允许调用一个显式设置 `this` 的函数。

语法如下：

```javascript
func.call(context, arg1, arg2, ...)
```

它运行 `func`，提供的第一个参数作为 `this`，后面的作为参数（arguments）。

简单地说，这两个调用几乎相同：

```javascript
func(1, 2, 3);
func.call(obj, 1, 2, 3)
```

它们调用的都是 `func`，参数是 `1`、`2` 和 `3`。唯一的区别是 `func.call` 还会将 `this` 设置为 `obj`。

例如，在下面的代码中，我们在不同对象的上下文中调用 `sayHi`：`sayHi.call(user)` 运行 `sayHi` 并提供了 `this=user`，然后下一行设置 `this=admin`：

```javascript
function sayHi() {
  alert(this.name);
}

let user = { name: "John" };
let admin = { name: "Admin" };

// 使用 call 将不同的对象传递为 "this"
sayHi.call( user ); // John
sayHi.call( admin ); // Admin
```

在这里我们用带有给定上下文和 phrase 的 `call` 调用 `say`：

```javascript
function say(phrase) {
  alert(this.name + ': ' + phrase);
}

let user = { name: "John" };

// user 成为 this，"Hello" 成为第一个参数
say.call( user, "Hello" ); // John: Hello
```

#### 2.func.apply

可以使用 `func.apply(this, arguments)` 代替 `func.call(this, ...arguments)`。

内建方法 [func.apply](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Function/apply) 的语法是：

```javascript
func.apply(context, args)
```

它运行 `func` 设置 `this=context`，并使用类数组对象 `args` 作为参数列表（arguments）。

`call` 和 `apply` 之间唯一的语法区别是，`call` 期望一个参数列表，而 `apply` 期望一个包含这些参数的类数组对象。

因此，这两个调用几乎是等效的：

```javascript
func.call(context, ...args);
func.apply(context, args);
```

它们使用给定的上下文和参数执行相同的 `func` 调用。

只有一个关于 `args` 的细微的差别：

- Spread 语法 `...` 允许将 **可迭代对象** `args` 作为列表传递给 `call`。
- `apply` 只接受 **类数组** `args`。

……对于即可迭代又是类数组的对象，例如一个真正的数组，我们使用 `call` 或 `apply` 均可，但是 `apply` 可能会更快，因为大多数 JavaScript 引擎在内部对其进行了优化。

#### 习题：

##### 防抖装饰器：

```js
function debounce(func, ms) {
    let timeout;
    return function() {
        clearTimeout(timeout);
        timeout = setTimeout(() => func.apply(this, arguments), ms);
        console.log("定时器编号："+timeout);
    };
}

  function print_1(num){
        console.log(num+"------------"+num);
  }
  let print = debounce(print_1,2000)

  print(1)
  print(2)
  print(3)
  print(4)
  print(5)
  print(6)
  print(7)
  print(8)
  print(9)
  print(100)

```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/83.gif" style="zoom: 100%"></img>

##### 节流装饰器：

```js
function f(a) {
    console.log(a);
}

let f1000 = throttle(f, 1000);

f1000(1); // 显示 1
f1000(2); // (节流，尚未到 1000ms)
f1000(2); // (节流，尚未到 1000ms)
f1000(2); // (节流，尚未到 1000ms)
f1000(2); // (节流，尚未到 1000ms)
f1000(2); // (节流，尚未到 1000ms)
f1000(3); // (节流，尚未到 1000ms)

function throttle(func, ms) {

    let isThrottled = false,
        savedArgs,
        savedThis;

    function wrapper() {

        if (isThrottled) { // (2)
            savedArgs = arguments;
            savedThis = this;
            console.log(savedArgs,"if");
            return;
        }
        isThrottled = true;
       
        func.apply(this, arguments); // (1)

        setTimeout(function () {
            isThrottled = false; // (3)
            console.log(savedArgs,"setTimeOut");
            if (savedArgs) {
                wrapper.apply(savedThis, savedArgs);
                savedArgs = savedThis = null;
                console.log(isThrottled,"setTimeOut-if");
            }
        }, ms);
    }

    return wrapper;
}
```

调用 `throttle(func, ms)` 返回 `wrapper`。

1. 在第一次调用期间，`wrapper` 只运行 `func` 并设置冷却状态（`isThrottled = true`）。
2. 在这种状态下，所有调用都记忆在 `savedArgs/savedThis` 中。请注意，上下文和参数（arguments）同等重要，应该被记下来。我们同时需要他们以重现调用。
3. ……然后经过 `ms` 毫秒后，触发 `setTimeout`。冷却状态被移除（`isThrottled = false`），如果我们忽略了调用，则将使用最后记忆的参数和上下文执行 `wrapper`。

第 3 步运行的不是 `func`，而是 `wrapper`，因为我们不仅需要执行 `func`，还需要再次进入冷却状态并设置 timeout 以重置它。



最终显示1和3

创建了两个setTimeOut

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/82.gif" style="zoom: 100%"></img>

### 6.10函数绑定

[函数绑定](https://zh.javascript.info/bind)

#### 0.丢失this

一旦方法被传递到与对象分开的某个地方 —— `this` 就丢失。

下面是使用 `setTimeout` 时 `this` 是如何丢失的：

```javascript
let user = {
  firstName: "John",
  sayHi() {
    alert(`Hello, ${this.firstName}!`);
  }
};

setTimeout(user.sayHi, 1000); // Hello, undefined!
```

正如我们所看到的，输出没有像 `this.firstName` 那样显示 “John”，而显示了 `undefined`！

这是因为 `setTimeout` 获取到了函数 `user.sayHi`，但它和对象分离开了。最后一行可以被重写为：

```javascript
let f = user.sayHi;
setTimeout(f, 1000); // 丢失了 user 上下文
```

浏览器中的 `setTimeout` 方法有些特殊：它为函数调用设定了 `this=window`（对于 Node.js，`this` 则会变为计时器（timer）对象，但在这儿并不重要）。所以对于 `this.firstName`，它其实试图获取的是 `window.firstName`，这个变量并不存在。在其他类似的情况下，通常 `this` 会变为 `undefined`。

#### 1.bind

返回一个原函数的拷贝，并拥有指定的 **`this`** 值和初始参数。

```javascript
let user = {
  firstName: "John"
};

function func() {
  alert(this.firstName);
}

let funcUser = func.bind(user);
funcUser(); // John
```

这里的 `func.bind(user)` 作为 `func` 的“绑定的（bound）变体”，绑定了 `this=user`。

所有的参数（arguments）都被“原样”传递给了初始的 `func`，例如：

```javascript
let user = {
  firstName: "John"
};

function func(phrase) {
  alert(phrase + ', ' + this.firstName);
}

// 将 this 绑定到 user
let funcUser = func.bind(user);

funcUser("Hello"); // Hello, John（参数 "Hello" 被传递，并且 this=user）
```

现在我们来尝试一个对象方法：

```javascript
let user = {
  firstName: "John",
  sayHi() {
    alert(`Hello, ${this.firstName}!`);
  }
};

let sayHi = user.sayHi.bind(user); // (*)

// 可以在没有对象（译注：与对象分离）的情况下运行它
sayHi(); // Hello, John!

setTimeout(sayHi, 1000); // Hello, John!

// 即使 user 的值在不到 1 秒内发生了改变
// sayHi 还是会使用预先绑定（pre-bound）的值，该值是对旧的 user 对象的引用
user = {
  sayHi() { alert("Another user in setTimeout!"); }
};
```

在 `(*)` 行，我们取了方法 `user.sayHi` 并将其绑定到 `user`。`sayHi` 是一个“绑定后（bound）”的方法，它可以被单独调用，也可以被传递给 `setTimeout` —— 都没关系，函数上下文都会是正确的。

这里我们能够看到参数（arguments）都被“原样”传递了，只是 `this` 被 `bind` 绑定了：

```javascript
let user = {
  firstName: "John",
  say(phrase) {
    alert(`${phrase}, ${this.firstName}!`);
  }
};

let say = user.say.bind(user);

say("Hello"); // Hello, John!（参数 "Hello" 被传递给了 say）
say("Bye"); // Bye, John!（参数 "Bye" 被传递给了 say）
```

#### 2.偏函数

我们不仅可以绑定 `this`，还可以绑定参数（arguments）。虽然很少这么做，但有时它可以派上用场。

`bind` 的完整语法如下：

```javascript
let bound = func.bind(context, [arg1], [arg2], ...);
```

它允许将上下文绑定为 `this`，以及绑定函数的起始参数。

例如，我们有一个乘法函数 `mul(a, b)`：

```javascript
function mul(a, b) {
  return a * b;
}
```

让我们使用 `bind` 在该函数基础上创建一个 `double` 函数：

```javascript
function mul(a, b) {
  return a * b;
}

let double = mul.bind(null, 2);//把a设置为2

alert( double(3) ); // = mul(2, 3) = 6
alert( double(4) ); // = mul(2, 4) = 8
alert( double(5) ); // = mul(2, 5) = 10
```

#### 3.没有上下文，只绑定参数

```js

function partial(func, ...argsBound) {
  return function(...args) { // (*)
    return func.call(this, ...argsBound, ...args);
  }
}

// 用法：
let user = {
  firstName: "John",
  say(time, phrase) {
    alert(`[${time}] ${this.firstName}: ${phrase}!`);
  }
};

// 添加一个带有绑定时间的 partial 方法
user.sayNow = partial(user.say, new Date().getHours() + ':' + new Date().getMinutes());

user.sayNow("Hello");
// 类似于这样的一些内容：
// [10:00] John: Hello!
```

`partial(func[, arg1, arg2...])` 调用的结果是一个包装器 `(*)`，它调用 `func` 并具有以下内容：

- 与它获得的函数具有相同的 `this`（对于 `user.sayNow` 调用来说，它是 `user`）
- 然后给它 `...argsBound` —— 来自于 `partial` 调用的参数（`"10:00"`）
- 然后给它 `...args` —— 给包装器的参数（`"Hello"`）

#### 习题：

<div style="color: red">一个函数不能被重复bind</div>

[二次 bind](https://zh.javascript.info/bind#er-ci-bind)

<div style="color: red">bind 的结果是另一个对象。它并没有原函数的函数属性</div>

[bind 后的函数属性](https://zh.javascript.info/bind#bind-hou-de-han-shu-shu-xing)

这个题会做，bind就过关了。（箭头函数也可以做到，我还没深入学）

[偏函数在登录中的应用](https://zh.javascript.info/bind#pian-han-shu-zai-deng-lu-zhong-de-ying-yong)

### 6.11深入理解箭头函数

[深入理解箭头函数](https://zh.javascript.info/arrow-functions)

推荐看这篇文章，加深下理解

[this、apply、call、bind - 掘金 (juejin.cn)](https://juejin.cn/post/6844903496253177863#heading-11)

众所周知，ES6 的箭头函数是可以避免 ES5 中使用 this 的坑的。**箭头函数的 this 始终指向函数定义时的 this，而非执行时。**，箭头函数需要记着这句话：“箭头函数中没有 this 绑定，必须通过查找作用域链来决定其值，如果箭头函数被非箭头函数包含，则 this 绑定的是最近一层非箭头函数的 this，否则，this 为 undefined”。



**匿名函数的 this 永远指向 window**



## 7.对象属性配置

### 7.1属性标志和属性描述符

[属性标志和属性描述符](https://zh.javascript.info/property-descriptors)

#### 1.属性标志

这三个默认如果简单创建对象都是true,而使用Object.defineProperty创建默认都是false

![image-20220327171828724](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327171828724.png)

##### 获取：

```js
let user = {
  name: "John"
};

let descriptor = Object.getOwnPropertyDescriptor(user, 'name');

alert( JSON.stringify(descriptor, null, 2 ) );
/* 属性描述符：
{
  "value": "John",
  "writable": true,
  "enumerable": true,
  "configurable": true
}
*/
```

##### 修改：

![image-20220327172055769](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327172055769.png)

例子：

创建了一个属性 `name`，该属性的所有标志都为 `false`：

```js
 Object.defineProperty(user, "name", {
      value: "John"
    });

    let descriptor = Object.getOwnPropertyDescriptor(user, 'name');

    alert(JSON.stringify(descriptor, null, 2));
/*
    {
      "value": "John",
      "writable": false,
      "enumerable": false,
      "configurable": false
    }
     */
```

#### 2.只读，不可枚举，不可配置

writable，enumerable，configurable

内容较多，我觉得比较重要。建议看原文

<div style="color: red">只读writable管理对象的值，不可配置configurable管理对象的键</div>

#### 3.其他

Object.definePropertie该方法相较于Object.defineProperty可以一次性设置多个属性

```js
Object.defineProperties(user, {
  name: { value: "John", writable: false },
  surname: { value: "Smith", writable: false },
  // ...
});
```

相较于Object.getOwnPropertyDescriptor，要一次获取所有属性描述符，我们可以使用 [Object.getOwnPropertyDescriptors(obj)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptors) 方法

### 7.2属性的 getter 和 setter

[属性的 getter 和 setter](https://zh.javascript.info/property-accessors)

这个部分也非常像java里面的get和set

#### 1.getter和setter

```js
let obj = {
  get propName() {
    // 当读取 obj.propName 时，getter 起作用
  },

  set propName(value) {
    // 当执行 obj.propName = value 操作时，setter 起作用
  }
};
```

例子：

```js
let user = {
  get name() {
    return this._name;
  },

  set name(value) {
    if (value.length < 4) {
      alert("Name is too short, need at least 4 characters");
      return;
    }
    this._name = value;
  }
};

user.name = "Pete";
alert(user.name); // Pete

user.name = ""; // alert("Name is too short, need at least 4 characters");
```

从技术上讲，外部代码可以使用 `user._name` 直接访问 name。但是，这儿有一个众所周知的约定，即以下划线 `"_"` 开头的属性是内部属性，不应该从对象外部进行访问。

#### 2.兼容性：

文中提了一个例子：感觉很巧妙啊

```js
function User(name, birthday) {
  this.name = name;
  this.birthday = birthday;

  // 年龄是根据当前日期和生日计算得出的
  Object.defineProperty(this, "age", {
    get() {
      let todayYear = new Date().getFullYear();
      return todayYear - this.birthday.getFullYear();
    }
  });
}

let john = new User("John", new Date(1992, 6, 1));

alert( john.birthday ); // birthday 是可访问的
alert( john.age );      // ……age 也是可访问的
```



## 8.原型，继承：

### 8.1原型继承

[原型继承](https://zh.javascript.info/prototype-inheritance)

<div style="color: red">__proto__是我们访问设置[[Prototype]]的一种方式。</div>

`__proto__` **是** `[[Prototype]]` 的因历史原因而留下来的 <span style="color: red">getter/setter</span>

用这些方法替代__proto__：

- [Object.getPrototypeOf(obj)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf) —— 返回对象 `obj` 的 `[[Prototype]]`。
- [Object.setPrototypeOf(obj, proto)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf) —— 将对象 `obj` 的 `[[Prototype]]` 设置为 `proto`。

#### 1.初识

```js
	let animal = {
      eats: true
    };
    let rabbit = {
      jumps: true
    };

    rabbit.__proto__ = animal; // 设置 rabbit.[[Prototype]] = animal
    console.log(rabbit.eats);//true
```

1. 引用不能形成闭环。如果我们试图在一个闭环中分配 `__proto__`，JavaScript 会抛出错误。
2. `__proto__` 的值可以是对象，也可以是 `null`。而其他的类型都会被忽略。
3. 只能有一个 `[[Prototype]]`。一个对象不能从其他两个对象获得继承。

#### 2.写入不使用原型

就是说如果本身有这个方法，就不会顺着原型链往上找了.

```js
let animal = {
  eats: true,
  walk() {
    /* rabbit 不会使用此方法 */
  }
};

let rabbit = {
  __proto__: animal
};

rabbit.walk = function() {
  alert("Rabbit! Bounce-bounce!");
};

rabbit.walk(); // Rabbit! Bounce-bounce!
```

访问器（accessor）属性是一个例外，因为分配（assignment）操作是由 setter 函数处理的。因此，写入此类属性实际上与调用函数相同。

也就是这个原因，所以下面这段代码中的 `admin.fullName` 能够正常运行：

```javascript
let user = {
  name: "John",
  surname: "Smith",

  set fullName(value) {
    [this.name, this.surname] = value.split(" ");
  },

  get fullName() {
    return `${this.name} ${this.surname}`;
  }
};

let admin = {
  __proto__: user,
  isAdmin: true
};

alert(admin.fullName); // John Smith (*)

// setter triggers!
admin.fullName = "Alice Cooper"; // (**)

alert(admin.fullName); // Alice Cooper，admin 的内容被修改了
alert(user.fullName);  // John Smith，user 的内容被保护了
```

在 `(*)` 行中，属性 `admin.fullName` 在原型 `user` 中有一个 getter，因此它会被调用。在 `(**)` 行中，属性在原型中有一个 setter，因此它会被调用。

#### 3.this

<div style="color: red">无论在哪里找到方法：在一个对象还是在原型中。在一个方法调用中，`this` 始终是点符号 `.` 前面的对象。</div>

```js
// animal 有一些方法
let animal = {
  walk() {
    if (!this.isSleeping) {
      alert(`I walk`);
    }
  },
  sleep() {
    this.isSleeping = true;
  }
};

let rabbit = {
  name: "White Rabbit",
  __proto__: animal
};

// 修改 rabbit.isSleeping
rabbit.sleep();

alert(rabbit.isSleeping); // true
alert(animal.isSleeping); // undefined（原型中没有此属性）
```

#### 4.for...in循环

<div style="color: red">`for..in` 循环也会迭代继承的属性。</div>

```js
let animal = {
  eats: true
};

let rabbit = {
  jumps: true,
  __proto__: animal
};

// Object.keys 只返回自己的 key
alert(Object.keys(rabbit)); // jumps

// for..in 会遍历自己以及继承的键
for(let prop in rabbit) alert(prop); // jumps，然后是 eats
```

如果这不是我们想要的，并且我们想排除继承的属性，那么这儿有一个内建方法 [obj.hasOwnProperty(key)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)：如果 `obj` 具有自己的（非继承的）名为 `key` 的属性，则返回 `true`。

```js
let animal = {
  eats: true
};

let rabbit = {
  jumps: true,
  __proto__: animal
};

for(let prop in rabbit) {
  let isOwn = rabbit.hasOwnProperty(prop);

  if (isOwn) {
    alert(`Our: ${prop}`); // Our: jumps
  } else {
    alert(`Inherited: ${prop}`); // Inherited: eats
  }
}
```

而几乎所有其他键/值获取方法，例如 `Object.keys` 和 `Object.values` 等，都会忽略继承的属性。它们只会对对象自身进行操作。**不考虑** 继承自原型的属性。

#### 习题：

[写在哪里？](https://zh.javascript.info/prototype-inheritance#xie-zai-na-li)

```js
let animal = {
    eat() {
        this.full = true;
    }
};

let rabbit = {
    __proto__: animal
};
console.log(rabbit)
rabbit.eat();
console.log(rabbit)
```

`this` 是点符号前面的这个对象，因此 `rabbit.eat()` 修改了 `rabbit`。

属性查找和执行是两回事儿。

首先在原型中找到 `rabbit.eat` 方法，然后在 `this=rabbit` 的情况下执行。

![image-20220427145422870](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220427145422870.png)



很简单喔

[为什么两只仓鼠都饱了？](https://zh.javascript.info/prototype-inheritance#wei-shi-mo-liang-zhi-cang-shu-du-bao-le)

```js
let hamster = {
  stomach: [],

  eat(food) {
    this.stomach.push(food);
  }
};

let speedy = {
  __proto__: hamster
};

let lazy = {
  __proto__: hamster
};

// 这只仓鼠找到了食物
speedy.eat("apple");
alert( speedy.stomach ); // apple

// 这只仓鼠也找到了食物，为什么？请修复它。
alert( lazy.stomach ); // apple
```

### 8.2F.prototype

[F.prototype](https://zh.javascript.info/function-prototype)

![](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220427152255333.png)

#### 1.F.prototype

就是说我们可以给构造函数设置一个属性叫prototype，如果我们把一个对象（称为A吧）赋值给这个属性prototype，那么通过这个构造函数创建出来的对象，它们的[[Prototype]]就是A。所以我们现在又获得了一种访问[[Prototype]]的方式。

<div style="color: red">"prototype"` 属性仅在设置了一个构造函数（constructor function），并通过 `new` 调用时，才具有这种特殊的影响。</div>

```js
let animal = {
  eats: true
};

function Rabbit(name) {
  this.name = name;
}

Rabbit.prototype = animal;

let rabbit = new Rabbit("White Rabbit"); //  rabbit.__proto__ == animal

alert( rabbit.eats ); // true
```

![image-20220331204716464](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220331204716464.png)

#### 2.默认的F.prototype,构造器属性

就是说我们如果不给构造函数设置prototype属性，它也是存在的，也是有默认值的。

这个默认值是一个对象，一个只有属性 `constructor` 的对象，属性 `constructor`的值就是函数自身

```js
function Rabbit() {}
// by default:
// Rabbit.prototype = { constructor: Rabbit }

alert( Rabbit.prototype.constructor == Rabbit ); // true
```

我们什么都不做，`constructor` 属性可以通过 `[[Prototype]]` 给所有 rabbits 使用：

```js
function Rabbit() {}
//Rabbit.prototype = { constructor: Rabbit }

let rabbit = new Rabbit(); 
let rabbit_1 = new Rabbit(); 

console.log(rabbit.constructor == Rabbit);//true
console.log(rabbit_1.constructor == Rabbit);//true
```

所以这样写也是可以的

```js
function Rabbit(name) {
  this.name = name;
  alert(name);
}

let rabbit = new Rabbit("White Rabbit");

let rabbit2 = new rabbit.constructor("Black Rabbit");
```

但是我们如果把构造函数的prototype替换掉，就不会有`constructor`了。但这些小rabbit获得了[[Prototype]]

```js
function Rabbit() {}
Rabbit.prototype = {
  jumps: true
};

let rabbit = new Rabbit();
alert(rabbit.constructor === Rabbit); // false
```

因此，为了确保正确的 `"constructor"`，我们可以选择添加/删除属性到默认 `"prototype"`，而不是将其整个覆盖：

```javascript
function Rabbit() {}

// 不要将 Rabbit.prototype 整个覆盖
// 可以向其中添加内容
Rabbit.prototype.jumps = true
// 默认的 Rabbit.prototype.constructor 被保留了下来
```

或者，也可以手动重新创建 `constructor` 属性：

```javascript
Rabbit.prototype = {
  jumps: true,
  constructor: Rabbit
};

// 这样的 constructor 也是正确的，因为我们手动添加了它
```

 <div style="color: red">在常规对象上，`prototype` 没什么特别的</div>

```javascript
let user = {
  name: "John",
  prototype: "Bla-bla" // 这里只是普通的属性
};
```

默认情况下，所有函数都有 `F.prototype = {constructor：F}`，所以我们可以通过访问它的 `"constructor"` 属性来获取一个对象的构造器。



#### 习题：

两个习题都有点难度，但看了解析，还是觉得挺简单的，hahaha。

[任务](https://zh.javascript.info/function-prototype#tasks)

### 8.3原生的原型

[原生的原型](https://zh.javascript.info/native-prototypes)

推荐阅读原文，我觉得都挺重要的没废话。

#### 习题：

[将装饰器 "defer()" 添加到函数](https://zh.javascript.info/native-prototypes#jiang-zhuang-shi-qi-defer-tian-jia-dao-han-shu)

我的做法：(没用箭头函数，笑)

```js
Function.prototype.defer=function(ms){
  let _this=this
  return function(...args){
    setTimeout(function(){
      _this.apply(_this,args)
    },ms)
  }
}


function f(a, b) {
  alert( a + b );
}

f.defer(1000)(1, 2); // 1 秒后显示 3
```

### 8.4原型方法，没有 __proto__ 的对象

[原型方法，没有 __proto__ 的对象](https://zh.javascript.info/prototype-methods)

#### 1替换____proto____

现代的方法有：

- [Object.create(proto, [descriptors\])](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Object/create) —— 利用给定的 `proto` 作为 `[[Prototype]]` 和可选的属性描述来创建一个空对象。

- [Object.getPrototypeOf(obj)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf) —— 返回对象 `obj` 的 `[[Prototype]]`。
- [Object.setPrototypeOf(obj, proto)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf) —— 将对象 `obj` 的 `[[Prototype]]` 设置为 `proto`。

```js
let animal = {
  eats: true
};

// 创建一个以 animal 为原型的新对象
let rabbit = Object.create(animal);

alert(rabbit.eats); // true

alert(Object.getPrototypeOf(rabbit) === animal); // true

Object.setPrototypeOf(rabbit, {}); // 将 rabbit 的原型修改为 {}
```

`Object.create` 有一个可选的第二参数：属性描述器。我们可以在此处为新对象提供额外的属性，就像这样：

```javascript
let animal = {
  eats: true
};

let rabbit = Object.create(animal, {
  jumps: {
    value: true
  }
});

console.log(animal);
console.log(rabbit);
```

![image-20220401015606730](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401015606730.png)

#### 2."Very plain" objects

["Very plain" objects](https://zh.javascript.info/prototype-methods#very-plain)

关于__proto__的一个bug，以及用“非常普通对象”如何解决，推荐看原文

#### 习题：

[任务](https://zh.javascript.info/prototype-methods#tasks)

这两个题会了，已经通了。

1.

```js
// "use strict"

let dictionary = Object.create(null);

Object.defineProperty(dictionary, "toString", {
  value: function() {
  return Object.keys(this).join();
},
  enumerable: false
})

// 添加一些数据
dictionary.apple = "Apple";
dictionary.__proto__ = "test"; // 这里 __proto__ 是一个常规的属性键

// 在循环中只有 apple 和 __proto__
for(let key in dictionary) {
  alert(key); // "apple", then "__proto__"
}

// 你的 toString 方法在发挥作用
alert(dictionary); // "apple,__proto__"
```



## 9.类

### 9.1.Class基本语法

[Class 基本语法](https://zh.javascript.info/class)

#### 1.基础

基本语法是：

```javascript
class MyClass {
  // class 方法
  constructor() { ... }
  method1() { ... }
  method2() { ... }
  method3() { ... }
  ...
}
```

然后使用 `new MyClass()` 来创建具有上述列出的所有方法的新对象。

`new` 会自动调用 `constructor()` 方法，因此我们可以在 `constructor()` 中初始化对象。

例如：

```javascript
class User {

  constructor(name) {
    this.name = name;
  }

  sayHi() {
    alert(this.name);
  }

}

// 用法：
let user = new User("John");
user.sayHi();
```

当 `new User("John")` 被调用：

1. 一个新对象被创建。
2. `constructor` 使用给定的参数运行，并将其赋值给 `this.name`。

#### 2.什么是class？

在 JavaScript 中，类是一种函数。

看看下面这段代码：

```javascript
class User {
  constructor(name) { this.name = name; }
  sayHi() { alert(this.name); }
}

// 佐证：User 是一个函数
alert(typeof User); // function
```

`class User {...}` 构造实际上做了如下的事儿：

1. 创建一个名为 `User` 的函数，该函数成为类声明的结果。该函数的代码来自于 `constructor` 方法（如果我们不编写这种方法，那么它就被假定为空）。
2. 存储类中的方法，例如 `User.prototype` 中的 `sayHi`。

![image-20220401123604996](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401123604996.png)



```javascript
class User {
  constructor(name) { this.name = name; }
  sayHi() { alert(this.name); }
}

// class 是一个函数
alert(typeof User); // function

// ...或者，更确切地说，是 constructor 方法
alert(User === User.prototype.constructor); // true

// 方法在 User.prototype 中，例如：
alert(User.prototype.sayHi); // sayHi 方法的代码

// 在原型中实际上有两个方法
alert(Object.getOwnPropertyNames(User.prototype)); // constructor, sayHi
```



#### 4.类表达式

函数有NFE，和函数一样,类也有命名类表达式

如果类表达式有名字，那么该名字仅在类内部可见：

```javascript
// “命名类表达式（Named Class Expression）”
// (规范中没有这样的术语，但是它和命名函数表达式类似)
let User = class MyClass {
  sayHi() {
    alert(MyClass); // MyClass 这个名字仅在类内部可见
  }
};

new User().sayHi(); // 正常运行，显示 MyClass 中定义的内容

alert(MyClass); // error，MyClass 在外部不可见
```

我们甚至可以动态地“按需”创建类，就像这样：

```javascript
function makeClass(phrase) {
  // 声明一个类并返回它
  return class {
    sayHi() {
      alert(phrase);
    }
  };
}

// 创建一个新的类
let User = makeClass("Hello");

new User().sayHi(); // Hello
```

#### 6.计算属性

这里有一个使用中括号 `[...]` 的计算方法名称示例：

```javascript
class User {

  ['say' + 'Hi']() {
    alert("Hello");
  }

}

new User().sayHi();
```

这种特性很容易记住，因为它们和对象字面量类似。

#### 7.类字段

“类字段”是一种允许添加任何属性的语法。

例如，让我们在 `class User` 中添加一个 `name` 属性：

```javascript
class User {
  name = "John";

  sayHi() {
    alert(`Hello, ${this.name}!`);
  }
}

new User().sayHi(); // Hello, John!
```

所以，我们就只需在表达式中写 " = "，就这样。

类字段重要的不同之处在于，它们会在每个独立对象中被设好，而不是设在 `User.prototype`：

```javascript
class User {
  name = "John";
}

let user = new User();
alert(user.name); // John
alert(User.prototype.name); // undefined
```

##### 使用类字段防止丢失this：

例如，此代码将显示 `undefined`：

```javascript
class Button {
  constructor(value) {
    this.value = value;
  }

  click() {
    alert(this.value);
  }
}

let button = new Button("hello");

setTimeout(button.click, 1000); // undefined
```

这个问题被称为“丢失 `this`”。

我们在 [函数绑定](https://zh.javascript.info/bind) 一章中讲过，有两种可以修复它的方式：

1. 传递一个包装函数，例如 `setTimeout(() => button.click(), 1000)`。
2. 将方法绑定到对象，例如在 constructor 中。

类字段提供了另一种非常优雅的语法：

```javascript
class Button {
  constructor(value) {
    this.value = value;
  }
  click = () => {
    alert(this.value);
  }
}

let button = new Button("hello");

setTimeout(button.click, 1000); // hello
```

类字段 `click = () => {...}` 是基于每一个对象被创建的，在这里对于每一个 `Button` 对象都有一个独立的方法，在内部都有一个指向此对象的 `this`。我们可以把 `button.click` 传递到任何地方，而且 `this` 的值总是正确的。

在浏览器环境中，它对于进行事件监听尤为有用。

### 9.2类继承

[类继承](https://zh.javascript.info/class-inheritance)

#### 1.extends关键字

假设我们有 class `Animal`：

```javascript
class Animal {
  constructor(name) {
    this.speed = 0;
    this.name = name;
  }
  run(speed) {
    this.speed = speed;
    alert(`${this.name} runs with speed ${this.speed}.`);
  }
  stop() {
    this.speed = 0;
    alert(`${this.name} stands still.`);
  }
}

let animal = new Animal("My animal");
```

![image-20220401130300723](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401130300723.png)

```js
class Rabbit extends Animal {
  hide() {
    alert(`${this.name} hides!`);
  }
}

let rabbit = new Rabbit("White Rabbit");

rabbit.run(5); // White Rabbit runs with speed 5.
rabbit.hide(); // White Rabbit hides!
```

在内部，关键字 `extends` 使用了很好的旧的原型机制进行工作。它将 `Rabbit.prototype.[[Prototype]]` 设置为 `Animal.prototype`。所以，如果在 `Rabbit.prototype` 中找不到一个方法，JavaScript 就会从 `Animal.prototype` 中获取该方法。

![image-20220401130352101](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401130352101.png)

例如，要查找 `rabbit.run` 方法，JavaScript 引擎会进行如下检查（如图所示从下到上）：

1. 查找对象 `rabbit`（没有 `run`）。
2. 查找它的原型，即 `Rabbit.prototype`（有 `hide`，但没有 `run`）。
3. 查找它的原型，即（由于 `extends`）`Animal.prototype`，在这儿找到了 `run` 方法。

#### 2.重写方法

我们在 `Rabbit` 中指定了我们自己的方法，例如 `stop()`，那么将会使用它：

```javascript
class Rabbit extends Animal {
  stop() {
    // ……现在这个将会被用作 rabbit.stop()
    // 而不是来自于 class Animal 的 stop()
  }
}
```

不希望完全替换掉父类的方法：

Class 为此提供了 `"super"` 关键字。

- 执行 `super.method(...)` 来调用一个父类方法。
- 执行 `super(...)` 来调用一个父类 constructor（只能在我们的 constructor 中）。

例如，让我们的 rabbit 在停下来的时候自动 hide：

```javascript
class Animal {

  constructor(name) {
    this.speed = 0;
    this.name = name;
  }

  run(speed) {
    this.speed = speed;
    alert(`${this.name} runs with speed ${this.speed}.`);
  }

  stop() {
    this.speed = 0;
    alert(`${this.name} stands still.`);
  }

}

class Rabbit extends Animal {
  hide() {
    alert(`${this.name} hides!`);
  }

  stop() {
    super.stop(); // 调用父类的 stop
    this.hide(); // 然后 hide
  }
}

let rabbit = new Rabbit("White Rabbit");

rabbit.run(5); // White Rabbit runs with speed 5.
rabbit.stop(); // White Rabbit stands still. White Rabbit hides!
```

#### 3.重写构造器

```js
class Animal {
  constructor(name) {
    this.speed = 0;
    this.name = name;
  }
  // ...
}

class Rabbit extends Animal {

  constructor(name, earLength) {
    this.speed = 0;
    this.name = name;
    this.earLength = earLength;
  }

  // ...
}

// 不工作！
let rabbit = new Rabbit("White Rabbit", 10); // Error: this is not defined.
```

<div style="color: red">继承类的 constructor 必须调用 `super(...)`，并且 (!) 一定要在使用 `this` 之前调用。</div>

```js
class Animal {

  constructor(name) {
    this.speed = 0;
    this.name = name;
  }

  // ...
}

class Rabbit extends Animal {

  constructor(name, earLength) {
    super(name);
    this.earLength = earLength;
  }

  // ...
}

// 现在可以了
let rabbit = new Rabbit("White Rabbit", 10);
alert(rabbit.name); // White Rabbit
alert(rabbit.earLength); // 10
```

#### 4.重写类字段

（我就没见过这种写法……）

```js
class Animal {
  name = 'animal';

  constructor() {
    alert(this.name); // (*)
  }
}

class Rabbit extends Animal {
  name = 'rabbit';
}

new Animal(); // animal
new Rabbit(); // animal
```

这里，`Rabbit` 继承自 `Animal`，并且用它自己的值重写了 `name` 字段。

因为 `Rabbit` 中没有自己的构造器，所以 `Animal` 的构造器被调用了。

有趣的是在这两种情况下：`new Animal()` 和 `new Rabbit()`，在 `(*)` 行的 `alert` 都打印了 `animal`。

<div style="color: red">换句话说，父类构造器总是会使用它自己字段的值，而不是被重写的那一个。</div>

下面是使用方法的情况，和使用类字段截然不同

```js
class Animal {
  showName() {  // 而不是 this.name = 'animal'
    alert('animal');
  }

  constructor() {
    this.showName(); // 而不是 alert(this.name);
  }
}

class Rabbit extends Animal {
  showName() {
    alert('rabbit');
  }
}

new Animal(); // animal
new Rabbit(); // rabbit
```

#### 5.深入：内部探究和 [[HomeObject\]]

[深入：内部探究和 [[HomeObject\]]](https://zh.javascript.info/class-inheritance#shen-ru-nei-bu-tan-jiu-he-homeobject)

挖的太深了，现阶段没必要深究的。

### 9.3静态属性和静态方法

#### 1.静态方法

我们可以把一个方法赋值给类的函数本身，而不是赋给它的 `"prototype"`。这样的方法被称为 **静态的（static）**。

在一个类中，它们以 `static` 关键字开头，如下所示：

```javascript
class User {
  static staticMethod() {
    alert(this === User);
  }
}

User.staticMethod(); // true
```

这实际上跟直接将其作为属性赋值的作用相同：

```javascript
class User { }

User.staticMethod = function() {
  alert(this === User);
};

User.staticMethod(); // true
```

使用场景

假如我们有对象 `Article`，并且需要一个方法来比较它们。一个自然的解决方案就是添加 `Article.compare` 方法，像下面这样：

```javascript
class Article {
  constructor(title, date) {
    this.title = title;
    this.date = date;
  }

  static compare(articleA, articleB) {
    return articleA.date - articleB.date;
  }
}

// 用法
let articles = [
  new Article("HTML", new Date(2019, 1, 1)),
  new Article("CSS", new Date(2019, 0, 1)),
  new Article("JavaScript", new Date(2019, 11, 1))
];

articles.sort(Article.compare);

alert( articles[0].title ); // CSS
```

#### 2.静态属性

静态的属性也是可能的，它们看起来就像常规的类属性，但前面加有 `static`：

```javascript
class Article {
  static publisher = "Levi Ding";
}

alert( Article.publisher ); // Levi Ding
```

这等同于直接给 `Article` 赋值：

```javascript
Article.publisher = "Levi Ding";
```

#### 3.继承静态属性和方法

```js
class Animal {
  static planet = "Earth";

  constructor(name, speed) {
    this.speed = speed;
    this.name = name;
  }

  run(speed = 0) {
    this.speed += speed;
    alert(`${this.name} runs with speed ${this.speed}.`);
  }

  static compare(animalA, animalB) {
    return animalA.speed - animalB.speed;
  }

}

// 继承于 Animal
class Rabbit extends Animal {
  hide() {
    alert(`${this.name} hides!`);
  }
}

let rabbits = [
  new Rabbit("White Rabbit", 10),
  new Rabbit("Black Rabbit", 5)
];

rabbits.sort(Rabbit.compare);

rabbits[0].run(); // Black Rabbit runs with speed 5.

alert(Rabbit.planet); // Earth
```

注意哟，extends创建了两个[[Prototype]]引用

![image-20220401140433343](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401140433343.png)

#### 习题：

[类扩展自对象？](https://zh.javascript.info/static-properties-methods#lei-kuo-zhan-zi-dui-xiang)

这个习题，解析拓展的内容很绕

### 9.5私有的和受保护的属性和方法

[私有的和受保护的属性和方法](https://zh.javascript.info/private-protected-properties-methods)

和java的大差不差，推荐看原文

### 9.6扩展内建类

[扩展内建类](https://zh.javascript.info/extend-natives)

我感觉没人会去这么做吧……

### 9.7类检查："instanceof"

[类检查："instanceof"](https://zh.javascript.info/instanceof)

<div style="color: red">根据 `instanceof` 的逻辑，真正决定类型的是 `prototype`，而不是构造函数。</div>

#### 1.instaceof操作符

语法：

```javascript
obj instanceof Class
```

如果 `obj` 隶属于 `Class` 类（或 `Class` 类的衍生类），则返回 `true`。

例如：

```javascript
class Rabbit {}
let rabbit = new Rabbit();

// rabbit 是 Rabbit class 的对象吗？
alert( rabbit instanceof Rabbit ); // true
```

它还可以与构造函数一起使用：

```javascript
// 这里是构造函数，而不是 class
function Rabbit() {}

alert( new Rabbit() instanceof Rabbit ); // true
```

……与诸如 `Array` 之类的内建 class 一起使用：

```javascript
let arr = [1, 2, 3];
alert( arr instanceof Array ); // true
alert( arr instanceof Object ); // true
```

##### 执行逻辑：

instanceof会考虑原型链，也可以在Symbol.hasInstance中设置自定义逻辑。检查逻辑是先检查有无Symbol.hasInstance，再顺着原型链找。

`obj instanceof Class` 算法的执行过程大致如下：

1. 如果这儿有静态方法 `Symbol.hasInstance`，那就直接调用这个方法：

   例如：

   ```javascript
   // 设置 instanceOf 检查
   // 并假设具有 canEat 属性的都是 animal
   class Animal {
     static [Symbol.hasInstance](obj) {
       if (obj.canEat) return true;
     }
   }
   
   let obj = { canEat: true };
   
   alert(obj instanceof Animal); // true：Animal[Symbol.hasInstance](obj) 被调用
   ```

2. 大多数 class 没有 `Symbol.hasInstance`。在这种情况下，标准的逻辑是：使用 `obj instanceOf Class` 检查 `Class.prototype` 是否等于 `obj` 的原型链中的原型之一。

   换句话说就是，一个接一个地比较：

   ```javascript
   obj.__proto__ === Class.prototype?
   obj.__proto__.__proto__ === Class.prototype?
   obj.__proto__.__proto__.__proto__ === Class.prototype?
   ...
   // 如果任意一个的答案为 true，则返回 true
   // 否则，如果我们已经检查到了原型链的尾端，则返回 false
   ```

![image-20220401144535045](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220401144535045.png)

##### 一个额外方法：

这里还要提到一个方法 [objA.isPrototypeOf(objB)](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/object/isPrototypeOf)，如果 `objA` 处在 `objB` 的原型链中，则返回 `true`。所以，可以将 `obj instanceof Class` 检查改为 `Class.prototype.isPrototypeOf(obj)`。

这很有趣，但是 `Class` 的 constructor 自身是不参与检查的！检查过程只和原型链以及 `Class.prototype` 有关。

创建对象后，如果更改 `prototype` 属性，可能会导致有趣的结果。

就像这样：

```javascript
function Rabbit() {}
let rabbit = new Rabbit();

// 修改了 prototype
Rabbit.prototype = {};

// ...再也不是 rabbit 了！
alert( rabbit instanceof Rabbit ); // false
```

#### 2.另一种判断的方法

[福利：使用 Object.prototype.toString 方法来揭示类型](https://zh.javascript.info/instanceof#fu-li-shi-yong-objectprototypetostring-fang-fa-lai-jie-shi-lei-xing)

我感觉这个就属于奇淫技巧了

### 9.8Mixin 模式

[Mixin 模式](https://zh.javascript.info/mixins)

让js获得多重继承的一种方式，推荐看原文

## 10.错误处理

### 1.try...catch

[错误处理，"try...catch"](https://zh.javascript.info/try-catch)

#### 1.基础

`try...catch` 结构由两部分组成：`try` 和 `catch`：

```javascript
try {

  // 代码...

} catch (err) {

  // 错误捕获

}
```

它按照以下步骤执行：

1. 首先，执行 `try {...}` 中的代码。
2. 如果这里没有错误，则忽略 `catch (err)`：执行到 `try` 的末尾并跳过 `catch` 继续执行。
3. 如果这里出现错误，则 `try` 执行停止，控制流转向 `catch (err)` 的开头。变量 `err`（我们可以使用任何名称）将包含一个 error 对象，该对象包含了所发生事件的详细信息。

​	

- 没有 error 的例子：显示 `alert` `(1)` 和 `(2)`：

  ```javascript
  try {
  
    alert('Start of try runs');  // (1) <--
  
    // ...这里没有 error
  
    alert('End of try runs');   // (2) <--
  
  } catch (err) {
  
    alert('Catch is ignored, because there are no errors'); // (3)
  
  }
  ```

- 包含 error 的例子：显示 `(1)` 和 `(3)` 行的 `alert` 中的内容：

  ```javascript
  try {
  
    alert('Start of try runs');  // (1) <--
  
    lalala; // Error，变量未定义！
  
    alert('End of try (never reached)');  // (2)
  
  } catch (err) {
  
    alert(`Error has occurred!`); // (3) <--
  
  }
  ```

​	两个注意点：

##### 仅对运行时error生效：

![image-20220402003652054](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402003652054.png)

##### 同步工作：

![image-20220402003802966](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402003802966.png)





#### 2.Error对象

发生错误时，JavaScript 生成一个包含有关其详细信息的对象。然后将该对象作为参数传递给 `catch`



对于所有内建的 error，error 对象具有两个主要属性：

- `name`

  Error 名称。例如，对于一个未定义的变量，名称是 `"ReferenceError"`。

- `message`

  关于 error 的详细文字描述。

还有其他非标准的属性在大多数环境中可用。其中被最广泛使用和支持的是：

- `stack`

  当前的调用栈：用于调试目的的一个字符串，其中包含有关导致 error 的嵌套调用序列的信息。

```js
try {
  lalala; 
} catch (err) {
  console.log(err.name); 
  console.log(err.message); 
  console.log(err.stack); 

  console.dir(err);
}

```

![image-20220402004432185](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402004432185.png)

#### 3.throw操作

`throw` 操作符会生成一个 error 对象。

```javascript
let json = '{ "age": 30 }'; // 不完整的数据

try {

  let user = JSON.parse(json); // <-- 没有 error

  if (!user.name) {
    throw new SyntaxError("Incomplete data: no name"); // (*)
  }

  alert( user.name );

} catch(err) {
  alert( "JSON Error: " + err.message ); // JSON Error: Incomplete data: no name
}
```

在 `(*)` 标记的这一行，`throw` 操作符生成了包含着我们所给定的 `message` 的 `SyntaxError`，与 JavaScript 自己生成的方式相同。`try` 的执行立即停止，控制流转向 `catch` 块。

现在，`catch` 成为了所有 error 处理的唯一场所：对于 `JSON.parse` 和其他情况都适用。

#### 4.catch：

![image-20220324143552954](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324143552954.png)

#### 5.再次抛出

“再次抛出（rethrowing）”技术可以被更详细地解释为：

1. Catch 捕获所有 error。
2. 在 `catch (err) {...}` 块中，我们对 error 对象 `err` 进行分析。
3. 如果我们不知道如何处理它，那我们就 `throw err`。

我们使用“再次抛出”，以达到在 `catch` 中只处理 `SyntaxError` 的目的：

```javascript
let json = '{ "age": 30 }'; // 不完整的数据
try {

  let user = JSON.parse(json);

  if (!user.name) {
    throw new SyntaxError("Incomplete data: no name");
  }

  blabla(); // 预料之外的 error

  alert( user.name );

} catch (err) {

  if (err instanceof SyntaxError) {
    alert( "JSON Error: " + err.message );
  } else {
    throw err; // 再次抛出 (*)
  }

}
```

如果 `(*)` 标记的这行 `catch` 块中的 error 从 `try...catch` 中“掉了出来”，那么它也可以被外部的 `try...catch` 结构（如果存在）捕获到，如果外部不存在这种结构，那么脚本就会被杀死。



`catch` 块实际上只处理它知道该如何处理的 error，并“跳过”所有其他的 error。

下面这个示例演示了这种类型的 error 是如何被另外一级 `try...catch` 捕获的：

```javascript
function readData() {
  let json = '{ "age": 30 }';

  try {
    // ...
    blabla(); // error!
  } catch (err) {
    // ...
    if (!(err instanceof SyntaxError)) {
      throw err; // 再次抛出（不知道如何处理它）
    }
  }
}

try {
  readData();
} catch (err) {
  alert( "External catch got: " + err ); // 捕获了它！
}
```

上面这个例子中的 `readData` 只知道如何处理 `SyntaxError`，而外部的 `try...catch` 知道如何处理任意的 error。

#### 6.finally

```js
try {
   ... 尝试执行的代码 ...
} catch (err) {
   ... 处理 error ...
} finally {
   ... 总是会执行的代码 ...
}
```

```javascript
try {
  alert( 'try' );
  if (confirm('Make an error?')) BAD_CODE();
} catch (err) {
  alert( 'catch' );
} finally {
  alert( 'finally' );
}
```

这段代码有两种执行方式：

1. 如果你对于 “Make an error?” 的回答是 “Yes”，那么执行 `try -> catch -> finally`。
2. 如果你的回答是 “No”，那么执行 `try -> finally`。



##### 注意点：

1.如果我们使用 `let` 在 `try` 块中声明变量，那么该变量将只在 `try` 块中可见。

2.finally和return

`finally` 子句适用于 `try...catch` 的 **任何** 出口。这包括显式的 `return`。

在下面这个例子中，在 `try` 中有一个 `return`。在这种情况下，`finally` 会在控制转向外部代码前被执行。

```javascript
function func() {

  try {
    return 1;

  } catch (err) {
    /* ... */
  } finally {
    alert( 'finally' );
  }
}

alert( func() ); // 先执行 finally 中的 alert，然后执行这个 alert
```

#### 7.全局catch

Node.JS 有 [`process.on("uncaughtException")`](https://nodejs.org/api/process.html#process_event_uncaughtexception)

在浏览器中，我们可以将一个函数赋值给特殊的 [window.onerror](https://developer.mozilla.org/zh/docs/Web/API/GlobalEventHandlers/onerror) 属性，该函数将在发生未捕获的 error 时执行。

语法如下：

```javascript
window.onerror = function(message, url, line, col, error) {
  // ...
};
```

- `message`

  Error 信息。

- `url`

  发生 error 的脚本的 URL。

- `line`，`col`

  发生 error 处的代码的行号和列号。

- `error`

  Error 对象。

例如：

```js
<script>
  window.onerror = function(message, url, line, col, error) {
    alert(`${message}\n At ${line}:${col} of ${url}`);
  };

  function readData() {
    badFunc(); // 啊，出问题了！
  }

  readData();
</script>
```

全局错误处理程序 `window.onerror` 的作用通常不是恢复脚本的执行 — 如果发生编程错误，那这几乎是不可能的，它的作用是将错误信息发送给开发者。

### 2.自定义 Error，扩展 Error

[自定义 Error，扩展 Error](https://zh.javascript.info/custom-errors)

#### 1.扩展Error



```javascript
class ValidationError extends Error {
  constructor(message) {
    super(message); // (1)
    this.name = "ValidationError"; // (2)
  }
}

function test() {
  throw new ValidationError("Whoops!");
}

try {
  test();
} catch(err) {
  alert(err.message); // Whoops!
  alert(err.name); // ValidationError
  alert(err.stack); // 一个嵌套调用的列表，每个调用都有对应的行号
}
```

请注意：在 `(1)` 行中我们调用了父类的 constructor。JavaScript 要求我们在子类的 constructor 中调用 `super`，所以这是必须的。父类的 constructor 设置了 `message` 属性。

父类的 constructor 还将 `name` 属性的值设置为了 `"Error"`，所以在 `(2)` 行中，我们将其重置为了右边的值。

让我们尝试在 `readUser(json)` 中使用它吧：

```javascript
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

// 用法
function readUser(json) {
  let user = JSON.parse(json);

  if (!user.age) {
    throw new ValidationError("No field: age");
  }
  if (!user.name) {
    throw new ValidationError("No field: name");
  }

  return user;
}

// try..catch 的工作示例

try {
  let user = readUser('{ "age": 25 }');
} catch (err) {
  if (err instanceof ValidationError) {
    alert("Invalid data: " + err.message); // Invalid data: No field: name
  } else if (err instanceof SyntaxError) { // (*)
    alert("JSON Syntax Error: " + err.message);
  } else {
    throw err; // 未知的 error，再次抛出 (**)
  }
}
```

上面代码中的 `try..catch` 块既处理我们的 `ValidationError` 又处理来自 `JSON.parse` 的内建 `SyntaxError`。

#### 2.深入继承

就是说为了完善我们的自定义error类，可以设想其他错误场景，细化我们的error类

`ValidationError` 类是非常通用的。很多东西都可能出错。对象的属性可能缺失或者属性可能有格式错误（例如 `age` 属性的值为一个字符串而不是数字）。让我们针对缺少属性的错误来制作一个更具体的 `PropertyRequiredError` 类。它将携带有关缺少的属性的相关信息。

```javascript
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = "ValidationError";
  }
}

class PropertyRequiredError extends ValidationError {
  constructor(property) {
    super("No property: " + property);
    this.name = "PropertyRequiredError";
    this.property = property;
  }
}

// 用法
function readUser(json) {
  let user = JSON.parse(json);

  if (!user.age) {
    throw new PropertyRequiredError("age");
  }
  if (!user.name) {
    throw new PropertyRequiredError("name");
  }

  return user;
}

// try..catch 的工作示例

try {
  let user = readUser('{ "age": 25 }');
} catch (err) {
  if (err instanceof ValidationError) {
    alert("Invalid data: " + err.message); // Invalid data: No property: name
    alert(err.name); // PropertyRequiredError
    alert(err.property); // name
  } else if (err instanceof SyntaxError) {
    alert("JSON Syntax Error: " + err.message);
  } else {
    throw err; // 为止 error，将其再次抛出
  }
}
```

这个新的类 `PropertyRequiredError` 使用起来很简单：我们只需要传递属性名：`new PropertyRequiredError(property)`。人类可读的 `message` 是由 constructor 生成的。

#### 3.包装异常

[包装异常](https://zh.javascript.info/custom-errors#bao-zhuang-yi-chang)

就是说我们判断异常类型时，要写很长的if else链，使用包装异常可以解决这个问题。准确说它处理低级error，创建高级error。

推荐看原文。



## 11.Promise,async/await

[Promise，async/await](https://zh.javascript.info/async)

### 11.2Promise:

[Promise](https://zh.javascript.info/promise-basics)

推荐看原文内容很多

#### 1.Promise构造器

![image-20220324143206747](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324143206747.png)

![image-20220324143350895](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324143350895.png)

我们也把绿色框或者红色框里的promise称为settled的promise（已经结束的promise），和pending的promise（等待状态的promise）相对应.

##### 注意点：

1.**以 `Error` 对象 reject**

如果什么东西出了问题， executor 应该调用 `reject`。这可以使用任何类型的参数来完成（就像 `resolve` 一样）。但是建议使用 `Error` 对象（或继承自 `Error` 的对象）。这样做的理由很快就会显而易见。

<div style="color: red">2.这儿只能有一个结果或一个 error</div>

executor 只能调用一个 `resolve` 或一个 `reject`。任何状态的更改都是最终的。

所有其他的再对 `resolve` 和 `reject` 的调用都会被忽略：

```javascript
let promise = new Promise(function(resolve, reject) {
  resolve("done");

  reject(new Error("…")); // 被忽略
  setTimeout(() => resolve("…")); // 被忽略
});
```

这儿的宗旨是，一个被 executor 完成的工作只能有一个结果或一个 error。

并且，`resolve/reject` 只需要一个参数（或不包含任何参数），并且将忽略额外的参数。



#### 2.then：

语法如下：

```javascript
promise.then(
  function(result) { /* handle a successful result */ },
  function(error) { /* handle an error */ }
);
```

`.then` 的第一个参数是一个函数，该函数将在 promise resolved 后运行并接收结果。

`.then` 的第二个参数也是一个函数，该函数将在 promise rejected 后运行并接收 error。

成功的例子：

```js
let promise = new Promise(function(resolve, reject) {
  setTimeout(() => resolve("done!"), 1000);
});

// resolve 运行 .then 中的第一个函数
promise.then(
  result => alert(result), // 1 秒后显示 "done!"
  error => alert(error) // 不运行
);
```

失败的例子：

```js
let promise = new Promise(function(resolve, reject) {
  setTimeout(() => reject(new Error("Whoops!")), 1000);
});

// reject 运行 .then 中的第二个函数
promise.then(
  result => alert(result), // 不运行
  error => alert(error) // 1 秒后显示 "Error: Whoops!"
);
```

只对成功感兴趣，可以只为 `.then` 提供一个函数参数：

```javascript
let promise = new Promise(resolve => {
  setTimeout(() => resolve("done!"), 1000);
});

promise.then(alert); // 1 秒后显示 "done!"
```

#### 3.catch：

只对失败感兴趣：

```javascript
let promise = new Promise((resolve, reject) => {
  setTimeout(() => reject(new Error("Whoops!")), 1000);
});

// .catch(f) 与 promise.then(null, f) 一样
promise.catch(alert); // 1 秒后显示 "Error: Whoops!"
```

`.catch(f)` 调用是 `.then(null, f)` 的完全的模拟，它只是一个简写形式。

#### 4.finally

`f` 总是在 promise 被 settled 时运行：即 promise 被 resolve 或 reject。

1. `finally` 处理程序（handler）没有参数。在 `finally` 中，我们不知道 promise 是否成功。没关系，因为我们的任务通常是执行“常规”的定稿程序（finalizing procedures）。

2. `finally` 处理程序将结果和 error 传递给下一个处理程序。

   例如，在这儿结果被从 `finally` 传递给了 `then`：

   ```javascript
   new Promise((resolve, reject) => {
     setTimeout(() => resolve("result"), 2000)
   })
     .finally(() => alert("Promise ready"))
     .then(result => alert(result)); // <-- .then 对结果进行处理
   ```

   在这儿，promise 中有一个 error，这个 error 被从 `finally` 传递给了 `catch`：

   ```javascript
   new Promise((resolve, reject) => {
     throw new Error("error");
   })
     .finally(() => alert("Promise ready"))
     .catch(err => alert(err));  // <-- .catch 对 error 对象进行处理
   ```



## 12.Generator，高级 iteration

### 12.1Generator

推荐结合原文一起看

[Generator](https://zh.javascript.info/generators)

#### 基础：

```js
function* generateSequence() {
    yield;
    yield 2;
    return 3;
}

let generator = generateSequence();

console.log(generator)

let one = generator.next();
let two = generator.next()
let three = generator.next()
// 到这里已经执行完了
let four = generator.next()

console.log(generator)
console.log(one)
console.log(two)
console.log(three)
console.log(four)

```



![image-20220509000448659](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220509000448659.png)

#### 可迭代

```js
let range = {
  from: 1,
  to: 5,

  // for..of range 在一开始就调用一次这个方法
  [Symbol.iterator]() {
    // ...它返回 iterator object：
    // 后续的操作中，for..of 将只针对这个对象，并使用 next() 向它请求下一个值
    return {
      current: this.from,
      last: this.to,

      // for..of 循环在每次迭代时都会调用 next()
      next() {
        // 它应该以对象 {done:.., value :...} 的形式返回值
        if (this.current <= this.last) {
          return { done: false, value: this.current++ };
        } else {
          return { done: true };
        }
      }
    };
  }
};

// 迭代整个 range 对象，返回从 `range.from` 到 `range.to` 范围的所有数字
alert([...range]); // 1,2,3,4,5
```



```js
let range = {
  from: 1,
  to: 5,

  *[Symbol.iterator]() { // [Symbol.iterator]: function*() 的简写形式
    for(let value = this.from; value <= this.to; value++) {
      yield value;
    }
  }
};

alert( [...range] ); // 1,2,3,4,5
```

<div style="color: red">function* f(…) 或 function *f(…)语法相同</div>

<div style="color: red">Spread 语法内部使用了迭代器来收集元素，与 `for..of` 的方式相同。</div>

两者功能完全相同

#### generator组合

yield*新写法

没怎么看懂……

#### [“yield” 是一条双向路](https://zh.javascript.info/generators#yield-shi-yi-tiao-shuang-xiang-lu)

next()可以传参数

推荐看原文，很容易看懂

```js
function* gen() {
  let ask1 = yield "2 + 2 = ?";

  alert(ask1); // 4

  let ask2 = yield "3 * 3 = ?"

  alert(ask2); // 9
}

let generator = gen();

alert( generator.next().value ); // "2 + 2 = ?"

alert( generator.next(4).value ); // "3 * 3 = ?"

alert( generator.next(9).done ); // true
```



## 13.模块

### 13.1模块简介

[模块 (Module) 简介](https://zh.javascript.info/modules-intro)

#### 1.import和export

![image-20220327133652150](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327133652150.png)

由于模块支持特殊的关键字和功能，因此我们必须通过使用 `<script type="module">` 特性（attribute）来告诉浏览器，此脚本应该被当作模块（module）来对待。

#### 2.模块只通过 HTTP(s) 工作，而非本地

如果你尝试通过 `file://` 协议在本地打开一个网页，你会发现 `import/export` 指令不起作用。你可以使用本地 Web 服务器，例如 [static-server](https://www.npmjs.com/package/static-server#getting-started)，或者使用编辑器的“实时服务器”功能，例如 VS Code 的 [Live Server Extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) 来测试模块。

#### 3.模块作用域，严格模式

模块中始终使用严格模式。

每个模块都有自己的顶级作用域（top-level scope）。换句话说，一个模块中的顶级作用域变量和函数在其他脚本中是不可见的。

#### 4.模块代码仅在第一次导入时被解析

https://zh.javascript.info/modules-intro#mo-kuai-dai-ma-jin-zai-di-yi-ci-dao-ru-shi-bei-jie-xi

假设一个模块导出了一个对象：

```javascript
// 📁 admin.js
export let admin = {
  name: "John"
};
```

如果这个模块被导入到多个文件中，模块仅在第一次被导入时被解析，并创建 `admin` 对象，然后将其传入到所有的导入。

所有的导入都只获得了一个唯一的 `admin` 对象：

```javascript
// 📁 1.js
import { admin } from './admin.js';
admin.name = "Pete";

// 📁 2.js
import { admin } from './admin.js';
alert(admin.name); // Pete

// 1.js 和 2.js 引用的是同一个 admin 对象
// 在 1.js 中对对象做的更改，在 2.js 中也是可见的
```

**这种行为实际上非常方便，因为它允许我们“配置”模块。**

#### 5.在一个模块中，“this” 是 undefined

```html
<script>
  alert(this); // window
</script>

<script type="module">
  alert(this); // undefined
</script>
```

#### 6.延时加载

模块脚本总是会“看到”已完全加载的 HTML 页面，包括在它们下方的 HTML 元素。

例如：

```js
<script type="module">
  alert(typeof button); // object：脚本可以“看见”下面的 button
  // 因为模块是被延迟的（deferred，所以模块脚本会在整个页面加载完成后才运行
</script>

相较于下面这个常规脚本：

<script>
  alert(typeof button); // button 为 undefined，脚本看不到下面的元素
  // 常规脚本会立即运行，常规脚本的运行是在在处理页面的其余部分之前进行的
</script>

<button id="button">Button</button>
```

请注意：上面的第二个脚本实际上要先于前一个脚本运行！所以我们会先看到 `undefined`，然后才是 `object`。

#### 7.Async属性

下面的内联脚本具有 `async` 特性，因此它不会等待任何东西。

它执行导入（fetch `./analytics.js`），并在准备导入完成时运行，即使 HTML 文档还未完成，或者其他脚本仍在等待处理中。

这对于不依赖任何其他东西的功能来说是非常棒的，例如计数器，广告，文档级事件监听器。

```js
<!-- 所有依赖都获取完成（analytics.js）然后脚本开始运行 -->
<!-- 不会等待 HTML 文档或者其他 <script> 标签 -->
<script async type="module">
  import {counter} from './analytics.js';

  counter.count();
</script>
```

#### 8.外部脚本

具有 `type="module"` 的外部脚本（external script）在两个方面有所不同：

1. 具有相同 `src` 的外部脚本仅运行一次：

   ```html
   <!-- 脚本 my.js 被加载完成（fetched）并只被运行一次 -->
   <script type="module" src="my.js"></script>
   <script type="module" src="my.js"></script>
   ```

2. 从另一个源（例如另一个网站）获取的外部脚本需要 [CORS](https://developer.mozilla.org/zh/docs/Web/HTTP/CORS) header，如我们在 [Fetch：跨源请求](https://zh.javascript.info/fetch-crossorigin) 一章中所讲的那样。换句话说，如果一个模块脚本是从另一个源获取的，则远程服务器必须提供表示允许获取的 header `Access-Control-Allow-Origin`。

   ```html
   <!-- another-site.com 必须提供 Access-Control-Allow-Origin -->
   <!-- 否则，脚本将无法执行 -->
   <script type="module" src="http://another-site.com/their.js"></script>
   ```

#### 9.构建工具

![image-20220403134337229](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220403134337229.png)



### 13.2导出和导入

[导出和导入](https://zh.javascript.info/import-export)

这一章内容平时使用最为频繁，推荐看原文。这里简单记录下

<div style="color: red">我们把 `import/export` 语句放在脚本的顶部或底部，都没关系。</div>

#### 1.Import *

通常，我们把要导入的东西列在花括号 `import {...}` 中，就像这样：

```javascript
// 📁 main.js
import {sayHi, sayBye} from './say.js';

sayHi('John'); // Hello, John!
sayBye('John'); // Bye, John!
```

但是如果有很多要导入的内容，我们可以使用 `import * as <obj>` 将所有内容导入为一个对象，例如：

```javascript
// 📁 main.js
import * as say from './say.js';

say.sayHi('John');
say.sayBye('John');
```

这样写其实不好，因为打包时，webpack有树摇机制。准确的命名导入更好

#### 2.Import as

我们也可以使用 `as` 让导入具有不同的名字。

例如，简洁起见，我们将 `sayHi` 导入到局部变量 `hi`，将 `sayBye` 导入到 `bye`：

```javascript
// 📁 main.js
import {sayHi as hi, sayBye as bye} from './say.js';

hi('John'); // Hello, John!
bye('John'); // Bye, John!
```

#### 3.Export as

导出也具有类似的语法。

我们将函数导出为 `hi` 和 `bye`：

```javascript
// 📁 say.js
...
export {sayHi as hi, sayBye as bye};
```

现在 `hi` 和 `bye` 是在外面使用时的正式名称：

```javascript
// 📁 main.js
import * as say from './say.js';

say.hi('John'); // Hello, John!
say.bye('John'); // Bye, John!
```

#### 4.Export default

模块提供了一个特殊的默认导出 `export default` 语法，以使“一个模块只做一件事”的方式看起来更好。

将 `export default` 放在要导出的实体前：

```javascript
// 📁 user.js
export default class User { // 只需要添加 "default" 即可
  constructor(name) {
    this.name = name;
  }
}
```

然后将其导入而不需要花括号：

```javascript
// 📁 main.js
import User from './user.js'; // 不需要花括号 {User}，只需要写成 User 即可

new User('John');
```

<div style="color: red">请记住，`import` 命名的导出时需要花括号，而 `import` 默认的导出时不需要花括号。</div>

| 默认的导出                        | 命名的导出                |
| :-------------------------------- | :------------------------ |
| `export default class User {...}` | `export class User {...}` |
| `import User from ...`            | `import {User} from ...`  |

我们可以在一个模块中同时有默认的导出和命名的导出，但是实际上人们通常不会混合使用它们。模块要么是命名的导出要么是默认的导出。

由于每个文件最多只能有一个默认的导出，因此导出的实体可能没有名称。

例如，下面这些都是完全有效的默认的导出：

```javascript
export default class { // 没有类名
  constructor() { ... }
}
export default function(user) { // 没有函数名
  alert(`Hello, ${user}!`);
}
// 导出单个值，而不使用变量
export default ['Jan', 'Feb', 'Mar','Apr', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
```

#### 5.重新导出

“重新导出（Re-export）”语法 `export ... from ...` 允许导入内容，并立即将其导出（可能是用的是其他的名字），就像这样：

```javascript
export {sayHi} from './say.js'; // 重新导出 sayHi

export {default as User} from './user.js'; // 重新导出 default
```

##### 使用场景：

作者举了一个例子：

我们正在编写一个 “package”：一个包含大量模块的文件夹，其中一些功能是导出到外部的（像 NPM 这样的工具允许我们发布和分发这样的 package，但我们不是必须要去使用它们），并且其中一些模块仅仅是供其他 package 中的模块内部使用的 “helpers”。

文件结构可能是这样的：

```none
auth/
    index.js
    user.js
    helpers.js
    tests/
        login.js
    providers/
        github.js
        facebook.js
        ...
```

我们希望通过单个入口暴露包的功能。

换句话说，想要使用我们的包的人，应该只从“主文件” `auth/index.js` 导入。

像这样：

```javascript
import {login, logout} from 'auth/index.js'
```

我们可能需要这样做：

由于实际导出的功能分散在 package 中，所以我们可以将它们导入到 `auth/index.js`，然后再从中导出它们：

```javascript
// 📁 auth/index.js

// 导入 login/logout 然后立即导出它们
import {login, logout} from './helpers.js';
export {login, logout};

// 将默认导出导入为 User，然后导出它
import User from './user.js';
export {User};
```



现在使用我们 package 的人可以 `import {login} from "auth/index.js"`。

<div style="color: red">语法 export ... from ... 只是下面这种导入-导出的简写：</div>

```javascript
// 📁 auth/index.js
// 重新导出 login/logout
export {login, logout} from './helpers.js';

// 将默认导出重新导出为 User
export {default as User} from './user.js';
```

##### 重新导出默认导出：

重新导出时，默认导出需要单独处理。

假设我们有一个 `user.js` 脚本，其中写了 `export default class User`，并且我们想重新导出类 `User`：

```javascript
// 📁 user.js
export default class User {
  // ...
}
```

我们可能会遇到两个问题：

1. `export User from './user.js'` 无效。这会导致一个语法错误。

   要重新导出默认导出，我们必须明确写出 `export {default as User}`，就像上面的例子中那样。

2. `export * from './user.js'` 重新导出只导出了命名的导出，但是忽略了默认的导出。

   如果我们想将命名的导出和默认的导出都重新导出，那么需要两条语句：

   ```javascript
   export * from './user.js'; // 重新导出命名的导出
   export {default} from './user.js'; // 重新导出默认的导出
   ```

重新导出一个默认导出的这种奇怪现象，是某些开发者不喜欢默认导出，而是喜欢命名的导出的原因之一。



### 13.3动态导入

https://zh.javascript.info/modules-dynamic-imports

这部分在vue路由懒加载中有使用到，webpack代码分割时也有使用到

















# 浏览器：文档，事件，接口

## Document

很多操作节点的方法很少使用，知道有这个东西，用的时候回来查查就行。一般来说都用框架了吧，估计自己封装组件库

会经常使用到。

### 1.2DOM树

[DOM 树](https://zh.javascript.info/dom-nodes)

空格和换行符都是完全有效的字符，就像字母和数字。它们形成文本节点并成为 DOM 的一部分，但这种文本节点一般都会被工具隐藏。

#### 节点类型

一共有 [12 种节点类型](https://dom.spec.whatwg.org/#node)。实际上，我们通常用到的是其中的 4 种：

1. `document` — DOM 的“入口点”。
2. 元素节点 — HTML 标签，树构建块。
3. 文本节点 — 包含文本。
4. 注释 — 有时我们可以将一些信息放入其中，它不会显示，但 JS 可以从 DOM 中读取它。

### 1.3遍历DOM

[遍历 DOM](https://zh.javascript.info/dom-navigation)

#### 顶层节点

最顶层的树节点可以直接作为 `document` 的属性来使用：

- `<html>` = `document.documentElement`

  最顶层的 document 节点是 `document.documentElement`。这是对应 `<html>` 标签的 DOM 节点。

- `<body>` = `document.body`

  另一个被广泛使用的 DOM 节点是 `<body>` 元素 — `document.body`。

- `<head>` = `document.head`

  `<head>` 标签可以通过 `document.head` 访问。

#### 子节点：

1.**`childNodes` 集合列出了所有子节点，包括文本节点。**

2.**`firstChild` 和 `lastChild` 属性是访问第一个和最后一个子元素的快捷方式。**

```js
elem.childNodes[0] === elem.firstChild
elem.childNodes[elem.childNodes.length - 1] === elem.lastChild
```

3.`childNodes` 看起来就像一个数组。但实际上它并不是一个数组，而是一个 **集合** — 一个类数组的可迭代对象。

如果我们想要使用数组的方法的话，我们可以使用 `Array.from` 方法来从集合创建一个“真”数组：

```js
alert( Array.from(document.body.childNodes).filter ); // function
```

4.`elem.hasChildNodes()` 用于检查节点是否有子节点。

#### 兄弟节点和父节点

下一个兄弟节点在 `nextSibling` 属性中，上一个是在 `previousSibling` 属性中。

可以通过 `parentNode` 来访问父节点。

```js
// <body> 的父节点是 <html>
alert( document.body.parentNode === document.documentElement ); // true

// <head> 的后一个是 <body>
alert( document.head.nextSibling ); // HTMLBodyElement

// <body> 的前一个是 <head>
alert( document.body.previousSibling ); // HTMLHeadElement
```

#### 纯元素导航

但是对于很多任务来说，我们并不想要文本节点或注释节点。我们希望操纵的是代表标签的和形成页面结构的元素节点。

所以，让我们看看更多只考虑 **元素节点** 的导航链接（navigation link）：

<div style="color: red">这些链接和我们在上面提到过的类似，只是在词中间加了 `Element`：</div>

- `children` — 仅那些作为元素节点的子代的节点。
- `firstElementChild`，`lastElementChild` — 第一个和最后一个子元素。
- `previousElementSibling`，`nextElementSibling` — 兄弟元素。
- `parentElement` — 父元素。

所以说访问节点的方式如下：

- 对于所有节点：`parentNode`，`childNodes`，`firstChild`，`lastChild`，`previousSibling`，`nextSibling`。
- 仅对于元素节点：`parentElement`，`children`，`firstElementChild`，`lastElementChild`，`previousElementSibling`，`nextElementSibling`。

小细节：

**为什么是** `parentElement`**? 父节点可以不是一个元素吗？**

```js
alert( document.documentElement.parentNode ); // document
alert( document.documentElement.parentElement ); // null
```

根节点 `document.documentElement`（`<html>`）的父节点是 `document`。但 `document` 不是一个元素节点，所以 `parentNode` 返回了 `document`，但 `parentElement` 返回的是 `null`。

### 1.4搜索：getElement*，querySelector*

[搜索：getElement*，querySelector*](https://zh.javascript.info/searching-elements-dom)

提供了很多访问节点的方法，我觉得用querySelector和querySelectorAll就足够了。

记一些不常用的方法

#### match:

只会检查 `elem` 是否与给定的 CSS 选择器匹配。它返回 `true` 或 `false`。

```js
<a href="http://example.com/file.zip">...</a>
<a href="http://ya.ru">...</a>

<script>
  // 不一定是 document.body.children，还可以是任何集合
  for (let elem of document.body.children) {
    if (elem.matches('a[href$="zip"]')) {
      alert("The archive reference: " + elem.href );
    }
  }
</script>
```

#### getElementsBy*

这个居然也成为了时代的眼泪了吗？以前经常用的。

注意返回的是集合哈

#### 实时的集合

所有的 `"getElementsBy*"` 方法都会返回一个 **实时的（live）** 集合。这样的集合始终反映的是文档的当前状态，并且在文档发生更改时会“自动更新”。

```js
<div>First div</div>

<script>
  let divs = document.getElementsByTagName('div');
  alert(divs.length); // 1
</script>

<div>Second div</div>

<script>
  alert(divs.length); // 2
</script>
```

`querySelectorAll` 返回的是一个 **静态的** 集合。就像元素的固定数组。

```js
<div>First div</div>

<script>
  let divs = document.querySelectorAll('div');
  alert(divs.length); // 1
</script>

<div>Second div</div>

<script>
  alert(divs.length); // 1
</script>
```

让我们在这里提一下另一种用来检查子级与父级之间关系的方法，因为它有时很有用：

- 如果 `elemB` 在 `elemA` 内（`elemA` 的后代）或者 `elemA==elemB`，`elemA.contains(elemB)` 将返回 true。

#### 习题:

这个习题看懂，就没多大问题了

https://zh.javascript.info/searching-elements-dom#sou-suo-yuan-su

### 1.5节点属性

[节点属性：type，tag 和 content](https://zh.javascript.info/basic-dom-node-properties)

所有属性：

传送门：

[HTML Standard (whatwg.org)](https://html.spec.whatwg.org/#htmlinputelement)

我觉得很少使用这些节点属性吧，简单看看就行了。

#### nodeType：

用数字检查节点类型的，过时了。

#### nodeName和tagName:

给定一个 DOM 节点，我们可以从 `nodeName` 或者 `tagName` 属性中读取它的标签名.

区别在于

- `tagName` 属性仅适用于 `Element` 节点。
- nodeName是为任意 Node定义的：
  - 对于元素，它的意义与 `tagName` 相同。
  - 对于其他节点类型（text，comment 等），它拥有一个对应节点类型的字符串。

和1.3节讲的纯元素导航很像喔。

#### innerHTML：内容

[innerHTML](https://w3c.github.io/DOM-Parsing/#the-innerhtml-mixin) 属性允许将元素中的 HTML 获取为字符串形式。

<div style="color: red">这个用的比较多。</div>

```html
下面这个示例显示了 document.body 中的内容，然后将其完全替换：

<body>
  <p>A paragraph</p>
  <div>A div</div>

  <script>
    alert( document.body.innerHTML ); // 读取当前内容
    document.body.innerHTML = 'The new BODY!'; // 替换它
  </script>

</body>
我们可以尝试插入无效的 HTML，浏览器会修复我们的错误：

<body>

  <script>
    document.body.innerHTML = '<b>test'; // 忘记闭合标签
    alert( document.body.innerHTML ); // <b>test</b>（被修复了）
  </script>

</body>
```

从技术上来说，下面这两行代码的作用相同：

```javascript
elem.innerHTML += "...";
// 进行写入的一种更简短的方式：
elem.innerHTML = elem.innerHTML + "..."
```

换句话说，`innerHTML+=` 做了以下工作：

1. 移除旧的内容。
2. 然后写入新的 `innerHTML`（新旧结合）。

<div style="color: red">因为内容已“归零”并从头开始重写，因此所有的图片和其他资源都将重写加载。</div>

所以慎用+=innerHTML喔。

#### outerHTML

`outerHTML` 属性包含了元素的完整 HTML。就像 `innerHTML` 加上元素本身一样。

下面是一个示例：

```html
<div id="elem">Hello <b>World</b></div>

<script>
  alert(elem.outerHTML); // <div id="elem">Hello <b>World</b></div>
</script>
```

与innerHTML的不同建议看原文，有点多。

#### 文本节点

`innerHTML` 属性仅对元素节点有效。

其他节点类型，例如文本节点，具有它们的对应项：`nodeValue` 和 `data` 属性。这两者在实际使用中几乎相同，只有细微规范上的差异。因此，我们将使用 `data`，因为它更短。

读取文本节点和注释节点的内容的示例：

```html
<body>
  Hello
  <!-- Comment -->
  <script>
    let text = document.body.firstChild;
    alert(text.data); // Hello

    let comment = text.nextSibling;
    alert(comment.data); // Comment
  </script>
</body>
```

#### textContext: 纯文本

`textContent` 提供了对元素内的 **文本** 的访问权限：仅文本，去掉所有 `<tags>`。

例如：

```html
<div id="news">
  <h1>Headline!</h1>
  <p>Martians attack people!</p>
</div>

<script>
  // Headline! Martians attack people!
  alert(news.textContent);
</script>
```

#### hidden

“hidden” 特性（attribute）和 DOM 属性（property）指定元素是否可见。

我们可以在 HTML 中使用它，或者使用 JavaScript 对其进行赋值，如下所示：

```html
<div>Both divs below are hidden</div>

<div hidden>With the attribute "hidden"</div>

<div id="elem">JavaScript assigned the property "hidden"</div>

<script>
  elem.hidden = true;
</script>
```

从技术上来说，`hidden` 与 `style="display:none"` 做的是相同的事。但 `hidden` 写法更简洁。

这里有一个 blinking 元素：

```html
<div id="elem">A blinking element</div>

<script>
  setInterval(() => elem.hidden = !elem.hidden, 1000);
</script>
```



#### 习题

这个可以看看，还可以复习原型知识

[层次结构中的 "document" 在哪里？](https://zh.javascript.info/basic-dom-node-properties#ceng-ci-jie-gou-zhong-de-document-zai-na-li)

### 1.6特性和属性

[特性和属性（Attributes and properties）](https://zh.javascript.info/dom-attributes-and-properties)

这一章内容多，杂。而且两个概念含义太相近了，很容易绕混，建议看原文

可以把其中的自定义属性dataset详细看看，我项目里还是用到了

[非标准的特性，dataset](https://zh.javascript.info/dom-attributes-and-properties#fei-biao-zhun-de-te-xing-dataset)

### 1.7修改文档

[修改文档（document）](https://zh.javascript.info/modifying-document)

这个用的就很多了。

#### 插入元素

```html
<ol id="ol">
  <li>0</li>
  <li>1</li>
  <li>2</li>
</ol>

<script>
  ol.before('before'); // 将字符串 "before" 插入到 <ol> 前面
  ol.after('after'); // 将字符串 "after" 插入到 <ol> 后面

  let liFirst = document.createElement('li');
  liFirst.innerHTML = 'prepend';
  ol.prepend(liFirst); // 将 liFirst 插入到 <ol> 的最开始

  let liLast = document.createElement('li');
  liLast.innerHTML = 'append';
  ol.append(liLast); // 将 liLast 插入到 <ol> 的最末尾
</script>
```



![image-20220425214324828](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220425214324828.png)

#### 替换节点

- `node.replaceWith(...nodes or strings)` —— 将 `node` 替换为给定的节点或字符串。

#### 作为HTML插入

```html
<div id="div"></div>
<script>
  div.insertAdjacentHTML('beforebegin', '<p>Hello</p>');
  div.insertAdjacentHTML('afterend', '<p>Bye</p>');
</script>
```

……将导致：

```html
<p>Hello</p>
<div id="div"></div>
<p>Bye</p>
```

这就是我们可以在页面上附加任意 HTML 的方式。

这是插入变体的示意图：

![image-20220425214739299](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220425214739299.png)

我们很容易就会注意到这张图片和上一张图片的相似之处。插入点实际上是相同的，但此方法插入的是 HTML。

#### 移除节点

想要移除一个节点，可以使用 `node.remove()`。

请注意：如果我们要将一个元素 **移动** 到另一个地方，则无需将其从原来的位置中删除。

**所有插入方法都会自动从旧位置删除该节点。**

例如，让我们进行元素交换：

```html
<div id="first">First</div>
<div id="second">Second</div>
<script>
  // 无需调用 remove
  second.after(first); // 获取 #second，并在其后面插入 #first
</script>
```

#### 克隆节点

调用 `elem.cloneNode(true)` 来创建元素的一个“深”克隆 — 具有所有特性（attribute）和子元素。如果我们调用 `elem.cloneNode(false)`，那克隆就不包括子元素。

```html
<style>
    .alert {
      padding: 15px;
      border: 1px solid #d6e9c6;
      border-radius: 4px;
      color: #3c763d;
      background-color: #dff0d8;
    }
    </style>
    
    <div class="alert" id="div">
      <strong>Hi there!</strong> You've read an important message.
    </div>
    
    <script>
      let div2 = div.cloneNode(true); // 克隆消息
      div2.querySelector('strong').innerHTML = 'Bye there!'; // 修改克隆
    
      div.after(div2); // 在已有的 div 后显示克隆
    </script>
```

![image-20220426131441105](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220426131441105.png)

#### DocumentFragment

我目前没看出来这个DOM节点有啥特别的



`DocumentFragment` 是一个特殊的 DOM 节点，用作来传递节点列表的包装器（wrapper）。

我们可以向其附加其他节点，但是当我们将其插入某个位置时，则会插入其内容。

例如，下面这段代码中的 `getListContent` 会生成带有 `<li>` 列表项的片段，然后将其插入到 `<ul>` 中：

```html
<ul id="ul"></ul>

<script>
function getListContent() {
  let fragment = new DocumentFragment();

  for(let i=1; i<=3; i++) {
    let li = document.createElement('li');
    li.append(i);
    fragment.append(li);
  }

  return fragment;
}

ul.append(getListContent()); // (*)
</script>
```

请注意，在最后一行 `(*)` 我们附加了 `DocumentFragment`，但是它和 `ul` “融为一体（blends in）”了，所以最终的文档结构应该是：

```html
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
```

#### 老式的 insert/remove 方法

- 这里还有“旧式”的方法：

  - `parent.appendChild(node)`
  - `parent.insertBefore(node, nextSibling)`
  - `parent.removeChild(node)`
  - `parent.replaceChild(newElem, node)`

  这些方法都返回 `node`。

#### 聊一聊 “document.write”

还有一个非常古老的向网页添加内容的方法：`document.write`。

语法如下：

```html
<p>Somewhere in the page...</p>
<script>
  document.write('<b>Hello from JS</b>');
</script>
<p>The end</p>
```

调用 `document.write(html)` 意味着将 `html` “就地马上”写入页面。`html` 字符串可以是动态生成的，所以它很灵活。我们可以使用 JavaScript 创建一个完整的页面并对其进行写入。

**`document.write` 调用只在页面加载时工作。**

如果我们稍后调用它，则现有文档内容将被擦除。

例如：

```html
<p>After one second the contents of this page will be replaced...</p>
<script>
  // 1 秒后调用 document.write
  // 这时页面已经加载完成，所以它会擦除现有内容
  setTimeout(() => document.write('<b>...By this.</b>'), 1000);
</script>
```

因此，在某种程度上讲，它在“加载完成”阶段是不可用的，这与我们上面介绍的其他 DOM 方法不同。

但它运行起来出奇的快，因为它 **不涉及 DOM 修改**。它直接写入到页面文本中，而此时 DOM 尚未构建。



要在页面加载完成之前将 HTML 附加到页面：

- `document.write(html)`

页面加载完成后，这样的调用将会擦除文档。多见于旧脚本。

#### 习题：

太难了！原生的操作dom节点，还是用的少

[任务](https://zh.javascript.info/modifying-document#tasks)





### 1.8样式和类

这章怎么说习惯用jquery的css了……。原生的看看就好

[样式和类](https://zh.javascript.info/styles-and-classes)

#### className和classList

```html
<body class="main page">
  <script>
    alert(document.body.className); // main page
  </script>
</body>
```

如果我们对 `elem.className` 进行赋值，它将替换类中的整个字符串。有时，这正是我们所需要的，但通常我们希望添加/删除单个类。这个时候用classList

`classList` 的方法：

- `elem.classList.add/remove(class)` — 添加/移除类。
- `elem.classList.toggle(class)` — 如果类不存在就添加类，存在就移除它。
- `elem.classList.contains(class)` — 检查给定类，返回 `true/false`。

此外，`classList` 是可迭代的，因此，我们可以像下面这样列出所有类：

```html
<body class="main page">
  <script>
    for (let name of document.body.classList) {
      alert(name); // main，然后是 page
    }
  </script>
</body>
```

#### 元素样式

`elem.style` 属性是一个对象，它对应于 `"style"` 特性（attribute）中所写的内容。`elem.style.width="100px"` 的效果等价于我们在 `style` 特性中有一个 `width:100px` 字符串。

对于多词（multi-word）属性，使用驼峰式 camelCase：

```javascript
background-color  => elem.style.backgroundColor
z-index           => elem.style.zIndex
border-left-width => elem.style.borderLeftWidth
```

#### 注意单位

就是要加上px喔

#### [计算样式：getComputedStyle](https://zh.javascript.info/styles-and-classes#ji-suan-yang-shi-getcomputedstyle)

这是用来读取样式的。建议看原文。

### 1.9元素大小和滚动

[元素大小和滚动](https://zh.javascript.info/size-and-scroll)

这张内容很多，很难记住那些几何属性。建议看原文

传送门：

几何属性这里面写的很形象，记不住也没有关系

[这些原生DOM操作你还记住多少😨 - 掘金 (juejin.cn)](https://juejin.cn/post/6966062224892756005#heading-24)

### 1.10window大小和滚动

这个我应用过，在路由跳转时,可以把页面滚动到最上方。详细说明建议看原文

[Window 大小和滚动](https://zh.javascript.info/size-and-scroll-window)















# 其他文章

## 网络请求

### 3.1Fetch

[Fetch](https://zh.javascript.info/fetch)













## 正则表达式

忘了学，学了忘……正则怎么这么难记！！！

传送门：["dotall" | Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/?search=dotall)  查看特定正则兼容性

[Regulex：JavaScript Regular Expression Visualizer (jex.im)](https://jex.im/regulex/#!flags=&re=^(a|b)*%3F%24)            图像化正则表达式

![image-20220405011540682](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220405011540682.png)

![image-20220405014135499](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220405014135499.png)

### 7.0常用方法：

这个是我自己添加的，书里没详细写，或者说写的比较分散

#### match：

 **`match()`** 方法检索返回一个字符串匹配正则表达式的结果。

- 如果使用g标志，则将返回与完整正则表达式匹配的所有结果，但不会返回捕获组。
- 如果未使用g标志，则仅返回第一个完整匹配及其相关的捕获组（`Array`）。 在这种情况下，返回的项目将具有如下所述的其他属性。

<div style="color: red">所以有多个匹配结果最好还是使用matchAll,这样可以获得完整的捕获组</div> 

详见7.11捕获组

```js
alert( "Mop top".match(/[tm]op/gi) ); // "Mop", "top"两者构成的数组
alert( "Mop top".match(/[tm]op/i) ); // "Mop"  只有一个元素的数组
```

#### search：

如果匹配成功，则 `search()` 返回正则表达式在字符串中首次匹配项的索引;否则，返回 `-1`。

```js
alert( "Mop top".search(/top/gi) ); // 4
alert( "Mop top".search(/[H]op/i) ); // -1
```

#### test：

test方法执行一个检索，用来查看正则表达式与指定的字符串是否匹配。返回 `true` 或 `false`。

```js
alert( /top/gi.test("Mop top") ); // true
alert( /[H]op/i.test("Mop top") ); // false
```

#### replace:

**`replace()`** 方法返回一个由替换值（`replacement`）替换部分或所有的模式（`pattern`）匹配项后的新字符串。模式可以是一个字符串或者一个[正则表达式](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/RegExp)，替换值可以是一个字符串或者一个每次匹配都要调用的回调函数。**如果`pattern`是字符串，则仅替换第一个匹配项。**

原字符串不会改变。

还有一个替换捕获组的用法，见7.11第4点

```js
let str = "+7(903)-123-45-67";

alert( str.replace(/\D/g, "") ); // 79031234567
```

#### matchAll:

[搜索所有具有组的匹配项：matchAll](https://zh.javascript.info/regexp-groups#sou-suo-suo-you-ju-you-zu-de-pi-pei-xiang-matchall)

就像 `match` 一样，它寻找匹配项，但有 3 个区别：

1. 它返回的不是数组，而是一个可迭代的对象。
2. 当标志 `g` 存在时，它将每个匹配组作为一个数组返回。
3. 如果没有匹配项，则不返回 `null`，而是返回一个空的可迭代对象。
4. 有多个匹配项，必须加标志g。否则报错（这是我自己发现的）

我们可以用Array.from把可迭代对象转换为数组

### 7.1模式和修饰符

[模式（Patterns）和修饰符（flags）](https://zh.javascript.info/regexp-introduction)

#### 1.正则表达式

正则表达式（可叫作“regexp”或者“reg”）包含 **模式** 和可选的 **修饰符**。

较长一点的语法：

```javascript
regexp = new RegExp("pattern", "flags");
```

…较短一点的语法，使用斜杠 `"/"`：

```javascript
regexp = /pattern/; // 没有修饰符
regexp = /pattern/gmi; // 伴随修饰符 g、m 和 i（后面会讲到）
```

斜杠 `"/"` 会告诉 JavaScript 我们正在创建一个正则表达式。它的作用类似于字符串的引号。

#### 2.用法

使用 [search](https://developer.mozilla.org/zh/docs/Web/JavaScript/Reference/Global_Objects/String/search) 方法。

```javascript
let str = "I love JavaScript!"; // 将在这里搜索

let regexp = /love/;
alert( str.search(regexp) ); // 2
```

`str.search` 方法会查找模式 `/love/`，然后返回匹配项在字符串中的位置。我们可以猜到，`/love/` 是最简单的模式。它所做的就是简单的子字符串的查找。

上面的代码等同于：

```javascript
let str = "I love JavaScript!"; // 将在这里搜索

let substr = 'love';
alert( str.search(substr) ); // 2
```

所以搜索 `/love/` 与搜索 `"love"` 是等价的。

##### 使用new RegExp()的场合

1.变量插入

2.动态创建

```javascript
let search = prompt("What you want to search?", "love");
let regexp = new RegExp(search);

// 找到用户想要的任何东西
alert( "I love JavaScript".search(regexp));
```

#### 3.最简单的修饰符：i

最简单的修饰符就是 `i` 了。

示例代码如下：

```javascript
let str = "I love JavaScript!";

alert( str.search(/LOVE/) ); // -1（没找到）
alert( str.search(/LOVE/i) ); // 2
```

1. 第一个搜索返回的是 `-1`（也就是没找到），因为搜索默认是区分大小写的。
2. 使用修饰符 `/LOVE/i`，在字符串的第 2 个位置上搜索到了 `love`。

### 7.2字符类

[字符类](https://zh.javascript.info/regexp-character-classes)

**字符类（Character classes）** 是一个特殊的符号，匹配特定集中的任何符号。

#### 1.常见字符类



首先，让我们探索“数字”类。它写为 `\d`，对应于“任何一个数字”。

例如，让我们找到电话号码的第一个数字：

```javascript
let str = "+7(903)-123-45-67";

let regexp = /\d/;

alert( str.match(regexp) ); // 7
```

如果没有标志 `g`，则正则表达式仅查找第一个匹配项，即第一个数字 `\d`。

让我们添加 `g`标志来查找所有数字：

```javascript
let str = "+7(903)-123-45-67";

let regexp = /\d/g;

alert( str.match(regexp) ); // array of matches: 7,9,0,3,1,2,3,4,5,6,7

// let's make the digits-only phone number of them:
alert( str.match(regexp).join('') ); // 79031234567
```

最常用的字符类是：

- `\d`（“d” 来自 “digit”）

  数字：从 `0` 到 `9` 的字符。

- `\s`（“s” 来自 “space”）

  空格符号：包括空格，制表符 `\t`，换行符 `\n` 和其他少数稀有字符，例如 `\v`，`\f` 和 `\r`。

- `\w`（“w” 来自 “word”）

  “单字”字符：拉丁字母或数字或下划线 `_`。非拉丁字母（如西里尔字母或印地文）不属于 `\w`。

例如，`\d\s\w`表示“数字”，后跟“空格字符”，后跟“单字字符”，例如 `1 a`。

案例：

```javascript
let str = "Is there CSS4?";
let regexp = /CSS\d/

alert( str.match(regexp) ); // CSS4
```

我们还可以使用许多字符类：

```javascript
alert( "I love HTML5!".match(/\s\w\w\w\w\d/) ); // ' HTML5'
```

#### 2.反向类

对于每个字符类，都有一个“反向类”，用相同的字母表示，但要以大写书写形式。

“反向”表示它与所有其他字符匹配，例如：

- `\D`

  非数字：除 `\d` 以外的任何字符，例如字母。

- `\S`

  非空格符号：除 `\s` 以外的任何字符，例如字母。

- `\W`

  非单字字符：除 `\w` 以外的任何字符，例如非拉丁字母或空格。

案例：

```javascript
let str = "+7(903)-123-45-67";

alert( str.match(/\d/g).join('') ); // 79031234567
```

另一种快捷的替代方法是查找非数字 `\D` 并将其从字符串中删除：

```javascript
let str = "+7(903)-123-45-67";

alert( str.replace(/\D/g, "") ); // 79031234567
```

#### 3 点.字符

点 `.` 是一种特殊字符类，它与 “除换行符之外的任何字符” 匹配。

例如：

```javascript
alert( "Z".match(/./) ); // Z
```

或在正则表达式中间：

```javascript
let regexp = /CS.4/;

alert( "CSS4".match(regexp) ); // CSS4
alert( "CS-4".match(regexp) ); // CS-4
alert( "CS 4".match(regexp) ); // CS 4 (space is also a character)
```

请注意，点表示“任何字符”，而不是“缺少字符”。必须有一个与之匹配的字符：

```javascript
alert( "CS4".match(/CS.4/) ); // null, no match because there's no character for the dot
```

##### 真正意义上的匹配任意字符

默认情况下，点与换行符 `\n` 不匹配。

例如，正则表达式 `A.B` 匹配 `A`，然后匹配 `B` 和它们之间的任何字符，除了换行符`\n`：

```javascript
alert( "A\nB".match(/A.B/) ); // null (no match)
```

在许多情况下，当我们希望用点来表示“任何字符”（包括换行符）时。

这就是标志 `s` 所做的。如果有一个正则表达式，则点 `.` 实际上匹配任何字符：

```javascript
alert( "A\nB".match(/A.B/s) ); // A\nB (match!)
```

兼容性问题：

标志s有些浏览器不支持。可以用另一种方法

使用诸如 `[\s\S]` 之类的正则表达式来匹配“任何字符”。

```javascript
alert( "A\nB".match(/A[\s\S]B/) ); // A\nB (match!)
```

模式 `[\s\S]` 从字面上说：“空格字符或非空格字符”。换句话说，“任何东西”。我们可以使用另一对互补的类，例如 `[\d\D]`。甚至是 `[^]` —— 意思是匹配任何字符，除了什么都没有。

### 7.3Unicode：修饰符 “u” 和 class \p{...}

[Unicode：修饰符 “u” 和 class \p{...}](https://zh.javascript.info/regexp-unicode)

内容很多，扩展内容也很多。推荐看原文。

![image-20220405005108924](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220405005108924.png)

XRegExp:http://xregexp.com/

我在这里只摘取几个案例：

#### 1.摘取任意语言的任意字母

`\p{Letter}` 表示任何语言中的一个字母。我们也可以使用 `\p{L}`，因为 `L` 是 `Letter` 的一个别名（alias）。对于每种属性而言，几乎都存在对应的缩写别名。

在下面的例子中 3 种字母将会被查找出：英语、格鲁吉亚语和韩语。

```javascript
let str = "A ბ ㄱ";

alert( str.match(/\p{L}/gu) ); // A,ბ,ㄱ
alert( str.match(/\p{L}/g) ); // null（没有匹配的文本，因为没有修饰符“u”）
```

#### 2.查找16进制数字

让我们来查找 16 进制数字，写作 `xFF` 其中 `F` 是一个 16 进制的数字（0…9 或者 A…F）。

一个 16 进制数字可以表示为 `\p{Hex_Digit}`：

```javascript
let regexp = /x\p{Hex_Digit}\p{Hex_Digit}/u;

alert("number: xAF".match(regexp)); // xAF
```

#### 3.查找中文字符

有一个 unicode 属性 `Script` （一个书写系统），这个属性可以有一个值：`Cyrillic`，`Greek`，`Arabic`，`Han` （中文）等等，[这里是一个完整的列表](https://en.wikipedia.org/wiki/Script_(Unicode))。

为了实现查找一个给定的书写系统中的字符，我们需要使用 `Script=<value>`，例如对于西里尔字符：`\p{sc=Cyrillic}`, 中文字符：`\p{sc=Han}`，等等。

```javascript
let regexp = /\p{sc=Han}/gu; // returns Chinese hieroglyphs

let str = `Hello Привет 你好 123_456`;

alert( str.match(regexp) ); // 你,好
```

#### 4.查找货币

表示货币的字符，例如 `$`，`€`，`¥`，具有 unicode 属性 `\p{Currency_Symbol}`，缩写为 `\p{Sc}`。

让我们使用这一属性来查找符合“货币，接着是一个数字”的价格文本：

```javascript
let regexp = /\p{Sc}\d/gu;

let  str = `Prices: $2, €1, ¥9`;

alert( str.match(regexp) ); // $2,€1,¥9
```

![image-20220402150147779](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402150147779.png)

### 7.4锚点（Anchors)：字符串开始 ^ 和末尾 $

[锚点（Anchors)：字符串开始 ^ 和末尾 $](https://zh.javascript.info/regexp-anchors)

#### 1.开始和结尾

插入符号 `^` 和美元符号 `$` 在正则表达式中具有特殊的意义。它们被称为“锚点”。

插入符号 `^` 匹配文本开头，而美元符号 `$` － 则匹配文本末尾。

举个例子，让我们测试一下文本是否以 `Mary` 开头：

```javascript
let str1 = "Mary had a little lamb";
alert( /^Mary/.test(str1) ); // true
```

该模式 `^Mary` 的意思是：字符串开始，接着是 “Mary”。

与此类似，我们可以用 `snow$` 来测试文本是否以 `snow` 结尾:

```javascript
let str1 = "it's fleece was white as snow";
alert( /snow$/.test(str1) ); // true
```

在以上这些具体的例子中我们实际上可以用 `startsWith/endsWith` 来代替。正则表达式应该被用于更加复杂的测试中。

#### 2.完全匹配

这两个锚点 `^...$` 放在一起常常被用于测试一个字符串是否完全匹配一个模式。比如，测试用户的输入是否符合正确的格式。

测试是否匹配"12:34"类似时间格式

```js
let goodInput = "12:34";
let badInput = "12:345";

let regexp = /^\d\d:\d\d$/;
alert( regexp.test(goodInput) ); // true
alert( regexp.test(badInput) ); // false
```

![image-20220402151258437](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220402151258437.png)

<div style="color: red">空字符串是匹配 `^$`</div>



### 7.5Flag "m" — 多行模式

[Flag "m" — 多行模式](https://zh.javascript.info/regexp-multiline-mode)

通过 flag `/.../m` 可以开启多行模式。

这仅仅会影响 `^` 和 `$` 锚符的行为。

在多行模式下，它们不仅仅匹配文本的开始与结束，还匹配每一行的开始与结束。

#### 1.行的开头

正则表达式 `/^\d+/gm` 将匹配每一行的开头数字：

```javascript
let str = `1st place: Winnie
2nd place: Piglet
33rd place: Eeyore`;

alert( str.match(/^\d+/gm) ); // 1, 2, 33
```

没有 flag `/.../m` 时，仅仅是第一个数字被匹配到：

```javascript
let str = `1st place: Winnie
2nd place: Piglet
33rd place: Eeyore`;

alert( str.match(/^\d+/g) ); // 1
```

默认情况下，锚符 `^` 仅仅匹配文本的开头，在多行模式下，它匹配行的开头。

正则表达式引擎将会在文本中查找以锚符 `^` 开始的字符串，我们找到之后继续匹配 `\d+` 模式。

#### 2.行的结尾

正则表达式 `\w+$ 会找到每一行的最后一个单词：

```javascript
let str = `1st place: Winnie
2nd place: Piglet
33rd place: Eeyore`;

alert( str.match(/\w+$/gim) ); // Winnie,Piglet,Eeyore
```

没有 `/.../m` flag 的话，美元符 `$` 将会仅仅匹配整个文本的结尾，所以只有最后的一个单词会被找到。

### 7.6词边界：\b

[词边界：\b](https://zh.javascript.info/regexp-boundary)

词边界 `\b` 是一种检查，就像 `^` 和 `$` 一样。

当正则表达式引擎（实现搜索正则表达式的程序模块）遇到 `\b` 时，它会检查字符串中的位置是否是词边界。

有三种不同的位置可作为词边界：

- 在字符串开头，如果第一个字符是单词字符 `\w`。
- 在字符串中的两个字符之间，其中一个是单词字符 `\w`，另一个不是。
- 在字符串末尾，如果最后一个字符是单词字符 `\w`。

例如，可以在 `Hello, Java!` 中找到匹配 `\bJava\b` 的单词，其中 `Java` 是一个独立的单词，而在 `Hello, JavaScript!` 中则不行。

```javascript
alert( "Hello, Java!".match(/\bJava\b/) ); // Java
alert( "Hello, JavaScript!".match(/\bJava\b/) ); // null
```

`\b` 既可以用于单词，也可以用于数字。

例如，模式 `\b\d\d\b` 查找独立的两位数。换句话说，它查找的是两位数，其周围是与 `\w` 不同的字符，例如空格或标点符号（或文本开头/结尾）。

```javascript
alert( "1 23 456 78".match(/\b\d\d\b/g) ); // 23,78
alert( "12,34,56".match(/\b\d\d\b/g) ); // 12,34,56
```

### 7.7转义，特殊字符

[转义，特殊字符](https://zh.javascript.info/regexp-escaping)

#### 1.转义

使用\转义特殊字符

```js
alert( "Chapter 5.1".match(/\d\.\d/) ); // 5.1
```

```js
alert( "function g()".match(/g\(\)/) ); // "g()"
```

#### 2.用new RegExp()的坑

```js
let reg = new RegExp("\d\.\d");

alert( "Chapter 5.1".match(reg) ); // null
```

在字符串中的反斜杠表示转义或者类似 `\n` 这种只能在字符串中使用的特殊字符。这个引用会“消费”并且解释这些字符。

常见的比如文件地址：

```js
let str="E:\\VScode-code\\note"
```

所以需要双斜杠，因为引用会把 `\\` 变为 `\`：

```javascript
let regStr = "\\d\\.\\d";
alert(regStr); // \d\.\d (correct now)

let regexp = new RegExp(regStr);

alert( "Chapter 5.1".match(regexp) ); // 5.1
```

### 7.8集合和范围[...]

[集合和范围 [...\]](https://zh.javascript.info/regexp-character-sets-and-ranges)

<div style="color: red">在方括号 `[…]` 中的几个字符或者字符类意味着“搜索给定的字符中的任意一个”。</div>

#### 1.集合

比如说，`[eao]` 意味着查找在 3 个字符 `'a'`、`'e'` 或者 `‘o’ 中的任意一个。

这被叫做一个**集合**。集合可以在正则表达式中和其它常规字符一起使用。

```javascript
// 查找 [t 或者 m]，然后再匹配 “op”
alert( "Mop top".match(/[tm]op/gi) ); // "Mop", "top"
```

请注意尽管在集合中有多个字符，但它们在匹配中只会对应其中的一个。

所以下面的示例并不会匹配上：

```javascript
// 查找 “V”，然后匹配 [o 或者 i]，之后再匹配 “la”
alert( "Voila".match(/V[oi]la/) ); // null，并没有匹配上
```

#### 2.范围

方括号也可以包含**字符范围**。

比如说，`[a-z]` 会匹配从 `a` 到 `z` 范围内的字母，`[0-5]` 表示从 `0` 到 `5` 的数字。

在下面的示例中，我们会查询首先匹配 `"x"` 字符，再匹配两个数字或者位于 `A` 到 `F` 范围内的字符。

```javascript
alert( "Exception 0xAF".match(/x[0-9A-F][0-9A-F]/g) ); // xAF
```

`[0-9A-F]` 表示两个范围：它搜索一个字符，满足数字 `0` 到 `9` 或字母 `A` 到 `F`。

也可以添加字符类

**字符类是某些字符集的简写**

例如：

- **\d** —— 和 `[0-9]` 相同，
- **\w** —— 和 `[a-zA-Z0-9_]` 相同，
- **\s** —— 和 `[\t\n\v\f\r ]` 外加少量罕见的 unicode 空格字符相同。

#### 3.排除范围

除了普通的范围匹配，还有类似 `[^…]` 的“排除”范围匹配。

它们通过在匹配查询的开头添加插入符号 `^` 来表示，它会匹配所有**除了给定的字符**之外的任意字符。

比如说：

- `[^aeyo]` —— 匹配任何除了 `'a'`、`'e'`、`'y'` 或者 `'o'` 之外的字符。
- `[^0-9]` —— 匹配任何除了数字之外的字符，也可以使用 `\D` 来表示。
- `[^\s]` —— 匹配任何非空字符，也可以使用 `\S` 来表示。

下面的示例查询除了字母，数字和空格之外的任意字符：

```javascript
alert( "alice15@gmail.com".match(/[^\d\sA-Z]/gi) ); // @ and .
```

#### 4.[]中不用转义

<div style="color: red">有特例，在不是开头的位置表示一个插入符号（在开头位置该符号表示的是排除）`'^'`</div>

第二个特例：

<div style="color: red">破折号 `'-'` 在方括号中有特殊含义，但这个含义只有当它位于其它字符之间而不是开头或结尾时才会发生作用，所以我们并不需要转义它。</div>

案例：

`[-().^+]` 会查找 `-().^+` 的其中任意一个字符：

```javascript
// 并不需要转义
let reg = /[-().^+]/g;

alert( "1 + 2 - 3".match(reg) ); // 匹配 +，-
```

。。。但是如果你为了“以防万一”转义了它们，这也不会有任何问题：

```javascript
//转义其中的所有字符
let reg = /[\-\(\)\.\^\+]/g;

alert( "1 + 2 - 3".match(reg) ); // 仍能正常工作：+，-
```

#### 5.代理对记得使用u

```js
alert( '𝒳'.match(/[𝒳𝒴]/u) ); // 𝒳
```

### 7.9量词

[量词 `+,*,?` 和 `{n}`](https://zh.javascript.info/regexp-quantifiers)

#### 1.数量{n}

- 确切的位数：`{5}`

  `\d{5}` 表示 5 位的数字，如同 `\d\d\d\d\d`。接下来的例子将会查找一个五位数的数字：`alert( "I'm 12345 years old".match(/\d{5}/) ); //  "12345"`我们可以添加 `\b` 来排除更多位数的数字：`\b\d{5}\b`。

- 某个范围的位数：`{3,5}`

  我们可以将限制范围的数字放入括号中，来查找位数为 3 至 5 位的数字：`\d{3,5}``alert( "I'm not 12, but 1234 years old".match(/\d{3,5}/) ); // "1234"`我们可以省略上限。那么正则表达式 `\d{3,}` 就会查找位数大于或等于 3 的数字：`alert( "I'm not 12, but 345678 years old".match(/\d{3,}/) ); // "345678"`

对于字符串 `+7(903)-123-45-67` 来说，我们如果需要一个或多个连续的数字，就使用 `\d{1,}`：

```javascript
let str = "+7(903)-123-45-67";

let numbers = str.match(/\d{1,}/g);

alert(numbers); // 7,903,123,45,67
```

#### 2.缩写

大多数常用的量词都可以有缩写：

我觉得需要注意的地方是他们都是写在后面的

- `+`

  代表“一个或多个”，相当于 `{1,}`。例如，`\d+` 用来查找所有数字：`

  ```js
  let str = "+7(903)-123-45-67"; alert( str.match(/\d+/g) ); // 7,903,123,45,67
  ```

- `?`

  代表“零个或一个”，相当于 `{0,1}`。换句话说，它使得符号变得可选。例如，模式 `ou?r` 查找 `o`，后跟零个或一个 `u`，然后是 `r`。所以他能够在 `color` 中找到 `or`，以及在 `colour` 中找到 `our`：

  ```js
  let str = "Should I write color or colour?"; alert( str.match(/colou?r/g) ); // color, colour
  ```

- `*`

  代表着“零个或多个”，相当于 `{0,}`。也就是说，这个字符可以多次出现或不出现。接下来的例子将要寻找一个后跟任意数量的 0 的数字：

  ```js
  alert( "100 10 1".match(/\d0*/g) ); // 100, 10, 1
  ```

  将它与 `'+'`（一个或多个）作比较：

  ```js
  alert( "100 10 1".match(/\d0+/g) ); // 100, 10
  ```

  #### 习题：

  这个还是有很多坑的

  [针对 HTML 颜色的正则表达式](https://zh.javascript.info/regexp-quantifiers#zhen-dui-html-yan-se-de-zheng-ze-biao-da-shi)

### 7.10贪婪量词和惰性量词

[贪婪量词和惰性量词](https://zh.javascript.info/regexp-greedy-and-lazy)

这部分写的太好了！强烈推荐看原文

#### 1.贪婪  + 和*

**在贪婪模式下（默认情况下），量词都会尽可能地重复多次。**

#### 2.惰性 量词后再加一个？

**懒惰模式只能够通过带 `?` 的量词启用，量词都会尽可能少的触发。**

量词有两种工作模式：

- 贪婪模式

  默认情况下，正则表达式引擎会尝试尽可能多地重复量词。例如，`\d+` 检测所有可能的字符。当不可能检测更多（没有更多的字符或到达字符串末尾）时，然后它再匹配模式的剩余部分。如果没有匹配，则减少重复的次数（回溯），并再次尝试。

- 懒惰模式

  通过在量词后添加问号 `?` 来启用。在每次重复量词之前，引擎会尝试去匹配模式的剩余部分。

正如我们所见，懒惰模式并不是针对贪婪搜索的灵丹妙药。另一种方式是“微调”贪婪搜索，我们很快就会见到更多的例子。

经典案例：

```javascript
alert( "123 456".match(/\d+ \d+?/g) ); // 123 4
```

1. 模式 `\d+` 尝试匹配尽可能多的数字（贪婪模式），因此在它找到 `123` 时停止，因为下一个字符为空格 `' '`。

2. 匹配到一个空格。

3. 由于 `\d+?`。量词是出于懒惰模式的，所以它匹配一个数字 `4` 并且尝试去检测模式的剩余部分是否匹配。

   。。。但是在 `\d+?` 之后没有其它的匹配项了。

   懒惰模式不会在不必要的情况下重复任何事情。模式结束，所以我们找到了匹配项 `123 4`。

### 7.11捕获组（）

[捕获组](https://zh.javascript.info/regexp-groups)

模式的一部分可以用括号括起来 `(...)`。这称为“捕获组（capturing group）”。

这有两个影响：

1. 它允许将匹配的一部分作为结果数组中的单独项。（这个直接看案例就行）
2. 如果我们将量词放在括号后，则它将括号视为一个整体。

#### 验证第一点：

括号从左到右编号。正则引擎会记住它们各自匹配的内容，并允许在结果中获得它。

方法 `str.match(regexp)`，如果 `regexp` 没有 `g` 标志，将查找第一个匹配并将它作为一个数组返回：

1. 在索引 `0` 处：完全匹配。
2. 在索引 `1` 处：第一个括号的内容。
3. 在索引 `2` 处：第二个括号的内容。
4. …等等…

我们想找到 HTML 标记 `<.*?>` 并进行处理。这将很方便的把标签内容（尖括号内的内容）放在单独的变量中。

让我们将内部内容包装在括号中，像这样：`<(.*?)>`。

现在，我们能在结果数组中获取标签的整体 `<h1>` 及其内容 `h1`：

```javascript
let str = '<h1>Hello, world!</h1>';

let tag = str.match(/<(.*?)>/);

alert( tag[0] ); // <h1>
alert( tag[1] ); // h1
alert( tag[2] ); // undefined 因为只有一个括号
```

#### 验证第二点：

不带括号，模式 `go+` 表示 `g` 字符，其后 `o` 重复一次或多次。例如 `goooo` 或 `gooooooooo`。

括号将字符组合，所以 `(go)+` 匹配 `go`，`gogo`，`gogogo`等。

```javascript
alert( 'Gogogo now!'.match(/(go)+/i) ); // "Gogogo"
```



#### 1.嵌套组：



`result` 的零索引始终保持完全匹配。

然后按左括号将组从左到右编号。第一组返回为 `result[1]`。它包含了整个标签内容。

然后 `result[2]` 从第二个开始的括号中进入该组 `([a-z]+)` —— 标签名称，然后在 `result[3]` 标签中：`([^>]*)`。

字符串中每个组的内容：

![image-20220406010849955](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220406010849955.png)

```js
let str = '<span class="my">';

let regexp = /<(([a-z]+)\s*([^>]*))>/;
//这个是没有括号的版本，看起来有清楚些
// let regexp = /<[a-z]+\s*[^>]*>/;

let result = str.match(regexp);
alert(result[0]); // <span class="my">
alert(result[1]); // span class="my"
alert(result[2]); // span
alert(result[3]); // class="my"
```

#### 2.可选组：

让我们考虑正则 `a(z)?(c)?`。它寻找 `"a"` ，然后是可选的 `"z"`，然后是可选的 `"c"`。

如果我们在单个字母的字符串上运行 `a`，则结果为：

```javascript
let match = 'a'.match(/a(z)?(c)?/);

alert( match.length ); // 3
alert( match[0] ); // a（完全匹配）
alert( match[1] ); // undefined
alert( match[2] ); // undefined
```

数组的长度为 `3`，但所有组均为空。

这是字符串的一个更复杂的匹配 `ac`：

```javascript
let match = 'ac'.match(/a(z)?(c)?/)

alert( match.length ); // 3
alert( match[0] ); // ac（完全匹配）
alert( match[1] ); // undefined，因为 (z)? 没匹配项
alert( match[2] ); // c
```

数组长度是恒定的：`3`。但是对于组 `(z)?` 而言，什么都没有，所以结果是 `["ac", undefined, "c"]`。

#### 3.命名组

用数字记录组很困难。对于简单模式，它是可行的，但对于更复杂的模式，计算括号很不方便。我们有一个更好的选择：给括号起个名字。

这是通过在开始括号之后立即放置 `?<name>` 来完成的。

例如，让我们查找 “year-month-day” 格式的日期：

```js
//不带命名组的版本
let dateRegexp = /[0-9]{4}-[0-9]{2}-[0-9]{2}/;

let str = "2019-04-30";

let array= str.match(dateRegexp)

console.log(array);
```

![image-20220406012806594](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220406012806594.png)

```js
//带命名组的版本
let dateRegexp = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/;

let str = "2019-04-30";

let array= str.match(dateRegexp)

console.log(array);
```

![image-20220406013037244](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220406013037244.png)

如果有多个匹配对象，最好使用matchAll，而不是使用match+g的方法，因为后者只会返回匹配结果，不会返回捕获组。

我们看看区别：

使用matchAll：

注意一定要加标志g否则会报错

```js
let dateRegexp = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/g;

let str = "2019-04-30 2020-01-01";

//str.match(dateRegexp)返回的是一个由一个元素构成的数组
let array= Array.from(str.matchAll(dateRegexp)) 

console.log(array);
```

正确返回命名组

![image-20220406014819998](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220406014819998.png)

使用match：

```js
let dateRegexp = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/g;

let str = "2019-04-30 2020-01-01";

//str.match(dateRegexp)返回的是一个由一个元素构成的数组
let array= str.match(dateRegexp) 

console.log(array);
```

![image-20220406014924387](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220406014924387.png)

#### 4替换捕获组

方法 `str.replace(regexp, replacement)` 用 `replacement` 替换 `str` 中匹配 `regexp` 的所有捕获组。这使用 `$n` 来完成，其中 `n` 是组号。在替换字符串中，`$&` 表示匹配本身

例如，

```javascript
let str = "John Bull";
let regexp = /(\w+) (\w+)/;

alert( str.replace(regexp, '$2, $1') ); // Bull, John
```

对于命名括号，引用为 `$<name>`。

例如，让我们将日期格式从 “year-month-day” 更改为 “day.month.year”：

```javascript
let regexp = /(?<year>[0-9]{4})-(?<month>[0-9]{2})-(?<day>[0-9]{2})/g;

let str = "2019-10-30, 2020-01-01";

alert( str.replace(regexp, '$<day>.$<month>.$<year>') );
// 30.10.2019, 01.01.2020
```

#### 5.非捕获组

有时我们需要括号才能正确应用量词，但我们不希望它们的内容出现在结果中。

可以通过在开头添加 `?:` 来排除组。

例如，如果我们要查找 `(go)+`，但不希望括号内容（`go`）作为一个单独的数组项，则可以编写：`(?:go)+`。

在下面的示例中，我们仅将名称 `John` 作为匹配项的单独成员：

```javascript
let str = "Gogogo John!";

// ?: 从捕获组中排除 'go'
let regexp = /(?:go)+ (\w+)/i;

let result = str.match(regexp);

alert( result[0] ); // Gogogo John（完全匹配）
alert( result[1] ); // John
alert( result.length ); // 2（数组中没有更多项）
```

#### 习题：

除了最后一个，其他的都很简单，但看了答案后，最后一个也不难

[任务](https://zh.javascript.info/regexp-groups#tasks)

### 7.12模式中的反向引用：\N 和 \k

[模式中的反向引用：\N 和 \k](https://zh.javascript.info/regexp-backreferences)

#### 按编号反向引用\N:

```javascript
let str = `He said: "She's the one!".`;

let regexp = /(['"])(.*?)\1/g;

alert( str.match(regexp) ); // "She's the one!"
```

正则表达式引擎会找到第一个引号 `(['"])` 并记住其内容。那是第一个捕获组。

`\1` 在模式中进一步的含义是“查找与第一（捕获）分组相同的文本”，在我们的示例中为完全相同的引号。

与此类似，`\2` 表示第二（捕获）分组的内容，`\3` – 第三分组，依此类推。

#### 按命名反向引用\k<name>:

如果正则表达式中有很多括号对（注：捕获组），给它们起个名字方便引用。

要引用命名组，我们可以使用：`\k<name>`。

在下面的示例中引号组命名为 `?<quote>`，因此反向引用为 `\k<quote>`：

```javascript
let str = `He said: "She's the one!".`;

let regexp = /(?<quote>['"])(.*?)\k<quote>/g;

alert( str.match(regexp) ); // "She's the one!"
```

### 7.13选择OR

[选择（OR）|](https://zh.javascript.info/regexp-alternation)

就是或的意思

我们已知的一个相似符号 —— 方括号。就允许在许多字符中进行选择，例如 `gr[ae]y` 匹配 `gray` 或 `grey`。

选择符号并非在字符级别生效，而是在表达式级别。正则表达式 `A|B|C` 意思是命中 `A`、`B` 或 `C` 其一均可。

例如：

- `gr(a|e)y` 严格等同 `gr[ae]y`。
- `gra|ey` 匹配 “gra” or “ey”。

我们通常用圆括号把模式中的选择部分括起来，像这样 `before(XXX|YYY)after`。

#### 习题：

[任务](https://zh.javascript.info/regexp-alternation#tasks)

4道题都值得看看，1和4比较简单，但有坑；2,3比较难



### 7.14前瞻断言与后瞻断言,也叫环视

[前瞻断言与后瞻断言](https://zh.javascript.info/regexp-lookahead-lookbehind)

![image-20220407014728111](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220407014728111.png)

#### 1.前瞻断言：

语法为：`x(?=y)`，它表示“仅在后面是 `y` 的情况匹配 `x`”。

那么对于一个后面跟着 `€` 的整数金额，它的正则表达式应该为：`\d+(?=€)`。

```javascript
let str = "1 turkey costs 30€";

alert( str.match(/\d+(?=€)/) ); // 30 （正确地跳过了单个的数字 1）
```



让我们来看另一种情况：这次我们想要一个数量，它是一个不被 `€` 跟着的数值。

这里就要用到前瞻否定断言了。

语法为：`x(?!y)`，意思是 “查找 `x`, 但是仅在不被 `y` 跟随的情况下匹配成功”。

```javascript
let str = "2 turkeys cost 60€";

alert( str.match(/\d+(?!€)/) ); // 2（正确地跳过了价格）
```

#### 2.后瞻断言

语法为:

- 后瞻肯定断言：`(?<=y)x`, 匹配 `x`, 仅在前面是 `y` 的情况。
- 后瞻否定断言：`(?<!y)x`, 匹配 `x`, 仅在前面不是 `y` 的情况。

举个例子，让我们把价格换成美元。美元符号通常在数字之前，所以要查找 `$30` 我们将使用 `(?<=\$)\d+` —— 一个前面带 `$` 的数值：

```javascript
let str = "1 turkey costs $30";

alert( str.match(/(?<=\$)\d+/) ); // 30 （跳过了单个的数字 1）
```

另外，为了找到数量 —— 一个前面不带 `$` 的数字，我们可以使用否定后瞻断言：`(?<!\$)\d+`

```javascript
let str = "2 turkeys cost $60";

alert( str.match(/(?<!\$)\d+/) ); // 2 (跳过了价格)
```

#### 3.捕获组

在模式 `\d+(?!€)` 中，`€` 符号就不会出现在匹配结果中。

但是如果我们想要捕捉整个环视表达式或其中的一部分，那也是有可能的。只需要将其包裹在另加的括号中。

例如，这里货币符号 `(€|kr)` 和金额一起被捕获了：

```javascript
let str = "1 turkey costs 30€";
let reg = /\d+(?=(€|kr))/; // €|kr 两边有额外的括号

alert( str.match(reg) ); // 30, €
```

#### 习题：

[任务](https://zh.javascript.info/regexp-lookahead-lookbehind#tasks)

两个题的值得做，1题有坑；2题解法太巧妙了

### 7.15灾难性回溯

建议看原文

[灾难性回溯](https://zh.javascript.info/regexp-catastrophic-backtracking)
