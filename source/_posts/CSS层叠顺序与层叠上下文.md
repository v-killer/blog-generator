---
title: CSS层叠顺序与层叠上下文
date: 2018-09-03 18:08:07
tags:
---
### 层叠顺序
****
层叠顺序(stacking order): 表示元素发生层叠时候有着特定的垂直显示顺序。
![](https://user-gold-cdn.xitu.io/2018/8/6/1650e7ca4e761771?w=1192&h=742&f=png&s=278520)
1. background
2. border
3. 块级元素
4. 浮动元素
5. 文字/内联元素
6. z-index: 0
7. z-index: 1
+ 后来居上：当层叠顺序相同的时候，后面的元素会覆盖前面的元素。  
+ 在层叠上下文中，`负z-index`在border和块级元素之间。
### 层叠上下文
****
层叠上下文是HTML元素的三维概念，这些HTML元素在一条假想的相对于面向（电脑屏幕的）视窗或者网页的用户的z轴上延伸，HTML元素依据其自身属性按照优先级顺序占用层叠上下文的空间。  
文档中的层叠上下文由满足以下任意一个条件的元素形成：
+ 根元素(HTML)
+ z-index值不为auto的绝对/相对定位
+ `opacity`属性小于1的元素。(透明度小于1)
+ `position: fixed;`  
更多条件请参考[MDN层叠上下文](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Understanding_z_index/The_stacking_context)