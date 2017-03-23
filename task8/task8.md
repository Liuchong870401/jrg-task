# 问答
## 一.块级元素和行内元素分别有哪些？动手测试并列出4条以上的特性区别
- **块级元素：**
div h1 h2 h13 h4 h5 h6 p hr form table td th tr ul ol dl li dt dd address menu fieldset
- **行内元素**
span a strong em br img input lable select textarea button code script
- **动手测试并列出4条以上的特性区别**
1.块级元素独占一行 行内元素则不是。
2.块级元素可以设置宽高，行内元素不可以设置宽高。
3.块级元素可以包含行内元素和块级元素。行内元素不能包含块级元素。
4.块级元素可以设置内边距padding外边距margin，行内元素只能设置左右内边距和左右外边距。
5.块级元素水平居中用margin：0 auto,行内元素则在父元素中使用text-align:center.
*************
## 二.什么是 CSS 继承? 哪些属性能继承，哪些不能？
- 继承性是CSS三大特性之一，是指给标签设置一些属性，子元素及其后代也可以使用。
- 一般只有以color(颜色)font(文字)text(文本)line(划线)开头的关于文本的属性以及表格属性才能继承。
**能够继承的属性有：**
text-indent、text-align、text- decoration、text-transform、direction、color、font、 font-family、font-size、font-style、font-variant、font-weight、list-style、list-style-type、list-style-position、list-style-image、border-collapse、visibility、cursor。
- 涉及到元素盒子的定位和现实方式的属性不能继承，如边框(border)外边距(margin)内边距(padding)等。另外a标签的颜色与下划线属性，h标签的文字大小不能继承。
**不能继承的属性有：**
display、margin、border、padding、background、height、min-height、max- height、width、min-width、max-width、overflow、position、left、right、top、 bottom、z-index、float、clear、table-layout、vertical-align、page-break-after、 page-bread-before、unicode-bidi。
****************
## 三.如何让块级元素水平居中？如何让行内元素水平居中?
- 块级元素水平居中用margin：0 auto,行内元素则在父元素中使用text-align:center.
************
## 四.用 CSS 实现一个三角形
**************
## 五.单行文本溢出加 ...如何实现?
- 分三个步骤实现：
1.先给文本使用white-space: nowrap;属性使文本不会换行。
2.再添加overflow: hidden;属性表示内容被修剪且其余内容不可见。
3.最后添加text-overflow: ellipsis;属性指定被修剪的内容用...符号表示。
************
## 六.px, em, rem 有什么区别
- 这几个都是代码中元素的大小计量单位。
- px是以屏幕分辨率的像素为标准。1px就代表一个像素大小。
- em以父元素的大小为计量标准。若父元素未设置大小则一直往上追溯，1em就是父元素的一倍大小。一般默认1em=16px。
- rem以根元素html的大小为计量标准。其他与em相同。
************
## 七.解释下面代码的作用?为什么要加引号? 字体里的数字符号代表什么?
```
body{
  font: 12px/1.5 tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif;
}
```
- 表明整个body里面的字体大小为12px,行高为12px的1.5倍，即18px.字体优先采用tahoma字体，后面用,分开的都是备选字体，若前面的字体浏览器找不到则按照顺序依次往下选择。
- 引号表明字体名称包含空格，引号内部是一个字体的整体名称。
- 在 CSS 中设置字体时，直接写字体中文或英文名称浏览器都能识别，直接写中文的情况下编码（GB2312、UTF-8 等）不匹配时会产生乱码。保险的方式是将字体名称用Unicode来表示。代码中的'\5b8b\4f53'就是用Unicode表示的字体宋体。
*************
# 代码
