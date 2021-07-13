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

![结果](Day7\day7.png)

