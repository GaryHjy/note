# Moment.js

## 介绍

官网：http://momentjs.cn/

对日期进行处理，可以转换成你想要的格式

## 安装

```
npm install --save moment
```

## 使用

```
//引入
var moment = require('moment');
moment().format();
```

### 1、日期格式化

```
moment().format('MMMM Do YYYY, h:mm:ss a'); // 十月 18日 2018, 8:31:13 早上
moment().format('dddd');                    // 星期四
moment().format("MMM Do YY");               // 10月 18日 18
moment().format('YYYY [escaped] YYYY');     // 2018 escaped 2018
moment().format();                          // 2018-10-18T08:31:13+08:00
```

### 2、相对时间

```
moment("20111031", "YYYYMMDD").fromNow(); // 7 年前
moment("20120620", "YYYYMMDD").fromNow(); // 6 年前
moment().startOf('day').fromNow();        // 9 小时前
moment().endOf('day').fromNow();          // 15 小时内
moment().startOf('hour').fromNow();       // 32 分钟前
```

### 3、日历时间

```
moment().subtract(10, 'days').calendar(); // 2018年10月8日
moment().subtract(6, 'days').calendar();  // 上周五早上8点32
moment().subtract(3, 'days').calendar();  // 本周一早上8点32
moment().subtract(1, 'days').calendar();  // 昨天早上8点32分
moment().calendar();                      // 今天早上8点32分
moment().add(1, 'days').calendar();       // 明天早上8点32分
moment().add(3, 'days').calendar();       // 本周日早上8点32
moment().add(10, 'days').calendar();      // 2018年10月28日
```

### 4、多语言支持

```
moment().format('L');    // 2018-10-18
moment().format('l');    // 2018-10-18
moment().format('LL');   // 2018年10月18日
moment().format('ll');   // 2018年10月18日
moment().format('LLL');  // 2018年10月18日早上8点32分
moment().format('lll');  // 2018年10月18日早上8点32分
moment().format('LLLL'); // 2018年10月18日星期四早上8点32分
moment().format('llll'); // 2018年10月18日星期四早上8点32分
```

更多内容可直接访问官网进行学习。