---
up:
  - "[[写题]]"
related:
date:
tags:
  - 量子场论
  - 习题
---

# 3.1 洛伦兹群

回忆洛伦兹对易关系（式(3.17)）：

$$
[J^{\mu\nu}, J^{\rho\sigma}] = i(g^{\nu\rho}J^{\mu\sigma} - g^{\mu\rho}J^{\nu\sigma} - g^{\nu\sigma}J^{\mu\rho} + g^{\mu\sigma}J^{\nu\rho}).
$$

## (a) 旋转与推动的生成元

定义旋转和推动的生成元为：

$$
L^{i} = \frac{1}{2}\epsilon^{ijk}J^{jk}, \quad K^{i} = J^{0i},
$$

其中 $i,j,k=1,2,3$。无穷小洛伦兹变换可写为：

$$
\Phi\ \rightarrow\ (1-i\boldsymbol{\theta}\cdot\mathbf{L}-i\boldsymbol{\beta}\cdot\mathbf{K})\Phi.
$$

写出这些矢量算符的显式对易关系（例如 $[L^{i},L^{j}]=i\epsilon^{ijk}L^{k}$）。证明组合：

$$
\mathbf{J}_{+}=\tfrac{1}{2}(\mathbf{L}+i\mathbf{K}) \quad\text{和}\quad \mathbf{J}_{-}=\tfrac {1}{2}(\mathbf{L}-i\mathbf{K})
$$

彼此对易，并分别满足角动量的对易关系。


$$\begin{align}
[J^{i}_{+} , J^{j}_{+}] &= \frac{1}{4} ( [ L^{i} , L^{j} ] + i[L^{i},K^{j}] + i[K^{i},L^{j}] - [ K^{i} , K^{j} ] ) \\
&= \frac{1}{4} ( i\varepsilon^{ijk} L^{k} - \varepsilon^{ijk} K^{k} - \varepsilon^{ijk} K^{k} + i\varepsilon^{ijk} L^{k} ) \\
&= \frac{i\varepsilon^{ijk}}{2} ( L^{k} + iK^{k} ) \\
&= i\varepsilon^{ijk} J^{k}_{+}
\end{align} $$
$$\begin{align}
[ J^{i}_{+},J^{j}_{-} ] &= \frac{1}{4} ( [L^{i} , L^{j}] - i[L^{i},K^{j}] + i[K^{i},L^{j}] + [K^{i},K^{j}] )  \\
&= \frac{1}{4} ( i\varepsilon^{ijk}L^{k} + \varepsilon^{ijk} K^{k} - \varepsilon^{ijk} K^{k} - i\varepsilon^{ijk} L^{k} ) \\
&= 0
\end{align} $$
$$\begin{align}
[J^{i}_{-},J^{j}_{-}] &= \frac{1}{4} ( [L^{i},L^{j}] - i[L^{i},K^{j}] - i[K^{i} , L^{j}] - [K^{i},K^{j}] ) \\
&=\frac{1}{4} ( i\varepsilon^{ijk} L^{k} + \varepsilon^{ijk}K^{k} +\varepsilon^{ijk}K^{k} + i\varepsilon^{ijk}L^{k} ) \\
&= \frac{i\varepsilon^{ijk}}{2} (L^{k} - iK^{k}) \\
&= i\varepsilon^{ijk} J^{k}_{-}
\end{align} $$

---

## (b) 有限维表示

旋转群的有限维表示恰好对应角动量的允许值：整数或半整数。 (a) 的结果意味着洛伦兹群的所有有限维表示对应于整数或半整数对 $(j_{+},j_{-})$，对应旋转群的两个表示。利用在自旋 $1/2$ 角动量表示中 $\mathbf{J}=\boldsymbol{\sigma}/2$ 的事实，明确写出按照洛伦兹群的 $(\tfrac{1}{2},0)$ 和 $(0,\tfrac{1}{2})$ 表示变换的 2 分量的变换规律。证明这些恰好对应于 (3.37) 中给出的 $\psi_{L}$ 和 $\psi_{R}$ 的变换。


对于 $\left( \frac{1}{2},0 \right)$ 
$$L^{i} = (J^{i}_{+} + J^{i}_{-}) = \frac{1}{2}\sigma^{i} , \quad K^{i} = -i(J^{i}_{+} - J^{i}_{-}) = -\frac{i}{2}\sigma^{i} $$
洛伦兹变换就能用泡利矩阵表示了
$$D(\Lambda) = e^{ -i\theta^{i}\sigma^{i}/2 -\vartheta^{i}\sigma^{i}/2 } $$
这对应了左手旋量的变换规则
$$\psi_{L} \to \exp\left(  -i\boldsymbol{\theta}\cdot \frac{\boldsymbol{\sigma}}{2} - \boldsymbol{\beta}\cdot \frac{\boldsymbol{\sigma}}{2}  \right) \psi_{L} $$

对于 $\left(0 , \frac{1}{2} \right)$ 
$$L^{i} = \frac{1}{2}\sigma^{i} , \quad K^{i} = \frac{i}{2}\sigma^{i} $$
$$D(\Lambda) = e^{ -i\theta^{i}\sigma^{i}/2 + \vartheta^{i}\sigma^{i}/2 } $$
这对应了右手旋量的变换规则
$$\psi_{R} \to \exp\left( -i\boldsymbol{\theta}\cdot \frac{\boldsymbol{\sigma}}{2} + \boldsymbol{\beta}\cdot \frac{\boldsymbol{\sigma}}{2} \right) \psi_{R} $$


---
## (c) 四矢量表示

恒等式 $\boldsymbol{\sigma}^{T}=-\sigma^{2}\boldsymbol{\sigma}\sigma^{2}$ 允许我们将 $\psi_{L}$ 变换改写为幺正等价形式：

$$
\psi^{\prime}\rightarrow\psi^{\prime}(1+i\boldsymbol{\theta}\cdot\frac{\boldsymbol{\sigma}}{2}+\boldsymbol{\beta}\cdot\frac{\boldsymbol{\sigma}}{2}),
$$

其中 $\psi^{\prime}=\psi_{L}^{T}\sigma^{2}$。利用此规律，我们可以将按 $(\tfrac{1}{2},\tfrac{1}{2})$ 表示变换的对象表示为一个 $2\times 2$ 矩阵，该矩阵在左侧具有 $\psi_{R}$ 变换规律，同时在右侧具有转置的 $\psi_{L}$ 变换规律。将此矩阵参数化为：

$$
\left(\begin{array}{cc}V^{0}+V^{3}&V^{1}-iV^{2}\\ V^{1}+iV^{2}&V^{0}-V^{3}\end{array}\right).
$$

证明对象 $V^{\mu}$ 按四矢量变换。



由题意一个洛伦兹变换作用到 $M$ 上是 $M\to \Lambda_{R}M\Lambda^{T}_{L}$ 其中 $\Lambda_{L}$ 和 $\Lambda_{R} = (\Lambda ^{\dagger}_{L})^{-1}$ 分别是 $\left( \frac{1}{2},0 \right)$ 和 $\left( 0 , \frac{1}{2} \right)$ 表示
$$M = V^{\mu}\sigma_{\mu} , \quad \sigma^{\mu} \equiv (1,\boldsymbol{\sigma}) , \bar{\sigma}^{\mu}\equiv(1,-\boldsymbol{\sigma}) $$
则
$$V^{\mu} = \frac{1}{2} \mathrm{Tr}( \bar{\sigma}^{\mu} M  )  $$
变换导致
$$V'^{\mu} = \frac{1}{2} \mathrm{Tr}(\bar{\sigma}^{\mu} \Lambda_{R} M \Lambda^{T}_{L}) = \frac{1}{2} \mathrm{Tr}(\Lambda^{T}_{L} \bar{\sigma}^{\mu} \Lambda_{R} M ) = \frac{1}{2} \mathrm{Tr}( \Lambda^{\mu}_{~~\nu} \bar{\sigma}^{\nu} M ) = \Lambda^{\mu}_{~~\nu} \frac{1}{2} \mathrm{Tr}(\bar{\sigma}^{\nu}M) = \Lambda^{\mu}_{~~\nu} V^{\nu} $$
可见确实 $V^{\mu}$ 按矢量进行变换

---

# 3.2 戈登恒等式

推导 **戈登恒等式**：

$$
\bar{u}(p^{\prime})\gamma^{\mu}u(p)=\bar{u}(p^{\prime})\bigg{[}\frac{p^{\prime\mu}+p^{\mu}}{2m}+\frac{i\sigma^{\mu\nu}q_{\nu}}{2m}\bigg{]}u(p),
$$

其中 $q=(p^{\prime}-p)$。我们将在第6章使用这个公式。


