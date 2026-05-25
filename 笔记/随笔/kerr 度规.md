---
up:
  - "[[随笔]]"
related:
  - "[[GR 基础计算习题册]]"
date: 2026-05-15
---
# Kerr 度规的推导

## 1. 物理背景与对称性

Kerr 度规描述的是**旋转黑洞**外部的真空引力场。与 Schwarzschild 度规（静态、球对称）不同，Kerr 黑洞具有角动量，因此时空是：

- **稳态 (stationary)**：存在类时 Killing 矢量场 $\xi^\mu = \partial_t$（度规系数不依赖于时间 $t$）
- **轴对称 (axisymmetric)**：存在类空 Killing 矢量场 $\eta^\mu = \partial_\phi$（度规系数不依赖于方位角 $\phi$）

> 与 Schwarzschild 不同，Kerr 时空**不是静态的**——旋转导致时空存在拖曳效应（frame-dragging），度规中出现 $dt\,d\phi$ 交叉项。

---

## 2. 稳态轴对称时空的一般形式

### 2.1 Lewis-Papapetrou 形式

最一般的稳态轴对称真空度规可以写成 **Lewis-Papapetrou 形式**（Weyl 型坐标）[^Lewis][^Papapetrou]：

$$
ds^2 = -e^{2U}(dt + A\,d\phi)^2 + e^{-2U}\left[ e^{2\gamma}(d\rho^2 + dz^2) + \rho^2 d\phi^2 \right]
\tag{2.1}
$$

其中 $U, A, \gamma$ 都是 $\rho, z$ 的函数（不含 $t, \phi$）。$\rho, z$ 是所谓 Weyl 型正则坐标。

### 2.2 度规形式的构造逻辑：为什么是这个形式？

Kerr 度规的最终形式并非凭空猜测，而是由**对称性约束 + 边界条件 + 可分离性要求**共同决定的。以下逐步剖析其构造逻辑。

#### 2.2.1 块对角结构：Papapetrou 定理

由于时空具有 $\partial_t$ 和 $\partial_\phi$ 两个 Killing 矢量场，最一般的稳态轴对称度规是 $2+2$ 分块形式：

$$
ds^2 = \underbrace{g_{tt}dt^2 + 2g_{t\phi}\,dt\,d\phi + g_{\phi\phi}d\phi^2}_{(t,\phi)\text{ 块}} \;+\; \underbrace{g_{rr}dr^2 + 2g_{r\theta}\,dr\,d\theta + g_{\theta\theta}d\theta^2}_{(r,\theta)\text{ 块}}
\tag{2.2a}
$$

> **为什么没有 $dt\,dr$、$dt\,d\theta$、$d\phi\,dr$、$d\phi\,d\theta$ 交叉项？**
>
> 这是 **Papapetrou 定理**（等价于 Kundt-Trümper 定理）的结论：对于真空稳态轴对称时空，若 Killing 矢量满足正交可迁条件，则 $(t,\phi)$ 二维曲面与 $(r,\theta)$ 二维曲面是**全局正交的**。这意味着所有混合分量 $g_{tr}=g_{t\theta}=g_{\phi r}=g_{\phi\theta}=0$。

此外，通过坐标变换可进一步消去 $g_{r\theta}$（在 $(r,\theta)$ 平面上取共形规范），使得 $(r,\theta)$ 块也对角化：

$$
ds^2 = g_{tt}dt^2 + 2g_{t\phi}dt\,d\phi + g_{\phi\phi}d\phi^2 + g_{rr}dr^2 + g_{\theta\theta}d\theta^2
\tag{2.2b}
$$

> 这与 Lewis-Papapetrou 形式 (2.1) 是等价的——只是坐标选择不同。

---

#### 2.2.2 $(t,\phi)$ 子空间的物理参数化

$(t,\phi)$ 块是一个 $2\times 2$ 对称矩阵，含 3 个独立函数。有两种等价但物理直觉不同的参数化方式：

**方式一：ZAMO 分解（物理直观）**

将 $(t,\phi)$ 块写为"观测者正交化"形式：

$$
ds^2_{(t,\phi)} = -N^2 dt^2 + \tilde{g}_{\phi\phi}\,(d\phi - \omega\,dt)^2
\tag{2.2c}
$$

