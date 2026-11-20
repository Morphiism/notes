在物理学中，我们通常需要确定一个给定的向量场 $F$ 是否是某个标量场 $f$ 的梯度。如果的确如此，那么我们就称 $F$ 是保守的，并称 $f$（有时取为 $-f$）为 $F$ 的势函数。翻译到微分形式的语言，这就是问一个 $\mathbb{R}^{3}$ 中的 $1$-形式 $\omega$ 是否是某个 $0$-形式 $f$ 的微分，也就是说，$\omega$ 是否是恰当的。

类似地，我们也想要知道一个向量场 $G$ 是否是另一个向量场 $F$ 的旋度。翻译为微分形式的语言，这就是问一个 $2$-形式 $\omega$ 是否是一个 $1$-形式的微分，于是我们就有同样的问题：$\omega$ 是否是恰当的？

本章我们来研究上面的问题在 $\mathbb{R}^{n}$ 中的推广。我们知道，如果 $\omega$ 是定义在开集 $A\subset \mathbb{R}^{n}$ 上的 $k$-形式，那么 $\omega$ 恰当的一个必要条件是 $\omega$ 是闭形式，即 $\mathrm{d}\omega=0$。这一条件一般来说不是充分的。下面我们来研究，在什么条件下，能够保证闭形式 $\omega$ 一定是恰当的。

# 39 The Poincaré Lemma

设 $A$ 是 $\mathbb{R}^{n}$ 中的开集。本节我们证明，如果 $A$ 具有一个我们称为“星状”的性质，那么 $A$ 上的任意闭形式 $\omega$ 都自动是恰当的。这一结论正是著名的 Poincaré 引理。

### Theorem 39.1 (Leibnitz)

设 $Q$ 是 $\mathbb{R}^{n}$ 中的长方体，$f\colon Q\times[a,b]\to \mathbb{R}$ 连续。将 $f$ 写成 $f(\mathbf{x},t)$，其中 $\mathbf{x}\in Q$ 且 $t \in[a,b]$，则函数

$$
\begin{gather}
F(\mathbf{x})=\int_{t=a}^{t=b} f(\mathbf{x},t)
\end{gather}
$$

在 $Q$ 上连续。此外，如果 $\partial f /\partial x_{j}$ 在 $Q\times[a,b]$ 上连续，则

$$
\begin{gather}
\frac{ \partial F }{ \partial x_{j} } (\mathbf{x})=\int_{t=a}^{t=b} \frac{ \partial f }{ \partial x_{j} } (\mathbf{x},t)
\end{gather}
$$

上式称为积分号下求导的 Leibnitz 定律。

#### Proof

**第一步** 我们证明 $F$ 是连续的。

由于 $f\colon Q\times[a,b]\to \mathbb{R}$ 连续，故 $f$ 在 $Q\times[a,b]$ 上一致连续。因此给定 $\varepsilon>0$，存在 $\delta>0$ 使得

$$
\begin{gather}
\lvert (\mathbf{x}_{1},t_{1})-(\mathbf{x}_{0},t_{0}) \rvert <\delta \implies \lvert f(\mathbf{x}_{1},t_{1})-f(\mathbf{x}_{0},t_{0}) \rvert <\varepsilon
\end{gather}
$$

于是当 $\lvert \mathbf{x}_{1}-\mathbf{x}_{0} \rvert<\delta$ 时，

$$
\begin{gather}
\lvert F(\mathbf{x}_{1})-F(\mathbf{x}_{0}) \rvert \leq \int_{t=a}^{t=b} \lvert f(\mathbf{x}_{1},t)-f(\mathbf{x}_{0},t) \rvert < \varepsilon(b-a)
\end{gather}
$$

即证 $F$ 在 $Q$ 上一致连续。

**第二步**

由于在 Leibnitz 定律中涉及的积分和导数都只和 $x_{j}$ 与 $t$ 相关，因此我们只需证明 $n=1$ 的情况，此时 $Q=[c,d]\subset \mathbb{R}$。

对 $x \in[c,d]$ 定义

$$
\begin{gather}
G(x)=\int_{t=a}^{t=b} D_{1}f(x,t)
\end{gather}
$$

我们要证 $F'(x)$ 存在且等于 $G(x)$。为此，我们应用 Fubini 定理。由于 $D_{1}f$ 在 $[c,d]\times[a,b]$ 上连续，故

$$
\begin{align}
\int_{x=c}^{x=x_{0}} G(x) &= \int_{x=c}^{x=x_{0}} \int_{t=a}^{t=b} D_{1}f(x,t) \\
&=\int_{t=a}^{t=b} \int_{x=c}^{x=x_{0}} D_{1}f(x,t) \\
&=\int_{t=a}^{t=b} (f(x_{0},t)-f(c,t)) \\
&=F(x_{0})-F(c)
\end{align}
$$

于是对任意 $x \in[c,d]$ 有

$$
\begin{gather}
\int_{c}^{x} G=F(x)-F(c)
\end{gather}
$$

重复第一步的论证，我们可知 $G$ 是连续的。应用微积分基本定理即证

$$
\begin{gather}
G(x)=F'(x)
\end{gather}
$$

### Definition 39.2 differentiable homotopy 可微同伦

设 $A\subset \mathbb{R}^{n}$ 和 $B\subset \mathbb{R}^{m}$ 是开集。令 $g,h\colon A\to B$ 为 $C^{\infty}$ 函数。我们称 $g$ 和 $h$ 是可微同伦的，如果存在 $C^{\infty}$ 函数 $H\colon A\times I\to B$ 使得

$$
\begin{gather}
H(\mathbf{x},0)=g(\mathbf{x}), \quad H(\mathbf{x},1)=h(\mathbf{x})
\end{gather}
$$

这一函数 $H$ 称为 $g$ 和 $h$ 之间的可微同伦。

对每个 $t$，$\mathbf{x}\mapsto H(\mathbf{x},t)$ 是一个从 $A$ 到 $B$ 的 $C^{\infty}$ 函数。如果我们将 $t$ 视为时间，那么 $H$ 就可以视为一种将 $g$ 变化为 $h$ 的方法。

### Theorem 39.3

