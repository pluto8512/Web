### 绘制文字

* textAlign

  * `CanvasRenderingContext2D.textAlign`是Canvas中绘制文本时文本的对齐方式的属性。其对齐是基于`fillText()`或`strokeText()`方法的`x`值。`textAlign`属性有点类似于CSS中的`text-align`，用来设置文本水平对齐方式,其主要包括：left,right,center,start,end

+ 保存图形状态

[save\(\)](http://www.w3school.com.cn/jsref/met_canvasrenderingcontext2d_save.asp)和[restore\(\)](http://www.w3school.com.cn/jsref/met_canvasrenderingcontext2d_restore.asp)方法允许你保存和恢复一个 CanvasRenderingContext2D 对象的状态。save\(\) 把当前状态推入到栈中，而 restore\(\) 从栈的顶端弹出最近保存的状态，并且根据这些存储的值来设置当前绘图状态。



