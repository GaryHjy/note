## clipboard

clipboard实现一键复制


- 安装

```
npm install clipboard --save
```

- 使用

```v
// html
<template>
  <p id="msg"> copy message </p>  //设置id,用以后面获取数据
  <button class="btn"
    data-clipboard-target="#msg"  //使用data-clipboard-target可以直接指向需要复制的数据。 data-clipboard-text 是放置需要复制的数据
    @click = "copy"/>
</template>
```

```v
methods: { 
  copy() { let clipboard = new Clipboard('.btn') //注意要使用let或者const，不能使用var，否则会出现复制次数叠加的问题，即复制不止一次。
    //因为var是全局变量，let和const是局部
    clipboard.on('success',e =>{
      alert('copy success')
      clipboard.destroy() //使用destroy可以清除缓存
    })
    clipboard.on('error',e =>{
      alert('failed')
      clipboard.destroy()
    }
  }
}

```