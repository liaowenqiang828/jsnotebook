### JavaScripts

- the javascript is executed by the browser's javascript engine, after the HTML and CSS have been assembled and put together into a web page.

- in most cases the code in each tab is run completely separately, and the code in one tab cannot directly affect the code in another tab.



- javascript generally runs in order, from top to bottom.

- Client-side code is code that is run on the user's computer

- the dynamic refers to the ability to update the display of a web page/app to show different things in different circumstances, generating new content as required.



- all the scripts with the **defer** attribute will load in the order they appear on the page.
- its best to use async when the scripts in the page run independently from each other and depend no on other script on the page.



internal javascript 

- ```
  <script>
  
  // javascript goes here
  
  </script>
  ```

external javascript

- ```
  <script src="script.js" defer></script>
  ```

  

内部引用：

```
<html>
  <head>
    <script>document.write("hello world");</script>
  </head>
  
  <body>
    //<script>document.write("hello world");</script>  引入部分也可以放在<body>里面。
  </body>
</html>
```

外部引用：

```
<html>
  <head>
    <script src="my-js.js" defer></script>
  </head>
  
  <body>
  </body>
</html>

my-js:
document.write("hello world");
```



Number:

- js 不区分整数和浮点数，统一用Number表示。

字符串：

- 以单引号或者双引号括起来的任意文本。

布尔值：

- true  false
- 布尔值和布尔代数表示完全一致
- && 与运算
- || 或运算
- ！ 非运算

比较运算符：

- == 会自动转换数据类型再进行比较；
- === 不会自动转换类型，如果数据类型不一致，返回`false` ,否则再进行下一步比较。
- 始终坚持使用 ===
- NaN 这个特殊的Number与其他所有的值都不相等，包括他自己。
- 唯一能判断NaN的方法是`isNaN()`函数
- 注意浮点数比较，运算过程会产生精度误差，比较时比较差值是否小于某一个阙值
- null 表示一个空值
- undefined 表示未定义， 仅仅在判断函数参数是否传递的情况下有用



数组：

- 数组是一组按顺序排列的集合，集合的每个值成为元素 js的数组可以包含任意数据类型
- 数组用[]表示，元素用,隔开。
- 可以通过Array（）函数创建数组



对象：

- 对象是一组由键-值组成的无序集合
- 键都是字符串类型，值可以是任意类型
- 每个键又称为对象属性
- 要获取一个对象的属性，用`对象变量.属性名` 的方式

变量：

- 变量名不能以数字开头

- 申明一个变量用`var`语句： `var  a ; ` 

- 使用等号= 进行变量赋值：`var a = 123;` 

- 这种变量本身类型不固定的语言称为动态语言

- 如果要显示变量内容，可以用`console.log(x);`

script模式：

- 如果一个变量没有通过`var`申明就使用，那么该变量就自动被申明为全局变量；



1. JS中有哪些数据类型？
   	- Boolean
      	- Null
         	- Undefined
            	- Number
               	- BigInt
                  	- String
                     	- Symbol
                        	- Object
2. JS Object 数据类型和其他原始类型有什么区别？
    - 声明变量时不同的内存分配
      	- 原始类型：存储在栈（stack）中的简单数据段，它们的值直接存储在变量访问的位置。
      	- 引用类型：存储在堆（heap）中的对象，存储在变量处的值是一个指针，指向存储对象的内存地址。
    - 不同的内存分配机制带来的不同的访问机制
      	- 在js中不允许直接访问保存在堆内存中的对象，所以在访问一个对象时，首先得得到的是这个对象在堆中的内存地址，然后再按照这个地址去获得这个对象中的值。
      	- 原始类型的值可以直接被访问。
   - 复制变量时的不同：
     	- 原始类型值：在将一个保存着原始值的变量复制给另一个变量时，会将原始值的副本赋值给新变量，此后这两个变量是完全独立的，他们只是拥有相同的value而已。
     	- 引用类型值：在将一个保存着对象内存地址的变量复制给另一个变量时，会把这个内存地址赋值给新变量，也就是说这两个变量都指向了堆内存中的同一个对象，他们中任何一个作出的改变都会反映在另一个身上。
   - 参数传递的不同：
     	- 原始类型值：只是把变量里的值传递给参数，之后参数和这个变量互不影响。
     	- 引用类型值：对象变量它里面的值是这个对象在堆内存中的内存地址。

