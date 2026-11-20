本章我们考虑 $\mathbb{R}^{m}$ 到 $\mathbb{R}^{n}$ 的函数，并定义我们所谓的向量值函数的导数。本章的两个主要结果是反函数定理与隐函数定理，前者给出了 $\mathbb{R}^{n}$ 上的可微函数有可微导数的条件，后者给出了隐函数求导法的理论保证。

# 5 The Derivative

首先我们回顾一下一元函数导数的定义。

设 $A\subset \mathbb{R}$，$\phi\colon A\to \mathbb{R}$。假设 $A$ 包含 $a$ 的一个邻域，我们定义 $\phi$ 在 $a$ 处的导数为

$$
\begin{gather}
\phi'(a)=\lim_{ t \to 0 } \frac{\phi(a+t)-\phi(a)}{t}
\end{gather}
$$

如果右侧的极限存在。在那种情况下，我们称 $\phi$ 在 $a$ 处可微。我们有如下事实：

1. 可微函数是连续的。
2. 可微函数的复合仍是可微函数。

现在我们希望为 $f\colon A(\subset \mathbb{R}^{m})\to \mathbb{R}^{n}$ 定义导数。我们不能在上面的定义中直接将 $a$ 和 $t$ 替换为 $\mathbb{R}^{m}$ 中的元素，因为我们不能除以一个 $\mathbb{R}^{m}(m>1)$ 的元素。为此，下面我们做出第一个尝试。

### Definition 5.1 directional derivative 方向导数

设 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}^{n}$。假设 $A$ 包含 $\mathbf{a}$ 的一个邻域，给定 $\mathbf{u}\in \mathbb{R}^{m},\mathbf{u}\neq \mathbf{0}$，定义

$$
\begin{gather}
f'(\mathbf{a};\mathbf{u})=\lim_{ t \to 0 } \frac{f(\mathbf{a}+t\mathbf{u})-f(\mathbf{a})}{t}
\end{gather}
$$

如果右侧的极限存在。它被称为 $f$ 在 $\mathbf{a}$ 处关于 $\mathbf{u}$ 的方向导数。

看上去一个合理的可微性定义是对任意 $\mathbf{u}\neq \mathbf{0}$，方向导数 $f'(\mathbf{a};\mathbf{u})$ 都存在。然而，事实证明这并不是一个良好的可微性定义，因为它不满足上面列出的性质 (1)。因此我们需要一个更强的条件。

要说明可微性定义的动机，我们先来重述一下一元函数导数的定义：$\phi\colon A\to \mathbb{R}$ 在 $a$ 处可微当且仅当存在 $\lambda$ 使得

$$
\begin{gather}
\lim_{ t \to 0 } \frac{\phi(a+t)-\phi(a)-\lambda t}{t}=0
\end{gather}
$$

这唯一的 $\lambda$ 就称为 $\phi$ 在 $a$ 处的导数。

从上面的定义可知，如果 $\phi$ 可微，那么当 $t\to 0$ 时，$\lambda t$ 是 $\Delta \phi=\phi(a+t)-\phi(a)$ 的一个良好近似。我们称 $\lambda t$ 为 $\Delta \phi$ 的一阶近似或线性近似。

下面我们来推广这个定义。如果 $A\subset \mathbb{R}^{m}$ 且 $f\colon A\to \mathbb{R}^{n}$，那么 $f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})$ 的线性近似是什么呢？一个自然的选择是取线性代数意义上的“线性”，这一思想引出了如下定义。

### Definition 5.2 differentiable 可微的

设 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}^{n}$，假设 $A$ 包含 $\mathbf{a}$ 的一个邻域。我们称 $f$ 在 $\mathbf{a}$ 处可微，如果存在 $n\times m$ 矩阵（线性变换）$B$ 使得

$$
\begin{gather}
\lim_{ \mathbf{h} \to \mathbf{0} } \frac{f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})-B\mathbf{h}}{\lvert \mathbf{h} \rvert }=\mathbf{0}
\end{gather}
$$

这唯一的矩阵（线性变换）$B$ 称为 $f$ 在 $\mathbf{a}$ 处的导数，记作 $Df(\mathbf{a})$。

等价地，我们可以将上述定义中的上确界范数 $\lvert \mathbf{h} \rvert$ 替换为 Euclidean 范数 $\lVert \mathbf{h} \rVert$。

容易证明 $B$ 是唯一的。如果矩阵 $C$ 也满足导数的定义，那么

$$
\begin{gather}
\frac{(C-B)\mathbf{h}}{\lvert \mathbf{h} \rvert } \to \mathbf{0} \quad (\mathbf{h}\to \mathbf{0})
\end{gather}
$$

固定 $\mathbf{u}\neq \mathbf{0}$，令 $\mathbf{h}=t\mathbf{u}$，则当 $t\to 0$ 时有 $(C-B)\mathbf{u}=\mathbf{0}$。由于 $\mathbf{u}$ 是任意的，故 $C=B$。

### Example 5.3

定义 $f\colon \mathbb{R}^{m}\to \mathbb{R}^{n}$ 为

$$
\begin{gather}
f(\mathbf{x})=B\mathbf{x}+\mathbf{b}
\end{gather}
$$

则 $f$ 是可微函数且 $Df(\mathbf{x})=B$。这是因为

$$
\begin{gather}
f(\mathbf{x}+\mathbf{h})-f(\mathbf{x})=B\mathbf{h}
\end{gather}
$$

这一公式是一元微积分中 $f(x)=ax+b$ 的导数是 $f'(x)=a$ 的推广。

下面我们证明 [[#Definition 5.2 differentiable 可微的]] 是一个更强的条件，并且满足以下的性质：

1. 可微函数是连续的。
2. 可微函数的复合是可微函数。
3. $f$ 在 $\mathbf{a}$ 处的可微性蕴含 $f$ 在 $\mathbf{a}$ 处任意方向导数的存在性。

### Theorem 5.4

设 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}^{n}$。如果 $f$ 在 $\mathbf{a}$ 处可微，则 $f$ 在 $\mathbf{a}$ 处的所有方向导数都存在，并且对 $\mathbf{u}\neq \mathbf{0}$ 有

$$
\begin{gather}
f'(\mathbf{a};\mathbf{u})=Df(\mathbf{a})\mathbf{u}
\end{gather}
$$

#### Proof

设 $B=Df(\mathbf{a})$。在可微性的定义中令 $\mathbf{h}=t\mathbf{u}$，则当 $t\to 0$ 时有

$$
\begin{gather}
\frac{f(\mathbf{a}+t\mathbf{u})-f(\mathbf{a})-B(t\mathbf{u})}{\lvert t\mathbf{u} \rvert } \to \mathbf{0}
\end{gather}
$$

令 $t$ 沿着正数趋于 $0$，并在上式两边乘以 $\lvert \mathbf{u} \rvert$，我们就有

$$
\begin{gather}
\frac{f(\mathbf{a}+t\mathbf{u})-f(\mathbf{a})}{t}-B\mathbf{u} \to \mathbf{0}
\end{gather}
$$

如果 $t$ 沿着负数趋于 $0$，那么我们在两边乘以 $-\lvert \mathbf{u} \rvert$，得到同样的结论，即证 $f'(\mathbf{a};\mathbf{u})=B\mathbf{u}$。

### Theorem 5.5

设 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}^{n}$。如果 $f$ 在 $\mathbf{a}$ 处可微，那么 $f$ 在 $\mathbf{a}$ 处连续。

#### Proof

设 $B=Df(\mathbf{a})$。在 $\mathbf{h}\to \mathbf{0}$ 时，我们有

$$
\begin{gather}
f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})=\lvert \mathbf{h} \rvert \cdot \frac{f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})-B\mathbf{h}}{\lvert \mathbf{h} \rvert }+B\mathbf{h} \to \mathbf{0}
\end{gather}
$$

即 $f(\mathbf{a}+\mathbf{h})\to f(\mathbf{a})$，即 $f$ 在 $\mathbf{a}$ 处连续。

下面我们来展示当 $Df(\mathbf{a})$ 存在时如何来计算它。

### Definition 5.6 partial derivative 偏导数

设 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}^{n}$。我们定义 $f$ 在 $\mathbf{a}$ 处的第 $j$ 个偏导数为 $f$ 在 $\mathbf{a}$ 处关于第 $j$ 个标准基向量 $\mathbf{e}_{j}$ 的方向导数，记作 $D_{j}f(\mathbf{a})$。具体来说，

$$
\begin{gather}
D_{j}f(\mathbf{a})=\lim_{ t \to 0 } \frac{f(\mathbf{a}+t\mathbf{e}_{j})-f(\mathbf{a})}{t}
\end{gather}
$$

如果右侧的极限存在。

