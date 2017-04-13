# JavaScript 编码规范

## 缩进

* 使用 `4` 个空格做为一个缩进层级，不允许使用 `2` 个空格 或 `tab` 字符

* `switch` 下的 `case` 和 `default` 必须增加一个缩进层级

```javascript
switch (variable) {
    case 1:
        break;
    default:
        break;
}
```

* 对象以缩进的形式书写，不要写在一行

```javascript
// better
let obj = {
    a: 1,
    b: 2
}

// bad
let obj = { a: 1, b: 2 }
```

## 分号

任何语句结尾都需要加分号 `;`

```javascript
do {
    x++;
} while (x < 10);
```

## 空格

* 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格

* 用作代码块起始的左花括号 `{` 前必须有一个空格

* `if / else / for / while / function / switch / do / try / catch / finally` 等关键字后，必须有一个空格

* 在非三目运算符中，`:` 之后必须有空格，之前不允许有空格

* `,` 和 `;` 之前不允许有空格，之后必须有空格

* 函数名和 `(` 之间不允许有空格

* 单行注释 `//` 后需要空格（若单行注释和代码同行，则 `//` 前也需要）

* 行尾不得有多余的空格

```javascript
let len = !arr.length;
if (len) {
    Demo(1, 2);
}

// 函数
function Demo(a, b) {
    let obj = { // 对象
        a: 1
    }
}
```

## 空行

* 代码块注释前与代码块后保留一个空行

```javascript
let a = 1;

// 注释
if (a == 2) {
    return;
}

a = 2;
```

## 换行

* 每个语句必须另起一行

* 变量赋值后需要换行

* 左大括号 `{` 后需要换行，右大括号 `}` 前需要换行

```javascript
let a, b,
    c = true;
if (c) {
    return;
}
```

## 注释

* 单行注释使用 `//`，多行注释使用 `/* */`

* 缩进与下一行代码保持一致

* 文档 / 接口注释使用以下写法

```javascript
/**
 * 文档描述
 * @author 作者
 * @date 创建时间
 * @update 更新者 更新时间
 */

/**
 * 接口描述
 * @param {String} title - 弹窗标题内容
 * @param {String} cancelBtnText = '默认值' - 取消按钮文本
 * @param {object} obj - 参数 obj 为一个对象
 * @param {String} obj.str - 参数 obj 的 str 属性
 */
function (title, cancelBtnText, obj) {
}
 ```

## 引号

最外层统一使用单引号 `''`

```javascript
let str = '<div id="test"></div>';
```

## 命名

* 标准变量使用驼峰命名

```javascript
let strObj = '{a: 1}';
```

* 常量全大写，用下划线连接

```javascript
const MAX_COUNT = 10;
```

* 类 / 构造函数每个单词首字母大写

```javascript
function TextNode(options) {
}
```

* jquery 对象必须以 `$` 开头命名

```javascript
let $body = $('body');
```

## 变量声明

* 变量在使用前必须通过 `var / let / const` 定义

* 不要使用未声明的变量，也不要先使用后声明

```javascript
let name = 'MyName';
```

## 对象

对象属性名不需要加引号，有特殊字符除外

```javascript
let obj = {
    name: 'test',
    age: 20,
    'max-weight': 60
};
```

## 大括号

`if / else / for / while / do / switch / try / catch` 等关键字后必须有大括号（即使代码块的内容只有一行）

```javascript
if (true) {
    return;
}
```

## undefined

* 永远不要直接使用undefined进行变量判断

* 使用 typeof 和字符串 `'undefined'` 对变量进行判断

```javascript
// good
if (typeof person === 'undefined') {
    return;
}

// bad
if (person === undefined) {
    return;
}
```

## 其他

* 用 `===`, `!==` 代替 `==`, `!=`

* debugger 不要出现在生产环境的代码里

* 不要在循环内部声明函数

* 不允许有空的代码块