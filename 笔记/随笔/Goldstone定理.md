---
up:
  - "[[随笔]]"
related:
date: 2026-01-31
---
Goldstone 定理说的是：

> **如果一个连续的全局对称性在真空中被自发破缺，那么理论中必然出现质量为零的玻色激发（Goldstone 模式）。**


#### 定理在说什么问题？

我们关心三样东西：

1. 拉氏量的对称性（全局、连续）
2. 真空是否保持这个对称性
3. 低能激发（粒子谱）长什么样

Goldstone 定理把这三件事绑在了一起。


# 定义的前提

Goldstone 定理有非常明确的假设条件：

## (A) 连续的全局对称性

存在一个连续群 $G$ ，其生成元  $Q^{a}$ 满足

$$[Q^{a} , H] = 0 $$

**局域对称性不算**（这点后面会直接关系到 [[Higgs 机制]]）。

## (B) 真空自发破缺

真空不对称说的是：对称性在拉氏量中存在，但在真空中没有体现出来。所以问题是，有没有某种可观测量，能够区分“对称真空”和“非对称真空”？而态的对称性，只能通过算符的期望值来判断，所以我们的问题是，是否存在某个算符 $\mathcal{O}$ 使得在在对称变换下非平凡变换 $\delta_{a}\mathcal{O} = i[Q^{a},\mathcal{O}] \neq{0}$ 。总之我就可以将真空不对称做如下的定义：

>[!green] Define
>对于参考真空 $\ket{0}$ ，若存在某个算符 $\mathcal{O}(x)$ ，使得
>
>$$\langle{0}|[Q^{a} , \mathcal{O}(x)]|0\rangle \neq 0$$
>
>就称真空在生成元 $Q^{a}$ 对应的全局变换 $G$ 下自发破缺(不对称)。
>ps. 由于真空平移不变性，该条件与 $x$ 的选取无关。

当然可以说本质应该是 $Q^{a}\ket{0}\neq 0$ 但是有时这个定义可能不是良的，上面则不会有这样的情况。

## (c) 洛伦兹不变性 + 正规量子场论结构



# 定理证明

设理论具有连续全局对称性，Noether 定理给出守恒流
$$\partial_{\mu}j^{\mu}_{a} = 0 $$
定义守恒荷：$Q^{a} = \int d^{3}x\ j_{a}^{0}(x)$ 则
$$[Q^{a} , H] = 0 $$
由于真空不对称所以
$$\langle{0}|[Q^{a},\mathcal{O}(0)]|0\rangle \neq{0} $$
而
$$[Q^{a},\mathcal{O}(0)] = \int d^{3}x [j_{a}^{0},\mathcal{O}(0)] $$
考虑两点函数
$$\begin{align}\langle{0}|j_{a}^{0}(x)\mathcal{O}(0)|0\rangle &= \sum_{n} \langle{0}|j_{a}^{0}(x)|n\rangle\langle{n}|\mathcal{O}(0)|n\rangle \\
&=\sum_{n} \langle{0}|e^{ iP\cdot x }j_{a}^{0}(0)e^{ -iP\cdot x }| n\rangle\langle{n}|\mathcal{O}(0)|0\rangle \\
&= \sum_{n} e^{ -ip_{n}\cdot x }\langle{0|j_{a}^{0}}(0)|n\rangle\langle{n}|\mathcal{O}(0)|0\rangle \end{align}$$
$$\begin{align}\int d^{3}x \langle{0}|j_{a}^{0}(x)\mathcal{O}(0)|0\rangle &= \sum_{n}\int d^{3}x e^{ -ip_{n}\cdot x }\langle{0|j_{a}^{0}}(0)|n\rangle\langle{n}|\mathcal{O}(0)|0\rangle \\
&= \sum_{n} (2\pi)^{3}\delta^{(3)}(\mathbf{p}_{n}) e^{ -iE_{n}t }\langle{0|j_{a}^{0}}(0)|n\rangle\langle{n}|\mathcal{O}(0)|0\rangle \end{align}$$
$$\begin{align}\langle{0}|[Q^{a},\mathcal{O}(0)]|0\rangle &= \sum_{n} (2\pi)^{3}\delta^{(3)}(\mathbf{p}_{n})[e^{ -iE_{n}t }\langle{0|j_{a}^{0}}(0)|n\rangle\langle{n}|\mathcal{O}(0)|0\rangle \\
&\qquad\qquad\qquad\qquad - e^{ iE_{n}t }\langle{0}|\mathcal{O}(0)|n\rangle\langle{n}|j^{0}_{a}(0)|0\rangle ] \end{align} $$
可见非平凡的贡献必然有 $\mathbf{p}= 0$ 而
$$e^{ -iEt }(\dots) + e^{ iEt }(\dots)$$
则这个结构是随时间变换的，这违背了真空不对称的要求，所以中间态有非平凡贡献的粒子必然有 $E\equiv0$ 

这意味着，唯一有贡献的态是 $\mathbf{p}=0,E=0$ 即 $p^{2}=0$ ，也就是说存在一个零质量的单粒子态 $\ket{\pi^{a}}$ 满足：
$$\langle{0}|j^{\mu}_{a}(0)|\pi^{b}(p)\rangle \neq 0 $$
这正是 **Goldstone 玻色子**。洛伦兹协变性进一步强迫：
$$\langle{0}|j^{\mu}_{a}(x)|\pi^{b}(p)\rangle = if_{\pi}\delta^{ab} p^{\mu} e^{ -ip\cdot x } $$

