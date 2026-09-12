本章我们仍然考虑实数区间上的实值函数。将积分推广至区间上向量值函数的方法是很直接的。

# Definition and Existence of the Integral 积分的定义与存在性

这里我们采用 Darboux 给出的 Riemann 积分的等价定义，而非 Riemann 最初的定义，因为前者在计算与定理证明方面更为方便。

## Definition 6.1 partition 划分，upper (lower) Riemann integral 上（下）黎曼积分，Riemann integrable 黎曼可积

给定闭区间 $[a,b]$，它的一个划分 $P$ 定义为有限个点 $x_{0},\dots,x_{n}$，满足

$$
\begin{gather}
a=x_{0}\leq x_{1}\leq\dots\leq x_{n-1}\leq x_{n}=b
\end{gather}
$$

我们记

$$
\begin{gather}
\Delta x_{i}=x_{i}-x_{i-1} \quad (i=1,\dots,n)
\end{gather}
$$

假设 $f$ 是 $[a,b]$ 上的有界实值函数，对每个划分 $P$，我们定义

$$
\begin{gather}
M_{i}=\sup_{x_{i-1}\leq x\leq x_{i}} f(x) \\
m_{i}=\inf_{x_{i-1}\leq x\leq x_{i}} f(x) \\
U(P,f)=\sum_{i=1}^{n} M_{i} \Delta x_{i} \\
L(P,f)=\sum_{i=1}^{n} m_{i}\Delta x_{i}
\end{gather}
$$

以及

$$
\begin{gather}
\overline{\int_{a}^{b}} f \, \mathrm{d}x = \inf_{P} U(P,f) \\
\underline{\int_{a}^{b}} f \, \mathrm{d}x= \sup_{P} L(P,f)
\end{gather}
$$

其中 $P$ 取遍 $[a,b]$ 上的所有划分。以上的两个表达式分别称为 $f$ 在 $[a,b]$ 上的上 Riemann 积分与下 Riemann 积分。

如果 $f$ 的上积分与下积分相等，则称 $f$ 在 $[a,b]$ 上 Riemann 可积，记作 $f \in \mathcal{R}$（即 $\mathcal{R}$ 表示所有 Riemann 可积函数构成的集合），并定义

$$
\begin{gather}
\int_{a}^{b} f \, \mathrm{d}x = \overline{\int_{a}^{b}} f \, \mathrm{d}x=\underline{\int_{a}^{b}} f \, \mathrm{d}x
\end{gather}
$$

称为 $f$ 在 $[a,b]$ 上的 Riemann 积分。

### Motivation

最初定义积分的动机是计算“曲线下方的面积”。具体来说，设 $f$ 是一个函数，它的图像 $\Gamma_{f}=\{ (x,f(x)) : x \in [a,b] \}$ 构成了平面上的一条曲线，从而 $x$ 轴、直线 $x=a$，$x=b$，以及 $\Gamma_{f}$ 共同围成了平面上的一个有界区域。

![](6-1.png)

对于这个区域的面积，我们可以用若干长方形的面积来近似，这就是所谓的 Darboux 上和 $U(P,f)$ 与下和 $L(P,f)$。其中，我们说上和 $U(P,f)$ 从上方逼近 $f$，而下和 $L(P,f)$ 从下方逼近 $f$，因为从图像上来看，组成上和的那些长方形总是位于 $f$ 的上方。同样地，组成下和的长方形总是在 $f$ 的下方。

对于 Riemann 可积函数，当 $P$ 的细度 $\lVert P \rVert=\max \Delta x_{i}\to 0$ 时（此时显然有 $n\to \infty$），上和 $U(P,f)$ 与下和 $L(P,f)$ 分别趋于同一个极限，这就是 $f$ 的 Riemann 积分 $\int _{a}^{b} f \, \mathrm{d}x$，也就是曲线下方这块区域的面积。

根据 $f$ 的有界性，存在 $m,M$ 使得

$$
\begin{gather}
m\leq f(x)\leq M \quad (a\leq x\leq b)
\end{gather}
$$

这表明对任意 $P$，

$$
\begin{gather}
m(b-a)\leq L(P,f)\leq U(P,f)\leq M(b-a)
\end{gather}
$$

因此对于有界函数 $f$ 来说，$f$ 的上积分与下积分总是存在。而它们是否相等的问题则更为困难，需要更为深入的研究。不过，在此之前我们可以对 Riemann 积分的概念做一些推广，这将不会改变之后的大多数定理的表述与证明。

## Definition 6.2 Riemann-Stieltjes integral

设 $\alpha$ 是 $[a,b]$ 上的单调递增函数，对每个划分 $P$，我们定义

$$
\begin{gather}
\Delta\alpha_{i}=\alpha(x_{i})-\alpha(x_{i-1})
\end{gather}
$$

对任意 $[a,b]$ 上的有界实值函数 $f$，定义

$$
\begin{gather}
U(P,f,\alpha)=\sum_{i=1}^{n} M_{i} \Delta \alpha_{i} \\
L(P,f,\alpha)=\sum_{i=1}^{n} m_{i} \Delta \alpha_{i}
\end{gather}
$$

并定义

$$
\begin{gather}
\overline{\int_{a}^{b}} f \, \mathrm{d}\alpha = \inf_{P} U(P,f,\alpha) \\
\underline{\int_{a}^{b}} f \, \mathrm{d}\alpha= \sup_{P} L(P,f,\alpha)
\end{gather}
$$

其中 $P$ 取遍 $[a,b]$ 上的所有划分。

如果 $f$ 关于 $\alpha$ 的上积分与下积分相等，我们就称 $f$ 关于 $\alpha$ Riemann 可积，记作 $f \in \mathcal{R}(\alpha)$，并定义

$$
\begin{gather}
\int_{a}^{b} f \, \mathrm{d}\alpha = \overline{\int_{a}^{b}} f \, \mathrm{d}\alpha=\underline{\int_{a}^{b}} f \, \mathrm{d}\alpha
\end{gather}
$$

称为 $f$ 在 $[a,b]$ 上关于 $\alpha$ 的 Riemann-Stieltjes 积分。

通过取 $\alpha(x)=x$，我们可知 Riemann 积分是 Stieltjes 积分的一个特例。此外，我们还指出，在一般的情况下，$\alpha$ 甚至不需要是一个连续函数。

下面我们固定一个区间 $[a,b]$，$f$ 是有界实值函数，且 $\alpha$ 单调递增。当不致歧义时，我们将 $\int_{a}^{b}$ 简记为 $\int$。

## Definition 6.3 refinement 细化

称划分 $P^{*}$ 是划分 $P$ 的一个细化，如果 $P^{*}\supset P$。（即 $P^{*}$ 是通过向 $P$ 添加划分点得到的。）给定两个划分 $P_{1},P_{2}$，称 $P^{*}=P_{1}\cup P_{2}$ 为它们的公共细化。

## Theorem 6.4

如果 $P^{*}$ 是 $P$ 的细化，则

$$
\begin{gather}
L(P,f,\alpha)\leq L(P^{*},f,\alpha)\leq U(P^{*},f,\alpha)\leq U(P,f,\alpha)
\end{gather}
$$

### Proof

