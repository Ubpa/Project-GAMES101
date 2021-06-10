# 08. 着色（着色频率、图像管线、纹理映射）

> 课件：[GAMES101_Lecture_08.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_08.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 08 Shading 2 (Shading, Pipeline and Texture Mapping)](https://www.bilibili.com/video/BV1X7411F744?p=8)

## Blinn-Phong 反射模型

### specular 项

视线方向靠近镜面反射方向时明亮

![image-20210610144048146](assets/image-20210610144048146.png)

通过 half vector 靠近 normal 来判断

![image-20210610144115602](assets/image-20210610144115602.png)

![image-20210610144145781](assets/image-20210610144145781.png)

### ambient 项

![image-20210610144215467](assets/image-20210610144215467.png)

### 完整

![image-20210610144235239](assets/image-20210610144235239.png)

## 着色频率

### flat shading

![image-20210610144348393](assets/image-20210610144348393.png)

### gouraud shading

![image-20210610144406482](assets/image-20210610144406482.png)

### phong shading

![image-20210610144420048](assets/image-20210610144420048.png)

注意 phong shading 不同于 Blinn-Phong 反射模型。

### 逐顶点法线

**从底层模型获取**

![image-20210610145641273](assets/image-20210610145641273.png)

**邻接三角形法线的平均**

![image-20210610145802862](assets/image-20210610145802862.png)

![image-20210610145834379](assets/image-20210610145834379.png)

### 逐像素法线

重心插值

![image-20210610145927286](assets/image-20210610145927286.png)

## 图形管线

![image-20210610150519377](assets/image-20210610150519377.png)

## 纹理映射

![image-20210610150549537](assets/image-20210610150549537.png)

