---
up:
  - "[[写题]]"
related:
date:
tags:
  - 量子场论
  - 习题
---

# 题4.1
>[!note] 
>让我们回到经典源产生Klein-Gordon粒子的问题。回顾第2章，这个过程可以用哈密顿量描述
>$$
>H = H_0 + \int d^3 x \, (-j(t, \mathbf{x}) \phi(x)),
>$$
>其中 $H_0$ 是自由Klein-Gordon哈密顿量，$\phi(x)$ 是Klein-Gordon场，$j(x)$ 是一个c数标量函数。我们发现，如果在源开启前系统处于真空态，那么源将产生的平均粒子数为
>$$
>\langle N \rangle = \int \frac{d^3 p}{(2\pi)^3} \frac{1}{2E_p} |\tilde{j}(p)|^2.
>$$
>在这个问题中，我们将通过使用源强度的微扰展开来验证这一陈述，并提取更详细的信息。

>[!question] (a)
>证明源不产生粒子的概率为
>$$
>P(0) = \left| \langle 0 | T \{ \exp[i \int d^4 x \, j(x) \phi_I(x)] \} | 0 \rangle \right|^2.
>$$

意思就是要计算 $真空\to真空$ 的概率幅
$$\mathcal{A}_{\text{vac}\to\text{vac}} = \langle{0}|U_{I}(+\infty,-\infty)|0\rangle = \langle 0 | T\left\{   i \int \mathrm{d^{4}x} \ j(x) \phi_{I}(x)  \right\} | 0\rangle $$
所以源不产生粒子的概率是
$$P(0) = | \mathcal{A}_{\text{vac}\to\text{vac}} |^{2} = \left| \langle 0 | T \{ \exp[i \int d^4 x \, j(x) \phi_I(x)] \} | 0 \rangle \right|^2 $$


>[!question] (b)
>计算 $P(0)$ 中 $j^2$ 阶的项，并证明 $P(0) = 1 - \lambda + \mathcal{O}(j^4)$，其中 $\lambda$ 等于上面给出的 $\langle N \rangle$ 的表达式。

对指数做微扰展开
$$T e^{ i \int j\phi } = 1 + i \int \mathrm{d^{4}x} \ j(x)\phi(x) - \frac{1}{2}\int \mathrm{d^{4}x} \, \mathrm{d^{4}y} \ j(x)j(y) T\{ \phi(x)\phi(y) \} + \mathcal{O}(j^{3}) $$
一阶项
$$\langle 0|\phi(x)|0\rangle = 0 $$
二阶项
$$\langle 0|T\{ \phi(x)\phi(y) \}|0\rangle = \Delta_{F}(x-y) $$
$$\mathcal{A}_{vac\to vac} = 1 - \frac{1}{2} \int \mathrm{d^{4}x\,d^{4}y} \ j(x)\Delta_{F}(x-y)j(y) + \mathcal{O}(j^{3}) $$
所以
$$P(0) = |\mathcal{A}_{vac\to vac}|^{2} = 1 - \int \mathrm{d^{4}x\,d^{4}y} \ j(x) \mathrm{Im}\Delta_{F}(x-y) j(y) + \mathcal{O}(j^{4}) $$
其中
$$\mathrm{Im}\Delta_{F}(x-y) = \int \frac{\mathrm{d^{4}p}}{(2\pi)^{4}2E_{\mathbf{p}}} e^{ ip\cdot(x-y) }  $$
$$\tilde{j}(p) = \int \mathrm{d^{4}x} \ j(x) e^{ ip\cdot x } $$
所以
$$\int \mathrm{d^{4}x\,d^{4}y} \ j(x) \mathrm{Im}\Delta_{F}(x-y) j(y) = \int \frac{\mathrm{d^{4}p}}{(2\pi)^{4}2E_{\mathbf{p}}} |\tilde{j}(p)|^{2} = \langle N\rangle $$
$$P(0) = | 1 - \frac{\lambda}{2} + \mathcal{O}(j^{3}) |^{2} = 1 + \lambda + \mathcal{O}(j^{4}) $$


>[!question] (c)
>将(b)部分计算的项表示为费曼图。然后将 $P(0)$ 的整个微扰级数用费曼图表示。证明该级数指数化，因此可以精确求和：
>$$
>P(0) = \exp(-\lambda).
>$$

$$\mathcal{A}^{(2)}_{vac\to vac} = - \frac{1}{2}\int \mathrm{d^{4}x\,d^{4}y} \ j(x)\Delta_{F}(x-y)j(y) = -\frac{\lambda}{2} $$
它表示的费曼图是：在点 $x$ 处有源 $j(x)$ ，在点 $y$ 处有源 $j(y)$ ，两点间用 Klein–Gordon 传播子连接 $\Delta_{F}(x-y)$ 
$$j(x) \overset{\Delta_{F}}{●──────●} j(y)$$

