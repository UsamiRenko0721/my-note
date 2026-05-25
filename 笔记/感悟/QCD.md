---
up:
  - "[[感悟]]"
  - 
related:
date: 2026-01-31
---
# 1. SU(3) 群与颜色对称性

## 1.1 历史

$SU(3)$ 的发现使用在历史上是基于对重子相互作用的研究，一开始是发现了质子和中子的质量与作用强度都相近，于是假设为核子的双重态 (当然所谓的 β 衰变就是关于核子双重态间的作用得一个例子，使用 $SU(2)$ 描述)，而传播作用的玻色子 $\pi$ 是三重态 $\pi^{\pm},\pi^{0}$ 它们带有荷

为了解释核力与电荷无关 (中子-中子散射是存在的) 的现象，引入了[[同位旋]] $I$ 的概念，显然它是 $SU(2)$ 的代数。在之后的实验中发现了更多种类的重子，于是意识到只有同位旋 $SU(2)$ 是不够的，Gell-Mann 和 Nishijima 等人发现这些新粒子都可以根据同位旋和奇异数排列，并进一步的提出了超荷 $Y=B+S$ (为重子数和奇异数的和) 的概念，并给出了 $\{ 超荷,电荷,同位旋 \}$ 间的深刻关系
$$Q = \frac{Y}{2} + I_{3}$$
进一步的，Gell-Mann 尝试用同位旋 $SU(2)$ 和超荷 $U(1)$ 解释了当时观测到的八个自旋为 1/2 的重子 (重子八重态)，并将这两个群嵌入到一个更大的群——味群 $SU(3)_{\text{flavor}}$，这样做成功的预测了新的重子。

为了将 $SU(3)_{\text{flavor}}$ 进行不可约表示，物理学家提出过多种路线，最终夸克模型活到了最后，夸克模型是说夸克是 $SU(3)$ 的 $(1,0)$ 的表示，反夸克是共轭表示 $(0,1)$。在这种表示中介子是一个夸克和一个反夸克组成 $3 \otimes \bar{3}=8\oplus 1$ 而重子是三个夸克组成的 $3\otimes 3\otimes 3 =10 \oplus 8 \oplus 8 \oplus 1$ 解释了十重态和八重态重子的存在。

但是在解释 $\Delta^{++}$ 粒子时又出现了问题，其波函数在空间、味、自旋上全对称，为了让费米子的全波函数保持反对称，物理学家引入了 “颜色” (红、绿、蓝) 这一新的自由度 $SU(3)_{\text{color}}$ 。理论要求所有物理可观测的强子必须是颜色单态的。这解释了为什么不能分离出两个夸克的结合态，以及为什么实验室中从未探测到孤立的自由夸克，此即 “色禁闭” 。

color 对称性的局域化催生了 QCD，通过胶子传递强力，构成了强相互作用的动力学基础。

## 1.2 SU(3) 数学简介

### 1.2.1 群定义和李代数

顾名思义 $SU(3)$ 就是
$$SU(3) = \{ U\in GL(3,\mathbb{C}) \mid U^{\dagger}U = 1 ,\det U = 1 \} $$
它有 $3^{2}-1=8$ 个独立参数描述，也就是有8个生成元，是一个8维光滑流形。$SU(3)$ 的几何结构可以从重要的纤维丛理解：
$$SU(2)↪SU(3)↪S^{5} $$
因此可以在几何上理解 $SU(3)$ 为 $S^{3}$ 在 $S^{5}$ 上的纤维丛。

$SU(3)$ 是紧的，因为 $SU(3)\subset \mathbb{C}^{3\times 3} \cong \mathbb{R}^{18}$ 是有限维，而其所有元素 $U_{ij}$ 都是有界的，所以是紧的。由于 $U\in SU(3)$ 可以写为 $U=\exp(iH)$ 所以对于任意的一点可以构造路径 $U(t)=\exp(iHt)$ , $U(0)=1,U(1)=U$ 连接到单位元，所以对于任意两点存在光滑路径连接，所以是连通的。


