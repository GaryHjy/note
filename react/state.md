## 状态(state)

状态就是组件描述某种显示情况的数据，由组件自己设置和更改，也就是说由组件自己维护，使用状态的目的就是为了在不同的状态下使组件的显示不同(自己管理)

在组件中只能通过getInitialState的钩子函数来给组件挂载初始状态,在组件内部通过this.state获取

this.props和this.state是纯js对象,在vue中，$data属性是利用Object.defineProperty处理过的，更改$data的数据的时候会触发数据的getter和setter，但是react中没有做这样的处理，如果直接更改的话，react是无法得知的，所以，需要使用特殊的更改状态的方法：

setState(params)

在setState中传入一个对象，就会将组件的状态中键值对的部分更改，还可以传入一个函数，这个回调函数必须返回像上面方式一样的一个对象，函数可以接收prevState和props

```
//1.
let doing = this.state.doing=='学习'+props.knowledge?'玩游戏':'学习'+props.knowledge
this.setState({doing})

//2.
this.setState((prevState,props)=>{
    return {
        doing:prevState.doing=='学习'+props.knowledge?'玩游戏':'学习'+props.knowledge
    }
})
```