# 18. 高级光线传播与复杂外观建模

> 课件：[GAMES101_Lecture_18.pdf](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_18.pdf)
>
> 视频：[GAMES101-现代计算机图形学入门-闫令琪 | Lecture 18 Advanced Topics in Rendering](https://www.bilibili.com/video/BV1X7411F744?p=18)

## 高级光线传播

- 无偏光线传播方法
  - Bidirectional path tracing，BDPT
  - Metropolis light transport，MLT
- 有偏光线传播方法
  - Photon mapping
  - Vertex connection and merging
- instant radiosity（VPL / many light methods)

## 高级外观建模

- 非表面模型
  - 参与介质
  - 头发 hair / 毛发 fur/ 纤维 fiber (BCSDF)
  - 颗粒材质 granular material
- 表面模型
  - 透光材质 BSSRDF
  - 衣服
  - 细节材质 detailed material（non-statistical BRDF）
- 程序化外观

