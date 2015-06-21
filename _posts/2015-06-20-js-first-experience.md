---
published: true
layout: post
title:  "JavaScript初体验"
date:   2015-06-20
category: work
---

其实已经不算初体验了，
毕竟虽然没有全职的JavaScript开发经历，
但是或多或少的使用也算是对JavaScript略熟。

刚好之前买了一本《JavaScript语言精粹》，
今天刚好有空把它翻了一遍。
所以有感而发想写一篇关于JavaScript的博文，
谈谈印象比较深的几个点，和一些疑惑。

【函数即变量，变量即函数】

最开始我接触的其实是Node.js，
当时我记得对Node.js的介绍里面，
经常会说到为什么Node选用了js作为编程语言而不是其他语言。
原因是因为JavaScript天生适合异步和回调。
当时给我造成了一个误解，
以为回调地狱就是JavaScript语言天生自带的。
其实并不是，只不过是JavaScript对函数的支持太灵活，

对于C++/Java传统语言来说，
函数就是函数，变量就是变量。
而JavaScript里面的函数和变量几乎没什么差别。
所以自然对于回调函数的支持再顺溜不过。

【JSON就是最天然的RPC通信序列化语言】

个人觉得JSON是JavaScript最伟大的副产品，可能没有之一。
对于传统语言C++/Java之类的，在服务端编程中，基本上都是需要借助第三方RPC工具来进行通信，
而且RPC工具使用都非常不方便，就拿thrift来说，每次都是先写一个xx.thrift文件，然后再使用thrift工具
将xx.thrift文件转换成一堆源代码，然后再把这些源代码加入工程。
每次增删一些属性都需要重新生成这些源代码重新编译。劳神费力，烦得要死。

而在JavaScript里面，字符串和结构体的转换直接就是
`JSON.stringify` 和 `JSON.parse` 来搞定。
还有比这更酸爽的吗？

编程语言的演进，个人认为就应该是越容易上手，才能越大程度的解放生产力。
而性能其实是次要的，幸运的是，越来越多人已经开始意识到这一点。
而JSON大大的简化了数据结构序列化这个过程，
所以我个人认为JSON是JavaScript最伟大的副产品。

【原型继承，闭包等】

不知道为什么很多人谈到JavaScript就喜欢谈论这些东西，
仿佛这些是一些很高逼格的东西一样。
其实只要明白【作用域链只和定义的时候有关，和调用的时候无关。】
就可以把作用域链弄明白了，
其他知识点就自然能推理出来。

有些人学一门语言都喜欢讨论那些看上去逼格很高的特性，
比如有些人讨论C++，
有时候连vector的内存分配这种基础概念都没弄明白，
就开口闭口谈论template是不是图灵完备。
为了装逼也是拼了。

如果不去讨论那些装逼特性的话，
其实JavaScript本身是一个非常简单的语言，
从一些数据结构的设计就可以看出来：

比如Array，可以任性的随意使用任何下标直接赋值，
反正他的大小会随之变化。

比如Object，可以任性的动态增加它的属性，
所以甚至在JavaScript里面都不需要map，
因为Object就是比map更强大的映射类型。
还可以无限嵌套。

比如函数甚至都含有一个内置变量arguments，
使得函数调用的参数可以丧心病狂的灵活。
根据传入参数的不同组合，实现不同的功能。

比如原生支持正则表达式。

【一些个人疑惑和期待】

1. 我很清楚jsonp的出现是为了应对浏览器的跨域问题而出现的。
但是毕竟在url里面写上callback回调函数，
然后返回的数据是一个函数调用的代码。
总觉得不够优雅。难道不能有更优雅的解决方案吗？

2. 回调地狱的解决方案promise似乎也不够优雅。
听说ECMAScript 6th会有更好的解决方案，
好像是什么generator之类的什么鬼想不起来了，
之后再跟进了解一下。 

3. 现在因为Node.js的出现，前端开发人员也开始蚕食后端开发人员的工作。
但是Node.js虽然很火热，其实个人不认为它是最佳的js后端解决方案。
个人认为fib.js之类的协程解决方案更适合后端开发逻辑。
不过显然生态也很重要，Node.js的生态发展很不错。
即使Express作者宣布转向go了，Node.js的火热程度似乎也没用受到任何衰减。
这让我对Node.js一直诟病的同时，也不得不对它的前景抱着不小的期许。

4. 为什么前端界造轮子的风气如此的严重？

【《JavaScript语言精粹》简单书评】

最后再说说关于《JavaScript语言精粹》，
我手头上也有一本《JavaScript权威指南》。
这两本书让我想起当年学C++的时候，
当有新手问如何入门C++的时候，就会有一些装逼的学长说去把MSDN手册看一遍就行了。
现在想想简直坑死人不偿命。
而《JavaScript权威指南》就给我一种非常冗长非常枯燥的说明书一样的感觉，
漫无重点，完全不适合入门。
而《JavaScript语言精粹》就好得多。
不啰嗦不装逼，三个字：接地气。
