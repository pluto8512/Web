###ng 面向对象的使用方式
````javascript
<body ng-app="myApp">

<h1>学习ng的第三个小demo!</h1>
<div class="ddemo01"  ng-controller="ngdom as obj">
    <i></i> demo01
    {{obj.name}}dream as {{obj.dream}}
</div>

<!--js B!-->
<script src="./lib/node_modules/angular/angular.js"></script>
<script>
    var myApp = angular.module("myApp",[]);

    myApp.controller("ngdom",function ($scope) {
        this.name = "晓东";
        this.dream = "web";
    });
</script>
<!--js E!-->

</body>
````