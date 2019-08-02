# JavaScript基础语法

## 一、语言介绍

### JavaScript的诞生

JavaScript 诞生于 1995 年。由Netscape(网景公司)的程序员Brendan Eich(布兰登)与Sun公司联手开发一门脚本语言, 最初名字叫做Mocha，1995年9月改为LiveScript。12月，Netscape公司与Sun公司（Java语言的发明者）达成协议，后者允许将这种语言叫做JavaScript。这样一来，Netscape公司可以借助Java语言的声势。 

1996年3月， Netscape公司的浏览器Navigator2.0浏览器正式内置了JavaScript脚本语言. 此后其他主流浏览器逐渐开始支持JavaScript. 

### js版本

JavaScript这种语言的基本语法结构是由ECMAScript来标准化的, 所以我们说的JavaScript版本一般指的是ECMAScript版本. 

​	1997年7月，ECMAScript 1.0发布。

​	1998年6月，ECMAScript 2.0版发布。

​	1999年12月，ECMAScript 3.0版发布。

​	2007年10月，ECMAScript 4.0版草案想要提交ECMA组织, 但由于4.0版的目标过于激进, 改动太大, 并且微软,谷歌等大公司极力反对；一直到2008年7月ECMA开会决定，中止ECMAScript 4.0的开发（即废除了这个版本）

​	2009年12月，ECMAScript 5.0版正式发布

​	2011年6月，ECMAscript 5.1版发布

​	2015年6月，ECMAScript 6正式发布，并且更名为“ECMAScript 2015”。

### js的优势

目前苹果公司的Safari, 谷歌的Chrome,微软的IE等几乎全部浏览器都支持JavaScript, 基于JavaScript开发的库和框架数不胜数, 例如: jQuery,Angular, React等…

JavaScript将在前端和服务器端(Node.js)有更好的发展

### js用途

它的主要目的是，验证发往服务器端的数据、增加 Web互动、加强用户体验度等。可用于开发网站、游戏、移动端app等

### js语言的组成

javascript = ECMAScript + BOM + DOM

1. 核心(ECMAScript)
2. 浏览器对象模型(BOM)
3. 文档对象模型(DOM)

### JS和H5的关系

h5全称html5,不是单纯的html的第5个版本，而是一项最新的web标准，是html、css、javascript等技术的集合

## 二、语法

### js代码的编写位置

1、script标签

```
<script type="text/javscript">
	js内容
</script>
```

2、js文件

独立的js文件需要引入页面才能执行 

```
<script type="text/javascript" src="js/common.js"><script>
```

3、script标签属性 

​	type：类型

​	src：js文件路径

注意：使用src属性后，忽略内部代码

### 变量的定义

变量：数据的容器

#### 变量声明

声明变量名

```
// var 变量名;
var num;
```

声明变量并赋值

```
var cup = 'shui';
```

声明多个变量

```
var a,b,c;
var a = 10,b = 20,c = 30;
```

### JS代码规范

#### 命名规范

1、变量名必须是数字，字母，下划线_和美元符$组成；

2、第一个字符不能为数字

3、不能使用关键字或保留字

```
var num1 = 10;
var 10cup = 'shui'; //错误，使用数字开头
var $10 = 10;
var _a = 10;
```

#### 代码可读写

1、标识符区分大小写。如：age和Age是不同的变量。但强烈不建议用同一个单词的大小写区分两个变量。

2、变量命名尽量遵守驼峰原则。如：myStudentScore

3、变量命名尽量见名知意

4、保持代码缩放

5、JS语法的末尾尽量写上分号;

6、运算符两边都留一个空格。如：var n = 1 + 2;

7、注释

### JS数据类型

#### 基本数据类型

##### Number数值

###### 1、NaN

特殊的值，即非数值(Not a Number)。数学运算无法得到数字时，就会返回NaN 

​	不代表任何值，也不等于任何值，甚至自己都不等于自己

​	任何数据与它运算都返回NaN

###### 2、isNaN(a)

isNaN(a)：用来判断a到底是不是非数字,返回布尔值

ture是非数字

false是数字

##### String字符串

带引号的（单引，双引）

```
var cup = "shui";
var cup = 'shui';
```

##### Boolean布尔值

true		真/是/1

false	假/否/0

#### 引用数据类型

##### Array：数组

##### Object：对象

#### 特殊数据类型

##### Null

Null 类型是一个只有一个值的数据类型，即特殊的值 null。它表示一个空对象引用(指针)，而 typeof 操作符检测 null 会返回 object 

##### Undefined

Undefined类型只有一个值，即特殊的 undefined，在使用 var 声明变量，但没有对其初始化时，这个变量的值就是 undefined 

​	与not defined的区别(not defined:未声明)

#### 数据类型转换

##### 显性转换

（主动转换：写代码实现）

```
var num1 = 100;
var num2 = "20";
var res1 = num1 + Number(num2);
```

##### 隐式转换

（被动转换：内部自己转换）

如果运算不能进行下去，内部就会尝试进行数据类型的转换 支持隐式转换的运算：逻辑运算、关系运算、算术运算 

#### 数据类型判断

##### typeof

```
typeof 'html5'; //=>string
typeof 100; //=>number
typeof true //=>boolean
typeof null //=>object
```

## 三、运算

### 算术运算

+, -, *, /, %:加,减,乘,除,取余(取模) 

#### toFixed(num)

在数字后面调用，num为小数位，有四舍五入的功能，得到一个字符串

#### parseInt()

取整:获取到第一个不为数字的字符为止

#### parseFloat()

取小数

**+ 的特殊用法：字符串拼接** 

+号两侧只要有一个是字符串则为字符串拼接 

### 赋值运算

#### = 

```
var num1=10;//表示把10赋值给num1变量
```

#### +=

在原来的内容基础上追加内容 

```
str += 'test' <==> str = str + 'test'
```

#### -=

```
var n=10; n -= 2 <==> n = n - 2
```

#### *=,/=,%=

### 关系运算（返回布尔值）

==(等于), !=(不等于)

<(小于)、>(大于)、<=(小于等于)、>=(大于等于)

===、恒等于/全等于，比较的时候要求值和类型都相等（不会进行类型隐式转换）

!==、不全等于 

关系运算符的比较规则:  

1. 数字和数字比较, 直接比较大小 
2. 数字和字符串比较, 字符串转换为数字后再比较 
3. 字符串和字符串比较, 进行字符的ASCII码值比较 

### 逻辑运算（返回布尔值）

1、&&: 逻辑与 

注：&&比||优先级高 

2、||：逻辑或

3、!：逻辑非 

```
!true //=> false
!false //=> true
```

### 一元运算

#### ++

自增1（在原来的数值基础上加1）

#### – –

自减1（在原来的数值基础上加1）

前置型是先计算，再赋值；后置型是先赋值，再计算。 

前置： 

```
var num = 10;
++num;
--num;
```

返回值：返回值是减1（加1）之后的值 

```
var i=1;
console.log(i);

var a=++i;
console.log(i); //输出2
console.log(a); //输出2
//先自身加1，再赋值给了a
```

后置： 

```
var num = 10;
num++;
num--;
```

返回值：返回值是没减1（加1）之前的值 

```
var i=1;
console.log(i); // 输出1
	
var a=i++;
console.log(i); //输出2
console.log(a); //输出1
//先赋值给了a，然后再自身加1
```

### 术语

表达式的概念: 

​	由运算符和操作数（变量或常量）组成的式子

​	算术运算符组成的式子叫算术表达式

​	关系运算符组成的式子叫关系表达式或者条件表达式

​	逻辑运算符组成的式子叫做逻辑表达式

```
如：2+3；a+5；c>3; a&&b等 
```

返回值：运算后得到的值

### 程序的三大流程控制

我们的计算机在执行一个程序的时候，最基本的方式是一条语句接一条语句的执行。但不可能所有的问题都能用顺序执行方式就能解决，总会有一些跳转。采用结构化的程序设计，可以大大提高开发程序的速度、提高程序的可读性、程序运行的速度和效率 

顺序：从上朝下执行的代码就是顺序

分支(选择)：根据不同的情况，执行对应代码

循环：重复做一件事情

# 语句

## 一、条件判断语句

### if语句

#### 单分支

```
if(条件){
	//条件成立（true）时，执行这里的代码，否则不执行
}
```

#### 双分支

```
if(条件){
	语句1
	//条件成立（true）时，执行这里的代码，忽略以下代码
}else{
    语句2
    //条件不成立（返回false）时，执行这里代码
}
```

#### 多分支

```
if(条件1){
    条件1成立（true）时，执行这里的代码，忽略以下代码
}else if(条件2){
	条件2成立（true）时，执行这里的代码，忽略以下代码
}
...
else{
    以上条件都不成立（都返回false）时，执行这里的代码
}
```

### 三元运算

格式：条件 ? 条件成立代码 : 条件不成立代码 

```
var a=20;
var b = 50;
var sum = a>b ? a-b : a+b;
```

简单的if双分语句可用三元运算替代

运算：算术运算、关系运算、赋值运算、逻辑运算、一元运算、三元运算

### switch语句

