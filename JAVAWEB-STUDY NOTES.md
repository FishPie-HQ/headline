JAVAWEB-STUDY NOTES



checkbox是复选框

# CSS样式

text-align:center	行内元素，块级元素居中

font-family:幼圆	字体样式为幼圆

border:2px solid yellow	边线宽2个像素，实线，黄色

border-radius:4px	圆形边角，4个像素

```
	width: 160px;
    height: 50px;
    background-color: lightsalmon;
    color: red;
    /*字体颜色*/
    font-size: 19px;
    /* 字体大小 */
    font-family: 'sans-serif';
    /* 字体样式 */
    border: 2px solid slategrey;
    /* 边线，不占用内部空间 solid实线 */
    margin-right:10px;
    /*设置右外边距为10个像素*/
    margin:10px 20px;
    /*设置上外边距为10个像素，下边距为20像素*/
    margin:10px 20px 30px 40px;
    /*设置上外边距为10个像素，右边距为20像素，下边距为30像素，左边距为40像素(clockwise顺时针)*/
    padding-top:20px;
    /*设置上内边距为20个像素*/
    margin: 0px auto;
    /* 上外边距为0px quto代表左右平均分配，就是居中  */
```

## 元素选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>

        /*
        1 元素选择器 根据标签的名字确定样式的作用元素
            语法：标签名{}
            缺点：某些同名的元素不希望使用某些样式，某些不同名的元素也使用该样式，都无法协调

        2 id选择器 根据标签的id确定样式的作用元素
                    一般一个页面中的每个元素的id是唯一的
            语法：#id名{}
            缺点：id值有唯一性，样式只能作用到一个元素上

        3 class选择器 根据元素的class属性值确定样式的作用元素
                        元素的class属性值可以重复 而且一个元素的class属性可以有多个值
            语法：.class属性值()
            缺点：优先级较#即id选择器低
        */

        /*input {*/
        /*    width: 160px;*/
        /*    height: 50px;*/
        /*    background-color: lightsalmon;*/
        /*    color: red;*/
        /*    !*字体颜色*!*/
        /*    font-size: 19px;*/
        /*    !* 字体大小 *!*/
        /*    font-family: 'sans-serif';*/
        /*    !* 字体样式 *!*/
        /*    border: 2px solid slategrey;*/
        /*    !* 边距 solid宽度 *!*/
        /*}*/

        /*#btn4{*/
        /*    width: 160px;*/
        /*    height: 50px;*/
        /*    background-color: lightsalmon;*/
        /*    color: red;*/
        /*    !*字体颜色*!*/
        /*    font-size: 19px;*/
        /*    !* 字体大小 *!*/
        /*    font-family: 'sans-serif';*/
        /*    !* 字体样式 *!*/
        /*    border: 2px solid slategrey;*/
        /*    !* 边距 solid宽度 *!*/
        /*}*/

        .shapeClass{
            width: 80px;
            height: 40px;
            border-radius: 5px;
        }
        .colorClass{
            background-color: greenyellow;
            color: wheat;
            border: 3px solid green;
        }
        .fontClass{
            font-size: 20px;
            font-family: '隶书';
            line-height: 30px;
        }
    </style>

</head>
<body>

<input id="btn1" class="shapeClass" type="button" value="按钮">
<input id="btn2" class="colorClass" type="button" value="按钮">
<input id="btn3" class="fontClass" type="button" value="按钮">
<input id="btn4" class="fontClass colorClass fontClass" type="button" value="按钮">

<button id="btn5">按钮</button>

</body>
</html>
```

## js的引入方式

![1700731769172](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700731769172.png)

## js运算符

![1700733470067](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700733470067.png)

## js的循环结构

```html
<script>
    document.write("张三")
    document.write("<h1>张三</h1>")


    for (var i = 1;i <= 9;i++){
        for (var j = 1;j <= i;j++){
          document.write(j + " * " + i + " = " + i * j + "&nbsp;&nbsp;&nbsp");

        }
        document.write("<hr>");
    }

    var arr = ["京","沪","粤"];
    document.write("<ul>");
    for (var index = 0;index < arr.length;index++){
        document.write("<li>" + arr[index] +"</li>");
    }
    document.write("</ul>")

    document.write("<hr>");

    for (var index in arr){
        document.write("<li>" + arr[index] +"</li>");
    }

  </script>
```

## js中创建对象

![1700739336040](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700739336040.png)

## js中JSON的使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <script>
        /*
        *
        * JSON格式的语法
        * var personStr = '{  "属性名":"属性值","属性名":"属性值","属性名":{}，"属性名":["","",""],:"属性名":[{},{},{}]  }'
        * 属性名 必须用 "" 包裹上                                    对象              数组              对象数组
        * 属性值、字符串 必须用 ""包好,数字可以不处理
        *
        * */

        //这是一个JSON格式的字符串
        var personStr = '{ "name":"张三","age":10,"dog":{"name":"小花"},' +
            '"loverPrinters":["啊","吧","从"],"friends":[{"fname":"四"},{"fname":"五"},' +
            '{"fname":"六"}] }'

        console.log(personStr);
        console.log(typeof personStr);
        console.log(personStr.name);//undefined

        //通过JSON.parse()可以将一个JSON串转换为一个对象
        var person = JSON.parse(personStr);
        console.log(person);
        console.log(person.name);
        console.log(person.loverPrinters);
        console.log(person.loverPrinters[0]);

        //通过JSON.stringify() 将一个对象转换为JSON串
        var person1 = JSON.stringify(person);
        console.log(person1);

    </script>

</head>
<body>

</body>
</html>
```

