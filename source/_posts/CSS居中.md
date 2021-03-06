---
title: CSS居中
date: 2018-08-28 14:27:27
tags:
---
#### 引入css的四种方式:
1. 内联`style`属性
2. `style`标签
3. 外部文件　`css link`
4. `@import url(./a.css);`

#### 实现并排效果
`style="float: left;"`　但是这样可能会出现BUG,在浮动元素的父标签写上`class="clearfix"`

css内写上
    
    .clearfix::after{
        content: ``;
        display: block;
        clear: both;
    }
    
#### div高度
块级元素的高度由其内部**文档流**元素的高度总和决定

**文档流**：文档内元素的流动方向。内联元素从左往右流动，如果遇到阻碍(宽度不够)，则换行继续流动（如果一个英文单词很长那么它不会换行，使用`word-break: break-all`可使其换行）。块级元素每一个元素都占据一行，从上往下流动。如下图所示：

![](https://user-gold-cdn.xitu.io/2018/6/4/163c9ce059fb45d6?w=1727&h=657&f=png&s=298568)
脱离文档流：
1. 相对于当前页面定位`position: fixed;`但是会出现BUG，解决方法`width: 100%`然后出现另一个BUG，解决方法:增加一个div。
2. `position: absolute`然后在其祖先元素加`position: relative;`相对于ralative的元素定位。



#### 最大宽度
`max-width: `当页面缩小时，会自动适应页面，比直接设置宽度好用。

#### 居中
1. 内联元素
+ 在父元素写`text-algin: center;`即可可实现内联元素水平居中。
+ 将内联元素行高设置`line-height: ;`与父元素高度相同即可实现内联元素垂直居中。
2. 块级元素
+ 设置块级元素`margin: 0 auto;`即可实现块级元素水平居中。
+ 使用`position`可实现块级元素水平垂直居中。

html代码
    
    <body>
        <div class="parent">parent
        <div class="child">child</div>
        </div>
    </body>
    
css代码
    
    .parent{
        height: 200px;
        width: 200px;
        border: 1px solid red;
        position: relative;
    }
    div.child{
        height: 50px;
        width: 50px;
        background: red;
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        margin: auto;
    }
    

![](https://user-gold-cdn.xitu.io/2018/6/10/163e587ea6d3379c?w=216&h=216&f=png&s=1819)
3. flex居中
+ 在父元素上写
    
        display: flex;
        justify-content: center;
        align-items: center;
   可实现子元素水平垂直居中