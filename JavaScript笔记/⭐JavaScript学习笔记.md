# JavaScript 学习笔记

## 什么是 `JavaScript`

`JavaScript` 是一种脚本语言，可以用来创建动态更新的内容，控制多媒体，制作图像动画等.

`JavaScript` 是轻量级解释型语言。浏览器接受到 `JavaScript` 代码，并以代码自身的文本格式运行它。技术上，几乎所有 `JavaScript` 转换器都运用了一种叫做即时编译（just-in-time compiling）的技术；当 `JavaScript` 源代码被执行时，它会被编译成二进制的格式，使代码运行速度更快。

> 解释代码 vs 编译代码

## 引入及 `javascript` 的方式

**内部 `javascript` 引入**

- 在 `</head>` 标签结束前插入 `<script>`

**外部 `javascript` 引入**

- 设置 `<script>` 标签中的 `src=""` 引入

- `<script src="script.js" async></script>`

**⚠警告:请不要使用内联 `JavaScript`  这将使 JavaScript 污染到 HTML，而且效率低下。**

若 JavaScript 加载于欲操作的 HTML 元素之前，则代码将出错。**外部引入**中使用了 `JavaScript` 的一项现代技术（`async` “异步”属性）来解决这一问题，它告知浏览器在遇到 `<script>` 元素时不要中断后续 `HTML` 内容的加载。这样 `JavaScript` 脚本和 HTML 将一并加载，代码将顺利运行

> **备注：** “外部引入”示例中 `async` 属性可以解决调用顺序问题，因此无需使用 `DOMContentLoaded` 事件。而 `async` 只能用于外部脚本，因此不适用于“内部引入”示例。

### `async` 属性

**脚本阻塞问题实际有两种解决方案 —— `async` 和 `defer`。**

浏览器遇到 `async` 脚本时不会阻塞页面渲染，而是直接下载然后运行。这样脚本的运行次序就无法控制，只是脚本不会阻止剩余页面的显示。当页面的脚本之间彼此独立，且不依赖于本页面的其它任何脚本时，`async` 是最理想的选择。

###  `defer` 属性

比如，如果你的页面要加载以下三个脚本：

```
<script async src="js/vendor/jquery.js"></script>

<script async src="js/script2.js"></script>

<script async src="js/script3.js"></script>
```

三者的调用顺序是不确定的。`jquery.js` 可能在 `script2` 和 `script3` 之前或之后调用，如果这样，后两个脚本中依赖 `jquery` 的函数将产生错误，因为脚本运行时 `jquery` 尚未加载。

解决这一问题可使用 `defer` 属性，脚本将按照在页面中出现的顺序加载和运行：

```
<script defer src="js/vendor/jquery.js"></script>

<script defer src="js/script2.js"></script>

<script defer src="js/script3.js"></script>
```

添加 `defer` 属性的脚本将按照在页面中出现的顺序加载，因此第二个示例可确保 `jquery.js` 必定加载于 `script2.js` 和 `script3.js` 之前，同时 `script2.js` 必定加载于 `script3.js` 之前。

**脚本调用策略小结：**

- **如果脚本无需等待页面解析，且无依赖独立运行，那么应使用 `async`。**
- **如果脚本需要等待页面解析，且依赖于其它脚本，调用这些脚本时应使用 `defer`，将关联的脚本按所需顺序置于 HTML 中。**

## `JavaScript` 注释

在双斜杠后添加**单行注释**，比如：

```
// 我是一条注释
```

在 `/*` 和 `*/` 之间添加**多行注释**，比如：

```
/*
  我也是
  一条注释
*/

```

## [查找并解决 JavaScript 代码的错误](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/What_went_wrong)

**错误类型**

一般来说，代码错误主要分为两种：

- **语法错误**：代码中存在拼写错误，将导致程序完全或部分不能运行，通常你会收到一些出错信息。只要熟悉语言并了解出错信息的含义，你就能够顺利修复它们。**(无法容忍)**
- **逻辑错误**：有些代码语法虽正确，但执行结果和预期相悖，这里便存在着逻辑错误。这意味着程序虽能运行，但会给出错误的结果。由于一般你不会收到来自这些错误的提示，它们通常比语法错误更难修复。

## 什么是变量

一个变量，就是一个用于存放数值的容器。

