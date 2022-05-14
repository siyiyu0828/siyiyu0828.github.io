---
title: "周报"
date: 2022-05-14
categories:
  - Blog
tags:
  - report
---

# 周报

# 5.8-5.14

1. 完成论文数值例子部分
2. 完成论文初稿

# 4.24-5.7

1. 准备复习考试-随机过程和优化过程。
2. 科创项目申报。
3. 将论文已完成部分翻译成英文。

# 4.17-4.23

1. 查阅相关参考文献，完成论文引言部分的撰写。
2. 准备复习第九周结课考试随机过程和优化理论

# 4.10-4.16

- [ ] 初步完成论文初稿预备知识及主要结论的撰写。开始构思论文初稿引言部分撰写，收集整理四元数、四元数神经网络、神经网络多稳定性的发展现状的文献资料。
- [ ] 准备4月15日组会汇报内容：《神经网络与深度学习》第四章前馈神经网络。



# 3.27-4.9

## 文献阅读情况

### Multiple and Complete Stability of Recurrent Neural Networks With Sinusoidal Activation Function

1. 研究内容：本文介绍了具有正弦激活函数的递归神经网络的多稳定性和完全稳定性的新理论结果。提供了足够的标准来确定具有不同数量平衡的递归神经网络的稳定性，例如唯一平衡、有限和可数无限数量的平衡。推导了平衡的多重指数稳定性判据，估计了平衡的吸引域。此外，为没有时间延迟的循环神经网络推导出了平衡完全稳定性和不稳定性的标准。阐述了具有有限和可数无限数量的平衡的两个说明性示例以证实结果。
2. 创新点：与具有有限数量平衡的现有稳定性结果相比，这里的新标准适用于有限和可数无限数量的平衡。激活函数考虑正弦激活函数。

## 一些思考

将上诉文章中的模型推广到四元数神经网络。考虑具有时滞的n维四元数神经网络，对所有的$r=1,2\dots,n$

$$\begin{equation}
\begin{aligned}
\frac{d q_{r}(t)}{d t}=-c_{r} q_{r}(t)+\sum_{s=1}^{n} a_{rs}f_{s}\left(q_{s}(t)\right)+\sum_{s=1}^{n} b_{rs} f_{s}\left(q_{s}(t-\tau(t))\right)+U_{r}
\end{aligned}
\end{equation}$$
其中$q_{r}(t) \in \mathbb{Q}$表示四元数神经网络在$t$时刻的状态, $c_{r} \in \mathbb{R}$($c_{r}>0$)是自反馈系数, $a_{rs}=a_{rs}^{R}+a_{rs}^{I}i+a_{rs}^{J}j+a_{rs}^{K}k \in \mathbb{Q}$,$b_{rs}=b_{rs}^{R}+b_{rs}^{I}i+b_{rs}^{J}j+b_{rs}^{K}k \in \mathbb{Q}$分别表示无时滞和有时滞的常值连接权值,$f(.) :\mathbb{Q}\rightarrow \mathbb{Q}$表示四元数神经网络的激活函数,本文仅考虑正弦激活函数,具体定义假设1.$u_{r}=u_{r}^{R}+u_{r}^{I}i+u_{r}^{J}j+u_{r}^{K}k \in \mathbb{Q}$表示常值外部输入值,$\tau(t)$是时滞项,满足$0 \le \tau(t) < \tau$.

# 3.20-3.26

## 相关课程学习

学Krasjet的四元数与三维旋转基本看完(有些看不懂暂时跳过了)

## 文献阅读情况

主要学习了四元数的一些相关知识，把我认为比较重要的点做了一些总结。

