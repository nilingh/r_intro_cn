# 4.3 有序因子

因子的水平是以字母顺序排列的，或者显式地在 `factor` 中指定。

有时候因子的水平有自己的自然顺序并且这种顺序是有意义的。我们需要记录下来可能在进一步的统计分析中用到。函数 `ordered()` 就是用来创建这种有序因子。在其他方面，函数 `ordered()` 和 `factor` 基本完全一样。大多数情况下，有序和无序因子的唯一差别在于前者显示的时候反应了各水平的顺序。另外，在线性模型拟合的时候，两种因子对应的对照矩阵的意义是完全不同的。