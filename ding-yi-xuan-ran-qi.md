\#\#\#\#\#\#渲染器将和Canvas元素进行绑定，如果之前在HTML中手动定义了id为mainCanvas的Canvas元素，那么Renderer可以这样写：

```javascript
var renderer = new THREE.WebGLRenderer({
    canvas: document.getElementById('mainCanvas')
});
```

\#\#\#\#\#\#而如果想要Three.js生成Canvas元素，在HTML中就不需要定义Canvas元素，在JavaScript代码中可以这样写：

```jvascript
var renderer = new THREE.WebGLRenderer();
renderer.setSize(400, 300);
document.getElementsByTagName('body')[0].appendChild(renderer.domElement); 
```



