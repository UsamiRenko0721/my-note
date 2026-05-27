---
up:
  - "[[笔记]]"
related:
  - "[[CFT for particle physicists.pdf]]"
date: 2026-05-18
---

# 缩略语表

AdS/CFT 反德西特弯曲时空中的量子场论与少一个维度的平坦空间中共形场论之间的对应关系
CFT         共形场论
IR 红外    量子场论中低能或长距离的同义词
OPE        算子积展开（见第5章）
QCD       量子色动力学：描述夸克和胶子相互作用的强耦合理论，如粒子物理标准模型所述
QFT        量子场论（通常指非共形的）
RG          重整化群：描述量子场论如何随能标变化的框架
UV 紫外  量子场论中高能或短距离的同义词

# 第一章 引言

共形场论是现代理论物理学中无处不在的课题。每个局域量子场论在长距离和短距离极限下都会趋近于一个CFT [1]，并且通过AdS/CFT对应，它甚至在量子引力的研究中扮演着关键角色。CFT也是少数可以在微扰论框架之外研究量子场论的罕见体系之一。目前已有一些优秀的现代综述文章[1–5]，本讲义的大部分内容直接受其启发。

大多数CFT的入门课程都是将共形群作为一个整体来处理。这种方法通常需要在欧几里得空间中讨论（我们将会看到原因）[2]，而与传统量子场论的联系（如果真有联系的话）会在课程的很晚阶段才出现。这可能会让粒子物理学家感到沮丧。我们在此建议从以下定义出发：

$$
\begin{array}{l} \mathrm{CFT} = \text{相对论性 QFT} \\ + \text{标度对称性} \tag{1.1} \\ + \text{特殊共形对称性,} \\ \end{array}
$$

然后逐一探讨每个部分。第一部分是平坦闵可夫斯基时空中的量子场论。我们假设读者对此已经熟悉，但我们的关注点并不局限于那些具有良好经典极限和微扰定义的量子场论。因此，我们将在第3章回顾一些QFT的基础知识，即Wightman公理，但不过分追求数学上的严谨性。

标度对称性将是下一个讨论的主题。粒子物理学家通常通过重整化群对其也有很好的物理直觉。CFT中的主要新奇之处在于，标度对称性禁止存在具有确定质量的粒子；相反，在标度不变的理论中，存在着任意能量的态（除非在自由理论这个非常特殊的情况下）。

最后，我们将讨论特殊共形对称性。它几乎总是与标度对称性一同出现，但它的威力要强大得多。这将引导我们在第4章研究共形关联函数，在第5章讨论算子积展开（OPE）及其优良特性，并最终在第6章讨论共形自举（bootstrap），包括一个仅通过对称性原理解决的强耦合理论的例子。

在深入讨论量子理论之前，我们将在第2章从经典共形变换开始。在 $d$ 维时空中讨论是方便的，并将 $d = 4$ 视为更一般框架的一个特例。因此，洛伦兹指标 $\mu, \nu, \dots$ 的取值范围是从 $0$ 到 $d-1$，其中 $x^0$ 是矢量 $x^\mu$ 的时间分量，$p^0$ 是动量 $p^\mu$ 的能量分量。尽管我们最终关心的是闵可夫斯基时空中的酉量子场论，但我们需要建立与在平坦欧几里得空间中定义的同一理论的联系。出于这个原因，（遗憾的是）我们采用“mostly-plus”度规约定 $(-, +, +, \dots, +)$，这样从闵可夫斯基时空到欧几里得空间的转换只需通过将时间坐标在复平面内旋转即可实现。

# 第二章 经典共形变换

物理学中最基本的原理之一是参考系的独立性：处于不同位置的观测者可能有不同的视角，但基本的物理定律是相同的。这在空间（平移和旋转不变性）中成立，在时空（洛伦兹推动不变性）中也成立。

## 2.1 无穷小变换

用数学语言来说，这意味着如果我们有一个坐标系 $x^\mu$，物理定律在变换下不会改变

$$
x ^ {\mu} \rightarrow x ^ {\prime \mu}. \tag{2.1}
$$

该原理适用于所有可逆（同构）且可微（光滑变换）的映射，因此通常被称为微分同胚不变性。由于可微，变换 (2.1) 可以泰勒展开为

$$
x ^ {\mu} \rightarrow x ^ {\prime \mu} = x ^ {\mu} + \varepsilon^{\mu} (x), \tag{2.2}
$$

其中 $\varepsilon^\mu$ 是一个无穷小矢量（意味着我们总是忽略 $\varepsilon^2$ 阶的项）。

除了坐标系，描述物理系统还需要一种测量距离的方法，这由度规 $g_{\mu\nu}(x)$ 提供。距离是通过积分无穷小线元来测量的，其平方等于

$$
d s ^ {2} = g _ {\mu \nu} (x) d x ^ {\mu} d x ^ {\nu}. \tag{2.3}
$$

由于所有观测者应该对距离的度量达成一致，我们必须有

$$
g _ {\mu \nu} ^ {\prime} (x ^ {\prime}) d x ^ {\prime \mu} d x ^ {\prime \nu} = g _ {\mu \nu} (x) d x ^ {\mu} d x ^ {\nu}, \tag{2.4}
$$

这里 $g_{\mu\nu}$ 可以是欧几里得度量 $\delta_{\mu\nu}$ 或闵可夫斯基度量 $\eta_{\mu\nu}$；为简单起见，我们只考虑 $g_{\mu\nu}$ 是平坦的情况，即 $\partial_\alpha g_{\mu\nu} = 0$。在这种情况下，我们可以写出

$$
\begin{array}{l} g _ {\mu \nu} ^ {\prime} = g _ {\alpha \beta} \frac {\partial x ^ {\alpha}}{\partial x ^ {\prime \mu}} \frac {\partial x ^ {\beta}}{\partial x ^ {\prime \nu}} \\ = g _ {\alpha \beta} \left(\delta_ {\mu} ^ {\alpha} - \partial_ {\mu} \varepsilon^ {\alpha}\right) \left(\delta_ {\nu} ^ {\beta} - \partial_ {\nu} \varepsilon^ {\beta}\right) \tag{2.5} \\ = g _ {\mu \nu} - \left(\partial_ {\mu} \varepsilon_ {\nu} + \partial_ {\nu} \varepsilon_ {\mu}\right). \\ \end{array}
$$

如果我们要求不同的观测者对度规也达成一致，那么必须有 $g'_{\mu\nu} = g_{\mu\nu}$，这给出了对可能的坐标变换的约束：它们必须满足

$$
\partial_ {\mu} \varepsilon_ {\nu} + \partial_ {\nu} \varepsilon_ {\mu} = 0. \tag{2.6}
$$

该条件的最一般解为

$$
\varepsilon^ {\mu} = a ^ {\mu} + \omega_ {\nu} ^ {\mu} x ^ {\nu}, \tag{2.7}
$$

其中 $a^\mu$ 是常矢量，$\omega_{\mu\nu} = g_{\mu\rho} \omega_\nu^\rho$ 是反对称张量，即 $\omega_{\mu\nu} = -\omega_{\nu\mu}$。变换

$$
x ^ {\mu} \xrightarrow {P} x ^ {\mu} + a ^ {\mu} \tag{2.8}
$$

显然是平移，而

$$
x ^ {\mu} \stackrel {M} {\rightarrow} \left(\delta_ {\nu} ^ {\mu} + \omega_ {\nu} ^ {\mu}\right) x ^ {\nu} \tag{2.9}
$$

是绕原点 $x=0$ 的旋转/洛伦兹变换：矩阵 $R_\nu^\mu = \delta_\nu^\mu + \omega_\nu^\mu$ 满足 $R_\alpha^\mu g^{\alpha\beta} R_\beta^{T\nu} = g^{\mu\nu}$。这两种运算的复合生成了庞加莱群。这是所有相对论性量子场论基础的时空基本对称性。它在极好的近似下是自然的对称性，至少直到量子引力变得重要的能标之前都是如此。

然而，我们也可以考虑两个观测者使用不同单位制的情况，即他们对整体的标度定义有分歧，但在其他方面都认同度规是平坦的。在这种情况下，我们必须有 $g'_{\mu\nu} \propto g_{\mu\nu}$，因此约束 (2.5) 变为

$$
\partial_ {\mu} \varepsilon_ {\nu} + \partial_ {\nu} \varepsilon_ {\mu} = 2 \lambda g _ {\mu \nu}, \tag{2.10}
$$

其中 $\lambda$ 是某个正实数，其最一般的解为

$$
\varepsilon^ {\mu} = a ^ {\mu} + \omega_ {\nu} ^ {\mu} x ^ {\nu} + \lambda x ^ {\mu}. \tag{2.11}
$$

新的无穷小变换是

$$
x ^ {\mu} \xrightarrow {D} (1 + \lambda) x ^ {\mu}. \tag{2.12}
$$

这是一个标度变换，也称为 dilatation。需要注意的是，标度对称性不是自然的一个好的对称性：存在一个所有观测者必须认同的基本能标（例如，可以选择为电子的质量）。尽管如此，仍有一些系统将其作为非常好的近似对称性，值得研究。

如果进一步推进这个逻辑，在一个标度不变的世界里，观测者没有物理手段来认同一个基本标度，他们甚至可能决定在移动时或随时间改变其标度的定义。这将对应于这样一种情况：一个观测者的度规 $g'_{\mu\nu}$ 可以通过一个时空函数与原始度规 $g_{\mu\nu}$ 相差一个因子：

$$
g _ {\mu \nu} ^ {\prime} (x) = \Omega (x) g _ {\mu \nu}. \tag{2.13}
$$

注意，我们并不是说 $g'_{\mu\nu}$ 是完全任意的：在时空的每一点，它通过一个标度变换与平坦度规相关。但标度因子在每一点都不同。$\varepsilon^\mu$ 的条件在这种情况下变为

$$
\partial_ {\mu} \varepsilon_ {\nu} + \partial_ {\nu} \varepsilon_ {\mu} = 2 \sigma g _ {\mu \nu}, \tag{2.14}
$$

其中 $\sigma$ 是 $\Omega$ 的无穷小版本，通常关系为 $\Omega(x) = e^{-2\sigma(x)} \approx 1 - 2\sigma(x)$。为了找到该方程的最一般解，注意用 $g^{\mu\nu}$ 缩并指标得到

$$
\partial_ {\mu} \varepsilon^ {\mu} = d \sigma , \tag{2.15}
$$

其中 $d$ 是时空维度，而作用 $\partial^\nu$ 得到

$$
\partial_ {\mu} \partial_ {\nu} \varepsilon^ {\nu} + \partial^ {2} \varepsilon_ {\mu} = 2 \partial_ {\mu} \sigma , \tag{2.16}
$$

所以我们得到

$$
\partial^ {2} \varepsilon_ {\mu} = (2 - d) \partial_ {\mu} \sigma . \tag{2.17}
$$

再次作用 $\partial^\mu$，我们得到

$$
(d - 1) \partial^ {2} \sigma = 0, \tag{2.18}
$$

而作用 $\partial^\nu$ 并对称化指标得到

$$
(2 - d) \partial_ {\mu} \partial_ {\nu} \sigma = g _ {\mu \nu} \partial^ {2} \sigma . \tag{2.19}
$$

因此，在所有维度 ($d > 1$) 中都必须满足条件 $\partial^2\sigma = 0$，并且在 $d > 2$ 中还需要满足附加条件 $\partial_\mu\partial_\nu\sigma = 0$，其解为

$$
\sigma (x) = \lambda + 2 b \cdot x. \tag{2.20}
$$

相应的 $\varepsilon^\mu$ 值为

$$
\varepsilon^ {\mu} = a ^ {\mu} + \omega_ {\nu} ^ {\mu} x ^ {\nu} + \lambda x ^ {\mu} + 2 (b \cdot x) x ^ {\mu} - x ^ {2} b ^ {\mu}. \tag{2.21}
$$

因此，除了之前发现的变换外，我们还有

$$
x ^ {\mu} \stackrel {K} {\rightarrow} x ^ {\mu} + 2 (b \cdot x) x ^ {\mu} - x ^ {2} b ^ {\mu}, \tag{2.22}
$$

这被称为特殊共形变换。检查此变换的雅可比矩阵，我们得到

$$
\frac {\partial x ^ {\prime \mu}}{\partial x ^ {\nu}} = (1 + 2 b \cdot x)   \delta_ {\nu} ^ {\mu} + 2   (b _ {\nu} x ^ {\mu} - x _ {\nu} b ^ {\mu}) \approx (1 + 2 b \cdot x)   R _ {\nu} ^ {\mu} (x). \tag{2.23}
$$

我们将其写为一个与位置相关的标度因子 $(1 + 2b\cdot x)$ 乘以一个正交矩阵

$$
R _ {\nu} ^ {\mu} (x) = \delta_ {\nu} ^ {\mu} + 2 \left(b _ {\nu} x ^ {\mu} - x _ {\nu} b ^ {\mu}\right). \tag{2.24}
$$

这表明，特殊共形变换局部地起着标度变换和旋转（或洛伦兹变换）的复合作用。这也表明共形变换保持角度不变，这也是其名称的由来。方程 (2.14) 被称为共形 Killing 方程，其解 (2.21) 被称为 Killing 矢量。

注意，在我们的推导中，原始度规 $g_{\mu\nu}$ 是平坦的，但新度规 $g'_{\mu\nu}$ 则不是。然而，它是共形平坦的：总是可以通过坐标变换使其再次平坦。通常，变换

$$
g _ {\mu \nu} (x) \rightarrow \Omega (x) g _ {\mu \nu} (x) \tag{2.25}
$$

被称为 Weyl 变换。它们改变了时空的几何。我们发现，最多为 $x$ 的二次函数的 Weyl 变换可以通过坐标变换来补偿，以回到平坦空间。相应的平坦空间变换称为共形变换。

在 $d=2$ 时，情况略有不同：条件 $\partial^2\sigma = 0$ 足以保证 Killing 方程有解。这在使用光锥坐标时最容易看出，

$$
x ^ {+} = \frac {x ^ {0} + x ^ {1}}{2}, \quad x ^ {-} = \frac {x ^ {0} - x ^ {1}}{2}, \tag{2.26}
$$

在此坐标系下

$$
\partial^ {2} \sigma = \partial_ {+} \partial_ {-} \sigma . \tag{2.27}
$$

## 2.2 共形代数

这通过取 $\sigma$ 为坐标 $x^+$ 的任意函数和 $x^-$ 的另一个任意函数之和来满足。事实上，如果我们写 $\varepsilon^\pm = \varepsilon^0 \pm \varepsilon^1$，我们可以取任意函数 $\varepsilon^+(x^+)$ 和 $\varepsilon^-(x^-)$，并验证方程 (2.14) 被满足，其中 $\sigma = \frac{1}{2}(\partial_+ \varepsilon_+ + \partial_- \varepsilon_-)$。在欧几里得空间中，我们定义

$$
z = \frac {x ^ {1} + i x ^ {2}}{2}, \quad \bar {z} = \frac {x ^ {1} - i x ^ {2}}{2}, \tag{2.28}
$$

它们互为复共轭，同样的逻辑也成立：我们可以对 $z$ 和 $\bar{z}$ 应用任意的全纯和反全纯变换，共形 Killing 方程总是被满足。这表明，在 $d=2$ 时，共形变换比 $d>2$ 时多得多（实际上是无限多），并且也表明在 $d=2$ 时，欧几里得和闵可夫斯基共形变换之间没有显著差异，因为变换本质上独立地作用于两个光锥/全纯坐标。

共形 Killing 方程 (2.21) 确定了无穷小共形变换的最一般形式。有限共形变换可以通过一系列无穷小变换得到。然而，必须记住，无穷小共形变换是不对易的：例如，先平移再旋转与相反顺序的结果不同。共形变换形成一个群：共形变换的复合仍然是共形变换。

正如我们从量子场论中所知，一个群由其生成元及其对易关系（代数）来表征。生成元 $G$ 描述了某个方向的无穷小变换，有限变换通过指数化 $e^{i\theta G}$ 获得，参数为 $\theta$（因子 $i$ 是物理学家的惯例，使生成元成为厄米的）。共形群的一个表示可以从坐标的光滑函数 $f(x)$ 获得。例如，在无穷小平移下，我们有

$$
f (x) \stackrel {P} {\rightarrow} f (x ^ {\prime}) = f (x + a) \approx f (x) + a ^ {\mu} \partial_ {\mu} f (x) \tag{2.29}
$$

并且我们要求它等于 $e^{-i a_\mu P^\mu} f(x)$，这意味着

$$
P _ {\mu} = i \partial_ {\mu}. \tag{2.30}
$$

对方程 (2.21) 中给出的其他无穷小变换进行类似分析，我们得到其他生成元[2]

旋转/洛伦兹变换： $\qquad M ^ {\mu \nu} = i ( x ^ { \mu } \partial ^ { \nu } - x ^ { \nu } \partial ^ { \mu } )$ (2.31)

标度变换： $D = i x ^ { \mu } \partial _ { \mu } ,$ (2.32)

特殊共形变换： $K ^ { \mu } = i \left( 2 x ^ { \mu } x ^ { \nu } \partial _ { \nu } - x ^ { 2 } \partial ^ { \mu } \right) .$ (2.33)

生成元的数量与 Killing 矢量的数量相匹配：有 $d$ 个平移，$d$ 个特殊共形变换，$d(d-1)/2$ 个旋转/洛伦兹变换 ($M^{\mu\nu}$ 是一个 $d\times d$ 反对称矩阵)，以及一个标度变换。因此，该生成元的总数，即该群的维数，是 $(d+1)(d+2)/2$。在 $d=4$ 维时空中，共形群有 15 个生成元。

使用上述定义，可以验证以下对易关系成立：

$$
\begin{array}{l} \left[ M ^ {\mu \nu}, M ^ {\rho \sigma} \right] = - i (g ^ {\mu \rho} M ^ {\nu \sigma} - g ^ {\mu \sigma} M ^ {\nu \rho} - g ^ {\nu \rho} M ^ {\mu \sigma} + g ^ {\nu \sigma} M ^ {\mu \rho}) \\ \left[ M ^ {\mu \nu}, P ^ {\rho} \right] = - i (g ^ {\mu \rho} P ^ {\nu} - g ^ {\nu \rho} P ^ {\mu}) \\ \left[ M ^ {\mu \nu}, K ^ {\rho} \right] = - i \left(g ^ {\mu \rho} K ^ {\nu} - g ^ {\nu \rho} K ^ {\mu}\right) \tag{2.34} \\ \left[ D, P ^ {\mu} \right] = - i P ^ {\mu} \\ \left[ D, K ^ {\mu} \right] = i K ^ {\mu} \\ \left[ P ^ {\mu}, K ^ {\nu} \right] = 2 i (g ^ {\mu \nu} D - M ^ {\mu \nu}) \\ \end{array}
$$

而所有其他对易子为零：

$$
\left[ M ^ {\mu \nu}, D \right] = \left[ P ^ {\mu}, P ^ {\nu} \right] = \left[ K ^ {\mu}, K ^ {\nu} \right] = 0. \tag{2.35}
$$

方程 (2.34) 中的前两个关系是熟悉的庞加莱代数。下一个关系表明 $K^\mu$ 像一个矢量一样变换（正如 $P^\mu$ 一样），而 $D$ 显然是一个标量。接下来的两个关系提醒我们，$K^\mu$ 和 $P^\mu$ 分别具有长度和长度倒数的量纲。

尽管不是一目了然，但如果 $g^{\mu\nu}$ 是欧几里得度规，则该代数同构于群 $SO(d+1,1)$ 的代数；如果是闵可夫斯基度规，则同构于 $SO(d,2)$ 的代数。为了看出这一点，让我们引入一个 $(d+2)$ 维空间，坐标为

$$
X ^ {\mu}, \quad X ^ {d + 1}, \quad X ^ {d + 2}, \tag{2.36}
$$

并由线元定义度规

$$
d s ^ {2} = g _ {\mu \nu} d X ^ {\mu} d X ^ {\nu} + d X ^ {d + 1} d X ^ {d + 1} - d X ^ {d + 2} d X ^ {d + 2} \equiv \eta_ {M N} d X ^ {M} d X ^ {N}. \tag{2.37}
$$

其中 $X^{d+1}$ 新定义的空间坐标，而 $X^{d+2}$ 是新定义的时间坐标。于是就像我们定义洛伦兹代数一样，我们能定义共形对易关系

$$[J^{MN},J^{RS}] = -i(\eta^{MR}J^{NS} - \eta^{MS}J^{NR} - \eta^{NR}J^{MS} + \eta^{NS}J^{MR}) \tag{2.38}$$

我们只需要如下的定义即可很容易得到这些对易关系：

$$\begin{align}
M^{\mu \nu} & = J^{\mu \nu} \\
P^{\mu} & = J^{\mu,d+1} + J^{\mu,d+2} \\
K^{\mu} & = J^{\mu,d+1} - J^{\mu,d+2} \\
D & = J^{d+1,d+2}
\end{align} \tag{2.39}$$


## 2.3 有限变换

我们刚刚看到无穷小共形变换生成一个群。但是我们如何描述有限共形变换呢？让我们看看每个生成元如何指数化为群的一个元素；最一般的共形变换可以通过这些有限变换的复合得到。

在某些情况下，指数化是平凡的。例如，对于平移，我们立即得到

$$
x ^ {\mu} \xrightarrow {P} x ^ {\mu} + a ^ {\mu}, \tag{2.40}
$$

其中 $a$ 现在可以是任意 $d$ 维矢量，不一定很小。标度变换也是如此，

$$
x ^ {\mu} \xrightarrow {D} \lambda x ^ {\mu} \tag{2.41}
$$

其中 $\lambda$ 是有限的。旋转或洛伦兹变换指数化为

$$
x ^ {\mu} \stackrel {M} {\rightarrow} \Lambda_ {\nu} ^ {\mu} x ^ {\nu} \tag{2.42}
$$

其中 $\Lambda_\nu^\mu$ 是 $SO(d)$ 或 $SO(1,d-1)$ 矩阵，取决于度规是欧几里得还是闵可夫斯基。这些都是量子场论中的标准内容。

相反，特殊共形变换的指数化并不平凡。推导其有限形式的最简单方法是进行以下观察：回顾无穷小形式我们有

$$
x ^ {\prime \mu} = x ^ {\mu} + 2 (b \cdot x) x ^ {\mu} - x ^ {2} b ^ {\mu}, \tag{2.43}
$$

这意味着 $x^{\prime 2} = (1 + 2b\cdot x) x^2$，因此（总是忽略 $b^2$ 阶项）

$$
\frac {x ^ {\prime \mu}}{x ^ {\prime 2}} = \frac {x ^ {\mu}}{x ^ {2}} - b ^ {\mu}. \tag{2.44}
$$

出现在方程两边的比值 $x^\mu/x^2$ 是坐标 $x^\mu$ 的逆，分别对应 $x'^\mu$：反演变换定义为

$$
x ^ {\mu} \xrightarrow {I} \frac {x ^ {\mu}}{x ^ {2}}. \tag{2.45}
$$

这个变换没有无穷小形式，但除此之外，它拥有共形变换的基本性质：其雅可比矩阵为

$$
\frac {\partial x ^ {\prime \mu}}{\partial x ^ {\nu}} = \frac {1}{x ^ {2}} \left[ \delta_ {\nu} ^ {\mu} - 2 \frac {x ^ {\mu} x _ {\nu}}{x ^ {2}} \right], \tag{2.46}
$$

它是一个与位置相关的标度因子 $(x^{-2})$ 与一个正交矩阵的乘积。要理解这个变换的全局行为，考虑一个欧几里得点 $\vec{x} = (a, 0, \ldots 0) \in \mathbb{R}^d$。那么方括号中的矩阵是对角的，等于 $\operatorname{diag}(-1,1,\dots,1)$。这是一个行列式为 $1$ 的正交矩阵，是 $O(d)$ 的一部分，但不是 $SO(d)$ 的一部分。这表明反演是一个不连通到恒等元的离散变换。一个共形不变的理论可能在反演下不变，但不是必须的。

方程 (2.44) 表明，无穷小特殊共形变换可以通过先进行反演，然后平移，再进行反演得到。由于这个过程涉及两次反演，并且反演是其自身的逆，因此反演是否为系统的真实对称性并不重要。这种表示的优势在于它可以轻松指数化：（无限多）无穷小特殊共形变换的复合可以写为一次反演，接着一次有限平移，然后再一次反演。换句话说，方程 (2.44) 对有限的 $b^\mu$ 也成立。这可以用来证明

