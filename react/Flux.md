##### Flux

在2014年，facebook提出了Flux，Flux 是一种架构思想，专门解决软件的结构问题。它跟MVC 架构是同一类东西，但是更加简单和清晰。

其实FLUX在react里的应用就类似于vue中的vuex的作用，但是

在vue中，vue是完整的mvvm框架，而vuex只是一个全局的插件

react只是一个视图层的框架，在flux是一个架构思想，我们在做项目的时候使用flux架构的话要比单纯使用react要简单很多，这个时候，react在整个FLUX架构中担任某一个角色的

react在这里只是充当了FLUX架构体系中的view层

Flux的组成部分：

* View： 视图层
* ActionCreator（动作创造者）：视图层发出的消息（比如mouseClick）
* Dispatcher（派发器）：用来接收Actions、执行回调函数
* Store（数据层）：用来存放应用的状态，一旦发生变动，就提醒Views要更新页面


Flux的流程：

1. 组件获取到store中保存的数据挂载在自己的状态上
2. 用户产生了操作，调用actions的方法
3. actions接收到了用户的操作，进行一系列的逻辑代码、异步操作
4. 然后actions会创建出对应的action，action带有标识性的属性
5. actions调用dispatcher的dispatch方法将action传递给dispatcher
6. dispatcher接收到action并根据标识信息判断之后，调用store的更改数据的方法
7. store的方法被调用后，更改状态，并触发自己的某一个事件
8. store更改状态后事件被触发，该事件的处理程序会通知view去获取最新的数据
