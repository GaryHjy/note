# PHP

## 语法

### 一、分界提示符

```
<?php//开始
	//php代码
?>//结束
```

### 二、注释

单行注释：//

多行注释：/**/

### 三、输出语句

echo：可以输出一个或多个字符串（字符串可以包含HTML标签），速度较快，一般用于向前端返回数据 

```
<?php
	//输出一个字符
	echo "Hello world!<br>";
	//输出多个字符
	echo "This", " string", " was", " made", " with multiple parameters.";
?>
```

print_r：打印关于变量的信息，适用于数组、对象的打印，一般用于测试 

var_dump：判断一个变量的类型与长度,并输出变量的数据类型和数值，一般用于测试 

### 四、变量

#### 命名规则

- 以 $ 符号开始，后面跟着变量的名称（$称为标识符，不属于变量组成部分）

- 只能包含字母数字字符以及下划线（A-z、0-9 和 _ ）

- 必须以字母或者下划线字符开始

- 不能包含空格

- 区分大小写

```
//PHP 没有声明变量的命令。
//变量在第一次赋值时被创建：
<?php
    $txt="Hello world!";
    $x=5;
    $y=10.5;
?>
```

#### 作用域

全局变量：在函数外部定义的变量，称为全局变量，全局变量可以在任意位置访问 

1、在函数中访问全局变量 

$GLOBALS 格式：`$GLOBALS[变量名]`，其中变量名不带$。 

```
<?php
    $x='global x';
    function myTest(){
        //echo $x;//报错

        //正确写法
        echo $GLOBALS['x'];

        //在函数中创建全局变量
        $GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];
    } 
    myTest();
    echo $y;
?>
```

global 关键字 

```
 <?php
        $x=5;
        $y=10;
        function myTest(){
            global $x,$y;
            $y=$x+$y;
        }
        myTest();
        echo $y; // 输出 15
?>
```

局部变量：函数内部声明的变量是局部变量，仅能在函数内部访问 

#### 超级全局变量

- `$GLOBALS` 是PHP的一个包含所有全局变量的数组，可以在任意位置使用
- `$_SERVER` 是一个包含了头信息(header)、路径(path)等信息的数组
- `$_POST / $_GET` 被广泛应用于收集表单数据，常用于ajax请求等操作
- `$_COOKIE` 用于收集前端发送过来的cookie数据
- `$_REQUEST` 变量包含了 `$_GET、$_POST 和 $_COOKIE` 的内容
- `$_SESSION` 服务器版cookie
- `$_FILES`

### 五、常量

#### 规范

- 命名规则与变量一致，但常量名不需要加 $ 修饰符。
- 常量值被定义后，在脚本的其他任何地方都不能被改变。
- 默认是全局作用域，可以在整个运行的脚本的任何地方使用。
- 常量名建议全部大写

#### 格式

 `define(name,value)` 

- name：必选参数，常量名称，即标志符。

- value：必选参数，常量的值。

```
define("EN_NAME", "laoxie");
```

### 六、运算符

#### 算术运算符

- +, -, *, /, %

#### 赋值运算符

- =

#### 递增/递减运算符

- ++
- --

#### 比较运算符

- 等于：`x == y`
- 恒等于：`x === y`
- 不等于：`x != y` ，`x <> y`
- 不恒等于：`x !== y`
- 大于：`x > y`
- 小于：`x < y`
- 大于等于：`x >= y`
- 小于等于：`x <= y`

#### 逻辑运算符

- 与：`x and y`，`x && y`
- 或：`x or y`，`x || y`
- 异或：`x xor y`
- 非：`!x`

#### 三元运算符 

格式：`expr1 ? expr2 : expr3`

### 七、条件语句

- if语句
- switch语句

### 八、循环语句

- while
- do…while
- for

## 数据类型

- String（字符串）
- Integer（整型）
- Float（浮点型）
- Boolean（布尔型）
- Array（数组）
- Object（对象）
- NULL（空值）

### String

并置运算符“.” 

```
<?php 
    $txt1="你是我的小呀小苹果"; 
    $txt2="怎么爱你都不嫌多"; 
    echo $txt1 . ", " . $txt2; 
?>
```

- strlen()

- mb_strlen() 获取字符串长度，得到的字符的字节数

- strpos() 查找某个字符在字符串中的索引，如果未找到匹配，则返回 false

   `strpos("Hello world!","world");//=>6`

### Array

数组是一个能在单个变量中存储多个值的特殊变量 

#### 类型

- 数值数组 - 带有数字索引值的数组
- 关联数组 - 带有指定的键的数组，每个键关联一个值
- 多维数组 - 包含一个或多个数组的数组

#### 创建数组

使用array()函数创建 

```
//数值数组
$cars=array("Volvo","BMW","Toyota");

//关联数组
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
```

