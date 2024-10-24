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

## 周期一 雪灾浙大作业

(之前写的有点谜语人，考虑改清楚点)

### T1:排序问题

:::note[标签]

keywords:`分类讨论`，`三角不等式`

:::

- 问1:略
- 问2:
  - 法一：分类讨论正偏态和负偏态情况，强行展开绝对值
  - 法二：三角不等式硬上，利用绝对值的差和差的绝对值，以及绝对值的和和和的绝对值之间的关系解题。可以找一个中转点，$A\leqslant 2B\Leftrightarrow A-B\leqslant A$
- 问3:
  - 中位数$\mu$是整数无限制下的最优解，$\sigma'$是排列意义下对$\mu$的逼近，$\sigma^*$是排列限制下最优解
  - 在这个意义上我们可以利用三角不等式，通过建立中间点来实现拆项
  - 对于$\beta$我们没有更好的性质，考虑用问2来搭桥

### T2:赛程计分问题

:::note[标签]

keywords:`递推`，`向量表示`

:::

第二题可能需要提示的是第四问，很容易想到向前递推，这里需要考虑清楚的是第一步的边贡献次数是多少。

:::warning[tip]

在给出答案前，想一想你真的能化简吗?

:::

具体过程如下：

<iframe
  src="/pdfjs-4.6.82-dist/web/viewer.html?file=/file/HW1(unlock).pdf"
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

## 周期二 慕课作业

### T1 吉祥三宝

>在杭州迎接2022年第19届亚洲运动会时，n名同学正在老师的带领下与亚运会吉祥物“江南忆”做游戏。游戏开始前，同学可以商定在游戏中采取的策略，但游戏进行过程中，同学之间不能互相交流。游戏开始时，老师在每位同学的背后贴上印有三个吉祥物“琮琮”、“宸宸”和“莲莲”之一的图案，不同同学背后的图案可以不同。每个同学不能看到自己背后的图案，但能看到除他自己外所有其他同学的图案。
>
>（1）现老师要求所有同学分站为3列。每列所有同学背后的图案均完全相同时，视为 “成功”。试给出一种策略，使成功的可能性尽可能大；
>
>（2）现老师要求每位同学同时在纸上画出自己背后的图案。一位同学所画的图案与自己背后的图案相同时视为该同学“成功”。试给出一种策略，使该策略能确保成功的同学数量尽可能多。

为了方便说明，我们将背后贴上印有三个吉祥物“琮琮”、“宸宸”和“莲莲"的图案的同学分别符号化为A，B，C

(1)

【法一】

下面我们将说明存在策略，成功的可能性为$1$

具体而言

我们设每个同学看到的A,B,C个数为$a,b,c$

则显然$a+b+c=n-1$，且具体而言，设所有同学中A,B,C个数为$a_0,b_0,c_0$

则$a=a_0-[\mathtt{self.c=A}],b=b_0-[\mathtt{self.c=B}],c=c_0-[\mathtt{self.c=C}]$​

我们构造排队方法

假设$(a-b)\mod 3\equiv 0$，其归到$1$队

假设$(a-b)\mod 3\equiv 1$，其归到$2$队

假设$(a-b)\mod 3\equiv 2$，其归到$3$​队

在这种策略下，

- 本身是$\mathtt A$​ :  $(a-b)\equiv (a_0-b_0-1)\mod 3$
- 本身是$\mathtt B$ :  $(a-b)\equiv (a_0-b_0+1)\mod 3$
- 本身是$\mathtt C$ :  $(a-b)\equiv (a_0-b_0)\mod 3$​ 

容易发现不同属性（即背后吉祥物不同）会有不同的计算结果，因此会被分到三个队列中

【法二】

首先，我们为每个人分配一个序号$i$，我们设$h_i$表示第$i$个人的颜色译码，设为
$$
h_i=\begin{cases}0&\mathtt{self_i.c=A}\\1&\mathtt{self_i.c=B}\\2&\mathtt{self_i.c=C}\end{cases}
$$
则我们将$i$分到$(\sum _{j\neq i}h_j\mod 3)+1$队列，则为一个合法的安排

证明和上面基本相同，这里不再赘述

:::tip[hint]

$-1\equiv 2\mod 3$

:::

(2)

延续(1)【法二】的定义，我们用0,1,2表示A,

设$n=3k+r(0 \leqslant m <3)$,即$k=\lfloor\frac{n}{3}\rfloor$​

