## vuex 状态管理工具

项目较为庞大，组件结构比较复杂的时候，多组件的状态共享会比较麻烦，而且如果只是用普通的组件通信方法根本无法做到高效的维护，所以vue给我们提供一个状态管理工具vuex，来帮助我们实现这样的功能。



采用集中式存储管理应用的所有组件的状态。



核心功能都是通过store来实现。



vue中引入vuex，并且注入到vue中，并暴露出去，可以在根入口直接引入vuex，这样可以在任何组件中直接通过this.$store的方式来使用里面的信息。

```
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

const store = new Vuex.Store({
    
});

export default store;
```

vue中分为几个部分

state，getters，actions，mutations

### state

state就是一个纯js对象，用来保存状态（数据）

```
const state = {
    count: 1
}
//暴露出去然后直接注入vuex中
```

在组件中使用状态的时候，可以通过this.$store.state来使用，但是有时候，我们希望自己定义一条数据来接收store中的数据，为了实现响应式，要使用computed

```
computed(){
    getCount(){
        return this.$store.state.count;
    }
}
```

以上定义的方法，如果组件中存在多个需要向state拿取数据的话，较为麻烦，所以vuex中给我们提供了一个 mapState 辅助函数用来简化我们的操作。其返回的是一个对象。

```
import { mapState } from 'vuex';

computed(){
	//方法里面是对象
    mapState({
    	//通过箭头函数
        count: (state)=>state.count,
        //直接获取state里面的数据，左边为组件定义的变量，右边为state中的值
        count:'count',
    });
    //方法里面是数组，这种方法更为简单，需要什么引入什么，缺点为无法定义组件中的变量名
    mapState(['count'])
}
```

函数返回的是一个对象。我们如何将它与局部计算属性混合使用呢？通常，我们需要使用一个工具函数将多个对象合并为一个，以使我们可以将最终对象传给 computed 属性。 通过扩展运算符。

```
computed(){
    ...mapState(['count']);
}
```

### mutations

mutations 提供更换数据的方法，里面的方法能接收到state这个参数，其中可以自定义传入一个参数，参数最好为一个对象。

```
const mutations = {
    updateCount(state){
        state.count ++;
    }
}
//自定义传参
const mutations = {
    updateCount(state,payload){
        state.count += payload.num;
    }
}
```

在组件中如果要调用这个方法，需要如下操作

```
methods:{
    updateCount(){
        this.$store.commit('updateCount');
    }
}
```

如果组件中需要调用多个mutations中的方法的话，我们的操作会变得非常繁琐，所以vuex中给我们提供了一个方法可以简化我们的操作。

```
import { mapMutations } from 'vuex';

methods:{
	//数组方法
    ...mapMutations( ['updateCount'] ),
    // 对象方法
    ...mapMutation({
    	// 这种方式可以定义组件中的方法名
        updateCount:'updateCount'
    })
}
```

### actions

vuex中给我们提供了一个actions方法，用来处理我们的异步请求。

```
// 一般用于发送异步请求
import axios from 'axios';

const actions = {
	// 通过context.commit调用mutations中的方法
    asyncToCount( context ){
        setTimeout(function(){
        	//第一种，直接调用
            // context.commit('updateCount',{num:2})
            
            //第二种
            context.commit({
                type:'updateCount',// 调用哪个方法
                num:2 //传入的参数
            });
            
        },500)
    }
}
export default actions;
```

在组件中直接调用actions中的方法

```
methods:{
    asyncToCount(){
        return this.$store.dispatch('asyncToCount')
    }
}
```

在actions中也给我们组件提供了mapActions方法，简化我们的操作，更好的调用我们的方法。

```
import { mapActions } from 'vuex';

methods : {
    ...mapActions(['asyncToCount']);
}

```

### 定义常量

到了这里，我们已经知道mutations是可以修改状态的，所以官方推荐我们使用常量替代 mutation 事件类型在各种 Flux 实现中是很常见的模式。这样可以使 linter 之类的工具发挥作用，同时把这些常量放在单独的文件中可以让你的代码合作者对整个 app 包含的 mutation 一目了然：

```
// const.js
const TEXT = 'TEXT';

export default = {
    TEXT
}
```

在mutations中引入

```
import { TEXT } from './const.js';

cosnt mutations = {
    [ TEXT ] (state){
        ....
    }
}
```

### getters

根据一条现有状态，派生出一条新状态.

这里的getters可以看成vuex中的计算属性

```
const getters = {
    getCount(state){
        return state.count * 2;
    }
}
export default getters;
```

在组件中使用this.$store.getters调用里面的方法

```
computed : {
    getCount(){
        return this.$store.getters.getCount
    }
}
```

getters中也提供了相应的遍历方法

```
import { mapGetters } from 'vuex';
computed : {
    // 数组的形式
    ...mapGetters(['getCount']),
    
    // 对象的形式
    ...mapGetters({
    	// 可自定义组件中的方法名
        getCount:'getCount'
    })
}
```

### Modules

vuex中为了方便我们团队维护自己的store，给我们提供了一个modules方法，让我们更方便维护自己的模块。但是，各个模块的state不会合并到一起，而是按照模块去存放数据。

```
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

const moduleA = {
    state:...,
    getters:...,
    mutations:...,
    actions:...
}
const moduleB = {
    state:...,
    getters:...,
    mutations:...,
    actions:...
}

const store = new Vuex.store({
    modules:{
        a : moduleA,
        b : moduleB
    }
});

```









 