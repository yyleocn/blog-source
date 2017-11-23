---
title: Javascript基础知识
categories:
  - program
  - front-end
abbrlink: 29076
date: 2017-11-21 00:00:00
tags:
---

Javascript基础知识

# 数据类型

>## Object 对象

### 概述
JavaScript 原生提供`Object`对象，所有其他对象都**继承自这个对象**。

> `Object`本身也是一个构造函数，可以直接通过它来生成新对象。
`var obj = new Object();`

`Object`作为构造函数使用时，可以接受一个参数。
> 如果该参数是一个对象，则**直接返回这个对象**；
如果是一个原始类型的值，则**返回该值对应的包装对象**。
```
var o1 = {a: 1};
var o2 = new Object(o1);
o1 === o2 // true

new Object(123) instanceof Number
// true
```
注意，通过`new Object()`的写法生成新对象，与字面量的写法`o = {}`是等价的。

**在Object实例对象上面增加一个方法或属性，有两种做法**
>* 直接在**对象本身**增加
比如，在Object对象上面定义一个`print`方法，显示其他对象的内容。
```
var o = new Object();
o.print = function(o){ console.log('Hello!') };
o.print();
```
>* 在**`prototype`（原型对象）**上增加
所有构造函数都有一个`prototype`属性，指向一个原型对象。
凡是定义在`prototype`对象上面的属性和方法，将被所有实例对象共享。
```
Object.prototype.print = function(){ console.log(this)};
var o = new Object();
o.print() // Object
```
>* 两种方法都能为`o`定义了一个`print`方法，然后生成一个`Object`的实例`o`。
`o`直接继承了`Object.prototype`的属性和方法，可以在自身调用它们，也就是说，`o`对象的`print`方法实质上是调用`Object.prototype.print`方法。

可以看到，尽管上面两种写法的`print`使用方法及效果相同，但是部署方法和原理是不一样的。
因此必须区分**构造函数的方法**和**实例对象的方法**。


### Object()

Object本身当作工具方法使用时，可以将任意值转为对象。**这个方法常用于保证某个值一定是对象。**
如果参数是原始类型的值，Object方法返回对应的包装对象的实例（参见《原始类型的包装对象》一节）。
```
Object() // 返回一个空对象
Object() instanceof Object // true

Object(undefined) // 返回一个空对象
Object(undefined) instanceof Object // true

Object(null) // 返回一个空对象
Object(null) instanceof Object // true

Object(1) // 等同于 new Number(1)
Object(1) instanceof Object // true
Object(1) instanceof Number // true

Object('foo') // 等同于 new String('foo')
Object('foo') instanceof Object // true
Object('foo') instanceof String // true

Object(true) // 等同于 new Boolean(true)
Object(true) instanceof Object // true
Object(true) instanceof Boolean // true
```

>## Number 数字
>


>* String
>* Boolean

># Symbol 符号
> 暂时用不上

># null 空对象
># undefined 空值
>* 变量没有值 -> `undefined`
>* 有一个对象，现在不想赋值 -> `null`
>* 有一个非对象，不想装值 -> `undefined`
