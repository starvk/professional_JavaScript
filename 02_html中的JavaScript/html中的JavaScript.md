# html中的JavaScript

## `<script>`元素

将JavaScript插入HTML的主要方法是使用`<script>`元素。`<script>`元素有以下属性：

+ async ：可选，标识应该立即开始下载脚本，但不能阻止其他页面动作，即异步下载脚本。该属性只对外部脚本有效。
+ charset：可选。使用src属性指定代码字符集，现在很少使用。
+ defer：可选。标识脚本可以延迟到文档被完全被解析和显示之后再执行。该属性只对外部脚本有效。
+ language：废弃。
+ src：可选，表示包含要执行的代码的外部文件。
+ type：可选。代替language，表示代码块中脚本语言的内容类型。如果这个值是modeule，则代码会被当做ES6模块，此时在代码中才能出现import和export关键字。

### 使用`<script>`的两种方式

1. 直接在html中嵌入JavaScript代码

   要嵌入行内JavaScript代码，直接把代码放在`<script>`元素中即可

   ```html
   <script>
   	function sayHi() {
   		console.log("Hi!");
   	}
   </script>
   ```

   包含在`<script>`内的代码会被从上到下解释。在`<script>`元素中的代码被计算完成之前，页面的其余内容不会被加载，也不会被显示，换句话说会阻塞页面的加载。

2. 引入外部JavaScript文件

   使用JavaScript的src属性可以引入外部的JavaScript文件，例如

   ```html
   <script src="example.js"></script>
   ```

   页面会加载一个名为example.js的外部文件。在解释该外部文件时，页面也会阻塞。

   **注意：**按照惯例，外部JavaScript文件的扩展名是.js。不过这不是必需的，因为浏览器不会检查所包含JavaScript文件的扩展名。不过需要注意：服务器经常会根据文件扩展来确定响应的正确MIME类型。如果不打算使用.js扩展名，一定要确保服务器能返回正确的MIME类型。

   另外：使用src属性的`<script>`元素会忽略行内代码。

   同时，如果引入了多个外部文件，浏览器会按照`<script>`在页面上出翔的顺序依次解释他们。



### 标签位置

JavaScript代码在下载、解析过程中会阻塞页面的加载，因此我们通常将所有的JavaScript代码或引入的JavaScript外部文件放在`</body>`标签前面，例如：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document</title>
</head>
<body>
    <!-- 页面内容 -->
    <script src="example1.js"></script>
    <script src="example2.js"></script>
</body>
</html>
```

### 推迟执行脚本

`<script>`标签的defer属性表示脚本在执行的时候不会改变页面的结构，即脚本延迟到页面解析完毕后再运行。因此使用defer属性的`<script>`标签可以放在页面的`<head>`标签中。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document</title>
    <script src="example1.js" defer></script>
    <script src="example2.js" defer></script>
</head>
<body>
    <!-- 页面内容 -->    
</body>
</html>
```

HTML5规范要求脚本必须按照它们出现的顺序执行，因此第一个推迟的脚本会在第二个推迟的脚本之前执行，不过在实际当中，推迟执行的脚本不一定总会按顺序执行或在DOMContentLoaded事件之前执行。



### 异步执行脚本

HTML5为`<script>`元素定义了async属性，用于异步加载并解析脚本。和defer不同的是，标记为async的脚本并不能保证按照出现的次序执行。

async属性的目的在于告诉浏览器，不必等脚本下载和执行完后再加载页面，同样也不必等到该异步脚本下载和执行后再加载其他脚本。

