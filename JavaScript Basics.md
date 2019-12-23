# JavaScript Basics

[toc]

#\[General\] JS intro

In HTML, JavaScript code must be inserted between`<script>` and `</script>` tags.

Old JavaScript examples may use a type attribute: `<script type="text/javascript">`.

Scripts can be placed in the `<body>`, or `<head>` section of an HTML page, or in both.

```javascript
<script src="https://www.w3schools.com/js/myScript1.js"></script>
```

用浏览器console对code进行实时的调试，快捷键`option`+`command`+`J`

进入浏览器开发者界面elements，快捷键`option`+`command`+`I`



One of many JavaScript HTML methods is `getElementById()`.

```javascript
document.getElementById("demo").innerHTML = "Hello JavaScript";
```

- Writing into an HTML element, using `innerHTML`.
- Writing into the HTML output using `document.write()`.
- Writing into an alert box, using `window.alert()`.
- Writing into the browser console, using `console.log()`.

## 1. Variables

JS是弱类型语言或者动态类型语言，所以不用提前声明变量的类型。微软的typeScript在JS的基础上增加了`isDone:` ，给定类型。

- | `var` | `let` | `const`            |
  | ----- | ----- | ------------------ |
  | 变量  | 变量  | 常量，不允许修改值 |

```js
for (var i = 0; i <10; i++) {
  //statements
} //var定义的是全局变量（假设这个for循环不在任何函数内）
for (let i = 0; i <10; i++) {
  //statements
}//let定义的是局部变量，在for循环外面无法引用
```

- 函数声明优先于变量声明。但是**函数声明提升不会被变量声明覆盖，但会被变量赋值覆盖。**

```js
function a() {return 2};
var a;
typeof a; //function 这里就是虽然var a在下面，但不会覆盖上面的function，因为没有赋值

function b() {return 3};
var b = 2;
typeof b; //number
```



- 创建变量的时候如果要给个类型，建议使用：

  Use object literals `{}` instead of `new Object()`.

  Use string literals `""` instead of `new String()`.

  Use number literals `12345` instead of `new Number()`.

  Use boolean literals `true / false` instead of `new Boolean()`.

  Use array literals `[]` instead of `new Array()`.

  Use pattern literals `/()/` instead of `new RegExp()`.

  Use function expressions `() {}` instead of `new Function()`.


- `var` creates new variable；`new` creates new object. object can not be compared(???)

```javascript
  var bgImg = new SimpleImg ("dinos.png") //这里是把图片存在一个叫SimpleImg的数组里，=并不代表赋值，而是指针，表面bgImg指向SimpleImg
```

- 全局变量 global scope，在js script中尽量少，因为在load page时跑script时有时会出现变量传输问题。尽量设为局部变量 local scope。In HTML, **the global scope is the window object**. All global variables belong to the window object. Sometimes we will use nested functions to solve the global scope variable dilemma. 

- **strict模式**

  JavaScript在设计之初，为了方便初学者学习，并不强制要求用`var`申明变量。这个设计错误带来了严重的后果：如果一个变量没有通过`var`申明就被使用，那么该变量就自动被申明为==全局变量==。

  ```js
  "use strict"; //在代码第一行写use strict启用strict模式
  ```

==Self-involking function== can be used to make local scope variable have the original value when it's global scope variable (like the starting value it wanna keep).



## 2. Data Types数据类型以及引用类型

### 2.1 JS的基本数据类型

- ES6中八种**JS的数据类型**包括：boolean, number, string, Object, undefined, null, Symbol, BigInt（新增最后两个）.

#### BigInt

```js
var a = 12366666666666n; //数字后面加个n表示是BigInt类型
var b = BigInt("9000111111111222"); //用BigInt()也可以设置类型
```

#### Symbol

表示独一无二的值。通过Symbol()函数包裹生成。和其它相等的时候都是false。

####Object

- array本质是Object，用typeof的时候可以发现，返回为object。 

