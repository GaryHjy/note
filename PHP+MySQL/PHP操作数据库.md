# php操作数据库

## 连接 MySQL

PHP 5 及以上版本建议使用以下方式连接 MySQL : 

### MySQLi extension

 (“i” 意为 improved)

安装：Linux 和 Windows: 在 php5 mysql 包安装时 MySQLi 扩展多数情况下是自动安装 

```
 <?php
        $servername = "localhost";
        $username = "username";
        $password = "password";
        $dbname = 'user';

        // 创建连接
        $conn = new mysqli($servername, $username, $password, $dbname);

        // 检测连接
        if ($conn->connect_error) {
            die("连接失败: " . $conn->connect_error);
        } 

        //查询前设置编码，防止输出乱码
        $conn->set_charset('utf8');

        echo "连接成功";
    ?>
```

### 执行sql语句查询结果集 

```
    //编写sql语句
    $sql = 'select * from student';

    //获取查询结果集
    $result = $conn->query($sql);

    //使用查询结果集
    //得到数组
    $row = $result->fetch_all(MYSQLI_ASSOC);

    //释放查询结果集，避免资源浪费
    $result->close();

    //把结果输出到前台
    echo json_encode($row);

    // 关闭数据库，避免资源浪费
    $conn->close();
```

## 插入数据

> INSERT INTO 

### 单条数据 

```
$sql = "INSERT INTO MyGuests (firstname, lastname, email)
VALUES ('John', 'Doe', 'john@example.com')";

if ($conn->query($sql)) {
	echo "新记录插入成功";
} else {
	echo "Error: " . $sql . "<br>" . $conn->error;
}
```

### 多条数据 

```
$sql = "INSERT INTO `projects` (`name`, `url`, `description`) VALUES ";
foreach ($projects as $item) {
	$sql .= "('$item',NULL, NULL),";
}
$sql = substr($sql,0,-1);

if ($conn->query($sql)) {
	echo "新记录插入成功";
} else {
	echo "Error: " . $sql . "<br>" . $conn->error;
}
```

## 读取数据

> SELECT…FROM

得到查询结果集 

- num_rows ：结果集中的数量，用于判断是否查询到结果
- fetch_all(MYSQLI_ASSOC) 得到所有结果
- fetch_assoc() 得到第一个结果
- fetch_row()

```
$sql = "SELECT id, firstname, lastname FROM MyGuests";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    // 输出每行数据
    while($row = $result->fetch_assoc()) {
    	echo "<br> id: ". $row["id"]. " - Name: ". $row["firstname"]. " " . $row["lastname"];
    }
}else{
    echo "0 个结果";
}
```

## mySQL语句返回值

返回布尔值

- insert
- update
- delete

返回查询结果集

- select语句







