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

### 23. 减少http请求次数

```
鹿总

```

 打包

精灵图

防抖节流

### 24. `webpack`

鹿总

1. 输入输出 entry,output
2. loader   sass-loader less-loader file-loader url-loader postcss-loader
3. plugins(插件)   htmlwebpackplugins  cleanwebpackplugins webpackderverhot 

### 25.数据可视化

echarts   d3

### 26. ajax问题

回调地狱问题

### 27.事件循环

js是单线程的程序,如果想要达到更好的用户体验,需要配合异步达到更好的效果,当代码从上到下依次执行的时候,碰到同步代码会进行执行,碰到异步代码会放到异步队列当中,等异步队列执行到这个地方之后,会判断是否触发,但是异步队列是一个队列结构,先进先出,可能我们需要让某些条件优先执行,那么就需要区分宏任务和微任务,微任务要优先执行,而宏任务要次一级去执行,常见的微任务有 Primose.then 宏任务定时器等等

### 28.数组方法

push pop shift unshift map foreach filter concat splice slice

### 29.判断数组

Array.isArray    instanceof     Object.prototype.toString.call([])

### 30. 输入url到加载完

重定向-> 拉取缓存-> DNS解析-> 发出请求(三次握手四次挥手)->建立连接->接受文件->渲染->展示

### 31. 遍历对象 & 数组

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

1. 默认的事件是冒泡
2. 委派的原理是冒泡
3. 委派是把事件绑定在父元素上,当事件冒泡到父元素上统一处理

好处:

* 动态创建的DOM可以绑定事件
* 优化,把多个事件合并为一个

### 33. 接口请求方法

get post  put delete 

### 34. css类名冲突怎么解决？

CSS modules

### 35. 权重

!important>行内>id>class>标签>*

### 36. 数组去重有哪些方法 & 排序

冒泡  indexof set 

冒泡  sort

### 37. 兼容性问题

事件对象

动画过度,阴影,渐变等

flex->box

### 38. 移动端适配 & 响应式

响应式: flex

移动端适配: rem