设 $A\subset \mathbb{R}^{n}$ 和 $B\subset \mathbb{R}^{m}$ 是开集，$g,h\colon A\to B$ 是可微同伦的 $C^{\infty}$ 函数。则存在线性变换

$$
\begin{gather}
\mathcal{P}\colon\Omega^{k+1}(B)\to\Omega^{k}(A)
\end{gather}
$$

使得对正数阶形式 $\eta$ 有

$$
\begin{gather}
\mathrm{d}\mathcal{P}\eta+\mathcal{P}\mathrm{d}\eta=h^{*}\eta-g^{*}\eta
\end{gather}
$$

而对 $0$-形式 $f$ 有

$$
\begin{gather}
\mathcal{P}\mathrm{d}f=h^{*}f-g^{*}f
\end{gather}
$$

以上定理表明，如果 $\eta$ 是闭形式，那么 $h^{*}\eta$ 和 $g^{*}\eta$ 仅相差一个恰当形式。因为此时 $\mathrm{d}\eta=0$，故 $h^{*}\eta-g^{*}\eta=\mathrm{d}\mathcal{P}\eta$。另一方面，如果 $f$ 是闭 $0$-形式，那么 $h^{*}f-g^{*}f=0$。

注意到微分算子 $\mathrm{d}$ 将形式的阶数增加 $1$，而 $\mathcal{P}$ 将形式的阶数减少 $1$。因此在某种程度上 $\mathcal{P}$ 是一种积分算子。

#### Proof

**第一步** 我们考虑一个特例。

给定开集 $A\subset \mathbb{R}^{n}$，$U\subset \mathbb{R}^{n+1}$ 为 $A\times I$ 的一个邻域。$\alpha,\beta\colon A\to U$ 定义为

$$
\begin{gather}
\alpha(\mathbf{x})=(\mathbf{x},0),\quad \beta(\mathbf{x})=(\mathbf{x},1)
\end{gather}
$$

则 $\alpha,\beta$ 是可微同伦的。我们对 $U$ 上的 $k+1$ 形式 $\eta$ 定义一个 $A$ 上的 $k$-形式 $P\eta$，使得

$$
\begin{align}
\mathrm{d}P\eta+P\mathrm{d}\eta &= \beta^{*}\eta-\alpha^{*}\eta & \text{if}\ \operatorname{order} \eta>0 \\
P\mathrm{d}f &= \beta^{*}f-\alpha^{*}f & \text{if}\ \operatorname{order}f=0
\end{align}\tag{$\ast$}
$$

首先，令 $\mathbf{x}$ 为 $\mathbb{R}^{n}$ 中的点，$t$ 为 $\mathbb{R}$ 中的点，则 $\mathrm{d}x_{1},\dots,\mathrm{d}x_{n},\mathrm{d}t$ 是 $\mathbb{R}^{n+1}$ 上的基本 $1$-形式。如果 $g$ 是 $A\times I$ 上的连续标量函数，我们定义 $A$ 上的标量函数 $\mathcal{I}g$ 为

$$
\begin{gather}
(\mathcal{I}g)(\mathbf{x})=\int_{t=0}^{t=1} g(\mathbf{x},t)
\end{gather}
$$

然后我们定义 $P$ 如下：如果 $k\geq 0$，$\mathbb{R}^{n+1}$ 中的 $k+1$ 形式 $\eta$ 可以唯一地写成

$$
\begin{gather}
\eta=\sum_{[I]} f_{I} \,\mathrm{d}x_{I}+\sum_{[J]} g_{J}\, \mathrm{d}x_{J}\land \mathrm{d}t
\end{gather}
$$

其中 $I,J$ 分别是 $\{ 1,\dots,n \}$ 上的升序 $k+1$ 和 $k$-元组。我们定义

$$
\begin{gather}
P\eta=\sum_{[I]} P(f_{I}\,\mathrm{d}x_{I})+\sum_{[J]} P(g_{J}\,\mathrm{d}x_{J}\land \mathrm{d}t)
\end{gather}
$$

其中

$$
\begin{gather}
P(f_{I}\,\mathrm{d}x_{I})=0,\quad P(g_{J}\,\mathrm{d}x_{J}\land \mathrm{d}t)=(-1)^{k}(\mathcal{I}g_{J})\,\mathrm{d}x_{J}
\end{gather}
$$

则 $P\eta$ 是定义在 $A$ 上的 $k$-形式。

根据 $\eta$ 的表示的唯一性，以及 $\mathcal{I}$ 的线性性，我们可知 $P$ 是线性的。

