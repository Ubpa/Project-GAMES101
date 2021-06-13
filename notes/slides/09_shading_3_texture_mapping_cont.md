# 09. 着色（插值、高级纹理映射）

> 课件：[GAMES101_Lecture_09.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_09.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 9 Shading 3 (Texture Mapping Cont.)](https://www.bilibili.com/video/BV1X7411F744?p=9)

## 重心坐标

![image-20210610154923792](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610154923792.jpg)

## 纹理

用重心坐标插值出逐像素纹理坐标

**双线性插值**

![image-20210610155110256](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610155110256.jpg)

**三线性插值**

先生成 mipmap，然后计算 level

![image-20210610155316680](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610155316680.jpg)

接着使用三线性插值

![image-20210610155340032](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610155340032.jpg)

但对于倾斜的情况还是有问题，可以采用 ripmap