偏导数非常容易计算：我们设

$$
\begin{gather}
\phi(t)=f(a_{1},\dots,a_{j-1},t,a_{j+1},\dots,a_{n})
\end{gather}
$$

则 $f$ 在 $\mathbf{a}$ 处的第 $j$ 个偏导数就等于 $\phi$ 在 $t=a_{j}$ 处的普通导数。这就是说，要计算 $D_{j}f(\mathbf{x})$，我们只需将 $x_{1},\dots,x_{j-1},x_{j+1},\dots,x_{m}$ 视为常数，然后对 $x_{j}$ 求普通导数即可。

### Theorem 5.7

设 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}$，如果 $f$ 在 $\mathbf{a}$ 处可微，则

$$
\begin{gather}
Df(\mathbf{a})=\begin{bmatrix}
D_{1}f(\mathbf{a}) & \cdots & D_{m}f(\mathbf{a})
\end{bmatrix}
\end{gather}
$$

#### Proof

根据可微性的定义，$Df(\mathbf{a})$ 是一个 $1\times m$ 矩阵，设其为

$$
\begin{gather}
Df(\mathbf{a})=[\lambda_{1} \cdots \lambda_{m}]
\end{gather}
$$

则 [[#Theorem 5.4]] 给出

$$
\begin{gather}
D_{j}f(\mathbf{a})=Df(\mathbf{a})\mathbf{e}_{j}=\lambda_{j}
\end{gather}
$$

这就完成了证明。

我们将以上定理推广如下。

### Theorem 5.8

设 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}^{n}$，假设 $A$ 包含 $\mathbf{a}$ 的一个邻域。令 $f_{i}\colon A\to \mathbb{R}$ 为 $f$ 的第 $i$ 个分量函数，使得

$$
\begin{gather}
f(\mathbf{x})=\begin{bmatrix}
f_{1}(\mathbf{x}) \\
\vdots \\
f_{n}(\mathbf{x})
\end{bmatrix}
\end{gather}
$$

我们有以下命题成立：

(a) $f$ 在 $\mathbf{a}$ 处可微当且仅当每个分量 $f_{i}$ 在 $\mathbf{a}$ 处可微。
(b) 如果 $f$ 在 $\mathbf{a}$ 处可微，那么 $Df(\mathbf{a})$ 是一个 $n\times m$ 矩阵，其第 $i$ 行为 $f_{i}$ 的导数。具体来说，

$$
\begin{gather}
Df(\mathbf{a})=\begin{bmatrix}
Df_{1}(\mathbf{a}) \\
\vdots \\
Df_{n}(\mathbf{a})
\end{bmatrix}
\end{gather}
$$

因此 $Df(\mathbf{a})$ 的 $(i,j)$ 元素为 $D_{j}f_{i}(\mathbf{a})$。

#### Proof

设 $B$ 是任意 $n\times m$ 矩阵，考虑定义在 $\mathbf{0}$ 的邻域上的函数

$$
\begin{gather}
F(\mathbf{h})=\frac{f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})-B\mathbf{h}}{\lvert \mathbf{h} \rvert }
\end{gather}
$$

$F(\mathbf{h})$ 是一个 $n\times 1$ 列向量，它的第 $i$ 个坐标为

$$
\begin{gather}
F_{i}(\mathbf{h})=\frac{f_{i}(\mathbf{a}+\mathbf{h})-f_{i}(\mathbf{a})-B_{i,\cdot}\mathbf{h}}{\lvert \mathbf{h} \rvert }
\end{gather}
$$

其中 $B_{i,\cdot}$ 为 $B$ 的第 $i$ 行。令 $\mathbf{h}\to \mathbf{0}$，则 $F(\mathbf{h})$ 趋于 $\mathbf{0}$ 当且仅当每个元素 $F_{i}(\mathbf{h})$ 趋于 $0$，因此如果 $B$ 是一个矩阵使得 $F(\mathbf{h})\to \mathbf{0}$，那么 $B$ 的第 $i$ 行就是一个行向量使得 $F_{i}(\mathbf{h})\to 0$，即 $B_{i,\cdot}=Df_{i}(\mathbf{a})$。反之亦然。这就完成了证明。

设 $f\colon A(\subset \mathbb{R}^{m})\to \mathbb{R}^{n}$。如果 $f$ 的各分量 $f_{i}$ 在 $\mathbf{a}$ 处的偏导数都存在，那么我们可以构造矩阵使得其 $(i,j)$ 元素为 $D_{j}f_{i}(\mathbf{a})$，它称为 $f$ 的 Jacobian 矩阵。[[#Theorem 5.8]] 表明了，如果 $f$ 在 $\mathbf{a}$ 处可微，那么 $Df(\mathbf{a})$ 就等于 $f$ 的 Jacobian 矩阵。然而，即使 $f$ 在 $\mathbf{a}$ 处不可微，它的 Jacobian 矩阵仍然可以存在。

### Remark 5.9

如果 $m=1$ 或 $n=1$，那么我们的导数定义就是对微积分中熟悉概念的一种重述。例如，如果 $f\colon \mathbb{R}\to \mathbb{R}^{3}$ 是可微函数，则它的矩阵就是列向量

$$
\begin{gather}
Df(t)=\begin{bmatrix}
f_{1}'(t) \\
f_{2}'(t) \\
f_{3}'(t)
\end{bmatrix}
\end{gather}
$$

$f$ 通常被视为一条参数曲线，而它的导数正是速度向量

$$
\begin{gather}
\mathbf{v}=f_{1}'(t)\mathbf{e}_{1}+f_{2}'(t)\mathbf{e}_{2}+f_{3}'(t)\mathbf{e}_{3}
\end{gather}
$$

又如，设 $g\colon \mathbb{R}^{3}\to \mathbb{R}$ 可微，它的导数是行向量

$$
\begin{gather}
Dg(\mathbf{x})=\begin{bmatrix}
D_{1}g(\mathbf{x}) & D_{2}g(\mathbf{x}) & D_{3}g(\mathbf{x})
\end{bmatrix}
\end{gather}
$$

而 $g$ 的方向导数等于 $Dg(\mathbf{x})\mathbf{u}$。在微积分中，$g$ 被视为一个标量场，而

$$
\begin{gather}
\operatorname{grad}g=(D_{1}g)\mathbf{e}_{1}+(D_{2}g)\mathbf{e}_{2}+(D_{3}g)\mathbf{e}_{3}
\end{gather}
$$

称为 $g$ 的梯度向量。$g$ 关于 $u$ 的方向导数则写成 $\operatorname{grad}g$ 与 $\mathbf{u}$ 的点积。

# 6 Continuously Differentiable Functions

本节我们给出可微性的一个充分条件。我们知道，偏导数的存在性无法推出函数的可微性。然而，如果我们假设偏导数是连续的，那么我们就能保证函数可微。

我们以一元函数的中值定理作为起点。

### Theorem 6.1 (中值定理)

设 $\phi\colon[a,b]\to \mathbb{R}$ 在 $[a,b]$ 上连续，且在 $(a,b)$ 上可微，则存在 $c \in(a,b)$ 使得

$$
\begin{gather}
\phi(b)-\phi(a)=\phi'(c)(b-a)
\end{gather}
$$

### Theorem 6.2

设开集 $A\subset \mathbb{R}^{m}$，并假设偏导数 $D_{j}f_{i}$ 在 $A$ 上存在且连续，则 $f$ 在 $A$ 上可微。

满足以上定理条件的函数称为在 $A$ 上是连续可微的，或者说是 $C^{1}$ 函数。

#### Proof

根据 [[#Theorem 5.8]]，我们只需证明每个分量 $f_{i}$ 是可微的，因此我们可以不失一般性地假设 $f\colon A\to \mathbb{R}$。

设 $\mathbf{a}\in A$，我们可以选取一个 $\varepsilon>0$ 使得 $D_{j}f(\mathbf{x})$ 在 $\lvert \mathbf{x}-\mathbf{a} \rvert<\varepsilon$ 上连续，我们要证 $f$ 在 $\mathbf{a}$ 处可微。

**第一步**

令 $\mathbf{h} \in \mathbb{R}^{m}$ 满足 $0<\lvert \mathbf{h} \rvert<\varepsilon$，$h_{1},\dots,h_{m}$ 为 $\mathbf{h}$ 的分量。考虑 $\mathbb{R}^{m}$ 中的如下点：

$$
\begin{align}
\mathbf{p}_{0}&=\mathbf{a} \\
\mathbf{p}_{1}&=\mathbf{a}+h_{1}\mathbf{e}_{1} \\
\mathbf{p}_{2}&=\mathbf{a}+h_{1}\mathbf{e}_{1}+h_{2}\mathbf{e}_{2} \\
\vdots \\
\mathbf{p}_{m}&=\mathbf{a}+h_{1}\mathbf{e}_{1}+\dots+h_{m}\mathbf{e}_{m}
\end{align}
$$

这些点都位于以 $\mathbf{a}$ 为中心，半径为 $\lvert \mathbf{h} \rvert$ 的立方体的顶点上。

由于我们要考虑 $f$ 的可微性，因此我们需要研究 $f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})$，我们将其分解为

$$
\begin{gather}
f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})=\sum_{j=1}^{m} (f(\mathbf{p}_{j})-f(\mathbf{p}_{j-1}))
\end{gather}
$$