由 Dirac 方程
$$
\not p u(p) = m u(p) , \quad \bar{u}(p') \not p' = m \bar{u}(p')
$$
$$\bar{u}(p')( \gamma^{\mu} \gamma\cdot p ) u(p) = m \bar{u}(p') \gamma^{\mu} u(p) , \quad \bar{u}(p')(\gamma\cdot p'\gamma^{\mu}) u(p) = m \bar{u}(p') \gamma^{\mu} u(p) $$
$$\bar{u}(p')( \gamma^{\mu} \gamma\cdot p + \gamma\cdot p' \gamma^{\mu} )u(p) = 2m \bar{u}(p') \gamma^{\mu} u(p) $$
其中
$$\gamma^{\mu} \gamma\cdot p = \gamma^{\mu} \gamma^{\nu} p_{\nu} = (g^{\mu \nu} - i\sigma^{\mu \nu})p_{\nu} = p^{\mu} - i\sigma^{\mu \nu}p_{\nu}  $$
$$\gamma^{\mu} \gamma\cdot p + \gamma\cdot p' \gamma^{\mu}  = p^{\mu} + p'^{\mu} + i\sigma^{\mu \nu}(p'_{\nu} - p_{\mu}) = (p+p')^{\mu} + i\sigma^{\mu \nu}q_{\nu} $$
所以
$$\bar{u}(p')[ (p+p')^{\mu} + i\sigma^{\mu \nu}q_{\nu} ]u(p) = 2m \bar{u}(p') \gamma^{\mu} u(p) $$
$$\bar{u}(p^{\prime})\gamma^{\mu}u(p)=\bar{u}(p^{\prime})\bigg{[}\frac{p^{\prime\mu}+p^{\mu}}{2m}+\frac{i\sigma^{\mu\nu}q_{\nu}}{2m}\bigg{]}u(p),$$


---

# 3.3 旋量积

（此问题与问题5.3和5.6一起，介绍了一种处理涉及无质量粒子过程的高效计算方法。）令 $k_{0}^{\mu}$, $k_{1}^{\mu}$ 为满足 $k_{0}^{2}=0$, $k_{1}^{2}=-1$, $k_{0}\cdot k_{1}=0$ 的固定四矢量。按以下方式定义基本旋量：令 $u_{L0}$ 为动量为 $k_{0}$ 的费米子的左手旋量。令 $u_{R0}=\not{k}_{1}u_{L0}$。那么，对于任何满足 $p$ 类光（$p^{2}=0$）的 $p$，定义：

$$
u_{L}(p)=\frac{1}{\sqrt{2p\cdot k_{0}}}\not{p}u_{R0}, \qquad u_{R}(p)=\frac{1}{\sqrt{2p\cdot k_{0}}}\not{p}u_{L0}.
$$

这组约定明确地定义了旋量的相位（除非 $p$ 与 $k_{0}$ 平行）。

### (a)
证明 $\not{k}_{0}u_{R0}=0$。证明对于任何类光 $p$，有 $\not{p}u_{L}(p)=\not{p}u_{R}(p)=0$。


已知对于类光矢量 $p$ 有 $\not{ \! k_{0} } u_{R0}=0$ 和 $\not{ \! p }u_{L}(p) = \not{ \! p }u_{R}(p)$ 所以 $u_{R 0}$ 是一个有动量 $k_{0}$ 的无质量旋量，而 $u_{L}(p)$ 和 $u_{R}(p)$ 是有动量 $p$ 的无质量旋量
$$\not{ \! k_{0} } u_{R 0} = \not{ \! k_{0} } \not{ \! k_{1} } u_{L 0} = (2g^{\mu \nu} -\gamma^{\nu}\gamma^{\mu})k_{0,\mu}k_{1,\nu} u_{L 0} = 2k_{0}\cdot k_{1} u_{L 0} - \not{ \! k_{1} } \not{ \! k_{0} } u_{L 0} = 0$$
所以按照定义
$$\not{ \! p } u_{L}(p) = \frac{1}{\sqrt{ 2p\cdot k_{0} }} \not{ \! p }\not{ \! p }u_{R 0} = \frac{1}{\sqrt{ 2p\cdot k_{0} }} p^{2} u_{R 0} = 0 $$
同理
$$\not{ \! p }u_{R}(p) = 0 $$

---
### (b)
对于选择 $k_{0}=(E,0,0,-E)$, $k_{1}=(0,1,0,0)$，显式构造 $u_{L0}$, $u_{R0}$, $u_{L}(p)$ 和 $u_{R}(p)$。


就是一个线代问题嘛，在 weyl 表示下
$$\not{ \! k_{0} } u_{L 0} = \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 2E \\
2E & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{pmatrix}u_{L 0} = 0 \implies u_{L 0} \equiv \begin{pmatrix}
0  \\
\sqrt{ 2E } \\
0 \\
0
\end{pmatrix} $$
$$u_{R 0} = \not{ \! k_{1} } u_{L 0} = \begin{pmatrix}
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & -1 & 0 & 0 \\
-1 & 0 & 0 & 0
\end{pmatrix} u_{L 0} \equiv \begin{pmatrix}
0 \\
0 \\
-\sqrt{ 2E } \\
0
\end{pmatrix} $$
于是这就是基了，对于任意动量 $p$ 的左右手旋量直接带公式就好
$$\begin{align}
u_{L}(p) &= \frac{1}{\sqrt{ 2p\cdot k_{0} }} \not{ \! p }u_{R 0} \\
&= \frac{1}{\sqrt{ 2E(p_{0}+p_{3}) }} \begin{pmatrix}
0 & 0 & p_{0}+p_{3} & p_{1}-ip_{2} \\
0 & 0 & p_{1}+ip_{2} & p_{0}-p_{3} \\
p_{0}-p_{3} & -p_{1}+ip_{2} & 0 & 0 \\
-p_{1}-ip_{2} & p_{0}+p_{3} & 0 & 0
\end{pmatrix} \begin{pmatrix}
0 \\
0 \\
-\sqrt{ 2E } \\
0
\end{pmatrix} \\
&= \frac{1}{\sqrt{ p_{0}+p_{3} }} \begin{pmatrix}
-(p_{0}+p_{3}) \\
-(p_{1}+ip_{2}) \\
0 \\
0
\end{pmatrix}
\end{align} $$
$$u_{R}(p) = \frac{1}{\sqrt{ 2p\cdot k_{0} }} \not{ \! p } u_{L 0} = \frac{1}{\sqrt{ p_{0}+p_{3} }} \begin{pmatrix}
0 \\
0 \\
-p_{1}+ip_{2} \\
p_{0}+p_{3}
\end{pmatrix} $$


---
### (c)
对于类光的 $p_{1},p_{2}$，通过下式定义旋量积 $s(p_{1},p_{2})$ 和 $t(p_{1},p_{2})$：

$$
s(p_{1},p_{2}) = \bar{u}_{R}(p_{1})u_{L}(p_{2}), \quad t(p_{1},p_{2}) = \bar{u}_{L}(p_{1})u_{R}(p_{2}).
$$

使用 (b) 部分给出的 $u_{\lambda}$ 的显式形式，显式计算旋量积，并证明 $t(p_{1},p_{2}) = (s(p_{2},p_{1}))^{*}$ 和 $s(p_{1},p_{2}) = -s(p_{2},p_{1})$。此外，证明：

$$
|s(p_{1},p_{2})|^{2} = 2p_{1}\cdot p_{2}.
$$

因此旋量积是四矢量点积的平方根。


依旧计算
$$\begin{align}
s(p,q) &= u^{\dagger}_{R}(p) \gamma^{0} u_{L}(q) = \frac{1}{\sqrt{ p_{0}+p_{3} }\sqrt{ q_{0}+q_{3} }} \begin{pmatrix}
0 & 0 & -p_{1}-ip_{2} & p_{0}+p_{3}
\end{pmatrix} \begin{pmatrix}
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
1 & 0 & 0 & 0
\end{pmatrix}\begin{pmatrix}
-(q_{0}+q_{3}) \\
-(q_{1}+iq_{2}) \\
0 \\
0
\end{pmatrix}\\
&= \frac{(p_{1}+ip_{2})(q_{0}+q_{3}) - (q_{1}+iq_{2})(p_{0}+p_{3})}{\sqrt{ p_{0}+p_{3} }\sqrt{ q_{0}+q_{3} }} 
\end{align} $$
$$\begin{align}
t(p,q) &= u_{L}^{\dagger}(p)\gamma^{0}u_{R}(q) = \frac{1}{\sqrt{ p_{0}+p_{3} }\sqrt{ q_{0}+q_{3} }} \begin{pmatrix}
-(p_{0}+p_{3}) & -p_{1}+ip_{2} & 0 & 0
\end{pmatrix}\begin{pmatrix}
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
1 & 0 & 0 & 0
\end{pmatrix}\begin{pmatrix}
0 \\
0 \\
-p_{1}+ip_{2} \\
p_{0}+p_{3}
\end{pmatrix} \\
&= \frac{(q_{1}-iq_{2})(p_{0}+p_{3}) - (p_{1}-ip_{2})(q_{0}+q_{3})}{\sqrt{ p_{0}+p_{3} }\sqrt{ q_{0}+q_{3} }}
\end{align}  $$
可见 $t(p,q) = (s(q,p))^{*}$ , $s(p,q)=-s(q,p)$ 注意类光矢量有 $p^{2}=q^{2}=0$ 即可
$$\begin{align}
|s(p,q)|^{2} &= \frac{|q_{1}(p_{0}+p_{3})-p_{1}(q_{0}+q_{3}) - iq_{2}(p_{0}+p_{3}) + ip_{2}(q_{0}+q_{3})|^{2}}{(p_{0}+p_{3})(q_{0}+q_{3})}  \\
&= \frac{(p_{0}q_{1}+p_{3}q_{0}-p_{1}q_{0}-p_{1}q_{3})^{2} + (p_{2}q_{0}+p_{2}q_{3}-p_{0}q_{2}-p_{3}q_{2})^{2}}{(p_{0}+p_{3})(q_{0}+q_{3})}  \\
&= q_{1}^{2} \frac{p_{0}+p_{3}}{q_{0}+q_{3}} + p_{1}^{2} \frac{q_{0}+q_{3}}{p_{0}+p_{3}} + q_{2}^{2} \frac{p_{0}+p_{3}}{q_{0}+q_{3}} + p_{2}^{2} \frac{q_{0}+q_{3}}{p_{0}+p_{3}} - 2(p_{1}q_{1}+p_{2}q_{2}) \\
&= (q_{1}^{2} + q_{2}^{2}) \frac{p_{0}+p_{3}}{q_{0}+q_{3}} + (p\leftrightarrow q) - 2(p_{1}q_{1}+p_{2}q_{2}) \\
&= (q_{0}^{2}-q_{3}^{2}) \frac{p_{0}+p_{3}}{q_{0}+q_{3}} + (p\leftrightarrow q) - 2(p_{1}q_{1}+p_{2}q_{2}) \\
&= (q_{0}+q_{3})(p_{0}+p_{3}) + (p\leftrightarrow q) - 2(p_{1}q_{1} + p_{2}q_{2}) \\
&= 2(p_{0}q_{0}-p_{1}q_{1}-p_{2}q_{2}-p_{3}q_{3}) \\
&= 2p\cdot q
\end{align} $$


---

# 3.4 马约拉纳费米子

回忆式 (3.40)，可以为作为狄拉克旋量 $(\psi_{L})$ 的上两个分量变换的无质量 2 分量费米子场写下相对论性方程。将这样的 2 分量场记为 $\chi_{a}(x)$，$a=1,2$。

### (a)
证明可以以下述方式将 $\chi(x)$ 的方程写为有质量场：

$$
i\bar{\sigma}\cdot\partial\chi - im\sigma^{2}\chi^{*} = 0.
$$

即，首先证明该方程是相对论不变的；其次证明它蕴含克莱因-戈登方程 $(\partial^{2}+m^{2})\chi = 0$。这种形式的费米子质量项称为马约拉纳质量项。


洛伦兹变换作用到这些量上的结果是这样的，注意区分 $\chi\in\left( \frac{1}{2},0 \right),\chi^{*}\in\left( 0, \frac{1}{2} \right)$ 

$$x^{\mu}\to \Lambda^{\mu}_{~~\nu}x^{\nu} ,\quad \partial_{\mu} \to (\Lambda^{-1})^{\nu}_{~~\mu}\partial_{\nu} , \quad \chi(x) \to U_{L}(\Lambda)\chi(x) , \quad \chi^{*}(x) \to U_{R}(\Lambda)\chi(x) ,\quad \bar{\sigma}^{\mu}U_{L}(\Lambda)=U_{R}(\Lambda)\Lambda^{\mu}_{~~\nu}\bar{\sigma}^{\nu} $$ 
其中 $U^{\dagger}_{L}(\Lambda)U_{R}(\Lambda)=\mathbf{1}$ 。所以对于 $i\bar{\sigma}^{\mu}\partial_{\mu}\chi = im\sigma^{2}\chi^{*}$ 

$$LHS \to i\bar{\sigma}^{\mu}\Lambda^{\nu}_{~~\mu}\partial_{\nu}(U_{L}(\Lambda)\chi) = i\big( \bar{\sigma}^{\mu} U_{L}(\Lambda) \big) \Lambda^{\nu}_{~~\mu} \partial_{\nu}\chi = i \big( U_{R}(\Lambda)\Lambda^{\mu}_{~~\nu} \bar{\sigma}^{\nu} \big) \Lambda^{\nu}_{~~\mu} \partial_{\nu}\chi = U_{R}(\Lambda) i \bar{\sigma}^{\mu}\partial_{\mu}\chi $$
$$RHS \to im\sigma^{2} U_{R}(\Lambda)\chi^{*} = U_{R}(\Lambda) im\sigma^{2}\chi^{*}  $$

可见方程左右边在洛伦兹变换下的变换规则相同，所以方程是相对论不变的


方程和它的共轭是
$$\begin{gather}
i\bar{\sigma}^{\mu}\partial_{\mu}\chi - im\sigma^{2}\chi^{*}=0 \\
-i\bar{\sigma}^{*\mu}\partial_{\mu}\chi^{*}+im\sigma^{*2}\chi=0
\end{gather} $$
其中 $\sigma^{2*}=-\sigma^{2}$ , $\sigma^{\mu*}=(\sigma^{\mu})^{T}$ , $(\sigma^{2})^{2}=\mathbf{1}$从第一个得到
$$\chi^{*} = \frac{1}{m} (\sigma^{2})^{-1} \bar{\sigma}^{\mu}\partial_{\mu}\chi = \frac{1}{m} \sigma^{2} \bar{\sigma}^{\mu}\partial_{\mu}\chi $$
代入第二个方程
$$\begin{align}
0 &= (\bar{\sigma}^{\mu})^{T} \partial_{\mu} \left(  \frac{1}{m} \sigma^{2} \bar{\sigma}^{\nu}\partial_{\nu} \chi  \right) + m\sigma^{2} \chi  \\
&= \frac{(\bar{\sigma}^{\mu})^{T}\sigma^{2}\bar{\sigma}^{\nu}}{m} \partial_{\mu}\partial_{\nu} \chi + m\sigma^{2}\chi \\
&= g^{\mu \nu} \sigma^{2} \partial_{\mu}\partial_{\nu} + m^{2}\sigma^{2}\chi \\
&= \partial^{2}\chi + m^{2}\chi
\end{align} $$
其中由于对称性 $$(\bar{\sigma}^{\nu})^{T} \sigma^{2}\bar{\sigma}^{\mu} = \sigma^{2}\sigma^{\nu}\bar{\sigma}^{\mu} \implies (\bar{\sigma}^{\nu})^{T} \sigma^{2}\bar{\sigma}^{\mu} = \frac{1}{2}( \sigma^{2}\sigma^{\nu}\bar{\sigma}^{\mu} + \sigma^{2}\sigma^{\mu}\bar{\sigma}^{\nu} ) = \frac{1}{2} \sigma^{2} \cdot 2g^{\mu \nu} \mathbf{1} = \sigma^{2}g^{\mu \nu} $$


---
### (b)
马约拉纳方程是否可从拉格朗日量导出？质量项看起来像是 $(\sigma^{2})_{ab}\chi_{a}^{*}\chi_{b}^{*}$ 的变分；然而，由于 $\sigma^{2}$ 是反对称的，如果 $\chi(x)$ 是普通的 c 数场，该表达式将为零。在量子场论中，我们知道 $\chi(x)$ 将成为反对易的量子场。因此，通过将 $\chi(x)$ 视为经典的反对易场来发展其经典理论是有意义的，即作为以格拉斯曼数为值的场，满足：

$$
\alpha\beta = -\beta\alpha \quad \text{对于任何 }\alpha,\beta.
$$

注意此关系意味着 $\alpha^{2} = 0$。格拉斯曼场 $\xi(x)$ 可以在函数基中展开为：

$$
\xi(x) = \sum_{n}\alpha_{n}\phi_{n}(x),
$$

其中 $\phi_{n}(x)$ 是正交的 c 数函数，$\alpha_{n}$ 是一组独立的格拉斯曼数。定义格拉斯曼数乘积的复共轭以反转顺序：

$$
(\alpha\beta)^{*} \equiv \beta^{*}\alpha^{*} = -\alpha^{*}\beta^{*}.
$$

此规则模仿量子场的厄米共轭。证明经典作用量：

$$
S = \int d^{4}x\left[\chi^{\dagger}i\bar{\sigma}\cdot\partial\chi + \frac{im}{2}(\chi^{T}\sigma^{2}\chi - \chi^{\dagger}\sigma^{2}\chi^{*})\right],
$$

是实的，并且关于 $\chi$ 和 $\chi^{*}$ 变分此 $S$ 得到马约拉纳方程。


说这么多，无非就是要来证明 $S^{*}=S$ 写出来看看就好

$$S = \int d^{4}x\left[\chi^{\dagger}i\bar{\sigma}\cdot\partial\chi + \frac{im}{2}(\chi^{T}\sigma^{2}\chi - \chi^{\dagger}\sigma^{2}\chi^{*})\right]$$
$$\begin{align}
S^{*} &= \int \mathrm{d^{4}x} \left[  (\chi ^{\dagger}i\bar{\sigma}\cdot \partial \chi)^{*} - \frac{im}{2}( \chi^{T}\sigma^{2}\chi - \chi ^{\dagger}\sigma^{2}\chi^{*} )^{*}  \right] \\
&= \int \mathrm{d^{4}x} \left[  -\chi^{T}i \bar{\sigma}\cdot \partial \chi^{*} - \frac{im}{2} \chi ^{\dagger}(\sigma^{2})^{*} \chi^{*} + \frac{im}{2} \chi^{T} (\sigma^{2})^{*} \chi  \right] \\
&= \int \mathrm{d^{4}x} \left[  -\chi^{T}i \bar{\sigma}\cdot \partial \chi^{*} + \frac{im}{2} \chi ^{\dagger}\sigma^{2} \chi^{*} - \frac{im}{2} \chi^{T} \sigma^{2} \chi  \right] \\
&= \int \mathrm{d^{4}x} \left[ \partial_{\mu}\chi ^{\dagger} i\bar{\sigma}^{\mu}\chi + \frac{im}{2} \chi ^{\dagger}\sigma^{2} \chi^{*} - \frac{im}{2} \chi^{T} \sigma^{2} \chi    \right] \\
&= \int \mathrm{d^{4}x} \left[  \partial_{\mu} \chi^{*}_{a} i(\bar{\sigma}^{\mu})_{ab} \chi_{b} + \frac{im}{2} \chi ^{\dagger}\sigma^{2} \chi^{*} - \frac{im}{2} \chi^{T} \sigma^{2} \chi   \right] \\
&= \int \mathrm{d^{4}x} \left[  \partial_{\mu} \chi_{a} i(\bar{\sigma}^{\mu})_{ab} \chi_{b}^{*} + \frac{im}{2} \chi ^{\dagger}\sigma^{2} \chi^{*} - \frac{im}{2} \chi^{T} \sigma^{2} \chi  \right] \\
&= \int d^{4}x\left[\chi^{\dagger}i\bar{\sigma}\cdot\partial\chi + \frac{im}{2}(\chi^{T}\sigma^{2}\chi - \chi^{\dagger}\sigma^{2}\chi^{*})\right] \\
&= S
\end{align} $$
然后变分算方程
$$\frac{\delta S}{\delta \chi^{*}_{a}} = i(\bar{\sigma}^{\mu})_{ab}\partial_{\mu}\chi_{b} - im(\sigma^{2})_{ab}\chi_{b}^{*} = 0 $$
$$\frac{\delta S}{\delta \chi ^{\dagger}} = i\bar{\sigma}\cdot \partial \chi - im\sigma^{2}\chi ^{\dagger} = 0 $$
这就是 (a) 中导出的方程


---
### (c)
让我们将 4 分量狄拉克场写为：

$$
\psi(x)=\left(\begin{array}{c}\psi_{L}\\ \psi_{R}\end{array}\right),
$$

并回忆 $\psi$ 的下分量的变换方式，通过一个幺正变换等价于表示 $\psi_{L}$ 的复共轭。这样，我们可以用两个 2 分量旋量重写 4 分量狄拉克场：

$$
\psi_{L}(x)=\chi_{1}(x), \qquad \psi_{R}(x)=i\sigma^{2}\chi^{*}_{2}(x).
$$

用 $\chi_{1}$ 和 $\chi_{2}$ 重写狄拉克拉格朗日量，并注意质量项的形式。


$$\begin{align}
\mathcal{L} &= \bar{\psi}(i\not{ \! \partial } -m)\psi  \\
&= \begin{pmatrix}
\chi_{1}^{\dagger} & -i\chi_{2}^{T}\sigma^{2}
\end{pmatrix} \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix} \begin{pmatrix}
-m & i\sigma\cdot \partial \\
i\bar{\sigma}\cdot \partial & -m
\end{pmatrix}\begin{pmatrix}
\chi_{1} \\i\sigma^{2}\chi_{2}^{*}
\end{pmatrix} \\
&= \begin{pmatrix}
\chi_{1}^{\dagger} & -i\chi_{2}^{T}\sigma^{2}
\end{pmatrix}\begin{pmatrix}
i\bar{\sigma}\cdot \partial & -m \\
-m & i\sigma \cdot \partial
\end{pmatrix}\begin{pmatrix}
\chi_{1} \\i\sigma^{2}\chi_{2}^{*}
\end{pmatrix} \\
&= \chi_{1}^{\dagger}i\bar{\sigma}\cdot \partial \chi_{1} - \chi_{1}^{\dagger}mi\sigma^{2}\chi_{2}^{*} + i\chi_{2}^{T}\sigma^{2}m\chi_{1} +i\chi_{2}^{T}\sigma^{2} \sigma\cdot \partial(\sigma^{2}\chi_{2}^{*}) \\
&= i\chi_{1}^{\dagger}\bar{\sigma}\cdot \partial \chi_{1} + i\chi_{2}^{\dagger}\bar{\sigma}\cdot \partial \chi_{2} -im ( \chi_{1}^{\dagger}\sigma^{2}\chi_{2}^{*} - \chi_{2}^{T}\sigma^{2}\chi_{1})
\end{align} $$
其中
$$\sigma^{2}\sigma^{\mu}\sigma^{2} = (\bar{\sigma}^{\mu})^{*} $$


---
### (d)
证明 (c) 部分的作用量具有全局对称性。分别计算 (b) 和 (c) 部分理论中以下流的散度：

$$
J^{\mu}=\chi^{\dagger}\bar{\sigma}^{\mu}\chi, \qquad J^{\mu}=\chi_{1}^{\dagger}\bar{\sigma}^{\mu}\chi_{1}-\chi_{2}^{\dagger}\bar{\sigma}^{\mu}\chi_{2},
$$

并将你的结果与这些理论的对称性联系起来。构造一个具有 $O(N)$ 对称性（即 $N$ 维空间中旋转的对称性）的 $N$ 个自由有质量 2 分量费米子场的理论。


显然有 $U(1)$ 对称性，做变换 $\psi\to e^{ i\alpha }\psi$ 则 $\chi_{1}\to e^{ i\alpha }\chi_{1},\chi_{2}\to e^{ -i\alpha }\chi_{2}$ 诺顿守恒流是
$$J^{\mu} = \bar{\psi}\gamma^{\mu}\psi = \chi_{1}^{\dagger}\bar{\sigma}^{\mu}\chi_{1} - \chi_{2}^{\dagger}\bar{\sigma}^{\mu}\chi_{2} $$
其中的左右手旋量满足方程 (下面两个是上面两个的共轭形式)
$$\begin{gather}
i\bar{\sigma}\cdot \partial \chi_{1} - im\sigma^{2}\chi_{2}^{*} = 0 \\
i\bar{\sigma}\cdot \partial \chi_{2} - im\sigma^{2}\chi_{1}^{*} = 0 \\
i(\partial_{\mu}\chi_{1}^{\dagger})\bar{\sigma}^{\mu} - im\chi_{2}^{T}\sigma^{2} = 0 \\
i(\partial_{\mu}\chi_{2}^{\dagger})\bar{\sigma}^{\mu} - im\chi_{1}^{T}\sigma^{2} = 0
\end{gather}$$
于是
$$\begin{align}
\partial_{\mu}J^{\mu} &= (\partial_{\mu}\chi_{1}^{\dagger})\bar{\sigma}^{\mu}\chi_{1} + \chi_{1}^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi_{1} - (\chi_{1}\leftrightarrow \chi_{2}) \\
&= m\chi_{2}^{T}\sigma^{2}\chi_{1} + m\chi_{1}^{\dagger}\sigma^{2}\chi_{2}^{*} - m\chi_{1}^{T}\sigma^{2}\chi_{2} - m\chi_{2}^{\dagger}\sigma^{2}\chi_{1}^{*} \\
&= 0
\end{align} $$
最后一步是二次型的双线性导致的，所以我在想似乎定义内积为
$$\langle \chi_{1},\chi_{2}\rangle \equiv \chi_{1}^{T}\sigma^{2}\chi_{2} $$
会方便描述很多呢


---
### (e)
将 (a) 和 (b) 部分的马约拉纳理论量子化。即将 $\chi(x)$ 提升为满足正则反对易关系：

$$
\{\chi_{a}(\mathbf{x}),\chi_{b}^{\dagger}(\mathbf{y})\}=\delta_{ab}\delta^{(3)}(\mathbf{x}-\mathbf{y}),
$$

的量子场，构造一个厄米哈密顿量，并找到一组对角化哈密顿量的产生湮灭算符的正则表示。（提示：将 $\chi(x)$ 与量子化狄拉克场的顶部两个分量进行比较。）


先看量子化前的哈密顿量怎么写
$$\begin{align}
H &= \int \mathrm{d^{3}x} \left(  \frac{\partial \mathcal{L}}{\partial(\partial_{0}\chi)}\partial_{0}\chi  - \mathcal{L}  \right) \\
&= \int \mathrm{d^{3}x} \left(  i\chi ^{\dagger}\boldsymbol{\sigma}\cdot \nabla \chi + \frac{im}{2} ( \chi ^{\dagger}\sigma^{2}\chi^{*} - \chi^{T}\sigma^{2}\chi )  \right)
\end{align} $$
从量子化条件我们尝试导出产生湮灭算符的对易性，首先旋量可以展开为
$$\chi(x) = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \sqrt{ \mathbf{p}\cdot \boldsymbol{\sigma} } \sum_{\lambda} [\xi(\mathbf{p},\lambda) a_{\mathbf{p},\lambda} e^{ -ip\cdot x } + (-i\sigma^{2})\xi^{*}(\mathbf{p},\lambda)a^{\dagger}_{\mathbf{p},\lambda} e^{ ip\cdot x }]$$
则可以导出
$$\{ a_{\mathbf{p},a},a_{\mathbf{q},b}^{\dagger} \} = \delta_{ab} \delta^{(3)}(\mathbf{p}-\mathbf{q}) , \quad \{ a_{\mathbf{p},a} , a_{\mathbf{q},b} \} = \{ a^{\dagger}_{\mathbf{p},a} , a^{\dagger}_{\mathbf{q},b} \} = 0 $$
代回到哈密顿量完成量子化
$$\begin{aligned} H &= \int \mathrm{d}^3x \int \frac{\mathrm{d}^3p\mathrm{d}^3q}{(2\pi)^6\sqrt{2E_p 2E_q}} \sum_{a,b} \left[ \left( \xi_a^\dagger a_a^\dagger(\mathbf{p})e^{-i\mathbf{p}\cdot\mathbf{x}} + \zeta_a^\dagger (i\sigma^2) a_a(\mathbf{p})e^{i\mathbf{p}\cdot\mathbf{x}} \right) \right. \times (\nabla\cdot\sigma)^\dagger (- \mathbf{q}\cdot\sigma)\sqrt{\mathbf{q}\cdot\sigma} \left( \xi_b a_b(\mathbf{q})e^{i\mathbf{q}\cdot\mathbf{x}} - (i\sigma^2)\zeta_b^\dagger a_b^\dagger(\mathbf{q})e^{-i\mathbf{q}\cdot\mathbf{x}} \right) \\ 
&\quad + \frac{im}{2} \left( \xi_a^\dagger a_a^\dagger(\mathbf{p})e^{-i\mathbf{p}\cdot\mathbf{x}} + \zeta_a^\dagger (i\sigma^2) a_a(\mathbf{p})e^{i\mathbf{p}\cdot\mathbf{x}} \right)  \times (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(\mathbf{q}\cdot\sigma)^\dagger} \left( \zeta_b^\dagger a_b^\dagger(\mathbf{q})e^{-i\mathbf{q}\cdot\mathbf{x}} + (-i\sigma^2)\xi_b a_b(\mathbf{q})e^{i\mathbf{q}\cdot\mathbf{x}} \right) \\ 
&\quad \left. - \frac{im}{2} \left( \zeta_a a_a(\mathbf{p})e^{i\mathbf{p}\cdot\mathbf{x}} + \xi_a (i\sigma^2) a_a^\dagger(\mathbf{p})e^{-i\mathbf{p}\cdot\mathbf{x}} \right) \times (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{\mathbf{q}\cdot\sigma} \left( \xi_b a_b(\mathbf{q})e^{i\mathbf{q}\cdot\mathbf{x}} + (-i\sigma^2)\zeta_b^\dagger a_b^\dagger(\mathbf{q})e^{-i\mathbf{q}\cdot\mathbf{x}} \right) \right] \\
&= \int \mathrm{d}^3x \int \frac{\mathrm{d}^3p\mathrm{d}^3q}{(2\pi)^6\sqrt{2E_p 2E_q}} \sum_{a,b} \Bigg\{ a_a^\dagger(\mathbf{p})a_b(\mathbf{q}) \xi_a^\dagger \left[ (\nabla\cdot\sigma)^\dagger (- \mathbf{q}\cdot\sigma)\sqrt{\mathbf{q}\cdot\sigma} \right.+ \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(\mathbf{q}\cdot\sigma)^\dagger} (-i\sigma^2) - \frac{im}{2} (i\sigma^2)(\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{\mathbf{q}\cdot\sigma} \Bigg] \xi_b e^{-i(\mathbf{p}-\mathbf{q})\cdot\mathbf{x}} \\ 
&\quad + a_a^\dagger(\mathbf{p})a_b^\dagger(\mathbf{q}) \xi_a^\dagger \left[ - (\nabla\cdot\sigma)^\dagger (- \mathbf{q}\cdot\sigma)\sqrt{\mathbf{q}\cdot\sigma} (i\sigma^2) + \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(\mathbf{q}\cdot\sigma)^\dagger} \right. \left. - \frac{im}{2} (i\sigma^2)(\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{\mathbf{q}\cdot\sigma} (-i\sigma^2) \right] \zeta_b^\dagger e^{-i(\mathbf{p}+\mathbf{q})\cdot\mathbf{x}} \\ 
&\quad + a_a(\mathbf{p})a_b(\mathbf{q}) \zeta_a^\dagger (i\sigma^2) \left[ (\nabla\cdot\sigma)^\dagger (- \mathbf{q}\cdot\sigma)\sqrt{\mathbf{q}\cdot\sigma} + \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(\mathbf{q}\cdot\sigma)^\dagger} (-i\sigma^2) \right. \left. - \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{\mathbf{q}\cdot\sigma} \right] \xi_b e^{i(\mathbf{p}+\mathbf{q})\cdot\mathbf{x}} \\ 
&\quad + a_a(\mathbf{p})a_b^\dagger(\mathbf{q}) \zeta_a^\dagger (i\sigma^2) \left[ - (\nabla\cdot\sigma)^\dagger (- \mathbf{q}\cdot\sigma)\sqrt{\mathbf{q}\cdot\sigma} (i\sigma^2) + \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(\mathbf{q}\cdot\sigma)^\dagger} \right.\left. - \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{\mathbf{q}\cdot\sigma} (-i\sigma^2) \right] \zeta_b^\dagger e^{i(\mathbf{p}-\mathbf{q})\cdot\mathbf{x}} \Bigg\} \\
&= \int \frac{\mathrm{d}^3p}{(2\pi)^3 2E_p} \sum_{a,b} \Bigg\{ a_a^\dagger(\mathbf{p})a_b(\mathbf{p}) \xi_a^\dagger \left[ (\nabla\cdot\sigma)^\dagger (- \mathbf{p}\cdot\sigma)\sqrt{\mathbf{p}\cdot\sigma} + \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(\mathbf{p}\cdot\sigma)^\dagger} (-i\sigma^2) - \frac{im}{2} (i\sigma^2)(\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{\mathbf{p}\cdot\sigma} \right] \xi_b \\ 
&\quad + a_a^\dagger(\mathbf{p})a_b^\dagger(-\mathbf{p}) \xi_a^\dagger \left[ - (\nabla\cdot\sigma)^\dagger (\mathbf{p}\cdot\sigma)\sqrt{-\mathbf{p}\cdot\sigma} (i\sigma^2) + \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(-\mathbf{p}\cdot\sigma)^\dagger} - \frac{im}{2} (i\sigma^2)(\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{-\mathbf{p}\cdot\sigma} (-i\sigma^2) \right] \zeta_b^\dagger \\ 
&\quad + a_a(\mathbf{p})a_b(-\mathbf{p}) \zeta_a^\dagger (i\sigma^2) \left[ (\nabla\cdot\sigma)^\dagger (\mathbf{p}\cdot\sigma)\sqrt{-\mathbf{p}\cdot\sigma} + \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(-\mathbf{p}\cdot\sigma)^\dagger} (-i\sigma^2) - \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{-\mathbf{p}\cdot\sigma} \right] \xi_b \\ 
&\quad + a_a(\mathbf{p})a_b^\dagger(-\mathbf{p}) \zeta_a^\dagger (i\sigma^2) \left[ - (\nabla\cdot\sigma)^\dagger (\mathbf{p}\cdot\sigma)\sqrt{-\mathbf{p}\cdot\sigma} (i\sigma^2) + \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{(-\mathbf{p}\cdot\sigma)^\dagger} - \frac{im}{2} (\nabla\cdot\sigma)^\dagger \sigma^2 \sqrt{-\mathbf{p}\cdot\sigma} (-i\sigma^2) \right] \zeta_b^\dagger \Bigg\} \\
&= \int \frac{\mathrm{d}^3p}{(2\pi)^3 2E_p} \sum_{a,b} \frac{1}{2}\left( E_p^2 + |\mathbf{p}|^2 + m^2 \right) \left[ a_a^\dagger(\mathbf{p})a_b(\mathbf{p}) \xi_a^\dagger \xi_b - a_a(\mathbf{p})a_b^\dagger(\mathbf{p}) \zeta_a^T \zeta_b^\dagger \right] \\ 
&= \int \frac{\mathrm{d}^3p}{(2\pi)^3} \frac{E_p}{2} \sum_{a} \left[ a_a^\dagger(\mathbf{p})a_a(\mathbf{p}) - a_a(\mathbf{p})a_a^\dagger(\mathbf{p}) \right] \\ &= \int \frac{\mathrm{d}^3p}{(2\pi)^3} E_p \sum_{a} a_a^\dagger(\mathbf{p})a_a(\mathbf{p}) \end{aligned} $$


---

# 3.5 超对称

可以编写具有连续对称性连接费米子和玻色子的场论；这种变换称为 **超对称**。

### (a)
超对称场论的最简单例子是自由复标量玻色子和自由外尔费米子的理论，写为以下形式：

$$
\mathcal{L}=\partial_{\mu}\phi^{*}\partial^{\mu}\phi+\chi^{\dagger}i\bar{\sigma}\cdot\partial\chi+F^{*}F.
$$

这里 $F$ 是一个辅助复标量场，其场方程为 $F=0$。证明该拉格朗日量在无穷小变换下不变（差一个全散度）：

$$
\begin{aligned}
\delta\phi &= -i\epsilon^{T}\sigma^{2}\chi, \\
\delta\chi &= \epsilon F + \sigma\cdot\partial\phi\,\sigma^{2}\epsilon^{*}, \\
\delta F &= -i\epsilon^{\dagger}\bar{\sigma}\cdot\partial\chi,
\end{aligned}
$$

其中参数 $\epsilon_{a}$ 是格拉斯曼数的 2 分量旋量。


$$\delta(\partial_{u}\phi^{*}\partial^{\mu}\phi) = (i\partial_{\mu}\chi ^{\dagger}\sigma^{2}\varepsilon^{*})\partial^{\mu}\phi + \partial_{\mu }\phi^{*}\partial^{\mu}(-i\varepsilon^{T}\sigma^{2}\chi) $$
$$\begin{align}
\delta(\chi ^{\dagger}i\bar{\sigma}\cdot \partial \chi) &= (\delta \chi ^{\dagger})i\bar{\sigma}\cdot \partial \chi + \chi ^{\dagger}i\bar{\sigma}\cdot \partial(\delta \chi)  \\
&= (\varepsilon ^{\dagger}F^{*} + \varepsilon^{T}\sigma^{2}(\partial_{\nu}\phi^{*})\sigma^{\nu})i\bar{\sigma}\cdot \partial \chi + \chi ^{\dagger}i\bar{\sigma}\cdot \partial(\varepsilon F+\sigma\cdot \partial \phi \sigma^{2}\varepsilon^{*}) \\
&= iF^{*}\varepsilon ^{\dagger}\bar{\sigma}\cdot \partial \chi + i\partial_{\mu}[ \varepsilon^{T}\sigma^{T}\sigma^{\nu}\bar{\sigma} ^{\mu}\partial_{\nu}\phi^{*} \chi] - i\varepsilon^{T}\sigma^{2}\sigma^{\nu}\bar{\sigma}^{\mu}(\partial_{\nu}\partial_{\mu}\phi^{*})\chi + i\chi ^{\dagger}\bar{\sigma}^{\mu}\varepsilon \partial_{\mu}F + i\chi ^{\dagger}\bar{\sigma}^{\mu}\sigma^{\nu}\sigma^{2}\varepsilon^{*}\partial_{\mu}\partial_{\nu}\phi  \\
&= iF^{*}\varepsilon ^{\dagger}\bar{\sigma}\cdot \partial \chi + i\partial_{\mu}[ \varepsilon^{T}\sigma^{T}\sigma^{\nu}\bar{\sigma} ^{\mu}\partial_{\nu}\phi^{*} \chi] - i\varepsilon^{T}\sigma^{2}(\partial^{2}\phi^{*})\chi + i\chi ^{\dagger}\bar{\sigma}^{\mu}\varepsilon \partial_{\mu}F + i\chi ^{\dagger} \sigma^{2}\varepsilon^{*}\partial^{2}\phi
\end{align} $$
$$\delta(F^{*}F) = (i\partial_{\mu}\chi ^{\dagger}\bar{\sigma}^{\mu}\varepsilon)F - iF^{*}\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi $$
$$\begin{align}
\delta \mathcal{L} = i\partial_{\mu}[ \chi ^{\dagger}\sigma^{2}\varepsilon^{*}\partial^{\mu}\phi + \chi ^{\dagger}\bar{\sigma}^{\mu}\varepsilon F + \phi^{*}\varepsilon^{T}\sigma^{2}(\sigma^{\mu}\sigma^{\nu}\sigma_{\nu}-\partial^{\mu})\chi ]
\end{align} $$


---
### (b)
证明项：

$$
\Delta\mathcal{L}=[m\phi F+\tfrac{1}{2}im\chi^{T}\sigma^{2}\chi]+(\text{复共轭})
$$

也由 (a) 部分给出的变换保持不变。通过解其场方程从完整拉格朗日量 $\mathcal{L}+\Delta\mathcal{L}$ 中消去 $F$，并证明费米子和玻色子场 $\phi$ 和 $\chi$ 被赋予相同的质量。



$$\begin{align}
\delta(\Delta \mathcal{L}) &= -im\varepsilon^{T}\sigma^{2}\chi F - im\phi \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi + \frac{im}{2} (\varepsilon^{T}F + \varepsilon ^{\dagger}(\sigma^{2})^{T}\partial_{\mu}\phi (\sigma^{\mu})^{T})\sigma^{2}\chi + \frac{im}{2}\chi^{T}\sigma^{2}( \varepsilon F + \sigma^{\mu}\partial_{\mu}\phi \sigma^{2}\varepsilon^{*} ) + cc. \\
&= -\frac{imF}{2}\varepsilon^{T}\sigma^{2}\chi  - im\phi \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi  - \frac{im}{2} \varepsilon ^{\dagger}\sigma^{2}(\partial_{\mu}\phi)(\sigma^{\mu})^{T}\sigma^{2}\chi + \frac{imF}{2}\chi^{T}\sigma^{2}\varepsilon + \frac{im}{2}\chi^{T}\sigma^{2}\sigma^{\mu}(\partial_{\mu}\phi) \sigma^{2}\varepsilon^{*} + cc. \\
\end{align} $$

先算一下含 $F$ 的项
$$\begin{align}
-\frac{imF}{2}\varepsilon^{T}\sigma^{2}\chi + \frac{imF}{2}\chi^{T}\sigma^{2}\varepsilon = -\frac{imF}{2}\varepsilon^{T}\sigma^{2}\chi + \frac{imF}{2}\varepsilon^{T}\sigma^{2}\chi = 0
\end{align} $$
然后含 $\partial_{\mu}\phi$ 的项，有这么几项
$$-im\phi\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi = -im\partial_{\mu}(\phi\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi) + im\partial_{\mu}\phi \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi$$
$$-\frac{im}{2}\varepsilon ^{\dagger}\sigma^{2}(\partial_{\mu}\phi)(\sigma^{\mu})^{T}\sigma^{2}\chi = -\frac{im}{2}\partial_{\mu}\phi \varepsilon ^{\dagger}\sigma^{2}(\sigma^{\mu})^{T}\sigma^{2}\chi = -\frac{im}{2}\partial_{\mu}\phi\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi$$
$$\frac{im}{2}\chi^{T}\sigma^{2}\sigma^{\mu}(\partial_{\mu}\phi) \sigma^{2}\varepsilon^{*} = \frac{im}{2}\partial_{\mu}\phi \chi^{T}\sigma^{2}\sigma^{\mu}\sigma^{2}\varepsilon^{*} = \frac{im}{2}\partial_{\mu}\phi (\varepsilon^{*})^{T}(\sigma^{2}\sigma^{\mu}\sigma^{2})^{T}(\chi^{T})^{T} = \frac{im}{2}\partial_{\mu}\phi \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi $$
于是
$$\begin{align}
\delta(\Delta \mathcal{L}) &= -im\partial_{\mu}(\phi\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi) + im\partial_{\mu}\phi \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi +im\partial_{\mu}(\phi^{*}\chi^{T}\bar{\sigma}^{\mu}\varepsilon) - im\partial_{\mu}\phi^{*}\chi ^{\dagger}\bar{\sigma}^{\mu}\varepsilon  \\
&= -im\partial_{\mu}(\phi\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi + cc.) + im\partial_{\mu}\phi\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi - im\partial_{\mu}\phi^{*}\chi ^{\dagger}\bar{\sigma}^{\mu}\varepsilon \\
&= -im\partial_{\mu}(\phi\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi + cc.)
\end{align}$$

所以完整的拉式量为
$$\mathcal{L}= \partial_{\mu}\phi^{*}\partial^{\mu}\phi + \chi ^{\dagger}i\bar{\sigma}^{\mu}\partial_{\mu}\chi + F^{*}F + \left( m\phi F + \frac{im}{2}\chi^{T}\sigma^{2}\chi + cc. \right) $$
取 $F=-m\phi^{*}$ 即可消去 $F$ 也
$$\mathcal{L} = \partial_{\mu}\phi^{*}\partial^{\mu}\phi + \chi ^{\dagger}i\bar{\sigma}^{\mu}\partial_{\mu}\chi -m^{2}\phi^{*}\phi + \frac{1}{2}\left( im\chi^{T}\sigma^{2}\chi + cc. \right) $$
可见对于 $\phi$ 和 $\chi$ 它们有相同的质量 $m$ 

---
### (c)
可以通过在拉格朗日量中添加三次和更高阶项来编写超对称非线性场方程。证明以下相当普遍的场论（包含场 $(\phi_{i},\chi_{i})$, $i=1,\ldots,n$）是超对称的：

$$
\begin{aligned}
\mathcal{L} =&\partial_{\mu}\phi^{*}_{i}\partial^{\mu}\phi_{i}+\chi^{\dagger}_{i}i\bar{\sigma}\cdot\partial\chi_{i}+F^{*}_{i}F_{i} \\
&+\left(F_{i}\frac{\partial W[\phi]}{\partial\phi_{i}}+\frac{i}{2}\frac{\partial^{2}W[\phi]}{\partial\phi_{i}\partial\phi_{j}}\chi^{T}_{i}\sigma^{2}\chi_{j}+\text{c.c.}\right),
\end{aligned}
$$

其中 $W[\phi]$ 是 $\phi_{i}$ 的任意函数，称为 **超势**。对于简单情况 $n=1$ 和 $W=g\phi^{3}/3$，写出 $\phi$ 和 $\chi$ 的场方程（消去 $F$ 后）。


$$\begin{align}
\delta\left[ F_{i}\frac{\partial W[\phi]}{\partial\phi_{i}}+\frac{i}{2}\frac{\partial^{2}W[\phi]}{\partial\phi_{i}\partial\phi_{j}}\chi^{T}_{i}\sigma^{2}\chi_{j}  \right] &= \delta F_{i} \frac{\partial W[\phi]}{\partial \phi_{i}} + F_{i}\frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}}\delta \phi_{j} + \frac{i}{2} \frac{\partial^{3}W[\phi]}{\partial \phi_{i}\partial \phi_{j}\partial \phi_{k}}\delta \phi_{k} \chi^{T}_{i}\sigma^{2}\chi_{j} + \frac{i}{2}\frac{\partial^{2}W[\phi]}{\partial\phi_{i}\partial\phi_{j}} [ \delta(\chi^{T}_{i})\sigma^{2}\chi_{j} + \chi^{T}_{i}\sigma^{2}\delta \chi_{j} ] + \text{c.c.}  \\
&= -i\epsilon^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi_{i} \frac{\partial W[\phi]}{\partial \phi_{i}} + F_{i}\frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}} (-i\epsilon^{T}\sigma^{2}\chi_{j}) +  \frac{i}{2} \frac{\partial^{3}W[\phi]}{\partial \phi_{i}\partial \phi_{j}\partial \phi_{k}} (-i\epsilon^{T}\sigma^{2}\chi_{k}) \chi^{T}_{i}\sigma^{2}\chi_{j} + \frac{i}{2}\frac{\partial^{2}W[\phi]}{\partial\phi_{i}\partial\phi_{j}}[ \epsilon^{T}\sigma^{2}\chi_{j} F_{i} + \varepsilon ^{\dagger}(\sigma^{2})^{T}(\sigma^{\mu})^{T}\partial_{\mu}\phi_{i} \sigma^{2}\chi_{j} + \chi^{T}_{i}\sigma^{2}(\epsilon F_{j} + \sigma^{\mu}\partial_{\mu}\phi_{j}\sigma^{2}\epsilon^{*}) ] \\
&= -i\epsilon^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi_{i} \frac{\partial W[\phi]}{\partial \phi_{i}} - iF_{i}\frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}} \epsilon^{T}\sigma^{2}\chi_{j} +  \frac{1}{2} \frac{\partial^{3}W[\phi]}{\partial \phi_{i}\partial \phi_{j}\partial \phi_{k}} \epsilon^{T}\sigma^{2}\chi_{k} \chi^{T}_{i}\sigma^{2}\chi_{j} + \frac{i}{2}\frac{\partial^{2}W[\phi]}{\partial\phi_{i}\partial\phi_{j}}[ F_{i}\epsilon^{T}\sigma^{2}\chi_{j}  + \partial_{\mu}\phi_{i} \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{j} + F_{j} \chi^{T}_{i}\sigma^{2}\epsilon + \partial_{\mu}\phi_{j}\chi^{T}_{i}(\bar{\sigma}^{\mu})^{T}\epsilon^{*}) ]
\end{align}$$
其中的 $\dfrac{\partial^{3}W[\phi]}{\partial \phi_{i}\partial \phi_{j}\partial \phi_{k}}$ 对于指标 $i,j,k$ 是轮换对称的，而 $\epsilon^{T}\sigma^{2}\chi_{k} \chi^{T}_{i}\sigma^{2}\chi_{j}$ 的轮换求和是零
$$\epsilon^{T}\sigma^{2}\chi_{k} \chi^{T}_{i}\sigma^{2}\chi_{j} + \epsilon^{T}\sigma^{2}\chi_{i} \chi^{T}_{j}\sigma^{2}\chi_{k} + \epsilon^{T}\sigma^{2}\chi_{j} \chi^{T}_{k}\sigma^{2}\chi_{i} = 0  $$
所以那坨玩意的变分就是
$$\begin{align}
&\quad -i\epsilon^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi_{i} \frac{\partial W[\phi]}{\partial \phi_{i}} - iF_{i}\frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}} \epsilon^{T}\sigma^{2}\chi_{j}  + \frac{i}{2}\frac{\partial^{2}W[\phi]}{\partial\phi_{i}\partial\phi_{j}}[ F_{i}\epsilon^{T}\sigma^{2}\chi_{j}  + \partial_{\mu}\phi_{i} \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{j} + F_{j} \chi^{T}_{i}\sigma^{2}\epsilon + \partial_{\mu}\phi_{j}\chi^{T}_{i}(\bar{\sigma}^{\mu})^{T}\epsilon^{*}) ] \\
&= -i\epsilon^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi_{i} \frac{\partial W[\phi]}{\partial \phi_{i}} + i \frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}} \left[  -\frac{1}{2} F_{i}\varepsilon^{T}\sigma^{2}\chi_{j} + \frac{1}{2} F_{j}\chi_{i}^{T}\sigma^{2}\varepsilon + \partial_{\mu}\phi_{i}\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{j} + \partial_{\mu}\phi_{j} \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{i} \right]
\end{align}$$
其中的第二部分对指标 $i,j$ 有轮换对称性，其中由于 $F$ 和 $\chi$ 可以交换所以轮换求和结果为零，剩余部分则刚好可以凑成一个全微分
$$\begin{align}
&\quad -i\epsilon^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi_{i} \frac{\partial W[\phi]}{\partial \phi_{i}} + i \frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}} \left[ \partial_{\mu}\phi_{i}\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{j} + \partial_{\mu}\phi_{j} \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{i} \right] \\
&= -i\epsilon^{\dagger}\bar{\sigma}^{\mu}\partial_{\mu}\chi_{i} \frac{\partial W[\phi]}{\partial \phi_{i}} + i \frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}} \partial_{\mu}[ \phi_{i}\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{j} ] \\
&= -i\partial_{\mu}\left(  \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{i}  \frac{\partial W[\phi]}{\partial \phi_{i}} \right) + i\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{i} \partial_{\mu}\left(  \frac{\partial W[\phi]}{\partial \phi_{i}}  \right) + i \frac{\partial^{2}W[\phi]}{\partial \phi_{i}\partial \phi_{j}} \partial_{\mu}[ \phi_{i}\varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{j} ] \\
&= -i\partial_{\mu}\left(  \varepsilon ^{\dagger}\bar{\sigma}^{\mu}\chi_{i}  \frac{\partial W[\phi]}{\partial \phi_{i}} \right)
\end{align}$$
所以在变换下拉式量只差一个全微分，所以拉式量是超对称不变的

