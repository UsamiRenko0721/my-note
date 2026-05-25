---
up:
  - "[[写题]]"
related:
  - "[[弯曲时空下的QFT]]"
  - "[[膨胀宇宙中的粒子产生]]"
  - "[[QFT 基础计算习题册]]"
  - "[[做题总结-膨胀宇宙]]"
date: 2026-05-06
tags:
  - GR
  - problem-set
  - differential-geometry
  - Einstein-equations
  - Schwarzschild
  - cosmology
---

# GR 基础计算习题册

> 共 10 章，52 道题。覆盖张量计算到场方程求解。
> 标 $\star$ 为选做，标 $\star\star$ 为挑战。

---

## 第一章 张量分析热身

### 1.1 度规与逆度规

给定 $3+1$ 维球对称度规的试探形式：
$$ds^2 = -e^{2\Phi(r)}dt^2 + e^{2\Lambda(r)}dr^2 + r^2(d\theta^2 + \sin^2\theta\,d\phi^2)$$

**(a)** 写出度规张量 $g_{\mu\nu}$ 的分量（按 $(t,r,\theta,\phi)$ 顺序）。

**(b)** 计算逆度规 $g^{\mu\nu}$（注意：逆度规是对角矩阵的逐分量倒数）。

**(c)** 验证 $g_{\mu\rho}g^{\rho\nu} = \delta_\mu^\nu$。

### 1.2 坐标变换

**(a)** 从极坐标 $(r,\phi)$ 变换到 Cartesian 坐标 $(x,y)$：$x=r\cos\phi$，$y=r\sin\phi$。计算变换矩阵 $J^\mu{}_\nu = \partial x'^\mu/\partial x^\nu$。

**(b)** 二维 Euclid 度规在 Cartesian 坐标下为 $ds^2 = dx^2 + dy^2$。用张量变换律 $g'_{\mu\nu} = (J^{-1})^\rho{}_\mu (J^{-1})^\sigma{}_\nu g_{\rho\sigma}$ 证明极坐标下 $ds^2 = dr^2 + r^2 d\phi^2$。

**(c)** 推广泛例：从 Minkowski 坐标 $(t,x)$ 变换到 Rindler 坐标 $(\eta,\rho)$：
$$t = e^{\rho}\sinh\eta,\quad x = e^{\rho}\cosh\eta$$
推导 $ds^2 = e^{2\rho}(d\eta^2 - d\rho^2)$。（参考 [[弯曲时空下的QFT]] II.1）

### 1.3 测地线方程：极值化方法

**(a)** 从作用量 $S = \int \sqrt{-g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu}\,d\lambda$ 出发，考虑类时测地线的 Lagrangian：
$$L = \frac{1}{2}g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu,\quad \dot{x}^\mu \equiv \frac{dx^\mu}{d\tau}$$
其中 $\tau$ 为本征时。导出 Euler-Lagrange 方程：
$$\frac{d}{d\tau}\left(\frac{\partial L}{\partial \dot{x}^\mu}\right) = \frac{\partial L}{\partial x^\mu}$$

**(b)** 由此证明测地线方程等价于：
$$\ddot{x}^\mu + \Gamma^\mu_{\alpha\beta}\dot{x}^\alpha\dot{x}^\beta = 0$$
并证明 Christoffel 符号由度规表达为：
$$\Gamma^\mu_{\alpha\beta} = \frac{1}{2}g^{\mu\nu}(\partial_\alpha g_{\nu\beta} + \partial_\beta g_{\nu\alpha} - \partial_\nu g_{\alpha\beta})$$

**(c)** 对 $1+1$ 维 Rindler 度规 $ds^2 = e^{2\rho}(d\eta^2 - d\rho^2)$，用 (a) 的 Lagrangian 方法直接写出 $\eta$ 和 $\rho$ 的测地线方程（算 $\Gamma$ 再代入，不要用公式）。

### 1.4 Christoffel 符号的变换性质 $\star$

**(a)** 证明 Christoffel 符号不是张量——在坐标变换 $x\to x'$ 下：
$$\Gamma'^\mu_{\alpha\beta} = \frac{\partial x'^\mu}{\partial x^\nu}\frac{\partial x^\rho}{\partial x'^\alpha}\frac{\partial x^\sigma}{\partial x'^\beta}\,\Gamma^\nu_{\rho\sigma} + \frac{\partial x'^\mu}{\partial x^\nu}\frac{\partial^2 x^\nu}{\partial x'^\alpha\partial x'^\beta}$$

**(b)** 解释第二项（非齐次项）为何使 $\Gamma$ 不是张量，并利用此性质证明：**总可以找到一点使得 $\Gamma^\mu_{\alpha\beta} = 0$**（局域惯性系，即等效原理的数学表达）。

> [!s]- **(a) 完整推导**
> 
> **Step 1：度规的变换律**
> 
> $$g'_{\alpha\beta} = \frac{\partial x^\mu}{\partial x'^\alpha}\frac{\partial x^\nu}{\partial x'^\beta}\, g_{\mu\nu}$$
> 
> 对 $x'^\gamma$ 求偏导。乘积法则打击三个因子：
> 
> $$\begin{aligned} \partial'_\gamma g'_{\alpha\beta} = &\frac{\partial^2 x^\mu}{\partial x'^\gamma\partial x'^\alpha}\frac{\partial x^\nu}{\partial x'^\beta} g_{\mu\nu} + \frac{\partial x^\mu}{\partial x'^\alpha}\frac{\partial^2 x^\nu}{\partial x'^\gamma\partial x'^\beta} g_{\mu\nu} \\ &+ \frac{\partial x^\mu}{\partial x'^\alpha}\frac{\partial x^\nu}{\partial x'^\beta}\frac{\partial x^\rho}{\partial x'^\gamma}\, \partial_\rho g_{\mu\nu} \end{aligned}$$
> 
> **Step 2：轮换组合**
> 
> Christoffel 符号在新坐标下：
> $$\Gamma'^\mu_{\alpha\beta} = \frac{1}{2}g'^{\mu\gamma}(\partial'_\alpha g'_{\gamma\beta} + \partial'_\beta g'_{\gamma\alpha} - \partial'_\gamma g'_{\alpha\beta})$$
> 
> 把 $\partial' g'$ 代入，逆度规按 $g'^{\mu\gamma} = \frac{\partial x'^\mu}{\partial x^\nu}\frac{\partial x'^\gamma}{\partial x^\sigma} g^{\nu\sigma}$ 变换。
> 
> **Step 3：分离两项**
> 
> 含 $\partial_\rho g_{\mu\nu}$ 的项经 $(\partial_\alpha g + \partial_\beta g - \partial_\gamma g)$ 轮换后恰好还原出 $\Gamma^\nu_{\rho\sigma}$ —— 这是**张量部分**。
> 
> 含二阶导数 $\partial^2 x/\partial x'\partial x'$ 的项无法消掉，整理后给出：
> $$g'^{\mu\gamma} \cdot \frac{\partial x^\rho}{\partial x'^\gamma} \cdot \frac{\partial^2 x^\nu}{\partial x'^\alpha\partial x'^\beta}\, g_{\rho\nu} = \frac{\partial x'^\mu}{\partial x^\nu}\frac{\partial^2 x^\nu}{\partial x'^\alpha\partial x'^\beta}$$
> 
> **最终结果**（$\Gamma' = J\Gamma J^{-1}J^{-1} + J\partial^2 x$）：
> $$\boxed{\Gamma'^\mu_{\alpha\beta} = \underbrace{\frac{\partial x'^\mu}{\partial x^\nu}\frac{\partial x^\rho}{\partial x'^\alpha}\frac{\partial x^\sigma}{\partial x'^\beta}\,\Gamma^\nu_{\rho\sigma}}_{\text{张量部分}} + \underbrace{\frac{\partial x'^\mu}{\partial x^\nu}\frac{\partial^2 x^\nu}{\partial x'^\alpha\partial x'^\beta}}_{\text{非齐次项}}}$$

> [!s]- **(b) 物理解释与局域惯性系**
> 
> **非齐次项使 $\Gamma$ 不是张量**：如果 $\Gamma$ 是张量，变换律应只有第一项（三项 Jacobi 行列式）。但二阶导数项的存在意味着——可通过选择弯曲坐标在某点消掉 $\Gamma$。一个真正的张量做不到这一点：若张量在某个坐标系的所有分量都为零，则它在任何坐标系的所有分量都为零。而 $\Gamma$ 可以在一点为零、另一点不为零。
> 
> **构造局域惯性系**：在点 $P$ 附近做坐标变换的 Taylor 展开：
> $$x'^\mu = x^\mu + a^\mu + \frac{1}{2}C^\mu_{\alpha\beta}(x^\alpha - x^\alpha_P)(x^\beta - x^\beta_P) + \cdots$$
> 
> 代入变换公式，在 $P$ 点得：
> $$\Gamma'^\mu_{\alpha\beta}(P) = \Gamma^\mu_{\alpha\beta}(P) + C^\mu_{\alpha\beta}$$
> 
> 取 $C^\mu_{\alpha\beta} = -\Gamma^\mu_{\alpha\beta}(P)$，则 $\Gamma'^\mu_{\alpha\beta}(P) = 0$。这等价于在 $P$ 点度规的一阶导数为零：
> $$g_{\mu\nu}(P) = \eta_{\mu\nu},\qquad \partial_\sigma g_{\mu\nu}(P) = 0$$
> 
> **等效原理**：在局域惯性系中 $\Gamma = 0$ → 测地线方程退化为 $\ddot{x}^\mu = 0$（自由粒子做匀速直线运动） → 引力局域消失。这就是 **Einstein 等效原理的数学化身** —— 在时空的每一点，总存在一个坐标系使得引力作用被「变换走」，物理规律回到狭义相对论。

---

## 第二章 曲率张量

### 2.1 Riemann 张量的独立分量

**(a)** 从定义出发：
$$R^\rho{}_{\sigma\mu\nu} = \partial_\mu\Gamma^\rho_{\nu\sigma} - \partial_\nu\Gamma^\rho_{\mu\sigma} + \Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma} - \Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma}$$
证明 $R_{\rho\sigma\mu\nu}$ 的对称性：
$$R_{\rho\sigma\mu\nu} = -R_{\sigma\rho\mu\nu} = -R_{\rho\sigma\nu\mu} = R_{\mu\nu\rho\sigma}$$

**(b)** 证明第一 Bianchi 恒等式：
$$R^\rho{}_{\sigma\mu\nu} + R^\rho{}_{\mu\nu\sigma} + R^\rho{}_{\nu\sigma\mu} = 0$$

**(c)** 计算 $n$ 维空间中 Riemann 张量的独立分量数：
$$N = \frac{n^2(n^2-1)}{12}$$
对 $n=2,3,4$ 给出具体数值。

> [!s]- **(a) Riemann 张量的对称性证明**
> 
> **关键技巧：Riemann 法坐标（RNC）**。在任一点 $P$，选择局域惯性系使得 $\Gamma^\mu_{\alpha\beta}(P) = 0$。此时 Riemann 张量简化为：
> $$R^\rho{}_{\sigma\mu\nu} = \partial_\mu\Gamma^\rho_{\nu\sigma} - \partial_\nu\Gamma^\rho_{\mu\sigma} \quad (\text{在 }P\text{ 点})$$
> 
> 降指标后 $R_{\rho\sigma\mu\nu} = g_{\rho\lambda}R^\lambda{}_{\sigma\mu\nu}$。在 $P$ 点 $\partial g = 0$，所以：
> $$R_{\rho\sigma\mu\nu} = g_{\rho\lambda}(\partial_\mu\Gamma^\lambda_{\nu\sigma} - \partial_\nu\Gamma^\lambda_{\mu\sigma})$$
> 
> 代入 $\Gamma^\lambda_{\nu\sigma} = \frac{1}{2}g^{\lambda\tau}(\partial_\nu g_{\sigma\tau} + \partial_\sigma g_{\nu\tau} - \partial_\tau g_{\nu\sigma})$，在 $P$ 点 $g_{\mu\nu} = \eta_{\mu\nu}$ 常数，$\partial g$ 不为零。整理所有项后：
> 
> $$\boxed{R_{\rho\sigma\mu\nu} = \frac{1}{2}(\partial_\mu\partial_\sigma g_{\rho\nu} - \partial_\mu\partial_\rho g_{\sigma\nu} - \partial_\nu\partial_\sigma g_{\rho\mu} + \partial_\nu\partial_\rho g_{\sigma\mu})}$$
> 
> **从这个表达式，四个对称性一目了然：**
> 
> (i) **$R_{\rho\sigma\mu\nu} = -R_{\sigma\rho\mu\nu}$** ：交换 $\rho\leftrightarrow\sigma$ 使两项变号。
> 
> (ii) **$R_{\rho\sigma\mu\nu} = -R_{\rho\sigma\nu\mu}$** ：交换 $\mu\leftrightarrow\nu$ 使两项变号。
> 
> (iii) **$R_{\rho\sigma\mu\nu} = R_{\mu\nu\rho\sigma}$** ：交换 $(\rho,\sigma)\leftrightarrow(\mu,\nu)$ —— 第一项 $\partial_\mu\partial_\sigma g_{\rho\nu}$ 变为 $\partial_\rho\partial_\nu g_{\mu\sigma}$，这正是第四项的对称。四项全部对调后不变。
> 
> (iv) **$R_{\rho[\sigma\mu\nu]} = 0$** （第一 Bianchi）：对后三个指标轮换求和为零。
> 
> 因为有 (iii)，(iv) 等价于 $R_{[\rho\sigma\mu]\nu} = 0$。

> [!s]- **(b) 第一 Bianchi 恒等式**
> 
> 在 RNC 中（$\Gamma=0$ 在 $P$）：
> $$R^\rho{}_{\sigma\mu\nu} = \partial_\mu\Gamma^\rho_{\nu\sigma} - \partial_\nu\Gamma^\rho_{\mu\sigma}$$
> 
> 轮换 $(\sigma,\mu,\nu)$：
> $$\begin{aligned}
> R^\rho{}_{\sigma\mu\nu} &= \partial_\mu\Gamma^\rho_{\nu\sigma} - \partial_\nu\Gamma^\rho_{\mu\sigma} \\
> R^\rho{}_{\mu\nu\sigma} &= \partial_\nu\Gamma^\rho_{\sigma\mu} - \partial_\sigma\Gamma^\rho_{\nu\mu} \\
> R^\rho{}_{\nu\sigma\mu} &= \partial_\sigma\Gamma^\rho_{\mu\nu} - \partial_\mu\Gamma^\rho_{\sigma\nu}
> \end{aligned}$$
> 
> 三项求和。$\partial_\mu\Gamma^\rho_{\nu\sigma}$ 与 $-\partial_\mu\Gamma^\rho_{\sigma\nu}$ 抵消（$\Gamma$ 对两个下标对称）。同理其余成对抵消：
> $$\boxed{R^\rho{}_{\sigma\mu\nu} + R^\rho{}_{\mu\nu\sigma} + R^\rho{}_{\nu\sigma\mu} = 0}$$
> 
> **为什么在 RNC 中证明就够了？** 因为 Bianchi 恒等式的每一项都是张量分量的组合。如果它在某个坐标系等于零，在所有坐标系都等于零。RNC 只是让证明简化。

> [!s]- **(c) 独立分量计数**
> 
> 将 $R_{\rho\sigma\mu\nu}$ 视为 $n\times n$ 反对称矩阵对：
> 
> - $(\rho,\sigma)$ 反对称：独立对数为 $\binom{n}{2} = \frac{n(n-1)}{2}$
> - $(\mu,\nu)$ 反对称：同上
> 
> 先不看 Bianchi：$R_{\rho\sigma\mu\nu}$ 可以看作 $\frac{n(n-1)}{2} \times \frac{n(n-1)}{2}$ 的矩阵，且具有交换对称性 $R_{AB} = R_{BA}$（$A$ 和 $B$ 都是反对称指标对）。因此 — 好比对称矩阵 — 独立分量数为：
> $$N_{\text{初}} = \frac{1}{2} \cdot \frac{n(n-1)}{2} \cdot \left(\frac{n(n-1)}{2} + 1\right) = \frac{n(n-1)(n^2 - n + 2)}{8}$$
> 
> **第一 Bianchi 恒等式的约束：** $R_{\rho[\sigma\mu\nu]} = 0$。在 $n\geq 4$ 时这是非平庸的。它的独立方程数等于选择四个不同指标的方式数：$\binom{n}{4}$。
> 
> 最终的独立分量数：
> $$N = \frac{n(n-1)(n^2-n+2)}{8} - \binom{n}{4} = \boxed{\frac{n^2(n^2-1)}{12}}$$
> 
> | 维数 $n$ | 独立分量数 $N$ | 备注 |
> |----------|---------------|------|
> | 1 | 0 | 一维没有内在曲率 |
> | 2 | 1 | $S^2$：只有 $R_{1212}$，即 Gauss 曲率 |
> | 3 | 6 | Ricci 完全决定 Riemann（Weyl=0） |
> | 4 | 20 | Ricci (10) + Weyl (10) |

### 2.2 FLRW 度规的曲率（手工计算）

对 $1+1$ 维 FLRW 度规 $ds^2 = a^2(\eta)(d\eta^2 - dx^2)$：

**(a)** 计算非零 Christoffel 符号。**不要跳步**——先写出 $g_{\mu\nu}$ 和 $g^{\mu\nu}$，再逐分量算。

**(b)** 计算 Riemann 张量的非零分量。

**(c)** 计算 Ricci 张量 $R_{\mu\nu} = R^\rho{}_{\mu\rho\nu}$ 和 Ricci 标量 $R = g^{\mu\nu}R_{\mu\nu}$。验证你得到 $R = -2a''/a^3$。（参考 [[膨胀宇宙中的粒子产生]] II.1(b) 的纠错讨论）

**(d)** 计算 Einstein 张量 $G_{\mu\nu} = R_{\mu\nu} - \frac{1}{2}R g_{\mu\nu}$，验证 $G_{\eta\eta} = 0$（$1+1$ 维的特性）。

> [!s]- **(a) Christoffel 符号**
> 
> **度规与逆度规**（坐标序 $(\eta, x)$，号差 $(+,-)$）：
> $$g_{\mu\nu} = \begin{pmatrix} a^2 & 0 \\ 0 & -a^2 \end{pmatrix}, \qquad g^{\mu\nu} = \begin{pmatrix} 1/a^2 & 0 \\ 0 & -1/a^2 \end{pmatrix}$$
> 
> 记 $a' \equiv da/d\eta$。非零偏导数只有：
> $$\partial_\eta g_{\eta\eta} = 2aa',\qquad \partial_\eta g_{xx} = -2aa'$$
> 所有 $\partial_x(\cdots) = 0$（空间均匀）。
> 
> 用 $\Gamma^\mu_{\alpha\beta} = \frac{1}{2}g^{\mu\nu}(\partial_\alpha g_{\nu\beta} + \partial_\beta g_{\nu\alpha} - \partial_\nu g_{\alpha\beta})$ 逐分量：
> 
> $$\begin{aligned}
> \Gamma^\eta_{\eta\eta} &= \frac{1}{2a^2} \cdot \partial_\eta g_{\eta\eta} = \frac{a'}{a} \\[6pt]
> \Gamma^\eta_{xx} &= \frac{1}{2a^2} \cdot (-\partial_\eta g_{xx}) = \frac{1}{2a^2} \cdot 2aa' = \frac{a'}{a} \\[6pt]
> \Gamma^x_{\eta x} = \Gamma^x_{x\eta} &= \frac{1}{2} \cdot \left(-\frac{1}{a^2}\right) \cdot \partial_\eta g_{xx} = \frac{1}{2a^2} \cdot 2aa' = \frac{a'}{a}
> \end{aligned}$$
> 
> 其余为零：$\Gamma^\eta_{\eta x} = \Gamma^x_{\eta\eta} = \Gamma^x_{xx} = 0$。
> 
> **汇总**：三个非零 $\Gamma$，全部等于 Hubble 率 $\mathcal{H} \equiv a'/a$。
> 
> | $\Gamma$ | 值 |
> |----------|-----|
> | $\Gamma^\eta_{\eta\eta}$ | $a'/a$ |
> | $\Gamma^\eta_{xx}$ | $a'/a$ |
> | $\Gamma^x_{\eta x} = \Gamma^x_{x\eta}$ | $a'/a$ |