- function也是一种特殊的object，但是typeof会返回function。

- > <font color=green>Primitive values, like "John Doe", cannot have properties or methods (because they are not objects). But with JavaScript, **methods and properties are also available to primitive values**, because **JavaScript treats primitive values as objects** when executing methods and properties.</font>


####类型转换

- When adding a number and a string, JavaScript will treat the number as a string.

 ```javascript
var x = 16 + "Volvo"; //16Volvo
 ```



### 2.1 Number

#### 运算以及Math.

- 求商`Math.floor(x/y)`, floor是取前面的整数，就是商的部分；求余数就用`x%y` 

####转为字符串

- 转化为字符串：num.toString();

#### 浮点数

JS中浮点数的运算会带来不准确的值，小数位会出现误差，来自于用二进制表示浮点数。解决方法是先变成integer运算，再还原成float，比如先乘以100，再除以100

```js
var a = (0.9*10 - 0.3*10)/10; //0.6
var b = 0.9 - 0.3; //0.6000000000000001
```



####关于数字排序：冒泡排序法。

### 2.2 Strings

`.length` is built-in property to get the length 

```javascript
var myString = "hello world!";
var x = myString.length;
window.alert(x); //输出的是myString的长度12.
```

String addition: `+` to add strings, or use`String1.concat(String2)` to connect String1 and String2. `concat()`can also be used to connect arrays.

```javascript
var String1 = "hello";
var String2 = "world";
var x = String1.concat(String2);
console.log(x); //在调试器中显示x的值，helloworld
```

#### Finding a String in a String

