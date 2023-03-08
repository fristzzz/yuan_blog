---
title: "分层分析"
date: "2023-03-09"
categories: [modelling]
---

# 层次分析法

将要决策的问题及有关因素分解成目标、准则、方案等层次，进而进行定性和定量分析的决策方法。
- 特征： 合理地将定性与定量决策结合起来，按照思维、心理的规律把决策过程层次化、数量化。

大致步骤：
1. 建立层次结构模型
2. 构造出各层次中的所有判断矩阵
3. 层次单排序及一致性检验
4. 层次总排序及一致性检验

## 层次的建立

1. 最高层： 一般是目标层
2. 中间层， 中间环节，主要考虑指标和准则
3. 最底层： 包含为了实现目标可供选择的各种方案

> 只考虑相邻两个层次间自上而下的支配作用，同一层次元素间**相互独立**
> 否则需要网络分析法

## 构造判断矩阵

![](/image/modelling/comparing_matrix.png)




## 层次单排序及一致性检验

### 原理

- 一致性即判断的一种传递性，比如a的重要性是b的2倍，b的重要性是c的2倍，则a的重要性必须是c的4倍。否则就是判断的不一致。
- 所谓一致性检验是指判断矩阵允许有一定**不一致的范围**

## 总结

怎么跟运筹学这么像，看了看案例，大致步骤依然是定义变量、写出目标函数、写出约束条件、求解。

层次分析大致是这样：

1. 写出偏好，并标明权重
2. 分析每一个偏好中所有选择的占比，一般是列**比较矩阵**（相对重要性）。但我觉得这玩意太花哨又不实用，并不是很简练。
3. 检验一致性，能用就用。一致可以理解为博弈论中的Preferrence Relationship. 如果出现not transitive, 则为不一致。

参考：

- <a href="https://www.cnblogs.com/BlueMountain-HaggenDazs/p/4278049.html">层次分析法</a>