## js中使用JSON

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <script>
        /*
        *
        * JSON格式的语法
        * var personStr = '{  "属性名":"属性值","属性名":"属性值","属性名":{}，"属性名":["","",""],:"属性名":[{},{},{}]  }'
        * 属性名 必须用 "" 包裹上                                    对象              数组              对象数组
        * 属性值、字符串 必须用 ""包好,数字可以不处理
        *
        * */

        //这是一个JSON格式的字符串
        var personStr = '{ "name":"张三","age":10,"dog":{"name":"小花"},' +
            '"loverPrinters":["啊","吧","从"],"friends":[{"fname":"四"},{"fname":"五"},' +
            '{"fname":"六"}] }'

        console.log(personStr);
        console.log(typeof personStr);
        console.log(personStr.name);//undefined

        //通过JSON.parse()可以将一个JSON串转换为一个对象
        var person = JSON.parse(personStr);
        console.log(person);
        console.log(person.name);
        console.log(person.loverPrinters);
        console.log(person.loverPrinters[0]);

        //通过JSON.stringify() 将一个对象转换为JSON串
        var person1 = JSON.stringify(person);
        console.log(person1);

    </script>

</head>
<body>

</body>
</html>
```

## java中使用JSON

```java
public class TestJson {
    @Test
    public void testWriteJson() throws JsonProcessingException {
        Dog dog = new Dog("大黄");
        Person person = new Person("张三",20,dog);

        ObjectMapper objectMapper = new ObjectMapper();
        String personStr = objectMapper.writeValueAsString(person);
        System.out.println(personStr);
    }

    @Test
    public void testReadJson() throws JsonProcessingException {
        String personStr = "{\"name\":\"张三\",\"age\":20,\"dog\":{\"name\":\"大黄\"}}"; 
        ObjectMapper objectMapper = new ObjectMapper();
        Person person = objectMapper.readValue(personStr, Person.class);
        System.out.println(person);
    }
}
```

## js中表单常用事件

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <script>
        function fun1() {
            console.log("单击了1")
        }

        function fun2() {
            console.log("单击了2")
        }

        function fun3() {
            console.log("双击了1")
        }

        function fun4() {
            console.log("鼠标悬停了")
        }

        function fun5() {
            console.log("鼠标移动了")
        }

        function fun6() {
            console.log("鼠标离开了")
        }

        function fun7() {
            console.log("按键按下了")
        }

        function fun8() {
            console.log("按键抬起了")
        }

        /*
        事件的绑定方式
            1 通过元素的属性绑定     on***
            2 通过 DOM 编程动态绑定
            注意事项：
                1 一个事件可以绑定多个函数
                2 一个元素可以绑定多个事件

         */
    </script>

</head>
<body>

<input
        type="button"
        value="图图图！"
        onclick="fun1(),fun2()"
        ondblclick="fun3()"
>
<br>
<img
        src="/workspaceforWEBSTORM/img/frost%20leaves.jpg"
        title="霜叶"
        alt="霜叶怎么没显示？"
        onmouseover="fun4()"
        onmousemove="fun5()"
        onmouseleave="fun6()"
>
<br>
<input
        type="text"
        onkeydown="fun7()"
        onkeyup="fun8()"
>

</body>
</html>
```

## DOM编程处理事件

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <script>
        /*
        事件的触发
            1 行为触发
            2 DOM编程触发

         */
    </script>

    <script>

        //通过body中的onload写法来完成事件绑定：
        // function ready() {
        //
        //     //通过dom获得要操作的元素
        //     var btn = document.getElementById("btn1");
        //     //绑定一个单击事件
        //     btn.onclick = function (){
        //         alert("单击，单击！")
        //     }
        // }

        //通过window.onload来完成事件绑定:
        window.onload = function () {
                //通过dom获得要操作的元素
                var btn = document.getElementById("btn1");
                //绑定一个单击事件
                btn.onclick = function (){
                    alert("单击，单击！")
                    //点击按钮变成蓝色
                    div1.style.backgroundColor = "blue";
                }

                //为div1绑定事件
                var div1 = document.getElementById("d1");
                //绑定一个单击事件
                div1.onclick = function (){
                    //单击后变成红色
                    div1.style.backgroundColor = "red";
                }
            }

    </script>

    <style>
        /*div1的默认属性*/
        .div1{
            width: 100px;
            height: 100px;
            background-color: greenyellow;
        }
    </style>

</head>
<!--<body onload="ready()">-->
<body>
<!--让浏览器加载完毕后再执行ready函数里的内容(最后执行ready函数内的内容)-->
<button id="btn1">按钮</button>

<div id="d1" class="div1">

</div>



</body>
</html>
```

## BOM编程常见的API的演示

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <script>

        /*
        window
            三种弹窗方式
            （window.可以省略不写）
                alert
                prompt
                confirm

            定时任务
                setTimeout
                ...

         history 窗口的访问历史


         */

        window.onload = function (){

            var hint = document.getElementById("btn1");
            var enter = document.getElementById("btn2");
            var confirm = document.getElementById("btn3");
            hint.onclick = function (){
                window.alert("单击！单击！");
            }
            enter.onclick = function (){
                var res = window.prompt("输入！输入！");
                console.log(res);
            }
            confirm.onclick = function (){
                window.confirm("确认！确认");
            }
        }

        function fun4(){
            window.setTimeout(function () {
                console.log("hello");
            },2000);
        }

        function funB(){
            //向前翻页
            history.back();
        }
        function funA() {
            //向后翻页
            history.forward();
            // history.go(1)//向前翻一页
        }

        function funC() {
            location.href = "http://www.bilibili.com"//修改地址栏的url
        }

    </script>

</head>
<body>
<button id="btn1" class="hint">信息提示框</button>
<button id="btn2" class="enter">信息输入框</button>
<button id="btn3" class="confirm">信息确认框</button>
<button onclick="fun4()">两秒后向控制台打印hello</button>

<hr>

<button onclick="funB()">上一页</button>
<button onclick="funA()">下一页</button>

<hr>

<a href="http://www.bilibili.com" target="_blank">bilibili</a>
<button onclick="funC()">bilibili</button>


</body>
</html>
```

