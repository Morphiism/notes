# 1 Review of Linear Algebra

## Vector Spaces

假设我们被给定一个集合 $V$，其中的元素称为向量。并假设我们被给定一个运算称为向量加法，其将 $\mathbf{x},\mathbf{y}\in V$ 映射到 $\mathbf{x}+\mathbf{y} \in V$。再假设我们被给定另一个运算称为标量乘法，其将标量（通常为实数）$\lambda$ 和 $\mathbf{x}\in V$ 映射到 $\lambda \mathbf{x}\in V$。

集合 $V$，连带着其上的加法和数乘，共同构成了一个向量空间，如果它满足以下公理：

1. $\mathbf{x}+\mathbf{y}=\mathbf{y}+\mathbf{x}$，
2. $(\mathbf{x}+\mathbf{y})+\mathbf{z}=\mathbf{x}+(\mathbf{y}+\mathbf{z})$，
3. 存在 $\mathbf{0}\in V$ 使得 $\mathbf{x}+\mathbf{0}=\mathbf{x}$，
4. 存在 $-\mathbf{x}\in V$ 使得 $\mathbf{x}+(-\mathbf{x})=\mathbf{0}$，
5. $1\mathbf{x}=\mathbf{x}$，
6. $c(d\mathbf{x})=(cd)\mathbf{x}$，
7. $(c+d)\mathbf{x}=c\mathbf{x}+d\mathbf{x}$，
8. $c(\mathbf{x}+\mathbf{y})=c\mathbf{x}+c\mathbf{y}$。

向量空间的一个典型例子是 $\mathbb{R}^{n}$，其中的加法和数乘是逐元素定义的。这就是说，如果 $\mathbf{x}=(x_{1},\dots,x_{n}),\mathbf{y}=(y_{1},\dots,y_{n})$，那么

$$
\begin{gather}
\mathbf{x}+\mathbf{y}=(x_{1}+y_{1},\dots,x_{n}+y_{n}) \\
c\mathbf{x}=(cx_{1},\dots,cx_{n})
\end{gather}
$$

如果 $V$ 是一个向量空间，$W$ 是 $V$ 的非空子集，我们称 $W$ 是 $V$ 的一个子空间，如果 $W$ 在加法和数乘下封闭。在这种情况下，$W$ 满足向量空间的八条公理，从而它自身也是向量空间。

本书中我们主要研究的向量空间只有 $\mathbb{R}^{n}$ 及其子空间。

称一组向量 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 张成 $V$，如果对任意 $\mathbf{x} \in V$，至少存在一组标量 $c_{1},\dots,c_{m}$ 使得

$$
\begin{gather}
\mathbf{x}=c_{1}\mathbf{a}_{1}+\dots+c_{m}\mathbf{a}_{m}
\end{gather}
$$

上式中我们说 $\mathbf{x}$ 可以写成 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 的线性组合

而称一组向量 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 线性无关，如果对任意 $v \in V$，至多存在一组标量 $c_{1},\dots,c_{m}$ 使得

$$
\begin{gather}
\mathbf{x}=c_{1}\mathbf{a}_{1}+\dots+c_{m}\mathbf{a}_{m}
\end{gather}
$$

等价地，一组向量 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 线性无关当且仅当将 $\mathbf{0}$ 写成 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 的线性组合的方法是唯一的，即 $c_{1}=\dots=c_{m}=0$。

如果 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 张成 $V$ 且线性无关，则称 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 是 $V$ 的一个基。对于基、张成、线性无关，我们有如下结果：

### Theorem 1.1

设 $V$ 有一个由 $m$ 个向量组成的基，则任何张成 $V$ 的向量组至少有 $m$ 个向量，且任何在 $V$ 中线性无关的向量组至多有 $m$ 个向量。特别地，$V$ 的任何基都恰有 $m$ 个向量。

以上定理中的 $m$，即 $V$ 的任意基的长度，称为 $V$ 的维数，记作 $\dim V$。

容易证明 $\mathbb{R}^{n}$ 的维数为 $n$。$\mathbb{R}^{n}$ 上的标准基定义为

$$
\begin{gather}
\mathbf{e}_{1}=(1,0,0,\dots,0) \\
\mathbf{e}_{2}=(0,1,0,\dots,0) \\
\vdots \\
\mathbf{e}_{n}=(0,0,0,\dots,1)
\end{gather}
$$

由于 $\mathbb{R}^{n}$ 是有限维的，因此它的所有子空间也是有限维的。这一事实是如下定理的推论：

### Theorem 1.2

设 $V$ 是 $m$ 维向量空间，如果 $W$ 是 $V$ 的子空间，那么 $W$ 的维数小于等于 $m$。此外，$W$ 的任意一个基 $\mathbf{a}_{1},\dots,\mathbf{a}_{k}$ 都可以扩张为 $V$ 的一个基 $\mathbf{a}_{1},\dots,\mathbf{a}_{k},\mathbf{a}_{k+1},\dots,\mathbf{a}_{m}$。

## Inner Products

向量空间 $V$ 上的一个（实）内积是一个函数，其将 $\mathbf{x},\mathbf{y}\in V$ 映射到 $\langle \mathbf{x},\mathbf{y} \rangle \in \mathbb{R}$，使其满足以下公理：

1. $\langle \mathbf{x},\mathbf{y} \rangle=\langle \mathbf{y},\mathbf{x} \rangle$，
2. $\langle \mathbf{x}+\mathbf{y},\mathbf{z} \rangle=\langle \mathbf{x},\mathbf{z} \rangle+\langle \mathbf{y},\mathbf{z} \rangle$，
3. $\langle c\mathbf{x},\mathbf{y} \rangle=c\langle \mathbf{x},\mathbf{y} \rangle$，
4. 如果 $\mathbf{x}\neq \mathbf{0}$ 则 $\langle \mathbf{x},\mathbf{x} \rangle>0$。

一个向量空间连带着以上的内积共同构成了一个内积空间。

$\mathbb{R}^{n}$ 上的标准内积，也称为点积，定义如下：如果 $\mathbf{x}=(x_{1},\dots,x_{n})$ 且 $\mathbf{y}=(y_{1},\dots,y_{n})$，那么

$$
\begin{gather}
\langle \mathbf{x},\mathbf{y} \rangle =x_{1}y_{1}+\dots+x_{n}y_{n}
\end{gather}
$$

如果 $V$ 是内积空间，定义 $\mathbf{x}\in V$ 的范数为

$$
\begin{gather}
\lVert \mathbf{x} \rVert =\langle \mathbf{x},\mathbf{x} \rangle ^{1/2}
\end{gather}
$$

范数满足以下公理：

1. 如果 $\mathbf{x}\neq \mathbf{0}$ 则 $\lVert \mathbf{x} \rVert>0$，
2. $\lVert c\mathbf{x} \rVert=\lvert c \rvert\lVert \mathbf{x} \rVert$，
3. $\lVert \mathbf{x}+\mathbf{y} \rVert\leq \lVert \mathbf{x} \rVert+\lVert \mathbf{y} \rVert$。

公理 (3) 也称为范数的三角不等式，它的一个等价形式是

$$
\begin{gather}
\lVert \mathbf{x} \rVert -\lVert \mathbf{y} \rVert \leq \lVert \mathbf{x}-\mathbf{y} \rVert 
\end{gather}
$$

称为逆三角不等式。

$V$ 上任意满足以上三条公理的实值函数都称为 $V$ 上的一个范数。有些范数可以由内积导出，例如 $\mathbb{R}^{n}$ 上的 Euclidean 范数

$$
\begin{gather}
\lVert \mathbf{x} \rVert =\sqrt{ x_{1}^{2}+\dots+x_{n}^{2} }=\langle \mathbf{x},\mathbf{x} \rangle ^{1/2}
\end{gather}
$$

而 $\mathbb{R}^{n}$ 上的上确界范数

$$
\begin{gather}
\lvert \mathbf{x} \rvert =\max(\lvert x_{1} \rvert ,\dots,\lvert x_{n} \rvert )
\end{gather}
$$

并非由某个内积生成。在 $\mathbb{R}^{n}$ 上，上述两个范数满足不等式

