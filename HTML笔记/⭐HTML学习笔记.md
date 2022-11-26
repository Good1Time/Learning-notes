# HTML（超文本标记语言）
- [HTML（超文本标记语言）](#html超文本标记语言)
  - [行级元素](#行级元素)
  - [块级元素](#块级元素)
  - [行级块元素](#行级块元素)
  - [HTML 编码（字符集）](#html-编码字符集)
  - [HTML 字符实体](#html-字符实体)
- [元数据脚本](#元数据脚本)
  - [title 元素-全局属性](#title-元素-全局属性)
  - [mate 元素](#mate-元素)
- [分组内容](#分组内容)
  - [div 元素](#div-元素)
  - [ol 元素](#ol-元素)
  - [ul 元素](#ul-元素)
  - [li 元素](#li-元素)
- [文档 块](#文档-块)
  - [address 元素](#address-元素)
- [文本语义](#文本语义)
  - [span 元素](#span-元素)
  - [strong 元素](#strong-元素)
  - [em 元素](#em-元素)
  - [del 元素](#del-元素)
- [嵌入内容](#嵌入内容)
  - [img 元素 未学完](#img-元素-未学完)
- [表单元素](#表单元素)
  - [form 元素 还没学懂!](#form-元素-还没学懂)
  - [select 元素](#select-元素)
  - [option 元素](#option-元素)
  - [input 元素](#input-元素)
      - [做成表格](#做成表格)
- [分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线](#分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线)
  - [iframe 元素](#iframe-元素)
  - [在页面中使用flash](#在页面中使用flash)
    - [object 元素](#object-元素)
    - [param 元素](#param-元素)
    - [embed 元素](#embed-元素)
  - [其他](#其他)
- [表单元素](#表单元素-1)
  - [4. optgroup 元素](#4-optgroup-元素)
  - [5. textarea 元素](#5-textarea-元素)
- [配合表单元素](#配合表单元素)
  - [1. label 元素](#1-label-元素)
  - [2. datalist 元素](#2-datalist-元素)
  - [4. fieldset 元素](#4-fieldset-元素)
  - [5. legend 元素](#5-legend-元素)
- [表格元素](#表格元素)
  - [1.tabel 元素](#1tabel-元素)
  - [2.caption 元素](#2caption-元素)
  - [3.colgroup 元素(未学)](#3colgroup-元素未学)
  - [4.col 元素(未学)](#4col-元素未学)
  - [5.tbead 元素](#5tbead-元素)
  - [6.tbody 元素](#6tbody-元素)
  - [7.tfoot 元素](#7tfoot-元素)
  - [8.tr 元素](#8tr-元素)
  - [9.th 元素](#9th-元素)
  - [10.td 元素](#10td-元素)
- [其他元素](#其他元素)
  - [abbr 元素](#abbr-元素)
  - [time 元素](#time-元素)
  - [b 元素](#b-元素)
  - [q 元素](#q-元素)
  - [figure 元素 为学习](#figure-元素-为学习)
  - [blockquote 元素](#blockquote-元素)
  - [figcaption 元素(未学)](#figcaption-元素未学)
  - [br 元素](#br-元素)
  - [hr 元素](#hr-元素)
  - [link 元素](#link-元素)

## [行级元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Inline_elements)

一个行内元素只占据它对应标签的边框所包含的空间。

内容决定元素所占位置

不可以通过 css 改变宽高

## [块级元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Block-level_elements)

块级元素占据其父元素（容器）的整个水平空间，垂直空间等于其内容高度，因此创建了一个“块”。

可以通过 css 改变宽高

块级元素只能出现在 `<body>` 元素内

一般块级元素可以包含行内元素和其他块级元素。这种结构上的包含继承区别可以使块级元素创建比行内元素更”大型“的结构。

⭐HTML 标准中块级元素和行内元素的区别至高出现在 4.01 标准中。在 HTML5，这种区别被一个更复杂的[内容类别 (en-US)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories)代替。”块级“类别大致相当于 HTML5 中的[流内容 (en-US)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content)类别，而”行内“类别相当于 HTML5 中的[措辞内容 (en-US)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content)类别，不过除了这两个还有其他类别。

## 行级块元素

(例如 `<img>` )

内容决定大小

可以通过 css 改变宽高

凡是带有文本属性(`inline`)  的元素,都有文字特性 ,有文字特性就会被分割(间隔了4像素)

## [HTML 编码（字符集）](https://www.w3school.com.cn/html/html_charset.asp)

应用:为了正确显示 HTML 页面，Web 浏览器必须知道要使用哪个字符集。

HTML5 中的默认字符编码为 UTF-8。

如果 HTML5 网页使用的字符集与 UTF-8 不同，则应在 <meta> 标记中指定该字符集

## [HTML 字符实体](https://www.w3school.com.cn/html/html_entities.asp)

应用:HTML 中的预留字符必须被替换为字符实体。

在 HTML 中不能使用小于号（<）和大于号（>），这是因为浏览器会误认为它们是标签。

常见实例:

- 不间断空格;`&nbsp;`
- 小于号;`&lt;`
- 大于号;` &gt;`
- 回车: `<br>`

- 水平线: `<hr>`

# 元数据脚本

## [title 元素-全局属性](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/title)

应用:[全局属性](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes) 包含了表示咨询信息文本，和它属于的元素相关。这个信息通常存在，但绝不必要，作为提示信息展示给用户

一些典型用例：

- 链接：被链接文档的标题或描述
- 媒体元素，例如图像：描述或关联信息
- 段落：脚注或者相关的评论
- 引用：作者信息，以及其他

如果省略了这个属性，就意味着这个元素的最近祖先的标题仍然是相关的（并且可以用作元素的提示信息）。如果这个属性设为空字符串，它就明确意味着，它的最近祖先的标题是不相关的（并且不应用于这个元素的提示信息）。

- 额外的语义可以附加到<link>，<abbr>，<input> 和 { HTMLElement("menuitem") }} 元素的 title 属性

- title 属性可以包含多行。每个插入"回车键"(`LF`) 代表一个换行。

## [mate 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta)

应用: 提供了 HTML 文档的元数据。元数据不会显示在客户端，但是会被浏览器解析通常用于指定网页的描述，关键词，文件的最后修改时间，作者及其他元数据。

表示那些不能由其它 HTML 元相关（meta-related）元素（(<base>、<link>, <script>、<style> 或 <title>）之一表示的任何元数据信息

- charset 属性:声明了文档的字符编码。

- content 属性:包含 `http-equiv` 或 `name` 属性的值，具体取决于所使用的值。 

- http-equiv 属性属性定义了一个编译指示指令。这个属性叫做 `http-equiv(alent)` 是因为所有允许的值都是特定 HTTP 头部的名称

- name 属性:常见声明application-name(应用程序名称)、author(文档作者的名字)、description(一段简短而精确的、对页面内容的描述)、generator(生成此页面的软件的标识符)、keywords(与页面内容相关的关键词，使用逗号分隔)、referrer(控制由当前文档发出的请求的 `HTTP` `Referer` 请求头)。

> `name` 和 `content` 属性可以一起使用，以名 - 值对的方式给文档提供元数据，其中 name 作为元数据的名	称，content 作为元数据的值。

# 分组内容

## [div 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/div)

应用:是一个通用型的流内容容器，在不使用CSS的情况下，其对内容或布局没有任何影响。

**⚠警告:<div> 元素应当仅在没有任何其它语义元素（比如 <article> 或 <nav>）可用时使用。**

## [ol 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ol)

应用:表示有序列表，通常渲染为一个带编号的列表。

reversed 属性;此布尔值属性指定列表中的条目是否是倒序排列的，即编号是否应从高到低反向标注

[**`start`**](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ol#attr-start) 属性;一个整数值属性，**指定了列表编号的起始值**。此属性的值应为阿拉伯数字，尽管列表条目的编号类型 `type` 属性可能指定为了罗马数字编号等其他类型的编号。比如说，想要让元素的编号从英文字母 "d" 或者罗马数字 "iv" 开始，都应当使用 `start="4"`。

type 属性;设置编号的类型：

- `a` 表示小写英文字母编号
- `A` 表示大写英文字母编号
- `i` 表示小写罗马数字编号
- `I` 表示大写罗马数字编号
- 1 表示数字编号（默认）编号类型适用于整个列表，除非在 <ol> 元素的 <li> 元素中使用不同的 type 属性。

## [ul 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ul)

应用:表示一个内可含多个元素的无序列表或项目符号列表。

[**`type`**](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ul#attr-type) 属性;已弃用

用于设置列表的着重号样式，被定义在 [HTML3.2](https://developer.mozilla.org/zh-CN/HTML3.2) 和过渡版本 [HTML 4.0/4.01](https://developer.mozilla.org/zh-CN/HTML4.01) 中的可用值有：

- `circle`

- `disc`

- `square`第四种着重号样式被定义在 WebTV 接口中，但并不是所有浏览器都支持：`triangle`如果未设置此 HTML 属性且没有 [CSS](https://developer.mozilla.org/zh-CN/docs/Web/CSS) [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type) 属性作用于这个元素，用户代理会决定使用哪种着重号样式，一般来说这也和嵌套的层级数有关。

  > 不要使用这个属性，它已经被废弃了：使用 [CSS](https://developer.mozilla.org/zh-CN/docs/Web/CSS) [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type) 属性作为代替。

**使用说明:**

- `<ul>` 元素用来将**没有数字顺序**的一组数据进行分组，并且它们的数字顺序是没有意义的。举个例子，无序列表的列表项通常通过一个字符进行装饰，这些字符的形式可以是点，圆乃至方形．虽然这个字符没有直接在页面上定义，但是可以用与之相关的 CSS 对其进行操作，例如使用 `list-style-type` 属性。
- 在 `<ol>` 和 `<ul>` 元素中，嵌套列表没有深度和嵌套顺序的限制。
- **⭐`<ol>` 和 `<ul>` 元素二者都代表一组数据，不过它们彼此是有区别的，ol 元素中的顺序是有意义的。如果想确定你到底需要使用哪一个列表元素，你可以试着去改变数据的顺序。如果想表达的语义改变了，你就需要使用 ol 元素，否则你该使用 ul 元素。**

> 一个功能有很多功能子项组成,每一个功能子项的功能和样式基本上是相同的只不过内容上可能有小小的差异,很多的功能子项组成了一个大功能.  使用 `ul>li` 组成,因为更符合天生的结构

## [li 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/li)

应用:表示列表里的条目。它必须包含在一个父元素里：一个有序列表 <ol>，一个无序列表 <ul>，或者一个菜单 [<menu>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/menu)。

> 旧的规则中 `<div>` 也可以作为父元素，但是并不提倡。

value 属性;这个整数型属性表明了本 <li> 元素在有序列表（由 <ol> 元素定义）中的序号。本属性值只能用数字，即使列表使用罗马数字或字母来展示。随后的列表条目会从设置的值开始计数。value 属性对于无序列表 (<ul>) 或者菜单 (<menu>) 无效。如图:

![image-20221101191648905](E:\文档\Web学习\笔记\HTML笔记\imgs\image-20221101191648905.png)





# 文档 块

## [address 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/address)

应用:提供了某个人或某个组织（等等）的联系信息。

**使用说明:**

- 当表示一个和联系信息无关的任意的地址时，请改用 <p> 元素而不是 <address> 元素。

- 这个元素不能包含除联系信息之外的任何信息，比如出版日期（这应当被包含在 <time> 元素之中）。
  通常，<address> 元素可以放在 <footer> 元素之中（如果存在的话）

-  <address> 可以使用在多种语境中，例如在文章开头提供商务的联系方式，或者放在<article>元素内，指明该文章的作者。

# 文本语义

## [span 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/span)

应用:短语内容的通用行内容器，并没有任何特殊语义。

<span> 与 <div> 元素很相似，但 <div> 是一个 块元素 而 <span> 则是行内元素.

**⚠警告:应该在没有其他合适的语义元素时才使用它。**

## [strong 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/strong)

应用:表示文本十分重要，一般用粗体显示。

> ### Bold vs. Strong
>
> 新的开发者经常感到疑惑，为什么在一个渲染的网站上会有这么多方式来表达同样的东西。Bold 和 Strong 可能就是这其中的一种。为什么使用<strong></strong>而不是<b></b>? 使用 strong 的话你不得不打更多的字母，却产生出和 b 同样的效果，对吧？
>
> 也许并不是；strong 是一个逻辑状态，而 bold 是一个物理状态。逻辑状态分离内容和表现形式，使用逻辑状态允许你用各种不同的方式来表达。比如你想把文字渲染成红色，使用其它大小的字体、带有下划线或其他样式，而不是加粗的样式。必须要理解使用 strong 呈现出的表现形式不同于单纯的加粗。因为 bold 是一个物理状态，他没有区分表现形式和内容。如果让 bold 做了加粗文本外的其它任何事情，都将会令人困惑而且也不符合逻辑。
>
> 同样应该注意<b></b> 还有其他用途，比如想单纯地吸引注意而不增加其重要性。
>
> ### Emphasis vs. Strong
>
> 在 HTML4 时，Strong 简单地表示一个更强的强调 (emphasis)，而在 HTML5 中，这个元素被描述为表征“内容强烈的重要性 (strong importance for its contents) ”。这是一个重要的区别。Em 标签 (Emphasis) 用于改变一个句子的意思 (比如"我<em>*喜欢</em>*胡萝卜" 和"我喜欢<em>*胡萝卜</em>*"，分别强调喜欢和胡萝卜), Strong 用来对一个句子的部分增加重要性 (比如 "**警告！** 这**非常危险**。") Strong 和 Emphasis 都可以分别通过嵌套来增加相对重要性或强调重点。

## [em 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/em)

应用:**着重元素**,标记出需要用户着重阅读的内容， `<em>` 元素是可以嵌套的，嵌套层次越深，则其包含的内容被认定为越需要着重阅读。

> 通常地，该元素会被浏览器展示为斜体文本，但是，它不应该仅仅用于应用斜体样式；为此目的，请使用 CSS 样式。使用 <cite> 元素标记作品的标题（书籍，戏剧，歌曲等）；它通常也采用斜体样式，但具有不同的含义。使用 <strong> 元素标记比周围文本更重要的文本。

> ## <i> vs. Emphasis
>
> 新的开发人员看到多个元素产生相似的效果，经常被混淆。`<em>` 和 `<i>` 就是一对常见的例子，因为它们都对文字斜体化。它们的区别是什么？应该使用哪一个？
>
> 在默认情况下，它们的视觉效果是一样的。但语义是不同的。 `<em>` 标签表示其内容的着重强调，而 `<i>` 标签表示从正常散文中区分出的文本，例如外来词，虚构人物的思想，或者当文本指的是一个词语的定义，而不是其语义含义。（作品的标题，例如书籍或电影的名字，应该使用 `<cite>`。）
>
> 这意味着，正确使用哪一个取决于具体的场景。两者都不是纯粹为了装饰的目的，那是 CSS 样式所做的。
>
> 一个 `<em>` 的例子可能是："Just *do* it already!"，或："We *had* to do something about it"。人或软件在阅读文本时，会对斜体字的发音使用重读强调。
>
> 一个 `<i>` 的例子可能是："The *Queen Mary* sailed last night"。在这里，没有对 "Queen Mary" 这个词添加强调或重要性。它只是表明，谈论的对象不是一个名叫玛丽的女王，而是一艘名字叫玛丽的船。另一个 `<i>` 的例子可能是："The word *the* is an article"。

## [del 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/del)

应用:表示一些被从文档中删除的文字内容。比如可以在需要显示修改记录或者源代码差异的情况使用这个标签。<ins>标签的作用恰恰于此相反：表示文档中添加的内容。

这个标签通常（但不一定要）在文字上显示删除线。

**两个属性都没学懂???**

cite 属性:提供一个 URI，其中的资源解释作出修改的原因（比如：根据某次会议讨论）。

datetime 属性:说明修改的时间和日期，这里的时间和日期格式要符合规范。如果设置的值不符合该规范，那么它将没有任何意义。

# 嵌入内容


## [img 元素 未学完](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img)

应用:将一份图像嵌入文档。 

src 属性:是**必须的**，它包含了你想嵌入的图片的文件路径。

1. 网上的url
2. 本地的绝对路径(同一个文件夹下)
3. 本地的相对路径(不同文件夹)

alt 属性:包含一条对图像的文本描述，这不是强制性的，但对无障碍而言，它**难以置信地有用**——屏幕阅读器会将这些描述读给需要使用阅读器的使用者听，让他们知道图像的含义。如果由于某种原因无法加载图像，普通浏览器也会在页面上显示`alt` 属性中的备用文本：例如，网络错误、内容被屏蔽或链接过期时。当图像上没有 `alt` 属性时，一些屏幕阅读器可能会读出图像的文件名。如果文件名不能代表图像的内容，甚至是一团乱码，这可只能造成令人迷惑的体验。

> 如果把这个属性设置为空字符串（alt=""），则表明该图像不是内容的关键部分（这是一种装饰或者一个追踪像素点），非可视化浏览器在渲染的时候可能会忽略它。而且，如果图片加载失败，可视化浏览器会隐藏表示图片损坏的图标。将图像复制并粘贴为文本，或是将图像的链接保存为浏览器书签时，也会用到此属性。

src 属性:图像的 URL，这个属性对 <img> 元素来说是必需的。在支持 srcset 的浏览器中，src 被当做拥有一个像素密度的描述符 1x 的候选图像处理，除非一个图像拥有这个像素密度描述符已经被在 srcset 或者 srcset 包含 w 描述符中定义了。

*srcset 属性:以逗号分隔的一个或多个字符串列表表明一系列用户代理使用的可能的图像。每一个字符串由以下组成：*

1.  指向图像的 URL。

2. 可选地，再加一个空格之后，附加以下的其一：

- 一个宽度描述符，这是一个正整数，后面紧跟 'w' 符号。该整数宽度除以 sizes 属性给出的资源（source）大小来计算得到有效的像素密度，即换算成和 x 描述符等价的值。
- 一个像素密度描述符，这是一个正浮点数，后面紧跟 'x' 符号。如果没有指定源描述符，那它会被指定为默认的 1x。在相同的 srcset 属性中混合使用宽度描述符和像素密度描述符时，会导致该值无效。重复的描述符（比如，两个源在相同的 srcset 两个源都是 2x）也是无效的。用户代理根据自己的判断选择任何可用的来源。这为他们提供了很大的余地，可以根据用户偏好或带宽条件等因素来调整他们的选择

title 属性:

- title 属性不是 alt 属性可接受的替代品。并且，避免将 alt 属性的值直接复制到同一幅图片的title 属性上。这样可能会让一些屏幕阅读器把同一段描述读两遍，造成一定程度上的困扰。

- title 属性也不该被用作一幅图片在 alt 之外的补充说明信息。如果一幅图片需要小标题，使用 figure 或 figcaption 元素。

- title 元素的值一般作为提示条 (tooltip) 呈现给用户，在光标于图片上停下后显示出来。尽管这确实能给用户提供更多的信息，您不该假定用户真的能看到：用户可能只有键盘或触摸屏。如果要把特别重要的信息提供给用户，选择上面提供的一种方法将其内联显示，而不是使用 title 。

***使用 CSS 为 <img> 附加样式***
*<img> 是一个可替换元素。它的 display 属性的默认值是 inline，但是它的默认分辨率是由被嵌入的图片的原始宽高来确定的，使得它就像 inline-block 一样。你可以为 <img> 设置 border/border-radius、padding/margin、width、height 等等的 CSS 属性。*

*<img> 没有基线（baseline），这意味着，当在一个行内格式的上下文（an inline formatting context）中使用 vertical-align: baseline 时，图像的底部将会与容器的文字基线对齐。*

*可以使用object-position属性在元素的方框内定位图像，使用object-fit属性调整方框内图像的大小(例如，即使需要剪切，图像是应该适合方框还是填充方框)。*

*根据图像文件的类型，图像可能会有一个原始分辨率（intrinsic dimension）或者叫原始宽高。对于一些类型的图像，原始分辨率并不是必要的。比如说，SVG 图像，如果它们的根 <svg> 元素没有 width 或 height 属性，SVG 图像就可以没有原始分辨率。*

*备注： 原始分辨率/原始宽高是图像的固有属性，基本上就是图像本身的分辨率/宽高。只与图像本身有关，与 <img> 元素的属性、显示分辨率等等无关。点阵图像通常有且只有一个随图片宽高变化的原始分辨率，而矢量图像可以没有。不过，编辑矢量图像时，通常可以手动/编辑器自动为其设置原始分辨率。*

# 表单元素

##  [form 元素 还没学懂!](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)

应用:通常，会将整个表单元素，放置form元素的内部，作用是当提交表单时，会将form元素内部的表单内容以合适的方式提交到服务器。

form元素对开发静态页面没有什么意义。

    <form action="" method=></form>

action 属性:处理表单提交的 URL。

method 属性:提交表单的方式。

- post ：指的是 HTTP POST 方法；表单数据会包含在表单体内然后发送给服务器。

- get ：指的是 HTTP GET 方法；表单数据会附加在 action 属性的 URL 中，并以 '?' 作为分隔符，没有副作用 时使用这个方法。

- dialog ：如果表单在 `<dialog>` 元素中，提交时关闭对话框。此值可以被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素中的 formmethod 属性覆盖。

```
<form action="https://www.baidu.com/" method="GET">
        <p>
            账号：
            <input type="text" name="loginid">
        </p>
        <p>
            密码：
            <input type="password" name="loginpwd">
        </p>
        <p>
            城市：
            <select name="city">
                <option value="1">成都</option>
                <option value="2">重庆</option>
                <option value="3">北京</option>
                <option value="4">哈尔滨</option>
            </select>
        </p>
        <p>
            <button type="submit">提交</button>
        </p>
</form>

```

发送数据需要:

1. 数据的名 
2. 数据的值;如图: `name` 属性内是数据的名称,等号"="后面的是属性是数据的值
3. 问好"?"后面的就时提交的数据
4. MD5加密

![image-20221101154230410](E:\文档\Web学习\笔记\HTML笔记\imgs\image-20221101154230410.png)

## [select 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select)

应用:下拉列表先择框,表示一个提供选项菜单的控件。
通常与 `<label>` 元素关联在一起。

每个菜单选项由 `<select>` 中的一个 `<option>`元素定义。

multiple 属性:这个布尔值属性表示列表中的选项是否支持**多选**。

size 属性:控制一次展示的个数,控件中同时可见的行数.

disabled 属性:这个布尔值的属性表示用户**不能**与该表单控件交互。

## [option 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)

应用:用于定义在 `<select>` , `<optgroup>` 或 `<datalist>` 元素中包含的项。`<option>` 可以在弹出窗口和 HTML 文档中的其他项目列表中表示菜单项。

**`<option>` 的内容默认是数据的 `value`**

可以将 `<option>` 元素放在 `<optgroup>` 元素中以为下拉菜单创建不同的选项分组
selected 属性(**默认选中**):这个布尔属性存在时表明这个选项是否一开始就被选中。

## [input 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)

应用：用于为基于 Web 的表单创建交互式控件，以便接受来自用户的数据; 可以使用各种类型的输入数据和控件小部件，具体取决于设备和用户代理。

type 属性：表示输入框的类型。

#### 做成表格 

```
type：text ，普通文本输入框
  
type：password ，密码框
  
type: date ，输入日期的控件（年、月、日，不包括时间）。（存在兼容性问题）

type: radio ，单选框(需设置name属性,允许在多个拥有相同 name 值的选项中选中其中一个。)
  
type: checkbox ，多选框(需设置name属性)
  
type: search ，搜索框（存在兼容性问题,在支持的浏览器中可能有一个删除按钮，用于清除整个区域。拥有动态键盘的设备上的回车图标会变成搜索图标。）
  
type: range ，滑动框（存在兼容性问题，用于输入不需要精确的数字。控件是一个范围组件，默认值为正中间的值。同时使用 min 和 max 来规定值的范围。）

type: color ，颜色选择框

type: number ，数字输入框（可设置min & max控制最小值和最大值,step属性控制步进值）
  
type: file ，文件上传框
```

value 属性：表示输入框的值。（内容）

placeholder 属性：显示提示的文本，文本框没有内容时显示。

maxlength 属性：如果 `type` 的值是 `text` 、`email` 、 `search` 、 `password` 、 `tel` 或 `url` ，那么这个属性指明了用户最多可以输入的字符个数（按照 `Unicode` 编码方式计数）；对于其他类型的输入框，该属性被忽略。

checked 属性:当 type 属性的值为 radio 或者 checkbox，则该布尔属性的存在与否表明了该控件是否是**默认选择状态**。 

list 属性: `list` 属性的值是位于同一文档中的 `<datalist>` 元素的id。 

**input 元素可以制作按钮**

当type值为：reset(重置)、submit(提交)、button(没有默认行为的按钮)时，input表示按钮。

`onfocus=""` ;获得焦点

`onblur=""` ;失去焦点

# 分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线分割线



## [iframe 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/iframe)

应用:在网页中嵌入另一个页面

可替换元素

        <iframe src="" frameborder="0"></iframe>

src 属性：网页的地址

name 属性：与`<a>`元素的`target`属性相关联.

## 在页面中使用flash
```
<iframe src="//player.bilibili.com/player.html?aid=57100756&bvid=BV1yx411d7Rc&cid=103978377&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
```
### [object 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/object)

应用:引入一个外部资源

可替换元素

       <object data="" type=""></object>


data 属性: 数据,地址

type 属性: 类型 (使用MIME[^1])

[^1] MIME(Multipurpose Internet Mail Extensions)
多用途互联网邮件类型：比如，资源是一个jpg图片，MIME：image/jpeg

```

 <object data="./example.swf" type="application/x-shockwave-flash">
        <param name="quality" value="high">
        <embed quality="high" src="./example.swf" type="application/x-shockwave-flash">
</object>

```

### [param 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/param)

应用:为 `<object>` 元素定义参数

         <param name="" value="">

### [embed 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/embed)

应用:将外部内容嵌入文档中的指定位置

可替换元素

    <embed src="" type="">

src 属性:资源位置

type 属性:类型

属性直接写在内部.如


    <embed  quality="high" src="" type="">

**注意**为了保证网页兼容性,一般嵌套书写

```

<object data="" type="">
    <embed src="" type="">
</object>

```

## 其他

可替换元素

1. 通常行盒
2. 通常显示的内容取决于元素的属性
3. CSS不能完全控制其中的样式
4. 具有行快盒的特点





# 表单元素

应用：主要用于收集用户数据



## 4. [optgroup 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/optgroup)

应用:为 `<select>` 元素中的选项创建分组。

    <optgroup label="">

label 属性:选项组的名字，浏览器用以在用户界面中标记选项。使用这个元素时必须加上这个属性。

## 5. [textarea 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)

应用:多行文本框。表示一个多行纯文本编辑控件。

    <textarea name="" id="" cols="30" rows="10"></textarea>

cols 属性:文本域的可视宽度。横向上有多少个文字。

rows 属性:元素的输入文本的行数（显示的高度）。

# 配合表单元素

## 1. [label 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)

应用:普通元素，通常配合单选和多选框使用

- 显示关联

可以通过for属性，让label元素关联某一个表单元素，for属性书写表单元素id的值
```

<input type="radio" id="radMale" name="gender">
    <label for="radMale">男</label>

<input type="radio" id="radFemale" name="gender">
    <label for="radFemale">女</label>


```
- 隐式关联

```
<label>
    <input name="gender" type="radio">
    男
</label>
<label>
    <input name="gender" type="radio">
    女
</label>
```

## 2. [datalist 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist)

应用:表示其它表单控件可选值。

该元素本身不会显示到页面，通常用于和普通文本框配合。

id 属性:属性值应与 `list` 对应。

```

<label>
    Choose a browser from this list:
        <input list="browsers" name="myBrowser" />
</label>

<datalist id="browsers">
  <option value="Chrome">谷歌浏览器</option>
  <option value="Firefox">火狐浏览器</option>
  <option value="Internet Explorer">IE浏览器</option>
  <option value="Opera">欧鹏浏览器</option>
  <option value="Safari">苹果浏览器</option>
</datalist>

```

## 4. [fieldset 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)

应用:对表单中的控制元素进行分组。

通常配合`<legend>`使用, `<legend>` 作为分组名称。

```

<h1>修改用户信息</h1>
        <fieldset>
            <legend>账号信息</legend>
            <p>
                用户账号：
                <input type="text" value="aaaaa" readonly>
            </p>
            <p>
                用户密码：
                <input type="password">
            </p>
        </fieldset>

```

## 5. [legend 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)

应用: 元素用于表示其父元素 `<fieldset>` 的内容标题。


# 表格元素

在CSS技术出现之前，网页通常使用表格布局。

##  1.[tabel 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table)

![术语1](../../../Web%E5%AD%A6%E4%B9%A0/%E8%A2%81%E8%80%81%E5%B8%88html%2Bcss%E6%BA%90%E7%A0%81/4.%20HTML%E8%BF%9B%E9%98%B6/6.%20%E8%A1%A8%E6%A0%BC%E5%85%83%E7%B4%A0/%E8%AF%B4%E6%98%8E/%E6%9C%AF%E8%AF%AD1.png)

应用:表示一个表格。

允许的内容:
按照这个顺序：

- 一个可选的 `<caption>` (表格标题)元素
- 零个或多个的 `<colgroup>` (表格列组)元素
- 一个可选的 `<thead>` (表头)元素

- 下列任意一个：
    - 零个或多个 `<tbody>`(表格主体)
    - 零个或多个 `<tr>`(表格中的一行)
    - 一个可选的 `<tfoot>` (表尾)元素

CSS 属性：

对齐方式：在实现表格内容对齐时不推荐使用 `align` 。应设置 `margin-left` 、`margin-right` 为 `auto` ( 或者 `margin` 设置为 `0 auto`) 来实现类似于 `align` 属性的效果。

border-collapse 属性:用来决定表格的边框是分开的还是合并的。在分隔模式下`默认值:separate`，相邻的单元格都拥有独立的边框。在合并模式下`collapse`，相邻单元格共享边框。

border-spacing 属性:指定相邻单元格边框之间的距离（只适用于边框分离模式）。
- 当指定一个 `<length>` 值时，它同时定义单元格之间的水平和垂直间距。
- 当指定两个 `<length>` 值时，第一个值定义单元格之间的水平间距(即相邻列中单元格之间的间距)，第二个值定义单元格之间的垂直间距(即相邻行中单元格之间的间距)。

```
/* <length> */
border-spacing: 2px;

/* horizontal <length> | vertical <length> */
border-spacing: 1cm 2em;

```

## 2.[caption 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption)

应用:一个表格的标题， 它常常作为 `<table>` 的第一个子元素出现。

caption-side 属性: 设置表格标题 `<caption>` 放置的位置。

```

/* Directional values */
caption-side: top;
caption-side: bottom;

```

## 3.[colgroup 元素(未学)](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/colgroup)

应用:定义表中的一组列表。

`<colgroup>` 必须出现在任何可选的 `<caption>` 元素之后但在` <thead>` ， `<th>` ， `<tbody>` ， `<tfoot>` 和 `<tr>` 元素之前。


## 4.[col 元素(未学)](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/col)

***由于不会在普通浏览器中产生任何视觉效果，很难判断浏览器是否支持 `scope` 属性。***

应用:定义表格中的列，并用于定义所有公共单元格上的公共语义。它通常位于 `<colgroup>` 元素内。

span 属性:该属性值为一个正整数，表示该 `<col>` 元素横跨的列数。默认值为 1。



## 5.[tbead 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/thead)

应用:表头。

允许内容:零或多个 `<tr>` 元素。

## 6.[tbody 元素](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody)

应用:表示表格的主体。

允许内容:零或多个 `<tr>` 元素。

需要在父元素 `<table>` 中，可以将 `<tbody>` 元素添加到 `<caption>` 、`<colgroup>` 和 `<thead>` 元素之后。

## 7.[tfoot 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/tfoot) 

应用:表尾。

`<tfoot>` 必须出现在一个或多个 `<caption>`，`<colgroup>` ， `<thead>` , `<tbody>` ，或 `<tr>` 元素之后。

## 8.[tr 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/tr)

![术语2](../../../Web%E5%AD%A6%E4%B9%A0/%E8%A2%81%E8%80%81%E5%B8%88html%2Bcss%E6%BA%90%E7%A0%81/4.%20HTML%E8%BF%9B%E9%98%B6/6.%20%E8%A1%A8%E6%A0%BC%E5%85%83%E7%B4%A0/%E8%AF%B4%E6%98%8E/%E6%9C%AF%E8%AF%AD2.png)

应用:定义表格中的行。 同一行可同时出现 `<td>` 和 `<th>` 元素。

允许的内容: 0 或多个 `<td>` 或 `<th>`元素,或者它们的混合。

## 9.[th 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th)

 ![术语3](../../../Web%E5%AD%A6%E4%B9%A0/%E8%A2%81%E8%80%81%E5%B8%88html%2Bcss%E6%BA%90%E7%A0%81/4.%20HTML%E8%BF%9B%E9%98%B6/6.%20%E8%A1%A8%E6%A0%BC%E5%85%83%E7%B4%A0/%E8%AF%B4%E6%98%8E/%E6%9C%AF%E8%AF%AD3.png)

应用:定义表格内的表头(标题)单元格。

colspan 属性(跨越N列):这个属性包含一个正整数表示了每单元格中扩展**列**的数量。默认值为1 。超过 1000 的值被视作 1000。

rowspan 属性:这个属性包含一个正整数表示了每单元格中扩展**行**的数量。默认值为1. 如果该值被设置为 0, 这个单元格就被扩展为 ( `<thead>` ， `<tbody>` 或 `<tfoot>` ) 中表格部分的最后一个元素。

headers 属性:包含了一个空间分隔的字符串的列表，每个与其他 `<th>` 元素相关联的id 属性一一对应。

scope 属性:这个枚举属性定义了头(在 `<th>` 元素中定义)与之相关的单元格。它可能有以下值:

- row:标题与它所属**行**的所有单元格相关。

- col:标题与它所属**列**的所有单元格相关。

- rowgroup:标题属于一个行组，与它的所有单元格相关。根据 `<table>` 元素中dir属性的值，可以将这些单元格放置在头部的右侧或左侧。

- colgroup:标题属于colgroup，与它的所有单元格相关。

- auto:如果没有指定scope属性，或者其值不是row、col或rowgroup或colgroup，则浏览器将自动选择标题单元格应用的单元格集。





## 10.[td 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td)

应用:定义了一个包含数据的表格单元格。


# 其他元素

## [abbr 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/abbr)

应用:用于代表缩写，并且可以通过可选的 title 属性提供完整的描述。

    <body>
        <abbr title="Cascading Style Sheets">CSS</abbr>用于为页面添加样式
    </body>

## [time 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/time)

应用:提供给浏览器或搜索引擎用的时间。

    <p>我在 <time datetime="2016-02-14">情人节</time> 有个约会</p>

datetime 属性:规定日期或时间。在该元素的内容中未指定日期或时间时，使用该属性。(该属性在所有浏览器中不会渲染任何特殊的效果。)

datetime 属性取值:
YYYY-MM-DDThh:mm:ssTZD	

日期或时间。下面解释了其中的成分：

YYYY - 年 (例如 2011)
MM - 月 (例如 01 表示 January)
DD - 天 (例如 08)
T - 必需的分隔符，若规定时间的话
hh - 时 (例如 22 表示 10.00pm)
mm - 分 (例如 55)
ss - 秒 (例如 03)
TZD - 时区标识符 (Z 表示祖鲁，也称为格林威治时间)

## [b 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/b)

应用:用于吸引读者的注意到该元素的内容上（如果没有另加特别强调）。这个元素过去被认为是粗体（Boldface）元素。

同等重要的文本做区分。

## [q 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/q)

应用:表示一小段引用文本。对于长的文本的引用请使用 `<blockquote>` 替代。

大多数现代浏览器，会为 `<q>` 文本添加引号。

    <q cite="http://en.wikipedia.org/wiki/Kenny_McCormick#Cultural_impact">
     Oh my God, you/they killed Kenny!
    </q>

cite 属性:这个属性的值是 URL，意在指出被引用的文本的源文档或者源信息。这个属性重在解释这个引用的参考或者是上下文。

## [figure 元素 为学习](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/figure)

应用：

## [blockquote 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/blockquote)

应用:表示大段引用的文本。

     <blockquote cite="https://www.huxley.net/bnw/four.html">
        <p>Words can be like X-rays, if you use them properly—they’ll go through anything. You read and you’re pierced.</p>
    </blockquote>

cite 属性:是一个标注引用的信息的来源文档或者相关信息的 URL。通常用来描述能够解释引文的上下文或者引用的信息。

## [figcaption 元素(未学)](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/figcaption)

应用:

## [br 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/br)

应用:在文本在换行。文本中生成一个换行（回车）符号。

## [hr 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/hr)

应用:表示段落级元素之间的主题转换。在 HTML 的早期版本中，它是一个水平线。现在它仍能在可视化浏览器中表现为水平线，但目前被定义为语义上的，而不是表现层面上。

## [link 元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link)

应用:链接外部资源(CSS、图标)。

    <link rel="stylesheet" href="">

[rel 属性](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Link_types):命名链接文档与当前文档的关系。

- stylesheet :定义要用作样式表的外部资源。如果没有设置 type，在进一步检查之前，浏览器应该假定它是 text/css 样式表。

- icon :通常用于设置网页的图标。

href 属性:指定被链接资源的URL。 URL 可以是绝对的，也可以是相对的。







