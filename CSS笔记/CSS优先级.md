# [CSS 优先级](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Specificity)

浏览器通过优先级来判断哪些属性值与一个元素最为相关，从而在该元素上应用这些属性值。优先级是基于不同种类**选择器**组成的匹配规则。

## 优先级的计算

优先级就是分配给指定的 CSS 声明的一个**权重**，它由匹配的选择器中的每一种选择器类型的**数值**决定。

当同一个元素有多个声明的时候，优先级才会有意义。

因为每一个直接作用于元素的 CSS 规则总是会接管/覆盖（take over）该元素**从祖先元素继承**而来的规则。

 **当优先级与多个 CSS 声明中任意一个声明的优先级相等的时候，CSS 中最后的那个声明将会被应用到元素上。**

### 下面列表中，选择器类型的优先级： *⭐在老的版本是256进制*
|选择器|权重值|
| :--- | :---- |
|**`important`**|Infinity|
|**行间样式(内联样式)**|1000|
|**`id` 选择器**（例如，`#example`）|100|
|**`class` 选择器**(例如，`.example`) 和 **属性选择器**（例如，`[type="radio"]`） 和 **伪类选择器**（例如，`:hover`）|10|
|**标签(元素)选择器**（例如，`h1`） 和 **伪元素选择器**（例如，`::before`）|1|
|**通配符**（*） 和 **关系选择器** （ `+` ,` >` , `~` , `" "(空格)` ） 和 **否定伪类** （ `:not()` ）|0|

⭐优先级比较:`!important` >行间样式> `id` 选择器 > `class` 选择器 和 属性选择器 和 伪类选择器>标签选择器 和 伪元素选择器>通配符选择器 和关系选择器 和 否定伪类*(在 `:not()` 有了内部声明的选择器会影响优先级)*

给元素添加的**内联样式** (例如，`style="font-weight:bold"` ) 总会覆盖外部样式表的任何样式，因此可看作是具有最高的优先级。

**`!important` 特殊规则**
当在一个样式声明中使用一个 !important 规则时，此声明将覆盖任何其他声明。

> 。当两条相互冲突的带有 `!important` 规则的声明被应用到相同的元素上时，拥有更大优先级的声明将会被采用。

案例:**直接添加样式 vs. 继承样式**

为目标元素直接添加样式，永远比继承样式的优先级高，无视优先级的遗传规则。

```
#parent {
  color: green;
}

h1 {
  color: purple;
}
```

Copy to Clipboard

当它应用在下面的 HTML 时：

```
<html>
  <body id="parent">
    <h1>Here is a title!</h1>
  </body>
</html>
```

Copy to Clipboard

浏览器会将它渲染成：

<iframe class="sample-code-frame" title="直接添加样式 vs. 继承样式 sample" id="frame_直接添加样式_vs._继承样式" src="https://yari-demos.prod.mdn.mozit.cloud/zh-CN/docs/Web/CSS/Specificity/_sample_.%E7%9B%B4%E6%8E%A5%E6%B7%BB%E5%8A%A0%E6%A0%B7%E5%BC%8F_vs._%E7%BB%A7%E6%89%BF%E6%A0%B7%E5%BC%8F.html" loading="lazy" style="box-sizing: content-box; border: 1px solid var(--border-primary); max-width: 100%; width: calc((100% - 2rem) - 2px); background: rgb(255, 255, 255); border-radius: var(--elem-radius); padding: 1rem;"></iframe>

因为 `h1` 选择器明确的定位到了元素，但绿色选择器的仅仅继承自其父级。

**一张图更好的理解css 选择器优先级**

![css权重解释图](E:\文档\Web学习\笔记\CSS笔记\imgs\css 选择器权重.png)
