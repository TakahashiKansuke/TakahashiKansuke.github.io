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


