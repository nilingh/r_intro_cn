# 5.4 array() 函数

除了用设定一个向量 `dim` 属性的方法来构建数组，它还可直接通过函数 `array` 将向量转换得到，具体格式为

```R
> Z <- array(data vector, dim vector) 
```

假定向量 `h` 有24个或更少的数值，那么命令

```R
> Z <- array(h, dim=c(3,4,2))
```

就会利用 `h` 在 `Z` 中创建一个3×4 ×2的数组。如果 `h` 的长度正好是24，那么就和下面的命令等价

```R
> dim(Z) <- c(3,4,2)
```

如果 `h` 的长度小于24，它的元素将会被循环使用直到长度为24 (见向量元素的循环使用规则)。一个极端但又普遍的例子是

```R
> Z <- array(0, c(3,4,2))
```

这样就会使得 `Z` 是一个所有值都是0的数组。此时，`dim(Z)` 表示维度向量 `c(3,4,2)`，`Z[1:24]` 表示数据向量(就像在向量 `h` 中一样)。空下标的 `Z[]` 和没有下标的 `Z` 都表示整个数组。 数组可用于算术表达式中，并且结果就是一个基于数据向量的对应元素运算而得到的数组。所有操作数的属性 `dim` 必须一致，而这个属性同样也是最终结果的维度向量。因此，如果 `A`，`B` 和 `C` 是相似矩阵，那么

```R
> D <- 2*A*B + C + 1
```

`D` 同样是一个相似矩阵。它的值是由给定操作数的对应元素计算所得。但是对于数组和向量的混合运算还是要小心一点。

* [5.4.1 向量和数组混合运算以及循环使用原则](chapter5/section5_4_1.md)