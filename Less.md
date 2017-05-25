### LESS

**1.1   什么是LESS?**

Less 是一门 CSS 预处理语言，使用了类似CSS的语法，为CSS赋予了动态语言的特征。它扩展了 CSS 语言，增加了变量、Mixin\(混合\)、嵌套、函数和运算等特性，使 CSS 更易维护和扩展。此外，Less 可以运行在 Node 或浏览器端。

一句话：用类似JS的语法去写CSS。

**1.2   LESS的特点？**

作为CSS的一种扩展，LESS CSS不仅向下兼容CSS的语法，而且连新增的特性也是使用CSS语法。这样的设置使得学习LESS非常轻松，而且你可以在任何时候回退到CSS。

**1.3   变量**

单独定义一系列通用的样式，然后在需要的时候去调用。所以在做全局样式调整的时候我们可能只需要修改几行代码就可以了。

```js
// JS中定义变量
var name = '张三';

// LESS中定义变量
@color:red;
h1{
   color: @color;
}
```

**1.4   嵌套**

在一个选择器中嵌套另一个选择器来实现继承，这样很大程度上减少了代码量，并且代码看起来更加清晰。

```

 div{
   h1{
     color:red;
   }
 }
```

> 注意：嵌套一般情况下，不要超过3层

**1.5   运算**

运算提供了加、减、乘、除操作，其他复杂的运算交给函数；通常我们可以做属性值和颜色的运算，这样就可以实现属性值之间的复杂关系。

> 注意：运算符与值之间必须以空格分开。

```

@w:500px;
div{
   h1{
     width: @w - 100;
   }
}

h1{
  width: @w;
  border: 1px solid #000;
}
```

**1.6  混合\(Mixins\)**

混合可以将一个定义好的class A轻松的引入到class B中，从而简单的实现class B 继承class A的所有属性。我们还可以带参数的调用，就像使用函数一样。

![](http://upload-images.jianshu.io/upload_images/1268909-47c87ce9ada2c14e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 注意：混合的使用就和js的自定义函数类似，首先 混合 必须前面是以 . +混合名称开始
> 
> 结构：.名称\(变量\){}
> 
> 可以有默认值，也可以没有默认值，没有的话，在调用的时候必须传参，有默认值的时候就可以不用传递参数；
> 
> 多个参数之间和js一样，用逗号（,） 隔开

**1.7  函数**

LESS中的函数 - 映射了JavaScript函数代码，如果你愿意的话，可以操纵属性值。

比如：鼠标移上亮度增加20%。

![](http://upload-images.jianshu.io/upload_images/1268909-0c53243634ccae88.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

需要查找的时候，直接查文档就可以了。

比如：

```

saturate(@color, 10%); // 饱和度增加 10%
desaturate(@color, 10%); // 饱和度降低 10%
lighten(@color, 10%); // 亮度增加 10%
darken(@color, 10%); // 亮度降低 10%
fadein(@color, 10%); // 透明度增加 10%
fadeout(@color, 10%); // 透明度降低 10%
fade(@color, 50%); // 设定透明度为 50%
spin(@color, 10); // 色相值增加 10
……
```

**1.8   匹配模式**

类似js中的if else判断，只有匹配成功才能起作用。

![](http://upload-images.jianshu.io/upload_images/1268909-1390d5d8494d8d94.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 注意：匹配模式中,定义的模式名称都是一样的，只是参数不一样，调用的时候只需选择对应的参数就可以了。

**1.9    如何使用LESS?**

**方式一：客户端直接调用**

```

<link rel="stylesheet/less" href="less/less.less">
<!--用于编译LESS的-->
<script type="text/javascript" src="js/less.min.js"></script>
```

> 注意：必须在服务器环境中才能生效，动态编译注入虚拟DOM或者内存中，类似ajax。
> 
> 开发中常用的服务器组合：WAPM

**方式二：预编译（提前编译）**

在代码编辑器中，按照LESS的语法规则写好LESS文件；

使用编译工具把.less文件编译成.css文件；

把编译后的css文件引入到页面即可。

> 编译工具：Koala

![](http://upload-images.jianshu.io/upload_images/1268909-791d357dc781af8f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**1.10  如何在一个LESS文件中导入另一个LESS文件？**

```

 @import "less.less"; // 注意：less文件扩展名可选
```

**1.11   其他补充?**

\/\/    不会被编译器编译的注释

\/\*\*\/  是可以被编译器编译的 注释

~’ ’  表示的是禁止被编译

&     表示选择所有的父级元素

**1.12 命名不要加空格** 

**1.13  《授之于渔》**

LESS官网：[http:\/\/lesscss.org\/](http://lesscss.org/)

LESS中文网 ：[http:\/\/www.lesscss.cn\/](http://www.lesscss.cn/)  和  [http:\/\/www.lesscss.net\/](http://www.lesscss.cn/)


