---
title: JS对象
date: 2018-09-01 14:05:43
tags:
---
### 全局对象window
#### window的属性
### 1. ECMAScript规定的属性
+ parseInt
+ parseFloat
+ Number()  
我们有两种方法可以声明一个Number  
`var n1 = 1; // 声明一个数字1`  
`var n2 = new Number(1); // 声明一个Number对象,对象的数字值是1`  
区别在于对象1有很多方法可以调用，如`toSring`、`valueof`等，数字1则没有。  
但是在实际应用中我们发现即使声明一个数字1，我们同样可以使用`toString`方法，  
这是因为当使用数字1的`toString`方法时，JS会声明一个临时的对象`temp = new Number(n1)`,将`temp.toString`的值作为`n1.toString`的值，然后把`temp`干掉。

![](https://user-gold-cdn.xitu.io/2018/7/22/164bec805719e140?w=263&h=165&f=png&s=4027)
+ String()  
同样我们有两种方法可以声明一个String  
`var s1 ='abc' // 声明一个基本类型的字符串`  
`var s2 = new String('abc') // 声明一个String对象,这个对象看起来像数组但不是数组,它只是一个hash`

![](https://user-gold-cdn.xitu.io/2018/7/22/164bed06c64c8cbe?w=388&h=190&f=png&s=8829)
**String的一些方法**
1. `charAt`方法从一个字符串中返回指定的字符  
语法：`string.charAt(index)`

![](https://user-gold-cdn.xitu.io/2018/8/1/164f535a75de950d?w=235&h=115&f=png&s=2396)
2. `charCodeAt`方法根据索引获取某一个字符的编码  
语法:`string.charCodeAt()`

![](https://user-gold-cdn.xitu.io/2018/8/1/164f538b883bf1d9?w=230&h=140&f=png&s=2138)
3. `trim`方法会从一个字符串的两端删除空白字符。  
语法：`string.trim()`
![](https://user-gold-cdn.xitu.io/2018/8/1/164f540ab9fa171d?w=353&h=96&f=png&s=1470)
4. `concat`方法将一个或多个字符串与原字符串合并。  
语法：`string.concat(string2,string3)`

![](https://user-gold-cdn.xitu.io/2018/8/1/164f545e5b53435b?w=214&h=180&f=png&s=3172)
`replace`
+ Boolean()
同样我们有两种方法可以声明一个Boolean  
`var b1 = true`  
`var b2 = new Boolean(true)`  
注意：false对象的布尔值是true
![](https://user-gold-cdn.xitu.io/2018/8/1/164f5572b9adf049?w=249&h=131&f=png&s=3348)
+ Object()
同样我们有两种方法声明一个对象  
`var o1 = {}`  
`var o2 = new object()`  
两种方法并没有什么区别，但是o1并不严格相等o2，这是因为内存不同

![](https://user-gold-cdn.xitu.io/2018/8/1/164f55db07364eab?w=285&h=200&f=png&s=3777)
+ setTimeout(function(){},5)
### 2. 浏览器私有的属性(Chrome/Firefox)
+ alert(弹框提示)
+ prompt(用户填写)
+ confirm(确认)
+ console(开发者)
+ document(文档)
***
### 原型对象
我们创建的每个函数的都有一个prototype(原型)属性，这个属性是一个指针(内存地址)，指向一个对象(原型对象)。  
这个对象(原型对象)的用途是包含可以由特定类型的所有实例共享的属性和方法。
![](https://user-gold-cdn.xitu.io/2018/8/2/164f97a098109635?w=590&h=512&f=jpeg&s=21422)
### 原型链
每个实例对象（object ）都有一个私有属性（称之为`__proto__`）指向它的原型对象（prototype）。该原型对象也有一个自己的原型对象 ，层层向上直到一个对象的原型对象为 null。根据定义，null 没有原型，并作为这个原型链中的最后一个环节。

![](https://user-gold-cdn.xitu.io/2018/8/2/164f98b96cabcdd1?w=1674&h=990&f=png&s=531913)