当 $n=1$ , $W=\frac{g\phi^{3}}{3}$时 
$$\mathcal{L} = \partial_{\mu}\phi^{*}\partial^{\mu}\phi_{}+\chi^{\dagger}_{}i\bar{\sigma}\cdot\partial\chi+F^{*}F + (gF\phi^{2} +i\phi \chi^{T}\sigma^{2}\chi + \text{c.c.}) $$
取 $F=-g(\phi^{*})^{2}$ 则
$$\mathcal{L} = \partial_{\mu}\phi^{*}\partial^{\mu}\phi +\chi ^{\dagger}i\bar{\sigma}^{\mu}\partial_{\mu}\chi - g^{2}(\phi^{*}\phi)^{2} + ig( \phi \chi^{T}\sigma^{2}\chi - \phi^{*}\chi ^{\dagger}\sigma^{2}\chi^{*} ) $$


---

# 3.6 费尔兹变换

令 $u_{i}$，$i=1,\ldots,4$，为四个 4 分量狄拉克旋量。在正文中，我们证明了费尔兹重排公式 (3.78) 和 (3.79)。第一个公式在 4 分量记号中可以写为：

$$
\bar{u}_{1}\gamma^{\mu}\!\left(\frac{1\!+\!\gamma^{5}}{2}\right)\!u_{2}\bar{u}_{3}\gamma_{\mu}\!\left(\frac{1\!+\!\gamma^{5}}{2}\right)\!u_{4}=-\bar{u}_{1}\gamma^{\mu}\!\left(\frac{1\!+\!\gamma^{5}}{2}\right)\!u_{4}\bar{u}_{3}\gamma_{\mu}\!\left(\frac{1\!+\!\gamma^{5}}{2}\right)\!u_{2}.
$$

