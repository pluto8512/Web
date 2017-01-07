###DOM原生的操作方法
1. `document.querySelectorAll('div');`:返回的是nodelist对象
2. 将nodelist对象转换成Array[]对象： `myList = Array.prototype.slice.call(a);`