变量的另一个特性就是它们能够存储任何的东西 -- 不只是字符串和数字。变量可以存储更复杂的数据，甚至是函数。

## 数据类型

### 不可改变的原始值

#### Number

经过封装的能让你处理数字值的对象。`Number` 对象由 `Number()` 构造器创建。

| Number                                                       | 值         |
| ------------------------------------------------------------ | ---------- |
| 整数 `123`                                                   | `123`      |
| 浮点数 `0.456`                                               | `0.456`    |
| 科学计数法表示 `1.2345x1000` ，等同于`1234.5`                | `1.2345e3` |
| 负数                                                         | `-99`      |
| ` NaN` 表示 `Not a Number` ，当无法计算结果时用 `NaN` 表示   | `NaN`      |
| ` Infinity` 表示无限大，当数值超过了 `JavaScript` 的 `Number` 所能表示的最大值时，就表示为 `Infinity` | `Infinity` |

#### String(字符串)

经过封装的能让你处理数字值的对象。`Number` 对象由 `Number()` 构造器创建。

字符串是以单引号'或双引号"括起来的任意文本，比如`'abc'`，`"xyz"`等等。请注意，`''`或`""`本身只是一种表示方式，不是字符串的一部分，因此，字符串`'abc'`只有`a`，`b`，`c`这3个字符。

>  字符串和数字连接时，浏览器很将**数字转换为字符串**，并将这两个字符串连接在一起

**长字符串的表示方法：**

1. 可以使用 + 运算符将多个字符串连接起来，如下所示：

   ```javascript
   let longString = "This is a very long string which needs " +
                    "to wrap across multiple lines because " +
                    "otherwise my code is unreadable.";
   ```

2. 可以在每行末尾使用反斜杠字符（“\”），以指示字符串将在下一行继续。确保反斜杠后面没有空格或任何除换行符之外的字符或缩进; 否则反斜杠将不会工作。如下所示：

   ```javascript
   let longString = "This is a very long string which needs \
   to wrap across multiple lines because \
   otherwise my code is unreadable.";
   ```

3. 由于多行字符串用`\n`写起来比较费事，所以最新的 `ES6` 标准新增了一种多行字符串的表示方法，用反引号 \`...\`表示：

   ```javascript
   `这是一个
   多行
   字符串`;
   ```

   *注意*：反引号在键盘的ESC下方，数字键1的左边：

   ```ascii
   ┌─────┐ ┌─────┬─────┬─────┬─────┐
   │ ESC │ │ F1  │ F2  │ F3  │ F4  │
   │     │ │     │     │     │     │
   └─────┘ └─────┴─────┴─────┴─────┘
   ┌─────┬─────┬─────┬─────┬─────┐
   │  ~  │  !  │  @  │  #  │  $  │
   │  `  │  1  │  2  │  3  │  4  │
   ├─────┴──┬──┴──┬──┴──┬──┴──┬──┘
   │        │     │     │     │
   │  tab   │  Q  │  W  │  E  │
   ├────────┴──┬──┴──┬──┴──┬──┘
   │           │     │     │
   │ caps lock │  A  │  S  │
   └───────────┴─────┴─────┘
   ```

##### 模板字符串

要把多个字符串连接起来，可以用`+`号连接：

```javascript
var name = '小明';
var age = 20;
var message = '你好, ' + name + ', 你今年' + age + '岁了!';
alert(message);
```

如果有很多变量需要连接，用`+`号就比较麻烦。`ES6` 新增了一种模板字符串，表示方法和上面的多行字符串一样，但是它会自动替换字符串中的变量：

```javascript
var name = '小明';
var age = 20;
var message = `你好, ${name}, 你今年${age}岁了!`;
alert(message);
```

##### 操作字符串

字符串常见的操作如下：

```
var s = 'Hello, world!';
s.length; // 13
```

要获取字符串某个指定位置的字符，使用类似Array的下标操作，索引号从0开始：

```
var s = 'Hello, world!';

s[0]; // 'H'
s[6]; // ' '
s[7]; // 'w'
s[12]; // '!'
s[13]; // undefined 超出范围的索引不会报错，但一律返回undefined
```

*需要特别注意的是*，字符串是不可变的，如果对字符串的某个索引赋值，不会有任何错误，但是，也没有任何效果：

