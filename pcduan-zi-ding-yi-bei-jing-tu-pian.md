1.common.jsp中有这句代码

```javascript
else if($('.gameBgBox').is(':visible')){
                    arg.from = "#gameBg";
                    arg.defSrc = '<%=gameImgPath %>/<%=gameTemplateName%>/game/bg.jpg';
```

所以在目录结构image/mobile/newgame/xxx/game下要添加bg.jpg

```html
src="http://127.0.0.1//image/mobile/newgame/mario/game/bg.jpg?v=3"
```