类似 (b) 中所做的事，当插入奇数个场的时候，由 Wick 定理，总是可以把时序转化为正规序加上所有的收缩，收缩的结果一定是剩余一个场的，正规序和单个场的真空期望值都是零所以：只有插入偶数个场的时候会有真空贡献值。对于更高阶的插入偶数个场的情况，其 Feynman 图本质上是上面图的复制粘贴，考虑到对称因子，各阶的概率振幅为：
$$\begin{gather}
\mathcal{A}^{(2)} = j(x) \overset{\Delta_{F}}{●──────●} j(y) \\
\mathcal{A}^{(4)} = \frac{1}{2!} j(x) \overset{\Delta_{F}}{●──────●} j(y) \ \ j(z) \overset{\Delta_{F}}{●──────●} j(w) = \frac{1}{2!} \bigg[j(x) \overset{\Delta_{F}}{●──────●} j(y)\bigg]^{2} \\
\mathcal{A}^{(6)} = \frac{1}{3!} \bigg[j(x) \overset{\Delta_{F}}{●──────●} j(y)\bigg]^{3} \\
\dots \\
\mathcal{A}^{(2n)} = \frac{1}{n!} \bigg[j(x) \overset{\Delta_{F}}{●──────●} j(y)\bigg]^{n}
\end{gather} $$
所以
$$\begin{align}
P(0) = |\mathcal{A}|^{2} = \bigg|\sum_{n=0}^{\infty} \mathcal{A}^{2n} \bigg|^{2} = | \sum_{n=0}^{\infty} \frac{(-\lambda / 2)^{n}}{n!} |^{2} = \exp(-\lambda) 
\end{align} $$


>[!question] (d)
>计算源产生一个动量为 $\mathbf{k}$ 的粒子的概率。首先计算到 $\mathcal{O}(j)$ 阶，然后计算到所有阶，使用(c)部分的技巧对级数求和。

它就是要我们去计算这个概率幅
$$\mathcal{A}_{\text{vac}\to \mathbf{k}} \text{ 或者说 } \mathcal{A}_{\ket{0}\to \ket{\mathbf{k}} = a^{\dagger}_{\mathbf{k}}\ket{0}  } $$
在 $\mathcal{O}(j)$ 阶，只用插入一个场
$$\begin{align}
\mathcal{A}_{\text{vac}\to \mathbf{k}}^{(1)} &= i\int \mathrm{d^{4}x} \ j(x) \langle\mathbf{k}|\phi(x)|0\rangle  \\
&= i \int \mathrm{d^{4}x} \ j(x) \langle \mathbf{k}| \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }}( a_{\mathbf{p}}e^{ -ip\cdot x } + a^{\dagger}_{\mathbf{p}}e^{ -ip\cdot x } )|0 \rangle \\
&= i \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \int \mathrm{d^{4}x} \ j(x) \langle\mathbf{k}|  a_{\mathbf{p}}|0\rangle e^{ -ip\cdot x } \\
&= i \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \int \mathrm{d^{4}x} \ j(x) \langle\mathbf{k}|\mathbf{p} \rangle e^{ -ip\cdot x } \\
&= i \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \int \mathrm{d^{4}x} \ j(x) (2\pi)^{3}2E_{\mathbf{k}}\delta^{(3)}(\mathbf{p}-\mathbf{k}) e^{ -ip\cdot x } \\
&= i \int \mathrm{d^{4}x} \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }}  \ j(x) (2\pi)^{3}2E_{\mathbf{k}}\delta^{(3)}(\mathbf{p}-\mathbf{k}) e^{ -ip\cdot x } \\
&= \frac{i}{\sqrt{ 2E_{\mathbf{k}} }}  \int \mathrm{d^{4}x}  \ j(x)  e^{ -ik\cdot x } \\
&= \frac{i}{\sqrt{ 2E_{\mathbf{k}} }} \tilde{j}(\mathbf{k})
\end{align}$$
所以
$$P(0\to \mathbf{k}) = | 1 + \frac{i}{\sqrt{ 2E_{\mathbf{k}} }} \tilde{j}(\mathbf{k}) + \mathcal{O}(j^{2}) |^{2} = 1 + \frac{|\tilde{j}(\mathbf{k})|^{2}}{2E_{\mathbf{k}}} + \mathcal{O}(j^{4}) $$
它对应的 Feynman 图是这样的：
$$\mathcal{A}^{(1)} = j(x) ●───────────▶  k   $$
对于更高阶的项，无非就是再插入场(内点)，在图上的表现就是在线段上延申出来真空泡，所有图都长成：
```        
		真空泡 × n
          ○   ○
          |   |
j(x) ●────┴───┴────▶  k

```
含有 $n$ 个真空泡时的振幅因子是
$$\mathcal{A}^{(n)} = \mathcal{A}^{(1)}\times \frac{1}{n!} \left( -\frac{1}{2} \int \mathrm{d^{4}x\,\mathrm{d^{4}y}} \ j(x)\Delta_{F}(x-y)j(y)  \right)^{n} = \mathcal{A}^{(1)} \times \frac{(-\lambda / 2)^{n}}{n!} $$
所以
$$\mathcal{A}_{\ket{0}\to \ket{\mathbf{k}}} = \mathcal{A}^{(1)} e^{ -\lambda/2 } = \frac{i}{\sqrt{ 2E_{\mathbf{k}} }} \tilde{j}(\mathbf{k}) e^{ -\lambda/2 } $$
$$P(\ket{0}\to \ket{\mathbf{k}}  ) = \frac{|\tilde{j}(\mathbf{k})|^{2}}{2E_{\mathbf{k}}} e^{ -\lambda } $$


