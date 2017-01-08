###Angular模拟jQuery的方法
```javascript
<body ng-app="myApp">

<h1>学习ng的第三个小demo!</h1>
<div class="ddemo01"  ng-controller="ngdom">
    <i></i> demo01

</div>
<div class="ddemo02">
</div>
<div class="ddemo03">
</div>
<div class="ddemo04">
</div>

<!--js B!-->
<script src="./lib/node_modules/angular/angular.js"></script>
<script>
    var myApp = angular.module("myApp",[]);

    myApp.controller("ngdom",function ($scope) {
        // element方法提供dom操作
        var $ = angular.element;
        $(document).ready(function () {
            $(document.getElementsByClassName("ddemo01")).css({ "color": "#ff0011", "background": "blue" });
        });
    });
</script>
<!--js E!-->
</body>
```