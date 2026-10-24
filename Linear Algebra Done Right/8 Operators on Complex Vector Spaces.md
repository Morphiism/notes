本章我们进一步研究向量空间上算子的结构，它可以视为 [[5 Eigenvalues and Eigenvectors]] 的延续。在第五章中我们提到，即使是在有限维的复向量空间上，一个算子可能也没有足够的特征向量以对角化，因此本章我们将引入一种广义特征向量，在有限维空间上算子的广义特征向量总是能够构成一个基，从而算子的所谓广义特征分解就给出了它的一种良好的描述。

本章我们假设 $V$ 是 $\mathbb{F}$ 上的有限维非零向量空间。

# 8A Generalized Eigenvectors and Nilpotent Operators

## Null Spaces of Powers of an Operator

### Theorem 8.1

设 $T \in L(V)$，则

$$
\begin{gather}
\{ 0 \}\subset \ker T \subset \ker T^{2}\subset\cdots \subset \ker T^{k}\subset \ker T^{k+1}\subset\cdots
\end{gather}
$$

#### Proof

设 $v \in \ker T^{k}$，则 $T^{k}v=0$，从而 $T^{k+1}=T(T^{k}v)=0$，即 $v \in \ker T^{k+1}$。

### Theorem 8.2

设 $T \in L(V)$ 且存在非负整数 $m$ 使得

$$
\begin{gather}
\ker T^{m}=\ker T^{m+1}
\end{gather}
$$

则

$$
\begin{gather}
\ker T^{m}=\ker T^{m+1}=\ker T^{m+2}=\ker T^{m+3}=\cdots
\end{gather}
$$

#### Proof

设 $k$ 是正整数，我们来证明 $\ker T^{m+k}=\ker T^{m+k+1}$。

显然 $\ker T^{m+k}\subset \ker T^{m+k+1}$。设 $v \in \ker T^{m+k+1}$，则

$$
\begin{gather}
T^{m+1}(T^{k}v)=T^{m+k+1}v=0
\end{gather}
$$

即 $T^{k}v \in \ker T^{m+1}$，从而 $T^{k}v \in \ker T^{m}$，于是

$$
\begin{gather}
T^{m+k}v=T^{m}(T^{k}v)=0
\end{gather}
$$

即证 $v \in \ker T^{m+k}$。

以上两个定理对任意维数的向量空间成立。下面我们证明，在有限维空间上，算子的零空间至多在 $m=\dim V$ 时就停止增长。

### Theorem 8.3

设 $T \in L(V)$，则

$$
\begin{gather}
\ker T^{\dim V}=\ker T^{\dim V+1}=\ker T^{\dim V+2}=\cdots
\end{gather}
$$

#### Proof

