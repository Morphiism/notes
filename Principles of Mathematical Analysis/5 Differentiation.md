本章我们将只考虑实数区间上的实值函数，因为多变量函数的微分性质与单变量函数的微分性质具有本质上的不同，并且单变量函数的相当一部分结论无法推广至更高维。

# The Derivative of a Real Function 实值函数的导数

## Definition 5.1 derivative 导数，differentiable 可微的

设 $f$ 是定义在 $[a,b]$ 上的实值函数，对任意 $x \in[a,b]$，定义微商

$$
\begin{gather}
\phi(t)=\frac{f(t)-f(x)}{t-x} \quad (a<t<b,t\neq x)
\end{gather}
$$

并定义

$$
\begin{gather}
f'(x)=\lim_{ t \to x } \phi(t)
\end{gather}
$$

如果右侧的极限存在且有限。

于是对任意 $f$，我们可以定义一个函数 $f'$，其定义域为使得上述极限存在且有限的点集，称为 $f$ 的导数。

如果 $f'$ 在 $x$ 处有定义，则称 $f$ 在 $x$ 处可微。如果 $f$ 在 $E\subset[a,b]$ 上的每一点处可微，则称 $f$ 在 $E$ 上可微。

在以上定义中将极限替换为相应的左右极限，我们就可以定义相应的左导数与右导数。特别地，在区间的端点 $a,b$ 处，如果 $f'$ 存在，那么它就是一个左导数（$x=b$）或右导数（$x=a$）。如果 $f$ 定义在开区间 $(a,b)$ 上，那么我们便不需要考虑端点处的行为，因此我们通常假设 $f$ 在某个开集上可微。

## Theorem 5.2

设 $f$ 定义在 $[a,b]$ 上，且 $f$ 在 $x \in[a,b]$ 处可微，则 $f$ 在 $x$ 处连续。

### Proof

当 $t\to x$ 时，我们有

$$
\begin{gather}
f(t)-f(x)= \frac{f(t)-f(x)}{t-x}\cdot(t-x) \to f'(x)\cdot 0=0
\end{gather}
$$

即 $\lim_{ t \to x }f(t)=f(x)$。

以上定理的逆命题是不成立的，容易构造一个连续但在一点不可微的函数：$x\mapsto \lvert x \rvert$。通过一些更高等的技术，我们甚至可以构造一个连续且处处不可微的函数。

## Theorem 5.3

设 $f,g$ 定义在 $[a,b]$ 上，且在 $x \in[a,b]$ 可微，则 $f+g,fg,f /g$ 在 $x$ 处可微，并且

1. $(f+g)'(x)=f'(x)+g'(x)$，
2. $(fg)'(x)=f'(x)g(x)+f(x)g'(x)$，
3. $(f /g)'(x)=(f'(x)g(x)-f(x)g'(x)) /g(x)^{2}$。

其中对于 $f /g$ 我们要求 $g(x)\neq 0$。

### Proof

(1) 根据极限的代数性质即证。对于 (2)，我们应用恒等式

$$
\begin{gather}
(fg)(t)-(fg)(x)=f(t)(g(t)-g(x))+g(x)(f(t)-f(x))
\end{gather}
$$

两边除以 $t-x$ 然后令 $t\to x$，根据 $f(t)\to f(x)$ 以及导数的定义即证。

最后，我们有

$$
\begin{gather}
\frac{(f /g)(t)-(f /g)(x)}{t-x}=\frac{1}{g(t)g(x)}\left( g(x) \frac{f(t)-f(x)}{t-x} - f(x) \frac{g(t)-g(x)}{t-x} \right)
\end{gather}
$$

令 $t\to x$ 即证。

## Example 5.4

任何常数的导数显然是零。函数 $f(x)=x$ 的导数为 $f'(x)=1$。根据 [[#Theorem 5.3]](2)(3) 以及归纳法可证 $x^{n}$ 的导数为 $n x^{n-1}$，其中 $n \in \mathbb{Z}$。于是任何多项式和有理函数在 $\mathbb{R}$ 上都是可微的，除了分母为零的那些点外。

## Theorem 5.5 (链式法则)

设 $f$ 在 $[a,b]$ 上连续，在 $x \in[a,b]$ 处可微，$g$ 在包含 $f([a,b])$ 的区间 $I$ 上有定义，且在 $f(x)$ 处可微，则函数 $h=g\circ f$ 在 $x$ 处可微，并且

$$
\begin{gather}
h'(x)=g'(f(x))f'(x)
\end{gather}
$$

