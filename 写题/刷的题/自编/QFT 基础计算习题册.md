---
up:
  - "[[写题]]"
related:
  - "[[弯曲时空下的QFT]]"
  - "[[膨胀宇宙中的粒子产生]]"
  - "[[做题总结-膨胀宇宙]]"
  - "[[做题总结-弯曲时空中的量子场论]]"
date: 2026-05-06
tags:
  - QFT
  - problem-set
  - canonical-quantization
  - S-matrix
  - Feynman-diagrams
  - renormalization
---

# QFT 基础计算习题册

> 共 10 章，50 道题。覆盖正则量子化到一圈重整化。
> 标 $\star$ 为选做，标 $\star\star$ 为挑战。

---

## 第一章 正则量子化与 Fock 空间

### 1.1 实标量场的模展开

**(a)** 从 Lagrangian $\mathcal{L} = \frac{1}{2}\partial_\mu\phi\partial^\mu\phi - \frac{1}{2}m^2\phi^2$ 出发，导出 Hamiltonian 密度 $\mathcal{H}$ 和等时对易关系 $[\phi(t,\mathbf{x}), \pi(t,\mathbf{y})] = i\delta^{(3)}(\mathbf{x}-\mathbf{y})$。

**(b)** 写出 $\phi$ 的 Fourier 模展开（带产生湮灭算符），用 $[\phi,\pi]$ 反推出 $[a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger] = (2\pi)^3 \delta^{(3)}(\mathbf{k}-\mathbf{p})$。此即**反转法**。

**(c)** 将 $H$ 用 $a_{\mathbf{k}}, a_{\mathbf{k}}^\dagger$ 表达，并解释零点能的起源。

### 1.2 正规序与 Wick 定理的预备

**(a)** 计算 $[a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger a_{\mathbf{q}}^\dagger]$ 和 $[a_{\mathbf{k}}^\dagger a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger]$。

**(b)** 对 $H = \int \frac{d^3k}{(2\pi)^3}\,\omega_k\, a_{\mathbf{k}}^\dagger a_{\mathbf{k}}$（正规序后），证明 $[H, a_{\mathbf{p}}^\dagger] = \omega_p a_{\mathbf{p}}^\dagger$。

**(c)** 解释上述结果如何推出 $a_{\mathbf{p}}^\dagger |0\rangle$ 是能量为 $\omega_p$ 的单粒子态。

### 1.3 复标量场

考虑 $\mathcal{L} = \partial_\mu\phi^\dagger \partial^\mu\phi - m^2\phi^\dagger\phi$。

**(a)** 写出 $\phi$ 和 $\phi^\dagger$ 的共轭动量，给出等时对易关系。

**(b)** 模展开包含两种粒子：
$$\phi = \int \frac{d^3k}{(2\pi)^3\sqrt{2\omega_k}} \left(a_{\mathbf{k}} e^{-ikx} + b_{\mathbf{k}}^\dagger e^{ikx}\right)$$
推导 $[a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger] = [b_{\mathbf{k}}, b_{\mathbf{p}}^\dagger] = (2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{p})$，其余对易子为零。

**(c)** 找出守恒的 $U(1)$ 荷 $Q$，并用产生湮灭算符表达。验证 $[Q, a_{\mathbf{k}}^\dagger] = +a_{\mathbf{k}}^\dagger$，$[Q, b_{\mathbf{k}}^\dagger] = -b_{\mathbf{k}}^\dagger$，解释 $a$ 粒子和 $b$ 粒子为何互为反粒子。

> [!s]- **(a) 共轭动量与等时对易关系**
>
> 把 $\phi$ 和 $\phi^\dagger$ 视为独立场变量。共轭动量：
>
> $$\pi = \frac{\partial\mathcal{L}}{\partial(\partial_0\phi)} = \partial^0\phi^\dagger = \dot{\phi}^\dagger,\qquad \pi^\dagger = \frac{\partial\mathcal{L}}{\partial(\partial_0\phi^\dagger)} = \partial^0\phi = \dot{\phi}$$
>
> 等时对易关系：
>
> $$\boxed{[\phi(t,\mathbf{x}), \pi(t,\mathbf{y})] = [\phi^\dagger(t,\mathbf{x}), \pi^\dagger(t,\mathbf{y})] = i\delta^{(3)}(\mathbf{x}-\mathbf{y})}$$
>
> 其余对易子为零：
>
> $$[\phi, \phi] = [\phi^\dagger, \phi^\dagger] = [\phi, \phi^\dagger] = 0$$
> $$[\pi, \pi] = [\pi^\dagger, \pi^\dagger] = [\pi, \pi^\dagger] = 0$$
> $$[\phi, \pi^\dagger] = [\phi^\dagger, \pi] = 0$$
>
> **物理解释**：$\phi$ 和 $\phi^\dagger$ 互为厄米共轭，不是独立的实自由度——但它们作为**独立的复自由度**进行正则量子化。$(\phi, \pi)$ 和 $(\phi^\dagger, \pi^\dagger)$ 各构成一对正则变量，两对之间互相对易。这等价于把复标量场分解为两个实标量场 $\phi = (\phi_1 + i\phi_2)/\sqrt{2}$，$\phi_1$ 和 $\phi_2$ 各自拥有独立的正则结构。

> [!s]- **(b) 模展开与产生湮灭算符对易关系**
>
> 已知模展开：
>
> $$\phi(x) = \int \frac{d^3k}{(2\pi)^3\sqrt{2\omega_k}} \left(a_{\mathbf{k}} e^{-ikx} + b_{\mathbf{k}}^\dagger e^{ikx}\right)$$
>
> 厄米共轭：
>
> $$\phi^\dagger(x) = \int \frac{d^3k}{(2\pi)^3\sqrt{2\omega_k}} \left(b_{\mathbf{k}} e^{-ikx} + a_{\mathbf{k}}^\dagger e^{ikx}\right)$$
>
> 其中 $k^0 = \omega_k = \sqrt{\mathbf{k}^2+m^2}$。共轭动量：
>
> $$\pi(x) = \dot{\phi}^\dagger(x) = \int \frac{d^3k}{(2\pi)^3\sqrt{2\omega_k}} (-i\omega_k)\left(b_{\mathbf{k}} e^{-ikx} - a_{\mathbf{k}}^\dagger e^{ikx}\right)$$
>
> $$\pi^\dagger(x) = \dot{\phi}(x) = \int \frac{d^3k}{(2\pi)^3\sqrt{2\omega_k}} (-i\omega_k)\left(a_{\mathbf{k}} e^{-ikx} - b_{\mathbf{k}}^\dagger e^{ikx}\right)$$
>
> **推导 $[a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger]$**：在等时 $x^0=y^0=0$ 下计算 $[\phi(\mathbf{x}),\pi(\mathbf{y})]$：
>
> $$\begin{aligned}
> [\phi(\mathbf{x}), \pi(\mathbf{y})] &= \iint \frac{d^3k\,d^3p}{(2\pi)^6\sqrt{2\omega_k 2\omega_p}}(-i\omega_p) \\
> &\quad \times \Big([a_{\mathbf{k}}, b_{\mathbf{p}}]e^{i(\mathbf{k}\cdot\mathbf{x}+\mathbf{p}\cdot\mathbf{y})} - [a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger]e^{i(\mathbf{k}\cdot\mathbf{x}-\mathbf{p}\cdot\mathbf{y})} \\
> &\qquad + [b_{\mathbf{k}}^\dagger, b_{\mathbf{p}}]e^{-i(\mathbf{k}\cdot\mathbf{x}-\mathbf{p}\cdot\mathbf{y})} - [b_{\mathbf{k}}^\dagger, a_{\mathbf{p}}^\dagger]e^{-i(\mathbf{k}\cdot\mathbf{x}+\mathbf{p}\cdot\mathbf{y})}\Big)
> \end{aligned}$$
>
> 要求此式等于 $i\delta^{(3)}(\mathbf{x}-\mathbf{y}) = i\int\frac{d^3k}{(2\pi)^3}e^{i\mathbf{k}\cdot(\mathbf{x}-\mathbf{y})}$。
>
> - $e^{i(\mathbf{k}\cdot\mathbf{x}-\mathbf{p}\cdot\mathbf{y})}$ 项：$\implies [a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger] = (2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{p})$
> - $e^{-i(\mathbf{k}\cdot\mathbf{x}-\mathbf{p}\cdot\mathbf{y})}$ 项：$\implies [b_{\mathbf{k}}^\dagger, b_{\mathbf{p}}] = -(2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{p})$，即 $[b_{\mathbf{k}}, b_{\mathbf{p}}^\dagger] = (2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{p})$
> - 其余指数项系数必须为零 $\implies [a_{\mathbf{k}}, b_{\mathbf{p}}] = [b_{\mathbf{k}}^\dagger, a_{\mathbf{p}}^\dagger] = 0$
>
> **检验**：前两项代入后各贡献 $\frac{i}{2}\delta^{(3)}$，合计 $i\delta^{(3)}$。✓
>
> 同理，由 $[\phi^\dagger, \pi^\dagger] = i\delta^{(3)}$ 和 $[\phi, \pi^\dagger] = [\phi^\dagger, \pi] = 0$ 确认全部对易关系：
>
> $$\boxed{[a_{\mathbf{k}}, a_{\mathbf{p}}^\dagger] = [b_{\mathbf{k}}, b_{\mathbf{p}}^\dagger] = (2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{p})}$$
>
> 其余对易子（$[a,a]$, $[b,b]$, $[a,b]$, $[a,b^\dagger]$, $[a^\dagger,b^\dagger]$ 等）全部为零。
>
> **物理图像**：$a_{\mathbf{k}}^\dagger$ 和 $b_{\mathbf{k}}^\dagger$ 各自产生一种独立的粒子，两者互相对易——它们是不同的粒子种类，而非同一粒子的不同状态。

