# Linear Transformations 线性变换

## Definition 9.1 vector space 向量空间，linear combination 线性组合，span 张成，linear independent (dependent) 线性无关（相关），dimension 维数，basis 基

(a) 称 $X\subset \mathbb{R}^{n}$ 是一个向量空间，如果对任意 $\mathbf{x},\mathbf{y}\in X$ 和 $c \in \mathbb{R}$ 有 $\mathbf{x}+\mathbf{y}\in X$ 且 $c\mathbf{x}\in X$。换句话说，$X$ 对加法和数乘封闭。

(b) 设 $\mathbf{x}_{1},\dots,\mathbf{x}_{k}\in \mathbb{R}^{n}$，$c_{1},\dots,c_{k}\in \mathbb{R}$，我们称

$$
\begin{gather}
c_{1}\mathbf{x}_{1}+\dots+c_{k}\mathbf{x}_{k}
\end{gather}
$$

为 $\mathbf{x}_{1},\dots,\mathbf{x}_{k}$ 的一个线性组合。如果 $S\subset \mathbb{R}^{n}$，我们定义 $S$ 的张成空间 $E=\operatorname{span}(S)$ 为所有 $S$ 中元素的线性组合构成的向量空间，并称 $S$ 是 $E$ 的一个张成集。

(c) 称 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{k} \}$ 是线性无关的，如果

$$
\begin{gather}
c_{1}\mathbf{x}_{1}+\dots+c_{k}\mathbf{x}_{k}=0 \implies c_{1}=\dots=c_{k}=0
\end{gather}
$$

否则，我们就称 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{k} \}$ 是线性相关的。

(d) 如果向量空间 $X$ 中存在一个大小为 $r$ 的线性无关集，但不存在大小为 $r+1$ 的线性无关集，我们就称 $X$ 的维数是 $r$，记作 $\dim X=r$。

特别地，$\{ \mathbf{0} \}$ 是一个向量空间，它的维数是 $0$。

(e) $X$ 的一个线性无关的张成集称为它的一个基。

如果 $B=\{ \mathbf{x}_{1},\dots,\mathbf{x}_{r} \}$ 是 $X$ 的一个基，那么任意 $\mathbf{x}\in X$ 都有唯一的表示

$$
\begin{gather}
\mathbf{x}=c_{1}\mathbf{x}_{1}+\dots+c_{r}\mathbf{x}_{r}
\end{gather}
$$

这样的表示存在，因为 $B$ 是张成集。这样的表示唯一，因为 $B$ 是线性无关的。系数 $c_{1},\dots,c_{r}$ 称为 $\mathbf{x}$ 在 $B$ 下的坐标。

在 $\mathbb{R}^{n}$ 中我们定义 $\mathbf{e}_{j}=(0,\dots,1,\dots,0)$ 为在第 $j$ 个位置是 $1$，其余位置为 $0$ 的向量，则 $\{ \mathbf{e}_{1},\dots,\mathbf{e}_{n} \}$ 构成了 $\mathbb{R}^{n}$ 的一个基，称为 $\mathbb{R}^{n}$ 上的标准基。如果 $\mathbf{x}=(x_{1},\dots,x_{n})\in \mathbb{R}^{n}$，则我们有

$$
\begin{gather}
\mathbf{x}=\sum_{j=1}^{n} x_{j} \mathbf{e}_{j}
\end{gather}
$$

## Theorem 9.2

如果向量空间 $X$ 由 $r$ 个向量张成，那么 $\dim X\leq r$。

### Proof

我们只需证明 $X$ 中任意线性无关集的大小都小于等于 $r$。

设 $\{ \mathbf{y}_{1},\dots,\mathbf{y}_{k} \}$ 在 $X$ 中线性无关，$S_{0}=\{ \mathbf{x}_{1},\dots,\mathbf{x}_{r} \}$ 张成 $X$。我们构造一列张成集 $S_{1},\dots,S_{k}$ 如下。

- 第 $1$ 步

集合 $\{ \mathbf{y}_{1},\mathbf{x}_{1},\dots,\mathbf{x}_{r} \}$ 张成 $X$，并且线性相关（$\mathbf{y}_{1}\in \operatorname{span}(S_{0})$），因此存在不全为零的实数 $a_{1},b_{1},\dots,b_{r}$ 使得

$$
\begin{gather}
a_{1}\mathbf{y}_{1}+\sum_{j=1}^{r} b_{j}\mathbf{x}_{j}=0
\end{gather}
$$

我们断言 $b_{1},\dots,b_{r}$ 不全为零。假设不然，由于 $\mathbf{y}_{1}\neq 0$，故 $a_{1}=0$，这与线性相关性矛盾。于是，某个 $\mathbf{x}_{j}$ 可以写成 $\mathbf{y}_{1}$ 与剩下的 $\mathbf{x}_{i}$ 的线性组合，因此去掉 $\mathbf{x}_{j}$ 后 $\mathbf{y}_{1}$ 与剩下的 $\mathbf{x}_{i}$ 构成的集合 $S_{1}$ 仍然张成 $X$。

- 第 $j$ 步

$S_{j-1}$ 包含 $\mathbf{y}_{1},\dots,\mathbf{y}_{j-1}$，以及 $S_{0}$ 中的 $r-j+1$ 个向量，通过重新编号，不妨记作 $\mathbf{x}_{1},\dots,\mathbf{x}_{r-j+1}$。把 $\mathbf{y}_{j}$ 加入 $S_{j-1}$ 中，由于 $\mathbf{y}_{j}\in \operatorname{span}(S_{j-1})$，得到的集合线性相关，故存在不全为零的实数 $a_{1},\dots,a_{j},b_{1},\dots,b_{r-j+1}$ 使得

$$
\begin{gather}
\sum_{i=1}^{j} a_{i}\mathbf{y}_{i}+\sum_{i=1}^{r-j+1} b_{i}\mathbf{x}_{i}=0
\end{gather}
$$

$b_{1},\dots,b_{r-j+1}$ 不全为零，因为 $\mathbf{y}_{1},\dots,\mathbf{y}_{j}$ 线性无关。于是我们可以去掉一个 $\mathbf{x}$，得到 $X$ 的张成集 $S_{j}$，其包含 $\mathbf{y}_{1},\dots,\mathbf{y}_{j}$ 和 $r-j$ 个 $\mathbf{x}$。

经过 $k$ 步后，我们用 $\mathbf{y}_{1},\dots,\mathbf{y}_{k}$ 替换了 $k$ 个 $\mathbf{x}$。在每一步中，我们证明了必然存在可供替换的 $\mathbf{x}$，因此 $\mathbf{x}$ 的数量 $r$ 必然大于等于 $\mathbf{y}$ 的数量 $k$。

## Corollary 9.3

$$
\begin{gather}
\dim \mathbb{R}^{n}=n
\end{gather}
$$

### Proof

标准基 $\{ \mathbf{e}_{1},\dots,\mathbf{e}_{n} \}$ 线性无关且张成 $\mathbb{R}^{n}$。根据维数的定义，$\dim \mathbb{R}^{n}\geq n$，再根据 [[#Theorem 9.2]]，$\dim \mathbb{R}^{n}\leq n$，即证。

## Theorem 9.4

设 $X$ 是向量空间，$\dim X=n$。

(a) 由 $n$ 个向量组成的集合 $E$ 张成 $X$ 当且仅当 $E$ 线性无关。
(b) $X$ 有基，并且每个基的大小均为 $n$。
(c) $X$ 中的线性无关集 $\{ \mathbf{y}_{1},\dots,\mathbf{y}_{r} \}$ 可以扩张为 $X$ 的一个基。

### Proof

(a) 设 $E=\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n} \}$。由于 $\dim X=n$，因此对任意 $\mathbf{y}\in X$，集合 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n},\mathbf{y} \}$ 线性相关。如果 $E$ 线性无关，那么 $\mathbf{y}$ 可以写成各 $\mathbf{x}_{j}$ 的线性组合，从而 $\mathbf{y}\in \operatorname{span}(E)$。

反之，如果 $E$ 线性相关，那么我们可以去掉一个 $\mathbf{x}_{j}$，而不改变 $E$ 的张成空间。但根据 [[#Theorem 9.2]]，$X$ 的张成集大小至少为 $n$，因此 $E$ 无法张成 $X$。

(b) 由于 $\dim X=n$，因此 $X$ 中必然存在一个大小为 $n$ 的线性无关集，而 (a) 表明任何这样的集合都能张成 $X$。

现在设 $B_{1},B_{2}$ 都是 $X$ 的基。由于 $B_{1}$ 线性无关，$B_{2}$ 张成 $X$，[[#Theorem 9.2]] 表明 $\lvert B_{1} \rvert\leq\lvert B_{2} \rvert$。下面交换 $B_{1}$ 与 $B_{2}$，再次应用 [[#Theorem 9.2]] 即证 $\lvert B_{1} \rvert=\lvert B_{2} \rvert$。

(c) 取 $X$ 的一个基 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n} \}$，构造集合

$$
\begin{gather}
\{ \mathbf{y}_{1},\dots,\mathbf{y}_{r},\mathbf{x}_{1},\dots,\mathbf{x}_{n} \}
\end{gather}
$$

以上集合显然是线性相关的。我们执行 [[#Theorem 9.2]] 证明中的过程，每一步去掉一个 $\mathbf{x}_{j}$，并保持集合张成 $X$。由于各 $\mathbf{y}$ 线性无关，因此它们不会在某一步中被去掉。经过 $r$ 步后，我们得到了一个大小为 $n$ 的张成集，由 (a) 可知它是线性无关的，从而是一个基。

## Definition 9.5 linear transformation 线性变换，linear operator 线性算子，invertible 可逆的

从向量空间 $X$ 到向量空间 $Y$ 的映射 $A$ 称为一个线性变换，如果对任意 $\mathbf{x},\mathbf{y}\in X$ 和 $c \in \mathbb{R}$ 有

$$
\begin{gather}
A(\mathbf{x}+\mathbf{y})=A\mathbf{x}+A\mathbf{y}, \quad A(c\mathbf{x})=cA\mathbf{x}
\end{gather}
$$

注意到 $A\mathbf{0}=\mathbf{0}$，并且线性变换 $A\colon X\to Y$ 完全由它在 $X$ 的基上的作用确定：如果 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n} \}$ 是一个基，那么任意 $\mathbf{x}\in X$ 都有唯一表示

$$
\begin{gather}
\mathbf{x}=\sum_{j=1}^{n} c_{j}\mathbf{x}_{j}
\end{gather}
$$

从而

$$
\begin{gather}
A\mathbf{x}=\sum_{j=1}^{n} c_{j} A\mathbf{x}_{j}
\end{gather}
$$

从向量空间 $X$ 到 $X$ 的线性变换称为线性算子。如果线性算子 $A$ 是一个双射，则称 $A$ 是可逆的，此时我们可以定义其逆算子 $A^{-1}$ 为

$$
\begin{gather}
A^{-1}(A\mathbf{x})=A(A^{-1}\mathbf{x})=\mathbf{x} \quad (\mathbf{x}\in X)
\end{gather}
$$

容易验证 $A^{-1}$ 也是线性算子。

在有限维向量空间上，一个重要结论是线性算子的单射性与满射性相互等价。

## Theorem 9.6

有限维向量空间 $X$ 上的线性算子 $A$ 是单射当且仅当它是满射。

### Proof

设 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n} \}$ 是 $X$ 的基。$A$ 线性性表明它的值域 $\operatorname{range}(A)$ 等于 $Q=\{ A\mathbf{x}_{1},\dots,A\mathbf{x}_{n} \}$ 的张成空间，因此由 [[#Theorem 9.4]] 知 $\operatorname{range}(A)=X$ 当且仅当 $Q$ 线性无关。我们来证明 $Q$ 线性无关当且仅当 $A$ 是单射。

如果 $Q$ 线性无关，则

$$
\begin{gather}
c_{1}A\mathbf{x}_{1}+\dots+c_{n}A\mathbf{x}_{n}=A(c_{1}\mathbf{x}_{1}+\dots+c_{n}\mathbf{x}_{n})=0 \implies c_{j}=0
\end{gather}
$$

这就是说，方程 $A\mathbf{x}=0$ 的解仅有 $\mathbf{x}=\mathbf{0}$，因此 $A$ 是单射：如果 $A\mathbf{x}=A\mathbf{y}$，那么 $A(\mathbf{x}-\mathbf{y})=0$，故 $\mathbf{x}=\mathbf{y}$。

反之，如果 $A$ 是单射，那么 $\sum c_{j}A\mathbf{x}_{j}=A\left( \sum c_{j}\mathbf{x}_{j} \right)=0$ 蕴含 $\sum c_{j}\mathbf{x}_{j}=0$，再由各 $\mathbf{x}$ 的线性无关性知 $c_{j}=0$，即证 $Q$ 线性无关。

## Definition 9.7

(a) 定义 $L(X,Y)$ 表示从向量空间 $X$ 到向量空间 $Y$ 的所有线性变换构成的集合。如果 $X=Y$，我们记 $L(X)=L(X,X)$。如果 $A_{1},A_{2}\in L(X,Y)$，$c_{1},c_{2}\in \mathbb{R}$，我们定义 $c_{1}A_{1}+c_{2}A_{2}$ 为

$$
\begin{gather}
(c_{1}A_{1}+c_{2}A_{2})(\mathbf{x})=c_{1}A_{1}\mathbf{x}+c_{2}A_{2}\mathbf{x} \quad (\mathbf{x}\in X)
\end{gather}
$$

容易证明 $c_{1}A_{1}+c_{2}A_{2}\in L(X,Y)$，因而 $L(X,Y)$ 也是一个向量空间。

(b) 设 $X,Y,Z$ 是向量空间，$A \in L(X,Y),B \in L(Y,Z)$，我们定义乘积 $BA$ 为 $A$ 与 $B$ 的复合

$$
\begin{gather}
(BA)(\mathbf{x})=B(A\mathbf{x}) \quad (\mathbf{x}\in X)
\end{gather}
$$

则 $BA \in L(X,Z)$。注意，一般来说 $BA\neq AB$，即使 $X=Y=Z$。

(c) 对 $A\in L(\mathbb{R}^{n},\mathbb{R}^{m})$，定义它的范数

$$
\begin{gather}
\lVert A \rVert =\sup_{\lvert \mathbf{x} \rvert \leq 1} \lvert A\mathbf{x} \rvert 
\end{gather}
$$

根据定义我们可得

$$
\begin{gather}
\lvert A\mathbf{x} \rvert \leq \lVert A \rVert \lvert \mathbf{x} \rvert  \quad (\mathbf{x}\in \mathbb{R}^{n})
\end{gather}
$$

此外，如果 $\lambda$ 满足 $\lvert A\mathbf{x} \rvert\leq\lambda\lvert \mathbf{x} \rvert$ 对任意 $\mathbf{x}\in \mathbb{R}^{n}$ 成立，那么 $\lVert A \rVert\leq\lambda$。

## Theorem 9.8

(a) 如果 $A\in L(\mathbb{R}^{n},\mathbb{R}^{m})$，则 $\lVert A \rVert<\infty$，且 $A$ 在 $\mathbb{R}^{n}$ 上一致连续。

(b) 如果 $A,B\in L(\mathbb{R}^{n},\mathbb{R}^{m})$ 且 $c \in \mathbb{R}$，则

$$
\begin{gather}
\lVert A+B \rVert \leq \lVert A \rVert +\lVert B \rVert , \quad \lVert cA \rVert =\lvert c \rvert \lVert A \rVert 
\end{gather}
$$

从而，通过将 $A,B$ 之间的距离定义为 $\lVert A-B \rVert$，可以使 $L(\mathbb{R}^{n},\mathbb{R}^{m})$ 成为一个度量空间。

(c) 如果 $A\in L(\mathbb{R}^{n},\mathbb{R}^{m}),B\in L(\mathbb{R}^{m},\mathbb{R}^{k})$，则

$$
\begin{gather}
\lVert BA \rVert \leq \lVert B \rVert \lVert A \rVert 
\end{gather}
$$

### Proof

(a) 取 $\mathbb{R}^{n}$ 上的标准基 $\{ \mathbf{e}_{1},\dots,\mathbf{e}_{n} \}$，设 $\mathbf{x}=\sum c_{j}\mathbf{e}_{j}$ 满足 $\lvert \mathbf{x} \rvert\leq 1$，则 $\lvert c_{j} \rvert\leq 1$，于是

$$
\begin{gather}
\lvert A\mathbf{x} \rvert =\left\lvert  \sum_{j=1}^{n} c_{j}A\mathbf{e}_{j}  \right\rvert \leq \sum_{j=1}^{n} \lvert c_{j} \rvert \lvert A\mathbf{e}_{j} \rvert \leq \sum_{j=1}^{n} \lvert A\mathbf{e}_{j} \rvert <\infty
\end{gather}
$$

取上确界即得

$$
\begin{gather}
\lVert A \rVert \leq \sum_{j=1}^{n} \lvert A\mathbf{e}_{j} \rvert <\infty
\end{gather}
$$

于是，对 $\mathbf{x},\mathbf{y}\in \mathbb{R}^{n}$ 有 $\lvert A\mathbf{x}-A\mathbf{y} \rvert\leq \lVert A \rVert\lvert \mathbf{x}-\mathbf{y} \rvert$，因此 $A$ 是 Lipschitz 连续的，从而一致连续。

(b) 我们有

$$
\begin{gather}
\lvert (A+B)\mathbf{x} \rvert \leq \lvert A\mathbf{x} \rvert +\lvert B\mathbf{x} \rvert \leq(\lVert A \rVert +\lVert B \rVert )\lvert \mathbf{x} \rvert 
\end{gather}
$$

取上确界即得

$$
\begin{gather}
\lVert A+B \rVert \leq \lVert A \rVert +\lVert B \rVert 
\end{gather}
$$

设 $c \in \mathbb{R}$，则

$$
\begin{gather}
\lvert cA\mathbf{x} \rvert =\lvert c \rvert \lvert A\mathbf{x} \rvert \leq \lvert c \rvert \lVert A \rVert \lvert \mathbf{x} \rvert 
\end{gather}
$$

从而

$$
\begin{gather}
\lVert cA \rVert \leq \lvert c \rvert \lVert A \rVert 
\end{gather}
$$

另一方面，

$$
\begin{gather}
\lvert c \rvert \lvert A\mathbf{x} \rvert =\lvert cA\mathbf{x} \rvert \leq \lVert cA \rVert \lvert \mathbf{x} \rvert 
\end{gather}
$$

从而

$$
\begin{gather}
\lvert c \rvert \lVert A \rVert \leq \lVert cA \rVert 
\end{gather}
$$

这就完成了 (b) 的证明。

(c) 我们有

$$
\begin{gather}
\lvert BA\mathbf{x} \rvert \leq \lVert B \rVert \lvert A\mathbf{x} \rvert \leq \lVert B \rVert \lVert A \rVert \lvert \mathbf{x} \rvert 
\end{gather}
$$

取上确界即证。

现在我们有了 $L(\mathbb{R}^{n},\mathbb{R}^{m})$ 上的度量，我们就可以讨论开集、连续性等拓扑概念。

## Theorem 9.9

设 $\Omega$ 为所有 $\mathbb{R}^{n}$ 上的可逆线性算子构成的集合。

(a) 如果 $A\in\Omega,B\in L(\mathbb{R}^{n})$，且

$$
\begin{gather}
\lVert B-A \rVert \lVert A^{-1} \rVert <1
\end{gather}
$$

则 $B\in\Omega$。

(b) $\Omega$ 是 $L(\mathbb{R}^{n})$ 中的一个开集，且映射 $A\mapsto A^{-1}$ 在 $\Omega$ 上连续。

### Proof

(a) 令 $\alpha=1 /\lVert A^{-1} \rVert,\beta=\lVert B-A \rVert$，则 $\beta<\alpha$。取 $\mathbf{x}\in \mathbb{R}^{n}$，则

$$
\begin{align}
\alpha\lvert \mathbf{x} \rvert &=\alpha\lvert A^{-1}A\mathbf{x} \rvert \leq \alpha \lVert A^{-1} \rVert \lvert A\mathbf{x} \rvert  \\
&=\lvert A\mathbf{x} \rvert \leq \lvert (A-B)\mathbf{x} \rvert +\lvert B\mathbf{x} \rvert \leq \beta\lvert \mathbf{x} \rvert +\lvert B\mathbf{x} \rvert 
\end{align}
$$

从而

$$
\begin{gather}
(\alpha-\beta)\lvert \mathbf{x} \rvert \leq \lvert B\mathbf{x} \rvert \tag{9.9.1}
\end{gather}
$$

由于 $\alpha-\beta>0$，因此当 $\mathbf{x}\neq \mathbf{0}$ 时 $B\mathbf{x}\neq 0$，即 $B$ 是单射，从而 [[#Theorem 9.6]] 表明 $B\in\Omega$。

以上论证对任意满足 $\lVert B-A \rVert<\alpha$ 的 $B$ 成立，因此 $\Omega$ 是一个开集。

(b) 我们要证 $B\to A$ 时 $B^{-1}\to A^{-1}$，即

$$
\begin{gather}
\lVert B^{-1}-A^{-1} \rVert \to 0 \quad (\lVert B-A \rVert \to 0)
\end{gather}
$$

利用公式

$$
\begin{gather}
\lVert B^{-1}-A^{-1} \rVert =\lVert B^{-1}(A-B)A^{-1} \rVert \leq \lVert B^{-1} \rVert \lVert A-B \rVert \lVert A^{-1} \rVert
\end{gather}
$$

下面我们需要求出 $\lVert B^{-1} \rVert$。

在 $(9.9.1)$ 中令 $\mathbf{x}=B^{-1}\mathbf{y}$，则有

$$
\begin{gather}
(\alpha-\beta)\lvert B^{-1}\mathbf{y} \rvert \leq \lvert \mathbf{y} \rvert 
\end{gather}
$$

从而 $\lVert B^{-1} \rVert\leq(\alpha-\beta)^{-1}$。于是我们有

$$
\begin{gather}
\lVert B^{-1}-A^{-1} \rVert \leq \frac{\beta}{\alpha(\alpha-\beta)}
\end{gather}
$$

当 $B\to A$ 即 $\beta\to 0$ 时，有 $\lVert B^{-1}-A^{-1} \rVert\to 0$，即证 $B^{-1}\to A^{-1}$。

## Definition 9.10 matrix 矩阵

设 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n} \}$ 和 $\{ \mathbf{y}_{1},\dots,\mathbf{y}_{m} \}$ 分别是向量空间 $X$ 和 $Y$ 的基，则每个线性变换 $A\in L(X,Y)$ 都唯一确定了 $a_{ij}$ 使得

$$
\begin{gather}
A\mathbf{x}_{j}=\sum_{i=1}^{m} a_{ij}\mathbf{y}_{i} \quad (j=1,\dots,n) \tag{9.10.1}
\end{gather}
$$

我们将这 $mn$ 个数排列成一个 $m\times n$ 的数组

$$
\begin{gather}
[A]=\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m 1} & a_{m 2} & \cdots & a_{mn}
\end{bmatrix}
\end{gather}
$$

称为 $A$ 在基 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n} \}$ 和 $\{ \mathbf{y}_{1},\dots,\mathbf{y}_{m} \}$ 下的矩阵。注意到 $A\mathbf{x}_{j}$ 的坐标出现在矩阵 $[A]$ 的第 $j$ 列，因此我们称 $A\mathbf{x}_{j}$ 为矩阵 $[A]$ 的列向量。在这一术语下，$A$ 的值域 $\operatorname{range}(A)$ 由 $[A]$ 的列向量张成。

