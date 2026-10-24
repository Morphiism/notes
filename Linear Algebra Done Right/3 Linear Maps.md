目前为止我们一直在研究向量空间。然而，重要的部分并非对象——向量空间，而是对象之间的态射——线性映射。本章的一个核心定理是秩-零化度定理，它允许我们证明有限维空间上的线性映射是单射当且仅当它是满射。在这之后我们将介绍矩阵，它是连接抽象向量空间与线性方程组的桥梁。

在本章中，我们将使用符号 $U,V,W$ 来表示 $\mathbb{F}$-向量空间。

# 3A Vector Space of Linear Maps

## Definition and Examples of Linear Maps

### Definition 3.1 linear map 线性映射

从 $V$ 到 $W$ 的一个线性映射是一个函数 $T\colon V\to W$ 满足如下性质：

1. 加性：对任意 $u,v \in V$ 有 $T(u+v)=Tu+Tv$。
2. 齐次性：对任意 $\lambda \in \mathbb{F}$ 和 $v \in V$ 有 $T(\lambda v)=\lambda Tv$。

所有从 $V$ 到 $W$ 的线性映射构成的集合记作 $L(V,W)$。

从 $V$ 到 $V$ 的线性映射称为 $V$ 上的线性算子，我们记 $L(V)=L(V,V)$。

### Example 3.2

(a) 我们用 $0$ 来表示值恒为零的线性映射：

$$
\begin{gather}
0v=0
\end{gather}
$$

其中我们将左边的 $0$ 视为 $L(V,W)$ 中的一个元素，右边的 $0$ 为 $W$ 上的加法单位元。

(b) 我们定义 $V$ 上的恒等算子 $I \in L(V)$ 为

$$
\begin{gather}
Iv=v \quad (v \in V)
\end{gather}
$$

(c) $\mathcal{P}(\mathbb{R})$ 上的微分算子

$$
\begin{gather}
Dp=p' \quad (p \in \mathcal{P}(\mathbb{R}))
\end{gather}
$$

满足 $D \in L(\mathcal{P}(\mathbb{R}))$，因为导数运算满足线性性：$(p+q)'=p'+q'$，$(\lambda p)'=\lambda p'$。

(d) 同样，由于积分运算也是线性的，故定义为

$$
\begin{gather}
Tp=\int_{0}^{1} p
\end{gather}
$$

的 $T \in L(\mathcal{P}(\mathbb{R}),\mathbb{R})$。

(e) 定义为

$$
\begin{gather}
(Tp)(x)=x^{2}p(x) \quad (x \in \mathbb{R})
\end{gather}
$$

的 $T \in L(\mathcal{P}(\mathbb{R}))$。

(f) 定义为

$$
\begin{gather}
T(x_{1},x_{2},x_{3},\dots)=(x_{2},x_{3},\dots)
\end{gather}
$$

的 $T \in L(\mathbb{F}^{\infty})$，它被称为后移位算子。

(g) 设 $m,n$ 是正整数，取 $A_{j,k}\in \mathbb{F}$，$1\leq j\leq m,1\leq k\leq n$，则我们可以定义 $T \in L(\mathbb{F}^{n},\mathbb{F}^{m})$ 为

$$
\begin{gather}
T(x_{1},\dots,x_{n})=(A_{1,1}x_{1}+\dots+A_{1,n}x_{n},\dots,A_{m,1}x_{1}+\dots+A_{m,n}x_{n})
\end{gather}
$$

事实上，任何 $T \in L(\mathbb{F}^{n},\mathbb{F}^{m})$ 都可以写成以上形式。

(h) 固定多项式 $q \in \mathcal{P}(\mathbb{R})$，则定义为

$$
\begin{gather}
(Tp)(x)=p(q(x))
\end{gather}
$$

的 $T \in L(\mathcal{P}(\mathbb{R}))$。

### Theorem 3.3

设 $v_{1},\dots,v_{n}$ 是 $V$ 的基，$w_{1},\dots,w_{n} \in W$，则存在唯一的 $T\in L(V,W)$ 使得

$$
\begin{gather}
Tv_{k}=w_{k} \quad (1\leq k\leq n)
\end{gather}
$$

换句话说，通过选取基向量的取值，我们可以完全确定一个线性映射。

#### Proof

首先我们证明唯一性。设 $T \in L(V,W)$ 满足 $Tv_{k}=w_{k}$，则 $T$ 的齐次性表明对任意 $c_{k}\in \mathbb{F}$ 有 $T(c_{k}v_{k})=c_{k}T(v_{k})=c_{k}w_{k}$，并且由 $T$ 的加性可得

$$
\begin{gather}
T(c_{1}v_{1}+\dots+c_{n}v_{n})=c_{1}w_{1}+\dots+c_{n}w_{n}
\end{gather}
$$

因此 $T$ 在 $\operatorname{span}(v_{1},\dots,v_{n})$ 上由上式唯一确定。但 $v_{1},\dots,v_{n}$ 是 $V$ 的基，故 $T$ 在 $V$ 上唯一确定。

下面我们证明存在性。任取 $v \in V$，则它存在唯一表示

$$
\begin{gather}
v=c_{1}v_{1}+\dots+c_{n}v_{n}
\end{gather}
$$

参考唯一性论证，我们定义 $T\colon V\to W$ 为

$$
\begin{gather}
T(v)=c_{1}w_{1}+\dots+c_{n}w_{n}
\end{gather}
$$

显然我们有 $Tv_{k}=w_{k}$，取 $c_{k}=1$，其他 $c$ 为零即可。

现设 $u,v \in V$，则有 $u=\sum a_{i}v_{i},v=\sum c_{i}v_{i}$，对任意 $\lambda,\mu \in \mathbb{F}$ 有

$$
\begin{align}
T(\lambda u+\mu v) &= T\left( \sum(\lambda a_{i}+\mu c_{i})v_{i} \right) \\
&=\sum(\lambda a_{i}+\mu c_{i})w_{i} \\
&=\lambda \sum a_{i}w_{i}+\mu \sum c_{i}w_{i} \\
&=\lambda Tu+\mu Tv
\end{align}
$$

从而 $T$ 是线性映射。

## Algebraic Operations on $L(V,W)$

### Definition 3.4

设 $S,T \in L(V,W)$ 且 $\lambda \in \mathbb{F}$，对任意 $v \in V$，我们定义 $L(V,W)$ 上的加法和数乘为

$$
\begin{gather}
(S+T)(v)=Sv+Tv, \quad (\lambda T)(v)=\lambda Tv
\end{gather}
$$

参照 $\mathbb{F}^{S}$ 上向量空间结构的定义，如下的结果应当不会让人意外。

### Theorem 3.5

$L(V,W)$，连带着其上的加法的数乘，构成了一个 $\mathbb{F}$-向量空间。

### Definition 3.6 product 乘积

设 $T \in L(U,V),S \in L(V,W)$，我们定义线性映射的乘积 $ST \in L(U,W)$ 为它们的复合：

$$
\begin{gather}
(ST)(u)=S(Tu) \quad (u \in U)
\end{gather}
$$

### Theorem 3.7

(a) 结合律：$(T_{1}T_{2})T_{3}=T_{1}(T_{2}T_{3})$。
(b) 单位元：对任意 $T \in L(V,W)$ 有 $IT=TI$，其中等式左边的 $I$ 是 $W$ 上的恒等算子，右边的 $I$ 是 $V$ 上的恒等算子。
(c) 分配律：对任意 $T,T_{1},T_{2}\in L(U,V)$ 和 $S,S_{1},S_{2}\in L(V,W)$ 有

$$
\begin{gather}
(S_{1}+S_{2})T=S_{1}T+S_{2}T, \quad S(T_{1}+T_{2})=ST_{1}+ST_{2}
\end{gather}
$$

#### Proof

(a) 就是函数复合的结合律。(b) 和 (c) 取 $v \in V$ 或者 $u \in U$ 然后验证等式两边给出同一个值即可。

### Example 3.8

线性映射的乘法是不交换的，意味着一般来说，$ST\neq TS$。例如，设 $D$ 为 $\mathcal{P}(\mathbb{R})$ 上的微分算子，$T$ 为 $\mathcal{P}(\mathbb{R})$ 上乘以 $x^{2}$ 的映射，则

$$
\begin{gather}
(TDp)(x)=x^{2}p'(x) \quad (DTp)(x)=x^{2}p'(x)+2xp(x)
\end{gather}
$$

因此 $TD\neq DT$。

### Theorem 3.9

设 $T \in L(V,W)$，则 $T(0)=0$。

#### Proof

利用加性，我们有

$$
\begin{gather}
T(0)=T(0+0)=T(0)+T(0)
\end{gather}
$$

两边加上 $T(0)$ 的加法逆元即得 $T(0)=0$。

设 $m,b \in \mathbb{R}$，则定义为

$$
\begin{gather}
f(x)=mx+b
\end{gather}
$$

的函数 $f\colon \mathbb{R}\to \mathbb{R}$ 是一个线性映射当且仅当 $b=0$。因此通常来说，所谓的“线性函数”不一定就是线性映射。

# 3B Null Spaces and Ranges

## Null Space and Injectivity

### Definition 3.10 null space (kernel) 零空间（核）

对于 $T \in L(V,W)$，它的零空间或核，定义为

$$
\begin{gather}
\ker T=\{ v \in V : Tv=0 \}
\end{gather}
$$

### Example 3.11

(a) 如果 $T$ 是 $L(V,W)$ 中的零映射，那么 $\ker T=V$。

(b) 微分算子 $D\in L(\mathcal{P}(\mathbb{R}))$ 的零空间为满足 $Dp=p'=0$ 的 $p$ 的集合，即 $\mathbb{R}$ 上的常值函数。

(c) 设 $T \in L(\mathcal{P}(\mathbb{R}))$ 定义为 $(Tp)(x)=x^{2}p(x)$，唯一使得 $x^{2}p(x)=0$ 的多项式为 $p=0$，因此 $\ker T=\{ 0 \}$。

(d) 设 $T \in L(\mathbb{F}^{\infty})$ 是后移位算子

$$
\begin{gather}
T(x_{1},x_{2},x_{3},\dots)=(x_{2},x_{3},\dots)
\end{gather}
$$

则 $\ker T=\{ (a,0,0,\dots) \in \mathbb{F}^{\infty}: a \in \mathbb{F} \}$。

注意到，$\ker T$ 似乎总是 $V$ 的一个子空间，下面我们证明这并非巧合。

### Theroem 3.12

设 $T \in L(V,W)$，则 $\ker T$ 是 $V$ 的一个子空间。

#### Proof

由于 $T(0)=0$，故 $0 \in \ker T$。

设 $u,v \in \ker T,\lambda,\mu \in \mathbb{F}$，则

$$
\begin{gather}
T(\lambda u+\mu v)=\lambda Tu+\mu Tv=\lambda 0+\mu 0=0
\end{gather}
$$

因此 $\ker T$ 关于加法和数乘封闭，从而是 $V$ 的子空间。

### Definition 3.13 injective 单射的

称函数 $T\colon V\to W$ 是单射的，如果 $u\neq v$ 蕴含 $Tu\neq Tv$。

取逆否命题，则 $T$ 是单射的，如果 $Tu=Tv$ 蕴含 $u=v$。

### Theorem 3.14

设 $T \in L(V,W)$，则 $T$ 是单射的当且仅当 $\ker T=\{ 0 \}$。

#### Proof

首先设 $T$ 是单射的。我们已有 $\{ 0 \}\subset \ker T$，下面我们要证反向的包含。

设 $u \in \ker T$，则 $Tu=T(0)=0$，单射性给出 $u=0$，故 $\ker T\subset \{ 0 \}$。

现设 $\ker T=\{ 0 \}$，设 $Tu=Tv$，则 $T(u-v)=0$，即 $u-v \in \ker T$，从而 $u-v=0$，即 $u=v$。换句话说，$T$ 是单射的。

## Range and Surjectivity

### Definition 3.15 range 值域

对于 $T \in L(V,W)$，则它的值域定义为

$$
\begin{gather}
\operatorname{range}T=\{ Tv \in W : v \in V \}
\end{gather}
$$

尽管我们对线性映射定义了值域，但以上定义对任何函数都适用。

### Example 3.16

(a) 如果 $T \in L(V,W)$ 是零映射，则 $\operatorname{range}T=\{ 0 \}$。

(b) 微分算子 $D \in L(\mathcal{P}(\mathbb{R}))$ 的值域是 $\mathcal{P}(\mathbb{R})$，因为多项式的原函数仍然是多项式，即，对任意多项式 $q$，存在 $p \in \mathcal{P}(\mathbb{R})$ 使得 $p'=q$。