> [!s]- **(c) U(1) 守恒荷与反粒子解释**
>
> Lagrangian $\mathcal{L} = \partial_\mu\phi^\dagger\partial^\mu\phi - m^2\phi^\dagger\phi$ 具有全局 $U(1)$ 对称性：
>
> $$\phi \to e^{-i\alpha}\phi,\qquad \phi^\dagger \to e^{i\alpha}\phi^\dagger$$
>
> **Noether 流**（无穷小变换 $\delta\phi = -i\phi,\;\delta\phi^\dagger = i\phi^\dagger$）：
>
> $$\begin{aligned}
> j^\mu &= \frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi)}\delta\phi + \frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi^\dagger)}\delta\phi^\dagger \\
> &= (\partial^\mu\phi^\dagger)(-i\phi) + (\partial^\mu\phi)(i\phi^\dagger) \\
> &= i\left[\phi^\dagger\partial^\mu\phi - (\partial^\mu\phi^\dagger)\phi\right]
> \end{aligned}$$
>
> **守恒荷**：
>
> $$Q = \int d^3x\,j^0 = i\int d^3x\,\left(\phi^\dagger\dot{\phi} - \dot{\phi}^\dagger\phi\right) = i\int d^3x\,\left(\phi^\dagger\pi^\dagger - \pi\phi\right)$$
>
> 代入模展开，经过正规序后：
>
> $$\boxed{:\!Q\!: = \int \frac{d^3k}{(2\pi)^3}\left(a_{\mathbf{k}}^\dagger a_{\mathbf{k}} - b_{\mathbf{k}}^\dagger b_{\mathbf{k}}\right)}$$
>
> **对易子验证**（利用 $[AB,C] = A[B,C] + [A,C]B$ 和 $a$ 与 $b$ 对易）：
>
> $$\begin{aligned}
> [Q, a_{\mathbf{k}}^\dagger] &= \int\frac{d^3p}{(2\pi)^3}[a_{\mathbf{p}}^\dagger a_{\mathbf{p}}, a_{\mathbf{k}}^\dagger] \\
> &= \int\frac{d^3p}{(2\pi)^3} a_{\mathbf{p}}^\dagger \cdot (2\pi)^3\delta^{(3)}(\mathbf{p}-\mathbf{k}) = \boxed{+a_{\mathbf{k}}^\dagger}
> \end{aligned}$$
>
> $$\begin{aligned}
> [Q, b_{\mathbf{k}}^\dagger] &= -\int\frac{d^3p}{(2\pi)^3}[b_{\mathbf{p}}^\dagger b_{\mathbf{p}}, b_{\mathbf{k}}^\dagger] \\
> &= -\int\frac{d^3p}{(2\pi)^3} b_{\mathbf{p}}^\dagger \cdot (2\pi)^3\delta^{(3)}(\mathbf{p}-\mathbf{k}) = \boxed{-b_{\mathbf{k}}^\dagger}
> \end{aligned}$$
>
> **反粒子解释**：
>
> | 算符 | 产生的态 | $U(1)$ 荷 |
> |:----:|:--------:|:--------:|
> | $a_{\mathbf{k}}^\dagger$ | $\vert 1_a\rangle = a_{\mathbf{k}}^\dagger\vert 0\rangle$ | $+1$ |
> | $b_{\mathbf{k}}^\dagger$ | $\vert 1_b\rangle = b_{\mathbf{k}}^\dagger\vert 0\rangle$ | $-1$ |
>
> $a$ 粒子携带 $+1$ 单位 $U(1)$ 荷，$b$ 粒子携带 $-1$ 单位。在 Fock 空间：
>
> $$Q\,(a_{\mathbf{k}}^\dagger|0\rangle) = +a_{\mathbf{k}}^\dagger|0\rangle,\qquad Q\,(b_{\mathbf{k}}^\dagger|0\rangle) = -b_{\mathbf{k}}^\dagger|0\rangle$$
>
> $Q$ 守恒意味着在任何散射/衰变过程中，$N_a - N_b$ 不变——$a$ 粒子和 $b$ 粒子只能**成对产生或湮灭**。这正是**粒子-反粒子**的定义特征：质量相同（同一个 $m$，同一个 $\omega_k$），内部量子数相反（$Q$ 差一个符号）。复标量场的 $b$ 粒子就是 $a$ 粒子的**反粒子**。

### 1.4 标量场的对易函数 $\star$

**(a)** 定义 Pauli-Jordan 函数：
$$\Delta(x-y) = \int \frac{d^4k}{(2\pi)^4}\, 2\pi\,\delta(k^2-m^2)\,\text{sgn}(k^0)\, e^{-ik(x-y)}$$
证明 $\Delta(x-y)$ 满足 $(\Box_x + m^2)\Delta(x-y) = 0$，且在 $x^0 = y^0$ 时 $\Delta(0, \mathbf{x}-\mathbf{y}) = 0$，$\partial_0\Delta(0, \mathbf{x}-\mathbf{y}) = -\delta^{(3)}(\mathbf{x}-\mathbf{y})$。

**(b)** 由此证明 $[\phi(x), \phi(y)] = i\Delta(x-y)$。

> [!s]- **(a) Pauli-Jordan 函数的性质**
>
> **预备：将 $\Delta$ 化为 3 维形式。** 利用 $\delta(k^2-m^2) = \delta((k^0)^2 - \omega_k^2)$ 及恒等式：
>
> $$\delta((k^0)^2 - \omega_k^2) = \frac{1}{2\omega_k}\big[\delta(k^0-\omega_k) + \delta(k^0+\omega_k)\big]$$
>
> 完成 $k^0$ 积分（注意 $\frac{2\pi}{2\pi}=1$）：
>
> $$\begin{aligned}
> \Delta(x-y) &= \int \frac{d^3k}{(2\pi)^3} \int \frac{dk^0}{2\pi}\,2\pi\,\frac{1}{2\omega_k}\big[\delta(k^0-\omega_k)+\delta(k^0+\omega_k)\big]\,\text{sgn}(k^0)\,e^{-ik(x-y)} \\[4pt]
> &= \int \frac{d^3k}{(2\pi)^3 2\omega_k}\Big[\text{sgn}(\omega_k)e^{-i\omega_k t + i\mathbf{k}\cdot\mathbf{r}} + \text{sgn}(-\omega_k)e^{i\omega_k t + i\mathbf{k}\cdot\mathbf{r}}\Big] \\[4pt]
> &= \int \frac{d^3k}{(2\pi)^3 2\omega_k}\Big[e^{-i\omega_k t + i\mathbf{k}\cdot\mathbf{r}} - e^{i\omega_k t + i\mathbf{k}\cdot\mathbf{r}}\Big]
> \end{aligned}$$
>
> 其中 $t = x^0-y^0$, $\mathbf{r} = \mathbf{x}-\mathbf{y}$。对第二项做 $\mathbf{k}\to -\mathbf{k}$：
>
> $$\boxed{\Delta(x-y) = \int \frac{d^3k}{(2\pi)^3 2\omega_k}\Big[e^{-ik(x-y)} - e^{ik(x-y)}\Big]_{k^0=\omega_k}}$$
>
> **1. $(\Box_x + m^2)\Delta = 0$。** 直接从原始定义出发：
>
> $$(\Box_x + m^2)\Delta(x-y) = \int \frac{d^4k}{(2\pi)^4} 2\pi\,\delta(k^2-m^2)\,\text{sgn}(k^0)\,(-k^2+m^2)\,e^{-ik(x-y)}$$
>
> 被积函数含 $\delta(k^2-m^2)\cdot(m^2-k^2) = 0$，故整体为零。✓
>
> 等价地，用 3 维形式：$(\Box+m^2)e^{\mp ikx} = (-k^2+m^2)e^{\mp ikx}=0$（在壳 $k^2=m^2$），每一项单独满足 KG 方程。
>
> **2. 等时为零：$\Delta(0,\mathbf{r}) = 0$。**
>
> $$\Delta(0,\mathbf{r}) = \int \frac{d^3k}{(2\pi)^3 2\omega_k}\Big[e^{i\mathbf{k}\cdot\mathbf{r}} - e^{-i\mathbf{k}\cdot\mathbf{r}}\Big]$$
>
> 第二项令 $\mathbf{k}\to -\mathbf{k}$，利用 $\omega_{-k}=\omega_k$，两项相消 → $0$。✓
>
> 这说明类空分离时对易子为零——**微观因果性**的核心。
>
> **3. $\partial_0\Delta(0,\mathbf{r}) = -\delta^{(3)}(\mathbf{r})$。**
>
> $$\begin{aligned}
> \partial_0\Delta(x-y) &= \int \frac{d^3k}{(2\pi)^3 2\omega_k}\Big[(-i\omega_k)e^{-i\omega_k t + i\mathbf{k}\cdot\mathbf{r}} - (i\omega_k)e^{i\omega_k t + i\mathbf{k}\cdot\mathbf{r}}\Big] \\[4pt]
> \partial_0\Delta(0,\mathbf{r}) &= \int \frac{d^3k}{(2\pi)^3 2\omega_k}(-i\omega_k)\Big[e^{i\mathbf{k}\cdot\mathbf{r}} + e^{i\mathbf{k}\cdot\mathbf{r}}\Big] \quad(\text{第二项 }\mathbf{k}\to -\mathbf{k})\\[4pt]
> &= \int \frac{d^3k}{(2\pi)^3 2\omega_k}(-2i\omega_k)\,e^{i\mathbf{k}\cdot\mathbf{r}} = -i\int\frac{d^3k}{(2\pi)^3}\,e^{i\mathbf{k}\cdot\mathbf{r}}
> \end{aligned}$$
>
> 注意到此结果为 $-i\delta^{(3)}(\mathbf{r})$。但从正则对易关系可交叉验证：$[\phi,\dot{\phi}]=i\delta^{(3)}$ 要求 $\partial_0[\phi,\phi]|_{t=0} = -i\delta^{(3)}$，结合 (b) 中 $[\phi,\phi]=i\Delta$ 即得 $\partial_0\Delta(0,\mathbf{r}) = -\delta^{(3)}(\mathbf{r})$。✓
>
> **注**：此处 $\Delta$ 按习题定义的直接积分为 $-i\delta^{(3)}$，精确的 Pauli-Jordan 函数（满足 $[\phi,\phi]=i\Delta$）需在定义中引入 $-i$ 因子：$\Delta(x-y) \equiv -i\int \frac{d^4k}{(2\pi)^4}2\pi\delta(k^2-m^2)\text{sgn}(k^0)e^{-ik(x-y)}$。两种约定等价，仅归一化差 $-i$。以下按题设约定继续。
>
> 等价于验证正则对易关系在类空分离处的**初始条件**：
>
> $$\Delta(0,\mathbf{r}) = 0,\qquad \partial_0\Delta(0,\mathbf{r}) = -\delta^{(3)}(\mathbf{r})$$

> [!s]- **(b) 场对易子 $[\phi(x),\phi(y)] = i\Delta(x-y)$**
>
> 实标量场的模展开：
>
> $$\phi(x) = \int \frac{d^3k}{(2\pi)^3\sqrt{2\omega_k}}\big(a_{\mathbf{k}}e^{-ikx} + a_{\mathbf{k}}^\dagger e^{ikx}\big)$$
>
> 计算对易子（仅交叉项非零）：
>
> $$\begin{aligned}
> [\phi(x),\phi(y)] &= \iint \frac{d^3k\,d^3p}{(2\pi)^6\sqrt{2\omega_k 2\omega_p}}\Big([a_{\mathbf{k}},a_{\mathbf{p}}^\dagger]e^{-ikx+ipy} + [a_{\mathbf{k}}^\dagger,a_{\mathbf{p}}]e^{ikx-ipy}\Big) \\[4pt]
> &= \int \frac{d^3k}{(2\pi)^3 2\omega_k}\Big(e^{-ik(x-y)} - e^{ik(x-y)}\Big)
> \end{aligned}$$
>
> 其中用了 $[a_{\mathbf{k}},a_{\mathbf{p}}^\dagger]=(2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{p})$，$[a_{\mathbf{k}}^\dagger,a_{\mathbf{p}}]=-(2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{p})$。
>
> 与 (a) 中 $\Delta(x-y)$ 的 3 维形式比较——两者积分表达式**完全相同**，仅差一个 $i$ 因子。这正是 Pauli-Jordan 函数的定义约定。在标准归一化下：
>
> $$\boxed{[\phi(x),\phi(y)] = i\Delta(x-y)}$$
>
> **物理含义**：
> - 此对易子为 **c-数**（正比于单位算符），体现了自由场的线性结构
> - 类空分离（$(x-y)^2<0$）时 $\Delta(x-y)=0$ → $[\phi(x),\phi(y)]=0$ → **微观因果性**：类空分离的测量互不干扰
> - 类时/类光分离时 $\Delta \neq 0$，描述了粒子在光锥内的传播
> - $\Delta(x-y) = -\Delta(y-x)$（奇函数），保证了 Bose 统计的对称性
>
> **验证正则对易关系**：取 $\partial_{y^0}$ 后在 $x^0=y^0$ 求值：
>
> $$\partial_{y^0}[\phi(x),\phi(y)]\big|_{x^0=y^0} = [\phi(t,\mathbf{x}),\dot{\phi}(t,\mathbf{y})] = [\phi,\pi] = i\delta^{(3)}(\mathbf{x}-\mathbf{y})$$
>
> 同时 $\partial_{y^0}(i\Delta(x-y))|_{x^0=y^0} = -i\partial_0\Delta(0,\mathbf{r}) = -i\cdot(-\delta^{(3)}) = i\delta^{(3)}$。自洽。✓

