# 1.3 R 和统计

我们对 R 环境的介绍中没有提到*统计*，但是大多数人用 R 就是因为它的统计功能。不过，我们宁可把 R 当作一个内部实现了许多经典的时髦的统计技术的环境。 部分的统计功能是整合在 R 环境的底层，但是大多数功能则以*包*的形式提供。大约 有25个包和 R 同时发布(被称为“标准” 和“推荐” 包)，更多的包可以通过网上或其他地方的CRAN 社区(参见 http://CRAN.R-project.org) 得到。关于包更多的细节将在后面的章节叙述(见包一章)。

大多数经典的统计方法和最新的技术都可以在 R 中直接得到。终端用户只是需要花点精力去找到一下就可以了。

S(也包括 R) 和其他主要的统计系统在观念上有着重要的差异。在 S 语言中，一次统计分析常常被分解成一系列步骤，并且所有的中间结果都被保存在对象(object) 中。因此，SAS 和SPSS 为回归和判别分析提供了丰富的屏幕输出内容，但 R 给出屏幕输出却很少。它将结果保存在一些合适的对象中以便于用 R 里面的函数做进一步的分析[^2]。



---

[^2]: 译者注：这点在 R 编程里面非常的重要。