如果 $\mathbf{x}=\sum c_{j}\mathbf{x}_{j}$，则 $A$ 的线性性表明

$$
\begin{gather}
A\mathbf{x}=\sum_{i=1}^{m} \left( \sum_{j=1}^{n} a_{ij}c_{j} \right)\mathbf{y}_{i} \tag{9.10.2}
\end{gather}
$$

换句话说，$A\mathbf{x}$ 的坐标等于 $\sum c_{j}\cdot\text{第}j\text{列}$。

假设已给定一个 $m\times n$ 实矩阵 $(a_{ij})$，我们可以定义一个线性变换 $A$ 使其满足 $(9.10.2)$。容易证明，$A\in L(X,Y)$，且它的矩阵正是 $(a_{ij})$。因此，存在一个从 $L(X,Y)$ 到 $m\times n$ 矩阵构成的向量空间的双射。不过，这样的双射不是唯一的：对于同一个线性变换 $A$，在不同的基下，它的矩阵可以是不同的。

设 $Z$ 是另一个向量空间，它的基是 $\{ \mathbf{z}_{1},\dots,\mathbf{z}_{p} \}$，再设 $A$ 由 $(9.10.1)$ 定义，

$$
\begin{gather}
B\mathbf{y}_{i}=\sum_{k=1}^{p} b_{ki}\mathbf{z}_{k}, \quad (BA)\mathbf{x}_{j}=\sum_{k=1}^{p} c_{kj}\mathbf{z}_{k}
\end{gather}
$$

则 $A\in L(X,Y),B\in L(Y,Z),BA\in L(X,Z)$。

由于

$$
\begin{align}
B(A\mathbf{x}_{j})&=B\left( \sum_{i=1}^{m} a_{ij}\mathbf{y}_{i} \right)=\sum_{i=1}^{m} a_{ij}B\mathbf{y}_{i} \\
&=\sum_{i=1}^{m} a_{ij} \sum_{k=1}^{p} b_{ki}\mathbf{z}_{k}=\sum_{k=1}^{p} \left( \sum_{i=1}^{m} b_{ki}a_{ij} \right)\mathbf{z}_{k}
\end{align}
$$

$\{ \mathbf{z}_{1},\dots,\mathbf{z}_{p} \}$ 的线性无关性表明

$$
\begin{gather}
c_{kj}=\sum_{i=1}^{m} b_{ki}a_{ij} \quad (1\leq k\leq p,1\leq j\leq n) \tag{9.10.3}
\end{gather}
$$

上式展示了如何从 $[A]$ 和 $[B]$ 得到 $BA$ 的矩阵 $[BA]$。如果我们定义矩阵的乘法 $[BA]=[B][A]$，那么 $(9.10.3)$ 就是通常的矩阵乘法公式（左矩阵的行点乘右矩阵的列）。

最后，设 $\{ \mathbf{x}_{1},\dots,\mathbf{x}_{n} \}$ 和 $\{ \mathbf{y}_{1},\dots,\mathbf{y}_{m} \}$ 分别是 $\mathbb{R}^{n}$ 和 $\mathbb{R}^{m}$ 的标准基，$A$ 由 $(9.10.2)$ 给出，则 Cauchy-Schwarz 不等式给出

$$
\begin{gather}
\lvert A\mathbf{x} \rvert ^{2}=\sum_{i=1}^{m} \left( \sum_{j=1}^{n} a_{ij}c_{j} \right)^{2}\leq \sum_{i=1}^{m} \left( \sum_{j=1}^{n} a_{ij}^{2}\sum_{j=1}^{n} c_{j}^{2} \right)=\sum_{i,j} a_{ij}^{2}\lvert \mathbf{x} \rvert ^{2}
\end{gather}
$$

因此

$$
\begin{gather}
\lVert A \rVert \leq \left( \sum_{i,j} a_{ij}^{2} \right)^{1/2}
\end{gather}
$$

在上式中将 $A$ 替换为 $B-A$，其中 $B,A\in L(\mathbb{R}^{n},\mathbb{R}^{m})$，我们可知，如果矩阵的项 $a_{ij}$ 是关于某个参数的连续函数，那么 $A$ 也是该参数的连续函数。精确的表述如下：

## Theorem 9.11

设 $S$ 是度量空间，$a_{11},\dots,a_{mn}$ 是 $S$ 上的实值连续函数，并且对任意 $p \in S$，令 $A_{p}$ 为从 $\mathbb{R}^{n}$ 到 $\mathbb{R}^{m}$ 的线性变换，其矩阵为 $[A_{p}]=(a_{ij}(p))$，则映射 $p\mapsto A_{p}$ 是从 $S$ 到 $L(\mathbb{R}^{n},\mathbb{R}^{m})$ 的连续函数。

# Differentiation 微分

前面我们提到，基于微商的微分定义无法直接推广到从 $\mathbb{R}^{n}$（或者 $\mathbb{R}^{n}$ 中的开集）到 $\mathbb{R}^{m}$ 的多变量函数。下面我们来给出 $n=1$ 时的一个等价定义，使得它能够自然地推广至 $n>1$ 的情形。

设 $f$ 是定义在 $(a,b)$ 上的实值函数，$x \in(a,b)$，则 $f$ 的导数定义为

$$
\begin{gather}
f'(x)=\lim_{ h \to 0 } \frac{f(x+h)-f(x)}{h}
\end{gather}
$$

如果以上极限存在。等价地，我们可以写成

$$
\begin{gather}
f(x+h)-f(x)=f'(x)h+r(h) \tag{1}
\end{gather}
$$

其中余项 $r(h)=o(h)$ 是一个高阶无穷小，意味着

$$
\begin{gather}
\lim_{ h \to 0 } \frac{r(h)}{h}=0
\end{gather}
$$

注意到，式 $(1)$ 将 $f$ 的变化量 $f(x+h)-f(x)$ 表示为了一个线性函数 $h\mapsto f'(x)h$ 与一个小量 $r(h)$ 的和。于是，我们可以将 $f$ 在 $x$ 处的导数视为一个从 $\mathbb{R}$ 到 $\mathbb{R}$ 的线性变换，而非一个实数。

以上的等同是合理的，因为任何线性变换 $\alpha\colon \mathbb{R}\to \mathbb{R}$ 都具有形式 $h\mapsto\alpha h$，相反，任何实数 $\alpha$ 都诱导了一个线性变换 $h\mapsto\alpha h$。正是这种 $\mathbb{R}$ 与 $L(\mathbb{R})$ 之间的一一对应启发了我们导数在多变量情形下的推广。

下面我们考虑函数 $\mathbf{f}\colon(a,b)\to \mathbb{R}^{m}$。此时，它在 $x \in(a,b)$ 的导数是一个向量 $\mathbf{y}\in \mathbb{R}^{m}$，满足

$$
\begin{gather}
\lim_{ h \to 0 } \left(  \frac{\mathbf{f}(x+h)-\mathbf{f}(x)}{h}-\mathbf{y}  \right) =\mathbf{0}
\end{gather}
$$

同样我们可以写成

$$
\begin{gather}
\mathbf{f}(x+h)-\mathbf{f}(x)=h\mathbf{y}+\mathbf{r}(h) \tag{2}
\end{gather}
$$

其中 $\lim_{ h \to 0 }\mathbf{r}(h) /h=\mathbf{0}$。等式 $(2)$ 右侧的主部同样是 $h$ 的一个线性函数。由于每个 $\mathbf{y}\in \mathbb{R}^{m}$ 都诱导了从 $\mathbb{R}$ 到 $\mathbb{R}^{m}$ 的线性变换 $h\mapsto h\mathbf{y}$，反之亦然，于是这种 $\mathbb{R}^{m}$ 与 $L(\mathbb{R},\mathbb{R}^{m})$ 之间的一一对应使得我们能够将 $\mathbf{f}'(x)$ 视为 $L(\mathbb{R},\mathbb{R}^{m})$ 中的一个元素。

因此，$\mathbf{f}$ 在 $x$ 处的导数是一个线性变换 $\mathbf{f}'(x)\in L(\mathbb{R},\mathbb{R}^{m})$，满足

$$
\begin{gather}
\lim_{ h \to 0 } \frac{\mathbf{f}(x+h)-\mathbf{f}(x)-\mathbf{f}'(x)h}{h}=\mathbf{0}
\end{gather}
$$

或者，等价地，

$$
\begin{gather}
\lim_{ h \to 0 } \frac{\lvert \mathbf{f}(x+h)-\mathbf{f}(x)-\mathbf{f}'(x)h \rvert }{\lvert h \rvert }=0
\end{gather}
$$

## Definition 9.12 Frechet differentiable

设 $E\subset \mathbb{R}^{n}$ 是开集，$\mathbf{f}\colon E\to \mathbb{R}^{m}$，$\mathbf{x}\in E$。如果存在线性变换 $A\in L(\mathbb{R}^{n},\mathbb{R}^{m})$ 使得

$$
\begin{gather}
\lim_{ \mathbf{h} \to \mathbf{0} } \frac{\lvert \mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})-A\mathbf{h} \rvert }{\lvert \mathbf{h} \rvert }=0 \tag{9.12.1}
\end{gather}
$$

则我们称 $\mathbf{f}$ 在 $\mathbf{x}$ 处 Frechet 可微，并定义它的 Frechet 导数为

$$
\begin{gather}
\mathbf{f}'(\mathbf{x})=A
\end{gather}
$$

如果 $\mathbf{f}$ 在任意 $\mathbf{x}\in E$ 上可微，则称 $\mathbf{f}$ 在 $E$ 上可微。

在 $(9.12.1)$ 中，显然 $\mathbf{h}\in \mathbb{R}^{n}$，于是当 $\lvert \mathbf{h} \rvert$ 足够小时，由于 $E$ 是开集，故 $\mathbf{x}+\mathbf{h}\in E$，从而 $\mathbf{f}(\mathbf{x}+\mathbf{h})$ 是有定义的，且 $\mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})\in \mathbb{R}^{m}$。又由于 $A\in L(\mathbb{R}^{n},\mathbb{R}^{m})$，因此 $A\mathbf{h}\in \mathbb{R}^{m}$，从而