3. 谈谈你对“变量提升”的理解

	- 对于一个变量声明语句，如`var a =1; ` 在代码解析过程的编译阶段，这个代码语句相当于两个语句：` var a; 和a=1;` 并且`var a` 这个语句会被提升到当前执行环境的最顶端，即先执行前半部分的代码。

4. 分别指出以下运算的执行结果

```
typeof undefined;   ---->undefined
typeof true;  ----->Boolean
typeof 42;  ---->Number
typeof "42";  ---->String
typeof {lift: 42};  ---->Object
```



- let 声明的变量只在let命令所在的代码块内有效。

- 函数内使用var声明的变量只能在函数内部访问，如果不使用var则是全局变量。
- 使用var在块中重新声明变量，也会重新声明快外的同名变量，而let则解决了这个问题。



运算符解题：

1. num++ 与++num之间的区别：

   	- num++ 在做计算时会先将自身的值用作计算，当前这一步的计算完成后再在自身上加1；
      	- ++num则是在计算时先将自身值加1，然后再完成当前这一不的计算操作。

2. 利用Math方法对得到的结果进行保留两位小数、四舍五入、向上取整、向下取整等操作：

    - 四舍五入：` Math.round(3.4); //输出为3`， `Math.round(3.5)； //输出为4`
      	- 保留两位小数：`Math.round(3.3533*100)/100; //输出结果为3.35`
         	- 向下取整：`Math.floor(3.5); //输出为3`
            	- 向上取整：`Math.ceil(3.5); //输出为4`

3. 分别指出以下运算的结果：

   ```
   42 == "42"; //true
   42 === "42"; //false
   "foo" == ["foo"]; //true
   "0" == false; // true
   "" == []; //true
   "" == 0; //true
   [] == 0; //true
   "true" == true; //false
   0 == "\n"; //true
   0 == null; //false
   false == {}; //false
   0.1+0.2 == 0.3; //false
   ```

4. 分别指出以下四处变量a对应的值，并说明为何等于该值。

   ```
   var a = 42;
   
   a++; //42, 变量a被初始化为42，而a++ 是先计算a的值，之后再进行自增加1操作
   a; //43，上一个a++操作之后，变量a的值增加了1
   
   ++a; //44， 上一个操作后变量a的值为43，而++a运算是先进行自增1操作，再进行a相关计算
   a; //44， 上一步运算之后a值变为44
   ```

5. 分别指出以下四处变量a对应的值，并说明为何等于该值。

   ``` 
   var a =42 & 24;
   a值为8，&运算为位与运算，42的二进制表示为：101010, 24的二进制表示为：11000，
   进行与运算操作，对应位同时为1则为1，否则为0，结果是001000，十进制表示为8。
   
   a = a && 34;
   a的值为34，首先a&&34的运算结果为true，而当数值参与逻辑与运算，结果为true时，返回第二个为真的值，就是34
   
   a = a | 54;
   a 的值为54，|是位或运算，等号右边a=34，二进制表示为：100010, 54二进制表示为：110110，二者进行或运算，相对应的位其中任意一位是1时结果为1，否则为0，结果为110110，十进制表示为54
   
   a = a || 68;
   a的值为54，首先a||68的运算结果为true，而当数值参与逻辑或运算，结果为true时，返回第一个为真的值，就是54
   ```

   

- 当数值参与逻辑与&&运算时，结果为true，那么返回的会是第二个为真的值；如果结果为false，返回的会是第一个为假的值。
- 当数值参与逻辑或||运算时，结果为true，那么返回的会是第一个为真的值；如果结果为false，返回的会是第二个为假的值。



1. ``` 
   var score;
   function score_level(score){
       if (score >= 95){
         console.log("卓越");
       }
       else if (score >= 85){
         console.log("优秀");
       }
       else if (score >= 75){
         console.log("一般");
       }
       else if (score >= 60){
         console.log("及格");
       }
       else{
         console.log("不合格")
       }
   }
   
   score_level(77); // 输出一般 
   ```

2. ```
   var operator = "-";
   var x = 10, y = 8;
   
   switch(true) {
     case operator == "+":
       console.log(x + y);
       break;
     case operator == "-":
       console.log(x - y);
       break;
     case operator == "*":
       console.log(x * y);
       break;
     case operator == "/":
       console.log(x / y);
       break;
     case operator == "%":
       console.log(x % y);
       break;
     default:
       console.log("请输入正确的运算符：");
   }
   
   operator == "-"时， x - y = 2,输出结果为2
   ```

