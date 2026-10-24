# 5A Invariant Subspaces

## Eigenvalues

回顾一下，我们称从向量空间到其自身的线性映射为一个算子。

对于算子 $T \in L(V)$，如果 $m\geq 2$ 且

$$
\begin{gather}
V=V_{1}\oplus \dots \oplus V_{m}
\end{gather}
$$

其中每个 $V_{k}$ 都是 $V$ 的非零子空间，则要理解 $T$ 在 $V$ 上的行为，我们只需研究 $T$ 在各 $V_{k}$ 上的限制 $T|_{V_{k}}$ 即可。由于 $V_{k}$ 的维度更低，$T|_{V_{k}}$ 的研究应当是更为简单的。

然而，我们面临一个问题：$T|_{V_{k}}$ 可能并不是 $V_{k}$ 上的算子，即，$T|_{V_{k}}$ 并不从 $V_{k}$ 映射到它自身。因此，我们需要限制 $V_{k}$ 的选取，使得 $T$ 将 $V_{k}$ 映射到它自身。

### Definition 5.1 invariant subspace 不变子空间

设 $T \in L(V)$，称 $V$ 的子空间 $U$ 在 $T$ 下不变，如果 $T(U)\subset U$。

于是 $U$ 在 $T$ 下不变如果 $T|_{U}$ 是 $U$ 上的算子。

### Example 5.2

如果 $T \in L(V)$，那么以下的子空间均在 $T$ 下不变：

- $\{ 0 \}$：因为 $T(0)=0$。
- $V$：根据 $T \in L(V)$ 知 $T(V)\subset V$。
- $\ker T$：如果 $u \in \ker T$，那么 $Tu=0 \in \ker T$。
- $\operatorname{range}T$：如果 $u \in \operatorname{range}T$，那么同样有 $Tu \in \operatorname{range}T$。

注意，以上四个子空间不一定是各不相同的。例如，对于可逆算子，有 $\ker T=\{ 0 \}$ 且 $\operatorname{range}T=V$。

一个向量空间是否一定有不同于 $\{ 0 \}$ 和 $V$ 的不变子空间？对于有限维空间，答案是肯定的：当 $V$ 为复向量空间时条件为 $\dim V>1$，当 $V$ 为实向量空间时条件为 $\dim V>2$。

我们考虑最简单的一维不变子空间，这就是那些由单个向量张成的空间

$$
\begin{gather}
U=\operatorname{span}(v)=\{ \lambda v: \lambda \in \mathbb{F} \}
\end{gather}
$$

如果 $U$ 在 $T \in L(V)$ 下不变，那么存在 $\lambda \in \mathbb{F}$ 使得

$$
\begin{gather}
Tv=\lambda v
\end{gather}
$$

反之，如果 $Tv=\lambda v$，那么 $\operatorname{span}(v)$ 就在算子 $T$ 下不变。这便是特征值的定义。

### Definition 5.3 eigenvalue 特征值，eigenvector 特征向量

设 $T \in L(V)$，称 $\lambda \in \mathbb{F}$ 是 $T$ 的一个特征值，如果存在 $v \in V$ 使得 $v\neq 0$ 且 $Tv=\lambda v$。我们称 $v$ 为对应于 $\lambda$ 的特征向量。

以上定义中我们要求特征向量 $v\neq 0$，因为对任意 $\lambda \in \mathbb{F}$ 都有 $T 0=\lambda 0$。

### Example 5.4

定义 $T \in L(\mathbb{F}^{2})$ 为 $T(w,z)=(-z,w)$，则：

(a) 如果 $\mathbb{F}=\mathbb{R}$，则 $T$ 是一个逆时针 $90^{\circ}$ 旋转映射。要使得 $v$ 成为 $T$ 的特征向量，我们必须使它经过 $T$ 的作用后与 $v$ 位于同一直线上，由于 $\mathbb{R}^{2}$ 上不存在这样的向量，因此我们得出结论：$T \in L(\mathbb{R}^{2})$ 没有特征向量，从而也没有特征值。

(b) 如果 $\mathbb{F}=\mathbb{C}$，我们可以找到 $T(w,z)=\lambda(w,z)$ 的非零解：方程 $(-z,w)=\lambda(w,z)$ 可以转化为

$$
\begin{gather}
-z=\lambda^{2}z \implies \lambda^{2}+1=0
\end{gather}
$$

其在 $\mathbb{C}$ 中的根为 $\lambda=\pm i$，从而 $T$ 的特征值为 $i$ 和 $-i$，分别对应的特征向量为 $(1,-i)$ 与 $(1,i)$。

### Theorem 5.5

设 $V$ 是有限维的，$T \in L(V)$，且 $\lambda \in \mathbb{F}$。如下四个命题等价：

1. $\lambda$ 是 $T$ 的一个特征值，
2. $T-\lambda I$ 不是单射，
3. $T-\lambda I$ 不是满射，
4. $T-\lambda I$ 不是可逆映射。

#### Proof