$$
x ^ {\mu} \xrightarrow {K} x ^ {\prime \mu} = \frac {x ^ {\mu} - x ^ {2} b ^ {\mu}}{1 - 2 b \cdot x + b ^ {2} x ^ {2}}. \tag{2.47}
$$

**练习 2.1** 使用方程 (2.44) 推导出 (2.47)。

特殊变换在全局上做了什么？让我们具体看看欧几里得空间。有一些特殊点：

- 坐标系原点 $x=0$ 映射到自身。
- 点 $b^\mu/b^2$ 映射到 $\infty$。
- 反之，“点” $x \to \infty$ 映射到有限值 $-b^\mu/b^2$。

这些性质可以从特殊共形变换和平移通过反演相关联这一事实来理解：特殊共形变换保持原点固定，但移动所有其他点，包括 $\infty$；平移移动除 $\infty$ 外的所有点。另外两种变换，旋转和标度变换，同时保持 $0$ 和 $\infty$ 固定。

共形变换的一个基本性质是它们允许我们将任意三点 $(x_1, x_2, x_3)$ 映射到另一个三元组 $(x_1', x_2', x_3')$。这可以通过以下步骤看出：首先，应用平移将 $x_1$ 放在原点，然后应用一个特殊共形变换将 $x_3$ 送到 $\infty$，之后原始三元组的像为 $(0, x_2'', \infty)$；然后使用旋转和标度变换将 $x_2''$ 移动到另一点 $x_2'''$，同时保持 $0$ 和 $\infty$ 固定；最后再次应用一个特殊共形变换将其送到 $x_3' - x_1'$，再通过平移 $x_1'$ 到达 $(x_1', x_2', x_3')$ 的构型。这个性质有一个直接的物理结果：在涉及 2 个或 3 个局域算子的关联函数中，所有运动学都由共形对称性固定。唯一的自由度在于算子本身，而不是它们在空间中的位置。

共形变换的另一个有趣性质是它们将球面映射为球面：这对于平移、旋转和标度变换是显而易见的，但对于特殊共形变换也成立。

**练习 2.2** 证明在特殊共形变换 (2.47) 下，中心在 $a^\mu$、半径为 $R$ 的球面被映射到中心在

$$
a ^ {\prime \mu} = \frac {a ^ {\mu} - (a ^ {2} - R ^ {2}) b ^ {\mu}}{1 - 2 a \cdot b + (a ^ {2} - R ^ {2}) b ^ {2}}
$$

半径为

$$
R ^ {\prime} = \frac {R}{\left| 1 - 2 a \cdot b + (a ^ {2} - R ^ {2}) b ^ {2} \right|}
$$

的球面。在特殊情况 $b^\mu/b^2$ 位于原始球面上时，证明该球面被映射到一个垂直于矢量 $a^\mu + (R^2 - a^2)b^\mu$ 的平面。注意，平面是半径无穷大的球面。

在 $d=2$ 时，额外的共形变换（有无穷多个！）意味着（几乎）任何形状都可以映射到另一个形状。这被称为黎曼映射定理。

## 2.4 紧致化

我们之前提到，共形对称性是平坦时空的对称性。确实，正如我们所见，只要将点 $\infty$ 视为空间的一部分，这一点就成立。这在欧几里得空间中相当直接，但在闵可夫斯基时空中则微妙得多，因为到达 $\infty$ 有不同的、不等价的方式。

为了更好地理解这一点，将平坦欧几里得空间 $\mathbb{R}^d$ 或闵可夫斯基时空 $\mathbb{R}^{1,d-1}$ 映射到一个弯曲流形上是很有用的。在欧几里得空间中，这可以通过（逆）球极投影实现，它将 $\mathbb{R}^d \cup \{\infty\}$ 映射到单位球面 $S^d$ 上。几何上，球极投影的构造如下（见图 2.1）：将 $\mathbb{R}^d$ 作为平面嵌入 $\mathbb{R}^{d+1}$ 中，连同中心在原点的单位球面。平面上的每个点都有一个球面上的像，通过连接原点和球面北极的线段，并记下它与球面的交点。原点映射到南极，$\infty$ 映射到北极，单位半径的球面 $S^{d-1}$ 映射到赤道。代数上，这可以通过以下方式实现：首先用球坐标写出欧几里得度规，

$$
d s ^ {2} = d r ^ {2} + r ^ {2} d \Omega_ {d-1} ^ {2}, \tag{2.48}
$$

其中在 $d=2$ 时立体角由 $d\Omega_1^2 = d\phi^2$ 给出，在 $d=3$ 时由 $d\Omega_2^2 = d\theta^2 + \sin\theta^2 d\phi^2$ 给出，更一般地由递推关系 $d\Omega_n^2 = d\theta^2 + \sin\theta^2 d\Omega_{n-1}^2$ 给出。让我们进行变量替换

$$
r = \frac {\sin \varphi}{1 - \cos \varphi}, \tag{2.49}
$$

并将 $\varphi \in [0, \pi]$ 解释为球面上的极角：$\varphi = 0$ 是北极，对应 $r \to \infty$，$\varphi = \pi$ 是南极，对应 $r=0$。在这些坐标下，我们有

![图 2.1 欧几里得空间 $\mathbb{R}^d$（此处表示为水平面）到球面 $\mathcal{S}^d$ 的逆球极投影，两者都嵌入 $\mathbb{R}^{d+1}$ 中。点 $x$ 满足 $|x|>1$ 被映射到北半球；点 $x'$ 满足 $|x'|<1$ 被映射到南半球；原点映射到南极 (S)，$\infty$ 映射到北极 (N)](image-link)

$$
d s ^ {2} = \frac {1}{(1 - \cos \varphi) ^ {2}} \left(d \varphi^ {2} + \sin \varphi^ {2} d \Omega_ {d-1} ^ {2}\right) = \frac {1}{(1 - \cos \varphi) ^ {2}} d \Omega_ {d} ^ {2}. \tag{2.50}
$$

新度规是平坦的，只是乘了一个依赖于 $\varphi$ 的整体 Weyl 因子。在这些坐标下，共形变换总是非奇异的。因此，通常在球面 $S^d$ 上研究经典共形变换比在欧几里得空间更方便。

然而，在量子理论中，如果希望沿着某个优选方向对空间进行分层，这种紧致化就不那么好了：如果选择 $\varphi$ 作为“欧几里得时间”，那么“空间”方向是一个球面 $S^{d-1}$，其体积依赖于 $\varphi$。换句话说，“时间”平移的生成元不是系统的对称性。球面上任何其他时间方向的选择也是如此。

相反，另一种紧致化通常比球面更受欢迎：从球坐标下的欧几里得度规出发，我们可以进行变量替换

$$
\tau = \log (r) \quad \Leftrightarrow \quad r = e ^ {\tau}, \tag{2.51}
$$

之后得到

$$
d s ^ {2} = e ^ {2 \tau} \left(d \tau^ {2} + d \Omega_ {d-1} ^ {2}\right). \tag{2.52}
$$

这又是一个平坦度规，只是乘了一个 Weyl 因子 $r^2 = e^{2\tau}$。然而，在这种情况下，重新标度后的度规与 $\tau$ 无关。这个空间具有圆柱体的几何形状：$\mathbb{R} \times S^{d-1}$。它不是完全紧致的：$\tau$ 从 $-\infty$ 到 $+\infty$。但它有一个重要的优点：$\tau$ 方向的平移由 dilatation $D$ 生成，这将被视为量子理论的一个对称性。将空间分层为常 $\tau$ 的曲面，将在后续的共形场论中引导我们进行径向量子化。

注意，在 $SO(d+1,1)$ 语言中，生成元 $D = J^{d+1,d+2}$ 与其他生成元 $J^{\mu,d+2} = \frac{1}{2}(P^\mu - K^\mu)$ 完全等价，因为它们通过 $SO(d+1)$ 旋转相关联。因此，我们也可以寻找一种圆柱体紧致化，其中非紧致方向对应于由 $\frac{1}{2}(P^0 - K^0)$ 生成的变换。这个生成元组合满足

$$
\frac {1}{2} \left(P ^ {0} - K ^ {0}\right) = i \left(\frac {1 - (x ^ {0}) ^ {2} + \vec {x} ^ {2}}{2} \partial_ {0} - x ^ {0} \vec {x} \cdot \vec {\partial}\right), \tag{2.53}
$$

有两个不动点位于 $x^0 = \pm 1$ 且 $\vec{x} = 0$。由这个生成元线性组合生成的时空分层被称为 N-S 量子化[3]，将在第 5 章讨论。图 2.2 展示了由 $D$ 和 $\frac{1}{2}(P^0 - K^0)$ 分层的欧几里得空间的两种方式，相应的圆柱体解释如图 2.3 所示。

![图 2.2 欧几里得空间的分层（此处 $d=2$），左图为径向量子化，右图为 N-S 量子化。相同颜色的圆通过共形变换相互映射。特别地，N-S 量子化中的平面 $x^0=0$ 被映射到径向量子化中的单位球面](image-link)

![图 2.3 左图：对应径向坐标 (2.52) 的欧几里得圆柱体，非紧致方向的演化由标度变换生成元 $D$ 给出；蓝色圆圈对应单位球面。中图：经过共形变换后的同一欧几里得圆柱体，演化由 $\frac{1}{2}(P^0 - K^0)$ 给出；蓝色圆圈现在是平面 $x^0=0$，包含原点和无穷远点。右图：洛伦兹圆柱体，通过对 $x^0$ 进行 Wick 旋转得到，曲面 $x^0=0$ 保持不变；该曲面在由 $P^0$ 生成的时间平移下的像是庞加莱片，显示为圆柱体表面的蓝色菱形；只有特殊共形变换才能将点从庞加莱片内部移动到外部](image-link)

**练习 2.3** 找出使欧几里得度规 Weyl 等价于一个圆柱体的坐标变换，其中非紧致方向的平移由 $\frac{1}{2}(P^0 - K^0)$ 生成。
提示：找到一个特殊共形变换后接一个平移，将 $(0,\infty)$ 映射到 $(1,1)$，并将其应用于径向坐标。

欧几里得空间的圆柱体紧致化本身就很有趣，而且对于理解欧几里得和闵可夫斯基时空之间的联系也极为方便：在这种最后的形式下，进行 Wick 旋转 $\tau \to -i t$ 定义了一个圆柱体，洛伦兹共形群 $SO(d,2)$ 自然作用其上。但在我们深入探讨之前，让我们回到平坦的闵可夫斯基时空，做一些一般性的评论。

## 2.5 闵可夫斯基时空

闵可夫斯基时空中的平移和洛伦兹变换是熟悉的，甚至 dilatation 也是重整化群分析中的标准工具。但是共形变换做了什么？

为了理解这一点，让我们将一个观测者放在闵可夫斯基时空的原点。这个观测者的存在破缺了平移，但不破缺洛伦兹变换（假设观测者是点状的），也不破缺 dilatation 或特殊共形变换。对观测者来说，时空被分为三个区域：未来光锥、过去光锥和一个类空区域，观测者对此一无所知。洛伦兹和标度变换保持这种因果结构：未来和过去光锥映射到自身。换句话说，如果一个点 $x$ 与观测者类空隔开，那么无论选择何种洛伦兹参考系或长度定义，它都将保持类空隔开。不失一般性，选择这个点的位置为 $x = (0, \vec{n})$，其中 $n$ 是单位矢量（可以选择单位使得这是成立的）。现在应用一个参数为 $b^\mu = (-\alpha, \alpha \vec{n})$ 的特殊共形变换，其中 $\alpha$ 在 $0$ 和 $1$ 之间变化。这在时空中画出一条曲线 $y^\mu$，由 $\alpha$ 参数化，满足

$$
y ^ {0} (\alpha) = \frac {\alpha}{1 - 2 \alpha}, \quad \vec {y} (\alpha) = \frac {1 - \alpha}{1 - 2 \alpha} \vec {n}. \tag{2.54}
$$

这条曲线从类空点 $y = (0, \vec{n})$ 开始，结束于过去光锥上的点 $y = (-1, \vec{0})$。注意 $y$ 从未穿过光锥：除非 $x$ 本身是类光的，否则在特殊共形变换下 $x$ 的像永远不会是类光的，因为 $x^{\prime 2} = x^2 / (1 - 2x\cdot b + x^2 b^2)$。相反，我们有

$$
y ^ {2} (\alpha) = \frac {1}{1 - 2 \alpha} \neq 0. \tag{2.55}
$$

实际发生的情况是，该点一直行进到 $\alpha = 1/2$ 处的类光无穷远，然后从过去无穷远返回。显然，特殊共形变换破坏了因果律！

这个谜题的解决方法是，共形变换并非直接作用于闵可夫斯基空间，而是作用于其通用覆盖空间，该空间同构于图 2.3 中描述的洛伦兹圆柱体。该圆柱体上的演化由哈密顿量 $H = \frac{1}{2}(P^0 - K^0)$ 给出，但这不同于由 $P^0$ 生成的闵可夫斯基时间演化。在洛伦兹圆柱体的任意一个切片上，空间是紧致化的，使得无穷远距离的概念是明确的：类光无穷远对应于球面上的一个点，与原点的对径点。如果取该球面上的任何其他点，并使用生成元 $P^\mu$ 施加有限平移，则定义了一个紧致的庞加莱片。整个洛伦兹圆柱体是庞加莱片的拼凑，但每个局域观测者只能访问其中一个[4]。

我们必须吸取的教训是，在闵可夫斯基时空中只能使用特殊共形变换的无穷小形式：任何有限特殊共形变换都会将时空的一部分带入圆柱体上的另一个片。这有时被称为弱共形不变性。

## 2.6 经典场论中的共形对称性

到目前为止，我们只讨论了坐标的共形变换。下一步是考虑一个内禀具有共形对称性的场论（目前是经典的）。最简单的例子是自由无质量标量场，由作用量定义

$$
S = \int d ^ {d} x \left[ - \frac {1}{2} \partial_ {\mu} \phi \partial^ {\mu} \phi \right]. \tag{2.56}
$$

我们将在下一节看到，在 CFT 中，作用量原理实际上可以被放弃，但目前它是一个方便的起点。

在此背景下，共形变换是场的变换。可以采取两种不同但互补的观点。通常，将度规张量本身视为一个场，并将共形变换定义为场的（与位置相关的）标度变换

$$
\phi (x) \rightarrow e ^ {\Delta \sigma (x)} \phi (x), \tag{2.57}
$$

结合度规的 Weyl 变换

$$
g _ {\mu \nu} (x) \rightarrow e ^ {2 \sigma (x)} g _ {\mu \nu} (x). \tag{2.58}
$$

$\Delta$ 是场 $\phi$ 的标度维度。在自由理论中，它与以能量为单位（长度单位的倒数）的场的维度一致，即

$$
\Delta = \frac {d - 2}{2}. \tag{2.59}
$$

$\sigma(x)$ 是一个无穷小标度因子，满足 $\partial_\mu\partial_\nu\sigma = 0$。这种观点的优点是共形变换是场的简单乘法变换。缺点是需要将理论视为在弯曲时空中。这意味着作用量 (2.56) 中隐含的度规必须明确写出，而且作用量可以补充一个依赖于标量曲率张量 $R$ 的项，如

$$
S = \int d ^ {d} x \sqrt {| g |} \left[ - \frac {1}{2} g ^ {\mu \nu} \partial_ {\mu} \phi \partial_ {\nu} \phi + \alpha R \phi^ {2} \right]. \tag{2.60}
$$

由于 $R$ 在平坦空间中为零，看起来这个附加项可以以任意系数 $\alpha$ 出现而不改变原始的平坦空间作用量，但事实并非如此。

**练习 2.4** 验证存在一个唯一的 $\alpha$ 值使得该作用量在无穷小共形变换 (2.57) 和 (2.58) 下不变。这个值是多少？

出于这个原因，考虑相反的观点也很方便，即共形变换是动力学场和坐标的变换，而不是度规的变换。在这种情况下，共形变换可以定义为

$$
\phi (x) \rightarrow e ^ {\Delta \sigma (x)} \phi (x + \varepsilon), \tag{2.61}
$$

其中参数 $\sigma$ 和 $\varepsilon$ 通过共形 Killing 方程 (2.14) 相关联，即 $\sigma = \frac{1}{d} \partial_\mu \varepsilon^\mu$。在无穷小形式下，此变换变为

$$
\phi (x) \rightarrow \left[ 1 + \frac {d - 2}{2 d} (\partial_ {\nu} \varepsilon^ {\nu}) + \varepsilon^ {\nu} \partial_ {\nu} \right] \phi (x). \tag{2.62}
$$

**练习 2.5** 证明在变换 (2.62) 下，自由标量场的拉格朗日量

$$
\mathcal {L} = - \frac {1}{2} \partial_ {\mu} \phi \partial^ {\mu} \phi ,
$$

被平移了一个总导数项

$$
\delta \mathcal {L} = \partial_ {\mu} \left(- \frac {1}{2} \varepsilon^ {\mu} \partial_ {\nu} \phi \partial^ {\nu} \phi - \frac {d - 2}{2 d} \partial_ {\nu} \varepsilon^ {\nu} \phi \partial^ {\mu} \phi\right),
$$

从而证明这是作用量的一个对称性。你需要用到 $\varepsilon$ 至多是 $x$ 的二次函数这一事实。

注意，庞加莱对称性是此变换的特例，对应于常数的 $\varepsilon$（因此 $\sigma=0$）。

根据诺特定理，每当作用量在场变换下不变

$$
\phi \rightarrow \phi + \delta_ {\varepsilon} \phi , \tag{2.63}
$$

即拉格朗日量变化一个总导数项时，

$$
\mathcal {L} \rightarrow \mathcal {L} + \partial_ {\mu} \Lambda_ {\varepsilon} ^ {\mu}, \tag{2.64}
$$

那么存在一个守恒流

$$
J _ {\varepsilon} ^ {\mu} = \Lambda_ {\varepsilon} ^ {\mu} - \frac {\partial \mathscr {L}}{\partial (\partial_ {\mu} \phi)} \delta_ {\varepsilon} \phi . \tag{2.65}
$$

在我们的例子中，这个守恒流是

$$
J _ {\varepsilon} ^ {\mu} = \varepsilon_ {\nu} \left(\partial^ {\mu} \phi \partial^ {\nu} \phi - \frac {1}{2} g ^ {\mu \nu} \partial_ {\rho} \phi \partial^ {\rho} \phi\right) \equiv \varepsilon_ {\nu} T _ {c} ^ {\mu \nu}. \tag{2.66}
$$

右边的二阶张量称为正则能动张量。它的散度满足

$$
\partial_ {\nu} T _ {c} ^ {\mu \nu} = \partial^ {\mu} \phi \partial^ {2} \phi , \tag{2.67}
$$

因此对于自由场，由运动方程 $\partial^2\phi = 0$ 可知其为零。这意味着对于常数 $\varepsilon$，诺特流 (2.66) 是守恒的。相反，如果 $\varepsilon$ 依赖于空间（时间），那么我们有

$$
\partial_ {\mu} J _ {\varepsilon} ^ {\mu} = (\partial_ {\nu} \varepsilon_ {\mu}) T _ {c} ^ {\mu \nu}. \tag{2.68}
$$

在我们的例子中，正则能动张量对其指标 $\mu$ 和 $\nu$ 是对称的，因此我们可以写出

$$
\partial_ {\mu} J _ {\varepsilon} ^ {\mu} = \frac {1}{2} (\partial_ {\mu} \varepsilon_ {\nu} + \partial_ {\nu} \varepsilon_ {\mu}) T _ {c} ^ {\mu \nu} = \sigma g _ {\mu \nu} T _ {c} ^ {\mu \nu} = - \frac {d - 2}{2} \sigma \partial_ {\mu} \phi \partial^ {\mu} \phi . \tag{2.69}
$$

在维度 $d > 2$ 时，只有当 $\sigma = 0$ 时该流才守恒。这令人惊讶，因为我们刚刚证明了标度和特殊共形变换也是作用量的对称性，那么为什么诺特流不守恒呢？

原因是上面给出的诺特定理形式并不直接适用于与时空相关的参数 $\varepsilon$ 的情况。事实上，在这个例子中我们计算的能动张量不是唯一的：总可以给它加上一项正比于

$$
\left(\partial^ {\mu} \partial^ {\nu} - g ^ {\mu \nu} \partial^ {2}\right) \phi^ {2}, \tag{2.70}
$$

这不会影响守恒方程 (2.67)，但会改变其迹的值。组合

$$
T ^ {\mu \nu} = T _ {c} ^ {\mu \nu} + \frac {d - 2}{2 (d - 1)} \left(\partial^ {\mu} \partial^ {\nu} - g ^ {\mu \nu} \partial^ {2}\right) \phi^ {2} \tag{2.71}
$$

例如，在任何 $d$ 中都是无迹的。事实证明，在具有共形对称性的场论中，总是可以构造一个能动张量，它具有以下性质：

- 对称的 ($T^{\mu\nu} = T^{\nu\mu}$)，
- 无迹的 ($g_{\mu\nu} T^{\mu\nu} = 0$)，
- 在施加运动方程后守恒 ($\partial_\nu T^{\mu\nu} \overset{\text{e.o.m.}}{=} 0$)。

这是一个非平凡的事实，但我们将跳过其证明（如前所述，我们感兴趣的是那些不一定通过作用量定义的理论）。

严格来说，诺特定理只适用于具有拉格朗日描述的理论，但我们将在所有情况下假设无迹能动张量的存在（从某种意义上说，这将成为共形场论的“公理”之一）。从这个假设出发，我们可以推断该理论在共形变换下不变：总可以从能动张量和共形 Killing 矢量 $\varepsilon$ 构造出一个守恒流

$$
J ^ {\mu} = \varepsilon_ {\nu} T ^ {\mu \nu} \Rightarrow \partial_ {\mu} J ^ {\mu} = \varepsilon_ {\nu} \partial_ {\mu} T ^ {\mu \nu} \stackrel {e. o. m.} {=} 0. \tag{2.72}
$$

通常，守恒荷可以构造为守恒流的时间分量对空间的积分。最简单的例子是

$$
P ^ {\mu} = - i \int d ^ {d - 1} \vec {x} T ^ {0 \mu} (x). \tag{2.73}
$$

这原则上是一个关于 $x^0$ 的函数，但事实上它是不随时间变化的，因为

$$
\partial_ {0} P ^ {\mu} = - i \int d ^ {d - 1} \vec {x} \partial_ {0} T ^ {0 \mu} (x) = i \int d ^ {d - 1} \vec {x} \partial_ {i} T ^ {i \mu} (x) = 0. \tag{2.74}
$$

这个守恒荷是动量，与平移对称性相关联。类似地，有与洛伦兹变换相关的守恒荷，

$$
M ^ {\mu \nu} = - i \int d ^ {d - 1} \vec {x} \left[ x ^ {\mu} T ^ {0 \nu} (x) - x ^ {\nu} T ^ {0 \nu} (x) \right] \tag{2.75}
$$

与标度变换相关的，

$$
D = - i \int d ^ {d - 1} \vec {x} x _ {\mu} T ^ {0 \mu} (x), \tag{2.76}
$$

以及与特殊共形变换相关的

$$
K ^ {\mu} = - i \int d ^ {d - 1} \vec {x} \left[ 2 x ^ {\mu} x _ {\nu} T ^ {0 \nu} (x) - x ^ {2} T ^ {0 \mu} (x) \right]. \tag{2.77}
$$

**练习 2.6** 证明荷 (2.75)、(2.76) 和 (2.77) 是时间守恒的。

所有这些荷的守恒都依赖于能动张量散度为零，$\partial_\nu T^{\mu\nu}$，而这本身依赖于运动方程的满足。在没有源项的情况下，这当然是正确的。但是当作用量中添加了源项时，运动方程会被修改。在我们自由标量场理论的例子中，向作用量 (2.56) 添加一个形如

$$
S _ {\text { source }} = \int d ^ {d} x J (x) \phi (x), \tag{2.78}
$$

的源项，会将运动方程修改为

$$
\partial^ {2} \phi + J = 0. \tag{2.79}
$$

对于正则能动张量，不再有守恒方程 (2.67)，而必须替换为

$$
\partial_ {\nu} T ^ {\mu \nu} (x) = - J \partial^ {\mu} \phi . \tag{2.80}
$$

