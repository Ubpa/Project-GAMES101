# 19. 相机与透镜

> 课件：[GAMES101_Lecture_19.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_19.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 19 Cameras, Lens and Light Fields](https://www.bilibili.com/video/BV1X7411F744?p=19)

## 相机结构

相机：透镜组 lens +传感器 sensor

传感器记录的是 irradiance，如果没有透镜，会很糊

![image-20210613134758219](assets/image-20210613134758219.png)



## 视域 FOV

![image-20210613134843861](assets/image-20210613134843861.png)
$$
\text{FOV} = 2\arctan \left(\frac{h}{2f}\right)
$$
由于历史原因，一般以 35mm 格式胶片下的焦距（focal length）来确定 FOV

![image-20210613135034069](assets/image-20210613135034069.png)

## 曝光 exposure

曝光是时间乘 irradiance，即 $H = T \times E$，其中曝光时间 $T$ 由快门（shutter）控制，irradiance 由透镜光圈（lens aperture）和焦距（focal length）控制。

![image-20210613135543052](assets/image-20210613135543052.png)

## 薄透镜近似

### 高斯薄透镜公式

![image-20210613135716395](assets/image-20210613135716395.png)
$$
\frac{1}{f}=\frac{1}{z_i}+\frac{1}{z_o}
$$

### 散焦模糊

![image-20210613135836925](assets/image-20210613135836925.png)

可用光追实现

![image-20210613140033422](assets/image-20210613140033422.png)

- 对于传感器上的像素 $x^\prime$
- 在透镜上随机采样 $x^{\prime\prime}$
- 过 $x^\prime$ 和透镜中心作一条直线与 subject plane 交于 $x^{\prime\prime\prime}$
- 则 $x^\prime x^{\prime\prime}$ 光线经过折射会朝向 $x^{\prime\prime\prime}$

### 景深

![image-20210613140341381](assets/image-20210613140341381.png)

