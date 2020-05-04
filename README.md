鹿总自我介绍

姓名，工作年限，工作地点，毕业院校，技术栈，最近的项目



## 第一天

### 1.模块化和组件化的区别

组件化：把一个模块划分成一个一个小的内容，例如：轮播图，二级导航。称之为黑盒

模块化：把功能划分成一个模块，重心在设计和开发阶段，称之为白盒

------------------

### 2.0 flex父子属性

父属性

1. flex-direction：主轴方向
2. flex-wrap：轴线排不下，如何换行
3. flex-flow：是`flex-direction`和`flex-wrap`属性简写形式，默认值为`row nowrap`
4. justify-content：项目在主轴上的对齐方式
5. align-items：项目在交叉轴上对齐方式
6. align-content：定义多根轴线的对齐方式。如果只有一根轴线，该属性不起作用

子属性

1. order：定义项目的排列顺序。数值越小，排列越靠前，默认为0
2. flex-grow：定义项目的放大比例，默认为0，即如果存在剩余空间也不放大
3. flex-shrink：定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小
4. flex-basis：定义了在分配多余空间之前，项目占据的主轴空间。默认值auto
5. flex：`flex-grow`,`flex-shrink` ,`flex-basis`的简写，默认值为0 1 auto。后两个属性可选
6. align-self：允许单个项目有其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素则等同于stretch

各6个，孙航英文

### 2.水平垂直居中的方式

--------------

1.固定定位方式,上下左右全部设置成0
2.不定宽高，固定定位+css3变换的方式，transform：translate（-50%，-50%）

孙航，英文

3.不定宽高flex属性，justify-content，主轴上居中，align-items，交叉轴上居中

4.固定宽高，负边距拉回

### 3.localStorage，sessionStorage，cookie的区别

-------

（localStorage，sessionStorage两个都是指本地存储）

（本地存储）和cookie

时间：cookie设置过期时间，本地存储localstorage是永久，session是关闭浏览器页面

大小：cookie<4kb   本地存储大小不限

服务器：cookie会随着请求发送给浏览器，本地存储不会

条数：cookie<50   本地存储不限

### 4.为什么产生了跨域

1.因为浏览器的同源策略，（协议，域名，端口号任一不同都不是同源）

2.协议域名端口号,王慧妍没有举例

### 5.解决跨域的方式

------------

```js
	location.search:只能get提交，并且只能在地址栏中发送数据
     ajax：get、post都可以
     jsonp：只能get提交，并且需要传递callback回调函数
     websocket：双向传输，只需要一次握手即可
     postMessage：有三种传值的设置，iframe、window.open、window.opener
     wndow.name+iframe：解决的是iframe只能实现同源传值的特性，值是放在name属性中来传的
     document.domain+iframe：只能是二级域名相等的话才能实现跨域传值
     cors：服务器和浏览器需要同时设置，和原生ajax写法一样
     
     面试的时候问：
     知道的跨域传值方式有以上几种，一般情况下，我们最常用到的是jquery中的ajax，jsonp；但是在使用jsonp的时候只能是get提交，如果有post提交的话，一般优先选择的是ajax来完成的，当然初次之外，也会用到我之前说过的记中跨域传值的方式，但是不多
```

### 6.什么是原型链

---------

```js
 原型链
  * 所有的实例对象都有__proto__属性, 它指向的就是原型对象
  * 这样通过__proto__属性就形成了一个链的结构---->原型链
  * 当查找对象内部的属性/方法时, js引擎自动沿着这个原型链查找
  * 当给对象属性赋值时不会使用原型链, 而只是在当前对象中进行操作

```



### 7.git常用的命令

```js
git init	陈旭-create
git add *	添加到暂存区
git commit -m "注释内容"
git push origin master
```

### 8.原生ajax

```js
步骤，6步
1.创建xmlhttprequest对象
2.设置发送的内容
3.设置发送方式
4.头部信息
5.处理函数
6.发送
```

### 9.创建对象的方式

