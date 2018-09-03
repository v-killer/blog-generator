---
title: 初识HTML
date: 2018-08-27 15:11:19
tags:
---
## w3c
万维网联盟（World Wide Web Consortium，W3C），又称W3C理事会，是万维网的主要国际标准组织,
由蒂姆·伯纳斯-李于1994年10月离开欧洲核子研究中心（CERN）后成立。
### 李爵士
蒂莫西·约翰·伯纳斯-李爵士英语：Sir Timothy John Berners-Lee，英国计算机科学家。他是万维网的发明者。1990年12月25日，他成功利用互联网实现了HTTP客户端与服务器的第一次通讯。
### MDN
MDN Web Docs是一个汇集众多Mozilla基金会产品和网络技术开发文档的免费网站。
### HTML
1. #### HTML的版本（W3C组织制定规范）
 
	①.HTML4.01

	②.XHTML
	
	③.HTML5
	
	④HTML5.1
2. #### 规范文档(Specifications)
	
    ①.由W3C写文档（李爵士）
	
    ②.W3C根据浏览器的实际情况总结文档，并不是凭空想象
3. #### DOCTYPE
 
	①.用来选择文档类型
	
    ②.除了HTML5的DOCTYPE，其他的都很难记：[查看其他的DOTCYPE](https://www.w3.org/QA/2002/04/valid-dtd-list.html)
	
    ③.如果你没写DOCTYPE,那你就惨了
4. #### 省略标签
	
    ①head、body、html标签可省略（如果标签为空）
	
    ②浏览器会自动补上省略的标签
5. #### 如何查看MDN文档
	
    ①Googel：关键词+MDN
	
    ②切换成中文
6. #### 空元素
	一个空元素（empty element）可能是 HTML，SVG，或者 MathML 里的一个不可能存在子节点（例如内嵌的元素或者元素内的文本）的element。
	
    在 HTML 中，通常在一个空元素上使用一个闭标签是无效的。
	
    在 HTML 中有以下这些空元素：`<area>` `<base>` `<br>` `<col>` `<command>` `<embed>` `<hr>` `<img>` `<input>` `<keygen>` `<link>` `<meta>` `<param>` `<source>` `<track>` `<wbr>`
7. #### 可替换元素
	CSS 里，可替换元素（replaced element）的展现不是由CSS来控制的。这些元素是一类 外观渲染独立于CSS的 外部对象。 
    典型的可替换元素有 `<img>`、 `<object>`、 `<video>` 和 表单元素，如`<textarea>`、 `<input>` 。 
    
    某些元素只在一些特殊情况下表现为可替换元素，例如 `<audio>` 和 `<canvas>` 。 通过 CSS content 属性来插入的对象 被称作 匿名可替换元素（anonymous replaced elements）。

    CSS在某些情况下会对可替换元素做特殊处理，比如计算外边距和一些auto值。

    需要注意的是，一部分（并非全部）可替换元素，本身具有尺寸和基线（baseline），会被像vertical-align之类的一些 CSS 属性用到。
8. 命令 `whois` 可以查看某个域名拥有者的身份