1. 初始化Box2d

```js
LGlobal.box2d = new LBox2d();
```

> 刚体：它上面任何两点之间的距离都是完全不变的



2. 矩形刚体

```js
 addBodyPolygon(width,height,type,density,friction,restitution);
```

> type\(静态或动态\) density\(密度\)friction\(摩擦\)restitution\(弹力\)



