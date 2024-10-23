---
title: ZJU ADS DS Part
published: 2024-10-08
description: 写一个集成度高一点的省流笔记～
tags: [note,ads,CS]
category: CS
draft: false
---
# 课程相关

:::important[课程信息]

- `名字` ：[浙江大学 21120491]高级数据结构与算法分析
- `老师` ：卜佳俊

:::

> *其实fds和ads真的可以合成一门课的…*

## Grading

:::tip[成绩组成]

- HW 10%
- discussions 10%
- Research Project + Peer Review 30% 8个项目，每个两组做
- MidTerm 10%*

:::

---

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

随机情况下，$\mathcal O(h(\mathcal T))=\mathcal O(\log n)$

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
- $\mathcal T$ is balanced $\Leftrightarrow$ $\mathrm{BF_x}\in \{-1,0,1\}$
- `trouble source`:(假定当前调整位置为$x$)出现失衡的$x$的一级分支
- `trouble maker`:(假定当前调整位置为$x$)出现失衡的$x$的二级分支
- 点的旋转：指根据点相对其父结点的方向决定旋转方向，具体而言通过将$x$转到根的位置，只影响原结构的二级子边
- 点的方向：点相对父亲（假设存在）的子边方向

:::

容易发现对于$h$层的AVL,其最少结点数为

$$
f_h=F_{h+3}-1= \mathcal O(\Phi^h)
$$

则有对于$n$个节点的AVL，其最大高度为$\mathcal O(\log _\Phi n)$

增补的操作本质上共两类，单旋和双旋，这里我们采取一个非常简单的口诀

> - 从矛盾点向插入位置走两级同向，转一级分支一次
> - 从矛盾点向插入位置走两级异向，从下往上转两次

## Splay Tree

AVL的限制很紧，时刻保证左右子树的高度平衡性，我们考虑将其放松一点，将最坏复杂度变成均摊复杂度。

具体而言给出一个很tricky的方法：每次对一个点进行操作完，就Splay到根。

下面对Splay操作做解释

---

`Splay(x)`

是一个递归的过程

- $x$的父节点为根节点，则单旋$x$,zig
- $x$和父节点的方向相同，单旋父节点再单旋$x$,zigzag
- $x$和父节点的方向相异，单旋两次$x$，zigzig

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
  >

:::

---

接着考虑Insert后染色旋转的操作

分三个阶段考虑

- $x=fa=uc=\mathtt{\color{red} R}\Rightarrow$把父亲层和祖父层换色，直接结束
- $x=fa=\mathtt {\color{red} R},uc=\mathtt {B}\Rightarrow $至多转两次
  - 首先$x,fa$异向转成同向
  - $x,fa$同向后，父亲红色推祖父，父亲转上去

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

- 删$x$，兄弟和外甥都是黑的，父亲随便
  - 父亲红，和兄弟换色
  - 父亲黑，兄弟变红，递归父亲
- 删$x$，兄弟黑，异侧儿子红的，父亲随便
  - 兄弟染成父亲颜色，父亲，异侧儿子变为黑色，转兄弟
- 删$x$，兄弟黑，异侧儿子黑的，父亲随便
  - 交换父亲和同侧儿子颜色，转同侧儿子，变为case2
- 删$x$，兄弟红，父亲黑
  - 交换父亲和兄弟颜色，转兄弟，继续递归$x$

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