```js
一.系统构造函数	let foo = new Object()
二.JSON/直接实例化	let foo = { name: 'li', age: 18 }

三.工厂模式
function 方法名(属性1, 属性2) {
  var 对象 = new Object()
  对象.属性 = 属性
  对象.方法 = function() {}
  return 对象
}
var 实例 = 方法名(属性1, 属性2)

四.构造函数
function foo(name, age) {
  this.name = name
  this.age = age
}
let obj = new foo('li', 12)
五.原型链
六.混合,构造函数+原型链，属性使用构造函数，方法挂载到原型链
function foo(name, age) {
  this.name = name
  this.age = age
}

foo.prototype.constructor = foo
//每个函数都有prototype属性，指向该函数原型对象，原型对象都有constructor属性，这是一个指向prototype属性所在函数的指针
foo.prototype.fn1 = function() {}
foo.prototype.fn2 = function() {}
```

### 10.对象的继承方式有哪几种

```js
陈旭 少说一种
 1.属性继承
 2.构造函数继承 call apply bind
 3.原型链继承
 4.组合
 5.组合寄生
```

### 11.call apply bind的区别

```js
陈旭，王慧妍
call参数字符串
apply参数数组

bind返回值是一个函数，需要自己调用一次
```



### 12.箭头函数

```js
陈旭
没有自己的this指向
指向的是外层的this
谁调用指向谁
原理
function(){}.bind(this)
```

### 13.防抖节流,原理，什么场景？

```js
王慧妍
区别
防抖，保证一定时间段内没有再触发事件
节流，保证一定时间内只调用一次事件处理函数

防抖:每次触发事件,设置延迟事件,再次触发事件的时候取消之前的方法

节流:每次触发事件,如果有等待执行的延时函数,则直接 return

```

### 14.什么是闭包

```js
函数，可以访问其他函数内部私有变量

```

### 15.什么情况产生内存泄漏

```js
1.变量未回收
2.定时器未及时清除
3.闭包不当使用

```



### 16.垃圾回收机制（补充

```js
js语言里，将来不会被使用的变量会自动被垃圾回收机制回收
其他语言  需要自己手动清除

```

### 17.伪类伪元素区别

```js
孙航

```

* 伪类没有兼容性问题,伪元素存在兼容性问题
* 伪类可以使用多个,而伪元素只能有一个
* 伪类的权重等于类的权重,而伪元素相当于标签的权重

### 18.rem的计算方式

```js
王慧妍，计算方式

```

19.闭包

* 闭包应用:
  * 模块化: 封装一些数据以及操作数据的函数, 向外暴露一些行为
  * 循环遍历，用var定义变量产生的index问题
  * JS框架(jQuery)大量使用了闭包

* 缺点:
  * 可能导致内存泄露
  * 解决:
    * 及时释放 : f = null; //让内部函数对象成为垃圾对象

## 第二天

### 19. ES6常用的语法

```
鹿总
```

* 箭头函数
* 对象,数组解构赋值
* 类
* `const let`
* 字符串模板
* 数组,对象,正则等api扩展
* promise
* generator
* await/async
* proxy (vue3)
* 模块的导入导出

### 20. `const var let`

```
鹿总
```

* 块级作用域
* 变量提升
* 暂存性死区 
* 重复声明

### 21. new之后干了什么

```
鹿总
```

1. 创建一个新对象
2. 把原对象原型链上的方法继承过来
3. 通过call执行函数
4. 判断新对象是否属于复杂数据类型,如果是返回复杂数据类型,否则返回执行的函数

### 22. 性能优化

```
鹿总
```

网络资源

* CDN

* 打包

* 防抖节流

* 精灵图 

* webp图片 

* 图片懒加载,图片预加载

* 缓存

渲染

* 减少重排重绘,减少DOM操作

JS异步执行

* async
* defer
* 动态创建JS标签 
* dom事件，回调函数，定时器，ajax

### 23. 减少http请求次数

```
鹿总
```

 打包

精灵图

防抖节流

### 24. webpack

鹿总

1. 输入输出 entry,output
2. loader   sass-loader less-loader file-loader url-loader postcss-loader
3. plugins(插件)   htmlwebpackplugins  cleanwebpackplugins webpackderverhot 

### 25.数据可视化

```
小王
```

echarts   d3

### 26. ajax问题

