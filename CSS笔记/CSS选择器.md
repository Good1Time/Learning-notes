# [CSS 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Selectors)

CSS 选择器是 CSS 规则的第一部分。它是元素和其他部分组合起来告诉浏览器哪个 HTML 元素应当是被选为应用规则中的 CSS 属性值的方式。选择器所选择的元素，叫做“选择器的对象”。

## 基本选择则器

**通配符选择器**（Universal selector）
选择所有元素。例子：* 将匹配文档的所有元素。

**元素(标签)选择器**（Type selector）
按照给定的节点名称，选择所有匹配的元素 例子：input 匹配任何 <input> 元素。

**类选择器**（Class selector）
按照给定的 class 属性的值，选择所有匹配的元素。例子：.index 匹配任何 class 属性中含有 "index" 类的元素。

**ID 选择器**（ID selector）
按照 id 属性选择一个与之匹配的元素。需要注意的是，一个文档中，每个 ID 属性都应当是唯一的。例子：#toc 匹配 ID 为 "toc" 的元素。

**属性选择器**（Attribute selector）
按照给定的属性，选择所有匹配的元素。 例子：[autoplay] 选择所有具有 autoplay 属性的元素（不论这个属性的值是什么）。

## 分组选择器

**选择器列表**（Selector list）
`,` 是将不同的选择器组合在一起的方法，它选择所有能被列表中的任意一个选择器选中的节点。 语法：A, B 示例：div, span 会同时匹配 <span> 元素和 <div> 元素。

## 组合(关系)选择器

**后代组合器**（Descendant combinator）
“ ”（空格）组合器选择前一个元素的后代节点。 例子：div span 匹配所有位于任意 <div> 元素之内的 <span> 元素。

**直接子代组合器**（Child combinator）
`>` 组合器选择前一个元素的直接子代的节点。例子：ul > li 匹配直接嵌套在 <ul> 元素内的所有 <li> 元素。

**一般兄弟组合器**（General sibling combinator）
~ 组合器选择兄弟元素，也就是说，后一个节点在前一个节点后面的任意位置，并且共享同一个父节点。 语法：A ~ B 例子：p ~ span 匹配同一父元素下，<p> 元素后的所有 <span> 元素。

**紧邻兄弟组合器**（Adjacent sibling combinator）
`+` 组合器选择相邻元素，即后一个元素紧跟在前一个之后，并且共享同一个父节点。 语法：A + B 例子：h2 + p 会匹配所有紧邻在 <h2> (en-US) 元素后的 <p> 元素。

## 伪选择器

**伪类**
`:` 伪选择器支持按照未被包含在文档树中的状态信息来选择元素。 例子：a:visited 匹配所有曾被访问过的 <a> 元素。

**伪元素**
`::` 伪选择器用于表示无法用 HTML 语义表达的实体。 例子：p::first-line 匹配所有 <p> 元素的第一行。
