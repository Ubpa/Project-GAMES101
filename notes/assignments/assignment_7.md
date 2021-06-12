# 作业 7：路径追踪

实现上有几个细节点

- PPT 里的伪代码是 `shade`，而我们要实现的是 `castRay`，两者差了一个 `intersection`，因此代码结构上略有不同
- 深度为 0 时叠加上 emission，否则如果有 emission 就退出（避免重复计算光源的贡献）
- 除 pdf 前先判定 pdf 为正（或者大于 `EPSILON`）
- 为了在求 shadow 和递归时避免自阴影，可以调整 `ray` 的 `t_min` 和 `t_max`，注意检测碰撞的实现代码中，合法的 `t` 应该在 `t_min` 和 `t_max` 之间

另外，microfacet 材质可以选用 GGX，为了改善效果，可以使用 VNDF 采样方法