我们首先假设 $P^{*}$ 只比 $P$ 多一个点 $x^{*}$，其位于 $x_{i-1}$ 与 $x_{i}$ 之间，令

$$
\begin{gather}
w_{1}=\inf_{x_{i-1}\leq x\leq x^{*}} f(x) \\
w_{2}=\inf_{x^{*}\leq x\leq x_{i}} f(x)
\end{gather}
$$

则显然 $w_{1}\geq m_{i},w_{2}\geq m_{i}$，从而

$$
\begin{align}
L(P^{*},f,\alpha)-L(P,f,\alpha) &= w_{1}(\alpha(x^{*})-\alpha(x_{i-1}))+w_{2}(\alpha(x_{i})-\alpha(x^{*})) \\
&- m_{i}(\alpha(x_{i})-\alpha(x_{i-1})) \\
&=(w_{1}-m_{i})(\alpha(x^{*})-\alpha(x_{i-1})) \\
&+(w_{2}-m_{i})(\alpha(x_{i})-\alpha(x^{*})) \\
&\geq 0
\end{align}
$$

如果 $P^{*}$ 比 $P$ 多 $k$ 个点，那么我们逐个添加分点，重复以上论证 $k$ 次，即得 $L(P^{*},f,\alpha)\geq L(P,f,\alpha)$。同理可证 $U(P^{*},f,\alpha)\leq U(P,f,\alpha)$。

## Theorem 6.5

$$
\begin{gather}
\underline{\int_{a}^{b}} f \, \mathrm{d}\alpha\leq \overline{\int_{a}^{b}} f \, \mathrm{d} \alpha
\end{gather}
$$

### Proof

任取 $[a,b]$ 的两个划分 $P_{1},P_{2}$，令 $P^{*}$ 为其公共细化，则

$$
\begin{gather}
L(P_{1},f,\alpha)\leq L(P^{*},f,\alpha)\leq U(P^{*},f,\alpha)\leq U(P_{2},f,\alpha)
\end{gather}
$$

在上式中固定 $P_{2}$，对任意 $P_{1}$ 取上确界即得

$$
\begin{gather}
\underline{\int} f \, \mathrm{d}\alpha\leq U(P_{2},f,\alpha)
\end{gather}
$$

再对任意 $P_{2}$ 取下确界就完成了证明。

## Theorem 6.6

在 $[a,b]$ 上有 $f \in \mathcal{R}(\alpha)$ 当且仅当对任意 $\varepsilon>0$，存在划分 $P$ 使得

$$
\begin{gather}
U(P,f,\alpha)-L(P,f,\alpha)<\varepsilon \tag{6.6.1}
\end{gather}
$$

### Proof

对任意划分 $P$，我们有

$$
\begin{gather}
L(P,f,\alpha)\leq \underline{\int } f \, \mathrm{d}\alpha\leq \overline{\int } f \, \mathrm{d}\alpha\leq U(P,f,\alpha)
\end{gather}
$$

因此如果 $U(P,f,\alpha)-L(P,f,\alpha)<\varepsilon$，则有

$$
\begin{gather}
0\leq \overline{\int } f \, \mathrm{d}\alpha- \underline{\int } f \, \mathrm{d}\alpha<\varepsilon
\end{gather}
$$

根据 $\varepsilon$ 的任意性可知上下积分相等，从而 $f \in \mathcal{R}(\alpha)$。

反之，设 $f \in \mathcal{R}(\alpha)$。根据上下确界的性质，对任意 $\varepsilon>0$，存在划分 $P_{1},P_{2}$ 使得

$$
\begin{gather}
U(P_{1},f,\alpha)<\int f \, \mathrm{d}\alpha +\frac{\varepsilon}{2} \\
L(P_{2},f,\alpha)>\int f \, \mathrm{d}\alpha-\frac{\varepsilon}{2} 
\end{gather}
$$

令 $P^{*}$ 为 $P_{1},P_{2}$ 的公共细化，则我们有

$$
\begin{gather}
U(P^{*},f,\alpha)<\int f \, \mathrm{d}\alpha+\frac{\varepsilon}{2} \\
-L(P^{*},f,\alpha)<-\int f \, \mathrm{d}\alpha+\frac{\varepsilon}{2} 
\end{gather}
$$

将以上两式相加即证。

### Remark

我们将 $(6.6.1)$ 写成

$$
\begin{gather}
\sum_{i=1}^{n} (M_{i}-m_{i})\Delta\alpha_{i}<\varepsilon
\end{gather}
$$

其中 $M_{i}-m_{i}$ 称为 $f$ 在区间 $[x_{i-1},x_{i}]$ 上的振幅。在可积性的证明中，要使得 $U-L<\varepsilon$，我们需要同时控制函数的振幅，以及区间的 $\alpha$-长度 $\Delta\alpha_{i}=\alpha(x_{i})-\alpha(x_{i-1})$。我们将看到，侧重于哪方面的控制取决于 $f$ 与 $\alpha$ 各自的连续性：在 $f$ 连续的地方，振幅更容易控制；在 $\alpha$ 连续的地方，长度更容易控制。根据连续性分而治之是分析学中的一种经典方法。

以上是 Riemann 积分的基本存在性定理。下面我们给出它的一些推论。

## Theorem 6.7

(a) 如果不等式 $(6.6.1)$ 对某个 $P$ 和 $\varepsilon$ 成立，那么对于相同的 $\varepsilon$，$(6.6.1)$ 对 $P$ 的任意细化都成立。

(b) 如果 $(6.6.1)$ 对 $P=\{ x_{0},\dots,x_{n} \}$ 成立，且 $s_{i},t_{i}\in[x_{i-1},x_{i}]$，则

$$
\begin{gather}
\sum_{i=1}^{n} \lvert f(s_{i})-f(t_{i}) \rvert \Delta \alpha_{i}<\varepsilon
\end{gather}
$$

(c) 如果 $f \in \mathcal{R}(\alpha)$ 且 (b) 的假设成立，则

$$
\begin{gather}
\left\lvert  \sum_{i=1}^{n} f(t_{i})\Delta\alpha_{i}- \int _{a}^{b} f \, \mathrm{d}\alpha   \right\rvert <\varepsilon
\end{gather}
$$

命题 (c) 表明我们可以用所谓的 Riemann 和 $\sum f(t_{i})\Delta\alpha_{i}$ 来近似积分，这也是 Riemann 积分最初的定义。

### Proof

