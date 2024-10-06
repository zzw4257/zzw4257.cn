---
title: ACEE数学建模作业+小测提示(2024版)
published: 2024-10-06
description: "工高数学建模的一些作业提示，希望帮到后来人"
image: "./dawn.jpg"
tags: ["ACEE", "浙江大学工高班", "数学建模", "record"]
category: Guides
draft: false
---
# ACEE数学建模作业+小测提示(2024版)

考虑到很多同学这门课对于一些作业可能需要一些提示，这里我为大家提供一些视角和参考，注意内容仅供参考，请勿抄袭～

## 周期一 排序问题

简单来说，这次作业考察的是三角不等式和向量形式递推关系的表示

具体而言，对第一题我们需要理解，中位数$\mu$是整数无限制下的最优解，$\sigma'$是排列意义下对$\mu$的逼近，$\sigma^*$是排列限制下最优解，在这个意义上我们可以利用三角不等式，通过建立中间点来实现拆项

$\beta$平均数的情况是类似的，需要利用(2)来做中转。

---

第二题可能需要提示的是第四问，很容易想到向前递推，这里需要考虑清楚的是第一步的边贡献次数是多少。

除了贡献法，还有一种殊途同归的方法能够导出这个结果。

:::note[tip]

你真的能化简吗?

:::

具体过程如下(密码作业截止后就撤掉)：

<iframe
  src="/pdfjs-4.6.82-dist/web/viewer.html?file=/file/HW1(final).pdf"
  width="100%"
  height="800px"
></iframe>

## 周期一 慕课作业

### 单循环赛break下限证明

pattern互不相同，只有两种能不出break

### 砍竹子问题

:::tip

竹子最高高度存在上界，其对偶表述是总高度增加量存在下界

:::

反证法，每个时刻总量增加总是H-当前砍伐高，你总能拉上去

## 小测一 线性规划转化问题

:::tip

本题的核心是引导大家利用01变量去刻画常规的多种关系，具体而言，要习惯于用对指标枚举去表示某些特定的数值/数值集合，也就是从是多少到有没有的转化。

可以借鉴的是[这本书](https://docs.mosek.com/modeling-cookbook/mio.html)

:::note

| Boolean                   | Linear                              |
| ------------------------- | ----------------------------------- |
| $z= x\ \mathrm{OR}\ y$  | $x\leq z,\ y\leq z,\ z\leq x+y$   |
| $z= x\ \mathrm{AND}\ y$ | $x\geq z,\ y\geq z,\ z+1\geq x+y$ |
| $z= \mathrm{NOT}\ x$    | $z=1-x$                           |
| $x\implies y$           | $x\leq y$                         |

:::

> 有$n$个小区需要服务，$m$处可以开设服务，开设服务费费用为$f_i$，提供服务的费用为$c_{i,j}$，每个最小化费用
> 不相容约束，某些小区不能同时由某一个服务点提供服务，记为:$\{a_k,b_k\}(k=1,2,\cdots,s)$
> 双指派约束，每个小区有两个服务点提供服务，且某些小区对有一个公共服务点:$\{c_w,d_w\}(w=1,2,\cdots,t)$

$x_i=[i$有服务$]$

$y_{ij}=[i$有点且在$j$小区服务$]$

$z_{i,t}=[i$为$c_t,d_t$的公共点$]$

则显然可以直接写出

$$
\min \sum _{i=1}^m f_ix_i+\sum _{i=1}^m\sum _{j=1}^n c_{ij}y_{ij}
$$

$$
\begin{align}s.t. x_i\in \{0,1\},y_{ij}&\in \{0,1\},z_{i,w}\in \{0,1\}\\y_{ij}&\leqslant x_i\\\sum _{i=1}^my_{ij} &\geqslant 1(=2)\\y_{ia_k}+y_{ib_k}&\leqslant 1\\z_{iw}&\leqslant y_{i,c_w}\\z_{iw}&\leqslant y_{i,d_w}\\z_{iw}+1&\geqslant y_{ic_w}+y_{id_w}\\\sum _{i=1}^m z_{iw}&\geqslant 1&\end{align}
$$

老师给的答案如下，实际上并不优秀，因为约束数反而变多了

$$
\begin{align}s.t. x_i\in \{0,1\}&,y_{ij}\in \{0,1\}\\y_{ij}&\leqslant x_i\\\sum _{i=1}^my_{ij} &\geqslant 1(=2)\\y_{ia_k}+y_{ib_k}&\leqslant 1\\x_{i_1c_w}+x_{i_2c_w}&\geqslant x_{i_1d_w}+x_{i_2d_w}-1\\\sum _{i=1}^m z_{iw}&\geqslant 1&\end{align}
$$
