# 摆线

标签（空格分隔）： 未分类

---

[TOC]



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

参数方程的命令
Curve[2 (t - sin(t)), 2 (1 - cos(t)), t, 0, 6.28319]

圆在直线上滚动的轨迹

![](http://hbimg.huabanimg.com/e384d31cb04cb7885714c0360aa025daf4b12ab248f50-AwwydY_fw658)

### 求摆线的轨迹方程



#### 圆在直线上滚动的摆线

求这个轨迹的方程

假设点 $C(x,y)$ 

弧ＢＣ＝线段ＯＢ

![](http://hbimg.huabanimg.com/ddbd4f1edd231269efdc5a475fe6e28d8701797a8c8c-7lWVlr_fw658)


$x =R\phi - R\sin\phi = R(\phi-\sin\phi) $

$y = R - R\cos\phi= R(1-\cos\phi)$

#### 外摆线轨迹方程

----

![](https://raw.githubusercontent.com/Listenpeng/GeoGebra/master/line/image/%E5%9C%86%E7%9A%84%E5%A4%96%E6%91%86%E7%BA%BF%E8%BD%A8%E8%BF%B9%E6%B1%82%E8%A7%A3.png)
A'(x,y)

$y = (R+r)\cos\alpha - r\cos(\alpha+\beta) \\ =(R+r)\cos\alpha -r\cos{\dfrac{R+r}{r}\alpha} $

$x = (R+r)\sin \alpha - r\sin(\alpha + \beta) \\ =(R+r)\sin\alpha -r\sin{\dfrac{R+r}{r}\alpha }$

$\beta = \dfrac{R}{r}\alpha$



#### 内摆线轨迹方程

![](https://raw.githubusercontent.com/Listenpeng/GeoGebra/master/line/image/%E5%9C%86%E7%9A%84%E5%86%85%E6%91%86%E7%BA%BF%E8%BD%A8%E8%BF%B9%E6%B1%82%E8%A7%A3.png)
圆在圆的内摆线

$A'(x,y)$　$\beta = \dfrac{R}{r} \alpha$

$x = (R-r)\cos \alpha  + r\cos(\beta - \alpha) \\ = (R-r)\cos \alpha  + r\cos(\dfrac{R-r}{r} \alpha)$

$y = (R-r)\sin\alpha - r \sin(\beta - \alpha) \\= (R-r)\sin\alpha - r\sin \dfrac{R-r}{r} \alpha$

#### 摆线示例

$R$为固定圆的半径，$r$为动圆的半径

圆的外摆线当$\dfrac{R}{r} = 1$时，是心形线

![](https://raw.githubusercontent.com/Listenpeng/GeoGebra/master/line/image/%E5%9C%86%E7%9A%84%E5%A4%96%E6%91%86%E7%BA%BF1%3A1%20%E5%BF%83%E8%84%8F%E7%BA%BF.gif)

圆的内摆线当$\dfrac{R}{r}=2$时，轨迹为一条直径

![](https://raw.githubusercontent.com/Listenpeng/GeoGebra/master/line/image/%E5%86%85%E6%91%86%E7%BA%BF%EF%BC%92%3A1.gif)

圆的内摆线当$\dfrac{R}{r}=３$时，轨迹为有３个尖

![](https://raw.githubusercontent.com/Listenpeng/GeoGebra/master/line/image/%E5%86%85%E6%91%86%E7%BA%BF3%3A1.gif)

```
程序遇到问题打不开了
listen@listen-Inspiron-3670:~/下载$ geogebra
18:31:14.036 INFO: geogebra.i.a.a[-1]: GeoGebra 4.2.60.0 04 October 2013 Java 11.0.4-64bit
18:31:14.036 DEBUG: geogebra.i.a.<init>[-1]: isApplet=false runningFromJar=true appletImpl=null
18:31:14.036 DEBUG: geogebra.i.a.ao[-1]: Setting up logging
18:31:14.042 DEBUG: geogebra.i.a.ao[-1]: Logging is redirected to /tmp/GeoGebraLog_kcsnreyfgv.txt
放弃吧，习惯geogebra classic模式才是正道
```

### 圆的直线摆线性质

旋轮线

#### 弧长

弧长公式

$$s = \int \sqrt{\dfrac{dx}{dt}+\dfrac{dy}{dt}}dt$$

$x =R\phi - R\sin\phi = R(\phi-\sin\phi)$

$ \dfrac{dx}{dt} = R - R\cos\phi   $  $\dfrac{dx}{dt}^2=R^2 - 2R^2\cos\phi +\cos^2\phi$

$y =  R(1-\cos\phi) $

$ \dfrac{dy}{dt} =\sin\phi$  $\dfrac{dy}{dt} ^2= \sin^2\phi $

$s = \int _{0}^{2\pi}\sqrt{2R^2 -2R^2\cos\phi} \ d\phi=\sqrt2 R\int_{0}^{2\pi}\sqrt{1-\cos\phi} \ d\phi  \\=\sqrt2 R\int_{0}^{2\pi}\sqrt{2\sin^2\dfrac{\phi}{2}} \ d\phi = 2R\int_{0}^{2\pi}\sin\dfrac{\phi}{2} d\phi=8\pi  R$

此处$s=8\pi R$



#### 包围的面积

面积公式$S = \int y dt = $

此处$S = 3\pi R^2$

如何画$\dfrac{R}{r} = 2.1 $的摆线




