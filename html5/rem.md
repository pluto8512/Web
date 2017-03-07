\#\#\#rem适配

```javascript
<script type="text/javascript" >
        var html = document.documentElement;
        var windowWidth = html.clientWidth;
        html.style.fontSize = windowWidth / 6.4+'px';
        console.log(windowWidth);
        console.log( html.style.fontSize);
        var urlPath = '<%=resourceDomain%>';
    </script>
    // rem适配,按100倍来计算
    // 设计稿是640
    // 然后设计稿里面的元素就按量的尺寸除以100+rem 
```



