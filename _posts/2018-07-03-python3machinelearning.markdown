---
layout:     post
title:      "Python3机器学习经典算法与应用"
subtitle:   "第一部分：监督学习，非监督学习，半监督学习，增强学习，批量学习，在线学习，参数学习和非参数学习"
date:       2018-07-03 18:00:00
author:     "HanLu"
header-img: "img/post-python3machinelearning.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 机器学习
---

> 这篇博文将会详细总结之前学过的各种机器学习算法原理，如：kNN，SVM，线性回归，决策树，多项式回归，随机森林，逻辑回归，集成学习，模型正则化，PCA，模型选择，模型调试。并通过使用这些算法解决真实场景问题。对不同算法进行对比试验，对同一算法的不同参数进行对比试验。对部分算法进行底层编写。

> 语言：Python 3

> 框架：Scikit-learn，numpy，matplotlib...

> IDE：Jupyter Notebook，Anaconda，Pycharm

> 数据集：Scikit-learn中内置的数据集或通过Scikit-learn可以直接下载的数据集，MNIST数据集

## 监督学习

给机器的训练数据拥有“标记”或者“答案” （分类，回归）

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.1.jpg)

 k近邻，线性回归和多项式回归，逻辑回归，SVM，决策树和随机森林
 
 ## 非监督学习

给机器的训练数据没有任何“标记”或者“答案” （聚类）

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.2.jpg)

非监督学习的意义：1. 聚类分析

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.3.jpg)

2. 对数据进行降维处理 

* 特征提取：信用卡的信用评级和人的胖瘦无关？
* 特征压缩：PCA

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.4.jpg)

3. 方便可视化

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.5.jpg)

4. 异常检测

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.6.jpg)

## 半监督学习

一部分数据有“标记”或者“答案”，另一部分没有 （更常见：各种原因产生的标记缺失）

通常都先使用无监督学习手段对数据做处理，之后使用监督学习手段做模型的训练和预测。

## 增强学习

根据周围环境的情况采取行动，根据采取行动的结果，学习行动方式。（无人驾驶，机器人）

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.7.jpg)

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.8.jpg)

## 批量学习（离线学习）和在线学习

* 批量学习（Batch Learning）：优点：简单 缺点：每次重新批量学习运算量巨大，在某些环境变化非常快的情况下不适用。

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.9.jpg)

问题：如何适应环境变化？ 解决方案：定时重新批量学习

* 在线学习（Online Learning）：优点：及时反映新的环境变化

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.10.jpg)

问题：新的数据带来不好的变化？ 解决方案：需要加强对数据进行监控

其他：也适用于数据量巨大，完全无法批量学习的环境。

## 参数学习和非参数学习

* 参数学习：一旦学习到了参数，就不再需要原有的数据集。

![](/img/in-post/post-python3machinelearning-1/post-python3machinelearning-1.11.jpg)

* 非参数学习：不对模型进行过多假设，非参数不等于没参数。

---

奥卡姆的剃刀：简单的就是好的

没有免费的午餐原理：可以严格地数学推导出：任意两个算法，他们的期望性能是相同的。脱离具体问题谈哪个算法好是没有意义的。在面对一个具体问题的时候，尝试使用多种算法进行对比试验，是必要的，