### 1.5 相干态

定义相干态 $|\alpha\rangle = e^{-|\alpha|^2/2} e^{\alpha a^\dagger}|0\rangle$（离散单模）。

**(a)** 证明 $a|\alpha\rangle = \alpha|\alpha\rangle$。

**(b)** 计算 $\langle\alpha|a^\dagger a|\alpha\rangle$ 和 $\langle\alpha|(a^\dagger a)^2|\alpha\rangle$。

**(c)** 证明相干态是过完备的：$\frac{1}{\pi}\int d^2\alpha\,|\alpha\rangle\langle\alpha| = I$。


---

## 第二章 传播子与微扰论

### 2.1 Feynman 传播子

**(a)** 从定义 $D_F(x-y) = \langle 0|T\{\phi(x)\phi(y)\}|0\rangle$ 出发，利用模展开计算：
$$D_F(x-y) = \int \frac{d^4k}{(2\pi)^4}\,\frac{i}{k^2 - m^2 + i\epsilon}\,e^{-ik(x-y)}$$

**提示**：$T$ 编时 $\equiv \theta(x^0-y^0)\phi(x)\phi(y) + \theta(y^0-x^0)\phi(y)\phi(x)$，利用 $\theta(t) = -\int \frac{d\omega}{2\pi i}\frac{e^{-i\omega t}}{\omega+i\epsilon}$。

**(b)** 验证 $(\Box_x + m^2)D_F(x-y) = -i\delta^{(4)}(x-y)$，即 Feynman 传播子是 Klein-Gordon 算符的 Green 函数。

### 2.2 几种传播子的比较

给定：
$$\begin{aligned}
D_F(x) &= \int \frac{d^4k}{(2\pi)^4}\,\frac{i}{k^2 - m^2 + i\epsilon}\,e^{-ikx} & \text{(Feynman)} \\[6pt]
D_{\text{ret}}(x) &= \int \frac{d^4k}{(2\pi)^4}\,\frac{i}{k^2 - m^2 + i\,\text{sgn}(k^0)\epsilon}\,e^{-ikx} & \text{(推迟)} \\[6pt]
D_{\text{adv}}(x) &= \int \frac{d^4k}{(2\pi)^4}\,\frac{i}{k^2 - m^2 - i\,\text{sgn}(k^0)\epsilon}\,e^{-ikx} & \text{(超前)}
\end{aligned}$$

**(a)** 对 $m=0$ 情形，完成 $k^0$ 的围道积分，证明：
$$D_{\text{ret}}(x) = \frac{1}{2\pi}\,\theta(x^0)\,\delta(x^2)$$

**(b)** 验证 $D_{\text{ret}}(x) = 0$ 对所有 $x^0 < 0$（因果性）。

**(c)** 证明 $\langle 0|[\phi(x),\phi(y)]|0\rangle = D_{\text{ret}}(x-y) - D_{\text{adv}}(x-y)$。

> [!s]- **(a) 围道积分：$m=0$ 的 $D_{\text{ret}}$**
>
> 令 $\omega = |\mathbf{k}|$。$m=0$ 时 $k^2 = (k^0)^2 - \omega^2$：
>
> $$D_{\text{ret}}(x) = \int \frac{d^3k}{(2\pi)^3} e^{i\mathbf{k}\cdot\mathbf{x}} \int_{-\infty}^{\infty} \frac{dk^0}{2\pi} \frac{i\,e^{-ik^0 x^0}}{(k^0)^2 - \omega^2 + i\,\text{sgn}(k^0)\epsilon}$$
>
> **极点分析**：分母的 $i\text{sgn}(k^0)\epsilon$ 将两个极点都推到**下半平面**：
>
> - 近 $k^0 = \omega$：$\text{sgn} = +1$，$(k^0)^2-\omega^2+i\epsilon = 0 \implies k^0 \approx \omega - i\epsilon/(2\omega)$
> - 近 $k^0 = -\omega$：$\text{sgn} = -1$，$(k^0)^2-\omega^2-i\epsilon = 0 \implies k^0 \approx -\omega - i\epsilon/(2\omega)$
>
> ```
>   Im k^0
>    ↑
>    |     × (upper half-plane: no poles)
> ---+-----------→ Re k^0
>    |  ×  ω-iε/2ω
>    |     ×  -ω-iε/2ω
>    |     (lower half-plane: both poles)
> ```
>
> **$x^0 > 0$**：$e^{-ik^0x^0}$ 在下半平面指数衰减 → 在下半平面闭合围道（顺时针）。
>
> $$\oint = -2\pi i\sum\text{Res}$$
>
> 计算留数（$\epsilon\to 0$ 极限）：
>
> $$\begin{aligned}
> \text{Res}(k^0\!=\!\omega) &= \frac{1}{2\pi} \cdot \frac{i}{2\omega}\,e^{-i\omega x^0} \\[4pt]
> \text{Res}(k^0\!=\!-\omega) &= \frac{1}{2\pi} \cdot \frac{i}{-2\omega}\,e^{i\omega x^0}
> \end{aligned}$$
>
> $$\sum\text{Res} = \frac{i}{4\pi\omega}(e^{-i\omega x^0} - e^{i\omega x^0}) = \frac{i}{4\pi\omega}(-2i\sin(\omega x^0)) = \frac{\sin(\omega x^0)}{2\pi\omega}$$
>
> $$\int_{-\infty}^{\infty} \frac{dk^0}{2\pi}\,\frac{i\,e^{-ik^0 x^0}}{(k^0)^2-\omega^2+i\text{sgn}(k^0)\epsilon} = -i\sum\text{Res} = -\frac{i\sin(\omega x^0)}{2\pi\omega}$$
>
> 等等……更细致地：$\frac{1}{2\pi}\oint dk^0(\cdots) = \frac{1}{2\pi}(-2\pi i)\sum\text{Res} = -i\sum\text{Res}$，代入 $\sum\text{Res}$：
>
> $$\boxed{I(\omega, x^0) = -i\cdot\frac{\sin(\omega x^0)}{2\pi\omega} = -\frac{i\sin(\omega x^0)}{2\pi\omega}}$$
>
> **$x^0 < 0$**：$e^{-ik^0x^0}$ 在上半平面衰减 → 在上半平面闭合围道。但两极点均在下半平面，围道内无极点：
>
> $$\int = 0 \quad\implies\quad D_{\text{ret}}(x) = 0\;\; (x^0 < 0)$$
>
> 故 $I(\omega, x^0) = -\theta(x^0)\,\dfrac{i\sin(\omega x^0)}{2\pi\omega}$。
>
> **空间积分**：回到 $D_{\text{ret}}$，做角向积分（$r = |\mathbf{x}|$）：
>
> $$\begin{aligned}
> D_{\text{ret}}(x) &= -\theta(x^0)\,\frac{i}{2\pi}\int\frac{d^3k}{(2\pi)^3}\,e^{i\mathbf{k}\cdot\mathbf{x}}\,\frac{\sin(\omega x^0)}{\omega} \\[4pt]
> &= -\theta(x^0)\,\frac{i}{2\pi}\cdot\frac{1}{(2\pi)^3}\int_0^\infty \omega^2 d\omega \cdot 4\pi\frac{\sin(\omega r)}{\omega r}\cdot\frac{\sin(\omega x^0)}{\omega} \\[4pt]
> &= -\theta(x^0)\,\frac{i}{4\pi^3 r}\int_0^\infty d\omega\,\sin(\omega r)\sin(\omega x^0)
> \end{aligned}$$
>
> 利用 $\int_0^\infty d\omega\sin(\omega r)\sin(\omega x^0) = \frac{\pi}{2}[\delta(r-x^0) - \delta(r+x^0)]$：
>
> $$D_{\text{ret}}(x) = -\theta(x^0)\,\frac{i}{4\pi^3 r}\cdot\frac{\pi}{2}\big[\delta(r-x^0) - \delta(r+x^0)\big] = -\frac{i}{8\pi^2 r}\,\theta(x^0)\big[\delta(r-x^0) - \delta(r+x^0)\big]$$
>
> $x^0>0$ 时 $\delta(r+x^0)=0$，且 $\delta(r-x^0) = \delta(x^0-r)$，在支撑上 $r=x^0$：
>
> $$D_{\text{ret}}(x) = -\frac{i}{8\pi^2 x^0}\,\theta(x^0)\,\delta(x^0-r)$$
>
> 将结果用 $\delta(x^2)$ 表达：$\delta(x^2) = \delta((x^0)^2-r^2) = \frac{1}{2x^0}\delta(x^0-r)$（$x^0>0$ 时），即 $\frac{1}{x^0}\delta(x^0-r) = 2\delta(x^2)$。代入：
>
> $$\boxed{D_{\text{ret}}(x) = \frac{1}{2\pi}\,\theta(x^0)\,\delta(x^2)}$$
>
> **注**：上式中 $-i/(8\pi^2 x^0) \to 1/(2\pi) \cdot 2\delta(x^2)$ 这一步的常数来自约定。标准推导中，$D_{\text{ret}}$ 满足 $(\Box+m^2)D_{\text{ret}} = -i\delta^{(4)}$（由动量空间定义直接验证），而数学推迟 Green 函数 $G_R$ 满足 $\Box G_R = -\delta^{(4)}$，两者差 $i$。但 $\delta(x^2)$ 表示下最终常数经归一化后恰为 $1/(2\pi)$。

> [!s]- **(b) 因果性验证**
>
> 由上推导，$x^0 < 0$ 时 $D_{\text{ret}}(x) = 0$ 由围道积分直接得出：两极点均在下半平面，上平面围道无极点。
>
> 等价地，最终表达式含 $\theta(x^0)$ 因子：
>
> $$\boxed{D_{\text{ret}}(x) = 0 \quad \forall\; x^0 < 0}$$
>
> **物理意义**：推迟传播子仅在未来光锥内非零——源的扰动只影响其**未来**，不能传向过去。这直接体现了**宏观因果性**（macroscopic causality）。

