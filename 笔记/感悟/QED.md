---
up:
  - "[[感悟]]"
  - 
related:
date: 2026-01-31
tags:
  - 量子场论
  - 概念梳理
---
# 1. U(1) 群

QED 可以说是 $U(1)$ 群的表示论的极佳运用，通过考虑其局域化后的规范不变性，可以得到直达电磁力的路径

## 1.1 内部对称性

QFT 中讨论的所有对称性可以分为 **时空对称性+内部对称性** (由 Coleman 证明)，其中的时空对称性就是指在庞加莱群的作用下保持不变的意思，我们还根据庞加莱群的不可约表示可以在自由理论中定义粒子 ([[希尔伯特空间、粒子、算符]])。

内部对称性就是指除此之外的对称性，换言之系统总的对称性可以如下的表示
$$\mathcal{G} = \mathcal{Poincare} \otimes \mathcal{Inter} $$
 用几何的角度，可以说：时空对称性是闵式时空作为底流形所必然承载的结构，而在每个时空点 $x$ 上都有表示空间 (纤维)，场就是某个纤维丛的截面，对于标量场它就是平凡线丛的截面，对于旋量场它就是旋量丛的截面...内部对称性就是主丛的结构。

## 1.2 局域对称性

上面已经剧透了 **主丛** ，这就暗示了群结构可能并非全局的，也就是说每个时空点上都可以附带一个群结构
$$g = g(x) $$
将会看到，正是注意到这个情况，我们能够自然的引出 **最小耦合** 并赋予QED理论来源

## 1.3 U(1) 群介绍

### 1.3.1 定义及性质

顾名思义 $U(1)$ 群就是所有 1×1 酉矩阵构成的群
$$U(1) = \{ U\in GL(1,\mathbb{C}) \mid U^{\dagger}U=1 \} $$
$1\times{1}$ 的 $\mathbb{C}$ 上的矩阵就是普普通通的复数，所以它也可以说是这样的群 $\{ z\mid |z|=1 \}$ (群乘法就是复数乘法) 而这样的复数都可以指数表示为 $z=e^{ i\theta },\theta \in \mathbb{R}$ 所以从群结构上看 $U(1)\cong S^1$ 

- 群的单位元显然是
  $$1 $$
  或者用指数参数说是 $\theta=2k\pi$
- 逆元被定义为复数的复共轭
  $$z^{-1} \equiv z^{*} $$

由于群乘法是复数乘法，所以是乘法交换的，$U(1)$ **是阿贝尔群**。我们知道 $\mathbb{C}\cong\mathbb{R}^{2},U(1)\cong S^1$ 而在 $\mathbb{R}^{2}$ 中 $S^1$ 是闭得且有界的所以**是紧的**。考虑其指数形式 (也说明了 $U(1)$ **是李群**) ，对于任意的两点 $\theta_{1},\theta_{2}$ 存在连续的路径 $\gamma(t)=\exp[i(1-t)\theta_{1}+it\theta_{2}]$ 将它们连接，所以**是连通的**。

### 1.3.2 李代数

作为李群 $U(1)$ 当然有它的李代数。记为 $\mathfrak{u}(1)$ 它被定义为所有满足反厄米 1×1 矩阵
$$\mathfrak{u}(1) = \{ X\mid X^{\dagger}=-X \} $$
由于是 1×1 复矩阵，所以也就是复数，再加上反厄米条件知道是纯虚数所以
$$X = i\theta,\quad \theta \in \mathbb{R} $$
因此 $\mathfrak{u}(1)\cong\mathbb{R}$ 。李群李代数间总是有指数关系的，即 $U = \exp(X) = e^{ i\theta }$ 这就是 $U(1)$ 的指数形式

由于 $U(1)$ 是阿贝尔的，所以李代数总是对易的。更多可见 [[U(1)]]


### 1.3.3 不可约表示

设 $\rho$ 是一个有限维表示，由于 $U(1)$ 是阿贝尔的，所以
$$\rho(g_{1})\rho(g_{2})=\rho(g_{2})\rho(g_{1}),\quad g_{1},g_{2}\in U(1) $$
而一组两两对易的复矩阵可以同时三角化；若表示是不可约的，则它必须是一维。否则可以找到不变子空间。所以 $U(1)$ 的所有有限维不可约复表示都是 1 维。

一维表示就是群同态 $\rho:U(1)\to \mathbb{C}^{*}$ 是连续的，因为 U(1) 是紧群，连续表示自动是酉的，所以值必须落在单位圆上 $\rho(g)\in U(1)$ 于是只要找到所有连续群同态 $U(1)\to U(1)$ 即可。

考虑到 $U(1)$ 可以参数化为 $e^{ i\theta },\theta\in S^1$ 所以设
$$\rho(e^{ i\theta }) = e^{ if(\theta) } $$
于是同态条件为
$$f(\theta_{1})+f(\theta_{2}) = f(\theta_{1}+\theta_{2}) $$
这个方程的解是 $f(\theta)=k\theta,k\in \mathbb{R}$ 现在再考虑到周期性条件 $e^{ i\theta } = e^{ i(\theta+2\pi) }$ 所以要求 $k\in \mathbb{N}$ 否则不满足单值性。

最后我们就得到了 $U(1)$ 群的不可约表示为
$$\rho_{n}(e^{ i\theta }) = e^{ in \theta } , n\in \mathbb{N} $$


### 1.3.4 全局 U(1) 对称性与电荷守恒

如果我们假定一个系统有全局的 $U(1)$ 对称性，则由 Noether 定理我们可以得到一个守恒律。下面来着手构建出来。

对于这个首先要知道系统的拉式量，在[[QED#2. 自由拉式量的构造]]中会讲，这里先给出结果。

- 复标量场QED的自由拉式量为
  $$ \mathcal{L} =   \partial_{\mu}\phi^{*}\partial^{\mu}\phi - m^{2}\phi^{*}\phi$$
- 旋量场QED的自由拉式量为
  $$\mathcal{L} = -\frac{1}{4} F^{\mu \nu}F_{\mu \nu} + \bar{\psi}(i\not{\!\partial}-m)\psi $$

先来看复标量场的，$U(1)$ 变换是
$$\begin{align}
\phi(x) &\longmapsto e^{ in\alpha }\phi(x) \\
\phi^{*}(x) &\longmapsto e^{ -in\alpha }\phi^{*}(x)
\end{align} $$
容易验证，这样的拉式量在变换下保持不变。对于无穷小变换
$$\begin{align}
\delta \phi &= in\alpha \phi \\
\delta \phi^{*} &= -in\alpha \phi^{*}
\end{align} $$
$$j^{\mu} = \frac{\partial \mathcal{L}}{\partial(\partial_{\mu}\phi)}\delta \phi + \frac{\partial \mathcal{L}}{\partial(\partial_{\mu}\phi^{*})}\delta \phi^{*} = i(\phi^{*}\partial^{\mu}\phi - \phi \partial^{\mu}\phi^{*}) $$
可以验证的它是守恒的 $\partial_{\mu}j^{\mu}=0$ 实际上它就是电荷守恒的方程。对应的守恒荷是
$$Q = \int \mathrm{d^{3}x}\,j^{0} $$


再看旋量场的，$U(1)$ 变换 (全局) 是
$$\begin{align}
\psi(x) &\longmapsto e^{ in\alpha }\psi(x) \\
\bar{\psi}(x) &\longmapsto e^{ -in\alpha }\bar{\psi}(x) \\
A^{\mu}(x) & \longmapsto A^{\mu}(x)
\end{align} $$
容易验证此时的拉式量是不变的。对于无穷小变换
$$\begin{align}
\delta \psi &= in\alpha \psi \\
\delta \bar{\psi} &= -in\alpha \bar{\psi} \\
\delta A^{\mu} &= 0
\end{align} $$
$$j^{\mu} = \frac{\partial \mathcal{L}}{\partial(\partial_{\mu}\psi)}\delta \psi + \frac{\partial \mathcal{L}}{\partial(\partial_{\mu}\bar{\psi})}\delta \bar{\psi} = in\alpha \bar{\psi}\gamma^{\mu}\psi $$
其中的 $n,\alpha$ 在变换中是常的，不重要，所以守恒流是
$$j^{\mu} = \bar{\psi}\gamma^{\mu}\psi $$
容易验证的 $\partial_{\mu}j^{\mu}=0$ 定义守恒荷
$$Q = \int \mathrm{d^{3}x}\, j^{0} = \int \mathrm{d^{3}x}\,\psi ^{\dagger}\psi $$

### 1.3.5 局域 U(1) 对称性与最小耦合

当对称性升级为局域的时候，就得考虑“联络”的事了。设有场 $\psi(x)$ ，局域 $U(1)$ 变换是说
$$\psi(x) \longmapsto \psi'(x') = e^{ in \theta }\psi(x) $$
问题马上就来了，因为普通的导数不再协变
$$\partial_{\mu}\psi \longmapsto e^{ in \theta }[\partial_{\mu}\psi + in(\partial_{\mu}\theta)\psi] $$
局域对称性意味着：在每个点 $x$，上面附着一个独立的内部 $U(1)$ 空间。现在问题变成：如何比较 $ψ(x)$ 与 $ψ(x+dx)$？因为它们属于不同纤维，不能直接相减。这正是一个 $U(1)$ 主丛。在任意主丛中，要定义“平行移动”，必须引入一个联络 1-形式 $A_μ$。也就是说进行这样一个替换即可
$$\partial_{\mu} \to D_{\mu} = \partial_{\mu} + iA_{\mu} $$
那么可以验证的，此时就满足的局域 $U(1)$ 对称性了
$$D_{\mu}\psi \longmapsto e^{ in \theta }D_{\mu}\psi $$
当然这样也就不再是自由理论了，而是一个相互作用的理论了，物质场与规范场的相互作用。

# 2. 自由拉式量的构造

自由的和有相互作用的当然不一样，就像谐振子一样可以说是“可精确解”的而高阶项就得微扰了，所以首先来研究自由场。拉式量的构建是遵循以下原则的

1. 庞加莱不变
2. 场方程线性
3. $U(1)$ 对称性
4. 可重整化

## 2.1 复标量场

复标量场可以看作是两个实标量场的组合，也是最简单的有内部自由度的场。在几何上，它对应于时空底流形上的一个复线丛的截面。同时由于它自旋为 $0$ 所以描述的是如 $\pi^{\pm}$ 介子这样的粒子。

由于场方程是线性的，所以拉式量必须是场的二次型，故可以的项有
$$\partial_{\mu}\phi^{*}\partial^{\nu}\phi ,\quad \phi^{*}\phi, \quad \phi^{2} ,\quad (\phi^{*})^{2},\quad \partial_{\mu}\phi \partial^{\mu}\phi ,\quad \partial_{\mu}\phi^{*}\partial^{\mu}\phi^{*} $$
考虑到拉式量必须是洛伦兹不变的，所以第一种类型种只有
$$\partial_{\mu}\phi^{*}\partial^{\mu}\phi $$
考虑到拉式量必须是 $U(1)$ 不变的，所以后四者不行，因为
$$\phi^{2}\to e^{ 2in\alpha }\phi^{2} \neq \phi^{2} ,\quad (\phi^{*})^{2} \to e^{ -2in\alpha }(\phi^{*})^{2}\neq(\phi^{*})^{2},\quad\dots $$
于是拉式量就只能有这两项了 $\partial_{\mu}\phi^{*}\partial^{\mu}\phi,\phi^{*}\phi$ ，它们的质量维数分别为 $[\partial_{\mu}\phi^{*}\partial^{\mu}\phi]=4,[\phi^{*}\phi]=2$ 所以拉式量为
$$\mathcal{L} = \partial_{\mu}\phi^{*}\partial^{\mu}\phi - m^{2}\phi^{*}\phi $$

## 2.2 旋量场

Dirac 旋量场是自旋 $\frac{1}{2}$ 的，描述的是如 $e,\mu$ 这样的粒子。在几何上，它对应于时空底流形上的一个旋量线丛的截面。旋量场 $\psi(x)$ 是按照洛伦兹群的 $\left( \frac{1}{2},0 \right)\oplus\left( 0, \frac{1}{2} \right)$ 表示变换的，若 $\Lambda$ 是一个洛伦兹变换它的自旋表示矩阵是 $S(\Lambda)$，则场变换规则为
$$\psi(x) \longmapsto \psi'(x') = S(\Lambda)\psi(x) $$
定义 $\bar{\psi} = \psi ^{\dagger}\gamma^{0}$ 则它的变换规则为
$$\bar{\psi}(x) \longmapsto \bar{\psi}'(x') = \bar{\psi}(x)S^{-1}(\Lambda) $$
所以 $\bar{\psi}\Gamma\psi,\partial_{\mu}\bar{\psi}\Gamma\partial^{\mu}\psi, \dots$ 可以构成洛伦兹协变对象。其中的 $\Gamma \in\{ \mathbf{1},\gamma^{\mu},\sigma^{\mu \nu},\gamma^{\mu}\gamma^{5},\gamma^{5} \}$ 它们只是自旋空间的“结构常数”不随洛伦兹变换而改变，这些二次型分别对应了 标量 矢量 二阶对称张量 赝矢量 赝标量