其中：
- $N(r,\theta)$ — **lapse 函数**，控制坐标时 $t$ 与局域固有时的关系（对静态观测者 $d\tau = N dt$）
- $\omega(r,\theta) = -\dfrac{g_{t\phi}}{g_{\phi\phi}}$ — **frame-dragging 角速度**，即零角动量观测者 (ZAMO) 被时空拖曳的角速度
- $\tilde{g}_{\phi\phi} = g_{\phi\phi}$

这一形式的物理含义：在旋转时空中，与 $t=\text{const}$ 超曲面正交的观测者（ZAMO）并非静止，而是以 $\omega$ 被拖曳着旋转。

**方式二：双完全平方分解（几何动机）**

Kerr 的深层代数结构（Petrov D 型）使度规可以写为两个**具有主零方向意义的完全平方**的组合。观察 Schwarzschild 极限 ($a=0$) 下的期望行为：
- $g_{tt} \to -(1 - 2M/r)$，$g_{t\phi} \to 0$，$g_{\phi\phi} \to r^2\sin^2\theta$

引入旋转后，$dt$ 和 $d\phi$ 会混合。考虑以下两个具有明确几何意义的 1-form：

1. **$\boldsymbol{(dt - a\sin^2\theta\,d\phi)}$**：沿视界共转方向。在视界上 $\Delta=0$，对以 $\Omega_H = a/(2Mr_+)$ 旋转的观测者，此组合为零——对应 Kerr-Schild 形式中的主零方向（principal null direction）。

2. **$\boldsymbol{[(r^2+a^2)d\phi - a\,dt]}$**：沿轴对称方向的"正则角动量"组合。当 $a\to 0$ 时约化为 $r^2 d\phi$，恢复球对称下方位角的自然测度。

将这两个 1-form 配上合适的系数函数，即可构造出同时满足真空 Einstein 方程和渐近平直条件的度规。系数由 $\Sigma$ 和 $\Delta$ 决定。

---

#### 2.2.3 $\Sigma$ 与 $\Delta$ 的起源

这两个函数是整个度规的灵魂。它们的来源可从三条进路理解：

**进路一：Carter 可分离性 → 强制 $\Sigma$ 的形式**

Brandon Carter (1968) 提出：寻找一个**第四运动常数**（Carter 常数 $\mathcal{Q}$）使得 Hamilton-Jacobi 方程可分离变量。对最一般的稳态轴对称度规 (2.2b)，要求

$$
g^{\mu\nu}\,\partial_\mu S\,\partial_\nu S + m^2 = 0,\qquad S = -Et + L_z\phi + S_r(r) + S_\theta(\theta)
$$

可分离的**充要条件**是将度规函数强制为：

$$
g_{rr} = \frac{\Sigma(r,\theta)}{\Delta(r)},\quad g_{\theta\theta} = \Sigma(r,\theta),\quad \Sigma = r^2 + a^2\cos^2\theta
\tag{2.2d}
$$

这里的关键是 $\Sigma$ 必须分离为 $r$ 和 $\theta$ 两部分的**加法**：
$$
\Sigma(r,\theta) = \underbrace{r^2}_{\Sigma_r} \;+\; \underbrace{a^2\cos^2\theta}_{\Sigma_\theta}
$$

这种 **$r$-$\theta$ 分离性**是 Kerr 解区别于一般轴对称解的本质特征，也是度规具有"简洁"形式的原因。

**进路二：扁椭球坐标的自然性**

从扁椭球坐标 $(x,y)$ 的 Ernst 方程精确解 (4.6) 经坐标变换 $x = (r-M)/\sigma$, $y = \cos\theta$ 后，度规自然地产生：
- $g_{\theta\theta} \propto r^2 + a^2\cos^2\theta$——这恰好是**扁椭球坐标系下到环奇点的"平方距离"**
- $g^{rr} = 0$ 定义视界，它是一个仅依赖于 $r$ 的函数 $\Delta(r)$。求解场方程得出 $\Delta = r^2 - 2Mr + a^2$

**进路三：渐近平直边界条件**

在 $r \to \infty$ 处，时空必须恢复 Minkowski：

| 度规分量 | $r \to \infty$ 极限 | 物理含义 |
|:---:|:---|:---|
| $g_{tt}$ | $-1 + \dfrac{2M}{r} + O(r^{-2})$ | Newton 引力势 → 质量 $M$ |
| $g_{t\phi}$ | $-\dfrac{2J\sin^2\theta}{r} + O(r^{-3})$ | Lense-Thirring 效应 → 角动量 $J$ |
| $g_{rr}$ | $1 + \dfrac{2M}{r} + O(r^{-2})$ | 各向同性径向坐标 |
| $g_{\theta\theta}$ | $r^2$ | 球面角向距离 |
| $g_{\phi\phi}$ | $r^2\sin^2\theta$ | 平直空间方位角距离 |