在这样的源存在下，荷 (2.73)–(2.77) 不再守恒。然而，如果源是局域的，比如 $J(x) = \delta^d(x - x_\odot)$，那么

$$
\partial_ {\nu} T ^ {\mu \nu} (x) = - \delta^ {d} (x - x _ {\odot}) \partial^ {\mu} \phi (x _ {\odot}), \tag{2.81}
$$

然后我们可以确定某个荷——比如 $P^\mu$——在早于局域源的时间 $x^0 < x_\odot^0$ 和晚于它的时间 $x^0 > x_\odot^0$ 之间的变化，并将这个差值称为源的动量 $P_\odot^\mu$。根据定义，这等于

$$
P _ {\odot} ^ {\mu} = - i \int d ^ {d - 1} \vec {x} T ^ {0 \mu} \Big | _ {x ^ {0} > x _ {\odot} ^ {0}} + i \int d ^ {d - 1} \vec {x} T ^ {0 \mu} \Big | _ {x ^ {0} <   x _ {\odot} ^ {0}}. \tag{2.82}
$$

由于两个积分面在空间无穷远处相接，它们可以被视为包围点 $x_\odot$ 的闭合曲面 $\partial\Sigma$ 的两侧，因此

$$
P _ {\odot} ^ {\mu} = - i \int_ {\partial \Sigma} d ^ {d - 1} n _ {\nu} T ^ {\mu \nu}. \tag{2.83}
$$

根据散度定理，这等于

$$
P _ {\odot} ^ {\mu} = - i \int_ {\Sigma} d ^ {d} x \partial_ {\nu} T ^ {\mu \nu} (x) = i \int_ {\Sigma} d ^ {d} x \delta^ {d} (x - x _ {\odot}) \partial^ {\mu} \phi (x) = i \partial^ {\mu} \phi (x _ {\odot}). \tag{2.84}
$$

注意，这个结果不依赖于 $\partial\Sigma$ 的选择，只要它包围了点 $x_\odot$。用专业术语说，$P^\mu$ 是一个拓扑荷。我们在方程 (2.73) 中选择了对能动张量沿常时间面积分的标准定义。但如果我们在欧几里得空间中工作，这共形等价于对球面或任何其他闭合曲面积分。

方程 (2.84) 非常重要：它说明与场 $\phi$ 的局域源相关联的荷 $P^\mu$ 等于 $i\partial^\mu\phi$。这与生成元 (2.30) 对坐标函数的作用惊人地相似。事实上，容易验证其他荷 (2.75)、(2.76) 和 (2.77) 对经典场 $\phi(x)$ 的作用完全类似于生成元 (2.31)、(2.32) 和 (2.33)。我们这里以自由标量场论为例进行了讨论，但我们的讨论可以推广到任意经典场论。重要的教训是，无迹能动张量可用于给出之前讨论的共形生成元的场论实现。

# 第三章 共形量子场论

现在让我们转向量子场论，并研究共形对称性在该背景下的含义。量子场论的标准方法是先考虑一个经典场论（我们现在对其中的共形对称性有了基本的理解），然后通过将场提升为作用在某个希尔伯特空间上的算符来对其进行量子化。但这并不是我们将要采用的方法。这里仍然会有态和算符，但后者不一定与拉格朗日量中出现的场相关联。

## 3.1 非微扰量子场论

为了非微扰地定义一个量子场论，我们需要以下要素：

1. **希尔伯特空间**：闵可夫斯基时空被分层为等时面，每个时间切片关联一个量子态的希尔伯特空间。
2. **局域算符**：存在许多（实际上是无限多）作用在这个希尔伯特空间上的局域算符。例如，令 $\phi(x)$ 为作用在时间 $t = x^0$ 的希尔伯特空间上的一个算符。我们称这个算符为局域的，是因为我们要求它与同一时间切片上不同点 $\vec{x}' \neq \vec{x}$ 处插入的任何其他局域算符对易[1]：
   $$
   \left[ \phi (x), \phi (x ^ {\prime}) \right] = 0, \quad x ^ {0} = x ^ {\prime 0}, \quad \vec {x} \neq \vec {x} ^ {\prime}. \tag{3.1}
   $$
3. **对称性**：该理论的局域算符之一是能动张量，从中我们可以定义守恒荷，包括如 (2.73) 和 (2.75) 中的 $P^\mu$ 和 $M^{\mu\nu}$。在一般的 QFT 中，能动张量不需要是无迹的，因此不能考虑荷 $D$ 和 $K^\mu$。$P^\mu$ 和 $M^{\mu\nu}$ 是时间守恒的，因此它们是每个时间 $t$ 的所有希尔伯特空间上的有效算符。然而，每当一个算符在某个点 $x$ 插入时，它们的值就会改变。与方程 (2.84) 类似，我们要求这个变化编码在对易子中
   $$
   \left[ P ^ {\mu}, \phi (x) \right] = i \partial^ {\mu} \phi (x). \tag{3.2}
   $$
   由于这个方程的解是
   $$
   \phi (x) = e ^ {- i x \cdot P} \phi (0) e ^ {i x \cdot P}, \tag{3.3}
   $$
   我们说 $P^\mu$ 是平移的生成元，它作为酉变换作用于算符（注意 $P^\mu$ 是厄米的）。
   洛伦兹变换类似地实现为酉变换，由荷 $M^{\mu\nu}$ 生成。我们可以选择将时空原点处插入的局域算符分解为洛伦兹群的不可约表示，并用 $\phi^a(0)$ 表示，其中 $a$ 代表一组洛伦兹指标，使得
   $$
   \left[ M ^ {\mu \nu}, \phi^ {a} (0) \right] = i \left(\mathcal {S} ^ {\mu \nu}\right) _ {b} ^ {a} \phi^ {b} (0), \tag{3.4}
   $$
   其中 $(S^{\mu\nu})_b^a$ 是一个满足洛伦兹代数的矩阵。对于标量算符，$S^{\mu\nu}$ 为零；对于具有一个洛伦兹指标的矢量算符，它由下式给出
   $$
   (\mathcal {S} ^ {\mu \nu}) _ {a b} = \delta_ {a} ^ {\mu} \delta_ {b} ^ {\nu} - \delta_ {b} ^ {\mu} \delta_ {a} ^ {\nu}, \tag{3.5}
   $$
   以此类推。当与方程 (3.3) 结合，并要求 $P^\mu$ 和 $M^{\mu\nu}$ 满足庞加莱代数 (2.34) 时，这意味着
   $$
   \left[ M ^ {\mu \nu}, \phi^ {a} (x) \right] = - i \left(x ^ {\mu} \partial^ {\nu} - x ^ {\nu} \partial^ {\mu}\right) \phi^ {a} (x) + i \left(\mathcal {S} ^ {\mu \nu}\right) _ {b} ^ {a} \phi^ {b} (0). \tag{3.6}
   $$
   注意，$P^\mu$ 和 $M^{\mu\nu}$ 不是局域算符，但它们与任何局域算符的对易子仍然是局域的（生成元 $D$ 和 $K^\mu$ 也是如此）。
4. **真空态**：希尔伯特空间包括一个真空态 $|0\rangle$，我们假设它在庞加莱变换（以及后来的共形变换）下不变，
   $$
   P ^ {\mu} \left| 0 \right\rangle = M ^ {\mu \nu} \left| 0 \right\rangle = 0. \tag{3.7}
   $$
   该理论的其他态可以通过将局域算符的乘积作用在真空上得到（详见下文）。原则上每个时间切片有一个希尔伯特空间，但由于时间平移是由 $P^0$ 生成的对称性，演化算符 $U(t) = e^{i t \mathcal{P}^0}$ 是酉的，所有希尔伯特空间等价。我们还要求真空是希尔伯特空间中能量最低的态。这意味着，如果我们可以构造一个能量本征态
   $$
   P ^ {0} \left| \Psi \right\rangle = E \left| \Psi \right\rangle , \tag{3.8}
   $$
   那么它的本征值必须满足 $E \geq 0$。

这四点基本上给出了量子场论最一般的非微扰定义。它们几乎等价于所谓的 Wightman 公理（但此处没有过多的数学严谨性）。一个显著的区别是，Wightman 公理不依赖于能动张量的存在，而是直接假设庞加莱变换在希尔伯特空间上实现为酉变换。

局域性条件 (3.1) 通常表述为洛伦兹不变的形式

$$
[ \phi (x), \phi (y) ] = 0 \quad \text { if } (x - y) ^ {2} > 0, \tag{3.9}
$$

说明只要局域算符是类空间隔的，它们就对易，这被称为微观因果性公理。类似地，当可以使用能量和动量的本征态时，

$$
P ^ {\mu} \left| \Psi \right\rangle = p ^ {\mu} \left| \Psi \right\rangle , \tag{3.10}
$$

那么能量正定的洛伦兹不变条件变为

$$
p ^ {0} \geq | \vec {p} | \quad \Leftrightarrow \quad p ^ {2} \leq 0 \text {   and   } p ^ {0} \geq 0, \tag{3.11}
$$

即动量 $p^\mu$ 包含在前向光锥内。这样的 $P^\mu$ 本征态可以通过局域算符的傅里叶变换构造，

$$
\widetilde {\phi} (p) = \int d ^ {d} x e ^ {i p \cdot x} \phi (x) \tag{3.12}
$$

然后作用在真空上。这意味着

$$
\widetilde {\phi} (p) \left| 0 \right\rangle = 0 \quad \text { if } p ^ {0} <   | \vec {p} |, \tag{3.13}
$$

以及其推广到多个局域算符乘积的形式，

$$
\widetilde {\phi} _ {1} (p _ {1}) \dots \widetilde {\phi} _ {n} (p _ {n}) | 0 \rangle = 0 \quad \text { if } p _ {1} ^ {0} + \dots + p _ {n} ^ {0} <   | \vec {p} _ {1} + \dots + \vec {p} _ {n} |. \tag{3.14}
$$

这有时被称为谱条件。

**练习 3.1** 使用定义 (3.3) 和分部积分，证明
$$
P ^ {\mu} \widetilde {\phi} (p) | 0 \rangle = p ^ {\mu} \widetilde {\phi} (p) | 0 \rangle .
$$

## 3.2 Wightman 函数

从这些公理出发，我们可以计算局域算符乘积的真空期望值，

$$
\langle 0 | \phi_ {1} (x _ {1}) \dots \phi_ {n} (x _ {n}) | 0 \rangle . \tag{3.15}
$$

这可以视为真空态 $\langle 0|$ 与通过一系列局域算符作用在真空上产生的态的重叠。注意，这些算符不需要按时间排序：时间演化算符是酉的，可以双向进行。因此，这个对象不同于从路径积分中得到的时间序关联函数。

这种类型的关联函数称为 Wightman 函数。它们是非微扰量子场论中的基本可观测量。事实上，甚至可以通过其所有 Wightman 函数来完整定义一个量子场论：Wightman 重建定理指出，一个量子场论的希尔伯特空间可以从其所有 Wightman 函数构造出来。因此，一个方便的观点是忘记希尔伯特空间，专注于关联函数。

这些关联函数的对称性属性编码在“Ward 恒等式”中：给定一个湮灭真空的守恒荷 $G$，即 $G|0\rangle = 0$（这可以是 $P^\mu$ 或 $M^{\mu\nu}$），则以下方程必须成立

$$
\begin{array}{l} \langle 0 | [ G, \phi_ {1} (x _ {1}) ] \phi_ {2} (x _ {2}) \dots \phi_ {n} (x _ {n}) | 0 \rangle \\ + \langle 0 | \phi_ {1} (x _ {1}) [ G, \phi_ {2} (x _ {2}) ] \dots \phi_ {n} (x _ {n}) | 0 \rangle \\ + \dots \\ + \langle 0 | \phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) \dots [ G, \phi_ {n} (x _ {n}) ] | 0 \rangle = 0. \tag{3.16} \\ \end{array}
$$

这在希尔伯特空间图景中是显而易见的，但它也作为 Wightman 函数的微分方程成立，因为每个对易子再次与局域算符相关。让我们看一些例子。

最简单的 Wightman 函数涉及单个标量算符，

$$
\langle 0 | \phi (x) | 0 \rangle . \tag{3.17}
$$

在这种情况下，与平移相关的 Ward 恒等式意味着

$$
\langle 0 | [ P ^ {\mu}, \phi (x) ] | 0 \rangle = 0 \Rightarrow \frac {\partial}{\partial x ^ {\mu}} \langle 0 | \phi (x) | 0 \rangle = 0, \tag{3.18}
$$

或者说，该算符的真空期望值在整个时空是常数。洛伦兹对称性没有给出关于这个常数的更多信息，但它禁止了所有在洛伦兹群下非平凡变换的算符具有真空期望值。

接下来考虑相同标量算符的 Wightman 2 点函数，

$$
\langle 0 | \phi (x) \phi (y) | 0 \rangle . \tag{3.19}
$$

在这种情况下，平移对称性告诉我们

$$
\left(\frac {\partial}{\partial x ^ {\mu}} + \frac {\partial}{\partial y ^ {\mu}}\right) \langle 0 | \phi (x) \phi (y) | 0 \rangle = 0. \tag{3.20}
$$

如果我们把关联函数视为 $x+y$ 和 $x-y$ 的函数，那么这个 Ward 恒等式确立了它不依赖于前者，即

$$
\langle 0 | \phi (x) \phi (y) | 0 \rangle = W (y - x), \tag{3.21}
$$

其中 $W$ 表示一个迄今任意的函数。

一般来说，平移对称性的结果在动量空间更容易看出，使用局域算符的傅里叶变换。根据方程 (3.12)，我们可以建立

$$
\left[ P ^ {\mu}, \widetilde {\phi} (p) \right] = p ^ {\mu} \widetilde {\phi} (p), \tag{3.22}
$$

因此 Wightman 2 点函数的傅里叶变换满足

$$
(p ^ {\mu} + q ^ {\mu}) \langle 0 | \widetilde {\phi} (p) \widetilde {\phi} (q) | 0 \rangle = 0. \tag{3.23}
$$

由此我们得出结论，2 点函数正比于狄拉克 delta 函数：

$$
\langle 0 | \widetilde {\phi} (p) \widetilde {\phi} (q)   | 0 \rangle = (2 \pi) ^ {d} \delta^ {d} (p + q) \widetilde {W} (q). \tag{3.24}
$$

数值因子 $(2\pi)^d$ 只是一个约定。如符号所示，$\widetilde{W}$ 实际上是 $W$ 的傅里叶变换，

$$
\widetilde {W} (q) = \int d ^ {d} x e ^ {i p \cdot x} W (x). \tag{3.25}
$$

考虑到洛伦兹对称性，还可以确定 Wightman 函数 $W(x)$ 只能依赖于洛伦兹不变距离 $x^2$，但有一个微妙之处：根据 $x$ 是类空还是类时（未来指向或过去指向），这是一个不同的函数，因为洛伦兹变换分别作用于这些区域。在动量空间中，同样的论证说 $\widetilde{W}(q)$ 必须是 $q^2$ 的函数。在这种情况下，只存在正能量态的条件要求 $\widetilde{W}(q)$ 除非 $q^0 \geq |\vec{q}|$ 否则为零，因此我们可以明确地写为

$$
\widetilde {W} (q) = 2 \pi \theta \left(q ^ {0} - | \vec {q} |\right) \rho (- q ^ {2}), \tag{3.26}
$$

其中 $\rho$ 是正量 $-q^2$ 的函数，$\theta$ 是 Heaviside 阶跃函数[2]。

Wightman 2 点函数 (3.24) 正比于 delta 函数这一事实提出了一个重要问题：尽管名称如此，Wightman 函数并非函数而是分布（这也是 Wightman 公理的一部分：它们是缓增分布）。还要注意，同一个函数计算了两个态

$$
\widetilde {\phi} (q) \left| 0 \right\rangle \quad \text { and } \quad \widetilde {\phi} (- p) \left| 0 \right\rangle \tag{3.27}
$$

的重叠（厄米共轭会翻转动量的符号）。因此，极限 $p \to -q$ 对应于这些态中任何一个的范数。但这个极限显然是不连续的，或者说态的范数是无穷大。这个问题的解决方法是，对象 $\phi(x)$ 及其傅里叶变换 $\widetilde{\phi}(p)$ 不是算符，而是算符值分布。换句话说，$\phi(x)|0\rangle$ 和 $\widetilde{\phi}(p)|0\rangle$ 不是理论的态，因为它们实际上具有无穷大的范数。形式上，这些算符值分布只有在与测试函数积分时才有意义，从而定义

$$
\phi [ f ] = \int d ^ {d} x f (x) \phi (x), \tag{3.28}
$$

或

$$
\widetilde {\phi} [ \tilde {f} ] = \int d ^ {d} p \tilde {f} (p) \widetilde {\phi} (p), \tag{3.29}
$$

其中 $f$ 和 $\tilde{f}$ 是 Schwartz 类测试函数（光滑且在无穷远处衰减快于任何幂次）。当作用在真空上时，这些涂抹过的算符给出定义良好的态，具有有限范数。例如，我们有

$$
\begin{array}{l} \left\| \widetilde {\phi} [ \tilde {f} ] | 0 \rangle \right\| ^ {2} = \int d ^ {d} p d ^ {d} q \tilde {f} ^ {*} (p) \tilde {f} (q) \langle 0 | \widetilde {\phi} (- p) \widetilde {\phi} (q) | 0 \rangle \\ = (2 \pi) ^ {d + 1} \int_ {q ^ {0} > | \vec {q} |} d ^ {d} q \left| \tilde {f} (q) \right| ^ {2} \rho (- q ^ {2}). \tag{3.30} \\ \end{array}
$$

## 3.3 谱表示

测试函数在后续讲义中将不再出现。对物理学家来说，它们主要是我们希望避免的麻烦。然而，了解存在一种处理 Wightman 函数的数学上严谨的方法是很重要的。一方面，这为为什么总是可以对 Wightman 函数（而非时间序关联函数）进行位置空间和动量空间表示之间的傅里叶变换提供了合理的理由，因为缓增分布总是允许傅里叶变换。

范数 (3.30) 也提供了重要信息：对于任何测试函数 $f$，只有当函数 $\rho$ 为正时，它才能为正，

$$
\rho (\mu^ {2}) \geq 0, \quad \forall   \mu^ {2} > 0. \tag{3.31}
$$

$\rho(\mu^2)$ 实际上是标准量子场论教科书中遇到的谱密度，我们通常可以将其形式写为

$$
\langle 0 | \phi (x) \phi (y) | 0 \rangle = 2 \pi \int \frac {d ^ {d} k}{(2 \pi) ^ {d}} \int_ {0} ^ {\infty} d \mu^ {2} e ^ {i k \cdot (x - y)} \theta (k ^ {0}) \delta (k ^ {2} + \mu^ {2}) \rho (\mu^ {2}). \tag{3.32}
$$

谱密度是非微扰量子场论中的一个基本工具。例如，它可用于构造时间序关联函数

$$
\langle \phi (x) \phi (y) \rangle_ {T} \equiv \theta (x ^ {0} - y ^ {0}) \left\langle 0 | \phi (x) \phi (y) | 0 \right\rangle + \theta (y ^ {0} - x ^ {0}) \left\langle 0 | \phi (y) \phi (x) | 0 \right\rangle . \tag{3.33}
$$

与 Wightman 函数不同，这不是一个缓增分布，因为 $\theta$ 函数在原点不可微。尽管如此，时间序乘积允许简单的表示

$$
\langle \phi (x) \phi (y) \rangle_ {T} = \int \frac {d ^ {d} k}{(2 \pi) ^ {d}} \int_ {0} ^ {\infty} d \mu^ {2} e ^ {i k \cdot (x - y)} \frac {i}{- k ^ {2} - \mu^ {2} + i \varepsilon} \rho (\mu^ {2}) \tag{3.34}
$$

其中极限 $\varepsilon \to 0_+$ 是默认的。这就是时间序 2 点函数的 Källen-Lehmann 表示。

**练习 3.2** 推导 Källen-Lehmann 表示。一个优雅的推导是首先证明时间序 2 点函数可以写为 Wightman 函数与推迟对易子真空期望值之差，
$$
\langle \phi (x) \phi (y) \rangle_ {T} = W (y - x) - \theta (y ^ {0} - x ^ {0}) \left\langle 0 \right| [ \phi (x), \phi (y) ] | 0 \rangle .
$$
下一步是在设 $x=0$ 后对 $y$ 中的两项进行傅里叶变换。我们知道 Wightman 函数 (3.24) 有一个良好的傅里叶变换
$$
\widetilde {W} (q) = 2 \pi \int_ {0} ^ {\infty} d \mu^ {2} \theta (q ^ {0}) \delta (q ^ {2} + \mu^ {2}) \rho (\mu^ {2}),
$$
它可以等价地写为
$$
\widetilde {W} (q) = \int_ {0} ^ {\infty} d \mu^ {2} \theta (q ^ {0}) \left[ \frac {i}{q ^ {2} + \mu^ {2} + i \varepsilon} - \frac {i}{q ^ {2} + \mu^ {2} - i \varepsilon} \right] \rho (\mu^ {2}).
$$
推迟对易子仅在 $y$ 的前向光锥内非零，因此它也允许傅里叶变换，前提是赋予 $q$ 一个虚部。计算这个傅里叶变换，并证明在实 $q$ 处它等于
$$
\int_ {0} ^ {\infty} d \mu^ {2} \left[ \theta (q ^ {0}) \frac {i}{q ^ {2} + \mu^ {2} + i \varepsilon} + \theta (- q ^ {0}) \frac {i}{q ^ {2} + \mu^ {2} - i \varepsilon} \right] \rho (\mu^ {2}).
$$
然后，最后两个积分之间的差可以很容易地转化为 Källen-Lehmann 表示 (3.34)。

2 点函数的谱表示在非相互作用理论中给出了熟悉的结果。例如，一个质量标量场的谱密度为

$$
\rho (\mu^ {2}) = \delta (\mu^ {2} - m ^ {2}), \tag{3.35}
$$

由此我们恢复已知的有质量传播子

$$
\langle \phi (x) \phi (y) \rangle_ {T} = \int \frac {d ^ {d} k}{(2 \pi) ^ {d}} e ^ {i k \cdot (x - y)} \frac {i}{- k ^ {2} - m ^ {2} + i \varepsilon}. \tag{3.36}
$$

![图 3.1 左图：自由有质量场理论中的谱密度，以及高于粒子产生阈值的典型贡献（虚线）。右图：标度不变理论中可能的谱密度](image-link)

在相互作用理论中，谱密度将获得对应于高于某个阈值的粒子产生的贡献（见图 3.1）。

到目前为止的讨论适用于没有共形对称性的一般量子场论。现在让我们考察标度对称性和特殊共形不变性的作用，从前者开始。

## 3.4 标度对称性

标度对称性的假设与除了 $P^\mu$ 和 $M^{\mu\nu}$ 之外存在第三个守恒荷 $D$ 相吻合。我们之前得到了一个一般局域算符与 $M^{\mu\nu}$ 的对易子，假设它在 $x=0$ 处变换为洛伦兹群的某个不可约表示（在其他点插入的算符不属于不可约表示，因为 $P^\mu$ 不与 $M^{\mu\nu}$ 对易）。由于 $M^{\mu\nu}$ 与 $D$ 对易，关于标度可以做出同样的假设：任何局域算符可以进一步分解为标度变换群的不可约表示，这意味着我们可以写

$$
[ D, \phi (0) ] = - i \Delta \phi (0). \tag{3.37}
$$

$\Delta$ 被称为算符 $\phi$ 的标度维度（理论的每个局域算符都有自己的标度维度）。因子 $i$ 确保当 $\phi$ 是实算符时 $\Delta$ 是实数。像之前一样，我们可以使用方程 (3.3) 得到任何其他点 $x$ 处的对易子：

$$
[ D, \phi (x) ] = - i \left(x ^ {\mu} \partial_ {\mu} + \Delta\right) \phi (x). \tag{3.38}
$$

注意，这与经典场的变换规则 (2.62) 一致：在自由理论中标度维度 $\Delta$ 与算符 $\phi$ 的质量维度一致。

使用这个新的对易子，并假设真空态在标度变换下不变，可以得到 Wightman 2 点函数的一个新 Ward 恒等式，

$$
\left(x ^ {\mu} \frac {\partial}{\partial x ^ {\mu}} + y ^ {\mu} \frac {\partial}{\partial y ^ {\mu}} + 2 \Delta\right) \langle 0 | \phi (x) \phi (y) | 0 \rangle = 0, \tag{3.39}
$$