自由理论要求拉氏量在场变量上是二次型。可构造的最低阶洛伦兹标量包括
- 质量项
  $$\bar{\psi}\psi $$
- 动能项
  $$\bar{\psi}\gamma^{\mu}\partial_{\mu}\psi $$
而其它的则不是洛伦兹标量。它们的质量维数分别为 $[\bar{\psi}\psi]=3,[\bar{\psi}\gamma^{\mu}\partial_{\mu}\psi ]=4$ 

最后由于 $\bar{\psi}\gamma^{\mu}\partial_{\mu}\psi$ 是纯虚的，所以为了让拉式量是实的，手动加一个虚数 $i$ 所以拉式量是
$$\mathcal{L} = \bar{\psi}(i\not{\!\partial} - m)\psi $$

## 2.3 规范场

规范场是自旋 $1$ 的无质量的，描述的是 $\gamma$ 这样的粒子。规范场是洛伦兹矢量，同时有规范冗余
$$A^{\mu}(x) \longmapsto A^{'\mu}(x') = D^{\mu \nu}(\Lambda)A_{\nu}(\Lambda x) + \partial^{\mu}\theta(x) $$
引入场强
$$F_{\mu \nu} = \partial_{\mu}A_{\nu} - \partial_{\nu}A_{\mu} $$
则它会在洛伦兹变换和 $U(1)$ 变换下保持不变，所以是构造拉式量的最佳人选。可由 $F_{\mu\nu}$ 构造的最低阶洛伦兹标量是
$$F^{\mu \nu}F_{\mu \nu} , \quad \tilde{F}^{\mu \nu}F_{\mu \nu} ,\quad \tilde{F}^{\mu \nu}\tilde{F}_{\mu \nu} $$
其中 $\tilde{F}^{\mu \nu}=\varepsilon^{\mu \nu \rho \sigma}F_{\rho \sigma}$ 但是问题是 $\tilde{F}^{\mu \nu}F_{\mu \nu}$ 不会产生动力学效果，也就是说在运动方程种无法体现出来它们是否存在，用一个很简单的等式就看出来了：
$$\tilde{F}^{\mu \nu}F_{\mu \nu} = \varepsilon^{\mu \nu \rho \sigma}(\partial_{\mu}A_{\nu})(\partial_{\rho}A_{\sigma}) = 2\partial_{\mu}(\varepsilon^{\mu \nu \rho \sigma}A_{\nu}\partial_{\rho}A_{\sigma}) $$
这是个全导数项，所以必然不会对运动方程产生任何影响。至于第三项，把定义代入不难验证其和第一项是相等的。

在四维时空中
$$[A^{\mu}]=1 \implies [F^{\mu \nu}]=2\implies [F^{\mu \nu}F_{\mu \nu}]=4 $$
所以拉式量可以取为
$$\mathcal{L} = -\frac{1}{4}F^{\mu \nu}F_{\mu \nu} $$
系数 $-\tfrac14$ 是为了得到标准归一化的动能项。我们还能将它显式的写为 $A^{\mu}$ 的形式
$$\mathcal{L} = -\frac{1}{2} A^{\mu}(g_{\mu \nu}\Box-\partial_{\mu}\partial_{\nu})A^{\nu} $$

### *2.3.1 规范冗余

我们知道对于规范场，其运动方程为(可以由欧拉-拉格朗日方程导出)
$$\partial_{\mu}F^{\mu \nu} = 0 $$
这说明了一个问题，就是规范场的四个分量不是相互独立的，它们是受约束的。另一方面，规范变换 $A^{\mu}\to A^{\mu}+\partial^{\mu}\theta$ 说明了某些 $A^{\mu}$ 是描述同一个物理态，这就是所谓了“冗余自由度”。

在讨论时为了统一，要事先约定一个规范选择，一个常用的是 Lorentz 规范
$$\partial_{\mu}A^{\mu}=0 $$
在 Lorentz 规范 $\partial_\mu A^\mu = 0$ 下，仍允许进行满足 $\Box \theta = 0$ 的残余规范变换。这对应于进一步固定剩余的规范自由度，最终将独立物理自由度减少为 2 个（对应光子的两个横极化）。


对于有质量的矢量场 (Proca 场) 则不一样，其拉式量是 $\mathcal{L} = -\frac{1}{4}F^{\mu \nu}F_{\mu \nu} + \frac{1}{2}mA^{\mu}A_{\mu}$ 场的运动方程是
$$\partial_{\mu}F^{\mu \nu} + m^{2}A^{\nu}=0 $$
$$m^{2}\partial_{\mu}A^{\mu}=0 $$
可见它自带“Lorentz 规范”，可是这并不是规范选择，这是动力学上的限制。所以 Proca 场的实际自由度是 3 (对应两个哼向极化态和一个纵向极化态)

# 3. 相互作用理论

## 3.1 路径积分与各泛函

### 3.1.1 高斯型积分

#### 1. 实数上的积分

先看看简单的
$$I = \int_{\mathbb{R}} \exp(-x^{2}) \mathrm{d}x = \sqrt{ \pi } $$
现在升级为高维的，比如二维矢量的积分
$$I = \int_{\mathbb{R}^{2}} \exp(-x^{T}x)\mathrm{d}^{2}x = \pi $$
进一步的
$$I = \int_{\mathbb{R}^{n}} \exp(-x^{T}x)\mathrm{d}^{n}x = \pi^{n/2} $$
$$I = \int_{\mathbb{R}^{n}} \exp(-x^{T}Ax)\mathrm{d}^{n}x=\frac{\pi^{n/2}}{\sqrt{ \det A }} $$
$$I = \int_{\mathbb{R}^{n}} \exp(-x^{T}Ax + J^{T}x)\mathrm{d}^{n}x=\frac{\pi^{n/2}}{\sqrt{ \det A }} e^{ \frac{1}{4} J^{T}A^{-1}J } $$
由此我们可以总结出经验来，高斯型积分就是找二次型 (和一次项) ，它把一个二次型转换为一个数值
$$\mathbb{R}^{2}\times \mathbb{R} \to \mathbb{R} ,\qquad (A,J) \mapsto \frac{\pi^{n/2}}{\sqrt{ \det A }} e^{ \frac{1}{4} J^{T}A^{-1}J } $$
#### 2. c-场上的积分

现在我们将它扩展到无穷维，我们要对场进行积分，场在每个点处都有值所以积分对象当然是无穷维的，但是我们不妨先考虑只是将空间划分为可数份 (此乃不严谨之处时空本身测度非零这样划分改变了测度) ，于是对场的积分可以定义为
$$\int \mathcal{D\phi} \sim \lim_{ n \to \infty } \prod_{i=1}^{n} \int \mathrm{d}\phi(x_{i}) $$
就我个人而言我还是喜欢只写成
$$\int(d\phi) $$
积分的对象成了函数，那么那个二次型或者说内积怎么定义呢？我们都是用一个积分来定义函数的内积，比如说
$$(\phi,\Box\phi) := \int \mathrm{d}^{4}x\, \phi(x)\Box\phi(x) $$
然后问题就是如何定义那个神秘的 $\det A$ 要是用上面的例子，那么我们就是要处理 $\det\Box$ 的意思。实际上它被定义为算符在满足边界条件时的特征值的积 (Nakahara)，而且即使如此问题也不小，因为它往往有发散的风险，处理方法是取个对数将乘积化为倒数求和即 $ζ$ 函数。

#### 3. Grassman 场上的积分

Grassman 数也就比 c-数 多了个反对易就有了很大的不同，简而言之，有奇妙的积分微分性质，所有的函数都是一次的，有共轭
$$\int d \eta = 0 , \quad \int \eta d \eta = 1 ,\quad \int f(\eta) d \eta = \frac{df}{d \eta} ,\quad e^{ \eta } = 1 + \eta $$
$$\forall \eta,\exists \bar{\eta} $$
对于向量的积分是类似的唯一的区别是
$$\int (d \bar{\eta})(d \eta) \exp(\bar{\eta}A\eta) = \det A  $$

