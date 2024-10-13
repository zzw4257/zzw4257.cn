---
title: ZJU ADS 速通 all in one
published: 2024-10-08
description: 写一个集成度高一点的省流笔记～
tags: [note,ads,CS]
category: CS
draft: false
---

# 课程相关

## Grading

:::tip[成绩组成]

- HW 10%
- discussions 10%
- Research Project + Peer Review 30% 8个项目，每个两组做
- MidTerm 10%*

:::

------

（总共60，QA可能有分）

Final Exam 40%（要求大于等于40/100卷面分）

主要分为两个部分：

- 高级数据结构

  主要包括 AVL 树、Splay 树、红黑树、B+ 树、倒排索引、左式堆、斜堆和二项堆等。

- 算法分析

  主要包括摊还分析、回溯、分治、动态规划、贪心、NP 问题、近似算法、局部搜索、随机算法、并行算法和外部排序等。

Project 20 report 6 presentation 10~15min

GD=助教和同学成绩平均值



# 平衡树专题

## BST

:::important

本题中默认树内不存在相同键值的节点

:::

每个节点至多两个子节点，左子节点的键值小于根节点键值，右子节点的键值大于根节点键值。

对于不同操作的复杂度如下

- Insert:$\mathcal O(h(\mathcal T))$
- Modify & Find:$\mathcal O(h(\mathcal T))$
- Delete:$\mathcal O(h(\mathcal T))$

:::note

随机情况下，$\mathcal O(h(\mathcal T))=\mathcal O(\log n)$​

