# 04. 变换（继续）

> 课件：[GAMES101_Lecture_04.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_04.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 04 Transformation Cont.](https://www.bilibili.com/video/BV1X7411F744?p=4)

## 3D 变换

点 $(x,y,z,1)^\top$

向量 $(x,y,z,0)^\top$

一般地 $(x,y,z,w)$（其中 $w\neq 0$）是 3D 点 $(x/w,y/w,z/w)$

旋转变化

![image-20210609142536954](assets/image-20210609142536954.png)

欧拉角

![image-20210609142549195](assets/image-20210609142549195.png)

![image-20210609142558598](assets/image-20210609142558598.png)

轴角

![image-20210609142621449](assets/image-20210609142621449.png)

> 详细内容可查阅[补充材料](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_04_supp.pdf)。

## 相机变换

将世界空间坐标转换到相机空间坐标

![image-20210609142958178](assets/image-20210609142958178.png)

![image-20210609143036193](assets/image-20210609143036193.png)

![image-20210609143044264](assets/image-20210609143044264.png)

![image-20210609143101248](assets/image-20210609143101248.png)

## 投影变换

![image-20210609143156678](assets/image-20210609143156678.png)

### 正交投影

![image-20210609143333186](assets/image-20210609143333186.png)

首先将中心平移到原点，然后将各边长缩放成 2

![image-20210609143352275](assets/image-20210609143352275.png)

### 透视投影

找一个变换 $M_{\text{perp}\to\text{ortho}}$ 将截头锥体变为长方体

![image-20210609144322132](assets/image-20210609144322132.png)

首先根据相似性

![image-20210609144602681](assets/image-20210609144602681.png)

可推得

![image-20210609144551170](assets/image-20210609144551170.png)

这说明

![image-20210609144719352](assets/image-20210609144719352.png)

又因为

![image-20210609144626737](assets/image-20210609144626737.png)

![image-20210609144637277](assets/image-20210609144637277.png)

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
