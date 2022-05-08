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

### indexTest:

键名都是规定好的

```js
export default{
    //命名空间
    namespace:'indexTest',
    state:{
        name:"小冯"
    },
    reducers:{
        setName(state,payload){
            console.log(payload,'payload')
            // 返回新的state,也可以深拷贝
            return {...state,name:payload.data}
        }
    }
}
```





```jsx
import React from 'react';
import { connect } from 'dva';


const IndexPage = (props) => {
  // console.log(props)
  const handleClick=()=>{
      //传递action
    props.dispatch({
        //这个地方type规定先写命名空间/再写reducers的方法
      type:"indexTest/setName",
        data:"猪猪侠"
    })
  }
  return (
    <div>
      Indexpage
      <div>{props.msg}</div>
      <div>{props.name}</div>
      <button onClick={handleClick}>点击</button>
    </div>
  );
}
//状态映射为props
  //state就是indexTest里的state
const mapStateToProps=state=>{
 
  return{
      msg:"我爱你",
      name:state.indexTest.name
  }
}

export default connect(mapStateToProps)(IndexPage);

```