## DOM编程获取元素的方式

![1700817883829](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700817883829.png)

DOM操作元素属性的方式



![1700818835243](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700818835243.png)

## 在父元素中追加子元素

![1700822264311](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700822264311.png)

默认子元素加在最后

可以通过 

`元素名.insertBefore(新元素,参照元素);`

来实现在参照元素前的插入

![1700822488168](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700822488168.png)

替换子元素

![1700822911258](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700822911258.png)

删除子元素

![1700822993991](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700822993991.png)

![1700823324228](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700823324228.png)

js中正则表达式的使用

[JavaScript 正则表达式 | 菜鸟教程 (runoob.com)](https://www.runoob.com/js/js-regexp.html)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

<script>
    /* 正则表达式 */

    //定一个正则表达式
    var reg = /o/;
    //定义一个字符串
    var str = "hello world!";
    //校验是否符合正则表达式
    console.log(reg.test(str));//true
    //判断 str 这个字符串中是否含有 o

    var str1 = "YEEEEEE..AUUUUUU!";
    var n = str1.search(/Auuuuuu/i);
    document.write(n);//搜索字符串 "Auuuuuu", 并显示匹配的起始位置：

    document.write("<br>");

    var str2 = /^hello$/;//以hello开头和结尾s
    var test1 = "hello";
    var test2 = "hellohello";
    document.write(str2.test(test1));//true
    document.write("<br>");
    document.write(str2.test(test2));//false

    var str3 = /^[a-h]$/i;//要求第一位是a~h的字符，不区分大小写
    var str3 = /^[a-hA-Z][1-6]$/i;//要求第一位是a~h的字符，不区分大小写,第二位是1-6的字符,且必须要有两位

    var str3 = /^[a-hA-Z][1-6]{2，7}$/i;//要求第一位是a~h的字符，不区分大小写,第二位是1-6的字符，第二位后2-7位要满足第二位的条件
    //该字符整体长度为 4 - 9



</script>


</head>
<body>


</body>
</html>
```

## dom4j解析xml代码（非重点，仅作了解，知道java可以来解析xml文件）

//dom4j只是众多解析技术中的一种

dom4j.java

```java
package com.atguigu;

import org.dom4j.Attribute;
import org.dom4j.Document;
import org.dom4j.DocumentException;
import org.dom4j.Element;
import org.dom4j.io.SAXReader;
import org.junit.Test;

import java.io.InputStream;
import java.util.List;

/**
 * ClassName:TestDom4j
 * Package: com.atguigu
 * Description:
 *
 * @Author fishPie_one
 * @Create 2023/11/24 23:36
 * @Version 1.0
 */
public class TestDom4j {

    @Test
    public void testRead() throws DocumentException {
        //  读取jdbc.xml配置文件，获得document对象
        SAXReader saxReader = new SAXReader();
        //  通过类加载器获得指向字节码根路径下的指定文件的输入流
        InputStream resourceAsStream = TestDom4j.class.getClassLoader().getResourceAsStream("jdbc.xml");
        //  通过输入流获得配置文件，解析成一个dom对象
        Document document = saxReader.read(resourceAsStream);
        //  从document对象上获取配置文件中的信息
        /*
          Node 结点
            Element     元素结点
            Attribute   属性结点
            Text        文本节点

         */
        Element rootElement = document.getRootElement();
        System.out.println(rootElement.getName());
        //获取元素的子元素,子元素都是<Element>,所以可以写成<Element>泛型
        List<Element> elements = rootElement.elements();
        for (Element element : elements){
            System.out.println("\t" + element.getName());

            //从元素上获取属性
            Attribute idAttribute = element.attribute("id");
            System.out.println("\t\t" + idAttribute.getName() + " = " + idAttribute.getValue());

            //  继续读取子元素
            List<Element> eles = element.elements();
            for (Element ele : eles){
                System.out.println("\t\t" + ele.getName() + ":" + ele.getText());
            }
        }

    }

}

```

jdbc.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!--
1.根标签只能有一个
2.第一行永远都是 <?xml version="1.0" encoding="UTF-8"?> 前面不能有任何东西
3.xml是有约束的  约束用于限定xml内部能编写的内容
    dtd     简单  不够细致
    schema  复杂  约束较为细致

-->

<jdbc>
    <dev id = "001">
        <username>root</username>
        <password>root</password>
        <driver>com.mysql.cj.jdbc.Driver</driver>
        <url>jdbc:mysql://localhost:3306/test</url>
    </dev>
    <test id = "002">
        <username>root</username>
        <password>654321</password>
        <driver>com.mysql.cj.jdbc.Driver</driver>
        <url>jdbc:mysql://localhost:3306/test</url>
    </test>
    <formal id = "003">
        <username>root</username>
        <password>123456</password>
        <driver>com.mysql.cj.jdbc.Driver</driver>
        <url>jdbc:mysql://localhost:3306/test</url>
    </formal>
</jdbc>
```

## Tomcat

web应用服务器

web开发界的GTR，比它好的要收费，Tom免费、更新速度快且稳定！！！

![1700842416678](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700842416678.png)

![1700842549010](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700842549010.png)

Tomcat在IDEA运行javaweb项目的原理

![1700892130120](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700892130120.png)

## HTTP简介

![1700892263546](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700892263546.png)

tomcat10还在使用http1.1

![1700892657585](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700892657585.png)

![1700895371222](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700895371222.png)

常见的响应码

![1700907312337](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700907312337.png)

## Servlet简介与运行原理

- 不是所有的JAVA类都能用于处理客户端请求,能处理客户端请求并做出响应的一套技术标准就是Servlet（小服务程序）
- Servlet是运行在服务端的,所以 Servlet必须在WEB项目中开发且在Tomcat这样的服务容器中运行

![1700909070577](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700909070577.png)

## **Servlet开发流程（重点）

![1700928084455](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700928084455.png)

### Content-Type响应头的设置（很重要，以至于有一个专门的API）

![1700931259253](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700931259253.png)



### 关于web.xml

![1700932007591](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700932007591.png)

![1700932550733](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700932550733.png)

![1700932570533](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700932570533.png)

通过注解的方式来实现html属性路径与servlet类的关联

![1700932789766](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700932789766.png)

可用注解更改为@WebServlet("/路径名")

![1700932813263](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700932813263.png)

![1700933285293](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700933285293.png)

（这是通过注解来配置多个urlPatterns的路径，一般一个路径就够了）

两种方式二选一

### servlet实例化的顺序设定

![1700934582433](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700934582433.png)

### Servlet的生命周期

![1700935022445](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700935022445.png)

**（不建议在service方法中修改成员变量，因为在并发编程时可能会引发线程安全问题）**

（因为它是单例的）

关于单例模式

[什么是单例模式？单例模式有什么作用？为什么要用单例模式_单例模式的作用-CSDN博客](https://blog.csdn.net/qq_36186690/article/details/82945836)

### servlet接口

![1700936490935](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700936490935.png)

### servlet的继承结构_HttpServlet

可以重写 service 方法，也可以重写 doGet 和 doPost 方法

如果重写了service方法，则重写的doGet和doPost方法就不生效了，因为service的优先级更高（doGet和doPost方法就在service方法里）

### servletConfig可获取web.xml中的servlet的初始配置信息

![1700988104339](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700988104339.png)

![1700988125380](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700988125380.png)

![1700988149131](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700988149131.png)

也可通过注解的方式来完成web.xml中的**初始信息的配置**

![1700988313698](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700988313698.png)

### servletContext的功能

servletContext可以为所有的servlet提供初始配置信息

配置方法：

web.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="https://jakarta.ee/xml/ns/jakartaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="https://jakarta.ee/xml/ns/jakartaee https://jakarta.ee/xml/ns/jakartaee/web-app_5_0.xsd"
         version="5.0">

    <context-param>
        <param-name>paramA</param-name>
        <param-value>valueA</param-value>
    </context-param>
    <context-param>
        <param-name>paramB</param-name>
        <param-value>valueB</param-value>
    </context-param>
</web-app>
```

此配置信息可都在/servlet1和/servlet2中查询到

```java
@WebServlet("/servlet3")
public class Servlet3 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        ServletContext servletContext = getServletContext();

        //获得一个指向项目部署位置下的某个文件/目录的磁盘真实路径的API
        String path = servletContext.getRealPath("upload");
        System.out.println(path);

        // 获得项目部署的上下文路径 项目的访问路径
        // 获取项目的上下文路径   项目的访问路径
        String contextPath = servletContext.getContextPath();
        System.out.println(contextPath);
    }
}
```

### HttpServletRequest获取请求行和请求头

```java
@WebServlet("/servlet4")
public class Servlet4 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //  行相关 GET/POST  uri   http/1.1
        System.out.println(req.getMethod());//获取请求方式    GET
        System.out.println(req.getScheme());//获取请求协议    http
        System.out.println(req.getProtocol());//获取请求协议及版本   HTTP/1.1
        System.out.println(req.getRequestURI());//获取请求的uri  项目内的资源路径    /demo03/servlet4
        System.out.println(req.getRequestURL());//获取请求的url  项目资源的完整路径   http://localhost:8080/demo03/servlet4
        /*
        URI 统一资源标识符     interface URI{}
        URL 统一资源定位符     class URL implement URI{}
         */
        System.out.println();
        System.out.println(req.getLocalPort());//本应用容器的端口号          8080
        System.out.println(req.getServerPort());//客户端发请求时使用的端口号   8080
        System.out.println(req.getRemotePort());//客户端软件的端口号         3665 (chrome浏览器的端口号)edge的为2532

        // 头相关  key:value   key:value
        // 根据名字单个获取请求头
        String accept = req.getHeader("Accept");
        System.out.println("Accept:" + accept);

        // 获取本次请求中所有的请求头的名字
        Enumeration<String> headerNames = req.getHeaderNames();
        while (headerNames.hasMoreElements()){
            String hname = headerNames.nextElement();
            System.out.println(hname + ":" + req.getHeader(hname));
        }

    }
}
```

控制台输出信息

| **GET**
**http**
**HTTP/1.1**
**/demo03/servlet4**
**http://localhost:8080/demo03/servlet4**
**8080**
**8080**
**4507** |
| ------------------------------------------------------------ |
| Accept:text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
host:localhost:8080
connection:keep-alive
cache-control:max-age=0
sec-ch-ua:"Google Chrome";v="119", "Chromium";v="119", "Not?A_Brand";v="24"
sec-ch-ua-mobile:?0
sec-ch-ua-platform:"Windows"
upgrade-insecure-requests:1
user-agent:Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36
accept:text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
sec-fetch-site:none
sec-fetch-mode:navigate
sec-fetch-user:?1
sec-fetch-dest:document
accept-encoding:gzip, deflate, br
accept-language:zh-CN,zh;q=0.9
cookie:Idea-4005eb13=dd0020ae-a5ba-4a74-a334-f92f71b6b471; Webstorm-8fd1475a=777788db-0203-4be0-90b4-dae01c286f45; JSESSIONID=0FAE1A1449DEE03F454CC8EAD1A325A3 |

### 请求转发的特点（背诵）

- 请求转发通过HttpServletRequest对象获取请求转发器实现
- 请求转发是服务器内部的行为,对客户端是屏蔽的
- 客户端只发送了一次请求,客户端地址栏不变
- 服务端只产生了一对请求和响应对象,这一对请求和响应对象会继续传递给下一个资源
- 因为全程只有一个HttpServletRequset对象,所以请求参数可以传递,请求域中的数据也可以传递
- 请求转发可以转发给其他Servlet动态资源,也可以转发给一些静态资源以实现页面跳转
- 请求转发可以转发给WEB-INF下受保护的资源
- 请求转发不能转发到本项目以外的外部资源

### 响应重定向的特点（背诵）

- 响应重定向通过HttpServletResponse对象的sendRedirect方法实现
- 响应重定向是服务端通过302响应码和路径,告诉客户端自己去找其他资源,是在服务端提示下的,客户端的行为
- 客户端至少发送了两次请求,客户端地址栏是要变化的
- 服务端产生了多对请求和响应对象,且请求和响应对象不会传递给下一个资源
- 因为全程产生了多个HttpServletRequset对象,所以请求参数不可以传递,请求域中的数据也不可以传递
- 重定向可以是其他Servlet动态资源,也可以是一些静态资源以实现页面跳转
- 重定向不可以到给WEB-INF下受保护的资源
- 重定向可以到本项目以外的外部资源

**在页面跳转方面，除了要求参数传递和访问WEB-INF中的资源，优先使用重定向**

## MVC架构模式

![1701100858895](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701100858895.png)

![1701157001214](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701157001214.png)



会话管理Session

```java
@WebServlet("/servlet1")
public class Servlet1 extends HttpServlet {
    @Override
    protected void service(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //接收请求中username对象
        String username = req.getParameter("username");

        //获得session对象
        HttpSession session = req.getSession();

        System.out.println(session.getId());
        System.out.println(session.isNew());

        //将username存入session
        session.setAttribute("username",username);

        //客户端响应信息
        resp.setContentType("text/html;charset=UTF-8");//如果没有这一步，下面的打印流会乱码
        resp.getWriter().write("成功");
    }
}
```

![1701176267693](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701176267693.png)

（获得session对象所要做的事）

默认的session最大闲置时间(两次使用同一个session中的间隔时间) 在tomcat/conf/web.xml配置为**30分钟**

### 请求域、会话域和应用域之间的关系

![1701180076946](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701180076946.png)

使用注解的方式配置过滤器的初始格式要重写init方法

（仅配置urlPartterns不需要重写init）

以下是一个示例代码

```java
@WebFilter(
        filterName = "loggingFilter",
        initParams = {@WebInitParam(name="dateTimePattern",value="yyyy-MM-dd HH:mm:ss")},
        urlPatterns = {"/servletA","*.html"},
        servletNames = {"servletBName"}
)
public class LoggingFilter  implements Filter {
    private SimpleDateFormat dateFormat ;

