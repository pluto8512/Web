### jQuery常用API

```js
$("img").attr("src" , img.src);
$('.moreBtn').off('touchend').on('touchend',function(){
    getHelpList();
});
$(".moreBtn").text("暂无更多助力").off('touchend');
$(".arrow_left").hide();
$(".arrow_left").show();
$('.helpList_posi').append(helpListHTML);
$(".getprize_count_text").html('<span class="num">'+result+'</span>'+'个小伙伴已领到');
$('.arrow_left').css('display','none');
$(".lightR li:nth-child(2n-1)").css("visibility","hidden");
$('#mark span:last-child').outerWidth();
var customObj = $.parseJSON(awardList[index-1].custom);
// 自定义属性
$("#helpOtherLayer #helpBargainIt img").attr("jump", true);
var needToJump = !!$("#helpBargainIt img").attr("jump");
if(needToJump){
    $(".join_play_link").trigger("touchend");//触发$(".join_play_link")的'touchend事件'
}else{            
    HelpBargainIt();
}
// 给动态元素绑定事件
$(document).on('touchend','#bargainIt',function(){//TODO});
// ajax
$.ajax({
    url: '/mobile/participation/classics_bargain/bargain',
    type: "GET",
    dataType: "json",
    data: {
        "aid":params.aid,
        "activityid":params.activityid,
        "wuid":window.game.config.wuid,
        "keyversion":window.game.config.keyversion,
        "isFromApiFilter":1,
        "awardId":currAwardId
    },success: function(data){
       // TODO
    }
});
//输入框清空获取焦点
$("input[name='test']").val("").focus();
$(".price_bar .bar").width( $("#mark").width() );
$('#backfill_panel').css("background-image","url("+gameCustomImg['background']+")");	
```



