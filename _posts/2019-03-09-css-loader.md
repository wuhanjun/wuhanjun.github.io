---
layout:     post
title:      "Welcome to W's Blog"
subtitle:   " \"css-loader\""
date:       2019-03-09 21:06:00
author:     "W"
header-img: "img/about-bg.jpeg"
tags:
    - webpack
---

> “css-loader源码 ”


## 前言

相比较于style-loader、less-loader、file-loader，css-loader要处理`@import`和`url(src)`的语法，所以较为繁琐一些。


<p id = "build"></p>
---

## 正文

---
从拿到的结果看，css-loader将`url('../images/favicon.png')`这个操作解析为了两步。

1.用require语法去解析图片，这样在打包时就生成一个新的模块：'./src/images/favicon.png'，导出的模块内容是图片名称

2.webpack将require语法解析成自定义的__webpack_require__。
```
// 解析前源=代码
body {
  background-color: red;
  background-image: url('../images/favicon.png')
}
```

```
// css-loader返回的代码
return callback(null, runtimeCode + importCode + moduleCode + exportsCode)
```

```
// 解析后的代码
./src/styles/index.css:

eval("
exports = module.exports = __webpack_require__(\"./node_modules/_css-loader@2.1.0@css-loader/dist/runtime/api.js\")(false);\n

// Imports\n
var urlEscape = __webpack_require__(\"./node_modules/_css-loader@2.1.0@css-loader/dist/runtime/url-escape.js\";\n

var ___CSS_LOADER_URL___0___ = urlEscape(__webpack_require__(/*! ../images/favicon.png */ \"./src/images/favicon.png\"));

\n\n
// Module\n
exports.push([
  module.i, 
  \"/* @import './a.css'; */\\n
  body {\\n
    background-color: red;\\n
    background-image: url(\" + ___CSS_LOADER_URL___0___ + \")\\n
  }\", \"\"
]);



./src/images/favicon.png:

eval("module.exports = __webpack_require__.p + \"61e8d657aff2d3d4637b4d541d170e9c.png\";
```