或者等价地，使用方程 (3.21)，

$$
\left(x ^ {\mu} \frac {\partial}{\partial x ^ {\mu}} + 2 \Delta\right) W (x) = 0. \tag{3.40}
$$

动量空间 2 点函数对应的条件通过傅里叶变换得到，使用分部积分：

$$
\left(- q ^ {\mu} \frac {\partial}{\partial q ^ {\mu}} + 2 \Delta - d\right) \widetilde {W} (q) = 0. \tag{3.41}
$$

与形式 (3.26) 一致的这个方程的解是唯一的，直到一个乘法常数 $C$，

$$
\widetilde {W} (q) = 2 \pi C \theta \left(q ^ {0} - | \vec {q} |\right) (- q ^ {2}) ^ {\Delta - d / 2}, \tag{3.42}
$$

这意味着谱密度是能量的幂次，

$$
\rho (\mu^ {2}) = C \left(\mu^ {2}\right) ^ {\Delta - d / 2}. \tag{3.43}
$$

这种谱密度，如图 3.1 所示，与有质量相互作用理论的谱密度非常不同：算符 $\phi$ 产生所有能量的态。同时，其简单性令人震惊：它由一个参数 $\Delta$ 表征，以及一个不携带物理信息的归一化常数（可以重新定义算符来吸收这个常数）。

使用 Källen-Lehmann 表示计算时间序函数是有启发性的：对 $\mu^2$ 进行积分，我们得到

$$
\langle \phi (x) \phi (y) \rangle_ {T} = \frac {i \pi C}{\sin \left[ \pi \left(\Delta - \frac {d}{2}\right) \right]} \int \frac {d ^ {d} k}{(2 \pi) ^ {d}} e ^ {i k \cdot (x - y)} \left(k ^ {2} - i \varepsilon\right) ^ {\Delta - d / 2}. \tag{3.44}
$$

积分中的项 $(k^2 - i\varepsilon)^{\Delta - d/2}$ 看起来像一个无质量标量场传播子的非整数次幂。这实际上正是我们在微扰论中当 $\beta$ 函数有一个非平凡不动点时所期望的：重整化后的 2 点函数具有对数，可以重求和为受场 $\phi$ 的反常维度 $\gamma$ 控制的幂次，

$$
\frac {i}{- q ^ {2}} \left[ 1 + \gamma \log (- q ^ {2}) + \dots \right] \approx i (- q ^ {2}) ^ {- 1 + \gamma}. \tag{3.45}
$$

在这种情况下，对应于重整化场的标量算符的标度维度是

$$
\Delta = \frac {d - 2}{2} + \gamma . \tag{3.46}
$$

在极限 $\gamma \to 0$ 时，我们恢复上述自由传播子。但请注意，除非系数 $C$ 满足

$$
C \propto \gamma = \Delta - \frac {d - 2}{2}, \tag{3.47}
$$

否则积分前的因子在这个极限下发散。假设情况确实如此（见下文），谱密度满足[3]

$$
\rho (\mu^ {2}) \propto \gamma (\mu^ {2}) ^ {- 1 + \gamma} \xrightarrow {\gamma \to 0} \delta (\mu^ {2}). \tag{3.48}
$$

这正是自由标量场论中预期的谱密度。在这种情况下（也仅在这种情况下！），算符 $\phi$ 描述了一个无质量标量粒子。

事实证明，$\Delta = \frac{d-2}{2}$ 是 $\Delta$ 可能的最小值：对于任何低于该值的 $\Delta$，谱密度在 $\mu^2 \to 0$ 的极限下不可积。人们也可能担心积分中 $\mu^2 \to \infty$ 的相反极限：对于任何 $\Delta > d/2$，谱密度随 $\mu^2$ 增长。然而，请记住，这个谱密度实际上是一个 Wightman 函数，即一个缓增分布，应该理解为与在大的 $q^2$ 处衰减快于任何幂次的测试函数积分。因此，任意大的 $\Delta$ 值是可能的，但 $\Delta$ 存在一个下界，低于它，用测试函数涂抹过的态将具有无穷大的范数。不等式

$$
\Delta \geq \frac {d - 2}{2}. \tag{3.49}
$$

在文献中被称为标量算符的幺正性界[4]。注意，任何饱和这个幺正性界的标量算符都有

$$
\langle 0 | \widetilde {\phi} (p) \widetilde {\phi} (q) | 0 \rangle \propto \delta (q ^ {2}), \tag{3.50}
$$

这意味着

$$
q ^ {2} \langle 0 | \widetilde {\phi} (p) \widetilde {\phi} (q) | 0 \rangle = 0, \tag{3.51}
$$

或者在位置空间中

$$
\langle 0 | \phi (x) \partial^ {2} \phi (y) | 0 \rangle = 0. \tag{3.52}
$$

由于这对任何 $x$ 和 $y$ 都成立，这意味着

$$
\partial^ {2} \phi (x) = 0 \tag{3.53}
$$

作为算符方程成立。由于这是自由场的运动方程，一个 $\Delta = \frac{d-2}{2}$ 的理论是自由场论。

标度不变理论中动量空间 2 点函数的简单性也意味着它可以很容易地通过傅里叶变换回位置空间，使用

$$
W (x) = \int \frac {d ^ {d} q}{(2 \pi) ^ {d}} e ^ {- i q \cdot x} \widetilde {W} (q). \tag{3.54}
$$

**练习 3.3** 显式地执行傅里叶变换。你可以利用积分是洛伦兹不变的事实来确定 $W(x)$ 实际上是 $x^2$ 的函数。此外，由于被积函数仅在 $q$ 位于前向光锥时有支撑，这定义了 $x$ 的一个函数，只要 $\operatorname{Im} x$ 包含在未来光锥内，该函数在 $x$ 上是解析的：在这种情况下，被积函数被指数 $e^{q \cdot \operatorname{Im} x}$ 阻尼，且 $q \cdot \operatorname{Im} x < 0$（这个解析性区域被称为“未来管”）。这意味着我们可以自由地在点 $x = (i\tau, 0)$ 处计算积分，然后使用 $\tau^2 = x^2$ 来恢复通解。在该点的积分对所有满足幺正性界的 $\Delta$ 都收敛，你应该会得到

$$
W (\tau) = C \frac {2 ^ {2 \Delta} \Gamma (\Delta) \Gamma \left(\Delta - \frac {d - 2}{2}\right)}{(4 \pi) ^ {d / 2}} \tau^ {- 2 \Delta}
$$

这个积分的结果可以写成

$$
W (x) = \frac {C ^ {\prime}}{\left[ - (x ^ {0} + i \varepsilon) ^ {2} + \vec {x} ^ {2} \right] ^ {\Delta}} \tag{3.55}
$$

其中极限 $\varepsilon \to 0_+$ 用于理解 $x^2 \leq 0$ 的情况，即