- 四元数乘法不遵守交换律，也就是对于任意两个四元数$q_1=a+bi+cj+dk$,$q_2=e+fi+gj+hk$一般情况下$q_{1}q_{2}\ne q_{2}q_{1}$.如果令$\mathbf{v}=[b\ c\ d]^T, \mathbf{u}=[f\ g\ h]^T$,则有
  $$
  \begin{aligned}
  \mathbf{v} \cdot \mathbf{u} &=b f+c g+d h \\
  \mathbf{v} \times \mathbf{u} &=\left|\begin{array}{lll}
  \mathbf{i} & \mathbf{j} & \mathbf{k} \\
  b & c & d \\
  f & g & h
  \end{array}\right| \\
  &=(c h-d g) \mathbf{i}-(b h-d f) \mathbf{j}+(b g-c f) \mathbf{k}
  \end{aligned}
  $$
  于是对于任意四元数$q_1=[a,\mathbf{v}]^T$,$q_2=[e,\mathbf{u}]^T$,$q_1q_2$的结果是:
  $$
  q_{1} q_{2}=[a e-\mathbf{v} \cdot \mathbf{u}, s \mathbf{u}+t \mathbf{v}+\mathbf{v} \times \mathbf{u}]
  $$
  这个公式高度概括了两个四元数的乘积形式，简单好记。

- 四元数的共轭，对一个四元数$q=[s,\mathbf{v}]$它的共轭记为$q^*=[s,-\mathbf{v}]$. 一个值得注意的点是四元数共轭满足乘法交换律即$q^*q=qq^*$,由于四元数的逆的定义为满足$qq^{-1}=q^{-1}q(q \ne 0)$中的$q^{-1}$为四元数的逆，可以发现通过四元数的共轭来找四元数的逆会非常高效。即
  $$
  q^{-1}=\frac{q^{*}}{\|q\|^{2}}
  $$

- 四元数与3D旋转里面有一些处理非常巧妙，以后涉及这部分知识可以再回来看看。

- 学习了四元数矩阵特征值的一些相关知识，主要参考文献"Quaternions and Matrices of Quaternions"。由于四元数不满足乘法交换律，所以在涉及特征值时，要分为左特征值和右特征值。

  1. 任意一个$n \times n$的四元数斜域上的矩阵都至少存在一个左特征值.
  2. 与左特征值相比，目前右特征值已经得到了很好的研究，因为右特征值更有用。这也启示我，在以后研究问题涉及四元数矩阵特征值问题，可以先只考虑其右特征值。关于右特征值的部分还在继续学习。

# 3.13-3.19

## 文献阅读情况

### 一类连续Hopfiled神经网络绝对稳定的充要条件

1.模型：


$$
\begin{equation}
c_{i} \dot{x}_{i}=-\frac{1}{R_{i}} x_{i}+\sum_{j=1}^{n} \Gamma_{i j} g_{j}\left(x_{j}\right)+i_{i}, \quad i=1,2, \cdots, n
\end{equation}
$$
2.研究内容：本文讨论了一类连续HOpfield型神经网络绝对稳定的充分必要条件:若连接权矩阵是对称的,则保证系统绝对稳定的充分必要条件是连接权矩阵半负定:若连接权矩阵对角以外的元素均为非负的,则保证系统绝对稳定的充分必要条件是一T的所有主子行列式非负.

3.研究意义：研究意义:此结论的意义在于给出的这类神经网络是在求解最优化问题时保证不出现伪响应的最大一类网络.

### Novel Criteria of Stability for Delayed Memristive Quaternionic Neural Networks: Directly Quaternionic Method

1.这篇文章主要研究变时滞记忆四元神经网络的稳定性。利用微分包含理论中凸包的闭包，将MQNN转化为变系数连续四元神经网络（QNN）。利用不动点定理，得到了MQNN平衡解的存在唯一性。然后给出了四元数函数范数的导数公式。利用该公式、M -矩阵理论和不等式技术，得到了确定MQNN全局指数稳定性的代数标准。

2.阅读这篇文献最大的收获是这篇文章是直接将四元数神经网络当成整体来处理，并且给出了四元数神经网络激活函数的定义方式以及四元函数范数的导数公式。

## 一些思考

能否将一类连续Hopfiled神经网络绝对稳定的充要条件推广到四元数神经网络，四元数神经网络激活函数定义参考文献Novel Criteria of Stability for Delayed Memristive
Quaternionic Neural Networks: Directly Quaternionic Method中的方法。但有一定难度，目前还在推导阶段，还需要加强四元数的学习。