3. ``` 
   var i = 1;
   var result = 0;
   while (i <= 100) {
     if (i % 10 == 3){
       i += 1;
       continue;
     }
     
     result += i;
     i += 1;
   }
   console.log(result);
   
   结果输出为4570；
   ```

4. ``` 
   var str = "";
   for (var i = 6; i >0; i--) {
     for (var j =1; j <= i; j++) {
       str +=  "* ";
       if  (j === i) {
         str += "\n"
       }
     }
   }
   console.log(str);
   ```

5. ``` 
   var str = "";
   
   for (var i = 1; i <= 9; i++) {
     for (var j = 1; j <= i; j++) {
       str += i + "*" + j + "=" + i*j + " ";
       if (i === j) {
         str += "\n";
       }
     }
   }
   console.log(str)
   ```

6. 



#### 函数与作用域

1. 创建函数有哪些方法？分别有什么特点？

   -  声明式：

     ``` 
     function func (x, y){
     		return x + y;
     }
     ```

     解析器会先读取函数声明，并使其在执行任何代码之前可以访问。

   -  匿名式：

     ``` 
     var func = function (x, y){
     		return x + y;
     }
     ```

     必须等到解析器执行到它所在的代码才会真正被解释执行。

   - Function 式：

     ``` 
     var func = new Function('x', 'y', 'return x + y;')
     ```

   

2. 见如下代码，b会打印出什么？

   ``` 
   (function() {
     var a = b = 5;
   })();
   console.log(b)
   
   b会打印出5，(function(...))();相当于调用函数自身的调用，在函数内部，变量b被赋值为5，并且变量b是用var声明的，会被声明为全局变量，在函数作用域外可以访问。
   ```

   

3. 编写一个函数，实现一个输出n遍连接后的str功能，如下：

   ```
   function repeatStr(str, num) {
     var result = "";
     for (var i = 1; i <= num; i++) {
       result += str;
     }
     return result;
   }
   
   var a = repeatStr("hello", 4);
   console.log(a)
   结果输出为：'hellohellohellohello'
   ```

   

4. 以下代码执行结果是：

   ```
   function test() {
     console.log(a);
     console.log(foo());
     
     var a = 1;
     function foo() {
       return 2;
     }
   }
   test()
   结果输出为：undefined  // 变量a提升到了函数内部上方，相当于还没有初始化，此时打印a就是undefined
                              2 // 函数foo()提升到test()函数内部的最上方，其返回结果为2，所当打印foo()函数时返回2.
   ```

   

5. 以下代码执行结果是：

   ```
   function foo() {
     return 1;
   }
   var foo;
   console.log(typeof foo);
   结果输出为： function  // 
   
   function foo() {
     return 1;
   }
   var foo = 1;
   console.log(typeof foo);
   结果输出为：number //
   
   ```

   

6. 编写一个函数，实现一个乘法计算器：无论输入多少个数字参数，最终都返回参数的乘积。例如：

   ```
   function multiplicationCalculator() {
     var result = 1;
     for (var i = 0; i < arguments.length; i++) {
       result *=  arguments[i];
     }
     return result;
   }
   
   var a = multiplicationCalculator(1, 2 ,5, 6);
   console.log(a);
   结果输出为：60
   ```

   

7. 编写一个函数，实现如下功能：`var a = add(2)(3)(4); // 9`, 提示：2 + 3 + 4 = 9.

   ``` 
   
   
   
   
   ```

   



1. 有哪些创建数组的方法？

   	- 第一种使用Array构造函数：` var colors = new Array();` 即创建了一个名为colors的空数组；
      	- 第二种使用数组字面量表示法：` var colors = ["Red", "blue", "green"]` 直接使用一对方括号创建一个数组，在方括号中可以初始化数组的项，项之间用逗号隔开。

2. 判断下列变量是不是数组类型。

   ``` 
   var a = '[a, b, c, d]'; // 不是数组类型，而是字符串类型
   var b = [1, 2, 3, 4]; // 是数组类型
   ```

