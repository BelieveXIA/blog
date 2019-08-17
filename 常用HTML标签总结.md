## 常用HTML标签总结     
一个好的网站是万丈高楼，html标签就是高楼里的一砖一瓦，希望这篇文章能为你打好基础。

### 首先讲述html里几种元素的区别 
至于我为什么要先讲述这元素种类呢，因为本人在学习html就是忽略了一下这个知识点，更惨的是它还是很重要的，吃了一点苦头，所以这个放在开头，没基础的可以先看看，先记个大概，然后区分开各个元素的类别，元素的分类关系到一个网站基础构架，看完下文对常用标签的学习，可以回来再看一次加深印象。
#### 块状元素 
一个块状元素独占一行，可设置元素的高度、宽度、行高、顶和底边距，不设置宽度时为父类容器的宽度。   
常见的块状元素标签有：
```html
<div>、<h1>...<h6>、<p>、<ol>、<ul>、<li>、<table>、<address>、<blockquote>、<form>
```
#### 内联元素 
和其他元素都在一行上，不可设置元素的高度、宽度、顶和底边距，宽度与高度由内容决定，就是它包含的文字或图片的宽度，不可改变。   
常见的内联元素有：

```html
<span>、<a>、<label>、<strong>、<em>、<br>、<i>、<q>、<var>、<cite>、<code>
```
#### 内联块状元素
和其他元素都在一行上，元素的高度、宽度、行高、顶和底边距都可设置（就是同时拥有块状元素和内联元素的特点）   
常见的内联块状元素有：

```html
<img>、<input>
```
#### 区别：

| 种类 | 是否占一行 | 能否设置宽高 | 能否设置垂直方向的边距margin |
|---------|-------------|-------------------|---------------------------------|
| 块状元素 | 是 | 是 | 是 |
| 内联元素 | 否 | 否 | 否 |
| 内联块级元素 | 否 | 是 | 是 |
## HTML标签
这里就从html文档最开始的元素，开始简述各种常用标签的含义及作用（包括html5的新增加的标签）  
#### 1.标签`<!DOCTYPE>`    
**描述：定义文档类型**

1).`<!DOCTYPE>` 声明必须是 HTML 文档的第一行，位于`<html>`标签之前。    
2).务必在html文档开头添加<!DOCTYPE> 声明，这样浏览器才能获知文档类型。   
3).在html5以前有许多种声明方式，这里就不讲述了，而在 HTML5 中只有一种声明：
```html
<!DOCTYPE html>
```
***
#### 2.标签`<html></html>`   
**描述：定义 HTML 文档** 

1.告知浏览器其自身是一个 HTML 文档。   
2.`<html>` 与 `</html>` 标签限定了文档的开始点和结束点，在它们之间是文档的头部`<head>`和主体`<body>`。  
3.代码：
```html
<!DOCTYPE html>
<html>

</html>
```
***
#### 3.标签`<head></head>`   
**描述：（文档头部）定义关于文档的信息** 

1).`<head></head>`中的元素可以引用脚本、指示浏览器在哪里找到样式表、提供元信息等，大部分数据是不展示给网站读者。   
2).在`<head>`中可添加标签有：
`<title>,<meta>,<base>,<link>,<script>,<style>`，**其中`<title>`定义文档的标题，它是 head 部分中唯一必需的元素**  
3).代码：
```html
<!DOCTYPE html>
<html>
<head>
    <title>html文档标题</title>
</head>
</html>
```
***
#### 4.标签`<body></body>`   
**描述：定义文档的主体** 

1).包含文档的所有内容（比如文本、超链接、图像、表格和列表等）。   
2).不赞成在body元素这里使用任何属性。  
3).代码：
```html
<!DOCTYPE html>
<html>
<head>
    <title>html文档标题</title>
</head>
<body>网站主体部分</body>
</html>
```
***
#### 5.标签`<script></script>`   
**描述：定义客户端脚本** 

1).type 属性规定脚本的 MIME 类型,如javascript表示为：type="text/javascript" 。   
2).script 元素既可以包含脚本语句，也可以通过 src 属性指向外部脚本文件，如：src="./myscript.js"。  
3).代码：
```html
<script type="text/javascript" src="./myscript.js"></script><!--引用外部脚本文件，可以相对路径，也可以绝对路径-->

<script type="text/javascript">
document.write("Hello World!")
</script><!--直接包含脚本语句-->
```
***
#### 6.标签`<style></style>`   
**描述：定义文档样式信息** 