$$
\begin{gather}
\mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})-A\mathbf{h}\in \mathbb{R}^{m}
\end{gather}
$$

故 $(9.12.1)$ 中分子上所用的是 $\mathbb{R}^{m}$ 上的范数，而分母上用的则是 $\mathbb{R}^{n}$ 上的范数。

## Theorem 9.13

定义 $E,\mathbf{f}$ 如 [[#Definition 9.12 Frechet differentiable]] 所示，且 $A_{1},A_{2}$ 均满足 $(9.12.1)$，则 $A_{1}=A_{2}$。

### Proof

令 $B=A_{1}-A_{2}$，则我们有

$$
\begin{gather}
\lvert B\mathbf{h} \rvert \leq \lvert \mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})-A_{1}\mathbf{h} \rvert +\lvert \mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})-A_{2}\mathbf{h} \rvert 
\end{gather}
$$

从而当 $\mathbf{h}\to \mathbf{0}$ 时有 $\lvert B\mathbf{h} \rvert /\lvert \mathbf{h} \rvert\to 0$。于是对任意固定的 $\mathbf{h}\neq \mathbf{0}$，我们有

$$
\begin{gather}
\lim_{ t \to 0 } \frac{\lvert B(t\mathbf{h}) \rvert }{\lvert t\mathbf{h} \rvert }=\frac{\lvert B\mathbf{h} \rvert }{\lvert \mathbf{h} \rvert }=0
\end{gather}
$$

故 $B\mathbf{h}=\mathbf{0}$ 对任意 $\mathbf{h}$ 成立，即 $B=0$。

## Remark 9.14

(a) 式 $(9.12.1)$ 也可以写成

$$
\begin{gather}
\mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})=\mathbf{f}'(\mathbf{x})\mathbf{h}+\mathbf{r}(\mathbf{h}) \tag{9.14.1}
\end{gather}
$$

其中 $\mathbf{r}(\mathbf{h})=o(\lvert \mathbf{h} \rvert)$ 满足

$$
\begin{gather}
\lim_{ \mathbf{h} \to \mathbf{0} } \frac{\lvert \mathbf{r}(\mathbf{h}) \rvert }{\lvert \mathbf{h} \rvert }=0
\end{gather}
$$

我们可以将其解读为：当 $\mathbf{x}\in E$ 且 $\mathbf{h}$ 接近 $\mathbf{0}$ 时，我们可以用线性主部 $\mathbf{f}'(\mathbf{x})\mathbf{h}$ 来近似 $\mathbf{f}$ 的变化量 $\mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})$。或者，等价地，$\mathbf{f}$ 在 $\mathbf{x}$ 的邻域内近似线性：

$$
\begin{gather}
\mathbf{f}(\mathbf{x}+\mathbf{h})=\mathbf{f}(\mathbf{x})+\mathbf{f}'(\mathbf{x})\mathbf{h}+o(\lvert \mathbf{h} \rvert )
\end{gather}
$$

