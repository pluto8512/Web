#Object.prototype成员

```javascript 
//////////////hasOwnPrototype//////////
function Person () {
   this.name = "jim";
}
Person.prototype.age = 19;
var p = new Person();
// p是否含有name属性
console.log(p.hasOwnPrototype("name"));
// p是否含有age属性
console.log(p.hasOwnPrototype("age"));
//////////////////END//////////////////

//////////////isPrototypeOf////////////
//isPrototypeOf方法用于测试一个对象是否存在于另一个对象的原型链上。
function Person () {
   this.name = "jim";
}
Person.prototype.age = 19;
var p = new Person();

//p是不是 
console.log( Person.prototype.isPrototypeOf( p ) );
//////////////////END//////////////////
```