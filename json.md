#AJAX请求
使用ajax获得json格式的字符串之后,转换成对象

```javascript
//转换json格式的字符串为对象
var data = "[{name: "张三",age: 19,gander: "男"}]";
// json 格式(严格,国际化了)
// json有两种结构
// 1: {}
// 2: []
// 注意: json格式中,键名也必须使用双引号括起来
// 在js中使用json对象,相对松散

// 将字符串变成对象,有三种做法
// 1. eval
var o1 = eval("("+data+")"); //注意一个习惯,两端加上圆括号,对结果没有什么影响
// 2. Function
var o2 = (new Function("return " + data))();
// 3. 使用es5中标准的处理json的语法
//JSON.parse();
```