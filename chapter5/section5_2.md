# 5.2 数组索引以及数组分割

数组元素可以通过给定数组名及其后方括号中用逗号隔开的下标访问。

更为一般的是，数组分割可以通过在下标位置给定一系列索引向量实现；需要注意的是，如果某个位置上给定的索引向量为空，则该下标处所有可能值都会被取到。

延续前面的例子，`a[2,,]` 是一个 4 × 2 的数组。它的维度向量为 `c(4,2)`，数据向量依次包括下面的值

```R
c(a[2,1,1], a[2,2,1], a[2,3,1], a[2,4,1], a[2,1,2], a[2,2,2], a[2,3,2], a[2,4,2])
```

`a[,,]` 表示整个数组。这和忽略下标直接使用 `a` 效果是一样的。

对于数组 `Z`，用 `dim(Z)` 可以对该数组维度向量进行显式的访问(可以放在赋值的任何一边)。 

还有，如果一个数组仅给出一个下标或索引向量，那么只有数据向量中对应的值才会被访问；在这种情况下，维度向量会被忽略的。但是，如果单个索引不是一个向量而是一个数组，可能就不是这样了，具体可以看下面的讨论。