$$
W (x) = \frac {C ^ {\prime}}{\left| x ^ {2} \right| ^ {\Delta}} \times \left\{ \begin{array}{l l} e ^ {- i \pi \Delta} & \text { if   } x ^ {0} <   - | \vec {x} |, \\ 1 & \text { if   } - | \vec {x} | <   x ^ {0} <   | \vec {x} |, \\ e ^ {i \pi \Delta} & \text { if   } x ^ {0} > | \vec {x} |. \end{array} \right. \tag{3.56}
$$

系数 $C'$ 和 $C$ 的关系为

$$
C = \frac {(4 \pi) ^ {d / 2}}{2 ^ {2 \Delta} \Gamma (\Delta) \Gamma \left(\Delta - \frac {d - 2}{2}\right)} C ^ {\prime}. \tag{3.57}
$$

注意，对于所有满足幺正性界 (3.49) 的 $\Delta$，比例因子为正。这意味着 2 点关联函数总是随距离减小，而不是相反。在共形场论中，习惯上对标量算符 $\phi$ 进行归一化，使得 $C' = 1$，在这种情况下，$C$ 在极限 $\Delta \to \frac{d-2}{2}$ 时如方程 (3.47) 所示趋于零。

最后，让我们以关于单点函数的一个评论来结束对标度对称性的分析。我们在前一节中看到，标量算符的常数真空期望值与庞加莱对称性兼容。然而，对易子 (3.38) 要求 $\Delta = 0$，这违反了幺正性界。我们得出结论，在标度不变的理论中，所有单点函数必须为零。

## 3.5 特殊共形对称性

与标度对称性一样，特殊共形对称性的存在与守恒荷 $K^\mu$ 的存在相关联，这些荷组成一个 $d$ 维矢量。然而，与 $D$ 不同，$K^\mu$ 不与 $M^{\mu\nu}$ 对易，因此不能在 $x=0$ 点对角化。尽管如此，我们可以使用共形代数来证明，如果 $\phi$ 是一个标度维度为 $\Delta$ 的局域算符，那么 $[K^\mu, \phi]$ 的标度维度为 $\Delta-1$：

$$
\begin{array}{l} \left[ D, \left[ K ^ {\mu}, \phi (0) \right] \right] = \left[ K ^ {\mu}, [ D, \phi (0) ] \right] + \left[ [ D, K ^ {\mu} ], \phi (0) \right] \\ = \left[ K ^ {\mu}, - i \Delta \phi (0) \right] + \left[ i K ^ {\mu}, \phi (0) \right] = - i (\Delta - 1) [ K ^ {\mu}, \phi (0) ]. \tag{3.58} \\ \end{array}
$$

这与观察 $[P^\mu, \phi(x)]$ 的标度维度为 $\Delta+1$ 类似，

$$
\left[ D, [ P ^ {\mu}, \phi (0) ] \right] = - i (\Delta + 1) [ P ^ {\mu}, \phi (0) ], \tag{3.59}
$$

这与导数 $\partial^\mu$ 的质量维度为 $1$ 一致。$K^\mu$ 降低标度维度的事实似乎与我们上一节的发现（$\Delta$ 有下界）相矛盾：给定任何局域算符，总可以构造其他具有任意更小标度维度的局域算符。

摆脱这个明显悖论的唯一方法是假设在某个时刻，$K^\mu$ 的作用会湮灭该算符。换句话说，必须存在某个局域算符使得

$$
\left[ K ^ {\mu}, \phi (0) \right] = 0. \tag{3.60}
$$

我们称这个局域算符为 primary。任何其他局域算符可以通过将 $P^\mu$ 作用在某个 primary 上得到，我们称其为 descendant。由于 $P^\mu$ 的作用等同于求导，primary 算符就是那些不能写成其他算符的导数的算符。除非另有说明，从现在起我们将只考虑 primary 算符的 Wightman 关联函数。Descendant 将用导数显式表示。

远离原点的 primary 算符的变换可以再次从方程 (3.3) 获得。注意，由于 $P^\mu$ 和 $K^\mu$ 的对易子涉及 $D$ 和 $M^{\mu\nu}$，这个变换取决于算符的标度维度和洛伦兹表示，即依赖于特征值 $\Delta$ 和 $S^{\mu\nu}$。我们得到

$$
\left[ K ^ {\mu}, \phi (x) \right] = - i \left(2 x ^ {\mu} x ^ {\nu} \partial_ {\nu} - x ^ {2} \partial^ {\mu} + 2 \Delta x ^ {\mu} - 2 \mathcal {S} ^ {\mu \nu} x _ {\nu}\right) \phi (x). \tag{3.61}
$$

这个方程也定义了动量空间算符的对易子：使用定义 (3.12) 进行分部积分，可以证明这相当于将 $\partial_\mu$ 替换为 $-i q_\mu$，将 $x^\mu$ 替换为 $-i \partial/\partial q_\mu$，因此

$$
\left[ K ^ {\mu}, \widetilde {\phi} (q) \right] = \left[ 2 \frac {\partial^ {2}}{\partial q _ {\mu} \partial q _ {\nu}} q _ {\nu} - \frac {\partial^ {2}}{\partial q _ {\nu} \partial q ^ {\nu}} q ^ {\mu} - 2 \Delta \frac {\partial}{\partial q _ {\mu}} + 2 \mathcal {S} ^ {\mu \nu} \frac {\partial}{\partial q ^ {\nu}} \right] \widetilde {\phi} (q), \tag{3.62}
$$

或者在重排导数和 $q$ 的顺序后，

$$
\left[ K ^ {\mu}, \widetilde {\phi} (q) \right] = \left[ 2 q ^ {\nu} \frac {\partial^ {2}}{\partial q _ {\mu} \partial q ^ {\nu}} - q ^ {\mu} \frac {\partial^ {2}}{\partial q _ {\nu} \partial q ^ {\nu}} + 2 (d - \Delta) \frac {\partial}{\partial q _ {\mu}} + 2 \mathcal {S} ^ {\mu \nu} \frac {\partial}{\partial q ^ {\nu}} \right] \widetilde {\phi} (q). \tag{3.63}
$$

这是一个作用在动量空间表示的算符上的二阶微分算子。

我们可以用这个对易子做的第一件事是检查 Wightman 2 点函数的相关 Ward 恒等式。记住这个函数可以写成

$$
W (x) = \langle 0 | \phi (0) \phi (x) | 0 \rangle . \tag{3.64}
$$

对易子平凡地作用在原点处插入的算符上，因此我们必须有（对标量算符，$S^{\mu\nu}=0$）

$$
\left(2 x ^ {\mu} x ^ {\nu} \partial_ {\nu} - x ^ {2} \partial^ {\mu} + 2 \Delta x ^ {\mu}\right) W (x) = 0. \tag{3.65}
$$

让我们在类空 $x$ 处检查：使用 $W(x) = 1/(x^2)^\Delta$，我们有 $\partial_\mu W(x) = -2\Delta W(x) x_\mu/x^2$，因此微分方程显然满足。同样可以在动量空间中验证：根据定义，我们有

$$
\widetilde {W} (q) = \langle 0 | \phi (0) \widetilde {\phi} (q) | 0 \rangle , \tag{3.66}
$$

其中只有右边的算符被傅里叶变换，左边的算符保持在位置空间的原点，因此上述对易子意味着

$$
\left[ 2 q ^ {\nu} \frac {\partial^ {2}}{\partial q _ {\mu} \partial q ^ {\nu}} - q ^ {\mu} \frac {\partial^ {2}}{\partial q _ {\nu} \partial q ^ {\nu}} + 2 (d - \Delta) \frac {\partial}{\partial q _ {\mu}} \right] \widetilde {W} (q) = 0. \tag{3.67}
$$

对于 $\widetilde{W}(q) = (-q^2)^{\Delta - d/2}$，这个方程再次被满足。

**不同算符**：$W(x)$ 和 $\widetilde{W}(q)$ 很容易满足特殊共形对称性施加的约束，这非常特定于相同的标量算符。在所有其他情况下，特殊共形对称性比庞加莱和标度对称性单独施加了更多的约束。最简单的例子是不同的标量算符的 2 点函数，

$$
\langle 0 | \phi_ {1} (x) \phi_ {2} (y) | 0 \rangle . \tag{3.68}
$$

根据庞加莱对称性，这仍然是 $(x-y)^2$ 的函数。但现在有两个不同的标度维度 $\Delta_1$ 和 $\Delta_2$ 对应于算符 $\phi_1$ 和 $\phi_2$，标度对称性的 Ward 恒等式变为（为简单起见，设 $\phi_1$ 在原点）

$$
\left(x ^ {\mu} \frac {\partial}{\partial x ^ {\mu}} + \Delta_ {1} + \Delta_ {2}\right) \langle 0 | \phi_ {1} (0) \phi_ {2} (x) | 0 \rangle = 0. \tag{3.69}
$$

解被固定到乘法常数，为（假设 $x$ 类空以简化）

$$
\langle 0 | \phi_ {1} (0) \phi_ {2} (x) | 0 \rangle = \frac {C _ {1 2}}{(x ^ {2}) ^ {(\Delta_ {1} + \Delta_ {2}) / 2}}. \tag{3.70}
$$

特殊共形变换的 Ward 恒等式从对易子 (3.61) 获得，给出

$$
\left(2 x ^ {\mu} x ^ {\nu} \partial_ {\nu} - x ^ {2} \partial^ {\mu} + 2 \Delta_ {2} x ^ {\mu}\right) \langle 0 | \phi_ {1} (0) \phi_ {2} (x) | 0 \rangle = 0. \tag{3.71}
$$

使用 $\partial_\mu [(x^2)^{-(\Delta_1+\Delta_2)/2}] = -(\Delta_1+\Delta_2) x_\mu/x^2$，这意味着

$$
\left(\Delta_ {2} - \Delta_ {1}\right) C _ {1 2} \frac {x ^ {\mu}}{\left(x ^ {2}\right) ^ {\left(\Delta_ {1} + \Delta_ {2}\right) / 2}} = 0. \tag{3.72}
$$

如果标度维度不同 ($\Delta_1 \neq \Delta_2$)，则 $C_{12}$ 必须为零。这是一个重要的教训：在共形场论中，只有具有相同标度维度的 primary 算符才能有非零的 2 点函数。

事实上，如果有多个具有相同标度维度 $\Delta$ 的标量算符 $\phi_i, i=1,\dots,N$，那么

$$
\langle 0 | \phi_ {i} (0) \phi_ {j} (x) | 0 \rangle = \frac {C _ {i j}}{(x ^ {2}) ^ {\Delta}}, \tag{3.73}
$$

其中 $C_{ij}$ 是一个对称的 $N\times N$ 矩阵。根据幺正性，这个矩阵必须是正定的：如果不是这样，那么可以通过取 $\phi_i$ 的适当线性组合并进行涂抹来定义一个负范数态。因此，总是可以选择一个算符基，使得 $C_{ij}$ 是对角的。此外，可以对算符进行归一化，使得 $C_{ij} = \delta_{ij}$。从现在起，我们将总是假设只有相同算符的非零 2 点函数。

**具有自旋的算符**：特殊共形对称性发挥重要作用的另一种情况是当算符带有自旋时。让我们以矢量算符 $A^\mu(x)$ 为例，将其 2 点函数记为

$$
W ^ {\mu \nu} (x) = \langle 0 | A ^ {\mu} (0) A ^ {\nu} (x) | 0 \rangle . \tag{3.74}
$$

与标量类似，也可以取这个缓增分布的傅里叶变换，定义

$$
\widetilde {W} ^ {\mu \nu} (p) = \int d ^ {d} x e ^ {i p \cdot x} \langle 0 | A ^ {\mu} (0) A ^ {\nu} (x) | 0 \rangle = \langle 0 | A ^ {\mu} (0) \widetilde {A} ^ {\nu} (p) | 0 \rangle . \tag{3.75}
$$

同样，这个函数对应于没有施加动量守恒 delta 函数的动量空间关联函数，即

$$
\langle 0 | \widetilde {A} ^ {\mu} (p) \widetilde {A} ^ {\nu} (q) | 0 \rangle = (2 \pi) ^ {d} \delta^ {d} (p + q) \widetilde {W} ^ {\mu \nu} (q). \tag{3.76}
$$

根据洛伦兹对称性，单个动量的函数 $\widetilde{W}$ 可以分解为两个不同的张量结构乘以标量函数，

$$
\widetilde {W} ^ {\mu \nu} (p) = (p ^ {\mu} p ^ {\nu} - p ^ {2} \eta^ {\mu \nu}) \widetilde {W} _ {1} (p) + p ^ {\mu} p ^ {\nu} \widetilde {W} _ {0} (p). \tag{3.77}
$$

此外，使用标度对称性和能量正定性，可以推断函数 $\widetilde{W}_{1,0}$ 只是前向光锥上 $p^2$ 的幂次，

$$
\widetilde {W} _ {1, 0} (p) = \theta \left(p ^ {0} - | \vec {p} |\right) (- p ^ {2}) ^ {\Delta - d / 2 - 1} C _ {1, 0}, \tag{3.78}
$$

其中 $\Delta$ 是算符 $A^\mu$ 的标度维度，$C_1, C_0$ 是两个不能仅由标度和庞加莱对称性关联起来的常数。

在方程 (3.77) 中使用恰好这两个张量结构而非比如 $\eta^{\mu\nu}$ 和 $p^\mu p^\nu$ 是有充分理由的。由于能量正定性，总可以选择一个 $\vec{q}=0$ 的洛伦兹参考系[5]。在这个参考系中，动量在空间旋转群 $SO(d-1)$ 下不变，因此 2 点函数可以分解为该群的不可约表示。正比于 $C_0$ 的部分只出现在分量 $\widetilde{W}^{00}$ 中，它像一个标量一样在旋转下变换。相反，正比于 $C_1$ 的部分只在空间洛伦兹指标 $\widetilde{W}^{ij}$ 上有非零条目；它实际上正比于 $d-1$ 维子空间中的单位矩阵，即它是 $SO(d-1)$ 的矢量表示的不变张量。用粒子物理的语言，我们将这两部分分别称为纵向和横向。

能够在动量空间使用 $SO(d-1)$ 的不可约表示是在动量空间工作的一个优势：在位置空间没有明显的洛伦兹参考系可以进行这样的分解，因为 2 点函数在整个闵可夫斯基时空都有支撑。在动量空间工作的缺点是特殊共形变换的 Ward 恒等式是 $p$ 的二阶微分方程，而在位置空间是一阶的。然而，这个 Ward 恒等式仍可以直接应用于方程 (3.77)，并给出纵向和横向部分之间的关系，即系数 $C_0$ 和 $C_1$ 之间的关系，由下式给出（见练习）

$$
C _ {0} = \frac {\Delta - d + 1}{\Delta - 1} C _ {1}. \tag{3.79}
$$

这是特殊共形对称性的一个非常重要的结果：在标度不变的理论中，纵向和横向极化是独立的，而在共形理论中，它们是相关的。

**练习 3.4** 使用函数 $\widetilde{W}^{\mu\nu}(p)$ 的定义 (3.75)，证明它满足特殊共形 Ward 恒等式
$$
\left(2 p ^ {\beta} \frac {\partial^ {2}}{\partial p _ {\alpha} \partial p ^ {\beta}} - p ^ {\alpha} \frac {\partial^ {2}}{\partial p _ {\beta} \partial p ^ {\beta}} + 2 (d - \Delta) \frac {\partial}{\partial p _ {\alpha}} + 2 \mathcal {S} ^ {\alpha \beta} \frac {\partial}{\partial p _ {\beta}}\right) \widetilde {W} ^ {\mu \nu} (p) = 0,
$$
其中 $S^{\alpha\beta}$ 由方程 (3.5) 给出，并用它来证明关系 (3.79)。

这对 $\Delta$ 的可能取值有影响。和之前一样，这个 2 点函数计算一个态的范数，其正定性要求：
- $\Delta > d/2$，使得 2 点函数在 $p^2 \to 0$ 时可积；
- $C_0$ 和 $C_1$ 都为正，使得对于任何外部极化矢量的选择范数为正（即张量 $\widetilde{W}^{\mu\nu}$ 必须是正定的）。这要求 $\Delta-1$ 和 $\Delta-d+1$ 具有相同的符号。

在 $d>2$ 维（$d=2$ 时自旋的处理方式不同）中，这两个条件的组合意味着

$$
\Delta \geq d - 1. \tag{3.80}
$$

这被称为矢量算符的幺正性界。

与标量情况一样，当幺正性界饱和时 ($\Delta = d-1$)，会发生一些特殊的事情。在这种情况下，2 点函数没有纵向分量，$C_0 = 0$，并且 $\widetilde{W}^{\mu\nu}$ 在与 $p_\mu$ 或 $p_\nu$ 缩并时为零。这意味着态的纵向部分是零范数的，

$$
p _ {\mu} \widetilde {A} ^ {\mu} (p) | 0 \rangle = 0, \tag{3.81}
$$

或者等价地，$\widetilde{A}^\mu(p)$ 是一个只产生横向极化态的算符。位置空间中的等价陈述是

$$
\partial_ {\mu} A ^ {\mu} (x) \left| 0 \right\rangle = 0. \tag{3.82}
$$

换句话说，$A^\mu$ 是一个守恒流。等价性双向成立：任何 $\Delta = d-1$ 的矢量算符都是守恒流，任何守恒流必须具有标度维度 $\Delta = d-1$。这也表明守恒流是 primary 算符：它们不能写成 $\partial^2$ 作用于另一个矢量算符（那个算符的 $\Delta = d-3$，低于幺正性界），也不能写成 $\partial^\mu$ 作用于一个标量算符 $\phi$，因为守恒要求会意味着 $\partial^2\phi = 0$，这仅在 $\phi$ 的标度维度为 $(d-2)/2$ 时才可能，从而使得流的 $\Delta = d/2$（再次低于幺正性界）。

Primary 算符的 2 点函数完全由共形对称性固定，直至一个归一化选择，这一事实并不特定于标量和矢量算符。事实上，任何由洛伦兹群的表示和标度维度指定的局域算符都定义了共形群 $SO(d,2)$ 的一个不可约表示，因此其 2 点函数由群论固定。这也从更一般的角度解释了为什么不同算符的 2 点函数为零。在 $d=4$ 维中，共形群的所有酉表示的构造由 Mack 于 1975 年完成 [1]，类似的构造可以在其他维度中进行。一些洛伦兹表示特定于给定的维度 $d$，而其他表示存在于任何 $d$ 中，比如具有 $\ell$ 个洛伦兹指标的对称无迹表示（上面讨论的矢量对应于 $\ell=1$ 的特例）。所有这样的对称张量都满足幺正性界

$$
\Delta \geq d - 2 + \ell , \tag{3.83}
$$

它们通常由 $\ell+1$ 个不同的极化（旋转群的不可约表示）来描述，除非在饱和界时，此时只有一个单一的横向极化，并且该算符是一个更高自旋的守恒流。就共形群的表示而言，一般的算符被称为属于长多重态，而特殊情况，如 $\Delta = (d-2)/2$ 的标量或 $\Delta = d-2+\ell$ 的对称张量，被称为属于短多重态（它们包含较少的 descendant）。

**练习 3.5** 显式构造一个 2 指标对称无迹算符 $B^{\mu\nu}(x)$ 的 2 点函数。作为起点，将动量空间关联函数分解为在静止系中旋转协变的张量。使用横向投影算符
$$
\eta_ {\perp} ^ {\mu \nu} = \eta^ {\mu \nu} - \frac {p ^ {\mu} p ^ {\nu}}{p ^ {2}}
$$
满足 $p_\mu \eta_\perp^{\mu\nu}=0$，可以这样分解：
$$
\begin{array}{l} \langle 0 | B ^ {\mu \nu} (0) \widetilde {B} ^ {\rho \sigma} (p) | 0 \rangle = \left[ \frac {1}{2} \left(\eta_ {\perp} ^ {\mu \rho} \eta_ {\perp} ^ {\nu \sigma} + \eta_ {\perp} ^ {\mu \sigma} \eta_ {\perp} ^ {\nu \rho} - \operatorname{traces}\right) C _ {2} \right. \\ + \frac {1}{4} \left(\eta_ {\perp} ^ {\mu \rho} \frac {p ^ {\nu} p ^ {\sigma}}{p ^ {2}} + \text { permutations }\right) C _ {1} \\ \left. + \frac {p ^ {\mu} p ^ {\nu} p ^ {\rho} p ^ {\sigma}}{(p ^ {2}) ^ {2}} C _ {0} \right] \theta (p ^ {0} - | \vec {q} |) (- p ^ {2}) ^ {\Delta - d / 2 + 1}. \\ \end{array}
$$
然后写下特殊共形变换的 Ward 恒等式（包括 2 指标张量的自旋算符，你需要确定它），并证明它导致条件
$$
\begin{array}{l} C _ {1} = 2 \frac {\Delta - d}{\Delta} C _ {0}, \\ C _ {2} = \frac {d}{d - 1} \frac {(\Delta - d) (\Delta - d + 1)}{\Delta (\Delta - 1)} C _ {0}. \\ \end{array}
$$
论证这给出了幺正性界 $\Delta \geq d$，与方程 (3.83) 一致。得出结论，能动张量 $T^{\mu\nu}$ 是一个 $\Delta = d$ 的 primary 算符。

## 3.6 UV/IR 发散与反常

到目前为止，讨论主要集中在 Wightman 函数上。除了具有希尔伯特空间解释并满足共形 Ward 恒等式（对其可能形式给出强约束）之外，Wightman 函数还没有发散。在动量空间中，小动量（IR）的正则性由幺正性界强制执行，而大动量（UV）的幂律增长与测试函数提供的阻尼兼容。在位置空间中，短距离（UV）的表观奇点由 $i\varepsilon$ 解决，它为任何积分轮廓的变形提供了明确的规则。

这些性质在时间序乘积中并不存在。让我们再次考虑标量 2 点函数。使用标准 CFT 归一化 (3.57) 和 Källen-Lehmann 表示，我们得到

$$
\langle \phi (x) \phi (y) \rangle_ {T} = - i \frac {(4 \pi) ^ {d / 2} \Gamma (\frac {d}{2} - \Delta)}{2 ^ {2 \Delta} \Gamma (\Delta)} \int \frac {d ^ {d} k}{(2 \pi) ^ {d}} e ^ {i k \cdot (x - y)} (k ^ {2} - i \varepsilon) ^ {\Delta - d / 2}. \tag{3.84}
$$

每当 $\Delta = d/2 + n$ 且 $n$ 为整数时，由于乘在积分前的 $\Gamma$ 函数，这个表达式发散，表明傅里叶变换不存在。在这种情况下，2 点函数具有标度维度 $d+2n$，因此与形如

$$
(\partial^ {2}) ^ {n} \delta^ {d} (x - y). \tag{3.85}
$$

的接触项兼容。在路径积分语言中，这是源场 $J$ 对于算符 $\phi$ 的标度维度为 $d-\Delta = d/2 - n$ 的情况，因此形如 $J (\partial^2)^n J$ 的接触项可以（并且必须）添加到作用量中。这些接触项显然在庞加莱和标度变换下是协变的，因此它们可以在不影响分离点处 Ward 恒等式的情况下添加到关联函数中。(3.85) 是标量 2 点函数中唯一可能出现的接触项，但其他关联函数中可能出现更多项。

当傅里叶变换到动量空间时，所有这些接触项都变成动量的多项式。在标量 2 点函数的情况下，它们是 $(p^2)^n$。多项式项与 Wightman 函数的正能量条件不兼容，因为它们在所有因果区域都有支撑。但它们在时间序乘积中是允许的（实际上是必需的）。时间序乘积在位置空间中被定义为 Wightman 函数（它们是缓增分布）与阶跃函数（它们不是）的乘积：因此它们不一定有傅里叶变换。接触项可以被视为“修正”时间序乘积使其可以进行傅里叶变换的一种方式。

这可以通过对标度维度 $\Delta$ 进行解析延拓来理解。假设我们的标量算符的标度维度为 $\Delta = d/2 + n - \epsilon$，并取极限 $\epsilon \to 0$（注意这个 $\varepsilon$ 与 $i\varepsilon$ 极限中的不同）。那么动量空间中的时间序 2 点函数的形式为

$$
\Gamma (- n + \epsilon) (p ^ {2}) ^ {n - \epsilon} + Z (p ^ {2}) ^ {n}, \tag{3.86}
$$

其中第一项在 $\varepsilon$ 处有极点，来自在 $x\neq y$ 处有效的表达式 (3.84)，第二项是添加到作用量的抵消项。选择 $Z \propto \varepsilon^{-1}$ 可以抵消 $\epsilon \to 0$ 时的发散，但也会产生一个对数，

$$
(p ^ {2}) ^ {n} \log \left(\frac {p ^ {2}}{\mu^ {2}}\right). \tag{3.87}
$$

我们需要引入一个有量纲量 $\mu$ 的事实是共形反常的标志：这种形式的 2 点函数不满足标度变换的 Ward 恒等式 (3.41)，

$$
\left[ - p ^ {\mu} \frac {\partial}{p ^ {\mu}} + 2 n \right] (p ^ {2}) ^ {n} \log \left(\frac {p ^ {2}}{\mu^ {2}}\right) = - 2 (p ^ {2}) ^ {n} \neq 0. \tag{3.88}
$$

然而，右侧的反常项是动量的多项式，对应于一个接触项，表明反常是局域的。在 QFT 语言中，这是典型的（重整化后的）UV 发散。

注意，接触项的存在与具有（半）整数标度维度的非常特殊类型的算符相关联。在相互作用的共形场论中，标度维度通常取无理数值，因此这类算符通常不存在。然而，这个规则的一个例外是在偶数时空维度 $d$ 中的守恒流。例如，$d=4$ 中的守恒流 $J^\mu$ 具有标度维度 $\Delta=3$；因此在路径积分语言中，它与一个维度为 $1$ 的源 $a_\mu$ 相关联。这个源还受到规范对称性的约束，$a_\mu \sim a_\mu + \partial_\mu\alpha$，因此一个可能的接触项是 $f_{\mu\nu}f^{\mu\nu}$，其中 $f_{\mu\nu} = \partial_\mu a_\nu - \partial_\nu a_\mu$。与标量情况一样，该项必须用作抵消项来消除时间序关联函数中出现的发散，通常会导致涉及流横向极化的关联函数中出现对数，

$$
\langle J ^ {\mu} (p) J ^ {\nu} (q) \rangle_ {T} \propto (2 \pi) ^ {4} \delta^ {4} (p + q) (q ^ {\mu} q ^ {\nu} - q ^ {2} \eta^ {\mu \nu}) \log \left(\frac {q ^ {2}}{\mu^ {2}}\right). \tag{3.89}
$$

与标量情况一样，这是 UV 发散的表现。然而，对数也意味着极限 $q^2 \to 0$ 是发散的：这就是我们在量子场论中称为 IR 发散的东西。在 CFT 的背景下，UV 和 IR 发散之间没有明确的区别，因为两者密切相关。它们都源于傅里叶变换的歧义性。UV 发散可以用局域抵消项来治愈，但代价是引入一个参考标度，而 IR 发散是物理的。

最后注意，涉及守恒流的时间序关联函数不仅具有横向极化：虽然守恒条件意味着态

$$
\partial_ {\mu} J ^ {\mu} (x) \left| 0 \right\rangle = 0, \tag{3.90}
$$

的消失，从而由该态构造的 Wightman 关联函数也为零，但这对于出现在时间序乘积中的 $J^\mu$ 的散度并不成立：守恒方程 $\partial_\mu J^\mu(x)=0$ 仅在作为算符方程，即在非重合点处成立。一般而言，我们期望

$$
\begin{array}{l} \langle \phi_ {1} (x _ {1}) \cdot \cdot \cdot \phi_ {n} (x _ {n}) \partial_ {\mu} J ^ {\mu} (y) \rangle_ {T} = - \delta^ {d} (x _ {1} - y) \langle \delta \phi_ {1} (x _ {1}) \cdot \cdot \cdot \phi_ {n} (x _ {n}) \rangle_ {T} \\ - \dots \\ - \delta^ {d} (x _ {n} - y) \langle \phi_ {1} (x _ {1}) \dots \delta \phi_ {n} (x _ {n}) \rangle_ {T}, \tag{3.91} \\ \end{array}
$$

其中 $\delta\phi_i$ 表示场 $\phi_i$ 在 $J^\mu$ 下的荷[6]。

# 第四章 共形关联函数

上一节中介绍的使用共形 Ward 恒等式和 Wightman 公理的方法原则上可以用来确定 3 点及更高点的关联函数[1]。然而，这相当不方便，并且隐藏了结果的简洁性。为了说明这一点，请注意，标量算符的 Wightman 3 点函数在动量空间中的构造直到 2019 年才完成 [3, 4][2]，而位置空间的关联函数自 1970 年 Polyakov 的工作以来就已为人所知 [7]。

## 4.1 从闵可夫斯基时空到欧几里得空间

首先，回到标量算符的 Wightman 2 点函数，它在位置空间中由下式给出

$$
W (x) = \frac {1}{\left[ - (x ^ {0} + i \varepsilon) ^ {2} + \vec {x} ^ {2} \right] ^ {\Delta}}. \tag{4.1}
$$

这个 2 点函数及其 $i\varepsilon$ 规则的定义表明 $x^0$ 应被视为一个复变量：作为复变量 $x^0$ 的函数，$W$ 在上半复平面解析。取 $x^0$ 为纯虚数，即

$$
x ^ {0} = i \tau , \quad \tau > 0, \tag{4.2}
$$

我们得到 Schwinger 函数

$$
\langle \phi (0) \phi (x _ {E}) \rangle = \frac {1}{(\tau^ {2} + \vec {x} ^ {2}) ^ {\Delta}} \equiv \frac {1}{(x _ {E} ^ {2}) ^ {\Delta}}. \tag{4.3}
$$

我们用 $x_E = (\tau, \vec{x})$ 表示与 $d$ 维欧几里得度规缩并的欧几里得矢量。Schwinger 函数将始终使用“平均”符号 $\langle \cdot \cdot \cdot \rangle$ 来写，而 Wightman 函数 $\langle 0 | \cdots | 0 \rangle$ 可以解释为真空期望值；由于这两类函数不会混淆，我们将用 $x$ 代替 $x_E$ 来表示欧几里得坐标，尽管暗示了后者。

注意，Schwinger 函数在欧几里得共形群 $SO(d+1,1)$ 下协变变换，该群通过将闵可夫斯基度规替换为欧几里得度规得到。这包括平移和 $SO(d)$ 旋转，因此我们有

$$
\langle \phi (0) \phi (x) \rangle \stackrel {\text { rotation }} {=} \langle \phi (0) \phi (- x) \rangle \stackrel {\text { translation }} {=} \langle \phi (x) \phi (0) \rangle , \tag{4.4}
$$

展示了一个在交换两个算符顺序下的新对称性。还要注意，Schwinger 2 点函数是正的，并且在点 $x_E = 0$ 处没有定义，这与 Wightman 函数不同，后者的 $i\varepsilon$ 规则指示了如何接近任何类零点。

**练习 4.1** 有另一种方法可以得到相同的结果，从 2 点函数的动量空间表示出发。Wightman 函数不太适合这样做（至少在不探索由微观因果性公理导出的解析性性质的情况下），但时间序函数是适合的：从 Källen-Lehmann 表示 (3.84) 开始，在动量空间中变为（使用动量守恒 delta 函数隐含的符号）

$$
\langle \phi (- p) \phi (p) \rangle_ {T} = - i \frac {(4 \pi) ^ {d / 2} \Gamma \left(\frac {d}{2} - \Delta\right)}{2 ^ {2 \Delta} \Gamma (\Delta)} \left(p ^ {2} - i \varepsilon\right) ^ {\Delta - d / 2},
$$

可以执行 Wick 旋转，其中 $x^0$ 和 $p^0$ 同时在复平面中沿相反方向旋转，得到欧几里得结果

$$
\langle \phi (- p _ {E}) \phi (p _ {E}) \rangle = \frac {(4 \pi) ^ {d / 2} \Gamma \left(\frac {d}{2} - \Delta\right)}{2 ^ {2 \Delta} \Gamma (\Delta)} \left(p _ {E} ^ {2}\right) ^ {\Delta - d / 2}.
$$

对 $p_E$ 进行傅里叶变换以恢复 Schwinger 函数 (4.3)。注意，你需要对 $\Delta$ 做出假设以使傅里叶积分收敛。然而，结果在 $\Delta$ 中是解析的，因此你可以事后论证它必须对所有标度维度都有效。

这种通过从 Wightman 函数解析延拓构造欧几里得函数的方法实际上可以推广到任意数量的算符。考虑 $n$ 点 Wightman 函数，参数化为

$$
\langle 0 | \phi_ {n} (x _ {n} - x _ {n - 1}) \phi_ {n - 1} (x _ {n - 1} - x _ {n - 2}) \dots \phi_ {2} (x _ {2} - x _ {1}) \phi_ {1} (x _ {1}) | 0 \rangle , \tag{4.5}
$$

并将所有时间分量 $x_i^0$ 复化。这个多复变量（以及更多实变量）的函数实际上在每个上半复平面 $x_1^0$ 到 $x_n^0$ 中都是解析的，因为它可以写成一个函数的傅里叶变换，该函数仅在对偶变量 $p_1^0$ 到 $p_n^0$ 都为正时有支撑[3]。因此，取纯虚时间 $x_i^0 = i\tau_i$，我们得到 Schwinger $n$ 点函数

$$
\langle \phi_ {n} (x _ {n} - x _ {n - 1}) \dots \phi_ {2} (x _ {2} - x _ {1}) \phi_ {1} (x _ {1}) \rangle , \tag{4.6}
$$

其中所有欧几里得时间满足 $\tau_i > 0$，即算符沿欧几里得时间方向排序。然而，后一个观察是无关紧要的，因为算符的顺序在 Schwinger 函数中无关紧要：解析延拓可以从所有真实闵可夫斯基时间相等的构型开始，在这种情况下，根据微观因果性，算符是对易的。因此，对 2 点函数所做的观察更普遍地成立：

- Schwinger 函数在算符交换下是对称的。

之前所做的其他观察通常也成立：

- Schwinger 函数在欧几里得共形群 $SO(d+1,1)$ 下协变变换。这个性质将非常有用，因为这意味着我们可以使用在欧几里得空间中表现良好（包括在 $\infty$ 点）的有限共形变换来简化计算。
- Schwinger 函数在重合点没有定义。这不是一个缺陷，而是一个特性：使用仅在分离点定义的函数意味着我们不需要担心接触项和 UV 发散[4]。然而，这意味着我们不能简单地对这些函数进行傅里叶变换来获得动量空间 Schwinger 函数。
- Schwinger 函数享有反射正性性质：如果算符组织在某个平面的反射下不变的构型中（例如，正方形的四个角；或者平凡地任意两点），那么关联函数是正的[5]。

我们已经看到 Wightman 函数通过解析延拓定义 Schwinger 函数。但事实证明，反过来也成立：Osterwalder-Schrader 定理指出，上面列出的 Schwinger 函数的性质足以重建 Wightman 函数[6]。这意味着我们实际上可以专注于欧几里得 Schwinger 函数以满足我们所有的目的，因为任何其他物理可观测量都可以从中重建（尽管我们不声称这种重建是容易的）。

我们将从第 3 章的分析中仅保留的信息是算符标度维度的幺正性界。纯粹从 Schwinger 函数推导出这些界也是可能的 [11]，但我们在这里不讨论这个过程。

## 4.2 从欧几里得空间到嵌入空间

一旦我们处理的关联函数在欧几里得共形群 $SO(d+1,1)$ 下变换，利用与 $(d+2)$ 维洛伦兹群的类比来获得优势就非常有意义[7]。我们已经在第 2 章中引入了一组在这个 $(d+2)$ 维嵌入空间中的坐标，以及满足下式的度规

$$
\eta_ {M N} d X ^ {M} d X ^ {N} = (d X ^ {\mu}) ^ {2} + (d X ^ {d + 1}) ^ {2} - (d X ^ {d + 2}) ^ {2}. \tag{4.7}
$$

注意，指标 $\mu$ 标记的方向都是类空的：类时方向是 $X^{d+2}$。

问题是如何从 $X^M \in \mathbb{R}^{d+1,1}$ 到达 $x^\mu \in \mathbb{R}^d$ 而不显式破坏 $(d+2)$ 维洛伦兹对称性。这可以通过两步完成：

1. 将注意力限制在未来光锥 $X^2 = 0$ 且 $X^{d+2} > 0$ 上，这是一个不变子空间。
2. 识别该光锥上由标度变换相关的任意两点，即 $X^M \sim \lambda X^M$，其中 $\lambda > 0$。

这意味着我们本质上是在考虑 $d$ 维欧几里得空间中的点 $x^\mu$ 与 $(d+2)$ 维闵可夫斯基时空中的一条光线之间的映射。为了使映射显式化，我们选择光锥的一个截面，我们将取为 $X^{d+1} + X^{d+2} = 1$，并做如下等同

$$
X ^ {\mu} = x ^ {\mu}, \quad X ^ {d + 1} = \frac {1 - x ^ {2}}{2}, \quad X ^ {d + 2} = \frac {1 + x ^ {2}}{2}. \tag{4.8}
$$

共形变换现在在嵌入空间中线性作用，

$$
X ^ {M} \rightarrow X ^ {\prime M} = \Lambda_ {N} ^ {M} X ^ {N} \tag{4.9}
$$

为了得到对 $x^\mu$ 的作用，我们首先使用方程 (4.8) 将其映射到我们首选的光锥截面上，应用洛伦兹变换于 $X^M$，然后执行一个（与时空相关的）重新标度 $X^{\prime M} \to \lambda(X') X^{\prime M}$ 以回到首选截面，并读出 $x^{\prime \mu} = \lambda(X') X^{\prime \mu}$。

欧几里得空间中的局域算符也必须提升到嵌入空间，或者至少提升到零锥上。在我们首选的截面上，我们定义

$$
\phi (X) \equiv \phi (x), \quad \left(X ^ {2} = 0, X ^ {d + 1} + X ^ {d + 2} = 1\right). \tag{4.10}
$$

然后，primary 算符通过标度规则定义在光锥的其他部分

$$
\phi (\lambda X) = \lambda^ {- \Delta} \phi (X). \tag{4.11}
$$

注意，这个规则只能应用于 primary 算符：通过作用导数得到的 descendant 不满足相同的标度性质。这个选择给出了所有无穷小共形变换下 primary 算符的正确变换规则。这可以显式验证（见下面的练习），或者论证如下：一个共形变换是一个 $(d+2)$ 维洛伦兹变换（局部作用于算符如同旋转或推动），接着是一个与位置相关的标度变换以回到首选截面，根据规则 (4.11)，这相当于一个权重为标度维度 $\Delta$ 的局域标度变换。这两种局域变换的组合正是我们期望的算符的共形变换。

**练习 4.2** 验证在 $X^{d+1}$ 方向上的洛伦兹推动对应于欧几里得空间中的标度变换，与方程 (2.39) 一致，并且算符相应地变换。

在射影零锥上定义带有自旋的算符需要更加小心，因为 $X^{d+1}$ 和 $X^{d+2}$ 方向上的额外洛伦兹指标意味着需要约束额外的自由度 [13]。这可以通过在嵌入空间中施加横向性以及一个规范对称性条件来实现。但我们不想在这里深入这个技术细节。因此，我们将只关注标量 primary 算符的关联函数。

一旦局域算符的变换性质明确，构造 $n$ 个点 $X_1$ 到 $X_n$ 的关联函数遵循两个简单的规则：

- 关联函数必须依赖于嵌入空间中的洛伦兹不变量，即形如 $X_i\cdot X_j$ 的标量积。由于在零锥上 $X_i^2 = 0$，只有 $i\neq j$ 的标量积可以出现。
- 应用局域标度变换 $X^M \to \lambda(X) X^M$，在此变换下所有标度维度为 $\Delta_i$ 的 primary 算符 $\phi_i$ 满足
  $$
  \phi_ {i} (X _ {i}) \rightarrow \lambda (X _ {i}) ^ {- \Delta_ {i}} \phi_ {i} (X _ {i}), \tag{4.12}
  $$
  那么关联函数必须齐次变换为
  $$
  \langle \phi_ {1} (X _ {1}) \dots \phi_ {n} (X _ {n}) \rangle \rightarrow \lambda (X _ {1}) ^ {- \Delta_ {1}} \dots \lambda (X _ {n}) ^ {- \Delta_ {n}} \langle \phi_ {1} (X _ {1}) \dots \phi_ {n} (X _ {n}) \rangle . \tag{4.13}
  $$

这些规则立即意味着不可能存在单点函数，因为在射影零锥上没有相应的洛伦兹不变量。最简单的非平凡情况是 2 点函数，它必须满足

$$
\langle \phi (X _ {1}) \phi (X _ {2}) \rangle \propto (X _ {1} \cdot X _ {2}) ^ {- \Delta}. \tag{4.14}
$$

注意，只有当两个算符具有相同的标度维度时，这才与齐次标度规则一致，这是第 3 章中通过艰难方式推导出的另一个性质。为了恢复对 $d$ 维欧几里得坐标的依赖性，我们只需使用等同 (4.8)，得到

$$
X _ {1} \cdot X _ {2} = - \frac {1}{2} (x _ {1} - x _ {2}) ^ {2}. \tag{4.15}
$$

在上述方程中固定比例因子后，我们恢复了预期的结果

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \rangle = \frac {1}{\left[ (x _ {1} - x _ {2}) ^ {2} \right] ^ {\Delta}}. \tag{4.16}
$$

## 4.3 3 点函数

当检查 3 点函数时，嵌入空间形式主义变得非常有趣

$$
\langle \phi_ {1} (X _ {1}) \phi_ {2} (X _ {2}) \phi_ {3} (X _ {3}) \rangle , \tag{4.17}
$$

其中 3 个标量算符现在可能具有不同的标度维度 $\Delta_1$、$\Delta_2$ 和 $\Delta_3$。求解这个 3 点函数的共形 Ward 恒等式将是一项烦人的任务。相反，根据上述规则，我们立即知道这是 3 个不变量的函数

$$
X _ {1} \cdot X _ {2}, \quad X _ {1} \cdot X _ {3}, \quad X _ {2} \cdot X _ {3}. \tag{4.18}
$$

此外，根据齐次标度规则，3 点函数唯一可能的形式是

$$
\left\langle \phi_ {1} (X _ {1}) \phi_ {2} (X _ {2}) \phi_ {3} (X _ {3}) \right\rangle \propto (X _ {1} \cdot X _ {2}) ^ {\alpha_ {1 2}} (X _ {1} \cdot X _ {3}) ^ {\alpha_ {1 3}} (X _ {2} \cdot X _ {3}) ^ {\alpha_ {2 3}} \tag{4.19}
$$

指数满足

$$
\alpha_ {1 2} + \alpha_ {1 3} = - \Delta_ {1},
$$

$$
\alpha_ {1 2} + \alpha_ {2 3} = - \Delta_ {2}, \tag{4.20}
$$

$$
\alpha_ {1 3} + \alpha_ {2 3} = - \Delta_ {3}.
$$

这个方程组有唯一解

$$
\alpha_ {1 2} = - \frac {\Delta_ {1} + \Delta_ {2} - \Delta_ {3}}{2},
$$

$$
\alpha_ {1 3} = - \frac {\Delta_ {1} + \Delta_ {3} - \Delta_ {2}}{2}, \tag{4.21}
$$

$$
\alpha_ {2 3} = - \frac {\Delta_ {2} + \Delta_ {3} - \Delta_ {1}}{2}. \tag{4.22}
$$

用欧几里得坐标表示，可以写成

$$
\langle \phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) \phi_ {3} (x _ {3}) \rangle = \frac {\lambda_ {1 2 3}}{(x _ {1 2} ^ {2}) ^ {\Delta_ {1 2 , 3}} (x _ {1 3} ^ {2}) ^ {\Delta_ {1 3 , 2}} (x _ {2 3} ^ {2}) ^ {\Delta_ {2 3 , 1}}}, \tag{4.23}
$$

