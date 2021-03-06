# 5.7.4 奇异值分解和行列式

函数 `svd(M)` 可以把任意一个矩阵 `M` 作为一个参数, 且对 `M` 进行奇异值分解。这包括 一个和 `M` 列空间一致的正交列 `U` 的矩阵，一个和 `M` 行空间一致的正交列 `V` 的矩阵，以及 一个正元素 `D` 的对角矩阵，如 `M = U %*% D %*% t(V)`。`D` 实际上以对角元素向量的形式返回。`svd(M)` 的结果是由 `d`， `u` 和 `v` 构成的一个列表。

如果 `M` 是一个方阵，就不难看出

```R
> absdetM <- prod(svd(M)$d)
```

计算 `M` 行列式的绝对值。如果在各种矩阵中都需要这种运算，我们可以把它定义为一 个 R 函数

```R
> absdet <- function(M) prod(svd(M)$d)
```

此后, 我们可以把 `absdet()` 当一个 R 函数使用了。作为一个零碎但可能很有用的例子，你应该考虑写一个计算方阵迹(trace)的函数 `tr()` [提示: 你不需要使用显式的循环, 仔细看一下函数 `diag()`]。

R 有一个计算行列式(包括符号)的内置函数 `det` 和另外一个给出符号和模(对数坐标可选)的函数。