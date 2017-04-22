---
layout:     post
title:      "number string object数据类型"
subtitle:   " \"高程3之js基本概念\""
date:       2017-04-22 11:00:00
author:     "wwwboat"
header-img: ""
catalog: true
tags:
    - 高程
---

# number类型
## NaN
NaN用于表示一个本来要返回数值的操作数未返回数值的情况（这样就不会抛出错误了）<br/>
NaN有两个非同寻常的特点：1.任何涉及NaN的操作（例如NaN／10）都会返回NaN；2.NaN与任何值都不相等，包括NaN本身。<br/>

#### isNaN()函数
接收的参数可以为任何值，传入布尔值时，值会隐式转换为数值。

#### 数值转换
有3个函数可以把非数值转换为数值：
- Number（）
- parseInt（）
- parseFloat（）

##### Number（）
对于空字符串，会被转换为0；对于非数值，会被转换为NaN。

##### parseInt（）
由于Number（）函数在转换字符串时比较复杂且不够合理，因此在处理整数的时候更常用的是parseInt。<br/>
parseInt()无法识别小数，所有的数字都会被转换为整数（去尾）。<br/>
parseInt（）能够识别出各种整数格式（十进制、八进制、十六进制数），所以为了避免错误的解析，最好在什么情况下都明确指定基数：
```
var num1=parseInt("10",2);  //2(按照二进制解析）
var num2=parseInt("10",8);  //8(按照八进制解析）
var num3=parseInt("10",10);  //10(按照十进制解析）
var num4=parseInt("10",16);  //16(按照十六进制解析）
```

##### parseFloat()
与parseInt（）的区别：1.第一个小数点有效；2.始终会忽略数字前面的0.<br/>
如果字符串是一个能被解析为整数的数，那它就会被解析为整数。


# string类型
### length属性
如果字符串中包含双字节字符，那么length属性可能不会精确地返回字符串中的字符数目。<br/>
### string特点
字符串一旦创建，值就无法改变。要改变某个变量保存的字符串，首先要销毁原来的字符串，然后再用另一个包含新值的字符串填充该变量(后台发生），例如：
```
var lang = "java";
lang = lang + "Script";
```
### toString（）方法
数值、布尔值、对象和字符串都有这个方法。null和undefined没有。

###string（）方法
可以将任何类型的值转换为字符串。

# object类型
对象，其实就是一组数据和功能的集合。<br/>
在ECMAScript中，Object类型所具有的任何属性和方法都同样存在于更具体的对象中。<br/>
Object的每个实例都具有下列的属性和方法：
- constructor ：构造函数，也就是Object（）。保存着用于创建当前对象的函数。
- hasOwnProperty（propertyName）： 用于检查propertyName在当前对象实例中是否存在，参数必须以字符串的形式传入。
- isPrototypeOf（object）：用于检查传入的对象是否是当前对象的原型。
- propertyIsEnumerable（propertyName）：检查给定的属性是否能用for-in语句来枚举。参数必须以字符串的形式传入。
- toLoaclString（）：返回对象的字符串表示，该字符串与执行环境的地区对应。
- toSring（）：返回对象的字符串表示。
- valueOf（）：返回对象的字符串、数值、布尔值。通常与toString（）返回的内容相同。<br/>
由于Object是所有对象的基础，因此所有对象都具有这些基本的属性和方法。


