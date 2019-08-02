# ECMAScript5(ES5)

## 支持ES5的浏览器

- Opera 11.60+
- Internet Explorer 9+
  - IE9不支持严格模式 
- Firefox 4+
- Safari 5.1+
- Chrome 13

## 加载事件

### DOM文档加载的步骤为

1. 解析HTML结构。
2. 加载外部脚本和样式表文件。
3. 解析并执行脚本代码。
4. DOM树构建完成。//DOMContentLoaded
5. 加载图片等外部文件。
6. 页面加载完毕。//window.onload

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

## ES5的严格模式

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

## JSON对象方法

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

## 获取元素节点

### querySelector(selector)

获取匹配选择器的第一个元素节点，返回DOM节点

### querySelectorAll(selector)

获取匹配选择器的所有元素，返回数组

## Function方法

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

## 其他

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

## Array新增方法

### 静态方法

#### Array.isArray()

判断是否为数组，返回true/false

```
var arr = [1,2,3,4,5];
Array.isArray(arr);//true
```

### 索引方法

#### indexOf/lastIndexOf

```
indexOf/lastIndexOf(keyword [,startIndex]);

keyword: 要查找的项，
startIndex：查找起点位置的索引，该参数可选，默认0
```

用途：判断数组中是否存在某个值

```
arr.indexOf(keyword)!=-1;
arr.indexOf(keyword)>=0;
```

### 迭代（遍历）方法

方法会把数组元素遍历一遍

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
var res = arr.every(function(item.idx){
	//当全部元素都满足条件是才会返回true
	//当有一个元素不满足条件就退出循环
    if(item>0){
        return true;
    }
});
console.log(res);//true
```

### 归并方法

#### reduce(fn,initVal)、reduceRight(fn,initVal)

fn：prev：前一次返回值

​	item：当前值

​	idx：索引值

​	arr：当前数组， 函数需要返回一个值，这个值会在下一次迭代中作为prev的值

initVal：迭代初始值（可选），如果缺省，prev的值为数组第一项

​		给定初始值，item从数组第一项开始

## String新增

### 获取索引

```
var str = 'hello';
str[3];//l
通过下标获取
```

### 删除前后空格

#### trim()

删除前后所有空格，返回新的字符串

## Date新增

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

