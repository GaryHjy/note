## 资源文件夹

static目录下的文件是绝对路径，会发起一个请求。/static

assets中引入的图片，会转换成base64编码格式，可以直接在img的src上使用，减少http请求，提高响应速度。如果体积太大的话不会自动转（10k以上），直接扔回static目录中，适合放一下体积比较小的图标图片。

### 设置服务器代理

```
'/api': {
    target: 'https://b2capigateway.yiguo.com/api',
    changeOrigin: true,
    pathRewrite: {
    	'^api': ''
    }
}
```