### 3.1.2 泛函们

作用量，就像理论力学中一样的，它被定义为
$$S[\phi] = \int \mathrm{d}^{4}x\, \mathcal{L}[\phi] $$
是最小作用量原理的直接描述对象。对于自由实标量场它是
$$S[\phi] = \int \mathrm{d}^{4}x\, \phi(x)\mathcal{O}\phi(x) $$
其中 $\mathcal{O}=-\Box-m^{2}$ 其它的场是类似的结构。

在量子场论中，我们通过引入一个**外源** $J(x)$ 来探测场的动力学。这类似于经典力学中给系统施加一个扰动。
#### 1. 生成泛函（配分函数） $Z[J]$

看名字都知道是从哪里借来的名字，类似的它是整个理论的“原始数据库”。通过路径积分定义为：
$$Z[J] = \int (d\phi) \exp\left( iS[\phi] + i \int \mathrm{d}^4x J(x)\phi(x) \right)$$
对 $J(x)$ 求 $n$ 次泛函导数，并令 $J=0$，就能得到 $n$ 点格林函数 $\langle 0 | T \phi(x_1)\dots\phi(x_n) | 0 \rangle$。
$$\frac{\delta Z}{\delta J(x)} = \int(d\phi) \exp\left( iS[\phi] +i \int \mathrm{d^{4}}yJ(y)\phi(y) \right) \phi(x) $$
$$\left.\frac{\delta Z}{\delta J(x)}\right|_{J=0} = \int (d\phi) \exp(iS[\phi])\phi(x) = \braket{ 0 | \phi(x) | 0 }  $$
$$\langle 0 | T \phi(x_1)\dots\phi(x_n) | 0 \rangle = \left.\frac{\delta Z}{\delta J(x_{1})\dots\delta J(x_{n})}\right|_{J=0} $$
它包含了所有的费曼图，包括那些互不相连的“真空泡”。还有一个有意思的结构，我们可以将不含源的项中的场替换为对源的求导而不对结果产生影响
$$ Z[J] = \int(d\phi) \exp\left( iS\left[ \frac{\delta}{\delta J(x)} \right] \right)\exp\left( i \int \mathrm{d}^{4}xJ(x)\phi(x) \right) $$

例如在 $\phi^{4}$ 理论中，利用上面的结论，将相互作用部分的 $\phi(x)$ 替换为 $\frac{\delta}{\delta J}$ 
$$\begin{align}
Z[J] &  = \int(d\phi) \exp\left( iS_{0}[\phi] + i \int \mathrm{d}^{4}xJ(x)\phi(x) \right)\exp\left( -i \int \mathrm{d}^{4}x \frac{\lambda}{4!}\phi^{4}(x) \right) \\
&= \exp\left( -i \int \mathrm{d}^{4}x \frac{\lambda}{4!}\left( \frac{\delta}{\delta J(x)} \right)^{4} \right)Z_{0}[J] 
\end{align}$$
$$\begin{align}
Z_{0}[J] &= \int(d\phi) \exp\left( iS_{0}[\phi]+i \int \mathrm{d^{4}}xJ(x)\phi(x) \right)  \\
&= \exp\left( -\frac{i}{2} \int \mathrm{d}^{4}x\mathrm{d}^{4}y\,J(x)D_{F}(x-y)J(y) \right) 
\end{align}$$
这里 $Z_{0}[J]$ 化简使用了高斯积分中得到的结论 $(A,J)\mapsto \frac{1}{\sqrt{ \det A }}\exp\left( \frac{1}{4}J^{T}A^{-1}J \right)$ 这里 $J$ 就是 $J$ ，$A$ 就是 $-(\Box+m^{2})$ 它的逆就是 $D_{F}(x-y)$ 也就是说 $(\Box+m^{2},D_{F})=-i\delta^{(4)}(x-y)$ 。无论如何看看第一阶项 (二点格林函数的)
$$-i\lambda \int \mathrm{d}^{4}x_{3}\, \braket{ 0 | T\left\{  \phi(x_{1})\phi(x_{2}) \frac{\phi^{4}(x_{3})}{4!}  \right\} | 0 }  $$
我们有 Wick 定理，可以化时序乘积为场的收缩，它有这样两个收缩方式 (我不想算几何因子，就只写了收缩方式)
$$D_{F}(x_{1}-x_{2})D_{F}(x_{3}-x_{3})D_{F}(x_{3}-x_{3}) $$
$$D_{F}(x_{1}-x_{3})D_{F}(x_{3}-x_{3})D_{F}(x_{3}-x_{2}) $$
可以看出无论如何它会产生像 $D_{F}(x_{3}-x_{3})D_{F}(x_{3}-x_{3})$ 这样的无外腿真空泡结构，和有外腿的真空泡 (第二个)。实际上我还没有对 $Z$ 做归一化处理，他的归一化条件是 $Z[J=0]=1$ 于是我们需要除以这样的常数以归一化，这样就能够消除无外腿的真空泡了，然鹅并不能消除有外腿的真空泡。

为什么要强调这个泡泡呢。实际上它们大多是发散的，所以有必要去规避它们。

#### 2. 连通生成泛函 $W[J]$

由于 $Z[J]$ 包含了不连通的图，而物理上的散射过程通常由连通图描述，我们定义：
$$Z[J] = e^{iW[J]} \implies W[J] = -i \ln Z[J]$$
物理意义：$W[J]$ 的泛函导数只生成 **连通格林函数**。在统计力学中，这对应于自由能。它是我们计算 $S$ 矩阵的直接基础。


类似的通过 $\phi^{4}$ 理论将展示他就没有这样的真空泡了
$$Z[J] = Z_{0}[J] - \frac{i\lambda}{4!} \int \mathrm{d}^{4}x \left( \frac{\delta}{\delta J(x)} \right)^{4}Z_{0}[J] + \mathcal{O}(\lambda^{2}) $$
由 Wick 定理得到
$$\left( \frac{\delta}{\delta J(x)} \right)^{4}Z_{0}[J] = Z_{0}[J](\Phi^{4}(x) + 6D_{F}(0)\Phi^{2}(x) + 3D_{F}^{2}(0)) $$
$$\Phi(x) = \int \mathrm{d^{4}y} D_{F}(x-y)J(y) $$
$$Z[J] = Z_{0}[J](1+A) + \mathcal{O}(\lambda^{2}) $$
取对数 $W = -i\ln Z$ 得到
$$W[J] = W_{0}[J] + \frac{\lambda}{4!} \int \mathrm{d^{4}}x( \Phi^{4}(x) + 6D_{F}(0)\Phi^{2}(x) + 3D_{F}^{2}(0) ) + \mathcal{O}(\lambda^{2}) $$
注意最后一项 $3D_{F}^{2}(0)$ 它本应该生成真空泡的但是我们计算连通格林函数，由于这一项压根不含源，所以求导必然是零
$$\text{带外腿的真空泡} \not\subset G_{c}(x_{1},x_{2}) = \left.\frac{\delta W}{\delta J(x_{1})\delta J(x_{2})}\right|_{J=0} $$


#### 3. 有效作用量 $\Gamma[\phi_{cl}]$

但是 $W[J]$ 仍然不够好，我们希望所有的图都是 **1PI** 图，也就是说随便切掉一条内线不会导致图变为独立的两部分。在这个意义上所有图都是 1PI 的连接罢了，所以它当然更好，值得去追求。我们通过 **勒让德变换** 从 $W[J]$ 转换到 $\Gamma$。 首先定义经典场（即有源 $J$ 时的真空期望值）
$$\phi_{cl}(x) = \frac{\delta W[J]}{\delta J(x)}$$
然后定义有效作用量
$$\Gamma[\phi_{cl}] = W[J] - \int \mathrm{d}^4x J(x) \phi_{cl}(x)$$
于是可以知道
$$\frac{\delta \Gamma[\phi_{cl}]}{\delta \phi_{cl}(x)} = - J(x) $$
可以看出 $\phi_{cl}(x)$ 与 $J(x)$ 是一对共轭量，就像理论力学中的 $q$ 和 $p$ 一样。还能看出来，当我们撤去源 $J(x)$ 时就相当于是真空，所以 $\frac{\delta \Gamma[\phi_{cl}]}{\delta \phi_{cl}(x)} = 0$ 就是真空的判定条件，这包含了所有的量子修正（即**有效势**的极小值）。

我们可以对它进行泰勒展开：
$$\Gamma[\phi_{cl}] = \sum_{n=0}^{\infty} \int \Gamma^{(n)}(x_{1},\dots ,x_{n})\phi_{cl}(x_{1})\dots \phi_{cl}(x_{n}) $$
其中的系数 $\Gamma^{(n)}$ 等下有大用，它是费曼规则中的顶点，如 $\Gamma^{(2)}$ 就是有两条外腿的 1PI (被截断的) 也就是传播子上的 1PI。根据 [[LSZ 归约公式]]，散射矩阵 $S$ 矩阵元正比于截断的、连通的格林函数。而 $\Gamma^{(n)}$ 恰恰就是这些“截断的 1PI 部分”的总和。

$\Gamma[\phi_{cl}]$ 最神奇的地方在于：全理论的所有连通格林函数，都可以通过对 $\Gamma$ 进行“树图级（Tree-level）”的组合得到。

- **全传播子的逆**：
  对 $\Gamma$ 的定义式再求一次导，可以证明：
  $$\int d^4z \frac{\delta^2 \Gamma}{\delta \phi_{cl}(x)\delta \phi_{cl}(z)} \frac{\delta^2 W}{\delta J(z)\delta J(y)} = -\delta^{(4)}(x-y)$$
  这意味着 $\frac{\delta^2 \Gamma}{\delta \phi_{cl}^2}$ 恰好是全传播子 (二点连通格林函数) 的逆算符。在动量空间，若全传播子为 $\Delta(p^2) = \frac{1}{p^2 - m^2 - \Sigma(p^2)}$，那么 $\Gamma^{(2)}$ 就是 $p^2 - m^2 - \Sigma(p^2)$，其中 $\Sigma(p^2)$ 就是 1PI 的自能修正 (也就是截腿的 1PI)，稍后会在一圈修正中讲到。

## 3.2 鬼场

### 3.2.1 路径积分失效

