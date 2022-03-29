# 说明：

1.此笔记记录我对电子书现代 JavaScript 教程学习情况。电子书中记录了很多新特性，不乏ES2020里面的新特性，且保持更新。很值得阅读。



2.我在每个三级标题下都标注了连接，方便查看原文。



3.有些难以理解的地方，我都写上了“我的见解”，方便自己以后看文档时快速理解，但详细说明还是看原文好。



4.多看传送门



5.传送门：[现代 JavaScript 教程](https://zh.javascript.info/)

[The Modern JavaScript Tutorial (github.com)](https://github.com/javascript-tutorial)

# 较难理解的地方

### 1.对象 — 原始值转换

https://zh.javascript.info/object-toprimitive

### 2.原始类型的方法

https://zh.javascript.info/primitives-methods



### 7.变量作用域，闭包 

 https://zh.javascript.info/closure

### 8.装饰器，fun.call,fun.apply 

https://zh.javascript.info/call-apply-decorators

看懂这个词法环境

### 9.函数对象，NFE

[函数对象，NFE (javascript.info)](https://zh.javascript.info/function-object)

尤其是这个https://zh.javascript.info/function-object#zi-ding-yi-shu-xing

还有习题https://zh.javascript.info/function-object#tasks

### 10.模块在浏览器中的特定功能

https://zh.javascript.info/modules-intro#liu-lan-qi-te-ding-gong-neng

### 11.导入导出

语法变体有点多

https://zh.javascript.info/import-export





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

https://zh.javascript.info/keys-values-entries#zhuan-huan-dui-xiang

### 5.10解构赋值

#### 1.交换两数：

```JS
let guest = "Jane";
let admin = "Pete";

// 让我们来交换变量的值：使得 guest = Pete，admin = Jane
[guest, admin] = [admin, guest];

alert(`${guest} ${admin}`); // Pete Jane（成功交换！）
```

还有一种用法是智能函数参数https://zh.javascript.info/destructuring-assignment#zhi-neng-han-shu-can-shu

#### 2.习题：

https://zh.javascript.info/destructuring-assignment#zui-gao-xin-zi

我的解法

```JS
let salaries = {
      "John": 100,
      "Pete": 300,
      "Mary": 250
    };
    console.log(opSalary(salaries)); 

    function opSalary(salaries){
      let array=Object.entries(salaries)
      for(let i = 0; i < array.length; i++){
        if(array[0][1]<=array[i][1]){
          [array[0],array[i]]=[array[i],array[0]]
        }
      }
      return array[0] 
    }
```

### 5.11.日期

#### 1.习题:

https://zh.javascript.info/date#mou-yue-de-zui-hou-yi-tian

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

#### 2.习题：

https://zh.javascript.info/date#jin-tian-guo-qu-le-duo-shao-miao

我的是答案的第二种解法

```JS
 getSecondsToday()
    function getSecondsToday(){
      let date=new Date()
     
      console.log(date.getHours()*3600+date.getMinutes()*60+date.getSeconds());
    }
```

#### 3.习题:

https://zh.javascript.info/date#ju-li-ming-tian-huan-you-duo-shao-miao

我的是答案的第一种解法

```JS
 getSecondsToTomorrow()
    function getSecondsToTomorrow(){
      let date=new Date()
      let date1=new Date(date.getFullYear(),date.getMonth(),date.getDate()+1)
      console.log((date1-date)/1000);
    }
```

#### 4.习题:

https://zh.javascript.info/date#ge-shi-hua-xiang-dui-ri-qi

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

## 6.函数进阶内容

### 6.2Rest 参数与 Spread 语法

#### 1.复制小技巧

用spread语法

https://zh.javascript.info/rest-parameters-spread#fu-zhi-arrayobject

### 6.3变量作用域，闭包

#### 1.习题:

https://zh.javascript.info/closure#if-nei-de-han-shu

https://zh.javascript.info/closure#bian-liang-ke-jian-ma

https://zh.javascript.info/closure#han-shu-da-jun

### 6.4var

https://zh.javascript.info/var#zong-jie

### 6.8setTimeOut,setInterval

习题：https://zh.javascript.info/settimeout-setinterval#mei-miao-shu-chu-yi-ci

掌握嵌套setTimeOut

习题:https://zh.javascript.info/settimeout-setinterval#settimeout-hui-xian-shi-shi-mo

## 7.对象属性配置

### 7.1属性标志和属性描述符

https://zh.javascript.info/property-descriptors

#### 1.属性标志

这三个默认如果简单创建对象都是true,而使用Object.defineProperty创建默认都是false

![image-20220327171828724](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327171828724.png)

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

这里json.stringfy第三个参数，是格式化后空格数量，无伤大雅。json.stringfy完整语法：

https://zh.javascript.info/json#pai-chu-he-zhuan-huan-replacer

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

这个部分也非常像java里面的get和set

https://zh.javascript.info/property-accessors

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

#### 兼容性：

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

这个概念很像Java里面的类的继承，设计理念应该是一样的，不要混淆了

### 8.1原型继承

https://zh.javascript.info/prototype-inheritance

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

#### 习题4：

https://zh.javascript.info/prototype-inheritance#wei-shi-mo-liang-zhi-cang-shu-du-bao-le

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



