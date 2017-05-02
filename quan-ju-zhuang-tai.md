```js
// 全局状态
	window.myApp = {
			// 回填面板
			"backfill_panel": $("#backfill_panel"),
			// 是否是助力人进入页面
			"isHelp": (window.game.config.fromOpenid && window.game.config.fromOpenid != window.game.config.openid)? true: false,
			// 是否是按排名
			"isRank": (activityJson.awardSendType === 1)? true: false,
			// 一等奖名称
			"firstTrophyName": JSON.parse(activityJson.awardTips)[0].trophyName || "",
			// 抽奖门槛
			"passCondition": window.game.sendRuleMap.passCondition,
			// 获取基本信息（当新闻没有被助力人操作时为null）
			"moreInfo": JSON.parse(window.game.userPlayinfo.moreInfo) || {},
			// 发布新闻时判断传入的json数据是否改变，不改变则不保存，直接弹出二维码
			"listenJSON": "",
			// 分享形式，0为二维码，1为分享图文
            "shareType": (activityJson.extraData & (Math.pow(2, 7)))==0? 0: 1,
            // 自定义新闻
            "newsList": JSON.parse(window.game.extendOperation.newsList),
            // 讯飞发音人列表
            "nameList":	[
                       	 {name: "aisxxin", txt: "蜡笔小新", imgPath: "/tts_xiaoxin.png"},
                       	 /*{name: "xiaowanzi", txt: "小丸子", imgPath: "/tts_xiaowanzi.png"},*/
                       	 {name: "aisxqian", txt: "东北娘们", imgPath: "/tts_xiaoqian.png"},
                       	 {name: "aisxrong", txt: "川妹子", imgPath: "/tts_aisxrong.png"},
                       	 {name: "aisxkun", txt: "河南老乡", imgPath: "/tts_xiaokun.png"},
                       	 {name: "aisxqiang", txt: "湖南小伙", imgPath: "/tts_aisxqiang.png"},
                       	 {name: "aisxying", txt: "陕西姑娘", imgPath: "/tts_aisxying.png"}
                       	],
            "img": {
            	"bg": gameCustomImg['bg'] || window.basepath + 'bg.jpg',
        		"contentBg": gameCustomImg['contentBg'] || window.basepath + 'content_bg.png',
        		"changeNews": gameCustomImg['changeNews'] || window.basepath + 'main_change.png',
        		"left": gameCustomImg['left'] || window.basepath + 'left.png',
        		"right": gameCustomImg['right'] || window.basepath + 'right.png',
        		"try": gameCustomImg['try'] || window.basepath + 'try.png',
        		"btnLottery": gameCustomImg['btnLottery'] || window.basepath + 'btn_lottery.png',
        		"btnRelease": gameCustomImg['btnRelease'] || window.basepath + 'btn_release.png',
        		"btnMeto" : gameCustomImg['btnMeto'] || window.basepath + 'btn_meto.png',
        		"dislike": gameCustomImg['dislike'] || window.basepath + 'dislike.png',
        		"like": gameCustomImg['like'] || window.basepath + 'like.png',
        		"cup": gameCustomImg['cup'] || window.basepath + 'cup.png'
            }            
	}
```