执行方式：代码从符合条件的那条case开始执行，直到结束或者遇到break

```
switch(值) {
    case value1: //要求value1与值恒等
        //如果表达式的值恒等于value1，代码从这里开始执行
        break;
    case value2:
        //如果表达式的值恒等于value2，代码从这里开始执行
        break;
    case value3: 
        //如果表达式的值恒等于value3，代码从这里开始执行
        break;
    case value4: 
        //如果表达式的值恒等于value4，代码从这里开始执行
        break;
    default: 
        如果以上条件都不成立，默认执行这里的代码
}
```

​	switch语句在比较值时使用的是全等操作符，因此不会发生类型转换

​	case: 当符合条件时，会从符合条件的那一条case语句开始，依次顺序向下执行，直到结束或遇到break

​	break: 跳出switch语句

​	default: 当所有的case都不满足的情况下会执行defalut下面的语句

## 二、循环语句

循环就是重复做一件事，在JS中指的是循环执行某部分代码

### while循环

```
while(条件){
	条件成立执行这里的代码
	这里的代码执行完毕，继续判断条件是否成立
	
	避免死循环：让条件不成立
	变量更新：往条件不成立的方向改变
}
```

死循环：尽量避免死循环（重要）

循环语句组成部分：变量初始化、条件判断、变量更新

理解：循环语句的执行过程

### do while循环

```
do{
	//先执行1次这里的代码（不管条件是否成立）
	//在进行条件判断，如果成立再执行这里的代码
}while(条件);
```

### for循环

```
for(变量初始化;条件判断;变量更新){
   	//1、变量初始化
   	//2、进入条件判断，成立执行这里的代码
   	//3、变量更新
   	//4、进入第2步
}
```

for：知道循环次数，用for

## 三、循环跳转

### break

退出当前整个循环

只能在循环语句中使用

循环体中位于break后的语句不会被执行

### continue

跳过本次循环，继续下一次循环

只能在循环语句中使用

循环体中位于continue后的语句不会被执行

### label

给循环代码添加标识 

```
outer:for(var x=0;x<5;x++){
	inner:for(var y=0;y<5;y++){
		// 跳出循环
		if(x === 2){
			// break;//跳出内循环（y所在的循环）
			break outer;
		}
		console.log(x,y);
	}
}
```

## 四、嵌套循环

```
for(var i=0;i<10;i++){
	for(var j=0;j<10;j++){
		console.log(i,j);
    }
}
```

# 函数 Function

## 一、了解函数

函数就是把特定功能的代码抽取出来并进行封装，用来重复执行一些功能，并起个名字（函数名）。函数对任何语言来说都是一个核心的概念。通过函数可以封装任意多条语句，而且可以在任何地方、任何时候调用执行 

好处：函数可以重复执行某一部分代码（通过函数名调用）

​	   使程序变得更简短而清晰

​	    有利于程序维护

什么时候需要函数

​	当相同的代码出现多次

​	当需要提取公共代码时

## 二、函数的定义

### 1、声明式

利用关键字function定义

```
function show(){
	
}
```

函数的声明会提前 ==> 解析器会率先读取函数声明，并使其在执行任何代码之前可用（可以访问）

### 2、赋值式

与变量声明一致，给变量赋值一个匿名函数

```
var show = function(){

}
```

匿名函数：没有名字的函数

## 三、函数的执行

### 1、手动执行（主动）

主动写一句代码执行，立即执行

```
函数名();
```

### 2、事件驱动（被动）

#### 第一种

```
<button id="btn">事件驱动</button>
<script>
	var btn = docuement.getElementById('btn');
	btn.onclick = show;
</script>
```

#### 第二种

```
<button id="btn">事件驱动</button>
<script>
	var btn = docuement.getElementById('btn');
	btn.onclick = function(){
        
	}
</script>
```

### 常用事件

onclick：点击事件

ondblclick：双击事件

onmouseover：鼠标移入事件

onmouseout：鼠标移开事件

onchange：内容改变事件（一般用于表单元素，修改后并失去焦点后执行）

onkeyup：键盘按键弹起事件

oninput：修改时执行

### 内置函数

js内部已经定义好的函数（直接调用，在任意位置使用）

## 四、声明提前

函数的声明提前

变量声明提前：声明但没有赋值的变量默认为undefined

## 五、浏览器如何执行js代码

1）声明提前（保存声明）：把变量声明，函数声明保存起来

​	提前到当前作用域

2）顺序：从上往下

## 六、作用域

变量的使用范围

### 全局作用域

在函数外

#### 全局变量

在全局作用域下声明的变量

### 局部作用域

在函数内

#### 局部变量

在局部作用域下声明的变量

### 变量访问规则

就近原则

当前作用域 > 上级作用 >... >全局作用域

如在某一作用域中作用，则停止查找

如到全局作用域还没找到，则报xxx is not defined

### 作用域链

当前作用域到全局作用域的链条

## 七、函数的参数

### 形参

函数定义时的参数

形参就是局部变量

### 实参

函数执行时的参数

```
function sum(a,b,c){
    //a为形参
    //内部自动声明局部变量 var a = 5
}
sum(5,10,15); //5为实参 10为实参 15为实参
sum(10,20);//实参数量小于形参：多余的形参为undefiend
sum(1,2,3,4,5,6,7,8)//实参数量大于形参：多余的实参被忽略
```

注：形参与实参的数量可以不同

### arguments

```
格式（数组）：[10,5]    
索引值index：从0开始的正整数
length：实参数量
获取其中某一个：arguments[index]
```

保存实参信息

只能在函数内使用

### 回调函数

引用数据类型与基本数据类型的传参（引用传递与值传递） 

函数作为参数传递

## 八、函数返回值

运算后得到的值

终止函数的执行（return后的代码不会被执行）

### return 

默认：返回undefined

后面带值：把值返回到函数执行的地方

函数内->函数外

## 九、函数中的this

函数中的this是一个关键字，表示当前对象（而当前对象是谁，取决于这个函数的执行环境）

### 指向

手动执行：window（全局作用域）

事件驱动：绑定事件的元素

## 十、递归

函数可以自己调用自己, 成为函数的递归调用 

递归函数中必须有跳出条件

递归调用的过程:

1. 首先去找临界值，即无需计算，获得的值(一般是返回该值)。
2. 找这一次和上一次的关系(一般从后往前找)
3. 假设当前函数已经可以使用，调用自身计算上一次的运行结果，再写出这次的运行结果。

# 数组 Array

## 一、什么叫数组

一系列数据的集合，每一项可以保存任何类型的数据，称为数组的元素，每个元素之间用逗号隔开 

## 二、数据定义方式

### 1、字面量

简单、直观

```
var arr = [];
```

### 2、构造函数

new 数据类型

```
var arr = new Array();
```

## 三、数组的属性

### length

保存数组元素的数量（根据数组元素的数量自动改变）

## 四、数组操作

### 增

添加数组元素

push();

unshift();

```
var arr = [10,20];
arr[2] = 30;
```

### 删

删除现有数组元素

pop()

shift()

### 改

修改已经存在的数组元素

```
var arr = [10,20];
arr[0] = 11;
```

### 查

获取对应的数组元素，不存在（超出索引值）会得到undefined

```
var arr = [10,20];
arr[0];
```

### 遍历

把所有数组元素查一遍

for循环

```
for(var i=0;i<arr.length;i++){
    console.log(arr[i]);
}
```

## 五、数组的方法

### 删除

#### pop()

删除最后一个

```
arr.pop();
```

#### shift()

删除第一个

```
arr.shift();
```

### 添加

#### push()

在最后添加

```
arr.push();
```

#### unshift()

在开始添加

```
arr.unshift();
```

### 删除/增加/替换

在任意位置进行

#### splice()

splice(idx,qty,...items)

值：start：起始索引位置

​	qty：要删除的数量

​	items：插入的元素（可以是多个）

**该方法会改变原数组**

```
arr = [a,b,c]
//在2的位置添加：d，0代表数量
arr.splice(2,0,d);
```

```
arr = [a,b,c,d,e]
//在索引值为4的值删除,1代表数量
arr.splice(4,1);
```

```
arr = [a,b,c,d,e,g]
// 替换：g替换成f
// 先删除，后添加,1代表数量
arr.splice(5,1,f);
```

### 倒序

#### reverse()

将数组中的元素颠倒顺序，返回逆序后的数组

```
var arr = [10,20,30];
arr.reverse();
```

### 排序

#### sort()

将数组中的元素排序，并返回排序后的数组 

默认以字符串的排列方式（转换成ASCII码进行对比） 

```
arr.sort();
//要实现数字排序，得使用一个排序函数
function sortNumber(a,b){
	return a - b;
}
arr.sort(sortNumber);
```

### 截取

#### slice()

返回数组的片段或子数组，从start开始到end(不包括end所对应的元素) 

如果省略end参数，则截取到数组的最后一项 支持负数 

**该方法不会改变原数组，而是返回一个子数组** 

```
var arr = [1,2,3,4,5,6]
//值为单个的时候默认截取到最后
var newArr = arr.slice(1);

//值为两个时，第一个代表从索引值第一个开始截取，第二个代表截取到索引值第几个，但不包括
var newArr = arr.slice(1,4);
```

