# Convergent Sequences 收敛序列

## Definition 3.1 converge 收敛，limit 极限，diverge 发散

设 $X$ 是度量空间，$d$ 是 $X$ 上的度量。称 $X$ 上的序列 $(p_{n})$ 收敛，如果存在 $p \in X$ 满足以下性质：对任意 $\varepsilon>0$，存在 $N \in \mathbb{N}^{*}$ 使得 $n\geq N$ 蕴含 $d(p_{n},p)<\varepsilon$。

此时我们称 $(p_{n})$ 收敛于 $p$，或称 $p$ 是 $(p_{n})$ 的极限，记作 $p_{n}\to p$ 或

$$
\begin{gather}
\lim_{ n \to \infty } p_{n}=p
\end{gather}
$$

如果 $(p_{n})$ 不收敛，则称该序列发散。

注意，上面的收敛性概念不仅与 $(p_{n})$ 有关，还与空间 $X$ 有关。例如序列 $(1 /n)$ 在 $\mathbb{R}$ 中收敛到 $0$，但其在正实数集 $\mathbb{R}^{+}$ 上发散。在需要区分空间的情况下，我们会说“在 $X$ 中收敛”。

一个序列 $(p_{n})$ 的值域 $\{ p_{n} \}$ 是一个集合。我们称 $(p_{n})$ 有界，如果其值域是有界的。

### Motivation

上面的 $\varepsilon-N$ 定义是对极限的直观“要多接近有多接近”的严格化。

我们可以将其视为一种博弈过程：玩家 $1$ 先手给出一个误差上界 $\varepsilon>0$，玩家 $2$ 的目标是给出一个起点 $N$，使得 $p_{N},p_{N+1},\dots$ 全部落在 $p$ 的 $\varepsilon$-邻域内。

如果玩家 $2$ 有必胜策略，也就是说无论玩家 $1$ 提出什么要求，玩家 $2$ 总能找到一个对应的 $N$，那么我们就说 $p_{n}\to p$。

反之，如果玩家 $1$ 有必胜策略，即玩家 $1$ 可以找到一个 $\varepsilon_{0}>0$，使得玩家 $2$ 无论取什么 $N$，都有 $n\geq N$ 使得 $p_{n}$ 在 $p$ 的 $\varepsilon_{0}$-邻域之外。这正是 $p_{n} \not\to p$ 的定义。

## Theorem 3.2

设 $(p_{n})$ 是度量空间 $X$ 中的序列，则

1. $(p_{n})$ 收敛于 $p \in X$ 当且仅当 $p$ 的任意邻域都包含除了有限个点以外的所有 $p_{n}$。
2. 如果 $(p_{n})$ 收敛于 $p \in X$ 和 $p' \in X$，那么 $p=p'$。
3. 如果 $(p_{n})$ 收敛，那么 $(p_{n})$ 有界。
4. 如果 $p$ 是 $E\subset X$ 的极限点，那么存在 $E$ 中的序列 $(p_{n})$ 使得 $p_{n}\to p$。

命题 (2) 表明极限是唯一的。命题 (4) 解释了“极限点”名字的来源。

### Proof

(1) 设 $p_{n}\to p$，$V$ 是 $p$ 的任意邻域。则存在 $\varepsilon>0$ 使得 $V=B(p,\varepsilon)$，于是存在 $N$ 使得 $n\geq N$ 蕴含 $d(p_{n},p)<\varepsilon$，即 $p_{n}\in V$。

反之，任取 $\varepsilon>0$，取 $p$ 的邻域 $V=B(p,\varepsilon)$，则 $V$ 包含了除有限个点外的所有 $p_{n}$，这就是说存在 $N$ 使得 $n\geq N$ 蕴含 $p_{n}\in B(p,\varepsilon)$，从而 $p_{n}\to p$。

(2) 对任意 $\varepsilon>0$，存在 $N_{1},N_{2}$，使得

$$
\begin{gather}
n\geq N_{1}\implies d(p_{n},p)<\varepsilon \\
n\geq N_{2}\implies d(p_{n},p')<\varepsilon
\end{gather}
$$

于是当 $n\geq \max(N_{1},N_{2})$ 时，成立

$$
\begin{gather}
d(p,p')\leq d(p,p_{n})+d(p_{n},p')<2\varepsilon
\end{gather}
$$

由于 $\varepsilon$ 是任意的，因此 $p=p'$。（否则令 $2\varepsilon=\frac{1}{2}d(p,p')$ 将得到矛盾）

(3) 设 $p_{n}\to p$，取 $\varepsilon=1$，则存在 $N$ 使得 $n\geq N$ 蕴含 $d(p_{n},p)<1$。令

$$
\begin{gather}
r=\max \{ 1,d(p_{1},p),\dots,d(p_{N},p) \}
\end{gather}
$$

则 $d(p_{n},p)\leq r$ 对任意 $n \in \mathbb{N}^{*}$ 成立。

(4) 如果 $p$ 是 $E$ 的极限点，那么任意邻域 $B(p,1 /n)$ 与 $E$ 的交集均非空，取 $p_{n}\in B(p,1 /n)\cap E$，则 $d(p_{n},p)<1 /n$，从而 $(p_{n})$ 是 $E$ 中的序列，且收敛于 $p$。

如果度量空间 $X$ 上还有向量空间或者域结构，我们可以证明 $X$ 上的代数运算与极限运算一致。

## Theorem 3.3

设 $(s_{n}),(t_{n})$ 是复数序列，且 $\lim_{ n \to \infty }s_{n}=s$，$\lim_{ n \to \infty }t_{n}=t$，则

1. $\lim_{ n \to \infty }(s_{n}+t_{n})=s+t$，
2. 对任意 $c \in \mathbb{C}$ 有 $\lim_{ n \to \infty }cs_{n}=cs$，
3. $\lim_{ n \to \infty }s_{n}t_{n}=st$，
4. 如果 $s_{n}\neq 0$ 且 $s\neq 0$，那么 $\lim_{ n \to \infty }s_{n}^{-1}=s^{-1}$。

### Proof

(1) 给定 $\varepsilon>0$，取 $N_{1},N_{2}$ 使得

$$
\begin{gather}
n\geq N_{1} \implies \lvert s_{n}-s \rvert < \frac{\varepsilon}{2} \\
n\geq N_{2} \implies \lvert t_{n}-t \rvert <\frac{\varepsilon}{2}
\end{gather}
$$

则当 $n\geq \max(N_{1},N_{2})$ 时，有

$$
\begin{gather}
\lvert (s_{n}+t_{n})-(s+t) \rvert \leq\lvert s_{n}-s \rvert +\lvert t_{n}-t \rvert <\varepsilon
\end{gather}
$$

即证 $\lim_{ n \to \infty }(s_{n}+t_{n})=s+t$。命题 (2) 的证明是平凡的。

(3) 我们使用恒等式

$$
\begin{align}
\lvert s_{n}t_{n}-st \rvert &=\lvert s_{n}(t_{n}-t)+t(s_{n}-s) \rvert \\
&\leq \lvert s_{n} \rvert \lvert t_{n}-t \rvert +\lvert t \rvert \lvert s_{n}-s \rvert 
\end{align}
$$

由于 $(s_{n})$ 收敛，故存在 $M>0$ 使得对任意 $n$ 有 $\lvert s_{n} \rvert\leq M$。给定 $\varepsilon>0$，取 $N_{1},N_{2}$ 使得

$$
\begin{gather}
n\geq N_{1}\implies \lvert s_{n}-s \rvert <\varepsilon \\
n\geq N_{2} \implies \lvert t_{n}-t \rvert <\varepsilon
\end{gather}
$$

于是当 $n\geq \max(N_{1},N_{2})$ 时有

$$
\begin{gather}
\lvert s_{n}t_{n}-st \rvert < (M+\lvert t \rvert )\varepsilon
\end{gather}
$$

根据 $\varepsilon$ 的任意性，我们可将 $\varepsilon$ 替换为 $\frac{\varepsilon}{M+\lvert t \rvert}$，即证 $s_{n}t_{n}\to st$。

(4) 我们使用恒等式

$$
\begin{gather}
\left\lvert  \frac{1}{s_{n}}-\frac{1}{s}  \right\rvert =\left\lvert  \frac{s_{n}-s}{s_{n}s}  \right\rvert 
\end{gather}
$$

取 $m$ 使得 $n\geq m$ 蕴含 $\lvert s_{n}-s \rvert<\frac{1}{2}\lvert s \rvert$，则对 $n\geq m$ 有

$$
\begin{gather}
\lvert s_{n} \rvert > \frac{1}{2}\lvert s \rvert 
\end{gather}
$$

再取 $N$ 使得 $n\geq N$ 蕴含 $\lvert s_{n}-s \rvert<\varepsilon$，从而当 $n\geq \max(m,N)$ 时，

$$
\begin{gather}
\left\lvert  \frac{1}{s_{n}}-\frac{1}{s}  \right\rvert < \frac{2}{\lvert s \rvert ^{2}}\lvert s_{n}-s \rvert <\frac{2}{\lvert s \rvert ^{2}}\varepsilon
\end{gather}
$$

