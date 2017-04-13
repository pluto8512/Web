```javascript
function getTrophyList() {
        $.ajax({
            url: '/mobile/participation/init',
            type: "GET",
            dataType: "json",
            data: {
                "aid":params.aid,
                "activityid":params.activityid,
                "keyversion":window.game.config.keyversion,
                "isFromApiFilter":1
            },
            success: function(data){
                // 通用逻辑
                if(data.retCode == 0){
                    var data = data.model,
                    trophyList = data.trophyList || [],
                    prizeImgs = [],
                    trophyListHTML = "";
                    // 轮播样式处理
                    builBannCss(trophyList.length+2);
                    // 奖品图片处理
                    buildPrizeImgs(prizeImgs,trophyList);
                    if (trophyList.length > 0) {
                        trophyListHTML += '<li><a href="javascript:void();">';
                        trophyListHTML += '<img src="'+prizeImgs[trophyList.length-1]+'" alt=""></a></li>';
                        for (var i=0; i<trophyList.length; i++) {
                            var awardItem = trophyList[i];

                            trophyListHTML += '<li><a href="javascript:void();">';
                            trophyListHTML += '<img src="'+prizeImgs[i]+'" alt=""></a></li>';
                        }
                        trophyListHTML += '<li><a href="javascript:void();">';
                        trophyListHTML += '<img src="'+prizeImgs[0]+'" alt=""></a></li>';
                        $("#awards").append(trophyListHTML);    
                    }else {
                        alert("暂时没有商品！");
                    }
                    countAwards = trophyList.length+2;  
                }else{
                    alert(data.message || "服务器繁忙，请稍后重试！")
                };
            }
        });
    }
```