这些渐近行为约束了 $\Sigma$ 和 $\Delta$ 的各项系数：
- $\Sigma \sim r^2$（当 $r \gg a$）保证 $g_{\theta\theta} \sim r^2$
- $\Delta \sim r^2 - 2Mr$ 中的 $-2Mr$ 来源于 Newton 极限下 $g_{tt} \sim -(1 - 2M/r)$

---

### 2.3 Boyer-Lindquist Ansatz（总结）

综合以上约束——Papapetrou 块对角定理 + frame-dragging 的 ZAMO 图像 + Carter 可分离性 + 渐近平直边界条件——稳态轴对称渐近平直真空度规的**唯一两参数解**即为 Kerr 度规。在 Boyer-Lindquist 坐标下：

$$
\boxed{
\begin{aligned}
ds^2 = &-\frac{\Delta}{\Sigma}\,(dt - a\sin^2\theta\,d\phi)^2 + \frac{\sin^2\theta}{\Sigma}\,\big[(r^2 + a^2)\,d\phi - a\,dt\big]^2 \\
&+ \frac{\Sigma}{\Delta}\,dr^2 + \Sigma\,d\theta^2
\end{aligned}}
\tag{2.3}
$$

其中：

- $\boxed{\Sigma = r^2 + a^2\cos^2\theta}$ — 椭球距离函数，体现轴对称向椭球对称的推广
- $\boxed{\Delta = r^2 - 2Mr + a^2}$ — 视界函数，$\Delta=0 \Rightarrow r_{\pm}=M\pm\sqrt{M^2-a^2}$
- $M$ — ADM 质量，$a = J/M$ — 比角动量 ($0 \leq a \leq M$)

> **几何直觉**：Kerr 度规可理解为 Schwarzschild 度规在椭球坐标下的"旋转推广"。$\Sigma = r^2 + a^2\cos^2\theta$ 实质上是从坐标原点到环奇点 $(r=0,\theta=\pi/2)$ 的椭球距离平方。度规中的两个完全平方分别对应 Kerr 时空的两个主零方向（Petrov D 型），这一代数结构保证了测地线方程和波动方程的可分离性（存在 Carter 常数）。

---

## 3. 真空 Einstein 场方程

真空中 Einstein 场方程为 $R_{\mu\nu} = 0$。

### 3.1 稳态轴对称下的场方程约化

对于形式 (2.1)，Einstein 方程 $R_{\mu\nu}=0$ 约化为以下耦合偏微分方程组：

1. **对 $U$ 的方程**（Laplace 型）：

$$
\nabla^2 U \equiv \frac{1}{\rho}\partial_\rho(\rho\,\partial_\rho U) + \partial_z^2 U = 0
\tag{3.1}
$$

> 这意味着 $U$ 是平直三维空间中的轴对称调和函数。

2. **对 $A$ 的方程**：

$$
\partial_\rho\left(\rho^{-1} e^{4U} \partial_\rho A\right) + \partial_z\left(\rho^{-1} e^{4U} \partial_z A\right) = 0
\tag{3.2}
$$

3. **对 $\gamma$ 的方程**（由 $U, A$ 确定）：

$$
\begin{aligned}
\partial_\rho \gamma &= \rho\left[(\partial_\rho U)^2 - (\partial_z U)^2\right] - \frac{1}{2\rho}e^{4U}\left[(\partial_\rho A)^2 - (\partial_z A)^2\right] \\
\partial_z \gamma &= 2\rho\,\partial_\rho U\,\partial_z U - \frac{1}{\rho}e^{4U}\,\partial_\rho A\,\partial_z A
\end{aligned}
\tag{3.3}
$$

方程 (3.3) 的可积性条件 $\partial_z\partial_\rho\gamma = \partial_\rho\partial_z\gamma$ 自动等价于 (3.1) 和 (3.2)。

---

## 4. Ernst 方程方法（复势形式）

### 4.1 Ernst 势

Ernst 发现了更加优美的复形式[^Ernst]。引入复势 $\mathcal{E}$：

$$
\mathcal{E} = e^{2U} + i\,\Phi
\tag{4.1}
$$

其中虚部 $\Phi$（扭势，twist potential）由下式定义：

