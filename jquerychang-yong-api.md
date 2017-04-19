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
// 自定义属性
$("#helpOtherLayer #helpBargainIt img").attr("jump", true);
var needToJump = !!$("#helpBargainIt img").attr("jump");
if(needToJump){
    $(".join_play_link").trigger("touchend");
}else{            
    HelpBargainIt();
}
// 给动态元素绑定事件
$(document).on('touchend','#bargainIt',function(){//TODO});
```



