# GeoGebra
```
#绘制圆的摆线
# 绘制一个圆心在原点的圆
命令：R = Circle[ <Point>, <Radius Number> ]
输入:R=[ (0,0),1 ]
在圆上取一点A
过点A做圆R的切线
l = Tangent[ <Point>, <Conic> ]
l = Tangent[ A, R ]
生成切线的单位法向量u
u = UnitPerpendicularVector[ <Line> ]
u = UnitPerpendicularVector[ l ]
从图片中可以判断单位法向量的方向
```



在圆外生成半径为1的圆r且与圆R相切，圆心为P

P = A + u

r =  Circle[ P, 1 ]

定义旋转过的角度逆时针方向以x正半轴为起始

m = Angle[ <Point>, <Apex>, <Point> ]

m = Angle[ (1,0), (0,0), (A) ]

动圆与定圆的圆心角关系为n=m

以角度n绕P点旋转A点得到A'

Rotate[ <Object>, <Angle>, <Point> ]

Rotate[ A, n, P ]注意观察方向

显示A' 的轨迹，播放A点的动画



圆在直线上滚动的轨迹

![](https://hbimg.huabanimg.com/e384d31cb04cb7885714c0360aa025daf4b12ab248f50-AwwydY_fw658)

求这个轨迹的方程

假设点 $C(x,y)$ 

弧ＢＣ＝线段ＯＢ

![](https://hbimg.huabanimg.com/ddbd4f1edd231269efdc5a475fe6e28d8701797a8c8c-7lWVlr_fw658)



$$x =R\phi - R\sin\phi = R(\phi-\sin\phi) $$

![](http://y = R - R\cos\phi= R(1-\cos\phi)\)

$$y = R - R\cos\phi= R(1-\cos\phi)$$



参数方程的命令

Curve[2 (t - sin(t)), 2 (1 - cos(t)), t, 0, 6.28319]

----

![](https://hbimg.huabanimg.com/2e062a3482202d38e47546da5b013f0c5ad40ad41fd1f-88ODba_fw658)

A'(x,y)

$y = (R+r)\cos\alpha - r\cos(\alpha+\beta) \\ =(R+r)\cos\alpha -r\cos{\dfrac{R+r}{r}\alpha} $

$x = (R+r)\sin \alpha - r\sin(\alpha + \beta) \\ =(R+r)\sin\alpha -r\sin{\dfrac{R+r}{r}\alpha }$

$\beta = \dfrac{R}{r}\alpha$

----

![](https://hbimg.huabanimg.com/8ba703b0f63d69ba8a8a3cb19ad093fd876068ac9fec-8LGOm1_fw658)



圆在圆的内摆线

$A'(x,y)$　$\beta = \dfrac{R}{r} \alpha$

$x = (R-r)\cos \alpha  + r\cos(\beta - \alpha) \\ = (R-r)\cos \alpha  + r\cos(\dfrac{R-r}{r} \alpha)$

$y = (R-r)\sin\alpha - r \sin(\beta - \alpha) \\= (R-r)\sin\alpha - r\sin \dfrac{R-r}{r} \alpha$



