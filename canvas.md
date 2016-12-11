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
<canvas width="600" height="400"></canvas>

```