(a) 由 [[#Theorem 6.4]] 给出。在 (b) 的假设下，由于

$$
\begin{gather}
\lvert f(s_{i})-f(t_{i}) \rvert \leq M_{i}-m_{i}
\end{gather}
$$

因此

$$
\begin{gather}
\sum_{i=1}^{n} \lvert f(s_{i})-f(t_{i}) \rvert \Delta\alpha_{i}\leq U(P,f,\alpha)-L(P,f,\alpha)<\varepsilon
\end{gather}
$$

此外，根据显然的不等式

$$
\begin{gather}
L(P,f,\alpha)\leq \sum_{i=1}^{n} f(t_{i})\Delta\alpha_{i}\leq U(P,f,\alpha)
\end{gather}
$$

以及

$$
\begin{gather}
L(P,f,\alpha)\leq \int _{a}^{b} f \, \mathrm{d}\alpha \leq U(P,f,\alpha)
\end{gather}
$$

立即证明了 (c)。

## Theorem 6.8

如果 $f$ 在 $[a,b]$ 上连续，那么 $f \in \mathcal{R}(\alpha)$。

### Proof

由于 $[a,b]$ 是紧致集，因此 $f$ 在 $[a,b]$ 上有界，并且一致连续。因此，对任意 $\varepsilon>0$，存在 $\delta>0$ 使得

$$
\begin{gather}
\lvert x-y \rvert <\delta \implies \lvert f(x)-f(y) \rvert <\varepsilon
\end{gather}
$$

设 $P$ 是一个划分使得 $\lVert P \rVert<\delta$，则我们有

$$
\begin{gather}
M_{i}-m_{i}\leq \varepsilon \quad (i=1,\dots,n)
\end{gather}
$$

从而

$$
\begin{align}
U(P,f,\alpha)-L(P,f,\alpha) = \sum_{i=1}^{n} (M_{i}-m_{i})\Delta\alpha_{i}\leq \varepsilon (\alpha(b)-\alpha(a))
\end{align}
$$

即证 $f \in \mathcal{R}(\alpha)$。

## Theorem 6.9

如果 $f$ 在 $[a,b]$ 上单调，且 $\alpha$ 在 $[a,b]$ 上连续，则 $f \in \mathcal{R}(\alpha)$。

### Proof

固定 $\varepsilon>0$。对正整数 $n$，取划分 $P_{n}$ 使得

$$
\begin{gather}
\Delta\alpha_{i}=\frac{\alpha(b)-\alpha(a)}{n} \quad (i=1,\dots,n)
\end{gather}
$$

这总是可能的，因为 $\alpha$ 连续，从而有介值性。

我们将假设 $f$ 是单调递增的。则

$$
\begin{gather}
M_{i}=f(x_{i}),\quad m_{i}=f(x_{i-1}) \quad (i=1,\dots,n)
\end{gather}
$$

于是当 $n$ 足够大时，有

$$
\begin{align}
U(P,f,\alpha)-L(P,f,\alpha) &= \frac{\alpha(b)-\alpha(a)}{n} \sum_{i=1}^{n} (f(x_{i})-f(x_{i-1})) \\
&= \frac{\alpha(b)-\alpha(a)}{n}(f(b)-f(a))<\varepsilon
\end{align}
$$

这就完成了证明。

## Theorem 6.10

设 $f$ 在 $[a,b]$ 上有界，只有有限个间断点，且 $\alpha$ 在这些间断点上连续，则 $f \in \mathcal{R}(\alpha)$。

注意，如果 $f$ 和 $\alpha$ 都在某点处间断，那么我们不一定有 $f \in \mathcal{R}(\alpha)$。

### Motivation

本定理的证明思路如下。首先考虑一种特殊情况：当 $\alpha(x)=x$ 时我们如何处理这个问题？此时 $\Delta\alpha_{i}$ 就是区间 $[x_{i-1},x_{i}]$ 的长度。

我们发现，正因为 $f$ 只有有限个间断点，因此我们可以轻松地将间断点连带着其周围的一个小邻域从 $[a,b]$ 上挖去，剩下的部分 $K$ 是一个紧致集，在其上 $f$ 是连续函数。从而，我们可以重复 [[#Theorem 6.8]] 中的论证，说明 $f$ 在 $K$ 上的误差小于 $\varepsilon$。

现在，我们要问：被挖去的部分对我们要控制的误差 $U-L$ 影响有多大？答案是：可以使其任意小。这是因为，$f$ 在间断点局部的振幅 $M_{i}-m_{i}$ 至多也就是 $2M=2 \sup\lvert f(x) \rvert$，但我们可以选取邻域的大小，使得与 $2M$ 相乘的长度 $\Delta x_{i}$ 变得任意小。结合以上两方面，$f$ 的总体误差 $U-L$ 可以被控制在 $O(\varepsilon)$ 级别。

接下来，从 $x$ 到 $\alpha$ 的推广的关键就在于，我们是否能够像控制区间长度那样，使得区间 $[x_{i-1},x_{i}]$ 的 $\alpha$-长度 $\Delta\alpha_{i}$ 任意小？答案当然也是肯定的：因为 $\alpha$ 在间断点处连续，而连续函数在局部邻域内的振幅可以是任意小的。

### Proof

给定 $\varepsilon>0$。取 $M=\sup \lvert f(x) \rvert$，$E$ 是 $f$ 的间断点构成的集合。由于 $E$ 是有限集且 $\alpha$ 在 $E$ 上连续，我们可以用有限个不交的区间 $[u_{j},v_{j}]$ 覆盖 $E$，使得 $\alpha(v_{j})-\alpha(u_{j})<\varepsilon$，并且 $E\cap (a,b)$ 中的点都位于某个 $[u_{j},v_{j}]$ 的内部。

从 $[a,b]$ 中将所有 $(u_{j},v_{j})$ 去除，剩下的集合 $K$ 是一个紧致集，因此 $f$ 在 $K$ 上一致连续。于是，存在 $\delta>0$ 使得对任意 $s,t \in K$ 有

$$
\begin{gather}
\lvert s-t \rvert <\delta \implies \lvert f(s)-f(t) \rvert <\varepsilon
\end{gather}
$$

构造划分 $P=\{ x_{0},\dots,x_{n} \}$ 如下：每个 $u_{j}$ 和 $v_{j}$ 都在 $P$ 中，$P$ 不包含 $(u_{j},v_{j})$ 中的点，并且如果 $x_{i-1}$ 不是某个 $u_{j}$，那么 $\Delta x_{i}<\delta$。

现在，我们有 $M_{i}-m_{i}\leq 2M$，并且当 $x_{i-1}$ 不是 $u_{j}$ 时，有 $M_{i}-m_{i}\leq\varepsilon$。因此，如 [[#Theorem 6.8]] 的证明中所示，我们有

$$
\begin{gather}
U(P,f,\alpha)-L(P,f,\alpha)\leq \varepsilon(\alpha(b)-\alpha(a))+2M \lvert E \rvert \varepsilon
\end{gather}
$$

其中 $\lvert E \rvert$ 表示 $E$ 的元素个数。根据 $\varepsilon$ 的任意性即证。

通过使用 Lebesgue 积分，我们可以将以上定理推广到可数个间断点，或者更精确地说，$f$ 的间断点构成的集合具有测度零。

## Theorem 6.11

假设在 $[a,b]$ 上有 $f \in \mathcal{R}(\alpha)$，$m\leq f\leq M$，$\phi$ 在 $[m,M]$ 上连续，$h=\phi \circ f$，则在 $[a,b]$ 上有 $h \in \mathcal{R}(\alpha)$。

### Proof

任取 $\varepsilon>0$。由于 $\phi$ 在 $[m,M]$ 上一致连续，存在 $0<\delta<\varepsilon$ 使得对任意 $s,t \in[m,M]$ 有

$$
\begin{gather}
\lvert s-t \rvert <\delta \implies \lvert \phi(s)-\phi(t) \rvert <\varepsilon
\end{gather}
$$

由于 $f \in \mathcal{R}(\alpha)$，存在 $[a,b]$ 的划分 $P=\{ x_{0},\dots,x_{n} \}$ 使得

$$
\begin{gather}
U(P,f,\alpha)-L(P,f,\alpha)<\delta^{2}
\end{gather}
$$

令 $M_{i},m_{i}$ 表示 $f$ 在各分段上的上下确界，$M_{i}^{*},m_{i}^{*}$ 为 $h$ 在各分段上的上下确界。将数 $1,\dots,n$ 分成两类：$i \in A$ 如果 $M_{i}-m_{i}<\delta$，$i \in B$ 如果 $M_{i}-m_{i}\geq\delta$。

对于 $i \in A$，根据 $\delta$ 的定义可知 $M_{i}^{*}-m_{i}^{*}\leq\varepsilon$。

对于 $i \in B$，由于

$$
\begin{gather}
\delta \sum_{i \in B} \Delta\alpha_{i}\leq \sum_{i \in B} (M_{i}-m_{i})\Delta\alpha_{i}<\delta^{2}
\end{gather}
$$

因此 $\sum_{i \in B}\Delta\alpha_{i}<\delta<\varepsilon$。于是

$$
\begin{align}
U(P,h,\alpha)-L(P,h,\alpha) &= \sum_{i \in A} (M_{i}^{*}-m_{i}^{*})\Delta\alpha_{i}+\sum_{i \in B} (M_{i}^{*}-m_{i}^{*})\Delta\alpha_{i} \\
&\leq \varepsilon(\alpha(b)-\alpha(a))+2K\varepsilon
\end{align}
$$

其中 $K=\sup\lvert \phi(t) \rvert$。根据 $\varepsilon$ 的任意性即证 $h \in \mathcal{R}(\alpha)$。

### Motivation

这个证明的逻辑实际上与 [[#Theorem 6.10]] 是完全相同的：$f$ 在一些点的局部振幅小（$A$ 类区间，类似于连续点附近），此时可以用 $\phi$ 的一致连续性来控制 $h$ 的振幅 $M_{i}^{*}-m_{i}^{*}$。但问题出在 $B$ 类区间（类似于间断点附近）上：此时 $f$ 的振幅可能很大，因此我们必须要控制这些区间的 $\alpha$-长度 $\Delta\alpha_{i}$。

因此，证明中的主要困难就在于如何在 $\alpha$ 不连续的情况下控制这些 $\alpha$-长度。在条件中唯一与 $\alpha$ 有关的就是 $f$ 的可积性，从而我们有不等式

$$
\begin{gather}
\sum_{i=1}^{n} (M_{i}-m_{i})\Delta\alpha_{i}<\eta
\end{gather}
$$

目前这里的 $\eta$ 可以任意选取。在 $B$ 类区间上，我们有 $M_{i}-m_{i}\geq\delta$，于是有

$$
\begin{gather}
\delta \sum_{i \in B} \Delta\alpha_{i}\leq \sum_{i \in B} (M_{i}-m_{i})\Delta\alpha_{i} <\eta
\end{gather}
$$

另一方面，在 $B$ 类点上 $h$ 的误差至多为 $2K \sum \Delta\alpha_{i}$，现在各常数的选取就很明显了：取 $\eta=\delta^{2}$ 然后令 $\delta<\varepsilon$ 即可将 $h$ 的总误差控制在 $O(\varepsilon)$ 级别。

# Properties of the Integral 积分的性质

## Theorem 6.12

(a) 如果在 $[a,b]$ 上 $f_{1},f_{2}\in \mathcal{R}(\alpha)$，则 $f_{1}+f_{2} \in \mathcal{R}(\alpha)$，且

$$
\begin{gather}
\int _{a}^{b} (f_{1}+f_{2}) \, \mathrm{d}\alpha =\int _{a}^{b} f_{1} \, \mathrm{d}\alpha+\int _{a}^{b} f_{2} \, \mathrm{d}\alpha  
\end{gather}
$$

如果 $f \in \mathcal{R}(\alpha)$ 且 $c \in \mathbb{R}$，则 $cf \in \mathcal{R}(\alpha)$，且

$$
\begin{gather}
\int _{a}^{b} cf \, \mathrm{d}\alpha=c \int _{a}^{b} f \, \mathrm{d}\alpha  
\end{gather}
$$

(b) 如果在 $[a,b]$ 上有 $f_{1},f_{2}\in \mathcal{R}(\alpha)$，且 $f_{1}\leq f_{2}$，则

$$
\begin{gather}
\int _{a}^{b} f_{1} \, \mathrm{d}\alpha \leq \int _{a}^{b} f_{2} \, \mathrm{d}\alpha 
\end{gather}
$$

(c) 如果在 $[a,b]$ 上 $f \in \mathcal{R}(\alpha)$，$a<c<b$，那么在 $[a,c]$ 和 $[c,b]$ 上都有 $f \in \mathcal{R}(\alpha)$，且

$$
\begin{gather}
\int _{a}^{c} f \, \mathrm{d}\alpha +\int _{c}^{b} f \, \mathrm{d}\alpha =\int _{a}^{b} f \, \mathrm{d}\alpha 
\end{gather}
$$

(d) 如果在 $[a,b]$ 上 $f \in \mathcal{R}(\alpha)$ 且 $\lvert f(x) \rvert\leq M$，则

$$
\begin{gather}
\left\lvert  \int _{a}^{b} f \, \mathrm{d}\alpha   \right\rvert\leq M(\alpha(b)-\alpha(a)) 
\end{gather}
$$

(e) 如果 $f \in \mathcal{R}(\alpha_{1})$ 且 $f \in \mathcal{R}(\alpha_{2})$，那么 $f \in \mathcal{R}(\alpha_{1}+\alpha_{2})$，且

$$
\begin{gather}
\int _{a}^{b} f \, \mathrm{d}(\alpha_{1}+\alpha_{2}) =\int _{a}^{b} f \, \mathrm{d}\alpha_{1}+\int _{a}^{b} f \, \mathrm{d}\alpha_{2}
\end{gather}
$$

如果 $f \in \mathcal{R}(\alpha)$ 且 $c>0$，那么 $f \in \mathcal{R}(c\alpha)$，且

$$
\begin{gather}
\int _{a}^{b} f \, \mathrm{d}(c\alpha) =c \int _{a}^{b} f \, \mathrm{d}\alpha 
\end{gather}
$$

### Proof

(a) 如果 $f=f_{1}+f_{2}$ 且 $P$ 是任意划分，则

$$
\begin{align}
L(P,f_{1},\alpha)+L_{2}(P,f_{2},\alpha) &\leq L(P,f,\alpha) \\
&\leq U(P,f,\alpha)\leq U(P,f_{1},\alpha)+U(P,f_{2},\alpha)
\end{align}
$$

设 $f_{1},f_{2}\in \mathcal{R}(\alpha)$，并给定 $\varepsilon>0$，则存在划分 $P_{j}\ (j=1,2)$ 使得

$$
\begin{gather}
U(P_{j},f_{j},\alpha)-L(P_{j},f_{j},\alpha)<\varepsilon
\end{gather}
$$

将 $P_{1},P_{2}$ 替换为它们的公共细化 $P$，以上不等式仍然成立，于是我们有

$$
\begin{gather}
U(P,f,\alpha)-L(P,f,\alpha)<2\varepsilon
\end{gather}
$$

即证 $f \in \mathcal{R}(\alpha)$。同时，对于上面的 $P$，有

$$
\begin{gather}
U(P,f_{j},\alpha)< \int f_{j} \, \mathrm{d}\alpha +\varepsilon
\end{gather}
$$

从而

$$
\begin{gather}
\int f \, \mathrm{d}\alpha \leq U(P,f,\alpha)<\int f_{1} \, \mathrm{d}\alpha +\int f_{2} \, \mathrm{d}\alpha +2\varepsilon
\end{gather}
$$

由 $\varepsilon$ 的任意性知 $\int f \, \mathrm{d}\alpha\leq \int f_{1} \, \mathrm{d}\alpha+\int f_{2} \, \mathrm{d}\alpha$。利用 $L(P,f_{j},\alpha)$，同理可证反方向的不等式。

对于 (a) 的第二部分，我们分成 $c>0$ 和 $c=-1$ 两种情况进行考虑，因为 $c=0$ 的情况是平凡的，而 $c<0$ 的部分我们可以将其写成 $(-1)(-c)$ 然后分步应用上面两种情况得到。

(1) 设 $f \in \mathcal{R}(\alpha)$ 且 $c>0$，则对任意划分 $P$，

$$
\begin{gather}
U(P,cf,\alpha)=c U(P,f,\alpha), \quad L(P,cf,\alpha)=c L(P,f,\alpha)
\end{gather}
$$

以上等式立即表明 $cf \in \mathcal{R}(\alpha)$。固定 $\varepsilon>0$，取划分 $P$ 使得

$$
\begin{gather}
U(P,f,\alpha)-L(P,f,\alpha)<\varepsilon
\end{gather}
$$

则

$$
\begin{gather}
U(P,f,\alpha) <\int f \, \mathrm{d}\alpha +\varepsilon
\end{gather}
$$

从而

$$
\begin{gather}
\int cf \, \mathrm{d}\alpha \leq U(P,cf,\alpha)< c \int f \, \mathrm{d}\alpha +c\varepsilon
\end{gather}
$$

根据 $\varepsilon$ 的任意性得 $\int cf \, \mathrm{d}\alpha\leq c\int f \, \mathrm{d}\alpha$。反方向的不等式同理。

(2) 设 $c=-1$，则对任意划分 $P$ 有

$$
\begin{gather}
U(P,-f,\alpha)=-L(P,f,\alpha), \quad L(P,-f,\alpha)=-U(P,f,\alpha)
\end{gather}
$$

取 (1) 中的划分 $P$，则

$$
\begin{gather}
U(P,-f,\alpha)-L(P,-f,\alpha)=U(P,f,\alpha)-L(P,f,\alpha)<\varepsilon
\end{gather}
$$

即 $-f \in \mathcal{R}(\alpha)$。在相同的 $P$ 下，有

$$
\begin{gather}
L(P,f,\alpha)>\int f \, \mathrm{d}\alpha -\varepsilon
\end{gather}
$$

于是，

$$
\begin{gather}
\int (-f) \, \mathrm{d}\alpha \leq U(P,-f,\alpha)<- \int f \, \mathrm{d}\alpha +\varepsilon
\end{gather}
$$

即得 $\int (-f) \, \mathrm{d}\alpha\leq -\int f \, \mathrm{d}\alpha$。反方向不等式同理。

剩下的命题的证明与 (a) 相似，因此我们略去。其中 (c) 的证明需要考虑包含点 $c$ 的任意划分，由于将一个点加入划分相当于该划分的一个细化，这样的划分总是存在。

## Theorem 6.13

如果在 $[a,b]$ 上有 $f,g \in \mathcal{R}(\alpha)$，则

1. $fg \in \mathcal{R}(\alpha)$，
2. $\lvert f \rvert\in \mathcal{R}(\alpha)$ 且 $\left\lvert  \int _{a}^{b} f \, \mathrm{d}\alpha  \right\rvert\leq \int _{a}^{b} \lvert f \rvert \, \mathrm{d}\alpha$。

### Proof

我们将主要应用 [[#Theorem 6.11]]。取 $\phi(t)=t^{2}$，则根据恒等式

$$
\begin{gather}
4fg=(f+g)^{2}-(f-g)^{2}
\end{gather}
$$

知 $fg \in \mathcal{R}(\alpha)$，因为 $(f+g)^{2}$ 和 $(f-g)^{2}$ 均可积。

同样，取 $\phi(t)=\lvert t \rvert$，则 $\lvert f \rvert\in \mathcal{R}(\alpha)$。令 $c=\pm 1$ 使得

$$
\begin{gather}
c \int f \, \mathrm{d}\alpha \geq 0
\end{gather}
$$

则我们有

$$
\begin{gather}
\left\lvert  \int f \, \mathrm{d}\alpha   \right\rvert =c \int f \, \mathrm{d}\alpha =\int cf \, \mathrm{d}\alpha \leq \int \lvert f \rvert  \, \mathrm{d}\alpha 
\end{gather}
$$

因为 $cf\leq \lvert f \rvert$ 总是成立。

## Definition 6.14 unit step 单位阶跃

单位阶跃函数 $I\colon \mathbb{R}\to \mathbb{R}$ 定义为

$$
\begin{gather}
I(x)=\begin{cases}
0, & x\leq 0 \\
1, & x>0
\end{cases}
\end{gather}
$$

## Theorem 6.15

如果 $a<s<b$，$f$ 在 $[a,b]$ 上有界，在 $s$ 处连续，并且 $\alpha(x)=I(x-s)$，则

$$
\begin{gather}
\int _{a}^{b} f \, \mathrm{d}\alpha =f(s)
\end{gather}
$$

### Proof

取划分 $P=\{ x_{0},x_{1},x_{2},x_{3} \}$，其中 $x_{0}=a$，$x_{1}=s<x_{2}$，$x_{3}=b$。则

$$
\begin{gather}
U(P,f,\alpha)=M_{2}, \quad L(P,f,\alpha)=m_{2}
\end{gather}
$$

当 $x_{2}\to s$ 时，由于 $f$ 在 $s$ 点连续，因此 $M_{2}$ 和 $m_{2}$ 均趋近于 $f(s)$。

## Theorem 6.16

假设 $c_{n}\geq 0$，$\sum c_{n}$ 收敛，$(s_{n})$ 是 $(a,b)$ 中的一列各不相同的点，且

$$
\begin{gather}
\alpha(x)=\sum_{n=1}^{\infty} c_{n} I(x-s_{n})
\end{gather}
$$

则如果 $f$ 在 $[a,b]$ 上连续，那么

$$
\begin{gather}
\int _{a}^{b} f \, \mathrm{d}\alpha =\sum_{n=1}^{\infty} c_{n} f(s_{n})
\end{gather}
$$

### Proof

通过比较准则可知对任意 $x$ 有 $\alpha(x)$ 收敛。显然 $\alpha(x)$ 单调递增，并且 $\alpha(a)=0$，$\alpha(b)=\sum c_{n}$。这就是我们在 [[4 Continuity#Remark 4.35]] 中讨论过的函数。

固定 $\varepsilon>0$，取 $N$ 使得

$$
\begin{gather}
\sum_{n=N+1}^{\infty} c_{n}<\varepsilon
\end{gather}
$$

令

$$
\begin{gather}
\alpha_{1}(x)=\sum_{n=1}^{N} c_{n}I(x-s_{n}), \quad \alpha_{2}(x)=\sum_{n=N+1}^{\infty} c_{n}I(x-s_{n})
\end{gather}
$$

则 [[#Theorem 6.15]] 表明

$$
\begin{gather}
\int f \, \mathrm{d}\alpha_{1} =\sum_{n=1}^{N} c_{n}f(s_{n})
\end{gather}
$$

另一方面，由于 $\alpha_{2}(b)-\alpha_{2}(a)<\varepsilon$，因此

$$
\begin{gather}
\left\lvert  \int f \, \mathrm{d}\alpha_{2}  \right\rvert \leq M\varepsilon
\end{gather}
$$

其中 $M=\sup \lvert f(x) \rvert$。由于 $\alpha=\alpha_{1}+\alpha_{2}$，从而根据 [[#Theorem 6.12]] 我们有

$$
\begin{gather}
\left\lvert  \int _{a}^{b} f \, \mathrm{d}\alpha -\sum_{n=1}^{N} c_{n}f(s_{n})  \right\rvert \leq M\varepsilon
\end{gather}
$$

以上不等式对任意 $N'\geq N$ 成立，这就完成了证明。

## Theorem 6.17

假设在 $[a,b]$ 上有 $\alpha' \in \mathcal{R}$，$f$ 是 $[a,b]$ 上的有界实值函数，则 $f \in \mathcal{R}(\alpha)$ 当且仅当 $f\alpha' \in \mathcal{R}$，此时

$$
\begin{gather}
\int _{a}^{b} f \, \mathrm{d}\alpha =\int _{a}^{b} f(x)\alpha'(x) \, \mathrm{d}x 
\end{gather}
$$

### Proof

给定 $\varepsilon>0$，由于 $\alpha' \in \mathcal{R}$，故存在划分 $P=\{ x_{0},\dots,x_{n} \}$ 使得

$$
\begin{gather}
U(P,\alpha')-L(P,\alpha')<\varepsilon
\end{gather}
$$

根据中值定理，存在 $t_{i}\in [x_{i-1},x_{i}]$ 使得

$$
\begin{gather}
\Delta\alpha_{i}=\alpha'(t_{i})\Delta x_{i} \quad (i=1,\dots,n)
\end{gather}
$$

此外，如果 $s_{i}\in [x_{i-1},x_{i}]$，那么

$$
\begin{gather}
\sum_{i=1}^{n} \lvert \alpha'(s_{i})-\alpha'(t_{i}) \rvert \Delta x_{i}<\varepsilon
\end{gather}
$$

取 $M=\sup \lvert f(x) \rvert$，由于

$$
\begin{gather}
\sum_{i=1}^{n} f(s_{i})\Delta\alpha_{i}=\sum_{i=1}^{n} f(s_{i})\alpha'(t_{i})\Delta x_{i}
\end{gather}
$$

因此

$$
\begin{gather}
\left\lvert  \sum_{i=1}^{n} f(s_{i})\Delta\alpha_{i}-\sum_{i=1}^{n} f(s_{i})\alpha'(s_{i})\Delta x_{i}  \right\rvert\leq M\varepsilon \tag{6.17.1}
\end{gather}
$$

特别地，我们有

$$
\begin{gather}
\sum_{i=1}^{n} f(s_{i})\Delta\alpha_{i}\leq U(P,f\alpha')+M\varepsilon
\end{gather}
$$

从而，通过对任意 $s_{i}\in [x_{i-1},x_{i}]$ 的选取方法取上确界，得到

$$
\begin{gather}
U(P,f,\alpha)\leq U(P,f\alpha')+M\varepsilon
\end{gather}
$$

通过将 $(6.17.1)$ 绝对值中的表达式取负号，我们可以通过相同的论证得到

$$
\begin{gather}
U(P,f\alpha')\leq U(P,f,\alpha)+M\varepsilon
\end{gather}
$$

即

$$
\begin{gather}
\lvert U(P,f,\alpha)-U(P,f\alpha') \rvert \leq M\varepsilon
\end{gather}
$$

以上不等式对 $P$ 的任意细化均成立，因此我们有

$$
\begin{gather}
\left\lvert  \overline{\int_{a}^{b}} f \, \mathrm{d}\alpha-\overline{\int_{a}^{b}} f(x)\alpha'(x) \, \mathrm{d}x  \right\rvert\leq M\varepsilon 
\end{gather}
$$

由 $\varepsilon$ 的任意性知两个上积分相等。同理可证两个下积分相等。这就完成了证明。

## Remark 6.18

[[#Theorem 6.16]] 和 [[#Theorem 6.17]] 鲜明地展示了 Stieltjes 积分的广泛性与灵活性。如果 $\alpha$ 是一个纯粹的阶跃函数，那么积分就退化为了一个级数；如果 $\alpha$ 有一个可积的导数，那么积分就变成了一个普通的 Riemann 积分。这使得我们可以同时研究级数与积分，这在概率分布以及物理学的相关研究中非常方便。

作为例子，考虑一个物理学问题。考虑平面上的一根单位长度的直杆，它相对于杆的一端的惯性矩定义为

$$
\begin{gather}
\int _{0}^{1} x^{2} \, \mathrm{d}m(x) 
\end{gather}
$$

其依赖于直杆的质量分布 $m(x)$，即区间 $[0,x]$ 上的总质量。如果该直杆的质量是通过一个连续的密度函数 $\rho(x)=m'(x)$ 定义的，那么惯性矩就是

$$
\begin{gather}
\int _{0}^{1} x^{2} \rho(x) \, \mathrm{d}x 
\end{gather}
$$

而如果直杆的质量集中在点 $x_{i}$ 处，则惯性矩为

$$
\begin{gather}
\sum_{i} x_{i}^{2}m_{i}
\end{gather}
$$

其中 $m_{i}$ 是 $x_{i}$ 处的点质量。

## Theorem 6.19 (变量替换)

设 $\phi\colon[A,B]\to[a,b]$ 是一个严格单调递增的连续双射，且在 $[a,b]$ 上有 $f \in \mathcal{R}(\alpha)$。在 $[A,B]$ 上定义 $\beta$ 和 $g$ 为

$$
\begin{gather}
\beta(y)=\alpha(\phi(y)), \quad g(y)=f(\phi(y))
\end{gather}
$$

则 $g \in \mathcal{R}(\beta)$，并且

$$
\begin{gather}
\int _{A}^{B} g \, \mathrm{d}\beta =\int _{a}^{b} f \, \mathrm{d}\alpha 
\end{gather}
$$

### Proof

对任意 $[a,b]$ 的划分 $P=\{ x_{0},\dots,x_{n} \}$，其唯一对应了 $[A,B]$ 上的划分 $Q=\{ y_{0},\dots,y_{n} \}$，其中 $x_{i}=\phi(y_{i})$。另一方面，所有 $[A,B]$ 的划分 $Q$ 都可以通过这种方式得到，因为 $\phi$ 是严格递增且连续的。

由于 $f$ 在 $[x_{i-1},x_{i}]$ 上的取值与 $g$ 在 $[y_{i-1},y_{i}]$ 上的取值完全相同，因此

$$
\begin{gather}
U(Q,g,\beta)=U(P,f,\alpha), \quad L(Q,g,\beta)=U(P,f,\alpha)
\end{gather}
$$

由于 $f \in \mathcal{R}(\alpha)$，参考 [[#Theorem 6.12]] 的证明即可得到 $g \in \mathcal{R}(\beta)$ 以及两个积分相等。

以上定理的名字通常指代的是如下的特例：取 $\alpha(x)=x$，则 $\beta=\phi$，从而

$$
\begin{gather}
\int _{a}^{b} f(x) \, \mathrm{d}x =\int _{A}^{B} f(\phi(y)) \, \mathrm{d}\phi(y) 
\end{gather}
$$

如果进一步还有 $\phi' \in \mathcal{R}$，那么我们就有

$$
\begin{gather}
\int _{a}^{b} f(x) \, \mathrm{d}x =\int _{A}^{B} f(\phi(y))\phi'(y) \, \mathrm{d}y
\end{gather}
$$

# Integration and Differentiation 积分与微分

本节将给出著名的微积分基本定理，它表明微分与积分在某种意义上互为逆元。

## Theorem 6.20 (微积分基本定理)

假设在 $[a,b]$ 上 $f \in \mathcal{R}$，定义

$$
\begin{gather}
F(x)=\int _{a}^{x} f(t) \, \mathrm{d}t  \quad (a\leq x\leq b)
\end{gather}
$$

则 $F$ 在 $[a,b]$ 上连续。如果 $f$ 在 $x_{0}\in[a,b]$ 处连续，那么 $F$ 在 $x_{0}$ 处可微，并且

$$
\begin{gather}
F'(x_{0})=f(x_{0})
\end{gather}
$$

### Proof

由于 $f \in \mathcal{R}$，故 $f$ 有界。取 $M=\sup\lvert f(t) \rvert$，则对任意 $a\leq x<y\leq b$ 有

$$
\begin{gather}
\lvert F(y)-F(x) \rvert =\left\lvert  \int _{x}^{y} f(t) \, \mathrm{d}t   \right\rvert \leq M(y-x)
\end{gather}
$$

这表明 $F$ 是 Lipschitz 连续的，从中可得 $F$ 一致连续。

现在假设 $f$ 在 $x_{0}$ 处连续，则对任意 $\varepsilon>0$，存在 $\delta>0$ 使得

$$
\begin{gather}
\lvert t-x_{0} \rvert <\delta \implies \lvert f(t)-f(x_{0}) \rvert <\varepsilon
\end{gather}
$$

于是，当

$$
\begin{gather}
x_{0}-\delta<s\leq x_{0}\leq t<x_{0}+\delta \quad \text{and} \quad a\leq s<t\leq b
\end{gather}
$$

时，有

$$
\begin{gather}
\left\lvert  \frac{F(t)-F(s)}{t-s}-f(x_{0})  \right\rvert =\left\lvert  \frac{1}{t-s} \int _{s}^{t}(f(u)-f(x_{0})) \, \mathrm{d}u   \right\rvert < \varepsilon
\end{gather}
$$

这就完成了证明。

## Theorem 6.21 (Newton-Leibnitz)

如果在 $[a,b]$ 上有 $f \in \mathcal{R}$，且存在可微函数 $F$ 使得 $F'=f$，则

$$
\begin{gather}
\int _{a}^{b} f(x) \, \mathrm{d}x =F(b)-F(a)
\end{gather}
$$

### Proof

给定 $\varepsilon>0$，取划分 $P=\{ x_{0},\dots,x_{n} \}$ 使得 $U(P,f)-L(P,f)<\varepsilon$，则中值定理表明存在 $t_{i}\in[x_{i-1},x_{i}]$ 使得

$$
\begin{gather}
F(x_{i})-F(x_{i-1})=f(t_{i})\Delta x_{i} \quad (i=1,\dots,n)
\end{gather}
$$

从而

$$
\begin{gather}
\sum_{i=1}^{n} f(t_{i})\Delta x_{i}=F(b)-F(a)
\end{gather}
$$

于是 [[#Theorem 6.7]](c) 给出

$$
\begin{gather}
\left\lvert  F(b)-F(a)-\int _{a}^{b} f(x) \, \mathrm{d}x   \right\rvert <\varepsilon
\end{gather}
$$

这就完成了证明。

## Theorem 6.22 (分部积分)

设 $F,G$ 是 $[a,b]$ 上的可微函数，$f=F' \in \mathcal{R}$，$g=G' \in \mathcal{R}$，则

$$
\begin{gather}
\int _{a}^{b} F(x)g(x) \, \mathrm{d}x =F(b)G(b)-F(a)G(a)-\int _{a}^{b} f(x)G(x) \, \mathrm{d}x 
\end{gather}
$$

### Proof

取 $H=FG$，则 $H'=Fg+fG \in \mathcal{R}$，应用 [[#Theorem 6.21 (Newton-Leibnitz)]] 即证。

下面我们将 Riemann 积分推广到单变量向量值函数。

## Definition 6.23

设 $f_{1},\dots,f_{k}$ 是 $[a,b]$ 上的实值函数，$\mathbf{f}=(f_{1},\dots,f_{k})$。如果 $\alpha$ 在 $[a,b]$ 上单调递增，定义 $\mathbf{f}\in \mathcal{R}(\alpha)$ 如果对任意 $j$ 有 $f_{j}\in \mathcal{R}(\alpha)$，此时我们定义

$$
\begin{gather}
\int _{a}^{b} \mathbf{f} \, \mathrm{d}\alpha =\left( \int _{a}^{b} f_{1} \, \mathrm{d}\alpha ,\dots,\int _{a}^{b} f_{k} \, \mathrm{d}\alpha  \right)
\end{gather}
$$

显然 [[#Theorem 6.12]] 的 (a)(c)(e) 部分对 $\mathbf{f}$ 的积分仍然成立，考虑每个分量上的积分即可。同样我们可得 [[#Theorem 6.17]]、[[#Theorem 6.20 (微积分基本定理)]] 以及 [[#Theorem 6.21 (Newton-Leibnitz)]]。例如下面的对于 [[#Theorem 6.21 (Newton-Leibnitz)]] 的推广：

## Theorem 6.24

如果 $\mathbf{f},\mathbf{F}\colon[a,b]\to \mathbb{R}^{k}$，$\mathbf{f}\in \mathcal{R}$，且 $\mathbf{F}'=\mathbf{f}$，则

$$
\begin{gather}
\int _{a}^{b} \mathbf{f}(t) \, \mathrm{d}t =\mathbf{F}(b)-\mathbf{F}(a)
\end{gather}
$$

唯一不同的是 [[#Theorem 6.13]](b) 的推广，它的证明有些新的特征。

## Theorem 6.25

设 $\mathbf{f}\colon[a,b]\to \mathbb{R}^{k}$，且 $\mathbf{f} \in \mathcal{R}(\alpha)$，则 $\lvert \mathbf{f} \rvert \in \mathcal{R}(\alpha)$，并且

$$
\begin{gather}
\left\lvert  \int _{a}^{b} \mathbf{f} \, \mathrm{d}\alpha   \right\rvert \leq \int _{a}^{b} \lvert \mathbf{f} \rvert  \, \mathrm{d}\alpha 
\end{gather}
$$

### Proof

设 $\mathbf{f}=(f_{1},\dots,f_{k})$，则

$$
\begin{gather}
\lvert \mathbf{f} \rvert =(f_{1}^{2}+\dots+f_{k}^{2})^{1/2}
\end{gather}
$$

根据 [[#Theorem 6.11]]，每个 $f_{j}^{2}\in \mathcal{R}(\alpha)$，从而它们的和也可积。由于 $x\mapsto x^{2}$ 是一个连续函数，[[4 Continuity#Theorem 4.20]] 表明平方根函数 $x\mapsto \sqrt{ x }$ 在任意 $[0,M]\ (M>0)$ 上连续，从而 $\lvert \mathbf{f} \rvert \in \mathcal{R}(\alpha)$。

令 $\mathbf{y}=\int \mathbf{f} \, \mathrm{d}\alpha$，则

$$
\begin{gather}
\lvert \mathbf{y} \rvert ^{2}=\sum_{j=1}^{k} y_{j}^{2}=\sum_{j=1}^{k} y_{j} \int f_{j} \, \mathrm{d}\alpha =\int \left( \sum_{j=1}^{k} y_{j}f_{j} \right) \, \mathrm{d}\alpha 
\end{gather}
$$

根据 Cauchy-Schwarz 不等式，

$$
\begin{gather}
\sum_{j=1}^{k} y_{j} f_{j}(t) \leq \lvert \mathbf{y} \rvert \lvert \mathbf{f}(t) \rvert  \quad (a\leq t\leq b)
\end{gather}
$$

即得

$$
\begin{gather}
\lvert \mathbf{y} \rvert ^{2}\leq \lvert \mathbf{y} \rvert \int \mathbf{f} \, \mathrm{d}\alpha 
\end{gather}
$$

$\mathbf{y}=\mathbf{0}$ 的情况是平凡的。其余情况根据以上不等式即证。

# Rectifiable Curves 可求长曲线

## Definition 6.26 curve 曲线，arc 弧，closed curve 闭曲线，rectifiable 可求长的

一个连续函数 $\gamma\colon[a,b]\to \mathbb{R}^{k}$ 称为 $\mathbb{R}^{k}$ 上的一条曲线。

- 如果 $\gamma$ 是单射，则称它是一条弧。
- 如果 $\gamma(a)=\gamma(b)$，则称它是一条闭曲线。

注意，我们定义曲线是一个函数，而非它的像：$\mathbb{R}^{k}$ 的一个子集。对于同一个像，它可以对应着不同的曲线。

我们将曲线 $\gamma\colon[a,b]\to \mathbb{R}^{k}$ 与 $[a,b]$ 的划分 $P=\{ x_{0},\dots,x_{n} \}$ 关联到数

$$
\begin{gather}
V(P,\gamma)=\sum_{i=1}^{n} \lvert \gamma(x_{i})-\gamma(x_{i-1}) \rvert 
\end{gather}
$$

它是折线 $\gamma(x_{0})\to \gamma(x_{1})\to \dots\to\gamma(x_{n})$ 的长度，当 $P$ 的细度趋于零时，这条折线将逐渐近似于 $\gamma$ 的像，因此将

$$
\begin{gather}
V(\gamma)=\sup_{P} V(P,\gamma)
\end{gather}
$$

定义为 $\gamma$ 的长度是合理的。在其他语境下 $V(\gamma)$ 称为函数 $\gamma$ 的总变差。

如果 $V(\gamma)<\infty$，则称 $\gamma$ 是可求长的。也称 $\gamma$ 具有有界变差。

## Theorem 6.27

如果 $\gamma'$ 在 $[a,b]$ 上连续（或称 $\gamma$ 在 $[a,b]$ 上连续可微），则 $\gamma$ 是可求长的，且

$$
\begin{gather}
V(\gamma)=\int _{a}^{b} \lvert \gamma'(t) \rvert  \, \mathrm{d}t 
\end{gather}
$$

### Proof

设 $a\leq x_{i-1}\leq x_{i}\leq b$，则

$$
\begin{gather}
\lvert \gamma(x_{i})-\gamma(x_{i-1}) \rvert =\left\lvert  \int _{x_{i-1}}^{x_{i}} \gamma'(t) \, \mathrm{d}t   \right\rvert \leq \int _{x_{i-1}}^{x_{i}} \lvert \gamma'(t) \rvert  \, \mathrm{d}t 
\end{gather}
$$

因此对任意划分 $P$ 有

$$
\begin{gather}
V(P,\gamma)\leq \int _{x_{i-1}}^{x_{i}} \lvert \gamma'(t) \rvert  \, \mathrm{d}t 
\end{gather}
$$

对 $P$ 取上确界即得

$$
\begin{gather}
V(\gamma)\leq \int _{x_{i-1}}^{x_{i}} \lvert \gamma'(t) \rvert  \, \mathrm{d}t <\infty
\end{gather}
$$

要证明反向的不等式，取 $\varepsilon>0$，由于 $\gamma'$ 一致连续，故存在 $\delta>0$ 使得

$$
\begin{gather}
\lvert s-t \rvert <\delta \implies \lvert \gamma'(s)-\gamma'(t) \rvert <\varepsilon
\end{gather}
$$

于是对于划分 $P=\{ x_{0},\dots,x_{n} \}$，满足 $\lVert P \rVert<\delta$，有

$$
\begin{gather}
\lvert \gamma'(t) \rvert \leq \lvert \gamma'(x_{i}) \rvert +\varepsilon \quad (x_{i-1}\leq t\leq x_{i})
\end{gather}
$$

因此

$$
\begin{align}
\int _{x_{i-1}}^{x_{i}} \lvert \gamma'(t) \rvert  \, \mathrm{d}t &\leq \lvert \gamma'(x_{i}) \rvert \Delta x_{i} +\varepsilon \Delta x_{i} \\
&=\left\lvert \int _{x_{i-1}}^{x_{i}} (\gamma'(t)+\gamma'(x_{i})-\gamma'(t))  \, \mathrm{d}t  \right\rvert  +\varepsilon\Delta x_{i} \\
&\leq \left\lvert  \int _{x_{i-1}}^{x_{i}} \gamma'(t) \, \mathrm{d}t   \right\rvert +\left\lvert  \int _{x_{i-1}}^{x_{i}}(\gamma'(x_{i})-\gamma'(t)) \, \mathrm{d}t   \right\rvert +\varepsilon\Delta x_{i} \\
&\leq \lvert \gamma(x_{i})-\gamma(x_{i-1}) \rvert +2\varepsilon\Delta x_{i}
\end{align}
$$

从而

$$
\begin{gather}
\int _{a}^{b} \lvert \gamma'(t) \rvert  \, \mathrm{d}t \leq V(P,\gamma)+2\varepsilon(b-a)\leq V(\gamma)+2\varepsilon(b-a)
\end{gather}
$$

这就完成了证明。