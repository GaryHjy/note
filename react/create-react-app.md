##### create-react-app 脚手架

npm install create-react-app -g

create-react-app my-app //生成一个react开发模板在my-app目录
//生成的过程特别缓慢，可以使用yarn工具来下载，也就是说先去下载安装yarn   ：npm install yarn -g

当我们要进行二次配置的时候，需要找到node_modules文件夹里的react-scripts进行配置，但是当我们执行npm run eject就可以将配置文件抽出，方便开发配置