(2)(3)(4) 的等价性由 [[3 Linear Maps#Theorem 3.54]] 给出。(1)(2) 的等价性源于 $Tv=\lambda v$ 与 $(T-\lambda I)v=0$ 的等价性。

以下定理的证明中同样用到了以上方程的等价性。

### Theorem 5.6

设 $T \in L(V)$，则对应于 $T$ 是不同特征值的特征向量是线性无关的。

#### Proof

我们用反证法。假设存在一个最小的正整数 $m\geq 2$ 使得一组对应于 $T$ 的不同特征值 $\lambda_{1},\dots,\lambda_{m}$ 的特征向量 $v_{1},\dots,v_{m}$ 线性相关（由于特征向量不为零，因此单个特征向量必定线性无关），则存在不全为零（至少两个不为零）的标量 $a_{1},\dots,a_{m}$ 使得

$$
\begin{gather}
a_{1}v_{1}+\dots+a_{m}v_{m}=0
\end{gather}
$$

将 $T-\lambda_{m}I$ 作用于等式两边，则有

$$
\begin{gather}
a_{1}(\lambda_{1}-\lambda_{m})v_{1}+\dots+a_{m-1}(\lambda_{m-1}-\lambda_{m})v_{m-1}=0
\end{gather}
$$

由于特征值各不相同，故上式中的系数也是不全为零的，因而我们就有了一个长度为 $m-1$ 的线性相关向量组，与假设矛盾。

### Theorem 5.7

设 $V$ 是有限维向量空间，则 $V$ 上的算子至多有 $\dim V$ 个不同的特征值。

#### Proof

根据 [[#Theorem 5.6]]，不同的特征值个数等于 $V$ 中的一个线性无关组的长度，其必然小于等于 $\dim V$。

## Polynomials Applied to Operators

相比于两个向量空间之间的线性映射，从一个向量空间到其自身的算子有更为丰富的理论，因为算子可以重复应用到其自身，进而形成算子的多项式。

### Notation 5.8

设 $T \in L(V)$，$m$ 是一个正整数。

我们递归地定义 $T^{m}\in L(V)$ 为 $T^{m}=TT^{m-1}$，且 $T^{0}=I$。

如果 $T$ 是可逆的，那么我们定义 $T^{-m}=(T^{-1})^{m}$。

我们可以验证等式

$$
\begin{gather}
T^{m+n}=T^{m}T^{n}, \quad T^{mn}=(T^{m})^{n}
\end{gather}
$$

### Notation 5.9

设 $T \in L(V)$，$p \in \mathcal{P}(\mathbb{F})$ 定义为

$$
\begin{gather}
p(z)=a_{0}+a_{1}z+\dots+a_{m}z^{m}
\end{gather}
$$

则 $p(T)$ 是 $V$ 上的一个算子，定义为

$$
\begin{gather}
p(T)=a_{0}I+a_{1}T+\dots+a_{m}T^{m}
\end{gather}
$$

有时我们也将恒等算子 $I$ 省略，因为标量数乘 $a_{0}T$ 与算子乘法 $(a_{0}I)T$ 的结果是一致的，于是我们可以将 $a_{0}$ 同时作为一个标量与算子参与运算。

### Example 5.10

设 $D$ 是 $\mathcal{P}(\mathbb{R})$ 上的微分算子，多项式 $p(x)=7-3x+5x^{2}$，则 $p(D)$ 是 $\mathcal{P}(\mathbb{R})$ 上的算子 $7-3D+5D^{2}$，定义为

$$
\begin{gather}
p(D)q=7q-3q'+5q''
\end{gather}
$$

如果我们固定一个 $T \in L(V)$，那么从 $\mathcal{P}(\mathbb{F})$ 到 $L(V)$ 的映射 $p\mapsto p(T)$ 是线性的。此外，这一映射与 $\mathcal{P}(\mathbb{F})$ 上的多项式乘法也是相容的，下面我们将来证明这一点。

### Definition 5.11

如果 $p,q \in \mathcal{P}(\mathbb{F})$，我们定义它们的乘积 $pq \in \mathcal{P}(\mathbb{F})$ 为

$$
\begin{gather}
(pq)(z)=p(z)q(z)
\end{gather}
$$

### Theorem 5.12

设 $p,q\in \mathcal{P}(\mathbb{F})$，$T \in L(V)$，则

1. $(pq)(T)=p(T)q(T)$，
2. $p(T)q(T)=q(T)p(T)$。

#### Proof

(1) 设 $p(z)=\sum_{j=0}^{m}a_{j}z^{j},q(z)=\sum_{k=0}^{n}b_{k}z^{k}$，则

$$
\begin{gather}
(pq)(z)=\sum_{j=0}^{m} \sum_{k=0}^{n} a_{j}b_{k} z^{j+k}
\end{gather}
$$

从而

$$
\begin{align}
(pq)(T) &= \sum_{j=0}^{m} \sum_{k=0}^{n} a_{j}b_{k} T^{j+k} \\
&=\left( \sum_{j=0}^{m} a_{j}T^{j} \right)\left( \sum_{k=0}^{n} b_{k}T^{k} \right) \\
&=p(T)q(T)
\end{align}
$$

(2) 应用 (1) 两次，得到

$$
\begin{gather}
p(T)q(T)=(pq)(T)=(qp)(T)=q(T)p(T)
\end{gather}
$$

### Theorem 5.13

设 $T \in L(V)$ 且 $p \in \mathcal{P}(\mathbb{F})$，则 $\ker p(T)$ 和 $\operatorname{range}p(T)$ 在 $T$ 下不变。

#### Proof

这实际上是一个更广泛的定理的特例：如果 $S,T \in L(V)$ 交换，即 $ST=TS$，那么 $\ker S$ 和 $\operatorname{range}S$ 在 $T$ 下不变，反之亦然。$T$ 与 $p(T)$ 的交换性由 [[#Theorem 5.12]] 给出，其中我们取 $q(T)=T$。

设 $u \in \ker S$，则 $Su=0$，从而 $T(Su)=S(Tu)=0$，$Tu \in \ker S$，即 $\ker S$ 在 $T$ 下不变。

设 $w \in \operatorname{range}S$，则存在 $u \in V$ 使得 $w=Su$，从而 $Tw=T(Su)=S(Tu)$，$Tw \in \operatorname{range}S$，即 $\operatorname{range}S$ 在 $T$ 下不变。

# 5B The Minimal Polynomial

## Existence of Eigenvalues on Complex Vector Spaces

现在我们给出复向量空间上的一个核心结论。

### Theorem 5.14

有限维非零复向量空间上的任意算子都有特征值。

#### Proof

设 $V$ 是一个 $n$ 维复向量空间，$n>0$ 且 $T \in L(V)$。取 $v \in V$ 满足 $v\neq 0$，则

$$
\begin{gather}
v,Tv,T^{2}v,\dots,T^{n}v
\end{gather}
$$

作为一个长度 $n+1$ 的向量组在 $V$ 中线性相关，因此存在一个次数最低的非常值多项式 $p$ 使得

$$
\begin{gather}
p(T)v=0
\end{gather}
$$

根据代数基本定理，存在 $\lambda \in \mathbb{C}$ 使得 $p(\lambda)=0$，于是有

$$
\begin{gather}
p(z)=(z-\lambda)q(z)
\end{gather}
$$

其中 $\deg q<\deg p$，故 $q(T)v\neq 0$，从而

$$
\begin{gather}
p(T)v=(T-\lambda I)q(T)v=0 \implies (T-\lambda I)v=0
\end{gather}
$$

这就是说 $\lambda$ 是 $T$ 的一个特征值。

以上定理显示了复向量空间与实向量空间的区别：实向量空间上的算子可能没有实特征值，例如 $\mathbb{R}^{2}$ 上的旋转算子。此外，以上定理中的有限维条件也不能去掉，见下例。

### Example 5.15

定义 $T \in L(\mathcal{P}(\mathbb{C}))$ 为 $(Tp)(z)=zp(z)$，则如果 $p\neq 0$，那么 $Tp$ 的次数总是比 $p$ 大，从而不可能是 $p$ 的标量倍。这表明 $T$ 没有特征值。

由于 $\mathcal{P}(\mathbb{C})$ 是无限维的，因此这与 [[#Theorem 5.14]] 并不矛盾。

## Eigenvalues and the Minimal Polynomial

### Definition 5.16 monic polynomial 首一多项式

一个首一多项式是一个最高次项系数为 $1$ 的多项式。

### Theorem 5.17

设 $V$ 是有限维的，$T \in L(V)$，则存在唯一的首一多项式 $p \in \mathcal{P}(\mathbb{F})$ 使得 $p$ 的次数最低，且 $p(T)=0$，并满足 $\deg p\leq \dim V$。

我们称多项式 $p$ 为算子 $T$ 的极小多项式（minimal polynomial）。

#### Proof

如果 $\dim V=0$，那么 $V$ 上的算子只有零算子，取 $p=1$ 即可。

下面我们对 $\dim V$ 进行归纳。假设 $\dim V>0$ 且结论对低维的空间都成立。取 $u\neq 0$，则 $u,Tu,\dots,T^{\dim V}u$ 具有长度 $\dim V+1$，故线性相关。根据线性相关引理，存在最小的整数 $m\leq \dim V$ 使得 $T^{m}u$ 是向量 $u,Tu,\dots T^{m-1}u$ 的线性组合，即

$$
\begin{gather}
c_{0}u+c_{1}Tu+\dots+c_{m-1}T^{m-1}u+T^{m}u=0
\end{gather}
$$

定义首一多项式 $q \in \mathcal{P}(\mathbb{F})$ 为

$$
\begin{gather}
q(z)=c_{0}+c_{1}z+\dots+c_{m-1}z^{m-1}+z^{m}
\end{gather}
$$

则 $q(T)u=0$。

设 $k$ 是非负整数，则

$$
\begin{gather}
q(T)(T^{k}u)=T^{k}(q(T)u)=T^{k}(0)=0
\end{gather}
$$

根据 $m$ 的最小性，$u,Tu,\dots,T^{m-1}u$ 线性无关，因此上式表明 $\dim\ker q(T)\geq m$，从而由秩-零化度定理得

$$
\begin{gather}
\dim \operatorname{range}q(T)=\dim V-\dim \ker q(T)\leq \dim V-m<\dim V
\end{gather}
$$

由于 $\operatorname{range}q(T)$ 在 $T$ 下不变，我们可以对算子 $T|_{\operatorname{range}q(T)}$ 应用归纳假设，得到首一多项式 $s \in \mathcal{P}(\mathbb{F})$ 满足

$$
\begin{gather}
\deg s\leq \dim V-m, \quad s(T|_{\operatorname{range}q(T)})=0
\end{gather}
$$

因此对任意 $v \in V$ 有

$$
\begin{gather}
(s q)(T)v=s(T)(q(T)v)=0
\end{gather}
$$

从而 $s q$ 是一个首一多项式，满足 $\deg s q\leq \dim V$ 且 $(s q)(T)=0$。

以上我们证明了满足 $\deg p\leq \dim V$ 且 $p(T)=0$ 的首一多项式的存在性，因而存在次数最低的首一多项式，满足上述条件。

现在证明唯一性。设 $p,r$ 是相同次数的首一多项式，满足所求的条件，则 $(p-r)(T)=0$ 且 $\deg(p-r)<\deg p$。如果 $p-r\neq 0$，那么我们可以将 $p-r$ 除以其最高次项系数得到一个首一多项式，这与 $p$ 的最低次性质矛盾。因此 $p-r=0$，这就证明了唯一性。

以上定理是一个存在性证明，它没有说明如何求出一个算子的极小多项式。在实际应用中，我们需要找到最小的整数 $m$，使得以 $c_{0},\dots,c_{m-1}$ 为未知数的方程

$$
\begin{gather}
c_{0}+c_{1}T+\dots+c_{m-1}T^{m-1}=-T^{m}
\end{gather}
$$

有解。如果我们选取 $V$ 的一个基，并将 $T$ 替换为它的矩阵，那么我们将得到一个有 $m$ 个未知量和 $(\dim V)^{2}$ 个方程的线性方程组，从而我们可以对 $m=1,2,\dots$ 使用 Gauss-Jordan 消元法来判断解的存在性或者求出方程的解。根据 [[#Theorem 5.17]]，至多在 $\dim V$ 次尝试后我们必然能够得到一个解，此时 $T$ 的极小多项式就是 $c_{0}+c_{1}z+\dots+c_{m-1}z^{m-1}+z^{m}$。

在大多数时候，我们可以取 $v\neq 0$ 并考虑方程

$$
\begin{gather}
c_{0}v+c_{1}Tv+\dots+c_{\dim V-1}T^{\dim V-1}v=-T^{\dim V}v
\end{gather}
$$

转换为矩阵形式，我们将得到一个 $\dim V$ 个未知数与方程的线性方程组，如果它有唯一解（对一个随机矩阵大概率成立），那么 $T$ 的极小多项式就是 $c_{0}+c_{1}z+\dots+c_{\dim V-1}z^{\dim V-1}+z^{\dim V}$。

### Example 5.18

设 $T \in L(\mathbb{F}^{5})$，其在标准基下的矩阵为

$$
\begin{gather}
\mathcal{M}(T)=\begin{pmatrix}
0 & 0 & 0 & 0 & -3 \\
1 & 0 & 0 & 0 & 6 \\
0 & 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 & 0
\end{pmatrix}
\end{gather}
$$

则我们有

$$
\begin{gather}
Te_{1}=e_{2}, \quad T^{2}e_{1}=Te_{2}=e_{3}, \quad T^{3}e_{1}=Te_{3}=e_{4} \\
T^{4}e_{1}=Te_{4}=e_{5}, \quad T^{5}e_{1}=Te_{5}=-3e_{1}+6e_{2}
\end{gather}
$$

因此 $3e_{1}-6Te_{1}=-T^{5}e_{1}$。显然 $e_{1},Te_{1},T^{2}e_{1},T^{3}e_{1},T^{4}e_{1}$ 线性无关，因此不存在其它线性组合能够给出 $-T^{5}e_{1}$，从而 $T$ 的极小多项式为 $3-6z+z^{5}$。

更一般地，设 $T \in L(\mathbb{F}^{n})$ 在标准基下的矩阵为

$$
\begin{gather}
\mathcal{M}(T)=\begin{pmatrix}
0 &  &  & &   & -a_{0} \\
1 & 0 &  & &   & -a_{1} \\
 & 1 & \ddots & &   & -a_{2} \\
 &  & \ddots &  &  & \vdots \\
 &  &  &  & 0 & -a_{n-2} \\
 &  &  &  & 1 & -a_{n-1}
\end{pmatrix}
\end{gather}
$$

则 $T$ 的极小多项式为

$$
\begin{gather}
a_{0}+a_{1}z+\dots+a_{n-1}z^{n-1}+z^{n}
\end{gather}
$$

上面的矩阵称为该多项式的友矩阵（companion matrix）。本例表明，每个首一多项式都是某个算子的极小多项式。

### Theorem 5.19

设 $V$ 是有限维的，$T \in L(V)$。

(a) $T$ 的极小多项式在 $\mathbb{F}$ 中的零点是 $T$ 的特征值，反之亦然。

(b) 如果 $V$ 是复向量空间，则 $T$ 的极小多项式具有形式

$$
\begin{gather}
(z-\lambda_{1})\cdots (z-\lambda_{m})
\end{gather}
$$

其中 $\lambda_{1},\dots,\lambda_{m}$ 都是 $T$ 的特征值，可能包含重复。

#### Proof

设 $p$ 为 $T$ 的极小多项式。

(a) 首先设 $\lambda$ 是 $p$ 的零点，我们要证明 $\lambda$ 是 $T$ 的特征值。$p$ 可以写成

$$
\begin{gather}
p(z)=(z-\lambda)q(z)
\end{gather}
$$

其中 $q \in \mathcal{P}(\mathbb{F})$ 是一个首一多项式。由于 $p(T)=0$，故

$$
\begin{gather}
p(T)v=(T-\lambda I)q(T)v=0 \quad (v \in V)
\end{gather}
$$

由于 $\deg q<\deg p$，故由极小性知必然存在 $v \in V$ 使得 $q(T)v\neq 0$，即证 $\lambda$ 是特征值。

现设 $\lambda$ 是 $T$ 的特征值，我们要证 $\lambda$ 是 $p$ 的零点。设 $v\neq 0$ 为 $\lambda$ 对应的特征向量，则 $Tv=\lambda v$。对等式两边重复应用 $T$ 即得 $T^{k}v=\lambda^{k}v$，从而

$$
\begin{gather}
p(T)v=p(\lambda)v=0
\end{gather}
$$

即 $p(\lambda)=0$，这就完成了证明。

(b) 由 (a) 以及 [[4 Polynomials#Theorem 4.6]] 给出。

以上定理表明，求解一个算子的特征值与求解一个多项式方程的解在某种意义上是等价的。由于每个首一多项式都是某个算子的极小多项式，任何能够精确求解特征值的通用方法都能够用来求解多项式的零点，而后者，根据 Galois 理论的相关结论，是不可能的。因此我们可知：不存在能够精确求解算子特征值的通用方法。然而，存在高效的数值方法，可用于得到算子特征值的非常精确的近似值。

### Theorem 5.20

设 $V$ 是有限维的，$T \in L(V)$，$q \in \mathcal{P}(\mathbb{F})$。则 $q(T)=0$ 当且仅当 $q$ 是 $T$ 的极小多项式的多项式倍。

#### Proof

设 $p$ 表示 $T$ 的极小多项式。

首先设 $q(T)=0$。根据多项式的带余除法定理，存在 $s,r \in \mathcal{P}(\mathbb{F})$ 使得

$$
\begin{gather}
q=s p+r, \quad \deg r<\deg p
\end{gather}
$$

我们有

$$
\begin{gather}
q(T)=s(T)p(T)+r(T)=r(T)=0
\end{gather}
$$

因此如果 $r\neq 0$，那么除以 $r$ 的最高次项系数我们将得到一个首一多项式，与 $p$ 的极小性矛盾。因此 $r=0$，即 $p$ 整除 $q$。

反之，如果 $q=s p$，则我们就有

$$
\begin{gather}
q(T)=s(T)p(T)=0
\end{gather}
$$

这就完成了证明。

### Corollary 5.21

设 $V$ 是有限维的，$T \in L(V)$，且 $U$ 是 $V$ 的子空间，在 $T$ 下不变。则 $T$ 的极小多项式是限制算子 $T|_{U}$ 的极小多项式的多项式倍。

#### Proof

设 $p$ 是 $T$ 的极小多项式，则对任意 $u \in U$ 有

$$
\begin{gather}
p(T)u=0
\end{gather}
$$

因此 $p(T|_{U})=0$。对 $T|_{U}$ 应用 [[#Theorem 5.20]] 即证。

### Theorem 5.22

设 $V$ 是有限维的，$T \in L(V)$，则 $T$ 不可逆当且仅当 $T$ 的极小多项式的常数项为 $0$。

#### Proof

设 $p$ 是 $T$ 的极小多项式，则我们有等价链：

$T$ 不可逆当且仅当 $0$ 是 $T$ 的特征值，当且仅当 $0$ 是 $p$ 的零点，当且仅当 $p$ 的常数项为 $0$。

其中第一个等价由 [[#Theorem 5.5]] 给出。

## Eigenvalues on Odd-Dimensional Real Vector Spaces

### Lemma 5.23

设 $\mathbb{F}=\mathbb{R}$ 且 $V$ 是有限维的。如果 $T \in L(V)$ 且 $b,c \in \mathbb{R}$ 满足 $b^{2}<4c$，则 $\dim \ker(T^{2}+bT+c)$ 是一个偶数。

#### Proof

由于 $\ker(T^{2}+bT+c)$ 在 $T$ 下不变，通过将 $V$ 替换为 $\ker(T^{2}+bT+c)$，将 $T$ 替换为 $T|_{\ker(T^{2}+bT+c)}$，我们可以假设 $T^{2}+bT+c=0$，于是我们只需证明 $\dim V$ 是偶数。

假设有 $v \in V$ 使得 $Tv=\lambda v$，则

$$
\begin{gather}
(T^{2}+bT+c)v=(\lambda^{2}+b\lambda+c)v=0
\end{gather}
$$

由于 $b^{2}<4c$，故 $\lambda^{2}+b\lambda+c$ 对任意 $\lambda \in \mathbb{R}$ 都是正数，从而 $v=0$，$T$ 没有特征向量。

设 $U$ 是 $V$ 的子空间，且是在 $T$ 下不变且维度是偶数的子空间中维度最大的。如果 $U=V$，我们就完成了证明；否则，我们取 $w \not\in U$。

取 $W=\operatorname{span}(w,Tw)$，则 $W$ 在 $T$ 下不变，因为 $T(Tw)=-bTw-cw$。此外，$\dim W=2$，因为否则 $w$ 将是 $T$ 的一个特征向量。从而

$$
\begin{gather}
\dim(U+W)=\dim U+\dim W-\dim (U\cap W)=\dim U+2
\end{gather}
$$

其中我们有 $U\cap W=\{ 0 \}$，因为否则 $U\cap W$ 将是在 $T$ 下不变的一维不变子空间，这是不可能的，因为 $T$ 没有特征向量。

由于 $U+W$ 在 $T$ 下不变，则以上等式表明存在 $V$ 的偶数维子空间，其在 $T$ 下不变并且维度大于 $\dim U$，这与 $U$ 的极大性矛盾。因此 $U=V$，故 $V$ 是偶数维的。

### Theorem 5.24

奇数维实向量空间上的任意算子都有特征值。

#### Proof

设 $n=\dim V$ 为奇数。任取 $T \in L(V)$，我们将对 $n$ 进行归纳来证明 $T$ 有特征值。$\dim V=1$ 的情况是平凡的，其中每个非零向量都是 $T$ 的特征向量。

现在假设 $n\geq 3$ 且结论对所有低维的奇数维空间成立。设 $p$ 为 $T$ 的极小多项式，如果 $p$ 有因子 $x-\lambda$，那么 $\lambda$ 就是 $T$ 的特征值。因此我们可以假设存在 $b,c$ 满足 $b^{2}<4c$ 且 $p$ 包含因子 $x^{2}+bx+c$。

于是有首一多项式 $q$ 使得 $p(x)=q(x)(x^{2}+bx+c)$，从而

$$
\begin{gather}
p(T)=q(T)(T^{2}+bT+c)=0
\end{gather}
$$

这表明 $q(T)$ 在 $\operatorname{range}(T^{2}+bT+c)$ 上的限制等于零算子。由于 $\deg q<\deg p$，故 $q(T)\neq 0$，从而我们可知 $\operatorname{range}(T^{2}+bT+c)\neq V$。

秩-零化度定理表明

$$
\begin{gather}
\dim V=\dim \ker(T^{2}+bT+c)+\dim \operatorname{range}(T^{2}+bT+c)
\end{gather}
$$

$\dim V$ 是奇数，$\dim \ker(T^{2}+bT+c)$ 是偶数（[[#Lemma 5.23]]），故 $\operatorname{range}(T^{2}+bT+c)$ 是奇数维空间，并且其维数小于 $\dim V$。应用归纳假设可知 $T|_{\operatorname{range}(T^{2}+bT+c)}$ 有特征值，因而 $T$ 有特征值。

当我们引入算子的行列式以及特征多项式后，我们将给出以上定理的一个更为简单的证明。它展示了以上定理成立的根本原因：奇数次的实系数多项式在实数上有零点。

# 5C Upper-Triangular Matrices

在 [[3 Linear Maps]] 中我们定义了一个线性映射在两个基下的矩阵。对于 $V$ 上的算子，我们通常将定义域和陪域的基取为同一个，从而算子的矩阵的大小为 $n\times n$ 的，其中 $n=\dim V$。这样的矩阵也称为 $n$ 阶方阵。

线性代数的一个核心目标是证明，对于满足特定性质的算子 $T$，存在一个 $V$ 上的基，使得 $T$ 在这个基下的矩阵尽可能地简单。本节我们来研究其中一种情况，即 $T$ 的矩阵是上三角的情况。

### Definition 5.25 diagonal 对角线

一个 $n$ 阶方阵 $A=(A_{i,j})_{1\leq i,j\leq n}$ 的对角线元素是 $A_{1,1},A_{2,2},\dots,A_{n,n}$。

### Definition 5.26 upper-triangular matrix 上三角矩阵

一个方阵称为是上三角的，如果它的对角线下方（不含对角线）的元素均为零。

这就是说，一个上三角矩阵具有形式

$$
\begin{gather}
\begin{pmatrix}
\lambda_{1} &  & \ast \\
 & \ddots &  \\
0 &  & \lambda_{n}
\end{pmatrix}
\end{gather}
$$

类似地我们也可以定义下三角矩阵。

### Theorem 5.27

设 $T \in L(V)$ 且 $v_{1},\dots,v_{n}$ 是 $V$ 的基，则以下命题等价：

1. $T$ 关于基 $v_{1},\dots,v_{n}$ 的矩阵是上三角的。
2. 对任意 $1\leq k\leq n$，$\operatorname{span}(v_{1},\dots,v_{k})$ 在 $T$ 下不变。
3. 对任意 $1\leq k\leq n$ 有 $Tv_{k}\in \operatorname{span}(v_{1},\dots,v_{k})$。

#### Proof

首先设 (1) 成立，则根据矩阵的定义我们立即得到

$$
\begin{gather}
Tv_{j} \in \operatorname{span}(v_{1},\dots,v_{j})
\end{gather}
$$

固定 $k$，则当 $j\leq k$ 时有 $\operatorname{span}(v_{1},\dots,v_{j})\subset \operatorname{span}(v_{1},\dots,v_{k})$，从而对任意 $1\leq j\leq k$ 有 $Tv_{j}\in \operatorname{span}(v_{1},\dots,v_{k})$，这表明 (2) 成立。

如果 (2) 成立，那么根据 $v_{k}\in \operatorname{span}(v_{1},\dots,v_{k})$ 显然有 $Tv_{k}\in \operatorname{span}(v_{1},\dots,v_{k})$。

如果 (3) 成立，根据矩阵的定义，$\mathcal{M}(T)$ 的第 $k$ 列是将 $Tv_{k}$ 写成 $v_{1},\dots,v_{n}$ 线性组合的系数，而 (3) 表明线性组合中我们只需用到 $v_{1},\dots,v_{k}$。因此，$\mathcal{M}(T)$ 的第 $k$ 列仅有前 $k$ 行的元素可能不为零，即 $\mathcal{M}(T)$ 是上三角的。

### Theorem 5.28

设 $T \in L(V)$，$V$ 有一个基使得 $T$ 在该基下的矩阵是上三角的，其对角线元素为 $\lambda_{1},\dots,\lambda_{n}$，则

$$
\begin{gather}
(T-\lambda_{1}I)\cdots (T-\lambda_{n}I)=0
\end{gather}
$$

#### Proof

设 $T$ 在基 $v_{1},\dots,v_{n}$ 下的矩阵是上三角的，其对角线元素为 $\lambda_{1},\dots,\lambda_{n}$。则 $Tv_{1}=\lambda_{1}v_{1}$，即 $(T-\lambda_{1}I)v_{1}=0$，从而

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v_{1}=0 \quad (1\leq m\leq n)
\end{gather}
$$

由于 $(T-\lambda_{2}I)v_{2} \in \operatorname{span}(v_{1})$，故 $(T-\lambda_{1}I)(T-\lambda_{2}I)v_{2}=0$，从而

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v_{2}=0 \quad (2\leq m\leq n)
\end{gather}
$$

以此类推，我们就有

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{n}I)v_{k}=0 \quad (1\leq k\leq n)
\end{gather}
$$

又由于 $v_{1},\dots,v_{n}$ 是基，因此 $(T-\lambda_{1}I)\cdots(T-\lambda_{n}I)=0$。

### Theorem 5.29

设 $T \in L(V)$ 在 $V$ 的某个基下有上三角矩阵，则 $T$ 的特征值恰是 $T$ 的上三角矩阵的对角线元素。

#### Proof

设 $T$ 在基 $v_{1},\dots,v_{n}$ 下有上三角矩阵

$$
\begin{gather}
\mathcal{M}(T)=\begin{pmatrix}
\lambda_{1} &  & \ast \\
 & \ddots &  \\
0 &  & \lambda_{n}
\end{pmatrix}
\end{gather}
$$

则 $Tv_{1}=\lambda_{1}v_{1}$，即 $\lambda_{1}$ 是 $T$ 的特征值。

设 $2\leq k\leq n$，则 $T-\lambda_{k}I$ 将 $\operatorname{span}(v_{1},\dots,v_{k})$ 映射到 $\operatorname{span}(v_{1},\dots,v_{k-1})$，又由于

$$
\begin{gather}
\dim \operatorname{span}(v_{1},\dots,v_{k})=k, \quad \dim \operatorname{span}(v_{1},\dots,v_{k-1})=k-1
\end{gather}
$$

$T-\lambda_{k}I$ 在 $\operatorname{span}(v_{1},\dots,v_{k})$ 上的限制映射作为从高维到低维空间的映射不是单射（[[3 Linear Maps#Theorem 3.21]]），因此 $\lambda_{k}$ 是 $T$ 的特征值。因此我们证明了对角线上的元素都是 $T$ 的特征值。

下面我们要证 $T$ 没有其它特征值。定义 $q(z)=(z-\lambda_{1})\cdots(z-\lambda_{n})$，则 [[#Theorem 5.28]] 表明 $q(T)=0$，从而 $T$ 的极小多项式整除 $q$。这表明极小多项式的零点集（特征值）包含于 $q$ 的零点集（对角线元素），这就完成了证明。

下面的定理是算子可上三角化的一个充分必要条件。

### Theorem 5.30

设 $V$ 是有限维的，$T \in L(V)$。则 $T$ 在 $V$ 的某个基下有上三角矩阵当且仅当 $T$ 的极小多项式具有形式 $(z-\lambda_{1})\cdots(z-\lambda_{m})$。

#### Proof

首先假设 $T$ 在某个基下有上三角矩阵，其对角线元素为 $\alpha_{1},\dots,\alpha_{n}$，则多项式

$$
\begin{gather}
q(z)=(z-\alpha_{1})\cdots(z-\alpha_{n})
\end{gather}
$$

满足 $q(T)=0$，从而它是极小多项式的多项式倍。这表明 $T$ 的极小多项式具有形式 $(z-\lambda_{1})\cdots(z-\lambda_{m})$，其中 $\{ \lambda_{1},\dots,\lambda_{m} \}\subset \{ \alpha_{1},\dots,\alpha_{n} \}$。

要证明反向的包含，我们对 $m$ 进行归纳。当 $m=1$ 时，$T$ 的极小多项式为 $z-\lambda_{1}$，从而 $T=\lambda_{1}I$，其在任意基下都是上三角矩阵。

现在假设 $m>1$ 且结论对更小的整数成立。取

$$
\begin{gather}
U=\operatorname{range}(T-\lambda_{m}I)
\end{gather}
$$

则 $U$ 在 $T$ 下不变，故 $T|_{U}$ 是 $U$ 上的算子。

设 $u \in U$，则存在 $v$ 使得 $u=(T-\lambda_{m}I)v$，从而

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{m-1}I)u=(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v=0
\end{gather}
$$

因此 $(z-\lambda_{1})\cdots(z-\lambda_{m-1})$ 是算子 $T|_{U}$ 的一个零化多项式，从而 $T|_{U}$ 的极小多项式可以分解为至多 $m-1$ 个一次因子 $z-\lambda_{k}$ 的乘积。

应用归纳假设，可知存在 $U$ 的基 $u_{1},\dots,u_{M}$ 使得 $T|_{U}$ 有上三角矩阵，于是

$$
\begin{gather}
Tu_{k}\in \operatorname{span}(u_{1},\dots,u_{k})
\end{gather}
$$

将 $u_{1},\dots,u_{M}$ 扩张为 $V$ 的基 $u_{1},\dots,u_{M},v_{1},\dots,v_{N}$，则

$$
\begin{gather}
Tv_{k}=(T-\lambda_{m}I)v_{k}+\lambda_{m}v_{k}
\end{gather}
$$

由于 $(T-\lambda_{m}I)v_{k}\in U$，故

$$
\begin{gather}
Tv_{k}\in \operatorname{span}(u_{1},\dots,u_{M},v_{1},\dots,v_{k})
\end{gather}
$$

根据 [[#Theorem 5.27]] 即证 $T$ 在 $u_{1},\dots,u_{M},v_{1},\dots,v_{N}$ 下的基是上三角的，这就完成了证明。

### Corollary 5.31

设 $V$ 是一个有限维复向量空间，则任意 $T \in L(V)$ 都可上三角化。

在后续的章节中，我们将极大地改进以上定理。最终我们将证明：有限维复向量空间上的算子都有 Jordan 标准型。

### Example 5.32

我们用一个例子来说明 [[#Theorem 5.30]] 中的“分解为一次因子”是什么意思。定义 $T \in L(\mathbb{F}^{4})$ 为

$$
\begin{gather}
T(z_{1},z_{2},z_{3},z_{4})=(-z_{2},z_{1},2z_{1}+3z_{3},z_{3}+3z_{4})
\end{gather}
$$

则在标准基下 $T$ 的矩阵为

$$
\begin{gather}
\begin{pmatrix}
0 & -1 & 0 & 0 \\
1 & 0 & 0 & 0 \\
2 & 0 & 3 & 0 \\
0 & 0 & 1 & 3
\end{pmatrix}
\end{gather}
$$

可以验证它的极小多项式为

$$
\begin{gather}
p(z)=z^4-6 z^3+10 z^2-6 z+9
\end{gather}
$$

在 $\mathbb{F}=\mathbb{R}$ 上它有分解式

$$
\begin{gather}
(z^{2}+1)(z-3)(z-3)
\end{gather}
$$

由于它不能继续分解为一次因子的乘积，因此 [[#Theorem 5.30]] 表明 $\mathbb{R}^{4}$ 上的算子 $T$ 不能上三角化。

现在考虑 $\mathbb{F}=\mathbb{C}$，则 $p$ 可以分解为

$$
\begin{gather}
(z-i)(z+i)(z-3)(z-3)
\end{gather}
$$

于是 [[#Theorem 5.30]] 保证了必然存在 $\mathbb{C}^{4}$ 上的基使得 $T$ 能够上三角化。可以验证，在基

$$
\begin{gather}
(4-3i,-3-4i,-3+i,1),(4+3i,-3+4i,-3-i,1), (0,0,0,1),(0,0,1,0)
\end{gather}
$$

下 $T$ 有上三角矩阵

$$
\begin{gather}
\begin{pmatrix}
i & 0 & 0 & 0 \\
0 & -i & 0 & 0 \\
0 & 0 & 3 & 1 \\
0 & 0 & 0 & 3
\end{pmatrix}
\end{gather}
$$

事实上，以上矩阵也是一个 Jordan 型。

### Remark 5.33

需注意的是，本节我们所说的“上三角化”指的是算子在某个基下的矩阵，换言之，相似变换。另一种对矩阵上三角化的方法是使用 Gaussian 消元法将矩阵化为行阶梯型，在方阵的情况下行阶梯型就退化为了上三角矩阵。这两种上三角化的方法是不同的，并且两种方法得到的上三角矩阵没有任何联系。

# 5D Diagonalizable Operators

## Diagonal Matrices

### Definition 5.34 diagonal matrix 对角矩阵

一个对角矩阵是一个除了对角线外所有元素均为零的方阵。

显然对角矩阵也是上三角矩阵，因此对角线上的元素就是该算子的特征值。

### Definition 5.35 diagonalizable 可对角化的

$V$ 上的算子称为是可对角化的，如果它在 $V$ 的某个基下的矩阵是对角矩阵。

### Definition 5.36 eigenspace 特征空间

设 $T \in L(V)$ 且 $\lambda \in \mathbb{F}$。定义 $T$ 关于 $\lambda$ 的特征空间为

$$
\begin{gather}
E(\lambda,T)=\ker(T-\lambda I)=\{ v \in V : Tv=\lambda v \}
\end{gather}
$$

因此 $\lambda$ 是 $T$ 的特征值当且仅当 $E(\lambda,T)\neq \{ 0 \}$，此时 $E(\lambda,T)$ 包含了所有 $T$ 的对应于 $\lambda$ 的特征向量。如果 $\lambda$ 是 $T$ 的特征值，那么 $T$ 在 $E(\lambda,T)$ 上的限制就是数乘 $\lambda$ 的算子 $v\mapsto\lambda v$。

### Theorem 5.37

设 $T \in L(V)$ 且 $\lambda_{1},\dots,\lambda_{m}$ 是 $T$ 的不同特征值，则

$$
\begin{gather}
E(\lambda_{1},T)+\dots+E(\lambda_{m},T)
\end{gather}
$$

是一个直和。如果进一步有 $V$ 是有限维的，那么

$$
\begin{gather}
\dim E(\lambda_{1},T)+\dots+\dim E(\lambda_{m},T)\leq \dim V
\end{gather}
$$

#### Proof

设

$$
\begin{gather}
v_{1}+\dots+v_{m}=0
\end{gather}
$$

其中 $v_{k}\in E(\lambda_{k},T)$，由于对应于不同特征值的特征向量线性无关（[[#Theorem 5.6]]），因此上式中每个 $v_{k}=0$，即证 $E(\lambda_{1},T)+\dots+E(\lambda_{m},T)$ 是一个直和。

现在假设 $V$ 是有限维的，则

$$
\begin{align}
\dim E(\lambda_{1},T)+\dots+\dim E(\lambda_{m},T) &= \dim(E(\lambda_{1},T)\oplus \dots \oplus E(\lambda_{m},T)) \\
&\leq \dim V
\end{align}
$$

这就完成了证明。

下面我们给出可对角化的充分必要条件。

### Theorem 5.38

设 $V$ 是有限维的，$T \in L(V)$，且 $\lambda_{1},\dots,\lambda_{m}$ 是 $T$ 的不同特征值，则以下命题等价：

1. $T$ 可对角化。
2. $V$ 有一个由 $T$ 的特征向量构成的基。
3. $V=E(\lambda_{1},T)\oplus\dots \oplus E(\lambda_{m},T)$。
4. $\dim V=\dim E(\lambda_{1},T)+\dots+\dim E(\lambda_{m},T)$。

#### Proof

一个算子 $T \in L(V)$ 关于基 $v_{1},\dots,v_{n}$ 有对角矩阵

$$
\begin{gather}
\begin{pmatrix}
\lambda_{1} &  & 0 \\
 & \ddots &  \\
0 &  & \lambda_{n}
\end{pmatrix}
\end{gather}
$$

当且仅当对任意 $k$ 有 $Tv_{k}=\lambda_{k}v_{k}$，从而我们有 (1) 等价于 (2)。

现在假设 (2) 成立，则任意 $v \in V$ 都是 $T$ 的特征向量的线性组合，因此

$$
\begin{gather}
V=E(\lambda_{1},T)+\dots+E(\lambda_{m},T)
\end{gather}
$$

[[#Theorem 5.37]] 表明上式是一个直和，因此 (3) 成立。

(4) 是 (3) 的直接推论。

假设 (4) 成立，则

$$
\begin{gather}
\dim V=\dim E(\lambda_{1},T)+\dots+\dim E(\lambda_{m},T)
\end{gather}
$$

为每个 $E(\lambda_{k},T)$ 选取一个基，组成 $V$ 中的一个长度为 $\dim V$ 的向量组 $v_{1},\dots,v_{n}$，我们要证它是线性无关的。设

$$
\begin{gather}
a_{1}v_{1}+\dots+a_{n}v_{n}=0
\end{gather}
$$

将各项关于其所在的空间 $E(\lambda_{k},T)$ 归类，我们可将上式写成

$$
\begin{gather}
u_{1}+\dots+u_{m}=0
\end{gather}
$$

其中 $u_{k} \in E(\lambda_{k},T)$。由于对应于不同特征值的特征向量线性无关，故每个 $u_{k}=0$。又由于 $u_{k}$ 是各 $a_{j}v_{j}$ 项使得 $v_{j}\in E(\lambda_{k},T)$ 的和，且各 $v_{j}$ 是 $E(\lambda_{k},T)$ 的基，因此每个 $a_{j}=0$，即证 (2)。这就完成了证明。

我们知道，每个有限维复向量空间上的算子都有特征值。然而，并非每个有限维复向量空间上的算子都有足够的线性无关的特征向量以对角化，如下例所示。

### Example 5.39

定义 $T \in L(\mathbb{F}^{3})$ 为 $T(a,b,c)=(b,c,0)$，其在标准基下的矩阵为

$$
\begin{gather}
\begin{pmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
0 & 0 & 0
\end{pmatrix}
\end{gather}
$$

可以验证，$0$ 是 $T$ 的唯一特征值，并且

$$
\begin{gather}
E(0,T)=\{ (a,0,0):a \in \mathbb{F} \}
\end{gather}
$$

因此 [[#Theorem 5.38]] 表明 $T$ 不可对角化，无论 $\mathbb{F}=\mathbb{R}$ 还是 $\mathbb{F}=\mathbb{C}$。

### Theorem 5.40

设 $V$ 是有限维的且 $T \in L(V)$ 有 $\dim V$ 个不同的特征值，则 $T$ 是可对角化的。

#### Proof

设 $T$ 的不同特征值为 $\lambda_{1},\dots,\lambda_{\dim V}$，其对应的特征向量为 $v_{1},\dots,v_{\dim V}$。由于对应于不同特征值的特征向量线性无关，因此 $v_{1},\dots,v_{\dim V}$ 线性无关，从而是 $V$ 的一个基。根据 [[#Theorem 5.38]] 即证。

### Example 5.41

在本例中我们将展示如何利用相似对角化来计算算子的指数。定义 $T \in L(\mathbb{F}^{3})$ 为 $T(x,y,z)=(2x+y,5y+3z,8z)$，其在标准基下的矩阵为

$$
\begin{gather}
\begin{pmatrix}
2 & 1 & 0 \\
0 & 5 & 3 \\
0 & 0 & 8
\end{pmatrix}
\end{gather}
$$

因此 $T$ 的特征值为 $2,5,8$，从而 $T$ 可对角化。

分别对 $\lambda=2,5,8$ 解方程

$$
\begin{gather}
T(x,y,z)=\lambda(x,y,z)
\end{gather}
$$

得到三个线性无关的特征向量 $(1,0,0),(1,3,0),(1,6,6)$。在这一特征基下 $T$ 有对角矩阵

$$
\begin{gather}
\begin{pmatrix}
2 & 0 & 0 \\
0 & 5 & 0 \\
0 & 0 & 8
\end{pmatrix}
\end{gather}
$$

假设我们需要计算 $T^{n}(0,0,1)$，我们首先将其写成特征向量的线性组合：

$$
\begin{gather}
(0,0,1)=\frac{1}{6}(1,0,0)-\frac{1}{3}(1,3,0)+\frac{1}{6}(1,6,6)
\end{gather}
$$

然后在等式两边应用 $T^{n}$：

$$
\begin{align}
T^{n}(0,0,1) &= \frac{1}{6} T^{n}(1,0,0)-\frac{1}{3}T^{n}(1,3,0)+\frac{1}{6}T^{n}(1,6,6) \\
&=\frac{1}{6}2^{n}(1,0,0)-\frac{1}{3}5^{n}(1,3,0)+\frac{1}{6}8^{n}(1,6,6) \\
&=\frac{1}{6}(2^{n}-2\cdot 5^{n}+8^{n},6\cdot 8^{n}-6\cdot 5^{n},6\cdot 8^{n})
\end{align}
$$

### Theorem 5.42

设 $V$ 是有限维的且 $T \in L(V)$。则 $T$ 是可对角化的当且仅当 $T$ 的极小多项式具有形式 $(z-\lambda_{1})\cdots(z-\lambda_{m})$，其中 $\lambda_{1},\dots,\lambda_{m}$ 各不相同。

注意它与可上三角化条件（[[#Theorem 5.30]]）的不同，对于后者我们允许一次因子 $z-\lambda_{k}$ 的重复出现。

#### Proof

假设 $T$ 可对角化，则存在 $V$ 的一个由 $T$ 的特征向量构成的基 $v_{1},\dots,v_{n}$。设 $\lambda_{1},\dots,\lambda_{m}$ 是 $T$ 的不同特征值，则对任意 $v_{j}$，存在一个 $\lambda_{k}$ 使得 $(T-\lambda_{k}I)v_{j}=0$，于是

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v_{j}=0
\end{gather}
$$

从而 $T$ 的极小多项式为 $(z-\lambda_{1})\cdots(z-\lambda_{m})$。

反之，假设 $T$ 的极小多项式为 $(z-\lambda_{1})\cdots(z-\lambda_{m})$，其中 $\lambda_{1},\dots,\lambda_{m}$ 各不相同，于是

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)=0
\end{gather}
$$

我们将对 $m$ 进行归纳来证明 $T$ 可对角化。当 $m=1$ 时，有 $T=\lambda_{1}I$，显然它在任意基下的矩阵都是对角矩阵。

假设 $m>1$ 且结论对更小的 $m$ 成立。子空间 $\operatorname{range}(T-\lambda_{m}I)$ 在 $T$ 下不变，因此 $T$ 在 $\operatorname{range}(T-\lambda_{m}I)$ 上的限制是一个算子。

设 $u \in \operatorname{range}(T-\lambda_{m}I)$，则存在 $v$ 使得 $u=(T-\lambda_{m}I)v$，从而

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{m-1}I)u=(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v=0
\end{gather}
$$

因此 $(z-\lambda_{1})\cdots(z-\lambda_{m-1})$ 是 $T|_{\operatorname{range}(T-\lambda_{m}I)}$ 的零化多项式，根据归纳假设，存在 $\operatorname{range}(T-\lambda_{m}I)$ 上的一个由 $T$ 的特征向量构成的基。

假设 $u \in \operatorname{range}(T-\lambda_{m}I)\cap \ker(T-\lambda_{m}I)$，则 $Tu=\lambda_{m}u$，于是

$$
\begin{gather}
(T-\lambda_{1}I)\cdots(T-\lambda_{m-1}I)u=(\lambda_{m}-\lambda_{1})\cdots(\lambda_{m}-\lambda_{m-1})u=0
\end{gather}
$$

由于各 $\lambda_{1},\dots,\lambda_{m}$ 不同，因此 $u=0$，这表明 $\operatorname{range}(T-\lambda_{m}I)\cap \ker(T-\lambda_{m}I)=\{ 0 \}$。

从而，$\operatorname{range}(T-\lambda_{m}I)+\ker(T-\lambda_{m}I)$ 是一个直和，其维度之和为 $\dim V$，因此 $V=\operatorname{range}(T-\lambda_{m}I)\oplus \ker(T-\lambda_{m}I)$。$\ker(T-\lambda_{m}I)$ 中的每个非零向量都是 $T$ 的特征向量，选取 $\ker(T-\lambda_{m}I)$ 的一个基添加到 $\operatorname{range}(T-\lambda_{m}I)$ 的基中，就得到了 $V$ 的一个由特征向量构成的基，在这个基下 $T$ 有对角矩阵。这就完成了证明。

### Example 5.43

定义 $T \in L(\mathbb{F}^{3})$ 为

$$
\begin{gather}
\mathcal{M}(T)=\begin{pmatrix}
6 & 3 & 4 \\
0 & 6 & 2 \\
0 & 0 & 7
\end{pmatrix}
\end{gather}
$$

$T$ 是可对角化的吗？我们可以来计算 $T$ 的极小多项式。由于 $\mathcal{M}(T)$ 是一个上三角矩阵，因此 $T$ 的特征值为 $6,7$，并且 $(z-6)^{2}(z-7)$ 是 $T$ 的一个零化多项式。这表明 $T$ 的极小多项式或者是 $(z-6)(z-7)$，或者是 $(z-6)^{2}(z-7)$。

代入 $T$ 的矩阵给出 $(T-6I)(T-7I)\neq 0$，因此 $T$ 的极小多项式为 $(z-6)^{2}(z-7)$，因此 [[#Theorem 5.42]] 表明 $T$ 不是可对角化的。

### Theorem 5.44

设 $T \in L(V)$ 可对角化，$U$ 是 $V$ 的子空间且在 $T$ 下不变，则 $T|_{U}$ 是 $U$ 上的可对角化算子。

#### Proof

根据 [[#Theorem 5.42]]，$T$ 的极小多项式为 $p(z)=(z-\lambda_{1})\cdots(z-\lambda_{m})$，其中 $\lambda_{1},\dots,\lambda_{m}$ 不同。该多项式也是 $T|_{U}$ 的零化多项式，因此 $T|_{U}$ 的极小多项式整除 $p$，因而也具有 [[#Theorem 5.42]] 中的形式。

## Gershgorin Disk Theorem

### Definition 5.45 Gershgorin disk

设 $T \in L(V)$ 且 $v_{1},\dots,v_{n}$ 是 $V$ 的一个基，设 $A$ 为 $T$ 在这个基下的矩阵。$T$ 关于 $v_{1},\dots,v_{n}$ 的一个 Gershgorin 圆盘定义为

$$
\begin{gather}
\left\{  z \in \mathbb{F}: \lvert z-A_{j,j} \rvert \leq \sum_{k\neq j} \lvert A_{j,k} \rvert   \right\}
\end{gather}
$$

其中 $1\leq j\leq n$。

每个算子 $T$ 都有 $n$ 个 Gershgorin 圆盘，对应于 $j$ 的 $n$ 个取值。如果 $\mathbb{F}=\mathbb{C}$，那么一个 Gershgorin 圆盘是平面上以 $A_{j,j}$ 为中心的一个闭圆盘，如果 $\mathbb{F}=\mathbb{R}$，那么一个 Gershgorin 圆盘是 $\mathbb{R}$ 上的一个闭区间。

### Theorem 5.46 (Gershgorin 圆盘定理)

设 $T \in L(V)$ 且 $v_{1},\dots,v_{n}$ 是 $V$ 的基。则 $T$ 的每个特征值都包含在 $T$ 关于 $v_{1},\dots,v_{n}$ 的某个 Gershgorin 圆盘中。

#### Proof

设 $\lambda \in \mathbb{F}$ 是 $T$ 的特征值，令 $w \in V$ 为对应的特征向量，则有

$$
\begin{gather}
w=c_{1}v_{1}+\dots+c_{n}v_{n}
\end{gather}
$$

对等式两边应用 $T$，设 $A$ 为 $T$ 在 $v_{1},\dots,v_{n}$ 下的矩阵，则

$$
\begin{align}
\lambda w &= \sum_{k=1}^{n} c_{k} Tv_{k} \\
&=\sum_{k=1}^{n} c_{k} \sum_{j=1}^{n} A_{j,k}v_{j} \\
&=\sum_{j=1}^{n} \left( \sum_{k=1}^{n} A_{j,k}c_{k} \right)v_{j}
\end{align}
$$

由于 $v_{1},\dots,v_{n}$ 是基，因此等式两边的线性组合系数一一对应，即

$$
\begin{gather}
\lambda c_{j}=\sum_{k=1}^{n} A_{j,k}c_{k}
\end{gather}
$$

取 $1\leq j\leq n$ 使得

$$
\begin{gather}
\lvert c_{j} \rvert =\max(\lvert c_{1} \rvert ,\dots,\lvert c_{n} \rvert )
\end{gather}
$$

则

$$
\begin{align}
\lvert \lambda-A_{j,j} \rvert &= \left\lvert  \sum_{k\neq j} A_{j,k} \frac{c_{k}}{c_{j}}  \right\rvert \\
&\leq \sum_{k\neq j} \lvert A_{j,k} \rvert  
\end{align}
$$

这就是说，$\lambda$ 位于第 $j$ 个 Gershgorin 圆盘中。

### Corollary 5.47

设 $T \in L(V)$ 且 $A$ 是 $T$ 在 $V$ 的某个基下的矩阵，如果对任意 $1\leq j\leq n$ 有

$$
\begin{gather}
\lvert A_{j,j} \rvert >\sum_{k\neq j}\lvert A_{j,k} \rvert 
\end{gather}
$$

那么 $T$ 是可逆的。

直观来看，这就是说如果矩阵的对角线元素相对于其它元素足够大，那么它是可逆的。

#### Proof

假设 $T$ 不可逆，则 $0$ 是 $T$ 的一个特征值，从而由 [[#Theorem 5.46 (Gershgorin 圆盘定理)]] 知存在 $j$ 使得

$$
\begin{gather}
\lvert A_{j,j} \rvert \leq \sum_{k\neq j} \lvert A_{j,k} \rvert 
\end{gather}
$$

这与条件矛盾。

# 5E Commuting Operaters

### Definition 5.48 commute 交换

称两个在同一向量空间上的算子 $S,T$ 交换，如果 $ST=TS$。

称两个相同大小的矩阵 $A,B$ 交换，如果 $AB=BA$。

我们已经见过一些交换算子的例子，例如 $\lambda I$ 与任何算子交换，并且如果 $T$ 是算子，$p,q$ 是多项式，那么 $p(T)$ 和 $q(T)$ 交换。

### Example 5.49

在分析学中，我们也可见到一个交换算子的例子。令 $\mathcal{P}_{m}(\mathbb{C}^{2},\mathbb{C})$ 表示所有次数小于等于 $m$ 的双变量多项式构成的向量空间，其中的元素形如

$$
\begin{gather}
p(w,z)=\sum_{j+k\leq m} a_{j,k}w^{j}z^{k}
\end{gather}
$$

定义 $D_{w},D_{z}\in L(\mathcal{P}_{m}(\mathbb{C}^{2},\mathbb{C}))$ 为

$$
\begin{gather}
D_{w}p(w,z)=\sum_{j+k\leq m} ja_{j,k}w^{j-1}z^{k}, \quad D_{z}p(w,z)=\sum_{j+k\leq m} ka_{j,k}w^{j}z^{k-1}
\end{gather}
$$

换言之，$D_{w},D_{z}$ 分别是关于变量 $w$ 和 $z$ 的偏导数算子。$D_{w},D_{z}$ 交换，因为

$$
\begin{gather}
(D_{w}D_{z})p(w,z)=\sum_{j+k\leq m}jk a_{j,k}w^{j-1}z^{k-1}=(D_{z}D_{w})p(w,z)
\end{gather}
$$

更一般地，对于二次连续可微函数（$C^{2}$ 函数），Clairaut 定理表明 $D_{z},D_{w}$ 作为 $C^{2}(E)$ 上的算子是交换的。

### Theorem 5.50

设 $S,T \in L(V)$ 且 $v_{1},\dots,v_{n}$ 是 $V$ 的基，则 $S,T$ 交换当且仅当它们在 $v_{1},\dots,v_{n}$ 下的矩阵交换。

#### Proof

我们有等价链：

$S,T$ 交换当且仅当 $ST=TS$，当且仅当

$$
\begin{gather}
\mathcal{M}(S)\mathcal{M}(T)=\mathcal{M}(ST)=\mathcal{M}(TS)=\mathcal{M}(T)\mathcal{M}(S)
\end{gather}
$$

当且仅当 $\mathcal{M}(S)$ 和 $\mathcal{M}(T)$ 交换。

### Theorem 5.51

设 $S,T \in L(V)$ 交换且 $\lambda \in \mathbb{F}$，则 $E(\lambda,S)$ 在 $T$ 下不变。

#### Proof

设 $v \in E(\lambda,S)$，则

$$
\begin{gather}
STv=TSv=T(\lambda v)=\lambda Tv
\end{gather}
$$

这就是说 $Tv \in E(\lambda,S)$，即 $E(\lambda,S)$ 在 $T$ 下不变。

### Theorem 5.52

两个在同一向量空间中可对角化的算子关于同一个基的矩阵都是对角矩阵，当且仅当两个算子交换。

换句话说，两个算子能够同时对角化当且仅当它们交换。

#### Proof

首先设 $S,T \in L(V)$ 关于同一个基的矩阵都是对角的，则它们的矩阵交换，从而由 [[#Theorem 5.50]] 知 $S,T$ 交换。

现在假设 $S,T$ 可对角化且交换。设 $\lambda_{1},\dots,\lambda_{m}$ 是 $S$ 的不同特征值，从而

$$
\begin{gather}
V=E(\lambda_{1},S)\oplus \dots \oplus E(\lambda_{m},S)
\end{gather}
$$

对任意 $1\leq k\leq m$，$E(\lambda_{k},S)$ 在 $T$ 下不变，由 [[#Theorem 5.44]] 知 $T|_{E(\lambda_{k},S)}$ 可对角化，从而存在 $E(\lambda_{k},S)$ 上由 $T$ 的特征向量构成的基。将这 $m$ 个空间上的基组合起来就得到了 $V$ 的一个基，其中的向量同时是 $S$ 与 $T$ 的特征向量，从而 $S,T$ 在这个基下同时有对角矩阵。这就完成了证明。

### Theorem 5.53

有限维非零复向量空间上的一对交换算子有一个共同的特征向量。

#### Proof

设 $V$ 是有限维非零复向量空间，$S,T \in L(V)$ 交换。[[#Theorem 5.14]] 表明 $S$ 有特征值 $\lambda$，从而 $E(\lambda,S)\neq \{ 0 \}$，且在 $T$ 下不变。

同样由 [[#Theorem 5.14]]，$T|_{E(\lambda,S)}$ 也有一个特征向量，它同时是 $S$ 和 $T$ 的特征向量。

下面的定理是 [[#Corollary 5.31]] 的一个推广。

### Theorem 5.54

设 $V$ 是有限维复向量空间，$S,T \in L(V)$ 交换。则存在 $V$ 的一个基使得 $S,T$ 在这个基下同时有上三角矩阵。

#### Proof

我们对 $n=\dim V$ 进行归纳。$n=1$ 的情况是平凡的，因为 $1\times 1$ 矩阵都是上三角的。现在假设 $n>1$ 且定理对维度更低的空间都成立。

令 $v_{1}$ 为 $S,T$ 的共同特征向量，于是 $Sv_{1}$ 和 $Tv_{1}$ 都在 $\operatorname{span}(v_{1})$ 中。令 $W$ 是 $V$ 的子空间使得

$$
\begin{gather}
V=\operatorname{span}(v_{1})\oplus W
\end{gather}
$$

定义线性映射 $P\colon V\to W$ 为

$$
\begin{gather}
P(av_{1}+w)=w
\end{gather}
$$

其中 $w \in W$。定义 $\hat{S},\hat{T}\in L(W)$ 为

$$
\begin{gather}
\hat{S}(w)=P(Sw), \quad \hat{T}(w)=P(Tw)
\end{gather}
$$

我们要对 $\hat{S},\hat{T}$ 应用归纳假设，因此我们需要证明 $\hat{S},\hat{T}$ 交换。我们有

$$
\begin{align}
\hat{S}\hat{T}w=\hat{S}(P(Tw))=\hat{S}(Tw-av_{1})=P(S(Tw-av_{1}))=P(STw)
\end{align}
$$

其中最后一个等式成立因为 $v_{1}$ 是 $S$ 的特征向量，且 $Pv_{1}=0$。同理我们有

$$
\begin{gather}
\hat{T}\hat{S}w=P(TSw)
\end{gather}
$$

由 $ST=TS$ 知 $\hat{S}\hat{T}=\hat{T}\hat{S}$。

应用归纳假设，可知存在 $W$ 的基 $v_{2},\dots,v_{n}$ 使得 $\hat{S},\hat{T}$ 同时上三角化，并且 $v_{1},\dots,v_{n}$ 是 $V$ 的基。

对任意 $2\leq k\leq n$，存在 $a_{k},b_{k}\in \mathbb{C}$ 使得

$$
\begin{gather}
Sv_{k}=a_{k}v_{1}+\hat{S}v_{k}, \quad Tv_{k}=b_{k}v_{1}+\hat{T}v_{k}
\end{gather}
$$

又由于 $\hat{S}v_{k},\hat{T}v_{k}\in \operatorname{span}(v_{2},\dots,v_{k})$，我们有

$$
\begin{gather}
Sv_{k},Tv_{k}\in \operatorname{span}(v_{1},\dots,v_{k})
\end{gather}
$$

即 $S,T$ 在 $v_{1},\dots,v_{n}$ 下的矩阵是上三角的。

### Theorem 5.55

设 $V$ 是有限维复向量空间且 $S,T \in L(V)$ 交换，则

1. $S+T$ 的每个特征值都等于 $S$ 的某个特征值加 $T$ 的某个特征值，
2. $ST$ 的每个特征值都等于 $S$ 的某个特征值乘以 $T$ 的某个特征值。

#### Proof

[[#Theorem 5.54]] 表明，存在一个基使得 $S,T$ 的矩阵 $\mathcal{M}(S),\mathcal{M}(T)$ 是上三角的。并且

$$
\begin{gather}
\mathcal{M}(S+T)=\mathcal{M}(S)+\mathcal{M}(T), \quad \mathcal{M}(ST)=\mathcal{M}(S)\mathcal{M}(T)
\end{gather}
$$

根据矩阵加法和乘法的定义，$\mathcal{M}(S+T)$ 对角线上的元素是 $\mathcal{M}(S)$ 和 $\mathcal{M}(T)$ 对角线上对应元素的和，$\mathcal{M}(ST)$ 对角线上的元素是 $\mathcal{M}(S)$ 和 $\mathcal{M}(T)$ 对角线上对应元素的乘积。

又由于上三角矩阵的对角线元素恰是算子的特征值，根据上面的讨论我们就完成了证明。