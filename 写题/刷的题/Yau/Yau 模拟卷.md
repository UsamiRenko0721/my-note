---
up:
  - "[[写题]]"
related:
  - "[[Yau_数学物理_Solutions]]"
  - "[[Yau 理论力学]]"
  - "[[Yau 电动力学]]"
  - "[[Yau 量子力学]]"
  - "[[Yau 统计力学]]"
  - "[[Yau 广义相对论]]"
  - "[[Yau 量子场论]]"
date: 2026-05-16
tags:
  - 模拟卷
  - 丘赛
  - 数学物理
---

# 丘赛数学物理 模拟卷

> 从 2022–2025 四届真题中精选，涵盖理论力学、电动力学、量子力学、统计力学、广义相对论、量子场论六大方向。

## 选题说明

| 题号  | 学科    | 来源     | 核心考点                                                |
| --- | ----- | ------ | --------------------------------------------------- |
| 1   | 理论力学  | 2024 年 | 拉格朗日力学、有效势、轨道稳定性、比奈方程、封闭轨道条件                        |
| 2   | 电动力学  | 2025 年 | 圆偏振波包的 Maxwell 解、角动量、傍轴修正、光子解释                      |
| 3   | 量子力学  | 2024 年 | 海森堡绘景、含时微扰、相干态、跃迁概率                                 |
| 4   | 统计力学  | 2025 年 | 精确配分函数、自由能、比热、磁化率、涨落                                |
| 5   | 广义相对论 | 2023 年 | 真空爱因斯坦方程+宇宙学常数、Schwarzschild-de Sitter 解、Killing 矢量 |
| 6   | 量子场论  | 2025 年 | Weyl 不变性、共形耦合 $\xi=-1/6$、de Sitter 时空标量场            |


**建议用时**: 3 小时 | **总分**: 120 分（每题 20 分）

> [!tip] 使用建议
> 每道题先尝试独立求解，再对照 [[Yau_数学物理_Solutions]] 中的解答。重点关注 **Higher viewpoint** 段落中的结构洞见。

---

# 第一题：中心幂律势（理论力学，2024）

Consider the motion of a particle of mass $m$ in an attractive central potential of the form

$$V(r) = \alpha r^{k}$$

where $k$ and $\alpha$ are real constants of the same sign (both positive or both negative).

**(a)** Write down the Lagrangian using polar coordinates $(r, \varphi)$.

**(b)** Using conservation of the angular momentum, reduce the problem of determining the radial motion to an effective one-dimensional problem (write down the effective Lagrangian).

**(c)** Determine the radius and period of the circular orbits.

**(d)** For which values of $k$ is the circular orbit stable?

**(e)** Assuming that the circular orbit is stable, consider a small perturbation around it. Find the period of the small oscillations. In the approximation of small oscillations, for which values of $k$ will the orbit close?

**(f)** Go back to the full 2D problem for $r$ and $\varphi$ (the polar coordinates in the plane of the orbit). Eliminate the time dependence and write a differential equation for the orbit.

