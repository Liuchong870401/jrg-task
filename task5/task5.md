# 问答
### 一.样式有几种引入方式? link 和 @import有什么区别?
- **样式有三种引入方法**
1. **外部样式表：**在html文件外建立css样式文件，然后再通过使用``<link>``标签在html的`<head>`部分把css样式引入。
格式例如：
``<link rel="stylesheet" type="text/css" href="../css/index.css">``
2. **内部样式表：**直接才html文件中的``<head>``部分写入css样式表。
格式例如：
  ```
  <style>
  p {
    background-color: red;
  }
  </style>
  ```
  3. **内联样式表：**直接在标签中规定该标签样式。
  格式例如：
  `<p style="border:10px solid #000">这是一个段落</p></body>`
- **link 和 @import有什么区别**
1. **身份不一样：**`<link>`是html标签，`@import`则是css提供的专用引入样式的。
2. **作用不一样：**`<link>`可以加载css样式，也可以定义被链接文档的位置`<url>`,文档中文本的语言`hreflang`,以及当前文档与被链接文档的关系`<rel>`等，而`@import`只能用来引入样式。
3. **浏览器加载速度不一样：**`<link>`会让浏览器同时加载样式与文本,而 `@import`是在浏览器加载文本后再进行样式加载。速度较慢。
4. **兼容性不同：**`@import`在css2.1之前的版本中部能使用，并且在js中用demo改变样式时`@import`不受demo控制。而`<link>`无此问题。
*********
### 二.文件路径../main.css 、./main.css、main.css、/main.css有什么区别？
- ../main.css指转向上一级目录下的CSS文件
- ./main.css指转向当前目录下的CSS文件
- main.css指转向当前目录下的CSS文件
- /main.css指转向当前磁盘根目录的CSS文件
**************
### 三.console.log是做什么用的
- `console.log`一般用于在控制台调试代码，并且可以一边输入一边显示相对内容。
********
### 四.text-align有几个值，分别有什么作用？为什么text-align:justify没有效果？
- **`text-align`有5个值，作用分别如下：**
`text-align：left` 默认值 文本左对齐
`text-align：right` 文本右对齐
`text-align：center` 文本水平居中
`text-align: justify` 文本两端对齐
`text-align: inherit` 文本属性继承父元素
- **为什么`text-align: justify`没有效果？**
如果页面最右边的剩下的空间不足以放下一个文字，文字只能换行，这时可用`text-align: justify`属性使文本左右两端对齐，如果文本太短不占一行则用此属性无效果。
![范例](../taskPictures/task5/task5-1.png)
**********
### 五.px、em、rem分别是什么？有什么区别？如何使用?
- 这几个都是代码中元素的大小计量单位。
- px是以屏幕分辨率的像素为标准。1px就代表一个像素大小。
- em以父元素的大小为计量标准。若父元素未设置大小则一直往上追溯，1em就是父元素的一倍大小。一般默认1em=16px。
- rem以根元素html的大小为计量标准。其他与em相同。
**************
### 六.对chrome 审查元素的功能做个简单的截图介绍
![审查元素介绍](../taskPictures/task5/google2.png)
******************
# [代码](http://js.jirengu.com/xoromizema/3/edit)
