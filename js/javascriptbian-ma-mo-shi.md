### 编码处理模式

1 缓存：将ajax里面请求来的数据放到全局变量里面做缓存，便于重用

2 沙箱

```js
window.overVar = {};

;(function() {
    var cacheVar = true;
    overVar .myInitGame = function() {
        var localVar = cacheVar.xx;
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

4 html拼接

```js
var selectedHTML = 
	'<div class="status" id="getLayer"> \
	     <img id="exchangeBg" src="'+basepath+'/frame.png" alt="底层"> \
	     <div class="realFrame"> \
            <div class="text"> \
                <div class="desc"> \
                    <p>成功砍到<span id="price">￥'+formatMoneyToShowFixed2(minPrice)+'</span></p> \
                    <p>快速领取优惠劵</p> \
                </div> \
            </div> \
            <div class="act_btn" id="getIt"> \
                <img src="'+gameCustomImg['btn-5']+'" alt=""> \
            </div> \
        </div> \
	 </div>';
$('#base_layer').html(selectedHTML);
$('#selectedLayer').show();
```



