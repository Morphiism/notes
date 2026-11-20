本章我们来定义多维 Riemann 积分，并推导它的性质。

# 10 The Integral over a Rectangle

我们首先定义长方体的体积。令

$$
\begin{gather}
Q=[a_{1},b_{1}]\times \dots \times [a_{n},b_{n}]
\end{gather}
$$

为 $\mathbb{R}^{n}$ 中的长方体，其中每个 $[a_{i},b_{i}]$ 称为 $Q$ 的一个分量区间。称

$$
\begin{gather}
\max(b_{1}-a_{1},\dots,b_{n}-a_{n})
\end{gather}
$$

为 $Q$ 的宽度，而

$$
\begin{gather}
v(Q)=(b_{1}-a_{1})\cdots (b_{n}-a_{n})
\end{gather}
$$

称为 $Q$ 的体积。当 $n=1$ 时，我们称 $v(Q)=b_{1}-a_{1}$ 为 $[a_{1},b_{1}]$ 的长度。

### Definition 10.1 partition 划分

给定闭区间 $[a,b]$，它的一个划分 $P$ 是 $[a,b]$ 的一个包含 $a,b$ 的有限子集。我们通常将 $P$ 的元素按升序排列，记作

$$
\begin{gather}
P=\{ a=t_{0}<t_{1}<\dots<t_{k}=b \}
\end{gather}
$$

每个 $[t_{i-1},t_{i}]$ 都称为 $[a,b]$ 的一个由 $P$ 确定的子区间。

给定长方体

$$
\begin{gather}
Q=[a_{1},b_{1}]\times\cdots\times [a_{n},b_{n}]
\end{gather}
$$

$Q$ 的一个划分 $P$ 是一个 $n$-元组 $(P_{1},\dots,P_{n})$ 使得 $P_{j}$ 是 $[a_{j},b_{j}]$ 的一个划分。如果 $I_{j}$ 是 $[a_{j},b_{j}]$ 的一个由 $P_{j}$ 确定的子区间，则长方体

$$
\begin{gather}
R=I_{1}\times\dots \times I_{n}
\end{gather}
$$

称为 $Q$ 的一个由 $P$ 确定的子长方体。所有这些子长方体宽度的最大值称为 $P$ 的网格。

### Definition 10.2 lower sum 下和，upper sum 上和

设 $Q$ 是 $\mathbb{R}^{n}$ 中的长方体，$f\colon Q\to \mathbb{R}$ 是有界的。设 $P$ 是 $Q$ 的一个划分，对任意由 $P$ 确定的子长方体 $R$，令

$$
\begin{gather}
m_{R}(f)=\inf_{\mathbf{x}\in R} f(\mathbf{x}) \\
M_{R}(f)=\sup_{\mathbf{x}\in R} f(\mathbf{x})
\end{gather}
$$

我们定义 $f$ 由 $P$ 确定的下和与上和分别为

$$
\begin{gather}
L(f,P)=\sum_{R} m_{R}(f) v(R) \\
U(f,P)=\sum_{R} M_{R}(f)v(R)
\end{gather}
$$

其中求和遍历所有由 $P$ 确定的子长方体 $R$。

设 $P=(P_{1},\dots,P_{n})$ 是长方体 $Q$ 的划分，如果 $P''$ 是 $Q$ 的划分使得对所有 $j$ 有 $P_{j}\subset P_{j}''$，则称 $P''$ 是 $P$ 的一个细化。给定 $Q$ 的两个划分 $P,P'$，划分

$$
\begin{gather}
P''=(P_{1}\cup P_{1}',\dots,P_{n}\cup P_{n}')
\end{gather}
$$

称为 $P$ 和 $P'$ 的公共细化。

### Lemma 10.3

设 $P$ 是长方体 $Q$ 的划分，$f\colon Q\to \mathbb{R}$ 是有界的，如果 $P''$ 是 $P$ 的细化，那么

$$
\begin{gather}
L(f,P)\leq L(f,P''), \quad U(f,P'')\leq U(f,P)
\end{gather}
$$

#### Proof

设

$$
\begin{gather}
Q=[a_{1},b_{1}]\times \dots \times [a_{n},b_{n}]
\end{gather}
$$

根据归纳法，我们只需证明 $P''$ 等于 $P$ 的某个分量添加了一个点的情况。不妨设 $P=(P_{1},\dots,P_{n})$，

$$
\begin{gather}
P_{1}=\{ a_{1}=t_{0}<t_{1}<\dots<t_{k}=b_{1} \}
\end{gather}
$$

$P''_{1}=P_{1}\cup \{ q \}$，且 $q \in(t_{i-1},t_{i})$。

![](3-1.png)

我们首先比较下和。$L(f,P)$ 中涉及的大多数子长方体都与 $L(f,P'')$ 涉及的相同，除了形如

$$
\begin{gather}
R_{S}=[t_{i-1},t_{i}] \times S
\end{gather}
$$

的子长方体被替换为

$$
\begin{gather}
R_{S}'=[t_{i-1},q]\times S \quad \text{and} \quad R_{S}''=[q,t_{i}]\times S
\end{gather}
$$

在 $\mathbf{x}\in R_{S}'$ 和 $\mathbf{x}\in R_{S}''$ 上有 $m_{R_{S}}(f)\leq f(\mathbf{x})$，因此

