我们已经给出了 Euclidean 空间中有界集的体积的概念：如果 $A\subset \mathbb{R}^{k}$ 有界且可求体积，它的体积就定义为

$$
\begin{gather}
v(A)=\int_{A} 1
\end{gather}
$$

当 $k=1$ 时，通常称 $v(A)$ 为 $A$ 的长度，而当 $k=2$ 时，通常称 $v(A)$ 为 $A$ 的面积。

在微积分中，我们不仅对 $\mathbb{R}$ 的子集定义了长度的概念，我们也对 $\mathbb{R}^{2}$ 或 $\mathbb{R}^{3}$ 中的光滑曲线定义了长度。类似地，我们不仅对 $\mathbb{R}^{2}$ 的子集定义了面积，我们也对 $\mathbb{R}^{3}$ 中的光滑曲面定义了面积。本章，我们将引入曲线与曲面的 $k$ 维推广，它们称为 $k$ 维流形，并且我们为这些对象定义一个 $k$ 维体积的概念。我们还将定义 $k$ 维流形上的标量函数关于 $k$ 维体积的积分，这是微积分中“第一类”曲线、曲面积分的推广。

# 21 The Volume of a Parallelepiped

设 $\mathcal{P}$ 是 $\mathbb{R}^{n}$ 中的 $k$ 维平行六面体，其中 $k<n$。我们希望为 $\mathcal{P}$ 定义一个 $k$ 维体积（它的 $n$ 维体积是零，因为它包含在 $\mathbb{R}^{n}$ 的一个低维子空间中）。我们如何入手呢？

根据直观的体积概念，它必须要满足两个合理的约束。第一，我们知道正交变换（等距映射）保持 $n$ 维体积，因此我们同样要求它保持 $k$ 维体积。第二，如果一个平行六面体恰好位于子空间 $\mathbb{R}^{k}\times 0$ 中，那么它在 $\mathbb{R}^{n}$ 中的 $k$ 维体积应当等于它作为 $\mathbb{R}^{k}$ 中的平行六面体的体积。本节我们将证明，以上两个合理的约束唯一确定了 $k$ 维体积函数。

### Lemma 21.1

设 $W$ 是 $\mathbb{R}^{n}$ 的 $k$ 维子空间，则存在 $\mathbb{R}^{n}$ 的标准正交基使得它的前 $k$ 个向量构成了 $W$ 的一个基。

#### Proof

取 $W$ 的一个基，然后将其扩张为 $\mathbb{R}^{n}$ 的基 $\mathbf{a}_{1},\dots,\mathbf{a}_{n}$，其中 $\mathbf{a}_{1},\dots,\mathbf{a}_{k}$ 是 $W$ 的基。下面我们对这个基应用 Gram-Schmidt 过程，得到一个标准正交基 $\mathbf{b}_{1},\dots,\mathbf{b}_{n}$，满足

$$
\begin{gather}
\operatorname{span}(\mathbf{a}_{1},\dots,\mathbf{a}_{k})=\operatorname{span}(\mathbf{b}_{1},\dots,\mathbf{b}_{k})=W
\end{gather}
$$

换言之，$\mathbf{b}_{1},\dots,\mathbf{b}_{k}$ 是 $W$ 的基。

### Theorem 21.2

设 $W$ 是 $\mathbb{R}^{n}$ 的 $k$ 维子空间，则存在正交变换 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$，其将 $W$ 映射到 $\mathbb{R}^{k}\times 0$。

#### Proof

取 $\mathbb{R}^{n}$ 的一个标准正交基 $\mathbf{b}_{1},\dots,\mathbf{b}_{n}$ 满足 [[#Lemma 21.1]] 中的性质。定义 $g\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 为线性映射 $g(\mathbf{x})=B\mathbf{x}$，其中 $B=[\mathbf{b}_{1}\cdots \mathbf{b}_{n}]$ 是正交矩阵。则 $g$ 是正交变换，其将 $\mathbb{R}^{k}\times 0$ 映射到 $W$，因此 $h=g^{-1}$ 就是所求的变换。

### Theorem 21.3

存在唯一的函数 $V$，其将 $\mathbb{R}^{n}$ 的 $k$-元组 $(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$ 关联到一个非负实数，使得

(1) 如果 $h\colon \mathbb{R}^{n}\to \mathbb{R}^{n}$ 是正交变换，那么
$$
\begin{gather}
V(h(\mathbf{x}_{1}),\dots,h(\mathbf{x}_{k}))=V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})
\end{gather}
$$
(2) 如果 $\mathbf{y}_{1},\dots,\mathbf{y}_{k}\in \mathbb{R}^{k}\times 0$，即存在 $\mathbf{z}_{i}\in \mathbb{R}^{k}$ 使得
$$
\begin{gather}
\mathbf{y}_{i}=\begin{bmatrix}
\mathbf{z}_{i} \\
\mathbf{0}
\end{bmatrix}
\end{gather}
$$
则
$$
\begin{gather}
V(\mathbf{y}_{1},\dots,\mathbf{y}_{k})=\lvert \det [\mathbf{z}_{1}\cdots \mathbf{z}_{k}] \rvert 
\end{gather}
$$

这一函数 $V$ 消失当且仅当 $\mathbf{x}_{1},\dots,\mathbf{x}_{k}$ 线性相关。并且它满足等式
$$
\begin{gather}
V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})=V(X)=(\det(X^{T}X))^{1/2}
\end{gather}
$$
其中 $X$ 是 $n\times k$ 矩阵 $X=[\mathbf{x}_{1}\cdots \mathbf{x}_{k}]$。

#### Proof

给定 $X=[\mathbf{x}_{1}\cdots \mathbf{x}_{k}]$，我们定义

$$
\begin{gather}
F(X)=\det(X^{T}X)
\end{gather}
$$

**第一步**

如果 $h$ 是正交变换 $h(\mathbf{x})=A\mathbf{x}$，则

$$
\begin{gather}
F(AX)=\det((AX)^{T}(AX))=\det(X^{T}X)=F(X)
\end{gather}
$$

因此 $F$ 在正交变换下不变。此外，如果 $Z$ 是 $k\times k$ 矩阵，并令

$$
\begin{gather}
Y=\begin{bmatrix}
Z \\
0
\end{bmatrix}
\end{gather}
$$

那么

$$
\begin{gather}
F(Y)=\det\left([Z^{T}\quad 0]\begin{bmatrix}
Z \\
0
\end{bmatrix}\right)=\det(Z^{T}Z)=\det(Z)^{2}
\end{gather}
$$

**第二步**

给定 $\mathbf{x}_{1},\dots,\mathbf{x}_{k}\in \mathbb{R}^{n}$，设 $W$ 是 $\mathbb{R}^{n}$ 中包含这些向量的 $k$ 维子空间，令 $h(\mathbf{x})=A\mathbf{x}$ 是一个正交变换，其将 $W$ 映射到 $\mathbb{R}^{k}\times 0$。则我们有

$$
\begin{gather}
AX=\begin{bmatrix}
Z \\
0
\end{bmatrix}
\end{gather}
$$

因此 $F(X)=F(AX)=\det(Z)^{2}\geq 0$。其中 $F(X)=0$ 当且仅当 $Z$ 的各列线性相关，而后者又等价于 $\mathbf{x}_{1},\dots,\mathbf{x}_{k}$ 线性相关。

**第三步**

我们定义 $V(X)=F(X)^{1/2}$。则第一步表明 $V$ 满足所求的两个条件，而第二步则表明 $V$ 是唯一确定的，这就完成了证明。

### Definition 21.4