$$
\begin{gather}
\lvert \mathbf{x} \rvert \leq \lVert \mathbf{x} \rVert \leq \sqrt{ n } \lvert \mathbf{x} \rvert 
\end{gather}
$$

这就是说 Euclidean 范数与上确界范数等价，意味着它们生成的拓扑相同，从而在涉及极限的论证中，我们可以任意选取使用的范数，而仍然得到相同的结论。

## Matrices

一个矩阵 $A$ 是一个矩形数表，记作 $A=(a_{ij})$，其中 $a_{ij}$ 是 $A$ 第 $i$ 行第 $j$ 列的元素。

如果 $A,B$ 是相同大小的矩阵，其 $(i,j)$ 元素分别为 $a_{ij}$ 和 $b_{ij}$，则我们定义 $A+B$ 为 $(i,j)$ 元素是 $a_{ij}+b_{ij}$ 的矩阵，并且 $cA$ 为 $(i,j)$ 元素是 $ca_{ij}$ 的矩阵。在以上逐元素定义的加法和数乘下，所有 $n\times m$ 矩阵的集合构成了一个向量空间。

矩阵还可以定义乘法。设 $A$ 是 $n\times m$ 矩阵，$B$ 是 $m\times p$ 矩阵，则我们定义 $A,B$ 的乘积 $AB$ 是一个 $n\times p$ 矩阵 $C$，其 $(i,j)$ 元素为

$$
\begin{gather}
c_{ij}=\sum_{k=1}^{m} a_{ik}b_{kj}
\end{gather}
$$

矩阵乘法满足以下性质：

1. $A(BC)=(AB)C$，
2. $A(B+C)=AB+AC$，
3. $(A+B)C=AC+BC$，
4. $(cA)B=c(AB)=A(cB)$，
5. 对每个 $k$，存在 $k\times k$ 矩阵 $I_{k}$ 使得如果 $A$ 是 $n\times m$ 矩阵，那么
$$
I_{n}A=A, \quad AI_{m}=A
$$

矩阵 $I_{k}$ 的 $(i,j)$ 元素定义为 $\delta_{ij}$，它等于 $1$ 如果 $i=j$，否则它等于 $0$。我们称 $I_{k}$ 为 $k$ 阶恒等矩阵，它具有形式

$$
\begin{gather}
I_{k}=\begin{bmatrix}
1 & 0 & \cdots & 0 \\
0 & 1 & \cdots & 0 \\
 & \cdots & \cdots &  \\
0 & 0 & \cdots & 1
\end{bmatrix}
\end{gather}
$$

其中 $I_{k}$ 的对角线元素均为 $1$，而其余的元素均为 $0$。

我们将上确界范数推广到矩阵集合。如果 $A=(a_{ij})$ 是 $n\times m$ 矩阵，则定义

$$
\begin{gather}
\lvert A \rvert =\max \{ \lvert a_{ij} \rvert : 1\leq i\leq n,1\leq j\leq m \}
\end{gather}
$$

容易验证范数的三条公理，并且我们还有以下结果：

### Theorem 1.3

设 $A$ 是 $n\times m$ 矩阵，$B$ 是 $m\times p$ 矩阵，则

$$
\begin{gather}
\lvert AB \rvert \leq m\lvert A \rvert \lvert B \rvert 
\end{gather}
$$

## Linear Transformations

设 $V,W$ 是向量空间，一个映射 $T\colon V\to W$ 称为是一个线性变换，如果它满足以下性质：

1. $T(\mathbf{x}+\mathbf{y})=T(\mathbf{x})+T(\mathbf{y})$，
2. $T(c\mathbf{x})=cT(\mathbf{x})$。

如果，进一步还有 $T$ 是一个双射，则我们称 $T$ 是一个线性同构。

容易验证如果 $T\colon V\to W$ 和 $S\colon W\to X$ 都是线性变换，那么 $S\circ T\colon V\to X$ 也是线性变换。此外，如果 $T\colon V\to W$ 是线性同构，那么 $T^{-1}\colon W\to V$ 也是线性同构。

一个线性变换完全由其在基向量上的取值决定，这就是以下定理的主要内容：

### Theorem 1.4

设 $V$ 是具有基 $\mathbf{a}_{1},\dots,\mathbf{a}_{m}$ 的向量空间，令 $W$ 是向量空间，且 $\mathbf{b}_{1},\dots,\mathbf{b}_{m}\in W$，则存在唯一的线性变换 $T\colon V\to W$ 使得 $T(\mathbf{a}_{i})=\mathbf{b}_{i}$。

在 $V,W$ 分别等于 $\mathbb{R}^{n}$ 和 $\mathbb{R}^{m}$ 的情况下，矩阵给出了线性变换 $T$ 的一个良好表示。

首先我们讨论行向量与列向量。一个 $1\times n$ 的矩阵称为行向量，而一个 $\mathbf{x} \in \mathbb{R}^{n}$ 显然可以等同于一个行向量：我们有线性同构

$$
\begin{gather}
(x_{1},\dots,x_{n}) \mapsto [x_{1}\cdots x_{n}]
\end{gather}
$$

类似地，一个 $n\times 1$ 矩阵称为列向量，而 $\mathbf{x}\in \mathbb{R}^{n}$ 显然也可以等同于一个列向量：我们有线性同构

$$
\begin{gather}
(x_{1},\dots,x_{n}) \mapsto \begin{bmatrix}
x_{1} \\
\vdots \\
x_{n}
\end{bmatrix}
\end{gather}
$$

上面的第二种同构在线性变换的研究中非常有用。假设现在我们将 $\mathbb{R}^{n}$ 中的元素与列向量等同，$A$ 是一个 $n\times m$ 矩阵，我们定义 $T\colon \mathbb{R}^{m}\to \mathbb{R}^{n}$ 为

$$
\begin{gather}
T(\mathbf{x})=A\mathbf{x}
\end{gather}
$$

则矩阵乘法的性质立即表明 $T$ 是线性变换。

