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

内容溢出容器时的处理方式

visible 可见的

hidden 隐藏

scroll 出现滚动条

auto 内容溢出才出现滚动条

overflow-x 设置水平方向

overflow-y 设置垂直方向

当某一个方向的值不为visible，另外一个方向的值会自动设置auto
