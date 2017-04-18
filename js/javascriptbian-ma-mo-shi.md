### 编码处理模式

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

3 动态请求图片

```js
// 当image对象的src被赋值的时候，就开始请求图片
function main() {
    var prizeImgs = ['http://www.xxx.xx.png','http://www.xxx.yy.png']
    for(var i=0;i<prizeImgs.length; i++) {
        var img = new Image();
        (function(i , img ){
            img.onload = function(){
                biultImgO(i,img);
            };
        })(i , img);
        img.src = prizeImgs[i];
    }
}
// 拿到请求到的图片后对图片进行处理
function biultImgO(i,img) {
    // 获取图片的宽高
    imgOW = img.width;
    imgOH = img.height;
    $(slecEle).attr("src" , img.src) ;
    //TODO ...
}
main();
```



