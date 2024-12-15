---
title: ACEE数模复习
published: 2024-12-15
description: "工高数学建模的复习"
image: "./dawn.jpg"
tags: ["ACEE", "浙江大学工高班", "数学建模", "review"]
category: Review
draft: false
---
# 工高极速复习

# 14 差分方程

## 差分

$\Delta y_n=y_{n+1}-y_{n}$后向差分，

$$
\begin{align}
\Delta^2y_n&=(y_{n+2}-y_{n+1})-(y_{n+1}-y_{n})=y_{n+2}-2y_
{n+1}+y_n\\ &\cdots\\\Delta^m y_n&=\sum _{k=0}^m (-1)^{m-k}\binom{m}{k}y_{n+k}
\end{align}
$$

差分方程是含有未知函数的有限差分的函数

- **$m$阶线性差分方程**

$$
a_m(n)y_{n+m}+\cdots a_0(n)y_n=f_n
$$

- **二阶线性常系数齐次差分方程**
  $$
  x_{n+2}+a_1x_{n+1}+a_2x_n=0
  $$

对特征方程$\lambda ^2+a_1\lambda +a_2=0$

- $\lambda _{1,2}$，则通解为$x_n=C_1\lambda _1^n+C_2\lambda _2^n,\lim x_n=0\Leftrightarrow |\lambda_{1,2}|<1$
- $\lambda,x_n=C_1\lambda ^n+C_2n\lambda ^n$，这个可以归纳证明

### 经济学与经济模型

- **需求函数**(demand): $Q^d=f(P)(P=f^{-1}(Q^d))$价格需求
- **供给函数**(supply): $Q^s=g(P)(P=g^{-1}(Q^s))$价格供给

均衡equiilibrium ，$p^*:f(p^*)=g(p^*)$

动态模型与静态模型:**动态均衡价格模型**

$$
\begin{align}
Q_n^s=g(P_{n-1})\\
Q_n^d=f(P_n)\\Q_n^d=Q_n^s
\end{align}
$$

:::note[蛛网模型]

- 记在周期 $n$ 某种商品的供求量为 $x_n$，价格为 $y_n$。
- 需求函数 $x_n = f(y_n)$，需求函数的反函数 $y_n = h(x_n)$，供给函数 $x_{n+1} = g(y_n)$，均衡点 $(x_0, y_0)$ 满足 $y_0 = h(x_0)$ 和 $x_0 = g(y_0)$。
- 需求函数与供给函数为线性函数：
  - $y_n - y_0 = -\alpha(x_n - x_0), x_{n+1} - x_0 = \beta(y_n - y_0)$
  - $\alpha$ 为商品需求量减少一个单位时价格的上涨量，$\frac{1}{\alpha}$ 为商品价格上涨一个单位时需求量的减少量。
  - $\beta$ 为商品价格上涨一个单位时（下一周期）供给量的增加量。
  - 递推关系 $x_{n+1} - x_0 = -\alpha\beta(x_n - x_0)$
  - $x_n - x_0 = (-\alpha\beta)^{n-1}(x_1 - x_0)$
  - 数列 $\{x_n\}$ 收敛的充要条件为 $\alpha\beta < 1$

若需求函数 $h$ 或供给函数 $g$ 不为线性函数，可在均衡点附近用线性函数近似，即令 $\alpha = -h'(x_0)$ 与 $\beta = g'(y_0)$。

