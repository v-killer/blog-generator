---
title: HTML常见标签详解
date: 2018-08-28 14:25:13
tags:
---
### iframe标签
**嵌套页面**

````<iframe src="https://www.baidu.com" name="xxx"><iframe>````
#### 属性
1. `height`以像素格式指定frame的高度
2. `width`以百分比格式指定frame的宽度
3. `frameborder`取值为1时（默认值），告诉浏览器在当前iframe与其他iframe之间绘制边框，取0时则无需绘制此边框。（一般写做`frameborder="0"`）
4. `name`嵌入的浏览上下文框架的名称。该名称可以用作`<a>`标签,`<form>`标签的target属性值，或`<input>` 标签和 `<button>`标签的formtaget属性值
5. `src`嵌套页面的URL地址。（支持相对路径）

### a标签
跳转页面(HTTP GET 请求)
#### 属性
1. `target`属性

该属性指定在何处显示链接的资源。 取值为标签（tab），窗口（window），或框架（iframe）等浏览上下文的名称或其他关键词。以下关键字具有特殊的意义:
+ `_blank`新窗口打开
+ `_self`当前页面加载
+ `_parent`加载响应到当前框架的HTML4父框架或当前的HTML5浏览上下文的父浏览上下文。
+ `_top`加载响应进入顶层浏览上下文

2. `download`属性

此属性指示浏览器下载URL而不是导航到URL，因此将提示用户将其保存为本地文件。如果http响应的Content-type写成`Content-type: application/octet-stream`那么浏览器就会以下载的形式接受请求（无需使用download属性）

3. `href`属性
+ `<a href="//qq.com"></a>`a标签的无协议绝对地址，当前页面是什么协议，跳转页面是什么协议。
+ `<a href="#xxx"></a>`页面内跳转（不发起请求,除了锚点其余均发起请求)可以使用`href="#"`或`href="#"`链接返回页面顶部。
+ `<a href=?name=xxx></a>`浏览器发起`?name=xxx`的请求
+ `<a href=./xxx.html></a>`
+ `<a href="javascript: alert(1);"></a>`伪协议。　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　如果要写一个点击后不会跳转的ａ标签，可以写为`<a href="javascript:;"></a>`

### form标签
跳转页面(HTTP POST 请求)

+ 如果form表单里面没有提交按钮，就无法提交form。（除非你用JS）

#### 属性
1. `method`
+ `post`:指的是HTTP，表单数据会包含在表单体内然后发送给服务器。
+ `get`:表单数据会附加在 `action` 属性的URI中，并以 '?' 作为分隔符, 然后这样得到的 URI 再发送给服务器。

`action`  一个处理这个form信息的程序所在的URL。
### input标签
`<input>` 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据。
#### 属性
1. `type` 控件类型的显示。如果这个属性没有指定，默认的类型是 text。可用的值包括：
+ `submit`:用于提交表单的按钮
+ `button`无缺省行为按钮
+ `checkbox`:复选框。（多个复选框需要给同一个name）
+ `radio`:单选按钮。（多个单选按钮需要给同一个name,否则可以同时选中）
### button标签

#### 属性
1. `type` button的类型。可选值:
+ `submit`:此按钮提交表单数据给服务器。**未指定时，此值为默认值**
### label标签
它通常关联一个控件，或者是将控件放置在label元素内

`<label>用户名<input type="text name="xxx"></label>`
