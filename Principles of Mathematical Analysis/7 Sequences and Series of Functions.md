在本章中我们主要考虑的是定义在度量空间上的复值函数，尽管绝大多数定理都可以推广到向量值函数或者取值在完备度量空间中的函数。我们选择采用这一简单框架是为了突出极限的交换过程中出现的问题。

# Discussion of the Main Problem 主要问题的讨论

## Definition 7.1 pointwise converge 逐点收敛

设 $(f_{n})_{n=1}^{\infty}$ 是 $E$ 上的一列函数，满足对任意 $x \in E$，序列 $(f_{n}(x))$ 收敛。定义 $E$ 上的函数 $f$ 为

$$
\begin{gather}
f(x)=\lim_{ n \to \infty } f_{n}(x) \quad (x \in E)
\end{gather}
$$

称 $f$ 是序列 $(f_{n})$ 的极限或者逐点极限。

类似地，如果 $\sum f_{n}(x)$ 对任意 $x \in E$ 收敛，定义

$$
\begin{gather}
f(x)=\sum_{n=1}^{\infty} f_{n}(x) \quad (x \in E)
\end{gather}
$$

称 $f$ 是级数 $\sum f_{n}$ 的和。

本章的主要问题是，在函数序列的极限过程中，有哪些性质能够保留下来。例如，如果 $f_{n}$ 都是连续、可微、可积的，那么它们的极限 $f$ 是否也是连续、可微、可积的？$f_{n}'$ 与 $f'$，或者 $\int f_{n}$ 与 $\int f$ 的关系如何？

说 $f$ 在一个极限点 $x$ 处连续意味着

$$
\begin{gather}
\lim_{ t \to x } f(t)=f(x)
\end{gather}
$$

于是，问一列连续函数的极限是否是连续函数等价于问是否有等式

$$
\begin{gather}
\lim_{ t \to x } \lim_{ n \to \infty } f_{n}(t)=\lim_{ n \to \infty } \lim_{ t \to x } f_{n}(t)
\end{gather}
$$

换句话说，两个极限过程是否能够交换而不影响结果。

下面我们将给出若干例子，说明在一般情况下，不能在不影响结果的情况下交换极限。

## Example 7.2

定义

$$
\begin{gather}
s_{m,n}=\frac{m}{m+n}
\end{gather}
$$

则对于固定的 $n$，有

$$
\begin{gather}
\lim_{ m \to \infty } s_{m,n}=1
\end{gather}
$$

从而

$$
\begin{gather}
\lim_{ n \to \infty } \lim_{ m \to \infty } s_{m,n}=1
\end{gather}
$$

然而，在另一方面，对于固定的 $m$，有

$$
\begin{gather}
\lim_{ n \to \infty } s_{m,n}=0
\end{gather}
$$

从而

$$
\begin{gather}
\lim_{ m \to \infty } \lim_{ n \to \infty } s_{m,n}=0
\end{gather}
$$

## Example 7.3

定义

$$
\begin{gather}
f_{n}(x)=\frac{x^{2}}{(1+x^{2})^{n}} \quad (x \in \mathbb{R}, n=0,1,2,\dots)
\end{gather}
$$

并考虑

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} f_{n}(x)=\sum_{n=0}^{\infty} \frac{x^{2}}{(1+x^{2})^{n}}
\end{gather}
$$

当 $x=0$ 时，$f_{n}(0)=0$，故 $f(0)=0$。当 $x\neq 0$ 时，$f(x)$ 是一个收敛的几何级数，其和为 $1+x^{2}$，从而

$$
\begin{gather}
f(x)=\begin{cases}
0, & x=0 \\
1+x^{2}, & x\neq 0
\end{cases}
\end{gather}
$$

因此一列连续函数的极限不一定是连续的。

## Example 7.4

定义

$$
\begin{gather}
f_{m}(x)=\lim_{ n \to \infty } (\cos(m! \pi x))^{2n}
\end{gather}
$$

当 $m! x$ 是一个整数时，$f_{m}(x)=1$，对于其他的 $x$ 值，$f_{m}(x)=0$。因此函数

$$
\begin{gather}
f(x)=\lim_{ m \to \infty } f_{m}(x)
\end{gather}
$$

在 $x$ 为无理数时等于 $0$，在 $x$ 为有理数时等于 $1$，即

$$
\begin{gather}
\lim_{ m \to \infty } \lim_{ n \to \infty } (\cos(m! \pi x))^{2n}=\begin{cases}
1, & x \in \mathbb{Q} \\
0, & x \not\in \mathbb{Q}
\end{cases}
\end{gather}
$$

因此一列连续函数的极限可以不是 Riemann 可积的，甚至可以是处处不连续的。

## Example 7.5

令

$$
\begin{gather}
f_{n}(x)=\frac{\sin nx}{\sqrt{ n }} \quad (x \in \mathbb{R}, n=1,2,3,\dots)
\end{gather}
$$

则

$$
\begin{gather}
f(x)=\lim_{ n \to \infty } f_{n}(x)=0
\end{gather}
$$

从而 $f'(x)=0$。然而

$$
\begin{gather}
f_{n}'(x)=\sqrt{ n } \cos nx
\end{gather}
$$