    /*init初始化方法,通过filterConfig获取初始化参数
    * init方法中,可以用于定义一些其他初始化功能代码
    * */
    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
        // 获取初始参数
        String dateTimePattern = filterConfig.getInitParameter("dateTimePattern");
        // 初始化成员变量
        dateFormat=new SimpleDateFormat(dateTimePattern);
    }
    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        // 参数父转子
        HttpServletRequest request =(HttpServletRequest)  servletRequest;
        HttpServletResponse  response =(HttpServletResponse)  servletResponse;
        // 拼接日志文本
        String requestURI = request.getRequestURI();
        String time = dateFormat.format(new Date());
        String beforeLogging =requestURI+"在"+time+"被请求了";
        // 打印日志
        System.out.println(beforeLogging);
        // 获取系统时间
        long t1 = System.currentTimeMillis();
        // 放行请求
        filterChain.doFilter(request,response);
        // 获取系统时间
        long t2 = System.currentTimeMillis();
        String afterLogging =requestURI+"在"+time+"的请求耗时:"+(t2-t1)+"毫秒";
        // 打印日志
        System.out.println(afterLogging);

    }
}
```





```java
private static ObjectMapper objectMapper;//静态方法只能调用静态属性

    static {
        objectMapper = new ObjectMapper();
    }

    //这样写的好处和坏处：
    /*
        写成静态方法调用静态属性objectMapper的好处是:

        提高性能。由于objectMapper是静态的,所以只需要初始化一次,之后可以重复利用,不需要每次都创建新的实例。这样可以提高性能。
        简化代码。可以直接通过类名调用objectMapper,而不需要先创建实例然后再调用。代码更简洁。

        坏处是:

        不易于测试。静态属性和方法都比较难以在测试中模拟或存根。
        可维护性较差。如果有很多静态属性和方法,类会变得很复杂,不利于代码的维护。
        可能产生线程安全问题。如果有多个线程同时调用objectMapper,则需要自行确保线程安全。
        代码复用性差。静态属性和方法与类耦合度高,如果想重用objectMapper则比较困难。
        所以一般情况下,除非是工具类或性能需要,否则不推荐将属性和方法设计为静态的,应该尽量采用面向对象的设计方式。
    */