和零空间一样，值域也是 $W$ 的一个子空间。

### Theorem 3.17

设 $T\in L(V,W)$，则 $\operatorname{range}T$ 是 $W$ 的子空间。

#### Proof

由于 $T(0)=0$，故 $0 \in \operatorname{range}T$。

设 $w_{1},w_{2} \in \operatorname{range}T,\lambda,\mu \in \mathbb{F}$，则存在 $v_{1},v_{2}\in V$ 使得 $Tv_{j}=w_{j}$。从而我们有

$$
\begin{gather}
\lambda w_{1}+\mu w_{2}=\lambda Tv_{1}+\mu Tv_{2}=T(\lambda v_{1}+\mu v_{2}) \in \operatorname{range}T
\end{gather}
$$

因此 $\operatorname{range}T$ 关于加法和数乘封闭，从而是一个子空间。

### Definition 3.18

称函数 $T\colon V\to W$ 是满射的，如果 $\operatorname{range}T=W$。

具体来说，$T$ 是满射的，如果对任意 $w \in W$，存在 $v \in V$ 使得 $Tv=w$。

### Example 3.19

需要注意的是，函数的满射性依赖于函数的陪域（codomain）$W$。例如，微分算子 $D$ 作为 $\mathcal{P}_{5}(\mathbb{R})$ 到 $\mathcal{P}_{5}(\mathbb{R})$ 的函数并非满射的，因为 $x^{5}$ 不在 $\operatorname{range}D$ 中。但 $D$ 作为 $\mathcal{P}_{5}(\mathbb{R})$ 到 $\mathcal{P}_{4}(\mathbb{R})$ 的函数是满射的。

## Fundamental Theorem of Linear Maps

下面的定理是有限维空间上线性映射的核心定理，它也被称为“线性映射基本定理”。

### Theorem 3.20 (秩-零化度定理)

设 $V$ 是有限维向量空间，$T \in L(V,W)$，则 $\operatorname{range}T$ 是有限维的，并且

$$
\begin{gather}
\dim V=\dim \ker T+\dim \operatorname{range}T
\end{gather}
$$

其中 $\dim \ker T$ 称为 $T$ 的零化度（nullity），$\dim \operatorname{range}T$ 称为 $T$ 的秩（rank）。

#### Proof

设 $u_{1},\dots,u_{m}$ 是 $\ker T$ 的基，则 $\dim \ker T=m$。我们将其扩张为 $V$ 的一个基

$$
\begin{gather}
u_{1},\dots,u_{m},v_{1},\dots,v_{n}
\end{gather}
$$

则 $\dim V=m+n$。下面我们只需证明 $\operatorname{range}T$ 是有限维的，并且 $\dim \operatorname{range}T=n$。我们通过证明 $Tv_{1},\dots,Tv_{n}$ 是 $\operatorname{range}T$ 的基来证明这一点。

设 $v \in V$，则我们有

$$
\begin{gather}
v=a_{1}u_{1}+\dots+a_{m}u_{m}+b_{1}v_{1}+\dots+b_{n}v_{n}
\end{gather}
$$

从而

$$
\begin{gather}
Tv=b_{1}Tv_{1}+\dots+b_{n}Tv_{n}
\end{gather}
$$

因此 $Tv_{1},\dots,Tv_{n}$ 张成 $\operatorname{range}T$。因此 $\operatorname{range}T$ 是有限维的。

设

$$
\begin{gather}
c_{1}Tv_{1}+\dots+c_{n}Tv_{n}=0
\end{gather}
$$

则

$$
\begin{gather}
T(c_{1}v_{1}+\dots+c_{n}v_{n})=0 \implies \sum c_{i}v_{i} \in \ker T
\end{gather}
$$

于是

$$
\begin{gather}
c_{1}v_{1}+\dots+c_{n}v_{n}=d_{1}u_{1}+\dots+d_{m}u_{m}
\end{gather}
$$

而 $v_{1},\dots,v_{n},u_{1},\dots,u_{m}$ 线性无关，因此所有 $c$ 均为零，故 $Tv_{1},\dots,Tv_{n}$ 线性无关，从而是 $\operatorname{range}T$ 的基。

### Theorem 3.21

设 $V,W$ 是有限维向量空间，满足 $\dim V>\dim W$，则任意 $T \in L(V,W)$ 都不是单射。

换句话说，不存在从高维空间到低维空间的单线性映射。

#### Proof

