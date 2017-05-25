### threejs的坐标体系

```javascript
// 平面不旋转的效果
plane.rotation.x = 0;
plane.position.x = 0;
plane.position.y = 0;
plane.position.z = 0;
```

![](/assets/three123.png)

```javascript
// 逆时针旋转90°
plane.rotation.x = -0.5*Math.PI;
plane.position.x = 0;
plane.position.y = 0;
plane.position.z = 0;
```

![](/assets/three就是24.png)

```javascript
plane.rotation.x = -Math.PI/4;
plane.position.x = 0;
plane.position.y = 0;
plane.position.z = 0;
```

![](/assets/threejs141.png)

* y轴和z轴的位置要互换（上图）

![](/assets/three就是2312.png)

* 上图中红绿蓝所在的方向是坐标轴的正方向



