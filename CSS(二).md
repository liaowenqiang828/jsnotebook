1. IE浏览器的盒模型有什么样的表现？

   IE盒模型中 width=content + padding + border，height = content + padding + border。

2. 让一个块级元素水平居中的方式有哪些？

   - 定宽度：需要谁居中，给其设置margin：0 auto ，使盒子自己居中。

     ``` 
     <style>
       #father {
                width: 500px;
                height: 300px;
                background-color:blue;
       }
       
       #son {
       			width: 100px;
       			heiight: 100px;
       			margin: 0 auto;
       			background-color: green;
       }
     </style>
     
     <div id="father">
       <div id="son">我是水平居中的块级元素</div>
     </div>
     ```

   - 不定宽度：默认子元素的宽度和父元素一样，这时需要设置子元素为display：inline-block； 或display：inline; 即将其转换成行内块级/行内元素，给父元素设置text-align:center;

     ``` 
     <style>
       #father {
                width: 500px;
                height: 300px;
                background-color:blue;
                text-align: center;
       }
       
       #son {
     		   background-color: green;
     		   display: inline;
       }
     </style>
     
     <div id="father">
       <div id="son">我是水平居中的块级元素</div>
     </div>
     ```

   - 使用定位属性：首先设定父元素的相对定位，再设置子元素的绝对定位，设置子元素的left：50%，即让子元素的左上角水平居中。

     ``` 
     <style>
       #father {
                width: 500px;
                height: 300px;
                background-color:blue;
                position：relative;
       }
       
       #son {
       			width: 100px;
       			heiight: 100px;
       		    background-color: green;
       		    position: absolute;
       		    left: 50%;
       		    margin-left: -50px
       }
     </style>
     
     <div id="father">
       <div id="son">我是水平居中的块级元素</div>
     </div>
     ```

   - 使用flexbox布局实现，只需要给待处理的块状元素的父元素添加属性display：flex；justify-content：center;

     ``` 
     <style>
       #father {
                width: 500px;
                height: 300px;
                background-color:blue;
                display: flex;
                justify-content: center;
       }
       
       #son {
       			width: 100px;
       			heiight: 100px;
       			background-color: green;
       }
     </style>
     
     <div id="father">
       <div id="son">我是水平居中的块级元素</div>
     </div>
     ```

     

3. display：none；和visibility：hidden；都是让元素隐藏，有什么区别？

   - visibility：hidden隐藏之后会依旧占据页面空间，但display：none直接不显示，不占用页面空间。

   - visibility具有继承性，给父元素设置visibility：hidden，其子元素也会继承此属性。
   - visibility：hidden不会影响计数器的计数，而display：none则不一样。
   - 在CSS3的transition中支持visibility属性，但不支持display，因为transition可以延迟执行，因此配合visibility使用纯CSS实现hover延时显示效果可以提高用户体验。

4. 请用多种方式实现如下布局，不必填充内容，用背景颜色区分就行：

   - 双列布局：侧边栏固定，主栏目自适应--比如体验课中的首页；

     1.  flex布局

        ```
        <html>
          <head>
            <meta charset="utf-8">
            <title>两列布局，左边固定右边自适应</title>
            <style>
              body {
                height: 100%;
                display: flex;
              }
            .left {
              height: 100%;
              width: 400px;
              background-color: red;
            }
            .right {
              flex: 1;
              background-color: royalblue;
            }
            </style>
          </head>
          
          <body>
            <div class="left">左边固定</div>
            <div class="right">右边自适应</div>
          </body>
        </html>
        ```

        
     2.  左边div绝对定位，右边div设置margin-left

        ``` 
        <html>
          <head>
            <meta charset="utf-8">
            <title>两列布局，左边固定右边自适应</title>
            <style>
              body {
                height: 100%;
                position: relative;
              }
            .left {
              position:absolute;
              top: 0;
              left: 0;
        
              height: 100%;
              width: 400px;
              background-color: red;
            }
            .right {
              margin-left: 400px;
              height: 100%;
              background-color: royalblue;
            }
            </style>
          </head>
          
          <body>
            <div class="left">左边固定</div>
            <div class="right">右边自适应</div>
          </body>
        </html>
        ```

        
     3.  双float + calc()

        ```
        <html>
          <head>
            <meta charset="utf-8">
            <title>两列布局，左边固定右边自适应</title>
            <style>
              body {
                height: 100%;
              }
            .left {
              float: left;
        
              height: 100%;
              width: 400px;
              background-color: red;
            }
            .right {
              float: left;
              width: calc(100% - 400px);
              height: 100%;
              background-color: royalblue;
            }
            </style>
          </head>
          
          <body>
            <div class="left">左边固定</div>
            <div class="right">右边自适应</div>
          </body>
        </html>
        ```

        

   - 三列布局：左右是固定宽度，中间是自适应宽度；

      1. flex布局：将父元素box设置为display：flex

         ```
         <html>
           <head>
             <meta charset="utf-8">
             <title>三列布局，左右两边固定，中间自适应</title>
             <style>
               body {
                 height: 100%;
                 display: flex;
               }
             .left {
               height: 100%;
               width: 400px;
               background-color: red;
             }
             .right {
               float: left;
               width: 400px;
               height: 100%;
               background-color: royalblue;
             }
             .middle {
             flex: 1;
             height: 100%;
             background-color: seagreen;
             }
             </style>
           </head>
           
           <body>
             <div class="left">左边固定</div>
             <div class="middle">中间自适应</div>
             <div class="right">右边固定</div>
           </body>
         </html>
         ```

     	2. 利用绝对定位：center居中并利用margin为左右两边留出位置，左右绝对定位

         ``` 
         <html>
           <head>
             <meta charset="utf-8">
             <title>三列布局，左右两边固定，中间自适应</title>
             <style>
               body {
                 height: 100%;
                 position: relative;
               }
             .left {
               position: absolute;
               left: 0;
               top: 0;
         
               height: 100%;
               width: 400px;
               background-color: red;
             }
             .right {
               position: absolute;
               top: 0;
               right: 0;
         
               width: 400px;
               height: 100%;
               background-color: royalblue;
             }
             .middle {
             margin: 0 400px;
             height: 100%;
             background-color: seagreen;
             }
             </style>
           </head>
           
           <body>
             <div class="left">左边固定</div>
             <div class="middle">中间自适应</div>
             <div class="right">右边固定</div>
           </body>
         </html>
         ```

     	3. 对中间的宽度进行calc计算：三个元素都向左浮动，左右定宽，对中间宽度进行计算，100%宽度减去左右两边宽度。

         ```
         <html>
           <head>
             <meta charset="utf-8">
             <title>三列布局，左右两边固定，中间自适应</title>
             <style>
               body {
                 height: 100%;
               }
             .left {
               float: left;
         
               height: 100%;
               width: 400px;
               background-color: red;
             }
             .right {
               float: left;
         
               width: 400px;
               height: 100%;
               background-color: royalblue;
             }
             .middle {
             float: left;
         
             width: calc(100% - 800px);
             height: 100%;
             background-color: seagreen;
             }
             </style>
           </head>
           
           <body>
             <div class="left">左边固定</div>
             <div class="middle">中间自适应</div>
             <div class="right">右边固定</div>
           </body>
         </html>
         ```

         

5. overflow的auto、hidden、scroll值分别代表什么？

   - 值auto：如果内容不被修剪则正常显示，如果内容被修剪，则浏览器会显示滚动条以便查看其他内容。
   - 值hidden：内容会被修剪，并且被修剪的部分是不可见的。
   - 值scroll：内容会被修剪，但是浏览器会显示滚动条以便查看其余内容。