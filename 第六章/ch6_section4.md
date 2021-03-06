# 通过网格搜索调参




机器学习算法中有两类参数：从训练集中学习到的参数，比如逻辑斯蒂回归中的权重参数，另一类是模型的超参数，也就是需要人工设定的参数，比如正则项系数或者决策树的深度。


前一节，我们使用验证曲线来提高模型的性能，实际上就是找最优参数。这一节我们学习另一种常用的超参数寻优算法：网格搜索(grid search)。





网格搜索听起来高大上，实际上简单的一笔，就是暴力搜索而已，我们事先为每个参数设定一组值，然后穷举各种参数组合，找到最好的那一组。

![](https://ooo.0o0.ooo/2016/06/28/57726f0da6780.png)


GridSearchCV中param_grid参数是字典构成的列表。对于线性SVM，我们只评估参数C；对于RBF核SVM，我们评估C和gamma。

最后， 我们通过best\_parmas_得到最优参数组合。

sklearn人性化的一点是，我们可以直接利用最优参数建模(best\_estimator_)：


![](https://ooo.0o0.ooo/2016/06/28/5772718b8e2bc.png)



**Note** 网格搜索虽然不错，但是穷举过于耗时，sklearn中还实现了随机搜索，使用 RandomizedSearchCV类，随机采样出不同的参数组合。