$$
\partial_\rho \Phi = -\frac{1}{\rho}e^{4U}\partial_z A,\qquad \partial_z \Phi = \frac{1}{\rho}e^{4U}\partial_\rho A
\tag{4.2}
$$

则真空 Einstein 方程等价于一条优美的 **Ernst 方程**：

$$
\boxed{\nabla^2 \mathcal{E} = \frac{2}{\mathcal{E} + \bar{\mathcal{E}}}\,\nabla\mathcal{E}\cdot\nabla\mathcal{E}}
\tag{4.3}
$$

或显式写作

$$
(\mathcal{E} + \bar{\mathcal{E}})\,\nabla^2\mathcal{E} = 2\,\nabla\mathcal{E}\cdot\nabla\mathcal{E}
\tag{4.4}
$$

其中 $\nabla$ 是平直三维柱坐标 $(\rho, z, \phi)$ 中的梯度算子。

### 4.2 椭球坐标下的分离变量

为了求解 Ernst 方程，引入扁椭球坐标 (prolate spheroidal coordinates) $(x, y)$：

$$
\rho = \sigma\sqrt{(x^2 - 1)(1 - y^2)},\qquad z = \sigma\,xy
\tag{4.5}
$$

其中 $x \geq 1$，$|y| \leq 1$。参数 $\sigma$ 由边界条件确定，对 Kerr 解 $\sigma = \sqrt{M^2 - a^2}$。

在此坐标下，Ernst 方程的**一类精确解**为：

$$
\mathcal{E} = \frac{x - 1 + i\,(ay/\sigma)}{x + 1 + i\,(ay/\sigma)} 
\tag{4.6}
$$

或更一般地写作“有理函数”解的形式：

$$
\mathcal{E} = \frac{p\,x - i\,q\,y - 1}{p\,x - i\,q\,y + 1}
\tag{4.7}
$$

其中 $p, q$ 满足 $p^2 + q^2 = 1$。对应 Kerr 解：$p = 1, q = a/\sigma$。

此解与参数的关系为 $p = \sigma/M$，$q = a/M$。

---

## 5. 从 Ernst 势回到度规

### 5.1 提取 $U$ 和 $A$

由 Ernst 势 $\mathcal{E} = e^{2U} + i\Phi$，我们有：

$$
e^{2U} = \text{Re}(\mathcal{E}) = \frac{p^2x^2 + q^2y^2 - 1}{(px + 1)^2 + q^2y^2}
\tag{5.1}
$$

$$
\Phi = \text{Im}(\mathcal{E}) = \frac{-2qy}{(px + 1)^2 + q^2y^2}
\tag{5.2}
$$

从 $\Phi$ 通过积分 (4.2) 可解得 $A$：

$$
A = 2a M r\,\frac{\sin^2\theta}{\Sigma}\quad\text{（在后续坐标变换下）}
\tag{5.3}
$$

### 5.2 从 $(x,y)$ 回到 $(r, \theta)$

定义关系：

$$
x = \frac{r - M}{\sigma},\qquad y = \cos\theta,\qquad \sigma = \sqrt{M^2 - a^2}
\tag{5.4}
$$

注意：对 $a^2 > M^2$（裸奇点），$\sigma$ 变为虚数，需用不同的参数化。此处仅考虑 $a \leq M$ 的黑洞情形。

于是：

$$
\Sigma = r^2 + a^2\cos^2\theta
\tag{5.5}
$$

$$
\Delta = r^2 - 2Mr + a^2
\tag{5.6}
$$

---

## 6. 最终形式：Boyer-Lindquist 坐标下的 Kerr 度规

经过冗长但直接的计算，得到 Kerr 度规在 **Boyer-Lindquist 坐标** 下的标准形式[^BoyerLindquist]：

$$
\boxed{
\begin{aligned}
ds^2 = &-\left(1 - \frac{2Mr}{\Sigma}\right)dt^2 - \frac{4Mar\sin^2\theta}{\Sigma}\,dt\,d\phi 
+ \frac{\Sigma}{\Delta}\,dr^2 \\[4pt]
&+ \Sigma\,d\theta^2 + \left(r^2 + a^2 + \frac{2Ma^2 r\sin^2\theta}{\Sigma}\right)\sin^2\theta\,d\phi^2
\end{aligned}}
\tag{6.1}
$$

其中：
- $M$ — 黑洞质量
- $a = J/M$ — 单位质量的角动量 ($0 \leq a \leq M$)
- $\Sigma = r^2 + a^2\cos^2\theta$
- $\Delta = r^2 - 2Mr + a^2$

