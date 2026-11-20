向量空间推广了 $\mathbb{F}^{n}$ 中的线性结构，而忽略了其上的几何结构：长度、角度等。这些概念均能够嵌入本章要研究的内积概念中。

# 6A Inner Products and Norms

## Inner Products

要引入内积，我们首先来看 $\mathbb{R}^{2}$ 和 $\mathbb{R}^{3}$ 中的相关概念。一个 $\mathbb{R}^{2}$ 中的向量 $v$ 可以视为从原点到 $(a,b)$ 的一个有向线段，它的长度我们记作 $\lVert v \rVert$，定义为

$$
\begin{gather}
\lVert v \rVert =\sqrt{ a^{2}+b^{2} }
\end{gather}
$$

类似地，如果 $v=(a,b,c)\in \mathbb{R}^{3}$，那么 $\lVert v \rVert=\sqrt{ a^{2}+b^{2}+c^{2} }$。

向 $\mathbb{R}^{n}$ 的推广是容易的：我们定义 $x=(x_{1},\dots,x_{n})\in \mathbb{R}^{n}$ 的长度为

$$
\begin{gather}
\lVert x \rVert =\sqrt{ x_{1}^{2}+\dots+x_{n}^{2} }
\end{gather}
$$

长度 $\lVert x \rVert$ 关于 $x$ 不是线性的，因此我们引入如下概念：

### Definition 6.1 dot product 点积

设 $x,y \in \mathbb{R}^{n}$，它们的点积定义为

$$
\begin{gather}
x\cdot y=x_{1}y_{1}+\dots+x_{n}y_{n}
\end{gather}
$$

其中 $x=(x_{1},\dots,x_{n}),y=(y_{1},\dots,y_{n})$。

注意到 $x\cdot x=\lVert x \rVert^{2}$，并且容易验证点积有如下性质：

- 正定性：$x\cdot x\geq 0$ 且 $x\cdot x=0$ 当且仅当 $x=0$。
- 第一个变量的线性性：固定 $y \in \mathbb{R}^{n}$，从 $\mathbb{R}^{n}$ 到 $\mathbb{R}$ 的映射 $x\mapsto x\cdot y$ 是线性的。
- 对称性：$x\cdot y=y\cdot x$。

内积是对点积性质的抽象。在实向量空间上，一个内积就是满足以上性质的双变量函数。不过，我们希望能够有一个对实向量空间与复向量空间都适用的定义，因此下面我们需要先研究 $\mathbb{C}^{n}$ 上的内积。

设 $z=(z_{1},\dots,z_{n})\in \mathbb{C}^{n}$，我们希望 $z$ 的长度是一个非负实数，因此我们定义

$$
\begin{gather}
\lVert z \rVert =\sqrt{ \lvert z_{1} \rvert ^{2}+\dots+\lvert z_{n} \rvert ^{2} }
\end{gather}
$$

于是，仿照实向量空间中的定义，我们希望 $\lVert z \rVert^{2}$ 等于 $z$ 与它自身的内积。注意到

$$
\begin{gather}
\lVert z \rVert ^{2}=z_{1} \overline{z}_{1}+\dots+z_{n} \overline{z}_{n}
\end{gather}
$$

因此 $\mathbb{C}^{n}$ 上 $w,z$ 的内积应当等于

$$
\begin{gather}
w_{1} \overline{z}_{1}+\dots+w_{n} \overline{z}_{n}
\end{gather}
$$

显然它满足正定性与第一个变量（$w$）的线性性。如果我们交换 $w$ 与 $z$ 的位置，那么内积的值将变成它的复共轭，因此 $\mathbb{C}^{n}$ 上的内积满足共轭对称性。这一定义与 $\mathbb{R}^{n}$ 上的点积是相容的，因为实数的复共轭是其自身。有了这样的动机，我们就可以来定义向量空间 $V$ 上的内积了。

### Definition 6.2 inner product 内积，inner product space 内积空间

$V$ 上的一个内积是一个函数，其将一对 $u,v \in V$ 对应到 $\langle u,v \rangle\in \mathbb{F}$，并且满足以下性质。

1. 正定性：对任意 $v \in V$，$\langle v,v \rangle\geq 0$，并且 $\langle v,v \rangle=0$ 当且仅当 $v=0$。
2. 第一个变量的加性：对 $u,v,w \in V$ 有 $\langle u+v,w \rangle=\langle u,w \rangle+\langle v,w \rangle$。
3. 第一个变量的齐次性：对 $\lambda \in \mathbb{F}$ 和 $u,v \in V$ 有 $\langle \lambda u,v \rangle=\lambda \langle u,v \rangle$。
4. 共轭对称性：对 $u,v \in V$ 有 $\langle u,v \rangle=\overline{\langle v,u \rangle}$。

一个定义了内积的向量空间称为一个内积空间。

### Example 6.3

(a) $\mathbb{F}^{n}$ 上的 Euclidean 内积定义为

$$
\begin{gather}
\langle w,z \rangle =w_{1} \overline{z}_{1}+\dots+w_{n} \overline{z}_{n}
\end{gather}
$$

除非特殊指定，否则我们总是将 Euclidean 内积作为 $\mathbb{F}^{n}$ 上的内积。

(b) 设 $c_{1},\dots,c_{n}>0$，那么 $\mathbb{F}^{n}$ 上的函数

$$
\begin{gather}
\langle w,z \rangle =c_{1}w_{1} \overline{z}_{1}+\dots+c_{n}w_{n} \overline{z}_{n}
\end{gather}
$$

是一个内积。

(c) 在 $[-1,1]$ 上的连续实值函数空间 $C([-1,1],\mathbb{R})$ 中可以定义内积

$$
\begin{gather}
\langle f,g \rangle =\int_{-1}^{1} fg
\end{gather}
$$

(d) 在 $\mathcal{P}(\mathbb{R})$ 上可以定义内积

$$
\begin{gather}
\langle p,q \rangle =\int _{0}^{\infty} p(x)q(x)e^{-x} \, \mathrm{d}x 
\end{gather}
$$

### Notation 6.4

在本章和下一章中，我们设 $V,W$ 为 $\mathbb{F}$ 上的内积空间。

### Theorem 6.5

(a) 固定 $v \in V$，从 $V$ 到 $\mathbb{F}$ 的函数 $u\mapsto \langle u,v \rangle$ 是线性的。
(b) 对任意 $v \in V$ 有 $\langle 0,v \rangle=\langle v,0 \rangle=0$。
(c) 对任意 $u,v,w \in V$ 有 $\langle u,v+w \rangle=\langle u,v \rangle+\langle u,w \rangle$。
(d) 对 $\lambda \in \mathbb{F}$ 和 $u,v \in V$ 有 $\langle u,\lambda v \rangle=\overline{\lambda}\langle u,v \rangle$。

#### Proof

(a) 由第一个变量的加性和齐次性立即得到。

由于 $T(u)=\langle u,v \rangle$ 是线性的，故 $T(0)=\langle 0,v \rangle=0$，利用共轭对称性可得 $\langle v,0 \rangle=0$。即证 (b)。

对于 (c)，我们有

$$
\begin{align}
\langle u,v+w \rangle &= \overline{\langle v+w,u \rangle } \\
&= \overline{\langle v,u \rangle }+\overline{\langle w,u \rangle } \\
&=\langle u,v \rangle +\langle u,w \rangle 
\end{align}
$$

对于 (d)，我们有

$$
\begin{align}
\langle u,\lambda v \rangle &= \overline{\langle \lambda v,u \rangle } \\
&= \overline{\lambda} \overline{\langle v,u \rangle } \\
&=\overline{\lambda} \langle u,v \rangle 
\end{align}
$$

