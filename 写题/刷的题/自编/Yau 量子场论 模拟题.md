---
up:
  - "[[写题]]"
related:
date: 2026-04-30
tags:
  - 量子场论
  - 习题
  - 模拟题
---

# 模拟题 1: $d$ 维共形标量场与改进能动张量

> 本题将原题中的 4 维标量场推广到任意 $d$ 维，并引入改进能动张量的概念。使用自然单位 $\hbar = c = 1$。

---

**(a)** 考虑 $d$ 维 Minkowski 时空中的无质量标量场：

$$S = \frac{1}{2} \int d^d x \, (\partial_\mu \phi)^2$$

在刚性（全局）标度变换 $\eta^{\mu\nu} \to \tilde{\eta}^{\mu\nu} = \Omega^2 \eta^{\mu\nu}$（$\Omega$ 为常数）下，同时令 $\phi \to \tilde{\phi} = \Omega^{\Delta} \phi$。求 $\Delta$ 作为 $d$ 的函数，并验证 $d=4$ 时 $\Delta = 1$。

>[!S]-
>在标度变换下
>$$x\to \lambda x ,\quad \phi(x) \to \lambda^{-\Delta}\phi(\lambda^{-1}x) $$
>于是
>$$\partial_{\mu}\phi \to \frac{1}{\lambda} \lambda^{-\Delta} \partial_{\mu}\phi(\lambda^{-1}x) = \lambda^{-\Delta-1} \partial_{\mu}\phi(x) $$
>作用量变换为
>$$S \to \int d^{d}x \lambda^{d} \lambda^{2(-\Delta-1)} (\partial_{\mu}\phi)^{2} $$
>故 $-d+2(\Delta+1)=0$ 即
>$$\Delta = \frac{d-2}{2} $$

---

**(b)** 将理论推广到弯曲时空，作用量为：

$$S_{\text{min}} = \frac{1}{2} \int d^d x \, \sqrt{-g} \, g^{\mu\nu} \partial_\mu \phi \, \partial_\nu \phi$$

在局域 Weyl 变换 $g^{\mu\nu} \to \tilde{g}^{\mu\nu} = \Omega^2(x) g^{\mu\nu}$ 和 $\phi \to \Omega^{\Delta} \phi$ 下，取 $\Delta$ 为 (a) 中的值。证明仅靠最小耦合，作用量 $S_{\text{min}}$ **不能**在任意 $d$ 下保持局域 Weyl 不变性。

>[!S]-
>在变换下
>$$\sqrt{ -g } \to \Omega^{-d}\sqrt{ -g } ,\quad \partial_{\mu}\phi \to \partial_{\mu}(\Omega^{\Delta}\phi) = \Omega^{\Delta}\partial_{\mu}\phi + \Delta \Omega^{\Delta-1}\phi \partial_{\mu}\Omega $$
>于是
>$$\begin{align} S & \to \frac{1}{2}\int d^{d}x \Omega^{-d}\sqrt{ -g }\Omega^{2}(\Omega^{2\Delta}(\partial_{\mu}\phi)^{2} + 2\Delta \Omega^{2\Delta-1}\phi \partial_{\mu}\phi \partial^{\mu}\Omega + \Delta^{2}\Omega^{2\Delta-2}\phi^{2}(\partial_{\mu}\Omega)^{2}) \\ & = \frac{1}{2}\int d^{d}x \Omega^{2\Delta-d}\sqrt{ -g }( \Omega^{2}(\partial_{\mu}\phi)^{2} + 2\Delta \Omega \phi \partial_{\mu}\phi\partial^{\mu}\Omega + \Delta^{2}\phi^{2}(\partial_{\mu}\Omega)^{2}) \end{align} $$
>注意到其中的 $\partial_{\mu}\Omega$ 项，其无法通过对 $\Delta$ 取值来消除，所以无论如何 $\delta S$ 都是与 $\Omega$ 的具体形式有关的，作用量 $S_{\text{min}}$ **不能**在任意 $d$ 下保持局域 Weyl 不变性
>

