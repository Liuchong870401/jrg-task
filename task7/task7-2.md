## 一.class 和 id 的使用场景?
- 一个元素可以使用多个class,多个class也可使用同一个class标记相同的类。选择器一般用class名可以比较方便灵活。而一个元素只能有唯一的id，并且id名不能重复。一般用于页面关键部位元素，往往用于JS中。
***********
## 二.CSS选择器常见的有几种?
选择器大致分五种
- 基础选择器：

|样式|选择器名|含义|
|--|--|--|
|*|通用元素选择器|匹配页面任何元素|
|#id|id选择器|匹配特定id的元素|
|.class	|类选择器|匹配class包含(不是等于)特定类的元素|
|element|	标签选择器|直接使用该标签的名字指定|
- 组合选择器：

|样式|选择器名|含义|
|--|--|--|
|E,F|多元素选择器|用,分隔，同时匹配元素E或元素F|
|E F|后代选择器|用空格分隔，匹配E元素所有的后代（不只是子元素、子元素向下递归）元素F|
|E>F|子元素选择器|用>分隔，匹配E元素的所有直接子元素|
|E+F|直接相邻选择器|匹配E元素之后的相邻的同级元素F|
|E~F|普通相邻选择器|匹配E元素之后的同级元素F（无论直接相邻与否）|
|.class1.class2	/E.class2|同时指定|选择器和选择器连写的时候中间没有分隔符，. 和 # 本身充当分隔符的元素，匹配同时有以上两个属性的标签|

- 属性选择器

|选择器样式|含义|
|--|--|
|E[attr]|匹配所有具有属性attr的元素，div[id]就能取到所有有id属性的div|
|E[attr = value]|匹配属性attr值为value的元素，div[id=test],匹配id=test的div|
|E[attr ~= value]	|匹配所有属性attr具有多个空格分隔、其中一个值等于value的元素|
|E[attr ^= value]	|匹配属性attr的值以value开头的元素|
|E[attr $= value]|	匹配属性attr的值以value结尾的元素|
|E[attr *= value]|	匹配属性attr的值包含value的元素|

- 伪类选择器

|选择器样式|含义|
|--|--|
|E:first-child	|匹配元素E的第一个子元素|
|E:link	|匹配所有未被点击的链接|
|E:visited	|匹配所有已被点击的链接|
|E:active	|匹配鼠标已经其上按下、还没有释放的E元素|
|E:hover	|匹配鼠标悬停其上的E元素|
|E:focus	|匹配获得当前焦点的E元素|
|E:lang(c)	|匹配lang属性等于c的E元素|
|E:enabled	|匹配表单中可用的元素|
|E:disabled	|匹配表单中禁用的元素|
|E:checked	|匹配表单中被选中的radio或checkbox元素|
|E::selection	|匹配用户当前选中的元素|
|E:root	|匹配文档的根元素，对于HTML文档，就是HTML元素|
|E:nth-child(n)	|匹配其父元素的第n个子元素，第一个编号为1|
|E:nth-last-child(n)|匹配其父元素的倒数第n个子元素，第一个编号为1|
|E:nth-of-type(n)	|与:nth-child()作用类似，但是仅匹配使用同种标签的元素|
|E:nth-last-of-type(n)|	与:nth-last-child() 作用类似，但是仅匹配使用同种标签的元素|
|E:last-child	|匹配父元素的最后一个子元素，等同于:nth-last-child(1)|
|E:first-of-type	|匹配父元素下使用同种标签的第一个子元素，等同于:nth-of-type(1)|
|E:last-of-type	|匹配父元素下使用同种标签的最后一个子元素，等同于:nth-last-of-type(1)|
|E:only-child	|匹配父元素下仅有的一个子元素，等同于:first-child:last-child或 :nth-child(1):nth-last-child(1)|
|E:only-of-type	|匹配父元素下使用同种标签的唯一一个子元素，等同于:first-of-type:last-of-type或 :nth-of-type(1):nth-last-of-type(1)|
|E:empty	|匹配一个不包含任何子元素的元素，文本节点也被看作子元素|
|E:not(selector)|	匹配不符合当前选择器的任何元素|
*上述n的取值1，2，3，4...，2n+1, 2n, 4n-1...,odd, even*

- 伪元素选择器