其中我们引入了紧凑记号

$$
x _ {i j} ^ {2} = (x _ {i} - x _ {j}) ^ {2}, \tag{4.24}
$$

以及

$$
\Delta_ {i j, k} = \frac {\Delta_ {i} + \Delta_ {j} - \Delta_ {k}}{2}. \tag{4.25}
$$

方程 (4.23) 确实很特别。应该将其与仅庞加莱和标度对称性不变的最一般 3 点函数进行比较：在这种情况下，任何形式为

$$
(x _ {1 2} ^ {2}) ^ {\alpha} (x _ {1 3} ^ {2}) ^ {\beta} (x _ {2 3} ^ {2}) ^ {\gamma} \tag{4.26}
$$

且满足

$$
\alpha + \beta + \gamma = \frac {\Delta_ {1} + \Delta_ {2} + \Delta_ {3}}{2} \tag{4.27}
$$

的项都满足对称性要求，因此 3 点函数可能具有形式

$$
\langle \phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) \phi_ {3} (x _ {3}) \rangle = \sum_ {i} \frac {c _ {i}}{(x _ {1 2} ^ {2}) ^ {\alpha_ {i}} (x _ {1 3} ^ {2}) ^ {\beta_ {i}} (x _ {2 3} ^ {2}) ^ {\gamma_ {i}}}, \tag{4.28}
$$

具有无限多个自由系数 $c_i$。而共形 3 点函数 (4.23) 被固定到唯一的乘法系数 $\lambda_{123}$。

为了给出另一个比较点，让我们考察一个涉及 descendant 算符的 3 点函数。由于关注标量算符，让我们在 (4.23) 中的第一个算符上作用 $\partial_\mu\partial^\mu$：

$$
\begin{array}{l} \langle \partial^ {2} \phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) \phi_ {3} (x _ {3}) \rangle = 4 \lambda_ {1 2 3} \left[ \frac {\left(\Delta_ {1} - \frac {d - 2}{2}\right) \Delta_ {1 2 , 3}}{\left(x _ {1 2} ^ {2}\right) ^ {\Delta_ {1 2 , 3} + 1} \left(x _ {1 3} ^ {2}\right) ^ {\Delta_ {1 3 , 2}} \left(x _ {2 3} ^ {2}\right) ^ {\Delta_ {2 3 , 1}}} \right. \\ + \frac {\left(\Delta_ {1} - \frac {d - 2}{2}\right) \Delta_ {1 3 , 2}}{\left(x _ {1 2} ^ {2}\right) ^ {\Delta_ {1 2 , 3}} \left(x _ {1 3} ^ {2}\right) ^ {\Delta_ {1 3 , 2} + 1} \left(x _ {2 3} ^ {2}\right) ^ {\Delta_ {2 3 , 1}}} \\ \left. + \frac {\Delta_ {1 2 , 3} \Delta_ {1 3 , 2}}{\left(x _ {1 2} ^ {2}\right) ^ {\Delta_ {1 2 , 3} + 1} \left(x _ {1 3} ^ {2}\right) ^ {\Delta_ {1 3 , 2} + 1} \left(x _ {2 3} ^ {2}\right) ^ {\Delta_ {2 3 , 1} - 1}} \right]. \tag{4.29} \\ \end{array}
$$

与 primary 算符的关联函数不同，这现在是三个具有不同距离 $x_{ij}^2$ 幂次的项之和，所有这些项单独与庞加莱和标度对称性兼容。

所有三项的系数都很特殊：实际上存在一些特殊情况，这个 3 点函数具有方程 (4.23) 的一般形式，即涉及 primary 算符的关联函数的形式。这些特殊情况并非偶然，而是对应于物理上有趣的情形：

- 如果 $\Delta_1 = |\Delta_2 - \Delta_3|$，那么要么 $\Delta_{12,3}=0$，要么 $\Delta_{13,2}=0$，在这两种情况下，方程 (4.29) 右侧的两项消失。这是一种非常特殊的情况，其中 primary 3 点函数因式分解为 2 点函数的乘积，例如当 $\Delta_3 = \Delta_1 + \Delta_2$ 时，
  $$
  \langle \phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) \phi_ {3} (x _ {3}) \rangle = \frac {\lambda_ {1 2 3}}{(x _ {1 3} ^ {2}) ^ {\Delta_ {1}} (x _ {2 3} ^ {2}) ^ {\Delta_ {2}}} \propto \langle \phi_ {1} (x _ {1}) \phi_ {1} (x _ {3}) \rangle \langle \phi_ {2} (x _ {2}) \phi_ {2} (x _ {3}) \rangle . \tag{4.30}
  $$
  这种情况在广义自由场论中实现（下文第 6 章定义），其中 $\phi_3$ 是一个复合算符 $\phi_3 \approx \phi_1\phi_2$。
- 如果 $\Delta_1 = \frac{d-2}{2}$，那么方程 (4.29) 中的前两项消失。正如我们在第 3 章中看到的，只有满足运动方程 $\partial^2\phi_1(x)=0$ 的自由标量场才能具有这样的标度维度。由于显然 $[K^\mu, \partial^2\phi_1(x)] = 0$，因此涉及运动方程的关联函数具有 primary 3 点函数的形式是很自然的。然而，我们也知道它必须恒为零，这意味着要么 3 点系数 $\lambda_{123}$ 为零，要么满足附加条件 $\Delta_1 = |\Delta_2 - \Delta_3|$：例如，涉及 primary 复合算符 $\phi^2$ 的 3 点函数就是这种情况，
  $$
  \langle \phi (x _ {1}) \phi (x _ {2}) \phi^ {2} (x _ {3}) \rangle = \frac {\lambda}{(x _ {1 3} ^ {2}) ^ {(d - 2) / 2} (x _ {2 3} ^ {2}) ^ {(d - 2) / 2}}, \tag{4.31}
  $$
  它是非零的，但在 $\partial^2/(\partial x_1)^2$ 作用下消失。

最后，让我们通过与我们之前所做的相反方向的解析延拓回到闵可夫斯基时空。不难看出，标量 primary 算符的 Wightman 函数满足

$$
\langle 0 | \phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) \phi_ {3} (x _ {3}) | 0 \rangle = \frac {\lambda_ {1 2 3}}{(x _ {1 2} ^ {2}) ^ {\Delta_ {1 2 , 3}} (x _ {1 3} ^ {2}) ^ {\Delta_ {1 3 , 2}} (x _ {2 3} ^ {2}) ^ {\Delta_ {2 3 , 1}}}, \tag{4.32}
$$

其中现在两点之间的闵可夫斯基距离定义为

$$
x _ {i j} ^ {2} = - (x _ {i} ^ {0} - x _ {j} ^ {0} - i \varepsilon) + (\vec {x} _ {i} - \vec {x} _ {j}) ^ {2}. \tag{4.33}
$$

注意 $x_{ij}^2 \neq x_{ji}^2$，因此 Wightman 3 点函数在算符交换下不是对称的。然而，对于满足 $\phi_i(x)^\dagger = \phi_i(x)$ 的实算符，我们必须有

$$
\langle 0 | \phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) \phi_ {3} (x _ {3}) | 0 \rangle = \langle 0 | \phi_ {3} (x _ {3}) \phi_ {2} (x _ {2}) \phi_ {1} (x _ {1}) | 0 \rangle^ {*}, \tag{4.34}
$$

只有当系数 $\lambda_{123}$ 是实数时，这才与方程 (4.32) 兼容。这个性质实际上对于第 6 章讨论的共形自举至关重要。

## 4.4 4 点函数

嵌入空间技术也可以用于更高点函数，但情况变得更复杂。为了避免处理四个不同的算符和同样多的标度维度，让我们将注意力集中在四个相同标量算符的情况，

$$
\langle \phi (X _ {1}) \phi (X _ {2}) \phi (X _ {3}) \phi (X _ {4}) \rangle . \tag{4.35}
$$

在这种情况下，有 6 个洛伦兹不变量 $X_i\cdot X_j$，$i\neq j$。很容易看出，形式为

$$
\frac {1}{(X _ {1} \cdot X _ {2}) ^ {\Delta} (X _ {3} \cdot X _ {4}) ^ {\Delta}} \tag{4.36}
$$

的项满足共形对称性的所有约束。然而，它不是唯一的：

$$
\frac {1}{(X _ {1} \cdot X _ {3}) ^ {\Delta} (X _ {2} \cdot X _ {4}) ^ {\Delta}}. \tag{4.37}
$$

也是如此。这立即表明，没有希望像约束 3 点函数那样强力地约束 4 点函数。事实上，可以从 $X_i$ 构造两个不变量：

$$
u = \frac {(X _ {1} \cdot X _ {2}) (X _ {3} \cdot X _ {4})}{(X _ {1} \cdot X _ {3}) (X _ {2} \cdot X _ {4})}, \quad v = \frac {(X _ {1} \cdot X _ {4}) (X _ {2} \cdot X _ {3})}{(X _ {1} \cdot X _ {3}) (X _ {2} \cdot X _ {4})}. \tag{4.38}
$$

这些被称为共形交叉比。$u$ 和 $v$ 的任何函数都是共形不变的，最一般的 4 点函数形式为

$$
\langle \phi (X _ {1}) \phi (X _ {2}) \phi (X _ {3}) \phi (X _ {4}) \rangle \propto \frac {g (u , v)}{(X _ {1} \cdot X _ {2}) ^ {\Delta} (X _ {3} \cdot X _ {4}) ^ {\Delta}}. \tag{4.39}
$$

用欧几里得坐标表示，这可以写成

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \phi (x _ {3}) \phi (x _ {4}) \rangle = \frac {g (u , v)}{\left(x _ {1 2} ^ {2} x _ {3 4} ^ {2}\right) ^ {\Delta}} \tag{4.40}
$$

其中

$$
u = \frac {x _ {1 2} ^ {2} x _ {3 4} ^ {2}}{x _ {1 3} ^ {2} x _ {2 4} ^ {2}}, \quad v = \frac {x _ {1 4} ^ {2} x _ {2 3} ^ {2}}{x _ {1 3} ^ {2} x _ {2 4} ^ {2}}. \tag{4.41}
$$

为了看到这是最一般的结果，考虑以下基于有限共形变换序列的论证：

1.  使用平移，总是可以选择一个参考系使得 $x_1 = 0$。
2.  使用特殊共形变换，可以将 $x_4 \to \infty$ 而不将 $x_1$ 移离原点。
3.  然后可以使用旋转将 $x_3$ 沿某个选定方向放置，接着使用标度变换得到 $x_3 = (0,\dots,0,1)$，而不触碰原点和无穷远点。
4.  最后，仍然存在一个不影响 $x_3$ 的旋转子集，可以用来将点 $x_2$ 移动到位置 $x_2 = (b,0,\dots,0,a)$，如图 6.1 所示。

注意，前 3 步可以用来完全固定 3 点函数的运动学，这解释了为什么它的唯一自由度是一个乘法系数。而对于 4 点函数，我们剩下两个量 $a$ 和 $b$，它们与两个共形交叉比一一对应。实际上，用复数 $z = a + i b$ 及其共轭 $\bar{z} = a - i b$ 来代替这两个实数更为方便。交叉比与 $z$ 和 $\bar{z}$ 的关系为

$$
u = z \bar {z}, \quad v = (1 - z) (1 - \bar {z}). \tag{4.42}
$$

Schwinger 函数在所有非重合点构型处是解析的，因此函数 $g(z)$ 是复平面上除去点 $\{0,1,\infty\}$ 外的单值函数。注意，$g$ 也受到 4 点函数 crossing 对称性的约束，这要求[8]

- 交换算符 $\phi(x_1)$ 和 $\phi(x_2)$ 后，
  $$
  g (u, v) = g \left(\frac {u}{v}, \frac {1}{v}\right) \tag{4.43}
  $$
- 交换 $\phi(x_1)$ 和 $\phi(x_3)$ 后，
  $$
  g (u, v) = \left(\frac {u}{v}\right) ^ {\Delta} g (v, u), \tag{4.44}
  $$

在闵可夫斯基时空中情况更复杂。仍然可以通过方程 (4.41) 定义交叉比，闵可夫斯基距离通过如 (4.33) 中的 $i\varepsilon$ 规则定义。但是 Wightman 函数不是解析的（它们位于复化坐标解析区域的边界上），因此 $g$ 是一个多值函数。它的值可以通过从一个所有 4 个算符都位于常时间切片上的构型进行解析延拓得到，在这种情况下，它与 Schwinger 函数一致。例如，将 $x_1, x_3$ 和 $x_4$ 保持在该时间切片上，但让 $x_2$ 的时间分量 $b$ 变为虚数，最终得到一个 $z$ 和 $\bar{z}$ 都是实数但不相等的构型。这个过程通常是繁琐的，可以说，目前对共形 Wightman 4 点函数的理解仍不完整[9]。

# 第五章 态-算符对应与 OPE

关联函数的构造本可以继续进行到 4 点以上，但我们有充分的理由在此止步（至少在本课程中）。我们现在将看到，任何 $n$ 点函数都可以使用算子积展开（OPE）简化为 $(n-1)$ 点函数。这个过程可以迭代，直到一切都用 2 点和 3 点函数表示。4 点函数将作为 OPE 可以应用的典型情况来研究，而更高点函数将不予考虑。

## 5.1 QFT 中的 OPE

量子场论中的算子积展开是指，当两个局域算符“足够接近”时，它们可以被另一个局域算符或更准确地说是一组局域算符的和所替代：

$$
\phi_ {1} (x) \phi_ {2} (y) \xrightarrow {x \to y} \sum_ {i} f _ {i} (x - y) \phi_ {i} (y), \tag{5.1}
$$

右边的算符 $\phi_i$ 是在 $x$ 还是 $y$ 处插入，或者在中间点 $(x+y)/2$ 处插入，都无关紧要，因为此展开在 $x$ 和 $y$ 重合的极限下有效。事实上，比例因子 $f_i$ 在极限 $x \to y$ 下可能发散，因此这应理解为渐近极限的意义，其收敛半径严格来说为零。

在非微扰量子场论中，OPE 可以用希尔伯特空间来表述：当方程 (5.1) 中的算符乘积作用在真空上时，希尔伯特空间的完备性意味着我们可以写出

$$
\phi_ {1} (x) \phi_ {2} (y) | 0 \rangle = \sum_ {| \Psi \rangle} | \Psi \rangle \langle \Psi | \phi_ {1} (x) \phi_ {2} (y) | 0 \rangle , \tag{5.2}
$$

其中求和遍及构成正交归一基的态 $|\Psi\rangle$。这些态包括通过将局域算符 $\phi_i(y)$ 作用在真空上得到的态，因此我们有

$$
\phi_ {1} (x) \phi_ {2} (y) | 0 \rangle = \sum_ {i} f _ {i} (x - y) \phi_ {i} (y) | 0 \rangle + \dots , \tag{5.3}
$$

其中 $f_i$ 与 Wightman 函数的比值有关

$$
f _ {i} (x - y) \approx \lim _ {z \rightarrow \infty} \frac {\langle 0 | \phi_ {i} (z) \phi_ {1} (x) \phi_ {2} (y) | 0 \rangle}{\langle 0 | \phi_ {i} (z) \phi_ {i} (y) | 0 \rangle}. \tag{5.4}
$$

然而，这种表述仍然不精确，而且不太清楚如何使用量子场论的一般原理使其更严谨。

然而，在共形场论中，由于以下观察，算子积展开达到了一个全新的严谨水平：

- Primary 算符的 2 点函数是对角的（即只有相同的 primary 有非零 2 点函数），这意味着不同 primary 创建的态是正交的。primary 态的范数也以算符的归一化形式已知。
- 3 点函数是已知的（见第 4 章），这意味着比例系数 $f_i$ 实际上被固定到至多一个整体乘法因子。
- 除了局域算符作用在真空上之外，没有其他对 OPE 的贡献。这个性质是由于接下来要讨论的态/算符对应。

## 5.2 态/算符对应

在共形场论中，给定时间切片上的态与由它们的标度维度和洛伦兹群表示定义的局域算符之间存在一一对应关系。

局域算符定义态这一事实在闵可夫斯基时空中是显然的，根据 Wightman 公理。但在解析延拓到欧几里得空间后，这也成立。为了理解这一点，记住一个在一般闵可夫斯基坐标 $x$ 处插入的局域算符可以使用方程 (3.3) 表示为在 $x^0=0$ 曲面上的算符，并通过酉演化得到，

$$
\phi (x) \left| 0 \right\rangle = e ^ {i x ^ {0} P ^ {0}} e ^ {- i \vec {x} \cdot \vec {P}} \phi (0) \left| 0 \right\rangle . \tag{5.5}
$$

由于 $P^0$ 的谱是非负的，这可以解析延拓到上半复平面中 $x^0$ 的任何值；相反，如果 $x^0$ 有负的虚部，那么会有任意高能量的态，其范数发散。通过取纯虚数值 $x^0 = i\tau$，我们因此可以通过在欧几里得空间中插入算符来定义理论的一个态，前提是这个算符在欧几里得时间 $\tau > 0$ 处插入。

这在欧几里得路径积分中有一个直接的解释：在 $\tau=0$ 的欧几里得曲面（与原始闵可夫斯基时间切片 $x^0=0$ 相同）上的一个态，由对所有限制在 $\tau<0$ 区域内的场构型进行路径积分来定义。对于任何数量的算符在 $\tau<0$ 的分离点处插入（包括没有算符，对应于真空态），这都是有效的。但反过来也成立：在 $\tau=0$ 曲面上给定的一个态为 $\tau<0$ 的路径积分定义了一个边界条件，这可能对应于在“过去”（或此类构型的叠加）插入的若干局域算符。通过这种方式，任何算符按欧几里得时间 $\tau$ 排序的欧几里得关联函数都可以赋予希尔伯特空间解释。

一旦我们采用欧几里得路径积分观点，那么使用 $P^0$ 作为哈密顿量，还是使用另一个共形生成元，只要 $\tau=0$ 曲面是其定义的分层的一部分，就无关紧要。例如，可以使用所谓的共形哈密顿量 $\frac{1}{2}(P^0 - K^0)$，它以图 2.2 所示的方式分层欧几里得空间。我们在第 2 章中提到，这个生成元组合实际上等价于 dilatation 生成元 $D$，因为它们通过共形群 $SO(d+1,1)$ 的紧致子群 $SO(d+1)$ 中的旋转相关联。这意味着存在一个共形变换，将 $\tau=0$ 曲面映射到单位球面，而由哈密顿量演化相关的其他曲面映射到不同半径的球面（再次参见图 2.2）。将欧几里得空间分层为以原点为中心的球面，并使用 dilatation 生成元作为哈密顿量，称为径向量子化。相比之下，物理上等价的哈密顿量选择 $\frac{1}{2}(P^0 - K^0)$ 通常称为 N-S 量子化。

这两种量子化在共形场论中的重要性在于它们具有不动点，这与等时量子化不同。随着“时间”向后演化，路径积分收缩到围绕其中一个不动点（径向量子化中的原点，或 N-S 量子化中的南极）的任意小半径的球体。这意味着单位球面或 $\tau=0$ 平面上的任何态，都可以通过哈密顿量演化与定域在不动点处的态相关。因此，它等价于由在该处插入的局域算符创建的态。这本质上就是论证态/算符对应双向成立：局域算符定义一个态，但任何态也定义一个局域算符（或更确切地说，局域算符的叠加）。

这个对应事后证明了我们选择将算符组织成具有确定标度维度的洛伦兹群不可约表示是合理的：对角化可以在希尔伯特空间层面进行，然后使用径向量子化来论证每个态对应一个局域算符。注意，既有 primary 态也有 descendant 态，意思是局域算符不一定是 primary。

许多共形场论的入门课程实际上从径向量子化开始，因为它在欧几里得空间中提供了一个引人注目的图景。然而，与酉量子场论的联系并不容易建立。在酉理论中的厄米共轭要求将 $x^0 = i\tau$ 变为 $(x^0)^* = -i\tau$，即对应于 N-S 量子化中 $\tau=0$ 曲面的反射。在径向量子化中，这变成了反演 $r \to r^{-1}$：关联函数计算对应于单位球面内部路径积分的态与对应于单位球面外部路径积分的态之间的重叠。闵可夫斯基时空中所需的态涂抹被替换为定义共轭态所需的极限 $r \to \infty$。一旦考虑了这个极限，就可以使用 $P_\mu$ 和 $K_\mu$（它们在反演下互为共轭）的相互作用推导出幺正性界。这个过程重现了第 3 章的结果，但可能不太直观。

## 5.3 共形 OPE

我们从径向量子化学到的教训是，希尔伯特空间中的每个态都可以写成由单个局域算符（包括 primary 和 descendant）作用在真空上产生的态的线性组合。将这个教训应用于闵可夫斯基时空中的 Wightman 函数，我们可能会尝试将整个希尔伯特空间写为

$$
\mathscr {H} \stackrel {?} {=} \operatorname{span} \left\{\left| 0 \right\rangle , \phi (0) \left| 0 \right\rangle , \partial_ {\mu} \phi (0) \left| 0 \right\rangle , \dots \right\}. \tag{5.6}
$$

问题在于这些不是可归一化的态。相反，我们可以考虑由 primary 算符在闵可夫斯基时空中任意点 $x$ 插入所创建的态，

$$
\mathcal {H} \sim \operatorname{span} \bigl \{\left| 0 \right\rangle , \phi (x) \left| 0 \right\rangle , \dots \bigr \}, \tag{5.7}
$$

其中我们默认局域算符应与测试函数涂抹。这给出了希尔伯特空间的一个良好描述，但不是非常实用，因为不同点处插入的 primary 算符（或与不同测试函数涂抹）彼此不正交。这引导我们考虑希尔伯特空间的另一种表示，使用动量空间中的局域算符，

$$
\mathscr {H} \sim \operatorname{span} \left\{\left| 0 \right\rangle , \widetilde {\phi} (p) \left| 0 \right\rangle , \dots \right\}. \tag{5.8}
$$

携带不同动量的态彼此正交，而且仅考虑前向光锥内的动量 $p$ 就足够了。这意味着我们可以通过恒等算符的分解来表达希尔伯特空间的完备性

