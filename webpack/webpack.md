### webpack

前端工程化： npm、cnpm、yarn、bower、tnpm | grunt 、 gulp 、webpack

gulp： 基于流的前端自动化构建工具，基于流的任务式的工具

gulp.src("a.scss").pipe(scss()).pipe(postcss()).pipe(gulp.dist(''))

webpack： 是一款模块化打包工具，webpack是基于配置的，通过配置一些选项来让webpack执行打包任务。

npm i webpack -g

npm i webpack-cli -g (4.0+)

npm i yarn -g

webpack在打包的时候，依靠依赖关系图，在打包的时候需要告知webpack两个概念：入口和出口

一般情况下，我们需要使用webpack.config.js进行配置

##### entry

entry配置项目打包的入口，值可以为单个的字符串执行某一个文件的地址，这个时候该文件就是入口文件，webpack会根据入口文件里各模块间的关系形成依赖关系图，然后根据依赖关系图进行打包
```
entry:'./src/app.js',
output:{
    path:path.join(__dirname,'build'),
    filename:'app.js'
}
```
但是有的时候我们需要的是多入口，我们就写成数组的形式，数组里的每一个字符串地址指向的都是一个独立的入口，webpack会将这些入口的依赖打包
```
entry:['./src/app.js','./src/vendor.js'],
output:{
    path:path.join(__dirname,'build'),
    filename:'[name].js'//不确定名字的时候，这里会打包成main.js
}
```
刚才的两种entry配置都只会打包出一个js文件，但是在某一个应用中我们可能需要将js根据依赖关系打包成多个js文件，并且在多页面应用中，我们也确实不可能只使用一个js文件，那么我们就可以使用如下的配置：

```
    entry:{
        app:'./src/app.js',
        vendor:'./src/vendor.js'
    },
    output:{
        path:path.join(__dirname,'build'),
        filename:'[name]_[hash].js'
    }
```
这样，因为filename里写成名字是[name],所以会根据entry的配置的键名来为打包出的js文件命名，hash是每次打包的一个随机的hash值，可以用来做版本控制

##### output 

在这里我们配置打包输出的一些选项

filename可以确定打包出来的文件的名字，在里面我们可以使用[name],[hash]这样的占位符

path配置打包出去的文件的路径，需要是绝对路径

##### env

在命令行或者终端中执行 webpack --env hello命令，就相当于在打包的时候传入一个参数为hello

在webpack.config.js中可以暴露出一个函数，这个函数就可以接收到env参数，当然函数就可以根据env参数来有选择的返回某一个或多个配置对象
```
module.exports = (env)=>{
    if(env=='production'){
        return productionConfig
    }
    return developmentConfig
}
```

--watch 可以让webpack去监听文件的改变。
可以在package.json里的scripts中配置一些快捷操作，通过npm run来运行


##### plugins

在webpack编译用的是loader，但是有一些loader无法完成的任务，交由插件（plugin）来完成，插件的时候需要在配置项中配置plugins选项，值是数组，可以放入多个插件的使用，而一般的插件都是一个构造器，我们只需在plugins数组中放入该插件的实例即可，在实例化插件的时候又可以传入options，对插件的使用进行配置

html-webpack-plugin