1).type 属性是必需的，唯一可能的值是 type="text/css"。   
2).`<style>` 元素位于 `<head>` 部分中，一样可以引用外部的层叠样式表或者直接包含样式语句
,不过引用外部的层叠样式表要使用`<link>`标签。    
3).代码：
```html
<head>
    <link rel="stylesheet" type="text/css" href="mystyle.css" /><!--引用外部的层叠样式表-->
    <style type="text/css">
    a{ color:blue; }
    </style><!--直接包含样式语句-->
</head>
```
***
#### 7.标签`<div></div>`   
**描述：定义文档中的分区或节** 

1).把文档分割为独立的、不同的部分,就像是把网站分割成一个个具有属性的方块，`<div>` 是最常用的布局标签。   
2).通过给 `<div>` 加上 class 或 id 属性可以应用额外的样式。  
3).代码：
```html
<div class=" " id=" ">块状元素</div>
```
***
#### 8.标签`<h1>...<h6>`   
**描述：六个不同的 HTML 标题** 

1).`<h1>`定义最大的标题。`<h6>` 定义最小的标题。   
2).代码：
```html
<h1>这是标题 1</h1>
<h2>这是标题 2</h2>
<h3>这是标题 3</h3>
<h4>这是标题 4</h4>
<h5>这是标题 5</h5>
<h6>这是标题 6</h6>
```
***
#### 9.标签`<p></p>`   
**描述：定义段落** 

1).段落样式建议不要直接属性取值定义，最好在样式表中规定。   
2).`<p>`元素会自动在其前后创建一些空白。浏览器会自动添加这些空间，也可以在样式表中规定
3).代码：
```html
<p>这是段落。</p>
<p>这是段落。</p>
```
***
#### 10.标签`<ol></ol>` ，`<ul></ul>`  ，`<li></li>`
**描述：`<ol></ol>`定义有序列表，`<ul></ul>`定义无序列表，`<li></li>`定义列表项目** 

1).`<ol>`有三个属性值的注意的：type规定在列表中使用的标记类型（如1、A、a、I、i）默认是数字；start规定有序列表的起始值；reversed规定列表顺序为降序(9,8,7...)。   
2).建议不要直接属性取值定义类型，最好在样式表中规定类型。  
3).`<li> `标签可用在有序列表 `<ol>` 和无序列表 `<ul>` 中。    
4)代码：
```html
<ol type="a" start="4" reversed="reversed">
  <li>标记类型为a</li>
  <li>从4（就是d）开始</li>
  <li>规定倒序</li>
</ol>
<ul>
  <li>一个无序列表</li>
  <li>一个无序列表</li>
  <li>一个无序列表</li>
</ul>
```
***
#### 11.标签 `<table></table>`,`<tr></tr>`,`<th></th>`,`<td></td>`
**描述： `<table></table>`定义表格,`<tr></tr>`定义表格中的行,`<th></th>`定义表格中的表头单元格,`<td></td>`定义表格中的单元** 

1). 有一个属性要注意的，是summary规定表格的摘要，这个的值网站读者不可见的，但是使搜索引擎更好的读懂表格内容，增加了表格的可读性（语义化），屏幕阅读器也可以利用该属性。  
2).想深入了解表格绘制的可以去了解`<caption>、<col>、<colgroup>、<thead>、<tfoot>、<tbody>` 元素
3).代码：
```html
<!--两行两列表格-->
<table>
  <tr>
    <th>onehead</th>
    <th>twohead</th>
  </tr>
  <tr>
    <td>one</td>
    <td>two</td>
  </tr>
</table>
```
***
#### 12.标签`<address></address>`   
**描述：定义文档作者或拥有者的联系信息** 

1). 当`<address>` 元素位于 `<body> `元素内，则它表示文档联系信息。当 `<address>` 元素位于 `<article>` 元素内，则它表示文章的联系信息。文本通常呈现为斜体。   
2).通常连同其他信息被包含在 `<footer>` 元素中。  
3).代码：
```html
<address>
Written by <a href="https://juejin.im">掘金</a>
</address>
```
***
#### 13.标签`<blockquote></blockquote>`，`<q></q>`   
**描述：`<blockquote></blockquote>`标记长的引用,`<q></q>`标记短的引用** 

1).`<blockquote>` 与 `</blockquote>` 之间的所有文本都会从常规文本中分离出来，经常会在左、右两边进行缩进（增加外边距），而且有时会使用斜体。  
2).`<q></q>`的短文本引用，呈现形式浏览器经常在引用的内容前后添加引号。   
3).代码：
```html
<html>
<body>
    <span>Here comes a long quotation:</span>
    <blockquote>
    This is a long quotation. This is a long quotation. This is a long quotation. This is a long quotation. This is a long quotation.
    </blockquote>
    <!--浏览器在 blockquote 元素前后添加了换行，并增加了外边距。-->
    <q>112233445566778899</q>
</body>
</html>

```
***
#### 14.标签`<form></form>`   
**描述：用于为用户输入创建 HTML 表单** 