根据 [[#Theorem 8.2]]，我们只需证明 $\ker T^{\dim V}=\ker T^{\dim V+1}$。假设等式不成立，则我们有

$$
\begin{gather}
\{ 0 \}\subsetneq \ker T \subsetneq \ker T^{2} \subsetneq \cdots \subsetneq \ker T^{\dim V} \subsetneq \ker T^{\dim V+1}
\end{gather}
$$

在上述包含链中，每相邻的两项均具有不同的维数，否则它们将相等。因此

$$
\begin{gather}
\dim \ker T^{\dim V+1}\geq \dim V+1
\end{gather}
$$

这与 $\ker T^{\dim V+1}\subset V$ 矛盾。

### Theorem 8.4

设 $T \in L(V)$，则

$$
\begin{gather}
V=\ker T^{\dim V} \oplus  \operatorname{range}T^{\dim V}
\end{gather}
$$

#### Proof

设 $n=\dim V$，我们首先证明

$$
\begin{gather}
\ker T^{n} \cap \operatorname{range}T^{n}=\{ 0 \}
\end{gather}
$$

设 $v \in \ker T^{n}\cap \operatorname{range}T^{n}$，则存在 $u \in V$ 使得 $v=T^{n}u$，并且 $T^{n}v=T^{2n}u=0$。由于算子的零空间在 $\dim V$ 次之后停止增长，故 $T^{n}u=0$，从而 $v=0$。

因此我们可知 $\ker T^{n}+\operatorname{range}T^{n}$ 是一个直和。此外，根据 $T^{n}$ 的秩-零化度定理，有

$$
\begin{gather}
\dim(\ker T^{n}\oplus \operatorname{range}T^{n})=\dim \ker T^{n}+\dim \operatorname{range}T^{n}=\dim V
\end{gather}
$$

从而 $\ker T^{n}\oplus \operatorname{range}T^{n}=V$。

## Generalized Eigenvectors

### Definition 8.5 generalized eigenvector 广义特征向量

设 $T \in L(V)$ 且 $\lambda$ 是 $T$ 的特征值，称 $v \in V$ 是 $T$ 的一个广义特征向量，如果 $v\neq 0$ 且存在正整数 $k$ 使得

$$
\begin{gather}
(T-\lambda I)^{k}v=0
\end{gather}
$$

根据 [[#Theorem 8.1]] 和 [[#Theorem 8.3]]，我们可知 $v$ 是一个广义特征向量当且仅当 $(T-\lambda I)^{\dim V}v=0$。

我们前面提到，一般的向量空间上不一定有足够的特征向量来构成一个基，下面的结果正是我们引入广义特征向量的初始动机。

### Theorem 8.6

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则 $V$ 有一个由 $T$ 的广义特征向量构成的基。

#### Proof

设 $n=\dim V$，我们对 $n$ 进行归纳。$n=1$ 的情况是平凡的：任何非零向量都是 $T$ 的特征向量。

假设 $n>1$ 且定理对维数更低的空间成立。令 $\lambda$ 为 $T$ 的特征值，则我们有

$$
\begin{gather}
V=\ker(T-\lambda I)^{n}\oplus  \operatorname{range}(T-\lambda I)^{n}
\end{gather}
$$

如果 $\ker(T-\lambda I)^{n}=V$，那么每个非零向量都是 $T$ 的广义特征向量，我们没有什么可证的。现在设 $\ker(T-\lambda I)^{n}\neq V$，又因为 $\lambda$ 是特征值，故 $\ker(T-\lambda I)^{n}\neq \{ 0 \}$，因此

$$
\begin{gather}
0<\dim \operatorname{range}(T-\lambda I)^{n}<n
\end{gather}
$$

由于 $\operatorname{range}(T-\lambda I)^{n}$ 在 $T$ 下不变，我们对 $S=T|_{\operatorname{range}(T-\lambda I)^{n}}$ 应用归纳假设，可得 $\operatorname{range}(T-\lambda I)^{n}$ 的一个由 $T$ 的广义特征向量构成的基，将它与 $\ker(T-\lambda I)^{n}$ 的基合并即可得到 $V$ 的一个由广义特征向量构成的基。

### Theorem 8.7

设 $T \in L(V)$，则 $T$ 的每个广义特征向量都对应于唯一的一个特征值。

#### Proof

假设 $v \in V$ 是对应于特征值 $\alpha$ 和 $\lambda$ 的广义特征向量。设 $m$ 为使得 $(T-\alpha I)^{m}v=0$ 的最小正整数，令 $n=\dim V$，则

$$
\begin{align}
0 &=(T-\lambda I)^{n}v \\
&= ((T-\alpha I)+(\alpha-\lambda)I)^{n}v \\
&= \sum_{k=0}^{n} \binom{n}{k} (\alpha-\lambda)^{n-k}(T-\alpha I)^{k}v
\end{align}
$$

两边应用 $(T-\alpha I)^{m-1}$，则有

$$
\begin{gather}
(\alpha-\lambda)^{n}(T-\alpha I)^{m-1}v=0
\end{gather}
$$

由于 $(T-\alpha I)^{m-1}v\neq 0$，故 $\alpha=\lambda$。因此 $v$ 对应的特征值是唯一的。

### Theorem 8.8

设 $T \in L(V)$，则 $T$ 的任意一组对应于不同特征值的广义特征向量是线性无关的。

#### Proof

我们用反证法。假设存在一个最小的正整数 $m$，使得 $T$ 的对应于特征值 $\lambda_{1},\dots,\lambda_{m}$ 的广义特征向量 $v_{1},\dots,v_{m}$ 线性相关。则存在不为零（否则与 $m$ 的极小性矛盾）的标量 $a_{1},\dots,a_{m}$ 使得

$$
\begin{gather}
a_{1}v_{1}+\dots+a_{m}v_{m}=0
\end{gather}
$$

令 $n=\dim V$，对等式两边应用 $(T-\lambda_{m}I)^{n}$，则有

$$
\begin{gather}
a_{1}(T-\lambda_{m}I)^{n}v_{1}+\dots+a_{m-1}(T-\lambda_{m}I)^{n}v_{m-1}=0
\end{gather}
$$

由于各特征值互不相等，根据 [[#Theorem 8.7]]，对 $k=1,\dots,m-1$ 有

$$
\begin{gather}
(T-\lambda_{m}I)^{n}v_{k}\neq 0
\end{gather}
$$

因为否则 $v_{k}$ 将对应于特征值 $\lambda_{k}$ 与 $\lambda_{m}$。进一步，等式

$$
\begin{gather}
(T-\lambda_{k}I)^{n}(T-\lambda_{m}I)^{n}v_{k}=(T-\lambda_{m}I)^{n}(T-\lambda_{k}I)^{n}v_{k}=0
\end{gather}
$$

表明 $(T-\lambda_{m}I)^{n}v_{k}$ 是对应于 $\lambda_{k}$ 的广义特征向量，因此

$$
\begin{gather}
(T-\lambda_{m}I)^{n}v_{1},\dots,(T-\lambda_{m}I)^{n}v_{m-1}
\end{gather}
$$

是一组对应于不同特征值的线性相关的广义特征向量，这与 $m$ 的极小性矛盾。

## Nilpotent Operators

### Definition 8.9 nilpotent 幂零的

一个算子 $T$ 称为是幂零的，如果存在正整数 $k$ 使得 $T^{k}=0$。

特别地，一个算子 $T \in L(V)$ 是幂零的当且仅当任何非零向量都是 $T$ 的对应于特征值 $0$ 的广义特征向量。

### Theorem 8.10

设 $T \in L(V)$ 是幂零的，则 $T^{\dim V}=0$。

#### Proof

根据定义，存在正整数 $k$ 使得 $\ker T^{k}=V$，于是 [[#Theorem 8.1]] 和 [[#Theorem 8.3]] 表明 $\ker T^{\dim V}=V$，即 $T^{\dim V}=0$。

### Theorem 8.11

设 $T \in L(V)$。

1. 如果 $T$ 是幂零算子，则 $0$ 是 $T$ 的唯一特征值。
2. 如果 $\mathbb{F}=\mathbb{C}$ 且 $0$ 是 $T$ 的唯一特征值，则 $T$ 是幂零算子。

#### Proof

(1) 首先我们证明 $0$ 是特征值。由于 $T$ 是幂零的，故存在 $m$ 使得 $T^{m}=0$，这表明 $T$ 不是单射，因而 $0$ 是 $T$ 的特征值。

下设 $T$ 有特征值 $\lambda$，对应的特征向量为 $v$，则 $Tv=\lambda v$。两边应用 $T^{m-1}$ 即得

$$
\begin{gather}
T^{m}v=\lambda^{m}v=0
\end{gather}
$$

即 $\lambda=0$。

(2) 设 $\mathbb{F}=\mathbb{C}$ 且 $0$ 是唯一特征值，根据 [[5 Eigenvalues and Eigenvectors#Theorem 5.19]]，$T$ 的极小多项式具有形式 $z^{m}$，其中 $m$ 是正整数，于是 $T^{m}=0$，即证 $T$ 是幂零的。

### Theorem 8.12

设 $T \in L(V)$，则如下命题等价。

(a) $T$ 是幂零算子。

(b) $T$ 的极小多项式具有形式 $z^{m}$。

(c) 存在 $V$ 的一个基，使得 $T$ 在该基下的矩阵具有形式
$$
\begin{gather}
\begin{pmatrix}
0 & & \ast \\
 & \ddots &  \\
0 & & 0 
\end{pmatrix}
\end{gather}
$$
其中对角线及以下的元素均为零。

#### Proof

设 (a) 成立，则存在 $n$ 使得 $T^{n}=0$。因此 $z^{n}$ 是 $T$ 的零化多项式，从而被 $T$ 的极小多项式整除。这表明 $T$ 的极小多项式具有形式 $z^{m}$。

设 (b) 成立，根据上三角化的充要条件 [[5 Eigenvalues and Eigenvectors#Theorem 5.30]]，$T$ 在某个基下有上三角矩阵，且对角线元素为 $T$ 的特征值。然而，$T$ 的特征值恰是 $T$ 的极小多项式的零点，因此矩阵的对角线元素均为零。

设 (c) 成立，则显然我们有 $T^{\dim V}=0$，从而 $T$ 是幂零的。

# 8B Generalized Eigenspace Decomposition

## Generalized Eigenspaces

### Definition 8.13 generalized eigenspace 广义特征空间

设 $T \in L(V)$ 且 $\lambda \in \mathbb{F}$。$T$ 的对应于 $\lambda$ 的广义特征空间 $G(\lambda,T)$ 定义为

$$
\begin{gather}
G(\lambda,T)=\{ v \in V : \exists k, (T-\lambda I)^{k}v=0 \}
\end{gather}
$$

于是，如果 $\lambda$ 是 $T$ 的特征值，那么 $G(\lambda,T)$ 就是对应于 $\lambda$ 的所有广义特征向量构成的空间。显然 $E(\lambda,T)\subset G(\lambda,T)$。

### Theorem 8.14

设 $T \in L(V)$ 且 $\lambda \in \mathbb{F}$，则 $G(\lambda,T)=\ker(T-\lambda I)^{\dim V}$。

#### Proof

我们已证明 $v$ 是广义特征向量当且仅当 $(T-\lambda I)^{\dim V}v=0$，这等价于 $G(\lambda,T)=\ker(T-\lambda I)^{\dim V}$。

### Theorem 8.15

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，令 $\lambda_{1},\dots,\lambda_{m}$ 为 $T$ 的不同特征值，则

1. $G(\lambda_{k},T)$ 在 $T$ 下不变，
2. $(T-\lambda_{k}I)|_{G(\lambda_{k},T)}$ 是幂零算子，
3. $V=G(\lambda_{1},T)\oplus\dots \oplus G(\lambda_{m},T)$。

#### Proof

(1) 由于 $G(\lambda_{k},T)=\ker(T-\lambda_{k}I)^{\dim V}$，故它在 $T$ 下不变。

(2) 如果 $v \in G(\lambda_{k},T)$，则 $(T-\lambda_{k}I)^{\dim V}v=0$，因此

$$
\begin{gather}
((T-\lambda_{k} I)|_{G(\lambda_{k},T)})^{\dim V}=0
\end{gather}
$$

即 $(T-\lambda_{k}I)|_{G(\lambda_{k},T)}$ 是幂零的。

(3) 设

$$
\begin{gather}
v_{1}+\dots+v_{m}=0, \quad v_{k} \in G(\lambda_{k},T)
\end{gather}
$$

由于对应于不同特征值的广义特征向量线性无关，因此每个 $v_{k}=0$，从而 $G(\lambda_{1},T)+\dots+G(\lambda_{m},T)$ 是直和。

根据 [[#Theorem 8.6]]，每个 $v \in V$ 都可以唯一地表示为广义特征向量的线性组合，因此

$$
\begin{gather}
V=G(\lambda_{1},T)\oplus \dots \oplus G(\lambda_{m},T)
\end{gather}
$$

## Multiplicity of an Eigenvalue

### Definition 8.16 multiplicity 重数

设 $T \in L(V)$，$T$ 的特征值 $\lambda$ 的重数定义为 $\dim G(\lambda,T)$。等价地，$\lambda$ 的重数定义为 $\dim \ker(T-\lambda I)^{\dim V}$。

在一些教材中将 $\dim G(\lambda,T)$ 定义为 $\lambda$ 的代数重数，因为它是 $\lambda$ 作为 $T$ 的特征多项式的零点的重数。相对地，$\lambda$ 的几何重数定义为 $\dim E(\lambda,T)$。容易证明，$T$ 可对角化当且仅当对 $T$ 的所有特征值 $\lambda$，其代数重数等于几何重数。

$T$ 的广义特征空间分解 $V=G(\lambda_{1},T)\oplus\dots \oplus G(\lambda_{m},T)$ 立即给出：

### Theorem 8.17

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则 $T$ 的所有特征值的重数之和等于 $\dim V$。

### Definition 8.18 characteristic polynomial 特征多项式

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，令 $\lambda_{1},\dots,\lambda_{m}$ 为 $T$ 的不同特征值，其重数分别为 $d_{1},\dots,d_{m}$，则

$$
\begin{gather}
(z-\lambda_{1})^{d_{1}}\cdots (z-\lambda_{m})^{d_{m}}
\end{gather}
$$

称为 $T$ 的特征多项式。

### Theorem 8.19

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则

1. $T$ 的特征多项式具有次数 $\dim V$，
2. $T$ 的特征多项式的零点恰是 $T$ 的特征值。

#### Proof

(1) 由 [[#Theorem 8.17]] 给出。(2) 由特征多项式的定义得到。

### Theorem 8.20 (Cayley-Hamilton)

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，$q$ 是 $T$ 的特征多项式，则 $q(T)=0$。

#### Proof

设 $T$ 的特征多项式为

$$
\begin{gather}
q(z)=(z-\lambda_{1})^{d_{1}}\cdots (z-\lambda_{m})^{d_{m}}
\end{gather}
$$

由于 $(T-\lambda_{k}I)|_{G(\lambda_{k},T)}$ 是幂零的，故 $(T-\lambda_{k}I)^{d_{k}}|_{G(\lambda_{k},T)}=0$。

根据 $T$ 的广义特征空间分解，每个向量都可以分解为广义特征向量之和，因此我们只需证明 $q(T)|_{G(\lambda_{k},T)}=0$。

然而，

$$
\begin{gather}
q(T)=(T-\lambda_{1}I)^{d_{1}}\cdots (T-\lambda_{m}I)^{d_{m}}
\end{gather}
$$

以上的各因子是交换的，因此我们可以将 $(T-\lambda_{k}I)^{d_{k}}$ 移动到最右端，从而对 $v \in G(\lambda_{k},T)$ 有 $q(T)v=0$，即 $q(T)|_{G(\lambda_{k},T)}=0$。

### Corollary 8.21

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则 $T$ 的特征多项式是 $T$ 的极小多项式的多项式倍。

以上定理表明，如果 $T$ 的极小多项式的次数等于 $\dim V$，那么 $T$ 的极小多项式就是 $T$ 的特征多项式。

前面我们已经证明，如果算子关于某个基有上三角矩阵，那么对角线上的元素是 $T$ 的特征值。以下的定理加强了上面的结果。

### Theorem 8.22

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$。设 $T$ 在 $V$ 的基 $v_{1},\dots,v_{n}$ 下有上三角矩阵 $\mathcal{M}(T)$，则 $\mathcal{M}(T)$ 对角线上 $\lambda$ 出现的次数等于 $\lambda$ 作为 $T$ 的特征值的重数。

#### Proof

设 $A=\mathcal{M}(T)$，则 $A$ 是上三角矩阵，其对角线元素设为 $\lambda_{1},\dots,\lambda_{n}$。则我们有

$$
\begin{gather}
Tv_{k}=u_{k}+\lambda_{k}v_{k}
\end{gather}
$$

其中 $u_{k}\in \operatorname{span}(v_{1},\dots,v_{k-1})$。因此如果 $\lambda_{k}\neq 0$，那么 $Tv_{k}$ 不是 $Tv_{1},\dots,Tv_{k-1}$ 的线性组合。因此，满足 $\lambda_{k}\neq 0$ 的 $Tv_{k}$ 构成的组是线性无关的。

令 $d$ 表示满足 $\lambda_{k}=0$ 的 $k$ 的数量。则我们有

$$
\begin{gather}
\dim \operatorname{range}T\geq n-d
\end{gather}
$$

从而

$$
\begin{gather}
\dim \ker T\leq d
\end{gather}
$$

算子 $T^{n}$ 在 $v_{1},\dots,v_{n}$ 下的矩阵是 $A^{n}$，根据矩阵乘法的定义，$A^{n}$ 也是一个上三角矩阵，其对角线元素为 $\lambda_{1}^{n},\dots,\lambda_{n}^{n}$。由于 $\lambda_{k}^{n}=0$ 当且仅当 $\lambda_{k}=0$，故

$$
\begin{gather}
\dim \ker T^{n}\leq d \tag{8.22.1}
\end{gather}
$$

设 $\lambda$ 是 $T$ 的特征值，令 $m_{\lambda}$ 为 $\lambda$ 的重数，$d_{\lambda}$ 为 $\lambda$ 在 $A$ 的对角线上出现的次数，在 $(8.22.1)$ 中用 $T-\lambda I$ 替换 $T$，我们就有

$$
\begin{gather}
m_{\lambda}\leq d_{\lambda} \tag{8.22.2}
\end{gather}
$$

然而，所有特征值的重数之和 $\sum_{\lambda}m_{\lambda}=\dim V=\sum_{\lambda}d_{\lambda}$，因此 $(8.22.2)$ 必然是一个等式，这就完成了证明。

## Block Diagonal Matrices

本章我们将广义特征空间分解的理论解释为矩阵形式，它极大地改进了前面我们关于矩阵上三角化的理论。

### Definition 8.23 block diagonal matrix 分块对角矩阵

称一个方阵是分块对角矩阵，如果它具有形式

$$
\begin{gather}
\begin{pmatrix}
A_{1} &  & 0 \\
 & \ddots &  \\
0 &  & A_{m}
\end{pmatrix}
\end{gather}
$$

其中 $A_{1},\dots,A_{m}$ 是放置在对角线上的方阵，其它所有元素均为 $0$。

### Theorem 8.24

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，令 $\lambda_{1},\dots,\lambda_{m}$ 为 $T$ 的不同特征值，其重数为 $d_{1},\dots,d_{m}$。则存在 $V$ 的一个基使得 $T$ 在这个基下有分块对角矩阵

$$
\begin{gather}
\begin{pmatrix}
A_{1} &  & 0 \\
 & \ddots &  \\
0 &  & A_{m}
\end{pmatrix}
\end{gather}
$$

其中 $A_{k}$ 是一个具有以下形式的 $d_{k}\times d_{k}$ 方阵：

$$
\begin{gather}
A_{k}=\begin{pmatrix}
\lambda_{k} &  & \ast \\
 & \ddots &  \\
0 &  & \lambda_{k}
\end{pmatrix}
\end{gather}
$$

#### Proof

每个 $(T-\lambda_{k}I)|_{G(\lambda_{k},T)}$ 都是幂零的，因此根据 [[#Theorem 8.12]]，存在 $G(\lambda_{k},T)$ 的一个基使得 $(T-\lambda_{k}I)|_{G(\lambda_{k},T)}$ 在这个基下的矩阵是上三角的，且对角线上均为零。于是，由于 $T|_{G(\lambda_{k},T)}=(T-\lambda_{k}I)|_{G(\lambda_{k},T)}+\lambda_{k}I|_{G(\lambda_{k},T)}$，在这个基下 $T|_{G(\lambda_{k},T)}$ 的矩阵具有 $A_{k}$ 的形式。

由于 $V=G(\lambda_{1},T)\oplus\dots \oplus G(\lambda_{m},T)$，在每个子空间上取类似的基即可得到 $V$ 的一个基，在这个基下 $T$ 就有所求的分块对角矩阵。

# 8C Consequences of Generalized Eigenspace Decomposition

## Square Roots of Operators

在上一章我们定义了算子 $T$ 的平方根是算子 $R$ 使得 $R^{2}=T$。任何复数都有平方根，但复向量空间上的算子不一定总是有平方根。本节我们来证明，复向量空间上的可逆算子总是有平方根。

### Lemma 8.25

设 $T \in L(V)$ 是幂零算子，则 $I+T$ 有平方根。

#### Proof

受到 Taylor 级数

$$
\begin{gather}
\sqrt{ 1+x }=1+a_{1}x+a_{2}x^{2}+\cdots
\end{gather}
$$

的启发，我们可以猜测 $I+T$ 的平方根也具有

$$
\begin{gather}
I+a_{1}T+a_{2}T^{2}+\cdots
\end{gather}
$$

的形式。由于 $T$ 是幂零的，设 $T^{m}=0$，则我们只需考虑形如

$$
\begin{gather}
I+a_{1}T+a_{2}T^{2}+\dots+a_{m-1}T^{m-1}
\end{gather}
$$

的算子，并假设它的平方

$$
\begin{multline}
(I+a_{1}T+a_{2}T^{2}+\dots+a_{m-1}T^{m-1})^{2} \\
= I+2a_{1}T+(2a_{2}+a_{1}^{2})T^{2}+(2a_{3}+2a_{1}a_{2})T^{3}+\dots+c_{m-1}T^{m-1}
\end{multline}
$$

等于 $I+T$，其中 $T^{k}$ 项的系数 $c_{k}$ 形如 $2a_{k}$ 加上若干与 $a_{1},\dots,a_{k-1}$ 有关的项。我们令

$$
\begin{gather}
2a_{1}=1 \\
2a_{2}+a_{1}^{2}=0 \\
2a_{3}+2a_{1}a_{2}=0 \\
\vdots \\
c_{m-1}=0
\end{gather}
$$

然后从上往下依次求解 $a_{k}$，即证 $I+T$ 的平方根的存在性。

### Theorem 8.26

设 $V$ 是复向量空间，$T \in L(V)$ 是可逆算子，则 $T$ 有平方根。

#### Proof

设 $\lambda_{1},\dots,\lambda_{m}$ 是 $T$ 的不同特征值，则对每个 $k$，存在幂零算子 $T_{k}$ 使得 $T|_{G(\lambda_{k},T)}=\lambda_{k}I+T_{k}$。由于 $T$ 是可逆的，故 $\lambda_{k}\neq 0$，从而

$$
\begin{gather}
T|_{G(\lambda_{k},T)}=\lambda_{k}\left( I+\frac{T_{k}}{\lambda_{k}} \right)
\end{gather}
$$

显然 $T_{k} /\lambda_{k}$ 是幂零的，因此 [[#Lemma 8.25]] 表明 $I+T_{k} /\lambda_{k}$ 有平方根。$\lambda_{k}$ 是一个复数，因此它也有平方根。我们定义 $R_{k}$ 为以上两个平方根的乘积，则 $R_{k}^{2}=T|_{G(\lambda_{k},T)}$。

根据广义特征空间分解，每个 $v \in V$ 可以唯一地写成

$$
\begin{gather}
v=u_{1}+\dots+u_{m}
\end{gather}
$$

其中 $u_{k}\in G(\lambda_{k},T)$。定义 $R \in L(V)$ 为

$$
\begin{gather}
Rv=R_{1}u_{1}+\dots+R_{m}u_{m}
\end{gather}
$$

则我们有 $R^{2}=T$。

利用本质上相同的技术（展开 $(I+a_{1}T+\dots+a_{m-1}T^{m-1})^{k}$ 然后令对应系数相等），我们可以证明如果 $T$ 是幂零算子，那么 $I+T$ 有 $k$ 次根，从而复向量空间上的可逆算子总有 $k$ 次根。

## Jordan Form

我们已经知道，如果 $V$ 是复向量空间，那么每个 $T \in L(V)$ 都有一个良好的上三角矩阵（[[#Theorem 8.24]]）。在本节中，我们将看到，这一结果可以进一步加强：存在 $V$ 的一个基使得 $T$ 在这个基下的矩阵只有对角线和上方的副对角线有非零元素。

要说明后续定义的动机，我们首先来看两个幂零算子的例子。

### Example 8.27

(a) 设 $T \in L(\mathbb{C}^{4})$ 定义为

$$
\begin{gather}
T(z_{1},z_{2},z_{3},z_{4})=(0,z_{1},z_{2},z_{3})
\end{gather}
$$

则 $T^{4}=0$。如果 $v=(1,0,0,0)$，那么 $T^{3}v,T^{2}v,Tv,v$ 是 $\mathbb{C}^{4}$ 的一个基，在这个基下 $T$ 的矩阵为

$$
\begin{gather}
\begin{pmatrix}
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix}
\end{gather}
$$

(b) 设 $T \in L(\mathbb{C}^{6})$ 定义为

$$
\begin{gather}
T(z_{1},z_{2},z_{3},z_{4},z_{5},z_{6})=(0,z_{1},z_{2},0,z_{4},0)
\end{gather}
$$

则 $T^{3}=0$。与 (a) 不同，此时不存在 $v$ 使得 $T^{5}v,T^{4}v,T^{3}v,T^{2}v,Tv,v$ 是 $\mathbb{C}^{6}$ 的基。然而，如果我们取 $v_{1}=e_{1},v_{2}=e_{4},v_{3}=e_{6}$，其中 $e_{k}$ 是第 $k$ 个标准基向量，那么 $T^{2}v_{1},Tv_{1},v_{1},Tv_{2},v_{2},v_{3}$ 是 $\mathbb{C}^{6}$ 的一个基，在这个基下 $T$ 的矩阵为

$$
\begin{gather}
\begin{pmatrix}
\underline{0} & \underline{1} & \underline{0} & 0 & 0 & 0 \\
\underline{0} & \underline{0} & \underline{1} & 0 & 0 & 0 \\
\underline{0} & \underline{0} & \underline{0} & 0 & 0 & 0 \\
0 & 0 & 0 & \underline{0} & \underline{1} & 0 \\
0 & 0 & 0 & \underline{0} & \underline{0} & 0 \\
0 & 0 & 0 & 0 & 0 & \underline{0}
\end{pmatrix}
\end{gather}
$$

其中我们可以将其视为一个分块对角矩阵，对角线上的分块 $A_{1},A_{2},A_{3}$ 形如 (a) 中的矩阵。

下面我们就要来证明，每个幂零算子 $T \in L(V)$ 都与上面的例子类似。也就是说，存在 $V$ 中的向量 $v_{1},\dots,v_{n}$，使得 $V$ 的一个基由形如 $T^{j}v_{k}$ 的向量组成，其中 $1\leq k\leq n$，而 $j$ 从 $0$ 遍历到最大的 $m_{k}$ 使得 $T^{m_{k}}v_{k}\neq 0$。在这个基下，$T$ 的矩阵如 [[#Example 8.27]](b) 所示。

### Definition 8.28 Jordan basis

设 $T \in L(V)$，称 $V$ 的一个基为 $T$ 的 Jordan 基，如果在这个基下 $T$ 有分块对角矩阵

$$
\begin{gather}
\begin{pmatrix}
A_{1} &  & 0 \\
 & \ddots &  \\
0 &  & A_{p}
\end{pmatrix}
\end{gather}
$$

其中 $A_{k}$ 是一个上三角矩阵，具有形式

$$
\begin{gather}
A_{k}=\begin{pmatrix}
\lambda_{k} & 1 &  & 0 \\
 & \ddots & \ddots &  \\
 &  & \ddots & 1 \\
0 &  &  & \lambda_{k}
\end{pmatrix}
\end{gather}
$$

### Lemma 8.29

设 $T \in L(V)$ 是幂零算子，则存在 $V$ 的一个基使得它是 $T$ 的 Jordan 基。

#### Proof

我们对 $\dim V$ 进行归纳。$\dim V=1$ 的情况是平凡的，因为其上唯一的幂零算子是 $T=0$。现在假设 $\dim V>1$ 且结论对维数更低的空间成立。

设 $m$ 是使得 $T^{m}=0$ 的最小正整数。则存在 $u \in V$ 使得 $T^{m-1}u\neq 0$。令

$$
\begin{gather}
U=\operatorname{span}(u,Tu,\dots,T^{m-1}u)
\end{gather}
$$

设

$$
\begin{gather}
a_{0}u+a_{1}Tu+\dots+a_{m-1}T^{m-1}u=0 \tag{8.29.1}
\end{gather}
$$

对 $(8.29.1)$ 两边应用 $T^{m-1}$，我们就有 $a_{0}T^{m-1}u=0$，于是 $a_{0}=0$。再对 $(8.29.1)$ 两边应用 $T^{m-2}$，则有 $a_{1}T^{m-1}u=0$，于是 $a_{1}=0$。以此类推，我们可证 $a_{0}=\dots=a_{m-1}=0$，从而 $u,Tu,\dots,T^{m-1}u$ 线性无关。

如果 $U=V$，那么将上面的向量组反过来写即可得到 $T$ 的一个 Jordan 基，因此下面我们假设 $U\neq V$。

注意到 $U$ 在 $T$ 下不变。根据归纳假设，$U$ 有一个基是 $T|_{U}$ 的 Jordan 基。下面我们需要找到一个 $W$，使得 $V=U\oplus W$ 并且 $W$ 在 $T$ 下不变，从而 $W$ 有一个基是 $T|_{W}$ 的 Jordan 基，把这两个基放在一起就得到了 $V$ 的一个基，它同时也是 $T$ 的 Jordan 基。

令 $\varphi \in V^{*}$ 使得 $\varphi(T^{m-1}u)\neq 0$，设

$$
\begin{gather}
W=\{ v \in V : \varphi(T^{k}v)=0, k=0,1,\dots,m-1 \}
\end{gather}
$$

则由于 $\varphi(T^{k}(Tv))=0$，故 $W$ 在 $T$ 下不变。下面我们要证 $V=U\oplus W$。

设 $v \in U\cap W$，假设 $v\neq 0$，我们将 $v$ 写成

$$
\begin{gather}
v=c_{0}u+c_{1}Tu+\dots+c_{m-1}T^{m-1}u
\end{gather}
$$

令 $j$ 为使得 $c_{j}\neq 0$ 的最小整数，两边应用 $T^{m-j-1}$ 可得

$$
\begin{gather}
T^{m-j-1}v=c_{j}T^{m-1}u
\end{gather}
$$

从而 $\varphi(T^{m-j-1}v)=c_{j}\varphi(T^{m-1}u)\neq 0$，即 $v \not\in W$，矛盾。这表明 $U\cap W=\{ 0 \}$。

要证 $U\oplus W=V$，定义 $S\colon V\to \mathbb{F}^{m}$ 为

$$
\begin{gather}
Sv=(\varphi(v),\varphi(Tv),\dots,\varphi(T^{m-1}v))
\end{gather}
$$

则 $W=\ker S$，从而

$$
\begin{gather}
\dim W=\dim \ker S=\dim V-\dim \operatorname{range}S\geq \dim V-m
\end{gather}
$$

于是

$$
\begin{gather}
\dim(U\oplus W)=\dim U+\dim W\geq m+(\dim V-m)=\dim V
\end{gather}
$$

即证 $U\oplus W=V$。这就完成了证明。

### Theorem 8.30

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则存在 $V$ 的一个基使得它是 $T$ 的 Jordan 基。

#### Proof

设 $\lambda_{1},\dots,\lambda_{m}$ 是 $T$ 的不同特征值，根据广义特征空间分解定理，

$$
\begin{gather}
V=G(\lambda_{1},T)\oplus \dots \oplus G(\lambda_{m},T)
\end{gather}
$$

且每个 $(T-\lambda_{k}I)|_{G(\lambda_{k},T)}$ 是幂零的。于是 [[#Lemma 8.29]] 表明，存在 $G(\lambda_{k},T)$ 的一个基是 $(T-\lambda_{k}I)|_{G(\lambda_{k},T)}$ 的 Jordan 基。把这些 Jordan 基组合起来就是 $V$ 上算子 $T$ 的 Jordan 基。

# 8D Trace: A Connection Between Matrices and Operators

### Definition 8.31 trace of a matrix 矩阵的迹

设 $A$ 是 $\mathbb{F}$ 上的 $n\times n$ 矩阵，则 $A$ 的迹 $\operatorname{tr}A$ 定义为

$$
\begin{gather}
\operatorname{tr}A=A_{1,1}+A_{2,2}+\dots+A_{n,n}
\end{gather}
$$

### Theorem 8.32

设 $A$ 是 $m\times n$ 矩阵，$B$ 是 $n\times m$ 矩阵，则

$$
\begin{gather}
\operatorname{tr}AB=\operatorname{tr}BA
\end{gather}
$$

#### Proof

设 $A=(A_{j,k}),B=(B_{j,k})$，则

$$
\begin{align}
\operatorname{tr}AB &=\sum_{j=1}^{m} \sum_{k=1}^{n} A_{j,k}B_{k,j} \\
&=\sum_{k=1}^{n} \sum_{j=1}^{m} B_{k,j}A_{j,k} \\
&=\operatorname{tr}BA
\end{align}
$$

我们希望定义算子 $T \in L(V)$ 的迹为 $T$ 在某个基下的矩阵的迹，因此我们需要保证迹不会因为基变换而改变。

### Theorem 8.33

设 $T \in L(V)$，$u_{1},\dots,u_{n}$ 和 $v_{1},\dots,v_{n}$ 为 $V$ 的基，则

$$
\begin{gather}
\operatorname{tr}\mathcal{M}(T,(u_{1},\dots,u_{n}))=\operatorname{tr}\mathcal{M}(T,(v_{1},\dots,v_{n}))
\end{gather}
$$

#### Proof

设 $A=\mathcal{M}(T,(u_{1},\dots,u_{n})),B=\mathcal{M}(T,(v_{1},\dots,v_{n}))$。根据基变换公式，存在可逆 $n\times n$ 矩阵 $C$ 使得 $A=C^{-1}BC$，从而

$$
\begin{align}
\operatorname{tr}A &= \operatorname{tr}((C^{-1}B)C) \\
&= \operatorname{tr}(C(C^{-1}B)) \\
&= \operatorname{tr}((C C^{-1})B) \\
&=\operatorname{tr}B
\end{align}
$$

### Definition 8.34 trace of an operator 算子的迹

设 $T \in L(V)$，则 $T$ 的迹 $\operatorname{tr}T$ 定义为

$$
\begin{gather}
\operatorname{tr}T=\operatorname{tr}\mathcal{M}(T,(v_{1},\dots,v_{n}))
\end{gather}
$$

其中 $v_{1},\dots,v_{n}$ 是 $V$ 的任意一个基。

### Theorem 8.35

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则 $\operatorname{tr}T$ 等于 $T$ 的所有特征值按重数的加权和。

这就是说，设 $\lambda_{1},\dots,\lambda_{m}$ 是 $T$ 的不同特征值，其重数为 $d_{1},\dots,d_{m}$，则

$$
\begin{gather}
\operatorname{tr}T=d_{1}\lambda_{1}+\dots+d_{m}\lambda_{m}
\end{gather}
$$

#### Proof

根据 [[#Theorem 8.22]]，$T$ 有一个上三角矩阵，其对角线元素恰为 $T$ 的特征值，并且每个特征值 $\lambda_{k}$ 出现 $d_{k}$ 次，这就完成了证明。

算子的迹与它的特征多项式有紧密的联系。设 $\mathbb{F}=\mathbb{C}$，$T \in L(V)$，且 $\lambda_{1},\dots,\lambda_{n}$ 是 $T$ 的特征值，其中每个不同的特征值重复其重数次。则 $T$ 的特征多项式定义为

$$
\begin{gather}
(z-\lambda_{1})\cdots (z-\lambda_{n})
\end{gather}
$$

将其展开即得

$$
\begin{gather}
z^{n}-(\lambda_{1}+\dots+\lambda_{n})z^{n-1}+\dots+(-1)^{n}\lambda_{1}\cdots \lambda_{n}
\end{gather}
$$

这给出了以下定理。

### Theorem 8.36

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则 $-\operatorname{tr}T$ 等于 $T$ 的特征多项式中 $z^{\dim V-1}$ 项的系数。

### Theorem 8.37

设 $V$ 是内积空间，$T \in L(V)$，且 $e_{1},\dots,e_{n}$ 是 $V$ 的标准正交基，则

$$
\begin{gather}
\operatorname{tr}T=\langle Te_{1},e_{1} \rangle +\dots+\langle Te_{n},e_{n} \rangle 
\end{gather}
$$

#### Proof

$T$ 在 $e_{1},\dots,e_{n}$ 下的矩阵的 $(k,k)$ 元素等于 $\langle Te_{k},e_{k} \rangle$，根据定义即证。

### Theorem 8.38

映射 $\operatorname{tr}\colon L(V)\to \mathbb{F}$ 是 $L(V)$ 上的线性泛函，并且对 $S,T \in L(V)$ 满足

$$
\begin{gather}
\operatorname{tr}ST=\operatorname{tr}TS
\end{gather}
$$

#### Proof

$\operatorname{tr}$ 的线性性（加性和齐次性）在矩阵上是显然的。取 $V$ 的一个基，在 $S,T$ 的矩阵上写出相应的等式，然后利用 $\mathcal{M}$ 的同构性即证。

同理，$\operatorname{tr}ST=\operatorname{tr}TS$ 由 [[#Theorem 8.32]] 给出。

### Corollary 8.39

不存在 $S,T \in L(V)$ 使得 $ST-TS=I$。

#### Proof

我们有 $\operatorname{tr}(ST-TS)=\operatorname{tr}ST-\operatorname{tr}TS=0$，但 $\operatorname{tr}I=\dim V$，因此它们不可能相等。

注意，以上两个结果只对有限维空间成立，要将其推广到无限维空间，我们需要对 $S$ 和 $T$ 做额外的限制。