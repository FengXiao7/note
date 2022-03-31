# 说明：

1.此笔记记录我对电子书现代 JavaScript 教程学习情况。电子书中记录了很多新特性，不乏ES2020里面的新特性，且保持更新，很值得深入阅读。



2.我在每个三级标题下都标注了连接，方便查看原文。



3.有些难以理解的地方，我都写的有自己的理解，实在不行还有传送门，但详细说明还是看原文好。



4.传送门：

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

文中举的装饰器的例子难以理解

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



# 值的常看的地方：

## 1.函数表达式

[函数表达式 (javascript.info)](https://zh.javascript.info/function-expressions)

## 2.垃圾回收

https://zh.javascript.info/garbage-collection

## 3.空值合并运算符  ??

（ES2020）

https://zh.javascript.info/nullish-coalescing-operator

## 4.可选链 ?.

(ES2020)

[可选链 "?."](https://zh.javascript.info/optional-chaining)

## 5.Symbol 类型

（ES2015）(ES6)

[Symbol 类型](https://zh.javascript.info/symbol)

## 6.reduce方法

https://zh.javascript.info/array-methods#reducereduceright

传送门：[25个你不得不知道的数组reduce高级用法 - 掘金 (juejin.cn)](https://juejin.cn/post/6844904063729926152)

[Reduce 和 Transduce 的含义 - 阮一峰的网络日志 (ruanyifeng.com)](https://www.ruanyifeng.com/blog/2017/03/reduce_transduce.html)

## 7.Array.from

[Array.from](https://zh.javascript.info/iterable#arrayfrom)

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

这个默认值是一个对象，一个只有属性 `constructor` 的对象，属性 `constructor` 指向函数自身

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

这两个题回了，已经通了。

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

和java很像不要记串了

### 1.Class基本语法

[Class 基本语法](https://zh.javascript.info/class)

## 11.Promise,async/await

### 11.2Promise:

#### 1.Promise构造器

![image-20220324143206747](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324143206747.png)

![image-20220324143350895](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324143350895.png)



#### 2.then：

![image-20220324143430643](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324143430643.png)

#### 3.catch：

![image-20220324143552954](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220324143552954.png)



## 13.模块

### 13.1模块简介

https://zh.javascript.info/modules-intro

#### 1.import和export

![image-20220327133652150](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327133652150.png)

由于模块支持特殊的关键字和功能，因此我们必须通过使用 `<script type="module">` 特性（attribute）来告诉浏览器，此脚本应该被当作模块（module）来对待。

#### 2.模块只通过 HTTP(s) 工作，而非本地

#### 3.模块作用域

每个模块都有自己的顶级作用域（top-level scope）。换句话说，一个模块中的顶级作用域变量和函数在其他脚本中是不可见的。

#### 4.模块代码仅在第一次导入时被解析

https://zh.javascript.info/modules-intro#mo-kuai-dai-ma-jin-zai-di-yi-ci-dao-ru-shi-bei-jie-xi

我们可以利用这一点配置对象

#### 5.在一个模块中，“this” 是 undefined

```html
<script>
  alert(this); // window
</script>

<script type="module">
  alert(this); // undefined
</script>
```

### 13.2导出和导入

#### 1.Export default

https://zh.javascript.info/import-export#exportdefault

![image-20220327140555462](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327140555462.png)

### 13.3动态导入

https://zh.javascript.info/modules-dynamic-imports

这部分在vue路由懒加载中有使用到，webpack代码分割时也有使用到

















# 浏览器：文档，事件，接口

## Document

### 1.3遍历DOM

对于所有节点：`parentNode`，`childNodes`，`firstChild`，`lastChild`，`previousSibling`，`nextSibling`。

仅对于元素节点：`parentElement`，`children`，`firstElementChild`，`lastElementChild`，`previousElementSibling`，`nextElementSibling`。

也就是说有“Element”就是操作元素节点的方法

对于很多任务来说，我们并不想要文本节点或注释节点。我们希望操纵的是代表标签的和形成页面结构的元素节点。

#### 

#### 1.习题：

https://zh.javascript.info/dom-navigation#dom-zi-jie-dian

#### 2.习题：

https://zh.javascript.info/dom-navigation#xiong-di-jie-dian-wen-ti

#### 3.习题：

https://zh.javascript.info/dom-navigation#xuan-ze-suo-you-dui-jiao-dan-yuan-ge

### 1.4搜索：getElement*，querySelector*

#### 1.习题:

https://zh.javascript.info/searching-elements-dom#sou-suo-yuan-su