- 假设商品的供求量由前两个周期的价格决定：
  - 需求函数 $x_n = f(y_n)$，需求函数的反函数 $y_n = h(x_n)$，供给函数 $x_{n+2} = g_2(y_{n+1}, y_n)$
  - 供给函数简化为 $x_{n+2} = g\left(\frac{y_{n+1} + y_n}{2}\right)$
  - 均衡点 $(x_0, y_0)$ 满足 $y_0 = h(x_0)$ 和 $x_0 = g(y_0)$
  - 需求函数 $h$ 与简化后的供给函数 $g$ 为线性函数（或在均衡点附近用线性函数近似）
  - $y_n - y_0 = -\alpha(x_n - x_0), x_{n+2} - x_0 = \beta\left(\frac{y_{n+1} + y_n}{2} - y_0\right)$
  - 递推关系 $2(x_{n+2} - x_0) = \beta(y_{n+1} + y_n - 2y_0) = \beta(y_{n+1} - y_0 + y_n - y_0) = \beta(-\alpha(x_{n+1} - x_0) - \alpha(x_n - x_0))$
  - 令 $z_n = x_n - x_0$，$2z_{n+2} + \alpha\beta z_{n+1} + \alpha\beta z_n = 0$
  - $2x_{n+2} + \alpha\beta x_{n+1} + \alpha\beta x_n = 2(1 + \alpha\beta)x_0$
  - $\lim_{n \to \infty} x_n = x_0$ 当且仅当 $\lim_{n \to \infty} z_n = 0$
  - - 差分方程 $2z_{n+2} + \alpha\beta z_{n+1} + \alpha\beta z_n = 0$
- 特征方程 $\lambda^2 + \frac{\alpha\beta}{2}\lambda + \frac{\alpha\beta}{2} = 0$
- $\lambda_1 = \frac{-\alpha\beta + \sqrt{(\alpha\beta)^2 - 8\alpha\beta}}{4}, \lambda_2 = \frac{-\alpha\beta - \sqrt{(\alpha\beta)^2 - 8\alpha\beta}}{4}$
- 当 $\alpha\beta \geq 8$ 时，$\lambda_1, \lambda_2 \in \mathbb{R}, \lambda_2 = \frac{-\alpha\beta - \sqrt{(\alpha\beta)^2 - 8\alpha\beta}}{4} \leq \frac{-\alpha\beta}{4} < -1$
- 当 $0 < \alpha\beta < 8$ 时，$\lambda_{1,2} = \frac{-\alpha\beta \pm (\sqrt{8\alpha\beta - (\alpha\beta)^2})i}{4}$
- $|\lambda_{1,2}| = \frac{\sqrt{(-\alpha\beta)^2 + (\sqrt{8\alpha\beta - (\alpha\beta)^2})^2}}{4} = \frac{\sqrt{8\alpha\beta}}{4}$
- 当且仅当 $0 < \alpha\beta < 2$ 时，价格体系是稳定均衡。与供给量由前一个周期的价格决定相比，价格体系是稳定均衡的条件有所放宽。
  :::

## 种群增长

个体individual -> 种群population -> 群落community -> 生态系统 ecosystem

:::note[种群模型]

离散单种种群模型

$x_n$为$n$代个体数量，$x_{n+1}=f(x_n)$

指数增长就是$x_{n+1}=rx_n$

Logistic模型：$x_{n+1}=x_n+rx_n\left(1-\frac{x_n}{K}\right)$

- 内禀增长率 innate rate of increase $r\geqslant -1$
- $K$环境承载量 carrying capacity

:::

**平衡点**:$f(x^*)=x^*$称为平衡点，equilibrium point

家和厨师点和平衡点充分接近则称渐进稳定asymptotic stable

- $-1\leqslant r<0$ 0渐进稳定，$K$不稳定
- $0< r<2$ $K$渐进稳定，$0$​不稳定
- $r>2$ $0,K$不稳定

**周期点**

$f_k(x^*)=x^*$的点称为 k-periodic point

差分方程的k周期点的监禁稳定性可以瘦改版的差分方程的平衡点的渐进稳定性决定

![image-20241215170639258](/pic/model/logistic2.png)

## 混沌原理

任意$n$可以唯一表示为$n=2^s(2p+1),(s,p\in \mathbb N)$，称为S型排序

**Sharkovsky定理** 若实轴上区间到自身的连续函数$f$有$k$周期点，在正整数S型排序中，$k$先于$m$,则$f$有$m$​周期点

具体排序：

3,5,7,9,...

2\*3,2\*5,...