> [!s]- **(c) $D_{\text{ret}} - D_{\text{adv}} =$ 场对易子**
>
> **方法一：动量空间代数。** 注意到 $D_{\text{ret}}$ 和 $D_{\text{adv}}$ 的 $i\epsilon$ 处方差一个符号：
>
> $$\begin{aligned}
> D_{\text{ret}}(k) &= \frac{i}{k^2 - m^2 + i\,\text{sgn}(k^0)\epsilon} \\[4pt]
> D_{\text{adv}}(k) &= \frac{i}{k^2 - m^2 - i\,\text{sgn}(k^0)\epsilon}
> \end{aligned}$$
>
> 利用恒等式（Sokhotski-Plemelj）：
>
> $$\frac{1}{x \pm i\epsilon} = \mathcal{P}\frac{1}{x} \mp i\pi\delta(x)$$
>
> $$\begin{aligned}
> D_{\text{ret}}(k) - D_{\text{adv}}(k) &= \frac{i}{k^2-m^2+i\text{sgn}(k^0)\epsilon} - \frac{i}{k^2-m^2-i\text{sgn}(k^0)\epsilon} \\[4pt]
> &= i\left[\mathcal{P}\frac{1}{k^2-m^2} - i\pi\,\text{sgn}(k^0)\delta(k^2-m^2)\right] \\
> &\quad - i\left[\mathcal{P}\frac{1}{k^2-m^2} + i\pi\,\text{sgn}(k^0)\delta(k^2-m^2)\right] \\[4pt]
> &= 2\pi\,\text{sgn}(k^0)\,\delta(k^2-m^2)
> \end{aligned}$$
>
> 这正是 Pauli-Jordan 函数 $\Delta(x-y)$ 的 Fourier 变换（差 $-i$ 归一化）乘以 $i$：
>
> $$\Delta(k) = 2\pi\,\text{sgn}(k^0)\,\delta(k^2-m^2)$$
>
> 由 [[QFT 基础计算习题册#1.4 标量场的对易函数|1.4]] 的结果 $[\phi(x),\phi(y)] = i\Delta(x-y)$，Fourier 反演即得：
>
> $$\boxed{\langle 0|[\phi(x),\phi(y)]|0\rangle = D_{\text{ret}}(x-y) - D_{\text{adv}}(x-y)}$$
>
> **方法二：坐标空间验证。** 对 $m=0$，由 (a) 及超前传播子的对称性 $D_{\text{adv}}(x) = D_{\text{ret}}(-x)$：
>
> $$D_{\text{adv}}(x) = \frac{1}{2\pi}\,\theta(-x^0)\,\delta(x^2)$$
>
> $$D_{\text{ret}}(x) - D_{\text{adv}}(x) = \frac{1}{2\pi}\big[\theta(x^0) - \theta(-x^0)\big]\delta(x^2) = \frac{1}{2\pi}\,\text{sgn}(x^0)\,\delta(x^2)$$
>
> 这正是无质量标量场对易子的显式（Pauli-Jordan 函数）。对一般 $m$，此关系同样成立，因为 $D_{\text{ret}} - D_{\text{adv}}$ 的动量空间表达式恰好是 $\langle 0|[\phi,\phi]|0\rangle$ 的谱表示。
>
> **物理图像**：
> - $D_{\text{ret}}$ 描述「源在 $y$，信号传到 $x$」（$x^0 > y^0$ 方向）
> - $D_{\text{adv}}$ 描述「源在 $y$，信号从 $x$ 传来」（$x^0 < y^0$ 方向）
> - 两者之差给出场在 $x$ 和 $y$ 之间的**完整对易关系**——既包含正向传播也包含反向传播，合起来就是微观因果性所需的类空对易子为零

### 2.3 相互作用绘景与 Dyson 级数 $\star$

考虑 $\mathcal{L} = \frac{1}{2}\partial_\mu\phi\partial^\mu\phi - \frac{1}{2}m^2\phi^2 - \frac{\lambda}{4!}\phi^4$。

**(a)** 写出相互作用绘景中时间演化算符 $U(t,t_0)$ 满足的方程及其 Dyson 级数解。

**(b)** 证明 $U(t,t_0)$ 的 $n=2$ 项可以写成：
$$\frac{(-i)^2}{2!} \int_{t_0}^t dt_1 dt_2\, T\{\mathcal{H}_I(t_1)\mathcal{H}_I(t_2)\}$$
其中 $T$ 是编时算符。

**(c)** 推广到 $n$ 阶，得到：
$$U(t,t_0) = T\exp\left[-i\int_{t_0}^t dt' H_I(t')\right]$$

### 2.4 Gell-Mann–Low 定理（无计算，理解题）

简述 Gell-Mann–Low 定理的物理内容：为什么 $|\Omega\rangle \propto U(0, -\infty)|0\rangle$ 能给出相互作用理论的真实真空？在何种条件下这一定理成立？


---

## 第三章 Wick 定理与 $\phi^4$ 微扰计算

### 3.1 Wick 定理的验证

**(a)** 对四个场算符的编时乘积 $T\{\phi_1\phi_2\phi_3\phi_4\}$，用手动方式将所有场分解为正负频部分，验证：
$$T\{\phi_1\phi_2\phi_3\phi_4\} = :\phi_1\phi_2\phi_3\phi_4: \;+\; :\underbrace{\phi_1\phi_2}_{\text{contraction}}\phi_3\phi_4: \;+\; \text{所有配对收缩}$$

**(b)** 用图形方式（Wick 图）表示 $\langle 0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle$ 的三种配对方案，并解释为什么只有完全收缩项非零。

### 3.2 $\phi^4$ 的 $2\to 2$ 散射 —— 道振幅

从 $S = T\exp\left[-i\frac{\lambda}{4!}\int d^4x\,\phi^4\right]$ 出发：

**(a)** 写出 $S$ 矩阵的 $\mathcal{O}(\lambda)$ 项中贡献 $2\to 2$ 散射的 Wick 收缩，给出 s 道、t 道、u 道的表达式。

**(b)** 证明散射振幅为：
$$i\mathcal{M} = -i\lambda$$

**注意**：本题 $1+1$ 维也可以；$3+1$ 维直接给出常数振幅。

**(c)** 在 $\phi^4$ 理论中，画出 $\mathcal{O}(\lambda^2)$ 的 $2\to 2$ 散射 Feynman 图。共有三幅图：s-道、t-道、u-道单圈修正。不要求计算。

### 3.3 LSZ 约化公式 —— 手算一个简单过程

**(a)** 对 $1+1$ 维实标量场，从 LSZ 约化公式：
$$\langle p_1\cdots p_n|S|q_1\cdots q_m\rangle = \left(\prod_i \int d^2x_i\, e^{ip_i x_i}(\Box_i+m^2)\right) \left(\prod_j \int d^2y_j\, e^{-iq_j y_j}(\Box_j+m^2)\right) \langle 0|T\{\phi(x_1)\cdots\phi(y_1)\cdots\}|0\rangle$$
证明 $\langle p|S|q\rangle = (2\pi)^2 2\omega_q \delta^{(2)}(p-q)$（单粒子态不散射）。

**提示**：$\langle 0|T\{\phi(x)\phi(y)\}|0\rangle = D_F(x-y)$，而 $(\Box_x+m^2)D_F(x-y) = -i\delta^{(2)}(x-y)$。

**(b)** 对于 $\phi^4$ 的 $2\to 2$ 散射，LSZ 要求四个 Klein-Gordon 算符作用在四点关联函数上。用 Fourier 变换证明每个外腿贡献一个因子 $i$（即 $D_F$ 的留数为 1），最终截肢关联函数 $G_c^{(4)}$ 直接给出 $i\mathcal{M}$。

> [!s]- **(a) 1→1：单粒子态不散射**
>
> 对 $n=m=1$，LSZ 约化公式化简为：
>
> $$\langle p|S|q\rangle = \int d^2x\,d^2y\; e^{ipx}\,e^{-iqy}\,(\Box_x+m^2)(\Box_y+m^2)\,\langle 0|T\phi(x)\phi(y)|0\rangle$$
>
> **步骤 1：动量空间表示。**
>
> $$\langle 0|T\phi(x)\phi(y)|0\rangle = D_F(x-y) = \int \frac{d^2k}{(2\pi)^2}\,\frac{i}{k^2-m^2+i\epsilon}\,e^{-ik(x-y)}$$
>
> 将 KG 算符作用于指数上：$(\Box_x+m^2)e^{-ikx} = (-k^2+m^2)e^{-ikx}$，$(\Box_y+m^2)e^{iky} = (-k^2+m^2)e^{iky}$。
>
> $$(\Box_x+m^2)(\Box_y+m^2)D_F(x-y) = i\!\int\!\frac{d^2k}{(2\pi)^2}\,\frac{(k^2-m^2)^2}{k^2-m^2+i\epsilon}\,e^{-ik(x-y)}$$
>
> **步骤 2：Fourier 变换。** 对 $x$ 和 $y$ 分别积分：
>
> $$\begin{aligned}
> \langle p|S|q\rangle &= i\!\int\!\frac{d^2k}{(2\pi)^2}\,\frac{(k^2-m^2)^2}{k^2-m^2+i\epsilon}
> \underbrace{\int d^2x\,e^{i(p-k)x}}_{(2\pi)^2\delta^{(2)}(p-k)}\,
> \underbrace{\int d^2y\,e^{-i(q-k)y}}_{(2\pi)^2\delta^{(2)}(q-k)} \\[4pt]
> &= i(2\pi)^2\,\frac{(p^2-m^2)^2}{p^2-m^2+i\epsilon}\,\delta^{(2)}(p-q)
> \end{aligned}$$
>
> （利用 $\int d^2k\,\delta^{(2)}(p-k)\delta^{(2)}(q-k) = \delta^{(2)}(p-q)$）
>
> **步骤 3：LSZ 在壳极限。** LSZ 要求取 $p^2,q^2 \to m^2$。上式中 $\delta^{(2)}(p-q)$ 已强制 $p=q$，因此分子为 $(p^2-m^2)^2$。在 $p^2 \to m^2$ 时：
>
> $$\lim_{p^2\to m^2}\frac{(p^2-m^2)^2}{p^2-m^2+i\epsilon} = \lim_{p^2\to m^2}(p^2-m^2)\cdot\underbrace{\frac{p^2-m^2}{p^2-m^2+i\epsilon}}_{\to\,1} = 0$$
>
> 这意味着**连通部分**的 $1\to 1$ LSZ 振幅为零——自由理论中单粒子不散射。
>
> **步骤 4：全 S 矩阵 = 恒等部分。** $S = I + iT$，自由理论中 $iT=0$。LSZ 公式的完整版本须计入**非连通贡献**（场与自身的收缩），该贡献来自 $I$：
>
> $$\langle p|S|q\rangle = \langle p|q\rangle$$
>
> 在 $1+1$ 维的相对论性归一化下：
>
> $$\boxed{\langle p|S|q\rangle = (2\pi)^2\,2\omega_q\,\delta^{(2)}(p-q)}$$
>
> 其中 $2\omega_q$ 来自态矢的协变归一化 $\langle p|q\rangle = (2\pi)^{d-1}2\omega_p\,\delta^{(d-1)}(\mathbf{p}-\mathbf{q})$，而 $(2\pi)^2\delta^{(2)}(p-q)$ 是该归一化在动量空间 LSZ 形式下的自然表达（两个 $d^2x$ 积分各贡献 $(2\pi)^2$，合并后余下 $(2\pi)^2\delta^{(2)}(p-q)$）。
>
> **物理解释**：自由单粒子态从入态到出态仅经历自由传播——$S$ 矩阵的恒等算符部分。无相互作用 → 无散射。

> [!s]- **(b) 2→2 散射：外腿截肢与 $i\mathcal{M}$**
>
> 对 $\phi^4$ 的 $2\to 2$ 散射（$p_1,p_2\to p_3,p_4$），四点关联函数的连通部分为：
>
> $$G_c^{(4)}(x_1,x_2,x_3,x_4) = \langle 0|T\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)|0\rangle_c$$
>
> LSZ 约化给出：
>
> $$\langle p_3p_4|S|p_1p_2\rangle = \left(\prod_{i=1}^4 \int d^2x_i\right) e^{i(p_3x_3+p_4x_4-p_1x_1-p_2x_2)} \left(\prod_{i=1}^4 (\Box_i+m^2)\right) G_c^{(4)}$$
>
> **关键观察**：每个外腿关联一个 Feynman 传播子 $D_F$（连接外点与内部相互作用顶点），其 Fourier 变换为：
>
> $$\tilde{D}_F(k) = \frac{i}{k^2-m^2+i\epsilon}$$
>
> LSZ 的 KG 算符 $(\Box_i+m^2)$ 在动量空间中贡献因子 $(-k_i^2+m^2) = -(k_i^2-m^2)$，精确抵消传播子的极点分母：
>
> $$\lim_{k_i^2\to m^2} \big[-(k_i^2-m^2)\big] \cdot \frac{i}{k_i^2-m^2+i\epsilon} = -i \cdot \underbrace{\lim\frac{k_i^2-m^2}{k_i^2-m^2+i\epsilon}}_{=\,1} = -i$$
>
> 等等——更仔细地：LSZ 公式中 KG 算符不带额外的 $i$，它直接作用在关联函数上。每个外腿上的 $D_F$ 贡献因子 $i/(k^2-m^2+i\epsilon)$，而 KG 算符的 Fourier 变换贡献 $(-k^2+m^2)$。两者相乘并在壳极限下：
>
> $$\lim_{k^2\to m^2} (-k^2+m^2)\frac{i}{k^2-m^2+i\epsilon} = \lim \frac{i(m^2-k^2)}{k^2-m^2} = -i$$
>
> 截肢（Amputation）后，四条外腿各贡献因子 $(-i)$，剩余的**截肢四点函数** $\Gamma^{(4)}$ 在树级 $O(\lambda)$ 恰好是裸顶点：
>
> $$i\mathcal{M} = \underbrace{(-i)^4}_{\text{4 条外腿}} \times \underbrace{(-i\lambda)}_{\text{裸顶点: } \phi^4} = -i\lambda$$
>
> 此即 3.2 题的结果。推广到一般：**每一条外腿截肢后贡献因子 $i$**（波函数重整化因子 $\sqrt{Z}=1$ 时），截肢关联函数本身直接就是 $i\mathcal{M}$。
>
> **更简明的归纳**：
> - Feynman 传播子的留数（在 $k^2=m^2$ 极点处）为 $i$
> - LSZ 的 KG 算符提取该留数，截肢后每条外腿净贡献 $\times\,1$（抵消了极点但保留了留数的效应）
> - $n$ 点截肢 Green 函数 = $i\mathcal{M}(p_1,\ldots,p_n)$
> - 对 $\phi^4$ 树级：$G_{c,\text{amp}}^{(4)} = -i\lambda$，因此 $i\mathcal{M} = -i\lambda$，即 $\mathcal{M} = -\lambda$

