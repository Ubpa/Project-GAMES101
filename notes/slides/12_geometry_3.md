# 12. 几何（网格处理）

> 课件：[GAMES101_Lecture_12.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_12.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 12 Geometry 3](https://www.bilibili.com/video/BV1X7411F744?p=12)

## 网格操作

- 细分：增加三角形数量
- 简化：减少三角形数量，保持形状
- 正则化：修改分布，改善质量

## 细分

### Loop 细分

- 每个三角形一分为四

  ![image-20210610201726940](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610201726940.jpg)

- 对新的点，加权平均

  ![image-20210610201750648](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610201750648.jpg)

- 对旧的点，加权平均

  ![image-20210610201820607](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610201820607.jpg)

### Catmull-Clark 细分

细分步骤

- 每个面新增一个点
- 每条边新增一个点
- 连接新点
- 修改旧点位置

![image-20210610202315813](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610202315813.jpg)

## 网格简化

塌缩边

![image-20210610203413617](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610203413617.jpg)

选二次误差最小的

## 阴影贴图

![image-20210610204405793](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610204405793.jpg)
