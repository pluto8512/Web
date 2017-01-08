#jQuery源码分析
```javascript
//匿名函数自执行,希望这些变成局部的
(function() {
 
})();
//如何提供对外的接口
(function() {
  var a = 10 ;
  
  function $() {
     alert(a);
  }
  //挂载在windows下面
  window.$ = $ ;  
})();
```
