\#\#\#pc端自定义游戏界面的模板

```javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>

<body>
    <!--最顶层的盒子的类名必须有game_page(否则没有背景图片的编辑按钮),
    gameBgBox(否则背景图片的编辑界面显示不完整)，
    gameBox(否则一部分编辑按钮会消失)-->
    <div class="game_page gameBox gameBgBox">
        <!--背景图片在目录结构image/mobile/newgame/xxx/game下的bg.jpg,这是写死的-->
        <div id="gameBgBox">
            <img id="gameBg" src="" style="width:100%;height:auto">
        </div>
        <!--放图片的盒子的id必须是gameLayerBox，否则不显示自定义的图片-->
        <!--要替换的图片前面添加editTarget前缀就可以-->
        <!--originDef里面的name属性必须和editTarget后面的名字一致-->
        <div id="gameLayerBox" style="z-index: 11;">
            <img class="editTarget-time">
            <div class="xxl-time">1000</div>
            <img class="editTarget-score">
            <div class="xxl-score">1000</div>
            <img class="editTarget-xiaochou">
            <img class="editTarget-mouth">
            <img class="editTarget-ban">
            <div id="canvas_wrap" class="canvas-wrap"></div>
        </div>
    </div>
    <script>
        // "name"必须和img里面的类名的后缀一致，否则会不显示
        // 由于数组里面已经有position和size信息，所以可以将样式里面的位置和大小信息去掉，不会影响布局
        // 因为被替换的元素被后台加上了绝对定位,所以样式里面的绝对定位也要去掉
        // 自定义替换的图片的地址是在image/mobile/newgame/xxx/game文件夹下的图片
        Edit.originDef = [{
            "name": "mario",
            "pos": {
                "left": "1rem",
                "top": "12.7rem",
                "disable": "disable"
            },
            "size": {
                "width": "1.93rem",
                "height": "2.45rem"
            },
            "path": [
                ["*_resRoot*/mario/game/jump.png", "马里奥跳", "100k"],
                ["*_resRoot*/mario/game/left.png", "马里奥左手右脚", "100k"],
                ["*_resRoot*/mario/game/middle.png", "马里奥站立", "100k"],
                ["*_resRoot*/mario/game/right.png", "马里奥右手左脚", "100k"]
            ],
            "edit": "all"
        }, {
            "name": "wugui",
            "pos": {
                "left": "8rem",
                "top": "6.8rem",
                "disable": "disable"
            },
            "size": {
                "width": "2rem",
                "height": "1.85rem"
            },
            "path": [
                ["*_resRoot*/mario/game/wugui.png", "乌龟1", "100k"],
                ["*_resRoot*/mario/game/wugui1.png", "乌龟2", "100k"]
            ],
            "edit": "all"
        }, {
            "name": "gold",
            "pos": {
                "left": "4rem",
                "top": "13.5rem",
                "disable": "disable"
            },
            "size": {
                "width": "1.5rem",
                "height": "1.63rem"
            },
            "path": [
                ["*_resRoot*/mario/game/gold30.png", "金币30分", "100k"],
                ["*_resRoot*/mario/game/gold50.png", "金币50分", "100k"],
                ["*_resRoot*/mario/game/gold100.png", "金币100分", "100k"],
                ["*_resRoot*/mario/game/qiang.png", "墙壁", "100k"]
            ],
            "edit": "all"
        }];
        // 这个配置是根据自己的实际情况确定的
        var pubResizeDef = { //图片恢复默认参数
            'titleImg': {
                width: '10.75rem',
                height: '8.95rem'
            },
            'startBtnImg': {
                width: '10rem',
                height: '3.58rem'
            }
        };
    </script>
</body>

</html>
```