实际上，对于任何乘积：

$$
(\bar{u}_{1}\Gamma^{A}u_{2})(\bar{u}_{3}\Gamma^{B}u_{4}),
$$

都有类似的重排公式，其中 $\Gamma^{A},\Gamma^{B}$ 是第3.4节列出的狄拉克矩阵的16种组合中的任意一种。

### (a)
首先，将16个矩阵 $\Gamma^{A}$ 归一化到约定：

$$
\operatorname{tr}[\Gamma^{A}\Gamma^{B}]=4\delta^{AB}.
$$

这给出 $\Gamma^{A}=\{1,\gamma^{0},i\gamma^{j},\ldots\}$；写出此集合的所有16个元素。


原本是这16个
$$\left\{  \mathbf{1} , \gamma^{\mu} , \sigma^{\mu \nu}=\frac{i}{2}[\gamma^{\mu},\gamma^{\nu}] , \gamma^{5}\gamma^{\mu} , \gamma^{5}  \right\} $$
$\mathbf{1}$ 满足归于化约定，gamma数 在 weyl 表象下写 $\gamma^{\mu}=\begin{pmatrix}0 & {\sigma}^{\mu} \\ \bar{\sigma}^{\mu} & 0 \end{pmatrix}$ 则有 $\mathrm{Tr}[\gamma^{\mu}\gamma^{\mu}]=-2\mathrm{Tr}(\sigma^{\mu}\bar{\sigma}^{\mu})$ 当 $\mu=0$ 时 