## Norms

### Definition 6.6 norm 范数

$v \in V$ 的范数 $\lVert v \rVert$ 定义为

$$
\begin{gather}
\lVert v \rVert =\sqrt{ \langle v,v \rangle  }
\end{gather}
$$

### Example 6.7

(a) $\mathbb{F}^{n}$ 上的 Euclidean 范数是由 Euclidean 内积诱导的范数

$$
\begin{gather}
\lVert z \rVert =\sqrt{ \lvert z_{1} \rvert ^{2}+\dots+\lvert z_{n} \rvert ^{2} }
\end{gather}
$$

(b) $C([-1,1],\mathbb{R})$ 上的内积诱导了其上的 $L^{2}$ 范数

$$
\begin{gather}
\lVert f \rVert =\left( \int_{-1}^{1} f^{2} \right)^{1/2}
\end{gather}
$$

### Theorem 6.8

设 $v \in V$，范数满足以下性质：

1. 正定性：$\lVert v \rVert\geq 0$，且 $\lVert v \rVert=0$ 当且仅当 $v=0$。
2. 齐次性：对 $\lambda \in \mathbb{F}$ 有 $\lVert \lambda v \rVert=\lvert \lambda \rvert\lVert v \rVert$。

#### Proof

(1) 的正性是显然的，定性由内积的性质 $\langle v,v \rangle=0$ 当且仅当 $v=0$ 给出。

(2) 我们有

$$
\begin{align}
\lVert \lambda v \rVert^{2} &= \langle \lambda v,\lambda v \rangle  \\
&=\lambda  \overline{\lambda} \langle v,v \rangle  \\
&=\lvert \lambda \rvert ^{2} \lVert v \rVert ^{2} 
\end{align}
$$

即 $\lVert \lambda v \rVert=\lvert \lambda \rvert\lVert v \rVert$。

性质 (2) 的证明指出了一个常用技巧：范数的平方通常比范数更容易处理，因为我们可以将其转换为内积的相关表达式。

### Definition 6.9 orthogonal 正交的

称两个向量 $u,v \in V$ 正交，如果 $\langle u,v \rangle=0$。

在上面的定义中，$u,v$ 的顺序是无关紧要的，因为 $\langle u,v \rangle=0$ 当且仅当 $\langle v,u \rangle=0$。

正交性是对垂直概念的推广。在 $\mathbb{R}^{2}$ 中，其上的 Euclidean 内积满足

$$
\begin{gather}
\langle u,v \rangle =\lVert u \rVert \lVert v \rVert \cos\theta
\end{gather}
$$

其中 $\theta$ 是向量 $u,v$ 之间的夹角。因此 $u,v$ 正交当且仅当它们的夹角为 $90^{\circ}$，即 $u,v$ 垂直。

### Theorem 6.10

(a) $0$ 与 $V$ 中的任何向量正交。
(b) $0$ 是唯一与自身正交的向量。

#### Proof

(a) 我们有 $\langle v,0 \rangle=0$，因此 $0$ 与任意向量 $v$ 正交。

(b) 由内积的正定性得 $\langle v,v \rangle=0$ 当且仅当 $v=0$，即证。

### Theorem 6.11 (勾股定理)

设 $u,v \in V$ 正交，则

$$
\begin{gather}
\lVert u+v \rVert ^{2}=\lVert u \rVert ^{2}+\lVert v \rVert ^{2}
\end{gather}
$$

#### Proof

我们有 $\langle u,v \rangle=0$，从而

$$
\begin{align}
\lVert u+v \rVert ^{2} &= \langle u+v,u+v \rangle  \\
&=\langle u,u \rangle +\langle v,u \rangle +\langle u,v \rangle +\langle v,v \rangle  \\
&=\lVert u \rVert ^{2}+\lVert v \rVert ^{2}
\end{align}
$$

设 $u,v \in V$，$v\neq 0$，在物理学中的一个重要方法是所谓的“正交分解”，其中我们把 $u$ 分解为 $v$ 的标量倍加上一个与 $v$ 正交的向量 $w$，如图所示。

![](6-1.png)

换言之，我们需要找到标量 $c$，使得

$$
\begin{gather}
u=cv+(u-cv)
\end{gather}
$$

满足 $\langle u-cv,v \rangle=0$。按内积的线性性展开可得

$$
\begin{gather}
\langle u,v \rangle -c\lVert v \rVert ^{2}=0 \implies c= \frac{\langle u,v \rangle }{\lVert v \rVert ^{2}}
\end{gather}
$$

### Lemma 6.12 (正交分解)

设 $u,v \in V,v\neq 0$，令 $c=\frac{\langle u,v \rangle}{\lVert v \rVert^{2}}$ 且 $w=u-cv$，则

$$
\begin{gather}
u=cv+w, \quad \langle w,v \rangle =0
\end{gather}
$$

### Theorem 6.13 (Cauchy-Schwarz 不等式)

设 $u,v \in V$，则

$$
\begin{gather}
\lvert \langle u,v \rangle  \rvert \leq \lVert u \rVert \lVert v \rVert 
\end{gather}
$$

等式成立当且仅当其中一个向量是另一个的标量倍。

#### Proof

如果 $v=0$，那么不等式两边的值都为零。如果 $v\neq 0$，考虑正交分解

$$
\begin{gather}
u=\frac{\langle u,v \rangle }{\lVert v \rVert ^{2}}v+w
\end{gather}
$$

根据勾股定理有

$$
\begin{align}
\lVert u \rVert ^{2} &= \left\lVert  \frac{\langle u,v \rangle }{\lVert v \rVert ^{2}}v  \right\rVert ^{2}+\lVert w \rVert ^{2} \\
&=\frac{\lvert \langle u,v \rangle  \rvert^{2} }{\lVert v \rVert ^{2}}+\lVert w \rVert ^{2} \\
&\geq \frac{\lvert \langle u,v \rangle  \rvert ^{2}}{\lVert v \rVert ^{2}}
\end{align}
$$

两边乘以 $\lVert v \rVert^{2}$ 并取平方根即证。此外，等式成立当且仅当 $w=0$，即 $u$ 是 $v$ 的标量倍。交换 $u,v$ 的角色，我们也可知等式成立当且仅当 $v$ 是 $u$ 的标量倍。

### Example 6.14

(a) 取 $\mathbb{R}^{n}$ 上的 Euclidean 内积，则 Cauchy-Schwarz 不等式给出

$$
\begin{gather}
(x_{1}y_{1}+\dots+x_{n}y_{n})^{2}\leq(x_{1}^{2}+\dots+x_{n}^{2})(y_{1}^{2}+\dots+y_{n}^{2})
\end{gather}
$$

(b) 取 $C([-1,1],\mathbb{R})$ 上的内积，则有

$$
\begin{gather}
\left\lvert  \int_{-1}^{1} fg  \right\rvert ^{2}\leq \left( \int_{-1}^{1} f^{2} \right)\left( \int_{-1}^{1}g^{2} \right)
\end{gather}
$$

### Theorem 6.15 (三角不等式)

设 $u,v \in V$，则

$$
\begin{gather}
\lVert u+v \rVert \leq \lVert u \rVert +\lVert v \rVert 
\end{gather}
$$

等式成立当且仅当其中一个向量是另一个的非负实数倍。

它的几何解释如下：在一个三角形中，斜边的长度总是小于等于两对边的长度之和。

#### Proof

根据 Cauchy-Schwarz 不等式有