对求和中的每一项，考虑相关的函数

$$
\begin{gather}
\phi(t)=f(\mathbf{p}_{j-1}+t\mathbf{e}_{j})
\end{gather}
$$

假设 $h_{j}\neq 0$，当 $t$ 从 $0$ 变化到 $h_{j}$ 时，$\mathbf{p}_{j-1}+t\mathbf{e}_{j}$ 从 $\mathbf{p}_{j-1}$ 连接到 $\mathbf{p}_{j}$。由于在这一过程中只有第 $j$ 个变量在变化，并且 $D_{j}f$ 在 $A$ 上连续，根据中值定理，存在 $c_{j}$ 介于 $0$ 和 $h_{j}$ 之间，使得

$$
\begin{gather}
f(\mathbf{p}_{j})-f(\mathbf{p}_{j-1})=\phi(h_{j})-\phi(0)=\phi'(c_{j})h_{j}=D_{j}f(\mathbf{q}_{j})h_{j}
\end{gather}
$$

其中 $\mathbf{q}_{j}=\mathbf{p}_{j-1}+c_{j}\mathbf{e}_{j}$。如果 $h_{j}=0$，那么以上等式是平凡的，因此我们可以去掉 $h_{j}\neq 0$ 的假设。

于是，我们有

$$
\begin{gather}
f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})=\sum_{j=1}^{m} D_{j}f(\mathbf{q}_{j})h_{j}
\end{gather}
$$

其中每个点 $\mathbf{q}_{j}$ 都落在以 $\mathbf{a}$ 为中心，$\lvert \mathbf{h} \rvert$ 为半径的立方体上。

**第二步**

设 $B$ 为 $f$ 的 Jacobian 矩阵

$$
\begin{gather}
B=\begin{bmatrix}
D_{1}f(\mathbf{a}) & \cdots & D_{m}f(\mathbf{a})
\end{bmatrix}
\end{gather}
$$

则我们有

$$
\begin{gather}
\frac{f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})-B\mathbf{h}}{\lvert \mathbf{h} \rvert }=\sum_{j=1}^{m} \frac{(D_{j}f(\mathbf{q}_{j})-D_{j}f(\mathbf{a}))h_{j}}{\lvert \mathbf{h} \rvert }
\end{gather}
$$

当 $\mathbf{h}\to \mathbf{0}$ 时，有 $\mathbf{q}_{j}\to \mathbf{a}$，于是我们就有上式趋于 $\mathbf{0}$。即证 $Df(\mathbf{a})=B$。

设 $f$ 是从开集 $A\subset \mathbb{R}^{m}$ 到 $\mathbb{R}^{n}$ 的函数，并假设偏导数 $D_{j}f_{i}$ 在 $A$ 上存在。这些都是从 $A$ 到 $\mathbb{R}$ 的函数，而我们也可以考虑它们各自的偏导数，其具有形式 $D_{k}D_{j}f_{i}$，称为 $f$ 的二阶偏导数。更一般地，我们也可以考虑 $f$ 的 $r$ 阶偏导数。

如果 $f$ 的小于等于 $r$ 阶的偏导数在 $A$ 上都连续，我们就称 $f$ 在 $A$ 上是 $C^{r}$ 函数。根据定义，$f$ 在 $A$ 上是 $C^{r}$ 函数当且仅当每个 $D_{j}f_{i}$ 在 $A$ 上是 $C^{r-1}$ 函数。我们称 $f$ 是光滑的，或者说是 $C^{\infty}$ 函数，如果 $f$ 的任意阶偏导数都连续。

### Theorem 6.3 (Clairaut)

设开集 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}$ 是 $C^{2}$ 函数，则对任意 $\mathbf{a}\in A$ 有

$$
\begin{gather}
D_{k}D_{j}f(\mathbf{a})=D_{j}D_{k}f(\mathbf{a})
\end{gather}
$$

#### Proof

由于定理中只有变量 $x_{j}$ 和 $x_{k}$ 在变化，其余变量都保持固定，因此我们不妨设 $f$ 是一个双变量函数，其中 $A\subset \mathbb{R}^{2}$ 且 $f\colon A\to \mathbb{R}$ 是 $C^{2}$ 函数。

**第一步** 我们首先证明一个“二维中值定理”。

令

$$
\begin{gather}
Q=[a,a+h]\times[b,b+k]
\end{gather}
$$

为 $A$ 中的长方体，定义

$$
\begin{gather}
\lambda(h,k)=f(a+h,b+k)-f(a+h,b)-f(a,b+k)+f(a,b)
\end{gather}
$$

即 $\lambda$ 是 $f$ 在长方体 $Q$ 的四个顶点上的取值之和（带有适当的符号）。我们要证存在 $\mathbf{p},\mathbf{q}\in Q$ 使得下面两个等式成立：

$$
\begin{gather}
\lambda(h,k)=D_{2}D_{1}f(\mathbf{p}) hk, \quad \lambda(h,k)=D_{1}D_{2}f(\mathbf{q}) hk
\end{gather}
$$

根据对称性，我们只需证明第一个等式即可。

定义

$$
\begin{gather}
\phi(s)=f(s,b+k)-f(s,b)
\end{gather}
$$

则 $\lambda(h,k)=\phi(a+h)-\phi(a)$。由于 $D_{1}f$ 在 $A$ 上存在，故根据一元中值定理，存在 $s_{0}$ 介于 $a$ 和 $a+h$ 之间使得

$$
\begin{gather}
\lambda(h,k)=\phi(a+h)-\phi(a)=\phi'(s_{0})h=(D_{1}f(s_{0},b+k)-D_{1}f(s_{0},b))h
\end{gather}
$$

又由于 $D_{2}D_{1}f$ 在 $A$ 上存在，故存在 $t_{0}$ 介于 $b$ 和 $b+k$ 之间使得

$$
\begin{gather}
D_{1}f(s_{0},b+k)-D_{1}f(s_{0},b)=D_{2}D_{1}f(s_{0},t_{0})k
\end{gather}
$$

代入上式即得 $\lambda(h,k)=D_{2}D_{1}f(s_{0},t_{0})hk$。

**第二步** 我们证明本定理。

给定 $\mathbf{a}=(a,b)\in A$，考虑长方体

$$
\begin{gather}
Q=[a,a+t]\times[b,b+t]
\end{gather}
$$

当 $t$ 足够小时，$Q\subset A$，从而存在 $\mathbf{p}\in Q$ 使得

$$
\begin{gather}
\lambda(t,t)=D_{2}D_{1}f(\mathbf{p})t^{2}
\end{gather}
$$

令 $t\to 0$，则 $\mathbf{p}\to \mathbf{a}$，由于 $D_{2}D_{1}f$ 连续，故

$$
\begin{gather}
\frac{\lambda(t,t)}{t^{2}} \to D_{2}D_{1}f(\mathbf{a})
\end{gather}
$$

同理我们也有

$$
\begin{gather}
\frac{\lambda(t,t)}{t^{2}} \to D_{1}D_{2}f(\mathbf{a})
\end{gather}
$$

这就完成了证明。

# 7 The Chain Rule

本节我们证明可微函数的复合也是可微函数，并推导出复合函数的导数公式。这一公式通常称为“链式法则”。

### Theorem 7.1 (链式法则)

设 $A\subset \mathbb{R}^{m},B\subset \mathbb{R}^{n}$，令

$$
\begin{gather}
f\colon A\to \mathbb{R}^{n}, \quad g\colon B\to \mathbb{R}^{p}
\end{gather}
$$

满足 $f(A)\subset B$。假设 $f(\mathbf{a})=\mathbf{b}$。如果 $f$ 在 $\mathbf{a}$ 处可微，$g$ 在 $\mathbf{b}$ 处可微，则复合函数 $g\circ f$ 在 $\mathbf{a}$ 处可微，且

$$
\begin{gather}
D(g\circ f)(\mathbf{a})=Dg(\mathbf{b}) Df(\mathbf{a})
\end{gather}
$$

#### Proof

设 $\mathbf{x}$ 表示 $\mathbb{R}^{m}$ 中的点，$\mathbf{y}$ 表示 $\mathbb{R}^{n}$ 中的点。