$$\{ \mathbf{1} , \gamma^{0} , \gamma^{i} , i\sigma^{0i} , \sigma^{ij} , \gamma^{5} , i\gamma^{5}\gamma^{0} , \gamma^{5}\gamma^{i} \} $$


---
### (b)
将一般费尔兹恒等式写为方程：

$$
(\bar{u}_{1}\Gamma^{A}u_{2})(\bar{u}_{3}\Gamma^{B}u_{4})=\sum_{C,D}C^{AB}\!_{CD}(\bar{u}_{1}\Gamma^{C}u_{4})(\bar{u}_{3}\Gamma^{D}u_{2}),
$$

具有未知系数 $C^{AB}\!_{CD}$。利用16个 $\Gamma^{A}$ 矩阵的完备性，证明：

$$
C^{AB}\!_{CD}=\frac{1}{16}\,\operatorname{tr}[\Gamma^{C}\Gamma^{A}\Gamma^{D}\Gamma^{B}].
$$


对
$$(\bar{u}_{1}\Gamma^{A}u_{2})(\bar{u}_{3}\Gamma^{B}u_{4})=\sum_{C,D}C^{AB}\!_{CD}(\bar{u}_{1}\Gamma^{C}u_{4})(\bar{u}_{3}\Gamma^{D}u_{2}), $$
左乘 $(\bar{u}_{2}\Gamma^{F}u_{3})(\bar{u}_{3}\Gamma^{E}u_{4})$ 得到
$$(\bar{u}_{2}\Gamma^{F}u_{3})(\bar{u}_{3}\Gamma^{E}u_{4})(\bar{u}_{1}\Gamma^{A}u_{2})(\bar{u}_{3}\Gamma^{B}u_{4})=\sum_{C,D}C^{AB}\!_{CD}\mathrm{Tr}(\Gamma^{E}\Gamma^{C})\mathrm{Tr}(\Gamma^{F}\Gamma^{D})  $$
而
$$LHS = \bar{u}_{4}\Gamma^{E}\Gamma^{A}\Gamma^{F}\Gamma^{B} u_{4} = \mathrm{Tr}(\Gamma^{E}\Gamma^{A}\Gamma^{F}\Gamma^{B}) $$
$$RHS = \sum_{C,D}C^{AB}\!_{CD}4\delta_{EC}4\delta_{FD} = 16C^{AB}\!_{EF} $$
所以
$$C^{AB}\!_{CD}=\frac{1}{16}\,\operatorname{tr}[\Gamma^{C}\Gamma^{A}\Gamma^{D}\Gamma^{B}].$$