$T$ 是单射的当且仅当 $\dim \ker T=0$（[[#Theorem 3.14]]），而

$$
\begin{align}
\dim \ker T &= \dim V-\dim \operatorname{range}T \\
&> \dim V-\dim W \\
&> 0
\end{align}
$$

因此任意 $T \in L(V,W)$ 都不是单射。

### Theorem 3.22

设 $V,W$ 是有限维向量空间，满足 $\dim V<\dim W$，则任意 $T \in L(V,W)$ 都不是满射。

换句话说，不存在从低维空间到高维空间的满射。

#### Proof

$T$ 是满射的当且仅当 $\dim \operatorname{range}T=\dim W$（[[2 Finite Dimensional Vector Spaces#Theorem 2.29]]），但

$$
\begin{align}
\dim \operatorname{range}T&=\dim V-\dim \ker T \\
&\leq \dim V \\
&<\dim W
\end{align}
$$

因此任意 $T \in L(V,W)$ 都不是满射。

[[#Theorem 3.21]] 与 [[#Theorem 3.22]] 在线性方程组理论中具有重要意义，这是因为我们可以将关于线性方程组的结论转换为线性映射 $T \in L(\mathbb{F}^{n},\mathbb{F}^{m})$ 的结论。

设 $m,n$ 是正整数，对于 $1\leq j\leq m,1\leq k\leq n$，令 $A_{j,k}\in \mathbb{F}$。考虑如下的齐次线性方程组：

$$
\begin{gather}
A_{1,1}x_{1}+\dots+A_{1,n}x_{n}=0 \\
\vdots \\
A_{m,1}x_{1}+\dots+A_{m,n}x_{n}=0
\end{gather}
$$

显然 $x_{1}=\dots=x_{n}=0$ 是方程的一个解，称为零解。我们要问的是是否还存在其他非零解？

定义 $T\colon \mathbb{F}^{n}\to \mathbb{F}^{m}$ 为

$$
\begin{gather}
T(x_{1},\dots,x_{n})=\left( \sum_{j=1}^{n} A_{1,j}x_{j},\dots,\sum_{j=1}^{n} A_{m,j}x_{j} \right)
\end{gather}
$$

则方程 $T(x_{1},\dots,x_{n})=0$ 就等价于上面的齐次方程组。换言之，我们要问的是 $\ker T$ 是否严格地大于 $\{ 0 \}$，也即 $T$ 是否是一个单射。利用前面证明的两个定理，我们可以给出如下结论。

### Theorem 3.23

如果一个齐次线性方程组的未知量个数大于方程个数，那么方程组有非零解。

#### Proof

定义 $T\colon \mathbb{F}^{n}\to \mathbb{F}^{m}$ 如上所示，则我们有 $n>m$，从而由 [[#Theorem 3.21]] 知 $T$ 不是单射，即 $\ker T\neq \{ 0 \}$，因此方程组有非零解。

另一个类似的定理涉及非齐次方程组以及满射性。考虑方程组

$$
\begin{gather}
A_{1,1}x_{1}+\dots+A_{1,n}x_{n}=c_{1} \\
\vdots \\
A_{m,1}x_{1}+\dots+A_{m,n}x_{n}=c_{m}
\end{gather}
$$

我们要问的是，是否存在常数 $c_{1},\dots,c_{m}\in \mathbb{F}$，使得方程组无解？

定义 $T\colon \mathbb{F}^{n}\to \mathbb{F}^{m}$ 如上所示，则方程组就等价于方程

$$
\begin{gather}
T(x_{1},\dots,x_{n})=(c_{1},\dots,c_{m})
\end{gather}
$$

因此我们要问的是是否有 $\operatorname{range}T=\mathbb{F}^{m}$。也即，$T$ 是否是一个满射。

### Theorem 3.24

如果一个线性方程组的方程个数大于未知量个数，那么存在一种常数项的选取，使得方程组无解。

#### Proof

取 $T\colon \mathbb{F}^{n}\to \mathbb{F}^{m}$ 如上所示，则 $n<m$，从而由 [[#Theorem 3.22]] 知 $T$ 不是满射，从而 $\operatorname{range}T\neq \mathbb{F}^{m}$。这就是说，存在 $c \in \mathbb{F}^{m}$ 使得方程 $T(x)=c$ 无解。

# 3C Matrices

## Representing a Linear Map by a Matrix

我们知道，如果 $v_{1},\dots,v_{n}$ 是 $V$ 的基，那么 $Tv_{1},\dots,Tv_{n}$ 唯一确定了线性映射 $T$ 在 $V$ 上的取值（[[#Theorem 3.3]]）。矩阵提供了一种有效的方法来记录 $Tv_{1},\dots,Tv_{n}$ 在 $W$ 的基下的坐标。

### Definition 3.25 matrix 矩阵

设 $m,n$ 是正整数，一个 $m\times n$ 矩阵 $A$ 是一个排成 $m$ 行 $n$ 列的数组

$$
\begin{gather}
A=\begin{pmatrix}
A_{1,1} & \cdots & A_{1,n} \\
\vdots & \ddots & \vdots \\
A_{m,1} & \cdots & A_{m,n}
\end{pmatrix}
\end{gather}
$$

其中 $A_{j,k}\in \mathbb{F}$。

### Definition 3.26

设 $T \in L(V,W)$，$v_{1},\dots,v_{n}$ 是 $V$ 的基，$w_{1},\dots,w_{m}$ 是 $W$ 的基。$T$ 关于这些基的矩阵是一个 $m\times n$ 矩阵 $\mathcal{M}(T,(v_{1},\dots,v_{n}),(w_{1},\dots,w_{m}))$，其 $j$ 行 $k$ 列的元素 $A_{j,k}$ 定义为

$$
\begin{gather}
Tv_{k}=A_{1,k}w_{1}+\dots+A_{m,k}w_{m}
\end{gather}
$$

如果基在上下文中是明确的，我们可以将 $T$ 的矩阵记为 $\mathcal{M}(T)$。

![](3-1.png)

如果 $T$ 是一个从 $\mathbb{F}^{n}$ 到 $\mathbb{F}^{m}$ 的线性映射，那么除非特别指定，我们均取两个向量空间上的标准基。此时，如果我们将 $\mathbb{F}^{m}$ 中的元素与矩阵的一列等同，那么 $\mathcal{M}(T)$ 的第 $k$ 列就是 $Te_{j}$，其中 $e_{j}=(0,\dots,0,1,0,\dots,0)$ 是仅在第 $j$ 个坐标为 $1$ 的向量。

### Example 3.27

(a) 定义 $T \in L(\mathbb{F}^{2},\mathbb{F}^{3})$ 为

$$
\begin{gather}
T(x,y)=(x+3y,2x+5y,7x+9y)
\end{gather}
$$

则 $T(1,0)=(1,2,7),T(0,1)=(3,5,9)$，故在标准基下 $T$ 的矩阵为

$$
\begin{gather}
\mathcal{M}(T)=\begin{pmatrix}
1 & 3 \\
2 & 5 \\
7 & 9
\end{pmatrix}
\end{gather}
$$

(b) 考虑微分算子 $D \in L(\mathcal{P}_{3}(\mathbb{R}),\mathcal{P}_{2}(\mathbb{R}))$，由于 $D(x^{n})=nx^{n-1}$，因此在标准基下 $D$ 的矩阵为

$$
\begin{gather}
\mathcal{M}(D)=\begin{pmatrix}
0 & 1 & 0 & 0 \\
0 & 0 & 2 & 0 \\
0 & 0 & 0 & 3
\end{pmatrix}
\end{gather}
$$

## Addition and Scalar Multiplication of Matrices

在本节中，我们假设 $U,V,W$ 是有限维向量空间，并且它们都各自选取了一个基。于是，我们可以讨论 $T \in L(V,W)$ 和 $S \in L(U,V)$ 的矩阵。

两个线性映射之和的矩阵是否等于它们各自矩阵的和？这个问题目前还没有意义，因为我们还未定义矩阵的加法。我们希望给出这样一种定义，使得矩阵的运算与线性映射的运算相一致，这是我们定义矩阵加法、数乘、乘法的主要动机。

### Definition 3.28

两个相同大小的矩阵的加法定义为逐项相加：

$$
\begin{gather}
(A_{j,k})_{1\leq j\leq m,1\leq k\leq n}+(C_{j,k})_{1\leq j\leq m,1\leq k\leq n}=(A_{j,k}+C_{j,k})_{1\leq j\leq m,1\leq k\leq n}
\end{gather}
$$

### Theorem 3.29

设 $S,T \in L(V,W)$，则在相同的基下有 $\mathcal{M}(S+T)=\mathcal{M}(S)+\mathcal{M}(T)$。

根据相同的原则，我们定义矩阵的数乘如下。

### Definition 3.30

一个矩阵与 $\lambda \in \mathbb{F}$ 的数乘定义为逐项相乘：

$$
\begin{gather}
\lambda (A_{j,k})_{1\leq j\leq m,1\leq k\leq n}=(\lambda A_{j,k})_{1\leq j\leq m,1\leq k\leq n}
\end{gather}
$$

### Theorem 3.31

设 $\lambda \in \mathbb{F},T \in L(V,W)$，则在相同的基下有 $\mathcal{M}(\lambda T)=\lambda \mathcal{M}(T)$。

既然我们定义了矩阵的加法和数乘，那么一个向量空间结构的出现应当是毫不意外的。

### Notation 3.32

设 $m,n$ 是正整数，我们记 $\mathbb{F}^{m,n}$ 表示所有 $\mathbb{F}$ 上 $m\times n$ 矩阵构成的集合。

### Theorem 3.33

设 $m,n$ 是正整数，则在矩阵的加法和数乘下，$\mathbb{F}^{m,n}$ 构成了一个维度 $mn$ 的向量空间。

#### Proof

容易验证 $\mathbb{F}^{m,n}$ 是向量空间，其中加法单位元是所有项为 $0$ 的零矩阵。

此外，我们也可以验证矩阵 $E_{j,k}$，定义为在 $j$ 行 $k$ 列为 $1$，其余项为 $0$ 的矩阵构成了 $\mathbb{F}^{m,n}$ 的一个基，它的长度为 $mn$。

## Matrix Multiplication

和上一节一样，我们假设 $v_{1},\dots,v_{n}$ 是 $V$ 的基，$w_{1},\dots,w_{m}$ 是 $W$ 的基，$u_{1},\dots,u_{p}$ 是 $U$ 的基。

考虑线性映射 $T\colon U\to V$ 和 $S\colon V\to W$，则它们的乘积 $ST \in L(U,W)$。根据前面介绍的原则，我们希望定义矩阵的乘积 $\mathcal{M}(S)\mathcal{M}(T)$，使得它等于 $\mathcal{M}(ST)$。

设 $\mathcal{M}(S)=A,\mathcal{M}(T)=B$，对于 $1\leq k\leq p$，我们有

$$
\begin{align}
(ST)u_{k} &= S\left( \sum_{r=1}^{n} B_{r,k}v_{r} \right) \\
&=\sum_{r=1}^{n} B_{r,k} Sv_{r} \\
&=\sum_{r=1}^{n} B_{r,k} \sum_{j=1}^{m} A_{j,r}w_{j} \\
&=\sum_{j=1}^{m} \sum_{r=1}^{n} A_{j,r}B_{r,k} w_{j}
\end{align}
$$

因此，矩阵 $\mathcal{M}(ST)$ 的第 $j$ 行第 $k$ 的元素应当为

$$
\begin{gather}
\sum_{r=1}^{n} A_{j,r}B_{r,k}
\end{gather}
$$

### Definition 3.34

设 $A$ 是一个 $m\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵，则 $AB$ 定义为一个 $m\times p$ 矩阵，其 $j$ 行 $k$ 列的元素为

$$
\begin{gather}
(AB)_{j,k}=\sum_{r=1}^{n} A_{j,r}B_{r,k}
\end{gather}
$$

既然矩阵的乘积与线性映射的乘积一致，因此它也继承了线性映射乘积的性质 [[#Theorem 3.7]]。具体来说，矩阵的乘法是结合的、分配的，但不是交换的。

### Theorem 3.35

假设我们分别在有限维向量空间 $U,V,W$ 上固定一个基，$T \in L(U,V)$，$S \in L(V,W)$，则 $\mathcal{M}(ST)=\mathcal{M}(S)\mathcal{M}(T)$。

### Notation 3.36

设 $A$ 是一个 $m\times n$ 矩阵。

如果 $1\leq j\leq m$，我们记 $A_{j,\cdot}$ 表示由 $A$ 的第 $j$ 行构成的 $1\times n$ 矩阵。

如果 $1\leq k\leq n$，我们记 $A_{\cdot,k}$ 表示由 $A$ 的第 $k$ 列构成的 $m\times 1$ 矩阵。

一个 $1\times n$ 行矩阵与一个 $n \times 1$ 列矩阵的乘积是一个 $1 \times 1$ 矩阵，后者我们通常将其与它的元素等同。例如，

$$
\begin{gather}
\begin{pmatrix}
3 & 4
\end{pmatrix} \begin{pmatrix}
6 \\
2
\end{pmatrix}=(26)
\end{gather}
$$

因为 $3\cdot 6+4\cdot 2=26$。我们可以将 $(26)$ 与 $26$ 等同，于是就得到 $\begin{pmatrix}3 & 4\end{pmatrix} \begin{pmatrix}6 \\ 2\end{pmatrix}=26$。

### Theorem 3.37

设 $A$ 是一个 $m\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵，则对于 $1\leq j\leq m$ 和 $1\leq k\leq p$ 有

$$
\begin{gather}
(AB)_{j,k}=A_{j,\cdot}B_{\cdot,k}
\end{gather}
$$

这就是说，$AB$ 的 $j$ 行 $k$ 列元素等于 $A$ 的第 $j$ 行乘以 $B$ 的第 $k$ 列。

#### Proof

根据矩阵乘法的定义，有

$$
\begin{gather}
(AB)_{j,k}=\sum_{r=1}^{n} A_{j,r}B_{r,k}
\end{gather}
$$

而通过将 $1\times 1$ 矩阵与其元素等同，右侧的表达式正是 $A_{j,\cdot}B_{\cdot,k}$。

### Theorem 3.38

设 $A$ 是一个 $m\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵，则对 $1\leq k\leq p$ 有

$$
\begin{gather}
(AB)_{\cdot,k}=AB_{\cdot,k}
\end{gather}
$$

这就是说，$AB$ 的第 $k$ 列等于 $A$ 乘以 $B$ 的第 $k$ 列。

#### Proof

显然，$(AB)_{\cdot,k}$ 和 $AB_{\cdot,k}$ 都是 $m\times 1$ 矩阵，它们第 $j$ 行的元素均为

$$
\begin{gather}
\sum_{r=1}^{n} A_{j,r}B_{r,k}
\end{gather}
$$

因此两者相等。

### Theorem 3.39

设 $A$ 是一个 $m\times n$ 矩阵，$b=\begin{pmatrix}b_{1}\\ \vdots\\ b_{n}\end{pmatrix}$ 是一个 $n\times 1$ 矩阵，则

$$
\begin{gather}
Ab=b_{1}A_{\cdot,1}+\dots+b_{n}A_{\cdot,n}
\end{gather}
$$

换言之，$A$ 与列矩阵 $b$ 的乘积是 $A$ 的列的线性组合，其系数为 $b$ 中的项。

#### Proof

等式两边都是 $m\times 1$ 矩阵，它们的第 $j$ 行元素均为

$$
\begin{gather}
A_{j,1}b_{1}+\dots+A_{j,n}b_{n}
\end{gather}
$$

因此两者相等。

上面两个定理展示了矩阵乘法的“列视角”，即，矩阵 $AB$ 的第 $k$ 列是 $A$ 的各列的线性组合，其系数为 $B$ 的第 $k$ 列元素。利用完全相同的论证方法，我们可以给出以下的“行视角”，也即，$AB$ 的第 $j$ 行是 $B$ 的各行的线性组合，其系数为 $A$ 的第 $j$ 行元素。

### Theorem 3.40

设 $A$ 是一个 $m\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵，则对 $1\leq j\leq m$ 有

$$
\begin{gather}
(AB)_{j,\cdot}=A_{j,\cdot}B
\end{gather}
$$

这就是说，$AB$ 的第 $j$ 行等于 $A$ 的第 $j$ 行乘以 $B$。

### Theorem 3.41

设 $a=\begin{pmatrix}a_{1} & \cdots & a_{n}\end{pmatrix}$ 是一个 $1\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵，则

$$
\begin{gather}
aB=a_{1}B_{1,\cdot}+\dots+a_{n}B_{n,\cdot}
\end{gather}
$$

换言之，行矩阵 $a$ 与 $B$ 的乘积是 $B$ 的行的线性组合，其系数为 $a$ 中的项。

### Theorem 3.42

设 $C$ 是一个 $m\times c$ 矩阵，$R$ 是一个 $c\times n$ 矩阵。

(a) 如果 $1\leq k\leq n$，则 $CR$ 的第 $k$ 列是 $C$ 的列的线性组合，其系数来自 $R$ 的第 $k$ 列。

(b) 如果 $1\leq j\leq m$，则 $CR$ 的第 $j$ 行是 $R$ 的行的线性组合，其系数来自 $C$ 的第 $j$ 行。

## Column-Row Factorization and Rank of a Matrix

### Definition 3.43 column rank 列秩，row rank 行秩

设 $A$ 是 $\mathbb{F}$ 上的 $m\times n$ 矩阵。

$A$ 的列秩定义为 $A$ 的列在 $\mathbb{F}^{m,1}$ 中的张成空间（列空间）的维度。

$A$ 的行秩定义为 $A$ 的行在 $\mathbb{F}^{1,n}$ 中的张成空间（行空间）的维度。

### Example 3.44

考虑矩阵

$$
\begin{gather}
A=\begin{pmatrix}
4 & 7 & 1 & 8 \\
3 & 5 & 2 & 9
\end{pmatrix}
\end{gather}
$$

它的前两列线性无关，又 $\dim \mathbb{F}^{2,1}=2$，因此 $A$ 的列秩为 $2$。类似地，$A$ 的两行线性无关，从而其行秩为 $2$。注意到行秩等于列秩，本节我们将证明这并非巧合。

### Definition 3.45 transpose 转置

一个 $m\times n$ 矩阵 $A$ 的转置 $A^{T}$ 是一个 $n\times m$ 矩阵，它第 $k$ 行第 $j$ 列的元素为

$$
\begin{gather}
(A^{T})_{k,j}=A_{j,k}
\end{gather}
$$

换言之，$A^{T}$ 是将 $A$ 的行列交换后得到的矩阵。

### Theorem 3.46

对任意 $m\times n$ 矩阵 $A,B$，$n\times p$ 矩阵 $C$ 和 $\lambda \in \mathbb{F}$ 有：

1. $(A+B)^{T}=A^{T}+B^{T}$，
2. $(\lambda A)^{T}=\lambda A^{T}$，
3. $(AC)^{T}=C^{T}A^{T}$。

#### Proof

容易验证命题 (1)(2)。对于 (3)，由于等式两边都是 $p\times m$ 矩阵，我们只需验证其元素逐项相等即可。

设 $1\leq k\leq p,1\leq j\leq m$，则

$$
\begin{gather}
((AC)^{T})_{k,j}=\sum_{r=1}^{n} A_{j,r}C_{r,k}=\sum_{r=1}^{n} (C^{T})_{k,r}(A^{T})_{r,j}=(C^{T}A^{T})_{k,j}
\end{gather}
$$

这就完成了证明。

### Theorem 3.47 (CR 分解)

设 $A$ 是 $\mathbb{F}$ 上的 $m\times n$ 矩阵，其列秩为 $c\geq 1$。则存在 $m\times c$ 矩阵 $C$ 和 $c\times n$ 矩阵 $R$ 使得 $A=CR$。

#### Proof

$A$ 的各列 $A_{\cdot,1},\dots,A_{\cdot,n}$ 张成了 $A$ 的列空间，从而它可以缩减为列空间的一个基，其长度为 $c$。我们将这 $c$ 列组合起来，构成一个矩阵 $C$。

对任意 $1\leq k\leq n$，$A$ 的第 $k$ 列可以写成 $C$ 的列的线性组合，我们将该线性组合的系数逐项写入 $c\times n$ 矩阵 $R$ 的第 $k$ 列，则 [[#Theorem 3.42]](a) 就给出 $A=CR$。

等价地，我们也可以选取行空间的一个基构成 $R$，然后将线性组合的系数写入 $C$。此时我们就需要 [[#Theorem 3.42]](b) 来保证 $A=CR$。

### Theorem 3.48

设 $A \in \mathbb{F}^{m,n}$，则 $A$ 的行秩等于 $A$ 的列秩。

#### Proof

设 $A$ 的列秩为 $c$。如果 $c=0$，那么 $A=0$，从而其行秩也为 $0$。因此我们可以假设 $c\geq 1$。

取 $A$ 的 CR 分解 $A=CR$，其中 $C$ 是 $m\times c$ 矩阵，$R$ 是 $c\times n$ 矩阵。[[#Theorem 3.42]](b) 表明，$A$ 的行是 $R$ 的行的线性组合，即 $A$ 的行空间由 $R$ 的行张成。由于 $R$ 只有 $c$ 行，因此 $A$ 的行秩小于等于 $A$ 的列秩 $c$。

我们对 $A$ 的转置 $A^{T}$ 重复上述论证，由于 $A^{T}$ 的列秩等于 $A$ 的行秩，$A^{T}$ 的行秩等于 $A$ 的列秩，因此我们也有 $A$ 的列秩小于等于 $A$ 的行秩。这就完成了证明。

由于上述结论，我们可以不加区分地使用行秩与列秩，并将其简称为秩。

### Definition 3.49 rank 秩

一个矩阵 $A \in \mathbb{F}^{m,n}$ 的秩定义为它的列秩，记作 $\operatorname{rank}A$。

# 3D Invertibility and Isomorphisms

## Invertible Linear Maps

### Definition 3.50 invertible 可逆的，inverse 逆映射

称 $T \in L(V,W)$ 是可逆的，如果存在 $S \in L(W,V)$ 使得 $ST=I_{V}$ 且 $TS=I_{W}$，其中 $I_{V}$ 和 $I_{W}$ 分别是 $V$ 和 $W$ 上的恒等算子。我们称 $S$ 为 $T$ 的一个逆映射。

### Theorem 3.51

一个可逆线性映射有唯一的逆映射。

#### Proof

设 $T \in L(V,W)$ 可逆，且 $S_{1},S_{2}$ 都是 $T$ 的逆，则

$$
\begin{gather}
S_{1}=S_{1}(TS_{2})=(S_{1}T)S_{2}=S_{2}
\end{gather}
$$

从而逆映射是唯一的。

由于以上定理，我们可以合理地称 $S$ 是 $T$ 的逆，而无需指明是 $T$ 的“一个”逆。

### Notation 3.52

如果 $T \in L(V,W)$ 是可逆的，我们用 $T^{-1}$ 来表示 $T$ 的唯一逆映射。

### Theorem 3.53

一个线性映射可逆当且仅当它既是单射也是满射。

#### Proof

首先设 $T \in L(V,W)$ 是可逆的。

设 $Tu=Tv$，则我们有

$$
\begin{gather}
u=T^{-1}(Tu)=T^{-1}(Tv)=v
\end{gather}
$$

故 $T$ 是单射。

对任意 $w \in W$，我们有 $w=T(T^{-1}w) \in \operatorname{range}T$，因此 $\operatorname{range}T=W$，即 $T$ 是满射。

反之，设 $T$ 既是单射也是满射。对于 $w \in W$，根据满射性，存在 $v \in V$ 使得 $Tv=w$，再由单射性，不存在其他 $v'$ 使得 $Tv'=w$。因此，定义为 $S(w)=v$ 的 $S$ 是一个良定的映射，并且满足 $T\circ S=I$。

下面我们证明 $S\circ T=I$。任取 $v \in V$，则

$$
\begin{gather}
T((S\circ T)v)=(T\circ S)(Tv)=Tv
\end{gather}
$$

由 $T$ 的单射性得 $(S\circ T)v=v$，即 $S\circ T=I$。

最后，我们需要证明 $S$ 是线性映射。设 $w_{1},w_{2}\in W$，则

$$
\begin{gather}
T(S(w_{1})+S(w_{2}))=T(S(w_{1}))+T(S(w_{2}))=w_{1}+w_{2}
\end{gather}
$$

这就是说，$S(w_{1})+S(w_{2})$ 是使得 $T$ 的值为 $w_{1}+w_{2}$ 的唯一输入，即 $S(w_{1}+w_{2})$。这就证明了加性。

对于齐次性，设 $w \in W,\lambda \in \mathbb{F}$，则

$$
\begin{gather}
T(\lambda S(w))=\lambda T(S(w))=\lambda w
\end{gather}
$$

由 $S$ 的定义即得 $S(\lambda w)=\lambda S(w)$，这就完成了证明。

以上定理对任意向量空间都成立。然而，在有限维空间上，我们有强得多的结论成立。

### Theorem 3.54

设 $V,W$ 是有限维向量空间，$\dim V=\dim W$，$T \in L(V,W)$，则 $T$ 是单射当且仅当 $T$ 是满射，当且仅当 $T$ 是可逆的。

#### Proof

我们只需证明第一个“当且仅当”，后一个由 [[#Theorem 3.53]] 给出。

在有限维空间上，秩-零化度定理给出

$$
\begin{gather}
\dim V=\dim \ker T+\dim \operatorname{range}T=\dim W
\end{gather}
$$

如果 $T$ 是单射，那么 $\dim \ker T=0$，从而 $\dim \operatorname{range}T=\dim W$，即 $\operatorname{range}T=W$，$T$ 是满射。

如果 $T$ 是满射，那么 $\dim \operatorname{range}T=\dim W$，从而 $\dim \ker T=0$，即 $\ker T=\{ 0 \}$，$T$ 是单射。

### Example 3.55

[[#Theorem 3.54]] 在无限维空间上并不成立，如下例子所示。

(a) 定义为 $(Tp)(x)=x^{2}p(x)$ 的线性映射 $T \in L(\mathcal{P}(\mathbb{R}))$ 是单射的，但不可逆：多项式 $1$ 不在 $T$ 的值域中。

(b) $\mathbb{F}^{\infty}$ 上的后移位算子 $T(x_{1},x_{2},x_{3},\dots)= (x_{2},x_{3},\dots)$ 是满射的，但不可逆：$(1,0,0,\dots)$ 在它的零空间中。

### Example 3.56

在本例中我们将展示如何应用 [[#Theorem 3.54]] 来解决相关问题。

给定多项式 $q$，我们要证：存在多项式 $p$ 使得 $((x^{2}+5x+7)p)''=q$。

定义线性映射

$$
\begin{gather}
Tp=((x^{2}+5x+7)p)''
\end{gather}
$$

它是单射的，因为满足二阶导数为零的多项式具有形式 $ax+b$，因此除非 $p=0$，否则我们都有 $Tp\neq 0$。因此，我们似乎能够应用 [[#Theorem 3.54]] 来证明 $T$ 是满射的。

然而，[[#Example 3.55]](a) 表明 [[#Theorem 3.54]] 不适用于无限维空间 $\mathcal{P}(\mathbb{R})$。为此，我们需要设法将 $T$ 限制在有限维空间 $\mathcal{P}_{m}(\mathbb{R})$ 上。

设 $q \in \mathcal{P}(\mathbb{R})$，它的次数为 $m$，则 $q \in \mathcal{P}_{m}(\mathbb{R})$。由于乘以一个二次多项式 $x^{2}+5x+7$ 将多项式的次数提高 $2$，求二阶导又将多项式的次数降低 $2$，因此 $T$ 可以限制为 $\mathcal{P}_{m}(\mathbb{R})$ 上的一个线性算子。

现在我们就可以应用 [[#Theorem 3.54]] 了，则 $T$ 在 $\mathcal{P}_{m}(\mathbb{R})$ 上是满射，即存在 $p \in \mathcal{P}_{m}(\mathbb{R})$ 使得 $Tp=q$。

### Theorem 3.57

设 $V,W$ 是有限维向量空间，$\dim V=\dim W$，$S \in L(W,V)$，$T \in L(V,W)$，则 $ST=I$ 当且仅当 $TS=I$。

换句话说，在相同维度的向量空间上，$T$ 有左逆当且仅当 $T$ 有右逆，并且此时左逆与右逆相等。

#### Proof

我们将证明两个更强的结论：$T$ 有左逆当且仅当 $T$ 是单射，以及 $T$ 有右逆当且仅当 $T$ 是满射，从而由 [[#Theorem 3.54]] 即证。

如果 $T$ 有左逆 $S$，设 $v \in \ker T$，则

$$
\begin{gather}
v=(ST)v=S(Tv)=S(0)=0
\end{gather}
$$

故 $T$ 是单射。反之，如果 $T$ 是单射，那么 [[#Theorem 3.54]] 表明 $T$ 可逆，它的逆映射 $T^{-1}$ 当然也是 $T$ 的左逆。

如果 $T$ 有右逆 $S$，则对任意 $w \in W$ 有

$$
\begin{gather}
w=(TS)w=T(Sw) \in \operatorname{range}T
\end{gather}
$$

从而 $\operatorname{range}T=W$，即 $T$ 是满射。反向的蕴含与上一段论证同理。

现在我们知道了 $T$ 有左逆当且仅当 $T$ 有右逆，分别设为 $S_{1}$ 和 $S_{2}$，则我们有

$$
\begin{gather}
S_{1}=S_{1}(TS_{2})=(S_{1}T)S_{2}=S_{2}
\end{gather}
$$

即证 $S_{1}=S_{2}=S$。

## Isomorphic Vector Spaces

### Definition 3.58 isomorphism 同构，isomorphic 同构的

一个可逆线性映射称为一个同构。

如果存在从一个向量空间 $V$ 到另一个向量空间 $W$ 的同构，我们就称这两个向量空间是同构的，记作 $V\cong W$。

我们可以将一个同构 $T\colon V\to W$ 视为一种将 $v \in V$ 重新标记为 $Tv \in W$ 的方法。从这一角度看，两个同构的向量空间在本质上是相同的，仅仅只是元素的表示不同。

### Theorem 3.59

两个有限维的 $\mathbb{F}$-向量空间是同构的，当且仅当它们的维度相同。

#### Proof

首先设 $V,W$ 是同构的有限维空间，则存在同构 $T\colon V\to W$。由 $T$ 的可逆性，可知 $\ker T=\{ 0 \}$ 且 $\operatorname{range}T=W$，从而秩-零化度定理给出

$$
\begin{gather}
\dim V=\dim \ker T+\dim \operatorname{range}T=\dim W
\end{gather}
$$

反之，如果 $\dim V=\dim W=n$，设 $v_{1},\dots,v_{n}$ 是 $V$ 的基，$w_{1},\dots,w_{n}$ 是 $W$ 的基，我们定义 $T \in L(V,W)$ 为

$$
\begin{gather}
T(c_{1}v_{1}+\dots+c_{n}v_{n})=c_{1}w_{1}+\dots+c_{n}w_{n}
\end{gather}
$$

则 $T$ 是良定的，因为 $v_{1},\dots,v_{n}$ 是基。$T$ 是满射的，因为 $w_{1},\dots,w_{n}$ 张成 $W$。最后，$\ker T=\{ 0 \}$，因为 $w_{1},\dots,w_{n}$ 线性无关，故 $T$ 是单射。因此 $T$ 是一个同构，从而 $V\cong W$。

以上定理表明，任何满足 $\dim V=n$ 的有限维空间 $V$ 同构于 $\mathbb{F}^{n}$。例如，由于 $\dim \mathcal{P}_{m}(\mathbb{F})=m+1$，故 $\mathcal{P}_{m}(\mathbb{F})\cong \mathbb{F}^{m+1}$。

之前我们定义了 $\mathbb{F}^{m,n}$，所有 $m\times n$ 矩阵构成的向量空间。设 $v_{1},\dots,v_{n}$ 是 $V$ 的一个基，$w_{1},\dots,w_{m}$ 是 $W$ 的一个基，则对任意 $T \in L(V,W)$，我们都有 $\mathcal{M}(T)\in \mathbb{F}^{m,n}$。于是，只要我们固定 $V$ 和 $W$ 上的一个基，那么 $\mathcal{M}$ 就构成了一个从 $L(V,W)$ 到 $\mathbb{F}^{m,n}$ 的一个函数。

### Theorem 3.60

设 $v_{1},\dots,v_{n}$ 是 $V$ 的一个基，$w_{1},\dots,w_{m}$ 是 $W$ 的一个基，则 $\mathcal{M}$ 是一个从 $L(V,W)$ 到 $\mathbb{F}^{m,n}$ 的同构。

#### Proof

由于我们定义矩阵的加法和数乘时保持了其与线性映射加法和数乘的一致性，因此 $\mathcal{M}$ 是线性的。下面我们分别证明 $\mathcal{M}$ 的单射性与满射性。

如果 $T \in L(V,W)$ 满足 $\mathcal{M}(T)=0$，那么 $Tv_{k}=0$。由于 $v_{1},\dots,v_{n}$ 是基，因此对任意 $v \in V$ 有 $Tv=0$，即 $T=0$。这表明 $\mathcal{M}$ 是单射。

任取 $A \in \mathbb{F}^{m,n}$，由于 $T$ 在基上的取值完全确定了 $T$，因此通过设置

$$
\begin{gather}
Tv_{k}=\sum_{j=1}^{m} A_{j,k}w_{j}
\end{gather}
$$

我们就定义了 $T \in L(V,W)$，使得 $\mathcal{M}(T)=A$。从而 $\mathcal{M}$ 是满射。

### Corollary 3.61

设 $V,W$ 是有限维向量空间，则 $L(V,W)$ 是有限维的，并且

$$
\begin{gather}
\dim L(V,W)=(\dim V)(\dim W)
\end{gather}
$$

## Linear Maps Thought of as Matrix Multiplication

### Definition 3.62

设 $v \in V$ 且 $v_{1},\dots,v_{n}$ 是 $V$ 的基，定义 $v$ 关于给定基的矩阵为 $n\times 1$ 矩阵

$$
\begin{gather}
\mathcal{M}(v)=\begin{pmatrix}
b_{1} \\
\vdots \\
b_{n}
\end{pmatrix}
\end{gather}
$$

其中 $b_{1},\dots,b_{n} \in \mathbb{F}$ 满足

$$
\begin{gather}
v=b_{1}v_{1}+\dots+b_{n}v_{n}
\end{gather}
$$

### Example 3.63

(a) 多项式 $2-7x+5x^{3}+x^{4}$ 在 $\mathcal{P}_{4}(\mathbb{R})$ 的标准基下的矩阵为

$$
\begin{gather}
\begin{pmatrix}
2 \\
-7 \\
0 \\
5 \\
1
\end{pmatrix}
\end{gather}
$$

(b) 一个向量 $x=(x_{1},\dots,x_{n})\in \mathbb{F}^{n}$ 在标准基下的矩阵就是将它的坐标竖着写入一个 $n\times 1$ 矩阵得到的：

$$
\begin{gather}
\begin{pmatrix}
x_{1} \\
\vdots \\
x_{n}
\end{pmatrix}
\end{gather}
$$

更一般地，只要 $V$ 上的一个基 $v_{1},\dots,v_{n}$ 已取定，我们就可以通过同构 $\mathcal{M}\colon V\to \mathbb{F}^{n,1}$ 将 $v \in V$ 与一个列矩阵等同。

### Theorem 3.64

设 $T \in L(V,W)$，$v_{1},\dots,v_{n}$ 是 $V$ 的基，$w_{1},\dots,w_{m}$ 是 $W$ 的基，则对于 $1\leq k\leq n$，$\mathcal{M}(T)$ 的第 $k$ 列 $\mathcal{M}(T)_{\cdot,k}$，作为 $\mathbb{F}^{n,1}$ 中的一个元素，等于 $\mathcal{M}(Tv_{k})$。

#### Proof

设 $A=\mathcal{M}(T)$，则根据矩阵乘法的定义

$$
\begin{gather}
Tv_{k}=A_{1,k}w_{1}+\dots+A_{m,k}w_{m}
\end{gather}
$$

即证。

### Theorem 3.65

设 $T \in L(V,W)$，$v \in V$，$v_{1},\dots,v_{n}$ 是 $V$ 的基，$w_{1},\dots,w_{m}$ 是 $W$ 的基，则

$$
\begin{gather}
\mathcal{M}(Tv)=\mathcal{M}(T)\mathcal{M}(v)
\end{gather}
$$

#### Proof

设 $v=b_{1}v_{1}+\dots+b_{n}v_{n}$，则

$$
\begin{gather}
Tv=b_{1}Tv_{1}+\dots+b_{n}Tv_{n}
\end{gather}
$$

从而

$$
\begin{align}
\mathcal{M}(Tv) &= b_{1} \mathcal{M}(Tv_{1})+\dots+b_{n} \mathcal{M}(Tv_{n}) \\
&= b_{1} \mathcal{M}(T)_{\cdot,1}+\dots+b_{n} \mathcal{M}(T)_{\cdot,n} \\
&=\mathcal{M}(T)\mathcal{M}(v)
\end{align}
$$

其中最后一个等式来自于矩阵乘法的列视角：$Ab$ 是 $A$ 的列的线性组合，其系数来源于 $b$。

任何 $m\times n$ 矩阵 $A$ 都诱导了一个从 $\mathbb{F}^{n,1}$ 到 $\mathbb{F}^{m,1}$ 的线性映射，即，将 $x \in \mathbb{F}^{n,1}$ 映射到 $Ax \in \mathbb{F}^{m,1}$ 的映射。以上的定理表明，任何线性映射在某个向量上的作用在同构意义下都可以等同于一个矩阵乘法。具体来说，如果 $T \in L(V,W)$，并且我们将 $v \in V$ 与 $\mathcal{M}(v) \in \mathbb{F}^{n,1}$ 等同，那么我们就可以将 $Tv \in W$ 与 $\mathcal{M}(T)\mathcal{M}(v) \in \mathbb{F}^{m,1}$ 等同。

正因如此，线性代数中最重要的几个结论本质上都是一种选取基的方法，使得 $T$ 在这个基下的矩阵具有最简单的形式。

### Theorem 3.66

设 $V,W$ 是有限维向量空间，$T \in L(V,W)$，则

$$
\begin{gather}
\dim \operatorname{range}T=\operatorname{rank}\mathcal{M}(T)
\end{gather}
$$

特别地，$\operatorname{rank}\mathcal{M}(T)$ 不依赖于 $V$ 上基的选取，因此我们可以定义线性映射 $T$ 的秩为 $\dim \operatorname{range}T$。

#### Proof

任取 $V$ 的基 $v_{1},\dots,v_{n}$ 和 $W$ 的基 $w_{1},\dots,w_{m}$。$\mathcal{M}\colon W\to \mathbb{F}^{m,1}$ 是一个同构，将其限制在 $\operatorname{range}T=\operatorname{span}(Tv_{1},\dots,Tv_{n})$ 上，则 $\mathcal{M}$ 是一个从 $\operatorname{range}T$ 到 $\operatorname{span}(\mathcal{M}(Tv_{1}),\dots,\mathcal{M}(Tv_{n}))$ 的同构。又由于 $\mathcal{M}(Tv_{k})$ 是矩阵 $\mathcal{M}(T)$ 的第 $k$ 列，故 $\operatorname{range}T$ 同构于 $\mathcal{M}(T)$ 的列空间，从而

$$
\begin{gather}
\dim \operatorname{range}T=\operatorname{rank}\mathcal{M}(T)
\end{gather}
$$

由于基 $v_{1},\dots,v_{n}$ 是任意选取的，并且 $\dim \operatorname{range}T$ 与基无关，故 $\operatorname{rank}\mathcal{M}(T)$ 也与基无关，这就完成了证明。

## Change of Basis

在 [[#3C Matrices]] 中我们定义了线性映射在给定基下的矩阵

$$
\begin{gather}
\mathcal{M}(T,(v_{1},\dots,v_{n}),(w_{1},\dots,w_{m}))
\end{gather}
$$

对于从向量空间 $V$ 到它自身的算子 $T \in L(V)$，我们通常在定义域 $V$ 和陪域 $V$ 上取相同的基，此时我们记

$$
\begin{gather}
\mathcal{M}(T,(v_{1},\dots,v_{n}))=\mathcal{M}(T,(v_{1},\dots,v_{n}),(v_{1},\dots,v_{n}))
\end{gather}
$$

如果基 $v_{1},\dots,v_{n}$ 在上下文中是明确的，那么我们可以简记为 $\mathcal{M}(T)$。

### Definition 3.67 identity matrix 恒等矩阵

设 $n$ 是正整数，主对角线上元素为 $1$，其余元素均为 $0$ 的 $n\times n$ 矩阵

$$
\begin{gather}
I=\begin{pmatrix}
1 &  & 0 \\
 & \ddots &  \\
0 &  & 1
\end{pmatrix}
\end{gather}
$$

称为 $n$ 阶恒等矩阵。

根据矩阵的定义，在 $V$ 的任意基下，恒等算子 $I \in L(V)$ 的矩阵都是恒等矩阵，只要我们将定义域和陪域上取相同的基。此外，如果 $A$ 是一个方阵（行数和列数相等的矩阵），那么我们就有 $AI=IA=A$，其中 $I$ 是与 $A$ 相同大小的恒等矩阵。

### Definition 3.68 invertible 可逆的，inverse 逆矩阵

称一个方阵 $A$ 是可逆的，如果存在方阵 $B$ 使得 $AB=BA=I$。我们称 $B$ 是 $A$ 的一个逆矩阵。

利用与 [[#Theorem 3.51]] 相同的证明方法，我们可以证明逆矩阵是唯一的，从而我们可以用符号 $A^{-1}$ 来表示 $A$ 的逆。

从而，我们就有等式 $(A^{-1})^{-1}=A$，因为唯一满足 $A^{-1}B=BA^{-1}=I$ 的矩阵 $B$ 就是 $A$。同理，如果 $A,C$ 是相同大小的可逆矩阵，那么 $(AC)^{-1}=C^{-1}A^{-1}$，因为

$$
\begin{align}
(AC)(C^{-1}A^{-1}) &= A(C C^{-1})A^{-1} \\
&= AA^{-1} \\
&= I
\end{align}
$$

类似地也有 $(C^{-1}A^{-1})(AC)=I$。

为了方便后续的讨论，我们将 [[#Theorem 3.35]] 中的基显式地写出。

### Theorem 3.69

设 $T \in L(U,V),S \in L(V,W)$，$u_{1},\dots,u_{m}$ 是 $U$ 的基，$v_{1},\dots,v_{n}$ 是 $V$ 的基，$w_{1},\dots,w_{p}$ 是 $W$ 的基，则

$$
\begin{multline}
\mathcal{M}(ST,(u_{1},\dots,u_{m}),(w_{1},\dots,w_{p}))= \\
\mathcal{M}(S,(v_{1},\dots,v_{n}),(w_{1},\dots,w_{p}))\mathcal{M}(T,(u_{1},\dots,u_{m}),(v_{1},\dots,v_{n}))
\end{multline}
$$

下一个结论涉及恒等算子 $I$ 在同一空间的两个基下的矩阵。根据定义，$C=\mathcal{M}(I,(u_{1},\dots,u_{n}),(v_{1},\dots,v_{n}))$ 的第 $k$ 列是将 $u_{k}$ 写成 $v_{1},\dots,v_{n}$ 的线性组合的系数

$$
\begin{gather}
u_{k}=C_{1,k}v_{1}+\dots+C_{n,k}v_{n}
\end{gather}
$$

因此，$C$ 通常被称为从基 $u_{1},\dots,u_{n}$ 到基 $v_{1},\dots,v_{n}$ 的转换矩阵。

### Theorem 3.70

设 $u_{1},\dots,u_{n}$ 和 $v_{1},\dots,v_{n}$ 是 $V$ 的基，则矩阵

$$
\begin{gather}
\mathcal{M}(I,(u_{1},\dots,u_{n}),(v_{1},\dots,v_{n})) \quad \text{and} \quad \mathcal{M}(I,(v_{1},\dots,v_{n}),(u_{1},\dots,u_{n}))
\end{gather}
$$

都是可逆的，并且它们互相是对方的逆。

#### Proof

在 [[#Theorem 3.69]] 中，将 $S,T$ 替换为 $I$，$w_{1},\dots,w_{p}$ 替换为 $u_{1},\dots,u_{n}$，则我们有

$$
\begin{gather}
I=\mathcal{M}(I,(v_{1},\dots,v_{n}),(u_{1},\dots,u_{n}))\mathcal{M}(I,(u_{1},\dots,u_{n}),(v_{1},\dots,v_{n}))
\end{gather}
$$

同理，交换 $u$ 和 $v$ 的角色，我们也有

$$
\begin{gather}
I=\mathcal{M}(I,(u_{1},\dots,u_{n}),(v_{1},\dots,v_{n}))\mathcal{M}(I,(v_{1},\dots,v_{n}),(u_{1},\dots,u_{n}))
\end{gather}
$$

这就完成了证明。

### Example 3.71

考虑 $\mathbb{F}^{2}$ 上的两个基 $(4,2),(5,3)$ 与 $(1,0),(0,1)$，则我们有

$$
\begin{gather}
\mathcal{M}(I,((4,2),(5,3)),((1,0),(0,1)))=\begin{pmatrix}
4 & 5 \\
2 & 3
\end{pmatrix}
\end{gather}
$$

上述矩阵的逆为

$$
\begin{gather}
\mathcal{M}(I,((1,0),(0,1)),((4,2),(5,3)))=\begin{pmatrix}
\frac{3}{2} & -\frac{5}{2} \\
-1 & 2
\end{pmatrix}
\end{gather}
$$

这就是说，

$$
\begin{gather}
(1,0)=\frac{3}{2}(4,2)-(5,3) \\
(0,1)=-\frac{5}{2}(4,2)+2(5,3)
\end{gather}
$$

下一个定理描述了当我们改变基时线性映射 $T$ 的矩阵的变化，这就是所谓的基变换公式。

### Theorem 3.72

设 $T \in L(V)$，$u_{1},\dots,u_{n}$ 和 $v_{1},\dots,v_{n}$ 是 $V$ 的基。令

$$
\begin{gather}
A=\mathcal{M}(T,(u_{1},\dots,u_{n})), \quad B=\mathcal{M}(T,(v_{1},\dots,v_{n}))
\end{gather}
$$

并令 $C=\mathcal{M}(I,(u_{1},\dots,u_{n}),(v_{1},\dots,v_{n}))$ 是从 $u$ 到 $v$ 的基变换矩阵，则

$$
\begin{gather}
A=C^{-1}BC
\end{gather}
$$

#### Proof

根据 [[#Theorem 3.70]]，$C$ 是可逆矩阵，因此我们只需证明

$$
\begin{gather}
CA=BC
\end{gather}
$$

根据 [[#Theorem 3.69]]，等式左边和右边均为

$$
\begin{gather}
\mathcal{M}(T,(u_{1},\dots,u_{n}),(v_{1},\dots,v_{n}))
\end{gather}
$$

这就完成了证明。

这就是说，在线性映射 $Tv=Av$ 的计算可以分解为三步：将空间的基转换为 $v_{1},\dots,v_{n}$（$C$），在这个基上计算 $Tv=Bv$，然后将空间的基转换回 $u_{1},\dots,u_{n}$（$C^{-1}$）。从后续的章节中我们将看到，通常我们可以选取合适的基 $v_{1},\dots,v_{n}$ 使得矩阵 $B$ 的形式尽可能的简单，而如何选取这样的基是线性代数的一个核心主题。

### Theorem 3.73

设 $v_{1},\dots,v_{n}$ 是 $V$ 的基，$T \in L(V)$ 是可逆的，则 $\mathcal{M}(T)$ 是可逆的，并且在相同的基下我们有

$$
\begin{gather}
\mathcal{M}(T^{-1})=\mathcal{M}(T)^{-1}
\end{gather}
$$

#### Proof

我们有

$$
\begin{gather}
\mathcal{M}(T)\mathcal{M}(T^{-1})=\mathcal{M}(T^{-1})\mathcal{M}(T)=\mathcal{M}(I)=I
\end{gather}
$$

根据逆矩阵的唯一性即得 $\mathcal{M}(T^{-1})=\mathcal{M}(T)^{-1}$。

# 3E Products and Quotients of Vector Spaces

## Products of Vector Spaces

### Definition 3.74 product 乘积

设 $V_{1},\dots,V_{m}$ 是 $\mathbb{F}$ 上的向量空间。

乘积 $V_{1}\times\dots \times V_{m}$ 定义为

$$
\begin{gather}
V_{1}\times\dots \times V_{m}=\{ (v_{1},\dots,v_{m}): v_{k}\in V_{k} \}
\end{gather}
$$

$V_{1}\times\dots \times V_{m}$ 上的加法和数乘定义为

$$
\begin{gather}
(u_{1},\dots,u_{m})+(v_{1},\dots,v_{m})=(u_{1}+v_{1},\dots,u_{m}+v_{m}) \\
\lambda(v_{1},\dots,v_{m})=(\lambda v_{1},\dots,\lambda v_{m})
\end{gather}
$$

参考 $\mathbb{F}^{n}$ 作为向量空间的证明，我们可以类似地证明如下定理：

### Theorem 3.75

设 $V_{1},\dots,V_{m}$ 是 $\mathbb{F}$-向量空间，则在如上定义的加法和数乘下，$V_{1}\times\dots \times V_{m}$ 构成了一个 $\mathbb{F}$-向量空间。

### Example 3.76

向量空间 $\mathbb{R}^{2}\times \mathbb{R}^{3}$ 的元素是有序对

$$
\begin{gather}
((x_{1},x_{2}),(x_{3},x_{4},x_{5}))
\end{gather}
$$

其中 $x_{k}\in \mathbb{R}$。向量空间 $\mathbb{R}^{5}$ 的元素是有序组

$$
\begin{gather}
(x_{1},x_{2},x_{3},x_{4},x_{5})
\end{gather}
$$

其中 $x_{k}\in \mathbb{R}$。

尽管 $\mathbb{R}^{2}\times \mathbb{R}^{3}$ 和 $\mathbb{R}^{5}$ 中的元素非常相似，但从严格的集合论角度来看，它们不是同一种元素：前者是长度为 $2$ 的组，其第一个坐标是长度 $2$ 的组，第二个坐标是长度 $3$ 的组，而后者是长度为 $5$ 的组。因此，从这一角度看，$\mathbb{R}^{2}\times \mathbb{R}^{3}\neq \mathbb{R}^{5}$。

然而，我们可以立即注意到两个向量空间之间显然的同构：

$$
\begin{gather}
((x_{1},x_{2}),(x_{3},x_{4},x_{5})) \mapsto (x_{1},x_{2},x_{3},x_{4},x_{5})
\end{gather}
$$

因此在同构意义下，$\mathbb{R}^{2}\times \mathbb{R}^{3}$ 与 $\mathbb{R}^{5}$ 是相同的。由于这一极为自然的同构，因此在大多数时候我们都能够直接将这两者等同，并写 $\mathbb{R}^{2}\times \mathbb{R}^{3}=\mathbb{R}^{5}$。正是在这种情况下，我们可以写 $\mathbb{F}^{n}=\mathbb{F}\times\dots \times \mathbb{F}$。

### Example 3.77

考虑 $\mathcal{P}_{2}(\mathbb{R})\times \mathbb{R}^{2}$ 中的一组向量

$$
\begin{gather}
(1,(0,0)),(x,(0,0)),(x^{2},(0,0)),(0,(1,0)),(0,(0,1))
\end{gather}
$$

它是线性无关的，并且张成 $\mathcal{P}_{2}(\mathbb{R})\times \mathbb{R}^{2}$，因而是一个基。

本例中的思想可以扩展到一般情况，如下定理所示。

### Theorem 3.78

设 $V_{1},\dots,V_{m}$ 是有限维向量空间，则 $V_{1}\times \dots \times V_{m}$ 是有限维的，并且

$$
\begin{gather}
\dim(V_{1}\times\dots \times V_{m})=\dim V_{1}+\dots+\dim V_{m}
\end{gather}
$$

#### Proof

在每个 $V_{k}$ 上取一个基。考虑 $V_{1}\times\dots \times V_{m}$ 中的如下元素：其在第 $k$ 个坐标处为 $V_{k}$ 上的基向量，在其他坐标处均为 $0$。这些向量构成的组线性无关，并且张成 $V_{1}\times\dots \times V_{m}$，从而是乘积空间的一个基。这一向量组的长度为 $\dim V_{1}+\dots+\dim V_{m}$，这就完成了证明。

### Theorem 3.79

设 $V_{1},\dots,V_{m}$ 是 $V$ 的子空间，定义 $\Gamma\colon V_{1}\times\dots \times V_{m}\to V_{1}+\dots+V_{m}$ 为

$$
\begin{gather}
\Gamma(v_{1},\dots,v_{m})=v_{1}+\dots+v_{m}
\end{gather}
$$

则 $V_{1}+\dots+V_{m}$ 是一个直和，当且仅当 $\Gamma$ 是单射。

特别地，根据 $V_{1}+\dots+V_{m}$ 的定义，$\Gamma$ 是满射，因此上面的条件“$\Gamma$ 是单射”可以替换为“$\Gamma$ 是可逆的”。

#### Proof

显然 $\Gamma$ 是一个线性映射。$\Gamma$ 是单射当且仅当 $\ker\Gamma=\{ 0 \}$，即，唯一使得 $v_{1}+\dots+v_{m}=0$ 的方法是取每个 $v_{k}=0$，这正是直和的等价条件（[[1 Vector Spaces#Theorem 1.32]]）。

### Theorem 3.80

设 $V$ 是有限维的，$V_{1},\dots,V_{m}$ 是 $V$ 的子空间，则 $V_{1}+\dots+V_{m}$ 是直和当且仅当

$$
\begin{gather}
\dim(V_{1}+\dots+V_{m})=\dim V_{1}+\dots+\dim V_{m}
\end{gather}
$$

#### Proof

根据 [[#Theorem 3.79]]，$V_{1}+\dots+V_{m}$ 是直和当且仅当 $\Gamma$ 是单射，当且仅当 $\Gamma$ 是一个同构。而后者成立当且仅当

$$
\begin{gather}
\dim(V_{1}+\dots+V_{m})=\dim(V_{1}\times\dots \times V_{m})
\end{gather}
$$

再根据 [[#Theorem 3.78]] 即证。

## Quotient Spaces

### Notation 3.81

设 $v \in V$ 且 $U\subset V$，则 $v+U$ 是 $V$ 的一个子集，定义为

$$
\begin{gather}
v+U=\{ v+u : u \in U \}
\end{gather}
$$

### Example 3.82

假设

$$
\begin{gather}
U=\{ (x,2x)\in \mathbb{R}^{2} : x \in \mathbb{R} \}
\end{gather}
$$

则 $U$ 是平面上过原点，斜率为 $2$ 的直线。则

$$
\begin{gather}
(17,20)+U
\end{gather}
$$

就是平面上过点 $(17,20)$ 且斜率为 $2$ 的直线。

![](3-2.png)

又因为

$$
\begin{gather}
(10,20) \in U, \quad (17,20)\in(17,20)+U
\end{gather}
$$

故我们可知 $(17,20)+U$ 由直线 $U$ 向右平移 $7$ 个单位得到。

受此启发，我们给出如下定义：

### Definition 3.83 translate 平移

对于 $v \in V$ 和 $U\subset V$，我们称 $v+U$ 为 $U$ 的一个平移。

### Definition 3.84 quotient space 商空间

设 $U$ 是 $V$ 的子空间，则商空间 $V /U$ 定义为所有 $U$ 的平移构成的集合，即

$$
\begin{gather}
V /U=\{ v +U : v \in V \}
\end{gather}
$$

#### Motivation

当 $U$ 是子空间时，所谓的商空间实质上是“关于等价关系的商集”的一个特例。这一等价关系定义如下：$v \sim w$ 当且仅当

$$
\begin{gather}
v=w+u, \quad u \in U
\end{gather}
$$

换言之，$v$ 与 $w$ 仅相差一个 $U$ 中的元素。当我们在 $V$ 上模去等价关系时，我们将每个元素 $v \in V$ 转化为了它所在的等价类 $[v]$，即所有与 $v$ 相差一个 $U$ 中元素的向量，也就是 $v+U$。

模去等价关系的结果是，原空间上的等价性 $v\sim w$ 转化为了商空间上的严格相等：$v+U=w+U$。这在泛代数角度下具有重要意义：我们假设有一个映射 $f$，其对于等价的元素总是给出相同的值，反之亦然，即 $v\sim w$ 当且仅当 $f(v)=f(w)$。则 $f$ 诱导了 $V /U$ 上的映射

$$
\begin{gather}
\tilde{f}(v+U)=f(v)
\end{gather}
$$

此时 $f$ 的性质给出 $v+U=w+U$ 当且仅当 $\tilde{f}(v+U)=\tilde{f}(w+U)$，即 $\tilde{f}$ 是单射。

特别地，对于线性映射 $T$，恰好有一个子空间 $\ker T$ 满足上述条件。因而，$T$ 在 $V /\ker T$ 上的诱导映射 $\tilde{T}$ 是单射。再根据 $T\colon V\to \operatorname{range}T$ 的满射性，我们就有所谓的“第一同构定理”

$$
\begin{gather}
V /\ker T \cong \operatorname{range}T
\end{gather}
$$

它的相应变体在各个代数结构中均有出现。

下面我们给出几个定理来使以上思想严格化。

### Theorem 3.85

设 $U$ 是 $V$ 的子空间，$v,w \in V$，则 $v-w \in U$ 当且仅当 $v+U=w+U$，当且仅当 $(v+U)\cap(w+U)\neq \varnothing$。

#### Proof

首先设 $v-w \in U$，则对任意 $u \in U$ 有

$$
\begin{gather}
v+u=w+(v-w)+u \in w+U
\end{gather}
$$

故 $v+U\subset w+U$。同理也有 $w+U\subset v+U$，从而 $v+U=w+U$。此时显然也有 $(v+U)\cap(w+U)\neq \varnothing$。

现在假设 $(v+U)\cap(w+U)\neq \varnothing$，则存在 $u_{1},u_{2}\in U$ 使得

$$
\begin{gather}
v+u_{1}=w+u_{2}
\end{gather}
$$

即 $v-w=u_{2}-u_{1}\in U$，这就完成了证明。

现在我们可以定义 $V /U$ 上的加法和数乘了。

### Definition 3.86

设 $U$ 是 $V$ 的子空间，则 $V /U$ 上的加法和数乘定义为

$$
\begin{gather}
(v+U)+(w+U)=(v+w)+U \\
\lambda(v+U)=(\lambda v)+U
\end{gather}
$$

其中 $v,w \in V,\lambda \in \mathbb{F}$。

以上定义的良定性将作为如下定理证明的一部分给出。

### Theorem 3.87

设 $U$ 是 $V$ 的子空间，则 $V /U$ 在如上定义的加法和数乘下构成一个向量空间。

#### Proof

[[#Definition 3.86]] 的潜在问题是，$U$ 的平移集（等价类）的代表元不是唯一的。特别地，如果

$$
\begin{gather}
v_{1}+U=v_{2}+U, \quad w_{1}+U=w_{2}+U
\end{gather}
$$

要使加法是良定的，我们就必须证明 $(v_{1}+w_{1})+U=(v_{2}+w_{2})+U$。

根据 [[#Theorem 3.85]]，我们有 $v_{1}-v_{2}\in U,w_{1}-w_{2}\in U$，从而

$$
\begin{gather}
(v_{1}+w_{1})-(v_{2}+w_{2})=(v_{1}-v_{2})+(w_{1}-w_{2}) \in U
\end{gather}
$$

再次应用 [[#Theorem 3.85]] 即得 $(v_{1}+w_{1})+U=(v_{2}+w_{2})+U$。

数乘的良定性也是类似的：如果 $v_{1}-v_{2}\in U$，那么 $\lambda(v_{1}-v_{2})\in U$，从而 $\lambda v_{1}+U=\lambda v_{2}+U$。

现在加法和数乘在 $V /U$ 上有了定义，验证它们满足向量空间的公理是容易的。特别地，其上的加法单位元为 $0+U=U$，并且 $v+U$ 的加法逆元为 $(-v)+U$。

### Definition 3.88 quotient map 商映射

设 $U$ 是 $V$ 的子空间，我们定义商映射 $\pi\colon V\to V /U$ 为

$$
\begin{gather}
\pi(v)=v+U \quad (v \in V)
\end{gather}
$$

显然，$\pi$ 是一个线性映射。

### Theorem 3.89

设 $V$ 是有限维向量空间，$U$ 是 $V$ 的子空间，则

$$
\begin{gather}
\dim V /U=\dim V -\dim U
\end{gather}
$$

#### Proof

考虑商映射 $\pi\colon V\to V /U$，显然它是一个满射。如果 $v \in V$ 满足 $\pi(v)=v+U=0+U$，则 $v \in U$，反之亦然。因此，$\ker \pi=U$，从而根据秩-零化度定理有

$$
\begin{gather}
\dim V=\dim U+\dim V /U
\end{gather}
$$

这就是所要证的。

### Notation 3.90

设 $T \in L(V,W)$，定义 $\tilde{T}\colon V /\ker T\to W$ 为

$$
\begin{gather}
\tilde{T}(v+\ker T)=Tv
\end{gather}
$$

要证明 $\tilde{T}$ 是良定的，设 $u+\ker T=v+\ker T$，则 $u-v \in \ker T$，即 $T(u-v)=0$，$Tu=Tv$。因此 $\tilde{T}$ 是一个良定的映射。容易验证它也是线性的。

### Theorem 3.91 (第一同构定理)

设 $T \in L(V,W)$，则

(a) $\tilde{T}\circ \pi=T$，其中 $\pi$ 是从 $V$ 到 $V /\ker T$ 的商映射，
(b) $\tilde{T}$ 是单射，
(c) $\operatorname{range}\tilde{T}=\operatorname{range}T$，
(d) $V /\ker T\cong \operatorname{range}T$。

#### Proof

(a) 如果 $v \in V$，则

$$
\begin{gather}
\tilde{T}\circ \pi(v)=\tilde{T}(v+\ker T)=Tv
\end{gather}
$$

即证 $\tilde{T}\circ \pi=T$。

(b) 假设 $v \in V$ 满足 $\tilde{T}(v+\ker T)=0$，则 $Tv=0$，$v \in \ker T$，从而 $v+\ker T=0+\ker T$。这表明 $\ker \tilde{T}=\{ 0+\ker T \}$，故 $\tilde{T}$ 是单射。

(c) 由 $\tilde{T}$ 的定义立即得到。

(d) 由 (b)(c) 可知，如果我们将 $\tilde{T}$ 视为从 $V /\ker T$ 到 $\operatorname{range}T$ 的映射，那么 $\tilde{T}$ 就是一个同构。

# 3F Duality

### Definition 3.92 linear functional 线性泛函

$V$ 上的一个线性泛函是 $L(V,\mathbb{F})$ 中的一个元素。

### Example 3.93

(a) 固定 $(c_{1},\dots,c_{n})\in \mathbb{F}^{n}$，则定义为 $\varphi(x_{1},\dots,x_{n})=\sum c_{i}x_{i}$ 的 $\varphi\colon \mathbb{F}^{n}\to \mathbb{F}$ 是一个线性泛函。

(b) 定义 $\varphi\colon \mathcal{P}(\mathbb{R})\to \mathbb{R}$ 为

$$
\begin{gather}
\varphi(p)=3p'(5)+7p(4)
\end{gather}
$$

则 $\varphi$ 是一个线性泛函。

(c) 定义 $\varphi\colon \mathcal{P}(\mathbb{R})\to \mathbb{R}$ 为

$$
\begin{gather}
\varphi(p)=\int_{0}^{1} p
\end{gather}
$$

则根据积分的性质，$\varphi$ 是一个线性泛函。

### Definition 3.94 dual space 对偶空间

$V$ 的对偶空间 $V^{*}$ 定义为 $V$ 上所有线性泛函构成的向量空间 $L(V,\mathbb{F})$。

### Theorem 3.95

设 $V$ 是有限维向量空间，则 $V^{*}$ 也是有限维的，且

$$
\begin{gather}
\dim V^{*}=\dim V
\end{gather}
$$

#### Proof

我们有

$$
\begin{gather}
\dim V^{*}=\dim L(V,\mathbb{F})=(\dim V)(\dim \mathbb{F})=\dim V
\end{gather}
$$

在下面的定义中，[[#Theorem 3.3]] 保证了各 $\varphi_{j}$ 是良定的。

### Definition 3.96 dual basis 对偶基

设 $v_{1},\dots,v_{n}$ 是 $V$ 的一个基，它的对偶基是线性泛函 $\varphi_{1},\dots,\varphi_{n}$，定义为

$$
\begin{gather}
\varphi_{j}(v_{k})=\delta_{j,k}=\begin{cases}
1, & j=k \\
0, & j\neq k
\end{cases}
\end{gather}
$$

### Example 3.97

定义 $\mathbb{F}^{n}$ 上的线性泛函 $\varphi_{j}$ 为

$$
\begin{gather}
\varphi_{j}(x_{1},\dots,x_{n})=x_{j}
\end{gather}
$$

则如果 $e_{1},\dots,e_{n}$ 是 $\mathbb{F}^{n}$ 的标准基，则

$$
\begin{gather}
\varphi_{j}(e_{k})=\delta_{j,k}
\end{gather}
$$

因而 $\varphi_{1},\dots,\varphi_{n}$ 是标准基的对偶基。

### Theorem 3.98

设 $v_{1},\dots,v_{n}$ 是 $V$ 的一个基，$\varphi_{1},\dots,\varphi_{n}$ 为其对偶基，则对任意 $v \in V$ 有

$$
\begin{gather}
v=\varphi_{1}(v)v_{1}+\dots+\varphi_{n}(v)v_{n}
\end{gather}
$$

#### Proof

设 $v \in V$，则存在唯一的 $c_{1},\dots,c_{n}\in \mathbb{F}$ 使得

$$
\begin{gather}
v=c_{1}v_{1}+\dots+c_{n}v_{n}
\end{gather}
$$

于是我们有

$$
\begin{gather}
\varphi_{j}(v)=\sum_{k=1}^{n} c_{k}\varphi_{j}(v_{k})=c_{j}
\end{gather}
$$

这就完成了证明。

以下结果解释了“对偶基”名字的由来。

### Theorem 3.99

设 $V$ 是有限维向量空间，则 $V$ 的一个基的对偶基是 $V^{*}$ 的一个基。

#### Proof

设 $v_{1},\dots,v_{n}$ 是 $V$ 的基，$\varphi_{1},\dots,\varphi_{n}$ 为其对偶基。

假设

$$
\begin{gather}
a_{1}\varphi_{1}+\dots+a_{n}\varphi_{n}=0
\end{gather}
$$

则

$$
\begin{gather}
(a_{1}\varphi_{1}+\dots+a_{n}\varphi_{n})(v_{k})=\sum_{j=1}^{n} a_{j}\varphi_{j}(v_{k})=a_{k}=0
\end{gather}
$$

因此 $a_{1}=\dots=a_{n}=0$，即 $\varphi_{1},\dots,\varphi_{n}$ 线性无关。又由于对偶基的长度等于 $\dim V^{*}=n$，因此它是 $V^{*}$ 的基。

### Definition 3.100 dual map 对偶映射

设 $T \in L(V,W)$，它的对偶映射是一个 $T^{*}\in L(W^{*},V^{*})$，定义为

$$
\begin{gather}
T^{*}(\varphi)=\varphi \circ T
\end{gather}
$$

我们来验证 $T^{*}$ 的确是一个线性映射：设 $\varphi,\psi \in W^{*},\lambda,\mu \in \mathbb{F}$，则

$$
\begin{gather}
T^{*}(\lambda\varphi+\mu \psi)=(\lambda\varphi+\mu \psi)\circ T=\lambda\varphi \circ T+\mu \psi \circ T=\lambda T^{*}(\varphi)+\mu T^{*}(\psi)
\end{gather}
$$

### Example 3.101

设 $D \in L(\mathcal{P}(\mathbb{R}),\mathcal{P}(\mathbb{R}))$ 为微分算子 $Dp=p'$。

(a) 假设线性泛函 $\varphi$ 定义为 $\varphi(p)=p(3)$，则

$$
\begin{gather}
D^{*}(\varphi)(p)=\varphi \circ D(p)=\varphi(p')=p'(3)
\end{gather}
$$

(b) 假设线性泛函 $\varphi$ 定义为 $\varphi(p)=\int_{0}^{1}p$，则

$$
\begin{gather}
D^{*}(\varphi)(p)=\varphi(p')=\int_{0}^{1} p'=p(1)-p(0)
\end{gather}
$$

### Theorem 3.102

设 $T \in L(V,W)$，则

1. 对任意 $S \in L(V,W)$ 有 $(S+T)^{*}=S^{*}+T^{*}$。
2. 对任意 $\lambda \in \mathbb{F}$ 有 $(\lambda T)^{*}=\lambda T^{*}$。
3. 对任意 $S \in L(W,U)$ 有 $(ST)^{*}=T^{*}S^{*}$。

(1)(2) 表明了从 $L(V,W)$ 到 $L(W^{*},V^{*})$ 的映射 $T\mapsto T^{*}$ 是线性的。

#### Proof

设 $S,T \in L(V,W),\lambda,\mu \in \mathbb{F}$，则对任意 $\varphi \in W^{*}$ 有

$$
\begin{gather}
(\lambda S+\mu T)^{*}(\varphi)=\varphi \circ(\lambda S+\mu T)=\lambda\varphi \circ S+\mu\varphi \circ T=\lambda S^{*}(\varphi)+\mu T^{*}(\varphi)
\end{gather}
$$

即证 $T\mapsto T^{*}$ 是线性映射。

下设 $S \in L(W,U),\varphi \in U^{*}$，则

$$
\begin{gather}
(ST)^{*}(\varphi)=\varphi \circ(ST)=(\varphi \circ S)\circ T=T^{*}(\varphi \circ S)=T^{*}(S^{*}(\varphi))
\end{gather}
$$

即 $(ST)^{*}=T^{*}S^{*}$。

## Null Space and Range of Dual of Linear Map

本节我们的目标是用 $\ker T$ 与 $\operatorname{range}T$ 来描述 $\ker T^{*}$ 与 $\operatorname{range}T^{*}$。为此，我们需要以下定义。

### Definition 3.103 annihilator 零化子

设 $U\subset V$，则 $U$ 的零化子 $U^{0}$ 定义为

$$
\begin{gather}
U^{0}=\{ \varphi \in V^{*}: \varphi(U)=\{ 0 \} \}
\end{gather}
$$

换言之，$U^{0}$ 包含了所有在 $U$ 上消失的 $\varphi$，或者说，所有使得 $U$ 在 $\varphi$ 的作用下“零化”的线性泛函 $\varphi$。

### Example 3.104

设 $e_{1},\dots,e_{5}$ 为 $\mathbb{R}^{5}$ 上的标准基，$\varphi_{1},\dots,\varphi_{5}$ 为其对偶基。假设

$$
\begin{gather}
U=\operatorname{span}(e_{1},e_{2})=\{ (x_{1},x_{2},0,0,0):x_{1},x_{2}\in \mathbb{R} \}
\end{gather}
$$

则我们可以证明 $U^{0}=\operatorname{span}(\varphi_{3},\varphi_{4},\varphi_{5})$。

在 [[#Example 3.97]] 中我们指出 $\varphi_{j}$ 是第 $j$ 个坐标的投影函数

$$
\begin{gather}
\varphi_{j}(x_{1},\dots,x_{5})=x_{j}
\end{gather}
$$

则对于 $\varphi \in \operatorname{span}(\varphi_{3},\varphi_{4},\varphi_{5})$，我们有

$$
\begin{gather}
\varphi(x_{1},x_{2},0,0,0)=(c_{3}\varphi_{3}+c_{4}\varphi_{4}+c_{5}\varphi_{5})(x_{1},x_{2},0,0,0)=0
\end{gather}
$$

因此 $\varphi \in U^{0}$，从而 $\operatorname{span}(\varphi_{3},\varphi_{4},\varphi_{5})\subset U^{0}$。

反之，如果 $\varphi=c_{1}\varphi_{1}+\dots+c_{5}\varphi_{5}\in U^{0}$，则

$$
\begin{gather}
\varphi(e_{1})=c_{1}=0, \quad \varphi(e_{2})=c_{2}=0
\end{gather}
$$

因此 $\varphi\in \operatorname{span}(\varphi_{3},\varphi_{4},\varphi_{5})$。即证 $U^{0}=\operatorname{span}(\varphi_{3},\varphi_{4},\varphi_{5})$。

### Theorem 3.105

设 $U\subset V$，则 $U^{0}$ 是 $V^{*}$ 的一个子空间。

注意以上定理中我们不要求 $U$ 是子空间。

#### Proof

显然 $0 \in U^{0}$。设 $\varphi,\psi \in U^{0},\lambda,\mu \in \mathbb{F}$，则对任意 $u \in U$ 有

$$
\begin{gather}
(\lambda\varphi+\mu \psi)(u)=\lambda\varphi(u)+\mu \psi(u)=\lambda 0+\mu 0=0
\end{gather}
$$

故 $\lambda\varphi+\mu \psi \in U^{0}$。这就完成了证明。

### Theorem 3.106

设 $V$ 是有限维向量空间，$U$ 是 $V$ 的子空间，则

$$
\begin{gather}
\dim U^{0}=\dim V-\dim U
\end{gather}
$$

#### Proof

以上定理的证明是 [[#Example 3.104]] 的一个推广。设 $u_{1},\dots,u_{m}$ 是 $U$ 的基，我们将其扩张为 $V$ 的基 $u_{1},\dots,u_{n}$。设其对偶基为 $\varphi_{1},\dots,\varphi_{n}$，则我们要证 $\varphi_{m+1},\dots,\varphi_{n}$ 是 $U^{0}$ 的一个基。

根据 [[#Theorem 3.99]]，$\varphi_{m+1},\dots,\varphi_{n}$ 是线性无关的，下面我们只需证明 $U^{0}=\operatorname{span}(\varphi_{m+1},\dots,\varphi_{n})$。

设 $\varphi \in \operatorname{span}(\varphi_{m+1},\dots,\varphi_{n}),u \in U$，则由 $\varphi_{j}(u_{k})=\delta_{j,k}$ 得

$$
\begin{gather}
\varphi(u)=\varphi(a_{1}u_{1}+\dots+a_{m}u_{m})=0
\end{gather}
$$

因此 $\varphi \in U^{0}$。

反之，如果 $\varphi=c_{1}\varphi_{1}+\dots+c_{n}\varphi_{n}\in U^{0}$，则对任意 $1\leq j\leq m$ 有

$$
\begin{gather}
\varphi(u_{j})=c_{j}=0
\end{gather}
$$

从而 $\varphi \in \operatorname{span}(\varphi_{m+1},\dots,\varphi_{n})$，这就完成了证明。

### Theorem 3.107

设 $V$ 是有限维向量空间，$U$ 是 $V$ 的子空间，则

1. $U^{0}=\{ 0 \}$ 当且仅当 $U=V$，
2. $U^{0}=V^{*}$ 当且仅当 $U=\{ 0 \}$。

#### Proof

(1) 我们有等价链

$$
\begin{align}
U^{0}=\{ 0 \}\iff \dim U^{0}=0\iff \dim U=\dim V\iff U=V
\end{align}
$$

(2) 我们有

$$
\begin{align}
U^{0}=V^{*}\iff \dim U^{0}=\dim V\iff \dim U=0\iff U=\{ 0 \}
\end{align}
$$

其中我们用到了 $\dim V=\dim V^{*}$。

### Theorem 3.108

设 $V,W$ 是有限维的，$T \in L(V,W)$，则

1. $\ker T^{*}=(\operatorname{range}T)^{0}$，
2. $\dim \ker T^{*}=\dim \ker T+\dim W-\dim V$。

其中命题 (1) 对无限维的 $V,W$ 也适用。

#### Proof

(2) 是 (1) 和秩-零化度定理的直接推论。下面关于 (1) 的证明不依赖于 $V,W$ 有限维的假设。

设 $\varphi \in \ker T^{*}$，即 $T^{*}(\varphi)=\varphi \circ T=0$，因此对任意 $v \in V$ 有

$$
\begin{gather}
\varphi(Tv)=0
\end{gather}
$$

这就是说 $\varphi$ 将所有 $Tv \in \operatorname{range}T$ 零化了，$\ker T^{*}\subset (\operatorname{range}T)^{0}$。

再设 $\varphi \in(\operatorname{range}T)^{0}$，则对任意 $v \in V$ 有

$$
\begin{gather}
\varphi(Tv)=T^{*}(\varphi)(v)=0
\end{gather}
$$

从而 $T^{*}(\varphi)=0$，$(\operatorname{range}T)^{0}\subset \ker T^{*}$。这就完成了证明。

下一个定理有时是有用的，因为通常来说，验证单射性比验证满射性更容易。

### Theorem 3.109

设 $V,W$ 是有限维的，$T \in L(V,W)$，则 $T$ 是满射当且仅当 $T^{*}$ 是单射。

#### Proof

根据 [[#Theorem 3.107]] 与 [[#Theorem 3.108]]，$T$ 是满射（$\operatorname{range}T=W$）当且仅当 $\ker T^{*}=(\operatorname{range}T)^{0}=\{ 0 \}$，即 $T^{*}$ 是单射。

### Theorem 3.110

设 $V,W$ 是有限维的，$T \in L(V,W)$，则

1. $\dim \operatorname{range}T^{*}=\dim \operatorname{range}T$，
2. $\operatorname{range}T^{*}=(\ker T)^{0}$。

#### Proof

(1) 我们有

$$
\begin{align}
\dim \operatorname{range}T^{*}&= \dim W-\dim \ker T^{*} \\
&=\dim W-\dim(\operatorname{range}T)^{0} \\
&=\dim W-(\dim W-\dim \operatorname{range}T) \\
&=\dim \operatorname{range}T
\end{align}
$$

(2) 首先设 $\varphi \in \operatorname{range}T^{*}$，则存在 $\psi \in W^{*}$ 使得 $\varphi=T^{*}(\psi)$。如果 $v \in \ker T$，则

$$
\begin{gather}
\varphi(v)=\psi(Tv)=\psi(0)=0
\end{gather}
$$

因此 $\varphi(\ker T)=\{ 0 \}$，$\operatorname{range}T^{*}\subset(\ker T)^{0}$。

要得到另一个方向的包含，我们可以证明两个空间的维度相同。注意到

$$
\begin{align}
\dim \operatorname{range}T^{*}=\dim \operatorname{range}T=\dim V-\dim \ker T=\dim(\ker T)^{0}
\end{align}
$$

这就完成了证明。

### Theorem 3.111

设 $V,W$ 是有限维的，$T \in L(V,W)$，则 $T$ 是单射当且仅当 $T^{*}$ 是满射。

#### Proof

与 [[#Theorem 3.109]] 同理，$T$ 是单射当且仅当 $\ker T=\{ 0 \}$，当且仅当 $(\ker T)^{0}=\operatorname{range}T^{*}=V^{*}$，即 $T^{*}$ 是满射。

## Matrix of Dual of Linear Map

在下面的定理中，我们假设有 $V$ 的基 $v_{1},\dots,v_{n}$，连带着它在 $V^{*}$ 中的对偶基 $\varphi_{1},\dots,\varphi_{n}$，以及 $W$ 的基 $w_{1},\dots,w_{m}$ 和对偶基 $\psi_{1},\dots,\psi_{m}$。而矩阵 $\mathcal{M}(T)$ 是通过 $V,W$ 上的基构造的，$\mathcal{M}(T^{*})$ 是通过 $W^{*},V^{*}$ 上的对偶基构造的。

### Theorem 3.112

设 $V,W$ 是有限维的，$T \in L(V,W)$，则

$$
\begin{gather}
\mathcal{M}(T^{*})=\mathcal{M}(T)^{T}
\end{gather}
$$

#### Proof

设 $A=\mathcal{M}(T),C=\mathcal{M}(T^{*})$，则

$$
\begin{gather}
T^{*}(\psi_{j})=\sum_{r=1}^{n} C_{r,j}\varphi_{r}
\end{gather}
$$

于是

$$
\begin{align}
T^{*}(\psi_{j})(v_{k})=\sum_{r=1}^{n} C_{r,j}\varphi_{r}(v_{k})=C_{k,j}
\end{align}
$$

另一方面，我们有

$$
\begin{align}
T^{*}(\psi_{j})(v_{k}) &= \psi_{j}(Tv_{k}) \\
&=\psi_{j} \sum_{r=1}^{m} A_{r,k}w_{r} \\
&=\sum_{r=1}^{m} A_{r,k}\psi_{j}(w_{r}) \\
&=A_{j,k}
\end{align}
$$

因此 $A_{j,k}=C_{k,j}$，即 $\mathcal{M}(T^{*})=\mathcal{M}(T)^{T}$。

我们将应用对偶性来给出矩阵行秩等于列秩的第二个证明。

### Theorem 3.113

设 $A \in \mathbb{F}^{m,n}$，则 $A$ 的行秩等于 $A$ 的列秩。

#### Proof

定义 $T\colon \mathbb{F}^{n,1}\to \mathbb{F}^{m,1}$ 为 $Tx=Ax$，则在标准基下有 $A=\mathcal{M}(T)$。于是我们有

$$
\begin{align}
\operatorname{colrank} A&= \operatorname{colrank} \mathcal{M}(T) \\
&=\dim \operatorname{range}T \\
&=\dim \operatorname{range}T^{*} \\
&=\operatorname{colrank} \mathcal{M}(T^{*}) \\
&=\operatorname{colrank} A^{T} \\
&=\operatorname{rowrank} A
\end{align}
$$

其中我们用 $\operatorname{colrank}$ 和 $\operatorname{rowrank}$ 表示列秩与行秩。