```



### 将result对象转换为JSON串响应给客户端

```java
resp.setContentType("application/json;charset=UTF-8");
```

（可取tomcat的conf目录下的web.xml查看）



# ES6语法

## ES6模板字符串的拼接

使用 ` 着重号

`let str = ``;`

![1701275807429](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701275807429.png)

JAVA中的拼接（老泪纵横）

![1701275907371](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701275907371.png)

## 语法糖，与JAVA类有一点点类似

```html
<script>
        
        class Person {
            //属性（相较于JAVA无权限修饰符，且是弱对象）
            name1;
            age;
            //getter setter
            get name(){
                return this.name1;
            }
            set name(name1){
                this.name1 = name1;
            }

        }
        let person = new Person();
        person.name1 = "张三";//"张三"变形参,如果属性是name，则走的是属性复制
                             //好怪的语法
        console.log(person);
        
        
    </script>
```



npm软件：1.前端框架的下载工具   2.前端项目的管理工具

package.json相当于maven的pom.xml文件，在项目开发中可以减少项目源码占用的带宽

## Vue3 中 App.vue的写法要求

（.vue文件名称的首字母要大写）

![1701353864533](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701353864533.png)

# 前端工程化的关系

![1701354145611](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701354145611.png)

工程化vue项目组件的组织方式

