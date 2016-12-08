#Object.prototype成员

```javascript 
///////////////hasOwnPrototype////////////////
function Person () {
   this.name = "jim";
}
Person.prototype.age = 19;
var p = new Person();
// p是否含有name属性
console.log(p.hasOwnPrototype("name"));
// p是否含有age属性
console.log(p.hasOwnPrototype("age"));
```