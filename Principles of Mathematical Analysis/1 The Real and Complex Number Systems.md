# Introduction 引言

开头，Rudin 指出了分析学研究中有理数的缺陷以及引入实数系统的必要性：有理数对于极限是不封闭的，这就是说有理数之间具有空隙，从而不满足“最小上界性质”，即完备性，尽管在两个有理数之间存在无穷多个不同的有理数。

## Definition 1.1 集合术语

设 $A$ 是集合，我们用 $x \in A$ 来表示 $x$ 是 $A$ 的元素，否则用 $x \not\in A$ 来表示 $x$ 不是 $A$ 的元素。空集 $\varnothing$ 是不包含任何元素的集合。如果集合 $A$ 的所有元素都是 $B$ 的元素，则称 $A$ 是 $B$ 的子集，记作 $A\subset B$。如果 $A\subset B$ 且 $A\neq B$，则称 $A$ 是 $B$ 的真子集。

## Definition 1.2 $\mathbb{Q}$

我们用 $\mathbb{Q}$ 来表示所有有理数构成的集合。

# Ordered Sets 有序集

本节和下一节讨论了一般的有序集和域，这里所做的讨论不仅对有理数成立，其对之后定义的实数、复数等结构同样成立。

## Definition 1.3 (total) order 全序

设 $S$ 是集合，$S$ 上的一个全序是其上的一个二元关系，满足以下性质：

1. 三分律：如果 $x,y \in S$，那么 $x<y,x=y,x>y$ 恰有一个成立。
2. 传递性：如果 $x,y,z \in S$，且 $x<y,y<z$，那么 $x<z$。

我们用 $x\leq y$ 来表示 $x<y$ 或 $x=y$。

## Definition 1.4 ordered set 有序集

一个有序集是一个集合 $S$，其上定义了一个全序。

例：有理数 $\mathbb{Q}$ 是一个有序集，其中 $r<s$ 定义为 $s-r$ 是一个正有理数。

## Definition 1.5 upper bound 上界，lower bound 下界

设 $S$ 是有序集，$E\subset S$，如果存在 $\beta \in S$ 使得对任意 $x \in E$ 有 $x\leq\beta$，则称 $E$ 有上界，且 $\beta$ 是它的一个上界。类似地我们可以定义下界，其中我们把 $\leq$ 替换为 $\geq$。

## Definition 1.6 supremum 上确界，infimum 下确界

设 $S$ 是有序集，$E\subset S$ 有上界。如果 $\alpha \in S$ 满足以下性质：

1. $\alpha$ 是 $E$ 的上界。
2. 如果 $\gamma<\alpha$ 那么 $\gamma$ 不是 $E$ 的上界。

则称 $\alpha$ 是 $E$ 的最小上界，或者上确界，记作

$$
\begin{gather}
\alpha=\sup E
\end{gather}
$$

最大下界，或下确界的定义是类似的。我们用

$$
\begin{gather}
\alpha=\inf E
\end{gather}
$$

来表示 $\alpha$ 是 $E$ 的下界，且任何 $\beta>\alpha$ 都不是 $E$ 的下界。

根据最大/最小性质，显然这样的上/下确界如果存在，总是唯一的。此外，上确界的最大性通常也有如下等价描述：

对任意 $\varepsilon>0$，存在 $x \in E$ 使得 $x>\alpha-\varepsilon$。

### Example 1.7

(a) 设 $A=\{ p \in \mathbb{Q} : p^2<2 \}$ 且 $B=\{ p \in \mathbb{Q} : p^2>2 \}$，则 $B$ 的所有元素都是 $A$ 的上界，然而 $A$ 的上确界在 $\mathbb{Q}$ 中不存在。类似地，$A$ 的所有元素都是 $B$ 的下界，但 $B$ 的下确界在 $\mathbb{Q}$ 中也不存在。

(b) $E$ 的上确界不一定是 $E$ 中的元素：设 $E_{1}=\{ r \in \mathbb{Q} : r<0 \}$，$E_{2}=\{ r \in \mathbb{Q} : r\leq 0 \}$，则 $\sup E_{1}=\sup E_{2}=0$，但 $0 \not\in E_{1}$ 而 $0 \in E_{2}$。

(c) 设 $E=\{ 1 /n : n \in \mathbb{N}^{*} \}$，则 $\sup E=1 \in E$，而 $\inf E=0\not\in E$。

## Definition 1.8 least-upper-bound property 最小上界性质（完备性）

称一个有序集 $S$ 具有最小上界性质，如果它满足以下性质：

如果 $E\subset S$，$E$ 非空，且 $E$ 有上界，那么 $\sup E$ 在 $S$ 中存在。