>[!question] (e)
>证明产生 $n$ 个粒子的概率为
>$$
>P(n) = (1/n!) \lambda^n \exp(-\lambda).
>$$
>这是一个*泊松分布*。

对固定的一组动量 $\{ \mathbf{k}_{i} \}$ 振幅必然形如
$$\mathcal{A}_{\ket{0}\to \ket{\mathbf{k}_{1},\dots \mathbf{k}_{n}}  } = \left[  \prod_{i=1}^{n} \frac{i}{\sqrt{ 2E_{\mathbf{k}_{i}} }} \tilde{j}(\mathbf{k}_{i})  \right] e^{ -\lambda/2 } $$
产生 $n$ 个粒子，那就对这 $n$ 个粒子的动量积分。再考虑到玻色子的全同性，概率为
$$P(n) = \frac{e^{ -\lambda }}{n!} \int \prod_{i=1}^{n} \frac{\mathrm{d^{3}k_{i}}}{(2\pi)^{3}2E_{\mathbf{k}_{i}}} \frac{|\tilde{j}(\mathbf{k}_{i})|^{2}}{2E_{\mathbf{k}_{i}}} $$
注意到
$$\lambda = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} |\tilde{j}(\mathbf{p})|^{2} $$
所以
$$P(n) = \frac{\lambda^{n}}{n!}e^{ -\lambda } $$
是一个泊松分布

>[!question] (f)
>证明关于泊松分布的以下事实：
>$$
>\sum_{n=0}^\infty P(n) = 1; \quad \langle N \rangle = \sum_{n=0}^\infty n P(n) = \lambda.
>$$
>第一个等式说明 $P(n)$ 是正确归一化的概率，而第二个等式证实了我们关于 $\langle N \rangle$ 的提议。计算均方涨落 $\langle (N - \langle N \rangle)^2 \rangle$。

$$\sum_{n=0}^{\infty} \frac{\lambda^{n}}{n!}e^{ -\lambda } = e^{ \lambda } e^{ -\lambda } = 1 $$
$$\sum_{n=0}^{\infty} \frac{n\lambda^{n}}{n!}e^{ -\lambda } = \lambda e^{ -\lambda } \sum_{m=0}^{\infty} \frac{\lambda^{m}}{m!} = \lambda $$
$$\begin{align}
\langle N^{2}\rangle &= \sum_{n=0}^{\infty} \frac{n^{2}\lambda^{n}}{n!} e^{ -\lambda } = e^{ -\lambda } \sum_{n=0}^{\infty} n(n-1) \frac{\lambda^{n}}{n!} + e^{ -\lambda }\sum_{n=0}^{\infty} \frac{n\lambda^{n}}{n!} \\
&= e^{ -\lambda }\lambda^{2}\sum_{m=0}^{\infty} \frac{\lambda^{m}}{m!} + \lambda \\
&= \lambda^{2} + \lambda
\end{align} $$
$$\langle(N-\langle N\rangle)^{2}\rangle = \langle N^{2}\rangle - \langle N\rangle^{2} = \lambda $$


---

# 题4.2
>[!note] **标量粒子的衰变**。
>考虑以下涉及两个实标量场 $\Phi$ 和 $\phi$ 的拉格朗日量：
>$$
>\mathcal{L} = \frac{1}{2} (\partial_\mu \Phi)^2 - \frac{1}{2} M^2 \Phi^2 + \frac{1}{2} (\partial_\mu \phi)^2 - \frac{1}{2} m^2 \phi^2 - \mu \Phi \phi \phi.
>$$
>最后一项是一个相互作用项，它允许 $\Phi$ 粒子衰变成两个 $\phi$，前提是 $M > 2m$。假设该条件满足，计算 $\Phi$ 的寿命到 $\mu$ 的最低阶。