3. 编写程序，将下面数组中的每一项都乘以2.

   ``` 
   var a = [1, 2, 3, 4, 5];
   
   var  a = [1, 2, 3, 4, 5];
   var  a_multiple_2  = a.map(function(item, index, array) {
     return item * 2;
   });
   
   console.log(a_multiple_2);
   结果输出为 [2, 4, 6, 8, 10] 
   
   ```

4. 编写程序，按下面的要求输出结果。

   ``` 
   var colors = ["Red", "Green", "White", "Black"];
   
   var case1 = colors.join(" ");
   console.log(case1); //输出为：'Red Green White Black'
   
   var case2 = colors.join("+");
   console.log(case2); //输出为：'Red+Green+White+Black'
   
   var  case3 = colors.toString();
   console.log(case3); // 输出为：'Red,Green,White,Black'
   
   ```

5. 编写程序，将下面数组中的数字按从大到小的顺序排列。

   ``` 
   ar a = [5, 1, 8, 10, 4];
   
   function sorting (arr) {
     for (var i = 0; i < arr.length; i++){
       for (var j = 0; j < arr.length - 1 - i; j++){
         if (arr[j] < arr[j + 1]){
           var tempValue = arr[j];
           arr[j] =  arr[j + 1];
           arr[j + 1] = tempValue;
         }
       }
     }
     return arr;
   }
   sorting(a);
   
   结果输出为：[10, 8, 5, 4, 1]
   ```

6. 编写程序，找出下列数组中出现频率最高的元素。

   ``` 
   var a = [3, 'a', 'a', 'a', 2, 3, 'a', 3, 'a', 2, 4, 9, 3];
   
   var a = [3, 'a', 'a', 'a', 2, 3, 'a', 3, 'a', 2, 4, 9, 3];
   
   function maxCountElement(arr) {
     var obj = {};
     for (var i = 0; i < arr.length; i++) {
       var key = arr[i];
       if (obj[key]){
         obj[key]++;
       }
       else {
         obj[key] = 1;
       }
     }
   
     var maxCount = 0;
     var maxElement = arr[0];
     for (var key in obj) {
       if (maxCount < obj[key]){
         maxCount = obj[key];
         maxElement = key;
       }
     }
     return maxElement;
   }
   
   maxCountElement(a) ;
   结果输出为'a'
   ```

   



#### 函数

- 每个函数都有return
- 如果你不写return，就相当于写了return undefined



- 词法作用域：变量的作用域是在定义时决定的，而不是执行时决定的，也就是说词法作用域取决于源码，通过静态分析能够确定，因此词法作用域也叫做静态作用域。with和eval除外。



- 如果一个变量没有经过显式声明或者出现赋值语句（可以看做隐式声明），那么它就是未声明的，这个时候我们使用它就会报错‘未定义’或‘not defined’，实际上可以理解为‘未声明’。
- 如果变量经过显式声明但是没有执行过赋值语句，那么他是‘未定义’的，也就是确实意义上的‘undefined’。我们可以使用它，但是默认值是‘undefined’。



- 函数内部如果不加关键字var而定义变量，默认为全局变量。



- 在同一个方法中，同名的实参、形参、变量之间是引用关系，也就是js引擎的处理是同名变量和实参都引用同一个内存地址。
- js引擎变量查找规则，首先在当前执行环境是Active Object中寻找，没找到，则顺着执行环境中属性指向的Scope Chain 指向的Active Object中寻找，一直到Global Object（Window）。



#### 闭包 

如果一个函数，使用了它范围外的变量，那么（这个函数+这个变量）就叫做闭包。

在js中，闭包就是一个匿名函数，被当作另一个函数的返回值。

闭包的核心作用是：在函数的外部访问函数的局部变量。

#### 如何使用闭包

1. 用外层函数包裹要保护的变量和内层函数
2. 外层函数将内层函数返回到外部
3. 调用外层函数，获得内层函数对象，保存在外部变量中---形成了闭包。

#### 回调

- 被当做参数的函数就是回调，有同步回调、异步回调

#### 为什么慎用闭包

闭包形成的原因是外层函数调用后，外层函数的函数作用域对象无法释放，被内层函数引用着，无法自动释放内存。



链式作用域（Chain Scope），子对象会一级一级的向上寻找所有父对象的变量，父对象的所有变量对子对象都是可见的，反之则不成立。



一个函数可以访问在它的调用上下文中定义的变量，这个就是词法作用域。