```
小王
```

回调地狱问题

解决回调地狱：promise，generator，await/async

### 27.事件循环

```
小王
```

js是单线程的程序,如果想要达到更好的用户体验,需要配合异步达到更好的效果,当代码从上到下依次执行的时候,碰到同步代码会进行执行,碰到异步代码会放到异步队列当中,等异步队列执行到这个地方之后,会判断是否触发,但是<font color="#0f0">异步队列是一个队列结构,先进先出</font>,可能我们需要让某些条件优先执行,那么就需要区分<font color="#0f0">宏任务和微任务</font>,微任务要优先执行,而宏任务要次一级去执行,常见的微任务有 Primose.then 宏任务定时器等等

### 28.数组方法

```
小王
```

push pop shift unshift map foreach filter concat splice slice

### 29.判断数组

```
小王
```

Array.isArray    instanceof     Object.prototype.toString.call([])

### 30. 输入url到加载完

```
小王
```

重定向-> 拉取缓存-> DNS解析-> 发出请求(三次握手四次挥手)->建立连接->接受文件->渲染->展示

### 31. 遍历对象 & 数组

```
旭
```

对象

* for in
* Object.keys()
* Object.values()
* Object.getOwnPropertyNames

数组

* for
* map
* forEach
* filter
* reduce

### 32. 事件冒泡与委托

```
旭
```

1. 默认的事件是冒泡
2. 委派的原理是冒泡
3. 委派是把事件绑定在父元素上,当事件冒泡到父元素上统一处理

好处:

* 动态创建的DOM可以绑定事件
* 优化,把多个事件合并为一个

### 33. 接口请求方法

```
旭
```

get post  put delete 

### 34. css类名冲突怎么解决？

```
旭
```

CSS modules

### 35. 权重

```
旭
```

!important>行内>id>class>标签>*

### 36. 数组去重有哪些方法 & 排序

```
旭
```

冒泡  indexof   new Set()

冒泡  sort

### 37. 兼容性问题

```
旭
```

* 事件对象

  var e=e || window.event

* 动画过度,阴影,渐变,圆角,2D,3D---->需要前缀

* resize(部分浏览器不支持)

* flex->box

### 38. 移动端适配 & 响应式

```
旭
```

响应式: flex-->PC与移动

移动端适配: rem-->手机机型

## 第三天  

```
旭: 25分  不包含项目总街和自我介绍
```

### 1. 如何实现左右固定中间自适应

flex布局

浮动

### 2. flex 是哪几个属性的复合属性

子 flex:  flex-basis   flex-grow   flex-shrink

父 flex-flow: flex-direction flex-wrap

### 3. 如何完成圣杯布局效果

浮动:

弹性盒: 

第三方UI库: `antd`提供了圣杯布局

### 4. transition和 animation 和使用场景

transition 属性值在一定的时间内从一个状态平滑的过渡到另一个状态。这种状态可以在鼠标单击、获得焦点、被点击或对元素任何改变中触发，并平滑的以动画效果改变css的属性值，增强用户体验。

animation是动画,是过渡的属性扩展,可以设置多帧过渡,

### 5. 用transition实现三角形

 三角形:border  tansition配合2D旋转

### 6. for in  for of 的区别

1. for of 是ES6新增

2.  for...in 循环主要是为了遍历对象而生，不适用于遍历数组

   for...of 循环可以用来遍历数组、类数组对象，字符串、Set、Map 以及 Generator 对象 

### 7. for in 和`object.keys`得到的数组区别

`Object.keys()`**用于获取对象自身所有的可枚举的属性值，但不包括原型中的属性，然后返回一个由属性名组成的数组**

返回的是所有能够通过对象访问的、可枚举的属性，既包括存在于实例中的属性，也包括存在于原型中的实例

### 8. `ES5、ES6`遍历方法和区别

数组

`map filter reudce forEach`

对象

for in

for of

`Object.keys`

`Object.values`

`Object.getOwnPropretyNames`

```
鹿总
```

### 9.  reduce数组新增方法

常用:  求和 求阶乘 数组扁平化等等

两个参数 ( function( 上一次的return值,value值,索引值,数组 ){},b ) b:第一次返回callback之后的初始值

