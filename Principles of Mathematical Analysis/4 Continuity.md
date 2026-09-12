# Limits of Functions 函数的极限

## Definition 4.1

设 $X,Y$ 是度量空间，$E\subset X$，函数 $f\colon E\to Y$，且 $p$ 是 $E$ 的一个极限点。我们定义 $x\to p$ 时 $f(x)\to q$，或者

$$
\begin{gather}
\lim_{ x \to p } f(x)=q
\end{gather}
$$

如果 $q \in Y$ 满足以下性质：对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $x \in E$ 有

$$
\begin{gather}
0<d_{X}(x,p)<\delta \implies d_{Y}(f(x),q)<\varepsilon
\end{gather}
$$

其中 $d_{X},d_{Y}$ 分别是 $X,Y$ 上的度量。

需要注意的是，$p$ 不需要是 $E$ 的一个元素。事实上，即使 $p \in E$，我们也常有 $f(p)\neq \lim_{ x \to p }f(x)$。

### Motivation

以上的 $\varepsilon-\delta$ 定义与序列极限的 $\varepsilon-N$ 定义是类似的：这只不过是在博弈过程中，将玩家 $2$ 的目标修改为选取 $\delta>0$，使得 $f$ 在 $B_{X}(p,\delta)\cap E\setminus\{ p \}$ 上的函数值均落在 $B_{Y}(q,\varepsilon)$ 内而已。

## Theorem 4.2 (Heine)