### JavaScript对象

1. 创建对象有哪些方式？

   - 第一种使用new操作符后跟Object构造函数：

     ``` 
     var person = new Object();
     ```

     

   - 第二种使用对象字面量表示法：

     ``` 
     var person = {
       name: "Nichlolas",
       age: 32
     }
     ```

     

2. 编程程序完成下列需求：

    - 创建一个空对象，变量名为user；

      ``` 
      var user = {};
      ```

    - 添加一个name属性，并设置值为John；

      ``` 
      user.name = "John";
      ```

    - 添加一个surname属性，并设置值为Mike；

      ``` 
      user["surname"] = "Mike";
      ```

    - 将name属性值改为Peter；

      ``` 
      user.name = "Peter";
      ```

    - 删除user的name属性；

      ``` 
      delete user.name;
      ```

      

3. 代码如下：

   ``` 
   var a = {
     name: "xiaoming",
     age: 32
   };
   var b = a;
   b.age = 18;
   console.log(a.age);
   // 18 变量b与变量a具有相同的一个对象引用，当执行b.age = 18时，对象属性值发生改变，变量a也指向着这个对象，所以打印age属性值为修改后的值。
   
   ```

4. 有如下几段代码，请分别指出代码中console打印的值和为什么打印该值？

   ``` 
   var name = 'window-Jack';
   var person = {
    name : 'person-Rose',
    greeting: function() {
      console.log('Hi! I\'m ' + this.name + '.');
    }
   }
   var greeting = person.greeting;
   greeting();
   // Hi! I'm window-Jack.
   // 全局变量greeting指向对象person内的greeting方法函数，当直接调用greeting时，为指定当前函数调用的对象，那么会默认指定成window，所以this.name会返回全局变量中name变量的值"window-Jack".
   ```

   ``` 
   var name = 'window-Jack';
   var person = {
    name : 'person-Rose',
    greeting: function() {
      console.log('Hi! I\'m ' + this.name + '.');
    }
   }
   var greeting = person.greeting.bind(person);
   greeting();
   // Hi! I'm person-Rose.
   // 这里使用了bind，用来创建一个指定了this的函数，根据bind()方法的参数，指定的this是person对象，所以当打印this.name的值时会返回person.name的值："peson-Rose".
   ```

   ``` 
   var name = 'window-Jack';
   var person = {
    name : 'person-Rose',
    greeting: function() {
      console.log('Hi! I\'m ' + this.name + '.');
    }
   }
   person.greeting.apply(this);
   // Hi! I'm window-Jack.
   // 这里使用了apply方法，调用一个具有给定this值的函数，这个程序中，person.greeting.apply(this)最开始的this是person对象，在使用了apply后，apply方法用this所对应的对象跟person对象进行替换，而在当前作用域中this代表的是window作用域，所以返回window.name 值为window-Jack.
   ```

   ``` 
   var name = 'window-Jack';
   var person = {
    name : 'person-Rose',
    greeting: function() {
      console.log('Hi! I\'m ' + this.name + '.');
    }
   }
   person.greeting.call(this);
   //Hi! I'm window-Jack.
   //与使用apply方法类似，这个程序中使用了call方法，将当前作用域中对应的this替换调person对象，再执行函数语句，而this对应window，所以返回window.name 值为window-Jack.
   ```



5. 编写程序实现下列需求：请计算下面fruit对象公有多少个水果，因该输出50.

   ``` 
   var fruit = {
     apple: 20,
     pear: 20,
     peach: 10
   }；
   
   function calFruit(fruit) {
     var sum = 0;
     for(var i in fruit) {
       sum += fruit[i];
     }
     return sum;
   }
   
   var fruitNum = calFruit(fruit);
   console.log(fruitNum);
   // 输出为50.
   ```

6. 什么是JSON?JSON与JavaScript的关系以及JSON的适用场景是什么？

   	- JSON（JavaScript Object Notation）is a standard text-based format for representing structured data based on JavaScript object syntax.
   - JSON是一种存储数据的类型，它是独立于语言存在的，只是在不同的编程语言中，对这种数据的实现不同，JSON这种数据格式用JavaScript对象字面量的表示方法进行描述，那么描述JSON的语法就是JavaScript对象字面量表示语法的一个子集。
    - 适用场景：
      	- 原生态JSON的使用场景--JSON.stringify(Object)
      	- jQuery中的使用场景--$.parseJSON(JSONString);



