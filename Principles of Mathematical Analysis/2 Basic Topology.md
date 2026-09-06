# Finite, Countable and Uncountable Sets 有限，可数与不可数集

## Definition 2.1 function (mapping) 函数（映射），domain 定义域，codomain 陪域，range 值域

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

设 $X$ 是度量空间，$Y\subset X$，则

1. $E\subset Y$ 相对于 $Y$ 开当且仅当存在 $X$ 中的开集 $G$ 使得 $E=G\cap Y$。
2. $E\subset Y$ 相对于 $Y$ 闭当且仅当存在 $X$ 中的闭集 $F$ 使得 $E=F\cap Y$。

### Proof

设 $E$ 相对于 $Y$ 是开的，则对任意 $p \in E$，存在 $r_{p}>0$ 使得 $B_{Y}(p,r_{p})\subset E$。令

$$
\begin{gather}
G=\bigcup_{p \in E} B_{X}(p,r_{p})
\end{gather}
$$

则 $G$ 是一族开集的并集，从而是 $X$ 中的开集。显然 $E\subset G\cap Y$。反之，对任意 $p \in E$ 我们有 $B_{X}(p,r_{p})\cap Y=B_{Y}(p,r_{p})\subset E$，因此 $G\cap Y\subset E$。

反方向的蕴含是显然的。

现在假设 $E$ 相对于 $Y$ 是闭的，则 $Y\setminus E$ 相对于 $Y$ 是开的，从而存在 $X$ 中的开集 $G$ 使得 $Y\setminus E=G\cap Y$。两边取关于 $Y$ 的补集，即得

$$
\begin{gather}
E=Y\setminus (G\cap Y)=(Y\setminus G)\cap Y=(X\setminus G)\cap Y
\end{gather}
$$

其中 $F=X\setminus G$ 是 $X$ 中的闭集。

# Compact Sets 紧致集

本节引入了紧致性的概念，它可以视为有限性在无限集上的推广：我们总可以将紧致集划分为有限多个简单区域（开集），然后分别在各个部分上对其性质进行考察。

## Definition 2.31 open cover 开覆盖

设 $X$ 是度量空间，$E \subset X$，$E$ 的一个开覆盖定义为开集族 $\{ G_{\alpha} \}$ 使得 $E\subset \bigcup_{\alpha}G_{\alpha}$。

## Definition 2.32 compact 紧致的

称度量空间 $X$ 的一个子集 $K$ 是紧致的，如果 $K$ 的任意开覆盖都包含一个有限子覆盖。具体来说，如果 $\{ G_{\alpha} \}$ 是 $K$ 的一个开覆盖，那么存在有限个指标 $\alpha_{1},\dots,\alpha_{n}$ 使得 $K\subset G_{\alpha_{1}}\cup\dots \cup G_{\alpha_{n}}$。

## Theorem 2.33

设 $K\subset Y\subset X$，则 $K$ 相对于 $X$ 紧致当且仅当 $K$ 相对于 $Y$ 紧致。

以上定理表明，不像开性和闭性，一个集合的紧致性与其周围的空间无关。因此，我们能够将一个紧致集视为一个单独的度量空间，而无需指明其嵌入的环境空间。

### Proof

设 $K$ 相对于 $X$ 紧致，$\{ V_{\alpha} \}$ 是 $Y$ 中的开集族，使得 $K\subset \bigcup_{\alpha}V_{\alpha}$。则存在 $X$ 中的开集 $\{ G_{\alpha} \}$，满足 $V_{\alpha}=G_{\alpha}\cap Y$，于是 $\{ G_{\alpha} \}$ 是 $K$ 的开覆盖，从而存在有限个指标 $\alpha_{1},\dots,\alpha_{n}$ 使得

$$
\begin{gather}
K \subset G_{\alpha_{1}}\cup\dots \cup G_{\alpha_{n}}
\end{gather}
$$

由于 $K\subset Y$，我们也有

$$
\begin{gather}
K\subset V_{\alpha_{1}}\cup \dots \cup V_{\alpha_{n}}
\end{gather}
$$

即证 $K$ 相对于 $Y$ 紧致。

