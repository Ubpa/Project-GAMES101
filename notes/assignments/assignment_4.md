# 作业 4：Bezier 曲线

框架自带了 `naive_bezier  `，它根据解析式计算位置。

作业要求实现的是根据 de Casteljau 算法来计算位置。

算法很简单，伪代码形式为

```
bezier(points, image)
  for t = 0:0.001:1
    p = recursive_bezier(points, t)
    image[p] = color

recursive_bezier(points, t)
  return recursive_bezier_impl(points, 0, points.size() - 1, t)

recursive_bezier_impl(points, left, right, t)
  if left == right
    return points[left];
  a = recursive_bezier_impl(points, left, right - 1, t)
  b = recursive_bezier_impl(points, left + 1, right, t)
  return lerp(a, b, t)
```

实现 anti-aliasing 的一个比较简单的方法可以是根据着色点与周围四个像素形成的四个面积而定

```
p10 O-------------------------O p11
    |     |                   |
    |     |                   |
    | a10 |        a11        |
    |     |                   |
    |     |                   |
    |----[X]------------------|
    |     |                   |
    | a00 |        a01        |
    |     |                   |
p00 O-------------------------O p01
```

着色点为 `[X]`，周围的四个像素为 `O`（`p00`，`p01`，`p10`，`p11`），边长为 1。`[X]`在四个像素中能形成 4 个区域，面积分别为 `a00`，`a01`，`a10`，`a11`。以  `[X]` 为中心画一个边长为 1 的正方形，它会被周围以四个像素为中心的正方形划分为四块。`[X]` 正方形在 `p00` 正方形上的面积正好是 `a11`，以此类推。各像素占面积的多少就是其亮度大小。

