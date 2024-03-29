# noie.js

[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu)
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

中文 | [English](README-EN.MD)

一个简单的脚本用于检查 ECMAScript 标准的支持情况。
常用的使用场景是检测 IE 浏览器。
个人认为连 ES6 都不支持的浏览器和 IE 没有区别，因此后文将所有不支持某 ECMAScript 版本的浏览器统称为 IE。

- [noie.js](#noiejs)
  * [为什么 noie](#为什么-noie)
  * [使用方法](#使用方法)
    - [自动检测](#自动检测)
    - [手动检测](#手动检测)
  * [版本检测支持列表](#版本检测支持列表)
  * [对某人的回复](#对某人的回复)

## 为什么 noie
个人观点：使用 Bable 支持 IE 是没有任何意义的行为，越是支持 IE 就会使得 IE 用户不愿意更新，新的技术就无法得到普及。
我们应该停止支持 IE。起码停止对那些不支持 ES6 的浏览器的支持。

当然，如果你的项目是使用在一些对安全有特殊要求的地方，那么应该优先考虑安全，其次才是新技术。

## 使用方法

### 自动检测
在新版本中，我添加了自动检测功能，如果你需要自动检测，可以加载对应版本的脚本
```html
<script src="/path/to/noie.<version>.js" />
```

比如我想检测，ES2020 是否支持，则您应该加载的脚本为
```html
<script src="/path/to/noie.es2020.js" />
```

当检测完毕后，会对 `document` 对象进行修饰，添加一个变量 `NOIE_PASS`，您可以直接对这个变量使用 `if` 来判断是否通过了 noie 检测。
例如下方代码将在检测到 IE 浏览器后弹出提示框。

```html
<script src="/path/to/noie.es2020.js" />
<script>
if (!document['NOIE_PASS']) {
  alert("不支持的浏览器")
}
</script>
```
### 手动检测
手动检测仍是支持的，您只需要导入完整的本体文件即可
```html
<script src="/path/to/noie.js" />
```

检测使用的函数请见 [版本检测支持列表](#版本检测支持列表) 的本体函数一项，下面给出一个检测 ES2020 的例子

```javascript
es2020(function() {
  alert("不支持的浏览器")
})
```

## 版本检测支持列表

- ES2015 (ES6)
  + 自动检测 `noie.es2015.js`
  + 本体函数 `es6(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 模板字符串 ``` `a`; ``` 
- ES2016 (ES7)
  + 自动检测 `noie.es2016.js`
  + 本体函数 `es2016(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 指数运算符 ``` 0**0; ``` 
- ES2017
  + 自动检测 `noie.es2017.js`
  + 本体函数 `es2017(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 异步箭头函数 ``` async()=>0; ``` 
- ES2018
  + 自动检测 `noie.es2018.js`
  + 本体函数 `es2018(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 扩展运算符 ``` {...{}}; ``` 
- ES2019
  + 自动检测 `noie.es2019.js`
  + 本体函数 `es2019(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 新 try-catch 语法 ``` try{}catch{}; ``` 
- ES2020
  + 自动检测 `noie.es2020.js`
  + 本体函数 `es2020(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 空值合并运算符 ``` 0??1; ``` 
- ES2021
  + 自动检测 `noie.es2021.js`
  + 本体函数 `es2021(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 数字分隔符 ``` 1_0; ``` 
- ES2022
  + 自动检测 `noie.es2022.js`
  + 本体函数 `es2022(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 Regex 支持 indices 模式 ``` /0/d ``` 
- ES2023
  + 自动检测 `noie.es2023.js`
  + 本体函数 `es2023(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 新内建函数 ``` Array.findLast ``` 
- ES2024
  + 自动检测 `noie.es2024.js`
  + 本体函数 `es2024(onFail?: () => void, onSuccess?: () => void)` 
  + 检测方法 Regex 支持 unicodeSets 模式 ``` /0/v ``` 

## 对某人的回复

介于我不认识的某人说我这脚本混淆了没开源，我决定补充一个中文解释说明

首先**这叫 minify**

然后在 README 正文第一行就写明了这不是检测 IE 浏览器，而是用来检测 ECMAScript 兼容版本

最后为什么你不贴出来没 minify 的？

因为这个脚本太简单了，所以我懒得上什么 ESBuild 什么 Vite blabla的，太麻烦了，我从我别的项目复制配置文件的时候我都写完本体了。
**因此我*手动* minify。**
两三行就搞定的东西，手动 minify 这事很让你感到震惊吗？

既然你这么喜欢混淆，**附上一个混淆版本 `noie.obfuscated.js`。**

使用的混淆器是我修改过的，原始项目来自 [这里](https://github.com/lowbyteproductions/JavaScript-Is-Weird)。
这边非常推荐看一下这个人的 [这个 Youtube 视频](https://www.youtube.com/watch?v=sRWE5tnaxlI)。

我修改过的版本在：[Gist](https://gist.github.com/Lama3L9R/16e84970e357ed77d72b3fb02d7c5fce)

## 开放源代码许可

本项目采用 Anti-996 开放源代码许可，若您需要使用本项目则您必须遵守该许可。

版权归属 Qumolama.d (aka lamadaemon) 2023 - Present

如果您希望了解更多反对 996 工作制请访问：https://996.icu