$$
\begin{gather}
m_{R_{S}}(f)\leq m_{R_{S}'}(f), \quad m_{R_{S}}(f)\leq m_{R_{S}''}(f)
\end{gather}
$$

显然 $v(R_{S})=v(R_{S}')+v(R_{S}'')$，于是

$$
\begin{gather}
m_{R_{S}}(f)v(R_{S})\leq m_{R_{S}'}(f)v(R_{S}')+m_{R_{S}''}(f)v(R_{S}'')
\end{gather}
$$

从而

$$
\begin{gather}
L(f,P)\leq L(f,P'')
\end{gather}
$$

上和的不等式同理。

### Lemma 10.4

设 $Q$ 是长方体，$f\colon Q\to \mathbb{R}$ 是有界的，如果 $P$ 和 $P'$ 是 $Q$ 的划分，那么

$$
\begin{gather}
L(f,P)\leq U(f,P')
\end{gather}
$$

#### Proof

如果 $P=P'$，由于对任意子长方体 $R$，有 $m_{R}(f)\leq M_{R}(f)$，因此 $L(f,P)\leq U(f,P)$。

一般地，设 $P''$ 为 $P$ 和 $P'$ 的公共细化，则根据 [[#Lemma 10.3]] 即得

$$
\begin{gather}
L(f,P)\leq L(f,P'')\leq U(f,P'')\leq U(f,P')
\end{gather}
$$

现在我们来定义积分。

### Definition 10.5 lower integral 下积分，upper integral 上积分，integrable 可积的

设 $Q$ 是长方体，$f\colon Q\to \mathbb{R}$ 是有界函数。设 $P$ 遍历 $Q$ 上的所有划分，定义

$$
\begin{gather}
\underline{\int_{Q}} f =\sup_{P} L(f,P), \quad \overline{\int_{Q}} f=\inf_{P}U(f,P)
\end{gather}
$$

分别称为 $f$ 在 $Q$ 上的下积分与上积分。如果 $f$ 在 $Q$ 上的上下积分相等，我们就称 $f$ 在 $Q$ 上 Riemann 可积，并定义 $f$ 在 $Q$ 上的 Riemann 积分为

$$
\begin{gather}
\int_{Q} f=\int_{\mathbf{x}\in Q} f(\mathbf{x})=\underline{\int_{Q}} f=\overline{\int_{Q}} f
\end{gather}
$$

一个常用的可积性条件如下：

### Theorem 10.6

设 $Q$ 是长方体，$f\colon Q\to \mathbb{R}$ 有界，则

$$
\begin{gather}
\underline{\int_{Q}} f\leq \overline{\int_{Q}} f
\end{gather}
$$

等式成立，即 $f$ 在 $Q$ 上可积，当且仅当对任意 $\varepsilon>0$，存在 $Q$ 的划分 $P$ 使得

$$
\begin{gather}
U(f,P)-L(f,P)<\varepsilon
\end{gather}
$$

#### Proof

固定划分 $P'$，根据 [[#Lemma 10.4]] 可知对任意划分 $P$ 有 $L(f,P)\leq U(f,P')$，对 $P$ 取上确界得

$$
\begin{gather}
\underline{\int_{Q}} f\leq U(f,P')
\end{gather}
$$

再对 $P'$ 取下确界即得

$$
\begin{gather}
\underline{\int_{Q}} f\leq \overline{\int_{Q}} f
\end{gather}
$$

现在假设下积分等于上积分。根据上下确界的定义，存在划分 $P$ 使得 $L(f,P)$ 和 $\int_{Q}f$ 的误差在 $\varepsilon /2$ 以内，并且存在划分 $P'$ 使得 $U(f,P)$ 和 $\int_{Q}f$ 的误差在 $\varepsilon /2$ 以内。令 $P''$ 为 $P,P'$ 的公共细化，则

$$
\begin{gather}
L(f,P)\leq L(f,P'')\leq \int_{Q} f\leq U(f,P'')\leq U(f,P')
\end{gather}
$$

从而 $L(f,P'')$ 和 $U(f,P'')$ 的误差在 $\varepsilon$ 以内。

反之，假设下积分不等于上积分，令

$$
\begin{gather}
\varepsilon=\overline{\int_{Q}} f-\underline{\int_{Q}} f>0
\end{gather}
$$

则对任意划分 $P$ 都有

$$
\begin{gather}
L(f,P)\leq \underline{\int_{Q}} f<\overline{\int_{Q}} f\leq U(f,P)
\end{gather}
$$

于是 $U(f,P)-L(f,P)\geq\varepsilon$。

### Theorem 10.7

常值函数 $f=c$ 是可积的。特别地，如果 $Q$ 是长方体且 $P$ 是 $Q$ 的划分，则

$$
\begin{gather}
\int_{Q} c=c v(Q)=c \sum_{R} v(R)
\end{gather}
$$

其中的求和遍历所有由 $P$ 确定的子长方体 $R$。

#### Proof

显然我们有 $m_{R}(f)=c=M_{R}(f)$，从而

$$
\begin{gather}
L(f,P)=c\sum_{R} v(R)=U(f,P)
\end{gather}
$$

因此 $c$ 可积，而由于 $L(f,P)\leq \int_{Q}c\leq U(f,P)$，$\int_{Q}c=c\sum_{R}v(R)$。

以上结果对任意划分 $P$ 成立。特别地，如果 $P$ 是平凡划分，其中的子长方体只有 $Q$，那么

$$
\begin{gather}
\int_{Q}c=c v(Q)
\end{gather}
$$

### Corollary 10.8

设 $Q$ 是 $\mathbb{R}^{n}$ 中的长方体，$\{ Q_{1},\dots,Q_{k} \}$ 是一系列覆盖 $Q$ 的长方体，则

$$
\begin{gather}
v(Q)\leq \sum_{i=1}^{k} v(Q_{i})
\end{gather}
$$

#### Proof

取一个长方体 $Q'$ 包含所有 $Q_{1},\dots,Q_{k}$，并使用 $Q_{1},\dots,Q_{k}$ 的分量区间来定义 $Q'$ 的一个划分 $P$，使得每个 $Q_{i}$ 都等于一系列子长方体的并集。

![](3-2.png)

根据 [[#Theorem 10.7]]，我们有

$$
\begin{gather}
v(Q)=\sum_{R\subset Q} v(R)
\end{gather}
$$

其中 $R$ 遍历包含于 $Q$ 的子长方体。由于每个 $R\subset Q$ 都包含于某个 $Q_{i}$ 中，故

$$
\begin{gather}
\sum_{R\subset Q} v(R)\leq \sum_{i=1}^{k} \sum_{R\subset Q_{i}} v(R)
\end{gather}
$$

再应用 [[#Theorem 10.7]]，我们就有

$$
\begin{gather}
\sum_{R\subset Q_{i}} v(R)=v(Q_{i})
\end{gather}
$$

这就完成了证明。

# 11 Existence of the Integral

本节我们给出积分存在是一个充分必要条件，它涉及所谓零测集的概念。

### Definition 11.1 set of measure zero 零测集

设 $A\subset \mathbb{R}^{n}$，我们称 $A$ 的测度为零，如果对任意 $\varepsilon>0$，存在可数个长方体 $Q_{1},Q_{2},\dots$ 覆盖 $A$，且

$$
\begin{gather}
\sum_{i=1}^{\infty} v(Q_{i})<\varepsilon
\end{gather}
$$

在以上不等式成立时，我们说 $Q_{1},Q_{2},\dots$ 的总体积小于 $\varepsilon$。

### Theorem 11.2

(a) 如果 $B\subset A$ 且 $A$ 是零测集，那么 $B$ 也是零测集。
(b) 设 $A$ 等于可数个集合 $A_{1},A_{2},\dots$ 的并集，如果每个 $A_{i}$ 的测度为零，那么 $A$ 是零测集。
(c) 集合 $A$ 的测度为零当且仅当对任意 $\varepsilon>0$，存在可数个开长方体 $\operatorname{Int}Q_{1},\operatorname{Int}Q_{2},\dots$ 覆盖 $A$，使得
$$
\begin{gather}
\sum_{i=1}^{\infty} v(Q_{i})<\varepsilon
\end{gather}
$$
(d) 如果 $Q$ 是 $\mathbb{R}^{n}$ 中的长方体，那么 $\operatorname{Bd}Q$ 的测度为零，而 $Q$ 的测度不为零。

#### Proof

(a) 是显然的。要证明 (b)，对每个 $j$，选取 $A_{j}$ 的覆盖

$$
\begin{gather}
Q_{1j},Q_{2j},\dots
\end{gather}
$$

使得它们的总体积小于 $\varepsilon /2^{j}$。于是 $\{ Q_{ij} \}$ 覆盖 $A$，并且它的总体积小于

$$
\begin{gather}
\sum_{j=1}^{\infty} \frac{\varepsilon}{2^{j}}=\varepsilon
\end{gather}
$$

(c) 如果开长方体 $\operatorname{Int}Q_{1},\operatorname{Int}Q_{2},\dots$ 覆盖 $A$，那么闭长方体 $Q_{1},Q_{2},\dots$ 也覆盖 $A$，于是由给定条件知 $A$ 的测度为零。

反之，设 $A$ 的测度为零，用总体积小于 $\varepsilon /2$ 的长方体 $Q_{1}',Q_{2}',\dots$ 覆盖 $A$。对每个 $i$，选取 $Q_{i}$ 满足

$$
\begin{gather}
Q_{i}'\subset \operatorname{Int}Q_{i}, \quad v(Q_{i})\leq 2v(Q_{i}')
\end{gather}
$$

则开长方体 $\operatorname{Int}Q_{1},\operatorname{Int}Q_{2},\dots$ 满足给定的条件。

(d) 令

$$
\begin{gather}
Q=[a_{1},b_{1}]\times\dots \times [a_{n},b_{n}]
\end{gather}
$$

我们称 $Q$ 中满足 $x_{i}=a_{i}$ 或 $x_{i}=b_{i}$ 的子集为 $Q$ 的一个面，$\operatorname{Bd}Q$ 为 $Q$ 的所有面的并集。每个面在 $\mathbb{R}^{n}$ 中是零测集：满足 $x_{i}=a_{i}$ 的面可以被长方体

$$
\begin{gather}
[a_{1},b_{1}]\times\dots \times [a_{i},a_{i}+\delta]\times\dots \times [a_{n},b_{n}]
\end{gather}
$$

覆盖，通过选取足够小的 $\delta$，我们可以使它的体积任意小。由于 $\operatorname{Bd}Q$ 等于有限个面的并集，故它的测度为零。

假设 $Q$ 的测度为零，我们推导一个矛盾。令 $\varepsilon=v(Q)$，根据 (c)，我们可以用总体积小于 $\varepsilon$ 的开长方体覆盖 $Q$。由于 $Q$ 是紧致的，故存在一个有限子覆盖 $\operatorname{Int}Q_{1},\dots,\operatorname{Int}Q_{k}$，满足

$$
\begin{gather}
\sum_{i=1}^{k} v(Q_{i})<\varepsilon=v(Q)
\end{gather}
$$

这与 [[#Corollary 10.8]] 矛盾。

下面我们给出本节的主定理。

### Theorem 11.3

设 $Q$ 是 $\mathbb{R}^{n}$ 中的长方体，$f\colon Q\to \mathbb{R}$ 有界。设 $D$ 为 $f$ 的不连续点构成的集合，则 $f$ 在 $Q$ 上可积当且仅当 $D$ 的测度为零（几乎处处连续）。

#### Proof

选取 $M$ 使得对 $\mathbf{x}\in Q$ 有 $\lvert f(\mathbf{x}) \rvert\leq M$。

**第一步** 我们证明 $D$ 的测度为零蕴含 $\int_{Q}f$ 存在。思路是在不连续点附近控制体积，在连续点附近控制振幅。

任取 $\varepsilon>0$，我们令

$$
\begin{gather}
\varepsilon'=\frac{\varepsilon}{2M+2v(Q)}
\end{gather}
$$

首先我们用总体积小于 $\varepsilon'$ 的开长方体 $\operatorname{Int}Q_{1},\operatorname{Int}Q_{2},\dots$ 覆盖 $D$。下面，对于 $\mathbf{a}\not\in D$，由于 $f$ 在 $\mathbf{a}$ 处连续，我们可以选取包含 $\mathbf{a}$ 的开长方体 $\operatorname{Int}Q_{\mathbf{a}}$ 使得

$$
\begin{gather}
\mathbf{x} \in Q_{\mathbf{a}}\cap Q \implies \lvert f(\mathbf{x})-f(\mathbf{a}) \rvert <\varepsilon'
\end{gather}
$$

则 $\operatorname{Int}Q_{i}$ 和 $\operatorname{Int}Q_{\mathbf{a}}$ 覆盖了 $Q$。由于 $Q$ 紧致，存在有限子覆盖（经过重新编号）

$$
\begin{gather}
\operatorname{Int}Q_{1},\dots,\operatorname{Int}Q_{k},\operatorname{Int}Q_{\mathbf{a}_{1}},\dots,\operatorname{Int}Q_{\mathbf{a}_{\ell}}
\end{gather}
$$

记 $Q_{j}'=Q_{\mathbf{a}_{j}}$，并将 $Q_{i}$ 和 $Q_{j}'$ 分别替换为 $Q_{i}\cap Q$ 和 $Q_{j}'\cap Q$，并仍记作 $Q_{i}$ 和 $Q_{j}'$，则长方体

$$
\begin{gather}
Q_{1},\dots,Q_{k},Q_{1}',\dots,Q_{\ell}'
\end{gather}
$$

覆盖 $Q$，并满足条件

$$
\begin{gather}
\sum_{i=1}^{k} v(Q_{i})<\varepsilon' \tag{1} \\
\mathbf{x},\mathbf{y}\in Q_{j}' \implies \lvert f(\mathbf{x})-f(\mathbf{y}) \rvert <2\varepsilon' \tag{2}
\end{gather}
$$

现在我们用 $Q_{1},\dots,Q_{k},Q_{1}',\dots,Q_{\ell}'$ 的分量区间来构造 $Q$ 的划分 $P$。

![](3-3.png)

将 $P$ 确定的子长方体划分为两个不相交的类 $\mathcal{R},\mathcal{R}'$，使得每个 $R\in \mathcal{R}$ 都包含于某个 $Q_{i}$，而每个 $R\in \mathcal{R}'$ 包含于某个 $Q_{j}'$。根据 $(2)$，我们有

$$
\begin{gather}
\sum_{R \in \mathcal{R}} (M_{R}(f)-m_{R}(f))v(R)\leq 2M \sum_{R \in \mathcal{R}} v(R) \\
\sum_{R \in \mathcal{R}'}(M_{R}(f)-m_{R}(f))v(R)\leq 2\varepsilon' \sum_{R \in \mathcal{R}'} v(R)
\end{gather}
$$

此外，

$$
\begin{gather}
\sum_{R \in \mathcal{R}} v(R)\leq \sum_{i=1}^{k} \sum_{R\subset Q_{i}} v(R)=\sum_{i=1}^{k} v(Q_{i})<\varepsilon' \\
\sum_{R \in \mathcal{R}'} v(R)\leq \sum_{R\subset Q} v(R)=v(Q)
\end{gather}
$$

于是

$$
\begin{gather}
U(f,P)-L(f,P)\leq 2M\varepsilon'+2v(Q) \varepsilon'=\varepsilon
\end{gather}
$$

**第二步** 我们定义 $f$ 的振荡，并将其与 $f$ 的连续性关联。

给定 $\mathbf{a}\in Q$ 和 $\delta>0$，令

$$
\begin{gather}
A_{\delta}=\{ f(\mathbf{x}) : \mathbf{x}\in Q, \lvert \mathbf{x}-\mathbf{a} \rvert <\delta \}
\end{gather}
$$

并令 $M_{\delta}(f)=\sup A_{\delta},m_{\delta}(f)=\inf A_{\delta}$。我们定义 $f$ 在 $\mathbf{a}$ 的振荡为

$$
\begin{gather}
\nu(f;\mathbf{a})=\inf_{\delta>0} (M_{\delta}(f)-m_{\delta}(f))
\end{gather}
$$

则 $\nu(f;\mathbf{a})\geq 0$。我们证明 $\nu(f;\mathbf{a})=0$ 当且仅当 $f$ 在 $\mathbf{a}$ 处连续。

如果 $f$ 在 $\mathbf{a}$ 处连续，则给定 $\varepsilon>0$，存在 $\delta>0$ 使得对 $\mathbf{x}\in Q$ 有

$$
\begin{gather}
\lvert \mathbf{x}-\mathbf{a} \rvert <\delta \implies f(\mathbf{a})-\varepsilon <f(\mathbf{x})<f(\mathbf{a})+\varepsilon
\end{gather}
$$

于是

$$
\begin{gather}
f(\mathbf{a})-\varepsilon\leq m_{\delta}(f)\leq M_{\delta}(f)\leq f(\mathbf{a})+\varepsilon
\end{gather}
$$

即 $\nu(f;\mathbf{a})\leq 2\varepsilon$。由 $\varepsilon$ 的任意性知 $\nu(f;\mathbf{a})=0$。

反之，设 $\nu(f;\mathbf{a})=0$。给定 $\varepsilon>0$，存在 $\delta>0$ 使得

$$
\begin{gather}
M_{\delta}(f)-m_{\delta}(f)<\varepsilon
\end{gather}
$$

由于当 $\mathbf{x}\in Q$ 且 $\lvert \mathbf{x}-\mathbf{a} \rvert<\delta$ 时

$$
\begin{gather}
m_{\delta}(f)\leq f(\mathbf{x})\leq M_{\delta}(f)
\end{gather}
$$

因此 $f(\mathbf{x})$ 和 $f(\mathbf{a})$，作为 $[m_{\delta}(f),M_{\delta}(f)]$ 中的点，它们间的距离小于 $\varepsilon$。从而 $f$ 在 $\mathbf{a}$ 处连续。

**第三步** 我们证明 $f$ 可积蕴含 $D$ 的测度为零。

对正整数 $m$，令

$$
\begin{gather}
D_{m}=\{ \mathbf{a} : \nu(f;\mathbf{a})\geq 1 /m \}
\end{gather}
$$

则根据第二步，$D=\bigcup_{m=1}^{\infty}D_{m}$。下面我们来证明每个 $D_{m}$ 的测度为零。

固定 $m$，对 $\varepsilon>0$，我们需要用可数个总体积小于 $\varepsilon$ 的长方体覆盖 $D_{m}$。

首先选取 $Q$ 的划分 $P$ 使得 $U(f,P)-L(f,P)<\varepsilon /2m$。令 $D_{m}'\subset D_{m}$ 由那些位于 $\operatorname{Bd}R$ 的点组成，其中 $R$ 是由 $P$ 确定的子长方体；$D_{m}''$ 由 $D_{m}$ 剩下的点组成。我们证明，可以用总体积小于 $\varepsilon /2$ 的长方体分别覆盖 $D_{m}'$ 和 $D_{m}''$。

对于 $D_{m}'$，证明是容易的。给定 $R$，$\operatorname{Bd}R$ 的测度为零，于是 $\bigcup_{R}\operatorname{Bd}R$ 的测度也为零。由于 $D_{m}'$ 是这个并集的子集，它可以由总体积小于 $\varepsilon /2$ 的长方体覆盖。

现在考虑 $D_{m}''$。设 $R_{1},\dots,R_{k}$ 为包含 $D_{m}''$ 中的点的子长方体。固定 $i$，设 $\mathbf{a}\in R_{i}\cap D_{m}''$。由于 $\mathbf{a}\not\in \operatorname{Bd}R_{i}$，存在 $\delta>0$ 使得 $C(\mathbf{a},\delta)\subset R_{i}$，于是

$$
\begin{gather}
\frac{1}{m}\leq \nu(f;\mathbf{a})\leq M_{\delta}(f)-m_{\delta}(f)\leq M_{R_{i}}(f)-m_{R_{i}}(f)
\end{gather}
$$

两边乘以 $v(R_{i})$ 并求和，即得

$$
\begin{gather}
\sum_{i=1}^{k} \frac{1}{m} v(R_{i})\leq U(f,P)-L(f,P)<\frac{\varepsilon}{2m}
\end{gather}
$$

于是 $\sum_{i=1}^{k}v(R_{i})<\varepsilon /2$。这就完成了证明。

### Theorem 11.4

设 $Q$ 是 $\mathbb{R}^{n}$ 中的长方体，$f\colon Q\to \mathbb{R}$ 在 $Q$ 上可积。

(a) 如果除了一个零测集外，$f=0$，那么 $\int_{Q}f=0$。
(b) 如果 $f$ 非负且 $\int_{Q}f=0$，那么除了一个零测集外，$f=0$。

#### Proof

(a) 设 $f$ 在零测集 $E$ 以外消失。设 $P$ 是 $Q$ 的划分，$R$ 是 $P$ 确定的子长方体，则 $R$ 不包含于 $E$（否则 $R$ 的测度为零）。于是 $f$ 在 $R$ 的某些点处消失，从而 $m_{R}(f)\leq 0$，而 $M_{R}(f)\geq 0$。这表明 $L(f,P)\leq 0,U(f,P)\geq 0$，于是

$$
\begin{gather}
\underline{\int_{Q}} f\leq 0, \quad \overline{\int_{Q}}f \geq 0
\end{gather}
$$

由于上下积分相等，故 $\int_{Q}f=0$。

(b) 设 $f(\mathbf{x})\geq 0$ 且 $\int_{Q}f=0$。我们证明，如果 $f$ 在 $\mathbf{a}$ 处连续，则 $f(\mathbf{a})=0$。于是 $f$ 只能在不连续点处非零，而 [[#Theorem 11.3]] 表明不连续点构成的集合具有测度零。

假设 $f$ 在 $\mathbf{a}$ 处连续且 $f(\mathbf{a})>0$。取 $\varepsilon=f(\mathbf{a})$，则存在 $\delta>0$ 使得对任意 $\mathbf{x}\in Q$ 有

$$
\begin{gather}
\lvert \mathbf{x}-\mathbf{a} \rvert <\delta \implies f(\mathbf{x})> \frac{\varepsilon}{2}
\end{gather}
$$

选择一个网格小于 $\delta$ 的划分 $P$，如果 $R_{0}$ 是一个包含 $\mathbf{a}$ 的子长方体，那么 $m_{R_{0}}(f)\geq\varepsilon /2$，而 $m_{R}(f)\geq 0$，因此

$$
\begin{gather}
\int_{Q}f\geq L(f,P)\geq \frac{\varepsilon}{2} v(R_{0})> 0
\end{gather}
$$

与条件矛盾。这就完成了证明。

# 12 Evaluation of the Integral

给定可积函数 $f\colon Q\to \mathbb{R}$，我们如何来计算它的积分？即使在一元函数 $f\colon[a,b]\to \mathbb{R}$ 的分析中，这一问题也是非平凡的。一种常用的方法是使用微积分基本定理，我们叙述如下。

### Theorem 12.1 (微积分基本定理)

(a) 如果 $f$ 在 $[a,b]$ 上连续，且
$$
\begin{gather}
F(x)=\int_{a}^{x} f \quad (x \in[a,b])
\end{gather}
$$
那么 $F'(x)=f(x)$。
(b) 如果 $f$ 在 $[a,b]$ 上可积，并且对 $x \in[a,b]$ 有 $g'(x)=f(x)$，则
$$
\begin{gather}
\int_{a}^{b} f=g(b)-g(a)
\end{gather}
$$

定理的 (b) 部分表明，如果我们可以找到可积函数 $f$ 的原函数 $g$，那么我们就能计算 $f$ 的积分。而 (a) 部分表明，如果 $f$ 是连续函数，那么在理论上总有一个 $f$ 的原函数。然而，问题在于实际中如何找到一个初等的原函数，即，能够通过常见函数的有限次运算得到的函数。

同样的困难也出现在 $n$ 维积分上。一种可行的方法是将积分约化为一系列低维积分。例如，假设我们要对连续函数 $f(x,y)$ 在 $Q=[a,b]\times[c,d]$ 上积分，我们可以应用公式

$$
\begin{gather}
\int_{Q} f=\int_{x=a}^{x=b} \int_{y=c}^{y=d} f(x,y)
\end{gather}
$$

将其约化为两个一维积分。我们将证明这些公式以及它们在 $n$ 维的推广在 $f$ 是连续函数时成立。然而，如果 $f$ 可积但不连续，那么我们可能会遇到问题：对于某个 $x$，积分

$$
\begin{gather}
\int_{y=c}^{y=d} f(x,y)
\end{gather}
$$

可能不存在。因为 $f$ 可能在某条直线上表现很差，但不影响 $f$ 在整个 $Q$ 上的积分。

由于以上的原因，下面我们给出一般的定理。

### Theorem 12.2 (Fubini)

设 $Q=A\times B$，其中 $A,B$ 分别是 $\mathbb{R}^{k},\mathbb{R}^{n}$ 中的长方体。设 $f\colon Q\to \mathbb{R}$ 有界，写成 $f(\mathbf{x},\mathbf{y})$，其中 $\mathbf{x}\in A,\mathbf{y}\in B$。对每个 $\mathbf{x}\in A$，考虑以 $\mathbf{x}$ 为自变量的函数

$$
\begin{gather}
\underline{\int_{\mathbf{y}\in B}} f(\mathbf{x},\mathbf{y}), \quad \overline{\int_{\mathbf{y}\in B}} f(\mathbf{x},\mathbf{y})
\end{gather}
$$

如果 $f$ 在 $Q$ 上可积，那么这两个函数在 $A$ 上可积，且

$$
\begin{gather}
\int_{Q} f=\int_{\mathbf{x}\in A} \underline{\int_{\mathbf{y}\in B}} f(\mathbf{x},\mathbf{y})=\int_{\mathbf{x}\in A} \overline{\int_{\mathbf{y}\in B}} f(\mathbf{x},\mathbf{y})
\end{gather}
$$

#### Proof

在本证明中，我们令

$$
\begin{gather}
\underline{I}(\mathbf{x})=\underline{\int_{\mathbf{y}\in B}} f(\mathbf{x},\mathbf{y}), \quad \overline{I}(\mathbf{x})=\overline{\int_{\mathbf{y}\in B}} f(\mathbf{x},\mathbf{y})
\end{gather}
$$

假设 $\int_{Q}f$ 存在，我们要证 $\underline{I}$ 和 $\overline{I}$ 在 $Q$ 上可积，并且积分等于 $\int_{Q}f$。

设 $P$ 是 $Q$ 的划分，则它可以写成 $P=(P_{A},P_{B})$，其中 $P_{A}$ 是 $A$ 的划分，$P_{B}$ 是 $B$ 的划分。同理，我们可以将 $P$ 确定的子长方体写成 $R_{A}\times R_{B}$。

**第一步** 我们证明

$$
\begin{gather}
L(f,P)\leq L(\underline{I},P_{A})
\end{gather}
$$

考虑由 $P$ 确定的子长方体 $R_{A}\times R_{B}$，$\mathbf{x}_{0}\in R_{A}$，则对 $\mathbf{y}\in R_{B}$ 有

$$
\begin{gather}
m_{R_{A}\times R_{B}}(f)\leq f(\mathbf{x}_{0},\mathbf{y})
\end{gather}
$$

于是

$$
\begin{gather}
m_{R_{A}\times R_{B}}(f)\leq m_{R_{B}}(f(\mathbf{x}_{0},\cdot))
\end{gather}
$$

固定 $R_{A}$ 与 $\mathbf{x}_{0}$，两边乘以 $v(R_{B})$ 并求和，得到

$$
\begin{gather}
\sum_{R_{B}} m_{R_{A}\times R_{B}}(f)v(R_{B})\leq L(f(\mathbf{x}_{0},\cdot),P_{B}) \leq \underline{\int_{\mathbf{y}\in B}} f(\mathbf{x}_{0},\mathbf{y})=\underline{I}(\mathbf{x}_{0})
\end{gather}
$$

以上不等式对 $\mathbf{x}_{0}\in R_{A}$ 成立，因此

$$
\begin{gather}
\sum_{R_{B}} m_{R_{A}\times R_{B}}(f)v(R_{B})\leq m_{R_{A}}(\underline{I})
\end{gather}
$$

两边乘以 $v(R_{A})$ 并求和，由于 $v(R_{A})v(R_{B})=v(R_{A}\times R_{B})$，故

$$
\begin{gather}
L(f,P)\leq L(\underline{I},P_{A})
\end{gather}
$$

**第二步** 与第一步同理可证

$$
\begin{gather}
U(f,P)\geq U(\overline{I},P_{A})
\end{gather}
$$

**第三步** 我们将 $f,\underline{I},\overline{I}$ 的上下和的关系总结如下：

$$
\begin{gather}
&\leq U(\underline{I},P_{A})\leq & \\
L(f,P)\leq L(\underline{I},P_{A})& & U(\overline{I},P_{A})\leq U(f,P) \\
& \leq L(\overline{I},P_{A}) \leq &
\end{gather}
$$

其中左上和右下的不等式由 [[#Lemma 10.4]] 给出，右上和左下的不等式由 $\underline{I}\leq \overline{I}$ 给出。

**第四步** 我们完成定理的证明。

如果 $f$ 可积，那么给定 $\varepsilon>0$，存在划分 $P=(P_{A},P_{B})$ 使得 $U(f,P)-L(f,P)<\varepsilon$。由于 $\underline{I}$ 与 $\overline{I}$ 的上和与下和在 $L(f,P)$ 与 $U(f,P)$ 之间，故它们的差距也小于 $\varepsilon$，从而 $\underline{I}$ 和 $\overline{I}$ 在 $Q$ 上可积。

此外，根据定义 $\int_{A}\underline{I}$ 在 $L(\underline{I},P_{A})$ 和 $U(\underline{I},P_{A})$ 之间，对 $\int_{A}\overline{I}$ 同理，因此三个数

$$
\begin{gather}
\int_{Q} f, \quad \int_{A} \underline{I}, \quad \int_{A} \overline{I}
\end{gather}
$$

均位于 $L(f,P)$ 与 $U(f,P)$ 之间。根据 $\varepsilon$ 的任意性即得

$$
\begin{gather}
\int_{Q} f=\int_{A} \underline{I}=\int_{A} \overline{I}
\end{gather}
$$

以上定理将一个多维积分写成了一个低维的累次积分。$\mathbf{x},\mathbf{y}$ 的顺序是无关紧要的：一个类似的论证表明，$\int_{Q}f$ 也等于先对 $\mathbf{x}$ 求下积分或上积分，再对 $\mathbf{y}$ 求积分的结果。

### Corollary 12.3

设 $Q=A\times B$，其中 $A,B$ 分别是 $\mathbb{R}^{k},\mathbb{R}^{n}$ 中的长方体。设 $f\colon Q\to \mathbb{R}$ 有界。如果 $f$ 在 $Q$ 上可积，且对任意 $\mathbf{x}\in A$ 有 $\int_{\mathbf{y}\in B}f(\mathbf{x},\mathbf{y})$ 存在，则

$$
\begin{gather}
\int_{Q} f= \int_{\mathbf{x}\in A} \int_{\mathbf{y}\in B} f(\mathbf{x},\mathbf{y})
\end{gather}
$$

### Corollary 12.4

设 $Q=I_{1}\times\dots \times I_{n}$，其中 $I_{j}$ 是 $\mathbb{R}$ 上的闭区间，如果 $f\colon Q\to \mathbb{R}$ 连续，那么

$$
\begin{gather}
\int_{Q} f=\int_{x_{1}\in I_{i}}\cdots \int_{x_{n}\in I_{n}} f(x_{1},\dots,x_{n})
\end{gather}
$$

# 13 The Integral over a Bounded Set

本节我们将积分域扩展为有界集合，核心思想就是将其转化为长方体上的积分。

### Definition 13.1

设 $S\subset \mathbb{R}^{n}$ 有界，$f\colon S\to \mathbb{R}$ 是有界函数，定义 $f_{S}\colon \mathbb{R}^{n}\to \mathbb{R}$ 为

$$
\begin{gather}
f_{S}(\mathbf{x})=\begin{cases}
f(\mathbf{x}), & \mathbf{x}\in S \\
0, & \mathbf{x} \in \mathbb{R}^{n} \setminus S
\end{cases}
\end{gather}
$$

选择一个包含 $S$ 的长方体 $Q$，我们定义 $f$ 在 $S$ 上的积分为

$$
\begin{gather}
\int_{S} f=\int_{Q} f_{S}
\end{gather}
$$

如果右侧的积分存在。

我们需要证明这一定义与长方体 $Q$ 的选取无关，如以下引理所示。

### Lemma 13.2

设 $Q,Q'$ 是 $\mathbb{R}^{n}$ 中的长方体，如果 $f\colon \mathbb{R}^{n}\to \mathbb{R}$ 有界且在 $Q\cap Q'$ 以外消失，则

$$
\begin{gather}
\int_{Q} f=\int_{Q'} f
\end{gather}
$$

其中一个积分存在当且仅当另一个积分存在。

#### Proof

我们首先考虑 $Q\subset Q'$ 的情况。设 $E$ 由 $f$ 在 $\operatorname{Int}Q$ 中的不连续点构成，则函数 $f\colon Q\to \mathbb{R}$ 和 $f\colon Q'\to \mathbb{R}$ 在除了 $E$ 和 $\operatorname{Bd}Q$ 的某些点外均连续。由于 $\operatorname{Bd}Q$ 的测度为零，故两个积分同时存在当且仅当 $E$ 的测度为零。

现在假设两个积分存在。设 $P$ 是 $Q'$ 的划分，将 $Q$ 的分量区间加入到 $P$ 中得到 $P$ 的细化 $P''$，则 $Q$ 等于一系列由 $P''$ 确定的子长方体的并集。

![](3-4.png)

如果 $R$ 是一个子长方体，其不包含于 $Q$，那么 $f$ 在 $R$ 的内部消失，从而 $m_{R}(f)\leq 0$。于是

$$
\begin{gather}
L(f,P)\leq L(f,P'')\leq \sum_{R\subset Q} m_{R}(f)v(R)\leq \int_{Q} f
\end{gather}
$$

同理我们可得 $U(f,P)\geq \int_{Q}f$。由于 $P$ 是任意划分，故

$$
\begin{gather}
\int_{Q}f=\int_{Q'} f
\end{gather}
$$

最后，设 $Q,Q'$ 是一般的长方体，取长方体 $Q''$ 使得 $Q\subset Q''$ 且 $Q'\subset Q''$，则根据上面的论证可知

$$
\begin{gather}
\int_{Q} f =\int_{Q''} f=\int_{Q'} f
\end{gather}
$$

本节的剩余部分，我们来研究有界集上积分的基本性质，并给出一个积分存在的充分条件。

### Lemma 13.3

设 $S\subset \mathbb{R}^{n}$，$f,g\colon S\to \mathbb{R}^{n}$，定义 $F,G\colon S\to \mathbb{R}^{n}$ 为

$$
\begin{gather}
F(\mathbf{x})=\max(f(\mathbf{x}),g(\mathbf{x})), \quad G(\mathbf{x})=\min(f(\mathbf{x}),g(\mathbf{x}))
\end{gather}
$$

(a) 如果 $f,g$ 在 $\mathbf{x}_{0}$ 处连续，那么 $F,G$ 也在 $\mathbf{x}_{0}$ 处连续。
(b) 如果 $f,g$ 在 $S$ 上可积，那么 $F,G$ 也在 $S$ 上可积。

#### Proof

(a) 首先考虑 $f(\mathbf{x}_{0})=g(\mathbf{x}_{0})=r$ 的情况，此时 $F(\mathbf{x}_{0})=G(\mathbf{x}_{0})=r$。根据连续性，对任意 $\varepsilon>0$，存在 $\delta>0$ 使得对 $\mathbf{x}\in S$ 有

$$
\begin{gather}
\lvert \mathbf{x}-\mathbf{x}_{0} \rvert <\delta \implies \lvert f(\mathbf{x})-r \rvert <\varepsilon, \lvert g(\mathbf{x})-r \rvert <\varepsilon
\end{gather}
$$

于是

$$
\begin{gather}
\lvert F(\mathbf{x})-r \rvert <\varepsilon, \quad \lvert G(\mathbf{x})-r \rvert <\varepsilon
\end{gather}
$$

下面我们考虑 $f(\mathbf{x}_{0})>g(\mathbf{x}_{0})$ 的情况，由于 $f-g$ 在 $\mathbf{x}_{0}$ 处连续，故存在 $\mathbf{x}_{0}$ 的邻域 $U$ 使得在 $U\cap S$ 中有 $f(\mathbf{x})-g(\mathbf{x})>0$，于是在 $U\cap S$ 中有 $F(\mathbf{x})=f(\mathbf{x}),G(\mathbf{x})=g(\mathbf{x})$，于是 $F,G$ 在 $\mathbf{x}_{0}$ 处连续。$f(\mathbf{x}_{0})<g(\mathbf{x}_{0})$ 的情况是类似的。

(b) 设 $f,g$ 在 $S$ 上可积，令 $Q$ 是一个包含 $S$ 的长方体，且 $f_{S},g_{S}$ 在除了零测集 $D,E$ 以外的点上连续。我们有

$$
\begin{gather}
F_{S}=\max(f_{S},g_{S}), \quad G_{S}=\min(f_{S},g_{S})
\end{gather}
$$

于是根据 (a)，$F_{S}$ 和 $G_{S}$ 在除了 $D\cup E$ 以外的点上连续。此外，$f_{S},g_{S}$ 有界，故 $F_{S},G_{S}$ 也有界。即证 $F_{S},G_{S}$ 可积。

### Theorem 13.4

设 $S\subset \mathbb{R}^{n}$ 是有界集，$f,g\colon S\to \mathbb{R}^{n}$ 有界。

(a) 线性性：如果 $f,g$ 在 $S$ 上可积，那么 $af+bg$ 也在 $S$ 上可积，且
$$
\begin{gather}
\int_{S}(af+bg)=a\int_{S} f+b \int_{S}g
\end{gather}
$$
(b) 保序性：设 $f,g$ 在 $S$ 上可积，如果对 $\mathbf{x}\in S$ 有 $f(\mathbf{x})\leq g(\mathbf{x})$，那么
$$
\begin{gather}
\int_{S} f\leq \int_{S} g
\end{gather}
$$
此外，$\lvert f \rvert$ 在 $S$ 上可积，且
$$
\begin{gather}
\left\lvert  \int_{S} f  \right\rvert \leq \int_{S} \lvert f \rvert 
\end{gather}
$$
(c) 单调性：设 $T\subset S$，如果 $f$ 非负且在 $T$ 和 $S$ 上可积，那么
$$
\begin{gather}
\int_{T}f\leq \int_{S} f
\end{gather}
$$
(d) 可加性：设 $S=S_{1}\cup S_{2}$，如果 $f$ 在 $S_{1},S_{2}$ 上可积，那么 $f$ 在 $S$ 和 $S_{1}\cap S_{2}$ 上可积，并且
$$
\begin{gather}
\int_{S} f=\int_{S_{1}}f+\int_{S_{2}} f-\int_{S_{1}\cap S_{2}} f
\end{gather}
$$

#### Proof

(a) 我们只需证明积分区域是一个长方体时的情况，因为

$$
\begin{gather}
(af+bg)_{S}=af_{S}+bg_{S}
\end{gather}
$$

因此假设 $f,g$ 在 $Q$ 上可积。则 $f,g$ 在除了零测集 $D,E$ 外的点上连续，从而 $af+bg$ 在除了 $D\cup E$ 外的点上连续，因而可积。

下面我们首先考虑 $a,b\geq 0$ 的情况。设 $P''$ 是 $Q$ 的划分，如果 $R$ 是由 $P''$ 确定，则对 $\mathbf{x}\in R$ 有

$$
\begin{gather}
am_{R}(f)+bm_{R}(g)\leq af(\mathbf{x})+bg(\mathbf{x})
\end{gather}
$$

于是

$$
\begin{gather}
am_{R}(f)+bm_{R}(g)\leq m_{R}(af+bg)
\end{gather}
$$

因此

$$
\begin{gather}
aL(f,P'')+bL(f,P'')\leq L(af+bg,P'')\leq \int_{Q} (af+bg)
\end{gather}
$$

同理可证

$$
\begin{gather}
aU(f,P'')+bU(f,P'')\geq \int_{Q} (af+bg)
\end{gather}
$$

现在令 $P,P'$ 为 $Q$ 的任意划分，$P''$ 为其公共细化，则由上面的论证得

$$
\begin{gather}
aL(f,P)+bL(f,P')\leq \int_{Q} (af+bg)\leq aU(f,P)+bU(f,P')
\end{gather}
$$

而根据定义，$a\int_{Q}f+b\int_{Q}g$ 同样位于以上区间中。由于 $P,P'$ 是任意的，我们可得

$$
\begin{gather}
\int_{Q}(af+bg)=a\int_{Q} f+b\int_{Q} g
\end{gather}
$$

剩下的情况都可以由 $a,b\geq 0$ 的情况与

$$
\begin{gather}
\int_{Q}(-f)=-\int_{Q} f
\end{gather}
$$

给出。令 $P$ 是 $Q$ 的划分，$R$ 是一个子长方体，对 $\mathbf{x}\in R$，我们有

$$
\begin{gather}
-M_{R}(f)\leq-f(\mathbf{x})\leq-m_{R}(f)
\end{gather}
$$

于是

$$
\begin{gather}
-M_{R}(f)\leq m_{R}(-f)\leq M_{R}(-f)\leq-m_{R}(f)
\end{gather}
$$

两边乘以 $v(R)$ 并求和，我们有

$$
\begin{gather}
-U(f,P)\leq L(-f,P)\leq \int_{Q}(-f) \leq U(-f,P)\leq -L(f,P)
\end{gather}
$$

而 $-\int_{Q}f$ 同样位于区间 $[-U(f,P),-L(f,P)]$ 中，即证。

(b) 只需证明积分区域是长方体的情况。假设对 $\mathbf{x}\in Q$ 有 $f(\mathbf{x})\leq g(\mathbf{x})$，则对子长方体 $R$ 有

$$
\begin{gather}
m_{R}(f)\leq m_{R}(g)
\end{gather}
$$

于是对任意划分 $P$，

$$
\begin{gather}
L(f,P)\leq L(g,P)\leq \int_{Q} g
\end{gather}
$$

从而

$$
\begin{gather}
\int_{Q}f\leq \int_{Q} g
\end{gather}
$$

$\lvert f \rvert$ 在 $S$ 上可积的结论来源于

$$
\begin{gather}
\lvert f(\mathbf{x}) \rvert =\max(f(\mathbf{x}),-f(\mathbf{x}))
\end{gather}
$$

剩下的不等式来源于

$$
\begin{gather}
-\lvert f(\mathbf{x}) \rvert \leq f(\mathbf{x})\leq\lvert f(\mathbf{x}) \rvert 
\end{gather}
$$

(c) 如果 $f$ 非负且 $T\subset S$，那么 $f_{T}(\mathbf{x})\leq f_{S}(\mathbf{x})$，应用 (b) 的结论即证。

(d) 令 $T=S_{1}\cap S_{2}$，我们证明 $f$ 在 $S,T$ 上可积。首先设 $f$ 在 $S$ 上非负，$Q$ 为包含 $S$ 的长方体。根据假设，$f_{S_{1}},f_{S_{2}}$ 在 $Q$ 上可积，从而由

$$
\begin{gather}
f_{S}(\mathbf{x})=\max(f_{S_{1}}(\mathbf{x}),f_{S_{2}}(\mathbf{x})), \quad f_{T}(\mathbf{x})=\min(f_{S_{1}}(\mathbf{x}),f_{S_{2}}(\mathbf{x}))
\end{gather}
$$

知 $f_{S},f_{T}$ 在 $Q$ 上可积。

在一般情况下，令

$$
\begin{gather}
f_{+}(\mathbf{x})=\max(f(\mathbf{x}),0), \quad f_{-}(\mathbf{x})=-\min(f(\mathbf{x}),0)
\end{gather}
$$

由于 $f$ 在 $S_{1},S_{2}$ 上可积，故 $f_{+},f_{-}$ 在 $S_{1},S_{2}$ 上可积。根据上面的论证，$f_{+},f_{-}$ 在 $S,T$ 上可积。由于

$$
\begin{gather}
f(\mathbf{x})=f_{+}(\mathbf{x})-f_{-}(\mathbf{x})
\end{gather}
$$

故 $f$ 在 $S,T$ 上可积。

最后，可加性的公式由积分的线性性与以下等式给出：

$$
\begin{gather}
f_{S}(\mathbf{x})=f_{S_{1}}(\mathbf{x})+f_{S_{2}}(\mathbf{x})-f_{T}(\mathbf{x})
\end{gather}
$$

### Corollary 13.5

设 $S_{1},\dots,S_{k}$ 是 $\mathbb{R}^{n}$ 中的有界集，对 $i\neq j$ 有 $S_{i}\cap S_{j}$ 的测度为零。令 $S=S_{1}\cup\dots \cup S_{k}$，如果 $f\colon S\to \mathbb{R}$ 在每个 $S_{i}$ 上可积，那么 $f$ 在 $S$ 上可积，且

$$
\begin{gather}
\int_{S}f=\int_{S_{1}} f+\dots+\int_{S_{k}} f
\end{gather}
$$

#### Proof

$k=2$ 的情况由积分的可加性以及 [[#Theorem 11.4]] 给出，其中 $\int_{S_{1}\cap S_{2}}f=0$。$k>2$ 的情况由归纳法给出。

目前为止，除了有界性外，我们还未对积分理论中的函数 $f$ 做什么先验的假设。不过，在本书中我们主要考虑的函数都至少是连续的，因此我们做出如下约定：

### Convention

从此以后，我们对积分理论的研究将只限制在连续函数 $f\colon S\to \mathbb{R}$ 上。

### Theorem 13.6

设 $S\subset \mathbb{R}^{n}$ 有界，$f\colon S\to \mathbb{R}$ 是有界连续函数，令

$$
\begin{gather}
E=\{ \mathbf{x}_{0}\in \operatorname{Bd}S : \lim_{ \mathbf{x} \to \mathbf{x}_{0} } f(\mathbf{x}) \neq 0 \}
\end{gather}
$$

如果 $E$ 的测度为零，那么 $f$ 在 $S$ 上可积。

#### Proof

设 $\mathbf{x}_{0}\not\in E$，我们证明 $f_{S}$ 在 $\mathbf{x}_{0}$ 处连续，从而 $f_{S}$ 几乎处处连续，于是可积。

如果 $\mathbf{x}_{0}\in \operatorname{Int}S$，那么 $f$ 和 $f_{S}$ 在 $\mathbf{x}_{0}$ 的一个邻域中相等，于是 $f_{S}$ 在 $\mathbf{x}_{0}$ 处连续。如果 $\mathbf{x}_{0}\in \operatorname{Ext}S$，则 $f_{S}$ 在 $\mathbf{x}_{0}$ 的一个邻域中消失，从而连续。

现在设 $\mathbf{x}_{0}\in \operatorname{Bd}S$。由于 $\mathbf{x}_{0}\not\in E$，故对于 $\mathbf{x}\in S$ 有

$$
\begin{gather}
f(\mathbf{x})\to 0 \quad (\mathbf{x}\to \mathbf{x}_{0})
\end{gather}
$$

由于 $f$ 连续，因此如果 $\mathbf{x}_{0}\in S$，那么 $f(\mathbf{x}_{0})=0$。此外，由于 $f_{S}(\mathbf{x})$ 等于 $f(\mathbf{x})$ 或者 $0$，故

$$
\begin{gather}
f_{S}(\mathbf{x})\to 0 \quad (\mathbf{x}\to \mathbf{x}_{0})
\end{gather}
$$

要证 $f_{S}$ 在 $\mathbf{x}_{0}$ 处连续，我们只需证明 $f_{S}(\mathbf{x}_{0})=0$。如果 $\mathbf{x}_{0}\in S$，前面我们已经证明 $f_{S}(\mathbf{x}_{0})=f(\mathbf{x}_{0})=0$。如果 $\mathbf{x}_{0}\not\in S$，那么根据定义就有 $f_{S}(\mathbf{x}_{0})=0$。这就完成了证明。

同样的方法可以用于证明如下定理。

### Theorem 13.7

设 $S\subset \mathbb{R}^{n}$ 有界，$f\colon S\to \mathbb{R}$ 是有界连续函数，令 $A=\operatorname{Int}S$。如果 $f$ 在 $S$ 上可积，则 $f$ 在 $A$ 上可积，且 $\int_{S}f=\int_{A}f$。

#### Proof

**第一步** 我们证明如果 $f_{S}$ 在 $\mathbf{x}_{0}$ 处连续，那么 $f_{A}$ 在 $\mathbf{x}_{0}$ 连续且等于 $f_{S}$。

如果 $\mathbf{x}_{0}\in \operatorname{Int}S$ 或 $\mathbf{x}_{0}\in \operatorname{Ext}S$，那么 $f_{S}$ 与 $f_{A}$ 在 $\mathbf{x}_{0}$ 的一个邻域中相等，从而结论是平凡的。

如果 $\mathbf{x}_{0}\in \operatorname{Bd}S$，连续性表明 $f_{S}(\mathbf{x})\to f_{S}(\mathbf{x}_{0})$，由于 $\mathbf{x}_{0}$ 的任意邻域中都包含 $\operatorname{Ext}S$ 中的点，取一列 $\operatorname{Ext}S$ 中趋于 $\mathbf{x}_{0}$ 的点 $\mathbf{x}_{n}$，则 $f_{S}(\mathbf{x}_{n})=0$，从而 $f_{S}(\mathbf{x}_{0})=0$。

由于 $f_{A}$ 等于 $f_{S}$ 或者 $0$，故 $\mathbf{x}\to \mathbf{x}_{0}$ 时 $f_{A}(\mathbf{x})\to 0$。又由于 $\mathbf{x}_{0}\not\in A$，故 $f_{A}(\mathbf{x}_{0})=0$，即证 $f_{A}$ 在 $\mathbf{x}_{0}$ 处连续，并且与 $f_{S}$ 相等。

**第二步** 我们证明本定理。

如果 $f$ 在 $S$ 上可积，则 $f_{S}$ 在除了零测集 $D$ 外的点上连续。则根据第一步的结论，$f_{A}$ 在 $D$ 以外的点上连续，故可积。由于 $f_{S}-f_{A}$ 在 $D$ 以外的点上消失，我们有

$$
\begin{gather}
\int_{Q} (f_{S}-f_{A})=0
\end{gather}
$$

其中 $Q$ 是包含 $S$ 的长方体。这就完成了证明。

# 14 Rectifiable Sets

我们现在将体积函数 $v$ 的定义域从长方体扩展至部分有界集。

### Definition 14.1 rectifiable 可求体积的

设 $S\subset \mathbb{R}^{n}$ 有界，如果常值函数 $1$ 在 $S$ 上可积，我们就称 $S$ 是可求体积的，并定义 $S$ 的体积为

$$
\begin{gather}
v(S)=\int_{S} 1
\end{gather}
$$

### Theorem 14.2

设 $S\subset \mathbb{R}^{n}$ 有界，则 $S$ 可求体积当且仅当 $\operatorname{Bd}S$ 的测度为零。

#### Proof

函数 $1_{S}$ 在 $\operatorname{Int}S$ 和 $\operatorname{Ext}S$ 上连续，而在 $\operatorname{Bd}S$ 上不连续。于是，$1_{S}$ 在包含 $S$ 的长方体 $Q$ 上可积当且仅当 $\operatorname{Bd}S$ 的测度为零。

我们列出可求体积集的一些性质。

### Theorem 14.3

(a) 正性：如果 $S$ 可求体积，则 $v(S)\geq 0$。
(b) 单调性：如果 $S_{1},S_{2}$ 可求体积且 $S_{1}\subset S_{2}$，则 $v(S_{1})\leq v(S_{2})$。
(c) 可加性：如果 $S_{1},S_{2}$ 可求体积，那么 $S_{1}\cup S_{2},S_{1}\cap S_{2}$ 也可求体积，且
$$
\begin{gather}
v(S_{1}\cup S_{2})=v(S_{1})+v(S_{2})-v(S_{1}\cap S_{2})
\end{gather}
$$
(d) 设 $S$ 可求体积，则 $v(S)=0$ 当且仅当 $S$ 的测度为零。
(e) 如果 $S$ 可求体积，那么 $A=\operatorname{Int}S$ 也可求体积，且 $v(A)=v(S)$。
(f) 如果 $S$ 可求体积，$f\colon S\to \mathbb{R}$ 是有界连续函数，则 $f$ 在 $S$ 上可积。

#### Proof

(a)(b)(c) 由 [[#Theorem 13.4]] 给出。对函数 $1_{S}$ 应用 [[#Theorem 11.4]] 可得 (d)。(e) 是 [[#Theorem 13.7]] 的推论，(f) 是 [[#Theorem 13.6]] 的推论。

### Remark 14.4

本节中我们定义的体积通常被称为 Jordan 容度，其与一个更为广泛的概念，即测度相对。测度是 Lebesgue 积分的基础，后者是 Riemann 积分的推广。

$\mathbb{R}^{n}$ 上可以定义测度的集合比可定义容度的集合更多，但如果两者都存在，那么测度和容度相等。我们定义的“零测集”实际上就是一个 Lebesgue 测度存在且为零。这样的集合当然不一定是可求体积的。

一个可以定义测度的集合称为是可测集。然而，没有一个广泛接受的术语来描述可以定义容度的集合。本书中我们使用了 rectifiable 来描述这样的集合，它的本义是用来描述可以定义长度概念的曲线，我们将它的内涵进行扩展，以使它能够描述可以定义体积概念的集合。

本节的最后我们来讨论一类常见的可求体积集合，称为简单区域。对于这些集合，我们可以在其上应用 Fubini 定理的一个变体，从而给出了积分 $\int_{S}f$ 的一种计算方法。

### Definition 14.5 simple region 简单区域

设 $C$ 是 $\mathbb{R}^{n-1}$ 中的紧致可求体积集，$\phi,\psi\colon C\to \mathbb{R}$ 是连续函数，满足对任意 $\mathbf{x}\in C$ 有 $\phi(\mathbf{x})\leq \psi(\mathbf{x})$。我们定义 $\mathbb{R}^{n}$ 的子集

$$
\begin{gather}
S=\{ (\mathbf{x},t): \mathbf{x} \in C, \phi(\mathbf{x})\leq t\leq \psi(\mathbf{x}) \}
\end{gather}
$$

是 $\mathbb{R}^{n}$ 中的一个简单区域。

简单区域并不仅限于最后一个坐标。如果 $k+\ell=n-1$，设 $\mathbf{y}\in \mathbb{R}^{k}$ 且 $\mathbf{z}\in \mathbb{R}^{\ell}$，则集合

$$
\begin{gather}
S=\{ (\mathbf{y},t,\mathbf{z}):(\mathbf{y},\mathbf{z}) \in C, \phi(\mathbf{y},\mathbf{z})\leq t\leq \psi(\mathbf{y},\mathbf{z}) \}
\end{gather}
$$

同样也称为一个简单区域。

### Lemma 14.6

如果 $S\subset \mathbb{R}^{n}$ 是简单区域，则 $S$ 紧致且可求体积。

#### Proof

设 $S$ 是简单区域，我们来证明 $S$ 紧致，且 $\operatorname{Bd}S$ 的测度为零。

**第一步** 函数 $\phi$ 的图像定义为

$$
\begin{gather}
G_{\phi}=\{ (\mathbf{x},t): \mathbf{x}\in C, t=\phi(\mathbf{x}) \}
\end{gather}
$$

我们证明 $\operatorname{Bd}S$ 等于集合 $G_{\phi},G_{\psi}$，以及

$$
\begin{gather}
D=\{ (\mathbf{x},t): \mathbf{x}\in \operatorname{Bd}C,\phi(\mathbf{x})\leq t\leq \psi(\mathbf{x}) \}
\end{gather}
$$

的并集。由于这些集合都包含于 $S$，故 $\operatorname{Bd}S\subset S$，因此 $S$ 是有界且闭的，从而紧致。

![](3-5.png)

假设 $(\mathbf{x}_{0},t_{0})$ 不在 $G_{\phi},G_{\psi},D$ 中，我们要证它位于 $\operatorname{Int}S$ 或 $\operatorname{Ext}S$。我们对 $\mathbf{x}_{0}$ 的位置做如下讨论：

1. $\mathbf{x}_{0}\not\in C$，
2. $\mathbf{x}_{0}\in C$ 且 $t_{0}<\phi(\mathbf{x}_{0})$ 或 $t_{0}>\psi(\mathbf{x}_{0})$，
3. $\mathbf{x}_{0}\in \operatorname{Int}C$ 且 $\phi(\mathbf{x}_{0})<t_{0}<\psi(\mathbf{x}_{0})$。

在情形 (1) 中，存在 $\mathbf{x}_{0}$ 的邻域 $U$ 与 $C$ 不相交，于是 $U\times \mathbb{R}$ 与 $S$ 不相交，故 $(\mathbf{x}_{0},t_{0})\in \operatorname{Ext}S$。

在情形 (2) 中，假设 $t_{0}<\phi(\mathbf{x}_{0})$。根据 $\phi$ 的连续性，存在 $(\mathbf{x}_{0},t_{0})$ 的邻域 $W$ 使得当 $\mathbf{x}\in C$ 且 $(\mathbf{x},t)\in W$ 时 $\phi(\mathbf{x})-t>0$，则 $W$ 与 $S$ 不相交，$(\mathbf{x}_{0},t_{0})\in \operatorname{Ext}S$。$t_{0}>\psi(\mathbf{x}_{0})$ 的情形是类似的。

在情形 (3) 中，根据连续性，存在 $(\mathbf{x}_{0},t_{0})$ 的邻域 $U\times V$ 使得 $U\subset C$ 且在 $U\times V$ 上 $t-\phi(\mathbf{x})$ 和 $\psi(\mathbf{x})-t$ 都是正的。于是 $U\times V\subset S$，$(\mathbf{x}_{0},t_{0})\in \operatorname{Int}S$。

**第二步** 我们证明 $G_{\phi},G_{\psi}$ 的测度为零。

我们只需考虑 $G_{\phi}$。选择 $\mathbb{R}^{n-1}$ 中的一个包含 $C$ 的长方体 $Q$。给定 $\varepsilon>0$，令 $\varepsilon'=\varepsilon /2v(Q)$，由于 $\phi$ 连续且 $C$ 紧致，故 $\phi$ 在 $C$ 上一致连续。于是存在 $\delta>0$ 使得对 $\mathbf{x},\mathbf{y}\in C$ 有

$$
\begin{gather}
\lvert \mathbf{x}-\mathbf{y} \rvert <\delta \implies \lvert \phi(\mathbf{x})-\phi(\mathbf{y}) \rvert <\varepsilon'
\end{gather}
$$

选择 $Q$ 的一个网格小于 $\delta$ 的划分 $P$，设 $R$ 是一个子长方体。如果 $R$ 与 $C$ 相交，那么在 $R\cap C$ 上就有 $\lvert \phi(\mathbf{x})-\phi(\mathbf{y}) \rvert<\varepsilon'$。对每个这样的 $R$，取 $\mathbf{x}_{R}\in R\cap C$ 并定义

$$
\begin{gather}
I_{R}=[\phi(\mathbf{x}_{R})-\varepsilon',\phi(\mathbf{x}_{R})+\varepsilon']
\end{gather}
$$

则 $R\times I_{R}$ 包含了所有点 $(\mathbf{x},\phi(\mathbf{x}))$，其中 $\mathbf{x}\in R\cap C$。

这些集合 $R\times I_{R}$ 覆盖了 $G_{\phi}$，其总体积为

$$
\begin{gather}
\sum_{R} v(R\times I_{R})=\sum_{R} v(R)(2\varepsilon')\leq 2\varepsilon' v(Q)=\varepsilon
\end{gather}
$$

![](3-6.png)

**第三步** 我们证明 $D$ 的测度为零。

由于 $\phi,\psi$ 连续且 $C$ 紧致，故存在 $M$ 使得

$$
\begin{gather}
-M\leq \phi(\mathbf{x})\leq \psi(\mathbf{x})\leq M
\end{gather}
$$

由于 $C$ 可求体积，故 $\operatorname{Bd}C$ 的测度为零。给定 $\varepsilon>0$，用总体积小于 $\varepsilon /2M$ 的长方体 $Q_{1},Q_{2},\dots \subset \mathbb{R}^{n-1}$ 覆盖 $\operatorname{Bd}C$，则长方体 $Q_{i}\times[-M,M]$ 覆盖了 $D$，其总体积小于 $\varepsilon$。

### Theorem 14.7 (Fubini)

设

$$
\begin{gather}
S=\{ (\mathbf{x},t): \mathbf{x}\in C, \phi(\mathbf{x})\leq t\leq \psi(\mathbf{x}) \}
\end{gather}
$$

是 $\mathbb{R}^{n}$ 中的简单区域，$f\colon S\to \mathbb{R}$ 是连续函数，则 $f$ 在 $S$ 上可积，且

$$
\begin{gather}
\int_{S} f=\int_{\mathbf{x}\in C} \int_{t=\phi(\mathbf{x})}^{t=\psi(\mathbf{x})} f(\mathbf{x},t)
\end{gather}
$$

#### Proof

设 $Q\times[-M,M]$ 是 $\mathbb{R}^{n}$ 中包含 $S$ 的长方体。由于 $f$ 在 $S$ 上有界连续，$S$ 可求体积，故 $f$ 在 $S$ 上可积。

固定 $\mathbf{x}_{0}\in Q$，函数 $f_{S}(\mathbf{x}_{0},t)$ 或者恒为零，或者除了两个点外在 $\mathbb{R}$ 上连续。根据 Fubini 定理就有

$$
\begin{gather}
\int_{S} f=\int_{\mathbf{x}\in Q} \int_{t=-M}^{t=M} f_{S}(\mathbf{x},t)
\end{gather}
$$

内层的积分在 $\mathbf{x}\not\in C$ 时消失，因此

$$
\begin{gather}
\int_{S} f=\int_{\mathbf{x}\in C} \int_{t=-M}^{t=M} f_{S}(\mathbf{x},t)
\end{gather}
$$

此外，$f_{S}(\mathbf{x},t)$ 在 $\phi(\mathbf{x})\leq t\leq \psi(\mathbf{x})$ 以外消失，因此我们有

$$
\begin{gather}
\int_{S}f=\int_{\mathbf{x}\in C} \int_{t=\phi(\mathbf{x})}^{t=\psi(\mathbf{x})}
\end{gather}
$$

以上定理给出了一种计算 $\int_{S}f$ 的直接方法。在实际应用中，集合 $S$ 可能不是简单的，但大多数情况下我们可以将其分解为有限个简单区域的并集，其中两两交集的测度为零。此时我们就可以利用积分的区域可加性完成计算。

当然，也存在一些无法分解为有限个简单区域并集的可求体积集。在这种情况下我们就需要用简单区域的并集来近似 $S$，然后应用一种极限过程。

# 15 Improper Integrals

本节我们将积分 $\int_{S}f$ 推广到 $S$ 无界或者 $f$ 无界的情况。这样的积分称为反常积分或者广义积分。

### Definition 15.1 extended integral 广义积分

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 连续。如果 $f$ 在 $A$ 上非负，我们定义 $f$ 在 $A$ 上的广义积分为

$$
\begin{gather}
\int_{A} f= \sup \left\{  \int_{D} f : D\subset A \  \text{紧致且可求体积}  \right\}
\end{gather}
$$

如果 $\int_{A}f<\infty$，我们就称 $f$ 在 $A$ 上广义可积。对于一般的连续函数 $f$，令

$$
\begin{gather}
f_{+}(\mathbf{x})=\max(f(\mathbf{x}),0), \quad f_{-}(\mathbf{x})=-\min(f(\mathbf{x}),0)
\end{gather}
$$

我们称 $f$ 在 $A$ 上广义可积如果 $f_{+}$ 和 $f_{-}$ 在 $A$ 上广义可积，此时我们定义

$$
\begin{gather}
\int_{A} f=\int_{A} f_{+}-\int_{A} f_{-}
\end{gather}
$$

如果 $A$ 是 $\mathbb{R}^{n}$ 中的开集且 $f$ 和 $A$ 都有界，此时符号 $\int_{A}f$ 有两种不同的解释：它可以表示 $f$ 在 $A$ 上的普通积分，或者广义积分。之后我们将证明，如果普通积分存在，那么广义积分也存在并且与普通积分相等。然而，这一符号仍然存在歧义，因为当普通积分不存在时广义积分仍然可以存在。为了避免歧义，我们做出如下约定：

### Convention

如果 $A\subset \mathbb{R}^{n}$ 是开集，那么除非特别指定，否则我们将用 $\int_{A}f$ 表示 $f$ 在 $A$ 上的广义积分。

当然，如果 $A$ 不是开集，那么此时就没有歧义：$\int_{A}f$ 只能表示 $f$ 的普通积分。

### Lemma 15.2

设开集 $A\subset \mathbb{R}^{n}$，则存在一列紧致可求体积集 $C_{1},C_{2},\dots \subset A$ 使得 $\bigcup_{N=1}^{\infty}C_{N}=A$ 且对任意 $N$ 有 $C_{N}\subset \operatorname{Int}C_{N+1}$。

#### Proof

我们用 $d$ 来表示 $\mathbb{R}^{n}$ 上的上确界度量 $d(\mathbf{x},\mathbf{y})=\lvert \mathbf{x}-\mathbf{y} \rvert$。如果 $B\subset \mathbb{R}^{n}$，令 $d(\mathbf{x},B)$ 表示 $\mathbf{x}$ 到 $B$ 的距离。

令 $B=\mathbb{R}^{n}\setminus A$，给定 $N$，定义

$$
\begin{gather}
D_{N}=\left\{  \mathbf{x} : d(\mathbf{x},B)\geq \frac{1}{N}, d(\mathbf{x},\mathbf{0})\leq N  \right\}
\end{gather}
$$

![](3-7.png)

由于 $d(\mathbf{x},B)$ 和 $d(\mathbf{x},\mathbf{0})$ 作为 $\mathbf{x}$ 的函数是连续的，故 $D_{N}$ 是闭集。又由于 $D_{N}$ 有界，故 $D_{N}$ 紧致。此外，$D_{N}\subset A$，因为 $d(\mathbf{x},B)\geq 1 /N$ 表明 $\mathbf{x}$ 不可能在 $B$ 中。

下面证明 $D_{N}$ 的并集是 $A$。设 $\mathbf{x}\in A$，由于 $A$ 是开集，故 $d(\mathbf{x},B)>0$，因此存在 $N$ 使得 $d(\mathbf{x},B)\geq 1 /N$ 且 $d(\mathbf{x},\mathbf{0})\leq N$。即证 $\mathbf{x}\in D_{N}$。最后，我们注意到集合

$$
\begin{gather}
A_{N+1}=\left\{  \mathbf{x} : d(\mathbf{x},B)> \frac{1}{N+1},d(\mathbf{x},\mathbf{0})< N+1  \right\}
\end{gather}
$$

是开集，并且 $D_{N}\subset A_{N+1}\subset D_{N+1}$，这就表明 $D_{N}\subset \operatorname{Int}D_{N+1}$。

接下来我们通过 $D_{N}$ 来构造 $C_{N}$，使得后者是可求体积的。对 $\mathbf{x}\in D_{N}$，选择一个以 $\mathbf{x}$ 为中心且包含于 $\operatorname{Int}D_{N+1}$ 的闭立方体，这些立方体的内部覆盖了 $D_{N}$，从而由紧致性，我们可以选取有限个立方体使得它们的内部覆盖 $D_{N}$。设这些立方体的并集为 $C_{N}$。

由于 $C_{N}$ 是有限个闭立方体的并集，故它是紧致的且可求体积。并且

$$
\begin{gather}
D_{N}\subset C_{N}\subset \operatorname{Int}D_{N+1}\subset \operatorname{Int}C_{N+1}
\end{gather}
$$

于是就有 $\bigcup_{N=1}^{\infty}C_{N}=A$ 且 $C_{N}\subset \operatorname{Int}C_{N+1}$。

### Theorem 15.3

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 连续。选择一列紧致可求体积集 $C_{N}\subset A$ 使得 $\bigcup_{N=1}^{\infty}C_{N}=A$ 且 $C_{N}\subset \operatorname{Int}C_{N+1}$。则 $f$ 在 $A$ 上广义可积当且仅当序列 $\int_{C_{N}}\lvert f \rvert$ 有界，此时

$$
\begin{gather}
\int_{A} f=\lim_{ N \to \infty } \int_{C_{N}} f
\end{gather}
$$

以上定理表明 $f$ 在 $A$ 上广义可积当且仅当 $\lvert f \rvert$ 在 $A$ 上广义可积。

#### Proof

**第一步** 我们证明 $f$ 非负时的情况。此时 $f=\lvert f \rvert$。序列 $\int_{C_{N}}f$ 单调递增，因此它收敛当且仅当它有界。

我们首先设 $f$ 在 $A$ 上广义可积，则令 $D$ 遍历 $A$ 的紧致可求体积子集，有

$$
\begin{gather}
\int_{C_{N}} f\leq \sup \int_{D}f=\int_{A} f
\end{gather}
$$

因为 $C_{N}$ 自身是紧致且可求体积的。于是 $\int_{C_{N}}f$ 有界，且

$$
\begin{gather}
\lim_{ N \to \infty } \int_{C_{N}} f\leq \int_{A} f \tag{1}
\end{gather}
$$

反之，设 $\int_{C_{N}} f$ 有界。令 $D$ 为 $A$ 的任意紧致可求体积子集，则 $D$ 可由开集

$$
\begin{gather}
\operatorname{Int}C_{1}\subset \operatorname{Int}C_{2}\subset\cdots
\end{gather}
$$

覆盖，于是它可由其中有限个集合覆盖。根据这些集合的嵌套特性，它可由其中一个集合覆盖，设为 $\operatorname{Int}C_{M}$。则

$$
\begin{gather}
\int_{D} f\leq \int_{C_{M}} f\leq \lim_{ N \to \infty } \int_{C_{N}} f
\end{gather}
$$

由于 $D$ 是任意的，故 $\sup \int_{D}f$ 有限，从而 $f$ 在 $A$ 上广义可积，且

$$
\begin{gather}
\int_{A} f \leq \lim_{ N \to \infty } \int_{C_{N}} f \tag{2}
\end{gather}
$$

综合 $(1)(2)$ 即证。

**第二步** 我们对一般的连续函数 $f$ 进行证明。

根据定义，$f$ 在 $A$ 上广义可积当且仅当 $f_{+},f_{-}$ 在 $A$ 上广义可积，后者成立当且仅当 $\int_{C_{N}}f_{+}$ 和 $\int_{C_{N}}f_{-}$ 有界。由于

$$
\begin{gather}
0\leq f_{\pm}(\mathbf{x})\leq\lvert f(\mathbf{x}) \rvert , \quad \lvert f(\mathbf{x}) \rvert =f_{+}(\mathbf{x})+f_{-}(\mathbf{x})
\end{gather}
$$

因此 $\int_{C_{N}}f_{+}$ 和 $\int_{C_{n}}f_{-}$ 有界当且仅当 $\int_{C_{N}}\lvert f \rvert$ 有界。此时，前两个序列收敛于 $\int_{A}f_{+}$ 和 $\int_{A}f_{-}$。由于收敛序列可以逐项相加，故序列

$$
\begin{gather}
\int_{C_{N}} f=\int_{C_{N}}f_{+}-\int_{C_{N}} f_{-}
\end{gather}
$$

收敛于 $\int_{A}f_{+}-\int_{A}f_{-}$，后者根据定义就是 $\int_{A}f$。

### Theorem 15.4

设开集 $A\subset \mathbb{R}^{n}$，$f,g\colon A\to \mathbb{R}$ 连续。

(a) 线性性：如果 $f,g$ 在 $A$ 上广义可积，那么 $af+bg$ 也是，并且
$$
\begin{gather}
\int_{A}(af+bg)=a \int_{A} f+b\int_{A} g
\end{gather}
$$
(b) 保序性：如果 $f,g$ 在 $A$ 上广义可积，且对 $\mathbf{x}\in A$ 有 $f(\mathbf{x})\leq g(\mathbf{x})$，那么
$$
\begin{gather}
\int_{A} f\leq \int_{A} g
\end{gather}
$$
特别地，
$$
\begin{gather}
\left\lvert  \int_{A} f  \right\rvert \leq \int_{A} \lvert f \rvert 
\end{gather}
$$
(c) 单调性：设 $B\subset A$ 是开集，如果 $f$ 在 $A$ 上非负且在 $A$ 上广义可积，则 $f$ 在 $B$ 上广义可积，且
$$
\begin{gather}
\int_{B} f\leq \int_{A} f
\end{gather}
$$
(d) 可加性：设 $A,B\subset \mathbb{R}^{n}$ 开，$f$ 在 $A\cup B$ 上连续。如果 $f$ 在 $A$ 和 $B$ 上广义可积，那么 $f$ 在 $A\cup B$ 和 $A\cap B$ 上广义可积，且
$$
\begin{gather}
\int_{A\cup B}f=\int_{A}f+\int_{B}f-\int_{A\cap B}f
\end{gather}
$$

#### Proof

选择一列紧致可求体积集 $C_{N}\subset A$ 使得 $\bigcup C_{N}=A$ 且 $C_{N}\subset \operatorname{Int}C_{N+1}$。

(a) 我们有

$$
\begin{gather}
\int_{C_{N}} \lvert af+bg \rvert \leq \lvert a \rvert \int_{C_{N}} \lvert f \rvert +\lvert b \rvert \int_{C_{N}} \lvert g \rvert 
\end{gather}
$$

不等式右侧有界，故 $af+bg$ 在 $A$ 上广义可积。对以下等式取极限即得积分的线性性：

$$
\begin{gather}
\int_{C_{N}} (af+bg)=a \int_{C_{N}} f+b\int_{C_{N}} g
\end{gather}
$$

(b) 如果 $f(\mathbf{x})\leq g(\mathbf{x})$，对下式取极限即证：

$$
\begin{gather}
\int_{C_{N}}f\leq \int_{C_{N}} g
\end{gather}
$$

(c) 如果 $D$ 是 $B$ 的紧致可求体积子集，那么 $D$ 同时也是 $A$ 的子集，因此

$$
\begin{gather}
\int_{D} f\leq \int_{A} f
\end{gather}
$$

由于 $D$ 是任意的，$f$ 在 $B$ 上广义可积，并且 $\int_{B}f\leq \int_{A}f$。

(d) 设 $D_{N}$ 是一列紧致可求体积集，其并集为 $B$，且 $D_{N}\subset \operatorname{Int}D_{N+1}$。令

$$
\begin{gather}
E_{N}=C_{N}\cup D_{N}, \quad F_{N}=C_{N}\cap D_{N}
\end{gather}
$$

则 $E_{N},F_{N}$ 是紧致可求体积集，它们的并集分别为 $A\cup B$ 和 $A\cap B$。此外，容易证明 $E_{N}\subset \operatorname{Int}E_{N+1}$ 且 $F_{N}\subset \operatorname{Int}F_{N+1}$。

普通积分的可加性给出

$$
\begin{gather}
\int_{E_{N}} f=\int_{C_{N}} f+\int_{D_{N}}-\int_{F_{N}} f \tag{$\ast$}
\end{gather}
$$

在上式中用 $\lvert f \rvert$ 替换 $f$，则 $\int_{E_{N}}\lvert f \rvert$ 和 $\int_{F_{N}}\lvert f \rvert$ 以 $\int_{C_{N}}\lvert f \rvert+\int_{D_{N}}\lvert f \rvert$ 为上界，从而 $f$ 在 $A\cup B$ 和 $A\cap B$ 上广义可积。最后，对 $(\ast)$ 取极限即证。

### Theorem 15.5

设 $A\subset \mathbb{R}^{n}$ 是有界开集，$f\colon A\to \mathbb{R}$ 有界连续，则广义积分 $\int_{A}f$ 存在。如果普通积分 $\int_{A}f$ 也存在，那么两个积分相等。

#### Proof

设 $Q$ 是包含 $A$ 的长方体。

**第一步** 我们证明广义积分 $\int_{A}f$ 存在。取 $M$ 使得 $\lvert f(\mathbf{x}) \rvert\leq M$，则对任意紧致可求体积集 $D\subset A$，有

$$
\begin{gather}
\int_{D} \lvert f \rvert \leq \int_{D} M\leq Mv(Q)
\end{gather}
$$

因此 $f$ 在 $A$ 上广义可积。

**第二步** 假设普通积分 $\int_{A}f$ 存在。我们首先考虑 $f$ 非负的情况。

设 $D$ 是 $A$ 的紧致可求体积子集，则

$$
\begin{align}
\int_{D} f &= \int_{D} f_{A} \\
&\leq \int_{Q} f_{A} \\
&= \mathrm{ord.} \int_{A} f
\end{align}
$$

由于 $D$ 是任意的，故

$$
\begin{gather}
\mathrm{ext}.\int_{A} f\leq \mathrm{ord.} \int_{A} f
\end{gather}
$$

另一方面，设 $P$ 是 $Q$ 的划分，假设 $R_{1},\dots,R_{k}$ 是包含于 $A$ 中的子长方体，令 $D=R_{1}\cup\dots \cup R_{k}$。

![](3-8.png)

我们有

$$
\begin{gather}
L(f_{A},P)=\sum_{i=1}^{k} m_{R_{i}}(f)v(R_{i})
\end{gather}
$$

并且

$$
\begin{align}
\sum_{i=1}^{k} m_{R_{i}}(f)v(R_{i}) &\leq \sum_{i=1}^{k} \int_{R_{i}} f \\
&= \int_{D} f \\
&\leq \mathrm{ext.} \int_{A} f
\end{align}
$$

由于 $P$ 是任意的，我们可得

$$
\begin{gather}
\mathrm{ord.}\int_{A} f\leq \mathrm{ext.} \int_{A} f
\end{gather}
$$

**第三步** 我们证明一般情况。

将 $f$ 写成 $f=f_{+}-f_{-}$，由于普通积分 $\int_{A}f$ 存在，故 $f_{+},f_{-}$ 的普通积分也存在。则我们有

$$
\begin{align}
\mathrm{ord.}\int_{A} f &=\mathrm{ord.}\int_{A}f_{+}-\mathrm{ord.}\int_{A} f_{-} \\
&= \mathrm{ext.}\int_{A} f_{+}-\mathrm{ext.}\int_{A}f_{-} \\
&=\mathrm{ext.}\int_{A} f
\end{align}
$$

这就完成了证明。

### Corollary 15.6

设 $S\subset \mathbb{R}^{n}$ 有界，$f\colon S\to \mathbb{R}^{n}$ 是有界连续函数。如果 $f$ 在 $S$ 上的普通积分存在，那么

$$
\begin{gather}
\mathrm{ord.}\int_{S} f=\mathrm{ext.}\int_{\operatorname{Int}S} f
\end{gather}
$$

#### Proof

应用 [[#Theorem 13.7]] 和 [[#Theorem 15.5]] 即可。

以上定理表明我们证明的任何关于广义积分的定理都可以迁移到普通积分上。下一章我们要证明的变量替换定理是一个重要例子。

最后我们再给出广义积分的一个等价定义，它通常被用来实际计算一个广义积分。

### Theorem 15.7

设开集 $A\subset \mathbb{R}^{n}$，$f\colon A\to \mathbb{R}$ 连续。设 $U_{1}\subset U_{2}\subset\cdots$ 是一列并集为 $A$ 的开集，则 $\int_{A}f$ 存在当且仅当序列 $\int_{U_{N}}\lvert f \rvert$ 存在且有界，此时

$$
\begin{gather}
\int_{A} f=\lim_{ N \to \infty } \int_{U_{N}}f
\end{gather}
$$

#### Proof

参考 [[#Theorem 15.3]] 的证明，我们只需证明 $f$ 非负的情况。

设 $\int_{A}f$ 存在，则广义积分的单调性表明 $\int_{U_{N}}f$ 存在，并且

$$
\begin{gather}
\int_{U_{N}}f\leq \int_{A} f
\end{gather}
$$

因此递增序列 $\int_{U_{N}}f$ 收敛，并且

$$
\begin{gather}
\lim_{ N \to \infty } \int_{U_{N}} f\leq \int_{A} f
\end{gather}
$$

反之，假设 $\int_{U_{N}}f$ 存在且有界。设 $D$ 是 $A$ 的紧致可求体积子集，由于 $D$ 被开集 $U_{1}\subset U_{2}\subset\cdots$ 覆盖，存在有限个，从而存在一个开集 $U_{M}$ 覆盖 $D$。因此

$$
\begin{gather}
\int_{D} f\leq \int_{U_{M}} f\leq \lim_{ N \to \infty } \int_{U_{N}} f
\end{gather}
$$

由于 $D$ 是任意的，故 $\int_{A}f$ 存在且

$$
\begin{gather}
\int_{A} f\leq \lim_{ N \to \infty } \int_{U_{N}} f
\end{gather}
$$

这就完成了证明。

在应用以上定理时，我们通常会选取 $U_{N}$ 使得它是可求体积的，并且 $f$ 在 $U_{N}$ 上有界。则 $\int_{U_{N}}f$ 作为一个普通积分存在，从而可由常见的技术进行计算。

### Example 15.8

定义

$$
\begin{gather}
A=\{ (x,y) : x>1, y>1 \}
\end{gather}
$$

设函数 $f(x,y)=1 /x^{2}y^{2}$，则 $f$ 在 $A$ 上有界，但 $A$ 无界。我们应用 [[#Theorem 15.7]] 来计算 $\int_{A}f$。

取 $U_{N}=(1,N)\times(1,N)$，则它是可求体积的。$f$ 在 $U_{N}$ 上有界，因为 $\overline{U}_{N}$ 紧致且 $f$ 在 $\overline{U}_{N}$ 上连续。因此普通积分 $\int_{U_{N}}f$ 存在，从而由 Fubini 定理得

$$
\begin{gather}
\int_{U_{N}} f=\int_{x=1}^{x=N} \int_{y=1}^{y=N} \frac{1}{x^{2}y^{2}}=\left( \frac{N-1}{N} \right)^{2}
\end{gather}
$$

从而 $\int_{A}f=1$。

![](3-9.png)

现在我们令 $B=(0,1)\times(0,1)$，仍令 $f(x,y)=1 /x^{2}y^{2}$，则 $B$ 有界，但 $f$ 在 $B$ 上无界。然而，如果我们令 $U_{N}=(1 /N,1)\times(1 /N,1)$，那么 $f$ 在 $U_{N}$ 上有界，于是

$$
\begin{gather}
\int_{U_{N}} f=(N-1)^{2}
\end{gather}
$$

因此 $\int_{B}f$ 不存在。