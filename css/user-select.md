做网页的时候，有些文字我们需要能被选中，有些我们不要能被选中，那么这就需要用到一个css属性了，那就是 user-select

```
user-select: none|auto|text|contain|all;
 
/*firefox浏览器*/
-moz-user-select: none|text|all;
 
/*safari、chrome浏览器*/
-webkit-user-select: none|text|all; /*Safari中不支持该属性值，只能使用none或者text，或者是在html的标签属性中使用*/
 
/*ie浏览器*/
-ms-user-select: none|text|element;
 
属性值：
none :  元素和子元素的文本将无法被选中

text :  文本可以被选中

auto :  文本将根据浏览器的默认属性进行选择

all  :  当所有内容作为一个整体时可以被选择。如果双击或者在上下文上点击子元素，那么被选择的部分将是以该子元素向上回溯的最高祖先元素

contain、element :  可以选择文本，但选择范围受元素边界的约束，也就是选择的文本将包含在该元素的范围内。只支持Internet Explorer

```