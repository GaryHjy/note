## 路由守卫

### 路由跳转

```
<router-link to="/home" />
<router-link to="{name:'home'}" tag="li" /> // tag属性时可以改变标签
```

replace 设置为无浏览记录

to 设置跳转到哪个路由

tag 设置标签类型

active-class 设置选中之后的类名

exact 匹配模式

event 触发事件



### 路由中独享的守卫

beforeEnter(to,from,next)

to：跳转的路由的时候执行，to身上携带着跳转过去的信息

from：来的路由的信息，从哪个路由过来

next：代表下一步操作，执行的时候可以跳转到要去的路由，可以传入path来控制

```
const router = new VueRouter({
  routes: [
    {
      path: '/foo',
      component: Foo,
      beforeEnter: (to, from, next) => {
        // ...
      }
    }
  ]
})
```

## 组件内的守卫

```
const Foo = {
  template: `...`,
  beforeRouteEnter (to, from, next) {
    // 在渲染该组件的对应路由被 confirm 前调用
    // 不！能！获取组件实例 `this`
    // 因为当守卫执行前，组件实例还没被创建
  },
  beforeRouteUpdate (to, from, next) {
    // 在当前路由改变，但是该组件被复用时调用
    // 举例来说，对于一个带有动态参数的路径 /foo/:id，在 /foo/1 和 /foo/2 之间跳转的时候，
    // 由于会渲染同样的 Foo 组件，因此组件实例会被复用。而这个钩子就会在这个情况下被调用。
    // 可以访问组件实例 `this`
  },
  beforeRouteLeave (to, from, next) {
    // 导航离开该组件的对应路由时调用
    // 可以访问组件实例 `this`
  }
}
```

### 全局守卫

全局路由判断，拦截放行

![1540880246827](C:\Users\John\AppData\Local\Temp\1540880246827.png)