### 合并数组

#### concat()

返回一个新数组，这个新数组是由调用这个方法的数组和参数组成 

参数可为多个

```
var arr1 = [12,34,5,2];
var arr2 = [12,52,21];
arr1.concat(arr2);
```

### 返回一个字符串

#### join()

返回字符串值，其中包含了连接到一起的数组的所有元素 

```
//separator为分隔符，默认为逗号
join(separator);
```

## 六、数组排序

### 冒泡排序法

（先排大的）

当前元素跟下个元素对比

把最大的逐个往后排列

### 选择排序法

（先排小的）

当前元素分别跟后面的元素对比

把最小的逐个往前排序

### 快速排序法

利用递归实现

取基准值，然后定义左右两个空数组，小于基准值的放左边，大于基准值的放右边，然后使用递归

## 七、值类型与引用类型的区别

内存中的状态

栈：变量、简单的数据类型

堆：复杂的数据类型

### 数组复制与传输

​	如何复制数组

​	把数组作为函数的参数

方法一：定义一个空数组，然后把元素逐个添加到新数组里面

```
var arr = [1,2,3,4,5];
var newArr = [];
for(var i=0;i<arr.length;i++){
	newArr[i]=arr[i];
	//newArr.push(arr[i]);
}
```

方法二：用截取slice()方法截取

```
var arr = [1,2,3,4,5];
var newArr = arr.slice(0);
```

### 多维数组(数组里面包含数组)

```
var arr = [1,2,'html5',[3,4,'css3'],[5,6,'javascript']]
arr[3][2]; //=>'css3'
```

# 对象 Object

对象和数组有很多类似的地方

经常配合使用达到完美的效果

## 一、对象的定义

### 字面量

空对象

```
var obj = {};
```

### 构造函数

```
var obj = new Object();
```

## 二、结构

{属性：属性值}

属性之间用逗号隔开，属性值可以为任意数值类型

属性类型为（String）

属性值（任意数据类型）

## 三、操作

### 增

添加属性和属性值

```
1、创建时添加
var obj = {name:'xiaoming',age:18};
```

```
2、创建后添加
obj['isDanshen'] = false;
```

```
3、创建后以.的形式添加
obj.isMarry = false;
```

### 删

删除已有属性

```
//删除isDanshen属性
delete obj.isDanshen;
```

### 改

修改已有属性的属性值

```
//修改isMarry属性为false;
obj.isMarry = false;
```

### 查

根据属性名读取属性值

如果读取一个不存在的属性，返回undefined 

```
//以.的方式读取
obj.name;
```

### 遍历：for...in

```
for(var key in obj){
    //遍历所有属性，并把属性名分别赋值给key变量
    //根据key获取对应属性值
    console.log(key,obj[key]);
}
```

.与[]：能用点语法的肯定能用方括号，反之不成立

## 四、对象的补充

### 方法

#### this指向

​	手动执行：window

​	事件驱动：绑定事件的元素

​	对象方法：指向对象

#### 判断对象是否包含某个属性

​	不存在得到undefined

# ECMAScript 5

提供一些有用的方法，来简化我们的操作

## 一、Array新增方法

### 1、静态方法

#### Array.isArray()

判断是否为数组，返回true/false

```
var arr = [1,2,3,4,5];
Array.isArray(arr);//true
```

### 2、索引方法

#### indexOf/lastIndexOf

```
indexOf/lastIndexOf(keyword [,startIndex]);

keyword: 要查找的项，
startIndex：查找起点位置的索引，该参数可选，默认0
```

用途：判断数组中是否存在某个值，如果数组中存在，会返回元素的索引值（大于等于0），如果不存在会返回-1

```
arr.indexOf(keyword)!=-1;
arr.indexOf(keyword)>=0;
```

### 3、迭代（遍历）方法

方法会把数组元素遍历一遍，**只能遍历数组**

#### forEach(fn)

fn：item	数组元素

​	idx		索引值

​	arr		数组本身

**无返回值**

用来替代for循环，比for循环更简单（但是不能随意break）

遍历方法，for循环没有太大区别，比for循环方便。

```
var arr = ['a','b','c','d'];
arr.forEach(function(item,idx,arr){
    //这里的代码会执行多少次：数组的长度
    //每次传入的参数：item，idx，arr
    console.log(item,idx);
});
```

#### map(fn)

fn：item	数组元素

​	idx		索引值

​	arr		数组本身

返回fn返回值组成的数组

```
var arr = [1,2,3,4];
var res = arr.map(function(item,idx){
   return item*idx;
});
console.log(res);//0,2,6,12
```

#### filter(fn)

fn：item	数组元素

​	idx		索引值

​	arr		数组本身

得到执行fn后返回true时对应的数组元素，利用这个方法可对数组元素进行过滤筛选 

返回true，数组元素保留下来。返回false，去掉数组元素。

```
var arr = [10,12,34,51,10,23,11,53,12];
var res = arr.filter(function(item,idx){
	//判断大于10的数字，然后返回到数组 
	//return item>10;
	if(item>10){
		return true;
	}
});
console.log(res);//res = [12,34,51,23,11,53,12]
```

#### some(fn)

fn：item	数组元素

​	idx		索引值

​	arr		数组本身

**该方法对数组中的每一项运行给定函数，如果该函数对任何一项返回 true，则返回true。** 

返回Boolean

```
var arr = [5,10,20,30];
var res = arr.some(function(item,idx){
	//只要有一个元素满足条件就会返回true
	//只要有一个元素满足条件之后就会结束循环
    if(item>5){
        return true;
    }
});
console.log(res);//true
```

#### every(fn)

fn：item	数组元素

​	idx		索引值

​	arr		数组本身

**该方法对数组中的每一项运行给定函数，如果该函数对每一项都返回 true，则返回true。**

返回Boolean

```
var arr = [5,10,20,30];
var res = arr.every(function(item,idx){
	//当全部元素都满足条件是才会返回true
	//当有一个元素不满足条件就退出循环
    if(item>0){
        return true;
    }
});
console.log(res);//true
```

### 4、归并方法

#### reduce(fn,initVal)、reduceRight(fn,initVal)

fn：prev：前一次返回值

​	item：当前值

​	idx：索引值

​	arr：当前数组， 函数需要返回一个值，这个值会在下一次迭代中作为prev的值

initVal：迭代初始值（可选），如果缺省，prev的值为数组第一项

​		给定初始值，item从数组第一项开始

# 字符串 String

## 一、了解字符串

字符串就是一串字符，由双（单）引号括起来。 

## 二、定义

### 字面量

```
var str = 'aaa';
```

### 构造函数

```
var str = new String(aaa);
```

## 三、属性

### length

字符串的长度（只读），数组可读写。

```
var str = 'aaa';
str.length;
```

## 四、读取某个字符

### [] ES5实现

用索引值读取（只读），ie9以下不支持

```
var str = 'abc';
str[2];//c
```

### charAt(idx)

```
var str = 'abc';
str.charAt(2);//c
```

## 五、字符串的操作

### 查找替换

#### indexOf/lastIndexOf()

用法与数组的一样

```
var str = 'abcdefg';
str.indexOf('a');//0
```

#### search()

支持正则表达式

#### replace()

replace(str|regExp,’‘) 替换字符串 

这里的替换只能执行一次，不能够进行全局匹配，如果需要全局匹配，则应使用正则表达式 

### 截取

#### slice(start,end)

end支持负数，截取不包括end的数

用法跟数组相同

```
var str = 'abcdef';
str.slice(0,3);//abc
```

#### substring(start,end)

end不支持负数，截取不包括end的数

```
var str = 'abcdef';
str.substring(1,3);//bc
```

#### substr(start,length)

start可为负数，length为截取数量

```
var str = 'abcdefg';
str.substr(0,2);//ab
```

### 分割

拆分：String ->Array

#### split(分隔符)

根据分割字符，把字符串拆分成**数组** 

```
var str = 'a,b,c,d';
str.split(',');//[a,b,c,d];
```

### 大小写转换

#### toLowerCase()

转换成小写

```
var name = 'Who Are You';
name.toLowerCase();//who are you 
```

#### toUpperCase()

转换成大写

```
var name = 'who are you';
name.toLowerCase();// Who Are You
```

### ECMAscript5新增

str[3]//通过下标获取

trim()：删除前后所有空格，返回新的字符串

## 六、ASCII码和字符集

### charCodeAt()

```
charCodeAt(3);
//获取下标为3的字符的ASCII(American Standard Code for * Information Interchange) == > unicode编码
```

### String.fromCharCode()

```
String.fromCharCode(94);
//编码转换成字符
```

[ascii码, GBK及Unicode由来] 字符编码是计算机技术的基石，想要熟练使用计算机，就必须懂得一点字符编码的知识。 

## 七、正则表达式

### 定义

#### 字面量

```
var reg = /内容/;
```

#### 构造函数

参数：以字符串的形式写在第二个位置

```
var reg = new RegExp();
```

### 参数

i：忽略大小写

g：全部匹配

