## console

### [console.log](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/log)

应用:向 `Web` 控制台输出一条信息。这条信息可能是单个字符串（包括可选的替代字符串），也可能是一个或多个对象。

## window

### [window. alert(message)](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/alert)

应用:显示一个警告对话框，上面显示有指定的文本内容以及一个"确定"按钮。

​		 显示具有给定消息的模式警报，并等待用户解除该警报。

**语法:**

```javascript
window.alert(message);
```

- `message` 是要显示在对话框中的文本字符串，如果传入其他类型的值，会转换成**字符串**。

> 警告对话框使用在无需用户确认的情况下，否则应该使用其他类型的对话框，比如[confirm](https://developer.mozilla.org/zh-CN/docs/DOM/window.confirm), [prompt](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/prompt).

### [result = window. confirm(message)](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/confirm)

应用:显示具有给定消息的模式“确定/取消”提示，等待用户关闭它，如果用户单击“确定”，则返回 `true` ;如果用户单击“取消”，则返回 `false` 。

**语法:**

```javascript
result = window.confirm(message);
```

- `message` 是要在对话框中显示的可选**字符串**。
- `result` 是一个布尔值，指示是选择了“确定”（true）还是“取消”（false）。如果浏览器忽略页内对话框，则返回值始终为 `false` 。

## [result = window. prompt(message [, default])](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/prompt)

应用:显示具有指定消息的胁迫回应文字控件提示，等候使用者解除提示，然后传回使用者输入的值。如果使用者取消提示，则会改为传回 `null` 。如果存在第二个参数，则使用给定值作为默认值。

**语法:**

```javascript
result = window.prompt(message);
result = window.prompt(message, defaultValue);
var sign = window.prompt('你觉得很幸运吗？','是的'); // 打开显示提示文本为"你觉得很幸运吗？"并且输入框默认值为"是的"的提示窗口
```

- `message` 要显示给使用者的文字字串。如果提示窗口中没有要显示的内容，则可以省略。 
- `defaultValue` 文本输入框中的默认值，该参数也可以省略不写。不过在 Internet Explorer 7 和 8 中，省略该参数会导致输入框中显示默认值"undefined"。
- `result` 用来存储用户输入文字的字符串，或者是 `null` 。