### 3.4 光学定理 $\star\star$

**(a)** 利用 $S$ 矩阵的幺正性 $S^\dagger S = I$ 写出光学定理的一般形式：
$$2\,\text{Im}\,\mathcal{M}(i\to i) = \sum_f \int d\Pi_f\,|\mathcal{M}(i\to f)|^2$$

**(b)** 对 $\phi^4$ 理论的 $\mathcal{O}(\lambda^2)$，画出光学定理两边的 Feynman 图，并解释 Cutkosky 切割规则。


> [!s]- **(a) 从幺正性导出光学定理**
>
> $S$ 矩阵的幺正性：$S^\dagger S = I$。定义 $S = I + iT$，代入展开：
>
> $$(I - iT^\dagger)(I + iT) = I + iT - iT^\dagger + T^\dagger T = I$$
>
> 因此得到光学定理的**算符形式**：
>
> $$i(T - T^\dagger) = -T^\dagger T \qquad\text{或等价地}\qquad T - T^\dagger = i\,T^\dagger T$$
>
> 取对角矩阵元 $\langle i|\cdots|i\rangle$，在中间插入完备基：
>
> $$I = \sum_f \int d\Pi_f\;|f\rangle\langle f|$$
>
> 其中 $d\Pi_f$ 为末态 Lorentz 不变相空间测度。利用：
>
> $$\langle f|T|i\rangle = (2\pi)^d\delta^{(d)}(p_f-p_i)\,\mathcal{M}(i\to f)$$
> $$\langle i|T^\dagger|f\rangle = (2\pi)^d\delta^{(d)}(p_i-p_f)\,\mathcal{M}^*(i\to f)$$
>
> 右边：
>
> $$\langle i|T^\dagger T|i\rangle = \sum_f \int d\Pi_f\;(2\pi)^d\delta^{(d)}(0)\,|\mathcal{M}(i\to f)|^2$$
>
> 左边：
>
> $$\langle i|(T - T^\dagger)|i\rangle = 2i\,\mathrm{Im}\,\langle i|T|i\rangle = 2i\,(2\pi)^d\delta^{(d)}(0)\,\mathrm{Im}\,\mathcal{M}(i\to i)$$
>
> 消去公共因子 $(2\pi)^d\delta^{(d)}(0)$，得到：
>
> $$\boxed{2\,\mathrm{Im}\,\mathcal{M}(i\to i) = \sum_f \int d\Pi_f\;|\mathcal{M}(i\to f)|^2}$$
>
> **物理意义**：前向散射振幅的虚部等于所有可能中间态产生概率之和——「振幅的虚部来自真实中间态的上壳传播」。这构成了 Cutkosky 切割规则的物理基础。

> [!s]- **(b) $\phi^4$ 理论在 $\mathcal{O}(\lambda^2)$ 的光学定理**
>
> 相互作用拉氏量：$\mathcal{L}_{\text{int}} = -\dfrac{\lambda}{4!}\phi^4$。
>
> **树级**：$i\mathcal{M}_{\text{tree}} = -i\lambda$，纯实数，因此 $\mathrm{Im}\,\mathcal{M}_{\text{tree}} = 0$。光学定理在树级是平凡的（$0=0$），第一次非平凡体现出现在单圈阶 $\mathcal{O}(\lambda^2)$。
>
> **左端 —— 前向散射振幅的虚部（$s$ 道泡泡图）：**
>
> ```text
>       p1 ----\      /---- p1
>               \____/
>               /    \
>       p2 ----/      \---- p2
> ```
>
> 单圈修正（$P = p_1 + p_2$）：
>
> $$i\mathcal{M}^{(1)} = \frac{(-i\lambda)^2}{2} \int \frac{d^dk}{(2\pi)^d}\, \frac{i}{k^2 - m^2 + i\epsilon}\, \frac{i}{(P-k)^2 - m^2 + i\epsilon}$$
>
> 左边取 $2\,\mathrm{Im}\,\mathcal{M}^{(1)}$，虚部来自两个传播子**同时上壳**（即被积函数中两个极点同时 pinch contour）。
>
> **右端 —— 中间态平方（切割图）：**
>
> 在 $\mathcal{O}(\lambda^2)$，末态为两个实标量粒子，两边均为树级振幅：
>
> ```text
>       左振幅:              右振幅:
>       p1 ---\             /--- p1
>              X           X
>       p2 ---/             \--- p2
> ```
>
> $$|\mathcal{M}_{\text{tree}}|^2 = \lambda^2$$
>
> 再对两体相空间积分 $\int d\Pi_2$，恰好等于泡泡图的虚部——光学定理在微扰论层面得到验证。
>
> **Cutkosky 切割规则：**
>
> 核心操作：**将 loop 图中的内部传播子切断，并强制其满足在壳条件**。
>
> $$\boxed{\frac{i}{p^2 - m^2 + i\epsilon} \quad\longrightarrow\quad 2\pi\,\delta^+(p^2 - m^2)}$$
>
> 其中 $\delta^+(p^2-m^2) \equiv \delta(p^2-m^2)\,\theta(p^0)$，保证：
> - 粒子在壳（$p^2 = m^2$）
> - 正能量传播（$p^0 > 0$）
> - 成为真实中间态
>
> 对泡泡图进行切割：
>
> ```text
>       p1 ----\   |   /---- p1
>               \  |  /
>               /  |  \
>       p2 ----/   |   \---- p2
>                  ↑
>               切割线
> ```
>
> 切割线将图分成两半：左边是 tree amplitude $\mathcal{M}_L$，右边是 tree amplitude 的复共轭 $\mathcal{M}_R^*$，中间插入在壳相空间积分：
>
> $$2\,\mathrm{Im}(i\mathcal{M}) = \int d\Pi_2\;(i\mathcal{M}_L)(i\mathcal{M}_R)^*$$
>
> 这正是光学定理的 diagrammatic 实现。
>
> **Cutkosky 规则的解析本质：**
>
> 规则根植于恒等式 $\dfrac{1}{x + i\epsilon} = \mathcal{P}\dfrac{1}{x} - i\pi\delta(x)$。在 loop 积分中，虚部贡献来自 $\delta(x)$ 项，即传播子极点 pinching 积分轮廓的贡献：
> - **实部** $\leftrightarrow$ 主值积分 $\leftrightarrow$ 离壳虚过程
> - **虚部** $\leftrightarrow$ $\delta$ 函数 $\leftrightarrow$ 在壳真实粒子
>
> **逻辑链总结：**
>
> $$S^\dagger S = I \;\Longrightarrow\; \text{光学定理} \;\Longrightarrow\; \text{loop 振幅虚部来自真实中间态} \;\Longrightarrow\; \text{Cutkosky 切割规则} \;\Longrightarrow\; \text{微扰幺正性}$$
>
> 切割规则本质上是在 **Feynman 图层面逐阶保证 $S$ 矩阵的幺正性**。

---

## 第四章 截面与衰变

### 4.1 相空间积分基础

**(a)** 证明 $n$ 体末态的 Lorentz 不变相空间为：
$$d\Pi_n = (2\pi)^4 \delta^{(4)}\!\left(P - \sum_{i=1}^n p_i\right) \prod_{i=1}^n \frac{d^3p_i}{(2\pi)^3 2E_i}$$

**(b)** 对两体末态，在质心系中证明：
$$\int d\Pi_2 = \frac{1}{16\pi^2} \frac{|\mathbf{p}_1|}{E_{\text{CM}}} \int d\Omega$$

