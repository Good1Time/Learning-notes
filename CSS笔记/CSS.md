# CSS是什么
CSS 指层叠样式表 (Cascading Style Sheets)

样式定义如何显示 HTML 元素

样式通常存储在样式表中

外部样式表可以极大提高工作效率

外部样式表通常存储在 CSS 文件中

多个样式定义可层叠为一个

# CSS语法

CSS规则由两个主要的部分构成：选择器，以及一条或多条声明

CSS规则 = 选择器 + 声明块

<!-- CSS声明总是以分号 ; 结束，声明总以大括号 {} 括起来 -->

```css
h1{
    color:red;
    background-color:lightblue;
    text-align: center;
}
```

选择器通常是您需要改变样式的 HTML 元素。

每条声明由一个属性和一个值组成。

属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。

## 选择器

1. ID选择器

id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。

HTML元素以id属性来设置id选择器,CSS 中 id 选择器以 "#" 来定义。

```html

 <!-- ID属性不要以数字开头，数字开头的ID在 Mozilla/Firefox 浏览器中不起作用。 -->

 <style>
#para1
{
	text-align:center;
	color:red;
} 
</style>
</head>
<body>
<p id="para1">Hello World!</p>
<p>这个段落不受该样式的影响。</p>
</body>

```


2. 元素选择器（选中元素，例如p,h1）

3. class选择器（类选择器）

class 选择器用于描述一组元素的样式，class 选择器有别于id选择器，class可以在多个元素中使用。

class 选择器在HTML中以class属性表示, 在 CSS 中，类选择器以一个点"."号显示：

在以下的例子中，所有拥有 center 类的 HTML 元素均为居中。

```html
<style>
.center
{
	text-align:center;
}
</style>
</head>
<body>
<h1 class="center">标题居中</h1>
<p class="center">段落居中。</p> 
</body>

```

也可以指定特定的HTML元素使用class。

在以下实例中, 所有的 p 元素使用 class="center" 让该元素的文本居中:

```html
<style>
p.center
{
	text-align:center;
}
</style>
</head>
<body>
<h1 class="center">这个标题不受影响</h1>
<p class="center">这个段落居中对齐。</p> 
</body>

```

# 常见样式声明

1. color

元素内部的文字颜色

CSS中定义颜色使用十六进制（hex）表示法为红，绿，蓝的颜色值结合。可以是最低值是0（十六进制00）到最高值是255（十六进制FF）3个双位数字的十六进制值写法，以＃符号开始。

**预设值**：定义好的单词

**三原色，色值**：光学三原色（红、绿、蓝），每个颜色可以使用0-255之间的数字来表达，色值。

rgb表示法： rgb(0, 255, 0)
hex（16进制）表示法： #红绿蓝

```html

/* 关键词 */
color: currentcolor;

/* <named-color>值 */
color: red;
color: orange;
color: tan;
color: rebeccapurple;

/* <hex-color>值 */  (16进制)
color: #090;
color: #009900;
color: #090a;
color: #009900aa;

/* <rgb()>值 */
color: rgb(34, 12, 64, 0.6);
color: rgba(34, 12, 64, 0.6);
color: rgb(34 12 64 / 0.6);
color: rgba(34 12 64 / 0.3);
color: rgb(34.0 12 64 / 60%);
color: rgba(34.6 12 64 / 30%);

/* <hsl()>值 */
color: hsl(30, 100%, 50%, 0.6);
color: hsla(30, 100%, 50%, 0.6);
color: hsl(30 100% 50% / 0.6);
color: hsla(30 100% 50% / 0.6);
color: hsl(30.0 100% 50% / 60%);
color: hsla(30.2 100% 50% / 60%);

/* 全局值 */
color: inherit;
color: initial;
color: unset;

淘宝红：#ff4400, #f40
黑色：#000000，#000
白色：#ffffff, #fff
红：#ff0000, #f00
绿：#00ff00, #0f0
蓝：#0000ff, #00f
紫：#f0f
青：#0ff
黄：#ff0
灰色：#ccc

```

2. background-color

设置一个元素的背景颜色。

元素的背景是元素的总大小，包括填充和边界（但不包括边距）。

3. font-size

指定字体的大小。因为该属性的值会被用于计算 em 和 ex 长度单位，定义该值可能改变其他元素的大小。

元素内部文字的尺寸大小

1）px：像素，绝对单位，简单的理解为文字的高度占多少个像素
2）em：相对单位，相对于父元素的字体大小
每个元素必须有字体大小，如果没有声明，则直接使用父元素的字体大小，如果没有父元素（html），则使用基准字号。

> user agent，UA，用户代理（浏览器）

4. font-weight

指定了字体的粗细程度。一些字体只提供 normal（正常） 和 bold（加粗） 两种值。

文字粗细程度，可以取值数字，可以取值为预设值

normal

正常粗细。与400等值。

bold

 加粗。与700等值。

lighter

比从父元素继承来的值更细 (处在字体可行的粗细值范围内)。

bolder

比从父元素继承来的值更粗 (处在字体可行的粗细值范围内)。

<number>

一个介于 1 和 1000 (包含) 之间的 <number> 类型值。更大的数值代表字体重量粗于更小的数值 (或一样粗)。

> strong，默认加粗。

5. font-family

文字类型

font - family属性指定一个元素的字体。

font-family 可以把多个字体名称作为一个"回退"系统来保存。如果浏览器不支持第一个字体，则会尝试下一个。

有两种类型的字体系列名称：

family-name - 指定的系列名称：具体字体的名称，比如："times"、"courier"、"arial"。

generic-family - 通常字体系列名称：比如："serif"、"sans-serif"、"cursive"、"fantasy"、"monospace"。

使用某种特定的字体系列（Geneva）完全取决于用户机器上该字体系列是否可用；这个属性没有指示任何字体下载。因此，强烈推荐使用一个通用字体系列名作为后路。

注意： 每个值用逗号分开。

注意: 如果字体名称包含空格，它必须加上引号。在HTML中使用"style"属性时，必须使用单引号。

注意：必须用户计算机中存在的字体才会有效。

6. font-style

允许你选择 font-family 字体下的 italic 或 oblique 样式。

字体样式，通常用它设置斜体

> i元素，em元素，默认样式，是倾斜字体; 实际使用中，通常用它表示一个图标（icon）

Italic 样式一般是指书写体，相比无样式的字体，通常会占用较少的高度，而 oblique 字形一般只是常规字形的倾斜版本。斜体（italic）和倾斜体（oblique）都是通过人工倾斜常规字体的字形来模拟的。

7. text-decoration

文本修饰，给文本加线。 规定添加到文本的修饰，下划线、上划线、删除线等。

none			默认。定义标准的文本。

underline		定义文本下的一条线。

overline		定义文本上的一条线。

line-through	定义穿过文本下的一条线。

blink			定义闪烁的文本。

> a元素
> del元素：错误的内容
> s元素：过期的内容

8. text-indent

规定文本块中首行文本的缩进。

注意： 负值是允许的。如果值是负数，将第一行左缩进。

9. text-align

定义行内内容（例如文字）如何相对它的块父元素对齐。

text-align 并不控制块元素自己的对齐，只控制它的行内内容的对齐。

left	把文本排列到左边。默认值：由浏览器决定。

right	把文本排列到右边。

center	把文本排列到中间。

justify	实现两端对齐文本效果。

10.  line-height

每行文本的高度，该值越大，每行文本的距离越大。

设置行高为容器的高度，可以让单行文本垂直居中

行高可以设置为纯数字，表示相对于当前元素的字体大小

11.  width

宽度

12.  height

高度