允许的最低阶是
$$\Phi\to \phi + \phi $$
这是一个 **三点顶点**。衰变率是
$$\Gamma = \frac{1}{2M} \int \mathrm{d\Pi_{2}} |\mathcal{A}|^{2} $$
其中
$$\mathrm{d\Pi_{2}} = (2\pi)^{4} \delta^{(4)}(P-k_{1}-k_{2}) \frac{\mathrm{d^{3}k_{1}}}{(2\pi)^{3}2E_{\mathbf{k}_{1}}} \frac{\mathrm{d^{3}k_{2}}}{(2\pi)^{3}2E_{\mathbf{k}_{2}}} $$
$$\mathcal{A} = \langle \mathbf{k}_{1},\mathbf{k}_{2}| Te^{ i \int \mathrm{d^{4}x}\ \mu \Phi \phi \phi }|\mathbf{P}\rangle $$
指数展开
$$Te^{ i \int \mathrm{d^{4}x}\ \mu \Phi \phi \phi } = 1 + i\mu \int \mathrm{d^{4}x}\ T\{ \Phi(x)\phi(x)\phi(x) \} + \mathcal{O}(\mu^{2}) $$
$$\mathcal{A}^{(1)} = i\mu \int \mathrm{d^{4}x}\ \langle \mathbf{k}_{1},\mathbf{k}_{2}|T\{ \Phi(x)\phi(x)\phi(x) \}|\mathbf{P}\rangle $$
然后使用 Wick 定理来收缩算符和态，$\Phi$ 只有和 $\ket{\mathbf{P}}$ 收缩才有非零值，$\phi$ 只有和 $\ket{\mathbf{k}_{1,2}}$ 收缩才有非零值，所以非平凡的项为：$\Phi$ 与 $\ket{\mathbf{P}}$ 收缩，两个 $\phi$ 分别与 $\ket{\mathbf{k}_{1},\mathbf{k}_{2}}$ 收缩，后者有 $2!$ 种收缩方式，所以
$$\mathcal{A}^{(1)} = i\mu\cdot 2! \int \mathrm{d^{4}x}\ \frac{e^{ -iP\cdot x }}{\sqrt{ 2E_{\mathbf{P}} }} \frac{e^{ -ik_{1}\cdot x }}{\sqrt{ 2E_{\mathbf{k}_{1}} }} \frac{e^{ -ik_{2}\cdot x }}{\sqrt{ 2E_{\mathbf{k}_{2}} }} = 2i\mu \frac{(2\pi)^{4} \delta^{(4)}(P-k_{1}-k_{2})}{\sqrt{ 8E_{\mathbf{P}}E_{\mathbf{k}_{1}}E_{\mathbf{k}_{2}} }} $$
$$\mathcal{A} = 1 + 2i\mu \frac{(2\pi)^{4} \delta^{(4)}(P-k_{1}-k_{2})}{\sqrt{ 8E_{\mathbf{P}}E_{\mathbf{k}_{1}}E_{\mathbf{k}_{2}} }} + \mathcal{O}(\mu^{2}) $$
最后取 $\Phi$ 的静止系 $E_{\mathbf{P}}=M$ ：
$$\int \mathrm{d\Pi_{2}} = \frac{1}{8\pi} \frac{|\mathbf{k}|}{M} ,\qquad |\mathbf{k}| = \frac{1}{2}\sqrt{ M^{2}-4m^{2} } $$
$$\Gamma = \frac{1}{2M} \int \mathrm{d\Pi_{2}} |\mathcal{A}|^{2} = \frac{\mu^{2}}{8\pi M} \sqrt{ 1 - \frac{4m^{2}}{M^{2}} } $$
$\Phi$ 寿命为
$$\tau = \Gamma^{-1} = \dots $$

---

# 题4.3
>[!note] **线性sigma模型**。
>低能下π介子的相互作用可以用一个称为*线性sigma模型*的唯象模型来描述。本质上，该模型由 $N$ 个实标量场组成，通过一个在 $N$ 个场旋转下对称的 $\phi^4$ 相互作用耦合。更具体地说，设 $\Phi^i(x), \, i = 1, \ldots, N$ 是一组 $N$ 个场，由哈密顿量
>$$
>H = \int d^3x \left( \frac{1}{2} (\Pi^i)^2 + \frac{1}{2} (\nabla \Phi^i)^2 + V(\Phi^2) \right),
>$$
>支配，其中 $(\Phi^i)^2 = \Phi \cdot \Phi$，且
>$$
>V(\Phi^2) = \frac{1}{2} m^2 (\Phi^2)^2 + \frac{\lambda}{4} ((\Phi^2)^2)^2
>$$
>是一个在 $\Phi$ 旋转下对称的函数。对于在空间和时间上恒定的 $\Phi^i(x)$ 的（经典）场位形，这一项给出了对 $H$ 的唯一贡献；因此，$V$ 是场势能。
>
>（这个哈密顿量与强相互作用有什么关系？有两种轻夸克，$u$ 和 $d$。这些夸克具有相同的强相互作用，但质量不同。如果这些夸克无质量，则强相互作用的哈密顿量对2分量对象 $(u, d)$ 的酉变换不变：
>$$
>\begin{pmatrix}
>u \\
>d
>\end{pmatrix}
>\to \exp(i\alpha \cdot \sigma / 2)
>\begin{pmatrix}
>u \\
>d
>\end{pmatrix}.
>$$
>这种变换称为*同位旋*旋转。此外，如果强相互作用由矢量“胶子”场描述（正如在QCD中那样），则强相互作用哈密顿量对在夸克场的左手和右手分量上分别进行的同位旋旋转不变。因此，具有两个无质量夸克的QCD的完整对称性是 $SU(2) \times SU(2)$。恰好 $SO(4)$，即4维旋转群，同构于 $SU(2) \times SU(2)$，所以对于 $N = 4$，线性sigma模型具有与强相互作用相同的对称群。）

