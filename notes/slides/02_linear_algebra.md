# 02. 向量与线性代数

> 课件：[GAMES101_Lecture_02.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_02.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 02 Review of Linear_Algebra](https://www.bilibili.com/video/BV1X7411F744?p=2)

向量、矩阵

## 向量

定义：有**大小**和**方向**的量

坐标表示：$\pmb{a}=\left(\begin{array}{c}x\\ y\end{array}\right)$（注意准确时应该竖着写，也可以横着写：$\pmb{a}^\top=(x,y)$），大小（也叫模长）为 $\|\pmb{a}\|=\sqrt{x^2+y^2}$，方向 $\frac{\pmb{a}}{\|\pmb{a}\|}$ 

### 运算

- 加法：平行四边形法则、三角形法则，$(x_1,y_1)+(x_2,y_2)=(x_1+x_2,y_1+y_2)$ 

- 乘法
  - 数乘/除：$k(x,y)=(kx,ky)$，$k(x,y,z)=(kx,ky,kz)$
  - 内积/点乘：$(x_1,y_1) \cdot (x_2,y_2) = x_1x_2+y_1y_2$，$(x_1,y_1,z_1)\cdot(x_2,y_2,z_2)=x_1x_2 + y_1y_2+z_1z_2$
  - 外积/叉乘：$(x_1,y_1)\times(x_2,y_2)=x_1y_2-y_1x_2$，$(x_1,y_1,z_1)\times(x_2,y_2,z_2)=(y_1z_2-z_1y_2,z_1x_2-x_1z_2,x_1y_2-y_1x_2)$

### 内积 / 点乘

两向量内积的结果是一个值（并非向量）

![image-20210615215350506](assets/image-20210615215350506.png)

![image-20210615215340643](assets/image-20210615215340643.png)

> 求夹角
>
> 两向量 $(1,0)$，$(0,1)$，则
>
> $$
> \cos\theta=\frac{1*0 + 0*1}{1 * 1}=\frac{0}{1}=0
> $$
> 故 $\theta = 90^\circ$

一个向量 $\pmb{b}$ 可以拆成分别与另一向量 $\pmb{a}$ 平行与垂直的两向量

![image-20210615220509346](assets/image-20210615220509346.png)

### 外积 / 叉乘

向量 $\pmb{a}$ 和 $\pmb{b}$ 叉乘的结果 $\pmb{a}\times\pmb{b}$ 是一个向量

- 大小：$\|\pmb{a}\|\|\pmb{b}\|\cos\theta$
- 方向：由“右手定则”确定

![image-20210615221315295](assets/image-20210615221315295.png)



![image-20210615221735444](assets/image-20210615221735444.png)

### 叉乘的应用

判断一个向量在另一个向量的左侧还是右侧（逆时针还是顺时针），只需看两向量的叉乘结果的 z 的正负，z 正则左侧（逆时针），z 负则右侧（顺时针）。

![image-20210610115028538](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610115028538.jpg)

判断一个点是否在三角形内部

![image-20210610115327975](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610115327975.jpg)

$\vec{AB}\times\vec{AP}$、$\vec{BC}\times \vec{BP}$、$\vec{CA}\times\vec{CP}$ 三者同向则说明 $P$ 在 $\triangle ABC$ 内

另外，还可以判断一个多边形是否为凸的，凸多边形要求临边绕向相同。

## 矩阵

**定义**：矩阵就是一组数，行 x 列

> **示例**
>
> 一个 3 行 2 列的矩阵
> $$
> \left(
> \begin{array}{c}
> 1 & 3\\
> 5 & 2\\
> 0 & 4\\
> \end{array}
> \right)
> $$

**单位矩阵**：方阵（行数和列数相等），对角线（从左上到右下，而不是从右上到左下）上的元素为 1，其余元素为 0，记为 $I$

> **示例**
>
> 3x3 的单位矩阵
> $$
> \left(
> \begin{array}{c}
> 1 & 0 & 0\\
> 0 & 1 & 0\\
> 0 & 0 & 1
> \end{array}
> \right)
> $$

### 运算

- 加法
  
  - 相同维度，对应数相加
  
- 乘法
  - 数乘/除：$kA$，$A/3=\frac{1}{3}A$ 

  - 乘：要求左边的列数等于右边的行数

    > **计算公式** 
    > $$
    > \left(
    > \begin{array}{c}
    > a_x & a_x\\
    > b_x & b_y\\
    > c_x & c_z\\
    > \end{array}
    > \right)
    > \left(
    > \begin{array}{c}
    > d_x & e_x & f_x\\
    > d_y & e_y & f_y \\
    > \end{array}
    > \right)
    > =
    > \left(
    > \begin{array}{c}
    > \pmb{a}^\top \\
    > \pmb{b}^\top \\
    > \pmb{c}^\top \\
    > \end{array}
    > \right)
    > \left(
    > \begin{array}{c}
    > \pmb{d} & \pmb{e} & \pmb{f}
    > \end{array}
    > \right)
    > =
    > \left(
    > \begin{array}{c}
    > \pmb{a} \cdot \pmb{d}\\
    > \pmb{b} \cdot \pmb{e}\\
    > \pmb{c} \cdot \pmb{f}\\
    > \end{array}
    > \right)
    > $$

- 转置：横着放

- 逆：若$AB=I$，则称 $B$ 为 $A$ 的逆矩阵，记为 $A^{-1}$，即 $AA^{-1}=I$

