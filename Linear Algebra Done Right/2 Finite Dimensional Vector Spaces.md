本章我们研究有限维向量空间的性质。其核心概念有两个：张成与线性无关，它们结合起来构成了向量空间的基的概念，而后者又被用于定义向量空间的维数。

# 2A Span and Linear Independence

## Linear Combinations and Span

### Definition 2.1 linear combination 线性组合

一组向量 $v_{1},\dots,v_{m}\in V$ 的一个线性组合是一个形如

$$
\begin{gather}
a_{1}v_{1}+\dots+a_{m}v_{m}
\end{gather}
$$

的向量，其中 $a_{1},\dots,a_{m}\in \mathbb{F}$。

### Example 2.2

(a) $(17,-4,2)$ 是向量 $(2,1,-3),(1,-2,4)$ 的线性组合，因为

$$
\begin{gather}
(17,-4,2)=6(2,1,-3)+5(1,-2,4)
\end{gather}
$$

(b) $(17,-4,5)$ 不是向量 $(2,1,-3),(1,-2,4)$ 的线性组合，因为不存在标量 $a_{1},a_{2}$ 使得

$$
\begin{gather}
(17,-4,5)=a_{1}(2,1,-3)+a_{2}(1,-2,4)
\end{gather}
$$

换言之，线性方程组

$$
\begin{gather}
17=2a_{1}+a_{2} \\
-4=a_{1}-2a_{2} \\
5=-3a_{1}+4a_{2}
\end{gather}
$$

无解。于是，一个线性方程组有无解的问题就自然地转换为了向量空间中的线性组合存在性问题。

### Definition 2.3 span 张成

一组向量 $v_{1},\dots,v_{m}\in V$ 的所有线性组合构成的集合称为 $v_{1},\dots,v_{m}$ 的张成空间，记作 $\operatorname{span}(v_{1},\dots,v_{m})$。这就是说，

$$
\begin{gather}
\operatorname{span}(v_{1},\dots,v_{m})=\{ a_{1}v_{1}+\dots+a_{m}v_{m} : a_{k}\in \mathbb{F} \}
\end{gather}
$$

我们定义空组 $()$ 的张成空间为 $\{ 0 \}$。

如果 $\operatorname{span}(v_{1},\dots,v_{m})=V$，我们就说 $v_{1},\dots,v_{m}$ 张成 $V$。

### Example 2.4

