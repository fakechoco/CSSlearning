### Day 7 July13
#### CSS基础

##### 在外联CSS文件中设置格式：

```css
p.r{color: red; margin-left: 20px;}
/* r类型的段落会被设置成此格式*/
h4 {color:purple; text-align: center;}
/* 未注明类型/ID的四号标题会被设置成此格式 */
#g{color: green; text-align: right;}
/* id=g的元素会被设置成此格式*/
```

##### 在HTML中的实例

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta name="author" content="CHOKE">
        <title>css查找</title>
        <link rel="stylesheet" type="text/css" href="colorset.css">
<!--导入CSS文件设置-->
    </head>
    <body>
        <p class="r">装饰红色，距离左边一定距离段落</p>
        <p>未装饰的段落</p>
        <h4>装饰紫色，居中标题</h4>
        <h4 id="g">找ID找到的标题</h4>
        <p id="g">ID找到的段落</p>
    </body>
</html>
```
---

#### Day8 July14

##### CSS背景

设置页面背景：

``` css
body{background-color:red;color:green}
```

此处将body的背景设置成红色，字体设置成绿色（优先级小于body内其他元素预设）

设置页面背景为图片：

``` css
body{background-image:url(图片地址);}
```

图片默认会水平，垂直同时屏幕，要控制平铺方向：

``` css
body{background-image:url(图片地址);background-repeat:repeat-x;}
```

repeat-x指的是：只在水平方向屏幕

repeat-y：垂直方向也平铺

no-repeat:不平铺

定位图片：

``` css
background-position:right top;
```

此处将图片固定在右上角

让图片随着页面下滑而移动，无论怎么滑动页面内容。始终处于视角的某个固定位置：

``` css
background-attachment:fixed;
```



背景的属性可以简写：

``` css
body {background:#ffffff url('img_tree.png') no-repeat right top;}
```

此处没有说明具体属性，直接设置了背景颜色，图片，平铺方式，位置（没有设定固定图片）

当使用简写属性时，属性值的顺序为：

1. background-color
2. background-image
3. background-repeat
4. background-attachment
5. background-position

##### CSS文本设置

* 颜色:color
* 文本对齐：text-align
* 文本装饰：text-decoration(可设置删除线，下划线，上划线)
* 文本大小写设置：text-transform
* 文本缩进：text-indent
* 字符之间的距离：letter-spacing
* 单词之间距离：word-spacing
* 行距：line-height
* 文字阴影：text-shadow（可设置垂直，水平方向阴影大小以及阴影颜色）
* 禁用文字环绕：white-space:wrap
* 文本方向：direction（rtl:右边开始 ltl:左边开始）

##### CSS字体设置

设置字体系列

``` css
p{font-family:"Times New Roman", Times, serif;}
```

上述代码中"Times New Roman", Times：两种字体类型，后者为备用字体，当浏览器不支持时会使用（若字体类型名称超过一个词，必须要加引号）

在CSS中，有两种类型的字体系列名称：

- **通用字体系列** - 拥有相似外观的字体系统组合（如 "Serif" 或 "Monospace"）
- **特定字体系列** - 一个特定的字体系列（如 "Times" 或 "Courier"）

serif：Serif字体中字符在行的末端拥有额外的装饰

Sans-serif    "Sans"是指无 - 这些字体在末端没有额外的装饰

Monospace：所有的等宽字符具有相同的宽度



字体样式：

``` css
p.normal {font-style:normal;}
p.italic {font-style:italic;}
p.oblique {font-style:oblique;}
```

此处设置字体为正常/斜体/向一边倾斜



字体大小：

``` css
body {font-size:100%;}
font-size: 20px;
font-size: 1.25em;
/* 1em=16px */
```

body元素默认字体设置大小单位为“%”



设置字体加粗:

``` css
font-weight:
```

后面可以直接添加加粗大小（数字值）

也可以用预设值：normal(不加粗) ，lighter(变细),bold(加粗)



设置字体转变

``` CSS
font-variant:small-caps;
```

将小写字母也显示为大写，但是原本大写的字母尺寸更大



字体设置也可以像背景一样，使用简写

---

#### Day9 July.15

 ##### CSS装饰链接

链接的四种状态：

* 访问前(link)
* 访问过(visited)
* 鼠标指定时(hover)
* 点击时(active)

例如:

``` css
a:link {color:#000000;}      /* 未访问链接*/
a:visited {color:#00FF00;}  /* 已访问链接 */
a:hover {color:#FF00FF;}  /* 鼠标移动到链接上 */
a:active {color:#0000FF;}  /* 鼠标点击时 */
```

在设置多个状态的样式时候：

hover必须在link,visited后方

active必须在hover后方



设置下划线，颜色，字体加粗和背景颜色：与普通文本一致

用text-decoration等元素装饰



创建链接框：

``` css
a:link,a:visited
{
	display:block;
	font-weight:bold;
	color:#FFFFFF;
	background-color:#98bf21;
	width:120px;
	text-align:center;
	padding:4px;
	text-decoration:none;
}
a:hover,a:active
{
	background-color:#7A991A;
}
```

display:后方的元素决定了链接框的形状

然后用width设置大小 padding设置边框到文本间的距离



##### CSS装饰列表

设置有序列表的排序基准：

``` css
ol{list-style-type:upper-alpha}
/* 设置基准位小写字母*/
```

设置无序列表前缀的样式：

``` css
ul{list-style-type: square;}
/* 设置为正方形 */
```

设置无序列表前缀为指定图像：

``` css
ul
{
    list-style-image:url()
}
/* 此处图片作为标记的设置，在不同浏览器中不一定显示效果一致 */
/* 解决浏览器兼容问题*/
ul.s
{
    list-style-type:none;
    margin: 0px;
    padding: 0px;
}
/* 设置无序列表为无标记(去掉默认的前缀“.”，设置填充，边距)
ul.s  li
{
    background-image: url();
    background-repeat: no-repeat;
    background-position: 0px 5px;
    padding-left: 20px;
}
/* 设置图像，不重复平铺，图像位置（左0px,上下5px) padding-left 属性把文本置于列表中 */

```

---

#### Day10 July.17

##### CSS表格

​	给表格设置边框，并且合并表格与单元格的边框：

``` css
table
{
    border-collapse: collapse;
  
}
/* 让表格的边框和表内单元格边框合并 */
table,td,th
{
    border: 1px solid black;
}
```

表格的垂直对齐：

``` css
td
{
	height:50px;
	vertical-align:baseline;
}
/* vertical-align:设置垂直位置  此处设置到基准线上*/
```

字体对齐方式在前面提过（text-align)

单元格大小也用height,width设置

控制边框间距：

间距(padding)指的是边框到内容的距离 边距(spacing)指的是边框与边框之间的距离

``` css
td,th{padding:2px;}/*设置间距*/
```

##### CSS盒子模型：

所有HTML元素可以看作盒子，CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容

从外到内的结构分别为：

- **Margin(外边距)** - 清除边框外的区域，外边距是透明的。
- **Border(边框)** - 围绕在内边距和内容外的边框。
- **Padding(内边距)** - 清除内容周围的区域，内边距是透明的。
- **Content(内容)** - 盒子的内容，显示文本和图像。

最终元素的总宽度计算公式：

总元素宽度=宽度+左外边距+右外边距+左边框+右边框+左内边距+右内边距

元素的总高度最终计算公式：

总元素高度=高度+顶部外边距+底部外边距+上边框+下边框+上内边距+下内边距

#####  CSS边框

定义边框样式：<kbd>border-style</kbd>

| none（默认） | 定义无边框。                                                 |
| ------------ | ------------------------------------------------------------ |
| hidden       | 与 "none" 相同。不过应用于表时除外，对于表，hidden 用于解决边框冲突。 |
| dotted       | 定义点状边框。在大多数浏览器中呈现为实线。                   |
| dashed       | 定义虚线。在大多数浏览器中呈现为实线。                       |
| solid        | 定义实线。                                                   |
| double       | 定义双线。双线的宽度等于 border-width 的值。                 |
| groove       | 定义 3D 凹槽边框。其效果取决于 border-color 的值。           |
| ridge        | 定义 3D 垄状边框。其效果取决于 border-color 的值。           |
| inset        | 定义 3D 嵌入边框。其效果取决于 border-color 的值。           |
| outset       | 定义 3D 突出 边框。其效果取决于 border-color 的值。          |

边框的四条边也可以单独设置格式：

``` css
p{ border-top-style:dotted;border-right-style:solid;border-bottom-style:dotted; border-left-style:solid;}
```

 也可以简写：（border-style后可以有1-4个样式）

``` css
border-style:dotted solid double dashed; /*对应上，右，下，左边框（从上开始，顺时针）*/
border-style:dotted solid double;/*上边框为dotted 左右为solid 下为double*/
border-style:dotted solid;/*上下为dotted 左右为solid*/
border-style：double /*上下左右都是double*/
```

边框颜色：<kbd>border-color</kbd>

``` css
p{border-style: none;border-color: red;}/*单独设置颜色无效，必须连同边框样式一起设置*/
```

边框的所有属性可以一起简写：

``` css
border:5px solid red;
```

对应的三个值为：

- border-width
- border-style 
- border-color

单独设置某一个边框的颜色

``` css
p 
{border-style:solid;border-top-color:#ff0000;}
/*设置上边框为红色，其他边框保持默认不变*/
```

---

#### Day11 July.19

##### CSS轮廓

轮廓（outline）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。

轮廓不会改变元素宽度/长度

轮廓有三个属性：样式(style),颜色(color),宽度(width)

设置轮廓 ：

``` css
p.a
{
    outline: 2px dotted red;
}
```

或者单独设置：

``` css
p.a
{
	outline-color:red;
    outline-style:dotted;
    outline-width:2px;    /*  此处亦可用预设值，比如:thick  */
}
```

##### CSS外边距

外边距(margin)定义了元素周围的空间

mairgin的属性：宽度(width)

为段落设置左外边距：

``` css
p.m
{
    color: blueviolet;
    margin-left: 20px;
}
```

上/下/左/右的外边距都可以单独设置（在一处代码中）

``` css
margin:
```

margin后可有1-4个值，不同数量的值对应的设置详见上方<kbd>CSS边框</kbd>

##### CSS内边距(填充)

CSS padding(填充)定义元素边框与元素内容之间的空间，即上下左右的内边距。

内边距和外边距一样，属性值为宽度(width)

``` css
p
{
    padding-left:50px;
}
```

和外边距一样也可以单独设置上下左右（在一处代码中）：格式与外边距一致

##### CSS分组与嵌套

为了使得代码更简洁，可以分组设置元素(使用逗号）：

设置一级/二级标题以及段落的颜色为绿色

``` css
h1,h2,p
{
    color:green;
}
```

嵌套选择器：

- p{ }: 为所有"p"元素指定一个样式。
- .marked{ }: 为所有 class="marked" 的元素指定一个样式。
- .marked p{ }: 为所有 class="marked" 元素内的 "p" 元素指定一个样式。
- p.marked{ }: 为所有 class="marked" 的 "p"元素指定一个样式。

例如：给段落设置为居中，字体蓝色；所有marked类的元素背景颜色设置为红色；所有marked类的段落字体设置成白色；marked类的段落设置下划线：

``` css
p
{
    color:blue;
    text-align:center;
}
.marked
{
    background-color:red;
}
.marked p
{
    color:white;
}
p.marked{
    text-decoration:underline;
}
```

---

#### Day12 July.22

##### CSS尺寸

| 属性        | 描述                 |
| :---------- | :------------------- |
| height      | 设置元素的高度。     |
| line-height | 设置行高。           |
| max-height  | 设置元素的最大高度。 |
| max-width   | 设置元素的最大宽度。 |
| min-height  | 设置元素的最小高度。 |
| min-width   | 设置元素的最小宽度。 |
| width       | 设置元素的宽度。     |

 

##### CSS显示

CSS的显示(display)属性可以设置一个元素的显示方式

要隐藏一个元素，可以使用<kbd>display:none</kbd>或者<kbd>visibility:hidden</kbd>

被前者设置过的元素不会占用页面空间，而后者会占用

想要在表格隐藏一行时：visibility: collapse



css的元素分为：块元素和内联元素

块元素：占用全部宽度，前后都有换行 比如：

- h1 (以及其它所有号的标题)
- p
- div

内联元素：只占用需要的宽度，不强制换行 比如：

- span
- a



可以通过display属性更改元素显示类型

把内联元素显示为块元素：

``` css
span {display:block;}
```

把块元素显示为内联元素：

``` css
p {display:inline;}
```

##### CSS定位

position 属性指定了元素的定位类型。

position 属性的五个值：

- static
- relative
- fixed
- absolute
- sticky



static定位：默认值，正常定位

fixed定位：相对于浏览器为固定位置，就算滚动页面也不会动

relative定位：相对定位，相对于正常定位

absolute定位：绝对定位，相对于父元素，若没有父元素就会相对于html元素

sticky定位：粘性定位，基于用户的滚动位置来定位，当处于阈值之内时，就等同于相对定位，当处于阈值之外，就等同于fixed定位



如果一个元素被设置成了absolute定位，那么它的大小就不像块元素，而是取决于内容大小，而且可以与其他元素重叠



z-index属性指定了一个元素的堆叠顺序，一个元素可以有正数或负数的堆叠顺序

具有更高堆叠顺序的元素总是在较低的堆叠顺序元素的前面

如果两个定位元素重叠，没有指定z - index，最后定位在HTML代码中的元素将被显示在最前面

---

#### Day13 July.23

##### CSS Overflow

当元素内的内容过大，导致溢出时，用overflow属性设置

overflow属性有以下值：

| 属性名  | 涵义                                                     |
| ------- | -------------------------------------------------------- |
| visible | 默认值。内容不会被修剪，会呈现在元素框之外。             |
| hidden  | 内容会被修剪，并且其余内容是不可见的。                   |
| scroll  | 内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。 |
| auto    | 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。 |

##### CSS Float

float属性会让元素向左/由移动，并且影响周围元素的排列，通常用于图像

``` css
img{float:right;} /* 向右浮动 */
```

浮动的时候，往往会改变周边元素的排列，要避免这个情况，要使用clear属性

``` css
.c{clear:both;}/* 两边不能出现浮动元素 */
```

##### CSS对齐

要对齐一个元素(若没设置width，或将其设置为100%，对齐将无效)

``` css
.a {margin:auto;width:80%;}
```

只设置文本居中对齐：text-align:center;

图片居中对齐：将图片放到div中，并设置margin:auto;



左右对齐：

将元素右对齐：(使用绝对定位)

``` css
div{
    position: absolute;
    right: 0px;
}
```

将元素右对齐：(使用浮动)

``` css
img{
    float:right;
}
```

如果该图片太大，在div溢出了，可在div中添加 margin:auto;来解决



垂直居中：通过设置line-height 属性值和 height 属性值相等来设置 div 元素居中、

``` css
.center {
    line-height: 200px;
    height: 200px;
    border: 3px solid green;
    /* 如果还要水平居中，添加 text-align: center;  */
}
```

也可以通过头部底部添加padding

``` css
.center {
    padding: 70px 0;
    /* 如果还要水平居中，添加 text-align: center;  */
}
```



使用绝对定位和transform

``` css
.center p {
    margin: 0;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);/* 根据顶部和左边(对应x/y轴)移动 */
}
```

---

#### Day14 July.24

##### CSS组合选择符

CSS组合选择符包括各种简单选择符的组合方式。

在 CSS3 中包含了四种组合方式:

- 后代选择器(以空格分隔)
- 子元素选择器(以大于 **>** 号分隔）
- 相邻兄弟选择器（以加号 **+** 分隔）
- 普通兄弟选择器（以波浪号 **～** 分隔）

##### CSS伪类

伪类的定义，以下解释来自于[此处博客]([CSS选择器：伪类（图文详解） - 千古壹号 - 博客园 (cnblogs.com)](https://www.cnblogs.com/qianguyihao/p/8280814.html))

````
伪类：同一个标签，根据其不同的种状态，有不同的样式。这就叫做“伪类”。伪类用冒号来表示。

比如div是属于box类，这一点很明确，就是属于box类。但是a属于什么类？不明确。因为需要看用户点击前是什么状态，点击后是什么状态。所以，就叫做“伪类”。
````

超链接伪类：设置超链接不同状态的样式

``` css
a:link {color:#FF0000;} /* 未访问的链接 */
a:visited {color:#00FF00;} /* 已访问的链接 */
a:hover {color:#FF00FF;} /* 鼠标划过链接 */
a:active {color:#0000FF;} /* 已选中的链接 */
```

伪类也可以配合类来使用

first-child伪类：选择父元素的第一个子元素

设置所有a类段落的第一个加粗单词为红色

``` css
p.a>b:first-child{color:red;}
```

##### CSS伪元素

用来添加一些特殊效果

:first-line  /:first-letter    在第一行/第一个字添加特效

``` css
p.a:first-line{color:red;}
p.a:first-letter{font-size:150%;}
```

:before / :after   在元素后/前添加内容

``` css
p:before{content:url("pic-url");}
p:after{content:url("pic-url");}/* 在前后都添加图片 */
```

##### 伪类和为元素区别：

以下内容来自于[菜鸟教程笔记(此页面最下方)]([CSS 伪元素 | 菜鸟教程 (runoob.com)](https://www.runoob.com/css/css-pseudo-elements.html))

**伪类**选择元素基于的是当前元素处于的状态，或者说元素当前所具有的特性，而不是元素的id、class、属性等静态的标志。由于状态是动态变化的，所以一个元素达到一个特定状态时，它可能得到一个伪类的样式；当状态改变时，它又会失去这个样式。由此可以看出，它的功能和class有些类似，但它是基于文档之外的抽象，所以叫伪类。

与伪类针对特殊状态的元素不同的是，**伪元素**是对元素中的特定内容进行操作，它所操作的层次比伪类更深了一层，也因此它的动态性比伪类要低得多。实际上，设计伪元素的目的就是去选取诸如元素内容第一个字（母）、第一行，选取某些内容前面或后面这种普通的选择器无法完成的工作。它控制的内容实际上和元素是相同的，但是它本身只是基于元素的抽象，并不存在于文档中，所以叫伪元素。

---

#### Day15 July.26

 ##### CSS导航栏

导航栏是用列表插入链接实现的

垂直导航栏：

``` css
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
}
a
{
    display:block;
    width:60px;
}
```

链接变成了块状，所以点击文本外的区域也能触发

给链接添加样式

``` css
li a:hover{
    background-color:blue;
    color:white;
}
```

添加分割线(底部添加边框)

```css
li{
     border-bottom: 1px solid #555;
}
```



水平导航栏：

① 内联方法：将li设置成内联

```css
li{
    display:inline;
}
```

②设置浮动：设置li的浮动

``` css
li
{
    float:left;
}
a
{
    display:block;
    width:60px;
}
```

将导航条最后一个选项放到最右边：

```css
li.last{
    float:right;
}
```

分割线(右边添加边框，但是最后一个元素不添加)

``` css
li:not(.last){
    border-right: 1px solid #555;
}
```

---

#### Day16 July.28

##### CSS下拉菜单

设置一个鼠标指定时现实的下拉菜单：原理是设置元素的：hover

让菜单在元素未被指定时不显示。指定时显示

``` css
.menu{
    position: relative;
    display: inline;
}
.dropdown{
    display: none;
    position: absolute;
    max-width: 160px;
    margin: 0;
    padding:0 16px;
    background-color: chartreuse;
}
.menu:hover .dropdown{
    display: block;
}
```

若想设置给用户选择的链接，设置<a>即可

``` css
.dropdown a{
    text-decoration: none;
    color:black;
    display: block;  
}
```

对齐：

如果要被指定的元素过于靠右，下拉菜单内容可能会溢出

为了避免这种情况，可以设置成下拉菜单从右到左对齐(默认左到右)

``` css
 right: 0;
```

但设置完毕以后，靠左的元素指定时下拉菜单又会左溢出，可以添加left:0;来覆盖以上的设置

##### CSS提示工具

提示工具指的是，鼠标指向某个元素后会弹出提示文本，原理和下拉菜单类似

设置元素的：hover 让文本在元素未被指定时不显示。指定时显示

设置一个在元素右侧的提示文本(设置提示文本元素的左边距，来和被指定的元素保持距离)



``` css
.tooltip{
    position: relative;
    display: inline-block;
}
.tooltip .text1 {
    visibility: hidden;
    width: 120px;
    background-color: black;
    color: white;
    text-align: center;
    border-radius: 6px;
    padding: 5px 0;
/* 定位 */
    position: absolute;
    z-index: 1;
    left:105%;
    top:-5px; /* 设置了顶部的负间距，因为被指定的元素也有padding，与其数值一致*/
}
.tooltip:hover .text1 {
    visibility: visible;
}
```

设置一个在元素左侧的提示文本(设置提示文本元素的右边距，来和被指定的元素保持距离)

``` css
/* 定位 */
    position: absolute;
    z-index: 1;
    left:105%;
    top:-5px; /* 设置了顶部的负间距，因为被指定的元素也有padding，与其数值一致*/
}
```

设置一个在元素上方的提示文本(设置提示文本元素的下边距，来和被指定的元素保持距离)

``` css
	position: absolute;
    bottom: 100%; /* 下边距 */
    margin-left: -60px; /* 居中对齐，这里的-60是根据被指定元素宽度一半计算的 */
    left: 50%;
    z-index: 1;
```

设置一个在元素下方的提示文本(设置提示文本元素的上边距，来和被指定的元素保持距离)

```css
	position: absolute;
	top: 100%; /* 上边距 */
	margin-left: -60px; /* 居中对齐，这里的-60是根据被指定元素宽度一半计算的 */
	left: 50%;
	z-index: 1;
```

---

#### Day17 August.3

##### CSS图像拼合技术

可以利用CSS来显示图像的一部分内容

``` css
width:46px;
height:44px;
background:url(img_navsprites.gif) 0 0;
```

url(img_navsprites.gif) 0 0：url:图源，后面的数字指定的是显示的位置，表示图片左作标，上作标，再预先指定显示的长宽就可以确定显示的部分

##### CSS透明/非透明

设置图像透明度：opacity

后面值为0-1，越小越透明

---

8/31 

*返校了 周末可能继续学*

---

#### Day18 September.3

##### CSS媒体类型

用 <kbd>@media</kbd>来选择页面显示的媒体类型 比如

``` css
@media screen{
    p.a{font-size:20px;}
}
@media print{
    p.a{font-size:10px;}
}
```

将screen(电脑屏幕)类型的显示媒体的a类段落字体大小改为20像素

而print(打印)改为10像素

##### CSS选择器

不通过class/id来选择元素,而是使用元素的特殊属性

``` css
p[title='rand']{
    color:red;
    font-weight: bold;
}
// html部分：
<p title="rand">用title属性选择并渲染的段落</p>
```



**"value 是完整单词"** 类型的比较符号: **~=**, **|=**

**"拼接字符串**" 类型的比较符号: ***=**, **^=**, **$=**

**1.attribute 属性中包含 value:**　

[attribute~=value] 属性中包含独立的单词为 value，例如：

```
[title~=flower]  -->  <img src="/i/eg_tulip.jpg" title="tulip flower" />
```

[attribute*=value] 属性中做字符串拆分，只要能拆出来 value 这个词就行，例如：

```
[title*=flower]   -->  <img src="/i/eg_tulip.jpg" title="ffffflowerrrrrr" />
```

**2.attribute 属性以 value 开头:**

[attribute|=value] 属性中必须是完整且唯一的单词，或者以 **-** 分隔开：，例如：

```
[lang|=en]     -->  <p lang="en">  <p lang="en-us">
```

[attribute^=value] 属性的前几个字母是 value 就可以，例如：

```
[lang^=en]    -->  <p lang="ennn">
```

**3.attribute 属性以 value 结尾:**

```
[attribute$=value] 属性的后几个字母是 value 就可以，例如：
a[src$=".pdf"]
```



##### CSS表单

设置输入框的风格，并且在输入框被选时提供额外特效

``` css
input[type=text]{
    width: 100%;
    padding:10px 10px;
    margin:10px 0px;
    box-sizing: border-box;
    border: 1px solid red;
}
input[type=text]:focus{
    background-color: darkgoldenrod;
}//在被选中时改变背景颜色
```



设置下拉菜单

``` css
select{
    width: 100%;
    padding: 10px 20px;
    border: 1px solid black;
    background-color: aqua;
}
```

##### CSS计数器

CSS 计数器根据规则来递增变量。

CSS 计数器使用到以下几个属性：

- `counter-reset` - 创建或者重置计数器
- `counter-increment` - 递增变量
- `content` - 插入生成的内容
- `counter()` 或 `counters()` 函数 - 将计数器的值添加到元素

``` css
body{
    counter-reset: section1;
}
h1{
    counter-reset: section2;
}
h2{
    margin-left: 16px;
}
h1::before{
    counter-increment: section1;
    content: counter(section1) ".";
}
h2::before{
    counter-increment: section2;
    content: counter(section1)"."counter(section2)":";
}
```