这个插件可以选择是否依据模板来生成一个打包好的html文件，在里面可以配置、title、template、filename、minify等选项，详情请查阅[文档](https://segmentfault.com/a/1190000007294861)

在这个插件里，我们可以使用jade、hbs、ejs等模板引擎来编译成html，这里举例jade的配置：

[文档](https://segmentfault.com/a/1190000000357534)
```
npm i jade jade-loader --save-dev

module:{
    rules:[
        {
            test:/\.jade$/,
            use:'jade-loader'
        }
    ]
},
plugins:[
    new HtmlWebpackPlugin({
        // title:'webpack-config-demo',
        template:'./src/index.jade',
        filename:'index.html'
    })
]
```

postcss:https://blog.csdn.net/xiaotuni/article/details/78014852

##### webpack-dev-server

webpack相辅相成的有一个server功能工具可以提供开发的热更新服务器

npm install webpack-dev-server -g
npm install webpack-dev-server -D

第一种启动方式： 直接执行webpack-dev-server,如果有需要配置的选项，在后面跟上参数即可。例如
```
webpack-dev-server --hot true
```
第二种启动方式：在webpack.config.js中配置devServer的选项，执行webpack-dev-server就ok
```
devServer:{
    port:9000,
    contentBase:'./build',
    historyApiFallback: true,
    open: true,
    proxy:{
        
    }
}
```
#### LOADERS
在webpack中专门有一些东西用来编译文件、处理文件，这些东西就叫loader，loader的使用就是在配置项中，设置modules，在modules中设置rule值为数组，在数组里放入多个匹配规则：

```
module:{
    rules:[
        {test:/\.css$/,use:'css-loader'}
    ],
    //before
    loaders:[
        {test:/\.css$/,loader:'css-loader'}
    ],
}
```

test为此次匹配要匹配的文件正则规则，use代表要使用的loader

使用url-loader可以将css中引入的图片（背景图）、js中生成的img图片处理一下，生成到打包目录里

视图html-withimg-loader可以将html中img标签引入的img图片打包到打包目录

file-loader

```
{
    test:/\.(png|jpe?g|svg|gif)$/,
    // use:'url-loader?limit=1000&name=images/[hash:8].[name].[ext]'
    use:[
        {
            loader:'url-loader',
            options:{
                limit:1000,
                name:'/static/images/assets/[hash:8].[name].[ext]'
            }
        }
    ]
},
{
    test:/\.html$/,
    use:'html-withimg-loader'
}
```

处理css：

cnpm i css-loader style-loader --save-dev


配置：

{
    test:/\.css$/,
    use:['style-loader','css-loader']
}

注意。webpack中loader的使用是从后往前的

css-loader可以将引入到js中的css代码给抽离出来，style-loader可以将抽离出来的css代码放入到style标签中

处理sass

{
test:/\.scss$/,
use:['style-loader','css-loader','sass-loader']
},

将引入项目的css文件、scss文件抽成一个文件，引入到页面中

cnpm i extract-text-webpack-plugin

```
const ExtractTextWebpackPlugin = require('extract-text-webpack-plugin')
///loader
{
	test:/\.css$/,
	use:ExtractTextWebpackPlugin.extract({
      fallback: "style-loader",
      use: "css-loader"
    })
},
{
	test:/\.scss/,
	use:ExtractTextWebpackPlugin.extract({
      fallback: "style-loader",
      use: ["css-loader","sass-loader"]
    })
}
///plugin
new ExtractTextWebpackPlugin({
	filename:'app.css',
	allChunks:true
})
```

因为ExtractTextWebpackPlugin对webpack4支持的不是很好，所以我们这样解决：

cnpm i extract-text-webpack-plugin@next -D
yarn add extract-text-webpack-plugin@next -D

@next下载的就是最最新的版本，可能是开发版本

webpack-dev-server进行了一个优化，在跑起服务的时候，会将编译结果保存在内存里，不会实时的输出的打包结果

css兼容优化处理：post-css 、autoprefixer
{
    test: /\.scss$/,
    use: ['style-loader','css-loader',{
        loader: 'postcss-loader',
        options: {
            sourceMap: true,
            config: {
            path: 'postcss.config.js'  // 这个得在项目根目录创建此文件
            }
        }
        },'sass-loader']
}

postcss.config.js：
module.exports = {
    plugins: [
      require('autoprefixer')
    ]
};
处理es6：

需要的依赖：

"babel": "^6.23.0",
"babel-core": "^6.24.1",
"babel-loader": "^7.0.0",
"babel-preset-es2015": "^6.24.1",
"babel-preset-react": "^6.24.1",



rules：
{
    test:/\.js$/,
    exclude: /node_modules/,
    loader:'babel-loader',
    query: {
        presets: ['es2015','react']
     }
}