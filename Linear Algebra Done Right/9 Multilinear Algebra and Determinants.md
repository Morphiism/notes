本章我们首先研究向量空间上的双线性型以及二次型。接下来我们转向向量空间上的多线性型，其中的核心定理是 $n$ 维向量空间上的 $n$-线性型构成的空间具有维数 $1$，这将为我们提供一个简洁且基无关的行列式定义。

本章我们假设 $V,W$ 是 $\mathbb{F}$ 上的有限维非零向量空间。

# 9A Bilinear Forms and Quadratic Forms

## Bilinear Forms

### Definition 9.1 bilinear form 双线性型

$V$ 上的一个双线性型是一个函数 $\beta\colon V\times V\to \mathbb{F}$ 使得

$$
\begin{gather}
v\mapsto\beta(v,u) \quad \text{and} \quad v\mapsto \beta(u,v)
\end{gather}
$$

都是 $V$ 上的线性泛函。

### Example 9.2

(a) 如果 $\mathbb{F}=\mathbb{R}$，那么 $V$ 上的内积 $(u,v)\mapsto \langle u,v \rangle$ 就是一个双线性型。然而，如果 $\mathbb{F}=\mathbb{C}$，那么内积不是双线性型，因为复内积关于第二个位置是共轭线性的，而非线性的。

(b) 更一般地，设 $V$ 是一个实内积空间，$T \in L(V)$，则定义为

$$
\begin{gather}
\beta(u,v)=\langle u,Tv \rangle 
\end{gather}
$$

的 $\beta$ 是一个双线性型。

(c) 我们可以用一个矩阵 $A$ 来表示 $\mathbb{F}^{n}$ 上的双线性型：定义 $\beta_{A}$ 为

$$
\begin{gather}
\beta_{A}((x_{1},\dots,x_{n}),(y_{1},\dots,y_{n}))=\sum_{k=1}^{n} \sum_{j=1}^{n} A_{j,k}x_{j}y_{k}
\end{gather}
$$

则 $\beta_{A}$ 是双线性型。反之，每个 $\mathbb{F}^{n}$ 上的双线性型都可写成以上形式，因此 $\mathbb{F}^{n}$ 上的双线性型与 $n\times n$ 的矩阵之间是一一对应的。

特别地，设 $x=(x_{1},\dots,x_{n}),y=(y_{1},\dots,y_{n})$，每个 $\mathbb{F}^{n}$ 上的双线性型 $\beta$ 都可以写成

$$
\begin{gather}
\beta(x,y)=x^{T}Ay
\end{gather}
$$

其中我们将 $x \in \mathbb{F}^{n}$ 与元素为 $x_{1},\dots,x_{n}$ 的列向量等同。

### Definition 9.3

$V$ 上所有双线性型构成的集合记作 $V^{(2)}$。在函数的加法和数乘下 $V^{(2)}$ 构成了一个向量空间。