---

**(c)** 在 $d$ 维时空中，Ricci 标量 $R$ 在局域 Weyl 变换下的变换规律为：

$$\tilde{R} = \Omega^2 \big[ R + 2(d-1) \Box \ln\Omega - (d-1)(d-2) (\nabla \ln\Omega)^2 \big]$$

（本题不需要推导此式，直接使用即可。）验证 $d=4$ 时此式回到原题 (c) 的结果。

>[!S]-
>$d=4$ 时
>$$\bar{R} = \Omega^{2}[ R + 6\Box\ln \Omega - 6(\nabla \ln \Omega)^{2} ] $$
>

>[]- 此式の证明
>变换为
>$$\tilde{g}_{\mu \nu} = \Omega^{2}g_{\mu \nu} ,\quad \tilde{g}^{\mu \nu} = \Omega^{-2}g^{\mu \nu} ,\quad \Omega>0$$
>考虑克里斯托弗联络
>$$\begin{align} \tilde{\Gamma}^{\lambda}_{\mu \nu} & = \frac{1}{2}\tilde{g}^{\lambda \rho}(\partial_{\mu}\tilde{g}_{\nu \rho} + \partial_{\nu}\tilde{g}_{\mu \rho} - \partial_{\rho}\tilde{g}_{\mu \nu}) \\ & =\frac{1}{2} \Omega^{-2}g^{\lambda \rho}( 2\Omega^{2}g_{\nu \rho}\partial_{\mu}\ln \Omega + \Omega^{2}{\color{red}\partial_{\mu}g_{\nu \rho}} + (\mu\leftrightarrow \nu) - 2\Omega^{2}g_{\mu \nu}\partial_{\rho}\ln \Omega + \Omega^{2}{\color{red}\partial_{\rho}g_{\mu \nu}} ) \\ & = {\color{red}\Gamma^{\lambda}_{\mu \nu}} + \delta^{\lambda}_{\nu}\partial_{\mu}\ln \Omega + \delta^{\lambda}_{\mu}\partial_{\nu}\ln \Omega - g_{\mu \nu}g^{\lambda \rho}\partial_{\rho}\ln \Omega \end{align}$$
>黎曼张量按照定义 $[\nabla_{\mu},\nabla_{\nu}]V^{\rho}=R^{\rho}_{\sigma \mu \nu}V^{\sigma}$ 于是
>$$R^{\rho}_{\sigma \mu \nu} = \partial_{\mu}\Gamma^{\rho}_{\nu \sigma} - \partial_{\nu}\Gamma^{\rho}_{\mu \sigma} + \Gamma^{\rho}_{\mu \lambda}\Gamma^{\lambda}_{\nu \sigma} - \Gamma^{\rho}_{\nu \lambda}\Gamma^{\lambda}_{\mu \sigma} $$
>而里奇张量 $R_{\mu \nu}=R^{\rho}_{\mu \rho \nu}$ 所以考虑令 $\mu=\rho,\sigma=\mu$ 求和
>其中
>$$\begin{align}\partial_{\rho}\tilde{\Gamma}^{\rho}_{\mu \nu} & = \partial_{\rho}( \Gamma^{\rho}_{\mu \nu} + \delta^{\rho}_{\mu}\partial_{\nu}\ln \Omega + \delta^{\rho}_{\nu}\partial_{\mu}\ln \Omega - g_{\mu \nu}\partial^{\rho}\ln \Omega ) \\ & = \partial_{\rho}\Gamma^{\rho}_{\mu \nu} + 2\partial_{\mu}\partial_{\nu}\ln \Omega - g_{\mu \nu}\Box\ln \Omega - \partial^{\rho}\ln \Omega \partial_{\rho}g_{\mu \nu} \end{align}$$
>$$\begin{align} \partial_{\nu}\tilde{\Gamma}^{\rho}_{\rho \mu} & = \partial_{\nu}(\Gamma^{\rho}_{\rho \mu} + \delta^{\rho}_{\rho}\partial_{\mu}\ln \Omega + \delta^{\rho}_{\mu}\partial_{\rho}\ln \Omega - g_{\rho \mu}\partial^{\rho}\ln \Omega) \\ & = \partial_{\nu}( \Gamma^{\rho}_{\rho \mu} + d\partial_{\mu}\ln \Omega ) \\ & = \partial_{\nu}\Gamma^{\rho}_{\rho \mu} + d \partial_{\mu}\partial_{\nu}\ln \Omega \end{align} $$
>$$\begin{align} \tilde{\Gamma}^{\lambda}_{\mu \nu}\tilde{\Gamma}^{\rho}_{\lambda \rho} & = (\Gamma^{\lambda}_{\mu \nu} + S^{\lambda}_{\mu \nu})\left( \Gamma^{\rho}_{\rho \lambda} + d \partial_{\mu}\ln \Omega \right) \\ & =  \end{align} $$
>$$ $$
>
>
>

