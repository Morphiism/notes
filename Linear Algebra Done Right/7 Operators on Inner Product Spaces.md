在内积空间上我们可以对其上的算子做最为精细化的研究：利用谱定理，我们可以给出内积空间上自伴算子和正规算子的完整描述。在这之后，我们将用这些结果来研究正算子（半正定算子）以及酉算子（幺正算子）。最后，我们以奇异值分解（SVD）以及极分解作为结尾。

本章中我们假设 $V,W$ 是 $\mathbb{F}$ 上的非零有限维内积空间。

# 7A Self-Adjoint and Normal Operators

## Adjoints

### Definition 7.1 adjoint 伴随

设 $T \in L(V,W)$，$T$ 的伴随映射 $T^{*}\colon W\to V$ 定义为

$$
\begin{gather}
\langle Tv,w \rangle =\langle v,T^{*}w \rangle  \quad (v \in V,w \in W)
\end{gather}
$$

首先我们需要证明以上定义是合理的。设 $T \in L(V,W)$，固定 $w \in W$，则映射

$$
\begin{gather}
v\mapsto \langle Tv,w \rangle 
\end{gather}
$$

是一个线性泛函，其依赖于 $T$ 和 $w$。根据 Riesz 表示定理，存在唯一的一个向量使得 $\langle Tv,w \rangle$ 等于 $v$ 与它的内积，我们就把这个向量定义为 $T^{*}w$。