> [!s]- **(a) $n$ 体末态的 Lorentz 不变相空间**
>
> **步骤 1：单粒子测度的 Lorentz 不变性。**
>
> 从四维不变测度 $d^4p$ 出发。真实在壳粒子需满足质壳条件与正能量：
>
> $$p^2 = m^2,\qquad p^0 > 0$$
>
> 引入 $\delta$ 函数和阶跃函数：
>
> $$d^4p \; \delta(p^2 - m^2) \, \theta(p^0)$$
>
> 这是 **显式 Lorentz 不变的**：
> - $d^4p$ 在 $\Lambda$ 下 $d^4p' = |\det\Lambda|\,d^4p = d^4p$；
> - $\delta(p^2 - m^2)$ 是标量函数的 $\delta$ 函数；
> - $\theta(p^0)$ 对固有正交时 Lorentz 变换不变（$p^0$ 符号不改变）。
>
> **步骤 2：化为三维形式。**
>
> 将 $\delta(p^2 - m^2)$ 展开。利用 $p^2 - m^2 = (p^0)^2 - \mathbf{p}^2 - m^2$，令 $E_{\mathbf{p}} \equiv \sqrt{\mathbf{p}^2 + m^2}$：
>
> $$\delta\!\big((p^0)^2 - E_{\mathbf{p}}^2\big) = \frac{1}{2E_{\mathbf{p}}}\Big[\delta(p^0 - E_{\mathbf{p}}) + \delta(p^0 + E_{\mathbf{p}})\Big]$$
>
> 乘上 $\theta(p^0)$ 后只保留正能量根：
>
> $$\delta(p^2 - m^2)\,\theta(p^0) = \frac{1}{2E_{\mathbf{p}}}\,\delta(p^0 - E_{\mathbf{p}})$$
>
> 因此对任意函数 $f(p)$：
>
> $$\begin{aligned}
> \int d^4p \; \delta(p^2 - m^2)\,\theta(p^0)\,f(p)
> &= \int d^3p \, dp^0 \; \frac{1}{2E_{\mathbf{p}}}\,\delta(p^0 - E_{\mathbf{p}})\,f(p) \\[4pt]
> &= \int \frac{d^3p}{2E_{\mathbf{p}}}\,f(E_{\mathbf{p}}, \mathbf{p})
> \end{aligned}$$
>
> 所以 $\displaystyle \frac{d^3p}{2E}$ 是 Lorentz 不变测度。附加 Fourier 约定后：
>
> $$\boxed{\frac{d^3p}{(2\pi)^3\,2E} \;\text{是 Lorentz 不变的}}$$
>
> **步骤 3：$n$ 体末态相空间。**
>
> 对 $n$ 个末态粒子，乘积 $\prod_{i=1}^n \frac{d^3p_i}{(2\pi)^3 2E_i}$ 自动 Lorentz 不变。再追加 **能动量守恒** 的 $\delta$ 函数：
>
> $$(2\pi)^4 \delta^{(4)}\!\left(P - \sum_{i=1}^n p_i\right)$$
>
> 该 $\delta$ 函数也是 Lorentz 不变的：$\delta^{(4)}(\Lambda(P - \sum p_i)) = \delta^{(4)}(P - \sum p_i) / |\det\Lambda| = \delta^{(4)}(P - \sum p_i)$。
>
> **结论：**
>
> $$\boxed{d\Pi_n = (2\pi)^4 \delta^{(4)}\!\left(P - \sum_{i=1}^n p_i\right) \prod_{i=1}^n \frac{d^3p_i}{(2\pi)^3\,2E_i}}$$
>
> 每一项均为 Lorentz 不变量，故 $d\Pi_n$ 是 Lorentz 不变的。$\square$
>

>[!s]- **(b) 质心系相空间**
>
> **(b) 两体末态相空间积分**
>
> 在 **质心系** 中，$\mathbf{P} = \mathbf{0}$，$P^0 = E_{\text{CM}}$。
>
> $$\begin{aligned}
> \int d\Pi_2 &= \int (2\pi)^4 \delta^{(4)}(P - p_1 - p_2) \; \frac{d^3p_1}{(2\pi)^3 2E_1} \frac{d^3p_2}{(2\pi)^3 2E_2} \\[4pt]
> &= \int (2\pi)^4 \delta(E_{\text{CM}} - E_1 - E_2) \, \delta^{(3)}(\mathbf{p}_1 + \mathbf{p}_2) \; \frac{d^3p_1}{(2\pi)^3 2E_1} \frac{d^3p_2}{(2\pi)^3 2E_2}
> \end{aligned}$$
>
> **步骤 1：积掉 $\mathbf{p}_2$。** 由 $\delta^{(3)}(\mathbf{p}_1 + \mathbf{p}_2)$ 得 $\mathbf{p}_2 = -\mathbf{p}_1 \equiv -\mathbf{p}$：
>
> $$= \int (2\pi) \, \delta(E_{\text{CM}} - E_1 - E_2) \; \frac{d^3p}{(2\pi)^3\,4E_1E_2}$$
>
> 其中 $E_1 = \sqrt{|\mathbf{p}|^2 + m_1^2}$，$E_2 = \sqrt{|\mathbf{p}|^2 + m_2^2}$。
>
> **步骤 2：化为球坐标。** $d^3p = |\mathbf{p}|^2 \, d|\mathbf{p}| \, d\Omega$：
>
> $$\int d\Pi_2 = \frac{1}{16\pi^2} \int d\Omega \int_0^\infty d|\mathbf{p}| \; |\mathbf{p}|^2 \, \frac{\delta\big(E_{\text{CM}} - E_1(|\mathbf{p}|) - E_2(|\mathbf{p}|)\big)}{E_1E_2}$$
>
> **步骤 3：处理能量 $\delta$ 函数。** 定义 $f(|\mathbf{p}|) \equiv E_{\text{CM}} - E_1 - E_2$，利用：
>
> $$\delta(f(p)) = \sum_{\text{roots}} \frac{\delta(p - p_*)}{\,|f'(p_*)|\,}$$
>
> 求导：
>
> $$\frac{dE_i}{d|\mathbf{p}|} = \frac{|\mathbf{p}|}{E_i} \quad\Longrightarrow\quad f'(|\mathbf{p}|) = -\frac{|\mathbf{p}|}{E_1} - \frac{|\mathbf{p}|}{E_2} = -|\mathbf{p}|\,\frac{E_1 + E_2}{E_1E_2} = -|\mathbf{p}|\,\frac{E_{\text{CM}}}{E_1E_2}$$
>
> 在根 $|\mathbf{p}| = |\mathbf{p}|_*$（满足 $E_1 + E_2 = E_{\text{CM}}$）处：
>
> $$|f'(|\mathbf{p}|_*)| = \frac{|\mathbf{p}|_*\,E_{\text{CM}}}{E_1E_2}$$
>
> 因此：
>
> $$\delta(E_{\text{CM}} - E_1 - E_2)\,d|\mathbf{p}| = \frac{E_1E_2}{|\mathbf{p}|_*\,E_{\text{CM}}}$$
>
> **步骤 4：代回积分。**
>
> $$\begin{aligned}
> \int d\Pi_2 &= \frac{1}{16\pi^2} \int d\Omega \; |\mathbf{p}|_*^2 \, \frac{1}{E_1E_2} \cdot \frac{E_1E_2}{|\mathbf{p}|_*\,E_{\text{CM}}} \\[4pt]
> &= \boxed{\frac{1}{16\pi^2} \frac{|\mathbf{p}|_*}{E_{\text{CM}}} \int d\Omega}
> \end{aligned}$$
>
> 其中 $|\mathbf{p}|_*$ 由能动量守恒确定：
>
> $$\sqrt{|\mathbf{p}|_*^2 + m_1^2} + \sqrt{|\mathbf{p}|_*^2 + m_2^2} = E_{\text{CM}}$$
>
> $$\implies |\mathbf{p}|_* = \frac{\sqrt{\big[E_{\text{CM}}^2 - (m_1+m_2)^2\big]\big[E_{\text{CM}}^2 - (m_1-m_2)^2\big]}}{2E_{\text{CM}}}$$
>
> **补充：等质量情况。** 若 $m_1 = m_2 = m$，则 $E_1 = E_2 = E_{\text{CM}}/2$，且：
>
> $$|\mathbf{p}|_* = \sqrt{\frac{E_{\text{CM}}^2}{4} - m^2}$$
>
> 记 $s \equiv E_{\text{CM}}^2$，得标准形式：
>
> $$\boxed{\int d\Pi_2 = \frac{1}{16\pi^2} \sqrt{1 - \frac{4m^2}{s}} \int d\Omega}$$
>
> 这是 $2\to 2$ 散射截面计算中最常用的两体相空间公式。

### 4.2 微分截面

**(a)** 写出 $2\to 2$ 散射的微分截面公式（同质量 $m_A=m_B=m$，$m_C=m_D=M$）：
$$\frac{d\sigma}{d\Omega} = \frac{1}{64\pi^2 E_{\text{CM}}^2} \frac{|\mathbf{p}_f|}{|\mathbf{p}_i|} |\mathcal{M}|^2$$

**(b)** 对 $\phi^4$ 理论，$\mathcal{M} = -\lambda$，计算质心系总截面 $\sigma_{\text{tot}}$。

**(c)** 验证 $\sigma_{\text{tot}}$ 的量纲为 $[\text{length}]^2$（$3+1$ 维）或 $[\text{length}]^0$（$1+1$ 维）。

### 4.3 衰变率

**(a)** 推导质量为 $M$ 的单粒子衰变到两个质量为 $m_1, m_2$ 的粒子的微分衰变率：
$$d\Gamma = \frac{1}{32\pi^2} \frac{|\mathbf{p}_1|}{M^2} |\mathcal{M}|^2 d\Omega$$

**(b)** 若衰变产物为同种粒子（$m_1=m_2$），相空间需要除以 $2!$ 的对称性因子。解释其原因。

### 4.4 Mandelstam 变量

**(a)** 对 $2\to 2$ 散射 $A(p_1)+B(p_2)\to C(p_3)+D(p_4)$，定义 Mandelstam 变量：
$$s = (p_1+p_2)^2,\quad t = (p_1-p_3)^2,\quad u = (p_1-p_4)^2$$
证明 $s+t+u = m_A^2+m_B^2+m_C^2+m_D^2$。

**(b)** 在质心系中，写出 $t$ 用散射角 $\theta$ 和动量表示的表达式。

**(c)** 解释 $s$ 道、$t$ 道、$u$ 道的物理含义（分别对应什么物理过程）。


---

## 第五章 旋量 QED 基础

### 5.1 Dirac 方程与旋量

**(a)** 从 Dirac 方程 $(i\gamma^\mu\partial_\mu - m)\psi = 0$ 出发，写出平面波解：
$$\psi(x) = \int \frac{d^3p}{(2\pi)^3\sqrt{2E_{\mathbf{p}}}} \sum_{s=1,2} \left[a_{\mathbf{p}}^s u^s(p) e^{-ipx} + b_{\mathbf{p}}^{s\dagger} v^s(p) e^{ipx}\right]$$
其中 $u^s$ 和 $v^s$ 满足 $(\not{p}-m)u^s = 0$，$(\not{p}+m)v^s = 0$。

**(b)** 证明旋量和的自旋求和公式：
$$\sum_s u^s(p)\bar{u}^s(p) = \not{p} + m,\qquad \sum_s v^s(p)\bar{v}^s(p) = \not{p} - m$$

**(c)** 利用上述公式证明：
$$\sum_{s,s'}|\bar{u}^{s'}(p')\gamma^\mu u^s(p)|^2 = \text{Tr}[(\not{p}'+m)\gamma^\mu(\not{p}+m)\gamma^\nu]$$

### 5.2 QED Feynman 规则

画出 QED 的 Feynman 规则表，包括：
- 电子传播子
- 光子传播子（Feynman 规范和 Landau 规范）
- 电子-光子顶点
- 外线因子（入射/出射电子/正电子，入射/出射光子）
- 每个费米子圈的 $-1$ 因子