此外，从 $\mathbb{R}^{m}$ 到 $\mathbb{R}^{n}$ 的任何线性变换均具有以上形式。这一结论是 [[#Theorem 1.4]] 的直接推论：给定 $T$，设 $\mathbf{b}_{1},\dots,\mathbf{b}_{m} \in \mathbb{R}^{n}$ 满足 $T(\mathbf{e}_{i})=\mathbf{b}_{i}$，令 $A$ 为 $n\times m$ 矩阵 $[\mathbf{b}_{1}\cdots \mathbf{b}_{m}]$，它以 $\mathbf{b}_{1},\dots,\mathbf{b}_{m}$ 作为列。由于恒等矩阵 $I_{m}$ 的列为 $\mathbf{e}_{1},\dots,\mathbf{e}_{m}$，因此等式 $AI_{m}=A$ 立即表明 $A\mathbf{e}_{i}=\mathbf{b}_{i}$，于是我们就有 $T(\mathbf{x})=A\mathbf{x}$。

由于这一原因，我们接下来做出如下约定：

### Convention

除非特殊说明，否则我们将 $(x_{1},\dots,x_{n})\in \mathbb{R}^{n}$ 与列向量 $[x_{1}\cdots x_{n}]^{T}$ 等同。

## Rank of a Matrix

给定一个 $n\times m$ 矩阵 $A$，我们考虑与之相关的几个重要子空间。由 $A$ 的各列张成的子空间称为 $A$ 的列空间，它的维数称为 $A$ 的列秩，同时它也是线性变换 $T(\mathbf{x})=A\mathbf{x}$ 的值域。

类似地，$A$ 的各行张成的子空间称为 $A$ 的行空间，它的维数称为 $A$ 的行秩。

我们有以下的基本结果：

### Theorem 1.5

对任意矩阵 $A$，$A$ 的列秩等于 $A$ 的行秩。

于是，我们可以直接用秩 $\operatorname{rank}A$ 来同时表示 $A$ 的列秩与行秩。

矩阵的秩通常不能直接通过观察 $A$ 的元素来得到。不过，我们有一个相当简单的算法，称为 Gauss-Jordan 消元法，来确定任意矩阵的秩。

消元法的基本思想是，通过三种基本操作，称为初等行变换，将一个矩阵 $A$ 转化为一个更为简单的形式 $B$。三种初等行变换如下所示：

1. 交换 $A$ 的第 $i_{1}$ 行与第 $i_{2}$ 行（$i_{1}\neq i_{2}$）。
2. 将 $A$ 的第 $i_{1}$ 行替换为 $i_{1}$ 行加上 $i_{2}$ 行的 $c$ 倍（$i_{1}\neq i_{2}$）。
3. 将 $A$ 的第 $i$ 行替换为第 $i$ 行的 $\lambda$ 倍（$\lambda\neq 0$）。

每一种初等行变换都是可逆的，并且其逆操作还是同一类行变换。我们有如下结果：

### Theorem 1.6

如果矩阵 $B$ 由矩阵 $A$ 经过初等行变换后得到，那么

$$
\begin{gather}
\operatorname{rank}B=\operatorname{rank}A
\end{gather}
$$

Gauss-Jordan 消元法的过程是，通过初等行变换将矩阵 $A$ 转化为所谓的行阶梯型，而后者的秩（以及其它性质）可以直接从元素中读出。行阶梯型矩阵的一个例子如下：

$$
\begin{gather}
B=\begin{bmatrix}
a & \ast & \ast & \ast & \ast & \ast \\
0 & b & \ast & \ast & \ast & \ast \\
0 & 0 & 0 & c & \ast & \ast \\
0 & 0 & 0 & 0 & 0 & 0
\end{bmatrix}
\end{gather}
$$

其中 $a,b,c\neq 0$ 称为主元，且“阶梯”下方的元素均为 $0$。此外，事实上我们只需使用第 (1) 类和第 (2) 类初等行变换即可将 $A$ 变换为行阶梯型。

容易看出，$B$ 的非零行线性无关，因此 $B$ 中非零行的数量就是 $B$ 的秩。

如果我们需要解线性方程组，那么我们可以将 $B$ 进一步变换为行最简型。使用第 (2) 类行变换，我们可以将主元所在的列上方变为 $0$，然后使用第 (3) 类行变换，我们可以将所有主元变为 $1$，这给出

$$
\begin{gather}
C=\begin{bmatrix}
1 & 0 & \ast & 0 & \ast & \ast \\
0 & 1 & \ast & 0 & \ast & \ast \\
0 & 0 & 0 & 1 & \ast & \ast \\
0 & 0 & 0 & 0 & 0 & 0
\end{bmatrix}
\end{gather}
$$

## Transpose of a Matrix

给定一个 $n\times m$ 矩阵 $A$，$A$ 的转置是一个 $m\times n$ 矩阵 $D=A^{T}$，其 $(i,j)$ 元素为 $d_{ij}=a_{ji}$。转置的以下性质是基础的：

1. $(A^{T})^{T}=A$，
2. $(A+B)^{T}=A^{T}+B^{T}$，
3. $(AC)^{T}=C^{T}A^{T}$，
4. $\operatorname{rank}A^{T}=\operatorname{rank}A$。

# 2 Matrix Inversion and Determinants

## Elementary Matrices

### Definition 2.1 elementary matrix 初等矩阵

一个 $n\times n$ 初等矩阵是对恒等矩阵 $I_{n}$ 应用一次初等行变换得到的矩阵。

对应于三类初等行变换，我们可以得到三类初等矩阵。对应于第一类行变换的初等矩阵具有形式

$$
\begin{gather}
E=\begin{bmatrix}
1 &  &  &  &  &  &  \\
 & 1 &  &  &  &  &  \\
 &  & 0 & \cdots & 1 &  &  \\
 &  & \vdots &  & \vdots &  &  \\
 &  & 1 & \cdots & 0 &  &  \\
 &  &  &  &  & 1 &  \\
 &  &  &  &  &  & 1
\end{bmatrix}
\end{gather}
$$

其中 $I_{n}$ 的第 $i_{1}$ 行与第 $i_{2}$ 行交换了位置。

对应于第二类行变换的初等矩阵具有形式

$$
\begin{gather}
E'=\begin{bmatrix}
1 &  &  &  &  &  &  \\
 & 1 &  &  &  &  &  \\
 &  & 1 & \cdots & c &  &  \\
 &  & \vdots &  & \vdots &  &  \\
 &  & 0 & \cdots & 1 &  &  \\
 &  &  &  &  & 1 &  \\
 &  &  &  &  &  & 1
\end{bmatrix}
\end{gather}
$$

其中 $I_{n}$ 的第 $i_{2}$ 行的 $c$ 倍加到了第 $i_{1}$ 行上。

对应于第三类行变换的初等矩阵具有形式

$$
\begin{gather}
E''=\begin{bmatrix}
1 &  &  &  &  &  &  \\
 & 1 &  &  &  &  &  \\
 &  & \lambda &  &  &  &  \\
 &  &  & \ddots &  &  &  \\
 &  &  &  &  & 1 &  \\
 &  &  &  &  &  & 1
\end{bmatrix}
\end{gather}
$$

其中 $I_{n}$ 的第 $i$ 行乘了 $\lambda$ 倍。

我们有如下的基本结果：

### Theorem 2.2

对矩阵 $A$ 做初等行变换等同于用相应的初等矩阵左乘 $A$。

## The Inverse of a Matrix

### Definition 2.3 left inverse 左逆，right inverse 右逆

设 $A$ 是 $n\times m$ 矩阵，$B,C$ 为 $m\times n$ 矩阵。称 $B$ 是 $A$ 的一个左逆，如果 $BA=I_{m}$；称 $C$ 是 $A$ 的一个右逆，如果 $AC=I_{n}$。

### Theorem 2.4

如果 $A$ 同时有左逆 $B$ 和右逆 $C$，那么它们唯一且相等。

#### Proof

我们有

$$
\begin{gather}
C=I_{m}C=(BA)C=B(AC)=BI_{n}=B
\end{gather}
$$

如果 $B_{1}$ 是另一个左逆，在以上论证中用 $B_{1}$ 替换 $B$，我们就有 $C=B_{1}$，从而 $B_{1}=B$。同理可证 $C_{1}=C$。

### Definition 2.5 invertible 可逆的

如果 $A$ 同时有左逆和右逆，则称 $A$ 是可逆的。其唯一且相等的双边逆元称为 $A$ 的逆矩阵，记作 $A^{-1}$。

矩阵 $A$ 可逆的充分且必要条件是 $A$ 为方阵且满秩，这是如下两个定理的直接推论。

### Theorem 2.6

设 $A$ 是 $n\times m$ 矩阵，如果 $A$ 可逆，那么

$$
\begin{gather}
n=m=\operatorname{rank}A
\end{gather}
$$

#### Proof

**第一步** 我们证明对任意 $k\times n$ 矩阵 $D$，有

$$
\begin{gather}
\operatorname{rank}(DA)\leq \operatorname{rank}A
\end{gather}
$$

根据矩阵乘法，$DA$ 的各行是 $A$ 的行的线性组合，因此 $DA$ 的行空间包含于 $A$ 的行空间，即证。

**第二步** 我们证明如果 $A$ 有左逆 $B$，那么 $A$ 的秩等于 $A$ 的列数。

等式 $I_{m}=BA$ 表明 $m=\operatorname{rank}(BA)\leq \operatorname{rank}A$。而另一方面，$A$ 的行空间包含于 $\mathbb{R}^{m}$，因此 $\operatorname{rank}A\leq m$。

**第三步** 我们证明本定理。

设 $B$ 是 $A$ 的逆，由于 $B$ 是 $A$ 的左逆，故 $\operatorname{rank}A=m$。另一方面，$B$ 是 $A$ 的右逆，故 $B^{T}A^{T}=I_{n}$，从而 $\operatorname{rank}A^{T}=\operatorname{rank}A=n$。

### Theorem 2.7

设 $A$ 是 $n\times m$ 矩阵，假设

$$
\begin{gather}
n=m=\operatorname{rank}A
\end{gather}
$$

则 $A$ 可逆，并且 $A$ 可以写成一系列初等矩阵的乘积。

#### Proof

**第一步** 任何初等矩阵都是可逆的，并且其逆矩阵也是初等矩阵。这一结果由初等行变换的可逆性给出。

**第二步** 我们证明本定理。

设 $A$ 是满秩的 $n\times n$ 矩阵。我们通过初等行变换将 $A$ 约化为行最简型 $C$，由于 $C$ 是方阵且满秩，故 $C$ 必然等于恒等矩阵 $I_{n}$。于是根据 [[#Theorem 2.2]] 可知存在初等矩阵 $E_{1},\dots,E_{k}$ 使得

$$
\begin{gather}
E_{k}\cdots E_{1}A=I_{n}
\end{gather}
$$

于是

$$
\begin{gather}
A=E_{1}^{-1}\cdots E_{k}^{-1}
\end{gather}
$$

从而 $A$ 等于一系列初等矩阵的乘积，并且有逆矩阵

$$
\begin{gather}
A^{-1}=E_{k}\cdots E_{1}
\end{gather}
$$

### Theorem 2.8

设 $A$ 是方阵，$B$ 是 $A$ 的左逆，则 $B$ 同时也是 $A$ 的右逆。

#### Proof

[[#Theorem 2.6]] 证明的第二步表明，如果 $B$ 是左逆，那么 $\operatorname{rank}A$ 等于 $A$ 的列数，其同时也是 $A$ 的行数。因此，[[#Theorem 2.7]] 表明 $A$ 有双边逆元，再由 [[#Theorem 2.4]] 知这个逆元就是 $B$。

一个 $n\times n$ 矩阵 $A$ 称为是奇异的，如果它不可逆；否则就说它是非奇异的。

## Determinants

一个行列式是一个将方阵 $A$ 关联到一个标量 $\det A$ 的函数，满足三条公理。在本章中我们将假设有这样一个函数满足所需的性质，而将具体的构造推迟到后续的章节。

### Definition 2.9 determinant 行列式

一个将 $n\times n$ 矩阵 $A$ 映射到标量 $\det A$ 的函数称为一个行列式函数，如果它满足以下公理：

1. 如果 $B$ 是将 $A$ 的两行交换得到的矩阵，那么 $\det B=-\det A$，
2. $\det A$ 作为 $A$ 的第 $i$ 行的函数是线性的，
3. $\det I_{n}=1$。

具体来说，公理 (2) 可以叙述如下：设 $A_{i}(\mathbf{x})$ 是将 $A$ 的第 $i$ 行替换为 $\mathbf{x}$ 得到的矩阵，则

$$
\begin{gather}
\det A_{i}(a\mathbf{x}+b \mathbf{y})=a \det A_{i}(\mathbf{x})+b \det A_{i}(\mathbf{y})
\end{gather}
$$

我们将看到，满足以上三条公理的行列式函数是唯一的，如果它存在的话。

### Theorem 2.10

设 $A$ 是 $n\times n$ 矩阵。

(a) 如果 $E$ 是对应于交换 $A$ 的两行的初等矩阵，则 $\det(EA)=-\det A$。
(b) 如果 $E'$ 是对应于将 $A$ 的 $i_{1}$ 行替换为 $i_{1}$ 行加 $i_{2}$ 行的 $c$ 倍的初等矩阵，那么 $\det(E'A)=\det A$。
(c) 如果 $E''$ 是对应于将 $A$ 的第 $i$ 行乘以 $\lambda\neq 0$ 的初等矩阵，那么 $\det(E''A)=\lambda \det A$。
(d) 如果 $A$ 是 $n$ 阶恒等矩阵，那么 $\det A=1$。

#### Proof

(a) 是公理 (1) 的重述，(d) 是公理 (3) 的重述。(c) 由行列式的多线性性给出：

$$
\begin{gather}
\det(\lambda A_{i}(\mathbf{x}))=\lambda \det A_{i}(\mathbf{x})
\end{gather}
$$

现在验证 (b)。首先我们证明，如果 $A$ 有相同的两行，那么 $\det A=0$：交换相同的那两行，我们得到 $\det A=-\det A$。于是我们有

$$
\begin{align}
\det(E'A) &= \det A_{i}(\mathbf{x}+c\mathbf{y}) \\
&=\det A_{i}(\mathbf{x})+c \det A_{i}(\mathbf{y}) \\
&=\det A_{i}(\mathbf{x}) \\
&=\det A
\end{align}
$$

其中 $\det A_{i}(\mathbf{y})=0$，因为 $A_{i}(\mathbf{y})$ 有相同的两行。

以上定理中的四条性质是实际应用中我们用来计算行列式的方法，它们同样也唯一确定了行列式函数。

在以上定理中，取 $A=I_{n}$ 即可得到三类初等矩阵的行列式：

$$
\begin{gather}
\det E=-1, \quad \det E'=1, \quad \det E''=\lambda
\end{gather}
$$

### Theorem 2.11

设 $A$ 是方阵。如果 $A$ 的行线性无关，则 $\det A\neq 0$；如果 $A$ 的行线性相关，则 $\det A=0$。因此 $A$ 满秩当且仅当 $\det A\neq 0$。

#### Proof

首先我们证明，如果 $A$ 有一行为零，那么 $\det A=0$：将零行乘以 $2$，我们有 $\det A=2\det A$。

第二，我们证明对 $A$ 做初等行变换不会使 $\det A$ 从 $0$ 变为非 $0$，反之亦然。这是因为 [[#Theorem 2.10]] 表明，对 $A$ 做初等行变换只能将 $\det A$ 变为原来的 $1,-1$ 或 $\lambda\neq 0$ 倍。

现在我们证明本定理。将 $A$ 行约化为阶梯型矩阵 $B$，如果 $A$ 的行线性相关，则 $\operatorname{rank}A<n$，从而 $\operatorname{rank}B<n$，故 $B$ 必然有零行，因此 $\det B=0$，这表明 $\det A=0$。

如果 $A$ 的行线性无关，则 $\operatorname{rank}A=n$。我们进一步将 $B$ 行约化为最简型 $C$。由于 $C$ 是 $n\times n$ 矩阵且 $\operatorname{rank}C=n$，故 $C=I_{n}$，从而 $\det C\neq 0$，$\det A\neq 0$。

### Theorem 2.12

给定方阵 $A$，我们用第 (1) 类和第 (2) 类初等行变换将 $A$ 约化为阶梯型矩阵 $B$。如果 $B$ 有零行，那么 $\det A=0$。否则，设 $k$ 为行约化过程中行交换的次数，则 $\det A$ 等于 $(-1)^{k}$ 乘以 $B$ 的对角线元素的乘积。

#### Proof

如果 $B$ 有零行，那么 $\det A=\det B=0$。下面我们假设 $B$ 没有零行，从而根据 [[#Theorem 2.10]] 知 $\det A=(-1)^{k}\det B$，并且 $B$ 具有形式

$$
\begin{gather}
B=\begin{bmatrix}
b_{11} & \ast & \cdots & \ast \\
0 & b_{22} & \cdots & \ast \\
 & \vdots &  & \vdots \\
0 & 0 & \cdots & b_{nn}
\end{bmatrix}
\end{gather}
$$

其中 $b_{ii}\neq 0$。下面我们只需证明

$$
\begin{gather}
\det B=b_{11}\cdots b_{nn}
\end{gather}
$$

为此，我们用第 (2) 类初等行变换将 $B$ 化为对角矩阵

$$
\begin{gather}
C=\begin{bmatrix}
b_{11} & 0 & \cdots & 0 \\
0 & b_{22} & \cdots & 0 \\
 & \vdots &  & \vdots \\
0 & 0 & \cdots & b_{nn}
\end{bmatrix}
\end{gather}
$$

由于我们只用了第 (2) 类行变换，故 $\det B=\det C$。而 $C$ 是由恒等矩阵 $I_{n}$ 应用 $n$ 次第 (3) 类行变换得到的，因此

$$
\begin{gather}
\det C=b_{11}\cdots b_{nn}\det I_{n}=b_{11}\cdots b_{nn}
\end{gather}
$$

这就完成了证明。

### Corollary 2.13

行列式函数由它的三条公理唯一确定，它也由 [[#Theorem 2.10]] 中的四条性质唯一确定。

#### Proof

[[#Theorem 2.12]] 中 $\det A$ 的计算仅使用了 [[#Theorem 2.10]] 中的四条性质，而后者可由三条公理推导出来。

### Theorem 2.14

设 $A,B$ 是 $n\times n$ 矩阵，则

$$
\begin{gather}
\det(AB)=(\det A)(\det B)
\end{gather}
$$

#### Proof

**第一步** 定理在 $A$ 是初等矩阵时成立。事实上，

$$
\begin{gather}
\det(EB)=-\det B=(\det E)(\det B) \\
\det(E'B)=\det B=(\det E')(\det B) \\
\det(E''B)=\lambda \det B=(\det E'')(\det B)
\end{gather}
$$

**第二步** 定理在 $\operatorname{rank}A=n$ 时成立。

此时，由 [[#Theorem 2.7]]，$A$ 可以写成一系列初等矩阵 $E_{1},\dots,E_{k}$ 的乘积，反复应用第一步的结论可得

$$
\begin{gather}
\det(AB)=(\det E_{1})\cdots (\det E_{k}) (\det B)
\end{gather}
$$

取 $B=I_{n}$ 可得 $\det(A)=(\det E_{1})\cdots(\det E_{k})$，从而 $\det(AB)=(\det A)(\det B)$。

**第三步** 我们证明 $\operatorname{rank}A<n$ 的情况。

根据矩阵乘法，$AB$ 的列是 $A$ 的列的线性组合，因此 $AB$ 的列空间包含于 $A$ 的列空间，从而 $\operatorname{rank}(AB)\leq \operatorname{rank}A<n$，于是

$$
\begin{gather}
\det(AB)=0=(\det A)(\det B)
\end{gather}
$$

### Theorem 2.15

$\det A^{T}=\det A$。

#### Proof

我们采用 [[#Theorem 2.14]] 相同的证明结构：初等矩阵，$\operatorname{rank}A=n$ 以及 $\operatorname{rank}A<n$。

**第一步** 初等矩阵。

第一类和第三类初等矩阵 $E,E''$ 是对称矩阵，因此等式显然成立。对于第二类初等矩阵 $E'$，它的转置也是第二类初等矩阵，故 $\det E'=\det(E')^{T}=1$。

**第二步** $\operatorname{rank}A=n$。

此时 $A$ 是一系列初等矩阵 $E_{1},\dots,E_{k}$ 的乘积，则

$$
\begin{align}
\det A^{T}&= \det(E_{k}^{T}\cdots E_{1}^{T}) \\
&=(\det E_{k}^{T})\cdots (\det E_{1}^{T}) \\
&=(\det E_{1})\cdots (\det E_{k}) \\
&=\det(E_{1}\cdots E_{k}) \\
&=\det A
\end{align}
$$

**第三步** $\operatorname{rank}A<n$。

此时 $\operatorname{rank}A^{T}=\operatorname{rank}A<n$，因此 $\det A^{T}=0=\det A$。

以上定理表明我们可以对矩阵做初等列变换，并且列变换同样满足与 [[#Theorem 2.10]] 类似的定理。

## A Formula for $A^{-1}$

我们知道 $A$ 可逆当且仅当 $\det A\neq 0$。本节我们给出 $A^{-1}$ 的一个涉及 $\det A$ 的显式公式。

### Definition 2.16 minor 子式，cofactor 代数余子式

设 $A$ 是 $n\times n$ 矩阵，将 $A$ 的第 $i$ 行与第 $j$ 列去除得到的 $(n-1)\times(n-1)$ 矩阵称为 $A$ 的 $(i,j)$-子式，记作 $A_{ij}$。

我们定义 $A$ 的 $(i,j)$-代数余子式为 $(-1)^{i+j}\det A_{ij}$。

### Lemma 2.17

设 $A$ 是 $n\times n$ 矩阵，$b$ 为它的 $(i,j)$ 元素。

(a) 如果第 $i$ 行除了 $b$ 以外均为 $0$，则
$$
\begin{gather}
\det A=(-1)^{i+j} b \det A_{ij}
\end{gather}
$$
(b) 同样的等式在第 $j$ 列除了 $b$ 外均为 $0$ 时成立。

#### Proof

**第一步** 我们证明定理的一个特例。令 $b,a_{2},\dots,a_{n}$ 是标量，给定一个 $(n-1)\times(n-1)$ 矩阵 $D$，令 $A(D)$ 表示 $n\times n$ 矩阵

$$
\begin{gather}
A(D)=\begin{bmatrix}
b & a_{2} & \cdots & a_{n} \\
0 &  &  &  \\
\vdots &  & D &  \\
0 &  &  & 
\end{bmatrix}
\end{gather}
$$

我们来证明 $\det A(D)=b\det D$。

如果 $b=0$，则显然有 $\det A(D)=0$。下面我们假设 $b\neq 0$，定义函数 $f$ 为

$$
\begin{gather}
f(D)=\frac{1}{b} \det A(D)
\end{gather}
$$

我们验证 $f(D)$ 满足 [[#Theorem 2.10]] 的四条性质，从而 $f(D)=\det D$。

交换 $D$ 的两行等同于交换 $A(D)$ 的两行，于是 $f(D)$ 变成原来的 $-1$ 倍。将 $D$ 的第 $i_{2}$ 行的 $c$ 倍加到第 $i_{1}$ 行上，这等同于将 $A(D)$ 的 $i_{2}+1$ 行的 $c$ 倍加到 $i_{1}+1$ 行上，使得 $f(D)$ 不变。将 $D$ 的第 $i$ 行乘以 $\lambda$，等同于将 $A(D)$ 的第 $i+1$ 行乘以 $\lambda$，这使得 $f(D)$ 的值变为 $\lambda$ 倍。最后，如果 $D=I_{n-1}$，那么 $A(D)$ 是一个阶梯型矩阵，$\det A(D)=b\cdot 1\cdots 1=b$，从而 $f(D)=1$。

**第二步** 取 $A(D)$ 的转置可得

$$
\begin{gather}
\det \begin{bmatrix}
b & 0 & \cdots & 0 \\
a_{2} &  &  &  \\
\vdots &  & D &  \\
a_{n} &  &  & 
\end{bmatrix}=b\det D
\end{gather}
$$

**第三步** 我们证明本定理。

设 $A$ 如定理所示。通过 $i-1$ 次的相邻行交换，我们可以将 $b$ 移动到第一行，再通过 $j-1$ 次相邻列交换，我们将 $A$ 变换为矩阵 $C$，其中 $C$ 的 $(1,1)$-子式 $C_{11}$ 等于 $A$ 的 $(i,j)$-子式 $A_{ij}$。此外，$C$ 具有第一步或第二步中的形式。

每次行交换和列交换改变行列式的符号，因此

$$
\begin{gather}
\det C=(-1)^{(i-1)+(j-1)}\det A=(-1)^{i+j}\det A
\end{gather}
$$

从而

$$
\begin{align}
\det A &=(-1)^{i+j}\det C \\
&=(-1)^{i+j} b \det C_{11} \\
&=(-1)^{i+j} b \det A_{ij}
\end{align}
$$

### Theorem 2.18 (Cramer)

设 $A$ 为 $n\times n$ 矩阵 $[\mathbf{a}_{1}\cdots \mathbf{a}_{n}]$，令 $\mathbf{x}=[x_{1}\cdots x_{n}]^{T}$ 和 $\mathbf{c}=[c_{1}\cdots c_{n}]^{T}$ 为列向量，如果 $A\mathbf{x}=\mathbf{c}$，则

$$
\begin{gather}
(\det A)x_{i}=\det [\mathbf{a}_{1}\cdots \mathbf{a}_{i-1}\ \mathbf{c}\  \mathbf{a}_{i+1}\cdots \mathbf{a}_{n}]
\end{gather}
$$

#### Proof

取 $\mathbb{R}^{n}$ 的标准基 $\mathbf{e}_{1},\dots,\mathbf{e}_{n}$，令

$$
\begin{gather}
C=[\mathbf{e}_{1}\cdots \mathbf{e}_{i-1}\ \mathbf{x}\ \mathbf{e}_{i+1}\cdots \mathbf{e}_{n}]
\end{gather}
$$

则我们有

$$
\begin{gather}
AC=[\mathbf{a}_{1}\cdots \mathbf{a}_{i-1}\ \mathbf{c}\ \mathbf{a}_{i+1}\cdots \mathbf{a}_{n}]
\end{gather}
$$

从而

$$
\begin{gather}
(\det A)(\det C)=\det [\mathbf{a}_{1}\cdots \mathbf{a}_{i-1}\ \mathbf{c}\  \mathbf{a}_{i+1}\cdots \mathbf{a}_{n}]
\end{gather}
$$

而 $C$ 的第 $i$ 行除了 $x_{i}$ 外均为 $0$，且 $C_{ii}=I_{n-1}$，因此根据 [[#Lemma 2.17]] 得

$$
\begin{gather}
\det C=(-1)^{i+i}x_{i} \det I_{n-1}=x_{i}
\end{gather}
$$

这就完成了证明。

### Theorem 2.19

设 $A$ 是 $n\times n$ 满秩矩阵，$B=A^{-1}$，则

$$
\begin{gather}
b_{ij}=\frac{(-1)^{i+j} \det A_{ji}}{\det A}
\end{gather}
$$

#### Proof

设 $\mathbf{x}=[x_{1}\cdots x_{n}]^{T}$ 表示 $B$ 的第 $j$ 列。$AB=I_{n}$ 表明 $A\mathbf{x}=\mathbf{e}_{j}$，从而由 Cramer 法则得

$$
\begin{gather}
(\det A) x_{i}=\det [\mathbf{a}_{1}\cdots \mathbf{a}_{i-1}\ \mathbf{e}_{j}\ \mathbf{a}_{i+1}\cdots \mathbf{a}_{n}]
\end{gather}
$$

从而

$$
\begin{gather}
x_{i}=b_{ij}=\frac{(-1)^{i+j}\det A_{ji}}{\det A}
\end{gather}
$$

以上定理给出了 $A^{-1}$ 的一个显式计算方法，其过程如下：

1. 构造矩阵 $C=(C_{ij})$，其中 $C_{ij}=(-1)^{i+j}\det A_{ij}$ 是 $A$ 的 $(i,j)$-代数余子式，这一矩阵的转置 $C^{T}$ 称为 $A$ 的伴随矩阵 $\operatorname{adj}(A)$。
2. $A$ 的逆矩阵就是 $A^{-1}=\operatorname{adj}(A) /\det(A)$。

然而，在实际应用中以上公式在 $n>3$ 时并不有用，因为计算行列式需要较长的时间来计算。如果我们需要实际计算 $A^{-1}$，使用 Gauss-Jordan 消元是一个更有效的方法。

## Expansion by Cofactors

### Theorem 2.20

设 $A$ 是 $n\times n$ 矩阵，则

$$
\begin{gather}
\det A=\sum_{k=1}^{n} (-1)^{i+k} a_{ik} \det A_{ik}
\end{gather}
$$

以上等式称为行列式的按第 $i$ 行展开。通过 $\det A^{T}=\det A$，我们还可以将行列式按第 $j$ 列展开。

#### Proof

和之前一样，我们用 $A_{i}(\mathbf{x})$ 表示将 $A$ 的第 $i$ 行替换为 $\mathbf{x}$ 得到的矩阵。取 $\mathbb{R}^{n}$ 的标准基 $\mathbf{e}_{1},\dots,\mathbf{e}_{n}$（等同于行向量），则 $A$ 的第 $i$ 行可以写成

$$
\begin{gather}
\sum_{k=1}^{n} a_{ik}\mathbf{e}_{k}
\end{gather}
$$

从而由行列式的多线性性有

$$
\begin{align}
\det A &= \sum_{k=1}^{n} a_{ik} \det A_{i}(\mathbf{e}_{k}) \\
&=\sum_{k=1}^{n} (-1)^{i+k} a_{ik}\det A_{ik}
\end{align}
$$

其中最后一个等式由 [[#Lemma 2.17]] 给出。

# 3 Review of Topology of $\mathbb{R}^{n}$

## Metric Spaces

给定一个集合 $X$，其上的一个度量是函数 $d\colon X\times X\to \mathbb{R}$，满足以下公理：

1. $d(x,y)\geq 0$，且等式成立当且仅当 $x=y$。
2. $d(x,y)=d(y,x)$。
3. $d(x,z)\leq d(x,y)+d(y,z)$。

集合 $X$ 与其上的度量共同构成了一个度量空间。

设 $X$ 是具有度量 $d$ 的度量空间，$Y\subset X$，则 $d$ 限制在 $Y\times Y$ 上同样满足度量的三条公理，因此 $Y$ 也是一个度量空间，称为 $X$ 的一个子空间。

$\mathbb{R}^{n}$ 上最重要的两个度量为

$$
\begin{gather}
d(\mathbf{x},\mathbf{y})=\lVert \mathbf{x}-\mathbf{y} \rVert \quad \text{and} \quad d(\mathbf{x},\mathbf{y})=\lvert \mathbf{x}-\mathbf{y} \rvert 
\end{gather}
$$

分别称为 Euclidean 度量与上确界度量。由 Euclidean 范数与上确界范数的等价性，以上两个度量也是等价的。我们称带有 Euclidean 度量的 $\mathbb{R}^{n}$ 为 $n$ 维 Euclidean 空间。

设 $X$ 是具有度量 $d$ 的度量空间，给定 $x_{0}\in X$ 和 $\varepsilon>0$，我们定义

$$
\begin{gather}
U(x_{0},\varepsilon)=\{ x : d(x,x_{0})<\varepsilon \}
\end{gather}
$$

为 $x_{0}$ 的 $\varepsilon$-邻域。$U\subset X$ 称为是开的，如果每个 $x_{0}\in U$ 都有一个 $\varepsilon$-邻域包含于 $U$ 中。$C\subset X$ 称为是闭的，如果其补集 $X\setminus C$ 是开的。显然每个 $\varepsilon$-邻域都是开集。

包含 $x_{0}$ 的开集 $U$ 称为 $x_{0}$ 的一个邻域。

### Theorem 3.1

设 $X$ 是度量空间，则 $X$ 中开集的任意并集与有限交集是开集，$X$ 中闭集的任意交集与有限并集是闭集。

### Theorem 3.2

设 $X$ 是度量空间，$Y$ 是 $X$ 的子空间。一个集合 $A$ 在 $Y$ 中开当且仅当存在 $X$ 中的开集 $U$ 使得 $A=U\cap Y$。类似地，一个集合 $A$ 在 $Y$ 中闭当且仅当存在 $X$ 中的闭集 $C$ 使得 $A=C\cap Y$。

因此如果 $A$ 在 $Y$ 中开，且 $Y$ 在 $X$ 中开，那么 $A$ 在 $X$ 中开。类似地，如果 $A$ 在 $Y$ 中闭，且 $Y$ 在 $X$ 中闭，那么 $A$ 在 $X$ 中闭。

设 $X$ 是度量空间，称 $x_{0}$ 是 $X$ 的一个极限点，如果 $x_{0}$ 的每个 $\varepsilon$-邻域都与 $A\setminus\{ x_{0} \}$ 相交。等价地，$x_{0}$ 是极限点如果 $x_{0}$ 的每个 $\varepsilon$-邻域都包含 $A$ 中的无穷多个点。

### Theorem 3.3

设 $A\subset X$，则 $A$ 与 $A$ 的极限点的并集 $\overline{A}$ 在 $X$ 中闭。$X$ 的一个子集是闭的当且仅当它包含它的所有极限点。

集合 $\overline{A}$ 称为 $A$ 的闭包。

在 $\mathbb{R}^{n}$ 中，相应于两个标准度量的 $\varepsilon$-邻域有特殊的名字。我们称 $\mathbf{a}$ 关于 Euclidean 度量的 $\varepsilon$-邻域为开球 $B(\mathbf{a},\varepsilon)$；而 $\mathbf{a}$ 关于上确界度量的 $\varepsilon$-邻域为开立方体 $C(\mathbf{a},\varepsilon)$。不等式 $\lvert \mathbf{x} \rvert\leq \lVert \mathbf{x} \rVert\leq \sqrt{ n }\lvert \mathbf{x} \rvert$ 给出了如下关系：

$$
\begin{gather}
B(\mathbf{a},\varepsilon)\subset C(\mathbf{a},\varepsilon)\subset B(\mathbf{a},\sqrt{ n }\varepsilon)
\end{gather}
$$

而以上关系又给出了如下结果：

### Theorem 3.4

设 $X\subset \mathbb{R}^{n}$，无论取 Euclidean 度量还是上确界度量，$X$ 上的开集集合是相同的。对 $X$ 上的闭集集合同理。

一般来说，任何只依赖于 $X$ 上的开集集合，而与度量的具体性质无关的性质都称为是一个拓扑性质。极限、连续性、紧致性、连通性等都是拓扑性质的例子。

## Limits and Continuity

设 $X,Y$ 是度量空间，其上的度量分别为 $d_{X},d_{Y}$。

我们称函数 $f\colon X\to Y$ 在 $x_{0}\in X$ 处连续，如果对任意 $f(x_{0})$ 的邻域 $V$，存在 $x_{0}$ 的邻域 $U$ 使得 $f(U)\subset V$。我们称函数 $f$ 在 $X$ 上连续，如果 $f$ 在 $X$ 的每一点处连续。$f$ 的连续性也等价于条件：对任意开集 $V\subset Y$，集合

$$
\begin{gather}
f^{-1}(V)=\{ x \in X : f(x) \in V \}
\end{gather}
$$

在 $X$ 中开。或者，对任意闭集 $D\subset Y$，集合 $f^{-1}(D)$ 在 $X$ 中闭。

在度量空间上，连续性可以通过度量的 $\varepsilon-\delta$ 定义来描述。称 $f$ 在 $x_{0}$ 处连续，如果对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对 $x \in X$ 有

$$
\begin{gather}
d_{X}(x,x_{0})<\delta \implies d_{Y}(f(x),f(x_{0}))<\varepsilon
\end{gather}
$$

在上面的条件中，有可能存在一个 $\delta>0$，使得 $x_{0}$ 的 $\delta$-邻域只有 $x_{0}$ 一个点。在这种情况下，$x_{0}$ 称为 $X$ 的一个孤立点。显然，任何函数在孤立点处都连续。

从 $X$ 到 $Y$ 的常值函数是连续的，并且恒等函数 $i_{X}\colon X\to X$ 也是连续的。此外，我们还有如下的结果：

### Theorem 3.5

(a) 设 $A\subset X$ 且 $x_{0}\in A$，如果 $f\colon X\to Y$ 在 $x_{0}$ 处连续，那么 $f$ 在 $A$ 上的限制 $f|A\colon A\to Y$ 也在 $x_{0}$ 处连续。

(b) 设 $f\colon X\to Y$ 在 $x_{0}$ 处连续，$g\colon Y\to Z$ 在 $f(x_{0})$ 处连续，则 $g\circ f\colon X\to Z$ 在 $x_{0}$ 处连续。

### Theorem 3.6

(a) 设 $X$ 是度量空间，设 $f\colon X\to \mathbb{R}^{n}$ 具有形式

$$
\begin{gather}
f(x)=(f_{1}(x),\dots,f_{n}(x))
\end{gather}
$$

则 $f$ 在 $x_{0}$ 处连续当且仅当每个 $f_{i}\colon X\to \mathbb{R}$ 在 $x_{0}$ 处连续。函数 $f_{i}$ 称为 $f$ 的第 $i$ 个分量函数。

(b) 设 $f,g\colon X\to \mathbb{R}$ 在 $x_{0}$ 处连续，则 $f\pm g,fg$ 均在 $x_{0}$ 处连续，并且如果 $g(x_{0})\neq 0$，那么 $f /g$ 在 $x_{0}$ 处连续。

(c) 定义为 $\pi_{i}(x)=x_{i}$ 的投影函数 $\pi_{i}\colon \mathbb{R}^{n}\to \mathbb{R}$ 是连续的。

现在我们定义极限的概念。设 $X$ 是度量空间，$A\subset X$，且 $f\colon A\to Y$。设 $x_{0}$ 是 $A$ 的一个极限点，我们称 $x$ 趋于 $x_{0}$ 时 $f(x)$ 的极限是 $y_{0}$，如果对任意 $y_{0}$ 的邻域 $V$，存在 $x_{0}$ 的邻域 $U$ 使得

$$
\begin{gather}
x \in U\cap A \setminus \{ x_{0} \} \implies f(x) \in V
\end{gather}
$$

我们将以上语句记作

$$
\begin{gather}
f(x)\to y_{0} \quad (x\to x_{0})
\end{gather}
$$

或者

$$
\begin{gather}
\lim_{ x \to x_{0} } f(x)=y_{0}
\end{gather}
$$

在以上定义中，$x_{0}$ 是极限点保证了 $U\cap A\setminus\{ x_{0} \}$ 总是非空的。当 $x_{0}$ 是孤立点时，我们不定义 $x$ 趋于 $x_{0}$ 的极限。

和连续性一样，在度量空间上我们有极限的 $\varepsilon-\delta$ 定义。当 $x\to x_{0}$ 时有 $f(x)\to y_{0}$，如果对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对 $x \in A$ 有

$$
\begin{gather}
0<d_{X}(x,x_{0})<\delta \implies d_{Y}(f(x),y_{0})<\varepsilon
\end{gather}
$$

### Theorem 3.7

设 $f\colon X\to Y$。如果 $x_{0}$ 是 $X$ 的孤立点，那么 $f$ 在 $x_{0}$ 处连续。如果 $x_{0}$ 是 $X$ 的极限点，那么 $f$ 在 $x_{0}$ 处连续当且仅当 $\lim_{ x \to x_{0} }f(x)=f(x_{0})$。

### Theorem 3.8

(a) 设 $A\subset X$，$f\colon A\to \mathbb{R}^{n}$ 具有形式

$$
\begin{gather}
f(x)=(f_{1}(x),\dots,f_{n}(x))
\end{gather}
$$

令 $\mathbf{a}=(a_{1},\dots,a_{n})$，则 $\lim_{ x \to x_{0} }f(x)=\mathbf{a}$ 当且仅当对每个 $i$ 有 $\lim_{ x \to x_{0} }f_{i}(x)=a_{i}$。

(b) 设 $f,g\colon A\to \mathbb{R}$，如果当 $x\to x_{0}$ 时 $f(x)\to a$ 且 $g(x)\to b$，则当 $x\to x_{0}$ 时有

$$
\begin{gather}
f(x)\pm g(x) \to a\pm b \\
f(x)g(x) \to ab
\end{gather}
$$

并且如果 $b\neq 0$ 则 $f(x) /g(x)\to a /b$。

## Interior and Exterior

### Definition 3.9 interior 内部，exterior 外部，boundary 边界

设 $A\subset \mathbb{R}^{n}$。$A$ 的内部 $\operatorname{Int}A$ 定义为所有包含于 $A$ 的开集的并集；$A$ 的外部 $\operatorname{Ext}A$ 定义为所有与 $A$ 不相交的开集的并集；而 $A$ 的边界 $\operatorname{Bd}A$ 定义为所有不属于 $A$ 的内部和外部的点构成的集合。

一个点 $\mathbf{x}\in \mathbb{R}^{n}$ 属于 $\operatorname{Bd}A$ 当且仅当 $\mathbf{x}$ 的任何邻域都与 $A$ 的内部和外部相交。此外，$\mathbb{R}^{n}$ 是集合 $\operatorname{Int}A,\operatorname{Ext}A,\operatorname{Bd}A$ 的无交并，前两者是开集，而后者是闭集。

设 $Q\subset \mathbb{R}^{n}$ 是长方体

$$
\begin{gather}
Q=[a_{1},b_{1}]\times \dots \times[a_{n},b_{n}]
\end{gather}
$$

它的内部是

$$
\begin{gather}
\operatorname{Int}Q=(a_{1},b_{1})\times\dots \times(a_{n},b_{n})
\end{gather}
$$

我们通常称 $\operatorname{Int}Q$ 为一个开长方体。

一个开立方体是开长方体的特例。事实上，

$$
\begin{gather}
C(\mathbf{a},\varepsilon)=(a_{1}-\varepsilon,a_{1}+\varepsilon)\times\dots \times(a_{n}-\varepsilon,a_{n}+\varepsilon)
\end{gather}
$$

其对应的（闭）长方体为

$$
\begin{gather}
C=[a_{1}-\varepsilon,a_{1}+\varepsilon]\times\dots \times[a_{n}-\varepsilon,a_{n}+\varepsilon]
\end{gather}
$$

它通常被称为一个（闭）立方体。

# 4 Compact Subspaces and Connected Subspaces of $\mathbb{R}^{n}$

## Compact Spaces

### Definition 4.1 covering 覆盖，compact 紧致的

设 $X\subset \mathbb{R}^{n}$。$X$ 的一个覆盖是 $\mathbb{R}^{n}$ 中的一族集合，使得它们的并集包含 $X$。如果集族中的集合都是开集，我们就称它是 $X$ 的一个开覆盖。称 $X$ 的紧致的，如果 $X$ 的每个开覆盖都有一个有限子集，使得它的并集也包含 $X$。

下面的定理表明，集合的紧致性与它所在的环绕空间无关。

### Theorem 4.2

$X\subset \mathbb{R}^{n}$ 是紧致的当且仅当对任意由 $X$ 中的开集组成的，并集为 $X$ 的集族，存在它的一个有限子集，使得后者的并集等于 $X$。

### Theorem 4.3

$\mathbb{R}^{n}$ 中的长方体 $Q=[a_{1},b_{1}]\times\dots \times[a_{n},b_{n}]$ 是紧致的。特别地，$\mathbb{R}$ 中的有界闭区间 $[a,b]$ 是紧致的。

### Definition 4.4 bounded 有界的

称 $X\subset \mathbb{R}^{n}$ 是有界的，如果存在 $M$ 使得对任意 $\mathbf{x}\in X$ 有 $\lvert \mathbf{x} \rvert\leq M$。

$\mathbb{R}^{n}$ 上的紧致集具有一个简单的等价条件，这就是如下定理所展示的内容。

### Theorem 4.5 (Heine-Boral)

$X\subset \mathbb{R}^{n}$ 是紧致的当且仅当 $X$ 闭且有界。

下面我们给出两个紧致集上函数的基本结果。

### Theorem 4.6 (最值定理)

设 $X\subset \mathbb{R}^{m}$ 是紧致的，$f\colon X\to \mathbb{R}^{n}$ 连续，则 $f(X)$ 是紧致集。

特别地，如果 $\phi\colon X\to \mathbb{R}$ 连续，那么 $\phi$ 有最大值和最小值。

### Theorem 4.7

设 $X\subset \mathbb{R}^{m}$ 是紧致的，$f\colon X\to \mathbb{R}^{n}$ 连续，则给定 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $\mathbf{x},\mathbf{y}\in X$ 有

$$
\begin{gather}
\lvert \mathbf{x}-\mathbf{y} \rvert <\delta \implies \lvert f(\mathbf{x})-f(\mathbf{y}) \rvert <\varepsilon
\end{gather}
$$

以上结论在范数取 Euclidean 范数时同样成立。

上述定理结论中的条件称为一致连续性，因此以上定理表明：紧致集上的连续函数是一致连续的。

下面我们证明一个可能不太熟悉的结果。

### Definition 4.8 neighborhood 邻域

设 $X\subset \mathbb{R}^{n}$。给定 $\varepsilon>0$，所有 $B(\mathbf{a},\varepsilon)$ 的并集，其中 $\mathbf{a}\in X$，称为 $X$ 在 Euclidean 度量下的 $\varepsilon$-邻域。类似地，所有 $C(\mathbf{a},\varepsilon)$ 的并集，其中 $\mathbf{a}\in X$，称为 $X$ 在上确界度量下的 $\varepsilon$-邻域。

### Theorem 4.9

设 $X\subset \mathbb{R}^{n}$ 是紧致的，$U$ 是包含 $X$ 的开集，则存在 $\varepsilon>0$ 使得 $X$ 的 $\varepsilon$-邻域（无论在哪个度量下）包含于 $U$。

#### Proof

$X$ 在 Euclidean 度量下的 $\varepsilon$-邻域包含于上确界度量下的 $\varepsilon$-邻域，因此我们只需证明上确界度量的情况即可。

**第一步**

设 $C\subset \mathbb{R}^{n}$，对 $\mathbf{x}\in \mathbb{R}^{n}$ 我们定义

$$
\begin{gather}
d(\mathbf{x},C)=\inf \{ \lvert \mathbf{x}-\mathbf{c} \rvert : \mathbf{c} \in C \}
\end{gather}
$$

称为 $\mathbf{x}$ 到 $C$ 的距离。我们来证明它作为 $\mathbf{x}$ 的函数是连续的。

取 $\mathbf{c}\in C,\mathbf{x},\mathbf{y}\in \mathbb{R}^{n}$，则有

$$
\begin{gather}
d(\mathbf{x},C)-\lvert \mathbf{x}-\mathbf{y} \rvert \leq \lvert \mathbf{x}-\mathbf{c} \rvert -\lvert \mathbf{x}-\mathbf{y} \rvert \leq\lvert \mathbf{y}-\mathbf{c} \rvert 
\end{gather}
$$

上式对任意 $\mathbf{c}\in C$ 成立，因此

$$
\begin{gather}
d(\mathbf{x},C)-\lvert \mathbf{x}-\mathbf{y} \rvert \leq d(\mathbf{y},C)
\end{gather}
$$

从而

$$
\begin{gather}
d(\mathbf{x},C)-d(\mathbf{y},C)\leq\lvert \mathbf{x}-\mathbf{y} \rvert 
\end{gather}
$$

交换 $\mathbf{x}$ 与 $\mathbf{y}$，上式仍然成立。这表明 $d(\cdot,C)$ 在 $\mathbb{R}^{n}$ 上 Lipschitz 连续。

**第二步** 我们证明本定理。

定义 $f\colon X\to \mathbb{R}$ 为

$$
\begin{gather}
f(\mathbf{x})=d(\mathbf{x},\mathbb{R}^{n}\setminus U)
\end{gather}
$$

则 $f$ 是连续函数，且 $f(\mathbf{x})>0$：对 $\mathbf{x}\in X$，存在它的一个 $\delta$-邻域包含于 $U$，从而 $f(\mathbf{x})\geq\delta$。由于 $X$ 紧致，故 $f$ 有最小值 $\varepsilon>0$，则 $X$ 的 $\varepsilon$-邻域包含于 $U$。

## Connected Spaces

如果 $X$ 是度量空间，称 $X$ 是连通的，如果 $X$ 不能写成两个非空开集 $A,B$ 的无交并。

### Theorem 4.10

$\mathbb{R}$ 上的闭区间 $[a,b]$ 是连通的。

### Theorem 4.11 (介值定理)

设 $X$ 是连通的，$f\colon X\to Y$ 连续，则 $f(X)$ 是连通集。

特别地，如果 $\phi\colon X\to \mathbb{R}$ 且 $\phi(x_{0})<r<\phi(x_{1})$，那么存在 $x \in X$ 使得 $f(x)=r$。

设 $\mathbf{a},\mathbf{b}\in \mathbb{R}^{n}$，我们定义连接 $\mathbf{a},\mathbf{b}$ 的线段为所有点 $\mathbf{x}=\mathbf{a}+t(\mathbf{b}-\mathbf{a})$，其中 $0\leq t\leq 1$，构成的集合。任何线段都是连通的，因为它是连通集 $[0,1]$ 在连续函数 $t\mapsto \mathbf{a}+t(\mathbf{b}-\mathbf{a})$ 下的像。

称一个集合 $A\subset \mathbb{R}^{n}$ 是凸的，如果对任意 $\mathbf{a},\mathbf{b}\in A$，连接两点的线段包含于 $A$。任何凸集都是连通的：假设不然，则 $A=U\cup V$，取 $\mathbf{a}\in U$ 且 $\mathbf{b}\in V$，$L$ 为连接 $\mathbf{a},\mathbf{b}$ 的线段，则集合 $U\cap L$ 与 $V\cap L$ 在 $L$ 中开，不相交，且并集为 $L$。这与 $L$ 的连通性矛盾。

特别地，$\mathbb{R}^{n}$ 中的球、立方体和长方体都是凸集，从而是连通的。