根据假设，$g$ 在 $\mathbf{b}$ 的邻域上有定义，取 $\varepsilon$ 使得 $g(\mathbf{y})$ 在 $\lvert \mathbf{y}-\mathbf{b} \rvert<\varepsilon$ 时有定义。类似地，由于 $f$ 在 $\mathbf{a}$ 处连续，取 $\delta$ 使得 $f(\mathbf{x})$ 在 $\lvert \mathbf{x}-\mathbf{a} \rvert<\delta$ 时有定义并满足 $\lvert f(\mathbf{x})-\mathbf{b} \rvert<\varepsilon$。则复合函数 $g\circ f(\mathbf{x})$ 在 $\lvert \mathbf{x}-\mathbf{a} \rvert<\delta$ 时有定义。

![](2-1.png)

**第一步**

令

$$
\begin{gather}
\Delta(\mathbf{h})=f(\mathbf{a}+\mathbf{h})-f(\mathbf{a}) \quad (\lvert \mathbf{h} \rvert <\delta)
\end{gather}
$$

我们来证明 $\lvert \Delta(\mathbf{h}) \rvert /\lvert \mathbf{h} \rvert$ 在 $\mathbf{0}$ 的去心邻域中有界。

定义 $F(\mathbf{h})$ 为 $F(\mathbf{0})=\mathbf{0}$ 且

$$
\begin{gather}
F(\mathbf{h})=\frac{\Delta(\mathbf{h})-Df(\mathbf{a})\mathbf{h}}{\lvert \mathbf{h} \rvert } \quad (0<\lvert \mathbf{h} \rvert <\delta)
\end{gather}
$$

由于 $f$ 在 $\mathbf{a}$ 处可微，故 $F$ 在 $\mathbf{a}$ 处连续，并且

$$
\begin{gather}
\Delta(\mathbf{h})=Df(\mathbf{a})\mathbf{h}+\lvert \mathbf{h} \rvert F(\mathbf{h}) \tag{$\ast$}
\end{gather}
$$

这给出

$$
\begin{gather}
\lvert \Delta(\mathbf{h}) \rvert \leq m \lvert Df(\mathbf{a}) \rvert \lvert \mathbf{h} \rvert +\lvert \mathbf{h} \rvert \lvert F(\mathbf{h}) \rvert 
\end{gather}
$$

因而 $\lvert \Delta(\mathbf{h}) \rvert /\lvert \mathbf{h} \rvert$ 在 $0<\lvert \mathbf{h} \rvert<\delta$ 时有界。

**第二步**

我们对函数 $g$ 重复第一步的论证。定义 $G(\mathbf{k})$ 为 $G(\mathbf{0})=\mathbf{0}$，而

$$
\begin{gather}
G(\mathbf{k})=\frac{g(\mathbf{b}+\mathbf{k})-g(\mathbf{b})-Dg(\mathbf{b})\mathbf{k}}{\lvert \mathbf{k} \rvert } \quad (0<\lvert \mathbf{k} \rvert <\varepsilon)
\end{gather}
$$

由于 $g$ 在 $\mathbf{b}$ 处可微，$G$ 在 $\mathbf{0}$ 处连续。此外，我们还有

$$
\begin{gather}
g(\mathbf{b}+\mathbf{k})-g(\mathbf{b})=Dg(\mathbf{b})\mathbf{k}+\lvert \mathbf{k} \rvert G(\mathbf{k}) \tag{$\ast\ast$}
\end{gather}
$$

**第三步**

取 $\mathbf{h}\in \mathbb{R}^{m}$ 满足 $\lvert \mathbf{h} \rvert<\delta$，则 $\lvert \Delta(\mathbf{h}) \rvert<\varepsilon$，因此我们可以在 $(\ast\ast)$ 中用 $\Delta(\mathbf{h})$ 替换 $\mathbf{k}$。此时我们有

$$
\begin{gather}
\mathbf{b}+\Delta(\mathbf{h})=f(\mathbf{a})+(f(\mathbf{a}+\mathbf{h})-f(\mathbf{a}))=f(\mathbf{a}+\mathbf{h})
\end{gather}
$$

于是

$$
\begin{gather}
g(f(\mathbf{a}+\mathbf{h}))-g(f(\mathbf{a}))=Dg(\mathbf{b})\Delta(\mathbf{h})+\lvert \Delta(\mathbf{h}) \rvert G(\Delta(\mathbf{h}))
\end{gather}
$$

代入 $(\ast)$ 的公式，我们有

$$
\begin{multline}
\frac{1}{\lvert \mathbf{h} \rvert }(g(f(\mathbf{a}+\mathbf{h}))-g(f(\mathbf{a}))-Dg(\mathbf{b})Df(\mathbf{a})\mathbf{h}) \\
=Dg(\mathbf{b})F(\mathbf{h})+\frac{1}{\lvert \mathbf{h} \rvert }(\lvert \Delta (\mathbf{h}) \rvert G(\Delta(\mathbf{h})))
\end{multline}
$$

令 $\mathbf{h}\to \mathbf{0}$，则 $\Delta(\mathbf{h})\to \mathbf{0}$。$F,G$ 在 $\mathbf{0}$ 处连续，故它们都趋于 $\mathbf{0}$。$Dg(\mathbf{b})$ 是常量，而 $\lvert \Delta(\mathbf{h}) \rvert /\lvert \mathbf{h} \rvert$ 有界。这就完成了证明。

### Corollary 7.2

设 $A\subset \mathbb{R}^{m}$ 和 $B\subset \mathbb{R}^{n}$ 是开集，令

$$
\begin{gather}
f\colon A\to \mathbb{R}^{n}, \quad g\colon B\to \mathbb{R}^{p}
\end{gather}
$$

满足 $f(A)\subset B$。如果 $f,g$ 是 $C^{r}$ 函数（$r$ 是正整数或 $\infty$），那么复合函数 $g\circ f$ 也是 $C^{r}$ 函数。

#### Proof

链式法则给出了公式

$$
\begin{gather}
D(g\circ f)(\mathbf{x})=Dg(f(\mathbf{x}))Df(\mathbf{x})
\end{gather}
$$

我们用归纳法。首先设 $f,g$ 是 $C^{1}$ 函数，则 $Dg$ 和 $Df$ 的各项都是连续函数。又因为 $f$ 也是连续的，故 $Dg(f(\mathbf{x}))$ 的各项也是连续的。这就表明 $Dg(f(\mathbf{x}))Df(\mathbf{x})$ 的各项连续，从而 $g\circ f$ 是 $C^{1}$ 函数。

现在假设定理对 $C^{r-1}$ 函数成立。设 $f,g$ 是 $C^{r}$ 函数，则 $Dg$ 和 $Df$ 的各项是 $C^{r-1}$ 函数。由于 $f$ 是 $C^{r-1}$ 函数，因此归纳假设表明 $Dg(f(\mathbf{x}))$ 的各项，作为两个 $C^{r-1}$ 函数的复合，是 $C^{r-1}$ 函数。从而 $Dg(f(\mathbf{x}))Df(\mathbf{x})$ 的各项是 $C^{r-1}$ 函数，因此 $g\circ f$ 是 $C^{r}$ 函数。

最后，假设 $f,g$ 是 $C^{\infty}$ 函数，则对任意 $r$，根据上述论证可知 $g\circ f$ 是 $C^{r}$ 函数，从而 $g\circ f$ 是 $C^{\infty}$ 函数。这就完成了证明。

作为链式法则的一个应用，我们将一元函数的中值定理推广到多维。

### Theorem 7.3 (中值定理)

设开集 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}$ 可微。如果 $A$ 包含连接 $\mathbf{a}$ 与 $\mathbf{a}+\mathbf{h}$ 的线段，则存在 $0<t_{0}<1$ 使得 $\mathbf{c}=\mathbf{a}+t_{0}\mathbf{h}$ 且

$$
\begin{gather}
f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})=Df(\mathbf{c}) \mathbf{h}
\end{gather}
$$

#### Proof

设 $\phi(t)=f(\mathbf{a}+t\mathbf{h})$。则 $\phi$ 在 $[0,1]$ 上可微，且存在 $0<t_{0}<1$ 使得

$$
\begin{gather}
f(\mathbf{a}+\mathbf{h})-f(\mathbf{a})=\phi(1)-\phi(0)=\phi'(t_{0})=Df(\mathbf{c}) \mathbf{h}
\end{gather}
$$

这就完成了证明。

作为另一个链式法则的应用，我们考虑对反函数进行求导的问题。首先回顾一下一元微分学中的公式。设 $\phi(x)$ 在一个开区间上可微，满足 $\phi'>0$，则 $\phi$ 在这个区间上严格递增，从而有反函数 $\psi$，定义为 $\psi(y)=x$ 当且仅当 $\phi(x)=y$。根据一元分析的结论，$\psi$ 是可微的，并且其导数为