(a) 根据 [[#Example 2.2]]，我们有 $(17,-4,2)\in \operatorname{span}((2,1,-3),(1,-2,4))$，但 $(17,-4,5)\not\in\operatorname{span}((2,1,-3),(1,-2,4))$。

(b) 向量

$$
\begin{gather}
(1,0,\dots,0),(0,1,0,\dots,0),\dots,(0,\dots,0,1)
\end{gather}
$$

张成 $\mathbb{F}^{n}$，因为任意向量 $x=(x_{1},\dots,x_{n})\in \mathbb{F}^{n}$ 都可以写成以上向量的线性组合

$$
\begin{gather}
(x_{1},\dots,x_{n})=x_{1}(1,0,\dots,0)+\dots+x_{n}(0,\dots,0,1)
\end{gather}
$$

事实上，这种表示还是唯一的。

### Theorem 2.5

$V$ 中一组向量的张成空间是包含这些向量的最小子空间。

#### Proof

设 $v_{1},\dots,v_{m}\in V$，我们首先证明 $\operatorname{span}(v_{1},\dots,v_{m})$ 是一个子空间。

加法单位元在张成空间中，因为

$$
\begin{gather}
0=0v_{1}+\dots+0v_{m}
\end{gather}
$$

张成空间对加法和数乘封闭，因为

$$
\begin{gather}
\sum_{k=1}^{m} a_{k}v_{k}+\sum_{k=1}^{m} b_{k}v_{k}=\sum_{k=1}^{n} (a_{k}+b_{k})v_{k} \\
\lambda \sum_{k=1}^{m} a_{k}v_{k}=\sum_{k=1}^{m} (\lambda a_{k})v_{k}
\end{gather}
$$

因而 $\operatorname{span}(v_{1},\dots,v_{m})$ 是 $V$ 的子空间。

显然每个 $v_{k}\in \operatorname{span}(v_{1},\dots,v_{m})$。反之，如果一个子空间 $U$ 包含每个 $v_{k}$，由于 $U$ 对加法和数乘封闭，因此 $U$ 必然包含 $v_{1},\dots,v_{m}$ 的所有线性组合，即 $\operatorname{span}(v_{1},\dots,v_{m})$。这就完成了证明。

### Definition 2.6 finite dimensional 有限维的，infinite dimensional 无限维的

称一个向量空间是有限维的，如果它可以由有限个向量张成。

称一个向量空间是无限维的，如果它不是有限维的。

[[#Example 2.4]](b) 表明向量空间 $\mathbb{F}^{n}$ 是有限维的，后续我们将证明它的维数是 $n$。

### Definition 2.7 polynomial 多项式

一个函数 $p\colon \mathbb{F}\to \mathbb{F}$ 称为一个 $\mathbb{F}$ 上的多项式，如果存在 $a_{0},\dots,a_{m}\in \mathbb{F}$ 使得

$$
\begin{gather}
p(z)=a_{0}+a_{1}z+a_{2}z^{2}+\dots+a_{m}z^{m} \quad (z \in \mathbb{F})
\end{gather}
$$

我们记 $\mathbb{F}$ 上所有多项式构成的集合为 $\mathcal{P}(\mathbb{F})$。

在通常的加法和数乘下，$\mathcal{P}(\mathbb{F})$ 构成了一个向量空间，并且还是 $\mathbb{F}^{\mathbb{F}}$ 的一个子空间。

如果一个多项式可以用两列系数来表示，那么将两者相减可得一个恒为零的多项式，因而其系数全为零。这表明，一个多项式的系数是由多项式唯一地确定的，从而以下的定义是合理的。

### Definition 2.8 degree 次数

称一个多项式 $p \in \mathcal{P}(\mathbb{F})$ 的次数为 $m$，如果存在标量 $a_{0},\dots,a_{m}$ 使得 $a_{m}\neq 0$，且

$$
\begin{gather}
p(z)=a_{0}+a_{1}z+a_{2}z^{2}+\dots+a_{m}z^{m} \quad (z \in \mathbb{F})
\end{gather}
$$

我们记 $p$ 的次数为 $\deg p$。

我们定义恒为零的多项式的次数为 $-\infty$。

### Notation 2.9

设 $m$ 是非负整数，记所有次数小于等于 $m$ 的 $\mathbb{F}$-多项式构成的集合为 $\mathcal{P}_{m}(\mathbb{F})$。

显然，如果 $m$ 是非负整数，那么 $\mathcal{P}_{m}(\mathbb{F})=\operatorname{span}(1,z,\dots,z^{m})$，因此 $\mathcal{P}_{m}(\mathbb{F})$ 是一个有限维向量空间。

然而，$\mathcal{P}(\mathbb{F})$ 不是有限维的：假设存在有限个多项式能够张成 $\mathcal{P}(\mathbb{F})$，那么这些多项式的次数有最大值 $m$，从而 $z^{m+1}$ 不在这些多项式的张成空间中。因此，不存在有限个多项式张成 $\mathcal{P}(\mathbb{F})$，从而它是无限维的。

## Linear Independence

假设 $v_{1},\dots,v_{m}\in V$ 且 $v \in \operatorname{span}(v_{1},\dots,v_{m})$，则存在标量 $a_{1},\dots,a_{m}$ 使得

$$
\begin{gather}
v=a_{1}v_{1}+\dots+a_{m}v_{m}
\end{gather}
$$

我们关心的问题是，以上的表示是否是唯一的？我们取另一列标量 $c_{1},\dots,c_{m}$ 使得

$$
\begin{gather}
v=c_{1}v_{1}+\dots+c_{m}v_{m}
\end{gather}
$$

从而

$$
\begin{gather}
0=(a_{1}-c_{1})v_{1}+\dots+(a_{m}-c_{m})v_{m}
\end{gather}
$$

于是，问题就归结为了：$0$ 在 $\operatorname{span}(v_{1},\dots,v_{m})$ 中是否有唯一表示？（注意以上结论与 [[1 Vector Spaces#Theorem 1.32]] 的相似性。）如果答案是肯定的，那么 $a_{k}=c_{k}$，即，任意 $v \in \operatorname{span}(v_{1},\dots,v_{m})$ 的表示是唯一的。这种情况有一个特殊的名字，下面我们给出定义。

### Definition 2.10 linearly independent 线性无关

一组向量 $v_{1},\dots,v_{m}\in V$ 称为是线性无关的，如果唯一使得

$$
\begin{gather}
a_{1}v_{1}+\dots+a_{m}v_{m}=0
\end{gather}
$$

的方法是取 $a_{1}=\dots=a_{m}=0$。

我们定义空组 $()$ 是线性无关的。

### Example 2.11

(a) $(1,0,0,0),(0,1,0,0),(0,0,1,0)$ 在 $\mathbb{F}^{4}$ 中线性无关，因为如果

$$
\begin{gather}
a_{1}(1,0,0,0)+a_{2}(0,1,0,0)+a_{3}(0,0,1,0)=(a_{1},a_{2},a_{3},0)=0
\end{gather}
$$

那么 $a_{1}=a_{2}=a_{3}=0$。

(b) 设 $m$ 是非负整数，那么 $1,z,\dots,z^{m}$ 在 $\mathcal{P}(\mathbb{F})$ 中线性无关。设

$$
\begin{gather}
a_{0}+a_{1}z+\dots+a_{m}z^{m}=0 \quad (z \in \mathbb{F})
\end{gather}
$$

假设有 $a_{k}\neq 0$，并且 $k$ 是使得系数不为零的最大整数，当 $z\neq 0$ 时我们可以在等式两边除以 $z^{k}$，得到

$$
\begin{gather}
\frac{a_{0}}{z^{k}}+\frac{a_{1}}{z^{k-1}}+\dots+\frac{a_{k-1}}{z}+a_{k}=0
\end{gather}
$$

令 $\lvert z \rvert\to \infty$ 即得 $a_{k}=0$，矛盾。因此我们必然有 $a_{0}=\dots=a_{m}=0$。

对于 $\mathbb{F}$ 是一般域时的证明，我们将在后续给出一个代数证明。

(c) 单个向量是线性无关的，当且仅当它不是 $0$。

(d) 两个向量是线性无关的，当且仅当任何一个向量都不是另一个向量的标量倍。

(e) 如果从一个线性无关组中去除一些向量，剩下的向量仍然是线性无关的。这是因为去除一些向量等同于在线性组合中直接设置那些向量的系数为零，而这不会影响线性无关性的判定。

### Definition 2.12 linearly dependent 线性相关

一组向量 $v_{1},\dots,v_{m}\in V$ 是线性相关的，如果它不是线性无关的。

换句话说，存在不全为零的 $a_{1},\dots,a_{m}\in \mathbb{F}$ 使得 $a_{1}v_{1}+\dots+a_{m}v_{m}=0$。

### Example 2.13

(a) $(2,3,1),(1,-1,2),(7,3,c)$ 在 $\mathbb{F}^{3}$ 中线性相关当且仅当 $c=8$。我们可以将这一问题转换为一个线性方程组问题：在 $c$ 取何值时方程组

$$
\begin{gather}
2a_{1}+a_{2}+7a_{3}=0 \\
3a_{1}-a_{2}+3a_{3}=0 \\
a_{1}+2a_{2}+ca_{3}=0
\end{gather}
$$

有非零解？对于这个问题我们可以使用消元法进行求解。

(b) 如果一列向量中有一个向量可以写成其他向量的线性组合，那么这个向量组是线性相关的。例如，如果

$$
\begin{gather}
v_{m}=\sum_{k=1}^{m-1} c_{k}v_{k}
\end{gather}
$$

那么 $c_{1}v_{1}+\dots+c_{m-1}v_{m-1}-v_{m}=0$。

(c) 任何包含零向量 $0$ 的向量组都是线性相关的。因为我们可以任意选取 $0$ 的系数，而不会改变线性组合的值。

### Lemma 2.14 (线性相关引理)

设 $v_{1},\dots,v_{m}$ 在 $V$ 中线性相关，则存在 $1\leq k\leq m$ 使得

$$
\begin{gather}
v_{k} \in \operatorname{span}(v_{1},\dots,v_{k-1})
\end{gather}
$$

并且如果将 $v_{k}$ 从 $v_{1},\dots,v_{m}$ 中去除，剩下的向量仍然能够张成 $\operatorname{span}(v_{1},\dots,v_{m})$。

#### Proof

根据线性相关性，存在不全为零的标量 $a_{1},\dots,a_{m}$ 使得

$$
\begin{gather}
a_{1}v_{1}+\dots+a_{m}v_{m}=0
\end{gather}
$$

在这些标量中，存在一个最大的 $k$，使得 $a_{k}\neq 0$，从而

$$
\begin{gather}
v_{k}=-\frac{a_{1}}{a_{k}}v_{1}-\dots-\frac{a_{k-1}}{a_{k}}v_{k-1} \tag{2.14.1}
\end{gather}
$$

即 $v_{k}\in \operatorname{span}(v_{1},\dots,v_{k-1})$。

现在取 $v \in \operatorname{span}(v_{1},\dots,v_{m})$，则我们有

$$
\begin{gather}
v=c_{1}v_{1}+\dots+c_{m}v_{m}
\end{gather}
$$

在上式中将 $v_{k}$ 用 $(2.14.1)$ 的右侧表达式代入，则我们就有 $v$ 属于去除 $v_{k}$ 后剩余向量的张成空间。因此，去除 $v_{k}$ 不会改变张成空间。

注意，如果 $k=1$，那么我们实际有 $v_{1}=0 \in \operatorname{span}()=\{ 0 \}$，此时将 $v_{1}$ 去除显然也不会改变张成空间。

以上引理将用来证明如下的重要结果，它说明 $V$ 中线性无关向量组的长度永远小于等于 $V$ 的张成组的长度。

### Theorem 2.15

在有限维向量空间 $V$ 中，线性无关向量组的长度小于等于张成 $V$ 的向量组的长度。

#### Proof

设 $u_{1},\dots,u_{m}$ 在 $V$ 中线性无关，$w_{1},\dots,w_{n}$ 张成 $V$，我们采用如下的步骤来证明 $m\leq n$。

第 $1$ 步：

令 $B=(w_{1},\dots,w_{n})$，它张成 $V$。将 $u_{1}$ 添加到 $B$ 的开头，由于 $u_{1}$ 可以写成 $w_{1},\dots,w_{n}$ 的线性组合，因此

$$
\begin{gather}
u_{1},w_{1},\dots,w_{n}
\end{gather}
$$

线性相关。

根据 [[#Lemma 2.14 (线性相关引理)]]，有一个向量位于前面向量的张成空间中。我们知道 $u_{1}\neq 0$，因为 $u_{1},\dots,u_{m}$ 线性无关。因此我们可以从 $B$ 中去掉一个 $w$，剩下的 $u_{1}$ 和 $w$ 仍然张成 $V$。

第 $k$ 步：

在第 $k-1$ 步后，$B$ 包含向量 $u_{1},\dots,u_{k-1}$，后面跟着 $n-k+1$ 个 $w$，并且张成 $V$。因此，$u_{k}$ 位于 $B$ 的张成空间中，从而将 $u_{k}$ 加入 $B$ 中得到的向量组线性相关。

根据线性相关引理，有一个向量位于前面向量的张成空间中。由于 $u_{1},\dots,u_{k}$ 线性无关，因此这个向量不可能是 $u$，从而此时必然还有一个 $w$，我们将其从 $B$ 中去掉后剩下的向量仍然张成 $V$。

经过 $m$ 步后，我们在 $B$ 中添加了所有的 $u$，并去掉了 $m$ 个 $w$。在每一步中，我们证明了必然存在可供去除的 $w$，因此 $w$ 的数量 $n$ 大于等于 $u$ 的数量 $m$。这就完成了证明。

### Theorem 2.16

有限维向量空间的子空间是有限维的。

#### Proof

设 $V$ 是有限维的，$U$ 是它的子空间。我们按照如下方法构造 $U$ 的一个张成组。

第 $1$ 步：

如果 $U=\{ 0 \}$，那么显然 $U$ 是有限维的。如果 $U\neq \{ 0 \}$，取一个非零向量 $u_{1}\in U$。

第 $k$ 步：

前 $k-1$ 步已选取了 $u_{1},\dots,u_{k-1}\in U$。如果 $U=\operatorname{span}(u_{1},\dots,u_{k-1})$，那么 $U$ 是有限维的。

如果 $U\neq \operatorname{span}(u_{1},\dots,u_{k-1})$，选取 $u_{k}\in U$ 使得

$$
\begin{gather}
u_{k}\not\in \operatorname{span}(u_{1},\dots,u_{k-1})
\end{gather}
$$

根据线性相关引理，对任意 $k$，向量组 $u_{1},\dots,u_{k}$ 都是线性无关的，因为不存在向量 $u_{j}$ 使得它包含在前 $j-1$ 个向量的张成空间中。然而，$V$ 中的线性无关组的长度小于等于 $V$ 的张成组的长度（[[#Theorem 2.15]]），而后者是有限的，因此以上的过程必然在有限步内停止，意味着 $U$ 是有限维的。

# 2B Bases

### Definition 2.17 basis 基

$V$ 的一个基是 $V$ 中的一个线性无关且张成 $V$ 的向量组。

### Example 2.18

(a) 向量 $(1,0,\dots,0),(0,1,0,\dots,0),\dots,(0,\dots,0,1)$ 是 $\mathbb{F}^{n}$ 上的一个基，称为 $\mathbb{F}^{n}$ 上的标准基。

(b) $(1,2),(3,5)$ 构成了 $\mathbb{F}^{2}$ 上的一个基。注意到基的长度与 $\mathbb{F}^{2}$ 上标准基的长度一样，这实际上是基的一个基本特征。

(c) $(1,1,0),(0,0,1)$ 是 $\{ (x,x,y) \in \mathbb{F}^{3}: x,y \in \mathbb{F} \}$ 的一个基。

(d) $(1,-1,0),(1,0,-1)$ 是 $\{ (x,y,z)\in \mathbb{F}^{3}:x+y+z=0 \}$ 的一个基。

(e) 多项式 $1,z,\dots,z^{m}$ 构成了 $\mathcal{P}_{m}(\mathbb{F})$ 的一个基，称为 $\mathcal{P}_{m}(\mathbb{F})$ 上的标准基。

### Theorem 2.19

一组向量 $v_{1},\dots,v_{n}\in V$ 是 $V$ 的一个基，当且仅当任意 $v \in V$ 都可以唯一地表示为

$$
\begin{gather}
v=a_{1}v_{1}+\dots+a_{n}v_{n}
\end{gather}
$$

其中 $a_{1},\dots,a_{n}\in \mathbb{F}$。

#### Proof

首先假设 $v_{1},\dots,v_{n}$ 是基，由于基张成 $V$，故对任意 $v \in V$ 都存在标量 $a_{1},\dots,a_{n}$ 使得

$$
\begin{gather}
v=a_{1}v_{1}+\dots+a_{n}v_{n}
\end{gather}
$$

再由基的线性无关性，如果 $v=c_{1}v_{1}+\dots+c_{n}v_{n}$，相减可得

$$
\begin{gather}
0=(a_{1}-c_{1})v_{1}+\dots+(a_{n}-c_{n})v_{n}
\end{gather}
$$

从而 $a_{k}=c_{k}$，即表示是唯一的。

反之，由于任意 $v \in V$ 都可以表示为 $v_{1},\dots,v_{n}$ 的线性组合，因此这些向量张成 $V$。另一方面，由于将 $0$ 写成线性组合的方法是唯一的，即 $a_{1}=\dots=a_{n}=0$，即证 $v_{1},\dots,v_{n}$ 线性无关，从而它是一个基。

### Theorem 2.20

任何张成向量空间的向量组都包含一个向量空间的基。

#### Proof

假设 $v_{1},\dots,v_{n}$ 张成 $V$，我们希望去除其中的一些向量，使得剩下的向量线性无关且仍张成 $V$。因此这里显然需要用到线性相关引理。

令 $B=(v_{1},\dots,v_{n})$。

第 $1$ 步：

如果 $v_{1}=0$，将 $v_{1}$ 从 $B$ 中去除。如果 $v_{1}\neq 0$，保持 $B$ 不变。

第 $k$ 步：

如果 $v_{k}\in \operatorname{span}(v_{1},\dots,v_{k-1})$，将 $v_{k}$ 从 $B$ 中去除，根据线性相关引理，$B$ 的张成空间仍然是 $V$。否则，保持 $B$ 不变。

最后，$B$ 中剩下的向量仍然张成 $V$，并且由于 $B$ 中不存在包含于前面向量张成空间中的向量，线性相关引理表明 $B$ 是线性无关的。因此 $B$ 是一个基。

### Corollary 2.21

任何有限维向量空间都有基。

#### Proof

根据有限维向量空间的定义，它有一个张成组，应用 [[#Theorem 2.20]] 即得向量空间的一个基。

张成组可以通过去除冗余向量得到一个基。类似地，一个线性无关组也可以通过扩充向量来构成一个基。

### Theorem 2.22

有限维向量空间中的线性无关向量组可以扩充为向量空间的一个基。

#### Proof

设 $u_{1},\dots,u_{m}$ 在 $V$ 中线性无关，并取 $V$ 的一个张成组 $w_{1},\dots,w_{n}$，构造向量组

$$
\begin{gather}
u_{1},\dots,u_{m},w_{1},\dots,w_{n}
\end{gather}
$$

显然它张成 $V$，对其应用 [[#Theorem 2.20]] 中的过程，由于 $u_{1},\dots,u_{m}$ 线性无关，因此在这一过程中所有的 $u$ 都将被保留。最后，我们将得到 $V$ 的一个基，其包含所有的 $u$ 以及部分 $w$。

### Theorem 2.23

设 $V$ 是有限维向量空间，$U$ 是 $V$ 的子空间。则存在 $V$ 的子空间 $W$ 使得 $V=U\oplus W$。

我们将 $W$ 称为子空间 $U$ 的补空间。

#### Proof

根据 [[#Theorem 2.16]]，$U$ 也是有限维的，从而有基 $u_{1},\dots,u_{m}$。再根据 [[#Theorem 2.22]]，作为 $V$ 中的线性无关组，它可以扩张为 $V$ 的一个基 $u_{1},\dots,u_{m},w_{1},\dots,w_{n}$，令 $W=\operatorname{span}(w_{1},..,w_{n})$。

要证 $V=U\oplus W$，由 [[1 Vector Spaces#Theorem 1.33]]，我们只需证明 $V=U+W$ 且 $U\cap W=\{ 0 \}$。

设 $v \in V$，由于 $u_{1},\dots,u_{m},w_{1},\dots,w_{n}$ 张成 $V$，故有

$$
\begin{gather}
v=a_{1}u_{1}+\dots+a_{m}u_{m}+b_{1}w_{1}+\dots+b_{n}w_{n}
\end{gather}
$$

记前 $m$ 项的和为 $u$，后 $n$ 项的和为 $w$，则 $v=u+w$，其中 $u \in U$，$w \in W$，即证 $V=U+W$。

再设 $v \in U\cap W$，则有

$$
\begin{gather}
v=a_{1}u_{1}+\dots+a_{m}u_{m}=b_{1}w_{1}+\dots+b_{n}w_{n}
\end{gather}
$$

从而

$$
\begin{gather}
a_{1}u_{1}+\dots+a_{m}u_{m}-b_{1}w_{1}-\dots-b_{n}w_{n}=0
\end{gather}
$$

根据 $u_{1},\dots,u_{m},w_{1},\dots,w_{n}$ 的线性无关性，上式中的系数均为零，从而 $v=0$。即证 $U\cap W=\{ 0 \}$。

# 2C Dimension

目前为止，尽管我们一直在讨论有限维向量空间，但我们还没有一个正式的维度定义。我们的动机是这样的：任何合理的维度概念都应当使得 $\mathbb{F}^{n}$ 的维度是 $n$。又由于 $\mathbb{F}^{n}$ 上的标准基

$$
\begin{gather}
(1,0,\dots,0),(0,1,0,\dots,0),\dots,(0,\dots,0,1)
\end{gather}
$$

长度为 $n$，维度的一个候选定义可以是向量空间的基的长度。然而，这一定义只有在所有的基都有相同长度时有效，这正是下面的定理所要证的。

### Theorem 2.24

有限维向量空间的任何基都有相同的长度。

#### Proof

设 $B_{1}$ 和 $B_{2}$ 的有限维空间 $V$ 的两个基。根据 [[#Theorem 2.15]]，$B_{1}$ 作为线性无关组的长度小于等于 $B_{2}$ 作为张成组的长度，反之，$B_{1}$ 作为张成组的长度大于等于 $B_{2}$ 作为线性无关组的长度。即证 $B_{1},B_{2}$ 有相同长度。

### Definition 2.25 dimension 维度

一个有限维向量空间 $V$ 的维度定义为 $V$ 上任意基的长度，记作 $\dim V$。

### Example 2.26

(a) $\dim \mathbb{F}^{n}=n$，因为其上的标准基长度为 $n$。

(b) $\dim \mathcal{P}_{m}(\mathbb{F})=m+1$，其上的标准基 $1,z,\dots,z^{m}$ 具有长度 $m+1$。

(c) $\{ (x,x,y)\in \mathbb{F}^{3}: x,y \in \mathbb{F} \}$ 的维度是 $2$，它的基是 $(1,1,0),(0,0,1)$。

(d) $\{ (x,y,z)\in \mathbb{F}^{3}:x+y+z=0 \}$ 的维度是 $2$，因为 $(1,-1,0),(1,0,-1)$ 是它的一个基。

(e) $\mathbb{R}^{2}$ 作为 $\mathbb{R}$-向量空间是 $2$ 维的，$\mathbb{C}$ 作为 $\mathbb{C}$-向量空间是 $1$ 维的。然而，$\mathbb{C}$ 作为 $\mathbb{R}$-向量空间是 $2$ 维的（$\mathbb{C}$ 作为集合可以与 $\mathbb{R}^{2}$ 等同），因此讨论维度时需要指明向量空间的标量域。

由于有限维向量空间的子空间是有限维的，因此子空间上也可以定义维度的概念。

### Theorem 2.27

如果 $V$ 是有限维向量空间，$U$ 是 $V$ 的子空间，那么 $\dim U\leq \dim V$。

#### Proof

$U$ 的基在 $V$ 中线性无关，因而其长度 $\dim U$ 小于等于 $V$ 的基作为张成组的长度 $\dim V$。

要判断一组向量是否是基，我们需要证明它满足张成与线性无关两个条件。下面的定理表明，我们可以将其中一个条件替换为“长度等于维度”。

### Theorem 2.28

设 $V$ 是有限维的。则任何具有长度 $\dim V$ 的线性无关向量组都是 $V$ 的基。

#### Proof

设 $\dim V=n$，$v_{1},\dots,v_{n}$ 在 $V$ 中线性无关。根据 [[#Theorem 2.22]]，线性无关向量组可以扩张为一个基，但 $V$ 的基的长度为 $n$，因此这一扩张是平凡的：我们什么都不添加。这表明 $v_{1},\dots,v_{n}$ 本身就是一个基。

### Theorem 2.29

设 $V$ 是有限维向量空间，$U$ 是 $V$ 的子空间。如果 $\dim U=\dim V$，则 $U=V$。

#### Proof

设 $u_{1},\dots,u_{n}$ 是 $U$ 的基，其中 $n=\dim U=\dim V$。由于 $u_{1},\dots,u_{n}$ 线性无关，[[#Theorem 2.28]] 表明它也是 $V$ 的一个基。从而我们有

$$
\begin{gather}
U=\operatorname{span}(u_{1},\dots,u_{n})=V
\end{gather}
$$

### Example 2.30

设 $U$ 是 $\mathcal{P}_{3}(\mathbb{R})$ 的子空间，定义为

$$
\begin{gather}
U=\{ p \in \mathcal{P}_{3}(\mathbb{R}): p'(5)=0 \}
\end{gather}
$$

我们想要构造 $U$ 的一个基。首先我们注意到 $1,(x-5)^{2},(x-5)^{3}$ 在 $U$ 内。

假设 $a,b,c \in \mathbb{R}$ 满足

$$
\begin{gather}
a+b(x-5)^{2}+c(x-5)^{3}=0 \quad (x \in \mathbb{R})
\end{gather}
$$

等式左边 $x^{3}$ 的系数为 $c$，右边没有 $x^{3}$ 项，因此 $c=0$。此时等式左边 $x^{2}$ 的系数 $b$ 也为 $0$。从而我们也有 $a=0$，即证 $1,(x-5)^{2},(x-5)^{3}$ 线性无关。

因此，我们有

$$
\begin{gather}
3\leq \dim U\leq \dim \mathcal{P}_{3}(\mathbb{R})=4
\end{gather}
$$

如果 $\dim U=4$，那么根据 [[#Theorem 2.29]]，$U=\mathcal{P}_{3}(\mathbb{R})$，但这是不可能的：$x$ 在 $\mathcal{P}_{3}(\mathbb{R})$ 中但不在 $U$ 中，因为 $x'=1$。这表明 $\dim U=3$，从而 $1,(x-5)^{2},(x-5)^{3}$ 就是 $U$ 的一个基。

### Theorem 2.31

设 $V$ 是有限维的。则任意长度为 $\dim V$ 且张成 $V$ 的向量组都是 $V$ 的基。

#### Proof

设 $n=\dim V$，$v_{1},\dots,v_{n}$ 张成 $V$。根据 [[#Theorem 2.20]]，它可以缩减为 $V$ 的一个基，但任何基的长度都为 $n$，因此这一缩减是平凡的：我们没有去除任何一个向量。这表明 $v_{1},\dots,v_{n}$ 自身就是一个基。

### Theorem 2.32

设 $V_{1},V_{2}$ 是有限维向量空间的子空间，则

$$
\begin{gather}
\dim(V_{1}+V_{2})=\dim V_{1}+\dim V_{2}-\dim(V_{1}\cap V_{2})
\end{gather}
$$

#### Proof

容易验证 $V_{1}\cap V_{2}$ 也是子空间。设 $v_{1},\dots,v_{m}$ 是 $V_{1}\cap V_{2}$ 的基，作为 $V_{1}$ 中的线性无关组，我们可将其扩张为 $V_{1}$ 的基 $v_{1},\dots,v_{m},u_{1},\dots,u_{j}$；同理，我们也可将其扩张为 $V_{2}$ 的基 $v_{1},\dots,v_{m},w_{1},\dots,w_{k}$。

下面我们要证

$$
\begin{gather}
v_{1},\dots,v_{m},u_{1},\dots,u_{j},w_{1},\dots,w_{k} \tag{2.32.1}
\end{gather}
$$

是 $V_{1}+V_{2}$ 的基，此时我们有

$$
\begin{align}
\dim(V_{1}+V_{2}) &= m+j+k \\
&=(m+j)+(m+k)-m \\
&=\dim V_{1}+\dim V_{2}-\dim(V_{1}\cap V_{2})
\end{align}
$$

向量组 $(2.32.1)$ 的张成空间包含 $V_{1}$，也包含 $V_{2}$，因此它张成 $V_{1}+V_{2}$。下面我们只需证明 $(2.32.1)$ 线性无关。

设

$$
\begin{gather}
a_{1}v_{1}+\dots+a_{m}v_{m}+b_{1}u_{1}+\dots+b_{j}u_{j}+c_{1}w_{1}+\dots+c_{k}w_{k}=0
\end{gather}
$$

则

$$
\begin{gather}
\sum c_{i}w_{i}=-\sum a_{i}v_{i}-\sum b_{i}u_{i} \in V_{1}
\end{gather}
$$

从而 $\sum c_{i}w_{i}\in V_{1}\cap V_{2}$。因此有

$$
\begin{gather}
c_{1}w_{1}+\dots+c_{k}w_{k}=d_{1}v_{1}+\dots+d_{m}v_{m}
\end{gather}
$$

但 $v_{1},\dots,v_{m},w_{1},\dots,w_{k}$ 线性无关，因此所有的 $c$ 都为零。于是我们有

$$
\begin{gather}
\sum a_{i}v_{i}+\sum b_{i}u_{i}=0
\end{gather}
$$

根据 $v_{1},\dots,v_{m},u_{1},\dots,u_{j}$ 的线性无关性可得所有的 $a$ 和 $b$ 都为零。这就完成了证明。