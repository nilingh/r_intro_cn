# 11.5 更新拟合模型

函数 `update()` 是一个非常便利的函数。它允许拟合一个比原先模型增加或减少一个项的模型。它的形式是

```R
> new.model <- update(old.model, new.formula)
```

 在 *new.formula* 中，公式中包含的句点，`.`， 仅仅表示“旧的公式模型中的对应部分”。例如

```R
> fm05 <- lm(y ~ x1 + x2 + x3 + x4 + x5, data = production) 
> fm6 <- update(fm05, . ~ . + x6)
> smf6 <- update(fm6, sqrt(.) ~ .)
```

这将分别拟合从数据框 `production` 中得到的五个变量的多重回归模型，拟合额外增加一个变量的六个回归量的模型，和进一步对响应值进行平方根变换后的模型拟合。

注意参数 `data=` 在最开始调用模型拟合函数的时候指定。这个信息将会通过拟合模型对象传递给函数 `update()` 及其相关者。

符号 `.` 同样可以用在其他情况下，不过含义有点不同。如 

```R
> fmfull <- lm(y ~ . , data = production)
```

它将会拟合响应量 `y` 对数据框 `production` 中所有变量回归的模型。 其他研究逐步回归的函数是 `add1()`， `drop1()` 和 `step()`。 从字面上就可以看出这些函数的意义，更细节的内容可以参考在线帮助文档。