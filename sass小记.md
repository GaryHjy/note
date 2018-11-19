# 安装Sass和Compass  #
 
window下安装SASS首先需要安装Ruby，先从官网下载Ruby并安装。安装过程中请注意勾选Add Ruby executables to your PATH添加到系统 （https://rubyinstaller.org/downloads/）   

ruby -v  
查看ruby安装成功  

因为国内网络的问题导致gem源间歇性中断因此我们需要更换gem源。  
gem sources --remove https://rubygems.org/  
删除原gem源  

gem sources -a https://ruby.taobao.org/  
添加国内淘宝源  

gem sources -l  
打印是否替换成功  

gem install sass   
安装sass  

gem uninstall sass  
删除sass  

gem install compass  
安装compass   

gem uninstall compass  
删除compass  

gem update sass  
更新sass  

sass -v  
查看sass版本信息  

sass -h  
查看sass帮助  

---------------------------------------------------------------
# 编译sass#

sass编译有很多种方式，如命令行编译模式、sublime插件SASS-Build、编译软件koala、前端自动化软件codekit、Grunt打造前端自动化工作流grunt-sass、Gulp打造前端自动化工作流gulp-ruby-sass等。  

	命令行编译  

sass input.scss output.css   
单文件转移命令  

sass --watch input.scss:output.css  
单文件监听命令  

sass --watch app/sass:public/stylesheets  
如果你有很多的sass文件的目录，你也可以告诉sass监听整个目录  

	命令行编译配置选项  

命令行编译sass有配置选项，如编译过后css排版、生成调试map、开启debug信息等，可通过使用命令sass -v查看详细。我们一般常用两种--style，--sourcemap。  

sass --watch input.scss:output.css --style compact  
编译格式  

sass --watch input.scss:output.css --sourcemap  
编译添加调试map  

sass --watch input.scss:output.css --style expanded --sourcemap  
选择编译格式并添加调试map  

sass --watch input.scss:output.css --debug-info  
开启debug信息  

- --style表示解析后的css是什么排版格式;  
 sass内置有四种编译格式:nested、expanded、compact、compressed。  
- --sourcemap表示开启sourcemap调试。开启sourcemap调试后，会生成一个后缀名为.css.map文件。   

nested：嵌套缩进的css代码，它是默认值。  
expanded：没有缩进的、扩展的css代码。  
compact：简洁格式的css代码。  
compressed：压缩后的css代码。  

---------------------------------------------------------------
#基本用法#

1.变量  
sass允许使用变量，所有变量以$头  
例：$blue:#1875e7;  
　　div{  
　　　　color:$blue;  
　　}  

如果变量需要镶嵌在字符串之中，就必须需要写在#{}之中。  
例：$side:left;   
　　.rounded {  
　　　　border-#{$side}-radius: 5px;  
　　}  

2.计算功能  
sass允许在代码中使用算式  
例：body {  
　　　　margin: (14px/2);  
　　　　top: 50px + 100px;  
　　　　right: $var * 10%;  
　　}

3.嵌套  
sass允许选择器嵌套。  
例：div h1 {  
　　　　color : red;  
　　}  
可以写成：  
　　div {  
　　　　h1 {  
　　　　　color:red;  
　　　　}  
　　}  
属性也可以嵌套，比如border-color属性，可以写成：  
　　p {  
　　　　border: {  
　　　　　　color: red;  
　　　　}  
　　}  
注意，border后面必须加上冒号。
在嵌套的代码块内，可以使用&引用父元素。比如a:hover伪类，可以写成：  
　　a {  
　　　&:hover {  
　　　　 color: #ffb3ff;  
　　　　}  
　　}  

4.注释  
SASS共有两种注释风格。  
标准的CSS注释 /* comment * / ，会保留到编译后的文件。  
单行注释 // comment，只保留在SASS源文件中，编译后被省略。  
在 / * 后面加一个感叹号，表示这是"重要注释"。即使是压缩模式编译，也会保留这行注释，通常可以用于声明版权信息。  

---------------------------------------------------------------

#代码的重用#

**1.继承**  
sass允许一个选择器，继承另一个选择器。  
例： .class1 {  
　　　　border: 1px solid #ddd;  
　　}  
class2要继承class1，就要使用@extend命令：  
　　.class2 {  
　　　　@extend .class1;  
　　　　font-size:120%;  
　　}  

**2.Mixin**  
Mixin有点像C语言的宏（macro），是可以重用的代码块。  
使用@mixin命令，定义一个代码块。  
　　@mixin left {  
　　　　float: left;  
　　　　margin-left: 10px;  
　　}  
使用@include命令，调用这个mixin。  
　　div {  
　　　　@include left;  
　　}  
mixin的强大之处，在于可以指定参数和缺省值。  
　　@mixin left($value: 10px) {  
　　　　float: left;  
　　　　margin-right: $value;  
　　}  
使用的时候，根据需要加入参数：  
　　div {  
　　　　@include left(20px);  
　　}  
下面是一个mixin的实例，用来生成浏览器前缀。  
　　@mixin rounded($vert, $horz, $radius: 10px) {  
　　　　border-#{$vert}-#{$horz}-radius: $radius;  
　　　　-moz-border-radius-#{$vert}#{$horz}: $radius;  
　　　　-webkit-border-#{$vert}-#{$horz}-radius: $radius;  
　　}  
使用的时候，可以像下面这样调用：  
　　#navbar li { @include rounded(top, left); }  
　　#footer { @include rounded(top, left, 5px); }  

**3.颜色函数**  
SASS提供了一些内置的颜色函数，以便生成系列颜色。  
　　lighten(#cc3, 10%) // #d6d65c  
　　darken(#cc3, 10%) // #a3a329  
　　grayscale(#cc3) // #808080  
　　complement(#cc3) // #33c  

**4 插入文件**  
@import命令，用来插入外部文件。  
　　@import "path/filename.scss";  
如果插入的是.css文件，则等同于css的import命令。  
　　@import "foo.css";  

---------------------------------------------------------------

#高级用法#

1.条件语句  
@if可以用来判断：  
例：p {  
　　　　@if 1 + 1 == 2 { border: 1px solid; }  
　　　　@if 5 < 3 { border: 2px dotted; }  
　　}  
配套的还有@else命令：  
例：@if lightness($color) > 30% {  
　　　　background-color: #000;  
　　} @else {  
　　　　background-color: #fff;  
　　}  

2.循环语句  
SASS支持for循环：  
例：@for $i from 1 to 10 {  
　　　　.border-#{$i} {  
　　　　　　border: #{$i}px solid blue;  
　　　　}  
　　}  
也支持while循环：  
例：$i: 6;  
　　@while $i > 0 {  
　　　　.item-#{$i} { width: 2em * $i; }  
　　　　$i: $i - 2;  
　　}  
each命令，作用与for类似：  
例：@each $member in a, b, c, d {  
　　　　.#{$member} {  
　　　　　　background-image: url("/image/#{$member}.jpg");  
　　　　}  
　　}  
3.自定义函数  
SASS允许用户编写自己的函数  
例：@function double($n) {  
　　　　@return $n * 2;  
　　}  
　　#sidebar {  
　　　　width: double(5px);  
　　}  