ps. 这里预设了有完备态 $\{ \ket{n} \}$ 这可能不是必要的，但是我想把完备性关系换成 $\sum_{\lambda}\int \frac{d^{3}p}{(2\pi)^{3}2E} |\mathbf{p},\lambda \rangle\langle{\mathbf{p},\lambda}|$ 结果是一致的，毕竟我只是拿 $\ket{n}$ 进行了 $\exp(-ip\cdot x)\ket{n}=\exp(-ip_{n}\cdot x)\ket{n}$ 而这个事 $\ket{\mathbf{p},\lambda}$ 也做得到。

# 输出有效拉式量

说一个东西存在不是我们的终极目标，一个很美的想法是，如果我们能够知道 场的类型、对称群、对称群的一个表示 就能一口气抓出来 所有的Goldstone玻色子拉式量的样子 就好了。


首先我们有一个场 $\psi$ ，对称群 $G$ 及其的一个表示 $\rho$。

因为不变子群 $H$ 有 $\rho(h)\langle{\psi\rangle}=\langle{\psi \rangle}=vn_{0}$ 其中 $n_{0}$ 是单位矢量，由此若记 $H$ 的生成元是 $T^{a}$ 则 $T^{a}\langle{\psi}\rangle=0$ ，于是我们反过来能确定不变子群 $H$ 。

由此我们能得到真空等价类 $M_{\text{vac}}=G / H$ ，作为流形我们能为其切空间设置局部坐标系 $\{ X_{a} \}$ ，于是能够表达商群的元素 $U(\pi)=\exp(i\pi^{a}X_{a})$ ，这个被称为 Goldstone 场。

然后 $U(\pi)$ 的坐标展开需要流形 $G / H$ 的坐标系，实际上这个在定义真空期望值时已经干了，直接取那里的坐标系即可，$n^{i}(x)=(U(\pi(x))n_{0})^{i}$ 。

最后将场 $\psi$ 重新表述：$\psi^{i}(x)=[v + h(x)]n^{i}(x)$ 其中的 $h(x)$ 是表征径向自由度的场，是一个值，可以通过计算两边矢量大小得到。最后把 $\psi(x)$ 代回拉式量即可。

# O(N) 例

就是有一个 $N$ 分量的实标量场 $\phi^{N}$，对称群是 $O(N)$ 。拉式量是
$$\mathcal{L} = \frac{1}{2}(\partial_{\mu}\phi^{i})^{2} - \frac{\lambda}{4}(\phi^{i}\phi^{i} - v^{2})^{2} $$

那么场的真空期望值是 $\langle{\phi^{N}}\rangle\in \mathbb{R}^{N}$ 我们可以通过调整真空将期望值取为 $\langle{\phi^{N}}\rangle=(0,\dots,v)^{T}$  (所以真空矢量为 $(0,\dots,1)$)。

于是不变子群的生成元有 $T^{a}(0,\dots,v)^{T}=0$ 可见保持这个向量不变的变换是那些只在前 $N-1$ 个分量中旋转，所以 $H=O(N-1)$ 

于是真空等价类 $M_{\text{vac}}=O(N) / O(N-1)\simeq S^{N-1}$ 其生成元是$$(X_{a})_{ij}=\delta_{ia}\delta_{Nj}-\delta_{iN}\delta_{aj},\quad a=1,\dots,N-1$$ Goldstone 场为
$$U(\pi) = \exp\left(  \frac{i\pi^{a}X_{a}}{v}  \right) $$
$$n^{i}(x) =( U(\pi)n_{0} )^{i}= \left\{ \begin{align} \frac{\pi^{i}}{|\pi|} \sin \frac{|\pi|}{v}, &\quad i=1\dots,N-1 \\ \cos \frac{|\pi|}{v}, &\quad i=N \end{align} \right. $$

所以场可以分解：
$$\phi^{i}(x) = [ v + h(x) ] n^{i}(x) $$
$$(\partial_{\mu}\phi^{i})^{2} = (\partial_{\mu}h)^{2} + (v+h)^{2} (\partial_{\mu}n^{i})^{2} $$
$$\mathcal{L} = (\partial_{\mu}h)^{2} + (v+h)^{2} (\partial_{\mu}n^{i})^{2} - \frac{\lambda}{4}( (v+h)^{2} - v^{2})^{2} $$
在小 Goldstone 场极限 $\frac{\pi^{a}}{v} \ll 1$ 下有近似
$$n^{i} \approx \left(  \frac{\pi^{a}}{v} , 1 - \frac{\pi^{2}}{2v^{2}}  \right) ,\quad a=1,\dots,N-1 $$
于是
$$\mathcal{L} = \frac{1}{2}(\partial_{\mu}h^{a})^{2} + \frac{1}{2}(\partial_{\mu}\pi^{a})^{2} + \frac{h}{v}(\partial_{\mu}\pi^{a})^{2} - \lambda v^{2}h^{2} - \lambda vh^{3} - \frac{\lambda}{4}h^{4} $$


# 几何视角

再次回忆，设时空是一个微分流形 $M$ 其配备度规 $g_{\mu \nu}=(+,-,-,-)$ (Minkowski) 因而还是一个 Riemann 流形，流形的元素是事件 $x$ 其可被局部坐标系描述。场是一种映射 $\psi:M\to \mathcal{T}$ ，对于标量场 $\mathcal{T}\simeq \mathbb{R}$ ，对于旋量场 $\mathcal{T}\simeq \mathbb{C}^{2}$ ... 当像空间 $\mathcal{T}$ 确定时，所有可能的映射 $\psi$ 构成一个空间 $\mathcal{C}$ 

...