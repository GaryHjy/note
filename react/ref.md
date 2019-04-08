#### ref

ref推荐使用函数的方法：

* 字符串方式
```
<Son ref="son"></Son>
//

this.refs.son
```
* 函数方式(推荐)

```
<Son ref={(el)=>{this.son = el}}></Son>

//

this.son
```
