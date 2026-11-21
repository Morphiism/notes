上一章我们展示了 $\mathbb{R}^{n}$ 上的 $k$-形式如何推广了 $\mathbb{R}^{3}$ 上的标量场与向量场，以及微分算子 $\mathrm{d}$ 如何推广了运算 $\operatorname{grad},\operatorname{div}$ 与 $\operatorname{curl}$。本章我们来定义 $k$-流形上的 $k$-形式的积分，这一概念推广了 $\mathbb{R}^{3}$ 中的“第二类”曲线、曲面积分。

# 33 Integrating Forms over Parametrized-Manifolds

在第五章中，我们定义了一个标量函数 $f$ 在流形上关于体积的积分。本章我们按照一个类似的过程来定义 $k$-流形上 $k$-形式的积分，以参数化流形上的积分入手。

### Definition 33.1

设开集 $A\subset \mathbb{R}^{k}$，$\eta$ 是 $A$ 上的 $k$-形式，则 $\eta$ 可以唯一地写成

$$
\begin{gather}
\eta=h\, \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}
\end{gather}
$$

我们定义 $\eta$ 在 $A$ 上的积分为

$$
\begin{gather}
\int_{A} \eta=\int_{A} h
\end{gather}
$$

如果右侧的积分存在。

以上定义看起来是坐标相关的：要定义 $\int_{A}\eta$，我们首先将 $\eta$ 写成基本 $1$-形式 $\mathrm{d}x_{i}$ 的相关表达式，后者依赖于 $\mathbb{R}^{k}$ 上的标准基 $\mathbf{e}_{1},\dots,\mathbf{e}_{n}$。然而，我们的确可以给出一个坐标无关的定义。特别地，如果 $\mathbf{a}_{1},\dots,\mathbf{a}_{k}$ 是 $\mathbb{R}^{k}$ 的任意右手标准正交标架，那么我们有

$$
\begin{gather}
\int_{A} \eta=\int_{\mathbf{x}\in A} \eta(\mathbf{x})((\mathbf{x};\mathbf{a}_{1}),\dots,(\mathbf{x};\mathbf{a}_{k}))
\end{gather}
$$

因为如果我们写 $\eta=h\,\mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}$，那么

$$
\begin{gather}
\eta(\mathbf{x})((\mathbf{x};\mathbf{a}_{1}),\dots,(\mathbf{x};\mathbf{a}_{k}))=h(\mathbf{x}) \det[\mathbf{a}_{1}\cdots \mathbf{a}_{k}]=h(\mathbf{x})
\end{gather}
$$

因此 $\eta$ 的积分不依赖于 $\mathbb{R}^{k}$ 上基的选取，但它的确依赖于 $\mathbb{R}^{k}$ 上的定向。

### Definition 33.2

设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{\infty}$ 函数。集合 $Y=\alpha(A)$ 以及函数 $\alpha$ 共同构成了一个参数化流形 $Y_{\alpha}$。如果 $\omega$ 是定义在包含 $Y$ 的开集上的 $k$-形式，我们定义 $\omega$ 在 $Y_{\alpha}$ 上的积分为

$$
\begin{gather}
\int_{Y_{\alpha}} \omega=\int_{A} \alpha^{*}\omega
\end{gather}
$$

如果右侧的积分存在。由于 $\int_{A}$ 和 $\alpha^{*}$ 都是线性的，故以上积分也是线性的。

### Theorem 33.3

设 $g\colon A\to B$ 是 $\mathbb{R}^{k}$ 上的开集之间的微分同胚，假设 $\det Dg$ 在 $A$ 上不改变符号。设 $\beta\colon B\to \mathbb{R}^{n}$ 是 $C^{\infty}$ 函数，$Y=\beta(B)$。令 $\alpha=\beta \circ g$，则 $\alpha\colon A\to \mathbb{R}^{n}$ 且 $Y=\alpha(A)$。如果 $\omega$ 是定义在包含 $Y$ 的开集上的 $k$-形式，则 $\omega$ 在 $Y_{\beta}$ 上可积当且仅当 $\omega$ 在 $Y_{\alpha}$ 上可积，此时

$$
\begin{gather}
\int_{Y_{\alpha}} \omega=\operatorname{sgn}(\det Dg)\int_{Y_{\beta}} \omega
\end{gather}
$$

以上定理表明，这一积分在重参数化下不变，最多相差一个符号。

#### Proof

设 $\mathbf{x}$ 是 $A$ 的任意点，$\mathbf{y}$ 是 $B$ 的任意点。我们要证

$$
\begin{gather}
\int_{A} \alpha^{*}\omega=\varepsilon\int_{B} \beta^{*}\omega
\end{gather}
$$

其中 $\varepsilon=\operatorname{sgn}(\det Dg)$。如果我们令 $\eta=\beta^{*}\omega$，则以上等式等价于

$$
\begin{gather}
\int_{A} g^{*}\eta=\varepsilon\int_{B} \eta
\end{gather}
$$

我们将 $\eta$ 写成 $\eta=f\,\mathrm{d}y_{1}\land\dots \land \mathrm{d}y_{k}$，则

$$
\begin{align}
g^{*}\eta &= g^{*}(f\,\mathrm{d}y_{1}\land\dots \land \mathrm{d}y_{k}) \\
&=(f\circ g) g^{*}(\mathrm{d}y_{1}\land\dots \land \mathrm{d}y_{k}) \\
&=(f\circ g) \det Dg \, \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}
\end{align}
$$

于是要证的等式就是

$$
\begin{gather}
\int_{A} (f\circ g)\det Dg=\varepsilon \int_{B} f
\end{gather}
$$

上式由变量替换定理立即给出，因为 $\det Dg=\varepsilon\lvert \det Dg \rvert$。

我们指出：如果 $A$ 是连通集，那么 $\det Dg$ 在 $A$ 上不改变符号的假设是自动满足的。这是因为 $\det Dg$ 是连续函数，从而其值域也是连通的。因而，如果 $\det Dg$ 改变符号，那么必然有 $\mathbf{x}\in A$ 使得 $\det Dg(\mathbf{x})=0$，这与 $g$ 是微分同胚矛盾。

### Theorem 33.4

设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{\infty}$ 函数，$Y=\alpha(A)$。设 $\mathbf{x}$ 为 $A$ 的任意点，$\mathbf{z}$ 为 $\mathbb{R}^{n}$ 的任意点，如果

$$
\begin{gather}
\omega=f\, \mathrm{d}z_{I}
\end{gather}
$$

是定义在包含 $Y$ 的开集上的 $k$-形式，则

$$
\begin{gather}
\int_{Y_{\alpha}} \omega=\int_{A} (f\circ\alpha) \det \frac{ \partial \alpha_{I} }{ \partial \mathbf{x} } 
\end{gather}
$$

#### Proof

