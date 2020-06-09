

# 2.7 索引向量；选出和修改一个数据集的子集

一个向量的元素的子集(subset)可以通过在该向量名后面加上一个用方括号包括的索引向量来得到。推而广之，如果一个表达式的结果是向量，则可以类似的直接在该表达式后面加上一个用方括号包括的索引向量以得到该向量的元素的子集。

这种索引向量可以采用下面四种不同方式的任何一种。

1. **逻辑向量**。这种情况下，索引向量会被循环至和被挑选元素的向量长度一致。向量中对应索引向量元素为 `TRUE` 的元素将会被选中，而那些对应 `FALSE` 的元素则被忽略。例如

   ```R
   > y <- x[!is.na(x)]
   ```

   这将创建(或重建)一个对象 `y`，其中包含有 `x` 的中非缺损(non-missing)元素，且次序不变。注意，如果 `x` 含有缺损(missing)值，`y` 在长度上将会比 `x` 短。同样 

   ```R
   > (x+1)[(!is.na(x)) & x>0] -> z
   ```

   将创建一个对象 `z` 并且把向量 `x+1` 的值赋给它，其中要求 `x` 中对应的元素既非缺损又是正值。

2. **正整数向量**。这种情况下，索引向量的值必须在集合 {1, 2,  . . . , `length(x)`} 中。向量中对应的元素会被选中，并且结果向量中的次序和索引向量中的*次序一致*。这种索引向量可以是任意长度的，结果向量的长度和索引向量完 全一致。如 `x[6]` 表示 `x` 的第六个元素，此外

   ```R
   > x[1:10]
   ```

   选择 `x` 的前10个元素(假定 `length(x)` 长度不小于10)。同样

   ```R
   > c("x","y")[rep(c(1,2,2,1), times=4)]
   ```

   (看上去好像不可能)会产生一个长度为16，由"x", "y", "y", "x" 重复4次而构成的字符向量。

3. **负整数向量**。这种索引向量指定被*排除*的元素而不是包括进来[^1]。因此

   ```R
   > y <- x[-(1:5)]
   ```

   将 `x` 中除开始五个元素外的其他元素都赋给 `y`。

4. **字符串向量**。这可能仅仅用于一个对象可以用 `names` 属性来识别它的元素。这种情况下，名字(names)向量的子向量(sub-vector)可以像上面第二条提到的正整数标签一样使用。

   ```R
   > fruit <- c(5, 10, 1, 20)
   > names(fruit) <- c("orange", "banana", "apple", "peach")
   > lunch <- fruit[c("apple","orange")]
   ```

   *字母数字*索引(alphanumeric *names*)相比*数值*索引(*numeric indices*)的好处通常是容易记住。后面我们将看到，该用法在与数据框(data frames)有关的操作中尤其有用。

一个索引表达式同样可以出现在赋值操作的末尾接受端。在这种情况下，赋值操作*仅仅作用在那些索引指定的向量元素上*。表达式必须以 `vector[index_vector]` 的形式出现， 其中向量名在此处意义不大，可以用任何表达式代替。[^2]

例如

```R
> x[is.na(x)] <- 0
```

将会用0替换 `x` 中所有的缺省值，而且

```R
> y[y < 0] <- -y[y < 0]
```

和下方表达式作用相同

```R
> y <- abs(y)
```

------

[^1]: 译者(丁国徽)注：索引向量中，不可以同时出现正整数和负整数。

[^2]: 译者(丁国徽)注：被赋值的向量必须吻合索引向量的长度，特别在逻辑向量中它的长度必须和被建索引的向量长度一致。
