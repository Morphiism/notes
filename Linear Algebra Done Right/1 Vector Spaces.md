“线性代数是研究有限维向量空间上的线性映射的学科”。本章我们先给出向量空间的定义，以及它的一些基本性质。

# 1A $\mathbb{R}^{n}$ and $\mathbb{C}^{n}$

## Complex Numbers

在线性代数中，使用复数通常能够得到更强的定理与更深刻的见解。因此，我们将首先给出复数的定义及其基本性质。

### Definition 1.1 complex number 复数

一个复数是一个有序对 $(a,b)$，其中 $a,b \in \mathbb{R}$。我们将其写成 $a+bi$。

所有复数构成的集合记作 $\mathbb{C}$，其上的加法和乘法定义为

$$
\begin{gather}
(a+bi)+(c+di)=(a+c)+(b+d)i \\
(a+bi)(c+di)=(ac-bd)+(ad+bc)i
\end{gather}
$$

其中 $a,b,c,d \in \mathbb{R}$。

### Theorem 1.2

复数的算术具有如下性质：

1. 交换律：对任意 $\alpha,\beta \in \mathbb{C}$ 有 $\alpha+\beta=\beta+\alpha,\alpha\beta=\beta\alpha$。
2. 结合律：对任意 $\alpha,\beta,\gamma \in \mathbb{C}$ 有 $(\alpha+\beta)+\gamma=\alpha+(\beta+\gamma)$，$(\alpha\beta)\gamma=\alpha(\beta\gamma)$。
3. 单位元：对任意 $\lambda \in \mathbb{C}$ 有 $\lambda+0=\lambda,1\lambda=\lambda$。
4. 加法逆元：对任意 $\alpha \in \mathbb{C}$，存在唯一的 $\beta \in \mathbb{C}$ 使得 $\alpha+\beta=0$。
5. 乘法逆元：对任意 $\alpha \in \mathbb{C}$，如果 $\alpha\neq 0$，那么存在唯一的 $\beta \in \mathbb{C}$ 使得 $\alpha\beta=1$。
6. 分配律：对任意 $\alpha,\beta,\lambda \in \mathbb{C}$ 有 $\lambda(\alpha+\beta)=\lambda\alpha+\lambda\beta$。

以上性质使得 $\mathbb{C}$，连带着其上的加法和乘法，构成了一个域。

### Definition 1.3 subtraction 减法，division 除法

设 $\alpha,\beta \in \mathbb{C}$。

令 $-\alpha$ 表示 $\alpha$ 的唯一加法逆元。$\mathbb{C}$ 上的减法定义为

$$
\begin{gather}
\beta-\alpha=\beta+(-\alpha)
\end{gather}
$$

对于 $\alpha\neq 0$，令 $1 /\alpha$ 表示 $\alpha$ 的唯一乘法逆元。$\mathbb{C}$ 上的除法定义为

$$
\begin{gather}
\beta /\alpha=\beta(1 /\alpha)
\end{gather}
$$