[[#Example 1.7]](a) 显然表明有理数 $\mathbb{Q}$ 不满足最小上界性质。我们不定义相对应的“最大下界性质”的原因是这两者是等价的，如以下定理所示。

## Theorem 1.9

设 $S$ 是一个有序集，满足最小上界性质。如果 $B\subset S$，$B$ 非空，且 $B$ 有下界，那么 $\inf B$ 在 $S$ 中存在。

### Proof

由于 $B$ 有下界，因此 $L$ 非空，因此 $\alpha=\sup L$ 在 $S$ 中存在。下面我们要证 $\alpha=\inf B$。

(a) $\alpha$ 是 $B$ 的下界：如果 $\gamma<\alpha$，那么 $\gamma$ 不是 $L$ 的上界，故 $\gamma \not\in B$，即对任意 $x \in B$ 有 $x\geq\alpha$。

(b) $\alpha$ 是最大下界：如果 $\beta>\alpha$，那么 $\beta \not\in L$，即 $\beta$ 不是下界。

# Fields 域

## Definition 1.10 field 域

一个域是一个集合 $\mathbb{F}$，其上定义了两个二元运算，称为加法和乘法，满足以下的域公理：

- (A) Axioms for addition 加法公理
	- (A1) 交换律：对任意 $x,y \in \mathbb{F}$ 有 $x+y=y+x$。
	- (A2) 结合律：对任意 $x,y,z \in \mathbb{F}$ 有 $(x+y)+z=x+(y+z)$。
	- (A3) 单位元：存在 $0 \in \mathbb{F}$ 使得对任意 $x \in \mathbb{F}$ 有 $x+0=x$。
	- (A4) 逆元：对任意 $x \in \mathbb{F}$ 存在 $-x \in \mathbb{F}$ 使得 $x+(-x)=0$。
- (M) Axioms for multiplication 乘法公理
	- (M1) 交换律：对任意 $x,y \in \mathbb{F}$ 有 $xy=yx$。
	- (M2) 结合律：对任意 $x,y,z \in \mathbb{F}$ 有 $(xy)z=x(yz)$。
	- (M3) 单位元：存在 $0\neq 1\in \mathbb{F}$ 使得对任意 $x \in \mathbb{F}$ 有 $1x=x$。
	- (M4) 逆元：对任意 $0\neq x \in \mathbb{F}$ 存在 $x^{-1} \in \mathbb{F}$ 使得 $x\cdot x^{-1}=1$。
- (D) The distributive law 分配律
	对任意 $x,y,z \in \mathbb{F}$ 有 $x(y+z)=xy+xz$。

结合律表明，在三个以上的连续加法或乘法中，没有必要添加括号。此外，我们通常用 $x-y$ 和 $x /y$ 来表示 $x+(-y)$ 和 $x\cdot y^{-1}$。

例：有理数 $\mathbb{Q}$ 在通常的加法和乘法下构成了一个域。

## Proposition 1.11

加法公理蕴含以下命题：

1. 如果 $x+y=x+z$，那么 $y=z$。
2. 如果 $x+y=x$，那么 $y=0$。
3. 如果 $x+y=0$，那么 $y=-x$。
4. $-(-x)=x$。

命题 1 称为加法的消去律。命题 2 和 3 分别表明了加法单位元和逆元的唯一性。

### Proof

如果 $x+y=x+z$，则我们有

$$
\begin{gather}
y=0+y=-x+x+y=-x+x+z=0+z=z
\end{gather}
$$

在命题 1 中令 $z=0$ 即证命题 2，再令 $z=-x$ 即证 3。最后，由于 $(-x)+(-(-x))=0$，根据逆元的唯一性，我们就有 $-(-x)=x$。

利用几乎相同的方法，我们可以证明以下命题，因此它的证明我们省略。

## Proposition 1.12

乘法公理蕴含以下命题：

1. 如果 $x\neq 0$ 且 $xy=xz$，那么 $y=z$。
2. 如果 $x\neq 0$ 且 $xy=x$，那么 $y=1$。
3. 如果 $x\neq 0$ 且 $xy=1$，那么 $y=1 /x$。
4. 如果 $x\neq 0$，那么 $(x^{-1})^{-1}=x$。

## Proposition 1.13

域公理蕴含以下命题：

1. $0x=0$。
2. 如果 $x\neq 0$ 且 $y\neq 0$ 那么 $xy\neq 0$。
3. $(-x)y=-(xy)=x(-y)$。
4. $(-x)(-y)=xy$。

### Proof

$0x+0x=(0+0)x=0x$，两边消去 $0x$ 即得 $0x=0$。下面，假设 $x,y$ 非零，但 $xy=0$，那么我们有

$$
\begin{gather}
1=\left( \frac{1}{y} \right)\left( \frac{1}{x} \right)xy=\left( \frac{1}{y} \right)\left( \frac{1}{x} \right)0=0
\end{gather}
$$

一个矛盾。因此 $xy\neq 0$。

命题 3 的第一个等式来源于 $(-x)y+xy=(-x+x)y=0y=0$，第二个等式同理。最后，我们有

$$
\begin{gather}
(-x)(-y)=-(x(-y))=-(-(xy))=xy
\end{gather}
$$

## Definition 1.14 ordered field 有序域

一个有序域是一个域 $\mathbb{F}$，其上定义了一个全序，使得

1. 对任意 $x,y,z \in \mathbb{F}$，如果 $y<z$ 那么 $x+y<x+z$。
2. 对任意 $x,y \in \mathbb{F}$，如果 $x>0$ 且 $y>0$，那么 $xy>0$。

如果 $x>0$，我们称 $x$ 是正的；如果 $x<0$，我们称 $x$ 是负的。

例：有理数 $\mathbb{Q}$ 在其上的通常序关系下构成了一个有序域。

## Proposition 1.15

有序域公理蕴含以下命题：

1. 如果 $x>0$ 那么 $-x<0$，反之亦然。
2. 如果 $x>0$ 且 $y<z$，那么 $xy<xz$。
3. 如果 $x<0$ 且 $y<z$，那么 $xy>xz$。
4. 如果 $x\neq 0$，那么 $x^2>0$。特别地，$1>0$。
5. 如果 $0<x<y$，那么 $0<1 /y<1 /x$。

### Proof

(1) 如果 $x>0$，那么 $0=-x+x>-x+0$，即 $-x<0$。如果 $x<0$，那么 $0=-x+x<-x+0$，即 $-x>0$。

(2) 由 $z>y$ 得 $z-y>y-y=0$，故 $x(z-y)>0$，因此

$$
\begin{gather}
xz=x(z-y)+xy>0+xy=xy
\end{gather}
$$

(3) 根据命题 (1)(2)，我们有 $(-x)(z-y)=-(x(z-y))>0$，故 $x(z-y)<0$，从而 $xz<xy$。

(4) 由于 $(-x)^2=x^2$，因此无论 $x>0$ 还是 $x<0$，均有 $x^2>0$。特别地，$1=1^2>0$。

(5) 根据命题 (2)(3)，一个正数乘以一个非正数是一个非正数，再根据 $y(1 /y)=1>0$，我们可知 $1 /y>0$，同理 $1 /x>0$。在不等式 $x<y$ 两边乘以 $(1 /y)(1 /x)$ 即得 $1 /y<1 /x$。

# The Real Field 实数域

本节通过有理数构造出了实数，并给出了实数完备性的若干推论。

## Theorem 1.16

存在一个有序域 $\mathbb{R}$，其具有最小上界性质，且包含 $\mathbb{Q}$ 作为子域。

这里最后一句话的意思是，$\mathbb{Q}\subset \mathbb{R}$，且 $\mathbb{R}$ 上的运算，当应用于 $\mathbb{Q}$ 中的元素时，与 $\mathbb{Q}$ 上通常的运算一致，并且 $\mathbb{Q}$ 中的正有理数也是 $\mathbb{R}$ 中的正数。我们称 $\mathbb{R}$ 中的元素为实数。

实数域的构造大多使用两种方法：Dedekind 分割以及 Cauchy 序列，这里我们采用前者的方案。

### Proof

**第一步** 我们定义一个实数为有理数 $\mathbb{Q}$ 的特定子集，称为分割。一个分割定义为 $\alpha \subset \mathbb{Q}$ 满足以下性质：

1. $\alpha$ 非空，$\alpha\neq \mathbb{Q}$。
2. 如果 $p \in\alpha$，$q \in \mathbb{Q}$，且 $q<p$，那么 $q \in\alpha$。（分割是有理数的“左半部分”）
3. 如果 $p \in\alpha$，那么存在 $r \in\alpha$ 使得 $p<r$。（分割没有最大元）

在证明中我们将用 $p,q,r,\dots$ 表示有理数，$\alpha,\beta,\gamma,\dots$ 表示分割。

性质 2 蕴含了以下命题：

- 如果 $p \in\alpha$ 且 $q \not\in\alpha$，那么 $p<q$。
- 如果 $r \not\in\alpha$ 且 $r<s$，那么 $s \not\in\alpha$。

这些结论将在后续的证明中发挥作用。

**第二步** 定义序关系 $\alpha<\beta$ 为 $\alpha \subset\beta$ 且 $\alpha\neq\beta$。我们来验证 $<$ 是一个全序关系。

首先，传递性是显然的：如果 $\alpha$ 是 $\beta$ 的真子集，$\beta$ 是 $\gamma$ 的真子集，那么 $\alpha$ 也是 $\gamma$ 的真子集。并且显然 $\alpha<\beta,\alpha=\beta,\beta<\alpha$ 至多有一个成立。

要证明三者至少有一个成立，我们假设 $\alpha<\beta,\alpha=\beta$ 都不成立，这就是说 $\alpha$ 不是 $\beta$ 的子集，故存在 $p \in\alpha$ 满足 $p\not\in\beta$，如果 $q \in\beta$，那么 $q<p$，因此 $q \in\alpha$，从而 $\beta \subset\alpha$。又由于 $\beta\neq\alpha$，即证 $\beta<\alpha$。

现在实数集 $\mathbb{R}$ 是一个有序集。

**第三步** $\mathbb{R}$ 满足最小上界性质。

设 $A\subset \mathbb{R}$ 非空，$\beta$ 是它的上界，我们定义 $\gamma$ 是所有 $\alpha \in A$ 的并集，下面要证 $\gamma \in \mathbb{R}$ 且 $\gamma=\sup A$。

由于 $A$ 非空，故存在 $\alpha_{0}\in A$，从而 $\gamma \supset\alpha_{0}$ 非空。由于对任意 $\alpha \in A$ 都有 $\alpha \subset\beta$，故 $\gamma \subset\beta$，因此 $\gamma\neq \mathbb{Q}$，这就满足了条件 (1)。

取 $p \in\gamma$，则存在 $\alpha_{1}\in A$ 使得 $p \in\alpha_{1}$，设 $q<p$，那么 $q \in\alpha_{1}\subset\gamma$，因此 $\gamma$ 满足条件 (2)。此外，我们还有 $r \in\alpha_{1}\subset\gamma$ 使得 $p<r$，故 $\gamma$ 满足条件 (3)。综上，我们有 $\gamma \in \mathbb{R}$。

$\gamma$ 显然是一个上界：$\alpha\leq\gamma$ 对任意 $\alpha \in A$ 成立。假设 $\delta<\gamma$，则存在 $s \in\gamma$ 使得 $s\not\in\delta$，于是有 $\alpha \in A$ 使得 $s \in\alpha$，从而 $\delta<\alpha$，因而 $\delta$ 不是上界。

综上，$\gamma=\sup A$ 在 $\mathbb{R}$ 中存在。

**第四步** 定义加法 $\alpha+\beta=\{ r+s : r \in\alpha,s \in\beta \}$，并定义 $0^{*}$ 为所有负有理数构成的集合，我们来验证 $\mathbb{R}$ 上的加法满足加法公理，其中 $0^{*}$ 扮演加法单位元的角色。

首先要验证加法是一个运算，即满足封闭性。显然 $\alpha+\beta$ 非空，如果 $r'\not\in\alpha,s'\not\in\beta$，那么 $r'+s'>r+s$ 对任意 $r \in\alpha$ 和 $s \in\beta$ 成立，因此 $\alpha+\beta\neq \mathbb{Q}$。

取 $p \in\alpha+\beta$，则 $p=r+s$，如果 $q<p$，那么 $q-s<r$，故 $q=(q-s)+s \in\alpha+\beta$，因此 $\alpha+\beta$ 满足条件 (2)。再取 $t \in\alpha$ 使得 $t>r$，则 $t+s \in\alpha+\beta$ 且 $t+s>p$，因此 $\alpha+\beta$ 满足条件 (3)。

(A1) $\alpha+\beta$ 由所有 $r+s$ 构成，而 $\beta+\alpha$ 由所有 $s+r$ 构成，根据 $\mathbb{Q}$ 上的交换律，我们就有 $\alpha+\beta=\beta+\alpha$。

(A2) 同理，其由 $\mathbb{Q}$ 上的结合律给出。

(A3) 如果 $r \in\alpha,s \in 0^{*}$，则 $r+s<r$，故 $r+s \in\alpha$，即 $\alpha+0^{*}\subset\alpha$。要得到反方向的包含，设 $p \in\alpha$，则有 $r \in\alpha$ 使得 $r>p$，于是 $p=r+(p-r)\in\alpha+0^{*}$，即得 $\alpha \subset\alpha+0^{*}$。

(A4) 这是四条加法公理中最复杂的一个，其难点在于如何不借助区间的语言（$(-\infty,a) \to (-\infty,-a)$）来表达“取相反数”这个概念，因为 $a=\sup\alpha$ 是一个实数，而除非我们完整地构造了实数域，否则我们不能随意地使用实数的性质。我们的动机来源于下图：

![图来源于 Understanding Analysis](1-1.png)

其中我们定义

$$
\begin{gather}
-\alpha=\{ r \in \mathbb{Q} : \text{存在 } s >0 \text{ 使得 } -r-s \not\in \alpha \}
\end{gather}
$$

换句话说，存在比 $-r$ 更小的数 $t=-r-s$ 不在 $\alpha$ 中。下证 $-\alpha \in \mathbb{R}$ 且 $\alpha+(-\alpha)=0^{*}$。

如果 $s \not\in\alpha$，取 $p=-s-1$，则 $-p-1 \not\in\alpha$，因此 $p \in-\alpha$，故 $-\alpha$ 非空。如果 $q \in\alpha$，那么 $-q\not\in -\alpha$（$-(-q)-s<q$，因此总是在 $\alpha$ 中），因此 $-\alpha \neq \mathbb{Q}$。

取 $p \in-\alpha$，$r>0$ 使得 $-p-r \not\in\alpha$，如果 $q<p$，那么 $-q-r>-p-r$，因此 $-q-r \not\in\alpha$，故 $q \in -\alpha$，因此 $-\alpha$ 满足条件 (2)。取 $t=p+r /2$，则 $t>p$ 且 $-t-r /2=-p-r \not\in\alpha$，因此 $-\alpha$ 满足条件 (3)。

如果 $r \in\alpha,s \in-\alpha$，则 $-s \not\in\alpha$，因此 $r<-s$，即 $r+s<0$，$\alpha+(-\alpha)\subset 0^{*}$。

反之，取 $v \in 0^{*}$，令 $w=-v /2$，则 $w>0$ 且存在 $n \in \mathbb{N}$ 使得 $nw \in\alpha$ 而 $(n+1)w \not\in\alpha$。（这是 $\mathbb{Q}$ 的 archimedean 性质）取 $p=-(n+2)w$，则 $p \in-\alpha$，且

$$
\begin{gather}
v=nw+p \in\alpha+(-\alpha)
\end{gather}
$$

因此 $0^{*}\subset\alpha+(-\alpha)$。

**第五步** 完成了全序与加法的定义，我们可以来验证有序域的第一条公理：

如果 $\alpha,\beta,\gamma \in \mathbb{R}$，且 $\beta<\gamma$，那么 $\alpha+\beta<\alpha+\gamma$。

事实上，根据定义我们立即得到 $\alpha+\beta \subset\alpha+\gamma$，而如果 $\alpha+\beta=\alpha+\gamma$，根据 [[#Proposition 1.11]](1) 可知 $\beta=\gamma$，矛盾。因此 $\alpha+\beta<\alpha+\gamma$。

此外，根据 [[#Proposition 1.15]](1) 我们可知 $\alpha>0^{*}$ 当且仅当 $-\alpha<0^{*}$。

**第六步** 乘法的定义比加法更为复杂，因为两个负数相乘得正数，故不能像加法那样直接在全体实数上定义。为此，我们首先在正实数 $\mathbb{R}^{+}$ 上定义乘法：$\alpha\beta$ 为所有满足 $p\leq rs$ 的有理数 $p$ 构成的集合，其中 $r \in\alpha$，$s \in\beta$，且 $r,s>0$。我们定义 $1^{*}$ 为所有小于 $1$ 的有理数构成的集合，它将扮演乘法单位元的角色。

先验证封闭性。显然 $\alpha\beta$ 非空且 $\alpha\beta\neq \mathbb{Q}$。设 $p \in\alpha\beta$，则存在正有理数 $r \in\alpha$、$s \in\beta$ 使得 $p\leq rs$。若 $q<p$，则 $q<p\leq rs$，故 $q \in\alpha\beta$，即证条件 (2)。为证条件 (3)，若 $p>0$，取 $r' \in\alpha$ 满足 $r'>r$，则 $r's>rs\geq p$ 且 $r's \in\alpha\beta$；若 $p\leq 0$，则取正有理数 $r\in\alpha$、$s\in\beta$，其乘积 $rs\in\alpha\beta$ 且 $rs>0\geq p$。故 $\alpha\beta$ 满足条件 (3)。

封闭性立即给出了有序域公理的第二条：若 $\alpha,\beta>0^{*}$，则 $\alpha\beta>0^{*}$。

接下来，(M1)(M2) 由 $\mathbb{Q}$ 上乘法的交换律和结合律直接给出。

(M3) 由于 $1^{*}\alpha$ 与 $\alpha$ 都包含 $\{ r \in \mathbb{Q} : r\leq 0 \}$，只需比较二者的正数部分。沿用 (A3) 的论证，把 $r+s$ 换成 $rs$、把 $-r$ 换成 $r^{-1}$、把 $0^{*}$ 换成 $1^{*}$ 即可。

(M4) 对 $\alpha>0^{*}$，定义其乘法逆元为

$$
\begin{gather}
\alpha^{-1}=\{ r \in \mathbb{Q} : r\leq 0 \} \cup \{ r \in \mathbb{Q}^{+} : \text{存在 } s>1 \text{ 使得 } r^{-1}s^{-1} \not\in \alpha \}
\end{gather}
$$

由 (M3) 中同样的替换可证 $\alpha^{-1}$ 非空，$\alpha^{-1}\neq \mathbb{Q}$，且满足条件 (2)。下面验证条件 (3)。取 $p \in\alpha^{-1}$；若 $p\leq 0$，取 $\alpha^{-1}$ 中任一正数即可（因 $\alpha>0^{*}$，$\alpha^{-1}$ 含正数），故不妨设 $p>0$。于是存在 $s>1$ 使得 $p^{-1}s^{-1}\not\in\alpha$，选 $t$ 满足 $p<t<ps$，则 $s'=ps /t>1$，且 $t^{-1}(s')^{-1}=p^{-1}s^{-1} \not\in \alpha$，故 $t \in\alpha^{-1}$ 且 $t>p$，条件 (3) 得证。

接下来证明 $\alpha\cdot\alpha^{-1}=1^{*}$。包含关系 $\alpha\cdot\alpha^{-1}\subset 1^{*}$ 亦可由上述替换论证得到。反之，设 $v \in 1^{*}$ 且 $v>0$（$v\leq 0$ 的情形是平凡的），取 $c>1$ 使得 $c<1 /v$，再取正有理数 $a \in\alpha$。由 $\mathbb{Q}$ 的 archimedean 性质，存在 $n \in \mathbb{N}$ 使得 $ac^{n}\in\alpha$ 而 $ac^{n+1}\not\in\alpha$，令 $r=ac^{n}$，$s=v /r$。由于 $c<1/v$，有 $(vc)^{-1}>1$，故可取 $1<u<(vc)^{-1}$，于是

$$
\begin{gather}
s^{-1}u^{-1}=\frac{r}{vu}>rc=ac^{n+1}\not\in\alpha
\end{gather}
$$

故 $s^{-1}u^{-1}\not\in\alpha$，从而 $s \in\alpha^{-1}$，即证 $v=rs \in\alpha\cdot\alpha^{-1}$。

最后是分配律。由于正数的和仍为正数，我们同样只需考虑正数部分。显然 $\alpha(\beta+\gamma)\subset\alpha\beta+\alpha\gamma$，因为 $p(q+r)=pq+pr$ 正是 $\mathbb{Q}$ 上的分配律。反之，设 $p_{1}q+p_{2}r \in\alpha\beta+\alpha\gamma$，其中 $p_1,p_2\in\alpha$，$q\in\beta$，$r\in\gamma$ 均为正数。取 $p \in\alpha$ 满足 $p>p_{1}$ 且 $p>p_{2}$，则 $p(q+r)=pq+pr\in\alpha(\beta+\gamma)$，且 $p(q+r)>p_{1}q+p_{2}r$，即得 $p_{1}q+p_{2}r\in\alpha(\beta+\gamma)$。

**第七步** 我们将正实数上的乘法扩展到实数集上。定义 $\alpha 0^{*}=0^{*}\alpha=0^{*}$，并定义

$$
\begin{gather}
\alpha\beta=\begin{cases}
(-\alpha)(-\beta), & \alpha<0^{*},\beta<0^{*} \\
-((-\alpha)\beta), & \alpha<0^{*},\beta>0^{*} \\
-(\alpha(-\beta)), & \alpha>0^{*},\beta<0^{*}
\end{cases}
\end{gather}
$$

这里右侧的乘积都是正实数上的乘积。通过重复应用 $-(-\gamma)=\gamma$，我们可以容易地证明 $\mathbb{R}$ 上的乘法满足乘法公理。最后，我们通过分类讨论对分配律

$$
\begin{gather}
\alpha(\beta+\gamma)=\alpha\beta+\alpha\gamma
\end{gather}
$$

进行证明。例如，假设 $\alpha>0^{*},\beta<0^{*},\beta+\gamma>0^{*}$，则 $\gamma=(\beta+\gamma)+(-\beta)$，从而由 $\mathbb{R}^{+}$ 上的分配律知

$$
\begin{gather}
\alpha\gamma=\alpha(\beta+\gamma)+\alpha(-\beta)=\alpha(\beta+\gamma)-\alpha \beta
\end{gather}
$$

两边加上 $\alpha \beta$ 就完成了这一情况的证明。其他的情况同理。

这样，我们就完成了完备有序域 $\mathbb{R}$ 的构造。

**第八步** 我们将每个 $r \in \mathbb{Q}$ 关联到有理分割 $r^{*}\in \mathbb{R}$，其中 $r^{*}$ 包含所有小于 $r$ 的有理数 $p$。这些分割满足以下性质：

(a) $r^{*}+s^{*}=(r+s)^{*}$。
(b) $r^{*}s^{*}=(rs)^{*}$。
(c) $r^{*}<s^{*}$ 当且仅当 $r<s$。

对于 (a)，取 $p \in r^{*}+s^{*}$，则 $p=u+v$，其中 $u<r,v<s$，于是 $p<r+s$，从而 $p \in(r+s)^{*}$。反之，设 $p \in(r+s)^{*}$，则 $p<r+s$，取 $t=(r+s-p) /2$，即得 $p=(r-t)+(s-t) \in r^{*}+s^{*}$。

对于 (b)，仿照第六和第七步中的工作，我们只需证明 $r,s>0$ 时的情况，并且由于 $rs>0$，故我们只需考虑正数部分。

容易证明 $r^{*}s^{*}\subset(rs)^{*}$。设 $p \in(rs)^{*}$ 且 $p>0$，则 $rs-p>0$，选取有理数 $0<\delta<\min\left( r,s, \frac{rs-p}{r+s} \right)$，则 $(r-\delta)(s-\delta) \in r^{*}s^{*}$，且

$$
\begin{align}
(r-\delta)(s-\delta)=rs-\delta(r+s)+\delta^{2}>rs-\delta(r+s)>p
\end{align}
$$

因此 $p \in r^{*}s^{*}$。

对于 (c)，如果 $r<s$，那么 $r \in s^{*}$，故 $r^{*}\subset s^{*}$。但 $r\not\in r^{*}$，故 $r^{*}\neq s^{*}$。

反之，如果 $r^{*}<s^{*}$，那么存在 $p \in s^{*}$ 使得 $p\not\in r^{*}$，故 $r\leq p<s$，即证。

**第九步**

从第八步中我们看到，将 $r \in \mathbb{Q}$ 映射到 $r^{*}\in \mathbb{R}$ 的函数保持了有理数上的加法、乘法和序关系。这就是说，$\mathbb{Q}$ 作为有序域与有理分割构成的有序域 $\mathbb{Q}^{*}$ 是同构的，我们把后者写成 $\mathbb{Q}$，其中的元素 $r^{*}$ 写作 $r$，然后“忘掉”原来的有理数结构，在这种新的有理数结构下，我们可以将 $\mathbb{Q}$ 视为实数域 $\mathbb{R}$ 的一个子域。

这种将同构的旧结构与新结构进行等同的操作在其他地方也有出现。例如，在复数域 $\mathbb{C}$ 的构造中，我们将实数域 $\mathbb{R}$ 嵌入 $\mathbb{C}$ 中作为它的子域；或者在更基础的层次，通过将 $n$ 与 $n /1$ 等同，我们得以将整数集 $\mathbb{Z}$ 嵌入有理数域 $\mathbb{Q}$ 中。

接下来我们来展示，通过最小上界性质，我们可以得到何种结果。

## Theorem 1.17

(a) 如果 $x,y \in \mathbb{R}$ 且 $x>0$，则存在正整数 $n$ 使得 $nx>y$。
(b) 如果 $x,y \in \mathbb{R}$ 且 $x<y$，则存在 $p \in \mathbb{Q}$ 使得 $x<p<y$。

命题 (a) 称为 $\mathbb{R}$ 的 archimedean 性质；命题 (b) 表明有理数 $\mathbb{Q}$ 在 $\mathbb{R}$ 中稠密：任意两个实数之间存在无穷多个有理数。

### Proof

(a) 假设 $A=\{ nx : n\in \mathbb{N}^{*} \}$ 有上界 $y$，则存在 $\alpha=\sup A$。由于 $x>0$，故 $\alpha-x<\alpha$，从而不是 $A$ 的上界，即存在 $m \in \mathbb{N}^{*}$ 使得 $\alpha-x<mx$，但此时 $\alpha<(m+1)x$，与 $\alpha$ 是上界矛盾。

(b) 根据 archimedean 性质，存在正整数 $n$ 使得 $n(y-x)>1$。此外，存在正整数 $m_{1},m_{2}$ 满足 $m_{1}>nx$，$m_{2}>-nx$，于是

$$
\begin{gather}
-m_{2}<nx<m_{1}
\end{gather}
$$

从而存在整数 $-m_{2}\leq m\leq m_{1}$ 使得 $m-1\leq nx<m$，因此

$$
\begin{gather}
nx<m\leq 1+nx<ny
\end{gather}
$$

即

$$
\begin{gather}
x<\frac{m}{n}<y
\end{gather}
$$

从以上证明中我们还可以得到如下结论：对任意实数 $x$，存在唯一的整数 $m$ 使得 $m\leq x<m+1$，我们记 $\lfloor x \rfloor=m$，称为向下取整。同理，存在唯一的整数 $n$ 使得 $n-1<x\leq n$，记 $\lceil x \rceil=n$，称为向上取整。

## Theorem 1.18

对任意实数 $x>0$ 和整数 $n>0$，存在唯一的实数 $y>0$ 使得 $y^{n}=x$。

这个实数 $y$ 称为 $x$ 的 $n$ 次根，记作 $\sqrt[n]{ x }$ 或 $x^{1/n}$。

### Proof

容易证明唯一性：如果 $0<y_{1}<y_{2}$，那么 $y_{1}^{n}<y_{2}^{n}$。

定义 $E$ 为所有满足 $t^{n}<x$ 的正实数 $t$ 构成的集合。如果 $t=\frac{x}{1+x}$，则 $t<1$，故 $t^{n}<t<x$，因此 $E$ 非空。如果 $t>1+x$，那么 $t^{n}>t>x$，故 $t\not\in E$，因而 $1+x$ 是 $E$ 的上界。最小上界性质表明

$$
\begin{gather}
y=\sup E
\end{gather}
$$

在 $\mathbb{R}$ 中存在。我们通过排除 $y^{n}<x$ 和 $y^{n}>x$ 两种情况来证明 $y^{n}=x$。

根据等式 $b^{n}-a^{n}=(b-a)(b^{n-1}+ab^{n-2}+\dots+a^{n-1})$，如果 $b>a>0$，则我们有

$$
\begin{gather}
b^{n}-a^{n}<(b-a)n b^{n-1}
\end{gather}
$$

假设 $y^{n}<x$，取 $0<h<1$ 满足

$$
\begin{gather}
h<\frac{x-y^{n}}{n(y+1)^{n-1}}
\end{gather}
$$

令 $a=y,b=y+h$，则

$$
\begin{gather}
(y+h)^{n}-y^{n}<hn (y+h)^{n-1}<hn(y+1)^{n-1}<x-y^{n}
\end{gather}
$$

因此 $(y+h)^{n}<x$，从而 $y+h \in E$，这与 $y$ 是上界矛盾。

假设 $y^{n}>x$，令

$$
\begin{gather}
k=\frac{y^{n}-x}{ny^{n-1}}
\end{gather}
$$

取 $t\geq y-k$，则我们有

$$
\begin{gather}
y^{n}-t^{n}\leq y^{n}-(y-k)^{n}<kny^{n-1}=y^{n}-x
\end{gather}
$$

因此 $t^{n}>x$，从而 $t \not\in E$，这表明 $y-k$ 也是 $E$ 的上界，这与 $y$ 是最小上界矛盾。

## Corollary 1.19

如果 $a,b$ 是正实数且 $n$ 是正整数，则

$$
\begin{gather}
(ab)^{1/n}=a^{1/n}b^{1/n}
\end{gather}
$$

### Proof

取 $\alpha=a^{1/n},\beta=b^{1/n}$，则

$$
\begin{gather}
ab=\alpha^{n}\beta^{n}=(\alpha\beta)^{n}
\end{gather}
$$

[[#Theorem 1.18]] 的唯一性部分立即给出

$$
\begin{gather}
(ab)^{1/n}=\alpha\beta=a^{1/n}b^{1/n}
\end{gather}
$$

# The Extended Real Number System 扩展实数系

## Definition 1.20 $\overline{\mathbb{R}}$

扩展实数系 $\overline{\mathbb{R}}$ 包含了实数域 $\mathbb{R}$，以及两个不同对象 $+\infty$ 和 $-\infty$。我们保留 $\mathbb{R}$ 上的标准序关系，并对任意 $x \in \mathbb{R}$ 定义

$$
\begin{gather}
-\infty<x<+\infty
\end{gather}
$$

我们称 $+\infty$ 为正无穷，$-\infty$ 为负无穷，而每个 $x \in \mathbb{R}$ 都是有限数。

根据以上定义，显然 $+\infty$ 是扩展实数系的每个子集的上界，从而每个子集都有上确界：实数的完备性保证了在实数中有上界的集合存在有限的上确界，而如果集合 $E$ 在实数中无上界，那么 $\sup E=+\infty$。

扩展实数系不构成域，但我们有时采用以下约定：

(a) 如果 $x \in \mathbb{R}$，则 $x+\infty=+\infty$，$x-\infty=-\infty$，$\frac{x}{\pm \infty}=0$。
(b) 如果 $x>0$，则 $x\cdot(+\infty)=+\infty$，$x\cdot(-\infty)=-\infty$。
(c) 如果 $x<0$，则 $x\cdot(+\infty)=-\infty$，$x\cdot(-\infty)=+\infty$。

# The Complex Field 复数域

本节通过实数构造出了复数域，并给出了复数的若干基本代数性质。

## Definition 1.21 complex number 复数

一个复数是实数的有序对 $(a,b)$，所有复数构成的集合记作 $\mathbb{C}$。

设 $z=(a,b),w=(c,d)$ 是两个复数，我们定义复数的加法和乘法为

$$
\begin{gather}
z+w=(a+c,b+d), \quad zw=(ac-bd,ad+bc)
\end{gather}
$$

## Theorem 1.22

复数 $\mathbb{C}$ 在定义的加法和乘法下构成一个域，其加法和乘法的单位元分别是 $(0,0)$ 和 $(1,0)$。

### Motivation

从代数角度来说，复数的运算完全和实系数多项式同构：设 $x$ 是一形式变量，则 $(a,b)\cdot(c,d)$ 的结果与 $(a+bx)(c+dx)$ 按照分配律展开后的形式完全相同，只要我们在最后将所有 $x^{2}$ 出现的地方用 $-1$ 替代。从这一角度来看，域的大多数公理对于复数来说就是显然的了。

### Proof

对于加法公理，封闭性，交换律和结合律是显然的，$(0,0)$ 是单位元容易验证，$(a,b)$ 的加法逆元为 $(-a,-b)$。

对于乘法公理同理，$(1,0)$ 是单位元容易验证。唯一需要仔细思考的是乘法逆元。考虑上面提到的等价对应，如果 $(a,b)\neq (0,0)$，则

$$
\begin{gather}
\frac{1}{a+bx}=\frac{a-bx}{(a+bx)(a-bx)}=\frac{a-bx}{a^{2}-b^{2}x^{2}}=\frac{a-bx}{a^{2}+b^{2}}
\end{gather}
$$

因此 $(a,b)$ 的乘法逆元为 $\left( \frac{a}{a^{2}+b^{2}},\frac{-b}{a^{2}+b^{2}} \right)$。最后，分配律也是同理。

## Theorem 1.23

对任意 $a,b \in \mathbb{R}$ 有

$$
\begin{gather}
(a,0)+(b,0)=(a+b,0), \quad (a,0)(b,0)=(ab,0)
\end{gather}
$$

证明是平凡的。

该定理表明，通过将实数 $a$ 与 $(a,0)$ 进行等同，我们可以将 $\mathbb{R}$ 嵌入 $\mathbb{C}$ 中作为它的子域。

## Definition 1.24 $i$

定义虚数单位 $i=(0,1)$。

## Theorem 1.25

$i^{2}=-1$。

直接验证即可：$i^{2}=(0,1)(0,1)=(-1,0)=-1$。

## Theorem 1.26

如果 $a,b \in \mathbb{R}$，则 $(a,b)=a+bi$。

证明也是平凡的。

以上两个定理表明复数的经典表示与 [[#Definition 1.21 complex number 复数]] 是一致的。

## Definition 1.27 conjugate 共轭，real part 实部，imaginary part 虚部

设 $a,b \in \mathbb{R}$，$z=a+bi$，则称复数 $\overline{z}=a-bi$ 是 $z$ 的共轭，$a,b$ 分别是 $z$ 的实部和虚部，记作 $a=\mathrm{Re}(z),b=\mathrm{Im}(z)$。

## Theorem 1.28

设 $z,w \in \mathbb{C}$，则

1. $\overline{z+w}=\overline{z}+\overline{w}$。
2. $\overline{zw}=\overline{z}\cdot \overline{w}$。
3. $z+\overline{z}=2\mathrm{Re}(z),z-\overline{z}=2i\mathrm{Im}(z)$。
4. 如果 $z\neq 0$，那么 $z \overline{z}$ 是正实数。

### Proof

命题 (1)(2)(3) 是平凡的。设 $z=a+bi$，其中 $a,b \in \mathbb{R}$，则 $z \overline{z}=a^{2}+b^{2}$，即证命题 (4)。

## Definition 1.29 absolute value 绝对值

设 $z \in \mathbb{C}$，定义它的绝对值为 $\lvert z \rvert=(z \overline{z})^{1/2}$。

平方根的唯一存在性保证了以上定义是良好的。特别地，如果 $x \in \mathbb{R}$，那么 $\lvert x \rvert=\sqrt{ x^{2} }$，因此 $\lvert x \rvert=x$ 如果 $x\geq 0$，$\lvert x \rvert=-x$ 如果 $x<0$。

## Theorem 1.30

设 $z,w \in \mathbb{C}$，则

1. （正定性）$\lvert z \rvert\geq 0$，其中等号成立当且仅当 $z=0$。
2. $\lvert \overline{z} \rvert=\lvert z \rvert$。
3. $\lvert zw \rvert=\lvert z \rvert\lvert w \rvert$。
4. $\lvert \mathrm{Re}(z) \rvert\leq\lvert z \rvert$。
5. （三角不等式）$\lvert z+w \rvert\leq\lvert z \rvert+\lvert w \rvert$。

### Proof

命题 (1)(2) 是平凡的。设 $z=a+bi,w=c+di$，对于 (3)，我们有

$$
\begin{gather}
\lvert zw \rvert ^{2}=(ac-bd)^{2}+(ad+bc)^{2}=(a^{2}+b^{2})(c^{2}+d^{2})=\lvert z \rvert ^{2}\lvert w \rvert ^{2}
\end{gather}
$$

两边取平方根即可。对于 (4)，由于 $a^{2}\leq a^{2}+b^{2}$，因此

$$
\begin{gather}
\lvert a \rvert =\sqrt{ a^{2} }\leq \sqrt{ a^{2}+b^{2} }=\lvert z \rvert 
\end{gather}
$$

最后，由于 $z \overline{w}$ 的共轭是 $\overline{z}w$，因此

$$
\begin{align}
\lvert z+w \rvert ^{2}&=(z+w)(\overline{z}+\overline{w}) \\
&=z\overline{z}+w\overline{w}+z \overline{w}+\overline{z}w \\
&=\lvert z \rvert ^{2}+\lvert w \rvert ^{2}+2\mathrm{Re}(z \overline{w}) \\
&\leq \lvert z \rvert ^{2}+\lvert w \rvert ^{2}+2\lvert zw \rvert \\
&=(\lvert z \rvert +\lvert w \rvert )^{2} 
\end{align}
$$

两边取平方根即证。

## Theorem 1.31 (Cauchy-Schwarz)

如果 $a_{1},\dots,a_{n},b_{1},\dots,b_{n}$ 是复数，则

$$
\begin{gather}
\left\lvert  \sum_{j=1}^{n} a_{j} \overline{b}_{j}  \right\rvert ^{2}\leq \sum_{j=1}^{n} \lvert a_{j} \rvert ^{2} \sum_{j=1}^{n} \lvert b_{j} \rvert ^{2}
\end{gather}
$$

### Proof #1

应用内积空间 $\mathbb{C}^{n}$ 上的 Cauchy-Schwarz 不等式即得

$$
\begin{gather}
\left\lvert  \sum_{j=1}^{n} a_{j} \overline{b}_{j}  \right\rvert ^{2}=\lvert \langle \mathbf{a},\mathbf{b} \rangle  \rvert ^{2}\leq \lVert \mathbf{a} \rVert ^{2}\lVert \mathbf{b} \rVert ^{2}=\sum_{j=1}^{n} \lvert a_{j} \rvert ^{2}\sum_{j=1}^{n} \lvert b_{j} \rvert ^{2}
\end{gather}
$$

其中 $\mathbf{a}=(a_{1},\dots,a_{n}),\mathbf{b}=(b_{1},\dots,b_{n})$。

### Proof #2 (Rudin)

令 $A=\sum \lvert a_{j} \rvert^{2}$，$B=\sum\lvert b_{j} \rvert^{2}$，$C=\sum a_{j} \overline{b_{j}}$，如果 $B=0$，那么 $b_{j}=0$，从而结论是平凡的。否则，我们有

$$
\begin{align}
\sum_{j=1}^{n} \lvert Ba_{j}-Cb_{j} \rvert ^{2} &= \sum_{j=1}^{n} (Ba_{j}-Cb_{j})(B \overline{a}_{j}-\overline{C} \overline{b}_{j}) \\
&=B^{2} \sum_{j=1}^{n} \lvert a_{j} \rvert ^{2}-B \overline{C}\sum_{j=1}^{n} a_{j}\overline{b}_{j}-BC\sum_{j=1}^{n} \overline{a}_{j}b_{j}+\lvert C \rvert ^{2}\sum_{j=1}^{n} \lvert b_{j} \rvert ^{2} \\
&=B^{2}A-B\lvert C \rvert ^{2}=B(AB-\lvert C \rvert ^{2})\geq 0
\end{align}
$$

由于 $B>0$，两边消去 $B$ 即得 $AB\geq \lvert C \rvert^{2}$。

# Euclidean Spaces 欧几里得空间

## Definition 1.32 $\mathbb{R}^{k}$

对任意正整数 $k$，定义 $\mathbb{R}^{k}$ 为所有 $k$ 元组

$$
\begin{gather}
\mathbf{x}=(x_{1},\dots,x_{k})
\end{gather}
$$

构成的集合，其中 $x_{j}\in \mathbb{R}$，称为 $\mathbf{x}$ 的第 $j$ 个坐标（$j=1,\dots,k$）。

设 $\mathbf{y}=(y_{1},\dots,y_{k})\in \mathbb{R}^{k}$ 且 $\alpha \in \mathbb{R}$，我们定义 $\mathbb{R}^{k}$ 上的加法和数乘为

$$
\begin{gather}
\mathbf{x}+\mathbf{y}=(x_{1}+y_{1},\dots,x_{k}+y_{k}), \quad \alpha \mathbf{x}=(\alpha x_{1},\dots,\alpha x_{k})
\end{gather}
$$

定义 $\mathbf{0}\in \mathbb{R}^{k}$ 为 $\mathbf{0}=(0,\dots,0)$，容易证明，在以上定义的加法和数乘下，$\mathbb{R}^{k}$ 构成了一个 $\mathbb{R}$ 上的向量空间，其中 $\mathbf{0}$ 是加法单位元而 $1 \in \mathbb{R}$ 是数乘单位元。

我们还定义 $\mathbb{R}^{k}$ 上的内积为

$$
\begin{gather}
\mathbf{x}\cdot \mathbf{y}=\sum_{j=1}^{k} x_{j}y_{j}
\end{gather}
$$

以及 $\mathbf{x}$ 的范数

$$
\begin{gather}
\lvert \mathbf{x} \rvert =(\mathbf{x}\cdot \mathbf{x})^{1/2}=\left( \sum_{j=1}^{k} \lvert x_{j} \rvert ^{2} \right)^{1/2}
\end{gather}
$$

带有如上定义的向量空间以及内积结构的空间 $\mathbb{R}^{k}$ 称为 $k$ 维 euclidean 空间。

## Theorem 1.33

设 $\mathbf{x},\mathbf{y},\mathbf{z}\in \mathbb{R}^{k}$ 且 $\alpha \in \mathbb{R}$，则

1. （正定性）$\lvert \mathbf{x} \rvert\geq 0$，等号成立当且仅当 $\mathbf{x}=\mathbf{0}$。
2. （齐次性）$\lvert \alpha \mathbf{x} \rvert=\lvert \alpha \rvert\lvert \mathbf{x} \rvert$。
3. （Cauchy-Schwarz）$\lvert \mathbf{x}\cdot \mathbf{y} \rvert\leq\lvert \mathbf{x} \rvert\lvert \mathbf{y} \rvert$。
4. （三角不等式 I）$\lvert \mathbf{x}+\mathbf{y} \rvert\leq\lvert \mathbf{x} \rvert+\lvert \mathbf{y} \rvert$。
5. （三角不等式 II）$\lvert \mathbf{x}-\mathbf{z} \rvert\leq\lvert \mathbf{x}-\mathbf{y} \rvert+\lvert \mathbf{y}-\mathbf{z} \rvert$。

### Proof

命题 (1)(2) 是平凡的。命题 (3) 是 [[#Theorem 1.31 (Cauchy-Schwarz)]] 的直接推论，从而我们有

$$
\begin{align}
\lvert \mathbf{x}+\mathbf{y} \rvert ^{2} &=(\mathbf{x}+\mathbf{y})\cdot(\mathbf{x}+\mathbf{y}) \\
&=\mathbf{x}\cdot \mathbf{x}+2\mathbf{x}\cdot \mathbf{y}+\mathbf{y}\cdot \mathbf{y} \\
&\leq \lvert \mathbf{x} \rvert ^{2}+2\lvert \mathbf{x} \rvert \lvert \mathbf{y} \rvert +\lvert \mathbf{y} \rvert ^{2} \\
&=(\lvert \mathbf{x} \rvert +\lvert \mathbf{y} \rvert )^{2}
\end{align}
$$

两边取平方根即可。最后，在命题 (4) 中取 $\mathbf{x}\leftarrow \mathbf{x}-\mathbf{y}$，$\mathbf{y}\leftarrow \mathbf{y-\mathbf{z}}$ 即得命题 (5)。

以上定理的 (1)(2)(5) 允许我们将 $\mathbb{R}^{k}$ 作为一个度量空间。通常我们称 $\mathbb{R}^{1}=\mathbb{R}$ 为直线或实数轴；称 $\mathbb{R}^{2}$ 为平面或复平面，因为除了复乘法，$\mathbb{R}^{2}$ 与 $\mathbb{C}$ 作为实向量空间是完全同构的。