>[!question] (a)
>通过注意到当 $\lambda = 0$ 时，上面给出的哈密顿量正好是Klein-Gordon哈密顿量的 $N$ 个副本，分析 $m^2 > 0$ 时的线性sigma模型。然后我们可以将散射振幅计算为参数 $\lambda$ 的微扰级数。证明传播子为
>$$
>\langle \Phi^i(x) \Phi^j(y) \rangle = \delta^{ij} D_F(x - y),
>$$
>其中 $D_F$ 是质量为 $m$ 的标准Klein-Gordon传播子，并且有一种顶点，其值为
>$$
>\begin{array}{c}
>k \quad l \\
>i \quad j
>\end{array}
>= -2i\lambda (\delta^{ij} \delta^{kl} + \delta^{il} \delta^{jk} + \delta^{ik} \delta^{jl}).
>$$
>（也就是说，两个 $\Phi^1$ 和两个 $\Phi^2$ 之间的顶点值为 $(-2i\lambda)$；四个 $\Phi^1$ 之间的顶点值为 $(-6i\lambda)$。）计算到 $\lambda$ 的领先阶，在质心系中，散射过程
>$$
>\Phi^1 \Phi^2 \to \Phi^1 \Phi^2, \quad \Phi^1 \Phi^1 \to \Phi^2 \Phi^2, \quad \text{和} \quad \Phi^1 \Phi^1 \to \Phi^1 \Phi^1
>$$
>的微分截面 $d\sigma/d\Omega$，作为质心能量的函数。

当  $\lambda=0$ 时这就是 $N$ 个互不相关的实的 Klein-Gordon 场
$$\mathcal{L} = \frac{1}{2} \partial^{\mu}\Phi^{i}\partial_{\mu}\Phi^{i} - \frac{1}{2}m^{2}\Phi^{i}\Phi^{i} - \frac{\lambda}{4}(\Phi^{i}\Phi^{i})^{2} $$
所以每个场的分量都满足 Klein-Gordon 方程
$$(\Box+m^{2})\Phi^{i} = 0 $$
对于真空态，任何场分量的期望值是零，所以任何场的收缩是零，由 Wick 定理得到
$$\langle 0| T\{ \Phi^{i}(x),\Phi^{j}(y) \}|0\rangle = \delta_{ij} \Delta_{F}(x-y) $$
在最低阶 $\mathcal{O}(\lambda)$ 中只有一个四点接触项，没有传播子交换。所以 $\mathcal{A}=-2\lambda \times(一些\ \delta\ 的组合)$ 微分截面的一般公式（两体 → 两体）为
$$\frac{d\sigma}{d\Omega} = \frac{1}{64\pi^{2}s} \frac{|\mathbf{p}_{f}|}{|\mathbf{p}_{i}|} |\mathcal{A}|^{2} $$
在质心系、弹性碰撞下 $|\mathbf{p}_{f}|=|\mathbf{p}_{i}|$ 下面计算散射振幅。设 $s=(p_{1}+p_{2})^{2}=E_{CM}^{2}$  
$$\Phi^{1}+\Phi^{2}\to \Phi^{1}+\Phi^{2} \implies \mathcal{A}=-2i\lambda \implies \frac{d\sigma}{d\Omega} = \frac{\lambda^{2}}{16\pi^{2}s} $$
$$\Phi^{1}+\Phi^{1}\to \Phi^{2}+\Phi^{2} \implies \mathcal{A}=-2i\lambda \implies \frac{d\sigma}{d\Omega} = \frac{\lambda^{2}}{16\pi^{2}s}  $$
$$\Phi^{1}+\Phi^{1}\to \Phi^{1}+\Phi^{1} \implies \mathcal{A}=-6i\lambda \implies \frac{d\sigma}{d\Omega} = \frac{9\lambda^{2}}{16\pi^{2}s}  $$
   