反之，如果 $K$ 相对于 $Y$ 紧致，令 $\{ G_{\alpha} \}$ 是 $X$ 中的开集族，且覆盖 $K$。定义 $V_{\alpha}=G_{\alpha}\cap Y$，由于 $K\subset Y$，因此 $\{ V_{\alpha} \}$ 也是 $K$ 的开覆盖，从而有有限子覆盖 $K\subset V_{\alpha_{1}}\cup\dots \cup V_{\alpha_{n}}$。又由于 $V_{\alpha}\subset G_{\alpha}$，因此 $\{ G_{\alpha} \}$ 也有有限子覆盖，从而 $K$ 相对于 $X$ 紧致。

## Theorem 2.34

度量空间的紧致子集是闭的。

### Proof

设 $K$ 是度量空间 $X$ 的紧致子集，我们来证明 $K^{c}$ 是一个开集。

设 $p \in K^{c}$，如果 $q \in K$，令 $V_{q}$ 和 $W_{q}$ 分别为 $p$ 和 $q$ 的邻域，其半径均小于 $\frac{1}{2}d(p,q)$。所有这些 $W_{q}$ 构成了 $K$ 的一个开覆盖，从而存在有限个 $q_{1},\dots,q_{n}\in K$ 使得

$$
\begin{gather}
K\subset W_{q_{1}}\cup\dots \cup W_{q_{n}}=W
\end{gather}
$$

设 $V=V_{q_{1}}\cup\dots \cup V_{q_{n}}$，则 $V$ 是 $p$ 的邻域，且 $V$ 与 $W$ 不相交。因此 $V\subset K^{c}$，从而 $p$ 是 $K^{c}$ 的内部点。

## Theorem 2.35

紧致集的闭子集是紧致的。

### Proof

设 $F\subset K\subset X$，其中 $K$ 紧致，$F$ 相对于 $X$ 闭。设 $\{ G_{\alpha} \}$ 是 $F$ 的一个开覆盖。由于 $F$ 在 $X$ 中闭，$F^{c}$ 在 $X$ 中开；又因为 $F\subset K$，$K$ 中的点要么属于 $F$，要么属于 $F^{c}$，所以 $\{ G_{\alpha} \}\cup \{ F^{c} \}$ 构成 $K$ 的一个开覆盖。

由 $K$ 的紧致性，该覆盖有一个有限子覆盖。如果 $F^{c}$ 恰好在这个有限子覆盖中，则将它删去，由于 $F$ 中的点均不在 $F^{c}$ 中，删去后剩下的有限个 $G_{\alpha}$ 仍然覆盖 $F$。于是 $\{ G_{\alpha} \}$ 含有 $F$ 的有限子覆盖，故 $F$ 紧致。

## Corollary 2.36

在度量空间中，如果 $F$ 是闭集，$K$ 是紧致集，那么 $F\cap K$ 紧致。

### Proof

