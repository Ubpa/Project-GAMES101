# 06. 光栅化（深度测试与抗锯齿）

> 课件：[GAMES101_Lecture_06.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_06.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 06 Rasterization 2 (Antialiasing and Z-buffering)](https://www.bilibili.com/video/BV1X7411F744?p=6)

## 采样

artifacts 看起来很奇怪的现象

- 锯齿
- 摩尔纹
- 车轮效应
- ...

本质：信号变化太快但采样太慢

反走样解决办法：滤波->采样（采样再滤波，错！）

## 频域

将函数表示成关于 sine 和 cosine 的加权和

![image-20210609231654666](assets/image-20210609231654666.png)

傅里叶变换

![image-20210609231816572](assets/image-20210609231816572.png)

越高频的信号需要更快的采样，下采样会造成频率 aliases

## 滤波

### 去除特定频率的内容

![image-20210609232523584](assets/image-20210609232523584.png)

频谱图像的理解

- 中间是低频部分，比较亮说明图像信息主要是低频的
- 有个十字架，因为在图像的两侧边缘处被视为连接的，这里会有特别高频的变化

高频边界，低频模糊

![image-20210609233558395](assets/image-20210609233558395.png)

![image-20210609233605234](assets/image-20210609233605234.png)

### 卷积 / 平均

卷积定理：时域卷积 = 频域乘积

> 时域乘积 = 频域卷积

![image-20210609233955921](assets/image-20210609233955921.png)

## 采样 = 重复频率内容

![image-20210609234242644](assets/image-20210609234242644.png)

## 反走样

![image-20210609234626359](assets/image-20210609234626359.png)

先模糊（低通滤波）再采样

![image-20210609234638485](assets/image-20210609234638485.png)

渲染的图形信号为 $f(x,y)$（连续的），先用 1x1 的盒子滤波（注意是滤波，而不是采样，相当于求 $f(x,y)$ 在 1x1 的像素的平均值），再进行采样

常见技术

- MSAA
- FXAA
- TAA
- DLSS