|选择器样式|含义|
|--|--|
|E::first-line	|匹配E元素内容的第一行|
|E::first-letter	|匹配E元素内容的第一个字母|
|E::before	|在E元素之前插入生成的内容|
|E::after	|在E元素之后插入生成的内容|
***********
## 三.选择器的优先级是怎样的?对于复杂场景如何计算优先级？
- 选择器的优先级是按照选择器的权重划分的。其权重由高到低如下：
1.在属性后面使用 !important 会覆盖页面内任何位置定义的元素样式
2.作为style属性写在元素标签上的内联样式
3.id选择器
4.类选择器，伪类选择器，属性选择器
5.标签选择器，伪元素选择器
6.通配符选择器
7.浏览器自定义
- 在复杂场景计算优先级：
1.按照上面选择器优先级的的权重值相加，看选择器中包含的的元素在哪个级别，权重级别高的元素越多则越优先。若同一级别元素一样多则依次往下类推。
2.若两个选择器权重一样，则写在后面的样式会覆盖前面的样式。
**********
## 四.a:link, a:hover, a:active, a:visited 的顺序是怎样的？ 为什么？
- 书写顺序是：a:link>a:visited>a:hover> a:active
- 因为css样式具有层叠行，上面四个样式的权重一样，写在后面的样式会覆盖前面的样式。
1.若无任何操作则显示a:link。
2.若已经访问则a:visited会覆盖a:link，所以a:visited在a:link之后。
3.无论访问与否a:hover必须生效，所以写在a:link和a:visited后面。
4.当点击时则只会显示a:active，所以写在最后。
************
## 五.以下选择器分别是什么意思?

|选择器|含义|
|--|--|
|#header{}|id为header的元素|
|.header{}|class名为header的元素|
|.header .logo{}|在class名为header的元素的后代中，class名为logo的元素|
|.header.mobile{}|既包含class名为header又包含class名为mobile的元素|
|.header p, .header h3{}|class名为header的元素后代p标签和class名为header的元素后代h3标签|
|#header .nav>li{}|class名为header的元素的后代中class名为nav的元素的子元素li标签|
|#header a:hover{}|id名为header的元素的后代a选择器鼠标悬停的状态|
|#header .logo~p{}|id名为header的元素的后代中class名为logo的元素的所有相邻同级别标签p|
|#header input[type="text"]{}|id名为header的元素的后代中type属性值为text的input标签|
  *********
## 六.列出你知道的伪类选择器
|选择器样式|含义|
|--|--|
|E:first-child	|匹配元素E的第一个子元素|
|E:link	|匹配所有未被点击的链接|
|E:visited	|匹配所有已被点击的链接|
|E:active	|匹配鼠标已经其上按下、还没有释放的E元素|
|E:hover	|匹配鼠标悬停其上的E元素|
|E:focus	|匹配获得当前焦点的E元素|
|E:lang(c)	|匹配lang属性等于c的E元素|
|E:enabled	|匹配表单中可用的元素|
|E:disabled	|匹配表单中禁用的元素|
|E:checked	|匹配表单中被选中的radio或checkbox元素|
|E::selection	|匹配用户当前选中的元素|
|E:root	|匹配文档的根元素，对于HTML文档，就是HTML元素|
|E:nth-child(n)	|匹配其父元素的第n个子元素，第一个编号为1|
|E:nth-last-child(n)|匹配其父元素的倒数第n个子元素，第一个编号为1|
|E:nth-of-type(n)	|与:nth-child()作用类似，但是仅匹配使用同种标签的元素|
|E:nth-last-of-type(n)|	与:nth-last-child() 作用类似，但是仅匹配使用同种标签的元素|
|E:last-child	|匹配父元素的最后一个子元素，等同于:nth-last-child(1)|
|E:first-of-type	|匹配父元素下使用同种标签的第一个子元素，等同于:nth-of-type(1)|
|E:last-of-type	|匹配父元素下使用同种标签的最后一个子元素，等同于:nth-last-of-type(1)|
|E:only-child	|匹配父元素下仅有的一个子元素，等同于:first-child:last-child或 :nth-child(1):nth-last-child(1)|
|E:only-of-type	|匹配父元素下使用同种标签的唯一一个子元素，等同于:first-of-type:last-of-type或 :nth-of-type(1):nth-last-of-type(1)|
|E:empty	|匹配一个不包含任何子元素的元素，文本节点也被看作子元素|
|E:not(selector)|	匹配不符合当前选择器的任何元素|
*********
## 七.div:first-child和div:first-of-type的作用和区别
- div:first-child：当前父元素下同一级别中的第一个子元素div。
- div:first-of-type：当前父元素下同一级别也是同一类型的子元素div。
## 八.运行如下代码，解析下输出样式的原因。