|   操作 `\` 数据结构[^ref4]   |                                          配对堆                                          |     二叉堆     |     左偏树     |        二项堆        |      斐波那契堆      |
| :-----------------------------: | :---------------------------------------------------------------------------------------: | :------------: | :------------: | :------------------: | :------------------: |
|         插入（insert）         |                                         $O(1)$                                         | $O(\log n)$ | $O(\log n)$ | $O(\log n)$[^ref1] |       $O(1)$       |
|     查询最小值（find-min）     |                                         $O(1)$                                         |    $O(1)$    |    $O(1)$    |   $O(1)$[^ref3]   |       $O(1)$       |
|    删除最小值（delete-min）    |                                   $O(\log n)$[^ref3]                                   | $O(\log n)$ | $O(\log n)$ |    $O(\log n)$    | $O(\log n)$[^ref3] |
|          合并 (merge)          |                                         $O(1)$                                         |    $O(n)$    | $O(\log n)$ |    $O(\log n)$    |       $O(1)$       |
| 减小一个元素的值 (decrease-key) | $o(\log n)$（下界 $\Omega(\log \log n)$，上界 $O(2^{2\sqrt{\log \log n}})$）[^ref3] | $O(\log n)$ | $O(\log n)$ |    $O(\log n)$    |   $O(1)$[^ref3]   |
|        是否支持可持久化        |                                        $\times$                                        | $\checkmark$ | $\checkmark$ |    $\checkmark$    |      $\times$      |

|                                                                                                 Operation                                                                                                 | find-min |      delete-min      |                                             decrease-key                                             |        insert        |                                              meld                                              |   make-heap[[a\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-14)   |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------: | :------------------: | :---------------------------------------------------------------------------------------------------: | :------------------: | :--------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------: |
|                                           [Binary](https://en.wikipedia.org/wiki/Binary_heap)[[10\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-CLRS-10)                                           | *Θ*(1) |  *Θ*(log *n*)  |                                           *Θ*(log *n*)                                           |  *Θ*(log *n*)  |                                         *Θ*(*n*)                                         |                                *Θ*(*n*)                                |
|                                      [Skew](https://en.wikipedia.org/wiki/Skew_heap)[[11\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-sleator-tarjan-skew-11)                                      | *Θ*(1) | *O*(log *n*) am. |                                         *O*(log *n*) am.                                         | *O*(log *n*) am. |                                      *O*(log *n*) am.                                      |                              *Θ*(*n*) am.                              |
|                                     [Leftist](https://en.wikipedia.org/wiki/Leftist_tree)[[12\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-tarjan-leftist-12)                                     | *Θ*(1) |  *Θ*(log *n*)  |                                           *Θ*(log *n*)                                           |  *Θ*(log *n*)  |                                       *Θ*(log *n*)                                       |                                *Θ*(*n*)                                |
|          [Binomial](https://en.wikipedia.org/wiki/Binomial_heap)[[10\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-CLRS-10)[[14\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-15)          | *Θ*(1) |  *Θ*(log *n*)  |                                           *Θ*(log *n*)                                           |    *Θ*(1) am.    | *Θ*(log *n*)[[b\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-bootstrap-meld-16) |                                *Θ*(*n*)                                |
|                               [Skew binomial](https://en.wikipedia.org/wiki/Skew_binomial_heap)[[15\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-brodal-okasaki-17)                               | *Θ*(1) |  *Θ*(log *n*)  |                                           *Θ*(log *n*)                                           |      *Θ*(1)      | *Θ*(log *n*)[[b\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-bootstrap-meld-16) |                                *Θ*(*n*)                                |
|                                             [2–3 heap](https://en.wikipedia.org/wiki/2–3_heap)[[17\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-19)                                             | *Θ*(1) | *O*(log *n*) am. |                                               *Θ*(1)                                               |    *Θ*(1) am.    | *O*(log *n*)[[b\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-bootstrap-meld-16) |                                *Θ*(*n*)                                |
|                                 [Bottom-up skew](https://en.wikipedia.org/wiki/Skew_heap)[[11\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-sleator-tarjan-skew-11)                                 | *Θ*(1) | *O*(log *n*) am. |                                         *O*(log *n*) am.                                         |    *Θ*(1) am.    |                                         *Θ*(1) am.                                         |                              *Θ*(*n*) am.                              |
|                                         [Pairing](https://en.wikipedia.org/wiki/Pairing_heap)[[18\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-Iacono-20)                                         | *Θ*(1) | *O*(log *n*) am. | *o*(log *n*) am.[[c\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-pairingdecreasekey-23) |      *Θ*(1)      |                                           *Θ*(1)                                           |                                *Θ*(*n*)                                |
|                      [Rank-pairing](https://en.wikipedia.org/w/index.php?title=Rank-pairing_heap&action=edit&redlink=1)[[21\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-24)                      | *Θ*(1) | *O*(log *n*) am. |                                             *Θ*(1) am.                                             |      *Θ*(1)      |                                           *Θ*(1)                                           |                                *Θ*(*n*)                                |
|                       Fibonacci[[10\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-CLRS-10)[[2\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-Fredman_And_Tarjan-2)                       | *Θ*(1) | *O*(log *n*) am. |                                             *Θ*(1) am.                                             |      *Θ*(1)      |                                           *Θ*(1)                                           |                                *Θ*(*n*)                                |
| [Strict Fibonacci](https://en.wikipedia.org/wiki/Strict_Fibonacci_heap)[[22\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-25)[[d\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-optimum-26) | *Θ*(1) |  *Θ*(log *n*)  |                                               *Θ*(1)                                               |      *Θ*(1)      |                                           *Θ*(1)                                           |                                *Θ*(*n*)                                |
|          [Brodal](https://en.wikipedia.org/wiki/Brodal_queue)[[23\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-27)[[d\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-optimum-26)          | *Θ*(1) |  *Θ*(log *n*)  |                                               *Θ*(1)                                               |      *Θ*(1)      |                                           *Θ*(1)                                           | *Θ*(*n*)[[24\]](https://en.wikipedia.org/wiki/Fibonacci_heap#cite_note-28) |

a.m表示均摊

## Binary Heaps

我们从最基础的二叉堆开始复习

二叉堆采取堆式编号，数组，含有

- `Find_min`
- `percolate up`
- `percolate down`

三种操作

实现略去，这里需要记忆的是关于堆的合并，其本质是重建

## Leftist Heaps

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

:::caution

这里提到的斜堆的合并定义为，在一边为空时必须对非空的一侧的右路径进行交换，**ADS考试中采取的是这种定义而非标准定义**，两者复杂性是等价的，但是证明方式构造不同。

:::

:::important[重要定义]

- heavy/light node:$S_R\geqslant \frac{1}{2}S_x$则为重节点，反之亦然

:::

我们丢弃NPL，正如AVL舍弃平衡性判定

具体而言，我们总是在合并两棵子树后交换新根的两个子树

合理性上的话，**我们总是往原来右侧的路径上合并**，交换能够有效平衡累积

下面考虑势能分析给出均摊分析

在给出构造前，我们先考虑定性刻画合并的结果

:::

每棵树到全局最大值前的路径全会交换

依赖这个，我们能给出斜堆合并结果的迭代性质刻画

- 合并后堆的右路径为两个堆右路径的排序
- 所有左子树为原有左子树
- 最后右路径上左右子树交换

:::note[复杂度分析]

> heavy node一旦发生合并反转一定变成light node
>
> Light node发生合并反转可以变成heavy node
>
> 假设两者互换，则一定在原先的右路径（只有右路径上的点的才会发生子树改变）

设$l_1,l_2,h_1,h_2$分别表示1,2堆右侧路径的轻/重节点数

我们思考的起点是

- $c_i\leqslant l_1+h_1+l_2+h_2$即右路径长度和
- 依赖定义，对于重节点总数的改变$\Delta \Phi \leqslant l_1+l_2-h_1-h_2$

定义势能函数

$$
\Phi(\mathcal H)=\sum _{x\in \mathcal H}[S_R\geqslant \frac{1}{2}S_x]
$$

credit

$$
\hat c_i=c_i+\Phi(\mathcal H')-\Phi(\mathcal H_1)-\Phi(\mathcal H_2)=c_i+\Delta \Phi
$$

我们可以得到

$$
\hat c_i\leqslant 2(l_1+l_2)
$$

我们证明$l_i=\mathcal O(\log n)$即可，这是归纳显然的

显然$\hat c_i=\mathcal O(\log n)$

:::

## Binomial heap/queue

这里我们开始思考 **堆-优先队列** 的意义，堆从目的上和搜索树有本质差异，其核心维护优先级的特性可以实现

我们讨论树型结构的堆，森林结构的堆，锻炼摊还分析

- 对顶堆维护$k$小
- ...

:::note[补充定义]

- 二项树是一个递归定义的树序列
  - $B_0$为单点
  - $B_i$为$B_{i-1}$添加在$B_{i-1}$根的子树序列开头的结果
  - $B_k$的$d$层有$\binom{k}{d}$个节点
- $N$的二进制拆解:$d_1,d_2\cdots,d_{\pi_N}:N=\sum _{i=1}^{\pi_N}2^i$

:::

---

给出合并操作

下面我们用$C_{11}=\mathtt{1011}$表示分解，表示森林形态为$\{B_3,B_1,B_0\}$

那么我们对两个二项队列的合并过程本质上是在做二进制加法

换一句话，我们实际上只解决相等大小的二项树

即合并操作可以被形式化表示成$\mathrm{Merge}_{k\in \Sigma}(B_{k1},B_{k2})$

由于$|\Sigma|=\mathcal O(\log n)$

---

删除操作/弹堆首是朴素的，你找到出现问题的堆拆开，在按序合并即可

显然复杂度是$\mathcal O(\log n)$

---

显然我们可以说明Insert的单次复杂度是$\mathcal O(\log n)$的，下面补充证明其均摊复杂度为$\mathcal O(1)$

:::tip[proof 1 聚合分析]

容易发现每次合并的具体贡献是可以算出来的

具体而言

$c_i=\mathrm{pop\_count}(i\oplus i-1)-1$

则

$$
\sum _{i=1}^n c_i\leqslant \sum _{i=1}^n\mathrm{pop\_count}(i\oplus i-1)-1\leqslant \sum_{i=1}^{n} \mathrm{suffix(i)+1}\\(2^k>n)\leqslant n+\sum _{i=1}^{2^k-1}\mathrm{suffix(i)}\\\leqslant n+ \sum _{i=1}^k i 2^{(k-i)}\leqslant n+2^k\sum _{i=1}^k\frac{i}{2^{i}}\leqslant n+2^k\leqslant 3n
$$

:::

当然上述放缩并没有意义，这里纯属习惯动作

后面的不等式可以参考建堆

:::tip[proof 2 势能分析]

$$
c_i=\mathrm{pop\_count}(i\oplus i-1)-1
$$

定义$\Phi(i)=\mathrm{pop\_count(i)}$

则$\hat c_i=c_{i}+\Phi(i)-\Phi(i-1)=2$

后面没必要说了

这里也可以由$\Delta\Phi(i)$的实际意义出发，就是1的后缀

:::

::: tip[proof 3 账分析]

这个反而更加有点tricky

你考虑成每个人给两块钱，出现就扣钱，合并确保根能给你就行

:::

---

复杂度分析上，有一个有争议的，Find_min到底当成$\mathcal O(1)$还是$\mathcal O(\log n)$的

## Fibonacci heap

:::important

本节内容参考自《Introduction to Algorithms(Third Edition)》Chap19

:::

:::note[可合并堆的性质重申]

$$
\begin{array}{|ccc|}\hline\text{操作(最坏情形)(摊近)}&\text{二项堆}&\text{斐波那契堆}\\\hline\text{MAKE-HEAP}&\Theta(1)&\Theta(1)\\\text{INSERT}&\Theta(\lg n)&\Theta(1)\\\text{MNMUM}&\Theta(1)&\Theta(1)\\\text{EXTRACT-MIN}&\Theta(\lg n)&O(\lg n)\\\text{UNION}&\Theta(n)&\Theta(1)\\\text{DECREASE-KEY}&\Theta(\lg n)&\Theta(1)\\\text{DELETE}&\Theta(\lg n)&O(\lg n)\\\hline\end{array}
$$

:::

容易发现二项堆在UNION或者说Merge上表现很差，我们基于这些问题给出一个更优秀的队列实现——斐波纳契堆/队列

---

:::note[定义]

- 斐波纳契堆是一个最小堆序的有根多叉树集合
  - 根被环形双向链表串起来
  - 每个点具有 `child,left,right,parent,degree,mark`属性，表示孩子列表，左右兄弟和父节点以及度数;
  - 注意根与根(root list)，儿子与儿子，兄弟与兄弟，child list的指向是随机的
  - $x.mark$代表$x$的**在成为别人的孩子后**，是否失去国孩子，新产生时为0，成为另一个节点孩子后清零。
  - 我们通过$H.min$访问斐波纳契堆，指向最小根，注意这里不做平行区分($H.n$表示数目)
- 斐波纳契对用到的势函数$\Phi(\mathcal H)=t(\mathcal H)+2m(\mathcal H)$
  - $t(\mathcal H)$表示跟链表大小
  - $m(\mathcal H)$表示标记节点数

:::

下面我们对于每个操作按照实现规范->势能变化的顺序介绍

### Init

$H.n=0,H.min=\mathrm{NIL},\Phi(\mathcal H)=0$

摊还代价就是实际代价 $\mathcal O(1)$

### Insert

直接生成全空的单节点插到根列表中，然后更新最小堆

$$
\begin{aligned}
&\mathrm{FIB\_HEAP\_INSERT}(H, x) \\
1.\ & x.\text{degree} = 0 \\
2.\ & x.\text{p} = \mathrm{NIL} \\
3.\ & x.\text{child} = \mathrm{NIL} \\
4.\ & x.\text{mark} = \mathrm{FALSE} \\
5.\ & \text{if } H.\text{min} == \mathrm{NIL} \\
6.\ & \quad \text{create a root list for } H \text{ containing just } x \\
7.\ & \quad H.\text{min} = x \\
8.\ & \text{else insert } x \text{ into } H\text{'s root list} \\
9.\ & \quad \text{if } x.\text{key} < H.\text{min}.\text{key} \\
10.\ & \quad \quad H.\text{min} = x \\
11.\ & H.\text{n} = H.\text{n} + 1
\end{aligned}
$$

$$
\Delta \Phi=((t(\mathcal H)+1)+2m(\mathcal H))-((t(\mathcal H))+2m(\mathcal H))=1
$$

$\hat c=\mathcal O(1)+1=\mathcal O(1)$

### Findmin

$\mathcal O(1)$

### Merge/UNION

简单的链接根链表，去诶的那个新的最小节点

$$
\begin{aligned}
&\mathbf{FIB\_HEAP\_UNION}(H_1, H_2) \\
1.\ & H = \text{MAKE-FIB-HEAP()} \\
2.\ & H.\text{min} = H_1.\text{min} \\
3.\ & \text{concatenate the root list of } H_2 \\&\text{ with the root list of } H \\
4.\ & \text{if } (H_1.\text{min} = \text{NIL}) \text{ or } \\&(H_2.\text{min} \neq \text{NIL} \text{ and } H_2.\text{min}.\text{key} < H_1.\text{min}.\text{key}) \\
5.\ & \quad H.\text{min} = H_2.\text{min} \\
6.\ & H.\text{n} = H_1.\text{n} + H_2.\text{n} \\
7.\ & \text{return } H
\end{aligned}
$$

$$
\Delta \Phi=0\Rightarrow \hat c=\mathcal O(1)
$$

### EXTRACT_MIN

$$
\begin{aligned}
&\mathbf{FIB\_HEAP\_EXTRACT\_MIN}(H) \\
1.\ & z = H.\text{min} \\
2.\ & \text{if } z \neq \text{NIL} \\
3.\ & \quad \text{for each child } x \text{ of } z \\
4.\ & \quad \quad \text{add } x \text{ to the root list of } H \\
5.\ & \quad \quad x.\text{p} = \text{NIL} \\
6.\ & \quad \text{remove } z \text{ from the root list of } H \\
7.\ & \quad \text{if } z = z.\text{right} \\
8.\ & \quad \quad H.\text{min} = \text{NIL} \\
9.\ & \quad \text{else } H.\text{min} = z.\text{right} \\
10.\ & \quad\quad\text{CONSOLIDATE}(H) \\
11.\ & \quad H.\text{n} = H.\text{n} - 1 \\
12.\ & \text{return } z
\end{aligned}
$$

首先把最小根的孩子全部挂上去，然后我们现在随便把H.min指向**原来的根**，进入**CONSOLIDATE**过程

### CONSOLIDATING 合并

一言一蔽之

找到相同度数的$x,y$，然后$y$连接到$x$,清除$y$上标记$A$是辅助数组，用来索引根节点度数的变化

具体实现上，我们先找一个根$x=w$，然后对于其$d$，我们找$A[d]=y$，然后合并$x'\leftarrow (y\to x)$，现在度数加一，问题迭代下去

处理完之后，我们可以基于A来更新$\mathcal H$

$$
\begin{aligned}
&\mathbf{CONSOLIDATE}(H) \\
1.\ & \text{let } A[0 \dots D(H.\text{n})] \text{ be a new array} \\
2.\ & \text{for } i = 0 \text{ to } D(H.\text{n}) \\
3.\ & \quad A[i] = \mathbf{NIL} \\
4.\ & \text{for each node } w \text{ in the root list of } H \\
5.\ & \quad x = w \\
6.\ & \quad d = x.\text{degree} \\
7.\ & \quad \text{while } A[d] \neq \mathbf{NIL} \\
8.\ & \quad \quad y = A[d] \quad / \text{another node with the same degree as } x \\
9.\ & \quad \quad \mathbf{if } x.\text{key} > y.\text{key} \\
10.\ & \quad \quad \quad \text{exchange } x \text{ with } y \\
11.\ & \quad \quad \text{FIB-HEAP-LINK}(H, y, x) \\
12.\ & \quad \quad A[d] = \mathbf{NIL} \\
13.\ & \quad \quad d = d + 1 \\
14.\ & \quad A[d] = x \\
15.\ & H.\text{min} = \mathbf{NIL} \\
16.\ & \text{for } i = 0 \text{ to } D(H.\text{n}) \\
17.\ & \quad \mathbf{if } A[i] \neq \mathbf{NIL} \\
18.\ & \quad \quad \mathbf{if } H.\text{min} = \mathbf{NIL} \\
19.\ & \quad \quad \quad \text{create a root list for } H \text{ containing just } A[i] \\
20.\ & \quad \quad \quad H.\text{min} = A[i] \\
21.\ & \quad \mathbf{else } \text{insert } A[i] \text{ into } H\text{'s root list} \\
22.\ & \quad \mathbf{if } A[i].\text{key} < H.\text{min}.\text{key} \\
23.\ & \quad \quad H.\text{min} = A[i] \\
\end{aligned}
$$

用到的连接过程

$$
\begin{aligned}
&\text{FIB-HEAP-LINK}(H, y, x) \\
1.\ & \text{remove } y \text{ from the root list of } H \\
2.\ & \text{make } y \text{ a child of } x, \text{ incrementing } x.\text{degree} \\
3.\ & y.\text{mark} = \text{FALSE}
\end{aligned}
$$

这一部分的复杂度分析最为复杂，首先引入引理

:::tip[Lemma 1: sup of max_degree]

设$D(n)$表示$n$个节点斐波纳契堆任意节点的度数上界

则$D(n)=\mathcal O(\ln n)$

:::

现在返回来考虑摊还代价，注意这里没有点被标记

$$
\Delta \Phi \leqslant ((D(n)+1)+2m(\mathcal H))-(t(\mathcal H)+2m(\mathcal H))\\
c_i=\mathcal O(D(n)+t(\mathcal H))
$$

这里解释一下基础操作数

循环本身一定不会多于最终分裂出来的根数

$\hat c_i=\mathcal O(D(n))=\mathcal O(\log n)$

### DECREASE-KEY

简单来说，我们将节点剪切，并考虑**级联切断**过程

:::note[补充定义]

- mark实际上表示了一个行为属性

  - 某个时刻$x$是根
  - $x$被连接到$y$上
  - $x$的两个孩子被切除

  当第3步发生是，$x$成为新的根

  当第1，2步发生，且$x$的一个孩子被切掉则$x.mark=1$
- 级联切断(cascading-cut)

  当一个被标记的节点被再次切除孩子，则其紧邻的被标记祖先链均需要被切断，这个过程是递归的

:::

$$
\begin{aligned}
&\mathbf{FIB\_HEAP\_DECREASE\_KEY}(H, x, k) \\
1.\ & \text{if } k > x.\text{key} \\
2.\ & \quad \text{error: "new key is greater than current key"} \\
3.\ & x.\text{key} = k \\
4.\ & y = x.\text{p} \\
5.\ & \mathbf{if } y \neq \text{NIL} \text{ and } x.\text{key} < y.\text{key} \\
6.\ & \quad \mathsf{CUT}(H, x, y) \\
7.\ & \quad \mathsf{CASCADING\_CUT}(H, y) \\
8.\ & \mathbf{if } x.\text{key} < H.\text{min}.\text{key} \\
9.\ & \quad H.\text{min} = x \\
\end{aligned}
$$

$$
\begin{aligned}
&\mathbf{CUT}(H, x, y) \\
1.\ & \text{remove } x \text{ from the child list of } y, \text{ decrementing } y.\text{degree} \\
2.\ & \text{add } x \text{ to the root list of } H \\
3.\ & x.\text{p} = \text{NIL} \\
4.\ & x.\text{mark} = \text{FALSE} \\
\end{aligned}
$$

$$
\begin{aligned}
&\mathsf{CASCADING\_CUT}(H, y) \\
1.\ & z = y.\text{p} \\
2.\ & \mathbf{if } z \neq \text{NIL} \\
3.\ & \quad \mathbf{if } y.\text{mark} = \mathbf{FALSE} \\
4.\ & \quad \quad y.\text{mark} = \mathbf{TRUE} \\
5.\ & \quad \mathbf{else} \ \mathsf{CUT}(H, y, z) \\
6.\ & \quad \mathsf{CASCADING\_CUT}(H, z) \\
\end{aligned}
$$

这里我们假设级连切除的次数是$c$(注意包含递归层)

$$
\Delta \Phi\leqslant ((t(\mathcal H)+c)+2(m(\mathcal H)-c+2))-(t(\mathcal H)+2m(\mathcal H)=4-c)
$$

$c_i=\mathcal O(c)$

则在考虑到势能可以随便修改单位$1$的情况下

$$
\hat c_i=\mathcal O(c)+(4-c)k=\mathcal O(1)
$$

### Delete

只需要将对应节点调整到$-\infty$，然后EXTRACT-MIN即可

摊还$\mathcal O(\log n)$无需多言

## *Pairing heap

:::warning

想不清楚，咕掉了

:::

:::note[重要定义]

- 配对堆是一个带权多叉堆
- 配对堆是纯粹的树形结构，不额外维护信息

:::

![img](/pic/phy2/pairingheap3.jpg)

合并时直接把新来的插到左边

下面随着我们

---

删除是配对堆的核心操作

直接看代码

```c++
Node* merges(Node* x) {
  if (x == nullptr || x->sibling == nullptr)
    return x;  // 如果该树为空或他没有下一个兄弟，就不需要合并了，return。
  Node* y = x->sibling;                // y 为 x 的下一个兄弟
  Node* c = y->sibling;                // c 是再下一个兄弟
  x->sibling = y->sibling = nullptr;   // 拆散
  return meld(merges(c), meld(x, y));  // 核心部分
}
```

这里 `meld(T1,T2)`是配对操作

---

Decresed key

我们得进一步重构了

# 复杂度分析学

## 均摊分析

### 聚合分析

### 账分析

### 势分享

## 主定理

[^ref1]: 单次插入的复杂度为 $O(\log n)$，但有 $k$ 次连续插入时，可创建一个只包含要插入元素的二项堆，再将此堆与原先的二项堆进行合并，均摊复杂度为 $O(1)$

[^ref2]: 可以保存一个指向最小元素的指针，在执行其他操作时修改该指针，即可在 $O(1)$ 的复杂度下进行查询了

[^ref3]: 复杂度为均摊复杂度

[^ref4]: 表格来自于 [Wikipedia](https://en.wikipedia.org/wiki/Priority_queue#Summary_of_running_times)