![1701358001300](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701358001300.png)

# vue3响应式数据和setup语法糖

```html
<script>
//导入ref函数
import {ref} from "vue";
export default {
  setup() {

    //定义一些要展示到html上的数据  变量/对象
    /*
    响应式数据：在数据变化时，vue框架会将变量最新的值更新到dom树中，页面数据就是实时最新的.
    非响应式数据：在数据变化时，vue框架会将变量最新的值不会更新到dom树中，页面数据不是实时最新的.

    vue2中，数据不做特殊处理，默认就是响应式
    vue3中，数据要经过ref / reactive函数的处理才是响应式的
          ref reactive函数时vue框中给我们提供的方法，导入进来即可使用

    ref处理的响应式数据，在操作时需要注意
      在script标签中，操作ref的响应式数据需要通过.value的形式操作

     */

    let counter = ref(1);

    //让counter 自增的方法
    function counterIncr() {
      counter.value++;
    }

    //让counter 自减的方法
    function counterDecr() {
      counter.value--;
    }

    //显示counter值
    function showCounter(){
      alert(counter.value);
    }

    return {
      counter,//不加这个return相当于counter没有暴露出来，方法外无法使用
      counterIncr,
      counterDecr,
      showCounter
    }
  }
}

</script>

<template>
  <div>
    <button @click="counterIncr()">+</button>
    <span v-text="counter"></span>
    <button @click="counterDecr()">-</button>
    <button @click="showCounter">showCounter</button>
  </div>
</template>

<style scoped>

</style>

```

可转为（script标签中setup的作用）

```html
<script setup>
//导入ref函数
import {ref} from "vue";
//定义一些要展示到html上的数据  变量/对象
/*
响应式数据：在数据变化时，vue框架会将变量最新的值更新到dom树中，页面数据就是实时最新的.
非响应式数据：在数据变化时，vue框架会将变量最新的值不会更新到dom树中，页面数据不是实时最新的.

vue2中，数据不做特殊处理，默认就是响应式
vue3中，数据要经过ref / reactive函数的处理才是响应式的
      ref reactive函数时vue框中给我们提供的方法，导入进来即可使用

ref处理的响应式数据，在操作时需要注意
  在script标签中，操作ref的响应式数据需要通过.value的形式操作

 */

let counter = ref(1);//{value:10}

//让counter 自增的方法
function counterIncr() {
  counter.value++;
}

//让counter 自减的方法
function counterDecr() {
  counter.value--;
}

//显示counter值
function showCounter() {
  alert(counter.value);
}

</script>
```

# vue工程创建步骤

![1701360261105](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701360261105.png)



# 插值表达式

```html
<script setup type="module">
let msg ="hello vue3"
let getMsg= ()=>{
  return 'hello vue3 message'
}
let age = 19
let bee = '蜜 蜂'
// 购物车
const carts = [{name:'可乐',price:3,number:10},{name:'薯片',price:6,number:8}];
//计算购物车总金额
function compute(){
  let count = 0;
  for(let index in carts){
    count += carts[index].price*carts[index].number;
  }
  return count;
}
</script>

<template>
  <div>
    <h1>{{ msg }}</h1>
    msg的值为: {{ msg }} <br>
    getMsg返回的值为:{{ getMsg() }}  <br>
    是否成年: {{ age>=18?'true':'false' }} <br>
      
     <!--    spilt返回的是个数组，以空格分割,再通过reverse颠倒数组 ['蜂' '蜜']，join转换字符串，并将，换成- -->
    反转: {{ bee.split(' ').reverse().join('-') }} <br>
    
    购物车总金额: {{ compute() }} <br/>
    购物车总金额: {{carts[0].price*carts[0].number + carts[1].price*carts[1].number}} <br>
  </div>
</template>

<style scoped>

</style>
```

![1701361176900](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701361176900.png)

插值表达式的优点就是不依赖标签，缺点是麻烦

v-bind 渲染属性

## async和await的使用

```html
<script>

/*
    async 用于标识函数的
        1. async标识函数后,async函数的返回值会变成一个promise对象
        2. 如果函数内部返回的数据是一个非promise对象,async函数的结果会返回一个成功状态 promise对象
        3. 如果函数内部返回的是一个promise对象,则async函数返回的状态与结果由该对象决定
        4. 如果函数内部抛出的是一个异常,则async函数返回的是一个失败的promise对象

    */
async function fun1(){
  //return 10
  //throw new Error("something wrong")
  let promise = Promise.reject("heihei")
  return promise
}

let promise =fun1()

promise.then(
    function(value){
      console.log("success:"+value)
    }
).catch(
    function(value){
      console.log("fail:"+value)
    }
)
</script>

<template>



</template>

<style scoped>

</style>

```

# Axios是封装了原生Ajax的方法，使用起来更方便

