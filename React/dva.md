# 路由

## 0.基础

可以说和react-router没有区别

## 1.切换 history 为 browserHistory

[知识地图 | DvaJS](https://dvajs.com/knowledgemap/#切换-history-为-browserhistory)

# Models

很多约定

## 处理同步Action:reducers

### 引入model

![image-20220508233106047](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220508233106047.png)

### 定义我们的Model:indexTest

键名namespace,state这些都是规定好的

```js
export default{
    namespace:'indexTest',
    state:{
        name:"小冯",
        age:21
    },
    reducers:{
        setName(state,payload){    
            console.log(payload,'payload')
            // 返回新的state,深拷贝
            return {...state,name:payload.data}
        }
    }
}
```

传递Action有规定，其他和redux无异

```jsx
import React from 'react';
import { connect } from 'dva';


const IndexPage = (props) => {
  console.log(props,'IndexPage  props')
  const handleClick=()=>{
    props.dispatch({
      type:"indexTest/setName",
      data:"猪猪侠"
    })
  }
  return (
    <div>
      Indexpage
      <div>{props.msg}</div>
      <div>{props.name}</div>
      <div>{props.age}</div>
      <button onClick={handleClick}>点击</button>
    </div>
  );
}

const mapStateToProps=state=>{
 
  return{
      msg:"我爱你",
      name:state.indexTest.name,
      age:state.indexTest.age
  }
}

export default connect(mapStateToProps)(IndexPage);


```

挂载时

![image-20220511170325322](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220511170325322.png)

点击按钮

![image-20220511170438407](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220511170438407.png)
