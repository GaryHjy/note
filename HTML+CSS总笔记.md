# HTML

## 版本

HTML超文本标记

XHTML可扩展超文本标记

HTML5第五个版本

## 重大改革

1999年发布HTML4.01 

2000年发布XHTML 1.0 

2014年发布HTML5   

## 组织

W3C  制定html和css的标准

WHATWG  浏览器临时组成的组织

 ECMA   JS的标准  

## web标准

1.结构（html）

2.表现（css）

3.行为（js）

## 文件命名规则

用英文，不用中文    

名称全部用小写英文字母、数字、下划线的组合，其中不得包含汉字、空格和特殊字符；必须以英文字母开头

首页必须命名为index.html 

## 结构    

### 写代码的注意事项    

1.html > head+body 双标签

2.缩进问题 tab键

3.shift+< >

4.一对对敲 

5.ctrl+s 保存

### 页面结构 

doctype：声明文档类型 DOTYPE html声明文档类型为html5    html：这是html文件 

head：存放页面信息 

body：书写页面代码，呈现在浏览器上

meta：元信息标签[charset字符编码 utf-8国际通用编码 gb2312国内通用编码] 

title：页面标题

## sublime编辑器的使用 

### 1.打开文件夹方式

菜单-打开文件夹-site文件夹

### 2.找到指定文件夹

右键新建文件-.html

### 3.快捷方式   

#### 键盘快捷方式

ctrl+a 全选

ctrl+c 复制

ctrl+v 粘贴

ctrl+x 剪切

ctrl+s 保存

ctrl+z 返回上一步

ctrl+y 返回下一步     

ctrl+? 生成注释

ctrl+滚轮 放大缩小

shift+tab 往回缩进

#### 快速打开浏览器

右键打开浏览器、

F1、

F12打开chrome浏览器，

F3 ie浏览器

#### 快速生成标签名

标签名+tab键 生成html元素

### 4.控制台的使用    

找到指定内容-右键检查

F12-elements查看元素-styles查看样式

## 基本语法 

### 1.html标签

由尖括号包裹的一个整体

### 2.html元素

由一对双标签或一个单标签组成

### 3.html属性

由html属性="属性值"组成，html属性写在标签名字后面，用空格隔开。多个html属性或属性值，都用空格隔开

### 4.html注释

方便自己或他人理解，不会呈现在页面上

## 常用标签 

### 1.标题标签 

```
<h1></h1>
<h2></h2>
<h3></h3>
<h4></h4>
<h5></h5>
<h6></h6>
```

h1代表的含义最重，一个页面只有一个。

### 2.段落标签 

```
<p></p>
```

备注：页面上书写空格、换行，会默认解析成一个空格。空格的大小与字体大小有关，但不一定等于字体大小

### 3.换行标签

```
<br />
```

### 4.标识符

```
&nbsp;空格
&lt;小于号
&gt;大于号 
```

### 5.加粗标签

```
<b></b>
<strong></strong>
```

### 6.倾斜标签 

```
<i></i>
<em></em>
```

 备注：   视觉标签：b、i

​		语义标签：strong、em

### 7.分割线

```
<hr/>
```

### 8.列表标签  

#### （1）无序列表

```
<ul>
	<li></li>
</ul>
```

#### （2）有序列表

```
<ol>
	<li></li>
</ol>
```

#### （3）自定义列表

dl(definition list)>dt(definition term 自定义列表项)+dd(definition description对自定义列表项的描述)

```
<dl>
	<dt></dt>
	<dd></dd>
</dl>
```

### 9.图片标签

img

[src引入图片的路径 ../返回上一层]

[alt图片无法显示时，出现的文字]

[title鼠标悬停在图片上，出现的文字]

```
<img src="" title="" alt=""/>
```

### 10.锚链接、超链接

a