> [!example]- 解答参考
> - [[Yau_数学物理_Solutions#3.1 Problem 1: Central power-law potentials and closed near-circular orbits]]
> - [[Yau 理论力学#24 年]]

做出 abcdef 部分

---

# 第二题：圆偏振波包的角动量（电动力学，2025）

Consider a wave packet with a transverse profile $E_{0}(x,y)$ propagating in the $z$ direction. For definiteness you may assume that the wave packet has a Gaussian profile

$$E_{0}(x,y) = \mathcal{A}e^{-\frac{x^{2} + y^{2}}{4\sigma^{2}}}$$

and is infinitely broad in the $z$ direction. The following integrals may be useful:

$$\int_{-\infty}^{\infty} du \, e^{-\alpha u^{2}} = \sqrt{\frac{\pi}{\alpha}}, \quad \int_{-\infty}^{\infty} du \, e^{-\alpha u^{2}} e^{iku} = \sqrt{\pi}\, e^{-\frac{k^{2}}{4\alpha}}$$

**(a)** When all derivatives of $E_{0}(x,y)$ are neglected, show that in Gaussian (Heaviside-Lorentz) units

$$\mathbf{E}^{(0)}(t,\mathbf{r}) = E_{0}(x,y)e^{i(kz - \omega t)}\frac{\hat{\mathbf{x}} + i\hat{\mathbf{y}}}{\sqrt{2}}, \quad \mathbf{B}^{(0)}(t,\mathbf{r}) = \hat{\mathbf{z}}\times \mathbf{E}^{(0)}$$

is a solution to the Maxwell equations for $\omega = ck$.

**(b)** Calculate the time averaged energy per length in the wave packet, $\langle U \rangle$.

**(c)** When the derivatives of $E_{0}(x,y)$ are not neglected, eq (3) is not a solution to the Maxwell equations. Determine the corrections to $\mathbf{E}^{(0)}$ and $\mathbf{B}^{(0)}$ to first order in gradients for $k\sigma \gg 1$.

> Hint: try a solution for $\mathbf{E}$ (and analogously for $\mathbf{B}$) of the form
> $$\mathbf{E}(t,\mathbf{r}) = \mathbf{E}^{(0)} + \mathbf{E}^{(1)}(x,y)e^{i(kz - \omega t)}\hat{\mathbf{z}}$$

**(d)** Write the solution to the last question as a linear superposition of the plane wave solutions to the Maxwell equations. First use the superposition to qualitatively explain why there is the correction to the electric field parallel to $\hat{\mathbf{z}}$, and then use the superposition to precisely reproduce this correction.

**(e)** Calculate the $z$-component of the time averaged angular momentum per length in the wave packet, $\langle L^{z} \rangle$, to the lowest non-trivial order in $k\sigma$.

**(f)** Determine the ratio $\langle L^{z} \rangle / \langle U \rangle$. Interpret the result using photons.

> [!example]- 解答参考
> - [[Yau_数学物理_Solutions#4.2 Problem 2: Angular momentum of a circularly polarized wave packet]]
> - [[Yau 电动力学#25 年]]

做出 abcef 部分

---

# 第三题：受迫谐振子与相干态（量子力学，2024）

Consider a 1-dim quantum-mechanical harmonic oscillator with mass $m$ and resonance frequency $\omega$. The oscillator initially (at $t \to -\infty$) is in its ground state. It is then subjected to a transient perturbation $\Delta H = F(t)x$ with $F(t \to \pm\infty) \to 0$.

**(a)** Write down the Hamiltonian $\hat{H}$ of the perturbed oscillator in terms of the usual ladder operators $\hat{a}$ and $\hat{a}^{\dagger}$, and solve their equations of motion in the Heisenberg picture. Show that the Hamiltonian at $t \to \pm\infty$ takes the form

$$\hat{H} = \hbar \omega\left( \hat{a}^{\dagger}_{\pm \infty}\hat{a}_{\pm \infty} + \frac{1}{2} \right)$$

and determine the relation between $a_{+\infty}$ and $a_{-\infty}$.

**(b)** At $t \to \pm\infty$, the ladder operators act on the state $|n_{\pm \infty}\rangle = (1/\sqrt{n!})(\hat{a}^{\dagger}_{\pm \infty})^{n}|0_{\pm \infty}\rangle$. Determine the probabilities $|c_{n}|^{2}$ that the oscillator has undergone a transition from the initial ground state to the $n$-th excited state at the end of the time evolution.

**(c)** What is the expectation value of the energy at the end of the time evolution?

**(d)** Now assume that $F(t) = F_{0}e^{-t^{2}/(2\sigma_{t}^{2})}$, with $F_{0} = \eta\hbar\omega/l$ where $\eta$ is a dimensionless parameter, and $l = \sqrt{\hbar/(m\omega)}$ is the harmonic oscillator length. For short pulses with $\sigma_{t}\omega \ll 1$, determine the maximum pulse strength $\eta$ for which less than 1% of the population gets lost from the ground state. Show explicitly that in the limit $\sigma_{t}\omega \ll 1$, losses can be suppressed for any given value of $\eta$.

> [!example]- 解答参考
> - [[Yau_数学物理_Solutions#3.2 Problem 2: A forced harmonic oscillator and coherent-state transitions]]
> - [[Yau 量子力学#24 年]]

做出 abc 部分

---

# 第四题：三角形 Ising 模型（统计力学，2025）

The Ising model on a triangle is described by the energy:

$$E = -J(\sigma_{1}\sigma_{2} + \sigma_{2}\sigma_{3} + \sigma_{3}\sigma_{1}) - h(\sigma_{1} + \sigma_{2} + \sigma_{3})$$

Here $J$ and $h$ are known parameters: exchange energy and external magnetic field, respectively. The Ising spins $\sigma_{1,2,3}$ are the only degrees of freedom and take values $\pm 1$. Assume that the temperature of the system is $T$. You may work in units such that $k_{B} = 1$.

**(a)** Compute the partition function of the model.

**(b)** Compute the free energy and the entropy of the model.

**(c)** Compute the specific heat at temperature $T$ and $h = 0$. What does the specific heat look like when $T \ll J$ and $T \gg J$?

**(d)** Compute the magnetization $M = \langle \sigma \rangle \equiv \langle \sigma_{1} + \sigma_{2} + \sigma_{3} \rangle$ at given $h$ and $T \ll J$. What is the behavior of the magnetic susceptibility $\chi = \left. \frac{\partial M}{\partial h} \right|_{h=0}$ at low temperature ($T \ll J$)?

**(e)** Find the fluctuation of magnetization $\langle (\sigma - M)^{2} \rangle$ at $T \ll J$.

> [!example]- 解答参考
> - [[Yau_数学物理_Solutions#4.4 Problem 4: The Ising model on a triangle]]
> - [[Yau 统计力学#25 年]]

做出 a

---

# 第五题：Schwarzschild-de Sitter 度规（广义相对论，2023）

Consider the vacuum Einstein's equation in four dimensional spacetime with a cosmological constant

$$R_{\mu \nu} - \frac{1}{2}g_{\mu \nu}R + g_{\mu \nu}\Lambda = 0$$

**(a)** Prove that $R_{\mu \nu} = k g_{\mu \nu}$ and find the value of $k$.

**(b)** Now start with an ansatz of a metric in the following form

$$ds^{2} = -f(r)dt^{2} + \frac{1}{f(r)}dr^{2} + r^{2}(d\theta^{2} + \sin^{2}\theta \, d\phi^{2})$$

where $f(r)$ is a polynomial in $r$. Compute non-zero components of the Ricci tensor $R_{\mu \nu}$ and scalar curvature $R$ of this metric.

**(c)** Assuming that the above ansatz is a solution of the vacuum Einstein equation with cosmological constant $\Lambda$, solve $f(r)$.

**(d)** Prove that $\partial_{t}$ and $\partial_{\phi}$ are Killing vector fields.

> [!example]- 解答参考
> - [[Yau_数学物理_Solutions#2.5 Problem 5: Schwarzschild-de Sitter geometry]]
> - [[Yau 广义相对论#23 年]]

做出 abcd 部分

---

# 第六题：共形标量场（量子场论，2025）

In this problem, we explore some physical properties of a conformal scalar field. Use natural units $c = \hbar = 1$.

**(a)** Consider a massless scalar field $\phi$ in Minkowski spacetime with the action

$$S = -\frac{1}{2}\int d^{4}x \, (\partial_{\mu}\phi)^{2}$$

Show that the action is invariant under a rigid rescaling of the metric, namely $\eta^{\mu\nu} \to \tilde{\eta}^{\mu\nu} = \Omega^{2}\eta^{\mu\nu}$ with $\Omega$ constant, if one rescales simultaneously $\phi \to \tilde{\phi} = \Omega^{\Delta}\phi$. Determine $\Delta$..

**(b)** Consider a local rescaling of an arbitrary metric $g^{\mu\nu} \to \tilde{g}^{\mu\nu} = \Omega^{2}g^{\mu\nu}$ and also $\phi \to \tilde{\phi} = \Omega^{\Delta}\phi$. Determine the transformation of the action

$$S = -\frac{1}{2}\int d^{4}x \, \sqrt{-g}\, g^{\mu\nu}(\partial_{\mu}\phi)(\partial_{\nu}\phi)$$

under the local rescaling. Can $S$ be made invariant by appropriately choosing the value of $\Delta$?

**(c)** Suppose the Ricci scalar transforms as $R \to \tilde{R}$ under the local rescaling $g^{\mu\nu}(x) \to \Omega^{2}(x)g^{\mu\nu}(x)$. Determine $\tilde{R}$.

**(d)** Show that the invariance of the scalar action under local rescaling can be restored by adding a new term:

$$S = \int d^{4}x \, \sqrt{-g}\left[ \frac{1}{2}(\partial_{\mu}\phi)^{2} - \frac{1}{2}R\xi\phi^{2} \right]$$

where $\xi$ is a coupling constant. Determine the value of $\xi$ such that the action is invariant. A scalar field $\phi$ with the above action is called a **conformal scalar**.

**(e)** Consider a spacetime with the metric:

$$ds^{2} = \frac{-d\tau^{2} + d\mathbf{x}^{2}}{(H\tau)^{2}}$$

where $\mathbf{x} \in \mathbb{R}^{3}$, $\tau \in (-\infty, 0)$, and $H$ is a constant. Show that a conformal scalar $\phi$ in this spacetime has an action identical to a scalar field with nonzero mass $m$. Determine $m$.

> [!example]- 解答参考
> - [[Yau_数学物理_Solutions#4.6 Problem 6: The conformal scalar field]]
> - [[Yau 量子场论#25 年]]

做出 ab 部分

---

## 难度评估

| 题号 | 学科 | 难度 | 说明 |
|------|------|:----:|------|
| 1 | 理论力学 | ⭐⭐⭐ | 经典力学综合，计算量中等，但需要系统推导 |
| 2 | 电动力学 | ⭐⭐⭐⭐ | 傍轴近似与角动量计算较有挑战性 |
| 3 | 量子力学 | ⭐⭐⭐ | 相干态是核心，含时微扰的标准套路 |
| 4 | 统计力学 | ⭐⭐ | 小系统精确解，计算直接但需仔细 |
| 5 | 广义相对论 | ⭐⭐⭐⭐ | 含 $\Lambda$ 的爱因斯坦方程，计算 Christoffel 符号繁琐 |
| 6 | 量子场论 | ⭐⭐⭐⭐ | Weyl 不变性与共形耦合，概念深刻 |

> 整体难度与真实丘赛数学物理卷持平。建议按顺序作答，第 4 题可作为热身。