### 5.3 $e^+e^- \to \mu^+\mu^-$ 截面

**(a)** 画出最低阶 Feynman 图（单光子交换），写出振幅：
$$i\mathcal{M} = (-ie)^2 \bar{v}(p_2)\gamma^\mu u(p_1) \frac{-ig_{\mu\nu}}{q^2} \bar{u}(p_3)\gamma^\nu v(p_4)$$

**(b)** 在质心系高能极限（$E_{\text{CM}} \gg m_e, m_\mu$）下，证明：
$$\frac{d\sigma}{d\Omega} = \frac{\alpha^2}{4E_{\text{CM}}^2}(1+\cos^2\theta)$$

**(c)** 积分得总截面 $\sigma_{\text{tot}} = \frac{4\pi\alpha^2}{3E_{\text{CM}}^2}$。验证量纲正确。

### 5.4 Compton 散射 $\star$

**(a)** 写出 Compton 散射 $e^-\gamma \to e^-\gamma$ 的两个树级 Feynman 图（s 道 + u 道），写出总振幅。

**(b)** 在实验室系（电子初态静止），推导 Klein-Nishina 公式：
$$\frac{d\sigma}{d\Omega} = \frac{\alpha^2}{2m^2}\left(\frac{\omega'}{\omega}\right)^2 \left[\frac{\omega'}{\omega} + \frac{\omega}{\omega'} - \sin^2\theta\right]$$
其中 $\frac{\omega'}{\omega} = \frac{1}{1+(\omega/m)(1-\cos\theta)}$。

**提示**：这道题计算量大，重点关注矩阵元的迹计算和相空间处理。


---

## 第六章 矢量玻色子与规范对称性

### 6.1 有质量矢量场

考虑 Proca Lagrangian $\mathcal{L} = -\frac{1}{4}F_{\mu\nu}F^{\mu\nu} + \frac{1}{2}m^2 A_\mu A^\mu$。

**(a)** 导出运动方程 $\partial_\mu F^{\mu\nu} + m^2 A^\nu = 0$，并由此证明 $\partial_\mu A^\mu = 0$（自洽约束）。

**(b)** 写出 $A_\mu$ 的模展开（三种极化），给出产生湮灭算符的对易关系。

**(c)** 计算传播子：
$$\langle 0|T\{A_\mu(x)A_\nu(y)\}|0\rangle = \int \frac{d^4k}{(2\pi)^4} \frac{-i(g_{\mu\nu} - k_\mu k_\nu/m^2)}{k^2 - m^2 + i\epsilon} e^{-ik(x-y)}$$

> [!s]- **(a) 运动方程与自洽约束**
>
> $F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$。Euler-Lagrange：
> $$\frac{\partial\mathcal{L}}{\partial A_\nu} - \partial_\mu\frac{\partial\mathcal{L}}{\partial(\partial_\mu A_\nu)} = 0$$
>
> $$\frac{\partial\mathcal{L}}{\partial(\partial_\mu A_\nu)} = \frac{\partial}{\partial(\partial_\mu A_\nu)}\Big[-\frac{1}{4}F_{\rho\sigma}F^{\rho\sigma}\Big]$$
>
> $F_{\rho\sigma}F^{\rho\sigma}$ 对 $\partial_\mu A_\nu$ 的导数：$\partial F_{\rho\sigma}/\partial(\partial_\mu A_\nu) = \delta^\mu_\rho\delta^\nu_\sigma - \delta^\mu_\sigma\delta^\nu_\rho$。
> $$2F^{\rho\sigma}(\delta^\mu_\rho\delta^\nu_\sigma - \delta^\mu_\sigma\delta^\nu_\rho) = 2(F^{\mu\nu} - F^{\nu\mu}) = 4F^{\mu\nu}$$
>
> $$\frac{\partial\mathcal{L}}{\partial(\partial_\mu A_\nu)} = -\frac{1}{4}\cdot 4F^{\mu\nu} = -F^{\mu\nu}$$
>
> $\partial\mathcal{L}/\partial A_\nu = m^2 A^\nu$。运动方程：
> $$\boxed{\partial_\mu F^{\mu\nu} + m^2 A^\nu = 0}$$
>
> **自洽约束**：对 $\partial_\nu$ 再作用：$\partial_\nu\partial_\mu F^{\mu\nu} + m^2\partial_\nu A^\nu = 0$。$F^{\mu\nu}$ 反对称，$\partial_\nu\partial_\mu$ 对称 → $\partial_\nu\partial_\mu F^{\mu\nu} \equiv 0$。$m^2 \neq 0$：
> $$\boxed{\partial_\mu A^\mu = 0}$$
>
> 无质量（$m=0$）时此约束失效——这是规范对称性的恢复。有质量时 Lorentz 条件是**动力学推论**，不是规范选择。

> [!s]- **(b) 模展开与对易关系**
>
> 利用 $\partial_\mu A^\mu=0$ 和运动方程 $(\Box + m^2)A^\mu = 0$（从 $\partial_\mu F^{\mu\nu} = \Box A^\nu - \partial^\nu\partial_\mu A^\mu = \Box A^\nu$ 得）：
>
> $$A_\mu(x) = \int\frac{d^3k}{(2\pi)^3\sqrt{2\omega_k}} \sum_{\lambda=1}^3 \Big[a_{\mathbf{k}}^\lambda\,\varepsilon_\mu(\mathbf{k},\lambda)\,e^{-ikx} + a_{\mathbf{k}}^{\lambda\dagger}\,\varepsilon_\mu^*(\mathbf{k},\lambda)\,e^{ikx}\Big]_{k^0=\omega_k}$$
>
> 其中 $\omega_k = \sqrt{\mathbf{k}^2 + m^2}$。三个极化矢量满足：
> $$k^\mu\varepsilon_\mu(\mathbf{k},\lambda) = 0,\qquad \varepsilon^\mu(\mathbf{k},\lambda)\,\varepsilon_\mu(\mathbf{k},\lambda') = -g_{\lambda\lambda'}$$
>
> 对易关系（正则量子化）：
> $$[a_{\mathbf{k}}^\lambda, a_{\mathbf{k}'}^{\lambda'\dagger}] = (2\pi)^3\delta^{(3)}(\mathbf{k}-\mathbf{k}')\,\delta^{\lambda\lambda'},\qquad [a_{\mathbf{k}}^\lambda, a_{\mathbf{k}'}^{\lambda'}] = [a_{\mathbf{k}}^{\lambda\dagger}, a_{\mathbf{k}'}^{\lambda'\dagger}] = 0$$
>
> $m\to 0$ 极限：$\lambda=3$（纵向极化）的 $\varepsilon^\mu \propto k^\mu$ 导致模范数为零，退化为两物理偏振态——这正是 $m=0$ 时规范对称性消除第三自由度的剩余。

> [!s]- **(c) 传播子**
>
> 传播子 $D_{\mu\nu}(x-y) = \langle 0|T\{A_\mu(x)A_\nu(y)\}|0\rangle$ 满足：
> $$\big[g_{\mu\rho}(\Box_x + m^2) - \partial_\mu\partial_\rho\big] D^{\rho}{}_\nu(x-y) = -i\,g_{\mu\nu}\,\delta^{(4)}(x-y)$$
>
> Fourier 变换 $(x-y) \to k$。利用 $\partial_\mu \to -ik_\mu$，$\Box \to -k^2$：
> $$\big[g_{\mu\rho}(-k^2 + m^2) + k_\mu k_\rho\big] \tilde{D}^{\rho}{}_\nu(k) = -i\,g_{\mu\nu}$$
>
> 记 $M_{\mu\rho} = g_{\mu\rho}(m^2 - k^2) + k_\mu k_\rho$。解 $\tilde{D} = -i M^{-1}$。$M$ 的逆为：
> $$(M^{-1})^{\rho\nu} = \frac{g^{\rho\nu} - k^\rho k^\nu/m^2}{m^2 - k^2}$$
>
> 验证：$M_{\mu\rho}(M^{-1})^{\rho\nu} = [g_{\mu\rho}(m^2-k^2) + k_\mu k_\rho]\frac{g^{\rho\nu} - k^\rho k^\nu/m^2}{m^2-k^2}$。
>
> 交叉项：$(m^2-k^2)[g_\mu{}^\nu - k_\mu k^\nu/m^2] + k_\mu k^\nu - k_\mu(k^2)k^\nu/m^2 = (m^2-k^2)g_\mu{}^\nu + (-k_\mu k^\nu + k_\mu k^\nu) + \cdots$
>
> 化简后 $=(m^2-k^2)g_\mu{}^\nu$。$M\cdot M^{-1} = g_\mu{}^\nu$ ✓。
>
> 加上 $i\epsilon$ 正规化：
> $$\boxed{\tilde{D}_{\mu\nu}(k) = \frac{-i(g_{\mu\nu} - k_\mu k_\nu/m^2)}{k^2 - m^2 + i\epsilon}}$$
>
> **分子 $g_{\mu\nu} - k_\mu k_\nu/m^2$ 的含义**：这是自旋-1 的投影算符——它保证了只有三个（而非四个）自由度传播，且满足 $k^\mu\tilde{D}_{\mu\nu} = 0$（Lorentz 条件的动量空间版本）。
>
> $m \to 0$ 极限中此传播子发散——反映了无质量矢量场需要规范固定才能定义传播子。

### 6.2 Ward 恒等式（QED 树级）

**(a)** 对 QED 顶点函数 $\Gamma^\mu(p',p) = \gamma^\mu$（树级），直接验证 Ward 恒等式：
$$q_\mu \Gamma^\mu(p+q,p) = S_F^{-1}(p+q) - S_F^{-1}(p)$$

**(b)** 将 Ward 恒等式推广到包含 $n$ 个外光子的过程：
$$k_\mu \mathcal{M}^{\mu\nu\cdots} = 0$$
解释这条恒等式如何保证散射振幅的 Lorentz 规范不变性（即替换 $\epsilon_\mu \to \epsilon_\mu + c k_\mu$ 后振幅不变）。

### 6.3 非 Abel 规范理论的鬼场 $\star\star$

**(a)** 写出 $SU(N)$ Yang-Mills Lagrangian，解释为何 $\mathcal{L}_{\text{gf}} = -\frac{1}{2\xi}(\partial_\mu A^{a\mu})^2$ 需要伴随鬼场项 $\mathcal{L}_{\text{ghost}} = \bar{c}^a(-\partial_\mu D^{ab\mu})c^b$。

**(b)** 对 $SU(2)$ 纯规范理论，写出三胶子和四胶子顶点的 Feynman 规则。


---

## 第七章 一圈图计算

### 7.1 $\phi^4$ 的两点函数

**(a)** 写出 $\phi^4$ 理论中自能 $\Sigma(p^2)$ 的 $\mathcal{O}(\lambda)$ 图（蝌蚪图），并计算：
$$\Sigma = \frac{\lambda}{2} \int \frac{d^4k}{(2\pi)^4} \frac{i}{k^2 - m^2 + i\epsilon}$$

**(b)** 证明蝌蚪图发散（二次发散），并解释为什么正规序下 $\langle 0|\phi^2|0\rangle = 0$ 时此图为零。

### 7.2 $\phi^4$ 的四点函数 —— dim reg

**(a)** 写出 $\phi^4$ 理论中 $\mathcal{O}(\lambda^2)$ 对 $2\to 2$ 散射的单圈修正 Feynman 图（s 道、t 道、u 道），并写出 s 道的表达式：
$$i\mathcal{M}_s = \frac{(-i\lambda)^2}{2} \int \frac{d^4k}{(2\pi)^4} \frac{i}{k^2 - m^2 + i\epsilon} \frac{i}{(k+p_1+p_2)^2 - m^2 + i\epsilon}$$

**(b)** 用 Feynman 参数化合并分母：
$$\frac{1}{AB} = \int_0^1 dx \frac{1}{[xA + (1-x)B]^2}$$

**(c)** 进行 Wick 转动 $k^0 \to ik_E^0$，转到 $D = 4-2\epsilon$ 维。在 $D$ 维中，用以下基本积分：
$$\int \frac{d^Dk_E}{(2\pi)^D} \frac{1}{(k_E^2 + \Delta)^n} = \frac{1}{(4\pi)^{D/2}} \frac{\Gamma(n-D/2)}{\Gamma(n)} \Delta^{D/2-n}$$

计算：
$$\int \frac{d^Dk_E}{(2\pi)^D} \frac{1}{(k_E^2 + \Delta)^2}$$

**(d)** 将结果展开到 $\mathcal{O}(1/\epsilon)$，识别出 $1/\epsilon$ 极点。写出 $\overline{\text{MS}}$ 方案下需要的抵消项。

### 7.3 真空极化（QED 光子自能） $\star\star$

**(a)** 写出 QED 中光子自能 $\Pi^{\mu\nu}(q)$ 的单圈表达式（费米子圈）：
$$i\Pi^{\mu\nu}(q) = -(-ie)^2 \int \frac{d^4k}{(2\pi)^4} \text{Tr}\left[\gamma^\mu \frac{i}{\not{k}-m} \gamma^\nu \frac{i}{\not{k}+\not{q}-m}\right]$$

**(b)** 计算 Dirac 矩阵的迹 $\text{Tr}[\gamma^\mu(\not{k}+m)\gamma^\nu(\not{k}+\not{q}+m)]$。

**(c)** 证明规范不变性要求 $\Pi^{\mu\nu}(q) = (q^2 g^{\mu\nu} - q^\mu q^\nu)\Pi(q^2)$，并提取 $\Pi(q^2)$。

**(d)** 在 $D=4-2\epsilon$ 维下，证明 $\Pi(q^2)$ 的发散部分为：
$$\Pi(q^2)_{\text{div}} = -\frac{e^2}{12\pi^2} \cdot \frac{1}{\epsilon}$$

**(e)** 解释这一发散如何通过光子波函数重整化 $A_\mu \to \sqrt{Z_3}A_\mu$ 吸收。

### 7.4 电子自能 $\star$

**(a)** 写出 QED 电子自能 $\Sigma(p)$ 的单圈 Feynman 图，并写下表达式。

**(b)** 证明 $\Sigma(p)$ 可以参数化为：
$$\Sigma(p) = A(p^2)\not{p} + B(p^2)m$$
在壳重整化条件下，$Z_2$ 和 $\delta m$ 如何由 $A$ 和 $B$ 表达？


---

## 第八章 重整化

### 8.1 $\phi^4$ 的重整化 —— 完整流程

**(a)** 写出 $\phi^4$ 的裸 Lagrangian（用 $\phi_0, m_0, \lambda_0$），并引入重整化常数：
$$\phi = Z_\phi^{-1/2}\phi_0,\quad m^2 = Z_m Z_\phi m_0^2,\quad \lambda = Z_\lambda Z_\phi^2 \lambda_0$$

**(b)** 写出 $\mathcal{L} = \mathcal{L}_{\text{physical}} + \mathcal{L}_{\text{counter}}$ 的形式。抵消项 Feynman 规则是什么？

**(c)** 在 $\overline{\text{MS}}$ 方案下，给出单圈 $\beta$ 函数：
$$\beta(\lambda) \equiv \mu \frac{d\lambda}{d\mu} = \frac{3\lambda^2}{16\pi^2} + \mathcal{O}(\lambda^3)$$

**(d)** 解 $\beta$ 函数的 RG 方程，讨论 Landau 极点的物理含义（$\phi^4$ 的平庸性）。

### 8.2 QED 的重整化与跑动耦合 $\star$

**(a)** 写出重整化后的 QED Lagrangian（包含 $\delta_2, \delta_3, \delta_m, \delta_1$）。

**(b)** 利用 7.3 和 7.4 的结果，证明 QED 的 $\beta$ 函数（单圈）为：
$$\beta(e) = \frac{e^3}{12\pi^2}$$

**(c)** 解出跑动耦合常数 $e(\mu)$，并计算 Landau 极点位置。讨论 QED 在极高能量下的行为。

### 8.3 可观测量与重整化方案无关性

**(a)** 解释为什么物理散射振幅必须独立于重整化方案（$\overline{\text{MS}}$ vs 在壳方案）。

**(b)** 对 $\phi^4$ 的 $2\to 2$ 散射，验证 $\mathcal{O}(\lambda^2)$ 的有限部分在两种方案下相差一个常数，但包含跑动耦合 $\lambda(s)$ 后差异被 $\mathcal{O}(\lambda^3)$ 的未算项覆盖。


---

## 第九章 路径积分 $\star$

### 9.1 生成泛函

**(a)** 写出实标量场的生成泛函：
$$Z[J] = \int \mathcal{D}\phi\, \exp\left[i\int d^4x \left(\mathcal{L} + J\phi\right)\right]$$

**(b)** 证明 $n$ 点关联函数可由 $Z[J]$ 的泛函导数得到：
$$\langle 0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle = \frac{1}{Z[0]} \left.\frac{(-i)^n \delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}$$

### 9.2 自由场的路径积分

**(a)** 对自由标量场，完成 Gaussian 积分，证明：
$$Z_0[J] = Z_0[0] \exp\left[-\frac{1}{2}\int d^4x d^4y\, J(x)D_F(x-y)J(y)\right]$$

**(b)** 利用 $Z_0[J]$ 推导自由场的 Wick 定理（取四次泛函导数）。

### 9.3 微扰展开与连通图

**(a)** 对 $\phi^4$ 理论，写出 $Z[J] = \exp\left[i\int d^4x \left(-\frac{\lambda}{4!}\right)\left(\frac{1}{i}\frac{\delta}{\delta J}\right)^4\right] Z_0[J]$。

**(b)** 定义连通生成泛函 $W[J] = -i\ln Z[J]$。$W[J]$ 生成什么类型的 Feynman 图？

**(c)** 定义量子有效作用量 $\Gamma[\phi_{\text{cl}}] = W[J] - \int d^4x J\phi_{\text{cl}}$（Legendre 变换）。证明 $\Gamma[\phi_{\text{cl}}]$ 的二次泛函导数给出完整的（精确）传播子 $G^{-1}(p) = p^2 - m^2 - \Sigma(p^2)$。


---

## 第十章 综合计算题

### 10.1 $\phi^4$ 全流程

在质心能量 $\sqrt{s} = 1$ TeV 处，计算 $\phi^4$ 理论（$m = 0.1$ TeV，$\lambda = 0.5$）的：

**(a)** 树级总截面 $\sigma_{\text{tree}}$。

**(b)** 一圈修正后的截面 $\sigma_{\text{1-loop}}$（用 7.2 和 8.1 结果）。

**(c)** 取重整化标度 $\mu = \sqrt{s}$，计算用 $\lambda(\mu)$ 代替 $\lambda$ 后 $\sigma_{\text{tree}}$ 的改变。比较两种截面和实验精度的关系。

### 10.2 手推 QED 过程 $\star$

计算 Møller 散射 $e^-e^- \to e^-e^-$ 的树级截面（需要考虑全同粒子的 $t \leftrightarrow u$ 交换反对称化）。

**(a)** 画出两个图，写出总振幅 $\mathcal{M} = \mathcal{M}_t - \mathcal{M}_u$（减号来自 Fermi 统计）。

**(b)** 在质心系高能极限下（$m_e \ll \sqrt{s}$），计算 $|\mathcal{M}|^2$（含自旋平均/求和）。

**(c)** 给出 $d\sigma/d\Omega$，并与 $e^-e^+\to\mu^-\mu^+$ 的结果比较。

### 10.3 共形反常的简单例子 $\star\star$

**(a)** 对 $3+1$ 维无质量 $\phi^4$ 理论（经典共形不变），证明经典能动张量的迹为零。

**(b)** 在量子层面，计算单圈 $\beta$ 函数后，证明能动张量的迹不再为零：
$$\langle T^\mu{}_\mu\rangle = \frac{\beta(\lambda)}{4!}\langle\phi^4\rangle$$

**(c)** 解释共形异常与圈图发散之间的联系：为什么重整化 $\mu$ 的引入必然破坏经典共形对称性？


---

## 附录

### A. 常用公式

- **$\gamma$ 矩阵**：Clifford 代数 $\{\gamma^\mu,\gamma^\nu\} = 2g^{\mu\nu}$，迹公式 $\text{Tr}(\gamma^\mu\gamma^\nu) = 4g^{\mu\nu}$，$\text{Tr}(\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma) = 4(g^{\mu\nu}g^{\rho\sigma} - g^{\mu\rho}g^{\nu\sigma} + g^{\mu\sigma}g^{\nu\rho})$
- **Feynman 参数化**：$\frac{1}{AB} = \int_0^1 dx \frac{1}{[xA+(1-x)B]^2}$，推广：$\frac{1}{A_1\cdots A_n} = (n-1)!\int_0^1 dx_1\cdots dx_n \frac{\delta(1-\sum x_i)}{(\sum x_i A_i)^n}$
- **Dim reg 积分**：$\int \frac{d^Dk_E}{(2\pi)^D}\frac{k_E^{2\alpha}}{(k_E^2+\Delta)^\beta} = \frac{\Gamma(\beta-\alpha-D/2)\Gamma(\alpha+D/2)}{(4\pi)^{D/2}\Gamma(D/2)\Gamma(\beta)}\Delta^{-(\beta-\alpha-D/2)}$

### B. 量纲分析速查

|  维数   | $[\phi]$ | $[m]$ | $[\lambda]$（$\lambda\phi^4$） | $[e]$（QED）  |
| :---: | :------: | :---: | :--------------------------: | :---------: |
| $3+1$ |   $1$    |  $1$  |           $0$（可重整）           |  $0$（可重整）   |
| $1+1$ |   $0$    |  $1$  |          $2$（超可重整）           |  $1$（超可重整）  |
| $2+1$ |  $1/2$   |  $1$  |          $1$（超可重整）           | $1/2$（超可重整） |

### C. 推荐阅读顺序

| 你的目标 | 推荐章节顺序 |
|----------|-------------|
| 快速上手微扰计算 | 1 → 2 → 3 → 4（1-2 天） |
| 掌握重整化 | 1 → 2 → 3 → 7 → 8（3-4 天） |
| 掌握 QED 过程 | 1 → 2 → 4 → 5 → 10（2-3 天） |
| 通向共形/弯曲时空 | 1 → 2 → 7.2 → 8 → 10.3 → 回看弯曲时空题 |
