---
layout:     post
title:      "Python3机器学习经典算法与应用"
subtitle:   "第三部分：k近邻算法kNN"
date:       2018-07-05 9:00:00
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

# k近邻算法

* 创建简单测试用例

```
import numpy as np
import matplotlib.pyplot as plt
raw_data_X = [[3.393533211, 2.331273381],
              [3.110073483, 1.781539638],
              [1.343808831, 3.368360954],
              [3.582294042, 4.679179110],
              [2.280362439, 2.866990263],
              [7.423436942, 4.696522875],
              [5.745051997, 3.533989803],
              [9.172168622, 2.511101045],
              [7.792783481, 3.424088941],
              [7.939820817, 0.791637231]
             ]
raw_data_y = [0, 0, 0, 0, 0, 1, 1, 1, 1, 1]
X_train = np.array(raw_data_X)
y_train = np.array(raw_data_y)
plt.scatter(X_train[y_train==0,0], X_train[y_train==0,1], color='g')
plt.scatter(X_train[y_train==1,0], X_train[y_train==1,1], color='r')
plt.show()
```
![](/img/in-post/post-python3machinelearning-3/post-python3machinelearning-3.1.jpg)

预测

```
x = np.array([8.093607318, 3.365731514])

plt.scatter(X_train[y_train==0,0], X_train[y_train==0,1], color='g')
plt.scatter(X_train[y_train==1,0], X_train[y_train==1,1], color='r')
plt.scatter(x[0], x[1], color='b')
plt.show()
```

![](/img/in-post/post-python3machinelearning-3/post-python3machinelearning-3.2.jpg)

```
from math import sqrt
distances = []
for x_train in X_train:
    d = sqrt(np.sum((x_train - x)**2))
    distances.append(d)
    
    

```
