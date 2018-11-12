---
title: js使用正则获取当前页面url指定参数
copyright: false
date: 2018-11-09 16:48:34
categories: 工具
tags: 
- JavaScript
- 正则
- URL
---
```js
function QueryString(item) {
    var sValue = location.search.match(new RegExp("[\?\&]" + item + "=([^\&]*)(\&?)", "i"));
    return sValue ? sValue[1] : sValue;
}
```
<!-- more -->
## 示例
### 无参数
网址：`http://1.com/`  
调用：`QueryString('name')`  
返回：`null`
### 有参数
网址：`http://1.com/?name=cwj&age=21`  
调用：`QueryString('name')`  
返回：`cwj`
## 解析
### location
现在随便拿一个网址：`https://m.weibo.cn/u/5902368392?topnav=1&wvr=6&is_all=1&jumpfrom=weibocom`，这个网址的`location`是：

![](/img/tools1/location.png)

所以这个地址的`location.search`是`?topnav=1&wvr=6&is_all=1&jumpfrom=weibocom`，这就是需要执行匹配的字符串
### match
#### 定义
`match()`方法可在字符串内检索指定的值，或找到一个或多个正则表达式的匹配。
#### 返回值
存放匹配结果的数组。在这个方法中将匹配结果放在了数组`sValue`中。
### RegExp对象
`RegExp`对象表示正则表达式

该对象接受两个参数，第一个参数是一个字符串，指定了正则表达式的模式或其他正则表达式。第二个参数`i`代表着区分大小写的匹配。
### 正则
#### 匹配
- `[\?\&]`代表从`?`或`&`开始匹配
- `item`即传入的参数名
- `([^\&]*)`匹配到`&`为止，并把结果存放在数组`sValue`
- `(\&?)`匹配`&`零次或一次，并存放在数组`sValue`
#### 结果
调用该方法：`QueryString('wvr')`，根据以上正则表达式匹配出来的结果是：

![](/img/tools1/result.png)

要注意的是`match`方法返回的数组`0`位置是匹配的字符串，所以相应参数在`sValue[1]`中