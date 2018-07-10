---
layout:     post
title:      "Python3机器学习经典算法与应用"
subtitle:   "第二部分：Jupyter Notebook, numpy和matplotlib"
date:       2018-07-04 9:00:00
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

# Jupyter Notebook 的快捷键

Jupyter Notebook 有两种键盘输入模式。编辑模式，允许你往单元中键入代码或文本；这时的单元框线是绿色的。命令模式，键盘输入运行程序命令；这时的单元框线是灰色。

## 命令模式（按键Esc开启）

Enter : 转入编辑模式

Shift-Enter : 运行本单元，选中下个单元

Ctrl-Enter : 运行本单元

Alt-Enter : 运行本单元，在其下插入新单元

Y : 单元转入代码状态

M :单元转入markdown状态

R : 单元转入raw状态

1 : 设定 1 级标题

2 : 设定 2 级标题

3 : 设定 3 级标题

4 : 设定 4 级标题

5 : 设定 5 级标题

6 : 设定 6 级标题

Up : 选中上方单元

K : 选中上方单元

Down : 选中下方单元

J : 选中下方单元

Shift-K : 扩大选中上方单元

Shift-J : 扩大选中下方单元

A : 在上方插入新单元

B : 在下方插入新单元

X : 剪切选中的单元

C : 复制选中的单元

Shift-V : 粘贴到上方单元

V : 粘贴到下方单元

Z : 恢复删除的最后一个单元

D,D : 删除选中的单元

Shift-M : 合并选中的单元

Ctrl-S : 文件存盘

S : 文件存盘

L : 转换行号

O : 转换输出

Shift-O : 转换输出滚动

Esc : 关闭页面

Q : 关闭页面

H : 显示快捷键帮助

I,I : 中断Notebook内核

0,0 : 重启Notebook内核

Shift : 忽略

Shift-Space : 向上滚动

Space : 向下滚动

### 编辑模式 ( Enter 键启动)

Tab : 代码补全或缩进

Shift-Tab : 提示

Ctrl-] : 缩进

Ctrl-[ : 解除缩进

Ctrl-A : 全选

Ctrl-Z : 复原

Ctrl-Shift-Z : 再做

Ctrl-Y : 再做

Ctrl-Home : 跳到单元开头

Ctrl-Up : 跳到单元开头

Ctrl-End : 跳到单元末尾

Ctrl-Down : 跳到单元末尾

Ctrl-Left : 跳到左边一个字首

Ctrl-Right : 跳到右边一个字首

Ctrl-Backspace : 删除前面一个字

Ctrl-Delete : 删除后面一个字

Esc : 进入命令模式

Ctrl-M : 进入命令模式

Shift-Enter : 运行本单元，选中下一单元

Ctrl-Enter : 运行本单元

Alt-Enter : 运行本单元，在下面插入一单元

Ctrl-Shift-- : 分割单元

Ctrl-Shift-Subtract : 分割单元

Ctrl-S : 文件存盘

Shift : 忽略

Up : 光标上移或转入上一单元

Down :光标下移或转入下一单元

# Jupyter Notebook 的魔法命令

* %run *.py

使用此命令运行外部python文件（默认是当前目录，最好加上绝对路径）

* %time statement

用此命令计算statement的运行时间

* %timeit statement

用此命令计算statement的平均运行时间，timeit会多次运行statement，最后得到一个更为精准的预期运行时间。

%time一般用于耗时长的代码段，%timeit一般用于耗时短的代码段。

* lsmagic 列出所有魔法命令 

# Numpy

NumPy是Python语言的一个扩充程序库。支持高级大量的维度数组与矩阵运算，此外也针对数组运算提供大量的数学函数库。Numpy内部解除了Python的PIL(全局解释器锁),运算效率极好,是大量机器学习框架的基础库!

Python的List不要求存储同样的类型，带来效率问题。

array的缺点是没有将数据当做向量或者矩阵，不支持基本运算。

## Numpy简单创建数组

```python
import numpy as np
# 创建简单的列表
a = [1, 2, 3, 4]
# 将列表转换为数组
b = np.array(b)
```

`np.arange` 类似range函数

`np.array` 用来生成矩阵

## Numpy查看数组属性

数组元素个数`b.size`

数组形状`b.shape`

数组维度`b.ndim`

```
# 每一个[]代表一维，比如
# [[[1,2,3],[4,5,6]],[[7,8,9],[10,11,12]]], 代表矩阵的维度是(2,2,3)
# 其中第一个2，代表最外层的两个[]，第二个2代表第二层[]，第三个3代表最里层的维度。
n=np.array([[1,2,3,4],[5,6,7,8]])
print n, n[0,2], n[1,1]

m=np.array([[[1,2,3],[4,5,6]],[[7,8,9],[10,11,12]]])
print m.shape
```

数组元素类型`b.dtype`

## 快速创建N维数组的api函数

创建10行10列的数值为浮点1的矩阵`array_one = np.ones([10, 10])`

创建10行10列的数值为浮点0的矩阵`array_zero = np.zeros([10, 10])`

从现有的数据创建数组: array(深拷贝)，asarray(浅拷贝)

## Numpy创建随机数组`np.random`

* 均匀分布

`np.random.rand(10, 10)` 创建指定形状(示例为10行10列)的数组(范围在0至1之间)

`np.random.uniform(0, 100)` 创建指定范围内的一个数

`np.random.randint(0, 100)` 创建指定范围内的一个整数

* 正态分布

给定均值/标准差/维度的正态分布 `np.random.normal(1.75, 0.1, (2, 3))`

* 数组的索引, 切片

```
# 正态生成4行5列的二维数组
arr = np.random.normal(1.75, 0.1, (4, 5))
print(arr)
# 截取第1至2行的第2至3列(从第0行算起)
after_arr = arr[1:3, 2:4]
print(after_arr)
```

* 改变数组形状(要求前后元素个数匹配)

```
print("reshape函数的使用!")
one_20 = np.ones([20])
print("-->1行20列<--")
print (one_20)

one_4_5 = one_20.reshape([4, 5])
print("-->4行5列<--")
print (one_4_5)
```

未完
