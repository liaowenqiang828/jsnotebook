**HTML** 

`html`is a markup language that defines the structure of your content .which consist of a series of *element* ,which you use to enclose ,or wrap, different parts of the content to make it appear a certain way, or act a certain way.

Web 浏览器的作用是读取HTML文档，并以网页的形式显示他们。

使用标签来解释页面的内容。

`<p> 这个标签用来定义段落</p>`    

`<a> 这个标签用来定义链接</a>`     `href`  属性中指定来链接的地址。

`<img> 定义图像</img>`       `src` 属性中提供图片的地址，网络链接或文档路径都可以，图片的名称和尺寸都在属性中提供。

开始标签通常称为开放标签，结束标签通常称为闭合标签。

- **HTML元素** 指的是从开始标签到结束标签的所有**代码** 

- 某些元素具有空内容，空元素在开始标签中进行关闭<hr/>

- 大多数HTML元素可以嵌套，既可以包含其他元素。

- `<body> 这个标签定义了HTML文档的主体，也是HTML文件所能显示出来的部分</body`

- `<head>` 中的内容用来描述当前文件

- `<ul>` 是无序列表（unordered list），用来显示一组`<li>` (list item)

  ``` 
  <ul>
    <li>cherry</li>
    <li>Peach</li>
    <li>Strawberry</li>
  </ul>
  ```

- `<li>` 是有序列表。

- HTML标签对大小写不敏感。

- `<hr />`标签在HTML页面中**创建水平线** 。hr元素用于分隔内容

- 查看源文件、查看页面源代码。

- 浏览器会自动在`<p>`段落前后添加空行

- 使用`<br/>` 正确添加一个空行

- style直接将样式引入到元素中

- background-color 属性为元素定义了背景颜色

- font-family 、color、font-size分别定义了元素中的字体系列、颜色，字体大小

- text-align 规定了元素中文本的水平对齐方式：left， right， center

#### 文本格式化标签 ####

- 



- `<q> ` 短引用，行内引用，使用引号进行包围。
- `<blockquote> ` 定义引用的节，比较长的引用，会对元素进行缩进处理
- `<address> ` 定义文章或文档的联系信息，通常以斜体显示
- `<kbd> ,<samp>, <code>` 均可用于计算机代码的显示，具有固定的格式显示
- `<!-- -->` 插入注释

**样式表 CSS** : 当浏览器读到一个样式表时，他就会按照这个样式表来对文档进行格式化

-  内联样式
- 内部样式表
- 外部样式表 ： 

        ```
<head>
  <link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
        ```



**超链接** 可以是一个字、词、图像等，通过点击这些内容来实现跳转

`<a>` 标签用于创建链接，两种使用方式

- 使用href属性-创建指向另一个文档的链接
- 使用name属性-创建文档内部的书签
- target属性定义被连接的文档在何处显示

`<a href="http://www.w3school.com.cn/">Visit W3School</a>` 中间的文字作为超级链接来显示

#### 锚    ####

多用于文档内部跳转

`<a href="#C4">查看 Chapter 4</a>`  : 创建一个指向“#C4”这个锚的链接，名字为查看Chapter4.

`<h2><a name="C4">Chapter 4</a><h2>`  创建了一个锚，名字为C4



##### 图像 ##### 

- `<img src="url" /`  图像标签，是空标签，只包含属性，没有**闭合标签** ，

​        `src` 源属性的值是图像的URL地址或图像文件地址

​      `alt`替换文本属性，当图片无法加载时显示该文本

- `<map>` 定义图像地图 ？
- `<area>` 定义图像中的可点击的区域 ？



#### 创建表格 #### 

表格由<table> 标签来定义

每个表格均有若干行，由<tr>标签定义

每行被分割为若干单元格，由<td> 标签定义 （table data：即单元格的数据内容）

```
<table border="1">
  <tr>
      <td>row-1, cell-1 </td>
      <td>row-1, cell-2</td>
    </tr>
    <tr>
       <td>row-2, cell-1</td>
       <td>row-2, cell-2</td>
    </tr>
</table>
```