---
### (c)
显式推导出乘积 $(\bar{u}_{1}u_{2})(\bar{u}_{3}u_{4})$ 和 $(\bar{u}_{1}\gamma^{\mu}u_{2})(\bar{u}_{3}\gamma_{\mu}u_{4})$ 的费尔兹变换规律。


$$(\bar{u}_{1}u_{2})(\bar{u}_{3}u_{4}) = \sum_{C,D} \frac{\mathrm{Tr}(\Gamma^{C}\Gamma^{D})}{16} (\bar{u}_{1}\Gamma^{C}u_{4})(\bar{u}_{3}\Gamma^{D}u_{2}) = \sum_{C,D} \frac{4\delta^{{CD}}}{16} (\bar{u}_{1}\Gamma^{C}u_{4})(\bar{u}_{3}\Gamma^{D}u_{2}) = \sum_{A} \frac{1}{4} (\bar{u}_{1}\Gamma^{A}u_{4})(\bar{u}_{3}\Gamma^{A}u_{2}) = \dots$$

$$(\bar{u}_{1}\gamma^{\mu}u_{2})(\bar{u}_{3}\gamma_{\mu}u_{4}) = \sum_{C,D} \frac{\mathrm{Tr}(\Gamma^{C}\gamma^{\mu}\Gamma^{D}\gamma_{\mu})}{16} (\bar{u}_{1}\Gamma^{C}u_{4})(\bar{u}_{3}\Gamma^{D}u_{2}) = \sum_{A} \frac{\mathrm{Tr}(\Gamma^{A}\gamma^{\mu}\Gamma^{A}\gamma_{\mu})}{16} (\bar{u}_{1}\Gamma^{A}u_{4})(\bar{u}_{3}\Gamma^{A}u_{2}) $$


