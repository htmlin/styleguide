# HTML 编码规范

## 语法

* 使用 `4` 个空格做为一个缩进层级，不允许使用 `2` 个空格或 `tab` 字符

* 在属性上，使用双引号 `""`，不要使用单引号 `''`

* 属性名 / 属性值全小写，用中划线 `-` 做分隔符

* 不要在自动闭合标签结尾处使用斜线，例：`<img>`

* 不要忽略可选的关闭标签，例：`</li>` 和 `</body>`

* 自定义属性必须使用 `data-` 前缀

```html
<!-- good -->
<body>
    <img src="logo.png" alt="logo">
    <ul>
        <li class="first-child">first</li>
        <li data-index="2">second</li>
    </ul>
</body>
```

## HTML5 doctype

在页面开头使用这个简单的 doctype 来启用标准模式，使其在每个浏览器中尽可能一致的展现

虽然 doctype 不区分大小写，但是按照惯例，doctype 使用全大写

```html
<!-- good -->
<!DOCTYPE html>
```

## lang 属性

根据HTML5规范：

> 应在 html 标签上加上 lang 属性。这会给语音工具和翻译工具帮助，告诉它们应当怎么去发音和翻译。

在 sitepoint 上可以查到 [语言列表](https://www.sitepoint.com/web-foundations/iso-2-letter-language-codes/)

但 sitepoint 只是给出了语言的大类，例如中文只给出了 zh，但是没有区分香港，台湾，大陆。而微软给出了一份更加详细的 [语言列表](https://msdn.microsoft.com/en-us/library/ms533052(v=vs.85).aspx)，其中细分了 zh-cn, zh-hk, zh-tw

```html
<!DOCTYPE html>
<html lang="zh-cn">
</html>
```

## 字符编码

通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为 "utf-8"

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
    </head>
</html>
```

## IE 兼容模式

用 `<meta>` 标签可以指定页面应该用什么版本的 IE 来渲染，PC 端项目，建议启用 IE Edge 模式

```html
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    </head>
</html>
```

## 引入 CSS、JS

* 根据 HTML5 规范, 通常在引入 CSS 和 JS 时不需要指明 `type`，因为 `text/css` 和 `text/javascript` 分别是他们的默认值

* 在引入 CSS 时，必须指明 `rel="stylesheet"`

* 将 script 放在页面中间将阻断页面的渲染，出于性能方面的考虑，如非必要，JavaScript 应当放在页面末尾

```html
<html>
    <head>
        <link rel="stylesheet" src="index.css">
    </head>
    <body>
        <script src="index.js"></script>
    </body>
</html>
```

## boolean 属性

boolean 属性指不需要声明取值的属性，XHTML 需要每个属性声明取值，但是 HTML5 并不需要

```html
<!-- good -->
<input type="text" disabled>
<input type="checkbox" value="1" checked>

<!-- bad -->
<input type="text" disabled="disabled">
<input type="checkbox" value="1" checked="true">
```

## 减少标签数量

在编写HTML代码时，需要尽量避免多余的父节点

```html
<!-- good -->
<img class="logo" src="logo.png">

<!-- bad -->
<span class="logo">
    <img src="logo.png">
</span>
```

## 实用高于完美

* 尽量遵循 HTML 标准和语义，但是不应该以浪费实用性作为代价

* 任何时候都要用尽量小的复杂度和尽量少的标签来解决问题