### 6.1 分量形式

度规非零分量为：

$$
\begin{aligned}
g_{tt} &= -\left(1 - \frac{2Mr}{\Sigma}\right) \\[4pt]
g_{t\phi} = g_{\phi t} &= -\frac{2Mar\sin^2\theta}{\Sigma} \\[4pt]
g_{rr} &= \frac{\Sigma}{\Delta} \\[4pt]
g_{\theta\theta} &= \Sigma \\[4pt]
g_{\phi\phi} &= \left(r^2 + a^2 + \frac{2Ma^2 r\sin^2\theta}{\Sigma}\right)\sin^2\theta
\end{aligned}
\tag{6.2}
$$

---

## 7. 极限情况

### 7.1 Schwarzschild 极限 ($a \to 0$)

当 $a \to 0$：

- $\Sigma \to r^2$
- $\Delta \to r^2 - 2Mr$
- $g_{t\phi} \to 0$（交叉项消失，时空恢复静态）

$$
ds^2 = -\left(1 - \frac{2M}{r}\right)dt^2 + \left(1 - \frac{2M}{r}\right)^{-1}dr^2 + r^2(d\theta^2 + \sin^2\theta\,d\phi^2)
\tag{7.1}
$$

即恢复 Schwarzschild 度规。

### 7.2 Minkowski 极限 ($M \to 0$)

当 $M \to 0$：
- $\Delta \to r^2 + a^2$
- $\Sigma \to r^2 + a^2\cos^2\theta$

得到扁椭球坐标下的平直时空（零质量极限的 Kerr 度规即 Minkowski 时空的椭球坐标表示）。

---

## 8. 关键几何特征

### 8.1 视界 (Horizons)

视界由 $g^{rr} = \Delta/\Sigma = 0 \Rightarrow \Delta = 0$ 确定：

$$
r_{\pm} = M \pm \sqrt{M^2 - a^2}
\tag{8.1}
$$

- $r_+$：外视界（事件视界）
- $r_-$：内视界（Cauchy 视界）
- 极端 Kerr 黑洞：$a = M$ 时，$r_+ = r_- = M$（单视界）

### 8.2 静界 (Ergosphere / 稳态极限面)

静界由 $g_{tt} = 0$ 确定：

$$
r_{E}^{\pm}(\theta) = M \pm \sqrt{M^2 - a^2\cos^2\theta}
\tag{8.2}
$$

- 外静界与视界之间的区域称为 **能层 (ergosphere)**
- 在能层内，任何观测者必须随黑洞一同旋转（frame-dragging 效应）

### 8.3 环奇点 (Ring Singularity)

Kreetschmann 标量 $R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}$ 在 $\Sigma = 0$ 处发散：

$$
r = 0,\quad \theta = \frac{\pi}{2}\quad\Rightarrow\quad r^2 + a^2\cos^2\theta = 0
\tag{8.3}
$$

即奇点为赤道面 $(\theta = \pi/2)$ 上的半径为 $a$ 的圆环（**环奇点**），而非点奇点。

---

## 9. 附注：Kerr-Schild 形式

Kerr 度规也可写成 **Kerr-Schild 形式**[^KerrSchild]：

$$
g_{\mu\nu} = \eta_{\mu\nu} + 2H\,k_\mu k_\nu
\tag{9.1}
$$

其中：
- $\eta_{\mu\nu}$ 是 Minkowski 度规
- $k_\mu$ 是零矢量（对 $\eta_{\mu\nu}$ 和 $g_{\mu\nu}$ 同时为零）
- $H = \dfrac{Mr^3}{r^4 + a^2z^2}$

这一形式在 Kerr 的原始推导和量子引力研究中尤为重要。

---

[^Lewis]: Lewis, T. (1932). *Proc. Roy. Soc. Lond.* A **136**, 176.
[^Papapetrou]: Papapetrou, A. (1953). *Ann. Physik* **12**, 309.
[^Carter]: Carter, B. (1968). *Phys. Rev.* **174**, 1559.
[^Ernst]: Ernst, F.J. (1968). *Phys. Rev.* **167**, 1175.
[^BoyerLindquist]: Boyer, R.H. & Lindquist, R.W. (1967). *J. Math. Phys.* **8**, 265.
[^KerrSchild]: Kerr, R.P. & Schild, A. (1965). *Proc. Symp. Appl. Math.* **17**, 199.

---