1).表单能够包含 input 元素，比如文本字段、复选框、单选框、提交按钮等。   
2).表单用于需要向服务器传输数据的网页部分，想深入地了解表单还可以了解 `<menus>、<textarea>、<fieldset>、<legend>、<label> `元素，它们均可被表单包含， 结合使用。    
3).属性：
| 属性 | 值 | 描述 |
|----------------|------------|--------------------------------------|
| action | URL | 规定当提交表单时向何处发送表单数据 |
| enctype |  | 规定在发送表单数据之前如何对其进行编码 |
| method | get\post | 规定用于发送 form-data 的 HTTP 方法 |
| name | form_name | 规定表单的名称 |
| target | _blank，_self，_parent，_top，framename | 规定在何处打开 action URL |
| autocomplete | on\off | 规定是否启用表单的自动完成功能(h5新增属性） |
| novalidate | novalidate | 如果使用该属性，则提交表单时不进行验证(h5新增属性） |
4).代码：
```html
<form>
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
```
***
#### 15.标签`<span></span>`   
**描述：定义文档中的节** 

1).`<span>` 标签被用来组合文档中的行内元素，以便通过样式来格式化它们。   
2).如果不对 span 应用样式，那么 `<span>` 元素中的文本与其他文本不会任何视觉上的差异，常常添加`<span>`元素就是为了给行内元素添加更多的样式和区分其他行内元素，可以为`<span>`添加class或id属性，增加适当的语义。  
3).代码：
```html
<span>行内元素</span>
```
***
#### 16.标签`<label></label>`   
**描述：为 input 元素定义标注（标记）** 

1).`<label>` 元素不会向用户呈现任何特殊效果。不过，它为鼠标用户改进了可用性。如果在 `<label>` 元素内点击文本，就会触发此控件。就是说，当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上。   
2)."for" 属性可把 label 绑定到另外一个元素。请把 "for" 属性的值设置为相关元素的 id 属性的值。  
3).代码：
```html
<form action="" method="get" id="">
<label>Male
<input type="radio" name="sex" id="male" value="male" />
</label>
<label>Female
<input type="radio" name="sex" id="female" value="female"  />
</label>
<input type="submit" value="提交" />
</form>
<p>以下的label位于 form 元素之外，但是设置了for="male",绑定到了form表单内的id为male的元素，仍然是表单的一部分。运行代码请尝试点击这个 label，可以切换到 radio 控件。</p>

<label for="male" form="nameform">Male</label>
```
***
#### 17.标签`<a></a>`   
**描述：定义超链接，用于从一张页面链接到另一张页面（跳转功能）** 

1).其最重要的属性是 href 属性，它指示链接的目标，例如：href="https://juejin.im"。   
2).有一个规定，如果不使用 href 属性，则不可以使用如下属性：download, hreflang, media, rel, target 以及 type 属性。   
3).download属性规定被下载的超链接目标；    
hreflang属性规定被链接文档的语言；  
media属性规定被链接文档是为何种媒介/设备优化的；   
rel属性规定当前文档与被链接文档之间的关系；   
target属性规定在何处打开链接文档；   
type属性规定被链接文档的的 MIME 类型。   
具体用法与前文讲得其他元素的属性用法基本一样，不重复。  
4).代码：
```html
<a href="https://juejin.im">掘金</a>
```
***
#### 18.短语元素   
**描述：  
`<em>`把文本定义为强调的内容，对浏览器一般呈现斜体；   
`<strong>`把文本定义为语气更强的强调的内容，对浏览器一般呈现斜体；   
`<code>`定义计算机代码文本，可以以代码形式输入给读者看；   
`<var>`定义变量，可以将此标签与` <pre>` 及 `<code>` 标签配合使用；   
`<cite>`定义引用,以斜体显示，可使用该标签对参考文献的引用进行定义，比如书籍或杂志的标题** 

1).通常情况下不反对也不建议使用这些短语元素，为了达到某种视觉效果能够用样式表解决的，最好用样式表。  
2).代码：
```html
<em>需要强调的文本。斜体</em>

<strong>需要强调的文本。加粗</strong>

<code>一行代码语言</code>
<!--注：如果是多行代码，可以使用<pre></pre>标签-->

<var>变量</var>

<address>
    <cite>The Scream</cite>
    by Edward Munch. Painted in 1893.
</address>
```
***
#### 19.标签`<i></i>`、`<mark></mark>`   
**描述：`<i></i>`定义显示斜体文本效果;`<mark></mark>` 标签定义带有记号的文本** 