要证 $P\eta$ 是 $C^{\infty}$ 的，我们只需证明 $\mathcal{I}g_{J}$ 是 $C^{\infty}$ 的。后者由 [[#Theorem 39.1 (Leibnitz)]] 给出，因为 $g_{J}$ 是 $C^{\infty}$ 的。

注意到，当 $k=0$ 时，$\eta$ 具有形式

$$
\begin{gather}
\eta=\sum_{i=1}^{n} f_{i}\,\mathrm{d}x_{i}+g\,\mathrm{d}t
\end{gather}
$$

于是

$$
\begin{gather}
P\eta=P(g\,\mathrm{d}t)=\mathcal{I}g
\end{gather}
$$

**第二步**

我们证明公式

$$
\begin{gather}
P(f_{I}\,\mathrm{d}x_{I})=0,\quad P(g_{J}\,\mathrm{d}x_{J}\land \mathrm{d}t)=(-1)^{k}(\mathcal{I}g_{J})\,\mathrm{d}x_{J}
\end{gather}
$$

对于任意 $k+1$ 和 $k$-元组 $I,J$ 成立。事实上，如果 $I,J$ 中有重复指标，那么等式是平凡的，因为两边均为零。如果 $I,J$ 中无重复指标且为升序，那么等式根据定义成立。最后，如果 $I,J$ 中无重复指标且并非升序，通过将这些指标排列，等式两边的符号变化是同步的，因此等式对任意 $I,J$ 成立。

**第三步** 我们在 $k=0$ 时验证第一步中的 $(\ast)$。

我们有

$$
\begin{align}
P\mathrm{d}f&=\sum_{j=1}^{n} P\left( \frac{ \partial f }{ \partial x_{j} } \,\mathrm{d}x_{j} \right)+P\left( \frac{ \partial f }{ \partial t } \,\mathrm{d}t \right) \\
&=\mathcal{I}\left( \frac{ \partial f }{ \partial t }  \right) \\
&=f\circ\beta-f\circ\alpha \\
&=\beta^{*}f-\alpha^{*}f
\end{align}
$$

**第四步** 我们在 $k>0$ 时验证 $(\ast)$。

注意到，由于 $\alpha(\mathbf{x})=(\mathbf{x},0)$，故

$$
\begin{align}
\alpha^{*}(\mathrm{d}x_{i}) &= \mathrm{d}\alpha_{i}=\mathrm{d}x_{i} \quad (i=1,\dots,n) \\
\alpha^{*}(\mathrm{d}t) &=\mathrm{d}\alpha_{n+1}=0
\end{align}
$$

对 $\beta^{*}$ 也有类似的等式。

由于 $\mathrm{d},P,\beta^{*},\alpha^{*}$ 都是线性的，故我们只需对 $f\,\mathrm{d}x_{I}$ 和 $g\,\mathrm{d}x_{J}\land \mathrm{d}t$ 进行验证即可。首先设 $\eta=f\,\mathrm{d}x_{I}$，则有

$$
\begin{align}
\mathrm{d}P\eta+P\mathrm{d}\eta &= \mathrm{d}(0)+P\mathrm{d}\eta \\
&=\sum_{j=1}^{n} P\left( \frac{ \partial f }{ \partial x_{j} } \,\mathrm{d}x_{j}\land \mathrm{d}x_{I} \right)+P\left( \frac{ \partial f }{ \partial t } \,\mathrm{d}t\land \mathrm{d}x_{I} \right) \\
&=(-1)^{k+1} P\left( \frac{ \partial f }{ \partial t } \,\mathrm{d}x_{I}\land \mathrm{d}t \right) \\
&=\mathcal{I}\left( \frac{ \partial f }{ \partial t } \right)\mathrm{d}x_{I} \\
&=(f\circ\beta-f\circ\alpha)\,\mathrm{d}x_{I}
\end{align}
$$

另一方面，

$$
\begin{align}
\beta^{*}(f\,\mathrm{d}x_{I})-\alpha^{*}(f\,\mathrm{d}x_{I}) &= (f\circ\beta)\beta^{*}(\mathrm{d}x_{I})-(f\circ\alpha)\alpha^{*}(\mathrm{d}x_{I}) \\
&=(f\circ\beta-f\circ\alpha)\,\mathrm{d}x_{I}
\end{align}
$$

现设 $\eta=g\,\mathrm{d}x_{J}\land \mathrm{d}t$，则

$$
\begin{align}
\mathrm{d}P\eta &= \mathrm{d}((-1)^{k}\mathcal{I}g\,\mathrm{d}x_{J}) \\
&=(-1)^{k} \sum_{j=1}^{n} D_{j}(\mathcal{I}g)\, \mathrm{d}x_{j}\land \mathrm{d}x_{J}
\end{align}\tag{$\ast\ast$}
$$

另一方面，

$$
\begin{align}
\mathrm{d}\eta=\sum_{j=1}^{n} D_{j}g\, \mathrm{d}x_{j}\land \mathrm{d}x_{J}\land \mathrm{d}t+D_{n+1}g\, \mathrm{d}t\land \mathrm{d}x_{J}\land \mathrm{d}t
\end{align}
$$

因此

$$
\begin{gather}
P\mathrm{d}\eta=(-1)^{k+1} \sum_{j=1}^{n} \mathcal{I}(D_{j}g)\, \mathrm{d}x_{j}\land \mathrm{d}x_{J}
\end{gather}\tag{$\ast\ast\ast$}
$$

比较 $(\ast\ast)$ 与 $(\ast\ast\ast)$，并应用 [[#Theorem 39.1 (Leibnitz)]] 即得

$$
\begin{gather}
\mathrm{d}P\eta+P\mathrm{d}\eta=0
\end{gather}
$$

又由于

$$
\begin{gather}
\beta^{*}(g\,\mathrm{d}x_{J}\land \mathrm{d}t)-\alpha^{*}(g\,\mathrm{d}x_{J}\land \mathrm{d}t)=0
\end{gather}
$$

因为 $\beta^{*}\mathrm{d}t=\alpha^{*}\mathrm{d}t=0$。这就验证了第一步中给出的特例。

**第五步** 我们证明一般的情况。

我们被给定 $C^{\infty}$ 函数 $g,h\colon A\to B$，以及它们之间的可微同伦 $H\colon A\times I\to B$。取 $\alpha,\beta\colon A\to A\times I$ 如第一步中所示，$P$ 为前面定义的线性变换。我们定义 $\mathcal{P}\colon\Omega^{k+1}(B)\to\Omega^{k}(A)$ 为

$$
\begin{gather}
\mathcal{P}\eta=P(H^{*}\eta)
\end{gather}
$$

由于 $H^{*}\eta$ 是定义在 $A\times I$ 邻域上的 $k+1$ 形式，因此 $P(H^{*}\eta)$ 是 $A$ 上的 $k$-形式。

由于 $H$ 是 $g,h$ 之间的可微同伦，故

$$
\begin{gather}
H\circ\alpha=g, \quad H\circ\beta=h
\end{gather}
$$

于是当 $k>0$ 时，有

$$
\begin{align}
\mathrm{d}\mathcal{P}\eta+\mathcal{P}\mathrm{d}\eta &= \mathrm{d}P(H^{*}\eta)+P(H^{*}\mathrm{d}\eta) \\
&=\mathrm{d}P(H^{*}\eta)+P\mathrm{d}(H^{*}\eta) \\
&=\beta^{*}(H^{*}\eta)-\alpha^{*}(H^{*}\eta) \\
&=h^{*}\eta-g^{*}\eta
\end{align}
$$

$k=0$ 的情况同理。这就完成了证明。

### Definition 39.4 star-convex 星状的

设开集 $A\subset \mathbb{R}^{n}$。称 $A$ 关于 $\mathbf{p}\in A$ 是星状的，如果对任意 $\mathbf{x}\in A$，连接 $\mathbf{x}$ 与 $\mathbf{p}$ 的线段包含于 $A$。

![](8-2.png)

在上图中，$A$ 关于 $\mathbf{p}$ 是星状的，但关于 $\mathbf{q}$ 不是星状的。$B$ 关于其中的每一点都是星状的，这就是说 $B$ 是一个凸集。$C$ 关于其中每一点都不是星状的。

### Theorem 39.5 (Poincaré)

设 $A$ 是 $\mathbb{R}^{n}$ 中的星状开集。如果 $\omega$ 是 $A$ 上的闭 $k$-形式，则 $\omega$ 是恰当的。

#### Proof

我们应用 [[#Theorem 39.3]]。设 $A$ 关于 $\mathbf{p}$ 是星状的。令 $h\colon A\to A$ 为恒等映射，$g\colon A\to A$ 为常值映射 $g(\mathbf{x})=\mathbf{p}$。则 $g$ 和 $h$ 是可微同伦的：函数

$$
\begin{gather}
H(\mathbf{x},t)=th(\mathbf{x})+(1-t)g(\mathbf{x})
\end{gather}
$$

将 $A\times I$ 映射入 $A$，且是 $g$ 与 $h$ 之间的可微同伦。随着 $t$ 从 $0$ 增加到 $1$，$H(\mathbf{x},t)$ 从 $g(\mathbf{x})=\mathbf{p}$ 沿着连接 $\mathbf{x}$ 与 $\mathbf{p}$ 的线段移动到 $h(\mathbf{x})=\mathbf{x}$。因此这一函数 $H$ 称为 $g$ 与 $h$ 之间的直线同伦。

令 $\mathcal{P}$ 如 [[#Theorem 39.3]] 所示。如果 $f$ 是 $A$ 上的 $0$-形式，则

$$
\begin{gather}
\mathcal{P}\mathrm{d}f=h^{*}f-g^{*}f=f\circ h-f\circ g
\end{gather}
$$

如果 $\mathrm{d}f=0$，那么我们就有

$$
\begin{gather}
0=f\circ h(\mathbf{x})-f\circ g(\mathbf{x})=f(\mathbf{x})-f(\mathbf{p})
\end{gather}
$$

因此 $f$ 在 $A$ 上为常值函数。

如果 $\omega$ 是 $k$-形式，$k>0$，我们有

$$
\begin{gather}
\mathrm{d}\mathcal{P}\omega+\mathcal{P}\mathrm{d}\omega=h^{*}\omega-g^{*}\omega
\end{gather}
$$

由于 $h$ 是恒等映射，故 $h^{*}\omega=\omega$；由于 $g$ 是常值映射，故 $g^{*}\omega=0$。则如果 $\mathrm{d}\omega=0$，那么

$$
\begin{gather}
\mathrm{d}\mathcal{P}\omega=\omega
\end{gather}
$$

这就是说 $\omega$ 是恰当形式。

### Theorem 39.6

设 $A$ 是 $\mathbb{R}^{n}$ 上的星状开集。令 $\omega$ 为 $A$ 上的闭 $k$-形式。如果 $k>1$，并且 $\eta$ 和 $\eta_{0}$ 是 $A$ 上的 $k-1$ 形式使得 $\mathrm{d}\eta=\omega=\mathrm{d}\eta_{0}$，则

$$
\begin{gather}
\eta=\eta_{0}+\mathrm{d}\theta
\end{gather}
$$

其中 $\theta$ 是 $A$ 上的 $k-2$ 形式。如果 $k=1$，且 $f$ 和 $f_{0}$ 是 $A$ 上的 $0$-形式使得 $\mathrm{d}f=\omega=\mathrm{d}f_{0}$，则存在常数 $c$ 使得 $f=f_{0}+c$。

#### Proof

由于 $\mathrm{d}(\eta-\eta_{0})=0$，即 $\eta-\eta_{0}$ 是闭形式。根据 [[#Theorem 39.5 (Poincaré)]]，它是恰当形式。同理可证 $f-f_{0}$ 是恰当的。

# 40 The De Rham Groups of Punctured Euclidean Space

我们已经证明星状开集 $A\subset \mathbb{R}^{n}$ 在任何维度上都是同调平凡的，即，$A$ 上的任何闭 $k$-形式都是恰当形式。现在我们考虑 $A$ 在某些维度上并非同调平凡的情况。最简单的非平凡情形为去心 Euclidean 空间 $\mathbb{R}^{n}\setminus \mathbf{0}$，本节我们将给出一个确定性条件以判断其上的闭形式是否是恰当形式。

对于这类问题，一种常用的方法是将其代数化：我们对开集 $A\subset \mathbb{R}^{n}$ 定义特定的向量空间 $H^{k}(A)$，称为 $A$ 的 de Rham 上同调群。$A$ 在 $k$ 维同调平凡的条件将等价于 $H^{k}(A)$ 是平凡向量空间。本节我们就来计算 $H^{k}(A)$，其中 $A=\mathbb{R}^{n}\setminus \mathbf{0}$。

### Definition 40.1 coset 陪集，quotient space 商空间

设 $V$ 是向量空间，$W$ 是 $V$ 的子空间，我们定义 $V /W$ 为所有形如

$$
\begin{gather}
\mathbf{v}+W=\{ \mathbf{v}+\mathbf{w} : \mathbf{w}\in W \}
\end{gather}
$$

的集合构成的空间，其中 $\mathbf{v}+W$ 称为 $\mathbf{v}$ 的由 $W$ 确定的一个陪集。容易证明如果 $\mathbf{v}_{1}-\mathbf{v}_{2}\in W$，那么 $\mathbf{v}_{1}+W=\mathbf{v}_{2}+W$；而如果 $\mathbf{v}_{1}-\mathbf{v}_{2}\not\in W$，那么这两个陪集不相交。因此 $V /W$ 是 $V$ 的一族不相交的子集，其并集为 $V$。这样的集族称为 $V$ 的一个划分。

我们定义 $V /W$ 上的加法和数乘为

$$
\begin{align}
(\mathbf{v}_{1}+W)+(\mathbf{v}_{2}+W) &= (\mathbf{v}_{1}+\mathbf{v}_{2})+W \\
c(\mathbf{v}+W) &= (c\mathbf{v})+W
\end{align}
$$

在如上定义的运算下，$V /W$ 构成了一个向量空间，称为 $V$ 关于 $W$ 的商空间。

### Definition 40.2

设 $V,V'$ 是向量空间，$W,W'$ 分别是 $V$ 和 $V'$ 的子空间。如果 $T\colon V\to V'$ 是线性变换，且 $T(W)\subset W'$，则存在线性变换

$$
\begin{gather}
\widetilde{T}\colon V /W\to V' /W'
\end{gather}
$$

定义为 $\widetilde{T}(\mathbf{v}+W)=T(\mathbf{v})+W'$。它称为由 $T$ 诱导的线性变换。

### Definition 40.3 de Rham group

设开集 $A\subset \mathbb{R}^{n}$，$A$ 上所有 $k$-形式构成了一个向量空间 $\Omega^{k}(A)$。$A$ 上的闭 $k$-形式 $C^{k}(A)$ 与 $A$ 上的恰当 $k$-形式 $E^{k}(A)$ 构成了 $\Omega^{k}(A)$ 的子空间。由于每个恰当形式都是闭的，$E^{k}(A)$ 是 $C^{k}(A)$ 的子空间。我们定义 $A$ 的 $k$ 维 de Rham 群为商空间

$$
\begin{gather}
H^{k}(A)=C^{k}(A) /E^{k}(A)
\end{gather}
$$

设 $\omega$ 是 $A$ 上的闭 $k$-形式，我们通常将它的陪集 $\omega+E^{k}(A)$ 记作 $\{ \omega \}$。

显然，$H^{k}(A)$ 等于平凡向量空间当且仅当 $A$ 在 $k$ 维是同调平凡的。

现在，如果 $A,B$ 分别是 $\mathbb{R}^{n}$ 和 $\mathbb{R}^{m}$ 中的开集，并且 $g\colon A\to B$ 是 $C^{\infty}$ 函数，那么 $g$ 诱导了一个线性变换 $g^{*}\colon\Omega^{k}(B)\to\Omega^{k}(A)$。由于 $g^{*}$ 与微分算子 $\mathrm{d}$ 交换，因此 $g^{*}$ 将闭形式映射到闭形式，将恰当形式映射到恰当形式，因此 $g^{*}$ 又诱导了 de Rham 群之间的线性变换

$$
\begin{gather}
\widetilde{g}^{*}\colon H^{k}(B)\to H^{k}(A)
\end{gather}
$$

为方便起见，我们仍用 $g^{*}$ 来表示线性变换 $\widetilde{g}^{*}$。

于是，$A$ 上闭形式与恰当形式就约化为了 de Rham 群 $H^{k}(A)$ 的计算。本节我们给出两个工具来计算这些空间，其一涉及我们称为“同伦等价”的概念，其二是 Mayer-Vietoris 定理的一个特例。它们都是代数拓扑中的标准工具。

### Theorem 40.4

设 $A,B$ 分别是 $\mathbb{R}^{n}$ 和 $\mathbb{R}^{m}$ 中的开集。令 $g\colon A\to B$ 和 $h\colon B\to A$ 为 $C^{\infty}$ 函数。如果 $g\circ h\colon B\to B$ 可微同伦于 $B$ 上的恒等映射 $i_{B}$，且 $h\circ g\colon A\to A$ 可微同伦于 $A$ 上的恒等映射 $i_{A}$，则 $g^{*}$ 和 $h^{*}$ 是对应 de Rham 群 $H^{k}(A)$ 与 $H^{k}(B)$ 之间的线性同构。

满足本定理条件的函数 $g,h$ 称为（可微）同伦等价。

#### Proof

设 $\eta$ 是 $A$ 上的闭 $k$-形式，则 [[#Theorem 39.3]] 表明

$$
\begin{gather}
(h\circ g)^{*}\eta-(i_{A})^{*}\eta
\end{gather}
$$

是恰当形式。因此 $g,h$ 诱导的 de Rham 群之间的映射 $g^{*},h^{*}$ 满足

$$
\begin{gather}
g^{*}(h^{*}\{ \eta \})=\{ \eta \}
\end{gather}
$$

因此 $g^{*}\circ h^{*}$ 是 $H^{k}(A)$ 上的恒等映射。同理可证 $h^{*}\circ g^{*}$ 是 $H^{k}(B)$ 上的恒等映射。这就表明 $g^{*},h^{*}$ 是 $H^{k}(A)$ 与 $H^{k}(B)$ 之间的线性同构。

### Lemma 40.5

设 $U,V$ 是 $\mathbb{R}^{n}$ 中的开集，$X=U\cup V$，且 $A=U\cap V$ 非空。则存在 $C^{\infty}$ 函数 $\phi\colon X\to[0,1]$ 使得在 $U\setminus A$ 的邻域上有 $\phi=0$，而在 $V\setminus A$ 的邻域上有 $\phi=1$。

#### Proof

![](8-3.png)

令 $\{ \phi_{i} \}$ 为 $X$ 上受 $\{ U,V \}$ 控制的一个单位分解。令 $S_{i}=\operatorname{supp}(\phi_{i})$。我们将 $\{ \phi_{i} \}$ 的指标集分成两个不相交的集合 $J,K$，使得对 $i \in J$ 有 $S_{i}\subset U$，而对 $i \in K$ 有 $S_{i}\subset V$。令

$$
\begin{gather}
\phi(\mathbf{x})=\sum_{i \in K} \phi_{i}(\mathbf{x})
\end{gather}
$$

单位分解的局部有限性保证了 $\phi$ 在 $X$ 上是 $C^{\infty}$ 函数。因为每个 $\mathbf{x}\in X$ 都有一个邻域，在其上 $\phi$ 等于有限个 $C^{\infty}$ 函数之和。

令 $\mathbf{a}\in U\setminus A$，我们证明 $\phi$ 在 $\mathbf{a}$ 的邻域上有 $\phi=0$。首先，选取 $\mathbf{a}$ 的邻域 $W$ 使得它只和有限个 $S_{i}$ 相交。从这些 $S_{i}$ 中，选出那些 $i \in K$ 的，并令 $D$ 等于这些 $S_{i}$ 的并集。则 $D$ 是闭集，且 $D$ 不包含 $\mathbf{a}$。于是 $W\setminus D$ 就是 $\mathbf{a}$ 的一个邻域，并且对 $i \in K$，函数 $\phi_{i}$ 在 $W\setminus D$ 上消失。这就表明对任意 $\mathbf{x}\in W\setminus D$ 有 $\phi(\mathbf{x})=0$。

由于

$$
\begin{gather}
1-\phi(\mathbf{x})=\sum_{i \in J} \phi_{i}(\mathbf{x})
\end{gather}
$$

根据对称性即证在 $V\setminus A$ 的邻域上有 $1-\phi=0$。

### Theorem 40.6 (Mayer-Vietoris)

设开集 $U,V\subset \mathbb{R}^{n}$ 在任意维度上同调平凡。令 $X=U\cup V$ 且 $A=U\cap V$ 非空。则 $H^{0}(X)$ 是平凡的，且对 $k\geq 0$，$H^{k+1}(X)$ 线性同构于 $H^{k}(A)$。

#### Proof

我们先引入一些记号。如果 $B,C\subset \mathbb{R}^{n}$ 是开集，$B\subset C$，且 $\eta$ 是 $C$ 上的 $k$-形式，我们用 $\eta|B$ 来表示 $\eta$ 在 $B$ 上的限制。这就是说，$\eta|B=j^{*}\eta$，其中 $j\colon B\to C$ 是包含映射。由于 $j^{*}$ 与 $\mathrm{d}$ 交换，因此一个闭形式或者恰当形式的限制仍然是闭形式或恰当形式。此外，如果 $A\subset B\subset C$，那么 $(\eta|B)|A=\eta|A$。

**第一步** 我们证明 $H^{0}(X)$ 是平凡的。

设 $f$ 是 $X$ 上的闭 $0$-形式，那么 $f|U$ 和 $f|V$ 分别是 $U,V$ 上的闭形式。由于 $U,V$ 是同调平凡的，故 $f|U,f|V$ 是恰当的，即存在标量 $c_{1},c_{2}$ 使得 $f|U=c_{1},f|V=c_{2}$。由于 $U\cap V\neq \varnothing$，故 $c_{1}=c_{2}$，即证 $f$ 是常数。

**第二步**

令 $C^{\infty}$ 函数 $\phi\colon X\to[0,1]$ 满足在 $U\setminus A$ 的邻域 $U'$ 上有 $\phi=0$，在 $V\setminus A$ 的邻域 $V'$ 上有 $\phi=1$。对 $k\geq 0$，我们定义

$$
\begin{gather}
\delta\colon\Omega^{k}(A)\to\Omega^{k+1}(X)
\end{gather}
$$

为

$$
\begin{gather}
\delta(\omega)=\begin{cases}
\mathrm{d}\phi \land\omega & \text{on}\ A \\
0 & \text{on}\ U'\cup V'
\end{cases}
\end{gather}
$$

由于在 $U'\cup V'$ 上 $\mathrm{d}\phi=0$，因此以上定义是良好的。由于 $A$ 和 $U'\cup V'$ 是开集且它们的并是 $X$，$\delta$ 在 $X$ 上是 $C^{\infty}$ 的。函数 $\delta$ 是线性的，并且它在相差一个符号下与微分算子 $\mathrm{d}$ 交换：

$$
\begin{gather}
\mathrm{d}\delta(\omega)=\left\{ \begin{matrix}
(-1)\mathrm{d}\phi \land \mathrm{d}\omega  &  \text{on}  & A \\
0  & \text{on} & U'\cup V'
\end{matrix} \right\} =-\delta(\mathrm{d}\omega)
\end{gather}
$$

因此 $\delta$ 将闭形式映射到闭形式，将恰当形式映射到恰当形式。因此它诱导了线性变换

$$
\begin{gather}
\widetilde{\delta}\colon H^{k}(A)\to H^{k+1}(X)
\end{gather}
$$

我们来证明 $\widetilde{\delta}$ 是一个线性同构。

**第三步** 我们证明 $\widetilde{\delta}$ 是单射。为此，我们只需证明如果 $\omega$ 是 $A$ 中的闭 $k$-形式，使得 $\delta(\omega)$ 是恰当的，那么 $\omega$ 本身是恰当的。

假设有 $X$ 中的 $k$-形式 $\theta$ 使得 $\delta(\omega)=\mathrm{d}\theta$。我们定义 $U$ 上的 $k$-形式 $\omega_{1}$ 和 $V$ 上的 $k$-形式 $\omega_{2}$ 为

$$
\begin{gather}
\omega_{1}=\begin{cases}
\phi\omega & \text{on}\ A \\
0 & \text{on}\ U'
\end{cases} \quad \text{and}\quad \omega_{2}=\begin{cases}
(1-\phi)\omega & \text{on}\ A \\
0 & \text{on}\ V'
\end{cases}
\end{gather}
$$

则 $\omega_{1},\omega_{2}$ 是良定的 $C^{\infty}$ 形式。

![](8-4.png)

由于 $\mathrm{d}\omega=0$，我们有

$$
\begin{gather}
\mathrm{d}\omega_{1}=\begin{cases}
\mathrm{d}\phi \land\omega & \text{on}\ A \\
0 & \text{on}\ U'
\end{cases}
\end{gather}
$$

故

$$
\begin{gather}
\mathrm{d}\omega_{1}=\delta(\omega)|U=\mathrm{d}\theta|U
\end{gather}
$$

因此 $\omega_{1}-\theta|U$ 是 $U$ 上的闭 $k$-形式。同理可证

$$
\begin{gather}
\mathrm{d}\omega_{2}=-\mathrm{d}\theta|V
\end{gather}
$$

因此 $\omega_{2}+\theta|V$ 是 $V$ 上的闭 $k$-形式。

$U$ 和 $V$ 在任意维度上同调平凡。如果 $k>0$，这表明存在 $k-1$ 形式 $\eta_{1},\eta_{2}$，分别定义在 $U$ 和 $V$ 上，使得

$$
\begin{gather}
\omega_{1}-\theta|U=\mathrm{d}\eta_{1}, \quad \omega_{2}+\theta|V=\mathrm{d}\eta_{2}
\end{gather}
$$

将它们限制在 $A$ 上并相加，可得

$$
\begin{gather}
\omega_{1}|A+\omega_{2}|A=\mathrm{d}\eta_{1}|A+\mathrm{d}\eta_{2}|A
\end{gather}
$$

从而

$$
\begin{gather}
\omega=\phi\omega+(1-\phi)\omega=\mathrm{d}(\eta_{1}|A+\eta_{2}|A)
\end{gather}
$$

即 $\omega$ 在 $A$ 上是恰当形式。

如果 $k=0$，那么有标量 $c_{1},c_{2}$ 使得

$$
\begin{gather}
\omega_{1}-\theta|U=c_{1}, \quad \omega_{2}+\theta|V=c_{2}
\end{gather}
$$

则

$$
\begin{gather}
\omega=\omega_{1}|A+\omega_{2}|A=c_{1}+c_{2}
\end{gather}
$$

为常值函数。

**第四步** 我们证明 $\widetilde{\delta}$ 是满射。为此，我们只需证明如果 $\eta$ 是 $X$ 上的闭 $k+1$ 形式，那么存在 $A$ 上的闭 $k$-形式 $\omega$ 使得 $\eta-\delta(\omega)$ 是恰当的。

给定 $\eta$，形式 $\eta|U$ 和 $\eta|V$ 是闭的，因此存在 $U$ 和 $V$ 上的 $k$-形式 $\theta_{1}$ 和 $\theta_{2}$ 使得

$$
\begin{gather}
\mathrm{d}\theta_{1}=\eta|U, \quad \mathrm{d}\theta_{2}=\eta|V
\end{gather}
$$

定义 $A$ 上的 $k$-形式 $\omega$ 为

$$
\begin{gather}
\omega=\theta_{1}|A-\theta_{2}|A
\end{gather}
$$

则 $\omega$ 是闭的，因为 $\mathrm{d}\omega=\eta|A-\eta|A=0$。我们定义 $X$ 上的 $k$-形式 $\theta$ 为

$$
\begin{gather}
\theta=\begin{cases}
(1-\phi)\theta_{1}+\phi\theta_{2} & \text{on}\ A \\
\theta_{1} & \text{on}\ U' \\
\theta_{2} & \text{on}\ V'
\end{cases}
\end{gather}
$$

则 $\theta$ 是良定的 $C^{\infty}$ 形式。

![](8-5.png)

我们来证明

$$
\begin{gather}
\eta-\delta(\omega)=\mathrm{d}\theta
\end{gather}
$$

为此，我们分别在 $A,U',V'$ 上计算 $\mathrm{d}\theta$。首先，在 $A$ 上有

$$
\begin{align}
\mathrm{d}\theta|A &= (-\mathrm{d}\phi \land\theta_{1}|A+(1-\phi)\mathrm{d}(\theta_{1}|A))+(\mathrm{d}\phi \land\theta_{2}|A+\phi \mathrm{d}(\theta_{2}|A)) \\
&=(1-\phi)\eta|A+\phi \eta|A+\mathrm{d}\phi \land(\theta_{2}|A-\theta_{1}|A) \\
&=\eta|A-\mathrm{d}\phi \land\omega \\
&=\eta|A-\delta(\omega)|A
\end{align}
$$

在 $U'$ 和 $V'$ 上，我们分别有

$$
\begin{gather}
\mathrm{d}\theta|U'=\mathrm{d}\theta_{1}|U'=\eta|U'=\eta|U'-\delta(\omega)|U' \\
\mathrm{d}\theta|V'=\mathrm{d}\theta_{2}|V'=\eta|V'=\eta|V'-\delta(\omega)|V'
\end{gather}
$$

因为 $\delta(\omega)|(U'\cup V')=0$。从而

$$
\begin{gather}
\mathrm{d}\theta=\eta-\delta(\omega)
\end{gather}
$$

这就完成了证明。

### Theorem 40.7

令 $n\geq 1$，则

$$
\begin{gather}
\dim H^{k}(\mathbb{R}^{n}\setminus \mathbf{0})=\begin{cases}
0, & k\neq n-1 \\
1, & k=n-1
\end{cases}
\end{gather}
$$

#### Proof

**第一步** 我们证明 $n=1$ 的情况。

令 $A=\mathbb{R}\setminus 0$，将 $A$ 写成 $A=A_{0}\cup A_{1}$，其中 $A_{0}$ 是负实数，$A_{1}$ 是正实数。如果 $\omega$ 是 $A$ 上的闭 $k$-形式，$k>0$，则 $\omega|A_{0}$ 和 $\omega|A_{1}$ 是闭形式。由于 $A_{0},A_{1}$ 是星状的，故存在 $k-1$ 形式 $\eta_{0}$ 和 $\eta_{1}$，分别定义在 $A_{0}$ 和 $A_{1}$ 上，使得 $\omega|A_{0}=\mathrm{d}\eta_{0}$ 且 $\omega|A_{1}=\mathrm{d}\eta_{1}$。定义

$$
\begin{gather}
\eta=\begin{cases}
\eta_{0} & \text{on}\ A_{0} \\
\eta_{1} & \text{on}\ A_{1}
\end{cases}
\end{gather}
$$

则 $\eta$ 是良定的 $C^{\infty}$ 形式，且 $\mathrm{d}\eta=\omega$。

现在令 $f_{0}$ 为 $A$ 上的 $0$-形式，定义为对 $x \in A_{0}$ 有 $f_{0}(x)=0$，对 $x \in A_{1}$ 有 $f_{0}(x)=1$。则 $f_{0}$ 是闭形式，但不是恰当形式。我们来证明 $\{ f_{0} \}$ 构成了 $H^{0}(A)$ 的一个基。

给定 $A$ 上的闭 $0$-形式 $f$，则 $f|A_{0}$ 和 $f|A_{1}$ 是恰当的，故存在标量 $c_{0},c_{1}$ 使得 $f|A_{0}=c_{0},f|A_{1}=c_{1}$，于是

$$
\begin{gather}
f(x)=(c_{1}-c_{0})f_{0}(x)+c_{0}
\end{gather}
$$

这表明 $\{ f \}=(c_{1}-c_{0})\{ f_{0} \}$。

**第二步**

设 $B\subset \mathbb{R}^{n}$ 是开集，则 $B\times \mathbb{R}$ 在 $\mathbb{R}^{n+1}$ 中开。我们来证明对任意 $k$ 有

$$
\begin{gather}
\dim H^{k}(B)=\dim H^{k}(B\times \mathbb{R})
\end{gather}
$$

我们应用同伦等价定理 [[#Theorem 40.4]]。定义 $g\colon B\to B\times \mathbb{R}$ 为 $g(\mathbf{x})=(\mathbf{x},0)$，定义 $h\colon B\times \mathbb{R}\to B$ 为 $h(\mathbf{x},s)=\mathbf{x}$。则 $h\circ g$ 等于 $B$ 上的恒等映射，而 $g\circ h$ 可微同伦于 $B\times \mathbb{R}$ 上的恒等映射：使用直线同伦

$$
\begin{gather}
H((\mathbf{x},s),t)=t(\mathbf{x},s)+(1-t)(\mathbf{x},0)=(\mathbf{x},st)
\end{gather}
$$

即可。

**第三步** 令 $n\geq 1$，我们假设定理对 $n$ 成立，要证定理对 $n+1$ 成立。

定义 $\mathbb{R}^{n+1}$ 中的开集 $U,V$ 为

$$
\begin{gather}
U=\mathbb{R}^{n+1} \setminus \{ (0,\dots,0,t): t\geq 0 \} \\
V=\mathbb{R}^{n+1}\setminus \{ (0,\dots,0,t): t\leq 0 \}
\end{gather}
$$

则 $A=U\cap V$ 非空，并且它包含了 $\mathbb{R}^{n+1}=\mathbb{R}^{n}\times \mathbb{R}$ 中所有不在直线 $\mathbf{0}\times \mathbb{R}$ 上的点。即

$$
\begin{gather}
A=(\mathbb{R}^{n}\setminus \mathbf{0})\times \mathbb{R}
\end{gather}
$$

![](8-6.png)

如果我们设 $X=U\cup V$，则

$$
\begin{gather}
X=\mathbb{R}^{n+1}\setminus \mathbf{0}
\end{gather}
$$

集合 $U$ 关于点 $\mathbf{p}=(0,\dots,0,-1)$ 是星状的，$V$ 关于点 $\mathbf{q}=(0,\dots,0,1)$ 是星状的。因此 [[#Theorem 40.6 (Mayer-Vietoris)]] 表明 $H^{0}(X)$ 是平凡的，并且

$$
\begin{gather}
\dim H^{k+1}(X)=\dim H^{k}(A) \quad (k\geq 0)
\end{gather}
$$

现在，第二步表明 $\dim H^{k}(A)=\dim H^{k}(\mathbb{R}^{n}\setminus \mathbf{0})$，而归纳假设表明后者等于 $0$ 如果 $k\neq n-1$，等于 $1$ 如果 $k=n-1$。这就完成了证明。

我们将以上定理翻译为微分形式的语言。

### Theorem 40.8

设 $A=\mathbb{R}^{n}\setminus \mathbf{0}$，$n\geq 1$。

(a) 如果 $k\neq n-1$，那么 $A$ 上的任意闭 $k$-形式都是恰当的。
(b) 存在 $A$ 上的闭 $n-1$ 形式 $\eta_{0}$ 不是恰当的。如果 $\eta$ 是 $A$ 上的任意闭 $n-1$ 形式，那么存在唯一的标量 $c$ 使得 $\eta-c\eta_{0}$ 是恰当的。

这一定理保证了 $\mathbb{R}^{n}\setminus \mathbf{0}$ 上存在不是恰当形式的闭 $n-1$ 形式，但它没有告诉我们如何构造这一形式。为此，我们考虑如下的 $n-1$ 形式

$$
\begin{gather}
\eta_{0}=\sum_{i=1}^{n} (-1)^{i-1} f_{i}\,\mathrm{d}x_{1}\land\dots \land \widehat{\mathrm{d}x}_{i}\land\dots \land \mathrm{d}x_{n}
\end{gather}
$$

其中 $f_{i}(\mathbf{x})=x_{i} /\lVert \mathbf{x} \rVert^{n}$。直接计算表明 $\eta_{0}$ 是闭形式。为证它不是恰当形式，我们考虑单位球面 $S^{n-1}$ 上的积分 $\int_{S^{n-1}} \eta_{0}$，其中 $S^{n-1}$ 的定向取外侧。由于 $S^{n-1}$ 上的点 $\mathbf{x}$ 处的外法向量为 $\mathbf{x} /\lVert \mathbf{x} \rVert$，因此

$$
\begin{gather}
\int_{S^{n-1}} \eta_{0}=\int_{S^{n-1}} \langle (f_{1},\dots,f_{n}),\mathbf{x} /\lVert \mathbf{x} \rVert  \rangle \,\mathrm{d}V=v(S^{n-1})\neq 0
\end{gather}
$$

从而由 Stokes 定理知 $\eta_{0}$ 不可能是恰当的，否则

$$
\begin{gather}
\int_{S^{n-1}}\eta_{0}=\int_{S^{n-1}} \mathrm{d}\theta=0
\end{gather}
$$

因为 $\partial S^{n-1}=\varnothing$。利用这一结果，我们给出一个判断 $\mathbb{R}^{n}\setminus \mathbf{0}$ 上的闭 $n-1$ 形式是否是恰当形式的条件。

### Theorem 40.9

令 $A=\mathbb{R}^{n}\setminus \mathbf{0}$，$n\geq 1$。如果 $\eta$ 是 $A$ 上的闭 $n-1$ 形式，那么 $\eta$ 是恰当的当且仅当

$$
\begin{gather}
\int_{S^{n-1}} \eta=0
\end{gather}
$$

#### Proof

如果 $\eta$ 是恰当的，那么由 Stokes 定理可知 $\eta$ 在 $S^{n-1}$ 上的积分为零。反之，假设给定的积分为零。令 $\eta_{0}$ 为前文定义的 $n-1$ 形式，则 [[#Theorem 40.8]] 表明存在唯一的标量 $c$ 使得 $\eta-c\eta_{0}$ 是恰当的，于是

$$
\begin{gather}
\int_{S^{n-1}} (\eta-c\eta_{0})=-c\int_{S^{n-1}} \eta_{0}=0
\end{gather}
$$

由于 $\int_{S^{n-1}}\eta_{0}\neq 0$，故 $c=0$，即证 $\eta$ 是恰当的。