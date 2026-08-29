# Finite, Countable and Uncountable Sets 有限，可数与不可数集

本节引入了基数的概念，并给出了若干关于可数集的基本结论。

## Definition 2.1 function/mapping 函数/映射，domain 定义域，codomain 陪域，range 值域

设 $A,B$ 是集合，$f \subset A\times B$，如果对任意 $x \in A$，存在 $y \in B$ 使得 $(x,y) \in f$，则称 $f$ 是一个从 $A$ 到 $B$ 的函数，记作 $f\colon A\to B$。我们记 $y=f(x)$ 为 $f$ 在 $x$ 处的值，称 $A$ 是 $f$ 的定义域，$B$ 是 $f$ 的陪域，$f$ 的所有值构成的集合是 $B$ 的一个子集，称为值域。所有从 $A$ 到 $B$ 的函数构成的集合记作 $B^{A}$。

## Definition 2.2 image 像，preimage 原像，surjection 满射，injection 单射

设 $A,B$ 是集合，$f\colon A\to B$。如果 $E\subset A$，则称 $f(E)=\{ f(x) : x \in E \}$ 为 $E$ 在 $f$ 下的像。则 $f(A)$ 就是 $f$ 的值域，如果 $f(A)=B$，我们就称 $f$ 是一个满射。

如果 $E\subset B$，我们称 $f^{-1}(E)=\{ x \in A : f(x) \in E \}$ 为 $E$ 在 $f$ 下的原像。特别地，如果 $E=\{ y \}$，我们将 $f^{-1}(\{ y \})$ 简记为 $f^{-1}(y)$。如果对任意 $y \in B$，集合 $f^{-1}(y)$ 至多只有一个元素，就称 $f$ 是一个单射。等价地，$f$ 是一个单射如果当 $x_{1}\neq x_{2}$ 时有 $f(x_{1})\neq f(x_{2})$。

我们在验证单射性时通常取上述条件的逆否命题：如果 $f(x_{1})=f(x_{2})$，那么 $x_{1}=x_{2}$。

## Definition 2.3 bijection 双射，equipotent 等势

如果 $f\colon A\to B$ 既是单射也是满射，则称 $f$ 是一个双射，并称 $A$ 和 $B$ 具有相同的基数，或等势，记作 $A\approx B$。

等势关系显然具有以下性质：

1. 自反性：$A\approx A$。
2. 对称性：如果 $A\approx B$ 那么 $B\approx A$。
3. 传递性：如果 $A\approx B$ 且 $B\approx C$，那么 $A\approx C$。

任何满足这三条性质的关系称为一个等价关系。

## Definition 2.4 finite 有限，countable 可数，uncountable 不可数

对任意集合 $A$，我们称它是

1. 有限的，如果 $A$ 与某个 $\{ 1,\dots,n \}$ 等势。
2. 无限的，如果 $A$ 不是有限的。
3. 可数的，如果 $A\approx \mathbb{N}$。
4. 不可数的，如果 $A$ 不是有限集也不是可数集。
5. 至多可数的，如果 $A$ 是有限集或者可数集。

可数集也称为是可列的，因为存在从 $\mathbb{N}$ 到 $A$ 的双射 $f$，其将 $A$ 的元素按照

$$
\begin{gather}
f(0),f(1),f(2),\dots
\end{gather}
$$

的顺序不重复也不遗漏地列出。

对于有限集 $A,B$，说两者等势就是指 $A$ 和 $B$ 包含相同个数的元素。然而，对于无限集，“元素个数”的概念是不明确的，因此我们只能借助于双射。

### Example 2.5

设 $\mathbb{Z}$ 是所有整数构成的集合，则 $\mathbb{Z}$ 是可数的，因为我们可以建立如下的双射：

$$
\begin{gather}
\mathbb{Z}: 0,1,-1,2,-2,3,-3,\dots \\
\mathbb{N}: 0,1,2,3,4,5,6,7,\dots
\end{gather}
$$

其中 $f\colon \mathbb{N}\to \mathbb{Z}$ 定义为

$$
\begin{gather}
f(n)=\begin{cases}
\dfrac{n}{2}, & n \text{ even} \\
-\dfrac{n+1}{2}, & n \text{ odd}
\end{cases}
\end{gather}
$$

可见，一个无限集可以与它的一个真子集等势，这对于有限集来说不成立。因此，这一性质可以作为无限集的一个定义（Dedekind 无限集）。

