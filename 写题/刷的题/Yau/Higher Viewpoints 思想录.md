---
tags:
  - 数学物理
  - 思想方法
  - 高视角
date: 2026-05-07
up:
  - "[[Yau_数学物理_Solutions]]"
  - "[[写题]]"
---

# Higher Viewpoints：Yau 数学物理的高视角思想录

> 从 Yau Mathematical Physics Solutions 2022-2025 全部 24 道题的 Higher viewpoint 中萃取。每题不再重复计算细节，只保留"这道题到底在讲什么结构"。

---

## 一、对称性与守恒律

### 2022 P1 — 时间反演与反幺正性

> Time reversal is the prototype of an anti-unitary symmetry. Ordinary spatial symmetries act by reshuffling basis vectors while leaving complex scalars untouched; time reversal must also reverse the sign of the quantum phase generator $\mathrm{i}\partial_t$. In a real one-dimensional nondegenerate bound-state problem this anti-linearity explains why the eigenfunction can be chosen real. The statement is special to the absence of degeneracy: when a time-reversed partner belongs to a distinct state, the symmetry may instead organize states into pairs, as in **Kramers degeneracy**.

**核心洞见**：时间反演不是"把 t 换成 -t"这么简单——它必须同时把 i 换成 -i。这个反线性结构直接解释了为什么无简并束缚态可以取实波函数。如果有简并呢？那就不是波函数变实，而是出现 **Kramers 对**。