表格**表头**使用`<th>` 标签定义

表格**标题** `<caption>` 

空的单元格可以使用**空格占位符** ：`<td>&nbsp;</td> ` 



#### 列表 ####

无序列表<ul>, 列表相<li>

列表项内部可使用段落、换行符、图片、链接以及其他列表等等

有序列表<ol>, 列表项目使用数字进行标记

自定义列表：？



#### 块级元素，内联元素 ####

块级元素在浏览器显示时，通常会以新的行来开始，内联元素则不会换行

`<div>` 元素可用于组合其他元素的容器，

`<span>` 可用作文本的容器



#### 类 ####

对HTML进行分类，使我们能够为元素的类定义CSS样式， 可以为相同的类设置相同的样式



#### 布局

`<div>` 元素常用作布局工具

#### 响应式

RWD(responsive Web Design)

#### 框架

通过使用框架可以在同一个浏览器窗口中显示不止一个页面，每份HTML文档称为一个框架，并且每一个框架都独立于其他框架。

`<frameset>`框架结构标签: 

- 定义如何将窗口分割为框架
- 每个 frameset 定义了一系列行或者列
- rows/columns 的值规定了每行或每列占据屏幕的面积

`<frame>` 框架标签定义了放置在每个框架中的HTML文档

```
下面的例子中，设置了一个两列的框架集，第一列占据窗口的25%.HTML文档frame-a.html 被置于第一列中。
<frameset cols="25%,75%">
  <frame src="frame-a.html">
  <frame src="frame-b.html">
</frameset>
```

**不能将`<body>` 标签与`<frameset>` 标签同时使用！！！**



#### iframe ：定义内联的子窗口

- 用于在网页中显示网页？
- `<iframe  src="URL"> </iframe>`  url指向隔离页面的位置？？
- `<iframe src="demo-iframe.html" width="200" height="200"> </iframe>` 规定iframe 的大小
- name属性与链接`<a>` 的target属性相同时，会在子窗口中显示链接的内容



**JavaScript使HTMl页面具有更强的动态和交互性**

**`<!DOCTYPE>`** 声明帮助浏览器正确的显示网页：它为浏览器提供一项信息，即HTML是用什么版本编写的



#### 表单

- 表单元素指的是不同类型的input元素、复选框、单选按钮、提交按钮等





### HTML5 

html5 规定一种通过video元素来包含视频的标准方法

当前，video元素支持三种视频格式：`Ogg, MPEG4, WebM`

`<video src="movie.ogg" control="control"></video> ` control属性：提供添加播放、暂停、音量控件

width、height属性

`<video>与</video> 之间插入的内容是供不支持video元素的浏览器显示的` 

video元素允许多个source元素，也可以链接不同的视频文件，但是将使用第一个识别的视频

`video 属性：autoplay、controls, height, width, loop, preload, src,`



- `<audio> 元素能够播放声音文件或者音频流`



拖放：Drag和drop ：即抓取对象后拖到另一个位置 ？？



**画布** ：canvas用于在网页上绘制图形，使用JavaScript在网页上绘制图像

`<canvas id="myCanvas" width="200", height="100"></canvas>`

所有绘制工作必须在JavaScript中完成

JavaScript使用id来寻找对应的canvas元素



**SVG** 可伸缩矢量图形（Scalable Vector Graphics）

- 用于定义用于网格的基于矢量的图形
- 使用XML格式定义图形
- 图像在放大或者改变尺寸的情况下图形质量不会有损失
- 是万维网联盟的标准

优势：

- 图像可以通过文本编辑器来创建和修改
- 可被搜索、索引、脚本化和压缩
- 是可伸缩的
- 图像可以再任何的分辨绿下被高质量的打印
- 可在图像质量不下降的情况下被放大



**在客户端存储数据**

localStorage:没有时间限制的数据存储

sessionStorage：针对一个session的数据存储

















 







