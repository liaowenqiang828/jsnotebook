- 反转PNG图片的颜色：

  ```
  .white {
  		 filter：invert(100%);
  		 }
  ```

- 全局环境中有不同的宿主对象，浏览器环境中是window，node环境中是global。

- 浏览器中非函数中的this指向window

- 把全局变量window传入匿名函数内缓存起来，避免直接访问，越读取外层的标识符性能越差。

- 非函数内直接使用var声明的变量默认为全局变量，且默认挂在window上作为属性



- 判断this指向谁，看执行时而非定义时，只要函数（function）没有绑定在对象上调用，它的this就是window。





- 浏览器中回到页面顶部快捷键：Home
- 浏览器中回到页面底部快捷键：End



逻辑或“||”运算，用于判断二者选一，如果结果是true，则返回第一个值为真的值，也被称为短路运算符。



字符串是不可变对象，无法对其进行本身进行修改。



- Ubuntu下安装deb类型文件：` sudo dpkg -i  ****.deb`