在[[QED#2.3 规范场]]中我们整到了规范场的自由拉氏量，对应的二次型算符是 $\mathcal{O}_{\mu\nu} = g_{\mu\nu}\Box - \partial_\mu\partial_\nu$如果我们想按照 3.1.1 的方法计算高斯积分 $Z_0[J]$，我们需要找到这个算符的**逆**（即传播子）。然而，这个算符是奇异的。

$\mathcal{O}_{\mu\nu}$ 作用在任何纯规范场 $\partial^\nu \alpha(x)$ 上结果都是 $0$（因为 $\Box\partial_\mu - \partial_\mu\Box = 0$）。这意味着它有无数个零特征值，行列式 $\det \mathcal{O} = 0$，逆算符不存在。这是为什么呢？

费曼在提出路径积分的思想时是怎么说的。他说相信在每个时空点插入一个只有孔的屏，那么就等效于没有插入任何东西，但是场应当走所有路径。这里本来是没问题的，但是规范变化有问题，在每个隔板间传播时的规范选择一致吗？不一定的。更危险的，我们可能对规范冗余的量在全空间积分了，这样发散当然是必然的 (Faddeev-Popov)。

 >[!两个数学上的类似例子]-
 >可见[[Faddeev–Popov#引子]]
### 3.2.2 Faddeev-Popov 配方

我们计算配分函数
$$Z = N \int (d\boldsymbol{\Phi}) \exp \{ iS[\boldsymbol{\Phi}] \} $$
立马会遇到和引子中一样的问题，由于规范冗余这个积分是发散的。为此 Faddeev 和 Popov 指出了这一点，和引子中一样他们并不是重新定义了测度 (积分对象) 他们选择重新定义积分：
$$Z = N \int(d\boldsymbol{\Phi}) \exp \{ iS[\boldsymbol{\Phi}] \} \delta(G)\det\left( \frac{\partial G}{\partial \chi} \right) $$
其中的雅可比行列式中的偏导应该理解为泛函微分。

下以 Lorentz 规范为例来说明他们的配方是怎么消除掉规范冗余的。在 Lorentz 规范下
$$G = \partial_{\mu}A^{\mu} $$
$$A^{\mu} \to A^{\mu} + \partial^{\mu}\chi \implies \partial_{\mu}A^{\mu} \to \partial_{\mu}A^{\mu} + \Box\chi $$
于是
$$\det\left( \frac{\partial G}{\partial \chi} \right) = \det\left( \frac{\delta(\partial_{\mu}A^{\mu})}{\delta \chi} \right) = \det(\Box) $$
对 QED 来说，这个行列式是场独立的常数，可以吸收到归一化 N。所以
$$Z = N \int \mathcal{D}A_{\mu}\mathcal{D}\psi \mathcal{D}\bar{\psi} \exp \{ iS[A,\psi,\bar{\psi}] \} \delta(\partial_{\mu}A^{\mu}) $$


### 3.2.3 雅可比行列式指数化

#### 1. 约束变量的高斯积分

我们会遇到这样的情况，如果对于一个粒子其拉式量可以写为这样的，看似有 $q,y$ 两个自由度，但是拉式量中没有 $\dot{y}$ 导致其实 $y$ 是受约束的
$$L = L_{1}(q,\dot{q}) + \frac{1}{2}ay^{2} + b(q)y $$
$$ay + b(q) = 0 $$
不妨叫 $y$ 为约束变量。我们将这个 $y$ 的方程代回到拉式量中得到有效拉式量
$$L_{eff} = L_{1}(q,\dot{q}) - \frac{b^{2}(q)}{2a} $$
现在我们要计算路径积分时会有这样的一个部分
$$\int(dy)\exp\left( i \int dt \left[  \frac{1}{2}ay^{2} + b(q)y \right] \right) = \sqrt{ \frac{2\pi}{a} } \exp\left( \frac{b^{2}}{2a} \right) $$
你看其实除了那个归一化因子，积分结果就是把约束变量的最小值代入高斯积分即可。换言之
$$\int(dq)(dy) \exp\left( i \int dt\ L(q,\dot{q},y) \right) = \int(dq) \sqrt{ \frac{2\pi}{a} } \exp\left( i \int dt\ L(q,\dot{q},y_{min}) \right) $$
值得注意的是，我这里没有把归一化因子 $\sqrt{ \frac{2\pi}{a} }$ 丢到积分外面，这给与了 $a$ 或许与 $q$ 相关的可能性。实际上这正是我们想要处理的东西。


我们可怜的规范场就是这样的家伙，甚至 Proca 场也是的。我们知道 Proca 场的拉式量是
$$\mathcal{L} = -\frac{1}{4}F^{\mu \nu}F_{\mu \nu} + \frac{1}{2} \mu^{2} A^{\mu}A_{\mu} = -\frac{1}{2}F^{0i}F_{0i} - \frac{1}{4}F^{ij}F_{ij} + \frac{1}{2}\mu^{2}A^{0}A_{0} + \frac{1}{2}\mu^{2}A^{i}A_{i} $$
它的时间分量动量是零 $\pi^{0}=\frac{\partial \mathcal{L}}{\partial(\partial_{0}A_{0})}=0$ 所以 $A^{0}$ 是约束变量。对于规范场也是的，通过固定规范我们能再找到一个规范冗余的分量，比如取轴向规范 $A^{3}=0$ 时它就是规范冗余。对于它们我们就能用上面对待约束变量的方法了。对于规范场真正的独立变量是 $\{ A^{i} , F^{0i} \},i=1,2$

#### 2. $\det\Delta$ 指数化

现在我们必须要处理这么一个东西了
$$\det\Delta,\quad \Delta = \frac{\delta G}{\delta \chi} $$
我们取规范为
$$G(\boldsymbol{\Phi}) = \partial_{\mu}A^{\mu} - f(x) $$
这样
$$A^{\mu} \to A^{\mu} + \partial_{\mu}\delta \chi $$
$$\delta G = \delta(\partial_{\mu}A^{\mu}) = \Box\chi $$
也就是说新加的这个任意函数 $f(x)$ 对雅可比行列式没有任何影响。

这个行列式与场无关也就是说它在积分中是一个常数，哪怕新增了函数 $f(x)$ 。在 3.1.1 中我们知道，一个行列式可以写为 Grassman 场的高斯型积分，这将方便我们得到费曼规则 (也是目的之一)，这个场就是所谓的 **鬼场**。
$$\det\left( \frac{\delta G}{\delta \chi} \right) = \int (\mathrm{d}\eta)(\mathrm{d}\bar{\eta}) e^{ iS_{FP} },\quad S_{FP} = \int \mathrm{d}^{4}x \, \bar{\eta}\Box\eta = -\int \mathrm{d^{4}}x \, (\partial_{\mu}\bar{\eta})(\partial^{\mu}\eta) $$
于是按照配方，配分函数可以写为
$$Z = N \int (d\boldsymbol{\Phi}) e^{ iS }\delta(\partial_{\mu}A^{\mu}-f) $$
考虑到配分函数和函数 $f(x)$ 无关，所以可进一步的写为
$$Z = N\int (d\boldsymbol{\Phi})(df) e^{ iS }\delta(\partial_{\mu}A^{\mu}-f)F[f] = N \int (d\boldsymbol{\Phi}) e^{ iS } F[\partial_{\mu}A^{\mu}] $$
为了得到费曼规则，选取泛函 $F$ 为二次型
$$F[f] = \exp \left\{  -\frac{i}{2\xi} \int d^{4}x \, f^{2} \right\} $$
这样我们就能得到配分函数
$$Z = N \int (d\boldsymbol{\Phi}) e^{ iS_{eff} } ,\quad S_{eff} = \int d^{4}x \, \mathcal{L}_{eff} $$
$$\begin{align}
\mathcal{L}_{eff} &  = \mathcal{L} + \mathcal{L}_{鬼} = -\frac{1}{4}(\partial_{\mu}A_{\nu}-\partial_{\nu}A_{\mu})^{2} + \bar{\psi}(i\gamma^{\mu}\partial_{\mu}-m-e\gamma^{\mu}A_{\mu})\psi - \frac{1}{2\xi} (\partial_{\mu}A^{\mu})^{2}  \\& = \frac{1}{2} A^{\mu}\left[  g_{\mu \nu}\Box - \left( 1-\frac{1}{\xi} \right)\partial_{\mu}\partial_{\nu}  \right]A^{\nu} + \bar{\psi}(i\not{\!\partial}-e\not{\!\!A}-m)\psi
\end{align}$$
这就是我们在某些地方会见到的“规范选择”，他们是天降了这么个 $\xi$ ，这这套方案中我们看到它是出于我们对鬼场的选择、得到费曼规则的目的构造的。从拉式量我们容易读出光子传播子
$$\tilde{D}^{\mu \nu}(k) = \frac{i}{k^{2}+i\varepsilon} \left[  -g^{\mu \nu} + \frac{k^{\mu}k^{\nu}}{k^{2}}  \right] - \frac{i\xi}{k^{2}+i\varepsilon} \frac{k^{\mu}k^{\nu}}{k^{2}} $$
这个传播子就没有发散问题了

### 3.2.4 QED 有效拉式量

经过 Faddeev-Popov 手续，我们最终得到的、用于计算费曼图的完整 QED 拉氏量（采用 Feynman 规范/权重规范）为：

$$\mathcal{L}_{eff} = \mathcal{L}_{QED} + \mathcal{L}_{gf} + \mathcal{L}_{ghost}$$

其中：
- **物理项 (QED)**: $$\mathcal{L}_{QED} = -\frac{1}{4}F_{\mu\nu}F^{\mu\nu} + \bar{\psi}(i\not{\!\!D}-m)\psi$$
- **规范固定项 (Gauge Fixing)**: $$\mathcal{L}_{gf} = -\frac{1}{2\xi}(\partial_\mu A^\mu)^2$$
- **鬼场项 (Ghost)**: $$\mathcal{L}_{ghost} = \bar{\eta}(-\Box)\eta$$
全部代入展开为场的二次型与相互作用项，我们得到 $$\begin{align} \mathcal{L}_{eff} = & \frac{1}{2} A^{\mu}\left[ g_{\mu \nu}\Box - \left( 1-\frac{1}{\xi} \right)\partial_{\mu}\partial_{\nu} \right]A^{\nu} + \bar{\psi}(i\not{\partial}-m)\psi  - e\bar{\psi}\gamma^\mu A_\mu \psi  + \bar{\eta}(-\Box)\eta  \end{align}$$
## 3.3 费曼规则

#### 1. 传播子

传播子就是二次型的逆，所以
- 光子传播子
  $$\tilde{D}^{\mu \nu}(k) = \frac{i}{k^{2}+i\varepsilon} \left[  -g^{\mu \nu} + \frac{k^{\mu}k^{\nu}}{k^{2}}  \right] - \frac{i\xi}{k^{2}+i\varepsilon} \frac{k^{\mu}k^{\nu}}{k^{2}} $$
- 电子传播子
  $$\tilde{D}(p) = i  \frac{\not{\!p}+m}{p^{2}-m^{2}+i\varepsilon} $$
- 鬼场传播子
  $$\tilde{D}(k) = \frac{i}{k^{2}-m^{2}+i\varepsilon} $$

#### 2. 顶点

顶点就是相互作用项的系数，所以
- 光子-电子作用顶点
  $$-ie\gamma^{\mu} $$
#### 3. 外线

外线因子本质是满足自由解的场，所以由 Dirac 方程可以直接导出费米子的外线，由 Maxswell 方程可以直接导出光子的外线，得注意规范问题

|     |       入射       |       出射       |
| :-: | :------------: | :------------: |
| 电子  |    $u(p,s)$    | $\bar{u}(p,s)$ |
| 反电子 | $\bar{v}(p,s)$ |    $v(p,s)$    |

|               入射               |                 出射                 |
| :----------------------------: | :--------------------------------: |
| $\varepsilon_{\mu}(k,\lambda)$ | $\varepsilon_{\mu}^{*}(k,\lambda)$ |

#### 4. 其它

- **动量守恒**：在每一个顶点，动量像电流一样守恒。
- **费米子流向**：沿着费米子箭头的反方向写矩阵。即：写振幅 $\mathcal{M}$ 时，要从末态 $\bar{u}$ 开始，逆着箭头写到初态 $u$。
- **闭环积分**：对于每个无法由守恒律确定的动量 $l$，补上 $\int \frac{d^4l}{(2\pi)^4}$。
- **统计因子与负号**：
    - 每个费米子圈贡献一个 $(-1)$（源自 Grassman 积分）。
    - 相同粒子交换贡献一个 $(-1)$（源自泡利不相容原理）。

### *实例演示

考虑一个康普顿散射 $e^{-}(p) + \gamma(k) \to e^{-}(p') + \gamma(k')$ 有两种可能的过程 (树图阶)，入射电子接收一个光子传播然后射出一个光子最后出射，入射电子射出一个光子传播然后接收一个光子最后出射，它们的散射因子分别为
$$i\mathcal{M}_1 = \bar{u}(p') [ \underbrace{(-ie\gamma^\nu)\varepsilon^*_\nu(k')}_{\text{出射顶点}} \underbrace{\frac{i(\not{p}+\not{k}+m)}{(p+k)^2-m^2}}_{\text{中间电子传播子}} \underbrace{(-ie\gamma^\mu)\varepsilon_\mu(k)}_{\text{入射顶点}} ] u(p)$$
$$i\mathcal{M}_2 = \bar{u}(p') [ \underbrace{(-ie\gamma^\mu)\varepsilon_\mu(k)}_{\text{入射顶点}} \underbrace{\frac{i(\not{p}-\not{k}'+m)}{(p-k')^2-m^2}}_{\text{中间电子传播子}} \underbrace{(-ie\gamma^\nu)\varepsilon^*_\nu(k')}_{\text{出射顶点}} ] u(p)$$