### Proof

设 $y=f(x)$，根据导数的定义，我们有

$$
\begin{gather}
f(t)-f(x)=(t-x)(f'(x)+u(t)) \\
g(s)-g(y)=(s-y)(g'(y)+v(s))
\end{gather}
$$

其中 $t \in[a,b],s \in I$，且 $\lim_{ t \to x }u(t)=\lim_{ s \to y }v(s)=0$。令 $s=f(t)$，则

$$
\begin{align}
h(t)-h(x) &= g(f(t))-g(f(x)) \\
&= (s-y)(g'(y)+v(s)) \\
&= (t-x)(f'(x)+u(t))(g'(y)+v(s))
\end{align}
$$

从而当 $t\neq x$ 时有

$$
\begin{gather}
\frac{h(t)-h(x)}{t-x}=(g'(y)+v(s))(f'(x)+u(t))
\end{gather}
$$

根据 $f$ 的连续性，当 $t\to x$ 时 $s\to y$，因此 $v(s)\to 0$，即证 $h'(x)=g'(y)f'(x)$。

### Remark

注意，在上面的证明中我们只用到了 $f$ 在 $x$ 处连续的性质，因此 $f$ 在 $[a,b]$ 上连续的条件是不必要的。加入这一条件是为了保持复合函数 $h$ 在整个区间 $[a,b]$ 上有定义，从而避免一些繁琐的定义域讨论。

## Example 5.6

(a) 定义函数 $f$ 为

$$
\begin{gather}
f(x)=\begin{cases}
x \sin (1 /x), & x\neq 0 \\
0, & x=0
\end{cases}
\end{gather}
$$

假设 $\sin'(x)=\cos(x)$ 已给定，则当 $x\neq 0$ 时我们有

$$
\begin{gather}
f'(x)=\sin\left( \frac{1}{x} \right)-\frac{1}{x} \cos \left( \frac{1}{x} \right)
\end{gather}
$$

在 $x=0$ 处，我们无法再使用 [[#Theorem 5.3]] 和 [[#Theorem 5.5 (链式法则)]] 了，因此我们只能使用定义：

$$
\begin{gather}
\frac{f(t)-f(0)}{t-0}=\sin \left( \frac{1}{t} \right)
\end{gather}
$$

当 $t\to 0$ 时，后者不趋于任何实数，因此 $f$ 在 $x=0$ 处不可微。

(b) 定义函数 $f$ 为

$$
\begin{gather}
f(x)=\begin{cases}
x^{2} \sin(1 /x), & x\neq 0 \\
0, & x=0
\end{cases}
\end{gather}
$$

和 (a) 一样，当 $x\neq 0$ 时我们有

$$
\begin{gather}
f'(x)=2x \sin\left( \frac{1}{x} \right)-\cos \left( \frac{1}{x} \right)
\end{gather}
$$

在 $x=0$ 处我们使用定义，得到

$$
\begin{gather}
\left\lvert  \frac{f(t)-f(0)}{t-0}  \right\rvert =\left\lvert  t \sin \left( \frac{1}{t} \right)  \right\rvert \leq \lvert t \rvert 
\end{gather}
$$

当 $t\to 0$ 时，上式趋于 $0$，因此 $f'(0)=0$。从而 $f$ 在 $\mathbb{R}$ 上可微，但 $f'$ 不是连续函数，因为 $\cos(1 /x)$ 在 $x=0$ 处不连续。

# Mean Value Theorems 中值定理

## Definition 5.7 local maximum (minimum) 局部最大值（最小值）

设 $f$ 是度量空间 $X$ 上的实值函数，称 $f$ 在 $p \in X$ 处有局部最大值（最小值）如果存在 $\delta>0$ 使得对任意 $q \in B_{X}(p,\delta)$ 有 $f(q)\leq f(p)$（$f(q)\geq f(p)$）。

## Theorem 5.8 (Fermat)

设 $f$ 在 $[a,b]$ 上有定义，如果 $f$ 在 $x \in[a,b]$ 处可微且有局部最大值，则 $f'(x)=0$。

类似的结论对局部最小值同样成立。

### Proof

取 $\delta>0$ 如 [[#Definition 5.7 local maximum (minimum) 局部最大值（最小值）]] 所示。当 $x-\delta<t<x$ 时，我们有

$$
\begin{gather}
\frac{f(t)-f(x)}{t-x}\geq 0
\end{gather}
$$

因此当 $t\to x$ 时有 $f'(x)\geq 0$。

当 $x<t<x+\delta$ 时，我们有

$$
\begin{gather}
\frac{f(t)-f(x)}{t-x}\leq 0
\end{gather}
$$

因此当 $t\to x$ 时有 $f'(x)\leq 0$。结合以上两个不等式，即得 $f'(x)=0$。

## Theorem 5.9 (Cauchy)

设 $f,g$ 在 $[a,b]$ 上连续，在 $(a,b)$ 上可微，则存在 $x \in(a,b)$ 使得

$$
\begin{gather}
(f(b)-f(a))g'(x)=(g(b)-g(a))f'(x)
\end{gather}
$$

### Proof

取

$$
\begin{gather}
h(t)=(f(b)-f(a))g(t)-(g(b)-g(a))f(t)
\end{gather}
$$

则 $h$ 在 $[a,b]$ 上连续，在 $(a,b)$ 上可微，并且

$$
\begin{gather}
h(a)=f(b)g(a)-f(a)g(b)=h(b)
\end{gather}
$$

下面我们要证存在 $x \in(a,b)$ 使得 $h'(x)=0$。（Rolle 定理）

如果 $h$ 是常数，那么 $h'(x)=0$ 对任意 $x$ 成立。否则，$h$ 必然在 $(a,b)$ 中的一点 $x$ 取到它的最大值或者最小值（根据最值定理），从而根据 [[#Theorem 5.8 (Fermat)]] 知 $h'(x)=0$，这就完成了证明。

以上定理通常称为广义中值定理，从而与下面的经典中值定理做区分：

## Theorem 5.10 (Lagrange)

设 $f$ 在 $[a,b]$ 上连续，在 $(a,b)$ 上可微，则存在 $x \in(a,b)$ 使得

$$
\begin{gather}
f(b)-f(a)=(b-a)f'(x)
\end{gather}
$$

### Proof

在 [[#Theorem 5.9 (Cauchy)]] 中取 $g(x)=x$ 即可。

## Theorem 5.11

设 $f$ 在 $(a,b)$ 上可微，则对任意 $x \in(a,b)$，如果

1. $f'(x)\geq 0$，那么 $f$ 单调递增。
2. $f'(x)=0$，那么 $f$ 是常数。
3. $f'(x)\leq 0$，那么 $f$ 单调递减。

### Proof

所有结论都可以从等式

$$
\begin{gather}
f(x_{2})-f(x_{1})=(x_{2}-x_{1})f'(x)
\end{gather}
$$

中读出，其中 $a<x_{1}<x<x_{2}<b$。

# The Continuity of Derivatives 导数的连续性

我们从 [[#Example 5.6]](b) 中看到，一个可微函数 $f$ 可以有一个在某点处间断的导数 $f'$。然而，所有在某个闭区间上有定义的导数与连续函数有一个共同点：它们都具有介值性。这也从另一个方面说明了介值性并不蕴含连续性。

## Theorem 5.12 (Darboux)

设 $f$ 是 $[a,b]$ 上的实值可微函数，并假设 $f'(a)<\lambda<f'(b)$，则存在 $x \in(a,b)$ 使得 $f'(x)=\lambda$。

类似的结论对 $f'(a)>f'(b)$ 也成立。

### Proof

取 $g(t)=f(t)-\lambda t$，则 $g'(t)=f'(t)-\lambda$，我们要证存在 $x \in(a,b)$ 使得 $g'(x)=0$。

由于 $g'(a)<0$，因此存在 $t_{1}\in(a,b)$ 使得 $g(t_{1})<g(a)$。同理存在 $t_{2}\in(a,b)$ 使得 $g(t_{2})<g(b)$。这表明 $g$ 在 $(a,b)$ 中的一点 $x$ 处取到最小值，从而 $g'(x)=0$。

## Corollary 5.13

如果 $f$ 在 $[a,b]$ 上可微，那么 $f'$ 在 $[a,b]$ 上没有简单间断点。

但 $f'$ 仍然可以有第二类间断点。这显示了介值性的作用：它能够排除简单间断点，但无法排除第二类间断点，正是后者阻碍了 $\sin(1 /x)$ 成为 $\mathbb{R}$ 上的连续函数。

# L'Hospital's Rule

## Theorem 5.14 (L'Hospital)

设 $f,g$ 在 $(a,b)$ 上可微，其中 $-\infty\leq a<b\leq+\infty$，且对任意 $x \in(a,b)$ 有 $g'(x)\neq 0$。假设

$$
\begin{gather}
\lim_{ x \to a } \frac{f'(x)}{g'(x)}=A \quad (A \in \overline{\mathbb{R}})
\end{gather}
$$

如果

$$
\begin{gather}
\lim_{ x \to a } f(x)=\lim_{ x \to a } g(x)=0
\end{gather}
$$

或者如果

$$
\begin{gather}
\lim_{ x \to a } g(x)=+\infty
\end{gather}
$$

那么

$$
\begin{gather}
\lim_{ x \to a } \frac{f(x)}{g(x)}=A
\end{gather}
$$

类似的结论对 $x\to b$ 以及 $g(x)\to -\infty$ 的情况也成立。

### Proof

我们首先考虑 $-\infty\leq A<+\infty$，取 $q \in \mathbb{R}$ 使得 $A<q$，并取 $r$ 使得 $A<r<q$。则存在 $c \in(a,b)$ 使得对任意 $a<x<c$ 有

$$
\begin{gather}
\frac{f'(x)}{g'(x)}< r
\end{gather}
$$

如果 $a<x<y<c$，则中值定理表明存在 $x<t<y$ 使得

$$
\begin{gather}
\frac{f(x)-f(y)}{g(x)-g(y)}=\frac{f'(t)}{g'(t)}<r
\end{gather}
$$

首先假设 $f(x)\to 0,g(x)\to 0$，则当 $x\to a$ 时有

$$
\begin{gather}
\frac{f(y)}{g(y)}\leq r<q \quad (a<y<c)
\end{gather}
$$

接下来假设 $g(x)\to +\infty$，固定 $y$，则存在 $c_{1}\in(a,y)$ 使得当 $a<x<c_{1}$ 时有 $g(x)>g(y)$ 且 $g(x)>0$。于是

$$
\begin{gather}
\frac{f(x)}{g(x)}< r-r \frac{g(y)}{g(x)}+\frac{f(y)}{g(x)} \quad (a<x<c_{1})
\end{gather}
$$

如果我们令 $x\to a$，则存在 $c_{2}\in(a,c_{1})$ 使得

$$
\begin{gather}
\frac{f(x)}{g(x)}<q \quad (a<x<c_{2})
\end{gather}
$$

综上，对任意 $A<q$，存在 $c_{2}$ 使得对 $a<x<c_{2}$ 有 $f(x) /g(x)<q$。

同理，对于 $-\infty<A\leq+\infty$ 和任意 $p<A$，存在 $c_{3}$ 使得 $a<x<c_{3}$ 蕴含 $f(x) /g(x)>p$。这就完成了证明。

L'Hospital 法则通常用来处理所谓的 $0 /0$ 型或 $A /\infty$ 型未定式极限，它允许我们对分子和分母同时求导以得到一个更简单的极限。

# Derivatives of Higher Order 高阶导数

## Definition 5.15

如果 $f$ 在一个区间上有导数 $f'$，而 $f'$ 自身在区间上也可导，我们用 $f''$ 来表示 $f'$ 的导数，称为 $f$ 的二阶导数。以此类推，我们可以得到函数

$$
\begin{gather}
f,f',f'',f^{(3)},\dots,f^{(n)},\dots
\end{gather}
$$

其中每个 $f^{(n)}$ 都是前一个函数 $f^{(n-1)}$ 的导数，并且我们称 $f^{(n)}$ 为 $f$ 的 $n$ 阶导数。

要使得 $f^{(n)}(x)$ 存在，$f^{(n-1)}$ 就必须在 $x$ 的邻域（或单边邻域）内存在，并且在 $x$ 处可微。由于 $f^{(n-1)}$ 在邻域内存在，$f^{(n-2)}$ 就必须在该邻域内可微。换句话说，在一点处 $n$ 阶导数的存在性能够蕴含该点邻域内 $n-1$ 阶导数的存在性。

# Taylor's Theorem 泰勒定理

## Theorem 5.16 (Taylor)

设 $f$ 是 $[a,b]$ 上的实值函数，$n \in \mathbb{N}^{*}$，$f^{(n-1)}$ 在 $[a,b]$ 上连续，$f^{(n)}(t)$ 在任意 $t \in (a,b)$ 上有定义。设 $\alpha,\beta$ 是 $[a,b]$ 上不同的两点，并定义

$$
\begin{gather}
P(t)=\sum_{k=0}^{n-1} \frac{f^{(k)}(\alpha)}{k!} (t-\alpha)^{k}
\end{gather}
$$

则存在位于 $\alpha,\beta$ 之间的点 $x$ 使得

$$
\begin{gather}
f(\beta)=P(\beta)+\frac{f^{(n)}(x)}{n!}(\beta-\alpha)^{n}
\end{gather}
$$

这就是说，$f$ 可以被一个 $n-1$ 次的多项式所近似，并且如果我们可以计算出 $f^{(n)}(x)$，那么我们还可以给出近似误差的一个估计。当 $n=1$ 时，以上定理就退化为了中值定理。

### Proof

设 $M$ 定义为

$$
\begin{gather}
f(\beta)=P(\beta)+M(\beta-\alpha)^{n}
\end{gather}
$$

并取

$$
\begin{gather}
g(t)=f(t)-P(t)-M(t-\alpha)^{n} \quad (a\leq t\leq b)
\end{gather}
$$

我们要证存在位于 $\alpha,\beta$ 之间的点 $x$ 使得 $n!M=f^{(n)}(x)$。由于 $P$ 的次数最多为 $n-1$ 次，因此 $P^{(n)}=0$，从而

$$
\begin{gather}
g^{(n)}(t)=f^{(n)}(t)-n!M
\end{gather}
$$

于是我们只需证明存在 $x$ 使得 $g^{(n)}(x)=0$。

由于对 $k=0,1,\dots,n-1$ 有 $P^{(k)}(\alpha)=f^{(k)}(\alpha)$，故

$$
\begin{gather}
g(\alpha)=g'(\alpha)=\dots=g^{(n-1)}(\alpha)=0
\end{gather}
$$

$M$ 的定义表明 $g(\beta)=0$，因此根据中值定理，存在 $x_{1}$ 介于 $\alpha,\beta$ 之间，使得 $g'(x_{1})=0$；于是又有 $x_{2}$ 介于 $\alpha$ 与 $x_{1}$ 之间，使得 $g''(x_{2})=0$。以此类推，我们可知存在 $x=x_{n}$ 介于 $\alpha$ 与 $x_{n-1}$ 之间，即 $\alpha$ 和 $\beta$ 之间，使得 $g^{(n)}(x)=0$。

# Differentiation of Vector-Valued Functions 向量值函数的微分

## Remark 5.17

[[#Definition 5.1 derivative 导数，differentiable 可微的]] 可以原封不动地应用到定义在区间 $[a,b]$ 上的复值函数 $f$ 上，并且 [[#Theorem 5.2]] 和 [[#Theorem 5.3]]，以及它们的证明，也同样对 $f$ 适用。如果

$$
\begin{gather}
f(t)=f_{1}(t)+i f_{2}(t)
\end{gather}
$$

其中 $f_{1},f_{2}$ 是实值函数，那么我们显然有

$$
\begin{gather}
f'(t)=f_{1}'(t)+i f_{2}'(t)
\end{gather}
$$

即 $f$ 在 $x$ 处可微当且仅当 $f$ 的实部和虚部均在 $x$ 处可微。

对于单变量向量值函数 $\mathbf{f}\colon[a,b]\to \mathbb{R}^{k}$ 也是一样的。此时它的微商 $\phi(t)$ 是 $\mathbb{R}^{k}$ 中的一个点，并且其极限是 $\mathbb{R}^{k}$ 上的范数意义下的。这就是说，$\mathbf{f}'(t)$ 是 $\mathbb{R}^{k}$ 中的一个点，使得

$$
\begin{gather}
\lim_{ t \to x } \left\lvert  \frac{\mathbf{f}(t)-\mathbf{f}(x)}{t-x}-\mathbf{f}'(x)  \right\rvert =0
\end{gather}
$$

此外，$\mathbf{f}'$ 也是一个从 $[a,b]$ 到 $\mathbb{R}^{k}$ 的函数。从这里我们也可以看出为什么多变量函数与单变量函数有本质上的不同：我们不能用 $\mathbf{f}(\mathbf{t})-\mathbf{f}(\mathbf{x})\in \mathbb{R}^{k}$ 除以 $\mathbf{t}-\mathbf{x}\in \mathbb{R}^{n}$，因而此时我们需要一种新的可微性定义。

如果 $f_{1},\dots,f_{k}$ 是 $\mathbf{f}$ 的各个分量，那么 $\mathbf{f}$ 在 $x$ 点可微当且仅当每个分量都在 $x$ 点可微，并且

$$
\begin{gather}
\mathbf{f}'(t)=(f_{1}'(t),\dots,f_{k}'(t))
\end{gather}
$$

在这一情况下，[[#Theorem 5.2]] 和 [[#Theorem 5.3]](1)(2) 仍然成立，其中我们要将 [[#Theorem 5.3]](2) 中的 $fg$ 替换成 $\mathbf{f}\cdot \mathbf{g}$，而其证明也几乎是相同的。

然而，当我们转向中值定理以及它的一个推论，即 L'Hospital 法则时，情况发生了改变。下面的例子表明，对于复值函数，这两个定理并不总是成立。

## Example 5.18

对 $x \in \mathbb{R}$，定义

$$
\begin{gather}
f(x)=e^{ ix }=\cos x+i \sin x
\end{gather}
$$

（上式可以视为一个定义或者一个定理，取决于你如何定义指数函数以及三角函数。）则

$$
\begin{gather}
f(2\pi)-f(0)=0
\end{gather}
$$

但

$$
\begin{gather}
f'(x)=i e^{ix} \neq 0
\end{gather}
$$

因此在这种情况下中值定理不成立。

## Example 5.19

在开区间 $(0,1)$ 上，定义 $f(x)=x$ 与

$$
\begin{gather}
g(x)=x+x^{2} e^{i / x^{2}}
\end{gather}
$$

由于 $\lvert e^{i / x^{2}} \rvert=1$ 对任意 $x \in(0,1)$ 成立，因此

$$
\begin{gather}
\lim_{ x \to 0 } \frac{f(x)}{g(x)}=1
\end{gather}
$$

然而，由于

$$
\begin{gather}
g'(x)=1+\left( 2x- \frac{2i}{x} \right) e^{i / x^{2}}
\end{gather}
$$

故

$$
\begin{gather}
\lvert g'(x) \rvert \geq\left\lvert  2x-\frac{2i}{x}  \right\rvert -1\geq \frac{2}{x}-1
\end{gather}
$$

从而

$$
\begin{gather}
\left\lvert  \frac{f'(x)}{g'(x)}  \right\rvert = \frac{1}{\lvert g'(x) \rvert }\leq \frac{x}{2-x}
\end{gather}
$$

当 $x\to 0$ 时上式趋于 $0$，因此在这种情况下 L'Hospital 法则不成立。

然而，对于向量值函数的确存在一个弱化版本的中值定理：从 [[#Theorem 5.10 (Lagrange)]] 中可知

$$
\begin{gather}
\lvert f(b)-f(a) \rvert \leq (b-a) \sup_{a<x<b} \lvert f'(x) \rvert 
\end{gather}
$$

## Theorem 5.20

设 $\mathbf{f}\colon [a,b]\to \mathbb{R}^{k}$ 是连续函数，且在 $(a,b)$ 上可微，则存在 $x \in(a,b)$ 使得

$$
\begin{gather}
\lvert \mathbf{f}(b)-\mathbf{f}(a) \rvert \leq (b-a)\lvert \mathbf{f}'(x) \rvert 
\end{gather}
$$

### Proof (V. P. Havin)

令 $\mathbf{z}=\mathbf{f}(b)-\mathbf{f}(a)$，定义

$$
\begin{gather}
\varphi(t)=\mathbf{z}\cdot \mathbf{f}(t) \quad (a\leq t\leq b)
\end{gather}
$$

则 $\varphi$ 是 $[a,b]$ 上的实值连续函数，且在 $(a,b)$ 上可微。于是中值定理表明存在 $x \in(a,b)$ 使得

$$
\begin{gather}
\varphi(b)-\varphi(a)=(b-a)\varphi'(x)=(b-a)\mathbf{z}\cdot \mathbf{f}'(x)
\end{gather}
$$

另一方面，我们有

$$
\begin{gather}
\varphi(b)-\varphi(a)=\mathbf{z}\cdot (\mathbf{f}(b)-\mathbf{f}(a))=\lvert \mathbf{z} \rvert ^{2}
\end{gather}
$$

因此

$$
\begin{gather}
\lvert \mathbf{z} \rvert ^{2}=(b-a) \lvert \mathbf{z}\cdot \mathbf{f}'(x) \rvert \leq (b-a) \lvert \mathbf{z} \rvert \lvert \mathbf{f}'(x) \rvert 
\end{gather}
$$

两边消去 $\lvert \mathbf{z} \rvert$ 即证（在 $\lvert \mathbf{z} \rvert=0$ 的极端情况下定理是平凡的）。