12.1.4 高级图形命令的参数

传递给高级绘图函数的命令有许多，如：

```R
add=TRUE
```

* 强制函数以低级绘图函数的形式运行，在当前的图上加载新的图形元素(仅适合于部分函数)。

```R
axes=FALSE
```

* 禁止产生坐标轴—当你想用函数 `axis()` 绘制个性化的坐标轴时非常有用。默认值是 `axes=TRUE`，表示产生坐标轴。

```R
log="x"
log="y"
log="xy"
```

* 让 `x` 轴，`y` 轴或者两者都成为对数坐标轴。这对很多图都有效，但不是全部。

```R
type=
```

* 参数 `type=` 控制输出图形(特别是线条)的类型：

`type="p"`

* 只显示点(默认)

`type="l"`

* 显示线条

`type="b"`

* (同时)显示点和线

`type="o"`

* 将点覆盖在线上

`type="h"`

* 绘制从点到零轴(x轴)的垂直线(*高密度(high-density)*)

`type="s"`

`type="S"`

* 步阶图。第一种形式，垂直线顶部匹配数据点；第二种形式，底部匹配。

`type="n"`

* 图形不显示。但是坐标轴仍然显示(默认)，并且坐标依然以数据设定。这个非常适合随后用低级绘图函数画图。

```R
xlab=string
ylab=string
```

* 设定 `x` 和 `y` 轴的标签。可以用这些参数修改默认标签。默认标签常常是用于高级绘图函数中的对象的名字。

```R
main=string
```

* 图形标题，以大字体置于图形的顶部。

```R
sub=string
```

* 子标题，以小字体放在*x-*轴底部。