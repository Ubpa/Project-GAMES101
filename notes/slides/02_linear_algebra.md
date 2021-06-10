# 02. 向量与线性代数

> 课件：[GAMES101_Lecture_02.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_02.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 02 Review of Linear_Algebra](https://www.bilibili.com/video/BV1X7411F744?p=2)

向量、矩阵

## 叉乘的应用

判断一个向量在另一个向量的左侧还是右侧（逆时针还是顺时针），只需看两向量的叉乘结果的 z 的正负，z 正则左侧（逆时针），z 负则右侧（顺时针）。

![image-20210610115028538](assets/image-20210610115028538.png)

判断一个点是否在三角形内部

![image-20210610115327975](assets/image-20210610115327975.png)

$\vec{AB}\times\vec{AP}$、$\vec{BC}\times \vec{BP}$、$\vec{CA}\times\vec{CP}$ 三者同向则说明 $P$ 在 $\triangle ABC$ 内

另外，还可以判断一个多边形是否为凸的，凸多边形要求临边绕向相同。