### 10. `webpack` 性能优化

* 按需加载
* 配置生产环境和开发环境不同的发包方式
* 生产环境去掉map文件

### 11. 实现一个loading的特效 用动画怎么去写 写一个旋转loading大概怎么写

* 使用`gif`图片
* 用animation设置多帧 rotate旋转 

### 12. css3盒模型有哪些 之间怎么进行转换

IE盒模型   box-sizing

标准盒子

弹性盒   display

```js
王
```

### 13. 你了解的异步方法

* 定时器

* promise

## 第四天

```js
小王
```

### 1. 实现下拉刷新，上拉加载更多(思路)

滚动加载: 给页面添加滚动事件,当页面距离底部达到我指定的高度的时候,发出请求,请求的结果循环遍历,追加到页面的DOM中
注意事项: 为了更好的用户体验,在发出请求之前做出动画,接受到的请求可能有两种状态,错误的话跳转到错误页面或者给出错误提示,正确的话则提示成功

### 2. 异步解决方案

* promise

* generator

* async/await

### 3. 缓存

强缓存  这个请求不需要发到后台,直接用

协商缓存  发到后台,问后台是否发生改变,如果发生改变请求新的,如果没发生改变,则拉取缓存

```js
小智
```

### 4. 深浅拷贝

Object.assign()
{...obj}

JSON.parse(JSON.stringify())



## 第5天

### 一/所用到的接口

```js
鹿总可以对用到的接口做了解
1.二级导航部分
2.轮播图
3.商品图片信息
.
.
.
```

### 二/typeof返回值

```js
鹿总，function
```

### 三/左右固定 中间自适应Css布局

```js
方式1.	浮动方式
方式2.	定位
方式3.	flex布局
方式4.	display：table
方式5.	display：grid
鹿总两种
代码:demo1
```

### 四/css盒子模型和ie盒子区别

```js
计算宽度的方式不一样

标准模型的宽度就是content宽度
Ie模型的宽就是border+padding+内容

W3C盒子在页面的宽度不包括margin+padding+border
IE盒子在页面的宽度是margin+padding+content
```

### 五/怎么设置盒子模型

```js
box-sizing:	border-box	标准
			content-box	IE
            鹿总,属性值
```

### 六/重排和重绘

```js
陈旭ok
智有强ok
可以延展到性能优化,那些方式可以减少重排重绘,还有重排一定重绘,重绘不一定重排
```

### 七/DOM事件的级别

```js
鹿总,陈旭
DOM的级别--面试题出现，必须要重点掌握
     DOM1级：允许获取和操作文档的任意部分
     DOM2级：新增加的鼠标和用户界面事件，对css的支持和遍历
     DOM3级：增加了对文档存储、载入、验证的方法

DOM事件级别,任何文档或者浏览器窗口发生的交互,都要通过绑定事件进行交互
事件有DOM0,DOM2和DOM3
     DOM0级：规定了行内事件的绑定
     DOM2级：新增加了通过addEventListener来绑定事件,还有ie下面的通过attachEvent来进行绑定
     DOM3级：新增了一些事件（例如移动端中的一些事件）
```

### 八/捕获冒泡顺序,Dom事件模型

```js
 鹿总,不了解Dom事件模型:捕获和冒泡
 	捕获,由外向内
	冒泡,由内向外
```

### 九/常用的HTTP状态码

```js
陈旭，鹿总，智有强
```

### 十/创建对象的几种方法

### 十一/call apply bind的区别

### 十二/promise的优缺点，什么是generator函数,generator函数和async/await区别

```js
王慧妍
```

### 十三/手写一个sleep函数

```js
/**
 * sleep函数
 */
const sleep = (time) => {
  return new Promise((resolve, reject) => {
    setTimeout(resolve, time);
  })
}
```

### 十四/本地存储和cookie的区别

```js
陈旭，本地存储包含那些不了解
```

### 十五/为什么产生了跨域/跨域产生的原因

智友强，关键字**同源策略**

```js
因为浏览器的同源策略,
    
什么是同源策略,协议域名端口号一致,一个不一致就会产生跨域
```

