# 05. 光栅化（三角形的离散化）

> 课件：[GAMES101_Lecture_05.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_05.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 05 Rasterization 1 (Triangle)](https://www.bilibili.com/video/BV1X7411F744?p=5)

## 标准立方体到屏幕

![image-20210609154121382](assets/image-20210609154121382.png)

像素索引为 $(x,y)$，其中 $x$ 和 $y$ 是整数，范围是 $(0,0)$ 到 $(\text{width}-1,\text{height}-1)$，中心坐标为 $(x+0.5,y+0.5)$。

屏幕覆盖范围是 $(0,0)$ 到 $(\text{width},\text{height})$。

视口变换

![image-20210609154335929](assets/image-20210609154335929.png)

![image-20210609154350820](assets/image-20210609154350820.png)

## 光栅化

![image-20210609190128101](assets/image-20210609190128101.png)