考虑如下策略

- $1\leqslant i\leqslant k$，猜测图案为$-\sum \limits _{j\neq i}  h_j\pmod 3$
- $k+1\leqslant i\leqslant 2k+[r\geqslant 1]$，猜测图案为$1-\sum \limits _{j\neq i}  h_j\pmod 3$
- $2k+1+[r\geqslant 1]\leqslant i\leqslant 3k+[r\geqslant 1]+[r\geqslant 2]$，猜测图案为$2-\sum \limits _{j\neq i}  h_j\pmod 3$​

容易证明

前$k$名同学，中间$k+[r\geqslant 1]$名同学，后面$k+[r\geqslant 2]$名同学 这三组同学，至少有完整的一组选择正确（证明基于分类讨论反证即可）

因此能保证至少$k=\lfloor\frac{n}{3}\rfloor$个成功

### T2 假币识别问题

(1)

>某种硬币单枚质量为$W$克。现有$N$堆该种硬币，依次标记为$1，2,...,N$。其中可能有若干堆，每堆均是伪币。所有伪币质量均相同，且不为$W$。伪币所在堆的指标集记为$I$。为求出$I$，现用一可精确测得质量的电子秤称量两次。第一次从每堆硬币中各取1枚，称得总质量为$M_{1}$克，第二次从第i堆硬币中取$p^i$枚，i=1,2,...,N,称得总质量为$M_2$克，这里p为正整数(假设每堆硬币数量足够多)。
>(1)试给出$M_1,M_2$和W的某个函数，其值仅与I和p有关，而与伪币的质量无关；
>(2)为能用上述方法通过两次称量求出指标集I，p应满足什么条件？试给出某个满足条件的p
>值；并说明若取$\mathfrak{p}=2$,可能无法用上述方法通过两次称量求出I。

$$ M_1=(N-|I|)W+|I|W'\\M_2=W\sum _{i\notin I}p^i+W'\sum _{i\in I}p^i\\ $$

有 $$ (M_1-NW)+\frac{|I|}{\sum _{i\in I}p^i}\left(\frac{p(1-p^N)}{1-p}W-M_2\right) $$ 因此我们

可以构造函数 $$ F(M_1,M_2,W,N,p)=\frac{(M_1-NW)}{\left(M_2-\frac{p(1-p^N)}{1-p}W\right)}=\frac{|I|}{\sum _{i\in I }p^i} $$

更好理解的形式是
$$
F(M_1,M_2,W,N,p)=\frac{M_2-\left(\frac{p(1-p^N)}{1-p}W\right)}{(M_1-NW)}=\frac{\sum _{i\in I }p^i}{|I|}
$$
我们已经给出了符合要求的函数

(2)

首先我们给出能够通过两次称量求出$I$的量化条件

对于
$$
F(M_1,M_2,W,N,p)=\frac{\sum _{i\in I }p^i}{|I|}=G_p(I)
$$

> 若对给定的$p$，$\forall I_1\neq I_2,G_p(I_1)\neq G_p(I_2)$
>
> 则我们称可以还原$I$

下面取$p=N+1$（实际上$p$可以任意取$>N$的正整数），证明还原性存在

若存在$I_1\neq I_2,G_p(I_1)= G_p(I_2)$

则
$$
\frac{\sum \limits_{i\in I_1}p^i}{|I_1|}=\frac{\sum \limits_{i\in I_2}p^i}{|I_2|}
$$
即
$$
|I_2|\sum \limits_{i\in I_1}p^i =|I_1|\sum _{i\in I_2}p^i
$$
容易发现由于$p=N+1>\max\{|I_2|,|I_1|\}$,因此等式两侧是一个$p=N+1$进制数的不同位权表达，这与位权展开的唯一性违背，因此矛盾。

故$\forall I_1\neq I_2,G_p(I_1)\neq G_p(I_2)$

$p=N+1$为一个可行的取法

---

对于$p=2$

我们可以构造一些$N$,和对应的$I_1,I_2$使得可还原性被破坏

反例如下
$$
p=2\\
N=7\\
I_1=\{2,2^3,2^7\}\Rightarrow G_p(I_1)=46\\
I_2=\{2,2^2,2^5,2^6,2^7\}\Rightarrow G_p(I_2)=46
$$
即在$N=7$时存在两个指标集合我们函数获取的值一样，无法区分。

因此$2$不一定能称出来