$$
\begin{gather}
\psi'(y)=\frac{1}{\phi'(x)}
\end{gather}
$$

在多元微分学中我们也有类似的公式。在以下定理中，我们假设 $f$ 有反函数 $g$，并且 $f$ 和 $g$ 都可微。在什么条件下有这些结论成立是下一节我们主要研究的问题。

### Theorem 7.4

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}^{n}$，令 $f(\mathbf{a})=\mathbf{b}$。设 $g$ 将 $\mathbf{b}$ 的一个邻域映射入 $\mathbb{R}^{n}$，$g(\mathbf{b})=\mathbf{a}$，且在 $\mathbf{a}$ 的一个邻域上有

$$
\begin{gather}
g(f(\mathbf{x}))=\mathbf{x}
\end{gather}
$$

如果 $f$ 在 $\mathbf{a}$ 处可微且 $g$ 在 $\mathbf{b}$ 处可微，那么

$$
\begin{gather}
Dg(\mathbf{b})=Df(\mathbf{a})^{-1}
\end{gather}
$$

#### Proof

令 $i\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 为恒等函数，它的导数是恒等矩阵 $I_{n}$。在 $\mathbf{a}$ 的邻域上，我们有

$$
\begin{gather}
g(f(\mathbf{x}))=i(\mathbf{x})
\end{gather}
$$

因此链式法则给出

$$
\begin{gather}
Dg(\mathbf{b})Df(\mathbf{a})=I_{n}
\end{gather}
$$

这就完成了证明。

以上定理表明，$Df$ 可逆是可微函数 $f$ 有可微反函数的必要条件。下一节的反函数定理表明，$Df$ 可逆实际上还是 $C^{1}$ 函数 $f$ 在局部有可微反函数的充分条件。

### Remark 7.5

