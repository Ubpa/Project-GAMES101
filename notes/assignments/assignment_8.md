# 作业 8：质点弹簧系统

分清楚方向很关键

当 `steps_per_frame` 较小时，很不稳定，显式欧拉法会直接飞出去；较大时稍微稳定性。

全局阻尼理解成空气阻力
$$
f=-k_d\cdot v
$$
显式 Verlet 方法在 ppt 里描述的不多，可以参考[关于作业8的一些问题解答](http://games-cn.org/forums/topic/guanyuzuoye8deyixiewentijieda/)，具体地，就是将求解分为两步：

- 直接修改位置以满足弹簧约束（各结点根据弹簧长度进行移动，以质量倒数为权重）
- 忽略约束，直接根据其他外力（如重力）修改位置