### 十六开发当中常用的跨域解决方式

```js
https://github.com/2209951505/mnms#5%E8%A7%A3%E5%86%B3%E8%B7%A8%E5%9F%9F%E7%9A%84%E6%96%B9%E5%BC%8F
```

### 十七/什么是原型链

### 十八/什么是闭包

```js
陈旭
```

### 十九/什么情况产生内存泄漏

```js
1.变量未回收
邱航,智有强
2.定时器未及时清除
3.闭包不当使用

一个未声明变量的引用会在全局对象中创建一个新的变量。在浏览器的环境下，全局对象就是 window，也就是说：

function foo(arg) {
    bar = "aaaaa";
}
实际上等价于
function foo(arg) {
    window.bar = "aaaaa";
}
function foo() {
    this.variable = "qqqqq";
}
//this 指向全局对象（window）
foo();
 为了防止这种错误的发生，添加 'use strict'; 语句
```

### 二十/防抖节流

### 二一/判断一个元素是否是数组

```js
* 正确:
1.Array.isArray()
2.Object.prototype.toString().call()	邱航
3.instanceof	let a = [];		a instanceof Array; //true
		

* 反例
typeof arr //Object

Object.prototype.toString().call()补充--补充---补充---补充----补充--补充--补充--补充---------

Object.prototype.toString().call()可以获取到对象的不同类型，例如

let a = [1,2,3]
Object.prototype.toString.call(a) === '[object Array]';//true
它强大的地方在于不仅仅可以检验是否为数组，比如是否是一个函数，是否是数字等等

//检验是否是函数
let a = function () {};
Object.prototype.toString.call(a) === '[object Function]';//true
//检验是否是数字
let b = 1;
Object.prototype.toString.call(a) === '[object Number]';//true
```

### 二二/map和forEach的区别

```js
相同点
每次执行匿名函数都支持三个参数，参数分别为item（当前每一项），index（索引值），arr（原数组）
第三个参数用法未找到
区别
forEach()方法不会返回执行结果，而是undefined。
也就是说，如果需要的话,除了遍历,forEach()有能力修改原来的数组。
而map()方法会得到一个新的数组并返回。
```

### 二三/get和post的区别

```js
1.是否密文
2.发送次数
3.是否在url显示(陈旭这处少)
```

### 二四/模块化和组件化的区别

```js
组件化：把一个模块划分成一个一个小的内容，例如：轮播图，二级导航。

模块化：把功能划分成一个模块，重心在设计和开发阶段
```

### 二五/git 常用命令 

### 二六/sass less	的区别

```js
智有强
```

### 二七/异步操作有那些

```js
延时器
ajax
promise
generator
async/await

陈旭,没有说出来es6
```

### 二八/事件委托

### 二九/常用的数组方法

```js
pop	  	尾部删除 
push	尾部添加
shift	头部删除
unshift 头部添加
map foreach filter concat splice slice
concat：连接多个数组，返回新的数组
join：将数组中所有元素以参数作为分隔符放入一个字符

那些方法会改变原来的数组,王慧妍
sort()：对数组排序
reverse()：数组反转
splice(index, howmany, 新数据)：返回被删除元素所组成的数组。用于插入、删除或替换数组的元素
```

### 三十/取消冒泡事件的方法

```js
陈旭,忘记
chrome->e.stopPropagation
ie->cancelBubble
```

### 三一/阻止默认事件的方法











### 一/移动端适配

```js
智有强，关键词rem,用的较少

答:使用的是rem+js和媒体查询来做适配
rem是css3新出的单位，根据html根元素字体大小来对元素的宽度进行计算,默认16px，
可以根据js来进行动态计算

js+rem,代码:demo2
```

### 二/display：flex的属性

```js
王慧妍，英文
陈旭,英文,父子各6个没记住
```

### 三/垂直居中的方式,水平居中的方式

```js
智有强
陈旭，顺序混乱
```

### 四/flex 是哪几个属性的复合属性

```js
子 flex: flex-basis flex-grow flex-shrink

父 flex-flow: flex-direction flex-wrap

智有强	flex的复合属性
```

```js
邱航，问具体一点的问题
```