$$
\mathbb {1} = | 0 \rangle \langle 0 | + \sum_ {i} \int_ {p ^ {0} > | \vec {p} |} \frac {d ^ {d} p}{(2 \pi) ^ {d}} \frac {\widetilde {\phi} _ {i} (p) | 0 \rangle \langle 0 | \widetilde {\phi} _ {i} (- p)}{2 \pi C (- p ^ {2}) ^ {\Delta - d / 2}} + \dots , \tag{5.9}
$$

其中求和遍及理论中所有的 primary 算符。分母就是标量 2 点函数，方程 (3.42)，为简单起见省略了携带自旋的态：在反转出现在 2 点函数中的洛伦兹张量后，它们可以用同样的方式包括进来，根据幺正性该张量是正定的。

这个恒等式可以应用于我们遇到的两个局域算符乘积作用在真空上的情况，以将该乘积重写为局域算符的和。当所有算符都用动量空间表示时，它取最简单的形式：

$$
\widetilde {\phi} _ {1} (p _ {1}) \widetilde {\phi} _ {2} (p _ {2}) | 0 \rangle = \sum_ {i} \widetilde {f} _ {i} \widetilde {\phi} _ {i} (p _ {1} + p _ {2}) | 0 \rangle . \tag{5.10}
$$

这就是闵可夫斯基时空中的共形 OPE，它将更高点函数简化为更低点函数。当应用于 2 点函数时它是平凡的，因为只有真空态出现在求和中（单位算符本身可以解释为一个 primary 算符）。当应用于 3 点函数时，它可以用来确定比例因子 $\tilde{f}_i$ 与标度维度、洛伦兹表示和 3 点系数 $\lambda_{12i}$ 的关系。进一步使用这个 OPE，一个 4 点函数可以分解为一系列项的和，其运动学完全由共形对称性决定。

然而，这种形式的 OPE 很少使用，原因有二：我们对动量空间中 Wightman 3 点函数的理解不完整，而且这个 OPE 的收敛性不是特别好。这里的意思是，OPE 在分布意义下收敛，即只有在与光滑测试函数涂抹后才收敛。相比之下，我们接下来将看到欧几里得 OPE 是绝对收敛的！

由于我们之前看到 Schwinger 函数也可以赋予希尔伯特空间解释，我们不妨直接在欧几里得空间中表述 OPE。我们写

$$
\phi_ {1} (x _ {1}) \phi_ {2} (x _ {2}) = \sum_ {i} f _ {i} \left(x _ {1} - x _ {2}, \partial_ {x _ {2}}\right) \phi_ {i} (x _ {2}). \tag{5.11}
$$

与闵可夫斯基 OPE (5.10) 不同，这个 OPE 的收敛是有条件的：它仅当在关联函数内部，点 $x_1$ 和 $x_2$ 能够通过一个量子化曲面（例如径向量子化中的球面）与其他所有局域算符的插入点分隔开时才成立。由于球面的中心和半径可以借助平移和标度对称性任意选择，这包括很多（实际上是几乎所有）点的构型，如下文所见。

在方程 (5.11) 的符号中，$f_i$ 不仅依赖于两个算符之间的距离，还依赖于作用在 primary 算符 $\phi_i$ 上的导数。这是将所有 descendant 包含在求和中的一种紧凑方式。但要记住，存在无限多个这样的 descendant，因此 $f_i$ 本身是一个无穷级数。唯一的例外是单位算符，当且仅当 (5.11) 左边的两个 primary 算符相同时，它才进入 OPE：在一个 2 点函数中，OPE 的形式为

$$
\langle \phi (x) \phi (0) \rangle = \frac {1}{(x ^ {2}) ^ {\Delta_ {\phi}}} \langle \mathbb {1} \rangle , \tag{5.12}
$$

其中 $\langle \mathbb{1} \rangle = 1$，由此我们推断

$$
f _ {\mathbb {1}} (x, \partial) = \frac {1}{(x ^ {2}) ^ {\Delta_ {\phi}}}. \tag{5.13}
$$

当被视为 primary 算符时，单位算符没有任何 descendant。在所有其他情况下，$f_i(x, \partial)$ 的值可以从 3 点函数确定：使用标量 3 点函数 (4.23) 中的 OPE，可以推断出例如

$$
f _ {i} (x, \partial) = \frac {\lambda_ {1 2 i}}{\left(x ^ {2}\right) ^ {\Delta_ {1 2 , i}}} \left[ 1 + a x ^ {\mu} \partial_ {\mu} + b _ {1} x ^ {\mu} x ^ {\nu} \partial_ {\mu} \partial_ {\nu} + b _ {2} x ^ {2} \partial^ {2} + \dots \right] \tag{5.14}
$$

其中

$$
a = \frac {\Delta_ {i 1 , 2}}{\Delta_ {i}},
$$

$$
b _ {1} = \frac {\Delta_ {i 1 , 2} (\Delta_ {i 1 , 2} + 1)}{2 \Delta_ {i} (\Delta_ {i} + 1)}, \tag{5.15}
$$

$$
b _ {2} = - \frac {\Delta_ {i 1 , 2} \Delta_ {i 2 , 1}}{4 \Delta_ {i} (\Delta_ {i} + 1) \left(\Delta_ {i} - \frac {d - 2}{2}\right)},
$$

等等。这个表达式在 $\phi_i$ 是标量算符时有效，但即使 $\phi_1$ 和 $\phi_2$ 是标量，也有带自旋的算符进入 OPE：在空间分离点 $x_1 \neq x_2$ 处插入的算符的乘积携带角动量；对于 OPE 另一侧的点状算符，这个角动量被实现为内禀自旋。然而，并非所有洛伦兹表示都出现在两个标量的 OPE 中，只有对称张量会出现。此外，当算符相同时，只有具有偶数个洛伦兹指标的张量出现。可以出现的表示列表可以从洛伦兹对称性的群论确定。相反，任何标度维度 $\Delta$ 都可能出现。

因此，OPE 中仍然有许多未知数。我们将在下一节看到，求和中实际上总是有无限多个 primary 算符。但与一般量子场论中的 OPE 相比，共形 OPE 是极其刚性的：在标度不变的 QFT 中，进入系数 $f_i(x, \partial)$ 定义的系数 $a, b_1, b_2, \dots$ 都是依赖于理论的因子。相反，在 CFT 中，它们完全由运动学决定。唯一的动力学信息包含在 OPE 系数 $\lambda_{12i}$ 中，它们乘以一个 primary 及其所有 descendant 的贡献。

# 第六章 共形自举

到目前为止，我们对共形场论的处理一直是代数的：在第 3 章中，我们将 primary 算符定义为共形群的不可约表示，以其在洛伦兹对称性下的变换和标度维度为特征。在第 5 章中，我们看到这些算符可以使用算子积展开组合。OPE 系数扮演了该算子代数结构常数的角色。一个理论的所有标度维度和洛伦兹群表示，连同 OPE 系数，

$$
\left\{(\Delta_ {i}, R _ {i}), \lambda_ {i j k} \right\} \tag{6.1}
$$

被称为 CFT 数据。一个共形场论完全由其 CFT 数据定义：任何关联函数都可以通过重复使用 OPE 从中计算出来。

但是，任何 CFT 数据都定义一个好的理论吗？答案是否定的：局域算符的代数必须闭合，这给出了非常强的自洽性条件[1]。这个闭合条件的具体表述取决于我们讨论的是欧几里得还是洛伦兹共形群。对于闵可夫斯基时空中的共形场论，关键点是 OPE 必须与微观因果性条件 (3.9) 一致。但微观因果性的后果在实践中很难追踪。

相反，对于欧几里得空间中的 Schwinger 函数，有一个简单得多的自洽性条件：由于这些函数在算符交换下是对称的（这个性质实际上与微观因果性相关），那么欧几里得 OPE 必须是结合的。为了说明这一点，让我们关注 4 点函数。对所有 4 点函数施加 OPE 的结合性，实际上足以保证更高点函数的结合性。为简单起见，像之前一样考虑 4 个相同标量 primary 算符的情况，其标度维度为 $\Delta_\phi$：

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \phi (x _ {3}) \phi (x _ {4}) \rangle = \frac {1}{(x _ {1 2} ^ {2} x _ {3 4} ^ {2}) ^ {\Delta_ {\phi}}} g (u, v). \tag{6.2}
$$

## 6.1 共形块

理解这个 4 点函数如何用 CFT 数据表示的最简单方法是两次使用 OPE (5.11)：

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \phi (x _ {3}) \phi (x _ {4}) \rangle = \sum_ {i} f _ {i} \left(x _ {1} - x _ {2}, \partial_ {x _ {2}}\right) f _ {i} \left(x _ {3} - x _ {4}, \partial_ {x _ {4}}\right) \langle \phi_ {i} (x _ {2}) \phi_ {i} (x _ {4}) \rangle \tag{6.3}
$$

右边只有一个求和，因为 2 点函数是对角的：除非两个 primary 算符相同，否则它为零。为了将其写成方便的形式，让我们提取出与 3 点函数 $\langle \phi \phi \phi_i \rangle$ 对应的 OPE 系数 $\lambda_i$，以及距离的特定幂次，定义

$$
f _ {i} (x, \partial) = \frac {\lambda_ {i}}{(x ^ {2}) ^ {\Delta_ {\phi}}} f _ {i} ^ {\prime} (x, \partial), \tag{6.4}
$$

新函数 $f_i'$ 的形式为

$$
f _ {i} ^ {\prime} (x, \partial) = (x ^ {2}) ^ {\Delta_ {i} / 2} [ 1 + \dots ], \tag{6.5}
$$

其中 $\Delta_i$ 是进入 OPE 的算符（内算符）的标度维度，不要与原始关联函数中算符（外算符）的标度维度 $\Delta_\phi$ 混淆。我们现在有

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \phi (x _ {3}) \phi (x _ {4}) \rangle = \frac {1}{(x _ {1 2} ^ {2} x _ {3 4} ^ {2}) ^ {\Delta_ {\phi}}} \sum_ {i} \lambda_ {i} ^ {2} g _ {i} (u, v), \tag{6.6}
$$

其中我们定义

$$
g _ {i} (u, v) = f _ {i} ^ {\prime} \left(x _ {1} - x _ {2}, \partial_ {x _ {2}}\right) f _ {i} ^ {\prime} \left(x _ {3} - x _ {4}, \partial_ {x _ {4}}\right) \frac {1}{(x _ {2 4}) ^ {\Delta_ {i}}}. \tag{6.7}
$$

这应与 4 点函数的表示 (6.2) 进行比较，由此可得

$$
g (u, v) = \sum_ {i} \lambda_ {i} ^ {2} g _ {i} (u, v). \tag{6.8}
$$

## 6.1 共形块

$g_i$ 被称为共形块 [1]：它们代表单个 primary 及其所有 descendant 对 4 点函数的贡献。它们是共形不变的[2]，因此必须是交叉比 $u$ 和 $v$ 的函数，尽管从它们的定义来看这一点完全不明显。

这个定义实际上并不是很实用：计算出 $f_i'$ 级数中的所有项很困难，而且当中间算符携带自旋时，还需要收缩洛伦兹指标。但在极限 $x_1 \to x_2$, $x_3 \to x_4$，或等价地 $u \to 0$ 下检查是方便的：在这种情况下，OPE 中的主导项显示

$$
g _ {i} (u, v) = u ^ {\Delta_ {i} / 2} [ 1 + \dots ]. \tag{6.9}
$$

具有最低标度维度的 primary 算符在这个极限下对 4 点函数给出主导贡献。绝对最低标度维度的算符是单位算符，它没有 descendant，因此[3]

$$
g _ {\mathbb {1}} (u, v) = 1. \tag{6.10}
$$

注意，这个陈述与量子场论中更一般的聚类分解原理有关：由于 CFT 中没有绝对标度，极限 $x_1 \to x_2$ 等价于其他点 $x_3$ 和 $x_4$ 被送到非常远的极限，直到无穷远，在这种情况下，根据一般原理，关联函数会因式分解为

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \phi (x _ {3}) \phi (x _ {4}) \rangle \xrightarrow {x _ {3} , x _ {4} \to \infty} \langle \phi (x _ {1}) \phi (x _ {2}) \rangle \langle \phi (x _ {3}) \phi (x _ {4}) \rangle . \tag{6.11}
$$

因此，这种因式分解由 OPE 在极限 $u \to 0$ 下再现。

计算共形块的更好方法基于共形群的 Casimir 不变量 [2]。从群代数可以验证，生成元 (2.39) 的组合

$$
\mathcal {C} _ {2} = - \frac {1}{2} J _ {M N} J ^ {M N} \tag{6.12}
$$

与所有单个生成元对易，例如

$$
\left[ \mathcal {C} _ {2}, P ^ {\mu} \right] = 0. \tag{6.13}
$$

用群论的语言，$\mathcal{C}_2$ 称为二次 Casimir 不变量。由于它与平移对易，它对由局域算符创建的态的作用与算符插入的位置无关，也与它是 primary 还是 descendant 无关：对于一个标量 primary，

$$
\mathcal {C} _ {2} \phi (x) | 0 \rangle = \Delta (\Delta - d) \phi (x) | 0 \rangle . \tag{6.14}
$$

**练习 6.1** 从共形生成元与 $\phi(x)$ 的对易子计算二次 Casimir 算符的本征值。为简单起见，在 $x=0$ 处计算。

对于具有 $\ell$ 个洛伦兹指标的对称张量，本征值包含一个附加项，该附加项正是 $d$ 维洛伦兹/旋转群的二次 Casimir 算符，

$$
\mathcal {C} _ {2} \phi^ {\mu_ {1} \dots \mu_ {\ell}} (x) | 0 \rangle = [ \Delta (\Delta - d) + \ell (\ell + d - 2) ] \phi^ {\mu_ {1} \dots \mu_ {\ell}} (x) | 0 \rangle . \tag{6.15}
$$

关键思想是计算这个 Casimir 算符在由两个局域算符创建的态之间的期望值，即计算关联函数

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \mathcal {C} _ {2} \phi (x _ {3}) \phi (x _ {4}) \rangle \tag{6.16}
$$

应用一次 OPE，这可以写成

$$
\langle \phi (x _ {1}) \phi (x _ {2}) \mathcal {C} _ {2} \phi (x _ {3}) \phi (x _ {4}) \rangle = \sum_ {i} f _ {i} \left(x _ {3} - x _ {4}, \partial_ {x _ {4}}\right) \langle \phi (x _ {1}) \phi (x _ {2}) \mathcal {C} _ {2} \phi_ {i} (x _ {4}) \rangle , \tag{6.17}
$$

现在右边每一项有两种计算方式：要么 $\mathcal{C}_2$ 向右作用，然后可以使用本征值方程 (6.15)，要么它向左作用。在第二种情况下，形成 $\mathcal{C}_2$ 的各个生成元必须依次与 $\phi(x_1)$ 和 $\phi(x_2)$ 对易。这在方便的参考系中最容易完成，例如在第 4 章中描述并在图 6.1 中显示的 $z$ 参考系。在这种情况下，我们发现 $\mathcal{C}_2$ 对每个共形块的作用是一个关于 $z$ 和 $\bar{z}$ 的二阶微分算符，我们将其记为 $D_{z,\bar{z}}$。这意味着每个共形块满足形式如下的微分方程

$$
D _ {z, \bar {z}} g _ {i} (z, \bar {z}) = \left[ \Delta_ {i} (\Delta_ {i} - d) + \ell_ {i} (\ell_ {i} + d - 2) \right] g _ {i} (z, \bar {z}). \tag{6.18}
$$

结合方程 (6.9) 提供的边界条件，这足以完全确定共形块。在偶数时空维度中，解的形式是超几何函数的乘积。在奇数维度中，没有已知的闭式解，但 Casimir 方程可以方便地按级数展开逐项求解。

注意，在我们的具体例子中，外算符都是相同的，共形块不依赖于外标度维度 $\Delta_\phi$，而只依赖于内算符的标度维度 $\Delta_i$ 和自旋 $\ell_i$。这个性质在一般情况下不成立。

## 6.2 OPE 收敛性

![图 6.1 描述 4 点函数的两个方便的共形参考系。左图：通过共形变换将 3 个点映射到 0、1 和 $\infty$，复坐标 $z$ 描述第四个点的位置。在平面中应用共形变换，可以达到右图的构型，算符放置在一对同心圆上的对径点，大圆半径为 1；该构型由复坐标 $\rho$ 参数化，满足 $|\rho| \leq 1$](image-link)

到目前为止，我们在 4 点函数中使用 OPE 而没有担心其收敛性。只要点 $x_1$ 和 $x_2$ 能够被一个球面与 $x_3$ 和 $x_4$ 分隔开，这就没问题。用坐标 $z$ 表示，这对所有 $|z| < 1$（图 6.1 中虚线划定的单位圆盘）显然成立：那么算符乘积 $\phi(x_1)\phi(x_2)$ 可以通过态-算符对应替换为在 $x_1=0$ 处的局域算符之和，因此 OPE 收敛，因为它是希尔伯特空间求和。但收敛域实际上要大得多：径向量子化可以围绕空间中的任何点使用，而不仅仅是在 $x_1$，不难看出，在大多数构型中，可以画出一个圆包围 $x_1$ 和 $x_2$，但排除 $x_3$ 和 $x_4$。这在所有情况下都是可能的，除了当 $z$ 是实数且 $z > 1$ 时[4]。

这在使用不同的参考系时更容易看出：使用 $z$ 平面中的共形变换，可以将 4 个点映射到图 6.1 右侧所示的构型，其中点对 $(x_1, x_2)$ 和 $(x_3, x_4)$ 放置在两个以原点为中心的圆上的对径点 [3]。映射由下式给出

$$
\rho = \frac {z}{(1 + \sqrt {1 - z}) ^ {2}} \quad \Leftrightarrow \quad z = \frac {4 \rho}{(1 + \rho) ^ {2}}. \tag{6.19}
$$

它将整个复 $z$ 平面映射到 $\rho$ 的单位圆盘内，半直线 $z > 1$ 映射到单位圆上。在这个参考系中，现在显然 OPE 在径向量子化中收敛，除非 $|\rho| = 1$。

![图 6.2 图 6.1 中的 $\rho$ 坐标构型在径向量子化圆柱体上的视图。两个线段 $x_1-x_2$ 和 $x_3-x_4$ 形成角度 $\theta$，它们在圆柱体时间上相隔 $\tau = \log(r)$。$\theta$ 和 $\tau$ 与平坦空间构型的关系为 $\rho = e^{\tau+i\theta} = r e^{i\theta}$](image-link)

这个共形参考系对于理解 OPE 的收敛性质也非常有用。它可以看作是径向量子化圆柱体上的一个构型，如图 6.2 所示，坐标为

$$
x _ {1} = (\tau , \vec {n}), \quad x _ {2} = (\tau , - \vec {n}), \quad x _ {3} = (0, \vec {n} ^ {\prime}), \quad x _ {4} = (0, - \vec {n} ^ {\prime}), \tag{6.20}
$$

其中 $\tau = \log(r)$ 是“时间”分量，“空间”分量是单位向量 $\vec{n}$ 和 $\vec{n}'$，它们参数化球面 $S^{d-1}$ 上的一个方向，并形成夹角 $\theta$。与平坦空间构型的联系是

$$
\rho = r e ^ {i \theta}. \tag{6.21}
$$

一个共形块对应于将这个构型投影到具有标度维度 $\Delta_i + n$（$n$ 为整数）和自旋 $j$（其范围由 primary 的自旋 $\ell$ 决定）的中间 primary 和 descendant 态上。基于一般原理，因此可以预期共形块具有形式

$$
g _ {i} (r, \theta) = \sum_ {n, j} B _ {n, j} r ^ {\Delta_ {i} + n} \mathcal {C} _ {j} ^ {(d - 2) / 2} (\cos \theta), \tag{6.22}
$$

其中 $\mathcal{C}_j^{(d-2)/2}(\cos\theta)$ 是一个 Gegenbauer 多项式，由对称无迹张量 $\vec{n}^{\mu_1}\cdots\vec{n}^{\mu_j}$ 与 $\vec{n}^{\prime\mu_1}\cdots\vec{n}^{\prime\mu_j}$ 的收缩得到。系数 $B_{n,j}$ 根据幺正性是正的，因为它们是具有确定自旋（由 $n$ 和 $j$ 标记）的本征态的范数。它们实际上是 $\Delta_i$ 的有理函数。这个表示非常有用：一方面，它提供了一种通过在 $n$ 中截断级数来以任何所需精度评估共形块的有效方法，因为根据假设 $r < 1$；另一方面，它表明 $g_i$ 是标度维度 $\Delta_i$ 的 nice（即解析）函数，适用于所有高于幺正性界的 $\Delta_i$ 值。

除了单个共形块，$\rho$ 坐标还展示了 OPE 如何作为 $r$ 的函数收敛。在 $r \ll 1$ 的构型中，级数由低 $\Delta$ 的算符（包括 primary 和 descendant）主导，可以通过截断的 OPE 获得 4 点函数的良好近似。例如，算符放置在正方形角上的构型对应于 $\tan z = 1/2$，或 $|\rho| = (1+\sqrt{2})^{-2} \approx 0.17$。尽管在此构型中 $x_1$ 和 $x_2$ 并不明显靠近，但 $r = |\rho|$ 是一个小数字，OPE 的收敛非常快。

这是欧几里得 OPE 的一个奇妙性质。在闵可夫斯基时空中情况不那么好。方程 (6.22) 中看到的 $r$ 的幂律依赖是欧几里得“时间” $\tau$ 指数阻尼的结果（$r^{\Delta_i} = e^{\tau \Delta_i}$ 且 $\tau$ 为负），遵循径向量子化中的哈密顿量演化。在闵可夫斯基时空中，无论选择何种量子化，演化总是酉的，例如 $e^{iEt}$：原则上没有理由认为高标度维度的算符在一般构型中的贡献应该比低维度的算符少。这并不意味着闵可夫斯基 OPE 无趣，但它比欧几里得 OPE 更难驾驭。

## 6.3 Crossing 方程与简单解

到目前为止，我们只讨论了一种特定的 OPE，其中假设点 $x_1$ 和 $x_2$ 在共形意义上是接近的。但由于 Schwinger 函数在算符交换下是对称的，没有理由不考虑不同的 OPE，例如，算符 $\phi(x_1)$ 和 $\phi(x_3)$ 之间，或 $\phi(x_1)$ 和 $\phi(x_4)$ 之间。在绝大多数 4 点构型中，空间可以通过一个球面以三种不等价的方式切成两半。即使在 4 点共圆的特殊情况下，仍然有两种不等价的方式用球面包围点对。这意味着我们预期不同的 OPE 在所有情况下都收敛[5]。

这意味着除了展开

$$
g (u, v) = \sum_ {i} \lambda_ {i} ^ {2} g _ {i} (u, v), \tag{6.23}
$$

我们还可以为通过 crossing 对称性相关的构型中的 4 点函数写一个类似的展开，例如

$$
\left(\frac {u}{v}\right) ^ {\Delta_ {\phi}} g (v, u) = \left(\frac {u}{v}\right) ^ {\Delta_ {\phi}} \sum_ {i} \lambda_ {i} ^ {2} g _ {i} (v, u). \tag{6.24}
$$

由于两者相等，我们必须有

$$
\sum_ {i} \lambda_ {i} ^ {2} g _ {i} (u, v) = \left(\frac {u}{v}\right) ^ {\Delta_ {\phi}} \sum_ {i} \lambda_ {i} ^ {2} g _ {i} (v, u). \tag{6.25}
$$

这个方程在图 6.3 中用图表示意。注意，在相同外算符的情况下，两个求和是对同一组 primary 算符进行的，但一般情况下，这些可能是不同的求和。

![图 6.3 共形自举核心 crossing 方程的图示，关联两个不同的 OPE](image-link)

这是一个相对简单的方程，但求解起来相当困难。我们在上面看到，在极限 $u \to 0$ 下，OPE 由低 $\Delta_i$ 的中间算符主导，但这只适用于左边：在右边取相同的极限，就到达了 OPE 收敛域的边界。使用已知的超几何函数形式的共形块表达式，可以证明极限 $z \to 1$ 接近一个分支割线，围绕它

$$
g _ {i} (z, \bar {z}) \propto \log (1 - z). \tag{6.26}
$$

这意味着 crossing 方程的右边在极限 $z \to 0$ 下由形式如下的项主导

$$
\left(\frac {u}{v}\right) ^ {\Delta_ {\phi}} g _ {i} (v, u) \propto z ^ {2 \Delta_ {\phi}} \log (z), \tag{6.27}
$$

