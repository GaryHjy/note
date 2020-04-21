 babel-plugin-import   是一款 babel 插件，它会在编译过程中将 import 的写法自动转换为按需引入的方式

 ```
 // .babelrc or babel-loader option
{
  "plugins": [
    ["import", {
      "libraryName": "antd",
      "libraryDirectory": "es",
      "style": "css" // `style: true` 会加载 less 文件
    }]
  ]
}
```