[[#Theorem 7.1 (链式法则)]] 事实上是多元链式法则的一个等价的矩阵形式，下面我们就来推导它的分量形式，它与微积分中的相应公式是一致的。

设 $f\colon \mathbb{R}^{m}\to \mathbb{R}^{n},g\colon \mathbb{R}^{n}\to \mathbb{R}$，则复合函数 $F=g\circ f\colon \mathbb{R}^{m}\to \mathbb{R}$，它的导数由

$$
\begin{gather}
DF(\mathbf{x})=Dg(f(\mathbf{x}))Df(\mathbf{x})
\end{gather}
$$

给出，即

$$
\begin{multline}
\begin{bmatrix}
D_{1}F(\mathbf{x}) & \cdots & D_{m}F(\mathbf{x})
\end{bmatrix} \\
= \begin{bmatrix}
D_{1}g(f(\mathbf{x})) & \cdots & D_{n}g(f(\mathbf{x}))
\end{bmatrix}\begin{bmatrix}
D_{1}f_{1}(\mathbf{x}) & \cdots & D_{m}f_{1}(\mathbf{x}) \\
\vdots &  & \vdots \\
D_{1}f_{n}(\mathbf{x}) & \cdots & D_{m}f_{n}(\mathbf{x})
\end{bmatrix}
\end{multline}
$$

展开，然后令 $\mathbf{y}=f(\mathbf{x}),z=g(\mathbf{y})$ 即得

$$
\begin{gather}
\frac{ \partial z }{ \partial x_{j} } =\sum_{k=1}^{n} \frac{ \partial z }{ \partial y_{k} } \frac{ \partial y_{k} }{ \partial x_{j} } 
\end{gather}
$$

# 8 The Inverse Function Theorem

本节我们证明反函数定理，它表明 $Df$ 可逆是 $C^{1}$ 函数 $f$ 在局部有可微反函数的充分条件。

我们首先来证明 $Df$ 的可逆性蕴含 $f$ 是局部单射的。

### Lemma 8.1

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}^{n}$ 是 $C^{1}$ 函数。如果 $Df(\mathbf{a})$ 可逆，则存在 $\alpha>0$ 使得在某个开立方体 $C(\mathbf{a},\varepsilon)$ 上有

$$
\begin{gather}
\lvert f(\mathbf{x}_{0})-f(\mathbf{x}_{1}) \rvert \geq \alpha\lvert \mathbf{x}_{0}-\mathbf{x}_{1} \rvert 
\end{gather}
$$

于是 $f$ 在 $C(\mathbf{a},\varepsilon)$ 上是单射的。

#### Proof

令 $E=Df(\mathbf{a})$，则 $E$ 可逆。我们首先考虑线性映射 $\mathbf{x}\mapsto E\mathbf{x}$，它满足

$$
\begin{align}
\lvert \mathbf{x}_{0}-\mathbf{x}_{1} \rvert &= \lvert E^{-1}(E\mathbf{x}_{0}-E\mathbf{x}_{1}) \rvert  \\
&\leq n\lvert E^{-1} \rvert \lvert E\mathbf{x}_{0}-E\mathbf{x}_{1} \rvert 
\end{align}
$$

取 $2\alpha=1 /n\lvert E^{-1} \rvert$，则 $\lvert E\mathbf{x}_{0}-E\mathbf{x}_{1} \rvert\geq 2\alpha\lvert \mathbf{x}_{0}-\mathbf{x}_{1} \rvert$。

现在我们证明以上引理。定义

$$
\begin{gather}
H(\mathbf{x})=f(\mathbf{x})-E\mathbf{x}
\end{gather}
$$

则 $DH(\mathbf{a})=Df(\mathbf{a})-E=0$。由于 $H$ 是 $C^{1}$ 函数，故存在 $\varepsilon>0$ 使得在 $C=C(\mathbf{a},\varepsilon)$ 上有 $\lvert DH(\mathbf{x}) \rvert<\alpha /n$。

对 $H_{i}$ 在 $\mathbf{x}_{0}$ 到 $\mathbf{x}_{1}$ 的连线上应用中值定理，则存在 $\mathbf{c}\in C$ 使得

$$
\begin{gather}
\lvert H_{i}(\mathbf{x}_{0})-H_{i}(\mathbf{x}_{1}) \rvert =\lvert DH(\mathbf{c})(\mathbf{x}_{0}-\mathbf{x}_{1}) \rvert \leq n(\alpha /n) \lvert \mathbf{x}_{0}-\mathbf{x}_{1} \rvert 
\end{gather}
$$

从而

$$
\begin{align}
\alpha\lvert \mathbf{x}_{0}-\mathbf{x}_{1} \rvert &\geq \lvert H(\mathbf{x}_{0})-H(\mathbf{x}_{1}) \rvert  \\
&=\lvert f(\mathbf{x}_{0})-f(\mathbf{x}_{1})-E\mathbf{x}_{0}+E\mathbf{x}_{1} \rvert  \\
&\geq \lvert E\mathbf{x}_{0}-E\mathbf{x}_{1} \rvert -\lvert f(\mathbf{x}_{0})-f(\mathbf{x}_{1}) \rvert  \\
&\geq 2\alpha \lvert \mathbf{x}_{0}-\mathbf{x}_{1} \rvert -\lvert f(\mathbf{x}_{0})-f(\mathbf{x}_{1}) \rvert 
\end{align}
$$

现在我们证明，$Df$ 的可逆性加上 $f$ 的单射性，蕴含其反函数的可微性。

### Theorem 8.2

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数，$B=f(A)$。如果 $f$ 在 $A$ 上是单射的，且对 $\mathbf{x}\in A$ 有 $Df(\mathbf{x})$ 可逆，则 $B$ 在 $\mathbb{R}^{n}$ 中开，且反函数 $g\colon B\to A$ 是 $C^{r}$ 函数。

#### Proof

**第一步** 我们证明一元微分学 Fermat 引理的推广：如果 $\phi\colon A\to \mathbb{R}$ 可微且在 $\mathbf{x}_{0}\in A$ 有局部最小值，则 $D\phi(\mathbf{x}_{0})=0$。

$\phi$ 在 $\mathbf{x}_{0}$ 有局部极小值意味着在 $\mathbf{x}_{0}$ 的邻域中有 $\phi(\mathbf{x})\geq \phi(\mathbf{x}_{0})$，则给定 $\mathbf{u}\neq \mathbf{0}$，对足够小的 $t$ 有

$$
\begin{gather}
\phi(\mathbf{x}_{0}+t\mathbf{u})-\phi(\mathbf{x}_{0})\geq 0
\end{gather}
$$

从而

$$
\begin{gather}
\phi'(\mathbf{x}_{0};\mathbf{u})=\lim_{ t \to 0 } \frac{\phi(\mathbf{x}_{0}+t\mathbf{u})-\phi(\mathbf{x}_{0})}{t}
\end{gather}
$$

在 $t$ 沿着正数趋于 $0$ 时有 $\phi'(\mathbf{x}_{0};\mathbf{u})\geq 0$，在 $t$ 沿着负数趋于 $0$ 时有 $\phi'(\mathbf{x}_{0};\mathbf{u})\leq 0$，从而 $\phi'(\mathbf{x}_{0};\mathbf{u})=0$。特别地，$D_{j}\phi(\mathbf{x}_{0})=0$，从而 $D\phi(\mathbf{x}_{0})=0$。

**第二步** 我们证明 $B$ 在 $\mathbb{R}^{n}$ 中开。给定 $\mathbf{b}\in B$，我们证明 $B$ 包含一个开球 $B(\mathbf{b},\delta)$。

我们首先取 $A$ 中包含 $\mathbf{a}=f^{-1}(\mathbf{b})$ 的一个长方体 $Q$，$\mathbf{a}$ 在 $Q$ 的内部。集合 $\operatorname{Bd}Q$ 作为 $\mathbb{R}^{n}$ 中闭且有界的集合是紧致的，故 $f(\operatorname{Bd}Q)$ 是紧致集。由于 $f$ 是单射，故 $f(\operatorname{Bd}Q)$ 不包含 $\mathbf{b}$，从而存在 $\delta>0$ 使得 $B(\mathbf{b},2\delta)$ 与 $f(\operatorname{Bd}Q)$ 不相交。给定 $\mathbf{c}\in B(\mathbf{b},\delta)$，我们来证明存在 $\mathbf{x}\in Q$ 使得 $\mathbf{c}=f(\mathbf{x})$，从而 $B=f(A)$ 包含 $B(\mathbf{b},\delta)$。

![](2-2.png)

给定 $\mathbf{c}\in B(\mathbf{b},\delta)$，考虑 $C^{r}$ 函数

$$
\begin{gather}
\phi(\mathbf{x})=\lVert f(\mathbf{x})-\mathbf{c} \rVert ^{2}
\end{gather}
$$

由于 $Q$ 是紧致的，故 $\phi$ 在 $Q$ 上有最小值 $\phi(\mathbf{x})$，我们要证 $\phi(\mathbf{x})=0$，从而 $f(\mathbf{x})=\mathbf{c}$。

我们有 $\phi(\mathbf{a})=\lVert \mathbf{b}-\mathbf{c} \rVert^{2}<\delta^{2}$，因此 $\phi(\mathbf{x})<\delta^{2}$，并且 $\mathbf{x}$ 不可能在 $\operatorname{Bd}Q$ 上，因为那时 $\phi(\mathbf{x})\geq\delta^{2}$。因此 $\mathbf{x}$ 属于 $Q$ 的内部。

根据第一步的结论，我们就有 $D\phi(\mathbf{x})=0$。由于

$$
\begin{align}
\phi(\mathbf{x}) &= \sum_{k=1}^{n} (f_{k}(\mathbf{x})-c_{k})^{2} \\
D_{j}\phi(\mathbf{x}) &= \sum_{k=1}^{n} 2(f_{k}(\mathbf{x})-c_{k}) D_{j}f_{k}(\mathbf{x})
\end{align}
$$

故

$$
\begin{gather}
D\phi(\mathbf{x})=\begin{bmatrix}
2(f_{1}(\mathbf{x})-c_{1}) & \cdots & 2(f_{n}(\mathbf{x})-c_{n})
\end{bmatrix} Df(\mathbf{x})=0
\end{gather}
$$

由于 $Df(\mathbf{x})$ 可逆，我们得到 $f_{k}(\mathbf{x})=c_{k}$，即 $f(\mathbf{x})=\mathbf{c}$。

**第三步** 根据假设，$f$ 是单射的，令 $g\colon B\to A$ 为它的反函数，我们证明 $g$ 是连续的。

反函数的连续性等价于 $f$ 的开性：对任意开集 $U\subset A$，$V=f(U)$ 在 $B$ 中开。对 $U,V$ 重复第二步的论证即可。

**第四步** 给定 $\mathbf{b}\in B$，我们证明 $g$ 在 $\mathbf{b}$ 处可微。

设 $\mathbf{a}=g(\mathbf{b})$，$E=Df(\mathbf{a})$。我们将证明函数

$$
\begin{gather}
G(\mathbf{k})=\frac{g(\mathbf{b}+\mathbf{k})-g(\mathbf{b})-E^{-1}\mathbf{k}}{\lvert \mathbf{k} \rvert }
\end{gather}
$$

在 $\mathbf{k}\to \mathbf{0}$ 时趋于 $\mathbf{0}$。则 $g$ 在 $\mathbf{b}$ 处的导数就是 $E^{-1}$。

我们在 $\mathbf{0}$ 的邻域上定义

$$
\begin{gather}
\Delta(\mathbf{k})=g(\mathbf{b}+\mathbf{k})-g(\mathbf{b})
\end{gather}
$$

我们首先证明存在 $\varepsilon>0$ 使得当 $0<\lvert \mathbf{k} \rvert<\varepsilon$ 时 $\lvert \Delta(\mathbf{k}) \rvert /\lvert \mathbf{k} \rvert$ 有界。根据 [[#Lemma 8.1]]，存在 $\mathbf{a}$ 的邻域 $C$ 和 $\alpha>0$ 使得

$$
\begin{gather}
\lvert f(\mathbf{x}_{0})-f(\mathbf{x}_{1}) \rvert \geq \alpha\lvert \mathbf{x}_{0}-\mathbf{x}_{1} \rvert 
\end{gather}
$$

根据第二步的结论，$f(C)$ 是 $\mathbf{b}$ 的邻域，于是存在 $\varepsilon>0$ 使得当 $\lvert \mathbf{k} \rvert<\varepsilon$ 时 $\mathbf{b}+\mathbf{k} \in f(C)$。我们令 $\mathbf{x}_{0}=g(\mathbf{b}+\mathbf{k}),\mathbf{x}_{1}=g(\mathbf{b})$，代入以上不等式得

$$
\begin{gather}
\lvert (\mathbf{b}+\mathbf{k})-\mathbf{b} \rvert \geq \alpha \lvert g(\mathbf{b}+\mathbf{k})-g(\mathbf{b}) \rvert 
\end{gather}
$$

从而

$$
\begin{gather}
\frac{1}{\alpha} \geq \frac{\lvert \Delta(\mathbf{k}) \rvert }{\lvert \mathbf{k} \rvert }
\end{gather}
$$

现在我们证明 $\mathbf{k}\to \mathbf{0}$ 时 $G(\mathbf{k})\to \mathbf{0}$。我们有

$$
\begin{align}
G(\mathbf{k}) &= \frac{\Delta(\mathbf{k})-E^{-1}\mathbf{k}}{\lvert \mathbf{k} \rvert } \\
&= -E^{-1} \left( \frac{\mathbf{k}-E\Delta(\mathbf{k})}{\lvert \Delta(\mathbf{k}) \rvert } \right) \frac{\lvert \Delta (\mathbf{k}) \rvert }{\lvert \mathbf{k} \rvert }
\end{align}
$$

其中由于 $g$ 是单射，故 $\Delta(\mathbf{k})\neq \mathbf{0}$。$E^{-1}$ 是常数，$\lvert \Delta(\mathbf{k}) \rvert /\lvert \mathbf{k} \rvert$ 有界，故我们只需证明括号中的项趋于 $\mathbf{0}$。

根据定义，

$$
\begin{gather}
\mathbf{b}+\mathbf{k}=f(g(\mathbf{b}+\mathbf{k}))=f(g(\mathbf{b})+\Delta(\mathbf{k}))=f(\mathbf{a}+\Delta(\mathbf{k}))
\end{gather}
$$

因此括号中的项等于

$$
\begin{gather}
\frac{f(\mathbf{a}+\Delta(\mathbf{k}))-f(\mathbf{a})-E\Delta(\mathbf{k})}{\lvert \Delta(\mathbf{k}) \rvert }
\end{gather}
$$

当 $\mathbf{k}\to \mathbf{0}$ 时，由 $g$ 的连续性知 $\Delta(\mathbf{k})\to \mathbf{0}$。又由于 $Df(\mathbf{a})=E$，上式趋于 $\mathbf{0}$。

**第五步** 我们证明 $g$ 是 $C^{r}$ 函数。

由于 $g$ 可微，链式法则给出了 $g$ 的导数公式

$$
\begin{gather}
Dg(\mathbf{y})=Df(g(\mathbf{y}))^{-1} \quad (\mathbf{y}\in B)
\end{gather}
$$

因此 $Dg$ 等于以下三个函数的复合：

$$
B \overset{g}{\longrightarrow} A \overset{Df}{\longrightarrow} GL(n) \overset{\operatorname{inv}}{\longrightarrow} GL(n)
$$

其中 $\operatorname{inv}$ 是可逆矩阵集合 $GL(n)$ 上的求逆函数 $E\mapsto E^{-1}$。由于 $E^{-1}$ 的各项是 $E$ 的各元素的有理函数，并且分母 $\det E\neq 0$，故 $\operatorname{inv}$ 是一个 $C^{\infty}$ 函数。

我们用归纳法证明 $g$ 是 $C^{r}$ 函数。设 $f$ 是 $C^{1}$ 函数，则 $Df$ 连续，又由于 $g$ 和 $\operatorname{inv}$ 都连续，故 $Dg$ 连续，即 $g$ 是 $C^{1}$ 函数。

假设定理对 $C^{r-1}$ 函数成立。设 $f$ 是 $C^{r}$ 函数，则 $f$ 也是 $C^{r-1}$ 函数，从而根据归纳假设知 $g$ 是 $C^{r-1}$ 函数。此外，$Df$ 和 $\operatorname{inv}$ 也是 $C^{r-1}$ 函数，因此 $Dg$ 是 $C^{r-1}$ 的，即证 $g$ 是 $C^{r}$ 的。

最后，$f$ 是 $C^{\infty}$ 的情况由 $C^{r}$ 的情况给出。这就完成了证明。

### Theorem 8.3 (反函数定理)

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数。如果 $Df(\mathbf{a})$ 可逆，那么存在 $\mathbf{a}$ 的邻域 $U$ 使得 $f$ 是从 $U$ 到开集 $V\subset \mathbb{R}^{n}$ 的双射，并且其反函数也是 $C^{r}$ 函数。

#### Proof

根据 [[#Lemma 8.1]]，存在 $\mathbf{a}$ 的邻域 $U_{0}$ 使得 $f$ 在 $U_{0}$ 上是单射的。由于 $\det Df$ 是连续函数，且 $Df(\mathbf{a})$ 可逆，则存在邻域 $U_{1}\subset U_{0}$ 使得在 $U_{1}$ 上有 $\det Df(\mathbf{x})\neq 0$。在 $U_{1}$ 上应用 [[#Theorem 8.2]] 就完成了证明。

以上是一般情况下能够得到的最强版本的反函数定理。尽管 $Df$ 的可逆性蕴含 $f$ 的局部单射性，它并不能推出 $f$ 的全局单射性，如以下例子所示。

### Example 8.4

设 $f\colon \mathbb{R}^{2}\to \mathbb{R}^{2}$ 为极坐标转换公式

$$
\begin{gather}
f(r,\theta)=(r\cos\theta,r\sin\theta)
\end{gather}
$$

则

$$
\begin{gather}
Df(r,\theta)=\begin{bmatrix}
\cos\theta & -r\sin\theta \\
\sin\theta & r\cos\theta
\end{bmatrix}
\end{gather}
$$

于是 $\det Df(r,\theta)=r$。

设 $A$ 为 $(r,\theta)$ 平面中的长方体 $(0,1)\times(0,b)$，则 $Df$ 在 $A$ 上可逆。然而，$f$ 在 $A$ 上是单射的仅当 $b\leq 2\pi$，如图所示。

![](2-3.png)

# 9 The Implicit Function Theorem

隐函数微分是实际应用中的一个常见方法。假设从方程 $f(x,y)=0$ 中我们可以确定 $y$ 作为 $x$ 的函数 $y=g(x)$，则 $f(x,g(x))=0$ 是一个恒等式，从而由链式法则可得

$$
\begin{gather}
\frac{ \partial f }{ \partial x } +\frac{ \partial f }{ \partial y } \frac{ \partial g }{ \partial x } =0
\end{gather}
$$

于是

$$
\begin{gather}
\frac{ \partial g }{ \partial x } =- \frac{\partial f / \partial x}{\partial f /\partial y}
\end{gather}
$$

此外，我们还可知，要使得 $g'(x)$ 存在，$\partial f /\partial y\neq 0$ 是一个必要条件。

事实证明，$\partial f /\partial y\neq 0$ 还是一个充分条件。这就是说，如果 $f(x,y)$ 在一点 $(a,b)$ 处满足 $f(a,b)=0$ 且 $\partial f /\partial y\neq 0$，那么 $f(x,y)=0$ 就在 $(a,b)$ 的邻域中确定了 $y$ 作为 $x$ 的函数，并且这一函数是可微的。

以上结论是所谓的隐函数定理的一个特例。隐函数定理的一般形式涉及一个方程组，并且我们希望解出一系列变量作为另一些变量的函数。具体来说，设 $f\colon \mathbb{R}^{k+n}\to \mathbb{R}^{n}$ 是 $C^{1}$ 函数，则向量方程

$$
\begin{gather}
f(x_{1},\dots,x_{k+n})=\mathbf{0}
\end{gather}
$$

等价于一个有 $n$ 个方程和 $k+n$ 个未知量的标量方程组。我们希望将其中的 $k$ 个变量作为自由变量，并解出剩下的 $n$ 个变量作为那 $k$ 个自由变量的函数。我们还希望这个函数是可微的，并且可以通过隐函数微分法得到它的导数。

以上我们提出了两个独立的问题。其一是在隐函数存在且可微时求出其导数，其二是在适当的假设下证明隐函数的存在性与可微性。为此，我们首先引入一些方便的记号。

### Definition 9.1

设开集 $A\subset \mathbb{R}^{m}$，$f\colon A\to \mathbb{R}^{n}$ 可微。设 $f_{1},\dots,f_{n}$ 为 $f$ 的分量，我们使用符号

$$
\begin{gather}
Df=\frac{ \partial (f_{1},\dots,f_{n}) }{ \partial (x_{1},\dots,x_{m}) } 
\end{gather}
$$

来表示 $f$ 的导数。我们可以将其简写为

$$
\begin{gather}
Df=\frac{ \partial f }{ \partial \mathbf{x} } 
\end{gather}
$$

更一般地，我们使用符号

$$
\begin{gather}
\frac{ \partial (f_{i_{1}},\dots,f_{i_{k}}) }{ \partial (x_{j_{1}},\dots,x_{j_{\ell}}) } 
\end{gather}
$$

来表示由 $Df$ 的第 $i_{1},\dots,i_{k}$ 行和第 $j_{1},\dots,j_{\ell}$ 列组成的 $k\times \ell$ 矩阵。

现在我们假设隐函数存在且可微，求解其导数。通过变量的交换，我们不妨假设前 $k$ 个变量是自由变量。

### Theorem 9.2

设开集 $A\subset \mathbb{R}^{k+n}$，$f\colon A\to \mathbb{R}^{n}$ 可微。将 $f$ 写成 $f(\mathbf{x},\mathbf{y})$，其中 $\mathbf{x}\in \mathbb{R}^{k},\mathbf{y}\in \mathbb{R}^{n}$，则 $Df$ 具有形式

$$
\begin{gather}
Df=\begin{bmatrix}
\dfrac{ \partial f }{ \partial \mathbf{x} }  & \dfrac{ \partial f }{ \partial \mathbf{y} } 
\end{bmatrix}
\end{gather}
$$

假设有可微函数 $g\colon B\to \mathbb{R}^{n}$ 使得 $B\subset \mathbb{R}^{n}$ 开，并且对 $\mathbf{x}\in B$ 有

$$
\begin{gather}
f(\mathbf{x},g(\mathbf{x}))=\mathbf{0}
\end{gather}
$$

则对 $\mathbf{x}\in B$ 有

$$
\begin{gather}
\frac{ \partial f }{ \partial \mathbf{x} } (\mathbf{x},g(\mathbf{x}))+\frac{ \partial f }{ \partial \mathbf{y} } (\mathbf{x},g(\mathbf{x})) Dg(\mathbf{x})=\mathbf{0}
\end{gather}
$$

于是如果 $\partial f /\partial \mathbf{y}$ 在 $(\mathbf{x},g(\mathbf{x}))$ 处可逆，那么

$$
\begin{gather}
Dg(\mathbf{x})=-\left( \frac{ \partial f }{ \partial \mathbf{y} } (\mathbf{x},g(\mathbf{x})) \right) ^{-1} \left( \frac{ \partial f }{ \partial \mathbf{x} } (\mathbf{x},g(\mathbf{x})) \right)
\end{gather}
$$

#### Proof

给定 $g$，定义 $h\colon B\to \mathbb{R}^{k+n}$ 为

$$
\begin{gather}
h(\mathbf{x})=(\mathbf{x},g(\mathbf{x}))
\end{gather}
$$

则我们有

$$
\begin{gather}
H(\mathbf{x})=f(h(\mathbf{x}))=f(\mathbf{x},g(\mathbf{x}))=\mathbf{0}
\end{gather}
$$

从而由链式法则有

$$
\begin{align}
\mathbf{0} &= DH(\mathbf{x})=Df(h(\mathbf{x}))Dh(\mathbf{x}) \\
&= \begin{bmatrix}
\dfrac{ \partial f }{ \partial \mathbf{x} }(h(\mathbf{x})) & \dfrac{ \partial f }{ \partial \mathbf{y} }(h(\mathbf{x})) 
\end{bmatrix} \begin{bmatrix}
I_{k} \\
Dg(\mathbf{x})
\end{bmatrix} \\
&= \frac{ \partial f }{ \partial \mathbf{x} } (\mathbf{x},g(\mathbf{x}))+\frac{ \partial f }{ \partial \mathbf{y} } (\mathbf{x},g(\mathbf{x})) Dg(\mathbf{x})
\end{align}
$$

这就完成了证明。

### Theorem 9.3 (隐函数定理)

设开集 $A\subset \mathbb{R}^{k+n}$，$f\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数。将 $f$ 写成 $f(\mathbf{x},\mathbf{y})$，其中 $\mathbf{x}\in \mathbb{R}^{k},\mathbf{y}\in \mathbb{R}^{n}$。假设 $(\mathbf{a},\mathbf{b})\in A$ 满足 $f(\mathbf{a},\mathbf{b})=\mathbf{0}$ 且

$$
\begin{gather}
\det \frac{ \partial f }{ \partial \mathbf{y} } (\mathbf{a},\mathbf{b})\neq 0
\end{gather}
$$

则存在 $\mathbf{a}$ 的邻域 $B\subset \mathbb{R}^{k}$ 和唯一的连续函数 $g\colon B\to \mathbb{R}^{n}$ 使得 $g(\mathbf{a})=\mathbf{b}$ 且对 $\mathbf{x}\in B$ 有

$$
\begin{gather}
f(\mathbf{x},g(\mathbf{x}))=\mathbf{0}
\end{gather}
$$

此外，函数 $g$ 还是一个 $C^{r}$ 函数。

#### Proof

我们构造一个函数 $F$ 使得我们可以应用反函数定理。定义 $F\colon A\to \mathbb{R}^{k+n}$ 为

$$
\begin{gather}
F(\mathbf{x},\mathbf{y})=(\mathbf{x},f(\mathbf{x},\mathbf{y}))
\end{gather}
$$

则 $F$ 将开集 $A\subset \mathbb{R}^{k+n}$ 映射入 $\mathbb{R}^{k+n}$。此外，

$$
\begin{gather}
DF=\begin{bmatrix}
I_{k} & 0 \\
\partial f /\partial \mathbf{x} & \partial f / \partial \mathbf{y}
\end{bmatrix}
\end{gather}
$$

应用行列式的按行展开公式 $k$ 次，我们有 $\det DF=\det(\partial f /\partial \mathbf{y})$，因此 $DF$ 在 $(\mathbf{a},\mathbf{b})$ 处可逆。

我们有 $F(\mathbf{a},\mathbf{b})=(\mathbf{a},\mathbf{0})$。对 $F$ 应用反函数定理，则存在 $(\mathbf{a},\mathbf{b})$ 的邻域 $U\times V\subset \mathbb{R}^{k+n}$ 使得

1. $F$ 是从 $U\times V$ 到 $(\mathbf{a},\mathbf{0})$ 的邻域 $W\subset \mathbb{R}^{k+n}$ 的双射，
2. 反函数 $G\colon W\to U\times V$ 是 $C^{r}$ 函数。

于是我们有

$$
\begin{gather}
(\mathbf{x},\mathbf{y})=G(\mathbf{x},f(\mathbf{x},\mathbf{y}))
\end{gather}
$$

定义 $h\colon W\to \mathbb{R}^{n}$ 为

$$
\begin{gather}
G(\mathbf{x},\mathbf{z})=(\mathbf{x},h(\mathbf{x},\mathbf{z}))
\end{gather}
$$

则 $h$ 是一个 $C^{r}$ 函数。

![](2-4.png)

设 $B\subset \mathbb{R}^{k}$ 是包含 $\mathbf{a}$ 的一个连通开集，取得足够小以使得 $B\times \mathbf{0}\subset W$。我们来证明 $g\colon B\to \mathbb{R}^{n}$ 的存在性。

如果 $\mathbf{x}\in B$，那么 $(\mathbf{x},\mathbf{0})\in W$，则有

$$
\begin{align}
G(\mathbf{x},\mathbf{0}) &= (\mathbf{x},h(\mathbf{x},\mathbf{0})) \\
(\mathbf{x},\mathbf{0}) &= F(\mathbf{x},h(\mathbf{x},\mathbf{0}))=(\mathbf{x},f(\mathbf{x},h(\mathbf{x},\mathbf{0}))) \\
\mathbf{0} &=f(\mathbf{x},h(\mathbf{x},\mathbf{0}))
\end{align}
$$

取 $g(\mathbf{x})=h(\mathbf{x},\mathbf{0})$ 即得 $f(\mathbf{x},g(\mathbf{x}))=\mathbf{0}$ 且 $g$ 是 $C^{r}$ 函数。此外，我们有

$$
\begin{gather}
G(\mathbf{a},\mathbf{0})=(\mathbf{a},\mathbf{b})=(\mathbf{a},h(\mathbf{a},\mathbf{0}))
\end{gather}
$$

即 $\mathbf{b}=h(\mathbf{a},\mathbf{0})=g(\mathbf{a})$。

最后我们证明 $g$ 的唯一性。设 $g_{0}\colon B\to \mathbb{R}^{n}$ 是一个满足定理结论的连续函数。则 $g$ 与 $g_{0}$ 在 $\mathbf{a}$ 处相等。我们证明如果 $g_{0}$ 和 $g$ 在点 $\mathbf{a}_{0}\in B$ 处相等，那么 $g_{0}$ 和 $g$ 在 $\mathbf{a}_{0}$ 的邻域上相等：$g$ 将 $\mathbf{a}_{0}$ 映射入 $V$。由于 $g_{0}$ 连续且 $V$ 是开集，存在 $\mathbf{a}_{0}$ 的邻域 $B_{0}$ 使得 $g_{0}(B_{0})\subset V$。

在 $\mathbf{x}\in B_{0}$ 上，$f(\mathbf{x},g_{0}(\mathbf{x}))=\mathbf{0}$ 表明

$$
\begin{align}
F(\mathbf{x},g_{0}(\mathbf{x})) &=(\mathbf{x},\mathbf{0}) \\
(\mathbf{x},g_{0}(\mathbf{x})) &= G(\mathbf{x},\mathbf{0})=(\mathbf{x},g(\mathbf{x}))
\end{align}
$$

因此 $g_{0}$ 和 $g$ 在 $B_{0}$ 上相等。于是，根据 $B$ 的连通性，$g_{0}$ 和 $g$ 在 $B$ 上相等：$g_{0}(\mathbf{x})=g(\mathbf{x})$ 的 $\mathbf{x}$ 构成的集合是开集，而由连续性知 $g_{0}(\mathbf{x})\neq g(\mathbf{x})$ 的 $\mathbf{x}$ 构成的集合也是开集，前者非空，因此后者必然是空集。这就完成了证明。

在实际应用中，我们不需要假设前 $k$ 个变量是自由变量。同样的论证也适用于求解任意 $n$ 个变量作为其它变量的函数，只要相关的 Jacobian 行列式非零。

例如，设 $A\subset \mathbb{R}^{5}$ 是开集且 $f\colon A\to \mathbb{R}^{2}$ 是 $C^{r}$ 函数。假设我们要从方程 $f(x,y,z,u,v)=\mathbf{0}$ 解出 $y$ 和 $u$ 作为其它变量的函数，此时，隐函数定理表明如果 $\mathbf{a}\in A$ 满足 $f(\mathbf{a})=\mathbf{0}$ 且

$$
\begin{gather}
\det \frac{ \partial f }{ \partial (y,u) } (\mathbf{a})\neq 0
\end{gather}
$$

那么我们可以在 $\mathbf{a}$ 的邻域中解出 $y=\phi(x,z,v)$ 和 $u=\psi(x,z,v)$。此外，$\phi,\psi$ 的导数满足公式

$$
\begin{gather}
\frac{ \partial (\phi,\psi) }{ \partial (x,z,v) } =- \left( \frac{ \partial f }{ \partial (y,u) }  \right)^{-1} \left( \frac{ \partial f }{ \partial (x,z,v) }  \right)
\end{gather}
$$