:::tip[proof by [Entropy Increaser](https://blog.csdn.net/EI_Captain)]

由琴生不等式
$$
2^{\mathbb E[x]}\leqslant \mathbb E[2^x]
$$
因此我们可以考虑构造
$$
f_x=\mathbb E[2^{h_x}]\\
$$
考虑用层序遍历对节点重编号，在该意义下，$fa_i\in [1,i)(i\geqslant 2)$

则
$$
f_{i}=\frac{\displaystyle \sum _{j=1}^{i-1}f_j}{\frac{i-1}{2}}=\frac{2}{i-1}\sum_{j=1}^{i-1}f_j
$$
解递归式得到
$$
Sf_{n}=\frac{n(n+1)}{2}=\mathcal O(n^2)
$$
即
$$
2^{\mathbb {E}[h(\mathcal T)]}\leqslant \mathbb E[2^{h(\mathcal T)}]\leqslant \mathbb E[\sum _{x} 2^{h(x)}]=\mathcal O(n^2)
$$


我们有$\mathbb E[h(\mathcal T)]\leqslant \mathcal O(\log n)$，下界是不需要说明的

:::

:::

## AVL Tree

我们接下来以AVL Tree为首例引入通过*平衡性约束*，限制和“树高”**相关**参量，确保不同操作复杂度。

:::important[重要定义]

- $\mathrm{BF}(x)=h_L-h_R$
- $\mathcal T$ is balanced $\Leftrightarrow$ $\mathrm{BF_x}\in \{-1,0,1\}$​
- `trouble source`:(假定当前调整位置为$x$)出现失衡的$x$的一级分支
- `trouble maker`:(假定当前调整位置为$x$)出现失衡的$x$的二级分支
- 点的旋转：指根据点相对其父结点的方向决定旋转方向，具体而言通过将$x$​转到根的位置，只影响原结构的二级子边
- 点的方向：点相对父亲（假设存在）的子边方向

:::

容易发现对于$h$层的AVL,其最少结点数为
$$
f_h=F_{h+3}-1= \mathcal O(\Phi^h)
$$
则有对于$n$个节点的AVL，其最大高度为$\mathcal O(\log _\Phi n)$

增补的操作本质上共两类，单旋和双旋，这里我们采取一个非常简单的口诀

>- 从矛盾点向插入位置走两级同向，转一级分支一次
>- 从矛盾点向插入位置走两级异向，从下往上转两次

## Splay Tree

AVL的限制很紧，时刻保证左右子树的高度平衡性，我们考虑将其放松一点，将最坏复杂度变成均摊复杂度。

具体而言给出一个很tricky的方法：每次对一个点进行操作完，就Splay到根。

下面对Splay操作做解释

---

`Splay(x)`

是一个递归的过程

- $x$的父节点为根节点，则单旋$x$,zig
- $x$和父节点的方向相同，单旋父节点再单旋$x$,zigzag
- $x$和父节点的方向相异，单旋两次$x$​，zigzig

---

复杂度分析由势能分析给出，这里仅给出构造方案

设$\Phi(\mathcal T)=\sum \log S_x$

其中$S_x$表示$x$为根子树的总结点数

最后可以取 credit $\bar{c_i}=3(R(x')-R(x))+1$

## R-B Tree

:::important[重要定义]

- NIL节点：红黑树用于确保结构完备性定义的"空叶子"（下文的叶子指儿子均为NIL的节点）
- $\mathrm{bh}(x)$: $x$ 到任意一个叶子节点路径（不含父亲和NIL节点）上的黑色节点数量

- 4 requirements:

  > - root is **black**
  > - NIL is **black**
  > - **Red** must have **black** kids
  > - $\mathrm{bh}$ 存在

:::

---

接着考虑Insert后染色旋转的操作

分三个阶段考虑

- $x=fa=uc=\mathtt{\color{red} R}\Rightarrow$把父亲层和祖父层换色，直接结束
- $x=fa=\mathtt {\color{red} R},uc=\mathtt {B}\Rightarrow $至多转两次
  - 首先$x,fa$异向转成同向
  - $x,fa$​同向后，父亲红色推祖父，父亲转上去

对现在的

最后是复杂的Delete操作，这里我们假定已经找到位置并且删除，分类讨论：

- 叶子节点：直接NIL替换

- 有一个非NIL子节点，直接替换

- 两个都是非NIL子节点，直接用前驱后继替代，然后到替代的节点开始考虑

  - 消失红色节点，完全不需要管
  - 消失黑色节点，则从这个位置开始递归考虑


（下面内容我故意不放图大家可以自行思考，更能加深体会）

:::warning

下面4种情况比较抽象，要认准一个描述顺序

:::

:::note[分类讨论]

- 删$x$​，兄弟和外甥都是黑的，父亲随便
  - 父亲红，和兄弟换色
  - 父亲黑，兄弟变红，递归父亲
- 删$x$​，兄弟黑，异侧儿子红的，父亲随便
  - 兄弟染成父亲颜色，父亲，异侧儿子变为黑色，转兄弟
- 删$x$，兄弟黑，异侧儿子黑的，父亲随便
  - 交换父亲和同侧儿子颜色，转同侧儿子，变为case2
- 删$x$，兄弟红，父亲黑
  - 交换父亲和兄弟颜色，转兄弟，继续递归$x$​

:::tip

一个核心思想是黑节点上移吸收不平衡的部分

:::



## B+ Tree

B+ Tree是一种扁平化索引结构，其在连续地址优势下相对红黑树更为高效（内存，外存）

这里我们按照$2,3,4$树进行说明

每个非节点储存至多$3$个键值表示管辖叶子节点域的数值区间左端点，至多$4$个子节点。

需要考虑的是插入问题，在发生溢出现象时，我们需要进行分裂操作，具体而言我们采取二分策略。假设出现根的分裂情况则向上新开一层。

:::note

红黑树和**标准的**B+树存在同构关系

:::

## *Treap

## Inverted File Index

在没有pagerank理论前，我们考虑使用preindex技术，定期建立 term-document incidence matrix——信息关联矩阵。采取压缩计数，对每个词建立元组vector序列，信息查找过程可以转化为集合求交过程

具体而言，反转文件索引分为下面几个步骤

- word stemming
- stop filter
- access term
  - search tree
  - hash
  - 有序性 vs 低复杂度
- Deal with sparling mem
  - 内存分块/外存内用
  - lazy-style 删除

---

数据量大后，我们考虑改善index范式

- distributed index
  - Term-partitional index
  - Document-partitional index
- Dynamic indexing

- Compression,对位置序列做差分

- Threshold: 回答排序

---

评估层面上,**information** retrievals

- Precision: 接收到的里面相关的占比
- Recall： 相关的接收到的占比

---

现代索引优化技术

- Page rank
- **BERT**
- Semantic Web
- **RankBrain**
- **Latent Semantic Indexing (LSI)**
- **TF-IDF**

# 堆专题

:::important

下面的堆均指小根堆，不加修饰词时，所有关于堆的描述均指向二叉堆

:::

|    操作 `\` 数据结构[^ref4]     |                            配对堆                            |    二叉堆    |    左偏树    |        二项堆        |     斐波那契堆     |
| :-----------------------------: | :----------------------------------------------------------: | :----------: | :----------: | :------------------: | :----------------: |
|         插入（insert）          |                            $O(1)$                            | $O(\log n)$  | $O(\log n)$  |  $O(\log n)$[^ref1]  |       $O(1)$       |
|     查询最小值（find-min）      |                            $O(1)$                            |    $O(1)$    |    $O(1)$    | $O(1)$[^ref2][^ref3] |       $O(1)$       |
|    删除最小值（delete-min）     |                      $O(\log n)$[^ref3]                      | $O(\log n)$  | $O(\log n)$  |     $O(\log n)$      | $O(\log n)$[^ref3] |
|          合并 (merge)           |                            $O(1)$                            |    $O(n)$    | $O(\log n)$  |     $O(\log n)$      |       $O(1)$       |
| 减小一个元素的值 (decrease-key) | $o(\log n)$（下界 $\Omega(\log \log n)$，上界 $O(2^{2\sqrt{\log \log n}})$）[^ref3] | $O(\log n)$  | $O(\log n)$  |     $O(\log n)$      |   $O(1)$[^ref3]    |
|        是否支持可持久化         |                           $\times$                           | $\checkmark$ | $\checkmark$ |     $\checkmark$     |      $\times$      |

[^ref1]: 单次插入的复杂度为 $O(\log n)$，但有 $k$ 次连续插入时，可创建一个只包含要插入元素的二项堆，再将此堆与原先的二项堆进行合并，均摊复杂度为 $O(1)$

[^ref2]: 可以保存一个指向最小元素的指针，在执行其他操作时修改该指针，即可在 $O(1)$ 的复杂度下进行查询了

[^ref3]: 复杂度为均摊复杂度

[^ref4]: 表格来自于 [Wikipedia](https://en.wikipedia.org/wiki/Priority_queue#Summary_of_running_times)

## Binary Heaps 

我们从最基础的二叉堆开始复习

二叉堆采取堆式编号，数组，含有

- `Find_min`
- `percolate up`
- `percolate down`

三种操作

实现略去，这里需要记忆的是关于堆的合并，其本质是重建

## Leftist Heaps

:::warning

施工中，未完成

:::

:::important[重要定义]

- NPL: 空路径距离，到最近的没有两个子节点的子树内节点的距离
- 左偏树要求：
  - $\forall x\in\mathcal H,NPL(L)\geqslant NPL(R)$

:::

基于定义，我们有

- $NPL(x)=NPL(R)+1$
- $x$为根右路径长度为$r$时，结点数最少为$2^r-1$

换一句话，$n$个节点的树的根右路径长为$\mathcal O(\log n)$

我们依赖这个设计**合并**

---

先比较当前两个待合并子树的根结点的键值，选择较小（较大）的那个作为根结点，其左子树依然为左子树，右子树和另一个合并子树合并，递归

更新完后，检查左偏性质并交换

这里容易发现递归层数为两棵子树的右路径长和，因此单次合并复杂度为$\mathcal O(\log n)$

## Skew Heaps

:::important[重要定义]

- heavy/light node:$S_R\geqslant \frac{1}{2}S_x$则为重节点，反之亦然

:::

我们丢弃NPL，正如AVL舍弃平衡性判定

具体而言，我们总是在合并两棵子树后交换新根的两个子树

合理性上的话，**我们总是往原来右侧的路径上合并**，交换能够有效平衡累积

下面考虑势能分析给出均摊分析

:::note[复杂度分析]

> heavy node一旦发生合并反转一定变成light node
>
> Light node发生合并反转可以变成heavy node
>
> 假设两者互换，则一定在原先的右路径



定义势能函数
$$
\Phi(\mathcal H)=\sum _{x\in \mathcal H}[S_R\geqslant \frac{1}{2}S_x]
$$
credit
$$
\hat c_i=c_i+\Phi(\mathcal H')-\Phi(\mathcal H_1)-\Phi(\mathcal H_2)
$$
省略过程，我们可以得到
$$
\hat c_i\leqslant 2(l_1+l_2)
$$
其中$l_1,l_2$分别表示1,2堆右侧路径的轻节点数

显然$\hat c_i=\mathcal O(\log n)$

:::

## *Fibonacci heap

## *Binomial heap

## *Pairing heap

# 复杂度分析学

## 均摊分析

### 聚合分析

### 账分析

### 势分享

## 主定理

## 
