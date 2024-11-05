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

- $S_i$为$i$步的可选域
- game tree 又叫决策树

:::

:::tip[例一:八皇后]

$$
S_i\{1\cdots 8\}\\
x_i\neq x_j(i\neq j)\\
\left|\frac{(x_i-x_j)}{(i-j)}\right|\neq 1(i\neq j)
$$

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

### Alpha-Beta prunning

- **Minmax Strategy**:以tic-tac-toe为例，A与B分别持有最大化/，最小化某一收益的前提目标，则我们可以对game tree奇偶分层分别实现最值
- **Alpha-Beta punning**:基于该想法卡上下界（开始进入有奇偶两种），可以在实践中缩减规模到$\mathcal O(\sqrt N)$的效率($N$表示搜索树整体节点数)

## Divide and Conquer

### Definition

- **Divide** ：将问题规模切割成结构相似的子问题
- **Conquer** : 递归解决子问题
- **Combine** : 总问题的解决依赖子问题的结果，同时也需要合并

## Closest Points Problem

> $n$个平面上的点，求最近点对

:::note[算法描述]

- 按照$x$坐标将点集分成等大小的两部分
- 处理两侧的最近点对和跨点集的最近点对
- 假设两侧的结果为$\delta$，则我们考虑$[x_0-\delta,x_0+\delta]$内的点
  - 任意选取范围内一个点，则可更新区域变为$[x_0-\delta,x_0+\delta]\times [y_0,y_0-\delta]$
  - 可以证明最多只有6个**不重合的**点
    - 对左右分看看

则复杂度为$T(N)=2T(\frac{N}{2})+\mathcal O(N)=\mathcal O(N\log N)$

:::

## 复杂度分析

$$
T(N)=aT(\frac{N}{b})+f(N),a,b\in \mathbb Z^+
$$

### 迭代求解法/递归树法

> $$
> T(N)=...=\underbrace{c N_{leaves}}_{conquer}+\underbrace{\sum_{node_i}^{non-leaf-nodes}f(N_{node_i})}_{combine}
> $$

以$T(N)=2T(N/2)+\mathcal O(N)$为例
$$
T(N)=2^kT(\frac{N}{2^k})+k\mathcal O(N)
$$
$k \to \infty ,2^kT(\frac{N}{2^k})\to \mathcal O(N)$

这个基于$N_0\in [1,\sigma)$,$T(N_0)=\mathcal O( 1)$

:::note[补充例子]
$$
T(N)=3T(\frac{N}{4})+\Theta (N^2)
$$
展开有
$$
\begin{align*}
T(N)&=\sum _{i=0}^{\log_4N-1}\left(\frac{3}{16}\right)^i cN^2+\Theta (N^{\log _43})
\\&<\sum_{i=0}^\infty \left(\frac{3}{16}\right)^icN^2+\Theta (N^{\log _4 3})\\&=\frac{cN^2}{1-\frac{3}{16}}+\Theta (N^{\log_4 3})=\mathcal O(N^2)
\end{align*}
$$
这个过程$a=3,b=4,f(n)=\Theta (n^2)$

:::

### 代换法/归纳法

上面这个你猜一下带入即可
$$
\begin{gathered}
\text{T(N)} \\
=dN\log N-dN(\log_23-\frac23)+cN\leq dN\log N \\
ford\geq c/(\log_23-\frac23) 
\end{gathered}
$$



### Master Method 

### Form1

:::important[Form 1]

对于形如$T(N)=aT(N/b)+f(N)$的递推式：
1.若$f(N)=O(N^{(\log_ba)-\varepsilon})$, for $\varepsilon>0$,那么$T(N)=\Theta(N^{\log_ba});$
2.若$f(N)=\Theta(N^{\log_ba})$,那么$T(N)=\Theta(N^{\log_ba}\log N);$
3.若$f(N)=\Omega(N^{(\log_ba)+\varepsilon})$, for $\varepsilon>0$且$af(\frac Nb)<cf(N)$, for $c<1$ and $\forall N>N_0$,那么$T(N)=\Theta(f(N))$ `regularity condition`	