---

**(d)** 在作用量中加入 Ricci 标量耦合项：

$$S = \int d^d x \, \sqrt{-g} \left[ \frac{1}{2} g^{\mu\nu} \partial_\mu \phi \, \partial_\nu \phi - \frac{1}{2} \xi R \phi^2 \right]$$

在局域 Weyl 变换下，通过适当选取 $\Delta$ 和耦合常数 $\xi$，使得总作用量保持不变。求 $\Delta$ 和 $\xi$ 作为 $d$ 的函数，并验证 $d=4$ 时 $\xi = -\frac{1}{6}$。

>[]
>

---

**(e)** 考虑 $d$ 维 de Sitter 时空，其度规为：

$$ds^2 = \frac{-d\tau^2 + d\mathbf{x}^2}{(H\tau)^2}, \qquad \mathbf{x} \in \mathbb{R}^{d-1}, \;\; \tau \in (-\infty, 0)$$

其中 $H$ 为常数。证明共形标量场 $\phi$（即取 (d) 中 $\xi$ 值的标量场）在此时空中的作用量等价于 $d$ 维 Minkowski 时空中的一个**有质量**标量场。求有效质量 $m_{\text{eff}}^2$（用 $H$ 和 $d$ 表示）。

---

# 模拟题 2: 麦克斯韦场的共形对称性

> 本题将共形对称性的分析方法应用于麦克斯韦（矢量）场。注意与标量场的关键区别：规范场在 4 维具有天然的局域 Weyl 不变性。

---

**(a)** 考虑 $d$ 维 Minkowski 时空中的自由麦克斯韦场：

$$S = -\frac{1}{4} \int d^d x \, F_{\mu\nu} F^{\mu\nu}, \qquad F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$$

在刚性标度变换 $\eta^{\mu\nu} \to \Omega^2 \eta^{\mu\nu}$ 和 $A_\mu \to \Omega^{\Delta} A_\mu$ 下，求 $\Delta$ 作为 $d$ 的函数。验证 $d=4$ 时 $\Delta = 0$。

---

**(b)** 推广到弯曲时空：

$$S = -\frac{1}{4} \int d^d x \, \sqrt{-g} \, g^{\mu\alpha} g^{\nu\beta} F_{\mu\nu} F_{\alpha\beta}$$

考虑局域 Weyl 变换 $g^{\mu\nu} \to \Omega^2(x) g^{\mu\nu}$ 和 $A_\mu \to \Omega^{\Delta} A_\mu$（取 $\Delta$ 为 (a) 中的值）。证明：
- 在 $d=4$ 时，$F_{\mu\nu}$ 在局域 Weyl 变换下**保持不变**（注意 $A_\mu$ 的变换指数为 0），因此麦克斯韦作用量自动具有局域 Weyl 不变性；
- 在 $d \neq 4$ 时，$\Delta \neq 0$，局域变换会产生 $\partial_\mu \Omega$ 的项，破坏 Weyl 不变性。

