# 作业 6：加速结构

这次作业代码量稍微大一些，主要是搬一下作业 5 的 `castRay`，并且要稍微修改一下才行。

关于额外内容 SAH，根据[参考资料](http://15462.courses.cs.cmu.edu/fall2015/lecture/acceleration/slide_023)来写也很简单，注意要处理特殊情况

- 划分时如果一边为 0 则视为失败
- 全都失败的时候要退回 naive 情形

build 的宏观伪代码如下

```c
build(objects)
  if objects.size() == 1
    build leaf node
  else if objects.size() == 2
    build by binary division
  else
    switch method
      case SAH
        try build by SAH
        if build success
          break
        // fall through
      case NAIVE
        build by NAIVE
```