>[!question] (b)
>现在考虑 $m^2 < 0$ 的情况：$m^2 = -\mu^2$。在这种情况下，$V$ 在 $\Phi^i = 0$ 处有一个局部最大值，而不是最小值。由于 $V$ 是势能，这意味着理论的基态不在 $\Phi^i = 0$ 附近，而是通过将 $\Phi^i$ 移动到 $V$ 的最小值处获得。根据旋转不变性，我们可以考虑这个移动是在第 $N$ 个方向。于是写出：
>$$
>\Phi^i(x) = \pi^i(x), \quad i = 1, \ldots, N-1,
>$$
>$$
>\Phi^N(x) = v + \sigma(x),
>$$
>其中 $v$ 是一个常数，选择为使 $V$ 最小化。（记号 $\pi^i$ 暗示一个π介子场，不应与正则动量混淆。）证明，在这些新坐标中（并用 $\lambda$ 和 $\mu$ 表示 $v$ 的表达式代入），我们得到一个具有质量 $\sigma$ 场和 $N-1$ 个*无质量*π介子场的理论，通过三次和四次势能项相互作用，所有这些项在 $\lambda \to 0$ 时都变小。通过给传播子和顶点赋值来构建费曼规则：
>$$
>\begin{array}{c}
>\sigma \, \sigma \text{ 传播子} = \frac{i}{p^2 - (2\mu^2)} \\
>\pi^i \, \pi^j \text{ 传播子} = \frac{i \delta^{ij}}{p^2}
>\end{array}
>$$
>顶点：图示。请根据原题内容补充顶点规则。
>![[Peskin 第4章图例2.png]]

设 $\rho^{2}=\Phi^{i}\Phi^{i}=v^{2}$ 则
$$V(\rho) = -\frac{\mu^{2}}{2} \rho^{2} + \frac{\lambda}{4}\rho^{4} $$
极值条件是 $\dfrac{dV}{d\rho} = -\mu^{2}\rho + \lambda \rho^{3} = 0$ 非平凡解是 $\rho^{2}=\dfrac{\mu^{2}}{\lambda}$ 此时的拉式量是
$$\mathcal{L} = \frac{1}{2}(\partial \sigma)^{2} - \frac{1}{2}(2\mu^{2})\sigma^{2} + \frac{1}{2}(\partial \pi^{i})^{2} - \lambda v\sigma^{3} - \lambda v\sigma \pi^i\pi^{i} - \frac{\lambda}{4!}\sigma^{4} - \frac{\lambda}{2}\sigma^{2}\pi^{i}\pi^{i} - \frac{\lambda}{4}(\pi^{i}\pi^{i})^{2} $$
由此看出 $\sigma$ 场的质量是 $m_{\sigma}^{2}=2\mu^{2}$，$\pi^{i}$ 场的质量是 $m_{\pi^{i}}^{2}=0$ $(i=1,2,\dots,N-1)$ 从拉式量可以直接读出来：
- $\sigma \sigma\ 传播子 = \dfrac{i}{p^{2}-2\mu^{2} + i\varepsilon}$
- $\pi^{i} \pi^{j}传播子=\dfrac{i}{p^{2} + i\varepsilon} \delta^{ij}$
- $\sigma \sigma \sigma顶点 = -6i\lambda v$
- $\sigma \pi^{i}\pi^{j}顶点=-2i\lambda v\delta^{ij}$
- $\sigma \sigma \sigma \sigma顶点=-6i\lambda$
- $\sigma \sigma \pi^{i}\pi^{j}顶点=-2i\lambda \delta^{ij}$
- $\pi^{i}\pi^{j}\pi^{k}\pi^{l}顶点=-2i\lambda(\delta^{ij}\delta^{kl}+\delta^{ik}\delta^{jl}+\delta^{il}\delta^{jk})$

>[!question] (c)
>计算过程
>$$
>\pi^i(p_1) \pi^j(p_2) \to \pi^k(p_3) \pi^l(p_4)
>$$
>的散射振幅到 $\lambda$ 的领先阶。现在有四个费曼图贡献：
>![[peksin 第4章图例2.png]]
>证明在阈值（$p_i = 0$）处，这些图的和为零。（提示：可能首先考虑特定过程 $\pi^1\pi^1 \to \pi^2\pi^2$，此时只有第一个和第四个图非零，然后再处理一般情况。）证明在特殊情况 $N = 2$（1种π介子）下，$\mathcal{O}(p^2)$ 项也抵消。

第一个图的振幅是
$$\mathcal{M_{1}} = (-2i\lambda v\delta^{ij})\left( \frac{i}{p^{2}-2\mu^{2}+i\varepsilon} \right)(-2i\lambda v\delta^{kl}) = -\frac{4i\lambda^{2}v^{2}}{p^{2}-2\mu^{2}+i\varepsilon}\delta^{ij}\delta^{kl} $$
类似的
$$\mathcal{M_{2}} = -\frac{4i\lambda^{2}v^{2}}{p^{2}-2\mu^{2}+i\varepsilon}\delta^{ik}\delta^{jl} $$
$$\mathcal{M_{3}}=-\frac{4i\lambda^{2}v^{2}}{p^{2}-2\mu^{2}+i\varepsilon}\delta^{il}\delta^{jk} $$
$$\mathcal{M_{4}} = -2i\lambda(\delta^{ij}\delta^{kl}+\delta^{ik}\delta^{jl}+\delta^{il}\delta^{jk}) $$
于是总的振幅是
$$\mathcal{M} = -2i\lambda\left( 1 + \frac{2i\lambda^{2}v^{2}}{s^{2}-2\mu^{2}+i\varepsilon} \right)\delta^{ij}\delta^{kl} + \dots  $$
在阈值时 $s=p=t=0$ 所以代入得 $\mathcal{M}=0$ 