$$
\begin{align}
\lVert u+v \rVert ^{2} &= \langle u+v,u+v \rangle  \\
&=\langle u,u \rangle +\langle v,v \rangle +\langle u,v \rangle +\langle v,u \rangle  \\
&=\lVert u \rVert ^{2}+\lVert v \rVert ^{2}+2\operatorname{Re} \langle u,v \rangle  \\
&\leq \lVert u \rVert ^{2}+\lVert v \rVert ^{2}+2\lvert \langle u,v \rangle  \rvert  \\
&\leq \lVert u \rVert ^{2}+\lVert v \rVert ^{2}+2\lVert u \rVert \lVert v \rVert  \\
&=(\lVert u \rVert +\lVert v \rVert )^{2}
\end{align}
$$

两边取平方根即证。等式成立当且仅当上式中的两个不等式取等号，即 $\langle u,v \rangle \in \mathbb{R}$ 且 $u,v$ 的其中一个是另一个的标量倍，它成立当且仅当其中一个向量是另一个的非负实数倍。

### Theorem 6.16 (平行四边形恒等式)

设 $u,v \in V$，则

$$
\begin{gather}
\lVert u+v \rVert ^{2}+\lVert u-v \rVert ^{2}=2(\lVert u \rVert ^{2}+\lVert v \rVert ^{2})
\end{gather}
$$

它的几何解释如下：在由 $u,v$ 为边构成的平行四边形中，其两条对角线的长度平方和等于四条边的长度平方和。

![](6-2.png)

#### Proof

我们有

$$
\begin{align}
\lVert u+v \rVert ^{2}+\lVert u-v \rVert ^{2} &= \langle u+v,u+v \rangle +\langle u-v,u-v \rangle  \\
&=\langle u,u \rangle +\langle v,v \rangle +\langle u,v \rangle +\langle v,u \rangle  \\
&+\langle u,u \rangle +\langle v,v \rangle -\langle v,u \rangle -\langle u,v \rangle  \\
&=2(\lVert u \rVert ^{2}+\lVert v \rVert ^{2})
\end{align}
$$

# 6B Orthonormal Bases

## Orthonormal Lists and the Gram-Schmidt Procedure

### Definition 6.17 orthonormal 标准正交的

称 $V$ 中的向量组 $e_{1},\dots,e_{m}$ 是标准正交的，如果对任意 $1\leq j,k\leq m$ 有

$$
\begin{gather}
\langle e_{j},e_{k} \rangle =\delta_{jk}=\begin{cases}
1, & j=k \\
0, & j\neq k
\end{cases}
\end{gather}
$$

换言之，一个标准正交的向量组中每个向量范数为 $1$，并且与其它向量均正交。

### Example 6.18

(a) $\mathbb{F}^{n}$ 中的标准基是标准正交的。

(b) $\left( \frac{1}{\sqrt{ 3 }},\frac{1}{\sqrt{ 3 }},\frac{1}{\sqrt{ 3 }} \right),\left( -\frac{1}{\sqrt{ 2 }},\frac{1}{\sqrt{ 2 }},0 \right)$ 在 $\mathbb{F}^{3}$ 中标准正交。

(c) $C([-\pi,\pi],\mathbb{R})$ 中的向量组

$$
\begin{gather}
\frac{1}{\sqrt{ 2\pi }},\frac{\cos x}{\sqrt{ \pi }},\frac{\sin x}{\sqrt{ \pi }},\dots,\frac{\cos nx}{\sqrt{ \pi }},\frac{\sin nx}{\sqrt{ \pi }}
\end{gather}
$$

在内积

$$
\begin{gather}
\langle f,g \rangle =\int_{-\pi}^{\pi} fg
\end{gather}
$$

下标准正交。这组标准正交向量通常出现在 Fourier 级数的研究中。

(d) 在 $\mathcal{P}_{2}(\mathbb{R})$ 上我们可以定义内积

$$
\begin{gather}
\langle p,q \rangle =\int_{-1}^{1}pq
\end{gather}
$$

$\mathcal{P}_{2}(\mathbb{R})$ 上的标准基 $1,x,x^{2}$ 不是标准正交的。这是因为这些向量的范数不为 $1$，并且 $1$ 与 $x^{2}$ 并不正交。

### Theorem 6.19

设 $e_{1},\dots,e_{m}$ 标准正交，则对任意 $a_{1},\dots,a_{m}\in \mathbb{F}$ 有

$$
\begin{gather}
\lVert a_{1}e_{1}+\dots+a_{m}e_{m} \rVert ^{2}=\lvert a_{1} \rvert ^{2}+\dots+\lvert a_{m} \rvert ^{2}
\end{gather}
$$

#### Proof

反复应用勾股定理并利用 $\lVert e_{k} \rVert=1$ 即证。

### Corollary 6.20

任何标准正交向量组都是线性无关的。

#### Proof

假设 $e_{1},\dots,e_{m}$ 标准正交，则如果

$$
\begin{gather}
a_{1}e_{1}+\dots+a_{m}e_{m}=0
\end{gather}
$$