另外需要注意，在 [[#Definition 7.1 adjoint 伴随]] 中，等式左边的是 $W$ 上的内积，右边是 $V$ 上的内积。在不致歧义的情况下，我们可以用同一个符号来同时表示 $V,W$ 上的内积。

### Example 7.2

固定 $u \in V,x \in W$，定义 $T \in L(V,W)$ 为

$$
\begin{gather}
Tv=\langle v,u \rangle x
\end{gather}
$$

要计算 $T^{*}$，我们设 $v \in V$ 且 $w \in W$，有

$$
\begin{align}
\langle Tv,w \rangle &= \langle \langle v,u \rangle x,w \rangle  \\
&=\langle v,u \rangle \langle x,w \rangle  \\
&=\langle v,\langle w,x \rangle u \rangle 
\end{align}
$$

从而

$$
\begin{gather}
T^{*}w=\langle w,x \rangle u
\end{gather}
$$

### Theorem 7.3

如果 $T \in L(V,W)$，那么 $T^{*}\in L(W,V)$。

#### Proof

设 $T \in L(V,W)$，$w_{1},w_{2}\in W,v \in V$，则

$$
\begin{align}
\langle Tv,w_{1}+w_{2} \rangle &= \langle Tv,w_{1} \rangle +\langle Tv,w_{2} \rangle  \\
&= \langle v,T^{*}w_{1} \rangle +\langle v,T^{*}w_{2} \rangle  \\
&=\langle v,T^{*}w_{1}+T^{*}w_{2} \rangle 
\end{align}
$$

因此 $T^{*}(w_{1}+w_{2})=T^{*}w_{1}+T^{*}w_{2}$。

同理，设 $\lambda \in \mathbb{F},w \in W$，则

$$
\begin{align}
\langle Tv,\lambda w \rangle &= \overline{\lambda}\langle Tv,w \rangle  \\
&=\overline{\lambda}\langle v,T^{*}w \rangle  \\
&=\langle v,\lambda T^{*}w \rangle 
\end{align}
$$

即证 $T^{*}(\lambda w)=\lambda T^{*}w$。

### Theorem 7.4

设 $T \in L(V,W)$，则

1. 对 $S \in L(V,W)$ 有 $(S+T)^{*}=S^{*}+T^{*}$，
2. 对 $\lambda \in \mathbb{F}$ 有 $(\lambda T)^{*}=\overline{\lambda}T^{*}$，
3. $(T^{*})^{*}=T$，
4. 设 $U$ 是有限维内积空间，对 $S \in L(W,U)$ 有 $(ST)^{*}=T^{*}S^{*}$，
5. $I^{*}=I$，其中 $I$ 是恒等算子，
6. 如果 $T$ 可逆，那么 $T^{*}$ 可逆，且 $(T^{*})^{-1}=(T^{-1})^{*}$。

#### Proof

设 $v \in V,w \in W$。

(1) 设 $S \in L(V,W)$，则

$$
\begin{align}
\langle (S+T)v,w \rangle &= \langle Sv,w \rangle +\langle Tv,w \rangle  \\
&=\langle v,S^{*}w \rangle +\langle v,T^{*}w \rangle  \\
&=\langle v,S^{*}w+T^{*}w \rangle 
\end{align}
$$

即证 $(S+T)^{*}w=S^{*}w+T^{*}w$。

(2) 设 $\lambda \in \mathbb{F}$，则

$$
\begin{align}
\langle (\lambda T)v,w \rangle &= \lambda \langle Tv,w \rangle  \\
&= \lambda \langle v,T^{*}w \rangle  \\
&= \langle v,\overline{\lambda}T^{*}w \rangle 
\end{align}
$$

即证 $(\lambda T)^{*}w=\overline{\lambda}T^{*}w$。

(3) 我们有

$$
\begin{gather}
\langle T^{*}w,v \rangle =\overline{\langle v,T^{*}w \rangle }=\overline{\langle Tv,w \rangle }=\langle w,Tv \rangle 
\end{gather}
$$

因此 $(T^{*})^{*}v=Tv$。

(4) 设 $S \in L(W,U)$ 且 $u \in U$，则

$$
\begin{gather}
\langle (ST)v,u \rangle =\langle S(Tv),u \rangle =\langle Tv,S^{*}u \rangle =\langle v,T^{*}S^{*}u \rangle 
\end{gather}
$$

即 $(ST)^{*}u=T^{*}S^{*}u$。

(5) 设 $u \in V$，则

$$
\begin{gather}
\langle Iu,v \rangle =\langle u,v \rangle 
\end{gather}
$$

故 $I^{*}v=v$，即 $I^{*}=I$。

(6) 设 $T$ 可逆，则 $T^{-1}T=TT^{-1}=I$，等式两边取伴随，利用 (4) 即得

$$
\begin{gather}
T^{*}(T^{-1})^{*}=(T^{-1})^{*}T^{*}=I^{*}=I
\end{gather}
$$

因此 $(T^{-1})^{*}$ 是 $T^{*}$ 的逆算子，即 $(T^{-1})^{*}=(T^{*})^{-1}$。

### Theorem 7.5

设 $T \in L(V,W)$，则

1. $\ker T^{*}=(\operatorname{range}T)^{\perp}$，
2. $\operatorname{range}T^{*}=(\ker T)^{\perp}$，
3. $\ker T=(\operatorname{range}T^{*})^{\perp}$，
4. $\operatorname{range}T=(\ker T^{*})^{\perp}$。

#### Proof

我们首先来证明 (1)。设 $w \in W$，则 $w \in \ker T^{*}$ 当且仅当 $T^{*}w=0$，当且仅当对 $v \in V$ 有 $\langle Tv,w \rangle=\langle v,T^{*}w \rangle=0$，当且仅当 $w \in (\operatorname{range}T)^{\perp}$。

对 (1) 两边取正交补，利用 $(U^{\perp})^{\perp}=U$ 可得 (4)。在 (1) 中用 $T^{*}$ 替换 $T$，并应用 $(T^{*})^{*}=T$ 即得 (3)。最后，在 (4) 中用 $T^{*}$ 替换 $T$ 即得 (2)。

### Definition 7.6 conjugate transpose 共轭转置

一个 $m\times n$ 矩阵 $A$ 的共轭转置 $A^{*}$ 是一个 $n\times m$ 矩阵，定义为

$$
\begin{gather}
(A^{*})_{j,k}=\overline{A}_{k,j}
\end{gather}
$$

下面的定理展示了如何从 $T$ 的矩阵得到 $T^{*}$ 的矩阵。注意：以下定理仅对标准正交基成立，这就是说，对于一般的基，$T^{*}$ 的矩阵不一定就是 $T$ 的矩阵的共轭转置。

### Theorem 7.7

设 $T \in L(V,W)$，$e_{1},\dots,e_{n}$ 是 $V$ 的标准正交基，$f_{1},\dots,f_{m}$ 是 $W$ 的标准正交基，则在这些基下我们有

$$
\begin{gather}
\mathcal{M}(T^{*})=\mathcal{M}(T)^{*}
\end{gather}
$$

#### Proof

根据矩阵的定义，$\mathcal{M}(T)$ 的第 $k$ 列是将 $Te_{k}$ 写成 $f_{1},\dots,f_{m}$ 的线性组合的系数。由于 $f_{1},\dots,f_{m}$ 是标准正交基，因此

$$
\begin{gather}
Te_{k}=\langle Te_{k},f_{1} \rangle f_{1}+\dots+\langle Te_{k},f_{m} \rangle f_{m}
\end{gather}
$$

从而

$$
\begin{gather}
\mathcal{M}(T)_{j,k}=\langle Te_{k},f_{j} \rangle 
\end{gather}
$$

在以上论证中将 $T$ 替换为 $T^{*}$，并交换 $e_{1},\dots,e_{n}$ 与 $f_{1},\dots,f_{m}$，则我们有

$$
\begin{gather}
\mathcal{M}(T^{*})_{k,j}=\langle T^{*}f_{j},e_{k} \rangle =\overline{\langle e_{k},T^{*}f_{j} \rangle }=\overline{\langle Te_{k},f_{j} \rangle }= \overline{\mathcal{M}(T)}_{j,k}
\end{gather}
$$

即证 $\mathcal{M}(T^{*})=\mathcal{M}(T)^{*}$。

在上一章中我们证明了 Riesz 表示定理，它提供了从内积空间 $V$ 到它的对偶空间 $V^{*}$ 的一个一一对应。如果我们将 $V$ 与 $V^{*}$ 等同，那么子集 $U$ 的正交补 $U^{\perp}$ 就对应于 $U$ 的零化子 $U^{0}$。这一点也可以从它们的维数公式上看出：如果 $U$ 是 $V$ 的子空间，那么

$$
\begin{gather}
\dim U^{\perp}=\dim U^{0}=\dim V-\dim U
\end{gather}
$$

与此同时，设 $T \in L(V,W)$，在 $V$ 与 $V^{*}$ 的这种等同下，它的伴随映射 $T^{*}$ 也与它的对偶映射 $T'\colon W^{*}\to V^{*}$ 等同。更精确地说，我们有：

### Theorem 7.8

设 $T \in L(V,W)$，$T'$ 为其对偶，$T^{*}$ 为其伴随，则对任意 $w \in W$ 有

$$
\begin{gather}
T'(\varphi_{w})=\varphi_{T^{*}w}
\end{gather}
$$

其中 $\varphi_{w} \in W^{*}$ 定义为 $\varphi_{w}(v)=\langle v,w \rangle$。

#### Proof

等式两边都是 $V$ 上的线性泛函。设 $v \in V$，则

$$
\begin{gather}
T'(\varphi_{w})v=\varphi_{w}(Tv)=\langle Tv,w \rangle =\langle v,T^{*}w \rangle =\varphi_{T^{*}w}v
\end{gather}
$$

即证 $T'(\varphi_{w})=\varphi_{T^{*}w}$。

在这种等同的意义下，$\ker T^{*}$ 和 $\operatorname{range}T^{*}$ 的公式就与 $\ker T'$ 和 $\operatorname{range}T'$ 的公式相同了。此外，$T^{*}$ 的矩阵公式也可类比于 $T'$ 的矩阵公式，其中前者是共轭转置，而后者是转置。

## Self-Adjoint Operators

### Definition 7.9 self-adjoint 自伴的

称 $T \in L(V)$ 是自伴的，如果 $T^{*}=T$。

我们可以根据 $T$ 的矩阵 $A$ 来判断它是否是自伴算子。如果 $\mathbb{F}=\mathbb{R}$，那么 $A^{*}=A^{T}$，从而如果 $A$ 是实对称矩阵，那么 $T$ 是自伴的。如果 $\mathbb{F}=\mathbb{C}$，那么如果 $A^{*}=A$（这种矩阵称为 Hermitian 矩阵），那么 $T$ 是自伴的。

一种有用的视角是将取伴随 $T\mapsto T^{*}$ 类比于 $\mathbb{C}$ 上的共轭 $z\mapsto \overline{z}$。于是，在这种角度下，一个自伴算子就类似于一个实数。我们后面将看到，自伴算子有许多类似于实数的性质。

### Theorem 7.10

自伴算子的所有特征值都是实数。

#### Proof

设 $T \in L(V)$ 是自伴算子，$\lambda$ 是 $T$ 的特征值，$v$ 是对应的特征向量，则

$$
\begin{gather}
\lambda \lVert v \rVert ^{2}=\langle \lambda v,v \rangle =\langle Tv,v \rangle =\langle v,Tv \rangle =\langle v,\lambda v \rangle =\overline{\lambda} \lVert v \rVert ^{2}
\end{gather}
$$

由于 $v\neq 0$，因此 $\lambda=\overline{\lambda}$，即 $\lambda$ 是实数。

### Theorem 7.11

设 $V$ 是复内积空间，$T \in L(V)$，则对任意 $v \in V$ 有 $\langle Tv,v \rangle=0$ 当且仅当 $T=0$。

#### Proof

$T=0$ 蕴含 $\langle Tv,v \rangle=0$ 是显然的。下面我们要证明反向的蕴含。

应用极化恒等式可得

$$
\begin{align}
\langle Tu,w \rangle &= \frac{\langle T(u+w),u+w \rangle -\langle T(u-w),u-w \rangle }{4} \\
&+ i \frac{\langle T(u+iw),u+iw \rangle -\langle T(u-iw),u-iw \rangle }{4}
\end{align}
$$

其中右侧每一项都是 $\langle Tv,v \rangle$ 的形式。于是，如果对任意 $v$ 有 $\langle Tv,v \rangle=0$，那么对任意 $u,w$ 有 $\langle Tu,w \rangle=0$。取 $w=Tu$ 即得 $Tu=0$，从而 $T=0$。

以上定理对实内积空间不成立：取 $T$ 为 $\mathbb{R}^{2}$ 上的 $90^{\circ}$ 旋转算子，则 $T\neq 0$ 但 $\langle Tv,v \rangle=0$。

### Theorem 7.12

设 $V$ 是复内积空间，$T \in L(V)$，则 $T$ 是自伴算子当且仅当对任意 $v \in V$ 有 $\langle Tv,v \rangle \in \mathbb{R}$。

#### Proof

如果 $v \in V$，则

$$
\begin{gather}
\langle T^{*}v,v \rangle =\overline{\langle v,T^{*}v \rangle }=\overline{\langle Tv,v \rangle }
\end{gather}
$$

现在我们有等价链：$T$ 自伴当且仅当 $T-T^{*}=0$，当且仅当对 $v \in V$ 有 $\langle (T-T^{*})v,v \rangle=\langle Tv,v \rangle-\langle T^{*}v,v \rangle=0$，当且仅当 $\langle Tv,v \rangle=\overline{\langle Tv,v \rangle}$，即 $\langle Tv,v \rangle\in \mathbb{R}$。

同样，以上定理对实内积空间也不成立，因为在实空间上总有 $\langle Tv,v \rangle \in \mathbb{R}$，但并非所有算子都是自伴的。

在 [[#Theorem 7.11]] 中我们提到，实内积空间上的算子可以满足 $\langle Tv,v \rangle=0$ 而 $T\neq 0$。不过，如果我们将条件加强为 $T$ 自伴，那么这种情况就不会发生。从中我们也可以看到一种普遍模式：要得到相同的结论，实内积空间上的条件通常要更强。这种模式在后续的谱定理中也有体现。

### Theorem 7.13

设 $V$ 是实内积空间，$T \in L(V)$ 是自伴算子，则对 $v \in V$ 有 $\langle Tv,v \rangle=0$ 当且仅当 $T=0$。

#### Proof

根据自伴性以及实内积的对称性，我们有

$$
\begin{gather}
\langle Tu,w \rangle =\langle u,Tw \rangle =\langle Tw,u \rangle 
\end{gather}
$$

从而我们可以证明实极化恒等式

$$
\begin{gather}
\langle Tu,w \rangle =\frac{\langle T(u+w),u+w \rangle -\langle T(u-w),u-w \rangle }{4}
\end{gather}
$$

之后的证明与 [[#Theorem 7.11]] 相同。

## Normal Operators

### Definition 7.14 normal 正规的

称 $T \in L(V)$ 是正规的，如果 $TT^{*}=T^{*}T$。

任何自伴算子都是正规的，因为自伴算子满足 $T^{*}=T$，而 $T$ 与自身显然是交换的。

### Theorem 7.15

设 $T \in L(V)$，则 $T$ 是正规算子当且仅当对 $v \in V$ 有 $\lVert Tv \rVert=\lVert T^{*}v \rVert$。

#### Proof

我们有等价链：

$T$ 正规当且仅当 $TT^{*}-T^{*}T=0$，当且仅当对 $v \in V$ 有

$$
\begin{gather}
\langle (TT^{*}-T^{*}T)v,v \rangle =0
\end{gather}
$$

当且仅当

$$
\begin{gather}
\langle T^{*}v,T^{*}v \rangle =\langle TT^{*}v,v \rangle=\langle T^{*}Tv,v \rangle =\langle Tv,Tv \rangle 
\end{gather}
$$

即 $\lVert T^{*}v \rVert=\lVert Tv \rVert$。

### Theorem 7.16

设 $T \in L(V)$ 是正规算子，则

1. $\ker T=\ker T^{*}$，
2. $\operatorname{range}T=\operatorname{range}T^{*}$，
3. $V=\ker T\oplus \operatorname{range}T$，
4. 对任意 $\lambda \in \mathbb{F}$，$T-\lambda I$ 是正规算子，
5. 如果 $v \in V$ 且 $\lambda \in \mathbb{F}$，则 $Tv=\lambda v$ 当且仅当 $T^{*}v=\overline{\lambda}v$。

这就是说，正规算子与其伴随拥有相同的特征向量，并且它们的特征值满足共轭关系。

#### Proof

(1) 设 $v \in V$，则 $v \in \ker T$ 当且仅当 $\lVert Tv \rVert=0$，当且仅当 $\lVert T^{*}v \rVert=0$，当且仅当 $v \in \ker T^{*}$。

(2) 我们有

$$
\begin{gather}
\operatorname{range}T=(\ker T^{*})^{\perp}=(\ker T)^{\perp}=\operatorname{range}T^{*}
\end{gather}
$$

(3) 我们有

$$
\begin{gather}
V=\ker T\oplus (\ker T)^{\perp}=\ker T\oplus \operatorname{range}T^{*}=\ker T\oplus \operatorname{range}T
\end{gather}
$$

(4) 设 $\lambda \in \mathbb{F}$，则

$$
\begin{align}
(T-\lambda I)(T-\lambda I)^{*} &= (T-\lambda I)(T^{*}-\overline{\lambda}I) \\
&=TT^{*}-\overline{\lambda}T-\lambda T^{*}+\lvert \lambda \rvert ^{2} \\
&=T^{*}T-\overline{\lambda}T-\lambda T^{*}+\lvert \lambda \rvert ^{2} \\
&=(T^{*}-\overline{\lambda}I)(T-\lambda I) \\
&=(T-\lambda I)^{*}(T-\lambda I)
\end{align}
$$

因此 $T-\lambda I$ 的正规的。

(5) 根据 (4)，我们有

$$
\begin{gather}
\lVert (T-\lambda I)v \rVert=\lVert (T-\lambda I)^{*}v \rVert=\lVert (T^{*}-\overline{\lambda}I)v \rVert   
\end{gather}
$$

因此 $(T-\lambda I)v=0$ 当且仅当 $(T^{*}-\overline{\lambda}I)v=0$。

### Theorem 7.17

设 $T \in L(V)$ 是正规算子，则 $T$ 的对应于不同特征值的特征向量正交。

#### Proof

设 $\alpha,\beta$ 是 $T$ 的不同特征值，对应的特征向量为 $u,v$，则 $Tu=\alpha u$ 且 $Tv=\beta v$。根据 [[#Theorem 7.16]](5) 我们有 $T^{*}v=\overline{\beta}v$，故

$$
\begin{align}
(\alpha-\beta)\langle u,v \rangle &= \langle \alpha u,v \rangle -\langle u,\overline{\beta}v \rangle  \\
&=\langle Tu,v \rangle -\langle u,T^{*}v \rangle  \\
&=0
\end{align}
$$

由于 $\alpha\neq\beta$，故 $\langle u,v \rangle$，即 $u,v$ 正交。

### Theorem 7.18

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则 $T$ 正规当且仅当存在交换的自伴算子 $A,B$ 使得 $T=A+iB$。

从 $L(V)$ 与 $\mathbb{C}$ 的类比来看，其中我们将自伴算子类比于实数，则以上定理表明一个正规算子可以类比于一个复数，其实部和虚部都是自伴算子。

#### Proof

设 $T$ 是正规的。令

$$
\begin{gather}
A=\frac{T+T^{*}}{2}, \quad B=\frac{T-T^{*}}{2i}
\end{gather}
$$

则 $A,B$ 是自伴的，$T=A+iB$，且

$$
\begin{gather}
AB-BA=\frac{T^{*}T-TT^{*}}{2i}=0
\end{gather}
$$

即 $AB$ 交换。

反之，设 $T=A+iB$，其中 $A,B$ 是交换的自伴算子。则 $T^{*}=A-iB$，从而

$$
\begin{gather}
T^{*}T-TT^{*}=2i(AB-BA)=0
\end{gather}
$$

即 $T$ 是正规的。

当 $\mathbb{F}=\mathbb{R}$ 时，以上定理没有意义。然而，在上面的证明中可以找到一些通用的结构，它能够引导我们给出实内积空间上正规算子的一个分解定理。

注意到，以上论证中的一个关键点是算子 $iB$ 经过伴随后成为了 $-iB$，这是一种类似于自伴性的性质，只是更改了一个符号。而在任意内积空间中，我们都可以做分解

$$
\begin{gather}
T=\frac{T+T^{*}}{2}+\frac{T-T^{*}}{2}
\end{gather}
$$

其中右侧第二项就满足上面我们所说的性质。

### Theorem 7.19

设 $\mathbb{F}=\mathbb{R}$，一个 $B \in L(V)$ 称为是反对称的（skew）如果

$$
\begin{gather}
B^{*}=-B
\end{gather}
$$

设 $T \in L(V)$，则 $T$ 是正规的当且仅当存在交换的算子 $A,B$ 使得 $A$ 是对称的（自伴的），$B$ 是反对称的，且 $T=A+B$。

以上定理的证明可以逐字逐句地从 [[#Theorem 7.18]] 中移动过来，只需在其中将 $iB$ 替换为 $B$ 即可。

# 7B Spectral Theorem

本节我们来研究内积空间上最为重要的问题之一：算子的相似对角化。我们说一个算子 $T$ 可对角化，就是说它在 $V$ 的某个基下有对角矩阵，这等价于 $V$ 有一个由 $T$ 的特征向量构成的基。在内积空间中，我们可以更进一步，问这个基是否是标准正交的。

本节的核心定理：谱定理指出，实内积空间上的自伴算子以及复内积空间上的正规算子都具有这种优良的性质：它们在 $V$ 的标准正交基下有对角矩阵。后续我们将看到，每个 $T \in L(V)$ 都可以分解为一个自伴算子与一个正规算子的乘积，因此这就等同于说我们能够完成内积空间上所有算子的描述。

## Real Spectral Theorem

### Lemma 7.20

设 $T \in L(V)$ 是自伴算子，$b,c \in \mathbb{R}$ 满足 $b^{2}<4c$，则

$$
\begin{gather}
T^{2}+bT+c
\end{gather}
$$

是一个可逆算子。

#### Proof

设 $v \in V$ 满足 $v\neq 0$，则

$$
\begin{align}
\langle (T^{2}+bT+c)v,v \rangle &= \langle Tv,Tv \rangle +b\langle Tv,v \rangle +c\langle v,v \rangle  \\
&\geq \lVert Tv \rVert ^{2}+\lvert b \rvert \lVert Tv \rVert \lVert v \rVert +c \lVert v \rVert ^{2} \\
&=\left( \lVert Tv \rVert -\frac{\lvert b \rvert \lVert v \rVert }{2} \right)^{2}+\left( c - \frac{b^{2}}{4} \right)\lVert v \rVert ^{2} \\
&> 0
\end{align}
$$

因此 $(T^{2}+bT+c)v\neq 0$，从而 $T^{2}+bT+c$ 是单射，在有限维空间上等价于可逆。

### Theorem 7.21

设 $T \in L(V)$ 自伴，则 $T$ 的极小多项式具有形式 $(z-\lambda_{1})\cdots(z-\lambda_{m})$，其中 $\lambda_{1},\dots,\lambda_{m}\in \mathbb{R}$。

#### Proof

首先设 $\mathbb{F}=\mathbb{C}$。由于极小多项式的零点恰是 $T$ 的特征值，又因为自伴算子的特征值是实数，于是根据代数基本定理可知 $T$ 的极小多项式具有定理中的形式。

下面设 $\mathbb{F}=\mathbb{R}$。根据 $\mathbb{R}$ 上多项式的分解定理，可知 $T$ 的极小多项式具有形式

$$
\begin{gather}
(z-\lambda_{1})\cdots(z-\lambda_{m})(z^{2}+b_{1}z+c_{1})\cdots(z^{2}+b_{N}z+c_{N})
\end{gather}
$$

其中 $\lambda_{k}\in \mathbb{R}$ 且 $b_{k},c_{k}\in \mathbb{R}$ 满足 $b_{k}^{2}<4c_{k}$。于是

$$
\begin{gather}
(T-\lambda_{1}I)\cdots (T-\lambda_{m}I)(T^{2}+b_{1}T+c_{1})\cdots(T^{2}+b_{N}T+c_{N})=0
\end{gather}
$$

[[#Lemma 7.20]] 表明 $T^{2}+b_{k}T+c_{k}$ 可逆，因此如果 $N>0$，那么我们可以在上面的等式中两边乘以 $(T^{2}+b_{N}T+c_{N})^{-1}$，而得到一个次数更小的零化多项式，这与极小多项式的定义矛盾。因此 $N=0$，从而 $T$ 的极小多项式具有形式 $(z-\lambda_{1})\cdots(z-\lambda_{m})$。这就完成了证明。

以上定理表明自伴算子总有特征值，而以下的定理表明我们还可以找到足够的特征向量来构成一个基。

### Theorem 7.22 (实谱定理)

设 $\mathbb{F}=\mathbb{R}$ 且 $T \in L(V)$，则以下命题等价。

1. $T$ 是自伴算子。
2. $T$ 关于 $V$ 的某个标准正交基有对角矩阵。
3. $V$ 有一个由 $T$ 的特征向量构成的标准正交基。

#### Proof

显然 (2) 和 (3) 是等价的。下面首先设 (1) 成立。根据 [[6 Inner Product Spaces#Theorem 6.28]] 以及 [[#Theorem 7.21]]，我们可知 $T$ 在 $V$ 的某个标准正交基下有上三角矩阵。又由于 $T$ 是自伴的，因此 $T$ 在标准正交基下的矩阵一定是对称的，故 $T$ 的上三角矩阵实际上是一个对角矩阵，即 (2) 成立。

现在设 (2) 成立，则 $T$ 在 $V$ 的标准正交基下有对角矩阵。对角矩阵是对称的，因此 $\mathcal{M}(T^{*})=\mathcal{M}(T)$，即 $T$ 是自伴的。

## Complex Spectral Theorem

### Theorem 7.23 (复谱定理)

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则以下命题等价。

1. $T$ 是正规算子。
2. $T$ 关于 $V$ 的某个标准正交基有对角矩阵。
3. $V$ 有一个由 $T$ 的特征向量构成的标准正交基。

#### Proof

(2) 与 (3) 的等价是显然的。设 (1) 成立，根据 [[6 Inner Product Spaces#Corollary 6.29 (Schur)]]，存在 $V$ 的标准正交基 $e_{1},\dots,e_{n}$ 使得 $T$ 有上三角矩阵

$$
\begin{gather}
\mathcal{M}(T)=\begin{pmatrix}
a_{1,1} & \cdots & a_{1,n} \\
 & \ddots & \vdots \\
0 &  & a_{n,n}
\end{pmatrix}
\end{gather}
$$

我们来证明 $\mathcal{M}(T)$ 实际上是一个对角矩阵。

由于 $T$ 正规，因此 $\lVert Tv \rVert=\lVert T^{*}v \rVert$。取 $v=e_{1}$ 得到

$$
\begin{gather}
\lVert Te_{1} \rVert ^{2}=\lvert a_{1,1} \rvert ^{2}=\lvert a_{1,1} \rvert ^{2}+\dots+\lvert a_{1,n} \rvert ^{2}=\lVert T^{*}e_{1} \rVert ^{2}
\end{gather}
$$

因此 $\mathcal{M}(T)$ 的第一行除了 $a_{1,1}$ 外均为零。接下来取 $v=e_{2}$，则有

$$
\begin{gather}
\lVert Te_{2} \rVert ^{2}=\lvert a_{2,2} \rvert ^{2}=\lvert a_{2,2} \rvert ^{2}+\dots+\lvert a_{2,n} \rvert ^{2}=\lVert T^{*}e_{2} \rVert ^{2}
\end{gather}
$$

于是 $\mathcal{M}(T)$ 的第二行除了 $a_{2,2}$ 外也均为零。以此类推，我们可以证明 $\mathcal{M}(T)$ 除了对角线元素外其余元素均为零，换句话说，$\mathcal{M}(T)$ 是一个对角矩阵。

反之，设 (2) 成立，则 $\mathcal{M}(T)$ 是对角矩阵，从而其共轭转置 $\mathcal{M}(T^{*})$ 也是对角矩阵。对角矩阵的乘法显然是交换的，因此 $T$ 正规。

# 7C Positive Operators

### Definition 7.24 positive (semidefinite) operator 正算子（半正定算子），positive definite operator 正定算子

称 $T \in L(V)$ 是一个正算子（或半正定算子），如果 $T$ 是自伴的，且对任意 $v \in V$ 有

$$
\begin{gather}
\langle Tv,v \rangle \geq 0
\end{gather}
$$

称 $T \in L(V)$ 是正定算子，如果 $T$ 是半正定的，并且 $\langle Tv,v \rangle=0$ 当且仅当 $v=0$。

根据 [[#Theorem 7.12]]，在复内积空间上，以上定义中的自伴性可以去掉。

### Example 7.25

(a) 设 $A \in \mathbb{R}^{n,n}$，取 $\mathbb{R}^{n}$ 上的 Euclidean 内积并将 $v \in \mathbb{R}^{n}$ 与列向量等同，则

$$
\begin{gather}
\langle Av,v \rangle =v^{T}Av
\end{gather}
$$

右侧是表达式称为一个二次型。如果对任意 $v$ 有 $v^{T}Av\geq 0$，我们就说该二次型是半正定的，并且矩阵 $A$ 是一个半正定矩阵。类似地，如果它满足 $v^{T}Av=0$ 当且仅当 $v=0$，就称它是一个正定二次型，且 $A$ 是一个正定矩阵。

(b) 设 $U$ 是 $V$ 的子空间，则正交投影 $P_{U}$ 是一个正算子。

(c) 如果 $T \in L(V)$ 自伴，$b,c \in \mathbb{R}$ 满足 $b^{2}<4c$，那么 $T^{2}+bT+c$ 是一个正定算子，如 [[#Lemma 7.20]] 的证明所示。

### Definition 7.26 square root 平方根

称算子 $R$ 是 $T$ 的一个平方根，如果 $R^{2}=T$。

正如自伴算子可以类比于实数，正算子可以类比于非负实数。特别地，一个复数 $z$ 是非负实数当且仅当它有非负的平方根，对应于性质 (4)；$z$ 是非负实数当且仅当它有实的平方根，对应于性质 (5)；$z$ 是非负实数当且仅当存在 $w \in \mathbb{C}$ 使得 $z=\overline{w}w$，对应于性质 (6)。

### Theorem 7.27

设 $T \in L(V)$，则以下命题等价。

1. $T$ 是正算子。
2. $T$ 是自伴的且 $T$ 的所有特征值非负。
3. 在 $V$ 的某个标准正交基下 $T$ 有对角矩阵，且对角线上的元素都是非负实数。
4. $T$ 有正的平方根。
5. $T$ 有自伴的平方根。
6. 存在 $R \in L(V)$ 使得 $T=R^{*}R$。

#### Proof

我们将证明 $1\implies 2\implies 3\implies 4\implies 5\implies 6\implies 1$。

设 (1) 成立，则根据定义有 $T$ 是自伴的。设 $\lambda$ 是 $T$ 的特征值，$v$ 是对应的特征向量，则

$$
\begin{gather}
\langle Tv,v \rangle =\langle \lambda v,v \rangle =\lambda \langle v,v \rangle \geq 0
\end{gather}
$$

从而 $\lambda\geq 0$，即证 (2)。

现在设 (2) 成立，根据谱定理，存在 $V$ 的标准正交基使得 $T$ 有对角矩阵，其对角线元素恰是 $T$ 的特征值，因而都是非负实数。

现设 (3) 成立，假设 $T$ 在标准正交基 $e_{1},\dots,e_{n}$ 下有对角矩阵，对角线元素 $\lambda_{1},\dots,\lambda_{n}$ 非负。我们定义 $R \in L(V)$ 为

$$
\begin{gather}
R e_{k}=\sqrt{ \lambda_{k} } e_{k}
\end{gather}
$$

则 $R^{2}e_{k}=\lambda_{k}e_{k}=Te_{k}$，故 $R^{2}=T$。此外，容易验证 $R$ 是正算子：

$$
\begin{align}
\langle Rv,v \rangle &=\langle R(a_{1}e_{1}+\dots+a_{n}e_{n}),a_{1}e_{1}+\dots+a_{n}e_{n} \rangle  \\
&=\langle a_{1}\sqrt{ \lambda_{1} }e_{1}+\dots+a_{n}\sqrt{ \lambda_{n} }e_{n},a_{1}e_{1}+\dots+a_{n}e_{n} \rangle  \\
&=\lvert a_{1} \rvert ^{2}\sqrt{ \lambda_{1} }+\dots+\lvert a_{n} \rvert ^{2}\sqrt{ \lambda_{n} }\geq 0
\end{align}
$$

即证 (4)。显然 (4) 蕴含 (5)。

设 (5) 成立，则存在自伴算子 $R \in L(V)$ 使得 $T=R^{2}$，由于 $R=R^{*}$，故 $T=R^{*}R$。

最后设 (6) 成立，则有 $R \in L(V)$ 使得 $T=R^{*}R$，则

$$
\begin{gather}
T^{*}=R^{*}(R^{*})^{*}=R^{*}R=T
\end{gather}
$$

因此 $T$ 是自伴的。此外，对 $v \in V$ 有

$$
\begin{gather}
\langle Tv,v \rangle =\langle R^{*}Rv,v \rangle =\langle Rv,Rv \rangle \geq 0
\end{gather}
$$

因此 $T$ 是正算子，这就完成了证明。

### Theorem 7.28

$V$ 上的任何正算子都有唯一的正平方根。

注意，正算子可以有无穷多个平方根，以上定理只是说这些平方根中只有一个是正算子。

#### Proof

设 $T \in L(V)$ 是正算子，$v \in V$ 是 $T$ 的一个特征向量，从而有 $\lambda\geq 0$ 使得 $Tv=\lambda v$。

设 $R$ 是 $T$ 的正平方根，我们要证 $Rv=\sqrt{ \lambda }v$，从而由于 $T$ 的特征向量构成了 $V$ 的一个标准正交基，$R$ 的值完全由其在特征向量上的取值决定。

谱定理给出了一个由 $R$ 的特征向量构成的标准正交基 $e_{1},\dots,e_{n}$，其对应的特征值非负，因此存在 $\lambda_{1},\dots,\lambda_{n}\geq 0$ 使得 $R e_{k}=\sqrt{ \lambda_{k} }e_{k}$。

将 $v$ 写成

$$
\begin{gather}
v=a_{1}e_{1}+\dots+a_{n}e_{n}
\end{gather}
$$

则

$$
\begin{align}
Rv &= a_{1}\sqrt{ \lambda_{1} }e_{1}+\dots+a_{n}\sqrt{ \lambda_{n} }e_{n}
\end{align}
$$

于是

$$
\begin{gather}
\lambda v=Tv=R^{2}v=a_{1}\lambda_{1}e_{1}+\dots+a_{n}\lambda_{n}e_{n}
\end{gather}
$$

即

$$
\begin{gather}
a_{1}\lambda e_{1}+\dots+a_{n}\lambda e_{n}=a_{1}\lambda_{1}e_{1}+\dots+a_{n}\lambda_{n}e_{n}
\end{gather}
$$

于是 $a_{k}(\lambda-\lambda_{k})=0$。从而

$$
\begin{gather}
v=\sum_{\lambda_{k}=\lambda} a_{k}e_{k}
\end{gather}
$$

这给出

$$
\begin{gather}
Rv=\sum_{\lambda_{k}=\lambda} a_{k}\sqrt{ \lambda_{k} }e_{k}=\sqrt{ \lambda } \sum_{\lambda_{k}=\lambda}a_{k}e_{k}=\sqrt{ \lambda }v
\end{gather}
$$

这就完成了证明。

根据以上定理，我们就可以用 $\sqrt{ T }$ 来表示 $T$ 的唯一正平方根。

### Theorem 7.29

设 $T \in L(V)$ 是正算子，$v \in V$，则 $\langle Tv,v \rangle=0$ 当且仅当 $Tv=0$。

#### Proof

显然 $Tv=0$ 蕴含 $\langle Tv,v \rangle=0$。

反之，我们有

$$
\begin{gather}
\langle Tv,v \rangle =\langle \sqrt{ T }\sqrt{ T }v,v \rangle =\langle \sqrt{ T }v,\sqrt{ T }v \rangle =\lVert \sqrt{ T }v \rVert ^{2}=0
\end{gather}
$$

即 $\sqrt{ T }v=0$，从而 $Tv=\sqrt{ T }\sqrt{ T }v=0$。

从以上定理中我们可得推论：正定算子就是可逆的半正定算子。

# 7D Isometries, Unitary Operators, and Matrix Factorization

## Isometries

### Definition 7.30 isometry 等距映射

称 $S \in L(V,W)$ 是一个等距映射，如果对任意 $v \in V$ 有

$$
\begin{gather}
\lVert Sv \rVert =\lVert v \rVert 
\end{gather}
$$

换言之，一个等距映射是一个保持范数的线性映射。

任何等距映射都是单射：设 $Sv=0$，则 $\lVert v \rVert=\lVert Sv \rVert=0$，从而 $v=0$。

### Example 7.31

设 $e_{1},\dots,e_{n}$ 是 $V$ 的标准正交基，$g_{1},\dots,g_{n}$ 在 $W$ 标准正交。定义 $S \in L(V,W)$ 为 $Se_{k}=g_{k}$，我们可以来证明 $S$ 是一个等距映射。

设 $v \in V$，则

$$
\begin{gather}
v=\langle v,e_{1} \rangle e_{1}+\dots+\langle v,e_{n} \rangle e_{n}
\end{gather}
$$

于是

$$
\begin{gather}
Sv=\langle v,e_{1} \rangle g_{1}+\dots+\langle v,e_{n} \rangle g_{n}
\end{gather}
$$

从而

$$
\begin{gather}
\lVert Sv \rVert ^{2}=\lvert \langle v,e_{1} \rangle  \rvert ^{2}+\dots+\lvert \langle v,e_{n} \rangle  \rvert ^{2}=\lVert v \rVert ^{2}
\end{gather}
$$

即证 $S$ 保持范数。综上，我们得到结论：如果一个线性映射将标准正交基映射到标准正交向量组，那么它就是一个等距映射。

### Theorem 7.32

设 $S \in L(V,W)$，$e_{1},\dots,e_{n}$ 是 $V$ 的标准正交基，$f_{1},\dots,f_{m}$ 是 $W$ 的标准正交基，则以下命题等价。

1. $S$ 是等距映射。
2. $S^{*}S=I$。
3. 对 $u,v \in V$ 有 $\langle Su,Sv \rangle=\langle u,v \rangle$。
4. $Se_{1},\dots,Se_{n}$ 在 $W$ 中标准正交。
5. $\mathcal{M}(S,(e_{1},\dots,e_{n}),(f_{1},\dots,f_{m}))$ 的各列关于 Euclidean 内积在 $\mathbb{F}^{n}$ 中标准正交。

#### Proof

我们将证明 $1\implies 2\implies 3\implies 4\implies 5\implies 1$。

设 (1) 成立，则对 $v \in V$ 有

$$
\begin{gather}
\langle (I-S^{*}S)v,v \rangle =\langle v,v \rangle -\langle S^{*}Sv,v \rangle =\langle v,v \rangle -\langle Sv,Sv \rangle =0
\end{gather}
$$

因此自伴算子 $I-S^{*}S=0$，即证 (2)。

设 (2) 成立，则

$$
\begin{gather}
\langle Su,Sv \rangle =\langle S^{*}Su,v \rangle =\langle u,v \rangle 
\end{gather}
$$

从而 $S$ 保持内积。

现设 (3) 成立，则

$$
\begin{gather}
\langle Se_{j},Se_{k} \rangle =\langle e_{j},e_{k} \rangle =\delta_{jk}
\end{gather}
$$

因此 $Se_{1},\dots,Se_{n}$ 在 $W$ 中标准正交。

设 (4) 成立，令 $A=\mathcal{M}(S)$，则对 $1\leq k,r\leq n$ 有

$$
\begin{gather}
\sum_{j=1}^{m} A_{j,k} \overline{A}_{j,r}=\left< \sum_{j=1}^{m} A_{j,k}f_{j},\sum_{j=1}^{m} A_{j,r}f_{j} \right> =\langle Se_{k},Se_{r} \rangle =\delta_{kr} \tag{$*$}
\end{gather}
$$

因此 $A$ 的各列在 Euclidean 内积下标准正交。

最后设 (5) 成立，则 $(*)$ 表明 $Se_{1},\dots,Se_{n}$ 在 $W$ 中标准正交，从而应用 [[#Example 7.31]] 中的证明即得 $S$ 是等距映射。

## Unitary Operators

### Definition 7.33 unitary operator 酉（幺正）算子

称 $S \in L(V)$ 是一个酉（幺正）算子，如果它是一个可逆的等距映射。

前面我们提到，任何等距映射都是单射，而在有限维空间上单射性与可逆性是等价的。因此，在有限维内积空间上，我们可以去掉定义中的可逆性假设。

### Example 7.34

酉算子的一个代表例子是平面上的旋转。设 $\theta \in \mathbb{R}$，定义 $S \in L(\mathbb{R}^{2})$ 在标准基下的矩阵为

$$
\begin{gather}
\mathcal{M}(S)=\begin{pmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{pmatrix}
\end{gather}
$$

矩阵的两列标准正交，因此 $S$ 是等距映射，从而是一个酉算子。

### Theorem 7.35

设 $S \in L(V)$，$e_{1},\dots,e_{n}$ 是 $V$ 的标准正交基，则以下命题等价。

1. $S$ 是酉算子。
2. $S^{*}S=SS^{*}=I$。
3. $S$ 可逆，且 $S^{-1}=S^{*}$。
4. $Se_{1},\dots,Se_{n}$ 是 $V$ 的标准正交基。
5. $\mathcal{M}(S,(e_{1},\dots,e_{n}))$ 的各行关于 Euclidean 内积构成了 $\mathbb{F}^{n}$ 中的一个标准正交基。
6. $S^{*}$ 是酉算子。

#### Proof

我们将证明 $1\implies 2\implies 3\implies 4\implies 5\implies 6\implies 1$。

设 (1) 成立，由于 $S$ 的等距映射，因此

$$
\begin{gather}
S^{*}S=I
\end{gather}
$$

两边右乘 $S^{-1}$ 即得 $S^{-1}=S^{*}$，从而 $SS^{*}=SS^{-1}=I$，即证 (2)。

显然 (2) 蕴含 (3)。

现设 (3) 成立，于是 $S^{*}S=S^{-1}S=I$，从而由 [[#Theorem 7.32]] 中 (2) 与 (4) 的等价性知 $Se_{1},\dots,Se_{n}$ 在 $V$ 中标准正交。该向量组的长度等于 $\dim V$，因而是一个标准正交基。

设 (4) 成立，则 [[#Theorem 7.32]] 中 (1) 与 (4) 的等价性表明 $S$ 是酉算子，于是由已经证明了 $1\implies 2$ 得到

$$
\begin{gather}
(S^{*})^{*}S^{*}=SS^{*}=I
\end{gather}
$$

从而 $S^{*}$ 是一个等距映射，因而 $\mathcal{M}(S^{*})$ 的各列标准正交。由于 $\mathcal{M}(S)$ 的各行是 $\mathcal{M}(S^{*})$ 的各列的共轭，因此 $\mathcal{M}(S)$ 的各行也标准正交。

设 (5) 成立，则 $\mathcal{M}(S^{*})$ 的各列标准正交，从而由 [[#Theorem 7.32]] 中 (1) 和 (5) 的等价性知 $S^{*}$ 是等距映射，从而是酉算子。

最后，设 $S^{*}$ 是酉算子。前面我们已经证明 $1\implies 6$，即 $S$ 是酉算子蕴含 $S^{*}$ 是酉算子。用 $S^{*}$ 替换 $S$，则 $(S^{*})^{*}=S$ 是酉算子，这就完成了证明。

回到我们的 $L(V)$ 与 $\mathbb{C}$ 之间的类比上。前面我们提到，一个复数 $z$ 对应于 $S \in L(V)$，其共轭 $\overline{z}$ 对应于 $S^{*}$。因此自伴算子对应于实数，而正算子对应于非负数。

另一类重要的复数是单位圆 $\lvert z \rvert=1$ 上的数。条件 $\lvert z \rvert=1$ 等价于 $\overline{z}z=1$，因此类比到 $L(V)$ 上，这一条件对应于 $S^{*}S=I$，即 $S$ 是酉算子。下面我们就来展示这种类比性。

### Theorem 7.36

设 $\lambda$ 是一个酉算子的特征值，则 $\lvert \lambda \rvert=1$。

#### Proof

设 $S \in L(V)$ 是酉算子，$v$ 是对应于 $\lambda$ 的特征向量，则

$$
\begin{gather}
\lvert \lambda \rvert \lVert v \rVert =\lVert \lambda v \rVert =\lVert Sv \rVert =\lVert v \rVert 
\end{gather}
$$

故 $\lvert \lambda \rvert=1$。

### Theorem 7.37

设 $\mathbb{F}=\mathbb{C}$ 且 $S \in L(V)$，则以下命题等价。

1. $S$ 是酉算子。
2. $V$ 上有一个由 $S$ 的特征向量构成的标准正交基，并且其对应的特征值均具有绝对值 $1$。

#### Proof

设 (1) 成立，于是 $S^{*}S=SS^{*}=I$，因此 $S$ 是正规的。谱定理指出：存在 $V$ 的一个由 $S$ 的特征向量构成的标准正交基，[[#Theorem 7.36]] 表明所有特征值的绝对值都是 $1$，即证 (2)。

现在设 (2) 成立。令 $e_{1},\dots,e_{n}$ 为所指的标准正交基，对应的特征值为 $\lambda_{1},\dots,\lambda_{n}$。则我们有

$$
\begin{gather}
\langle Se_{j},Se_{k} \rangle =\langle \lambda_{j}e_{j},\lambda_{k}e_{k} \rangle =\lambda_{j} \overline{\lambda}_{k} \langle e_{j},e_{k} \rangle =\delta_{jk}
\end{gather}
$$

因此 $Se_{1},\dots,Se_{n}$ 是 $V$ 的标准正交基，从而 $S$ 是酉算子。

## QR Factorization

### Definition 7.38 unitary matrix 酉（幺正）矩阵

称一个 $n\times n$ 矩阵是酉（幺正）矩阵，如果它的各列在 $\mathbb{F}^{n}$ 中标准正交。

一个酉矩阵可以与一个酉算子等同。事实上，设 $S$ 是一个酉算子，那么 $S$ 在任何标准正交基下的矩阵都是酉矩阵。反之，给定一个酉矩阵 $U$，那么定义为 $Sv=Uv$ 的 $S \in L(\mathbb{F}^{n})$ 就是一个酉算子，如 [[#Theorem 7.32]] 与 [[#Theorem 7.35]] 所示。这种一一对应允许我们直接写出酉矩阵的如下性质：

### Theorem 7.39

设 $Q$ 是 $n\times n$ 矩阵，则以下命题等价。

1. $Q$ 是酉矩阵。
2. $Q$ 的各行在 $\mathbb{F}^{n}$ 中标准正交。
3. 对 $v \in \mathbb{F}^{n}$ 有 $\lVert Qv \rVert=\lVert v \rVert$。
4. $Q^{*}Q=Q Q^{*}=I$。

### Theorem 7.40 (QR 分解)

设 $A$ 是一个方阵，其各列线性无关，则存在唯一的方阵 $Q,R$ 使得 $Q$ 是酉矩阵，$R$ 是上三角矩阵且对角线元素均为正数，并且

$$
\begin{gather}
A=QR
\end{gather}
$$

#### Proof

设 $A$ 的各列为 $v_{1},\dots,v_{n}$，与 $\mathbb{F}^{n}$ 中的相应元素等同。对其应用 Gram-Schmidt 过程可得一个标准正交基 $e_{1},\dots,e_{n}$ 使得

$$
\begin{gather}
\operatorname{span}(v_{1},\dots,v_{k})=\operatorname{span}(e_{1},\dots,e_{k})
\end{gather}
$$

定义方阵 $R$ 为

$$
\begin{gather}
R_{j,k}=\langle v_{k},e_{j} \rangle 
\end{gather}
$$

如果 $j>k$，那么 $e_{j}$ 正交于 $\operatorname{span}(e_{1},\dots,e_{k})=\operatorname{span}(v_{1},\dots,v_{k})$，因此 $R_{j,k}=0$，这表明 $R$ 是上三角矩阵。

设 $Q$ 是各列为 $e_{1},\dots,e_{n}$ 的酉矩阵。根据矩阵乘法的定义，$QR$ 的第 $k$ 列是 $Q$ 的各列的线性组合，其系数来源于 $R$ 的第 $k$ 列。因此 $QR$ 的第 $k$ 列等于

$$
\begin{gather}
\langle v_{k},e_{1} \rangle e_{1}+\dots+\langle v_{k},e_{k} \rangle e_{k}=v_{k}
\end{gather}
$$

即证 $A=QR$。

Gram-Schmidt 过程中 $e_{k}$ 的计算公式表明 $v_{k}$ 等于 $e_{k}$ 的正数倍加上 $e_{1},\dots,e_{k-1}$ 的一个线性组合，因此 $\langle v_{k},e_{k} \rangle>0$，即证 $R$ 的对角线元素为正数。这就证明了存在性。

下面我们证明唯一性。设 $A=\hat{Q}\hat{R}$，其中 $\hat{Q}$ 是酉矩阵，$\hat{R}$ 是上三角矩阵，且对角线元素是正数。设 $\hat{Q}$ 的各列为 $q_{1},\dots,q_{n}$，根据矩阵乘法，我们可知 $v_{k}$ 等于 $\hat{Q}$ 各列的线性组合，其系数来源于 $\hat{R}$ 的第 $k$ 列。这表明 $\operatorname{span}(v_{1},\dots,v_{k})=\operatorname{span}(q_{1},\dots,q_{k})$，且 $\langle v_{k},q_{k} \rangle>0$。我们要证 $q_{k}=e_{k}$。

我们使用归纳法。当 $k=1$ 时，我们有 $\operatorname{span}(v_{1})=\operatorname{span}(q_{1})$ 且 $\langle v_{1},q_{1} \rangle>0$，于是 $q_{1}=v_{1} /\lVert v_{1} \rVert=e_{1}$。

假设 $q_{m}=e_{m}$ 对 $m\leq k-1$ 成立，则我们有

$$
\begin{align}
v_{k} &= \langle v_{k},q_{k} \rangle q_{k}+\langle v_{k},q_{k-1} \rangle q_{k-1}+\dots+\langle v_{k},q_{1} \rangle q_{1} \\
&=\langle v_{k},q_{k} \rangle q_{k}+\langle v_{k},e_{k-1} \rangle e_{k-1}+\dots+\langle v_{k},e_{1} \rangle e_{1}
\end{align}
$$

从而

$$
\begin{gather}
\langle v_{k},q_{k} \rangle q_{k}=\langle v_{k},e_{k} \rangle e_{k}
\end{gather}
$$

由于 $q_{k},e_{k}$ 都是单位向量，且 $\langle v_{k},q_{k} \rangle>0,\langle v_{k},e_{k} \rangle>0$ 表明它们的方向相同，因此 $q_{k}=e_{k}$。这就证明了 $\hat{Q}=Q$，从而我们有 $\hat{R}=R$。

QR 分解定理的证明表明，酉矩阵 $Q$ 的列可以通过对 $A$ 的各列进行 Gram-Schmidt 过程得到，并且在这一过程中产生的标准正交基是唯一的。下面的例子展示了求解矩阵的 QR 分解的全过程。

### Example 7.41

我们来计算矩阵

$$
\begin{gather}
A=\begin{pmatrix}
1 & 2 & 1 \\
0 & 1 & -4 \\
0 & 3 & 2
\end{pmatrix}
\end{gather}
$$

的 QR 分解。$A$ 的各列为

$$
\begin{gather}
v_{1}=(1,0,0), \quad v_{2}=(2,1,3), \quad v_{3}=(1,-4,2)
\end{gather}
$$

应用 Gram-Schmidt 过程产生了标准正交基

$$
\begin{gather}
e_{1}=(1,0,0), \quad e_{2}=\left( 0,\frac{1}{\sqrt{ 10 }},\frac{3}{\sqrt{ 10 }} \right), \quad e_{3}=\left( 0,-\frac{3}{\sqrt{ 10 }},\frac{1}{\sqrt{ 10 }} \right)
\end{gather}
$$

于是

$$
\begin{gather}
Q=\begin{pmatrix}
1 & 0 & 0 \\
0 & \frac{1}{\sqrt{ 10 }} & -\frac{3}{\sqrt{ 10 }} \\
0 & \frac{3}{\sqrt{ 10 }} & \frac{1}{\sqrt{ 10 }}
\end{pmatrix}
\end{gather}
$$

是一个酉矩阵。接下来，逐个计算 $\langle v_{k},e_{j} \rangle$ 即得上三角矩阵

$$
\begin{gather}
R=\begin{pmatrix}
1 & 2 & 1 \\
0 & \sqrt{ 10 } & \frac{\sqrt{ 10 }}{5} \\
0 & 0 & \frac{7\sqrt{ 10 }}{5}
\end{pmatrix}
\end{gather}
$$

我们可以验证 $A=QR$。

QR 分解可以用来快速求解线性方程组。假设我们需要解方程 $Ax=b$，其中 $A$ 是 $n\times n$ 矩阵，$b \in \mathbb{F}^{n}$，代入 $A=QR$，则我们就有 $QRx=b$，两边乘以 $Q^{*}=Q^{-1}$ 即得

$$
\begin{gather}
Rx=Q^{*}b
\end{gather}
$$

由于 $R$ 是上三角矩阵，因此我们做 $n$ 次回代即可完成求解。

## Cholesky Factorization

我们首先给出正定算子的一些等价性质。

### Theorem 7.42

设 $T \in L(V)$，则以下命题等价。

1. $T$ 是正定算子。
2. $T$ 是自伴的且所有特征值为正数。
3. 在 $V$ 的某个标准正交基下 $T$ 有对角矩阵，且对角线上的元素都是正数。
4. $T$ 有正定的平方根。
5. 存在可逆的 $R \in L(V)$ 使得 $T=R^{*}R$。

#### Proof

本证明与 [[#Theorem 7.27]] 的证明在结构上是相同的。

设 (1) 成立，则对于特性向量 $v$ 有

$$
\begin{gather}
\lambda \langle v,v \rangle =\langle \lambda v,v \rangle =\langle Tv,v \rangle >0
\end{gather}
$$

即 $\lambda>0$。

$2\implies 3$ 由谱定理给出。

设 (3) 成立，令 $e_{1},\dots,e_{n}$ 为相应的标准正交基，对角线元素（特征值）$\lambda_{1},\dots,\lambda_{n}>0$。定义

$$
\begin{gather}
R e_{k}=\sqrt{ \lambda_{k} } e_{k}
\end{gather}
$$

则 $R^{2}=T$ 且对于 $v\neq 0$ 有

$$
\begin{gather}
\langle Rv,v \rangle =\lvert a_{1} \rvert ^{2}\sqrt{ \lambda_{1} }+\dots+\lvert a_{n} \rvert ^{2}\sqrt{ \lambda_{n} } > 0
\end{gather}
$$

因为存在 $a_{k}\neq 0$。

下面设 (4) 成立，则令 $R=\sqrt{ T }$ 即可，其中 $\sqrt{ T }$ 正定，从而可逆。

最后，设 $T=R^{*}R$，则对于 $v\neq 0$ 有 $Rv\neq 0$，从而

$$
\begin{gather}
\langle Tv,v \rangle =\langle R^{*}Rv,v \rangle =\langle Rv,Rv \rangle =\lVert Rv \rVert ^{2}> 0
\end{gather}
$$

即证 $T$ 正定。

### Theorem 7.43 (Cholesky 分解)

设 $B$ 是一个正定矩阵，则存在唯一的上三角矩阵 $R$，其对角线元素均为正数，并且

$$
\begin{gather}
B=R^{*}R
\end{gather}
$$

#### Proof

由于 $B$ 正定，根据 [[#Theorem 7.42]] 中 (1) 和 (5) 的等价性，存在可逆矩阵 $A$ 使得 $B=A^{*}A$。

对 $A$ 做 QR 分解 $A=QR$，其中 $Q$ 是酉矩阵，$R$ 是上三角矩阵，其对角线元素为正数，则 $A^{*}=R^{*}Q^{*}$，从而

$$
\begin{gather}
B=R^{*}Q^{*}Q R=R^{*}R
\end{gather}
$$

要证明唯一性，假设有 $B=S^{*}S$。由于 $B$ 可逆，因此

$$
\begin{gather}
\mathbb{F}^{n}=\operatorname{range} S^{*}S \subset \operatorname{range}S^{*}
\end{gather}
$$

故 $S^{*}$ 是满射，从而可逆，因而 $S$ 也是可逆的。两边乘以 $S^{-1}$ 可得 $BS^{-1}=S^{*}$。

令 $A$ 如上文所示，则

$$
\begin{align}
(AS^{-1})^{*}(AS^{-1})&= (S^{*})^{-1}A^{*}AS^{-1} \\
&=(S^{*})^{-1}BS^{-1} \\
&=(S^{*})^{-1}S^{*} \\
&=I
\end{align}
$$

因此 $AS^{-1}$ 是酉矩阵，从而 $A=(AS^{-1})S$ 是一个酉矩阵与一个上三角矩阵的乘积。根据 QR 分解的唯一性，我们就有 $AS^{-1}=Q$ 且 $S=R$。这就完成了证明。

值得一提的是，尽管在以上证明中我们使用 QR 分解来证明 Cholesky 分解的存在性，但在实际应用中我们通常使用 Gaussian 消元法与 LR 分解来得到 $R$。上述定理的唯一性保证了无论我们用什么方法得到 $R$，其结果总是不变的。

# 7E Singular Value Decomposition

## Singular Values

### Theorem 7.44

设 $T \in L(V,W)$，则

1. $T^{*}T \in L(V)$ 是正算子，
2. $\ker T^{*}T=\ker T$，
3. $\operatorname{range}T^{*}T=\operatorname{range}T^{*}$，
4. $\dim \operatorname{range}T=\dim \operatorname{range}T^{*}=\dim \operatorname{range}T^{*}T$。

#### Proof

(1) 显然 $T^{*}T$ 是自伴的。设 $v \in V$，则

$$
\begin{gather}
\langle T^{*}Tv,v \rangle =\langle Tv,Tv \rangle =\lVert Tv \rVert ^{2}\geq 0
\end{gather}
$$

因此 $T^{*}T$ 是正算子。

(2) 显然 $\ker T\subset \ker T^{*}T$。设 $v \in \ker T^{*}T$，则

$$
\begin{gather}
\lVert Tv \rVert ^{2}=\langle Tv,Tv \rangle =\langle T^{*}Tv,v \rangle =0
\end{gather}
$$

故 $Tv=0$，即 $v \in \ker T$。即证 $\ker T^{*}T=\ker T$。

(3) 我们有

$$
\begin{gather}
\operatorname{range}T^{*}T=(\ker T^{*}T)^{\perp}=(\ker T)^{\perp}=\operatorname{range}T^{*}
\end{gather}
$$

(4) 第一个等式来源于

$$
\begin{gather}
\dim \operatorname{range}T^{*}=\dim(\ker T)^{\perp}=\dim V-\dim \ker T=\dim \operatorname{range}T
\end{gather}
$$

而第二个等式由 (3) 给出。

一个算子的特征值能够告诉我们关于算子的一些信息。奇异值是特征值在 $L(V,W)$ 中的一种类似的推广。

### Definition 7.45 singular value 奇异值

设 $T \in L(V,W)$，$T$ 的奇异值定义为 $T^{*}T$ 的特征值的非负平方根，降序排列，并且每个特征值 $\lambda$ 所对应的奇异值重复 $\dim E(\lambda,T^{*}T)$ 次。

### Theorem 7.46

设 $T \in L(V,W)$，则

1. $T$ 是单射当且仅当 $0$ 不是 $T$ 的奇异值，
2. $T$ 的正奇异值的数量等于 $\dim \operatorname{range}T$，
3. $T$ 的满射当且仅当 $T$ 的正奇异值数量等于 $\dim W$。

#### Proof

(1) $T$ 是单射当且仅当 $\ker T=\ker T^{*}T=\{ 0 \}$，当且仅当 $0$ 不是 $T^{*}T$ 的特征值，当且仅当 $0$ 不是 $T$ 的奇异值。

(2) 对 $T^{*}T$ 应用谱定理，则我们可知 $\dim \operatorname{range}T=\dim \operatorname{range}T^{*}T$ 等于 $T^{*}T$ 的正特征值数量（计入重复），等于 $T$ 的正奇异值数量。

显然 (2) 蕴含 (3)，这就完成了证明。

### Theorem 7.47

设 $S \in L(V,W)$，则 $S$ 是等距映射当且仅当 $S$ 的奇异值均为 $1$。

#### Proof

我们有：$S$ 是等距映射当且仅当 $S^{*}S=I$，当且仅当 $S^{*}S$ 的特征值均为 $1$，当且仅当 $S$ 的奇异值均为 $1$。

## SVD for Linear Maps and for Matrices

本节我们将证明奇异值分解（SVD）的存在性，它表明，利用奇异值，我们可以为每个 $T \in L(V,W)$ 给出一个清晰且简单的表示。

### Theorem 7.48 (奇异值分解)

设 $T \in L(V,W)$，且 $T$ 的正奇异值为 $s_{1},\dots,s_{m}$，则存在 $V$ 中的标准正交向量组 $e_{1},\dots,e_{m}$ 和 $W$ 中的标准正交向量组 $f_{1},\dots,f_{m}$ 使得

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m} \quad (v \in V)
\end{gather}
$$

#### Proof

设 $s_{1},\dots,s_{n}$ 为 $T$ 的奇异值，其中 $n=\dim V$。由于 $T^{*}T$ 是正算子，因此谱定理表明存在 $V$ 的标准正交基 $e_{1},\dots,e_{n}$ 使得

$$
\begin{gather}
T^{*}Te_{k}=s_{k}^{2}e_{k}
\end{gather}
$$

对 $1\leq k\leq m$，令

$$
\begin{gather}
f_{k}=\frac{Te_{k}}{s_{k}}
\end{gather}
$$

则当 $1\leq j,k\leq m$ 时有

$$
\begin{gather}
\langle f_{j},f_{k} \rangle =\frac{1}{s_{j}s_{k}} \langle Te_{j},Te_{k} \rangle =\frac{1}{s_{j}s_{k}}\langle e_{j},T^{*}Te_{k} \rangle =\frac{s_{k}}{s_{j}}\langle e_{j},e_{k} \rangle =\delta_{jk}
\end{gather}
$$

因此 $f_{1},\dots,f_{m}$ 在 $W$ 中标准正交。

如果 $k>m$，则 $s_{k}=0$，从而 $T^{*}Te_{k}=0$，由 $\ker T^{*}T=\ker T$ 知 $Te_{k}=0$，因此

$$
\begin{align}
Tv &= T(\langle v,e_{1} \rangle e_{1}+\dots+\langle v,e_{n} \rangle e_{n}) \\
&= \langle v,e_{1} \rangle Te_{1}+\dots+\langle v,e_{n} \rangle Te_{n} \\
&=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m}
\end{align}
$$

这就完成了证明。

设 $T \in L(V,W)$，$T$ 的正奇异值为 $s_{1},\dots,s_{m}$，并令标准正交组 $e_{1},\dots,e_{m}$ 和 $f_{1},\dots,f_{m}$ 如 [[#Theorem 7.48 (奇异值分解)]] 所示。我们可以将其扩张为标准正交基 $e_{1},\dots,e_{\dim V}$ 和 $f_{1},\dots,f_{\dim W}$，则 SVD 表明

$$
\begin{gather}
Te_{k}=\begin{cases}
s_{k} f_{k}, & 1\leq k\leq m \\
0, & m<k\leq \dim V
\end{cases}
\end{gather}
$$

因此 $T$ 在基 $e_{1},\dots,e_{\dim V}$ 和 $f_{1},\dots,f_{\dim W}$ 下的矩阵具有如下的简单形式：

$$
\begin{gather}
\mathcal{M}(T)_{j,k}=\begin{cases}
s_{k}, & 1\leq j=k\leq m \\
0, & \text{otherwise}
\end{cases}
\end{gather}
$$

如果 $\dim V=\dim W$，那么以上矩阵就是一个对角矩阵。因此，如果我们将对角矩阵的定义扩展一些，那么 SVD 就给出了如下的重要事实：在定义域和陪域的合适标准正交基下，任何 $T \in L(V,W)$ 都有对角矩阵。

### Definition 7.49 diagonal matrix 对角矩阵

称一个 $m\times n$ 矩阵 $A$ 是一个对角矩阵，如果除了对角线元素 $A_{k,k}$，其中 $1\leq k\leq \min(m,n)$ 外，所有项均为 $0$。

SVD 为我们研究伴随与伪逆提供了一种新的视角，如以下定理所示。

### Theorem 7.50

设 $T \in L(V,W)$ 的正奇异值为 $s_{1},\dots,s_{m}$，且 $e_{1},\dots,e_{m}$ 在 $V$ 中标准正交，$f_{1},\dots,f_{m}$ 在 $W$ 中标准正交，满足

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m} \quad (v \in V)
\end{gather}
$$

则对任意 $w \in W$ 有

$$
\begin{gather}
T^{*}w=s_{1}\langle w,f_{1} \rangle e_{1}+\dots+s_{m}\langle w,f_{m} \rangle e_{m}
\end{gather}
$$

且

$$
\begin{gather}
T^{\dagger}w=\frac{\langle w,f_{1} \rangle }{s_{1}}e_{1}+\dots+\frac{\langle w,f_{m} \rangle }{s_{m}}e_{m}
\end{gather}
$$

#### Proof

设 $v \in V,w \in W$，则

$$
\begin{align}
\langle Tv,w \rangle &= \langle s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m},w \rangle  \\
&=s_{1}\langle v,e_{1} \rangle \langle f_{1},w \rangle +\dots+s_{m}\langle v,e_{m} \rangle \langle f_{m},w \rangle  \\
&=\langle v,s_{1}\langle w,f_{1} \rangle e_{1}+\dots+s_{m}\langle w,f_{m} \rangle e_{m} \rangle 
\end{align}
$$

因此

$$
\begin{gather}
T^{*}w=s_{1}\langle w,f_{1} \rangle e_{1}+\dots+s_{m}\langle w,f_{m} \rangle e_{m}
\end{gather}
$$

接下来，令 $w \in W$，设

$$
\begin{gather}
v=\frac{\langle w,f_{1} \rangle }{s_{1}}e_{1}+\dots+\frac{\langle w,f_{m} \rangle }{s_{m}}e_{m}
\end{gather}
$$

则

$$
\begin{align}
Tv &= \frac{\langle w,f_{1} \rangle }{s_{1}}Te_{1}+\dots+\frac{\langle w,f_{m} \rangle }{s_{m}}Te_{m} \\
&=\langle w,f_{1} \rangle f_{1}+\dots+\langle w,f_{m} \rangle f_{m} \\
&=P_{\operatorname{range}T}w
\end{align}
$$

由于 $e_{1},\dots,e_{m}$ 是 $(\ker T)^{\perp}$ 的标准正交基，因此 $v \in(\ker T)^{\perp}$，从而

$$
\begin{gather}
v=(T|_{(\ker T)^{\perp}})^{-1}P_{\operatorname{range}T}w=T^{\dagger}w
\end{gather}
$$

这就完成了证明。

### Theorem 7.51 (奇异值分解)

设 $A$ 是一个 $p\times n$ 矩阵，其秩为 $m\geq 1$。则存在一个具有标准正交列的 $p\times n$ 矩阵 $B$，一个对角线元素为正数的 $m\times m$ 对角矩阵 $D$，以及一个具有标准正交列的 $n\times m$ 矩阵 $C$ 使得

$$
\begin{gather}
A=BDC^{*}
\end{gather}
$$

#### Proof

令 $T \in L(\mathbb{F}^{n},\mathbb{F}^{p})$ 定义为 $Tv=Av$，则 $\dim \operatorname{range}T=\operatorname{rank}A=m$。令

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m}
\end{gather}
$$

为 $T$ 的奇异值分解，定义矩阵 $B$ 的列为 $f_{1},\dots,f_{m}$，$D$ 为对角矩阵，其对角线元素为 $s_{1},\dots,s_{m}$，以及 $C$ 的列为 $e_{1},\dots,e_{m}$。

设 $u_{1},\dots,u_{m}$ 为 $\mathbb{F}^{m}$ 上的标准基，则

$$
\begin{gather}
(AC-BD)u_{k}=Ae_{k}-B(s_{k}u_{k})=s_{k}f_{k}-s_{k}f_{k}=0
\end{gather}
$$

从而 $AC=BD$。

两边乘以 $C^{*}$ 即得

$$
\begin{gather}
AC C^{*}=BDC^{*}
\end{gather}
$$

我们要证 $AC C^{*}=A$。由于 $C^{*}$ 的行是 $e_{1},\dots,e_{m}$ 的共轭，因此对 $1\leq k\leq m$ 有 $C C^{*}e_{k}=e_{k}$，从而对 $v \in \operatorname{span}(e_{1},\dots,e_{m})$ 有 $AC C^{*}v=Av$。

如果 $v \in \operatorname{span}(e_{1},\dots,e_{m})^{\perp}$，则 $Av=0$ 且 $C^{*}v=0$，从而 $AC C^{*}$ 与 $A$ 在 $\operatorname{span}(e_{1},\dots,e_{m})^{\perp}$ 上相等。即证

$$
\begin{gather}
A=BDC^{*}
\end{gather}
$$

特别地，结合矩阵的 SVD 与 [[#Theorem 7.50]]，我们可以给出伪逆矩阵 $A^{+}$ 的一个公式

$$
\begin{gather}
A^{+}=CD^{-1}B^{*}
\end{gather}
$$

# 7F Consequences of Singular Value Decomposition

## Norms of Linear Maps

### Theorem 7.52

设 $T \in L(V,W)$，$s_{1}$ 是 $T$ 的最大奇异值，则

$$
\begin{gather}
\lVert Tv \rVert \leq s_{1}\lVert v \rVert  \quad (v \in V)
\end{gather}
$$

#### Proof

设 $s_{1},\dots,s_{m}$ 是 $T$ 的正奇异值，按大小降序排列。根据 SVD，我们有

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m}
\end{gather}
$$

其中 $e_{1},\dots,e_{m}$ 和 $f_{1},\dots,f_{m}$ 分别在 $V$ 和 $W$ 中标准正交。于是

$$
\begin{align}
\lVert Tv \rVert ^{2}&= s_{1}^{2} \lvert \langle v,e_{1} \rangle  \rvert ^{2}+\dots+s_{m}^{2}\lvert \langle v,e_{m} \rangle  \rvert ^{2} \\
&\leq s_{1}^{2} (\lvert \langle v,e_{1} \rangle  \rvert ^{2}+\dots+\lvert \langle v,e_{m} \rangle  \rvert ^{2}) \\
&\leq s_{1}^{2} \lVert v \rVert ^{2}
\end{align}
$$

取平方根即证 $\lVert Tv \rVert\leq s_{1}\lVert v \rVert$。

设 $T \in L(V,W)$ 且 $s_{1}$ 是 $T$ 的最大奇异值，则上面的定理表明

$$
\begin{gather}
\lVert Tv \rVert \leq s_{1}
\end{gather}
$$

对任意 $v \in V,\lVert v \rVert\leq 1$ 成立。取 $v=e_{1}$，我们有 $Te_{1}=s_{1}f_{1}$，从而 $\lVert Te_{1} \rVert=s_{1}$，因此我们就有

$$
\begin{gather}
s_{1}=\max_{\lVert v \rVert \leq 1} \lVert Tv \rVert 
\end{gather}
$$

右侧的表达式有非常丰富的应用，我们给它一个定义。

### Definition 7.53

设 $T \in L(V,W)$，则 $T$ 的范数 $\lVert T \rVert$ 定义为

$$
\begin{gather}
\lVert T \rVert =\max_{\lVert v \rVert \leq 1} \lVert Tv \rVert 
\end{gather}
$$

一般来说，一个无限集的最大值可能无法取到。不过，上面的讨论表明，对任意 $T \in L(V,W)$，我们总是可以取到那个最大值，它等于 $T$ 的最大奇异值。

线性映射的范数 $\lVert T \rVert$ 与内积空间中向量的范数 $\lVert v \rVert$ 具有相同的性质：正定性、齐次性、三角不等式，见下方的定理。只不过不同的是，前者不一定是由一个内积所生成的。一个配备了范数的向量空间称为一个赋范向量空间，这种结构是泛函分析研究的核心。

### Theorem 7.54

设 $T \in L(V,W)$，则

1. 正定性：$\lVert T \rVert\geq 0$，且 $\lVert T \rVert=0$ 当且仅当 $T=0$，
2. 齐次性：对 $\lambda \in \mathbb{F}$ 有 $\lVert \lambda T \rVert=\lvert \lambda \rvert\lVert T \rVert$，
3. 三角不等式：对 $S \in L(V,W)$ 有 $\lVert S+T \rVert\leq \lVert S \rVert+\lVert T \rVert$。

#### Proof

(1) 由于 $\lVert Tv \rVert\geq 0$，因此 $\lVert T \rVert$ 的定义表明 $\lVert T \rVert\geq 0$。

设 $\lVert T \rVert=0$，则对任意 $\lVert v \rVert\leq 1$ 有 $\lVert Tv \rVert=0$。设 $u \in V,u\neq 0$，则

$$
\begin{gather}
Tu=\lVert u \rVert T\left( \frac{u}{\lVert u \rVert } \right)=0
\end{gather}
$$

因而 $T=0$。反向的蕴含是显然的。

(2) 我们有

$$
\begin{align}
\lVert \lambda T \rVert &=\max_{\lVert v \rVert \leq 1} \lVert \lambda Tv \rVert  \\
&=\lvert \lambda \rvert \max_{\lVert v \rVert \leq 1} \lVert Tv \rVert  \\
&=\lvert \lambda \rvert  \lVert T \rVert 
\end{align}
$$

(3) 设 $S \in L(V,W)$，则对 $\lVert v \rVert\leq 1$ 有

$$
\begin{gather}
\lVert (S+T)v \rVert \leq \lVert Sv \rVert +\lVert Tv \rVert \leq \lVert S \rVert +\lVert T \rVert 
\end{gather}
$$

对不等式左边取最大值即得 $\lVert S+T \rVert\leq \lVert S \rVert+\lVert T \rVert$。

### Theorem 7.55

设 $T \in L(V,W)$，则

1. $\lVert T \rVert$ 等于 $T$ 的最大奇异值，
2. $\lVert T \rVert=\max_{\lVert v \rVert=1}\lVert Tv \rVert$，
3. $\lVert T \rVert=\min \{ c \in \mathbb{R} : \lVert Tv \rVert\leq c \lVert v \rVert \}$。

#### Proof

我们已经证明了 (1)。

(2) 设 $v \in V,0<\lVert v \rVert\leq 1$，令 $u=v /\lVert v \rVert$，则 $\lVert u \rVert=1$，且

$$
\begin{gather}
\lVert Tu \rVert =\frac{\lVert Tv \rVert }{\lVert v \rVert }\geq \lVert Tv \rVert 
\end{gather}
$$

因此当我们在 $\lVert v \rVert\leq 1$ 中选取 $\lVert Tv \rVert$ 的最大值时，我们可以将 $v$ 的范围限定在 $\lVert v \rVert=1$ 上。

(3) 设 $v \in V,v\neq 0$，则 $\lVert T \rVert$ 的定义给出

$$
\begin{gather}
\left\lVert  T\left( \frac{v}{\lVert v \rVert } \right)  \right\rVert \leq \lVert T \rVert 
\end{gather}
$$

即

$$
\begin{gather}
\lVert Tv \rVert \leq \lVert T \rVert \lVert v \rVert 
\end{gather}
$$

现在假设 $c$ 满足 $\lVert Tv \rVert\leq c\lVert v \rVert$，则对 $\lVert v \rVert\leq 1$ 有

$$
\begin{gather}
\lVert Tv \rVert \leq c
\end{gather}
$$

取最大值即得 $\lVert T \rVert\leq c$。这就表明 $\lVert T \rVert$ 是最小的使得 $\lVert Tv \rVert\leq c\lVert v \rVert$ 的实数。

### Example 7.56

(a) $V$ 上的恒等算子 $I$ 满足 $\lVert I \rVert=1$。

(b) 设 $T \in L(V)$ 在 $V$ 的某个标准正交基下有对角矩阵，其特征值为 $\lambda_{1},\dots,\lambda_{n}$，则 $\lVert T \rVert=\max(\lvert \lambda_{1} \rvert,\dots,\lvert \lambda_{n} \rvert)$。

### Theorem 7.57

设 $T \in L(V,W)$，则 $\lVert T^{*} \rVert=\lVert T \rVert$。

#### Proof

设 $w \in W$，则

$$
\begin{gather}
\lVert T^{*}w \rVert ^{2}=\langle T^{*}w,T^{*}w \rangle =\langle TT^{*}w,w \rangle \leq \lVert TT^{*}w \rVert \lVert w \rVert \leq \lVert T \rVert \lVert T^{*}w \rVert \lVert w \rVert 
\end{gather}
$$

于是

$$
\begin{gather}
\lVert T^{*}w \rVert \leq \lVert T \rVert \lVert w \rVert 
\end{gather}
$$

从而我们有 $\lVert T^{*} \rVert\leq \lVert T \rVert$。

在以上不等式中用 $T^{*}$ 替换 $T$，根据 $(T^{*})^{*}=T$ 即得 $\lVert T \rVert\leq \lVert T^{*} \rVert$，这就完成了证明。

## Approximation by Linear Maps with Lower-Dimensional Range

以下的定理是 SVD 的一个重要应用。它说的是，$T$ 的前 $k$ 个奇异值所对应的方向在保留 $k$ 个主要方向信息的情况下给出了 $T$ 的最佳近似。这一结果启发了用于保留最重要的信息的同时压缩大型矩阵的算法。

### Theorem 7.58

设 $T \in L(V,W)$，$s_{1}\geq\dots\geq s_{m}$ 是 $T$ 的正奇异值，则对 $1\leq k<m$ 有

$$
\begin{gather}
\min \{ \lVert T-S \rVert : S \in L(V,W), \dim \operatorname{range}S\leq k \}=s_{k+1}
\end{gather}
$$

此外，如果

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m}
\end{gather}
$$

是 $T$ 的 SVD，且 $T_{k}\in L(V,W)$ 定义为

$$
\begin{gather}
T_{k}v=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{k}\langle v,e_{k} \rangle f_{k}
\end{gather}
$$

则 $\dim \operatorname{range}T_{k}=k$ 且 $\lVert T-T_{k} \rVert=s_{k+1}$。

#### Proof

设 $v \in V$ 则

$$
\begin{align}
\lVert (T-T_{k})v \rVert ^{2} &= \lVert s_{k+1}\langle v,e_{k+1} \rangle f_{k+1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m} \rVert ^{2} \\
&= s_{k+1}^{2} \lvert \langle v,e_{k+1} \rangle  \rvert ^{2}+\dots+s_{m}^{2}\lvert \langle v,e_{m} \rangle  \rvert ^{2} \\
&\leq s_{k+1}^{2}(\lvert \langle v,e_{k+1} \rangle  \rvert ^{2}+\dots+\lvert \langle v,e_{m} \rangle  \rvert ^{2}) \\
&\leq s_{k+1}^{2}\lVert v \rVert 
\end{align}
$$

因此 $\lVert T-T_{k} \rVert\leq s_{k+1}$。等式 $(T-T_{k})e_{k+1}=s_{k+1}f_{k+1}$ 表明 $\lVert T-T_{k} \rVert=s_{k+1}$。

设 $S \in L(V,W)$ 满足 $\dim \operatorname{range}S\leq k$，则 $Se_{1},\dots,Se_{k+1}$ 作为长度为 $k+1$ 的向量组是线性相关的，因此存在不全为零的 $a_{1},\dots,a_{k+1}$ 使得

$$
\begin{gather}
a_{1}Se_{1}+\dots+a_{k+1}Se_{k+1}=0
\end{gather}
$$

并且 $a_{1}e_{1}+\dots+a_{k+1}e_{k+1}\neq 0$。我们有

$$
\begin{align}
\lVert (T-S)(a_{1}e_{1}+\dots+a_{k+1}e_{k+1}) \rVert ^{2} &= \lVert T(a_{1}e_{1}+\dots+a_{k+1}e_{k+1}) \rVert ^{2} \\
&=\lVert s_{1}a_{1}f_{1}+\dots+s_{k+1}a_{k+1}f_{k+1} \rVert ^{2} \\
&=s_{1}^{2}\lvert a_{1} \rvert ^{2}+\dots+s_{k+1}^{2}\lvert a_{k+1} \rvert ^{2} \\
&\geq s_{k+1}^{2}(\lvert a_{1} \rvert ^{2}+\dots+\lvert a_{k+1} \rvert ^{2}) \\
&=s_{k+1}^{2} \lVert a_{1}e_{1}+\dots+a_{k+1}e_{k+1} \rVert ^{2}
\end{align}
$$

从而 $\lVert T-S \rVert\geq s_{k+1}$。

取 $S=T_{k}$ 表明 $s_{k+1}=\min \lVert T-S \rVert$，其中 $S$ 遍历 $\dim \operatorname{range}S\leq k$ 的 $S \in L(V,W)$。

## Polar Decomposition

再次引用复数 $z$ 与 $T \in L(V)$ 之间的类比。前面我们提到，单位圆 $\lvert z \rvert=1$ 上的复数可以类比于一个酉算子，进一步，由于每个非零复数都可以写成

$$
\begin{align}
z&=\left( \frac{z}{\lvert z \rvert } \right)\lvert z \rvert  \\
&=\left( \frac{z}{\lvert z \rvert } \right)\sqrt{ \overline{z}z }
\end{align}
$$

其中第一项的绝对值为 $1$。我们的类比启发我们猜测，任何算子 $T$ 都可以写成一个酉算子与 $\sqrt{ T^{*}T }$ 的乘积。这一猜想的确是正确的，它被称为算子的极分解。

### Theorem 7.59 (极分解)

设 $T \in L(V)$，则存在酉算子 $S \in L(V)$ 使得

$$
\begin{gather}
T=S\sqrt{ T^{*}T }
\end{gather}
$$

#### Proof

设 $s_{1},\dots,s_{m}$ 为 $T$ 的正奇异值，令

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m}
\end{gather}
$$

为 $T$ 的 SVD。将 $e_{1},\dots,e_{m}$ 和 $f_{1},\dots,f_{m}$ 扩张为 $V$ 上的标准正交基 $e_{1},\dots,e_{n}$ 和 $f_{1},\dots,f_{n}$。

定义 $S \in L(V)$ 为

$$
\begin{gather}
Sv=\langle v,e_{1} \rangle f_{1}+\dots+\langle v,e_{n} \rangle f_{n}
\end{gather}
$$

于是

$$
\begin{align}
\lVert Sv \rVert ^{2} &= \lVert \langle v,e_{1} \rangle f_{1}+\dots+\langle v,e_{n} \rangle f_{n} \rVert ^{2} \\
&=\lvert \langle v,e_{1} \rangle  \rvert^{2}+\dots+\lvert \langle v,e_{n} \rangle  \rvert ^{2} \\
&=\lVert v \rVert ^{2} 
\end{align}
$$

故 $S$ 是酉算子。

根据 [[#Theorem 7.50]]，我们有

$$
\begin{gather}
T^{*}Tv=s_{1}^{2}\langle v,e_{1} \rangle e_{1}+\dots+s_{m}^{2}\langle v,e_{m} \rangle e_{m}
\end{gather}
$$

因此

$$
\begin{gather}
\sqrt{ T^{*}T }v=s_{1}\langle v,e_{1} \rangle e_{1}+\dots+s_{m}\langle v,e_{m} \rangle e_{m}
\end{gather}
$$

现在将 $S$ 应用到等式两边就有

$$
\begin{align}
S\sqrt{ T^{*}T }v &= s_{1}\langle v,e_{1} \rangle Se_{1}+\dots+s_{m}\langle v,e_{m} \rangle Se_{m} \\
&=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{m}\langle v,e_{m} \rangle f_{m} \\
&=Tv
\end{align}
$$

即证 $T=S\sqrt{ T^{*}T }$。

## Operators Applied to Ellipsoids and Parallelepipeds

本节与下一节的内容在分析学中有广泛的应用。

### Definition 7.60 ball 球

$V$ 中以 $v$ 为中心，$r$ 为半径的开球 $B(v,r)$ 定义为

$$
\begin{gather}
B(v,r)=\{ w \in V : \lVert v-w \rVert <r \}
\end{gather}
$$

我们记 $B=B(0,1)$。此外，如果 $\dim V=2$，那么我们通常称一个开球为一个开圆盘（disk）。

### Definition 7.61 ellipsoid 椭球，principle axes 主轴

设 $f_{1},\dots,f_{n}$ 是 $V$ 的标准正交基，$s_{1},\dots,s_{n}$ 是正数，则具有主轴 $s_{1}f_{1},\dots,s_{n}f_{n}$ 的开椭球 $E(s_{1}f_{1},\dots,s_{n}f_{n})$ 定义为

$$
\begin{gather}
E(s_{1}f_{1},\dots,s_{n}f_{n})=\left\{  v \in V : \frac{\lvert \langle v,f_{1} \rangle  \rvert ^{2}}{s_{1}^{2}}+\dots+\frac{\lvert \langle v,f_{n} \rangle  \rvert ^{2}}{s_{n}^{2}} < 1 \right\}
\end{gather}
$$

容易证明，对任意标准正交基 $f_{1},\dots,f_{n}$，椭球 $E(f_{1},\dots,f_{n})$ 等于单位球 $B$。

### Notation 7.62

设映射 $T$ 定义在 $V$ 上，$\Omega \subset V$，则我们定义

$$
\begin{gather}
T(\Omega)=\{ Tv : v \in\Omega \}
\end{gather}
$$

特别地，我们有 $\operatorname{range}T=T(V)$。

### Theorem 7.63

设 $T \in L(V)$ 是可逆的，则 $T$ 将 $V$ 中的开球 $B$ 映射到 $V$ 中的一个开椭球。

#### Proof

设 $T$ 有奇异值分解

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{n}\langle v,e_{n} \rangle f_{n}
\end{gather}
$$

其中 $s_{1},\dots,s_{n}$ 都是正数，且 $e_{1},\dots,e_{n}$ 和 $f_{1},\dots,f_{n}$ 都是 $V$ 的标准正交基。我们将证明 $T(B)=E(s_{1}f_{1},\dots,s_{n}f_{n})$。

设 $v \in B$，则 $\lVert v \rVert<1$，从而

$$
\begin{gather}
\frac{\lvert \langle Tv,f_{1} \rangle  \rvert ^{2}}{s_{1}^{2}}+\dots+\frac{\lvert \langle Tv,f_{n} \rangle  \rvert ^{2}}{s_{n}^{2}}=\lvert \langle v,e_{1} \rangle  \rvert ^{2}+\dots+\lvert \langle v,e_{n} \rangle  \rvert ^{2}<1 
\end{gather}
$$

因此 $T(B)\subset E(s_{1}f_{1},\dots,s_{n}f_{n})$。

另一方面，设 $w \in E(s_{1}f_{1},\dots,s_{n}f_{n})$，令

$$
\begin{gather}
v=\frac{\langle w,f_{1} \rangle }{s_{1}}e_{1}+\dots+\frac{\langle w,f_{n} \rangle }{s_{n}}e_{n}
\end{gather}
$$

则 $\lVert v \rVert<1$，并且 $Tv=\langle w,f_{1} \rangle f_{1}+\dots+\langle w,f_{n} \rangle f_{n}=w$，因此 $E(s_{1}f_{1},\dots,s_{n}f_{n})\subset T(B)$。

### Theorem 7.64

设 $T \in L(V)$ 是可逆映射，$E$ 是 $V$ 中的开椭球，则 $T(E)$ 也是一个开椭球。

#### Proof

设 $E=E(s_{1}f_{1},\dots,s_{n}f_{n})$，定义 $S \in L(V)$ 为

$$
\begin{gather}
S(a_{1}f_{1}+\dots+a_{n}f_{n})=a_{1}s_{1}f_{1}+\dots+a_{n}s_{n}f_{n}
\end{gather}
$$

则可以验证 $S$ 将 $B$ 映射到 $E$。于是

$$
\begin{gather}
T(E)=T(S(B))=(TS)(B)
\end{gather}
$$

由于 $s_{1},\dots,s_{n}$ 都是正数，故 $S$ 可逆，因而 [[#Theorem 7.63]] 表明 $TS$ 将 $B$ 映射到一个椭球，这就完成了证明。

回顾一下，符号 $u+\Omega$ 表示 $\Omega$ 整体向 $u$ 的方向平移后的集合。从几何上看，$\Omega$ 与 $u+\Omega$ 是相同的，只是它们的位置不同。

### Definition 7.65 parallelepiped 平行六面体

设 $v_{1},\dots,v_{n}$ 是 $V$ 的基，定义

$$
\begin{gather}
P(v_{1},\dots,v_{n})=\{ a_{1}v_{1}+\dots+a_{n}v_{n} : 0<a_{k}<1 \}
\end{gather}
$$

一个开平行六面体定义为一个形如 $u+P(v_{1},\dots,v_{n})$ 的集合，其中 $u \in V$，且 $v_{1},\dots,v_{n}$ 称为该平行六面体的边。

### Theorem 7.66

设 $u \in V$，$v_{1},\dots,v_{n}$ 是 $V$ 的基，且 $T \in L(V)$ 是可逆的，则

$$
\begin{gather}
T(u+P(v_{1},\dots,v_{n}))=Tu+P(Tv_{1},\dots,Tv_{n})
\end{gather}
$$

这就是说，可逆映射将平行六面体映射到平行六面体。

#### Proof

由于 $T$ 可逆，因此 $Tv_{1},\dots,Tv_{n}$ 是 $V$ 的基。$T$ 的线性性给出

$$
\begin{gather}
T(u+a_{1}v_{1}+\dots+a_{n}v_{n})=Tu+a_{1}Tv_{1}+\dots+a_{n}Tv_{n}
\end{gather}
$$

因此 $T(u+P(v_{1},\dots,v_{n}))=Tu+P(Tv_{1},\dots,Tv_{n})$。

### Definition 7.67 box 长方体

$V$ 中的一个长方体定义为一个形如

$$
\begin{gather}
u+P(r_{1}e_{1},\dots,r_{n}e_{n})
\end{gather}
$$

的集合，其中 $u \in V$，$r_{1},\dots,r_{n}$ 是正数，且 $e_{1},\dots,e_{n}$ 是标准正交基。

显然，由于长方体也是平行六面体，因此可逆映射将长方体映射到平行六面体。这就引出了一个问题：在什么情况下可逆映射能够将长方体映射到长方体？下面的定理给出了答案。

### Theorem 7.68

设 $T \in L(V)$ 是可逆映射，并假设其有奇异值分解

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{n}\langle v,e_{n} \rangle f_{n}
\end{gather}
$$

则对正数 $r_{1},\dots,r_{n}$ 和 $u \in V$，$T$ 将长方体 $u+P(r_{1}e_{1},\dots,r_{n}e_{n})$ 映射到长方体 $Tu+P(r_{1}s_{1}f_{1},\dots,r_{n}s_{n}f_{n})$。

#### Proof

我们有

$$
\begin{gather}
T(u+a_{1}r_{1}e_{1}+\dots+a_{n}r_{n}e_{n})=Tu+a_{1}r_{1}s_{1}f_{1}+\dots+a_{n}r_{n}s_{n}f_{n}
\end{gather}
$$

即 $T(u+P(r_{1}e_{1},\dots,r_{n}e_{n}))=Tu+P(r_{1}s_{1}f_{1},\dots,r_{n}s_{n}f_{n})$。

## Volume via Singular Values

本节我们来展示一个线性算子如何改变一个集合的体积。由于体积（测度）的概念属于分析学的领域，因此在本节中我们只给出一些定理的证明概述，而省略了其中的测度论技术细节。

在各种形状的集合中，长方体的体积概念是最为清晰的，它们将作为我们定义任何形状的体积概念的起点。

### Definition 7.69 volume 体积

设 $\mathbb{F}=\mathbb{R}$，如果 $u \in V$，$r_{1},\dots,r_{n}>0$，且 $e_{1},\dots,e_{n}$ 是标准正交基，则我们定义长方体 $u+P(r_{1}e_{1},\dots,r_{n}e_{n})$ 的体积为

$$
\begin{gather}
\operatorname{vol}(u+P(r_{1}e_{1},\dots,r_{n}e_{n}))=r_{1}\cdots r_{n}
\end{gather}
$$

对于一般的集合 $\Omega$，我们采取一种极限的手段来定义它的体积：我们用一组互不相交的长方体来近似 $\Omega$，然后用长方体的体积之和来近似该集合的体积。对于一大类集合，包括所有开集与闭集，当我们取越来越精细的长方体时，长方体的体积之和将收敛于一个实数（或者正无穷），我们就将这个数定义为 $\Omega$ 的体积 $\operatorname{vol}\Omega$。

### Example 7.70

假设我们需要计算一个开球的体积，我们可以用如图所示的五个长方体来近似它：

![](7-1.png)

如果我们增加长方体的数量，我们将得到一个更好的近似。

现在我们考虑算子 $T \in L(\mathbb{R}^{2})$ 对开球体积的影响。假设

$$
\begin{gather}
Tv=2 \langle v,e_{1} \rangle e_{1}+\langle v,e_{2} \rangle e_{2}
\end{gather}
$$

其中 $e_{1},e_{2}$ 是标准基。这一算子使得所有的长方体在 $e_{1}$ 方向上拉伸了 $2$ 倍，而在 $e_{2}$ 方向上保持不变。

![](7-2.png)

于是，由于这一椭球的体积由变换后的长方体近似，因此在 $T$ 的作用下 $B$ 的体积变成了原来的两倍。

以上例子可以自然地扩展为如下的定理。

### Theorem 7.71

设 $\mathbb{F}=\mathbb{R}$，$T \in L(V)$ 可逆，其有正奇异值 $s_{1},\dots,s_{n}$，且 $\Omega \subset V$，$\operatorname{vol}\Omega$ 有定义，则

$$
\begin{gather}
\operatorname{vol} T(\Omega)=s_{1}\cdots s_{n} \operatorname{vol}\Omega
\end{gather}
$$

#### Proof (sketch)

设 $T$ 有奇异值分解

$$
\begin{gather}
Tv=s_{1}\langle v,e_{1} \rangle f_{1}+\dots+s_{n}\langle v,e_{n} \rangle f_{n}
\end{gather}
$$

用形如 $u+P(r_{1}e_{1},\dots,r_{n}e_{n})$ 的长方体近似 $\Omega$，这些长方体的体积为 $r_{1}\cdots r_{n}$。$T$ 将它们映射到长方体 $Tu+P(r_{1}s_{1}f_{1},\dots,r_{n}s_{n}f_{n})$，其体积为 $(s_{1}\cdots s_{n})(r_{1}\cdots r_{n})$。

算子 $T$ 将一系列近似 $\Omega$ 的长方体映射为了一系列近似 $T(\Omega)$ 的长方体，由于 $T$ 将每个长方体的体积变成了原来的 $s_{1}\cdots s_{n}$ 倍，因此我们就有

$$
\begin{gather}
\operatorname{vol} T(\Omega)=s_{1}\cdots s_{n} \operatorname{vol}\Omega
\end{gather}
$$

后续当我们定义行列式时，我们将证明 $\lvert \det T \rvert=s_{1}\cdots s_{n}$，从而以上定理就可以写成 $\operatorname{vol}T(\Omega)=\lvert \det T \rvert \operatorname{vol}\Omega$。