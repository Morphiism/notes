## Zeros of Polynomials

回顾一下，一个 $m$ 次多项式 $p\colon \mathbb{F}\to \mathbb{F}$ 形如

$$
\begin{gather}
p(z)=a_{0}+a_{1}z+\dots+a_{m}z^{m} \quad (a_{m}\neq 0)
\end{gather}
$$

如果一个多项式有两组不同的系数，那么多项式的次数可能就不是唯一的。下面我们首先就要来证明这种情况不会发生。

### Definition 4.1 zero 零点，root 根

一个数 $\lambda \in \mathbb{F}$ 称为多项式 $p \in \mathcal{P}(\mathbb{F})$ 的一个零点或根，如果

$$
\begin{gather}
p(\lambda)=0
\end{gather}
$$

### Theorem 4.2

设 $m$ 是正整数，$p \in \mathcal{P}(\mathbb{F})$ 是一个 $m$ 次多项式。假设 $\lambda \in \mathbb{F}$，则 $p(\lambda)=0$ 当且仅当存在 $m-1$ 次多项式 $q$ 使得

$$
\begin{gather}
p(z)=(z-\lambda)q(z)
\end{gather}
$$

#### Proof

显然，如果 $p(z)=(z-\lambda)q(z)$，那么 $p(\lambda)=0\cdot q(0)=0$。因此我们假设 $p(\lambda)=0$。

假设

$$
\begin{gather}
p(z)=a_{0}+a_{1}z+\dots+a_{m}z^{m}
\end{gather}
$$

则

$$
\begin{gather}
p(z)=p(z)-p(\lambda)=a_{1}(z-\lambda)+\dots+a_{m}(z^{m}-\lambda^{m})
\end{gather}
$$

再根据恒等式

$$
\begin{gather}
z^{k}-\lambda^{k}=(z-\lambda)(z^{k-1}+\lambda z^{k-2}+\dots+\lambda^{k-1})
\end{gather}
$$

我们可知 $p(z)-p(\lambda)$ 等于 $z-\lambda$ 乘以一个最高 $m-1$ 次的多项式 $q(z)$，这就完成了证明。

### Theorem 4.3

设 $m$ 是正整数，$p \in \mathcal{P}(\mathbb{F})$ 是 $m$ 次多项式，则 $p$ 在 $\mathbb{F}$ 中最多有 $m$ 个零点。

#### Proof

我们对 $m$ 进行归纳。如果 $m=1$，则 $p(z)=a_{0}+a_{1}z$，由 $a_{1}\neq 0$ 知 $p$ 只有一个零点 $-a_{0} /a_{1}$。