设 $\mathbf{x}_{1},\dots,\mathbf{x}_{k}\in \mathbb{R}^{n}$ 线性无关，我们定义平行六面体 $\mathcal{P}(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$ 的 $k$ 维体积为 $V(\mathbf{x}_{1},\dots,\mathbf{x}_{k})$。

### Example 21.5

考虑 $\mathbb{R}^{3}$ 中的 $2$-平行六面体 $\mathcal{P}(\mathbf{a},\mathbf{b})$，令 $X=[\mathbf{a}\quad \mathbf{b}]$，则 $V(X)$ 就是这个平行四边形的面积。利用公式 $\langle \mathbf{a},\mathbf{b} \rangle=\lVert \mathbf{a} \rVert\lVert \mathbf{b} \rVert\cos\theta$，其中 $\theta$ 是 $\mathbf{a},\mathbf{b}$ 的夹角，我们得到

$$
\begin{align}
V(X)^{2} &= \det(X^{T}X) \\
&= \det \begin{bmatrix}
\lVert \mathbf{a} \rVert ^{2} & \langle \mathbf{a},\mathbf{b} \rangle  \\
\langle \mathbf{b},\mathbf{a} \rangle  & \lVert \mathbf{b} \rVert ^{2}
\end{bmatrix} \\
&=\lVert \mathbf{a} \rVert ^{2}\lVert \mathbf{b} \rVert ^{2} (1-\cos^{2}\theta)=\lVert \mathbf{a} \rVert ^{2}\lVert \mathbf{b} \rVert ^{2}\sin^{2}\theta
\end{align}
$$

因此平行四边形的面积为

$$
\begin{gather}
V(X)=\lVert \mathbf{a} \rVert \lVert \mathbf{b} \rVert \sin\theta
\end{gather}
$$

这是一个熟悉的结论。

在微积分中，我们还见过平行四边形面积的另一个公式。定义 $\mathbf{a}$ 与 $\mathbf{b}$ 的叉积 $\mathbf{a}\times \mathbf{b}$ 为

$$
\begin{gather}
\mathbf{a}\times \mathbf{b}=\det \begin{bmatrix}
a_{2} & b_{2} \\
a_{3} & b_{3}
\end{bmatrix}\mathbf{e}_{1}-\det \begin{bmatrix}
a_{1} & b_{1} \\
a_{3} & b_{3}
\end{bmatrix}\mathbf{e}_{2}+\det \begin{bmatrix}
a_{1} & b_{1} \\
a_{2} & b_{2}
\end{bmatrix}\mathbf{e}_{3}
\end{gather}
$$

那么我们可以验证 $\lVert \mathbf{a}\times \mathbf{b} \rVert$ 就是 $\mathcal{P}(\mathbf{a},\mathbf{b})$ 的面积，换句话说我们有等式

$$
\begin{gather}
\lVert \mathbf{a} \rVert ^{2}\lVert \mathbf{b} \rVert ^{2}-\langle \mathbf{a},\mathbf{b} \rangle ^{2}=\lVert \mathbf{a}\times \mathbf{b} \rVert ^{2}
\end{gather}
$$

就像 $\mathbb{R}^{3}$ 中的平行四边形一样，在 $\mathbb{R}^{n}$ 中的 $k$-平行六面体也有两种不同的 $k$-体积公式。其一由 [[#Theorem 21.3]] 给出，其二则是上面的叉积公式的一种推广。

### Definition 21.6

设 $k\leq n$，$\mathbf{x}_{1},\dots,\mathbf{x}_{k}\in \mathbb{R}^{n}$。令 $X=[\mathbf{x}_{1}\cdots \mathbf{x}_{k}]$。如果 $I=(i_{1},\dots,i_{k})$ 是正整数的 $k$-元组，满足 $1\leq i_{1}<\dots<i_{k}\leq n$，我们就称 $I$ 是 $\{ 1,\dots,n \}$ 上的一个升序 $k$-元组。并且我们用

$$
\begin{gather}
X_{I} \quad \text{or} \quad X(i_{1},\dots,i_{k})
\end{gather}
$$

来表示 $X$ 的第 $i_{1},\dots,i_{k}$ 行构成的 $k\times k$ 子矩阵。

更一般地，设 $I=(i_{1},\dots,i_{k})$ 是 $\{ 1,\dots,n \}$ 上的任意 $k$-元组，我们用同样的符号 $X_{I}$ 来表示由 $X$ 的第 $i_{1},\dots,i_{k}$ 行组成的 $k\times k$ 矩阵，此时它不一定是 $X$ 的子矩阵，因为 $I$ 中可能有重复或逆序。

### Theorem 21.7

设 $k\leq n$，$X$ 是 $n\times k$ 矩阵，则

$$
\begin{gather}
V(X)=\left( \sum_{[I]} \det(X_{I})^{2} \right)^{1/2}
\end{gather}
$$

其中求和遍历 $\{ 1,\dots,n \}$ 上的所有升序 $k$-元组。

#### Proof

令

$$
\begin{gather}
F(X)=\det(X^{T}X), \quad G(X)=\sum_{[I]} \det(X_{I})^{2}
\end{gather}
$$

我们要证 $F=G$。

**第一步** 我们证明定理对 $k=1$ 和 $k=n$ 成立。

如果 $k=1$，那么 $X$ 就是列向量 $[\lambda_{1}\cdots \lambda_{n}]^{T}$，则

$$
\begin{gather}
F(X)=\sum_{i=1}^{n} \lambda_{i}^{2}=G(X)
\end{gather}
$$

如果 $k=n$，那么 $G$ 的求和中只有一项 $\det(X)^{2}$，于是

$$
\begin{gather}
F(X)=\det(X)^{2}=G(X)
\end{gather}
$$

**第二步** 我们证明如果 $X=[\mathbf{x}_{1}\cdots \mathbf{x}_{k}]$ 且各 $\mathbf{x}_{i}$ 相互正交，那么

$$
\begin{gather}
F(X)=\lVert \mathbf{x}_{1} \rVert ^{2}\cdots \lVert \mathbf{x}_{k} \rVert ^{2}
\end{gather}
$$

这是因为 $X^{T}X$ 中的项形如 $\mathbf{x}_{i}^{T}\mathbf{x}_{j}$，即两个列的内积。于是如果 $X$ 的各列正交，那么 $X^{T}X$ 就是一个对角矩阵，其对角线元素为 $\lVert \mathbf{x}_{i} \rVert^{2}$。

**第三步** 设 $j\neq \ell$，我们证明下面两个初等列变换不改变 $F$ 和 $G$ 的值：

1. 交换第 $j$ 列与第 $\ell$ 列。
2. 将第 $\ell$ 列的 $c$ 倍加到第 $j$ 列上。

我们知道，对 $X$ 做初等行变换等价于用对应的初等矩阵 $E$ 左乘 $X$，而对 $X$ 做初等列变换等价于用初等矩阵 $E$ 右乘 $X$。上面两个列变换不改变 $F$ 的值，因为它们对应的初等矩阵满足 $\det E=\pm 1$，从而

$$
\begin{align}
F(XE)&=\det(E^{T}X^{T}X^{T}E) \\
&=(\det E^{T})(\det X^{T}X)(\det E) \\
&=F(X)
\end{align}
$$

这些列变换也不改变 $G$ 的值，因为对 $X$ 做列变换，然后取 $i_{1},\dots,i_{k}$ 行与先取 $i_{1},\dots,i_{k}$ 行，然后再做列变换的结果是相同的，即

$$
\begin{gather}
(XE)_{I}=X_{I} E
\end{gather}
$$

于是

$$
\begin{align}
G(XE) &= \sum_{[I]} \det((XE)_{I})^{2} \\
&=\sum_{[I]} \det (X_{I}E)^{2} \\
&=\sum_{[I]} \det(X_{I})^{2} \det(E)^{2} \\
&=G(X)
\end{align}
$$

**第四步** 我们证明，如果我们对特例：$X$ 的最后一行除了最后一个元素外均为零，并且 $X$ 的各列正交证明了定理，那么我们就对所有矩阵证明了定理。

给定任意的 $X$，如果 $X$ 的最后一行有非零元素，那么我们可以用第三步中的列变换 (1)(2) 将 $X$ 变换为如下形式：

$$
\begin{gather}
D=\begin{bmatrix}
\ast \\
0 \quad  \cdots \quad  0 \quad \lambda
\end{bmatrix}
\end{gather}
$$

其中 $\lambda\neq 0$。如果 $X$ 的最后一行均为零，那么它也有以上形式，其中 $\lambda=0$。现在我们对 $D$ 的列应用无归一化的 Gram-Schmidt 过程，则 $D$ 的第一列保持不变，而 $D$ 的第 $j$ 列被替换为第 $j$ 列减去前面列的相应标量倍。在这一过程中，最后一行的形式不会改变。最后，我们就得到了一个各列正交的矩阵，且最后一行除了最后一个元素外均为零。

**第五步** 我们对 $n$ 进行归纳。

如果 $n=1$，那么 $k=1$，我们已在第一步中完成了证明。如果 $n=2$，那么 $k=1$ 或 $k=2$，这也在第一步中得到证明。

现在假设定理对行数小于 $n$ 的矩阵成立，我们对 $n\times k$ 矩阵进行证明。根据第一步，我们只需考虑 $1<k<n$ 的情况。根据第四步，我们可以假设 $X$ 的最后一行除了最后一个元素外都为零，并且 $X$ 的各列正交。则 $X$ 具有形式

$$
\begin{gather}
X=\begin{bmatrix}
\mathbf{b}_{1} & \cdots & \mathbf{b}_{k-1} & \mathbf{b}_{k} \\
0 & \cdots & 0 & \lambda
\end{bmatrix}
\end{gather}
$$

其中 $\mathbf{b}_{i}$ 是 $\mathbb{R}^{n-1}$ 中的正交向量。令

$$
\begin{gather}
B=[\mathbf{b}_{1}\cdots \mathbf{b}_{k}], \quad C=[\mathbf{b}_{1}\cdots \mathbf{b}_{k-1}]
\end{gather}
$$

则我们有

$$
\begin{align}
F(X) &= \lVert \mathbf{b}_{1} \rVert ^{2}\cdots \lVert \mathbf{b}_{k-1} \rVert ^{2}(\lVert \mathbf{b}_{k} \rVert ^{2}+\lambda^{2}) \\
&=F(B)+\lambda^{2}F(C)
\end{align}
$$

要计算 $G(X)$，我们将其分成两个求和，取决于其是否包含 $X$ 的最后一行：

$$
\begin{gather}
G(X)=\sum_{i_{k}<n} \det(X_{I})^{2}+\sum_{i_{k}=n} \det(X_{I})^{2}
\end{gather}
$$

上式第一项等于 $G(B)$，因为如果 $i_{k}<n$，那么 $X_{I}=B_{I}$。另一方面，如果 $i_{k}=n$，我们有

$$
\begin{gather}
\det X(i_{1},\dots,i_{k-1},n)=\pm \lambda \det X(i_{1},\dots,i_{k-1})
\end{gather}
$$

于是求和的第二项等于 $\lambda^{2} G(C)$，于是

$$
\begin{gather}
G(X)=G(B)+\lambda^{2}G(C)
\end{gather}
$$

根据归纳假设，$F(B)=G(B)$ 且 $F(C)=G(C)$，这就完成了证明。

# 22 The Volume of a Parametrized-Manifold

现在我们定义 $\mathbb{R}^{n}$ 中的参数化流形，并定义这类对象的 $k$ 维体积。这些对象是参数化曲线与参数化曲面的推广。

### Definition 22.1 parametrized-manifold 参数化流形

设 $k\leq n$，开集 $A\subset \mathbb{R}^{k}$，并令 $\alpha\colon A\to \mathbb{R}^{n}$ 为一个 $C^{r}$ 函数。我们称集合 $Y=\alpha(A)$ 以及函数 $\alpha$ 共同构成了一个 $k$ 维参数化流形，记作 $Y_{\alpha}$。我们定义 $Y_{\alpha}$ 的 $k$ 维体积为

$$
\begin{gather}
v(Y_{\alpha})=\int_{A} V(D\alpha)
\end{gather}
$$

如果右侧的积分存在。

我们来说明一下以上定义的动机。假设 $A$ 是 $\mathbb{R}^{k}$ 中一个长方体 $Q$ 的内部，且 $\alpha\colon A\to \mathbb{R}^{n}$ 在 $Q$ 的一个邻域中可以扩张为一个 $C^{r}$ 函数。令 $Y=\alpha(A)$。

取 $Q$ 的一个划分 $P$，考虑子长方体

$$
\begin{gather}
R=[a_{1},a_{1}+h_{1}]\times\dots \times[a_{k},a_{k}+h_{k}]
\end{gather}
$$

在 $\alpha$ 的作用下，$R$ 被映射到 $Y$ 上的一小片区域，它连接 $\mathbf{a}$ 与 $\mathbf{a}+h_{i}\mathbf{e}_{i}$ 的边被映射到 $Y$ 中的一条曲线，连接这条曲线两端的向量为

$$
\begin{gather}
\alpha(\mathbf{a}+h_{i}\mathbf{e}_{i})-\alpha(\mathbf{a})
\end{gather}
$$

我们知道，以上表达式的一个一阶近似为

$$
\begin{gather}
\mathbf{v}_{i}=D\alpha(\mathbf{a}) h_{i}\mathbf{e}_{i}=\frac{ \partial \alpha }{ \partial x_{i} } h_{i}
\end{gather}
$$

于是，我们将 $k$-平行六面体 $\mathcal{P}=\mathcal{P}(\mathbf{v}_{1},\dots,\mathbf{v}_{k})$ 作为 $\alpha(R)$ 的近似是合理的，前者的 $k$-体积为

$$
\begin{align}
V(\mathbf{v}_{1},\dots,\mathbf{v}_{k}) &= V(\partial\alpha /\partial x_{1},\dots,\partial\alpha /\partial x_{k}) h_{1}\cdots h_{k} \\
&= V(D\alpha) v(R)
\end{align}
$$

如果我们对以上表达式关于子长方体 $R$ 求和，我们就得到了积分

$$
\begin{gather}
\int_{A} V(D\alpha)
\end{gather}
$$

的一个近似，并且如果我们选取适当的 $P$，我们可以使近似的误差任意小。

![](5-1.png)

现在我们定义参数化流形上标量函数关于 $k$-体积的积分，这是微积分中“第一类”曲线/曲面积分的推广。

### Definition 22.2

设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数，$Y=\alpha(A)$。设 $f$ 是在 $Y$ 上有定义的实值连续函数，我们定义 $f$ 在 $Y_{\alpha}$ 上关于体积的积分为

$$
\begin{gather}
\int_{Y_{\alpha}} f\, \mathrm{d}V=\int_{A} (f\circ\alpha) V(D\alpha)
\end{gather}
$$

如果右侧的积分存在。

这里我们使用了符号 $\mathrm{d}V$ 来表示对体积的积分。注意到，在这个定义下，参数化流形的体积可以写成

$$
\begin{gather}
v(Y_{\alpha})=\int_{Y_{\alpha}} \mathrm{d}V
\end{gather}
$$

### Theorem 22.3

设 $g\colon A\to B$ 是 $\mathbb{R}^{k}$ 中开集上的微分同胚，$\beta\colon B\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数，$Y=\beta(B)$。设 $\alpha=\beta \circ g$，则 $\alpha\colon A\to \mathbb{R}^{n}$ 且 $Y=\alpha(A)$。如果 $f\colon Y\to \mathbb{R}$ 连续，则 $f$ 在 $Y_{\beta}$ 上可积当且仅当 $f$ 在 $Y_{\alpha}$ 上可积，此时

$$
\begin{gather}
\int_{Y_{\alpha}} f \, \mathrm{d}V=\int_{Y_{\beta}} f\, \mathrm{d}V
\end{gather}
$$

特别地，$v(Y_{\alpha})=v(Y_{\beta})$。

以上定理表明，标量函数对体积的积分不依赖于特定的参数化函数 $\alpha$。

#### Proof

我们要证

$$
\begin{gather}
\int_{A} (f\circ\alpha)V(D\alpha)=\int_{B} (f\circ\beta)V(D\beta)
\end{gather}
$$

其中一个积分存在当且仅当另一存在。

积分的变量替换定理给出

$$
\begin{gather}
\int_{B} (f\circ\beta)V(D\beta)=\int_{A} (f\circ\beta \circ g)V(D\beta \circ g)\lvert \det Dg \rvert 
\end{gather}
$$

由于 $\alpha=\beta \circ g$，我们只需证明

$$
\begin{gather}
V(D\beta \circ g)\lvert \det Dg \rvert =V(D\alpha)
\end{gather}
$$

任取 $\mathbf{x}\in A$，设 $\mathbf{y}=g(\mathbf{x})$，根据链式法则有

$$
\begin{gather}
D\alpha(\mathbf{x})=D\beta(\mathbf{y})Dg(\mathbf{x})
\end{gather}
$$

于是

$$
\begin{align}
V(D\alpha)^{2} &= \det(Dg(\mathbf{x})^{T} D\beta(\mathbf{y})^{T} D\beta(\mathbf{y})Dg(\mathbf{x})) \\
&=\det(Dg(\mathbf{x}))^{2} V(D\beta \circ g)^{2}
\end{align}
$$

这就完成了证明。

### Example 22.4

(1) 设 $A\subset \mathbb{R}$ 是开区间，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数，$Y=\alpha(A)$。则 $Y_{\alpha}$ 称为是 $\mathbb{R}^{n}$ 中的一条参数化曲线，它的 $1$ 维体积称为它的长度。并且我们有公式

$$
\begin{gather}
v(Y_{\alpha})=\int_{A} V(D\alpha)=\int_{A} (\alpha_{1}'(t)^{2}+\dots+\alpha_{n}'(t)^{2})^{1/2}
\end{gather}
$$

因为 $D\alpha$ 是列向量 $[\alpha_{1}' \cdots \alpha_{n}']^{T}$。当 $n=3$ 时，以上公式正是参数化曲线的弧长公式。

(2) 设开集 $A\subset \mathbb{R}^{2}$，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数，$Y=\alpha(A)$。则 $Y_{\alpha}$ 称为 $\mathbb{R}^{n}$ 中的一个参数化曲面，并且它的 $2$-体积称为它的面积。

在 $n=3$ 时，我们可以给出 $v(Y_{\alpha})$ 的一个简单公式。我们用 $(x,y)$ 来表示 $\mathbb{R}^{2}$ 中的点，则 $D\alpha=[\partial\alpha /\partial x\quad \partial\alpha /\partial y]$，从而

$$
\begin{gather}
v(Y_{\alpha})=\int_{A} V(D\alpha)=\int_{A} \left\lVert  \frac{ \partial \alpha }{ \partial x } \times \frac{ \partial \alpha }{ \partial y }   \right\rVert 
\end{gather}
$$

特别地，如果 $\alpha$ 具有形式

$$
\begin{gather}
\alpha(x,y)=(x,y,f(x,y))
\end{gather}
$$

也就是说，曲面的方程为 $z=f(x,y)$，其中 $f\colon A\to \mathbb{R}$ 是 $C^{r}$ 函数，则

$$
\begin{gather}
D\alpha=\begin{bmatrix}
1 & 0 \\
0 & 1 \\
\partial f / \partial x & \partial f /\partial y
\end{bmatrix}
\end{gather}
$$

从而

$$
\begin{gather}
v(Y_{\alpha})=\int_{A} (1+(\partial f /\partial x)^{2}+(\partial f /\partial y)^{2})^{1/2}
\end{gather}
$$

我们来用以上公式实际计算一个曲面的面积。

设 $A$ 为开圆盘 $x^{2}+y^{2}<a^{2}$，$f$ 为函数

$$
\begin{gather}
(a^{2}-x^{2}-y^{2})^{1/2}
\end{gather}
$$

则曲面 $z=f(x,y)$ 正是半径为 $a$ 的上半球。令 $\alpha(x,y)=(x,y,f(x,y))$，则

$$
\begin{gather}
V(D\alpha)=\frac{a}{(a^{2}-x^{2}-y^{2})^{1/2}}
\end{gather}
$$

因此，利用极坐标变换，我们有

$$
\begin{gather}
v(Y_{\alpha})=\int_{B} \frac{ar}{(a^{2}-r^{2})^{1/2}}
\end{gather}
$$

其中 $B=(0,a)\times(0,2\pi)$。这是一个广义积分，要使用 Fubini 定理，我们将积分区域限制在 $(0,a_{n})\times(0,2\pi)$，其中 $0<a_{n}<a$，然后再令 $a_{n}\to a$，得到

$$
\begin{gather}
v(Y_{\alpha})=\lim_{ n \to \infty } (-2\pi a)((a^{2}-a_{n}^{2})^{1/2}-a)=2\pi a^{2}
\end{gather}
$$

这就证明了半径为 $a$ 的球的表面积为 $4\pi a^{2}$。

# 23 Manifolds in $\mathbb{R}^{n}$

流形是现代几何学的核心对象，在本书中我们将只研究 $\mathbb{R}^{n}$ 的子流形。

### Definition 23.1 manifold without boundary 无边界流形，coordinate patch 坐标卡

设 $k>0$。设 $M\subset \mathbb{R}^{n}$ 满足如下性质：对每个 $\mathbf{p}\in M$，存在 $M$ 中包含 $\mathbf{p}$ 的开集 $V$，$\mathbb{R}^{k}$ 中的开集 $U$，以及一个连续双射（同胚）$\alpha\colon U\to V$，使得

1. $\alpha$ 是 $C^{r}$ 函数，
2. $\alpha^{-1}\colon V\to U$ 连续，
3. 对任意 $\mathbf{x}\in U$，$D\alpha(\mathbf{x})$ 的秩为 $k$。

则我们称 $M$ 是 $\mathbb{R}^{n}$ 中的一个 $C^{r}$ 无边界流形。函数 $\alpha$ 称为 $M$ 上在 $\mathbf{p}$ 处的一个坐标卡。

简单来说，一个流形 $M$ 就是在局部同胚于 Euclidean 空间的对象，这使得我们可以在 $M$ 的局部坐标卡上应用基于坐标的微积分与线性代数。

### Example 23.2

我们来研究上述定义中各条件不成立时会发生什么。

(1) 考虑 $k=1$ 的情况。如果 $\alpha$ 是 $M$ 上的坐标卡，那么条件 $\operatorname{rank}D\alpha=1$ 意味着 $D\alpha\neq 0$，这表明 $M$ 不能有驻点（$D\alpha=0$ 的点）或尖点（不可微的点）。例如，设 $\alpha\colon \mathbb{R}\to \mathbb{R}^{2}$ 定义为 $\alpha(t)=(t^{3},t^{2})$，并令 $M$ 为 $\alpha$ 的值域，则 $M$ 在原点处有一个驻点。此时 $\alpha$ 是 $C^{\infty}$ 的，$\alpha^{-1}$ 连续，但 $D\alpha$ 并不总有秩 $1$。

![](5-2.png)

类似地，设 $\beta\colon \mathbb{R}\to \mathbb{R}^{2}$ 为 $\beta(t)=(t^{3},\lvert t \rvert^{3})$，令 $N$ 为 $\beta$ 的值域，则 $N$ 在原点有一个尖点。此时 $\beta$ 是 $C^{2}$ 函数，$\beta^{-1}$ 连续，但 $D\beta$ 在 $t=0$ 处不存在，因而也不是秩 $1$ 的。

![](5-3.png)

(2) 考虑 $k=2$ 的情况。$\operatorname{rank}D\alpha(\mathbf{a})=2$ 的条件意味着 $D\alpha$ 的列 $\partial\alpha /\partial x_{1}$ 和 $\partial\alpha /\partial x_{2}$ 在 $\mathbf{a}$ 处线性无关。注意到，$\partial\alpha /\partial x_{j}$ 是函数 $f(t)=\alpha(\mathbf{a}+t\mathbf{e}_{j})$ 的速度向量，因而与曲面 $M$ 相切。这表明 $\partial\alpha /\partial x_{1}$ 和 $\partial\alpha /\partial x_{2}$ 张成了 $M$ 上的一个二维切平面。

![](5-4.png)

下面我们来展示该条件不满足的情况。考虑

$$
\begin{gather}
\alpha(x,y)=(x(x^{2}+y^{2}),y(x^{2}+y^{2}),x^{2}+y^{2})
\end{gather}
$$

令 $M$ 为 $\alpha$ 的值域，则 $M$ 在原点处没有切平面。此时 $\alpha$ 是 $C^{\infty}$ 函数，$\alpha^{-1}$ 连续，但 $D\alpha$ 在 $\mathbf{0}$ 处的秩不为 $2$。

![](5-5.png)

(3) $\alpha^{-1}$ 连续的条件同样去除了不同类型的“病态表现”。例如，定义

$$
\begin{gather}
\alpha(t)=(\sin 2t)(\lvert \cos t \rvert ,\sin t) \quad (0<t<\pi)
\end{gather}
$$

令 $M$ 为 $\alpha$ 的值域。

![](5-6.png)

函数 $\alpha$ 是 $C^{1}$ 的，且 $D\alpha$ 的秩为 $1$，并且 $\alpha$ 是从 $(0,\pi)$ 到 $M$ 的双射。然而，$\alpha^{-1}$ 不是连续的，因为 $\pi /2$ 的邻域 $U_{0}$ 在 $\alpha$ 下的像（从而是它在 $\alpha^{-1}$ 下的原像）不是 $M$ 中的开集。或者说，当 $M$ 中的点接近 $\mathbf{0}$ 时，在 $(0,\pi)$ 中不一定有 $t\to \pi /2$。

(4) 设开集 $A\subset \mathbb{R}^{k}$，$\alpha\colon A\to \mathbb{R}^{n}$ 是 $C^{r}$ 函数，$Y=\alpha(A)$。则 $Y_{\alpha}$ 是一个参数化流形，但 $Y$ 不一定是一个流形。不过，如果 $\alpha$ 是单射，$\alpha^{-1}$ 连续，并且 $D\alpha$ 的秩为 $k$，那么 $Y$ 就是一个无边界流形，并且它由单个坐标卡 $\alpha$ 覆盖。

现在我们来定义一般的流形。首先我们需要将可微性的概念推广到任意集合上。

### Definition 23.3

设 $S\subset \mathbb{R}^{k}$，$f\colon S\to \mathbb{R}^{n}$。我们称 $f$ 在 $S$ 上是 $C^{r}$ 连续的，如果 $f$ 可以扩张为一个在开集 $U\subset \mathbb{R}^{n}$ 上 $C^{r}$ 连续的函数 $g\colon U\to \mathbb{R}^{n}$。

容易证明，在这个定义下，$C^{r}$ 函数的复合仍然是 $C^{r}$ 函数。假设 $S\subset \mathbb{R}^{k}$，$f_{1}\colon S\to \mathbb{R}^{n}$ 是 $C^{r}$ 连续的，$f_{1}(S)\subset T$，且 $f_{2}\colon T\to \mathbb{R}^{p}$ 是 $C^{r}$ 连续的。将 $f_{1}$ 扩张为 $g_{1}\colon U\to \mathbb{R}^{n}$，$f_{2}$ 扩张为 $g_{2}\colon V\to \mathbb{R}^{p}$，则 $g_{2}\circ g_{1}$ 是定义在开集 $g_{1}^{-1}(V)$ 上的 $C^{r}$ 连续函数，它是 $f_{2}\circ f_{1}$ 的扩张。

下面的引理表明，如果函数在局部是 $C^{r}$ 连续的，那么它在全局也是 $C^{r}$ 连续的。

### Lemma 23.4

设 $S\subset \mathbb{R}^{k}$，$f\colon S\to \mathbb{R}^{n}$。如果对 $\mathbf{x}\in S$，存在邻域 $U_{\mathbf{x}}$ 以及 $C^{r}$ 函数 $g_{\mathbf{x}}:U_{\mathbf{x}}\to \mathbb{R}^{n}$ 使得在 $U_{\mathbf{x}}\cap S$ 上有 $f=g_{\mathbf{x}}$，则 $f$ 在 $S$ 上 $C^{r}$ 连续。

#### Proof

用邻域 $U_{\mathbf{x}}$ 覆盖 $S$，令 $A$ 为这些邻域的并集。取一族受 $\{ U_{\mathbf{x}} \}$ 控制的单位分解 $\{ \phi_{i} \}$。对每个 $i$，取一个邻域 $U_{\mathbf{x}}$，其包含 $\phi_{i}$ 的支撑集，并令 $g_{i}$ 表示 $C^{r}$ 函数 $g_{\mathbf{x}}$。$C^{r}$ 函数 $\phi_{i}g_{i}$ 在 $U_{\mathbf{x}}$ 的一个紧致子集外消失，通过令它在 $U_{\mathbf{x}}$ 外消失，我们将 $\phi_{i}g_{i}$ 扩张为 $A$ 上的 $C^{r}$ 函数 $h_{i}$。然后我们定义

$$
\begin{gather}
g(\mathbf{x})=\sum_{i=1}^{\infty} h_{i}(\mathbf{x})
\end{gather}
$$

现在，$A$ 的每个点都有一个邻域使得在其上只有有限个 $h_{i}(\mathbf{x})$ 非零，从而 $g$ 在这个邻域上 $C^{r}$ 连续，因而 $g$ 在 $A$ 上 $C^{r}$ 连续。

此外，如果 $\mathbf{x}\in S$，那么对任意 $i$ 和 $\phi_{i}(\mathbf{x})\neq 0$ 有

$$
\begin{gather}
h_{i}(\mathbf{x})=\phi_{i}(\mathbf{x})g_{i}(\mathbf{x})=\phi_{i}(\mathbf{x})f(\mathbf{x})
\end{gather}
$$

因此对 $\mathbf{x}\in S$ 有

$$
\begin{gather}
g(\mathbf{x})=\sum_{i=1}^{\infty} \phi_{i}(\mathbf{x})f(\mathbf{x})=f(\mathbf{x})
\end{gather}
$$

这就完成了证明。

### Definition 23.5 upper half-space 上半平面

定义 $\mathbb{H}^{k}$ 为 $\mathbb{R}^{k}$ 的上半平面

$$
\begin{gather}
\mathbb{H}^{k}=\{ (x_{1},\dots,x_{k}) \in \mathbb{R}^{k} : x_{k}\geq 0 \}
\end{gather}
$$

定义 $\mathbb{H}_{+}^{k}$ 为开上半平面

$$
\begin{gather}
\mathbb{H}_{+}^{k}=\{ (x_{1},\dots,x_{k}) \in \mathbb{R}^{k} : x_{k}> 0 \}
\end{gather}
$$

### Lemma 23.6

设 $U$ 在 $\mathbb{H}^{k}$ 中开，但不在 $\mathbb{R}^{k}$ 中开。令 $\alpha\colon U\to \mathbb{R}^{n}$ 为 $C^{r}$ 函数，$\beta\colon U'\to \mathbb{R}^{n}$ 是 $\alpha$ 在 $\mathbb{R}^{k}$ 中的开集 $U'$ 上的 $C^{r}$ 扩张。则对 $\mathbf{x}\in U$，导数 $D\beta(\mathbf{x})$ 仅取决于 $\alpha$，而与特定的扩张 $\beta$ 无关。于是我们可以将这个导数记作 $D\alpha(\mathbf{x})$。

#### Proof

要计算 $\partial\beta /\partial x_{j}$ 在 $\mathbf{x}$ 处的值，我们需要考虑差商

$$
\begin{gather}
\frac{\beta(\mathbf{x}+h\mathbf{e}_{j})-\beta(\mathbf{x})}{h}
\end{gather}
$$

然后取 $h\to 0$ 时的极限。由于 $\beta$ 是 $C^{r}$ 连续的，因此以上表达式在 $h\to 0$ 时的极限存在，并且等于 $h$ 从正数趋于 $0+$ 的极限。在这种情况下，如果 $\mathbf{x}\in \mathbb{H}^{k}$，那么也有 $\mathbf{x}+h\mathbf{e}_{j}\in \mathbb{H}^{k}$。又因为 $\beta$ 和 $\alpha$ 在 $\mathbb{H}^{k}$ 上相等，导数 $D\beta(\mathbf{x})$ 的值仅取决于 $\alpha$。

![](5-7.png)

### Definition 23.7 manifold 流形

设 $k>0$。$\mathbb{R}^{n}$ 中的一个 $C^{r}$ 连续的 $k$-流形是一个 $M\subset \mathbb{R}^{n}$ 满足如下性质：对任意 $\mathbf{p}\in M$，存在 $M$ 中包含 $\mathbf{p}$ 的开集 $V$，$\mathbb{R}^{k}$ 或者 $\mathbb{H}^{k}$ 中的开集 $U$，以及一个连续双射 $\alpha\colon U\to V$ 使得

1. $\alpha$ 是 $C^{r}$ 函数，
2. $\alpha^{-1}\colon V\to U$ 连续，
3. 对 $\mathbf{x}\in U$，$D\alpha(\mathbf{x})$ 的秩为 $k$。

函数 $\alpha$ 称为 $M$ 上在 $\mathbf{p}$ 处的坐标卡。

我们定义 $k=0$ 时，$\mathbb{R}^{n}$ 中的一集离散点为 $\mathbb{R}^{n}$ 上的一个 $0$-流形。

比较上述定义与 [[#Definition 23.1 manifold without boundary 无边界流形，coordinate patch 坐标卡]]，我们看到一个无边界流形就是一个流形，其所有坐标卡的定义域都是 $\mathbb{R}^{k}$ 中的开集。

一个典型的带边界流形如下图所示。

![](5-8.png)

从中我们可以看出，在一个流形中，存在着两种不同类型的点：其一有同胚于 $\mathbb{R}^{n}$ 中的开球的邻域，其二有同胚于 $\mathbb{R}^{n}$ 中的半球的邻域。正是这第二类点构成了我们所说的“流形的边界”。下一节我们将给出一个精确的定义。

### Lemma 23.8

设 $M$ 是 $\mathbb{R}^{n}$ 中的流形，$\alpha\colon U\to V$ 是 $M$ 上的一个坐标卡。如果 $U_{0}$ 是 $U$ 的开子集，那么限制函数 $\alpha|U_{0}$ 也是 $M$ 上的一个坐标卡。

#### Proof

由于 $U_{0}$ 在 $U$ 中开，且 $\alpha^{-1}$ 连续，故 $\alpha(U_{0})=V_{0}$ 是开集。此外，$U_{0}$ 在 $\mathbb{R}^{k}$ 或 $\mathbb{H}^{k}$ 中开，取决于 $U$ 在 $\mathbb{R}^{k}$ 或 $\mathbb{H}^{k}$ 中开。于是 $\alpha|U_{0}$ 是坐标卡：它将 $U_{0}$ 一一对应于 $V_{0}$；它是 $C^{r}$ 连续的，因为 $\alpha$ 是 $C^{r}$ 函数；它的反函数作为 $\alpha^{-1}$ 的限制是连续的；它导数的秩为 $k$，因为 $\operatorname{rank}D\alpha(\mathbf{x})=k$。

# 24 The Boundary of a Manifold

本节我们来精确定义流形的边界，并给出一个常用的构造流形的方法。

### Theorem 24.1

设 $M$ 是 $\mathbb{R}^{n}$ 中 $C^{r}$ 连续的 $k$-流形，$\alpha_{0}\colon U_{0}\to V_{0}$，$\alpha_{1}\colon U_{1}\to V_{1}$ 是 $M$ 上的坐标卡，使得 $W=V_{0}\cap V_{1}\neq \varnothing$。令 $W_{i}=\alpha_{i}^{-1}(W)$，则函数

$$
\begin{gather}
\alpha_{1}^{-1}\circ\alpha_{0}\colon W_{0}\to W_{1}
\end{gather}
$$

是 $C^{r}$ 连续的，并且它的导数可逆。

我们称 $\alpha_{1}^{-1}\circ\alpha_{0}$ 为坐标卡 $\alpha_{0}$ 和 $\alpha_{1}$ 之间的转移函数。

#### Proof

我们只需证明如果 $\alpha\colon U\to V$ 是坐标卡，那么 $\alpha^{-1}\colon V\to \mathbb{R}^{k}$ 是 $C^{r}$ 函数，从而 $\alpha_{1}^{-1}\circ\alpha_{0}$ 作为两个 $C^{r}$ 函数的复合是 $C^{r}$ 连续的，其反函数 $\alpha_{0}^{-1}\circ\alpha_{1}$ 同理也是 $C^{r}$ 连续的。链式法则就表明这两个转移函数的导数可逆。

要证明 $\alpha^{-1}$ 是 $C^{r}$ 连续的，我们只需证明它在局部 $C^{r}$ 连续。设 $\mathbf{p}_{0}\in V$，$\alpha^{-1}(\mathbf{p}_{0})=\mathbf{x}_{0}$，我们证明 $\alpha^{-1}$ 可以扩张为 $\mathbf{p}_{0}$ 的邻域上的 $C^{r}$ 函数。

首先我们考虑 $U$ 在 $\mathbb{H}^{k}$ 中开，不在 $\mathbb{R}^{k}$ 中开的情况。

![](5-9.png)

将 $\alpha$ 扩张为 $\mathbb{R}^{k}$ 中开集 $U'$ 上的 $C^{r}$ 函数 $\beta$。由于 $D\alpha(\mathbf{x}_{0})$ 的秩为 $k$，因此这个矩阵中有 $k$ 行线性无关，不妨设为前 $k$ 行。设 $\pi\colon \mathbb{R}^{n}\to \mathbb{R}^{k}$ 将 $\mathbb{R}^{n}$ 投影到它的前 $k$ 个坐标上，则函数 $g=\pi \circ\beta$ 将 $U'$ 映射到 $\mathbb{R}^{k}$，且 $Dg(\mathbf{x}_{0})$ 可逆。根据反函数定理，$g$ 是一个从开集 $W$ 到 $g(W)$ 的 $C^{r}$ 微分同胚。

我们来证明 $h=g^{-1}\circ \pi$ 就是所求的扩张。首先注意到 $U_{0}=W\cap U$ 是 $U$ 的开子集，于是 $V_{0}=\alpha(U_{0})$ 在 $V$ 中开。这意味着存在开集 $A$ 使得 $A\cap V=V_{0}$。我们将 $A$ 限制在 $\pi^{-1}(g(W))$ 中，于是 $h\colon A\to \mathbb{R}^{k}$ 是 $C^{r}$ 函数。并且如果 $\mathbf{p}\in A\cap V=V_{0}$，取 $\mathbf{x}=\alpha^{-1}(\mathbf{p})$，我们有

$$
\begin{gather}
h(\mathbf{p})=g^{-1}(\pi(\mathbf{p}))=g^{-1}(\pi(\alpha(\mathbf{x})))=g^{-1}(g(\mathbf{x}))=\mathbf{x}=\alpha^{-1}(\mathbf{p})
\end{gather}
$$

这就是所要证的。

如果 $U$ 在 $\mathbb{R}^{k}$ 中开，此时我们令 $U'=U$ 且 $\beta=\alpha$，然后重复上面的论证即可。

### Definition 24.2

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $k$-流形，$\mathbf{p}\in M$。如果存在 $\mathbf{p}$ 处的坐标卡 $\alpha\colon U\to V$ 使得 $U$ 在 $\mathbb{R}^{k}$ 中开，我们就称 $\mathbf{p}$ 是 $M$ 的内部点。否则，我们就称 $\mathbf{p}$ 是 $M$ 的边界点。所有边界点构成的集合记作 $\partial M$，称为 $M$ 的边界。

注意，以上定义中的“内部”与“边界”与拓扑学中集合的内部与边界是不同的。为表示区分，我们用 $\operatorname{Bd}S$ 来表示集合 $S$ 的拓扑学边界，而用 $\partial M$ 来表示流形 $M$ 的几何学边界。

### Lemma 24.3

设 $M$ 是 $\mathbb{R}^{n}$ 中的 $k$-流形，$\alpha\colon U\to V$ 是 $\mathbf{p}$ 处的坐标卡。

(a) 如果 $U$ 在 $\mathbb{R}^{k}$ 中开，那么 $\mathbf{p}$ 是 $M$ 的内部点。
(b) 如果 $U$ 在 $\mathbb{H}^{k}$ 中开，且存在 $\mathbf{x}_{0}\in \mathbb{H}_{+}^{k}$ 使得 $\mathbf{p}=\alpha(\mathbf{x}_{0})$，那么 $\mathbf{p}$ 是 $M$ 的内部点。
(c) 如果 $U$ 在 $\mathbb{H}^{k}$ 中开，且存在 $\mathbf{x}_{0}\in \mathbb{R}^{k-1}\times 0$ 使得 $\mathbf{p}=\alpha(\mathbf{x}_{0})$，那么 $\mathbf{p}$ 是 $M$ 的边界点。

#### Proof

由定义立即得到 (a)。对于 (b)，我们取 $U_{0}=U\cap \mathbb{H}_{+}^{k}$，$V_{0}=\alpha(U_{0})$，则 $\alpha|U_{0}$ 是 $\mathbf{p}$ 处的坐标卡，其中 $U_{0}$ 在 $\mathbb{R}^{k}$ 中开。

我们证明 (c)。设 $\alpha_{0}\colon U_{0}\to V_{0}$ 是满足 (c) 中条件的坐标卡，我们假设存在 $\mathbf{p}$ 的坐标卡 $\alpha_{1}\colon U_{1}\to V_{1}$ 使得 $U_{1}$ 在 $\mathbb{R}^{k}$ 中开，然后推出矛盾。

由于 $V_{0},V_{1}$ 在 $M$ 中开，故 $W=V_{0}\cap V_{1}$ 在 $M$ 中开。设 $W_{i}=\alpha_{i}^{-1}(W)$，则 $W_{0}$ 在 $\mathbb{H}^{k}$ 中开且包含 $\mathbf{x}_{0}\in \mathbb{R}^{k-1}\times 0$，$W_{1}$ 在 $\mathbb{R}^{k}$ 中开。[[#Theorem 24.1]] 表明转移函数

$$
\begin{gather}
\alpha_{0}^{-1}\circ\alpha_{1}\colon W_{1}\to W_{0}
\end{gather}
$$

是一个 $C^{r}$ 连续双射，其导数可逆。因此 [[2 Differentiation#Theorem 8.2]] 表明 $W_{0}$ 是 $\mathbb{R}^{k}$ 中的开集。然而，$W_{0}\subset \mathbb{H}^{k}$ 且包含 $\mathbf{x}_{0}$，因此它不是 $\mathbb{R}^{k}$ 中的开集。这是一个矛盾，因而完成了证明。

![](5-10.png)

根据以上引理，$\mathbb{H}^{k}$ 自身也是 $\mathbb{R}^{k}$ 中的流形，并且 $\partial \mathbb{H}^{k}=\mathbb{R}^{k-1}\times 0$。

### Theorem 24.4

设 $M$ 是 $\mathbb{R}^{n}$ 中 $C^{r}$ 连续的 $k$-流形，如果 $\partial M\neq \varnothing$，那么 $\partial M$ 是 $\mathbb{R}^{n}$ 中 $C^{r}$ 连续的无边界 $k-1$ 流形。

#### Proof

设 $\mathbf{p}\in \partial M$，$\alpha\colon U\to V$ 为 $\mathbf{p}$ 的坐标卡。则 $U$ 在 $\mathbb{H}^{k}$ 中开并且存在 $\mathbf{x}_{0}\in \partial \mathbb{H}^{k}$ 使得 $\mathbf{p}=\alpha(\mathbf{x}_{0})$。根据 [[#Lemma 24.3]]，$U\cap \mathbb{H}_{+}^{k}$ 的每个点都被映射到 $M$ 的内部，而 $U\cap \partial \mathbb{H}^{k}$ 的每个点都被映射到 $M$ 的边界上。因此 $\alpha$ 在 $U\cap \partial \mathbb{H}^{k}$ 的限制函数是从 $U\cap \partial \mathbb{H}^{k}$ 到 $V_{0}=V\cap \partial M$ 的双射。

令 $U_{0}$ 为 $\mathbb{R}^{k-1}$ 中的开集，使得 $U_{0}\times 0=U\cap \partial \mathbb{H}^{k}$。如果 $\mathbf{x}\in U_{0}$，定义 $\alpha_{0}(\mathbf{x})=\alpha(\mathbf{x},0)$，则 $\alpha_{0}\colon U_{0}\to V_{0}$ 是 $\partial M$ 上的坐标卡：它是 $C^{r}$ 连续的；它的导数的秩为 $k-1$，因为 $D\alpha_{0}(\mathbf{x})$ 就是 $D\alpha(\mathbf{x},0)$ 的前 $k-1$ 列；$\alpha_{0}^{-1}$ 连续，因为它等于 $\alpha^{-1}$ 在 $V_{0}$ 上的限制，然后再把它投影到前 $k-1$ 个坐标上。

以上定理的证明中构造的坐标卡 $\alpha_{0}$ 称为是通过将 $\alpha$ 进行限制而得到的。

### Theorem 24.5

设开集 $\mathcal{O}\subset \mathbb{R}^{n}$，$f\colon \mathcal{O}\to \mathbb{R}$ 是 $C^{r}$ 函数。令 $M$ 由满足 $f(\mathbf{x})=0$ 的点 $\mathbf{x}$ 构成，$N$ 由满足 $f(\mathbf{x})\geq 0$ 的点 $\mathbf{x}$ 构成。假设 $M$ 非空且在其上 $Df(\mathbf{x})$ 的秩为 $1$，则 $N$ 是 $\mathbb{R}^{n}$ 中的一个 $n$-流形，满足 $\partial N=M$。

#### Proof

如果 $\mathbf{p}\in N$ 满足 $f(\mathbf{p})>0$，令 $U$ 由满足 $f(\mathbf{x})>0$ 的点 $\mathbf{x}$ 构成，则 $U$ 是 $\mathbb{R}^{n}$ 中的开集，并且恒等函数 $i\colon U\to U$ 是 $N$ 上的一个坐标卡。

现在设 $f(\mathbf{p})=0$。由于 $Df(\mathbf{p})$ 的秩为 $1$，必定存在一个 $D_{j}f(\mathbf{p})\neq 0$，不妨设 $D_{n}f(\mathbf{p})\neq 0$。定义 $F\colon \mathcal{O}\to \mathbb{R}^{n}$ 为 $F(\mathbf{x})=(x_{1},\dots,x_{n-1},f(\mathbf{x}))$，则

$$
\begin{gather}
DF=\begin{bmatrix}
I_{n-1} & 0 \\
\ast & D_{n}f
\end{bmatrix}
\end{gather}
$$

因此 $DF(\mathbf{p})$ 可逆。根据反函数定理，$F$ 是从 $\mathbf{p}$ 的邻域 $A$ 到开集 $B\subset \mathbb{R}^{n}$ 的微分同胚。进一步，$F$ 将 $N$ 中的开集 $A\cap N$ 映射到 $\mathbb{H}^{n}$ 中的开集 $B\cap \mathbb{H}^{n}$，因为 $\mathbf{x}\in N$ 当且仅当 $f(\mathbf{x})\geq 0$；并且 $F$ 将 $A\cap M$ 映射到 $B\cap \partial \mathbb{H}^{n}$，因为 $\mathbf{x}\in M$ 当且仅当 $f(\mathbf{x})=0$。于是 $F^{-1}\colon B\cap \mathbb{H}^{n}\to A\cap N$ 就是所求的坐标卡。

### Definition 24.6 ball 球，sphere 球面

定义半径为 $a$ 的 $n$-球 $B^{n}(a)$ 为

$$
\begin{gather}
B^{n}(a)=\{ \mathbf{x}\in \mathbb{R}^{n} : \lVert \mathbf{x} \rVert \leq a \}
\end{gather}
$$

定义半径为 $a$ 的 $n-1$ 球面 $S^{n-1}(a)$ 为

$$
\begin{gather}
S^{n-1}(a)=\{ \mathbf{x}\in \mathbb{R}^{n} : \lVert \mathbf{x} \rVert =a \}
\end{gather}
$$

### Corollary 24.7

$n$-球 $B^{n}(a)$ 是 $\mathbb{R}^{n}$ 上 $C^{\infty}$ 连续的 $n$-流形，且 $S^{n-1}(a)=\partial B^{n}(a)$。

#### Proof

我们对 $f(\mathbf{x})=a^{2}-\lVert \mathbf{x} \rVert^{2}$ 应用 [[#Theorem 24.5]]，则

$$
\begin{gather}
Df(\mathbf{x})=[(-2x_{1})\quad \cdots \quad (-2x_{n})]
\end{gather}
$$

它在 $S^{n-1}(a)$ 的每点上都非零。

# 25 Integrating a Scalar Function over a Manifold

现在我们定义一个连续标量函数 $f$ 在一个流形 $M$ 上的积分。为了保持简洁性，我们将限制在 $M$ 紧致的情况进行研究。向一般情况的推广可以采取与 [[3 Integration]] 中与广义积分的定义类似的方法。

首先，我们定义 $f$ 的支撑集可以被单个坐标卡覆盖的情况。

### Definition 25.1

设 $M$ 是 $\mathbb{R}^{n}$ 中 $C^{r}$ 连续的紧致 $k$-流形。$f\colon M\to \mathbb{R}$ 连续，$C=\operatorname{supp}(f)$，则 $C$ 是紧致集。假设 $M$ 上的坐标卡 $\alpha\colon U\to V$ 满足 $C\subset V$，则 $\alpha^{-1}(C)$ 紧致。因此，通过将 $U$ 替换为一个更小的开集，我们可以假设 $U$ 是有界的。我们定义 $f$ 在 $M$ 上的积分为

$$
\begin{gather}
\int_{M} f \, \mathrm{d}V=\int_{\operatorname{Int}U} (f\circ\alpha) V(D\alpha)
\end{gather}
$$

此处 $\operatorname{Int}U=U$ 如果 $U$ 在 $\mathbb{R}^{k}$ 中开；$\operatorname{Int}U=U\cap \mathbb{H}_{+}^{k}$ 如果 $U$ 在 $\mathbb{H}^{k}$ 中开而不在 $\mathbb{R}^{k}$ 中开。

容易看出上面的积分作为普通积分存在，从而其作为广义积分也存在。事实上，函数 $F=(f\circ\alpha)V(D\alpha)$ 在 $U$ 上连续，在紧致集 $\alpha^{-1}(C)$ 外消失，因此 $F$ 是有界的。如果 $U$ 在 $\mathbb{R}^{k}$ 上开，那么 $F$ 在 $\operatorname{Bd}U$ 上消失；如果 $U$ 在 $\mathbb{H}^{k}$ 上开而不在 $\mathbb{R}^{k}$ 上开，那么 $F$ 在 $(\operatorname{Bd}U) \setminus \partial \mathbb{H}^{k}$ 上消失，又 $\partial \mathbb{H}^{k}$ 的测度为零，因此 $F$ 在 $U$ 上可积，从而在 $\operatorname{Int}U$ 上可积。

### Lemma 25.2

如果 $f$ 的支撑集可以被单个坐标卡覆盖，则 $\int_{M}f\, \mathrm{d}V$ 不依赖于特定坐标卡的选取。

#### Proof

**第一步** 我们首先证明：设 $\alpha\colon U\to V$ 是包含 $f$ 支撑集的坐标卡，$W\subset U$ 是开集，使得 $\alpha(W)$ 也包含 $\operatorname{supp}(f)$，那么

$$
\begin{gather}
\int_{\operatorname{Int}W} (f\circ\alpha)V(D\alpha)=\int_{\operatorname{Int}U} (f\circ\alpha) V(D\alpha)
\end{gather}
$$

事实上，以上两个积分作为普通积分相等，因为积分项在 $W$ 以外消失，然后我们应用 [[3 Integration#Theorem 13.7]]。

**第二步**

令 $\alpha_{i}\colon U_{i}\to V_{i}$ 为 $M$ 的坐标卡，使得 $V_{0}$ 和 $V_{1}$ 都包含 $\operatorname{supp}(f)$。我们希望证明

$$
\begin{gather}
\int_{\operatorname{Int}U_{0}} (f\circ\alpha_{0})V(D\alpha_{0})=\int_{\operatorname{Int}U_{1}} (f\circ\alpha_{1}) V(D\alpha_{1})
\end{gather}
$$

取 $W=V_{0}\cap V_{1}$，令 $W_{i}=\alpha_{i}^{-1}(W)$，则根据第一步，我们只需证明与上面相同的等式，只是其中用 $W_{i}$ 替换了 $U_{i}$。由于 $\alpha_{1}^{-1}\circ\alpha_{0}\colon \operatorname{Int}W_{0}\to \operatorname{Int}W_{1}$ 是微分同胚，我们应用 [[#Theorem 22.3]] 即证。

要定义一般情况下的 $\int_{M}f\, \mathrm{d}V$，我们将使用 $M$ 上的单位分解。

### Theorem 25.3

设 $M$ 是 $\mathbb{R}^{n}$ 上 $C^{r}$ 连续的紧致 $k$-流形。给定覆盖 $M$ 的一族坐标卡，存在有限个 $C^{\infty}$ 函数 $\phi_{1},\dots,\phi_{\ell}\colon \mathbb{R}^{n}\to \mathbb{R}$ 使得

1. $\phi_{i}\geq 0$；
2. 给定 $i$，$\operatorname{supp}(\phi_{i})$ 是紧致集并且存在坐标卡 $\alpha_{i}\colon U_{i}\to V_{i}$ 属于给定的坐标卡族，满足 $\operatorname{supp}(\phi_{i})\cap M\subset V_{i}$；
3. 对 $\mathbf{x}\in M$ 有 $\sum \phi_{i}(\mathbf{x})=1$。

我们称 $\{ \phi_{1},\dots,\phi_{\ell} \}$ 为 $M$ 上的一个单位分解，其受给定坐标卡族的控制。

#### Proof

对每个属于给定坐标卡族的坐标卡 $\alpha\colon U\to V$，取 $\mathbb{R}^{n}$ 中的开集 $A_{V}$ 使得 $A_{V}\cap M=V$。令 $A$ 为所有 $A_{V}$ 的并集，我们取 $A$ 上的坐标分解，其受开集族 $\{ A_{V} \}$ 的控制。单位分解的局部有限性以及 $M$ 的紧致性保证了只有有限个函数 $\phi_{1},\dots,\phi_{\ell}$ 在 $M$ 上不恒为零。

### Definition 25.4

设 $M$ 是 $\mathbb{R}^{n}$ 上 $C^{r}$ 连续的紧致 $k$-流形。设 $f\colon M\to \mathbb{R}$ 连续。取 $M$ 的一个单位分解 $\phi_{1},\dots,\phi_{\ell}$，其受 $M$ 上所有坐标卡的控制。我们定义 $f$ 在 $M$ 上的积分为

$$
\begin{gather}
\int_{M} f \, \mathrm{d}V=\sum_{i=1}^{\ell} \int_{M} \phi_{i} f \, \mathrm{d}V
\end{gather}
$$

特别地，我们定义 $M$ 的 $k$ 维体积为

$$
\begin{gather}
v(M)=\int_{M} 1 \, \mathrm{d}V
\end{gather}
$$

如果 $f$ 的支撑集恰好被单个坐标卡 $\alpha\colon U\to V$ 覆盖，那么以上的定义与之前的定义 [[#Definition 25.1]] 一致：令 $A=\operatorname{Int}U$，则

$$
\begin{align}
\sum_{i=1}^{\ell} \int_{M} \phi_{i} f \, \mathrm{d}V &= \sum_{i=1}^{\ell} \int_{A} (\phi_{i}\circ\alpha)(f\circ\alpha) V(D\alpha) \\
&= \int_{A} \sum_{i=1}^{\ell} (\phi_{i}\circ\alpha)(f\circ\alpha)V(D\alpha) \\
&=\int_{A} (f\circ\alpha) V(D\alpha) \\
&=\int_{M} f \, \mathrm{d}V
\end{align}
$$

我们注意到这一定义同样也不依赖于特定单位分解的选取。设 $\psi_{1},\dots,\psi_{m}$ 是另一组单位分解，由于 $\psi_{j}f$ 的支撑集可以被单个坐标卡覆盖，我们可以应用上面的论证得到

$$
\begin{gather}
\sum_{i=1}^{\ell} \int_{M} \phi_{i} \psi_{j}f \, \mathrm{d}V=\int_{M} \psi_{j} f \, \mathrm{d}V
\end{gather}
$$

于是

$$
\begin{gather}
\sum_{j=1}^{m} \sum_{i=1}^{\ell} \int_{M} \phi_{i}\psi_{j}f \, \mathrm{d}V=\sum_{j=1}^{m} \int_{M} \psi_{j} f \, \mathrm{d}V
\end{gather}
$$

根据对称性，我们可以证明上式左侧的表达式同样等于

$$
\begin{gather}
\sum_{i=1}^{\ell} \int_{M} \phi_{i}f \, \mathrm{d}V
\end{gather}
$$

这就是所要证的。

以上积分的线性性是显然的，下面我们将其作为一个定理列出。

### Theorem 25.5

设 $M$ 是 $\mathbb{R}^{n}$ 上 $C^{r}$ 连续的紧致 $k$-流形，$f,g\colon M\to \mathbb{R}$ 连续，则

$$
\begin{gather}
\int_{M} (af+bg)\, \mathrm{d}V=a\int_{M} f \, \mathrm{d}V+b \int_{M} g \, \mathrm{d}V
\end{gather}
$$

以上的积分定义是纯粹理论性质的。下面我们给出一个实用的积分计算方法。

### Definition 25.6

设 $M$ 是 $\mathbb{R}^{n}$ 中 $C^{r}$ 连续的紧致 $k$-流形。称 $D\subset M$ 在 $M$ 中的测度为零，如果它可以被可数个坐标卡 $\alpha_{i}\colon U_{i}\to V_{i}$ 覆盖，使得

$$
\begin{gather}
D_{i}=\alpha_{i}^{-1}(D\cap V_{i})
\end{gather}
$$

在 $\mathbb{R}^{k}$ 中的测度为零。

### Theorem 25.7

设 $M$ 是 $\mathbb{R}^{n}$ 中 $C^{r}$ 连续的紧致 $k$-流形，$f\colon M\to \mathbb{R}$ 连续。假设对 $1\leq i\leq N$，$\alpha_{i}\colon A_{i}\to M_{i}$ 是 $M$ 上的坐标卡，使得 $A_{i}$ 在 $\mathbb{R}^{k}$ 中开，并且 $M$ 等于 $M$ 中的开集 $M_{1},\dots,M_{N}$ 和 $M$ 中的一个零测集 $K$ 的无交并。则

$$
\begin{gather}
\int_{M} f \, \mathrm{d}V =\sum_{i=1}^{N} \int_{A_{i}} (f\circ\alpha_{i}) V(D\alpha_{i})
\end{gather}
$$

以上定理表明，要计算 $\int_{M}f\, \mathrm{d}V$，我们可以将 $M$ 分解为一系列可参数化的部分，然后分别在每个部分上积分。

#### Proof

由于等式的两边对 $f$ 是线性的，因此我们只需证明 $f$ 的支撑集 $C$ 可以被单个坐标卡 $\alpha\colon U\to V$ 覆盖的情况。此时 $C$ 是紧致集，因此我们可以假设 $U$ 有界。于是

$$
\begin{gather}
\int_{M} f \, \mathrm{d}V=\int_{\operatorname{Int}U} (f\circ\alpha) V(D\alpha)
\end{gather}
$$

**第一步** 令 $W_{i}=\alpha^{-1}(M_{i}\cap V)$，$L=\alpha^{-1}(K\cap V)$，则 $W_{i}$ 在 $\mathbb{R}^{k}$ 中开，$L$ 在 $\mathbb{R}^{k}$ 中测度为零，并且 $U$ 等于 $W_{i}$ 以及 $L$ 的无交并。

![](5-11.png)

我们首先证明

$$
\begin{gather}
\int_{M} f\, \mathrm{d}V = \sum_{i=1}^{N} \int_{W_{i}} (f\circ\alpha) V(D\alpha)
\end{gather}
$$

事实上，各 $W_{i}$ 上的积分作为普通积分存在，因为 $F=(f\circ\alpha)V(D\alpha)$ 有界，且在 $(\operatorname{Bd}W_{i})\setminus L$ 上消失，于是

$$
\begin{align}
\sum_{i=1}^{N} \int_{W_{i}} F &= \int_{(\operatorname{Int}U) \setminus L} F \\
&=\int_{\operatorname{Int}U} F \\
&=\int_{M} f\, \mathrm{d}V
\end{align}
$$

**第二步** 我们来证明

$$
\begin{gather}
\int_{W_{i}} F=\int_{A_{i}} F_{i}
\end{gather}
$$

其中 $F_{i}=(f\circ\alpha_{i})V(D\alpha_{i})$。

![](5-12.png)

函数 $\alpha_{i}^{-1}\circ\alpha$ 是一个从 $W_{i}$ 到开集

$$
\begin{gather}
B_{i}=\alpha_{i}^{-1}(M_{i}\cap V)
\end{gather}
$$

的微分同胚。于是根据变量替换定理有

$$
\begin{gather}
\int_{W_{i}} F=\int_{B_{i}} F_{i}
\end{gather}
$$

接下来我们证明

$$
\begin{gather}
\int_{B_{i}} F_{i}=\int_{A_{i}} F_{i}
\end{gather}
$$

由于 $C=\operatorname{supp}(f)$ 在 $M$ 中闭，故 $\alpha_{i}^{-1}(C)$ 在 $A_{i}$ 中闭，从而

$$
\begin{gather}
D_{i}=A_{i} \setminus \alpha_{i}^{-1}(C)
\end{gather}
$$

在 $A_{i}$ 中开，从而在 $\mathbb{R}^{k}$ 中开。函数 $F_{i}$ 在 $D_{i}$ 上消失，因此根据广义积分的可加性，有

$$
\begin{gather}
\int_{A_{i}} F_{i}=\int_{B_{i}} F_{i}+\int_{D_{i}} F_{i}-\int_{B_{i}\cap D_{i}} F_{i}=\int_{B_{i}} F_{i}
\end{gather}
$$

这就完成了证明。

### Example 25.8

利用以上定理，我们给出球面 $S^{2}(a)$ 面积的另一种计算方法。

给定 $z_{0}$ 满足 $\lvert z_{0} \rvert<a$，球面 $S^{2}(a)$ 与平面 $z=z_{0}$ 的交线是圆

$$
\begin{gather}
x^{2}+y^{2}=a^{2}-z_{0}^{2}
\end{gather}
$$

这一事实表明我们可以用函数

$$
\begin{gather}
\alpha(t,z)=((a^{2}-z^{2})^{1/2}\cos t,(a^{2}-z^{2})^{1/2}\sin t,z)
\end{gather}
$$

对 $S^{2}(a)$ 进行参数化。

我们将 $\alpha$ 的定义域取为 $A=\{ (t,z) : 0<t<2\pi,\lvert z \rvert<a \}$，则 $\alpha$ 是一个坐标卡，其覆盖了全部的 $S^{2}(a)$，除了一个大圆，后者在球面上的测度为零。

![](5-13.png)

我们使用这个坐标卡计算 $S^{2}(a)$ 的面积。我们有

$$
\begin{gather}
D\alpha = \begin{bmatrix}
-(a^{2}-z^{2})^{1/2}\sin t & (-z\cos t) / (a^{2}-z^{2})^{1/2} \\
(a^{2}-z^{2})^{1/2}\cos t & (-z\sin t) / (a^{2}-z^{2})^{1/2} \\
0 & 1
\end{bmatrix}
\end{gather}
$$

于是 $V(D\alpha)=a$，从而

$$
\begin{gather}
v(S^{2}(a))=\int_{A} a=4\pi a^{2}
\end{gather}
$$

这一方法并不涉及广义积分的计算。