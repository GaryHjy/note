## slot 插槽

### 插槽

- vue提供一个内容分发的功能，将元素作为承载分发内容的出口。
- 指令：v-slot


#### 默认插槽

- 一个不带 name 的 `<slot>` 出口会带有隐含的名字“default”。

```
  <div class="a-component>
    <slot></slot>
  <div>
```
- 使用

```
  <a-component>
    这是默认插槽
  <a-component>
```


#### 具名插槽

- 可以通过给插槽定义名字，插入指定位置

```
  <div class="a-component>
    <slot name="slotA"></slo>
  <div>
```

- 使用方法

```
  <a-component>
    <template v-slot:slotA>
      具名插槽
    </template>
  </a-component>
```

- 缩写

```
  <a-component>
    <template #slotA>
      具名插槽
    </template>
  </a-component>
```


#### 作用域插槽

- 可以通过作用域插槽将数据传递至父级

```
  <div class="a-component>
    <slot v-bind:user="user">
      {{ user}}
    </slot>
  <div>
```

- 使用方式

```
  <a-component>
    <template v-slot:default="slotProp">
      {{ slotProp.user }}
    </tempate>
  </a-component>
```

- 默认插槽简写

```
  <a-component>
    <template v-slot="slotProp">
      {{ slotProp.user }}
    </template>
  </a-component>
```
