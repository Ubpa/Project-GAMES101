# 08. 着色（着色频率、图像管线、纹理映射）

> 课件：[GAMES101_Lecture_08.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_08.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 08 Shading 2 (Shading, Pipeline and Texture Mapping)](https://www.bilibili.com/video/BV1X7411F744?p=8)

## Blinn-Phong 反射模型

### specular 项

视线方向靠近镜面反射方向时明亮

![image-20210610144048146](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144048146.jpg)

通过 half vector 靠近 normal 来判断

![image-20210610144115602](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144115602.jpg)

![image-20210610144145781](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144145781.jpg)

### ambient 项

![image-20210610144215467](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144215467.jpg)

### 完整

![image-20210610144235239](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144235239.jpg)

## 着色频率

### flat shading

![image-20210610144348393](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144348393.jpg)

### gouraud shading

![image-20210610144406482](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144406482.jpg)

### phong shading

![image-20210610144420048](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610144420048.jpg)

注意 phong shading 不同于 Blinn-Phong 反射模型。

### 逐顶点法线

**从底层模型获取**

![image-20210610145641273](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610145641273.jpg)

**邻接三角形法线的平均**

![image-20210610145802862](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610145802862.jpg)

![image-20210610145834379](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610145834379.jpg)

### 逐像素法线

重心插值

![image-20210610145927286](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610145927286.jpg)

## 图形管线

![image-20210610150519377](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610150519377.jpg)

## 纹理映射

![image-20210610150549537](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610150549537.jpg)