---

# 3.7 离散对称性

此问题涉及离散对称性 $P$（宇称）、$C$（电荷共轭）和 $T$（时间反演）。

### (a)
计算反对称张量费米子双线性 $\bar{\psi}\sigma^{\mu\nu}\psi$（其中 $\sigma^{\mu\nu}=\frac{i}{2}[\gamma^{\mu},\gamma^{\nu}]$）在 $P$、$C$ 和 $T$ 下的变换性质。这完成了本章末尾双线性变换性质表格。


P 就是 $\gamma^{0}$ 呀
$$P \bar{\psi}\sigma^{\mu \nu}\psi P = \frac{i}{2} \psi(t,-\mathbf{x})\gamma^{0}[\gamma^{\mu},\gamma^{\nu}]\gamma^{0}\psi(t,-\mathbf{x}) $$
其中
$$\gamma^{0}[\gamma^{0},\gamma^{i}]\gamma^{0} = -[\gamma^{0},\gamma^{i}] , \quad \gamma^{0}[\gamma^{i},\gamma^{j}]\gamma^{0} = [\gamma^{i},\gamma^{j}] $$
所以
$$P \bar{\psi}\sigma^{\mu \nu}\psi P = \left\{ \begin{align}
& -\bar{\psi}(t,-\mathbf{x})\sigma^{0i}\psi(t,-\mathbf{x}) \\
& \bar{\psi}(t,-\mathbf{x})\sigma^{ij}\psi(t,-\mathbf{x})
\end{align}  \right. $$

T 就事 $\gamma^{1}\gamma^{3}$ 
$$T\bar{\psi}\sigma^{\mu \nu}\psi T = -\frac{i}{2}\bar{\psi}(-t,\mathbf{x})(-\gamma^{1}\gamma^{3})[\gamma^{\mu},\gamma^{\nu}]^{*}(\gamma^{1}\gamma^{3})\psi(-t,\mathbf{x}) $$


C 就是 $-i\gamma^{0}\gamma^{2}$ 所以
$$C\bar{\psi}\sigma^{\mu \nu}\psi C = \frac{i}{2}(-i\gamma^{0}\gamma^{2}{\psi})^{T}\sigma^{\mu \nu}(-i\bar{\psi}\gamma^{0}\gamma^{3}) = \bar{\psi}\gamma^{0}\gamma^{2}(\sigma^{\mu \nu})^{T}\gamma^{0}\gamma^{2}\psi $$


---
### (b)
令 $\phi(x)$ 为我们在问题2.2中考虑的复值克莱因-戈登场。找出幺正算符 $P$、$C$ 和反幺正算符 $T$（均用它们对克莱因-戈登粒子和反粒子的湮灭算符 $a_{p}$ 和 $b_{p}$ 的作用定义），使得给出克莱因-戈登场的以下变换：

$$
\begin{aligned}
P\,\phi(t,\mathbf{x})\,P &= \phi(t,-\mathbf{x}); \\
T\,\phi(t,\mathbf{x})\,T &= \phi(-t,\mathbf{x}); \\
C\,\phi(t,\mathbf{x})\,C &= \phi^{*}(t,\mathbf{x}).
\end{aligned}
$$

找出流的分量：

$$
J^{\mu}=i(\phi^{*}\partial^{\mu}\phi-\partial^{\mu}\phi^{*}\phi)
$$

在 $P$、$C$ 和 $T$ 下的变换性质。

$$PJ^{\mu}(t,\mathbf{x})P = (-1)^{s(\mu)}J^{\mu}(t,-\mathbf{x}) $$
$$TJ^{\mu}(t,\mathbf{x})T = (-1)^{s(\mu)}J^{\mu}(-t,\mathbf{x}) $$
$$CJ^{\mu}(t,\mathbf{x})C = -J^{\mu}(t,\mathbf{x}) $$
---
### (c)
证明由 $\psi(x)$、$\phi(x)$ 及其共轭构造的任何厄米洛伦兹标量局域算符满足 $CPT=+1$。





---

# 3.8 束缚态

两个自旋 $1/2$ 粒子可以结合成总自旋为0或1的状态。这些状态的波函数在两个自旋交换下分别是奇和偶的。

## (a)
利用此信息计算具有 $S$、$P$ 或 $D$ 波函数的正负电子束缚态在 $P$ 和 $C$ 下的所有量子数。


这是一个多电子态，可以表达为
$$\ket{L,S} \sim \int \frac{\mathrm{d}^{3}\mathbf{k}}{(2\pi)^{3}\sqrt{ E_{\mathbf{k}} }} \Psi_{L}(\mathbf{k}) a^{\dagger}(\mathbf{k},s) b^{\dagger}(-\mathbf{k},s') \ket{0}   $$
其中 $\Psi(\mathbf{k})$ 是一个波包函数

于是宇称作用上去
$$P\ket{L,S} \sim \int \frac{\mathrm{d}^{3}\mathbf{k}}{(2\pi)^{3}\sqrt{ E_{\mathbf{k}} }} \Psi_{L}(-\mathbf{k}) \eta_{a}\eta_{b} a^{\dagger}(-\mathbf{k},s) b^{\dagger}(\mathbf{k},s') \ket{0} = (-1)^{L}\eta_{a}\eta_{b} \int \frac{\mathrm{d}^{3}\mathbf{k}}{(2\pi)^{3}\sqrt{ E_{\mathbf{k}} }} \Psi_{L}(\mathbf{k}) \eta_{a}\eta_{b} a^{\dagger}(\mathbf{k},s) b^{\dagger}(-\mathbf{k},s') \ket{0}   $$
由于 $\eta_{b}=-\eta_{a}^{*}$ 所以提供一个负号，总的来说变化了 $(-1)^{L+1}$ 可见对于宇称变换负号仅取决于总角动量量子数 $L$ 

电荷反转作用上去
$$C\ket{L,S} \sim \int \frac{\mathrm{d}^{3}\mathbf{k}}{(2\pi)^{3}\sqrt{ E_{\mathbf{k}} }} \Psi_{L}(\mathbf{k})  b^{\dagger}(\mathbf{k},s) a^{\dagger}(-\mathbf{k},s') \ket{0} = (-1)^{L+S} \int \frac{\mathrm{d}^{3}\mathbf{k}}{(2\pi)^{3}\sqrt{ E_{\mathbf{k}} }} \Psi_{L}(\mathbf{k})  a^{\dagger}(\mathbf{k},s) b^{\dagger}(-\mathbf{k},s') \ket{0} $$
可见对于电荷反转负号取决于 $L$ 和 $S$ 

| 电子态 | $^{1}S$ | $^{3}S$ | $^{1}P$ | $^{3}P$ | $^{1}D$ | $^{3}D$ |
| :-: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: |
|  P  |    -    |    -    |    +    |    +    |    -    |    -    |
|  C  |    +    |    -    |    -    |    +    |    +    |    -    |


---
## (b)
由于电子-光子耦合由哈密顿量给出：

$$
\Delta H=\int\!d^{3}x\ eA_{\mu}j^{\mu},
$$

其中 $j^{\mu}$ 是电流，如果矢量势的分量与 $j^{\mu}$ 的对应分量具有相同的 $P$ 和 $C$ 宇称，则电动力学对 $P$ 和 $C$ 不变。证明这暗示了以下令人惊讶的事实：电子偶素的基态（自旋0）可以衰变为2个光子，而自旋1的基态必须衰变为3个光子。找出高电子偶素态湮灭的选择定则，以及电子偶素能级之间单光子跃迁的选择定则。



