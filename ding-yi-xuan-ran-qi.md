\#\#\#\#\#\#渲染器将和Canvas元素进行绑定，如果之前在HTML中手动定义了id为mainCanvas的Canvas元素，那么Renderer可以这样写：

```javascript
var renderer = new THREE.WebGLRenderer({
    canvas: document.getElementById('mainCanvas')
}); 
```



