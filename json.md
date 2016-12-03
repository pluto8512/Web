#AJAX请求
使用ajax获得json格式的字符串之后,转换成对象

```javascript
//转换json格式的字符串为对象
var data = "[{"name": "张三","age": 19,"gander": "男"},{"name": "张四","age": 18,"gander": "女"}]";
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
// JSON.parse();
var o3 = JSON.parse(data);// 要求字符串必须是严格的json格式
```

```javascript
// eval 函数
var s = "{}";
var o = eval(s); //没有任何结果

var s2 = "{name: "张三"}";
var o2 = eval(s2); //没有得到对象,得到张三

var s3 = "{name: "张三", age: 19}";
var o3 = eval(s3); //报错:逗号出现语法错误

//换成标准的json格式
var s2 = "{"name": "张三"}";
var o2 = eval(s2); //报错

//解决方法
//两端加圆括号就可以了
//{}被eval解释成代码块的含义
//标记语言,标记后面加冒号,就证明加了标记
label123:
while (true) {
   console.log("第一层循环开始");
   while (true) {
      console.log("第二层循环开始");
      break label123;
   }
}
console.log("over");
```
