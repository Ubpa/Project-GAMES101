# 作业 3：管线和着色

插值需要使用透视校正插值（[参考](https://www.cnblogs.com/wickedpriest/p/5509007.html)）

其余内容比较简单

有个小坑点是需要在投影矩阵里把 z 反过来，具体地，最左边乘上如下矩阵

```c++
 1  0  0  0
 0  1  0  0
 0  0 -1  0
 0  0  0  1
```

也可以将 $M_{\text{ortho_scale}}$ 中的 z 缩放部分加 `-` 号

