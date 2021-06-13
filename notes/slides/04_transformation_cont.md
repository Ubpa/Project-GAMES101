# 04. 变换（模型、视图、投影）

> 课件：[GAMES101_Lecture_04.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_04.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 04 Transformation Cont.](https://www.bilibili.com/video/BV1X7411F744?p=4)

## 3D 变换

点 $(x,y,z,1)^\top$

向量 $(x,y,z,0)^\top$

一般地 $(x,y,z,w)$（其中 $w\neq 0$）是 3D 点 $(x/w,y/w,z/w)$

旋转变化

![image-20210609142536954](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609142536954.jpg)

欧拉角

![image-20210609142549195](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609142549195.jpg)

![image-20210609142558598](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609142558598.jpg)

轴角

![image-20210609142621449](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609142621449.jpg)

> 详细内容可查阅[补充材料](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_04_supp.pdf)。

## 视图变换

将世界空间坐标转换到相机空间坐标

![image-20210609142958178](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609142958178.jpg)

![image-20210609143036193](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609143036193.jpg)

![image-20210609143044264](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609143044264.jpg)

![image-20210609143101248](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609143101248.jpg)

## 投影变换

![image-20210609143156678](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609143156678.jpg)

### 正交投影

![image-20210609143333186](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609143333186.jpg)

首先将中心平移到原点，然后将各边长缩放成 2

![image-20210609143352275](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609143352275.jpg)

### 透视投影

找一个变换 $M_{\text{perp}\to\text{ortho}}$ 将截头锥体变为长方体

![image-20210609144322132](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609144322132.jpg)

首先根据相似性

![image-20210609144602681](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609144602681.jpg)

可推得

![image-20210609144551170](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609144551170.jpg)

这说明

![image-20210609144719352](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609144719352.jpg)

又因为

![image-20210609144626737](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609144626737.jpg)

![image-20210609144637277](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210609144637277.jpg)

所以第三行可设为 $(0,0,A,B)$，代入可得
$$
\begin{aligned}
An+B&=n^2\\
Af+B&=f^2
\end{aligned}
\to
\begin{aligned}
A&=n+f\\
B&=-nf
\end{aligned}
$$
