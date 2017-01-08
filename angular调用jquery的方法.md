###Angular模拟jQuery的方法
```javascript
var myApp = angular.module("myApp",[]);

myApp.controller("ngdom",function ($scope) {
        // element方法提供dom操作
        var $ = angular.element;
        $(document).ready(function () {
            $(document.getElementsByClassName("ddemo01")).css({ "color": "#ff0011", "background": "blue" });
        });
});
```