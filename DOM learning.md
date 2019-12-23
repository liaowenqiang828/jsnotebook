除了解析HTML结构和CSS样式外，浏览器还创建了 文档对象模型 ，也就是DOM.

DOM模型允许JavaScript以对象的形式访问网站文档中的文本内容和元素。

- DOM是关于如何获取、修改、添加和删除HTML元素的标准。
- 通过节点的innerHTML属性来访问文本节点的值



### 作业一

1. 编写一个模拟用户登录的功能，正确的账号密码均为 123，页面需要两个 input 节点和一个 button 节点。要求：

   - 点击 button 时需要判断用户输入的账号密码是否为 123 ，并给予相应的提示（方式不限）；
   - 如果账号或密码错误，将密码所在的 input 节点中的内容清空；

   ``` html
   <!DOCTYPE html>
   <html>
     <head>
       <script>
         function login() {
           var account = document.getElementById("account").value;
           var password = document.getElementById("password").value;
   
           if (account === "123" && password === "123") {
            window.location.href="https://school.thoughtworks.cn";
           }
           else {
             document.getElementById("account").value="";
             document.getElementById("password").value="";
           }
         }
       </script>
     </head>
   
     <body>
       <form>
         账号：<input type="text " name="账号：" id="account" />
         密码：<input type="text" name="密码：" id="password" />
         <input type="button" value="登录" onclick=javascript:login() />
       </form>
     </body>
   </html>
   ```

   

2. 编程实现以下功能：

   	- AC1: 在页面上有一个矩形区域（宽：1000px ，高： 800px），容器里面会有两个 div 元素(宽：80px ，高：80px)，一个背景色为绿色，一个背景色为黄色
   	- AC2: 其中绿色的 div 可以被拖拽，但是只能在矩形区域里面移动，不可超出矩形区域
   	- AC3: 当两个 div 元素碰撞在一起的时候，黄色的div变成蓝色

   ``` html
   <!DOCTYPE html>
   <html>
     <head>
       <meta charset="utf-8">
       <title>square-move</title>
       <link rel="stylesheet" href="./square-move.css" />
     </head>
   
     <body>
       <div id="gray-bg">
         <div id="yellow-square"></div>
         <div id="green-square" draggable="true"></div>
       </div>    
       <script>
           var moveElem = document.getElementById("green-square");
     
           var dragging;
           var tLeft, tTop;
     
           document.addEventListener("mousedown", function(e) {
             if (e.target == moveElem) {
               dragging = true;
               var moveElemRect = moveElem.getBoundingClientRect();
               tLeft = e.clientX - moveElemRect.left;
               tTop = e.clientY - moveElemRect.top;
             }
           });
         document.addEventListener("mouseup", function(e) {
           dragging = false;
         });
     
         document.addEventListener("mousemove", function(e) {
           if (dragging) {
             var moveX = e.clientX + tLeft - 220;
             var moveY = e.clientY - tTop;
   
             moveElem.style.left = moveX + "px";
             moveElem.style.top = moveY + "px";
           }
           
           var colorChange = document.getElementById("yellow-square");
           var colorChangeRect = colorChange.getBoundingClientRect();
   
           var colorChangeX = colorChangeRect.left;
           var colorChangeY = colorChangeRect.top;
   
           if ((moveElem.style.left >= ((colorChangeX - 80 - 183)+ "px") && moveElem.style.left <= ((colorChangeX + 80 - 183) + "px")) 
           && (moveElem.style.top >= ((colorChangeY-80) + "px") && moveElem.style.top <= ((colorChangeY + 80) + "px"))) {
             colorChange.style.backgroundColor = "blue";
           }
   
           if (moveElem.style.left < (0 + "px")) {
             moveElem.style.left = 0 + "px";
           }
           if (moveElem.style.left > (920 + "px")) {
             moveElem.style.left = 920 + "px";
           }
         });
   
       </script>
   
     </body>
   </html>
   ```

   



1. 如果一个HTML元素触发事件，那么这个事件就会在DOM树中的触发节点和根节点之间按照一定的顺序传播，所有经过的节点都会接收到被触发的事件，这个传播过程称之为事件流。

2. 事件冒泡：

   ​	     所谓的事件冒泡就是当一个元素触发一个事件，事件会像是水泡一样，从触发元素向它的所有父节点传播，一直到根节点都会接收到此事件，如果父元素中注册了相应的事件处理函数，那么尽管事件在子节点触发的，在父元素上注册的事件处理函数同样会被触发

3. 事件捕获：

   ​	    事件捕获和事件冒泡恰好相反，当点击一个元素的时候，事件传播的方向是从根元素到触发元素，IE浏览器并不支持，为了跨浏览器支持，所以默认情况下一般都是使用冒泡型事件处理模型。

   ​	    

4. DOM0事件 和 DOM2事件：

   ​	DOM0的事件绑定方法只能给一个事件绑定一个响应函数，重复绑定会覆盖之前的绑定。

   ​    DOM2则可以给一个元素绑定多个事件处理函数。

   ​	             以下为两种绑定模式：

   ```
   var btn = document.getElementById("submit");
   // DOM0事件
   btn.onclick = onClickFn;
   //DOM2事件
   btn.addEventListener("click", onClickFn, false)
   ```

5. Js冒泡机制是指如果某元素定义了事件A，如click事件，如果触发了事件之后，没有阻止冒泡事件，那么事件将向父级元素传播，触发父类的click函数。

6. 冒泡事件：事件开始由最具体的元素接受。

7. 事件代理：事件在冒泡的过程中会上传到父节点，因此可以把子节点的监听函数定义在父节点上，由父节点的监听函数统一处理多个子元素的事件，这种方式称为事件代理。

8. 



- clientX/Y ：获取到的是触发点相对浏览器可视区域左上角距离，不随页面滚动而改变。
- pageX/Y ：获取到的是触发点相对文档区域左上角距离，会随页面滚动而发生改变。
- offsetX/Y：获取到的是触发点相对于被触发DOM的左上角距离。
- layerX/Y:获取到的是触发点相对被触发DOM的左上角距离。
- screenX/Y: 获取到的是触发点相对于显示器屏幕左上角的距离，不随页面滚动而变化。

！[鼠标事件坐标](/home/lwq/图片/鼠标点击位置.png) 