那么 [[#Theorem 6.19]] 给出 $\lvert a_{1} \rvert^{2}+\dots+\lvert a_{m} \rvert^{2}=0$，即 $a_{1}=\dots=a_{m}=0$。因此 $e_{1},\dots,e_{m}$ 线性无关。

### Theorem 6.21 (Bessel 不等式)

设 $e_{1},\dots,e_{m}\in V$ 标准正交，则对任意 $v \in V$ 有

$$
\begin{gather}
\lvert \langle v,e_{1} \rangle  \rvert ^{2}+\dots+\lvert \langle v,e_{m} \rangle  \rvert ^{2}\leq \lVert v \rVert ^{2}
\end{gather}
$$

#### Proof

设 $v \in V$，令

$$
\begin{gather}
u=\langle v,e_{1} \rangle e_{1}+\dots+\langle v,e_{m} \rangle e_{m}, \quad w=v-u
\end{gather}
$$

由于 $\langle w,e_{k} \rangle=\langle v,e_{k} \rangle-\langle v,e_{k} \rangle\langle e_{k},e_{k} \rangle=0$，故 $\langle w,u \rangle=0$，从而

$$
\begin{align}
\lVert v \rVert ^{2} &= \lVert u \rVert ^{2}+\lVert w \rVert ^{2} \\
&\geq \lVert u \rVert ^{2} \\
&=\lvert \langle v,e_{1} \rangle  \rvert ^{2}+\dots+\lvert \langle v,e_{m} \rangle  \rvert ^{2}
\end{align}
$$

### Definition 6.22 orthonormal basis 标准正交基

$V$ 的一个标准正交基是 $V$ 中的一个标准正交向量组，其同时也是一个基。

例如，$\mathbb{F}^{n}$ 上的标准基就是一个标准正交基。

### Theorem 6.23

设 $V$ 是有限维的，则 $V$ 中长度为 $\dim V$ 的标准正交向量组是一个标准正交基。

#### Proof

根据 [[#Corollary 6.20]]，标准正交向量组是线性无关的，而长度为 $\dim V$ 的线性无关向量组是一个基，这就完成了证明。

### Theorem 6.24

设 $e_{1},\dots,e_{n}$ 是 $V$ 的标准正交基，$u,v \in V$，则

1. $v=\langle v,e_{1} \rangle e_{1}+\dots+\langle v,e_{n} \rangle e_{n}$，
2. (Parseval) $\lVert v \rVert^{2}=\lvert \langle v,e_{1} \rangle \rvert^{2}+\dots+\lvert \langle v,e_{n} \rangle \rvert^{2}$，
3. $\langle u,v \rangle=\langle u,e_{1} \rangle \overline{\langle v,e_{1} \rangle}+\dots+\langle u,e_{n} \rangle \overline{\langle v,e_{n} \rangle}$。

这就是说，任何有限维的内积空间都同构于带有 Euclidean 内积的 $\mathbb{F}^{n}$，其中 $\langle v,e_{k} \rangle$ 扮演了 $z \in \mathbb{F}^{n}$ 中第 $k$ 个坐标 $z_{k}$ 的角色。

#### Proof

由于 $e_{1},\dots,e_{n}$ 是基，因此 $v \in V$ 有唯一的表示

$$
\begin{gather}
v=a_{1}e_{1}+\dots+a_{n}e_{n}
\end{gather}
$$

两边取关于 $e_{k}$ 的内积，利用标准正交性即得 $\langle v,e_{k} \rangle=a_{k}$。

(2) 直接由 (1) 以及勾股定理给出。

(3) 将 $u,v$ 写成如 (1) 所示的坐标形式并按内积的性质展开，根据标准正交性即得

$$
\begin{gather}
\langle u,v \rangle =\sum_{j,k} \langle u,e_{j} \rangle \overline{\langle v,e_{k} \rangle } \langle e_{j},e_{k} \rangle =\sum_{j=1}^{n} \langle u,e_{j} \rangle \overline{\langle v,e_{j} \rangle }
\end{gather}
$$

下面的算法指出，我们可以将任何线性无关向量组转换成标准正交组。

### Theorem 6.25 (Gram-Schmidt)

设 $v_{1},\dots,v_{m}$ 在 $V$ 中线性无关。令 $f_{1}=v_{1}$，对 $2\leq k\leq m$，递归地定义

$$
\begin{gather}
f_{k}=v_{k}-\frac{\langle v_{k},f_{1} \rangle }{\lVert f_{1} \rVert ^{2}}f_{1}-\dots-\frac{\langle v_{k},f_{k-1} \rangle }{\lVert f_{k-1} \rVert ^{2}} f_{k-1}
\end{gather}
$$

再令 $e_{k}=f_{k} /\lVert f_{k} \rVert$，则 $e_{1},\dots,e_{m}$ 在 $V$ 中标准正交，并且对 $1\leq k\leq m$ 有

$$
\begin{gather}
\operatorname{span}(v_{1},\dots,v_{k})=\operatorname{span}(e_{1},\dots,e_{k})
\end{gather}
$$

#### Proof

我们对 $k$ 进行归纳。当 $k=1$ 时，由于 $e_{1}=f_{1} /\lVert f_{1} \rVert$，故 $\lVert e_{1} \rVert=1$，并且 $\operatorname{span}(v_{1})=\operatorname{span}(e_{1})$，因为 $e_{1}$ 是 $v_{1}$ 的非零常数倍。

设 $k>1$ 且 $e_{1},\dots,e_{k-1}$ 标准正交，满足

$$
\begin{gather}
\operatorname{span}(v_{1},\dots,v_{k-1})=\operatorname{span}(e_{1},\dots,e_{k-1})
\end{gather}
$$

由于 $v_{1},\dots,v_{m}$ 线性无关，因此 $v_{k}\not\in \operatorname{span}(v_{1},\dots,v_{k-1})$，因此 $v_{k}\not\in \operatorname{span}(e_{1},\dots,e_{k-1})=\operatorname{span}(f_{1},\dots,f_{k-1})$，从而 $f_{k}\neq 0$。取 $e_{k}=f_{k} /\lVert f_{k} \rVert$，则 $\lVert e_{k} \rVert=1$。

设 $1\leq j\leq k-1$，则

$$
\begin{align}
\langle e_{k},e_{j} \rangle &= \frac{1}{\lVert f_{k} \rVert \lVert f_{j} \rVert } \langle f_{k},f_{j} \rangle  \\
&=\frac{1}{\lVert f_{k} \rVert \lVert f_{j} \rVert } \left< v_{k}-\frac{\langle v_{k},f_{j} \rangle }{\lVert f_{j} \rVert ^{2}} f_{j}, f_{j} \right>  \\
&=0
\end{align}
$$

因此 $e_{1},\dots,e_{k}$ 标准正交。

根据 $e_{k}$ 的定义，我们可知 $v_{k}\in \operatorname{span}(e_{1},\dots,e_{k})$，从而

$$
\begin{gather}
\operatorname{span}(v_{1},\dots,v_{k})\subset \operatorname{span}(e_{1},\dots,e_{k})
\end{gather}
$$

又因为两组向量均线性无关，因此两个张成空间的维度均为 $k$，从而它们相等。这就完成了证明。

#### Motivation

Gram-Schmidt 过程的几何直观非常简单：在算法的每一步中，我们从 $v_{k}$ 中减去 $v_{k}$ 在前面 $k-1$ 条轴（根据归纳假设，它们是正交的）上的投影 $\frac{\langle v_{k},f_{j} \rangle}{\lVert f_{j} \rVert^{2}}f_{j}$，剩下的部分就是正交于所有前面 $k-1$ 个方向的部分。

![](6-3.png)

### Theorem 6.26

任何有限维内积空间都有标准正交基。

#### Proof

设 $V$ 是有限维的，取 $V$ 的一个基，对其应用 Gram-Schmidt 过程即可得到一个长度为 $\dim V$ 的标准正交向量组，从而是一个标准正交基。

### Theorem 6.27

设 $V$ 是有限维的，则 $V$ 中任意标准正交向量组都可扩张为 $V$ 的一个标准正交基。

#### Proof

设 $e_{1},\dots,e_{m}$ 在 $V$ 中标准正交，则 $e_{1},\dots,e_{m}$ 线性无关，从而可以扩张为 $V$ 的基 $e_{1},\dots,e_{m},v_{1},\dots,v_{n}$。应用 Gram-Schmidt 过程可得一个标准正交基

$$
\begin{gather}
e_{1},\dots,e_{m},f_{1},\dots,f_{n}
\end{gather}
$$

其中 $e_{1},\dots,e_{m}$ 在 Gram-Schmidt 过程中保持不变，因为它们自身就是正交的。

回顾一下，一个上三角矩阵形如

$$
\begin{gather}
\begin{pmatrix}
\ast &  & \ast \\
 & \ddots &  \\
0 &  & \ast
\end{pmatrix}
\end{gather}
$$

其中对角线下方的元素均为零。在上一章中我们给出了算子 $T$ 可上三角化的一个充分必要条件，而在内积空间中，我们关心的是：是否存在一个标准正交基使得 $T$ 在这个基下的矩阵是上三角的？下面的定理表明，只要 $T$ 可上三角化，那么必然存在这样的标准正交基。

### Theorem 6.28

设 $V$ 是有限维的且 $T \in L(V)$。则 $T$ 在 $V$ 的某个标准正交基下有上三角矩阵当且仅当 $T$ 的极小多项式可分解为 $(z-\lambda_{1})\cdots(z-\lambda_{m})$。

#### Proof

假设 $T$ 在某个基 $v_{1},\dots,v_{n}$ 下有上三角矩阵，则对任意 $1\leq k\leq n$，$\operatorname{span}(v_{1},\dots,v_{k})$ 在 $T$ 下不变。对 $v_{1},\dots,v_{n}$ 应用 Gram-Schmidt 过程可得一个标准正交基 $e_{1},\dots,e_{n}$，满足

$$
\begin{gather}
\operatorname{span}(v_{1},\dots,v_{k})=\operatorname{span}(e_{1},\dots,e_{k})
\end{gather}
$$

因此 $\operatorname{span}(e_{1},\dots,e_{k})$ 在 $T$ 下不变。于是，$T$ 在 $e_{1},\dots,e_{n}$ 下的矩阵是上三角的。根据 [[5 Eigenvalues and Eigenvectors#Theorem 5.30]] 即证。

### Corollary 6.29 (Schur)

有限维非零复内积空间上的任意算子都可在某个标准正交基下有上三角矩阵。

## Linear Functionals on Inner Product Spaces

回顾一下，一个线性泛函是 $V^{*}=L(V,\mathbb{F})$ 中的一个元素。特别地，如果 $v \in V$，那么映射 $u\mapsto \langle u,v \rangle$ 就是一个线性泛函。下面的定理表明，$V$ 上的任意线性泛函都具有以上形式。

### Theorem 6.30 (Riesz 表示定理)

设 $V$ 是有限维的，$\varphi$ 是 $V$ 上的线性泛函，则存在唯一的 $v \in V$ 使得

$$
\begin{gather}
\varphi(u)=\langle u,v \rangle \quad (u \in V)
\end{gather}
$$

#### Proof

首先我们证明存在性。取 $V$ 的一个标准正交基 $e_{1},\dots,e_{n}$，则

$$
\begin{align}
\varphi(u)&= \varphi(\langle u,e_{1} \rangle e_{1}+\dots+\langle u,e_{n} \rangle e_{n}) \\
&=\langle u,e_{1} \rangle \varphi(e_{1})+\dots+\langle u,e_{n} \rangle \varphi(e_{n}) \\
&=\langle u,\overline{\varphi(e_{1})}e_{1}+\dots+\overline{\varphi(e_{n})}e_{n} \rangle 
\end{align}
$$

因此取 $v=\overline{\varphi(e_{1})}e_{1}+\dots+\overline{\varphi(e_{n})}e_{n}$ 即可。

下面证明唯一性。假设有 $v_{1},v_{2}\in V$ 使得对任意 $u \in V$ 有

$$
\begin{gather}
\varphi(u)=\langle u,v_{1} \rangle =\langle u,v_{2} \rangle 
\end{gather}
$$

则 $\langle u,v_{1}-v_{2} \rangle=0$，取 $u=v_{1}-v_{2}$ 即得 $v_{1}-v_{2}=0$，即证。

上述定理给出了一个公式以计算满足

$$
\begin{gather}
\varphi(u)=\langle u,v \rangle 
\end{gather}
$$

的 $v$。特别地，我们有

$$
\begin{gather}
v=\overline{\varphi(e_{1})}e_{1}+\dots+\overline{\varphi(e_{n})}e_{n}
\end{gather}
$$

以上公式看上去不仅依赖于 $\varphi$，还依赖于选取的标准正交基。然而，[[#Theorem 6.30 (Riesz 表示定理)]] 的唯一性表明 $v$ 只依赖于 $\varphi$，而与正交基的选取无关。

在下一节我们还将回到 Riesz 表示定理，我们将展示，通过这种线性泛函 $\varphi$ 与向量 $v$ 的一一对应，我们得以建立向量空间 $V$ 与其对偶空间 $V^{*}$ 的同构。

# 6C Orthogonal Complements and Minimization Problems

## Orthogonal Complements

### Definition 6.31 orthogonal complement 正交补

设 $U\subset V$，则 $U$ 的正交补 $U^{\perp}$ 定义为 $V$ 中所有与 $U$ 中所有向量正交的向量构成的集合：

$$
\begin{gather}
U^{\perp}=\{ v \in V : \langle u,v \rangle =0, u \in U \}
\end{gather}
$$

### Example 6.32

(a) 设 $V=\mathbb{R}^{3}$，如果 $U=\{ (2,3,5) \}$，则 $U^{\perp}$ 是平面 $\{ (x,y,z): 2x+3y+5z=0 \}$。

如果 $U$ 是平面 $\{ (x,y,z):2x+3y+5z=0 \}$，那么 $U^{\perp}$ 就是直线 $\{ (2t,3t,5t): t\in \mathbb{R} \}$

(b) 更一般地，如果 $U$ 是 $\mathbb{R}^{3}$ 中过原点的直线，那么 $U^{\perp}$ 就是正交于该直线的平面；如果 $U$ 是 $\mathbb{R}^{3}$ 中过原点的平面，那么 $U^{\perp}$ 就是正交于该平面的直线。

(c) 如果 $e_{1},\dots,e_{m},f_{1},\dots,f_{n}$ 是 $V$ 的标准正交基，那么

$$
\begin{gather}
\operatorname{span}(e_{1},\dots,e_{m})^{\perp}=\operatorname{span}(f_{1},\dots,f_{n})
\end{gather}
$$

### Theorem 6.33

(a) 如果 $U\subset V$，那么 $U^{\perp}$ 是 $V$ 的一个子空间。
(b) $\{ 0 \}^{\perp}=V$。
(c) $V^{\perp}=\{ 0 \}$。
(d) 如果 $U\subset V$，那么 $U\cap U^{\perp}\subset \{ 0 \}$。
(e) 如果 $G,H\subset V$ 且 $G\subset H$，那么 $H^{\perp}\subset G^{\perp}$。

#### Proof

(a) 设 $U\subset V$，则对任意 $u \in U$ 有 $\langle u,0 \rangle=0$，故 $0 \in U^{\perp}$。

如果 $v,w \in U^{\perp}$，那么 $\langle u,v+w \rangle=\langle u,v \rangle+\langle u,w \rangle=0$，故 $v+w \in U^{\perp}$。

如果 $v \in U^{\perp},\lambda \in \mathbb{F}$，那么 $\langle u,\lambda v \rangle=\overline{\lambda}\langle u,v \rangle=0$，故 $\lambda v \in U^{\perp}$。

综上，$U^{\perp}$ 是 $V$ 的一个子空间。

(b) 设 $v \in V$，则 $\langle 0,v \rangle=0$，因此 $v \in \{ 0 \}^{\perp}$，即证 $\{ 0 \}^{\perp}=V$。

(c) 如果 $v \in V^{\perp}$，那么 $\langle v,v \rangle=0$，从而 $v=0$，即证 $V^{\perp}=\{ 0 \}$。

(d) 设 $u \in U\cap U^{\perp}$，则 $\langle u,u \rangle=0$，从而 $u=0$，即 $U\cap U^{\perp}\subset \{ 0 \}$。

(e) 设 $v \in H^{\perp}$，则对任意 $u \in H$ 有 $\langle u,v \rangle=0$，从而对任意 $u \in G$ 有 $\langle u,v \rangle=0$，故 $v \in G^{\perp}$，即证 $H^{\perp}\subset G^{\perp}$。

### Theorem 6.34

设 $U$ 是 $V$ 的有限维子空间，则

$$
\begin{gather}
V=U\oplus U^{\perp}
\end{gather}
$$

#### Proof

根据 [[#Theorem 6.33]](d) 可知 $U\cap U^{\perp}=\{ 0 \}$，因此我们只需证明

$$
\begin{gather}
V=U+U^{\perp}
\end{gather}
$$

令 $e_{1},\dots,e_{m}$ 为 $U$ 的标准正交基，任取 $v \in V$，我们令

$$
\begin{gather}
u=\langle v,e_{1} \rangle e_{1}+\dots+\langle v,e_{m} \rangle e_{m}, \quad w=v-u
\end{gather}
$$

则

$$
\begin{gather}
\langle w,e_{k} \rangle =\langle v,e_{k} \rangle -\langle v,e_{k} \rangle =0
\end{gather}
$$

从而 $w$ 正交于 $\operatorname{span}(e_{1},\dots,e_{m})$，故 $w \in U^{\perp}$。因此我们将 $v$ 写成了 $v=u+w$，其中 $u \in U,w \in U^{\perp}$，这就完成了证明。

### Corollary 6.35

设 $V$ 是有限维的，$U$ 是 $V$ 的子空间，则

$$
\begin{gather}
\dim U^{\perp}=\dim V-\dim U
\end{gather}
$$

### Theorem 6.36

设 $U$ 是 $V$ 的有限维子空间，则

$$
\begin{gather}
U=(U^{\perp})^{\perp}
\end{gather}
$$

#### Proof

首先我们证明

$$
\begin{gather}
U\subset(U^{\perp})^{\perp}
\end{gather}
$$

设 $u \in U$，则对任意 $w \in U^{\perp}$ 有 $\langle u,w \rangle=0$，因此 $u$ 正交于 $U^{\perp}$ 中的所有向量，根据正交补的定义就有 $u \in(U^{\perp})^{\perp}$。

下面我们证明

$$
\begin{gather}
(U^{\perp})^{\perp}\subset U
\end{gather}
$$

设 $v \in(U^{\perp})^{\perp}$，根据直和分解 [[#Theorem 6.34]]，我们将 $v$ 写成 $v=u+w$，其中 $u \in U,w \in U^{\perp}$。于是 $v-u=w \in U^{\perp}$。

又由于 $U\subset(U^{\perp})^{\perp}$，故 $u \in(U^{\perp})^{\perp}$，从而 $v-u \in(U^{\perp})^{\perp}$，即 $v-u \in U^{\perp}\cap(U^{\perp})^{\perp}$，于是 $v-u=0$。这表明 $v=u \in U$，这就完成了证明。

### Corollary 6.37

设 $U$ 是 $V$ 的有限维子空间，则 $U^{\perp}=\{ 0 \}$ 当且仅当 $U=V$。

#### Proof

设 $U^{\perp}=\{ 0 \}$，则 $U=(U^{\perp})^{\perp}=\{ 0 \}^{\perp}=V$。

反之，如果 $U=V$，那么 $U^{\perp}=V^{\perp}=\{ 0 \}$。

### Definition 6.38 orthogonal projection 正交投影

设 $U$ 是 $V$ 的有限维子空间。$V$ 上向 $U$ 的正交投影 $P_{U}\in L(V)$ 定义如下：对任意 $v \in V$，有 $v=u+w$，其中 $u \in U,w \in U^{\perp}$，取 $P_{U}v=u$。

$V$ 的直和分解 $V=U\oplus U^{\perp}$ 保证了正交投影 $P_{U}$ 的良定性。$P_{U}$ 的线性性将在后面进行验证。

### Example 6.39

我们已经在之前见过了正交投影的特例，也就是向着一维子空间（直线）的投影。

设 $u \in V,u\neq 0$，令 $U$ 为一维子空间 $U=\operatorname{span}(u)$。如果 $v \in V$，那么

$$
\begin{gather}
v=\frac{\langle v,u \rangle }{\lVert u \rVert ^{2}}u+\left( v-\frac{\langle v,u \rangle }{\lVert u \rVert ^{2}}u \right)
\end{gather}
$$

其中等式右侧第一项属于 $U$，第二项正交于 $u$，从而属于 $U^{\perp}$。因此向着 $U$ 的正交投影为

$$
\begin{gather}
P_{U}v=\frac{\langle v,u \rangle }{\lVert u \rVert ^{2}}u= \left< v, \frac{u}{\lVert u \rVert } \right>  \frac{u}{\lVert u \rVert }
\end{gather}
$$

特别地，如果 $e$ 是一个单位向量（$\lVert e \rVert=1$），那么向着 $\operatorname{span}(e)$ 的正交投影就等价于与 $e$ 做内积：$P_{\operatorname{span}(e)}v=\langle v,e \rangle e$。

### Theorem 6.40

设 $U$ 是 $V$ 的有限维子空间，则

1. $P_{U}\in L(V)$，
2. 对 $u \in U$ 有 $P_{U}u=u$，
3. 对 $w \in U^{\perp}$ 有 $P_{U}w=0$，
4. $\operatorname{range}P_{U}=U$，
5. $\ker P_{U}=U^{\perp}$，
6. 对 $v \in V$ 有 $v-P_{U}v \in U^{\perp}$，
7. $P_{U}^{2}=P_{U}$，
8. 对 $v \in V$ 有 $\lVert P_{U}v \rVert\leq \lVert v \rVert$，
9. 如果 $e_{1},\dots,e_{m}$ 是 $U$ 的标准正交基，$v \in V$，则
$$
\begin{gather}
P_{U}v=\langle v,e_{1} \rangle e_{1}+\dots+\langle v,e_{m} \rangle e_{m}
\end{gather}
$$

#### Proof

(1) 设 $v_{1},v_{2}\in V$，有分解

$$
\begin{gather}
v_{1}=u_{1}+w_{1}, \quad v_{2}=u_{2}+w_{2}
\end{gather}
$$

其中 $u_{1},u_{2}\in U,w_{1},w_{2}\in U^{\perp}$，于是

$$
\begin{gather}
P_{U}(v_{1}+v_{2})=u_{1}+u_{2}=P_{U}v_{1}+P_{U}v_{2}
\end{gather}
$$

同理，

$$
\begin{gather}
P_{U}(\lambda v_{1})=\lambda u_{1}=\lambda P_{U}(v_{1})
\end{gather}
$$

因此 $P_{U}$ 是线性算子。

(2) $u \in U$ 有分解 $u=u+0$，其中 $u \in U,0 \in U^{\perp}$，于是 $P_{U}u=u$。

(3) $w \in U^{\perp}$ 有分解 $w=0+w$，其中 $0 \in U,w \in U^{\perp}$，故 $P_{U}w=0$。

(4) $P_{U}$ 的定义给出 $\operatorname{range}P_{U}\subset U$。对 $u \in U$，(2) 给出 $u=P_{U}u \in \operatorname{range}P_{U}$，因此 $\operatorname{range}P_{U}=U$。

(5) 命题 (3) 给出 $U^{\perp}\subset \ker P_{U}$。设 $v \in \ker P_{U}$，则 $P_{U}v=0$，故 $v$ 的分解必然是 $v=0+v$，其中 $v \in U^{\perp}$，即证 $\ker P_{U}=U^{\perp}$。

(6) $v \in V$ 有分解 $v=u+w$，其中 $u=P_{U}v \in U,w \in U^{\perp}$，于是 $v-P_{U}v=w \in U^{\perp}$。

(7) $v \in V$ 有分解 $v=u+w$，我们有

$$
\begin{gather}
P_{U}^{2}v=P_{U}u=u=P_{U}v
\end{gather}
$$

即证 $P_{U}^{2}=P_{U}$。

(8) 根据勾股定理有

$$
\begin{gather}
\lVert P_{U}v \rVert ^{2}=\lVert u \rVert ^{2}\leq \lVert u \rVert ^{2}+\lVert w \rVert ^{2}=\lVert v \rVert ^{2}
\end{gather}
$$

两边取平方根即证。

(9) 与 [[#Theorem 6.34]] 的证明同理可证。

在上一节我们证明了 Riesz 表示定理，它表明有限维内积空间上的线性泛函均形如与某个固定向量的内积。下面我们使用正交补的方法给出该定理的另一个证明，它提供了从另一个角度理解 Riesz 表示定理的方法。

### Theorem 6.41 (Riesz 表示定理)

设 $V$ 是有限维的。对任意 $v \in V$，定义 $\varphi_{v}\in V^{*}$ 为

$$
\begin{gather}
\varphi_{v}(u)=\langle u,v \rangle 
\end{gather}
$$

则 $v\mapsto\varphi_{v}$ 是从 $V$ 到 $V^{*}$ 的一个双射。

#### Proof

单射性与 [[#Theorem 6.30 (Riesz 表示定理)]] 中唯一性的证明方法相同。

满射性的证明思路如下：如果 $\varphi \in V^{*}$，$v \in V$，且对 $u \in V$ 有 $\varphi(u)=\langle u,v \rangle$，那么 $v \in(\ker\varphi)^{\perp}$，因为对任意 $u \in \ker\varphi$ 有 $\langle u,v \rangle=0$。然而，除了 $\varphi=0$ 的平凡情况外，$\dim \operatorname{range}\varphi=1$，从而 $\dim \ker\varphi=\dim V-1$，$\dim(\ker\varphi)^{\perp}=1$。因此我们只需选择 $(\ker\varphi)^{\perp}$ 中的一个非零向量，然后乘以一个适当的标量即可。

设 $\varphi \in V^{*}$，如果 $\varphi=0$，那么 $\varphi=\varphi_{0}$。于是我们可以假设 $\varphi\neq 0$，从而 $(\ker\varphi)^{\perp}\neq \{ 0 \}$。

取 $w \in(\ker\varphi)^{\perp}$ 满足 $w\neq 0$，设

$$
\begin{gather}
v=\frac{\overline{\varphi(w)}}{\lVert w \rVert ^{2}}w
\end{gather}
$$

则 $v \in(\ker\varphi)^{\perp}$ 且 $v\neq 0$，因为 $w \not\in \ker\varphi$。

两边取范数得

$$
\begin{gather}
\lVert v \rVert =\frac{\lvert \varphi(w) \rvert }{\lVert w \rVert }
\end{gather}
$$

此外，我们还有

$$
\begin{gather}
\varphi(v)=\frac{\lvert \varphi(w) \rvert ^{2}}{\lVert w \rVert ^{2}}=\lVert v \rVert ^{2}
\end{gather}
$$

现在设 $u \in V$，则它有分解

$$
\begin{gather}
u=\left( u-\frac{\varphi(u)}{\varphi(v)}v \right)+\frac{\varphi(u)}{\lVert v \rVert ^{2}}v
\end{gather}
$$

其中括号内的项属于 $\ker\varphi$，从而正交于 $v$。因此我们有

$$
\begin{gather}
\langle u,v \rangle =\frac{\varphi(u)}{\lVert v \rVert ^{2}}\langle v,v \rangle =\varphi(u)
\end{gather}
$$

即 $\varphi=\varphi_{v}$，这就完成了证明。

## Minimization Problems

如下的问题在应用中反复出现：给定 $V$ 的子空间 $U$ 以及 $v \in V$，找到一个 $u \in U$ 使得 $\lVert v-u \rVert$ 尽可能小。这类问题通常称为“最小化问题”，而如下的定理表明 $v$ 在 $U$ 上的正交投影 $P_{U}v$ 就是最小化问题的解。这一最小化问题的解法极为简洁，因而使得内积空间在纯数学之外得到了许多重要的应用。

### Theorem 6.42

设 $U$ 是 $V$ 的有限维子空间，$v \in V,u \in U$，则

$$
\begin{gather}
\lVert v-P_{U}v \rVert \leq \lVert v-u \rVert 
\end{gather}
$$

并且等式成立当且仅当 $u=P_{U}v$。

#### Proof

我们有

$$
\begin{align}
\lVert v-P_{U}v \rVert ^{2} &\leq \lVert v-P_{U}v \rVert ^{2}+\lVert P_{U}v-u \rVert ^{2} \\
&=\lVert (v-P_{U}v)+(P_{U}v-u) \rVert ^{2} \\
&=\lVert v-u \rVert ^{2}
\end{align}
$$

其中我们用到了勾股定理：$v-P_{U}v \in U^{\perp}$，$P_{U}v-u \in U$，它们的内积为零。此外，显然当 $u=P_{U}v$ 时等式成立，反之，当等式成立时有 $\lVert P_{U}v-u \rVert^{2}=0$，即 $P_{U}v=u$。

以上定理通常与 [[#Theorem 6.40]](9) 结合以给出最小化问题的显式答案，如下例所示。

### Example 6.43

假设我们想要用次数不超过 $5$ 的多项式 $u(x)$ 来在区间 $[-\pi,\pi]$ 上近似正弦函数 $\sin x$，使得

$$
\begin{gather}
\int_{-\pi}^{\pi} \lvert \sin x-u(x) \rvert ^{2} \, \mathrm{d}x
\end{gather}
$$

最小。令 $C([-\pi,\pi],\mathbb{R})$ 表示 $[-\pi,\pi]$ 上的实值连续函数空间，配备有内积

$$
\begin{gather}
\langle f,g \rangle =\int_{-\pi}^{\pi} fg
\end{gather}
$$

令 $v \in C([-\pi,\pi],\mathbb{R})$ 为 $v(x)=\sin x$，$U$ 是 $C([-\pi,\pi],\mathbb{R})$ 的由次数小于等于 $5$ 的多项式构成的子空间，则我们的问题就转化为了一个最小化问题：找到 $u \in U$ 使得 $\lVert v-u \rVert$ 最小。

要求解这一问题，我们首先给出 $U$ 上的一个标准正交基。对 $\mathcal{P}_{5}(\mathbb{R})$ 的标准基 $1,x,x^{2},x^{3},x^{4},x^{5}$ 应用 Gram-Schmidt 过程，得到一个标准正交基 $e_{1},\dots,e_{6}$，然后我们可以计算

$$
\begin{gather}
P_{U}v=\langle v,e_{1} \rangle e_{1}+\dots+\langle v,e_{6} \rangle e_{6}
\end{gather}
$$

计算机给出了如下数值解：

$$
\begin{gather}
u(x)=0.987862x − 0.155271x^{3} + 0.00564312x^{5}
\end{gather}
$$

要看出这个解的近似效果有多好，我们可以画出 $\sin x$ 与 $u(x)$ 的图像以进行比较：

![](6-4.png)

可见，$u(x)$ 除了在 $-\pi$ 和 $\pi$ 附近有偏差外，其余部分的图像几乎与 $\sin x$ 的图像重合了。与之相对，$\sin x$ 的 Taylor 多项式与 $\sin x$ 的图像的比较如下：

![](6-5.png)

可以看出 Taylor 多项式在 $\lvert x \rvert>\pi /2$ 处有明显的偏差。

## Pseudoinverse

设 $T \in L(V,W)$ 且 $w \in W$，线性代数中的一个重要问题是找到 $v \in V$ 使得

$$
\begin{gather}
Tv=w
\end{gather}
$$

例如，如果 $V=\mathbb{F}^{n}$ 且 $W=\mathbb{F}^{m}$，那么以上方程可以表示一个含有 $m$ 个方程和 $n$ 个未知数 $v_{1},\dots,v_{n}$ 的线性方程组。

如果 $T$ 是可逆的，那么以上方程有唯一解 $v=T^{-1}w$。然而，如果 $T$ 不可逆，那么对某些 $w$，方程无解，而对另一些 $w$，方程有无穷多解。

不过，如果 $V,W$ 上配备了内积，那么我们仍然可以在 $T$ 不可逆时给出一个最佳的答案。例如，如果 $Tv=w$ 无解，那么我们可以尝试找到 $v \in V$ 使得 $\lVert Tv-w \rVert$ 尽可能小。或者，如果 $Tv=w$ 有无穷多解，那么我们可以尝试找到一个解使得 $\lVert v \rVert$ 最小。

能够给出以上问题答案的就是本节要介绍的 Moore-Penrose 伪逆。

### Theorem 6.44

设 $V$ 是有限维的且 $T \in L(V,W)$，则 $T|_{(\ker T)^{\perp}}$ 是从 $(\ker T)^{\perp}$ 到 $\operatorname{range}T$ 的线性同构。

#### Proof

设 $v \in(\ker T)^{\perp}$ 且 $T|_{(\ker T)^{\perp}}v=0$，则 $v \in \ker T$，于是 $v \in \ker T\cap(\ker T)^{\perp}$，因此 $v=0$。这表明 $T|_{(\ker T)^{\perp}}$ 是单射。

显然 $\operatorname{range}(T|_{(\ker T)^{\perp}})\subset \operatorname{range}T$。设 $w \in \operatorname{range}T$，则存在 $v \in V$ 使得 $Tv=w$。根据直和分解 $V=\ker T\oplus(\ker T)^{\perp}$，我们有 $v=u+x$，其中 $u \in \ker T,x \in(\ker T)^{\perp}$，并且

$$
\begin{gather}
T|_{(\ker T)^{\perp}}x=Tx=Tv-Tu=w-0=w
\end{gather}
$$

故 $w \in \operatorname{range}(T|_{(\ker T)^{\perp}})$，这就完成了证明。

该定理保证了伪逆的存在性。

### Definition 6.45 Moore-Penrose pseudoinverse

设 $V$ 是有限维的，$T \in L(V,W)$。$T$ 的 Moore-Penrose 伪逆 $T^{\dagger}\in L(W,V)$ 定义为

$$
\begin{gather}
T^{\dagger}=(T|_{(\ker T)^{\perp}})^{-1}P_{\operatorname{range}T}
\end{gather}
$$

其中 $P_{\operatorname{range}T}$ 是向着 $\operatorname{range}T$ 的正交投影。

根据正交投影的性质，如果 $w \in(\operatorname{range}T)^{\perp}$，那么 $T^{\dagger}w=0$；如果 $w \in \operatorname{range}T$，那么 $T^{\dagger}w$ 是 $(\ker T)^{\perp}$ 中唯一使得 $T(T^{\dagger}w)=w$ 的元素。

### Theorem 6.46

设 $V$ 是有限维的且 $T \in L(V,W)$。

(a) 如果 $T$ 是可逆的，那么 $T^{\dagger}=T^{-1}$。
(b) $TT^{\dagger}=P_{\operatorname{range}T}$ 为 $\operatorname{range}T$ 上的正交投影。
(c) $T^{\dagger}T=P_{(\ker T)^{\perp}}$ 为 $(\ker T)^{\perp}$ 上的正交投影。

#### Proof

(a) 如果 $T$ 可逆，那么 $(\ker T)^{\perp}=V$，$\operatorname{range}T=W$，因此 $T|_{(\ker T)^{\perp}}=T$ 且 $P_{\operatorname{range}T}$ 是 $W$ 上的恒等映射，即证 $T^{\dagger}=T^{-1}$。

(b) 设 $w \in \operatorname{range}T$，则

$$
\begin{gather}
TT^{\dagger}w=T(T|_{(\ker T)^{\perp}})^{-1}w=w=P_{\operatorname{range}T} w
\end{gather}
$$

如果 $w \in(\operatorname{range}T)^{\perp}$，那么 $TT^{\dagger}w=0=P_{\operatorname{range}T}w$。由于

$$
\begin{gather}
W=\operatorname{range}T\oplus (\operatorname{range}T)^{\perp}
\end{gather}
$$

且 $TT^{\dagger}$ 与 $P_{\operatorname{range}T}$ 分别在两个直和项上相等，故它们也在 $W$ 上相等。

(c) 设 $v \in(\ker T)^{\perp}$，则

$$
\begin{gather}
T^{\dagger}(Tv)=(T|_{(\ker T)^{\perp}})^{-1}(Tv)=v=P_{(\ker T)^{\perp}}v
\end{gather}
$$

如果 $v \in \ker T$，那么 $T^{\dagger}Tv=0=P_{(\ker T)^{\perp}}v$。同样根据直和分解可知 $T^{\dagger}T$ 与 $P_{(\ker T)^{\perp}}$ 在 $V$ 上相等。

由 (b) 可知，如果 $T$ 是满射，那么 $TT^{\dagger}$ 是 $W$ 上的恒等映射。同理由 (c) 可知，如果 $T$ 是单射，那么 $T^{\dagger}T$ 是 $V$ 上的恒等映射。

我们回到本节开头的问题：找到方程

$$
\begin{gather}
Tv=w
\end{gather}
$$

的解，或者当无解时给出一个最佳近似。之前说过，如果 $T$ 可逆，那么 $v=T^{-1}w$ 就是唯一解。然而当 $T$ 不可逆时，$T^{-1}$ 不存在，但此时我们可以定义伪逆 $T^{\dagger}$，取 $v=T^{\dagger}w$ 就给出了一个最佳近似，如下定理 (a) 所示。

进一步，在所有满足 $Tv=w$ 的 $v$ 中，$T^{\dagger}w$ 的范数是最小的，这一性质由如下定理 (b) 所示。

### Theorem 6.47

设 $V$ 是有限维的，$T \in L(V,W)$，且 $w \in W$。

(a) 如果 $v \in V$，则

$$
\begin{gather}
\lVert T(T^{\dagger}w)-w \rVert \leq \lVert Tv-w \rVert 
\end{gather}
$$

等式成立当且仅当 $v \in T^{\dagger}w+\ker T$。

(b) 如果 $v \in T^{\dagger}w+\ker T$，那么

$$
\begin{gather}
\lVert T^{\dagger}w \rVert \leq \lVert v \rVert 
\end{gather}
$$

等式成立当且仅当 $v=T^{\dagger}w$。

#### Proof

(a) 设 $v \in V$，则

$$
\begin{gather}
Tv-w=(Tv-TT^{\dagger}w)+(TT^{\dagger}w-w)
\end{gather}
$$

其中等式右侧第一项属于 $\operatorname{range}T$，第二项属于 $(\operatorname{range}T)^{\perp}$，因为 $TT^{\dagger}=P_{\operatorname{range}T}$。因此，勾股定理表明

$$
\begin{gather}
\lVert Tv-w \rVert ^{2}=\lVert Tv-TT^{\dagger}w \rVert ^{2}+\lVert TT^{\dagger}w-w \rVert ^{2}\geq \lVert TT^{\dagger}w-w \rVert ^{2}
\end{gather}
$$

等式成立当且仅当 $Tv=TT^{\dagger}w$，即 $v-T^{\dagger}w \in \ker T$，或者 $v \in T^{\dagger}w+\ker T$。

(b) 设 $v \in T^{\dagger}w+\ker T$，则

$$
\begin{gather}
v=(v-T^{\dagger}w)+T^{\dagger}w
\end{gather}
$$

其中 $v-T^{\dagger}w\in \ker T,T^{\dagger}w \in(\ker T)^{\perp}$，因此

$$
\begin{gather}
\lVert v \rVert ^{2}=\lVert v-T^{\dagger}w \rVert ^{2}+\lVert T^{\dagger}w \rVert ^{2}\geq \lVert T^{\dagger}w \rVert ^{2}
\end{gather}
$$

等式成立当且仅当 $v=T^{\dagger}w$。

下一章我们将利用 SVD 给出伪逆的一个计算公式。