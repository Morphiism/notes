在一元积分的计算中，一个重要的方法是变量替换定理：

$$
\begin{gather}
\int_{g(a)}^{g(b)}f=\int_{a}^{b} (f\circ g) g'
\end{gather}
$$

本节我们要研究的就是变量替换定理的推广，它分成两个方面：

1. 我们将研究 $n$ 维积分的变量替换。
2. 我们将对广义积分证明变量替换定理，这将使我们限制在 $\mathbb{R}^{n}$ 的开集上。但根据 [[3 Integration#Corollary 15.6]] 所示，这不会造成本质性的问题。

# 16 Partitions of Unity

在证明变量替换定理之前，我们需要重新表述广义积分 $\int_{A}f$ 的定义。在上一章中，我们将 $A$ 分解成了一列紧致可求体积集 $C_{N}$，然后取 $\int_{C_{N}}f$ 的极限。在本节的新定义中，我们不改动积分区域 $A$，而是将 $f$ 分解为一系列 $f_{N}$，后者在某个紧致集外消失，然后我们取 $\int_{A}f_{N}$ 的极限。这种定义方法在理论上有许多优点。

### Lemma 16.1

设 $Q$ 是 $\mathbb{R}^{n}$ 中的长方体，则存在 $C^{\infty}$ 函数 $\phi\colon \mathbb{R}^{n}\to \mathbb{R}$ 使得对 $\mathbf{x}\in \operatorname{Int}Q$ 有 $\phi(\mathbf{x})>0$ 且在其余位置有 $\phi(\mathbf{x})=0$。

#### Proof

设 $f\colon \mathbb{R}\to \mathbb{R}$ 定义为

$$
\begin{gather}
f(x)=\begin{cases}
e^{-1/x}, & x>0 \\
0, & \text{otherwise}
\end{cases}
\end{gather}
$$

则 $x>0$ 时 $f(x)>0$，并且容易证明 $f$ 在 $\mathbb{R}$ 上是 $C^{\infty}$ 的。定义

$$
\begin{gather}
g(x)=f(x)f(1-x)
\end{gather}
$$

则 $g$ 是 $C^{\infty}$ 函数，且在 $0<x<1$ 上 $g(x)>0$，而在其它位置消失。

![](4-1.png)

最后，设

$$
\begin{gather}
Q=[a_{1},b_{1}]\times\dots \times[a_{n},b_{n}]
\end{gather}
$$

我们令

$$
\begin{gather}
\phi(\mathbf{x})=g\left( \frac{x_{1}-a_{1}}{b_{1}-a_{1}} \right) \cdots g\left( \frac{x_{n}-a_{n}}{b_{n}-a_{n}} \right)
\end{gather}
$$

即证。

### Lemma 16.2

设 $\mathcal{A}$ 是 $\mathbb{R}^{n}$ 中的一个开集族，$A=\bigcup \mathcal{A}$。则存在可数个长方体 $Q_{1},Q_{2},\dots$ 包含于 $A$ 使得

1. 所有集合 $\operatorname{Int}Q_{i}$ 覆盖 $A$，
2. 每个 $Q_{i}$ 都包含于 $\mathcal{A}$ 的某个元素，
3. $A$ 中的每个点都有一个邻域，使得它仅和有限个 $Q_{i}$ 相交。

性质 (3) 称为局部有限性质。

#### Proof

**第一步**

令 $D_{1},D_{2},\dots$ 为一列 $A$ 的紧致子集，其并集为 $A$，且 $D_{i}\subset \operatorname{Int}D_{i+1}$。定义 $D_{0}=\varnothing$，并定义

$$
\begin{gather}
B_{i}=D_{i}\setminus \operatorname{Int}D_{i-1}
\end{gather}
$$

则 $B_{i}$ 作为 $D_{i}$ 的子集是有界的，且它是两个闭集的交，从而是闭的，因此 $B_{i}$ 是紧致集。此外，$B_{i}$ 与 $D_{i-2}$ 不相交，因为 $D_{i-2}\subset \operatorname{Int}D_{i-1}$。

![](4-2.png)

对 $\mathbf{x}\in B_{i}$，取一个闭立方体 $C_{\mathbf{x}}$ 使得它包含于 $A$ 且与 $D_{i-2}$ 不相交，并且使得它包含于 $\mathcal{A}$ 的某个元素中。

$C_{\mathbf{x}}$ 的内部覆盖了 $B_{i}$，故存在有限个立方体其内部覆盖 $B_{i}$，这些立方体的集合记作 $\mathcal{C}_{i}$。

**第二步**

令

$$
\begin{gather}
\mathcal{C}=\bigcup_{i=1}^{\infty} \mathcal{C}_{i}
\end{gather}
$$

则 $\mathcal{C}$ 是一个长方体（立方体）的可数集合。我们证明这个集合满足所需的条件。

根据定义，$\mathcal{C}$ 的每个元素都包含在 $\mathcal{A}$ 的某个元素中。给定 $\mathbf{x}\in A$，令 $i$ 为使得 $\mathbf{x}\in \operatorname{Int}D_{i}$ 的最小整数，则 $\mathbf{x}$ 是 $B_{i}=D_{i}-\operatorname{Int}D_{i-1}$ 的元素，从而包含于 $\mathcal{C}$ 的某个元素中。这表明 $\mathcal{C}$ 覆盖 $A$。

最后我们验证局部有限性。给定 $\mathbf{x}$，存在 $i$ 使得 $\mathbf{x}\in \operatorname{Int}D_{i}$。由于 $\mathcal{C}_{i+2},\mathcal{C}_{i+3},\dots$ 中的立方体与 $D_{i}$ 不相交，因此开集 $\operatorname{Int}D_{i}$ 只可能与 $\mathcal{C}_{1},\dots,\mathcal{C}_{i+1}$ 中的立方体相交，这其中只有有限个立方体。

### Definition 16.3 support 支撑

设 $\phi\colon \mathbb{R}^{n}\to \mathbb{R}$，它的支撑集 $\operatorname{supp}(\phi)$ 定义为集合 $\{ \mathbf{x}: \phi(\mathbf{x})\neq 0 \}$ 的闭包。等价地，如果 $\mathbf{x}\not\in \operatorname{supp}(\phi)$，那么存在 $\mathbf{x}$ 的邻域，在其上 $\phi$ 恒等于零。

下面我们给出单位分解的存在性定理。

### Theorem 16.4

设 $\mathcal{A}$ 为 $\mathbb{R}^{n}$ 中的一个开集族，$A=\bigcup \mathcal{A}$。存在一列连续函数 $\phi_{i}\colon \mathbb{R}^{n}\to \mathbb{R}$ 使得

1. $\phi_{i}\geq 0$，
2. $S_{i}=\operatorname{supp}(\phi_{i})$ 包含于 $A$，
3. $A$ 的每个点都有一个邻域使得它仅和有限个 $S_{i}$ 相交，
4. 对 $\mathbf{x}\in A$ 有 $\sum_{i=1}^{\infty}\phi_{i}(\mathbf{x})=1$，
5. $\phi_{i}$ 是 $C^{\infty}$ 函数，
6. $S_{i}$ 是紧致集，
7. 每个 $S_{i}$ 都包含于 $\mathcal{A}$ 的某个元素中。

满足性质 (1)-(4) 的函数族 $\{ \phi_{i} \}$ 称为一个 $A$ 上的单位分解；如果它满足 (5)，则称它是 $C^{\infty}$ 的；如果它满足 (6)，则称它是紧支撑的；如果它满足 (7)，则称它受 $\mathcal{A}$ 的控制。

#### Proof

给定 $\mathcal{A}$ 和 $A$，令 $Q_{1},Q_{2},\dots$ 为满足 [[#Lemma 16.2]] 中性质的一列长方体，对每个 $i$，令 $\psi_{i}\colon \mathbb{R}^{n}\to \mathbb{R}$ 为一个 $C^{\infty}$ 函数，其在 $\operatorname{Int}Q_{i}$ 上为正，在其余位置消失（[[#Lemma 16.1]]）。则 $\psi_{i}\geq 0$，且 $\operatorname{supp}(\psi_{i})=Q_{i}$，后者是包含于 $\mathcal{A}$ 的某个元素的紧致集。最后，每个 $A$ 中的点都有一个邻域使得它仅和有限个 $Q_{i}$ 相交，因此 $\{ \psi_{i} \}$ 满足除 (4) 以外的所有性质。

性质 (3) 表明，对 $\mathbf{x}\in A$，只有有限个 $\psi_{i}(\mathbf{x})$ 非零，因此级数

$$
\begin{gather}
\lambda(\mathbf{x})=\sum_{i=1}^{\infty} \psi_{i}(\mathbf{x})
\end{gather}
$$

收敛。由于对任意 $\mathbf{x}\in A$ 有一个邻域使得在其中 $\lambda(\mathbf{x})$ 等于有限个 $C^{\infty}$ 函数之和，因此 $\lambda$ 也是 $C^{\infty}$ 的。最后，对 $\mathbf{x}\in A$ 有 $\lambda(\mathbf{x})> 0$：给定 $\mathbf{x}$，存在一个 $Q_{i}$ 使其内部包含 $\mathbf{x}$，此时 $\psi_{i}(\mathbf{x})>0$。于是我们可以定义

$$
\begin{gather}
\phi_{i}(\mathbf{x})=\frac{\psi_{i}(\mathbf{x})}{\lambda(\mathbf{x})}
\end{gather}
$$

$\{ \phi_{i} \}$ 就是所求的函数族。

上面的性质 (1) 和 (4) 表明，数 $\phi_{i}(\mathbf{x})$ 事实上就是单位 $1$ 的分解：它们将单位 $1$ 分解为了一系列非负数的和。局部有限性 (3) 表明对任意紧致集 $C\subset A$，存在一个包含 $C$ 的开集，在其中仅有有限个 $\phi_{i}$ 不为零。要找到这样的开集，我们用有限个邻域覆盖 $C$，每个邻域仅和有限个 $\operatorname{supp}(\phi_{i})$ 相交，然后我们取这些邻域的并集。

### Lemma 16.5

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 连续。如果 $f$ 在紧致集 $C\subset A$ 外消失，那么 $\int_{A}f$ 和 $\int_{C}f$ 都存在且相等。

#### Proof

积分 $\int_{C}f$ 存在，因为 $C$ 有界并且函数 $f_{C}$ 有界连续。

设 $C_{i}$ 是一列紧致可求体积集，其并集为 $A$，且 $C_{i}\subset \operatorname{Int}C_{i+1}$。则 $C$ 可以由有限个 $\operatorname{Int}C_{i}$ 覆盖，从而可由其中一个覆盖，设为 $\operatorname{Int}C_{M}$。由于 $f$ 在 $C$ 外消失，因此对 $N\geq M$ 有

$$
\begin{gather}
\int_{C} f=\int_{C_{N}} f
\end{gather}
$$

在上式中用 $\lvert f \rvert$ 替换 $f$，则 $\lim_{ N \to \infty }\int_{C_{N}}\lvert f \rvert$ 存在，故 $f$ 在 $A$ 上可积。从而我们有

$$
\begin{gather}
\int_{C}f=\lim_{ N \to \infty } \int_{C_{N}} f=\int_{A} f
\end{gather}
$$

### Theorem 16.6

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 连续。设 $\{ \phi_{i} \}$ 是 $A$ 上的一个紧支撑单位分解，则 $\int_{A}f$ 存在当且仅当级数

$$
\begin{gather}
\sum_{i=1}^{\infty} \int_{A} \phi_{i}\lvert f \rvert 
\end{gather}
$$

收敛，此时

$$
\begin{gather}
\int_{A} f=\sum_{i=1}^{\infty} \int_{A} \phi_{i} f
\end{gather}
$$

注意到，根据 [[#Lemma 16.5]]，$\int_{A}\phi_{i}f$ 存在且等于普通积分 $\int_{S_{i}}\phi_{i}f$。

#### Proof

我们首先考虑 $f$ 非负的情况。

**第一步** 假设 $\sum \int_{A}\phi_{i}f$ 收敛，我们来证明 $\int_{A}f$ 存在。

令 $D\subset A$ 是一个紧致可求体积集，则存在 $M$ 使得当 $i>M$ 时 $\phi_{i}$ 在 $D$ 上消失。此时

$$
\begin{gather}
f(\mathbf{x})=\sum_{i=1}^{M} \phi_{i}(\mathbf{x})f(\mathbf{x})
\end{gather}
$$

从而

$$
\begin{align}
\int_{D} f &= \sum_{i=1}^{M} \int_{D} \phi_{i}f \\
&\leq \sum_{i=1}^{M} \int_{D\cup S_{i}} \phi_{i}f \\
&= \sum_{i=1}^{M} \int_{A} \phi_{i}f \\
&\leq \sum_{i=1}^{\infty} \int_{A} \phi_{i}f
\end{align}
$$

于是 $f$ 在 $A$ 上可积，并且

$$
\begin{gather}
\int_{A} f\leq \sum_{i=1}^{\infty} \int_{A} \phi_{i}f
\end{gather}
$$

**第二步** 假设 $f$ 在 $A$ 上可积，我们来证明级数 $\sum \int_{A}\phi_{i}f$ 收敛。

给定 $N$，令 $D=S_{1}\cup\dots \cup S_{N}$，则 $D$ 是紧致集。此外，对于 $1\leq i\leq N$，$\phi_{i}f$ 在 $D$ 外消失，于是

$$
\begin{gather}
\int_{A} \phi_{i}f=\int_{D} \phi_{i}f
\end{gather}
$$

从而

$$
\begin{align}
\sum_{i=1}^{N} \int_{A} \phi_{i}f &= \sum_{i=1}^{N} \int_{D} \phi_{i} f \\
&\leq \int_{D} \sum_{i=1}^{N} \phi_{i}f \\
&\leq \int_{D} f \\
&\leq \int_{A} f
\end{align}
$$

因此级数 $\sum \int_{A}\phi_{i}f$ 收敛，并且

$$
\begin{gather}
\sum_{i=1}^{\infty} \int_{A} \phi_{i}f\leq \int_{A} f
\end{gather}
$$

**第三步** 我们对一般连续函数进行证明。

根据 [[3 Integration#Theorem 15.3]]，$\int_{A}f$ 存在当且仅当 $\int_{A}\lvert f \rvert$ 存在，而根据第一、二步的结论，后者成立当且仅当级数

$$
\begin{gather}
\sum_{i=1}^{\infty} \int_{A} \phi_{i}\lvert f \rvert 
\end{gather}
$$

收敛。

另一方面，如果 $f$ 在 $A$ 上可积，那么

$$
\begin{align}
\int_{A} f &=\int_{A} f_{+}-\int_{A} f_{-} \\
&=\sum_{i=1}^{\infty} \int_{A} \phi_{i}f_{+}-\sum_{i=1}^{\infty} \int_{A} \phi_{i}f_{-} \\
&= \sum_{i=1}^{\infty} \int_{A} \phi_{i}f
\end{align}
$$

因为收敛级数可以逐项相加。

# 17 The Change of Variables Theorem

现在我们来叙述一般的变量替换定理。我们首先回顾一下一元积分的变量替换定理。设 $f$ 在 $[a,b]$ 上可积，我们约定

$$
\begin{gather}
\int_{b}^{a} f=-\int_{a}^{b} f
\end{gather}
$$

### Theorem 17.1

设 $I=[a,b]$，$g\colon I\to \mathbb{R}$ 是 $C^{1}$ 函数，对 $x \in(a,b)$ 有 $g'(x)\neq 0$。则 $J=g(I)$ 是一个闭区间，其端点为 $g(a)$ 和 $g(b)$。如果 $f\colon J\to \mathbb{R}$ 连续，那么

$$
\begin{gather}
\int_{g(a)}^{g(b)} f=\int_{a}^{b} (f\circ g)g'
\end{gather}
$$

或者等价地，

$$
\begin{gather}
\int_{J} f=\int_{I} (f\circ g)\lvert g' \rvert 
\end{gather}
$$

在第一个公式中我们不需要为 $g'$ 添加绝对值，因为当 $g'<0$ 时 $g(a)>g(b)$，此时等式左边的项等于 $-\int_{J}f$。

### Example 17.2

我们来看微积分中一个典型的变量替换的应用。考虑积分

$$
\begin{gather}
\int_{y=-1}^{y=1} \frac{1}{\sqrt{ 1-y^{2} }}
\end{gather}
$$

一个典型过程如下：令 $y=g(x)=\sin x$，$x \in [-\pi /2,\pi /2]$，则 $g'(x)=\cos x$ 在 $(-\pi /2,\pi /2)$ 上非零，且 $g(-\pi /2)=-1,g(\pi /2)=1$。如果 $f(y)$ 在 $[-1,1]$ 上连续，那么变量替换公式给出

$$
\begin{gather}
\int_{-1}^{1} f=\int_{-\pi /2}^{\pi /2} (f\circ g)g'
\end{gather}
$$

代入 $f(y)=1 /(1-y^{2})^{1 /2}$ 就有

$$
\begin{gather}
\int_{y=-1}^{y=1} \frac{1}{\sqrt{ 1-y^{2} }}=\int_{x=-\pi /2}^{x=\pi /2} 1=\pi
\end{gather}
$$

然而，上面的论证有一个问题：$f(y)$ 并不在 $-1$ 和 $1$ 处连续，因此 [[#Theorem 17.1]] 并不适用。$f$ 的积分实际上是一个广义积分，因为 $f$ 甚至在 $(-1,1)$ 上并非有界。

前面我们提到，我们将对 $n$ 维的广义积分证明变量替换定理。其中一个原因是广义积分实际上比普通积分更容易处理，另一个原因，如 [[#Example 17.2]] 所示，即使是在初等问题中，我们也通常需要广义积分版本的变量替换定理。

### Definition 17.3 change of variables 变量替换，diffeomorphism 微分同胚

设开集 $A\subset \mathbb{R}^{n}$，称 $g\colon A\to \mathbb{R}^{n}$ 是 $\mathbb{R}^{n}$ 上的一个变量替换，如果它是一个 $C^{r}$ 单射，且对 $\mathbf{x}\in A$ 有 $\det Dg(\mathbf{x})\neq 0$。

一个等价的定义如下：设 $A,B\subset \mathbb{R}^{n}$ 是开集，称 $g\colon A\to B$ 是一个微分同胚，如果 $g$ 是双射并且 $g$ 和 $g^{-1}$ 都是 $C^{r}$ 函数。

如果 $g$ 是 $C^{r}$ 微分同胚，那么链式法则表明 $Dg(\mathbf{x})$ 可逆，故 $\det Dg(\mathbf{x})\neq 0$，因此 $g$ 是变量替换。反之，如果 $g$ 是 $C^{r}$ 变量替换，那么 [[2 Differentiation#Theorem 8.2]] 表明 $B=g(A)$ 是开集，$g\colon A\to B$ 是双射，并且 $g^{-1}$ 也是 $C^{r}$ 函数。换句话说，$g$ 是一个微分同胚。综上所述，“微分同胚”与“变量替换”是相同概念的不同名称。

### Theorem 17.4 (变量替换定理)

设 $g\colon A\to B$ 是 $\mathbb{R}^{n}$ 上开集之间的微分同胚，$f\colon B\to \mathbb{R}$ 连续。则 $f$ 在 $B$ 上可积当且仅当 $(f\circ g)\lvert \det Dg \rvert$ 在 $A$ 上可积，此时

$$
\begin{gather}
\int_{B} f=\int_{A} (f\circ g)\lvert \det Dg \rvert 
\end{gather}
$$

我们将在后续的章节证明这个定理，下面我们给出一些变量替换定理的应用例子。

### Example 17.5

(a) 设 $B\subset \mathbb{R}^{2}$ 定义为开四分之一圆

$$
\begin{gather}
B=\{ (x,y) : x>0,y>0,x^{2}+y^{2}<a^{2} \}
\end{gather}
$$

通常我们利用极坐标变换来计算 $B$ 上的积分 $\int_{B}f$，这便是定义为

$$
\begin{gather}
g(r,\theta)=(r\cos\theta,r\sin\theta)
\end{gather}
$$

的函数 $g\colon \mathbb{R}^{2}\to \mathbb{R}^{2}$。容易验证 $\det Dg=r$。要应用变量替换定理，我们将 $g$ 的定义域限制在开长方体

$$
\begin{gather}
A=(0,a)\times(0,\pi /2)
\end{gather}
$$

上，则 $g\colon A\to B$ 是双射，从而是一个微分同胚。于是

$$
\begin{gather}
\int_{B} f=\int_{A} f(r\cos\theta,r\sin\theta) r
\end{gather}
$$

极坐标变换中的因子 $r$ 正是来源于 $g$ 的 Jacobian 行列式。

![](4-3.png)

(b) 假设现在我们要在整个开圆

$$
\begin{gather}
W=\{ (x,y) : x^{2}+y^{2}<a^{2} \}
\end{gather}
$$

上做积分。此时我们不能直接应用变量替换定理，因为此时 $W$ 在极坐标变换 $g$ 下的原像 $g^{-1}(W)$ 不是一个开集。然而，如果我们从 $W$ 中去掉非负 $x$ 轴

$$
\begin{gather}
V=W \setminus \{ (x,0) : x\geq 0 \}
\end{gather}
$$

那么 $g$ 的确定义了一个从 $U=(0,a)\times(0,2\pi)$ 到 $V$ 的微分同胚。又由于非负 $x$ 轴的测度为零，我们就有

$$
\begin{gather}
\int_{W} f=\int_{V} f=\int_{U} f(r\cos\theta,r\sin\theta)r
\end{gather}
$$

![](4-4.png)

(c) 极坐标变换的三维对应是球坐标变换。设 $B\subset \mathbb{R}^{3}$ 为

$$
\begin{gather}
B=\{ (x,y,z) : x>0,y>0, x^{2}+y^{2}+z^{2}<a^{2} \}
\end{gather}
$$

对于积分 $\int_{B}f$，我们通常使用球坐标变换 $g\colon \mathbb{R}^{3}\to \mathbb{R}^{3}$，定义为

$$
\begin{gather}
g(r,\phi,\theta)=(\rho\sin \phi \cos\theta,\rho\sin \phi \sin\theta,\rho\cos \phi)
\end{gather}
$$

计算可得 $\det Dg=\rho^{2}\sin \phi$。给定 $B$ 中的一点 $\mathbf{x}$，我们用 $\phi$ 来表示 $\mathbf{x}$ 与正 $z$ 轴形成的夹角，用 $\theta$ 来表示 $\mathbf{x}$ 在 $xy$ 平面中的投影与正 $x$ 轴的夹角，于是 $g$ 是从开集

$$
\begin{gather}
A=\left\{  (\rho,\phi,\theta) : 0<\rho<a,0<\phi<\pi,0<\theta<\frac{\pi}{2}  \right\}
\end{gather}
$$

到 $B$ 的微分同胚。变量替换定理给出

$$
\begin{gather}
\int_{B} f=\int_{A} f(\rho\sin \phi \cos\theta,\rho\sin \phi \sin\theta,\rho\cos \phi)\rho^{2}\sin \phi
\end{gather}
$$

![](4-5.png)

# 18 Diffeomorphisms in $\mathbb{R}^{n}$

在证明变量替换定理之前，我们需要给出微分同胚的一些基本性质。其一是微分同胚将紧致可求体积集映射到紧致可求体积集；其二是一个微分同胚总可以分解为一系列特殊的微分同胚的复合，称为“最简微分同胚”。

### Lemma 18.1

设开集 $A\subset \mathbb{R}^{n}$，$g\colon A\to \mathbb{R}^{n}$ 是 $C^{1}$ 函数。如果 $E\subset A$ 的测度为零，那么 $g(E)$ 的测度也为零。

#### Proof

**第一步** 设 $\varepsilon,\delta>0$，我们首先证明如果 $S$ 的测度为零，那么 $S$ 可以被可数个宽度小于 $\delta$，总体积小于 $\varepsilon$ 的立方体覆盖。

为此，我们只需证明长方体

$$
\begin{gather}
Q=[a_{1},b_{1}]\times \dots \times [a_{n},b_{n}]
\end{gather}
$$

可以被有限个宽度小于 $\delta$，总体积小于 $2v(Q)$ 的立方体覆盖。

选取 $\lambda>0$ 使得

$$
\begin{gather}
Q_{\lambda}=[a_{1}-\lambda,b_{1}+\lambda]\times\dots \times[a_{n}-\lambda,b_{n}+\lambda]
\end{gather}
$$

的体积小于 $2v(Q)$，再取 $N$ 使得 $1 /N$ 小于 $\delta$ 和 $\lambda$。考虑具有形式 $m /N$ 的有理数，令 $c_{i}$ 为其中满足 $c_{i}\leq a_{i}$ 的最大项，$d_{i}$ 为满足 $d_{i}\geq b_{i}$ 的最小项，则 $[a_{i},b_{i}]\subset[c_{i},d_{i}]\subset[a_{i}-\lambda,b_{i}+\lambda]$。令

$$
\begin{gather}
Q'=[c_{1},d_{1}]\times\dots \times[c_{n},d_{n}]
\end{gather}
$$

则 $Q\subset Q'\subset Q_{\lambda}$，故 $v(Q')<2v(Q)$。我们将 $Q'$ 的每个分量区间划分为长度为 $1 /N$ 的子区间，这就将 $Q'$ 划分为了有限个宽度 $1 /N<\delta$，总体积小于 $2v(Q)$ 的子长方体，这些长方体覆盖 $Q$。

**第二步** 设 $C\subset A$ 是一个立方体，令

$$
\begin{gather}
\lvert Dg(\mathbf{x}) \rvert \leq M \quad (\mathbf{x}\in C)
\end{gather}
$$

我们证明如果 $C$ 的宽度为 $w$，那么 $g(C)$ 包含于一个宽度 $nMw$ 的立方体中。

设 $\mathbf{a}$ 是 $C$ 的中心，那么 $C$ 包含所有满足 $\lvert \mathbf{x}-\mathbf{a} \rvert\leq w /2$ 的 $\mathbf{x}$。根据中值定理，在 $\mathbf{a}$ 和 $\mathbf{x}$ 的连线上存在一点 $\mathbf{c}_{j}$ 使得

$$
\begin{gather}
g_{j}(\mathbf{x})-g_{j}(\mathbf{a})=Dg_{j}(\mathbf{c}_{j})(\mathbf{x}-\mathbf{a})
\end{gather}
$$

则

$$
\begin{gather}
\lvert g_{j}(\mathbf{x})-g_{j}(\mathbf{a}) \rvert \leq n\lvert Dg_{j}(\mathbf{c}_{j}) \rvert \lvert \mathbf{x}-\mathbf{a} \rvert \leq nM(w /2)
\end{gather}
$$

于是 $g(\mathbf{x})$ 位于这样一个立方体中：它包含所有满足

$$
\begin{gather}
\lvert \mathbf{y}-g(\mathbf{a}) \rvert \leq nM(w /2)
\end{gather}
$$

的 $\mathbf{y}$。这一立方体的宽度为 $nMw$，即证。

**第三步** 我们证明该定理。设 $E$ 是 $A$ 的零测子集，我们证明 $g(E)$ 的测度为零。

设 $C_{i}$ 是一列紧致子集，其并集为 $A$，且 $C_{i}\subset \operatorname{Int}C_{i+1}$。令 $E_{k}=C_{k}\cap E$，则我们只需证明 $g(E_{k})$ 的测度为零。给定 $\varepsilon>0$，我们将用总体积小于 $\varepsilon$ 的立方体覆盖 $g(E_{k})$。

由于 $C_{k}$ 紧致，根据 [[1 The Algebra and Topology of Rn#Theorem 4.9]]，存在 $\delta>0$ 使得 $C_{k}$ 在上确界度量下的 $\delta$-邻域包含于 $\operatorname{Int}C_{k+1}$。取 $M$ 使得

$$
\begin{gather}
\lvert Dg(\mathbf{x}) \rvert \leq M \quad (\mathbf{x}\in C_{k+1})
\end{gather}
$$

应用第一步的结论，用可数个宽度小于 $\delta$，总体积小于

$$
\begin{gather}
\varepsilon'=\frac{\varepsilon}{(nM)^{n}}
\end{gather}
$$

的立方体覆盖 $E_{k}$，记 $D_{1},D_{2},\dots$ 为那些与 $E_{k}$ 相交的立方体。我们有

$$
\begin{gather}
\lvert Dg(\mathbf{x}) \rvert \leq M \quad (\mathbf{x}\in D_{i})
\end{gather}
$$

因此 $g(D_{i})$ 包含在一个宽度 $nM(\operatorname{width}D_{i})$ 的立方体 $D_{i}'$ 中，后者的体积为

$$
\begin{gather}
v(D_{i}')=(nM)^{n} (\operatorname{width}D_{i})^{n}=(nM)^{n}v(D_{i})
\end{gather}
$$

因此覆盖 $g(E_{k})$ 的立方体 $D_{i}'$ 的总体积小于 $(nM)^{n}\varepsilon'=\varepsilon$，这就完成了证明。

![](4-6.png)

### Theorem 18.2

设 $A,B\subset \mathbb{R}^{n}$ 是开集，$g\colon A\to B$ 是 $C^{r}$ 微分同胚。设 $D\subset A$ 是紧致集，$E=g(D)$。

(a) 我们有
$$
\begin{gather}
g(\operatorname{Int}D)=\operatorname{Int}E, \quad g(\operatorname{Bd}D)=\operatorname{Bd}E
\end{gather}
$$
(b) 如果 $D$ 可求体积，那么 $E$ 也可求体积。

#### Proof

(a) 根据定义，$g^{-1}$ 连续，因此对任意开集 $U\subset A$，$g(U)$ 是 $B$ 中的开集。特别地，$g(\operatorname{Int}D)$ 是一个包含于 $g(D)=E$ 的开集，从而

$$
\begin{gather}
g(\operatorname{Int}D)\subset \operatorname{Int}E \tag{1}
\end{gather}
$$

同理，$g$ 将开集 $(\operatorname{Ext}D)\cap A$ 映射到 $B$ 中的一个开集，由于 $g$ 是单射，故 $g((\operatorname{Ext}D)\cap A)$ 与 $g(D)=E$ 不相交，因此

$$
\begin{gather}
g((\operatorname{Ext}D)\cap A) \subset \operatorname{Ext}E \tag{2}
\end{gather}
$$

现在设 $\mathbf{y}\in \operatorname{Bd}E$，由于 $g$ 连续，故 $E$ 是紧致的，从而它包含其边界。则 $\mathbf{y}\in B$，令 $\mathbf{x}\in A$ 使得 $g(\mathbf{x})=\mathbf{y}$。根据 $(1)$，$\mathbf{x}\not\in \operatorname{Int}D$；根据 $(2)$，也有 $\mathbf{x}\not\in \operatorname{Ext}D$，因而 $\mathbf{x}\in \operatorname{Bd}D$，故

$$
\begin{gather}
g(\operatorname{Bd}D)\supset \operatorname{Bd}E
\end{gather}
$$

利用对称性，我们对 $g^{-1}\colon B\to A$ 重复上述论证，得到

$$
\begin{gather}
g^{-1}(\operatorname{Int}E)\subset \operatorname{Int}D \\
g^{-1}(\operatorname{Bd}E)\supset \operatorname{Bd}D
\end{gather}
$$

综上我们就有 $g(\operatorname{Int}D)=\operatorname{Int}E,g(\operatorname{Bd}D)=\operatorname{Bd}E$。

(b) 如果 $D$ 可求体积，那么 $\operatorname{Bd}D$ 的测度为零。根据 [[#Lemma 18.1]]，$g(\operatorname{Bd}D)=\operatorname{Bd}E$ 的测度为零，因而 $E$ 也是可求体积的。

### Definition 18.3 primitive diffeomorphism 最简微分同胚

设 $h\colon A\to B$ 是 $\mathbb{R}^{n}(n\geq 2)$ 中开集之间的微分同胚，定义为

$$
\begin{gather}
h(\mathbf{x})=(h_{1}(\mathbf{x}),\dots,h_{n}(\mathbf{x}))
\end{gather}
$$

给定 $i$，我们说 $h$ 保持第 $i$ 个坐标，如果对 $\mathbf{x}\in A$ 有 $h_{i}(\mathbf{x})=x_{i}$。如果 $h$ 保持某个坐标，我们就称 $h$ 是一个最简微分同胚。

下面的定理表明，任何微分同胚在局部都可以分解为最简微分同胚的复合。这一结果在变量替换定理的证明中起到了重要作用。

### Theorem 18.4

设 $g\colon A\to B$ 是 $\mathbb{R}^{n}(n\geq 2)$ 中开集之间的微分同胚。给定 $\mathbf{a}\in A$，存在 $\mathbf{a}$ 的一个邻域 $U_{0}\subset A$，以及一系列 $\mathbb{R}^{n}$ 中开集之间的微分同胚

$$
\begin{gather}
U_{0} \overset{h_{1}}{\longrightarrow} U_{1} \overset{h_{2}}{\longrightarrow} U_{2} \overset{h_{3}}{\longrightarrow} \cdots \overset{h_{k}}{\longrightarrow} U_{k}
\end{gather}
$$

使得 $g|U_{0}=h_{k}\circ\cdots \circ h_{1}$，且每个 $h_{i}$ 都是最简微分同胚。

#### Proof

**第一步** 我们证明可逆线性变换 $T(\mathbf{x})=C\mathbf{x}$ 可以分解为一系列保持坐标的线性变换。

证明是容易的：可逆矩阵 $C$ 可以写成一系列初等矩阵的乘积。初等矩阵对应的初等变换有

1. 交换两个坐标，
2. 将第 $j$ 个坐标的标量倍加到第 $i$ 个坐标上，
3. 用一个非零标量乘以第 $i$ 个坐标。

变换 (2) 和 (3) 是保持坐标的，下面我们证明变换 (1) 可以写成变换 (2)(3) 的复合。事实上，如下的操作具有交换第 $i$ 行和第 $j$ 行的效果：

$$
\begin{gather}
\begin{matrix}
 & \text{Row}\ i & \text{Row}\ j \\
\text{初始状态} & \mathbf{a} & \mathbf{b} \\
\text{Row}\ i \leftarrow \text{Row}\ i-\text{Row}\ j & \mathbf{a}-\mathbf{b} & \mathbf{b} \\
\text{Row}\ j\leftarrow \text{Row}\ i+\text{Row}\ j & \mathbf{a}-\mathbf{b} & \mathbf{a} \\
\text{Row}\ i \leftarrow \text{Row}\ i-\text{Row}\ j & -\mathbf{b} & \mathbf{a} \\
\text{Row}\ i \leftarrow (-1)\text{Row}\ i & \mathbf{b} & \mathbf{a}
\end{matrix}
\end{gather}
$$

**第二步** 我们证明平移变换 $t(\mathbf{x})=\mathbf{x}+\mathbf{c}$ 可以分解为最简微分同胚的复合。

事实上，

$$
\begin{gather}
t_{1}(\mathbf{x})=\mathbf{x}+(c_{1},0,\dots,0) \\
t_{2}(\mathbf{x})=\mathbf{x}+(0,c_{2},\dots,c_{n})
\end{gather}
$$

都是最简微分同胚，且 $t=t_{2}\circ t_{1}$。

**第三步** 我们证明 $\mathbf{a}=\mathbf{0}$，$g(\mathbf{0})=\mathbf{0}$，且 $Dg(\mathbf{0})=I_{n}$ 的特殊情况。

我们将 $g$ 写成

$$
\begin{gather}
g(\mathbf{x})=(g_{1}(\mathbf{x}),\dots,g_{n}(\mathbf{x}))
\end{gather}
$$

定义 $h\colon A\to \mathbb{R}^{n}$ 为

$$
\begin{gather}
h(\mathbf{x})=(g_{1}(\mathbf{x}),\dots,g_{n-1}(\mathbf{x}),x_{n})
\end{gather}
$$

则 $h(\mathbf{0})=\mathbf{0}$，且

$$
\begin{gather}
Dh(\mathbf{x})=\begin{bmatrix}
\partial (g_{1},\dots,g_{n-1}) / \partial \mathbf{x} \\
0\quad \cdots \quad 0 \quad 1
\end{bmatrix}
\end{gather}
$$

由于 $Dg(\mathbf{0})=I_{n}$，故 $Dh(\mathbf{0})=I_{n}$。从而根据反函数定理，存在 $\mathbf{0}$ 的邻域 $V_{0}$ 和开集 $V_{1}\subset \mathbb{R}^{n}$ 使得 $h\colon V_{0}\to V_{1}$ 是微分同胚。

现在我们定义 $k\colon V_{1}\to \mathbb{R}^{n}$ 为

$$
\begin{gather}
k(\mathbf{y})=(y_{1},\dots,y_{n-1},g_{n}(h^{-1}(\mathbf{y})))
\end{gather}
$$

则 $k(\mathbf{0})=\mathbf{0}$，且

$$
\begin{gather}
Dk(\mathbf{y})=\begin{bmatrix}
I_{n-1} \quad \mathbf{0} \\
D(g_{n}\circ h^{-1})(\mathbf{y})
\end{bmatrix}
\end{gather}
$$

其中

$$
\begin{align}
D(g_{n}\circ h^{-1})(\mathbf{0}) &= Dg_{n}(\mathbf{0})Dh^{-1}(\mathbf{0}) \\
&= Dg_{n}(\mathbf{0}) (Dh(\mathbf{0}))^{-1} \\
&=[0\cdots 0\ 1]I_{n}=[0\cdots 0\ 1]
\end{align}
$$

因此 $Dk(\mathbf{0})=I_{n}$。再次应用反函数定理，存在 $\mathbf{0}$ 的邻域 $W_{1}$ 和开集 $W_{2}\subset \mathbb{R}^{n}$ 使得 $k\colon W_{1}\to W_{2}$ 是微分同胚。

现在令 $W_{0}=h^{-1}(W_{1})$，则微分同胚

$$
\begin{gather}
W_{0} \overset{h}{\longrightarrow} W_{1} \overset{k}{\longrightarrow} W_{2}
\end{gather}
$$

是最简的。下面我们证明 $g|W_{0}=k\circ h$。

给定 $\mathbf{x}\in W_{0}$，令 $\mathbf{y}=h(\mathbf{x})$，则

$$
\begin{gather}
\mathbf{y}=(g_{1}(\mathbf{x}),\dots,g_{n-1}(\mathbf{x}),x_{n}), \quad h^{-1}(\mathbf{y})=\mathbf{x}
\end{gather}
$$

从而

$$
\begin{align}
k(\mathbf{y}) &= (y_{1},\dots,y_{n-1},g_{n}(h^{-1}(\mathbf{y}))) \\
&=(g_{1}(\mathbf{x}),\dots,g_{n-1}(\mathbf{x}),g_{n}(\mathbf{x})) \\
&= g(\mathbf{x})
\end{align}
$$

**第四步** 我们证明该定理。

给定 $g\colon A\to B$ 和 $\mathbf{a}\in A$，令 $C=Dg(\mathbf{a})$，我们定义微分同胚 $t_{1},t_{2},T$ 为

$$
\begin{gather}
t_{1}(\mathbf{x})=\mathbf{x}+\mathbf{a}, \quad t_{2}(\mathbf{x})=\mathbf{x}-g(\mathbf{a}), \quad T(\mathbf{x})=C^{-1}\mathbf{x}
\end{gather}
$$

令 $\tilde{g}=T\circ t_{2}\circ g\circ t_{1}$，则 $\tilde{g}$ 是从 $t_{1}^{-1}(A)$ 到 $T(t_{2}(B))$ 的微分同胚，满足性质

$$
\begin{gather}
\tilde{g}(\mathbf{0})=\mathbf{0}, \quad D\tilde{g}(\mathbf{0})=I_{n}
\end{gather}
$$

根据第三步，存在 $\mathbf{0}$ 的邻域 $W_{0}\subset t_{1}^{-1}(A)$ 使得 $\tilde{g}|W_{0}$ 可以分解为最简微分同胚。令 $W_{2}=\tilde{g}(W_{0})$，并令

$$
\begin{gather}
A_{0}=t_{1}(W_{0}), \quad B_{0}=t_{2}^{-1}(T^{-1}(W_{2}))
\end{gather}
$$

则 $g(A_{0})=B_{0}$，并且 $g|A_{0}$ 等于如下四个函数的复合：

$$
\begin{gather}
A_{0} \overset{t_{1}^{-1}}{\longrightarrow} W_{0} \overset{\tilde{g}}{\longrightarrow} W_{2} \overset{T^{-1}}{\longrightarrow} T^{-1}(W_{2}) \overset{t_{2}^{-1}}{\longrightarrow} B_{0}
\end{gather}
$$

根据第一、二步，$t_{1}^{-1},t_{2}^{-1},T^{-1}$ 都可分解为最简微分同胚，这就完成了证明。

# 19 Proof of the Change of Variables Theorem

现在我们证明积分的变量替换定理，我们将其分成两个引理。

### Lemma 19.1

设 $g\colon A\to B$ 是 $\mathbb{R}^{n}$ 中开集之间的微分同胚，连续函数 $f\colon B\to \mathbb{R}$ 在 $B$ 上可积，则 $(f\circ g)\lvert \det Dg \rvert$ 在 $A$ 上可积，并且

$$
\begin{gather}
\int_{B} f=\int_{A} (f\circ g)\lvert \det Dg \rvert 
\end{gather}
$$

#### Proof

**第一步**

设 $g\colon U\to V$ 和 $h\colon V\to W$ 是微分同胚，我们证明如果引理对 $g$ 和 $h$ 成立，那么它也对 $h\circ g$ 成立。

设连续函数 $f\colon W\to \mathbb{R}$ 在 $W$ 上可积，则根据假设我们可知

$$
\begin{gather}
\int_{W}f=\int_{V} (f\circ h)\lvert \det Dh \rvert =\int_{U} (f\circ h\circ g) \lvert (\det Dh)\circ g \rvert \lvert \det Dg \rvert 
\end{gather}
$$

下面我们只需证明

$$
\begin{gather}
\lvert (\det Dh)\circ g \rvert \lvert \det Dg \rvert =\lvert \det D(h\circ g) \rvert 
\end{gather}
$$

这一结果来源于链式法则：

$$
\begin{gather}
D(h\circ g)(\mathbf{x})=Dh(g(\mathbf{x}))Dg(\mathbf{x})
\end{gather}
$$

从而

$$
\begin{gather}
\det D(h\circ g)=((\det Dh)\circ g)(\det Dg)
\end{gather}
$$

这就是所要证的。

**第二步** 我们证明如果引理在局部对 $g$ 和紧支撑连续函数 $f$ 成立，那么引理在全局对 $g$ 和所有连续函数 $f$ 成立。

具体来说，如果对 $\mathbf{x}\in A$，有 $\mathbf{x}$ 的邻域 $U$ 使得引理对 $g\colon U\to V$ 和紧支撑的连续函数 $f\colon V\to \mathbb{R}$ 成立，那么引理对 $g$ 成立。

这里就是我们使用单位分解的地方。将 $A$ 写成一族开集 $U_{\alpha}$ 的并集，使得如果 $V_{\alpha}=g(U_{\alpha})$，那么引理对 $g\colon U_{\alpha}\to V_{\alpha}$ 和支撑集为 $V_{\alpha}$ 的紧致子集的连续函数 $f\colon V_{\alpha}\to \mathbb{R}$ 成立。

开集 $V_{\alpha}$ 的并集等于 $B$，我们选取 $B$ 的一个紧支撑单位分解 $\{ \phi_{i} \}$，其受 $\{ V_{\alpha} \}$ 的控制。我们证明 $\{ \phi_{i}\circ g \}$ 是 $A$ 上的单位分解，并且是紧支撑的。

首先，对 $\mathbf{x}\in A$ 有 $\phi_{i}(g(\mathbf{x}))\geq 0$。

第二，设 $T_{i}=\operatorname{supp}(\phi_{i})$，则 $g^{-1}(T_{i})$ 是紧致的，而 $\phi_{i}\circ g$ 在 $g^{-1}(T_{i})$ 外消失，故 $S_{i}=\operatorname{supp}(\phi_{i}\circ g)$ 作为 $g^{-1}(T_{i})$ 中的闭集是紧致的。

第三，我们验证局部有限性。设 $\mathbf{x}\in A$，点 $\mathbf{y}=g(\mathbf{x})$ 有一个邻域 $W$ 使得它仅和有限个 $T_{i}$ 相交，因此 $g^{-1}(W)$ 是 $\mathbf{x}$ 的一个邻域，其只和有限个 $S_{i}\subset g^{-1}(T_{i})$ 相交。

第四，我们有

$$
\begin{gather}
\sum \phi_{i}(g(\mathbf{x}))=\sum \phi_{i}(\mathbf{y})=1
\end{gather}
$$

因此 $\{ \phi_{i}\circ g \}$ 是 $A$ 上的紧支撑单位分解。

现在设连续函数 $f\colon B\to \mathbb{R}$ 在 $B$ 上可积，则由 [[#Theorem 16.6]] 得

$$
\begin{gather}
\int_{B} f=\sum_{i=1}^{\infty} \int_{B} \phi_{i}f
\end{gather}
$$

给定 $i$，取 $\alpha$ 使得 $T_{i}\subset V_{\alpha}$。函数 $\phi_{i}f$ 在 $B$ 上连续，且在紧致集 $T_{i}$ 外消失，因此由 [[#Lemma 16.5]] 有

$$
\begin{gather}
\int_{B} \phi_{i} f=\int_{T_{i}} \phi_{i} f=\int_{V_{\alpha}} \phi_{i} f
\end{gather}
$$

根据假设，引理对 $g\colon U_{\alpha}\to V_{\alpha}$ 和 $\phi_{i}f$ 成立，故

$$
\begin{gather}
\int_{V_{\alpha}} \phi_{i} f=\int_{U_{\alpha}} (\phi_{i}\circ g) (f\circ g) \lvert \det Dg \rvert 
\end{gather}
$$

右侧的积分项在紧致集 $S_{i}$ 外消失，再次应用 [[#Lemma 16.5]] 得

$$
\begin{gather}
\int_{B} \phi_{i}f=\int_{A} (\phi_{i}\circ g)(f\circ g) \lvert \det Dg \rvert 
\end{gather}
$$

两边对 $i$ 求和得到

$$
\begin{gather}
\int_{B} f=\sum_{i=1}^{\infty} \int_{A} (\phi_{i}\circ g)(f\circ g)\lvert \det Dg \rvert 
\end{gather}
$$

由于 $\lvert f \rvert$ 在 $B$ 上可积，因此在上式中用 $\lvert f \rvert$ 替换 $f$，等式仍然成立。又由于 $\{ \phi_{i}\circ g \}$ 是 $A$ 上的单位分解，根据 [[#Theorem 16.6]] 可知 $(f\circ g)\lvert \det Dg \rvert$ 在 $A$ 上可积，并且

$$
\begin{gather}
\int_{B} f=\int_{A} (f\circ g)\lvert \det Dg \rvert 
\end{gather}
$$

**第三步** 我们证明引理在 $n=1$ 时成立。

设 $g\colon A\to B$ 是 $\mathbb{R}$ 中开集之间的微分同胚。给定 $x \in A$，令 $I$ 为 $A$ 中包含 $x$ 的闭区间，$J=g(I)$。根据 [[#Theorem 18.2]]，$J$ 是一个闭区间，且 $g(\operatorname{Int}I)=\operatorname{Int}J$。

由于 $x$ 是任意的，根据第二步的结论，我们只需对 $g\colon \operatorname{Int}I\to \operatorname{Int}J$ 以及支撑集为 $\operatorname{Int}J$ 中的紧致集的连续函数 $f\colon \operatorname{Int}J\to \mathbb{R}$ 证明即可。这就是说，我们需要验证

$$
\begin{gather}
\int_{\operatorname{Int}J} f=\int_{\operatorname{Int}I} (f\circ g)\lvert g' \rvert 
\end{gather}
$$

这一证明是容易的。首先我们令 $f$ 在 $\operatorname{Bd}J$ 上消失，这就将 $f$ 扩张为了一个 $J$ 上的连续函数。于是上式就等价于普通积分的等式

$$
\begin{gather}
\int_{J} f=\int_{I} (f\circ g)\lvert g' \rvert 
\end{gather}
$$

后者由 [[#Theorem 17.1]] 给出。

**第四步** 令 $n>1$。我们证明如果引理对最简微分同胚成立，那么引理就对任意微分同胚 $g$ 成立。

设 $g\colon A\to B$ 是微分同胚。给定 $\mathbf{x}\in A$，[[#Theorem 18.4]] 表明存在 $\mathbf{x}$ 的邻域 $U_{0}$，以及一系列最简微分同胚

$$
\begin{gather}
U_{0} \overset{h_{1}}{\longrightarrow} U_{1} \overset{h_{2}}{\longrightarrow} U_{2} \overset{h_{3}}{\longrightarrow} \cdots \overset{h_{k}}{\longrightarrow} U_{k}
\end{gather}
$$

其复合为 $g|U_{0}$。根据假设，引理对每个 $h_{i}$ 成立，于是根据第一步，它对 $g|U_{0}$ 成立。再由第二步可知引理对 $g$ 成立。

**第五步** 我们证明如果引理对 $n-1$ 成立，那么它对 $n$ 成立。从而由归纳法知引理得证。

根据第四步的结论，我们只需证明引理对最简微分同胚 $h\colon U\to V$ 成立。不妨设 $h$ 保持最后一个坐标。

设 $\mathbf{p}\in U,\mathbf{q}=h(\mathbf{p})$，选取长方体 $Q\subset V$ 包含 $\mathbf{q}$，令 $S=h^{-1}(Q)$。根据 [[#Theorem 18.2]]，$h\colon \operatorname{Int}S\to \operatorname{Int}Q$ 是一个微分同胚，并且根据第二步，我们只需证明引理对 $h\colon \operatorname{Int}S\to \operatorname{Int}Q$ 和支撑集是 $\operatorname{Int}S$ 的紧致子集的连续函数 $f\colon \operatorname{Int}S\to \mathbb{R}$ 成立。

$(f\circ h)\lvert \det Dh \rvert$ 在 $\operatorname{Int}S$ 内的一个紧致集外消失，因此它在 $\operatorname{Int}S$ 上可积（[[#Lemma 16.5]]）。我们需要证明

$$
\begin{gather}
\int_{\operatorname{Int}Q} f=\int_{\operatorname{Int}S} (f\circ h)\lvert \det Dh \rvert 
\end{gather}
$$

由于上式中的两个积分作为普通积分也存在，因此它等价于作为普通积分的相应等式。

令 $f$ 在 $\operatorname{Int}Q$ 外消失，这使得 $f$ 的定义域扩张为 $\mathbb{R}^{n}$。并且我们定义 $F$ 在 $\operatorname{Int}S$ 上等于 $(f\circ h)\lvert \det Dh \rvert$，在其余位置为零。则 $f$ 和 $F$ 都是连续的，而我们需要证明等式

$$
\begin{gather}
\int_{Q} f=\int_{S} F
\end{gather}
$$

长方体 $Q$ 具有形式 $D\times I$，其中 $D$ 是 $\mathbb{R}^{n-1}$ 中的长方体，$I$ 是一个闭区间。由于 $S$ 紧致，它在 $\mathbb{R}^{n-1}\times 0$ 上的投影也是紧致的，因此该投影包含在 $E\times 0$ 中，其中 $E$ 是 $\mathbb{R}^{n-1}$ 中的长方体。由于 $h$ 保持最后一个坐标，故 $S$ 包含在 $E\times I$ 中。

![](4-7.png)

由于 $F$ 在 $S$ 外消失，因此要证的等式等价于

$$
\begin{gather}
\int_{E\times I} f=\int_{E\times I} F
\end{gather}
$$

应用 Fubini 定理，其等价于

$$
\begin{gather}
\int_{t \in I} \int_{\mathbf{y}\in D} f(\mathbf{y},t)=\int_{t \in I} \int_{\mathbf{x}\in E} F(\mathbf{x},t)
\end{gather}
$$

下面我们证明内层的积分相等。

$U$ 和 $V$ 与 $\mathbb{R}^{n-1}\times t$ 的交集具有形式 $U_{t}\times t$ 和 $V_{t}\times t$，其中 $U_{t},V_{t}$ 都是 $\mathbb{R}^{n-1}$ 中的开集。类似地，$S$ 与 $\mathbb{R}^{n-1}\times t$ 的交集具有形式 $S_{t}\times t$，其中 $S_{t}$ 是 $\mathbb{R}^{n-1}$ 中的紧致集。由于 $F$ 在 $S$ 外消失，因此内层积分的等式可以写成

$$
\begin{gather}
\int_{\mathbf{y}\in D} f(\mathbf{y},t)=\int_{\mathbf{x}\in S_{t}} F(\mathbf{x},t)
\end{gather}
$$

而这又等价于

$$
\begin{gather}
\int_{\mathbf{y}\in V_{t}} f(\mathbf{y},t)=\int_{\mathbf{x}\in U_{t}} F(\mathbf{x},t)
\end{gather}
$$

这是一个 $n-1$ 维积分，因而可以使用归纳假设。

微分同胚 $h\colon U\to V$ 具有形式

$$
\begin{gather}
h(\mathbf{x},t)=(k(\mathbf{x},t),t)
\end{gather}
$$

其中 $k\colon U\to \mathbb{R}^{n-1}$ 是 $C^{1}$ 函数。$h$ 的导数具有形式

$$
\begin{gather}
Dh=\begin{bmatrix}
\partial k / \partial \mathbf{x} & \partial k / \partial t \\
0\ \cdots \ 0 & 1
\end{bmatrix}
\end{gather}
$$

因此 $\det Dh=\det \partial k /\partial \mathbf{x}$。固定 $t$，$\mathbf{x}\mapsto k(\mathbf{x},t)$ 是一个从 $U_{t}$ 到 $V_{t}$ 的 $C^{1}$ 双射，又 $\det \partial k /\partial \mathbf{x}=\det Dh\neq 0$，故 $k$ 事实上一个微分同胚。

应用归纳假设，我们有

$$
\begin{gather}
\int_{\mathbf{y}\in V_{t}} f(\mathbf{y},t)=\int_{\mathbf{x}\in U_{t}} f(k(\mathbf{x},t),t) \lvert \det \partial k / \partial \mathbf{x} \rvert 
\end{gather}
$$

右侧的积分项正是 $F(\mathbf{x},t)$，这就完成了证明。

### Lemma 19.2

设 $g\colon A\to B$ 是 $\mathbb{R}^{n}$ 中开集之间的微分同胚，$f\colon B\to \mathbb{R}$ 是连续函数。如果 $(f\circ g)\lvert \det Dg \rvert$ 在 $A$ 上可积，那么 $f$ 在 $B$ 上可积。

#### Proof

我们将 [[#Lemma 19.1]] 应用于微分同胚 $g^{-1}\colon B\to A$。由于连续函数 $F=(f\circ g)\lvert \det Dg \rvert$ 在 $A$ 上连续且可积，故

$$
\begin{gather}
(F\circ g^{-1}) \lvert \det Dg^{-1} \rvert
\end{gather}
$$

在 $B$ 上可积。而这一函数等于 $f$，因为对于 $\mathbf{y}=g(\mathbf{x})$，有

$$
\begin{gather}
Dg^{-1}(\mathbf{y})=(Dg(\mathbf{x}))^{-1}
\end{gather}
$$

从而

$$
\begin{gather}
(F\circ g^{-1})(\mathbf{y})\lvert \det Dg^{-1}(\mathbf{y}) \rvert =F(\mathbf{x}) \lvert \det Dg(\mathbf{x}) \rvert ^{-1}=f(\mathbf{y})
\end{gather}
$$

这就完成了证明。

# 20 Applications of Change of Variables

## The Meaning of the Determinant

现在我们可以给出行列式的一个几何意义。其一是线性变换下图形的“放缩倍数”。

### Theorem 20.1

设 $A$ 是 $n\times n$ 矩阵，$h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 为线性变换 $h(\mathbf{x})=A\mathbf{x}$。设 $S\subset \mathbb{R}^{n}$ 是可求体积集，$T=h(S)$，则

$$
\begin{gather}
v(T)=\lvert \det T \rvert v(S)
\end{gather}
$$

#### Proof

首先考虑 $A$ 可逆的情况。此时 $h$ 是 $\mathbb{R}^{n}$ 上的微分同胚，$h(\operatorname{Int}S)=\operatorname{Int}T$，且 $T$ 是可求体积的。根据变量替换定理，我们有

$$
\begin{gather}
v(T)=v(\operatorname{Int}T)=\int_{\operatorname{Int}T}1=\int_{\operatorname{Int}S} \lvert \det Dh \rvert 
\end{gather}
$$

于是

$$
\begin{gather}
v(T)=\int_{\operatorname{Int}S} \lvert \det A \rvert =\lvert \det A \rvert v(S)
\end{gather}
$$

现在假设 $A$ 不可逆。此时 $\det A=0$，我们来证明 $v(T)=0$。

$h$ 将 $\mathbb{R}^{n}$ 映射到 $\mathbb{R}^{n}$ 中的一个低维子空间 $V$ 上，后者在 $\mathbb{R}^{n}$ 中的测度为零。由于 $S$ 有界，故 $T$ 有界，因此 $\overline{T}$ 是紧致集。函数 $1_{T}$ 在 $\overline{T}$ 上连续，而在 $\overline{T}$ 外消失，因此 $\int_{T}1$ 存在且为零。

行列式的第二个几何表示是平行六面体的体积。

### Definition 20.2 parallelepiped 平行六面体

设 $\mathbf{a}_{1},\dots,\mathbf{a}_{k}$ 是 $\mathbb{R}^{n}$ 中的线性无关向量，我们定义 $k$ 维平行六面体 $\mathcal{P}(\mathbf{a}_{1},\dots,\mathbf{a}_{k})$ 为

$$
\begin{gather}
\mathcal{P}(\mathbf{a}_{1},\dots,\mathbf{a}_{k})=\{ c_{1}\mathbf{a}_{1}+\dots+c_{k}\mathbf{a}_{k} : 0\leq c_{i}\leq 1 \}
\end{gather}
$$

向量 $\mathbf{a}_{1},\dots,\mathbf{a}_{k}$ 称为它的边。

一个二维平行六面体通常称为一个平行四边形，而一个三维平行六面体是我们通常指代的“狭义”平行六面体。

后续我们将定义 $k$-平行六面体的 $k$ 维体积。而在 $k=n$ 时，我们已经有了一个体积定义，它有如下公式：

### Theorem 20.3

设 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 是 $\mathbb{R}^{n}$ 中的线性无关向量，$A=[\mathbf{a}_{1}\cdots \mathbf{a}_{n}]$ 是 $n\times n$ 矩阵，则

$$
\begin{gather}
v(\mathcal{P}(\mathbf{a}_{1},\dots,\mathbf{a}_{n}))=\lvert \det A \rvert 
\end{gather}
$$

#### Proof

考虑线性变换 $h(\mathbf{x})=A\mathbf{x}$，则 $h$ 将标准基 $\mathbf{e}_{j}$ 映射到 $\mathbf{a}_{j}$，因此 $h$ 将单位立方体 $I^{n}=[0,1]^{n}$ 映射到平行六面体 $\mathcal{P}(\mathbf{a}_{1},\dots,\mathbf{a}_{n})$，从而由 [[#Theorem 20.1]] 得

$$
\begin{gather}
v(\mathcal{P}(\mathbf{a}_{1},\dots,\mathbf{a}_{n}))=\lvert \det A \rvert v(I^{n})=\lvert \det A \rvert 
\end{gather}
$$

### Example 20.4

在微积分中，我们研究了以上公式的三维版本。其中，一个以 $\mathbf{a},\mathbf{b},\mathbf{c}$ 为边的平行六面体的有符号体积可以用三重积

$$
\begin{gather}
\mathbf{a}\cdot (\mathbf{b}\times \mathbf{c})=\det[\mathbf{a}\ \mathbf{b}\ \mathbf{c}]
\end{gather}
$$

表示，其符号取决于 $\mathbf{a},\mathbf{b},\mathbf{c}$ 是“右手的”还是“左手的”。现在我们将向量的“手性”，或称为定向扩展到任意有限维向量空间。

### Definition 20.5 frame 标架，orientation 定向

设 $V$ 是 $n$ 维向量空间。$V$ 中的一个线性无关的 $n$-元组 $(\mathbf{a}_{1},\dots,\mathbf{a}_{n})$ 称为 $V$ 的一个 $n$-标架。在 $\mathbb{R}^{n}$ 中，我们称一个标架是右手的，如果

$$
\begin{gather}
\det [\mathbf{a}_{1}\cdots \mathbf{a}_{n}]>0
\end{gather}
$$

否则我们就称该标架是左手的。$\mathbb{R}^{n}$ 上所有右手（左手）标架的集合称为 $\mathbb{R}^{n}$ 的一个定向。对于一般的 $V$，选取一个线性同构 $T\colon \mathbb{R}^{n}\to V$，并定义 $V$ 的一个定向为所有具有形式 $(T(\mathbf{a}_{1}),\dots,T(\mathbf{a}_{n}))$ 的标架构成的集合，其中 $(\mathbf{a}_{1},\dots,\mathbf{a}_{n})$ 是 $\mathbb{R}^{n}$ 中的右手（左手）标架。因此 $V$ 有两个定向，它们互相称为对方的相反定向。

容易看出以上定义不依赖于特定 $T$ 的选取，因为

$$
\begin{gather}
\det[T(\mathbf{a}_{1})\cdots T(\mathbf{a}_{n})]=(\det T)(\det[\mathbf{a}_{1}\cdots \mathbf{a}_{n}])
\end{gather}
$$

然而，在一般的 $V$ 上，不存在一个良定的“右手标架”概念，尽管其上定向的概念是良定的。

### Example 20.6

在 $\mathbb{R}$ 中，一个标架就是一个非零标量，它是右手的当且仅当它是正数。在 $\mathbb{R}^{2}$ 中，一个标架 $(\mathbf{a}_{1},\mathbf{a}_{2})$ 是右手的，如果我们可以将 $\mathbf{a}_{1}$ 以小于 $\pi$ 的角度逆时针旋转到 $\mathbf{a}_{2}$ 的方向。在 $\mathbb{R}^{3}$ 中，一个标架 $(\mathbf{a}_{1},\mathbf{a}_{2},\mathbf{a}_{3})$ 是右手的如果它满足“右手法则”：将右手的四指沿 $\mathbf{a}_{1}$ 到 $\mathbf{a}_{2}$ 的方向弯曲，此时大拇指就指向 $\mathbf{a}_{3}$ 的方向。

![](4-8.png)

### Theorem 20.7

设 $C$ 是可逆 $n\times n$ 矩阵，令 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 为线性变换 $h(\mathbf{x})=C\mathbf{x}$。设 $(\mathbf{a}_{1},\dots,\mathbf{a}_{n})$ 为 $\mathbb{R}^{n}$ 中的一个标架，则如果 $\det C>0$，那么标架

$$
\begin{gather}
(\mathbf{a}_{1},\dots,\mathbf{a}_{n}) \quad \text{and} \quad (h(\mathbf{a}_{1}),\dots,h(\mathbf{a}_{n}))
\end{gather}
$$

属于 $\mathbb{R}^{n}$ 的相同定向；而如果 $\det C<0$，那么它们属于 $\mathbb{R}^{n}$ 的相反定向。

如果 $\det C>0$，我们称 $h$ 是保持定向的；如果 $\det C<0$，我们称 $h$ 是反转定向的。

#### Proof

我们有

$$
\begin{gather}
\det [h(\mathbf{a}_{1})\cdots h(\mathbf{a}_{n})]=(\det C)(\det[\mathbf{a}_{1},\dots,\mathbf{a}_{n}])
\end{gather}
$$

如果 $\det C>0$，那么两个行列式同号，反之则符号相反。

## Invariance of Volume under Isometries

### Definition 20.8 orthogonal 正交的，orthonormal 标准正交的

称 $\mathbf{a}_{1},\dots,\mathbf{a}_{k}\in \mathbb{R}^{n}$ 是正交向量组，如果对 $i\neq j$ 有 $\langle \mathbf{a}_{i},\mathbf{a}_{j} \rangle=0$。称它是一个标准正交向量组，如果它进一步还满足 $\langle \mathbf{a}_{i},\mathbf{a}_{i} \rangle=1$。

显然，如果 $\mathbf{a}_{1},\dots,\mathbf{a}_{k}$ 正交且非零，那么 $\mathbf{a}_{1} /\lVert \mathbf{a}_{1} \rVert,\dots,\mathbf{a}_{k} /\lVert \mathbf{a}_{k} \rVert$ 是一个标准正交向量组。

正交且其中向量非零的向量组总是线性无关的。特别地，正交且非零的 $n$ 个向量可以构成 $\mathbb{R}^{n}$ 的一个正交基。将其归一化即可得到 $\mathbb{R}^{n}$ 的一个标准正交基。

### Definition 20.9 orthogonal matrix 正交矩阵

一个 $n\times n$ 矩阵 $A$ 称为是一个正交矩阵，如果 $A$ 的列构成了一个标准正交向量组。等价地，矩阵 $A$ 是一个正交矩阵，如果

$$
\begin{gather}
A^{T}A=I_{n}
\end{gather}
$$

上式表明 $A^{T}$ 是 $A$ 的左逆，于是由 [[1 The Algebra and Topology of Rn#Theorem 2.8]] 知 $A^{T}$ 也是右逆，从而 $A^{T}=A^{-1}$。

此外，如果 $A$ 是正交矩阵，那么 $\lvert \det A \rvert=1$。因为

$$
\begin{gather}
(\det A)^{2}=(\det A^{T})(\det A)=\det I_{n}=1
\end{gather}
$$

所有正交矩阵构成的集合，连带着其上的矩阵乘法，构成了一个群。这就是以下定理的内容：

### Theorem 20.10

设 $A,B,C$ 为正交 $n\times n$ 矩阵，则

1. $AB$ 是正交矩阵，
2. $A(BC)=(AB)C$，
3. 存在正交矩阵 $I_{n}$ 使得 $AI_{n}=I_{n}A=A$，
4. 存在正交矩阵 $A^{-1}$ 使得 $AA^{-1}=A^{-1}A=I_{n}$。

#### Proof

要证 (1)，我们计算

$$
\begin{gather}
(AB)^{T}(AB)=B^{T}A^{T}AB=B^{T}B=I_{n}
\end{gather}
$$

(2) 由矩阵乘法的性质得到，(3) 由 $I_{n}$ 正交的事实给出。最后，对于 (4)，我们可以验证 $A^{-1}=A^{T}$。

### Definition 20.11 orthogonal transformation 正交变换

一个线性映射 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 定义为

$$
\begin{gather}
h(\mathbf{x})=A\mathbf{x}
\end{gather}
$$

称为一个正交变换，如果 $A$ 是正交矩阵。等价地，$h$ 是正交变换如果它将标准基 $\mathbf{e}_{1},\dots,\mathbf{e}_{n}$ 映射到 $\mathbb{R}^{n}$ 的一个标准正交基。

### Definition 20.12 isometry 等距映射

称 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 是一个（Euclidean）等距映射，如果

$$
\begin{gather}
\lVert h(\mathbf{x})-h(\mathbf{y}) \rVert =\lVert \mathbf{x}-\mathbf{y} \rVert \quad (\mathbf{x},\mathbf{y}\in \mathbb{R}^{n})
\end{gather}
$$

换句话说，等距映射是一个保持 Euclidean 范数的映射。

### Theorem 20.13

设 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 满足 $h(\mathbf{0})=\mathbf{0}$。

(a) $h$ 是等距映射当且仅当它保持内积。
(b) $h$ 是等距映射当且仅当它是正交变换。

#### Proof

(a) 给定 $\mathbf{x},\mathbf{y}$，我们有

$$
\begin{align}
\lVert h(\mathbf{x})-h(\mathbf{y}) \rVert ^{2} &= \langle h(\mathbf{x}),h(\mathbf{x}) \rangle -2\langle h(\mathbf{x}),h(\mathbf{y}) \rangle +\langle h(\mathbf{y}),h(\mathbf{y}) \rangle \tag{1} \\
\lVert \mathbf{x}-\mathbf{y} \rVert ^{2} &= \langle \mathbf{x},\mathbf{x} \rangle -2\langle \mathbf{x},\mathbf{y} \rangle +\langle \mathbf{y},\mathbf{y} \rangle \tag{2}
\end{align}
$$

如果 $h$ 保持内积，那么 $(1)$ 和 $(2)$ 中等式的右侧相等，从而 $h$ 保持范数。反之，如果 $h$ 保持范数，则我们有

$$
\begin{gather}
\lVert h(\mathbf{x}) \rVert =\lVert h(\mathbf{x})-h(\mathbf{0}) \rVert =\lVert \mathbf{x}-\mathbf{0} \rVert =\lVert \mathbf{x} \rVert 
\end{gather}
$$

因此 $(1)$ 中右侧的第一项和第三项等于 $(2)$ 中右侧的第一项和第三项。根据假设，等式左侧的项相同，因此

$$
\begin{gather}
\langle h(\mathbf{x}),h(\mathbf{y}) \rangle =\langle \mathbf{x},\mathbf{y} \rangle 
\end{gather}
$$

(b) 设 $h(\mathbf{x})=A\mathbf{x}$ 是正交变换，我们要证 $h$ 是等距映射。根据 (a)，我们只需证明 $h$ 保持内积，而 $\mathbb{R}^{n}$ 上的内积具有形式

$$
\begin{gather}
\langle h(\mathbf{x}),h(\mathbf{y}) \rangle =h(\mathbf{x})^{T} h(\mathbf{y})
\end{gather}
$$

其中我们把 $\mathbf{x}\in \mathbb{R}^{n}$ 与列向量等同。此时我们有

$$
\begin{gather}
h(\mathbf{x})^{T}h(\mathbf{y})=(A\mathbf{x})^{T}(A\mathbf{y})=\mathbf{x}^{T} A^{T}A\mathbf{y}=\mathbf{x}^{T}\mathbf{y}
\end{gather}
$$

即证 $h$ 保持内积。

反之，设 $h$ 是等距映射。令 $\mathbf{a}_{i}=h(\mathbf{e}_{i})$，$A=[\mathbf{a}_{1}\cdots \mathbf{a}_{n}]$。由于 $h$ 保持内积，因此 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 的标准正交的，从而 $A$ 是正交矩阵。下面我们要证 $h(\mathbf{x})=A\mathbf{x}$。

由于 $\mathbf{a}_{i}$ 构成了 $\mathbb{R}^{n}$ 的一个基，对 $\mathbf{x}\in \mathbb{R}^{n}$，向量 $h(\mathbf{x})$ 可以唯一地写成

$$
\begin{gather}
h(\mathbf{x})=\sum_{i=1}^{n} \alpha_{i}(\mathbf{x})\mathbf{a}_{i}
\end{gather}
$$

于是

$$
\begin{gather}
\alpha_{j}(\mathbf{x})=\langle h(\mathbf{x}),\mathbf{a}_{j} \rangle =\langle h(\mathbf{x}),h(\mathbf{e}_{j}) \rangle =\langle \mathbf{x},\mathbf{e}_{j} \rangle =x_{j}
\end{gather}
$$

因此

$$
\begin{gather}
h(\mathbf{x})=\sum_{i=1}^{n} x_{i}\mathbf{a}_{i}=[\mathbf{a}_{1}\cdots \mathbf{a}_{n}] \begin{bmatrix}
x_{1} \\
\vdots \\
x_{n}
\end{bmatrix}=A\mathbf{x}
\end{gather}
$$

### Theorem 20.14

设 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$，则 $h$ 是等距映射当且仅当 $h$ 具有形式

$$
\begin{gather}
h(\mathbf{x})=A\mathbf{x}+\mathbf{p} \quad (\mathbf{x}\in \mathbb{R}^{n})
\end{gather}
$$

其中 $A$ 是正交矩阵。

换句话说，一个等距映射就是一个正交变换与一个平移的复合。

#### Proof

令 $\mathbf{p}=h(\mathbf{0})$，定义 $k(\mathbf{x})=h(\mathbf{x})-\mathbf{p}$，则

$$
\begin{gather}
\lVert k(\mathbf{x})-k(\mathbf{y}) \rVert =\lVert h(\mathbf{x})-h(\mathbf{y}) \rVert 
\end{gather}
$$

因此 $k$ 是等距映射当且仅当 $h$ 是等距映射。

由于 $k(\mathbf{0})=\mathbf{0}$，因此由 [[#Theorem 20.13]] 得 $k$ 是等距映射当且仅当 $k(\mathbf{x})=A\mathbf{x}$，其中 $A$ 是正交矩阵，这等价于 $h(\mathbf{x})=A\mathbf{x}+\mathbf{p}$。

最后我们来证明，在等距映射下，集合的体积保持不变。

### Theorem 20.15

设 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 是等距映射，如果 $S\subset \mathbb{R}^{n}$ 可求体积，那么 $T=h(S)$ 可求体积，并且 $v(T)=v(S)$。

#### Proof

$h$ 具有形式 $h(\mathbf{x})=A\mathbf{x}+\mathbf{p}$，其中 $A$ 是正交的。则 $Dh(\mathbf{x})=A$，从而由变量替换定理得

$$
\begin{gather}
v(T)=\lvert \det A \rvert v(S)=v(S)
\end{gather}
$$