## Definition 2.6 sequence 序列

设 $A$ 是集合，$A$ 上的一个序列是 $\mathbb{N}$ 到 $A$ 的一个函数 $f$。设 $f(n)=x_{n}$，则我们可以将该序列记作 $(x_{n})_{n=0}^{\infty}$，元素 $x_{n}$ 称为序列的第 $n$ 项。

有时候，我们将序列定义为正整数集 $\mathbb{N}^{*}$ 到 $A$ 的函数 $(x_{n})_{n=1}^{\infty}$，此时序列的下标从 $1$ 开始。

## Theorem 2.7

可数集 $A$ 的无限子集是可数的。

这就是说，可数无穷是“最小的”一种无穷。

### Proof

设 $E\subset A$ 是无限集。由于 $A$ 可数，将 $A$ 的元素排成一列 $(x_{n})$，构造正整数序列 $(n_{k})$ 如下：

取 $n_{1}$ 为使得 $x_{n_{1}}\in E$ 的最小正整数。假设已取定 $n_{1},\dots,n_{k-1}$，令 $n_{k}$ 为使得 $x_{n_{k}}\in E$ 且 $n_{k}>n_{k-1}$ 的最小正整数。

设 $f(k)=x_{n_{k}}$，则 $f$ 是 $\mathbb{N}^{*}$ 到 $E$ 的一个双射，从而 $E$ 可数。（$\mathbb{N}$ 与 $\mathbb{N}^{*}$ 显然等势）

## Definition 2.8 union 并集，intersection 交集

设 $A$ 和 $\Omega$ 是集合，我们将每个 $\alpha \in A$ 关联到 $E_{\alpha}\subset\Omega$，所有这些 $E_{\alpha}$ 构成的集合记作 $\{ E_{\alpha} \}_{\alpha \in A}$。

$\{ E_{\alpha} \}$ 的并集 $S$ 定义为

$$
\begin{gather}
S=\bigcup_{\alpha \in A} E_{\alpha}=\{ x \in\Omega : x \in \text{至少一个 } E_{\alpha} \}
\end{gather}
$$

如果 $A=\{ 1,\dots,n \}$，则我们通常记作

$$
\begin{gather}
S=\bigcup_{j=1}^{n} E_{j}=E_{1}\cup\dots \cup E_{n}
\end{gather}
$$

如果 $A=\mathbb{N}^{*}$，则我们记作

$$
\begin{gather}
S=\bigcup_{j=1}^{\infty} E_{j}
\end{gather}
$$

其中符号 $\infty$ 表明我们正在对可数个集合取并集。

$\{ E_{\alpha} \}$ 的交集 $P$ 定义为

$$
\begin{gather}
P=\bigcap_{\alpha \in A}E_{\alpha}=\{ x \in\Omega : x \in \text{每个 } E_{\alpha} \}
\end{gather}
$$

当 $A=\{ 1,\dots,n \}$ 或 $\mathbb{N}^{*}$ 时的记号与并集是类似的。

设 $A,B$ 是集合，如果 $A\cap B$ 非空，则称 $A,B$ 相交，否则就称 $A,B$ 不相交。

## Theorem 2.9

设 $\{ E_{n} \}_{n=1}^{\infty}$ 是可数集的一列可数子集，那么它们的并集 $\bigcup_{n=1}^{\infty}E_{n}$ 也是可数的。

### Proof

将 $E_{n}$ 的元素排成一列 $(x_{n}^{k})_{k=1}^{\infty}$，我们得到下面的二维列表：

$$
\begin{gather}
x_{1}^{1},x_{1}^{2},x_{1}^{3},x_{1}^{4},\dots \\
x_{2}^{1},x_{2}^{2},x_{2}^{3},x_{2}^{4},\dots \\
x_{3}^{1},x_{3}^{2},x_{3}^{3},x_{3}^{4},\dots \\
x_{4}^{1},x_{4}^{2},x_{4}^{3},x_{4}^{4},\dots \\
\vdots
\end{gather}
$$

将这些元素按斜线方向排成一列

$$
\begin{gather}
x_{1}^{1}; \quad x_{2}^{1},x_{1}^{2}; \quad x_{3}^{1},x_{2}^{2},x_{1}^{3}; \quad x_{4}^{1},x_{3}^{2},x_{2}^{3},x_{1}^{4}; \dots
\end{gather}
$$

