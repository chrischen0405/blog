---
title: 【长期更新】前端试题整理
copyright: true
date: 2018-10-17 17:33:38
categories: 刷题ing
tags:
- HTML5
- CSS3
- JavaScript
- 前端
- 面试
---
有些刷题遇到的题目，怕以后忘记，整理起来可以方便回顾。
<!-- more -->

## HTML5
### 1.常见的浏览器端的存储技术有哪些
A.cookie  
B.localStorage  
C.session  
D.userData  
**答案**：ABD
**解析**：  
cookie 是靠谱的浏览器都支持；localStorge 比 cookie 存的更多，获取更方便，而且存储内容不会随请求发送给服务器；session 虽然需要 cookie 支持（通常存放加密过的 sessionId），但是不在浏览器端存放主要信息，排除；IE 支持 userData 存储数据，但是基本很少使用到，除非有很强的浏览器兼容需求。
### 2.下面哪些是HTML5 新增的表单元素
A.datalist  
B.optgroup  
C.output  
D.legend  
**答案**：A C  
**解析**：`datalist`元素规定输入域的选项列表。`keygen`元素的作用是提供一种验证用户的可靠方法。`output`元素用于不同类型的输出。

## CSS3
### 1.下面有关CSS sprites说法错误的是
A.允许你将一个页面涉及到的所有零星图片都包含到一张大图中去  
B.利用CSS的“background-image”，“background-repeat”，“background-position”的组合进行背景定位  
C.CSS Sprites虽然增加了总的图片的字节，但是很好地减少网页的http请求，从而大大的提高页面的性能  
D.CSS Sprites整理起来更为方便，同一个按钮不同状态的图片也不需要一个个切割出来并个别命名  
**答案**：C  
**解析**：CSS Sprites  
1.简介  
CSS Sprites在国内很多人叫css精灵，是一种网页图片应用处理方式。它允许将一个页面涉及到的所有零星图片都包含到一张大图中， 利用CSS的“background-image”，“background- repeat”，“background-position”的组合进行背景定位， 访问页面时避免图片载入缓慢的现象。  
2.优点  
（1）CSS Sprites能很好地减少网页的http请求，从而大大的提高页面的性能，这是CSS Sprites最大的优点，也是其被广泛传播和应用的主要原因；  
（2）CSS Sprites能减少图片的字节；  
（3）CSS Sprites解决了网页设计师在图片命名上的困扰，只需对一张集合的图片命名，不需要对每一个小图片进行命名，从而提高了网页制作效率。  
（4）CSS Sprites只需要修改一张或少张图片的颜色或样式来改变整个网页的风格。  
3.缺点  
（1）图片合并麻烦：图片合并时，需要把多张图片有序的合理的合并成一张图片，并留好足够的空间防止版块出现不必要的背景。  
（2）图片适应性差：在高分辨的屏幕下自适应页面，若图片不够宽会出现背景断裂。  
（3）图片定位繁琐：开发时需要通过工具测量计算每个背景单元的精确位置。  
（4）可维护性差：页面背景需要少许改动，可能要修改部分或整张已合并的图片，进而要改动css。在避免改动图片的前提下，又只能（最好）往下追加图片，但这样增加了图片字节。  
### 2.下述有关border:none以及border:0的区别，描述错误的是
A.border:none表示边框样式无  
B.border:0表示边框宽度为0  
C.当定义了border:none，即隐藏了边框的显示，实际就是边框宽度为0  
D.当定义边框时，仅设置边框宽度也可以达到显示的效果  
**答案**：C,D  
**解析**：  
C:当定义border:none时，表示无边框样式，浏览器并不会对边框进行渲染，也就没有实际的宽度；  
D:定义边框时，除了设置宽度外，还必须设置边框的样式才能显示出来。
### 3.下面哪条声明能固定背景图片
A.background-attachment:fixed;  
B.background-attachment:scroll;  
C.background-origin: initial;  
D.background-clip: initial;  
**答案**：A
**解析**：  
- `background-attachment`有三个值：  
`scroll`是默认值，背景图像会随着页面其余部分的滚动而移动。  
`fixed`当页面的其余部分滚动时，背景图像不会移动。  
`inherit`规定应该从父元素继承`background-attachment`属性的设置。
- `background-origin`属性规定`background-position`属性相对于什么位置来定位。
- `background-clip`属性规定背景的绘制区域。
### 4.重绘与回流的区别
**解析**：
- repaint(重绘) ，`repaint`发生更改时，元素的外观被改变，且在**没有改变布局**的情况下发生，如改变`outline`,`visibility`,`background color`，不会影响到dom结构渲染。
- reflow(回流)，与`repaint`区别就是他会**影响到dom的结构渲染**，同时他会触发`repaint`，他会改变他本身与所有父辈元素(祖先)，这种开销是非常昂贵的，导致性能下降是必然的，页面元素越多效果越明显。


## JavaScript
### 1.下列js可以让一个input的背景颜色变成红色的是
A.inputElement.style.backgroundColor = 'red';  
B.inputElement.backgroundColor = 'red';  
C.inputElement.style.backgroundColor = '#0000';  
D.inputElement.backgroundColor = '#0000';  
**答案**：A  
**解析**：  
1.获取元素可以借助`document.getElementById()`/`document.getElementsByTagName()`等若干方法，也可以利用层级关系（父子关系、兄弟关系等）。而这一点题目已经直接略过了，它直接给出了该元素的引用名称`inputElement`。  
2.通过js来改变元素样式的两个最常见的API为：`style`、`className`。使用`style`接口一次只能改变一个样式，而使用`className`则可以同时改变多个样式，当然前提是已经用css定义该类名的相关样式。  
3.backgroundColor? background-color?  
在使用点运算符时，浏览器看到`-`就没法正确解析了，在那种情况下，只能将该变量使用驼峰命名法来表示。而使用方括号表示法，`-`被理解为字符串中的内容，该字符串能被正确解析。  
eg:
```js
inputElement.style.backgroundColor = 'red'; // 这是没问题的
inputElement.style.background-color = 'red'; // 这是错的
inputElement.style["background-color"] = 'red'; // 这也是可以的
```
4.表示红色有若干种方法:  
- 颜色名：red
- 百分数：rgb(100%, 0%, 0%)
- 数值：rgb(255, 0, 0)
- 十六进制：#FF0000
- 简写的十六进制：#F00
### 2.页面有一个按钮button id为 button1，通过原生的js如何禁用？(IE 考虑IE 8.0以上版本)
document.A.getElementById("button1").readolny= true;  
document.B.getElementById("button1").setAttribute(“readolny”,”true”);  
document.C.getElementById("button1").disabled = true;  
document.D.getElementById("button1").setAttribute(“disabled”,”true”);  
**答案**：C D  
**解析**：`disabled`和`readOnly`都是表单的公有属性，`readOnly`是只读，`disabled`是禁用。  
`setAttribute`在ie7以前是不能通过`style`和`class`设置属性的