1).`<i>`被用来表示科技术语、其他语种的成语俗语、想法、宇宙飞船的名字等。   
2).`<mark>` 被标记的/高亮显示的文本。  
3).代码：
```html
<i> 标签一定要和结束标签一起用 </i>

<mark>标记的/高亮显示的文本</mark>
```
***
#### 20.标签`<input>`   
**描述：用于搜集用户信息** 

1).**`<input>`元素很重要，也很多样化**。根据不同的 type 属性值，输入字段拥有很多种形式。输入字段可以是文本字段(text)、掩码后的文本控件(password)、隐藏的输入字段(hidden)、单选按钮(radio)、复选框(checkbox)、按钮(button)、提交按钮(submit)、供文件上传按钮(file)、图像形式的提交按钮(image)、定义重置按钮(reset)等 。   
2).value属性规定 input 元素的值；placeholder属性规定帮助用户填写输入字段的提示；readonly属性规定输入字段为只读。   
3).`<input>`还有个很多其他的属性，就不一一列举了       
4).代码：
```html
<input type="text" value="文本框" />
<input type="password" value="密码框" />
<input type="hidden" value="不可见输入框" />
<input type="button" value="按钮"/>
<input type="image" value="image" />
<input type="file" value="file" />
<input type="submit" value="提交" />
<input type="reset" value="重置"/>
<input type="radio" value="单选框" />
<input type="chexkbox" value="复选框" />
```
***
#### 21.标签`<img>`   
**描述：向网页中嵌入一幅图像** 

1).`<img>` 标签创建的是被引用图像的占位空间，并不会在网页中插入图像，而是从网页上链接图像。     
2).有两个必需的属性：src 属性规定显示图像的 URL（可以绝对路径，也可以相对路径） 和 alt 属性规定图像的替代文本。  
3).代码：
```html
<img src="./img/a.jpg"  alt="图片1" />
<img src="https://preview.qiantucdn.com/58pic/35/00/10/86c58PICwHV9K52N5wa58PIC58PIC_PIC2018.jpg!w1024_small"  alt="图片2" />
```
***
#### 22.标签`<br>`,`<hr>`  
**描述：`<br>`定义简单的折行；`<hr>`定义水平线** 

1).`<br>` 标签只是简单地开始新的一行，如果希望文本流在内联表格或图像的下一行继续输出，使用 clear 属性：left、right 或者 all，每个值都代表一个边界或两边的边界。   
2).`<hr>`水平分隔线可以在视觉上将文档分隔成各个部分。  
3).代码：
```html
<br/>
<hr/>
```
***
#### 23.标签`<footer></footer>`   
**描述：定义文档或节的页脚** 

1).页脚通常包含文档的作者、版权信息、使用条款链接、联系信息等，但`<footer>`是 HTML 5 中的新标签，IE 8 以及更早的版本不支持。   
2).可以在一个文档中使用多个 `<footer>` 元素。  
3).代码：
```html
<footer>
    <div></div>
    <address>
    Written by <a href="https://juejin.im">掘金</a>
    </address>
</footer>
```
***
#### 24.标签`<header></header>`   
**描述：定义文档的页眉（介绍信息）** 

1).`<header>` 标签是 HTML 5 中的新标签，IE 8 以及更早的版本不支持。   
2).作为介绍内容或者导航链接栏的容器，在一个文档中，您可以定义多个` <header>` 元素。  
3).代码：
```html
<header>
    <div>页眉</div>
</header>
```
***
#### 25.标签`<meta>`   
**描述：提供了 HTML 文档的元数据** 

1).`<meta>` 标签通常位于` <head>` 区域内，不会显示在客户端，但是会被浏览器解析；通常用于指定网页的描述，关键词，文件的最后修改时间，作者及其他元数据。   
2).在实际使用中，最常用到它的一个属性是charset，定义文档的字符编码（中文为"UTF-8"),这是html5出现的新属性，取代了以前复杂的代码写法。  
3).代码：
```html
<head>
    <meta charset="UTF-8">
</head>
```
***
以上是我总结的较为常用的html标签及用法，很多都是在我学习HTML时笔记的整理，在html中这只是一部分标签，想深入前端学习，剩下的标签也要好好学。   
如文中有不对的地方请指出，谢谢观看！
