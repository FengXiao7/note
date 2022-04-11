# 说明：

资料：[React Hooks 核心原理与实战 (geekbang.org)](https://time.geekbang.org/column/intro/100079901)

[React Hooks Course - CodeSandbox](https://codesandbox.io/s/react-hooks-course-20vzg?file=/src/01/Counter.js)

老师没有视频，只有口述加文档，代码在线编辑，不过我下了下来，方便看代码。

md里面不好折叠代码，最好在IDE里面看。



# 基础篇：

## 1.认识React

<a name="userList">userList</a>

这个例子我觉得写的太好了，我以前确实不知道怎么优雅地写异步发送请求。

```jsx
import React from "react";

export default function UserList() {
  const [users, setUsers] = React.useState([]);
  const [loading, setLoading] = React.useState(false);
  const [error, setError] = React.useState(null);
  const fetchUsers = async () => {
    setLoading(true);
    try {
      const res = await fetch("https://reqres.in/api/users/");
      const json = await res.json();
      setUsers(json.data);
    } catch (err) {
      setError(err);
    }
    setLoading(false);
  };

  return (
    <div className="user-list">
      <button onClick={fetchUsers} disabled={loading}>
        {loading ? "Loading..." : "Show Users"}
      </button>
      {error && <div style={{ color: "red" }}>Failed: {String(error)}</div>}
      <br />
      <ul>
        {users.length > 0 &&
          users.map((user) => {
            return <li key={user.id}>{user.first_name}</li>;
          })}
      </ul>
    </div>
  );
}

```

### 两个问题：

1.函数中定义了回调函数 fetchUsers，但函数每次都是全部重新执行，那会不会重复定义很多次呢？

是的，这种写法会重复定义很多函数。不过为了避免这样的问题，React 提供了 useCallback 这样一个 Hook 来缓存回调函数。

2.如果另外一个组件可能也需要使用到 Users 这个数据，比如一个下拉框，那么是不是每次都要重复这个发起请求的逻辑呢？

对于异步请求逻辑的重用，这其实也意味着跨组件状态的重用，我会在第 7 讲利用 Redux 这样一个全局状态管理框架来实现异步逻辑的复用。

## 2.为啥需要Hooks？

### 逻辑复用：

#### 类式组件：

在 Class 组件的场景下，我们首先需要定义一个高阶组件，负责监听窗口大小变化，并将变化后的值作为 props 传给下一个组件。

```jsx

const withWindowSize = Component => {
    // 产生一个高阶组件 WrappedComponent，只包含监听窗口大小的逻辑
    class WrappedComponent extends React.PureComponent {
      constructor(props) {
        super(props);
        this.state = {
          size: this.getSize()
        };
      }
      componentDidMount() {
        window.addEventListener("resize", this.handleResize); 
      }
      componentWillUnmount() {
        window.removeEventListener("resize", this.handleResize);
      }
      getSize() {
        return window.innerWidth > 1000 ? "large" :"small";
      }
      handleResize = ()=> {
        const currentSize = this.getSize();
        this.setState({
          size: this.getSize()
        });
      }
      render() {
        // 将窗口大小传递给真正的业务逻辑组件
        return <Component size={this.state.size} />;
      }
    }
    return WrappedComponent;
  };
```

这样，在你的自定义组件中可以调用 withWindowSize 这样的函数来产生一个新组件，并自带 size 属性，例如：

```jsx

class MyComponent extends React.Component{
  render() {
    const { size } = this.props;
    if (size === "small") return <SmallComponent />;
    else return <LargeComponent />;
  }
}
// 使用 withWindowSize 产生高阶组件，用于产生 size 属性传递给真正的业务组件
export default withWindowSize(MyComponent); 
```

在这里，我们可以看到，为了传递一个外部的状态，我们不得不定义一个没有 UI 的外层组件，而这个组件只是为了封装一段可重用的逻辑。更为糟糕的是，高阶组件几乎是 Class 组件中实现代码逻辑复用的唯一方式，其缺点其实比较显然：

1.代码难理解，不直观，很多人甚至宁愿重复代码，也不愿用高阶组件；

2.会增加很多额外的组件节点。每一个高阶组件都会多一层节点，这就会给调试带来很大的负担。

#### 函数式组件+Hooks：

可以说，正因为这些缺点被抱怨已久，React 团队才终于提出了 Hooks 这样一个全新的方案。那么现在我们不妨看一下，同样的逻辑如果用 Hooks 和函数组件该如何实现。首先我们需要实现一个 Hooks：

```jsx

const getSize = () => {
  return window.innerWidth > 1000 ? "large" : "small";
}
const useWindowSize = () => {
  const [size, setSize] = useState(getSize());
  useEffect(() => {
  const handler = () => {
      setSize(getSize())
    };
    window.addEventListener('resize', handler);
    return () => {
      window.removeEventListener('resize', handler);
    };
  }, []);
  
  return size;
};
```

这样，我们在组件中使用窗口大小就会非常简单：

```jsx

const Demo = () => {
  const size = useWindowSize();
  if (size === "small") return <SmallComponent />;
  else return <LargeComponent />;
};
```

可以看到，窗口大小是一个外部的一个数据状态，我们通过 Hooks 的方式对其进行了封装，从而将其变成一个可绑定的数据源。这样当窗口大小发生变化时，使用这个 Hook 的组件就都会重新渲染。而且代码也更加简洁和直观，不会产生额外的组件节点。

### 关注分离：

除了逻辑复用之外，Hooks 能够带来的另外一大好处就是有助于关注分离，意思是说 Hooks 能够让针对同一个业务逻辑的代码尽可能聚合在一块儿。这是过去在 Class 组件中很难做到的。因为在 Class 组件中，你不得不把同一个业务逻辑的代码分散在类组件的不同生命周期的方法中。所以通过 Hooks 的方式，把业务逻辑清晰地隔离开，能够让代码更加容易理解和维护。

![image-20220409133207123](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220409133207123.png)

图的左侧是 Class 组件，右侧是函数组件结合 Hooks。蓝色和黄色代表不同的业务功能。可以看到，在 Class 组件中，代码是从技术角度组织在一起的，例如在 componentDidMount 中都去做一些初始化的事情。而在函数组件中，代码是从业务角度组织在一起的，相关代码能够出现在集中的地方，从而更容易理解和维护。

## 3.内置Hooks（1）

### useEffect：

```
useEffect(callback, dependencies)
```

第一个为要执行的函数 callback，第二个是可选的依赖项数组 dependencies。其中依赖项是可选的，如果不指定，那么 callback 就会在每次函数组件执行完后都执行；如果指定了，那么只有依赖项中的值发生变化的时候，它才会执行。



对应到 Class 组件，那么 useEffect 就涵盖了 ComponentDidMount、componentDidUpdate 和 componentWillUnmount 三个生命周期方法。不过如果你习惯了使用 Class 组件，那千万不要按照把 useEffect 对应到某个或者某几个生命周期的方法。你只要记住，**useEffect 是每次组件 render 完后判断依赖并执行就可以了**。

```jsx
// 举个例子，某个组件用于显示一篇 Blog 文章，那么这个组件会接收一个参数来表示 Blog 的 ID。
// 而当 ID 发生变化时，组件需要发起请求来获取文章内容并展示：
import React, { useState, useEffect } from "react";

function BlogView({ id }) {
  // 设置一个本地 state 用于保存 blog 内容
  const [blogContent, setBlogContent] = useState(null);

  useEffect(() => {
    // useEffect 的 callback 要避免直接的 async 函数，需要封装一下
    const doAsync = async () => {
      // 当 id 发生变化时，将当前内容清除以保持一致性
      setBlogContent(null);
      // 发起请求获取数据
      const res = await fetch(`/blog-content/${id}`);
      // 将获取的数据放入 state
      setBlogContent(await res.text());
    };
    doAsync();
  }, [id]); // 使用 id 作为依赖项，变化时则执行副作用

  // 如果没有 blogContent 则认为是在 loading 状态
  const isLoading = !blogContent;
  return <div>{isLoading ? "Loading..." : blogContent}</div>;
}
```

这样，我们就利用 useEffect 完成了一个简单的数据请求的需求。在这段代码中，我们把 ID 作为依赖项参数，这样就很自然地在 ID 发生变化时，利用 useEffect 执行副作用去获取数据。如果在之前的类组件中要完成类似的需求，我们就需要在 componentDidUpdate 这个方法里，自己去判断两次 ID 是否发生了变化。如果变了，才去发起请求。这样的话，逻辑上就不如 useEffect 来得直观。

#### 需注意：

React 会使用浅比较来对比依赖项是否发生了变化，所以要特别注意数组或者对象类型。如果你是每次创建一个新对象，即使和之前的值是等价的，也会被认为是依赖项发生了变化。这是一个刚开始使用 Hooks 时很容易导致 Bug 的地方。例如下面的代码：

```jsx

function Sample() {
  // 这里在每次组件执行时创建了一个新数组
  const todos = [{ text: 'Learn hooks.'}];
  useEffect(() => {
    console.log('Todos changed.');
  }, [todos]);
}
```

代码的原意可能是在 todos 变化的时候去产生一些副作用，但是这里的 todos 变量是在函数内创建的，实际上每次都产生了一个新数组。所以在作为依赖项的时候进行引用的比较，实际上被认为是发生了变化的。

这个我在PureComponent里面天禹老师也说过

#### 总结：

总结一下，useEffect 让我们能够在下面四种时机去执行一个回调函数产生副作用：

1.每次 render 后执行：不提供第二个依赖项参数。比如useEffect(() => {})。

2.仅第一次 render 后执行：提供一个空数组作为依赖项。比如useEffect(() => {}, [])。

3.第一次以及依赖项发生变化后执行：提供依赖项数组。比如useEffect(() => {}, [deps])。

4.组件 unmount 后执行：返回一个回调函数。比如useEffect() => { return () => {} }, [])。

### 补充-掌握 Hooks 的使用规则：

推荐看原文，全是干货。

[03｜内置 Hooks（1）：如何保存组件状态和使用生命周期？ (geekbang.org)](https://time.geekbang.org/column/article/379299)  最下面

## 4.内置Hooks（2）

### useCallback：缓存回调函数



每次创建新函数的方式会让接收事件处理函数的组件，需要重新渲染。

```jsx

function Counter() {
  const [count, setCount] = useState(0);
  const handleIncrement = () => setCount(count + 1);
  // ...
  return <button onClick={handleIncrement}>+</button>
}
```

比如这个例子中的 button 组件，接收了 handleIncrement ，并作为一个属性。如果每次都是一个新的，那么这个 React 就会认为这个组件的 props 发生了变化，从而必须重新渲染。因此，我们需要做到的是：只有当 count 发生变化时，我们才需要重新定一个回调函数。而这正是 useCallback 这个 Hook 的作用。它的 API 签名如下：

**简单来说就是返回一个函数，只有在依赖项发生变化的时候才会更新（返回一个新的函数）。**

```js
useCallback(fn, deps)
```

这里 fn 是定义的回调函数，deps 是依赖的变量数组。只有当某个依赖变量发生变化时，才会重新声明 fn 这个回调函数。那么对于上面的例子，我们可以把 handleIncrement 这个事件处理函数通过 useCallback 来进行性能的优化：

```jsx

import React, { useState, useCallback } from 'react';

function Counter() {
  const [count, setCount] = useState(0);
  const handleIncrement = useCallback(
    () => setCount(count + 1),
    [count], // 只有当 count 发生变化时，才会重新创建回调函数
  );
  // ...
  return <button onClick={handleIncrement}>+</button>
}

```

在这里，我们把 count 这个 state ，作为一个依赖传递给 useCallback。这样，只有 count 发生变化的时候，才需要重新创建一个回调函数，这样就保证了组件不会创建重复的回调函数。而接收这个回调函数作为属性的组件，也不会频繁地需要重新渲染。

### useMemo：缓存计算的结果



举个例子，对于一个显示用户信息的列表，现在需要对用户名进行搜索，且 UI 上需要根据搜索关键字显示过滤后的用户，那么这样一个功能需要有两个状态：

1.用户列表数据本身：来自某个请求。

2.搜索关键字：用户在搜索框输入的数据。

无论是两个数据中的哪一个发生变化，都需要过滤用户列表以获得需要展示的数据。那么如果不使用 useMemo 的话，就需要用这样的代码实现：

```jsx

import React, { useState, useEffect } from "react";

export default function SearchUserList() {
  //筛选users列表
  const [users, setUsers] = useState(null);
  //搜索栏关键字
  const [searchKey, setSearchKey] = useState("");

  useEffect(()=>{
    // 组件首次加载时发请求获取用户数据
      const doFetch =async ()=>{
        const res = await fetch("https://reqres.in/api/users/")
        setUsers(await res.json())
      };
      doFetch();
  },[])

  let userListShow = null
// 无论组件为何刷新，这里一定会对数组做一次过滤的操作
  if(users){
    userListShow=users.data.filter(user=>{
      return user.first_name.includes(searchKey)
    })
  }

  return (
    <div>
      <input
        type="text"
        value={searchKey}
        onChange={ event=>setSearchKey(event.target.value)}
      />
      <ul>
        {
          userListShow && userListShow.length>0 &&
          userListShow.map(user=>{
            return <li key={user.id}>{user.first_name}</li>
          })
        }
      </ul>
    </div>
  );
}
```

在这个例子中，无论组件为何要进行一次重新渲染，实际上都需要进行一次过滤的操作。但其实你只需要在 users 或者 searchKey 这两个状态中的某一个发生变化时，重新计算获得需要展示的数据就行了。那么，这个时候，我们就可以用 useMemo 这个 Hook 来实现这个逻辑，缓存计算的结果：

**简单来说就是传递一个创建函数和依赖项，创建函数会需要返回一个值，只有在依赖项发生改变的时候，才会重新调用此函数，返回一个新的值。**

```jsx

//...
// 使用 userMemo 缓存计算的结果
const usersToShow = useMemo(() => {
    if (!users) return null;
    return users.data.filter((user) => {
      return user.first_name.includes(searchKey));
    }
  }, [users, searchKey]);
//...
```



这个时候，如果我们结合 useMemo 和 useCallback 这两个 Hooks 一起看，会发现一个有趣的特性，那就是 useCallback 的功能其实是可以用 useMemo 来实现的。比如下面的代码就是利用 useMemo 实现了 useCallback 的功能：

```JSX

 const myEventHandler = useMemo(() => {
   // 返回一个函数作为缓存结果
   return () => {
     // 在这里进行事件处理
   }
 }, [dep1, dep2]);
```

理解了这一点，相信你一下子会对这两个 Hooks 的机制有更进一步的认识，也就不用死记硬背两个 API 都是干嘛的了，因为从本质上来说，它们只是做了同一件事情：**建立了一个绑定某个结果到依赖数据的关系。只有当依赖变了，这个结果才需要被重新得到。**对于useCallback，这个结果是个函数，对于useMemo这个结果可以是任意值，当然也包括函数。

### useRef：在多次渲染之间共享数据

```jsx
const myRefContainer = useRef(initialValue);
```

我们可以把 useRef 看作是在函数组件之外创建的一个容器空间。在这个容器上，我们可以通过唯一的 current 属性设置一个值，从而在函数组件的多次渲染之间共享这个值。

```jsx
import React, { useState, useCallback, useRef } from "react";

export default function Timer() {
  // 定义 time state 用于保存计时的累积时间
  const [time, setTime] = useState(0);

  // 定义 timer 这样一个容器用于在跨组件渲染之间保存一个变量
  const timer = useRef(null);

  // 开始计时的事件处理函数
  const handleStart = useCallback(() => {
    // 使用 current 属性设置 ref 的值
    timer.current = window.setInterval(() => {
      setTime((time) => time + 1);
    }, 100);
  }, []);

  // 暂停计时的事件处理函数
  const handlePause = useCallback(() => {
    // 使用 clearInterval 来停止计时
    window.clearInterval(timer.current);
    timer.current = null;
  }, []);

  return (
    <div>
      {time / 10} seconds.
      <br />
      <button onClick={handleStart}>Start</button>
      <button onClick={handlePause}>Pause</button>
    </div>
  );
}

```

**还有一个作用就是保存某个DOM节点的引用，我在基础篇已经写过案例了**

useRef的特性： 1. 存储跨渲染的数据 2. 保存某个DOM节点的引用

### useContext：定义全局状态

```jsx
import React, { useState, useContext, useCallback } from "react";

const themes = {
  light: {
    foreground: "#000000",
    background: "#eeeeee",
  },
  dark: {
    foreground: "#ffffff",
    background: "#222222",
  },
};

// 创建一个 Theme 的 Context
const ThemeContext = React.createContext(themes.light);

// 在 Toolbar 组件中使用一个会使用 Theme 的 Button
function Toolbar() {
  return (
    <div>
      <ThemedButton />
    </div>
  );
}

// 在 Theme Button 中使用 useContext 来获取当前的主题
function ThemedButton() {
  const theme = useContext(ThemeContext);
  return (
    <button
      style={{
        background: theme.background,
        color: theme.foreground,
      }}
    >
      I am styled by theme context!
    </button>
  );
}

// 在 Toolbar 组件中使用一个会使用 Theme 的 Button
export default function () {
  // 使用 state 来保存 theme 从而可以动态修改
  const [theme, setTheme] = useState("light");

  // 切换 theme 的回调函数
  const toggleTheme = useCallback(() => {
    setTheme((theme) => (theme === "light" ? "dark" : "light"));
  }, []);
    //useCallBack依赖是空数组没有意义，相当于每次都创建一个新的函数

  return (
    // 使用 theme state 作为当前 Context
    <ThemeContext.Provider value={themes[theme]}>
      <button onClick={toggleTheme}>Toggle Theme</button>
      <br />
      <br />
      <Toolbar />
    </ThemeContext.Provider>
  );
}

```

我发现不用useContext钩子也可以用Consumer，生成新节点来实现同样的功能

官网：[Context – React (reactjs.org)](https://zh-hans.reactjs.org/docs/context.html#contextconsumer)

改变下孙子组件的代码

```jsx
function ThemedButton() {
    return (
        <ThemeContext.Consumer>
            {
            value => 
                <button
                    style={{
                        background: value.background,
                        color: value.foreground,
                    }}
                >
                    I am styled by theme context!
                </button>
            }
        </ThemeContext.Consumer>
    );
}
```

## 5.理解函数式组件生命周期

### 1.构造函数

构造函数的本质，其实就是：在所以其它代码执行之前的一次性初始化工作。在函数组件中，因为没有生命周期的机制，那么转换一下思路，其实我们要实现的是：一次性的代码执行。

虽然没有直接的机制可以做到这一点，但是利用 useRef 这个 Hook，我们可以实现一个 useSingleton 这样的一次性执行某段代码的自定义 Hook，代码如下：

```jsx

import { useRef } from 'react';

// 创建一个自定义 Hook 用于执行一次性代码
function useSingleton(callback) {
  // 用一个 called ref 标记 callback 是否执行过
  const called = useRef(false);
  // 如果已经执行过，则直接返回
  if (called.current) return;
  // 第一次调用时直接执行
  callBack();
  // 设置标记为已执行过
  called.current = true;
}
```

从而在一个函数组件中，可以调用这个自定义 Hook 来执行一些一次性的初始化逻辑：

```jsx

import useSingleton from './useSingleton';

const MyComp = () => {
  // 使用自定义 Hook
  useSingleton(() => {
    console.log('这段代码只执行一次');
  });

  return (
    <div>My Component</div>
  );
};
```

### 2.三个生命周期函数

```jsx

useEffect(() => {
  // componentDidMount + componentDidUpdate
  console.log('这里基本等价于 componentDidMount + componentDidUpdate');
  return () => {
    // componentWillUnmount
    console.log('这里基本等价于 componentWillUnmount');
  }
}, [deps])
```

**为什么说基本等价于？**

#### 原因1：

一方面，useEffect(callback) 这个 Hook 接收的 callback，只有在依赖项变化时才被执行。而传统componentDidUpdate 则一定会执行。这样来看，Hook 的机制其实更具有语义化，因为过去在 componentDidUpdate 中，我们通常都需要手动判断某个状态是否发生变化，然后再执行特定的逻辑。

#### 原因2：

另一方面，callback 返回的函数（一般用于清理工作）在下一次依赖项发生变化以及组件销毁之前执行，而传统的 componentWillUnmount 只在组件销毁时才会执行。

第二点详细说明：

案例：假设当文章 id 发生变化时，我们不仅需要获取文章，同时还要监听某个事件，这样在有新的评论时获得通知，就能显示新的评论了。这时候的代码结构如下：

```jsx

import React, { useEffect } from 'react';
import comments from './comments';

function BlogView({ id }) {
  const handleCommentsChange = useCallback(() => {
    // 处理评论变化的通知
  }, []);
  useEffect(() => {
    // 获取博客内容
    fetchBlog(id);
    // 监听指定 id 的博客文章的评论变化通知
    const listener = comments.addListener(id, handleCommentsChange);
    
    return () => {
      // 当 id 发生变化时，移除之前的监听
      comments.removeListener(listener);
    };
  }, [id, handleCommentsChange])
}
```

**useEffect 接收的返回值是一个回调函数，这个回调函数不只是会在组件销毁时执行，而且是每次 Effect 重新执行之前都会执行，用于清理上一次 Effect 的执行结果。**

### 3.其他生命周期函数

但是 Class 组件中还有其它一些比较少用的方法，比如 getSnapshotBeforeUpdate, componentDidCatch, getDerivedStateFromError。比较遗憾的是目前 Hooks 还没法实现这些功能。因此如果必须用到，你的组件仍然需要用类组件去实现。

### 4.重构类式组件？

说了这么多，你可能会觉得写 React 应用就一定非 Hooks 不可了，其实也并非绝对。比如说很多时候，你面临的可能并不是开始一个全新的项目，而是参与到一个已有的项目中。那么就很可能会遇到这样一个问题：对于已有项目中的 Class 组件，是否要重构到函数组件和 Hooks 呢？

答案其实很明确：完全没必要。

在 React 中，Class 组件和函数组件是完全可以共存的。对于新的功能，我会更推荐使用函数组件。而对于已有的功能，则维持现状就可以。除非要进行大的功能改变，可以顺便把相关的类组件进行重构，否则是没有必要进行迁移的。

因为终究来说，能正确工作的代码就是好代码。React 组件的两种写法本身就可以很好地一起工作了：类组件和函数组件可以互相引用；Hooks 很容易就能转换成高阶组件，并供类组件使用。

总结来说，我们完全没必要为了迁移而迁移。

## 6.自定义Hooks ：四个典型的使用场景

### 1.自定义hooks

#### 特点1：

名字一定是以 use 开头的函数，这样 React 才能够知道这个函数是一个 Hook；

#### 特点2：

函数内部一定调用了其它的 Hooks，可以是内置的 Hooks，也可以是其它自定义 Hooks。这样才能够让组件刷新，或者去产生副作用。

#### 案例：

自定义的useCounter 

```jsx
import { useState, useCallback }from 'react';
 
function useCounter() {
  // 定义 count 这个 state 用于保存当前数值
  const [count, setCount] = useState(0);
  // 实现加 1 的操作
  const increment = useCallback(() => setCount(count + 1), [count]);
  // 实现减 1 的操作
  const decrement = useCallback(() => setCount(count - 1), [count]);
  // 重置计数器
  const reset = useCallback(() => setCount(0), []);
  
  // 将业务逻辑的操作 export 出去供调用者使用
  return { count, increment, decrement, reset };
}

export default useCounter
```

使用

```jsx

import React from 'react';
import useCounter from './test';
function Counter() {
  // 调用自定义 Hook
  const { count, increment, decrement, reset } = useCounter();

  // 渲染 UI
  return (
    <div>
      <button onClick={decrement}> - </button>
      <p>{count}</p>
      <button onClick={increment}> + </button>
      <button onClick={reset}> reset </button>
    </div>
  );
}
export default Counter
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/120.gif" style="zoom: 100%"></img>

我们把原来在函数组件中实现的逻辑提取了出来，成为一个单独的 Hook，**一方面能让这个逻辑得到重用，另外一方面也能让代码更加语义化，并且易于理解和维护。**

### 2.封装通用逻辑：useAsync

比如说，在日常 UI 的开发中，有一个最常见的需求：**发起异步请求获取数据并显示在界面上**。在这个过程中，我们不仅要关心请求正确返回时，UI 会如何展现数据；还需要处理请求出错，以及关注 Loading 状态在 UI 上如何显示

#### 案例：

可以重新看下在第 1 讲中看到的异步请求的例子，从 Server 端获取用户列表，并显示在界面上：

<a href="#userList">Link</a>

1.创建 data，loading，error 这 3 个 state；

2.请求发出后，设置 loading state 为 true；

3.请求成功后，将返回的数据放到某个 state 中，并将 loading state 设为 false；

4.请求失败后，设置 error state 为 true，并将 loading state 设为 false。

#### useAsync：

<a name="useAsync">useAsync</a>

把逻辑抽取出来

```jsx

import { useState,useCallback } from 'react';

const useAsync = (asyncFunction) => {
  // 设置三个异步逻辑相关的 state
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);
  // 定义一个 callback 用于执行异步逻辑
  const execute = useCallback(() => {
    // 请求开始时，设置 loading 为 true，清除已有数据和 error 状态
    setLoading(true);
    setData(null);
    setError(null);
    return asyncFunction()
      .then((response) => {
        // 请求成功时，将数据写进 state，设置 loading 为 false
        setData(response);
        setLoading(false);
      })
      .catch((error) => {
        // 请求失败时，设置 loading 为 false，并设置错误状态
        setError(error);
        setLoading(false);
      });
  }, [asyncFunction]);

  return { execute, loading, data, error };
};
export default useAsync
```

#### 使用：

```jsx

import React from "react";
import useAsync from './test';

function UserList() {
  // 通过 useAsync 这个函数，只需要提供异步逻辑的实现
  const {
    execute: fetchUsers,
    data: users,
    loading,
    error,
  } = useAsync(async () => {
    const res = await fetch("https://reqres.in/api/users/");
    const json = await res.json();
    return json.data;
  });

  return (
    // 根据状态渲染 UI...
    <div>
      <button onClick={fetchUsers} disabled={loading}>
        {loading ? "Loading..." : "Show Users"}
      </button>
      {error && <div style={{ color: "red" }}>Failed: {String(error)}</div>}
      <br />
      <ul>
        {users&&
          users.map((user) => {
            return <li key={user.id}>{user.first_name}</li>;
          })}
      </ul>
    </div>

    );
}
export default UserList
```

通过这个例子可以看到，**我们利用了 Hooks 能够管理 React 组件状态的能力，将一个组件中的某一部分状态独立出来，从而实现了通用逻辑的重用。**

### 3.监听浏览器状态：useScroll

**可以让 React 的组件绑定在任何可能的数据源上。这样当数据源发生变化时，组件能够自动刷新。**

把这个好处对应到滚动条位置这个场景就是：组件需要绑定到当前滚动条的位置数据上。虽然这个逻辑在函数组件中可以直接实现，但是把这个逻辑实现为一个独立的 Hooks，既可以达到逻辑重用，在语义上也更加清晰。这个和上面的 useAsync 的作用是非常类似的。

#### useScroll:

```JSX
import { useState, useEffect } from 'react';

// 获取横向，纵向滚动条位置
const getPosition = () => {
  return {
    x: document.documentElement.scrollLeft,
    y: document.documentElement.scrollTop,
  };
};
const useScroll = () => {
  // 定一个 position 这个 state 保存滚动条位置
  const [position, setPosition] = useState(getPosition());
  useEffect(() => {
    const handler = () => {
      setPosition(getPosition());
    };
    // 监听 scroll 事件，更新滚动条位置
    document.addEventListener("scroll", handler);
    return () => {
      // 组件销毁时，取消事件监听
      document.removeEventListener("scroll", handler);
    };
  }, []);
  return position;
};
export default useScroll
```

有了这个 Hook，你就可以非常方便地监听当前浏览器窗口的滚动条位置了。比如下面的代码就展示了“返回顶部”这样一个功能的实现：

#### 使用：

```jsx

import React, { useCallback } from 'react';
import useScroll from './test';

function ScrollTop() {
  const { x,y } = useScroll();
  const goTop = useCallback(() => {
    document.documentElement.scrollTop = 0;
  }, []);

  const style = {
    position: "fixed",
    right: "10px",
    bottom: "10px",
  };
  // 当滚动条位置纵向超过 300 时，显示返回顶部按钮
  if (y > 300) {
    return (
      <button onClick={goTop} style={style}>
        Back to Top
      </button>
    );
  }
  return(
    <div style={{position:'fixed',left:'50%',top:'50%'}}>
      <span>x:{x},y:{y}</span>
    </div>
  );
}
export default ScrollTop
```

<img src="https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/121.gif" style="zoom: 100%"></img>

当然，除了窗口大小、滚动条位置这些状态，还有其它一些数据也可以这样操作，比如 cookies，localStorage, URL，等等。你都可以通过这样的方法来实现。

### 4.拆分复杂组件

怎么才能让函数组件不会太过冗长呢？

做法很简单，就是**尽量将相关的逻辑做成独立的 Hooks，然后在函数组中使用这些 Hooks，通过参数传递和返回值让 Hooks 之间完成交互。**

#### 例子：

```jsx

function BlogList() {
  // 获取文章列表...
  // 获取分类列表...
  // 组合文章数据和分类数据...
  // 根据选择的分类过滤文章...
  
  // 渲染 UI ...
}
```

很多同学在写函数组件时没有意识到 Hooks 就是普通的函数，所以通常不会这么去做隔离，而是习惯于一路写下来，这就会造成某个函数组件特别长。还是老生常谈的那句话，**改变这个状况的关键仍然在于开发思路的转变。**我们要真正**把 Hooks 就看成普通的函数，能隔离的尽量去做隔离**，从而让代码更加模块化，更易于理解和维护。

那么针对这样一个功能，我们甚至可以将其拆分成 4 个 Hooks，每一个 Hook 都尽量小，代码如下：

这里的useAsync就是之前写的那个

<a href="#useAsync">Link</a>

建议放在IDE里面看，方便折叠代码。这里请求地址是假的

```jsx

import React, { useEffect, useCallback, useMemo, useState } from "react";
import { Select, Table } from "antd";
import _ from "lodash";
import useAsync from "./useAsync";

const endpoint = "https://myserver.com/api/";
const useArticles = () => {
  // 使用上面创建的 useAsync 获取文章列表
  const { execute, data, loading, error } = useAsync(
    useCallback(async () => {
      const res = await fetch(`${endpoint}/posts`);
      return await res.json();
    }, []),
  );
  // 执行异步调用
  useEffect(() => execute(), [execute]);
  // 返回语义化的数据结构
  return {
    articles: data,
    articlesLoading: loading,
    articlesError: error,
  };
};
const useCategories = () => {
  // 使用上面创建的 useAsync 获取分类列表
  const { execute, data, loading, error } = useAsync(
    useCallback(async () => {
      const res = await fetch(`${endpoint}/categories`);
      return await res.json();
    }, []),
  );
  // 执行异步调用
  useEffect(() => execute(), [execute]);

  // 返回语义化的数据结构
  return {
    categories: data,
    categoriesLoading: loading,
    categoriesError: error,
  };
};
const useCombinedArticles = (articles, categories) => {
  // 将文章数据和分类数据组合到一起
  return useMemo(() => {
    // 如果没有文章或者分类数据则返回 null
    if (!articles || !categories) return null;
    return articles.map((article) => {
      return {
        ...article,
        category: categories.find(
          (c) => String(c.id) === String(article.categoryId),
        ),
      };
    });
  }, [articles, categories]);
};
const useFilteredArticles = (articles, selectedCategory) => {
  // 实现按照分类过滤
  return useMemo(() => {
    if (!articles) return null;
    if (!selectedCategory) return articles;
    return articles.filter((article) => {
      console.log("filter: ", article.categoryId, selectedCategory);
      return String(article?.category?.name) === String(selectedCategory);
    });
  }, [articles, selectedCategory]);
};

const columns = [
  { dataIndex: "title", title: "Title" },
  { dataIndex: ["category", "name"], title: "Category" },
];

export default function BlogList() {
  const [selectedCategory, setSelectedCategory] = useState(null);
  // 获取文章列表
  const { articles, articlesError } = useArticles();
  // 获取分类列表
  const { categories, categoriesError } = useCategories();
  // 组合数据
  const combined = useCombinedArticles(articles, categories);
  // 实现过滤
  const result = useFilteredArticles(combined, selectedCategory);

  // 分类下拉框选项用于过滤
  const options = useMemo(() => {
    const arr = _.uniqBy(categories, (c) => c.name).map((c) => ({
      value: c.name,
      label: c.name,
    }));
    arr.unshift({ value: null, label: "All" });
    return arr;
  }, [categories]);

  // 如果出错，简单返回 Failed
  if (articlesError || categoriesError) return "Failed";

  // 如果没有结果，说明正在加载
  if (!result) return "Loading...";

  return (
    <div>
      <Select
        value={selectedCategory}
        onChange={(value) => setSelectedCategory(value)}
        options={options}
        style={{ width: "200px" }}
        placeholder="Select a category"
      />
      <Table dataSource={result} columns={columns} />
    </div>
  );
}
```

