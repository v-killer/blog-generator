---
title: JS数据类型
date: 2018-08-31 13:41:56
tags:
---
#### JS历史

![](https://user-gold-cdn.xitu.io/2018/7/13/1649401a87b13c0b?w=1554&h=259&f=png&s=42047)
#### 数据类型
七种数据类型(请背诵): 
+ `number`(数值) 
+ `string`(字符串) 
+ `boolean`(布尔值) 
+ `Symbol`(符号) 
+ `object`(对象) 
+ `undefined` 
+ `null`  
+ 注意：没有`arry`类型也没有`function`类型。
1. `number`
+ 整数和小数：`1` `0.1` `.1`
+ 科学计数法: `1.23e2`
+ 二进制: `0b11`
+ 八进制: `011`(后来ES5添加了`0o11`语法)
+ 十六进制: `0x11`
2. `string`
+ 空字符串: `''` `""` length为0
+ 空格字符串: `' '` `" "` length为1
+ 多行字符串
    
        var a = '12345' + 
                '67890'  //无回车符号
        var a = `12345
        67890`           //含回车符号
        var a = '12345 \
        67890'           //不推荐使用，若反斜杠后有空格则报错。

3. `boolean`
+ 乔治·布尔  
乔治·布尔是英格兰数学家和哲学家、数理逻辑学先驱。  
由于其在符号逻辑运算中的特殊贡献，很多计算机语言中将逻辑运算称为布尔运算，将其结果称为布尔值。
+ `boolean`的取值  
只有两个值：`true` `false`  
`a&&b`即在a和b都为true时，取值为true,否则均取值为false（与门）  
`a||b`即在a和b都为false时，取值为false,否则均为true（或门）
4. `Symbol`  
Symbol生成一个全局唯一的值
5. `undefined`和`null`  
+ 都表示没有值。一般来说`null`表示空对象，`undefined`表示空字符串/数值/布尔值/Symbol。
+ (规范)如果一个变量没有被赋值，那么这个变量的值就是`undefined`
+ (惯例)如果你想表示一个还没有被赋值的对象，就用`null`。  
`var obj = null` 
+ (惯例)如果你想表示一个还没有被赋值的字符串/数值/布尔值/Symbol,就用`undefined`。   
`var xxx = undefined`实际上只需要`var xxx`
6. `object`
+ `object`就是上面几种基本类型(无序的)组合在一起
+ `object`的key一律是字符串，不存在其他类型的key
+ `object`里面可以有`object`  
    
        var person = {
            name: 'Lilei',
            'child':{
                name: 'Jack'
            }, // 最后这个逗号可有可无
        }

+ `object['']`是合法的
+ 如果key符合标识符条件的话`object['key']`可以写作`object.key`  ,注意`object.key`不同于`object[key]`
+ `delete object['key']`(同时删除`key`和`value`)
+ `'key' in object`检测'key'是否在object里面，返回一个布尔值(即使键值为undefined)


#### typeof运算符

|xxx的类型|string|number|boolean|symbol|undefined|null|object|function|
|------|-----|-----|-----|-----|-----|-----|-----|:--:|
|typeof xxx|'string'|'number'|'boolean'|'symbol'|'undefined'|**'object'**|'object'|**'function'**|
注意：**function**并不是一个类型