```js
// 输入框联动
    $("#listen_ipt").on("input", function(){
        var $txt = $(".listen_txt");
        if (!$(this).val()) {
            $txt.text("xxx");
        } else {
            $txt.text($(this).val());
        }
    });
```