受到 [[#Example 9.2]](c) 的启发，我们可以在任意向量空间上定义双线性型的矩阵。

### Definition 9.4

设 $\beta$ 是 $V$ 上的双线性型，$e_{1},\dots,e_{n}$ 是 $V$ 的基。$\beta$ 在基 $e_{1},\dots,e_{n}$ 下的矩阵 $\mathcal{M}(\beta)$ 定义为

$$
\begin{gather}
\mathcal{M}(\beta)_{j,k}=\beta(e_{j},e_{k})
\end{gather}
$$

### Theorem 9.5

设 $e_{1},\dots,e_{n}$ 是 $V$ 的基。则映射 $\beta\mapsto \mathcal{M}(\beta)$ 是一个从 $V^{(2)}$ 到 $\mathbb{F}^{n,n}$ 的同构，从而 $\dim V^{(2)}=(\dim V)^{2}$。

#### Proof

显然 $\beta\mapsto \mathcal{M}(\beta)$ 是线性映射。设 $A \in \mathbb{F}^{n,n}$，定义双线性型 $\beta_{A}$ 为

$$
\begin{gather}
\beta_{A}(x_{1}e_{1}+\dots+x_{n}e_{n},y_{1}e_{1}+\dots+y_{n}e_{n})=\sum_{k=1}^{n} \sum_{j=1}^{n} A_{j,k}x_{j}y_{k}
\end{gather}
$$

容易验证，$\beta_{\mathcal{M}(\beta)}=\beta$ 且 $\mathcal{M}(\beta_{A})=A$，因此 $\beta\mapsto \mathcal{M}(\beta)$ 与 $A\mapsto\beta_{A}$ 互为逆映射，从而两者都是 $V^{(2)}$ 与 $\mathbb{F}^{n,n}$ 之间的同构。根据 $\dim \mathbb{F}^{n,n}=n^{2}$ 即得 $\dim V^{(2)}=(\dim V)^{2}$。

### Theorem 9.6

设 $\beta$ 是 $V$ 上的双线性型，$T \in L(V)$。定义双线性型 $\alpha,\rho$ 为

$$
\begin{gather}
\alpha(u,v)=\beta(u,Tv), \quad \rho(u,v)=\beta(Tu,v)
\end{gather}
$$

则在 $V$ 的基 $e_{1},\dots,e_{n}$ 下有

$$
\begin{gather}
\mathcal{M}(\alpha)=\mathcal{M}(\beta)\mathcal{M}(T), \quad \mathcal{M}(\rho)=\mathcal{M}(T)^{T}\mathcal{M}(\beta)
\end{gather}
$$

这与 [[#Example 9.2]](c) 是一致的：将双线性型 $\beta$ 写成 $x^{T}Ay$ 的形式，则中间的矩阵 $A$ 就是 $\beta$ 的矩阵。那么如果我们将 $y$ 替换为 $By$，那么上述形式就变成了 $x^{T}ABy$，从而 $\alpha$ 的矩阵就是 $AB$。类似地，将 $x$ 替换为 $Cx$，那么我们就有 $(Cx)^{T}Ay=x^{T}C^{T}Ay$，从而 $\rho$ 的矩阵就是 $C^{T}A$。

#### Proof

设 $1\leq j,k\leq n$，则

$$
\begin{align}
\mathcal{M}(\alpha)_{j,k}&=\alpha(e_{j},e_{k}) \\
&=\beta(e_{j},Te_{k}) \\
&=\beta\left( e_{j},\sum_{m=1}^{n} \mathcal{M}(T)_{m,k}e_{m} \right) \\
&=\sum_{m=1}^{n} \beta(e_{j},e_{m})\mathcal{M}(T)_{m,k} \\
&=(\mathcal{M}(\beta)\mathcal{M}(T))_{j,k}
\end{align}
$$

于是 $\mathcal{M}(\alpha)=\mathcal{M}(\beta)\mathcal{M}(T)$。$\rho$ 的矩阵可以类似地计算。

### Theorem 9.7

设 $\beta \in V^{(2)}$，$e_{1},\dots,e_{n}$ 和 $f_{1},\dots,f_{n}$ 是 $V$ 的基，令

$$
\begin{gather}
A=\mathcal{M}(\beta,(e_{1},\dots,e_{n})), \quad B=\mathcal{M}(\beta,(f_{1},\dots,f_{n}))
\end{gather}
$$

且 $C=\mathcal{M}(I,(e_{1},\dots,e_{n}),(f_{1},\dots,f_{n}))$，则

$$
\begin{gather}
A=C^{T}BC
\end{gather}
$$

#### Proof

定义 $T \in L(V)$ 为 $Tf_{k}=e_{k}$，则我们有

$$
\begin{gather}
\mathcal{M}(T,(f_{1},\dots,f_{n}))=C
\end{gather}
$$

定义双线性型 $\alpha,\rho$ 为

$$
\begin{gather}
\alpha(u,v)=\beta(u,Tv), \quad \rho(u,v)=\alpha(Tu,v)=\beta(Tu,Tv)
\end{gather}
$$

则 $\beta(e_{j},e_{k})=\beta(Tf_{j},Tf_{k})=\rho(f_{j},f_{k})$，于是

$$
\begin{align}
A &= \mathcal{M}(\rho,(f_{1},\dots,f_{n})) \\
&=C^{T}\mathcal{M}(\alpha,(f_{1},\dots,f_{n})) \\
&=C^{T}BC
\end{align}
$$

## Symmetric Bilinear Forms

### Definition 9.8 symmetric bilinear form 对称双线性型

称 $\rho \in V^{(2)}$ 是对称的，如果对 $u,w \in V$ 有

$$
\begin{gather}
\rho(u,w)=\rho(w,u)
\end{gather}
$$

$V$ 上的对称双线性型构成的向量空间记作 $V_{\mathrm{sym}}^{(2)}$。

### Example 9.9

(a) 设 $V$ 是实内积空间，则

$$
\begin{gather}
\rho(u,w)=\langle u,w \rangle 
\end{gather}
$$

是一个对称双线性型。

(b) 在实内积空间 $V$ 上，双线性型

$$
\begin{gather}
\rho(u,w)=\langle u,Tw \rangle 
\end{gather}
$$

是对称的当且仅当 $T$ 是自伴算子。(a) 是 $T=I$ 时的特例。

(c) 设 $\rho\colon L(V)\times L(V)\to \mathbb{F}$ 定义为

$$
\begin{gather}
\rho(S,T)=\operatorname{tr} (ST)
\end{gather}
$$

则由于 $\operatorname{tr}$ 是线性泛函，并且 $\operatorname{tr}ST=\operatorname{tr}TS$，故 $\rho$ 是一个对称双线性型。

### Definition 9.10 symmetric matrix 对称矩阵

一个方阵 $A$ 是对称的，如果 $A^{T}=A$。

一个算子在 $V$ 的某个基下有对称矩阵，但不一定在任何基下都有对称矩阵。与之相对，一个双线性型或者没有对称矩阵，或者在任何基下都有对称矩阵。

### Theorem 9.11

设 $\rho \in V^{(2)}$，则以下命题等价。

1. $\rho$ 是对称双线性型。
2. 对任意 $V$ 的基 $e_{1},\dots,e_{n}$，$\mathcal{M}(\rho)$ 是对称矩阵。
3. 存在 $V$ 的基 $e_{1},\dots,e_{n}$ 使得 $\mathcal{M}(\rho)$ 是对称矩阵。
4. 存在 $V$ 的基 $e_{1},\dots,e_{n}$ 使得 $\mathcal{M}(\rho)$ 是对角矩阵。

#### Proof

设 (1) 成立，则我们有 $\rho(e_{j},e_{k})=\rho(e_{k},e_{j})$，因此 $\mathcal{M}(\rho,(e_{1},\dots,e_{n}))$ 是一个对称矩阵，从而 (2) 成立。

显然 (2) 蕴含 (3)。

现在设 (3) 成立，$\mathcal{M}(\rho,(e_{1},\dots,e_{n}))$ 是对称矩阵。设 $u,w \in V$，我们将其写成

$$
\begin{gather}
u=a_{1}e_{1}+\dots+a_{n}e_{n}, \quad v=b_{1}e_{1}+\dots+b_{n}e_{n}
\end{gather}
$$

于是

$$
\begin{align}
\rho(u,w) &= \rho\left( \sum_{j=1}^{n} a_{j}e_{j}, \sum_{k=1}^{n} b_{k}e_{k} \right) \\
&= \sum_{j=1}^{n} \sum_{k=1}^{n} a_{j}b_{k} \rho(e_{j},e_{k}) \\
&= \sum_{k=1}^{n} \sum_{j=1}^{n} a_{j}b_{k}\rho(e_{k},e_{j}) \\
&= \rho\left( \sum_{k=1}^{n} b_{k}e_{k},\sum_{j=1}^{n} a_{j}e_{j} \right) \\
&= \rho(w,u)
\end{align}
$$

于是 $\rho$ 是对称双线性型，从而 (1) 成立。

我们已经证明了 (1)(2)(3) 等价，对角矩阵显然是对称的，因此 (4) 蕴含 (3)，下面我们只需证明 (1) 蕴含 (4)。

我们对 $n=\dim V$ 归纳。$n=1$ 的情况是平凡的，因为 $1\times 1$ 矩阵总是对角的。下设 $n>1$ 且结论对更低维度的空间成立。

设 $\rho$ 是对称双线性型，如果 $\rho=0$，那么 $\rho$ 的矩阵是零矩阵，它是对角矩阵。下面我们设 $\rho\neq 0$，于是存在 $u,w$ 使得 $\rho(u,w)\neq 0$。由于

$$
\begin{gather}
2\rho(u,w)=\rho(u+w,u+w)-\rho(u,u)-\rho(w,w)\neq 0
\end{gather}
$$

因此存在 $v$ 使得 $\rho(v,v)\neq 0$。

令 $U=\{ u \in V : \rho(u,v)=0 \}$，则 $U$ 是线性泛函 $u\mapsto \rho(u,v)$ 的零空间。该线性泛函不可能是零函数，因为 $\rho(v,v)\neq 0$，因此 $\dim U=n-1$。我们对 $\rho|_{U\times U}$ 应用归纳假设，得到基 $e_{1},\dots,e_{n-1}$ 使得 $\rho|_{U\times U}$ 的矩阵是对角矩阵。

由于 $v \not\in U$，故 $e_{1},\dots,e_{n-1},v$ 是 $V$ 的基。根据 $U$ 的定义知 $\rho(e_{k},v)=0=\rho(v,e_{k})$，因此 $\rho$ 在这个基下的矩阵是对角矩阵，这就完成了证明。

以上定理表明每个对称双线性型都可以对角化。在实内积空间中，我们还可以进一步加强这个结果：每个对称双线性型都可以在某个标准正交基上对角化，这是因为实正交矩阵满足 $C^{T}=C^{-1}$。

### Theorem 9.12

设 $V$ 是实内积空间，$\rho$ 是 $V$ 上的对称双线性型，则 $\rho$ 在 $V$ 的某个标准正交基下有对角矩阵。

#### Proof

设 $f_{1},\dots,f_{n}$ 是 $V$ 的标准正交基，$B=\mathcal{M}(\rho,(f_{1},\dots,f_{n}))$，则 $B$ 是对称矩阵（[[#Theorem 9.11]]）。令 $T \in L(V)$ 定义为 $\mathcal{M}(T,(f_{1},\dots,f_{n}))=B$，则 $T$ 是自伴的。

根据谱定理，存在 $V$ 的一个标准正交基 $e_{1},\dots,e_{n}$ 使得 $T$ 有对角矩阵。令 $C=\mathcal{M}(I,(e_{1},\dots,e_{n}),(f_{1},\dots,f_{n}))$，则 $C^{-1}BC$ 是 $T$ 在 $e_{1},\dots,e_{n}$ 下的矩阵。于是我们有

$$
\begin{gather}
\mathcal{M}(\rho,(e_{1},\dots,e_{n}))=C^{T}BC=C^{-1}BC
\end{gather}
$$

后者是对角矩阵。

### Definition 9.13 alternating bilinear form 交错双线性型

称 $\alpha \in V^{(2)}$ 是交错的，如果对 $v \in V$ 有

$$
\begin{gather}
\alpha(v,v)=0
\end{gather}
$$

$V$ 上的交错双线性型构成的向量空间记作 $V_{\mathrm{alt}}^{(2)}$。

### Theorem 9.14

$V$ 上的双线性型 $\alpha$ 是交错的当且仅当对 $u,w \in V$ 有

$$
\begin{gather}
\alpha(u,w)=-\alpha(w,u)
\end{gather}
$$

#### Proof

首先设 $\alpha$ 是交错的，则

$$
\begin{align}
\alpha(u+w,u+w) &= \alpha(u,u)+\alpha(u,w)+\alpha(w,u)+\alpha(w,w) \\
&=\alpha(u,w)+\alpha(w,u) \\
&=0
\end{align}
$$

于是 $\alpha(u,w)=-\alpha(w,u)$。

反之，任取 $v \in V$，则 $\alpha(v,v)=-\alpha(v,v)$，即 $\alpha(v,v)=0$，从而 $\alpha$ 是交错的。

### Theorem 9.15

$V_{\mathrm{sym}}^{(2)}$ 和 $V_{\mathrm{alt}}^{(2)}$ 都是 $V$ 的子空间，并且

$$
\begin{gather}
V^{(2)}=V_{\mathrm{sym}}^{(2)}\oplus  V_{\mathrm{alt}}^{(2)}
\end{gather}
$$

#### Proof

显然，对称/交错双线性型之和也是对称/交错双线性型，它们的数乘也是对称/交错双线性型，且 $0 \in V_{\mathrm{sym}}^{(2)}\cap V_{\mathrm{alt}}^{(2)}$，因此两者都是子空间。

下面我们证明 $V^{(2)}=V_{\mathrm{sym}}^{(2)}+V_{\mathrm{alt}}^{(2)}$。设 $\beta \in V^{(2)}$，定义 $\alpha,\rho$ 为

$$
\begin{gather}
\rho(u,w)=\frac{\beta(u,w)+\beta(w,u)}{2}, \quad \alpha(u,w)=\frac{\beta(u,w)-\beta(w,u)}{2}
\end{gather}
$$

于是 $\beta=\rho +\alpha$，且 $\rho$ 对称，$\alpha$ 交错。

最后，我们证明 $V_{\mathrm{sym}}^{(2)}\cap V_{\mathrm{alt}}^{(2)}=\{ 0 \}$。设 $\beta$ 属于它们的交集，则

$$
\begin{gather}
\beta(u,w)=\beta(w,u)=-\beta(u,w)
\end{gather}
$$

从而 $\beta=0$，这就完成了证明。

## Quadratic Forms

### Definition 9.16 quadratic form 二次型

设 $\beta$ 是 $V$ 上的双线性型，定义 $q_{\beta}\colon V\to \mathbb{F}$ 为 $q_{\beta}(v)=\beta(v,v)$。一个函数 $q\colon V\to \mathbb{F}$ 称为是 $V$ 上的一个二次型，如果存在双线性型 $\beta$ 使得 $q=q_{\beta}$。

注意到，与 $\beta$ 相关的二次型 $q_{\beta}$ 的值只与 $\beta$ 的对称部分有关：$q_{\beta}=0$ 当且仅当 $\beta$ 是交错双线性型。

### Theorem 9.17

设 $n$ 是正整数且 $q\colon \mathbb{F}^{n}\to \mathbb{F}$，则 $q$ 是二次型当且仅当存在 $A_{j,k}\in \mathbb{F}$ 使得

$$
\begin{gather}
q(x_{1},\dots,x_{n})=\sum_{k=1}^{n} \sum_{j=1}^{n} A_{j,k}x_{j}x_{k}
\end{gather}
$$

#### Proof

首先设 $q$ 是二次型，则存在双线性型 $\beta$ 使得 $q=q_{\beta}$。令 $A$ 为 $\beta$ 在标准基下的矩阵，则

$$
\begin{gather}
q(x_{1},\dots,x_{n})=\beta((x_{1},\dots,x_{n}),(x_{1},\dots,x_{n}))=\sum_{k=1}^{n} \sum_{j=1}^{n} A_{j,k}x_{j}x_{k}
\end{gather}
$$

反之，设

$$
\begin{gather}
q(x_{1},\dots,x_{n})=\sum_{k=1}^{n} \sum_{j=1}^{n} A_{j,k}x_{j}x_{k}
\end{gather}
$$

则定义双线性型 $\beta$ 为

$$
\begin{gather}
\beta((x_{1},\dots,x_{n}),(y_{1},\dots,y_{n}))=\sum_{k=1}^{n} \sum_{j=1}^{n} A_{j,k}x_{j}y_{k}
\end{gather}
$$

则 $q=q_{\beta}$。

### Theorem 9.18

设 $q\colon V\to \mathbb{F}$，则以下命题等价。

(a) $q$ 是二次型。

(b) 存在唯一的对称双线性型 $\rho$ 使得 $q=q_{\rho}$。

(c) 对 $\lambda \in \mathbb{F}$ 和 $v \in V$ 有 $q(\lambda v)=\lambda^{2}q(v)$，且

$$
\begin{gather}
(u,w)\mapsto q(u+w)-q(u)-q(w)
\end{gather}
$$

是 $V$ 上的对称双线性型。

(d) 对 $v \in V$ 有 $q(2v)=4q(v)$，且

$$
\begin{gather}
(u,w)\mapsto q(u+w)-q(u)-q(w)
\end{gather}
$$

是 $V$ 上的对称双线性型。

#### Proof

设 (a) 成立，则存在双线性型 $\beta$ 使得 $q=q_{\beta}$。根据 [[#Theorem 9.15]]，存在唯一的对称双线性型 $\rho$ 和交错双线性型 $\alpha$ 使得 $\beta=\rho +\alpha$，于是

$$
\begin{gather}
q=q_{\beta}=q_{\rho}+q_{\alpha}=q_{\rho}
\end{gather}
$$

如果 $\rho' \in V_{\mathrm{sym}}^{(2)}$ 满足 $q=q_{\rho'}$，则 $q_{\rho-\rho'}=0$，从而 $\rho-\rho' \in V_{\mathrm{sym}}^{(2)}\cap V_{\mathrm{alt}}^{(2)}=\{ 0 \}$，即 $\rho=\rho'$。

现在设 (b) 成立，则存在对称双线性型 $\rho$ 使得 $q=q_{\rho}$。如果 $\lambda \in \mathbb{F}$ 且 $v \in V$，则

$$
\begin{gather}
q(\lambda v)=\rho(\lambda v,\lambda v)=\lambda^{2}\rho(v,v)=\lambda^{2}q(v)
\end{gather}
$$

此外，如果 $u,w \in V$，则

$$
\begin{gather}
q(u+w)-q(u)-q(w)=\rho(u+w,u+w)-\rho(u,u)-\rho(w,w)=2\rho(u,w)
\end{gather}
$$

是一个对称双线性型，这就证明了 (c)。

显然 (c) 蕴含 (d)。

最后设 (d) 成立，定义对称双线性型 $\rho$ 为

$$
\begin{gather}
\rho(u,w)=\frac{q(u+w)-q(u)-q(w)}{2}
\end{gather}
$$

则

$$
\begin{gather}
\rho(v,v)=\frac{q(2v)-2q(v)}{2}=\frac{4q(v)-2q(v)}{2}=q(v)
\end{gather}
$$

即 $q=q_{\rho}$，从而 $q$ 是一个二次型。

### Theorem 9.19

设 $q$ 是 $V$ 上的二次型。

(a) 存在 $V$ 的一个基 $e_{1},\dots,e_{n}$ 和 $\lambda_{1},\dots,\lambda_{n}\in \mathbb{F}$ 使得

$$
\begin{gather}
q(x_{1}e_{1}+\dots+x_{n}e_{n})=\lambda_{1}x_{1}^{2}+\dots+\lambda_{n}x_{n}^{2}
\end{gather}
$$

(b) 如果 $\mathbb{F}=\mathbb{R}$ 且 $V$ 是内积空间，那么 (a) 中的基可以取为一个标准正交基。

#### Proof

(a) 存在 $V$ 上的对称双线性型 $\rho$ 使得 $q=q_{\rho}$。[[#Theorem 9.11]] 表明，存在一个基 $e_{1},\dots,e_{n}$ 使得 $\mathcal{M}(\rho)$ 是对角矩阵，我们设

$$
\begin{gather}
\mathcal{M}(\rho)_{k,k}=\rho(e_{k},e_{k})=\lambda_{k}
\end{gather}
$$

则

$$
\begin{align}
q\left( \sum_{k=1}^{n} x_{k}e_{k} \right) &= \rho\left( \sum_{j=1}^{n} x_{j}e_{j},\sum_{k=1}^{n} x_{k}e_{k} \right) \\
&=\sum_{k=1}^{n} \sum_{j=1}^{n} x_{j}x_{k}\rho(e_{j},e_{k}) \\
&=\sum_{k=1}^{n} \lambda_{k}x_{k}^{2}
\end{align}
$$

(b) 在实内积空间上，根据 [[#Theorem 9.12]]，我们可以将 (a) 中的基取为标准正交基。

# 9B Alternating Multilinear Forms

## Multilinear Forms

### Definition 9.20 $m$-linear form

设 $m$ 是正整数，$V$ 上的一个 $m$-线性型是一个函数 $\beta\colon V^{m}\to \mathbb{F}$ 使得它在每个位置都是线性的。具体来说，对 $1\leq k\leq m$ 和 $u_{1},\dots,u_{m}\in V$，

$$
\begin{gather}
v\mapsto\beta(u_{1},\dots,u_{k-1},v,u_{k+1},\dots,u_{m})
\end{gather}
$$

是一个 $V$ 上的线性泛函。

$V$ 上 $m$-线性型构成的向量空间记作 $V^{(m)}$。一个函数 $\beta$ 称为一个多线性型，如果它是某个 $m$-线性型。

多线性型是对线性泛函（$1$-线性型）与双线性型的推广。一个 $m$-线性型也被称为一个 $m$-张量（tensor）。

### Theorem 9.21 alternating multilinear form 交错多线性型

设 $m$ 是正整数，一个 $m$-线性型 $\alpha$ 称为是交错的，如果每当 $j\neq k$ 且 $v_{j}=v_{k}$ 时有 $\alpha(v_{1},\dots,v_{m})=0$。

所有 $V$ 上的交错 $m$-线性型构成的向量空间记作 $V_{\mathrm{alt}}^{(m)}$。

容易证明 $V_{\mathrm{alt}}^{(m)}$ 是 $V^{(m)}$ 的子空间。

### Theorem 9.22

设 $m$ 是正整数，$\alpha$ 是 $V$ 上的交错 $m$-线性型。如果 $v_{1},\dots,v_{m}$ 在 $V$ 上线性相关，则

$$
\begin{gather}
\alpha(v_{1},\dots,v_{m})=0
\end{gather}
$$

#### Proof

根据线性相关引理，存在 $v_{k}$ 属于 $\operatorname{span}(v_{1},\dots,v_{k-1})$，于是

$$
\begin{align}
\alpha(v_{1},\dots,v_{m}) &= \alpha\left( v_{1},\dots,v_{k-1},\sum_{j=1}^{k-1} b_{j}v_{j},v_{k+1},\dots,v_{m} \right) \\
&= \sum_{j=1}^{k-1} b_{j} \alpha(v_{1},\dots,v_{k-1},v_{j},v_{k+1},\dots,v_{m}) \\
&= 0
\end{align}
$$

### Corollary 9.23

设 $m>\dim V$，则 $0$ 是 $V$ 上唯一的交错 $m$-线性型。

#### Proof

如果 $m>\dim V$，那么 $v_{1},\dots,v_{m}\in V$ 总是线性相关的，由 [[#Theorem 9.22]] 即证。

## Alternating Multilinear Forms and Permutations

### Theorem 9.24

设 $m$ 是正整数，$\alpha$ 是 $V$ 上的交错 $m$-线性型，且 $v_{1},\dots,v_{m}\in V$，则在 $\alpha(v_{1},\dots,v_{m})$ 中交换任意两个 $v$ 的位置将使得 $\alpha$ 的值变为原来的 $-1$ 倍。

#### Proof

不妨设我们交换 $v_{1}$ 与 $v_{2}$，考虑

$$
\begin{gather}
\alpha(v_{1}+v_{2},v_{1}+v_{2},v_{3},\dots,v_{m})=0
\end{gather}
$$

仿照 [[#Theorem 9.14]] 的证明展开以上表达式，则我们就有

$$
\begin{gather}
\alpha(v_{1},v_{2},\dots,v_{m})=-\alpha(v_{2},v_{1},\dots,v_{m})
\end{gather}
$$

类似地我们可以证明，交换任意两个 $v$ 的位置等同于乘以 $-1$。

要研究 $\alpha$ 的值在 $v$ 的任意排列下的变化，我们需要一些关于置换的知识。

### Definition 9.25 permutation 置换

设 $m$ 是正整数，$\{ 1,2,\dots,m \}$ 的一个置换是一个组 $(j_{1},\dots,j_{m})$ 使得每个 $k$ 在其中出现且仅出现一次。

$\{ 1,2,\dots,m \}$ 的所有置换构成的集合记作 $S_{m}$。

### Definition 9.26 sign of a permutation 置换的符号

一个置换 $(j_{1},\dots,j_{m})$ 的符号定义为

$$
\begin{gather}
\operatorname{sgn}(j_{1},\dots,j_{m})=(-1)^{N}
\end{gather}
$$

其中 $N$ 是置换 $(j_{1},\dots,j_{m})$ 的逆序数，即满足 $k<\ell$ 而 $j_{k}>j_{\ell}$ 的有序对 $(k,\ell)$ 的数量。

由于一个置换可以分解为若干二元交换的复合，我们只需研究二元交换对置换符号的影响即可。

### Theorem 9.27

在置换中交换两个元素的位置使得置换的符号变为原来的 $-1$ 倍。

#### Proof (sketch)

考虑交换置换中相邻的两个元素，这不影响那两个元素与其它元素的逆序关系，而那两个元素之间的先后关系被逆转了，因此总体的逆序数改变了 $1$。

现在考虑交换相距 $k$ 的两个元素，它可以分解为 $2k+1$ 个相邻交换，因此总体的逆序数改变了 $2k+1 \equiv 1 \pmod{2}$。

### Theorem 9.28

设 $m$ 是正整数且 $\alpha \in V_{\mathrm{alt}}^{(m)}$，则

$$
\begin{gather}
\alpha(v_{j_{1}},\dots,v_{j_{m}})=\operatorname{sgn}(j_{1},\dots,j_{m})\alpha(v_{1},\dots,v_{m})
\end{gather}
$$

其中 $v_{1},\dots,v_{m}\in V$ 且 $(j_{1},\dots,j_{m})\in S_{m}$。

#### Proof

我们可以通过一系列二元交换将 $(j_{1},\dots,j_{m})$ 变成 $(1,\dots,m)$。每个这样的二元交换将置换的符号变成了原来的 $-1$ 倍，同时将 $\alpha$ 的值也变成原来的 $-1$ 倍。在合适的一系列交换后，我们得到了置换 $(1,\dots,m)$，其符号为 $1$，这就完成了证明。

### Theorem 9.29

令 $n=\dim V$，设 $e_{1},\dots,e_{n}$ 是 $V$ 的基，且 $v_{1},\dots,v_{n}\in V$。对 $1\leq k\leq n$，令 $b_{1,k},\dots,b_{n,k}\in \mathbb{F}$ 使得

$$
\begin{gather}
v_{k}=\sum_{j=1}^{n} b_{j,k}e_{j}
\end{gather}
$$

则对 $V$ 上的交错 $n$-线性型 $\alpha$ 有

$$
\begin{gather}
\alpha(v_{1},\dots,v_{n})=\alpha(e_{1},\dots,e_{n}) \sum_{(j_{1},\dots,j_{n})\in S_{n}} \operatorname{sgn}(j_{1},\dots,j_{n}) b_{j_{1},1}\cdots b_{j_{n},n}
\end{gather}
$$

#### Proof

我们有

$$
\begin{align}
\alpha(v_{1},\dots,v_{n}) &= \alpha\left( \sum_{j=1}^{n} b_{j,1}e_{j},\dots,\sum_{j=1}^{n} b_{j,n}e_{j} \right) \\
&=\sum_{(j_{1},\dots,j_{n})} b_{j_{1},1}\cdots b_{j_{n},n} \alpha(e_{j_{1}},\dots,e_{j_{n}}) \\
&=\alpha(e_{1},\dots,e_{n}) \sum_{(j_{1},\dots,j_{n})\in S_{n}} \operatorname{sgn}(j_{1},\dots,j_{n}) b_{j_{1},1}\cdots b_{j_{n},n}
\end{align}
$$

以下是本节的核心定理，它是我们定义行列式的基础。

### Theorem 9.30

向量空间 $V_{\mathrm{alt}}^{(\dim V)}$ 的维数为 $1$。

#### Proof

令 $n=\dim V$。设 $\alpha$ 和 $\alpha'$ 是 $V$ 上的交错 $n$-线性型，$\alpha\neq 0$。取 $e_{1},\dots,e_{n}$ 使得 $\alpha(e_{1},\dots,e_{n})\neq 0$，则存在 $c \in \mathbb{F}$ 使得

$$
\begin{gather}
\alpha'(e_{1},\dots,e_{n})=c\alpha(e_{1},\dots,e_{n})
\end{gather}
$$

且 [[#Theorem 9.22]] 表明 $e_{1},\dots,e_{n}$ 线性无关，从而是 $V$ 的一个基。

设 $v_{1},\dots,v_{n} \in V$，令 $b_{j,k}$ 为 $v_{k}$ 在基 $e_{1},\dots,e_{n}$ 下的第 $j$ 个系数，则

$$
\begin{align}
\alpha'(v_{1},\dots,v_{n}) &= \alpha'(e_{1},\dots,e_{n}) \sum_{(j_{1},\dots,j_{n})\in S_{n}} \operatorname{sgn}(j_{1},\dots,j_{n}) b_{j_{1},1}\cdots b_{j_{n},n} \\
&=c\alpha(e_{1},\dots,e_{n}) \sum_{(j_{1},\dots,j_{n})\in S_{n}} \operatorname{sgn}(j_{1},\dots,j_{n})b_{j_{1},1}\cdots b_{j_{n},n} \\
&=c \alpha(v_{1},\dots,v_{n})
\end{align}
$$

于是 $\alpha'=c\alpha$，这表明 $\alpha',\alpha$ 线性相关，从而 $\dim V_{\mathrm{alt}}^{(n)}\leq 1$。

要证 $\dim V_{\mathrm{alt}}^{(n)}\neq 0$，我们只需证明存在一个非零交错 $n$-线性型。为此，设 $e_{1},\dots,e_{n}$ 是 $V$ 的一个基，$\varphi_{1},\dots,\varphi_{n}\in V^{*}$ 为其对偶基，使得

$$
\begin{gather}
v=\sum_{j=1}^{n} \varphi_{j}(v)e_{j}
\end{gather}
$$

于是对 $v_{1},\dots,v_{n}\in V$，定义

$$
\begin{gather}
\alpha(v_{1},\dots,v_{n})=\sum_{(j_{1},\dots,j_{n})\in S_{n}} \operatorname{sgn}(j_{1},\dots,j_{n}) \varphi_{j_{1}}(v_{1})\cdots \varphi_{j_{n}}(v_{n})
\end{gather}
$$

下面我们验证 $\alpha$ 是一个非零交错 $n$-线性型。

要证 $\alpha$ 是交错的，不妨设 $v_{1}=v_{2}$。对每个置换 $(j_{1},j_{2},\dots,j_{n})$，将第一和第二个元素交换的置换 $(j_{2},j_{1},\dots,j_{n})$ 有相反的符号，因此在求和中每一项 $\varphi_{j_{1}}(v_{1})\varphi_{j_{2}}(v_{2})\cdots \varphi_{j_{n}}(v_{n})$ 均有一个对应的 $-\varphi_{j_{2}}(v_{1})\varphi_{j_{1}}(v_{2})\cdots \varphi_{j_{n}}(v_{n})$，从而 $\alpha(v_{1},v_{1},\dots,v_{n})=0$。同理可证 $v_{j}=v_{k}$ 时 $\alpha$ 的值为 $0$。

最后，我们来证 $\alpha\neq 0$。取 $v_{k}=e_{k}$，由于 $\varphi_{j}(e_{k})=\delta_{jk}$，因此求和中只有 $\varphi_{1}(e_{1})\cdots \varphi_{n}(e_{n})=1$ 这一项不为零，这给出 $\alpha(e_{1},\dots,e_{n})=1$，这就完成了证明。

### Theorem 9.31

令 $n=\dim V$，设 $\alpha$ 是 $V$ 上的非零交错 $n$-线性型，$e_{1},\dots,e_{n}\in V$，则

$$
\begin{gather}
\alpha(e_{1},\dots,e_{n})\neq 0
\end{gather}
$$

当且仅当 $e_{1},\dots,e_{n}$ 线性无关。

#### Proof

设 $\alpha(e_{1},\dots,e_{n})\neq 0$，则 [[#Theorem 9.22]] 的逆否命题给出 $e_{1},\dots,e_{n}$ 线性无关。

反之，设 $e_{1},\dots,e_{n}$ 线性无关，从而是 $V$ 的基。由于 $\alpha\neq 0$，故存在 $v_{1},\dots,v_{n}$ 使得 $\alpha(v_{1},\dots,v_{n})\neq 0$。应用 [[#Theorem 9.29]] 即证。

# 9C Determinants

## Defining the Determinant

### Definition 9.32

设 $m$ 是正整数且 $T \in L(V)$，对 $\alpha \in V_{\mathrm{alt}}^{(m)}$，定义 $\alpha_{T}\in V_{\mathrm{alt}}^{(m)}$ 为

$$
\begin{gather}
\alpha_{T}(v_{1},\dots,v_{m})=\alpha(Tv_{1},\dots,Tv_{m})
\end{gather}
$$

其中 $v_{1},\dots,v_{m}\in V$。

如果 $j\neq k$ 且 $v_{j}=v_{k}$，那么 $Tv_{j}=Tv_{k}$，从而 $\alpha_{T}(v_{1},\dots,v_{m})=0$。这表明 $\alpha_{T}$ 也是一个交错多线性型，从而 $\alpha\mapsto\alpha_{T}$ 是 $V_{\mathrm{alt}}^{(m)}$ 上的一个线性算子。

我们已经知道 $\dim V_{\mathrm{alt}}^{(\dim V)}=1$，而一维向量空间上的线性映射总是等同于一个数乘。对于 $\alpha\mapsto\alpha_{T}$，我们就定义 $T$ 的行列式为那个唯一的标量。

### Definition 9.33 determinant of an operator 算子的行列式

设 $T \in L(V)$，$T$ 的行列式 $\det T$ 定义为 $\mathbb{F}$ 中的唯一元素，使得对任意 $\alpha \in V_{\mathrm{alt}}^{(\dim V)}$ 有

$$
\begin{gather}
\alpha_{T}=(\det T) \alpha
\end{gather}
$$

### Example 9.34

设 $n=\dim V$。

(a) 如果 $I$ 是恒等算子，则 $\alpha_{I}=\alpha$，于是 $\det I=1$。

(b) 设 $\lambda \in \mathbb{F}$，则 $\alpha_{\lambda I}=\lambda^{n}\alpha$，于是 $\det(\lambda I)=\lambda^{n}$。

(c) 更一般地，设 $T \in L(V)$ 且 $\lambda \in \mathbb{F}$，则 $\alpha_{\lambda T}=\lambda^{n}\alpha_{T}=\lambda^{n}(\det T)\alpha$，因此 $\det(\lambda T)=\lambda^{n}\det T$。

(d) 设 $T \in L(V)$，且 $V$ 有一个由 $T$ 的特征向量构成的基 $e_{1},\dots,e_{n}$，对应的特征值为 $\lambda_{1},\dots,\lambda_{n}$，则

$$
\begin{gather}
\alpha_{T}(e_{1},\dots,e_{n})=\alpha(\lambda_{1}e_{1},\dots,\lambda_{n}e_{n})=\lambda_{1}\cdots \lambda_{n} \alpha(e_{1},\dots,e_{n})
\end{gather}
$$

如果 $\alpha\neq 0$，那么 [[#Theorem 9.31]] 表明 $\alpha(e_{1},\dots,e_{n})\neq 0$，从而

$$
\begin{gather}
\det T=\lambda_{1}\cdots \lambda_{n}
\end{gather}
$$

### Definition 9.35 determinant of a matrix 矩阵的行列式

设 $n$ 是正整数，$A$ 是 $\mathbb{F}$ 上的 $n\times n$ 矩阵。令 $T \in L(\mathbb{F}^{n})$ 使得 $T$ 在标准基下的矩阵是 $A$，则 $A$ 的行列式定义为

$$
\begin{gather}
\det A=\det T
\end{gather}
$$

### Example 9.36

(a) 设 $I$ 是 $n\times n$ 恒等矩阵，则它在 $\mathbb{F}^{n}$ 上对应的算子就是恒等算子，从而 $\det I=1$。

(b) 更一般地，设 $A$ 是对角矩阵，对角线元素为 $\lambda_{1},\dots,\lambda_{n}$，则其对应的算子以标准基为特征向量，对应的特征值为 $\lambda_{1},\dots,\lambda_{n}$。[[#Example 9.34]](d) 给出 $\det A=\lambda_{1}\cdots\lambda_{n}$。

下面的定理是所有行列式性质的基石，其中我们用 $(v_{1},\dots,v_{n})$ 来表示以 $v_{k}$ 作为第 $k$ 列的 $n\times n$ 矩阵。

### Theorem 9.37

设 $n$ 是正整数，则将 $v_{1},\dots,v_{n}\in \mathbb{F}^{n}$ 映射到 $\det(v_{1},\dots,v_{n})$ 的函数是 $\mathbb{F}^{n}$ 上的一个交错 $n$-线性型。

#### Proof

设 $e_{1},\dots,e_{n}$ 是 $\mathbb{F}^{n}$ 的标准基，$v_{1},\dots,v_{n}\in \mathbb{F}^{n}$。定义 $T \in L(V)$ 为 $Te_{k}=v_{k}$，则 $T$ 在标准基下的矩阵就是 $(v_{1},\dots,v_{n})$，因此 $\det(v_{1},\dots,v_{n})=\det T$。

令 $\alpha$ 是 $\mathbb{F}^{n}$ 上的交错 $n$-线性型，满足 $\alpha(e_{1},\dots,e_{n})=1$，则

$$
\begin{align}
\det(v_{1},\dots,v_{n}) &= \det T \\
&=(\det T)\alpha(e_{1},\dots,e_{n}) \\
&=\alpha(Te_{1},\dots,Te_{n}) \\
&=\alpha(v_{1},\dots,v_{n})
\end{align}
$$

从而将 $v_{1},\dots,v_{n}$ 映射到 $\det(v_{1},\dots,v_{n})$ 的函数就是 $\alpha$，一个交错 $n$-线性型。

### Theorem 9.38

设 $n$ 是正整数且 $A$ 是 $n\times n$ 矩阵，则

$$
\begin{gather}
\det A=\sum_{(j_{1},\dots,j_{n})\in S_{n}}\operatorname{sgn}(j_{1},\dots,j_{n}) A_{j_{1},1}\cdots A_{j_{n},n}
\end{gather}
$$

#### Proof

应用 [[#Theorem 9.29]]，其中 $e_{1},\dots,e_{n}$ 为标准基，$\alpha$ 为行列式函数。如果 $v_{k}$ 是 $A$ 的第 $k$ 列，则每个 $b_{j,k}$ 等于 $A_{j,k}$。最后，我们有

$$
\begin{gather}
\det(e_{1},\dots,e_{n})=\det I=1
\end{gather}
$$

这就完成了证明。

### Corollary 9.39

设 $A$ 是一个上三角矩阵，对角线元素为 $\lambda_{1},\dots,\lambda_{n}$，则

$$
\begin{gather}
\det A=\lambda_{1}\cdots \lambda_{n}
\end{gather}
$$

#### Proof

如果 $(j_{1},\dots,j_{n})\in S_{n}$ 满足 $(j_{1},\dots,j_{n})\neq (1,\dots,n)$，则存在 $j_{k}>k$，于是 $A_{j_{k},k}=0$。这表明求和 [[#Theorem 9.38]] 中唯一不为零的项只有 $(j_{1},\dots,j_{n})=(1,\dots,n)$ 的项，即 $\lambda_{1}\cdots\lambda_{n}$。

## Properties of Determinants

### Theorem 9.40

(a) 设 $S,T \in L(V)$，则 $\det(ST)=(\det S)(\det T)$。
(b) 设 $A,B$ 是相同大小的方阵，则 $\det(AB)=(\det A)(\det B)$。

#### Proof

(a) 设 $n=\dim V$，取 $\alpha \in V_{\mathrm{alt}}^{(n)}$，$v_{1},\dots,v_{n}\in V$，则

$$
\begin{align}
\alpha_{ST}(v_{1},\dots,v_{n}) &= \alpha(STv_{1},\dots,STv_{n}) \\
&=(\det S)\alpha(Tv_{1},\dots,Tv_{n}) \\
&=(\det S)(\det T)\alpha(v_{1},\dots,v_{n})
\end{align}
$$

即证 $\det ST=(\det S)(\det T)$。

(b) 取 $S,T \in L(V)$ 使得在标准基下 $\mathcal{M}(S)=A,\mathcal{M}(T)=B$，则 $\mathcal{M}(ST)=\mathcal{M}(S)\mathcal{M}(T)=AB$，于是

$$
\begin{gather}
\det AB=\det ST=(\det S)(\det T)=(\det A)(\det B)
\end{gather}
$$

### Theorem 9.41

$T \in L(V)$ 是可逆的当且仅当 $\det T\neq 0$。此外，如果 $T$ 可逆，那么 $\det(T^{-1})=(\det T)^{-1}$。

#### Proof

首先设 $T$ 可逆，则 $TT^{-1}=I$，从而

$$
\begin{gather}
\det(TT^{-1})=(\det T)(\det T^{-1})=\det I=1
\end{gather}
$$

因此 $\det T\neq 0$ 且 $\det(T^{-1})=(\det T)^{-1}$。

反之，设 $\det T\neq 0$。取 $v \in V,v\neq 0$。令 $v,e_{2},\dots,e_{n}$ 是 $V$ 的基，且 $\alpha \in V_{\mathrm{alt}}^{(n)}$ 满足 $\alpha\neq 0$。则 $\alpha(v,e_{2},\dots,e_{n})\neq 0$，从而

$$
\begin{gather}
\alpha(Tv,Te_{2},\dots,Te_{n})=(\det T)\alpha(v,e_{2},\dots,e_{n})\neq 0
\end{gather}
$$

因此 $Tv\neq 0$，即证 $T$ 可逆。

通过取 $T$ 在标准基下的矩阵，我们立即得到：一个方阵 $A$ 是可逆的当且仅当 $\det A\neq 0$。

### Theorem 9.42

设 $T \in L(V)$ 且 $\lambda \in \mathbb{F}$，则 $\lambda$ 是 $T$ 的特征值当且仅当 $\det(\lambda I-T)=0$。

#### Proof

$\lambda$ 是 $T$ 的特征值当且仅当 $T-\lambda I$ 不可逆，当且仅当 $\lambda I-T$ 不可逆，当且仅当 $\det(\lambda I-T)=0$。

### Theorem 9.43

设 $T \in L(V)$ 且 $S \in L(W,V)$ 是可逆映射，则

$$
\begin{gather}
\det(S^{-1}TS)=\det T
\end{gather}
$$

#### Proof

令 $n=\dim V=\dim W$，设 $\tau \in V_{\mathrm{alt}}^{(n)}$，令 $\alpha \in V_{\mathrm{alt}}^{(n)}$ 为

$$
\begin{gather}
\alpha(v_{1},\dots,v_{n})=\tau(S^{-1}v_{1},\dots,S^{-1}v_{n})
\end{gather}
$$

设 $w_{1},\dots,w_{n}\in W$，则

$$
\begin{align}
\tau_{S^{-1}TS}(w_{1},\dots,w_{n}) &= \tau(S^{-1}TSw_{1},\dots,S^{-1}TSw_{n}) \\
&=\alpha(TSw_{1},\dots,TSw_{n}) \\
&=(\det T)\alpha(Sw_{1},\dots,Sw_{n}) \\
&=(\det T)\tau(w_{1},\dots,w_{n})
\end{align}
$$

即证 $\det(S^{-1}TS)=\det T$。

以上定理表明，行列式在基变换下保持不变，于是我们可以定义一个算子的行列式为它在任意一个基下矩阵的行列式，其中后者通过 [[#Theorem 9.38]] 来定义。

### Theorem 9.44

设 $T \in L(V)$ 且 $e_{1},\dots,e_{n}$ 是 $V$ 的基，则

$$
\begin{gather}
\det T=\det \mathcal{M}(T,(e_{1},\dots,e_{n}))
\end{gather}
$$

#### Proof

设 $f_{1},\dots,f_{n}$ 为 $\mathbb{F}^{n}$ 的标准基，定义 $S \in L(\mathbb{F}^{n},V)$ 为 $Sf_{k}=e_{k}$，则

$$
\begin{gather}
\mathcal{M}(S^{-1}TS,(f_{1},\dots,f_{n}))=\mathcal{M}(T,(e_{1},\dots,e_{n}))
\end{gather}
$$

于是

$$
\begin{align}
\det T &= \det(S^{-1}TS) \\
&=\det \mathcal{M}(S^{-1}TS,(f_{1},\dots,f_{n})) \\
&=\det \mathcal{M}(T,(e_{1},\dots,e_{n}))
\end{align}
$$

在复向量空间上，我们还可以有另一个算子行列式的等价定义。

### Theorem 9.45

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，则 $\det T$ 等于 $T$ 的所有特征值的乘积，其中每个特征值重复其重数次。具体来说，设 $\lambda_{1},\dots,\lambda_{m}$ 是 $T$ 的不同特征值，其重数分别为 $d_{1},\dots,d_{m}$，则

$$
\begin{gather}
\det T=\lambda_{1}^{d_{1}}\cdots \lambda_{m}^{d_{m}}
\end{gather}
$$

#### Proof

$V$ 有一个基，使得 $T$ 在这个基下的矩阵是上三角的，其对角线元素为 $\lambda_{1},\dots,\lambda_{m}$，其中 $\lambda_{k}$ 出现了 $d_{k}$ 次（[[8 Operators on Complex Vector Spaces#Theorem 8.22]]）。于是根据 [[#Corollary 9.39]] 即证。

### Theorem 9.46

(a) 设 $A$ 是方阵，则 $\det A^{T}=\det A$。

(b) 设 $T \in L(V)$，$T'$ 是 $T$ 的对偶，则 $\det T'=\det T$。

(c) 设 $V$ 是内积空间且 $T \in L(V)$，$T^{*}$ 是 $T$ 的伴随，则 $\det T^{*}=\overline{\det T}$。

#### Proof

(a) 设 $n$ 是正整数，定义 $\alpha\colon(\mathbb{F}^{n})^{n}\to \mathbb{F}$ 为

$$
\begin{gather}
\alpha(v_{1},\dots,v_{n})=\det((v_{1},\dots,v_{n})^{T})
\end{gather}
$$

[[#Theorem 9.38]] 中的公式表明 $\alpha$ 是一个 $n$-线性型。

设 $j\neq k$ 且 $v_{j}=v_{k}$，如果 $B$ 是一个 $n\times n$ 矩阵，那么 $(v_{1},\dots,v_{n})^{T}B$ 不可能是恒等矩阵 $I$，因为它的第 $j$ 行和第 $k$ 行相同。于是 $(v_{1},\dots,v_{n})^{T}$ 不可逆，从而 $\alpha(v_{1},\dots,v_{n})=0$，因而 $\alpha$ 是交错 $n$-线性型。

最后，设 $e_{1},\dots,e_{n}$ 是标准基，则 $\alpha(e_{1},\dots,e_{n})=\det I=1$，故 $\alpha$ 就是行列式函数，从而 $\det A^{T}=\det A$。

(b) 由 [[3 Linear Maps#Theorem 3.112]] 和 (a) 立即得到。

(c) 取 $V$ 的一个标准正交基，则 $T^{*}$ 在这个基下的矩阵等于 $T$ 的矩阵的共轭转置，从而由 (a) 以及 [[#Theorem 9.38]] 表明

$$
\begin{gather}
\det T^{*}=\overline{\det T}
\end{gather}
$$

### Theorem 9.47

(a) 如果一个方阵的两列或两行相等，则它的行列式为 $0$。
(b) 如果一个方阵的两列或两行交换位置，则它的行列式变成原来的 $-1$ 倍。
(c) 如果一个方阵的一列或一行变成原来的 $c$ 倍，则它的行列式也变成原来的 $c$ 倍。
(d) 如果将一个方阵的一列的标量倍加到另一列上，则它的行列式不变。
(e) 如果将一个方阵的一行的标量倍加到另一行上，则它的行列式不变。

#### Proof

以上的所有性质都可以从函数 $(v_{1},\dots,v_{n})\mapsto \det(v_{1},\dots,v_{n})$ 和 $(v_{1},\dots,v_{n})\mapsto \det((v_{1},\dots,v_{n})^{T})$ 都是交错 $n$-线性型得到。

例如，要证明 (d)，我们不妨设将 $v_{2}$ 的 $c$ 倍加到 $v_{1}$ 上，则

$$
\begin{align}
& \det(v_{1}+cv_{2},v_{2},\dots,v_{n}) \\
& =\det(v_{1},v_{2},\dots,v_{n})+c\det(v_{2},v_{2},\dots,v_{n}) \\
& =\det(v_{1},v_{2},\dots,v_{n})
\end{align}
$$

(e) 由 (d) 以及 $\det A^{T}=\det A$ 得到。其余的性质同理。

以上定理为我们提供了一种利用 Gaussian 消元法计算矩阵行列式的方法。

### Theorem 9.48

设 $V$ 是内积空间，$S \in L(V)$ 是酉算子，则 $\lvert \det S \rvert=1$。

#### Proof

由于 $S$ 是酉算子，$I=S^{*}S$，因此

$$
\begin{gather}
1=\det(S^{*}S)=(\det S^{*})(\det S)=(\overline{\det S})(\det S)=\lvert \det S \rvert ^{2}
\end{gather}
$$

于是 $\lvert \det S \rvert=1$。

### Theorem 9.49

设 $V$ 是内积空间，$T \in L(V)$ 是正算子，则 $\det T\geq 0$。

#### Proof

根据谱定理，$V$ 有一个由 $T$ 的特征向量构成的标准正交基，于是 $T$ 在这个基下的矩阵是对角矩阵，其对角线元素恰是 $T$ 的特征值。正算子的特征值都是非负数，因而 $\det T\geq 0$。

### Theorem 9.50

设 $V$ 是内积空间，$T \in L(V)$ 的奇异值为 $s_{1},\dots,s_{n}$，则

$$
\begin{gather}
\lvert \det T \rvert =\sqrt{ \det(T^{*}T) }=s_{1}\cdots s_{n}
\end{gather}
$$

#### Proof

我们有

$$
\begin{gather}
\lvert \det T \rvert ^{2}=(\overline{\det T})(\det T)=(\det T^{*})(\det T)=\det(T^{*}T)
\end{gather}
$$

两边取平方根为 $\lvert \det T \rvert=\sqrt{ \det(T^{*}T) }$。

令 $s_{1},\dots,s_{n}$ 为 $T$ 的奇异值，则 $s_{1}^{2},\dots,s_{n}^{2}$ 是 $T^{*}T$ 的特征值，对应于 $V$ 的由 $T^{*}T$ 的特征向量构成的标准正交基。因此根据对角矩阵的行列式公式，我们就有

$$
\begin{gather}
\det(T^{*}T)=s_{1}^{2}\cdots s_{n}^{2}
\end{gather}
$$

从而 $\lvert \det T \rvert=s_{1}\cdots s_{n}$。

根据 [[7 Operators on Inner Product Spaces#Theorem 7.71]] 我们有推论。

### Corollary 9.51

设 $T \in L(\mathbb{R}^{n})$ 且 $\Omega \subset \mathbb{R}^{n}$，$\operatorname{vol}\Omega$ 有定义，则

$$
\begin{gather}
\operatorname{vol}T(\Omega)=\lvert \det T \rvert \operatorname{vol}\Omega
\end{gather}
$$

### Theorem 9.52

设 $\mathbb{F}=\mathbb{C}$ 且 $T \in L(V)$，$\lambda_{1},\dots,\lambda_{m}$ 为 $T$ 的不同特征值，其重数为 $d_{1},\dots,d_{m}$，则

$$
\begin{gather}
\det(zI-T)=(z-\lambda_{1})^{d_{1}}\cdots (z-\lambda_{m})^{d_{m}}
\end{gather}
$$

#### Proof

存在 $V$ 的一个基，使得 $T$ 在这个基下的矩阵有上三角矩阵，其中 $\lambda_{k}$ 在对角线上出现了 $d_{k}$ 次。于是在这个基下 $zI-T$ 有上三角矩阵，在对角线上 $z-\lambda_{k}$ 出现了 $d_{k}$ 次，这就完成了证明。

以上定理给出了 $V$ 上算子 $T$ 的特征多项式的一个等价定义。此外，它也允许我们在实向量空间上定义特征多项式，而在其上可能没有特征值，从而基于特征值与重数的定义并不适用。

### Definition 9.53 characteristic polynomial 特征多项式

设 $T \in L(V)$，则 $T$ 的特征多项式定义为 $\det(zI-T)$。

以上定理允许我们将 Cayley-Hamilton 定理推广到实向量空间。

### Theorem 9.54 (Cayley-Hamilton)

设 $T \in L(V)$ 且 $q$ 是 $T$ 的特征多项式，则 $q(T)=0$。

#### Proof

$\mathbb{F}=\mathbb{C}$ 的情况已在 [[8 Operators on Complex Vector Spaces#Theorem 8.20 (Cayley-Hamilton)]] 中证明。

现在设 $\mathbb{F}=\mathbb{R}$，固定 $V$ 的一个基，$A=\mathcal{M}(T)$。令 $S \in L(\mathbb{C}^{\dim V})$ 使得 $S$ 在这个基下的矩阵为 $A$，则对 $z \in \mathbb{R}$ 有

$$
\begin{gather}
q(z)=\det(zI-T)=\det(zI-A)=\det(zI-S)
\end{gather}
$$

则 $q$ 也是 $S$ 的特征多项式，从而 $\mathbb{F}=\mathbb{C}$ 的情况给出

$$
\begin{gather}
q(S)=q(A)=q(T)=0
\end{gather}
$$

### Theorem 9.55

设 $T \in L(V)$，令 $n=\dim V$，则 $T$ 的特征多项式具有形式

$$
\begin{gather}
z^{n}-(\operatorname{tr}T)z^{n-1}+\dots+(-1)^{n}(\det T)
\end{gather}
$$

#### Proof

特征多项式 $q(z)$ 的常数项等于 $q(0)=\det(-T)=(-1)^{n}\det T$。

现在固定 $V$ 的一个基，令 $A=\mathcal{M}(T)$。则 $zI-T$ 在这个基下的矩阵为 $zI-A$，而根据 [[#Theorem 9.38]]，要得到 $z^{n-1}$ 项，我们必须将置换 $(j_{1},\dots,j_{n})$ 取为 $(1,\dots,n)$，其对应的项为

$$
\begin{gather}
(z-A_{1,1})\cdots (z-A_{n,n})
\end{gather}
$$

其展开式中 $z^{n-1}$ 项的系数为 $-(A_{1,1}+\dots+A_{n,n})$，即 $-\operatorname{tr}T$。

最后我们给出矩阵行列式的一个上界估计。

### Theorem 9.56 (Hadamard)

设 $A$ 是 $n\times n$ 矩阵，其各列为 $v_{1},\dots,v_{n}$，则

$$
\begin{gather}
\lvert \det A \rvert \leq \prod_{k=1}^{n} \lVert v_{k} \rVert 
\end{gather}
$$

#### Proof

如果 $A$ 不可逆，那么 $\det A=0$，不等式显然成立。

如果 $A$ 可逆，QR 分解表明，存在酉矩阵 $Q$ 和上三角矩阵 $R$ 使得 $A=QR$，于是

$$
\begin{align}
\lvert \det A \rvert &= \lvert \det Q \rvert \lvert \det R \rvert  \\
&=\lvert \det R \rvert  \\
&=\prod_{k=1}^{n} R_{k,k} \\
&\leq \prod_{k=1}^{n} \lVert R_{\cdot,k} \rVert  \\
&=\prod_{k=1}^{n} \lVert QR_{\cdot,k} \rVert  \\
&=\prod_{k=1}^{n} \lVert v_{k} \rVert 
\end{align}
$$

下面我们给出 Hadamard 不等式的一个几何解释。设 $T \in L(\mathbb{R}^{n})$ 将标准基 $e_{k}$ 映射到 $Te_{k}=v_{k}$。则 $T$ 将长方体 $P(e_{1},\dots,e_{n})$ 映射到平行六面体 $P(v_{1},\dots,v_{n})$。由于 $\operatorname{vol}P(e_{1},\dots,e_{n})=1$，故由 [[#Corollary 9.51]] 知 $P(v_{1},\dots,v_{n})$ 的体积为 $\lvert \det T \rvert=\lvert \det A \rvert$。因此 Hadamard 不等式可以解释如下：在所有具有边长 $\lVert v_{1} \rVert,\dots,\lVert v_{n} \rVert$ 的平行六面体中，各边正交的长方体有最大的体积。