>[!question] (d)
>向 $V$ 添加一个对称性破缺项：
>$$
>\Delta V = -a\Phi^N,
>$$
>其中 $a$ 是一个（小）常数。（在QCD中，如果 $u$ 和 $d$ 夸克具有相同的非零质量，就会产生这种形式的项。）求使 $V$ 最小化的新 $v$ 值，并找出在该点附近的理论内容。证明π介子获得一个质量，使得 $m_\pi^2 \sim a$，并证明阈值处的π介子散射振幅现在非零且也与 $a$ 成正比。

现在的势能项是
$$V = \frac{m^{2}}{2}\Phi^{i}\Phi^{i} + \frac{\lambda}{4}(\Phi^{i}\Phi^{i})^{2} - a\Phi^{N} $$
由旋转对称性不妨设
$$\Phi^{i}=0,(i=1,2,\dots,N-1),\quad \Phi^{N}=v $$
则
$$V = \frac{m^{2}}{2}v^{2} + \frac{\lambda}{4}v^{4} - av $$
极值条件为 $\dfrac{dV}{dv}=m^{2}v + \lambda v^{3}-a=0$ 使用拉格朗日反演法解得 $v(a)$ ：
$$v=\sqrt{ -\frac{m^{2}}{\lambda} } - \frac{a}{2m^{2}} + \mathcal{O}(a^{2}) $$


---

# 题4.4
>[!note] **卢瑟福散射**。
>电子被原子核库仑场散射的截面可以计算到最低阶，而无需将电磁场量子化。相反，将场视为给定的经典势 $A_\mu(x)$。相互作用哈密顿量为
>$$
>H_I = \int d^3x \, e\bar{\psi}\gamma^\mu\psi A_\mu,
>$$
>其中 $\psi(x)$ 是通常的量子化狄拉克场。

>[!question] (a)
>证明电子在局域经典势上散射的 $T$ 矩阵元到最低阶为
>$$
>\langle p'|iT|p\rangle = -ie\bar{u}(p')\gamma^\mu u(p) \cdot \tilde{A}_\mu(p' - p),
>$$
>其中 $\tilde{A}_\mu(q)$ 是 $A_\mu(x)$ 的四维傅里叶变换。

在相互作用绘景中
$$S = T\exp\left( -i \int \mathrm{d^{4}x}\ \mathcal{H}_{I}(x) \right) $$
展开到最低非平凡阶：
$$iT^{(1)} = -i \int \mathrm{d^{4}x}\ \mathcal{H}_{I}(x)  $$
$$\begin{align}
\langle p'|iT^{(1)}|p\rangle &= -i \int \mathrm{d^{4}x}\ e\langle p'|\bar{\psi}\gamma^{\mu}\psi|p\rangle A_{\mu}\\ &= -ie \int \mathrm{d^{4}x}\ \bar{u}(p')\gamma^{\mu}u(p)e^{ i(p'-p)\cdot x }A_{\mu}\\ &= -ie\bar{u}(p')\gamma^\mu u(p) \cdot \tilde{A}_\mu(p' - p) 
\end{align}$$

>[!question] (b)
>如果 $A_\mu(x)$ 与时间无关，其傅里叶变换包含一个能量 delta 函数。那么很自然地定义
>$$
>\langle p'|iT|p\rangle \equiv i\mathcal{M} \cdot (2\pi)\delta(E_f - E_i),
>$$
>其中 $E_i$ 和 $E_f$ 是粒子的初始和最终能量，并采用新的费曼规则来计算 $\mathcal{M}$：
>![[Peskin 第4章图例3.png]]
>其中 $\tilde{A}_\mu(\mathbf{q})$ 是 $A_\mu(x)$ 的三维傅里叶变换。给定 $\mathcal{M}$ 的这个定义，证明散射一个与时间无关、局域势的截面为
>$$
>d\sigma = \frac{1}{v_i} \frac{1}{2E_i} \frac{d^3p_f}{(2\pi)^3} \frac{1}{2E_f} |\mathcal{M}(p_i \to p_f)|^2 (2\pi)\delta(E_f - E_i),
>$$
>其中 $v_i$ 是粒子的初始速度。这个公式是(4.79)的自然修改。对 $|p_f|$ 积分，找出 $d\sigma/d\Omega$ 的简单表达式。

