# 较难理解的地方

### 1.对象 — 原始值转换

https://zh.javascript.info/object-toprimitive

### 2.原始类型的方法

https://zh.javascript.info/primitives-methods

### 3.数组中的reduce方法

https://zh.javascript.info/array-methods#reducereduceright

### 4.数组的Array.from方法

https://zh.javascript.info/iterable#arrayfrom

### 5.Symbol类型

https://zh.javascript.info/symbol#symbol

### 6.可迭代对象

[Iterable object（可迭代对象） (javascript.info)](https://zh.javascript.info/iterable)

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



# JavaScript 编程语言

## 2.JavaScript基础知识

### 2.6交互

#### 1.prompt

https://zh.javascript.info/alert-prompt-confirm#prompt

![image-20220327204219358](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327204219358.png)

访问者可以在提示输入栏中输入一些内容，然后按“确定”键。然后我们在 `result` 中获取该文本。或者他们可以按取消键或按 Esc 键取消输入，然后我们得到 `null` 作为 `result`。

`prompt` 将返回用户在 `input` 框内输入的文本，如果用户取消了输入，则返回 `null`。

#### 2.confirm

![image-20220327204320763](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220327204320763.png)

## 4.Object（对象）：基础知识

### 4.1对象

#### 1.方括号

和‘.’一个意思

https://zh.javascript.info/object#fang-kuo-hao

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

属性命名没有限制。属性名可以是任何字符串或者 symbol（一种特殊的标志符类型，将在后面介绍）。

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

### 4.5构造器和操作符"new"

[构造器和操作符 "new" (javascript.info)](https://zh.javascript.info/constructor-new)

## 5.数据类型：

### 5.2数字类型：

#### 1.进制转换

[https://zh.javascript.info/number#tostringbase  10进制转其他进制

https://zh.javascript.info/number#parseint-he-parsefloat  其他进制转10进制

#### 2.四舍五入

https://zh.javascript.info/number#she-ru 

https://zh.javascript.info/number#wei-shi-mo-6-35tofixed-1-6-3   有坑

#### 3.数字精度问题

https://zh.javascript.info/number#bu-jing-que-de-ji-suan

https://zh.javascript.info/number#yi-ge-ou-fa-de-wu-xian-xun-huan  有坑

#### 4.验证字符串值是否为常规数字

https://zh.javascript.info/number#ce-shi-isfinite-he-isnan  可以用isFinite办到

#### 5.从字符串中“读取”数字，直到无法读取为止

https://zh.javascript.info/number#parseint-he-parsefloat

### 5.3.字符串

[字符串 (javascript.info)](https://zh.javascript.info/string)

### 5.4数组

[数组 (javascript.info)](https://zh.javascript.info/array)

把这个例子看懂https://zh.javascript.info/array-methods#cong-shu-zu-chuang-jian-jian-zhi-dui-xiang

### 5.7Map和set

#### 1.普通对象转换为Map

https://zh.javascript.info/map-set#objectentries-cong-dui-xiang-chuang-jian-map

#### 2.Map转换为普通对象

https://zh.javascript.info/map-set#objectfromentries-cong-map-chuang-jian-dui-xiang

#### 3.熟悉这个例子配合Array.from使用

https://zh.javascript.info/map-set#guo-lv-shu-zu-zhong-de-wei-yi-yuan-su

#### 4.做题

https://zh.javascript.info/map-set#guo-lv-zi-mi-anagrams

我的做法，有瑕疵，不能保留原始数据不满足要求。

正确做法，用map

```JS
let arr = ["nap", "teachers", "cheaters", "PAN", "ear", "era", "hectares"];

    function aclean(arr){
      //用map改造原数组
      let array=arr.map((item)=>item.toLowerCase().split('').sort().join(''))
      return Array.from(new Set(array))
    }
    alert(aclean(arr));
```

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