根据 [[6 Differential Forms#Theorem 32.3]]，我们有

$$
\begin{gather}
\alpha^{*}\omega=(f\circ\alpha)(\det \partial\alpha_{I} /\partial \mathbf{x}) \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}
\end{gather}
$$

根据定义即证。

### Remark 33.5

现在我们可以为积分中常用的 $\mathrm{d}x$ 符号给出一个解释。设 $\eta=f\,\mathrm{d}x$ 是一个 $1$-形式，定义在 $A=(a,b)$ 上，则

$$
\begin{gather}
\int_{A} \eta=\int_{A} f
\end{gather}
$$

这就是说，

$$
\begin{gather}
\int_{A} f\, \mathrm{d}x=\int_{a}^{b} f
\end{gather}
$$

其中，等式左侧是一个微分形式的积分，而右侧是一个函数的积分。形式 $\mathrm{d}x$ 提供了一种将形式的积分转化为函数的积分的方法。

同样，我们可以给出第二类曲线积分的一个公式。给定一个定义在开集 $A$ 上的 $1$-形式 $P\,\mathrm{d}x+Q\,\mathrm{d}y+R\,\mathrm{d}z$，以及参数化曲线 $\gamma\colon(a,b)\to A$，我们有

$$
\begin{multline}
\int_{C_{\gamma}} P\,\mathrm{d}x+Q\,\mathrm{d}y+R\,\mathrm{d}z \\
=\int_{(a,b)} \left( P(\gamma(t)) \frac{\mathrm{d}\gamma_{1}}{\mathrm{d}t}+Q(\gamma(t)) \frac{\mathrm{d}\gamma_{2}}{\mathrm{d}t}+R(\gamma(t)) \frac{\mathrm{d}\gamma_{3}}{\mathrm{d}t} \right) \mathrm{d}t
\end{multline}
$$

其中 $C=\gamma((a,b))$。这正是曲线积分 $\int_{C}P\,\mathrm{d}x+Q\,\mathrm{d}y+R\,\mathrm{d}z$ 的计算公式。

然而，要解释二重积分中常用的 $\mathrm{d}x\,\mathrm{d}y$ 符号更为困难。如果 $f$ 是 $A$ 上的有界连续函数，我们通常将 $f$ 在 $A$ 上的积分写成

$$
\begin{gather}
\iint_{A} f(x,y)\, \mathrm{d}x\,\mathrm{d}y
\end{gather}
$$

此处的 $\mathrm{d}x\,\mathrm{d}y$ 没有独立的含义。一种解释是，这一符号表示了累次积分的计算顺序：如果 $A$ 是长方体 $[a,b]\times[c,d]$ 的内部，则根据 Fubini 定理，我们有

$$
\begin{gather}
\int_{c}^{d} \left( \int_{a}^{b} f(x,y)\, \mathrm{d}x \right) \mathrm{d}y=\int_{A} f
\end{gather}
$$

另一种解释是，这一符号表示了 $2$-形式的积分

$$
\begin{gather}
\int_{A} f\, \mathrm{d}x\land \mathrm{d}y=\int_{A}f
\end{gather}
$$

但当我们交换 $x$ 与 $y$ 的位置时出现了问题：如果采用第一种解释，我们仍然有

$$
\begin{gather}
\int_{a}^{b}\left( \int_{c}^{d} f(x,y)\,\mathrm{d}y \right)\mathrm{d}x=\int_{A} f
\end{gather}
$$

但如果按第二种解释，我们却有

$$
\begin{gather}
\int_{A} f\, \mathrm{d}y\land \mathrm{d}x=-\int_{A} f
\end{gather}
$$

由于这样的歧义，我们将不使用 $\mathrm{d}x\,\mathrm{d}y$ 符号。

在第五章中，我们还引入了 $\mathrm{d}V$ 符号以表示关于体积的积分。这一符号是无歧义的：设开集 $A\subset \mathbb{R}^{k}$，则 $A$ 可以被视为一个由恒等映射 $\alpha\colon A\to A$ 参数化的参数化流形 $A_{\alpha}$，则

$$
\begin{gather}
\int_{A_{\alpha}} f\,\mathrm{d}V=\int_{A} (f\circ\alpha) V(D\alpha)=\int_{A} f
\end{gather}
$$

当然，这里的 $\mathrm{d}V$ 与微分算子 $\mathrm{d}$ 没有任何联系。

# 34 Orientable Manifolds

我们希望按照定义流形 $M$ 上标量函数的积分的过程，定义 $M$ 上微分形式 $\omega$ 的积分。首先，我们考虑 $\omega$ 的支撑集可以被单个坐标卡 $\alpha\colon U\to V$ 覆盖的情况，此时我们定义

$$
\begin{gather}
\int_{M} \omega=\int_{\operatorname{Int}U}\alpha^{*}\omega
\end{gather}
$$

但此时有一个问题：右侧的积分在重参数化下可能会相差一个符号。因此，要使得 $\int_{M}\omega$ 是良定的，我们就需要在 $M$ 上添加一个额外的条件以确定拉回 $\alpha^{*}\omega$ 的符号。这一条件称为流形的定向，它是本节的主要研究对象。

### Definition 34.1 orientation-preserving 保持定向的，orientation-reversing 反转定向的

设 $g\colon A\to B$ 是 $\mathbb{R}^{k}$ 中的开集之间的微分同胚。我们说 $g$ 是保持定向的，如果在 $A$ 上 $\det Dg>0$；说 $g$ 是反转定向的，如果在 $A$ 上 $\det Dg<0$。

### Definition 34.2 orientable 可定向的

设 $M$ 是 $\mathbb{R}^{n}$ 上的 $k$-流形。对 $i=0,1$ 给定 $M$ 上的坐标卡 $\alpha_{i}\colon U_{i}\to V_{i}$，我们说它们重叠，如果 $V_{0}\cap V_{1}\neq \varnothing$。我们说它们正向重叠，如果转移函数 $\alpha_{1}^{-1}\circ\alpha_{0}$ 是保持定向的。如果 $M$ 可以被一族两两正向重叠（如果有重叠）的坐标卡覆盖，我们称 $M$ 是可定向的。否则，我们就称 $M$ 是不可定向的。

### Definition 34.3 orientation 定向，oriented manifold 定向流形

设 $M$ 是 $\mathbb{R}^{n}$ 上的可定向 $k$-流形。给定覆盖 $M$ 的一族两两正向重叠的坐标卡，我们将 $M$ 上所有与这族坐标卡正向重叠的坐标卡加入这个集合，则在这个扩展的集合中的坐标卡是两两正向重叠的。这一扩展的集合称为 $M$ 的一个定向。一个流形 $M$ 连同其上的一个定向构成了一个定向流形。

以上定义对 $0$-流形，也就是 $\mathbb{R}^{n}$ 上的离散点集不适用。在后续我们将讨论什么是 $0$-流形的定向。

设 $V$ 是 $k$ 维向量空间，则 $V$ 自身也是一个 $k$-流形。此时在 $V$ 上有两种定向的概念：其一是 $V$ 上的一族对应于 $\mathbb{R}^{k}$ 中右手（左手）系的标架；其二是 $V$ 上的一族两两正向重叠的坐标卡。我们来证明这两个概念是一致的。

给定 $V$ 上的第一种意义下的定向，我们构造 $V$ 的第二种意义下的定向如下：对每个属于给定定向的标架 $(\mathbf{v}_{1},\dots,\mathbf{v}_{k})$，定义为 $\alpha(\mathbf{e}_{i})=\mathbf{v}_{i}$ 的线性同构 $\alpha\colon \mathbb{R}^{k}\to V$ 是 $V$ 上的一个坐标卡。容易证明任何两个这样的坐标卡正向重叠，并且所有这样的坐标卡构成了 $V$ 上第二种意义下的定向。

## Oriented Manifolds in $\mathbb{R}^{n}$ of Dimensions 1 and $n-1$ and $n$

在特定的维数中，即 $k=1,n-1$ 和 $n$，流形的定向有一个简单的几何表示。首先，在 $k=1$ 时，我们可以将一个定向描述为一个切向量场。

### Definition 34.4

设 $M$ 是 $\mathbb{R}^{n}$ 中的定向 $1$-流形。我们定义 $M$ 上的单位切向量场 $T$ 如下：给定 $\mathbf{p}\in M$，选取 $\mathbf{p}$ 处的坐标卡 $\alpha\colon U\to V$ 属于给定定向，定义

$$
\begin{gather}
T(\mathbf{p})=(\mathbf{p};D\alpha(t_{0}) /\lVert D\alpha(t_{0}) \rVert )
\end{gather}
$$

其中 $t_{0}=\alpha^{-1}(\mathbf{p})$。我们称 $T$ 为对应于 $M$ 上定向的单位切向量场。

注意到 $(\mathbf{p};D\alpha(t_{0}))$ 是曲线 $\alpha$ 在 $t_{0}$ 时的速度向量，因此 $T(\mathbf{p})$ 也可以称为是一个单位速度向量。

我们来证明 $T$ 是良定的，与特定坐标卡的选取无关。设 $\beta$ 是 $\mathbf{p}$ 处的另一个坐标卡，与 $\alpha$ 正向重叠。令 $\mathbf{p}=\beta(t_{1})$ 且 $g=\beta^{-1}\circ\alpha$，则 $g$ 是一个微分同胚，并且

$$
\begin{align}
D\alpha(t_{0})=D(\beta \circ g)(t_{0})=D\beta(t_{1})Dg(t_{0})
\end{align}
$$

$Dg(t_{0})$ 是一个 $1\times 1$ 矩阵，又由于 $g$ 是保持定向的，$Dg(t_{0})>0$。这表明

$$
\begin{gather}
\frac{D\alpha(t_{0})}{\lVert D\alpha(t_{0}) \rVert }=\frac{D\beta(t_{1})}{\lVert D\beta(t_{1}) \rVert }
\end{gather}
$$

因此向量场 $T$ 良定，并且 $C^{\infty}$ 连续。因为 $t=\alpha^{-1}(\mathbf{p})$ 是关于 $\mathbf{p}$ 的 $C^{\infty}$ 函数，并且 $D\alpha(t)$ 是关于 $t$ 的 $C^{\infty}$ 函数。

### Example 34.5

给定一个定向 $1$-流形 $M$，以及其上的单位切向量场 $T$，我们通常将 $T$ 的方向直接画在曲线上。因此一个定向 $1$-流形可以用一条有向曲线来表示。

![](7-1.png)

如果 $M$ 有一个非空边界，我们可能会遇到一个问题，如下图所示。

![](7-2.png)

其中 $\partial M$ 包含两个点 $\mathbf{p}$ 和 $\mathbf{q}$。如果 $\alpha\colon U\to V$ 是 $\mathbf{p}$ 处的坐标卡，$U$ 在 $\mathbb{H}^{1}$ 中开的事实表明 $\mathbf{p}$ 处的切向量 $T(\mathbf{p})$ 必然是从 $\mathbf{p}$ 指向 $M$ 的内部。类似地，$T(\mathbf{q})$ 从 $\mathbf{q}$ 指向 $M$ 的内部。然而，从上图中我们可以看出，不存在 $M$ 上的一个连续切向量场同时在 $\mathbf{p},\mathbf{q}$ 点都指向 $M$ 的内部。因此，似乎 $M$ 不是可定向的。显然这是一个谬论。

这一问题来源于我们对 $1$-流形上的坐标卡设置了过大的约束。如果我们允许坐标卡的定义域在 $\mathbb{R},\mathbb{H}^{1}$ 或者左半直线 $\mathbb{L}^{1}=\{ x:x\leq 0 \}$ 中开，那么这一额外的自由度将允许我们给予每个 $1$-流形定向。

![](7-3.png)

因此，我们做出如下约定：

### Convention

对于 $1$-流形 $M$，我们将允许坐标卡的定义域是 $\mathbb{R},\mathbb{H}^{1}$ 或 $\mathbb{L}^{1}$ 中的开集。

现在我们考虑 $\mathbb{R}^{n}$ 中的 $n-1$ 流形，此时我们可以将 $M$ 上的定向描述为其上的一个单位法向量场。

### Definition 34.6

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $n-1$ 流形。如果 $\mathbf{p}\in M$，令 $(\mathbf{p};\mathbf{n})$ 为 $n$ 维向量空间 $T_{\mathbf{p}}(\mathbb{R}^{n})$ 中正交于 $n-1$ 维子空间 $T_{\mathbf{p}}(M)$ 的一个单位向量。则 $\mathbf{n}$ 在相差一个符号下是唯一的。给定 $M$ 的一个定向，选取 $\mathbf{p}$ 处的坐标卡 $\alpha\colon U\to V$ 属于该定向，令 $\alpha(\mathbf{x})=\mathbf{p}$。则 $D\alpha(\mathbf{x})$ 的列给出了 $T_{\mathbf{p}}(M)$ 的一个基

$$
\begin{gather}
(\mathbf{p};\partial\alpha /\partial x_{1}),\dots,(\mathbf{p};\partial\alpha /\partial x_{n-1})
\end{gather}
$$

我们确定 $\mathbf{n}$ 的符号，使得标架

$$
\begin{gather}
(\mathbf{n},\partial\alpha /\partial x_{1},\dots,\partial\alpha /\partial x_{n-1})
\end{gather}
$$

是右手系，即 $\det[\mathbf{n}\quad D\alpha(\mathbf{x})]>0$。在后续的章节我们将证明 $\mathbf{n}$ 是良定的，并且 $\mathbf{n}(\mathbf{p})$ 是关于 $\mathbf{p}$ 的 $C^{\infty}$ 函数。向量场 $N(\mathbf{p})=(\mathbf{p};\mathbf{n}(\mathbf{p}))$ 就称为对应于 $M$ 上定向的单位法向量场。

### Example 34.7

我们现在可以给出一个不可定向流形的例子。如图，

![](7-4.png)

$\mathbb{R}^{3}$ 中的这个 $2$-流形上不存在连续的单位法向量场，因为从一点处沿着“一侧”走，最终会达到“另一侧”。这一流形被称为 Möbius 带。

最后，我们来考虑 $\mathbb{R}^{n}$ 中的 $n$-流形。在这种情况下，$M$ 不仅是可定向的，并且事实上它还有一种“自然的”定向。

### Definition 34.8

设 $M$ 是 $\mathbb{R}^{n}$ 上的 $n$-流形。如果 $\alpha\colon U\to V$ 是 $M$ 上的坐标卡，那么 $D\alpha$ 是 $n\times n$ 矩阵。我们定义 $M$ 的自然定向为所有满足 $\det D\alpha>0$ 的坐标卡 $\alpha$ 构成的集合。容易看出两个这样的坐标卡是正向重叠的。

我们需要证明 $M$ 可以被这样的坐标卡覆盖。给定 $\mathbf{p}\in M$，令 $\alpha\colon U\to V$ 为 $\mathbf{p}$ 处的坐标卡。现在 $U$ 在 $\mathbb{R}^{n}$ 或 $\mathbb{H}^{n}$ 中开，通过缩小 $U$，我们可以假设 $U$ 或者是 $\varepsilon$-开球，或者是 $\varepsilon$-开球与 $\mathbb{H}^{n}$ 的交集。无论哪种情况，$U$ 是连通的，故 $\det D\alpha$ 在 $U$ 上不改变符号。如果 $\det D\alpha>0$，那么 $\alpha$ 就是所求的 $\mathbf{p}$ 处的坐标卡；否则 $\alpha \circ r$ 是所求的坐标卡，其中 $r\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 定义为

$$
\begin{gather}
r(x_{1},x_{2},\dots,x_{n})=(-x_{1},x_{2},\dots,x_{n})
\end{gather}
$$

## Reversing the Orientation of a Manifold

我们令 $r\colon \mathbb{R}^{k}\to \mathbb{R}^{k}$ 为反射变换

$$
\begin{gather}
r(x_{1},x_{2},\dots,x_{k})=(-x_{1},x_{2},\dots,x_{k})
\end{gather}
$$

它是自身的逆。当 $k>1$ 时，$r$ 将 $\mathbb{H}^{k}$ 映射到 $\mathbb{H}^{k}$；当 $k=1$ 时，$r$ 将 $\mathbb{H}^{1}$ 映射到 $\mathbb{L}^{1}$。

### Definition 34.9

设 $M$ 是 $\mathbb{R}^{n}$ 中的定向 $k$-流形。如果 $\alpha_{i}\colon U_{i}\to V_{i}$ 是属于 $M$ 的定向的坐标卡，令 $\beta_{i}$ 为坐标卡

$$
\begin{gather}
\beta_{i}=\alpha_{i}\circ r\colon r(U_{i})\to V_{i}
\end{gather}
$$

则 $\beta_{i}$ 与 $\alpha_{i}$ 负向重叠，因此它不属于 $M$ 的定向。然而，$\beta_{i}$ 两两之间正向重叠，它们构成了 $M$ 的一个定向，称为定向 $\{ \alpha_{i} \}$ 的反定向。

于是，任何定向 $k$-流形 $M$ 上都至少有两个定向，一个给定的定向与其反定向。

注意到，如果 $M$ 是定向 $1$-流形，其切向量场为 $T$，则其反定向对应的切向量场为 $-T$。因为如果 $\alpha\colon U\to V$ 是属于给定定向的坐标卡，那么 $\alpha \circ r$ 属于 $M$ 的反定向。我们有 $(\alpha \circ r)(t)=\alpha(-t)$，因此 $D(\alpha \circ r)=-D\alpha$。

类似地，如果 $M$ 是定向 $n-1$ 流形，其法向量场为 $N$，则其反定向对应的法向量场为 $-N$。因为

$$
\begin{gather}
\frac{ \partial (\alpha \circ r) }{ \partial x_{1} } =-\frac{ \partial \alpha }{ \partial x_{1} } , \quad \frac{ \partial (\alpha \circ r) }{ \partial x_{i} } =\frac{ \partial \alpha }{ \partial x_{i} } \quad (i>1)
\end{gather}
$$

另外，下面两个标架

$$
\begin{gather}
\left( \mathbf{n},\frac{ \partial \alpha }{ \partial x_{1} } ,\frac{ \partial \alpha }{ \partial x_{2} } ,\dots,\frac{ \partial \alpha }{ \partial x_{n-1} }  \right) \quad \text{and}\quad \left( -\mathbf{n},-\frac{ \partial \alpha }{ \partial x_{1} } ,\frac{ \partial \alpha }{ \partial x_{2} } ,\dots,\frac{ \partial \alpha }{ \partial x_{n-1} }  \right)
\end{gather}
$$

中，一个标架是右手的当且仅当另一个是右手的。因此如果 $\mathbf{n}$ 对应于坐标卡 $\alpha$，那么 $-\mathbf{n}$ 对应于坐标卡 $\alpha \circ r$。

## The Induced Orientation of $\partial M$

### Theorem 34.10

设 $k>1$。如果 $M$ 是有非空边界的定向 $k$-流形，那么 $\partial M$ 是可定向的。

#### Proof

设 $\mathbf{p}\in \partial M$，$\alpha\colon U\to V$ 为 $\mathbf{p}$ 处的坐标卡。根据 [[5 Manifolds#Theorem 24.4]]，存在一个 $\partial M$ 上的坐标卡 $\alpha_{0}$，它可以通过对 $\alpha$ 进行限制得到。形式上，如果我们定义 $b\colon \mathbb{R}^{k-1}\to \mathbb{R}^{k}$ 为

$$
\begin{gather}
b(x_{1},\dots,x_{k-1})=(x_{1},\dots,x_{k-1},0)
\end{gather}
$$

那么 $\alpha_{0}=\alpha \circ b$。

我们证明，如果 $\alpha,\beta$ 是 $\mathbf{p}$ 处正向重叠的坐标卡，那么 $\alpha_{0}$ 和 $\beta_{0}$ 也正向重叠。令 $g\colon W_{0}\to W_{1}$ 为转移函数 $g=\beta^{-1}\circ\alpha$，其中 $W_{0},W_{1}$ 在 $\mathbb{H}^{k}$ 中开，则 $\det Dg>0$。

![](7-5.png)

如果 $\mathbf{x}\in \partial \mathbb{H}^{k}$，那么 $Dg(\mathbf{x})$ 的最后一行为

$$
\begin{gather}
Dg_{k}(\mathbf{x})=[0\quad \cdots \quad 0 \quad \partial g_{k} /\partial x_{k}]
\end{gather}
$$

其中 $\partial g_{k} /\partial x_{k}\geq 0$。因为在 $\mathbf{x}$ 处，如果我们给予 $x_{1},\dots,x_{k-1}$ 一个正增量，那么 $g_{k}$ 的值不变；而如果我们给予 $x_{k}$ 一个正增量，$g_{k}$ 的值不会减少。于是对 $j<k$ 有 $\partial g_{k} /\partial x_{j}=0$，而 $\partial g_{k} /\partial x_{k}\geq 0$。

由于 $\det Dg>0$，故 $\partial g_{k} /\partial x_{k}>0$，从而

$$
\begin{gather}
\det\frac{ \partial (g_{1},\dots,g_{k-1}) }{ \partial (x_{1},\dots,x_{k-1}) } >0
\end{gather}
$$

但这个矩阵正是转移函数 $\beta_{0}^{-1}\circ\alpha_{0}$ 的导数。

以上定理的证明表明，给定 $M$ 的一个定向，我们可以通过对给定定向进行限制来得到 $\partial M$ 上的一个定向。然而，这一定向并不总是我们想要的。我们给出如下定义。

### Definition 34.11

设 $M$ 是有非空边界的定向 $k$-流形。给定 $M$ 的一个定向，其对应的 $\partial M$ 上的诱导定向定义如下：如果 $k$ 是偶数，它就是通过对给定定向中的坐标卡进行限制得到的定向；如果 $k$ 是奇数，它就是如上定义的定向的反定向。

### Example 34.12

$\mathbb{R}^{3}$ 中的 $2$-球面 $S^{2}$ 与环面 $T$ 都是可定向 $2$-流形，因为它们都是某个 $3$-流形的边界。一般来说，设 $M$ 是 $\mathbb{R}^{3}$ 中的 $3$-流形，取自然定向，我们可以得到关于 $\partial M$ 的诱导定向的什么结论？事实表明，这一诱导定向正是对应于 $\partial M$ 外法线方向的法向量场的定向。

给定 $M$，令 $\alpha\colon U\to V$ 为 $\mathbf{p}\in \partial M$ 处的坐标卡，属于给定的定向。则

$$
\begin{gather}
(\alpha \circ b)(\mathbf{x})=\alpha(x_{1},x_{2},0)
\end{gather}
$$

给出了 $\partial M$ 上 $\mathbf{p}$ 处的坐标卡。由于 $M$ 是 $3$-流形，故 $\partial M$ 的诱导定向是由限制坐标卡得到的定向的反定向。因此 $\partial M$ 上的单位法向量场 $N=(\mathbf{p};\mathbf{n})$ 满足性质：$(-\mathbf{n},\partial\alpha /\partial x_{1},\partial\alpha /\partial x_{2})$ 是右手标架。

另一方面，由于 $M$ 上取自然定向，$\det D\alpha>0$。于是标架 $(\partial\alpha /\partial x_{3},\partial\alpha /\partial x_{1},\partial\alpha /\partial x_{2})$ 是右手的。因此 $-\mathbf{n}$ 与 $\partial\alpha /\partial x_{3}$ 位于 $\mathbf{p}$ 处的切平面的同一侧。由于 $\partial\alpha /\partial x_{3}$ 指向 $M$ 的内部，$\mathbf{n}$ 指向 $M$ 的外部。

![](7-6.png)

### Example 34.13

设 $M$ 是 $\mathbb{R}^{3}$ 中有非空边界的 $2$-流形。如果 $M$ 有定向，给予 $\partial M$ 诱导定向。令 $N$ 为 $M$ 上对应于给定定向的单位法向量场，$T$ 为 $\partial M$ 上对应于诱导定向的单位切向量场。$N$ 和 $T$ 的关系是什么？

![](7-7.png)

我们指出如下事实：给定 $N$ 和 $T$，对每个 $\mathbf{p}\in \partial M$ 我们令 $W(\mathbf{p})$ 为正交于 $N(\mathbf{p})$ 和 $T(\mathbf{p})$，并且使得 $(N(\mathbf{p}),T(\mathbf{p}),W(\mathbf{p}))$ 为右手标架的单位向量。则 $W(\mathbf{p})$ 在 $\mathbf{p}$ 处与 $M$ 相切，且从 $\partial M$ 指向 $M$ 的内部。

更直观地说，$N$ 与 $T$ 的关系可以描述为：如果你按 $T$ 的方向沿着 $\partial M$ 走，并且你的头顶方向与 $N$ 一致，那么流形 $M$ 就在你的左手边。

要证明这一断言，令 $\alpha\colon U\to V$ 为 $\mathbf{p}$ 处的坐标卡，属于 $M$ 的给定定向。则坐标卡 $\alpha \circ b$ 属于 $\partial M$ 的诱导定向，因为 $M$ 是 $2$-流形。向量 $\partial\alpha /\partial x_{1}$ 是参数化曲线 $\alpha \circ b$ 的速度向量，因此它与 $T$ 的方向一致。

另一方面，$\partial\alpha /\partial x_{2}$ 是一条从 $\mathbf{p}$ 进入 $M$ 的内部的参数化曲线的速度向量，因此它从 $\mathbf{p}$ 指向 $M$ 的内部。从 $\partial\alpha /\partial x_{2}$ 中减去其在 $T$ 方向上的投影，我们得到一个指向 $M$ 内部的向量 $\mathbf{w}$，它与 $T$ 正交。定义 $W(\mathbf{p})=(\mathbf{p};\mathbf{w} /\lVert \mathbf{w} \rVert)$。

最后，根据定义，$N(\mathbf{p})=(\mathbf{p};\mathbf{n})$ 是 $\mathbf{p}$ 处的法向量，使得 $(\mathbf{n},\partial\alpha /\partial x_{1},\partial\alpha /\partial x_{2})$ 是右手标架。由于

$$
\begin{gather}
\det[\mathbf{n} \quad \partial\alpha /\partial x_{1}\quad \partial\alpha /\partial x_{2}]=\det[\mathbf{n}\quad \partial\alpha /\partial x_{1}\quad \mathbf{w}]
\end{gather}
$$

故 $(N,T,W)$ 是右手标架。

# 35 Integrating Forms over Oriented Manifolds

现在我们定义一个定向 $k$-流形上的 $k$-形式 $\omega$ 的积分。这一过程与 [[5 Manifolds#25 Integrating a Scalar Function over a Manifold]] 中的过程是类似的。

我们首先考虑 $\omega$ 的支撑集可被单个坐标卡覆盖的情况。

### Definition 35.1

设 $M$ 是 $\mathbb{R}^{n}$ 上的紧致定向 $k$-流形，$\omega$ 为定义在包含 $M$ 的开集上的 $k$-形式。令 $C=M\cap \operatorname{supp}(\omega)$，则 $C$ 是紧致的。假设有坐标卡 $\alpha\colon U\to V$ 属于 $M$ 的定向，且 $C\subset V$。通过缩小 $U$，我们可以假设 $U$ 是有界的。我们定义 $\omega$ 在 $M$ 上的积分为

$$
\begin{gather}
\int_{M} \omega=\int_{\operatorname{Int}U} \alpha^{*}\omega
\end{gather}
$$

其中 $\operatorname{Int}U=U$ 如果 $U$ 在 $\mathbb{R}^{k}$ 中开；$\operatorname{Int}U=U\cap \mathbb{H}_{+}^{k}$ 如果 $U$ 在 $\mathbb{H}^{k}$ 中开但不在 $\mathbb{R}^{k}$ 中开。

首先，我们指出这一积分作为普通积分存在，从而其作为广义积分也存在。由于 $\alpha$ 可以扩张为 $\mathbb{R}^{k}$ 中的开集 $U'$ 上的 $C^{\infty}$ 函数，形式 $\alpha^{*}\omega$ 可以扩张为 $U'$ 上的 $C^{\infty}$ 形式。这一形式可以写成 $h\,\mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}$，于是

$$
\begin{gather}
\int_{\operatorname{Int}U}\alpha^{*}\omega=\int_{\operatorname{Int}U} h
\end{gather}
$$

函数 $h$ 在 $U$ 上连续，在 $U$ 中的紧致集 $\alpha^{-1}(C)$ 外消失，因此 $h$ 在 $U$ 上有界。如果 $U$ 在 $\mathbb{R}^{k}$ 中开，那么 $h$ 在 $\operatorname{Bd}U$ 上消失；如果 $U$ 在 $\mathbb{H}^{k}$ 中开但不在 $\mathbb{R}^{k}$ 中开，那么 $h$ 在 $(\operatorname{Bd}U)\setminus \partial \mathbb{H}^{k}$ 上消失，而 $\partial \mathbb{H}^{k}$ 的测度为零。无论在哪种情况下，$h$ 都在 $U$ 上可积，于是在 $\operatorname{Int}U$ 上可积。

第二，我们指出积分 $\int_{M}\omega$ 是良定的，与坐标卡的选取无关。这一结果的证明与 [[5 Manifolds#Lemma 25.2]] 非常类似，这里我们需要用到属于同一定向的坐标卡正向重叠的事实，于是转移函数 $\beta^{-1}\circ\alpha$ 是保持定向，从而 [[#Theorem 33.3]] 中的符号取 $+1$。

第三，我们可证该积分是线性的。这是因为 $\alpha^{*}$ 和 $\int_{\operatorname{Int}U}$ 都是线性的。

最后，如果 $-M$ 表示具有反定向的流形 $M$，则

$$
\begin{gather}
\int_{-M}\omega=-\int_{M}\omega
\end{gather}
$$

这一结果由 [[#Theorem 33.3]] 给出，其中的符号取 $-1$。

要定义一般的 $\int_{M}\omega$，我们用 $M$ 上的单位分解。

### Definition 35.2

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致定向 $k$-流形，$\omega$ 为定义在包含 $M$ 的开集上的 $k$-形式。用属于给定定向的坐标卡覆盖 $M$，选取一个单位分解 $\phi_{1},\dots,\phi_{\ell}$ 受这一族坐标卡控制，我们定义 $\omega$ 在 $M$ 上的积分为

$$
\begin{gather}
\int_{M} \omega=\sum_{i=1}^{\ell} \int_{M} \phi_{i}\omega
\end{gather}
$$

这一定义在 $\omega$ 的支撑集可被单个坐标卡覆盖时与前面的定义一致。此外，这一定义不依赖于特定单位分解的选取。这两个结论的证明和 [[5 Manifolds#25 Integrating a Scalar Function over a Manifold]] 中的证明是类似的。

### Theorem 35.3

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致定向 $k$-流形，$\omega,\eta$ 为定义在包含 $M$ 的开集上的 $k$-形式。则

$$
\begin{gather}
\int_{M} (a\omega+b \eta)=a\int_{M}\omega+b\int_{M}\eta
\end{gather}
$$

令 $-M$ 为具有反定向的流形 $M$，则

$$
\begin{gather}
\int_{-M} \omega=-\int_{M}\omega
\end{gather}
$$

最后，和 $\int_{M}f\,\mathrm{d}V$ 一样，我们给出 $\int_{M}\omega$ 的一个计算公式。在实际应用中，我们将 $M$ 分解为若干参数化流形，然后在每个部分上积分。

### Theorem 35.4

设 $M$ 是 $\mathbb{R}^{n}$ 上的紧致定向 $k$-流形，$\omega$ 为定义在包含 $M$ 的开集上的 $k$-形式。假设对 $i=1,\dots,N$，坐标卡 $\alpha\colon A_{i}\to M_{i}$ 属于 $M$ 的定向，使得 $A_{i}$ 在 $\mathbb{R}^{k}$ 中开，且 $M$ 等于 $M$ 中的开集 $M_{1},\dots,M_{N}$ 和 $M$ 中的零测集 $K$ 的无交并，则

$$
\begin{gather}
\int_{M} \omega=\sum_{i=1}^{N} \int_{A_{i}} \alpha_{i}^{*}\omega
\end{gather}
$$

#### Proof

这一定理的证明与 [[5 Manifolds#Theorem 25.7]] 是几乎一致的。等价地，我们可以应用下一节中的 [[#Theorem 36.3]]，将形式的积分转化为标量函数对体积的积分，然后应用 [[5 Manifolds#Theorem 25.7]]。

# 36 A Geometric Interpretation of Forms and Integrals

一个 $k$-形式在定向 $k$-流形上的积分的概念相当抽象。我们可以给它一个直观的描述吗？本节我们来展示形式的积分如何与流形上的特定标量函数的积分联系起来，后者是一个更贴近于我们的几何直观的概念。

### Theorem 36.1

设 $W$ 是 $\mathbb{R}^{n}$ 的 $k$ 维子空间，$(\mathbf{a}_{1},\dots,\mathbf{a}_{k})$ 为 $W$ 中的标准正交 $k$-标架，并令 $f$ 为 $W$ 上的交错 $k$-张量。如果 $(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$ 是 $W$ 上的任意 $k$-元组，那么

$$
\begin{gather}
f(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=\varepsilon V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})f(\mathbf{a}_{1},\dots,\mathbf{a}_{k})
\end{gather}
$$

其中 $\varepsilon=\pm 1$。如果 $\mathbf{x}_{i}$ 线性无关，那么 $\varepsilon=+1$ 如果 $(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$ 与 $(\mathbf{a}_{1},\dots,\mathbf{a}_{k})$ 属于 $W$ 的相同定向，反之则 $\varepsilon=-1$。

如果 $\mathbf{x}_{i}$ 是线性相关的，那么 $V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=0$，$\varepsilon$ 的符号无关紧要。

#### Proof

**第一步** 我们证明 $W=\mathbb{R}^{k}$ 时的情况。

此时，交错张量 $f$ 是行列式函数的标量倍，即

$$
\begin{gather}
f(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=c \det[\mathbf{x}_{1}\cdots \mathbf{x}_{k}]
\end{gather}
$$

如果 $\mathbf{x}_{i}$ 线性相关，那么 $f$ 消失，结论是平凡的。反之，我们有

$$
\begin{gather}
f(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=c\det [\mathbf{x}_{1}\cdots \mathbf{x}_{k}]=c\varepsilon_{1}V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})
\end{gather}
$$

其中 $\varepsilon_{1}=+1$ 如果 $(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$ 是右手标架，反之则 $\varepsilon_{1}=-1$。类似地，

$$
\begin{gather}
f(\mathbf{a}_{1},\dots,\mathbf{a}_{k})=c\varepsilon_{2}V(\mathbf{a}_{1},\dots,\mathbf{a}_{k})=c\varepsilon_{2}
\end{gather}
$$

因此

$$
\begin{gather}
f(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=(\varepsilon_{1} /\varepsilon_{2}) V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})f(\mathbf{a}_{1},\dots,\mathbf{a}_{k})
\end{gather}
$$

其中 $\varepsilon=\varepsilon_{1} /\varepsilon_{2}=+1$ 如果 $(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$ 与 $(\mathbf{a}_{1},\dots,\mathbf{a}_{k})$ 属于同一定向，否则 $\varepsilon=-1$。

**第二步** 我们证明一般的情况。

给定 $W$，选取一个正交变换 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 将 $W$ 映射到 $\mathbb{R}^{k}\times 0$。令 $k\colon \mathbb{R}^{k}\times 0\to W$ 为其逆变换。我们用 $k$ 将 $W$ 上的交错张量拉回到 $\mathbb{R}^{k}\times 0$ 的交错张量 $k^{*}f$ 上。

由于 $(h(\mathbf{x}_{1}),\dots,h(\mathbf{x}_{k}))$ 是 $\mathbb{R}^{k}\times 0$ 中的 $k$-元组，$(h(\mathbf{a}_{1}),\dots,h(\mathbf{a}_{k}))$ 为 $\mathbb{R}^{k}\times 0$ 中的标准正交标架，根据第一步的结论有

$$
\begin{gather}
(k^{*}f)(h(\mathbf{x}_{1}),\dots,h(\mathbf{x}_{k}))=\varepsilon V(h(\mathbf{x}_{1}),\dots,h(\mathbf{x}_{k}))(k^{*}f)(h(\mathbf{a}_{1}),\dots,h(\mathbf{a}_{k}))
\end{gather}
$$

由于 $V$ 在正交变换下不变，我们可以将上式写成

$$
\begin{gather}
f(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=\varepsilon V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})f(\mathbf{a}_{1},\dots,\mathbf{a}_{k})
\end{gather}
$$

现在假设 $\mathbf{x}_{i}$ 线性无关。由于 $h$ 是正交变换，故它是线性同构，于是 $(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$ 与 $(\mathbf{a}_{1},\dots,\mathbf{a}_{k})$ 属于 $W$ 的同一定向当且仅当 $(h(\mathbf{x}_{1}),\dots,h(\mathbf{x}_{k}))$ 与 $(h(\mathbf{a}_{1}),\dots,h(\mathbf{a}_{k}))$ 属于 $\mathbb{R}^{k}\times 0$ 的同一定向。

特别地，以上定理表明，如果 $(\mathbf{a}_{1},\dots,\mathbf{a}_{k})$ 和 $(\mathbf{b}_{1},\dots,\mathbf{b}_{k})$ 是 $W$ 中的两个标准正交标架，那么

$$
\begin{gather}
f(\mathbf{a}_{1},\dots,\mathbf{a}_{k})=\pm f(\mathbf{b}_{1},\dots,\mathbf{b}_{k})
\end{gather}
$$

其中的符号取决于两个标架是否属于 $W$ 的同一定向。

### Definition 36.2

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $k$-流形，$\mathbf{p}\in M$。如果 $M$ 有定向，那么 $M$ 在 $\mathbf{p}$ 处的切空间有一个自然的定向，定义如下：选取 $\mathbf{p}$ 处的坐标卡 $\alpha\colon U\to V$ 属于 $M$ 的定向，令 $\alpha(\mathbf{x})=\mathbf{p}$。$T_{\mathbf{p}}(M)$ 中所有具有形式

$$
\begin{gather}
(\alpha_{*}(\mathbf{x};\mathbf{a}_{1}),\dots,\alpha_{*}(\mathbf{x};\mathbf{a}_{k}))
\end{gather}
$$

的 $k$-标架，其中 $(\mathbf{a}_{1},\dots,\mathbf{a}_{k})$ 是 $\mathbb{R}^{k}$ 中的右手标架，构成了 $T_{\mathbf{p}}(M)$ 上由 $M$ 的定向所诱导的自然定向。容易证明这一定向的良定的，与 $\alpha$ 的选取无关。

### Theorem 36.3

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致定向 $k$-流形，$\omega$ 是定义在包含 $M$ 的开集上的 $k$-形式。设 $\lambda$ 为 $M$ 上的标量函数，定义为

$$
\begin{gather}
\lambda(\mathbf{p})=\omega(\mathbf{p})((\mathbf{p};\mathbf{a}_{1}),\dots,(\mathbf{p};\mathbf{a}_{k}))
\end{gather}
$$

其中 $((\mathbf{p};\mathbf{a}_{1}),\dots,(\mathbf{p};\mathbf{a}_{k}))$ 是属于 $T_{\mathbf{p}}(M)$ 自然定向的标准正交标架。则 $\lambda$ 是连续的，且

$$
\begin{gather}
\int_{M} \omega=\int_{M} \lambda \, \mathrm{d}V
\end{gather}
$$

#### Proof

根据线性性，我们只需证明 $\omega$ 的支撑集可被单个坐标卡 $\alpha\colon U\to V$ 覆盖的情况。我们有

$$
\begin{gather}
\alpha^{*}\omega=h\,\mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}
\end{gather}
$$

令 $\alpha(\mathbf{x})=\mathbf{p}$，我们计算 $h(\mathbf{x})$ 如下：

$$
\begin{align}
h(\mathbf{x}) &= (\alpha^{*}\omega)(\mathbf{x})((\mathbf{x};\mathbf{e}_{1}),\dots,(\mathbf{x};\mathbf{e}_{k})) \\
&=\omega(\mathbf{p})(\alpha_{*}(\mathbf{x};\mathbf{e}_{1}),\dots,\alpha_{*}(\mathbf{x};\mathbf{e}_{k})) \\
&=\omega(\mathbf{p})((\mathbf{p};\partial\alpha /\partial x_{1}),\dots,(\mathbf{p};\partial\alpha /\partial x_{k})) \\
&= V(D\alpha(\mathbf{x})) \lambda(\mathbf{p})
\end{align}
$$

其中最后一步由 [[#Theorem 36.1]] 给出。其符号是 $+1$，因为根据定义，标架

$$
\begin{gather}
((\mathbf{p};\partial\alpha /\partial x_{1}),\dots,(\mathbf{p};\partial\alpha /\partial x_{k}))
\end{gather}
$$

属于 $T_{\mathbf{p}}(M)$ 的自然定向。现在，由于 $D\alpha$ 的秩为 $k$，故 $V(D\alpha)\neq 0$。又由于 $\mathbf{x}=\alpha^{-1}(\mathbf{p})$ 是连续函数，故

$$
\begin{gather}
\lambda(\mathbf{p})=h(\mathbf{x}) / V(D\alpha(\mathbf{x}))
\end{gather}
$$

也是连续函数。于是

$$
\begin{gather}
\int_{M} \lambda\,\mathrm{d}V=\int_{\operatorname{Int}U} (\lambda \circ\alpha)V(D\alpha)=\int_{\operatorname{Int}U} h
\end{gather}
$$

另一方面，

$$
\begin{gather}
\int_{M} \omega=\int_{\operatorname{Int}U}\alpha^{*}\omega=\int_{\operatorname{Int}U} h
\end{gather}
$$

这就完成了证明。

这一定理表明，对每个定义在包含紧致定向 $k$-流形 $M$ 的开集上的 $k$-形式 $\omega$，我们总是可以将其积分写成一个关于特定（$C^{\infty}$）标量函数 $\lambda$ 的积分：

$$
\begin{gather}
\int_{M} \omega=\int_{M} \lambda\,\mathrm{d}V
\end{gather}
$$

这一定理的逆命题也成立，但它的证明要困难的多：

首先我们证明存在一个 $k$-形式 $\omega_{v}$，定义在包含 $M$ 的开集上，使得 $\omega_{v}(\mathbf{p})$ 在 $T_{\mathbf{p}}(M)$ 的任意属于自然定向的标准正交标架上的值都为 $1$。于是如果 $\lambda$ 是 $M$ 上的 $C^{\infty}$ 函数，那么

$$
\begin{gather}
\int_{M} \lambda\,\mathrm{d}V=\int_{M} \lambda\omega_{v}
\end{gather}
$$

于是 $\lambda$ 在 $M$ 上关于体积的积分就可以转化为形式 $\lambda\omega_{v}$ 在 $M$ 上的积分。这一形式 $\omega_{v}$ 就称为 $M$ 上的一个体积形式，因为

$$
\begin{gather}
\int_{M} \omega_{v}=\int_{M} \mathrm{d}V=v(M)
\end{gather}
$$

# 37 The Generalized Stokes' Theorem

现在我们来到了前面几章内容的集大成者。它是一个关于微分形式的积分的普遍定理，包含了向量积分学的三个基本定理——Green 定理、Stokes 定理和散度定理——作为它的特例。

我们首先以一个特例入手。令 $I^{k}$ 表示 $\mathbb{R}^{k}$ 中的单位 $k$-立方体

$$
\begin{gather}
I^{k}=[0,1]^{k}=[0,1]\times\dots \times[0,1]
\end{gather}
$$

则 $\operatorname{Int}I^{k}$ 就是开立方体 $(0,1)^{k}$。

### Lemma 37.1

设 $k>1$。令 $\eta$ 为定义在包含 $I^{k}$ 的开集 $U$ 上的 $k-1$ 形式。假设 $\eta$ 在除了 $(\operatorname{Int}I^{k-1})\times 0$ 外的 $\operatorname{Bd}I^{k}$ 上消失，则

$$
\begin{gather}
\int_{\operatorname{Int}I^{k}} \mathrm{d}\eta=(-1)^{k} \int_{\operatorname{Int}I^{k-1}} b^{*}\eta 
\end{gather}
$$

其中 $b\colon I^{k-1}\to I^{k}$ 定义为

$$
\begin{gather}
b(u_{1},\dots,u_{k-1})=b(u_{1},\dots,u_{k-1},0)
\end{gather}
$$

#### Proof

![](7-8.png)

我们用 $\mathbf{x}$ 表示 $\mathbb{R}^{k}$ 的点，$\mathbf{u}$ 表示 $\mathbb{R}^{k-1}$ 的点。给定 $1\leq j\leq k$，我们令 $I_{j}$ 为 $k-1$ 元组

$$
\begin{gather}
I_{j}=(1,\dots,\hat{\jmath},\dots,k)=(1,\dots,j-1,j+1,\dots,k)
\end{gather}
$$

并记

$$
\begin{gather}
\mathrm{d}x_{I_{j}}=\mathrm{d}x_{1}\land\dots \land \widehat{\mathrm{d}x}_{j}\land\dots \land \mathrm{d}x_{k}
\end{gather}
$$

由于引理中的积分和 $b^{*}$ 都是线性的，我们只需证明特例

$$
\begin{gather}
\eta=f\, \mathrm{d}x_{I_{j}}
\end{gather}
$$

**第一步**

我们来计算

$$
\begin{gather}
\int_{\operatorname{Int}I^{k}} \mathrm{d}\eta
\end{gather}
$$

我们有

$$
\begin{align}
\mathrm{d}\eta &= \mathrm{d}f \land \mathrm{d}x_{I_{j}} \\
&=\left( \sum_{i=1}^{k} D_{i}f\, \mathrm{d}x_{i} \right)\land \mathrm{d}x_{I_{j}} \\
&=(-1)^{j-1}D_{j}f \, \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}
\end{align}
$$

于是

$$
\begin{align}
\int_{\operatorname{Int}I^{k}} \mathrm{d}\eta &= (-1)^{j-1} \int_{\operatorname{Int}I^{k}} D_{j}f \\
&=(-1)^{j-1} \int_{I^{k}} D_{j}f \\
&=(-1)^{j-1} \int_{\mathbf{v}\in I^{k-1}}\int_{x_{j}\in I} D_{j}f(x_{1},\dots,x_{k})
\end{align}
$$

其中 $\mathbf{v}=(x_{1},\dots,\widehat{x}_{j},\dots,x_{k})$。根据微积分基本定理，我们有

$$
\begin{gather}
\int_{x_{j}\in I} D_{j}f(x_{1},\dots,x_{k})=f(x_{1},\dots,1,\dots,x_{k})-f(x_{1},\dots,0,\dots,x_{k})
\end{gather}
$$

由于 $\eta$ 在除了 $(\operatorname{Int}I^{k-1})\times 0$ 外的 $\operatorname{Bd}I^{k}$ 上消失，因此如果 $j<k$，那么上式右侧的表达式消失，而当 $j=k$ 时，它等于

$$
\begin{gather}
-f(x_{1},\dots,x_{k-1},0)
\end{gather}
$$

于是

$$
\begin{gather}
\int_{\operatorname{Int}I^{k}} \mathrm{d}\eta=\begin{cases}
0, & j<k \\
\displaystyle (-1)^{k} \int_{I^{k-1}} (f\circ b),  & j=k
\end{cases}
\end{gather}
$$

**第二步**

我们计算另一个积分。函数 $b\colon \mathbb{R}^{k-1}\to \mathbb{R}^{k}$ 的导数为

$$
\begin{gather}
Db=\begin{bmatrix}
I_{k-1} \\
0
\end{bmatrix}
\end{gather}
$$

因此

$$
\begin{align}
b^{*}(\mathrm{d}x_{I_{j}}) &= \det Db(1,\dots,\hat{\jmath},\dots,k)\, \mathrm{d}u_{1}\land\dots \land \mathrm{d}u_{k-1} \\
&=\begin{cases}
0, & j<k \\
\mathrm{d}u_{1}\land\dots \land \mathrm{d}u_{k-1}, & j=k
\end{cases}
\end{align}
$$

于是

$$
\begin{gather}
\int_{\operatorname{Int}I^{k-1}} b^{*}\eta =\begin{cases}
0, & j<k \\
\displaystyle \int_{\operatorname{Int}I^{k-1}} (f\circ b), & j=k
\end{cases}
\end{gather}
$$

这就完成了证明。

### Theorem 37.2 (Stokes)

设 $k>1$。设 $M$ 是 $\mathbb{R}^{n}$ 上的紧致定向 $k$-流形，并给予 $\partial M$ 诱导定向如果 $\partial M\neq \varnothing$。令 $\omega$ 是定义在包含 $M$ 的开集上的 $k-1$ 形式，则

$$
\begin{gather}
\int_{M} \mathrm{d}\omega=\int_{\partial M} \omega
\end{gather}
$$

如果 $\partial M\neq \varnothing$；而 $\int_{M}\mathrm{d}\omega=0$ 如果 $\partial M=\varnothing$。

#### Proof

**第一步** 我们用精心选取的坐标卡覆盖 $M$。

![](7-9.png)

对于第一类情况，$\mathbf{p}\in M\setminus \partial M$。选取坐标卡 $\alpha\colon U\to V$ 属于 $M$ 的定向，使得 $U$ 在 $\mathbb{R}^{k}$ 中开，且包含 $I^{k}$，并且 $\alpha$ 将 $\operatorname{Int}I^{k}$ 中的一点映射到 $\mathbf{p}$。（如果我们从一个任意坐标卡 $\alpha\colon U\to V$ 开始，通过一个平移与定义域的拉伸，我们可以得到所求的形式）。令 $W=\operatorname{Int}I^{k}$，$Y=\alpha(W)$。则 $\alpha\colon W\to Y$ 仍然是 $\mathbf{p}$ 处的坐标卡，属于 $M$ 的定向，且 $W$ 在 $\mathbb{R}^{k}$ 中开。我们选取这个 $\alpha$ 作为 $\mathbf{p}$ 处的坐标卡。

对于第二类情况，$\mathbf{p}\in \partial M$。选取坐标卡 $\alpha\colon U\to V$ 属于 $M$ 的定向，使得 $U$ 在 $\mathbb{H}^{k}$ 中开，且包含 $I^{k}$，并且 $\alpha$ 将 $(\operatorname{Int}I^{k-1})\times 0$ 中的一点映射到 $\mathbf{p}$。令

$$
\begin{gather}
W=(\operatorname{Int}I^{k})\cup((\operatorname{Int}I^{k-1})\times 0)
\end{gather}
$$

并取 $Y=\alpha(W)$。则 $\alpha\colon W\to Y$ 也是 $\mathbf{p}$ 处属于 $M$ 的定向的坐标卡，其中 $W$ 在 $\mathbb{H}^{k}$ 中开而不在 $\mathbb{R}^{k}$ 中开。

我们将用上面两种坐标卡 $\alpha\colon W\to Y$ 覆盖 $M$。在每种情况下，我们都可以将 $\alpha$ 扩张为一个 $\mathbb{R}^{k}$ 中包含 $I^{k}$ 的开集上的 $C^{\infty}$ 函数。

**第二步**

由于微分算子 $\mathrm{d}$ 和相关的积分是线性的，故我们只需考虑集合

$$
\begin{gather}
C=M\cap \operatorname{supp}(\omega)
\end{gather}
$$

可被单个坐标卡 $\alpha\colon W\to Y$ 覆盖的情况。由于 $\mathrm{d}\omega$ 的支撑集包含于 $\operatorname{supp}(\omega)$，因此 $\alpha$ 也覆盖了 $M\cap \operatorname{supp}(\mathrm{d}\omega)$。

令 $\eta=\alpha^{*}\omega$。它可以扩张为 $\mathbb{R}^{k}$ 中包含 $I^{k}$ 的开集上的 $C^{\infty}$ 形式。此外，$\eta$ 在除了 $(\operatorname{Int}I^{k-1})\times 0$ 外的 $\operatorname{Bd}I^{k}$ 上消失，因此它满足 [[#Lemma 37.1]] 的条件。

**第三步** 我们对第一种 $\alpha\colon W\to Y$ 证明该定理。此时 $W=\operatorname{Int}I^{k}$ 且 $Y$ 与 $\partial M$ 不相交。

由于 $\alpha^{*}\mathrm{d}\omega=\mathrm{d}(\alpha^{*}\omega)=\mathrm{d}\eta$，我们有

$$
\begin{gather}
\int_{M} \mathrm{d}\omega=\int_{\operatorname{Int}I^{k}} \alpha^{*}\mathrm{d}\omega=\int_{\operatorname{Int}I^{k}} \mathrm{d}\eta=(-1)^{k}\int_{\operatorname{Int}I^{k-1}} b^{*}\eta
\end{gather}
$$

此时，$\eta$ 在 $\operatorname{Int}I^{k}$ 外消失，特别地，它在 $I^{k-1}\times 0$ 上消失，故 $b^{*}\eta=0$，因此 $\int_{M}\mathrm{d}\omega=0$。

如果 $\partial M=\varnothing$，那么我们就完成了证明。如果 $\partial M\neq \varnothing$，则结论是平凡的：$\omega$ 的支撑集与 $\partial M$ 不相交，因此 $\int_{\partial M}\omega=0$。

**第四步** 我们对第二种 $\alpha\colon W\to Y$ 证明该定理。此时 $W$ 在 $\mathbb{H}^{k}$ 中开而不在 $\mathbb{R}^{k}$ 中开，并且 $Y$ 与 $\partial M$ 相交。

我们仍然有

$$
\begin{gather}
\int_{M} \mathrm{d}\omega=\int_{\operatorname{Int}I^{k}}\mathrm{d}\eta=(-1)^{k} \int_{\operatorname{Int}I^{k-1}} b^{*}\eta
\end{gather}
$$

下面我们计算 $\int_{\partial M}\omega$。集合 $\partial M\cap \operatorname{supp}(\omega)$ 由坐标卡

$$
\begin{gather}
\beta=\alpha \circ b\colon \operatorname{Int}I^{k-1}\to Y\cap \partial M
\end{gather}
$$

覆盖，后者通过限制 $\alpha$ 得到。$\beta$ 属于 $\partial M$ 的诱导定向如果 $k$ 是偶数，反之则属于诱导定向的反定向。因此当 $k$ 为奇数时，我们必须反转积分的符号，因此

$$
\begin{gather}
\int_{\partial M} \omega=(-1)^{k}\int_{\operatorname{Int}I^{k-1}} \beta^{*}\omega
\end{gather}
$$

根据 $\beta^{*}\omega=b^{*}(\alpha^{*}\omega)=b^{*}\eta$ 就完成了证明。

### Corollary 37.3 (Green)

设 $M$ 是 $\mathbb{R}^{2}$ 中的紧致 $2$-流形，取自然定向，给予 $\partial M$ 诱导定向如果 $\partial M\neq \varnothing$。令 $P\,\mathrm{d}x+Q\,\mathrm{d}y$ 为定义在包含 $M$ 的开集上的 $1$-形式，则

$$
\begin{gather}
\int_{\partial M} P\,\mathrm{d}x+Q\,\mathrm{d}y=\int_{M} (D_{1}Q-D_{2}P)\,\mathrm{d}x\land \mathrm{d}y
\end{gather}
$$

#### Proof

取 $\omega=P\,\mathrm{d}x+Q\,\mathrm{d}y$，则

$$
\begin{align}
\mathrm{d}\omega &= \mathrm{d}P\land \mathrm{d}x+\mathrm{d}Q\land \mathrm{d}y \\
&=D_{2}P\,\mathrm{d}y\land \mathrm{d}x+D_{1}Q\,\mathrm{d}x\land \mathrm{d}y \\
&=(D_{1}Q-D_{2}P)\,\mathrm{d}x\land \mathrm{d}y
\end{align}
$$

应用 Stokes 定理即证。

我们对维数 $k>1$ 的流形证明了 Stokes 定理，当 $k=1$ 时会发生什么？如果 $\partial M=\varnothing$，我们不会有问题。然而，如果 $\partial M\neq \varnothing$，我们就面临着如下问题：$0$-流形的所谓“定向”是什么意思？以及我们如何定义 $0$-形式在 $0$-流形上的“积分”？

要回答这些问题，我们首先考虑一个特殊情况。

### Definition 37.4 arc 弧

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $1$-流形。假设有 $C^{\infty}$ 双射 $\alpha\colon [a,b]\to M$ 使得对任意 $t$ 有 $D\alpha(t)\neq 0$，则我们称 $M$ 是 $\mathbb{R}^{n}$ 中的一段弧。如果 $M$ 上有定向，使得坐标卡 $\alpha|(a,b)$ 属于该定向，我们就称 $\mathbf{p}=\alpha(a)$ 是 $M$ 的起点，$\mathbf{q}=\alpha(b)$ 是 $M$ 的终点。

![](7-10.png)

### Theorem 37.5

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $1$-流形，$f$ 为定义在包含 $M$ 的开集上的 $0$-形式。如果 $M$ 是以 $\mathbf{p}$ 为起点，$\mathbf{q}$ 为终点的弧，那么

$$
\begin{gather}
\int_{M} \mathrm{d}f=f(\mathbf{q})-f(\mathbf{p})
\end{gather}
$$

#### Proof

令 $\alpha\colon[a,b]\to M$ 如 [[#Definition 37.4 arc 弧]] 所示。则 $\alpha\colon(a,b)\to M\setminus \{ \mathbf{p},\mathbf{q} \}$ 是一个坐标卡，其覆盖了 $M$，除了一个零测集。因此根据 [[#Theorem 35.4]] 有

$$
\begin{gather}
\int_{M} \mathrm{d}f=\int_{(a,b)} \alpha^{*}(\mathrm{d}f)
\end{gather}
$$

而

$$
\begin{gather}
\alpha^{*}(\mathrm{d}f)=\mathrm{d}(f\circ\alpha)=D(f\circ\alpha)\,\mathrm{d}t
\end{gather}
$$

因此根据微积分基本定理有

$$
\begin{gather}
\int_{M} \mathrm{d}f=\int_{(a,b)} D(f\circ\alpha)\,\mathrm{d}t=f(\alpha(b))-f(\alpha(a))
\end{gather}
$$

以上定理给予了我们如何定义 $0$-流形上积分的启示。

### Definition 37.6

$\mathbb{R}^{n}$ 中的一个紧致 $0$-流形 $N$ 是 $\mathbb{R}^{n}$ 中的一个有限集 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{m} \}$。我们定义 $N$ 上的一个定向为一个函数 $\varepsilon\colon N\to \{ 1,-1 \}$。如果 $f$ 是定义在包含 $N$ 的开集上的 $0$-形式，我们定义 $f$ 在定向流形 $N$ 上的积分为

$$
\begin{gather}
\int_{N} f=\sum_{i=1}^{m} \varepsilon(\mathbf{x}_{i})f(\mathbf{x}_{i})
\end{gather}
$$

### Definition 37.7

如果 $M$ 是 $\mathbb{R}^{n}$ 中有非空边界的定向 $1$-流形，我们定义 $\partial M$ 上的诱导定向如下：对 $\mathbf{p}\in \partial M$，如果 $\mathbf{p}$ 处的坐标卡 $\alpha\colon U\to V$ 满足 $U$ 在 $\mathbb{H}^{1}$ 中开，则令 $\varepsilon(\mathbf{p})=-1$；反之，如果 $U$ 在 $\mathbb{L}^{1}$ 中开，则令 $\varepsilon(\mathbf{p})=+1$。

![](7-11.png)

### Theorem 37.8 (Stokes)

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致定向 $1$-流形，给予 $\partial M$ 诱导定向如果 $\partial M\neq \varnothing$。令 $f$ 为定义在包含 $M$ 的开集上的 $0$-形式，则

$$
\begin{gather}
\int_{M} \mathrm{d}f=\int_{\partial M} f
\end{gather}
$$

如果 $\partial M\neq \varnothing$；而 $\int_{M}\mathrm{d}f=0$ 如果 $\partial M=\varnothing$。

#### Proof

通过对任意属于 $M$ 的定向的坐标卡 $\alpha\colon U\to V$ 进行定义域的平移和伸缩，我们总可以用形如 $\alpha\colon W\to Y$ 的的坐标卡覆盖 $M$，其属于 $M$ 的定向，且 $W$ 是区间 $(0,1),[0,1),(-1,0]$ 中的一个。

我们来证明集合

$$
\begin{gather}
C=M\cap \operatorname{supp}(f)
\end{gather}
$$

可被单个坐标卡覆盖的情况。

如果 $W=(0,1)$，那么 $Y$ 与 $\partial M$ 不相交。我们有

$$
\begin{gather}
\int_{M} \mathrm{d}f=\int_{(0,1)} \alpha^{*}(\mathrm{d}f)=f(\alpha(1))-f(\alpha(0))=0
\end{gather}
$$

因为 $f$ 在 $Y$ 中的紧致集 $C$ 外消失，从而 $f(\alpha(1))=f(\alpha(0))=0$。当 $\partial M\neq \varnothing$ 时，由于 $Y\cap \partial M=\varnothing$，故 $\int_{\partial M}f=0$。

如果 $W=[0,1)$，那么 $Y$ 与 $\partial M$ 相交。此时

$$
\begin{gather}
\int_{M} \mathrm{d}f=-f(\alpha(0))
\end{gather}
$$

另一方面，由于 $W$ 在 $\mathbb{H}^{1}$ 中开，因此 $\alpha(0) \in \partial M$ 处的诱导定向符号为 $-1$，从而

$$
\begin{gather}
\int_{\partial M}f=-f(\alpha(0))=\int_{M} \mathrm{d}f
\end{gather}
$$

最后，如果 $W=(-1,0]$，则其在 $\mathbb{L}^{1}$ 中开，从而 $\alpha(0)$ 处诱导定向的符号为 $+1$，故

$$
\begin{gather}
\int_{M} \mathrm{d}f=f(\alpha(0))=\int_{\partial M} f
\end{gather}
$$

这就完成了证明。

# 38 Applications to Vector Analysis

在 [[6 Differential Forms#31 Application to Vector and Scalar Fields]] 中，我们展示了特定阶数的微分形式可以解释为标量场或向量场。具体来说，当 $k=0,1,n-1,n$ 时。本节我们来展示形式的积分也可以做类似的解释，并且 Stokes 定理在这些情况下可以用标量场或向量场来表述。

## The Gradient Theorem for 1-Manifolds in $\mathbb{R}^{n}$

首先我们将 $1$-形式的积分用向量场来表示。设 $F$ 是定义在 $\mathbb{R}^{n}$ 中开集上的向量场，则它通过 $\alpha_{1}$ 线性同构于某个 $1$-形式 $\omega$，见 [[6 Differential Forms#Theorem 31.2]]。事实表明，$\omega$ 在一个定向 $1$-流形上的积分就等于 $F$ 的切向分量在流形上关于体积的积分。这就是如下引理的内容：

### Lemma 38.1

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致定向 $1$-流形，$T$ 为对应于此定向的单位切向量场。令

$$
\begin{gather}
F(\mathbf{x})=(\mathbf{x};f(\mathbf{x}))=\left( \mathbf{x};\sum f_{i}(\mathbf{x})\mathbf{e}_{i} \right)
\end{gather}
$$

为定义在包含 $M$ 的开集上的向量场，它对应于 $1$-形式

$$
\begin{gather}
\omega=\sum f_{i}\, \mathrm{d}x_{i}
\end{gather}
$$

则

$$
\begin{gather}
\int_{M} \omega=\int_{M} \langle F,T \rangle \,\mathrm{d}s
\end{gather}
$$

这里我们用 $\mathrm{d}s$ 来表示关于 $1$-体积，即长度的积分。注意到，如果我们将 $M$ 替换为 $-M$，那么积分 $\int_{M}\omega$ 改变符号。这一替换将使得 $T$ 变成 $-T$，因此 $\int_{M}\langle F,T \rangle\,\mathrm{d}s$ 同样改变符号。

#### Proof

根据 [[#Theorem 36.3]]，我们有

$$
\begin{gather}
\int_{M} \omega=\int_{M} \lambda\, \mathrm{d}s
\end{gather}
$$

其中 $\lambda(\mathbf{p})$ 是 $\omega(\mathbf{p})$ 在属于 $T_{\mathbf{p}}(M)$ 自然定向的标准正交基上的值。此时，切空间 $T_{\mathbf{p}}(M)$ 是 $1$ 维的，且 $T(\mathbf{p})$ 就是这样一个基。令 $T(\mathbf{p})=(\mathbf{p};\mathbf{t})$，则根据 $\omega=\sum f_{i}\,\mathrm{d}x_{i}$ 有

$$
\begin{gather}
\omega(\mathbf{p})(\mathbf{p};\mathbf{t})=\sum f_{i}(\mathbf{p}) t_{i}(\mathbf{p})
\end{gather}
$$

因此

$$
\begin{gather}
\lambda(\mathbf{p})=\langle F(\mathbf{p}),T(\mathbf{p}) \rangle 
\end{gather}
$$

### Theorem 38.2 (梯度定理)

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致 $1$-流形，$T$ 为 $M$ 上的单位切向量场。设 $f$ 为定义在包含 $M$ 的开集上的 $C^{\infty}$ 函数，如果 $\partial M= \varnothing$，则

$$
\begin{gather}
\int_{M} \langle \operatorname{grad}f,T \rangle \,\mathrm{d}s=0
\end{gather}
$$

如果 $\partial M=\{ \mathbf{x}_{1},\dots,\mathbf{x}_{m} \}$，令 $\varepsilon_{i}=-1$ 如果 $T$ 从 $\mathbf{x}_{i}$ 指向 $M$ 的内部；否则令 $\varepsilon_{i}=+1$。则

$$
\begin{gather}
\int_{M} \langle \operatorname{grad}f,T \rangle \,\mathrm{d}s=\sum_{i=1}^{m} \varepsilon_{i}f(\mathbf{x}_{i})
\end{gather}
$$

#### Proof

$1$-形式 $\mathrm{d}f$ 同构于向量场 $\operatorname{grad}f$，于是

$$
\begin{gather}
\int_{M} \mathrm{d}f=\int_{M} \langle \operatorname{grad}f,T \rangle \,\mathrm{d}s
\end{gather}
$$

根据 $1$ 维 Stokes 定理即证。

## The Divergence Theorem for $n-1$ Manifolds in $\mathbb{R}^{n}$

现在我们将 $n-1$ 形式的积分用向量场来表示。首先，我们验证一个前面的事实，即 $M$ 上的定向确定了 $M$ 上的一个单位法向量场。我们回顾一下 [[#Definition 34.6]]：

### Definition

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $n-1$ 流形。如果 $\mathbf{p}\in M$，令 $(\mathbf{p};\mathbf{n})$ 为 $n$ 维向量空间 $T_{\mathbf{p}}(\mathbb{R}^{n})$ 中正交于 $n-1$ 维子空间 $T_{\mathbf{p}}(M)$ 的一个单位向量。则 $\mathbf{n}$ 在相差一个符号下是唯一的。给定 $M$ 的一个定向，选取 $\mathbf{p}$ 处的坐标卡 $\alpha\colon U\to V$ 属于该定向，令 $\alpha(\mathbf{x})=\mathbf{p}$。则 $D\alpha(\mathbf{x})$ 的列给出了 $T_{\mathbf{p}}(M)$ 的一个基

$$
\begin{gather}
(\mathbf{p};\partial\alpha /\partial x_{1}),\dots,(\mathbf{p};\partial\alpha /\partial x_{n-1})
\end{gather}
$$

我们确定 $\mathbf{n}$ 的符号，使得标架

$$
\begin{gather}
(\mathbf{n},\partial\alpha /\partial x_{1},\dots,\partial\alpha /\partial x_{n-1})
\end{gather}
$$

是右手系，即 $\det[\mathbf{n}\quad D\alpha(\mathbf{x})]>0$。向量场 $N(\mathbf{p})=(\mathbf{p};\mathbf{n}(\mathbf{p}))$ 就称为对应于 $M$ 上定向的单位法向量场。

我们来证明 $N$ 是良定的。令 $\beta$ 为 $\mathbf{p}$ 处的另一个坐标卡，属于 $M$ 的定向。令 $g=\beta^{-1}\circ\alpha$ 为转移函数，$g(\mathbf{x})=\mathbf{y}$。由于 $\alpha=\beta \circ g$，故

$$
\begin{gather}
D\alpha(\mathbf{x})=D\beta(\mathbf{y})Dg(\mathbf{x})
\end{gather}
$$

则对任意 $\mathbf{v}\in \mathbb{R}^{n}$，有

$$
\begin{gather}
[\mathbf{v}\quad D\alpha(\mathbf{x})]=[\mathbf{v}\quad D\beta(\mathbf{y})]\begin{bmatrix}
1 & 0 \\
0 & Dg(\mathbf{x})
\end{bmatrix}
\end{gather}
$$

因此

$$
\begin{gather}
\det [\mathbf{v}\quad D\alpha(\mathbf{x})]=\det [\mathbf{v}\quad D\beta(\mathbf{y})] \det Dg(\mathbf{x})
\end{gather}
$$

由于 $\det Dg>0$，故 $\det[\mathbf{v}\quad D\alpha(\mathbf{x})]>0$ 当且仅当 $\det[\mathbf{v}\quad D\beta(\mathbf{y})]>0$。

要证 $N$ 是 $C^{\infty}$ 的，我们给出它的一个公式。要说明动机，我们首先看一个 $n=3$ 的特例。

### Example 38.3

给定 $\mathbf{a},\mathbf{b}\in \mathbb{R}^{3}$，我们在微积分中知道向量 $\mathbf{c}=\mathbf{a}\times \mathbf{b}$ 正交于 $\mathbf{a}$ 和 $\mathbf{b}$，标架 $(\mathbf{c},\mathbf{a},\mathbf{b})$ 是右手的，并且 $\lVert \mathbf{c} \rVert=V(\mathbf{a},\mathbf{b})$。这一向量 $\mathbf{c}$ 的各分量为

$$
\begin{gather}
c_{1}=\det \begin{bmatrix}
a_{2} & b_{2} \\
a_{3} & b_{3}
\end{bmatrix}, \quad c_{2}=-\det \begin{bmatrix}
a_{1} & b_{1} \\
a_{3} & b_{3}
\end{bmatrix}, \quad c_{3}=\det \begin{bmatrix}
a_{1} & b_{1} \\
a_{2} & b_{2}
\end{bmatrix}
\end{gather}
$$

于是，如果 $M$ 是 $\mathbb{R}^{3}$ 中的定向 $2$-流形，且 $\alpha\colon U\to V$ 是属于给定定向的坐标卡，并且我们令

$$
\begin{gather}
\mathbf{c}=\frac{ \partial \alpha }{ \partial x_{1} } \times \frac{ \partial \alpha }{ \partial x_{2} } 
\end{gather}
$$

则向量 $\mathbf{n}=\mathbf{c} /\lVert \mathbf{c} \rVert$ 给出了 $M$ 上的单位法向量。

![](8-1.png)

对于一般的 $\mathbf{n}$，我们有一个类似的公式。

### Lemma 38.4

给定线性无关的 $\mathbf{x}_{1},\dots,\mathbf{x}_{n-1}\in \mathbb{R}^{n}$，令 $X=[\mathbf{x}_{1}\cdots \mathbf{x}_{n-1}]$，并令 $\mathbf{c}=\sum c_{i}\mathbf{e}_{i}$，其中

$$
\begin{gather}
c_{i}=(-1)^{i-1}\det X(1,\dots,\hat{\imath},\dots,n)
\end{gather}
$$

这一向量 $\mathbf{c}$ 满足以下性质：

1. $\mathbf{c}\neq \mathbf{0}$ 且正交于每个 $\mathbf{x}_{i}$；
2. 标架 $(\mathbf{c},\mathbf{x}_{1},\dots,\mathbf{x}_{n-1})$ 是右手的；
3. $\lVert \mathbf{c} \rVert=V(X)$。

#### Proof

我们首先做一个预先的计算。任给 $\mathbf{a}\in \mathbb{R}^{n}$，我们计算行列式 $\det[\mathbf{a}\ \mathbf{x}_{1}\cdots \mathbf{x}_{n-1}]$。将其按第一列做余子式展开，我们得到

$$
\begin{align}
\det[\mathbf{a}\ \mathbf{x}_{1}\cdots \mathbf{x}_{n-1}] &= \sum_{i=1}^{n} a_{i} (-1)^{i-1}\det X(1,\dots,\hat{\imath},\dots,n) \\
&=\langle \mathbf{a},\mathbf{c} \rangle 
\end{align}
$$

这一公式包含了本定理中所有需要的信息。

(1) 令 $\mathbf{a}=\mathbf{x}_{i}$，则矩阵 $[\mathbf{a}\ \mathbf{x}_{1}\cdots \mathbf{x}_{n-1}]$ 有两列相同，故 $\langle \mathbf{x}_{i},\mathbf{c} \rangle=0$。要证 $\mathbf{c}\neq \mathbf{0}$，我们注意到由于 $X$ 有 $n-1$ 个线性无关的列，它也有 $n-1$ 个线性无关的行，不妨设为前 $n-1$ 行。则此时 $c_{n}$ 中涉及的行列式不为零，故 $\mathbf{c}\neq \mathbf{0}$。

(2) 令 $\mathbf{a}=\mathbf{c}$，于是

$$
\begin{gather}
\det[\mathbf{c}\ \mathbf{x}_{1}\cdots \mathbf{x}_{n}]=\langle \mathbf{c},\mathbf{c} \rangle =\lVert \mathbf{c} \rVert ^{2}>0
\end{gather}
$$

(3) 该性质由 [[5 Manifolds#Theorem 21.7]] 立即给出。等价地，我们计算

$$
\begin{gather}
[\mathbf{c}\ \mathbf{x}_{1}\cdots \mathbf{x}_{n-1}]^{T} [\mathbf{c}\ \mathbf{x}_{1}\cdots \mathbf{x}_{n-1}]=\begin{bmatrix}
\lVert c \rVert ^{2} & 0 \\
0 & X^{T}X
\end{bmatrix}
\end{gather}
$$

两边取行列式并应用 (2) 即得

$$
\begin{gather}
\lVert \mathbf{c} \rVert ^{4}=\lVert \mathbf{c} \rVert ^{2}V(X)^{2}
\end{gather}
$$

即证 $\lVert \mathbf{c} \rVert=V(X)$。

### Corollary 38.5

设 $M$ 是 $\mathbb{R}^{n}$ 中的定向 $n-1$ 流形，则其上属于给定定向的单位法向量场 $N(\mathbf{p})$ 是关于 $\mathbf{p}$ 的 $C^{\infty}$ 函数。

#### Proof

设 $\alpha\colon U\to V$ 是 $\mathbf{p}$ 处的坐标卡，令

$$
\begin{gather}
c_{i}(\mathbf{x})=(-1)^{i-1}\det D\alpha(1,\dots,\hat{\imath},\dots,n)(\mathbf{x})
\end{gather}
$$

并令 $\mathbf{c}(\mathbf{x})=\sum c_{i}(\mathbf{x})\mathbf{e}_{i}$。则对 $\mathbf{p}\in V$ 有

$$
\begin{gather}
N(\mathbf{p})=(\mathbf{p};\mathbf{c}(\mathbf{x}) /\lVert \mathbf{c}(\mathbf{x}) \rVert )
\end{gather}
$$

$\mathbf{x}=\alpha^{-1}(\mathbf{p})$ 是 $C^{\infty}$ 函数，$\mathbf{c}(\mathbf{x})$ 是关于 $\mathbf{x}$ 的 $C^{\infty}$ 函数，因此 $N(\mathbf{p})$ 是关于 $\mathbf{p}$ 的 $C^{\infty}$ 函数。

现在我们将 $n-1$ 形式用向量场来表示。如果 $G$ 是向量场，那么它通过 $\beta_{n-1}$ 线性同构于某个 $n-1$ 形式 $\omega$，见 [[6 Differential Forms#Theorem 31.2]]。事实表明，$\omega$ 在定向 $n-1$ 流形 $M$ 上的积分等于向量场 $G$ 的法向分量在 $M$ 上关于体积的积分。这就是如下引理的内容：

### Lemma 38.6

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致定向 $n-1$ 流形，令 $N$ 为对应的单位法向量场。令 $G$ 为定义在包含 $M$ 的开集上的向量场。我们用 $\mathbf{y}$ 来表示 $\mathbb{R}^{n}$ 中的任意点，则该向量场具有形式

$$
\begin{gather}
G(\mathbf{y})=(\mathbf{y};g(\mathbf{y}))=\left( \mathbf{y};\sum g_{i}(\mathbf{y})\mathbf{e}_{i} \right)
\end{gather}
$$

它对应于 $n-1$ 形式

$$
\begin{gather}
\omega=\sum_{i=1}^{n} (-1)^{i-1}g_{i} \, \mathrm{d}y_{1}\land\dots \land \widehat{\mathrm{d}y}_{i}\land\dots \land \mathrm{d}y_{n}
\end{gather}
$$

则

$$
\begin{gather}
\int_{M} \omega=\int_{M} \langle G,N \rangle \,\mathrm{d}V
\end{gather}
$$

注意到如果我们将 $M$ 替换为 $-M$，则积分 $\int_{M}\omega$ 改变符号。这一替换使得 $N$ 变成 $-N$，因此积分 $\int_{M}\langle G,N \rangle\,\mathrm{d}V$ 也改变符号。

#### Proof

根据 [[#Theorem 36.3]]，有

$$
\begin{gather}
\int_{M} \omega=\int_{M} \lambda\, \mathrm{d}V
\end{gather}
$$

其中 $\lambda(\mathbf{p})$ 是 $\omega(\mathbf{p})$ 在属于 $T_{\mathbf{p}}(M)$ 自然定向的标准正交基上的取值。我们要证 $\lambda=\langle G,N \rangle$。

设 $(\mathbf{p};\mathbf{a}_{1}),\dots,(\mathbf{p};\mathbf{a}_{n-1})$ 是属于自然定向的标准正交基。令 $A=[\mathbf{a}_{1}\cdots\mathbf{a}_{n-1}]$，并令 $\mathbf{c}=\sum c_{i}\mathbf{e}_{i}$，其中

$$
\begin{gather}
c_{i}=(-1)^{i-1}\det A(1,\dots,\hat{\imath},\dots,n)
\end{gather}
$$

则根据 [[#Lemma 38.4]]，$\mathbf{c}$ 正交于每个 $\mathbf{a}_{i}$，$(\mathbf{c},\mathbf{a}_{1},\dots,\mathbf{a}_{n-1})$ 是右手标架，且

$$
\begin{gather}
\lVert \mathbf{c} \rVert =V(A)=(\det A^{T}A)^{1/2}=1
\end{gather}
$$

则 $N=(\mathbf{p};\mathbf{c})$ 是属于 $M$ 的定向的单位法向量场。由于

$$
\begin{multline}
\mathrm{d}y_{1}\land\dots \land \widehat{\mathrm{d}y}_{i}\land\dots \land \mathrm{d}y_{n}(\mathbf{p})((\mathbf{p};\mathbf{a}_{1}),\dots,(\mathbf{p};\mathbf{a}_{n-1})) \\
=\det A(1,\dots,\hat{\imath},\dots,n)
\end{multline}
$$

因此

$$
\begin{align}
\lambda(\mathbf{p}) &= \sum_{i=1}^{n} (-1)^{i-1}g_{i}(\mathbf{p}) \det A(1,\dots,\hat{\imath},\dots,n) \\
&=\sum_{i=1}^{n} g_{i}(\mathbf{p})c_{i} \\
&= \langle G(\mathbf{p}),N(\mathbf{p}) \rangle 
\end{align}
$$

下面我们将 $n$-形式的积分解释为标量函数的积分。

### Lemma 38.7

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致 $n$-流形，取自然定向。设 $\omega=h\,\mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{n}$ 为定义在包含 $M$ 的开集上的 $n$-形式，则 $h$ 就是对应的标量场，且

$$
\begin{gather}
\int_{M} \omega=\int_{M} h\, \mathrm{d}V
\end{gather}
$$

#### Proof

我们有

$$
\begin{gather}
\int_{M} \omega=\int_{M} \lambda \,\mathrm{d}V
\end{gather}
$$

其中 $\lambda$ 是 $\omega$ 在属于 $T_{\mathbf{p}}(M)$ 自然定向的标准正交基上的取值。坐标卡 $\alpha$ 属于 $M$ 的定向当且仅当 $\det D\alpha>0$，因此 $T_{\mathbf{p}}(M)$ 的自然定向由右手标架构成。$T_{\mathbf{p}}(M)=T_{\mathbf{p}}(\mathbb{R}^{n})$ 上的标准基就是这样一个标架，$\omega(\mathbf{p})$ 在以上的值为 $h$。

我们指出积分 $\int_{M}h\,\mathrm{d}V$ 事实上等于 $h$ 在有界集 $M$ 上的普通积分。因为如果 $A=M\setminus \partial M$，则 $A$ 在 $\mathbb{R}^{n}$ 中开，并且恒等映射 $i\colon A\to A$ 是 $M$ 上的坐标卡，属于自然定向，并且覆盖了 $M$，除了一个零测集 $\partial M$。于是

$$
\begin{gather}
\int_{M} h\,\mathrm{d}V=\int_{A} (h\circ i)V(Di)=\int_{A} h
\end{gather}
$$

后者是一个普通积分，它等于 $\int_{M}h$ 因为 $\partial M$ 的测度为零。

接下来我们来研究取自然定向的 $n$-流形 $M$，它的边界 $\partial M$ 上的诱导定向是什么样的。在 [[#Example 34.12]] 中我们考虑了 $n=3$ 的情况，下面我们来给出一般的推广。

### Lemma 38.8

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $n$-流形。如果 $M$ 取自然定向，则 $\partial M$ 上的诱导定向所对应的单位法向量场 $N$ 在 $\partial M$ 的每一点处指向外法线方向。

$\partial M$ 在 $\mathbf{p}$ 处的内法线方向是一条从 $\mathbf{p}$ 进入 $M$ 内部的参数化曲线的速度向量的方向。它的外法线方向是内法线方向的反方向。

#### Proof

设 $\alpha\colon U\to V$ 是 $\mathbf{p}$ 处属于 $M$ 的定向的坐标卡。则 $\det D\alpha>0$。令 $b\colon \mathbb{R}^{n-1}\to \mathbb{R}^{n}$ 为

$$
\begin{gather}
b(x_{1},\dots,x_{n-1})=(x_{1},\dots,x_{n-1},0)
\end{gather}
$$

则 $\alpha_{0}=\alpha \circ b$ 是 $\mathbf{p}$ 处 $\partial M$ 上的坐标卡。它属于诱导定向如果 $n$ 是偶数，反之则属于诱导定向的反定向。令 $N$ 为对应于 $\partial M$ 的诱导定向的单位法向量场，$N(\mathbf{p})=(\mathbf{p};\mathbf{n}(\mathbf{p}))$，则

$$
\begin{gather}
\det[(-1)^{n}\mathbf{n}\quad D\alpha_{0}]>0
\end{gather}
$$

这表明

$$
\begin{gather}
\det[D\alpha_{0}\quad \mathbf{n}]=\det\left[ \frac{ \partial \alpha }{ \partial x_{1} } \quad \cdots\quad \frac{ \partial \alpha }{ \partial x_{n-1} } \quad \mathbf{n} \right]<0
\end{gather}
$$

另一方面，我们有

$$
\begin{gather}
\det D\alpha=\det\left[ \frac{ \partial \alpha }{ \partial x_{1} } \quad \cdots\quad \frac{ \partial \alpha }{ \partial x_{n-1} } \quad \frac{ \partial \alpha }{ \partial x_{n} }  \right]>0
\end{gather}
$$

而 $\partial\alpha /\partial x_{n}$ 在 $x_{n}$ 增加时从 $\mathbf{p}$ 进入 $M$ 的内部，因此它指向 $\partial M$ 的内法线方向。从而 $\mathbf{n}$ 指向 $\partial M$ 的外法线方向。

### Theorem 38.9 (散度定理)

设 $M$ 是 $\mathbb{R}^{n}$ 中的紧致 $n$-流形。令 $N$ 为 $\partial M$ 上指向外法线方向的单位法向量场。如果 $G$ 是定义在包含 $M$ 的开集上的向量场，那么

$$
\begin{gather}
\int_{M} (\operatorname{div}G)\,\mathrm{d}V=\int_{\partial M} \langle G,N \rangle \,\mathrm{d}V
\end{gather}
$$

其中左边是关于 $n$-体积的积分，右边是关于 $n-1$ 体积的积分。

当 $n=3$ 时，散度定理也称为 Gauss 定理。

#### Proof

给定 $G$，令 $\omega=\beta_{n-1}G$ 为与其同构的 $n-1$ 形式。取 $M$ 的自然定向并给予 $\partial M$ 诱导定向，则由 [[#Lemma 38.8]] 知 $N$ 对应于 $\partial M$ 的诱导定向。因此根据 [[#Lemma 38.6]]，

$$
\begin{gather}
\int_{\partial M} \omega=\int_{\partial M}\langle G,N \rangle \,\mathrm{d}V
\end{gather}
$$

再根据 [[6 Differential Forms#Theorem 31.2]]，标量场 $\operatorname{div}G$ 同构于 $n$-形式 $\mathrm{d}\omega=(\operatorname{div}G)\,\mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{n}$，于是

$$
\begin{gather}
\int_{M} \mathrm{d}\omega=\int_{M} (\operatorname{div}G)\,\mathrm{d}V
\end{gather}
$$

应用 Stokes 定理即证。

## Stokes' Theorem for 2-Manifolds in $\mathbb{R}^{3}$

还有最后一种情况，其中我们可以将广义 Stokes 定理转化为向量场积分的定理。它发生在 $M$ 是 $\mathbb{R}^{3}$ 中的定向 $2$-流形时。

### Theorem 38.10 (Stokes)

设 $M$ 是 $\mathbb{R}^{3}$ 中的紧致可定向 $2$-流形，$N$ 为 $M$ 上的单位法向量场。令 $F$ 为定义在包含 $M$ 的开集上的 $C^{\infty}$ 向量场。如果 $\partial M=\varnothing$，那么

$$
\begin{gather}
\int_{M} \langle \operatorname{curl}F,N \rangle \,\mathrm{d}S=0
\end{gather}
$$

如果 $\partial M\neq \varnothing$，令 $T$ 为 $\partial M$ 上的单位切向量场，使得定义为 $W(\mathbf{p})=N(\mathbf{p})\times T(\mathbf{p})$ 的向量从 $\partial M$ 指向 $M$ 的内部。则

$$
\begin{gather}
\int_{M} \langle \operatorname{curl}F,N \rangle \,\mathrm{d}S=\int_{\partial M} \langle F,T \rangle \,\mathrm{d}s
\end{gather}
$$

其中我们用 $\mathrm{d}S$ 来表示关于 $2$-体积，即面积的积分。

#### Proof

给定 $F$，令 $\omega=\alpha_{1}F$ 为与其同构的 $1$-形式。根据 [[6 Differential Forms#Theorem 31.4]]，向量场 $\operatorname{curl}F$ 同构于 $2$-形式 $\mathrm{d}\omega$。给予 $M$ 定向使得 $N$ 为对应于给定定向的单位法向量场。则

$$
\begin{gather}
\int_{M} \mathrm{d}\omega=\int_{M} \langle \operatorname{curl}F,N \rangle \,\mathrm{d}S
\end{gather}
$$

另一方面，如果 $\partial M\neq \varnothing$，那么它的诱导定向对应于单位切向量场 $T$，见 [[#Example 34.13]]。于是

$$
\begin{gather}
\int_{\partial M} \omega=\int_{\partial M} \langle F,T \rangle \,\mathrm{d}s
\end{gather}
$$

应用广义 Stokes 定理即证。