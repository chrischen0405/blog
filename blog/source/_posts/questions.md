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

### 1.下面哪些是HTML5 新增的表单元素
A.datalist  
B.optgroup  
C.output  
D.legend  
**答案**：A C  
**解析**：`datalist`元素规定输入域的选项列表。`keygen`元素的作用是提供一种验证用户的可靠方法。`output`元素用于不同类型的输出。
### 2.HTML5新增的布局标签
`header`、`hgroup`、`nav`、`aside`、`section`、`article`、`footer`、`figure`、`menu`
### 3.给定下面的 HTML 代码：
```html
<div id=”wrapper”>
<div class=”wText”>…</div>…<!--more wText items here -->
<div class=”wImg”>…</div>…<!--more wImg items here -->
<div class=”wVideo”>…</div>…<!--more wVideo items here -->
</div>
```
怎么能够取得 ”wrapper” 中全部项的集合？  
A.$(‘#wrapper’).children();  
B.$(‘#wrapper’).html();  
C.$(‘#wrapper’).contents();  
D.$(‘#wrapper’).find(“all”);  
**答案**：C  
**解析**：  
```js
$(‘#wrapper’).children();  //（只沿着 DOM 树向下遍历单一层级）查询直接的子元素。而不管子元素的子元素。
$(‘#wrapper’).html();  //返回的是dom结构。而不是集合
$(‘#wrapper’).find(“all”);   //并没有all这个元素
```
### 4.span标签的width和height分别为多少？
```html
<div style=”width:400px;height:200px;”>
  <span style=”float:left;width:auto;height:100%;”>
           <i style=”position:absolute;float:left;width:100px;height:50px;”>hello</i>
  </span>
</div>
```
A.width = 0px，height = 0px  
B.width = 400px，height = 200px  
C.width = 100px，height = 50px  
D.width = 0px，height = 200px  
**答案**：D  
**解析**：`span`标签无法设置宽高，但是`float`会把浮动元素变成块级元素，`span`元素继承父元素的`height`的高度`200px`，由于i设置为绝对定位会脱离原先的文档流，`span`元素`width`设置为`auto`，所以会变`0`
### 5.`input`属于窗体元素,层级显示比`flash`、其它元素都高。请判断这句话的正确与否。
错误，在`html`中，帧元素（`frameset`）的优先级最高，表单元素比非表单元素的优先级要高。  
表单元素包括：文本输入框，密码输入框，单选框，复选框，文本输入域，列表框等等；  
非表单元素包括：连接（`a`），`div`，`table`，`span`等。  
所有的`html`元素又可以根据其显示分成两类：有窗口元素以及无窗口元素。有窗口元素总是显示在无窗口元素的前面。  
有窗口元素包括：`select`元素，`object`元素，以及`frames`元素等等。  
无窗口元素：大部分`html`元素都是无窗口元素。  


## CSS3   
### 1.下述有关border:none以及border:0的区别，描述错误的是
A.border:none表示边框样式无  
B.border:0表示边框宽度为0  
C.当定义了border:none，即隐藏了边框的显示，实际就是边框宽度为0  
D.当定义边框时，仅设置边框宽度也可以达到显示的效果  
**答案**：C,D  
**解析**：  
C:当定义border:none时，表示无边框样式，浏览器并不会对边框进行渲染，也就没有实际的宽度；  
D:定义边框时，除了设置宽度外，还必须设置边框的样式才能显示出来。
### 2.下面哪条声明能固定背景图片
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

### 3.重绘与回流的区别
**解析**：
- repaint(重绘) ，`repaint`发生更改时，元素的外观被改变，且在**没有改变布局**的情况下发生，如改变`outline`,`visibility`,`background color`，不会影响到dom结构渲染。
- reflow(回流)，与`repaint`区别就是他会**影响到dom的结构渲染**，同时他会触发`repaint`，他会改变他本身与所有父辈元素(祖先)，这种开销是非常昂贵的，导致性能下降是必然的，页面元素越多效果越明显。
### 4.盒子模型
**解析**：  
CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容：
- **Margin(外边距)** - 清除边框外的区域，外边距是透明的。
- **Border(边框)** - 围绕在内边距和内容外的边框。
- **Padding(内边距)** - 清除内容周围的区域，内边距是透明的。
- **Content(内容)** - 盒子的内容，显示文本和图像。  
盒子模型分为普通盒子模型和怪异盒子模型，大多数浏览器的元素内容占据的空间是由`width`属性设置的，而内容周围的`padding`和`border`值是另外计算的。然而`IE 5`和`IE 6`的呈现却是不正确的。它们在怪异模式中使用自己的非标准模型，浏览器中元素的`width`属性不是内容的宽度，而是内容、内边距和边框的宽度的总和。


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
A.document.getElementById("button1").readolny= true;  
B.document.getElementById("button1").setAttribute(“readolny”,”true”);  
C.document.getElementById("button1").disabled = true;  
D.document.getElementById("button1").setAttribute(“disabled”,”true”);  
**答案**：C D  
**解析**：`disabled`和`readOnly`都是表单的公有属性，`readOnly`是只读，`disabled`是禁用。`readOnly`只针对`input(text/password)`和`textarea`有效，而`disabled`对于所有的表单元素都有效，包括`select, radio, checkbox, button`等。  
`setAttribute`在ie7以前是不能通过`style`和`class`设置属性的
### 3.`[“1", "2", "3"].map(parseInt)`的执行结果是？
**答案**：[1, NaN, NaN]  
**解析**：通常使用parseInt时,只需要传递一个参数。但实际上,parseInt可以有两个参数，第二个参数是进制数
### 4.下列代码存在几个变量没有被回收？
```js
var i = 1;
var i = 2;
var add = function() {
    var i = 0;
    return function()
{
        i++;
        console.log(i);
    }
}();
add();
```
**答案**：3  
**解析**：  
变量回收规则：
- 全局变量不会被回收。
- 局部变量会被回收，也就是函数一旦运行完以后，函数内部的东西都会被销毁。
- 只要被另外一个作用域所引用就不会被回收（闭包）

全局变量不会被回收，但是会被覆盖，所以第一个`i`被第二个`i`覆盖了，第二个`i`没有被回收，变量`add`被赋值了一个匿名函数，所以也没有被回收。虽然局部变量会被回收，但是`add`函数中形成了一个闭包，所以里面的变量`i`也不会被回收。
### 5.以下代码的输出结果是
```js
var f = function g() {
        return 23;
    };
typeof g();
```
A."number"  
B."undefined"  
C."function"  
D.Error  
**答案**：D  
**解析**：  
js定义函数的方法：  
1、函数声明：```function foo(){...}```  
2、函数表达式：```var foo = function(){...}```  
3、构造函数：```var foo = new Function(...)```  
除此以外，类似```var foo = function bar(){...}```这样的定义函数的方法就是第二种函数表达式，在函数外部无法通过`bar`访问到函数，因为这已经变成了一个表达式。所以`g`就是`undefined`，`g()`就会抛出异常。
### 6.javascirpt中的数字在计算机内存储为多少Byte？
8Byte，Javascript中，由于其变量内容不同，变量被分为基本数据类型变量和引用数据类型变量。基本类型变量用八字节内存，存储基本数据类型(数值、布尔值、null和未定义)的值，引用类型变量则只保存对对象、数组和函数等引用类型的值的引用(即内存地址)。
### 7.```+new Array(017)```输出？
`+`是一元运算符，无运算效果，但是可以将字符串等转为`number`类型，`017`是八进制，故而是`Array(15)`，这里相当于对于一个未赋值但是长度为15的数组进行`number`类型转化，其结果为`NaN`


## 浏览器
### 1.常见的浏览器端的存储技术有哪些
A.cookie  
B.localStorage  
C.session  
D.userData  
**答案**：ABD  
**解析**：cookie 是靠谱的浏览器都支持；localStorge 比 cookie 存的更多，获取更方便，而且存储内容不会随请求发送给服务器；session 虽然需要 cookie 支持（通常存放加密过的 sessionId），但是不在浏览器端存放主要信息，排除；IE 支持 userData 存储数据，但是基本很少使用到，除非有很强的浏览器兼容需求。


## 网络
### 1.HTTP状态码
常见HTTP状态码：
- 200 - 请求成功
- 301 - 资源（网页等）被永久转移到其它URL
- 404 - 请求的资源（网页等）不存在
- 500 - 内部服务器错误

HTTP状态码分类：
- 1**   信息，服务器收到请求，需要请求者继续执行操作
- 2**   成功，操作被成功接收并处理
- 3**   重定向，需要进一步的操作以完成请求
- 4**   客户端错误，请求包含语法错误或无法完成请求
- 5**   服务器错误，服务器在处理请求的过程中发生了错误

### 2.GET和POST的区别
- （1）GET请求在浏览器回退时是无害的，POST会再次提交请求
- （2）GET请求会被浏览器主动缓存，而POST不会，除非手动设置
- （3）GET请求参数会被完整的保留在浏览器历史记录里，而POST中的参数不会被保留
- （4）GET请求在URL中传递的参数是有长度限制的（不固定，因浏览器决定），而POST没有限制
- （5）GET请求参数通过URL传递，而POST放在request.body上
- （6）GET请求产生的URL地址可以被收藏，而POST不可以
- （7）GET请求只能进行URL编码，而POST支持多种编码方式
- （8）GET请求只接受ASC2字符，而对参数的数据类型POST没有限制
- （9）GET请求比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感数据

## 其他
### 1.哪些操作会造成内存泄漏？
1、闭包引起的内存泄漏；  
2、意外的全局变量引起的内存泄漏；  
3、没有清理的DOM元素引起的内存泄漏   
4、被遗忘的定时器或者回调函数；  
5、子元素存在引用引起的内存泄漏；