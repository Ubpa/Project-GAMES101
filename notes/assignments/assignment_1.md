# 作业 1：旋转与投影

> [作业1发布公告 – 计算机图形学与混合现实研讨会 (games-cn.org)](http://games-cn.org/forums/topic/graphics-intro-hw1/)

## 编程环境

框架使用了重度框架 opencv，本人替代地使用了轻量型的跨平台框架

- glfw
- glad
- opengl
- stb_image

## 作业

模型矩阵
$$
\left[
\begin{array}{c}
\cos\theta & -\sin\theta & 0 & 0\\
\sin\theta &  \cos\theta & 0 & 0\\
         0 &           0 & 1 & 0\\
         0 &           0 & 0 & 1\\
\end{array}
\right]
$$
透视矩阵

根据 fov（$\theta$），aspect ratio（ar），n 和 f 推出 t，b，l，r
$$
\begin{aligned}
t &= n \tan \frac{\theta}{2}\\
b &= -t\\
r &= t * ar\\
l &= -r 
\end{aligned}
$$
剩下的根据 ppt 推即可

注意，n 和 f 是负数。

框架要求 depth 是近小远大，我们这里近是 n 远是 f，由于 n 和 f 是负数，所以不做其他处理的话，近大远小（负更多）。因此需要在 ortho 的 scale 处将 z 反过来 $2/(f-n)$。