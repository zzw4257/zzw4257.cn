---
title: ZJU ADS Algorithm Part
published: 2024-10-22
description: 这是灰烬中的余生～
tags: [note,ads,CS]
category: CS
draft: false

---

# *课程框架树

- Advanced DS 
  - Search 
    - AVL
    - RB
    - B+
    - [App]Inverted file index
  - heap
    - Leftist
    - Skew
    - Binomial
    - Fibonacci
    - Paring
- Algorithm
  - Design Technique
    - Basic
      - **Greedy**
      - **DP**
      - Devide and Conquer
      - Backtracking
    - Opti.
      - Approximation
      - Local search
    - misc
      - Randomized
      - *Parallel
      - **External Sorting**
  - Analysis Technique
    - PC vs NPC
    - Amortized Analysis

## Backtracking

:::note[补充定义]

- $S_i$为$i$​步的可选域
- game tree 又叫决策树

:::

:::tip[例一:八皇后]
$$
S_i\{1\cdots 8\}\\
x_i\neq x_j(i\neq j)\\
\left|\frac{(x_i-x_j)}{(i-j)}\right|\neq 1(i\neq j)
$$

```
Solution 1:
Q . . . . . . .
. . . . . . Q .
. . . . Q . . .
. . . . . . . Q
. Q . . . . . .
. . . Q . . . .
. . . . . Q . .
. . Q . . . . .

Solution 2:
Q . . . . . . .
. . . . . . Q .
. . . Q . . . .
. . . . . Q . .
. . . . . . . Q
. Q . . . . . .
. . . . Q . . .
. . Q . . . . .

Solution 3:
Q . . . . . . .
. . . . . Q . .
. . . . . . . Q
. . Q . . . . .
. . . . . . Q .
. . . Q . . . .
. Q . . . . . .
. . . . Q . . .

Solution 4:
Q . . . . . . .
. . . . Q . . .
. . . . . . . Q
. . . . . Q . .
. . Q . . . . .
. . . . . . Q .
. Q . . . . . .
. . . Q . . . .
(...)
```

:::

另外一个例子的**阶段**设计则没有那么显然

:::note[eg2. Turnpike Reconstruction]
$$
S_1=[1,n]
\\S_{i-1} =S_i-\{l_i\}\vee S_{i-1}=S_i-\{r_i\}\\
$$
每个阶段的决策并不好用变量来写

具体而言我们考虑用递归的方式定义这个过程

$\mathrm{Reconstruction}(X,D,N,l,r)$

表示我们已经将$[1,l-1],[r+1,N]$之间产生的距离全部从$D$中取出，你需要安排$X[l\to r]$的位置，**能否**产生可行解的过程

后续递归显然，剪枝即为，我们在选左和选右缩减时需要提前检查是否出现了未知的距离

:::

### Alpha-Beta prunhnnn  ing

- **Minmax Strategy**:以tic-tac-toe为例，A与B分别持有最大化/，最小化某一收益的前提目标，则我们可以对game tree奇偶分层分别实现最值

- **Alpha-Beta punning**:基于该想法卡上下界（开始进入有奇偶两种），可以在实践中缩减规模到$\mathcal O(\sqrt N)$的效率($N$表示搜索树整体节点数)

