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