> [!s]- **(b) Riemann 张量**
> 
> 在 $1+1$ 维，Riemann 张量只有一个独立分量。取 $R^\eta{}_{x\eta x}$：
> 
> $$R^\eta{}_{x\eta x} = \partial_\eta\Gamma^\eta_{xx} - \partial_x\Gamma^\eta_{\eta x} + \Gamma^\eta_{\eta\lambda}\Gamma^\lambda_{xx} - \Gamma^\eta_{x\lambda}\Gamma^\lambda_{\eta x}$$
> 
> $$\begin{aligned}
> \partial_\eta\Gamma^\eta_{xx} &= \partial_\eta\!\left(\frac{a'}{a}\right) = \frac{a''a - a'^2}{a^2} \\[6pt]
> \Gamma^\eta_{\eta\lambda}\Gamma^\lambda_{xx} &= \Gamma^\eta_{\eta\eta}\Gamma^\eta_{xx} + \Gamma^\eta_{\eta x}\Gamma^x_{xx} = \frac{a'}{a}\cdot\frac{a'}{a} + 0 = \frac{a'^2}{a^2} \\[6pt]
> \Gamma^\eta_{x\lambda}\Gamma^\lambda_{\eta x} &= \Gamma^\eta_{x\eta}\Gamma^\eta_{\eta x} + \Gamma^\eta_{xx}\Gamma^x_{\eta x} = 0 + \frac{a'}{a}\cdot\frac{a'}{a} = \frac{a'^2}{a^2}
> \end{aligned}$$
> 
> $$\boxed{R^\eta{}_{x\eta x} = \frac{a''a - a'^2}{a^2}}$$
> 
> 降指标得唯一的独立分量：
> $$R_{\eta x\eta x} = g_{\eta\eta}R^\eta{}_{x\eta x} = a^2 \cdot \frac{a''a - a'^2}{a^2} = a''a - a'^2$$
> 
> 由对称性：$R_{x\eta x\eta} = R_{\eta x\eta x}$（交换对），$R_{\eta xx\eta} = -R_{\eta x\eta x}$（末两指标反对称）。

> [!s]- **(c) Ricci 张量与 Ricci 标量**
> 
> **Ricci 张量** $R_{\mu\nu} = R^\rho{}_{\mu\rho\nu}$：
> 
> $$\begin{aligned}
> R_{\eta\eta} &= R^\eta{}_{\eta\eta\eta} + R^x{}_{\eta x\eta} = 0 + R^x{}_{\eta x\eta} \\[6pt]
> R^x{}_{\eta x\eta} &= \partial_x\Gamma^x_{\eta\eta} - \partial_\eta\Gamma^x_{x\eta} + \Gamma^x_{x\lambda}\Gamma^\lambda_{\eta\eta} - \Gamma^x_{\eta\lambda}\Gamma^\lambda_{x\eta} \\[4pt]
> &= 0 - \partial_\eta\!\left(\frac{a'}{a}\right) + \frac{a'}{a}\cdot\frac{a'}{a} - \frac{a'}{a}\cdot\frac{a'}{a} = -\frac{a''a - a'^2}{a^2}
> \end{aligned}$$
> 
> $$\boxed{R_{\eta\eta} = -\frac{a''a - a'^2}{a^2},\qquad R_{xx} = \frac{a''a - a'^2}{a^2}}$$
> 
> **Ricci 标量**：
> $$\begin{aligned}
> R &= g^{\mu\nu}R_{\mu\nu} = g^{\eta\eta}R_{\eta\eta} + g^{xx}R_{xx} \\[4pt]
> &= \frac{1}{a^2}\!\left(-\frac{a''a - a'^2}{a^2}\right) + \left(-\frac{1}{a^2}\right)\!\left(\frac{a''a - a'^2}{a^2}\right) \\[4pt]
> &= -2\frac{a''a - a'^2}{a^4}
> \end{aligned}$$
> 
> $$\boxed{R = -\frac{2(a''a - a'^2)}{a^4}}$$
> 
> > **关于 $R = -2a''/a^3$**：这是题目中的简化写法。严格结果是 $R = -2(a''a - a'^2)/a^4$，包含 $a'^2$ 项。在共形时间下，仅当 $a'^2$ 可忽略（准静态极限）或使用不同记号约定时退化为 $-2a''/a^3$。详见 [[膨胀宇宙中的粒子产生]] II.1(b) 的讨论。

> [!s]- **(d) Einstein 张量**
> 
> $$G_{\mu\nu} = R_{\mu\nu} - \frac{1}{2}R g_{\mu\nu}$$
> 
> $$\begin{aligned}
> G_{\eta\eta} &= -\frac{a''a - a'^2}{a^2} - \frac{1}{2}\!\left(-2\frac{a''a - a'^2}{a^4}\right) \cdot a^2 \\[4pt]
> &= -\frac{a''a - a'^2}{a^2} + \frac{a''a - a'^2}{a^2} = 0 \\[8pt]
> G_{xx} &= \frac{a''a - a'^2}{a^2} - \frac{1}{2}\!\left(-2\frac{a''a - a'^2}{a^4}\right) \cdot (-a^2) \\[4pt]
> &= \frac{a''a - a'^2}{a^2} - \frac{a''a - a'^2}{a^2} = 0
> \end{aligned}$$
> 
> $$\boxed{G_{\mu\nu} \equiv 0}$$
> 
> 这是 $1+1$ 维引力的普遍性质：在二维，Einstein 张量恒为零（$G_{\mu\nu} = R_{\mu\nu} - \frac{1}{2}R g_{\mu\nu}$ 在二维的恒等式可从 $R_{\mu\nu\rho\sigma} = \frac{R}{2}(g_{\mu\rho}g_{\nu\sigma} - g_{\mu\sigma}g_{\nu\rho})$ 直接推出）。因此 **$1+1$ 维 Einstein 方程退化为 $T_{\mu\nu}=0$，没有局域引力自由度**。这也是为什么弯曲时空 QFT 题选 $1+1$ 维——背景几何是真空解，但量子场仍然感知曲率。

### 2.3 二维球面的曲率

对度规 $ds^2 = a^2(d\theta^2 + \sin^2\theta\,d\phi^2)$（$a$ 为常数半径）：

**(a)** 计算非零 Christoffel 符号。

**(b)** 计算 Riemann 张量，证明 $R_{\theta\phi\theta\phi} = a^2\sin^2\theta$。

**(c)** 计算 Ricci 标量 $R = 2/a^2$。

**(d)** 推广到 $n$ 维球面 $S^n$，Ricci 标量为 $R = n(n-1)/a^2$。对 $S^2$ 验证此公式。

> [!s]- **(a) Christoffel 符号**
>
> 度规 $g_{\mu\nu} = \text{diag}(a^2,\, a^2\sin^2\theta)$，逆度规 $g^{\mu\nu} = \text{diag}(1/a^2,\, 1/(a^2\sin^2\theta))$。
>
> 唯一非零偏导数：$\partial_\theta g_{\phi\phi} = 2a^2\sin\theta\cos\theta$。所有 $\partial_\phi(\cdots)=0$。
>
> $$\begin{aligned}
> \Gamma^\theta_{\phi\phi} &= \frac{1}{2}g^{\theta\theta}(-\partial_\theta g_{\phi\phi}) = \frac{1}{2a^2}(-2a^2\sin\theta\cos\theta) = -\sin\theta\cos\theta \\[6pt]
> \Gamma^\phi_{\theta\phi} = \Gamma^\phi_{\phi\theta} &= \frac{1}{2}g^{\phi\phi}(\partial_\theta g_{\phi\phi}) = \frac{1}{2a^2\sin^2\theta}(2a^2\sin\theta\cos\theta) = \cot\theta
> \end{aligned}$$
>
> 其余为零。只有两个非零 $\Gamma$（不计对称），都只依赖 $\theta$。

> [!s]- **(b) Riemann 张量**
>
> 二维球面只有一个独立分量。计算 $R^\theta{}_{\phi\theta\phi}$：
>
> $$\begin{aligned}
> R^\theta{}_{\phi\theta\phi} &= \partial_\theta\Gamma^\theta_{\phi\phi} - \partial_\phi\Gamma^\theta_{\theta\phi} + \Gamma^\theta_{\theta\lambda}\Gamma^\lambda_{\phi\phi} - \Gamma^\theta_{\phi\lambda}\Gamma^\lambda_{\theta\phi} \\[4pt]
> \partial_\theta\Gamma^\theta_{\phi\phi} &= \partial_\theta(-\sin\theta\cos\theta) = -(\cos^2\theta - \sin^2\theta) = \sin^2\theta - \cos^2\theta \\[4pt]
> \Gamma^\theta_{\theta\lambda}\Gamma^\lambda_{\phi\phi} &= \underbrace{\Gamma^\theta_{\theta\theta}}_{=0}\Gamma^\theta_{\phi\phi} + \underbrace{\Gamma^\theta_{\theta\phi}}_{=0}\Gamma^\phi_{\phi\phi} = 0 \\[4pt]
> \Gamma^\theta_{\phi\lambda}\Gamma^\lambda_{\theta\phi} &= \underbrace{\Gamma^\theta_{\phi\theta}}_{=0}\Gamma^\theta_{\theta\phi} + \Gamma^\theta_{\phi\phi}\Gamma^\phi_{\theta\phi} = (-\sin\theta\cos\theta)(\cot\theta) = -\cos^2\theta
> \end{aligned}$$
>
> $$R^\theta{}_{\phi\theta\phi} = (\sin^2\theta - \cos^2\theta) - 0 + 0 - (-\cos^2\theta) = \sin^2\theta$$
>
> 降指标：
> $$\boxed{R_{\theta\phi\theta\phi} = g_{\theta\theta}R^\theta{}_{\phi\theta\phi} = a^2\sin^2\theta}$$
>
> 这是 $S^2$ 上 Riemann 张量的唯一独立分量。由对称性：
> $$R_{\theta\phi\theta\phi} = -R_{\theta\phi\phi\theta} = -R_{\phi\theta\theta\phi} = R_{\phi\theta\phi\theta}$$

> [!S]- **(c) Ricci 标量**
>
>利用 $R_{\mu\nu} = g^{\rho\sigma}R_{\rho\mu\sigma\nu}$：
>
> $$\begin{aligned}
> R_{\theta\theta} &= g^{\phi\phi}R_{\phi\theta\phi\theta} = g^{\phi\phi}R_{\theta\phi\theta\phi} = \frac{1}{a^2\sin^2\theta} \cdot a^2\sin^2\theta = 1 \\[6pt]
> R_{\phi\phi} &= g^{\theta\theta}R_{\theta\phi\theta\phi} = \frac{1}{a^2} \cdot a^2\sin^2\theta = \sin^2\theta
> \end{aligned}$$
>
> Ricci 标量：
> $$R = g^{\theta\theta}R_{\theta\theta} + g^{\phi\phi}R_{\phi\phi} = \frac{1}{a^2}\cdot 1 + \frac{1}{a^2\sin^2\theta}\cdot\sin^2\theta$$
>
> $$\boxed{R = \frac{2}{a^2}}$$
>
> 与 $\theta$ 无关——这是均匀空间（常曲率空间）的标志。

> [!s]- **(d) 推广到 $S^n$**
>
> **思路**：最大对称空间（$S^n$、$H^n$、$\mathbb{R}^n$）的 Riemann 张量只能由度规构造——因为没有其他几何量可用。满足所有对称性的唯一结构是：
>
> $$\boxed{R_{\rho\sigma\mu\nu} = K\,(g_{\rho\mu}g_{\sigma\nu} - g_{\rho\nu}g_{\sigma\mu})}$$
>
> 其中 $K$ 是曲率参数（常数）。
>
> **从二维读出 $K$**：由 (b) 已知 $R_{\theta\phi\theta\phi} = a^2\sin^2\theta$，而代入上式：
> $$R_{\theta\phi\theta\phi} = K(g_{\theta\theta}g_{\phi\phi} - g_{\theta\phi}g_{\phi\theta}) = K \cdot a^2 \cdot a^2\sin^2\theta = K a^4\sin^2\theta$$
>
> 对比得 $K a^4\sin^2\theta = a^2\sin^2\theta \;\Rightarrow\; K = 1/a^2$。
>
> **缩并回 Ricci**：
> $$R_{\sigma\nu} = g^{\rho\mu}R_{\rho\sigma\mu\nu} = K(\delta^\mu_\sigma g_{\sigma\nu} - g_{\sigma\nu}) = K(n-1)g_{\sigma\nu}$$
>
> $$R = g^{\sigma\nu}R_{\sigma\nu} = K(n-1) \cdot g^{\sigma\nu}g_{\sigma\nu} = K(n-1)n$$
>
> $$\boxed{R = \frac{n(n-1)}{a^2}}$$
>
> **验证 $S^2$**：$n=2 \;\Rightarrow\; R = 2/a^2$，与 (c) 一致。✓
>
> 这个推导的精髓在于：**二维的显式计算结果固定了唯一的曲率参数 $K$，不需要在 $n$ 维重做任何 Christoffel 计算，缩并关系会自动把维度信息编入因子 $n(n-1)$。**

### 2.4 共形变换下的曲率 $\star$

度规的共形变换 $g_{\mu\nu} = \Omega^2(x)\tilde{g}_{\mu\nu}$。 

**(a)** 证明 Christoffel 符号的变换为：

$$\Gamma^\rho_{\mu\nu} = \tilde{\Gamma}^\rho_{\mu\nu} + \delta^\rho_\mu \partial_\nu\ln\Omega + \delta^\rho_\nu \partial_\mu\ln\Omega - \tilde{g}_{\mu\nu}\tilde{g}^{\rho\sigma}\partial_\sigma\ln\Omega$$

**(b)** 推导 Ricci 标量的变换（$n$ 维）：

$$R = \Omega^{-2}\left[\tilde{R} - 2(n-1)\tilde{\Box}\ln\Omega - (n-1)(n-2)\tilde{g}^{\mu\nu}(\partial_\mu\ln\Omega)(\partial_\nu\ln\Omega)\right]$$

**(c)** 对 FLRW 度规（$\Omega = a(\eta)$，$\tilde{g}_{\mu\nu} = \eta_{\mu\nu}$，$\tilde{R}=0$），验证 (b) 的公式与 2.2(c) 的结果一致。

> [!s]- **(a) Christoffel 符号的共形变换**
>
> 出发点：$\Gamma^\rho_{\mu\nu} = \frac{1}{2}g^{\rho\sigma}(\partial_\mu g_{\nu\sigma} + \partial_\nu g_{\mu\sigma} - \partial_\sigma g_{\mu\nu})$。
>
> 共形变换下 $g_{\mu\nu} = \Omega^2 \tilde{g}_{\mu\nu}$，$g^{\rho\sigma} = \Omega^{-2} \tilde{g}^{\rho\sigma}$。
>
> 度规的偏导数产生两项——$\partial_\mu(\Omega^2\tilde{g}_{\nu\sigma})$ 的乘积法则打击两个因子：
> $$\partial_\mu g_{\nu\sigma} = 2\Omega\,\partial_\mu\Omega\,\tilde{g}_{\nu\sigma} + \Omega^2\,\partial_\mu\tilde{g}_{\nu\sigma} = \Omega^2(2\,\partial_\mu\!\ln\Omega \cdot \tilde{g}_{\nu\sigma} + \partial_\mu\tilde{g}_{\nu\sigma})$$
>
> 三组偏导数代入 Christoffel 公式。$\Omega^2$ 与 $g^{\rho\sigma}$ 的 $\Omega^{-2}$ 精确抵消：
>
> $$\begin{aligned}
> \Gamma^\rho_{\mu\nu} &= \frac{1}{2}\tilde{g}^{\rho\sigma}\Big[(2\partial_\mu\!\ln\Omega \cdot \tilde{g}_{\nu\sigma} + \cancel{\partial_\mu\tilde{g}_{\nu\sigma}}) \\
> &\qquad\qquad\; + (2\partial_\nu\!\ln\Omega \cdot \tilde{g}_{\mu\sigma} + \cancel{\partial_\nu\tilde{g}_{\mu\sigma}}) \\
> &\qquad\qquad\; - (2\partial_\sigma\!\ln\Omega \cdot \tilde{g}_{\mu\nu} + \cancel{\partial_\sigma\tilde{g}_{\mu\nu}})\Big]
> \end{aligned}$$
>
> 划掉的部分还原出 $\tilde{\Gamma}^\rho_{\mu\nu}$。
>
> 留下的三项中，$\ln\Omega$ 的导数直接与 $\tilde{g}$ 和 $\tilde{g}^{-1}$ 缩并：
> $$\tilde{g}^{\rho\sigma}\tilde{g}_{\nu\sigma}\,\partial_\mu\!\ln\Omega = \delta^\rho_\nu\,\partial_\mu\!\ln\Omega$$
>
> $$\boxed{\Gamma^\rho_{\mu\nu} = \tilde{\Gamma}^\rho_{\mu\nu} + \delta^\rho_\mu\partial_\nu\!\ln\Omega + \delta^\rho_\nu\partial_\mu\!\ln\Omega - \tilde{g}_{\mu\nu}\tilde{g}^{\rho\sigma}\partial_\sigma\!\ln\Omega}$$

> [!s]- **(b) Ricci 标量的共形变换**
>
> 推导路径：$\Gamma$ 变换 $\,\to\,$ Riemann 变换 $\,\to\,$ Ricci 变换 $\,\to\,$ $R$ 变换。两个中间结果：
>
> **Ricci 张量**（$n$ 维，缀饰量在 $\tilde{g}$ 背景下计算）：
>
> $$\begin{aligned}
> R_{\mu\nu} = \tilde{R}_{\mu\nu} &- (n-2)\tilde{\nabla}_\mu\tilde{\nabla}_\nu\!\ln\Omega - \tilde{g}_{\mu\nu}\,\tilde{\Box}\!\ln\Omega \\
> &+ (n-2)(\tilde{\nabla}_\mu\!\ln\Omega)(\tilde{\nabla}_\nu\!\ln\Omega) - (n-2)\tilde{g}_{\mu\nu}\,\tilde{g}^{\alpha\beta}(\tilde{\nabla}_\alpha\!\ln\Omega)(\tilde{\nabla}_\beta\!\ln\Omega)
> \end{aligned}$$
>
> 这个结果的关键结构：所有"超出 $\tilde{R}_{\mu\nu}$"的项都由 $\ln\Omega$ 的一阶和二阶协变导数组成。系数 $n-2$ 的来源是缩并 $\delta^\mu_\mu = n$ 时减去$1$——这正是共形耦合常数 $\xi_c = (n-2)/[4(n-1)]$ 的深层几何根源。
>
> **Ricci 标量**：用 $g^{\mu\nu} = \Omega^{-2}\tilde{g}^{\mu\nu}$ 缩并。每项 $R_{\mu\nu}$ 乘 $\Omega^{-2}\tilde{g}^{\mu\nu}$ 后：
>
> - $\Omega^{-2}\tilde{g}^{\mu\nu}\tilde{R}_{\mu\nu} = \Omega^{-2}\tilde{R}$
> - $\Omega^{-2}\tilde{g}^{\mu\nu}[\tilde{g}_{\mu\nu}\tilde{\Box}\ln\Omega] = \Omega^{-2}n\,\tilde{\Box}\ln\Omega$
> - $\Omega^{-2}\tilde{g}^{\mu\nu}[-(n-2)\tilde{\nabla}_\mu\tilde{\nabla}_\nu\ln\Omega] = -(n-2)\Omega^{-2}\tilde{\Box}\ln\Omega$
> - 含 $(\tilde{\nabla}\ln\Omega)^2$ 的项整理后给出 $-(n-1)(n-2)$ 组合因子
>
> 最终：
> $$\boxed{R = \Omega^{-2}\Big[\tilde{R} - 2(n-1)\tilde{\Box}\!\ln\Omega - (n-1)(n-2)\,\tilde{g}^{\mu\nu}(\partial_\mu\!\ln\Omega)(\partial_\nu\!\ln\Omega)\Big]}$$
>
> **特殊维度**：
> - $n=2$：$(n-2)=0$，第二项消失，$R = \Omega^{-2}[\tilde{R} - 2\tilde{\Box}\ln\Omega]$
> - $n=4$：$R = \Omega^{-2}[\tilde{R} - 6\tilde{\Box}\ln\Omega - 6\tilde{g}^{\mu\nu}(\partial_\mu\ln\Omega)(\partial_\nu\ln\Omega)]$ ← 这直接联系到你之前弯曲时空 QFT 题中 $3+1$ 维 FLRW 的 $R$ 表达式

> [!s]- **(c) FLRW 验证**
>
> 取 $\Omega = a(\eta)$，$\tilde{g}_{\mu\nu} = \eta_{\mu\nu} = \text{diag}(1,-1)$，$\tilde{R}=0$。
>
> $n=2$ 时：
> $$\begin{aligned}
> \tilde{\Box}\ln a &= \eta^{\mu\nu}\partial_\mu\partial_\nu\ln a = \partial_\eta^2\ln a = \frac{a''a - a'^2}{a^2} \\[6pt]
> R &= a^{-2}\big[0 - 2(2-1)\tilde{\Box}\ln a - (2-1)(2-2)(\cdots)\big] \\[4pt]
>   &= -\frac{2}{a^2}\cdot\frac{a''a - a'^2}{a^2} = -\frac{2(a''a - a'^2)}{a^4}
> \end{aligned}$$
>
> 这正是 2.2(c) 的结果。✓
>
> 共形变换公式避免了逐分量计算 $\Gamma$ 和 Riemann——**一次代数运算替换了 2.2 的全部手工推理**。这是共形方法的威力：只要背景度规（Minkowski）的曲率为零，所有弯曲信息都被 $\Omega$ 的导数完全捕获。

---

## 第三章 Einstein 场方程

### 3.1 作用量原理

**(a)** 从 Einstein-Hilbert 作用量出发：
$$S = \frac{1}{16\pi G}\int d^4x\,\sqrt{-g}\,R + S_{\text{matter}}$$
通过对 $g^{\mu\nu}$ 的变分（$\delta\sqrt{-g} = -\frac{1}{2}\sqrt{-g}g_{\mu\nu}\delta g^{\mu\nu}$，$\delta R = R_{\mu\nu}\delta g^{\mu\nu} + \text{全导数项}$），导出 Einstein 方程：
$$R_{\mu\nu} - \frac{1}{2}R g_{\mu\nu} = 8\pi G\,T_{\mu\nu}$$

**(b)** 证明 $G^\mu{}_{\nu;\mu} = 0$（缩并的第二 Bianchi 恒等式），并解释这与 $\nabla_\mu T^{\mu\nu} = 0$ 的自洽性。

> [!s]- **(a) 从作用量到场方程**
>
> **Step 1：变分 $\sqrt{-g}$。** 利用 Jacobi 公式 $\delta\det M = \det M \cdot \text{Tr}(M^{-1}\delta M)$：
>
> $$\delta g = g\,g^{\mu\nu}\delta g_{\mu\nu} = -g\,g_{\mu\nu}\delta g^{\mu\nu}$$
>
> 其中用了 $\delta(g^{\mu\rho}g_{\rho\nu}) = 0 \;\Rightarrow\; \delta g_{\mu\nu} = -g_{\mu\rho}g_{\nu\sigma}\delta g^{\rho\sigma}$。因此：
>
> $$\delta\sqrt{-g} = \frac{\delta g}{2\sqrt{-g}} = -\frac{1}{2}\sqrt{-g}\,g_{\mu\nu}\,\delta g^{\mu\nu}$$
>
> **Step 2：变分 $R$ — 这是整个推导的核心。** $R = g^{\mu\nu}R_{\mu\nu}$：
>
> $$\delta R = \underbrace{\delta g^{\mu\nu}R_{\mu\nu}}_{(i)} + \underbrace{g^{\mu\nu}\delta R_{\mu\nu}}_{(ii)}$$
>
> $(i)$ 简单——$R_{\mu\nu}$ 不参与变分，直接出 $R_{\mu\nu}\delta g^{\mu\nu}$。
>
> $(ii)$ 需要变分 $R_{\mu\nu}$。先抛出三个关键事实，再逐条展开：
>
> **事实一：$\delta\Gamma$ 是张量。** 虽然 $\Gamma$ 不是张量，但两个 Christoffel 符号的**差** $(\Gamma' - \Gamma)$ 是 $(1,2)$ 型张量——因为 1.4 中的非齐次项 $\partial^2 x/\partial x'\partial x'$ 在相减时抵消。$\delta\Gamma^\rho_{\mu\nu} = \Gamma^\rho_{\mu\nu}[g+\delta g] - \Gamma^\rho_{\mu\nu}[g]$ 是两个 Christoffel 的差，所以是张量。因此对它的协变导数 $\nabla_\rho(\delta\Gamma^\lambda_{\mu\nu})$ 有良好定义。
>
> **事实二：Palatini 恒等式。**
> $$\delta R^\rho{}_{\sigma\mu\nu} = \nabla_\mu(\delta\Gamma^\rho_{\nu\sigma}) - \nabla_\nu(\delta\Gamma^\rho_{\mu\sigma})$$
>
> 证明：回忆 $R^\rho{}_{\sigma\mu\nu} = \partial_\mu\Gamma^\rho_{\nu\sigma} - \partial_\nu\Gamma^\rho_{\mu\sigma} + \Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma} - \Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma}$。变分：
>
> $$\delta R^\rho{}_{\sigma\mu\nu} = \partial_\mu(\delta\Gamma^\rho_{\nu\sigma}) - \partial_\nu(\delta\Gamma^\rho_{\mu\sigma}) + \delta\Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma} + \Gamma^\rho_{\mu\lambda}\delta\Gamma^\lambda_{\nu\sigma} - \delta\Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma} - \Gamma^\rho_{\nu\lambda}\delta\Gamma^\lambda_{\mu\sigma}$$
>
> 另一方面，计算 $\nabla_\mu(\delta\Gamma^\rho_{\nu\sigma})$：
> $$\nabla_\mu(\delta\Gamma^\rho_{\nu\sigma}) = \partial_\mu(\delta\Gamma^\rho_{\nu\sigma}) + \Gamma^\rho_{\mu\lambda}\delta\Gamma^\lambda_{\nu\sigma} - \Gamma^\lambda_{\mu\nu}\delta\Gamma^\rho_{\lambda\sigma} - \Gamma^\lambda_{\mu\sigma}\delta\Gamma^\rho_{\nu\lambda}$$
>
> 同理 $\nabla_\nu(\delta\Gamma^\rho_{\mu\sigma})$，相减：
> $$\begin{aligned}
> \nabla_\mu(\delta\Gamma^\rho_{\nu\sigma}) - \nabla_\nu(\delta\Gamma^\rho_{\mu\sigma}) 
> &= \partial_\mu(\delta\Gamma^\rho_{\nu\sigma}) - \partial_\nu(\delta\Gamma^\rho_{\mu\sigma}) \\
> &+ \Gamma^\rho_{\mu\lambda}\delta\Gamma^\lambda_{\nu\sigma} - \cancel{\Gamma^\lambda_{\mu\nu}\delta\Gamma^\rho_{\lambda\sigma}} - \Gamma^\lambda_{\mu\sigma}\delta\Gamma^\rho_{\nu\lambda} \\
> &- \Gamma^\rho_{\nu\lambda}\delta\Gamma^\lambda_{\mu\sigma} + \cancel{\Gamma^\lambda_{\nu\mu}\delta\Gamma^\rho_{\lambda\sigma}} + \Gamma^\lambda_{\nu\sigma}\delta\Gamma^\rho_{\mu\lambda}
> \end{aligned}$$
>
> 划掉的项抵消（$\Gamma$ 下标对称 $\Gamma^\lambda_{\mu\nu} = \Gamma^\lambda_{\nu\mu}$）。剩下的 $-\Gamma^\lambda_{\mu\sigma}\delta\Gamma^\rho_{\nu\lambda} + \Gamma^\lambda_{\nu\sigma}\delta\Gamma^\rho_{\mu\lambda}$ 对应 $\delta\Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma}$ vs $\delta\Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma}$（重新标记哑指标 $\lambda$），与 $\delta R$ 展开式中 $\Gamma\Gamma$ 变分项精确匹配。
>
> $$\boxed{\delta R^\rho{}_{\sigma\mu\nu} = \nabla_\mu(\delta\Gamma^\rho_{\nu\sigma}) - \nabla_\nu(\delta\Gamma^\rho_{\mu\sigma})}$$
>
> 缩并 $\rho$ 与 $\mu$：
> $$\boxed{\delta R_{\sigma\nu} = \nabla_\rho(\delta\Gamma^\rho_{\nu\sigma}) - \nabla_\nu(\delta\Gamma^\rho_{\rho\sigma})}$$
>
> **事实三：$g^{\mu\nu}\delta R_{\mu\nu}$ 是全导数，积分为零。**
>
> $$g^{\mu\nu}\delta R_{\mu\nu} = \nabla_\rho\big(g^{\mu\nu}\delta\Gamma^\rho_{\nu\mu} - g^{\mu\rho}\delta\Gamma^\nu_{\nu\mu}\big)$$
>
> 在积分中：
> $$\int d^4x\,\sqrt{-g}\,g^{\mu\nu}\delta R_{\mu\nu} = \int d^4x\,\sqrt{-g}\,\nabla_\rho V^\rho = \int d^4x\,\partial_\rho(\sqrt{-g}\,V^\rho)$$
>
> 这是边界项，变分原理中边界上 $\delta g^{\mu\nu} = 0$ 强制 $\delta\Gamma = 0$，故积分为零。
>
> **结论**：$\delta R$ 中只有 $(i)$ 存活：
> $$\boxed{\delta R = R_{\mu\nu}\,\delta g^{\mu\nu}}$$
>
> 这个结果不显然——$R$ 含度规的二阶导数，变分本应产生三阶导数。但 Hilbert 在 1915 年发现 $g^{\mu\nu}\delta R_{\mu\nu}$ 恰好是散度，使 Einstein-Hilbert 作用量只产生二阶场方程。**这不是巧合，这是 Lovelock 定理的 $n=2$ 体现：Einstein-Hilbert 是唯一产生二阶场方程的标量曲率作用量。**
>
> **Step 3：组装。** Einstein-Hilbert 部分的变分：
>
> $$\begin{aligned}
> \delta S_{\text{EH}} &= \frac{1}{16\pi G}\int d^4x\Big[\delta\sqrt{-g}\,R + \sqrt{-g}\,\delta R\Big] \\[4pt]
> &= \frac{1}{16\pi G}\int d^4x\,\sqrt{-g}\Big[-\frac{1}{2}R\,g_{\mu\nu} + R_{\mu\nu}\Big]\delta g^{\mu\nu}
> \end{aligned}$$
>
> 物质部分：按定义 $T_{\mu\nu} = -\frac{2}{\sqrt{-g}}\frac{\delta S_{\text{matter}}}{\delta g^{\mu\nu}}$：
>
> $$\delta S_{\text{matter}} = -\frac{1}{2}\int d^4x\,\sqrt{-g}\,T_{\mu\nu}\,\delta g^{\mu\nu}$$
>
> 要求 $\delta S_{\text{EH}} + \delta S_{\text{matter}} = 0$ 对任意 $\delta g^{\mu\nu}$ 成立：
>
> $$\boxed{R_{\mu\nu} - \frac{1}{2}R\,g_{\mu\nu} = 8\pi G\,T_{\mu\nu}}$$

> [!s]- **(b) 缩并 Bianchi 恒等式与自洽性**
>
> **证明 $G^\mu{}_{\nu;\mu}=0$。** 第二 Bianchi 恒等式：
> $$\nabla_{[\lambda}R_{\rho\sigma]\mu\nu} = 0$$
>
> 与 $g^{\rho\mu}g^{\sigma\nu}$ 缩并。利用 $g$ 的度规相容性（$\nabla g=0$），$g$ 可自由进出协变导数：
> $$g^{\rho\mu}g^{\sigma\nu}\nabla_\lambda R_{\rho\sigma\mu\nu} - g^{\rho\mu}g^{\sigma\nu}\nabla_\rho R_{\sigma\lambda\mu\nu} + \cdots = 0$$
>
> 前两项整理后给出 $\nabla^\mu R_{\mu\lambda} - \frac{1}{2}\nabla_\lambda R = 0$，即：
>
> $$\boxed{\nabla_\mu G^{\mu\nu} = 0}$$
>
> **自洽性论证**：Einstein 方程左边 $G^{\mu\nu}$ 的散度恒为零（几何恒等式），因此右边 $T^{\mu\nu}$ 的散度也必须恒为零：
>
> $$\nabla_\mu T^{\mu\nu} = 0$$
>
> 这不是额外假设——是场方程的**自洽性要求**。如果 $T^{\mu\nu}$ 不守恒，就没有度规解能满足 Einstein 方程。反过来，这也可以从物质作用量的微分同胚不变性独立证明（Noether 第二定理），两者一致构成了 GR 的内在完整性。

### 3.2 宇宙学常数

**(a)** 在 Einstein-Hilbert 作用量中加入宇宙学常数项：
$$S_\Lambda = -\frac{\Lambda}{8\pi G}\int d^4x\,\sqrt{-g}$$
变分导出场方程 $G_{\mu\nu} + \Lambda g_{\mu\nu} = 8\pi G\,T_{\mu\nu}$。

**(b)** 证明 $\Lambda$ 可以解释为真空能量密度 $\rho_{\text{vac}} = \Lambda/8\pi G$，压强 $p_{\text{vac}} = -\rho_{\text{vac}}$（即 $T_{\mu\nu}^{\text{vac}} = -\rho_{\text{vac}}g_{\mu\nu}$）。

> [!s]- **(a) 场方程中的宇宙学常数项**
>
> 全作用量 $S = S_{\text{EH}} + S_\Lambda + S_{\text{matter}}$，其中：
> $$S_\Lambda = -\frac{\Lambda}{8\pi G}\int d^4x\,\sqrt{-g}$$
>
> 变分：$\delta(\sqrt{-g}) = -\frac{1}{2}\sqrt{-g}\,g_{\mu\nu}\delta g^{\mu\nu}$（与 3.1(a) Step 1 相同）：
>
> $$\begin{aligned}
> \delta S_\Lambda &= -\frac{\Lambda}{8\pi G}\int d^4x\,\delta(\sqrt{-g}) \\[4pt]
> &= -\frac{\Lambda}{8\pi G}\int d^4x\left(-\frac{1}{2}\sqrt{-g}\,g_{\mu\nu}\delta g^{\mu\nu}\right) \\[4pt]
> &= \frac{\Lambda}{16\pi G}\int d^4x\,\sqrt{-g}\,g_{\mu\nu}\,\delta g^{\mu\nu}
> \end{aligned}$$
>
> 与 3.1(a) 的 $\delta S_{\text{EH}}$ 合并：
>
> $$\delta S_{\text{EH}} + \delta S_\Lambda = \frac{1}{16\pi G}\int d^4x\,\sqrt{-g}\Big[R_{\mu\nu} - \frac{1}{2}R\,g_{\mu\nu} + \Lambda\,g_{\mu\nu}\Big]\delta g^{\mu\nu}$$
>
> $\delta S_{\text{matter}}$ 不变。对任意 $\delta g^{\mu\nu}$ 为零：
>
> $$\boxed{R_{\mu\nu} - \frac{1}{2}R\,g_{\mu\nu} + \Lambda\,g_{\mu\nu} = 8\pi G\,T_{\mu\nu}}$$
>
> 或用 Einstein 张量记法：$G_{\mu\nu} + \Lambda g_{\mu\nu} = 8\pi G\,T_{\mu\nu}$。
>
> $\Lambda$ 项的符号约定：这里是 $(+ \Lambda g_{\mu\nu})$，意味着正 $\Lambda$ 等效于排斥性引力（与真空能的负压一致）。

> [!s]- **(b) 真空能解释**
>
> 将 $\Lambda$ 项移到方程右边：
> $$G_{\mu\nu} = 8\pi G\,T_{\mu\nu} - \Lambda\,g_{\mu\nu} = 8\pi G\Big(T_{\mu\nu} - \frac{\Lambda}{8\pi G}\,g_{\mu\nu}\Big)$$
>
> 定义**真空能动张量**：
> $$T_{\mu\nu}^{\text{vac}} \equiv -\frac{\Lambda}{8\pi G}\,g_{\mu\nu} = -\rho_{\text{vac}}\,g_{\mu\nu}$$
>
> 其中 $\rho_{\text{vac}} \equiv \Lambda/8\pi G$。
>
> 与理想流体形式 $T_{\mu\nu} = (\rho+p)u_\mu u_\nu + p\,g_{\mu\nu}$ 对比。在静系（$u^\mu = (1,0,0,0)$）：
> $$T_{00} = \rho,\quad T_{ij} = p\,\delta_{ij}$$
>
> 而 $T_{\mu\nu}^{\text{vac}} = -\rho_{\text{vac}}\,g_{\mu\nu}$。在局域惯性系中 $g_{\mu\nu} = (-1,1,1,1)$：
> $$T_{00}^{\text{vac}} = -\rho_{\text{vac}}\cdot(-1) = \rho_{\text{vac}},\qquad T_{ij}^{\text{vac}} = -\rho_{\text{vac}}\cdot\delta_{ij}$$
>
> 对比得：
>
> $$\boxed{p_{\text{vac}} = -\rho_{\text{vac}}}$$
>
> 负压是真空能的标志——膨胀做功时 $dU = -p\,dV = +\rho_{\text{vac}}\,dV$，能量不降反升。这意味着 $\Lambda > 0$ 的宇宙在膨胀中真空能量密度保持恒定（这正是 $\rho \propto a^0$ 的物态方程来源），导致**加速膨胀**。

### 3.3 理想流体的能动张量

**(a)** 写出理想流体的能动张量：
$$T^{\mu\nu} = (\rho + p)u^\mu u^\nu + p g^{\mu\nu}$$

**(b)** 对 FLRW 度规（$u^\mu = (1/a, 0)$），验证 $\nabla_\mu T^{\mu\nu} = 0$ 给出连续性方程：
$$\dot{\rho} + 3\frac{\dot{a}}{a}(\rho + p) = 0\quad\text{（$3+1$ 维）}$$

**(c)** 推导三种物态方程下的 $\rho(a)$：
- 辐射：$p = \rho/3 \;\Rightarrow\; \rho \propto a^{-4}$
- 尘埃：$p = 0 \;\Rightarrow\; \rho \propto a^{-3}$
- 真空能：$p = -\rho \;\Rightarrow\; \rho = \text{常数}$

> [!s]- **(a) 理想流体的能动张量**
>
> 在局域静系中 $T_{\mu\nu} = \text{diag}(\rho, p, p, p)$。为写成协变形式，唯一可用的几何量是 $u^\mu$（四速度，$u^\mu u_\mu = -1$）和 $g^{\mu\nu}$。满足静系对角形式的唯一组合：
>
> $$\boxed{T^{\mu\nu} = (\rho + p)u^\mu u^\nu + p\,g^{\mu\nu}}$$
>
> 验证：在静系 $u^\mu = (1,0,0,0)$，$g^{\mu\nu} = \text{diag}(-1,1,1,1)$：
> $$T^{00} = (\rho+p)\cdot 1 + p\cdot(-1) = \rho,\quad T^{ij} = 0 + p\,\delta^{ij}$$
>
> 迹：$T^\mu{}_\mu = g_{\mu\nu}T^{\mu\nu} = -\rho + 3p$。对辐射（$p=\rho/3$）迹为零——这是经典共形不变性的标志。

> [!s]- **(b) $\nabla_\mu T^{\mu\nu}=0$ 在 FLRW 背景下**
>
> $3+1$ 维 FLRW 共形时间度规：$ds^2 = a^2(\eta)(-d\eta^2 + d\mathbf{x}^2)$，$\sqrt{-g}=a^4$。
>
> 共动观测者 $u^\mu = (1/a, 0, 0, 0)$，$u^\mu u_\mu = -1$。能动张量分量：
> $$T^{\eta\eta} = \frac{\rho}{a^2},\qquad T^{\eta i} = 0,\qquad T^{ij} = \frac{p}{a^2}\,\delta^{ij}$$
>
> 计算 $\nabla_\mu T^{\mu\eta} = 0$（$\nu=\eta$ 分量；$\nu=i$ 自动满足）：$\nabla_\mu T^{\mu\eta} = \partial_\mu T^{\mu\eta} + \Gamma^\mu_{\mu\lambda}T^{\lambda\eta} + \Gamma^\eta_{\mu\lambda}T^{\mu\lambda}$。
>
> **第一项**：$\partial_\mu T^{\mu\eta} = \partial_\eta T^{\eta\eta} = \partial_\eta(\rho/a^2) = \rho'/a^2 - 2\rho a'/a^3$。
>
> **第二项**：$\Gamma^\mu_{\mu\lambda}T^{\lambda\eta} = \Gamma^\mu_{\mu\eta}T^{\eta\eta}$。$\Gamma^\mu_{\mu\eta} = \partial_\eta\ln\sqrt{-g} = \partial_\eta\ln a^4 = 4a'/a$。
> $$= \frac{4a'}{a}\cdot\frac{\rho}{a^2} = \frac{4\rho a'}{a^3}$$
>
> **第三项**：非零 $T^{\mu\lambda}$ 为 $T^{\eta\eta}$ 和 $T^{ij}$。
> $\Gamma^\eta_{\eta\eta} = a'/a$，$\Gamma^\eta_{ij} = (a'/a)\delta_{ij}$。
> $$= \frac{a'}{a}\cdot\frac{\rho}{a^2} + \frac{a'}{a}\delta_{ij}\cdot\frac{p}{a^2}\delta^{ij} = \frac{\rho a'}{a^3} + \frac{3p a'}{a^3}$$
>
> **三项求和**：
> $$\nabla_\mu T^{\mu\eta} = \frac{\rho'}{a^2} + (-2+4+1)\frac{\rho a'}{a^3} + \frac{3p a'}{a^3} = \frac{\rho'}{a^2} + \frac{3(\rho+p)a'}{a^3} = 0$$
>
> 记 $\dot{\;} \equiv d/d\eta$：
>
> $$\boxed{\dot{\rho} + 3\frac{\dot{a}}{a}(\rho + p) = 0}$$
>
> 转换到宇宙时 $t$（$dt = a\,d\eta$）：$d\rho/dt + 3H(\rho+p) = 0$，$H = \dot{a}/a$（物理 Hubble 参数）。

> [!s]- **(c) 三种宇宙学流体的演化**
>
> 将物态方程 $p = w\rho$ 代入 (b)：
> $$\frac{d\rho}{\rho} = -3(1+w)\frac{da}{a} \;\Rightarrow\; \rho(a) \propto a^{-3(1+w)}$$
>
> | 成分 | $w$ | $\rho(a)$ | 物理解释 |
> |------|-----|-----------|----------|
> | 辐射 | $1/3$ | $\rho \propto a^{-4}$ | 数密度 $\propto a^{-3}$ + 红移 $\propto a^{-1}$ |
> | 尘埃（物质） | $0$ | $\rho \propto a^{-3}$ | 纯数密度稀释 |
> | 真空能（$\Lambda$） | $-1$ | $\rho = \text{常数}$ | $p=-\rho \Rightarrow$ 膨胀不做净功 |
> | 曲率等效流体 | $-1/3$ | $\rho \propto a^{-2}$ | $k/a^2$ 项的等效物态方程 |
>
> **交叉点**：$a$ 从小变大时，辐射 $\to$ 物质 $\to$ 真空能 依次主导——这就是标准 $\Lambda$CDM 宇宙的热历史。

### 3.4 标量场的能动张量

对 $\mathcal{L} = -\frac{1}{2}g^{\mu\nu}\partial_\mu\phi\,\partial_\nu\phi - V(\phi)$：

**(a)** 用 $T_{\mu\nu} = -\frac{2}{\sqrt{-g}}\frac{\delta S_{\text{matter}}}{\delta g^{\mu\nu}}$ 推导：
$$T_{\mu\nu} = \partial_\mu\phi\,\partial_\nu\phi - g_{\mu\nu}\left[\frac{1}{2}g^{\alpha\beta}\partial_\alpha\phi\,\partial_\beta\phi + V(\phi)\right]$$

**(b)** 对共形平直 FLRW 背景，取 $\phi = \phi(\eta)$ 只依赖共形时间，计算 $T_{\eta\eta}$ 和 $T_{xx}$（$1+1$ 维），验证 $T^\mu{}_\mu = -2V(\phi)$（$1+1$ 维无质量时迹为零）。

> [!s]- **(a) 标量场能动张量的推导**
>
> 作用量 $S = \int d^4x\,\sqrt{-g}\,\mathcal{L}$，$\mathcal{L} = -\frac{1}{2}g^{\mu\nu}\partial_\mu\phi\,\partial_\nu\phi - V(\phi)$。
>
> 变分 $\delta S/\delta g^{\mu\nu}$ 时，$g^{\mu\nu}$ 出现在 $\sqrt{-g}$（通过行列式）和 $\mathcal{L}$ 中：
>
> **行列式部分**：$\delta\sqrt{-g} = -\frac{1}{2}\sqrt{-g}\,g_{\mu\nu}\,\delta g^{\mu\nu}$
> $$\delta(\sqrt{-g})\mathcal{L} = -\frac{1}{2}\sqrt{-g}\,g_{\mu\nu}\mathcal{L}\,\delta g^{\mu\nu}$$
>
> **Lagrangian 部分**：$\mathcal{L}$ 对 $g^{\mu\nu}$ 的显式依赖仅来自动能项：
> $$\delta\mathcal{L} = -\frac{1}{2}\partial_\mu\phi\,\partial_\nu\phi\,\delta g^{\mu\nu}$$
>
> 合并：
> $$\begin{aligned}
> \delta S &= \int d^4x\Big[\delta(\sqrt{-g})\mathcal{L} + \sqrt{-g}\,\delta\mathcal{L}\Big] \\[4pt]
> &= \int d^4x\,\sqrt{-g}\Big[-\frac{1}{2}g_{\mu\nu}\mathcal{L} - \frac{1}{2}\partial_\mu\phi\,\partial_\nu\phi\Big]\delta g^{\mu\nu} \\[4pt]
> &= -\frac{1}{2}\int d^4x\,\sqrt{-g}\Big[g_{\mu\nu}\mathcal{L} + \partial_\mu\phi\,\partial_\nu\phi\Big]\delta g^{\mu\nu}
> \end{aligned}$$
>
> 按定义 $T_{\mu\nu} = -\frac{2}{\sqrt{-g}}\frac{\delta S}{\delta g^{\mu\nu}}$：
> $$T_{\mu\nu} = g_{\mu\nu}\mathcal{L} + \partial_\mu\phi\,\partial_\nu\phi$$
>
> 代入 $\mathcal{L} = -\frac{1}{2}g^{\alpha\beta}\partial_\alpha\phi\,\partial_\beta\phi - V(\phi)$：
>
> $$\boxed{T_{\mu\nu} = \partial_\mu\phi\,\partial_\nu\phi - g_{\mu\nu}\left[\frac{1}{2}g^{\alpha\beta}\partial_\alpha\phi\,\partial_\beta\phi + V(\phi)\right]}$$
>
> 这个形式是普遍的——对任何度规背景、任何维数均成立。签名约定决定了 $g_{\mu\nu}\mathcal{L}$ 前的符号，但物理内容不变。

> [!s]- **(b) FLRW 背景下的显式计算**
>
> $1+1$ 维 FLRW 共形度规：$ds^2 = a^2(\eta)(d\eta^2 - dx^2)$。$g_{\eta\eta}=a^2$, $g_{xx}=-a^2$, $g^{\eta\eta}=1/a^2$, $g^{xx}=-1/a^2$。
>
> $\phi = \phi(\eta)$ 仅依赖 $\eta$，记 $\phi' \equiv d\phi/d\eta$。
>
> 动能项：$g^{\alpha\beta}\partial_\alpha\phi\,\partial_\beta\phi = g^{\eta\eta}(\phi')^2 = (\phi')^2/a^2$。
>
> **$T_{\eta\eta}$：**
> $$\begin{aligned}
> T_{\eta\eta} &= \underbrace{\phi'\cdot\phi'}_{(\phi')^2} - g_{\eta\eta}\left[\frac{1}{2}\frac{(\phi')^2}{a^2} + V(\phi)\right] \\[4pt]
> &= (\phi')^2 - a^2\left[\frac{(\phi')^2}{2a^2} + V(\phi)\right] \\[4pt]
> &= (\phi')^2 - \frac{1}{2}(\phi')^2 - a^2V(\phi) \\[4pt]
> &= \boxed{\frac{1}{2}(\phi')^2 - a^2V(\phi)}
> \end{aligned}$$
>
> **$T_{xx}$：**
> $$\begin{aligned}
> T_{xx} &= \underbrace{\partial_x\phi\,\partial_x\phi}_{0} - g_{xx}\left[\frac{1}{2}\frac{(\phi')^2}{a^2} + V(\phi)\right] \\[4pt]
> &= 0 - (-a^2)\left[\frac{(\phi')^2}{2a^2} + V(\phi)\right] \\[4pt]
> &= \boxed{\frac{1}{2}(\phi')^2 + a^2V(\phi)}
> \end{aligned}$$
>
> 能量密度 $\rho = T^\eta{}_\eta = g^{\eta\eta}T_{\eta\eta} = \frac{1}{a^2}\left[\frac{1}{2}(\phi')^2 - a^2V\right] = \frac{(\phi')^2}{2a^2} - V(\phi)$。
>
> 压强 $p = T^x{}_x = g^{xx}T_{xx} = -\frac{1}{a^2}\left[\frac{1}{2}(\phi')^2 + a^2V\right] = -\frac{(\phi')^2}{2a^2} - V(\phi)$。
>
> **迹：**
> $$\begin{aligned}
> T^\mu{}_\mu &= T^\eta{}_\eta + T^x{}_x \\[4pt]
> &= \left[\frac{(\phi')^2}{2a^2} - V(\phi)\right] + \left[-\frac{(\phi')^2}{2a^2} - V(\phi)\right] \\[4pt]
> &= \boxed{-2V(\phi)}
> \end{aligned}$$
>
> **关键推论**：当 $V = 0$（无质量），$T^\mu{}_\mu = 0$。经典共形不变性要求能动张量无迹——$1+1$ 维最小耦合（$\xi=0$）的无质量标量场恰好满足这一点，和你在 [[膨胀宇宙中的粒子产生]] II.3(b) 中得到的 $\omega_k^2 = k^2$（常数）是同一事实的两个不同面貌：迹为零 $\Leftrightarrow$ 共形不变 $\Leftrightarrow$ 无粒子产生。

---


## 第四章 Schwarzschild 解

### 4.1 Birkhoff 定理的推导

**(a)** 从球对称静态度规的试探形式出发：
$$ds^2 = -e^{2\Phi(r)}dt^2 + e^{2\Lambda(r)}dr^2 + r^2 d\Omega^2$$
计算 Christoffel 符号和 Ricci 张量。

**(b)** 真空 Einstein 方程 $R_{\mu\nu} = 0$：
- $R_{tt} = 0 \;\Rightarrow\; \Phi'' + \Phi'^2 - \Phi'\Lambda' + 2\Phi'/r = 0$
- $R_{rr} = 0 \;\Rightarrow\; \Phi'' + \Phi'^2 - \Phi'\Lambda' - 2\Lambda'/r = 0$
- $R_{\theta\theta} = 0 \;\Rightarrow\; e^{-2\Lambda}(1 + r(\Phi'-\Lambda')) - 1 = 0$

**(c)** 由 $R_{tt} - R_{rr} = 0$ 得到 $\Phi'+\Lambda'=0 \Rightarrow \Phi = -\Lambda + \text{const}$。结合 $R_{\theta\theta}=0$，推导：
$$e^{2\Phi} = e^{-2\Lambda} = 1 - \frac{r_s}{r}$$
其中 $r_s$ 为积分常数。

**(d)** 通过弱场近似（牛顿极限：$g_{00} \approx -(1+2\Phi_N)$，$\Phi_N = -GM/r$），证明 $r_s = 2GM$。

> [!s]- **(c) 求解 $\Phi$ 和 $\Lambda$**
>
> **Step 1：$R_{tt} - R_{rr} = 0$。**
>
> $$\begin{aligned}
> &[\Phi'' + \Phi'^2 - \Phi'\Lambda' + 2\Phi'/r] - [\Phi'' + \Phi'^2 - \Phi'\Lambda' - 2\Lambda'/r] = 0 \\[4pt]
> &\frac{2\Phi'}{r} + \frac{2\Lambda'}{r} = 0 \quad\Rightarrow\quad \Phi' + \Lambda' = 0
> \end{aligned}$$
>
> 积分：$\Phi(r) + \Lambda(r) = C$。渐近平直条件（$r\to\infty$ 时 $g_{\mu\nu}\to\eta_{\mu\nu}$）要求 $\Phi\to 0$, $\Lambda\to 0$，故 $C=0$：
>
> $$\boxed{\Lambda(r) = -\Phi(r)}$$
>
> **Step 2：代入 $R_{\theta\theta}=0$。**
>
> $$e^{-2\Lambda}(1 + r(\Phi' - \Lambda')) - 1 = 0$$
>
> 用 $\Lambda = -\Phi$，则 $\Phi' - \Lambda' = \Phi' - (-\Phi') = 2\Phi'$，$e^{-2\Lambda} = e^{2\Phi}$：
>
> $$e^{2\Phi}(1 + 2r\Phi') = 1$$
>
> **关键洞察**：上式左边恰好是全导数：
> $$\frac{d}{dr}\big(r e^{2\Phi}\big) = e^{2\Phi} + 2r\Phi' e^{2\Phi} = e^{2\Phi}(1 + 2r\Phi')$$
>
> 所以 $R_{\theta\theta}=0 \;\Leftrightarrow\; \frac{d}{dr}(r e^{2\Phi}) = 1$。
>
> **Step 3：积分。**
>
> $$r e^{2\Phi} = r - r_s \quad\Rightarrow\quad e^{2\Phi} = 1 - \frac{r_s}{r}$$
>
> 其中 $r_s$ 为积分常数。由 $\Lambda = -\Phi$：
>
> $$e^{2\Lambda} = e^{-2\Phi} = \frac{1}{1 - r_s/r}$$
>
> $$\boxed{g_{tt} = -e^{2\Phi} = -\Big(1 - \frac{r_s}{r}\Big),\qquad g_{rr} = e^{2\Lambda} = \Big(1 - \frac{r_s}{r}\Big)^{-1}}$$
>
> $r_s$ 的符号：若 $r_s<0$，则对所有 $r$ 有 $g_{tt}<0$（无事件视界），这是裸奇点解——物理上不可接受。因此 $r_s>0$。

> [!s]- **(d) 弱场极限与 $r_s = 2GM$**
>
> 在 $r \gg r_s$ 处，Schwarzschild 度规退化为弱场。低速粒子（$v\ll c$）的测地线方程在弱场下化为 Newton 第二定律：
> $$\frac{d^2 x^i}{dt^2} \approx -\frac{1}{2}\partial_i g_{00}$$
>
> Newton 引力中：$\frac{d^2 x^i}{dt^2} = -\partial_i\Phi_N$，其中 Newton 势 $\Phi_N = -GM/r$。
>
> 对比得 $g_{00} \approx -(1 + 2\Phi_N) = -\Big(1 - \frac{2GM}{r}\Big)$。
>
> 而 Schwarzschild 解给出 $g_{00} = -\Big(1 - \frac{r_s}{r}\Big)$。
>
> 逐项匹配：
> $$1 - \frac{r_s}{r} = 1 - \frac{2GM}{r} \quad\Rightarrow\quad \boxed{r_s = 2GM}$$
>
> 恢复 $c$：$r_s = 2GM/c^2$。对太阳 $r_s \approx 3$ km，对地球 $r_s \approx 9$ mm。

### 4.2 测地线与守恒量

**(a)** 对 Schwarzschild 度规，从 Lagrangian $L = \frac{1}{2}g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu$ 出发：
- 由于 $g_{\mu\nu}$ 不显含 $t$ 和 $\phi$，写出两个守恒量 $E$ 和 $L$（能量与角动量）。
- 写出 $\theta$ 方向的运动方程，并解释为何可以选择赤道面 $\theta = \pi/2$。

**(b)** 利用守恒量和类时条件 $g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu = -1$，导出有效势方程：
$$\frac{1}{2}\dot{r}^2 + V_{\text{eff}}(r) = \frac{E^2 - 1}{2}$$
其中：
$$V_{\text{eff}}(r) = -\frac{GM}{r} + \frac{L^2}{2r^2} - \frac{GML^2}{r^3}$$

**(c)** 解释有效势中三项的物理含义（牛顿引力势、离心势、GR 修正）。

> [!s]- **(a) 守恒量与赤道面**
>
> Schwarzschild 度规：$ds^2 = -\big(1-\frac{2GM}{r}\big)dt^2 + \big(1-\frac{2GM}{r}\big)^{-1}dr^2 + r^2(d\theta^2 + \sin^2\theta\,d\phi^2)$。
>
> Lagrangian：$L = \frac{1}{2}g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu$（$\dot{}\; \equiv d/d\tau$）：
> $$L = \frac{1}{2}\Big[-\Big(1-\frac{2GM}{r}\Big)\dot{t}^2 + \Big(1-\frac{2GM}{r}\Big)^{-1}\dot{r}^2 + r^2(\dot{\theta}^2 + \sin^2\theta\,\dot{\phi}^2)\Big]$$
>
> **$t$ 不显含** $\Rightarrow$ 能量守恒。Euler-Lagrange：$\frac{d}{d\tau}\frac{\partial L}{\partial\dot{t}} = \frac{\partial L}{\partial t} = 0$：
> $$\frac{\partial L}{\partial\dot{t}} = -\Big(1-\frac{2GM}{r}\Big)\dot{t} = -E = \text{const}$$
> $$\boxed{E = \Big(1-\frac{2GM}{r}\Big)\dot{t}}$$
>
> **$\phi$ 不显含** $\Rightarrow$ 角动量守恒：
> $$\frac{\partial L}{\partial\dot{\phi}} = r^2\sin^2\theta\,\dot{\phi} = L = \text{const}$$
>
> **$\theta$ 方向**：$\frac{d}{d\tau}(r^2\dot{\theta}) = r^2\sin\theta\cos\theta\,\dot{\phi}^2$。若初始条件取 $\theta = \pi/2$，$\dot{\theta}=0$，则 $\ddot{\theta}=0$（因为 $\sin\frac{\pi}{2}\cos\frac{\pi}{2}=0$）。粒子始终停在赤道面。
>
> 这不是近似——**球对称保证角动量矢量守恒，坐标系总可旋转使角动量沿 $z$ 轴，即运动始终在 $\theta=\pi/2$ 平面**。此后 $\theta=\pi/2$，$\dot{\theta}=0$。

> [!s]- **(b) 有效势方程**
>
> 类时测地线的归一化条件 $g_{\mu\nu}\dot{x}^\mu\dot{x}^\nu = -1$。代入 $\theta=\pi/2$ 和守恒量 $\dot{t}=E/(1-2GM/r)$，$\dot{\phi}=L/r^2$：
>
> $$-\Big(1-\frac{2GM}{r}\Big)\left[\frac{E}{1-2GM/r}\right]^2 + \Big(1-\frac{2GM}{r}\Big)^{-1}\dot{r}^2 + r^2\Big(\frac{L}{r^2}\Big)^2 = -1$$
>
> 化简第一项：$-\frac{E^2}{1-2GM/r}$。通乘 $\frac{1}{2}(1-\frac{2GM}{r})$：
> $$-\frac{1}{2}E^2 + \frac{1}{2}\dot{r}^2 + \frac{1}{2}\Big(1-\frac{2GM}{r}\Big)\frac{L^2}{r^2} = -\frac{1}{2}\Big(1-\frac{2GM}{r}\Big)$$
>
> $$\frac{1}{2}\dot{r}^2 = \frac{1}{2}(E^2 - 1) + \frac{GM}{r} - \frac{L^2}{2r^2} + \frac{GML^2}{r^3}$$
>
> $$\boxed{\frac{1}{2}\dot{r}^2 + V_{\text{eff}}(r) = \frac{E^2 - 1}{2},\qquad V_{\text{eff}}(r) = -\frac{GM}{r} + \frac{L^2}{2r^2} - \frac{GML^2}{r^3}}$$

> [!s]- **(c) 三项的物理含义**
>
> $$V_{\text{eff}}(r) = \underbrace{-\frac{GM}{r}}_{\text{①}} + \underbrace{\frac{L^2}{2r^2}}_{\text{②}} - \underbrace{\frac{GML^2}{r^3}}_{\text{③}}$$
>
> | 项 | 来源 | 物理 | $r$ 依赖 |
> |----|------|------|----------|
> | ① | Newton 引力势 | 质量产生的吸引力 | $\sim 1/r$ |
> | ② | 角动量守恒 | 离心势垒，阻止塌缩 | $\sim 1/r^2$ |
> | ③ | GR 修正 | 强场下引力的额外增强 | $\sim 1/r^3$ |
>
> **Newton 极限**：仅 ① + ②，形如 $V_{\text{Newton}} = -GM/r + L^2/(2r^2)$。存在最小值，所有束缚轨道都是闭合的椭圆。
>
> **GR 修正 ③**：在大 $r$ 处可忽略，在 $r \sim 3GM$ 处与 ② 同量级。关键效应：
> - 有效势在 $r \approx 3GM$ 处出现**极大值**——Newton 引力中没有的势垒顶
> - 存在**最内稳定圆轨道**（ISCO）$r_{\text{ISCO}} = 6GM$。$r < r_{\text{ISCO}}$ 的任何圆轨道都不稳定——微小扰动即导致坠入视界
> - 离心势垒不足以阻挡角动量极高的粒子——GR 的额外吸引克服了离心排斥
>
> 这就是水星近日点进动和黑洞吸积盘内边缘的几何根源。

### 4.3 水星近日点进动

**(a)** 从测地线方程导出 $r(\phi)$ 满足的 Binet 公式（令 $u = 1/r$）：
$$\frac{d^2u}{d\phi^2} + u = \frac{GM}{L^2} + 3GM u^2$$

**(b)** 将右边最后一项作为微扰（$\epsilon = 3GM u^2$），在 Newtonian 解 $u_0 = \frac{GM}{L^2}(1+e\cos\phi)$ 的基础上，证明每圈的进动角为：
$$\Delta\phi = \frac{6\pi GM}{a(1-e^2)}$$
其中 $a$ 为半长轴，$e$ 为偏心率。

**(c)** 代入水星数据（$a = 5.79\times 10^{10}$ m，$e = 0.2056$，$M_\odot = 1.989\times 10^{30}$ kg），计算每世纪的进动角（水星轨道周期 87.97 天）。与观测值 $43''/\text{世纪}$ 比较。

> [!s]- **(a) Binet 公式**
>
> 从 4.2(b) 的有效势方程出发：$\frac{1}{2}\dot{r}^2 - \frac{GM}{r} + \frac{L^2}{2r^2} - \frac{GML^2}{r^3} = \frac{E^2-1}{2}$。
>
> 换变量：$u = 1/r$，$r = 1/u$，$dr/du = -1/u^2$。用链式法则消去 $\tau$：
> $$\dot{r} = \frac{dr}{d\phi}\frac{d\phi}{d\tau} = \frac{dr}{d\phi}\cdot\frac{L}{r^2} = \frac{dr}{d\phi}\,L u^2$$
>
> $$\frac{dr}{d\phi} = \frac{d(1/u)}{d\phi} = -\frac{1}{u^2}\frac{du}{d\phi} \quad\Rightarrow\quad \dot{r} = -L\frac{du}{d\phi}$$
>
> 有效势方程中各项用 $u$ 表示：
> $$\frac{1}{2}L^2\Big(\frac{du}{d\phi}\Big)^2 - GM u + \frac{L^2}{2}u^2 - GM L^2 u^3 = \frac{E^2-1}{2}$$
>
> 对 $\phi$ 求导（$E$ 和 $L$ 为常数）：
> $$L^2\frac{du}{d\phi}\frac{d^2u}{d\phi^2} - GM\frac{du}{d\phi} + L^2 u\frac{du}{d\phi} - 3GM L^2 u^2\frac{du}{d\phi} = 0$$
>
> 除以 $L^2(du/d\phi)$（假设 $du/d\phi \neq 0$，即非圆轨道）：
> $$\boxed{\frac{d^2u}{d\phi^2} + u = \frac{GM}{L^2} + 3GM u^2}$$
>
> 右边第一项 $GM/L^2$ 是 Newton 引力的标准来源；第二项 $3GM u^2$ 是 GR 修正。无量纲微扰参数为 $GM u \sim GM/(\text{轨道半径}) \ll 1$。

> [!s]- **(b) 微扰求解**
>
> Newton 极限（略去 $3GM u^2$）：$u_0''+u_0 = GM/L^2$。通解为椭圆：
> $$u_0 = \frac{GM}{L^2}(1 + e\cos\phi)$$
>
> 将 $u = u_0 + u_1$ 代入完整方程，$u_1 \ll u_0$。$u_1$ 满足：$u_1'' + u_1 = 3GM u_0^2$。
>
> $$u_0^2 = \Big(\frac{GM}{L^2}\Big)^2(1 + 2e\cos\phi + e^2\cos^2\phi)$$
>
> 展开 $\cos^2\phi = (1+\cos 2\phi)/2$：
> $$u_1'' + u_1 = 3\frac{G^3M^3}{L^4}\Big[\underbrace{1+\frac{e^2}{2}}_{\text{常数项}} + \underbrace{2e\cos\phi}_{\text{共振项!}} + \underbrace{\frac{e^2}{2}\cos 2\phi}_{\text{非共振}}\Big]$$
>
> 常数项 $\to u_1^{(0)} = 3G^3M^3(1+e^2/2)/L^4$（极移，不引起进动）。
>
> $\cos 2\phi$ 项 $\to u_1^{(2)} = -(G^3M^3e^2/L^4)\cos 2\phi$（高频微扰，叠加进轨道椭率，不积累）。
>
> **共振项** $\cos\phi$：方程 $u_1''+u_1 \propto \cos\phi$ 产生特解 $u_1^{(1)} \propto \phi\sin\phi$（试探 $A\phi\sin\phi$ 代入得 $2A\cos\phi = 6G^3M^3e/L^4 \cdot \cos\phi$，所以 $A = 3G^3M^3e/L^4$）。这个 **$\phi$ 因子随角度线性增长**——长期进动。
>
> 组合 $u_0$ 和 $u_1^{(1)}$：
> $$u \approx \frac{GM}{L^2}\Big[1 + e\cos\phi + \frac{3G^2M^2}{L^2}e\,\phi\sin\phi\Big]$$
>
> 利用 $\cos(\phi - \delta) \approx \cos\phi + \delta\sin\phi$（小 $\delta$），对比得每弧度的进动偏移：
> $$\delta\phi = \frac{3G^2M^2}{L^2}\,\phi$$
>
> 一整圈（$\phi$ 从 $0$ 到 $2\pi$）：
> $$\Delta\phi_{\text{orbit}} = \frac{3G^2M^2}{L^2}\cdot 2\pi = \frac{6\pi G^2M^2}{L^2}$$
>
> 用椭圆关系 $L^2 = GM a(1-e^2)$ 消去 $L$：
> $$\boxed{\Delta\phi = \frac{6\pi GM}{a(1-e^2)}}$$

> [!s]- **(c) 水星数值**
>
> $$G = 6.674\times 10^{-11}\,\text{m}^3\text{kg}^{-1}\text{s}^{-2},\quad M_\odot = 1.989\times 10^{30}\,\text{kg}$$
>
> $$GM_\odot = 1.327\times 10^{20}\,\text{m}^3/\text{s}^2$$
>
> $$a = 5.79\times 10^{10}\,\text{m},\quad e = 0.2056,\quad 1-e^2 = 0.9577$$
>
> $$\Delta\phi_{\text{orbit}} = \frac{6\pi \cdot 1.327\times 10^{20}}{5.79\times 10^{10} \cdot 0.9577} = 4.52\times 10^{-7}\,\text{rad}$$
>
> 转换为角秒：$\Delta\phi_{\text{orbit}} = 4.52\times 10^{-7} \cdot \frac{180}{\pi}\cdot 3600 = 0.0933''$。
>
> 水星周期 87.97 天 = 0.241 年。每世纪：
> $$N = \frac{100}{0.241} = 415\,\text{圈/世纪}$$
>
> $$\Delta\phi_{\text{century}} = 415 \times 0.0933'' = \boxed{38.7''/\text{世纪}}$$
>
> 剩余 $\sim 4''$ 是其他行星的 Newton 摄动。GR 单独贡献 $43''$（精确计算用 $1-e^2$ 和更精确的 $a$ 值）。**1915 年 Einstein 算出的正是这个值**，与 Le Verrier 1859 年发现的反常进动吻合——这是 GR 的第一个实验验证，发生在日食光线偏折观测之前。

### 4.4 光的偏折与 Shapiro 延迟 $\star$

**(a)** 对零测地线（光子，$d\tau = 0$），导出 $u(\phi)$ 满足：
$$\frac{d^2u}{d\phi^2} + u = 3GM u^2$$
（注意与 (a) 的区别：右边没有 $GM/L^2$ 项——用 $u = 1/r$ 的定义直接算）

**(b)** 微扰求解，证明光线的总偏转角为 $\Delta\phi = 4GM/b$，其中 $b$ 为碰撞参数。

**(c)** 代入太阳数据（$R_\odot = 6.96\times 10^8$ m，$M_\odot$ 同上），计算掠过太阳表面光线的偏转角（单位：角秒）。与 1919 年 Eddington 的观测比较。


---

## 第五章 线性化引力与引力波

### 5.1 线性化 Einstein 方程

**(a)** 将度规展开为 Minkowski 背景 + 小扰动：
$$g_{\mu\nu} = \eta_{\mu\nu} + h_{\mu\nu},\quad |h_{\mu\nu}| \ll 1$$
证明到线性阶：
$$R_{\mu\nu} = \frac{1}{2}(\partial_\mu\partial_\nu h + \Box h_{\mu\nu} - \partial_\rho\partial_\mu h^\rho{}_\nu - \partial_\rho\partial_\nu h^\rho{}_\mu)$$
其中 $h = h^\mu{}_\mu$，$\Box = \partial_\mu\partial^\mu$（平直 d'Alembertian）。

**(b)** 引入迹反转扰动 $\bar{h}_{\mu\nu} = h_{\mu\nu} - \frac{1}{2}\eta_{\mu\nu}h$，并在 Lorenz 规范 $\partial^\mu\bar{h}_{\mu\nu} = 0$ 下，证明线性化 Einstein 方程简化为：
$$\Box \bar{h}_{\mu\nu} = -16\pi G\,T_{\mu\nu}$$

**(c)** 写出真空解（$T_{\mu\nu}=0$）的平面波形式，并解释为何引力波只有两个独立偏振态（$h_+$ 和 $h_\times$）。

> [!s]- **(a) 线性阶 Ricci 张量**
>
> $g_{\mu\nu} = \eta_{\mu\nu} + h_{\mu\nu}$，$|h_{\mu\nu}| \ll 1$。指标升降用 $\eta_{\mu\nu}$（$h$ 的乘积贡献二阶可略）。
>
> **Christoffel 到 $O(h)$**：
> $$\Gamma^\mu_{\alpha\beta} \approx \frac{1}{2}\eta^{\mu\nu}(\partial_\alpha h_{\nu\beta} + \partial_\beta h_{\nu\alpha} - \partial_\nu h_{\alpha\beta})$$
>
> **Riemann**：$R^\mu{}_{\nu\alpha\beta} = \partial_\alpha\Gamma^\mu_{\nu\beta} - \partial_\beta\Gamma^\mu_{\nu\alpha} + \cancel{O(h^2)}$
>
> 代入 $\Gamma$ 后偏导数交叉项 $\partial_\alpha\partial_\beta$ 对消，留存项：
> $$\boxed{R^\mu{}_{\nu\alpha\beta} \approx \frac{1}{2}\eta^{\mu\rho}(\partial_\alpha\partial_\nu h_{\rho\beta} - \partial_\alpha\partial_\rho h_{\nu\beta} - \partial_\beta\partial_\nu h_{\rho\alpha} + \partial_\beta\partial_\rho h_{\nu\alpha})}$$
>
> **收缩得 Ricci**（$R_{\nu\beta} = R^\mu{}_{\nu\mu\beta}$）：
> $$R_{\nu\beta} = \frac{1}{2}\big[\partial_\mu\partial_\nu h^\mu{}_\beta - \Box h_{\nu\beta} - \partial_\beta\partial_\nu h + \partial_\beta\partial_\rho h^\rho{}_\nu\big]$$
>
> 其中 $h \equiv h^\mu{}_\mu = \eta^{\mu\nu}h_{\mu\nu}$，$\Box \equiv \eta^{\mu\nu}\partial_\mu\partial_\nu$。重标 $(\nu,\beta) \to (\mu,\nu)$：
> $$\boxed{R_{\mu\nu} = \frac{1}{2}\big(\partial_\mu\partial_\nu h + \Box h_{\mu\nu} - \partial_\rho\partial_\mu h^\rho{}_\nu - \partial_\rho\partial_\nu h^\rho{}_\mu\big)}$$

> [!s]- **(b) 迹反转扰动与波动方程**
>
> 定义 $\bar{h}_{\mu\nu} \equiv h_{\mu\nu} - \frac{1}{2}\eta_{\mu\nu}h$。取迹：
> $$\bar{h} = \bar{h}^\mu{}_\mu = h - \frac{1}{2}\cdot 4\cdot h = -h$$
>
> 逆关系：$h_{\mu\nu} = \bar{h}_{\mu\nu} - \frac{1}{2}\eta_{\mu\nu}\bar{h}$，$h = -\bar{h}$。代入 (a) 的 $R_{\mu\nu}$：
> $$\begin{aligned} R_{\mu\nu} &= \frac{1}{2}\big[-\partial_\mu\partial_\nu\bar{h} + \Box(\bar{h}_{\mu\nu} - \frac{1}{2}\eta_{\mu\nu}\bar{h}) - \partial_\rho\partial_\mu(\bar{h}^\rho{}_\nu - \frac{1}{2}\delta^\rho_\nu\bar{h}) - \partial_\rho\partial_\nu(\bar{h}^\rho{}_\mu - \frac{1}{2}\delta^\rho_\mu\bar{h})\big] \\ &= \frac{1}{2}\big(\Box\bar{h}_{\mu\nu} - \frac{1}{2}\eta_{\mu\nu}\Box\bar{h} - \partial_\rho\partial_\mu\bar{h}^\rho{}_\nu - \partial_\rho\partial_\nu\bar{h}^\rho{}_\mu\big) \end{aligned}$$
>
> （含 $\partial_\mu\partial_\nu\bar{h}$ 的三项对消。）
>
> **Lorenz 规范** $\partial^\mu\bar{h}_{\mu\nu}=0$ 使混合导数项消失：
> $$R_{\mu\nu} = \frac{1}{2}\Box\bar{h}_{\mu\nu} - \frac{1}{4}\eta_{\mu\nu}\Box\bar{h}$$
>
> Ricci 标量：$R \approx \eta^{\mu\nu}R_{\mu\nu} = -\frac{1}{2}\Box\bar{h}$。
>
> Einstein 张量到线性阶：
> $$G_{\mu\nu} = R_{\mu\nu} - \frac{1}{2}\eta_{\mu\nu}R = \frac{1}{2}\Box\bar{h}_{\mu\nu} - \frac{1}{4}\eta_{\mu\nu}\Box\bar{h} + \frac{1}{4}\eta_{\mu\nu}\Box\bar{h} = \frac{1}{2}\Box\bar{h}_{\mu\nu}$$
>
> 代入 $G_{\mu\nu} = 8\pi G\,T_{\mu\nu}$：
> $$\boxed{\Box \bar{h}_{\mu\nu} = -16\pi G\,T_{\mu\nu}}$$

> [!s]- **(c) 平面波解与两个偏振态**
>
> 真空：$\Box\bar{h}_{\mu\nu} = 0$。平面波解：
> $$\bar{h}_{\mu\nu} = A_{\mu\nu} e^{ik_\alpha x^\alpha},\quad k^\mu k_\mu = 0$$
>
> $A_{\mu\nu}$ 为常对称张量（10 个实分量）。**规范约束逐步削减**：
>
> 1. **Lorenz 规范**（4 个条件）：$k^\mu A_{\mu\nu} = 0$ → 独立分量 10 − 4 = 6。
>
> 2. **剩余规范变换**：$x^\mu \to x^\mu + \xi^\mu$，$\Box\xi^\mu = 0$，$\xi^\mu = iC^\mu e^{ikx}$ 有 4 个自由参数。进一步减为 6 − 4 = **2**。
>
> 3. **TT 规范实现**：对沿 $+z$ 的波（$k^\mu = (\omega,0,0,\omega)$），可选取规范使 $h_{0\mu}=h_{3\mu}=0$ 且 $h=0$（此时 $\bar{h}_{\mu\nu}=h_{\mu\nu}$）。唯一非零空间分量为：
> $$\boxed{h_{xx}^{\text{TT}} = -h_{yy}^{\text{TT}} = h_+,\quad h_{xy}^{\text{TT}} = h_{yx}^{\text{TT}} = h_\times}$$
>
> 2 个独立偏振态对应对自旋-2 无质量引力子的 $\pm 2$ 螺旋度。

### 5.2 TT 规范

**(a)** 对沿 $z$ 轴传播的平面引力波，证明在横向无迹（TT）规范下，$h_{\mu\nu}^{\text{TT}}$ 的非零分量只有：
$$h_{xx}^{\text{TT}} = -h_{yy}^{\text{TT}} = h_+,\quad h_{xy}^{\text{TT}} = h_{yx}^{\text{TT}} = h_\times$$

**(b)** 计算 TT 规范下 Riemann 张量的非零分量，并证明测地线偏离方程中 $\ddot{\xi}^i = -R^i{}_{0j0}\xi^j$。

**(c)** 分析一个由静止粒子组成的圆环在经过 $h_+$ 和 $h_\times$ 偏振的引力波时的形变模式。

> [!s]- **(a) TT 规范形式**
>
> 沿 $+z$ 传播的平面波，TT 规范要求 $h_{0\mu}=h_{3\mu}=0$ 且 $h = h_{xx}+h_{yy}=0$。非零分量仅限于空间 2×2 无迹对称子空间：
> $$h_{\mu\nu}^{\text{TT}}(t,z) = \begin{pmatrix} 0 & 0 & 0 & 0 \\ 0 & h_+ & h_\times & 0 \\ 0 & h_\times & -h_+ & 0 \\ 0 & 0 & 0 & 0 \end{pmatrix} e^{i\omega(t-z)}$$
>
> （取实部作物理场。）无迹性 $\operatorname{tr}(h) = h_+ - h_+ = 0$。✓
>
> **论证 $h_{3\mu}=0$**：Lorenz 条件 $k^\mu h_{\mu\nu}=0$ 对 $k^\mu = (\omega,0,0,\omega)$ 给出 $h_{0\nu}+h_{3\nu}=0$；$h_{0\nu}=0$（TT 的"时间分量零"条件）$\Rightarrow h_{3\nu}=0$。

> [!s]- **(b) Riemann 张量与测地线偏离**
>
> 弱场 Riemann 到 $O(h)$：
> $$R_{\mu\nu\alpha\beta} \approx \frac{1}{2}(\partial_\nu\partial_\alpha h_{\mu\beta} + \partial_\mu\partial_\beta h_{\nu\alpha} - \partial_\mu\partial_\alpha h_{\nu\beta} - \partial_\nu\partial_\beta h_{\mu\alpha})$$
>
> 平面波 $h_{\mu\nu} = h_{\mu\nu}(t-z)$，用 $\partial_z h = -\partial_t h$（行波 $f(t-z)$ 的特性）：
> $$R_{x0x0} = -\frac{1}{2}\ddot{h}_{xx}^{\text{TT}},\quad R_{y0y0} = -\frac{1}{2}\ddot{h}_{yy}^{\text{TT}} = +\frac{1}{2}\ddot{h}_{xx}^{\text{TT}}$$
> $$R_{x0y0} = R_{y0x0} = -\frac{1}{2}\ddot{h}_{xy}^{\text{TT}}$$
>
> 对自由下落观测者（$u^\mu = (1,0,0,0)$，$\Gamma|_{测地线}=0$），在局域 Lorentz 系中 $D/d\tau \to d/d\tau$：
> $$\frac{d^2\xi^\mu}{d\tau^2} = -R^\mu{}_{\nu\alpha\beta}u^\nu u^\alpha \xi^\beta$$
>
> 空间分量 $(i=1,2,3)$：
> $$\boxed{\ddot{\xi}^i = -R^i{}_{0j0}\,\xi^j}$$
>
> 这是 LIGO 探测器响应的理论基础——引力波在两个自由下落检验质量之间产生潮汐加速度差，两臂的正交布置用于同时测量 $h_+$ 与 $h_\times$。

> [!s]- **(c) 粒子环的形变模式**
>
> 由 $\ddot{\xi}^i = -R^i{}_{0j0}\xi^j$ 分情形分析。
>
> **$h_+$ 偏振**（$h_{xx}^{\text{TT}} = -h_{yy}^{\text{TT}} = h_+\cos\omega t$，$h_{xy}=0$）：
> $$\ddot{\xi}^x = +\frac{\omega^2}{2}h_+\cos\omega t \cdot \xi^x,\quad \ddot{\xi}^y = -\frac{\omega^2}{2}h_+\cos\omega t \cdot \xi^y$$
> - 每个半周期，$x$ 方向拉伸时 $y$ 方向压缩（反之亦然）
> - 初始圆形粒子环 → 交替横椭圆、竖椭圆
> - 形变轴与坐标 $x,y$ 轴重合：「＋」形
>
> **$h_\times$ 偏振**（$h_{xy}^{\text{TT}} = h_\times\cos\omega t$，$h_{xx}=h_{yy}=0$）：
> $$\ddot{\xi}^x = +\frac{\omega^2}{2}h_\times\cos\omega t \cdot \xi^y,\quad \ddot{\xi}^y = +\frac{\omega^2}{2}h_\times\cos\omega t \cdot \xi^x$$
> - 转到 $45^\circ$ 方向 $(x\pm y)/\sqrt{2}$ 后，方程化为与 $h_+$ 相同的形式
> - 形变轴相对坐标轴旋转 $45^\circ$：「×」形
>
> **示意图**（$T = 2\pi/\omega$）：
> $$\begin{aligned} h_+ &: \bigcirc \xrightarrow{T/4} \text{横椭圆} \xrightarrow{T/4} \bigcirc \xrightarrow{T/4} \text{竖椭圆} \xrightarrow{T/4} \bigcirc \\ h_\times &: \bigcirc \xrightarrow{T/4} \text{斜椭圆}(\nearrow) \xrightarrow{T/4} \bigcirc \xrightarrow{T/4} \text{斜椭圆}(\searrow) \xrightarrow{T/4} \bigcirc \end{aligned}$$

### 5.3 引力波能量与四极辐射

**(a)** 从线性化理论的二阶有效能动张量出发（Isaacson 张量）：
$$t_{\mu\nu} = \frac{1}{32\pi G}\langle \partial_\mu \bar{h}_{\alpha\beta}\,\partial_\nu \bar{h}^{\alpha\beta} \rangle$$
计算沿 $z$ 轴传播的单色波的能流通量 $\mathcal{F} = t_{0z}$。

**(b)** 证明引力辐射总功率的四极公式：
$$P = \frac{G}{5}\langle \dddot{Q}_{ij}\dddot{Q}^{ij} \rangle,\quad Q_{ij} = \int d^3x\,\rho\left(x_i x_j - \frac{1}{3}\delta_{ij}r^2\right)$$

**(c)** 估算地球绕太阳公转的引力辐射功率，并讨论何时辐射反作用显著。

> [!s]- **(a) 单色波能流通量**
>
> Isaacson 张量（在几个波长上平均 $\langle\cdot\rangle$）：
> $$t_{\mu\nu} = \frac{1}{32\pi G}\langle \partial_\mu \bar{h}_{\alpha\beta}\,\partial_\nu \bar{h}^{\alpha\beta} \rangle$$
>
> TT 规范下 $\bar{h}_{\mu\nu}=h_{\mu\nu}^{\text{TT}}$，单色波沿 $+z$：
> $$h_{xx} = -h_{yy} = A_+\cos\omega(t-z),\quad h_{xy} = h_{yx} = A_\times\cos\omega(t-z)$$
>
> **能流 $\mathcal{F} = t_{0z}$** —— 先算导数：
> $$\partial_0 h_{ij} = -\omega A_{ij}\sin\omega(t-z),\quad \partial_z h_{ij} = +\omega A_{ij}\sin\omega(t-z)$$
>
> 收缩 $h_{ij}h^{ij} = h_{xx}^2 + h_{yy}^2 + 2h_{xy}^2 = A_+^2 + A_+^2 + 2A_\times^2 = 2(A_+^2+A_\times^2)$
>
> $$\begin{aligned} t_{0z} &= \frac{1}{32\pi G}\langle \partial_0 h_{ij}\,\partial_z h^{ij} \rangle \\ &= \frac{1}{32\pi G} \cdot (-\omega^2) \cdot 2(A_+^2+A_\times^2) \cdot \langle\sin^2\omega(t-z)\rangle \end{aligned}$$
>
> $\langle\sin^2\rangle = 1/2$，$\partial_0\partial_z$ 乘积为 $-\omega^2$（对 $f(t-z)$，$\partial_z = -\partial_0$）。沿 $+z$ 方向能流为正：
> $$\boxed{\mathcal{F} = t_{0z} = \frac{\omega^2}{32\pi G}(A_+^2 + A_\times^2)}$$
>
> **量级感知**：GW150914 峰值 $h \sim 10^{-21}$，$f \sim 150$ Hz。$\mathcal{F} \sim 10^{20}$ W/m² —— 振幅虽极小，但 $f^2$ 因子使其瞬时能流通量与太阳表面光度密度可比。

> [!s]- **(b) 四极辐射功率公式**
>
> **推迟解**（类比电动力学）：$\Box\bar{h}_{ij} = -16\pi G\,T_{ij}$
>
> 远场近似 $r \gg$ 源尺寸：
> $$\bar{h}_{ij}(t,\vec{x}) \approx \frac{4G}{r}\int d^3x'\,T_{ij}(t-r, \vec{x}')$$
>
> **关键恒等式**：由 $\partial_\mu T^{\mu\nu}=0$ 两次分部积分，
> $$\int d^3x\,T^{ij} = \frac{1}{2}\frac{d^2}{dt^2}\int d^3x\,\rho\,x^i x^j \equiv \frac{1}{2}\ddot{I}_{ij}$$
>
> 其中 $I_{ij} \equiv \int \rho\,x^i x^j\,d^3x$ 为质量四极矩。
>
> 定义**无迹四极矩**（迹部分不产生引力辐射——只有无迹部分耦合到 $h_{\mu\nu}^{\text{TT}}$）：
> $$Q_{ij} \equiv I_{ij} - \frac{1}{3}\delta_{ij}I^k{}_k = \int d^3x\,\rho\Big(x_i x_j - \frac{1}{3}\delta_{ij}r^2\Big)$$
>
> 因此渐近形式：$\bar{h}_{ij} \approx \frac{2G}{r}\ddot{Q}_{ij}(t-r)$（TT 投影后）。
>
> **辐射功率**：对 Isaacson 张量的径向分量在远场球面上积分 $P = \lim_{r\to\infty}\int t_{0r}\,r^2 d\Omega$。TT 投影的方向平均给出因子 $1/5$：
> $$\boxed{P = \frac{G}{5c^5}\langle \dddot{Q}_{ij}\,\dddot{Q}^{ij} \rangle}$$
>
> $c^5$ 因子的来源：$\bar{h} \propto G/c^4$，$t_{\mu\nu} \propto c^4/G$，$d/dt$ 在 Newton 源中引入 $v/c \sim \Omega a/c$。四极辐射是慢速展开的领头阶 $(v/c)^5$（质量四极为主导，偶极因动量守恒禁戒）。

> [!s]- **(c) 地日系统的引力辐射**
>
> 近似：$M_\odot \gg M_\oplus$，太阳静止。地球在 $x\text{-}y$ 面圆周运动：
> $$x = a\cos\Omega t,\quad y = a\sin\Omega t,\quad \Omega = \frac{2\pi}{T}$$
>
> **质量四极矩**（只保留含时部分）：
> $$\begin{aligned} I_{xx} &= M_\oplus a^2\cos^2\Omega t = \frac{M_\oplus a^2}{2}(1 + \cos 2\Omega t) \\ I_{yy} &= M_\oplus a^2\sin^2\Omega t = \frac{M_\oplus a^2}{2}(1 - \cos 2\Omega t) \\ I_{xy} &= I_{yx} = \frac{M_\oplus a^2}{2}\sin 2\Omega t \end{aligned}$$
>
> 无迹化（常数项消去）：
> $$Q_{xx} = -Q_{yy} = \frac{M_\oplus a^2}{2}\cos 2\Omega t,\quad Q_{xy} = Q_{yx} = \frac{M_\oplus a^2}{2}\sin 2\Omega t$$
>
> 三阶时间导数：$\dddot{Q}_{ij} \propto (2\Omega)^3 M_\oplus a^2 = 8\Omega^3 M_\oplus a^2$。
>
> 精确代入四极公式（含角度积分）：
> $$P = \frac{32G}{5c^5}\,\Omega^6 M_\oplus^2 a^4$$
>
> **数值代入**：
> $$\begin{aligned} M_\oplus &= 5.97\times 10^{24}\;\text{kg} \\ a &= 1.50\times 10^{11}\;\text{m} \\ \Omega &= \frac{2\pi}{365.25\times 86400} \approx 1.99\times 10^{-7}\;\text{s}^{-1} \\ G &= 6.67\times 10^{-11},\quad c = 3.00\times 10^8 \end{aligned}$$
>
> $$\boxed{P \approx 200\;\text{W}}$$
>
> **仅约 200 瓦**。对比太阳电磁光度 $\sim 3.8\times 10^{26}$ W，引力辐射弱 $10^{24}$ 量级。
>
> **辐射反作用的时间尺度**：
> $$t_{\text{GW}} \equiv \frac{|E_{\text{orbit}}|}{P} = \frac{GM_\odot M_\oplus/(2a)}{200\;\text{W}} \approx 10^{23}\;\text{年} \;\gg\; \text{宇宙年龄}\;(1.38\times 10^{10}\;\text{年})$$
>
> 地球在宇宙寿命内靠引力辐射损失的轨道能量完全可忽略。**唯一可探测引力辐射反作用的系统是致密双星**：Hulse-Taylor 双脉冲星 PSR B1913+16（$P \approx 7.35\times 10^{24}$ W），其轨道衰减与 GR 四极辐射预言完美吻合，获 1993 年 Nobel 物理学奖。
---

---
## 第六章 Killing 矢量与对称性

### 6.1 Killing 方程

**(a)** 证明度规沿 Killing 矢量 $\xi^\mu$ 不变的充要条件是 Killing 方程：
$$\nabla_\mu\xi_\nu + \nabla_\nu\xi_\mu = 0$$
在坐标基下等价于 $\mathcal{L}_\xi g_{\mu\nu} = 0$（Lie 导数）。

**(b)** 对 $n$ 维平直时空（Minkowski 或 Euclid），证明独立 Killing 矢量数为 $n(n+1)/2$。对 $n=4$，列出所有 Killing 矢量（4 个平移 + 6 个 Lorentz）。

> [!s]- **(a) Killing 方程 $\Longleftrightarrow$ $\mathcal{L}_\xi g_{\mu\nu}=0$**
> 
> **Step 1：Lie 导数的坐标基定义**
> 
> 度规沿矢量场 $\xi$ 的 Lie 导数在坐标基下为：
> $$\mathcal{L}_\xi g_{\mu\nu} = \xi^\rho\partial_\rho g_{\mu\nu} + g_{\rho\nu}\partial_\mu\xi^\rho + g_{\mu\rho}\partial_\nu\xi^\rho$$
> 
> **Step 2：将偏导数替换为协变导数**
> 
> 利用 $\partial_\mu\xi^\rho = \nabla_\mu\xi^\rho - \Gamma^\rho_{\mu\sigma}\xi^\sigma$：
> 
> $$\begin{aligned}
> \mathcal{L}_\xi g_{\mu\nu} &= \xi^\rho\partial_\rho g_{\mu\nu} + g_{\rho\nu}(\nabla_\mu\xi^\rho - \Gamma^\rho_{\mu\sigma}\xi^\sigma) + g_{\mu\rho}(\nabla_\nu\xi^\rho - \Gamma^\rho_{\nu\sigma}\xi^\sigma) \\[4pt]
> &= \underbrace{\xi^\rho\partial_\rho g_{\mu\nu} - g_{\rho\nu}\Gamma^\rho_{\mu\sigma}\xi^\sigma - g_{\mu\rho}\Gamma^\rho_{\nu\sigma}\xi^\sigma}_{\text{三项组合成度规的协变导数}} \;+\; g_{\rho\nu}\nabla_\mu\xi^\rho + g_{\mu\rho}\nabla_\nu\xi^\rho
> \end{aligned}$$
> 
> **Step 3：识别度规协变导数的展开**
> 
> 度规相容性 $\nabla_\rho g_{\mu\nu} = 0$ 展开为：
> $$\partial_\rho g_{\mu\nu} = \Gamma^\sigma_{\rho\mu}g_{\sigma\nu} + \Gamma^\sigma_{\rho\nu}g_{\mu\sigma}$$
> 
> 因此：
> $$\xi^\rho\partial_\rho g_{\mu\nu} = \xi^\rho(\Gamma^\sigma_{\rho\mu}g_{\sigma\nu} + \Gamma^\sigma_{\rho\nu}g_{\mu\sigma})$$
> 
> 而 $-g_{\rho\nu}\Gamma^\rho_{\mu\sigma}\xi^\sigma = -g_{\rho\nu}\Gamma^\rho_{\sigma\mu}\xi^\sigma$（重命名哑指标 $\mu\leftrightarrow\sigma$），同理第二项。三个含 $\Gamma$ 的项成对抵消。
> 
> **结果**：
> $$\boxed{\mathcal{L}_\xi g_{\mu\nu} = g_{\rho\nu}\nabla_\mu\xi^\rho + g_{\mu\rho}\nabla_\nu\xi^\rho}$$
> 
> **Step 4：降指标**
> 
> 用 $\nabla_\mu\xi_\nu = \nabla_\mu(g_{\nu\rho}\xi^\rho) = g_{\nu\rho}\nabla_\mu\xi^\rho$（度规相容性允许 $g$ 自由进出 $\nabla$）：
> 
> $$\boxed{\mathcal{L}_\xi g_{\mu\nu} = \nabla_\mu\xi_\nu + \nabla_\nu\xi_\mu}$$
> 
> **Step 5：等价性**
> 
> $\mathcal{L}_\xi g_{\mu\nu} = 0$ 表示度规沿 $\xi$ 不变。由上式：
> 
> $$\boxed{\mathcal{L}_\xi g_{\mu\nu} = 0 \;\Longleftrightarrow\; \nabla_\mu\xi_\nu + \nabla_\nu\xi_\mu = 0}$$
> 
> **几何含义**：Killing 方程是等度规流生成的协变条件。满足此方程的 $\xi^\mu$ 生成时空的连续对称性——这是 Noether 定理在 GR 中的体现：每个 Killing 矢量对应一个沿测地线的守恒量。

> [!s]- **(b) 平直时空的 Killing 矢量：计数 $N = n(n+1)/2$**
> 
> **Step 1：平直时空中的 Killing 方程**
> 
> 平直度规 $\eta_{\mu\nu}$ 的 Christoffel 符号处处为零 → $\nabla_\mu\xi_\nu = \partial_\mu\xi_\nu$。Killing 方程简化为：
> 
> $$\partial_\mu\xi_\nu + \partial_\nu\xi_\mu = 0 \tag{1}$$
> 
> **Step 2：二阶导数约束**
> 
> 对 (1) 求 $\partial_\rho$：$\partial_\rho\partial_\mu\xi_\nu + \partial_\rho\partial_\nu\xi_\mu = 0$。
> 
> 轮换指标并对 $(\rho,\mu,\nu)$ 做组合 $(\rho\mu\nu) + (\mu\nu\rho) - (\nu\rho\mu)$（偏导数可交换）：
> 
> $$\begin{aligned}
> &\partial_\rho\partial_\mu\xi_\nu + \cancel{\partial_\rho\partial_\nu\xi_\mu} \\
> + &\cancel{\partial_\mu\partial_\nu\xi_\rho} + \partial_\mu\partial_\rho\xi_\nu \\
> - &\partial_\nu\partial_\rho\xi_\mu - \partial_\nu\partial_\mu\xi_\rho
> \end{aligned}$$
> 
> 前两项合并为 $2\partial_\rho\partial_\mu\xi_\nu$，其余项利用 (1) 两两配对消去：
> 
> $$\boxed{\partial_\rho\partial_\mu\xi_\nu = 0}$$
> 
> 所有二阶导数为零 → **$\xi_\mu$ 是坐标的线性函数**。
> 
> **Step 3：通解形式**
> 
> $$\xi_\mu(x) = A_\mu + B_{\mu\nu}x^\nu$$
> 
> 代入 Killing 方程 (1)：
> $$\partial_\mu\xi_\nu + \partial_\nu\xi_\mu = B_{\nu\mu} + B_{\mu\nu} = 0 \;\Rightarrow\; \boxed{B_{\mu\nu} = -B_{\nu\mu}}$$
> 
> $B_{\mu\nu}$ 是反对称矩阵。
> 
> **Step 4：独立参数计数**
> 
> - $A_\mu$（平移）：$n$ 个独立分量
> - $B_{\mu\nu}$（反对称）：$\binom{n}{2} = n(n-1)/2$ 个独立分量
> 
> $$\boxed{N = n + \frac{n(n-1)}{2} = \frac{n(n+1)}{2}}$$
> 
> 这恰好是 **Poincaré 群** 的维数 = 平移维数 $n$ + 旋转/boost 维数 $\binom{n}{2}$。
> 
> **Step 5：$n=4$ Minkowski 时空的具体列表（10 个独立 Killing 矢量）**
> 
> | 类型 | Killing 矢量 $\xi^\mu$ | 个数 | 物理含义 |
> |:-----|:-----------------------|:----:|:---------|
> | $P_0$ | $(1, 0, 0, 0)$ | | 时间平移 |
> | $P_1$ | $(0, 1, 0, 0)$ | 4 | $x$ 方向空间平移 |
> | $P_2$ | $(0, 0, 1, 0)$ | | $y$ 方向空间平移 |
> | $P_3$ | $(0, 0, 0, 1)$ | | $z$ 方向空间平移 |
> | $M_{01}$ | $(x, t, 0, 0)$ | | $x$ 方向 boost |
> | $M_{02}$ | $(y, 0, t, 0)$ | | $y$ 方向 boost |
> | $M_{03}$ | $(z, 0, 0, t)$ | 6 | $z$ 方向 boost |
> | $M_{12}$ | $(0, -y, x, 0)$ | | 绕 $z$ 轴旋转 |
> | $M_{23}$ | $(0, 0, -z, y)$ | | 绕 $x$ 轴旋转 |
> | $M_{31}$ | $(0, z, 0, -x)$ | | 绕 $y$ 轴旋转 |
> 
> **验证示例**：以 $M_{01}$（$x$ 方向 boost）为例，$\xi^\mu = (x, t, 0, 0)$，降指标 $\xi_\mu = \eta_{\mu\nu}\xi^\nu = (-x, t, 0, 0)$：
> 
> $$\partial_0\xi_1 + \partial_1\xi_0 = \partial_t(t) + \partial_x(-x) = 1 - 1 = 0 \;\checkmark$$
> 
> **一般形式**：Lorentz Killing 矢量可统一写为 $\xi^\mu = \omega^\mu{}_\nu x^\nu$，$\omega_{\mu\nu} = -\omega_{\nu\mu}$ 是常反对称参数——这正是无穷小 Lorentz 变换 $\Lambda^\mu{}_\nu \approx \delta^\mu_\nu + \omega^\mu{}_\nu$ 的 Killing 矢量形式。
> 
> **GR 视角**：平直时空的 $n(n+1)/2$ 是**最大对称空间**的 Killing 矢量数。任何弯曲时空的 Killing 矢量数 ≤ 此值——缺失的 Killing 矢量标志着被引力破坏的对称性。

### 6.2 测地线上的守恒量

**(a)** 证明若 $\xi^\mu$ 是 Killing 矢量，则沿测地线（$u^\mu = dx^\mu/d\tau$）量 $u^\mu\xi_\mu$ 守恒：
$$\frac{d}{d\tau}(u^\mu\xi_\mu) = 0$$

**(b)** 对 Schwarzschild 度规，写出 $\partial_t$ 和 $\partial_\phi$ 对应的守恒量，并证明它们对应能量 $E = -(1-2GM/r)\dot{t}$ 和角动量 $L = r^2\sin^2\theta\,\dot{\phi}$。

> [!s]- **(a) $u^\mu\xi_\mu$ 沿测地线守恒**
> 
> **要证**：$\displaystyle \frac{d}{d\tau}(u^\mu\xi_\mu) = 0$，其中 $u^\mu = dx^\mu/d\tau$ 满足测地线方程。
> 
> **Step 1：沿测地线的协变导数 = 普通导数**
> 
> 对标量函数 $f = u^\mu\xi_\mu$，协变导数和普通导数的方向导数相同：
> $$\frac{d}{d\tau}(u^\mu\xi_\mu) = u^\nu\nabla_\nu(u^\mu\xi_\mu)$$
> 
> **Step 2：乘积法则**
> 
> $$u^\nu\nabla_\nu(u^\mu\xi_\mu) = u^\nu(\nabla_\nu u^\mu)\,\xi_\mu + u^\nu u^\mu(\nabla_\nu\xi_\mu)$$
> 
> **Step 3：第一项为零——测地线条件**
> 
> $u^\mu$ 满足测地线方程 $u^\nu\nabla_\nu u^\mu = 0$（即 $\ddot{x}^\mu + \Gamma^\mu_{\alpha\beta}\dot{x}^\alpha\dot{x}^\beta = 0$）：
> $$u^\nu(\nabla_\nu u^\mu)\,\xi_\mu = 0 \cdot \xi_\mu = 0$$
> 
> **Step 4：第二项为零——Killing 方程**
> 
> $u^\nu u^\mu\nabla_\nu\xi_\mu$ 是对称张量 $\nabla_\nu\xi_\mu$ 与对称张量 $u^\nu u^\mu$ 的缩并。将 $\nabla_\nu\xi_\mu$ 分解为对称+反对称部分：
> $$\nabla_\nu\xi_\mu = \underbrace{\frac{1}{2}(\nabla_\nu\xi_\mu + \nabla_\mu\xi_\nu)}_{\text{对称部分}} + \underbrace{\frac{1}{2}(\nabla_\nu\xi_\mu - \nabla_\mu\xi_\nu)}_{\text{反对称部分}}$$
> 
> 反对称张量与对称张量 $u^\nu u^\mu$ 的缩并恒为零。而对称部分恰好是 $\frac{1}{2}$ Killing 方程——根据假设 $\xi^\mu$ 为 Killing 矢量，**此项为零**：
> 
> $$u^\nu u^\mu \cdot \frac{1}{2}(\nabla_\nu\xi_\mu + \nabla_\mu\xi_\nu) = 0$$
> 
> **结论**：
> 
> $$\boxed{\frac{d}{d\tau}(u^\mu\xi_\mu) = 0}$$
> 
> **物理本质**：每个 Killing 矢量 = 一个 Noether 守恒荷。沿测地线，度规的每一个连续对称性都产生一个运动常数——这是 GR 中守恒定律的几何版本。Noether 定理的「空间平移 → 动量守恒」在弯曲时空中精确化为「Killing 矢量 → $u^\mu\xi_\mu$ 守恒」。

> [!s]- **(b) Schwarzschild 度规中 $\partial_t$ 与 $\partial_\phi$ 的守恒量**
> 
> **Schwarzschild 度规**：
> $$ds^2 = -\Big(1-\frac{2GM}{r}\Big)dt^2 + \Big(1-\frac{2GM}{r}\Big)^{-1}dr^2 + r^2(d\theta^2 + \sin^2\theta\,d\phi^2)$$
> 
> **判据**：度规分量不显含 $t$ 和 $\phi$ → $\partial_t$ 和 $\partial_\phi$ 是 Killing 矢量。
> 
> **Step 1：$\xi = \partial_t$ → 能量 $E$**
> 
> 在坐标基下 $\xi^\mu = \delta^\mu_t = (1, 0, 0, 0)$。降指标：
> $$\xi_\mu = g_{\mu\nu}\xi^\nu = g_{\mu t} = (g_{tt}, 0, 0, 0) = \Big(-\big(1-\frac{2GM}{r}\big),\, 0,\, 0,\, 0\Big)$$
> 
> 守恒量（按惯例定义为 $-u^\mu\xi_\mu$ 以使无穷远观测者测得正能量）：
> $$E \equiv -u^\mu\xi_\mu = -g_{\mu\nu}u^\mu\xi^\nu = -g_{tt}u^t \cdot 1 = -\Big[-\Big(1-\frac{2GM}{r}\Big)\Big] \dot{t}$$
> 
> $$\boxed{E = \Big(1-\frac{2GM}{r}\Big)\dot{t}}$$
> 
> 其中 $\dot{t} \equiv dt/d\tau$。$r \to \infty$ 时 $E \to \dot{t} = dt/d\tau = \gamma = \text{狭义相对论能量（单位质量）}$。
> 
> **Step 2：$\xi = \partial_\phi$ → 角动量 $L$**
> 
> $\xi^\mu = \delta^\mu_\phi = (0, 0, 0, 1)$。降指标：
> $$\xi_\mu = g_{\mu\phi} = (0, 0, 0, g_{\phi\phi}) = (0, 0, 0, r^2\sin^2\theta)$$
> 
> 守恒量：
> $$L \equiv u^\mu\xi_\mu = g_{\phi\phi}u^\phi \cdot 1 = r^2\sin^2\theta \cdot \dot{\phi}$$
> 
> $$\boxed{L = r^2\sin^2\theta\,\dot{\phi}}$$
> 
> **Summary**：
> 
> | Killing 矢量 | 分量 $\xi^\mu$ | 守恒量 | 表达式 | 无穷远物理含义 |
> |:------------|:--------------|:-------|:-------|:---------------|
> | $\partial_t$ | $(1,0,0,0)$ | 能量 $E$ | $E = (1-2GM/r)\dot{t}$ | 单位质量的轨道能量 |
> | $\partial_\phi$ | $(0,0,0,1)$ | 角动量 $L$ | $L = r^2\sin^2\theta\,\dot{\phi}$ | 单位质量的轨道角动量 |
> 
> **与 4.2(a) 的统一**：这两个守恒量正是第四章 Schwarzschild 测地线分析中 Lagrangian 方法的出发点。因为 $\partial L/\partial t = 0$ 和 $\partial L/\partial \phi = 0$ 的底层几何原因，就是 $\partial_t$ 和 $\partial_\phi$ 是 Killing 矢量。Killing 矢量的视角揭示了 Lagrangian 守恒量的**几何不变量本质**——它们不依赖于坐标选取技巧，而是时空对称性的直接后果。

### 6.3 静态与稳态时空

**(a)** 解释静态时空和稳态时空的区别。哪一类有时空交叉项 $g_{0i}$？

**(b)** 证明 Schwarzschild 是静态的（$\xi = \partial_t$ 与等时面正交），而 Kerr 只是稳态的（$\xi = \partial_t$ 不与等时面正交，存在拖曳效应）。

**(c)** 对 $1+1$ 维 Rindler 度规 $ds^2 = e^{2\rho}(d\eta^2 - d\rho^2)$：
- 写出 $\partial_\eta$ 和 $\partial_\rho$ 中哪些是 Killing 矢量。
- 计算 $\partial_\eta$ 的 Killing 方程并验证。
- 证明在 Minkowski 坐标下 $\partial_\eta = x\partial_t + t\partial_x$（你已在 [[弯曲时空下的QFT]] 中见过这个 boost Killing 矢量）。

> [!s]- **(a) 静态 vs 稳态时空**
> 
> **定义（Killing 矢量视角）**：
> 
> | 类型 | 定义 | 数学条件 |
> |:-----|:-----|:---------|
> | **稳态时空** | 存在类时 Killing 矢量场 $\xi^\mu$（即度规不随时间演化） | $\exists\,\xi^\mu$ 类时，满足 $\nabla_\mu\xi_\nu + \nabla_\nu\xi_\mu = 0$ |
> | **静态时空** | 稳态 + $\xi^\mu$ 与等时面族正交（超曲面正交） | 稳态条件 + $\xi_{[\mu}\nabla_\nu\xi_{\rho]} = 0$（Frobenius 条件） |
> 
> **在适配坐标系中的表现**：
> 
> 若 $\xi = \partial_t$ 为类时 Killing 矢量：
> 
> - **稳态**：$\partial_t g_{\mu\nu} = 0$，线元一般形式为：
>   $$ds^2 = g_{00}(\vec{x})dt^2 + 2g_{0i}(\vec{x})dt\,dx^i + g_{ij}(\vec{x})dx^i dx^j$$
>   所有分量可含 $x^i$，但不含 $t$。
> 
> - **静态**：进一步要求不存在 $dt\,dx^i$ 交叉项——这等价于 $\xi = \partial_t$ 与 $t=\text{const}$ 等时面正交。线元形式为：
>   $$ds^2 = g_{00}(\vec{x})dt^2 + g_{ij}(\vec{x})dx^i dx^j$$
> 
> **核心判据**：
> 
> $$\boxed{\text{存在交叉项 } g_{0i} \neq 0 \;\Longleftrightarrow\; \text{稳态但非静态}}$$
> 
> 物理直观：$g_{0i} \neq 0$ 意味着时空在"旋转"——时间平移 Killing 矢量的积分曲线与等时面不垂直，观测者即使"静止"（空间坐标不变）也会被拖曳旋转。
> 
> **例子速览**：
> 
> | 时空 | 类时 Killing | $g_{0i}$ | 分类 |
> |:-----|:------------|:--------:|:-----|
> | Minkowski | $\partial_t$ | 无 | 静态 |
> | Schwarzschild | $\partial_t$ | 无 | 静态 |
> | Kerr | $\partial_t$ | $g_{t\phi} \neq 0$ | 稳态（非静态） |
> | FLRW | 无（度规随时间演化） | — | 非稳态 |
> | Rindler | $\partial_\eta$ | 无 | 静态 |

> [!s]- **(b) Schwarzschild 是静态的，Kerr 只是稳态的**
> 
> **Schwarzschild 度规**：
> $$ds^2 = -\Big(1-\frac{2GM}{r}\Big)dt^2 + \Big(1-\frac{2GM}{r}\Big)^{-1}dr^2 + r^2(d\theta^2 + \sin^2\theta\,d\phi^2)$$
> 
> - $\partial_t$ 是类时 Killing 矢量（$r > 2GM$ 时），$\partial_t g_{\mu\nu} = 0$ ✓
> - **无交叉项** $g_{ti} = g_{tr} = g_{t\theta} = g_{t\phi} = 0$
> - 在 $t = \text{const}$ 等时面上，$dt = 0$，线元退化为纯空间度规 → $\partial_t$ 与等时面正交
> 
> $$\boxed{\text{Schwarzschild} = \text{静态}}$$
> 
> **Kerr 度规**（Boyer-Lindquist 坐标）：
> $$ds^2 = -\Big(1-\frac{2GMr}{\Sigma}\Big)dt^2 - \frac{4GMar\sin^2\theta}{\Sigma}dt\,d\phi + \frac{\Sigma}{\Delta}dr^2 + \Sigma\,d\theta^2 + \Big(r^2+a^2+\frac{2GMa^2 r\sin^2\theta}{\Sigma}\Big)\sin^2\theta\,d\phi^2$$
> 
> - $\partial_t$ 是类时 Killing 矢量（在能层外）
> - **存在交叉项** $g_{t\phi} = -\dfrac{2GMar\sin^2\theta}{\Sigma} \neq 0$（$a \neq 0$ 时）
> - $\partial_t$ 与 $t = \text{const}$ 等时面**不正交** → Frobenius 条件 $\xi_{[\mu}\nabla_\nu\xi_{\rho]} \neq 0$
> 
> $$\boxed{\text{Kerr} = \text{稳态但非静态}}$$
> 
> **物理根源——拖曳效应**：
> 
> Kerr 的 $g_{t\phi} \neq 0$ 意味着：一个空间坐标固定（$dr=d\theta=d\phi=0$）的观测者，其四速度 $u^\mu = (u^t, 0, 0, 0)$ 的角动量不为零：
> $$L = u_\phi = g_{\phi t}u^t = g_{t\phi}u^t \neq 0$$
> 
> 静止观测者被旋转黑洞"拖曳"着绕对称轴转动——这就是 **Lense-Thirring 效应**（参考系拖曳）。在能层（ergosphere）内，拖曳效应强到使任何观测者都无法保持 $\phi = \text{const}$。
> 
> **超曲面正交性的 Frobenius 条件**（补充）：
> $$\xi_{[\mu}\nabla_\nu\xi_{\rho]} = 0 \;\Longleftrightarrow\; \text{Killing 矢量 } \xi \text{ 与某族超曲面正交}$$
> 
> 对 Schwarzschild（$\xi = \partial_t$）：$\xi_\mu = (g_{tt}, 0, 0, 0)$，梯度的反对称部分恒为零。✓
> 
> 对 Kerr（$\xi = \partial_t$）：$\xi_\mu = (g_{tt}, 0, 0, g_{t\phi})$，$\xi_{[t}\nabla_r\xi_{\phi]} \propto \partial_r(g_{t\phi}) \neq 0$ → 不与等时面正交。

> [!s]- **(c) Rindler 度规的 Killing 矢量分析**
> 
> **度规**：$ds^2 = e^{2\rho}(d\eta^2 - d\rho^2)$。
> 
> **判断哪些是 Killing 矢量**：
> 
> 度规分量 $g_{\eta\eta} = e^{2\rho}$，$g_{\rho\rho} = -e^{2\rho}$，$g_{\eta\rho} = 0$。
> 
> - **$\partial_\eta$：是 Killing 矢量**。度规不含 $\eta$ → $\partial_\eta g_{\mu\nu} = 0$ → $\mathcal{L}_{\partial_\eta} g_{\mu\nu} = 0$。
> - **$\partial_\rho$：不是 Killing 矢量**。$g_{\mu\nu} \propto e^{2\rho}$ 显含 $\rho$ → $\partial_\rho g_{\mu\nu} \neq 0$。
> 
> **验证 $\partial_\eta$ 满足 Killing 方程**：
> 
> $\xi^\mu = \delta^\mu_\eta = (1, 0)$，降指标 $\xi_\mu = g_{\mu\nu}\xi^\nu = (e^{2\rho}, 0)$。
> 
> 先求 Christoffel 符号（$x^0 = \eta$，$x^1 = \rho$，号差 $(+,-)$）：
> 
> $$g_{\mu\nu} = \begin{pmatrix} e^{2\rho} & 0 \\ 0 & -e^{2\rho} \end{pmatrix},\qquad g^{\mu\nu} = \begin{pmatrix} e^{-2\rho} & 0 \\ 0 & -e^{-2\rho} \end{pmatrix}$$
> 
> 非零偏导数仅有 $\partial_\rho g_{\eta\eta} = 2e^{2\rho}$，$\partial_\rho g_{\rho\rho} = -2e^{2\rho}$。
> 
> $$\begin{aligned}
> \Gamma^\eta_{\eta\rho} = \Gamma^\eta_{\rho\eta} &= \frac{1}{2}g^{\eta\eta}\partial_\rho g_{\eta\eta} = \frac{1}{2}e^{-2\rho}\cdot 2e^{2\rho} = 1 \\[4pt]
> \Gamma^\rho_{\eta\eta} &= -\frac{1}{2}g^{\rho\rho}\partial_\rho g_{\eta\eta} = -\frac{1}{2}(-e^{-2\rho})\cdot 2e^{2\rho} = 1 \\[4pt]
> \Gamma^\rho_{\rho\rho} &= \frac{1}{2}g^{\rho\rho}\partial_\rho g_{\rho\rho} = \frac{1}{2}(-e^{-2\rho})\cdot(-2e^{2\rho}) = 1
> \end{aligned}$$
> 
> 计算 $\nabla_\mu\xi_\nu = \partial_\mu\xi_\nu - \Gamma^\lambda_{\mu\nu}\xi_\lambda$：
> 
> $$\begin{aligned}
> \nabla_\eta\xi_\eta &= \partial_\eta(e^{2\rho}) - \Gamma^\lambda_{\eta\eta}\xi_\lambda = 0 - \Gamma^\rho_{\eta\eta}\cdot 0 = 0 \\[4pt]
> \nabla_\eta\xi_\rho &= \partial_\eta(0) - \Gamma^\lambda_{\eta\rho}\xi_\lambda = -\Gamma^\eta_{\eta\rho}\,\xi_\eta = -1\cdot e^{2\rho} = -e^{2\rho} \\[4pt]
> \nabla_\rho\xi_\eta &= \partial_\rho(e^{2\rho}) - \Gamma^\lambda_{\rho\eta}\xi_\lambda = 2e^{2\rho} - \Gamma^\eta_{\rho\eta}\,\xi_\eta = 2e^{2\rho} - 1\cdot e^{2\rho} = e^{2\rho} \\[4pt]
> \nabla_\rho\xi_\rho &= \partial_\rho(0) - \Gamma^\lambda_{\rho\rho}\xi_\lambda = -1\cdot 0 = 0
> \end{aligned}$$
> 
> **验证 Killing 方程**：
> 
> $$\begin{aligned}
> \nabla_\eta\xi_\eta + \nabla_\eta\xi_\eta &= 0 + 0 = 0 \;\checkmark \\[4pt]
> \nabla_\eta\xi_\rho + \nabla_\rho\xi_\eta &= -e^{2\rho} + e^{2\rho} = 0 \;\checkmark \\[4pt]
> \nabla_\rho\xi_\rho + \nabla_\rho\xi_\rho &= 0 + 0 = 0 \;\checkmark
> \end{aligned}$$
> 
> → $\partial_\eta$ 是 Killing 矢量。✓
> 
> **在 Minkowski 坐标下证明 $\partial_\eta = x\partial_t + t\partial_x$**：
> 
> Rindler → Minkowski 坐标变换（来自 1.2(c)）：
> $$t = e^\rho\sinh\eta,\quad x = e^\rho\cosh\eta$$
> 
> 链式法则：
> 
> $$\begin{aligned}
> \partial_\eta &= \frac{\partial t}{\partial\eta}\frac{\partial}{\partial t} + \frac{\partial x}{\partial\eta}\frac{\partial}{\partial x} \\[4pt]
> &= e^\rho\cosh\eta\,\partial_t + e^\rho\sinh\eta\,\partial_x \\[4pt]
> &= x\,\partial_t + t\,\partial_x
> \end{aligned}$$
> 
> $$\boxed{\partial_\eta = x\partial_t + t\partial_x}$$
> 
> **这正是 $x$ 方向的 Lorentz boost Killing 矢量！** 回忆 6.1(b) 中 $M_{01}$ 的分量形式：
> $$\xi^\mu_{M_{01}} = (x, t, 0, 0) \;\Longleftrightarrow\; \xi_{M_{01}} = x\partial_t + t\partial_x$$
> 
> **统一的几何图像**：
> 
> - 在 Minkowski 坐标下，$\partial_\eta$ 表现为 boost Killing 矢量 → 生成 Lorentz 变换
> - 在 Rindler 坐标下，$\partial_\eta$ 表现为时间平移 Killing 矢量 → 度规不显含 $\eta$
> 
> 同一个 Killing 矢量在两个坐标系中扮演不同的角色：
> 
> | 坐标系 | $\partial_\eta$ 的表现 | 物理 |
> |:------|:----------------------|:-----|
> | Minkowski $(t,x)$ | $x\partial_t + t\partial_x$ | Boost 生成元 |
> | Rindler $(\eta,\rho)$ | $\partial_\eta$ | Rindler 时间平移 |
> 
> **这正是 Unruh 效应的几何核心**：Minkowski 真空的 boost Killing 矢量在 Rindler 坐标下成为时间平移生成元 → Rindler 观测者的 Hamiltonian 是 Minkowski 的 boost 算符 → Minkowski 真空对 Rindler 观测者表现为热态。你在 [[弯曲时空下的QFT]] 中正是使用了这个事实。

---

## 第七章 视界与因果结构

### 7.1 光锥与类光曲面

**(a)** 对 $1+1$ 维 Minkowski 时空，在 $(t,x)$ 图中画出过原点的光锥，标出类时、类光、类空区域。

**(b)** 对 Schwarzschild 度规，写出径向零测地线条件：
$$\frac{dr}{dt} = \pm\left(1 - \frac{2GM}{r}\right)$$
画出 $(t,r)$ 图（不含奇点），并指出 $r = 2GM$ 处光锥的行为。

### 7.2 Eddington-Finkelstein 坐标

**(a)** 定义乌龟坐标 $r_* = r + 2GM\ln|r/2GM - 1|$，再定义入射线坐标 $v = t + r_*$。证明线元变为：
$$ds^2 = -\left(1 - \frac{2GM}{r}\right)dv^2 + 2dv\,dr + r^2 d\Omega^2$$
此度规在 $r = 2GM$ 处**非奇异**。

**(b)** 在 $(v,r)$ 图中画出径向入射线和出射零测地线，并解释出射线为何在 $r < 2GM$ 区域只能向内走。

**(c)** 用此坐标证明 $r = 2GM$ 是一个单向膜（事件视界）——任何类时或类光曲线一旦进入 $r < 2GM$ 就永远无法返回 $r > 2GM$。

### 7.3 Kruskal 坐标与最大延拓 $\star$

**(a)** 定义 Kruskal 坐标：
$$T = e^{r/4GM}\sinh(t/4GM)\sqrt{\frac{|r-2GM|}{2GM}},\quad X = \ldots$$
证明线元变为：
$$ds^2 = \frac{32G^3M^3}{r}e^{-r/2GM}(-dT^2 + dX^2) + r^2 d\Omega^2$$

**(b)** 在 $(T,X)$ 图上，标出四个区域（I: 外部，II: 黑洞内部，III: 白洞，IV: 平行宇宙），画出 $r = 0$ 奇点和 $r = 2GM$ 视界。

**(c)** 指出 Einstein-Rosen 桥（可穿越虫洞为何不存在——它被奇点阻断）。

### 7.4 表面引力与 Hawking 温度 $\star$

**(a)** 对 Schwarzschild 视界，定义表面引力 $\kappa$（在静态 Killing 矢量 $\xi = \partial_t$ 的归一化下的加速度）。证明：
$$\kappa = \frac{1}{4GM}$$

**(b)** 通过 Euclid 时间的周期性（$\tau_E = it$ 的周期），导出 Hawking 温度：
$$T_H = \frac{\kappa}{2\pi} = \frac{1}{8\pi GM}$$

**(c)** 代入太阳质量 $M_\odot$，计算 Schwarzschild 黑洞的 Hawking 温度，并与 CMB 温度对比。


---

## 第八章 FLRW 宇宙学

### 8.1 Friedmann 方程

**(a)** 对 $3+1$ 维 FLRW 度规（含空间曲率 $k$）：
$$ds^2 = -dt^2 + a^2(t)\left[\frac{dr^2}{1-kr^2} + r^2 d\Omega^2\right]$$
计算 Einstein 张量，导出 Friedmann 方程：
$$\left(\frac{\dot{a}}{a}\right)^2 = \frac{8\pi G}{3}\rho - \frac{k}{a^2},\qquad \frac{\ddot{a}}{a} = -\frac{4\pi G}{3}(\rho + 3p)$$

**(b)** 从两个 Friedmann 方程推导出连续性方程 $\dot{\rho} + 3H(\rho+p) = 0$（$H \equiv \dot{a}/a$）。

**(c)** 证明对 $k=0$ 和单一成分宇宙，$a(t)$ 的解为：
- 辐射为主：$a \propto t^{1/2}$
- 物质为主：$a \propto t^{2/3}$
- 真空能为主：$a \propto e^{Ht}$

### 8.2 共形时间

**(a)** 定义共形时间 $\eta = \int dt/a(t)$。证明在共形时间下 FLRW 线元变为：
$$ds^2 = a^2(\eta)(-d\eta^2 + d\chi^2 + \ldots)$$
其中 $d\chi = dr/\sqrt{1-kr^2}$。

**(b)** 对 $k=0$ 辐射为主宇宙，证明 $a(\eta) \propto \eta$。对物质为主宇宙 $a(\eta) \propto \eta^2$。对 de Sitter 宇宙 $a(\eta) \propto -1/\eta$（$\eta < 0$）。

**(c)** 在共形时间图中画出一个光子从大爆炸（$\eta=0$）到今天的传播路径，并解释为何 $k=0$ 的共形图就是平直空间的三角形（"光锥"）。

### 8.3 视界问题与暴胀 $\star$

**(a)** 定义粒子视界 $d_p = \int_0^t dt'/a(t')$。在辐射为主和物质为主宇宙中，$d_p$ 如何随时间增长？

**(b)** 计算 CMB 最后散射面（$z=1100$，$t=38$ 万年）的粒子视界在天球上的角尺度。证明在没有暴胀的标准宇宙学中，因果不连接的天区比视界大得多——这就是**视界问题**。

**(c)** 证明 de Sitter 暴胀（$a(t) \propto e^{Ht}$）使粒子视界趋于常数，而物理尺度指数膨胀——从而在暴胀前使整个可观测宇宙处于因果接触中。


---

## 第九章 能量条件与奇点定理

### 9.1 经典能量条件

**(a)** 写出四种经典能量条件的数学表达式（用 $T_{\mu\nu}$ 或等效的 $\rho$ 和 $p$）：
- 弱能量条件（WEC）
- 零能量条件（NEC）
- 强能量条件（SEC）
- 主能量条件（DEC）

**(b)** 对理想流体 $T_{\mu\nu} = \text{diag}(-\rho, p, p, p)$，将四个条件简化为 $\rho$ 和 $p$ 的不等式。

**(c)** 验证：电磁场（$\rho = 3p$）满足哪些条件？真空能（$p=-\rho$）违反哪些条件？

### 9.2 类时测地线的汇与膨胀标量 $\star$

**(a)** 定义膨胀标量 $\theta = \nabla_\mu u^\mu$（类时测地线汇 $u^\mu$ 的体积膨胀率）。证明 Raychaudhuri 方程：
$$\frac{d\theta}{d\tau} = -\frac{1}{3}\theta^2 - \sigma_{\mu\nu}\sigma^{\mu\nu} + \omega_{\mu\nu}\omega^{\mu\nu} - R_{\mu\nu}u^\mu u^\nu$$

**(b)** 若 SEC 成立，$R_{\mu\nu}u^\mu u^\nu \geq 0$。假设无旋（$\omega_{\mu\nu}=0$），证明 $\theta$ 必然在有限本征时内发散到 $-\infty$（**共轭点**）。

**(c)** 简述此结果如何通向 Penrose-Hawking 奇点定理。

### 9.3 白洞与虫洞（概念题）

**(a)** 解释 Einstein 场方程的时间反演对称性为何允许白洞解，而热力学第二定律为何禁止白洞稳定存在。

**(b)** 简述 Morris-Thorne 可穿越虫洞需要违反哪些能量条件（特别是 NEC），以及"奇异物质"的含义。


---

## 第十章 ADM 形式与初值问题 $\star\star$

### 10.1 ADM 度规分解

**(a)** 证明任意 $3+1$ 维度规可以分解为：
$$ds^2 = -N^2 dt^2 + \gamma_{ij}(dx^i + N^i dt)(dx^j + N^j dt)$$
其中 $N$ 为流逝函数，$N^i$ 为移位矢量，$\gamma_{ij}$ 为诱导三维度规。

**(b)** 解释 $N$ 和 $N^i$ 的几何含义：它们分别如何描述等时面的"堆叠"方式？

### 10.2 外曲率与约束方程

**(a)** 定义外曲率 $K_{ij} = -\frac{1}{2N}(\partial_t\gamma_{ij} - \nabla_i N_j - \nabla_j N_i)$。对于 FLRW 度规（$N=1$，$N^i=0$），计算 $K_{ij}$。

**(b)** 证明 Einstein 方程分解为四个约束方程和六个演化方程：
- Hamiltonian 约束：$R^{(3)} + K^2 - K_{ij}K^{ij} = 16\pi G\,\rho$
- 动量约束：$\nabla_j(K^{ij} - \gamma^{ij}K) = 8\pi G\,S^i$

**(c)** 对 FLRW 度规，验证 Hamiltonian 约束等价于 Friedmann 方程。


---

## 附录

### A. 常用公式速查

- **Christoffel 符号**：$\Gamma^\mu_{\alpha\beta} = \frac{1}{2}g^{\mu\nu}(\partial_\alpha g_{\nu\beta} + \partial_\beta g_{\nu\alpha} - \partial_\nu g_{\alpha\beta})$
- **Riemann 张量**：$R^\rho{}_{\sigma\mu\nu} = \partial_\mu\Gamma^\rho_{\nu\sigma} - \partial_\nu\Gamma^\rho_{\mu\sigma} + \Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma} - \Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma}$
- **Ricci 张量**：$R_{\mu\nu} = R^\rho{}_{\mu\rho\nu}$
- **测地线偏离方程**：$\frac{D^2\xi^\mu}{D\tau^2} = R^\mu{}_{\nu\rho\sigma}u^\nu u^\rho \xi^\sigma$
- **Bianchi 恒等式**：$\nabla_{[\lambda}R_{\rho\sigma]\mu\nu} = 0$
- **Killing 方程**：$\nabla_\mu\xi_\nu + \nabla_\nu\xi_\mu = 0$

### B. 度规快速参考

| 时空 | 线元 | 关键参数 |
|------|------|----------|
| Minkowski | $-dt^2 + dx^2 + dy^2 + dz^2$ | — |
| Schwarzschild | $-(1-2GM/r)dt^2 + (1-2GM/r)^{-1}dr^2 + r^2 d\Omega^2$ | $M$ |
| FLRW（宇宙时） | $-dt^2 + a^2(t)[dr^2/(1-kr^2) + r^2 d\Omega^2]$ | $a(t), k$ |
| FLRW（共形时） | $a^2(\eta)[-d\eta^2 + d\chi^2 + \ldots]$ | $a(\eta)$ |
| Rindler | $e^{2\rho}(d\eta^2 - d\rho^2)$ | — |
| de Sitter（静态） | $-(1-\Lambda r^2/3)dt^2 + (1-\Lambda r^2/3)^{-1}dr^2 + r^2 d\Omega^2$ | $\Lambda$ |
| Kerr | $-\frac{\Delta-a^2\sin^2\theta}{\Sigma}dt^2 + \ldots$ | $M, a$ |

### C. 推荐阅读路径

| 你的目标              | 推荐章节顺序                                      |
| ----------------- | ------------------------------------------- |
| 计算工具精通            | 1 → 2.1 → 2.2 → 2.3（1-2 天）                  |
| Schwarzschild 全流程 | 1 → 4 → 6 → 7（2-3 天）                        |
| 宇宙学               | 1.2 → 2.2 → 3.3 → 8（2 天）                    |
| 引力波               | 5（1 天，需先学 1-2 章的基础）                         |
| 衔接弯曲时空 QFT        | 1.2(c) → 2.2 → 2.4 → 6.3(c) → 7.3 → 回看弯曲时空题 |