[href跳转到的地址 属性值可以是网址，#代表不跳转]

[target 跳转的目标窗口 属性值默认为_self当前窗口 _blank新窗口]

```
<a href="" target=""></a>
```

### 11.表格标签

table>行tr>单元格td

#### table属性

[border添加边框]

[cellspacing单元格间距]

[cellpadding单元格内填充，单元格边框与内容之间的距离]

[width表格宽度]

[height表格高度]

#### td属性

[colspan单元格合并列]

[rowspan单元格合并行]

```
<table border="" cellspacing="" cellpadding="" width="" height="">
	<tr>
		<td colspan=""></td>
		<td rowspan=""></td>
	</tr>
</table>
```

### 12.表单标签

#### form  

[action提交到的后台地址]

[method提交方式 get、post]

[name]

```
<form action="" name="" method=""></form>
```

#### input 

input

[type表单控件的类型 属性值：text文本框 password密码框 radio单选框 checkbox多选框 submit提交按钮 button普通按钮]  

[name给同一个单选框或多选框添加相同的名字]  

[checked 默认选中]  

[value 给表单控件添加内容]

```
<input type="" value="" name="" checked="" />
```

#### select

select&gt;选项option

[value 添加内容]

[selected默认选中] 

```
<select name="" id="">
	<option value=""></option>
</select>
```

#### textarea

[cols 列数]

[rows 行数]

```
<textarea name="" id="" cols="30" rows="10"></textarea>
```

### 13.div标签

没有语义的标签

 块级元素的特点：
    （1）默认占据一整行
    （2）可以设置宽高
块级元素：标题标签、p、列表、form

大部分块级元素都会存在默认的margin（外边距）或padding（内填充），除了div

### 14.span标签 

没有语义的标签
行内元素的特点：
	宽高由内容决定
	一行显示多个
行内元素：加粗、倾斜、a、img、input、select、textarea

# css基础

## 一、css简介

cascading style sheets 层叠样式表

层叠性：给同一个元素添加相同的属性，属性会存在覆盖问题。

## 二、CSS语法

选择器{声明}

声明由[css属性：属性值；]组成

## 三、CSS属性

#### width

宽度

#### height

高度

#### background-color

背景颜色

#### color

字体颜色

注释的写法：/**/

## 四、三种样式表

### 1.内部样式表

head>style[type="text/css"]，在style标签里面写css语法

作用域：当前页面

```
<style type="text/css"></style>
```

### 2.外部样式表

在css文件里面新建css文件，在css文件里面写css语法

head>link

[rel="styleheet"]

[href="链接外部样式表的路径"] 

作用域：引入了该css文件的所有页面生效

```
<link rel="stylesheet" type="text/css" href="路径" />
```

### 3.内联样式表、行内样式表

将style作为html属性，将声明作为html属性值

声明由 [css属性值：属性值;]组成

作用域：当前元素

```
<div style="width:100px;"></div>
```

### 4.优先级

内联样式>内部样式表

内联样式>外部样式表

权重一样的前提下，写在后面的样式表层叠前面的样式表

## 五、选择器

### 1.标签选择器

通过标签名字获取元素

```
<style type="text/css">
	div{
		color:red;
	}
</style>

<div>这是个div</div>
```

### 2.类选择器

通过[.类名]获取元素

[class]给元素添加类名（绰号），绰号可以重复 

```
<style type="text/css">
	.box{
		color:red;
	}
</style>

<div class="box">这是个div</div>
```

### 3.id选择器

通过[#id名]获取元素

[id]给元素添加id名（身份证号），不可以重复

```
<style type="text/css">
	#box{
		color:red;
	}
</style>

<div id="box">这是个div</div>
```

### 4.群组选择器

通过逗号将基本选择器隔开，表示都获取到。

```
#a,#b,#c{
    
}
```

### 5.通配符选择器

获取到页面中所有的元素

```
*{
    
}
```

### 6.后代选择器

（包含选择器）将基本选择器用空格隔开，表示获取到的后一个选择器是前一个的后代

```
#father #son{

}

<div id="father">
	<div id="son"></div>
</div>
```

### 7.子代选择器

将基本选择器用>隔开，表示获取到的后一个选择器是前一个的儿子

```
#father>#son{

}

<div id="father">
	<div id="son"></div>
</div>
```

### 8.交集选择器

将多个基本选择器不留空格书写，表示满足多个选择器条件的元素才会被获取到

```
<style type="text/css">
	p.aa{
        
	}
</style>

<p class="aa">paa</p>
<div class="aa">divaa</div>
```

### 9.伪类选择器

（1）:link 锚链接被访问前添加的样式

（2）:visited 锚链接被访问后添加的样式

（3）:hover 鼠标悬停在E元素添加的样式

（4）:active 鼠标点击E元素添加的样式

注：要按顺序。

### 命名规则

英文开头，可以包含数字、下划线、-，不要用关键字

## 六、选择器的优先级及权重

（存在层叠性问题时）
优先级：!important>内联样式>id选择器>类选择器（伪类选择器）>标签选择器>通配符选择器

权重0000：作用在同一个元素上，才能比较权重，若不是作用在同一个元素上，则继承的权重是最低的

第一个0 代表!important或者内联样式

第二个0 代表id选择器的个数

第三个0 代表类选择器的个数

第四个0 代表标签选择器的个数

# CSS核心属性

## 一、字体的相关属性

### 1.字体大小 font-size

默认的字体大小为16px，最小为12px。

9pt=12px。12pt=16px。

### 2.字体加粗 font-weight

属性值：normal正常

​		bold加粗

### 3.字体倾斜 font-style

属性值：normal正常

​		italic倾斜

### 4.字体家族 font-family

属性值为中文或者多个英文单词，必须用引号引起来

多个字体家族，用逗号隔开。

### 5.字体颜色 color

属性值可以是英文单词，也可以是16进制

#000000 六位数字，前两位数字表示红色，中间两位为绿色，后两位为蓝色

每一个数字的取值都为0-9、a-f

若是表示同一个颜色的两位数值都相等，则可以省略（三个数字）

## 二、文本的相关属性

### 1.文本大小写 text-transform

属性值：none 

​		capitalize首字母大写

​		lowercase全部小写

 		uppercase全部大写

### 2.文本修饰 text-decoration

属性值：none

​		underline下划线

​		overline 上划线

​		line-through 删除线

### 3.首行缩进 text-indent

单位：em代表的是以当前字体大小为基准

取值可以为负数。

### 4.字间距 letter-spacing

letter-spacing:属性值;

### 5.词间距 word-spacing

(空格标记点)单词与单词之间的空格

word-spacing:属性值;

### 6.水平对齐方式 text-algin

文本在所在的容器中的水平对齐方式(单行文本)

text-align:属性值;

属性值：left左边

​		right右边

​		center中间

​		justify两端对齐(对英文有效)

### 7.垂直对齐方式 vertical-align

文本的垂直对齐方式(行内元素)

vertical-align:属性值;

属性值：baseline(基线) 

​		top(顶线)

​		bottom(底线)

​		middle(中线)

文本若是一行显示，默认是以基线对齐、

### 8.行高 line-height

一行文本的高度。行高=字体大小+行高的上间距+下间距

行高的上间距=下间距

若想单行文本在容器中垂直居中，将line-height的大小等于height的大小

若想单行文本在容器的垂直偏上位置，设置line-height<height

测量同一段文本的行高，直接从上一行文本的最顶（底）端到下一行文本的对顶（底）端

## 三、列表符号的相关属性

### 1.列表样式类型 list-style-type

list-style-type:属性值;

 属性值：disc实心圆

​		circle空心圆 

​		square方块

​		none空

### 2.列表样式图片 list-style-image

list-style-image:url()

### 3.列表样式位置 list-style-position

list-style-position:属性值;

属性值: inside  在列表项里面

默认在外面	

### 4.总属性 list-style

list-style:type或url position

## 四、边框的相关属性

### 1.边框宽度 border-width

border-width:属性值;

```
border-width:16px;
```

### 2.边框样式 border-style

border-style:属性值;

属性值：实线solid 

​		虚线dashed  

​		点线dotted

​		双线double

### 3.边框颜色 border-color

border-color:属性值;

### 4.总属性 border

border:border-width border-style border-color

之间用空格隔开

### 5.border-方位

border-方位

备注：top上 bottom下 left左 right右

总属性与分属性同时存在，先写总属性。

### 6.border-方位-分属性

border-方位-分属性:分属性值;

## 五、背景的相关属性

### 1.背景颜色background-color

background-color:颜色;

### 2.背景图片background-image

当容器尺寸大于背景图片尺寸时，背景图片会重复平铺整个容器

当容器尺寸等于背景图片尺寸时，背景图片会被裁剪

当容器尺寸等于背景图片尺寸时，刚好放下。

### 3.背景平铺background-repeat

属性值：repeat重复(默认)

​		no-repeat不重复

​		repeat-x 水平方向平铺

​		repeat-y 垂直方向平铺

### 4.背景图片在容器中的定位background-position

background-position:水平方向(右为正) 垂直方向(下为正)

取值：数值(右为正)(下为正)

​	    方位(水平：left、center、right;垂直：top、center、bottom;)

### 5.背景图片的固定background-attachment

(必须用在滚动条的地方) 

属性值：scroll 滚动(默认)

​		fixed 固定

### 6.总属性background

background:‘’background-color‘’ ‘’background-image‘’ ‘’background-repeat‘’ ‘’background-position‘’ ‘’packground-attachment‘’

之间用空格隔开

## 六、浮动属性

### float

属性值：none    left左浮动   right右浮动

特点：

​	(1)浮动的元素会脱离标准流，但文本不会脱离文本流。

​	(2)浮动后的元素相当于行内块级元素(一行显示多个，可以设置宽高)

​	(3)如果浮动的元素一行无法放下，则会换行显示。换行元素的垂直位置会参考上一个元素的最低点开始摆放

# 页面书写注意

1.h1必须加背景图片，文本用text-indent隐藏掉

2.a标签默认字体颜色要覆盖的话，必须给a添加字体颜色

3.列表项小图标，若存在a，a{display:block;padding-left:;background:url() no-repeat left center;}。不存在a，就给li加上面的代码。

4.导航条部分，li只做浮动，a{dispaly:block;height;;}
 若每个列表项的宽度不一样，则不设置width，width默认由字数撑开，只设置左右的padding。{font-size;color;line-height;}

5.一般列表项悬停都是悬停在li上，改变里面的子元素

6.一般清除默认样式、添加公共样式、页面公共部分的样式都写在base.css里面，每个页面单独的样式写在对应的css文件。页面要同时链接两个css文件

7.页面之间的跳转通过锚链接的路径实现。

8.若父元素与子元素都浮动了，父元素如果不设置宽度，会由子元素撑开

# 元素类型

## 一、块级元素

div、h1-h6、p、列表、form

### 特点

（1）占父元素宽度的一整行，若是设置死宽度，那多余的位置会用margin填充。

（2）可以设置宽高

（3）块级元素可以包括部门块级元素及所有的行内元素

错误：p>h1，p>p，p>div

### 应用

若想子元素（块级元素）在父元素水平居中，对子元素设置margin:0 auto;

## 二、行内元素（内联）

span、a、加粗、倾斜、img、input、select、textarea、label

### 特点

（1）宽高由内容决定，不能设置宽高

（2）一行显示多个

（3）行内元素遵循盒模型，不能设置上下的padding、margin（不起作用）

补充：若想行内元素在容器中居中，则给容器加text-align:center即可。

## 三、元素类型的转换

### display 

改变元素的显示类型

### 属性值

​	1.block  转换成块级元素（用得很多）

​	2.inline  转换成行内元素

​	3.inline-block  转换成行内块级元素（一行显示多个、可以设置宽高）

​	4.list-item  转换成列表项

​	5.none  隐藏元素，不占位置

注：

​	1.大部分块级元素display属性值默认为block，其中列表li的默认值为list-item

​	2.大部分的内联元素的display属性值默认为inline，其中img、input、textarea默认为inline-block

## 四、行内块级元素与浮动的区别

### 行内块级布局

​	当元素设置成行内块级元素进行布局，之间换行会被当做一个空格。

​	解决方法

​		（1）不要换行

​		（2）给它们设置一个父元素｛font-size:0｝

​	行内元素垂直方向都存在基线对齐问题，通过｛vertical-align｝解决。

### 实现元素在父容器中垂直居中的方式

​	将子元素设置成inline-block;给它一个同级元素（尺子）{display:inlne-block;width:0;height:父元素高度;}

​	最后给两个子元素都设置{vertical-align:middle;}



！！！

行内不可置换元素（行内元素）

行内可置换元素（行内块级元素）

# position定位

## 一、静态定位

static 静态定位，默认定位。不能配合left、right、top、bottom使用

## 二、相对定位

relative 相对定位

特点：（1）相对于自己本身所在的位置进行移动定位

​	（2）配合left、right、top、bottom使用，相对于自己的某条边往元素中心方向移动为正值

​	（3）相对定位的元素不脱离标准流（灵魂出窍）

## 三、绝对定位

absolute 绝对定位

特点：（1）绝对定位的元素相对于html或者最近的有定位（除了static）的父辈元素进行定位。

​	（2）通过left、right、top、bottom实现定位，相当于包含块的某条边往包含块内部方向移动为正值。

​	（3）绝对定位的元素脱离标准流

## 四、固定定位

fixed 固定定位

特点：（1）相对于浏览器的可视区域进行定位

​	（2）通过left、right、top、bottom实现定位，相对于浏览器的可视区域的某条边内部方向移动为正值。

​	（3）固定定位的元素脱离标准流。

## 实现元素在父元素居中显示

子绝父相（父元素的定位还要具体案例），子元素{left:50%;top:50%;margin-left:负自己宽度的一半;margin-top:负自己高度的一半;}

备注：

​	盒模型中任意一个属性width、height、padding、border、margin，加上left、right、top、bottom使用百分比的话，指的是父元素宽高的百分比。

# z-index 层级

定位（除了static）>浮动>标准流

该属性只能用于有定位的元素上，取值可以为负数。

# 命名锚点

a[href="#id名"]关联到id名所在的元素，实现一种快速定位的效果

a[href="页面路径#id名"]关联到其他页面的id名所在的元素

# overflow

对内容溢出容器时的处理方式

visible 可见的

hidden 隐藏

scroll 出现滚动条

auto 内容溢出才出现滚动条

overflow-x 设置水平方向

overflow-y 设置垂直方向

当某一个方向的值不为visible，另外一个方向的值会自动设置auto

## 隐藏元素的两种方式

1.display:none;隐藏元素，不占位置

2.visibility:hidden;隐藏元素，占位置

# 宽高自适应

特点：适应在不同的设备、不同窗口和不同分辨率下显示。

## 1.宽度只适应

块级元素宽度设置为100%，或者不设置宽度（width），宽度是父元素的宽度。

补充：

​	若父元素脱离了标准流，父元素的宽度如果不写，就由子元素撑开。

备注：做页面一般都是给父元素加宽度，除非父元素宽度要由子元素确定的。

## 2.父元素高度由子元素撑开

### （1）高度塌陷

当子元素都浮动了，父元素会没有子元素撑开它的高度。

解决方法：

​	*给父元素加overflow:hidden;（可能造成部分内容丢失。）

​	*给父元素添加最后一个子元素（块级元素）{height:0;clear:both;overflow:hidden;}（造成内存浪费，页面生成太多无用元素）

​	*给父元素::after添加伪元素，从而实现给父元素添加最后一个子元素的效果。（display:block;height:0;clear:both;overflow:hidden;visibility:hidden;zoom:1;）

备注：一般会采用第三种方式，将清除浮动代码放在base.css，以后子元素都浮动了，只要给父元素加类名.clearfix即可。

### （2）父元素高度为0

当子元素没有内容时，父元素的高度为0

解决方法：最小高度min-height。当内容高度小于最小高度时，按最小高度显示。当内容高度大于最小高度，按内容高度显示。

兼容ie6：height作为最小高度，通过_下划线过滤器，让ie6才能识别这个属性。

## 3.元素高度自适应窗口高度

html，body{height:100%;}

div{height:100%;;}

## 4.最小高度min-height

内容不确定

当内容高度小于最小高度时，按最小高度显示

当内容高度大于最小高度时，按内容高度显示

## 5.最小宽度min-width

当页面宽度小于最小宽度时，按最小宽度显示（版心容器的宽度）

当页面宽度大于最小宽度时，按页面宽度显示

# 伪元素(对象)

模仿元素存在。

## 1. ::after

给元素添加最后一个子元素（行内元素）

content:"";不能省略。

content:url()添加图片

默认情况下为行内元素

## 2. ::before

给元素添加第一个子元素（行内元素）

content:"";不能省略。

## 3. ::first-letter

给元素的第一个文本添加样式

## 4. ::first-line

给元素的第一行文本添加样式

# 浏览器兼容

## 主流浏览器

IE、Safari、Mozilia Firefox、Google Chromo、Opera

## 最早浏览器

网景浏览器

第一次浏览器大战 IE浏览器

第二次是IE9

## 浏览器内核

Trident：IE

Gecko：Mozilia Firefox

Webkit：Safari、Google Chromo

Presto：Opera、公认的渲染速度最快的引擎

Blink：由Google 、Opera Software开发的浏览器排版引擎

## 问题

### 1.图片出现边框（ie8-）

解决方法：给图片加border:0;或者border:0 none;

### 2.图片留有间隙

解决方法：

​	（1）将img装换成块级元素==>base.css

​	（2）将父元素的字体大小设成0、

扩展：

​	背景图片：精灵图（小图标、万年不变的图片）、h1的logo（不做成精灵图）、轮播图

​	图片：经常变的图片（例如产品信息、也可以用背景图片）

### 3.双倍浮动（ie6）

给浮动元素的浮动向添加margin，会加倍显示

解决方法：给浮动元素{display:inline;}

### 4.默认高度（ie6、ie7）

部分块级元素拥有默认高度（在16px左右）

解决方法：（1）{font-size:0;}

​		（2）overflow:hidden;

### 5.表单元素行高对齐不一致

解决方法：（1）float:left:

​		（2）vertical-align:middle;

### 6.按钮元素默认大小不一

解决方法：设置成块级元素，清除边框，清除内填充，input{display:block;padding:0;border:0 none;}然后在元素外边加一个标签，给标签加input样式。

### 7.百分比bug（ie6-）

在IE6及以下版本中在解析百分比时，会按四舍五入方式计算从而导致50%加50%大于100%的情况。（也会受系统影响）

解决方法：给右边的浮动元素添加样式clear:right;清除右浮动，clear:left;清除左浮动。

### 8.鼠标指针bug

cursor属性的hand属性值只有IE9以下浏览器识别，其它浏览器不识别该声明，cursor属性的pointer属性值IE6.0以上版本及其它内核浏览器都识别该声明

解决方法：统一某元素鼠标指针形状为手型，应添加声明：cursor:pointer;

### 9.不透明度opacity（ie8-）

ie8：filter:alpha(opacity=50) 取值为0-100

### 10.不区分伪类与伪元素（ie8-）

ie8以下不区分伪类与伪元素，统一用单冒号。ie9以后，单冒号代表伪类，双冒号代表伪元素。

解决方法：伪元素清除浮动法兼容ie8，将伪元素改成单冒号

### 11.ie6出现高度塌陷

给子元素加浮动。

### 12.ie7-不支持子代选择器

### 13.margin塌陷

当父元素与第一个子元素存在上间距，若是给子元素加margin-top，它会错误的被渲染成父元素的margin-top

解决方法：

​	（1）将子元素的margin-top变成父元素的padding-top

​	（2）子元素或者父元素浮动了

​	（3）父元素加border-top

​	（4）父元素加overflow:hidden;

### 14.margin合并

当两个上下排列的元素，上元素有margin-bottom，下元素有margin-top，它们中间的距离不会叠加，而是会设置较大的值。

# 高级表单、表格、BFC

## 一、高级表单

### fieldset标签

表单字段集

作用：对表单中的元素进行分组

属性值：disabled定义空间禁止使用

### legend标签

字段集标题

作用：在fieldset对象绘制的方框内插入一个标题。对整个字段集的总结。（放在fieldset第一个子元素）

属性值：align:left/center/right/justify;

### label标签

提示信息标签

属性值：for 关联id所在的表单元素

作用：点击文字可以选中表单元素。

若是用在多选框或单选框，则直接将表单控件及文字一起作为label的子元素。

### input标签

#### type属性值

##### 1.file

上传文件

属性值：multiple 多个文件上传

```
<input type="file" name="file" multiple />
```

##### 2.image

图像提交按钮

属性值：src 图片路径 alt title

```
<input type="image" src="" />
```

## 二、表格

### caption标签

表格标题标签，放在table里面，第一个子元素

### th标签

标题行单元格，内容默认居中、且加粗

### thead、tbody、tfoot标签

行分组

thead>tr>td 表头

tbody>tr>td 表体

tfoot>tr>td 表尾

如果使用了其中一个标签，就必须使用全部的元素。

次序：thead、tfoot、tbody

### colgroup标签

列分组

属性值：span 表示每个列分组占据的列数

### 表格属性

#### rules属性

作用：添加分隔线

值：cols 添加列分隔线

​	rows添加行分隔线

​	all添加行列分隔线

​	none 默认值没有

​	groups添加组分隔线

### CSS属性

#### border-spacing属性

表格单元格间距（必须给table加，距离不可为负值）

#### border-collpase属性

合并单元格边框

属性值：separate 默认分离

​		collpase 合并

#### empty-cells属性

控制无内容时单元格的设置，给td加的属性

属性值：show 默认显示

​		hide 隐藏

#### caption-side属性

定义表格的caption对象位于表格的哪个位置

属性值：top、right、bottom、left

## 三、BFC

BFC（Block formatting context）直译“块级格式化上下文”。

代表独立的渲染区域，它规定了内部的块如何布局，并且与这个区域外部毫不相干。

### 布局规则

1、内部的box垂直方向一个接一个的放置

2、两个相邻的块会发生margin重叠

3、盒模型=content+padding+border+margin，width指的是content的宽，height是content的高

4、overflow:hidden会触发独立bfc，规定bfc的区域不会与浮动的区域重叠

5、bfc是独立的容器，容器里面的子元素不会影响到外面的元素

6、计算BFC的高度时，里面的浮动元素也参与计算（应用场景：清除浮动的第一种方式）

### 不会触发BFC的标签或元素

根元素html

float属性不为none

position为absolute（有定位的父元素或html）或fixed（可视窗口）

display为inline-block, table-cell, table-caption, flex, inline-flex（css3）

overflow不为visible(overflow:hidden;)

### 作用及原理

#### 自适应两栏布局

某一边宽度确定，另一边跟着屏幕宽度改变

左边定宽加+float，右边加overflow:hidden;

#### 清除内部浮动

两个元素设置浮动，会出现父元素高度不见了。

给父元素设置overflow:hidden;

#### 防止margin重叠

一个元素设置了margin-bottom，一个设置了margin-top，会导致两个元素之间的margin会发生重叠，

给第一个元素外面套一个元素，然后设置overflow:hidden;

## HTML5新标签+表单新类型、新属性

## 一、HTML5简介

### 1、HTML5的发展历史

### 2、HTML5的支持浏览器

IE9+、Firefox、Opear、Safari、Chrome

### 3、HTML5的特点

增加了新特性：语义特性（更好的支持屏幕阅读器，视障人士），本地存储特性，设备兼容特性，连接特性，网页多媒体特性，三维、图形及特效特性，性能与集成特性，CSS3特性

## 二、HTML5新标签

### 1、header

头部标签，主要存放标题、导航条。header、footer不要互相嵌套。

### 2、hgroup

对标题进行组合

### 3、nav

导航条标签，对于屏幕阅读器等设备效果更好。

### 4、main

内容标签，一般都是出现在结构外层，只能出现一次。

### 5、article

文章标签，独立的完整内容块。可以嵌套。

### 6、aisde

侧边栏标签，装载非正文的内容。

### 7、section

区块标签，代表专题性的内容，文章的章节。

### 8、footer

眉脚一般会包含作者姓名、文档版权信息、使用条款链接、联系信息等. （可多个）

### 9、figure、figcaption

figure标签对文字及图片进行组合。

figcaption对内容进行说明

IE9+支持

### 10、time

用来表现时间或日期

属性：datetime 

IE9+支持

### 11、details、summary

details定义细节

属性：open

summary对细节内容的总结

### 12、mark

定义带有记号的文本，突出文本

IE9+支持

### 13、progress

定义进度条

属性：max 定义最大值

​	value 当前值

IE10+支持

### 14、meter

定义度量尺

属性：min最低值

​	max最高值

​	value当前值

​	high较高的值

​	low较低的值

​	optimum定义较佳的值，如果该值高于“high”，意味值越高越好，如果该值低于“high”，意味值越低越好。

IE不支持

### 15、ruby、rt

注释标签，可以注释音标之类的

rt是注释的内容

```
<ruby>
	<rt></rt>
</ruby>
```

### 16、datalist

拥有输入功能的下拉列表数据列表，得与input关联

```
<input type="text" list="word"/>
<datalist id="word">
	<option></option>
</datalist>
```

### 17、output

输出标签

属性：oninput 将input的value值关联起来

```
<form action="#" oninput="jieguo.value = number1.value*number2.value">
	<input type="text" name="number1" />
        *
	<input type="text" name="number2"/>
        =
	<output name="jieguo"></output>
</form>
```



### 18、video

属性：autoplay 自动播放

​	controls向用户显示播放控件

​	width、height

​	poster 加载等待时的画面图片

​	loop 循环播放

支持的视频格式

​	ogg、webM、MP4

```
<video src="" autoplay></video>
```

兼容写法

```
<video controls>
	<soure src=""></soure>
</video>
```

### 19、audio

音频播放

属性与视频一样

## 三、表单新增输入类型

### 1、color

```
<input type="color">
```

### 2、email

```
<input type="email">
```

存在正则验证

### 3、number

```
<input type="number">
```

只能输入数字

属性值：min、max

### 4、tel

```
<input type="tel">
```

### 5、url

```
<input type="url">
```

存在正则验证

### 6、search

```
<input type="search" results="n">
```

配合results="n"使用

### 7、range

```
<input type="range" min="0" max="100" value="50" tep="5">
```

min 最小

max 最大

value 当前值

step 步数

### 8、date、month、week

date选择日、月、年

month选择月、年

week选择周、年

### 9、time

选择时间（时、分）

### 10、datetime

选择时间、日期、月、年（UTC时间）

### 11、datetime-local

选择时间、日期、月、年（本地时间）

## 四、表单新增属性

### 1、placeholder

占位符

### 2、autofocus

自动聚焦

### 3、required

必填项

### 4、pattern

添加正则验证

# css3选择器及相关属性

## 一、选择器

### 1、基本选择器

通配选择器、元素选择器、ID选择器、类选择器、群组选择器

### 2、层次选择器

#### （1）后代选择器

​	将多个选择器用空格隔开，表示获取到的后一个选择器是前一个的后代。

#### （2）子代选择器

​	将多个选择器用>隔开，表示获取到的后一个选择器是前一个的子代。

#### （3）相邻兄弟选择器

​	E+F，表示获取到F元素紧位于E元素后面。

#### （4）兄弟选择器

​	E~F，表示获取到E元素后面所有的F元素

### 3、动态伪类选择器

:link 鼠标被访问前时添加的样式

:visited 鼠标访问后添加的样式

:hover 鼠标悬停时添加的样式

:active 鼠标点击时添加的样式

:focus 表单元素被聚焦时添加的样式

### 4、目标伪类选择器

：target 当目标被触发时，添加样式

### 5、语言伪类选择器

```
q:lang(no){
	quotes:"（符号）""（符号）";
}
<div><q lang="no">文字</q></div>
```

### 6、UI元素状态伪类选择器

（1）:enabled 可用的表单元素添加样式

（2）:disabled 禁用的表单元素添加样式

（3）:checked 被选中的表单元素添加样式

（4）::selection 被选中的文本内容添加样式

​	  ::-moz-selection 兼容火狐

### 7、否定伪类选择器

:not() 除了括号里的元素以外的所有元素添加样式（冒号前记得加空格）

### 8、结构伪类选择器

（1）E:first-child 满足为其父元素的第一个孩子，而且为E元素

（2）E:last-child 满足为其父元素的最后一个孩子，而且为E元素

（3）E:nth-child(n) 满足为其父元素的第n个孩子，而且为E元素

​	E:nth-child(-n+a) 满足为其父元素的第1-a个孩子，而且为E元素

​	odd、2n-1 第奇数个孩子

​	even、2n 第偶个孩子

（4）E:nth-last-child(n) 满足其父元素的倒数第n个孩子，而且为E元素

（5）E:first-of-type 满足为其父元素第一个E类型的孩子

（6）E:last-of-type 满足为其父元素倒数第一个E类型的孩子

（7）E:nth-of-type(n) 满足为其父元素第n个E类型的孩子

（8）E:nth-last-of-type(n) 满足为其父元素倒数第n个E类型的孩子

（9）E:empty 获取到内容为空（不能为空格）的E元素

（10）E:only-child 获取到其父元素唯一一个孩子，而且为E元素

（11）E:only-child-type 获取到其父元素为一个E元素的孩子

### 9、属性选择器

（1）E[attr] 获取到拥有attr属性的E元素

（2）E[attr="vakue"] 获取attr属性，且属性值为value的E元素被获取到

（3）E[attr^="value"]拥有attr属性，且属性值以value值开头的E元素被获取到

（4）E[attr$="value"]拥有attr属性，且属性值以value值结尾的E元素被获取到

（5）E[attr*="value"]拥有attr属性，且属性值包含value值的E元素被获取到

## 二、文本属性

### 1、文本阴影 text-shadow

text-shadow：x y b color;

x：x-offset水平偏移（右为正）

y：y-offset垂直方向（下为正）

b：blur（模糊区域）

### 2、文本溢出 text-overflow

属性值：clip 默认值

​		ellipsis 以省略号的形式表现

```
需要配合一下三种属性
width、white-space:nowrap;overflow:hidden;
```

### 3、单词换行word-wrap

属性值：break-word; （单词从中间拆开）

解决单词没有空格就不会换行的问题

### 4、自定义字体@font-face

```
@font-face{
	font-family:;src:url();
}
```

### 5、字体图标

图标：精灵图background-position 减少请求次数，减少体积（失真、图片占内存会比文字大）

字体图标：特殊的文字。不会失真，且占空间小。

## 三、背景属性

### 1、背景图片的尺寸 background-size

​	（1）数值、百分比：水平方向	垂直方向;大部分情况会出现图片变形

​	（2）cover：背景图片完全覆盖容器，可能会出现图片丢失

​	（3）contain：容器完全包含背景图片，可能会出现容器留白

轮播图做背景图片：background-position:center center;

​				background-size:cover;

### 2、背景图片的定位区域background-origin

padding-box 从padding左上角开始摆放背景图片。

（背景图片在容器的定位区域中的定位background-position:0 0在padding的左上角）

border-box 从border的左上角开始摆放图片

content-box 从content的左上角开始摆放图片

### 3、背景图片的裁剪background-clip

最终的显示区域

padding-box 背景被裁剪到内边距框。 

content-box 背景被裁剪到内容框。 

border-box 背景被裁剪到边框盒。 

# CSS3新特性

## CSS3颜色

英文单词：red，yellow...

十六进制：#58 ba 58

十进制：rgb(255,0,0)

### 1、rgba

​	r：red	0-255

​	g：green	0-255

​	b：blue		0-255

​	a：alpha 不透明度	0-1

### 2、hsl&hsla

​	h：Hue（色调）：取值为0-360,过渡为：(红橙黄绿青蓝紫红) 

​					0(或360)：红色

​					120：绿色

​					240：蓝色，也可取其他数值来指定颜色。

​	s：Saturation（饱和度）：取值为0.0%-100.0%

​	l：Lightness（亮度）：取值为0.0%-100.0%,50%是平衡值 

​	a：alpha 不透明度（0-1）

### 3、transparent

完全透明

### 关于透明度的补充

​	raba()来控制颜色透明度

​	opactiy:值数字，背景跟字体都会生效

​	transparent不可调节透明度，始终完全透明

## 盒模型

margin->border->padding->content(width+height)

标准盒子模型中（实际宽度），width、height指的是content内容的宽高; 

怪异盒子模型，width、height指的是border+padding+content的宽高； 

### 1、修改盒子模型：box-sizing

属性值：content-box content以内的宽高作为width、height的大小（默认）

​		border-box border以内的宽高作为width、height的大小

### 2、盒子阴影：box-shadow

box-shadow:h-shadow  v-shadow blur apread color inset;

属性值：h-shadow 	horizontal水平

​		v-shadow 	vertical垂直

​		blur			模糊距离

​		spread		阴影大小

​		color		颜色

​		inset 		内部阴影（默认outset外部阴影，可省略）

多阴影：用逗号隔开

## 边框属性

### 1、边框圆角：border-radius

### （1）border-垂直方向-水平方向-radius

border-垂直方向-水平方向-radius：水平方向半径  垂直方向半径

### （2）border-radius

border-radius:水平方向的半径（左上角开始顺时针）/垂直方向半径（左上角开始顺时针）;

对角的值相同可以省略。

常用单位：像素/百分比； 单个圆角的设置： border-top-left-radius

注：值不要超过容器宽高

### 2、边框图片：border-image

border-image:source slice width outset repeat （默认值：none 100% 1 0 stretch） 

#### （1）border-image-source

​	用在边框的图片的路径。

#### （2）border-image-slice

​	切割图片，取值支持：number或percent，其中number是没有单位的。

​	此属性指定（上，右，下，左）边缘的图像向内偏移，拆分为九个区域：四个角，四边和中间。图像中间部分将被丢弃（完全透明的处理），除非填写关键字。 （省略写法：与边框相同）

#### （3）border-image-width

​	图片边框的宽度（可用边框宽度替代），默认为边框宽度

#### （4）border-image-outset

​	设置边框图像与边框（border-image）的距离，默认为0(在边框内显示)，取值支持:number 或percentage其中number是没有单位的，出边框的量。（不可为负值）

​	边框图片向外延伸（不可为负值）解决了边框图片宽度占到内容区域。

#### （5）border-image-repeat

​	图像切割后四边的处理方式。

属性值： stretch(默认)：拉伸。

​		repeat：平铺。

​		round：铺满（类似repeat,完整显示，缩放后的重复）

​		fill  以切割的中间部位作为背景填充进元素content 

应用：按钮自适应背景图片

原理就是九宫格伸缩法：把图片切割成九块，然后把他们应用到边和角。 

## 文本属性

### 1、文本阴影：text-shadow

text-shadow：xOffset yOffset 模糊半径(Blur) 颜色 

### 2、文字描边：text-stroke

text-stroke：宽度 颜色 ;

存在浏览器兼容性，得加前缀

### 3、文字排版：direction

direction：ltr|| rtl;

​	ltr 从左向右排列（默认）

​	rtl 从右向左排列

注：要配合unicode-bidi:bidi-override（重新排版） 一块使用 

### 4、溢出省略：text-overflow

text-overflow: clip||ellipsis;

​	clip 无省略号

​	ellipsis 省略号

注：配合overflow:hidden和white-space:nowrap一块使用 

## 背景

### 1、background-size

background-size: auto|| number || percentage || cover || contain 

​	auto：默认值，保持背景图片的原始高度和宽度;

​	number：可以改变背景图片的大小，有可能让图片变形

​	percentage：此值只能应用在块元素上，所设置百分值将使用背景图片大小根据所在元素的宽度的百分比来计算。

​	cover：容器被图片完全覆盖，但图片可能不能完全显示（常配合background-position：center使用）;

​	contain：将图片完全包裹在容器内，可能容器导致出现空白区域。

注意：只设置一个值时，第二个值相当于auto，会参照第一个参数值进行等比例缩放。 

### 2、background-origin

background-origin: padding-box|border-box|content-box; 

规定 background-position 属性相对于什么位置来定定位。 

​	padding-box 背景图像填充框的相对位置(默认)

​	border-box 背景图像边界框的相对位置

​	content-box 背景图像的相对位置的内容框

注：对背景图片才有效果。

### 3、background-clip

指定背景绘制区域

​	border-box 默认值。背景绘制在边框方框内（剪切成边框方框）。

​	padding-box 背景绘制在衬距方框内（剪切成衬距方框）。

​	content-box 背景绘制在内容方框内（剪切成内容方框）。

## 渐变：gradient

### 1、线性渐变：linear-gradient

（1）-浏览器内核前缀-gradient(linear,起点，终点，from(颜色)，to(颜色))

起点/终点：水平方向   垂直方向;  取值可以是方向，也可以是数字

```
background:-webkit-gradient(linear,left top,right bottom,from(red),to(green));
```

（2）-浏览器内核前缀-gradient(linear,起点，终点，color-stop(开始位置，颜色)[,...])

color-stop的开始位置取值为0-1

```
background:-webkit-gradient(linear,left top,right bottom,color-stop(0.5,red),color-stop(0.8,green));
```

（3）background:linear-gradient(方向||角度，颜色 开始位置[,...]);

```
老版本：
background:-webkit-linear-gradient(-30deg,red 30%,green 50%,blue 80%);
新版本：
background:linear-gradient(120deg,red 30%,green 50%,blue 80%);
```

此时开始位置取值为0-100%

角度单位用deg表示

角度为0默认从下往上排列，为正从左往右，为负从右到左

老版本角度+新版本角度=90度

默认颜色平均分配到容器中。指定某个颜色占比。

### 2、径向渐变：radial-gradient

（1）-浏览器内核前缀-radial-gradient（圆心，颜色  开始位置）

​	圆心取值：数值0-100%、方向

```
background:-webkit-radial-gradient(50% 50%,yellow 20%,pink 50%,green 80%);
```

（2）-浏览器内核前缀-radial-gradient(圆心 形状||大小 颜色 开始位置)

渐变的形状：	ellipse椭圆形（默认），circle表示圆形

渐变的大小，即渐变到哪条边停止，它有四个值。

​		closest-side（最近变）

​		farthest-side：（最远边）

​		closest-corner：（最近角）

​		farthest-corner：（最远边）默认值

```
background:-webkit-radial-gradient(50% 50%,circle closest-side,yellow,green);
```

### 3、重复渐变：repeating-linear（radial）-gradient

```
background:-webkit-repeating-linear-gradient(30deg,red 0,red 5%,black 5%,black 10%);
```

## 浏览器兼容性（前缀）

### 1、浏览器兼容

| 浏览器  | 前缀    | 内核    |
| :------ | ------- | ------- |
| Chromen | -webkit | webkit  |
| Safari  | -webkit | webkit  |
| Opera   | -o      | presto  |
| Firefox | -moz    | gecko   |
| IE      | -ms     | trident |

### 2、平台兼容（iOS+Android）

​		-webkit

工具（插件）：Autoprefixer

## 过渡 transition

时间单位：s、ms

### 1、过渡的属性transition-property

必填

```
transition-property:background;
```

### 2、过渡时间transition-duration

必填

```
transition-duration:3s;
```

### 3、过渡的形式transition-timing-function

```
transition-timing-function:属性值;
```

​	属性值：linear匀速

​			ease慢速进入慢速离开	（默认）

​			ease-in慢速进入

​			ease-out慢速离开

​			ease-in-out慢速进入慢速离开

### 4、过渡的延迟transition-delay

默认值为0

```
transition-delay:3s;
```

### 5、总属性transition

```
transition:transition-property transition-duration transition-timing-function transition-delay;
```

多个可以用逗号隔开

```
transition-property:background,width,height;
transition-duration:2s,4s,6s;
transition-timing-function:linear;
transition-delay:0s;
```

```
transition:all 3s linear;
all:代表全部属性
```

## 2D变换 transform

### 1、translate() 移动变换

移动变换

```
transform:translate（x，y）;
```

x代表水平方向移动的距离，往右为正

y代表垂直方向移动的距离，往下为正

```
transform:translateX(x);
```

水平方向移动

```
transform:translateY(y);
```

垂直方向移动

取值：数值、百分比（当前元素的宽高）

变换的百分值指的是以自己的宽高为基准的。

应用：小图标的居中定位。

### 2、scale() 缩放变换

```
transform:scale(x,y);
```

x代表水平方向的缩放，值代表倍数的意思

y代表垂直方向的缩放，值代表倍数的意思

transform:scaleX(x);

transform:scaleY(y);

注意：缩放的中心点在元素中间

### 3、rotate() 旋转变换

```
transform:rotate(角度);
```

注：正值的为顺时针，旋转的基准点在元素中间。单位deg

### 4、skew() 扭曲变换

```
transform:skew(x,y);
```

x代表x轴旋转的角度，y代表y轴旋转的角度

transform:skewX(x);

transform:skewY(y);

注意：变换的基准点在元素中间。扭曲变换的x轴与y轴与平常看到xy轴是相反的。

### 5、transform-origin 变换的基准点

默认在元素中心

```
transform-origin:0 0;
```

取值：方位、数值、百分比

## 3D变换

### 1、translate3d() 3d移动变换

```
transform:translate3d(x,y,z);
```

z:表示垂直于平面的轴上移动，电脑屏幕往人眼那个方向为正方向。

```
transform:translateZ(z);
```

### 2、transform-style 规定变换的样式

```
transform-style:flag;
```

属性值：flag平面（默认）

​		preserve-3d	保持3d变换

必须设置，而且子元素有变换才能看到效果

### 3、perspective 景深

设置观察的距离，透视点（眼睛所在的位置），以3d效果呈现

```
perspective:;
```

### 4、rotate3d()

```
transform:rotate3d(x,y,z,角度);
transform:rotate3d(0,1,1,30deg);
transform:rotate3d(rotateX(角度) rotateY(角度) rotateZ(角度));
```

此时x，y，z取值为或1，0代表不选择，1代表旋转

```
transform:rotateX(角度)
transform:rotateY(角度)
transform:rotateZ(角度)
```

以x/y/z轴为基准旋转，左手定律，大拇指指向轴的正方向，手指望去的方向为旋转的正方向。

### 5、perspective-origin

观察的基准点

```
perspective-origin:left top;
```

取值可为方位，数值，百分比

当设置单个值的时候，第二个值默认为center

默认为中心。

## 关键帧动画 animation

### 1、自定义动画

（1）通过@keyframs指定动画序列

```
@keyframs change{
    
}
```

（2）通过百分比将动画序列分割成多个节点

（3）在各节点中分别定义各属性

```
@keyframs change{
    0%{}
    ...
    100%{}
}
```

（4）通过animation属性将动画应用于相应元素

```
div{
    animation:change 3s;
}
```

### 2、animation属性

（1）animation-name 动画名字（必填）

（2）animation-duration 动画播放时间（必填）

（3）animation-timing-function 动画播放形式 

​	属性值： linear匀速	

​			ease慢速进入慢速离开	（默认）

​			ease-in慢速进入

​			ease-out慢速离开

​			ease-in-out慢速进入慢速离开

​			steps(n) n为每个百分比跳的次数

（4）animation-delay 动画播放的延迟

（5）animation-iteration-count 动画播放的次数

​	属性值： infinite（无限次播放）

​			次数

（6）animation-direction 动画是否轮流反向播放

​	属性值：normal（默认） 

​			alternate（交替播放）

​			reverse（反向播放）

​			alternate-reverse（轮流反向）

（7）animation-fill-mode 动画完成的模式

​	属性值： forwards 停留在结束状态

（8）总属性 animation

```
animation:<name> <duration> [timing-function] [delay] [iteration-count] [direction]
```

# 伸缩布局盒模型（弹性盒模型）

伸缩布局盒模型，用来提供一个更有效的方式制定、调整和分布一个容器里的子项目布局，即使他们的大小是未知或者动态的。

主要思想是让容器有能力让其子项目能够改变其宽度、高度（甚至顺序），以最佳的方式填充可用空间（主要是为了适应所有类型的显示设备和屏幕大小）。flex容器会使子项目扩展来填充可用空间，或缩小他们以防止溢出容器。

## 一、容器（父元素）

```
display:flex;
```

父元素设置成弹性盒，规定子项目在父元素主轴方向一行显示，侧轴方向会默认拉伸。

### 1、flex-direction 主轴方向 

​	属性值： row 从左到右（ 默认）

​			row-reverse 从右到左

​			column 从上到下

​			column-reverse 从下到上

### 2、flex-wrap 伸缩换行

​	属性值：nowrap 默认不换行

​			wrap 换行

### 3、flex-flow 伸缩流方向及换行

​	flex-flow:flex-direction||flex-wrap;

### 4、justify-content 主轴对齐

设置子项目在容器主轴方向的对齐方式

​	属性值：flex-start 默认在主轴起点对齐

​			flex-end 主轴方向终点位置对齐

​			center 主轴居中对齐

​			space-between 将空白区域平分在子项目之间

​			space-around 将空白区域环绕在子项目之间 

### 5、align-items 交叉轴对齐

设置子项目在其所在行的交叉轴对齐方式（单行）

​	属性值：	stretch  默认拉伸

​			flex-start 子项目在其所在行的起始位置摆放

​			center  居中

​			baseline  基线对齐

### 6、align-content 堆栈伸缩行

设置子项目在交叉轴方向的对齐方式

​	属性值：flex-start 默认在交叉起点对齐

​			flex-end 交叉轴方向终点位置对齐

​			center 交叉轴居中对齐

​			space-between 将空白区域平分在子项目之间

​			space-around 将空白区域环绕在子项目之间 

## 二、子项目

### 1、flex 分配空间

设置子项目在父元素主轴方向的比份

设置或检索弹性盒模型对象的子元素如何分配空间。 

flex 属性是 flex-grow、flex-shrink 和 flex-basis 属性的简写属性。 	

### 2、align-self 交叉轴对齐方式

设置单个子项目在其所在行的交叉轴对齐方式

​	属性值：	stretch  默认拉伸

​			flex-start 子项目在其所在行的起始位置摆放

​			center  居中

​			baseline  基线对齐

### 3、order 改变顺序

设置子项目的顺序

有order属性的元素排在order属性的元素后面

数字越小的在越前面

# 多列布局

## 1、column-width

最小的宽度

## 2、column-count

最多的列数

## 3、column-gap

列间距

## 4、column-rule

列分割线

```
column-rule：1px solid #ccc; 
```

## 5、column-span

横跨的列数

​	属性值：none 不跨列

​			all  跨所有

# 媒体查询

​	许多智能手机都使用了一个比实际屏幕尺寸大很多的虚拟可视区域viewpoint(布局视口)，主要目的就是让页面在智能手机端阅读时不会因为实际可视区域变形。所以你看到的页面还是普通样式，即一个全局缩小后的页面。为了让智能手机能根据媒体查询匹配对应样式，让页面在智能手机中正常显示，特意添加了一个meta标签。这个标签的主要作用就是让智能手机浏览页面时能进行优化，并且可以自定义界面可视区域的尺寸和缩放级别。

## meta语句

如何识别手机尺寸通过设置meta语句：

```
<meta name="viewport" content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no" />
```

width	      可视区域的宽度；

height           可视区域的高度；

device-width		设备屏幕分辨率的宽度值

initial-scale  	初始的缩放比例（0-10.0），取值为1时页面按实际尺寸显示，无任何缩放

minimum-scale 	允许用户缩放到的最小比例 

maximum-scale 	允许用户缩放到的最大比例

user-scalable 	设定用户是否可以缩放（yes/no）

可以写成：

```
<meta name="viewport" content="width=device-width,initial-scale=1.0" />
```

## 常见设备类型(media type)

all			所有设备

screen 		电脑显示器

print		打印用纸或打印预览视图

handheld	便携设备

tv			电视机类型的设备

speech		语意和音频盒成器

braille		盲人用点字法触觉回馈设备

embossed	盲文打印机

projection	各种投影设备

tty			使用固定密度字母栅格的媒介，比如电传打字机和终端

## 媒体类型引用方法

### 1、link方式

```
<link rel="stylesheet" href="css/wide.css" media="screen and (min-width:641px)" />

<link rel="stylesheet" href="css/mobile.css" media="screen and (min-width:320px) and (max-width:640px)" />
```

### 2、@import方式

```
<style>
@import url(style.css) screen and (min-width:641px);
</style>

<style>
@import url(style.css) print   /*print:打印预览视图*/
</style>
```

### 3、@media方式

#### （1）在样式文件中引用媒体类型

```
@media all and (min-width:600px) and (max-width:800px) {
	h1 {
		background: red;
	}
}
```

#### （2）写在内部样式中

```
<head>
<style type="text/css">	
	@media only screen and (min-width:600px) and (max-width:800px) {
		h1 {
			background: red;
		}
	}
	/*设备横向放置是*/
	@media (orientation: landscape) {
		h1 {
			background: yellow;
		}
	}
</style>
</head>
```

# 移动端布局

## 1、弹性布局（100%布局）

好处：充分发挥大手机的优势——显示内容越多.

缺点：屏幕过大，间距过大，比例失调。

特点：

​	顶部与底部的bar不管分辨率怎么变，它的高度和位置都不变；

​	中间每条招聘信息不管分辨率怎么变，图标等信息都位于条目的左边，薪资都位于右边。

```
<script type="text/javascript">
        // 把屏幕的倍率缩小到N分之一（N是window.devicePixelRatio）
        var scale = 1/window.devicePixelRatio;
        var mstr = 'initial-scale='+ scale +', maximum-scale='+ scale +', minimum-scale='+ scale +', user-scalable=no';
        document.getElementById("vp").content = mstr;
</script>
```

```
1. 新建html及对应的css 
2. 引入meta:vp。
3.引入设备缩放比代码(后三句)，将id名添加到meta标签
4.一般拿到640px的设计稿，在iphone5开发。
		 750px的设计稿，在iphone6开发。
5.做页面，量出来多少写多少。
	（1）整个盒子高度100%，设置成弹性盒，主轴垂直向下
	（2）main部分高度不确定，所以剩余高度都给main，flex:1;由于main内容很多，所以还要添加overflow-x:hidden;从而overflow-y:auto;（可以省略），这一部分可以垂直滚动。
```

## 2、等比缩放布局（rem布局）

 尽量保持不同设备显示效果一致

```
<script type="text/javascript">
	// 把尺寸放大N倍（N是window.devicePixelRatio）
	var wd = document.documentElement.clientWidth*window.devicePixelRatio/10;
	//物理像素*设备像素比=真实像素
	document.getElementsByTagName("html")[0].style.fontSize = wd + "px";
	// 把屏幕的倍率缩小到N分之一（N是window.devicePixelRatio）
	var scale = 1/window.devicePixelRatio;
	var mstr = 'initial-scale='+ scale +', maximum-scale='+ scale +', minimum-scale='+ scale +', user-scalable=no';
	document.getElementById("vp").content = mstr;
</script>
```

### 视口设置

```
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"/>
```

原理：在html上根据不同分辨率设置不同font-size，通过js计算出来

页面里除了font-size之外的其它css尺寸都使用了rem作为单位

正文的font-size需要额外的媒介查询，并且不使用rem

devicePixelRatio设备像素比   真实像素640/物理像素320(固定)
视网膜屏幕

动态设置viewport的scale，淘宝触屏版首页布局的前提是viewport的scale根据devicePixelRatio动态设置：在devicePixelRatio为1的时候，scale为1；在devicePixelRatio为2的时候，scale为0.5；在devicePixelRatio为3的时候，scale为0.3333

动态计算html的font-size：font-size = deviceWidth / 10

布局的时候，各元素的css尺寸=设计稿标注尺寸/设计稿横向分辨率/10

每个元素的font-size可能需要额外的媒介查询，并且font-size不使用rem

注：

​	1.百分比布局（量到多少写多少，js代码删掉前两句，记得meta加id）

​	2.复制一份百分比布局文件，在复制的文件夹上面改成rem布局（js代码。设计稿640px，说明你在iphone5上开发，插件px-rem：64；设计稿750px，说明在iphone6开发，px-rem75）

​	3.rem概念理解:以根部字体大小为基准。

每个元素的font-size可能需要额外的媒介查询