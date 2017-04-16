# Web前端面试题目汇总
## HTML/CSS部分
### 1、什么是盒子模型？
在网页中，一个元素占有空间的大小由几个部分构成，其中包括元素的内容（content），元素的内边距（padding），元素的边框（border），元素的外边距（margin）四个部分。这四个部分占有的空间中，有的部分可以显示相应的内容，而有的部分只用来分隔相邻的区域或区域。4个部分一起构成了css中元素的盒模型。

### 2、行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？
行内元素：a、b、span、img、input、strong、select、label、em、button、textarea  
块级元素：div、ul、li、dl、dt、dd、p、h1-h6、blockquote  
空元素：即系没有内容的HTML元素，例如：br、meta、hr、link、input、img

### 3、CSS实现垂直水平居中
一道经典的问题，实现方法有很多种，以下是其中一种实现：  
HTML结构：
```html
<div class="wrapper">
    <div class="content"></div>
</div>  
```
CSS：
```css
.wrapper {
  position: relative;
  width: 500px;
  height: 500px;
  background-color: #ddd;
 }
.content{
    background-color:#6699FF;
    width:200px;
    height:200px;
    position: absolute;        //父元素需要相对定位
    top: 50%;
    left: 50%;
    margin-top:-100px ;   //二分之一的height，width
    margin-left: -100px;
} 
```
### 4、简述一下src与href的区别
一般来说是针对不同的浏览器写不同的CSS,就是 CSS Hack。  
IE浏览器Hack一般又分为三种，条件Hack、属性级Hack、选择符Hack（详细参考CSS文档：css文档）。例如：
```css
// 1、条件Hack
<!--[if IE]>
  <style>
        .test{color:red;}
  </style>
<![endif]-->
// 2、属性Hack
.test{
color:#090\9; /* For IE8+ */
*color:#f00;  /* For IE7 and earlier */
_color:#ff0;  /* For IE6 and earlier */
}
// 3、选择符Hack
* html .test{color:#090;}       /* For IE6 and earlier */
* + html .test{color:#ff0;}     /* For IE7 */
```
### 6、简述同步和异步的区别
同步是阻塞模式，异步是非阻塞模式。  
同步就是指一个进程在执行某个请求的时候，若该请求需要一段时间才能返回信息，那么这个进程将会一直等待下去，直到收到返回信息才继续执行下去；  
异步是指进程不需要一直等下去，而是继续执行下面的操作，不管其他进程的状态。当有消息返回时系统会通知进程进行处理，这样可以提高执行的效率。
### 7、px和em的区别
px和em都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，并且em会继承父级元素的字体大小。  
浏览器的默认字体高都是16px。所以未经调整的浏览器都符合: 1em=16px。那么12px=0.75em, 10px=0.625em
### 8、什么叫优雅降级和渐进增强？
渐进增强 progressive enhancement：  
针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。  

优雅降级 graceful degradation：  
一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。  

区别：  
a. 优雅降级是从复杂的现状开始，并试图减少用户体验的供给  
b. 渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，以适应未来环境的需要  
c. 降级（功能衰减）意味着往回看；而渐进增强则意味着朝前看，同时保证其根基处于安全地带
### 9、浏览器的内核分别是什么?
IE: trident内核  
Firefox：gecko内核  
Safari：webkit内核  
Opera：以前是presto内核，Opera现已改用Google Chrome的Blink内核  
Chrome：Blink(基于webkit，Google与Opera Software共同开发)


> 作者：GeniusLyzh  
出处：http://www.cnblogs.com/GeniusLyzh/  
本文链接：http://www.cnblogs.com/bigboyLin/p/5272902.html  
本文版权归作者和博客园共有，欢迎转载，须保留此段声明，并给出原文链接，谢谢！  
如果阅读了本文章，觉得有帮助，欢迎点击右下角推荐  
