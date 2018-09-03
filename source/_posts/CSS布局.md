---
title: CSS布局
date: 2018-08-29 14:53:16
tags:
---
### 左右布局
使用浮动即可实现左右布局

左侧定宽右侧自适应

html代码
    
    <body>
        <div class="left">left</div>
        <div class="right">right</div>
    </body>
    
css代码
    
    .left{
        background: red;
        height: 500px;
        width: 300px;
        float: left;
    }
    .right{
        background: green;
        height: 500px;
        margin-left: 300px;
    }
    


![](https://user-gold-cdn.xitu.io/2018/6/10/163e5536e5655d2c?w=893&h=507&f=png&s=4593)

#### 左中右布局
使用浮动即可实现左中右布局

左侧定宽，右侧定宽，中间自适应

html代码
    
    <body>
        <div class="left">left</div>
        <div class="right">right</div>
        <div class="middle">middle</div>
    </body>
    
css代码
    
    .left{
        background: red;
        height: 500px;
        width: 300px;
        float: left;
    }
    .right{
        background: green;
        height: 500px;
        float: right;
        width: 300px;
    }
    .middle{
        background: yellow;
        margin: 0 300px;
        height: 500px;
    }
    


![](https://user-gold-cdn.xitu.io/2018/6/10/163e56192b15bd26?w=985&h=510&f=png&s=8827)  