:::

:::tip[注意]

- Merge sort
  - $a=b=2$,case2, $T(N)=\mathcal O(N\log N)$
- $a=b=2,f(N)=N\log ⁡N$；
  - $f(N)=N\log ⁡N$，虽然 $N\log ⁡N=\Theta(N^{log_⁡{2}2})$，但是 $N\log⁡ N\not=\Theta(N^{\log⁡_2 2−\epsilon})$，所以不适用于情况 3；
  - 具体来说，$\lim\limits_{⁡N\rightarrow\infty}\frac{N\log ⁡N}{N^{1+\epsilon}}=\lim\limits_{⁡N\rightarrow\infty}\frac{\log ⁡N}{N^\epsilon}=0\text{ for fixed }\epsilon>0$；
  - 这个例子体现出了 $\epsilon$ 的一定作用；

:::

对于形如 $T(N)=aT(\frac{N}{b})+f(N)$ 的递推式，我们需要依次证明，此处我们使用递归树法进行证明。

:::note[Case 1]
$$
	T(N)=\Theta(N^{\log_{b}a})+\sum\limits_{j=0}^{\log_{b}N-1}a^jf(\frac{N}{b^j})
$$
​	而我们有条件 $f(N)=O(N^{\log_{b}a−\epsilon}),\text{ for }\epsilon>0$，将它代入到上式中得到：              
$$
	\begin{aligned}
	T(N)&=\Theta(N^{\log_{b}a})+\sum\limits_{j=0}^{\log_{b}N-1}a^jO((\frac{N}{b^j})^{\log_{b}a-\epsilon})\\
	&=\Theta(N^{\log_{b}a})+O(N^{\log_{b}a−\epsilon}×\sum\limits_{j=0}^{\log_{b}N−1}(\frac{a}{b^{\log_{b}a−\epsilon}})^j)\\
	&=\Theta(N^{\log_{b}a})+O(N^{\log_{b}a−\epsilon}×\sum\limits_{j=0}^{\log_{b}N−1}(b^\epsilon)^j)\\
	&=\Theta(N^{\log_{b}a})+O(N^{\log_{b}a−\epsilon}×\frac{1×(1−(b^\epsilon)^{\log_{b}N})}{1−b^\epsilon})\\
	&=\Theta(N^{\log_{b}a})+O(N^{\log_{b}a−\epsilon}×\frac{N^\epsilon-1}{b^\epsilon−1})\\
	&=\Theta(N^{\log_{b}a})+O(N^{\log_{b}a−\epsilon}×N^\epsilon)\\
	&=\Theta(N^{\log_{b}a})+O(N^{\log_{b}a})\\
	&=\Theta(N^{\log_{b}a})
	\end{aligned}
$$
​	证毕
:::

:::note[Case 2]
$$
T(N)=\Theta(N^{\log_{b}a})+\sum\limits_{j=0}^{\log_{b}N-1}a^jf(\frac{N}{b^j})
$$

而我们有条件 $f(N)=\Theta(N^{\log_{⁡b}a})$，将它代入到上式中得到：

$$
\begin{aligned}
T(N)&=\Theta(N^{\log_{⁡b}a})+\sum\limits_{j=0}^{\log⁡_{b}N−1}a^j\Theta((\frac{N}{b^j})^{\log⁡_{b}a})\\
&=\Theta(N^{\log_{⁡b}a})+\Theta(N^{\log_{b}a}×\sum\limits_{j=0}^{\log_{⁡b}N−1}(\frac{a}{b^{\log_{b}a}})^j)\\
&=\Theta(N^{\log_{⁡b}a})+\Theta(N^{\log_{b}a}×\log_{⁡b}N)\\
&=Θ(N^{\log_{⁡b}a}\log⁡N)
\end{aligned}
$$