```
var s = 'Test';
s[0] = 'X';
alert(s); // s仍然为'Test'
```

JavaScript为字符串提供了一些常用方法，注意，调用这些方法本身不会改变原有字符串的内容，而是返回一个新字符串：

###### toUpperCase

`toUpperCase()`把一个字符串全部变为**大写**：

```
var s = 'Hello';
s.toUpperCase(); // 返回'HELLO'
```

###### toLowerCase

`toLowerCase()`把一个字符串全部变为**小写**：

```
var s = 'Hello';
var lower = s.toLowerCase(); // 返回'hello'并赋值给变量lower
lower; // 'hello'
```

###### index Of

`indexOf()`会搜索指定字符串出现的位置：

```
var s = 'hello, world';
s.indexOf('world'); // 返回7
s.indexOf('World'); // 没有找到指定的子串，返回-1
```

###### substring

`substring()`返回指定索引区间的子串：

```
var s = 'hello, world'
s.substring(0, 5); // 从索引0开始到5（不包括5），返回'hello'
s.substring(7); // 从索引7开始到结束，返回'world'
```

#### Boolean(布尔值)

布尔值和布尔代数的表示完全一致，一个布尔值只有`true`、`false`两种值，要么是`true`，要么是`false`，可以直接用`true`、`false`表示布尔值，也可以通过布尔运算计算出来

#### null(空值)

特指对象的值未设置(表示一个“空”的值)。它和`0`以及空字符串`''`不同，`0`是一个数值，`''`表示长度为0的字符串，而`null`表示“空”。

它是 `JavaScript` 基本类型 之一，在布尔运算中被认为是 `falsy` 。

值 `null` 是一个字面量，不像 `undefined`，它不是全局对象的一个属性。`null` 是表示缺少的标识，指示变量未指向任何对象。把 `null` 作为尚未创建的对象，也许更好理解。在 `API` 中，`null` 常在返回类型应是一个对象，但没有关联的值的地方使用。

#### undefined(未定义)

表示值未定义。事实证明，这并没有什么卵用，区分两者的意义不大。大多数情况下，我们都应该用`null`。`undefined`仅仅在判断函数参数是否传递的情况下有用

一个没有被赋值的变量的类型是 undefined。如果方法或者是语句中**操作的变量没有被赋值，则会返回 undefined**

### 引用值

#### Array(数组)

支持在单个变量名下存储多个元素，并具有执行常见数组操作的成员。

**数组用`[]`表示，元素之间用`,`分隔;出于代码的可读性考虑，强烈建议直接使用`[]`。**

**数组的索引**从 0 开始：数组的第一个元素在索引 0 处，第二个在索引 1 处，以此类推，最后一个元素是数组的 `length` 属性减去 1 的值。

数组的元素可以通过索引来访问。请注意，索引的起始值为`0`：

```javascript
var arr = [1, 2, 3.14, 'Hello', null, true];
arr[0]; // 返回索引为0的元素，即1
arr[5]; // 返回索引为5的元素，即true
arr[6]; // 索引超出了范围，返回undefined
```

**`length`** 是 `Array` 的实例属性。返回或设置一个数组中的元素个数。

要取得`Array`的长度，直接访问`length`属性：

```
var arr = [1, 2, 3.14, 'Hello', null, true];
arr.length; // 6
```

*请注意*，直接给`Array`的`length`赋一个新的值会导致`Array`大小的变化：

```
var arr = [1, 2, 3];
arr.length; // 3
arr.length = 6;
arr; // arr变为[1, 2, 3, undefined, undefined, undefined]
arr.length = 2;
arr; // arr变为[1, 2]
```

`Array`可以通过索引把对应的元素修改为新的值，因此，对`Array`的索引进行赋值会直接修改这个`Array`：

```
var arr = ['A', 'B', 'C'];
arr[1] = 99;
arr; // arr现在变为['A', 99, 'C']
```

*请注意*，如果通过索引赋值时，索引超过了范围，同样会引起`Array`大小的变化：

```
var arr = [1, 2, 3];
arr[5] = 'x';
arr; // arr变为[1, 2, 3, undefined, undefined, 'x']
```