- The `indexOf()` method returns the index of (the position of) the `first` occurrence of a specified text in a string (array中也有indexOf）:

```javascript
var str = "Please locate where 'locate' occurs!";
var pos = str.indexOf("locate");
```

==`indexOf` is frequently used in conditions to see if a stringA is in anthor stringB==.

```javascript
//如果stringChild在stringParent里，就输出stringChild，否则就error
var stringParent = 'ab12345cd' ;
var stringChild = 'a' ;
if (stringParent.indexOf(stringChild) !== -1) {
  console.log(stringChild);
} else {
  console.log('error');
}
```

- `includes()`

```js
'Blue Whale'.includes('blue'); // false (大小写不同)
```

####String Slice and Substr

`slice()` and `substr()` **methods** are used to cut a string and return substring, they are similar. The difference is `str.slice(pos1, pos2)` cuts the `str` string from position `pos1` to position `pos2`(不包括pos2, pos2前面一个); `str.substr(pos1, len)` cuts the str from pos1 with `len` as the substring's length, no parameter as end position. 如果省略长度或pos2，这些函数就切到str最后。

```js
var string = "Hello World";
var subString = string.slice(1,3);
console.log(subString);
// el
var subStr = string.substr(1,3);
console.log(subStr);
// ell
```

####常用String methods(注意区分基本字符串和字符串对象)

<font color=red>红色的输出为array</font>

| Methods                               | Usage                                                        | Notes                                                        |
| ------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| string.charAt(index)                  | 截取string中的单个字符，index为截取字符的位置                | 基本字符串                                                   |
| stringObj.valueOf()                   | 字符串对象转换为其对应的基本字符串                           | 作用于字符串对象                                             |
| String.fromCharCode()                 | UTF-16的数字转化成对应的ASCII字符（65对应A，97对应a）        | 由于 `fromCharCode()` 是 [`String`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/String) 的静态方法，所以应该像这样使用：`String.fromCharCode()`，而不是作为你创建的 [`String`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/String) 对象的方法。 |
| <font color=red>string.split()</font> | split a string into an array of substrings, and returns the **new array**. | string.split(separator, limit), separator用引号括起来的分隔符，limit则限制了分割次数（也即新数组里面元素的个数） |
| <font color=red>string.match()</font> | 在string中搜索符合()内正则表达的item，返回符合条件的items，as an array object | match内的条件需要**RegExp**书写。常用RegExp：\d, \d+分别是找到单位digit和多位digit。\b\w单词开始一位, \w\b单词末尾一位。 |
| string.replace()                      | 搜索string里的一段值/RegExp，替代，返回新的string。不改变原来的string或者string object。 | *string*.replace(*searchvalue, newvalue*), searchvalue可以是string或者RegExp，newvalue可以是新的string或者function to be called。 |
| string.toUpperCase()                  | 将string全部转为大写                                         | *string*.toUpperCase()； string.toLowerCase()                |

```js
var s1 = "2 + 2";               // creates a string primitive
var s2 = new String("2 + 2");   // creates a String object
console.log(eval(s1));      // returns the number 4
console.log(eval(s2));      // returns the string "2 + 2"
console.log(eval(s2.valueOf())); // returns the number 4
```




### 2.3 Array

- 数组中的length属性很有特点，它**不是只读**的。因此，我们还可以通过设置这个属性，从数组的末尾移除数据项
- <https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array#数组实例>

####Array常用methods

==提亮method不改变原数组==, <font color=red>红色为改变array为string</font>

| Methods               | Usage                                                        | Notes                                                        |
| --------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ==array.concat(arr1, arr2,...,arrX)== | 连接数组，返回新数组，不影响原来数组| 数组元素以逗号隔开|
| array.push("item")    | 向数组array末尾添加item的新元素，返回新数组长度。                    | `array.push("item"); return array` |
| array.pop()           | 移除array数组末尾的一个元素，并返回被移除的元素。                  | `var a = array.pop();`// a为被移除的元素；要得到被移除后的数组，直接对数组作用但是不要pop的返回值，要被改变的原数组即可：`array.pop(); var a = array;` //此时a就是移除后的数组 |
| array.unshift("item") | 向数组array前面添加item新元素，返回新的长度lengt                   |                                                              |
| array.shift()         | 移除array数组前面的一个元素，返回被移除的元素。                        |                                                              |
|array.splice() |删除array中的某些元素，并可以在删除位新增元素。改变原数组。返回值是删除的元素|*array*.splice(*index*, *howmany*, *item1*, ....., *itemX*)|
| ==array.filter()==    | 根据filter里面的内容来筛选array数组的每一个元素，生成符合条件的**新数组**。functionName会对每个array元素作用一次。返回值为真假，根据真假判断是否添加元素。 | array.filter(function(element, index, self){ function code }) or array.filter(functionName), fucntionName不加括号，引用函数定义；对于functionName的返回值为真或者coerce to true时会存到新数组里，这里注意，返回值是零的时候为false！！！7种falsy values。 |
| array.indexOf("item") | 在array中查找item，返回index                                 | 若item出现多次，只返回第一次出现的位置。                     |
|array.lastIndexOf("item")     |在array中查找item，返回最后一次出现的位置。|因为是从后往前搜索，搜到即返回，那么返回的是正序里面的最后一次出现的位置。可以指定开始搜索的位置。|
| ==array.flat(depth)== | 在array中，下挖深度depth，打开内部elements，生成的为**新数组** | 比如[1,[2,3],4] flat(1)之后是[1,2,3,4].                      |
| ==array.map()==       | 返回一个**新数组**，数组中的元素为原始数组元素调用函数处理后的值 | array.map(function(currentValue,index,arr) {//code}）        |
| array.sort()          | 对array进行基于unicode的排序，**改变原数组**。如果是数字，引入比较函数进行排序。 | array.sort(function(a, b) {return a - b})升序；array.sort(function(a, b) {return b - a})降序； |
| ==array.reduce()==    | 对每个元素调用function，返回total，下一次这个total会被用在调用函数里，一起迭代。==total可以是任意形式==, 可以是数，数组，对象。**不改变原数组。** | array.reduce(function(total, currentValue, index, arr), initialValue)或者省略为array.reduce(functionName)。注意有initialValue时element从第0位开始，没有时默认functionName里面为第0位element，currentValue从第1位element开始。 |
| ==array.reduceRight()== | 对array中每个元素，从末尾开始往开始，调用function。其它同reduce() |  |
| ==<font color=red>array.toString()</font>== | 将array转化为新的string，以comma分隔 |  |
| ==<font color=red>array.join()</font>== | 将array转化为新的string，以join括号内的为分隔符 | array.join("")即没有分隔符。|
| ==array.forEach()== | 对array每个元素执行一遍内部的函数，没有返回值。就是创造一个循环环境。 | array.forEach(function(curr, index, self){}) |
| Array.isArray(obj) | 判断一个obj是不是array | 注意前面固定的Array用法，不是要检测对象；要检测对象在括号里 |

- array.filter()的用法<https://blog.csdn.net/qq_39207948/article/details/80357367> 

- array.map()的用法<https://www.w3schools.com/jsref/jsref_map.asp>

```js
var collection = [{key:"a", count: 2}, {key: "b", count:3},{key:"c", count: 4}];
//返回一个只有key内容的数组
var keyArray = collection.map(function(element) {
  return element.key;
});
console.log(keyArray);
```

- array.sort()改变原数组，如要拷贝数组<https://blog.csdn.net/gzyzwx/article/details/82501968>

- array.reduce()的用法，下列返回一个对象。

```js
var names = ['Alice', 'Bob', 'Tiff', 'Bruce', 'Alice'];
var countedNames = names.reduce(function (allNames, name) { 
  if (name in allNames) {
    allNames[name]++;
  }
  else {
    allNames[name] = 1;
  }
  return allNames;
}, {});
// countedNames is:
// { 'Alice': 2, 'Bob': 1, 'Tiff': 1, 'Bruce': 1 }
```

数组去重的多种方法：<https://segmentfault.com/a/1190000016418021>

###2.4 Object

这里的object指的是instance object。毕竟如果是基础类型Object的话，Array等都是基于Object的。所以这里讨论小的实例。

```javascript
var myObj = {}; //创建一个空数组；
```

object有键值对构成，键都是**字符串**类型，值可以是任意类型。

####Add new property

You can add new properties to an existing object by simply giving it a value:

```javascript
var myObj = {};
myObj.propertyName = propertyValue; 
//myObj= {propertyName: propertyValue}这里的名字和值都是字符串本身，不能是变量
myObj["propertyName"] = propertyValue;
var name = "propertyName";
myObj[name] = propertyValue;
```

需要用变量作为object的property和value时，也可以用`Object.defineProperty()`.

```javascript
var demo = {};
var name = "John";
var age = 12;
Object.defineProperty(demo, name, {value : age});
//property位置可以是这里的name，也可以是"John".同样value部分可以是age也可以是12.
```

#### Delete property

Use `delete`.

```js
delete myObj.propertyName
```



## 3.条件语句(Condition)和循环语句(Loop)

###3.1 Conditions

everything with a value is true.

- 运算符中，`if (!variableName){}`,其中的`!` negates the condition. 所以上述语句等于`if (variableName == 0){}`. 通常情况下， if 括号里的condition不为零或者空时return true，执行{}里的语句。

The Boolean value of **0** (zero) is **false**:

```javascript
var voteable = (age < 18) ? "Too young":"Old enough";
//”真在前，假在后“ condition ? exprIfTrue : exprIfFalse
```

**conditional operator**: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator>

###3.2 Loop

```javascript
//记得要声明变量
for (var i=0; i< className.length; i++) {
  //运行需要loop的code
}
```



## 4. Functions

Functions: *not* invokes on an object. While Methods are invoked on an object.

function can contain parameter and argument in the `()`

==When JavaScript reaches a `return` statement, the function will stop executing.==

Function **arguments** are the **values** received by the function when it is invoked. 就是函数中的可变量，你从函数外面得到，然后这个值会在函数中的操作里。

```javascript
function name(parameter1, parameter2, parameter3) {
  // code to be executed
}
```

```javascript
function myFunction(p1, p2) {
  return p1 * p2;   // The function returns the product of p1 and p2
}
```

Function call, is how we make use of a specific function.

```javascript
var y = myFunction(3, 4); //y=12
```
### Arrow Function

### inner Functions (Nested Functions)

see variable section for self-invoking functions.

### Self-voking Function

==Self-involking function== can be used to make local scope variable have the original value when it's global scope variable (like the starting value it wanna keep).

```javascript
var add = (function () {
  var counter = 0;
  return function () {counter += 1; return counter}
})();
```

The variable `add` is assigned the return value of a self-invoking function.

The self-invoking function only runs once. It sets the counter to zero (0), and returns a function expression.

This way add becomes a function. The "wonderful" part is that it can access the counter in the parent scope.

This is called a JavaScript **closure.** It makes it possible for a function to have "**private**" variables.

The counter is protected by the scope of the anonymous function, and can only be changed using the add function.

### Function Apply

With the `apply()` method, you can write a method that can be used on different objects.

The difference is:

The `call()` method takes arguments **separately**.

The `apply()` method takes arguments as an **array**

```js
Math.max.apply(null,[10, 20,30]); //输出30;
```



## 5. Methods 

Methods are invoked on an object, some have parameters in `()`. 

```javascript
var w = bgImg.getWidth() //getWidth()是duke自己内置methods，得到宽度，中间的`.`代表inside of，后面的is inside of 前面的
```

We already mentioned a lot of built-in methods in the previous sections, like  `indexOf` method for a string.





# \[Important\]: Interactivity

## 1. Event Listener (更多JS DOM Event.md)

`element.addEventListener("click", myFunction());` 对element添加event listener，作用是在click时触发myFunction() 函数。

当传递参数值时，请以参数形式使用调用指定函数的“匿名函数”(一般也用不到，了解即可)：

```javascript
element.addEventListener("click", function(){ myFunction(p1, p2); });
```



##2. JS HTML DOM Basics

Document Object Model (DOM):

> DOM is the full, parsed representation of the HTML

DOM itself is **NOT** part of JS, it's constructed from browser and is globally accessible by JS code using the `document` object.

All Element properties and methods can be found on <https://developer.mozilla.org/en-US/docs/Web/API/Element> or <https://www.w3schools.com/jsref/dom_obj_all.asp>

 JS can access and change elements of HTML, so your html become **interactive**. 通常的格式如下`document.getElementById("IDname").innerHTML` ，其中document作为object，getElementById是常用的Method，method执行后`document.getElementById()`返回的是那个element as an object，innerHTML是property，改变文字内容。
### 2.1 Get，Create and Remove Element
#### 2.1.1已有element

  `document.getElementById` 返回一个node，`document.getElementsByClassName` 和 `document.getElementsByTagName`返回一串nodelist。 **但是用`document.querySelector(".className")` 返回的则是找到的第一个值！！即使里面的是class或者tag name。**

下方例子中，用ClassName找element，返回的是一串nodelist，即使只有一个，==也要加[index]才能access那个node==。否则无法定位。

```html
<div><input type="button" value="details" onclick ="changeSize()"></div>
<div class="font">here is the font</div> 
<div id = "size">show the size.</div>
<script>
  function changeSize(){
  var size = document.getElementById("size");
  var font = document.getElementsByClassName("font")[0];
  size.innerHTML = 12;
  font.innerHTML = "Times New Romam";
  }
</script>
```

`className` property can be used to change the class name of an element, and then you can use this way to **change the CSS style**, if you have new CSS style under the new className you changed.

#### 2.1.2新建element (Node)并插入

`document.createElement` to create element like\<p\>, \<li\>; add text content by `createTextNode`. Append new element as the last child of the parent using `appendChild`.

```javascript
var newPara = document.createElement("p");
var newText = document.createTextNode("this is new text");
newPara.appendChild(newText);
```

先append最内层的，再往外套，否则先append外层，内层的内容不会显示。比如下面14行如果在13行前面，则"this is new"不会显示。

```html
<html>
<body>

<div id="outDiv">
<p id="p1">This is a paragraph.</p>
<p id="p2">This is another paragraph.</p>
</div>

<script>
var outElement = document.getElementById("outDiv");
var para = document.createElement("p");
var text = document.createTextNode("This is new.");
para.appendChild(text);
outElement.appendChild(para);
</script>

</body>
</html>
```

如果要指定插入在其它child node前面，可以用`fatherNodeName.insertBefore(newNode, existNode)`, 其中fatherNodeName是要插入的父元素，newNode是你要插入的子节点，existNode就是你要插在它前面的那个已经存在的node，一般可以用父元素的第几个childNode找到`fatherNodeName.childNodes[2]`.

在html中我们用`\<input type="button"\> `中的\<input\> tag来插入各种框体，比如type = "button"时为按钮，type = "checkbox"时则为选择框，type = "text" 时则为输入文本框。那么如何在JS中创造相应的element呢？这里用`setAttribut("type", "checkbox")`来实现，将属性设置为checkbox。

```javascript
var x = document.createElement("INPUT");
x.setAttribute("type", "checkbox");
```
#### 2.1.3删除element

用`element.remove()`, 或者`parent.removeChild(child)`来实现删除某个element。不知道parent的时候可以用parentNode来找到parent。

```html
<div>
  <p id = "p1">this is paragraph one</p>
  <p id = "p2">this is paragraph two</p>
</div>
<script>
//删除p1的element，所以显示的内容只有”this is paragraph two“
var child = document.getElementById("p1");
var removed = child.parentNode.removeChild(child); 
removed === child; //true
</script>
```

注意到删除后的节点虽然不在文档树中了，但其实它还在内存中，可以随时再次被添加到别的位置。

### 2.2 innerHTML, innerText, textContent, nodeValue

四个都是用来获取某个node的文字信息，返回的都是==string==，那么它们有什么区别呢？

| property    | usage                                                        |
| ----------- | ------------------------------------------------------------ |
| innerHTML   | 可以写入text和html格式，比如element.innerHTML = "\<div\>text\</div\>"; |
| innerText   | 返回一个node的文字以及其所有子元素node的文字，不包括被css隐藏的文字部分，且不返回\<script\>和\<style\>下的内容 |
| textContent | 返回一个node的文字以及其所有子元素node的文字，包括被css隐藏的文字部分 |
| nodeValue   | 只获取textNode的文字；如果是element node，会返回null         |

如果一个元素*fatherElement*，下面的子元素包含text和非text部分（其它html source code），而你只想改变这个元素下面的text为"new text"，但是保留非text部分，则用childNodes找到textNode部分，改变其nodeValue = "new text"。如果不定位到具体的textNode直接改变*fatherElement*的innerHTML/innerText/textContent = "new text"，其它非text的部分也会直接被抹掉。

### 2.3 location, history, screen

- The location object is part of the window object and is accessed through the window.location property.

```js
window.location.reload()  //重新加载当前页
window.location.replace("url") //当前页加载内容替换为url的页面
```

- The screen object contains information about the visitor's screen.

### 2.4 MouseEvent

Event: mousedown, mouseup, mousemove.

Property: clientX, clientY返回鼠标坐标

实现元素拖拽：<https://segmentfault.com/a/1190000008712963>

##3. JSON（具体在“JS对象基础.md”）

> **JSON** (JavaScript Object Notation) is a lightweight data-interchange format. 
>
> JSON is built on two structures:
>
> - A collection of name/value pairs. In various languages, this is realized as an **object**, record, struct, dictionary, hash table, keyed list, or associative array.
> - An ordered list of values. In most languages, this is realized as an **array**, vector, list, or sequence.




##4. JQuery Library

# Reference

## 1. 自带函数

The `isNaN()` function determines whether a value is NaN or not.

###String to Number:

`Number()` function converts object ro number. If the value cannot be converted to a legal number, NaN is returned. 具体转换规则：

| 被转换的类型                         | 转换为的数字                                                 |
| ------------------------------------ | ------------------------------------------------------------ |
| boolean                              | true转换为1，false转换为0                                    |
| number                               | number                                                       |
| null                                 | 0                                                            |
| undefined                            | NaN                                                          |
| string且只包含数字，比如"123"; "0xf" | 转换为十进制数字，123; "011"转换为11，前导零被忽略; "0xf"十六进制数转换为十进制数值15 |
| string中数字有浮点格式"12.33"        | 转换为对应的浮点数 12.33                                     |
| ""                                   | 0                                                            |
| "abd12d"                             | NaN                                                          |

`parseInt()`, 将string转化为整数integer（floor型取整，不四舍五入），但如果第一个字符不可转化，则不继续，返回NaN；

`parseFloat()`, 将string转化为浮点数float，也是如果第一个字符不可转化则NaN。

`eval()`会输出字符串运算的结果，结果也是数字类型。

## 2. 关键字

### in

in用于判断某item是否在被查obj的key里面，如果被查的是array，key则是index。

## 3. Operators

### 3.1 `==` and `===`

详细内容参考JS equality and data type conversion.md

| operator | Usage                                            | example                                                      |
| -------- | ------------------------------------------------ | ------------------------------------------------------------ |
| `==`     | 等值；类型不等时会先自动转化成相同类型再比较大小 | `1 == 1` <font color=green>// true</font>;   ` '1' == 1` <font color=green>// true;</font>   `var object1 = {'key': 'value'}, object2 = {'key': 'value'};  object1.key == object2.key` <font color=green>//true</font>。当两个操作数都是对象时，JavaScript会比较其内部引用，当且仅当他们的引用指向内存中的相同对象（区域）时才相等，即他们在栈内存中的引用地址相同。 |
| `===`    | 等值且等类型 strict equality                     | `3 === 3`   <font color=green>// true</font>;    `3 === '3' `<font color=red>// false;</font>     `var object1 = {'key': 'value'}, object2 = {'key': 'value'}; object1 === object2;` <font color=red>//false</font> |

### 3.2 `~~`

`~~` has the same effect as `Math.floor()`

```js
var a = ~~2.4; 
a === 2; //true
```

`~`单个tilde表示binary NOT，即将数字转化为二进制，每位取非，0的非是1， 1的非是0。按位非得到的是操作数的负值减1：

```js
~5 === -6; //true
```

### 3.3 `||`

logical OR. 除了基础用法外，还有一种传值时的用法, find the first truthy value or to the last one：

```js
var a = x || y; //x不是falsy value(0, false, undefined, "", NaN, null)时传x，否则传y。
```

```js
function convert(num) {
  return num <= 26 ?
    String.fromCharCode(num + 64) : convert(~~((num - 1) / 96)) + convert(num % 26 || 26);
} //数字转化为字符的递归函数.
```



## 4. Template Literal (ES6 new feature)

```js
var a = 5;
var b = 10;
console.log(`Fifteen is ${a + b} and
not ${2 * a + b}.`);
// "Fifteen is 15 and
// not 20."
```

<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals>

##Code Example

###Calculator

Calculator example <https://www.geeksforgeeks.org/html-calculator/>, but the problem is that it displays all items including operators. And it did not limit the input of successive operators, which will result in error. Too easy, it did not rule out some special cases, like inputting successive operators.

Calculator example setting calculator as object <https://freshman.tech/calculator/>, this one is object-oriented. You can see many `object.method` lines here. Good to learn how to code in object-oriented fashion.

###To-do List

<https://www.w3schools.com/howto/howto_js_todolist.asp>