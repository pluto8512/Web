### 编码模式

1 缓存：将ajax里面请求来的数据放到全局变量里面做缓存，便于重用

2

```js
window.overVar = {};

;(function() {
    var cacheVar = true;
    overVar .myInitGame = function() {
        var localVar = true;
    };
})();
```

```js
overVar .myInitGame();
```



