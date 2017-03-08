\#\#\#检查参数的方法

```javascript
// 检查参数的方法
        timeout = timeout || 5000;
        imgList = isArray(imgList) && imgList || [];
        callback = typeof(callback) === 'function' && callback;
```



