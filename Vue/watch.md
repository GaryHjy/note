## watch

Vue 通过 watch 选项提供了一个更通用的方法，来响应数据的变化。当需要在数据变化时执行异步或开销较大的操作时，这个方式是最有用的。

- 普通用法

只能监听普通的变量，如果是对象的话需要深度监听

```
<script>
  export default {
    data() {
      return {
        isWatch: true
      }
    },
    watch: {
      isWatch(val,oldVal) {
        ...
      }
    }
}
</script>
```

- 监听对象  

监听对象需要深度监听

```
<script>
  export default {
    data() {
      return {
        obj: {
          a: 1,
          b: 2
        }
      }
    },
    watch: {
      obj(val,oldVal) {
        //这里的val与oldVal是获取的值是一样的
        handler:function() {
          ...
        },
        deep: true
      }
    }
}
</script>
```
高级用法

上面深度监听对象获取的val与oldVal是一样的值。其最好的方法是与computed配合,而且能够与上一个值是可以对比的。
```
<script>
  export default {
    data() {
      return {
        obj: {
          a: 1,
          b: 2
        }
      }
    },
    computed: {
      newObj() {
        return this.obj
      }
    },
    watch: {
      newObj(val,oldVal) {
        //这里的val与oldVal是获取的值是不一样的
        ...
      }
    }
}
</script>
```