$2^2\times 3,2^2\times 5$...

$2^n\cdots 2^1,1$

# 15 博弈论

博弈论研究由一些带有**相互竞争性质**的主体所构成的体系的理论。它能以数字表示人的行为或为人的行为建立模式，研究对抗局势中**最优的对抗策略和稳定局势**，以及如何追求各方的最优策略和决定对策的结果，协助人们在一定规则范围内寻求**最合理的行为方式**

相较优化最大的差异在于主体的个数

## 基础

### 要素

- 参与度
- 策略
- 策略组合 strategy profile
- 收益 payoff
  - 费用 cost

### 分类

- 合作博弈：可以结盟协调策略
- 静态博弈：所有人静态一次性给出策略
- 完全信息：参与者掌握其他参与者的可选策略
- 完美信息：参与者掌握其他参与者的策略选择

## 经典实例

### 囚徒困境 **Prisoner's Dilemma**

|              | **乙认罪**       | **乙不认罪**     |
| ------------ | ---------------- | ---------------- |
| **甲认罪**   | 甲6个月，乙6个月 | 甲1个月，乙9个月 |
| **甲不认罪** | 甲9个月，乙1个月 | 甲2个月，乙2个月 |

### Nash 均衡(equilibrium)

（完全信息静态）博弈的某个局势，每一个理性的参与者都不会单独偏离它,对每一个参与者，在其他参与者策略不变情况下，单独采取其他策略，收益不会增加

- **纯策略（pure strategy）**：参与者每次行动都选择某个确定的策略
- **混合策略（mixed strategy）**：参与者可以以一定的概率分布选择若干个不同的策略

:::note[Nash定理]

若参与者有限，每位参与者的策略集均有限，收益函数均为实值函数，则博弈必存在混合策略意义下的 Nash 均衡

:::

- 公交车上设有宽体单人座，可同时坐下两人但空间较普通双人座狭窄。
- 乘车舒适度以单人就坐最佳，与人合坐次之，站立最差。
- 两人上车后发现车厢中只余这一个座位，他们各自考虑就坐还是站立。

若每人均为自身考虑，自身舒适度愈大愈好。试求其Nash均衡

|      | 坐         | 站     |
| ---- | ---------- | ------ |
| 坐   | **(2、2)** | (3、1) |
| 站   | (1、3)     | (1、1) |

若每人均为对方考虑，对方舒适度愈大愈好，且当对方站立时，宁愿陪同站立而不独坐。试求其Nash均衡

|      | 坐         | 站     |
| ---- | ---------- | ------ |
| 坐   | **(3、3)** | (1、4) |
| 站   | (4、1)     | (2、2) |

## 矩阵博弈

矩阵 $A = [a_{ij}]_{m \times n}$ 称为博弈的收益矩阵

- 零和：甲的收益为 $a_{ij}$，乙的收益为 $-a_{ij}$

### 极小极大原理

若甲选择策略 $X_i$，不论乙如何选择，其收益至少为 $\min_{1 \leq j \leq n} a_{ij}$

甲的最佳策略是 $\max_{1 \leq i \leq m} \min_{1 \leq j \leq n} a_{ij}$ （每行最小值的最大值）

乙的最佳策略是 $\min_{1 \leq j \leq n} \max_{1 \leq i \leq m} a_{ij}$ （每列最大值的最小值）

可以证明 $\max_{1 \leq i \leq m} \min_{1 \leq j \leq n} a_{ij} \leq \min_{1 \leq j \leq n} \max_{1 \leq i \leq m} a_{ij}$

### 矩阵博弈的鞍点

如果 $\max_{1 \leq i \leq m} \min_{1 \leq j \leq n} a_{ij} = \min_{1 \leq j \leq n} \max_{1 \leq i \leq m} a_{ij}$，其为鞍点（saddle point）

若鞍点不存在，则博弈不存在纯策略 Nash 均衡

### 混合策略与期望收益