证毕

:::

:::note[Case 3]
$$
T(N)=\Theta(N^{\log_{b}a})+\sum\limits_{j=0}^{\log_{b}N-1}a^jf(\frac{N}{b^j})
$$

接下来的步骤和之前不同。在继续之前，我们首先观察不等式 $af(\frac{N}{b})<cf(N)$，在我们的求和式中，我们观察到我们有大量的形如 $a^jf(\frac{N}{b^j})$ 的项，而这些项都可以通过迭代上面那个不等式来实现，即：

$$
a^jf(\frac{N}{b^j})<c×a^{j−1}f(\frac{N}{b^{j−1}})<...<c^jf(N)
$$

将这个不等式应用于求和式中，我们能够得到：

$$
\begin{aligned}
T(N)&<\Theta(N^{\log_{b}a})+\sum\limits_{j=0}^{\log_{b}N-1}c^jf(N)\\
&=\Theta(N^{\log_{b}a})+f(N)\sum\limits_{j=0}^{\log_{b}N-1}c^j\\
&=\Theta(N^{\log_{b}a})+f(N)\times\frac{1-c^{\log_{b}N}}{1-c}\\
&=\Theta(N^{\log_{b}a})+f(N)\times\frac{1-N^{\log_{b}c}}{1-c}
\end{aligned}
$$

而由于 $c<1$，所以 $\log_{⁡b}c<0$；而 $N>0$，而且一般非常大，所以 $N\log_{⁡b}c\in(0,1)$。因此，对于确定的常数 $c$，我们有 $\frac{1−N^{\log_{⁡b}c}}{1−c}\in(0,\frac{1}{1−c})$；

因此，上式便能改变为：

$$
\begin{aligned}
T(N)&<\Theta(N^{\log_{b}a})+f(N)\times\frac{1-N^{\log_{b}c}}{1-c}\\
&<\Theta(N^{\log_{b}a})+f(N)\times\frac{1}{1-c}
\end{aligned}
$$

并且，由于 $f(N)=\Omega(N^{\log_{⁡b}a+\epsilon}),\text{ for }\epsilon>0$，所以可以得到 $c_2N^{\log_{⁡b}a+\epsilon}<f(N)\Rightarrow N^{\log_{b}a}<\frac{1}{c_2N^\epsilon}f(N)$，因此 $T(N)<\Theta(N^{\log_{b}a})+f(N)\times\frac{1}{1-c}<c_1N^{\log_{b}a}+f(N)\times\frac{1}{1-c}<(\frac{c_1}{c_2N^\epsilon}+\frac{1}{1-c})f(N)=O(f(N))$

而我们知道，要证明 $T(N)=\Theta(f(N))$ 还需要证明 $T(N)=\Omega(f(N))$：

$$
T(N)=Θ(N^{\log_{b}a})+\sum\limits_{j=0}^{\log_{b}N−1}a^jf(\frac{N}{b^j})
\geq\sum\limits_{j=0}^{\log_{b}N−1}a^jf(\frac{N}{b^j})\geq f(N)
$$

由此得到 $T(N)=\Omega(f(N))$，最终证得 $T(N)=\Theta(f(N))$，至此证毕。

:::

### Form 2

:::important[Form 2]

对于形如 $T(N)=aT(\frac{N}{b})+f(N)$ 的递推式：

1. 若 $af(\frac{N}{b})=\kappa f(N)\text{ for fixed }\kappa <1$，那么 $T(N)=\Theta(f(N))$；
2. 若 $af(\frac{N}{b})=\kappa f(N)\text{ for fixed }\kappa >1$，那么 $T(N)=\Theta(N^{\log_{⁡b}a})=\Theta(a^{\log_{⁡b}N})$；
3. 若 $af(\frac{N}{b})=f(N)$，那么 $T(N)=\Theta(f(N)log_{⁡b}N)$；