---

**(c)** 在 $d=4$ 时，麦克斯韦场的能动张量为：

$$T_{\mu\nu} = F_{\mu\alpha} F_\nu{}^\alpha - \frac{1}{4} g_{\mu\nu} F_{\alpha\beta} F^{\alpha\beta}$$

证明：
- (i) $T^\mu{}_\mu = 0$（经典无迹）；
- (ii) $\nabla^\mu T_{\mu\nu} = 0$（在源 $J^\mu = 0$ 时利用运动方程 $\nabla^\mu F_{\mu\nu} = 0$ 验证）。

---

**(d)** 在 $d \neq 4$ 时，为恢复 Weyl 不变性，引入 dilaton 场 $\varphi(x)$：

$$S = -\frac{1}{4} \int d^d x \, \sqrt{-g} \, e^{\kappa \varphi} F_{\mu\nu} F^{\mu\nu}$$

在 Weyl 变换下，令 $\varphi$ 按照 $\varphi \to \varphi + \alpha \ln\Omega$ 变换，$A_\mu$ 不变（取 Weyl 权为 0）。求 $\kappa$ 和 $\alpha$ 应满足的关系，使得作用量在**任意** $d$ 下具有局域 Weyl 不变性。

---

**(e)** 在 $d=3$ 维时空中，自由麦克斯韦场与自由标量场存在对偶关系：

$$F_{\mu\nu} = \varepsilon_{\mu\nu\rho} \, \partial^\rho \chi$$

其中 $\chi$ 是标量场。写出 $\chi$ 的作用量，利用 (a) 的结果求 $\chi$ 在 $d=3$ 下的标度维数 $\Delta_\chi$。验证这与标量场的标度维数 (模拟题 1(a)) 是否一致，并解释其物理含义。

---

# 模拟题 3: Yukawa 理论的单圈重整化

> 本题与「24 年」的 Yukawa 问题类似，但考察**顶角修正**而非自能图。

---

**(a)** 写出 $d = 4 - \varepsilon$ 维时空中 Yukawa 理论（标量-旋量耦合）的拉氏量：

$$\mathcal{L} = \frac{1}{2} (\partial_\mu \phi)^2 - \frac{1}{2} m^2 \phi^2 + \bar{\psi}(i\gamma^\mu \partial_\mu - M)\psi - ig \bar{\psi} \gamma^5 \psi \phi$$

确定量纲正规化下耦合常数 $g$ 的**质量量纲**。如何引入重整化标度 $\mu$ 使 $g$ 在 $d=4-\varepsilon$ 下保持无量纲？

---

**(b)** 考虑单圈顶角修正 $\Gamma^\mu(p, p')$（即 $\phi \psi \bar{\psi}$ 三线顶角的单圈修正）。画出所有单圈 Feynman 图，写出对应的振幅表达式（不必计算积分）。

---

**(c)** 利用**表观发散度**（superficial degree of divergence）判断顶角修正图的发散类型。这个理论是否需要引入新的抵消项来重整化顶角？如果需要，写出所需抵消项的形式。

---

**(d)** 假定标量场自能 $\Pi_\phi(p^2)$ 和旋量场自能 $\Sigma(p)$ 的单圈修正均已算得，写出包含所有抵消项的完整拉氏量 $\mathcal{L} + \mathcal{L}_{\text{CT}}$，并说明各抵消项的来源（对应哪个发散图）。

---

**(e)** 计算顶角修正的发散部分。利用运动方程和 Ward 恒等式（或手征对称性）讨论耦合常数 $g$ 的重整化群 $\beta$ 函数在单圈阶的符号。该理论是渐近自由的还是红外自由的？