- 甲以概率 $x$ 选择策略 $X_i, i = 1, \ldots, m$，其中 $x \geq 0$，且 $\sum_{i=1}^m x_i = 1$
- 该混合策略也可用 $m$ 维列向量 $x = (x_1, x_2, \ldots, x_m)^T$ 表示
- 类似地，乙的混合策略也可用 $n$ 维列向量 $y = (y_1, y_2, \ldots, y_n)^T$ 表示
- 甲、乙的混合策略集分别为 $X = \{ (x_1, x_2, \ldots, x_m)^T | x_i \geq 0, \sum_{i=1}^m x_i = 1 \}$ 和 $Y = \{ (y_1, y_2, \ldots, y_n)^T | y_j \geq 0, \sum_{j=1}^n y_j = 1 \}$
- 若甲、乙采用的混合策略分别为 $x \in X, y \in Y$，甲的期望收益（expected payoff）为 $x^T A y = \sum_{i=1}^m \sum_{j=1}^n x_i a_{ij} y_j$，乙的期望收益为 $-x^T A y$

### von Neumann 极小极大定理，Minimax Theorem

设 $A = (a_{ij})_{m \times n}$，则存在 $x^* \in X, y^* \in Y$，使得 $x^{*T} A y^* = \max_{x \in X} \min_{y \in Y} x^T A y = \min_{y \in Y} \max_{x \in X} x^T A y$​

### Braess 悖论

s->u:c1(x)=x

u->t:c2(x)=1

s->v:c2(x)=1

v->t:c1(x)=x

- 新建一条从 $u$ 到 $v$ 的道路，通行时间为 0
- Nash 均衡
  - 一半车辆选择 $sut$，一半车辆选择 $svt$ 为均衡
  - 所有车辆选择 $s_{uv}$ 为均衡
- 所有车辆行驶总时间为 $\frac{1}{2}$
- 若社会费用为所有车辆行驶的时间，对任意道路通行时间函数为线性函数的网络，不存在 Nash 均衡的社会费用不超过最优社会费用的 $\frac{1}{3}$

## 最优反应函数

记参与者 $i$ 的策略集为 $A_i$，收益函数为 $u_i(a_1, a_2, \ldots, a_n)$，其中 $a_i \in A_i$，用 $a_{-i}$ 表示其他参与者的策略组合 $(a_1, \ldots, a_{i-1}, a_{i+1}, \ldots, a_n)$，收益函数简记为 $u_i(a_i, a_{-i})$。

对其他参与者的任一策略组合，参与者的最优反应函数为可使收益达到最大的策略集合，记为 $B_i(a_{-i})$，即 
$$
B_i(a_{-i}) = \{ a_i | u_i(a_i, a_{-i}) \geq u_i(a_i', a_{-i}), \forall a_i' \in A_i \}
$$。

**策略组合 $(a_1^*, a_2^*, \ldots, a_n^*)$ 为 Nash 均衡的充要条件**

- $u_i(a_i^*, a_{-i}^*) \geq u_i(a_i, a_{-i}^*), \forall a_i \in A_i$
- $a_i^* \in B_i(a_{-i}^*), i = 1, \ldots, n$

定义 $\mathcal{F}(a) = (B_1(a_1), B_2(a_2), \ldots, B_n(a_n))$

则充要条件可写为 $a^* \in \mathcal{F}(a^*)$

如果只有一个的话，那就是 $a^* = B(a^*)$​，我们可以由此想到不动点定理

:::note[不动点定理]

数 $f$ 在 $C$ 上连续，则存在 $x^* \in C$，使得 $f(x^*) = x^*$​ (Kakutani)

:::

设 $C \subseteq \mathbb{R}^n$ 是一个非空有界闭凸集，$F: C \rightarrow P_0(C)$ 满足对任意 $x \in C$，$F(x)$ 是 $C$ 中的非空闭凸集，且 $F$ 在 $C$ 上上半连续，则存在 $x^* \in C$，使得 $x^* \in F(x^*)$。

## 讨价还价



# 思考题集合

这里我们专门开一篇
