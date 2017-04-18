### 编码模式

1 缓存：将ajax里面请求来的数据放到全局变量里面做缓存，便于重用

2 沙箱

```js
window.overVar = {};

;(function() {
    var cacheVar = true;
    overVar .myInitGame = function() {
        var localVar = true;
    };
});
```

```js
overVar .myInitGame();
```

3 图片缓存

```js
var prizeImgs = ['http://www.xxx.xx.png','http://www.xxx.yy.png']
for(var i=0;i<prizeImgs.length; i++) {

    var img = new Image();
    (function(i , img ,countLi){
        img.onload = function(){
            biultImgO(i,img,countLi);
        };
    })(i , img ,countLi);
    img.src = prizeImgs[i];
}
```



