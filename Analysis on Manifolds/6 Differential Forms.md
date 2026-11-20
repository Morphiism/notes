我们已经讨论了多元微积分的两个主题——微分与积分，现在我们转向第三个主题。这一主题通常称为“向量积分学”，其中我们研究向量场的梯度、散度和旋度，并且其中的主定理以 Green、Gauss 和 Stokes 的名字来命名。在本章中，我们将讨论 $k$-流形上的对应物：微分形式。要正确地描述这类对象，我们需要一些更为高级的概念，它们构成了线性代数的后续学科，称为多线性代数。

# 26 Multilinear Algebra

## Tensors

### Definition 26.1 tensor 张量

设 $V$ 是向量空间，一个函数 $f\colon V^{k}\to \mathbb{R}$ 称为是关于第 $i$ 个坐标线性的，如果给定向量 $\mathbf{v}_{j},j\neq i$，定义为

$$
\begin{gather}
T(\mathbf{v})=f(\mathbf{v}_{1},\dots,\mathbf{v}_{i-1},\mathbf{v},\mathbf{v}_{i+1},\dots,\mathbf{v}_{k})
\end{gather}
$$

的函数 $T\colon V\to \mathbb{R}$ 是线性的。称 $f$ 是多线性的，如果它对每个坐标都是线性的。这样的函数 $f$ 也称为是一个 $k$ 阶张量，或 $k$-张量。我们记 $V$ 上所有 $k$-张量构成的集合为 $\mathcal{L}^{k}(V)$。如果 $k=1$，那么 $\mathcal{L}^{1}(V)$ 就是 $V$ 上所有线性泛函构成的集合，它称为 $V$ 的对偶空间，记作 $V^{*}$。

### Theorem 26.2

$V$ 上所有 $k$-张量构成的集合可以构成一个向量空间，如果我们定义

$$
\begin{gather}
(f+g)(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=f(\mathbf{v}_{1},\dots,\mathbf{v}_{k})+g(\mathbf{v}_{1},\dots,\mathbf{v}_{k}) \\
(cf)(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=cf(\mathbf{v}_{1},\dots,\mathbf{v}_{k})
\end{gather}
$$

就像一个从 $V$ 到 $W$ 的线性变换可以由其在 $V$ 的基上的取值唯一确定一样，$V$ 上的一个 $k$-张量同样由其在 $V$ 的基向量的 $k$-元组上的取值唯一确定，下面我们就来证明这一点。

### Lemma 26.3

设 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 是 $V$ 的基，如果 $f,g\colon V^{k}\to \mathbb{R}$ 是 $k$-张量，并且对任意 $\{ 1,\dots,n \}$ 上的 $k$-元组 $I=(i_{1},\dots,i_{k})$ 有

$$
\begin{gather}
f(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})=g(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})
\end{gather}
$$

那么 $f=g$。

#### Proof

给定 $V$ 上的 $k$-元组 $(\mathbf{v}_{1},\dots,\mathbf{v}_{k})$，我们将每个 $\mathbf{v}_{i}$ 唯一地表示为基向量的线性组合

$$
\begin{gather}
\mathbf{v}_{i}=\sum_{j=1}^{n} c_{ij}\mathbf{a}_{j}
\end{gather}
$$

则我们有

$$
\begin{gather}
f(\mathbf{v}_{1},\dots,\mathbf{v}_{k}) = \sum_{1\leq j_{1},\dots,j_{k}\leq n} c_{1j_{1}} \cdots c_{k j_{k}} f(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})
\end{gather}
$$

在上式中用 $g$ 替换 $f$，等式同样成立。根据假设，我们即得 $f=g$。

### Theorem 26.4

设 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 是 $V$ 的基，$I=(i_{1},\dots,i_{k})$ 是 $\{ 1,\dots,n \}$ 上的 $k$-元组。则存在唯一的 $k$-张量 $\phi_{I}$，使得对任意 $\{ 1,\dots,n \}$ 上的 $k$-元组 $J=(j_{1},\dots,j_{k})$ 有

$$
\begin{gather}
\phi_{I}(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})=\begin{cases}
0, & I\neq J \\
1, & I=J
\end{cases}
\end{gather}
$$

这些 $k$-张量 $\phi_{I}$ 构成了 $\mathcal{L}^{k}(V)$ 的一个基。

我们称张量 $\phi_{I}$ 为 $V$ 上对应于基 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 的基本 $k$-张量。由于它们构成了 $\mathcal{L}^{k}(V)$ 的一个基，并且 $\{ 1,\dots,n \}$ 上共有 $n^{k}$ 个不同的 $k$-元组，因此 $\mathcal{L}^{k}(V)$ 的维数为 $n^{k}$。当 $k=1$ 时，$V^{*}$ 的基 $\phi_{1},\dots,\phi_{n}$ 称为 $V$ 上给定基的对偶基。

#### Proof

