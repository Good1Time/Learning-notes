# Markdown 学习笔记

- [Markdown 学习笔记](#markdown-学习笔记)
  - [1.代码块](#1代码块)
    - [1.1 行内代码与代码块](#11-行内代码与代码块)
  - [2. 标题](#2-标题)
  - [3.字体](#3字体)
  - [4.引用](#4引用)
      - [具有其他元素的块引用](#具有其他元素的块引用)
  - [5.分割线](#5分割线)
  - [6.插入图片](#6插入图片)
  - [7.链接](#7链接)
    - [1.超链接](#1超链接)
    - [2.自动网址链接及禁用网址链接](#2自动网址链接及禁用网址链接)
    - [3.邮箱](#3邮箱)
    - [4.格式化链接](#4格式化链接)
  - [8.列表](#8列表)
    - [在列表中添加元素](#在列表中添加元素)
  - [9.表格](#9表格)
  - [10、脚注](#10脚注)
  - [11.任务清单](#11任务清单)
  - [11.定义清单](#11定义清单)
  - [段落](#段落)
  - [转移符号](#转移符号)
  - [表情符号](#表情符号)
  - [其他](#其他)

## 1.代码块

```

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
</html>

```

### 1.1 行内代码与代码块

行内代码语法: `包裹代码; 代码块语法: 以 Tab或4个空格开头; 但是由于原生代码块语法不够直观, 扩展语法几乎都提供了围栏代码块语法如下:

`` `python
// `中间去掉空格
def print_name():
    print("Markdown")
`` `

## 2. 标题

```

#一级标题
##二级标题
###三级标题
#### 四级标题
#####五级标题
###### 六级标题

```

## 3.字体

```

*这是斜体效果*
**这是加粗效果**
***这是斜体加粗效果***
~~这是删除效果~~
==这是高亮效果==
<u>这是下划线效果</u>

```

*这是斜体效果*
**这是加粗效果**
***这是斜体加粗效果***
~~这是删除效果~~
==这是高亮效果==
<u>这是下划线效果</u>

## 4.引用

```

>一级引用
>>二级引用

```

> 一级引用
> 
> > 二级引用
> > 
> > > 三级引用

#### 具有其他元素的块引用


> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.


## 5.分割线

```

---
***

```

---

***

## 6.插入图片

```

![名称](地址 (建议相对地址)+ "title")

```

![Baidu](https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png "百度一下,你就知道")

***
```

<img src="https://github.githubassets.com/images/modules/site/home/astro-mona.svg" alt="GitHub">

```

<img src="https://github.githubassets.com/images/modules/site/home/astro-mona.svg" width = "200" height = "200" div align=center />



## 7.链接

### 1.超链接

```

[名称](地址+ "title")

```

[斗鱼](https://www.douyu.com/ "斗鱼-每个人的直播平台")

### 2.自动网址链接及禁用网址链接

许多Markdown处理器会自动将URL转换为链接。这意味着如果您输入https://developer.mozilla.org/zh-CN/，即使您没有使用方括号，您的Markdown处理器也会自动将其转换为链接。

```

https://developer.mozilla.org/zh-CN/

```

呈现的输出如下所示：

https://developer.mozilla.org/zh-CN/

禁用自动URL链接

如果您不希望自动链接URL，则可以通过将URL表示为带有刻度线的代码来删除该链接。

```

`http://www.example.com`

```

呈现的输出如下所示：

`http://www.example.com`

### 3.邮箱

```
<fake@example.com>
```
<fake@example.com>

### 4.格式化链接

为了强调链接，请在方括号和括号之前和之后添加星号。

```

我喜欢代码 **[MDN](https://developer.mozilla.org/zh-CN/)**.
这是Markdown指南 *[Markdown Guide](https://markdown.p2hp.com)*.

```

我喜欢代码 **[MDN](https://developer.mozilla.org/zh-CN/)**.
这是Markdown指南 *[《Markdown Guide》](https://markdown.p2hp.com)*.

## 8.列表

```

//无序列表

- 标题1
- 标题2
- - 标题2.1
- - 标题2.2

//有序列表

1. 目录1

2. 目录2

3. 目录3

   - 目录3.1

   - 目录3.1

```

- 标题1
- 标题2
  - 标题2.1
  - 标题2.2
- 
1. 目录1
2. 目录2
3. 目录3
   - 目录3.1
   - 目录3.1

### 在列表中添加元素

要在保留列表连续性的同时在列表中添加另一个元素，请将该元素缩进四个空格或一个制表符 

```

*   This is the first list item.
*   Here's the second list item.

    I need to add another paragraph below the second list item.

*   And here's the third list item.

```

*   This is the first list item.
*   Here's the second list item.

    I need to add another paragraph below the second list item.

*   And here's the third list item.



## 9.表格

使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行。

对齐方式

我们可以设置表格的对齐方式：

1. `-:` 设置内容和标题栏居右对齐

2. `:-` 设置内容和标题栏居左对齐

3. :`-:` 设置内容和标题栏居中对齐

```

|左对齐|居中|右对齐|

<!-- 对齐方式 -->

|:--|:--:|--:|
|XXXXX|XXXXX|XXXXX|

```

| 左对齐  |  居中   |  右对齐 |

| :------ | :-----: | ------: |

| XXXXXXX | XXXXXXX | XXXXXXX |


## 10、脚注

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1 ]: This is the first footnote.

[^bignote ]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.
    
    `{ my code }`
    
    Add as many paragraphs as you like.

 ## 11.任务清单

```

要创建任务列表，请在任务列表项之前添加破折号 "-" 和方括号，并[ ]在其前面加上一个空格。要选择一个复选框，请在方括号 [ ] 内部添加"X" 。

```
- [ ] Write the press release
- [x] Update the website
- [ ] Contact the media

## 11.定义清单

要创建定义列表，请在第一行上键入术语。下一行，键入一个冒号后跟一个空格和定义。

```

第一学期
: 这是第一个术语的定义。

第二期
: 这是第二项的定义。
: 这是第二项的另一个定义。

```

第一学期
: 这是第一个术语的定义。

第二期
: 这是第二项的定义。
: 这是第二项的另一个定义。

## 段落

`Markdown` 段落没有特殊的格式，直接编写文字就好，段落的换行是使用两个以上空格加上回车。

![换行](https://www.runoob.com/wp-content/uploads/2019/03/36A89BDA-A062-4D66-A41B-0EBEE7891AB9.jpg)

## 转移符号

要显示原义字符，否则将用于设置Markdown文档中的文本格式\，请在字符前面添加反斜杠。

```

\*如果没有反斜杠，这将是无序列表中的项目符号。

```

* 如果没有反斜杠，这将是无序列表中的项目符号。

## 表情符号

表情符号语法: :表情代码:, 只有一个 :, 支持 `emoji` 表情

## 其他

1. 更改字体、大小、颜色
2. 为文字添加背景色
3. 设置文字居中
4. 加入上下标

![](https://pics3.baidu.com/feed/cdbf6c81800a19d8439b73ef09643382a41e46ec.jpeg?token=d5a58e193fd6bccc26b57e4c9678ec02)