- 对于全局的方法调用，this指向的是全局对象window，即调用方法所在的对象。

- 如果函数作为对象的方法调用，this指向的是这个上级对象，即调用方法的对象。

  ``` 
  function showName() {
    console.log(this.name);
  }
  var obj = {};
  obj.name = "ooo";
  obj.show = showName; //对象obj的方法show的具体实现是函数showName;
  obj.show();// 对象调用show方法，就等于执行函数showName;
  // ooo
  ```

- 构造函数中的this指向新创建的对象本身

  ``` 
  function showName() {
    this.name = "show name function";
  }
  var obj = new showName(); // 创建一个新对象，在构造函数里面，对当前对象进行初始化，此时this指向新建的对象obj
  console.log(obj.name), // show name function
  ```

- call 方法：调用一个对象的方法，以另一个对象替换当前对象。



- apply方法：应用某一对象的方法，用另一个对象替换当前对象。

























































代码重构第二题：
``` var sentence = "good afternoon, mr mike.";

function sentenceStartWithUpperCase(str) {
  var newArr1, newArr2 = [];
  newArr1 = str.split(" ");
  for (var i = 0; i < newArr1.length; i++) {
    newArr2.push(newArr1[i][0].toUpperCase(0) + newArr1[i].substring(1));
  }
  return newArr2.join(" ");
}

var sentenceStartWithUpperCaseResult = sentenceStartWithUpperCase(sentence);
console.log(sentenceStartWithUpperCaseResult);
// 输出结果：Good Afternoon, Mr Mike.
```

第三题重构：

``` 
var money = "￥ 20";

function getMoney(money) {
  var arr = money.split("￥");

  return parseInt(arr[1].trim());
}

var moneyValue = getMoney(money);
console.log(moneyValue);
// 输出为20
```



第四题重构：

``` 
function toCamelStyle(str) {
  if (str === null) {
    console.log("input right strings");
    return;
  }

  var i = 1;
  var arr = [str[0]]; // 第一个字母始终都会保持原型

  while (i < str.length) {
    if (str[i] != "_") {
      arr.push(str[i]);
      i += 1;
    }
    else {
      arr.push(str[i + 1].toUpperCase());
      i += 2;
    }
  }
  return arr.join("");
}

var camelStyleString = toCamelStyle("_a_b_c_d_ef");
console.log(camelStyleString);
//输出为_aBCDEf
```



array

第四题重构：

``` 
var colors = ["Red", "Green", "White", "Black"];

function joinArrayElement(array, seperator) {
  switch (seperator) {
    case (" "):
      console.log(array.join(" "));
      break;

    case ("+"):
      console.log(array.join("+"));
      break;

    case (","):
    console.log(array.toString());
    break;

    default:
      console.log("Please input right array and seperator like  ' ', '+', ','" );
  }
}
var seperator = " ";
joinArrayElement(colors, seperator);
// 输出结果为： Red Green White Black
```

第五题重构：

``` 
var a = [5, 1, 8, 10, 4];

function arraySortFromLargeToSmall(array) {
  for (var i = 0; i < array.length; i++) {
    for (var j = 0; j < array.length - 1 - i; j++) {
      if (array[j] < array[j + 1]) {
        var temp = array[j];
        array[j] = array[j + 1];
        array[j + 1] = temp;
      }
    }
  }
  return array;
}

var arraySorted = arraySortFromLargeToSmall(a);
console.log(arraySorted);
//输出为：[10, 8, 5, 4, 1]
```

第六题重构：

``` 
var a = [3, "a", "a", "a", 2, 3, "a", 3, "a", 2, 4, 9, 3];

function maxCountElement(array) {
  var tempObj = {};
  for (var i = 0; i < array.length; i++) {
    var key = array[i];
    if (tempObj[key]) {
      tempObj[key]++;
    }
    else {
      tempObj[key] = 1;
    }
  }

  var maxCount = 0;
  var maxElement = array[0];
  
  for (var key in tempObj) {
    if (maxCount < tempObj[key]) {
      maxCount = tempObj[key];
      maxElement = key;
    }
  }
  return maxElement;
}

var maxElementOfArray = maxCountElement(a);
console.log(maxElementOfArray);
// 输出结果为：a
```



