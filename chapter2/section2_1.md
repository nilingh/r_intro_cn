# 2.1 向量和赋值

R 在已经命名的数据结构(data structure)上起作用的。其中，最简单的结构就是由一串有序数值构成的数值向量(vector)。假如我们要创建一个含有五个数值的向量x，且这五个值分别为10.4，5.6，3.1，6.4 和 21.7，则 R 中的命令为

```R
> x <- c(10.4, 5.6, 3.1, 6.4, 21.7)
```

这是一个用函数 `c()` 完成的赋值语句。这里的函数 `c()` 可以有任意多个参数，而它返回的值则是一个把这些参数首尾相连形成的向量[^1]。

在 R 环境里面，单个的数值也是被看作长度为1的向量。

注意一下赋值符号 (`<-`)，它实际上包括两个字符，即 `<` (“小于号”) 和 `-` (“负号”)。 这两个字符在方向上要求严格一致[^2]并且”指向“被表达式赋值的对象。在许多情况 下，`=` 可以代替使用。

赋值也可以用函数 `assign()` 实现。下面的命令和前面的赋值命令等价: 

```R
> assign("x", c(10.4, 5.6, 3.1, 6.4, 21.7))
```

我们常用的赋值符 `<-` 可以看作是该命令一个语义上的缩写。 当然，还可以从另外一个方向上赋值。用下面的语句，可以完成上面同样的赋值工作

```R
> c(10.4, 5.6, 3.1, 6.4, 21.7) -> x
```

如果一个表达式是一个完整的命令，那么它的值将会被显示在屏幕上并且不能被别的对象访问[^3]。因此，如果我们运行语句

```R
> 1/x
```

五个数的倒数就会在终端显示(注意，x 的值没有改变)。 进一步的赋值

```R
> y <- c(x, 0, x)
```

会创建一个含有11个元素的向量 y，其中包括两份 x 拷贝和位于中间的一个0。



---

[^1]:函数c() 的对向量格式和list 模式的参数起的作用可能会有点差异。具体参见列表的连接
[^2]:译者注:‘->’和‘<-’是一致的，但’‘-<’与‘>-’就不一致了。
[^3]:实际上，在其他命令运行前，它是保存在变量.Last.value 中。译者注:当然，你还可以直接在屏 幕上直接拷贝表达式的输出值。