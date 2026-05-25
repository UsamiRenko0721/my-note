---
up:
  - "[[感悟]]"
---
自由标量场的拉式量为
$$\mathcal{L}_{0} = \frac{1}{2}(\partial^{\mu}\phi)^{2} - \frac{1}{2}m^{2}\phi^{2} $$
$\phi^{4}$ 是一个最简单的满足量纲、局域、洛伦兹不变、幺正的相互作用项，于是考虑了这样一项后的拉式量为
$$\mathcal{L} = \frac{1}{2}(\partial^{\mu}\phi)^{2} - \frac{1}{2}m^{2}\phi^{2} - \frac{\lambda}{4!} \phi^{4} $$

# 导出费曼规则

## 前戏准备

生成泛函
$$Z[J] = \int \mathcal{D\phi} \ \exp \left\{  i \int \mathrm{d^{4}x} \ \left[  \frac{1}{2}(\partial^{\mu}\phi)^{2} - \frac{1}{2}m\phi^{2} - \frac{\lambda}{4!}\phi^{4} + J\phi \right]  \right\} $$
将其拆分为自由部分与相互作用部分：
$$Z[J] = \exp\left(  i \int \mathrm{d^{4}x} \, \mathcal{L}_{\text{int}} \left(  \frac{1}{i} \frac{\partial}{\partial J}  \right)  \right) Z_{0}[J] $$
其中
$$Z_{0}[J] = \exp\left(  -\frac{i}{2} \int \mathrm{d^{4}x} \ \mathrm{d^{4}y} \ J(x) \Delta_{F}(x-y) J(y)  \right) $$
对相互作用指数作微扰展开：
$$Z[J] = \sum_{n=0}^{\infty} \frac{1}{n!}\left( -\frac{i\lambda}{4!} \right)^{n} \prod_{k=1}^{n} \int \mathrm{d^{4}x_{k}} \left(  \frac{1}{i} \frac{\partial}{\partial J(x_{k})}  \right)^{4} Z_{0}[J] $$
每一次泛函微分作用在 $Z_{0}[J]$ 上，都会产生一个传播子：
$$\frac{1}{i} \frac{\partial}{\partial J(x_{k})} Z_{0}[J] = \int \mathrm{d^{4}y} \ \Delta_{F}(x_{k}-y) J(x_{k})Z_{0}[J] $$
在最终取 $J=0$ 时，只保留**完全由传播子配对的项**。

定义时间有序 $n$ 点函数：
$$G^{(n)}(x_{1},\dots,x_{n}) = \frac{1}{i^{n}} \left. \frac{\partial^{n}Z_{0}[J]}{\partial J(x_{1})\dots \partial J(x_{n})} \right|_{J=0} $$
代入展开式后，$G^{(n)}$ 被表示为：各阶 $\lambda^k$ 的项之和；每一项对应若干传播子的配对方式。此处自动得到 Wick 收缩，无需额外假设。

生成泛函可写成
$$Z[J] = Z_{0}[J] e^{ iW[J] } $$
其中 $W[J]$ 只生成**连通关联函数**。在实际散射计算中，只需使用连通部分；所有纯真空泡贡献被 $Z[0]$ 消去。

