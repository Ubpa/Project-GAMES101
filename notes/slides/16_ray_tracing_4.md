# 16. 光线追踪（蒙特卡洛积分与路径追踪）

> 课件：[GAMES101_Lecture_16.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_16.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 16 Ray Tracing 4](https://www.bilibili.com/video/BV1X7411F744?p=16)

## 蒙特卡洛积分

![image-20210611215453079](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611215453079.jpg)

## 路径追踪

### 计算方法

![image-20210611223825188](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611223825188.jpg)

### 俄罗斯轮盘赌

![image-20210611223910633](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611223910633.jpg)

### 采样光源

![image-20210611223953149](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611223953149.jpg)

![image-20210611224010243](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611224010243.jpg)

![image-20210611224042267](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611224042267.jpg)

![image-20210611224111914](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611224111914.jpg)

### 伪代码

![image-20210611224143301](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611224143301.jpg)

### 其他

- 路径追踪 100% 正确

  ![image-20210611224416222](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611224416222.jpg)

  康奈尔盒子：http://www.graphics.cornell.edu/online/box/compare.html

- 如何均匀采样？如何根据一个 pdf 采样？

- 重要性采样

- 随机数质量（低差异序列）

- 多重重要性采样

- radiance 和 color 的差异（gamma 校正，颜色空间，色调映射等）