它的李代数 $\mathfrak{su}(3)$ 是
$$\mathfrak{su}(3) = \{ T\in GL(3,\mathbb{C}) \mid T^{\dagger} = -T , \mathrm{Tr}T = 0 \} $$
在物理中通常写为
$$T^{a} = \frac{\lambda^{a}}{2} $$
其中的 $\lambda^{a}$ 是 Gell-Mann matrices，它们满足对易关系
$$[T^{a},T^{b}] = if^{ab}_{c}T^{c} $$
也就是说与 [[QED#1.3 U(1) 群介绍|U(1)]] 最大的不同就是 $SU(3)$ 不是对易的，有结构参数。

### 1.2.2 Weyl 张量构造法

可见 [[SU(n)]] 一个一般的不可约表示可以表示为具有 $n$ 个上指标和 $m$ 个下指标的张量
$$x^{i_{1}\dots i_{n}}_{j_{1}\dots j_{m}} $$
为了确保表示是不可约的，张量必须满足三个约束条件：

-  **上指标全对称**
-  **下指标全对称**
-  **全无迹**：任何一个上指标与任何一个下指标收缩的结果必须为 0

$SU(3)$ 的基本表示是
$$x^{i} ,\quad i=1,2,3 $$
共轭表示是 $y_{i},\quad i=1,2,3$ 群作用为
$$x^{i} \to U^{i}_{\ \ j}x^{j} $$
由于 $U\in SU(3)\implies \det U=1$ 所以存在一个不变完全反对称张量 $\varepsilon_{ijk}$ 满足
$$\varepsilon_{ijk} U^{i}_{\ \ a}U^{j}_{\ \ b}U^{k}_{\ \ c} = \varepsilon_{abc} $$
因此可以用 ε 张量进行指标变换，例如 $x_{i} = \varepsilon_{ijk}x^{jk}$ 但是上下指标不能等价了，也就是说基本表示 $3$ 和共轭表示 $\bar{3}$ 不等价。任意多指标张量 $T^{i_{1}\dots}_{j_{1}\dots}$ 可以分解为对称部分和反对称部分，三个指标的完全反对称部分可以用 ε 张量消去
$$T^{[ijk]} \propto \varepsilon^{ijk} $$
因此三指标反对称张量不产生新的表示，可以化为低阶张量。

如果 $SU(3)$ 由有 $q$ 个对称上标和 $p$ 个对称下标且全无迹的张量表示，则记这种表示为 $(q,p)$ ，这个表示的维度是
$$\text{dim}(q,p) = \frac{1}{2}(p+1)(q+1)(p+q+2) $$

|  $表示$   | $维数$ | $物理意义$  |
| :-----: | :--: | :-----: |
| $(1,0)$ | $3$  |  $夸克$   |
| $(0,1)$ | $3$  |  $反夸克$  |
| $(1,1)$ | $8$  |  $八重态$  |
| $(3,0)$ | $10$ | $重子十重态$ |

$SU(3)$ 的秩是 $\text{rank}SU(3)=2$  所以有两个对角生成元，通常选为
$$I_{3},Y $$
群元可以写为
$$U= \begin{pmatrix}
e^{ i\theta_{1} } & 0 & 0 \\
0 & e^{ i\theta_{2} } & 0 \\
0 & 0 & e^{ -i(\theta_{1}+\theta_{2}) }
\end{pmatrix} $$
在表示空间中，每个张量分量都会获得相位 $e^{ i(w_{1}\theta_{1}+w_{2}\theta_{2}) }$ 其中 $(w_{1},w_{2})$ 称为权也是上下指标数量。

### 1.2.3 不可约表示

$SU(3)$ 的不可约表示可以用两个非负整数 $(p,q)$ 标记，其中 $p$ 和 $q$ 分别对应张量的上指标和下指标的对称化数目。这种表示通常记作 $(p,q)$，其维数为
$$\text{dim}(p,q) = \frac{1}{2}(p+1)(q+1)(p+q+2) $$

#### 重要表示举例

1. **基本表示 $(1,0)$**：维数 3
   - 对应一个上指标张量 $x^i$，$i=1,2,3$
   - 物理上描述夸克的颜色三重态：红、绿、蓝

2. **共轭表示 $(0,1)$**：维数 3  
   - 对应一个下指标张量 $y_i$，通过 $\varepsilon_{ijk}$ 与 $(2,0)$ 表示相关联
   - 物理上描述反夸克的颜色反三重态：反红、反绿、反蓝

3. **伴随表示 $(1,1)$**：维数 8
   - 对应无迹的二阶混合张量 $T^i_j$，满足 $T^i_i = 0$
   - 物理上描述胶子的八重态，对应 $SU(3)$ 的八个生成元

4. **对称表示 $(3,0)$**：维数 10
   - 对应完全对称的三个上指标张量
   - 在味 $SU(3)$ 中对应重子十重态（如 $\Delta^{++}$、$\Omega^-$ 等）

#### 表示乘积分解

$SU(3)$ 表示的张量积可以分解为不可约表示的直和。重要分解包括：

- **两个夸克的结合**：$3 \otimes 3 = 6 \oplus \bar{3}$
   - $6$ 是对称二重态 $(2,0)$，维数 6
   - $\bar{3}$ 是反对称二重态 $(0,1)$，维数 3

- **夸克-反夸克结合**：$3 \otimes \bar{3} = 8 \oplus 1$
   - $8$ 是伴随表示 $(1,1)$，描述胶子和介子八重态
   - $1$ 是单态 $(0,0)$，对应颜色单态（如 $\eta'$ 介子）

- **三个夸克的结合**：$3 \otimes 3 \otimes 3 = 10 \oplus 8 \oplus 8 \oplus 1$
   - $10$ 是完全对称表示 $(3,0)$，对应重子十重态
   - 两个 $8$ 是混合对称表示，对应重子八重态
   - $1$ 是完全反对称颜色单态

#### 权图和最高权理论

$SU(3)$ 是秩为 2 的李群，有两个 Cartan 子代数生成元 $H_1, H_2$。在表示 $(p,q)$ 中，权（weight）是 $H_1, H_2$ 的本征值组 $(w_1, w_2)$。最高权由 $(p,q)$ 决定：
$$w_{\text{最高}} = \left(p + \frac{q}{2}, \frac{\sqrt{3}}{2}q\right)$$

所有其它权可以通过 Weyl 反射得到，构成一个六边形或三角形的权图。表示 $(p,q)$ 的权多重集（weight multiplicities）可以用 Freudenthal 公式计算。

#### 与 $U(1)$ 表示的对比

与 [[QED#1.3.3 不可约表示|U(1)]] 的一维表示 $e^{in\theta}$ 不同，$SU(3)$ 表示有以下特点：

1. **多维性**：大多数表示维度大于 1
2. **非对易性**：生成元不对易，导致复杂的表示结构  
3. **共轭不等价**：$(p,q)$ 与 $(q,p)$ 一般不等价（除非 $p=q$）
4. **张量结构**：不可约表示由对称化的张量描述

这反映了 $SU(3)$ 作为非阿贝尔群与阿贝尔群 $U(1)$ 的本质区别，也为 QCD 的非阿贝尔特性埋下伏笔。



## 1.3 SU(3) 局域化

### 1.3.1 从全局对称性到局域规范对称性

在[[QED#1.3.5 局域 U(1) 对称性与最小耦合|QED]]中，我们将全局 $U(1)$ 对称性推广为局域规范对称性，引入了电磁场 $A_\mu$ 作为规范场。对于 $SU(3)$ 颜色对称性，我们进行类似的推广，但面临非阿贝尔群带来的根本差异。

考虑夸克场 $\psi(x)$，它在 $SU(3)$ 的基本表示 $(1,0)$ 下变换。**全局** $SU(3)$ 变换为：
$$\psi(x) \longmapsto \psi'(x) = U\psi(x),\quad U \in SU(3)$$
其中 $U$ 是与时空点无关的常数矩阵。

**局域** $SU(3)$ 变换则将 $U$ 提升为时空依赖的函数：
$$\psi(x) \longmapsto \psi'(x) = U(x)\psi(x),\quad U(x) \in SU(3)$$

### 1.3.2 协变导数与非阿贝尔规范场

与 QED 类似，普通导数 $\partial_\mu\psi$ 在局域变换下不协变：
$$\partial_\mu\psi \longmapsto U(x)[\partial_\mu\psi] + [\partial_\mu U(x)]\psi(x)$$
多出的第二项破坏了协变性。

为了构造协变导数，我们引入 $SU(3)$ 规范场（胶子场）$A_\mu(x)$。$A_\mu(x)$ 取值于 $\mathfrak{su}(3)$ 李代数，可以展开为：
$$A_\mu(x) = A_\mu^a(x) T^a,\quad a=1,\dots,8$$
其中 $T^a = \lambda^a/2$ 是 $SU(3)$ 的生成元。

协变导数定义为：
$$D_\mu\psi = \partial_\mu\psi - ig_s A_\mu\psi$$
其中 $g_s$ 是强耦合常数。

为使 $D_\mu\psi$ 协变变换：
$$D_\mu\psi \longmapsto U(x) D_\mu\psi$$
规范场 $A_\mu$ 必须按如下规则变换：
$$A_\mu \longmapsto U A_\mu U^{-1} + \frac{i}{g_s} (\partial_\mu U) U^{-1}$$

### 1.3.3 非阿贝尔场强张量

在 QED 中，场强张量 $F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$ 是规范不变的。对于非阿贝尔规范理论，我们需要定义相应的场强张量。

从协变导数的对易子出发：
$$[D_\mu, D_\nu]\psi = -ig_s F_{\mu\nu}\psi$$
可以导出：
$$F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu - ig_s [A_\mu, A_\nu]$$

写成分量形式：
$$F_{\mu\nu}^a = \partial_\mu A_\nu^a - \partial_\nu A_\mu^a + g_s f^{abc} A_\mu^b A_\nu^c$$
其中 $f^{abc}$ 是 $SU(3)$ 的结构常数。

与 QED 场强相比，非阿贝尔场强多出了 $-ig_s[A_\mu, A_\nu]$ 项（或 $g_s f^{abc} A_\mu^b A_\nu^c$），这反映了规范场的自相互作用。

### 1.3.4 规范变换的几何解释

从纤维丛几何的角度看：

1. **主丛**：时空 $M$ 上的 $SU(3)$ 主丛 $P(M, SU(3))$
2. **联络**：规范场 $A_\mu$ 是主丛上的联络 1-形式
3. **曲率**：场强 $F_{\mu\nu}$ 是联络的曲率 2-形式
4. **伴从丛**：夸克场是伴从丛 $\mathbb{C}^3$ 的截面

局域规范变换对应于主丛的局部平凡化坐标变换。非阿贝尔性体现在：
- 联络 $A_\mu$ 的李代数值特性
- 曲率公式中的 $A \wedge A$ 项
- 规范变换的非线性性：$A_\mu \mapsto U A_\mu U^{-1} + \frac{i}{g_s} (\partial_\mu U) U^{-1}$

### 1.3.5 与 QED 局域化的对比

| 特性 | QED ($U(1)$) | QCD ($SU(3)$) |
|------|-------------|---------------|
| **规范群** | 阿贝尔 $U(1)$ | 非阿贝尔 $SU(3)$ |
| **规范场** | 光子 $A_\mu$ | 胶子 $A_\mu^a$ (8个分量) |
| **场强公式** | $F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$ | $F_{\mu\nu}^a = \partial_\mu A_\nu^a - \partial_\nu A_\mu^a + g_s f^{abc} A_\mu^b A_\nu^c$ |
| **自相互作用** | 无 ($[A_\mu, A_\nu]=0$) | 有 (非线性项) |
| **规范变换** | $A_\mu \mapsto A_\mu + \partial_\mu\theta$ | $A_\mu \mapsto U A_\mu U^{-1} + \frac{i}{g_s} (\partial_\mu U) U^{-1}$ |
| **几何结构** | $U(1)$ 主丛，平凡曲率代数 | $SU(3)$ 主丛，非平凡曲率代数 |

### 1.3.6 物理意义

$SU(3)$ 局域化导致：

1. **胶子的自相互作用**：三胶子和四胶子顶点，源于场强中的非线性项
2. **渐近自由**：非阿贝尔性使得耦合常数随能量增加而减小
3. **色禁闭的可能机制**：非线性的动力学可能导致通量管形成
4. **丰富的真空结构**：瞬子、$\theta$ 真空等非微扰效应

这些特性使 QCD 成为比 QED 更复杂、更丰富的规范理论，也解释了强相互作用的独特现象。


# 2. QCD 作用量

## 2.1 构建原则

与 [[QED#2. 自由拉式量的构造|QED]] 类似，QCD 作用量的构建遵循以下基本原则：

1. **庞加莱不变性**：作用量在洛伦兹变换和时空平移下不变
2. **定域 $SU(3)_c$ 规范不变性**：作用量在局域颜色 $SU(3)$ 变换下不变
3. **可重整性**：耦合常数的量纲允许进行微扰展开和重整化
4. **幺正性**：保证概率守恒和物理态的合理性

与 QED 相比，QCD 的**非阿贝尔性**引入了新的约束和要求：
- 规范场的自相互作用必须包含在作用量中
- 规范固定过程更复杂，需要引入鬼场
- 重整化群行为不同（渐近自由）

## 2.2 夸克场部分

### 2.2.1 夸克场的多重结构

夸克场 $\psi_f^i(x)$ 携带多个指标：
- **味指标** $f = u, d, s, c, b, t$：区分不同种类的夸克
- **颜色指标** $i = 1,2,3$：对应红、绿、蓝三种颜色
- **旋量指标**（隐含）：4分量 Dirac 旋量

对于轻夸克 ($u,d,s$)，质量较小，手征对称性近似成立；对于重夸克 ($c,b,t$)，质量较大，非相对论近似可能适用。

### 2.2.2 夸克场的自由拉格朗日量

不考虑相互作用的自由夸克场拉格朗日量为：
$$\mathcal{L}_q^{\text{free}} = \sum_f \bar{\psi}_f (i\not{\!\partial} - m_f) \psi_f$$

其中 $\not{\!\partial} = \gamma^\mu \partial_\mu$，$m_f$ 是夸克 $f$ 的质量。在颜色空间，这实际上是单位矩阵：
$$\mathcal{L}_q^{\text{free}} = \sum_f \bar{\psi}_f^i (i\not{\!\partial} - m_f) \delta^{ij} \psi_f^j$$

### 2.2.3 规范不变的要求

为了满足局域 $SU(3)$ 规范不变性，普通导数 $\partial_\mu$ 必须替换为协变导数 $D_\mu$：
$$\partial_\mu \longrightarrow D_\mu = \partial_\mu - ig_s A_\mu$$

其中 $A_\mu = A_\mu^a T^a$，$T^a$ 是 $SU(3)$ 在夸克表示（基本表示）中的生成元。在基本表示中，$T^a = \lambda^a/2$，$\lambda^a$ 是 Gell-Mann 矩阵。

夸克部分的规范不变拉格朗日量为：
$$\mathcal{L}_q = \sum_f \bar{\psi}_f (i\not{\!D} - m_f) \psi_f$$
其中 $\not{\!D} = \gamma^\mu D_\mu$。

## 2.3 胶子场部分

### 2.3.1 规范场的引入

胶子场 $A_\mu^a(x)$ 是 $SU(3)$ 规范势，$a=1,\dots,8$ 对应 8 个生成元。与 QED 的光子场不同：
- 胶子场携带颜色电荷（在伴随表示下变换）
- 胶子之间有自相互作用
- 胶子场本身不是规范不变的物理可观测量

### 2.3.2 场强张量的构造

从 [[#1.3.3 非阿贝尔场强张量|1.3.3 节]] 已知，非阿贝尔场强张量为：
$$F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu - ig_s [A_\mu, A_\nu]$$
$$F_{\mu\nu}^a = \partial_\mu A_\nu^a - \partial_\nu A_\mu^a + g_s f^{abc} A_\mu^b A_\nu^c$$

关键的非线性项 $g_s f^{abc} A_\mu^b A_\nu^c$ 反映了胶子的自相互作用。

### 2.3.3 胶子场的动力学项

与 QED 类似，我们希望构造规范不变的动力学项。最简单的二次型是：
$$\mathcal{L}_g = -\frac{1}{4} F_{\mu\nu}^a F^{a\mu\nu}$$

可以验证，这一项在规范变换下不变。展开后得到：
$$\mathcal{L}_g = -\frac{1}{4} (\partial_\mu A_\nu^a - \partial_\nu A_\mu^a)(\partial^\mu A^{a\nu} - \partial^\nu A^{a\mu}) - \frac{g_s}{2} f^{abc} (\partial_\mu A_\nu^a - \partial_\nu A_\mu^a) A^{b\mu} A^{c\nu} - \frac{g_s^2}{4} f^{abc} f^{ade} A_\mu^b A_\nu^c A^{d\mu} A^{e\nu}$$

这三项分别对应：
1. **自由胶子项**：类似于光子的 Maxwell 项
2. **三胶子顶点项**：胶子自相互作用的立方项
3. **四胶子顶点项**：胶子自相互作用的四次项

### 2.3.4 与 QED 规范场的对比

| 特性 | QED 光子场 | QCD 胶子场 |
|------|-----------|-----------|
| **数目** | 1 种 ($A_\mu$) | 8 种 ($A_\mu^a$) |
| **群表示** | $U(1)$ 伴随表示（平凡） | $SU(3)$ 伴随表示（8 维） |
| **自相互作用** | 无 | 有（三胶子、四胶子顶点） |
| **携带电荷** | 不带电（中性） | 带颜色电荷 |
| **规范变换** | $A_\mu \to A_\mu + \partial_\mu\theta$ | $A_\mu \to U A_\mu U^{-1} + \frac{i}{g_s}(\partial_\mu U)U^{-1}$ |

## 2.4 完整 QCD 拉格朗日量

### 2.4.1 经典 QCD 拉格朗日量

结合夸克部分和胶子部分，得到完整的经典 QCD 拉格朗日量：
$$\mathcal{L}_{\text{QCD}}^{\text{classical}} = -\frac{1}{4} F_{\mu\nu}^a F^{a\mu\nu} + \sum_f \bar{\psi}_f (i\not{\!D} - m_f) \psi_f$$

写为更显式的形式：
$$\mathcal{L}_{\text{QCD}}^{\text{classical}} = -\frac{1}{4} (\partial_\mu A_\nu^a - \partial_\nu A_\mu^a + g_s f^{abc} A_\mu^b A_\nu^c)(\partial^\mu A^{a\nu} - \partial^\nu A^{a\mu} + g_s f^{ade} A^{d\mu} A^{e\nu}) + \sum_f \bar{\psi}_f^i \left[i\gamma^\mu(\partial_\mu \delta^{ij} - ig_s A_\mu^a T^a_{ij}) - m_f \delta^{ij}\right] \psi_f^j$$

### 2.4.2 规范不变性验证

可以验证 $\mathcal{L}_{\text{QCD}}$ 在以下局域规范变换下不变：
1. 夸克场：$\psi(x) \to U(x)\psi(x)$
2. 胶子场：$A_\mu(x) \to U(x)A_\mu(x)U^{-1}(x) + \frac{i}{g_s}[\partial_\mu U(x)]U^{-1}(x)$

其中 $U(x) = \exp[i\theta^a(x)T^a] \in SU(3)$。

### 2.4.3 经典运动方程

从拉格朗日量可以导出经典运动方程：

1. **夸克的 Dirac 方程**：
   $$(i\not{\!D} - m_f)\psi_f = 0$$

2. **胶子的 Yang-Mills 方程**：
   $$D_\mu F^{a\mu\nu} = g_s \sum_f \bar{\psi}_f \gamma^\nu T^a \psi_f$$
   其中 $D_\mu F^{a\mu\nu} = \partial_\mu F^{a\mu\nu} + g_s f^{abc} A_\mu^b F^{c\mu\nu}$ 是协变导数。

第二方程右侧是夸克的色流，类似于 Maxwell 方程中的电流源。

### 2.4.4 守恒律与对称性

1. **能量-动量守恒**：来自庞加莱不变性
2. **色流守恒**：来自规范对称性，但注意色流不是规范不变的物理量
3. **重子数守恒**：来自全局 $U(1)_B$ 对称性
4. **味对称性**：在质量简并极限下，有 $SU(n_f)_V \times SU(n_f)_A$ 对称性

### 2.4.5 与 QED 作用量的比较

QCD 拉格朗日量与 QED 拉格朗日量的关键区别：

1. **规范群**：$U(1)$ vs $SU(3)$
2. **场强张量**：线性 vs 非线性
3. **规范玻色子**：中性光子 vs 带色胶子
4. **自相互作用**：无 vs 有三胶子、四胶子顶点
5. **耦合常数跑动**：红外自由 vs 渐近自由

这些差异导致 QCD 展现出与 QED 完全不同的物理现象：色禁闭、渐近自由、手征对称性自发破缺等。


# 3. 路径积分与鬼场

## 3.1 路径积分量子化与泛函方法

QCD 的路径积分量子化面临比 QED 更复杂的规范冗余问题。由于 $SU(3)$ 的非阿贝尔特性，规范固定过程需要更精细的处理。

### 3.1.1 路径积分测度与规范冗余

QCD 的配分函数定义为：
$$Z = \int \mathcal{D}A \mathcal{D}\bar{\psi}\mathcal{D}\psi \, e^{iS_{\text{QCD}}[A,\bar{\psi},\psi]}$$

其中 $S_{\text{QCD}} = \int d^4x \, \mathcal{L}_{\text{QCD}}$ 是经典作用量。与 QED 类似，直接积分会因规范冗余而发散：对于每个物理构型，有无穷多个通过规范变换相关的构型给出相同的贡献。

考虑规范变换 $A_\mu \to A_\mu^\Omega = \Omega A_\mu \Omega^{-1} + \frac{i}{g_s}(\partial_\mu\Omega)\Omega^{-1}$，其中 $\Omega(x) \in SU(3)$。测度 $\mathcal{D}A$ 在规范变换下形式不变（因为 Jacobi 行列式为 1），但积分域包含了所有规范等价类，导致发散。

### 3.1.2 Faddeev-Popov 手续

Faddeev-Popov 方法通过插入恒等式来固定规范。选择规范条件 $G^a[A](x) = 0$，常用的有：
- **协变规范**：$\partial^\mu A_\mu^a(x) = 0$（Lorenz 规范）
- **轴向规范**：$n^\mu A_\mu^a(x) = 0$，其中 $n^\mu$ 是固定矢量
- **库仑规范**：$\partial^i A_i^a(x) = 0$

插入恒等式：
$$1 = \int \mathcal{D}\Omega \, \delta(G[A^\Omega]) \det\left(\frac{\delta G[A^\Omega]}{\delta\Omega}\right)$$

其中 $\mathcal{D}\Omega$ 是规范群上的 Haar 测度，行列式是 Faddeev-Popov 行列式。

### 3.1.3 Faddeev-Popov 行列式与鬼场

对于协变规范 $G^a[A] = \partial^\mu A_\mu^a - \omega^a$，其中 $\omega^a(x)$ 是任意函数。规范变换的变分为：
$$\delta A_\mu^a = D_\mu^{ab} \delta\theta^b = (\partial_\mu \delta^{ab} + g_s f^{acb} A_\mu^c) \delta\theta^b$$

因此：
$$\frac{\delta G^a[A^\Omega](x)}{\delta\Omega^b(y)} = \partial^\mu D_\mu^{ab} \delta^{(4)}(x-y)$$

Faddeev-Popov 行列式为：
$$\det\left(\partial^\mu D_\mu^{ab}\right)$$

与 QED 不同，这个行列式依赖于规范场 $A_\mu$，不能吸收为常数。通过引入反对易标量场（鬼场）$\eta^a, \bar{\eta}^a$，可以将行列式指数化：
$$\det(\partial^\mu D_\mu^{ab}) = \int \mathcal{D}\bar{\eta}\mathcal{D}\eta \, \exp\left(i\int d^4x \, \bar{\eta}^a \partial^\mu D_\mu^{ab} \eta^b\right)$$

鬼场拉格朗日量为：
$$\mathcal{L}_{\text{ghost}} = \bar{\eta}^a \partial^\mu D_\mu^{ab} \eta^b = \bar{\eta}^a \partial^2 \eta^a + g_s f^{abc} \bar{\eta}^a \partial^\mu (A_\mu^b \eta^c)$$

鬼场是标量场但满足 Grassmann 统计，这是为了保证行列式表达式的正确性。

### 3.1.4 规范固定项

为了得到可逆的传播子，需要添加规范固定项。对于协变规范，通常采用：
$$\mathcal{L}_{\text{gf}} = -\frac{1}{2\xi} (\partial^\mu A_\mu^a)^2$$

其中 $\xi$ 是规范参数。常用选择：
- $\xi = 1$：Feynman 规范
- $\xi = 0$：Landau 规范（严格满足 $\partial^\mu A_\mu^a = 0$）

### 3.1.5 完整量子作用量

经过 Faddeev-Popov 手续，QCD 的完整量子作用量为：
$$S_{\text{QCD}}^{\text{quantum}} = \int d^4x \left[ \mathcal{L}_{\text{QCD}}^{\text{classical}} + \mathcal{L}_{\text{gf}} + \mathcal{L}_{\text{ghost}} \right]$$

展开写为：
$$\begin{align}
S_{\text{QCD}}^{\text{quantum}} = & \int d^4x \left[ -\frac{1}{4} F_{\mu\nu}^a F^{a\mu\nu} + \sum_f \bar{\psi}_f (i\not{\!D} - m_f) \psi_f \right] \\
& - \frac{1}{2\xi} \int d^4x \, (\partial^\mu A_\mu^a)^2 \\
& + \int d^4x \, \bar{\eta}^a \partial^\mu D_\mu^{ab} \eta^b
\end{align}$$

### 3.1.6 BRST 对称性

量子作用量具有重要的 Becchi-Rouet-Stora-Tyutin (BRST) 对称性，这是规范对称性在量子水平上的体现。BRST 变换定义为：
$$\begin{align}
\delta A_\mu^a &= \epsilon D_\mu^{ab} \eta^b \\
\delta \psi &= i g_s \epsilon \eta^a T^a \psi \\
\delta \bar{\psi} &= i g_s \epsilon \bar{\psi} \eta^a T^a \\
\delta \eta^a &= -\frac{1}{2} g_s \epsilon f^{abc} \eta^b \eta^c \\
\delta \bar{\eta}^a &= -\frac{1}{\xi} \epsilon \partial^\mu A_\mu^a
\end{align}$$

其中 $\epsilon$ 是反交换的 Grassmann 参数。可以验证量子作用量在 BRST 变换下不变。BRST 对称性保证了：
1. 物理 Hilbert 空间的正定性
2. 规范参数 $\xi$ 的不相关性（物理可观测量与 $\xi$ 无关）
3. Slavnov-Taylor 恒等式（非阿贝尔版本的 Ward 恒等式）

### 3.1.7 泛函生成泛函

引入外源 $J_\mu^a, \bar{\eta}_\psi, \eta_\psi, \bar{\xi}^a, \xi^a$ 分别对应胶子场、夸克场、反夸克场、鬼场、反鬼场，定义生成泛函：
$$Z[J,\bar{\eta}_\psi,\eta_\psi,\bar{\xi},\xi] = \int \mathcal{D}A\mathcal{D}\bar{\psi}\mathcal{D}\psi\mathcal{D}\bar{\eta}\mathcal{D}\eta \, \exp\left(iS_{\text{quantum}} + i\int d^4x \, [J_\mu^a A^{a\mu} + \bar{\eta}_\psi\psi + \bar{\psi}\eta_\psi + \bar{\xi}^a\eta^a + \bar{\eta}^a\xi^a]\right)$$

连通生成泛函 $W = -i\ln Z$，有效作用量 $\Gamma$ 通过 Legendre 变换定义：
$$\Gamma[\Phi_{\text{cl}}] = W[J] - \int d^4x \, J_i \Phi_{\text{cl}}^i$$

其中 $\Phi_{\text{cl}}$ 是经典场。

## 3.2 鬼场的物理意义与必要性

### 3.2.1 为什么需要鬼场

在非阿贝尔规范理论中，鬼场是必需的，原因包括：
1. **抵消非物理极化**：胶子有 4 个分量，但物理自由度只有 2 个（横极化）。鬼场抵消了纵极化和类时极化的贡献。
2. **保持幺正性**：没有鬼场时，S 矩阵不满足幺正性。
3. **实现 BRST 对称性**：鬼场是 BRST 多重态的组成部分。

### 3.2.2 鬼场的统计性质

鬼场是标量场但满足 Grassmann 代数：
$$\eta^a(x)\eta^b(y) + \eta^b(y)\eta^a(x) = 0$$
$$\bar{\eta}^a(x)\bar{\eta}^b(y) + \bar{\eta}^b(y)\bar{\eta}^a(x) = 0$$
$$\eta^a(x)\bar{\eta}^b(y) + \bar{\eta}^b(y)\eta^a(x) = 0$$

这使得鬼场环图贡献额外的负号，恰抵消了规范玻色子环图中非物理自由度的贡献。

### 3.2.3 鬼场不与物理态耦合

在协变规范中，鬼场只与规范场耦合，不与物质场（夸克）直接耦合。鬼场线总是以闭合圈的形式出现在费曼图中，或者连接规范玻色子线。

### 3.2.4 不同规范下的鬼场

1. **协变规范**：需要鬼场，有鬼场-胶子相互作用项
2. **轴向规范** $(n\cdot A^a=0)$：不需要鬼场（Faddeev-Popov 行列式与 $A_\mu$ 无关），但传播子形式复杂
3. **库仑规范**：需要鬼场，但鬼场是静态的（只有空间分量）


# 4. 费曼规则

基于量子作用量 $S_{\text{QCD}}^{\text{quantum}}$，可以导出微扰计算所需的费曼规则。以下给出协变规范（$R_\xi$ 规范）下的规则。

## 4.1 传播子

### 4.1.1 胶子传播子

在协变规范 $(\partial^\mu A_\mu^a)^2/(2\xi)$ 下，胶子传播子为：
$$\tilde{D}_{\mu\nu}^{ab}(k) = \frac{i\delta^{ab}}{k^2 + i\epsilon} \left[ -g_{\mu\nu} + (1-\xi)\frac{k_\mu k_\nu}{k^2} \right]$$

常用规范选择：
- **Feynman 规范** ($\xi=1$): $\tilde{D}_{\mu\nu}^{ab}(k) = -\frac{i\delta^{ab} g_{\mu\nu}}{k^2 + i\epsilon}$
- **Landau 规范** ($\xi=0$): $\tilde{D}_{\mu\nu}^{ab}(k) = \frac{i\delta^{ab}}{k^2 + i\epsilon} \left( -g_{\mu\nu} + \frac{k_\mu k_\nu}{k^2} \right)$

### 4.1.2 夸克传播子

夸克的费米子传播子与 QED 中的电子传播子形式相同，但带有颜色指标：
$$\tilde{S}_{ij}(p) = i\delta_{ij} \frac{\not{\!p} + m}{p^2 - m^2 + i\epsilon}$$

其中 $i,j=1,2,3$ 是颜色指标。在味空间，不同味的夸克传播子是对角的。

### 4.1.3 鬼场传播子

鬼场是标量 Grassmann 场，其传播子为：
$$\tilde{\Delta}^{ab}(k) = \frac{i\delta^{ab}}{k^2 + i\epsilon}$$

注意鬼场是无质量的，即使对应的规范玻色子可能有有效质量（在红外区域）。

## 4.2 相互作用顶点

### 4.2.1 夸克-胶子顶点

夸克-胶子相互作用顶点来自 $\bar{\psi} (i g_s \gamma^\mu A_\mu^a T^a) \psi$：
$$V_{q\bar{q}g}^{\mu,a} = -i g_s \gamma^\mu T^a_{ij}$$

其中 $i,j$ 是夸克的出、入颜色指标，$a$ 是胶子的颜色指标。动量从夸克流向顶点时守恒。

### 4.2.2 三胶子顶点

来自 $\mathcal{L}_g$ 中的三次项，三胶子顶点为：
$$V_{3g}^{\mu\nu\rho,abc}(p,q,r) = g_s f^{abc} V^{\mu\nu\rho}(p,q,r)$$

其中动量约定：所有动量指向顶点，$p+q+r=0$，
$$\begin{align}
V^{\mu\nu\rho}(p,q,r) = & (p-q)^\rho g^{\mu\nu} + (q-r)^\mu g^{\nu\rho} + (r-p)^\nu g^{\rho\mu} \\
& = (p-q)^\rho g^{\mu\nu} + (q-r)^\mu g^{\nu\rho} + (r-p)^\nu g^{\rho\mu}
\end{align}$$

或者更对称的形式：
$$V^{\mu\nu\rho}(p,q,r) = (p-q)^\rho g^{\mu\nu} + (q-r)^\mu g^{\nu\rho} + (r-p)^\nu g^{\rho\mu}$$

### 4.2.3 四胶子顶点

来自 $\mathcal{L}_g$ 中的四次项，四胶子顶点为：
$$V_{4g}^{\mu\nu\rho\sigma,abcd} = -i g_s^2 [ f^{abe} f^{cde} (g^{\mu\rho} g^{\nu\sigma} - g^{\mu\sigma} g^{\nu\rho}) + f^{ace} f^{bde} (g^{\mu\nu} g^{\rho\sigma} - g^{\mu\sigma} g^{\nu\rho}) + f^{ade} f^{bce} (g^{\mu\nu} g^{\rho\sigma} - g^{\mu\rho} g^{\nu\sigma}) ]$$

可以简记为：
$$V_{4g}^{\mu\nu\rho\sigma,abcd} = -i g_s^2 \sum_{\text{cyclic}} f^{abe} f^{cde} (g^{\mu\rho} g^{\nu\sigma} - g^{\mu\sigma} g^{\nu\rho})$$

### 4.2.4 鬼场-胶子顶点

来自鬼场拉格朗日量 $\mathcal{L}_{\text{ghost}} = g_s f^{abc} \bar{\eta}^a \partial^\mu (A_\mu^b \eta^c)$，鬼场-胶子顶点为：
$$V_{\bar{\eta}\eta g}^{\mu,abc}(k) = -g_s f^{abc} k^\mu$$

其中 $k^\mu$ 是进入鬼场 $\eta^c$ 的动量（按鬼场线箭头方向）。

## 4.3 外线因子

### 4.3.1 夸克外线

|        | 入射夸克       | 出射夸克       |
|--------|---------------|---------------|
| 粒子   | $u(p,s)_{i}$  | $\bar{u}(p,s)_{i}$ |
| 反粒子 | $\bar{v}(p,s)_{i}$ | $v(p,s)_{i}$ |

其中 $i=1,2,3$ 是颜色指标，$s$ 是自旋指标。

### 4.3.2 胶子外线

胶子外线极化矢量满足：
$$k_\mu \varepsilon^\mu(k,\lambda) = 0 \quad (\text{对于物理极化})$$

|                | 入射胶子               | 出射胶子                 |
|----------------|-----------------------|-------------------------|
| 极化矢量       | $\varepsilon_\mu^a(k,\lambda)$ | $\varepsilon_\mu^{a*}(k,\lambda)$ |

颜色指标 $a=1,\dots,8$，极化指标 $\lambda=1,2$ 对应两个横极化。

### 4.3.3 鬼场外线

鬼场只在圈图中作为内线出现，没有外线鬼场粒子（鬼场不是物理态）。

## 4.4 计算规则与符号约定

### 4.4.1 颜色代数

计算振幅时需要进行颜色求和。常用关系：

1. **生成元迹**：
   $$\text{Tr}(T^a T^b) = T_F \delta^{ab} = \frac{1}{2} \delta^{ab}$$

2. **生成元乘积**：
   $$T^a_{ij} T^a_{kl} = \frac{1}{2} \left( \delta_{il} \delta_{kj} - \frac{1}{N_c} \delta_{ij} \delta_{kl} \right)$$
   对于 $SU(3)$，$N_c=3$。

3. **结构常数**：
   $$f^{acd} f^{bcd} = C_A \delta^{ab} = 3 \delta^{ab} \quad (\text{对 } SU(3))$$

4. **Casmir 算符**：
   - 基本表示：$C_F = \frac{N_c^2-1}{2N_c} = \frac{4}{3}$
   - 伴随表示：$C_A = N_c = 3$

### 4.4.2 费曼图规则总结

1. **动量守恒**：每个顶点处动量守恒。
2. **费米子线方向**：沿着费米子箭头方向写振幅。
3. **鬼场线方向**：鬼场线有方向（从 $\eta$ 到 $\bar{\eta}$）。
4. **圈图积分**：对每个独立圈动量 $l$ 积分 $\int d^4l/(2\pi)^4$。
5. **对称因子**：考虑图的对称性。
6. **费米子圈符号**：每个闭合费米子圈贡献因子 $(-1)$。
7. **鬼场圈符号**：每个鬼场圈也贡献因子 $(-1)$。

### 4.4.3 颜色流表示法

在计算多胶子振幅时，常用颜色流表示法（color-flow representation）。将 $SU(3)$ 生成元写为：
$$(T^a)_{ij} = \frac{1}{\sqrt{2}} (\delta_{i\alpha} \delta_{\beta j} - \frac{1}{3} \delta_{ij} \delta_{\alpha\beta})$$

这样可以分离颜色流和动力学部分。

## 4.5 树图振幅示例

### 4.5.1 $q\bar{q} \to gg$ 过程

考虑夸克-反夸克湮灭产生两个胶子：$q(p_1) + \bar{q}(p_2) \to g(k_1) + g(k_2)$。

有三个贡献图：
1. $s$-道：夸克-反夸克通过胶子传播子产生两个胶子
2. $t$-道：夸克发射胶子 $k_1$ 后与反夸克作用产生胶子 $k_2$
3. $u$-道：夸克发射胶子 $k_2$ 后与反夸克作用产生胶子 $k_1$

振幅结构：
$$i\mathcal{M} = \bar{v}(p_2) [ \Gamma^{\mu\nu} ] u(p_1) \varepsilon_\mu^{a*}(k_1) \varepsilon_\nu^{b*}(k_2)$$

其中 $\Gamma^{\mu\nu}$ 包含三个图的贡献，涉及颜色因子 $T^a T^b$, $T^b T^a$ 和 $if^{abc} T^c$。

### 4.5.2 $gg \to gg$ 过程

胶子-胶子散射有四类图：
1. 四胶子顶点
2. $s$-, $t$-, $u$-道的三胶子顶点交换

振幅包含完全对称的颜色和 Lorentz 结构。

### 4.5.3 颜色排序振幅

对于胶子振幅，常用颜色排序（color-ordered）振幅。将全振幅写为：
$$\mathcal{M} = \sum_{\sigma \in S_{n-1}} \text{Tr}(T^{a_1} T^{a_{\sigma(2)}} \cdots T^{a_{\sigma(n)}}) A(1,\sigma(2),\ldots,\sigma(n))$$

其中 $A(1,2,\ldots,n)$ 是颜色排序振幅，仅依赖于胶子的极化和动量，满足：
- **循环对称性**：$A(1,2,\ldots,n) = A(2,\ldots,n,1)$
- **反射对称性**：$A(1,2,\ldots,n) = (-1)^n A(n,\ldots,2,1)$
- **光子分解性质**（U(1）解耦）：将任一胶子替换为光子时，某些和为零


# 5. 重整化

QCD 作为可重整化量子场论，其紫外发散可以通过重整化手续消除。与 QED 相比，QCD 的重整化有独特特征，最重要的是**渐近自由**——耦合常数随能量增加而减小。

## 5.1 QCD 中的紫外发散

### 5.1.1 发散结构

QCD 的单圈发散主要出现在以下 1PI 图中：

1. **夸克自能** $\Sigma(p)$：夸克两点函数修正
2. **胶子自能（真空极化）** $\Pi^{\mu\nu}_{ab}(q)$：胶子两点函数修正  
3. **夸克-胶子顶点修正** $\Lambda^\mu_{a,ij}(p,p')$：三点函数修正
4. **三胶子顶点修正** $\Gamma^{\mu\nu\rho}_{abc}(p,q,r)$
5. **四胶子顶点修正** $\Gamma^{\mu\nu\rho\sigma}_{abcd}$
6. **鬼场自能** 和 **鬼场-胶子顶点修正**

### 5.1.2 幂次计数与可重整性

QCD 拉格朗日量中各项的量纲：
- $[A_\mu^a] = 1$, $[\psi] = 3/2$, $[\eta^a] = 1$
- $[F_{\mu\nu}^a] = 2$, $[\bar{\psi}\psi] = 3$, $[\bar{\psi}D\!\!\!\!/\psi] = 4$
- 耦合常数 $[g_s] = 0$，理论是可重整的。

用 BPHZ 幂次计数公式：
$$D = 4 - E_A - \frac{3}{2} E_\psi + \sum_V (d_V + \frac{3}{2} f_V + b_V - 4)$$

其中 $E_A, E_\psi$ 是外胶子、夸克线数，$b_V, f_V, d_V$ 是顶点 $V$ 的玻色子、费米子线数和导数数。对于 QCD 所有顶点 $d_V + \frac{3}{2} f_V + b_V - 4 = 0$，所以：
$$D = 4 - E_A - \frac{3}{2} E_\psi$$

需要抵消的格林函数有：
- $E_A=2, E_\psi=0$（胶子自能）：$D=2$，可能发散形式 $\sim A^2, (\partial A)^2$
- $E_A=0, E_\psi=2$（夸克自能）：$D=1$，实际为对数发散（Lorentz 结构限制）
- $E_A=1, E_\psi=2$（夸克-胶子顶点）：$D=0$，对数发散
- $E_A=3, E_\psi=0$（三胶子顶点）：$D=1$，实际为对数发散
- $E_A=4, E_\psi=0$（四胶子顶点）：$D=0$，对数发散

### 5.1.3 对称性限制

与 QED 的 Ward 恒等式类似，QCD 有更复杂的 Slavnov-Taylor 恒等式（BRST 对称性的结果），限制抵消项的形式。这些恒等式保证：
1. 胶子质量项 $m_A^2 A_\mu^a A^{a\mu}$ 不被生成
2. 规范固定参数 $\xi$ 的重整化与场重整化关联
3. 鬼场结构与规范场结构协调

## 5.2 重整化方案

### 5.2.1 裸量与重整化量

引入重整化尺度 $\mu$，定义重整化场和参数：
$$\begin{align}
A_{0\mu}^a &= Z_3^{1/2} A_\mu^a \\
\psi_0 &= Z_2^{1/2} \psi \\
\eta_0^a &= \tilde{Z}_3^{1/2} \eta^a \\
g_{s0} &= Z_g g_s \mu^\epsilon \quad (\text{在 } d=4-2\epsilon \text{ 维}) \\
\xi_0 &= Z_\xi \xi \\
m_{0f} &= Z_m m_f
\end{align}$$

对于 $SU(N_c)$ 规范群，约定归一化 $\text{Tr}(T^a T^b) = T_F \delta^{ab}$，$T_F=1/2$。

### 5.2.2 MS 与 $\overline{\text{MS}}$ 方案

最常用的是最小减除（MS）和改进的最小减除（$\overline{\text{MS}}$）方案：
- **MS**：只减除发散部分 $1/\epsilon^n$
- **$\overline{\text{MS}}$**：减除 $1/\epsilon^n - \gamma_E + \ln(4\pi)$ 组合

在维数正规化 $d=4-2\epsilon$ 下，发散表现为 $\epsilon$ 极点。

### 5.2.3 在壳方案

与 QED 类似，也可用在壳重整化：
1. 极点位置定义物理质量
2. 留数定义场重整化常数
3. 特定动量点定义耦合常数

但在 QCD 中，由于色禁闭，夸克和胶子不在质壳上，在壳方案不直接适用。

## 5.3 一圈重整化常数计算

### 5.3.1 胶子自能与真空极化

一圈胶子自能来自三个图：
1. 夸克圈（类似 QED 的光子自能）
2. 胶子圈（三胶子顶点贡献）
3. 鬼场圈

在协变规范、维数正规化下，真空极化张量为：
$$\Pi^{\mu\nu}_{ab}(q) = i(q^2 g^{\mu\nu} - q^\mu q^\nu) \delta_{ab} \Pi(q^2)$$

$$\Pi(q^2) = \frac{g_s^2}{16\pi^2} \left[ \left( \frac{13}{6} C_A - \frac{4}{3} T_F N_f \right) \frac{1}{\epsilon} + \text{有限项} \right]$$

对于 $SU(3)$，$C_A=3$, $T_F=1/2$：
$$\Pi(q^2)_{\text{div}} = \frac{g_s^2}{16\pi^2} \left( \frac{11}{2} - \frac{2}{3} N_f \right) \frac{1}{\epsilon}$$

其中 $N_f$ 是活跃夸克味数。

### 5.3.2 夸克自能

夸克自能来自单胶子交换图：
$$\Sigma(p) = \frac{g_s^2}{16\pi^2} C_F \left[ \frac{1}{\epsilon} (\not{\!p} - 4m) + \text{有限项} \right]$$

对于 $SU(3)$，$C_F = 4/3$。

### 5.3.3 夸克-胶子顶点

夸克-胶子顶点修正来自三个图（胶子交换、夸克自能插入、胶子自能插入）：
$$\Lambda^\mu_a = \frac{g_s^3}{16\pi^2} \left[ \left( C_F + \frac{C_A}{2} \right) \frac{1}{\epsilon} \gamma^\mu T^a + \text{有限项} \right]$$

### 5.3.4 重整化常数

从发散部分提取重整化常数（MS 方案）：
$$\begin{align}
Z_3 &= 1 + \frac{g_s^2}{16\pi^2 \epsilon} \left( \frac{5}{3} C_A - \frac{4}{3} T_F N_f \right) + \mathcal{O}(g_s^4) \\
Z_2 &= 1 - \frac{g_s^2}{16\pi^2 \epsilon} C_F + \mathcal{O}(g_s^4) \\
Z_g &= 1 - \frac{g_s^2}{16\pi^2 \epsilon} \left( \frac{11}{6} C_A - \frac{2}{3} T_F N_f \right) + \mathcal{O}(g_s^4) \\
Z_m &= 1 - \frac{g_s^2}{16\pi^2 \epsilon} 3C_F + \mathcal{O}(g_s^4) \\
\tilde{Z}_3 &= 1 + \frac{g_s^2}{16\pi^2 \epsilon} \frac{C_A}{2} + \mathcal{O}(g_s^4) \\
Z_\xi &= 1 + \frac{g_s^2}{16\pi^2 \epsilon} \left( \frac{3}{2} C_A - \frac{4}{3} T_F N_f \right) + \mathcal{O}(g_s^4)
\end{align}$$

注意关系 $Z_g = Z_1 / (Z_2 Z_3^{1/2})$，其中 $Z_1$ 是夸克-胶子顶点重整化常数。

## 5.4 β函数与渐近自由

### 5.4.1 β函数定义

耦合常数的跑动由 β 函数描述：
$$\beta(g_s) = \mu \frac{\partial g_s}{\partial \mu} = -\frac{g_s^3}{16\pi^2} \left( \frac{11}{3} C_A - \frac{4}{3} T_F N_f \right) + \mathcal{O}(g_s^5)$$

对于 $SU(3)$ QCD：
$$\beta(g_s) = -\frac{g_s^3}{16\pi^2} \left( 11 - \frac{2}{3} N_f \right) + \mathcal{O}(g_s^5)$$

### 5.4.2 渐近自由

当 $N_f < 16.5$（实际上 $N_f \leq 6$）时，$\beta(g_s) < 0$，即：
- **高能（短距离）**：$g_s$ 减小，理论趋于自由（渐近自由）
- **低能（长距离）**：$g_s$ 增大，微扰论失效（红外 slavery）

这是非阿贝尔规范理论的独特性质，与阿贝尔规范理论（如 QED）的 $\beta>0$ 相反。

### 5.4.3 跑动耦合

解重整化群方程：
$$\mu \frac{d\alpha_s}{d\mu} = \beta(\alpha_s), \quad \alpha_s = \frac{g_s^2}{4\pi}$$

到一圈阶：
$$\alpha_s(\mu) = \frac{\alpha_s(\mu_0)}{1 + \frac{\alpha_s(\mu_0)}{4\pi} \beta_0 \ln(\mu^2/\mu_0^2)}$$

其中 $\beta_0 = 11 - \frac{2}{3} N_f$。定义 $\Lambda_{\text{QCD}}$：
$$\alpha_s(\mu) = \frac{4\pi}{\beta_0 \ln(\mu^2/\Lambda_{\text{QCD}}^2)}$$

$\Lambda_{\text{QCD}} \sim 200-300\text{ MeV}$ 是 QCD 能标，标志微扰论失效的尺度。

### 5.4.4 高圈修正

两圈 β 函数：
$$\beta(g_s) = -\frac{g_s^3}{16\pi^2} \beta_0 - \frac{g_s^5}{(16\pi^2)^2} \beta_1 + \mathcal{O}(g_s^7)$$

$$\beta_0 = 11 - \frac{2}{3} N_f$$
$$\beta_1 = 102 - \frac{38}{3} N_f$$

更高阶修正已计算到五圈。

## 5.5 Slavnov-Taylor 恒等式

### 5.5.1 BRST 不变性与恒等式

量子作用量的 BRST 对称性导致 Slavnov-Taylor 恒等式，是非阿贝尔规范理论中的 Ward 恒等式推广。

对于有效作用量 $\Gamma$：
$$\int d^4x \left[ \frac{\delta \Gamma}{\delta A_\mu^a} \frac{\delta \Gamma}{\delta K^{a\mu}} + \frac{\delta \Gamma}{\delta \psi} \frac{\delta \Gamma}{\delta L} + \frac{\delta \Gamma}{\delta \bar{\psi}} \frac{\delta \Gamma}{\delta \bar{L}} + \frac{\delta \Gamma}{\delta \eta^a} \frac{\delta \Gamma}{\delta N^a} + B^a \frac{\delta \Gamma}{\delta \bar{\eta}^a} \right] = 0$$

其中 $K^{a\mu}, L, \bar{L}, N^a$ 是外源，耦合到 BRST 变换的复合算符。

### 5.5.2 具体恒等式

1. **胶子传播子横性**：
   $$q_\mu \Gamma^{\mu\nu}_{ab}(q) = \xi^{-1} q^\nu \delta_{ab}$$

2. **夸克-胶子顶点**：
   $$q_\mu \Gamma^{\mu}_{a,ij}(p,p+q) = g_s T^a_{ij} [\Gamma_{ij}(p+q) - \Gamma_{ij}(p)]$$
   其中 $\Gamma_{ij}(p)$ 是夸克两点函数的逆。

3. **鬼场-胶子顶点**：
   类似关系约束鬼场顶点。

### 5.5.3 对重整化的约束

Slavnov-Taylor 恒等式要求重整化常数满足：
$$Z_1 = Z_2, \quad \tilde{Z}_1 = \tilde{Z}_3, \quad Z_{4g} = Z_g^2 Z_3^2, \quad \text{等等}$$

其中 $Z_1$ 是夸克-胶子顶点，$\tilde{Z}_1$ 是鬼场-胶子顶点，$Z_{4g}$ 是四胶子顶点常数。这些关系减少独立重整化常数的数量。

## 5.6 重整化群方程

### 5.6.1 Callan-Symanzik 方程

重整化格林函数 $\Gamma^{(n)}$ 满足：
$$\left[ \mu \frac{\partial}{\partial \mu} + \beta(g_s) \frac{\partial}{\partial g_s} - n_\psi \gamma_\psi - n_A \gamma_A - n_\eta \gamma_\eta + \gamma_m m \frac{\partial}{\partial m} \right] \Gamma^{(n)} = 0$$

其中 $\gamma_i$ 是反常维度：
$$\gamma_\psi = \frac{1}{2} \mu \frac{\partial}{\partial \mu} \ln Z_2, \quad \gamma_A = \frac{1}{2} \mu \frac{\partial}{\partial \mu} \ln Z_3, \quad \gamma_\eta = \frac{1}{2} \mu \frac{\partial}{\partial \mu} \ln \tilde{Z}_3$$

一圈计算给出：
$$\begin{align}
\gamma_\psi &= \frac{g_s^2}{16\pi^2} C_F + \mathcal{O}(g_s^4) \\
\gamma_A &= \frac{g_s^2}{16\pi^2} \left( \frac{5}{3} C_A - \frac{4}{3} T_F N_f \right) + \mathcal{O}(g_s^4) \\
\gamma_\eta &= \frac{g_s^2}{16\pi^2} \frac{C_A}{2} + \mathcal{O}(g_s^4) \\
\gamma_m &= \frac{g_s^2}{16\pi^2} 3C_F + \mathcal{O}(g_s^4)
\end{align}$$

### 5.6.2 算符乘积展开与标度无关性

重整化群方程解释了深度非弹性散射中的标度无关性破坏（Bjorken scaling violation）。算符乘积展开系数函数满足重整化群方程，其演化由反常维度矩阵决定。

## 5.7 红外发散与因子化

### 5.7.1 红外发散问题

与 QED 类似，QCD 微扰计算存在红外（软和共线）发散。但 QCD 更复杂：
1. 胶子无质量，导致更多红外发散
2. 非阿贝尔相互作用产生新的发散结构

### 5.7.2 Kinoshita-Lee-Nauenberg 定理

KLN 定理保证：对初末态所有退简并物理态求和，红外发散相消。

### 5.7.3 因子化定理

硬过程的微扰计算可以因子化为：
$$d\sigma = H \otimes f \otimes f \otimes D$$

其中：
- $H$：硬散射部分（微扰计算）
- $f$：部分子分布函数（非微扰）
- $D$：碎裂函数（非微扰）

因子化标度 $\mu_F$ 分离微扰与非微扰物理。

### 5.7.4 DGLAP 演化方程

部分子分布函数 $f_i(x,\mu_F)$ 满足 DGLAP 方程：
$$\mu_F \frac{\partial}{\partial \mu_F} f_i(x,\mu_F) = \sum_j \int_x^1 \frac{dz}{z} P_{ij}(z,\alpha_s(\mu_F)) f_j(x/z,\mu_F)$$

其中 $P_{ij}$ 是分裂函数，微扰计算可得。

## 5.8 与 QED 重整化的对比

| 特性 | QED | QCD |
|------|-----|-----|
| **β函数符号** | $\beta>0$（红外自由） | $\beta<0$（$N_f<16.5$，渐近自由） |
| **紫外行为** | 高能耦合增大 | 高能耦合减小 |
| **红外行为** | 红外安全（有电子质量） | 红外发散复杂（胶子无质量） |
| **规范群** | 阿贝尔 $U(1)$ | 非阿贝尔 $SU(3)$ |
| **自相互作用** | 无 | 有（三胶子、四胶子顶点） |
| **鬼场作用** | 可吸收为常数 | 必需，有相互作用 |
| **重整化常数关系** | $Z_1=Z_2$（Ward 恒等式） | $Z_1=Z_2$，$\tilde{Z}_1=\tilde{Z}_3$ 等（Slavnov-Taylor） |
| **物理含义** | 耦合常数跑动较弱 | 强耦合跑动，解释 confinement |

## 5.9 当前进展

现代 QCD 重整化研究包括：
1. **高圈计算**：β函数到五圈，分裂函数到三圈
2. **红外结构**：软共线有效理论（SCET）
3. **重夸克有效理论**（HQET）的重整化
4. **格点 QCD**：非微扰重整化
5. **共形对称性**：$\mathcal{N}=4$ SYM 中的可积性

QCD 重整化的成功建立了强相互作用的微扰理论基础，并与非微扰现象（如禁闭、手征对称性破缺）的研究互补。

