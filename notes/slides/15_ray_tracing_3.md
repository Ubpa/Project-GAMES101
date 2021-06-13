# 15. 光线追踪（辐射度量学、渲染方程与全局光照）

> 课件：[GAMES101_Lecture_15.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_15.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 15 Ray Tracing 3](https://www.bilibili.com/video/BV1X7411F744?p=15)

## 复习概念

- radiant energy 电磁辐射能量 $Q[J=\text{Joule}]$
- radiant flux（power）单位时间能量 $Q=\frac{\mathbb{d}Q}{\mathbb{d}t}[W=\text{Watt}][\text{lm}=\text{lumen}]$
- radiant intensity 单位立体角能量 $I(\omega)=\frac{\mathbb{d}\Phi}{\mathbb{d}\omega}$
- solid angle 立体角 $\Omega=\frac{A}{r^2}$

## Irradiance

irradiance 是入射到曲面一点上单位投影面积的功率
$$
E(x)=\frac{\mathbb{d}\Phi(x)}{\mathbb{d}A}\left[\frac{W}{m^2}\right]\left[\frac{\text{lm}}{m^2}=\text{lux}\right]
$$

## radiance

radiance 是在单位投影面积单位立体角的功率

![image-20210611155645685](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611155645685.jpg)
$$
L(x,\omega)=\frac{\mathrm{d}^2\Phi(x,\omega)}{\mathrm{d}\omega\mathrm{d}A\cos\theta}
\left[\frac{W}{\text{sr}\ \text{m}^2}\right]
\left[\frac{\text{cd}}{\text{m}^2}=\frac{\text{lm}}{\text{sr}\ \text{m}^2}=\text{nit}\right]
$$
可以理解成

- 单位立体角的 irradiance => incident radiance
- 单位面积的 radiant intensity => exiting radiance

##  BRDF

![image-20210611162113341](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611162113341.jpg)

![image-20210611162145801](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611162145801.jpg)

## 反射方程

![image-20210611162154501](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611162154501.jpg)

## 渲染方程

![image-20210611162616612](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611162616612.jpg)

## 理解渲染方程

![image-20210611163651950](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611163651950.jpg)

![image-20210611163700903](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611163700903.jpg)

![image-20210611163711247](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611163711247.jpg)

![image-20210611163719832](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611163719832.jpg)

![image-20210611163736132](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611163736132.jpg)