#### 数组方法 

- count() 获取数组长度
- in_array() 判断某个值是否存在数组中
- array_slice() 从数组中取出一段
- array_rand() 随机获取索引值

#### 遍历数组 

- for 一般用于遍历数值数组

- foreach() 一般用于遍历关联数组

  ```
  <?php
      //遍历数值数组：for循环
      $cars=array("Volvo","BMW","Toyota");
      $arrlength=count($cars);
      for($x=0;$x<$arrlength;$x++){
          echo $cars[$x] . "<br>";
      }
  
      //遍历关联数组：foreach..as
      $age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
      foreach($age as $x=>$x_value){
          echo "Key=" . $x . ", Value=" . $x_value;
          echo "<br>";
      }
  ?>
  ```

#### 数组排序 

- sort() 对数组进行升序排列
- rsort() 对数组进行降序排列
- asort() 根据关联数组的值，对数组进行升序排列
- ksort() 根据关联数组的键，对数组进行升序排列
- arsort() 根据关联数组的值，对数组进行降序排列
- krsort() 根据关联数组的键，对数组进行降序排列

## 函数

### 内建函数

PHP 的真正威力源自于它的函数。在 PHP 中，提供了超过 1000 个内建的函数 

### 自定义函数

参数

- 参数默认值

return返回值 

```
function add($x,$y){
    $total=$x+$y;
    return $total;
}
```

## 面向对象

### 类

#### 定义一个类 

- 类使用 class 关键字后加上类名定义。
- 类名后的一对大括号{}内可以定义变量和方法。
- 类的变量使用 var 来声明, 变量也可以初始化值。
- 函数定义类似 PHP 函数的定义，但函数只能通过该类及其实例化的对象访问。

```
<?php
    class Person{
        // 成员属性
        var $name;
        var $age = 18;

        //成员方法
        function setName($name){
            $this->name = $name;
        }

        function getAge(){
            return $this->age;
        }
    }
?>
```

#### 实例化对象

 `$p = new Person();` 

#### 调用成员属性/方法 

在实例化对象后，我们可以使用‘->’操作该对象调用成员属性/方法 

```
$p->setName('老谢');
$p->name;
```

#### 构造函数

 __construct构造函数是一种特殊的方法。主要用来在创建对象时初始化对象，写在创建对象的语句中。 

```
class Web{
    function __construct( $par1, $par2 ) {
       $this->url = $par1;
       $this->title = $par2;
    }
}
```

#### 指针对象 

$this 

```
this是指向对象实例的一个指针 
```

### 继承

使用关键字 extends 来继承一个类，继承后子类就拥有父类的属性和方法（私有除外），格式如下： 

```
class Man extends Person {
    // 添加成员函数
    function setAge($age){
        $this->age = $age;
    }

    //重写方法
    function setName($name){
        $this->name = $name;
        return $name;
    }
}
```

### 本地数据库操作

#### 文件的读取与写入

fopen(path,mode)：打开文件 **使用fopen函数打开文件时，你首先需要明确：** 

- 文件模式（mode）
  - `r` 以只读方式打开文件，从文件头开始读
  - `r+` 以读写方式打开文件，写入时以追加的方式写入文件
  - `w` 以写入方式打开文件，从文件头开始写。如果文件不存在则尝试创建，如果文件存在，则先删除文件中的内容
  - `w+` 以读写方式打开文件，从文件头开始读写。如果文件不存在则尝试创建，如果文件存在，则先删除文件中的内容
  - `a` 以写入方式打开，从文件末尾开始追加写。如果文件不存在则尝试创建
  - `a+` 以读写方式打开，从文件末尾开始追加写入或者读。如果文件不存在则尝试创建。

- fread(file,length)：读取内容
- fwrite(file,content)：写入内容
- fclose()：关闭文件,避免资源占用
- filesize(path)：读取文件字符长度

```
  //以读取模式打开文件
    $myfile = fopen('./data/weibo.json', 'r');

    //读取文件内容
    $content = fread($myfile, filesize('./data/weibo.json'));

    //关闭文件，减少资源占用
    fclose($myfile);
```

#### 直接返回数据

json_encode(); 把数组转成字符串

- php5.4+ 使用`JSON_UNESCAPED_UNICODE`防止中文转义

json_decode(json,assoc); 把字符串转成数组/对象

- json：待解码的 json string 格式的字符串
- assoc：默认false,返回object, 当该参数为 true 时，将返回array

### 远程数据操作

ajax跨域请求之服务端代理（爬虫） 原理：获取页面所有内容，并利用正则匹配所需内容

- file_get_contents($url)
- preg_match_all($reg,$str,$res)
- preg_match($reg,$str,$res)
- iconv(current,target,$content);