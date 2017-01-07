###DOM原生的操作方法
1. `document.querySelectorAll('div');`:返回的是nodelist对象 (IE6、IE7不兼容)
2. 将nodelist对象转换成Array[]对象： `myList = Array.prototype.slice.call(a);`
3. 尾部追加dom元素： `appendChild` (没有兼容问题) 
4. 头部追加dom元素： `parentDiv.insertBefore([插入的元素a], [参考的元素b]);`在子元素b前插入子元素a (没有兼容问题)
5. 删除dom元素： `child.parentNode.removeChild(child)` （没有兼容问题）
6. 添加事件监听： `addEventListener("click",function(){})` (兼容问题)
7. 目前的最佳实践，是将JavaScript脚本文件都放在页面底部加载。这样的话，其实document.ready方法（jQuery简写为$(function)）已经不必要了，因为等到运行的时候，DOM对象已经生成了。
8. 为dom元素添加一个class： `document.body.className = 'hasJS';` (没有兼容问题)
9. 设置样式： `element.style.color = "red";` (支持的样式有限制，可以查看：http://caniuse.com/#search=style)