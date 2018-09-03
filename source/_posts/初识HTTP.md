---
title: 初识HTTP
date: 2018-08-26 17:20:19
tags:
---
### HTTP
**HTTP**全称 *HyperText Transfer Protocol* **即超文本传输协议**
是一种用于分布式、协作式和超媒体信息系统的应用层协议。HTTP是万维网的数据通信的基础。

**HTML** 全称：*HyperText Markup Language* 即**超文本标记语言**
是一种用于创建网页的标准标记语言。

**URI** 全称：*Uniform Resource Identifier*即**统一资源标识符**

**URI**分为**URL**和**URN** 我们一般使用URL作为**网址**

**URN**全称：*Uniform Resource Name* 即**统一资源名称**
通过**URN**可以确定一个【唯一的】资源

**URL** 全称：*Uniform Resource Locator* 即**统一资源定位符**
通过**URL**可以确定一个【唯一的】地址（网址）

例如：`https://www.baidu.com/s?wd=hello&rsv_spt=1#5` 就是一个 URL

![](https://user-gold-cdn.xitu.io/2018/5/23/1638c9eb2da7c13b?w=2298&h=878&f=png&s=418072)

#### 域名
以`www.baidu.com`为例
- `.com`或`.cn`或`.tt` 为一级域名（顶级域名）。
- `baidu.com`为二级域名。
- `www.baidu.com`为三级域名。
- `www.baidu.com`和`baidu.com`共有一个二级域名。

#### DNS
**DNS** 全称 *Domain Name System* 即**网域名称系统**。
它作为将域名和IP地址相互映射的一个分布式数据库，能够使人更方便地访问互联网。**DNS**使用**TCP**和**UDP端口53**
**DNS**会根据一个域名返回一个**IP**
在本地设置hosts可以绕过**DNS**。使用命令`sudo vi /etc/hosts`设置。

![](https://user-gold-cdn.xitu.io/2018/5/23/1638c9f5539c888f?w=1548&h=720&f=png&s=291242)
+ 每一个电脑都有很多端口，每一个端口只做一件事情。从0到2048都是指定做某事情。80端口是用来服务HTTP协议的。
+ 浏览器负责发起请求
+ 服务器在80端口接受请求
+ 服务器负责返回内容
+ 浏览器负责下载相应内容
+ HTTP的作用是指导浏览器和服务器如何进行沟通

### HTTP请求
一个HTTP请求报文由请求行、请求头部、空行和请求数据4个部分组成
请求的格式
````
1 动词 路径 协议/版本
2 Key1: value1
2 Key2: value2
2 Key3: value3
2 Content-Type: application/x-www-form-urlencoded
2 Host: www.baidu.com
2 User-Agent: curl/7.54.0
3 
4 要上传的数据
````
1. 请求最多包含四部分，最少包含三部分。（也就是说第四部分可以为空）
2. 第三部分永远都是一个回车（\n）
3. 动词有 GET POST PUT PATCH DELETE HEAD OPTIONS 等
4. 这里的路径包括「查询参数」，但不包括「锚点」
5. 如果你没有写路径，那么路径默认为 /
6. 第 2 部分中的 Content-Type 标注了第 4 部分的格式

#### 用Chrome查看请求
1. 在谷歌浏览器空白处单击右键，点击检查，打开`Network`
2. 地址栏输入网址
3. 选中第一个请求
4. 查看`Request Headers`，点击`view source`将会看到请求的前两部分
4. 查看`FormData`或`Payload`将会看到请求的第四部分（如果有的话）

### HTTP响应
HTTP响应也由四个部分组成，分别是：状态行、消息报头、空行、响应正文。
响应的格式
````
1 协议/版本号 状态码 状态解释
2 Key1: value1
2 Key2: value2
2 Content-Length: 17931
2 Content-Type: text/html
3
4 要下载的内容
````
响应示例
状态码是服务器对浏览器说的话
+ 1xx：指示信息--表示请求已接收，继续处理。
+ 2xx：成功--表示请求已被成功接收、理解、接受。
+ 3xx：重定向--要完成请求必须进行更进一步的操作。
+ 4xx：客户端错误--请求有语法错误或请求无法实现。
+ 5xx：服务器端错误--服务器未能实现合法的请求。

#### 用Chrome查看响应
1. 打开`Network`
2. 输入网址
3. 选中第一个响应
4. 查看`Response Headers`，点击`view source`将会看到响应的前两部分
5. 查看`Response`或者`Preview`将会看到响应的第四部分。
### CURL
在Linux中curl是一个利用URL规则在命令行下工作的文件传输工具，可以说是一款很强大的http命令行工具。它支持文件的上传和下载，是综合传输工具，但按传统，习惯称url为下载工具。更多用法可以参考这篇[网站](http://man.linuxde.net/curl)