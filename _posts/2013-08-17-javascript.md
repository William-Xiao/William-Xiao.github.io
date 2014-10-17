---
layout: post
title: JavaScript变量的生命周期
description: 最近看国外经典教材的时候发现JavaScript与熟知的Java,C,C++都不同的特性，其中一个就是变量的生命周期。
keywords: 
category: JavaScript
---

最近看国外经典教材的时候发现JavaScript与熟知的Java,C,C++都不同的特性，其中一个就是变量的生命周期。
 
1.在JavaScript中，对于for循环中定义的i变量，其生命周期在循环结束后仍然是有效的。

```JavaScript
for (var i=0; i < 10; i++){
    doSomething(i);
}
alert(i); //10
```

这样的特性对于我们传统的习惯来说是不可理解的，这是因为JavaScript变量作用范围没有语句块的概念，他并不像JAVA一样在for循环内部声明的变量，在for循环外部就不能使用。
 
2.对于全局变量和局部变量的区分，要对var的使用特别注意。

```html
<html>
    <head></head>
    <body>
        <script type="text/javascript">
            var global_one = "I am global";
            function fun(){
                global_two = "I am global too";
                var local_one = "I am local";
            }
            alert(global_one); // "I am global"
            //alert(global_two);// error
            //alert(local_one);//error

            fun();
            alert(global_one); // "I am global"
            alert(global_two);// "I am global"
            //alert(local_one);//error
        </script>
    </body>
</html>
```

从上面的实例可以看到两点：

* JavaScript中的方法内部定义变量的时候如果没有加var，就是全局变量；否则为局部变量；
* 当fun()没有执行的时候，方法内部的全局变量是不会声明并且定义的。
 
Reference:
<http://www.blogjava.net/ycyk168/archive/2008/06/27/211182.html>
