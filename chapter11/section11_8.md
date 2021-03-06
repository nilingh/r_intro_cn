# 11.8 一些非标准模型

在结束本章前，我们简单提一下 R 里面某些用于某些特殊回归和数据分析问题的工具。

- **混合模型(Mixedmodels)**。推荐使用 [**nlme**](https://cran.r-project.org/web/packages/nlme/index.html) 包，里面提供了函数 `lme()` 和 `nlme()`。 这些函数可以用于混合效应模型(mixed-effects models)的线性和非线性回归。也就是说在线性和非线性回归中，一些系数受随机因素的影响。这些函数需要充分利用公式来描述模型。

- **局部近似回归(Local approximating regressions)**。函数 `loess()` 利用局部加权回归进行一个非参数回归。这种回归对显示一组凌乱数据的趋势和描述大数据集的整体情况非常有用。

  函数 `loess` 和投影跟踪回归(projection pursuit regression)的代码一起包含在标准包 `stats` 中。

- **稳健回归(Robust regression)**。有多个函数可以用于拟合回归模型，同时尽量不受数据中极端值的影响。在推荐包 [**MASS**](https://cran.r-project.org/web/packages/MASS/index.html) 中的函数 `lqs` 为高稳健性的拟合提供了最新的算法。另外，稳健性较低但统计学上高效的方法同样可以在包 [**MASS**](https://cran.r-project.org/web/packages/MASS/index.html)  中得到，如函数 `rlm`。

- **累加模型(Additive models)**。这种技术期望可以通过决定变量的平滑累加函数 (smooth additive function)构建回归函数。一般来说，每个决定变量都有一个平滑累加函数。用户贡献的包 [**acepack**](https://cran.r-project.org/web/packages/acepack/index.html) 里面的函数 `avas` 和 `ace` 以及包 [**mda**](https://cran.r-project.org/package=mda) 里面的函数 `bruto` 和 `mars` 为这种技术提供了一些例子。这种技术的一个扩充是用户贡献包 [**gam**](https://cran.r-project.org/package=gam)  和 [**mgcv**](https://cran.r-project.org/package=mgcv) 里面实现的**广义累加模型**。

- **树型模型(Tree-based models)**。除了利用外在的全局线性模型预测和解释数据， 还可以利用树型模型递归地在决定性变量的判断点上将数据的分叉分开。这样做会把数据最终分成几个不同组，使得组内尽可能相似而组间尽可能差异。这样常常会得到一些其他数据分析方法不能产生的的信息。 模型可以用一般的线性模型形式指定。该模型拟合函数是 `tree()`， 而且许多泛型函数，如 `plot()` 和`text()` 都可以很好的用于树型模型拟合结果的图形显示。 R 里面的树型模型函数可以通过用户贡献的包 [**rpart**](https://cran.r-project.org/package=rpart) 和 [**tree**](https://cran.r-project.org/package=tree) 得到。