关联：[[Yau 量子力学#22 年]]

---

### 2022 P3 — Killing 场与守恒动量

> A Killing field is the infinitesimal form of an isometry. The equality $D_{(\mu}k_{\nu)} = 0$ says that the metric has zero first-order deformation along the flow of $k$. For geodesic motion, this metric symmetry becomes a conserved linear momentum $k^{\mu}P_{\mu}$. **Time translations give energy, rotations give angular momentum, and spatial translations give ordinary linear momentum; all are the same theorem written in different coordinate systems.**

**核心洞见**：能量、角动量、线动量——它们本质上是同一件事：度规的等距对称性导致的 Noether 守恒量。只是坐标系不同，"名字"不同而已。

---

### 2022 P5 — 标度与共形流

> The trace of the stress tensor is the local diagnostic for scale and conformal symmetry. Classically, a traceless stress tensor implies conservation of the dilatation current and, for a suitably improved stress tensor, the special conformal currents. The dilaton construction shows how a scale can be hidden inside a field rather than inserted as a fixed number. **Quantum theory changes the situation because choosing a regulator and renormalization scale breaks the naive scaling relation, producing the trace anomaly.**

**核心洞见**：能动张量的迹 $\theta^{\mu}_{\mu}$ 是标度对称性的"诊断器"。经典层面 $\theta^{\mu}_{\mu}=0$ ↔ 标度不变。量子层面？重整化引入了一个尺度，所以 $\langle \theta^{\mu}_{\mu} \rangle \neq 0$——这就是**迹反常**。

---

## 二、量子力学：代数结构

### 2022 P2 — Schwinger 表示

> The Schwinger representation converts a two-oscillator degeneracy problem into angular-momentum representation theory. The perturbation then asks for an operator to be diagonalized inside a fixed irreducible $\mathfrak{su}(2)$-module. **This is the standard strategy behind many oscillator degeneracy problems: first identify the hidden symmetry algebra, then diagonalize the perturbation on the finite-dimensional symmetry multiplet rather than in the full Hilbert space.**

**核心洞见**：两个谐振子的简并空间 $\{n_1+n_2=n\}$ 恰好构成 $\mathfrak{su}(2)$ 的 $j=n/2$ 不可约表示。微扰计算不是在整个 Hilbert 空间里蛮干，而是**在这个有限维对称多重态里对角化**。识别隐藏的对称代数 → 在对称多重态里做微扰，这是谐振子简并问题的标准策略。

关联：[[Yau 量子力学#22 年]]

---

### 2024 P2 — 受迫谐振子与相干态

> A linear force does not squeeze or distort a harmonic oscillator state; **it translates the state in phase space.** Consequently the entire transition problem is determined by a single complex displacement parameter, which is the Fourier component of the force at the oscillator frequency. Slow pulses are adiabatically suppressed, while pulses with spectral weight near $\omega$ efficiently create excitations. The Poisson distribution is the number-state shadow of a coherent final state.

**核心洞见**：线性外力 = 相空间平移。不挤压、不扭曲，只平移。所以整个问题归结为一个复数 $\beta$（外力在 $\omega$ 处的 Fourier 分量）。末态是相干态，在各粒子数基上的投影自然给出 Poisson 分布。脉冲的频谱在 $\omega$ 附近有分量 → 高效激发；慢脉冲（绝热）→ 抑制跃迁。

关联：[[Yau 量子力学#24 年]]

---

### 2025 P3 — 电场中的平移谐振子

> A constant electric field completes the square rather than changing the oscillator's intrinsic frequency. The spectrum is shifted uniformly downward, and the eigenstates are translated number states. Dynamically, an old ground state is not the new ground state; **it is a coherent state relative to the shifted oscillator.** The oscillating dipole moment is therefore the quantum expectation-value version of classical motion about the new equilibrium.

**核心洞见**：匀强电场不改变频率，只平移平衡点。关键点：旧基态 $|0_{\text{old}}\rangle$ 不是新基态，而是新谐振子的相干态。所以初态在新表象下有 Poisson 分布，每过一个周期 $T=2\pi/\omega$ 回到自身。

---

### 2023 P2 — 各向异性谐振子的简并微扰

> Degenerate perturbation theory is the infinitesimal form of normal-mode diagonalization. The perturbation $xy$ does not introduce an essentially new interaction; **it says that the chosen coordinate axes are not principal axes of the quadratic potential.** The finite-dimensional perturbation matrices are therefore the first-order shadows of an exact rotation of coordinates. This problem is a useful model for recognizing when perturbation theory is hiding a simple change of variables.

**核心洞见**：$xy$ 项不是"新的相互作用"——它只是说你的坐标轴不是势能的主轴。旋转 $45^\circ$ 就对角化了。微扰论给出的有限维矩阵就是坐标旋转的一阶影子。**当你发现微扰论的结果恰好能通过一个简单变量变换精确对角化时，说明微扰论在"隐藏"一个更简单的物理。**

关联：[[Yau 量子力学#23 年]]

---

## 三、统计物理：序与涨落

### 2024 P4 — 平均场 Ising 与临界指数

> Mean-field theory is Landau theory in microscopic disguise. The self-consistency equation and the free-energy expansion contain the same information: a quadratic coefficient changes sign while a positive quartic term stabilizes the ordered phase. The resulting exponents are classical because **spatial fluctuations have been replaced by an averaged field.** In low dimensions the true exponents can differ, but the mean-field calculation remains the baseline mechanism for symmetry breaking.

**核心洞见**：平均场 = 穿了微观马甲的 Landau 理论。核心机制：二次项系数在 $T_c$ 变号 + 正四次项稳定有序相 = 对称性自发破缺。临界指数是"经典"的 $(\alpha=0,\ \beta=1/2,\ \gamma=1)$，因为在平均场里**空间涨落被一个平均场替代了**。在低维，真正的涨落会改变指数，但平均场永远是理解对称破缺的基准。

关联：[[Yau 统计力学#24 年]] | [[统计物理知识点#三、平均场理论]]

---

### 2025 P4 — 三角 Ising 模型

> The triangle Ising model is small enough to solve exactly, yet it already contains the key finite-size signature of ferromagnetism. At low temperature the two aligned states dominate, so the average magnetization vanishes at zero field by symmetry but its fluctuations are large. A tiny field selects one of the two sectors, producing a Curie-like susceptibility. **The absence of a thermodynamic limit prevents a true singular phase transition.**

**核心洞见**：三个自旋就够了——已经包含铁磁序的有限尺寸信号。低温下 $M=\pm 3$ 两个态等权主导 → $\langle M \rangle_{h=0}=0$，但涨落 $\langle (\Delta M)^2 \rangle \approx 9$ 很大。加一个无穷小的场 → 立即选出一个方向 → Curie 型磁化率 $\chi \sim 1/T$。没有热力学极限 → 没有真正的奇异相变，但**相变的所有"种子"都在这个小系统里了。**

关联：[[Yau 统计力学#25 年]] | [[统计物理知识点#二、Ising 模型]]

---

### 2023 P4 — 一维玻色子与费米子的热容

> The detailed microscopic statistics differ, but **the low-temperature answer is controlled by the same one-dimensional gapless structure.** Linear dispersion near the relevant low-energy points gives a constant density of states per energy, so the thermal energy scales as $T^2$ and the heat capacity as $T$. The only model-dependent parameter that remains is the propagation velocity: $v$ for the boson and $v_F$ for the fermion.

**核心洞见**：Bose 还是 Fermi——微观统计完全不同，但低温热容给出**一样的形式** $C \propto T$。因为低温下只有无能隙的低能激发有贡献，而一维无能隙模的态密度是常数。唯一区分 Bose 和 Fermi 的参数是传播速度。这是**普适性（universality）**的绝佳例子：微观细节在低能下被"洗掉"了。

关联：[[统计物理知识点#四、低维系统的热容]]

---

### 2025 P1 — 旋转圆环上的珠子

> The rotating hoop is a concrete pitchfork bifurcation. The angular velocity controls the curvature of the effective potential at the bottom. Below the critical value $\sqrt{g/R}$, gravity dominates and the bottom is stable. Above it, centrifugal effects destabilize the bottom and create two symmetric stable equilibria. **This is the mechanical analogue of a Landau double-well transition, with $\theta$ playing the role of an order parameter.**

**核心洞见**：一个经典力学系统完美地演示了**叉式分岔**（pitchfork bifurcation）。有效势 $V_{\text{eff}}(\theta)$ 的底部曲率由 $\omega$ 控制：$\omega < \omega_c$ → 单稳（顺磁类比），$\omega > \omega_c$ → 双稳（铁磁类比）。$\theta$ 就是"序参量"。这是**没有统计物理的统计物理**——Landau 相变理论的纯力学类比。

---

## 四、几何与引力

### 2022 P4 — Eddington-Finkelstein 视界

> A null hypersurface is geometrically unlike a spacelike or timelike hypersurface: **its normal vector is also tangent to it.** The surface $r = 2M$ is singled out by the vanishing of the inverse radial component $g^{rr}$, which makes the normal $dr$ null after raising the index. This is why a horizon can be generated by null curves lying inside the horizon itself.

**核心洞见**：类光超曲面和类空/类时超曲面本质不同——**法矢量同时也是切矢量**。$g^{rr}=0$ 在 $r=2M$ 处使得 $dr$ 升指标后变成类光 → 这就是视界的几何定义。视界上的生成元（null generator）躺在视界内部，这是它和普通曲面的根本区别。

---

### 2023 P5 — Schwarzschild-de Sitter 度规

> The Schwarzschild-de Sitter metric is determined by symmetry plus the Einstein condition. Spherical symmetry reduces a nonlinear tensor equation to **a single radial equation for $f(r)$.** The integration constant is interpreted as the mass parameter, while the cosmological constant supplies the quadratic de Sitter term.

**核心洞见**：球对称 + Einstein 方程 → 整个非线性张量方程坍缩为一个 $f(r)$ 的径向 ODE：$(rf)' = 1 - \Lambda r^2$。$M$ 和 $\Lambda$ 是积分的两个常数，分别对应质量和宇宙学常数。这是**对称性约化**的威力——十个耦合偏微分方程变成一阶常微分方程。

---

### 2024 P5 — de Sitter 静态度规

> The static patch metric is a coordinate expression of a constant-curvature hyperquadric. The horizon at $r = \alpha$ is not a curvature singularity; it is where the static time coordinate ceases to be timelike. **The embedding picture explains the curvature immediately, while the coordinate form makes the Killing fields and the horizon structure visible.** These are complementary descriptions of the same de Sitter geometry.

**核心洞见**：dS 空间可以从两个互补的角度看：(1) 嵌入图景 → 曲率一目了然（常曲率空间的 Gauss 方程）；(2) 静态度规 → Killing 场和视界结构一目了然。**同一个几何，两种表示各有优势。** $r = \alpha$ 不是奇点——只是静态度规中 $\partial_t$ 从类时变类光的地方。

---

### 2025 P5 — 双黑洞系统的引力波

> The gravitational-wave chirp is **energy balance made observable.** The quadrupole luminosity removes orbital binding energy, forcing the separation to decrease. Kepler's law then converts decreasing separation into increasing orbital and wave frequency. The chirp mass is the parameter combination that controls the leading frequency sweep, which is why gravitational-wave observations can measure it so accurately even before detailed modeling of the final merger.

**核心洞见**：引力波啁啾 = 能量平衡的可观测表现。四极辐射 → 带走轨道能量 → $r$ 减小 → Kepler 定律迫使 $\Omega$ 增大 → 频率上升。**啁啾质量 $\mathcal{M} = \mu^{3/5}M^{2/5}$** 是控制频率扫描的参数组合——这就是 LIGO 能精确测量它的原因。

---

### 2025 P6 — 共形标量场

> Conformal coupling is not an optional decorative term; it is the unique curvature correction that makes a massless scalar compatible with local Weyl rescalings in four dimensions. In the original curved-space field variable it appears as an effective mass $\xi R$, but after the conformal field redefinition it cancels the spurious curvature contribution generated by the scale factor. **This is the basic reason conformally coupled massless fields in conformally flat backgrounds behave like flat-space fields after rescaling.**

**核心洞见**：$\xi = 1/6$ 不是随手选的——它是四维下使无质量标量场局域 Weyl 不变唯一的曲率耦合。变换 $\chi = a\phi$ 后，曲率贡献恰好抵消标度因子带来的额外项，$\chi$ 的行为和 flat space 完全一样。**共形平坦背景 + 共形耦合 = 等效 flat space。**

---

## 五、规范场与重正化

### 2023 P3 — 规范势与辐射场

> Gauge theory separates redundant description from physical field strength. The potentials are not unique, but they make causality and wave propagation transparent once a gauge condition is imposed. In Lorenz gauge, Maxwell's equations become hyperbolic wave equations for $A^{\mu}$, while the fields $E$ and $B$ remain gauge-invariant derivatives. **The far-zone radiation field is governed by the source motion at the retarded time, reflecting propagation along the light cone.**

**核心洞见**：规范理论 = 冗余描述 + 物理场强分离。$A^\mu$ 不唯一，但选 Lorenz 规范后变成波动方程 → 因果性透明。远场辐射由**推迟时间**的源运动决定——信息沿光锥传播。

---

### 2023 P6 — $\phi^3$ 理论的单圈自能

> The calculation illustrates the logic of perturbative renormalization. Power counting identifies the possible local counterterms, and dimensional regularization computes the precise pole coefficient. In this $\phi^3$ two-point graph the ultraviolet divergence is logarithmic and momentum-independent at leading order, so it renormalizes the mass. **The nonlocal dependence on $p^2$ is physical after subtraction and cannot be removed by a local counterterm.**

**核心洞见**：重正化的逻辑链：功率计数 → 识别可能的局域抵消项 → 维数正规化提取极点系数。对数发散 + 动量无关 → 质量重正化。**减除后剩下的 $p^2$ 非局域依赖是物理的**，不能用局域抵消项消除。

---

### 2024 P6 — 赝标 Yukawa 理论的单圈发散

> Renormalizability means closure of the Lagrangian under quantum corrections. The role of the one-loop computation is not only to find pole coefficients but also to **verify that the divergent structures match operators already present in the action.** The pseudoscalar matrix $\gamma^5$ changes signs inside traces, but it does not alter the dimensional classification of possible counterterms. Thus the theory remains perturbatively renormalizable at one loop.

**核心洞见**：可重正化 = 拉氏量在量子修正下的**封闭性**。单圈计算不只要算极点系数，还要验证发散结构是否对应拉氏量中已有的算符。$\gamma^5$ 会翻转符号但不改变量纲分类。只要发散都可以被已有算符吸收 → 理论可重正化。

---

### 2022 P6 — $O(N)$ 标量模型的大 $N$ 计数

> Large-$N$ perturbation theory reorganizes Feynman diagrams by **index combinatorics** rather than by the number of loops alone. Keeping $g_0 = \lambda_0 N$ fixed makes the interaction weak at each vertex but compensates it through many internal components. The leading four-point function is therefore obtained from an infinite bubble-chain family. **This mechanism is the vector-model analogue of the planar-diagram selection familiar from matrix large-$N$ limits.**

**核心洞见**：大 $N$ 展开不按圈数组织，按**指标组合**组织。固定 $g_0 = \lambda_0 N$ → 每个顶角贡献 $1/N$，每个闭合指标环贡献 $N$。气泡链每加一个泡：多一个顶角 ($1/N$) 和多一个闭合环 ($N$) → 净阶不变 → 无穷气泡链都是同阶的。**这是矢量模型的"平面图选择"，对应矩阵大 $N$ 中的 't Hooft 极限。**

---

## 六、拓扑与全局效应

### 2023 P1 — 穿孔平面上的带电粒子

> This system separates local dynamics from global topology. Locally, the vector potential is pure gauge and the particle feels no magnetic force on the punctured plane. Globally, the removed origin prevents the gauge potential from being single-valued, so the angular momentum is shifted by a circulation term. **This is the classical counterpart of the Aharonov-Bohm mechanism: the field strength may vanish where the particle moves, while the topology of the configuration space still affects conserved quantities and phases.**

**核心洞见**：$B=0$ 处处成立（除了原点），但原点被挖掉了 → 平面不是单连通的。规范势 $A$ 在局部是纯规范，但全局有非平凡环量 $\oint A \cdot dr = 4\pi$。所以角动量被这个拓扑项平移了：$p_\varphi = r^2\dot{\varphi} + 2$。**这是 Aharonov-Bohm 效应的经典版本：场强为零 ≠ 物理效应为零。**

---

### 2024 P1 — 中心势轨道与 Bertrand 定理

> Central-force problems are governed by two equivalent reductions: an effective radial potential in time and Binet's equation in polar angle. Stability is the positivity of the second variation of the effective potential, while precession is encoded in the mismatch between radial and angular frequencies. **The exceptional Kepler and oscillator potentials are distinguished because their frequency ratios make all bounded orbits close, not merely selected near-circular ones.**

**核心洞见**：中心力问题有两种等价约化——有效势（时间域）和 Binet 方程（角度域）。稳定性 = $V_{\text{eff}}''(r_0) > 0$。进动 = $\Omega_r / \Omega_\varphi \notin \mathbb{Q}$。Kepler ($k=-1$) 和谐振子 ($k=2$) 之所以特殊，是因为**所有束缚轨道都闭合**，不仅是近圆轨道——频率比恰好满足封闭条件。这就是 **Bertrand 定理**的视角。

---

### 2024 P3 — 导体的趋肤深度

> A good conductor converts electromagnetic propagation into diffusion over a short skin depth. The perfect-conductor limit is controlled by the boundary condition $E_{\parallel} = 0$, while finite conductivity allows a small tangential electric field inside the metal to drive Ohmic current. The complex wave number records both attenuation and phase lag. **The skin depth is therefore the penetration length of a dissipative boundary layer, not merely a geometric cutoff.**

**核心洞见**：良导体内部，Maxwell 方程组从波动方程变成**扩散方程**。复波数 $k_c = (1+i)/\delta$ 同时编码衰减和相位滞后。趋肤深度 $\delta = \sqrt{2/\sigma\omega}$ 是一个**耗散边界层**的穿透长度。完美导体极限 ($\sigma \to \infty$)：$\delta \to 0$，$E_{\parallel}|_{\text{表面}} = 0$。

---

### 2025 P2 — 圆偏振波包的角动量

> A finite-width electromagnetic beam cannot be exactly transverse in the naive plane-wave sense; transversality forces a small longitudinal component controlled by transverse gradients. Once this consistency condition is imposed, circular polarization carries spin angular momentum whose ratio to energy is $1/\omega$. **The same result appears both classically, through field angular momentum, and quantum mechanically, through the helicity and energy of photons.**

**核心洞见**：有限宽度的光束不可能严格横场化——$\nabla \cdot \mathbf{E}=0$ 迫使存在一个 $O(1/k\sigma)$ 的纵向分量。但这对自旋-能量比 $L_z/U = 1/\omega$ 没有影响。经典场角动量 = 量子光子螺旋度的大占有数极限。**同一个 $1/\omega$，两种语言。**

---

## 七、方法论总结

### 复现的核心方法

| 方法           | 出现                            | 本质                        |
| ------------ | ----------------------------- | ------------------------- |
| **对称性约化**    | 2022 P3, P5; 2023 P5; 2024 P5 | 利用对称性将高维问题降为低维            |
| **代数结构识别**   | 2022 P2; 2023 P2              | 找到隐藏的李代数 → 在有限维表示里工作      |
| **有效势方法**    | 2024 P1; 2025 P1              | 将多维动力学约化为 1D 有效势中的平衡与稳定分析 |
| **相干态/平移算符** | 2024 P2; 2025 P3              | 线性外场 = 相空间平移 → 精确可解       |
| **重正化逻辑**    | 2022 P6; 2023 P6; 2024 P6     | 功率计数 → 识别抵消项 → 验证封闭性      |
| **规范/几何对偶**  | 2022 P4; 2023 P3; 2024 P5     | 同一个物理有两种互补的数学表示           |
| **普适性**      | 2023 P4; 2024 P4              | 微观细节在低能/临界点被"洗掉"          |
| **拓扑 vs 局域** | 2023 P1                       | 局部平凡 ≠ 全局平凡               |

### 贯穿始终的哲学

1. **不要满足于算出答案** — 追问"这个计算背后是什么结构？"
2. **寻找隐藏的对称性** — 对称性告诉你答案应该长什么样，然后只需确定系数
3. **选择合适的表示** — 同一个物理问题，换个变量/坐标/表象可能 trivial
4. **区分局部与全局** — $B=0$ 局部成立，不意味着没有物理效应
5. **微扰论是精确对角化的"影子"** — 当微扰结果恰好能用变量变换精确对角化时，说明你选的基不好

---

## 关联笔记

- [[Yau_数学物理_Solutions]] — 完整解答（含计算细节）
- [[Yau 量子力学]] — 个人量子力学解题笔记
- [[Yau 统计力学]] — 个人统计力学解题笔记
- [[统计物理知识点]] — 热统知识点梳理
- [[统计物理练习题]] — 热统练习题


---

# 2026 年出题方向预测分析

> 基于 2022-2025 四年 24 道数学物理题 + 各科分科考题的出题轨迹，系统分析各领域的"已覆盖"与"空白"，预测 2026 年可能的方向。

---

## 零、历年全景网格

### 数学物理个人赛（每年 6 题，6 个领域各 1 题）

|   年份   | 经典力学                    | 量子力学              | 电动力学         | 统计力学                  | 广义相对论           | 量子场论             |
| :----: | :---------------------- | :---------------- | :----------- | :-------------------- | :-------------- | :--------------- |
| **22** | —                       | 时间反演 (P1)         | —            | —                     | Killing 守恒 (P3) | 标度/共形流 (P5)      |
| **22** | —                       | Schwinger 表示 (P2) | —            | —                     | EF 视界 (P4)      | O(N) 大 N (P6)    |
| **23** | 穿孔平面/Aharonov-Bohm (P1) | 各向异性 HO 微扰 (P2)   | 规范势+辐射场 (P3) | 1D Bose/Fermi 热容 (P4) | S-dS 度规 (P5)    | φ³ 单圈自能 (P6)     |
| **24** | 中心势+Bertrand (P1)       | 受迫 HO+相干态 (P2)    | 趋肤深度 (P3)    | 平均场 Ising (P4)        | dS 静态度规 (P5)    | Yukawa 单圈发散 (P6) |
| **25** | 旋转圆环/叉式分岔 (P1)          | 电场中平移 HO (P3)     | 波包 OAM (P2)  | 三角 Ising (P4)         | 双黑洞 GW 啁啾 (P5)  | 共形标量场 (P6)       |

### 各科分科考题补充覆盖

| 科目 | 22 年 | 23 年 | 24 年 | 25 年 |
|:----:|:------|:------|:------|:------|
| **理论力学** | 空缺 | 磁场型拉氏量+Noether | 中心势全分析 | — |
| **电动力学** | — | 规范势+Green 函数 | 欧姆金属+趋肤 | 高斯光束+OAM |
| **统计力学** | — | — | 平均场 Ising | 三角 Ising |
| **量子力学** | 时间反演 | 各向异性 HO | 受迫 HO | — |
| **广义相对论** | Killing (×2) | Einstein+Λ | dS 静态度规 | — |
| **量子场论** | — | φ³ 单圈 | Yukawa 单圈 | 共形标量 |

---

## 一、核心发现：出题规律

### 规律 1：各领域内的"主题链"

每年不是随机选题，而是**围绕一个主题思想**在 6 个领域里各自出一题。

- **2022 主题：对称性** — 时间反演(反幺正)、Schwinger(李代数)、Killing(等距)、EF视界(零曲面)、标度(共形)、大N(指标对称)
- **2023 主题：计算技术** — 拓扑环量、简并微扰、推迟势、1D量子统计、度规求解、维数正规化
- **2024 主题：经典-量子对应** — Bertrand(有效势)、相干态(平移)、趋肤(耗散边界层)、平均场(Landau)、dS(嵌入vs坐标)、可重正化(封闭性)
- **2025 主题：现代物理前沿** — 分岔(序参量)、OAM(光自旋)、电场平移(相干态)、有限系统(涨落)、GW啁啾(能量平衡)、共形(外尔不变)

### 规律 2：量子力学的谐振子"执念"

四年 QM 全部是谐振子变体：
- 2022: 双谐振子 → Schwinger 表示
- 2023: 各向异性谐振子 → 简并微扰
- 2024: 受迫谐振子 → 相干态
- 2025: 电场平移谐振子 → 相干态另一面

**→ 2026 大概率继续谐振子变体**，但四年了，也该换个"对手"了。

### 规律 3：统计力学的 Ising 主题链

- 2023: 1D 量子统计（Bose vs Fermi 热容）
- 2024: 平均场 Ising → 临界指数
- 2025: 三角 Ising → 精确解 + 有限尺寸
- **→ 2026 可能：BEC 或量子气体，跳出 Ising 框架**

### 规律 4：QFT 的逐年递进

- 2022: 非微扰（对称性分析、大N）
- 2023: 微扰单圈（φ³，维数正规化）
- 2024: 微扰单圈（Yukawa，可重正化验证）
- 2025: 非微扰+几何（共形场论，Weyl 不变性）
- **→ 2026 可能：重整化群/β函数**（结合微扰计算和物理含义的下一步）

### 规律 5：GR 的清晰递进

- 2022: 对称性(Killing) + 视界结构(EF)
- 2023: 含宇宙学常数(S-dS)
- 2024: 正曲率空间(dS 静态)
- 2025: 引力辐射(GW 啁啾)
- **→ 2026 可能：Kerr(旋转) 或 FRW(膨胀) 或引力透镜(观测)**

---

## 二、各领域的"出题空白"（TODAY 最重要）

### 经典力学 — 未考核心主题

| 主题 | 重要性 | 出题概率 | 理由 |
|:-----|:------:|:------:|:-----|
| **刚体动力学**（Euler 方程、陀螺、进动） | ★★★★★ | 🔴🔴🔴🔴🔴 | 最大空白。四年从未涉及。Euler 角、对称陀螺、网球拍定理——都是经典的"数学物理" |
| **约束系统**（Lagrange 乘子、d'Alembert） | ★★★ | 🔴🔴🔴 | 可与刚体结合 |
| **Hamilton-Jacobi 理论** | ★★★★ | 🔴🔴🔴 | 作用角变量、旧量子论桥梁 |
| **混沌 / KAM 定理** | ★★★ | 🔴🔴 | 丘赛风格，连接数学 |
| **小振动与简正模** | ★★★ | 🔴🔴 | 23 年 QM 已经做过类似（各向异性 HO 对角化就是简正模） |

### 量子力学 — 未考核心主题

| 主题 | 重要性 | 出题概率 | 理由 |
|:-----|:------:|:------:|:-----|
| **Berry 相 / 几何相** | ★★★★★ | 🔴🔴🔴🔴🔴 | **最大空白！** 这是近 40 年最重要的理论发现之一，连接 QM ↔ 微分几何，丘赛气质拉满 |
| **WKB 近似 / 隧穿** | ★★★★★ | 🔴🔴🔴🔴 | 经典方法，从未出现 |
| **密度矩阵 / 纠缠熵** | ★★★★ | 🔴🔴🔴🔴 | 量子信息时代的基础概念 |
| **Landau 能级** | ★★★★★ | 🔴🔴🔴🔴 | QM + EM 完美结合，De Haas-van Alphen 等效应 |
| **自旋动力学**（Rabi、Larmor、磁共振） | ★★★★ | 🔴🔴🔴 | 时间反演 → 自旋体系 → 自然延展 |
| **散射理论**（分波法、Born 近似） | ★★★★ | 🔴🔴🔴 | 经典但未考 |
| **路径积分** | ★★★★★ | 🔴🔴 | 可以出但可能太技术化 |
| **EPR / Bell 不等式** | ★★★★ | 🔴🔴 | 基础量子信息 |

### 电动力学 — 未考核心主题

| 主题 | 重要性 | 出题概率 | 理由 |
|:-----|:------:|:------:|:-----|
| **波导与谐振腔** | ★★★★★ | 🔴🔴🔴🔴 | 完美的边界值问题，数学丰富（Bessel 函数） |
| **Cherenkov 辐射** | ★★★★ | 🔴🔴🔴 | 相对论+EM，简洁优美 |
| **同步辐射** | ★★★ | 🔴🔴 | 较复杂 |
| **多极辐射** | ★★★★★ | 🔴🔴🔴🔴 | 经典中的经典 |
| **介质中的 Maxwell 方程**（色散、Kramers-Kronig） | ★★★★ | 🔴🔴🔴 | 24 年趋肤是介质，可延续 |
| **等离子体** | ★★★ | 🔴🔴 | 太专 |
| **衍射理论** | ★★★ | 🔴🔴 | 光学偏多 |

### 统计力学 — 未考核心主题

| 主题 | 重要性 | 出题概率 | 理由 |
|:-----|:------:|:------:|:-----|
| **Bose-Einstein 凝聚** | ★★★★★ | 🔴🔴🔴🔴🔴 | **最大空白！** 诺贝尔奖级发现，丰富数学 |
| **Debye 模型 / 固体比热** | ★★★★★ | 🔴🔴🔴🔴 | 经典，连接 QFT（声子） |
| **van der Waals / 液气相变** | ★★★★ | 🔴🔴🔴🔴 | 平均场 + Maxwell 构造 |
| **涨落-耗散定理** | ★★★★★ | 🔴🔴🔴 | 连接统计 ↔ 线性响应 |
| **Brown 运动 / Langevin** | ★★★ | 🔴🔴 | 随机过程 |
| **Fermi 气体简并 / 金属电子** | ★★★★ | 🔴🔴🔴 | 23 年有 1D，可以升维 |
| **超流 / 元激发** | ★★★ | 🔴🔴 | 太专 |

### 广义相对论 — 未考核心主题

| 主题 | 重要性 | 出题概率 | 理由 |
|:-----|:------:|:------:|:-----|
| **Kerr 度规 / 参考系拖曳** | ★★★★★ | 🔴🔴🔴🔴🔴 | **最大空白。** Schwarzschild → S-dS → dS → Kerr 是自然递进 |
| **引力透镜** | ★★★★ | 🔴🔴🔴🔴 | 观测天体物理核心 |
| **FRW 宇宙学 / 红移** | ★★★★★ | 🔴🔴🔴🔴 | 基础宇宙学从未出现 |
| **Penrose 过程 / BH 热力学** | ★★★★ | 🔴🔴🔴 | GR + 统计跨界 |
| **线性化引力** | ★★★ | 🔴🔴 | 25 年 GW 已经涉及 |
| **能量条件 / 奇点定理** | ★★★ | 🔴🔴 | 偏数学 |

### 量子场论 — 未考核心主题

| 主题 | 重要性 | 出题概率 | 理由 |
|:-----|:------:|:------:|:-----|
| **重整化群 / β 函数** | ★★★★★ | 🔴🔴🔴🔴🔴 | **最大空白。** 单圈算完了，该问物理含义了 |
| **自发对称破缺 / Goldstone** | ★★★★★ | 🔴🔴🔴🔴 | 现代 QFT 核心，从未出现 |
| **轴反常（显式计算）** | ★★★★ | 🔴🔴🔴🔴 | 三角图 + 拓扑 |
| **Yang-Mills / 非阿贝尔** | ★★★★★ | 🔴🔴🔴 | 已考 O(N) 大 N，可转非阿贝尔 |
| **有效势 / Coleman-Weinberg** | ★★★★ | 🔴🔴🔴 | 连接 SSB + 辐射修正 |
| **LSZ 约化 / S 矩阵** | ★★★★ | 🔴🔴 | 散射形式理论 |
| **瞬子 / 孤子** | ★★★ | 🔴🔴 | 非微扰效应 |
| **红外发散 / Bloch-Nordsieck** | ★★★ | 🔴 | 太专 |

---

## 三、2026 年核心预测

### Tier 1（概率最高 🔴🔴🔴🔴🔴）—— 最大空白 + 丘赛气质

|      领域       | 预测题               | 核心思路                                                                                                                                        |
| :-----------: | :---------------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
|    **QM**     | **Berry 相**       | 绝热演化中的几何相位。给一个含时 Hamiltonian $H(\mathbf{R}(t))$，计算 Berry 联络 $A_n = i\langle n\nabla_Rn\rangle$ 和 Berry 曲率，然后讨论参数空间的拓扑——这跟 2023 年的"穿孔平面"一脉相承 |
|    **GR**     | **Kerr 度规或引力透镜**  | Kerr：给 Boyer-Lindquist 形式，计算参考系拖曳角速度 $\omega = 2Mar/(r^2+a^2)^2$；透镜：给 Schwarzschild，计算偏转角 $\Delta\phi = 4GM/bc^2$                           |
| **Stat Mech** | **BEC**           | 三维自由 Bose 气体，计算临界温度 $T_c = \frac{2\pi\hbar^2}{mk_B} (n/\zeta(3/2))^{2/3}$，凝聚份额，比热不连续性                                                       |
|    **QFT**    | **重整化群 / β 函数**   | 计算 Callan-Symanzik 方程或直接在 $\phi^4$ 中导出 $\beta(\lambda) = \frac{3\lambda^2}{16\pi^2}$，讨论渐近自由 vs Landau 极点                                    |
|    **CM**     | **刚体陀螺**          | Euler 方程 $\dot{\mathbf{L}} + \boldsymbol{\omega}\times\mathbf{L} = 0$，对称陀螺的规则进动，网球拍定理（中间轴不稳定）                                               |
|    **ED**     | **波导或 Cherenkov** | 波导：TE/TM 模，截止频率，色散关系；Cherenkov：$\cos\theta = c/nv$，Fourier 变换算辐射谱                                                                           |


### Tier 2（概率高 🔴🔴🔴🔴）—— 重要空白，可能穿插

| 领域 | 预测题 | 理由 |
|:----:|:------|:-----|
| **QM** | **Landau 能级** | 2025 ED 波包 OAM → 光有角动量 → 电子在磁场中的角动量 → Landau 能级，逻辑串联 |
| **QM** | **WKB + 隧穿** | 经典方法从未出现，α 衰变、双势阱分裂 |
| **ED** | **多极辐射** | 电偶极+磁偶极+电四极，给出了源分布求辐射场 |
| **GR** | **FRW 宇宙学** | 给 Robertson-Walker 度规，推导 Friedmann 方程 |
| **QFT** | **自发对称破缺** | 给复标量场 Mexican hat，计算 Goldstone 模和质量模 |
| **CM** | **约束系统** | 绳上珠子、Atwood 机、Lagrange 乘子 |

### Tier 3（值得准备 🔴🔴🔴）—— 暗马

| 领域 | 预测题 | 理由 |
|:----:|:------|:-----|
| **QM** | **密度矩阵 / 纠缠** | 量子信息时代的必备，但竞赛可能觉得"太新" |
| **QFT** | **轴反常显式计算** | 三角图 $AVV$，$\partial_\mu j^\mu_5 = \frac{e^2}{16\pi^2}F_{\mu\nu}\tilde{F}^{\mu\nu}$ |
| **Stat Mech** | **Debye 模型** | $C_V \propto T^3$ 的推导，经典的"普适性"例子 |
| **GR** | **Penrose 过程** | 黑洞能量提取，结合热力学 |
| **ED** | **Kramers-Kronig** | 因果性 → 色散关系，美而简洁 |
| **CM** | **Noether 定理变体** | 23 年已考过基础版，可能出高阶 Noether 或非平凡边界条件 |

---

## 四、2026 年的可能"年度主题"

| 主题 | 可能覆盖 | 动机 |
|:-----|:--------|:-----|
| **几何与拓扑** | Berry 相 (QM) + 引力透镜 (GR) + 轴反常 (QFT) | 延续 2025 共形场论的几何转向 |
| **量子物质** | BEC (Stat) + Landau 能级 (QM) + 重整化群 (QFT) | 量子多体效应成为主线 |
| **观测物理** | 引力透镜 (GR) + Cherenkov (ED) + Debye (Stat) | 理论与观测的桥梁 |
| **动力学与稳性** | 刚体陀螺 (CM) + 自发破缺 (QFT) + 分岔续集 (CM) | 稳定性主题的深化 |

我的判断：**2026 年最有可能是"几何与拓扑"主题**——这与丘成桐本人的数学品味一致，也与 2023 (穿孔平面)、2024 (dS 嵌入)、2025 (共形场论、GW) 的轨迹一脉相承。

---

## 五、你的备考策略建议

### 必须补的缺口（按优先级）

1. **Berry 相 / 绝热定理** — QM 四年全是 HO，今年大概率换方向，Berry 相是头号候选
2. **BEC / Bose 气体** — 统计力学两年 Ising，必须跳出
3. **Kerr 度规 / 参考系拖曳** — GR 的球对称已经出透了
4. **重整化群方程** — 单圈算了两遍，该问 RG 了
5. **刚体动力学** — 经典力学四年没碰过这个方向
6. **波导 / 谐振腔** — ED 的边界值问题从未出过

### 保持熟练的方向

- 谐振子（所有变体）——仍然可能出现作为某个问题的"基础设施"
- 微扰论（简并+非简并）
- Killing 矢量 / 守恒量
- 维数正规化
- 产生湮灭算符形式

### 建议新开的学习主题

1. 微分几何与 QM 的交叉（Berry 联络、曲率、Chern 数）
2. 黑洞热力学四定律（温度、熵、面积定理）
3. 重整化群的物理图像（Kadanoff 块自旋、Wilson 递推）
4. Goldstone 定理的推导和例子
5. 波导模式理论的完整推导

---




---

# 附录：题库备战充分度审计

> 评估日期：2026-05-14。基于对全 Vault 120+ 个知识文件的全面扫描，对丘赛六个领域的「已覆盖 vs 空白」做系统性审计。

---

## 审计方法论

对六个领域各选取 ~15 个丘赛级别的核心主题，按四个维度评分：

| 标记 | 含义 |
|:----:|:-----|
| ✅ | 有真题练习 + 知识点笔记 + 深度理解 |
| 🔶 | 有真题或笔记，但不够系统 |
| ❌ | 几乎空白 |

---

## 一、量子力学

| 主题 | 状态 | 证据 |
|:-----|:----:|:-----|
| 时间反演/反幺正 | ✅ | Yau 22 P1, 曾谨言, Solutions |
| 谐振子（所有变体） | ✅ | 四年 Yau 全有 + 相干态题型 + 费米相干态 |
| Schwinger 表示 / su(2) | ✅ | Yau 22 P2, Solutions |
| 简并微扰论 | ✅ | Yau 23 P2 + 定态微扰论练习题 + 曾谨言 |
| 非简并微扰论 | ✅ | 仿丘赛题 #1 + 曾谨言定态微扰计算 |
| δ 势 / 边界条件 | ✅ | 曾谨言 δ 势 + 仿丘赛题 #1 |
| WKB / 隧穿 | 🔶 | 工具箱有 WKB-Airy 重整化笔记，但无真题 |
| SUSY QM | ✅ | 仿丘赛题 #1 + 超对称性于固有能量简并 |
| 自旋 / Pauli 矩阵 | ✅ | 曾谨言自旋空间 + 泡利矩阵 |
| 角动量理论 / CG 系数 | ✅ | CG系数笔记 + Wigner-Eckart + 角动量投影定理 |
| Hellmann-Feynman | ✅ | 曾谨言 Hellmann 定理 |
| Aharonov-Bohm | ✅ | 仿丘赛题 #10 |
| **Berry 相 / 几何相** | ❌ | **全 Vault 零覆盖！最大空白** |
| **Landau 能级** | ❌ | 无任何笔记 |
| **密度矩阵 / 纠缠** | ❌ | 无任何笔记 |
| 散射理论 | 🔶 | 感悟/随笔有散射理论笔记，无计算题 |

**QM 评分：7.5/10** — 谐振子方向强到溢出，但 Berry 相和 Landau 能级是致命空白。

---

## 二、量子场论

| 主题 | 状态 | 证据 |
|:-----|:----:|:-----|
| 标度/共形对称性 | ✅ | Yau 22 P5 + 25 P6 + CFT 读书笔记 (3 本) |
| φ⁴ 单圈重整化 | ✅ | 仿丘赛题 #2 (β 函数全解) |
| φ³ 单圈自能 | ✅ | Yau 23 P6 |
| 维数正规化 | ✅ | 维数正规化笔记 + Peskin Ch 2-5 |
| Pauli-Villars 正规化 | ✅ | 泡利-维拉斯正规化笔记 |
| BPHZ 重整化 | ✅ | BPHZ重整化笔记 + 在壳重整化 |
| 重整化群 / β 函数 | ✅ | 重整化群笔记 + 仿丘赛题 #2 完整解 |
| 大 N 展开 | ✅ | Yau 22 P6 |
| Yukawa 理论 | ✅ | Yau 24 P6 |
| QED 真空极化 | ✅ | 仿丘赛题 #3 + QED 导论 + 光锥坐标 in QED |
| 规范理论 (U(1)/SU(2)/SU(3)) | ✅ | 各规范群笔记 + Yang-Mills 笔记 + Faddeev-Popov |
| 对称破缺 / Goldstone | ✅ | Goldstone定理笔记 + Higgs 机制 |
| 费曼规则/对称因子 | ✅ | 如何直接读出费曼规则 + 费曼图对称数 |
| 弯曲时空 QFT | ✅ | 弯曲时空下的QFT + 膨胀宇宙粒子产生 + 做题总结 |
| 共形场论 (Virasoro) | ✅ | Francesoe CFT 读书笔记 (5 篇) |
| 庞加莱群 / 表示论 | ✅ | 庞加莱群笔记 |
| 路径积分 | 🔶 | 感悟中有涉及但无系统习题 |
| LSZ / S 矩阵 | 🔶 | 散射理论笔记，无具体计算 |
| **轴反常（显式计算）** | 🔶 | 感悟涉及但无具体三角图计算 |
| 瞬子 / 孤子 | 🔶 | 读书笔记有但无练习 |

**QFT 评分：9/10** — Vault 中最强的领域。从单圈计算到 CFT，覆盖面惊人。唯一可加强的是反常的显式计算和路径积分技术。

---

## 三、广义相对论

| 主题 | 状态 | 证据 |
|:-----|:----:|:-----|
| Killing 矢量 / 守恒量 | ✅ | Yau 22 P3, 23 P5, 24 P5 |
| Schwarzschild 度规 | ✅ | GR 习题册 Ch 1-10 |
| Eddington-Finkelstein | ✅ | Yau 22 P4 |
| S-dS / 宇宙学常数 | ✅ | Yau 23 P5 |
| de Sitter 空间 | ✅ | Yau 24 P5 + de Sitter 笔记 |
| 引力波啁啾 | ✅ | Yau 25 P5 + 仿丘赛题 #11 |
| AdS-Schwarzschild | ✅ | 仿丘赛题 #12 (Killing 视界+表面引力) |
| 张量分析 / 微分几何 | ✅ | GR 习题册 Ch 1 + Arnold 读书笔记 + 联络-矩阵算法 |
| 联络与曲率计算 | ✅ | 联络与曲率计算技巧 + 黎曼张量-常曲率算法 |
| 爱因斯坦方程求解 | ✅ | 静态球对称度规 + S-dS 通解 |
| Cartan 结构方程 | ✅ | Cartan 结构方程笔记 |
| 常曲率空间 | ✅ | 常曲率算法 |
| **Kerr 度规 / 拖曳** | ❌ | **全 Vault 零覆盖！第二大空白** |
| **FRW 宇宙学** | 🔶 | 粒子产生笔记涉及膨胀宇宙，但无 Friedmann 方程推导 |
| **引力透镜** | ❌ | 零覆盖 |

**GR 评分：7.5/10** — 微分几何功底极强（Arnold + Nakahara + Cartan），球对称度规家族全覆盖。但 Kerr 和 FRW 这两个核心方向完全空白。

---

## 四、统计力学

| 主题 | 状态 | 证据 |
|:-----|:----:|:-----|
| 配分函数 / 自由能 | ✅ | Pathira Ch 1-7 + 汪志诚系综 + 统计物理知识点 |
| Ising 模型（精确解） | ✅ | Yau 25 P4 (三角) + 仿丘赛题 #4, #5 |
| 平均场 / Landau 理论 | ✅ | Yau 24 P4 |
| 临界指数 | ✅ | Yau 24 P4 + 仿丘赛题 #4 |
| 转移矩阵 | ✅ | 伊辛模型方法总结 + 1D Ising 自编 |
| 1D 量子统计 | ✅ | Yau 23 P4 (Bose/Fermi 热容) |
| Bethe 格点 | ✅ | 仿丘赛题 #5 |
| 系综理论 | ✅ | Pathira 三种系综笔记 + 汪志诚 |
| 鞍点法 | ✅ | 鞍点法推导分布 |
| 涨落 | ✅ | 统计物理知识点 1.3 |
| **BEC / Bose 气体** | 🔶 | Pathria 量子统计学笔记，但无 BEC 专项练习 |
| **Debye 模型 / 固体比热** | ❌ | 零覆盖 |
| **van der Waals / 液气相变** | ❌ | 零覆盖 |
| **涨落-耗散定理** | ❌ | 零覆盖 |
| Fermi 气体简并 | 🔶 | Pathria 量子统计学有涉及，无专项 |
| 超流 / 超导基础 | ❌ | 零覆盖（但有超对称性于固有能量简并，可算跨界） |

**统计力学评分：5.5/10** — Vault 中最薄弱领域。Ising 模型方向极强（从 1D 到三角到 Bethe 格点到平均场），但其他方向几乎全部空白。BEC、Debye、van der Waals 是最紧迫的三个缺口。

---

## 五、电动力学

| 主题 | 状态 | 证据 |
|:-----|:----:|:-----|
| Maxwell 方程 / 规范势 | ✅ | 电动力学知识点 + Yau 23 P3 |
| 规范变换 | ✅ | 电动力学知识点 + Liu Chuan Ch 1-8 |
| Lorentz 规范 / 波动方程 | ✅ | Yau 23 P3 |
| Green 函数 / 推迟势 | ✅ | Yau 23 P3 |
| 导体 / 趋肤深度 | ✅ | Yau 24 P3 |
| 波包 / 高斯光束 / OAM | ✅ | Yau 25 P2 |
| 偶极辐射 | ✅ | 工具箱偶极辐射总结 |
| Dirac 磁单极 | ✅ | 仿丘赛题 #9 + 拓扑量子化 |
| AB 效应 | ✅ | 仿丘赛题 #10 |
| 电子在强激光场 | ✅ | 仿丘赛题 #8 |
| Jackson 习题 | ✅ | Jackson Ch 1-3 |
| 偏心导体球 | ✅ | 独立笔记 |
| 刘川电动全 8 章 | ✅ | 系统练习 |
| **波导 / 谐振腔** | ❌ | **全 Vault 零覆盖！** |
| **Cherenkov 辐射** | ❌ | 零覆盖 |
| 多极辐射 | 🔶 | 偶极有总结，电四极/磁偶极无 |
| 介质色散 / Kramers-Kronig | ❌ | 零覆盖 |
| 同步辐射 | 🔶 | 仿丘赛题 #8 部分涉及 |

**ED 评分：7.5/10** — 理论方面（规范场、磁单极、AB 效应、拓扑）极强。短板在工程物理方向：波导、谐振腔、色散。但丘赛 ED 偏理论，波导是最大的实际缺口。

---

## 六、经典力学

| 主题 | 状态 | 证据 |
|:-----|:----:|:-----|
| 中心势 / Bertrand | ✅ | Yau 24 P1 + 理力基础计算习题册 |
| 有效势 / 稳定性 | ✅ | Yau 24 P1 |
| Binet 方程 | ✅ | Yau 24 P1 |
| Noether 定理 / 守恒量 | ✅ | Yau 23 (理力) |
| 拉格朗日力学 | ✅ | 东京大学理力 + Arnold 读书 |
| 哈密顿力学 | ✅ | 理论力学基础计算习题册 |
| 辛几何 | ✅ | Arnold 辛流形笔记 |
| 约束系统（滚球） | ✅ | 仿丘赛题 #6 (球的无滑滚动) |
| Kapitza 摆 | ✅ | 仿丘赛题 #7 (振荡悬挂点) |
| 非线性振动 | ✅ | 非线性振子周期修正 + 时间重整化 |
| 微分形式 | ✅ | Arnold 微分形式笔记 |
| **刚体动力学（Euler/陀螺）** | ❌ | **全 Vault 零覆盖！最大经典力学空白** |
| **Hamilton-Jacobi / 作用角变量** | ❌ | 零覆盖 |
| 混沌 / KAM | ❌ | 零覆盖（但 Arnold 读书可能涉及） |
| 小振动 / 简正模 | 🔶 | 非线性振子涉及但不够系统 |

**经典力学评分：7/10** — 分析力学方向极强（Arnold 读书三篇 + 辛几何），但刚体动力学、H-J 理论是两个显著空白。

---

## 七、全 Vault 统计

```
├── Atlas/
│   ├── 写题/刷的题/
│   │   ├── Yau/          (11 files) — 真题 + 知识点
│   │   ├── 自编/         (12 files) — 自编习题册 + 模拟题
│   │   ├── 曾谨言/       (11 files) — QM 专题练习
│   │   ├── 刘川 电动/    (8 files)  — ED 系统练习
│   │   ├── Pathira/      (7 files)  — 统计力学练习
│   │   ├── Jackson/      (3 files)  — ED 经典教材
│   │   ├── Peskin/       (4 files)  — QFT 经典教材
│   │   ├── 东京大学/     (2 files)  — 理力 + 热统
│   │   └── 中科大/       (2 files)  — ED + QM
│   │
│   ├── 工具箱/           (15 files) — 方法总结
│   ├── 笔记/感悟/        (16 files) — 深层理解
│   ├── 笔记/随笔/        (34 files) — 专题笔记
│   └── 读书/             (22 files) — Arnold, CFT, Nakahara, Pathira, 场论几何
│
├── 仿丘赛题.md           (12 problems, 151KB)
└── 固体物理的数学原理.md  (79KB)
```

## 八、综合评估

### 各领域评分

| 领域 | 得分 | 定性 |
|:-----|:----:|:-----|
| 量子场论 | 9.0 | **最强领域** — 从单圈到 CFT 到弯曲时空全覆盖 |
| 量子力学 | 7.5 | 谐振子极强，Berry/Landau 空白 |
| 广义相对论 | 7.5 | 微分几何功力深，缺 Kerr/FRW |
| 电动力学 | 7.5 | 规范理论强，缺波导/谐振腔 |
| 经典力学 | 7.0 | 分析力学强，缺刚体/H-J |
| 统计力学 | 5.5 | **最薄弱** — Ising 一枝独秀，其余大面积空白 |
| **综合** | **7.3** | 整体准备充分，但统计力学拖后腿 |

### 核心优势

1. **理论深度惊人** — Arnold 的微分几何、Francesoe 的 CFT、Nakahara 的同调群、场论的构造与几何……你的读书广度和深度远超一般丘赛选手
2. **自编题质量极高** — 仿丘赛题 12 道完全是丘赛风格，多段递进、含 Higher Viewpoint，"仿"得非常到位
3. **QFT 是杀手锏** — 这个领域的准备程度几乎无可挑剔
4. **工具链齐全** — 从维数正规化到 Cartan 结构方程，工具箱覆盖了几乎所有"怎么算"
5. **知识体系互联** — Higher Viewpoints 思想录把 24 道题按主题思想串联，说明你在做"理解"而不只是"刷题"

### 核心风险

| 优先级 | 缺口 | 风险 | 建议 |
|:------:|:-----|:-----|:-----|
| 🔴🔴🔴 | **统计力学大面积空白** | 2026 如果出 BEC/Debye/van der Waals，几乎没有准备 | 最紧迫！建议补 Pathira BEC 章+自编 5 题 |
| 🔴🔴🔴 | **Berry 相零覆盖** | QM 四年考了 HO，今年换方向的概率极高 | 补 Berry 相推导 + 自旋 1/2 绝热演化全套 |
| 🔴🔴 | **刚体动力学空白** | 经典力学大概率换方向 | 补 Euler 方程 → 对称陀螺 → 网球拍定理 |
| 🔴🔴 | **Kerr/FRW 空白** | GR 球对称出透了 | 补 Boyer-Lindquist + Friedmann 方程推导 |
| 🔴 | **波导/谐振腔空白** | ED 规范理论出透了 | 补矩形波导 TE/TM 模 |
| 🔴 | **SSB 无练习** | 有 Goldstone 笔记但无计算题 | 补 Mexican hat → 质量谱完整计算 |

### 总体判断

> **准备充分度：7.3/10**

你已经建立了一个远超一般竞赛选手的知识体系。QFT 和 GR 的理论深度尤其突出。最大的问题不是"不会算"，而是统计力学和几个关键空白方向可能在考场成为"没想到会考这个"的意外。

如果能在考前两个月集中补上统计力学（BEC + Debye）和 Berry 相，综合准备度可以提升到 **8.5/10**。



---

# 附录二：晋级策略分析

> 2026-05-14。从"做对 3-4 题进决赛"这一硬约束出发，做博弈论式的策略规划。

---

## 一、游戏规则

- 数学物理个人赛每年 **6 题**，6 个领域各 1 题
- 进决赛大致需要 **做对 3-4 题**
- 每题有若干小问 (a)-(f)，不要求全做完，**核心子问题做对即得分**

这意味着：你不需要六个领域全精通。你需要 **4 个"稳"的领域 + 2 个"能蹭分"的领域**。

---

## 二、你的"稳"与"不稳"

基于 Vault 审计，给每个领域的**确定性**打分（不是你的绝对水平，而是"无论出什么题都能做对核心子问"的概率）：

| 领域 | 绝对水平 | 确定性 | 风险项 |
|:-----|:------:|:------:|:------|
| **QFT** | 9.0 | 🟢🟢🟢🟢🟢 95% | 几乎无风险 |
| **QM** | 7.5 | 🟡🟡🟡 65% | **Berry 相** = 零准备 |
| **GR** | 7.5 | 🟡🟡🟡 65% | **Kerr 度规** = 零准备 |
| **ED** | 7.5 | 🟢🟢🟢🟢 80% | 波导/谐振腔（概率较低） |
| **CM** | 7.0 | 🟡🟡🟡 60% | **刚体动力学** = 零准备 |
| **Stat Mech** | 5.5 | 🔴🔴 30% | BEC/Debye/vdW 大面积空白 |

### 当前最可能的得分情景

| 情景 | QFT | QM | GR | ED | CM | Stat Mech | 总分 | 晋级？ |
|:-----|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 乐观（全出强项） | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | 5 | ✅ |
| 中性（各出一个弱项） | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | 4 | ✅ |
| **中性偏不利** | ✅ | ❌ | ✅ | ✅ | ❌ | ❌ | **3** | ⚠️ |
| 悲观（QM+GR 同时暴雷） | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | **2** | ❌ |

**关键发现**：你的风险不是均匀分布的。QFT 和 ED 是两块压舱石，Stat Mech 基本放弃。胜负手在 **QM 和 GR 是否暴雷**——QM 出 Berry 相、GR 出 Kerr，同时暴雷的概率不低，因为这两个恰好是各自领域最可能的新方向。

---

## 三、最优策略：集中火力保 4

### 核心思想

> **不要在弱项上花时间补到满分，把强项的不确定性消除。**

你现在的情况是：
- 5.5 → 7.0（Stat Mech）需要 50+ 小时
- 7.5 → 9.0（QM/GR）只需要 **把两个致命空白填上**，约 15 小时

同样的时间投入，补弱项的边际收益远低于消除强项的风险。

### 策略：4+2 格局

```
████████████████████  QFT    — 稳（95%）
██████████████░░░░░░  ED     — 稳（80%）
████████████░░░░░░░  QM     — 目标：消除 Berry 相风险 → 85%
████████████░░░░░░░  GR     — 目标：消除 Kerr 风险 → 85%
██████░░░░░░░░░░░░░  CM     — 维持现状 + 补刚体基础（60% → 70%）
███░░░░░░░░░░░░░░░░  StatM  — 放弃深度，只保"如果出 Ising 能拿分"
```

目标场景变为：

| 情景 | QFT | QM | GR | ED | CM | Stat | 总分 |
|:-----|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 乐观 | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | **5** |
| 中性 | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | **4** |
| 悲观 | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | **3** |
| 极端 | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | 不太可能 |

**补上 QM 和 GR 的两个致命空白后，即使在悲观情景下也能保 3。**

---

## 四、精准打击清单（按优先级）

### 第一优先级：消除致命空白（~15 小时）

| 主题 | 时间 | 具体内容 | 目标 |
|:-----|:----:|:-----|:-----|
| **Berry 相** | 8h | ① 绝热定理回顾 ② Berry 联络 $A_n = i\langle n\|\nabla_R\|n\rangle$ ③ 自旋 1/2 在缓变磁场中的 Berry 曲率 ④ 参数空间拓扑（Chern 数）⑤ 自编 3 道全流程题 | QM 确定性 65%→85% |
| **Kerr 度规** | 5h | ① Boyer-Lindquist 度规 ② 参考系拖曳角速度 $\omega(r,\theta)$ ③ 能层/静界 ④ Killing 视界表面引力 ⑤ 与 Schwarzschild 的退化关系 | GR 确定性 65%→85% |
| **刚体 Euler 方程** | 2h | ① Euler 方程推导 ② 对称陀螺进动 ③ 网球拍定理（至少知道存在） | CM 确定性 60%→70% |

### 第二优先级：统计力学止损（~10 小时）

| 主题 | 时间 | 具体内容 | 目标 |
|:-----|:----:|:-----|:-----|
| **BEC** | 4h | ① 3D Bose 气体态密度 ② 临界温度 $T_c$ 推导 ③ 凝聚份额 $N_0/N = 1-(T/T_c)^{3/2}$ ④ 比热不连续性 | 从 0 → 能应对 BEC 基础题 |
| **Debye 模型** | 2h | ① 声子态密度 $g(\omega)\propto\omega^2$ ② $C_V \propto T^3$ 推导 ③ Einstein 模型对比 | 从 0 → 能应对固体比热题 |
| **Ising 保持熟练** | 2h | ① 回顾三角 Ising + 平均场 + 转移矩阵 ② 确保如果出 Ising 变体不失分 | 维持现有水平 |
| **配分函数速算** | 2h | ① 各种系综的 $Z$ 快速计算技巧 ② 从 $Z$ 到热力学量的链式推导 | 通用计算能力 |

### 第三优先级（如果有余力）

| 主题 | 时间 | 理由 |
|:-----|:----:|:-----|
| FRW 宇宙学 | 3h | 与 dS 有联系，不是从零开始 |
| 多极辐射 | 2h | ED 辐射方向自然延伸 |
| 波导基础 | 2h | 虽概率低，但矩形波导不难 |
| 轴反常三角图 | 3h | 如果出 QFT 的新方向 |

---

## 五、考前 15 小时的ROI 分析

```
投入 15 小时：
├── Berry 相 (8h)  → QM 确定性 +20%
├── Kerr 度规 (5h) → GR 确定性 +20%
└── 刚体基础 (2h) → CM 确定性 +10%

结果：
├── 4 题把握：从"需要运气"→"大概率"
├── 最坏情景：从 2 题 → 3 题（可能压线晋级）
└── 统计力学仍然弱，但不影响大局
```

**同样的 15 小时如果用来补统计力学（BEC 8h + Debye 5h + vdW 2h）：**
- Stat Mech 确定性 30% → 55%（仍然不够稳）
- QM 和 GR 风险未消除 → 悲观情景仍是 2 题
- **净效果远不如"消除强项风险"**

---

## 六、心态层面的实话

1. **你不需要做对所有 6 题。** 丘赛数学物理的晋级线从来没有要求全对。3-4 题就够。

2. **QFT 是你的定心丸。** 有这个 95% 确定性的领域垫底，你已经比 90% 的选手多了一个"白送"的题。大多数人六个领域均匀弱，你有一个领域压倒性强。

3. **统计学上，QFT + QM + GR + ED 同时暴雷的概率极低。** 即使每个有 15% 的失败概率，四个同时失败的概率是 $0.15^4 \approx 0.05\%$。关键是让 QM 和 GR 的失败概率从 35% 降到 15%。

4. **丘赛的 6 题不是"每道都要独立攻克"**——每道题有 (a)-(f) 多个子问，前面的子问题通常是在给你搭梯子。你不需要做到 (f)，做到 (c) 或 (d) 往往已经拿到大部分分数。

5. **你现在的水平，如果 2025 年的卷子放在你面前**：
   - P1 (旋转圆环/分岔)：CM，你的 CM 水平 OK → ✅
   - P2 (波包 OAM)：ED，你的 ED 有波包题 → ✅
   - P3 (电场平移 HO)：QM，你的 HO 极强 → ✅
   - P4 (三角 Ising)：Stat Mech，你做过 → ✅
   - P5 (GW 啁啾)：GR，你做过仿丘赛题 #11 → ✅
   - P6 (共形标量)：QFT，你的 CFT 极强 → ✅
   
   **你能做对 6 题中的至少 5 题。** 所以问题不在"你不够强"，而在"2026 年的方向可能恰好绕过你的强项"。

---

## 七、结论

> **你要的不是"变得更强"，而是"消除强项中的盲点"。**

当前策略清晰：
1. **Berry 相**和**Kerr 度规**是两个必须立刻补的盲点（共计 ~13h）
2. 统计力学只止损不追求深度（BEC + Debye 基础，~8h）
3. QFT 和 ED 保持熟练，不需要额外投入

投入 20-25 小时精准打击 → 4 题把握从"需要运气"变为"高度确定" → 晋级概率从 ~60% 提升到 ~85%。
