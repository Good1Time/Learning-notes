# 伪类选择器 nth选择器复习!!

CSS **伪类** 是添加到选择器的关键字，指定要选择的元素的**特殊状态**。例如，`:hover`可被用于在用户将鼠标悬停在按钮上时改变按钮的颜色。

用于选择处于特定状态的元素，比如当它们是这一类型的第一个元素时，或者是当鼠标指针悬浮在元素上面的时候。<u>它们表现得会像是你向你的文档的某个部分应用了一个类一样</u>，帮你在你的标记文本中减少多余的类，让你的代码更灵活、更易于维护。

结构：伪类总是由一个“冒号”(:) 后跟伪类的名称和<u>可选的括号之间的值组成（`:nth-child()`）</u>。

## 爱和法则

应用:为了可以正确地渲染链接元素的样式，`:link` 伪类选择器应当放在其他伪类选择器的前面，并且遵循 `LVHA` 的先后顺序，即：`:link` — `:visited` — `:hover` — `:active`。`:focus` 伪类选择器常伴随在 `:hover` 伪类选择器左右，需要根据你想要实现的效果确定它们的顺序

`a:link` - 正常，未访问过的链接 `a:visited` - 用户已访问过的链接 `a:hover` - 当用户鼠标放在链接上时 `a:active` - 链接被点击的那一刻

### [:link 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:link)

应用:选择未被访问的链接，并设置其样式

**注意:** `:link` 选择器对已经访问的链接没有样式。

### [:visited 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:visited)

应用:选择已访问的链接，并设置其样式

注意:未设置颜色或透明的属性不能使用:visited。

### [:hover 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:hover)

应用:选择鼠标指针浮动在其上的元素，并设置其样式

**提示:** :hover 选择器器可用于所有元素，不仅是链接

### [:active 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:active)

应用:选择活动链接，并设置其样式

当您在一个链接上点击时，它就会成为活动的（激活的）,当用鼠标交互时，它代表的是用户按下按键和松开按键之间的时间。

一般被用在 `<a>` 和 `<button>` 元素中。这个伪类的一些其他适用对象包括包含激活元素的元素，以及可以通过他们关联的 `<label>` 标签被激活的表格元素。



## [:first-child 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-child)

应用:表示选择在兄弟列表中排在第一位的元素

## [:last-child 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:last-child)

应用:表示选择在兄弟列表中排在最后一位的元素

**last和first**在**选择最后标签不是自己元素的时候会有问题?????**

##  [:only-child 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:only-child)

应用:选择没有任何兄弟元素的元素,等效的选择器还可以写成 `:first-child:last-child`或者`:nth-child(1):nth-last-child(1)`,当然，前者(`:only-child`) 的权重会低一点。

## [:invalid 选择器 未学习](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid)



## [:focus 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus)

应用:元素聚焦时的样式,获得焦点的元素。只会在用户**使用键盘控制**，选定元素的时候激活

tabindex 属性:通过设置数字可以改变聚焦顺序。

### [:focus-within 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus-within)

应用: 元素自身或者它的某个后代匹配 `:focus` 伪类。

### [:focus-visible 选择器 不明白](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus-visible)

应用:这个选择器可以有效地根据用户的输入方式 (鼠标 vs 键盘) 展示不同形式的焦点。