令 $X,Y,E,f,p$ 如 [[#Definition 4.1]] 中所示，则

$$
\begin{gather}
\lim_{ x \to p } f(x)=q
\end{gather}
$$

当且仅当对任意 $E$ 中的序列 $(p_{n})$，如果

$$
\begin{gather}
p_{n}\neq p, \quad \lim_{ n \to \infty } p_{n}=p
\end{gather}
$$

那么

$$
\begin{gather}
\lim_{ n \to \infty } f(p_{n})=q
\end{gather}
$$

该定理将函数的极限归结为了序列的极限，从而我们可以直接应用序列极限的性质来得到函数极限的结论。

### Proof

（$\implies$）假设 $\lim_{ x \to p }f(x)=q$，任取 $\varepsilon>0$，存在 $\delta>0$ 使得当 $x \in E$ 且 $0<d_{X}(x,p)<\delta$ 时 $d_{Y}(f(x),q)<\varepsilon$。

取 $(p_{n})$ 满足 $p_{n}\neq p$ 且 $p_{n}\to p$，则存在 $N$ 使得 $n\geq N$ 蕴含 $0<d_{X}(p_{n},p)<\delta$。

于是，当 $n\geq N$ 时，$d_{Y}(f(p_{n}),q)<\varepsilon$，即证 $f(p_{n})\to q$。

（$\impliedby$）假设 $\lim_{ x \to p }f(x)=q$ 不成立，即存在 $\varepsilon>0$，对任意 $\delta>0$ 都存在 $x \in E$ 满足 $0<d_{X}(x,p)<\delta$ 且 $d_{Y}(f(x),q)\geq\varepsilon$。

选取序列 $(p_{n})$ 如下：固定 $\varepsilon>0$，令 $\delta_{n}=1 /n$，取 $p_{n}\in E$ 满足上述条件。

于是，我们有 $p_{n}\neq p,p_{n}\to p$，但 $d_{Y}(f(p_{n}),q)\geq\varepsilon$，即 $(p_{n})$ 不收敛于 $q$。

## Corollary 4.3

如果 $f$ 在 $p$ 处有极限，那么该极限是唯一的。

### Proof

应用 [[3 Numerical Sequences and Series#Theorem 3.2]](2) 以及 [[#Theorem 4.2 (Heine)]]。

## Definition 4.4

设 $f,g$ 是定义在 $E$ 上的复值函数。定义 $E$ 上的函数 $f+g$ 为

$$
\begin{gather}
(f+g)(x)=f(x)+g(x) \quad (x \in E)
\end{gather}
$$

类似地我们可以定义 $f-g,fg$ 以及 $f /g$，其中 $f /g$ 仅定义在满足 $g(x)\neq 0$ 的 $x \in E$ 上。如果对任意 $x \in E$ 有 $f(x)=c \in \mathbb{C}$，则称 $f$ 是一个常值函数或常数，记作 $f=c$。如果 $f,g$ 是实值函数，满足对任意 $x \in E$ 有 $f(x)\leq g(x)$，则记作 $f\leq g$。

类似地，如果 $\mathbf{f},\mathbf{g}\colon E\to \mathbb{R}^{k}$，我们定义 $\mathbf{f}+\mathbf{g}$ 和 $\mathbf{f}\cdot \mathbf{g}$ 为

$$
\begin{gather}
(\mathbf{f}+\mathbf{g})(x)=\mathbf{f}(x)+\mathbf{g}(x), \quad (\mathbf{f}\cdot \mathbf{g})(x)=\mathbf{f}(x)\cdot \mathbf{g}(x)
\end{gather}
$$

并且如果 $\lambda \in \mathbb{R}$，定义 $(\lambda \mathbf{f})(x)=\lambda \mathbf{f}(x)$。

## Theorem 4.5

设 $X$ 是度量空间，$E\subset X$，$p$ 是 $E$ 的极限点，$f,g$ 是 $E$ 上的复值函数，且

$$
\begin{gather}
\lim_{ x \to p } f(x)=A, \quad \lim_{ x \to p } g(x)=B
\end{gather}
$$

则

1. $\lim_{ x \to p }(f+g)(x)=A+B$，
2. $\lim_{ x \to p }(fg)(x)=AB$，
3. $\lim_{ x \to p }(f /g)(x)=A /B$，如果 $B\neq 0$。

### Proof

应用序列的对应性质以及 [[#Theorem 4.2 (Heine)]] 即可。

同理我们也可以证明如下定理：

## Theorem 4.6

设 $X$ 是度量空间，$E\subset X$，$p$ 是 $E$ 的极限点，$\mathbf{f},\mathbf{g}\colon E\to \mathbb{R}^{k}$，且

$$
\begin{gather}
\lim_{ x \to p } \mathbf{f}(x)=\mathbf{A}, \quad \lim_{ x \to p } \mathbf{g}(x)=\mathbf{B}
\end{gather}
$$

则

1. $\lim_{ x \to p }(\mathbf{f}+\mathbf{g})(x)=\mathbf{A}+\mathbf{B}$，
2. $\lim_{ x \to p }(\mathbf{f}\cdot \mathbf{g})(x)=\mathbf{A}\cdot \mathbf{B}$。

# Continuous Functions 连续函数

## Definition 4.7 continuous 连续的

设 $X,Y$ 是度量空间，$E\subset X$，$p \in E$，函数 $f\colon E\to Y$。则称 $f$ 在 $p$ 处连续，如果对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $x \in E$ 有

$$
\begin{gather}
d_{X}(x,p)<\delta \implies d_{Y}(f(x),f(p))<\varepsilon
\end{gather}
$$

如果 $f$ 在 $E$ 上的每一点连续，则称 $f$ 在 $E$ 上连续，或 $f$ 是 $E$ 上的连续函数。

注意，连续性要求 $f$ 在 $p$ 点有定义，这与极限的定义 [[#Definition 4.1]] 不同。

如果 $p$ 是 $E$ 的孤立点，那么 $f$ 必然在 $p$ 点连续，因为对任意 $\varepsilon>0$，我们总是可以取 $\delta>0$ 使得邻域 $B_{X}(p,\delta)$ 中只有 $x=p$ 一个点，此时

$$
\begin{gather}
d_{Y}(f(x),f(p))=0<\varepsilon
\end{gather}
$$

另一方面，如果 $p$ 是极限点，那么通过比较两个定义，我们可以立即得到：

## Theorem 4.8

在 [[#Definition 4.7 continuous 连续的]] 的假设下，如果 $p$ 也是 $E$ 的一个极限点，那么 $f$ 在 $p$ 处连续当且仅当 $\lim_{ x \to p }f(x)=f(p)$。

## Theorem 4.9

设 $X,Y,Z$ 是度量空间，$E\subset X$，$f\colon E\to Y$，$g\colon f(E)\to Z$，并定义 $h\colon E\to Z$ 为

$$
\begin{gather}
h(x)=g(f(x)) \quad (x \in E)
\end{gather}
$$

如果 $f$ 在 $p \in E$ 连续且 $g$ 在 $f(p)$ 处连续，那么 $h$ 在 $p$ 处连续。

函数 $h$ 称为函数 $f,g$ 的复合，记作 $h=g\circ f$。该定理表明，两个连续函数的复合仍然是连续函数。

### Proof

给定 $\varepsilon>0$。由于 $g$ 在 $f(p)$ 连续，故存在 $\eta>0$ 使得

$$
\begin{gather}
y \in f(E), d_{Y}(y,f(p))<\eta \implies d_{Z}(g(y),g(f(p)))<\varepsilon
\end{gather}
$$

由于 $f$ 在 $p$ 处连续，故存在 $\delta>0$ 使得

$$
\begin{gather}
x \in E, d_{X}(x,p)<\delta \implies d_{Y}(f(x),f(p))<\eta
\end{gather}
$$

于是当 $x \in E$ 且 $d_{X}(x,p)<\delta$ 时，

$$
\begin{gather}
d_{Z}(h(x),h(p))=d_{Z}(g(f(x)),g(f(p)))<\varepsilon
\end{gather}
$$

即 $h$ 在 $p$ 处连续。

## Theorem 4.10

一个从度量空间 $X$ 到度量空间 $Y$ 的映射 $f$ 在 $X$ 上连续，当且仅当对任意开集 $V\subset Y$，$f^{-1}(V)$ 在 $X$ 中开。

### Proof

（$\implies$）如果 $f\colon X\to Y$ 连续，设 $p \in f^{-1}(V)$，我们要证 $p$ 是一个内部点。

由于 $f(p)\in V$，$V$ 是开集，因此存在 $\varepsilon>0$ 使得 $B_{Y}(f(p),\varepsilon)\subset V$。根据连续性，存在 $\delta>0$ 使得

$$
\begin{gather}
d_{X}(x,p)<\delta \implies d_{Y}(f(x),f(p))<\varepsilon
\end{gather}
$$

即 $B_{X}(p,\delta)\subset f^{-1}(V)$。

（$\impliedby$）假设开集的原像也是开集，固定 $p \in X$ 与 $\varepsilon>0$，则 $V=B_{Y}(f(p),\varepsilon)$ 是 $Y$ 中的开集，从而 $f^{-1}(V)$ 是开集。

显然 $p \in f^{-1}(V)$，则存在 $\delta>0$ 使得 $B_{X}(p,\delta)\subset f^{-1}(V)$，这正是 $f$ 在 $p$ 处连续的定义。（$d_{X}(x,p)<\delta \implies f(x) \in B_{Y}(f(p),\varepsilon)$）

## Corollary 4.11

一个从度量空间 $X$ 到度量空间 $Y$ 的映射 $f$ 在 $X$ 上连续，当且仅当对任意闭集 $C\subset Y$，$f^{-1}(C)$ 在 $X$ 中闭。

### Proof

由于一个集合是闭集当且仅当其补集是开集，根据 $f^{-1}(E^{c})=f^{-1}(E)^{c}$ 即证。

## Theorem 4.12

设 $f,g$ 是度量空间 $X$ 上的复值连续函数，则 $f+g,fg,f /g$ 在 $X$ 上连续。

在 $f /g$ 的情况下，我们需要假设对任意 $x \in X$ 有 $g(x)\neq 0$。

### Proof

在孤立点上定理是平凡的。在极限点上，应用 [[#Theorem 4.5]] 和 [[#Theorem 4.8]] 即可。

## Theorem 4.13

(a) 设 $f_{1},\dots,f_{k}$ 是度量空间 $X$ 上的实值函数，定义 $\mathbf{f}\colon X\to \mathbb{R}^{k}$ 为

$$
\begin{gather}
\mathbf{f}(x)=(f_{1}(x),\dots,f_{k}(x)) \quad (x \in X)
\end{gather}
$$

则 $\mathbf{f}$ 是连续函数当且仅当每个 $f_{1},\dots,f_{k}$ 都连续。

(b) 如果 $\mathbf{f},\mathbf{g}\colon X\to \mathbb{R}^{k}$ 是连续函数，则 $\mathbf{f}+\mathbf{g}$ 和 $\mathbf{f}\cdot \mathbf{g}$ 也是连续函数。

函数 $f_{1},\dots,f_{k}$ 称为 $\mathbf{f}$ 的分量。注意 $\mathbf{f}+\mathbf{g}$ 是从 $X$ 到 $\mathbb{R}^{k}$ 的函数，而 $\mathbf{f}\cdot \mathbf{g}$ 是 $X$ 上的实值函数。

### Proof

命题 (a) 由不等式

$$
\begin{gather}
\lvert f_{j}(x)-f_{j}(y) \rvert \leq \lvert \mathbf{f}(x)-\mathbf{f}(y) \rvert =\left( \sum_{j=1}^{k} \lvert f_{j}(x)-f_{j}(y) \rvert ^{2} \right)^{1/2}
\end{gather}
$$

给出。命题 (b) 由 (a) 以及 [[#Theorem 4.12]] 给出。

## Example 4.14

设 $x_{1},\dots,x_{k}$ 是 $\mathbf{x}\in \mathbb{R}^{k}$ 的坐标，定义为

$$
\begin{gather}
\phi_{i}(\mathbf{x})=x_{i}
\end{gather}
$$

的函数 $\phi_{i}\colon \mathbb{R}^{k}\to \mathbb{R}$ 是一个连续函数，因为

$$
\begin{gather}
\lvert \phi_{i}(\mathbf{x})-\phi_{i}(\mathbf{y}) \rvert \leq\lvert \mathbf{x}-\mathbf{y} \rvert 
\end{gather}
$$

表明我们可以取 $\delta=\varepsilon$。函数 $\phi_{i}$ 通常称为坐标函数或者投影函数。

重复应用 [[#Theorem 4.12]] 则表明单项式

$$
\begin{gather}
\mathbf{x} \mapsto x_{1}^{n_{1}}x_{2}^{n_{2}}\cdots x_{k}^{n_{k}}
\end{gather}
$$

在 $\mathbb{R}^{k}$ 上连续，其中 $n_{i}\in \mathbb{N}$。于是以上单项式的常数倍也是连续的，因为常数显然是连续的。从而，对任意多项式 $P$，形如

$$
\begin{gather}
P(\mathbf{x})=\sum c_{n_{1},\dots,n_{k}} x_{1}^{n_{1}}\cdots x_{k}^{n_{k}}
\end{gather}
$$

在 $\mathbb{R}^{k}$ 上连续。其中 $c_{n_{1},\dots,n_{k}}\in \mathbb{C}$，$n_{i}\in \mathbb{N}$，且上面的求和中只有有限个非零项。

更进一步，任何有理函数 $P /Q$，其中 $P,Q$ 是多项式，在 $Q\neq 0$ 的任意点上均连续。

另一边，根据三角不等式

$$
\begin{gather}
\lvert \lvert \mathbf{x} \rvert -\lvert \mathbf{y} \rvert  \rvert \leq \lvert \mathbf{x}-\mathbf{y} \rvert 
\end{gather}
$$

容易证明绝对值函数 $\mathbf{x}\mapsto \lvert \mathbf{x} \rvert$ 在 $\mathbb{R}^{k}$ 上连续。于是，对任意连续函数 $\mathbf{f}\colon X\to \mathbb{R}^{k}$，定义为 $\phi(p)=\lvert \mathbf{f}(p) \rvert$ 的函数 $\phi$ 在 $X$ 上连续。

## Remark 4.15

我们为度量空间的子集 $E\subset X$ 上的函数定义了连续性的概念。然而，在 [[#Definition 4.7 continuous 连续的]] 中，$E$ 的补集对于函数 $f\colon E\to Y$ 的连续性没有任何影响（这与函数的极限不同），因此如果我们直接将 $f$ 视为从度量空间 $E$ 到 $Y$ 的函数，我们不会丢失任何信息。这表明我们不需要讨论定义在子集上的函数，直接研究从度量空间到度量空间的函数即可。这可以简化一些定理的表述与证明。

# Continuity and Compactness 连续性与紧致性

## Definition 4.16 bounded 有界的

称函数 $\mathbf{f}\colon E\to \mathbb{R}^{k}$ 有界，如果存在 $M>0$ 使得对任意 $x \in E$ 有 $\lvert \mathbf{f}(x) \rvert\leq M$。

一个等价定义是，$f$ 有界如果 $f(E)$ 是有界集。

## Theorem 4.17

设 $f$ 是一个从紧致度量空间 $X$ 到度量空间 $Y$ 的连续函数，则 $f(X)$ 是紧致集。

### Proof

设 $\{ V_{\alpha} \}$ 是 $f(X)$ 的一个开覆盖，则对任意 $\alpha$，$f^{-1}(V_{\alpha})$ 是开集，从而 $\{ f^{-1}(V_{\alpha}) \}$ 是 $X$ 的开覆盖，于是存在 $\alpha_{1},\dots,\alpha_{n}$ 使得

$$
\begin{gather}
X\subset f^{-1}(V_{\alpha_{1}})\cup\dots \cup f^{-1}(V_{\alpha_{n}})
\end{gather}
$$

由于 $f(f^{-1}(E))\subset E$，因此

$$
\begin{gather}
f(X)\subset V_{\alpha_{1}}\cup \dots \cup V_{\alpha_{n}}
\end{gather}
$$

即证 $f(X)$ 紧致。

## Theorem 4.18

设 $\mathbf{f}$ 是一个从紧致度量空间 $X$ 到 $\mathbb{R}^{k}$ 的连续函数，则 $\mathbf{f}(X)$ 闭且有界。

### Proof

根据 [[#Theorem 4.17]] 以及 Heine-Borel 定理即证。

## Theorem 4.19 (最值定理)

设 $f$ 是一个紧致度量空间 $X$ 上的连续实值函数，令

$$
\begin{gather}
M=\sup_{p \in X} f(p), \quad m=\inf_{p \in X} f(p)
\end{gather}
$$

则存在 $p,q \in X$ 使得 $f(p)=M,f(q)=m$。

换句话说，连续函数在紧致集上能够取到最大值和最小值。

### Proof

[[#Theorem 4.18]] 表明 $f(X)$ 是 $\mathbb{R}$ 上的有界闭集，因此根据 [[2 Basic Topology#Theorem 2.28]] 知 $f(X)$ 包含了

$$
\begin{gather}
M=\sup f(X), \quad m=\inf f(X)
\end{gather}
$$

即证存在 $p,q \in X$ 使得 $M=f(p),m=f(q)$。

## Theorem 4.20

设 $f$ 是一个从紧致度量空间 $X$ 到度量空间 $Y$ 的连续双射，则定义为

$$
\begin{gather}
f^{-1}(f(x))=x \quad (x \in X)
\end{gather}
$$

的反函数 $f^{-1}\colon Y\to X$ 是一个连续函数。

### Proof

对 $f^{-1}$ 应用 [[#Theorem 4.10]]，我们只需证明 $f$ 是一个开映射：对任意开集 $V\subset X$，$f(V)$ 在 $Y$ 中开。

固定 $V$，$V^{c}$ 是紧致集 $X$ 中的闭集，从而也是紧致集，因此 $f(V^{c})$ 是紧致集，因而是 $Y$ 中的闭集。由于 $f$ 是双射，因此 $f(V)$ 是 $f(V^{c})$ 的补集，从而是 $Y$ 中的开集。

## Definition 4.21 uniformly continuous 一致连续

设 $f$ 是一个从度量空间 $X$ 到度量空间 $Y$ 的映射，称 $f$ 在 $X$ 上一致连续，如果对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $p,q \in X$ 有

$$
\begin{gather}
d_{X}(p,q)<\delta \implies d_{Y}(f(p),f(q))<\varepsilon
\end{gather}
$$

我们来考虑一下一致连续与连续性的区别。

首先，一致连续是函数在某个集合上的性质，而连续性可以对一个点进行定义。问函数在某个点上是否一致连续是无意义的。

另一方面，在集合上连续与在集合上一致连续的区别在于量词的顺序：如果 $f$ 在 $X$ 上连续，那么对任意 $p \in X$ 和 $\varepsilon>0$，存在 $\delta>0$ 使得

$$
\begin{gather}
d_{X}(p,q)<\delta \implies d_{Y}(f(p),f(q))<\varepsilon
\end{gather}
$$

注意这里的 $\delta$ 同时依赖于 $p$ 和 $\varepsilon$。对于一致连续，我们可以取一个 $\delta$，它只依赖于 $\varepsilon$，而对任意 $p,q \in X$ 都适用。

显然，一致连续函数一定是连续函数，反之则不然。不过，下面的定理表明，在紧致集上这两者等价。

## Theorem 4.22

设 $f$ 是一个从紧致度量空间 $X$ 到度量空间 $Y$ 的连续函数，则 $f$ 在 $X$ 上一致连续。

### Motivation

在以上定理的证明中我们将要用到的一个结论是：连续函数在局部（一点的某个邻域内）是一致连续的。

这是因为连续函数 $f$ 在 $B_{X}(x,\delta)$ 内有如下性质：对任意 $p,q \in B_{X}(x,\delta)$，有

$$
\begin{gather}
d_{Y}(f(p),f(q))\leq d_{Y}(f(p),f(x))+d_{Y}(f(x),f(q))<\frac{\varepsilon}{2}+\frac{\varepsilon}{2}=\varepsilon
\end{gather}
$$

因此 $f$ 在 $B_{X}(x,\delta)$ 上一致连续。（事实上，我们有更强的结论：$\operatorname{diam} f(B_{X}(x,\delta))\leq\varepsilon$，因为在邻域内我们不需要选取 $\delta$。）

要将局部一致连续加强为全局一致连续，这里就是 $X$ 的紧致性发挥作用的时刻：它允许我们用有限个这样的邻域 $B_{X}(x,\delta)$ 覆盖 $X$，而从单个邻域到有限个邻域的推广是容易实现的。

### Proof

根据连续性，对任意 $p \in X$，存在 $\delta_{p}>0$ 使得 $f$ 在 $B_{X}(p,\delta_{p})$ 上一致连续。所有开球 $\{ B_{X}(p,\delta_{p} /2) \}_{p \in X}$ 覆盖 $X$，从而存在 $p_{1},\dots,p_{n}\in X$ 以及 $\delta_{1},\dots,\delta_{n}>0$ 使得

$$
\begin{gather}
X \subset B_{X}\left( p_{1},\frac{\delta_{1}}{2} \right)\cup \dots \cup B_{X}\left( p_{n},\frac{\delta_{n}}{2} \right)
\end{gather}
$$

且 $f$ 在 $B_{X}(p_{j},\delta_{j})$ 上一致连续。

取

$$
\begin{gather}
\delta=\frac{1}{2} \min (\delta_{1},\dots,\delta_{n})>0
\end{gather}
$$

设 $p,q \in X$ 满足 $d_{X}(p,q)<\delta$，则存在 $m$ 使得

$$
\begin{gather}
d_{X}(p,p_{m})< \frac{\delta_{m}}{2}
\end{gather}
$$

则

$$
\begin{gather}
d_{X}(q,p_{m})\leq d_{X}(q,p)+d_{X}(p,p_{m})<\delta+\frac{\delta_{m}}{2}\leq \delta_{m}
\end{gather}
$$

于是 $p,q \in B_{X}(p_{m},\delta_{m})$，从而由局部一致连续性得 $d_{Y}(f(p),f(q))<\varepsilon$。

下面我们来证明 [[#Theorem 4.17]]，[[#Theorem 4.18]]，[[#Theorem 4.22]] 中紧致性的假设是必要的。

## Theorem 4.23

设 $E\subset \mathbb{R}$ 是一个非紧致无限集，则

1. 存在 $E$ 上的连续函数，它不是有界的。
2. 存在 $E$ 上的有界连续函数，其没有最大值。

如果进一步，$E$ 是有界的，那么

3. 存在 $E$ 上的连续函数，其不是一致连续的。

### Proof

首先假设 $E$ 是有界的，则存在 $E$ 的极限点 $x_{0}\not\in E$。考虑

$$
\begin{gather}
f(x)=\frac{1}{x-x_{0}} \quad (x \in E)
\end{gather}
$$

则显然 $f$ 是无界的。此外，它也不是一致连续的：任取 $\varepsilon>0$ 和 $\delta>0$，并取 $x \in E$ 使得 $\lvert x-x_{0} \rvert<\delta /2$。由于当 $x\to x_{0}$ 时 $\lvert f(x) \rvert \to \infty$，因此我们可以取 $\lvert t-x_{0} \rvert<\delta /2$ 使得 $\lvert f(t)-f(x) \rvert\geq\varepsilon$，即使此时 $\lvert t-x \rvert<\delta$。

另一方面，考虑

$$
\begin{gather}
g(x)=\frac{1}{1+(x-x_{0})^{2}} \quad (x \in E)
\end{gather}
$$

则 $g$ 是 $E$ 上的有界连续函数，但它取不到最大值 $\sup g(x)=1$。

如果 $E$ 是无界集，则 $f(x)=x$ 满足 (1) 的要求，而

$$
\begin{gather}
h(x)=\frac{x^{2}}{1+x^{2}} \quad (x \in E)
\end{gather}
$$

满足 (2) 的要求：$h(x)<1$ 而 $\sup h(x)=1$。

(3) 中 $E$ 有界性的要求是必要的。例如，设 $E=\mathbb{Z}$，则 $E$ 上的任意函数都是一致连续的：取 $\delta<1$ 即可。

最后我们再给出一个例子，表明 [[#Theorem 4.20]] 中紧致性的假设也是必要的。

## Example 4.24

令 $X=[0,2\pi)$，定义

$$
\begin{gather}
\mathbf{f}(t)=(\cos t,\sin t) \quad (0\leq t<2\pi)
\end{gather}
$$

我们现在还未定义三角函数，但现在我们先将它们的连续性视为已知，则 $\mathbf{f}$ 就是从 $X$ 到 $\mathbb{R}^{2}$ 上的单位圆的一个连续双射。

然而，它的反函数在 $(1,0)$ 这一点从 $0$ 跳变到 $2\pi$，从而不是连续的。当然，此时的 $X$ 显然不是紧致集。

# Continuity and Connectedness 连续性与连通性

## Theorem 4.25

设 $f$ 是一个从度量空间 $X$ 到度量空间 $Y$ 的连续函数，$E\subset X$ 是连通集，则 $f(E)$ 也是连通集。

### Proof

我们用反证法。假设 $f(E)=A\cup B$，其中 $A,B$ 是非空分离集，令 $G=E\cap f^{-1}(A)$，$H=E\cap f^{-1}(B)$，则 $E=G\cup H$，且 $G,H$ 非空。

由于 $A\subset \overline{A}$，故 $G\subset f^{-1}(\overline{A})$，根据连续性，后者是闭集。从而 $\overline{G}\subset f^{-1}(\overline{A})$，故 $f(\overline{G})\subset \overline{A}$。由于 $f(H)=B$，且 $\overline{A}\cap B=\varnothing$，我们可得 $\overline{G}\cap H=\varnothing$。

同理可得 $G\cap \overline{H}=\varnothing$，因此 $G,H$ 是非空分离集，这与 $E$ 的连通性矛盾。

## Theorem 4.26 (介值定理)

设 $f$ 是区间 $[a,b]$ 上的连续实值函数，如果 $f(a)<f(b)$ 且 $c$ 是任意满足 $f(a)<c<f(b)$ 的实数，则存在 $x \in(a,b)$ 使得 $f(x)=c$。

对于 $f(a)>f(b)$ 的情况有类似的结论成立。结合闭区间 $[a,b]$ 是紧致集的事实，我们可知 $f$ 在 $[a,b]$ 上的值构成一个区间 $[m,M]$，其中 $m,M$ 分别是 $f$ 在 $[a,b]$ 上的最小值和最大值。

### Proof

根据 [[#Theorem 4.25]] 以及 [[2 Basic Topology#Theorem 2.50]] 即证。

# Discontinuities 间断点

如果 $f$ 在定义域中的点 $x$ 处不连续，我们就称 $f$ 在 $x$ 处间断。如果 $f$ 是定义在 $E\subset \mathbb{R}$ 上的函数，那么我们通常将 $f$ 的间断点分成两类。在这之前，我们需要讨论 $f$ 的单边极限。

## Definition 4.27 right-hand limit 右极限，left-hand limit 左极限

设 $f$ 在 $(a,b)$ 上有定义，取 $a\leq x<b$，我们定义 $f$ 在 $x$ 处的右极限

$$
\begin{gather}
\lim_{ t \to x+ } f(t)=f(x+)=q
\end{gather}
$$

如果对任意 $(x,b)$ 中满足 $t_{n}\to x$ 的序列 $(t_{n})$ 有 $f(t_{n})\to q$。

取 $a<x\leq b$，我们类似地定义 $f$ 在 $x$ 处的左极限 $\lim_{ t \to x- }f(t)=f(x-)$，其中我们将序列 $(t_{n})$ 限制在 $(a,x)$ 中。

## Proposition 4.28

对任意 $x \in(a,b)$，$\lim_{ t \to x }f(t)$ 存在当且仅当

$$
\begin{gather}
f(x+)=f(x-)=\lim_{ t \to x } f(t)
\end{gather}
$$

### Proof

利用与 [[#Theorem 4.2 (Heine)]] 的证明中相同的方法，我们可以给出左右极限的一个 $\varepsilon-\delta$ 定义：$f(x+)=q$ 当且仅当对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $t \in(a,b)$ 有

$$
\begin{gather}
x<t<x+\delta \implies \lvert f(t)-q \rvert <\varepsilon
\end{gather}
$$

$f(x-)=q$ 是类似的，其中我们将 $x<t<x+\delta$ 替换为 $x-\delta<t<x$。

比较一下 $\lim_{ t \to x }f(t)=q$ 的定义：对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $t \in(a,b)$ 有

$$
\begin{gather}
0<\lvert t-x \rvert <\delta \implies \lvert f(t)-q \rvert <\varepsilon
\end{gather}
$$

就完成了证明。

## Definition 4.29

设 $f$ 在 $(a,b)$ 上有定义，如果 $f$ 在 $x$ 处间断，且 $f(x+)$ 和 $f(x-)$ 都存在，则称 $x$ 是 $f$ 的一个第一类间断点，或简单间断点。否则就称 $x$ 是一个第二类间断点。

在简单间断点中又分为两类：如果 $f(x+)=f(x-)\neq f(x)$，则称 $x$ 是一个可去间断点；如果 $f(x+)\neq f(x-)$，则称 $x$ 是一个跳跃间断点。

## Example 4.30

(a) 函数

$$
\begin{gather}
f(x)=\begin{cases}
1, & x \in \mathbb{Q} \\
0, & x \in \mathbb{R}\setminus \mathbb{Q}
\end{cases}
\end{gather}
$$

在任意点 $x$ 上都有第二类间断点，因为 $f(x+)$ 和 $f(x-)$ 都不存在。（根据有理数和无理数的稠密性，我们总能找到趋于 $x$ 的有理数列和无理数列，两种序列的极限分别是 $1$ 和 $0$。）

(b) 函数

$$
\begin{gather}
f(x)=\begin{cases}
x, & x \in \mathbb{Q} \\
0, & x \in \mathbb{R}\setminus \mathbb{Q}
\end{cases}
\end{gather}
$$

在 $x=0$ 连续，而在其他点处有第二类间断点。

(c) 函数

$$
\begin{gather}
f(x)=\begin{cases}
x+2, & -3<x<-2 \\
-x-2, & -2\leq x<0 \\
x+2, & 0\leq x<1
\end{cases}
\end{gather}
$$

在 $x=0$ 处有一个跳跃间断点。其在 $(-3,1)$ 的其他点处连续。

(d) 函数

$$
\begin{gather}
f(x)=\begin{cases}
\sin(1 /x), & x\neq 0 \\
0, & x=0
\end{cases}
\end{gather}
$$

在 $x=0$ 处有第二类间断点，在其他点处连续。该例证明了 [[#Theorem 4.26 (介值定理)]] 的逆命题不成立：在 $x=0$ 附近，$f(x)$ 可以取到 $[-1,1]$ 上的任意点，但 $f$ 在 $0$ 处不连续。

# Monotonic Functions 单调函数

## Definition 4.31 monotonically increasing (decreasing) 单调递增（递减）

设 $f$ 是 $(a,b)$ 上的实值函数，称 $f$ 是单调递增（递减）的，如果对任意 $a<x<y<b$ 有 $f(x)\leq f(y)$（$f(x)\geq f(y)$）。单调递增函数与单调递减函数合称为单调函数。

## Theorem 4.32

设 $f$ 在 $(a,b)$ 上单调递增，则对任意 $x \in(a,b)$，$f(x+)$ 和 $f(x-)$ 均存在，并且

$$
\begin{gather}
\sup_{a<t<x} f(t)=f(x-)\leq f(x)\leq f(x+)=\inf_{x<t<b} f(t)
\end{gather}
$$

此外，如果 $a<x<y<b$，那么

$$
\begin{gather}
f(x+)\leq f(y-)
\end{gather}
$$

对单调递减函数也有类似的结论成立。

### Proof

根据单调递增性质，$\{ f(t) : a<t<x \}$ 有上界 $f(x)$，因而有上确界 $A\leq f(x)$，我们要证 $A=f(x-)$。

给定 $\varepsilon>0$，根据上确界的性质，存在 $\delta>0$ 使得

$$
\begin{gather}
A-\varepsilon<f(x-\delta)\leq A
\end{gather}
$$

从而对 $x-\delta<t<x$ 有

$$
\begin{gather}
A-\varepsilon<f(x-\delta)\leq f(t)\leq A
\end{gather}
$$

即证 $f(x-)=A$。同理可证 $f(x)\leq f(x+)=\inf_{x<t<b}f(t)$。

接下来，设 $a<x<y<b$，则我们有

$$
\begin{gather}
f(x+)=\inf_{x<t<b} f(t)=\inf_{x<t<y} f(t) \\
f(y-)=\sup_{a<t<y} f(t)=\sup_{x<t<y} f(t)
\end{gather}
$$

从而有 $f(x+)\leq f(y-)$。

## Corollary 4.33

单调函数没有第二类间断点。

## Theorem 4.34

$(a,b)$ 上的单调函数 $f$ 最多有可数个间断点。

### Proof

假设 $f$ 是单调递增函数，单调递减函数同理。$E$ 是 $f$ 的间断点构成的集合。根据 [[#Theorem 4.32]]，单调函数只有跳跃间断点。

对任意 $x \in E$，各个开区间 $(f(x-),f(x+))$ 是两两不交的，因为 $x_{1}<x_{2}$ 时 $f(x_{1}+)\leq f(x_{2}-)$。我们取有理数 $r(x)\in(f(x-),f(x+))$，则定义为

$$
\begin{gather}
x \mapsto r(x) \in \mathbb{Q} \cap (f(x-),f(x+))
\end{gather}
$$

的函数 $r\colon E\to \mathbb{Q}$ 的函数是一个单射，这表明 $E$ 与 $\mathbb{Q}$ 的一个子集等势，从而是至多可数的。

## Remark 4.35

需要注意的是，即使单调函数的间断点最多只有可数个，但这不代表这些间断点都是孤立点。事实上，给定任意可数集 $E\subset(a,b)$，我们都能构造一个单调递增函数 $f$ 使得它的间断点构成的集合恰为 $E$。

为此，将 $E$ 中的元素排成一列 $(x_{n})$，并取任意一列正数 $(c_{n})$ 使得 $\sum_{n=1}^{\infty}c_{n}$ 收敛。定义

$$
\begin{gather}
f(x)=\sum_{x_{n}< x} c_{n} \quad (a<x<b)
\end{gather}
$$

显然以上级数对任意 $x$ 都绝对收敛，因此我们可以按任意顺序对小于 $x$ 的 $x_{n}$ 求和。容易验证函数 $f$ 满足以下性质：

1. $f$ 在 $(a,b)$ 上单调递增，
2. $f$ 在 $E$ 上的任意点处间断，特别地，$f(x_{n}+)-f(x_{n}-)=c_{n}$，
3. $f$ 在 $(a,b)\setminus E$ 上连续。

此外，我们还可知 $f(x-)=f(x)$ 对任意 $x \in(a,b)$ 成立。满足这一性质的函数 $f$ 称为是左连续的。如果我们将 $x_{n}<x$ 替换为 $x_{n}\leq x$，那么此时 $f$ 就是右连续的。

（证明思路：由于 $\sum c_{n}$ 收敛，因此对任意 $\varepsilon>0$，存在 $N$ 使得 $s-s_{N}=\sum_{n=N+1}^{\infty}c_{n}<\varepsilon$，于是只需考虑有限个点 $x_{1},\dots,x_{N}$ 的影响。）

# Infinite Limits and Limits at Infinity 无穷极限与无穷远处的极限

有时候，我们需要处理极限为无穷的情况（例如 $x\to 0$ 时 $1 /x$ 的极限）或者在无穷远处的极限（形如 $\lim_{ x \to +\infty }f(x)$）。为了将这些情况包含进 [[#Definition 4.1]]，我们需要用邻域的语言重新叙述。之前我们已经定义了 $x \in \mathbb{R}$ 的邻域为 $B(x,\delta)=(x-\delta,x+\delta)$。

## Definition 4.36

对任意 $c \in \mathbb{R}$，定义开射线 $(c,+\infty)=\{ x \in \mathbb{R} : x>c \}$ 为 $+\infty$ 的一个邻域。类似地，定义 $(-\infty,c)$ 为 $-\infty$ 的一个邻域。

## Definition 4.37

设 $f$ 是定义在 $E\subset \mathbb{R}$ 上的实值函数，称 $t\to x$ 时 $f(t)\to A$，或

$$
\begin{gather}
\lim_{ t \to x } f(t)=A
\end{gather}
$$

其中 $x,A \in \overline{\mathbb{R}}$，如果对任意 $A$ 的邻域 $V$，存在 $x$ 的邻域 $U$，使得 $U\cap E\setminus \{ x \}\neq \varnothing$ 且 $f(U\cap E \setminus \{ x \})\subset V$。

容易证明当 $x,A \in \mathbb{R}$ 时，以上定义与 [[#Definition 4.1]] 一致。在这一定义下，[[#Theorem 4.5]] 仍然成立，其证明只需对各个无穷情况分类讨论即可，因此我们略去。

## Theorem 4.38

设 $f,g$ 是定义在 $E\subset \mathbb{R}$ 上的实值函数，假设

$$
\begin{gather}
f(t)\to A, \quad g(t)\to B \quad (t\to x)
\end{gather}
$$

则

1. $f(t)\to A'$ 蕴含 $A=A'$，
2. $(f+g)(t)\to A+B$，
3. $(fg)(t)\to AB$，
4. $(f /g)(t)\to A /B$。

只要其中不出现 $\infty-\infty,0\cdot \infty,\infty /\infty,A /0$ 等未定式。