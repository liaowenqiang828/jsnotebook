1. 为了更好的向前兼容不同的浏览器，编写CSS3时都有哪些前缀？分别对应什么浏览器？
   	- -ms- 对应兼容IE浏览器；
   	- -moz- 对应兼容Firefox浏览器；
   	- -o- 对应兼容Opera浏览器；
   	- -webkit- 兼容chrome 和 Safari浏览器。
2. 说说你理解的伪类和伪元素分别是什么？
   	- 伪类是针对于那些存在于DOM树以外的或者无法使用简单选择器所能够描述清楚的那些类可以被CSS选择器所识别存在的。本质上是为了弥补CSS中选择器的不足而存在、而产生的。
   	- 伪元素可以用于创建一些在文档语言中无法创建的虚拟元素，比如元素内容的第一个字母、第一行等等在原有的文档语言中没有对应的机制来进行相应的描述，那么就可以分别创建出能实现相应选择效果的虚拟元素，即伪元素。
3. 分清`Transform` 、`Transition`、 ` Animation` 三兄弟，并阐述他们分别的用处？
   	- transition：过渡，用于设置元素的样式过渡，就是元素从这个属性的某个值过渡到这个属性的另一个值，是一个状态的转变，通常需要一种条件来出发这个转变的发生。
   	- transform：变换，用于元素进行旋转、缩放、移动或者倾斜。
   	- animation：动画，用于设置动画属性，可以看做是对transition属性的拓展，弥补了很多transition的不足，可以理解为多个transition的叠加，可以做出更加复杂的连续变化的效果。