#jQuery源码解析
###必备的基础知识
####异常
代码在执行的过程中出现的错误  

异常出现以后,其后的代码不在执行

凡是错误就会出现Uncaught关键字

syntaxerror:语法错误

解决办法:调试异常,异常捕获

1. try-catch
2. try-catch-finallly

如果我们做了异常的捕获的处理,会继续执行后面其他的代码

####原型

```javascript
function Person (name) 
{
    this.name = name;
    this.sayHello = function(){
        console.log("你是,我是"+this.name);
    }
}

var p1 = new Person("李磊");
var p2 = new Person("李梅");

p1.sayHello();
p2.sayHello();
```
> 存在的问题

```javascript
console.log(p1.sayHello == p2.sayHello);//返回false
```

>说明每个对象都有一个独立的sayHello的方法,而sayHell这个方法是完全相同的,所以造成了内存的浪费

```javascript
var sayHello = function()
{
    console.log("你是,我是"+this.name);
};
function Person (name)
{
     this.name = name;
     this.sayHello = sayHello;
}
var p1 = new Person("李磊");
var p2 = new Person("李梅");

p1.sayHello();
p2.sayHello();

console.log(p1.sayHello == p2.sayHello);//返回true

```

>一个对象可能有N多方法,所有的方法都暴露在全局作用域下,与外部库冲突的几率就会变大,所以不宜采取该方法

>解决办法:将所有的方法放到一个对象中

```javascript
var Tool (name) = {
    this.name = name;
    this.sayHello = function(name){
         console.log("你是,我是"+this.name);
    }
}

function Person (name)
{
 this.name = name;
 var tool = new Tool(name);
 this.sayHello = tool.sayHello;
}

var p1 = new Person("李磊");
var p2 = new Person("李梅");

p1.sayHello();
p2.sayHello();

console.log(p1.sayHello == p2.sayHello);//返回true
```
>最好的解决方法

```javascript
function Foo() 
{
    
}
Foo.prototype.sayHello = function()
{
    console.log("js高级");
};
var foo = new Foo();
foo.sayHello();
```

>自带的原型对象,每个函数都有指向原型对象的属性,然后
对象会沿原型链来找属性和方法.每一个由构造函数创建的对象都会指向该构造函数的原型对象

>什么东西应该加在原型上面

>公用的,共享的方法放到原型中

>独有的数据和独有的行为应该放在对象中

####利用对象修改原型对象属性

1. 修改原型对象里面的属性值会怎么样?

```javascript 
function Person() {
}
Person.prototypy.name = "xiaodong";
var p = new Person();
console.log(p.name); //xioaodong 
p.name = "xiaofang ";
console.log(p); //xiaofang,对比可以看出p.name不会更改原型中的属性

var p1 = new Person();
console.log(p1.name); //xiaodong

var p2 = new Person();
p2 ._proto_.name = "xiaolan";
console.log(p2 .name); //xiaolan 
```
####混入(实现继承常用的方法之一)

```javascript
//混入(mix)
var o1 = {name:"xiaofang" };
var o2 = {};
o2.name = o1.name;//最简单的混入,也是一种继承的方式

//封装
function _mix_(obj,obj1) {
 for(var k in obj1) {
  abj[k] = obj1[k];
 }
}

var o1 = {"name":"xiaoming"};
var o2 = {"name":"xiaofang","age":12};
_mix_(o1,o2);

console.log(o1); //name: xioafang ; age: 12;

//对混入进行升级
//可以带多个参数,将所有对象的成员都加到this当前对象上
var o = {
 extend: function (obj) {
  for ( var k in obj) {
   this[k] = obj[k];
  }
 }
};

//在函数中有一个默认的对象存在即argument
//混入的扩展
var o = function (obj) {
 for (var i=0;i<arguments.length,i++){
  for (var k in arguments[i]) {
    this[k] = arguments[i][k];
  }
 }
}

```

####继承
1. 针对构造函数而言,原型就是够着函数的prototype属性,通常将其称为原型属性,原型就是 实例对象的 原型对象

![](/assets/2016-11-30_151945.png)

2.
```javascript
function Person (name , age, gender) 
{
    this.name = name;
    this.age = age;
    this.geder = gender;
}
//Person.prototype是一个对象,可以点新建方法
Person.prototype.sayHello = function() 
{
     console.log("你好,我是"+ this.name);
}
Person.prototype.run= function()
{
     console.log("你好,我是"+ this.age);
}
var p1 = new Person("李磊",19."男");
p1.sayHello();
p1.run();
```

```javascript
//让Person.protorype 指向另一个对象(替换了原型对象)
Person.prototype = {
    Person.prototype.sayHello = function() 
    {
        console.log("你好,我是"+ this.name);
    }
};
```

3. 这两种做法之间有什么区别?

系统提供的prototype对象拥有一个construct属性,这个属性指向构造函数

使用替换原型对象的时候要手动添加construct属性

construct:Person,

4. _proto_

和prototype是否存在关系

早期浏览器是不支持_proto_,火狐率先使用该属性,但是是非标准,基本的浏览器都支持,ie8是不支持的.

原型属性:对于构造函数来说,原型是原型属性,构造函数可以使用prototype属性访问原型

原型对象:对于实例来说,原型是原型对象,实例可以使用_proto_访问原型