(b) 假设 $E,\mathbf{f}$ 如 [[#Definition 9.12 Frechet differentiable]] 所示且 $\mathbf{f}$ 在 $E$ 上可微，则对任意 $\mathbf{x}\in E$，$\mathbf{f}'(\mathbf{x})$ 是从 $\mathbb{R}^{n}$ 到 $\mathbb{R}^{m}$ 的线性变换。而 $\mathbf{f}'$ 自身也是一个函数：它将 $\mathbf{x}\in E$ 映射到 $\mathbf{f}'(\mathbf{x})\in L(\mathbb{R}^{n},\mathbb{R}^{m})$。

(c) 在 $(9.14.1)$ 中令 $\mathbf{h}\to \mathbf{0}$，我们立即得到：如果 $\mathbf{f}$ 在 $\mathbf{x}$ 处可微，那么它在该点连续。

(d) 由 $(9.12.1)$ 或 $(9.14.1)$ 定义的导数通常称为 $\mathbf{f}$ 的微分或者全导数，以便与后续定义的偏导数做区分。

## Example 9.15

设 $A \in L(\mathbb{R}^{n},\mathbb{R}^{m})$，$\mathbf{x}\in \mathbb{R}^{n}$，则 $A$ 在 $\mathbf{x}$ 处的导数为

$$
\begin{gather}
A'(\mathbf{x})=A
\end{gather}
$$

注意上式两边都是 $\mathbb{R}^{n}$ 到 $\mathbb{R}^{m}$ 的线性变换，但左边有 $\mathbf{x}$ 而右边没有。我们可以将其与一维的情况做比较：线性函数 $f(x)=ax$ 的导数为 $f'(x)=a$。

## Theorem 9.16 (链式法则)

设 $E\subset \mathbb{R}^{n}$ 是开集，$\mathbf{f}\colon E\to \mathbb{R}^{m}$ 在 $\mathbf{x}_{0}\in E$ 可微，$\mathbf{g}$ 是从一个包含 $\mathbf{f}(E)$ 的开集到 $\mathbb{R}^{k}$ 的函数，在 $\mathbf{f}(\mathbf{x}_{0})$ 处可微。则定义为

$$
\begin{gather}
\mathbf{F}=\mathbf{g}\circ \mathbf{f}
\end{gather}
$$

的函数 $\mathbf{F}\colon E\to \mathbb{R}^{k}$ 在 $\mathbf{x}_{0}$ 处可微，且

$$
\begin{gather}
\mathbf{F}'(\mathbf{x}_{0})=\mathbf{g}'(\mathbf{f}(\mathbf{x}_{0}))\mathbf{f}'(\mathbf{x}_{0})
\end{gather}
$$

### Proof

取 $\mathbf{y}_{0}=\mathbf{f}(\mathbf{x}_{0})$，$A=\mathbf{f}'(\mathbf{x}_{0}),B=\mathbf{g}'(\mathbf{y}_{0})$，并令

$$
\begin{gather}
\mathbf{u}(\mathbf{h})=\mathbf{f}(\mathbf{x}_{0}+\mathbf{h})-\mathbf{f}(\mathbf{x}_{0})-A\mathbf{h} \\
\mathbf{v}(\mathbf{k})=\mathbf{g}(\mathbf{y}_{0}+\mathbf{k})-\mathbf{g}(\mathbf{y}_{0})-B\mathbf{k}
\end{gather}
$$

则

$$
\begin{gather}
\lvert \mathbf{u}(\mathbf{h}) \rvert =\varepsilon(\mathbf{h})\lvert \mathbf{h} \rvert ,\quad \lvert \mathbf{v}(\mathbf{k}) \rvert =\eta(\mathbf{k})\lvert \mathbf{k} \rvert 
\end{gather}
$$

其中当 $\mathbf{h}\to \mathbf{0}$ 和 $\mathbf{k}\to \mathbf{0}$ 时分别有 $\varepsilon(\mathbf{h})\to 0$ 和 $\eta(\mathbf{k})\to 0$。

给定 $\mathbf{h}$，令 $\mathbf{k}=\mathbf{f}(\mathbf{x}_{0}+\mathbf{h})-\mathbf{f}(\mathbf{x}_{0})$，则

$$
\begin{align}
\lvert \mathbf{k} \rvert =\lvert \mathbf{u}(\mathbf{h})+A\mathbf{h} \rvert \leq (\lVert A \rVert +\varepsilon(\mathbf{h}))\lvert \mathbf{h} \rvert 
\end{align}
$$

并且

$$
\begin{align}
\mathbf{F}(\mathbf{x}_{0}+\mathbf{h})-\mathbf{F}(\mathbf{x}_{0})-BA\mathbf{h} &= \mathbf{g}(\mathbf{y}_{0}+\mathbf{k})-\mathbf{g}(\mathbf{y}_{0})-BA\mathbf{h} \\
&=B(\mathbf{k}-A\mathbf{h})+\mathbf{v}(\mathbf{k}) \\
&\leq B\mathbf{u}(\mathbf{h})+\mathbf{v}(\mathbf{k})
\end{align}
$$

从而

$$
\begin{align}
\frac{\lvert \mathbf{F}(\mathbf{x}_{0}+\mathbf{h})-\mathbf{F}(\mathbf{x}_{0})-BA\mathbf{h} \rvert }{\lvert \mathbf{h} \rvert }\leq \lVert B \rVert \varepsilon(\mathbf{h})+(\lVert A \rVert +\varepsilon(\mathbf{h}))\eta(\mathbf{k})
\end{align}
$$

当 $\mathbf{h}\to \mathbf{0}$ 时，有 $\varepsilon(\mathbf{h})\to 0$，并且根据连续性，有 $\mathbf{k}\to 0$，从而 $\eta(\mathbf{k})\to 0$。即证 $\mathbf{F}'(\mathbf{x}_{0})=BA$。

## Definition 9.17 partial derivative 偏导数

考虑函数 $\mathbf{f}\colon E\to \mathbb{R}^{m}$，其中 $E\subset \mathbb{R}^{n}$ 是开集。令 $\{ \mathbf{e}_{1},\dots,\mathbf{e}_{n} \}$ 和 $\{ \mathbf{u}_{1},\dots,\mathbf{u}_{m} \}$ 分别是 $\mathbb{R}^{n}$ 和 $\mathbb{R}^{m}$ 的标准基，则 $\mathbf{f}$ 的各分量为实值函数 $f_{1},\dots,f_{m}$，满足

$$
\begin{gather}
\mathbf{f}(\mathbf{x})=\sum_{i=1}^{m} f_{i}(\mathbf{x})\mathbf{u}_{i} \quad (\mathbf{x}\in E)
\end{gather}
$$

或者，等价地，$f_{i}(\mathbf{x})=\mathbf{f}(\mathbf{x})\cdot \mathbf{u}_{i}$。

对 $\mathbf{x}\in E$，$1\leq i\leq m,1\leq j\leq n$，我们定义

$$
\begin{gather}
D_{j}f_{i}(\mathbf{x})=\lim_{ t \to 0 } \frac{f_{i}(\mathbf{x}+t\mathbf{e}_{j})-f_{i}(\mathbf{x})}{t}
\end{gather}
$$

称为 $f_{i}$ 对第 $j$ 个自变量的偏导数。将 $f_{i}$ 写成 $f_{i}(x_{1},\dots,x_{n})$，则偏导数 $D_{j}f_{i}$ 就是 $f_{i}$ 在保持其他变量固定时，对 $x_{j}$ 的导数，因此我们通常记

$$
\begin{gather}
D_{j}f_{i}=\frac{ \partial f_{i} }{ \partial x_{j} } 
\end{gather}
$$

对于多变量函数 $\mathbf{f}$，即使它是连续的，且所有偏导数都存在，我们也不能得到 $\mathbf{f}$ 可微的结论。这是因为在 $\mathbb{R}^{n}\ (n>1)$ 中，与一维的情况不同，$\mathbf{h}$ 可以从无穷多个方向趋于 $\mathbf{0}$，而 $\mathbf{h}$ 从各 $\mathbf{e}_{j}$ 的方向趋于 $\mathbf{0}$ 的极限（偏导数）存在不足以覆盖所有不可数无穷个方向。

然而，反向的蕴含的确是成立的：如果 $\mathbf{f}$ 在 $\mathbf{x}$ 处可微，那么 $\mathbf{f}$ 的所有偏导数在 $\mathbf{x}$ 处存在，并且它们完全确定了 $\mathbf{f}'(\mathbf{x})$。

## Theorem 9.18

设 $\mathbf{f}$ 是从开集 $E\subset \mathbb{R}^{n}$ 到 $\mathbb{R}^{m}$ 的函数，在 $\mathbf{x}\in E$ 可微，则偏导数 $D_{j}f_{i}$ 存在，并且

$$
\begin{gather}
\mathbf{f}'(\mathbf{x})\mathbf{e}_{j}=\sum_{i=1}^{m} D_{j}f_{i}(\mathbf{x})\mathbf{u}_{i}
\end{gather}
$$

### Proof

由 $\mathbf{f}$ 的可微性有

$$
\begin{gather}
\mathbf{f}(\mathbf{x}+t\mathbf{e}_{j})-\mathbf{f}(\mathbf{x})=\mathbf{f}'(\mathbf{x}) t\mathbf{e}_{j}+\mathbf{r}(t\mathbf{e}_{j})
\end{gather}
$$

其中 $\lim_{ t \to 0 }\lvert \mathbf{r}(t\mathbf{e}_{j}) \rvert /t=0$。从而

$$
\begin{gather}
\lim_{ t \to 0 } \frac{\mathbf{f}(\mathbf{x}+t\mathbf{e}_{j})-\mathbf{f}(\mathbf{x})}{t}=\mathbf{f}'(\mathbf{x})\mathbf{e}_{j}
\end{gather}
$$

将 $\mathbf{f}$ 表示为分量形式，则

$$
\begin{gather}
\lim_{ t \to 0 } \sum_{i=1}^{m} \frac{f_{i}(\mathbf{x}+t\mathbf{e}_{j})-f_{i}(\mathbf{x})}{t}\mathbf{u}_{i}=\mathbf{f}'(\mathbf{x})\mathbf{e}_{j}
\end{gather}
$$

根据 [[4 Continuity#Theorem 4.13]] 可知求和中的每个分量的极限都存在，从而根据偏导数的定义即证。

现在我们令 $[\mathbf{f}'(\mathbf{x})]$ 为 $\mathbf{f}'(\mathbf{x})$ 相对于标准基的矩阵，则 [[#Theorem 9.18]] 表明，矩阵 $[\mathbf{f}'(\mathbf{x})]$ 的第 $i$ 行第 $j$ 列的元素就是 $D_{j}f_{i}(\mathbf{x})$，从而

$$
\begin{gather}
[\mathbf{f}'(\mathbf{x})]=\begin{bmatrix}
D_{1}f_{1}(\mathbf{x}) & \cdots & D_{n}f_{1}(\mathbf{x}) \\
\vdots & \ddots & \vdots \\
D_{1}f_{m}(\mathbf{x}) & \cdots & D_{n}f_{m}(\mathbf{x})
\end{bmatrix}
\end{gather}
$$

于是，设 $\mathbf{h}=\sum h_{j}\mathbf{e}_{j}$，则

$$
\begin{gather}
\mathbf{f}'(\mathbf{x})\mathbf{h}=\sum_{i=1}^{m} \left( \sum_{j=1}^{n} h_{j} D_{j}f_{i}(\mathbf{x}) \right) \mathbf{u}_{i}
\end{gather}
$$

## Example 9.19

设 $\gamma$ 是一个从 $(a,b)$ 到开集 $E\subset \mathbb{R}^{n}$ 的可微映射，$f$ 是定义在 $E$ 上的可微实值函数，定义

$$
\begin{gather}
g(t)=f(\gamma(t)) \quad (a<t<b)
\end{gather}
$$

则链式法则给出

$$
\begin{gather}
g'(t)=f'(\gamma(t))\gamma'(t)
\end{gather}
$$

由于 $\gamma'(t)\in L(\mathbb{R},\mathbb{R}^{n})$，$f'(\gamma(t))\in L(\mathbb{R}^{n},\mathbb{R})$，因此上式定义了 $g'(t)$ 作为从 $\mathbb{R}$ 到 $\mathbb{R}$ 的一个线性算子，换言之，一个实数。这与 $g$ 是一个从 $(a,b)$ 到 $\mathbb{R}$ 的函数一致。

取 $\mathbb{R}^{n}$ 上的标准基 $\{ \mathbf{e}_{1},\dots,\mathbf{e}_{n} \}$，则 $[\gamma'(t)]$ 就是一个 $n\times 1$ 的矩阵（列向量），其在第 $i$ 行的元素为 $\gamma_{i}'(t)$。类似地，对 $\mathbf{x}\in E$，$[f'(\mathbf{x})]$ 是一个 $1\times n$ 的矩阵（行向量），其在第 $j$ 列的元素为 $D_{j}f(\mathbf{x})$。于是 $[g'(t)]$ 就是一个 $1\times 1$ 的矩阵（实数）

$$
\begin{gather}
g'(t)=\sum_{i=1}^{n} D_{i}f(\gamma(t))\gamma_{i}'(t) \tag{9.19.1}
\end{gather}
$$

这是链式法则的一个常用推论。一种等价形式如下所示。

对任意 $\mathbf{x}\in E$，我们定义 $f$ 在 $\mathbf{x}$ 处的梯度（gradient）为

$$
\begin{gather}
\nabla f(\mathbf{x})=\sum_{i=1}^{n} D_{i}f(\mathbf{x})\mathbf{e}_{i}
\end{gather}
$$

由于

$$
\begin{gather}
\gamma'(t)=\sum_{i=1}^{n} \gamma_{i}'(t)\mathbf{e}_{i}
\end{gather}
$$

因此我们可以将 $(9.19.1)$ 写成

$$
\begin{gather}
g'(t)=\nabla f(\gamma(t))\cdot \gamma'(t) \tag{9.19.2}
\end{gather}
$$

即 $\nabla f(\gamma(t))$ 与 $\gamma'(t)$ 的点积。

现在固定 $\mathbf{x}\in E$，取单位向量 $\mathbf{u}\in \mathbb{R}^{n}$，并定义

$$
\begin{gather}
\gamma(t)=\mathbf{x}+t\mathbf{u} \quad (-\infty<t<\infty)
\end{gather}
$$

则 $\gamma$ 的像就是空间中经过 $\mathbf{x}$ 且与 $\mathbf{u}$ 平行的一条直线。我们有 $\gamma'(t)=\mathbf{u}$，因此 $(9.19.2)$ 给出

$$
\begin{gather}
g'(0)=\nabla f(\mathbf{x})\cdot \mathbf{u}
\end{gather}
$$

另一方面，我们有

$$
\begin{gather}
g(t)-g(0)=f(\mathbf{x}+t\mathbf{u})-f(\mathbf{x})
\end{gather}
$$

从而

$$
\begin{gather}
\lim_{ t \to 0 } \frac{f(\mathbf{x}+t\mathbf{u})-f(\mathbf{x})}{t}=\nabla f(\mathbf{x})\cdot \mathbf{u}
\end{gather}
$$

左边的极限称为 $f$ 在 $\mathbf{x}$ 处关于方向 $\mathbf{u}$ 的方向导数，记作 $D_{\mathbf{u}}f(\mathbf{x})$。从上式可知，当 $f,\mathbf{x}$ 固定时，$D_{\mathbf{u}}f(\mathbf{x})$ 在 $\mathbf{u}$ 与 $\nabla f(\mathbf{x})$ 同向时达到最大值。换句话说，梯度向量是函数值上升/下降最快的方向。

如果 $\mathbf{u}=\sum u_{i}\mathbf{e}_{i}$，则我们将方向导数写成坐标形式有

$$
\begin{gather}
D_{\mathbf{u}}f(\mathbf{x})=\sum_{i=1}^{n} D_{i}f(\mathbf{x})u_{i}
\end{gather}
$$

## Theorem 9.20

设 $E\subset \mathbb{R}^{n}$ 是一个开凸集，$\mathbf{f}\colon E\to \mathbb{R}^{m}$ 在 $E$ 上可微，且存在 $M<\infty$ 使得

$$
\begin{gather}
\lVert \mathbf{f}'(\mathbf{x}) \rVert \leq M \quad (\mathbf{x}\in E)
\end{gather}
$$

则对任意 $\mathbf{a},\mathbf{b}\in E$ 有

$$
\begin{gather}
\lvert \mathbf{f}(\mathbf{b})-\mathbf{f}(\mathbf{a}) \rvert \leq M\lvert \mathbf{b}-\mathbf{a} \rvert 
\end{gather}
$$

### Proof

取 $\mathbf{a},\mathbf{b}\in E$，定义

$$
\begin{gather}
\gamma(t)=(1-t)\mathbf{a}+t\mathbf{b} \quad (-\infty<t<\infty)
\end{gather}
$$

则 $\gamma$ 的像是经过 $\mathbf{a},\mathbf{b}$ 两点的直线。由于 $E$ 是凸的，因此对于 $0\leq t\leq 1$ 有 $\gamma(t)\in E$，因此我们可以定义

$$
\begin{gather}
\mathbf{g}(t)=\mathbf{f}(\gamma(t)) \quad (0\leq t\leq 1)
\end{gather}
$$

其满足

$$
\begin{gather}
\mathbf{g}'(t)=\mathbf{f}'(\gamma(t))\gamma'(t)=\mathbf{f}'(\gamma(t))(\mathbf{b}-\mathbf{a})
\end{gather}
$$

因此

$$
\begin{gather}
\lvert \mathbf{g}'(t) \rvert \leq \lVert \mathbf{f}'(\gamma(t)) \rVert \lvert \mathbf{b}-\mathbf{a} \rvert \leq M\lvert \mathbf{b}-\mathbf{a} \rvert 
\end{gather}
$$

对 $0\leq t\leq 1$ 成立。于是，根据 [[5 Differentiation#Theorem 5.21]]，有

$$
\begin{gather}
\lvert \mathbf{g}(1)-\mathbf{g}(0) \rvert =\lvert \mathbf{f}(\mathbf{b})-\mathbf{f}(\mathbf{a}) \rvert \leq M\lvert \mathbf{b}-\mathbf{a} \rvert 
\end{gather}
$$

## Corollary 9.21

如果进一步，对任意 $\mathbf{x}\in E$ 有 $\mathbf{f}'(\mathbf{x})=0$，那么 $\mathbf{f}$ 是常值函数。

### Proof

此时在 [[#Theorem 9.20]] 中可以取 $M=0$，从而对任意 $\mathbf{a},\mathbf{b}\in E$ 有 $\mathbf{f}(\mathbf{b})=\mathbf{f}(\mathbf{a})$。

## Definition 9.22 continuously differentiable 连续可微的

从开集 $E\subset \mathbb{R}^{n}$ 到 $\mathbb{R}^{m}$ 的可微函数 $\mathbf{f}$ 称为是连续可微的，如果 $\mathbf{f}'$ 作为从 $E$ 到 $L(\mathbb{R}^{n},\mathbb{R}^{m})$ 的函数是连续的。

具体来说，称 $\mathbf{f}$ 是连续可微的，如果对任意 $\mathbf{x}\in E$ 和 $\varepsilon>0$，存在 $\delta>0$ 使得对于 $\mathbf{y}\in E$ 有

$$
\begin{gather}
\lvert \mathbf{x}-\mathbf{y} \rvert <\delta \implies \lVert \mathbf{f}'(\mathbf{x})-\mathbf{f}'(\mathbf{y}) \rVert <\varepsilon
\end{gather}
$$

此时我们也说 $\mathbf{f}$ 是一个 $C^{1}$ 连续函数，或者 $\mathbf{f}\in C^{1}(E)$。

## Theorem 9.23

设 $E\subset \mathbb{R}^{n}$ 是开集，$\mathbf{f}\colon E\to \mathbb{R}^{m}$，则 $\mathbf{f}\in C^{1}(E)$ 当且仅当所有偏导数 $D_{j}f_{i}$ 在 $E$ 上存在且连续。

### Proof

首先设 $\mathbf{f}\in C^{1}(E)$，根据

$$
\begin{gather}
D_{j}f_{i}(\mathbf{x})=\mathbf{f}'(\mathbf{x})\mathbf{e}_{j}\cdot \mathbf{u}_{i}
\end{gather}
$$

我们有

$$
\begin{gather}
D_{j}f_{i}(\mathbf{y})-D_{j}f_{i}(\mathbf{x})=(\mathbf{f}'(\mathbf{y})-\mathbf{f}'(\mathbf{x}))\mathbf{e}_{j}\cdot \mathbf{u}_{i}
\end{gather}
$$

从而

$$
\begin{align}
\lvert D_{j}f_{i}(\mathbf{y})-D_{j}f_{i}(\mathbf{x}) \rvert &\leq \lvert (\mathbf{f}'(\mathbf{y})-\mathbf{f}'(\mathbf{x}))\mathbf{e}_{j} \rvert  \\
&\leq \lVert \mathbf{f}'(\mathbf{y})-\mathbf{f}'(\mathbf{x}) \rVert 
\end{align}
$$

即证 $D_{j}f_{i}$ 在 $E$ 上连续。

下面假设所有偏导数存在且连续。首先我们证明 $m=1$ 的情况。

固定 $\mathbf{x}\in E$ 和 $\varepsilon>0$，由于 $E$ 是开集，存在开球 $S=B(\mathbf{x},r)\subset E$。$D_{j}f$ 的连续性表明我们可以选取 $r$ 使得

$$
\begin{gather}
\lvert D_{j}f(\mathbf{y})-D_{j}f(\mathbf{x}) \rvert <\frac{\varepsilon}{n} \quad (\mathbf{y}\in S,1\leq j\leq n)
\end{gather}
$$

设 $\mathbf{h}=\sum h_{j}\mathbf{e}_{j}$，$\lvert \mathbf{h} \rvert<r$，取 $\mathbf{v}_{0}=\mathbf{0}$，$\mathbf{v}_{k}=h_{1}\mathbf{e}_{1}+\dots+h_{k}\mathbf{e}_{k}$，则

$$
\begin{gather}
f(\mathbf{x}+\mathbf{h})-f(\mathbf{x})=\sum_{j=1}^{n} (f(\mathbf{x}+\mathbf{v}_{j})-f(\mathbf{x}+\mathbf{v}_{j-1}))
\end{gather}
$$

由于 $\lvert \mathbf{v}_{k} \rvert<r$，且 $S$ 是凸集，因此连接 $\mathbf{x}+\mathbf{v}_{j-1}$ 与 $\mathbf{x}+\mathbf{v}_{j}$ 的线段包含于 $S$ 中。又由于 $\mathbf{v}_{j}=\mathbf{v}_{j-1}+h_{j}\mathbf{e}_{j}$，对函数

$$
\begin{gather}
t\mapsto f(\mathbf{x}+\mathbf{v}_{j-1}+th_{j}\mathbf{e}_{j}) \quad (0\leq t\leq 1)
\end{gather}
$$

应用中值定理，则存在 $\theta_{j}\in(0,1)$ 使得

$$
\begin{gather}
f(\mathbf{x}+\mathbf{v}_{j})-f(\mathbf{x}+\mathbf{v}_{j-1})=h_{j}D_{j}f(\mathbf{x}+\mathbf{v}_{j-1}+\theta_{j}h_{j}\mathbf{e}_{j})
\end{gather}
$$

后者与 $h_{j}D_{j}f(\mathbf{x})$ 的距离小于等于 $\lvert h_{j} \rvert\varepsilon /n$，因此

$$
\begin{align}
\left\lvert  f(\mathbf{x}+\mathbf{h})-f(\mathbf{x})-\sum_{j=1}^{n} h_{j}D_{j}f(\mathbf{x})  \right\rvert \leq \frac{1}{n} \sum_{j=1}^{n} \lvert h_{j} \rvert \varepsilon\leq \lvert \mathbf{h} \rvert \varepsilon
\end{align}
$$

其中最后一个不等式来源于 Cauchy-Schwarz 不等式

$$
\begin{align}
\left( \sum \lvert h_{j} \rvert  \right)^{2}\leq \left( \sum \lvert h_{j} \rvert ^{2} \right)\left( \sum 1^{2} \right)=n \lvert \mathbf{h} \rvert ^{2}
\end{align}
$$

这就是说，$f$ 在 $\mathbf{x}$ 处可微，其导数 $f'(\mathbf{x})$ 将 $\mathbf{h}=\sum h_{j}\mathbf{e}_{j}$ 映射到 $\sum h_{j}D_{j}f(\mathbf{x})$。因此，$[f'(\mathbf{x})]$ 是一个行向量 $[D_{1}f(\mathbf{x}),\dots,D_{n}f(\mathbf{x})]$。又因为各 $D_{j}f$ 是连续函数，故由 [[#Theorem 9.11]] 知 $f'$ 是连续函数。

现在考虑 $m>1$ 的情况。通过对 $\mathbf{f}$ 的各分量应用上面的论证，得到 $f_{i}$ 在 $\mathbf{x}$ 处可微，且 $[f_{i}'(\mathbf{x})]=[D_{1}f_{i}(\mathbf{x}),\dots,D_{n}f_{i}(\mathbf{x})]$。令 $A$ 为 $m\times n$ 矩阵 $(D_{j}f_{i}(\mathbf{x}))$ 所对应的线性变换，根据

$$
\begin{gather}
\lvert \mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})-A\mathbf{h} \rvert ^{2}=\sum_{i=1}^{m} \left\lvert  f_{i}(\mathbf{x}+\mathbf{h})-f_{i}(\mathbf{x})-\sum_{j=1}^{n} h_{j}D_{j}f_{i}(\mathbf{x})  \right\rvert ^{2}
\end{gather}
$$

即证 $\mathbf{f}$ 在 $\mathbf{x}$ 处可微，并且 $\mathbf{f}'(\mathbf{x})=A$，从而由 [[#Theorem 9.11]] 立即得到 $\mathbf{f}'$ 连续。

# The Contraction Principle 压缩映射原理

## Definition 9.24 contraction 压缩映射

设 $X$ 是度量空间，其上的度量为 $d$。如果 $\varphi\colon X\to X$ 满足性质：存在 $c<1$ 使得对任意 $x,y \in X$ 有

$$
\begin{gather}
d(\varphi(x),\varphi(y))\leq cd(x,y)
\end{gather}
$$

则称 $\varphi$ 是 $X$ 上的一个压缩映射。

## Theorem 9.25 (压缩映射原理)

如果 $X$ 是一个完备度量空间，$\varphi$ 是 $X$ 上的压缩映射，则存在唯一的 $x \in X$ 使得 $\varphi(x)=x$。

换句话说，$\varphi$ 有唯一的不动点。唯一性是显然的：设 $x,y$ 是不动点，则

$$
\begin{gather}
d(\varphi(x),\varphi(y))=d(x,y)\leq cd(x,y)
\end{gather}
$$

上式仅在 $d(x,y)=0$，即 $x=y$ 时成立。

不动点的存在性是以上定理的主要部分，而下面的证明给出了一种构造性的方法来求出不动点。

### Proof

任取 $x_{0}\in X$，定义序列 $(x_{n})$ 满足

$$
\begin{gather}
x_{n+1}=\varphi(x_{n})
\end{gather}
$$

令 $c<1$ 为 $\varphi$ 的压缩系数，则对于 $n\geq 1$ 有

$$
\begin{gather}
d(x_{n+1},x_{n})=d(\varphi(x_{n}),\varphi(x_{n-1}))\leq cd(x_{n},x_{n-1})\leq \dots\leq c^{n}d(x_{1},x_{0})
\end{gather}
$$

于是当 $m>n$ 时，

$$
\begin{align}
d(x_{n},x_{m})&\leq \sum_{k=n}^{m-1} d(x_{k},x_{k+1}) \\
&\leq \sum_{k=n}^{m-1} c^{k}d(x_{0},x_{1}) \\
&\leq \frac{c^{n}}{1-c} d(x_{0},x_{1})
\end{align}
$$

当 $n\to \infty$ 时，有 $d(x_{n},x_{m})\to 0$，因此 $(x_{n})$ 是 Cauchy 序列，由 $X$ 的完备性知存在 $x=\lim_{ n \to \infty }x_{n}$。

由于 $\varphi$ 是压缩映射，因此 $\varphi$ 是 Lipschitz 连续的，从而

$$
\begin{gather}
\varphi(x)=\lim_{ n \to \infty } \varphi(x_{n})=\lim_{ n \to \infty } x_{n+1}=x
\end{gather}
$$

这就完成了证明。

# The Inverse Function Theorem 反函数定理

简单来说，反函数定理表明，一个连续可微的函数 $\mathbf{f}$ 在任意 $\mathbf{f}'(\mathbf{x})$ 可逆的点 $\mathbf{x}$ 的邻域中可逆（单射）。

## Theorem 9.26 (反函数定理)

设 $\mathbf{f}$ 是从开集 $E\subset \mathbb{R}^{n}$ 到 $\mathbb{R}^{n}$ 的 $C^{1}$ 函数，有 $\mathbf{a}\in E$ 使得 $\mathbf{f}'(\mathbf{a})$ 可逆，且 $\mathbf{b}=\mathbf{f}(\mathbf{a})$，则

(a) 存在开集 $U\subset E,V\subset \mathbb{R}^{n}$ 使得 $\mathbf{a}\in U,\mathbf{b}\in V$，且 $\mathbf{f}\colon U\to V$ 是双射。

(b) 设 $\mathbf{g}\colon V\to U$ 是 $\mathbf{f}$ 的反函数，定义为

$$
\begin{gather}
\mathbf{g}(\mathbf{f}(\mathbf{x}))=\mathbf{x} \quad (\mathbf{x}\in U)
\end{gather}
$$

则 $\mathbf{g}\in C^{1}(V)$。

将 $\mathbf{y}=\mathbf{f}(\mathbf{x})$ 写成分量形式，我们有如下的等价表述：由 $n$ 个方程

$$
\begin{gather}
y_{i}=f_{i}(x_{1},\dots,x_{n}) \quad (1\leq i\leq n)
\end{gather}
$$

组成的方程组在 $\mathbf{a}$ 和 $\mathbf{b}$ 的足够小邻域内可以解出 $x_{1},\dots,x_{n}$，这些解是关于 $y_{1},\dots,y_{n}$ 的连续可微函数。

### Proof

(a) 取 $A=\mathbf{f}'(\mathbf{a})$ 和 $\lambda$ 使得

$$
\begin{gather}
2\lambda \lVert A^{-1} \rVert =1
\end{gather}
$$

由于 $\mathbf{f}'$ 在 $\mathbf{a}$ 处连续，故存在以 $\mathbf{a}$ 为中心的开球 $U\subset E$ 使得

$$
\begin{gather}
\lVert \mathbf{f}'(\mathbf{x})-A \rVert <\lambda \quad (\mathbf{x}\in U)
\end{gather}
$$

我们将每个 $\mathbf{y}\in \mathbb{R}^{n}$ 关联到函数

$$
\begin{gather}
\varphi(\mathbf{x})=\mathbf{x}+A^{-1}(\mathbf{y}-\mathbf{f}(\mathbf{x})) \quad (\mathbf{x}\in E)
\end{gather}
$$

则 $\mathbf{f}(\mathbf{x})=\mathbf{y}$ 当且仅当 $\mathbf{x}$ 是 $\varphi$ 的不动点。

由于 $\varphi'(\mathbf{x})=I-A^{-1}\mathbf{f}'(\mathbf{x})=A^{-1}(A-\mathbf{f}'(\mathbf{x}))$，因此我们有

$$
\begin{gather}
\lVert \varphi'(\mathbf{x}) \rVert < \frac{1}{2} \quad (\mathbf{x}\in U)
\end{gather}
$$

从而由 [[#Theorem 9.20]]，对任意 $\mathbf{x}_{1},\mathbf{x}_{2}\in U$ 有

$$
\begin{gather}
\lvert \varphi(\mathbf{x}_{1})-\varphi(\mathbf{x}_{2}) \rvert \leq \frac{1}{2} \lvert \mathbf{x}_{1}-\mathbf{x}_{2} \rvert 
\end{gather}
$$

换句话说，$\varphi$ 是一个压缩映射。因此，$\varphi$ 在 $U$ 上至多有一个不动点，即最多有一个 $\mathbf{x}\in U$ 使得 $\mathbf{f}(\mathbf{x})=\mathbf{y}$。（但这样的 $\mathbf{x}$ 完全有可能不存在。）

于是，$\mathbf{f}$ 在 $U$ 上是单射的。

取 $V=\mathbf{f}(U)$，则 $\mathbf{f}\colon U\to V$ 是双射。设 $\mathbf{y}_{0}\in V$，则存在 $\mathbf{x}_{0}\in U$ 使得 $\mathbf{y}_{0}=\mathbf{f}(\mathbf{x}_{0})$。取一个开球 $B=B(\mathbf{x}_{0},r)$ 使得 $\overline{B}\subset U$，我们要证

$$
\begin{gather}
\lvert \mathbf{y}-\mathbf{y}_{0} \rvert <\lambda r \implies \mathbf{y} \in V
\end{gather}
$$

即 $B(\mathbf{y}_{0},\lambda r)\subset V$，换句话说，$V$ 是开的。

设 $\lvert \mathbf{y}-\mathbf{y}_{0} \rvert<\lambda r$，则我们有

$$
\begin{gather}
\lvert \varphi(\mathbf{x}_{0})-\mathbf{x}_{0} \rvert =\lvert A^{-1}(\mathbf{y}-\mathbf{f}(\mathbf{x}_{0})) \rvert < \lVert A^{-1} \rVert \lambda r=\frac{r}{2}
\end{gather}
$$

如果 $\mathbf{x}\in \overline{B}$，则

$$
\begin{align}
\lvert \varphi(\mathbf{x})-\mathbf{x}_{0} \rvert &\leq \lvert \varphi(\mathbf{x})-\varphi(\mathbf{x}_{0}) \rvert +\lvert \varphi(\mathbf{x}_{0})-\mathbf{x}_{0} \rvert  \\
&\leq \frac{1}{2}\lvert \mathbf{x}-\mathbf{x}_{0} \rvert +\frac{r}{2}\leq r
\end{align}
$$

即 $\varphi$ 是 $\overline{B}$ 上的压缩映射。由于 $\overline{B}$ 是完备度量空间 $\mathbb{R}^{n}$ 的闭子集，因此它也是完备的，从而由压缩映射原理知存在 $\mathbf{x}\in \overline{B}$ 使得 $\varphi(\mathbf{x})=\mathbf{x}$。对于这个 $\mathbf{x}$，有 $\mathbf{y}=\mathbf{f}(\mathbf{x})\in \mathbf{f}(\overline{B})\subset \mathbf{f}(U)=V$。即证 $V$ 是开集。

(b) 取 $\mathbf{y}\in V,\mathbf{y}+\mathbf{k}\in V$，则存在 $\mathbf{x}\in U,\mathbf{x}+\mathbf{h}\in U$ 使得 $\mathbf{y}=\mathbf{f}(\mathbf{x})$，$\mathbf{y}+\mathbf{k}=\mathbf{f}(\mathbf{x}+\mathbf{h})$。定义 $\varphi$ 如 (a) 中所示，则

$$
\begin{gather}
\varphi(\mathbf{x}+\mathbf{h})-\varphi(\mathbf{x})=\mathbf{h}+A^{-1}(\mathbf{f}(\mathbf{x})-\mathbf{f}(\mathbf{x}+\mathbf{h}))=\mathbf{h}-A^{-1}\mathbf{k}
\end{gather}
$$

由于 $\varphi$ 的压缩系数为 $1 /2$，故

$$
\begin{gather}
\lvert \mathbf{h}-A^{-1}\mathbf{k} \rvert < \frac{\lvert \mathbf{h} \rvert }{2}
\end{gather}
$$

因此 $\lvert A^{-1}\mathbf{k} \rvert>\lvert \mathbf{h} \rvert /2$，且

$$
\begin{gather}
\lvert \mathbf{h} \rvert \leq 2 \lVert A^{-1} \rVert \lvert \mathbf{k} \rvert =\frac{\lvert \mathbf{k} \rvert }{\lambda}
\end{gather}
$$

根据 (a)，$\lVert \mathbf{f}'(\mathbf{x})-A \rVert \lVert A^{-1} \rVert<1 /2$，因此由 [[#Theorem 9.9]] 知 $\mathbf{f}'(\mathbf{x})$ 可逆，设其逆元为 $T$。由于

$$
\begin{gather}
\mathbf{g}(\mathbf{y}+\mathbf{k})-\mathbf{g}(\mathbf{y})-T\mathbf{k}=\mathbf{h}-T\mathbf{k}=-T(\mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})-\mathbf{f}'(\mathbf{x})\mathbf{h})
\end{gather}
$$

故

$$
\begin{gather}
\frac{\lvert \mathbf{g}(\mathbf{y}+\mathbf{k})-\mathbf{g}(\mathbf{y})-T\mathbf{k} \rvert }{\lvert \mathbf{k} \rvert }\leq \frac{\lVert T \rVert \lvert \mathbf{f}(\mathbf{x}+\mathbf{h})-\mathbf{f}(\mathbf{x})-\mathbf{f}'(\mathbf{x})\mathbf{h} \rvert }{\lambda \lvert \mathbf{h} \rvert }
\end{gather}
$$

当 $\mathbf{k}\to \mathbf{0}$ 时，$\mathbf{h}\to \mathbf{0}$，因此上式右侧趋于 $0$。因此 $\mathbf{g}$ 在 $\mathbf{y}$ 处可微，且

$$
\begin{gather}
\mathbf{g}'(\mathbf{y})=T=\mathbf{f}'(\mathbf{x})^{-1}=\mathbf{f}'(\mathbf{g}(\mathbf{y}))^{-1} \quad (\mathbf{y}\in V)
\end{gather}
$$

最后，由于 $\mathbf{g}\colon V\to U$ 可微（因而连续），$\mathbf{f}'\colon U\to \Omega$ 连续，其中 $\Omega \subset L(\mathbb{R}^{n})$ 是可逆线性变换构成的集合，逆元映射 $A\mapsto A^{-1}$ 在 $\Omega$ 上连续，即证 $\mathbf{g}'$ 在 $V$ 上连续。

### Remark

在上面的证明中，性质 $\mathbf{f}\in C^{1}(E)$ 仅在最后一段，即 $\mathbf{g}\in C^{1}(V)$ 的证明中用到。所有之前的性质与证明，一直到 $\mathbf{g}'(\mathbf{y})$ 的存在性，都可以从假设：$\mathbf{f}'(\mathbf{x})$ 对任意 $\mathbf{x}\in E$ 存在，$\mathbf{f}'(\mathbf{a})$ 可逆，以及 $\mathbf{f}'$ 在 $\mathbf{a}$ 的连续性中导出。

以下是反函数定理 (a) 的直接推论。

## Theorem 9.27

如果 $\mathbf{f}$ 是从开集 $E\subset \mathbb{R}^{n}$ 到 $\mathbb{R}^{n}$ 的 $C^{1}$ 函数，且对任意 $\mathbf{x}\in E$ 有 $\mathbf{f}'(\mathbf{x})$ 可逆，则对任意开集 $W\subset E$，$\mathbf{f}(W)$ 是 $\mathbb{R}^{n}$ 中的开集。换言之，$\mathbf{f}\colon E\to \mathbb{R}^{n}$ 是一个开映射。

以上定理中的假设保证了 $\mathbf{f}$ 在任意点 $\mathbf{x}\in E$ 的邻域中是单射的，即 $\mathbf{f}$ 是局部单射的。然而，局部单射性无法推出全局单射性。

# The Implicit Function Theorem 隐函数定理

如果 $f$ 是平面上的一个连续可微函数，则对于方程 $f(x,y)=0$，我们可以在满足 $f(a,b)=0$ 且 $\frac{ \partial f }{ \partial y }\neq 0$ 的点 $(a,b)$ 的邻域中解出 $y$，作为 $x$ 的一个函数。类似地，如果 $\frac{ \partial f }{ \partial x }\neq 0$，那么我们可以在 $(a,b)$ 的邻域中解出 $x$ 作为 $y$ 的函数。一个简单例子是 $f(x,y)=x^{2}+y^{2}-1$，其在 $(1,0)$ 的任何邻域中都无法解出 $y$ 作为 $x$ 的函数，因为此处 $\frac{ \partial f }{ \partial y }=0$。

以上的结论是所谓“隐函数定理”的一个特例。它的证明极强地依赖于性质：连续可微函数在局部的行为与它的在此处的导数非常相似。因此，我们首先来证明线性函数的隐函数定理，然后推广到一般的连续可微函数。

设 $\mathbf{x}=(x_{1},\dots,x_{n})\in \mathbb{R}^{n}$，$\mathbf{y}=(y_{1},\dots,y_{m})\in \mathbb{R}^{m}$，我们记

$$
\begin{gather}
(\mathbf{x},\mathbf{y})=(x_{1},\dots,x_{n},y_{1},\dots,y_{m})\in \mathbb{R}^{n+m}
\end{gather}
$$

于是，任何 $A\in L(\mathbb{R}^{n+m},\mathbb{R}^{n})$ 都可以表示为

$$
\begin{gather}
A(\mathbf{h},\mathbf{k})=A_{x}\mathbf{h}+A_{y}\mathbf{k}
\end{gather}
$$

其中

$$
\begin{gather}
A_{x}\mathbf{h}=A(\mathbf{h},\mathbf{0}), \quad A_{y}\mathbf{k}=A(\mathbf{0},\mathbf{k}) \quad (\mathbf{h}\in \mathbb{R}^{n},\mathbf{k}\in \mathbb{R}^{m})
\end{gather}
$$

从而 $A_{x}\in L(\mathbb{R}^{n})$，$A_{y}\in L(\mathbb{R}^{m},\mathbb{R}^{n})$。

## Theorem 9.28

如果 $A\in L(\mathbb{R}^{n+m},\mathbb{R}^{n})$，且 $A_{x}$ 可逆，则对任意 $\mathbf{k}\in \mathbb{R}^{m}$，存在唯一的 $\mathbf{h}\in \mathbb{R}^{n}$ 使得 $A(\mathbf{h},\mathbf{k})=\mathbf{0}$。这个 $\mathbf{h}$ 可以通过下式进行计算：

$$
\begin{gather}
\mathbf{h}=-A_{x}^{-1}A_{y}\mathbf{k}
\end{gather}
$$

### Proof

$A(\mathbf{h},\mathbf{k})=\mathbf{0}$ 当且仅当

$$
\begin{gather}
A_{x}\mathbf{h}+A_{y}\mathbf{k}=\mathbf{0}
\end{gather}
$$

当 $A_{x}$ 可逆时，从上式中解出 $\mathbf{h}$ 即可。

### Motivation

以上定理的结论表明，方程 $A(\mathbf{h},\mathbf{k})=\mathbf{0}$ 在给定 $\mathbf{k}$ 时可以唯一地解出 $\mathbf{h}$，并且解 $\mathbf{h}$ 是 $\mathbf{k}$ 的一个线性函数。这实际上是线性代数中关于线性方程组的一个基本结论。

考虑我们上面定义的

$$
\begin{gather}
(\mathbf{x},\mathbf{y})=(x_{1},\dots,x_{n},y_{1},\dots,y_{m})
\end{gather}
$$

方程 $A(\mathbf{x},\mathbf{y})=\mathbf{0}$，根据 [[#Definition 9.10 matrix 矩阵]] 中线性变换与矩阵的一一对应性，就等价于线性方程组

$$
\begin{gather}
a_{11}x_{1}+\dots+a_{1n}x_{n}+b_{11}y_{1}+\dots+b_{1m}y_{m}=0 \\
\vdots \\
a_{n 1}x_{1}+\dots+a_{nn}x_{n}+b_{n 1}y_{1}+\dots+b_{nm}y_{m}=0
\end{gather}
$$

其中线性变换 $A_{x}$ 的矩阵就是 $(a_{ij})$，$A_{y}$ 的矩阵为 $(b_{ij})$。根据线性代数中的结论，如果 $A_{x}$ 可逆，即矩阵 $(a_{ij})$ 满秩，则我们可以通过消元法，将主元（pivot）$x_{1},\dots,x_{n}$ 解出，作为自由变量 $y_{1},\dots,y_{m}$ 的线性函数。换言之，对任意给定的 $y_{1},\dots,y_{m}$，有唯一确定的 $x_{1},\dots,x_{n}$ 满足方程组。

## Theorem 9.29 (隐函数定理)

设 $\mathbf{f}$ 是从开集 $E\subset \mathbb{R}^{n+m}$ 到 $\mathbb{R}^{n}$ 的 $C^{1}$ 函数，有 $(\mathbf{a},\mathbf{b})\in E$ 满足 $\mathbf{f}(\mathbf{a},\mathbf{b})=\mathbf{0}$。

令 $A=\mathbf{f}'(\mathbf{a},\mathbf{b})$，并假设 $A_{x}$ 可逆。则存在开集 $U\subset E$ 和 $W\subset \mathbb{R}^{n}$，使得 $(\mathbf{a},\mathbf{b})\in U$ 且 $\mathbf{b}\in W$，且满足以下性质：

对任意 $\mathbf{y}\in W$，存在唯一的 $\mathbf{x}$ 使得

$$
\begin{gather}
(\mathbf{x},\mathbf{y})\in U, \quad \mathbf{f}(\mathbf{x},\mathbf{y})=\mathbf{0}
\end{gather}
$$

定义 $\mathbf{g}(\mathbf{y})=\mathbf{x}$，则 $\mathbf{g}\colon W\to \mathbb{R}^{n}$ 是一个 $C^{1}$ 函数，$\mathbf{g}(\mathbf{b})=\mathbf{a}$，

$$
\begin{gather}
\mathbf{f}(\mathbf{g}(\mathbf{y}),\mathbf{y})=\mathbf{0} \quad (\mathbf{y}\in W)
\end{gather}
$$

并且

$$
\begin{gather}
\mathbf{g}'(\mathbf{b})=-A_{x}^{-1}A_{y}
\end{gather}
$$

我们说函数 $\mathbf{g}$ 是由方程 $\mathbf{f}(\mathbf{x},\mathbf{y})=\mathbf{0}$ 隐含地定义的，或称 $\mathbf{g}$ 是一个隐函数。

将以上定理写成分量形式，我们有等价表述：方程 $\mathbf{f}(\mathbf{x},\mathbf{y})=\mathbf{0}$ 是一个有 $n+m$ 个未知量和 $n$ 个方程构成的方程组

$$
\begin{gather}
f_{1}(x_{1},\dots,x_{n},y_{1},\dots,y_{m})=0 \\
\vdots \\
f_{n}(x_{1},\dots,x_{n},y_{1},\dots,y_{m})=0
\end{gather} \tag{9.29.1}
$$

$A_{x}$ 可逆的假设则等价于 $n\times n$ 矩阵

$$
\begin{gather}
\begin{bmatrix}
D_{1}f_{1}(\mathbf{a},\mathbf{b}) & \cdots & D_{n}f_{1}(\mathbf{a},\mathbf{b}) \\
\vdots & \ddots & \vdots \\
D_{1}f_{n}(\mathbf{a},\mathbf{b}) & \cdots & D_{n}f_{n}(\mathbf{a},\mathbf{b})
\end{bmatrix}
\end{gather}
$$

的可逆性，即它的列向量线性无关，或者它的行列式不等于零。定理假设 $\mathbf{x}=\mathbf{a},\mathbf{y}=\mathbf{b}$ 是方程组的一个解，而定理的结论是，对任意在 $\mathbf{b}$ 的邻域内的 $\mathbf{y}$，我们总是能够解出 $x_{1},\dots,x_{n}$，作为自由变量 $y_{1},\dots,y_{m}$ 的隐函数 $\mathbf{g}(\mathbf{y})$，并且它是连续可微的。这是定理的第一部分。

定理的第二部分讲述的是隐函数微分。要得到 $x_{1},\dots,x_{n}$ 作为 $\mathbf{y}$ 的函数在 $\mathbf{y}=\mathbf{b}$ 处的导数，我们可以对这 $n$ 个方程求关于 $y_{k}$ 的偏导数，利用链式法则我们就有

$$
\begin{gather}
\sum_{j=1}^{n} \frac{ \partial f_{i} }{ \partial x_{j} } (\mathbf{a},\mathbf{b}) \frac{ \partial g_{j} }{ \partial y_{k} } (\mathbf{b})+\frac{ \partial f_{i} }{ \partial y_{k} }(\mathbf{a},\mathbf{b})=0 \quad (1\leq i\leq n,1\leq k\leq m)
\end{gather}
$$

对每个 $k$，我们都有 $n$ 个线性方程构成的满秩方程组，其中未知量 $\frac{ \partial g_{j} }{ \partial y_{k} }$ 可以通过消元法解出。

### Proof

我们将使用反函数定理进行证明。因此我们定义

$$
\begin{gather}
\mathbf{F}(\mathbf{x},\mathbf{y})=(\mathbf{f}(\mathbf{x},\mathbf{y}),\mathbf{y}) \quad ((\mathbf{x},\mathbf{y})\in E)
\end{gather}
$$

则 $\mathbf{F}\colon E\to \mathbb{R}^{n+m}$ 是一个 $C^{1}$ 函数。我们断言 $\mathbf{F}'(\mathbf{a},\mathbf{b})$ 可逆，从而满足反函数定理的假设。

由于 $\mathbf{f}(\mathbf{a},\mathbf{b})=\mathbf{0}$，因此

$$
\begin{gather}
\mathbf{f}(\mathbf{a}+\mathbf{h},\mathbf{b}+\mathbf{k})=A(\mathbf{h},\mathbf{k})+\mathbf{r}(\mathbf{h},\mathbf{k})
\end{gather}
$$

其中 $A=\mathbf{f}'(\mathbf{a},\mathbf{b})$，$\mathbf{r}$ 是一个高阶无穷小。于是

$$
\begin{align}
\mathbf{F}(\mathbf{a}+\mathbf{h},\mathbf{b}+\mathbf{k})-\mathbf{F}(\mathbf{a},\mathbf{b})&= (\mathbf{f}(\mathbf{a}+\mathbf{h},\mathbf{b}+\mathbf{k}),\mathbf{k}) \\
&=(A(\mathbf{h},\mathbf{k}),\mathbf{k})+(\mathbf{r}(\mathbf{h},\mathbf{k}),\mathbf{0})
\end{align}
$$

由于 $(\mathbf{r}(\mathbf{h},\mathbf{k}),\mathbf{0})$ 也是高阶无穷小，因此 $\mathbf{F}'(\mathbf{a},\mathbf{b})$ 存在，其将 $(\mathbf{h},\mathbf{k})$ 映射到 $(A(\mathbf{h},\mathbf{k}),\mathbf{k})$。

如果 $(A(\mathbf{h},\mathbf{k}),\mathbf{k})=\mathbf{0}$，则 $A(\mathbf{h},\mathbf{k})=0,\mathbf{k}=\mathbf{0}$，即 $A(\mathbf{h},\mathbf{0})=A_{x}\mathbf{h}=\mathbf{0}$。$A_{x}$ 的可逆性表明 $\mathbf{h}=\mathbf{0}$，因而 $\mathbf{F}'(\mathbf{a},\mathbf{b})$ 是单射，从而由 [[#Theorem 9.6]] 知 $\mathbf{F}'(\mathbf{a},\mathbf{b})$ 可逆。

于是，我们对 $\mathbf{F}$ 应用反函数定理，从而存在开集 $U\subset E,V\subset \mathbb{R}^{n+m}$，使得 $(\mathbf{a},\mathbf{b})\in U,(\mathbf{0},\mathbf{b})\in V$，且 $\mathbf{F}\colon U\to V$ 是双射。

我们令 $W$ 为所有满足 $(\mathbf{0},\mathbf{y})\in V$ 的 $\mathbf{y}\in \mathbb{R}^{m}$ 构成的集合，显然 $W$ 是开集，且 $\mathbf{b}\in W$。

如果 $\mathbf{y}\in W$，则存在 $(\mathbf{x},\mathbf{y})\in U$ 使得 $\mathbf{F}(\mathbf{x},\mathbf{y})=(\mathbf{0},\mathbf{y})$，即 $\mathbf{f}(\mathbf{x},\mathbf{y})=\mathbf{0}$。如果另有 $\mathbf{x}'$ 使得 $(\mathbf{x}',\mathbf{y})\in U$ 且 $\mathbf{f}(\mathbf{x}',\mathbf{y})=\mathbf{0}$，则我们有

$$
\begin{gather}
\mathbf{F}(\mathbf{x}',\mathbf{y})=(\mathbf{f}(\mathbf{x}',\mathbf{y}),\mathbf{y})=(\mathbf{f}(\mathbf{x},\mathbf{y}),\mathbf{y})=\mathbf{F}(\mathbf{x},\mathbf{y})
\end{gather}
$$

由于 $\mathbf{F}$ 在 $U$ 上是单射的，因此 $\mathbf{x}'=\mathbf{x}$。这就完成了第一部分的证明。

对于第二部分，我们定义 $\mathbf{g}(\mathbf{y})=\mathbf{x}$，使得 $(\mathbf{x},\mathbf{y})\in U$ 且 $\mathbf{f}(\mathbf{x},\mathbf{y})=\mathbf{0}$。于是

$$
\begin{gather}
\mathbf{F}(\mathbf{g}(\mathbf{y}),\mathbf{y})=(\mathbf{0},\mathbf{y}) \quad (\mathbf{y}\in W)
\end{gather}
$$

取 $\mathbf{F}$ 的反函数 $\mathbf{G}\colon V\to U$，则

$$
\begin{gather}
(\mathbf{g}(\mathbf{y}),\mathbf{y})=\mathbf{G}(\mathbf{0},\mathbf{y}) \quad (\mathbf{y}\in W)
\end{gather}
$$

反函数定理给出 $\mathbf{G}\in C^{1}(V)$，因此我们有 $\mathbf{g}\in C^{1}(W)$。

最后，要计算 $\mathbf{g}'(\mathbf{b})$，我们记 $\Phi(\mathbf{y})=(\mathbf{g}(\mathbf{y}),\mathbf{y})$，则

$$
\begin{gather}
\Phi'(\mathbf{y})\mathbf{k}=(\mathbf{g}'(\mathbf{y})\mathbf{k},\mathbf{k}) \quad (\mathbf{y}\in W,\mathbf{k}\in \mathbb{R}^{m})
\end{gather}
$$

并且在 $W$ 上有 $\mathbf{f}(\Phi(\mathbf{y}))=\mathbf{f}(\mathbf{g}(\mathbf{y}),\mathbf{y})=\mathbf{0}$。应用链式法则可得

$$
\begin{gather}
\mathbf{f}'(\Phi(\mathbf{y}))\Phi'(\mathbf{y})=0
\end{gather}
$$

当 $\mathbf{y}=\mathbf{b}$ 时，有 $\Phi(\mathbf{b})=(\mathbf{a},\mathbf{b})$，因此 $\mathbf{f}'(\Phi(\mathbf{b}))=\mathbf{f}'(\mathbf{a},\mathbf{b})=A$，

$$
\begin{gather}
A\Phi'(\mathbf{b})=0
\end{gather}
$$

从而对任意 $\mathbf{k}\in \mathbb{R}^{m}$ 有

$$
\begin{gather}
A\Phi'(\mathbf{b})\mathbf{k}=A(\mathbf{g}'(\mathbf{b})\mathbf{k},\mathbf{k})=A_{x}\mathbf{g}'(\mathbf{b})\mathbf{k}+A_{y}\mathbf{k}=\mathbf{0}
\end{gather}
$$

即

$$
\begin{gather}
A_{x}\mathbf{g}'(\mathbf{b})+A_{y}=0
\end{gather}
$$

由 $A_{x}$ 的可逆性，从上式中解出 $\mathbf{g}'(\mathbf{b})$ 即证。

特别地，写出 $\mathbf{f}$ 与 $\mathbf{g}$ 的分量形式，则矩阵 $[A_{x}\mathbf{g}'(\mathbf{b})+A_{y}]$ 的 $(i,k)$ 元素为

$$
\begin{gather}
\sum_{j=1}^{n} D_{j}f_{i}(\mathbf{a},\mathbf{b})D_{k}g_{j}(\mathbf{b})+D_{n+k}f_{i}(\mathbf{a},\mathbf{b})=0
\end{gather}
$$

即

$$
\begin{gather}
\sum_{j=1}^{n} \frac{ \partial f_{i} }{ \partial x_{j} } (\mathbf{a},\mathbf{b}) \frac{ \partial g_{j} }{ \partial y_{k} } (\mathbf{b})+\frac{ \partial f_{i} }{ \partial y_{k} } (\mathbf{a},\mathbf{b})=0
\end{gather}
$$

# The Rank Theorem 秩定理

秩定理是隐函数定理的一个推广。同样地，它显示了连续可微函数在局部的行为与它在该点处的导数相似。

## Definition 9.30 null space 零空间，rank 秩

设 $X,Y$ 是向量空间，$A\in L(X,Y)$，我们定义 $A$ 的零空间或者核（kernel）为

$$
\begin{gather}
\ker A=\{ \mathbf{x}\in X : A\mathbf{x}=\mathbf{0} \}
\end{gather}
$$

显然 $\ker A$ 是 $X$ 的一个子空间。类似地，$A$ 的值域 $\operatorname{range}A$ 是 $Y$ 的一个子空间。我们定义 $A$ 的秩为 $\operatorname{rank}A=\dim \operatorname{range}A$。

根据 [[#Theorem 9.6]]，$L(\mathbb{R}^{n})$ 中的可逆元素正是那些秩为 $n$ 的线性变换。如果 $A\in L(X,Y)$ 且 $\operatorname{rank}A=0$，则线性代数中的秩-零化度定理保证了 $\ker A=X$，即对任意 $\mathbf{x}\in X$ 有 $A\mathbf{x}=\mathbf{0}$。

## Theorem 9.31 projection 投影

设 $X$ 是向量空间，称 $P\in L(X)$ 是一个 $X$ 上的投影，如果 $P^{2}=P$。

具体来说，对任意 $\mathbf{x}\in X$ 有 $P(P\mathbf{x})=P\mathbf{x}$。因此，$P$ 保持 $\operatorname{range}P$ 中的向量不变。以下是投影变换的一些基本性质：

(a) 如果 $P$ 是 $X$ 上的投影，那么任意 $\mathbf{x}\in X$ 都有唯一分解

$$
\begin{gather}
\mathbf{x}=\mathbf{x}_{1}+\mathbf{x}_{2}
\end{gather}
$$

其中 $\mathbf{x}_{1}\in \operatorname{range}P,\mathbf{x}_{2}\in \ker P$。

对于存在性，我们取 $\mathbf{x}_{1}=P\mathbf{x},\mathbf{x}_{2}=\mathbf{x}-\mathbf{x}_{1}$，则

$$
\begin{gather}
P\mathbf{x}_{2}=P\mathbf{x}-P\mathbf{x}_{1}=P\mathbf{x}-P^{2}\mathbf{x}=\mathbf{0}
\end{gather}
$$

对于唯一性，对等式 $\mathbf{x}=\mathbf{x}_{1}+\mathbf{x}_{2}$ 两边应用 $P$，则有 $P\mathbf{x}=P\mathbf{x}_{1}$。由于 $\mathbf{x}_{1}\in \operatorname{range}P$，因此 $P\mathbf{x}_{1}=\mathbf{x}_{1}$，故 $\mathbf{x}_{1}=P\mathbf{x}$ 唯一。从而 $\mathbf{x}_{2}=\mathbf{x}-\mathbf{x}_{1}$ 也是唯一的。

(b) 设 $X$ 是有限维向量空间，$X_{1}$ 是 $X$ 的子空间，则存在 $X$ 上的投影 $P$ 使得 $\operatorname{range}P=X_{1}$。

如果 $X_{1}=\{ \mathbf{0} \}$，结论是平凡的：取 $P=0$ 即可。

如果 $\dim X_{1}=k>0$，则我们可以取 $X_{1}$ 的基 $\{ \mathbf{u}_{1},\dots,\mathbf{u}_{k} \}$，然后将其扩张为 $X$ 的基 $\{ \mathbf{u}_{1},\dots,\mathbf{u}_{n} \}$。定义

$$
\begin{gather}
P(c_{1}\mathbf{u}_{1}+\dots+c_{n}\mathbf{u}_{n})=c_{1}\mathbf{u}_{1}+\dots+c_{k}\mathbf{u}_{k}
\end{gather}
$$

则 $P$ 是一个投影，并且 $\operatorname{range}P=X_{1}$。

注意到 $\ker P$ 的一个基是 $\{ \mathbf{u}_{k+1},\dots,\mathbf{u}_{n} \}$。此外，由于我们可以任意选取基，因此如果 $0<\dim X_{1}<\dim X$，那么存在无穷多个投影 $P$ 使得 $\operatorname{range}P=X_{1}$。

## Theorem 9.32 (秩定理)

设 $m,n,r$ 是非负整数，$m\geq r,n\geq r$，$\mathbf{F}$ 是从开集 $E\subset \mathbb{R}^{n}$ 到 $\mathbb{R}^{m}$ 的 $C^{1}$ 函数，并且对任意 $\mathbf{x}\in E$，$\operatorname{rank}\mathbf{F}'(\mathbf{x})=r$。

固定 $\mathbf{a}\in E$，令 $A=\mathbf{F}'(\mathbf{a})$，$Y_{1}=\operatorname{range}A$，并令 $P$ 是 $\mathbb{R}^{m}$ 上的投影，使得 $\operatorname{range}P=Y_{1}$，取 $Y_{2}=\ker P$。

则存在开集 $U\subset E,V\subset \mathbb{R}^{n}$，满足 $\mathbf{a}\in U$，且有 $C^{1}$ 双射 $\mathbf{H}\colon V\to U$ 使得

$$
\begin{gather}
\mathbf{F}(\mathbf{H}(\mathbf{x}))=A\mathbf{x}+\varphi(A\mathbf{x}) \quad (\mathbf{x}\in V) \tag{9.32.1}
\end{gather}
$$

其中 $\varphi$ 是一个从开集 $A(V)\subset Y_{1}$ 到 $Y_{2}$ 的 $C^{1}$ 函数。

我们来解释一下 $(9.32.1)$ 给出了 $\mathbf{F}$ 在局部的什么信息。如果 $\mathbf{y}\in \mathbf{F}(U)$，则存在 $\mathbf{x}\in V$ 使得 $\mathbf{y}=\mathbf{F}(\mathbf{H}(\mathbf{x}))$，从而 $P\mathbf{y}=A\mathbf{x}$，因此

$$
\begin{gather}
\mathbf{y}=P\mathbf{y}+\varphi(P\mathbf{y}) \quad (\mathbf{y}\in \mathbf{F}(U))
\end{gather}
$$

换句话说，$\mathbf{y}$ 仅由它的投影 $P\mathbf{y}$ 确定。从而，$P\colon \mathbf{F}(U)\to A(V)$ 是一个双射，因而 $\mathbf{F}(U)$ 是 $\mathbb{R}^{m}$ 中的一个 $r$ 维流形，其上的每个点都恰好覆盖了 $A(V)$ 上的一个点。等价地，我们也可以将 $\mathbf{F}(U)$ 视为 $\varphi$ 在 $A(V)$ 上的图像。

如果 $\Phi(\mathbf{x})=\mathbf{F}(\mathbf{H}(\mathbf{x}))$，则 $(9.32.1)$ 表明，$\Phi$ 的水平集（使得 $\Phi$ 取特定值的自变量的集合）正是 $A$ 在 $V$ 上的水平集，根据线性代数中的结论，这些集合平行于子空间 $\ker A$，因而是“平直”的。相应地，根据秩-零化度定理，$\dim \ker A=n-r$，因此 $\mathbf{F}$ 的水平集是 $\Phi$ 的平直水平集在 $\mathbf{H}$ 下的像，从而是 $\mathbb{R}^{n}$ 中的 $n-r$ 维流形。

我们将其写成分量形式，则秩定理说的就是：$\mathbf{F}$ 在局部的行为等价于一个秩为 $r$ 的线性变换。

根据线性代数的结论，定义域 $\mathbb{R}^{n}$ 有直和分解 $\mathbb{R}^{n}=X_{1}\oplus \ker A$，其中 $X_{1}$ 对应于 $A$ 的 $r$ 个“有效方向”。取 $\mathbb{R}^{n}$ 的基 $\{ \mathbf{u}_{1},\dots,\mathbf{u}_{n} \}$ 使得前 $r$ 个向量为 $X_{1}$ 的基，后 $n-r$ 个向量为 $\ker A$ 的基，则 $A\mathbf{u}_{1},\dots,A\mathbf{u}_{r}$ 构成了 $Y_{1}=\operatorname{range}A$ 的一个基。

另一方面，对于 $\mathbb{R}^{m}$ 也有 $\mathbb{R}^{m}=Y_{1}\oplus Y_{2}$，我们取

$$
\begin{gather}
\mathbf{v}_{1}=A\mathbf{u}_{1},\dots,\mathbf{v}_{r}=A\mathbf{u}_{r}
\end{gather}
$$

然后任取 $Y_{2}=\ker P$ 的一个基 $\mathbf{v}_{r+1},\dots,\mathbf{v}_{m}$ 组成 $\mathbb{R}^{m}$ 的一个基。

于是，对任意 $\mathbf{x}\in V$，设它在基 $\{ \mathbf{u}_{1},\dots,\mathbf{u}_{n} \}$ 下的坐标为

$$
\begin{gather}
\mathbf{x}=\sum_{j=1}^{n} x_{j}\mathbf{u}_{j} \implies \mathbf{x}=(x_{1},\dots,x_{n})
\end{gather}
$$

则 $A\mathbf{x}$ 在基 $\{ \mathbf{v}_{1},\dots,\mathbf{v}_{m} \}$ 下有坐标

$$
\begin{gather}
A\mathbf{x}=\sum_{j=1}^{r} x_{j}A\mathbf{u}_{j}+\mathbf{0}=\sum_{j=1}^{r} x_{j}\mathbf{v}_{j} \implies A\mathbf{x}=(x_{1},\dots,x_{r},0,\dots,0)
\end{gather}
$$

由于 $\varphi$ 将 $A(V)\subset Y_{1}$ 映射到 $Y_{2}$，后者由 $\mathbf{v}_{r+1},\dots,\mathbf{v}_{m}$ 张成，因此

$$
\begin{gather}
A\mathbf{x}+\varphi(A\mathbf{x})=(x_{1},\dots,x_{r},\varphi_{1}(\mathbf{x}_{r}),\dots,\varphi_{m-r}(\mathbf{x}_{r}))
\end{gather}
$$

其中 $\mathbf{x}_{r}=(x_{1},\dots,x_{r})$。

这就是说，$\mathbf{F}(\mathbf{H}(\mathbf{x}))$ 的值完全由 $\mathbf{x}$ 在 $X_{1}$ 上的投影 $\mathbf{x}_{r}$ 决定，因此 $\mathbf{F}(\mathbf{H}(V))=\mathbf{F}(U)$ 可以通过 $r$ 个坐标进行参数化，换言之，$\mathbf{F}(U)$ 是一个 $r$ 维流形。相应地，$\mathbf{F}\circ \mathbf{H}$ 的水平集元素总可以写成一个特解 $\mathbf{x}_{r}^{*}$ 加上任意选取的齐次解 $(0,\dots,0,x_{r+1},\dots,x_{n})$ 的形式，因而是一个平行于子空间 $\ker A$ 的平直集合。从而，$\mathbf{F}$ 的水平集可以通过 $n-r$ 个坐标进行参数化，即，它是一个 $n-r$ 维的流形。

最后，利用 $\mathbb{R}^{m}$ 上的坐标变换

$$
\begin{gather}
\mathbf{G}(y_{1},\dots,y_{m})=(y_{1},\dots,y_{r},y_{r+1}-\varphi_{1}(\mathbf{y}_{r}),\dots,y_{m}-\varphi_{m-r}(\mathbf{y}_{r}))
\end{gather}
$$

我们就有

$$
\begin{gather}
\mathbf{G}\circ \mathbf{F}\circ \mathbf{H}(\mathbf{x})=(x_{1},\dots,x_{r},0,\dots,0)
\end{gather}
$$

换言之，通过适当的坐标变换 $\mathbf{G}$ 和 $\mathbf{H}$，$\mathbf{F}$ 在局部的行为就等价于一个秩为 $r$ 的投影+嵌入。

从这一角度看，反函数定理和隐函数定理都是秩定理的特例。对于前者有 $n=m=r$，此时 $\mathbf{F}$ 在局部等价于恒等变换，换言之，$\mathbf{F}$ 本身是一个坐标变换（微分同胚）。对于后者有 $n+m\geq n=r$，此时 $\mathbf{F}$ 在局部等价于在前 $n$ 个坐标上的投影，这使得 $\mathbf{F}$ 的水平集可由后 $m$ 个坐标参数化，从而是一个 $m$ 维流形。

### Proof

如果 $r=0$，则 $\mathbf{F}'(\mathbf{x})=0$，从而 $\mathbf{F}$ 在 $\mathbf{a}$ 的邻域 $U$ 上是常值函数。取 $V=U$，$\mathbf{H}(\mathbf{x})=\mathbf{x}$，$\varphi(\mathbf{0})=\mathbf{F}(\mathbf{a})$ 即证。下面假设 $r>0$。

由于 $\dim Y_{1}=r$，故其有基 $\{ \mathbf{y}_{1},\dots,\mathbf{y}_{r} \}$。取 $\mathbf{z}_{i}\in \mathbb{R}^{n}$ 使得 $A\mathbf{z}_{i}=\mathbf{y}_{i}$，并定义线性变换 $S\in L(Y_{1},\mathbb{R}^{n})$ 为

$$
\begin{gather}
S(c_{1}\mathbf{y}_{1}+\dots+c_{r}\mathbf{y}_{r})=c_{1}\mathbf{z}_{1}+\dots+c_{r}\mathbf{z}_{r}
\end{gather}
$$

则 $AS\mathbf{y}_{i}=A\mathbf{z}_{i}=\mathbf{y}_{i}$，从而

$$
\begin{gather}
AS\mathbf{y}=\mathbf{y} \quad (\mathbf{y}\in Y_{1})
\end{gather}
$$

定义

$$
\begin{gather}
\mathbf{G}(\mathbf{x})=\mathbf{x}+SP(\mathbf{F}(\mathbf{x})-A\mathbf{x}) \quad (\mathbf{x}\in E)
\end{gather}
$$

由于 $\mathbf{F}'(\mathbf{a})=A$，因此 $\mathbf{G}'(\mathbf{a})=I\neq 0$。根据反函数定理，存在开集 $U,V\subset \mathbb{R}^{n}$，使得 $\mathbf{a}\in U$，且 $\mathbf{G}\colon U\to V$ 是 $C^{1}$ 双射，其反函数 $\mathbf{H}$ 也是 $C^{1}$ 函数。此外，通过取 $V$ 中的一个开球，我们可以选取 $U,V$ 使得 $V$ 是凸集，且 $\mathbf{H}'(\mathbf{x})$ 对任意 $\mathbf{x}\in V$ 都可逆。

注意到，$ASPA=A$，因为 $AS$ 是 $Y_{1}=\operatorname{range}P$ 上的恒等变换，且 $P$ 是一个投影，故 $PA=A$。因此，

$$
\begin{gather}
A\mathbf{G}(\mathbf{x})=P\mathbf{F}(\mathbf{x}) \quad (\mathbf{x}\in E)
\end{gather}
$$

将 $\mathbf{x}$ 替换为 $\mathbf{H}(\mathbf{x})$，就有

$$
\begin{gather}
P\mathbf{F}(\mathbf{H}(\mathbf{x}))=A\mathbf{x} \quad (\mathbf{x}\in V) \tag{9.32.2}
\end{gather}
$$

定义

$$
\begin{gather}
\psi(\mathbf{x})=\mathbf{F}(\mathbf{H}(\mathbf{x}))-A\mathbf{x} \quad (\mathbf{x}\in V)
\end{gather}
$$

则 $P\psi(\mathbf{x})=\mathbf{0}$，因此 $\psi\colon V\to Y_{2}=\ker P$ 是一个 $C^{1}$ 函数。由于 $V$ 是开集，$A$ 是线性变换，因此 $A(V)$ 也是 $Y_{1}=\operatorname{range}A$ 中的开集。

要完成证明，我们需要构造 $C^{1}$ 函数 $\varphi\colon A(V)\to Y_{2}$ 满足

$$
\begin{gather}
\varphi(A\mathbf{x})=\psi(\mathbf{x}) \quad (\mathbf{x}\in V) \tag{9.32.3}
\end{gather}
$$

首先，我们来证明当 $\mathbf{x}_{1},\mathbf{x}_{2}\in V,A\mathbf{x}_{1}=A\mathbf{x}_{2}$ 时

$$
\begin{gather}
\psi(\mathbf{x}_{1})=\psi(\mathbf{x}_{2}) \tag{9.32.4}
\end{gather}
$$

取 $\Phi(\mathbf{x})=\mathbf{F}(\mathbf{H}(\mathbf{x}))$，由于 $\mathbf{H}'(\mathbf{x})$ 的秩为 $n$，$\mathbf{F}'(\mathbf{\mathbf{x}})$ 的秩为 $r$，因此

$$
\begin{gather}
\operatorname{rank}\Phi'(\mathbf{x})=\operatorname{rank} \mathbf{F}'(\mathbf{H}(\mathbf{x}))\mathbf{H}'(\mathbf{x})=r
\end{gather}
$$

固定 $\mathbf{x}\in V$，令 $M$ 为 $\Phi'(\mathbf{x})$ 的值域，则 $M\subset \mathbb{R}^{m},\dim M=r$。对 $(9.32.2)$ 两边求导，可得

$$
\begin{gather}
P \Phi'(\mathbf{x})=A
\end{gather}
$$

因此 $P$ 将 $M$ 满射到 $Y_{1}=\operatorname{range}A$。由于 $\dim M=\dim Y_{1}=r$，因此 $P$ 在 $M$ 上是单射的。

现在假设 $A\mathbf{h}=\mathbf{0}$，则 $P\Phi'(\mathbf{x})\mathbf{h}=\mathbf{0}$。但 $\Phi'(\mathbf{x})\mathbf{h}\in M$，因此由 $P$ 的单射性知 $\Phi'(\mathbf{x})\mathbf{h}=\mathbf{0}$。于是，我们就证明了如下结论：

如果 $\mathbf{x}\in V$ 且 $A\mathbf{h}=\mathbf{0}$，那么 $\psi'(\mathbf{x})\mathbf{h}=\mathbf{0}$。

现在我们可以来证明 $(9.32.4)$ 了。设 $A\mathbf{x}_{1}=A\mathbf{x}_{2}$，令 $\mathbf{h}=\mathbf{x}_{2}-\mathbf{x}_{1}$，则 $A\mathbf{h}=\mathbf{0}$。定义

$$
\begin{gather}
\mathbf{g}(t)=\psi(\mathbf{x}_{1}+t\mathbf{h}) \quad (0\leq t\leq 1)
\end{gather}
$$

由 $V$ 的凸性可知 $\mathbf{x}_{1}+t\mathbf{h}\in V$，因此

$$
\begin{gather}
\mathbf{g}'(t)=\psi'(\mathbf{x}_{1}+t\mathbf{h})\mathbf{h}=\mathbf{0} \quad (0\leq t\leq 1)
\end{gather}
$$

因此 $\psi(\mathbf{x}_{1})=\mathbf{g}(0)=\mathbf{g}(1)=\psi(\mathbf{x}_{2})$。

这就是说，$\psi(\mathbf{x})$ 的取值仅和 $A\mathbf{x}$ 有关，从而 $(9.32.3)$ 在 $A(V)$ 上唯一地定义了函数 $\varphi$，下面我们只需证明 $\varphi \in C^{1}$。

固定 $\mathbf{y}_{0}\in A(V)$，取 $\mathbf{x}_{0}\in V$ 使得 $A\mathbf{x}_{0}=\mathbf{y}_{0}$。由于 $V$ 是开集，存在 $\mathbf{y}_{0}$ 的邻域 $W\subset Y_{1}$ 使得对任意 $\mathbf{y}\in W$ 有

$$
\begin{gather}
\mathbf{x}=\mathbf{x}_{0}+S(\mathbf{y}-\mathbf{y}_{0}) \in V
\end{gather}
$$

从而

$$
\begin{gather}
A\mathbf{x}=A\mathbf{x}_{0}+\mathbf{y}-\mathbf{y}_{0}=\mathbf{y}
\end{gather}
$$

因此

$$
\begin{gather}
\varphi(\mathbf{y})=\psi(\mathbf{x}_{0}+S(\mathbf{y}-\mathbf{y}_{0})) \quad (\mathbf{y}\in W)
\end{gather}
$$

上式表明 $\varphi \in C^{1}(W)$。再根据 $\mathbf{y}_{0}$ 的任意性可得 $\varphi \in C^{1}(A(V))$，这就完成了证明。

# Determinants 行列式

行列式是与 $n\times n$ 矩阵，以及这些矩阵所对应的线性变换相关联的一个数字。根据行列式是否为零，它们可以检测一个线性变换是否可逆，因而可以用来判断反函数定理与隐函数定理中的相关假设是否满足。不仅如此，它们在微分形式的研究中扮演了更为重要的角色。

## Definition 9.33 determinant 行列式

设 $(j_{1},\dots,j_{n})$ 是整数的 $n$ 元组，定义

$$
\begin{gather}
\operatorname{sgn}(j_{1},\dots,j_{n})=\prod_{p<q} \operatorname{sgn}(j_{q}-j_{p})
\end{gather}
$$

其中

$$
\begin{gather}
\operatorname{sgn}x=\begin{cases}
1, & x>0 \\
0, & x=0 \\
-1, & x<0
\end{cases}
\end{gather}
$$

为符号函数。从而，在以上定义中 $\operatorname{sgn}(j_{1},\dots,j_{n})\in \{ -1,0,1 \}$，并且如果两个 $j$ 交换位置，那么 $\operatorname{sgn}(j_{1},\dots,j_{n})$ 将改变符号。

设 $A\in L(\mathbb{R}^{n})$，其在标准基下的矩阵为 $[A]=(a(i,j))$，该矩阵的行列式定义为

$$
\begin{gather}
\det [A]=\sum_{(j_{1},\dots,j_{n})} \operatorname{sgn}(j_{1},\dots,j_{n}) a(1,j_{1})a_{2}(2,j_{2})\cdots a(n,j_{n})
\end{gather}
$$

其中 $(j_{1},\dots,j_{n})$ 遍历 $\{ 1,2,\dots n \}$ 上的所有 $n$ 元组。

$[A]$ 的列向量 $\mathbf{x}_{j}$ 可以表示为

$$
\begin{gather}
\mathbf{x}_{j}=\sum_{i=1}^{n} a(i,j)\mathbf{e}_{i} \quad (1\leq j\leq n)
\end{gather}
$$

我们可以将 $\det[A]$ 视为关于 $[A]$ 的列向量的函数

$$
\begin{gather}
\det(\mathbf{x}_{1},\dots,\mathbf{x}_{n})=\det[A]
\end{gather}
$$

于是 $\det$ 就是一个从 $(\mathbb{R}^{n})^{n}\cong \mathbb{R}^{n\times n}$ 到 $\mathbb{R}$ 的函数。

### Motivation

如果 $(j_{1},\dots,j_{n})$ 是一个置换，即 $j_{1},\dots,j_{n}\in \{ 1,2,\dots,n \}$ 且各不相同，则 $\operatorname{sgn}(j_{1},\dots,j_{n})$ 就是该置换的符号，它显示了置换中的逆序数量的奇偶性。所谓逆序，就是满足 $p<q$ 且 $j_{p}>j_{p}$ 的二元组 $(p,q)$，因此利用符号函数的特性，[[#Definition 9.33]] 中的乘积正确地捕捉了置换中逆序的奇偶性。

现在我们将 $(j_{1},\dots,j_{n})$ 扩展为 $\{ 1,2,\dots n \}$ 上的所有 $n$ 元组，容易看出，只有置换才能使 $\operatorname{sgn}(j_{1},\dots,j_{n})\neq 0$。这是因为如果有 $j_{p}=j_{q}$，那么定义中的乘积有一项为零，从而 $\operatorname{sgn}(j_{1},\dots,j_{n})=0$。作为结果，在 $\det[A]$ 的定义式中，我们可以将 $(j_{1},\dots,j_{n})$ 的遍历范围替换为 $\{ 1,2,\dots,n \}$ 上的所有置换。

## Theorem 9.34

(a) 如果 $I\in L(\mathbb{R}^{n})$ 是恒等算子，则

$$
\begin{gather}
\det[I]=\det(\mathbf{e}_{1},\dots,\mathbf{e}_{n})=1
\end{gather}
$$

(b) $\det$ 关于每个列向量 $\mathbf{x}_{j}$ 都是线性函数。也就是说，定义为

$$
\begin{gather}
T(\mathbf{x})=\det(\mathbf{x}_{1},\dots,\mathbf{x}_{j-1},\mathbf{x},\mathbf{x}_{j+1},\dots,\mathbf{x}_{n})
\end{gather}
$$

的函数 $T$ 是一个线性函数。

(c) 如果 $[A]_{1}$ 由矩阵 $[A]$ 交换两列得到，那么 $\det[A]_{1}=-\det[A]$。
(d) 如果 $[A]$ 有相同的两列，那么 $\det[A]=0$。

### Proof

(a) 如果 $A=I$，则 $a(i,i)=1$，且当 $i\neq j$ 时有 $a(i,j)\neq 0$，因此

$$
\begin{gather}
\det[I]=\operatorname{sgn}(1,2,\dots,n)=1
\end{gather}
$$

(b) 根据 [[#Definition 9.33 determinant 行列式#Motivation]] 中的讨论，$\det[A]$ 的定义式中求和的每一项都恰包含每一列中的一个因子，因而 $\det$ 关于每一列是线性的。

(c) 是性质：如果交换 $(j_{1},\dots,j_{n})$ 中的两个 $j$，那么 $\operatorname{sgn}(j_{1},\dots,j_{n})$ 改变符号的直接推论。(d) 是 (c) 的一个推论（交换相同的那两列即可）。

## Theorem 9.35

如果 $[A]$ 和 $[B]$ 是 $n\times n$ 矩阵，则

$$
\begin{gather}
\det([B][A])=\det[B] \det[A]
\end{gather}
$$

### Proof

设 $\mathbf{x}_{1},\dots,\mathbf{x}_{n}$ 是 $[A]$ 的列，定义

$$
\begin{gather}
\Delta_{B}(\mathbf{x}_{1},\dots,\mathbf{x}_{n})=\Delta_{B}[A]=\det([B][A])
\end{gather}
$$

由于矩阵 $[B][A]$ 的列为 $B\mathbf{x}_{1},\dots,B\mathbf{x}_{n}$，因此

$$
\begin{gather}
\Delta_{B}(\mathbf{x}_{1},\dots,\mathbf{x}_{n})=\det(B\mathbf{x}_{1},\dots,B\mathbf{x}_{n})
\end{gather}
$$

故 $\Delta_{B}$ 满足 [[#Theorem 9.34]] 的 (b)(c)(d)。利用 $\Delta_{B}$ 关于每列的线性性，可得

$$
\begin{align}
\Delta_{B}[A] &= \Delta_{B}\left( \sum a(i,1)\mathbf{e}_{i},\mathbf{x}_{2},\dots,\mathbf{x}_{n} \right)=\sum_{i} a(i,1)\Delta_{B}(\mathbf{e}_{i},\mathbf{x}_{2},\dots,\mathbf{x}_{n}) \\
&=\sum_{(i_{1},\dots,i_{n})} a(i_{1},1)a(i_{2},2)\cdots a(i_{n},n)\Delta_{B}(\mathbf{e}_{i_{1}},\dots,\mathbf{e}_{i_{n}})
\end{align}
$$

其中 $(i_{1},\dots,i_{n})$ 遍历 $\{ 1,2,\dots,n \}$ 上的所有 $n$ 元组。根据 (c) 和 (d)，我们有

$$
\begin{gather}
\Delta_{B}(\mathbf{e}_{i_{1}},\dots,\mathbf{e}_{i_{n}})=\operatorname{sgn}(i_{1},\dots,i_{n})\Delta_{B}(\mathbf{e}_{1},\dots,\mathbf{e}_{n})
\end{gather}
$$

由于 $[B][I]=[B]$，故

$$
\begin{gather}
\Delta_{B}(\mathbf{e}_{1},\dots,\mathbf{e}_{n})=\det[B]
\end{gather}
$$

从而

$$
\begin{gather}
\det([B][A])=\sum_{(i_{1},\dots,i_{n})} \operatorname{sgn}(i_{1},\dots,i_{n})a(i_{1},1)\cdots a(i_{n},n) \det[B]
\end{gather}
$$

对任意 $n\times n$ 矩阵 $[A],[B]$ 成立。取 $[B]=[I]$ 可知右侧的求和为 $\det[A]$，这就完成了证明。

## Theorem 9.36

一个线性算子 $A\in L(\mathbb{R}^{n})$ 可逆当且仅当 $\det[A]\neq 0$。

### Proof

如果 $A$ 可逆，则

$$
\begin{gather}
\det[A]\det[A^{-1}]=\det([AA^{-1}])=\det[I]=1
\end{gather}
$$

因此 $\det[A]\neq 0$。

反之，如果 $A$ 不可逆，则 $[A]$ 的列是线性相关的。因此，存在 $\mathbf{x}_{k}$ 使得

$$
\begin{gather}
\mathbf{x}_{k}+\sum_{j\neq k} c_{j}\mathbf{x}_{j}=\mathbf{0}
\end{gather}
$$

根据 [[#Theorem 9.34]] (b) 和 (d)，将 $\mathbf{x}_{k}$ 替换为 $\mathbf{x}_{k}+\sum c_{j}\mathbf{x}_{j}$ 不会改变行列式的值。但有一列为零的矩阵其行列式为零，因此 $\det[A]=0$。

## Remark 9.37

假设 $\{ \mathbf{e}_{1},\dots,\mathbf{e}_{n} \}$ 和 $\{ \mathbf{u}_{1},\dots,\mathbf{u}_{n} \}$ 都是 $\mathbb{R}^{n}$ 的基，则对于 $A\in L(\mathbb{R}^{n})$，我们可以分别在两个基上构造矩阵 $[A]$ 和 $[A]_{U}$，其元素设为

$$
\begin{gather}
A\mathbf{e}_{j}=\sum_{i} a_{ij} \mathbf{e}_{i}, \quad A\mathbf{u}_{j}=\sum_{i} \alpha_{ij}\mathbf{u}_{i}
\end{gather}
$$

由于 $\mathbf{e}$ 和 $\mathbf{u}$ 都是基，故存在可逆映射 $B$ 使得 $\mathbf{u}_{j}=B\mathbf{e}_{j}=\sum_{i} b_{ij}\mathbf{e}_{i}$，从而

$$
\begin{align}
A\mathbf{u}_{j}=\sum_{k} \alpha_{kj} B\mathbf{e}_{k}=\sum_{i} \sum_{k} \alpha_{kj}b_{ik}\mathbf{e}_{i}
\end{align}
$$

再由

$$
\begin{gather}
AB\mathbf{e}_{j}=A\sum_{k} b_{kj}\mathbf{e}_{k}=\sum_{i}\sum_{k} b_{kj}a_{ik}\mathbf{e}_{i}
\end{gather}
$$

可得 $\sum a_{ik}b_{kj}=\sum b_{ik}\alpha_{kj}$，即

$$
\begin{gather}
[A][B]=[B][A]_{U}
\end{gather}
$$

两边取行列式，根据 $\det[B]\neq 0$ 即得

$$
\begin{gather}
\det[A]=\det[A]_{U}
\end{gather}
$$

换句话说，线性算子的矩阵的行列式不依赖于构造矩阵时所用的基。因此，我们可以定义线性算子的行列式 $\det A$ 等于它在任意基下的矩阵的行列式，而无需显式地构造一个矩阵。

## Definition 9.38 Jacobian

如果 $\mathbf{f}$ 是从开集 $E\subset \mathbb{R}^{n}$ 到 $\mathbb{R}^{n}$ 的函数，其在 $\mathbf{x}\in E$ 处可微，则我们定义 $\mathbf{f}$ 在 $\mathbf{x}$ 处的 Jacobian 为

$$
\begin{gather}
J_{\mathbf{f}}(\mathbf{x})=\det \mathbf{f}'(\mathbf{x})=\det \begin{bmatrix}
D_{1}f_{1}(\mathbf{x}) & \cdots & D_{n}f_{1}(\mathbf{x}) \\
\vdots & \ddots & \vdots \\
D_{1}f_{n}(\mathbf{x}) & \cdots & D_{n}f_{n}(\mathbf{x})
\end{bmatrix}
\end{gather}
$$

对于最右侧的表达式我们也用符号

$$
\begin{gather}
\frac{ \partial (f_{1},\dots,f_{n}) }{ \partial (x_{1},\dots,x_{n}) } 
\end{gather}
$$

来表示。

利用行列式的性质，我们可以将反函数定理中的条件 $\mathbf{f}'(\mathbf{a})$ 可逆替换为 $J_{\mathbf{f}}(\mathbf{a})\neq 0$。如果隐函数定理是以 $(9.29.1)$ 的形式叙述的，那么定理中关于线性变换 $A_{x}$ 可逆的假设就可以替换为

$$
\begin{gather}
\frac{ \partial (f_{1},\dots,f_{n}) }{ \partial (x_{1},\dots,x_{n}) } \neq 0
\end{gather}
$$

# Derivatives of Higher Order 高阶导数

## Definition 9.39

设 $f$ 是定义在开集 $E\subset \mathbb{R}^{n}$ 上的实值函数，其偏导数为 $D_{1}f,\dots,D_{n}f$。如果这些偏导数 $D_{j}f$ 自身也是可微的，则我们定义二阶偏导数为

$$
\begin{gather}
D_{ij}f=D_{i}D_{j}f \quad (i,j=1,2,\dots,n)
\end{gather}
$$

如果所有 $D_{ij}f$ 都在 $E$ 上连续，则我们称 $f\in C^{2}(E)$。函数 $\mathbf{f}\colon E\to \mathbb{R}^{m}$ 称为是一个 $C^{2}$ 函数，如果它的每个分量都是 $C^{2}$ 函数。

同理我们可以定义更高阶的偏导数，以及 $C^{3},C^{4},\dots$ 函数。特别地，我们定义 $f \in C^{\infty}$，如果 $f$ 属于每一个 $C^{k}\ (k=0,1,2,\dots)$。

下面我们给出的两个定理均只涉及两个方向上的偏导数，因此我们可以不失一般性地假设 $f$ 是一个双变量实值函数。其一是一个中值定理。

## Theorem 9.40

设 $f$ 是定义在开集 $E\subset \mathbb{R}^{2}$ 上的实值函数，$D_{1}f$ 和 $D_{21}f$ 在 $E$ 上存在。假设 $Q\subset E$ 是一个闭矩形，其边平行于坐标轴，并且其对角线上的两个顶点为 $(a,b)$ 和 $(a+h,b+k)$。令

$$
\begin{gather}
\Delta(f,Q)=f(a+h,b+k)-f(a+h,b)-f(a,b+k)+f(a,b)
\end{gather}
$$

则存在 $(x,y)\in \operatorname{Int}Q$ 使得

$$
\begin{gather}
\Delta(f,Q)=hkD_{21}f(x,y)
\end{gather}
$$

### Proof

我们应用两次中值定理。取 $u(t)=f(t,b+k)-f(t,b)$，则存在 $x$ 位于 $a$ 与 $a+h$ 之间，$y$ 位于 $b$ 与 $b+k$ 之间，使得

$$
\begin{align}
\Delta(f,Q) &= u(a+h)-u(a) \\
&= hu'(x) \\
&=h(D_{1}f(x,b+k)-D_{1}f(x,b)) \\
&=hkD_{21}f(x,y)
\end{align}
$$

其二表明，如果二阶偏导数连续，那么求导的顺序可以交换。

## Theorem 9.41 (Clairaut)

设 $f$ 是定义在开集 $E\subset \mathbb{R}^{2}$ 上的实值函数，且 $D_{1}f,D_{21}f,D_{2}f$ 在 $E$ 上存在。如果 $D_{21}f$ 在 $(a,b)\in E$ 处连续，则 $D_{12}f$ 在该点存在，并且

$$
\begin{gather}
D_{12}f(a,b)=D_{21}f(a,b)
\end{gather}
$$

### Proof

取 $A=D_{21}f(a,b)$，根据连续性，对任意 $\varepsilon>0$，存在 $h,k>0$ 使得在 [[#Theorem 9.40]] 的闭矩形 $Q$ 上有

$$
\begin{gather}
\lvert D_{21}(x,y)-A \rvert <\varepsilon \quad ((x,y)\in Q)
\end{gather}
$$

因此

$$
\begin{gather}
\left\lvert  \frac{\Delta(f,Q)}{hk}-A  \right\rvert <\varepsilon
\end{gather}
$$

固定 $h$ 并令 $k\to 0$，由于 $D_{2}f$ 在 $E$ 上存在，故

$$
\begin{gather}
\left\lvert  \frac{D_{2}f(a+h,b)-D_{2}f(a,b)}{h}-A  \right\rvert \leq\varepsilon
\end{gather}
$$

即证 $D_{12}f(a,b)=A$。

## Corollary 9.42

如果 $f\in C^{2}(E)$，则 $D_{12}f=D_{21}f$。

# Differentiation of Integrals 积分下的微分

假设 $\varphi$ 是一个双变量函数，它可以对一个变量积分，也可以对另一个变量做微分。一个自然的问题是：在什么情况下，这两种极限过程可以交换？更精确地说，$\varphi$ 要满足什么条件，可以使等式

$$
\begin{gather}
\frac{\mathrm{d}}{\mathrm{d}t} \int _{a}^{b} \varphi(x,t) \, \mathrm{d}x =\int _{a}^{b} \frac{ \partial \varphi }{ \partial t } (x,t) \, \mathrm{d}x 
\end{gather}
$$

成立？

在下面的定理中，我们采用记号

$$
\begin{gather}
\varphi(\cdot,t)(x)=\varphi(x,t), \quad \varphi(x,\cdot)(t)=\varphi(x,t)
\end{gather}
$$

换句话说，$\varphi(\cdot,t)$ 和 $\varphi(x,\cdot)$ 都是单变量函数。

## Theorem 9.43 (Leibnitz)

假设有以下性质成立：

(a) $\varphi(x,t)$ 在 $(x,t)\in[a,b]\times[c,d]$ 上有定义，
(b) $\alpha$ 是 $[a,b]$ 上的单调递增函数，
(c) 对任意 $t \in[c,d]$ 有 $\varphi(\cdot,t)\in \mathcal{R}(\alpha)$，
(d) $c<s<d$，对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对任意 $x \in[a,b]$ 有

$$
\begin{gather}
\lvert t-s \rvert <\delta \implies \lvert D_{2}\varphi(x,t)-D_{2}\varphi(x,s) \rvert <\varepsilon
\end{gather}
$$

即 $D_{2}\varphi(x,\cdot)$ 在 $t=s$ 处连续，并且这种连续性关于 $x$ 一致。

定义

$$
\begin{gather}
f(t)=\int _{a}^{b} \varphi(x,t) \, \mathrm{d}\alpha(x)  \quad (c\leq t\leq d)
\end{gather}
$$

则 $D_{2}\varphi(\cdot,s)\in \mathcal{R}(\alpha)$，$f'(s)$ 存在，并且

$$
\begin{gather}
f'(s)=\int _{a}^{b} D_{2}\varphi(x,s) \, \mathrm{d}\alpha(x) 
\end{gather}
$$

注意到，(c) 表明函数 $f$ 在 $[c,d]$ 上处处有定义。并且如果 $\varphi$ 在闭矩形 $[a,b]\times[c,d]$ 上连续（从而一致连续），那么 (d) 自然成立。

### Proof

考虑差商

$$
\begin{gather}
\psi(x,t)=\frac{\varphi(x,t)-\varphi(x,s)}{t-s} \quad (0<\lvert t-s \rvert <\delta)
\end{gather}
$$

根据中值定理，对任意 $(x,t)$，存在 $u$ 介于 $t$ 与 $s$ 之间，使得

$$
\begin{gather}
\psi(x,t)=D_{2}\varphi(x,u)
\end{gather}
$$

因此 (d) 表明

$$
\begin{gather}
\lvert \psi(x,t)-D_{2}\varphi(x,s) \rvert <\varepsilon \quad (a\leq x\leq b,0<\lvert t-s \rvert <\delta)
\end{gather}
$$

即，当 $t\to s$ 时，$\psi(\cdot,t)\to D_{2}\varphi(\cdot,s)$ 关于 $x$ 一致收敛。

又由于

$$
\begin{gather}
\frac{f(t)-f(s)}{t-s}=\int _{a}^{b} \psi(x,t) \, \mathrm{d}\alpha(x) 
\end{gather}
$$

且 $\psi(\cdot,t)\in \mathcal{R}(\alpha)$，应用 [[7 Sequences and Series of Functions#Theorem 7.16]] 就完成了证明。