唯一性由 [[#Lemma 26.3]] 给出。下面我们来证明存在性。

首先考虑 $k=1$ 的情况。已知我们可以通过选取线性变换在基上的取值来确定一个线性变换，因此存在唯一的线性变换 $\phi_{i}\colon V\to \mathbb{R}$ 满足

$$
\begin{gather}
\phi_{i}(\mathbf{a}_{j})=\delta_{ij}
\end{gather}
$$

这些就是所求的 $1$-张量。对于 $k>1$，我们定义 $\phi_{I}$ 为

$$
\begin{gather}
\phi_{I}(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=\phi_{i_{1}}(\mathbf{v}_{1}) \cdots \phi_{i_{k}}(\mathbf{v}_{k})
\end{gather}
$$

则由于各 $\phi_{i}$ 是线性的，故 $\phi_{I}$ 是多线性的。容易验证 $\phi_{I}(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})=1$ 当且仅当 $I=J$。

下面我们证明 $\phi_{I}$ 构成了 $\mathcal{L}^{k}(V)$ 的一个基。我们证明每个张量都可以写成基本张量的唯一线性组合。给定 $k$-张量 $f$，对每个 $k$-元组 $I=(i_{1},\dots,i_{k})$，我们定义

$$
\begin{gather}
d_{I}=f(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})
\end{gather}
$$

然后考虑张量

$$
\begin{gather}
g=\sum_{J} d_{J} \phi_{J}
\end{gather}
$$

则 $g(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})=d_{I}$，从而由 [[#Lemma 26.3]] 知 $f=g$。

通过在每个 $(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})$ 上取值，我们可以证明各 $\phi_{I}$ 线性无关，这就完成了证明。

### Example 26.5

考虑 $V=\mathbb{R}^{n}$。设 $\mathbf{e}_{1},\dots,\mathbf{e}_{n}$ 为 $\mathbb{R}^{n}$ 上的标准基，$\phi_{1},\dots,\phi_{n}$ 为其对偶基。则如果 $\mathbf{x}=(x_{1},\dots,x_{n})$，那么

$$
\begin{gather}
\phi_{i}(\mathbf{x})=\phi_{i}(x_{1}\mathbf{e}_{1}+\dots+x_{n}\mathbf{e}_{n})=x_{i}
\end{gather}
$$

因此 $\phi_{i}\colon \mathbb{R}^{n}\to \mathbb{R}$ 就是在第 $i$ 个坐标上的投影函数。

更一般地，给定 $I=(i_{1},\dots,i_{k})$，基本张量 $\phi_{I}$ 定义为

$$
\begin{gather}
\phi_{I}(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=\phi_{i_{1}}(\mathbf{x}_{1})\cdots \phi_{i_{k}}(\mathbf{x}_{k})
\end{gather}
$$

设 $\mathbf{x}_{j}=(x_{1j},\dots,x_{nj})$，则

$$
\begin{gather}
\phi_{I}(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=x_{i_{1} 1}\cdots x_{i_{k}k}
\end{gather}
$$

换句话说，$\phi_{I}$ 就是一个单项式，而一个一般的 $k$-张量就是这类单项式的线性组合。

例如，$\mathbb{R}^{n}$ 上的 $1$-张量具有形式

$$
\begin{gather}
f(\mathbf{x})=d_{1}x_{1}+\dots+d_{n}x_{n}
\end{gather}
$$

而 $2$-张量具有形式

$$
\begin{gather}
g(\mathbf{x},\mathbf{y})=\sum_{1\leq i,j\leq n} d_{ij} x_{i}y_{j}
\end{gather}
$$

## The Tensor Product

### Definition 26.6 tensor product 张量积

设 $f$ 是 $V$ 上的 $k$-张量，$g$ 是 $V$ 上的 $\ell$-张量，我们定义 $V$ 上的 $(k+\ell)$-张量 $f\otimes g$ 为

$$
\begin{gather}
(f\otimes g)(\mathbf{v}_{1},\dots,\mathbf{v}_{k+\ell})=f(\mathbf{v}_{1},\dots,\mathbf{v}_{k})g(\mathbf{v}_{k+1},\dots,\mathbf{v}_{k+\ell})
\end{gather}
$$

容易验证 $f\otimes g$ 是多线性的，它称为 $f$ 与 $g$ 的张量积。

### Theorem 26.7

设 $f,g,h$ 是 $V$ 上的张量，其满足以下性质：

(1) 结合律：$f\otimes(g\otimes h)=(f\otimes g)\otimes h$，
(2) 齐次性：$(cf)\otimes g=c(f\otimes g)=f\otimes(cg)$，
(3) 设 $f,g$ 同阶，则
$$
\begin{gather}
(f+g)\otimes h=f\otimes h+g\otimes h \\
h\otimes (f+g)=h\otimes f+h\otimes g
\end{gather}
$$
(4) 给定 $V$ 的基 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$，对应的基本张量 $\phi_{I}$ 满足
$$
\begin{gather}
\phi_{I}=\phi_{i_{1}}\otimes \dots \otimes  \phi_{i_{k}}
\end{gather}
$$
其中 $I=(i_{1},\dots,i_{k})$。

## The Action of a Linear Transformation

### Definition 26.8 dual transformation 对偶变换

设 $T\colon V\to W$ 是线性变换，我们定义它的对偶变换

$$
\begin{gather}
T^{*}\colon \mathcal{L}^{k}(W)\to \mathcal{L}^{k}(V)
\end{gather}
$$

如下：如果 $f \in \mathcal{L}^{k}(W)$，且 $\mathbf{v}_{1},\dots,\mathbf{v}_{k}\in V$，则

$$
\begin{gather}
(T^{*}f)(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=f(T(\mathbf{v}_{1}),\dots,T(\mathbf{v}_{k}))
\end{gather}
$$

变换 $T^{*}$ 等于变换 $T\times\dots \times T$ 与张量 $f$ 的复合，如下交换图所示：

<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsMyxbMCwwLCJWXntrfSJdLFsyLDEsIlxcbWF0aGJie1J9Il0sWzIsMCwiV157a30iXSxbMCwyLCJUXFx0aW1lcyBcXGRvdHMgXFx0aW1lcyBUIl0sWzIsMSwiZiJdLFswLDEsIlReeyp9IGYiLDJdXQ==&embed&theme=dark" width="600" height="250" style="border-radius: 8px; border: none;"></iframe>

从这个角度来看，$T^{*}$ 称为一个“拉回”，因为它将 $W$ 上的张量拉回到 $V$ 上。容易验证 $T^{*}f$ 是多线性的，以及 $T^{*}$ 自身也是线性变换。

### Theorem 26.9

设 $T\colon V\to W$ 是线性变换，令

$$
\begin{gather}
T^{*}\colon \mathcal{L}^{k}(W)\to \mathcal{L}^{k}(V)
\end{gather}
$$

为其对偶变换，则

1. $T^{*}$ 是线性的，
2. $T^{*}(f\otimes g)=T^{*}f\otimes T^{*}g$，
3. 如果 $S\colon W\to X$ 是线性变换，则 $(S\circ T)^{*}f=T^{*}(S^{*}f)$。

性质 (3) 的交换图如下：

<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsNixbMCwxLCJWIl0sWzEsMCwiVyJdLFsyLDEsIlgiXSxbMywxLCJcXG1hdGhjYWx7TH1ee2t9KFYpIl0sWzQsMCwiXFxtYXRoY2Fse0x9XntrfShXKSJdLFs1LDEsIlxcbWF0aGNhbHtMfV57a30oWCkiXSxbMCwxLCJUIl0sWzEsMiwiUyJdLFswLDIsIlNcXGNpcmMgVCIsMl0sWzUsNCwiU14qIiwyXSxbNCwzLCJUXioiLDJdLFs1LDMsIihTXFxjaXJjIFQpXioiXV0=&embed&theme=dark" width="600" height="250" style="border-radius: 8px; border: none;"></iframe>

# 27 Alternating Tensors

本节我们将引入一类特殊的张量——交错张量，然后推导它们的一些性质。为此，我们首先需要一些关于置换的基本事实。

## Permutations

### Definition 27.1 permutation 置换

设 $k\geq 2$。$\{ 1,\dots,k \}$ 上的一个置换 $\sigma$ 是从该集合到其自身的一个双射。我们将 $\{ 1,\dots,k \}$ 上所有置换构成的集合记作 $S_{k}$。如果 $\sigma$ 和 $\tau$ 是 $S_{k}$ 中的置换，则 $\sigma \circ \tau$ 和 $\sigma^{-1}$ 也是置换，因此 $S_{k}$ 连带着其上的复合运算构成了一个群，称为 $\{ 1,\dots,k \}$ 上的对称群。这个群有 $k!$ 个元素。

### Definition 27.2 elementary permutation 基本置换

给定 $1\leq i<k$，定义 $e_{i}\in S_{k}$ 为 $e_{i}(j)=j$ 如果 $j\neq i$ 且 $j\neq i+1$，而

$$
\begin{gather}
e_{i}(i)=i+1, \quad e_{i}(i+1)=i
\end{gather}
$$

我们称 $e_{i}$ 为一个基本置换。显然 $e_{i}\circ e_{i}$ 为恒等映射，故 $e_{i}^{-1}=e_{i}$。

### Lemma 27.3

设 $\sigma \in S_{k}$，则 $\sigma$ 等于一系列基本置换的复合。

#### Proof

给定 $0\leq i\leq k$，我们说 $\sigma$ 固定前 $i$ 个数，如果对 $1\leq j\leq i$ 有 $\sigma(j)=j$。如果 $i=0$，那么 $\sigma$ 可能不固定任何数。如果 $i=k$，那么 $\sigma$ 固定了所有数，即 $\sigma$ 等于恒等映射。此时它满足定理的结论，因为 $e_{j}\circ e_{j}$ 等于恒等映射。

我们来证明如果 $\sigma$ 固定前 $i-1$ 个数，那么 $\sigma$ 可以写成 $\sigma=\pi \circ\sigma'$，其中 $\pi$ 是一系列基本置换的复合，而 $\sigma'$ 固定前 $i$ 个数。由此，通过归纳法我们就完成了证明。

假设 $\sigma$ 固定 $1,\dots,i-1$，由于 $\sigma$ 是双射，因此 $\sigma(i)$ 不等于 $1,\dots,i-1$。如果 $\sigma(i)=i$，那么我们取 $\pi$ 为恒等映射，$\sigma'=\sigma$ 即可。如果 $\sigma(i)=\ell>i$，我们令

$$
\begin{gather}
\sigma'=e_{i}\circ\dots \circ e_{\ell-1}\circ\sigma
\end{gather}
$$

则 $\sigma'$ 固定 $1,\dots,i-1$，因为 $\sigma$ 固定前 $i-1$ 个数并且 $e_{i},\dots,e_{\ell-1}$ 保持这些数不变。此外，$\sigma'(i)=i$，从而 $\sigma'$ 固定前 $i$ 个数。令

$$
\begin{gather}
\pi=e_{\ell-1}\circ\dots \circ e_{i}
\end{gather}
$$

即证 $\sigma=\pi \circ\sigma'$。

### Definition 27.4 inversion 逆序

设 $\sigma \in S_{k}$。$\{ 1,\dots,k \}$ 中满足 $i<j$ 且 $\sigma(i)>\sigma(j)$ 的有序对 $(i,j)$ 称为 $\sigma$ 的一个逆序。我们定义 $\sigma$ 的符号 $\operatorname{sgn}\sigma=-1$ 如果 $\sigma$ 的逆序数为奇数，此时我们称 $\sigma$ 是奇置换；$\operatorname{sgn}\sigma=1$ 如果 $\sigma$ 的逆序数为偶数，此时我们称 $\sigma$ 是偶置换。

### Lemma 27.5

设 $\sigma,\tau \in S_{k}$。

(a) 如果 $\sigma$ 等于 $m$ 个基本置换的复合，那么 $\operatorname{sgn}\sigma=(-1)^{m}$。
(b) $\operatorname{sgn}(\sigma \circ \tau)=(\operatorname{sgn}\sigma)(\operatorname{sgn}\tau)$。
(c) $\operatorname{sgn}\sigma^{-1}=(\operatorname{sgn}\sigma)^{-1}$。
(d) 如果 $p\neq q$，$\tau$ 是只交换 $p$ 和 $q$ 的置换，则 $\operatorname{sgn}\tau=-1$。

#### Proof

**第一步** 我们证明，对任意 $\sigma$，有

$$
\begin{gather}
\operatorname{sgn}(\sigma \circ e_{\ell})=-\operatorname{sgn}\sigma
\end{gather}
$$

给定 $\sigma$，我们将它的值写成一个序列

$$
\begin{gather}
(\sigma(1),\dots,\sigma(\ell),\sigma(\ell+1),\dots,\sigma(k)) \tag{$\ast$}
\end{gather}
$$

令 $\tau=\sigma \circ e_{\ell}$，则对应于 $\tau$ 的序列为

$$
\begin{gather}
(\sigma(1),\dots,\sigma(\ell+1),\sigma(\ell),\dots,\sigma(k)) \tag{$\ast\ast$}
\end{gather}
$$

我们来比较两个序列中的逆序数。令 $p\neq q$，如果 $p,q$ 都不等于 $\ell$ 或 $\ell+1$，那么 $\sigma(p)$ 和 $\sigma(q)$ 在两个序列中位于相同的位置，因此 $(p,q)$ 是 $(\ast)$ 的逆序当且仅当它是 $(\ast\ast)$ 的逆序。

如果 $p$ 等于 $\ell$ 或 $\ell+1$，而 $q$ 不等于 $\ell,\ell+1$，则 $\sigma(q)$ 在两个序列中位于相同的位置，而 $\sigma(p)$ 在两个序列中位于相邻的位置。然而，我们仍然有性质：$(p,q)$ 是 $(\ast)$ 的逆序当且仅当它是 $(\ast\ast)$ 的逆序。

最后，如果 $p,q$ 等于 $\ell$ 和 $\ell+1$，那么如果 $(p,q)$ 在 $(\ast)$ 中是逆序，那么它在 $(\ast\ast)$ 中不是逆序，反之亦然。

综上，$(\ast)$ 的逆序数与 $(\ast\ast)$ 的逆序数仅相差 $1$。

**第二步** 我们证明该定理。

恒等映射的符号为 $+1$，将其与 $m$ 个基本置换复合将它的符号改变了 $m$ 次，这就证明了 (a)。要证 (b)，我们将 $\sigma$ 和 $\tau$ 分别写成 $m$ 和 $n$ 个基本置换的复合，由 $(-1)^{m+n}=(-1)^{m}(-1)^{n}$ 即证。对于 (c)，由于 $\sigma^{-1}\circ\sigma$ 等于恒等映射，应用 (b) 即证。

最后，要证 (d)，我们只需计算逆序数。设 $p<q$，我们将 $\tau$ 的值写成序列

$$
\begin{gather}
(1,\dots,p-1,q,p+1,\dots,p+\ell-1,p,p+\ell+1,\dots,k)
\end{gather}
$$

其中 $q=p+\ell$。每一对 $(q,p+i)$ 和 $(p+i,p),i=1,\dots,\ell-1$ 都是逆序，另外 $(q,p)$ 也是一个逆序，因此 $\tau$ 的逆序数为 $2\ell-1$，因而 $\operatorname{sgn}\tau=-1$。

## Alternating Tensors

### Definition 27.6 symmetric tensor 对称张量，alternating tensor 交错张量

设 $f$ 是 $V$ 上的 $k$-张量，$\sigma \in S_{k}$，我们定义 $f^{\sigma}$ 为

$$
\begin{gather}
f^{\sigma}(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=f(\mathbf{v}_{\sigma(1)},\dots,\mathbf{v}_{\sigma(k)})
\end{gather}
$$

显然 $f^{\sigma}$ 是多线性的。称 $f$ 是对称的，如果对任意基本置换 $e$ 有 $f^{e}=f$；称 $f$ 是交错的，如果对任意基本置换 $e$ 有 $f^{e}=-f$。

在本书中，我们将主要研究交错张量。

### Definition 27.7

设 $V$ 是向量空间，我们定义 $V$ 上所有交错 $k$-张量构成的集合为 $\mathcal{A}^{k}(V)$。容易证明 $\mathcal{A}^{k}(V)$ 是 $\mathcal{L}^{k}(V)$ 的线性子空间，并且 $\mathcal{A}^{1}(V)=\mathcal{L}^{1}(V)$，因为 $1$-张量自动是交错的。

### Example 27.8

设 $k>1$。取 $V=\mathbb{R}^{n}$ 并取其上的标准基以及对应的对偶基 $\phi_{i}$，我们可以验证函数

$$
\begin{gather}
f(\mathbf{x},\mathbf{y})=x_{i}y_{j}-x_{j}y_{i}=\det \begin{bmatrix}
x_{i} & y_{i} \\
x_{j} & y_{j}
\end{bmatrix}
\end{gather}
$$

是一个交错 $2$-张量。类似地，函数

$$
\begin{gather}
g(\mathbf{x},\mathbf{y},\mathbf{z})=\det \begin{bmatrix}
x_{i} & y_{i} & z_{i} \\
x_{j} & y_{j} & z_{j} \\
x_{k} & y_{k} & z_{k}
\end{bmatrix}
\end{gather}
$$

是 $\mathbb{R}^{n}$ 上的交错 $3$-张量。我们也可以将 $g$ 写成

$$
\begin{gather}
g=\phi_{i,j,k}+\phi_{j,k,i}+\phi_{k,i,j}-\phi_{j,i,k}-\phi_{i,k,j}-\phi_{k,j,i}
\end{gather}
$$

上面的例子表明，行列式与交错张量有深刻的联系。下面我们就来研究这一点。

### Lemma 27.9

设 $f$ 是 $V$ 上的 $k$-张量，$\sigma,\tau \in S_{k}$。

(a) 映射 $f\mapsto f^{\sigma}$ 是 $\mathcal{L}^{k}(V)$ 上的线性变换，并且有
$$
\begin{gather}
(f^{\sigma})^{\tau}=f^{\tau \circ\sigma}
\end{gather}
$$
(b) $f$ 是交错的当且仅当 $f^{\sigma}=(\operatorname{sgn}\sigma)f$。如果 $f$ 是交错的并且有 $p\neq q$ 满足 $\mathbf{v}_{p}=\mathbf{v}_{q}$，则 $f(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=0$。

#### Proof

(a) 线性性是容易验证的。取 $\sigma,\tau \in S_{k}$，则

$$
\begin{align}
(f^{\sigma})^{\tau}(\mathbf{v}_{1},\dots,\mathbf{v}_{k}) &= f^{\sigma}(\mathbf{v}_{\tau(1)},\dots,\mathbf{v}_{\tau(k)}) \\
&=f^{\sigma}(\mathbf{w}_{1},\dots,\mathbf{w}_{k}) \quad (\mathbf{w}_{i}=\mathbf{v}_{\tau(i)}) \\
&=f(\mathbf{w}_{\sigma(1)},\dots,\mathbf{w}_{\sigma(k)}) \\
&=f(\mathbf{v}_{\tau(\sigma(1))},\dots,\mathbf{v}_{\tau(\sigma(k))}) \\
&=f^{\tau \circ\sigma}(\mathbf{v}_{1},\dots,\mathbf{v}_{k})
\end{align}
$$

(b) 给定 $\sigma \in S_{k}$，我们将其写成基本置换的复合

$$
\begin{gather}
\sigma=\sigma_{1}\circ\dots \circ\sigma_{m}
\end{gather}
$$

则

$$
\begin{align}
f^{\sigma} &= f^{\sigma_{1}\circ\dots \circ\sigma_{m}} \\
&= (\cdots(f^{\sigma_{m}})\cdots)^{\sigma_{1}} \\
&= (-1)^{m} f \\
&= (\operatorname{sgn}\sigma)f
\end{align}
$$

现在设有 $p\neq q$ 使得 $\mathbf{v}_{p}=\mathbf{v}_{q}$，令 $\tau$ 为仅交换 $p$ 和 $q$ 的置换，则

$$
\begin{gather}
f(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=f^{\tau}(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=-f(\mathbf{v}_{1},\dots,\mathbf{v}_{k})
\end{gather}
$$

从而 $f(\mathbf{v}_{1},\dots,\mathbf{v}_{k})=0$。

现在我们来求解 $\mathcal{A}^{k}(V)$ 的一个基。当 $k=1$ 时，没有什么可以研究的，因为 $\mathcal{A}^{1}(V)=\mathcal{L}^{1}(V)$。此外，当 $k>n$ 时，$\mathcal{A}^{k}(V)$ 是平凡的，因为每个 $k$-张量 $f$ 都由其在基向量 $k$-元组上的取值决定，而此时的 $k$-元组中必然存在两个相同的基向量，从而 $f=0$。

最后，我们考虑 $1<k\leq n$ 的情况。我们证明交错张量 $f$ 完全由其在基向量的升序 $k$-元组上的取值决定，然后我们证明这些取值可以任意指定。

### Lemma 27.10

设 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 是 $V$ 的基。如果 $f,g$ 是 $V$ 上的交错 $k$-张量，且对任意 $\{ 1,\dots,n \}$ 上的升序 $k$-元组 $I=(i_{1},\dots,i_{k})$ 有

$$
\begin{gather}
f(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})=g(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})
\end{gather}
$$

那么 $f=g$。

#### Proof

根据 [[#Lemma 26.3]]，我们只需证明 $f,g$ 在任意 $k$-元组 $(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})$ 上的取值相同。令 $J=(j_{1},\dots,j_{k})$。

如果存在 $p\neq q$ 使得 $j_{p}=j_{q}$，则 [[#Lemma 27.9]] 表明 $f$ 和 $g$ 在该元组上的值均为零。如果 $J$ 中的各指标不同，令 $\sigma \in S_{k}$ 使得 $(j_{\sigma(1)},\dots,j_{\sigma(k)})$ 为升序，则

$$
\begin{align}
f(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}}) &= f^{\sigma}(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}}) \\
&= (\operatorname{sgn}\sigma) f(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})
\end{align}
$$

在上式中用 $g$ 替换 $f$，等式仍然成立。由于 $f,g$ 在升序 $k$-元组上的值相同，因此 $f=g$。

### Theorem 27.11

设 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 是 $V$ 的基，$I=(i_{1},\dots,i_{k})$ 是 $\{ 1,\dots,n \}$ 上的升序 $k$-元组。则存在唯一的交错 $k$-张量 $\psi_{I}$ 使得对任意升序 $k$-元组 $J=(j_{1},\dots,j_{k})$ 有

$$
\begin{gather}
\psi_{I}(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})=\begin{cases}
0, & I\neq J \\
1, & I=J
\end{cases}
\end{gather}
$$

张量 $\psi_{I}$ 构成了 $\mathcal{A}^{k}(V)$ 的一个基。此外，我们有

$$
\begin{gather}
\psi_{I}=\sum_{\sigma \in S_{k}} (\operatorname{sgn}\sigma)(\phi_{I})^{\sigma}
\end{gather}
$$

我们称 $\psi_{I}$ 为 $V$ 上对应于基 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$ 的基本交错 $k$-张量。

#### Proof

唯一性由 [[#Lemma 27.10]] 给出。要证存在性，我们用定理中的公式定义 $\psi_{I}$，然后证明它满足给出的条件。

首先，我们证明 $\psi_{I}$ 是交错的。设 $\tau \in S_{k}$，则

$$
\begin{align}
(\psi_{I})^{\tau} &= \sum_{\sigma} (\operatorname{sgn}\sigma)((\phi_{I})^{\sigma})^{\tau} \\
&=\sum_{\sigma} (\operatorname{sgn}\sigma)(\phi_{I})^{\tau \circ\sigma} \\
&=(\operatorname{sgn}\tau) \sum_{\sigma} (\operatorname{sgn}\tau \circ\sigma) (\phi_{I})^{\tau \circ\sigma} \\
&=(\operatorname{sgn}\tau) \psi_{I}
\end{align}
$$

最后一个等式成立，因为当 $\sigma$ 遍历 $S_{k}$ 时，$\tau \circ\sigma$ 也遍历 $S_{k}$。

我们证明 $\psi_{I}$ 的值符合期望。给定升序元组 $J$，有

$$
\begin{gather}
\psi_{I}(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})=\sum_{\sigma} (\operatorname{sgn}\sigma)\phi_{I}(\mathbf{a}_{j_{\sigma(1)}},\dots,\mathbf{a}_{j_{\sigma(k)}})
\end{gather}
$$

右侧的求和中仅有一项不为零，即，使得 $I=(j_{\sigma(1)},\dots,j_{\sigma(k)})$ 的 $\sigma \in S_{k}$ 所对应的那一项。由于 $I$ 和 $J$ 都是升序的，这只可能发生在 $\sigma$ 为恒等映射，$I=J$ 的时候，此时 $\psi_{I}$ 的值为 $1$，而其余情况下 $\psi_{I}=0$。

最后我们证明 $\psi_{I}$ 是 $\mathcal{A}^{k}(V)$ 的基。给定交错 $k$-张量 $f$，对每个升序 $k$-元组 $I=(i_{1},\dots,i_{k})$，定义

$$
\begin{gather}
d_{I}=f(\mathbf{a}_{i_{1}},\dots,\mathbf{a}_{i_{k}})
\end{gather}
$$

考虑交错 $k$-张量

$$
\begin{gather}
g=\sum_{[J]} d_{J} \psi_{J}
\end{gather}
$$

其中 $[J]$ 表示求和遍历所有升序 $k$-元组 $J$。由 [[#Lemma 27.10]] 知 $f=g$。此外，通过在 $k$-元组 $(\mathbf{a}_{j_{1}},\dots,\mathbf{a}_{j_{k}})$ 上取值，我们可以证明各 $\psi_{I}$ 线性无关，这就完成了证明。

这一定理表明，只要 $V$ 上选取了一个基 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$，那么任意一个交错 $k$-张量 $f$ 都可以唯一的写成

$$
\begin{gather}
f=\sum_{[J]} d_{J}\psi_{J}
\end{gather}
$$

我们称 $d_{J}$ 为 $f$ 相对于基 $\{ \psi_{J} \}$ 的分量。

向量空间 $\mathcal{A}^{k}(V)$ 的维数是多少？这取决于 $\{ 1,\dots,n \}$ 上有多少升序 $k$-元组。容易看出这个数等于 $\{ 1,\dots,n \}$ 的 $k$-子集的数量，后者由二项式系数

$$
\begin{gather}
\binom{n}{k}=\frac{n!}{k!(n-k)!}
\end{gather}
$$

给出。

最后，我们容易证明交错张量在拉回下仍然是交错的。

### Theorem 27.12

设 $T\colon V\to W$ 是线性变换，如果 $f$ 是 $W$ 上的交错张量，那么 $T^{*}f$ 是 $V$ 上的交错张量。

## Determinants

现在我们就来构造一般方阵的行列式函数。

### Definition 27.13 determinant 行列式

设 $\mathbf{e}_{1},\dots,\mathbf{e}_{n}$ 是 $\mathbb{R}^{n}$ 的标准基，$\phi_{1},\dots,\phi_{n}$ 是 $\mathcal{L}^{1}(\mathbb{R}^{n})$ 中对应于标准基的对偶基。向量空间 $\mathcal{A}^{n}(\mathbb{R}^{n})$ 的维数是 $1$，其唯一的交错 $n$-张量为 $\psi_{1,\dots,n}$。如果 $X=[\mathbf{x}_{1}\cdots \mathbf{x}_{n}]$ 是 $n\times n$ 矩阵，我们定义 $X$ 的行列式为

$$
\begin{gather}
\det X=\psi_{1,\dots,n}(\mathbf{x}_{1},\dots,\mathbf{x}_{n})
\end{gather}
$$

我们来证明上面的函数满足行列式函数的三条公理。记

$$
\begin{gather}
g(X)=\psi_{I}(\mathbf{x}_{1},\dots,\mathbf{x}_{n})
\end{gather}
$$

其中 $I=(1,\dots,n)$。函数 $g$ 关于 $X$ 的列是多线性且交错的，因为 $\psi_{I}$ 是多线性且交错的。因此 $f(A)=g(A^{T})$ 关于 $A$ 的行是多线性且交错的。此外，

$$
\begin{gather}
f(I_{n})=g(I_{n})=\psi_{I}(\mathbf{e}_{1},\dots,\mathbf{e}_{n})=1
\end{gather}
$$

因此 $f$ 满足行列式的三条公理。根据 [[1 The Algebra and Topology of Rn#Theorem 2.15]]，我们可知 $f(A)=f(A^{T})$，于是 $f(A)=f(A^{T})=g((A^{T})^{T})=g(A)$，从而 $g$ 也是行列式函数。

[[#Theorem 27.11]] 中 $\psi_{I}$ 的公式给出了行列式函数的一个公式。设 $I=(1,\dots,n)$，我们有

$$
\begin{align}
\det X &= \sum_{\sigma} (\operatorname{sgn}\sigma)\phi_{I}(\mathbf{x}_{\sigma(1)},\dots,\mathbf{x}_{\sigma(n)}) \\
&=\sum_{\sigma} (\operatorname{sgn}\sigma)\mathbf{x}_{1,\sigma(1)}\cdots \mathbf{x}_{n,\sigma(n)}
\end{align}
$$

以上公式通常被作为行列式函数的定义使用。

### Theorem 27.14

设 $\psi_{I}$ 是 $\mathbb{R}^{n}$ 上对应于标准基的基本交错张量，其中 $I=(i_{1},\dots,i_{k})$。给定 $\mathbf{x}_{1},\dots,\mathbf{x}_{k}\in \mathbb{R}^{n}$，令 $X=[\mathbf{x}_{1}\cdots \mathbf{x}_{k}]$，则

$$
\begin{gather}
\psi_{I}(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=\det X_{I}
\end{gather}
$$

其中 $X_{I}$ 表示由 $X$ 的 $i_{1},\dots,i_{k}$ 行构成的子矩阵。

#### Proof

我们有

$$
\begin{align}
\psi_{I}(\mathbf{x}_{1},\dots,\mathbf{x}_{k}) &= \sum_{\sigma} (\operatorname{sgn}\sigma) \phi_{I}(\mathbf{x}_{\sigma(1)},\dots,\mathbf{x}_{\sigma(k)}) \\
&=\sum_{\sigma} (\operatorname{sgn}\sigma) \mathbf{x}_{i_{1},\sigma(1)}\cdots \mathbf{x}_{i_{k},\sigma(k)}
\end{align}
$$

后者正是 $\det X_{I}$ 的公式。

# 28 The Wedge Product

本节我们来定义交错张量上的一个运算。这一运算的实际定义是无关紧要的，真正重要的是它满足的性质，如以下定理所示。

### Theorem 28.1

设 $V$ 是向量空间，存在一个运算，其将 $f \in \mathcal{A}^{k}(V)$ 和 $g \in \mathcal{A}^{\ell}(V)$ 关联到 $f\land g \in \mathcal{A}^{k+\ell}(V)$，使得它满足以下性质：

(1) 结合律：$f\land(g\land h)=(f\land g)\land h$。
(2) 齐次性：$(cf)\land g=c(f\land g)=f\land(cg)$。
(3) 分配律：如果 $f,g$ 是同阶张量，那么
$$
\begin{gather}
(f+g)\land h=f\land h+g\land h \\
h\land (f+g)=h\land f+h\land g
\end{gather}
$$
(4) 反对称性：设 $f,g$ 的阶数分别为 $k$ 和 $\ell$，则
$$
\begin{gather}
g\land f=(-1)^{k\ell} f\land g
\end{gather}
$$
(5) 给定 $V$ 的基 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$，令 $\phi_{i}$ 表示 $V^{*}$ 上的对偶基，$\psi_{I}$ 为对应的基本交错张量。如果 $I=(i_{1},\dots,i_{k})$ 是 $\{ 1,\dots,n \}$ 上的升序 $k$-元组，则
$$
\begin{gather}
\psi_{I}=\phi_{i_{1}}\land\dots \land \phi_{i_{k}}
\end{gather}
$$

以上五个性质在有限维空间 $V$ 上唯一地确定了运算 $\land$。此外，其还满足性质

(6) 设 $T\colon V\to W$ 是线性变换，$f,g$ 是 $W$ 上的交错张量，则
$$
\begin{gather}
T^{*}(f\land g)=T^{*}f\land T^{*}g
\end{gather}
$$

张量 $f\land g$ 称为 $f$ 和 $g$ 的楔积。注意到，性质 (4) 表明如果 $f$ 是奇数阶交错张量，那么 $f\land f=0$。

#### Proof

**第一步**

令 $F$ 为 $V$ 上任意一个 $k$-张量，我们定义映射 $A\colon \mathcal{L}^{k}(V)\to \mathcal{L}^{k}(V)$ 为

$$
\begin{gather}
AF=\sum_{\sigma} (\operatorname{sgn}\sigma) F^{\sigma}
\end{gather}
$$

于是基本交错张量 $\psi_{I}$ 就可以写成

$$
\begin{gather}
\psi_{I}=A\phi_{I}
\end{gather}
$$

我们证明 $A$ 满足以下性质：

1. $A$ 是线性的；
2. $AF$ 是交错张量；
3. 如果 $F$ 是交错的，那么 $AF=(k!)F$。

由于 $F\mapsto F^{\sigma}$ 是线性的，故 $A$ 是线性的。设 $\tau \in S_{k}$，我们有

$$
\begin{align}
(AF)^{\tau} &= \sum_{\sigma} (\operatorname{sgn}\sigma)(F^{\sigma})^{\tau} \\
&=\sum_{\sigma} (\operatorname{sgn}\sigma) F^{\tau \circ\sigma} \\
&=(\operatorname{sgn}\tau)\sum_{\sigma} (\operatorname{sgn}\tau \circ\sigma)F^{\tau \circ\sigma} \\
&=(\operatorname{sgn}\tau)AF
\end{align}
$$

因此 $AF$ 是交错的。最后，如果 $F$ 是交错的，那么 $F^{\sigma}=(\operatorname{sgn}\sigma)F$，从而

$$
\begin{gather}
AF=\sum_{\sigma} (\operatorname{sgn}\sigma)^{2}F=(k!)F
\end{gather}
$$

**第二步**

我们定义交错 $k$-张量 $f$ 与交错 $\ell$-张量 $g$ 的楔积为

$$
\begin{gather}
f\land g=\frac{1}{k!\ell!}A(f\otimes g)
\end{gather}
$$

则 $f\land g$ 是一个 $k+\ell$ 阶交错张量。

**第三步**

结合律是这些性质中最难验证的，因此我们将它放到最后。要验证齐次性，我们计算

$$
\begin{align}
(cf)\land g &= \frac{1}{k!\ell!} A((cf)\otimes g) \\
&=\frac{1}{k!\ell!} A(c(f\otimes g)) \\
&=\frac{c}{k!\ell!} A(f\otimes g) \\
&=c(f\land g)
\end{align}
$$

对 $f\land(cg)$ 也有类似的计算，即证齐次性。同理，利用 $\otimes$ 的分配性和 $A$ 的线性性，我们可以类似地验证 $\land$ 的分配性。

**第四步**

我们验证反对称性。这里我们证明一个更普遍的结论：设 $F,G$ 分别是 $k$ 阶和 $\ell$ 阶张量，则

$$
\begin{gather}
A(F\otimes G)=(-1)^{k\ell}A(G\otimes F)
\end{gather}
$$

为此令 $\pi$ 为置换

$$
\begin{gather}
(\pi(1),\dots,\pi(k+\ell))=(k+1,\dots,k+\ell,1,\dots,k)
\end{gather}
$$

则 $(G\otimes F)^{\pi}=F\otimes G$。此外，通过计算逆序数，我们有 $\operatorname{sgn}\pi=(-1)^{k\ell}$。于是

$$
\begin{align}
A(F\otimes G) &= \sum_{\sigma} (\operatorname{sgn}\sigma)(F\otimes G)^{\sigma} \\
&=\sum_{\sigma} (\operatorname{sgn}\sigma) ((G\otimes F)^{\pi})^{\sigma} \\
&=(\operatorname{sgn}\pi)\sum_{\sigma} (\operatorname{sgn}\sigma \circ \pi)(G\otimes F)^{\sigma \circ \pi} \\
&=(\operatorname{sgn}\pi)A(G\otimes F)
\end{align}
$$

**第五步**

在以下的几步中我们来验证结合性。首先我们证明如果 $F,G$ 分别是 $k$ 阶和 $\ell$ 阶张量，使得 $AF=0$，则 $A(F\otimes G)=0$。

为此，我们考虑 $A(F\otimes G)$ 中的一项

$$
\begin{gather} \\
(\operatorname{sgn}\sigma) F(\mathbf{v}_{\sigma(1)},\dots,\mathbf{v}_{\sigma(k)})G(\mathbf{v}_{\sigma(k+1)},\dots,\mathbf{v}_{\sigma(k+\ell)})
\end{gather}
$$

我们将含有因子 $G(\mathbf{v}_{\sigma(k+1)},\dots,\mathbf{v}_{\sigma(k+\ell)})$ 的项放在一起，这些项可以写成

$$
\begin{gather}
(\operatorname{sgn}\sigma)\left( \sum_{\tau} (\operatorname{sgn}\tau)F(\mathbf{v}_{\sigma(\tau(1))},\dots,\mathbf{v}_{\sigma(\tau(k))}) \right) G(\mathbf{v}_{\sigma(k+1)},\dots,\mathbf{v}_{\sigma(k+\ell)})
\end{gather}
$$

括号内的求和等于 $AF(\mathbf{v}_{\sigma(1)},\dots,\mathbf{v}_{\sigma(k)})=0$，因此上面这一组项之和消失。对每个这样的组应用以上论证，我们即得 $A(F\otimes G)=0$。

**第六步**

设 $F$ 是任意张量，$h$ 是交错 $m$-张量，我们证明

$$
\begin{gather}
(AF)\land h=\frac{1}{m!} A(F\otimes h)
\end{gather}
$$

设 $F$ 的阶为 $k$。上面的等式可以写成

$$
\begin{gather}
\frac{1}{k!m!}A((AF)\otimes h)=\frac{1}{m!}A(F\otimes h)
\end{gather}
$$

利用 $A$ 的线性性与 $\otimes$ 的分配性，上式等价于

$$
\begin{gather}
A((AF-k!F)\otimes h)=0
\end{gather}
$$

根据第五步，上式成立的一个充分条件是

$$
\begin{gather}
A(AF-k!F)=0
\end{gather}
$$

然而根据 $A$ 的性质 (3)，$A(AF)=k!AF$，即证。

**第七步**

我们证明，如果 $f,g,h$ 分别是 $k,\ell,m$ 阶交错张量，那么

$$
\begin{gather}
(f\land g)\land h=\frac{1}{k!\ell!m!} A((f\otimes g)\otimes h)
\end{gather}
$$

令 $F=f\otimes g$，则

$$
\begin{gather}
f\land g=\frac{1}{k!\ell!} AF
\end{gather}
$$

于是

$$
\begin{align}
(f\land g)\land h &= \frac{1}{k!\ell!} (AF)\land h \\
&= \frac{1}{k!\ell!m!} A(F\otimes h) \\
&=\frac{1}{k!\ell!m!} A((f\otimes g)\otimes h)
\end{align}
$$

**第八步**

现在我们来验证结合律。令 $f,g,h$ 如第七步所示，则

$$
\begin{align}
(k!\ell!m!)(f\land g)\land h & = A((f\otimes g)\otimes h) \\
&=A(f\otimes (g\otimes h)) \\
&=(-1)^{k(\ell+m)} A((g\otimes h)\otimes f) \\
&=(-1)^{k(\ell+m)} (\ell!m!k!) (g\land h)\land f \\
&=(\ell!m!k!) f\land(g\land h)
\end{align}
$$

其中最后一步我们用了 $\land$ 的反对称性。

**第九步**

我们验证性质 (5)。我们来证明对 $1$-张量 $f_{1},\dots,f_{k}$ 有

$$
\begin{gather}
A(f_{1}\otimes \dots \otimes f_{k})=f_{1}\land\dots \land f_{k} \tag{$\ast$}
\end{gather}
$$

性质 (5) 是它的直接推论，因为

$$
\begin{gather}
\psi_{I}=A\phi_{I}=A(\phi_{i_{1}}\otimes \dots \otimes \phi_{i_{k}})
\end{gather}
$$

我们用归纳法。等式 $(\ast)$ 在 $k=1$ 时是平凡的，假设其对 $k-1$ 成立，则令 $F=f_{1}\land\dots \land f_{k-1}$，我们有

$$
\begin{align}
A(F\otimes f_{k}) &= (1!) F\land f_{k} \\
&=(f_{1}\land\dots \land f_{k-1})\land f_{k}
\end{align}
$$

**第十步**

我们验证唯一性，我们通过给出 $\land$ 的一个仅利用性质 (1)-(5) 的计算方法来证明这一点。

令 $\phi_{i}$ 和 $\psi_{I}$ 如 (5) 中所示。给定交错张量 $f,g$，它可以唯一地表示为

$$
\begin{gather}
f=\sum_{[I]} b_{I}\psi_{I}, \quad g=\sum_{[J]} c_{J}\psi_{J}
\end{gather}
$$

分配性和齐次性给出

$$
\begin{gather}
f\land g=\sum_{[I]}\sum_{[J]} b_{I}c_{J} \psi_{I}\land \psi_{J}
\end{gather}
$$

因此，要计算 $f\land g$，我们只需计算

$$
\begin{gather}
\psi_{I}\land \psi_{J}=(\phi_{i_{1}}\land\dots \land \phi_{i_{k}})\land(\phi_{j_{1}}\land\dots \land \phi_{j_{\ell}})
\end{gather}
$$

为此，我们应用结合律，以及反对称性的推论

$$
\begin{gather}
\phi_{i}\land \phi_{i}=0, \quad \phi_{i}\land \phi_{j}=-\phi_{j}\land \phi_{i}
\end{gather}
$$

于是，$\psi_{I}\land \psi_{J}=0$ 如果有某两个 $\phi$ 的下标相同，否则它就等于 $\operatorname{sgn}\pi$ 乘以 $k+\ell$ 阶基本交错张量 $\psi_{K}$，其中 $K$ 为将 $I\cup J$ 排成升序得到的 $(k+\ell)$-元组，而 $\pi$ 则是完成这一排序所用的置换。

**第十一步**

最后我们验证性质 (6)。设 $T\colon V\to W$ 是线性变换，$F$ 是 $W$ 上的任意张量，容易证明 $T^{*}(F^{\sigma})=(T^{*}F)^{\sigma}$。又由于 $T^{*}$ 是线性的，故 $T^{*}(AF)=A(T^{*}F)$。

现在设 $f,g$ 是 $W$ 上的交错张量，则我们有

$$
\begin{align}
T^{*}(f\land g) &= \frac{1}{k!\ell!} T^{*}(A(f\otimes g)) \\
&=\frac{1}{k!\ell!} A(T^{*}(f\otimes g)) \\
&=\frac{1}{k!\ell!} A(T^{*}f\otimes T^{*}g) \\
&=T^{*}f \land T^{*}g
\end{align}
$$

# 29 Tangent Vectors and Differential Forms

在微积分中，我们学习了 $\mathbb{R}^{3}$ 上的向量代数，其中引入了标量场与向量场——在 $\mathbb{R}^{3}$ 上有定义、输出为标量或向量的函数。此外，我们还定义了标量场和向量场的运算，即

$$
\begin{gather}
\operatorname{grad}f=\nabla F, \quad \operatorname{curl}F=\nabla \times F, \quad \operatorname{div}G=\nabla\cdot G
\end{gather}
$$

分别称为梯度、旋度和散度。这些运算构成了向量积分学的重要部分。

现在我们要将以上运算推广到 $\mathbb{R}^{n}$。我们已经介绍了必要的多线性代数知识，在下面几节中，我们将引入所谓张量场的概念，特别地，我们将引入交错张量场的概念，称为一个“微分形式”。在这之后，我们将定义微分形式上的一个运算，称为“微分算子”，它是梯度、旋度和散度在 $n$ 维空间中的推广。

## Tangent Vectors and Vector Fields

### Definition 29.1 tangent vector 切向量

给定 $\mathbf{x}\in \mathbb{R}^{n}$，我们定义 $\mathbf{x}$ 处关于 $\mathbb{R}^{n}$ 的切向量为有序对 $(\mathbf{x};\mathbf{v})$，其中 $\mathbf{v}\in \mathbb{R}^{n}$。我们定义

$$
\begin{gather}
(\mathbf{x};\mathbf{v})+(\mathbf{x};\mathbf{w})=(\mathbf{x};\mathbf{v}+\mathbf{w}) \\
c(\mathbf{x};\mathbf{v})=(\mathbf{x};c\mathbf{v})
\end{gather}
$$

则 $\mathbf{x}$ 处关于 $\mathbb{R}^{n}$ 的所有切向量构成的集合 $T_{\mathbf{x}}(\mathbb{R}^{n})$ 是一个向量空间，称为 $\mathbf{x}$ 处关于 $\mathbb{R}^{n}$ 的切空间。

在图像上，我们将 $\mathbf{x}$ 和 $\mathbf{v}$ 视为不同的对象，尽管它们都是 $\mathbb{R}^{n}$ 中的元素。我们将 $\mathbf{x}$ 视为度量空间 $\mathbb{R}^{n}$ 中的点，并用一个点来表示它；我们将 $\mathbf{v}$ 视为向量空间 $\mathbb{R}^{n}$ 中的向量，并用一个箭头来表示它。于是，切空间 $T_{\mathbf{x}}(\mathbb{R}^{n})$ 中的元素通常表示为一个起点在 $\mathbf{x}$ 而指向 $\mathbf{v}$ 的箭头。

### Definition 29.2 velocity vector 速度向量

设 $(a,b)\subset \mathbb{R}$，$\gamma\colon(a,b)\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数。我们定义 $\gamma$ 在 $t$ 处的速度向量为 $(\gamma(t);D\gamma(t))$。

直观上看，速度向量就是一个 $\mathbf{p}=\gamma(t)$ 处的切向量。我们称它是速度向量，是受到力学的启发：设

$$
\begin{gather}
\gamma(t)=x(t)\mathbf{e}_{1}+y(t)\mathbf{e}_{2}+z(t)\mathbf{e}_{3}
\end{gather}
$$

是一条参数化曲线（或质点的轨迹），则 $\gamma$ 的速度向量就是

$$
\begin{gather}
D\gamma(t)=x'(t)\mathbf{e}_{1}+y'(t)\mathbf{e}_{2}+z'(t)\mathbf{e}_{3}
\end{gather}
$$

![](6-1.png)

### Definition 29.3

设 $A$ 是 $\mathbb{R}^{k}$ 或 $\mathbb{H}^{k}$ 中的开集，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数。设 $\mathbf{x}\in A$，$\mathbf{p}=\alpha(\mathbf{x})$，我们定义线性变换

$$
\begin{gather}
\alpha_{*}\colon T_{\mathbf{x}}(\mathbb{R}^{k})\to T_{\mathbf{p}}(\mathbb{R}^{n})
\end{gather}
$$

为

$$
\begin{gather}
\alpha_{*}(\mathbf{x};\mathbf{v})=(\mathbf{p};D\alpha(\mathbf{x})\mathbf{v})
\end{gather}
$$

它称为由 $\alpha$ 诱导的变换。

给定 $(\mathbf{x};\mathbf{v})$，链式法则表明 $\alpha_{*}(\mathbf{x};\mathbf{v})$ 事实上是曲线 $\gamma(t)=\alpha(\mathbf{x}+t\mathbf{v})$ 在 $t=0$ 处的速度向量。

![](6-2.png)

### Lemma 29.4

设 $A$ 在 $\mathbb{R}^{k}$ 或 $\mathbb{H}^{k}$ 中开，$\alpha\colon A\to \mathbb{R}^{m}$ 为 $C^{r}$ 函数。设 $B$ 在 $\mathbb{R}^{m}$ 或 $\mathbb{H}^{m}$ 中开，并且包含 $\alpha(A)$。令 $\beta\colon B\to \mathbb{R}^{n}$ 为 $C^{r}$ 函数，则

$$
\begin{gather}
(\beta \circ\alpha)_{*}=\beta_{*}\circ\alpha_{*}
\end{gather}
$$

#### Proof

应用链式法则即可。设 $\mathbf{y}=\alpha(\mathbf{x}),\mathbf{z}=\beta(\mathbf{y})$，则

$$
\begin{align}
(\beta \circ\alpha)_{*}(\mathbf{x};\mathbf{v}) &= (\mathbf{z}; D(\beta \circ\alpha)(\mathbf{x})\mathbf{v}) \\
&=(\beta(\mathbf{y});D\beta(\mathbf{y})D\alpha(\mathbf{x})\mathbf{v}) \\
&=\beta_{*}(\alpha(\mathbf{x});D\alpha(\mathbf{x})\mathbf{v}) \\
&=(\beta_{*}\circ\alpha_{*})(\mathbf{x};\mathbf{v})
\end{align}
$$

即证。

函数 $\alpha,\beta$ 以及它们诱导的变换的交换图如下所示：

<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsNixbMCwwLCJBIl0sWzEsMSwiQiJdLFsyLDAsIlxcbWF0aGJie1J9XntufSJdLFszLDAsIlRfe1xcbWF0aGJme3h9fShcXG1hdGhiYntSfV5rKSJdLFs0LDEsIlRfe1xcbWF0aGJme3l9fShcXG1hdGhiYntSfV5tKSJdLFs1LDAsIlRfe1xcbWF0aGJme3p9fShcXG1hdGhiYntSfV5uKSJdLFswLDEsIlxcYWxwaGEiLDJdLFsxLDIsIlxcYmV0YSIsMl0sWzAsMiwiXFxiZXRhXFxjaXJjXFxhbHBoYSJdLFszLDQsIlxcYWxwaGFfKiIsMl0sWzQsNSwiXFxiZXRhXyoiLDJdLFszLDUsIihcXGJldGFcXGNpcmNcXGFscGhhKV8qIl1d&embed&theme=dark" width="600" height="250" style="border-radius: 8px; border: none;"></iframe>

### Definition 29.5 tangent vector field 切向量场

设开集 $A\subset \mathbb{R}^{n}$，$A$ 上的一个切向量场是一个连续函数 $F\colon A\to \mathbb{R}^{n}\times \mathbb{R}^{n}$ 使得 $F(\mathbf{x})\in T_{\mathbf{x}}(\mathbb{R}^{n})$。则 $F$ 具有形式 $F(\mathbf{x})=(\mathbf{x};f(\mathbf{x}))$，其中 $f\colon A\to \mathbb{R}^{n}$ 是连续函数。如果 $F$ 是 $C^{r}$ 函数，我们就称它是一个 $C^{r}$ 切向量场。

现在我们定义流形上的切向量，我们将在下一章中使用该定义。

### Definition 29.6

设 $M$ 是 $\mathbb{R}^{n}$ 中 $C^{r}$ 连续的 $k$-流形。如果 $\mathbf{p}\in M$，选取坐标卡 $\alpha\colon U\to V$ 使得 $V$ 包含 $\mathbf{p}$。令 $\mathbf{x}\in U$ 满足 $\alpha(\mathbf{x})=\mathbf{p}$。所有具有形式 $\alpha_{*}(\mathbf{x};\mathbf{v})$ 的向量构成的空间称为 $M$ 在 $\mathbf{p}$ 处的切空间，记作 $T_{\mathbf{p}}(M)$。换言之，

$$
\begin{gather}
T_{\mathbf{p}}(M)=\alpha_{*}(T_{\mathbf{x}}(\mathbb{R}^{k}))
\end{gather}
$$

$T_{\mathbf{p}}(M)$ 是 $T_{\mathbf{p}}(\mathbb{R}^{n})$ 的一个线性子空间，它与 $\alpha$ 的选取无关。这是因为 $\mathbb{R}^{k}$ 由标准基 $\mathbf{e}_{1},\dots,\mathbf{e}_{k}$ 张成，而 $T_{\mathbf{p}}(M)$ 由向量

$$
\begin{gather}
(\mathbf{p};D\alpha(\mathbf{x})\mathbf{e}_{j})=(\mathbf{p};\partial\alpha /\partial x_{j})
\end{gather}
$$

张成。由于 $D\alpha$ 的秩为 $k$，因此这些向量是线性无关的，从而它们构成了 $T_{\mathbf{p}}(M)$ 的一个基。典型的切空间如下图所示：

![](6-3.png)

我们记 $T(M)=\bigcup_{\mathbf{p}\in M}T_{\mathbf{p}}(M)$，称为 $M$ 的切丛。$M$ 上的一个切向量场是一个连续函数 $F\colon M\to T(M)$ 使得 $F(\mathbf{p})\in T_{\mathbf{p}}(M)$。

## Tensor Fields

### Definition 29.7 tensor field 张量场，differential form 微分形式

设开集 $A\subset \mathbb{R}^{n}$，$A$ 上的一个 $k$-张量场是一个函数 $\omega$，其将每个 $\mathbf{x}\in A$ 关联到 $T_{\mathbf{x}}(\mathbb{R}^{n})$ 上的一个 $k$-张量 $\omega(\mathbf{x})$。这就是说，

$$
\begin{gather}
\omega(\mathbf{x}) \in \mathcal{L}^{k}(T_{\mathbf{x}}(\mathbb{R}^{n}))
\end{gather}
$$

因此 $\omega(\mathbf{x})$ 将 $\mathbf{x}$ 处关于 $\mathbb{R}^{n}$ 的切向量 $k$-元组映射到一个实数

$$
\begin{gather}
\omega(\mathbf{x})((\mathbf{x};\mathbf{v}_{1}),\dots,(\mathbf{x};\mathbf{v}_{k}))
\end{gather}
$$

我们要求 $\omega$ 作为 $(\mathbf{x},\mathbf{v}_{1},\dots,\mathbf{v}_{k})$ 的函数是连续的。如果它是 $C^{r}$ 函数，我们说 $\omega$ 是一个 $C^{r}$ 张量场。如果对每个 $\mathbf{x}$，$\omega(\mathbf{x})$ 是交错 $k$-张量，则我们称 $\omega$ 是 $A$ 上的一个 $k$ 阶微分形式，或 $k$-形式。

更一般地，如果 $M$ 是 $\mathbb{R}^{n}$ 上的 $m$-流形，则我们定义 $M$ 上的一个 $k$-张量场为一个函数 $\omega$ 使得对 $\mathbf{p}\in M$ 有 $\omega(\mathbf{p})\in \mathcal{L}^{k}(T_{\mathbf{p}}(M))$。如果对每个 $\mathbf{p}$ 有 $\omega(\mathbf{p})$ 是交错张量，我们就称 $\omega$ 是 $M$ 上的一个微分形式。

如果 $\omega$ 是定义在 $\mathbb{R}^{n}$ 中包含 $M$ 的开集上的张量场，那么 $\omega$ 在 $M$ 上的限制就是 $M$ 上的一个张量场，因为每个关于 $M$ 的切向量都是关于 $\mathbb{R}^{n}$ 的切向量。反之，每个 $M$ 上的张量场都可以扩张为一个包含 $M$ 的开集上的张量场。然而，后者的证明是非常不平凡的。因此，为了保持简洁性，我们将假设张量场均定义在 $\mathbb{R}^{n}$ 的开集上。

### Definition 29.8

设 $\mathbf{e}_{1},\dots,\mathbf{e}_{n}$ 是 $\mathbb{R}^{n}$ 的标准基，则 $(\mathbf{x};\mathbf{e}_{1}),\dots,(\mathbf{x};\mathbf{e}_{n})$ 称为 $T_{\mathbf{x}}(\mathbb{R}^{n})$ 的标准基。我们定义 $\mathbb{R}^{n}$ 上的 $1$-形式 $\widetilde{\phi}_{i}$ 为

$$
\begin{gather}
\widetilde{\phi}_{i}(\mathbf{x})(\mathbf{\mathbf{x}};\mathbf{e}_{j})=\delta_{ij}
\end{gather}
$$

我们称 $\widetilde{\phi}_{1},\dots,\widetilde{\phi}_{n}$ 为 $\mathbb{R}^{n}$ 上的基本 $1$-形式。类似地，给定 $\{ 1,\dots,n \}$ 上的一个升序 $k$-元组 $I=(i_{1},\dots,i_{k})$，我们定义 $k$-形式 $\widetilde{\psi}_{I}$ 为

$$
\begin{gather}
\widetilde{\psi}_{I}(\mathbf{x})=\widetilde{\phi}_{i_{1}}(\mathbf{x})\land\dots \land \widetilde{\phi}_{i_{k}}(\mathbf{x})
\end{gather}
$$

我们称 $\widetilde{\psi}_{I}$ 为 $\mathbb{R}^{n}$ 上的基本 $k$-形式。

注意到，对每个 $\mathbf{x}$，$1$-张量 $\widetilde{\phi}_{1}(\mathbf{x}),\dots,\widetilde{\phi}_{n}(\mathbf{x})$ 构成了 $T_{\mathbf{x}}(\mathbb{R}^{n})$ 上对应于标准基的对偶基，并且 $k$-张量 $\widetilde{\psi}_{I}$ 是 $T_{\mathbf{x}}(\mathbb{R}^{n})$ 上的对应的基本交错张量。

此外，$\widetilde{\phi}_{i}$ 和 $\widetilde{\psi}_{I}$ 都是 $C^{\infty}$ 的，因为我们有公式

$$
\begin{align}
&\widetilde{\phi}_{i}(\mathbf{x})(\mathbf{x};\mathbf{v})=v_{i} \\
&\widetilde{\psi}_{I}(\mathbf{x})((\mathbf{x};\mathbf{v}_{1}),\dots,(\mathbf{x};\mathbf{v}_{k}))=\det X_{I}
\end{align}
$$

其中 $X=[\mathbf{v}_{1}\cdots \mathbf{v}_{k}]$。

如果 $\omega$ 是定义在开集 $A$ 上的 $k$-形式，那么 $k$-张量 $\omega(\mathbf{x})$ 可以唯一地表示为

$$
\begin{gather}
\omega(\mathbf{x})=\sum_{[I]} b_{I}(\mathbf{x})\widetilde{\psi}_{I}(\mathbf{x})
\end{gather}
$$

其中标量函数 $b_{I}(\mathbf{x})$ 称为 $\omega$ 相对于基本微分形式的分量。

### Lemma 29.9

设 $\omega$ 是开集 $A$ 上的 $k$-形式，则 $\omega$ 是 $C^{r}$ 连续的当且仅当它的分量 $b_{I}$ 在 $A$ 上 $C^{r}$ 连续。

#### Proof

给定 $\omega$，它可以唯一地表示为

$$
\begin{gather}
\omega=\sum_{[I]} b_{I}\widetilde{\psi}_{I}
\end{gather}
$$

函数 $\widetilde{\psi}_{I}$ 是 $C^{\infty}$ 函数。因此，如果 $b_{I}$ 是 $C^{r}$ 连续的，那么 $\omega$ 也是 $C^{r}$ 连续的。反之，如果 $\omega$ 作为 $(\mathbf{x},\mathbf{v}_{1},\dots,\mathbf{v}_{k})$ 的函数是 $C^{r}$ 连续的，那么特别地，给定升序 $k$-元组 $J=(j_{1},\dots,j_{k})$，函数

$$
\begin{gather}
b_{J}(\mathbf{x})=\omega(\mathbf{x})((\mathbf{x};\mathbf{e}_{j_{1}}),\dots,(\mathbf{x};\mathbf{e}_{j_{k}}))
\end{gather}
$$

作为 $\mathbf{x}$ 的函数是 $C^{r}$ 连续的。

### Lemma 29.10

设 $\omega,\eta$ 是 $k$-形式，$\theta$ 是 $\ell$-形式，定义在开集 $A$ 上。如果 $\omega,\eta,\theta$ 都是 $C^{r}$ 连续的，那么 $a\omega+b \eta$ 和 $\omega \land\theta$ 都是 $C^{r}$ 连续的。

#### Proof

容易证明 $a\omega+b \eta$ 作为两个 $C^{r}$ 函数的和是 $C^{r}$ 连续的。为证 $\omega \land\theta$ 是 $C^{r}$ 函数，我们写

$$
\begin{gather}
\omega=\sum_{[I]} b_{I}\widetilde{\psi}_{I}, \quad \theta=\sum_{[J]} c_{J} \widetilde{\psi}_{J}
\end{gather}
$$

则

$$
\begin{gather}
\omega \land\theta=\sum_{[I]}\sum_{[J]} b_{I}c_{J} \widetilde{\psi}_{I}\land \widetilde{\psi}_{J}
\end{gather}
$$

由于 $\widetilde{\psi}_{I}\land \widetilde{\psi}_{J}$ 或者等于 $0$，或者等于某个 $\widetilde{\psi}_{K}$，因此 $\omega \land\theta$ 的分量函数形如若干 $b_{I}c_{J}$ 之和，从而 [[#Lemma 29.9]] 表明 $\omega \land\theta$ 是 $C^{r}$ 连续的。

## Differential Forms of Order 0

在后面的章节中，我们不仅要研究张量场，还需要研究标量场。由于一个标量场就是一个函数 $f\colon \mathbb{R}^{n}\to \mathbb{R}$，将其视为一个 $0$ 阶的微分形式会很方便。

### Definition 29.11 scalar field 标量场

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 是 $C^{r}$ 函数，则我们称 $f$ 为 $A$ 上的一个标量场。我们也称 $f$ 是一个 $0$ 阶微分形式。

我们定义两个 $0$-形式的楔积为 $f\land g=fg$，即，标量函数的通常乘法。更一般地，我们定义一个 $0$-形式 $f$ 与 $k$-形式 $\omega$ 的楔积为

$$
\begin{gather}
(\omega \land f)(\mathbf{x})=(f\land\omega)(\mathbf{x})=f(\mathbf{x})\omega(\mathbf{x})
\end{gather}
$$

即，$\omega(\mathbf{x})$ 的标量 $f(\mathbf{x})$ 数乘。这一定义满足楔积的所有性质：结合律、齐次性和分配律立即得到，反对称性成立因为

$$
\begin{gather}
f\land g=(-1)^{0}g\land f, \quad f\land\omega=(-1)^{0}\omega \land f
\end{gather}
$$

### Convention

在下文中，我们将用拉丁字母如 $f,g,h$ 来表示 $0$-形式，用希腊字母如 $\omega,\eta,\theta$ 来表示 $k$-形式，$k>0$。

# 30 The Differential Operator

我们现在定义微分形式上的运算 $\mathrm{d}$，称为微分算子。一般来说，对一个 $k$-形式应用微分算子，将得到一个 $k+1$ 阶形式。下面我们从 $0$-形式开始定义微分算子。

## The Differential of a 0-form

一个 $0$-形式是一个函数 $f\colon A\to \mathbb{R}$。它的微分 $\mathrm{d}f$ 是 $A$ 上的一个 $1$-形式，即，从 $T_{\mathbf{x}}(\mathbb{R}^{n})$ 到 $\mathbb{R}$ 的一个线性变换。我们在第二章研究了这样的线性变换，它被称为“$f$ 在 $\mathbf{x}$ 处关于 $\mathbf{v}$ 的方向导数”。

### Definition 30.1 differential 微分

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数。我们定义 $A$ 上的 $1$-形式 $\mathrm{d}f$ 为

$$
\begin{gather}
\mathrm{d}f(\mathbf{x})(\mathbf{x};\mathbf{v})=f'(\mathbf{x};\mathbf{v})=Df(\mathbf{x})\mathbf{v}
\end{gather}
$$

形式 $\mathrm{d}f$ 称为 $f$ 的微分，它是关于 $\mathbf{x}$ 和 $\mathbf{v}$ 的 $C^{r-1}$ 函数。

### Theorem 30.2

算子 $\mathrm{d}$ 对 $0$-形式是线性的。

#### Proof

设 $f,g\colon A\to \mathbb{R}$ 是 $C^{r}$ 函数，$h=af+bg$，则

$$
\begin{gather}
Dh(\mathbf{x})=aDf(\mathbf{x})+bDg(\mathbf{x})
\end{gather}
$$

于是

$$
\begin{gather}
\mathrm{d}h(\mathbf{x})(\mathbf{x};\mathbf{v})=a\mathrm{d}f(\mathbf{x})(\mathbf{x};\mathbf{v})+b\mathrm{d}g(\mathbf{x})(\mathbf{x};\mathbf{v})
\end{gather}
$$

即证 $\mathrm{d}h=a\mathrm{d}f+b\mathrm{d}g$。

利用微分算子，我们可以给出基本 $1$-形式 $\widetilde{\phi}_{i}$ 的另一种表示方法。

### Theorem 30.3

设 $\widetilde{\phi}_{1},\dots,\widetilde{\phi}_{n}$ 为 $\mathbb{R}^{n}$ 上的基本 $1$-形式，令 $\pi_{i}\colon \mathbb{R}^{n}\to \mathbb{R}$ 为在第 $i$ 个坐标上的投影函数，定义为

$$
\begin{gather}
\pi_{i}(x_{1},\dots,x_{n})=x_{i}
\end{gather}
$$

则 $\mathrm{d}\pi_{i}=\widetilde{\phi}_{i}$。

#### Proof

由于 $\pi_{i}$ 是 $C^{\infty}$ 函数，故 $\mathrm{d}\pi_{i}$ 是 $C^{\infty}$ 形式。我们有

$$
\begin{align}
\mathrm{d}\pi_{i}(\mathbf{x})(\mathbf{x};\mathbf{v}) &= D\pi_{i}(\mathbf{x})\mathbf{v} \\
&=[0 \cdots 0\ 1\ 0 \cdots 0] \begin{bmatrix}
v_{1} \\
\vdots \\
v_{n}
\end{bmatrix}=v_{i}
\end{align}
$$

即证 $\mathrm{d}\pi_{i}=\widetilde{\phi}_{i}$。

### Convention

设 $\mathbf{x}$ 是 $\mathbb{R}^{n}$ 的任意点。我们用 $x_{i}$ 来表示在第 $i$ 个坐标下的投影函数 $\pi_{i}$，则 $\mathrm{d}x_{i}=\mathrm{d}\pi_{i}$ 等于基本 $1$-形式 $\widetilde{\phi}_{i}$。如果 $I=(i_{1},\dots,i_{k})$ 是 $\{ 1,\dots,n \}$ 上的一个升序 $k$-元组，我们引入符号

$$
\begin{gather}
\mathrm{d}x_{I}=\mathrm{d}x_{i_{1}}\land\dots \land \mathrm{d}x_{i_{k}}
\end{gather}
$$

来表示基本 $k$-形式 $\widetilde{\psi}_{I}$。于是，一个 $k$-形式可以唯一地表示为

$$
\begin{gather}
\omega=\sum_{[I]} b_{I} \, \mathrm{d}x_{I}
\end{gather}
$$

其中我们有公式

$$
\begin{align}
& \mathrm{d}x_{i}(\mathbf{x})(\mathbf{x};\mathbf{v})=v_{i} \\
& \mathrm{d}x_{I}(\mathbf{x})((\mathbf{x};\mathbf{v}_{1}),\dots,(\mathbf{x};\mathbf{v}_{k}))=\det X_{I}
\end{align}
$$

其中 $X=[\mathbf{v}_{1}\cdots \mathbf{v}_{k}]$。

为了方便起见，我们将以上符号扩张到任意 $k$-元组 $J=(j_{1},\dots,j_{k})$，令

$$
\begin{gather}
\mathrm{d}x_{J}=\mathrm{d}x_{j_{1}}\land\dots \land \mathrm{d}x_{j_{k}}
\end{gather}
$$

注意到，尽管 $\mathrm{d}x_{I}$ 是一个 $k$-形式，但一般来说，$\mathrm{d}x_{J}$ 不是 $k$-形式，而是一系列 $1$-形式的楔积。

如果 $f$ 是 $0$-形式，那么 $\mathrm{d}f$ 是一个 $1$-形式，从而它可以写成基本 $1$-形式的线性组合。下面的公式应当是熟悉的：

### Theorem 30.4

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 是 $C^{r}$ 函数，则

$$
\begin{gather}
\mathrm{d}f=(D_{1}f)\mathrm{d}x_{1}+\dots+(D_{n}f)\mathrm{d}x_{n}
\end{gather}
$$

特别地，$\mathrm{d}f=0$ 当且仅当 $f$ 是常值函数。

#### Proof

我们在切向量 $(\mathbf{x};\mathbf{v})$ 上计算两边的值。我们有

$$
\begin{gather}
\mathrm{d}f(\mathbf{x})(\mathbf{x};\mathbf{v})=Df(\mathbf{x})\mathbf{v}=\sum_{i=1}^{n} D_{i}f(\mathbf{x})v_{i}
\end{gather}
$$

而

$$
\begin{gather}
\sum_{i=1}^{n} D_{i}f(\mathbf{x}) \mathrm{d}x_{i}(\mathbf{x})(\mathbf{x};\mathbf{v})=\sum_{i=1}^{n} D_{i}f(\mathbf{x}) v_{i}
\end{gather}
$$

这就完成了证明。

当 $f$ 是 $C^{r}$ 函数时 $\mathrm{d}f$ 只有 $C^{r-1}$ 连续。这一事实非常不方便，因为我们需要时刻追踪所需的微分次数。为了避免这些技术性的讨论，我们做出如下约定：

### Convention

下面，我们将讨论限定在 $C^{\infty}$ 连续的流形、映射、向量场以及微分形式上。

## The Differential of a $k$-form

### Definition 30.5

设开集 $A\subset \mathbb{R}^{n}$，令 $\Omega^{k}(A)$ 表示所有 $A$ 上的 $k$-形式构成的集合。容易验证 $\Omega^{k}(A)$ 满足向量空间的公理，它被称为 $A$ 上的 $k$-形式向量空间。

### Theorem 30.6

设开集 $A\subset \mathbb{R}^{n}$，存在唯一的线性变换

$$
\begin{gather}
\mathrm{d}\colon \Omega^{k}(A)\to\Omega^{k+1}(A)
\end{gather}
$$

使得

(1) 如果 $f$ 是 $0$-形式，那么 $\mathrm{d}f$ 是 $1$-形式
$$
\begin{gather}
\mathrm{d}f(\mathbf{x})(\mathbf{x};\mathbf{v})=Df(\mathbf{x})\mathbf{v}
\end{gather}
$$
(2) 如果 $\omega,\eta$ 分别是 $k$ 阶和 $\ell$ 阶的形式，则
$$
\begin{gather}
\mathrm{d}(\omega \land \eta)=\mathrm{d}\omega \land \eta+(-1)^{k}\omega \land \mathrm{d}\eta
\end{gather}
$$
(3) 对每个形式 $\omega$，有
$$
\begin{gather}
\mathrm{d}(\mathrm{d}\omega)=0
\end{gather}
$$

我们称 $\mathrm{d}$ 为微分算子，$\mathrm{d}\omega$ 为形式 $\omega$ 的微分。

#### Proof

**第一步** 

我们验证唯一性。首先，我们证明性质 (2)(3) 蕴含对任意形式 $\omega_{1},\dots,\omega_{k}$ 有

$$
\begin{gather}
\mathrm{d}(\mathrm{d}\omega_{1}\land\dots \land \mathrm{d}\omega_{k})=0
\end{gather}
$$

$k=1$ 的情况是 (3) 的推论。假设等式对 $k-1$ 成立，令 $\eta=\mathrm{d}\omega_{2}\land\dots \land \mathrm{d}\omega_{k}$，我们有

$$
\begin{gather}
\mathrm{d}(\mathrm{d}\omega_{1}\land \eta)=\mathrm{d}(\mathrm{d}\omega_{1})\land \eta\pm \omega_{1}\land \mathrm{d}\eta=0
\end{gather}
$$

根据归纳法即证。

现在我们证明对任意 $k$-形式 $\omega$，其微分 $\mathrm{d}\omega$ 完全由 $\mathrm{d}$ 在 $0$-形式上的取值决定，后者由 (1) 给出。由于 $\mathrm{d}$ 是线性的，我们只需考虑 $\omega=f\,\mathrm{d}x_{I}$，得到

$$
\begin{align}
\mathrm{d}\omega=\mathrm{d}(f\, \mathrm{d}x_{I}) &= \mathrm{d}(f\land \mathrm{d}x_{I}) \\
&=\mathrm{d}f\land \mathrm{d}x_{I}+f\land \mathrm{d}(\mathrm{d}x_{I}) \\
&=\mathrm{d}f\land \mathrm{d}x_{I}
\end{align}
$$

因此 $\mathrm{d}\omega$ 由 $\mathrm{d}$ 在 $f$ 上的值确定。

**第二步**

我们定义算子 $\mathrm{d}$。它在 $0$-形式上的取值由 (1) 给出。对于 $k>0$，第一步的证明中给出了 $\mathrm{d}\omega$ 的计算方式：将 $\omega$ 写成

$$
\begin{gather}
\omega=\sum_{[I]} f_{I}\, \mathrm{d}x_{I}
\end{gather}
$$

我们定义

$$
\begin{gather}
\mathrm{d}\omega=\sum_{[I]} \mathrm{d}f_{I}\land \mathrm{d}x_{I}
\end{gather}
$$

我们验证 $\mathrm{d}\omega$ 是 $C^{\infty}$ 的。为此，我们计算

$$
\begin{gather}
\mathrm{d}\omega=\sum_{[I]} \left( \sum_{j=1}^{n} (D_{j}f)\mathrm{d}x_{j} \right)\land \mathrm{d}x_{I}
\end{gather}
$$

则我们可知 $\mathrm{d}\omega$ 是 $k+1$ 阶基本交错张量的线性组合，它的每个分量都是函数 $D_{j}f$ 的线性组合，因而 $\mathrm{d}\omega$ 是 $C^{\infty}$ 的。（注意到如果 $\omega$ 是 $C^{r}$ 的，那么 $\mathrm{d}\omega$ 就是 $C^{r-1}$ 连续的。）

我们证明 $\mathrm{d}$ 对于 $k$-形式（$k>0$）是线性的。令

$$
\begin{gather}
\omega=\sum_{[I]} f_{I}\, \mathrm{d}x_{I}, \quad \eta=\sum_{[I]} g_{I}\, \mathrm{d}x_{I}
\end{gather}
$$

则

$$
\begin{align}
\mathrm{d}(a\omega+b \eta)&= \mathrm{d} \sum_{[I]} (af_{I}+bg_{I}) \mathrm{d}x_{I} \\
&=\sum_{[I]} \mathrm{d}(af_{I}+bg_{I})\land \mathrm{d}x_{I} \\
&=\sum_{[I]} (a\mathrm{d}f_{I}+b\mathrm{d}g_{I})\land \mathrm{d}x_{I} \\
&=a\mathrm{d}\omega+b\mathrm{d}\eta
\end{align}
$$

**第三步**

我们来证明如果 $J$ 是任意 $k$-元组，那么

$$
\begin{gather}
\mathrm{d}(f\land \mathrm{d}x_{J})=\mathrm{d}f\land \mathrm{d}x_{J}
\end{gather}
$$

显然，如果 $J$ 中有两个指标相同，那么 $\mathrm{d}x_{J}=0$，从而等式两边都为零。下面我们假设 $J$ 中的指标各不相同。令 $I$ 为将 $J$ 升序排列得到的 $k$-元组，$\pi$ 为完成这一排序所用的置换。楔积的反对称性给出 $\mathrm{d}x_{I}=(\operatorname{sgn}\pi)\mathrm{d}x_{J}$，又由 $\mathrm{d}$ 的线性性与楔积的齐次性，我们有

$$
\begin{gather}
(\operatorname{sgn}\pi)\mathrm{d}(f\land \mathrm{d}x_{J})=\mathrm{d}(f\land \mathrm{d}x_{I})=\mathrm{d}f\land \mathrm{d}x_{I}=(\operatorname{sgn}\pi)\mathrm{d}f\land \mathrm{d}x_{J}
\end{gather}
$$

**第四步**

我们对 $0$-形式验证性质 (2)。我们有

$$
\begin{align}
\mathrm{d}(f\land g) &= \sum_{j=1}^{n} D_{j}(fg) \mathrm{d}x_{j} \\
&=\sum_{j=1}^{n} (gD_{j}f+fD_{j}g)\mathrm{d}x_{j} \\
&=\mathrm{d}f\land g+f\land \mathrm{d}g
\end{align}
$$

**第五步**

我们对所有形式验证性质 (2)。首先我们考虑 $\omega,\eta$ 的阶数都为正数的情况。由于等式两边关于 $\omega$ 和 $\eta$ 都是线性的，故我们只需考虑

$$
\begin{gather}
\omega=f\, \mathrm{d}x_{I},\quad \eta=g\, \mathrm{d}x_{J}
\end{gather}
$$

我们有

$$
\begin{align}
\mathrm{d}(\omega \land \eta) &= \mathrm{d}(fg\, \mathrm{d}x_{I}\land \mathrm{d}x_{J}) \\
&=\mathrm{d}(fg)\land \mathrm{d}x_{I}\land \mathrm{d}x_{J} \\
&=(\mathrm{d}f\land g+f\land \mathrm{d}g)\land \mathrm{d}x_{I}\land \mathrm{d}x_{J} \\
&=\mathrm{d}f\land \mathrm{d}x_{I}\land g\land \mathrm{d}x_{J}+(-1)^{k}f\land \mathrm{d}x_{I}\land \mathrm{d}g\land \mathrm{d}x_{J} \\
&=\mathrm{d}\omega \land \eta+(-1)^{k} \omega \land \mathrm{d}\eta
\end{align}
$$

其中因子 $(-1)^{k}$ 来源于交换 $1$-形式 $\mathrm{d}g$ 与 $k$-形式 $\mathrm{d}x_{I}$。

如果 $\omega$ 是 $0$ 阶的，那么 $\mathrm{d}x_{I}$ 这一项消失；如果 $\eta$ 是 $0$ 阶的，那么 $\mathrm{d}x_{J}$ 这一项消失。无论哪种情况，我们仍然有等式成立，即证。

**第六步**

我们对 $0$-形式 $f$ 证明性质 (3)。我们有

$$
\begin{align}
\mathrm{d}(\mathrm{d}f) &= \mathrm{d} \sum_{j=1}^{n} D_{j}f\, \mathrm{d}x_{j} \\
&=\sum_{j=1}^{n} \mathrm{d}(D_{j}f)\land \mathrm{d}x_{j} \\
&=\sum_{j=1}^{n} \sum_{i=1}^{n} D_{i}D_{j}f \, \mathrm{d}x_{i}\land \mathrm{d}x_{j}
\end{align}
$$

我们将以上求和中的 $\mathrm{d}x_{i}\land \mathrm{d}x_{j}$ 都变成 $i<j$ 的形式，则有

$$
\begin{gather}
\mathrm{d}(\mathrm{d}f)=\sum_{1\leq i<j\leq n} (D_{i}D_{j}f-D_{j}D_{i}f)\mathrm{d}x_{i}\land \mathrm{d}x_{j}=0
\end{gather}
$$

**第七步**

我们对正数阶形式 $\omega$ 证明性质 (3)。由于 $\mathrm{d}$ 是线性的，我们只需考虑 $\omega=f\,\mathrm{d}x_{I}$，此时

$$
\begin{align}
\mathrm{d}(\mathrm{d}\omega) &= \mathrm{d}(\mathrm{d}f\land \mathrm{d}x_{I}) \\
&=\mathrm{d}(\mathrm{d}f)\land \mathrm{d}x_{I}-\mathrm{d}f\land \mathrm{d}(\mathrm{d}x_{I})
\end{align}
$$

根据第六步，$\mathrm{d}(\mathrm{d}f)=0$。又

$$
\begin{gather}
\mathrm{d}(\mathrm{d}x_{I})=\mathrm{d}(1)\land \mathrm{d}x_{I}=0
\end{gather}
$$

故 $\mathrm{d}(\mathrm{d}\omega)=0$。

### Definition 30.7 closed 闭的，exact 恰当的

设开集 $A\subset \mathbb{R}^{n}$。称一个 $0$-形式 $f$ 是恰当的，如果 $f$ 在 $A$ 上是常值函数；对于 $k>0$，一个 $k$-形式 $\omega$ 是恰当的，如果存在 $k-1$ 阶形式 $\theta$ 使得 $\omega=\mathrm{d}\theta$。对于 $k\geq 0$，称一个 $k$-形式 $\omega$ 是闭的，如果 $\mathrm{d}\omega=0$。

任何恰当形式都是闭的：如果 $f$ 是常值函数，那么 $\mathrm{d}f=0$；如果 $\omega=\mathrm{d}\theta$，那么 $\mathrm{d}\omega=\mathrm{d}(\mathrm{d}\theta)=0$。反之则不一定。如果 $A$ 上的任何闭 $k$-形式都是恰当 $k$-形式，我们就称 $A$ 在 $k$ 维是同调平凡的。

### Example 30.8

恰当性是一个熟悉的概念。例如，称微分方程

$$
\begin{gather}
P(x,y)\,\mathrm{d}x+Q(x,y)\,\mathrm{d}y=0
\end{gather}
$$

是恰当的，如果存在函数 $f$ 使得 $P=\partial f /\partial x,Q=\partial f /\partial y$。在我们的术语中，这就是说 $1$-形式 $P\,\mathrm{d}x+Q\,\mathrm{d}y$ 等于 $0$-形式 $f$ 的微分，因此它是恰当的。

恰当性还与向量场的保守性紧密相关。称向量场

$$
\begin{gather}
F=P\mathbf{e}_{1}+Q\mathbf{e}_{2}+R\mathbf{e}_{3}
\end{gather}
$$

是保守的，如果它是一个标量函数 $f$ 的梯度，这就是说，如果

$$
\begin{gather}
P=\frac{ \partial f }{ \partial x } , \quad Q=\frac{ \partial f }{ \partial y } , \quad R=\frac{ \partial f }{ \partial z } 
\end{gather}
$$

这等价于说 $1$-形式 $P\,\mathrm{d}x+Q\,\mathrm{d}y+R\,\mathrm{d}z$ 是 $0$-形式 $f$ 的微分。在下一节，我们将深入研究向量场与微分形式的对应关系。

# 31 Application to Vector and Scalar Fields

本节我们来证明张量场与微分算子可以被视为向量场以及其上的梯度、散度和旋度的正确推广。这可以通过构造从 $\Omega^{k}(A)$ 到 $A$ 上的向量场的同构实现。

### Definition 31.1 gradient 梯度，divergence 散度

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 是 $A$ 上的标量场。我们定义 $f$ 的梯度 $\operatorname{grad}f$ 为向量场

$$
\begin{gather}
(\operatorname{grad}f)(\mathbf{x})=(\mathbf{x};D_{1}f(\mathbf{x})\mathbf{e}_{1}+\dots+D_{n}f(\mathbf{x})\mathbf{e}_{n})
\end{gather}
$$

设 $G(\mathbf{x})=(\mathbf{x};g(\mathbf{x}))$ 为 $A$ 上的向量场，其中 $g\colon A\to \mathbb{R}^{n}$ 定义为

$$
\begin{gather}
g(\mathbf{x})=g_{1}(\mathbf{x})\mathbf{e}_{1}+\dots+g_{n}(\mathbf{x})\mathbf{e}_{n}
\end{gather}
$$

则我们定义 $G$ 的散度 $\operatorname{div}G$ 为标量场

$$
\begin{gather}
(\operatorname{div}G)(\mathbf{x})=D_{1}g_{1}(\mathbf{x})+\dots+D_{n}g_{n}(\mathbf{x})
\end{gather}
$$

### Theorem 31.2

设开集 $A\subset \mathbb{R}^{n}$，则存在线性同构 $\alpha_{i}$ 和 $\beta_{j}$ 使得下图交换：

<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsOCxbMCwwLCJcXHRleHR7U2NhbGFyIEZpZWxkcyBpbn1cXCBBIl0sWzAsMSwiXFx0ZXh0e1ZlY3RvciBGaWVsZHMgaW59XFwgQSJdLFsyLDAsIlxcT21lZ2FeMChBKSJdLFsyLDEsIlxcT21lZ2FeMShBKSJdLFswLDIsIlxcdGV4dHtWZWN0b3IgRmllbGRzIGlufVxcIEEiXSxbMCwzLCJcXHRleHR7U2NhbGFyIEZpZWxkcyBpbn1cXCBBIl0sWzIsMiwiXFxPbWVnYV57bi0xfShBKSJdLFsyLDMsIlxcT21lZ2Fee259KEEpIl0sWzAsMSwiXFxvcGVyYXRvcm5hbWV7Z3JhZH0iXSxbMiwzLCJcXG1hdGhybXtkfSJdLFswLDIsIlxcYWxwaGFfMCJdLFsxLDMsIlxcYWxwaGFfMSJdLFs0LDUsIlxcb3BlcmF0b3JuYW1le2Rpdn0iXSxbNiw3LCJcXG1hdGhybXtkfSJdLFs0LDYsIlxcYmV0YV97bi0xfSJdLFs1LDcsIlxcYmV0YV97bn0iXV0=&embed&theme=dark" width="600" height="400" style="border-radius: 8px; border: none;"></iframe>

这就是说，

$$
\begin{gather}
\mathrm{d}\circ\alpha_{0}=\alpha_{1}\circ \operatorname{grad}, \quad \mathrm{d}\circ\beta_{n-1}=\beta_{n}\circ \operatorname{div}
\end{gather}
$$

#### Proof

令 $f,h$ 为 $A$ 上的标量场，并令

$$
\begin{gather}
F(\mathbf{x})=\left( \mathbf{x};\sum f_{i}(\mathbf{x})\mathbf{e}_{i} \right), \quad G(\mathbf{x})=\left( \mathbf{x};\sum g_{i}(\mathbf{x})\mathbf{e}_{i} \right)
\end{gather}
$$

为 $A$ 上的向量场，我们定义映射 $\alpha_{i},\beta_{j}$ 为

$$
\begin{align}
\alpha_{0}f &= f \\
\alpha_{1}F &= \sum_{i=1}^{n} f_{i}\, \mathrm{d}x_{i} \\
\beta_{n-1}G &= \sum_{i=1}^{n} (-1)^{i-1}g_{i}\, \mathrm{d}x_{1}\land\dots \land \widehat{\mathrm{d}x}_{i} \land \dots \land \mathrm{d}x_{n} \\
\beta_{n}h &= h\, \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{n}
\end{align}
$$

其中我们用 $\widehat{\mathrm{d}x}_{i}$ 表示去掉 $\mathrm{d}x_{i}$ 这一项。容易验证 $\alpha_{i},\beta_{j}$ 是线性的，并且它们是同构，因为 $\mathrm{d}x_{i}$ 和 $\mathrm{d}x_{1}\land\dots \land \widehat{\mathrm{d}x}_{i}\land\dots \land \mathrm{d}x_{n}$ 分别构成了 $\Omega^{1}(A)$ 和 $\Omega^{n-1}(A)$ 的基，$\alpha_{1}$ 和 $\beta_{n-1}$ 将定义域的标准基映射到了这两个基上。

最后我们验证图的交换性。给定标量场 $f$，我们有

$$
\begin{align}
\mathrm{d}\circ\alpha_{0}(f)&=\mathrm{d}f=\sum_{i=1}^{n} D_{i}f\, \mathrm{d}x_{i} \\
\alpha_{1}\circ \operatorname{grad}(f) &=\alpha_{1}\left( \mathbf{x};\sum_{i=1}^{n} D_{i}f(\mathbf{x})\mathbf{e}_{i} \right)=\sum_{i=1}^{n} D_{i}f \, \mathrm{d}x_{i}
\end{align}
$$

以及对于向量场 $G$ 有

$$
\begin{align}
\mathrm{d}\circ\beta_{n-1}(G) &= \mathrm{d} \sum_{i=1}^{n} (-1)^{i-1}g_{i} \, \mathrm{d}x_{1}\land\dots \land \widehat{\mathrm{d}x}_{i}\land\dots \land \mathrm{d}x_{n} \\
&=\sum_{i=1}^{n} (-1)^{i-1}\left( \sum_{j=1}^{n} D_{j}g_{i}\,\mathrm{d}x_{j} \right) \land \mathrm{d}x_{1}\land\dots \land \widehat{\mathrm{d}x}_{i}\land\dots \land \mathrm{d}x_{n} \\
&=\sum_{i=1}^{n} (-1)^{i-1}D_{i}g_{i} \, \mathrm{d}x_{i}\land \mathrm{d}x_{1}\land\dots \land \widehat{\mathrm{d}x}_{i}\land\dots \land \mathrm{d}x_{n} \\
&=\sum_{i=1}^{n} D_{i}g_{i} \, \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{n} \\
\beta_{n}\circ \operatorname{div}(G) &=\beta_{n}\left( \sum_{i=1}^{n} D_{i}g_{i} \right)=\sum_{i=1}^{n} D_{i}g_{i}\, \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{n}
\end{align}
$$

这就完成了证明。

以上定理表明梯度和散度在本质上是微分算子 $\mathrm{d}$ 在不同维度下的限制。当 $n=3$ 时，我们进一步还可以定义一个旋度算子，它连接了上面交换图中“断裂”的部分。

### Definition 31.3 curl 旋度

设开集 $A\subset \mathbb{R}^{3}$，令

$$
\begin{gather}
F(\mathbf{x})=\left( \mathbf{x};\sum f_{i}(\mathbf{x})\mathbf{e}_{i} \right)
\end{gather}
$$

为 $A$ 上的向量场。我们定义 $F$ 的旋度 $\operatorname{curl}F$ 为向量场

$$
\begin{gather}
(\operatorname{curl}F)(\mathbf{x})=(\mathbf{x};(D_{2}f_{3}-D_{3}f_{2})\mathbf{e}_{1}+(D_{3}f_{1}-D_{1}f_{3})\mathbf{e}_{2}+(D_{1}f_{2}-D_{2}f_{1})\mathbf{e}_{3})
\end{gather}
$$

为便于记忆，我们将右侧的表达式形式地写成

$$
\begin{gather}
\det \begin{bmatrix}
\mathbf{e}_{1} & \mathbf{e}_{2} & \mathbf{e}_{3} \\
D_{1} & D_{2} & D_{3} \\
f_{1} & f_{2} & f_{3}
\end{bmatrix}
\end{gather}
$$

### Theorem 31.4

设开集 $A\subset \mathbb{R}^{3}$，则存在线性同构 $\alpha_{i},\beta_{j}$ 使得下图交换：

<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsOCxbMCwwLCJcXHRleHR7U2NhbGFyIEZpZWxkcyBpbn1cXCBBIl0sWzAsMSwiXFx0ZXh0e1ZlY3RvciBGaWVsZHMgaW59XFwgQSJdLFsyLDAsIlxcT21lZ2FeMChBKSJdLFsyLDEsIlxcT21lZ2FeMShBKSJdLFswLDIsIlxcdGV4dHtWZWN0b3IgRmllbGRzIGlufVxcIEEiXSxbMCwzLCJcXHRleHR7U2NhbGFyIEZpZWxkcyBpbn1cXCBBIl0sWzIsMiwiXFxPbWVnYV57Mn0oQSkiXSxbMiwzLCJcXE9tZWdhXnszfShBKSJdLFswLDEsIlxcb3BlcmF0b3JuYW1le2dyYWR9Il0sWzIsMywiXFxtYXRocm17ZH0iXSxbMCwyLCJcXGFscGhhXzAiXSxbMSwzLCJcXGFscGhhXzEiXSxbNCw1LCJcXG9wZXJhdG9ybmFtZXtkaXZ9Il0sWzYsNywiXFxtYXRocm17ZH0iXSxbNCw2LCJcXGJldGFfezJ9Il0sWzUsNywiXFxiZXRhX3szfSJdLFsxLDQsIlxcb3BlcmF0b3JuYW1le2N1cmx9Il0sWzMsNiwiXFxtYXRocm17ZH0iXV0=&embed&theme=dark" width="600" height="400" style="border-radius: 8px; border: none;"></iframe>

这就是说，

$$
\begin{gather}
\mathrm{d}\circ\alpha_{0}=\alpha_{1}\circ \operatorname{grad},\quad \mathrm{d}\circ\alpha_{1}=\beta_{2}\circ \operatorname{curl}, \quad \mathrm{d}\circ\beta_{2}=\beta_{3}\circ \operatorname{div}
\end{gather}
$$

#### Proof

我们在 [[#Theorem 31.2]] 中已给出了 $\alpha_{i},\beta_{j}$ 的定义。这里我们只需证明第二个等式。

设 $F(\mathbf{x})=(\mathbf{x};f_{1}(\mathbf{x})\mathbf{e}_{1}+f_{2}(\mathbf{x})\mathbf{e}_{2}+f_{3}(\mathbf{x})\mathbf{e}_{3})$ 是 $A$ 上的向量场，则

$$
\begin{align}
\mathrm{d}\circ\alpha_{1}(F) &= \mathrm{d} \sum_{i=1}^{3} f_{i}\, \mathrm{d}x_{i} \\
&=\sum_{i=1}^{3} \sum_{j=1}^{3} (D_{j}f_{i}) \mathrm{d}x_{j}\land \mathrm{d}x_{i} \\
&=(D_{1}f_{2}-D_{2}f_{1})\mathrm{d}x_{1}\land \mathrm{d}x_{2}+(D_{1}f_{3}-D_{3}f_{1})\mathrm{d}x_{1}\land \mathrm{d}x_{3} \\
&+(D_{2}f_{3}-D_{3}f_{2})\mathrm{d}x_{2}\land \mathrm{d}x_{3} \\
\beta_{2}\circ \operatorname{curl}(F) &=\beta_{2}(\mathbf{x};(D_{2}f_{3}-D_{3}f_{2})\mathbf{e}_{1}+(D_{3}f_{1}-D_{1}f_{3})\mathbf{e}_{2}+(D_{1}f_{2}-D_{2}f_{1})\mathbf{e}_{3}) \\
&=(D_{2}f_{3}-D_{3}f_{2})\mathrm{d}x_{2}\land \mathrm{d}x_{3}+(-1)(D_{3}f_{1}-D_{1}f_{3})\mathrm{d}x_{1}\land \mathrm{d}x_{3} \\
&+(D_{1}f_{2}-D_{2}f_{1})\mathrm{d}x_{1}\land \mathrm{d}x_{2}
\end{align}
$$

对比等式右侧表达式即证。

# 32 The Action of a Differentiable Map

设 $\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{\infty}$ 函数，其中 $A\subset \mathbb{R}^{k}$ 是开集，则 $\alpha$ 诱导了一个从 $\mathbf{x}$ 的切空间到 $\alpha(\mathbf{x})$ 的切空间的线性映射 $\alpha_{*}$。此外，我们知道任何线性映射 $T\colon V\to W$ 都诱导了一个交错张量的拉回 $T^{*}\colon \mathcal{A}^{\ell}(W)\to \mathcal{A}^{\ell}(V)$。我们将这两个事实组合，以展示一个函数 $\alpha$ 如何诱导了微分形式的一个拉回 $\alpha^{*}$，它保持了微分形式空间中的所有运算：向量空间结构、楔积，以及微分算子。

### Definition 32.1

设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{\infty}$ 函数。设 $B$ 是 $\mathbb{R}^{n}$ 中包含 $\alpha(A)$ 的开集。我们定义对偶变换

$$
\begin{gather}
\alpha^{*}\colon\Omega^{\ell}(B)\to\Omega^{\ell}(A)
\end{gather}
$$

如下：对于 $0$-形式 $f\colon B\to \mathbb{R}$，令 $(\alpha^{*}f)(\mathbf{x})=f(\alpha(\mathbf{x}))$；而对 $\ell>0$ 的 $\ell$-形式 $\omega$ 有

$$
\begin{gather}
(\alpha^{*}\omega)(\mathbf{x})((\mathbf{x};\mathbf{v}_{1}),\dots,(\mathbf{x};\mathbf{v}_{\ell}))=\omega(\alpha(\mathbf{x}))(\alpha_{*}(\mathbf{x};\mathbf{v}_{1}),\dots,\alpha_{*}(\mathbf{x};\mathbf{v}_{\ell}))
\end{gather}
$$

注意到，如果 $f,\omega$ 和 $\alpha$ 都是 $C^{r}$ 连续的，那么 $\alpha^{*}f$ 是 $C^{r}$ 的，但 $\alpha^{*}\omega$ 仅仅是 $C^{r-1}$ 连续的。因此，我们将讨论限制在 $C^{\infty}$ 结构上更为方便。

拉回 $\alpha^{*}$ 与线性变换 $\alpha_{*}$ 的对偶的关系如下所示：给定 $\alpha\colon A\to \mathbb{R}^{n}$，设 $\alpha(\mathbf{x})=\mathbf{y}$，它诱导了线性变换

$$
\begin{gather}
T=\alpha_{*}\colon T_{\mathbf{x}}(\mathbb{R}^{k})\to T_{\mathbf{y}}(\mathbb{R}^{n})
\end{gather}
$$

这一线性变换又给出了切向量上的张量之间的拉回

$$
\begin{gather}
T^{*}\colon \mathcal{A}^{\ell}(T_{\mathbf{y}}(\mathbb{R}^{n}))\to \mathcal{A}^{\ell}(T_{\mathbf{x}}(\mathbb{R}^{k}))
\end{gather}
$$

如果 $\omega$ 是 $B$ 上的 $\ell$ 形式，则 $\omega(\mathbf{y})$ 是 $T_{\mathbf{y}}(\mathbb{R}^{n})$ 上的交错张量，于是 $T^{*}(\omega(\mathbf{y}))$ 是 $T_{\mathbf{x}}(\mathbb{R}^{k})$ 上的交错张量，满足

$$
\begin{gather}
T^{*}(\omega(\mathbf{y}))=(\alpha^{*}\omega)(\mathbf{x})
\end{gather}
$$

因为

$$
\begin{align}
T^{*}(\omega(\mathbf{y}))((\mathbf{x};\mathbf{v}_{1}),\dots,(\mathbf{x};\mathbf{v}_{\ell})) &= \omega(\alpha(\mathbf{x}))(\alpha_{*}(\mathbf{x};\mathbf{v}_{1}),\dots,\alpha_{*}(\mathbf{x};\mathbf{v}_{\ell})) \\
&=(\alpha^{*}\omega)(\mathbf{x})((\mathbf{x};\mathbf{v}_{1}),\dots,(\mathbf{x};\mathbf{v}_{\ell}))
\end{align}
$$

这一事实允许我们将对偶映射 $T^{*}$ 的性质推广到形式上。

### Theorem 32.2

设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{m}$ 为 $C^{\infty}$ 函数。设开集 $B\subset \mathbb{R}^{m}$ 包含 $\alpha(A)$，$\beta\colon B\to \mathbb{R}^{n}$ 为 $C^{\infty}$ 函数。设 $\omega,\eta,\theta$ 为定义在包含 $\beta(B)$ 的开集 $C$ 上的形式，$\omega$ 和 $\eta$ 的阶数相同。

1. $\beta^{*}(a\omega+b \eta)=a\beta^{*}\omega+b\beta^{*}\eta$，
2. $\beta^{*}(\omega \land\theta)=\beta^{*}\omega \land\beta^{*}\theta$，
3. $(\beta \circ\alpha)^{*}\omega=\alpha^{*}(\beta^{*}\omega)$。

以上定理表明 $\alpha^{*}$ 保持向量空间结构与楔积，下面我们来证明它保持微分算子 $\mathrm{d}$。为此，我们给出 $\alpha^{*}\omega$ 的一个计算公式，其中 $\alpha\colon A\to \mathbb{R}^{n}$，$A\subset \mathbb{R}^{k}$ 为开集。在后续的章节中，我们只会用到 $\omega$ 是 $1$-形式与 $k$-形式时的公式，又因为 $\alpha^{*}$ 是线性的，我们只需考虑 $\omega$ 是基本形式的情况。

### Theorem 32.3

设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{n}$ 为 $C^{\infty}$ 函数。设 $\mathbf{x}$ 为 $\mathbb{R}^{k}$ 的任意点，$\mathbf{y}$ 为 $\mathbb{R}^{n}$ 的任意点，则 $\mathrm{d}x_{i}$ 和 $\mathrm{d}y_{i}$ 分别是 $\mathbb{R}^{k}$ 和 $\mathbb{R}^{n}$ 上的基本 $1$-形式。

(a) $\alpha^{*}(\mathrm{d}y_{i})=\mathrm{d}\alpha_{i}$。
(b) 如果 $I=(i_{1},\dots,i_{k})$ 是 $\{ 1,\dots,n \}$ 上的升序 $k$-元组，则
$$
\begin{gather}
\alpha^{*}(\mathrm{d}y_{I})=\left( \det \frac{ \partial \alpha_{I} }{ \partial \mathbf{x} }  \right) \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}
\end{gather}
$$
其中
$$
\begin{gather}
\frac{ \partial \alpha_{I} }{ \partial \mathbf{x} } = \frac{ \partial (\alpha_{i_{1}},\dots,\alpha_{i_{k}}) }{ \partial (x_{1},\dots,x_{k}) } 
\end{gather}
$$

#### Proof

(a) 令 $\mathbf{y}=\alpha(\mathbf{x})$，我们计算

$$
\begin{align}
\alpha^{*}(\mathrm{d}y_{i})(\mathbf{x})(\mathbf{x};\mathbf{v}) &= \mathrm{d}y_{i}(\mathbf{y})(\alpha_{*}(\mathbf{x};\mathbf{v})) \\
&= \mathrm{d}y_{i}(\mathbf{y})(\mathbf{y};D\alpha(\mathbf{x})\mathbf{v}) \\
&= \sum_{j=1}^{k} D_{j}\alpha_{i}(\mathbf{x}) v_{j} \\
&= \sum_{j=1}^{k} D_{j}\alpha_{i}(\mathbf{x}) \, \mathrm{d}x_{j}(\mathbf{x})(\mathbf{x};\mathbf{v})
\end{align}
$$

而后者就是 $\mathrm{d}\alpha_{i}=\sum D_{j}\alpha_{i}\, \mathrm{d}x_{j}$。

(b) $\alpha^{*}(\mathrm{d}y_{I})$ 是 $\mathbb{R}^{k}$ 上的一个 $k$-形式，因此存在标量函数 $h$ 使得

$$
\begin{gather}
\alpha^{*}(\mathrm{d}y_{I})=h \, \mathrm{d}x_{1}\land\dots \land \mathrm{d}x_{k}
\end{gather}
$$

对上式在 $(\mathbf{x};\mathbf{e}_{1}),\dots,(\mathbf{x};\mathbf{e}_{k})$ 上的取值，我们有

$$
\begin{align}
h(\mathbf{x}) &= \alpha^{*}(\mathrm{d}y_{I})(\mathbf{x})((\mathbf{x};\mathbf{e}_{1}),\dots,(\mathbf{x};\mathbf{e}_{k})) \\
&= \mathrm{d}y_{I}(\mathbf{y})(\alpha_{*}(\mathbf{x};\mathbf{e}_{1}),\dots,\alpha_{*}(\mathbf{x};\mathbf{e}_{k})) \\
&=\mathrm{d}y_{I}(\mathbf{y})((\mathbf{y};\partial\alpha /\partial x_{1}),\dots,(\mathbf{y};\partial\alpha / \partial x_{k})) \\
&=\det (D\alpha(\mathbf{x}))_{I} \\
&=\det \frac{ \partial \alpha_{I} }{ \partial \mathbf{x} } 
\end{align}
$$

这就完成了证明。

### Theorem 32.4

设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{n}$ 为 $C^{\infty}$ 函数。如果 $\omega$ 是定义在包含 $\alpha(A)$ 的开集上的 $\ell$-形式，那么

$$
\begin{gather}
\alpha^{*}(\mathrm{d}\omega)=\mathrm{d}(\alpha^{*}\omega)
\end{gather}
$$

#### Proof

设 $\mathbf{x},\mathbf{y}$ 分别为 $\mathbb{R}^{k}$ 和 $\mathbb{R}^{n}$ 中的任意点。

**第一步** 我们对 $0$-形式进行验证。我们有

$$
\begin{align}
\alpha^{*}(\mathrm{d}f) &= \alpha^{*} \sum_{i=1}^{n} D_{i}f \,\mathrm{d}y_{i} \tag{$\ast$} \\
&=\sum_{i=1}^{n} (D_{i}f \circ\alpha)\, \mathrm{d}\alpha_{i}
\end{align}
$$

另一方面，

$$
\begin{align}
\mathrm{d}(\alpha^{*}f) &= \mathrm{d}(f\circ\alpha) \tag{$\ast\ast$} \\
&=\sum_{j=1}^{k} D_{j}(f\circ\alpha) \, \mathrm{d}x_{j}
\end{align}
$$

应用链式法则，令 $\mathbf{y}=\alpha(\mathbf{x})$，则

$$
\begin{gather}
D(f\circ\alpha)(\mathbf{x})=Df(\mathbf{y}) D\alpha(\mathbf{x})
\end{gather}
$$

于是

$$
\begin{gather}
D_{j}(f\circ\alpha)(\mathbf{x})=\sum_{i=1}^{n} D_{i}f(\mathbf{y}) D_{j}\alpha_{i}(\mathbf{x})
\end{gather}
$$

即

$$
\begin{gather}
D_{j}(f\circ\alpha)=\sum_{i=1}^{n} (D_{i}f\circ\alpha)D_{j}\alpha_{i}
\end{gather}
$$

代入 $(\ast\ast)$ 即得

$$
\begin{align}
\mathrm{d}(\alpha^{*}f) &= \sum_{j=1}^{k} \sum_{i=1}^{n} (D_{i}f\circ\alpha) D_{j}\alpha_{i} \, \mathrm{d}x_{j} \\
&=\sum_{i=1}^{n} (D_{i}f\circ\alpha) \,\mathrm{d}\alpha_{i}
\end{align}
$$

**第二步** 我们验证阶数为正的情况。

由于 $\alpha^{*}$ 和 $\mathrm{d}$ 是线性的，我们只需考虑 $\omega=f\,\mathrm{d}y_{I}$ 的情况。首先我们有

$$
\begin{align}
\alpha^{*}(\mathrm{d}\omega) &= \alpha^{*}(\mathrm{d}f\land \mathrm{d}y_{I}) \tag{$\dagger$} \\
&=\alpha^{*}(\mathrm{d}f)\land\alpha^{*}(\mathrm{d}y_{I})
\end{align}
$$

另一方面，

$$
\begin{align}
\mathrm{d}(\alpha^{*}\omega) &= \mathrm{d}(\alpha^{*}f\land\alpha^{*}(\mathrm{d}y_{I})) \tag{$\dagger\dagger$} \\
&=\mathrm{d}(\alpha^{*}f)\land\alpha^{*}(\mathrm{d}y_{I})+\alpha^{*}f\land 0
\end{align}
$$

因为

$$
\begin{gather}
\mathrm{d}(\mathrm{d}y_{I})=\mathrm{d}(\mathrm{d}y_{i_{1}}\land\dots \land \mathrm{d}y_{i_{\ell}})=0
\end{gather}
$$

比较 $(\dagger)$ 和 $(\dagger\dagger)$，然后应用第一步的结论即证。

正是在本节的拉回角度下，我们才能看到微分形式在某种意义上是比向量场更为“自然”的对象。一个函数 $\alpha\colon A\to \mathbb{R}^{n}$ 总是诱导了切向量上的线性变换 $\alpha_{*}$，但我们没有一种方法能够从 $\alpha$ 中得到从 $A$ 上的向量场映射到 $\alpha(A)$ 上的向量场的变换。例如，设 $F(\mathbf{x})=(\mathbf{x};f(\mathbf{x}))$ 是 $A$ 上的向量场，如果 $\mathbf{y} \in B=\alpha(A)$ 使得 $\mathbf{y}=\alpha(\mathbf{x}_{1})=\alpha(\mathbf{x}_{2})$，那么 $\alpha_{*}$ 在 $\mathbf{y}$ 处可能有两个完全不同的切线方向，如图所示。

![](6-4.png)

如果 $\alpha\colon A\to B$ 是微分同胚，那么以上问题不会出现。此时，我们可以定义向量场上的诱导变换 $\widetilde{\alpha}_{*}$，其将 $A$ 上的向量场映射到 $B$ 上的向量场

$$
\begin{gather}
G(\mathbf{y})=(\widetilde{\alpha}_{*}F)(\mathbf{y})=\alpha_{*}(F(\alpha^{-1}(\mathbf{y})))
\end{gather}
$$

然而，这一变换 $\widetilde{\alpha}_{*}$ 并非是自然的，这就是说，它不与 $\operatorname{grad},\operatorname{div}$ 和 $\operatorname{curl}$ 交换，同样也不与 [[#31 Application to Vector and Scalar Fields]] 中的线性同构 $\alpha_{i},\beta_{j}$ 交换。