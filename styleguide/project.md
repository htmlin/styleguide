# 项目规范

## 项目目录规范

```
.
├─ css
├─ component
├─ img
├─ js
├─ page
├─ test
├─ package.json
├─ README.md
```

### css

存放样式类文件，且所有 CSS 文件编写应当遵循 [CSS 编码规范](./css.md)

### component

存放项目组件

### img

存放项目的图片资源，应当按模块分文件夹存放

### js

存放项目的 JS 源代码，且所有 JS 文件编写应当遵循 [JavaScript 编码规范](./javascript.md)

### page

存放项目的 HTML 页面代码文件，且所有 HTML 文件编写应当遵循 [HTML 编码规范](./html.md)

备注：单页应用可以例外

### test

所有测试相关文件应当放在此目录

### package.json

每个项目都必须包含一个 `package.json` 文件，在使用 `npm init` 新建项目时自动生成，此文件中应当包含项目的基本信息、项目的依赖以及项目的相关执行命令等

### README.md

每个项目都必须包含一个 `README.md` 文件，此文件中应当描述此项目的功能、特点、API 等信息

## 项目命名规范

* 文件及目录命名全部采用小写方式， 以下划线分隔

* 目录有复数结构时，始终采用单数命名法

```
my_project_name/img/user_order.png
```