# MySQL	

## MySql的特点

MySql是目前最流行的关系型数据库管理系统，由瑞典MySQL AB公司开发，目前属于Oracle公司 

- MySQL是开源的，免费。
- MySQL支持标准的SQL数据语句
- MySQL可以允许于多个系统上，并且支持多种语言。这些编程语言包括C、C++、Python、Java、Perl、PHP、Eiffel、NodeJS、Ruby和Tcl等。
- MySQL对PHP有很好的支持，PHP是目前最流行的Web开发语言。
- MySQL支持大型数据库，支持5000万条记录的数据仓库，32位系统表文件最大可支持4GB，64位系统支持最大的表文件为8TB。

## 数据库操作

### 表操作

#### 连接数据库

格式：`mysql -h主机地址 -u用户名 -p用户密码`

#### 显示所有数据库

格式：`show databases;`

#### 创建数据库

格式：`create database <数据库名>;`

#### 使用数据库

格式：`use <数据库名>;`

#### 显示当前数据库所有表

格式：`show tables;`

#### 创建数据表

格式：`create table <表名> (<字段名1> <类型1> [,..<字段名n> <类型n>]);`

```
  create table MyGuests (
    id int(6) unsigned auto_increment primary key, 
    firstname varchar(30) not null,
    lastname varchar(30) not null,
    email varchar(50),
    reg_date timestamp
    )
```

以上创建一个名为 “MyGuests” 的表，包含5个列： “id”, “firstname”, “lastname”, “email” 和 “reg_date”，参数如下： 

##### 数据类型

- INT(整型),
- FLOAT(浮点),
- CHAR(固定长度字符串),
- VARCHAR(可变长度字符串),
- BLOB(二进制),
- TEXT(字符串)
- TIMESTAMP(时间戳)

##### 列的其他属性

- NOT NULL - 每一行都必须含有值（不能为空），null 值是不允许的。
- DEFAULT value - 设置默认值
- UNSIGNED - 使用无符号数值类型，0 及正数
- AUTO_INCREMENT - 设置 MySQL 字段的值在新增记录时每次自动增长 1
- PRIMARY KEY - 设置数据表中每条记录的唯一标识。 通常列的 PRIMARY KEY 设置为 ID 数值，与 AUTO_INCREMENT 一起使用。

#### 删除表

 格式：`drop table <表名>;` 

```
drop table MyGuests;
drop table if exists MyGuests
```

#### 查询表结构

 `desc MyGuests` 

#### 修改表名

 `rename table MyClass to YouClass;` 

#### 增加字段

 `alter table MyGuests add sku_id bigint(20) unsigned DEFAULT NULL COMMENT '商品销售码';` 

#### 复制表结构

 `create table table1 like table;` 

### 数据操作

#### 插入数据

格式：`insert into <表名> [(<字段名1>[,..<字段名n > ])] values ( 值1 )[, (值n )];` 

```
//单条数据
insert into MyGuests (firstname, lastname, email)
values ('John', 'Doe', 'john@example.com')
```

#### 删除表数据

格式：delete from 表名 where 表达式 

```
//删除MyGuests表中id为1的数据
DELETE FROM MyGuests where id=1;

//删除所有数据
DELETE FROM MyGuests
```

#### 查询表中的数据

格式： select <字段1, 字段2, …> from < 表名 > where < 表达式 >; 

select一般配合where使用，以查询更精确更复杂的数据。 

```
//查看表 MyGuests 中所有数据
select * from MyGuests;

//查看表 MyGuests 中前10行数据：
select * from MyGuests order by id limit 0,10;
```

#### 修改表中的数据

格式：update 表名 set 字段=新值,… where 条件; 

```
update MyGuests set name='Mary' where id=1;
```

#### 条件控制语句 

WHERE 语句：

> SELECT * FROM tb_name WHERE id=3;

相关条件控制符：

- =、>、<、<>、IN(1,2,3......)、BETWEEN a AND b
- AND、OR、NOT
- LIKE用法中
  - % 匹配任意、
  - _ 匹配一个字符（可以是汉字）

- LIMIT idx,qty：数量控制
  - SELECT * FROM goods LIMIT 2,5

- IS NULL 空值检测
- 排序ORDER BY
  - asc 升序（默认）
  - desc 降序