参数卸载第二个斜杠后，字面量中不能为变量

```
var reg = /内容/gi;

//将要替换的内容赋值给一个变量,只有构造函数能这样子使用
var reg = new RegExp(变量,'gi');
```

## 八、支持正则表达式的方法

search()

split()

replace()

# Math对象方法

一个保存数学公式和信息的对象，一般用于执行数学任务

## 一、属性

Math.PI  //3.1415926

## 二、方法

### Math.round()

取整，四舍五入取整

```
Math.round(3.14);//3
Math.round(3.84);//4
Math.round(3.84);//-4
```

### Math.ceil()

向上取整（得到一个比当前数大的最小整数）

```
Math.ceil(3.14);//4
Math.ceil(-3.14);//-3
```

### Math.floor()

向下取整（得到一个比当前数小的最大整数）

类似parseInt()

```
Math.floor(3.84);//3
Math.floor(-3.84);//-4
```

### Math.random()

随机数，返回0-1之间的随机数（不包括1）

```
Math.random();
```

### Math.max(num1,num2)

返回较大的数

```
Math.max(11,23);//23
```

### Math.min(num1,num2)

返回较小的数

```
Math.min(11,23);//11
```

### Math.abs(num)

绝对值

```
Math.abs(-10);//10
```

### Math.pow(x,y)

x的y次方

```
Math.pow(4,2);//16
```

### Math.sqrt(num)

开平方根

```
Math.sqrt(16);//4
```

## 三、相关数学知识

### 角度与弧度的转换

```
弧度=角度*Math.PI/180;
```

1弧度等于的r的半径

### 三角函数

#### sin(radian)

求对边的长度 

```
Math.sin(角度*Math.PI/180)*r;//r代表斜边
```

#### cos(radian)

求邻边的长度

```
Math.cos(角度*Math.PI/180)*r;//r代表斜边
```

#### tan(radian)

求斜边的长度

```
Math.tan(角度*Math.PI/180);// => 求出的是对边比邻边;
//再利用勾股定理求出斜边
```

![1531535664865](D:\学习\笔记\img\圆.png)

# 日期 Date

## 一、了解时间

​	GMT：格林尼治标准时(Greenwich Mean Time)，俗称“天文学时间”

​	UTC：协调世界时(Universal Time Coordinated)，“原子物理时间”，它更加精确,50亿年才误差1秒

​	时区：为了克服时间上的混乱，1884年在华盛顿召开的一次国际经度会议（又称国际子午线会议[1]）上，规定将全球划分为24个时区（东、西各12个时区）。规定英国（格林尼治天文台旧址）为中时区（零时区）、东1-12区，西1-12区。每个时区横跨经度15度，时间正好是1小时

​	闰年：四年一闰，百年不闰，四百年再闰

​	纪元时间(UNIX TIME)：1970-1-1零时

## 二、创建日期时间

### 构造函数

```
//当前运行此行代码的时间
//包含年月日 时分秒 毫秒 星期 时区
var date = new Date();
//Thu Jul 12 2018 18:27:10 GMT+0800 (中国标准时间)
```

```
//指定日期创建日期
var date = new Date('2018-10-1');
```

```
//指定毫秒创建日期
var date = new Date(1671010103043753;
```

```
//指定日期创建日期（多个参数）
var date = new Date(2018,10,1);
//Thu Nov 01 2018 00:00:00 GMT+0800 (中国标准时间)
```

## 三、获取/设置 年月日

### getFullYear()

获取年份

```
var date = new Date();
date.getFullYear();//获取到当前的年份
```

### setFullYear()

设置年份

```
var date = new Date();
//修改了date的年份
date.setFullYear(2020);
//Sun Jul 12 2020 19:17:14 GMT+0800 (中国标准时间)
```

### getMonth()

获取月份，默认是0-11

```
var date = new Date();
date.getMonth()+1;//获取当前月份
```

### setMonth()

设置月份，默认是0-11

```
var date = new Date();
date.setMonth(8);//显示9月
```

### getDate()

获取当前日期

```
var date = new Date();
date.getDate();//显示当前的日期
```

### setDate()

设置当前日期

```
var date = new Date();
date.setDate(20);//当前日期设置为20号
```

## 四、获取/设置 时分秒

### getHours()/setHours()

获取（设置）时

```
var date = new Date();
date.getHours();//获取当前时间的小时
```

### getMinutes()/setMinutes()

获取（设置）分

```
var date = new Date();
date.getMinutes();//获取当前时间的分钟
```

### getSeconds()/setSeconds()

获取（设置）秒

```
var date = new Date();
date.getSeconds();//获取当前时间的秒
```

### getMilliseconds()/setMilliseconds()

获取（设置）毫秒

```
var date = new Date();
date.getMilliseconds();//获取当前时间的毫秒
```

## 五、获取星期

### getDay()

 0-6:星期天-星期六

```
var date = new Date();
date.getDay();//获取星期
```

## 六、日期处理

### getTime()/setTime()

获取/修改某个日期自1970年1月1日0时以来的毫秒数

```
var date = new Date();
date.getTime();//获取当前日期到19701月1日0时的毫秒数
```

### toLocaleDateString()

以特定地区格式显示年、月、日

```
var date = new Date();
date.toLocaleDateString();// 默认之间为/
```

### toUTCString()

转换成UTC时间 字符串

```
var date = new Date();
date.toUTCString();//转换成UTC字符串
```

## 七、ES5方法

### Date.parse()

```
Date.parse(“2015-08-24”);
//返回指定日期距1970-1-1零时的毫秒数 
```

### Date.now()

```
Date.now();
//返回执行这行代码时距1970-1-1零时的毫秒数
```

## 八、延迟与定时器

### setInterval()

```
setInterval(fn,30);
//每隔30毫秒执行一次fn这个函数，返回一个id标识
```

### clearInterval()

```
var timer = setInterval(function(){
    //函数执行的内容
},1000);
clearInterval(timer);
//清除指定id标识的定时器操作
```

### setTimeout()

```
setTimeout(fn,200);
//两百毫秒后执行fn这个函数（只执行一次）,返回一个id标识
```

### clearTimeout()

```
var timer = setTimeout(function(){
    //函数执行的内容
},1000);
clearTimeout(timer);
//清除指定id标识的延迟操作
```

# BOM

## 一、BOM的概念

BOM 是Browser Object Model（浏览器对象模型）的缩写，提供与浏览器窗口进行交互的对象。JavaScript语法的标准化组织是ECMA，DOM的标准化组织是W3C, 而BOM缺乏标准。这也是各种浏览器不兼容的根源所在 

## 二、window对象

window对象是BOM的核心, 是最顶层的对象，所有对象都是通过它延伸出来的 

### 全局作用域

1、定义在全局环境下的变量都会成为window对象的属性

2、把变量定义在函数体里，可以有效减少全局环境下的变量冲突，避免污染全局环境

3、在函数内部不用var声明的变量会成为全局变量，即window对象的属性

4、window对象可以在代码中省略，如window.alert()可以写成alert();

5、通过var在全局作用域下声明的变量用delete无法删除

```
var obj = {name:'xxx'};
//删除对象的属性用delete：
delete obj.name;
```

### window对象下的属性

#### window.innerWidth

获取可视区域宽度

#### window.innerHeight

获取可视区域高度

#### window.scrollX

水平滚动条滚动过的距离（只读）

#### window.scrollY

垂直滚动条滚动过的距离（只读）

#### scrollTo(x,y);

设置浏览器滚动距离 

#### scrollBy(xnum,ynum)

设置基于当前位置滚动的距离，可以为负数

### 常用方法

#### alert()

弹出对话框

#### confirm()

弹出警告框，返回布尔值

#### prompt()

弹出输入框，返回消息或null

#### open()

```
open(url,name,[options]);
打开一个新窗口并返回新window对象 
```

name:不命名会每次打开新窗口，命名的第一次打开新窗口,之后在这个窗口中加载

options为字符串：`'width=400,height=400,top=200,left=200'`

opener父窗口对象，通过open方法打开的窗口才有opener对象

#### close()

关闭窗口

#### print()

调出打印对话框

### 属性对象

#### document

document(核心): 文档对象，让我们可以在js脚本中直接访问页面元素(DOM) 

#### history

history(重要): 历史对象,包含窗口的浏览历史，可以实现后退 

##### 属性

###### length

返回浏览器历史列表中的 URL 数量。

##### 方法

###### back()

加载 history 列表中的前一个 URL。

###### forward()

加载 history 列表中的下一个 URL。

###### go()

加载 history 列表中的某个具体页面，支持负数。

```
history.go(2);//向前两个页面
history.go(-2);//后退两个页面
```

#### location

location是BOM最有用的对象之一，保存着当前窗口中加载文档的相关信息，还提供一些导航功能，它是个很特别的对象，既是window的属性，也是document的属性 

##### 属性

###### hash