由于 $\mathbb{R}$ 和 $\mathbb{C}$ 都满足域的公理（[[#Theorem 1.2]]），因此它们在很多方面都有相同的性质。为了避免重复相同的证明，我们采取如下符号：

### Notation 1.4

我们用 $\mathbb{F}$ 来表示域 $\mathbb{R}$ 或 $\mathbb{C}$。

$\mathbb{F}$ 中的元素称为标量（scalar）。对于任意 $\alpha \in \mathbb{F}$ 和非负整数 $m$，我们定义 $\alpha^{m}$ 表示 $\alpha$ 自乘 $m$ 次的结果：

$$
\begin{gather}
\alpha^{m}=\alpha \cdot \alpha^{m-1}, \quad \alpha^{0}=1
\end{gather}
$$

利用归纳法我们可以证明对任意非负整数 $m,n$ 有

$$
\begin{gather}
(\alpha^{m})^{n}=\alpha^{mn}, \quad (\alpha\beta)^{m}=\alpha^{m}\beta^{m}
\end{gather}
$$

## Lists

$\mathbb{R}^{n}$ 与 $\mathbb{C}^{n}$ 是通常的平面 $\mathbb{R}^{2}$ 与空间 $\mathbb{R}^{3}$ 在更高维度的推广。要定义 $\mathbb{F}^{n}$，我们首先需要讨论有序组的概念。

### Definition 1.5 list 有序组，length 长度

设 $n$ 是非负整数，一个长度为 $n$ 的有序组（或 $n$-元组）是由 $n$ 个元素构成的有序集合 $(z_{1},\dots,z_{n})$。其中重复的元素是允许出现的。

两个有序组 $(z_{1},\dots,z_{n}),(w_{1},\dots,w_{m})$ 相等当且仅当 $n=m$ 且对任意 $1\leq j\leq n$ 有 $z_{j}=w_{j}$。

我们将长度为 $0$ 的有序组记作 $()$，我们将其视为一个有序组以便于一些定理没有平凡的例外。

## $\mathbb{F}^{n}$

下面我们固定一个正整数 $n$，并定义 $\mathbb{R}^{2}$ 与 $\mathbb{R}^{3}$ 的高维推广。

### Definition 1.6 $\mathbb{F}^{n}$，coordinate 坐标

定义 $\mathbb{F}^{n}$ 为所有 $\mathbb{F}$ 上长度为 $n$ 的有序组构成的集合：

$$
\begin{gather}
\mathbb{F}^{n}=\{ (x_{1},\dots,x_{n}) : x_{k}\in \mathbb{F} \}
\end{gather}
$$

对于 $x=(x_{1},\dots,x_{n})\in \mathbb{F}^{n}$ 以及 $1\leq k\leq n$，我们称 $x_{k}$ 为 $x$ 的第 $k$ 个坐标。

### Definition 1.7 addition 加法

$\mathbb{F}^{n}$ 上的加法定义为逐项相加：

$$
\begin{gather}
(x_{1},\dots,x_{n})+(y_{1},\dots,y_{n})=(x_{1}+y_{1},\dots,x_{n}+y_{n})
\end{gather}
$$

### Theorem 1.8

$\mathbb{F}^{n}$ 上的加法满足交换律：对任意 $x,y\in \mathbb{F}^{n}$，有 $x+y=y+x$。

#### Proof

设 $x=(x_{1},\dots,x_{n}),y=(y_{1},\dots,y_{n})$，则

$$
\begin{align}
x+y &= (x_{1}+y_{1},\dots,x_{n}+y_{n}) \\
&=(y_{1}+x_{1},\dots,y_{n}+x_{n}) \\
&=y+x
\end{align}
$$

这里我们用到了 $\mathbb{F}$ 上的交换律。

同理我们也可以证明 $\mathbb{F}^{n}$ 上的加法满足结合律。

### Notation 1.9

我们用 $0$ 来表示坐标全为 $0$ 的 $n$-元组：

$$
\begin{gather}
0=(0,\dots,0)
\end{gather}
$$

显然它是 $\mathbb{F}^{n}$ 上的加法单位元。

$\mathbb{R}^{2}$ 中的元素有一种几何的表示方法。通常，我们将 $v=(a,b)\in \mathbb{R}^{2}$ 视为平面上的一个点，或者从原点指向 $v$ 的一个箭头。在后一种情况下，我们通常称 $v$ 是一个向量。

我们可以任意地平移向量 $v$，并仍然将其视为同一个向量。这是因为平面上的向量完全由它的长度和方向确定。利用这个方法，我们可以给出平面向量加法的一个几何表示。

假设 $u,v\in \mathbb{R}^{2}$，我们将 $v$ 的起点移动到 $u$ 的终点，则 $u+v$ 就是这样一个向量：它的起点是 $u$ 的起点，终点指向此时 $v$ 的终点。

![](1-1.png)

### Definition 1.10 additive inverse 加法逆元

对于 $x=(x_{1},\dots,x_{n}) \in \mathbb{F}^{n}$，它的加法逆元定义为使得等式

$$
\begin{gather}
x+(-x)=0
\end{gather}
$$

成立的唯一 $-x \in \mathbb{F}^{n}$，即 $-x=(-x_{1},\dots,-x_{n})$。

在 $\mathbb{R}^{2}$ 中，$v$ 的加法逆元 $-v$ 是一个长度与 $v$ 相同，但方向相反的向量。根据前面加法的几何表示，$v+(-v)$ 正是一个起点与终点相同的向量，即零向量 $0$。

在加法之后我们可以定义 $\mathbb{F}^{n}$ 上的乘法。我们可以仿照加法的定义，把两个 $\mathbb{F}^{n}$ 元素的乘法定义为逐项相乘。但实践表明这个定义并不有用。相反，我们需要的是标量乘法的定义，即，将一个 $\lambda \in \mathbb{F}$ 与一个 $x \in \mathbb{F}^{n}$ 相乘的乘法定义。

### Definition 1.11 scalar multiplication 数乘

$\mathbb{F}^{n}$ 上的数乘定义为

$$
\begin{gather}
\lambda(x_{1},\dots,x_{n})=(\lambda x_{1},\dots,\lambda x_{n})
\end{gather}
$$

其中 $\lambda \in \mathbb{F},(x_{1},\dots,x_{n})\in \mathbb{F}^{n}$。

在 $\mathbb{R}^{2}$ 中，数乘 $\lambda v$ 是这样的向量：如果 $\lambda>0$，那么 $\lambda v$ 与 $v$ 方向相同，其长度为 $v$ 的 $\lambda$ 倍；而如果 $\lambda<0$，那么 $\lambda v$ 与 $v$ 方向相反，长度为 $v$ 的 $\lvert \lambda \rvert$ 倍。

## Digression on Fields

一个域是一个包含了至少两个不同元素 $0,1$ 的集合，其上定义了加法和乘法，满足 [[#Theorem 1.2]] 中列出的所有性质。因此，$\mathbb{R}$ 和 $\mathbb{C}$ 是域，有理数集合 $\mathbb{Q}$ 也是域。另一个最简单的例子是集合 $\{ 0,1 \}$，其中 $1+1=0$。

在本书中我们只考虑 $\mathbb{R}$ 和 $\mathbb{C}$，但对于大部分定理，其对于一般的域仍然成立。对于某些定理，其中假设为 $\mathbb{F}=\mathbb{C}$，我们通常可以将 $\mathbb{C}$ 替换为任意代数闭域 $\mathbb{F}$，意味着以 $\mathbb{F}$ 中元素为系数的非常值多项式在 $\mathbb{F}$ 中必然有零点。还有一些定理需要假设 $\mathbb{F}$ 的特征为 $0$，意味着不论自加多少次，都有 $1+1+\dots+1\neq 0$ 成立。

# 1B Definition of Vector Space

向量空间的定义是对 $\mathbb{F}^{n}$ 性质的一种抽象：加法是交换的、结合的、有单位元和逆元；数乘是结合的、有单位元，并且满足分配律。

满足以上这些性质的集合 $V$，连带着其上的加法和数乘，就构成了一个向量空间。

### Definition 1.12 addition, scalar multiplication

集合 $V$ 上的加法是一个函数，其将 $u,v \in V$ 关联到一个元素 $u+v\in V$。

$V$ 上的数乘是一个函数，其将 $\lambda \in \mathbb{F}$ 和 $v \in V$ 关联到一个元素 $\lambda v \in V$。

### Definition 1.13 vector space 向量空间

一个 $\mathbb{F}$ 上的向量空间是一个集合 $V$，连带着其上的加法和数乘，满足以下性质：

1. 交换律：对任意 $u,v\in V$ 有 $u+v=v+u$。
2. 结合律：对任意 $u,v,w \in V$ 和 $a,b \in \mathbb{F}$ 有 $(u+v)+w=u+(v+w)$，$(ab)v=a(bv)$。
3. 加法单位元：存在 $0 \in V$ 使得对任意 $v \in V$ 有 $v+0=v$。
4. 加法逆元：对任意 $v \in V$，存在 $w \in V$ 使得 $v+w=0$。
5. 数乘单位元：对任意 $v \in V$ 有 $1v=v$。
6. 分配律：对任意 $a,b \in \mathbb{F}$ 和 $u,v \in V$ 有 $(a+b)v=av+bv$，$a(u+v)=au+av$。

向量空间中的元素称为向量或者点。

一个 $\mathbb{R}$ 上的向量空间称为实向量空间，一个 $\mathbb{C}$ 上的向量空间称为复向量空间。

容易验证，$\mathbb{F}^{n}$ 在其上的加法和数乘下构成了一个 $\mathbb{F}$ 上的向量空间。最小的向量空间是 $\{ 0 \}$，它只包含了一个加法单位元。

### Example 1.14

设 $\mathbb{F}^{\infty}$ 表示 $\mathbb{F}$ 上的所有序列构成的集合：

$$
\begin{gather}
\mathbb{F}^{\infty}=\{ (x_{1},x_{2},\dots): x_{k}\in \mathbb{F} \}
\end{gather}
$$

其上的加法和数乘是逐项定义的：

$$
\begin{gather}
(x_{1},x_{2},\dots)+(y_{1},y_{2},\dots)=(x_{1}+y_{1},x_{2}+y_{2},\dots) \\
\lambda(x_{1},x_{2},\dots)=(\lambda x_{1},\lambda x_{2},\dots)
\end{gather}
$$

可以验证，$\mathbb{F}^{\infty}$ 在如上定义的运算下构成了一个 $\mathbb{F}$-向量空间，其加法单位元是全为零的序列 $(0,0,\dots)$。

### Notation 1.15

设 $S$ 是集合，令 $\mathbb{F}^{S}$ 表示所有函数 $f\colon S\to \mathbb{F}$ 构成的集合。

在 $\mathbb{F}^{S}$ 上可以逐点定义加法与数乘：

$$
\begin{gather}
(f+g)(x)=f(x)+g(x) \\
(\lambda f)(x)=\lambda f(x)
\end{gather}
$$

对任意 $x \in S$。

同样，我们可以验证 $\mathbb{F}^{S}$ 在以上定义下构成了一个 $\mathbb{F}$-向量空间，其中加法单位元是定义为

$$
\begin{gather}
0(x)=0
\end{gather}
$$

的零函数 $0\colon S\to \mathbb{F}$。$f$ 的加法逆元是定义为

$$
\begin{gather}
(-f)(x)=-f(x)
\end{gather}
$$

的函数 $-f$。

前面我们定义的 $\mathbb{F}^{n}$ 和 $\mathbb{F}^{\infty}$ 都是 $\mathbb{F}^{S}$ 的特例。对于前者，我们有 $\mathbb{F}^{n}=\mathbb{F}^{\{ 1,2,\dots,n \}}$，因为每个 $(x_{1},\dots,x_{n})\in \mathbb{F}^{n}$ 都可以等同于一个函数 $x\colon \{ 1,2,\dots,n \}\to \mathbb{F}$，其将 $k$ 映射到 $x(k)=x_{k}$。对于后者，我们有 $\mathbb{F}^{\infty}=\mathbb{F}^{\{ 1,2,\dots \}}$，因为根据定义，一个序列就是一个从 $\mathbb{N}^{*}$ 到 $\mathbb{F}$ 的函数。

### Theorem 1.16

向量空间的加法单位元是唯一的。

#### Proof

假设 $0$ 和 $0'$ 都是加法单位元，则

$$
\begin{gather}
0=0+0'=0'+0=0'
\end{gather}
$$

故加法单位元是唯一的。

### Theorem 1.17

向量空间中的任何元素都有唯一的加法逆元。

#### Proof

假设 $w$ 和 $w'$ 都是 $v$ 的加法逆元，则

$$
\begin{gather}
w=w+(v+w')=(w+v)+w'=w'
\end{gather}
$$

故加法逆元是唯一的。

由于加法单位元和逆元都是唯一的，下面的符号就是合理的了。

### Notation 1.18

设 $v,w \in V$。

我们用 $-v$ 来表示 $v$ 的唯一加法逆元。我们定义 $V$ 上的减法为

$$
\begin{gather}
w-v=w+(-v)
\end{gather}
$$

### Notation 1.19

如果没有特别说明，我们将使用 $V$ 来表示一个 $\mathbb{F}$-向量空间。

下面我们将给出三个与分配律相关的结论。

### Theorem 1.20

对任意 $v \in V$ 有 $0v=0$。

#### Proof

注意，上面等式两边的 $0$ 是不同的：左边的 $0$ 的 $\mathbb{F}$ 中的加法单位，而右边的 $0$ 是 $V$ 中的加法单位。唯一将标量与向量联系起来的公理是分配律，因此我们必然要用到这一条件。

我们有

$$
\begin{gather}
0v=(0+0)v=0v+0v
\end{gather}
$$

两边加上 $0v$ 的加法逆元即证。

### Theorem 1.21

对任意 $a \in \mathbb{F}$ 有 $a 0=0$。

#### Proof

我们有

$$
\begin{gather}
a 0=a(0+0)=a 0+a 0
\end{gather}
$$

两边加上 $a 0$ 的加法逆元即可。

### Theorem 1.22

对任意 $v \in V$ 有 $(-1)v=-v$。

#### Proof

我们有

$$
\begin{gather}
v+(-1)v=(1+(-1))v=0v=0
\end{gather}
$$

由于 $v$ 的加法逆元是唯一的，因此 $(-1)v$ 就是 $v$ 的加法逆元 $-v$。

### Theorem 1.23

对任意 $v \in V$ 有 $-(-v)=v$。

#### Proof

我们有

$$
\begin{gather}
-(-v)=(-1)(-v)=(-1)((-1)v)=1v=v
\end{gather}
$$

# 1C Subspaces

### Definition 1.24 subspace 子空间

称 $U\subset V$ 是 $V$ 的一个子空间，如果 $U$ 也是一个向量空间，其上的加法、数乘以及加法单位元与 $V$ 相同。

以下定理表明，只要非空子集 $U$ 在加法和数乘下封闭，那么它就是一个子空间。

### Theorem 1.25

$U\subset V$ 是 $V$ 的一个子空间当且仅当 $U$ 满足以下条件：

1. $0 \in U$，
2. 如果 $u,w \in U$，则 $u+w \in U$，
3. 如果 $a \in \mathbb{F}$ 且 $u \in U$，则 $au \in U$。

#### Proof

如果 $U$ 是 $V$ 的子空间，那么显然它满足以上三个条件。

反之，如果 $U$ 满足三个条件，那么 (1) 保证了 $U$ 中有加法单位元，(2) 保证了加法在 $U$ 上有定义，(3) 保证了数乘在 $U$ 上有定义。

如果 $u \in U$，则 (3) 给出 $-u=(-1)u \in U$，因而 $U$ 中的元素有加法逆元。对于剩下的向量空间公理，由于它们在更大的空间 $V$ 上成立，因此它们也在 $U$ 上成立，这就完成了证明。

### Example 1.26

(a) 如果 $b \in \mathbb{F}$，则

$$
\begin{gather}
\{ (x_{1},x_{2},x_{3},x_{4}) \in \mathbb{F}^{4}: x_{3}=5x_{4}+b \}
\end{gather}
$$

是 $\mathbb{F}^{4}$ 的子空间当且仅当 $b=0$。

(b) 区间 $[0,1]$ 上的连续实值函数构成了 $\mathbb{R}^{[0,1]}$ 的子空间。

(c) $\mathbb{R}$ 上的可微实值函数构成了 $\mathbb{R}^{\mathbb{R}}$ 的子空间。

(d) 区间 $(0,3)$ 上满足 $f'(2)=b$ 的可微实值函数构成 $\mathbb{R}^{(0,3)}$ 的子空间，当且仅当 $b=0$。

(e) 所有极限为 $0$ 的复数序列构成了 $\mathbb{C}^{\infty}$ 的子空间。

(f) $\mathbb{R}^{2}$ 的所有子空间为 $\{ 0 \}$，通过原点的直线，以及 $\mathbb{R}^{2}$ 本身。$\mathbb{R}^{3}$ 的所有子空间为 $\{ 0 \}$，通过原点的直线，包含原点的平面，以及 $\mathbb{R}^{3}$ 本身。

## Sums of Subspaces

### Definition 1.27 sum of subspaces 子空间的和

设 $V_{1},\dots,V_{m}$ 是 $V$ 的子空间，定义它们的和为

$$
\begin{gather}
V_{1}+\dots+V_{m}=\{ v_{1}+\dots+v_{m}: v_{k}\in V_{k} \}
\end{gather}
$$

### Example 1.28

在本例中我们将展示求解子空间的和的一般步骤。

设

$$
\begin{gather}
U=\{ (x,x,y,y)\in \mathbb{F}^{4}: x,y \in \mathbb{F} \}, \quad W=\{ (x,x,x,y)\in \mathbb{F}^{4} : x,y \in \mathbb{F} \}
\end{gather}
$$

我们要给出 $U+W$ 的一个描述。首先我们取 $U,W$ 中的典型元素并相加

$$
\begin{gather}
(a,a,b,b)+(c,c,c,d)=(a+c,a+c,b+c,b+d)
\end{gather}
$$

这表明

$$
\begin{gather}
U+W \subset \{ (x,x,y,z) \in \mathbb{F}^{4}: x,y,z \in \mathbb{F} \}
\end{gather}
$$

要证明反向的包含，我们取 $(x,x,y,z)$，然后将其分解为

$$
\begin{gather}
(x,x,y,z)=(x,x,y,y)+(0,0,0,z-y)
\end{gather}
$$

其中第一个向量属于 $U$，第二个向量属于 $W$，从而有

$$
\begin{gather}
\{ (x,x,y,z) \in \mathbb{F}^{4}: x,y,z \in \mathbb{F} \}\subset U+W
\end{gather}
$$

因此

$$
\begin{gather}
U+W = \{ (x,x,y,z) \in \mathbb{F}^{4}: x,y,z \in \mathbb{F} \}
\end{gather}
$$

### Theorem 1.29

设 $V_{1},\dots,V_{m}$ 是 $V$ 的子空间，则 $V_{1}+\dots+V_{m}$ 是 $V$ 的子空间，并且它是包含 $V_{1},\dots,V_{m}$ 的最小子空间。

#### Proof

显然，$V_{1}+\dots+V_{m}$ 包含加法单位元 $0=0+\dots+0$，并且关于加法和数乘封闭，从而由 [[#Theorem 1.25]] 得 $V_{1}+\dots+V_{m}$ 是子空间。

此外，$V_{1},\dots,V_{m}$ 都包含在 $V_{1}+\dots+V_{m}$ 中，取 $v_{k}\in V_{k}$ 然后将其他 $v_{j}$ 取为 $0$ 即可。反之，任何包含 $V_{1},\dots,V_{m}$ 的子空间都必须包含它们的和，因为子空间对加法和数乘封闭，因此如果它包含 $v_{k}\in V_{k}$，那么它也包含 $v_{1}+\dots+v_{m}\in V_{1}+\dots+V_{m}$。这就完成了证明。

## Direct Sums

设 $V_{1},\dots,V_{m}$ 是 $V$ 的子空间，则 $V_{1}+\dots+V_{m}$ 的任意元素都可以表示为

$$
\begin{gather}
v=v_{1}+\dots+v_{m}
\end{gather}
$$

其中 $v_{k}\in V_{k}$。令我们感兴趣的，也是最为重要的情况是，和空间的元素有且仅有一种表示方法，我们有一个特别的名字来称呼这种情况。

### Definition 1.30 direct sum 直和

设 $V_{1},\dots,V_{m}$ 是 $V$ 的子空间。

称 $V_{1}+\dots+V_{m}$ 是一个直和，如果 $V_{1}+\dots+V_{m}$ 中的元素只有一种表示 $v_{1}+\dots+v_{m}$，其中 $v_{k}\in V_{k}$。

如果 $V_{1}+\dots+V_{m}$ 是一个直和，我们用 $V_{1}\oplus\dots \oplus V_{m}$ 来表示这个和。

### Example 1.31

(a) 设

$$
\begin{gather}
U=\{ (x,y,0) \in \mathbb{F}^{3}:x,y \in \mathbb{F} \}, \quad W=\{ (0,0,z) \in \mathbb{F}^{3}: z \in \mathbb{F} \}
\end{gather}
$$

则我们可以验证 $U+W$ 是一个直和，并且 $\mathbb{F}^{3}=U\oplus W$。

(b) 设 $V_{k}$ 表示 $\mathbb{F}^{n}$ 中仅第 $k$ 个坐标不为零的 $n$-元组构成的空间，则我们有

$$
\begin{gather}
\mathbb{F}^{n}=V_{1}\oplus \dots \oplus V_{n}
\end{gather}
$$

(c) 设

$$
\begin{gather}
V_{1}=\{ (x,y,0) \in \mathbb{F}^{3}:x,y \in \mathbb{F} \} \\
V_{2}=\{ (0,0,z)\in \mathbb{F}^{3}:z \in \mathbb{F} \} \\
V_{3}=\{ (0,y,y)\in \mathbb{F}^{3}: y \in \mathbb{F} \}
\end{gather}
$$

则 $\mathbb{F}^{3}=V_{1}+V_{2}=V_{3}$，但它不是一个直和：我们有

$$
\begin{gather}
(0,0,0)=(0,1,0)+(0,0,1)+(0,-1,-1)
\end{gather}
$$

并且

$$
\begin{gather}
(0,0,0)=(0,0,0)+(0,0,0)+(0,0,0)
\end{gather}
$$

这使得直和的唯一表示性对任意向量都不成立了：对 $v=v_{1}+v_{2}+v_{3}$，我们总可以将其写成 $v=v+0$，然后应用 $0$ 的那个非全零表示，得到 $v$ 的另一个表示。因此 $V_{1}+V_{2}+V_{3}$ 不是一个直和。

### Theorem 1.32

设 $V_{1},\dots,V_{m}$ 是 $V$ 的子空间，则 $V_{1}+\dots+V_{m}$ 是直和当且仅当将 $0$ 表示为 $v_{1}+\dots+v_{m}$ 的唯一方式是取每个 $v_{k}=0$。

#### Proof

首先设 $V_{1}+\dots+V_{m}$ 是直和，则 $0$ 的表示是唯一的，即令每个 $v_{k}=0$。

反之，如果 $0$ 的表示为 $v_{1}+\dots+v_{m}$ 的唯一方式是取 $v_{k}=0$。我们要证任意 $v \in V_{1}+\dots+V_{m}$ 都有唯一的表示。

设

$$
\begin{gather}
v=v_{1}+\dots+v_{m}=u_{1}+\dots+u_{m}
\end{gather}
$$

其中 $v_{k},u_{k}\in V_{k}$。则我们有

$$
\begin{gather}
0=(v_{1}-u_{1})+\dots+(v_{m}-u_{m})
\end{gather}
$$

且 $v_{k}-u_{k}\in V_{k}$。根据 $0$ 的唯一表示性质，我们就有 $v_{k}-u_{k}=0$，即 $v_{k}=u_{k}$。换句话说，$v$ 的表示是唯一的。

### Theorem 1.33

设 $U,W$ 是 $V$ 的子空间，则 $U+W$ 是直和当且仅当 $U\cap W=\{ 0 \}$。

#### Proof

设 $U+W$ 是直和，取 $v\in U\cap W$，则 $0=v+(-v)$，其中 $v \in U$，$-v \in W$。根据唯一表示性质，我们就有 $v=0$，从而 $U\cap W=\{ 0 \}$。

现在假设 $U\cap W=\{ 0 \}$，根据 [[#Theorem 1.32]]，我们只需证明 $0$ 有唯一表示。设 $u \in U,w \in W$ 满足

$$
\begin{gather}
0=u+w
\end{gather}
$$

则 $u=-w \in W$，且 $w=-u \in U$，从而 $u,w \in U\cap W=\{ 0 \}$，即 $u=w=0$，这就完成了证明。

需要注意的是，以上定理仅对两个子空间的和成立。对于三个以上的子空间，仅检测子空间两两之间的交集为 $\{ 0 \}$ 是不够的，参考 [[#Example 1.31]](c)。