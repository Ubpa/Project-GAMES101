# 07. 着色（光照与基本着色模型）

> 课件：[GAMES101_Lecture_07.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_07.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 07 Shading 1 (Illumination, Shading and Graphics Pipeline)](https://www.bilibili.com/video/BV1X7411F744?p=7)

## 可见性 visibility

depth buffer 存储各像素最小的 z 值

假设 z 为正，近小远大

![image-20210610111809179](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610111809179.jpg)

z-buffer 算法

```c++
initialize depth buffer to \infty
during rasterization
  for(each triangle T)
    for(each sample (x,y,z) in T)
      if(z < zbuffer[x,y])      // closest samples so far
        framebuffer[x,y] = rgb; // update color
        zbuffer[x,y] = z;       // update depth
      else
        ; // do nothing, this sample is occluded
```

![image-20210610112115557](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610112115557.jpg)

## Blinn-Phong 反射模型

### diffuse 项

**输入**

- 视线方向 $v$
- 表面法线 $n$
- 光线方向 $l$
- 表面参数（颜色，光滑度 shininess，...）

![image-20210610112452677](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610112452677.jpg)

漫反射

![image-20210610112913479](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610112913479.jpg)

![image-20210610112943407](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610112943407.jpg)

![image-20210610112731147](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610112731147.jpg)

![image-20210610112807735](http://home.ustc.edu.cn/~ustczt/resources/Project-GAMES101/assets/image-20210610112807735.jpg)

