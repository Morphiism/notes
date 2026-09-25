# Power Series 幂级数

本节我们主要研究那些由一个幂级数所定义的函数，形如

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} c_{n}x^{n} \tag{1}
\end{gather}
$$

或者更一般地，

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} c_{n}(x-a)^{n} \tag{2}
\end{gather}
$$

这些函数称为解析函数。

我们主要考虑 $x$ 取实数的情况。设 $R>0$，如果级数 $(1)$ 在 $(-R,R)$ 上收敛，我们就说 $f$ 在 $x=0$ 处可展开为幂级数。类似地，如果级数 $(2)$ 在 $(a-R,a+R)$ 上收敛，则称 $f$ 在 $x=a$ 处可展开为幂级数。通过一个变量替换 $y=x-a$，我们总可以将 $(2)$ 变换为 $(1)$，因此本节中我们可以不失一般性地假设 $a=0$。

## Theorem 8.1

假设幂级数

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} c_{n}x^{n} \tag{8.1.1}
\end{gather}
$$

在 $(-R,R)$ 上收敛，则对任意 $\varepsilon>0$，级数在 $[-R+\varepsilon,R-\varepsilon]$ 上一致收敛。函数 $f$ 在 $(-R,R)$ 上连续且可导，并且

$$
\begin{gather}
f'(x)=\sum_{n=1}^{\infty} nc_{n}x^{n-1} \quad (\lvert x \rvert <R) \tag{8.1.2}
\end{gather}
$$

### Proof

给定 $\varepsilon>0$，对于 $\lvert x \rvert\leq R-\varepsilon$，成立

$$
\begin{gather}
\lvert c_{n}x^{n} \rvert \leq \lvert c_{n}(R-\varepsilon)^{n} \rvert 
\end{gather}
$$

而由于幂级数在收敛圆内部绝对收敛，故

$$
\begin{gather}
\sum_{n=0}^{\infty} c_{n}(R-\varepsilon)^{n}
\end{gather}
$$

绝对收敛，从而由 Weierstrass M 准则知级数 $(8.1.1)$ 在 $[-R+\varepsilon,R-\varepsilon]$ 上一致收敛。从而 $f$ 在 $[-R+\varepsilon,R-\varepsilon]$ 上连续，由 $\varepsilon$ 的任意性知 $f$ 在 $(-R,R)$ 上连续。

当 $n\to \infty$ 时，$n^{1 /n}\to 1$，因此

$$
\begin{gather}
\limsup_{ n \to \infty } (n\lvert c_{n} \rvert)^{1/n}=\limsup_{ n \to \infty } \lvert c_{n} \rvert ^{1/n}
\end{gather}
$$