有限项的和无法再现左边单位算符的主导常数贡献。这是 crossing 方程 (6.25) 包含的第一个智慧：它永远无法逐块满足，而只能通过无限多个共形块的和来满足，因此 OPE 中必须有无限多个 primary 算符。

在深入研究共形自举处理这个问题的巧妙方法之前，让我们检查一下我们所知的最简单的 crossing 对称解。一个可能的在共形群下协变且满足 crossing 对称的函数是以下 2 点函数的组合：

$$
\begin{array}{l} \langle \phi (x _ {1}) \phi (x _ {2}) \rangle \langle \phi (x _ {3}) \phi (x _ {4}) \rangle + \langle \phi (x _ {1}) \phi (x _ {3}) \rangle \langle \phi (x _ {2}) \phi (x _ {4}) \rangle \\ + \langle \phi (x _ {1}) \phi (x _ {4}) \rangle \langle \phi (x _ {2}) \phi (x _ {3}) \rangle , \tag{6.28} \\ \end{array}
$$

对应于

$$
g (u, v) = 1 + u ^ {\Delta_ {\phi}} + \left(\frac {u}{v}\right) ^ {\Delta_ {\phi}}. \tag{6.29}
$$

在小 $u$ 下进行展开，并将每一项与假设的 primary 算符匹配，我们找到一个由其自旋 $\ell$ 和标度维度

$$
\Delta_ {i} = 2 \Delta_ {\phi} + 2 n + \ell \tag{6.30}
$$

刻画的无限谱，其中 $n = 0, 1, 2, \dots$。这定义了一个有效的 4 点关联函数，它属于一个称为广义自由场论（有时也称为平均自由理论，或高斯理论）的理论。它在某种意义上类似于自由理论，因为 OPE $\phi\times\phi$ 包含的算符具有与场 $\phi$ 的复合算符相同的标度维度和自旋，其示意形式为

$$
\left[ \phi (\partial^ {2}) ^ {n} \partial^ {\mu_ {1}} \dots \partial^ {\mu_ {\ell}} \phi \right]. \tag{6.31}
$$

自由标量场论是此理论的一个特例，其中 OPE 中只存在 $n=0$ 的算符（其他的因运动方程 $\partial^2\phi=0$ 而消失，或者是 descendant），并且这些算符是更高自旋的守恒流。广义自由场论通常被认为是非局域的：其通过上述 4 点函数的定义不包括能动张量[6]。然而，它在物理上是一个有趣的情况，因为规范理论的大 $N$ 极限恰好呈现这种形式：如果考虑规范不变复合算符（如费米子双线性 $\bar{\psi}_a \psi_a$）的 4 点函数，那么在 $1/N$ 主导阶下，它分解为“双迹”算符（标度维度为 $2\Delta_\phi + 2n + \ell$）的和，而“单迹”算符（其中包括能动张量）仅在 $1/N$ 的次导阶出现。

## 6.4 数值自举

催生现代共形自举的革命性思想出现在 2008 年 [4][7]。出发点是将 crossing 方程 (6.25) 重写为

$$
\sum_ {i} \lambda_ {i} ^ {2} \left[ v ^ {\Delta_ {\phi}} g _ {i} (u, v) - u ^ {\Delta_ {\phi}} g _ {i} (v, u) \right] = 0, \tag{6.32}
$$

并意识到它可以看作一个无限维矢量空间中的方程

$$
\sum_ {i} \lambda_ {i} ^ {2} \vec {F} _ {i} (\Delta_ {\phi}, \Delta_ {i}, \ell_ {i}) = 0, \tag{6.33}
$$

其中 $\lambda_i^2$ 是正系数（记住在酉量子场论中 $\lambda_i$ 必须是实数）。矢量 $\vec{F}_i$ 的分量对应于在无穷多个点 $(u, v)$ 处计算的 $v^{\Delta_\phi} g_i(u,v) - u^{\Delta_\phi} g_i(v,u)$，或者等效地作为围绕某个首选点的泰勒展开系数[8]。$\vec{F}_i$ 有无穷多个分量，但即使我们将其截断到任何有限子集，该方程也成立。从考虑二维子空间已经可以获得一些有趣的结果，但通常，得到下图所示的更严格的界限需要扫描具有大量维数的空间。

矢量 $\vec{F}_i$ 的范数在这个方程中无关紧要，因为它乘以我们不知道的正因子 $\lambda_i^2$。但矢量 $\vec{F}_i$ 指向的方向至关重要：如果对于所有自旋 $\ell_i$ 和所有高于相应幺正性界的 $\Delta_i$，所有矢量 $\vec{F}_i$ 都指向大致相同的方向，那么该方程无解，因为 $\vec{F}_i$ 的任何非平凡线性组合都无法求和为零。图 6.4 展示了这个机制的一个玩具例子。这个观察是所有数值自举算法的核心，其思路如下：我们从对 $\phi$ 的标度维度以及 $\phi\times\phi$ OPE 中出现的具有最低标度维度的算符做出假设开始[9]；然后在这个假设下研究矢量 $\vec{F}_i$ 的行为，并尝试找到一个分离平面，使得所有矢量都指向该平面的同一侧；如果找到了这样的平面，那么方程无法满足，这意味着该假设是错误的。在这个策略上迭代，可以排除参数空间中的整个区域。图 6.5 显示了在 $d=3$ 维中这个过程的结果。

![图 6.4 一个玩具例子，展示了矢量 $\vec{F}_i$ 在三维空间中的行为。对于每个自旋 $\ell_i = 0,2,4,6,\dots$，当 $\Delta_i$ 在幺正性界 $\Delta_{\text{min}}$ 和无穷大之间变化时，$\vec{F}_i$ 在单位球面上画出一条光滑曲线。所有曲线都包含在上半球，除了标量曲线 $\ell=0$，当 $\Delta < \Delta_*$ 时进入下半球。这意味着一个假设不存在标量 primary 算符满足 $\Delta < \Delta_*$ 的理论是被排除的，因为 crossing 方程 (6.33) 无法满足：所有矢量 $\vec{F}_i$ 指向水平分离平面的同一侧，因此它们无法相加为零。注意，这里显示的曲线是虚构的，并不对应于作用在共形块上的实际泛函](image-link)

![图 6.5 虚线显示了通过对两个具有标度维度 $\Delta_\sigma$ 的相同标量算符的 OPE 中第一个算符的标度维度 $\Delta_\varepsilon$ 的上界，该上界由共形自举程序获得。在没有特定理论假设的情况下，这个界显示出一个“扭结”，接近第 6.5 节讨论的 Ising CFT，并用十字标记。蓝色区域是在添加额外假设后剩下的允许区域，即 OPE 具有方程 (6.40) 的形式。注意，此图已过时：目前该岛的大小已经缩小到比最佳 Ising 模型蒙特卡洛模拟的不确定度还要小。图片取自 Kos 等人 [6]。图片版权归作者所有。根据 CC-BY-4.0 许可复制](image-link)

## 6.5 例子：三维 Ising 模型

例如，考虑由作用量描述的理论

$$
S = \int d ^ {3} x \left[ - \frac {1}{2} \partial_ {\mu} \phi \partial^ {\mu} \phi - \frac {1}{2} m ^ {2} \phi^ {2} - \frac {g}{4 !} \phi^ {4} \right]. \tag{6.34}
$$

其中 $g > 0$ 以保证势能从下方有界。注意，在 $d=3$ 维中自由标量场的质量维度为 $[\phi] = 1/2$，因此

$$
\left[ m ^ {2} \right] = 2, \quad [ g ] = 1. \tag{6.35}
$$

由于 $m^2$ 和 $g$ 都具有正的质量维度，它们是相关算符：它们决定低能极限（IR）下的动力学，但在高能（UV）下其重要性降低：在能量 $E \gg g, |m|$ 时，该理论趋近于自由无质量标量场。另一方面，在低能下，物理显然依赖于 $g$ 和 $m$：当 $m^2 \gg g^2$ 时，这是一个质量为 $m$ 的有质量标量理论；当 $m^2 \ll -g^2$ 时，势能在

$$
\langle \phi \rangle = \pm \sqrt {- \frac {6 m ^ {2}}{g}}, \tag{6.36}
$$

处有两个极小值，围绕它们的激发质量为 $\sqrt{2}|m|$。显然，这个理论有两个相，因此必定存在一个 $m^2$ 的中间值（或以 $g$ 为单位，无量纲比 $m^2/g^2$ 的临界值）处发生相变。注意，该理论具有对应于 $\phi \to -\phi$ 的 $\mathbb{Z}_2$ 对称性，在一个相中自发破缺，在另一个相中则没有。

事实证明，精确描述相变点处 IR 物理的理论是一个共形场论。与围绕它的两个相不同，它允许任意小能量的激发（但它们不是粒子）。我们怎么知道的？费曼图计算在 IR 中不可信：渐近微扰级数的近似在 UV 中有效，但在 IR 中失效，就像在 QCD 中一样。理解相变的一种方法是检查 $d\neq 3$ 维中的理论：同样的理论在 $d=4-\varepsilon$ 维中有一个微扰不动点，称为 Wilson-Fisher 不动点。不动点的位置依赖于重整化方案，但存在其他方案无关的量。

例如，算符 $\phi$ 的反常维度就是这样的量。在极限 $\varepsilon \to 1$ 时，最先进的多圈计算给出[10]

$$
\gamma_ {\phi} \approx 0. 0 1 8 2 \quad \Leftrightarrow \quad \Delta_ {\phi} = \frac {d - 2}{2} + \gamma_ {\phi} \approx 0. 5 1 8 2. \tag{6.37}
$$

这个标度维度的估计与一个统计物理模型的标度维度一致：Ising 模型是一个经典自旋 $\sigma_i = \pm 1$ 在晶格上具有最近邻相互作用的理论，由哈密顿量刻画

$$
H = - J \sum_ {\langle i j \rangle} \sigma_ {i} \sigma_ {j}. \tag{6.38}
$$

该模型有一个 $J$ 的临界值，在此值处连续极限由一个 CFT 描述。在这个值处，蒙特卡洛模拟表明两个自旋之间的关联随距离的幂次下降，由下式给出

$$
\Delta_ {\sigma} \approx 0. 5 1 8 1. \tag{6.39}
$$

这两个理论具有完全不同的微观描述：一个是描述闵可夫斯基时空中粒子的量子场论，另一个是欧几里得晶格上的简单理论。更令人惊讶的是，在实验中也能发现相同的临界指数，例如水和其他液体的临界点。这是普适性的一个例子。

这种重合的解释是，能够描述 $\phi^4$ 理论和 Ising 模型相变的候选共形场论并不多。这两个理论共同之处在于：

- 一个全局 $\mathbb{Z}_2$ 对称性（分别为 $\phi \to -\phi$ 和 $\sigma_i \to -\sigma_i$），该对称性在一个相中破缺，在另一个相中未破缺；
- 恰好两个相关算符，都是标量，我们将它们记为 $\sigma$（在 $\mathbb{Z}_2$ 下为奇）和 $\varepsilon$（在 $\mathbb{Z}_2$ 下为偶）。

第二点需要一些澄清。在晶格模型中，除了 $J$，相图还由与外磁场的相互作用刻画，对应于哈密顿量中添加项 $\delta H = -\mu \sum \sigma_i$。在量子场论中，这一说法得到了 UV 中相关 primary 算符列表的支持，见表 6.1 的第一列。这些 primary 中有两个可以合理地预期在相互作用的不动点仍然是 primary 算符：$\phi$ 和 $\phi^2$ 一开始就具有足够低的标度维度。相反，$\phi^4$ 是在 UV 中触发重整化群流的相关算符，因此我们预期它在 IR 中变成无关的（否则流会继续）。$\phi^3$ 是特殊的：一旦耦合 $g$ 被打开，运动方程 $(-\partial^2 + m^2)\phi = \frac{1}{3!}\phi^3$ 意味着它不是独立的 primary 算符，而是 $\phi$ 的 descendant。在携带自旋的算符中，唯一相关的是能动张量 $T^{\mu\nu}$：这个算符存在于任何 QFT 中，因此可以预期它也存在于 IR 中，并且具有不变的标度维度。

表 6.1 拉格朗日量 (6.34) 描述的理论在自由 UV 极限中的 primary 算符列表，以及 IR CFT 中对应的 primary

| UV primary | $\Delta$ | IR primary | $\Delta$ | $\mathbb{Z}_2$ |
| :--- | :--- | :--- | :--- | :--- |
| $\phi$ | 0.5 | $\sigma$ | 0.51815 | Odd |
| $\phi^2$ | 1 | $\varepsilon$ | 1.14126 | Even |
| $\phi^3$ | 1.5 | – | – | – |
| $\phi^4$ | 2 | $\varepsilon'$ | $>3$ | Even |
| $T^{\mu\nu} \sim \partial^\mu\phi\partial^\nu\phi$ | 3 | $T^{\mu\nu}$ | 3 | Even |

共形自举的哲学与此讨论相当正交，它不关心微观细节（晶格模型或拉格朗日理论）。相反，它纯粹依赖对称性论证。除了方法中内置的共形对称性，$\sigma$ 和 $\varepsilon$ 的 $\mathbb{Z}_2$ 变换性质意味着它们的 OPE 具有以下示意形式：

$$
\sigma \times \sigma = \mathbb {1} + \epsilon + T ^ {\mu \nu} + \dots
$$

$$
\sigma \times \epsilon = \sigma + \dots \tag{6.40}
$$

$$
\epsilon \times \epsilon = \mathbb {1} + \epsilon + T ^ {\mu \nu} + \dots
$$

其中点表示来自所有（无限多个）无关 primary 算符的贡献。使用这些性质作为输入，并研究涉及 $\sigma$ 和 $\varepsilon$ 的所有 4 点函数，人们能够将允许的参数区域 $(\Delta_\sigma, \Delta_\varepsilon)$ 缩小到一个围绕实验已知值的小岛，见图 6.5。通过更近期的数值分析，这个允许岛的大小已经缩小到远小于蒙特卡洛模拟的不确定度，因此当前 Ising 模型临界指数的最佳理论预测来自共形自举 ($\Delta_\sigma \approx 0.5181489$)。

这非常令人印象深刻，并极好地说明了统计物理学中普适性概念的工作原理：给定一些非常一般的假设（共形对称性、只有两个相关算符、以及一个 $\mathbb{Z}_2$ 对称性），共形自举基本上确立了存在一个唯一的理论，并提供了具有严格误差棒的极好数值结果。此外，在允许区域和禁止区域的交界处（即岛的边界上），crossing 方程 (6.33) 必须以特殊的方式满足：许多矢量必须精确地位于分离平面上，并且只有它们才能具有非零的 OPE 系数以使方程成立。读出与这些矢量关联的标度维度 $\Delta_i$ 和自旋 $\ell_i$，可以得到进入 OPE 的 primary 算符谱的数值估计。图 6.6 显示了 Ising 模型的这样一个谱估计。该图显示了作为自旋 $\ell_i$ 和差值 $\Delta_i - \ell_i$（称为“扭转”）的函数的算符谱，因此一个基本结构清晰地显现出来：算符被组织成共形 Regge 轨迹。

![图 6.6 三维 Ising 模型中进入 $\sigma\times\sigma$ OPE 的算符谱，自旋高达 40，标度维度与自旋同量级。基于 Simmons-Duffin [8] 的数据。数据版权归作者所有。根据 CC-BY-4.0 许可复制](image-link)

这个观察与 crossing 方程的最新分析理解 [9, 10] 相匹配：每个具有低标度维度 $\Delta_i$（因此根据幺正性界具有低自旋）的算符，通过 crossing 对称性与一簇具有标度维度 $2\Delta_i + 2n + \ell$ 的算符相关联。这就是我们在广义自由场论中看到的，但在 Ising 模型中也相当有效，如图 6.6 所示：对于 $\Delta-\ell < 4$，有三簇算符与值 $\Delta_i - \ell_i = 2\Delta_\sigma, 2\Delta_\varepsilon$ 和 $2\Delta_\sigma+2$ 对齐。这些簇与低标度维度算符之间的等价性已经在无限自旋极限 $\ell \to \infty$ 下被严格证明，并且它们扭转向自旋 $\ell$ 的幂次的领先修正也被很好地理解 [11, 12]。在足够接近广义自由场论的理论中，这种等价性甚至走得更远 [8, 13, 14]。

## 6.6 其他共形自举结果

共形自举的范围并不仅限于 Ising 模型。我们对许多共形场论的理解已因共形自举而显著提升。这在二维和三维理论中尤其如此。在三维中，存在拉格朗日量 (6.34) 到 $N$ 个标量场 $\phi_a$ 的推广，具有 $(\sum \phi_a^2)^2$ 形式的相互作用和一个 $O(N)$ 对称性，自举对此做出了引人注目的物理预测：

- $O(2)$ 模型描述了液氦的超流相变。对这个相变的最佳测量（在航天飞机上进行的实验）与最佳蒙特卡洛模拟之间存在未解决的分歧。在这种情况下，共形自举设定的理论界限与蒙特卡洛结果一致 [15]，呼唤新的实验。
- $O(3)$ 模型描述了海森堡磁体的临界行为。这些是统计物理模型，其中磁化是各向同性的：它可以指向空间中的任何方向，没有首选方向。然而，在实践中，在晶格或固体中达到所需各向同性水平似乎非常困难：$O(3)$ 对称性倾向于自发破缺到其立方子群（立方体的有限对称群）。这里的关键问题是，能够触发从 $O(3)$ 模型到具有立方对称性的 CFT 的 RG 流的 4 指标算符 $O_{ijkl}$ 是否相关。由于它的标度维度意外地非常接近 3，这很难从晶格模拟中确定。共形自举现已严格证明该算符的标度维度低于 3，因此 $O(3)$ 对称性自然倾向于被破缺 [16]。

还有很多与共形自举相关的有趣结果和令人兴奋的开放问题，这里无法一一列举（这个列表不会长时间保持最新）。有关近期总结，请参见例如 2022 年 Snowmass 关于数值共形自举的白皮书 [17]。

# 第七章 结论

还有许多已知的共形场论我们尚未提及：

- 自由无质量理论是共形的。例如任意维数中的自由玻色子和自由费米子，以及在 $d=2n+2$ 维中的 $n$ 形式规范理论（例如 $d=4$ 中的自由矢量理论）。也存在任意多个自由场的理论。我们习惯于将自由理论的希尔伯特空间描述为 Fock 空间（具有确定“粒子数”的态），但也存在对于它们而言由 primary 和 descendant 组成的共形基，这在有效场论方法或哈密顿截断中很有用。
- 存在 $\beta$ 函数具有微扰不动点的理论。典型的例子是具有 $\phi^n$ 型势能的自由标量理论的形变，例如 $d=4-\varepsilon$ 维中的 $\phi^4$ 理论（在微扰论中对非整数维度的处理是可能的）：给定作用量
  $$
  S = \int d ^ {d} x \left[ - \frac {1}{2} \partial_ {\mu} \phi \partial^ {\mu} \phi - \frac {g}{4 !} \phi^ {4} \right], \tag{7.1}
  $$
  $g$ 的 $\beta$ 函数可以计算为
  $$
  \beta_ {g} = \mu \frac {d g}{d \mu} = - \varepsilon + \frac {3 g}{(4 \pi) ^ {2}} + \mathcal {O} (g ^ {2}), \tag{7.2}
  $$
  当
  $$
  \frac {g _ {*}}{(4 \pi) ^ {2}} = \frac {\varepsilon}{3}. \tag{7.3}
  $$
  时为零。在极限 $\varepsilon\ll 1$ 中，高阶修正可忽略。在 $d=6+\varepsilon$ 维中存在类似的 $\phi^3$ 相互作用的不动点，或在 $d=3$ 维附近有 $\phi^6$ 相互作用的不动点。
- 在 $SU(N_c)$ 规范理论与 $N_f$ 个费米子（在基础表示中）的 $\beta$ 函数中也可以找到类似的固定点，其规范耦合 $\alpha = g^2/(4\pi)^2$ 的领先阶为
  $$
  \beta_ {\alpha} = \mu \frac {d \alpha}{d \mu} = - \frac {2}{3} \alpha^ {2} (1 1 N _ {c} - 2 N _ {f}) + \mathcal {O} (\alpha^ {3}). \tag{7.4}
  $$
  当 $N_f = \frac{11}{2}N_c$ 时，$\beta$ 函数中的领先阶项为零，因此次领阶项变得重要。在该值附近，前两项重要性相当，并且当 $N_f \lesssim \frac{11}{2}N_c$ 时发现一个微扰不动点。这被称为 (Caswell-)Banks-Zaks 不动点。处于这种情况的理论像 QCD 一样是渐近自由的，但它在低能下趋近一个相互作用的共形场论。对于像 QCD 这样的 $SU(3)$ 规范理论，这个临界值是 $N_f = 16.5$。有强有力的证据来自晶格模拟表明 $N_f = 16$ 的理论是共形的。另一方面，低 $N_f$ 的理论（QCD 有 3 个轻夸克）显然是禁闭的，意味着其低能极限是无质量 Goldstone 玻色子（如果夸克无质量）或有质量$\pi$介子的理论。存在一个临界值 $N_f^* \approx 12$，高于该值时，我们预期在低能极限下出现一个相互作用的共形场论。区间 $N_f^* \leq N_f \leq \frac{11}{2}N_c$ 被称为共形窗口。注意，具有不同规范群和/或费米子以不同方式耦合到规范场（即处于不同表示）的规范理论也可以拥有共形窗口。甚至可以通过不仅使用费米子还使用标量来设计具有微扰 UV 不动点的规范理论。

- 还存在具有扩展超对称性的理论，其中 $\beta$ 函数在微扰论的所有阶都精确为零，例如 $\mathcal{N}=4$ 超对称 Yang-Mills 理论。更一般地，在具有足够多超对称性的理论中，通常只需在领 order 使 $\beta$ 函数为零，然后非重整化定理确保其在所有阶为零。当与超对称性结合时，共形代数被扩展为更大且更刚性的结构。所有超共形代数已被分类，并且仅限于维度 $d \leq 6$（参见文献 [2, 3] 的近期综述）。
- 在二维中，我们在第 2 章提到存在更多的 Killing 矢量，因此有更多的共形生成元。在具有能动张量的理论中，这产生了无限维的 Virasoro 代数，该代数已被用于完全解决一类极小模型。人们还可以将二维 CFT 放在环面上，并在自举框架中研究其配分函数的模性质。这是一个浩瀚的课题，有其自身的文献 [4–9]。
- 最后，另一类 CFT 是通过将量子场论放在 $(d+1)$ 维反德西特（AdS）时空中得到的理论族。AdS 允许一个具有球面边界的紧致化，该边界上的关联函数同构于 $d$ 维共形场论的关联函数。这里有两种截然不同的情况：一方面，可以考虑渐近 AdS 时空的量子引力理论；这些理论对偶于具有能动张量（和一些特殊性质）的真正 CFT。另一方面，也可以将局域量子场论放在固定的 AdS 背景中，并研究其边界上的 CFT 关联函数；这个 CFT 不一定有能动张量，实际上它与广义自由场论（或大 $N$ 理论）非常相似。在后一种方法中研究无穷大 AdS 半径的极限，揭示了与平坦空间散射振幅的有趣联系。这一观察是最近复兴的 $S$ 矩阵自举技术 [11] 的核心。

这个非详尽的列表显示了共形场论在理论物理学中变得多么重要。但是正如粒子物理学家所知，自然界肯定不是标度不变的，那么我们为什么如此关心 CFT 呢？

有时研究一个课题的最佳动机是其美感，我们希望这份对 CFT 的粗浅介绍至少能反映其部分魅力。但粒子物理学家也有非常实际的理由对 CFT 感兴趣。首先，这里呈现的一些共形自举结果为强耦合量子场论的动力学提供了独特的视角，这是微扰论无法达到的。此外，未来将在 $3+1$ 维闵可夫斯基时空中推导出的可能 CFT 的约束，必将教会我们关于规范理论（如 QCD、大统一理论或各种超出标准模型的情景）的重要课程。到目前为止，在 $3+1$ 维中，一般的自举界限仍然相对较弱且缺乏特征。已知存在的 CFT 是规范理论，这带来了额外的困难，因为规范群的信息以复杂的方式编码在 CFT 数据中。然而，这不应被视为共形自举的失败，而应被视为对下一代理论物理学家的挑战！