因此 $(f_{n}')$ 不收敛于 $f'$。

## Example 7.6

令

$$
\begin{gather}
f_{n}(x)=n^{2}x(1-x^{2})^{n} \quad (0\leq x\leq 1, n=1,2,\dots)
\end{gather}
$$

对于 $0<x\leq 1$，有

$$
\begin{gather}
f(x)=\lim_{ n \to \infty } f_{n}(x)=0
\end{gather}
$$

由于 $f_{n}(0)=0$，因此 $f=0$。简单的计算表明

$$
\begin{gather}
\int _{0}^{1} x(1-x^{2})^{n} \, \mathrm{d}x =\frac{1}{2n+2}
\end{gather}
$$

因此我们有

$$
\begin{gather}
\int _{0}^{1} f_{n}(x) \, \mathrm{d}x = \frac{n^{2}}{2n+2} \to +\infty
\end{gather}
$$

这表明一列函数积分的极限不一定等于极限函数的积分，它甚至可以不存在。

以上的五个例子表明，随意地交换极限过程将会导致错误的发生。要使得这种交换得以成立，我们必须引入一种比逐点收敛更强的收敛模式。

# Uniform Convergence 一致收敛

## Definition 7.7 uniformly converge 一致收敛

称一列定义在 $E$ 上的函数 $(f_{n})$ 一致收敛于 $f$，如果对任意 $\varepsilon>0$，存在 $N \in \mathbb{N}^{*}$ 使得 $n\geq N,x \in E$ 蕴含

$$
\begin{gather}
\lvert f_{n}(x)-f(x) \rvert <\varepsilon
\end{gather}
$$

称级数 $\sum f_{n}$ 在 $E$ 上一致收敛于 $f$，如果其部分和序列

$$
\begin{gather}
s_{n}(x)=\sum_{i=1}^{n} f_{i}(x)
\end{gather}
$$

一致收敛于 $f$。

### Motivation

就如连续性与一致连续性的关系一样，一致收敛与逐点收敛的区别仅在于量词的顺序：在逐点收敛中，整数 $N$ 的取值取决于 $\varepsilon$ 和 $x$；而在一致收敛中，整数 $N$ 仅取决于 $\varepsilon$，它对于所有 $x \in E$ 都成立，我们说 $f_{n}$ 的收敛性“关于 $x$ 是一致的”。

以下定理通常称为一致收敛性的 Cauchy 准则。

## Theorem 7.8

设 $(f_{n})$ 是定义在 $E$ 上的一列函数，它一致收敛当且仅当对任意 $\varepsilon>0$，存在 $N \in \mathbb{N}^{*}$ 使得 $m,n\geq N,x \in E$ 蕴含

$$
\begin{gather}
\lvert f_{m}(x)-f_{n}(x) \rvert <\varepsilon
\end{gather}
$$

### Proof

假设 $(f_{n})$ 一致收敛于 $f$，则存在 $N$ 使得 $n\geq N,x \in E$ 蕴含

$$
\begin{gather}
\lvert f_{n}(x)-f(x) \rvert <\varepsilon
\end{gather}
$$

取 $m,n\geq N$，则有

$$
\begin{gather}
\lvert f_{m}(x)-f_{n}(x) \rvert \leq \lvert f_{m}(x)-f(x) \rvert +\lvert f(x)-f_{n}(x) \rvert <2\varepsilon
\end{gather}
$$

反之，如果 $(f_{n})$ 满足 Cauchy 条件，则 $(f_{n}(x))$ 是 $\mathbb{C}$ 中的 Cauchy 序列，从而收敛。我们定义

$$
\begin{gather}
f(x)=\lim_{ n \to \infty } f_{n}(x)
\end{gather}
$$

下面我们要证以上收敛是一致的。

给定 $\varepsilon>0$，取 $N$ 使得 $m,n\geq N,x \in E$ 蕴含

$$
\begin{gather}
\lvert f_{m}(x)-f_{n}(x) \rvert <\varepsilon
\end{gather}
$$

固定 $n$，令 $m\to \infty$，则有

$$
\begin{gather}
\lvert f_{n}(x)-f(x) \rvert <\varepsilon
\end{gather}
$$

对任意 $n\geq N$ 和 $x \in E$ 成立。这就完成了证明。

注意，在以上定理中我们可以将复值函数 $f_{n}$ 替换为任意取值在完备度量空间 $Y$ 上的函数，因为我们唯一用到的 $\mathbb{C}$ 的性质就是它的完备性（Cauchy 序列有极限）。

一致收敛性的一个等价形式如下。

## Theorem 7.9

设

$$
\begin{gather}
\lim_{ n \to \infty } f_{n}(x)=f(x) \quad (x \in E)
\end{gather}
$$

令

$$
\begin{gather}
M_{n}=\sup_{x \in E} \lvert f_{n}(x)-f(x) \rvert 
\end{gather}
$$

则在 $E$ 上 $f_{n}\to f$ 一致收敛，当且仅当 $M_{n}\to 0$。

## Theorem 7.10 (Weierstrass M 准则)

设 $(f_{n})$ 是定义在 $E$ 上一列函数，并假设

$$
\begin{gather}
\lvert f_{n}(x) \rvert \leq M_{n} \quad (x \in E, n=1,2,\dots)
\end{gather}
$$

则如果 $\sum M_{n}$ 收敛，则 $\sum f_{n}$ 一致收敛。

### Proof

如果 $\sum M_{n}$ 收敛，则根据 Cauchy 准则，对任意 $\varepsilon>0$，以及足够大的 $m,n$，有

$$
\begin{gather}
\left\lvert  \sum_{i=n}^{m} f_{i}(x)  \right\rvert \leq \sum_{i=n}^{m} M_{i}<\varepsilon
\end{gather}
$$

根据 [[#Theorem 7.8]] 即证。

# Uniform Convergence and Continuity 一致收敛与连续性

## Theorem 7.11

假设 $f_{n}\to f$ 在 $E$ 上一致收敛，$x$ 是 $E$ 的极限点，并且假设

$$
\begin{gather}
\lim_{ t \to x } f_{n}(t)=A_{n} \quad (n=1,2,\dots)
\end{gather}
$$

则 $(A_{n})$ 收敛，并且

$$
\begin{gather}
\lim_{ t \to x } f(t)=\lim_{ n \to \infty } A_{n}
\end{gather}
$$

换句话说，我们有

$$
\begin{gather}
\lim_{ t \to x } \lim_{ n \to \infty } f_{n}(t)=\lim_{ n \to \infty } \lim_{ t \to x } f_{n}(t)
\end{gather}
$$

### Proof

给定 $\varepsilon>0$，根据一致连续性，存在 $N$ 使得 $m,n\geq N, t\in E$ 蕴含

$$
\begin{gather}
\lvert f_{n}(t)-f_{m}(t) \rvert <\varepsilon
\end{gather}
$$

令 $t\to x$，可得

$$
\begin{gather}
\lvert A_{n}-A_{m} \rvert <\varepsilon
\end{gather}
$$

从而 $(A_{n})$ 是 Cauchy 序列，因而收敛，设其极限为 $A$。

根据不等式

$$
\begin{gather}
\lvert f(t)-A \rvert \leq \lvert f(t)-f_{n}(t) \rvert +\lvert f_{n}(t)-A_{n} \rvert +\lvert A_{n}-A \rvert 
\end{gather}
$$

我们需要控制右边三个表达式的大小。

对于第一项，我们应用 $(f_{n})$ 的一致收敛性：选取 $n_{0}$ 使得

$$
\begin{gather}
\lvert f_{n}(t)-f(t) \rvert <\varepsilon \quad (t \in E, n>n_{0})
\end{gather}
$$

第二项直接应用 $A_{n}$ 的定义：取 $x$ 的邻域 $V$ 使得

$$
\begin{gather}
t \in V\cap E \setminus \{ x \} \implies \lvert f_{n}(t)-A_{n} \rvert <\varepsilon
\end{gather}
$$

第三项需要应用 $A$ 的定义：取 $n>n_{0}$ 使得

$$
\begin{gather}
\lvert A_{n}-A \rvert <\varepsilon
\end{gather}
$$

综上，对于 $t \in V\cap E \setminus \{ x \}$ 有

$$
\begin{gather}
\lvert f(t)-A \rvert <3\varepsilon
\end{gather}
$$

这就完成了证明。

以上定理立即给出了以下结论：一列连续函数的一致极限是连续的。

## Theorem 7.12

如果 $(f_{n})$ 是 $E$ 上的一列连续函数，且 $f_{n}\to f$ 一致收敛，则 $f$ 在 $E$ 上连续。

以上定理的逆命题不一定成立：即使只有逐点收敛，一列连续函数的极限也可能是连续的，见 [[#Example 7.6]]。但在一些特定情况下，我们可以将逐点收敛加强为一致收敛。

## Theorem 7.13 (Dini)

设 $K$ 是紧致集，且

1. $(f_{n})$ 是 $K$ 上的一列连续函数，
2. $(f_{n})$ 在 $K$ 上逐点收敛于连续函数 $f$，
3. 对 $n=1,2,\dots$ 有 $f_{n}\geq f_{n+1}$。

则 $f_{n}\to f$ 一致收敛。

以上定理对于 $f_{n}\leq f_{n+1}$ 的序列 $(f_{n})$ 也成立。

### Proof

通过将 $f_{n},f$ 替换为 $-f_{n},-f$，我们可以将递增的函数列转化为递减的函数列。

令 $g_{n}=f_{n}-f$，则 $g_{n}$ 连续，且递减到 $0$，我们要证 $g_{n}\to 0$ 一致收敛。

给定 $\varepsilon>0$，定义 $K_{n}$ 为所有满足 $g_{n}(x)\geq\varepsilon$ 的 $x \in K$ 构成的集合。

由于 $g_{n}$ 连续，故 $K_{n}\subset K$ 是闭集，从而紧致。

由于 $g_{n}\geq g_{n+1}$，因此 $K_{n}\supset K_{n+1}$。

固定 $x \in K$，由于 $g_{n}\to 0$，故存在 $n$ 使得 $x \not\in K_{n}$，这表明 $\bigcap K_{n}=\varnothing$。

根据紧致套定理，必然存在 $N$ 使得 $K_{N}=\varnothing$（否则 $\bigcap K_{n}\neq \varnothing$），于是对于 $n\geq N$，有 $0\leq g_{n}(x)<\varepsilon$ 对任意 $x \in K$ 成立。即证 $g_{n}\to 0$ 一致收敛。

注意，以上定理中紧致性是必要的，例如

$$
\begin{gather}
f_{n}(x)=\frac{1}{nx+1} \quad (0<x<1)
\end{gather}
$$

递减到 $0$，但不一致收敛。

## Definition 7.14

如果 $X$ 是一个度量空间，定义 $C_{b}(X)$ 表示所有 $X$ 上的有界连续复值函数构成的集合。注意当 $X$ 是紧致集时，其上的连续函数自动是有界的，因此有 $C(X)=C_{b}(X)$。

我们对每个 $f \in C_{b}(X)$ 定义其上确界范数

$$
\begin{gather}
\lVert f \rVert =\sup_{x \in X} \lvert f(x) \rvert 
\end{gather}
$$

由于 $f$ 是有界的，$\lVert f \rVert<\infty$。显然 $\lVert f \rVert=0$ 当且仅当 $f=0$。此外，我们有

$$
\begin{gather}
\lvert f(x)+g(x) \rvert \leq \lvert f(x) \rvert +\lvert g(x) \rvert \leq \lVert f \rVert +\lVert g \rVert 
\end{gather}
$$

左边对 $x \in X$ 取上确界得 $\lVert f+g \rVert\leq \lVert f \rVert+\lVert g \rVert$。

根据上面的结论，如果我们定义 $f,g \in C_{b}(X)$ 之间的距离为 $\lVert f-g \rVert$，那么它满足度量的定义，因此 $C_{b}(X)$ 与其上的上确界度量构成了一个度量空间。在这一框架下，[[#Theorem 7.9]] 可以重述如下：

一列函数 $(f_{n})$ 关于 $C_{b}(X)$ 上的度量收敛于 $f$，当且仅当 $f_{n}\to f$ 一致收敛。

因此，$C_{b}(X)$ 上的上确界度量也称为一致度量，其中的闭集称为一致闭集，一个集合 $\mathcal{A}\subset C_{b}(X)$ 的闭包称为一致闭包。

## Theorem 7.15

带有上确界度量的空间 $C_{b}(X)$ 是一个完备度量空间。

### Proof

设 $(f_{n})$ 是 $C_{b}(X)$ 中的 Cauchy 序列，则对任意 $\varepsilon>0$，存在 $N$ 使得 $m,n\geq N$ 蕴含

$$
\begin{gather}
\lVert f_{n}-f_{m} \rVert =\sup_{x \in X}\lvert f_{n}(x)-f_{m}(x) \rvert <\varepsilon
\end{gather}
$$

根据 [[#Theorem 7.8]]，序列 $(f_{n})$ 一致收敛于 $f$。根据 [[#Theorem 7.12]]，$f$ 是连续函数。此外，$f$ 是有界的，因为存在 $n$ 使得 $\lvert f(x)-f_{n}(x) \rvert<1$ 对任意 $x \in X$ 成立，而 $f_{n}$ 是有界的。

因此 $f \in C_{b}(X)$，而由于 $f_{n}\to f$ 一致收敛，故 $\lVert f_{n}-f \rVert\to 0$。

# Uniform Convergence and Integration 一致收敛与积分

## Theorem 7.16

设 $\alpha$ 在 $[a,b]$ 上单调递增，$f_{n}\in \mathcal{R}(\alpha)\ (n=1,2,\dots)$，$f_{n}\to f$ 一致收敛。则在 $[a,b]$ 上 $f \in \mathcal{R}(\alpha)$，且

$$
\begin{gather}
\int _{a}^{b} f \, \mathrm{d}\alpha =\lim_{ n \to \infty } \int _{a}^{b} f_{n} \, \mathrm{d}\alpha 
\end{gather}
$$

### Proof

通过分别考虑函数的各个分量，我们只需考虑实值函数的情况。

令

$$
\begin{gather}
\varepsilon_{n}=\sup \lvert f_{n}(x)-f(x) \rvert 
\end{gather}
$$

则有

$$
\begin{gather}
f_{n}(x)-\varepsilon_{n}\leq f(x)\leq f_{n}(x)+\varepsilon_{n}
\end{gather}
$$

因此 $f$ 的上下积分满足

$$
\begin{gather}
\int (f_{n}-\varepsilon_{n}) \, \mathrm{d}\alpha \leq \underline{\int } f \, \mathrm{d}\alpha\leq \overline{\int } f \mathrm{d}\alpha\leq \int (f_{n}+\varepsilon_{n}) \, \mathrm{d}\alpha \tag{7.16.1}
\end{gather}
$$

因此

$$
\begin{gather}
0\leq \overline{\int } f \mathrm{d}\alpha-\underline{\int } f \, \mathrm{d}\alpha\leq 2\varepsilon_{n}(\alpha(b)-\alpha(a))
\end{gather}
$$

由一致收敛性，$\varepsilon_{n}\to 0$，因此 $f \in \mathcal{R}(\alpha)$。再次应用 $(7.16.1)$ 即得

$$
\begin{gather}
\left\lvert  \int f \, \mathrm{d}\alpha -\int f_{n} \, \mathrm{d}\alpha   \right\rvert \leq \varepsilon_{n}(\alpha(b)-\alpha(a))
\end{gather}
$$

这就完成了证明。

## Corollary 7.17

如果在 $[a,b]$ 上 $f_{n}\in \mathcal{R}(\alpha)$，且

$$
\begin{gather}
f=\sum_{n=1}^{\infty} f_{n}
\end{gather}
$$

一致收敛，则

$$
\begin{gather}
\int _{a}^{b} f \, \mathrm{d}\alpha =\sum_{n=1}^{\infty} \int _{a}^{b} f_{n} \, \mathrm{d}\alpha 
\end{gather}
$$

# Uniform Convergence and Differentiation 一致收敛与微分

在 [[#Example 7.5]] 中，我们看到 $(f_{n})$ 的一致收敛性无法导出 $f_{n}'\to f'$，因此我们需要更强的条件以从 $f_{n}\to f$ 得到 $f_{n}'\to f'$。

## Theorem 7.18

设 $(f_{n})$ 是一列在 $[a,b]$ 上可微的函数，且存在 $x_{0}\in [a,b]$ 使得 $(f_{n}(x_{0}))$ 收敛。如果 $(f_{n}')$ 一致收敛，则 $(f_{n})$ 一致收敛于可微函数 $f$，满足

$$
\begin{gather}
f'(x)=\lim_{ n \to \infty } f_{n}'(x) \quad (a\leq x\leq b)
\end{gather}
$$

### Proof

给定 $\varepsilon>0$，取 $N$ 使得 $n,m\geq N$ 蕴含

$$
\begin{gather}
\lvert f_{n}(x_{0})-f_{m}(x_{0}) \rvert < \varepsilon
\end{gather}
$$

且

$$
\begin{gather}
\lvert f_{n}'(t)-f_{m}'(t) \rvert < \frac{\varepsilon}{b-a} \quad (a\leq t\leq b)
\end{gather}
$$

对 $f_{n}-f_{m}$ 应用中值定理，则对任意 $x,t \in[a,b]$ 有

$$
\begin{gather}
\lvert f_{n}(x)-f_{m}(x)-f_{n}(t)+f_{m}(t) \rvert \leq \frac{\lvert x-t \rvert \varepsilon}{b-a}\leq \varepsilon \tag{7.18.1}
\end{gather}
$$

根据不等式

$$
\begin{gather}
\lvert f_{n}(x)-f_{m}(x) \rvert \leq \lvert f_{n}(x)-f_{m}(x)-f_{n}(x_{0})+f_{m}(x_{0}) \rvert +\lvert f_{n}(x_{0})-f_{m}(x_{0}) \rvert 
\end{gather}
$$

当 $n,m\geq N$ 时就有

$$
\begin{gather}
\lvert f_{n}(x)-f_{m}(x) \rvert <2\varepsilon
\end{gather}
$$

因此 $(f_{n})$ 一致收敛，设极限为 $f$。

固定 $x \in [a,b]$，定义

$$
\begin{gather}
\phi_{n}(t)=\frac{f_{n}(t)-f_{n}(x)}{t-x}, \quad \phi(t)=\frac{f(t)-f(x)}{t-x}
\end{gather}
$$

则

$$
\begin{gather}
\lim_{ t \to x } \phi_{n}(t)=f_{n}'(x)
\end{gather}
$$

$(7.18.1)$ 的第一个不等式给出

$$
\begin{gather}
\lvert \phi_{n}(t)-\phi_{m}(t) \rvert \leq \frac{\varepsilon}{b-a} \quad (a\leq t\leq b,t\neq x)
\end{gather}
$$

因此 $(\phi_{n})$ 一致收敛。由于 $f_{n}\to f$ 一致收敛，我们得到

$$
\begin{gather}
\lim_{ n \to \infty } \phi_{n}(t)=\phi(t)
\end{gather}
$$

在 $[a,b]\setminus\{ x \}$ 上一致收敛。

对 $(\phi_{n})$ 应用 [[#Theorem 7.11]]，即证

$$
\begin{gather}
f'(x)=\lim_{ t \to x } \phi(t)=\lim_{ n \to \infty } f_{n}'(x)
\end{gather}
$$

## Theorem 7.19

存在 $\mathbb{R}$ 上的实值连续函数，其处处不可微。

### Proof

定义

$$
\begin{gather}
\varphi(x)=\lvert x \rvert \quad (-1\leq x\leq 1)
\end{gather}
$$

并周期地将 $\varphi$ 的定义延拓到 $\mathbb{R}$ 上：

$$
\begin{gather}
\varphi(x+2)=\varphi(x)
\end{gather}
$$

则对任意 $s,t$ 有

$$
\begin{gather}
\lvert \varphi(s)-\varphi(t) \rvert \leq \lvert s-t \rvert 
\end{gather}
$$

因此 $\varphi$ 在 $\mathbb{R}$ 上连续。定义

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} \left( \frac{3}{4} \right)^{n} \varphi(4^{n}x)
\end{gather}
$$

由于 $0\leq\varphi\leq 1$，[[#Theorem 7.10 (Weierstrass M 准则)]] 表明级数在 $\mathbb{R}$ 上一致收敛，从而 $f$ 是连续函数。

现在固定 $x \in \mathbb{R}$ 与正整数 $m$，令

$$
\begin{gather}
\delta_{m}=\pm \frac{1}{2}\cdot 4^{-m}
\end{gather}
$$

其中我们选取 $\delta_{m}$ 的符号，使得 $4^{m}x$ 与 $4^{m}(x+\delta_{m})$ 之间没有整数。定义

$$
\gamma_{n}=\frac{\varphi(4^{n}(x+\delta_{m}))-\varphi(4^{n}x)}{\delta_{m}}
$$

当 $n>m$ 时，$4^{n}\delta_{m}$ 是一个偶数，因此 $\gamma_{n}=0$。当 $n\leq m$ 时，根据 $\varphi$ 的 Lipschitz 条件，有

$$
\begin{gather}
\lvert \gamma_{n} \rvert \leq \frac{\lvert 4^{n}(x+\delta_{m})-4^{n}x \rvert }{\lvert \delta_{m} \rvert }=4^{n}
\end{gather}
$$

由于 $\lvert \gamma_{m} \rvert=4^{m}$，我们就有

$$
\begin{align}
\left\lvert  \frac{f(x+\delta_{m})-f(x)}{\delta_{m}}  \right\rvert &= \left\lvert  \sum_{n=0}^{m} \left( \frac{3}{4} \right)^{n} \gamma_{n}  \right\rvert \\
&\geq 3^{m}-\sum_{n=0}^{m-1} 3^{n} \\
&= \frac{1}{2}(3^{m}+1)
\end{align}
$$

当 $m\to \infty$ 时 $\delta_{m}\to 0$，因此上式表明 $f$ 在 $x$ 处不可微。

# Equicontinuous Families of Functions 等度连续的函数族

在 [[3 Numerical Sequences and Series#Theorem 3.7]] 中我们看到，任何有界复值序列都有一个收敛的子列。下面我们要问，对于函数序列是否也有类似的定理成立。函数序列的特殊性在于，它具有两种不同的有界性，取决于对自变量 $x$ 的量化顺序。

## Definition 7.20 pointwise bounded 逐点有界，uniformly bounded 一致有界

设 $(f_{n})$ 是 $E$ 上的一列函数。

称 $(f_{n})$ 在 $E$ 上逐点有界，如果对任意 $x \in E$，序列 $(f_{n}(x))$ 是有界的。换句话说，存在实值函数 $\phi$ 使得

$$
\begin{gather}
\lvert f_{n}(x) \rvert \leq \phi(x) \quad (x \in E,n=1,2,\dots)
\end{gather}
$$

称 $(f_{n})$ 在 $E$ 上一致有界，如果存在 $M>0$ 使得

$$
\begin{gather}
\lvert f_{n}(x) \rvert \leq M \quad (x \in E,n=1,2,\dots)
\end{gather}
$$

### Motivation

需要明确的是，逐点有界性与一致有界性都是函数族的性质，而非单个函数的性质。这是因为，以上定义中对于函数的量化（对 $n$ 的量化）位于上界 $M$ 之后，从而 $M$ 与 $n$ 的取值无关。如果我们将 $n$ 的量化提到上界之前，我们就有性质：$(f_{n})$ 是一列有界函数，即对任意 $n \in \mathbb{N}^{*}$，存在 $M_{n}>0$ 使得

$$
\begin{gather}
\lvert f_{n}(x) \rvert \leq M_{n} \quad (x \in E)
\end{gather}
$$

从这个方面来看，有界函数列可以被称为“逐个一致有界的”。[[#Example 7.6]] 表明一列有界函数可以在不一致有界的情况下收敛，但我们容易证明，一列一致收敛的有界函数是一致有界的（参考 Cauchy 序列有界的证明）。

后面我们将证明，如果 $(f_{n})$ 在 $E$ 上逐点有界，$E_{1}\subset E$ 是一个可数集，我们可以找到一个子序列 $(f_{n_{k}})$ 使得对 $x \in E_{1}$ 有 $(f_{n_{k}}(x))$ 收敛。

然而，即使 $(f_{n})$ 是在紧致集 $E$ 上一致有界的连续函数，也不一定有子序列在 $E$ 上逐点收敛，如下例所示。

## Example 7.21

令

$$
\begin{gather}
f_{n}(x)=\sin nx \quad (0\leq x\leq 2\pi,n=1,2,\dots)
\end{gather}
$$

假设存在 $(n_{k})$ 使得 $(\sin n_{k}x)$ 逐点收敛 ，则我们有

$$
\begin{gather}
\lim_{ k \to \infty } (\sin n_{k}x-\sin n_{k+1}x)=0
\end{gather}
$$

从而

$$
\begin{gather}
\lim_{ k \to \infty } (\sin n_{k}x-\sin n_{k+1}x)^{2}=0
\end{gather}
$$

根据 Lebesgue 控制收敛定理，有

$$
\begin{gather}
\lim_{ k \to \infty } \int _{0}^{2\pi} (\sin n_{k}x-\sin n_{k+1}x)^{2} \, \mathrm{d}x =0
\end{gather}
$$

然而

$$
\begin{gather}
\int _{0}^{2\pi} (\sin n_{k}x-\sin n_{k+1}x)^{2} \, \mathrm{d}x =2\pi
\end{gather}
$$

产生矛盾。因此不存在这样的子序列。

另一个问题是，是否每个收敛序列都包含一个一致收敛的子序列。下例表明这也是不一定的，即使该序列在紧致集上一致有界。

## Example 7.22

令

$$
\begin{gather}
f_{n}(x)=\frac{x^{2}}{x^{2}+(1-nx)^{2}} \quad (0\leq x\leq 1,n=1,2,\dots)
\end{gather}
$$

则 $\lvert f_{n}(x) \rvert\leq 1$，从而 $(f_{n})$ 一致有界。此外，

$$
\begin{gather}
\lim_{ n \to \infty } f_{n}(x)=0 \quad (0\leq x\leq 1)
\end{gather}
$$

且

$$
\begin{gather}
f_{n}\left( \frac{1}{n} \right)=1
\end{gather}
$$

因此没有子序列能够一致收敛于极限 $0$。

## Definition 7.23 equicontinuous 等度连续

由 $E$ 上的复值函数 $f$ 构成的一个函数族 $\mathcal{F}$ 称为是等度连续的，如果对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $x,y \in E,f \in \mathcal{F}$ 有

$$
\begin{gather}
d(x,y)<\delta \implies \lvert f(x)-f(y) \rvert <\varepsilon
\end{gather}
$$

### Motivation

等度连续性可以视为关于函数 $f$ 一致的一致连续性：它将性质“每个函数均一致连续”中关于 $f$ 的量化放置到了 $\delta$ 的选取之后。因而，等度连续的函数族可以选取 $\delta$，其只与 $\varepsilon$ 有关，而适用于任何 $f \in \mathcal{F}$ 和 $x,y \in E$。

## Theorem 7.24

如果 $(f_{n})$ 是可数集 $E$ 上逐点有界复值函数，则存在子序列 $(f_{n_{k}})$ 使得对任意 $x \in E$ 有 $(f_{n_{k}}(x))$ 收敛。

### Proof

我们来使用所谓的“对角线法”进行证明。

将 $E$ 中的元素排成一列 $(x_{i})$，由于 $(f_{n}(x_{1}))$ 是有界的，因此存在一个子序列，记作 $(f_{1,k})$，使得 $(f_{1,k}(x_{1}))$ 收敛。

由于 $(f_{1,k}(x_{2}))$ 有界，故存在子序列，记作 $(f_{2,k})$，使得 $(f_{2,k}(x_{2}))$ 收敛。以此类推，我们就得到了序列 $S_{1},S_{2},\dots$，排成一个二维矩阵：

$$
\begin{gather}
S_{1} : f_{1,1},f_{1,2},f_{1,3},\dots \\
S_{2} : f_{2,1},f_{2,2},f_{2,3},\dots \\
S_{3} : f_{3,1},f_{3,2},f_{3,3},\dots \\
\vdots
\end{gather}
$$

其满足性质

1. $S_{n}$ 是 $S_{n-1}$ 的子序列，
2. 当 $k\to \infty$ 时，$(f_{n,k}(x_{n}))$ 收敛，
3. 函数 $f_{n}$ 在各序列中出现的顺序不变，这就是说，如果 $m<n$，那么在各个序列中，$f_{m}$ 必然排在 $f_{n}$ 之前（如果存在的话）。

现在我们取矩阵的对角线

$$
\begin{gather}
S : f_{1,1},f_{2,2},f_{3,3},\dots
\end{gather}
$$

它是 $(f_{n})$ 的一个子序列，并且除了前 $n-1$ 项外，它也是 $S_{n}$ 的一个子序列。因此，当 $n\to \infty$ 时，序列 $(f_{n,n}(x_{i}))$ 收敛，对任意 $x_{i}\in E$ 成立。

## Theorem 7.25

设 $K$ 是紧致度量空间，$f_{n}\in C(K)\ (n=1,2,\dots)$，且 $(f_{n})$ 在 $K$ 上一致收敛，则 $(f_{n})$ 在 $K$ 上等度连续。

### Proof

给定 $\varepsilon>0$，由于 $(f_{n})$ 一致收敛，因此存在 $N$ 使得

$$
\begin{gather}
\lVert f_{n}-f_{N} \rVert <\varepsilon \quad (n>N)
\end{gather}
$$

由于 $f_{i}$ 在 $K$ 上一致连续，存在 $\delta>0$ 使得对 $1\leq i\leq N$ 有

$$
\begin{gather}
d(x,y)<\delta \implies \lvert f_{i}(x)-f_{i}(y) \rvert <\varepsilon
\end{gather}
$$

（对于有限个函数，可以选取最大的那个 $\delta$ 使得 $(f_{i})_{i=1}^{N}$ 等度连续。）对于 $n>N$，我们利用不等式

$$
\begin{gather}
\lvert f_{n}(x)-f_{n}(y) \rvert \leq \lvert f_{n}(x)-f_{N}(x) \rvert +\lvert f_{N}(x)-f_{N}(y) \rvert +\lvert f_{N}(y)-f_{n}(y) \rvert 
\end{gather}
$$

得到 $d(x,y)<\delta$ 时 $\lvert f_{n}(x)-f_{n}(y) \rvert<3\varepsilon$。这就完成了证明。

## Theorem 7.26 (Arzela-Ascoli)

设 $K$ 是紧致度量空间，$f_{n}\in C(K)\ (n=1,2,\dots)$，且 $(f_{n})$ 在 $K$ 上逐点有界且等度连续，则

1. $(f_{n})$ 在 $K$ 上一致有界，
2. $(f_{n})$ 有一个一致收敛子列。

### Proof

(1) 固定 $\varepsilon>0$，根据逐点有界性，对任意 $p \in K$，存在 $\phi(p)$ 使得

$$
\begin{gather}
\lvert f_{n}(p) \rvert <\phi(p) \quad (n=1,2,\dots)
\end{gather}
$$

由等度连续性，存在 $\delta>0$，使得对任意 $x,y \in K,n \in \mathbb{N}^{*}$ 有

$$
\begin{gather}
d(x,y)<\delta \implies \lvert f_{n}(x)-f_{n}(y) \rvert <\varepsilon
\end{gather}
$$

再根据紧致性，存在有限个 $p_{1},\dots,p_{r}$ 使得

$$
\begin{gather}
K\subset B(p_{1},\delta)\cup\dots \cup B(p_{r},\delta)
\end{gather}
$$

于是对任意 $x \in K$，存在 $p_{i}$ 使得 $d(x,p_{i})<\delta$，从而

$$
\begin{gather}
\lvert f_{n}(x) \rvert \leq \lvert f_{n}(p_{i}) \rvert +\varepsilon\leq \max_{1\leq i\leq r} \phi(p_{i})+\varepsilon
\end{gather}
$$

即证 $(f_{n})$ 的一致有界性。

(2) 由于 $K$ 紧致，因此它有一个可数稠密子集：对任意 $n \in \mathbb{N}^{*}$，存在有限个半径为 $1 /n$ 的开球覆盖 $K$，这些开球的中心构成的集合记作 $E$。[[#Theorem 7.24]] 表明存在子序列 $(f_{n_{k}})$ 在 $E$ 上处处收敛。

记 $g_{i}=f_{n_{i}}$，我们要证 $(g_{i})$ 在 $K$ 上一致收敛。

固定 $\varepsilon>0$，等度连续性表明，存在 $\delta>0$ 使得对任意 $x,y \in K,i \in \mathbb{N}^{*}$ 有

$$
\begin{gather}
d(x,y)<\delta \implies \lvert g_{i}(x)-g_{i}(y) \rvert<\varepsilon 
\end{gather}
$$

由于 $E$ 在紧致集 $K$ 中稠密，因此存在有限个 $x_{1},\dots,x_{m}\in E$ 使得

$$
\begin{gather}
K\subset B(x_{1},\delta)\cup\dots \cup B(x_{m},\delta)
\end{gather}
$$

由于 $(g_{i})$ 在 $E$ 上处处收敛，因此存在 $N$ 使得 $i,j\geq N$ 蕴含

$$
\begin{gather}
\lvert g_{i}(x_{s})-g_{j}(x_{s}) \rvert <\varepsilon
\end{gather}
$$

现在取 $x \in K$，存在 $x_{s}$ 使得 $d(x,x_{s})<\delta$，于是当 $i,j\geq N$ 时，

$$
\begin{align}
\lvert g_{i}(x)-g_{j}(x) \rvert&\leq \lvert g_{i}(x)-g_{i}(x_{s}) \rvert +\lvert g_{i}(x_{s})-g_{j}(x_{s}) \rvert +\lvert g_{j}(x_{s})-g_{j}(x) \rvert  \\
&<3\varepsilon
\end{align}
$$

即证 $(g_{i})$ 一致收敛。

# The Stone-Weierstrass Theorem

## Theorem 7.27 (Weierstrass 逼近定理)

如果 $f$ 是 $[a,b]$ 上的连续复值函数，则存在一列多项式 $P_{n}$ 使得

$$
\begin{gather}
\lim_{ n \to \infty } P_{n}(x)=f(x)
\end{gather}
$$

在 $[a,b]$ 上一致收敛。如果 $f$ 是实值函数，则可以选取 $P_{n}$ 使得它也是实值函数。

### Proof

通过取

$$
\begin{gather}
g(x)=f(x)-f(0)-x(f(1)-f(0))
\end{gather}
$$

我们可以假设 $f$ 定义在 $[0,1]$ 上，并且 $f(0)=f(1)=0$。此外，我们假设在 $[0,1]$ 之外 $f(x)=0$，从而 $f$ 在 $\mathbb{R}$ 上一致连续。

下面的证明思想来源于 Fourier 分析，其中 $Q_{n}$ 称为一个“单位逼近”，而函数 $f$ 与 $Q_{n}$ 的卷积，根据单位逼近的性质，一致收敛于原函数 $f$。

令

$$
\begin{gather}
Q_{n}(x)=c_{n}(1-x^{2})^{n} \quad (n=1,2,\dots)
\end{gather}
$$

其中 $c_{n}$ 满足

$$
\begin{gather}
\int _{-1}^{1} Q_{n}(x) \, \mathrm{d}x =2 \int _{0}^{1} Q_{n}(x) \, \mathrm{d}x =1 \tag{7.27.1}
\end{gather}
$$

而根据

$$
\begin{align}
2 \int _{0}^{1} (1-x^{2})^{n} \, \mathrm{d}x &\geq 2 \int _{0}^{1 /\sqrt{ n }} (1-x^{2})^{n} \, \mathrm{d}x  \\
&\geq 2 \int _{0}^{1 /\sqrt{ n }} (1-nx^{2}) \, \mathrm{d}x  \\
&= \frac{4}{3\sqrt{ n }} \\
&> \frac{1}{\sqrt{ n }}
\end{align}
$$

因此

$$
\begin{gather}
c_{n}<\sqrt{ n }
\end{gather}
$$

取 $\delta>0$，则我们有

$$
\begin{gather}
Q_{n}(x)\leq \sqrt{ n }(1-\delta^{2})^{n} \tag{7.27.2} \quad (\delta\leq \lvert x \rvert \leq 1)
\end{gather}
$$

因此 $Q_{n}\to 0$ 在 $\delta\leq\lvert x \rvert\leq 1$ 上一致收敛。

现在令

$$
\begin{gather}
P_{n}(x)=\int _{-1}^{1} f(x+t)Q_{n}(t) \, \mathrm{d}t  \quad (0\leq x\leq 1)
\end{gather}
$$

为 $f$ 与 $Q_{n}$ 的卷积。根据 $f$ 的性质，应用变量替换公式得

$$
\begin{gather}
P_{n}(x)=\int _{-x}^{1-x} f(x+t)Q_{n}(t) \, \mathrm{d}t =\int _{0}^{1} f(t)Q_{n}(t-x) \, \mathrm{d}t 
\end{gather}
$$

它显然是一个以 $x$ 为变量的多项式。如果 $f$ 是实值函数，那么根据以上公式定义的 $P_{n}$ 也是实值多项式。

给定 $\varepsilon>0$，取 $\delta>0$ 使得

$$
\begin{gather}
\lvert x-y \rvert <\delta \implies \lvert f(x)-f(y) \rvert <\varepsilon
\end{gather}
$$

令 $M=\sup\lvert f(x) \rvert$，根据 $(7.27.1),(7.27.2)$ 以及 $Q_{n}\geq 0$，对 $0\leq x\leq 1$ 有

$$
\begin{align}
\lvert P_{n}(x)-f(x) \rvert &= \left\lvert  \int _{-1}^{1} (f(x+t)-f(x))Q_{n}(t) \, \mathrm{d}t   \right\rvert  \\
&\leq \int _{-1}^{1} \lvert f(x+t)-f(x) \rvert Q_{n}(t) \, \mathrm{d}t  \\
&\leq 2M \int _{\delta\leq\lvert x \rvert \leq 1} Q_{n}(t) \, \mathrm{d}t +\varepsilon \int _{-\delta}^{\delta} Q_{n}(t) \, \mathrm{d}t  \\
&\leq 4M \sqrt{ n }(1-\delta^{2})^{n}+\varepsilon
\end{align}
$$

当 $n$ 足够大时，可以使右侧的第一项小于 $\varepsilon$，即证 $P_{n}\to f$ 一致收敛。

## Corollary 7.28

对任意区间 $[-a,a]$，存在一列实值多项式 $P_{n}$ 使得 $P_{n}(0)=0$，并且

$$
\begin{gather}
\lim_{ n \to \infty } P_{n}(x)=\lvert x \rvert 
\end{gather}
$$

在 $[-a,a]$ 上一致收敛。

### Proof

根据 [[#Theorem 7.27 (Weierstrass 逼近定理)]]，存在实值多项式 $P_{n}^{*}$ 使得它一致收敛于绝对值函数。特别地，$P_{n}^{*}(0)\to 0$，因此

$$
\begin{gather}
P_{n}(x)=P_{n}^{*}(x)-P_{n}^{*}(0)
\end{gather}
$$

满足所求的条件。

多项式是一种性质极其优良的函数，然而，对于连续函数的逼近来说，我们并不需要多项式的全部性质。下面我们就来分离出使得多项式能够逼近连续函数的那些性质。

## Definition 7.29 algebra 代数

$E$ 上的复值函数构成的一个函数族 $\mathcal{A}$ 称为是一个代数，如果对任意 $f,g \in \mathcal{A}$ 和 $c \in \mathbb{C}$ 有

1. $f+g \in \mathcal{A}$，
2. $fg \in \mathcal{A}$，
3. $c f \in \mathcal{A}$。

这就是说，复代数 $\mathcal{A}$ 关于加法、乘法和复数数乘封闭。有时我们也需要考虑实值函数构成的实代数，此时我们只需令性质 (3) 中的 $c \in \mathbb{R}$。

如果 $\mathcal{A}$ 满足性质：如果 $f_{n}\in \mathcal{A}$ 且 $f_{n}\to f$ 一致收敛，那么 $f \in \mathcal{A}$，我们就称 $\mathcal{A}$ 是一致闭的。

设 $\mathcal{B}$ 是由 $\mathcal{A}$ 中的一致收敛级数的极限构成的函数族，则我们称 $\mathcal{B}$ 为 $\mathcal{A}$ 的一致闭包。

显然，区间 $[a,b]$ 上的多项式构成了一个代数，而 Weierstrass 逼近定理就是说，$[a,b]$ 上的连续函数集是多项式代数的一致闭包。

## Theorem 7.30

设 $\mathcal{B}$ 是一个由有界函数构成的代数 $\mathcal{A}$ 的一致闭包，则 $\mathcal{B}$ 是一个一致闭的代数。

### Proof

设 $f,g \in \mathcal{B}$，则存在 $f_{n},g_{n}\in \mathcal{A}$ 使得 $f_{n}\to f,g_{n}\to g$ 一致收敛。由于 $\mathcal{A}$ 中的函数是有界的，我们可以像 [[3 Numerical Sequences and Series#Theorem 3.3]] 那样证明

$$
\begin{gather}
f_{n}+g_{n}\to f+g, \quad f_{n}g_{n} \to fg, \quad cf_{n}\to cf
\end{gather}
$$

一致收敛。因此 $f+g,fg,cf \in \mathcal{B}$，即 $\mathcal{B}$ 是一个代数。又因为闭包一定是闭集，因此 $\mathcal{B}$ 是一致闭的。

## Definition 7.31 separate points 分离点

设 $\mathcal{A}$ 是 $E$ 上的一个函数族，称 $\mathcal{A}$ 在 $E$ 上是分离点的，如果对任意不同的 $x_{1},x_{2}\in E$，存在 $f \in \mathcal{A}$ 使得 $f(x_{1})\neq f(x_{2})$。

如果对任意 $x \in E$，存在 $g \in \mathcal{A}$ 使得 $g(x)\neq 0$，则我们就称 $\mathcal{A}$ 在 $E$ 的任意点上都不消失。

多项式集合显然是分离点且不消失的。一个反例是 $[-1,1]$ 上的偶多项式集合，因为这些函数满足 $f(x)=f(-x)$，因而无法分离 $x$ 与 $-x$。

## Theorem 7.32

设 $\mathcal{A}$ 是 $E$ 上函数构成的一个代数，$\mathcal{A}$ 在 $E$ 上分离点，并且在任何点上都不消失。假设 $x_{1},x_{2}\in E$ 是不同的点，$c_{1},c_{2}\in \mathbb{C}$（其属于 $\mathbb{R}$ 如果 $\mathcal{A}$ 是实代数），则存在 $f \in \mathcal{A}$ 使得

$$
\begin{gather}
f(x_{1})=c_{1}, \quad f(x_{2})=c_{2}
\end{gather}
$$

### Proof

根据条件，$\mathcal{A}$ 包含函数 $g,h,k$，使得

$$
\begin{gather}
g(x_{1})\neq g(x_{2}), \quad h(x_{1})\neq 0, \quad k(x_{2})\neq 0
\end{gather}
$$

取

$$
\begin{gather}
u=gk-g(x_{1})k, \quad v=gh-g(x_{2})h
\end{gather}
$$

则 $u,v \in \mathcal{A}$，$u(x_{1})=v(x_{2})=0$，$u(x_{2})\neq 0$，$v(x_{1})\neq 0$。因此

$$
\begin{gather}
f=\frac{c_{1}v}{v(x_{1})}+\frac{c_{2}u}{u(x_{2})}
\end{gather}
$$

就是所求的函数。

## Theorem 7.33 (Stone-Weierstrass)

设 $\mathcal{A}$ 是紧致集 $K$ 上的实值连续函数构成的代数，如果 $\mathcal{A}$ 在 $K$ 上分离点，并且在任何点上都不消失，则 $\mathcal{A}$ 的一致闭包 $\mathcal{B}$ 包含了 $K$ 上的所有实值连续函数。

### Proof

**第一步** 如果 $f \in \mathcal{B}$，那么 $\lvert f \rvert\in \mathcal{B}$。

令

$$
\begin{gather}
a=\sup_{x \in K} \lvert f(x) \rvert 
\end{gather}
$$

则根据 [[#Corollary 7.28]]，在 $[-a,a]$ 上存在实数 $c_{1},\dots,c_{n}$ 使得

$$
\begin{gather}
\left\lvert  \sum_{i=1}^{n} c_{i}y^{i} - \lvert y \rvert   \right\rvert <\varepsilon \quad (-a\leq y\leq a)
\end{gather}
$$

由于 $\mathcal{B}$ 是代数（根据 [[#Theorem 7.30]]），函数

$$
\begin{gather}
g=\sum_{i=1}^{n} c_{i}f^{i} \in \mathcal{B}
\end{gather}
$$

并且满足

$$
\begin{gather}
\lvert g(x)-\lvert f(x) \rvert  \rvert <\varepsilon \quad (x \in K)
\end{gather}
$$

又因为 $\mathcal{B}$ 是一致闭的，因此 $\lvert f \rvert \in \mathcal{B}$。

**第二步** $\mathcal{B}$ 是一个格（lattice）：如果 $f,g \in \mathcal{B}$，那么 $\max(f,g)$ 和 $\min(f,g)$ 都属于 $\mathcal{B}$。

根据恒等式

$$
\begin{gather}
\max(f,g)=\frac{f+g+\lvert f-g \rvert }{2} \\
\min(f,g)=\frac{f+g-\lvert f-g \rvert }{2}
\end{gather}
$$

利用第一步的结果即证。

根据归纳法，我们可以将最大值和最小值扩展到任意有限个函数：如果 $f_{1},\dots,f_{n}\in \mathcal{B}$，那么 $\max(f_{1},\dots,f_{n}),\min(f_{1},\dots,f_{n})\in \mathcal{B}$。

**第三步** 给定在 $K$ 上连续的实值函数 $f$，以及 $x \in K$，$\varepsilon>0$，存在 $g_{x}\in \mathcal{B}$ 使得 $g_{x}(x)=f(x)$ 且

$$
\begin{gather}
g_{x}(t)>f(t)-\varepsilon \quad (t \in K)
\end{gather}
$$

由于 $\mathcal{A}\subset \mathcal{B}$，$\mathcal{A}$ 满足 [[#Theorem 7.32]] 的条件，因此 $\mathcal{B}$ 也满足条件。于是，对任意 $y \in K$，存在 $h_{y}\in \mathcal{B}$ 使得

$$
\begin{gather}
h_{y}(x)=f(x), \quad h_{y}(y)=f(y)
\end{gather}
$$

根据 $h_{y}$ 的连续性，存在 $y$ 的邻域 $J_{y}$ 使得

$$
\begin{gather}
h_{y}(t)>f(t)-\varepsilon \quad (t \in J_{y})
\end{gather}
$$

由于 $K$ 是紧致的，存在有限个 $y_{1},\dots,y_{n}$ 使得

$$
\begin{gather}
K\subset J_{y_{1}}\cup \dots \cup J_{y_{n}}
\end{gather}
$$

取

$$
\begin{gather}
g_{x}=\max(h_{y_{1}},\dots,h_{y_{n}})
\end{gather}
$$

则 $g_{x} \in \mathcal{B}$，并且满足所求的条件。

**第四步** 给定在 $K$ 上连续的实值函数 $f$，和 $\varepsilon>0$，存在 $h \in \mathcal{B}$ 使得

$$
\begin{gather}
\lvert h(x)-f(x) \rvert <\varepsilon \quad (x \in K)
\end{gather}
$$

由于 $\mathcal{B}$ 是一致闭的，这就是说 $f \in \mathcal{B}$。

考虑第三步中构造的函数 $g_{x}$。根据连续性，存在 $x$ 的邻域 $V_{x}$ 使得

$$
\begin{gather}
g_{x}(t)<f(t)+\varepsilon \quad (t \in V_{x})
\end{gather}
$$

由于 $K$ 紧致，存在有限个 $x_{1},\dots,x_{m}$ 使得

$$
\begin{gather}
K\subset V_{x_{1}}\cup \dots \cup V_{x_{m}}
\end{gather}
$$

取

$$
\begin{gather}
h=\min(g_{x_{1}},\dots,g_{x_{m}})
\end{gather}
$$

根据第三步，对任意 $t \in K$ 有

$$
\begin{gather}
h(t)>f(t)-\varepsilon
\end{gather}
$$

另一方面，我们也有

$$
\begin{gather}
h(t)<f(t)+\varepsilon
\end{gather}
$$

即证

$$
\begin{gather}
\lvert h(t)-f(t) \rvert <\varepsilon \quad (t \in K)
\end{gather}
$$

[[#Theorem 7.33 (Stone-Weierstrass)]] 对复代数并不成立。事实上，我们还缺少一个条件，$\mathcal{A}$ 对于复共轭封闭：如果 $f \in \mathcal{A}$，那么 $\overline{f}\in \mathcal{A}$。实代数则自动满足了这一条件。

## Theorem 7.34

设 $\mathcal{A}$ 是紧致集 $K$ 上的复值连续函数构成的代数，其对复共轭封闭，在 $K$ 上分离点，且不在任何点上消失。则 $\mathcal{A}$ 的一致闭包 $\mathcal{B}$ 包含了 $K$ 上的所有复值连续函数。换言之，$\mathcal{A}$ 在 $C(K)$ 中稠密。

### Proof

定义 $\mathcal{A}_{\mathbb{R}}$ 包含所有 $\mathcal{A}$ 中的实值函数。

如果 $f \in \mathcal{A}$，则 $f=u+iv$，从而 $u=\frac{1}{2}(f+\overline{f}) \in \mathcal{A}_{\mathbb{R}}$。

$\mathcal{A}_{\mathbb{R}}$ 在 $K$ 上分离点：设 $x_{1}\neq x_{2}$，取 $f \in \mathcal{A}$ 使得 $f(x_{1})=0$，$f(x_{2})=1$，则 $0=u(x_{1})\neq u(x_{2})=1$。

$\mathcal{A}_{\mathbb{R}}$ 没有消失点：取 $f \in \mathcal{A}$ 使得 $f(x)\neq 0$，令 $\lambda \in \mathbb{C}$ 使得 $\lambda f(x)>0$，则 $u=\mathrm{Re}(\lambda f) \in \mathcal{A}_{\mathbb{R}}$ 满足 $u(x)\neq 0$。

根据 [[#Theorem 7.33 (Stone-Weierstrass)]]，$\mathcal{A}_{\mathbb{R}}$ 的一致闭包包含了所有 $K$ 上的实值连续函数，从而 $\mathcal{B}$ 也包含了这些函数。如果 $f \in C(K)$，则它具有形式 $f=u+iv$，$u,v \in \mathcal{B}$，从而 $f \in \mathcal{B}$。