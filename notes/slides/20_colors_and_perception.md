# 20. 光场、颜色与感知

> 课件：[GAMES101_Lecture_20.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_20.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 20 Colors and Perception](https://www.bilibili.com/video/BV1X7411F744?p=20)

## 全光函数 The Plenoptic Function

$$
P(\theta,\phi,\lambda,t,V_x,V_y,V_z)
$$

其中

- $\theta$ 和 $\phi$ 决定视线方向
- $\lambda$ 是波长
- $t$ 是时间
- $V_x$、$V_y$ 和 $V_z$ 是位置

## 光场

![image-20210613141809448](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613141809448.jpg)

![image-20210613141840677](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613141840677.jpg)

## 颜色的物理基础

### 可见光谱

![image-20210613141935029](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613141935029.jpg)

### 谱功率密度 Spectral Power Distribution（SPD）

![image-20210613142032530](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613142032530.jpg)

SPD 具有线性性质

![image-20210613142214132](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613142214132.jpg)

## 颜色

颜色是人类的感知

### 人类视锥细胞的谱响应

人眼感光细胞分

- 杆细胞 rods：感知灰度
- 锥细胞 cones：有 3 种锥细胞，每种对光谱的感知不同；提供了颜色的感觉。

![image-20210613142354032](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613142354032.jpg)

人眼不能直接感知光谱，而是感知了 $(S,M,L)$ 这三个数

![image-20210613142407263](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613142407263.jpg)

### 颜色生成

给定三个基光谱
$$
s_R(\lambda),s_G(\lambda),s_B(\lambda)
$$
可以进行线性组合
$$
s(\lambda)=Rs_R(\lambda)+Gs_G(\lambda)+Bs_B(\lambda)
$$

### CIE RGB

三个基光谱

![image-20210613142803122](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613142803122.jpg)

对于任意波长的光线，根据**人的感知**匹配，可以得到一个组合系数，称为 CIE RGB 颜色匹配函数 $\bar{r}(\lambda),\bar{g}(\lambda),\bar{b}(\lambda)$，绘制如下图

![image-20210613143155886](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613143155886.jpg)

因此，根据光谱的线性性，任意一个光谱 $s$，都可以计算 CIE RGB 基元，如下

![image-20210613143607979](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613143607979.jpg)

> 用这三个数去控制三个基光源，混出来的颜色与 $s$ 相同

## 颜色空间

### 标准颜色空间

sRGB

### 通用颜色空间 CIE XYZ

![image-20210613144020017](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613144020017.jpg)

这是人造的颜色响应函数，与之对应的基础颜色是不存在的

$Y$ 是亮度

### 分离亮度与色品 chromaticity

相对的 XYZ 就是色品

![image-20210613151317064](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613151317064.jpg)

固定 $Y$，并且将 $x,y$ 作为坐标可以得到色域图

![image-20210613151403456](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210613151403456.jpg)

> 一个光谱，有一个感知的颜色，将光谱与匹配函数进行积分，得到 XYZ，然后算出 xyz，并根据 xy 找到位置，把颜色填上去
>
> 最外围是单波长对应的颜色，根据光谱的线性性，其他光谱都可以由单波长混合出来，因此其他颜色都可以混合出来
>
> 那单波长对应的颜色是不是就是所有颜色？并不是，比如白色，它就是一个混合色，可以说，整个色域上不同的点的颜色都是不同的。

