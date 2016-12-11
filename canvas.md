#canvas
- 游戏
- 可视化数据 重点
- banner广告
- 多媒体
- 未来
  - 模拟仿真 threejs.org 将3d引擎引入
  - 远程协作
  - 图形编辑

###入门
```javascript
//默认宽高 300*150 300*150个像素点
//不要用css来设置,如果使用css来设置画布的大小,不会增加像素点,只会将像素扩大
//canvas只能展示画图的内容,不能绘图,每一个canvas都有一套工具,利用工具可以在cancas上进行绘图
//canvas.getContext('2d') 就返回一个在当前页面上绘图的工具集
//这个工具集专门绘制平面图形,里面有很多方法
//<canvas width="600" height="400"></canvas>
//从页面获取canvas的DOM元素
//开始绘图
var ctx = cas.getContext('2d');

ctx.moveTo(100, 100);//描点
ctx.lineTo(200, 200);//描点

ctx.stroke();//描边绘图
```

###canvas的直角坐标系
![](/assets/1.bmp)

###canvas绘制虚线
```javascript
<body>
<canvas id="canvas"></canvas>
<script>
		var cas = document.getElementById("canvas");
		var ctx = cas.getContext('2d');

ctx.moveTo(100, 100);//描绘图的起始点
ctx.lineTo(200, 200);//描点直线的终点

ctx.stroke();//连点描边
</script>
</body>
```
###非零环绕原则

- 如果需要判断某区域是否要填充颜色,我们需要
非零环绕原则来判断,在这块区域选点,随便向任意
方向拉出去一条线L,如果画的图的线条穿过L线
是顺时钟方向的记1,反之记-1

###闭合路径

- closePath(): 将绘图的起点和终点连接起来
- closePath与lineto直接闭合的区别:closePath是完美闭合

###线宽的问题
lineWidth()

canvas在进行绘制线条的时候,如果线宽只要是奇数值都会去做取消锯齿的操作

###路径
- 状态: 在需要改变颜色绘制方法,改变颜色,绘制方法,改变一些属性...就需要改变绘图状态.使用beginPath()方法.开启一个新的路径.不会影响其他的路径
