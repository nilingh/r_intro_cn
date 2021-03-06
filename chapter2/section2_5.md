# 2.5 缺损值

在某些情况下，向量的元素可能有残缺。当一个元素或者值在统计意义上“不可得到”(not available)或者“值丢失” (missing value)，相关位置可能会被保留并且赋予一个特定的值 `NA`[^1]。通常，任何含有 `NA` 数据的运算结果都将是 `NA` 。这样做法的道理很简单，如果一次操作的数据都是残缺的，那么结果也必然是不可预料的，因此也是不可得的。

函数 `is.na(x)` 返回一个和 `x` 同等长度的逻辑向量。它的某个元素值为 `TRUE` 当且仅当 `x` 中对应元素是 `NA`。

```R
> z <- c(1:3,NA);  ind <- is.na(z)
```

特别要注意的是逻辑表达式 `x == NA` 和 `is.na(x)` 完全不同，因为 `NA` 不是一个真实的值而是一个符号以表示某个量是不可得到的(not available)。因此 `x == NA` 得到的是一个长度和 `x` 一致的向量，它的所有元素的值都是 `NA`，因为该逻辑表达式本身不完整，因此它也是不可确定的。

还要注意数值计算会产生第二种“缺损”值，也称为非数值(Not a Number) `NaN`。例如

```R
> 0/0
```

或者

```R
> Inf - Inf
```

得到的都是 `NaN`，这是因为它们的结果都不能被显式的定义。

总之，对于 `NA` 和 `NaN` 用 `is.na(xx)` 检验都是 `TRUE`。为了区分它们，`is.nan(xx)` 就只对是 `NaN` 的元素显示 `TRUE`。 

当字符向量以没有引号的形式输出时，缺损值[^2]可能会以 `<NA>` 形式输出。

```R
> a <- c("a","b",NA)
> a
[1] "a" "b" NA
> print(a, quote = F)
[1] a b <NA>
```





---

[^1]: 译者(丁国徽)注：我在0.01β版里面用缺省值这个汉语概念来描述这种数据，PDF版本里面改用缺损值描述。这样可能更为准确一点。
[^2]: 译者(丁国徽)注：下面的例子由黄荣贵网友提供。