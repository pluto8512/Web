apply/call回调数组方法

```javascript
<body>
    <div class="box">
        <ul>
        <li id="test">1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
        </ul>
    </div>
<script>
  var lis = document.getElementsByTagName("li");

  function o(arr){
      var res = [1,2];
      [].push.apply(res,arr);
      return res;
  }
  console.log(o(lis));//成功返回
</script>
</body>
////////////////////////////success
```
```javascript
<body>
    <div class="box">
        <ul>
        <li id="test">1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
        </ul>
    </div>
<script>
  var lis = document.getElementsByTagName("li");

  function o(arr){
      var res = [1,2];
      res.push.apply(res,arr);
      return res;
  }
  console.log(o(lis));//成功返回
</script>
</body>
////////////////////////////success
```
```javascript
<body>
    <div class="box">
        <ul>
        <li id="test">1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
        </ul>
    </div>
<script>
  var lis = document.getElementsByTagName("li");

  function o(arr){
      var res = [1,2];
      push.apply(res,arr);
      return res;
  }
  console.log(o(lis));//成功返回
</script>
</body>
////////////////////////////报错:push is not defined
```