设置或返回从井号 (#) 开始的 URL（锚）==>哈希值。

（单页面应用）

###### href

设置或返回完整的 URL。	    

###### search

设置或返回从问号 (?) 开始的 URL（参数部分）。

```
encodeURI();//转码
decodeURI();//解码
```

**PS：**修改以上属性(hash除外)都会刷新当前页面，并生成历史纪录 

##### 方法

###### reload()

重新加载当前文档，带参数true表示不使用缓存刷新页面。

#### navigator

导航对象, 包含所有有关访问者浏览器的信息，通常用于检测浏览器类型 

**appName** 浏览器名称

**appVersion** 浏览器版本

**platform** 操作系统

**userAgent** 用户代理信息，通过该属性可以获取浏览器及操作系统信息

**geolocation** 获取地理位置信息（比较常用）

#### screen

关于屏幕信息

### window对象常用事件

#### onload

页面资源全部加载完成后触发这个事件

#### onscroll

窗口滚动条滚动时触发

#### onresize

窗口大小改变时触发

# DOM

## 一、什么是DOM

DOM是Document Object Model（文档对象模型）的缩写，它是W3C国际组织的一套Web标准。是针对HTML和XML文档的一个API，它定义了访问HTML文档对象的一套属性、方法和事件

## 二、节点类型

每个节点都有一个nodeType属性，用于表明节点的类型。

常用节点类型与对应nodeType值：用于判断获取到的元素属于什么类型节点 

元素节点 <==> 1

属性节点 <==> 2

文本节点 <==> 3

## 三、节点获取

### document.getElementById()

通过 ID获取元素的节点（速度最快）

必须通过document调用

返回DOM节点对象，如果id不存在返回null

```
<div id='box'>这是一个div</div>
//通过id获取元素
var box = document.getElementById('box');
```

### getElementsByTagName()

通过标签名获取元素节点列表

返回类数组，如果tagname不存在返回空数组[]

```
<div>第一个div</div>
<div>第二个div</div>
//通过标签名获取元素
var divOne = document.getElementsTagName('div')[0];
```

### getElementsByClassName()

通过class类名获取节点列表

返回类数组，如果类名不存在返回空数组[]

IE8- 不兼容

```
<div class='box'>第一个div</div>
<div class='box'>第二个div</div>
//通过类名获取元素
var classOne = document.getElementsByClassName('box')[0];
```

### document.getElementsByName()

通过name属性获取元素节点列表

必须通过document调用

返回类数组，如果name属性不存在返回空数组[]

```
<input type="text" name='gender' />男
<input type="text" name='gender' />女
//通过name属性获取元素
var boy = document.getElementsByName('gender')[0];
```

**注意: 如果确认元素存在, 但是返回null或[]，一定是代码执行顺序的问题** 

## 四、节点操作

### 节点属性

#### nodeName

返回节点的名称，根据其类型。

```
ele		大写标签名
attr 	属性名
text	#Text
```

#### nodeType

返回节点的类型。

```
ele		1
attr	2
text	3
```

#### nodeValue

返回节点的值（元素节点的nodeValue为null）

```
ele		null
attr	属性值
text	文本内容
```

### 节点方法

#### 创建

##### document.createElement()

创建一个元素节点

```
var div = document.createElement('div');
```

##### document.createTextNode()

创建一个文本节点

```
var text = document.createTextNode('txt');
```

##### document.createAttribute()

创建一个属性节点（了解）

```
var myclass = document.createAttribute('class');
```

#### 插入

##### parent.appendChild()

向节点的子节点列表的结尾添加新的子节点

##### parent.insertBefore(new,node)

在指定的子节点node前插入新的子节点new。

##### ele.setAttributeNode(attrNode)

在指定元素中插入一个属性节点（了解）

**对页面已存在节点的处理**

#### 复制

##### cloneNode(boolean)

复制节点，为true是深复制。

#### 删除

##### parent.removeChild(ele)

删除（并返回）当前节点parent的指定子节点ele。

#### 判断

##### parent.hasChildNodes()

判断当前节点是否拥有子节点，返回布尔值

### 利用节点关系获取其他节点

#### 获取父级节点

##### ele.parentNode

得到ele元素的父节点

#### 获取子节点

##### ele.childNodes

得到ele元素的全部子节点列表（类数组）

##### ele.firstChild

获得ele元素的第一个子节点

##### ele.lastChild

获得ele元素的最后一个子节点

#### 获取兄弟节点

##### ele.nextSibling

获得ele元素的后一个兄弟节点

##### ele.previousSibling

得到ele元素的前一个兄弟节点

## 五、元素节点的操作

### 常用属性

**可以通过点语法或方括号访问** 

#### tagName

获取元素元素的标签名

#### id

设置/获取元素id属性

#### name

设置/获取元素name属性

#### style

设置/获取元素的内联样式

#### className

设置/获取元素的class属性

#### innerHTML

设置/获取元素的内容（包含html代码）

#### outerHTML

设置或获取元素及其内容（包含html代码）

#### innerText

设置或获取位于元素标签内的文本

#### outerText

设置(包括标签)或获取(不包括标签)元素的文本

### 盒模型相关

#### offsetTop

当前元素离<定位父级>元素顶部的距离。（如果没定位的父级，则相对于根元素html的距离 ）

#### offsetLeft

当前元素离<定位父级>元素左边的距离。（如果没定位的父级，则相对于根元素html的距离 ）

#### offsetWidth

当前元素的宽度（border + padding + content）

#### offsetHeight

当前元素的高度（border + padding + content）

### 元素方法(适用所有的属性)

#### ele.getAttribute(attr)

获取元素的属性值（自定义属性获取）

#### ele.setAttribute(attr,val)

设置元素的属性

#### ele.removeAttribute(attr)

删除属性attr

#### ele.hasAttribute(attr)

判断是否存在属性attr

### 根据元素关系获取其他元素（IE9+）

#### parentElement

获取父级节点元素

#### children

获取元素的全部子元素（兼容所有浏览器）

#### firstElementChild

获取第一个子元素

#### lastElementChild

获取最后一个子元素

#### previousElementSibling

获取前一个元素

#### nextElementSibling

获取下一个元素

### 获取css样式（非内联样式）

得到当前元素计算后的所有样式 

#### getComputedStyle(ele,pseudo) （标准）

ele:要获取样式的元素

pseudo:伪元素样式字符(可选)，可获取伪元素样式

#### ele.currentStyle （IE8-）

## 六、table对象

### table对象属性&方法

#### rows

返回包含表格中所有行的一个数组

#### tBodies

返回包含表格中所有 tbody 的一个数组

#### insertRow(index)

在表格中插入一个新行。

#### deleteRow(index)

从表格删除一行。

### tr对象属性&方法

#### cells

返回包含表格中所有单元格的一个数组

#### rowIndex

返回该行在表中的位置

#### sectionRowIndex

返回在 tBody 、tHead 或 tFoot 中行的位置。

#### insertCell(index)

在一行中的指定位置插入一个空的列

#### deleteCell(index)

删除行中的指定的单元格

### td/th对象属性&方法

#### cellIndex

返回单元格在表格行的单元格集合中的位置 

# Event 事件

## 一、什么是事件

事件是可以被JavaScript侦测到的行为。网页中的每个元素都可以产生某些可以触发JavaScript函数的事件

### 事件绑定方式

格式：节点.on+事件名 = 事件处理函数

```
div.onclick = function(){}
```

### 事件分类

#### 1、鼠标事件

##### onclick

当用户点击某个对象时调用的事件

##### ondblclick

当用户双击某个对象时调用的事件

##### onmousedown

鼠标按钮被按下

##### onmouseup

鼠标按键被松开

##### onmouseover

鼠标移到某元素之上

##### onmouseout

鼠标从某元素移开

##### onmousemove

鼠标被移动时触发

##### onmouseenter

在鼠标光标从元素外部移动到元素范围之内时触发。这个事件不冒泡

##### onmouseleave

在位于元素上方的鼠标光标移动到元素范围之外时触发。这个事件不冒泡

##### oncontextmenu

鼠标右键菜单展开时触发

注：click = mousedown + mouseup

​	dblclick = click*2（短时间内两次单击）

执行顺序：mouseover => mouseenter

​		   mouseout => mouseleave

#### 2、键盘事件

##### onkeydown

按键被按下时触发，可以连续触发

##### onkeyup

按键被松开时触发

##### onkeypress

键盘<字符键>被按下时触发，可以连续触发

#### 3、UI事件

##### onload

页面元素（包括图片多媒体等）加载完成后

##### onscroll

滚动时触发

##### onresize

窗口或框架被重新调整大小

#### 4、表单事件

##### onblur

元素失去焦点时触发

##### onfocus

元素获得焦点时触发

##### onchange

元素内容被改变，且失去焦点时触发

##### oninput

输入字符时触发

##### onreset

重置按钮被点击

##### onsubmit

确认按钮被点击

##### onselect

输入框文本被选中

## 二、Event 对象

### 什么是event对象

事件执行过程中的状态，用来保存当前事件的信息对象

### 如何获取event对象

#### 标准

事件处理函数的第一个参数

```
div.onclick = function(e){
    执行内容
}
```

#### IE8-

window.event

#### 兼容写法

```
div.onclick = function(e){
    e = e||window.event;
}
```

### Event对象详情

#### 1、鼠标j/键盘事件Event属性

##### button

返回当事件被触发时，哪个鼠标按钮被点击

```
W3C标准
0：代表鼠标按下了左键
1：代表按下了滚轮
2：代表按下了右键
```

```
IE8-
1：鼠标左键
2：鼠标右键
3：左右同时按
4：滚轮
5：左键加滚轮
6：右键加滚轮
7：三个同时
```

##### which/keyCode

对于keypress事件，该属性声明了被敲击的键生成的Unicode字符码（ascii码）

对于keydown和keyup事件，它指定了被敲击的键的虚拟键盘码。虚拟键盘码可能和使用的键盘的布局相关

```
document.onkeypress = function(e){
    var key = e.keyCode || e.which;
}
```

##### altKey

返回当事件被触发时，ALT键是否被按下。

##### ctrlKey

返回当事件被触发时，CTRL键是否被按下。

##### shiftKey

返回当事件被触发时，Shift键是否被按下。

#### 2、光标位置信息

##### clientX/clientY

光标相对于浏览器可视区域的位置，也就是浏览器坐标

##### screenX/screenY

光标指针相对于电脑屏幕的水平/垂直坐标

##### pageX/pageY

鼠标相对于文档的位置

包括滚动条滚动的距离，即：clientX+window.scrollX

IE8-不支持

```
//兼容性写法
document.onmousemove = function(e){
    e = e||window.event;
    if(!e.pageX){
        e.pageX = e.clientX + document.body.scrollLeft;
    }
    if(!e.pageY){
        e.pageY = e.clientY + document.body.scrollTop;
    }
}
```

##### offsetX/offsetY

光标相对于事件源对象的相对偏移量

事件源对象：触发事件的对象

#### 3、Event公共属性

##### type

被触发的事件类型（一般用于判断）

##### currentTarget

其事件处理程序当前正在处理事件的那个元素

### 事件冒泡

什么是事件冒泡：在一个对象上触发某类事件（如onclick事件），那么click事件就会沿着DOM树向这个对象的父级传播，从里到外，直至它被处理程序处理，或者事件到达了最顶层（document/window）

#### 事件源对象

触发事件的元素

标准：event.target

IE8-：event.srcElement

事件源对象在事件传播过程中不会改变

#### 停止事件的传播

标准：event.stopPropagation();

IE8-：event.cancelBubble = true;

注：1、不是所有的事件都能冒泡。以下事件不冒泡：blur、focus、load、unload...

​	2、冒泡到最顶层的目标不同。大部分浏览器到window对象，IE8-到document对象

### 阻止浏览器默认行为

如：链接跳转、表单提交、右键菜单、文本的选择...

#### 标准

```
event.preventDefault();
```

#### IE8-

```
event.returnValue = false;
```

## 三、 事件监听与捕获（反冒泡）

### 事件监听器

是否把事件处理函数提前到捕获阶段执行

格式：元素.addEventListener(事件名,事件处理函数,是否捕获)

```
target.addEventListener("click",fn,false);
```

***可以绑定多个处理函数在一个对象上，执行顺序按照绑定的顺序来**

​	*不同元素事件执行顺序跟html结构有关

​	*相同元素事件执行顺序跟绑定先后有关

***第三个参数是否使用捕获（反向冒泡），默认为false，为冒泡**

***IE8-的事件监听**

格式：元素.attachEvent(on+事件名,事件处理函数)

```
target.attachEvent("onclick",fn);
```

可以绑定多个函数在一个对象上，执行顺序按照绑定的反序

### 移除

#### 标准

```
removeEventListener('click',fn,true);
//传入的所有参数（包括函数）必须与事件监听器中一致，否则不能被移除
```

### IE8

```
detachEvent('onclick',fn);
传入的参数fn要跟添加时是一样，否则不能被移除事件
```

注意：页面事件绑定数量越多，越影响性能（速度越慢）

## 四、拖拽效果

### 拖拽的原理

鼠标按下且移动鼠标时，改变当前元素的top，left值

### 拖拽的思路

#### 1、给目标元素添加onmousedown事件

<u>拖拽的前提是目标元素设置css定位</u>

记录按下鼠标位置与元素左上角的偏移量

ox = offsetX，oy = offsetY

ox = clientX - offsetLeft，oy = clientY - offsetTop

#### 2、当onmousedown发生以后，此刻给document添加onmousemove事件

<u>意味着此刻鼠标在网页的移动都将改变元素的位置</u>

在onmousemove事件中，设定目标元素的left和top

公式：目标元素的left = 鼠标的clientX - offsetX

​	    目标元素的top = 鼠标的clentY - offsetY

#### 3、给document添加onmouseup事件，清空document的onmousemove事件

意味着拖动过程中鼠标在网页的任意位置松开鼠标，都会放弃拖拽的效果

# Cookie

## 一、网络知识

### 1、通信协议

通信规则，设备与设备之间通信时共同遵守的规则 

### 2、TCP/UDP/IP

#### IP

Internet Protocol（网络之间互连的协议），规定了计算机在因特网上进行通信时应当遵守的规则

- IP地址：4个字节, 一共32位 ，用来标识设备在网络中的位置
- 子网掩码: 255.255.255.0 确认两台计算机是否处于同一网段

#### TCP

Transmission Control Protocol（传输控制协议） 

TCP面向连接的协议（通信之前必须先建立连接）

TCP相对可靠，它建立连接的过程称为3次握手

- 经历3次握手，才能建立连接
- 所有的消息传送，需要对方确认送达

因此可以确保数据的准确送达 

#### UDP

UDP面向数据报的协议 (不可靠的协议)，如果TCP比作是打电话，那么UDP就是在发短信

- 无需建立连接，发送消息也无需对方确认
- 无法保证数据的发送顺序，以及准确率
- UDP通常用于视频、语音等通信（丢掉了一帧画面是无所谓的）

### 3、http/https

超文本传输协议HyperText Transfer Protocol，基于TCP协议的一种高级协议, 用于客户端和服务器直接的通信 

- http的特点是，请求完成后就立即断开与服务器的连接
- 缺点
  - 通信使用明文（不加密），内容可能会被窃听
  - 不适用特定的Web服务器，如：聊天室，消息广播

### 4、socket

是一种通信模式，客户端与服务端一直保持着连接，用于随时传输数据 

## 二、cookie的概念

cookie 是客户端与服务器端进行通讯使用的一个能够在浏览器本地化存储的技术 

PS：chrome不支持本地文件的cookie读写 

### cookie的应用场景

- 七天免登陆
  7天内访问网站无需输入密码
- 购物车信息
  添加到购物车后，取到购物车页面，商品信息依然存在
- 商品浏览记录
  用户每浏览一个商品就会保留商品的浏览记录

## 三、cookie的组成

cookie由键值对形式的文本组成，完整格式如下： 

```
document.cookie = name=value[;expires=date][;path=路径][;domain=域名]
//[]表示该值是可选
```

name=value: 为你要保存的键值对(必选)

- 利用decodeURI解码中文字符
- 利用json保存多条信息

expires=date: 表示cookie的失效时间, 默认是浏览器关闭时失效(可选) 

```
//设置7天内生效的cookie
var date = new Date();  
date.setDate(date.getDate() +7); 
document.cookie = "user=laoxie;expires=" + date.toUTCString();
```

path=路径: 访问路径, 默认为当前文件所在目录(可选) cookie只能在设置的路径及它的子目录下使用 

domain=域名: 访问域名, 限制在该域名下访问(可选) 没有设置则默认为当前域名 

## 四、cookie的操作

### 1、cookie的获取和设置

```
//设置
document.cookie = 'name=laoxie';
//获取
var cookies = document.cookie;
```

- 一次只能写入一个cookie
- 获取时得到所有cookie，多个cookie之间用分号+空格（’; ‘）来隔开

### 2、cookie的删除

利用设置过期时间达到删除的效果。 

### 3、cookie的封装

封装cookie的增删改查 

```
var Cookie = {
	get:function(name){
        var cookis = document.cookie;
        cookie = cookie.split('; ');
        var res = '';
        for(var i=0;i<cookie.length;i++){
        	var arr = cookie[i].split('=');
            if(arr[0]===name){
                res = cookit[1];
            }
        }
        return res;
	};
	remove:function(){
        
	};
	set:function(){
        
	};
};
```

## 五、XSS攻击

cross-site scripting（跨域脚本攻击）是最常见的Web攻击，其重点是“跨域”和“客户端执行”。有人将XSS攻击分为三种，分别是： 

1、Reflected XSS（基于反射的XSS攻击） 

XSS攻击脚本被web server反射回来给浏览器执行 

2、Stored XSS（基于存储的XSS攻击） 

XSS恶意代码存储在web server中，一般是通过网站的留言、评论、博客、日志等等功能将攻击代码存储到web server上的 

3、DOM-based or local XSS（基于DOM或本地的XSS攻击） 

根据用户的输入来动态构造一个DOM节点，如果没有对用户的输入进行过滤，那么也就导致XSS攻击的产生 

### XSS攻击的防御

- 对输入(和URL参数)进行过滤
- 对输出进行编码

## 六、cookie发送到服务器

cookie会随着请求自动发送到后台服务器，接收cookie

# 正则表达式

## 一、了解正则表达式

正则表达式(regular expression)是一个描述字符模式的对象 。

正则表达式能够进行强大的“模式匹配”和“文本检索与替换”功能。前端往往有大量的表单数据校验的工作，采用正则表达式会使得数据校验的工作量大大减轻 

## 二、创建正则表达式

### 构造函数

第一个参数就是我们的模式“字符串”

```
var reg = new RegExp('study');

//使用特殊字符
var reg = new RegExp('\\d\\w+');\d\w+
```

第二个参数可选，模式修饰符

i：case-insensitive，表示忽略大小写

g：global，表示全局匹配

m：multiline，表示多行匹配

```
var reg = new RegExp('study','ig');
```

### 字面量

```
var reg = /study/gi;
```

直接量是字符匹配，不支持变量

## 三、使用正则表达式

### 支持正则表达式的字符串方法

#### search

返回第一次匹配时所在的索引值，如果匹配不到则返回-1

#### match

默认匹配字符串，返回一个数组

- 0：所匹配的字符
- index：匹配第一个字符所在的索引
- input：对字符串的引用

全局匹配（g），返回一个匹配所有字符串数组

如果匹配不到则返回null

#### replace

替换字符串

#### split

```
'a,b,c,d,e'.split(/\s*,\s*/);
```

### 正则表达式的属性和方法

#### test()

- 测试正则表达式用test方法，返回布尔值
  - 格式：正则表达式.test(字符串)
  - 用<正则表达式>测试<字符串>是否匹配，返回true/false

```
/xx/.test(字符串)
```

#### exec()

- 测试正则表达式exec方法

```
/xx/.exec(字符串)
```

### 匹配规则

- 所在字符和数字都是按照字面量进行匹配，和字符串匹配等效

```
/good/gi
```

- 字符类（只记小写字母即可）

  - . ：除换行符以外的字符
  - \w：代表数字或字母或下划线
  - \W：非数字字母和下划线字符
  - \d：数字
  - \D：非数字
  - \s：代表一个空格
  - \S：空格以外的字符
  - \b：匹配一个单词边界，也就是指单词和空格间的位置
  - \B：匹配非单词边界。

  以上所有字符类都只是匹配“一个”字符

- 特殊符号

  ```
  ^$.*+?=!:|\/()[]{}
  ```

  - []：代表任意“单个字符”，里面的内容表示“或”的关系

    - -：代表范围
    - ^：代表非

  - ()：表示分组（n是以最左边括号出现的顺序排列）

    - $1：表示第一个分组

    - $n：表示第n个分组（不能写在正则表达式里）

    - \n：在正则分组后面使用，表示对第n个分组的引用（一定要写在正则表达式里）

      编写的正则分组数量越少越好

  - |：表示或者

  - 锚点定位

    - ^：表示以什么开头
    - $：表示以什么结尾

  - 表示数量，对前一个字符计数

    - *：代表0个或0个以上<==>{0,}

    - +：代表1个或1个以上<==>{1,}

    - ?：代表0个或1个<==>{0,1}

    - {}：

      ```
      \d{5}:匹配5个数字
      \d{5,10}：匹配5个到10个数字
      \d{5,}：匹配5个或5个以上的数字
      ```

      1）数量词*，+，{5,}，会尽可能多的去匹配结果（贪婪）

      2）在后面加一个？表示尽可能少的去匹配结果（非贪婪）

      google,goooole ==> /go+/

# ECMAScript5（ES5）

## 一、支持ES5的浏览器

- Opera 11.60+
- Internet Explorer 9+
  - IE9不支持严格模式 
- Firefox 4+
- Safari 5.1+
- Chrome 13

## 二、加载事件

### DOM文档加载的步骤为

1. 解析HTML结构。
2. 加载外部脚本和样式表文件。
3. 解析并执行脚本代码。（匿名函数）
4. DOM树构建完成。（interactive、DOMContentLoaded）
5. 加载图片等外部文件。（complete）
6. 页面加载完毕。（window.onload）

### document事件

readystatechange事件

- interactive

- complete

  ```
  document.onreadystatechange = function(){
      if(document.readyState === 'interactive'){
      }
  }
  ```

- DOMContentLoaded事件 

  ```
  document.addEventListener('DOMContentLoaded',function(){
      //DOM树构建完成后执行
  })
  ```

注意：以上事件用以取代window.onload事件 

## 三、ES5的严格模式

除了正常模式，ES5添加了第二种运行模式：“严格模式(strict mode)”。顾名思义，这种模式使得javascript在更严格的条件下运行(更可靠，更安全)。目前，除了IE6-9，其它浏览器均已支持ES5严格模式。 

### 为什么要用严格模式

- 消除javascript语法的一些不合理，不严谨的地方，减少一些怪异行为；
- 消除代码运行的一些不安全之处，保证代码运行的安全；
- 提高编译器效率，增加运行速度；
- 为未来新版本的javascript做好铺垫；

### 如何使用

```
在头部写入 “use strict”
```

- 全局：针对整个js文件
  将”use strict”放在脚本文件的第一行，则整个脚本都将以”严格模式”运行
- 局部：针对单个函数
  将”use strict”放在函数体的第一行，则整个函数以”严格模式”运行。

```
function strict(){
    "use strict";
    return "这是严格模式";
}
```

- 执行限制 

- 不使用var声明变量严格模式中将不通过

- 删除系统内置的属性会报错

- delete不可删除属性的对象时报错，如：

  - var声明的全局变量（会自动称为window的属性）

- 对象有重名的属性将报错 

  ```
  var obj={name:"小王",name:'王大锤'} 
  ```

- 函数有重名的参数将报错 

  ```
  function sum(a,a,b){} 
  ```

- arguments严格定义为参数 

  - 不允许对arguments赋值
  - 禁止使用arguments.callee

- 函数必须声明在顶层，不能写在条件判断语句或for循环语句中 

```
var arr = [10,2,3,50];
if(arr.length>3){
    function sum(){//报错

    }
}
```

## 四、JSON对象方法

### JSON.parse(text)

将json字符串转换成对象/数组

- text：json字符串
- json字符串格式
  - 属性名必须加`双引号`
  - 字符串必须加`双引号`
  - 不能有注释
  - 最后不能有多余逗号
  - 属性值可以为以下值
    - 数字（整数或浮点数）
    - 字符串（在双引号中）
    - 布尔值（true 或 false）
    - 数组（在方括号中）
    - 对象（在花括号中）
    - null

### JSON.stringify(value)

将数组/对象转换成标准的json字符串

## 五、获取元素节点

### querySelector(selector)

获取匹配选择器的第一个元素节点，返回DOM节点

### querySelectorAll(selector)

获取匹配选择器的所有元素，返回数组

当页面添加了新的dom无法自动更新dom节点

## 六、Function方法

### bind()

用于将当前函数和指定对象绑定(改变this指向)，返回一个新的函数

应用 

```
var btns = document.querySelectorAll('.btn');
for(var i=0;i<btns.length;i++){
    btns[i].onclick = function(){
        //这里的this指向按钮
        setTimeout(function(){
            // 这里的this呢？
            console.log(this);
            output.innerHTML = '你点击了' + this.innerHTML;
        }.bind(this),1000);
    };
}
```

## 七、其他

### 获取class列表属性

classList：js 的方法

- length : class类名的个数
- add() : 添加class方法
- remove() : 删除class方法
- toggle() : 切换class方法
- contains():是否含有某个类,返回布尔值

### data自定义属性

- dataset 

```
data-name :  dataset.name
data-name-first  :  dataset.nameFirst
```

# ECMAScript6（ES6）

## 一、变量声明

### let

代码块内的变量声明

```
let a = 10;
//1、声明不会提前
//2、块级作用域
//3、不允许相同作用域内多次声明同一变量
```

### const

常量声明（一般定义常量用大写，多个单词用下划线）

```
const A = 10;
const USER_NAME = 'xiaoming';
//1、声明不会提前
//2、块级作用域
//3、不允许相同作用域内多次声明同一变量
//4、声明后无法修改值
```

## 二、解构赋值Destructuring

ES6允许我们对数组和对象中提取值，对变量进行赋值，这被叫做“解构” 

### 使用

#### 数组

```
let arr = [1,2,3];
let [a,b,c] = arr;
console.log(a,b,c);//1,2,3
```

#### 对象

```
let obj = {name:'xiaoming',gender:'男'};
let {name:username,gender:sex} = obj;
console.log(username,sex);//xiaoming 男
```

解构失败返回undefined 

```
let obj = {name:'xiaoming',age:18};//obj中没有gender属性
let {name:username,gender:sex} = obj;//找不到gender属性
console.log(username,sex);//xiaoming undefined
```

设置默认值

```
let obj = {name:'xiaoming',age:18};//obj中没有gender属性
let {name:username,gender:sex='男'} = obj;//设置默认值
console.log(username,sex);//xiaoming 男
```

解构只能用于数组和对象，如果解构不成功，变量会返回undefined。但如果对undefined和null解构则会报错

### 解构用途

#### 交换变量值

```
var x=10,y=20;
var [x,y] = [y,x];
console.log(x,y);//20 10
```

#### 函数返回多个值

```
function example(){
    return [1,2,3];
}
var [a,b,c] = example();
console.log(a,b,c);//1,2,3
```

#### 定义函数形参

 定义函数形参，函数的参数定义方式, 不用再考虑参数的顺序 

```
function test({x,y,z}){
    console.log(x,y,z);
}
test({x:10,y:20,z:30});// 10 20 30
test({x:10,z:30,y:20});// 10 20 30
```

可设置默认值

```
function test({x,y,z=10}){
    console.log(x,y,z);
}
test({x:10,y:20});//10 20 10
```

## 三、字符串扩展

### 字符串方法

#### includes()

判断字符串中是否存在某个字符，返回布尔值

```
'html5'.includes('html');//true
```

#### startsWith()

判断字符串的开头是否存在某个字符，返回布尔值

```
'html5'.startsWith('h');//true
```

#### endsWith()

判断字符串的结尾是否存在某个字符，返回布尔值

```
'html5'.endsWith('5');//true
```

#### repeat()

得到字符串重复n次后的结果，n可以为小数，但不能为负数 

```
'laoxie'.repeat(2);//laoxielaoxie
```

### 字符串模版

用反引号`表示，可以通过更美观、更加方便的方式向字符串中插入变量

格式：${变量|函数}

```
<div id="output"></div>

var output = document.querySelector('#output');
var a = 1;
var content = `<ul>
	<li>${a}</li>//变量
</ul>`;
output.appendChild('content');
```

## 四、对象扩展

### Object.assign()

合并对象，如果后面的对象如果存在原本对象中一样的属性名，后者会覆盖前者的

```
var person = {
	name:'xiaoming',
	age:18
};
Object.assign(person,{sex:'男',age:17});
console.log(person);//name:'xiaoming',age:17,sex:'男'
```

#### 复制对象

```
var person = {
	name:'xiaoming',
	age:18
};
var newObj = Object.assign({},person);//复制
console.log(newObj);//name:'xiaoming',age:18
```

以上复制只是浅复制，对于引用类型，只复制引用

```
var person = {
	name:'xiaoming',
	age:18,
	score:{
		english:58,
		music:88,
		math:30
	}
};
var newObj = Object.assign({},person);//复制
console.log(newObj);//name:'xiaoming',age:18
newObj.score.math = 100;//改变了person的值
```

#### 深复制

使用JSON转换的方法实现

```
var person = {
	name:'xiaoming',
	age:18,
	score:{
		english:58,
		music:88,
		math:30
	}
};
var newObj = JSON.parse(JSON.stringify(person));//深复制
newObj.score.math = 100;//不会改变了person
```

### 简写

ES6允许在对象中直接写变量

属性简写

```
//属性简写
var myName = 'xiaoming';
var obj = {
    myName
}

//相当于
var obj = {
    myName:'xiaoming'
}
```

变量名作为属性值

```
//使用变量名作为属性值
var myName = 'xiaoming';
var obj = {
    [myName]:18
}

//相当于
var obj = {
    xiaoming:18
}
```

方法简写

```
var obj = {
	coding(){
        
	}
}

//相当于
var obj = {
    coding:function()
}
```

## 五、遍历扩展

### for...of

```
var arr = [10,12,18,30];
for(var value of arr){
    console.log(value);//10 12 18 30
}
```

特性：不需要知道数组的length值。

​	    正常响应break、continue和return语句 。

​	    可直接获取元素不需要知道索引值。

​	    可遍历很多集合，除了普通对象。

## 六、箭头函数

函数的简写，选择性省略function，()，{}，return

### 无参数

当函数中没有参数的时候用()表示

```
//传统写法
var sum = function(){
    return 10+10;
}
//ES6箭头函数
var sum =()=>10+10
```

### 一个参数

只有一个参数的时候可省略括号

```
//传统写法
var test = function(x){
    return x+2;
}
//ES6写法
var test = x=>x+2;
```

### 多个参数

```
//传统写法
var total = values.reduce(function(a,b){
	return a+b; 
},0);
//ES6写法
var total = values.reduce((a,b)=>a+b,0);
```

### 包含多行代码

当函数中包含多行代码时用代码块括起来

```
//ES5
btn.onclick = function(e){
    e = e || window.event;
    var keCode = e.while||e.keyCode;
    console.log(keyCode);
};
//ES6
btn.onclick = e=>{
    e = e || window.event;
    var keyCode = e.while||e.keyCode;
    console.log(keyCode);
};
```

### 返回对象时

ES6中，紧随箭头的{被解析为块的开始，而不是对象的开始

当箭头函数返回一个普通对象时，需要将对象包裹在小括号里

```
//传统写法
var createPerson = function(){
    return {name:'xiaoming',age:18}
}
//ES6
var createPerson = ()=>{name:'xiaoming',age:18};//会报错
var createPerson = ()=>({name:'xiaoming',age:18});//需要加个小括号
```

### 默认参数

可以在函数中设置默认参数

```
var func1 = (x=1,y=2)=>x+y;
func1();//3
```

### 剩余参数

```
var func2 = (x,...args) => console.log(args);
func2(1,2,3);//[2,3]
```

### 箭头函数中的this值

箭头函数没有他自己的this值，箭头函数内的this值继承自外围作用域

## 七、Symbol数据类型

一个独一无二的值，一旦创建后无法更改，是一种类似字符串的数据类型，不能与其他类型的值进行运算，否则报错。

特性：独一无二，不可更改，不能运算，类似字符串

### 定义

#### 普通定义

```
var s1 = Symbol();
var s1 = Sumbol();

s1 === s2; //false

```

#### 带标识的定义

接受一个字符串作为参数，表示对Symbol实例的描述，主要是为了标识和区分，对调式非常有用 。

```
var s1 = Symbol('xiaoming');
var s2 = Symbol('xiaohong');
var s3 = Symbol('xiaoming');

s1 === s3; //false

```

#### Symbol.for()定义

定义变量使用同一个Symbol值 。

执行过程：查找是否存在，不存在=>登记 （创建）|| 存在=>应用

```
var s1 = Symbol.for('xiaoming');
var s2 = Symbol.for('xiaoming');

s1 === s2;//true

```

### 应用

#### 私有属性

可以给对象添加私有属性

```
var mySex = Symbol('mySex');
var objPerson = {
    name:'xiaoming',
    age:18,
    [mySex]:'男'
}
console.log(objPerson[mySex]);//男
```

## 八、Set集合

类似数组，但是里面的成员的是唯一的，可以自动去重。

特性：自动去重（恒等数据）

### 方法

add(value)：添加某个值

delete(value)：删除某个值，返回布尔值，表示删除成功

has(value)：返回一个布尔值，表示Set集合中是否存在该值

clear()：清除所有成员，没有返回值

```
let imgs = new Set();//定义
imgs.add(1);//添加
imgs.add(2);//添加
imgs.delete(2);//删除
imgs.has(1);//判断是否包含1，是返回true，否则为false
imgs.clear();//清空

```

### 去重数组

Set返回的不是一个数组，所以需要用Array.from()转换

```
let items = new Set([1,2,3,4,5,5,5]);
//Set->Array
Array.from(items);//[1,2,3,4,5]
```

## 九、Map映射（键值对）

js对象（Object）只能用字符串当作键(属性名)。这让它的使用有了很大的限制。所以ES6推出了一种类似于对象的数据集合：Map映射，它能让所有类型的数据作为属性名 

### 常用方法

set(key, value)

get(key)

has(key)

delete(key)

clear()

```
//创建
let map = new Map(); 

//设置
map.set("S0", "张三"); 
map.set("S1", "李四"); 
map.set("S2", "王五");

//获取
map.get("s2"); //王五

//判断
map.has('S2');//true

//删除
map.delete('S0');

//清空
map.clear();

```

### 遍历方法

keys() 获取所有键

values() 获取所有值

entries() 获取所有键值对，返回类数组

forEach()：遍历 Map 的所有成员。

循环遍历，配合解构赋值

```
//创建
let map = new Map(); 

//设置
map.set("S0", "张三"); 
map.set("S1", "李四"); 
map.set("S2", "王五");

//keys()
map.keys();//'S0','S1','S2'

//values()
map.values();//'张三','李四','王五'

//entries()
map.entries();//'S0':'张三','S1':'李四','S3':'王五'

//forEach
//value:值 key:键 map:map的引用
map.forEach(function(value,key,map){
    console.log(value,key,map);
});

//for...of
//for(let [key value] of map)
for(let item of map){
    console.log(item);
}
```

## 十、生成器函数 Generators

执行生成器函数，不会立刻执行里面的代码，而是得到一个暂停对象

### next()

执行next()后得到一个yield或return返回值组成的对象（包含value,done属性）

格式：{value:xx,done:false}

value：返回值

done：函数执行是否结束

```
function* sum(){
    console.log(1);
    yield 'xiaoming';
    console.log(2);
    yield 'xiaohong';
}

var gen = sum();
gen.next();// value:'xiaoming',done:false;
```