采用傅里叶变换约定：
$$\phi(x) = \int \mathrm{\frac{d^{4}p}{(2\pi)^{4}}} \phi(p) $$
自由传播子：
$$\Delta_{F}(p) = \frac{i}{p^{2}-m^{2}+i\varepsilon} $$
相互作用项：
$$\int \mathrm{d^{4}x} \ \phi^{4}(x) \to (2\pi)^{4}\delta^{(4)}\left( \sum p - \sum p' \right) $$

## 顶点因子

考虑一次相互作用插入（$n=1$）：
$$ -\frac{i\lambda}{4!} \int \mathrm{d^{4}x} \left(  \frac{1}{i} \frac{\partial}{\partial J(x)} \right)^{4} $$
当该算符作用在 $Z_0[J]$ 上并最终取 $J=0$ 时四个泛函微分必须两两作用在不同的 $J$ 上，4! 种排列方式完全抵消分母中的 4!。因此每一个相互作用点**净贡献一个因子**
$$-i\lambda $$
并伴随一个空间积分 $\int \mathrm{d^{4}x}$

## 传播子

自由生成泛函为
$$Z_{0}[J] = \exp\left(  -\frac{i}{2} \int \mathrm{d^{4}x} \ \mathrm{d^{4}y} \ J(x) \Delta_{F}(x-y) J(y)  \right) $$
对其作两次泛函微分：
$$\frac{1}{i^{2}} \left. \frac{\partial^{2}Z_{0}[J]}{\partial J(x)\partial J(y)} \right|_{J=0} = \Delta_{F}(x-y) $$
因此每一次 Wick 配对必然产生一个费曼传播子
$$\Delta_{F}(x-y) $$
不存在其它类型的二点结构。

## Wick 收缩与图形结构

在计算 $n$ 点函数时每个顶点提供 4 个场，所有场必须通过 Wick 收缩成对。于是每一对收缩 ↔ 一条内部或外部线，每一个相互作用插入 ↔ 一个四价顶点。

## 动量空间中的传播子

将费曼传播子傅里叶变换
$$\Delta_{F}(x-y) = \int \frac{\mathrm{d^{4}p}}{(2\pi)^{4}} \frac{i}{p^{2}-m^{2}+i\varepsilon} e^{ ip\cdot (x-y) } $$
因此，在动量空间中
$$每一条内部线 \to \frac{i}{p^{2}-m^{2}+i\varepsilon} $$

## 顶点动量守恒

考虑一个顶点积分：
$$\int \mathrm{d^{4}x} \ e^{ -i(p_{1}+p_{2}+p_{3}+p_{4})\cdot x } = (2\pi)^{4} \delta^{(4)}(p_{1}+p_{2}+p_{3}+p_{4}) $$
因此每一个相互作用点都自动产生一个四动量守恒 delta 函数

## 内部动量积分

对于内部传播子，其动量并未被外部指定，因此，每一个未固定的内部动量必须对其进行积分
$$\int \frac{\mathrm{d^{4}k}}{(2\pi)^{4}} $$
该积分直接来自傅里叶展开中对中间动量变量的求和。

## 对称因子

对称因子来自两部分：
1. 微扰展开中的 $\frac{1}{n!}$
2. Wick 收缩中等价配对的重复计数

最终规则是：

> **每一个拓扑不同的收缩结构只计算一次，其余重复通过对称因子消去。**

不需要人为引入，只需忠实执行展开。

至此，$\phi^4$ 理论的微扰计算规则完全确定。


# 树图四点函数与 2→2 散射振幅

## 四点关联函数的最低阶项

生成泛函为
$$Z[J] = \int \mathcal{D\phi} \ \exp \left\{  i \int \mathrm{d^{4}x} \ \left[  \frac{1}{2}(\partial^{\mu}\phi)^{2} - \frac{1}{2}m\phi^{2} - \frac{\lambda}{4!}\phi^{4} + J\phi \right]  \right\} $$
时间有序 $4$ 点关联函数为
$$G^{(n)}(x_{1,2,3,4}) = \left. \frac{\partial^{4}Z_{0}[J]}{\partial J(x_{1})\dots \partial J(x_{4})} \right|_{J=0} = \langle\Omega|\mathsf{T}\{ \phi(x_{1})\phi(x_{2})\phi(x_{3})\phi(x_{4}) \}|\Omega \rangle $$
四点关联函数可以用路径积分表示为：
$$G^{(4)}(x_{1,2,3,4}) = \frac{\displaystyle \int \mathcal{D\phi} \ \phi(x_{1})\phi(x_{2})\phi(x_{3})\phi(x_{4}) e^{ i \int \mathrm{d^{4}x} \ \mathcal{L} }}{\displaystyle \int \mathcal{D\phi} \ e^{ i \int \mathrm{d^{4}x} \ \mathcal{L} } } $$
而
$$e^{ i \int \mathrm{d^{4}x} \ \mathcal{L} } = e^{ i \int \mathrm{d^{4}x} \ \mathcal{L}{_{0}} } \left[  1 - \frac{i\lambda}{4!} \int \mathrm{d^{4}x} \ \phi(x) + \dots  \right] $$
所以关联函数的微扰展开为
$$G^{(4)}(x_{1,2,3,4}) = \frac{\langle 0|\mathsf{T}\left\{  \phi(x_{1})\phi(x_{2})\phi(x_{3})\phi(x_{4})e^{ -i\lambda/4! \int \mathrm{d^{4}x} \ \phi^{4}(x) } \right\}|0 \rangle}{\langle 0|\mathsf{T}\left\{  e^{ -i\lambda/4! \int \mathrm{d^{4}x} \ \phi^{4}(x) }  \right\}0\rangle} $$
首先，自由理论（λ=0）的四点关联函数为：
$$\begin{align}
\langle 0|\mathsf{T}\{ \phi(x_{1})\phi(x_{2})\phi(x_{3})\phi(x_{4}) \} | 0\rangle &= G(x_{1}-x_{2})G(x_{3}-x_{4}) \\ &\quad + G(x_{1}-x_{3})G(x_{2}-x_{4}) \\ &\quad + G(x_{1}-x_{4})G(x_{2}-x_{3}) 
\end{align}$$
在树图级别，四点顶点直接来自相互作用项的一阶。实际上，四点关联函数在树图级别由四个外腿通过一个四点顶点连接而成。对应的贡献是（在坐标空间中）：
$$-i\lambda \int \mathrm{d^{4}x} \ G(x_{1}-x)G(x_{2}-x)G(x_{3}-x)G(x_{4}-x) $$
