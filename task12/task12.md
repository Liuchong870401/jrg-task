##一.什么是 CSS hack
- 由于不同厂商的浏览器，比如Internet Explorer,Safari,Mozilla Firefox,Chrome等，或者是同一厂商的浏览器的不同版本，如IE6和IE7，对CSS的解析认识不完全一样，因此会导致生成的页面效果不一样，得不到我们所需要的页面效果。这个时候我们就需要针对不同的浏览器去写不同的CSS，让它能在不同的浏览器中也能得到我们想要的页面效果。这个过程就是CSS hack。
*********
##二.谈一谈浏览器兼容的思路
- 1.要不要做
 - 产品的角度（产品的受众、受众的浏览器比例、效果优先还是基本功能优先）
 - 成本的角度 (有无必要做某件事)
- 2.做到什么程度
 - 让哪些浏览器支持哪些效果
- 3.如何做
 - 根据兼容需求选择技术框架/库(jquery)
 - 根据兼容需求选择兼容工具(html5shiv.js、respond.js、css reset、normalize.css、Modernizr)
postCSS
 - 条件注释、CSS Hack、js 能力检测做一些修补
- 4.代码兼容的方式
  - 渐进增强(progressive enhancement): 针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。
   - 优雅降级 (graceful degradation): 一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。
 *********
##三.列举5种以上浏览器兼容的写法
|格式|作用|
|-- |-- |
|* |ie6,ie7可以识别|
|_和- | ie6可以识别|
|!important |ie7及以上，firefox都支持，ie6认识带!important的样式属性但不认识!important的优先级|
|-webkit-|针对safari，chrome浏览器的内核CSS写法|
|-moz-|针对firefox浏览器的内核CSS写法|
|-ms-|针对ie内核的CSS写法|
|-o-|针对Opera内核的CSS写法|
|value后加\9|ie/edge 6-8可以识别|

**********
##四.以下工具/名词是做什么的
- 条件注释
 - 条件注释 (conditional comment) 是于HTML源码中被IE有条件解释的语句。条件注释可被用来向IE提供及隐藏代码。IE10不再支持条件注释，若代码使用了条件注释，可在该页面顶部添加下面的 meta 标记，以选择采用 Internet Explorer 9 行为：

 ```
 <meta http-equiv="X-UA-Compatible" content="IE=EmulateIE9">
 ```
 - 条件注释格式如下：
 ```
    <!--[if IE 6]>
    <p>You are using Internet Explorer 6.</p>
    <![endif]-->
    <!--[if !IE]>-->
    <script>alert(1);</script>
    <!--<![endif]-->
    <!--[if IE 8]>
    <link href="ie8only.css" rel="stylesheet">
    <![endif]-->
 ```
 
```
<!--[if IE 9]>用于 IE9 <![endif]-->
<!--[if !IE]> -->用于非 IE <!-- <![endif]-->
<!--[if lt IE 8]>用于 IE8 以下版本<![endif]-->
<!--[if lte IE 8]> 用于 IE8及更低版本 <![endif]-->
<!--[if gt IE 6]> 用于 IE6 以上版本<![endif]-->
<!--[if gte IE 6]>用于 IE6 及更高版本 <![endif]-->
<!--[if(IE6)|(IE7)]>用于IE6或者IE7<![endif]-->
```
- IE Hack
 - 针对IE浏览器编写不同的CSS的让IE能够正常渲染的过程。有3种表现形式：CSS属性前缀法、选择器前缀法以及IE条件注释法。
- js 能力检测
 - 能力检测的目标不是识别特定的浏览器，而是识别浏览器的能力。采用这种方式不必顾及特定的浏览器如何如何，只要确定浏览器支持特定的能力，就可以给出解决方案。
- html5shiv.js
 - 有些浏览器不支持一些新的HTML5标签，css不起作用。html5shiv.js利用脚本document.createElement(“”)创建对应的脚本，CSS选择器便可正确应用到该标签。
- respond.js
 - 用于为 IE6-8 以及其它不支持 CSS3 Media Queries 的浏览器提供媒体查询的 min-width 和 max-width 特性，实现响应式网页设计（Responsive Web Design）。
- css reset
 - 重置浏览器中的CSS默认样式。
- normalize.css
 - Normalize.css 只是一个很小的CSS文件，但它在默认的HTML元素样式上提供了跨浏览器的高度一致性。相比于传统的CSS Reset，Normalize.css是一种现代的、为HTML5准备的优质替代方案。
- Modernizr
 - 添加完Modernizr引用以后，它就立即生效了。运行的时候它会在html元素上添加一批CSS的class名称，这些class名称标记当前浏览器支持哪些特性和不支持哪些特性，支持的特性就直接显示该天特性的名称作为一个class，不支持的特性显示的class是“no-特性名称”（例如：no-flexbox）。
- postCSS
 - PostCSS 是使用 JS 插件来转换 CSS 的工具，支持变量，混入，未来 CSS 语法，内联图像等等。
**********
##五.一般在哪个网站查询属性兼容性？

[caniuse](http://caniuse.com/)