由于在以上序列中可能出现相同的元素，因此 $S=\bigcup_{n=1}^{\infty}E_{n}$ 与正整数的某个子集等势，从而是至多可数的。另一方面，$E_{1}\subset S$ 是无限集，因此 $S$ 也是无限集，从而 $S$ 可数。

## Corollary 2.10

设 $A$ 至多可数，并且对任意 $\alpha \in A$，$B_{\alpha}$ 至多可数，则 $\bigcup_{\alpha \in A}B_{\alpha}$ 是至多可数的。

## Theorem 2.11

设 $A$ 是可数集，$B_{n}$ 为所有 $n$ 元组 $(a_{1},\dots,a_{n})$ 构成的集合，其中 $a_{k}\in A$，则 $B_{n}$ 是可数集。

### Proof

我们使用归纳法。$B_{1}=A$ 是可数集。假设 $B_{n-1}$ 可数，则 $B_{n}$ 中的元素具有形式

$$
\begin{gather}
(b,a) \quad (b \in B_{n-1},a \in A)
\end{gather}
$$

对固定的 $b$，所有这些 $(b,a)$ 构成的集合与 $A$ 等势，从而可数。因此 $B_{n}$ 是可数个可数集的并集，应用 [[#Theorem 2.9]] 即证。

## Corollary 2.12

有理数集 $\mathbb{Q}$ 是可数集。

这是因为 $r \in \mathbb{Q}$ 具有形式 $b /a$，它对应于二元组 $(a,b)$，其中 $a,b$ 是整数。

## Theorem 2.13

所有元素为 $0$ 或 $1$ 的序列构成的集合 $\{ 0,1 \}^{\mathbb{N}}$ 是不可数集。

### Proof (Cantor)

设 $E\subset A$ 是可数集，将它的元素排成一列 $s_{1},s_{2},\dots$，我们构造一个序列 $s$ 如下：

如果 $s_{n}$ 的第 $n$ 项是 $1$，那么我们令 $s$ 的第 $n$ 项为 $0$，反之亦然。于是，序列 $s$ 与 $s_{1},s_{2},\dots$ 中的每一个都有一项不同，因此 $s \not\in E$。这表明 $E$ 是 $A=\{ 0,1 \}^{\mathbb{N}}$ 的真子集。

我们已经证明 $A$ 的每个可数子集都是真子集，这表明 $A$ 不可数。（否则 $A$ 将是自身的真子集，矛盾）

以上的证明称为 Cantor 对角线论证，它被用于证明 $\mathbb{R}$ 是不可数集。

# Metric Spaces 度量空间

本节引入了度量空间，以及开性、闭性等基本拓扑学概念。

## Definition 2.14 metric space 度量空间

称集合 $X$ 是一个度量空间，如果在其上可以定义函数 $d\colon X\times X\to \mathbb{R}$ 使得对任意 $p,q \in X$ 成立：

- 正定性：如果 $p\neq q$ 那么 $d(p,q)>0$；$d(p,p)=0$。
- 对称性：$d(p,q)=d(q,p)$。
- 三角不等式：对任意 $r \in X$ 有 $d(p,q)\leq d(p,r)+d(r,q)$。

满足以上性质的函数称为度量。度量空间中的元素称为点。

### Example 2.15

在数学分析中最为重要的度量空间是 euclidean 空间 $\mathbb{R}^{k}$，其上的度量为

$$
\begin{gather}
d(\mathbf{x},\mathbf{y})=\lvert \mathbf{x}-\mathbf{y} \rvert 
\end{gather}
$$

此外，度量空间 $X$ 的任意子集 $Y$ 也是度量空间，我们可以验证函数 $d$，限制在 $Y$ 上，满足定义中的三条性质。因此，euclidean 空间的任意子集也是度量空间。其他例子包括紧空间上的连续函数空间 $C(K)$ 以及平方可积函数空间 $L^{2}(\mu)$。

## Definition 2.16 interval 区间，cell，ball 球，convex 凸的

定义开区间 $(a,b)=\{ x \in \mathbb{R} : a<x<b \}$，闭区间 $[a,b]=\{ x \in \mathbb{R}:a\leq x\leq b \}$，左开右闭区间 $(a,b]$ 和左闭右开区间 $[a,b)$ 的定义是类似的。

设 $a_{j}<b_{j}\ (j=1,\dots,k)$，定义一个 $k$-cell 为

$$
\begin{gather}
[a_{1},b_{1}]\times\dots \times [a_{k},b_{k}]=\{ (x_{1},\dots,x_{k}) \in \mathbb{R}^{k} : a_{j}\leq x_{j}\leq b_{j} \}
\end{gather}
$$

因此一个 $1$-cell 是一个区间，一个 $2$-cell 是一个矩形，以此类推。

设 $\mathbf{x}\in \mathbb{R}^{k},r>0$，一个以 $\mathbf{x}$ 为中心，$r$ 为半径的开球定义为

$$
\begin{gather}
B(\mathbf{x},r)=\{ \mathbf{y}\in \mathbb{R}^{k}: \lvert \mathbf{y}-\mathbf{x} \rvert <r \}
\end{gather}
$$

同中心、同半径的闭球的定义是类似的，只需将 $<$ 改成 $\leq$ 即可。

称 $E\subset \mathbb{R}^{k}$ 是凸集，如果对任意 $\mathbf{x},\mathbf{y}\in E$ 和 $0<\lambda<1$ 有

$$
\begin{gather}
\lambda \mathbf{x}+(1-\lambda)\mathbf{y} \in E
\end{gather}
$$

容易验证，$k$-cell、开球、闭球都是凸集。

## Definition 2.17 neighborhood 邻域，limit point 极限点，isolated point 孤立点，closed 闭的，interior 内部，open 开的，perfect 完美的，bounded 有界的，dense 稠密的

设 $X$ 是度量空间，下面提到的所有点和集合都是 $X$ 的元素和子集。

1. $p$ 的一个邻域是一以 $p$ 为中心的开球 $B(p,r)=\{ q \in X:d(p,q)<r \}$，$r>0$ 称为它的半径。
2. 称 $p$ 是 $E$ 的一个极限点，如果 $p$ 的每个邻域都包含一个点 $q \in E$ 使得 $q\neq p$。
3. 如果 $p \in E$ 且 $p$ 不是 $E$ 的极限点，则称 $p$ 是 $E$ 的一个孤立点。
4. 称 $E$ 是闭集，如果 $E$ 的所有极限点都属于 $E$。
5. 称 $p$ 是 $E$ 的一个内部点，如果存在 $p$ 的邻域 $N$ 使得 $N\subset E$。
6. 称 $E$ 是开集，如果 $E$ 的所有点都是内部点。
7. 称 $E$ 是完美集，如果 $E$ 是闭集，且 $E$ 的每个点都是极限点。
8. 称 $E$ 有界，如果存在 $M>0$ 和 $q \in X$ 使得对任意 $p \in E$ 有 $d(p,q)\leq M$。
9. 称 $E$ 在 $X$ 中稠密，如果 $X$ 中的每个点都是 $E$ 的元素或者 $E$ 的极限点（或者同时成立）。

例：$\mathbb{R}$ 中的邻域是开区间，而 $\mathbb{R}^{2}$ 中的邻域是圆盘的内部。

## Theorem 2.18

任何邻域都是开集。

### Proof

设 $E=B(p,r)$ 是一个邻域，$q \in E$，则

$$
\begin{gather}
h=r-d(p,q)>0
\end{gather}
$$

于是当 $s$ 满足 $d(q,s)<h$ 时，有

$$
\begin{gather}
d(p,s)\leq d(p,q)+d(q,s)<r
\end{gather}
$$

即 $B(q,h)\subset E$，从而 $q$ 是 $E$ 的内部点。

## Theorem 2.19

如果 $p$ 是 $E$ 的一个极限点，那么 $p$ 的每个邻域都包含了 $E$ 中无穷多个元素。

### Proof

假设有 $p$ 的邻域 $N$ 仅包含有限个 $E$ 中的点 $q_{1},\dots,q_{n}$，并设它们都和 $p$ 不同，则

$$
\begin{gather}
r=\min_{1\leq j\leq n} d(q_{j},p)>0
\end{gather}
$$

并且 $B(p,r)$ 与 $E$ 的交集中没有与 $p$ 不同的点，这与 $p$ 是极限点的条件矛盾。

## Corollary 2.20

有限集不存在极限点。

## Theorem 2.21 (De Morgen)

设 $\{ E_{\alpha} \}_{\alpha \in A}$ 是一个集族，则

$$
\begin{gather}
\left( \bigcup_{\alpha \in A} E_{\alpha} \right)^{c}=\bigcap_{\alpha \in A} E_{\alpha}^{c} \\
\left( \bigcap_{\alpha \in A} E_{\alpha} \right)^{c}=\bigcup_{\alpha \in A} E_{\alpha}^{c}
\end{gather}
$$

### Proof

证明集合相等的命题，我们通常通过分别证明两个方向的包含来进行。

设 $x \in\left( \bigcup E_{\alpha} \right)^{c}$，则 $x \not\in \bigcup E_{\alpha}$，即 $x \not\in$ 任何 $E_{\alpha}$，从而 $x \in$ 每个 $E_{\alpha}^{c}$，因此 $x \in \bigcap E_{\alpha}^{c}$。将以上论证倒过来写即得反方向的包含。

对于第二个命题，对第一个等式做替换 $E_{\alpha}\leftarrow E_{\alpha}^{c}$ 然后两边取补集即可。

## Theorem 2.22

一个集合 $E$ 是开集当且仅当 $E^{c}$ 是闭集。

### Proof

设 $E^{c}$ 是闭集，则如果 $x \not\in E^{c}$ 即 $x \in E$，那么 $x$ 不是 $E^{c}$ 的极限点，从而存在 $x$ 的邻域 $N$，它与 $E^{c}$ 不相交，即 $N\subset E$。

设 $E$ 是开集，$x$ 是 $E^{c}$ 的极限点，那么 $x$ 不可能在 $E$ 中，否则存在 $x$ 的邻域 $N\subset E$，这与 $x$ 是极限点矛盾。因此 $x \in E^{c}$。

## Corollary 2.23

一个集合 $E$ 是闭集当且仅当 $E^{c}$ 是开集。

## Theorem 2.24

(a) 对任意开集族 $\{ G_{\alpha} \}$，$\bigcup_{\alpha}G_{\alpha}$ 是开集。
(b) 对任意闭集族 $\{ F_{\alpha} \}$，$\bigcap_{\alpha}F_{\alpha}$ 是闭集。
(c) 对任意有限个开集 $G_{1},\dots,G_{n}$，$\bigcap_{j=1}^{n}G_{j}$ 是开集。
(d) 对任意有限个闭集 $F_{1},\dots,F_{n}$，$\bigcup_{j=1}^{n}F_{j}$ 是闭集。

### Proof

(a) 设 $G=\bigcup G_{\alpha}$，如果 $x \in G$，那么 $x$ 属于某个 $G_{\alpha}$，从而有 $x$ 的邻域 $N\subset G_{\alpha}\subset G$。

(b) 根据 [[#Theorem 2.21 (De Morgen)]]，我们有

$$
\begin{gather}
\bigcap_{\alpha} F_{\alpha}=\left( \bigcup_{\alpha} F_{\alpha}^{c} \right)^{c}
\end{gather}
$$

$F_{\alpha}^{c}$ 是开集，由 (a) 知 $\bigcup F_{\alpha}^{c}$ 也是开集，因而 $\bigcap F_{\alpha}$ 是闭集。

(c) 设 $H=\bigcap_{j=1}^{n}G_{j}$，$x \in H$，则 $x$ 属于每个 $G_{j}$，对每个 $j$，都有 $x$ 的邻域 $B(x,r_{j})\subset G_{j}$，令

$$
\begin{gather}
r=\min_{1\leq j\leq n} r_{j}>0
\end{gather}
$$

则 $B(x,r)$ 包含于每个 $G_{j}$ 中，从而 $B(x,r)\subset H$。

(d) 对 (c) 取补集即证。

### Example 2.25

以上定理中 (c)(d) 的有限性是必要的，这从证明过程中也可以看出来：无穷多个正数的下确界（最小值）不一定是正数。比如 $G_{n}=(-1 /n,1 /n)$，其交集 $\bigcap_{n=1}^{\infty}G_{n}=\{ 0 \}$ 不是开集。

## Definition 2.26 closure 闭包

设 $X$ 是度量空间，$E\subset X$，令 $E'$ 表示 $E$ 的所有极限点构成的集合，则我们定义 $E$ 的闭包为 $\overline{E}=E\cup E'$。

## Theorem 2.27

设 $X$ 是度量空间，$E\subset X$，则

1. $\overline{E}$ 是闭集。
2. $E=\overline{E}$ 当且仅当 $E$ 是闭集。
3. 对任意闭集 $F\supset E$ 都有 $\overline{E}\subset F$。

命题 (1)(3) 表明 $\overline{E}$ 是包含 $E$ 的最小闭集。

### Proof

(1) 设 $p$ 是 $\overline{E}$ 的极限点，则对任意 $r>0$，邻域 $B(p,r /2)$ 中都包含 $q \in \overline{E}$ 使得 $q\neq p$。对于相同的 $r$，邻域 $B(q,r /2)$ 中包含某个 $s \in E$，于是

$$
\begin{gather}
d(p,s)\leq d(p,q)+d(q,s)<r
\end{gather}
$$

因此 $B(p,r)$ 中包含了 $s \in E$，从而 $p$ 要么是 $E$ 的元素，要么是 $E$ 的极限点，即证 $p \in \overline{E}$。

(2) 如果 $E=\overline{E}$，则 (1) 表明 $E$ 是闭集。反之，如果 $E$ 是闭集，则 $E'\subset E$，因此 $\overline{E}=E\cup E'= E$。

(3) 由于 $F$ 是闭集，则 $F\supset F'$，从而 $F\supset E'$，故 $F\supset E\cup E'=\overline{E}$。

## Theorem 2.28

设 $E\subset \mathbb{R}$ 非空有上界，令 $y=\sup E$，则 $y \in \overline{E}$。特别地，如果 $E$ 是闭集，那么 $y \in E$。

### Proof

如果 $y \in E$ 那么 $y \in \overline{E}$。假设 $y \not\in E$，则对任意 $h>0$，存在 $x \in E$ 使得 $y-h<x< y$，于是 $y$ 是 $E$ 的一个极限点，从而 $y \in \overline{E}$。

## Remark 2.29

前面提到，一个度量空间 $X$ 的子集 $Y$ 也是度量空间，因此，我们也可以在 $Y$ 上定义开集、闭集等概念。例如，在 $\mathbb{R}^{2}$ 中，开区间 $(a,b)$ 不是开集，但它是 $\mathbb{R}\subset \mathbb{R}^{2}$ 中的开集。因此，一个集合开性和闭性是相对于其周围的空间而言的。在需要区分 $X$ 和 $Y$ 的情况下，我们说 $E$ 相对于 $Y$ 是开的，如果对任意 $p \in E$，存在 $r>0$ 使得

$$
\begin{gather}
B_{Y}(p,r)=\{ q \in Y : d(p,q)<r \} \subset E
\end{gather}
$$

下面的定理表明，相对于 $X$ 开和相对于 $Y$ 开之间有一个简单的联系。

## Theorem 2.30

设 $Y\subset X$，$E\subset Y$ 相对于 $Y$ 是开的当且仅当存在 $X$ 中的开集 $G$ 使得 $E=Y\cap G$。

此外，$E\subset Y$ 相对于 $Y$ 是闭的当且仅当存在 $X$ 中的闭集 $F$ 使得 $E=Y\cap F$。

### Proof

设 $E$ 相对于 $Y$ 是开的，则对任意 $p \in E$，存在 $r_{p}>0$ 使得 $B_{Y}(p,r_{p})\subset E$。令

$$
\begin{gather}
G=\bigcup_{p \in E} B_{X}(p,r_{p})
\end{gather}
$$

则 $G$ 是一族开集的并集，从而是 $X$ 中的开集。显然 $E\subset Y\cap G$。反之，对任意 $p \in E$ 我们有 $B_{X}(p,r_{p})\cap Y=B_{Y}(p,r_{p})\subset E$，因此 $Y\cap G\subset E$。

现在假设 $E$ 相对于 $Y$ 是闭的，则 $Y\setminus E$ 相对于 $Y$ 是开的，从而存在 $X$ 中的开集 $G$ 使得 $Y\setminus E=Y\cap G$。两边取关于 $Y$ 的补集，即得

$$
\begin{gather}
E=Y\setminus (Y\cap G)=Y\cap (Y\setminus G)=Y\cap (X\setminus G)
\end{gather}
$$

$X\setminus G$ 是 $X$ 中的闭集，这就完成了证明。

# Compact Sets 紧致集