大多数其他编程语言不允许直接改变数组的大小，越界访问索引会报错。然而，JavaScript的`Array`却不会有任何错误。在编写代码时，不建议直接修改`Array`的大小，访问索引时要确保索引不会越界。

[未学完](https://www.liaoxuefeng.com/wiki/1022910821149312/1023020967732032)



#### Object(对象)

它用于存储各种**键**-**值**集合和更复杂的实体。`Objects` 可以通过 `Object()` 构造函数或者使用 对象字面量 的方式创建

[未学完](https://www.liaoxuefeng.com/wiki/1022910821149312/1023020997017056)



## 逻辑运算符

用于测定变量或值之间的逻辑

- `&&` — 逻辑与; 使得并列两个或者更多的表达式成为可能，只有当这些表达式**每一个**都返回`true`时，整个表达式才会返回`true.`
- `||` — 逻辑或; 当两个或者更多表达式当中的**任何一个**返回 `true` 则整个表达式将会返回 `true`.
- `!` — 逻辑非; 对一个布尔值取反，非 `true` 返回 `false` ，非 `false` 返回 `true` .

给定 **x=6 以及 y=3**，下表解释了逻辑运算符：

| 运算符 | 描述 | 例子                        | 口诀                                                       |
| :----- | :--- | :-------------------------- | ---------------------------------------------------------- |
| &&     | and  | (x < 10 && y > 1) 为 true   | 只有所有都为`true`，`&&`运算结果才是`true`                 |
| \|\|   | or   | (x\==5 \|\| y\==5) 为 false | 只要其中有一个为`true`，`||`运算结果就是`true`             |
| !      | not  | !(x==y) 为 true             | 它是一个单目运算符，把`true`变成`false`，`false`变成`true` |

### 短路求值

作为逻辑表达式进行求值是从左到右，它们是为可能的“短路”的出现而使用以下规则进行测试：

- `false` && *anything* 		// 被短路求值为 `false`

> 1. 先看第一个表达式转化成布尔值是否为 `  true` ,如果为真,那么它会看第二个表达式转换为布尔值的结果,然后如果只有两个表达式的话,只看到第二个表达式,就可以返回改表达式的值了
>
>    ⭐ `undefined` , `null` , `NaN` , `""(没有内容的字符串)` , `0` , `false` ==>**false**
>
> 2. 当第一个表达式转化成布尔值的结果为 ` false ` 时,返回第一个表达式的值

- `true` || *anything* 		// 被短路求值为 `true`

> 1. 先看第一个表达式转换成布尔值是否为 `  true`,如果是真,那么它会返回第一个表达式的转换为布尔值的结果
> 2. 当第一个表达式转化成布尔值的结果为 ` false ` 时,那么它会看第二个表达式转换为布尔值的结果,然后如果只有两个表达式的话,只看到第二个表达式,就可以返回改表达式的值了

逻辑的规则，保证这些评估是总是正确的。请注意，上述表达式的`anything`部分不会被求值，所以这样做不会产生任何副作用。

## 比较运算符

比较它的操作数并返回一个基于表达式是否为真的逻辑值

| 运算符 | 名称       | 作用                           | 示例          |
| :----- | :--------- | :----------------------------- | :------------ |
| `===`  | 严格等于   | 测试左右值是否相同             | `5 === 2 + 4` |
| `!==`  | 严格不等于 | 测试左右值是否**不**相同       | `5 !== 2 + 3` |
| `<`    | 小于       | 测试左值是否小于右值。         | `10 < 6`      |
| `>`    | 大于       | 测试左值是否大于右值           | `10 > 20`     |
| 〈=    | 小于或等于 | 测试左值是否小于或等于右值。   | `3 <= 2`      |
| 〉=    | 大于或等于 | 测试左值是否大于或等于正确值。 | `5 >= 4`      |

> ` = =` 默认转换数据类型;会把字符数据类型的转换为数字类型 
>
> 要特别注意相等运算符`==`。JavaScript在设计时，有两种比较运算符：
>
> 第一种是`==`比较，它会自动转换数据类型再比较，很多时候，会得到非常诡异的结果；
>
> 第二种是`===`比较，它不会自动转换数据类型，如果数据类型不一致，返回`false`，如果一致，再比较。
>
> 由于JavaScript这个设计缺陷，*不要*使用`==`比较，始终坚持使用`===`比较。
>
> 另一个例外是`NaN`这个特殊的Number与所有其他值都不相等，包括它自己：
>
> ```
> NaN === NaN; // false
> ```
>
> 唯一能判断`NaN`的方法是通过`isNaN()`函数：
>
> ```
> isNaN(NaN); // true
> ```
>
> 最后要注意浮点数的相等比较：
>
> ```
> 1 / 3 === (1 - 2 / 3); // false
> ```
>
> 这不是JavaScript的设计缺陷。浮点数在运算过程中会产生误差，因为计算机无法精确表示无限循环小数。要比较两个浮点数是否相等，只能计算它们之差的绝对值，看是否小于某个阈值：
>
> ```
> Math.abs(1 / 3 - (1 - 2 / 3)) < 0.0000001; // true
> ```

## [算术运算符](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/Math#算术运算符)

算术运算符是我们用来做和的基本运算符：

| 运算符 | 名称                  | 作用                                                         | 示例                                                |
| :----- | :-------------------- | :----------------------------------------------------------- | :-------------------------------------------------- |
| `+`    | 加法                  | 两个数相加。                                                 | `6 + 9`                                             |
| `-`    | 减法                  | 从左边减去右边的数。                                         | `20 - 15`                                           |
| `*`    | 乘法                  | 两个数相乘。                                                 | `3 * 7`                                             |
| `/`    | 除法                  | 将左边的数字除以右边的。                                     | `10 / 5`                                            |
| `%`    | 求余 (有时候也叫取模) | 将左边的数字除以等于右边数字的整数部分后的余数。             | `8 % 3` (返回 2，8 除以 3 的倍数，余下 2。)         |
| `**`   | 幂                    | 将底数自乘到指数幂，即底数乘以其自身的指数倍。它在 EcmaScript 2016 中首次引入。 | `5 ** 5` (返回 3125，相当于 `5 * 5 * 5 * 5 * 5` 。) |

## [赋值运算符](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/Math#赋值运算符)

赋值运算符是向变量分配值的运算符。我们已经使用了最基本的一个很多次了：`=`，它只是将右边的值赋给左边的变量

| 运算符 | 名称     | 作用                                           | 示例              | 等价于               |
| :----- | :------- | :--------------------------------------------- | :---------------- | :------------------- |
| `+=`   | 加法赋值 | 右边的数值加上左边的变量，然后再返回新的变量。 | `x = 3; x += 4;`  | `x = 3; x = x + 4;`  |
| `-=`   | 减法赋值 | 左边的变量减去右边的数值，然后再返回新的变量。 | `x = 6; x -= 3;`  | `x = 6; x = x - 3;`  |
| `*=`   | 乘法赋值 | 左边的变量乘以右边的数值，然后再返回新的变量。 | `x = 2; x *= 3;`  | `x = 2; x = x * 3;`  |
| `/=`   | 除法赋值 | 左边的变量除以右边的数值，然后再返回新的变量。 | `x = 10; x /= 5;` | `x = 10; x = x / 5;` |

## [自增和自减运算符](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/Math#自增和自减运算符)

### 自增

如使用后缀式，操作符在操作数后（例如 `x++`），操作数会加一，然后返回加一之前的值。(先返回原值,后自加)

如使用前缀式，操作符在操作数前（例如 `++x`），操作数会加一，然后返回加一之后的值。

```javascript
let x = 3;
const y = x++;

console.log(`x:${x}, y:${y}`);
// expected output: "x:4, y:3"

let a = 3;
const b = ++a;

console.log(`a:${a}, b:${b}`);
// expected output: "a:4, b:4"
```



### 自减

如果使用后缀式，即将操作符放在操作数的后面 (如，`x--`)，运算会减一，然后返回减一之前的值。(先返回原值,后自加)

如果使用前缀式，即将操作符放在操作数的前面 (如，`--x`)，运算会减一，然后返回减一之后的值。

```javascript
let x = 3;
const y = x--;

console.log(`x:${x}, y:${y}`);
// expected output: "x:2, y:3"

let a = 3;
const b = --a;

console.log(`a:${a}, b:${b}`);
// expected output: "a:2, b:2"
```

## [运算符优先级](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

**运算子优先级**

在计算某个计算的结果时（称为*表达方式* `JavaScript` 中的运算符优先级和学校数学课上教的一样--先算乘法和除法，然后是加法和减法（计算总是从左到右进行）。

## [var 语句](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/var#var_hoisting)

应用:用于声明一个函数范围或全局范围的变量，并可将其初始化为一个值（可选）。

## [let 语句](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let)

应用:用于声明一个块级作用域的局部变量，并可以初始化为一个值（可选）。

⭐**从 `ECMAScript` 2015 开始，使用 `let` 和`const`变量是块作用域的。更多信息请参考 [`let`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let) 和 [`const`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const)。**

## 使用了一个名为`typeof`的特殊的操作符 ——它会返回所传递给它的变量的数据类型。

## [String .length 属性](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/length)

应用:返回字符串中字符编码单元的数量。

空字符串的 `length` 为 0。

静态属性 `String .length` 返回 1。

> `JavaScript` 使用 `UTF-16` 编码，该编码使用一个 16 比特的编码单元来表示大部分常见的字符，使用两个代码单元表示不常用的字符。因此 `length` 返回值可能与字符串中实际的字符数量不相同。

## 条件语句

**⭐`JavaScript` 把`null`、`undefined`、`0`、`NaN`和空字符串`''`视为`false`，其他值一概视为`true`，因此上述代码条件判断的结果是`true`。**

### if 语句

**语法:**

1. 关键字 if，并且后面跟随括号。
2. 要测试的条件，放到括号里（通常是“这个值大于另一个值吗”或者“这个值存在吗”）。这个条件会利用**比较运算符**进行比较，并且返回 true 或者 false。
3. 一组花括号，在里面我们有一些代码——可以是任何我们喜欢的代码，并且只会在条件语句返回 true 的时候运行。
4. 关键字 else。
5. 另一组花括号，在里面我们有一些代码——可以是任何我们喜欢的代码，并且当条件语句返回值不是 true 的话，它才会运行。

这段代码真的非常易懂——它说“**如果（if）条件（condition）**返回 true，运行代码 A，**否则（else）**运行代码 B”

>  你不一定需要 else 和第二个花括号

---

只有当指定条件为 `true` 时，使用该语句来执行代码

```javascript
if (条件)
{
  当条件为 true 时执行的代码块
}
```

### if...else 语句

当条件为 `true` 时执行代码，当条件为 `false` 时执行 `else` 中的代码

```javascript
if (条件)
{
    当条件为 true 时执行的代码块
}
else
{
    条件为 false 时执行的代码块
}
```

### if...else if...else 语句

选择多个代码块之一来执行,**如果某个条件成立，则后续就不再继续判断了**。

```javascript
if (条件 1)
{
    条件 1 为 true 时执行的代码块
}
else if (条件 2) 
{
    条件 1 为 false 而条件 2 为 true 时执行的代码块
 } 
else 
{
    条件 1 和条件 2 同时为 false 时执行的代码块
}
```

### switch 语句

应用：评估一个表达式，将表达式的值与 `case` 子句匹配，并执行与该情况相关联的语句

**语法:**

```javascript
switch(expression) {
    case n:
        代码块
        break;
    case n:
        代码块
        break;
    default:
        默认代码块
}
```



**default** 关键字 来规定匹配不存在时做的事情。 default 关键字在 switch 语句中只能出现一次。虽然是可选参数，但是建议都使用该参数，在不是我们期望的情况下，可以使用它输出信息。

> 如果忘记添加 `break` ，那么代码将会从值所匹配的 `case` 语句开始运行，然后持续执行下一个 `case` 语句而不论值是否匹配。

###  [break 语句](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/break)

应用:中止当前循环，`switch` 语句或 `label` 语句，并把程序控制流转到紧接着被中止语句后面的语句。

Swift break语句会立刻结束整个控制流的执行。

如果您使用的是嵌套循环（即一个循环内嵌套另一个循环），break 语句会停止执行最内层的循环，然后开始执行该块之后的下一行代码。

> `break`语句需要**内嵌**在引用的标签中。
>
> break 语句不能在 function 函数体中直接使用，break 语句应嵌套在要中断的当前循环、switch 或 label 语句中。

### for 循环

**语法:**

1. 关键字`for`，后跟一些括号。
2. 在括号内，我们有三个项目，以分号分隔：
   1. 一个**初始化器** - 这通常是一个设置为一个数字的变量，它被递增来计算循环运行的次数。它也有时被称为**计数变量**。
   2. 一个**退出条件** - 如前面提到的，这个定义循环何时停止循环。这通常是一个表现为比较运算符的表达式，用于查看退出条件是否已满足的测试。
   3. 一个**递增条件** - 这总是被判断（或运行），每个循环已经通过一个完整的迭代消失时间。它通常用于增加（或在某些情况下递减）计数器变量，使其更接近退出条件值。
3. 一些包含代码块的花括号 - 每次循环迭代时都会运行这个代码。

```javascript
for ( 初始化器; 退出条件; 递增条件)
{
    被执行的代码块
}
```

### while 循环

`while` 循环与 `for` 循环结构相似除了在循环之前设置初始化器变量，并且在运行代码之后，循环中包含 final-expression，而不是这两个项目被包含在括号中，这与以前的 for 循环非常类似。退出条件包含在括号内，前面是 while 关键字而不是 `for`。

只要指定条件为 `true` ，循环就可以一直执行代码块

**语法:**

```javascript
while (条件)
{
  需要执行的代码
}
```

### do···while 循环

do/while 循环是 while 循环的变体。该循环会在检查条件是否为真之前执行一次代码块，然后如果条件为真的话，就会重复这个循环。

**语法:**

```javascript
do
{
  需要执行的代码
}
while (条件);
```



## [continue 声明](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/continue)

应用:终止当前循环或标记循环的当前迭代中的语句执行，并在下一次迭代时继续执行循环。

**continue与 break 语句的区别**

`continue` 并不会终止循环的迭代，而是：

在 `while` 循环中，控制流跳回到**条件判断**；

在 `for` 循环中，控制流跳转到**更新表达式**。

 `continue` 语句可以包含一个可选的标号以控制程序跳转到指定循环的下一次迭代，而非当前循环。此时要求 `continue` 语句在对应的循环内部。

## Math.sqrt()

应用:函数返回一个数的平方根

## [typeof 运算符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/typeof)

应用:返回一个字符串，表示操作数的类型。

**6种数据类型:`number`、`string`、`boolean`、`undefined`、 `object` 和`function`**

- `typeof` 操作符的[优先级](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)高于加法（`+`）等二进制操作符。因此，需要用括号来计算加法结果的类型。

**与未声明和未初始化的变量交互**
`typeof` 通常总是保证为提供给它的任何操作数返回一个字符串。即使使用未声明的标识符，`typeof` 也将返回“undefined”，而不是引发错误。

### 显示类型转换

### Number ( value )

### Number() constructor

应用:创建一个 `Number` 对象

- 如果参数无法被转换为数字，则返回 [`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)。
- 在非构造器上下文中 (如：没有 [`new`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/new) 操作符)，`Number` 能被用来执行类型转换
- **如果是 `Boolean` 值，`true` 和 `false` 将分别转换为1和0**

### [parseInt(string, radix)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseInt)

应用:解析一个字符串并返回指定基数的十进制整数，`radix` 是 2-36 之间的整数，表示被解析字符串的基数。

此函数根据指定的基数，通过解释字符串参数的内容来生成整数 `Number` 。忽略字符串中的前导和空格。如果 `radix` 为 `undefined` 或 `0` ，则假定为10.

**语法:**

```javascript
parseInt(string, radix);
```

- `string(字符串)` 以整数开头的字符串。忽略此参数中的前导空格。

- `radix 基数(可选)` 2到36之间的整数，表示字串的基数（数学数字系统中的基底）。它被转换为32位整数;如果在转换后它超出了[2，36]的范围，函数将始终返回 `NaN` 。如果为0或未提供，则将根据字符串的值推断基数。请注意-这并不总是默认为10！ 

**返回值:**

1. 从给定的字符串中解析出的一个**整数**(设置了基数时,义目标进制为基数,转换为10进制的数)
2. `NaN`,下面情况出现 `NaN`
   1. `radix` 小于 2 或大于 3
   2. 第一个非空格字符不能转换为数字

- 如果 `parseInt` 遇到的字符不是指定 `radix` 参数中的**数字**，它将忽略该字符以及所有后续字符，并返回到该点为止已解析的整数值。`parseInt` 将数字截断为整数值。|||||允许前导和尾随空格。**?????不理解!**      

- `parseInt` 可以理解两个符号。`+` 表示正数，`-` 表示负数（从 ECMAScript 1 开始）。它是在去掉空格后作为解析的初始步骤进行的。如果没有找到符号，算法将进入下一步；否则，它将删除符号，并对字符串的其余部分进行数字解析。

**`radix` 设置注意事项:**

如果 `radix` 是 `undefined (undefined被强制为NaN)`、`0` 或未指定的**(这里注意! `undefined ` 和`0 (零)` 都默认为10进制)**，JavaScript 会假定以下情况：

1. 如果输入的 `string` 以 `0x` 或 `0X`（一个 0，后面是小写或大写的 X）开头，那么 radix 被假定为 16，字符串的其余部分被当做十六进制数去解析。
2. 如果输入的 `string` 以 "`0`"（0）开头，`radix` 被假定为 `8`（八进制）或 `10`（十进制）。具体选择哪一个 radix 取决于实现。ECMAScript 5 澄清了应该使用 10 (十进制)，但不是所有的浏览器都支持。**因此，在使用 `parseInt` 时，一定要指定一个 radix**。
3. 如果输入的 `string` 以任何其他值开头，`radix` 是 `10` (十进制)。

**如果第一个字符不能转换为数字，`parseInt` 会返回 `NaN`。**

为了算术的目的，`NaN` 值不能作为任何 `radix` 的数字。你可以调用 [`isNaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/isNaN) 函数来确定 `parseInt` 的结果是否为 `NaN`。如果将 `NaN` 传递给算术运算，则运算结果也将是 `NaN`。

要将一个数字转换为特定的 `radix` 中的字符串字段，请使用 `thatNumber.toString(radix)` 函数。

**⭐ `parseInt`在运算非常大的值和非常小的值是会存在问题!!!**

```javascript
parseInt(4.7 * 1e22, 10); // Very large number becomes 4
parseInt(0.00000000000434, 10); // Very small number becomes 4
```

[查看网页的最下面](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)

### [parseFloat ( string )](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)

应用:解析一个参数（必要时先转换为字符串）并返回一个浮点数。

**语法:**

```javascript
parseFloat(string)
```

- `string(字符串)` 要解析为浮点数的值，强制为字符串。忽略此参数中的前导空格。

**返回值:**

从给定字符串分析得出的浮点数;如果第一个非空白字符无法转换为数字，则为 `NaN`

**注意事项:**

- 如果 `parseFloat` 在解析过程中遇到了正号`（+）`、负号`（- U+002D HYPHEN-MINUS）`、数字`（0-9）`、小数点`（.）`、或者科学记数法中的指数`（e 或 E）`以外的字符，则它会忽略该字符以及之后的所有字符，返回当前已经解析到的浮点数。
- 第二个小数点的出现也会使解析停止（在这之前的字符都会被解析）。
- 参数首位和末位的空白符会被忽略。
- 如果参数字符串的第一个字符不能被解析成为数字，则 `parseFloat` 返回`NaN`。

- `parseFloat` 也可以解析并返回 Infinity。

- `parseFloat` 解析 `BigInt` 为 `Numbers` , 丢失精度。因为末位  `n` 字符被丢弃。

考虑使用 `Number(value)` 进行更严谨的解析，只要参数带有无效字符就会被转换为 `NaN` 。

### string(value)

### [toString()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toString)

应用:            XXX.toString(),相当于将XXX转换为字符串

`toString(radix)`

- `radix` 是基数,让XXX转化为 `radix` 进制的数

**注意：** `undefined` 和 `null` 在使用时会报错

### Boolean ( value )

## 隐式类型转换

### [ isNaN ( number )==>内部调用Number(value)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/isNaN)

应用:用来确定一个值是否为 `NaN` 。

**语法:**

```javascript
isNaN(value)
```

**返回值:**

如果给定值为 `NaN` 则返回值为 `true` ；否则为 `false` 。

**⭐先把里面的值放入 `Number ( value )` 中判断是否为 `NaN` ,如果是输出 `true` 否则返回 `false`**





`undefined` == `null`

` NaN` != `NaN` 

当一个变量未定义就使用时，只有放在 `typeof()` 内不会报错,并且会打印出值