请求要素

1. 请求的url
2. 请求的方式
3. 请求的参数 keyvalue json ... ...

# element-plus的main.js

```javascript
import { createApp } from 'vue'
//导入element-plus相关内容
import ElementPlus from 'element-plus'
import 'element-plus/dist/index.css'

import App from './App.vue'

const app = createApp(App)

app.use(ElementPlus)
app.mount('#app')
```



# 微头条项目



![1701534920222](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701534920222.png)

这里的密码是使用md5进行加密（粗糙使用）

![1701535158270](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701535158270.png)

type对应新闻类型（新闻ID），publisher对应用户id，page_view用于统计浏览量

## 准备包结构

![1701536935141](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701536935141.png)

- controller 控制层代码,主要由Servlet组成
- service     服务层代码,主要用于处理业务逻辑
- dao          数据访问层,主要用户定义对于各个表格的CURD的方法
- pojo         实体类层,主要用于存放和数据库对应的实体类以及一些VO对象
- util           工具类包,主要用存放一些工具类
- common  公共包,主要用户存放一些其他公共代码
- filters       过滤器包,专门用于存放一些过滤器
- test          测试代码包,专门用于定义一些测试的功能代码,上线前应该删掉,后期用maven可以自动处理掉

## jdbc.properties

![1701538294983](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701538294983.png)

initialSize  初始容量

maxActive 最大容量

maxWait    最大等待时间



![1701540958512](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701540958512.png)

//BaseDao基础类，封装了公告的查询方法和公告的增删改方法



VO里的类是 值取类 当实体类中的参数与前端要求的请求没有对应时，可以根据前端的请求来创建vo值取类



```
//baseQuery查询返回的是一个List集合
//baseQueryObject查询返回的是一个单个的值
```



一定注意前端要求的请求格式，确定是否要补充map来达成请求格式



## 为什么使用token而不是cookie和session：

session的大量使用会对服务器内存造成大量压力，可以使用IO流对session进行钝化和活化，但是IO流会大大增加session的处理时间

token产生于服务器，是一大串可以包含用户信息（id、name ...）的密文

客户端有一种存储技术，localStorage（关闭浏览器也会存在）,可以存储token，并将token以请求头的形式发送给服务器。（判断用户有没有登陆，可以根据localStorage中有无token来进行判断）

（客户端是没有解析token密文的能力）

**这样做的好处：**

1.后端不用产生大量的session对象，前端也不需要再存储相关的cookie。

2.可以根据token口令及时验证用户的登录时长（token的时长可以自己设置，如在一定时间内免登录）。

不好的地方：

**对编程人员的要求较高**

