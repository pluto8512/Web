```javascript
<html>
    <head></head>
    <body>
        <div id="hello">hello world</div>
        <script>
        //w3c中使用addEventListener()函数监听事件，IE中使用attachEvent()函数监听事件
        //w3c中使用 removeEventListener ()函数移除事件监听，IE中使用detachEvent()函数来移除事件监听



        var doc = window.document,
        w3c = !!doc.addEventListener,//判断浏览器是否为w3c
        //编写兼容w3c和ie的事件监听函数
        addListener = w3c ?
            function(el, type, fn) { el.addEventListener(type, fn, false); } :
            function(el, type, fn) { el.attachEvent('on' + type, fn); },
        removeListener = w3c ?
            function(el, type, fn) { el.removeEventListener(type, fn, false); } :
            function(el, type, fn) { el.detachEvent('on' + type, fn); };


        //监听事件
        addListener(document.getElementById("hello"),"click",handler);
        //移除监听
        removeListener(document.getElementById("hello"),"click",handler);

        function handler(){
            this.innerHTML="nihao";
            console.log(this);
        }

        //注：移除监听事件的处理函数必须和监听时间的处理函数相同时才可以成功移除监听
        </script>
    </body>
</html>
```



