###DOM原生的操作方法
1. `document.querySelectorAll('div');`:返回的是nodelist对象
2. 将nodelist对象转换成Array[]对象： `myList = Array.prototype.slice.call(a);`
3. 尾部追加dom元素： `appendChild` (没有兼容问题) 
4. 头部追加dom元素： `parentDiv.insertBefore([插入的元素a], [参考的元素b]);`在子元素b前插入子元素a (没有兼容问题)
5. 删除dom元素： child.parentNode.removeChild(child) （没有兼容问题）
6. 添加事件监听： `addEventListener("click",function(){})`