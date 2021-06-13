# 13. 光线追踪（基本原理）

> 课件：[GAMES101_Lecture_13.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_13.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 13 Ray Tracing 1](https://www.bilibili.com/video/BV1X7411F744?p=13)

## 基础光追算法

![image-20210610211736323](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610211736323.jpg)

## 光线曲面相交

### 光线方程

![image-20210610212040273](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610212040273.jpg)

### 光-圆相交

![image-20210610212104542](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610212104542.jpg)

![image-20210610212123523](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610212123523.jpg)

### 光-面相交

![image-20210611114025529](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210611114025529.jpg)

### 光-网格相交

转换成光-三角形相交，最快的方法是 Moller Trumbore 算法（详细[推导](https://blog.csdn.net/zhanxi1992/article/details/109903792)）

![image-20210610212257717](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610212257717.jpg)

### 光-盒相交

![image-20210610212542729](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610212542729.jpg)

![image-20210610212615651](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610212615651.jpg)