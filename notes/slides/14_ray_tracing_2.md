# 14. 光线追踪（加速结构）

> 课件：[GAMES101_Lecture_14.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_14.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 14 Ray Tracing 2](https://www.bilibili.com/video/BV1X7411F744?p=14)

## 加速结构

### 均匀空间划分

![image-20210611135643094](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611135643094.jpg)

### 空间划分

![image-20210611135705126](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611135705126.jpg)

Oct-Tree 依赖于维度（3 维有 8 个结点）

KD-Tree 不依赖于维度，但问题有：

- 难求一个区域内有哪些几何体
- 一个几何体可能出现在多个区域内

BSP-Tree 依赖于维度

### 物体划分：BVH

![image-20210611135951768](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611135951768.jpg)

关键在于划分，思路有

- 选取最长的轴划分
- 中间划分

终止标准：当结点内只有少数几个元素时，暂停划分

## 辐射度量学

度量系统，包括：radiant flux，intensity，irradiance，radiance，...

### Radiant Energy 和 Flux（Power）

radiant energy 是电磁辐射的能量，单位焦耳 $J$，符号为
$$
Q[J=\text{Joule}]
$$
radiant flux（power）是单位时间的辐射能量
$$
\Phi=\frac{\mathbb{d}Q}{\mathbb{d}t}[W=\text{Watt}][lm=\text{lumen}]
$$

## Radiant Intensity

radiant（luminous）intensity 是由点光源发出的单位立体角的功率

![image-20210611142428003](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611142428003.jpg)
$$
I(\omega) = \frac{\mathrm{d}\Phi}{\mathrm{d}\omega}\left[\frac{W}{sr}=cd=\text{candela}\right]
$$

## Solid Angle

![image-20210611142946793](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611142946793.jpg)

**立体角微元**

![image-20210611143111138](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611143111138.jpg)

各向同性点光源的 radiant intensity 与 radiant flux 的关系

![image-20210611143544085](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611143544085.jpg)