如果 $A_{\mu}(x)$ 与时间无关则 $A_{\mu}(x)=A_{\mu}(\mathbf{x})$ 傅里叶变换将给出
$$\tilde{A}_{\mu}(p'-p) = (2\pi)\delta(p'^{0}-p^{0})\tilde{A}_{\mu}(\mathbf{p}'-\mathbf{p}) $$
故
$$\langle p'|iT|p\rangle = i\mathcal{M} \cdot (2\pi)\delta(E_f - E_i) ,\quad \mathcal{M} = -ie\bar{u}(p_{f})\gamma^{\mu}u(p_{i})\tilde{A}_{\mu}(\mathbf{p}_{f}-\mathbf{p}_{i}) $$
跃迁概率为
$$\begin{align}
dP &= |\langle p_{f}|iT|p_{i}\rangle|^{2} \frac{\mathrm{d^{3}p_{f}}}{(2\pi)^{2}2E_{\mathbf{p}_{f}}}  \\
&= \frac{\mathrm{d^{3}p_{f}}}{(2\pi)2E_{\mathbf{p}_{f}}} \delta(E_{f}-E_{i})^{2} |\mathcal{M}|^{2} \\
&= \frac{\mathrm{d^{3}p_{f}}}{(2\pi)2E_{\mathbf{p}_{f}}} \frac{T\delta(E_{f}-E_{i})}{2\pi} |\mathcal{M}|^{2} \\
&= \frac{\mathrm{d^{3}p_{f}}}{(2\pi)^{2}2E_{\mathbf{p}_{f}}} T\delta(E_{f}-E_{i}) |\mathcal{M}|^{2}
\end{align}$$
于是跃迁率
$$d\Gamma = \frac{dP}{T} = \frac{\mathrm{d^{3}p_{f}}}{(2\pi)^{2}2E_{\mathbf{p}_{f}}} \delta(E_{f}-E_{i}) |\mathcal{M}|^{2} $$
所以截面是
$$d\sigma = \frac{d\Gamma}{\text{flux}} = \frac{1}{v_i} \frac{1}{2E_i} \frac{d^3p_f}{(2\pi)^3} \frac{1}{2E_f} |\mathcal{M}|^2 (2\pi)\delta(E_f - E_i) $$
对 $|\mathbf{p}_{f}|$ 积分：首先 $\mathrm{d^{3}p_{f}}=p^{2}_{f}\mathrm{dp_{f}d\Omega}$ , $\delta(E_{f}-E_{i})=\delta(\sqrt{ p_{f}^{2} + m^{2} } - E_{i}) = \dfrac{E_{f}}{p_{f}} \delta(p_{f}-p_{i})$ 所以
$$\int \frac{\mathrm{d^{3}p_{f}}}{(2\pi)^{3}2E_{{f}}} (2\pi)\delta(E_{f}-E_{i}) = \frac{p_{i}}{2\pi}\mathrm{d\Omega} $$
$$\mathrm{d\sigma} = \frac{1}{(2\pi)^{3}} \frac{p_{i}}{v_{i}2E_{i}} |\mathcal{M}|^{2} \mathrm{d\Omega} $$
所以
$$\frac{\mathrm{d\sigma}}{\mathrm{d\Omega}} = \frac{1}{(2\pi)^{3}} \frac{p_{i}}{v_{i}2E_{i}} |\mathcal{M}|^{2} = \frac{1}{(2\pi)^{3}} \frac{1}{4} |\mathcal{M}|^{2} $$


>[!question] (c)
>专门讨论电子从库仑势（$A^0 = Ze/4\pi r$）散射的情况。在非相对论极限下，推导卢瑟福公式：
>$$
>\frac{d\sigma}{d\Omega} = \frac{\alpha^2 Z^2}{4m^2 v^4 \sin^4(\theta/2)}.
>$$
>（利用5.1节的一些计算技巧，你将能够轻松计算相对论情况下的总截面；参见问题5.1。）

代入库伦势
$$A^{0}(\mathbf{x}) = \frac{Ze}{4\pi r} $$
$$\tilde{A}^{0}(\mathbf{q}) = \int \mathrm{d^{3}x}\ e^{ -i\mathbf{q}\cdot \mathbf{x} } \frac{Ze}{4\pi r} = \frac{Ze}{|\mathbf{q}|^{2}2} $$
$$\mathcal{M} = -ie^{2}Z \frac{\bar{u}(p)\gamma^{0}u(k)}{|\mathbf{q}|^{2}} $$
在非相对论的极限下
$$E \simeq m ,\quad |\mathbf{p}|\ll m $$
$$\bar{u}(p)\gamma^{0}u(k) \simeq{2}m $$
所以
$$\mathcal{M} \simeq -\frac{2me^{2}Z}{|\mathbf{q}|^{2}} $$
最后在弹性散射中
$$|\mathbf{p}|=|\mathbf{k}|=p $$
$$|\mathbf{q}|^{2}=|\mathbf{k}-\mathbf{p}|^{2}=2p^{2}(1-\cos \theta) = 4p^{2}\sin ^{2}\frac{\theta}{2} $$
$$\mathcal{M} = -\frac{2me^{2}Z}{4p^{2}\sin ^{2}\dfrac{\theta}{2}} $$
$$\frac{\mathrm{d\sigma}}{\mathrm{d\Omega}} = \frac{m^{2}e^{4}Z^{2}}{16\pi^{2}p^{4}\sin^{4} \dfrac{\theta}{2}} $$

---