这表明级数 $(8.1.2)$ 的收敛半径与 $(8.1.1)$ 的收敛半径相同，因此由上面证明的结论，有 $(8.1.2)$ 在 $[-R+\varepsilon,R-\varepsilon]$ 上一致收敛。应用 [[7 Sequences and Series of Functions#Theorem 7.18]] 即证

$$
\begin{gather}
f'(x)=\sum_{n=1}^{\infty} nc_{n}x^{n-1} \quad (\lvert x \rvert \leq R-\varepsilon)
\end{gather}
$$

根据 $\varepsilon$ 的任意性即证。

## Corollary 8.2

在 [[#Theorem 8.1]] 的假设下，$f$ 在 $(-R,R)$ 上存在任意阶导数，满足

$$
\begin{gather}
f^{(k)}(x)=\sum_{n=k}^{\infty} n(n-1)\cdots (n-k+1)c_{n} x^{n-k} \quad (\lvert x \rvert <R)
\end{gather}
$$

特别地，

$$
\begin{gather}
f^{(k)}(0)=k! c_{k}
\end{gather}
$$

以上公式表明，一方面，解析函数 $f$ 在某点的幂级数完全由 $f$ 在该点的导数值决定；另一方面，如果幂级数已给定，那么我们能够直接从级数的系数中读出 $f$ 的各阶导数。

然而，需要注意的是，即使一个函数 $f$ 在某邻域内存在任意阶导数，这也不能表明它在该点由 $\sum c_{n}x^{n}$ 所定义的幂级数收敛于 $f$。此时，$f$ 在该点无法展开成幂级数，因为如果 $f(x)=\sum a_{n}x^{n}$，那么我们有

$$
\begin{gather}
a_{n}=\frac{f^{(n)}(0)}{n!}=c_{n}
\end{gather}
$$

以上论证也表明如果函数 $f$ 在某点可展开为幂级数，那么幂级数的系数是唯一确定的。

如果 $(8.1.1)$ 在端点处，例如 $x=R$ 处收敛，那么如下定理表明，函数 $f$ 不仅在 $(-R,R)$ 上连续，其也在 $x=R$ 处连续。通过变量替换 $x=y /R$，我们可以将 $(8.1.1)$ 转化为一个收敛半径为 $1$ 的幂级数，因此我们可以不失一般性地假设 $R=1$。

## Theorem 8.3 (Abel)

假设 $\sum c_{n}$ 收敛，定义

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} c_{n} x^{n} \quad (\lvert x \rvert <1)
\end{gather}
$$

则

$$
\begin{gather}
\lim_{ x \to 1 } f(x)=\sum_{n=0}^{\infty} c_{n}
\end{gather}
$$

### Proof

取 $s_{n}=\sum_{k=0}^{n}c_{k},s_{-1}=0$，则

$$
\begin{gather}
\sum_{n=0}^{m} c_{n}x^{n}=\sum_{n=0}^{m} (s_{n}-s_{n-1})x^{n}=(1-x)\sum_{n=0}^{m-1} s_{n}x^{n}+s_{m}x^{m}
\end{gather}
$$

对于 $\lvert x \rvert<1$，令 $m\to \infty$ 即得

$$
\begin{gather}
f(x)=(1-x)\sum_{n=0}^{\infty} s_{n}x^{n}
\end{gather}
$$

假设 $s=\lim_{ n \to \infty }s_{n}=\sum c_{n}$，给定 $\varepsilon>0$，取 $N$ 使得 $n\geq N$ 蕴含

$$
\begin{gather}
\lvert s-s_{n} \rvert <\varepsilon
\end{gather}
$$

则由于

$$
\begin{gather}
(1-x)\sum_{n=0}^{\infty} x^{n}=1 \quad (\lvert x \rvert <1)
\end{gather}
$$

我们有

$$
\begin{gather}
\lvert f(x)-s \rvert = \left\lvert  (1-x)\sum_{n=0}^{\infty} (s_{n}-s)x^{n}  \right\rvert \leq (1-x)\sum_{n=0}^{N} \lvert s_{n}-s \rvert +\varepsilon
\end{gather}
$$

通过取 $\delta$ 足够小，当 $x>1-\delta$ 时我们可以使右侧的第一项小于 $\varepsilon$，这就完成了证明。

## Theorem 8.4 (Fubini)

给定序列 $(a_{i,j})_{i,j=1}^{\infty}$，假设

$$
\begin{gather}
\sum_{j=1}^{\infty} \lvert a_{i,j} \rvert = b_{i} \quad (i=1,2,\dots) \tag{8.4.1}
\end{gather}
$$

并且 $\sum b_{i}$ 收敛，则

$$
\begin{gather}
\sum_{i=1}^{\infty} \sum_{j=1}^{\infty} a_{i,j}=\sum_{j=1}^{\infty} \sum_{i=1}^{\infty} a_{i,j} \tag{8.4.2}
\end{gather}
$$

换句话说，如果 $\sum_{i,j}a_{i,j}$ 绝对收敛，那么我们可以任意交换累次求和的顺序。特别地，如果 $(a_{i,j})$ 是非负序列，那么我们可以随意交换求和顺序，定理保证了，只要序列的和有限，那么交换求和顺序不会影响结果。

### Proof #1 (Rudin)

设 $E=\{ x_{0},x_{1},x_{2},\dots \}$ 是一个可数集，满足当 $n\to \infty$ 时 $x_{n}\to x_{0}$。定义

$$
\begin{align}
f_{i}(x_{0})&=\sum_{j=1}^{\infty} a_{i,j} \quad (i=1,2,\dots) \tag{8.4.3} \\
f_{i}(x_{n})&=\sum_{j=1}^{n} a_{i,j} \quad (i,n=1,2,\dots) \tag{8.4.4} \\
g(x)&=\sum_{i=1}^{\infty} f_{i}(x) \quad (x \in E) \tag{8.4.5}
\end{align}
$$

公式 $(8.4.3),(8.4.4)$，以及 $(8.4.1)$ 表明，$f_{i}$ 在 $x_{0}$ 处连续。由于 $\lvert f_{i}(x) \rvert\leq b_{i}$，级数 $(8.4.5)$ 一致收敛，因此 $g$ 也在 $x_{0}$ 处连续。于是有

$$
\begin{align}
\sum_{i=1}^{\infty} \sum_{j=1}^{\infty} a_{i,j} &= \sum_{i=1}^{\infty} f_{i}(x_{0})=g(x_{0})=\lim_{ n \to \infty } g(x_{n}) \\
&=\lim_{ n \to \infty } \sum_{i=1}^{\infty} f_{i}(x_{n})=\lim_{ n \to \infty } \sum_{i=1}^{\infty} \sum_{j=1}^{n} a_{i,j} \\
&=\lim_{ n \to \infty } \sum_{j=1}^{n} \sum_{i=1}^{\infty} a_{i,j}=\sum_{j=1}^{\infty} \sum_{i=1}^{\infty} a_{i,j}
\end{align}
$$

### Proof #2 (Tao)

在本证明中我们将用到以下的求和定义

$$
\begin{gather}
\sum_{x \in X} f(x) =\sup \left\{  \sum_{x \in F} f(x) : F\subset X\text{ 有限}  \right\}
\end{gather}
$$

其中 $f\geq 0$。

令 $X=\mathbb{N}^{*}\times \mathbb{N}^{*}$，$f(i,j)=a_{i,j}$。由于任意有限集 $F\subset X$ 都包含在某个集合 $\{ (i,j) : i\leq n,j\leq m \}$ 中，因此定理假设表明

$$
\begin{gather}
\sum_{(i,j) \in F} \lvert f(i,j) \rvert \leq \sum_{i=1}^{n} \sum_{j=1}^{m} \lvert f(i,j) \rvert \leq \sum_{i=1}^{n} b_{i}\leq \sum_{i=1}^{\infty} b_{i}< \infty
\end{gather}
$$

从而

$$
\begin{gather}
\sum_{(i,j) \in X} \lvert f(i,j) \rvert < \infty
\end{gather}
$$

我们说 $f$ 在 $X$ 上是绝对可和的（absolutely summable）。

现在我们使用一个经典技巧：将 $f$ 分成实部和虚部，再将它们分别分成正数部分和负数部分

$$
\begin{gather}
f=R_{+}-R_{-}+i(J_{+}-J_{-})
\end{gather}
$$

其中

$$
\begin{gather}
R_{+}=\max(\operatorname{Re} f,0), \quad R_{-}=-\min(\operatorname{Re} f,0)
\end{gather}
$$

$J_{+},J_{-}$ 的定义是类似的。由于 $0\leq R_{\pm}\leq\lvert f \rvert$ 且 $0\leq J_{\pm}\leq\lvert f \rvert$，因此它们也都是绝对可和的。再根据求和的线性性，我们可以不失一般性地假设 $f\geq 0$。于是下面我们要证

$$
\begin{gather}
\sum_{i=1}^{\infty} \sum_{j=1}^{\infty} f(i,j)=\sum_{(i,j)\in X} f(i,j)=L
\end{gather}
$$

从而，根据绝对可和函数的重排不变性，有

$$
\begin{gather}
\sum_{i=1}^{\infty} \sum_{j=1}^{\infty} f(i,j)=\sum_{(i,j)\in X} f(i,j)=\sum_{(j,i) \in X} f(i,j)=\sum_{j=1}^{\infty} \sum_{i=1}^{\infty} f(i,j)
\end{gather}
$$

一方面，对任意 $n,m$ 有

$$
\begin{gather}
\sum_{i=1}^{n} \sum_{j=1}^{m} f(i,j)=\sum_{(i,j)\in F} f(i,j)\leq L
\end{gather}
$$

因此对任意 $n$，令 $m\to \infty$ 可得

$$
\begin{gather}
\sum_{i=1}^{n} \sum_{j=1}^{\infty} f(i,j)\leq L
\end{gather}
$$

从而根据单调有界原理，

$$
\begin{gather}
\sum_{i=1}^{\infty} \sum_{j=1}^{\infty} f(i,j)\leq L
\end{gather}
$$

另一方面，任取 $\varepsilon>0$，存在有限集 $F\subset X$ 使得

$$
\begin{gather}
\sum_{(i,j) \in F} f(i,j)>L-\varepsilon
\end{gather}
$$

由于 $F$ 包含在某个 $\{ (i,j) : i\leq N,j\leq M \}$ 中，因此 $n\geq N$ 蕴含

$$
\begin{gather}
\sum_{i=1}^{n} \sum_{j=1}^{\infty} f(i,j)\geq \sum_{i=1}^{N} \sum_{j=1}^{M} f(i,j)\geq \sum_{(i,j)\in F} f(i,j)>L-\varepsilon
\end{gather}
$$

即证

$$
\begin{gather}
\sum_{i=1}^{\infty} \sum_{j=1}^{\infty} f(i,j)=L
\end{gather}
$$

## Theorem 8.5 (Taylor)

假设幂级数

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} c_{n}x^{n}
\end{gather}
$$

在 $\lvert x \rvert<R$ 内收敛。设 $-R<a<R$，则 $f$ 可以在 $x=a$ 处展开为幂级数，其在 $\lvert x-a \rvert<R-\lvert a \rvert$ 内收敛，且

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!}(x-a)^{n} \quad (\lvert x-a \rvert <R-\lvert a \rvert )
\end{gather}
$$

### Proof

我们有

$$
\begin{align}
f(x) &= \sum_{n=0}^{\infty} c_{n}((x-a)+a)^{n} \\
&= \sum_{n=0}^{\infty} \sum_{m=0}^{n} c_{n} \binom{n}{m} a^{n-m} (x-a)^{m} \\
&= \sum_{m=0}^{\infty} \sum_{n=m}^{\infty} c_{n} \binom{n}{m}a^{n-m}(x-a)^{m}
\end{align}
$$

这便是 $x=a$ 处的幂级数展开式。它是否成立取决于最后一步交换求和顺序的合理性，而 [[#Theorem 8.4 (Fubini)]] 表明这种交换是合理的，如果

$$
\begin{gather}
\sum_{n=0}^{\infty} \sum_{m=0}^{n} \left\lvert  c_{n} \binom{n}{m}a^{n-m}(x-a)^{m}  \right\rvert =\sum_{n=0}^{\infty} \lvert c_{n} \rvert (\lvert x-a \rvert +\lvert a \rvert )^{n}
\end{gather}
$$

收敛，即 $\lvert x-a \rvert+\lvert a \rvert<R$。

最后，根据 [[#Corollary 8.2]] 即得

$$
\begin{gather}
\frac{f^{(m)}(a)}{m!}=\sum_{n=m}^{\infty} c_{n} \binom{n}{m}a^{n-m}
\end{gather}
$$

需要注意的是，$f$ 在 $x=a$ 处的幂级数其收敛半径可能大于 $R-\lvert a \rvert$，于是，根据下面的定理，超出 $(-R,R)$ 范围的幂级数便可以作为 $f$ 在该区间之外的保持解析性的延拓，称为解析延拓（analytic continuation）。

## Theorem 8.6

假设幂级数 $\sum a_{n}x^{n}$ 和 $\sum b_{n}x^{n}$ 在区间 $S=(-R,R)$ 上收敛，定义

$$
\begin{gather}
E=\left\{  x \in S : \sum_{n=0}^{\infty} a_{n}x^{n}=\sum_{n=0}^{\infty} b_{n}x^{n}  \right\}
\end{gather}
$$

如果 $E$ 在 $S$ 中有极限点，那么对任意 $n \in \mathbb{N}$ 有 $a_{n}=b_{n}$，即 $E=S$。

### Proof

取 $c_{n}=a_{n}-b_{n}$，则

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} c_{n}x^{n} \quad (x \in S)
\end{gather}
$$

在 $E$ 上消失。

令 $A\subset S$ 为 $E$ 的所有极限点构成的集合，$B=S\setminus A$。则根据极限点的定义，$B$ 是开集。如果我们能够证明 $A$ 是开集，那么 $S=A\cup B$ 是两个开集的无交并，根据 $S$ 的连通性，必然有一个集合是空集。由于 $A\neq \varnothing$，因此 $B=\varnothing,A=S$。又由于 $f$ 在 $S$ 上连续，因此 $f$ 的零点集 $E$ 是闭集，从而 $A\subset E,E=S$。

下面我们来证明 $A$ 是开集。取 $x_{0}\in A$，则在 $x=x_{0}$ 处 $f$ 有幂级数展开

$$
\begin{gather}
f(x)=\sum_{n=0}^{\infty} d_{n}(x-x_{0})^{n} \quad (\lvert x-x_{0} \rvert <R-\lvert x_{0} \rvert )
\end{gather}
$$

我们断言对任意 $n \in \mathbb{N}$ 有 $d_{n}=0$。假设不然，则存在最小的自然数 $k$ 使得 $d_{k}\neq 0$，则

$$
\begin{gather}
f(x)=(x-x_{0})^{k} g(x)
\end{gather}
$$

其中

$$
\begin{gather}
g(x)=\sum_{m=0}^{\infty} d_{k+m}(x-x_{0})^{m}
\end{gather}
$$

满足

$$
\begin{gather}
g(x_{0})=d_{k}\neq 0
\end{gather}
$$

由于 $g$ 在 $x_{0}$ 处连续，故存在 $\delta>0$ 使得在 $B(x_{0},\delta)$ 中有 $g(x)\neq 0$，从而当 $0<\lvert x-x_{0} \rvert<\delta$ 时 $f(x)\neq 0$，这与 $x_{0}$ 是 $E$ 的极限点矛盾。

因此我们有

$$
\begin{gather}
f(x)=0 \quad (\lvert x-x_{0} \rvert <R-\lvert x_{0} \rvert )
\end{gather}
$$

即 $A$ 包含了 $x_{0}$ 的一个邻域。这就完成了证明。

# The Exponential and Logarithmic Functions 指数函数与对数函数

我们定义指数函数

$$
\begin{gather}
E(z)=\sum_{n=0}^{\infty} \frac{z^{n}}{n!}
\end{gather}
$$

比值准则表明，以上级数对任意 $z \in \mathbb{C}$ 都绝对收敛。因此，根据无穷级数的 Fubini 定理，有加法公式

$$
\begin{align}
E(z)E(w)&= \sum_{n=0}^{\infty} \frac{z^{n}}{n!} \sum_{m=0}^{\infty} \frac{w^{m}}{m!}=\sum_{n=0}^{\infty} \sum_{k=0}^{n} \frac{z^{k}w^{n-k}}{k!(n-k)!} \\
&=\sum_{n=0}^{\infty} \sum_{k=0}^{n} \frac{1}{n!} \binom{n}{k} z^{k}w^{n-k}=\sum_{n=0}^{\infty} \frac{(z+w)^{n}}{n!}=E(z+w)
\end{align}
$$

于是，令 $w=-z$，则我们有

$$
\begin{gather}
E(z)E(-z)=E(0)=1
\end{gather}
$$

即 $E(-z)=1 /E(z)$。由于 $x>0$ 时 $E(x)>0$，因此上式表明 $x \in \mathbb{R}$ 时都有 $E(x)>0$。此外，当 $x\to +\infty$ 时 $E(x)\to +\infty$，因此当 $x\to -\infty$ 时 $E(x)\to 0$。当 $0<x<y$ 时 $E(x)<E(y)$，因此 $E(-y)<E(-x)$，从而指数函数 $E$ 在 $\mathbb{R}$ 上严格单调递增。

加法公式也表明

$$
\begin{gather}
\lim_{ h \to 0 } \frac{E(z+h)-E(z)}{h}=E(z) \lim_{ h \to 0 } \frac{E(h)-1}{h}=E(z)
\end{gather}
$$

这就是说，$E$ 在 $\mathbb{C}$ 上处处可微，且 $E'(z)=E(z)$。

重复应用加法公式，根据归纳法可得

$$
\begin{gather}
E(z_{1}+\dots+z_{n})=E(z_{1})\cdots E(z_{n})
\end{gather}
$$

取 $z_{1}=\dots=z_{n}=1$，由于 $E(1)=e$，我们有

$$
\begin{gather}
E(n)=e^{n} \quad (n=1,2,\dots)
\end{gather}
$$

如果 $p=n /m$ 是正有理数，其中 $n,m \in \mathbb{N}^{*}$，则

$$
\begin{gather}
E(p)^{m}=E(mp)=E(n)=e^{n}
\end{gather}
$$

从而

$$
\begin{gather}
E(p)=e^{p} \quad (p \in \mathbb{Q}_{>0})
\end{gather}
$$

于是根据 $E(-p)=1 /E(p)$ 得 $E(p)=e^{p}$ 对任意 $p \in \mathbb{Q}$ 成立。

最后，对于 $x \in \mathbb{R}$，我们定义 $e^{x}$ 以使得它成为一个连续函数：取有理数列 $r_{n}\to x$，定义

$$
\begin{gather}
e^{x}=\lim_{ n \to \infty } e^{r_{n}}
\end{gather}
$$

则根据 $E$ 的连续性，我们就有

$$
\begin{gather}
E(x)=e^{x} \quad (x \in \mathbb{R})
\end{gather}
$$

上式解释了为什么 $E(x)$ 被称为指数函数。有时，我们也将 $e^{x}$ 写成 $\exp(x)$，尤其是当 $x$ 是一个复杂表达式时。

## Theorem 8.7

定义在 $\mathbb{R}$ 上的指数函数 $e^{x}$ 满足以下性质：

1. $e^{x}$ 在 $\mathbb{R}$ 上连续且可微，
2. $(e^{x})'=e^{x}$，
3. $e^{x}$ 在 $\mathbb{R}$ 上严格单调递增，$e^{x}>0$，
4. $e^{x+y}=e^{x}e^{y}$，
5. $\lim_{ x \to +\infty }e^{x}=+\infty,\lim_{ x \to -\infty }e^{x}=0$，
6. 对任意 $n \in \mathbb{N}$，有 $\lim_{ x \to +\infty }x^{n}e^{-x}=0$。

命题 (6) 表明，当 $x\to +\infty$ 时，指数函数的增长速度比任何幂函数都快。

### Proof

我们已经证明了 (1)-(5)。对于 (6)，根据指数函数的定义可知

$$
\begin{gather}
e^{x}> \frac{x^{n+1}}{(n+1)!} \quad (x>0)
\end{gather}
$$

从而

$$
\begin{gather}
x^{n} e^{-x}< \frac{(n+1)!}{x}
\end{gather}
$$

当 $x\to +\infty$ 时，右侧表达式趋于 $0$，即证 $x^{n}e^{-x}\to 0$。

由于 $E\colon \mathbb{R}\to (0,\infty)$ 是一个可微且严格单调递增的函数，因此它在 $(0,\infty)$ 上有一个可微的反函数 $L$，定义为

$$
\begin{gather}
E(L(y))=y \quad (y>0)
\end{gather}
$$

或者

$$
\begin{gather}
L(E(x))=x \quad (x \in \mathbb{R})
\end{gather}
$$

应用链式法则得

$$
\begin{gather}
L'(E(x))\cdot E(x)=1
\end{gather}
$$

记 $y=E(x)$，则我们有

$$
\begin{gather}
L'(y)=\frac{1}{y} \quad (y>0)
\end{gather}
$$

结合 $L(1)=0$，我们就有

$$
\begin{gather}
L(y)=\int _{1}^{y} \frac{1}{x} \, \mathrm{d}x 
\end{gather}
$$

这一函数称为对数函数，通常记作 $L(x)=\log x$，并且与指数函数相对，它将乘法转换为加法：设 $u=E(x),v=E(y)$，则

$$
\begin{gather}
L(uv)=L(E(x)E(y))=L(E(x+y))=x+y
\end{gather}
$$

即

$$
\begin{gather}
L(uv)=L(u)+L(v) \quad (u,v>0)
\end{gather}
$$

下面我们考虑 $\log x$ 在 $x\to 0$ 与 $x\to +\infty$ 时的行为，根据 $e^{x}$ 的极限行为，我们立即得到

$$
\begin{gather}
\lim_{ x \to +\infty } \log x=+\infty \\
\lim_{ x \to 0 } \log x=-\infty
\end{gather}
$$

此外，利用 $E(x)$ 的加法公式，我们容易得到

$$
\begin{gather}
x^{n}=E(n L(x)) \quad (x>0, n \in \mathbb{Z})
\end{gather}
$$

类似地，如果 $m \in \mathbb{N}^{*}$，则

$$
\begin{gather}
x^{1/m}=E\left( \frac{1}{m}L(x) \right)
\end{gather}
$$

因为两边的 $m$ 次方都等于 $x$。结合以上两个公式，我们有

$$
\begin{gather}
x^{\alpha}=E(\alpha L(x))=e^{\alpha \log x} \quad (\alpha \in \mathbb{Q})
\end{gather}
$$

现在我们对任意 $\alpha \in \mathbb{R}$ 与 $x>0$ 定义 $x^{\alpha}$ 如上。根据函数 $E,L$ 的连续性，我们可以证明以上定义与前面所述的极限定义

$$
\begin{gather}
x^{\alpha}=\lim_{ n \to \infty } x^{r_{n}} \quad (r_{n}\in \mathbb{Q},r_{n}\to \alpha)
\end{gather}
$$

一致，从而实数乘方的相关性质都是上述定义的平凡推论。特别地，求导数可得

$$
\begin{gather}
(x^{\alpha})'=E(\alpha L(x))\cdot \frac{\alpha}{x}=\alpha x^{\alpha-1} \quad (\alpha \in \mathbb{R})
\end{gather}
$$

最后我们再给出一个与 [[#Theorem 8.7]](6) 类似的性质，它表明：当 $x\to +\infty$ 时，对数函数增长得比任何正数幂函数都慢，即

$$
\begin{gather}
\lim_{ x \to +\infty } x^{-\alpha} \log x=0 \quad (\alpha>0)
\end{gather}
$$

取 $0<\varepsilon<\alpha,x>1$，则

$$
\begin{align}
x^{-\alpha}\log x &=x^{-\alpha} \int _{1}^{x} \frac{1}{t} \, \mathrm{d}t < x^{-\alpha} \int _{1}^{x} t^{\varepsilon-1} \, \mathrm{d}t  \\
&= x^{-\alpha} \frac{x^{\varepsilon}-1}{\varepsilon}< \frac{x^{\varepsilon-\alpha}}{\varepsilon}
\end{align}
$$

当 $x\to +\infty$ 时右侧趋于 $0$，即证。

# The Trigonometric Functions 三角函数

我们定义

$$
\begin{gather}
C(x)=\frac{E(ix)+E(-ix)}{2}, \quad S(x)=\frac{E(ix)-E(-ix)}{2i} \quad (x \in \mathbb{R})
\end{gather}
$$

我们将证明，上面的函数 $C,S$ 正是熟悉的三角函数 $\cos,\sin$，后者的定义基于直角三角形的边的长度之比。

根据 $E$ 的定义，我们有 $E(\overline{z})=\overline{E(z)}$，因此对于 $x \in \mathbb{R}$，$C(x)$ 和 $S(x)$ 都是实数，并且分别是 $E(ix)$ 的实部和虚部。又由于

$$
\begin{gather}
\lvert E(ix) \rvert ^{2}=E(ix) \overline{E(ix)}=E(ix)E(-ix)=1
\end{gather}
$$

即

$$
\begin{gather}
\lvert E(ix) \rvert =1
\end{gather}
$$

我们有 $C(0)=1,S(0)=0$，并且

$$
\begin{gather}
C'(x)=-S(x), \quad S'(x)=C(x)
\end{gather}
$$

我们断言存在 $x>0$ 使得 $C(x)=0$。假设不然，由于 $C(0)=1$，因此对于 $x>0$ 有 $C(x)=S'(x)>0$，从而 $S$ 在 $x>0$ 上单调递增，$S(x)>0$。然而，对于 $0<x<y$ 有

$$
\begin{gather}
S(x)(y-x)\leq \int _{x}^{y} S(t) \, \mathrm{d}t =C(y)-C(x)\leq 2
\end{gather}
$$

当 $y$ 足够大时，上式不可能成立，构成矛盾。

我们令 $x_{0}$ 为 $C$ 的最小正零点，它存在，因为连续函数的零点集是闭集，并且 $C(0)\neq 0$。我们将它作为圆周率的一个定义：

$$
\begin{gather}
\pi=2x_{0}
\end{gather}
$$

则 $C(\pi /2)=0$，从而 $S(\pi /2)=\pm 1$。又由于在 $(0,\pi /2)$ 上 $C(x)>0$，因此 $S$ 在 $(0,\pi /2)$ 上递增，于是 $S(\pi /2)>0$，即 $S(\pi /2)=1$。故

$$
\begin{gather}
E\left( \frac{\pi i}{2} \right)=C\left( \frac{\pi}{2} \right)+i S\left( \frac{\pi}{2} \right)=i
\end{gather}
$$

加法公式给出

$$
\begin{gather}
E(\pi i)=-1, \quad E(2\pi i)=1
\end{gather}
$$

因此

$$
\begin{gather}
E(z+2\pi i)=E(z) \quad (z \in \mathbb{C})
\end{gather}
$$

## Theorem 8.8

(a) 函数 $E$ 是周期的，$2\pi i$ 是它的一个周期。
(b) 函数 $C,S$ 是周期的，其均有周期 $2\pi$。
(c) 如果 $0<t<2\pi$，那么 $E(it)\neq 1$。
(d) 如果 $z \in \mathbb{C}$ 满足 $\lvert z \rvert=1$，那么存在唯一的 $t \in[0,2\pi)$ 使得 $z=E(it)$。

### Proof

我们已经证明了 (a)，根据 $C,S$ 的定义即得 (b)。

假设 $0<t<\pi /2$，$E(it)=x+iy$，由于 $\lvert E(it) \rvert=1$，因此 $0<x<1$ 且 $0<y<1$，并且

$$
\begin{gather}
E(4it)=(x+iy)^{4}=x^{4}-6x^{2}y^{2}+y^{4}+4ixy(x^{2}-y^{2})
\end{gather}
$$

如果 $E(4it)$ 是实数，那么 $x^{2}-y^{2}=0$，由于 $x^{2}+y^{2}=1$，故 $x^{2}=y^{2}=1 /2$，从而 $E(4it)=-1$。这就证明了 (c)。

如果 $0\leq t_{1}<t_{2}<2\pi$，那么根据 (c) 有

$$
\begin{gather}
\frac{E(it_{2})}{E(it_{1})}=E(it_{2}-it_{1})\neq 1
\end{gather}
$$

这就证明了 (d) 的唯一性部分。

要证明存在性，固定 $\lvert z \rvert=1$，记 $z=x+iy$，首先我们证明 $x,y\geq 0$ 的情况。在 $[0, \pi /2]$ 上，$C$ 从 $1$ 减小到 $0$，因此根据介值性，存在 $t \in[0,\pi /2]$ 使得 $C(t)=x$。由于 $C^{2}+S^{2}=1$ 且在 $[0,\pi /2]$ 上 $S\geq 0$，故 $z=E(it)$。

如果 $x<0,y\geq 0$，那么 $-iz$ 位于第一象限中，因而可以应用上面的论证，得到 $t \in[0,\pi /2]$ 使得 $-iz=E(it)$。两边乘以 $i$ 得

$$
\begin{gather}
z=iE(it)=E\left( \frac{\pi i}{2} \right)E(it)=E\left( i\left( t+\frac{\pi}{2} \right) \right)
\end{gather}
$$

最后，如果 $y<0$，那么 $-z$ 落在第一和第二象限中，可以应用上面的论证。则存在 $t \in (0,\pi)$ 使得 $-z=E(it)$，于是 $z=-E(it)=E(i(t+\pi))$。

以上定理的 (d) 表明，定义为

$$
\begin{gather}
\gamma(t)=E(it) \quad (0\leq t\leq 2\pi)
\end{gather}
$$

的 $\gamma\colon [0,2\pi]\to \mathbb{C}$ 是平面上的一条简单闭曲线，它的像是单位圆。由于 $\gamma'(t)=iE(it)$，因此 $\gamma$ 的长度为

$$
\begin{gather}
\int _{0}^{2\pi} \lvert \gamma'(t) \rvert  \, \mathrm{d}t =2\pi
\end{gather}
$$

换句话说，单位圆的周长为 $2\pi$。因此，上面定义的 $\pi$ 与其原始的意义：圆的周长与直径之比是一致的。

以相同的方法，$\gamma(t) \ (0\leq t\leq t_{0})$ 在平面上描绘了一条长度为 $t_{0}$ 的圆弧。考虑三个顶点分别为

$$
\begin{gather}
z_{1}=0, \quad z_{2}=C(t_{0}), \quad z_{3}=\gamma(t_{0})
\end{gather}
$$

的平面三角形，则我们可以立即看出，$C(t)$ 和 $S(t)$ 的确与余弦函数 $\cos t$ 和正弦函数 $\sin t$ 相同。

# The Algebraic Completeness of the Complex Field 复数域的代数闭性

本节我们来给出复数域的代数闭性的一个简单证明，它表明，复系数的非常值多项式必定有复数根。

## Theorem 8.9 (代数基本定理)

设 $a_{0},\dots,a_{n}$ 是复数，$n \in \mathbb{N}^{*},a_{n}\neq 0$，

$$
\begin{gather}
P(z)=\sum_{k=0}^{n} a_{k}z^{k}
\end{gather}
$$

则存在 $z \in \mathbb{C}$ 使得 $P(z)=0$。

### Proof

将 $P(z)$ 替换为 $\frac{1}{a_{n}}P(z)$ 不会改变它的零点，因此我们可以不失一般性地假设 $a_{n}=1$。令

$$
\begin{gather}
\mu=\inf_{z \in \mathbb{C}} \lvert P(z) \rvert 
\end{gather}
$$

如果 $\lvert z \rvert=R$，则

$$
\begin{gather}
\lvert P(z) \rvert \geq R^{n}(1-\lvert a_{n-1} \rvert R^{-1}-\dots-\lvert a_{n} \rvert R^{-n})
\end{gather}
$$

当 $R\to +\infty$ 时，上式右侧趋于 $+\infty$。因此存在 $R_{0}>0$ 使得当 $\lvert z \rvert>R_{0}$ 时有 $\lvert P(z) \rvert>\mu$。现在，$\lvert P \rvert$ 在闭圆盘 $\overline{B}(0,R_{0})$ 上连续，从而它能够取到闭圆盘内的最小值 $\mu=\lvert P(z_{0}) \rvert$。

我们要证 $\mu=0$。

假设不然，则 $Q(z)=P(z+z_{0}) /P(z_{0})$ 是一个非常值多项式，$Q(0)=1$，且对于 $z \in \mathbb{C}$ 有 $Q(z)\geq 1$。取最小的 $k$，$1\leq k\leq n$，使得

$$
\begin{gather}
Q(z)=1+b_{k}z^{k}+\dots+b_{n}z^{n}, \quad b_{k}\neq 0
\end{gather}
$$

我们可以取 $\theta \in \mathbb{R}$ 使得

$$
\begin{gather}
e^{ik\theta}b_{k}=-\lvert b_{k} \rvert 
\end{gather}
$$

于是取 $r>0$ 使得 $r^{k}\lvert b_{k} \rvert<1$，则

$$
\begin{gather}
\lvert 1+b_{k}r^{k} e^{ik\theta} \rvert =1-r^{k}\lvert b_{k} \rvert 
\end{gather}
$$

从而

$$
\begin{gather}
\lvert Q(re^{i\theta}) \rvert \leq 1-r^{k}(\lvert b_{k} \rvert -r\lvert b_{k+1} \rvert -\dots-r^{n-k}\lvert b_{n} \rvert )
\end{gather}
$$

当 $r$ 足够小时，括号内的表达式是正数，从而 $\lvert Q(re^{i\theta}) \rvert<1$，矛盾。

因此，$\mu=0$，即存在 $z_{0}$ 使得 $P(z_{0})=0$。

# Fourier Series 傅里叶级数

## Definition 8.10

一个三角多项式形如

$$
\begin{gather}
f(x)=a_{0}+\sum_{n=1}^{N} (a_{n}\cos nx+b_{n}\sin nx) \quad (x \in \mathbb{R})
\end{gather}
$$

其中 $a_{0},\dots,a_{N},b_{1},\dots,b_{N}$ 是复数。根据 Euler 公式 $e^{ix}=\cos x+i\sin x$ 我们可以将其写成

$$
\begin{gather}
f(x)=\sum_{n=-N}^{N} c_{n}e^{inx} \quad (x \in \mathbb{R})
\end{gather}
$$

在通常情况下，我们均使用以上的指数形式。根据以上定义，容易看出任何三角多项式均具有周期 $2\pi$。在其他教材中，有的也定义三角多项式为周期 $1$ 的形式：$\tilde{f}(x)=f(2\pi x)$。

如果 $n$ 是非零整数，则 $\int e^{inx}=e^{inx} /in$，于是我们有

$$
\begin{gather}
\frac{1}{2\pi} \int _{-\pi}^{\pi} e^{inx} \, \mathrm{d}x =\begin{cases}
1, & n=0 \\
0, & n\neq 0
\end{cases}
\end{gather}
$$

从而

$$
\begin{gather}
\frac{1}{2\pi} \int _{-\pi}^{\pi} f(x) e^{-imx} \, \mathrm{d}x =c_{m} \quad (\lvert m \rvert \leq N) \tag{8.10.1}
\end{gather}
$$

当 $\lvert m \rvert>N$ 时，我们定义 $c_{m}=0$，则上式对任意整数 $m$ 成立。根据上式，我们立即得到：三角多项式 $f$ 是实值函数当且仅当 $c_{-n}=\overline{c}_{n}$。

我们定义一个三角级数具有形式

$$
\begin{gather}
\sum_{n=-\infty}^{\infty} c_{n} e^{inx} \tag{8.10.2}
\end{gather}
$$

它的第 $N$ 个部分和定义为对称和

$$
\begin{gather}
s_{N}(x)=\sum_{n=-N}^{N} c_{n}e^{inx}
\end{gather}
$$

设 $f$ 在 $[-\pi,\pi]$ 上可积，则由 $(8.10.1)$ 给出的系数 $c_{n}$ 称为 $f$ 的第 $n$ 个 Fourier 系数，相应地级数 $(8.10.2)$ 就称为 $f$ 的 Fourier 级数。

一个自然的问题是：$f$ 的 Fourier 级数是否收敛于 $f$？或者更一般地，$f$ 是否完全由它的 Fourier 级数确定，即，如果我们知道一个函数的 Fourier 级数，那么我们是否能够找到一个函数 $f$，使得它的 Fourier 级数与给定的级数相同？

以上这些问题的回答及其推论构成了现代分析学的一个核心领域：Fourier 分析或调和分析。本节我们仅取少数基本结果进行研究，对于更深入的结果，Lebesgue 积分是必要的工具。

## Definition 8.11 orthogonal 正交的，orthonormal 标准正交的

设 $(\phi_{n})_{n=1}^{\infty}$ 是一列 $[a,b]$ 上的复值函数，满足

$$
\begin{gather}
\int _{a}^{b} \phi_{n}(x) \overline{\phi_{m}(x)} \, \mathrm{d}x =0 \quad (n\neq m)
\end{gather}
$$

则称 $(\phi_{n})$ 是 $[a,b]$ 上的一个正交函数系。如果进一步有

$$
\begin{gather}
\int _{a}^{b} \lvert \phi_{n}(x) \rvert ^{2} \, \mathrm{d}x =1 \quad (n=1,2,\dots)
\end{gather}
$$

则称 $(\phi_{n})$ 是标准正交的。

例如，$\frac{1}{\sqrt{ 2\pi }}e^{inx}$ 是 $[-\pi,\pi]$ 上的标准正交函数系，下面的函数系也是一样：

$$
\begin{gather}
\frac{1}{\sqrt{ 2\pi }}, \frac{\cos x}{\sqrt{ \pi }},\frac{\sin x}{\sqrt{ \pi }},\frac{\cos 2x}{\sqrt{ \pi }},\frac{\sin 2x}{\sqrt{ \pi }},\dots
\end{gather}
$$

如果 $(\phi_{n})$ 在 $[a,b]$ 上标准正交，则我们定义

$$
\begin{gather}
c_{n}=\int _{a}^{b} f(x) \overline{\phi_{n}(x)} \, \mathrm{d}x \quad (n=1,2,\dots)
\end{gather}
$$

为函数 $f$ 相对于 $(\phi_{n})$ 的第 $n$ 个 Fourier 系数。我们用

$$
\begin{gather}
f(x) \sim \sum_{n=1}^{\infty} c_{n} \phi_{n}(x)
\end{gather}
$$

来表示 $f$ 相对于 $(\phi_{n})$ 的 Fourier 级数。上面我们使用 $\sim$ 来连接 $f$ 与级数，这表明我们现在还未考虑级数的收敛性，而仅仅在形式上表示右侧级数是 $f$ 的 Fourier 级数。

在本节的剩余部分，我们将假设 $f \in \mathcal{R}$。

## Theorem 8.12

设 $(\phi_{n})$ 在 $[a,b]$ 上标准正交，令

$$
\begin{gather}
s_{n}(x)=\sum_{m=1}^{n} c_{m}\phi_{m}(x)
\end{gather}
$$

为 $f$ 的 Fourier 级数的第 $n$ 个部分和，并设

$$
\begin{gather}
t_{n}(x)=\sum_{m=1}^{n} \gamma_{m}\phi_{m}(x)
\end{gather}
$$

则

$$
\begin{gather}
\int _{a}^{b} \lvert f-s_{n} \rvert ^{2} \, \mathrm{d}x \leq \int _{a}^{b} \lvert f-t_{n} \rvert ^{2} \, \mathrm{d}x 
\end{gather}
$$

等号成立当且仅当

$$
\begin{gather}
\gamma_{m}=c_{m} \quad (m=1,\dots,n)
\end{gather}
$$

这就是说，在均方意义下，Fourier 级数的部分和构成了 $f$ 的最佳近似。

### Proof

我们引入符号

$$
\begin{gather}
\langle f,g \rangle =\int _{a}^{b} f(x) \overline{g(x)} \, \mathrm{d}x 
\end{gather}
$$

$\langle f,g \rangle$ 可以视为 $\mathbb{R}^{n}$ 中的向量点乘 $\mathbf{x}\cdot \mathbf{y}$ 的一种推广，称为内积，因为它有如下性质：

1. 正定性：$\langle f,f \rangle\geq 0$，等号成立当且仅当 $f=0$。
2. 共轭对称性：$\langle f,g \rangle=\overline{\langle g,f \rangle}$。
3. 线性性：$\langle af+bg,h \rangle=a \langle f,h \rangle+b \langle g,h \rangle$。

和 $\mathbb{R}^{n}$ 中一样，我们可以定义函数 $f,g$ 之间的距离为

$$
\begin{gather}
\lVert f-g \rVert =\langle f-g,f-g \rangle ^{1/2}
\end{gather}
$$

于是我们要证的就是

$$
\begin{gather}
\lVert f-s_{n} \rVert ^{2}\leq \lVert f-t_{n} \rVert ^{2}
\end{gather}
$$

下面我们分步证明以上结论。

**第一步** $s_{n}$ 是 $f$ 在 $(\phi_{m})_{m=1}^{n}$ 张成空间上的正交投影。

![](8-1.png)

$$
\begin{align}
\langle f-s_{n},\phi_{m} \rangle =\langle f,\phi_{m} \rangle -\langle s_{n},\phi_{m} \rangle =c_{m}-c_{m}=0
\end{align}
$$

因此，根据内积的线性性，对任意 $(\phi_{m})_{m=1}^{n}$ 的线性组合 $t_{n}'$，都有 $\langle f-s_{n},t_{n}' \rangle=0$ 成立。

**第二步** 距离具有正交可加性（勾股定理）：如果 $\langle f,g \rangle=0$，那么 $\lVert f+g \rVert^{2}=\lVert f \rVert^{2}+\lVert g \rVert^{2}$。

$$
\begin{align}
\lVert f+g \rVert ^{2}&= \langle f+g,f+g \rangle \\
&=\langle f,f \rangle +\langle f,g \rangle +\langle g,f \rangle +\langle g,g \rangle  \\
&=\langle f,f \rangle +\langle g,g \rangle +2\operatorname{Re} \langle f,g \rangle  \\
&=\lVert f \rVert ^{2}+\lVert g \rVert ^{2} 
\end{align}
$$

**第三步** $s_{n}$ 与 $f$ 之间的距离在张成空间上最短。

$t_{n}$ 可以分解为 $t_{n}=s_{n}+t_{n}'$，于是根据正交性有

$$
\begin{align}
\lVert t_{n}-f \rVert ^{2} &= \lVert s_{n}-f+t_{n}' \rVert^{2} \\
&=\lVert s_{n}-f \rVert ^{2}+\lVert t_{n}' \rVert ^{2}  \\
&\geq \lVert s_{n}-f \rVert ^{2}
\end{align}
$$

即

$$
\begin{gather}
\int \lvert f-s_{n} \rvert ^{2} \, \mathrm{d}x \leq \int \lvert f-t_{n} \rvert ^{2} \, \mathrm{d}x 
\end{gather}
$$

等号成立当且仅当

$$
\begin{gather}
\lVert t_{n}' \rVert ^{2}=\lVert t_{n}-s_{n} \rVert ^{2}=\sum_{m=1}^{n} \lvert \gamma_{m}-c_{m} \rvert ^{2}=0
\end{gather}
$$

即 $\gamma_{m}=c_{m}$。

## Theorem 8.13 (Bessel)

如果 $(\phi_{n})$ 在 $[a,b]$ 上标准正交，且

$$
\begin{gather}
f(x) \sim \sum_{n=1}^{\infty} c_{n} \phi_{n}(x)
\end{gather}
$$

则

$$
\begin{gather}
\sum_{n=1}^{\infty} \lvert c_{n} \rvert ^{2}\leq \int _{a}^{b} \lvert f(x) \rvert ^{2} \, \mathrm{d}x 
\end{gather}
$$

特别地，$\lim_{ n \to \infty }c_{n}=0$。

### Proof

根据 [[#Theorem 8.12]] 的证明，我们有

$$
\begin{gather}
\langle f,s_{n} \rangle =\langle s_{n},s_{n} \rangle +\langle f-s_{n},s_{n} \rangle =\langle s_{n},s_{n} \rangle =\sum_{m=1}^{n} \lvert c_{m} \rvert ^{2}
\end{gather}
$$

于是

$$
\begin{align}
\lVert f-s_{n} \rVert ^{2}&=\langle f-s_{n},f-s_{n} \rangle  \\
&=\langle f,f \rangle -\langle f,s_{n} \rangle -\langle s_{n},f \rangle +\langle s_{n},s_{n} \rangle  \\
&=\int \lvert f(x) \rvert ^{2} \, \mathrm{d}x -\sum_{m=1}^{n} \lvert c_{m} \rvert ^{2}\geq 0
\end{align}
$$

令 $n\to \infty$ 即证。

接下来我们考虑三角级数。其中我们设 $f$ 具有周期 $2\pi$，且在 $[-\pi,\pi]$ 上 Riemann 可积（从而在任意有界区间上可积）。$f$ 的 Fourier 级数就是级数 $(8.10.2)$，其系数 $c_{n}$ 由 $(8.10.1)$ 给出，且

$$
\begin{gather}
s_{N}(x)=s_{N}(f;x)=\sum_{n=-N}^{N} c_{n} e^{inx}
\end{gather}
$$

此时的 Bessel 不等式具有形式

$$
\begin{gather}
\frac{1}{2\pi} \int _{-\pi}^{\pi} \lvert s_{N}(x) \rvert ^{2} \, \mathrm{d}x =\sum_{n=-N}^{N} \lvert c_{n} \rvert ^{2}\leq \frac{1}{2\pi} \int _{-\pi}^{\pi} \lvert f(x) \rvert ^{2} \, \mathrm{d}x 
\end{gather}
$$

要给出 $s_{N}$ 的一个表达式，我们考虑如下的 Dirichlet 核

$$
\begin{gather}
D_{N}(x)=\sum_{n=-N}^{N} e^{inx}=\frac{e^{i(N+1)x}-e^{-iNx}}{e^{ix}-1}=\frac{\sin\left( N+\frac{1}{2} \right)x}{\sin (x /2)}
\end{gather}
$$

则 $s_{N}$ 就可以写成 $f$ 与 $D_{N}$ 的卷积形式：

$$
\begin{align}
s_{N}(f;x)&= \sum_{n=-N}^{N} e^{inx} \frac{1}{2\pi} \int _{-\pi}^{\pi} f(t)e^{-int} \, \mathrm{d}t  \\
&= \frac{1}{2\pi} \int _{-\pi}^{\pi} f(t) \sum_{n=-N}^{N} e^{in(x-t)} \, \mathrm{d}t \\
&=\frac{1}{2\pi} \int_{-\pi}^{\pi} f(t)D_{N}(x-t) \, \mathrm{d}t \\
&=\frac{1}{2\pi} \int _{-\pi}^{\pi} f(x-t)D_{N}(t) \, \mathrm{d}t 
\end{align}
$$

最后一个等式成立，因为 $f$ 与 $D_{N}$ 具有周期 $2\pi$，因此其在任意长度为 $2\pi$ 的区间上都有相同的积分。

## Theorem 8.14

如果 $f$ 在 $x$ 处满足 Lipschitz 条件，即存在 $\delta>0$ 与 $M<\infty$ 使得对任意 $-\delta<t<\delta$ 有

$$
\begin{gather}
\lvert f(x+t)-f(x) \rvert \leq M\lvert t \rvert 
\end{gather}
$$

则

$$
\begin{gather}
\lim_{ N \to \infty } s_{N}(f;x)=f(x)
\end{gather}
$$

### Proof

定义

$$
\begin{gather}
g(t)=\frac{f(x-t)-f(x)}{\sin(t /2)} \quad (0<\lvert t \rvert \leq \pi)
\end{gather}
$$

并取 $g(0)=0$。由于

$$
\begin{gather}
\frac{1}{2\pi} \int _{-\pi}^{\pi} D_{N}(x) \, \mathrm{d}x =1
\end{gather}
$$

因此我们有

$$
\begin{align}
s_{N}(f;x)-f(x) &= \frac{1}{2\pi} \int _{-\pi}^{\pi} g(t) \sin\left( N+\frac{1}{2} \right)t \, \mathrm{d}t  \\
&=\frac{1}{2\pi} \int _{-\pi}^{\pi}  \left( g(t) \cos \frac{t}{2} \sin Nt+g(t) \sin \frac{t}{2} \cos Nt \right) \, \mathrm{d}t 
\end{align}
$$

现在我们有以下结论：

1. $1,\cos x,\sin x,\cos 2x,\sin 2x,\dots$ 是正交系，
2. $g(t),\cos(t /2),\sin(t /2)$ 是有界函数，
3. $f$ 是 Riemann 可积函数，故 $\int_{-\pi}^{\pi} \lvert f \rvert^{2}<\infty$。

根据 [[#Theorem 8.13 (Bessel)]] 即证当 $N\to \infty$ 时 $s_{N}(f;x)-f(x)\to 0$。

## Corollary 8.15 (局部化定理)

如果在开区间 $J$ 上有 $f=0$，则对任意 $x \in J$ 有 $s_{N}(f;x)\to 0$。特别地，如果在 $x$ 的邻域内有 $f(t)=g(t)$，那么

$$
\begin{gather}
\lim_{ N \to \infty } s_{N}(f;x)=\lim_{ N \to \infty } s_{N}(g;x)
\end{gather}
$$

以上定理表明，Fourier 级数的（逐点）收敛性只与 $x$ 的邻域内 $f$ 的取值有关。这与幂级数不同：后者在任意小邻域中的取值足以确定整个函数，因此我们说解析函数具有刚性。

## Theorem 8.16

如果连续函数 $f$ 具有周期 $2\pi$，$\varepsilon>0$，则存在三角多项式 $P$ 使得对任意 $x \in \mathbb{R}$ 有

$$
\begin{gather}
\lvert P(x)-f(x) \rvert <\varepsilon
\end{gather}
$$

### Proof

如果我们将 $x$ 与 $x+2\pi$ 等同，通过将 $x$ 替换为 $e^{ix}$，我们可以将 $\mathbb{R}$ 上周期 $2\pi$ 的函数视为单位圆 $\mathbb{T}$ 上的函数。所有三角多项式构成的集合 $\mathcal{A}$ 构成了 $\mathbb{T}$ 上的一个自伴随代数，它可以分离点，并且在任何点上不消失。于是，根据 Stone-Weierstrass 定理，$\mathcal{A}$ 在 $C(\mathbb{T})$ 中稠密，这就是所要证的。

## Theorem 8.17 (Fourier-Parseval)

设 $f,g$ 是周期 $2\pi$ 的 Riemann 可积函数，且

$$
\begin{gather}
f(x)\sim \sum_{n=-\infty}^{\infty} c_{n}e^{inx}, \quad g(x)\sim \sum_{n=-\infty}^{\infty} \gamma_{n}e^{inx}
\end{gather}
$$

则

$$
\begin{align}
\lim_{ N \to \infty } \frac{1}{2\pi} \int _{-\pi}^{\pi} \lvert f(x)-s_{N}(f;x) \rvert ^{2} \, \mathrm{d}x &=0 \\
\frac{1}{2\pi} \int _{-\pi}^{\pi} f(x) \overline{g(x)} \, \mathrm{d}x &=\sum_{n=-\infty}^{\infty} c_{n} \overline{\gamma}_{n} \\
\frac{1}{2\pi} \int _{-\pi}^{\pi} \lvert f(x) \rvert ^{2} \, \mathrm{d}x &=\sum_{n=-\infty}^{\infty} \lvert c_{n} \rvert ^{2}
\end{align}
$$

其中第一个极限式称为 Fourier 定理，后两个等式称为 Parseval 定理。

### Proof

我们定义

$$
\begin{gather}
\lVert h \rVert _{2}=\left( \frac{1}{2\pi} \int _{-\pi}^{\pi} \lvert h(x) \rvert ^{2} \, \mathrm{d}x  \right)^{1/2}
\end{gather}
$$

固定 $\varepsilon>0$，我们可以构造周期 $2\pi$ 的连续函数 $h$ 使得 $\lVert f-h \rVert_{2}<\varepsilon$ 如下：

取 $[-\pi,\pi]$ 的划分 $P=\{ x_{0},\dots,x_{n} \}$ 使得

$$
\begin{gather}
U(P,f)-L(P,f)<\varepsilon^{2}
\end{gather}
$$

令

$$
\begin{gather}
f^{*}(x)=\sum_{i=1}^{n} (\sup_{x_{i-1}\leq y\leq x_{i}} f(y)) \chi_{[x_{i-1},x_{i})}(x)
\end{gather}
$$

其中 $\chi_{[x_{i-1},x_{i})}(x)=1$ 如果 $x \in[x_{i-1},x_{i})$，否则 $\chi_{[x_{i-1},x_{i})}(x)=0$。则我们有

$$
\begin{gather}
\int _{-\pi}^{\pi} \lvert f^{*}(x)-f(x) \rvert  \, \mathrm{d}x =U(P,f)-\int _{-\pi}^{\pi} f(x) \, \mathrm{d}x <\varepsilon^{2}
\end{gather}
$$

![](8-2.png)

取 $\delta>0$，构造连续函数 $h$ 如下：对于 $i=1,\dots,n-1$，在区间 $[x_{i-1}+\delta,x_{i}-\delta]$ 上令 $h(x)=f^{*}(x)$，在 $[x_{i}-\delta,x_{i}+\delta]$ 上用直线连接 $f^{*}(x_{i}-\delta)$ 和 $f^{*}(x_{i}+\delta)$。在 $x_{0}=-\pi$ 与 $x_{n}=\pi$ 处分别只需做半边插值：在 $[-\pi,-\pi+\delta]$ 上用直线连接 $f(-\pi)$ 与 $f^{*}(-\pi+\delta)$，在 $[\pi-\delta,\pi]$ 上连接 $f^{*}(\pi-\delta)$ 与 $f(\pi)$。

于是，$h$ 与 $f^{*}$ 仅在 $n$ 个长度为 $2\delta$ 的区间上不同。设 $M=\sup\lvert f(x) \rvert$，则

$$
\begin{gather}
\int _{-\pi}^{\pi} \lvert h(x)-f^{*}(x) \rvert \, \mathrm{d}x \leq 2M\cdot 2n\delta
\end{gather}
$$

于是当 $\delta$ 足够小时，可以使上式小于 $\varepsilon^{2}$。

根据三角不等式，我们就有

$$
\begin{gather}
\int _{-\pi}^{\pi} \lvert f(x)-h(x) \rvert  \, \mathrm{d}x <2\varepsilon^{2}
\end{gather}
$$

从而

$$
\begin{align}
\lVert f-h \rVert _{2}^{2} &= \frac{1}{2\pi} \int _{-\pi}^{\pi} \lvert f(x)-h(x) \rvert ^{2} \, \mathrm{d}x  \\
&\leq \frac{2M}{2\pi} \int _{-\pi}^{\pi} \lvert f(x)-h(x) \rvert  \, \mathrm{d}x  \\
&<C\varepsilon^{2}
\end{align}
$$

即 $\lVert f-h \rVert_{2}<C'\varepsilon$。（这也解释了为什么最初要选取 $U-L<\varepsilon^{2}$。）根据 $\varepsilon$ 的任意性，我们可以将 $\varepsilon$ 替换为 $\varepsilon /C'$，得到 $\lVert f-h \rVert_{2}<\varepsilon$。

根据 [[#Theorem 8.16]]，存在三角多项式 $P$ 使得

$$
\begin{gather}
\lVert P-h \rVert _{2}\leq \sup \lvert P(x)-h(x) \rvert <\varepsilon
\end{gather}
$$

如果 $P$ 的次数为 $N_{0}$，那么根据 [[#Theorem 8.12]]，对任意 $N\geq N_{0}$，有

$$
\begin{gather}
\lVert h-s_{N}(h) \rVert _{2}\leq \lVert h-P \rVert _{2}<\varepsilon
\end{gather}
$$

再根据 Bessel 不等式，有

$$
\begin{gather}
\lVert s_{N}(h)-s_{N}(f) \rVert _{2}=\lVert s_{N}(h-f) \rVert _{2}\leq \lVert h-f \rVert _{2}<\varepsilon
\end{gather}
$$

于是由 $\lVert \cdot \rVert_{2}$ 的三角不等式（将 $\lVert \cdot \rVert_{2}^{2}$ 写成内积形式然后展开即证），得到

$$
\begin{gather}
\lVert f-s_{N}(f) \rVert _{2}<3\varepsilon \quad (N\geq N_{0})
\end{gather}
$$

这就完成了 Fourier 定理的证明。

接下来，

$$
\begin{gather}
\frac{1}{2\pi} \int _{-\pi}^{\pi} s_{N}(f) \overline{g} \, \mathrm{d}x =\sum_{n=-N}^{N} \frac{1}{2\pi} \int _{-\pi}^{\pi} c_{n} e^{inx} \overline{g(x)} \, \mathrm{d}x =\sum_{n=-N}^{N} c_{n} \overline{\gamma}_{n}
\end{gather}
$$

则 Cauchy-Schwarz 不等式给出

$$
\begin{gather}
\left\lvert  \int f \overline{g}-\int s_{N}(f)\overline{g}  \right\rvert  \leq \int \lvert f-s_{N}(f) \rvert \lvert g \rvert \leq \left( \int \lvert f-s_{N}(f) \rvert ^{2} \right)^{1/2} \left( \int \lvert g \rvert ^{2} \right)^{1/2}
\end{gather}
$$

右边在 $N\to \infty$ 时趋于 $0$，从而

$$
\begin{gather}
\frac{1}{2\pi} \int f \overline{g}=\sum_{n=-\infty}^{\infty} c_{n} \overline{\gamma}_{n}
\end{gather}
$$

取 $g=f$ 即得

$$
\begin{gather}
\frac{1}{2\pi} \int \lvert f \rvert ^{2}=\sum_{n=-\infty}^{\infty} \lvert c_{n} \rvert ^{2}
\end{gather}
$$

这就完成了 Parseval 定理的证明。

# The Gamma Function

## Definition 8.18

对于 $0<x<\infty$，定义

$$
\begin{gather}
\Gamma(x)=\int _{0}^{\infty} t^{x-1} e^{-t} \, \mathrm{d}t \tag{8.18.1}
\end{gather}
$$

以上积分对任意 $x>0$ 都收敛：将积分分成两部分

$$
\begin{gather}
\int _{0}^{1} t^{x-1}e^{-t} \, \mathrm{d}t +\int _{1}^{\infty} t^{x-1}e^{-t} \, \mathrm{d}t 
\end{gather}
$$

由于 $t^{x-1}e^{-t}\leq t^{x-1}$，且 $\int _{0}^{1}t^{x-1} \, \mathrm{d}t=1 /x$，因此前者收敛。对于后者，容易证明 $t^{x-1}e^{-t /2}$ 在 $t \in(1,\infty)$ 上先增大后减小，因而有最大值 $M$，从而 $t^{x-1}e^{-t}\leq Me^{-t /2}$。由于 $\int _{1}^{\infty}e^{-t/2} \, \mathrm{d}t<\infty$，因此 $\Gamma(x)$ 对任意 $0<x<\infty$ 都有定义。

## Theorem 8.19

(a) $\Gamma$ 满足函数方程 $\Gamma(x+1)=x\Gamma(x)$，其中 $0<x<\infty$。
(b) 对 $n=1,2,\dots$ 有 $\Gamma(n+1)=n!$。
(c) $\log \Gamma$ 在 $(0,\infty)$ 上凸。

### Proof

(a) 应用分部积分得

$$
\begin{align}
\Gamma(x+1) &= \int _{0}^{\infty} t^{x} e^{-t} \, \mathrm{d}t  \\
&= \left. -t^{x} e^{-t} \right| _{t=0}^{t=\infty}+\int _{0}^{\infty} x t^{x-1} e^{-t} \, \mathrm{d}t  \\
&=x \Gamma(x)
\end{align}
$$

(b) 是 (a) 以及 $\Gamma(1)=1$ 的推论。对于 (c)，取 $1<p<\infty$ 以及 $1 /p+1 /q=1$，应用 Holder 不等式得

$$
\begin{align}
\Gamma\left( \frac{x}{p}+\frac{y}{q} \right) &= \int _{0}^{\infty} t^{(x-1)/p+(y-1)/q} e^{-t/p-t/q} \, \mathrm{d}t  \\
&\leq \left( \int _{0}^{\infty} t^{x-1} e^{-t} \, \mathrm{d}t  \right)^{1/p} \left( \int _{0}^{\infty} t^{y-1}e^{-t} \, \mathrm{d}t  \right)^{1/q} \\
&=\Gamma(x)^{1/p}\Gamma(y)^{1/q}
\end{align}
$$

即

$$
\begin{gather}
\log\Gamma\left( \frac{x}{p}+\frac{y}{q} \right)\leq \frac{1}{p}\log \Gamma(x)+\frac{1}{q}\log\Gamma(y)
\end{gather}
$$

这等价于 $\log\Gamma$ 的凸性。

以下定理表明，上面三个性质完全确定了 $\Gamma$ 的取值。

## Theorem 8.20 (Bohr-Mollerup)

如果 $f$ 是 $(0,\infty)$ 上的正函数，满足性质

1. $f(x+1)=xf(x)$，
2. $f(1)=1$，
3. $\log f$ 是凸函数。

那么 $f=\Gamma$。

### Proof

由于 $\Gamma$ 满足性质 (1)(2)(3)，我们只需证明由以上性质定义的函数 $f$ 是唯一的。又因为 $f$ 在 $(1,\infty)$ 上的取值完全取决于其在 $(0,1)$ 上的取值，下面我们假设 $0<x<1$。

令 $\phi=\log f$，则

$$
\begin{gather}
\phi(x+1)=\phi(x)+\log x \quad (0<x<\infty)
\end{gather}
$$

$\phi(1)=0$，$\phi$ 是凸函数。根据凸函数的一种等价定义，对任意 $0<x<1$ 和正整数 $n$，有

$$
\begin{gather}
\frac{\phi(n+1)-\phi(n)}{(n+1)-n}\leq \frac{\phi(n+1+x)-\phi(n+1)}{(n+1+x)-(n+1)}\leq \frac{\phi(n+2)-\phi(n+1)}{(n+2)-(n+1)}
\end{gather}
$$

即

$$
\begin{gather}
\log n\leq \frac{\phi(n+1+x)-\phi(n+1)}{x}\leq \log(n+1)
\end{gather}
$$

再根据

$$
\begin{gather}
\phi(n+1+x)=\phi(x)+\log x(x+1)\cdots (x+n),\quad \phi(n+1)=\log(n!)
\end{gather}
$$

因此

$$
\begin{gather}
0\leq \phi(x)-\log \frac{n! n^{x}}{x(x+1)\cdots (x+n)}\leq x \log\left( 1+\frac{1}{n} \right)
\end{gather}
$$

当 $n\to \infty$ 时，右侧表达式趋于 $0$，从而 $\phi$ 在 $(0,1)$ 上是唯一确定的，这就完成了证明。

作为副产物，我们得到了 $\Gamma$ 函数的乘积公式

$$
\begin{gather}
\Gamma(x)=\lim_{ n \to \infty } \frac{n!n^{x}}{x(x+1)\cdots (x+n)}
\end{gather}
$$

上式在 $(0,1)$ 上成立。而根据 $\Gamma(x+1)=x\Gamma(x)$，我们可以将其推广到所有 $0<x<\infty$。

## Theorem 8.21

如果 $x,y>0$，则

$$
\begin{gather}
\int _{0}^{1} t^{x-1}(1-t)^{y-1} \, \mathrm{d}t =\frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)} \tag{8.21.1}
\end{gather}
$$

上面的积分就是 Beta 函数 $\mathrm{B}(x,y)$。

### Proof

我们有 $\mathrm{B}(1,y)=1 /y$，并且根据 Holder 不等式，$\log \mathrm{B}(x,y)$ 是关于 $x$ 的凸函数。应用分部积分，有

$$
\begin{align}
\mathrm{B}(x+1,y) &= \int _{0}^{1} \left( \frac{t}{1-t} \right)^{x}(1-t)^{x+y-1} \, \mathrm{d}t  \\
&=\int _{0}^{1} \frac{x}{x+y} \frac{1}{(1-t)^{2}} \left( \frac{t}{1-t} \right)^{x-1} (1-t)^{x+y} \, \mathrm{d}t \\
&=\frac{x}{x+y} \mathrm{B}(x,y)
\end{align}
$$

于是，定义为

$$
\begin{gather}
f(x)=\frac{\Gamma(x+y)}{\Gamma(y)}\mathrm{B}(x,y)
\end{gather}
$$

的函数 $f$ 满足 [[#Theorem 8.20 (Bohr-Mollerup)]] 中的三个性质，从而有 $f(x)=\Gamma(x)$。

在 $(8.21.1)$ 中做替换 $t=\sin^{2}\theta$ 得到

$$
\begin{gather}
2 \int _{0}^{\pi /2} (\sin\theta)^{2x-1} (\cos\theta)^{2y-1} \, \mathrm{d}\theta = \frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)}
\end{gather}
$$

取 $x=y=1 /2$ 即得

$$
\begin{gather}
\Gamma\left( \frac{1}{2} \right)=\sqrt{ \pi }
\end{gather}
$$

于是

$$
\begin{gather}
f(x)=\frac{2^{x-1}}{\sqrt{ \pi }} \Gamma\left( \frac{x}{2} \right)\Gamma\left( \frac{x+1}{2} \right)
\end{gather}
$$

满足 [[#Theorem 8.20 (Bohr-Mollerup)]] 的三个条件，从而 $f=\Gamma$。

在 $(8.18.1)$ 中令 $t=s^{2}$，则有

$$
\begin{gather}
\Gamma(x)=2 \int _{0}^{\infty} s^{2x-1}e^{-s^{2}} \, \mathrm{d}s 
\end{gather}
$$

当 $x=1 /2$ 时我们就有

$$
\begin{gather}
2 \int _{0}^{\infty} e^{-s^{2}} \, \mathrm{d}s =\int _{-\infty}^{\infty} e^{-s^{2}} \, \mathrm{d}s =\sqrt{ \pi }
\end{gather}
$$

## Theorem 8.22 (Stirling)

$$
\begin{gather}
\lim_{ x \to \infty } \frac{\Gamma(x+1)}{(x /e)^{x}\sqrt{ 2\pi x }}=1
\end{gather}
$$

特别地，当 $n\to \infty$ 时，

$$
\begin{gather}
n! \sim \left( \frac{n}{e} \right)^{n} \sqrt{ 2\pi n }
\end{gather}
$$

### Proof

在 $(8.18.1)$ 中做替换 $t=x(1+u)$，有

$$
\begin{gather}
\Gamma(x+1)=x^{x+1}e^{-x} \int _{-1}^{\infty} ((1+u)e^{-u})^{x} \, \mathrm{d}u \tag{8.22.1}
\end{gather}
$$

定义 $h(u)$ 为 $h(0)=1$，且

$$
\begin{gather}
(1+u)e^{-u}=\exp\left( -\frac{u^{2}}{2}h(u) \right)
\end{gather}
$$

则当 $-1<u<\infty,u\neq 0$ 时，有

$$
\begin{gather}
h(u)=\frac{2}{u^{2}}(u-\log(1+u))
\end{gather}
$$

因此 $h$ 是连续的，且当 $u$ 从 $-1$ 增长到 $\infty$ 时，$h(u)$ 从 $\infty$ 递减至 $0$。

在 $(8.22.1)$ 中做替换 $u=s\sqrt{ 2 /x }$，则有

$$
\begin{gather}
\Gamma(x+1)=x^{x}e^{-x}\sqrt{ 2x } \int _{-\infty}^{\infty} \psi_{x}(s) \, \mathrm{d}s \tag{8.22.2}
\end{gather}
$$

其中

$$
\begin{gather}
\psi_{x}(s)=\begin{cases}
\exp(-s^{2}h(s \sqrt{ 2 /x })), & s>-\sqrt{ x /2 } \\
0, & s\leq -\sqrt{ x /2 }
\end{cases}
\end{gather}
$$

对于 $\psi_{x}(s)$，我们有如下结论：

1. 对任意 $s$，当 $x\to \infty$ 时有 $\psi_{x}(s)\to e^{-s^{2}}$，
2. 当 $s<0$ 时，$0<\psi_{x}(s)<e^{-s^{2}}$，
3. 当 $s>0$ 且 $x>1$ 时，$0<\psi_{x}(s)<\psi_{1}(s)$，
4. $\int _{0}^{\infty} \psi_{1}(s) \, \mathrm{d}s<\infty$。

于是，根据 Lebesgue 控制收敛定理，积分 $(8.22.2)$ 在 $x\to \infty$ 时收敛于

$$
\begin{gather}
\int _{-\infty}^{\infty} e^{-s^{2}} \, \mathrm{d}s =\sqrt{ \pi }
\end{gather}
$$

这就完成了证明。