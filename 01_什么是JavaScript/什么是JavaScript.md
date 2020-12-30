# 什么是JavaScript



## 1.历史回顾

1995年，网景公司的工程师Brendan Eich开发了一个叫Mocha的脚本语言，主要用于客户端处理简单的数据验证。发布前夕，为了搭上热点临时改名JavaScript。

在网景公司发展JavaScript的同时，微软也在在家的IE3中实现了JavaScript（名为JScript）。

两个巨头的对抗使得JavaScript的发展两级分化，语法和特性无法统一。终于在1997年，JavaScript1.1被提交到欧洲计算机制造商协会(Ecma)的第39技术委员会（TC39），目的在于将JavaScript标准化为一门通用、跨平台、厂商中立的脚本语言。最终，TC39委员会打造了**ECMAScript脚本语言标准**。各大浏览器厂商也都已ECMAScript作为自己JavaScript实现的依据。



## 2.JavaScript实现

尽管ECMAScript是语言标准，但我们可能更习惯说JavaScript。那么JavaScript和ECMAScript是什么关系呢？

> ECMAScript是JavaScript的规格，JavaScript是ECMAScript的实现。

完整的JavaScript包含以下3个部分：

+ 核心（ECMScript）
+ 文档对象模型（DOM）
+ 浏览器对象模型（BOM）

![](JavaScript01.png)



### ECMAScript

ECMAScript，定义了这门脚本语言的基准；该语言也不局限于浏览器，Web浏览器仅仅是ECMAScript实现的一种宿主环境，服务器端Node.js也实现了宿主环境。

ECMA262(ECMAScript)主要描述或定义了以下部分：

+ 语法
+ 类型
+ 语句
+ 关键字
+ 保留字
+ 操作符
+ 全局对象

#### ECMAScript版本

ECMAScript（以下简称ES）第三版增加了许多东西，标志着ECMAScript成为一门真正的编程语言。

ES4对该语言进行了彻底修订，但是很可惜在发布前夕被放弃。

ES5于2009年发布，是目前主流浏览器兼容性最好的一个版本。

ES6于2015年发布，正式支持类，模块，迭代器，生成器，箭头函数等，

...

ES10，也称ES2019，发布于2019年6月。