根据 $\varepsilon$ 的任意性即证 $s_{n}^{-1}\to s^{-1}$。

## Theorem 3.4

(a) 设 $\mathbf{x}_{n}=(\alpha_{1,n},\dots,\alpha_{k,n})\in \mathbb{R}^{k}$，则 $(\mathbf{x}_{n})$ 收敛于 $\mathbf{x}=(\alpha_{1},\dots,\alpha_{k})$ 当且仅当对任意 $1\leq j\leq k$ 有 $\lim_{ n \to \infty }\alpha_{j,n}=\alpha_{j}$。

(b) 设 $(\mathbf{x}_{n}),(\mathbf{y}_{n})$ 是 $\mathbb{R}^{k}$ 中的序列，$(\beta_{n})$ 是一列实数，满足 $\mathbf{x}_{n}\to \mathbf{x}$，$\mathbf{y}_{n}\to \mathbf{y}$，$\beta_{n}\to\beta$，则

$$
\begin{gather}
\lim_{ n \to \infty } (\mathbf{x}_{n}+\mathbf{y}_{n})=\mathbf{x}+\mathbf{y}, \quad \lim_{ n \to \infty } (\mathbf{x}_{n}\cdot \mathbf{y_{n}})=\mathbf{x}\cdot \mathbf{y}, \quad \lim_{ n \to \infty } (\beta_{n}\mathbf{x}_{n})=\beta \mathbf{x}
\end{gather}
$$

### Proof

(a) 如果 $\mathbf{x}_{n}\to \mathbf{x}$，则根据不等式

$$
\begin{gather}
\lvert \alpha_{j,n}-\alpha_{j} \rvert \leq \lvert \mathbf{x}_{n}-\mathbf{x} \rvert 
\end{gather}
$$

可知对任意 $j$ 有 $\alpha_{j,n}\to\alpha_{j}$。

反之，如果 $\alpha_{j,n}\to\alpha_{j}$，那么任取 $\varepsilon>0$，存在 $N_{j}$ 使得

$$
\begin{gather}
n\geq N_{j} \implies \lvert \alpha_{j,n}-\alpha_{j} \rvert <\varepsilon
\end{gather}
$$

当 $n\geq \max(N_{1},\dots,N_{k})$ 时，有

$$
\begin{align}
\lvert \mathbf{x}_{n}-\mathbf{x} \rvert = \left( \sum_{j=1}^{k} \lvert \alpha_{j,n}-\alpha_{j} \rvert ^{2} \right)^{1/2}<\sqrt{ k } \varepsilon
\end{align}
$$