## 3.4 重整化与修正

目前为止我们使用费曼规则也只是导出树图阶的计算，注意到那些真空泡，它们携带积分
$$\int \frac{\mathrm{d}^{4}k}{k^{m}} $$
而往往它们是发散的。在QED中这样的问题有三大常见的情况

1. 电子自能 $\Sigma(p)$
2. 真空极化 $\Pi^{\mu \nu}(k)$
3. 顶点修正 $\Lambda^{\mu}(p,p')$

### 3.4.1 费曼技巧

费曼的技巧是进行一个含参变量的积分来代替分式
$$\frac{1}{AB} = \int dxdy \, \delta(x+y-1) \frac{1}{xA+yB} $$
对于更多的变量是类似的
$$\frac{1}{A\dots C} = \int dx\dots dz \delta(x+\dots+z-1) \frac{1}{xA + \dots + zC} $$

### 3.4.2 正规化

所谓正规化就是说，我们原本的圈积分是对全动量空间进行的积分，现在我们引入一些参数使得它们被有限的参数截断，从而表现出发散结构也就是积分是如何随着参数而发散的。

#### 1. 截断正规化

就是为动量大小设定一个上限 $\Lambda$ 比如对于下面的积分
$$\int \frac{\mathrm{d}^{4}k}{k^{4}} = \int \mathrm{d}\Omega \int_{0}^{\Lambda} \frac{k^{3}\mathrm{d}k}{k^{4}} =\mathcal{O}(\ln \Lambda) $$
#### 2. PV 正规化

就是设置一个大质量的传播子场，
$$\frac{i}{k^{2}-m^{2}} \to \frac{i}{k^{2}-m^{2}} - \frac{i}{k^{2}-M^{2}} = \frac{i(m^{2}-M^{2})}{(k^{2}-m^{2})(k^{2}-M^{2})} $$
这样就将传播子的分母次数提高了，积分结果就能收敛了
$$\int \mathrm{d}^{4}k\left[  \frac{i}{k^{2}-m^{2}} - \frac{i}{k^{2}-M^{2}} \right] = \mathcal{O}\left( \ln \frac{M^{2}}{m^{2}} \right) $$
更多可见 [[泡利-维拉斯正规化]]

#### 3. 维数正规化

就是假定时空的维数是连续的 $d$ 最后让他取到 $d\to 4$ 的极限即可看出发散度
$$\int \frac{\mathrm{d}^d k}{(2\pi)^d} \frac{1}{(k^2 + \Delta)^n} = \frac{1}{(4\pi)^{d/2}} \frac{\Gamma(n - d/2)}{\Gamma(n)} \Delta^{d/2 - n}$$
当 $d \to 4$ 时，由于欧拉 $\Gamma$ 函数在 0 和负整数处有极点，发散结构会显式地表现为
$$\Gamma\left( \frac{\epsilon}{2} \right) = \frac{2}{\epsilon} - \gamma_E + \mathcal{O}(\epsilon)$$
这里 $\frac{2}{\epsilon}$ 完美地承载了原本的对数发散。**它是最常用的手法**，更多可见 [[维数正规化]]

### 3.4.2 重整化

正规化给出来发散的形式，而重整化负责解释它们并修正为符合物理的。

#### 1. 在壳重整化

这是最符合物理直觉的方案。它的核心思想是：拉氏量中裸参数是不可观测的，物理参数必须在实验测量点（通常是质壳上）定义。[[在壳重整化]]

##### a. Källén-Lehmann 谱表示与极点的含义

我们不能简单地假设相互作用区域的参数与自由区域一致。事实上，相互作用会让单粒子态“穿上衣服”。为此考虑往两点格林函数中插入完备基
$$\begin{align}
\braket{ 0 | \phi(x)\phi(y) | 0 } &= \sum_{n} \braket{ 0 | \phi(x) | n } \braket{ n | \phi(y)| 0 }  \\
&= \sum_{n} e^{ -ip_{n}\cdot(x-y) } | \braket{ n | \phi(0) | 0 }  |^{2} \\
&= \underbrace{|\braket{ 0 |\phi(0)| 0 } |^{2}}_{真空项} + \underbrace{\int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}2\omega_{\mathbf{p}}}e^{ -ip\cdot(x-y) }|\braket{ p |\phi(0)| 0 } |^{2}}_{单粒子} \\
&\quad + \underbrace{\sum_{n}'e^{ -ip_{n}\cdot(x-y) } | \braket{ n | \phi(0) | 0 }  |^{2}}_{多粒子态} \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}2\omega_{\mathbf{p}}}e^{ -ip\cdot(x-y) }|\braket{ p |\phi(0)| 0 } |^{2} + \sum_{n}'e^{ -ip_{n}\cdot(x-y) } | \braket{ n | \phi(0) | 0 }  |^{2} \\
&= \Delta_{+}(x-y;m^{2}) + \int_{0}^{\infty} da^{2}\ \sigma(a^{2})\Delta_{+}(x-y;a^{2})
\end{align} $$
我们插入完备基后发现，场 $\phi(x)$ 不仅能从真空激发出质量为 $m$ 的单粒子态 $\ket{p}$，还能激发出质量从 $m_{threshold}$（通常是 $2m$ 或 $3m$）开始的连续多粒子态。我们将这种结构反映在复动量平面上，全传播子 $\Delta(p^2)$ 就呈现出以下谱结构：
$$\Delta(p^{2}) = \frac{iZ}{p^{2}-m^{2}+i\varepsilon} + \int_{m_{threshold}}^{\infty} da^{2} \sigma(a^{2}) \frac{i}{p^{2}-a^{2}+i\varepsilon}$$
- **极点结构**：第一项即我们所谓的“极点结构”。它明示了在能壳 $p^2=m^2$ 处，依然存在一个清晰的单粒子态。这里的 $m$ 就是**物理质量**。
- **波函数重整化**：系数 $Z$（谱权重）必然满足 $0 \le Z < 1$。这意味着物理场 $\phi$ 产生单粒子态的概率被相互作用“稀释”了。为了让物理粒子的产生算符归一化，我们必须重新定义场 $\phi_r = Z^{-1/2} \phi$ 这就是**波函数重整化**的物理来源。

##### b. 物理条件

虽然谱表示在理论上很完美，但在计算一圈修正时，我们需要一套更高效的语言。利用 3.1.2 中定义的有效作用量 $\Gamma[\phi_{cl}]$，我们可以将上述极点结构翻译为具体的物理约束。

在微扰论中，全传播子 $\Delta(p^2)$ 可以写成级数求和的形式 (Dyson 方程)
$$\Delta(p^2) = \Delta_0 + \Delta_0 (-i\Sigma) \Delta_0 + \Delta_0 (-i\Sigma) \Delta_0 (-i\Sigma) \Delta_0 + \dots = \frac{i}{p^2 - m^2 - \Sigma(p^2)}$$
这里 $-i\Sigma(p^2)$ 代表所有 1PI 二点图的总和。根据 3.1.2，$\Gamma^{(2)}$ 是全传播子的逆
$$\Gamma^{(2)}(p^2) \equiv i[\Delta(p^2)]^{-1} = p^2 - m^2 - \Sigma(p^2)$$
所以在壳重整化要求 $\Gamma$ 必须在物理点满足：

1. **极点位置（对应质量修正）**：
   要求全传播子的极点恰好位于实验测得的物理质量 $m$ 处
   $$\Gamma^{(2)}(p^2) \Big|_{p^2=m^2} = 0$$
   这等价于要求自能修正 $\Sigma(m^2)$ 被反项精确抵消。
2. **残数归一（对应波函数修正）**
   要求极点处的行为与自由粒子完全一致（即留数为 1），这意味着 $\Gamma^{(2)}$ 在极点处的斜率必须被修正回 1
   $$\frac{\partial \Gamma^{(2)}(p^2)}{\partial p^2} \Big|_{p^2=m^2} = 1$$
   这决定了抵消项 $\delta_Z$ 的值。

##### c. 确定抵消项

以包含量子修正的标量场为例，我们将自能 $\Sigma(p^2)$ 分解为两部分
$$\Sigma(p^2) = \Sigma_{\text{loop}}(p^2) + \Sigma_{\text{ct}}(p^2)$$
其中 $\Sigma_{\text{loop}}$ 是通过费曼规则算出的发散积分，而 $\Sigma_{\text{ct}}$ 是来自反项拉氏量的贡献。对于二点函数，反项贡献具有固定的多项式形式
$$\Sigma_{\text{ct}}(p^2) = p^2 \delta_Z - \delta_m$$
现在，我们将 b 中的两个物理条件“翻译”为锁定这两个常数的方程：

1. 锁定质量反项 $\delta_m$
    由 $\Gamma^{(2)}(m^2) = m^2 - m^2 - \Sigma(m^2) = 0$ 导出：
    
    $$\delta_m = m^2 \delta_Z - \Sigma_{\text{loop}}(m^2)$$
    
    这说明 $\delta_m$ 的任务是把被量子圈图“推开”的极点，强行拽回到物理质量 $m^2$ 处。
1. 锁定场强反项 $\delta_Z$
    由 $\left. \frac{\partial \Gamma^{(2)}}{\partial p^2} \right|_{m^2} = 1 - \left. \frac{\partial \Sigma}{\partial p^2} \right|_{m^2} = 1$ 导出：
    
    $$\delta_Z = \left. \frac{\partial \Sigma_{\text{loop}}}{\partial p^2} \right|_{p^2=m^2}$$
    这说明 $\delta_Z$ 补偿了由于多粒子态连续谱的出现而导致的单粒子占比的缩减。

#### 2. BPHZ 重整化手续

在壳重整化很直观，但是它要求对过程很熟悉，就像牛顿力学中的受力分析一样。而 BPHZ 重整化就像拉格朗日力学一样一切都是流程化的。BPHZ 提供了一套严谨的递归方案，证明对于可重整化理论，我们总能通过有限个反项抵消掉所有阶数的紫外发散。

##### a. 表观发散度

对于每个图我们计算它的表观发散度
$$D = 4L - 2I_{B} - I_{F} $$
$D > 0$：多项式发散，$D = 0$：对数发散，$D < 0$：表面收敛。$D<0$ 不能断言这个图是收敛的，要仔细看子图中有没有发散的，必需确保所有子图都能收敛才算完全。

##### b. 在外动量 p=0 处泰勒展开

对**无零质量粒子**的理论，费曼图在外动量 $p_{i}=0$ 附近是解析函数。因此可以对图做泰勒展开，以及要注意洛伦兹不变性。

比如在 $\phi^{4}$ 理论中一个 sunset 图可以展开为
$$\text{Sunset Diagram} = A + B p^{2} + \dots $$
##### c. 算法流程

首先我们在微扰论中计算到所有阶，直到遇到一张 $D≥0$ 的 1PI 图。然后向 $\mathcal{L}$ 中添加抵消项 $\mathcal{L}_{CT}$ ，以抵消该图在零动量处泰勒展开中阶数 $≤D$ 的项。最后回到步骤 1，用新的拉格朗日量 $\mathcal{L}'=\mathcal{L}+\mathcal{L}_{\text{CT}}​$ 继续计算。

在理论中**不含无质量场**时，由算法得到的格林函数在 $Λ→∞$ 时与截断 $Λ$ 无关，且在微扰论所有阶都成立，与正规化方案无关。该算法解决了重整化问题，因为抵消项被正确构造。在微扰论的每一阶，只有来自**表面发散图**的新发散会带来新问题，其他发散都会被之前的抵消项自动处理。

在实际使用中，我们关心顶点和外线，可以写为
$$D = -B_{E} - \frac{3}{2}F_{E} + \sum_{顶点} n_{i}\left( b_{i}+\frac{3}{2}f_{i}+d_{i}-4 \right) + 4 $$
$$\delta_{i} := b_{i}+\frac{3}{2}f_{i}+d_{i}-4 $$
规则是
$$\begin{gather}
D = 抵消项中的微商次数 \\
B_{E} = 抵消项中的玻色子场个数 \\
F_{E} = 抵消项中的费米子场个数
\end{gather}$$
##### *φ4例

$$\mathcal{L} = \frac{1}{2}(\partial_{\mu}\phi)(\partial^{\mu}\phi) - \frac{1}{2}\mu^{2}\phi^{2} - \frac{\lambda}{4!}\phi^{4} + \mathcal{L}_{CT}$$
只有一种顶点，其 $b_{i}=4,f_{i}=0,d_{i}=0,\delta_{i}=0$ 所以无论加多少顶点，表观发散度都不会变 $D = -B_{E}+4$ 当 $B_{E}> 4$ 时图一定收敛，当 $B_{E}\leq 4$ 时才考虑，由于理论宇称为偶所以奇数个的外玻色子线不存在，于是只考虑 $B_{E}=0,2,4$ 的情况

$B_{E}=0,D=4$ 时，为真空-真空散射图，不考虑。
$B_{E}=2,D=2$ 时，为两点函数。按照规则抵消项有两个微商和两个玻色子场，也就是
$$\mathcal{L}_{\text{CT,1}}=A\phi^{2} + B(\partial_{\mu}\phi)^{2} $$
$B_{E}=4,D=0$ 时，为四点函数。按照规则抵消项有四个玻色子场，即
$$\mathcal{L}_{\text{CT,2}} = C\phi^{4} $$

可以看出其实它们就是修正了 $\phi^{4}$ 理论中的质量、场函数、耦合常数。

#### 3. 应用到QED

标量场的 BPHZ 告诉我们，只要 $\delta_i \leq 0$，理论就是可重整化的。现在我们应用这一套流程到 QED
$$\mathcal{L}_{QED} = \bar{\psi}(i\not{D}-m)\psi - \frac{1}{4}F_{\mu\nu}F^{\mu\nu} + \mathcal{L}_{CT}$$
从公式 $D = 4 - B_E - \frac{3}{2}F_E$，我们可以列出 QED 中所有可能的“病灶”：

1. 电子自能 ($B_E=0, F_E=2$) 虽然 $D=1$ 预示着线性发散，但由于洛伦兹不变性，发散项必须是 $\not{\!p}$ 或 $m$。这意味着实际只有对数发散。

2. 光子自能/真空极化 ($B_E=2, F_E=0$) $D=2$ 预示着平方发散（即光子可能获得质量）。

3. QED 顶点 ($B_E=1, F_E=2$)：$D = 0$。刚好对数发散。

用BPHZ流程我们可以整理到

| $D$ |                                                                                                   抵消项                                                                                                    |                                                   物理意义                                                    |
| :-: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------: |
|  0  |                                                                                                    \                                                                                                     |                                                  只改变真空能                                                   |
|  1  |                                                                                                    \                                                                                                     |                                                     无                                                     |
|  2  |                                                                                            $AA^{\mu}A_{\mu}$                                                                                             |                                                   光子质量项                                                   |
|  3  |                                                                                            $B\bar{\psi}\psi$                                                                                             |                                                   电子质量项                                                   |
|  4  | $\left\{\begin{gather}<br>C \bar{\psi}\not{\!\partial}\psi \\<br>D\bar{\psi}e\not{\!\!A}\psi \\<br>E(F^{\mu \nu})^{2} \\<br>F(\partial_{\mu}A^{\mu})^{2} \\<br>G(A^{\mu}A_{\mu})<br>\end{gather}\right.$ | $$\begin{gather}<br>电子波函数重整 \\<br>耦合项 \\<br>光子波函数重整 \\<br>规范项 \xi 重整 \\<br>类比 \phi^{4}<br>\end{gather} $$ |
下面我们用对称性来删掉不符合 庞加莱对称性×C,P对称×规范对称 的抵消项。

- QED 是宇称守恒的。这意味着抵消项不能包含类似 $\bar{\psi}\gamma^5\psi$（伪标量）或 $\bar{\psi}\gamma^5\gamma^\mu\psi$（轴矢量）的项。
- 关于 $D=1$ 的电子自能，虽然数学上允许线性发散，但洛伦兹项只有 $\not{p}$ 和 $m$。这意味着 $D=1$ 的项其实表现得像 $D=0$ 的对数发散，因为发散的系数必须具有矢量结构来匹配 $\gamma^\mu$。
- C 对称要求包含奇数个外部光子线的费米子圈图贡献为零。

关于规范对称性的，其实用 Ward 恒等式说明更好，这里提前引用。

- $D=2$ 的 $A^{\mu}A_{\mu}$ 项和 $D=4$ 的 $(A^{\mu}A_{\mu})^{2}$ 项预示着光子可能获得质量。但 Ward 恒等式要求光子自能满足 $k_\mu \Pi^{\mu\nu}(k) = 0$。所以 $A=G=0$。
- Ward 恒等式强制要求 **$Z_1 = Z_2$**。这意味着这两个抵消项不是独立的，它们的发散部分必须精确抵消。这保证了电荷的普适性。
- 由于规范固定项 $(\partial A)^2$ 本身就是我们为了定义传播子手动加入的非奇异项，Ward 恒等式保证了**规范参数 $\xi$ 不需要重整化**（或者说它的重整化是被动的），所以可以直接取 $F = 0$。

总之，可能的抵消项为
$$\mathcal{L}_{\text{CT}} = B\bar{\psi}\psi + C\bar{\psi}\not{\!\partial}\psi + Die\bar{\psi}\not{\!\!A}\psi + E(F^{\mu \nu})^{2} $$
分别修正了 电子质量、电子波函数、耦合强度(电荷)、光子波函数，其中电荷与光子波函数的参数是关联的。将抵消项改写为场重整化与顶点重整化：
$$\begin{align}
\mathcal{L} &= -\frac{1}{4}(F^{\mu \nu}F_{\mu \nu})[1+E] + \bar{\psi}\not{\!\partial}\psi[1+C] + \bar{\psi}\psi[m+B] + ie\bar{\psi}\gamma^{\mu}A_{\mu}\psi[1+C]  \\
&= -\frac{1}{4}Z_{3}(F^{\mu \nu}F_{\mu \nu}) + Z_{2}\bar{\psi}\not{\!\partial}\psi + Z_{m}Z_{2}m\bar{\psi}\psi + Z_{1}ie\bar{\psi}\gamma^{\mu}A_{\mu}\psi
\end{align}$$
其中 $Z_{3}=Z_{1}$ 

### 3.4.3 Ward 恒等式

它其实是要研究这么个问题：**规范不变性如何限制抵消项**。

#### 1. 泛函视角下推导

在 3.1.2 中我们定义了有效作用量 $\Gamma[\bar{\psi},\psi,A^{\mu}]$ 。记场的集合为 $\Phi=(\bar{\psi},\psi,A^{\mu})$ 规范变换记作
$$\Phi\to \Phi' = \Phi + A(\Phi)\delta \chi $$
作用量在规范变换下的行为
$$S[\Phi] = S_{GI}[\Phi] + S_{GF}[\Phi] = S_{GI} - \frac{1}{2\xi}\int \mathrm{d}^{4}x\ (\partial_{\mu}A^{\mu})^{2} $$
$$\begin{align}
S[\Phi] \to S'[\Phi'] &= S[\Phi] + \delta S[\Phi] = S[\Phi] - \frac{1}{\xi}\int \mathrm{d}^{4}x\ (\partial_{\mu}A^{\mu})\Box\delta\chi \\
& \equiv S[\Phi] + \int \mathrm{d}^{4}x\ B[\Phi]\delta \chi
\end{align} $$
这里的 $A,B$ 都至多是 $\Phi$ 的一阶。规范变换不会改变积分测度因为它只是给 $A^{\mu}$ 加上一个常数，而 $\bar{\psi},\psi$ 进行一个关于 $\delta \chi$ 的旋转所以 $d\Phi \to d\Phi'=d\Phi$ 。下面就能开始计算泛函的变换了
$$\begin{align}
e^{ iW[J] } &  = N\int(d\Phi) e^{ iS[\Phi]+i \int J\Phi } \to N \int(d\Phi') e^{ iS'[\Phi']+i \int J\Phi' } \\
&= N\int(d\Phi') \exp\left(  i\left\{  S[\Phi] + \int \mathrm{d}^{4}xB[\Phi]\delta \chi + \int \mathrm{d}^{4}xJ(x)(\Phi+A[\Phi]\delta \chi) \right\}  \right) \\
&= e^{ iW[J] } + N\int(d\Phi) e^{ iS[\Phi]+i \int J\Phi } \left[  i \int \mathrm{d}^{4}y (B[\Phi] + J(y)A[\Phi])\delta \chi(y)  \right] \\
&= e^{ iW[J] }
\end{align} $$
记得 $A,B$ 是关于 $\Phi$ 线性的，所以可以用平均值代替 $\bar{\Phi}$ (在3.1.2中称为 $\phi_{cl}$) 第二部分为
$$ N\int(d\Phi) e^{ iS[\Phi]+i \int J\Phi } \left[  i \int \mathrm{d}^{4}y (B[\bar{\Phi}] + J(y)A[\bar{\Phi}])\delta \chi(y)  \right] = 0 $$
而 $J(x) = -\frac{\delta \Gamma}{\delta \bar{\Phi}(x)}$ 所以
$$\delta \Gamma[\bar{\Phi}] = \int \mathrm{d^{4}}x \frac{\delta \Gamma}{\delta \bar{\Phi}} \delta \Phi = \int \mathrm{d}^{4}x \frac{\delta \Gamma}{\delta \bar{\Phi}} A[\bar{\Phi}]\delta \chi = \int \mathrm{d}^{4}x B[\bar{\Phi}]\delta \chi $$
于是可见
$$\delta \Gamma[\bar{\Phi}] = \delta S[\bar{\Phi}] = \delta S_{GF}[\bar{\Phi}] $$
在关于场至多为线性的规范变换下，**有效作用量的变化等于经典作用量的变化**，这就是 Wrad 恒等式。

#### 2. QED中体现

好的，现在来看看QED
$$S = \int \mathrm{d}^{4}x\left\{   -\frac{1}{4}(F^{\mu \nu})^{2} + \bar{\psi}(i\not{\!\partial}-m-e\not{\!\!A})\psi - \frac{1}{2\xi}(\partial_{\mu}A^{\mu})^{2}  \right\} $$
$$\delta \begin{pmatrix}
\psi(x) \\
\bar{\psi}(x) \\
A^{\mu}(x)
\end{pmatrix} = \begin{pmatrix}
-ie\delta \chi(x)\psi(x) \\
ie\delta \chi(x)\bar{\psi}(x) \\
\partial^{\mu}\delta \chi(x)
\end{pmatrix} $$
于是可以知道
$$\begin{align}
\int \mathrm{d}^{4}x\left\{  -ie \frac{\delta \Gamma}{\delta \psi(x)}\psi(x) + ie \frac{\delta \Gamma}{\delta \bar{\psi}(x)}\bar{\psi}(x) - \partial^{\mu} \frac{\delta \Gamma}{\delta A^{\mu}(x)}  \right\}\delta \chi(x) = - \int \mathrm{d}^{4}x \left\{  \frac{1}{\xi}\Box \partial_{\mu}A^{\mu}  \right\}\delta \chi(x)
\end{align} $$
由规范选择的任意性知
$$\boxed{-ie \frac{\delta \Gamma}{\delta \psi(x)}\psi(x) + ie \frac{\delta \Gamma}{\delta \bar{\psi}(x)}\bar{\psi}(x) - \partial^{\mu} \frac{\delta \Gamma}{\delta A^{\mu}(x)} =  \frac{1}{\xi}\Box \partial_{\mu}A^{\mu}}$$
对这个方程求导就能得到很多有意思的东西了，在此前先回忆一下，我们可以对 $\Gamma$ 进行泰勒展开，展开系数就是顶点因子，看看吧。先对 $A_{\nu}$ 求导再令其它场归零：
$$-\partial^{\mu}_{x} \frac{\delta^{2}\Gamma}{\delta A^{\mu}(x)\delta A_{\nu}(y)} = \frac{1}{\xi}\Box\partial^{\nu}\delta^{(4)}(x-y) $$
$$-\partial^{\mu}_{x} \Gamma^{(2)}_{\mu \nu}(x,y) = \frac{1}{\xi}\Box\partial^{\nu}\delta^{(4)}(x-y) $$
所以傅里叶变换到动量空间即得
$$k_{\mu}\Gamma^{(2)\mu \nu}(k) = \frac{1}{\xi}k^{\nu}k^{2} $$
由此 $\Gamma^{(2)\mu \nu}(k)$ ，也就是光子传播子，由洛伦兹结构其必然为
$$\Gamma^{(2)\mu \nu}(k) = A(k^{2})g^{\mu \nu} + B(k^{2})k^{\mu}k^{\nu} $$
$$A(k^{2}) = k^{2}\left( \frac{1}{\xi} - B(k^{2})k^{2} \right) := k^{2}\Pi(k^{2}) $$
$$\Gamma^{(2)\mu \nu}(k) = \Pi(k^{2})(g^{\mu \nu}-k^{\mu}k^{\nu}) + \frac{1}{\xi}k^{\mu}k^{\nu} $$
看这就是完全光子传播子。下面再对 $\psi,\bar{\psi}$ 求导再让其它场归零：
$$-ie\left(  \delta(x-y) \frac{\delta^{2}\Gamma}{\delta \bar{\psi}(z)\psi(x)} - \delta(x-z) \frac{\delta^{2}\Gamma}{\delta \bar{\psi}(x)\delta \psi(y)}  \right) + \partial^{\mu}_{x} \frac{\delta^{3}\Gamma}{\delta \bar{\psi}(z)\delta \psi(y)\delta A^{\mu}(x)} = 0 $$
$$\partial^{\mu}_{x}\Gamma^{(3)}_{\mu}(x,y,z) = ie[ \delta(x-y)\Gamma^{(2)}(x,z) - \delta(x-z) \Gamma^{(2)}(y,x) ] $$
傅里叶变换
$$\Gamma^{(2)}(x,y) = \int \frac{\mathrm{d}^{4}p}{(2\pi)^{4}} e^{ -ip\cdot(x-y) } \Gamma^{(2)}(p) $$
$$\Gamma^{(3)}_{\mu}(x,y,z) = \int \frac{\mathrm{d}^{4}p\mathrm{d}^{4}k}{(2\pi)^{8}} e^{ -i(p+k)\cdot y + ip\cdot z + ik\cdot x } \Gamma^{(2)}_{\mu}(p+k,k) $$
于是得到
$$k^{\mu}\Gamma^{(3)}_{\mu}(p+k,p) = e[ \Gamma^{(2)}(p+k) - \Gamma^{(2)}(p) ] $$
$$\Gamma^{(3)}_{\mu}(p,p) = e\lim_{ k \to 0 } \frac{\Gamma^{(2)}(p+k)-\Gamma^{(2)}(p)}{k^{\mu}} = e \frac{\partial \Gamma^{(2)}(p)}{\partial p^{\mu}}  $$

#### 3. 对QED重整化的限制

与抵消项的形式不同，还有一种写法是从 Källén-Lehmann 谱表示中来，也就是在相互作用中单粒子的影响被稀释，定义裸场和物理场间有
$$e_{0}\bar{\psi}_{0}\gamma_{\mu}A_{0}^{\mu}\psi_{0} = Z_{1} \bar{\psi}\gamma^{\mu}A_{\mu}\psi ,\quad \psi_{0} = \sqrt{ Z_{2} }\psi,\quad A^{\mu}_{0} = \sqrt{ Z_{3} }A^{\mu},\quad e_{0} = Z_{e}e $$
故
$$Z_{1} = Z_{e}Z_{2}\sqrt{ Z_{3} } $$
通过二点三点函数的物理意义，我们有
$$\Gamma^{(2)}(p) = Z_{2}^{-1}(\not{\!p}-m) + 有限项 $$
$$\Gamma^{(3)}_{\mu}(p,p) = Z_{1}^{-1}e\gamma_{\mu} + 有限项 $$
代入 Ward 恒等式有
$$eZ_{1}^{-1}\gamma_{\mu} + 有限项 = eZ_{2}^{-1}\gamma_{\mu} + 有限项 $$
故 $Z_{1}=Z_{2}$ 这说明了
$$e_{0} = \frac{1}{\sqrt{ Z_{3} }}e $$
电荷的重整化与电子本身波函数无关，而是和光子的波函数相关。

## 3.5 一圈计算

### 3.5.1 电子自能

一圈修正后的电子传播子逆算符为 $\Gamma^{(2)}(p) = \not{p} - m_0 - \Sigma(p)$ 我们要计算其中的 $\Sigma(p)$ 它是
$$-i\Sigma(p) = \int \frac{\mathrm{d}^{4}k}{(2\pi)^{4}} (-ie\gamma^{\mu}) \frac{i}{\not{\!p}-\not{\!k}-m+i\varepsilon}(-ie\gamma^{\nu}) \frac{-ig_{\mu \nu}}{k^{2}+i\varepsilon} $$
进行以下的正规化：维数正规化规避 UV 发散，引入光子质量 $\mu$ 规避红外发散。
$$\Sigma(p) = -ie^{2} \int \frac{\mathrm{d}^{d}k}{(2\pi)^{d}} \frac{\gamma^{\mu}[\not{\!p}-\not{\!k}-m]\gamma_{\mu}}{(p-k)^{2}-m^{2}+i\varepsilon} \frac{1}{k^{2}-\mu^{2}+i\varepsilon} $$
对于分母使用费曼技巧
$$\frac{1}{AB} = \int dxdy \frac{\delta(x+y-1)}{[Ax+By]^{2}} $$
$$\begin{align}
\frac{1}{(p-k)^{2}-m^{2}} \frac{1}{k^{2}-\mu^{2}} &  = \int_{0}^{1} dx \frac{1}{[x(p-k)^{2}-xm^{2}+(1-x)k^{2}-(1-x)\mu^{2}]^{2}} \\
&= \int_{0}^{1} dx \frac{1}{[(k-xp)^{2}-(1-x)m^{2} -x\mu^{2} + x(1-x)p^{2}]^{2}} \\
 & = \int_{0}^{1} dx \frac{1}{[l^{2}-\Delta]^{2}}
\end{align} $$
对于分子使用迹技巧
$$\begin{align}
\gamma^{\mu}[\not{\!p}-\not{\!k}-m]\gamma_{\mu} & = (2-d)(\not{\!p}-\not{\!k}) + dm \\
 & = (2-d)\not{l} + (2-d)(1-x)\not{\!p} + dm 
\end{align} $$
于是积分变为
$$\begin{align}
&\quad\int_{0}^{1}  \, dx \int \frac{\mathrm{d}^{d}l}{(2\pi)^{d}} \frac{(2-d)\not{l} + (2-d)(1-x)\not{\!p} + dm }{[l^{2}-\Delta]^{2}}  \\
&= \int_{0}^{1}dx \int \frac{\mathrm{d}^{d}l}{(2\pi)^{d}} \frac{(2-d)(1-x)\not{\!p}+dm}{[l^{2}-\Delta]^{2}} & 奇偶性 \\
&= \int_{0}^{1}dx[ (2-d)(1-x)\not{\!p}+dm ] (-i) \int \frac{\mathrm{d}^{d}l_{E}}{(2\pi)^{d}} \frac{1}{[l_{E}^{2}-m^{2}]^{2}} & Wick转动 \\
&= -i\int_{0}^{1}dx[ (2-d)(1-x)\not{\!p}+dm ] \frac{1}{(4\pi)^{d/2}}\frac{\Gamma\left( 2-\frac{d}{2} \right)}{\Gamma(2)}\left( \frac{2}{\Delta} \right)^{2-d/2} & n维球积分 \\
&= -i \int_{0}^{1}dx[ (2-\varepsilon)(1-x)\not{\!p}+4m ] \frac{1}{(4\pi)^{2}}\left[  \frac{2}{\varepsilon} - \gamma + \ln(4\pi) - \ln\Delta + \mathcal{O}(\varepsilon) \right] & 渐进展开
\end{align}$$
所以
$$\Sigma(p) = \frac{\alpha}{4\pi} \int_{0}^{1} dx[ (2-\varepsilon)(1-x)\not{\!p} + 4m ] \left(  \frac{2}{\varepsilon} - \gamma + \ln \frac{4\pi \mu^{2}}{\Delta} \right) $$
提取发散部分（极点）：
$$\Sigma(p)_{div} = \frac{\alpha}{4\pi} \left( \frac{2}{\epsilon} \right) \int_0^1 dx [ 2(1-x)\not{p} - 4m ] = \frac{\alpha}{4\pi} \frac{2}{\epsilon} (\not{p} - 4m)$$


我们有抵消项 $\mathcal{L}_{CT} = (Z_2-1)\bar{\psi}i\not{\partial}\psi - (Z_2 Z_m - 1)m\bar{\psi}\psi$。要求全传播子在物理质量 $m$ 处有极点：$\Sigma(\not{p})\big|_{\not{p}=m} = \delta m$。利用上面的结果，在 $\not{p}=m$ 处：
$$\delta m = \Sigma(m) = \frac{3\alpha m}{4\pi} \left( \frac{2}{\epsilon} + \dots \right)$$
这决定了质量抵消项。要求极点处的残数为 1，即 $\frac{d\Sigma}{d\not{p}}\big|_{\not{p}=m} = Z_2 - 1 = \delta_2$。对 $\Sigma(p)$ 关于 $\not{p}$ 求导：
$$\delta_2 = \frac{\alpha}{4\pi} \left[ -\frac{2}{\epsilon} - \gamma_E - \int_0^1 dx \left( (1-x) \ln \frac{\mu^2}{\Delta} - \frac{2x(1-x)m^2}{\Delta} \right) \right]$$
### 3.5.2 真空极化

真空极化对应一个电子圈（Loop），其两个顶点分别注入和流出动量为 $q$ 的光子。根据费曼规则：
$$i\Pi^{\mu \nu}(q) = -(-ie)^{2} \int \frac{\mathrm{d}^{4}k}{(2\pi)^{4}} \gamma^{\mu} \frac{i}{\not{\!k}-m+i\varepsilon}\gamma^{\nu} \frac{i}{\not{\!k}+\not{\!q}-m+i\varepsilon} $$
使用维数正规化来处理 UV，
$$\Pi^{\mu \nu}(q) = ie^{2} \int \frac{\mathrm{d}^{d}k}{(2\pi)^{d}} \frac{\mathrm{Tr}[ \gamma^{\mu}(\not{\!k}-m)\gamma^{\nu}(\not{\!k}+\not{\!q}-m) ]}{(k^{2}-m^{2})((k+q)^{2}-m^{2})}$$
分母用费曼技巧
$$\begin{align}
 &\quad \int_{0}^{1} dx \frac{1}{[xk^{2}-xm^{2}+(1-x)(k+q)^{2}-(1-x)m^{2}]^{2}} \\
 & =\int_{0}^{1} dx \frac{1}{[(k+xq)^{2}-m^{2}+x(1-x)p^{2}]^{2}} \\
 & =\int_{0}^{1} dx \frac{1}{[l^{2}-\Delta]^{2}}
\end{align} $$
分子用迹技巧
$$\begin{align}
 & \quad4[k^{\mu}(k^{\nu}+q^{\nu})+k^{\nu}(k^{\mu}+q^{\mu})-g^{\mu \nu}(k^{2}+k\cdot q)] \\
 & = 4[ 2l^{\mu}l^{\nu} - 2x(1-x)q^{\mu}q^{\nu} - g^{\mu \nu}(l^{2}-x(1-x)q^{2}) ] \\
 & = 4 \left[ \frac{2-d}{d} g^{\mu\nu} l^2 + x(1-x)(q^2 g^{\mu\nu} - 2q^\mu q^\nu) \right]
\end{align}$$
所以积分为
$$\begin{align}
 & \quad\int_{0}^{1}dx \int \frac{\mathrm{d}^{d}l}{(2\pi)^{d}} \frac{4 \left[ \frac{2-d}{d} g^{\mu\nu} l^2 + x(1-x)(q^2 g^{\mu\nu} - 2q^\mu q^\nu) \right]}{[l^{2}-\Delta]^{2}}  \\
\end{align}$$
其中
$$\begin{align}
\int \frac{d^d l}{(2\pi)^d} \frac{l^2}{(l^2-\Delta)^2} = \frac{i}{(4\pi)^{d/2}} \frac{d}{2} \frac{\Gamma(1-d/2)}{\Gamma(2)} \Delta^{d/2-1}
\end{align} $$
$$\int \frac{d^d l}{(2\pi)^d} \frac{1}{(l^2-\Delta)^2} = \frac{i}{(4\pi)^{d/2}} \frac{\Gamma(2-d/2)}{\Gamma(2)} \Delta^{d/2-2} $$
所以
$$\begin{align}
\Pi^{\mu\nu}(q) &= \frac{-8e^2}{(4\pi)^{d/2}} \Gamma\left(2-\frac{d}{2}\right) \int_0^1 dx \, x(1-x) (q^2 g^{\mu\nu} - q^\mu q^\nu) \Delta^{d/2-2}  \\
\Pi(q) & = \frac{-8e^2}{16\pi^2} \left( \frac{2}{\epsilon} - \gamma + \ln(4\pi) + O(\epsilon) \right) \int_0^1 dx \, x(1-x) (1 - \frac{\epsilon}{2} \ln \Delta) \\
 & = -\frac{\alpha}{3\pi} \left[ \left( \frac{2}{\epsilon} - \gamma + \ln(4\pi) \right) - 6 \int_0^1 dx \, x(1-x) \ln \frac{\Delta}{\mu^2} \right]
\end{align}$$

发散部分 (UV Divergence)：
$$\Pi(q^2)_{div} = -\frac{\alpha}{3\pi} \frac{2}{\epsilon}$$

可以看出
$$\Pi^{\mu \nu}(q) = \Pi(q)(q^{2}g^{\mu \nu}-q^{\mu}q^{\nu}) $$
自动满足 Wrad 恒等式
$$q_{\mu}\Pi^{\mu \nu}(q)= 0 $$

### 3.5.3 顶点修正

顶点修正对应一个光子跨接在电子-光子顶点上的图。设入射电子动量为 $p$，出射为 $p'$，外线光子动量为 $q = p' - p$ 
$$-ie \Lambda^\mu(p', p) = \int \frac{d^d k}{(2\pi)^d} (-ie\gamma^\alpha) \frac{i}{\not{p}'-\not{k}-m} \gamma^\mu \frac{i}{\not{p}-\not{k}-m} (-ie\gamma^\beta) \frac{-ig_{\alpha\beta}}{k^2 - \mu_{ph}^2}$$
$$\frac{1}{abc} = \int_0^1 dx dy dz \, \delta(x+y+z-1) \frac{2}{[ax + by + cz]^3}$$