[token登录验证机制与session登录验证机制的优缺点_token和session的优缺点-CSDN博客](https://blog.csdn.net/weixin_42237752/article/details/88655511#:~:text=Token%E5%8F%AF%E4%BB%A5%E5%9C%A8%E4%BB%BB%E4%BD%95%E5%9C%B0%E6%96%B9%E7%94%9F%E6%88%90%EF%BC%8C%E5%8F%AA%E8%A6%81%E5%9C%A8%E4%BD%A0%E7%9A%84API%E8%A2%AB%E8%B0%83%E7%94%A8%E7%9A%84%E6%97%B6%E5%80%99%EF%BC%8C%E4%BD%A0%E5%8F%AF%E4%BB%A5%E8%BF%9B%E8%A1%8CToken%E7%94%9F%E6%88%90%E8%B0%83%E7%94%A8%E5%8D%B3%E5%8F%AF.%20%E9%80%82%E7%94%A8%E6%8E%A5%E5%8F%A3%E8%B7%A8%E5%B9%B3%E5%8F%B0%3A%20%E5%BD%93%E4%BD%A0%E7%9A%84%E5%AE%A2%E6%88%B7%E7%AB%AF%E6%98%AF%E4%B8%80%E4%B8%AA%E5%8E%9F%E7%94%9F%E5%B9%B3%E5%8F%B0%EF%BC%88iOS%2C%20Android%EF%BC%8CWindows%208%E7%AD%89%EF%BC%89%E6%97%B6%EF%BC%8CCookie%E6%98%AF%E4%B8%8D%E8%A2%AB%E6%94%AF%E6%8C%81%E7%9A%84%EF%BC%88%E4%BD%A0%E9%9C%80%E8%A6%81%E9%80%9A%E8%BF%87Cookie%E5%AE%B9%E5%99%A8%E8%BF%9B%E8%A1%8C%E5%A4%84%E7%90%86%EF%BC%89%EF%BC%8C%E8%BF%99%E6%97%B6%E9%87%87%E7%94%A8Token%E8%AE%A4%E8%AF%81%E6%9C%BA%E5%88%B6%E5%B0%B1%E4%BC%9A%E7%AE%80%E5%8D%95%E5%BE%97%E5%A4%9A%E3%80%82%20CSRF%3A%E5%9B%A0%E4%B8%BA%E4%B8%8D%E5%86%8D%E4%BE%9D%E8%B5%96%E4%BA%8ECookie%EF%BC%8C%E6%89%80%E4%BB%A5%E4%BD%A0%E5%B0%B1%E4%B8%8D%E9%9C%80%E8%A6%81%E8%80%83%E8%99%91%E5%AF%B9CSRF%EF%BC%88%E8%B7%A8%E7%AB%99%E8%AF%B7%E6%B1%82%E4%BC%AA%E9%80%A0%EF%BC%89%E7%9A%84%E9%98%B2%E8%8C%83%E3%80%82,%E6%80%A7%E8%83%BD%3A%20%E4%B8%80%E6%AC%A1%E7%BD%91%E7%BB%9C%E5%BE%80%E8%BF%94%E6%97%B6%E9%97%B4%EF%BC%88%E9%80%9A%E8%BF%87%E6%95%B0%E6%8D%AE%E5%BA%93%E6%9F%A5%E8%AF%A2session%E4%BF%A1%E6%81%AF%EF%BC%89%E6%80%BB%E6%AF%94%E5%81%9A%E4%B8%80%E6%AC%A1HMACSHA256%E8%AE%A1%E7%AE%97%20%E7%9A%84Token%E9%AA%8C%E8%AF%81%E5%92%8C%E8%A7%A3%E6%9E%90%E8%A6%81%E8%B4%B9%E6%97%B6%E5%BE%97%E5%A4%9A.%20%E4%B8%8D%E9%9C%80%E8%A6%81%E4%B8%BA%E7%99%BB%E5%BD%95%E9%A1%B5%E9%9D%A2%E5%81%9A%E7%89%B9%E6%AE%8A%E5%A4%84%E7%90%86%3A%20%E5%A6%82%E6%9E%9C%E4%BD%A0%E4%BD%BF%E7%94%A8Protractor%20%E5%81%9A%E5%8A%9F%E8%83%BD%E6%B5%8B%E8%AF%95%E7%9A%84%E6%97%B6%E5%80%99%EF%BC%8C%E4%B8%8D%E5%86%8D%E9%9C%80%E8%A6%81%E4%B8%BA%E7%99%BB%E5%BD%95%E9%A1%B5%E9%9D%A2%E5%81%9A%E7%89%B9%E6%AE%8A%E5%A4%84%E7%90%86.)

## 登陆业务的两个请求流程

![1701686047234](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701686047234.png)

![1701686082675](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701686082675.png)

两个业务接口

























































# **错误解决**

## 但凡遇到接口，就要写文档注释

### **Warning: No artifacts configured**

**![1700929708598](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1700929708598.png)**

form表单里的请求不往请求体里放

get请求有请求体

post请求放在uri	P80



## **一定要写文档注释！方法，接口及其形参入参方式都要写！**

sql查询列名与方法的属性名不一致，可通过起别名的方式来解决（鱼白的sql语句有讲）

## IDEA进行单元测试的时候无法在控制台输入问题解决办法？

[IDEA进行单元测试的时候无法在控制台输入问题解决办法？_51CTO博客_idea单元测试不了](https://blog.51cto.com/YangPC/6272850)

## JavaScript let和const的区别

[JavaScript let 和 const | 菜鸟教程 (runoob.com)](https://www.runoob.com/js/js-let-const.html#:~:text=ES2015%20%28ES6%29%20%E6%96%B0%E5%A2%9E%E5%8A%A0%E4%BA%86%E4%B8%A4%E4%B8%AA%E9%87%8D%E8%A6%81%E7%9A%84%20JavaScript%20%E5%85%B3%E9%94%AE%E5%AD%97%3A%20let%20%E5%92%8C%20const,%E5%9C%A8%20ES6%20%E4%B9%8B%E5%89%8D%EF%BC%8CJavaScript%20%E5%8F%AA%E6%9C%89%E4%B8%A4%E7%A7%8D%E4%BD%9C%E7%94%A8%E5%9F%9F%EF%BC%9A%20%E5%85%A8%E5%B1%80%E5%8F%98%E9%87%8F%20%E4%B8%8E%20%E5%87%BD%E6%95%B0%E5%86%85%E7%9A%84%E5%B1%80%E9%83%A8%E5%8F%98%E9%87%8F%20%E3%80%82)

## 类选择器中不能加注释

## out路径要设置好，不然JDK运行会出现问题

## Cannot resolve symbol

![1701592230570](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701592230570.png)



## was expecting comma to separate Object entries

 at [Source: (String)"{    "username":"zhangsan"    "userPwd":"123456"}"; line: 1, column: 32]

请求方式中的键值对一定要用,（逗号隔开）

{
    "username":"zhangsan",
    "userPwd":"123456"
}





























# **未解决的问题：**

第二遍

```java
protected void checkUserName(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取账号
        String username = req.getParameter("username");

        //根据用户名查询用户信息   找到505  找不到200
        NewsUser newsUser = newsUserService.findByUserName(username);
        Result result = Result.ok(null);
        if (null != newsUser){
            result = Result.build(null,ResultCodeEnum.USERNAME_USED);
        }

        WebUtil.writeJson(resp,result);
    }
```

第一遍

```java
protected void checkUsername(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        //获取账号
        String username = req.getParameter("username");

        //根据用户名查询用户信息  找到了 返回505  找不到200
        NewsUser newsUser = newsUserService.findByUserName(username);
        Result result = Result.ok(null);    //先存储200业务码
        if (null != newsUser) {     //如果用户名被占用
            result = Result.build(null,ResultCodeEnum.USERNAME_USED);
        }

        WebUtil.writeJson(resp,result);
    }

```

```java
protected void checkUserName(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        String username = req.getParameter("username");
        NewsUser newsUser = newsUserService.findByUserName(username);
        Result result=null;
        if (null == newsUser){
            result=Result.ok(null);
        }else{
            result=Result.build(null,ResultCodeEnum.USERNAME_USED);
        }
        WebUtil.writeJson(resp,result);
    }
```

tomcat service报错

![1701607085133](C:\Users\xiaoyubing\AppData\Roaming\Typora\typora-user-images\1701607085133.png)

（第一遍不可运行，其余正常）(清理cookie，重新加载项目，重启idea，手动导包，更改方法权限修饰符)

[方法未找到异常java.lang.NoSuchMethodException的解决办法-CSDN博客](https://blog.csdn.net/Bee_AI/article/details/85648078)

**原因暂未了解**