:::

对于形如 $T(N)=aT(\frac{N}{b})+f(N)$ 的递推式，基于线性关系的形式二的证明实际上和形式一的第三种情况的证明非常相像。

假设我们有 $af(\frac{N}{b})=cf(N)$，只需要讨论 c 的取值范围对结果的影响，就可以一次性得到结果。

类似于形式一的第三种情况的证明，我们迭代该关系式，得到关系：

$$
a^jf(\frac{N}{b^j})=c^jf(N)
$$

于是，我们有：

$$
\begin{aligned}
T(N)&<\Theta(N^{\log_{b}a})+\sum\limits_{j=0}^{\log_{b}N-1}c^jf(N)\\
&=\Theta(N^{\log_{b}a})+f(N)\sum\limits_{j=0}^{\log_{b}N-1}c^j\\
&=\Theta(N^{\log_{b}a})+f(N)\times\frac{1-c^{\log_{b}N}}{1-c}\\
&=\Theta(N^{\log_{b}a})+f(N)\times\frac{1-N^{\log_{b}c}}{1-c}
\end{aligned}
$$

我们现在并不像 Form 1 有显式的 $f(N)=\Omega(N^{\log_{⁡b}a+\epsilon})$ 的条件，而这个条件最终决定 conquer 部分和 combine 部分谁占主导地位。但是，我们实际上只需要得到 $f(N) = \Omega(N^{\log_{⁡b}a})$ 就够了。其实 $af(\frac{N}{b})∼cf(N)$ 这件事本身就暗含了它与 $N^{\log_{⁡b}a}$ 的关系：

$$
cf(N)∼af(\frac{N}{b})∼...∼a^Lf(\frac{N}{b^L})
$$

可以发现，这一步还是和 Form 1 的第三种情况的证明过程高度相似。只不过现在我们要更进一步地看这个式子。

当 $c<1$ 时，实际上有 $f(N)>af(\frac{N}{b})$；当 $c=1$ 时，实际上有 $f(N)=af(\frac{N}{b})$；当 $c>1$ 时，实际上有 $f(N)<af(\frac{N}{b})$；

我们假设 $\frac{N}{b^L}$ 足够小（即递归到最末端，只需要进行 conquer 的时候），即 $\frac{N}{b^L}=\Theta(1)$，那么就有 $L=\Theta(\log_{⁡b}N)$。于是，我们有：

$$
f(N)∼Θ(a^{\log_{⁡b}N})=Θ(N^{\log_{⁡b}a})
$$

剩下的证明就跟 Form 1 的第三种情况一致

#### Form 3

:::important[Form 3]

当递推关系满足：

$$
T(N)=aT(\frac{N}{b})+\Theta(N^k\log^{p}N)\text{ Where }a\geq 1,b>1,p\geq 0
$$

其复杂度有结论：

$$
T(N)=
\begin{cases}
O(N^{\log_{⁡b}a}),a>b^k\\
O(N^k\log⁡^{p+1}N),a=b^k\\
O(N^k\log^{p}N),a<b^k
\end{cases}
$$
:::

#### Form4(re-Form3)

(Chap4.5 4.1Master Method)

:::important[Form4]

对于形如$T(N)=aT(N/b)+f(N)$的递推式：
1.若$f(N)=O(N^{(\log_ba)-\varepsilon})$, for $\varepsilon>0$,那么$T(N)=\Theta(N^{\log_ba});$
2.若$f(N)=\Theta(N^{\log_ba}\log^k N)$,那么$T(N)=\Theta(N^{\log_ba}\log^{k+1} N);$
3.若$f(N)=\Omega(N^{(\log_ba)+\varepsilon})$, for $\varepsilon>0$且$af(\frac Nb)<cf(N)$, for $c<1$ and $\forall N>N_0$,那么$T(N)=\Theta(f(N))$ `regularity condition`	

:::

实际上就是Form3的重述
