adding css to our documnet

`<link rel="stlylesheet" href="style.css">`

we can target multiple selectors at once, by separating the selectors with a comma



`selector{declaration1; declaration2......}`

- 选择器--通常是你需要改变样式的HTML元素。

- 每一条声明由一个属性和一个值组成。

ex:

- `h1{color: red; font-size: 14px;}`

- 如果属性的值为若干个单词，只需要给值添加引号，比如字体

可以对选择器进行分组，共享相同的声明，每个选择器之间逗号隔开

- ``` 
  h1, h2, h3, h4, h5, h6 {
    color: green;
  }
  ```



派生选择器允许你根据文档的上下文关系来确定某个标签的样式

类选择器，以一个点号显示

class也可被用作派生选择器

``` 
.fancy td {
  color: #f60;
  background: #666;
}
上面这个例子中，类名为fancy的更大的元素内部的表格单元会以灰色背景显示橙色文字
```

元素也可以基于它们的类而被选择：

``` 
td.fancy {
  color: #f60;
  background: #666;
}
在上面这个例子中，类名为fancy的**表格单元（td）**将是带有灰色背景的橙色

<td class="fancy">
可以将类fancy分配给任何一个表格元素任意多次。以fancy标注的表格单元<td>都会带有灰色背景
即被限制于被标注为fancy类的表格单元具有该样式效果
```



属性选择器？？？





- 当样式需要应用于很多页面时，外部样式表是理想的选择
- 当单个文件需要特殊样式时，就应该使用内部样式表



可以为所有元素设置背景颜色：background-color: gray; 其默认值为transparent，即透明的效果

所有的背景属性都不能继承！！！



- 把图像放入一个背景，使用background-image属性：
- 必须为该属性设置一个URL值：`body {background-image: url(..........)}`
- 属性background-repeat 可以实现在对背景图片进行平铺
- background-attachment
- background-position



通过文本属性，可以改变文本的颜色、字符间距、对齐文本、装饰文本、对文本进行缩进等等。

` p {text-index: 5em}`  text-index属性可以实现文本缩进，如实现段落首行缩进

text-index 属性无法应用于行内元素

文本对齐属性：text-align, 属性值有：left、right、center、justify水平对齐



将块级元素或表居中，要通过在这些元素上适当的去设置**左、右外边距来实现**



text-decoration属性：文本装饰  underline下划线、overline上划线、line-through贯穿线、none关闭所有装饰，例如去掉超链接的下划线`a {text-decoration: none; }`



字体属性定义文本的字体系列、大小、加粗、风格（如斜体）、变形（如小型大写字母）

有两种不同类型的字体系列名称：

- 通用字体系列
- 特定字体系列

使用font-family 属性指定文本的字体系列

font-weight属性设置字体的粗细

font-size 属性设置文本大小（默认大小是16像素16px=1em）



1em等于当前的**字体尺寸** ：

> 如果一个元素的font-size为16像素，那么对于该元素，1em就等于16像素。在设置字体大小时，em的值会相对于父元素的字体大小改变



#### 链接

链接的特殊性在于能够根据他们所处的状态来设置他们的样式

四种状态：

```
a:link {color: #ff0000; }
a:visited {color: #00FF00; }
a:hover {color: #FF00FF; }
a:active {color: #0000FF; }

为了使定义生效，a:hover 必须位于a:link 和a:visited之后
									a:active必须位于a:hover之后
**具体顺序记忆方式：l(link)ov(visited)e ，h(hover)a(active)te**
```

- a:link ---普通的、未被访问的链接
- a:visited ---用户已访问的链接
- a:hover ---鼠标指针位于链接的上方
- a:active ---链接被点进去时刻

常见设置：

``` 
a:link {text-decoration:none; }
a:visited {text-decoration:none; }
a:hover {text-decoration:underline; }
a:active {text-decoration:underline; }
```



#### 列表

list-style-type 属性用于修改列表项的标志类型：

`ul {list-style-type: square} ` 设置为方块

`ul li {list-style-type: url(.....)}` 使用图像作为标志



#### 表格

border-collapse 属性设置是否将表格边框折叠为单一边框

`border-collapse: collapse`

表格中文段对齐：text-align属性设置水平对齐方式

​									vertical-align属性设置垂直对齐方式

使用caption-side属性设置表格标题位置。



通用选择器：

```
* {

}
```

背景应用于由内容、内边距、边框组成的区域

元素由内向外一次为：内容——内边距——边框——外边距



如果你希望出现一个边框，那么一定要声明一个边框样式



外边距合并？？？



### 定位

一切皆为框

div h1 p 元素常常被称为跨级元素，这意味着这些元素显示为一块内容，即块框。

与之相反

span strong等元素被称为行内元素，他们的内容在行内显示，即行内框。



使用display属性改变生成的框的类型

`disply: block--让行内元素显示得像块级元素，inline--相反，**none**让元素没有框，即该框和其内容不在显示，页不占用文档中的内容`

**块级框**从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。

行内框在一行中水平布置。可以使用水平内边距、边框和外边距调整它们的间距。但是，垂直内边距、边框和外边距不影响行内框的高度。由一行形成的水平框称为*行框（Line Box）*，行框的高度总是足以容纳它包含的所有行内框。不过，设置行高可以增加这个框的高度。

#### position

static 

relative

absolute

fixed



float 浮动？？？？？



多类选择器？？？？



ID选择器前面包含一个#号 `#intro {font-size: 10px; }`









