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

效果图：

![结果](https://github.com/fakechoco/CSSlearning/blob/main/Day7/day7.png)


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



