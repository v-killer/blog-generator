---
title: CSS盒模型详解
date: 2018-09-03 18:06:59
tags:
---
### 盒模型
****
盒模型(框模型)是网页布局的基础，每个元素都被表示为一个矩形的方框。


![](https://user-gold-cdn.xitu.io/2018/8/5/1650982825a61d9e?w=967&h=720&f=png&s=9673)
+ `width`和`height`设置内容框(content box)的宽度和高度。
>使用`min-width`、`min-height`、`max-width`、`max-height`可以设置最大(小)宽度和高度,优点是当页面放大或缩小时，内容框会自动适应页面。

+ `padding`表示css框的内边距。
+ `border`表示css框的边界,也就是边框。`border-width`、`border-color`分别设置边框的厚度和颜色。
+ `margin`表示css框的外边距。
### 外边距合并(折叠)  
块级元素的上外边距和下外边距有时会合并(折叠)为一个外边距，其大小取其中最大者。
+ 相邻元素之间：毗邻的两个元素之间的外边距会合并。  
+ 父元素与其第一个或最后一个子元素之间:如果父元素与其第一个(最后一个)子元素之间不存在边框，内边距，行内内容，那么这两对外边距之间会产生合并，此时子元素的外边距会"溢出"到父元素的外面。  
+ 空的块级元素：如果一个块级元素内不包含任何内容，则该元素的上下外边距会合并。
>使用`overflow: hidden;`可以避免外边距合并，但是不建议这样做。建议加padding。
### box-sizing
`box-sizing`属性用于更改用于计算元素宽度和高度的默认的CSS盒子模型。
+ `content-box`:默认值，标准盒模型。width和height只包括内容的宽高。  
width/height = 内容的宽度/高度
+ `border-box`:IE盒模型。width和height包括内容、内边距和边框。(如果想要使一个框占窗口的50%可以使用`border-box`)  
width/height = border + padding + 内容的宽度/高度

![](https://user-gold-cdn.xitu.io/2018/8/5/165099c69a923a3c?w=967&h=719&f=png&s=9653)
### display
****
`display`属性指定用于元素的呈现框的类型
+ `block`(块框):定义为堆放在其他框上的框（例如：其内容会独占一行），可以设置它的宽高。
+ `inline`(行内框):与块框是相反的，它随着文档的文字（例如：它将会和周围的文字和其他行内元素出现在同一行，而且它的内容会像一段中的文字一样随着文字部分的流动而打乱），对行内盒设置宽高无效。
+ `inline-block`(行内块状框):像是上述两种的集合：它不会重新另起一行但会像行内框一样随着周围文字而流动，它能够设置宽高，并且像块框一样保持了其块特性的完整性，它不会在段落行中断开。（在下面的示例中，行内块状框会放在第二行文本上，因为第一行没有足够的空间，并且不会突破两行。然而，如果没有足够的空间，行内框会在多条线上断裂，而它会失去一个框的形状。）

### 溢出
****
**overflow**:当你使用绝对的值设置了一个框的大小（如，固定像素的宽/高），允许的大小可能不适合放置内容，这种情况下内容会从盒子溢流。我们使用`overflow`属性来控制这种情况的发生。
+ `auto`：当内容过多，溢流的内容被隐藏，然后出现滚动条来让我们滚动查看所有的内容。
+ `hidden`:当内容过多，溢流的内容被隐藏。
+ `visible`:默认值，当内容过多，溢流的内容被显示在盒子的外边。

![](https://user-gold-cdn.xitu.io/2018/8/5/16509a51ed00a7e8?w=675&h=402&f=png&s=26076)
### 文字溢出省略

+ 单行文字  
`white-space: nowrap`:文本内的换行符无效(使文字显示在一行)  
    
        text-overflow: ellipsis:   //多出的文本变为省略号
        overflow: hidden;
+ 多行文字

        div{
            display: -webkit-box;
            -webkit-line-clamp: 2;//第几行省略
            -webkit-box-orient: vertical;
        }


### 文字两端对齐

如果想要使[姓名]和[联系方式]两端对齐，呈现这样的效果:

![](https://user-gold-cdn.xitu.io/2018/8/5/16509d73c05fc08d?w=336&h=99&f=png&s=1583)
代码如下：    
    
    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="utf-8">
      <title>JS Bin</title>
      <style>
        span{
          display: inline-block;
          width: 4em;
          text-align: justify;
        }
        span::after{
          content: '';
          display: inline-block;
          width: 100%;
        }
      </style>
    </head>
    <body>
      <div>
        <span>姓名</span><br/>
        <span>联系方式</span>
      </div>
    </body>
    </html>
    

### 文档流
****
文档流：文档内元素流动的方向。
+ 内联元素从左向右流动，如果遇到阻碍(宽度不够)，则换行继续流动。
+ 如果一个英文单词很长，那么它不会换行，使用`word-break: break-all`可使其换行。(或者使用连字符`-`)
+ 块级元素每一个元素都占据一行，从上向下流动。如下图所示：
![](https://user-gold-cdn.xitu.io/2018/8/5/1650a2e91a341891?w=1727&h=657&f=png&s=252910)