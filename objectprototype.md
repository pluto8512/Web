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

#包装类型
Number Boolean String 

#getter/setter 
```javascript
var o = (function () {
		var num = 13;
		return {
				
			// get 名字 () { 逻辑体 }
			get num () {
				console.log( '执行 getter 读写器了' );
				return num;
			},

			// set 名字 ( v ) { 逻辑体 }
			set num ( v ) {
				console.log( '执行 setter 读写器了' );

				if ( v < 0 || v > 150 ) {
					console.log( '赋值超出范围, 不成功 ' );
					return;
				}	
				num = v;
			}
		};
	})();

	//var obj = { num: 123 };  // 要限制其赋值的范围
	// obj.age   要求 age 的范围是 0 到 150

	console.log( o.num );
	o.num = 33;
	console.log( o.num );
```
