1. CSS的引入方式有哪些？

   - 外部样式表：`<link rel="stylesheet" type="text/css" href="mystyle.css" />` 浏览器会从外部文件mystle.css 中读取样式声明。
   - 内部样式表：使用<style>标签在文档头部定义内部样式表。
   - 内联样式：在相关的标签内使用样式（style）属性。

2. 简述CSS选择器的权重计算。

   - 第一等：代表内联式，如style=" "， 权值为1000；
   - 第二等：代表ID选择器，如#content，权值为0100；
   - 第三等：代表类，伪类和属性选择器，如.content，权值为0010；
   - 第四等：代表类型选择器和伪元素选择器，如div p, 权值为0001；
   - 通配符、子选择器、相邻选择器等，如*、>、+,权值为0000；

3. 给一个p元素的文字设置文字居右。

   - `p {text-align: right; }`

4. 链接a元素的伪类有哪些，分别代表什么状态？

   ``` 
   a:link  -- 表示未访问的链接;
   a:visited --表示已访问的链接；
   a:hover --鼠标移动到链接；
   a:active --链接被激活。
   ```

5. 初始化列表样式怎么设置？

   - 使用属性list-style-type 设置列表项的标志类型如：`ul {list-style-type: square; }`
   - 使用属性list-style-image将一个图像设置为列表项的标志如：`ul {list-style-image: url(.......)}`
   - 使用属性list-style-position确定标志出现在列表内容之外还是列表内容之内如：`ul {list-style-position: inside}`
   - 使用属性list-style将以上三个属性简写在一起如：`li {list-style: url(....) square inside`

6. 假设元素设置了如下样式，怎么用background简写？

   - ``` 
     div {
     		background: red url(./static/images/banner_bg.png no-repeat center 80%)
     }
     ```

7. 怎么去掉input元素focus后的蓝色模糊框？

   - ```
     input {
     border: 0; 
     outline: none;
     }
     ```

8. 用border实现如图效果，颜色不限。

   - ``` 
     <!DOCTYPE>
     <html>
       <head>
       <title>画三角形</title>
       <meta charset="utf-8">
       <style >
         div.left {
                 position: absolute;
                 top: 0;
                 left: 0;
                 width: 0;
                 height: 0;
                 border: 40px solid;
                 border-color: transparent transparent transparent red;
               }
               div.up {
                 position: absolute;
                 top: 0;
                 left: 100px;
                 width: 0;
                 height: 0;
                 border: 40px solid;
                 border-color: blue transparent transparent;
               }
               div.right {
                 position: absolute;
                 top: 0;
                 left: 200px;
                 width: 0;
                 height: 0;
                 border: 40px solid;
                 border-color: transparent green transparent transparent;
       </style>
       </head>
     
       <body >
         <div class="left"></div>
         <div class="up"></div>
         <div class="right"></div>
       </body>
     
     </html>
     
     
     图形链接：https://liaowenqiang828.github.io/test-example-triangle/
     ```

     