根据 [[#Theorem 2.34]]，$K$ 是闭集，因此 $F\cap K$ 闭。再由 [[#Theorem 2.35]]，$F\cap K\subset K$ 是紧致集。

## Theorem 2.37

设 $\{ K_{\alpha} \}$ 是度量空间 $X$ 中的一族紧致集，使得任意有限个 $K_{\alpha}$ 的交集非空，那么 $\bigcap_{\alpha}K_{\alpha}\neq \varnothing$。

### Proof

固定 $K_{1} \in \{ K_{\alpha} \}$，令 $G_{\alpha}=K_{\alpha}^{c}$。假设 $K_{1}$ 中的每个点都不属于所有 $K_{\alpha}$，则 $\bigcap K_{\alpha}=\varnothing$，此时我们有 $\bigcup G_{\alpha}=X$ 覆盖 $K_{1}$，因此存在有限子覆盖 $K_{1}\subset G_{\alpha_{1}}\cup\dots \cup G_{\alpha_{n}}$，但这表明

$$
\begin{gather}
K_{1}\cap K_{\alpha_{1}}\cap\dots \cap K_{\alpha_{n}}=\varnothing
\end{gather}
$$

与有限交性质矛盾。

## Corollary 2.38 (紧致套定理)

设 $\{ K_{n} \}$ 是一列非空紧致集，满足 $K_{n}\supset K_{n+1}$ 对任意 $n \in \mathbb{N}^{*}$ 成立，则 $\bigcap_{n=1}^{\infty}K_{n}\neq \varnothing$。

## Theorem 2.39

如果 $E$ 是紧致集 $K$ 的无限子集，那么 $E$ 在 $K$ 中存在极限点。

### Proof

如果 $K$ 中的点都不是 $E$ 的极限点，那么对每个 $q \in K$ 我们都可以找到一个邻域 $V_{q}$ 其只包含有限个 $E$ 中的点。因此，开覆盖 $\{ V_{q} \}$ 的任意有限子集都无法覆盖 $E$，从而无法覆盖 $K$，这与 $K$ 的紧致性矛盾。

## Theorem 2.40

设 $\{ I_{n} \}$ 是 $\mathbb{R}$ 中的一列闭区间，使得 $I_{n}\supset I_{n+1}$ 对任意 $n \in \mathbb{N}^{*}$ 成立，则 $\bigcap_{n=1}^{\infty}I_{n}\neq \varnothing$。

### Proof

设 $I_{n}=[a_{n},b_{n}]$，$E=\{ a_{n} : n\in \mathbb{N}^{*} \}$，则 $E$ 非空且有上界，从而有 $x=\sup E$。设 $m,n \in \mathbb{N}^{*}$，则

$$
\begin{gather}
a_{n}\leq a_{m+n}\leq b_{m+n}\leq b_{m}
\end{gather}
$$

这表明 $x\leq b_{m}$ 对任意 $m$ 成立。显然我们也有 $x\geq a_{n}$，因此 $x \in I_{m}$ 对任意 $m \in \mathbb{N}^{*}$ 成立。

## Theorem 2.41

设 $\{ I_{n} \}$ 是 $\mathbb{R}^{k}$ 中的一列 $k$-cell，使得 $I_{n}\supset I_{n+1}$ 对任意 $n \in \mathbb{N}^{*}$ 成立，则 $\bigcap_{n=1}^{\infty}I_{n}\neq \varnothing$。

### Proof

设

$$
\begin{gather}
I_{n}=[a_{n,1},b_{n,1}]\times\dots \times[a_{n,k},b_{n,k}]=I_{n,1}\times\dots \times I_{n,k}
\end{gather}
$$

对任意 $j$，序列 $\{ I_{n,j} \}$ 满足 [[#Theorem 2.40]] 中的条件，因此有 $x_{j}^{*} \in \bigcap_{n}I_{n,j}$，从而 $\mathbf{x}^{*}=(x_{1}^{*},\dots,x_{k}^{*})$ 属于每个 $I_{n}$。

## Theorem 2.42

每个 $k$-cell 都是紧致的。

### Proof

设 $I=[a_{1},b_{1}]\times\dots \times[a_{k},b_{k}]$ 是一个 $k$-cell，令

$$
\begin{gather}
\delta=\left( \sum_{j=1}^{k} \lvert b_{j}-a_{j} \rvert ^{2} \right)^{1/2}
\end{gather}
$$

则对任意 $\mathbf{x},\mathbf{y}\in I$ 有 $\lvert \mathbf{x}-\mathbf{y} \rvert\leq\delta$。（几何上看，$\delta$ 就是 $k$ 维长方体 $I$ 的对角线长度）

假设存在 $I$ 的开覆盖 $\{ G_{\alpha} \}$ ，其没有有限开覆盖。令 $c_{j}=\frac{1}{2}(a_{j}+b_{j})$，则区间 $[a_{j},c_{j}]$ 和 $[c_{j},b_{j}]$ 共构成了 $I$ 的 $2^{k}$ 个子 $k$-cell，并且其中至少有一个 cell，记作 $I_{1}$，不能被有限个 $G_{\alpha}$ 覆盖。接下来我们分割 $I_{1}$，选出一个更小的 $I_{2}$ 使得它不能被有限个 $G_{\alpha}$ 覆盖，以此类推。

现在，我们得到了一个序列 $\{ I_{n} \}$，满足如下性质：

(a) $I\supset I_{1}\supset I_{2}\supset\cdots$，
(b) $I_{n}$ 不能被有限个 $G_{\alpha}$ 覆盖，
(c) 如果 $\mathbf{x},\mathbf{y}\in I_{n}$，则 $\lvert \mathbf{x}-\mathbf{y} \rvert\leq 2^{-n}\delta$。

根据 (a) 与 [[#Theorem 2.41]]，存在 $\mathbf{x}^{*}\in \bigcap I_{n}$。设 $\mathbf{x}^{*}\in G_{\alpha}$，由于 $G_{\alpha}$ 是开集，存在 $r>0$ 使得 $B(\mathbf{x}^{*},r)\subset G_{\alpha}$，取足够大的 $n$ 使得 $2^{-n}\delta<r$（archimedean 性质保证了这样的 $n$ 存在），则 (c) 表明 $I_{n}\subset G_{\alpha}$，这与性质 (b) 矛盾。

## Theorem 2.43 (Heine-Borel)

设 $E\subset \mathbb{R}^{k}$，则以下命题等价：

1. $E$ 是有界闭集。
2. $E$ 是紧致集。
3. $E$ 的每个无限子集在 $E$ 中都存在极限点。

命题 (1) 和 (2) 的等价性被称为 Heine-Borel 定理。

### Proof

如果 (1) 成立，那么 $E$ 包含于某个 $k$-cell $I$ 中，于是 [[#Theorem 2.42]] 给出了命题 (2)。此外，[[#Theorem 2.39]] 表明 (2) 蕴含 (3)。下面我们只需证明 (3) 蕴含 (1)。

如果 $E$ 不是有界的，那么 $E$ 包含序列 $(\mathbf{x}_{n})$ 满足

$$
\begin{gather}
\lvert \mathbf{x}_{n} \rvert >n \quad (n \in \mathbb{N}^{*})
\end{gather}
$$

显然无限集 $\{ \mathbf{x}_{n} \}$ 在 $E$ 中没有极限点，因此 (3) 表明 $E$ 有界。

如果 $E$ 不是闭集，那么有 $\mathbf{x}_{0}\in \mathbb{R}^{k}$ 使得它是 $E$ 的极限点但不是 $E$ 的元素。取 $\mathbf{x}_{n}\in E$ 使得 $\lvert \mathbf{x}_{n}-\mathbf{x}_{0} \rvert<1 /n$，则集合 $\{ \mathbf{x}_{n} \}$ 的极限点为 $\mathbf{x}_{0}$，且没有其他极限点，因为对 $\mathbf{y}\neq \mathbf{x}_{0}$ 有

$$
\begin{align}
\lvert \mathbf{x}_{n}-\mathbf{y} \rvert &\geq \lvert \mathbf{x}_{0}-\mathbf{y} \rvert -\lvert \mathbf{x}_{n}-\mathbf{x}_{0} \rvert \\
&\geq \lvert \mathbf{x}_{0}-\mathbf{y} \rvert - \frac{1}{n}\geq \frac{1}{2}\lvert \mathbf{x}_{0}-\mathbf{y} \rvert 
\end{align}
$$

对除了有限个以外的 $n$ 都成立，这表明 $\mathbf{y}$ 不是 $\{ \mathbf{x}_{n} \}$ 的极限点。

因此，$\{ \mathbf{x}_{n} \}$ 在 $E$ 中没有极限点，于是 (3) 表明 $E$ 是闭集。

以上定理在一般度量空间中有如下推广。特别地，在一般度量空间中，命题 (2) 和 (3) 仍然等价。

## Theorem 2.44

设 $X$ 是度量空间，则以下命题等价：

1. $X$ 是紧致的。
2. $X$ 的每个无限子集在 $X$ 中都存在极限点。

### Proof

(1) 蕴含 (2) 已由 [[#Theorem 2.39]] 给出，因此我们只需证明 (2) 蕴含 (1)。证明分三步：

**第一步** 任意可分的（存在可数稠密子集）度量空间有可数基。

我们称开集族 $\{ V_{\alpha} \}$ 是 $X$ 的一个基，如果对任意 $x \in X$ 和包含它的开集 $G\subset X$，有 $x \in V_{\alpha}\subset G$。换句话说，任何开集都是 $\{ V_{\alpha} \}$ 的某个子集的并。

设 $X$ 可分，$C$ 为它的可数稠密子集，我们考虑由所有开球

$$
\begin{gather}
B(x,r) \quad (x \in C,r \in \mathbb{Q}_{>0})
\end{gather}
$$

构成的集族，则它是一个可数集。对任意 $x \in X$ 和包含它的开集 $G$，存在开球 $B(x,r)\subset G$。由于 $\mathbb{Q}$ 在 $\mathbb{R}$ 中稠密，因此存在 $r_{1}\in \mathbb{Q}_{>0}$ 使得 $r_{1}<r$。又由于 $C$ 在 $X$ 中稠密，故存在 $x_{1}\in C$ 使得 $d(x,x_{1})<r_{1} /2$，从而 $x \in B(x_{1},r_{1} /2)\subset B(x,r)\subset G$。

**第二步** 设 $X$ 是一个度量空间，其中每个无限子集都有极限点，则 $X$ 是可分的。

固定 $\delta>0$，取 $x_{1}\in X$。假设已取定 $x_{1},\dots,x_{n-1}$，我们取 $x_{n}\in X$ 使得对任意 $1\leq j\leq n-1$ 有 $d(x_{j},x_{n})\geq\delta$，如果没有这样的 $x_{n}$ 则停止。我们来证明，这一过程必然在有限步后停止。假设不然，则我们可得一个序列 $(x_{n})$ 满足任意两个元素之间的距离 $\geq\delta$，这与 $\{ x_{n} \}$ 有极限点矛盾。

以上结论表明：对任意 $\delta>0$，$X$ 可以被有限个半径为 $\delta$ 的开球覆盖。取 $\delta=1 /n$，设这些开球的中心为 $x_{n,1},\dots,x_{n,k_{n}}$，我们令

$$
\begin{gather}
C=\bigcup_{n=1}^{\infty} \{ x_{n,1},\dots,x_{n,k_{n}} \}
\end{gather}
$$

则 $C$ 就是 $X$ 的一个可数稠密子集。

**第三步**

现在我们知道 $X$ 有一个可数基，从而 $X$ 的任意开覆盖 $\{ G_{\alpha} \}$ 都有一个可数子覆盖 $\{ G_{n} \}$。假设 $\{ G_{n} \}$ 的任意有限子集不能覆盖 $X$，则对任意 $n$，

$$
\begin{gather}
F_{n}=(G_{1}\cup\dots \cup G_{n})^{c}\neq \varnothing
\end{gather}
$$

但 $\bigcap_{n=1}^{\infty} F_{n}=\varnothing$。考虑序列 $(x_{n})$，其中 $x_{n}\in F_{n}$，其值域 $\{ x_{n} \}$ 是无限集：因为 $F_{1}\supset F_{2}\supset\cdots$，如果 $\{ x_{n} \}$ 有限，则存在 $n_{1}<n_{2}<\cdots$ 使得 $x_{n_{1}}=x_{n_{2}}=\dots=p$，则 $p \in F_{n_{1}}\cap F_{n_{2}}\cap\cdots=\bigcap F_{n}$，这与 $\bigcap F_{n}=\varnothing$ 矛盾。综上，$\{ x_{n} \}$ 是无限集，从而有极限点 $x$。

由于 $\{ G_{n} \}$ 覆盖 $X$，故存在 $n$ 使得 $x \in G_{n}$，从而有 $B(x,\delta)\subset G_{n}$。根据极限点的性质，$B(x,\delta)$ 中存在无穷个 $\{ x_{n} \}$ 中的点，特别是 $x_{k}$，其中 $k>n$。然而 $x_{k}\in F_{k}=(G_{1}\cup\dots \cup G_{k})^{c}$，即 $x_{k}\not\in G_{n}$，矛盾。因此 $X$ 上存在有限子覆盖，从而紧致。

## Theorem 2.45 (Bolzano-Weierstrass)

$\mathbb{R}^{k}$ 中的无限有界点集在 $\mathbb{R}^{k}$ 中有极限点。

### Proof

设 $E$ 无限且有界，则 $E$ 包含于某个 $k$-cell $I$，从而 $E$ 是紧致集 $I$ 的无限子集，其在 $I$ 中有极限点。

# Perfect Sets 完美集

完美集是每个点都是极限点的闭集。根据定义，极限点的任一邻域都含有集合中无穷多个点，因此完美集的每一点周围都聚集着无穷多个点，这类集合的元素因而极其丰富。

## Theorem 2.46

设 $P\subset \mathbb{R}^{k}$ 是完美集，则 $P$ 是不可数的。

### Proof

由于 $P$ 有极限点，因此 $P$ 是无限集。假设 $P$ 可数，我们将其元素排成一列 $\mathbf{x}_{1},\mathbf{x}_{2},\dots$，构造一列邻域 $\{ V_{n} \}$ 如下：

令 $V_{1}$ 为 $\mathbf{x}_{1}$ 的任意邻域，如果 $V_{1}=B(\mathbf{x}_{1},r)$，那么其闭包 $\overline{V}_{1}$ 就是闭球 $\overline{B}(\mathbf{x}_{1},r)=\{ \mathbf{y} : \lvert \mathbf{x}_{1}-\mathbf{y} \rvert\leq r \}$。

假设已完成 $V_{n}$ 的构造，使得 $V_{n}\cap P$ 非空。由于 $P$ 中的每个点都是极限点，故存在邻域 $V_{n+1}$ 满足：

(i) $\overline{V}_{n+1}\subset V_{n}$，
(ii) $\mathbf{x}_{n}\not\in \overline{V}_{n+1}$，
(iii) $V_{n+1}\cap P$ 非空。

根据 (iii)，$V_{n+1}$ 满足归纳假设，因此上述构造可以继续下去。

令 $K_{n}=\overline{V}_{n}\cap P$，由于 $\overline{V}_{n}$ 闭且有界，从而紧致。由于 $\mathbf{x}_{n}\not\in K_{n+1}$，因此 $\bigcap_{n=1}^{\infty}K_{n}=\varnothing$。然而，根据 (iii)，每个 $K_{n}$ 非空，并且根据 (i)，$K_{n}\supset K_{n+1}$，因此这与 [[#Corollary 2.38 (紧致套定理)]] 矛盾。

## Corollary 2.47

闭区间 $[a,b]\ (a<b)$ 是不可数的。特别地，实数集 $\mathbb{R}$ 是不可数的。

## Example 2.48 Cantor Set

下面我们给出分析学中的经典反例 Cantor 集，它显示了一个集合的拓扑性质与测度性质可以有极大的不同：它是一个具有 Lebesgue 测度零的完美集。

令 $E_{0}=[0,1]$，将其三等分并去掉中间的开区间 $(1 /3,2 /3)$，得到

$$
\begin{gather}
E_{1}=\left[ 0,\frac{1}{3} \right] \cup \left[ \frac{2}{3},1 \right]
\end{gather}
$$

下面，对剩下的两个区间三等分并去掉中间的开区间，得到

$$
\begin{gather}
E_{2}=\left[ 0,\frac{1}{9} \right]\cup \left[ \frac{2}{9},\frac{1}{3} \right]\cup \left[ \frac{2}{3},\frac{7}{9} \right]\cup \left[ \frac{8}{9},1 \right]
\end{gather}
$$

以此类推，我们可得一列集合 $E_{n}$ 满足

(a) $E_{0}\supset E_{1}\supset E_{2}\supset\cdots$，
(b) $E_{n}$ 是 $2^{n}$ 个闭区间的并集，每个区间的长度为 $3^{-n}$。

我们称

$$
\begin{gather}
P=\bigcap_{n=1}^{\infty} E_{n}
\end{gather}
$$

为 Cantor 集。显然 $P$ 是紧致的，且 [[#Corollary 2.38 (紧致套定理)]] 表明 $P$ 非空。

没有形如

$$
\begin{gather}
\left( \frac{3k+1}{3^{m}},\frac{3k+2}{3^{m}} \right) \tag{2.47.1}
\end{gather}
$$

的开区间与 $P$ 相交。事实上，$P$ 不包含任何开区间，因为每个开区间 $(\alpha,\beta)$ 都包含一个形如 $(2.47.1)$ 的区间，其中

$$
\begin{gather}
3^{-m}<\frac{\beta-\alpha}{6}
\end{gather}
$$

要证 $P$ 是完美集，我们只需证明 $P$ 不包含孤立点。设 $x \in P$，$S$ 为任意包含 $x$ 的开区间，$I_{n}$ 为 $E_{n}$ 中所有包含 $x$ 的区间的并集，并取 $n$ 足够大使得 $I_{n}\subset S$。设 $x_{n}$ 是 $I_{n}$ 的一个端点，使得 $x_{n}\neq x$。

根据 $P$ 的定义，$x_{n}\in P$，因此 $x$ 是 $P$ 的极限点，且 $P$ 是完美集。

# Connected Sets 连通集

## Definition 2.49 separated 分离的，connected 连通的

称度量空间 $X$ 的两个子集 $A,B$ 是分离的，如果 $A\cap \overline{B}=\varnothing$ 且 $\overline{A}\cap B=\varnothing$。一个集合 $E\subset X$ 称为是连通的，如果它不是两个非空分离集的并。

## Theorem 2.50

$E\subset \mathbb{R}$ 是连通集当且仅当它具有性质：如果 $x,y \in E$ 且 $x<z<y$，那么 $z \in E$。

容易验证，$\mathbb{R}$ 上的单个区间（如闭区间 $[a,b]$）满足上面所说的性质，因而是连通集。

### Proof

如果存在 $x,y \in E$ 以及 $x<z<y$ 使得 $z \not\in E$，那么 $E$ 可以写成 $A_{z}\cup B_{z}$，其中

$$
\begin{gather}
A_{z}=E\cap(-\infty,z), \quad B_{z}=E\cap(z,\infty)
\end{gather}
$$

由于 $x \in A_{z},y \in B_{z}$，两个集合非空。又由于 $(-\infty,z)$ 和 $(z,\infty)$ 分离，从而 $A_{z}$ 和 $B_{z}$ 也是分离的，因此 $E$ 不连通。

反之，假设 $E$ 不连通，则存在非空分离集 $A,B$ 使得 $E=A\cup B$。取 $x \in A,y \in B$，并不失一般性地假设 $x<y$，定义

$$
\begin{gather}
z=\sup(A\cap [x,y])
\end{gather}
$$

则 [[#Theorem 2.28]] 表明 $z \in \overline{A}$，因此 $z \not\in B$，从而 $x\leq z<y$。

如果 $z \not\in A$，那么 $x<z<y$ 且 $z \not\in E$。

如果 $z \in A$，那么 $z\not\in \overline{B}$，因此存在 $z_{1}$ 使得 $z<z_{1}<y$ 且 $z_{1}\not\in B$，则 $x<z_{1}<y$ 且 $z_{1}\not\in E$。

## Remark 2.51

在其他分析教材中连通性的标准定义为：$E\subset X$ 连通当且仅当 $E$ 不能写成两个非空、相对于 $E$ 开、且不相交的集合的并。我们来证明这两个定义是等价的。

设 $E=A\cup B$，其中 $A,B$ 是非空分离集。由于 $A=E\cap \overline{A}$，因此 $A$ 相对于 $E$ 是闭集，从而 $B=E\setminus A$ 相对于 $E$ 是开集。同理 $A$ 相对于 $E$ 是开集，$B$ 相对于 $E$ 是闭集。这表明 $E$ 可以写成两个非空相对开集的不交并。

反之，设 $E=A\cup B$，其中 $A,B$ 是不交的相对开集。根据上一段论证，$A,B$ 也是相对于 $E$ 的闭集，从而存在 $X$ 中的闭集 $F$ 使得 $A=E\cap F$，从而 $\overline{A}\subset F$，且

$$
\begin{gather}
\overline{A}\cap B\subset F\cap B=F\cap E\cap B=A\cap B=\varnothing
\end{gather}
$$

同理也有 $A\cap \overline{B}=\varnothing$，从而 $A,B$ 是不交的分离集。

使用 [[#Definition 2.49 separated 分离的，connected 连通的]] 的优点是，我们无需考虑集合的相对开性，并直接得到了连通性的环境空间无关性。这也与我们的直觉相符：连通性应当是集合内蕴的性质，而与周围的空间无关。