这就完成了证明。命题 (b) 由 (a) 以及 [[#Theorem 3.3]] 给出。

# Subsequences 子序列

## Definition 3.5 subsequence 子序列，subsequential limit 子列极限

给定序列 $(p_{n})$，对任意满足 $n_{1}<n_{2}<n_{3}<\cdots$ 的正整数序列 $(n_{k})$，序列 $(p_{n_{k}})$ 称为 $(p_{n})$ 的一个子序列。如果 $(p_{n_{k}})$ 收敛，则称其极限为 $(p_{n})$ 的一个子列极限。

## Proposition 3.6

序列 $(p_{n})$ 收敛于 $p$ 当且仅当 $(p_{n})$ 的所有子序列都收敛于 $p$。

### Proof

首先，序列自身也是它的一个子序列，因此子序列收敛蕴含 $p_{n}\to p$。反之，如果 $p_{n}\to p$，则对任意 $\varepsilon>0$，存在 $N$ 使得

$$
\begin{gather}
n\geq N \implies d(p_{n},p)<\varepsilon
\end{gather}
$$

对任意子序列 $(p_{n_{k}})$，由于 $n_{k}\geq k$ 对任意 $k$ 成立，因此当 $k\geq N$ 时，我们有 $n_{k}\geq N$，从而 $d(p_{n_{k}},p)<\varepsilon$，即证 $p_{n_{k}}\to p$。

## Theorem 3.7

(a) 如果 $(p_{n})$ 是紧致度量空间 $X$ 中的序列，则存在 $(p_{n})$ 的子序列收敛于 $X$ 中的一个点。
(b) 任何 $\mathbb{R}^{k}$ 中的有界序列都包含一个收敛的子序列。

满足 (a) 中的子序列性质的空间 $X$ 称为是列紧的。在度量空间中，紧致性与列紧性是等价的。

### Proof

(a) 设 $E$ 为 $(p_{n})$ 的值域。如果 $E$ 是有限集，那么存在 $p \in E$ 以及无穷个 $n_{1}<n_{2}<\cdots$ 使得

$$
\begin{gather}
p_{n_{1}}=p_{n_{2}}=\dots=p
\end{gather}
$$

于是子序列 $(p_{n_{k}})$ 收敛于 $p$。

如果 $E$ 是无限集，则 [[2 Basic Topology#Theorem 2.44]] 表明 $E$ 在 $X$ 中有极限点 $p \in X$。取 $n_{1}$ 使得 $d(p_{n_{1}},p)<1$。假设已取定 $n_{1},\dots,n_{k-1}$，我们取 $n_{k}>n_{k-1}$ 使得 $d(p_{n_{k}},p)<1 /k$。则子序列 $(p_{n_{k}})$ 收敛于 $p$。

(b) 由 (a) 以及 Heine-Borel 定理给出，因为 $\mathbb{R}^{k}$ 中的有界集总包含在某个紧致集中。

## Theorem 3.8

序列 $(p_{n})$ 的所有子列极限构成了 $X$ 中的一个闭集。

### Proof

设 $E^{*}$ 是所有子列极限构成的集合，$q$ 是它的一个极限点。我们要证 $q \in E^{*}$。

取 $n_{1}$ 使得 $p_{n_{1}}\neq q$。（如果没有这样的 $n_{1}$ 存在，那么 $E^{*}$ 只有一个点，从而结论是平凡的。）令 $\delta=d(p_{n_{1}},q)$，假设已选取 $n_{1},\dots,n_{k-1}$，由于 $q$ 是极限点，因此存在 $x \in E^{*}$ 使得 $d(x,q)<2^{-k}\delta$，从而可以取 $n_{k}>n_{k-1}$ 使得 $d(x,p_{n_{k}})<2^{-k}\delta$，于是

$$
\begin{gather}
d(p_{n_{k}},q)\leq d(p_{n_{k}},x)+d(x,q)<2^{1-k}\delta
\end{gather}
$$

即证 $p_{n_{k}}\to q$，故 $q \in E^{*}$。

# Cauchy Sequences 柯西序列

## Definition 3.9 Cauchy sequence 柯西序列

称度量空间 $X$ 中的序列 $(p_{n})$ 是一个 Cauchy 序列，如果对任意 $\varepsilon>0$，存在 $N \in \mathbb{N}^{*}$ 使得 $n,m\geq N$ 蕴含 $d(p_{n},p_{m})<\varepsilon$。

对 Cauchy 序列的一个直观描述是，当 $n$ 足够大时，$p_{n}$ 及其之后的项将极为紧密地聚集在一起。

## Definition 3.10 diameter 直径

设 $X$ 是度量空间，$E\subset X$ 非空，定义 $E$ 的直径为

$$
\begin{gather}
\operatorname{diam} E=\sup \{ d(p,q) : p,q \in E \}
\end{gather}
$$

## Proposition 3.11

设 $(p_{n})$ 是度量空间 $X$ 中的序列，$E_{N}=\{ p_{N},p_{N+1},p_{N+2},\dots \}$，则 $(p_{n})$ 是 Cauchy 序列当且仅当

$$
\begin{gather}
\lim_{ N \to \infty } \operatorname{diam} E_{N}=0
\end{gather}
$$

### Proof

如果 $(p_{n})$ 是 Cauchy 的，那么存在 $N$ 使得 $n,m\geq N$ 蕴含 $d(p_{n},p_{m})<\varepsilon$，从而

$$
\begin{gather}
\operatorname{diam} E_{N+p}\leq \operatorname{diam}E_{N}=\sup_{n,m\geq N} d(p_{n},p_{m})\leq\varepsilon
\end{gather}
$$

对任意 $p \in \mathbb{N}$ 成立，即证 $\operatorname{diam}E_{N}\to 0$。

反之，如果 $\operatorname{diam}E_{N}\to 0$，则存在 $N$ 使得 $\operatorname{diam}E_{N}<\varepsilon$，因此对 $n,m\geq N$ 有 $d(p_{n},p_{m})\leq \operatorname{diam}E_{N}<\varepsilon$，故 $(p_{n})$ 是 Cauchy 的。

## Theorem 3.12

(a) 设 $\overline{E}$ 是 $E\subset X$ 的闭包，则

$$
\begin{gather}
\operatorname{diam}\overline{E}=\operatorname{diam}E
\end{gather}
$$

(b) 如果 $\{ K_{n} \}$ 是 $X$ 中的非空紧致集，使得 $K_{n}\supset K_{n+1}$ 对任意 $n \in \mathbb{N}^{*}$ 成立，并且 $\operatorname{diam}K_{n}\to 0$，则 $\bigcap_{n=1}^{\infty}K_{n}$ 恰有一个元素。

### Proof

(a) 由于 $E\subset \overline{E}$，故显然有

$$
\begin{gather}
\operatorname{diam}E\leq \operatorname{diam}\overline{E}
\end{gather}
$$

固定 $\varepsilon>0$，取 $p,q \in \overline{E}$，则存在 $p',q' \in E$ 使得 $d(p,p')<\varepsilon$ 且 $d(q,q')<\varepsilon$，于是

$$
\begin{align}
d(p,q) &\leq d(p,p')+d(p',q')+d(q,q') \\
&< 2\varepsilon+d(p',q')\leq 2\varepsilon+\operatorname{diam}E
\end{align}
$$

故 $\operatorname{diam}\overline{E}\leq 2\varepsilon+\operatorname{diam}E$，根据 $\varepsilon$ 的任意性即证 $\operatorname{diam}\overline{E}\leq \operatorname{diam}E$。

(b) 根据 [[2 Basic Topology#Corollary 2.38 (紧致套定理)]]，$K=\bigcap K_{n}$ 非空。如果 $K$ 包含两个元素，那么 $\operatorname{diam}K>0$，但 $\operatorname{diam}K\leq \operatorname{diam}K_{n}$ 对任意 $n$ 成立，这与 $\operatorname{diam}K_{n}\to 0$ 矛盾。因此 $K$ 最多包含一个元素。

## Theorem 3.13 (Cauchy 准则)

(a) 在任意度量空间 $X$ 中，收敛序列是 Cauchy 序列。
(b) 如果 $X$ 是紧致度量空间，$(p_{n})$ 是 $X$ 中的 Cauchy 序列，那么 $(p_{n})$ 收敛于 $X$ 中的某个点。
(c) 在 $\mathbb{R}^{k}$ 中，任何 Cauchy 序列都收敛。

在 $\mathbb{R}^{k}$ 上，一个序列收敛当且仅当它是 Cauchy 序列的这一性质被称为 Cauchy 准则。它允许我们在未得知极限是什么的情况下判断一个序列的收敛性。

### Proof

(a) 如果 $p_{n}\to p$，任取 $\varepsilon>0$，存在 $N$ 使得 $n\geq N$ 蕴含 $d(p_{n},p)<\varepsilon$，于是当 $n,m\geq N$ 时有

$$
\begin{gather}
d(p_{n},p_{m})\leq d(p_{n},p)+d(p_{m},p)<2\varepsilon
\end{gather}
$$

因此 $(p_{n})$ 是 Cauchy 序列。

(b) 设 $(p_{n})$ 是紧致度量空间 $X$ 中的 Cauchy 序列。令 $E_{N}=\{ p_{N},p_{N+1},p_{N+2},\dots \}$，则

$$
\begin{gather}
\lim_{ N \to \infty } \operatorname{diam} \overline{E}_{N}=0
\end{gather}
$$

$\overline{E}_{N}$ 是 $X$ 中的闭集，因而紧致。此外，$\overline{E}_{N}\supset \overline{E}_{N+1}$，故 [[#Theorem 3.12]] 表明存在唯一的 $p \in \bigcap \overline{E}_{N}$。

给定 $\varepsilon>0$，则存在 $N$ 使得 $\operatorname{diam}\overline{E}_{N}<\varepsilon$。由于 $p \in \overline{E}_{N}$，故对任意 $n\geq N$ 有 $d(p,p_{n})\leq \operatorname{diam}\overline{E}_{N}<\varepsilon$，这正是 $p_{n}\to p$ 的定义。

(c) 我们来证明任何 Cauchy 序列都有界，从而根据 Heine-Borel 定理以及 (b) 即证。

取 $\varepsilon=1$，存在 $N$ 使得 $n\geq N$ 蕴含 $d(p_{n},p_{N})<1$，取

$$
\begin{gather}
M=\max \{ d(p_{1},p_{N}),\dots,d(p_{N-1},p_{N}),1 \}
\end{gather}
$$

则对任意 $n$ 有 $d(p_{n},p_{N})\leq M$。

## Definition 3.14 complete 完备的

如果一个度量空间上的任意 Cauchy 序列都收敛，则称该度量空间是完备的。

于是，[[#Theorem 3.13 (Cauchy criterion)]] 表明，所有紧致度量空间和所有 euclidean 空间都是完备的。此外，我们还可知完备度量空间 $X$ 的闭子集 $E$ 是完备的：$E$ 中的 Cauchy 序列也是 $X$ 中的 Cauchy 序列，从而收敛；又因为 $E$ 是闭集，因此其极限落在 $E$ 中，从而 $E$ 是完备的。

一个不完备的度量空间例子是有理数 $\mathbb{Q}$，这也是我们定义实数集 $\mathbb{R}$ 的原因之一。

## Definition 3.15 monotonically increasing (decreasing) 单调递增（递减）

称一列实数 $(s_{n})$ 是

1. 单调递增的，如果对任意 $n \in \mathbb{N}^{*}$ 有 $s_{n}\leq s_{n+1}$。
2. 单调递减的，如果对任意 $n \in \mathbb{N}^{*}$ 有 $s_{n}\geq s_{n+1}$。

单调递增与单调递减序列合称为单调序列。

## Theorem 3.16 (单调有界原理)

设 $(s_{n})$ 单调递增（或递减），则 $(s_{n})$ 收敛当且仅当 $(s_{n})$ 有上界（或下界）。

### Proof

假设 $(s_{n})$ 单调递增。设 $E$ 是 $(s_{n})$ 的值域，如果 $E$ 有上界，则存在 $s=\sup E$，从而对任意 $\varepsilon>0$，存在 $n$ 使得

$$
\begin{gather}
s-\varepsilon<s_{n}\leq s_{n+p}\leq s
\end{gather}
$$

对任意 $p \in \mathbb{N}$ 成立。即证 $s_{n}\to s$。反之，根据 [[#Theorem 3.2]](3)，$(s_{n})$ 有界。

单调递减的情况同理。

# Upper and Lower Limits 上极限与下极限

## Definition 3.17

设 $(s_{n})$ 是一列实数，满足性质：对任意 $M>0$，存在 $N$ 使得 $n\geq N$ 蕴含 $s_{n}\geq M$，则我们定义

$$
\begin{gather}
\lim_{ n \to \infty } s_{n}=+\infty
\end{gather}
$$

类似地，如果 $(s_{n})$ 满足性质：对任意 $M>0$，存在 $N$ 使得 $n\geq N$ 蕴含 $s_{n}\leq-M$，则我们定义

$$
\begin{gather}
\lim_{ n \to \infty } s_{n}=-\infty
\end{gather}
$$

需要注意，尽管我们使用了极限符号，但上面定义的极限为无穷的情况仍然属于发散的实数序列。

## Definition 3.18 upper limit 上极限，lower limit 下极限

设 $(s_{n})$ 是一列实数，$E$ 为 $(s_{n})$ 在扩展实数系中的子列极限构成的集合（即 $(s_{n})$ 的一般子列极限加上可能存在的 $\pm \infty$），定义

$$
\begin{gather}
s^{*}=\sup E, \quad s_{*}=\inf E
\end{gather}
$$

分别称为 $(s_{n})$ 的上极限与下极限，记作

$$
\begin{gather}
\limsup_{ n \to \infty } s_{n}=s^{*}, \quad \liminf_{ n \to \infty } s_{n}=s_{*}
\end{gather}
$$

## Theorem 3.19

设 $(s_{n})$ 是一列实数，$E$ 和 $s^{*}$ 如 [[#Definition 3.18 upper limit 上极限，lower limit 下极限]] 中所示，则 $s^{*}$ 是唯一满足以下性质的数：

1. $s^{*}\in E$，
2. 如果 $x>s^{*}$，则存在 $N$ 使得 $n\geq N$ 蕴含 $s_{n}<x$。

同理，$s_{*}$ 是唯一满足以下性质的数：

1. $s_{*}\in E$，
2. 如果 $x<s_{*}$，则存在 $N$ 使得 $n\geq N$ 蕴含 $s_{n}>x$。

### Proof

我们只证明上极限的部分。

(1) 如果 $s^{*}=+\infty$，则 $E$ 无上界，从而 $(s_{n})$ 无上界，于是有子序列 $s_{n_{k}}\to +\infty$。

如果 $s^{*}\in \mathbb{R}$，则 $E$ 非空有上界。根据 [[#Theorem 3.8]]，$E$ 是一个闭集，从而其包含 $s^{*}=\sup E$。

如果 $s^{*}=-\infty$，则 $E$ 仅有一个元素 $-\infty$，于是对任意 $M \in \mathbb{R}$，只有有限个 $n$ 满足 $s_{n}>M$，即证 $s_{n}\to -\infty$。

(2) 假设存在 $x>s^{*}$ 使得 $s_{n}\geq x$ 对无穷多个 $n$ 成立，则将有 $y \in E$ 使得 $y\geq x>s^{*}$，但这与 $s^{*}$ 的定义矛盾。

最后我们来证明唯一性。假设有 $p,q$ 满足性质 (1)(2)，且 $p<q$，选取 $p<x<q$，则存在 $N$ 使得 $n\geq N$ 蕴含 $s_{n}<x$，这与 $q \in E$ 矛盾。

利用以上定理，我们可以给出上下极限的一个计算公式。

## Theorem 3.20

设 $(s_{n})$ 是一列实数，则

$$
\begin{gather}
\limsup_{ n \to \infty } s_{n}=\lim_{ n \to \infty } \sup_{k\geq n} s_{k}, \quad \liminf_{ n \to \infty } s_{n}=\lim_{ n \to \infty } \inf_{k\geq n} s_{k}
\end{gather}
$$

其中我们定义 $\lim_{ n \to \infty }(+\infty)=+\infty$，$\lim_{ n \to \infty }(-\infty)=-\infty$。

### Proof

我们只需证明 $\overline{s}=\lim_{ n \to \infty }\sup_{k\geq n}s_{k}$ 满足 [[#Theorem 3.19]] 的性质 (1)(2)。下极限的证明同理。

(1) 如果 $\overline{s}=+\infty$，由于 $\sup_{k\geq n}s_{k}$ 是单调递减的，因此要使 $\overline{s}=+\infty$，就必然有 $\sup_{k\geq n}s_{k}=+\infty$ 恒成立。这表明 $(s_{n})$ 无上界，从而 $\overline{s} \in E$。

如果 $\overline{s} \in \mathbb{R}$，构造序列 $(n_{m})$ 如下：

令 $\varepsilon=1 /m$，则存在 $N_{m}$ 使得 $n\geq N_{m}$ 蕴含

$$
\begin{gather}
\overline{s}\leq \sup_{k\geq N_{m}}s_{k}<\overline{s}+1 /m
\end{gather}
$$

取 $n_{m}\geq N_{m}$ 且 $n_{m}>n_{m-1}$，使得

$$
\begin{gather}
\sup_{k\geq N_{m}} s_{k}-1 /m < s_{n_{m}}\leq \sup_{k\geq N_{m}} s_{k}
\end{gather}
$$

则我们有

$$
\begin{gather}
\lvert s_{n_{m}}-\overline{s} \rvert < \frac{1}{m}
\end{gather}
$$

即证 $s_{n_{m}}\to \overline{s}$。

如果 $\overline{s}=-\infty$，这表明对任意 $M$，满足 $s_{n}>M$ 的 $n$ 只有有限个，从而 $s_{n}\to -\infty$。

(2) 如果 $x>\overline{s}$，当 $x=+\infty$ 时结论是平凡的。设 $x \in \mathbb{R}$，则存在 $N$ 使得 $n\geq N$ 蕴含

$$
\begin{gather}
\lvert \sup_{k\geq n} s_{k}-\overline{s} \rvert < \frac{x-\overline{s}}{2}
\end{gather}
$$

从而

$$
\begin{gather}
s_{n}\leq \sup_{k\geq N} s_{k} < \frac{x+\overline{s}}{2}<x
\end{gather}
$$

根据 [[#Theorem 3.19]] 的唯一性部分即证。

## Theorem 3.21

设 $(s_{n}),(t_{n})$ 是实数序列，则

1. $\lim_{ n \to \infty }s_{n}=s$ 当且仅当 $\limsup_{ n \to \infty }s_{n}=\liminf_{ n \to \infty }s_{n}=s$。
2. 如果存在 $N$ 使得对 $n\geq N$ 有 $s_{n}\leq t_{n}$，则
$$
\begin{gather}
\liminf_{ n \to \infty } s_{n}\leq \liminf_{ n \to \infty } t_{n} \\
\limsup_{ n \to \infty } s_{n}\leq \limsup_{ n \to \infty } t_{n}
\end{gather}
$$

### Proof

(1) 由 [[#Theorem 3.20]] 直接给出，其中的关键不等式为

$$
\begin{gather}
s-\varepsilon\leq\inf_{k\geq n} s_{k}\leq s_{n}\leq \sup_{k\geq n} s_{k}\leq s+\varepsilon
\end{gather}
$$

(2) 由于 $\sup_{k\geq n}s_{k}$ 单调递减，因此

$$
\begin{gather}
\limsup_{ n \to \infty } s_{n}=\inf_{n>0} \sup_{k\geq n} s_{k}=\inf_{n\geq N} \sup_{k\geq n} s_{k}
\end{gather}
$$

由于当 $n\geq N$ 时有 $\sup_{k\geq n}s_{k}\leq \sup_{k\geq n}t_{k}$，故我们有

$$
\begin{gather}
\inf_{n\geq N} \sup_{k\geq n} s_{k}\leq \sup_{k\geq n} t_{k}
\end{gather}
$$

对任意 $n\geq N$ 成立，从而

$$
\begin{gather}
\limsup_{ n \to \infty } s_{n}\leq \inf_{n\geq N} \sup_{k\geq n} t_{k}=\limsup_{ n \to \infty } t_{n}
\end{gather}
$$

对下极限同理，这就完成了证明。

# Some Special Sequences

本节我们给出一些常用序列的极限。其证明将用到一个基础结论：如果存在 $N$ 使得 $n\geq N$ 蕴含 $0\leq x_{n}\leq s_{n}$，且 $s_{n}\to 0$，那么 $x_{n}\to 0$。我们定义实数的乘方 $x^{\alpha}$ 为序列 $(x^{r_{n}})$ 的极限，其中 $r_{n}\in \mathbb{Q},r_{n}\to\alpha$。

## Theorem 3.22

(a) 如果 $p>0$，则 $\lim_{ n \to \infty }(1 /n^{p})=0$。
(b) 如果 $p>0$，则 $\lim_{ n \to \infty } p^{1/n}=1$。
(c) $\lim_{ n \to \infty } n^{1/n}=1$。
(d) 如果 $p>0$ 且 $\alpha \in \mathbb{R}$，则 $\lim_{ n \to \infty } n^{\alpha} /(1+p)^{n}=0$。
(e) 如果 $\lvert x \rvert<1$，则 $\lim_{ n \to \infty } x^{n}=0$。

### Proof

(a) 要使 $1 /n^{p}<\varepsilon$，两边取倒数然后开 $p$ 次根即可，即 $n>(1 /\varepsilon)^{1/p}$。

(b) 如果 $p>1$，令 $x_{n}=p^{1/n}-1$，则 $x_{n}>0$ 且

$$
\begin{gather}
1+nx_{n}\leq(1+x_{n})^{n}=p
\end{gather}
$$

从而

$$
\begin{gather}
0<x_{n}\leq \frac{p-1}{n} \to 0
\end{gather}
$$

如果 $p=1$，结论是平凡的。如果 $p<1$，取倒数然后利用 $p>1$ 的结果即可。

(c) 令 $x_{n}=n^{1/n}-1$，则

$$
\begin{gather}
n=(1+x_{n})^{n}\geq \frac{n(n-1)}{2}x_{n}^{2}
\end{gather}
$$

于是

$$
\begin{gather}
0\leq x_{n}\leq \sqrt{ \frac{2}{n-1} } \to 0
\end{gather}
$$

(d) 设 $k>\alpha$ 是一个正整数，当 $n>2k$ 时，我们有

$$
\begin{gather}
(1+p)^{n}\geq \frac{n(n-1)\cdots(n-k+1)}{k!} p^{k}\geq \frac{n^{k}p^{k}}{2^{k}k!}
\end{gather}
$$

于是

$$
\begin{gather}
0<\frac{n^{\alpha}}{(1+p)^{n}}\leq \frac{2^{k}k!}{p^{k}} n^{\alpha-k}
\end{gather}
$$

由于 $\alpha-k<0$，应用 (a) 即证。

在 (d) 中取 $\alpha=0$ 即证 (e)。

# Series 级数

本节中的序列，除非有特殊的指定，否则都取为复数序列。

## Definition 3.23 series 级数

给定一个序列 $(a_{n})$，定义其部分和序列 $(s_{n})$ 为

$$
\begin{gather}
s_{n}=\sum_{k=1}^{n} a_{k}
\end{gather}
$$

如果 $(s_{n})$ 收敛于 $s$，我们就称级数 $\sum_{n=1}^{\infty}a_{n}$ 收敛，且

$$
\begin{gather}
\sum_{n=1}^{\infty} a_{n}=s
\end{gather}
$$

称 $s$ 为级数的和。如果 $(s_{n})$ 发散，则称级数 $\sum_{n=1}^{\infty}a_{n}$ 发散。

根据以上定义，显然每个级数都是某个序列的极限。另一方面，每个序列的极限也可以视为一个级数：取 $a_{1}=s_{1}$，$a_{n}=s_{n}-s_{n-1}$。因此，对序列极限成立的多数定理也可以应用于级数。

## Theorem 3.24 (Cauchy 准则)

级数 $\sum a_{n}$ 收敛当且仅当对任意 $\varepsilon>0$，存在 $N$ 使得 $m\geq n\geq N$ 蕴含

$$
\begin{gather}
\left\lvert  \sum_{k=n}^{m} a_{k}  \right\rvert <\varepsilon
\end{gather}
$$

特别地，取 $m=n$，我们就有 $\lvert a_{n} \rvert<\varepsilon$，即：

## Theorem 3.25

如果 $\sum a_{n}$ 收敛，那么 $\lim_{ n \to \infty }a_{n}=0$。

以上定理通常被用于证明级数不收敛：如果 $\lim_{ n \to \infty }a_{n}\neq 0$，那么级数 $\sum a_{n}$ 发散。

## Theorem 3.26 (单调有界原理)

一个非负级数收敛当且仅当它的部分和序列有上界。

## Theorem 3.27 (比较准则)

(a) 如果存在 $N_{0}$ 使得 $n\geq N_{0}$ 蕴含 $\lvert a_{n} \rvert\leq c_{n}$，并且 $\sum c_{n}$ 收敛，那么 $\sum a_{n}$ 收敛。
(b) 如果存在 $N_{0}$ 使得 $n\geq N_{0}$ 蕴含 $a_{n}\geq d_{n}\geq 0$，并且 $\sum d_{n}$ 发散，那么 $\sum a_{n}$ 发散。

### Proof

(a) 给定 $\varepsilon>0$，[[#Theorem 3.24 (Cauchy 准则)]] 表明存在 $N$ 使得 $m\geq n\geq N$ 蕴含

$$
\begin{gather}
\sum_{k=n}^{m} c_{n}<\varepsilon
\end{gather}
$$

于是

$$
\begin{gather}
\left\lvert  \sum_{k=n}^{m} a_{k}  \right\rvert \leq \sum_{k=n}^{m} \lvert a_{k} \rvert \leq \sum_{k=n}^{m} c_{k}<\varepsilon
\end{gather}
$$

即证 $\sum a_{n}$ 收敛。

(b) 由 (a) 给出：如果 $\sum a_{n}$ 收敛，那么 $\sum d_{n}$ 收敛，取逆否命题即证。

比较准则是一个非常有用的收敛性判别法，但要发挥它的最大作用，我们必须对一些常用级数的收敛性进行考察。

# Series of Nonnegative Terms 非负级数

## Theorem 3.28

如果 $0\leq x<1$，则

$$
\begin{gather}
\sum_{n=0}^{\infty} x^{n}=\frac{1}{1-x}
\end{gather}
$$

如果 $x\geq 1$，则级数发散。

本定理中的级数 $\sum_{n=0}^{\infty}x^{n}$ 称为几何级数。

### Proof

如果 $x\neq 1$，则

$$
\begin{gather}
s_{n}=\sum_{k=0}^{n} x^{k}=\frac{1-x^{n+1}}{1-x}
\end{gather}
$$

令 $n\to \infty$ 即证。对于 $x=1$，我们有

$$
\begin{gather}
s_{n}=\sum_{k=0}^{n} 1=n+1
\end{gather}
$$

显然它是发散的。

## Theorem 3.29 (Cauchy)

设 $a_{1}\geq a_{2}\geq a_{3}\geq \dots\geq 0$，则级数 $\sum_{n=1}^{\infty}a_{n}$ 收敛当且仅当级数

$$
\begin{gather}
\sum_{k=0}^{\infty} 2^{k}a_{2^{k}}=a_{1}+2a_{2}+4a_{4}+\cdots
\end{gather}
$$

收敛。

### Proof

根据 [[#Theorem 3.26 (单调有界原理)]]，我们只需考虑部分和的有界性。设

$$
\begin{gather}
s_{n}=a_{1}+a_{2}+\dots+a_{n} \\
t_{k}=a_{1}+2a_{2}+\dots+2^{k}a_{2^{k}}
\end{gather}
$$

对于 $n<2^{k}$，有

$$
\begin{align}
s_{n} &\leq a_{1}+(a_{2}+a_{3})+\dots+(a_{2^{k}}+\dots+a_{2^{k+1}-1}) \\
&\leq a_{1}+2a_{2}+\dots+2^{k}a_{2^{k}}=t_{k}
\end{align}
$$

另一方面，如果 $n>2^{k}$，则

$$
\begin{align}
s_{n} &\geq a_{1}+a_{2}+(a_{3}+a_{4})+\dots+(a_{2^{k-1}+1}+\dots+a_{2^{k}}) \\
&\geq \frac{1}{2}a_{1}+a_{2}+2a_{4}+\dots+2^{k-1}a_{2^{k}}=\frac{1}{2}t_{k}
\end{align}
$$

综上，我们可知 $(s_{n})$ 与 $(t_{k})$ 同时有界或者同时无界，这就完成了证明。

## Theorem 3.30

级数 $\sum 1 /n^{p}$ 在 $p>1$ 时收敛，在 $p\leq 1$ 时发散。

这一级数 $\sum 1 /n^{p}$ 称为 $p$-级数或广义调和级数，因为 $\sum 1 /n$ 被称为调和级数。

### Proof

$p\leq 0$ 时的发散性由 [[#Theorem 3.25]] 给出。如果 $p>0$，应用 [[#Theorem 3.29 (Cauchy)]]，则我们只需考虑级数

$$
\begin{gather}
\sum_{k=0}^{\infty} 2^{k} \frac{1}{2^{kp}}=\sum_{k=0}^{\infty} 2^{k(1-p)}
\end{gather}
$$

取 $x=2^{1-p}$，则以上级数是一个几何级数，从而在 $x<1$ 即 $p>1$ 时收敛，在 $p\leq 1$ 时发散。

## Theorem 3.31

如果 $p>1$，则级数

$$
\begin{gather}
\sum_{n=2}^{\infty} \frac{1}{n(\log n)^{p}}
\end{gather}
$$

收敛。如果 $p\leq 1$，则级数发散。

这里 $\log n$ 表示 $n$ 关于自然常数 $e$ 的对数。

### Proof

对数函数的单调性表明 $1 / n(\log n)^{p}$ 单调递减，因此我们可以使用 [[#Theorem 3.29 (Cauchy)]]，则我们只需考虑级数

$$
\begin{gather}
\sum_{k=1}^{\infty} 2^{k} \frac{1}{2^{k}(\log 2^{k})^{p}}=\sum_{k=1}^{\infty} \frac{1}{(\log 2)^{p} k^{p}}=\frac{1}{(\log 2)^{p}} \sum_{k=1}^{\infty} \frac{1}{k^{p}}
\end{gather}
$$

根据 $p$-级数的收敛性即证。

# The Number $e$

## Definition 3.32 $e$

定义自然常数 $e=\sum_{n=0}^{\infty} \frac{1}{n!}$。

以上级数是收敛的：

$$
\begin{align}
s_{n}&=1+1+\frac{1}{2!}+\frac{1}{3!}+\dots+\frac{1}{n!} \\
&\leq 1+1+\frac{1}{2}+\frac{1}{2^{2}}+\dots+\frac{1}{2^{n-1}}\leq 3
\end{align}
$$

因此以上定义是合理的。

## Theorem 3.33

$$
\lim_{ n \to \infty } \left( 1+\frac{1}{n} \right)^{n}=e
$$

### Proof

设

$$
\begin{gather}
s_{n}=\sum_{k=0}^{n} \frac{1}{k!}, \quad t_{n}=\left( 1+\frac{1}{n} \right)^{n}
\end{gather}
$$

则二项式定理给出

$$
\begin{align}
t_{n} &= 1+1+\frac{1}{2!} \left( 1-\frac{1}{n} \right)+\frac{1}{3!}\left( 1-\frac{1}{n} \right)\left( 1-\frac{2}{n} \right)+\cdots \\
&+ \frac{1}{n!} \left( 1-\frac{1}{n} \right) \cdots \left( 1-\frac{n-1}{n} \right)
\end{align}
$$

因此 $t_{n}\leq s_{n}$，从而

$$
\begin{gather}
\limsup_{ n \to \infty } t_{n}\leq e
\end{gather}
$$

另一方面，如果 $n\geq m$，则

$$
\begin{align}
t_{n}\geq 1+1+\frac{1}{2!}\left( 1-\frac{1}{n} \right)+\dots+\frac{1}{m!}\left( 1-\frac{1}{n} \right)\cdots \left( 1-\frac{m-1}{n} \right)
\end{align}
$$

固定 $m$，令 $n\to \infty$，则

$$
\begin{gather}
\liminf_{ n \to \infty } t_{n}\geq 1+1+\frac{1}{2!}+\dots+\frac{1}{m!}=s_{m}\to e
\end{gather}
$$

因此我们有

$$
\begin{gather}
e\leq \liminf_{ n \to \infty } t_{n}\leq \limsup_{ n \to \infty } t_{n}\leq e
\end{gather}
$$

这就完成了证明。

$e$ 的级数定义式收敛得非常快，这允许我们仅取少量项即可得到相当高的精度。精确地说，其误差上界为

$$
\begin{align}
e-s_{n}&= \frac{1}{(n+1)!}+\frac{1}{(n+2)!}+\frac{1}{(n+3)!}+\cdots \\
&< \frac{1}{(n+1)!}\left( 1+\frac{1}{n+1}+\frac{1}{(n+1)^{2}}+\dots \right)=\frac{1}{n!n}
\end{align}
$$

## Theorem 3.34

$e$ 是无理数。

### Proof

假设 $e=p /q$，则

$$
\begin{gather}
0<q! (e-s_{q})< \frac{1}{q}
\end{gather}
$$

根据假设，$q! e$ 是整数，而

$$
\begin{gather}
q! s_{q}=q! \left( 1+1+\frac{1}{2!}+\dots+\frac{1}{q!} \right)
\end{gather}
$$

也是整数，因此 $q!(e-s_{q})$ 也是整数。这与 $q!(e-s_{q})<1 /q$ 矛盾。

# The Root and Ratio Tests 根值准则与比值准则

## Theorem 3.35 (根值准则)

给定级数 $\sum a_{n}$，令 $\alpha=\limsup_{ n \to \infty } \lvert a_{n} \rvert^{1/n}$，则

1. 如果 $\alpha<1$，那么 $\sum a_{n}$ 收敛。
2. 如果 $\alpha>1$，那么 $\sum a_{n}$ 发散。
3. 如果 $\alpha=1$，我们不能得到任何结论。

### Proof

(1) 由于 $\alpha<1$，我们可以选取 $\alpha<\beta<1$，以及整数 $N$ 使得 $n\geq N$ 蕴含

$$
\begin{gather}
\lvert a_{n} \rvert ^{1/n}<\beta
\end{gather}
$$

从而

$$
\begin{gather}
\lvert a_{n} \rvert <\beta^{n}
\end{gather}
$$

由于几何级数 $\sum\beta^{n}$ 在 $\beta<1$ 时收敛，故由比较准则知 $\sum a_{n}$ 收敛。

(2) 如果 $\alpha>1$，则存在子序列 $\lvert a_{n_{k}} \rvert^{1/n_{k}}\to\alpha$，换句话说，有无穷多个 $\lvert a_{n} \rvert>1$，于是 $a_{n} \to 0$ 不成立，从而 $\sum a_{n}$ 发散。

(3) 考虑 $p$-级数

$$
\begin{gather}
\sum \frac{1}{n}, \quad \sum \frac{1}{n^{2}}
\end{gather}
$$

两者均满足 $\alpha=1$，但前者发散，后者收敛。

## Theorem 3.36 (比值准则)

级数 $\sum a_{n}$

1. 收敛，如果 $\limsup_{ n \to \infty }\lvert a_{n+1} /a_{n} \rvert<1$。
2. 发散，如果存在 $N_{0}$ 使得 $n\geq N_{0}$ 蕴含 $\lvert a_{n+1} /a_{n} \rvert\geq 1$。

这里条件 (2) 的一个充分条件为 $\liminf_{ n \to \infty }\lvert a_{n+1} /a_{n} \rvert>1$。

### Proof

(1) 如果 $\limsup_{ n \to \infty }\lvert a_{n+1} /a_{n} \rvert<1$，我们可以找到 $\beta<1$ 以及整数 $N$ 使得 $n\geq N$ 蕴含

$$
\begin{gather}
\left\lvert  \frac{a_{n+1}}{a_{n}}  \right\rvert <\beta
\end{gather}
$$

从而

$$
\begin{align}
\lvert a_{n} \rvert < \beta \lvert a_{n-1} \rvert <\beta^{2}\lvert a_{n-2} \rvert <\dots<\beta^{n-N}\lvert a_{N} \rvert 
\end{align}
$$

根据比较准则以及几何级数的收敛性即证。

(2) 对于 $n\geq N_{0}$，显然 $a_{n}\neq 0$，再根据 $\lvert a_{n+1} \rvert\geq\lvert a_{n} \rvert$，故 $a_{n}\to 0$ 不成立，从而 $\sum a_{n}$ 发散。

## Remark 3.37

通常来说，比值准则比根值准则更为常用，因为求相邻项的比值通常比求 $n$ 次根更容易。然而，根值准则有其自身的优点：它的适用范围更广。具体来说，每当比值准则给出收敛的结果，根值准则将同样给出收敛；每当根值准则不适用时，比值准则也同样不适用。这是如下定理的一个反映：

## Theorem 3.38

设 $(c_{n})$ 是一列正数，则

$$
\begin{gather}
\liminf_{ n \to \infty } \frac{c_{n+1}}{c_{n}}\leq \liminf_{ n \to \infty } c_{n}^{1/n} \\
\limsup_{ n \to \infty } c_{n}^{1/n}\leq \limsup_{ n \to \infty } \frac{c_{n+1}}{c_{n}}
\end{gather}
$$

### Proof

我们只证明上极限的不等式，另一个是类似的。

令 $\alpha=\limsup_{ n \to \infty }(c_{n+1} /c_{n})$，如果 $\alpha=+\infty$，那么结论是平凡的。如果 $\alpha \in \mathbb{R}$，选取 $\beta>\alpha$，则存在 $N$ 使得 $n\geq N$ 蕴含

$$
\begin{gather}
\frac{c_{n+1}}{c_{n}}<\beta
\end{gather}
$$

于是

$$
\begin{gather}
c_{n}<\beta c_{n-1}<\dots<\beta^{n-N} c_{N}
\end{gather}
$$

从而

$$
\begin{gather}
c_{n}^{1/n}<(\beta^{-N}c_{N})^{1/n} \beta
\end{gather}
$$

取 $n\to \infty$ 的上极限即得

$$
\begin{gather}
\limsup_{ n \to \infty } c_{n}^{1/n}\leq \beta
\end{gather}
$$

上式对任意 $\beta>\alpha$ 成立，因而也对 $\alpha$ 成立，即

$$
\begin{gather}
\limsup_{ n \to \infty } c_{n}^{1/n}\leq \limsup_{ n \to \infty } \frac{c_{n+1}}{c_{n}}
\end{gather}
$$

# Power Series 幂级数

## Definition 3.39 power series 幂级数

给定一列复数 $(c_{n})$，级数

$$
\begin{gather}
\sum_{n=0}^{\infty} c_{n}z^{n}
\end{gather}
$$

称为一个幂级数，其中 $z \in \mathbb{C}$，$c_{n}$ 称为幂级数的第 $n$ 个系数。

幂级数的收敛性取决于 $z$ 的取值。幂级数理论中的一个基本结果是，每个幂级数都关联着复平面上的一个圆（我们将点视为半径为 $0$ 的圆，复平面视为半径为无穷大的圆），在其内部幂级数处处收敛，而在其外部幂级数发散，级数在圆的边界上的行为则更为复杂。

## Theorem 3.40

给定幂级数 $\sum_{n=0}^{\infty}c_{n}z^{n}$，令

$$
\begin{gather}
\alpha=\limsup_{ n \to \infty } \lvert c_{n} \rvert ^{1/n}, \quad R=\frac{1}{\alpha} \quad \left( \frac{1}{0}=+\infty, \frac{1}{+\infty}=0 \right)
\end{gather}
$$

则当 $\lvert z \rvert<R$ 时级数收敛，$\lvert z \rvert>R$ 时级数发散。

这里的 $R$ 称为幂级数的收敛半径。

### Proof

令 $a_{n}=c_{n}z^{n}$，应用根值准则：

$$
\begin{gather}
\limsup_{ n \to \infty } \lvert a_{n} \rvert ^{1/n}=\lvert z \rvert \limsup_{ n \to \infty } \lvert c_{n} \rvert ^{1/n}=\frac{\lvert z \rvert }{R}
\end{gather}
$$

## Example 3.41

(a) $\sum n^{n}z^{n}$ 的收敛半径为 $R=0$。
(b) $\sum z^{n} /n!$ 的收敛半径为 $R=+\infty$（可应用比值准则），该级数就是指数函数 $e^{z}$。
(c) $\sum z^{n}$ 的收敛半径为 $R=1$，在 $\lvert z \rvert=1$ 上发散，因为其不满足 $z^{n}\to 0$ 的条件。
(d) $\sum z^{n} /n$ 的收敛半径为 $R=1$，它在 $z=1$ 处发散，而在 $\lvert z \rvert=1$ 的其他地方收敛。该级数是对数函数 $\log (1+z)$ 在 $z=0$ 处的 Taylor 级数。
(e) $\sum z^{n} /n^{2}$ 的收敛半径为 $R=1$，并且在 $\lvert z \rvert=1$ 上处处收敛，因为我们可以应用比较准则：$\lvert z^{n} /n^{2} \rvert=1 /n^{2}$。

# Summation by Parts 分部求和

## Theorem 3.42 (分部求和)

给定序列 $(a_{n}),(b_{n})$，令

$$
\begin{gather}
A_{n}=\sum_{k=0}^{n} a_{k} \quad (n\geq 0)
\end{gather}
$$

且 $A_{-1}=0$，则对 $0\leq p\leq q$ 有

$$
\begin{gather}
\sum_{n=p}^{q} a_{n}b_{n}=\sum_{n=p}^{q-1} A_{n}(b_{n}-b_{n+1})+A_{q}b_{q}-A_{p-1}b_{p}
\end{gather}
$$

### Proof

$$
\begin{align}
\sum_{n=p}^{q} a_{n}b_{n}=\sum_{n=p}^{q} (A_{n}-A_{n-1})b_{n}=\sum_{n=p}^{q} A_{n}b_{n}-\sum_{n=p-1}^{q-1} A_{n}b_{n+1}
\end{align}
$$

最后一个表达式显然与定理中的右侧表达式一致。

分部求和通常用于分析形如 $\sum a_{n}b_{n}$ 的级数，特别是当 $(b_{n})$ 是一个单调序列时。

## Theorem 3.43 (Dirichlet)

假设

1. 级数 $\sum a_{n}$ 的部分和 $A_{n}$ 有界，
2. $b_{0}\geq b_{1}\geq b_{2}\geq\dots\geq 0$，
3. $\lim_{ n \to \infty }b_{n}=0$。

则级数 $\sum a_{n}b_{n}$ 收敛。

### Proof

取 $M>0$ 使得 $\lvert A_{n} \rvert\leq M$ 对任意 $n$ 成立。给定 $\varepsilon>0$，存在 $N$ 使得 $b_{N}<\varepsilon$，于是对 $q\geq p\geq N$ 有

$$
\begin{align}
\left\lvert  \sum_{n=p}^{q} a_{n}b_{n}  \right\rvert &= \left\lvert  \sum_{n=p}^{q-1} A_{n}(b_{n}-b_{n+1})+A_{q}b_{q}-A_{p-1}b_{p}  \right\rvert  \\
&\leq M \left\lvert  \sum_{n=p}^{q-1} (b_{n}-b_{n+1})+b_{q}+b_{p}  \right\rvert  \\
&=2Mb_{p}<2M\varepsilon
\end{align}
$$

根据 Cauchy 准则知 $\sum a_{n}b_{n}$ 收敛。

## Theorem 3.44 (Leibnitz)

假设

1. $\lvert c_{1} \rvert\geq\lvert c_{2} \rvert\geq\lvert c_{3} \rvert\geq\dots\geq 0$，
2. $c_{2m-1}\geq 0,c_{2m}\leq 0$（序列的符号正负交替），
3. $\lim_{ n \to \infty }c_{n}=0$。

则级数 $\sum c_{n}$ 收敛。

这一定理也称为交错级数判别法。

### Proof

对 $a_{n}=(-1)^{n+1},b_{n}=\lvert c_{n} \rvert$ 应用 [[#Theorem 3.43 (Dirichlet)]]。

## Theorem 3.45

设幂级数 $\sum c_{n}z^{n}$ 的收敛半径为 $1$，且 $c_{0}\geq c_{1}\geq\dots\geq 0$，$\lim_{ n \to \infty }c_{n}=0$，则除了 $z=1$ 外，级数在 $\lvert z \rvert=1$ 上处处收敛。

### Proof

取 $a_{n}=z^{n},b_{n}=c_{n}$，则当 $\lvert z \rvert=1$ 且 $z\neq 1$ 时，

$$
\begin{gather}
\lvert A_{n} \rvert =\left\lvert  \sum_{k=0}^{n} z^{k}  \right\rvert =\left\lvert  \frac{1-z^{n+1}}{1-z}  \right\rvert \leq \frac{2}{\lvert 1-z \rvert }
\end{gather}
$$

是有界序列。因此根据 [[#Theorem 3.43 (Dirichlet)]] 即证。

# Absolute Convergence 绝对收敛

## Definition 3.46 converge absolutely 绝对收敛，converge conditionally 条件收敛

称级数 $\sum a_{n}$ 绝对收敛，如果 $\sum\lvert a_{n} \rvert$ 收敛。如果 $\sum a_{n}$ 收敛但不绝对收敛，则称级数 $\sum a_{n}$ 条件收敛。

## Theorem 3.47

如果 $\sum a_{n}$ 绝对收敛，那么 $\sum a_{n}$ 收敛。

### Proof

根据

$$
\begin{gather}
\left\lvert  \sum_{k=n}^{m} a_{k}  \right\rvert \leq \sum_{k=n}^{m} \lvert a_{k} \rvert 
\end{gather}
$$

以及 Cauchy 准则即证。

## Remark 3.48

比较准则、根值准则与比值准则在实质上都是绝对收敛的判别法：如果这些准则给出收敛，那么我们事实上可知原级数绝对收敛。特别地，幂级数在收敛圆内部绝对收敛。但也由于这个原因，它们无法对条件收敛的级数起效。分部求和有时能够用于条件收敛的级数，例如

$$
\begin{gather}
\sum_{n=1}^{\infty} \frac{(-1)^{n+1}}{n}
\end{gather}
$$

的条件收敛性由交错级数判别法给出。但对于更为奇异的级数，我们只能一个个单独分析。

# Addition and Multiplication of Series 级数的加法与乘法

## Theorem 3.47

如果 $\sum a_{n}=A,\sum b_{n}=B$，那么 $\sum(a_{n}+b_{n})=A+B$，且对任意 $c \in \mathbb{C}$ 有 $\sum ca_{n}=cA$。

### Proof

根据 [[#Theorem 3.3]] 即证。

## Definition 3.48 Cauchy product 柯西乘积

给定级数 $\sum a_{n},\sum b_{n}$，定义

$$
\begin{gather}
c_{n}=\sum_{k=0}^{n} a_{k}b_{n-k}
\end{gather}
$$

称 $\sum c_{n}$ 为两个级数的 Cauchy 乘积。

以上定义的动机如下：我们考虑两个幂级数的乘积

$$
\begin{align}
\left( \sum_{n=0}^{\infty} a_{n}z^{n} \right)\left( \sum_{n=0}^{\infty} b_{n}z^{n} \right)&=a_{0}b_{0}+(a_{0}b_{1}+a_{1}b_{0})z \\
&+(a_{0}b_{2}+a_{1}b_{1}+a_{2}b_{0})z^{2}+\cdots
\end{align}
$$

可见 Cauchy 乘积正是将乘积展开后按 $z$ 的次数合并得到的系数。令 $z=1$，我们就得到了 $\sum c_{n}$。

## Example 3.49

不像加法与数乘，部分和 $C_{n}$ 与 $A_{n},B_{n}$ 的关系更为复杂，因而我们不能确定当 $A_{n}\to A,B_{n}\to B$ 时是否有 $C_{n}\to AB$。下面我们将看到，两个收敛级数的乘积有可能发散。

根据交错级数判别法，级数

$$
\begin{gather}
\sum_{n=0}^{\infty} \frac{(-1)^{n}}{\sqrt{ n+1 }}=1-\frac{1}{\sqrt{ 2 }}+\frac{1}{\sqrt{ 3 }}-\frac{1}{\sqrt{ 4 }}+\cdots
\end{gather}
$$

收敛。我们考虑它与自身的乘积

$$
\begin{align}
c_{n}=(-1)^{n} \sum_{k=0}^{n} \frac{1}{\sqrt{ (n-k+1)(k+1) }}
\end{align}
$$

由于

$$
\begin{gather}
(n-k+1)(k+1)=\left( \frac{n}{2}+1 \right)^{2}-\left( \frac{n}{2}-k \right)^{2}\leq \left( \frac{n+2}{2} \right)^{2}
\end{gather}
$$

因此

$$
\begin{gather}
\lvert c_{n} \rvert \geq \sum_{k=0}^{n} \frac{2}{n+2}=\frac{2(n+1)}{(n+2)} \to 1
\end{gather}
$$

从而不满足 $c_{n}\to 0$ 的条件，即 $\sum c_{n}$ 发散。

依据以下定理，我们注意到，上面的例子是两个条件收敛级数的乘积。

## Theorem 3.50 (Mertens)

假设

1. $\sum_{n=0}^{\infty}a_{n}$ 绝对收敛，
2. $\sum_{n=0}^{\infty}a_{n}=A$，
3. $\sum_{n=0}^{\infty}b_{n}=B$，
4. $c_{n}=\sum_{k=0}^{n}a_{k}b_{n-k}$。

则

$$
\begin{gather}
\sum_{n=0}^{\infty} c_{n}=AB
\end{gather}
$$

换句话说，两个收敛级数的乘积收敛于和的乘积，如果至少一个级数绝对收敛。

### Proof

令

$$
\begin{gather}
A_{n}=\sum_{k=0}^{n} a_{k}, \quad B_{n}=\sum_{k=0}^{n} b_{k}, \quad C_{n}=\sum_{k=0}^{n} c_{k}, \quad \beta_{n}=B_{n}-B
\end{gather}
$$

则

$$
\begin{align}
C_{n} &= a_{0}b_{0}+(a_{0}b_{1}+a_{1}b_{0})+\dots+(a_{0}b_{n}+a_{1}b_{n-1}+\dots+a_{n}b_{0}) \\
&= a_{0}B_{n}+a_{1}B_{n-1}+\dots+a_{n}B_{0} \\
&=a_{0}(B+\beta_{n})+a_{1}(B+\beta_{n-1})+\dots+a_{n}(B+\beta_{0}) \\
&=A_{n}B+a_{0}\beta_{n}+\dots+a_{n}\beta_{0}
\end{align}
$$

令

$$
\begin{gather}
\gamma_{n}=a_{0}\beta_{n}+\dots+a_{n}\beta_{0}
\end{gather}
$$

由于 $A_{n}B\to AB$，则要证 $C_{n}\to AB$，我们只需证明 $\gamma_{n}\to 0$。

取

$$
\begin{gather}
\alpha=\sum_{n=0}^{\infty} \lvert a_{n} \rvert 
\end{gather}
$$

给定 $\varepsilon>0$，由于 $\beta_{n}\to 0$，故存在 $N$ 使得 $n\geq N$ 蕴含 $\lvert \beta_{n} \rvert<\varepsilon$，从而

$$
\begin{align}
\lvert \gamma_{n} \rvert &\leq \lvert \beta_{0}a_{n}+\dots+\beta_{N}a_{n-N} \rvert+\lvert \beta_{N+1}a_{n-N-1}+\dots+\beta_{n}a_{0} \rvert  \\
&\leq \lvert \beta_{0}a_{n}+\dots+\beta_{N}a_{n-N} \rvert +\varepsilon \alpha 
\end{align}
$$

由于 $a_{n}\to 0$，因此

$$
\begin{gather}
\limsup_{ n \to \infty } \lvert \gamma_{n} \rvert \leq \varepsilon\alpha
\end{gather}
$$

根据 $\varepsilon$ 的任意性即证 $\gamma_{n}\to 0$，因为 $\liminf_{ n \to \infty }\lvert \gamma_{n} \rvert\geq 0$。

另一个问题是，如果乘积级数 $\sum c_{n}$ 自身是收敛的，那么它的极限是否一定是 $AB$。Abel 证明了其答案是肯定的。

## Theorem 3.51 (Abel)

如果级数 $\sum a_{n},\sum b_{n},\sum c_{n}$ 分别收敛于 $A,B,C$，且 $c_{n}=\sum_{k=0}^{n}a_{k}b_{n-k}$，则 $C=AB$。

注意，这里没有对级数的绝对收敛性做要求。

### Proof

我们将给出一个基于幂级数连续性（Abel 定理）的证明。

定义 $[0,1]$ 上的函数

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} a_{n}x^{n}, \quad g(x)=\sum_{n=0}^{\infty} b_{n}x^{n}, \quad h(x)=\sum_{n=0}^{\infty} c_{n}x^{n}
\end{gather}
$$

则在 $0\leq x<1$ 上，三个级数均绝对收敛（[[#Theorem 3.40]]），且

$$
\begin{gather}
f(x)g(x)=h(x)
\end{gather}
$$

此外，当 $x\to 1$ 时，有

$$
\begin{gather}
f(x)\to A, \quad g(x)\to B,\quad h(x)\to C
\end{gather}
$$

因此我们有 $AB=C$。

# Rearrangements 重排

## Definition 3.52 rearrangement 重排

设序列 $(k_{n})$ 是 $\mathbb{N}$ 到 $\mathbb{N}$ 的一个双射，令

$$
\begin{gather}
a_{n}'=a_{k_{n}}
\end{gather}
$$

则称 $\sum a_{n}'$ 是级数 $\sum a_{n}$ 的一个重排。

如果 $s_{n},s_{n}'$ 分别是 $\sum a_{n}$ 和 $\sum a_{n}'$ 的部分和，则一般来说，这两个序列是完全不同的。这就引出了如下问题：在什么情况下，重排级数仍然收敛，并且其极限与原极限相同。

Riemann 的一个著名定理表明：对于绝对收敛级数，其重排仍然收敛，并且极限相同。（这可以视为无穷级数的交换律，而结合律与序列和子序列的关联 [[#Proposition 3.6]] 有关。）然而，对于条件收敛级数，我们可以构造重排，使得重排后的级数收敛于任何值，或发散。

## Theorem 3.53 (Riemann)

设实数级数 $\sum a_{n}$ 条件收敛，任取

$$
\begin{gather}
-\infty\leq\alpha\leq\beta\leq+\infty
\end{gather}
$$

则存在重排级数 $\sum a_{n}'$ 使得

$$
\begin{gather}
\liminf_{ n \to \infty } s_{n}'=\alpha, \quad \limsup_{ n \to \infty } s_{n}'=\beta
\end{gather}
$$

其中 $s_{n}'$ 是 $\sum a_{n}'$ 的部分和。

### Motivation

条件收敛级数有这样一种性质：它的正数部分的总和为正无穷，负数部分的总和为负无穷。于是我们可以这样排列：首先将正数和负数部分分开，然后我们加入若干正数项直到部分和位于 $\beta$ 附近，之后再加入若干负数项直到部分和位于 $\alpha$ 附近，就这样交替地加入正数和负数项，直到无穷。由于原级数收敛，因此各项的绝对值趋于零，这样就保证了必然有子序列收敛于 $\alpha$ 和 $\beta$。

### Proof

令

$$
\begin{gather}
p_{n}=\frac{\lvert a_{n} \rvert +a_{n}}{2}=\max(a_{n},0), \quad q_{n}=\frac{\lvert a_{n} \rvert -a_{n}}{2}=-\min(a_{n},0)
\end{gather}
$$

它们分别是 $\sum a_{n}$ 的正数项与负数项，满足

$$
\begin{gather}
\sum_{n=1}^{N} a_{n}=\sum_{n=1}^{N} p_{n}-\sum_{n=1}^{N} q_{n}
\end{gather}
$$

我们来证明 $\sum p_{n}$ 和 $\sum q_{n}$ 均发散。如果两个级数收敛，那么

$$
\begin{gather}
\sum_{n=1}^{\infty} (p_{n}+q_{n})=\sum_{n=1}^{\infty} \lvert a_{n} \rvert 
\end{gather}
$$

收敛，这与 $\sum a_{n}$ 条件收敛矛盾。如果仅有一个级数发散，那么 $\sum a_{n}$ 也发散。因此，两个级数均发散。

我们令 $P_{1},P_{2},\dots$ 为 $\sum a_{n}$ 中的非负项，$Q_{1},Q_{2},\dots$ 为 $\sum a_{n}$ 中负数项的绝对值。则 $\sum P_{n},\sum Q_{n}$ 与 $\sum p_{n},\sum q_{n}$ 仅相差若干零元素，因此也是发散的。

下面我们将构造序列 $(m_{n}),(k_{n})$，使得重排级数

$$
\begin{align}
P_{1}+\dots+P_{m_{1}}-Q_{1}-\dots-Q_{k_{1}}&+P_{m_{1}+1}+\dots+P_{m_{2}} \\
&- Q_{k_{1}+1}-\dots-Q_{k_{2}}+\cdots
\end{align}
$$

满足定理中的条件。

选取实数序列 $\alpha_{n}\to\alpha,\beta_{n}\to\beta$，使得 $\alpha_{n}<\beta_{n},\beta_{1}>0$。令 $m_{1},k_{1}$ 为满足

$$
\begin{gather}
P_{1}+\dots+P_{m_{1}}>\beta_{1} \\
P_{1}+\dots+P_{m_{1}}-Q_{1}-\dots-Q_{k_{1}}<\alpha_{1}
\end{gather}
$$

的最小正整数。再令 $m_{2},k_{2}$ 为满足

$$
\begin{gather}
P_{1}+\dots-Q_{k_{1}}+P_{m_{1}+1}+\dots+P_{m_{2}}>\beta_{2} \\
P_{1}+\dots+P_{m_{2}}-Q_{k_{1}+1}-\dots-Q_{k_{2}}<\alpha_{2}
\end{gather}
$$

的最小正整数。以此类推。我们总是可以这样选取，因为 $\sum P_{n},\sum Q_{n}$ 是发散的。

设

$$
\begin{gather}
x_{n}=P_{1}+\dots+P_{m_{n}} \\
y_{n}=P_{1}+\dots-Q_{k_{n}}
\end{gather}
$$

则

$$
\begin{gather}
\lvert x_{n}-\beta_{n} \rvert \leq P_{m_{n}}, \quad \lvert y_{n}-\alpha_{n} \rvert \leq Q_{k_{n}}
\end{gather}
$$

由于 $P_{n}\to 0,Q_{n}\to 0$，因此 $x_{n}\to\beta,y_{n}\to\alpha$。最后，容易看出上述重排级数的部分和不可能有 $>\beta$ 或 $<\alpha$ 的子列极限。

## Theorem 3.54

设复数级数 $\sum a_{n}$ 绝对收敛，则 $\sum a_{n}$ 的任意重排都收敛于同一个极限。

### Proof

设 $\sum a_{n}'=\sum a_{k_{n}}$ 是一个重排，其部分和为 $s_{n}'$。给定 $\varepsilon>0$，存在 $N$ 使得 $m\geq n\geq N$ 蕴含

$$
\begin{gather}
\sum_{k=n}^{m} \lvert a_{k} \rvert <\varepsilon
\end{gather}
$$

现在选取 $p$ 使得 $1,2,\dots,N$ 都包含在 $k_{1},k_{2},\dots,k_{p}$ 中，则当 $n>p$ 时，$s_{n}-s_{n}'$ 中的项 $a_{1},\dots,a_{N}$ 将抵消，从而

$$
\begin{gather}
\lvert s_{n}-s_{n}' \rvert \leq \sum_{k=N}^{N'} \lvert a_{k} \rvert <\varepsilon
\end{gather}
$$

因此 $s_{n}'$ 与 $s_{n}$ 收敛于同一个极限。