下面我们假设定理对 $m-1$ 成立。设 $p$ 是一个 $m$ 次多项式，如果 $p$ 没有零点，那么证明结束。如果 $p$ 有一个零点 $\lambda$，则 [[#Theorem 4.2]] 表明存在 $m-1$ 次多项式 $q$ 使得

$$
\begin{gather}
p(z)=(z-\lambda)q(z)
\end{gather}
$$

根据归纳假设，$q$ 在 $\mathbb{F}$ 上最多有 $m-1$ 个零点，从而 $p$ 最多有 $m$ 个零点，这就完成了证明。

以上的定理证明了多项式系数的唯一性，因为如果

$$
\begin{gather}
p(z)=a_{0}+a_{1}z+\dots+a_{m}z^{m}=b_{0}+b_{1}z+\dots+b_{n}z^{n}
\end{gather}
$$

那么

$$
\begin{gather}
(a_{0}-b_{0})+(a_{1}-b_{1})z+\dots=0
\end{gather}
$$

如果存在 $k\geq 1$ 使得 $a_{k}\neq b_{k}$，那么左侧的多项式至少是 $k$ 次的，从而 [[#Theorem 4.3]] 表明它的零点数有限，但等式右边有无穷多个零点，矛盾。另一方面，如果等式左边为 $a_{0}-b_{0}$，那么显然也有 $a_{0}=b_{0}$。因此，一个多项式的系数完全由多项式本身决定，特别地，其次数也是唯一的。

我们定义多项式 $0$ 的次数为 $-\infty$，以使得等式

$$
\begin{gather}
\deg pq=\deg p+\deg q
\end{gather}
$$

没有平凡的例外。其中我们假设对 $m \in \mathbb{R}$ 有 $-\infty+m=-\infty$。

## Division Algorithm for Polynomials

在整数环中，我们有带余除法定理：如果 $p,s$ 是非负整数，$s\neq 0$，则存在唯一的非负整数 $q,r$ 使得

$$
\begin{gather}
p=qs+r, \quad 0\leq r<s
\end{gather}
$$

我们将 $q$ 称为 $p$ 除以 $s$ 的商，$r$ 称为余数。在多项式环中，我们同样也有类似的带余除法定理。

### Theorem 4.4 (带余除法)

设 $p,s \in \mathcal{P}(\mathbb{F})$，$s\neq 0$，则存在唯一的多项式 $q,r \in \mathcal{P}(\mathbb{F})$ 使得

$$
\begin{gather}
p(z)=q(z)s(z)+r(z), \quad \deg r<\deg s
\end{gather}
$$

#### Proof

令 $n=\deg p,m=\deg s$，如果 $n<m$，我们取 $q=0,r=p$ 即可。因此下面我们假设 $n\geq m$。

考虑向量空间 $\mathcal{P}_{n}(\mathbb{F})$ 中的向量组

$$
\begin{gather}
1,z,\dots,z^{m-1},s,zs,\dots,z^{n-m}s
\end{gather}
$$

它是线性无关的，因为其中的每个多项式都有不同的次数，并且它的长度为 $n+1=\dim \mathcal{P}_{n}(\mathbb{F})$，因此它是 $\mathcal{P}_{n}(\mathbb{F})$ 的一个基。

由于 $p \in \mathcal{P}_{n}(\mathbb{F})$，故存在唯一的 $a_{0},\dots,a_{m-1},b_{0},\dots,b_{n-m} \in \mathbb{F}$ 使得

$$
\begin{gather}
p=a_{0}+\dots+a_{m-1}z^{m-1}+s(b_{0}+\dots+b_{n-m}z^{n-m})
\end{gather}
$$

令 $q=b_{0}+\dots+b_{n-m}z^{n-m},r=a_{0}+\dots+a_{m-1}z^{m-1}$，则 $p=qs+r$ 且 $\deg r<\deg s$。

最后，$q,r$ 的唯一性由系数 $a_{0},\dots,a_{m-1},b_{0},\dots,b_{n-m}$ 的唯一性给出。

## Factorization of Polynomials over $\mathbb{C}$

前面我们统一地研究了 $\mathbb{F}=\mathbb{R},\mathbb{C}$ 上的多项式的代数性质。接下来，我们将看到 $\mathbb{R}$ 上与 $\mathbb{C}$ 上的多项式之间的区别。对于复系数多项式，它的一个基本性质如下。

### Theorem 4.5 (代数基本定理)

非常值复系数多项式在 $\mathbb{C}$ 上存在零点。

以上定理的证明可在任意一本复分析的教材中找到，尽管它称为代数基本定理，但它的每个证明都在不同程度上用到了 $\mathbb{C}$ 的完备性，一种分析学性质。

代数基本定理的一个重要推论是，它允许我们将复系数多项式分解为若干一次因子的乘积。

### Theorem 4.6

如果 $p \in \mathcal{P}(\mathbb{C})$ 是非常值多项式，则它有唯一分解（在各因子的不同排列被视为等价的意义下）

$$
\begin{gather}
p(z)=c(z-\lambda_{1})\cdots(z-\lambda_{m})
\end{gather}
$$

其中 $c,\lambda_{1},\dots,\lambda_{m}\in \mathbb{C}$。

#### Proof

设 $m=\deg p$，我们对 $m$ 进行归纳。如果 $m=1$，我们可以取

$$
\begin{gather}
p(z)=a_{0}+a_{1}z=a_{1}(z+a_{0} /a_{1})
\end{gather}
$$

显然该分解是唯一的。

下面我们假设定理对 $m-1$ 成立。根据代数基本定理，$p$ 有一个零点 $\lambda \in \mathbb{C}$，从而由 [[#Theorem 4.2]] 知存在 $m-1$ 次多项式 $q$ 使得

$$
\begin{gather}
p(z)=(z-\lambda)q(z)
\end{gather}
$$

对 $q$ 应用归纳假设，即得 $p$ 有所求的分解。

下面我们证明唯一性。常数 $c$ 由 $p$ 的 $z^{m}$ 项系数唯一确定，假设

$$
\begin{gather}
(z-\lambda_{1})\cdots(z-\lambda_{m})=(z-\tau_{1})\cdots(z-\tau_{m})
\end{gather}
$$

令 $z=\lambda_{1}$，则等式左边为零，从而右边必然有一项也为零，即有一个 $\tau$ 等于 $\lambda_{1}$。通过重新标号，我们可以假设 $\tau_{1}=\lambda_{1}$，于是

$$
\begin{gather}
(z-\lambda_{2})\cdots(z-\lambda_{m})=(z-\tau_{2})\cdots(z-\tau_{m})
\end{gather}
$$

对任意 $z\neq\lambda_{1}$ 成立。然而，根据 [[#Theorem 4.3]]，如果两个 $m-1$ 次多项式在无穷多个点上相等，那么它们作为多项式是相等的。因此以上等式对任意 $z \in \mathbb{C}$ 成立。

将以上论证重复 $m$ 次，即证 $\tau_{1},\dots,\tau_{m}$ 就是 $\lambda_{1},\dots,\lambda_{m}$ 的一个重排，这就完成了证明。

## Factorization of Polynomials over $\mathbb{R}$

一个实系数多项式在 $\mathbb{R}$ 中可能没有零点，例如 $1+x^{2}$。这是实系数多项式与复系数多项式最大的区别。后续我们也将看到，这也造成了实向量空间与复向量空间上定理条件的区别。

要得到 $\mathbb{R}$ 上的多项式分解，我们需要使用多项式在 $\mathbb{C}$ 上的分解。

### Theorem 4.7

设 $p \in \mathcal{P}(\mathbb{C})$ 是一个实系数多项式，则如果 $\lambda \in \mathbb{C}$ 是 $p$ 的零点，那么 $\overline{\lambda}$ 也是 $p$ 的零点。

#### Proof

设

$$
\begin{gather}
p(z)=a_{0}+a_{1}z+\dots+a_{m}z^{m}
\end{gather}
$$

并且

$$
\begin{gather}
p(\lambda)=a_{0}+a_{1}\lambda+\dots+a_{m}\lambda^{m}=0
\end{gather}
$$

由于实数的复共轭是其自身，故两边取复共轭即得

$$
\begin{gather}
a_{0}+a_{1}\overline{\lambda}+\dots+a_{m} \overline{\lambda}^{m}=0
\end{gather}
$$

即 $p(\overline{\lambda})=0$。

以上定理表明，实系数多项式的虚数根总是成对出现的。对于实数根，我们有如下的基本性质。

### Lemma 4.8

设 $b,c \in \mathbb{R}$，则存在如下形式的多项式分解

$$
\begin{gather}
x^{2}+bx+c=(x-\lambda_{1})(x-\lambda_{2}) \quad (\lambda_{1},\lambda_{2}\in \mathbb{R})
\end{gather}
$$

当且仅当 $b^{2}\geq 4c$。

现在我们可以给出 $\mathbb{R}$ 上多项式的分解了。其证明思路是这样的：我们将实系数多项式视为 $\mathcal{P}(\mathbb{C})$ 中的一个元素，并应用 [[#Theorem 4.6]]，这给出了 $p$ 作为一个复多项式的分解。在这之中 [[#Theorem 4.7]] 表明 $p$ 的非实数零点成对出现，因此如果 $p$ 的分解中有因子 $z-\lambda$，那么它一定也有 $z-\overline{\lambda}$，两种相乘就得到实系数多项式

$$
\begin{gather}
z^{2}-2(\operatorname{Re}\lambda)z+\lvert \lambda \rvert ^{2}
\end{gather}
$$

不过，以上思路有一个潜在的问题。[[#Theorem 4.7]] 只保证了当 $z-\lambda$ 出现在因子中时，一定有 $z-\overline{\lambda}$ 出现，但它没有保证两者出现的次数相同，这就是我们在证明中要解决的问题。

### Theorem 4.9

设 $p \in \mathcal{P}(\mathbb{R})$ 是非常值多项式，则 $p$ 有唯一分解（在各因子的不同排列被视为等价的意义下）

$$
\begin{gather}
p(x)=c(x-\lambda_{1})\cdots(x-\lambda_{m})(x^{2}+b_{1}x+c_{1})\cdots(x^{2}+b_{M}x+c_{M})
\end{gather}
$$

其中 $c,\lambda_{j},b_{k},c_{k}\in \mathbb{R}$，且 $b_{k}^{2}<4c_{k}$。

#### Proof

首先我们证明存在性。

将 $p$ 视为 $\mathcal{P}(\mathbb{C})$ 中的元素，如果 $p$ 的所有零点都是实数，那么我们就有所求的分解。因此我们假设存在非实数零点 $\lambda$，从而 [[#Theorem 4.7]] 表明 $\overline{\lambda}$ 也是 $p$ 的零点。于是我们有

$$
\begin{align}
p(x)&=(x-\lambda)(x-\overline{\lambda})q(x) \\
&=(x^{2}-2(\operatorname{Re}\lambda)x+\lvert \lambda \rvert ^{2})q(x)
\end{align}
$$

其中 $q \in \mathcal{P}(\mathbb{C})$ 具有次数 $\deg p-2$。如果我们能证明 $q$ 的系数都是实数，那么对 $p$ 的次数进行归纳即可证明以上定理。

我们有

$$
\begin{gather}
q(x)=\frac{p(x)}{x^{2}-2(\operatorname{Re}\lambda)x+\lvert \lambda \rvert ^{2}}
\end{gather}
$$

由于 $p \in \mathcal{P}(\mathbb{R})$，因此对任意 $x \in \mathbb{R}$ 有 $q(x) \in \mathbb{R}$。记

$$
\begin{gather}
q(x)=a_{0}+a_{1}x+\dots+a_{n-2}x^{n-2}
\end{gather}
$$

则由 $\operatorname{Im}q(x)=0$ 得

$$
\begin{gather}
\operatorname{Im}a_{0}+(\operatorname{Im}a_{1})x+\dots+(\operatorname{Im}a_{n-2})x^{n-2}=0
\end{gather}
$$

即 $\operatorname{Im}a_{0}=\dots=\operatorname{Im}a_{n-2}=0$。即证 $q$ 是实系数多项式，因而存在所求的分解。

下面我们证明唯一性。由于当 $b_{k}^{2}<4c_{k}$ 时有分解

$$
\begin{gather}
x^{2}+b_{k}x+c_{k}=(x-\lambda_{k})(x-\overline{\lambda}_{k}) \quad (\lambda_{k}\in \mathbb{C})
\end{gather}
$$

因此如果 $p$ 作为 $\mathcal{P}(\mathbb{R})$ 中的元素有两种不同的分解，那么 $p$ 作为 $\mathcal{P}(\mathbb{C})$ 中的元素也有两种不同的分解，与 [[#Theorem 4.6]] 矛盾。这就完成了证明。