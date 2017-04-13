# CSS 编码规范

## 页面布局

页面布局均采用最新版 `flexbox` 进行布局，需兼容低版本 IE 项目除外。

```css
.selector {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

## 缩进

使用 `4` 个空格作为一个缩进层级，不允许使用 `2` 个空格或 `tab` 字符。

```css
.selector {
    margin: 0;
    padding: 0;
}
```

## 分号

每个属性声明末尾都要加分号

```css
.selector {
    width: 100%;
    height: 100%;
}
```

## 空格

* `:` 与属性值之间需要空格，与属性名之间不需要空格

* 属性值中的 `,` 后需要空格，`,` 前不需要空格

* 选择器 `> + ~` 等前后需要空格

* 选择器与 `{` 之间需要空格

* `/` 前后需要空格

* 注释 `/*` 后和 `*/` 前需要空格

```css
.selector > .wrapper {
    font-family: "Hiragino Sans GB", sans-serif;
    background: rgba(0, 0, 0, 0.5) url(logo.png) no-repeat center / contain;
    height: 100%;
}
```

## 空行

* 两个选择器属性块之间保留一个空行

* 代码块注释前与代码块后保留一个空行

```css
.wrapper {
    height: 100%;

    /* 字体相关 */
    font-family: 'DINPro';
    font-size: 16px;
    font-weight: 700;

    background: #000;
}

.selector {
    height: 100%;
}
```

## 换行

* 当一个规则包含多个选择器时，每个选择器声明必须独占一行

* 每个属性定义必须另起一行

* `{` 后需要换行，`}` 前需要换行

```css
.wrapper,
.selector {
    width: 100%;
    height: 100%;
}
```

## 注释

* 统一使用 `/* */` 进行注释

* 缩进与下一行代码保持一致

* 可位于一个代码行的末尾，与代码间隔一个空格

```css
.wrapper,
.selector {

    /* 字体相关 */
    font-family: 'DINPro';
    font-size: 16px;
    font-weight: 700; /* 字重 */
}
```

## 引号

* 引号统一使用双引号

* 属性选择器中的属性值需要引号

```css
[class="demo"]::after {
    content: "";
}
```

## 命名

* id 与类名使用小写字母，以中划线 `-` 分隔

```css
.demo-test,
#test-demo {
    width: 100%;
}
```

## 颜色

* 16 进制颜色使用小写字母

* 16 进制颜色尽量使用简写

```css
/* good */
.selector {
    color: #abc;
}

/* bad */
.selector {
    color: #AABBCC;
}
```

## 属性简写

支持简写的属性尽量使用简写

```css
/* better */
.selector {
    background: rgba(0, 0, 0, 0.5) url(logo.png) no-repeat center / contain;
}

/* bad */
.selector {
    background-color: rgba(0, 0, 0, 0.5);
    background-image: url(logo.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
}
```

## 属性声明顺序

1. 影响文档流的属性（比如：`display / position / float / clear / visibility` 等）
2. 自身盒模型的属性（比如：`width / height / margin / padding / border` 等）
3. 排版相关属性（比如：`font / line-height / text-align / vertical-align` 等）
4. 装饰性属性（比如：`color / background / opacity / cursor` 等） 
5. CSS3 新特性（比如：`transform / transition / animation` 等）

## 其他

* 不允许有空的规则

* 元素选择器用小写字母

* 属性值 `0` 后面不要加单位

* 无前缀的标准属性应该写在有前缀的属性后面

* 不要在一个文件里出现两个相同的规则

* 发布的代码中不要有 `@import`

* 尽量不用 `*` 选择器