---
up:
  - "[[写题]]"
related:
date:
tags:
  - 量子场论
  - 习题
---

# 题5.1
>[!note] **库仑散射**。
>使用矩阵元的完整相对论表达式，重复问题4.4(c)部分的计算。你应该会发现，对于自旋平均后的截面，有
>$$
>\frac{d\sigma}{d\Omega} = \frac{\alpha^2}{4|\mathbf{p}|^2\beta^2\sin^4(\theta/2)} \left( 1 - \beta^2 \sin^2\frac{\theta}{2} \right),
>$$
>其中 $\mathbf{p}$ 是电子的3-动量，$\beta$ 是其速度。这就是相对论性电子库仑散射的*莫特公式*。现在用第二种方法推导它：计算$\mu$子静止系中的电子-$\mu$子散射截面，保留电子质量但令 $m_{\mu} \to \infty$。

散射过程为
$$e^{-}(p) + \mu^{-}(P) \to e^{-}(p') + \mu^{-}(P') $$
在 $\mu$ 子静止参考系中 $P=(m_{\mu},\mathbf{0}),p=(E,\mathbf{p})$ 相互作用是通过库仑（光子）交换：**t 通道**。
树图下的矩阵元：
$$i\mathcal{M} = (-ie)^{2} \bar{u}(p')\gamma^{\mu}u(p) \frac{-ig_{\mu \nu}}{q^{2}} \bar{u}(P')u(P) $$
其中 $q=p'-p=P-P'$ 是交换的四动量。平方并平均自旋：
$$\begin{align}
\overline{|\mathcal{M}|^{2}} &= \frac{1}{4} \sum_{\text{spin}} |\mathcal{M}|^{2}  \\
&= \frac{1}{4}\sum_{\text{spin}} \frac{e^{4}}{q^{4}} | \bar{u}(p')u(p)\gamma^{\mu}\bar{u}(P')\gamma_{\mu}u(P) |^{2} \\
&= \frac{e^{4}}{4q^{4}} \sum_{\text{spin}} (\bar{u}(p')\gamma^{\mu}u(p))(\bar{u}(p')\gamma^{\mu}u(p))^{*}(\bar{u}(P')\gamma_{\mu}u(P))(\bar{u}(P')\gamma_{\mu}u(P))^{*}
\end{align} $$
使用迹公式
$$\sum_{s} u(p,s)\bar{u}(p,s) = \not{ \! p } + m $$
所以
$$\begin{align}
&\quad \sum_{s,s'} (\bar{u}(p')\gamma^{\mu}u(p))(\bar{u}(p')\gamma^{\nu}u(p))^{*} \\
&= \sum_{s,s'} \bar{u}(p',s')\gamma^{\mu}u(p,s)\bar{u}(p,s)\gamma^{\nu}u(p',s') \\
&= \sum_{s,s'} \bar{u}_{a}(p',s')(\gamma^{\mu})_{ab}u_{b}(p,s)\bar{u}_{c}(p,s)(\gamma^{\nu})_{cd}u_{d}(p',s') \\
&=  (\not{ \! p' }+m)_{da}(\gamma^{\nu})_{cd}(\not{ \! p }+m)_{bd}(\gamma^{\mu})_{ab} \\
&= \text{Tr}\big[(\not{\!p'}+m)\gamma^{\mu}(\not{\!p}+m)\gamma^{\nu} \big] \\
&= \text{Tr}\big[\not{ \! p' }\gamma^{\mu}\not{ \! p }\gamma^{\nu} + m\gamma^{\mu}\not{ \! p }\gamma^{\nu} + m\not{ \! p' }\gamma^{\mu}\gamma^{\nu} + m^{2}\gamma^{\mu}\gamma^{\nu} \big] \\
&= 4(p'^{\mu}p^{\nu}+p'^{\nu}p^{\mu}-g^{\mu \nu}p'\cdot p) + 0 + 0 + 4m^{2}g^{\mu \nu}  \\
&:= L^{\mu \nu}
\end{align} $$
类似的 $\mu$ 子部分的求和为
$$4(P'_{\mu}P_{\nu} + P'_{\nu}P_{\mu}-g_{\mu \nu}P'\cdot P+m^{2}g_{\mu \nu}) := M_{\mu \nu} $$
在 $\mu$ 子静止系 $P=(m_{\mu},\mathbf{0})$ 由于取 $m_{\mu}\to \infty$ 所以 $P'\approx P$ ：
$$M_{00} = 4m_{\mu}^{2} ,\quad M_{0i} = M_{i{0}} = M_{ij} = 0 $$
$$L^{00} = 4(EE' + \mathbf{p}\cdot \mathbf{p}' + m^{2}) $$
所以
$$\overline{|\mathcal{M}|^{2}} = \frac{16e^{4}}{q^{4}}(EE' + \mathbf{p}\cdot \mathbf{p}' + m^{2}) m_{\mu}^{2} $$
所以
$$\frac{\mathrm{d\sigma}}{\mathrm{d\Omega}} = \frac{\alpha^{2}}{4|\mathbf{p}|^{2}\beta^{2}\sin^{4}\left( \dfrac{\theta}{2} \right)} \left(  1 - \beta^{2} \sin^2 \frac{\theta}{2}  \right) $$
其中 $\beta = \dfrac{|\mathbf{p}|}{E}$

---

# 题5.2
>[!note] **Bhabha散射**。
>计算Bhabha散射 $e^+e^- \to e^+e^-$ 的微分截面 $d\sigma/d\cos\theta$。你可以在 $E_{cm} \gg m_e$ 的极限下工作，此时忽略电子质量是允许的。有两个费曼图；在取平方之前，必须在不变矩阵元中将它们相加。确保这两个图之间有正确的相对符号。中间步骤很复杂，但最终结果相当简单。特别是，你可能会发现引入Mandelstam变量 $s, t, u$ 是有用的。注意，如果我们忽略电子质量，则有 $s + t + u = 0$。你应该能够将微分截面转化为以下形式：
>$$
>\frac{d\sigma}{d\cos\theta} = \frac{\pi\alpha^2}{s} \left[ u^2 \left( \frac{1}{s} + \frac{1}{t} \right)^2 + \left( \frac{t}{s} \right)^2 + \left( \frac{s}{t} \right)^2 \right].
>$$
>用 $\cos\theta$ 重写这个公式并绘图。图表的什么特征导致微分截面在 $\theta \to 0$ 时发散？

Bhabha 散射有两条树图：
![[image.png|344x148]]看得出一个是S通道，一个是T通道，很容易读出来它们的散射振幅
$$\begin{gather}
\mathcal{M}_{s} = (-ie)^{2} \bar{v}(k_{2})\gamma^{\mu}u(k_{1}) \frac{-ig_{\mu \nu}}{s} \bar{u}(p_{1})\gamma^{\nu}v(p_{2}) \\
\mathcal{M}_{t} = (-ie)^{2} \bar{u}(p_{1})\gamma^{\mu}u(k_{1}) \frac{-ig_{\mu \nu}}{t} \bar{v}(k_{2})\gamma^{\nu}v(p_{2})
\end{gather} $$
其中使用了 Mandelstam 变量：
$$s=(k_{1}+k_{2})^{2},\quad t=(p_{1}-k_{1})^{2},\quad u=(p_{2}-k_{1})^{2} $$
平方并平均自旋：
$$\begin{align}
\overline{|\mathcal{M}|^{2}} &= \frac{1}{4} \sum_{\text{spin}} |\mathcal{M}_{s} - \mathcal{M}_{t}|^{2}  \\
&= \frac{e^{4}}{4s^{4}} \sum\left| \bar{v}(k_{2})\gamma^{\mu}u(k_{1})\bar{u}(p_{1})\gamma_{\mu}v(p_{2}) \right|^{2} \\
&\quad + \frac{e^{4}}{4t^{4}}\sum| \bar{u}(p_{1})\gamma^{\mu}u(k_{1})\bar{v}(k_{2})\gamma_{\mu}v(p_{2}) | \\
&\quad - \frac{e^{4}}{4st} \sum| \bar{v}(p_{2})\gamma_{\mu}u(p_{1})\bar{u}(k_{1})\gamma^{\mu}v(k_{2})\bar{u}(p_{1})\gamma_{\nu}u(k_{1})\bar{v}(k_{2})\gamma^{\nu}v(p_{2}) + cc. | \\
&= \frac{e^{4}}{4s ^{4}} \text{tr}[ \not{ \! k_{1} }\gamma^{\mu}\not{ \! k_{2} }\gamma^{\nu} ]\text{tr}[\not{ \! p_{2} }\gamma_{\mu}\not{ \! p_{1} }\gamma_{\nu}] + \frac{e^{4}}{4t^{4}}\text{tr}[\not{ \! p_{1} }\gamma^{\mu}\not{ \! k_{1} \gamma^{\nu}}]\text{tr}[\not{ \! p_{2} }\gamma_{\mu}\not{ \! k_{2} \gamma_{\nu}}] \\
&\quad - \frac{e^{4}}{4st} \{ \text{tr}[\not{ \! k_{1} }\gamma^{\nu}\not{ \! k_{2} }\gamma^{\mu}\not{ \! p_{2} }\gamma_{_{\nu}}\not{ \! p_{1} }\gamma_{\mu}] + cc. \} \\
&= \frac{2e^{4}(u^{2}+t^{2})}{s^2} + \frac{2e^{4}(u^{2}+s^{2})}{t^2} - \frac{4e^{4}u^{2}}{st} \\
&= 2e^{4}\left[  \frac{t^{2}}{s^2} + \frac{s^2}{t^{2}} + u^{2}\left( \frac{1}{s} + \frac{1}{t} \right)^{2}  \right]
\end{align}$$
对 2 → 2 无质量散射：
$$\frac{d\sigma}{d\Omega} = \frac{1}{64 \pi^2 s} \overline{|\mathcal{M}|^2}$$




---

# 题5.3
>[!note] 
>问题3.3中引入的旋量积形式主义为计算涉及无质量粒子的树图提供了一种有效的方法。回顾在问题3.3中，我们如下定义旋量积：设 $u_{L0}, u_{R0}$ 为某个固定类光动量 $k_0$ 下的左手和右手旋量。它们满足
>$$
>u_{L0} \bar{u}_{L0} = \left( \frac{1-\gamma^5}{2} \right) \psi_0, \quad u_{R0} \bar{u}_{R0} = \left( \frac{1+\gamma^5}{2} \right) \psi_0.
>$$
>（这些关系只是更标准的公式 $\sum u_0 \bar{u}_0 = \psi_0$ 在确定螺旋性上的投影。）然后为任何其他类光动量 $p$ 定义旋量：
>$$
>u_L(p) = \frac{1}{\sqrt{2p \cdot k_0}} \psi u_{R0}, \quad u_R(p) = \frac{1}{\sqrt{2p \cdot k_0}} \bar{\psi} u_{L0}.
>$$
>我们证明了这些旋量满足 $\psi u(p) = 0$；由于没有 $m$ 存在，它们可以用作费米子或反费米子的旋量。我们定义了
>$$
>s(p_1, p_2) = \bar{u}_R(p_1) u_L(p_2), \quad t(p_1, p_2) = \bar{u}_L(p_1) u_R(p_2),
>$$
>并且在一个特殊参考系中，我们证明了性质
>$$
>t(p_1, p_2) = (s(p_2, p_1))^*, \quad s(p_1, p_2) = -s(p_2, p_1), \quad |s(p_1, p_2)|^2 = 2p_1 \cdot p_2.
>$$
>现在让我们应用这些结果。

>[!question] (a)
>作为热身，通过使用(1)将 $|s(p_1, p_2)|^2$ 重写为狄拉克矩阵的迹，然后应用迹计算，给出方程(3)中最后一个关系的另一个证明。

$$\begin{align}
|s(p_{1},p_{2})|^{2} &= (\bar{u}_{R}(p_{1})u_{L}(p_{2}))(\bar{u}_{R}(p_{1})u_{L}(p_{2}))^{*} \\
&= (\bar{u}_{R}(p_{1})u_{L}(p_{2}))(\bar{u}_{L}(p_{2})u_{R}(p_{1})) \\
&= \bar{u}_{R}(p_{1})( u_{L}(p_{2})\bar{u}_{L}(p_{2}) )u_{R}(p_{1}) \\
&= \bar{u}_{R}(p_{1}) P_{L}\not{ \! p_{2} } u_{R}(p_{1}) \\
&= \mathrm{Tr}[ P_{L}\not{ \! p_{2} } \bar{u}(p_{1})u_{R}(p_{1}) ] \\
&= \mathrm{Tr}[ P_{L}\not{ \! p_{2} } P_{R}\not{ \! p_{1} } ] \\
&= \frac{1}{4} \mathrm{Tr}[ (1-\gamma^{5})\not{ \! p_{2} }(1+\gamma^{5})\not{ \! p_{1} } ] \\
&= \frac{1}{2}\mathrm{Tr}[ \not{ \! p_{1} } \not{ \! p_{2} } ] \\
&= \frac{1}{2}\cdot{4}p_{1}\cdot p{2}= 2p_{1}\cdot p_{2}
\end{align} $$

>[!question] (b)
>证明，对于任何狄拉克矩阵串，
>$$
>\text{tr}[\gamma^\mu \gamma^\nu \gamma^\rho \cdots] = \text{tr}[\cdots \gamma^\rho \gamma^\nu \gamma^\mu]
>$$
>其中 $\mu, \nu, \rho, \ldots = 0, 1, 2, 3,$ 或 $5$。使用这个恒等式证明
>$$
>\bar{u}_L(p_1) \gamma^\mu u_L(p_2) = \bar{u}_R(p_2) \gamma^\mu u_R(p_1).
>$$

$$\mathrm{Tr}[\gamma^{\mu}\gamma^{\nu}\gamma^{\rho}\dots] = \mathrm{Tr}[(\gamma^{\mu}\gamma^{\nu}\gamma^{\rho}\dots)^{T}] = \mathrm{Tr}[\dots \gamma^{\rho}\gamma^{\nu}\gamma^{\mu}] $$

$$\begin{align}
\bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2}) &= \mathrm{Tr}[ \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2}) ] \\
&= \mathrm{Tr}[u(p_{1}) P_{R}\gamma^{\mu} P_{L} u(p_{2}) ] \\
&= \mathrm{Tr}[u(p_{2})P_{L}\gamma^{\mu}P_{R}u(p_{1})] \\
&= \mathrm{Tr}[\bar{u}_{R}(p_{2})\gamma^{\mu}u_{R}(p_{1})] \\
&= \bar{u}_{R}(p_{2})\gamma^{\mu}u_{R}(p_{1})
\end{align} $$


>[!question] (c)
>证明Fierz恒等式
>$$
>\bar{u}_L(p_1) \gamma^\mu u_L(p_2) [\gamma_\mu]_{\alpha b} = 2[u_L(p_2) \bar{u}_L(p_1) + u_R(p_1) \bar{u}_R(p_2)]_{\alpha b},
>$$
>其中 $a, b = 1, 2, 3, 4$ 是狄拉克指标。这可以通过证明以下陈述来完成：该方程的右边是一个狄拉克矩阵；因此，它可以写成3.4节讨论的16个 $\Gamma$ 矩阵的线性组合。它满足
>$$
>\gamma^5[M] = -[M]\gamma^5,
>$$
>因此，它必须具有形式
>$$
>[M] = \left( \frac{1-\gamma^5}{2} \right)\gamma_\mu V^\mu + \left( \frac{1+\gamma^5}{2} \right)\gamma_\mu W^\mu
>$$
>其中 $V^\mu$ 和 $W^\mu$ 是4-矢量。这些4-矢量可以通过迹技术计算；例如，
>$$
>V^\nu = \frac{1}{2} \operatorname{tr}[\gamma^\nu \left( \frac{1-\gamma^5}{2} \right) M].
>$$

令
$$[M]_{ab} = \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2})[\gamma_{\mu}]_{ab} $$
则
$$\gamma^{5}[M] = \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2}) [\gamma^{5}\gamma_{\mu}]_{ab} = \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2})[-\gamma_{\mu}\gamma^{5}]_{ab} = -[M]\gamma^{5} $$

考虑到狄拉克基只有16个，满足 $\gamma^{5}[M]=-[M]\gamma^{5}$ 的元素必然是奇 γ 结构，即
$$P_{L}\gamma^{\mu},\quad P_{R}\gamma^{\mu} $$
为了指标，$\gamma^{\mu}$ 必然需要和分量非克里福德数的矢量内积，即
$$[M] = P_{L}\gamma^{\mu}V_{\mu} + P_{R}\gamma^{\nu}W_{\nu} $$

下面使用迹技术来计算这两个矢量
$$\begin{align}
V^{\mu} &= \frac{1}{2}\mathrm{Tr}[\gamma^{\mu}P_{L}M] \\
&= \frac{1}{2} \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2}) \mathrm{Tr}[ \gamma^{\mu}P_{L}\gamma_{\nu} ] \\
&= \frac{1}{4} \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2}) \{  \mathrm{Tr}[\gamma^{\mu}\gamma_{\nu}] - \mathrm{Tr}[\gamma^{\mu}\gamma^{5}\gamma_{\nu}]  \} \\
&= \frac{1}{4} \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2}) (4\delta^{\mu}_{\ \nu} + 0) \\
&= \bar{u}_{L}(p_{1})\gamma^{\mu}u_{L}(p_{2})
\end{align} $$
同理
$$\begin{align}
W^{\mu} &= \frac{1}{2} \mathrm{Tr}[\gamma^{\mu}P_{R}M] \\
&= \frac{1}{2} \bar{u}_R(p_2) \gamma^\mu u_R(p_1) \mathrm{Tr}[\gamma^{\mu}P_{R}\gamma_{\nu}] \\
&= \frac{1}{4} \bar{u}_R(p_2) \gamma^\mu u_R(p_1) \{ \mathrm{Tr}[\gamma^{\mu}\gamma_{\nu}] + \mathrm{Tr}[\gamma^{\mu}\gamma^{5}\gamma_{\nu}] \} \\
&= \frac{1}{4} \bar{u}_R(p_2) \gamma^\mu u_R(p_1) (4\delta^{\mu}_{\ \nu} + 0) \\
&= \bar{u}_R(p_2) \gamma^\mu u_R(p_1) 
\end{align} $$

下面去证明 Firez 恒等式，把这两个矢量代回 $M$ ：
$$\begin{align}
[M] &= P_{L}\gamma^{\mu}\bar{u}_{L}(p_{1})\gamma_{\mu}u_{L}(p_{2}) + P_{R}\gamma^{\mu}\bar{u}_R(p_2) \gamma^\mu u_R(p_1) \\
&=2 [\bar{u}_{L}(p_{1})u_{L}(p_{2}) + \bar{u}_{R}(p_{2})u_{R}(p_{1})]
\end{align} $$
所以
$$\bar{u}_L(p_1) \gamma^\mu u_L(p_2) [\gamma_\mu]_{\alpha b} = 2[u_L(p_2) \bar{u}_L(p_1) + u_R(p_1) \bar{u}_R(p_2)]_{\alpha b} $$



>[!question] (d)
>考虑过程 $e^+e^- \to \mu^+\mu^-$，到 $\alpha$ 的领头阶，忽略电子和$\mu$子的质量。首先考虑电子和末态$\mu$子都是右手的，而正电子和末态反$\mu$子都是左手的情况。（对反$\mu$子使用旋量 $v_R$，对正电子使用 $\bar{u}_R$。）应用Fierz恒等式证明振幅可以直接用旋量积计算。将振幅平方，并重现方程(5.22)中给出的
>$$
>\frac{d\sigma}{d\cos\theta} (e_R^- e_L^+ \to \mu_R^- \mu_L^+)
>$$
>的结果。计算此过程的其他螺旋性截面，并证明它们也重现了5.2节中找到的结果。

树图过程是
$$e_{R}^{-}(p_{1}) + e_{L}^{+}(p_{2}) \to \gamma^{*}(p_{1}+p_{2}) \to \mu_{R}^{-}(k_{1}) + \mu_{L}^{+}(k_{2}) $$
由费曼规则，散射振幅是
$$i\mathcal{M} = (-ie)^{2} \bar{u}_{R}(p_{2})\gamma^{\mu}u_{R}(p_{1}) \frac{-ig_{\mu \nu}}{q} \bar{u}_{R}(k_{1})\gamma^{\nu}u_{R}(k_{2}) $$
$$\mathcal{M} = \frac{e^{2}}{s} \bar{u}_{R}(p_{2})\gamma^{\mu}u_{R}(p_{1}) \bar{u}_{R}(k_{1})\gamma_{\mu}u_{R}(k_{2}) $$
使用 Firez 恒等式
$$\begin{gather}
\bar{u}_{R}(p_{2})\gamma^{\mu}u_{R}(p_{1})\bar{u}_{R}(k_{1})\gamma_{\mu}u_{R}(k_{2}) = 2s(p_{1},k_{1})s(p_{2},k_{2})
\end{gather} $$

于是
$$\begin{align}
|\mathcal{M}|^{2} &= \frac{4e^{4}}{s^{2}} |s(p_{1},k_{1})|^{2} |s(p_{2},k_{2})|^{2}  \\
&= \frac{16e^{4}}{s^{2}} (p_{1}\cdot k_{1})(p_{2}\cdot k_{2})
\end{align} $$

在质心系
$$\begin{gather}
p_{1} = (E,p\hat{z}), & p_{2} = (E,-p\hat{z}) \\
k_{1}=(E,\mathbf{p}), & k_{2}=(E,-\mathbf{p})
\end{gather} $$
$$p_{1}\cdot k_{1} = p_{2}\cdot k_{2} = E^{2}(1+\cos \theta)  $$
$$|\mathcal{M}|^{2} = \frac{16e^{4}}{s^2} E^{4}(1+coa\theta)^{2} =e^{4}(1+\cos \theta)^{2} $$

代入微分散射截面公式 $\dfrac{d\sigma}{d\Omega}=\dfrac{1}{8s}|\mathcal{M}|^{2}$ 得到
$$\frac{d\sigma}{d\cos \theta} = \frac{1}{32\pi s}|\mathcal{M|^{2}} $$


>[!question] (e)
>使用旋量积形式主义，逐个螺旋性态地计算无质量电子Bhabha散射的微分截面。对初始螺旋性取平均，对末态螺旋性求和，应重现问题5.2的结果。在此过程中，你应该能看到这个结果是如何作为确定螺旋性贡献的和产生的。

---

# 题5.4
>[!note] **电子偶素寿命**。

>[!question] (a)
>在极端非相对论极限下（即仅保留与电子和正电子3-动量的零次幂成正比的项），计算 $e^+e^-$ 湮灭成2个光子的振幅 $M$。使用这个结果，连同我们关于费米子-反费米子束缚态的公式，计算电子偶素1S态湮灭成2个光子的速率。你应该发现电子偶素的自旋1态不会湮灭成2个光子，这证实了问题3.8的对称性论证。对于电子偶素的自旋0态，你应该得到一个与1S波函数在原点的平方成正比的结果。代入非相对论量子力学中该波函数的值，你应该发现
>$$
>\frac{1}{\tau} = \Gamma = \frac{\alpha^5 m_e}{2} \approx 8.03 \times 10^9 \, \text{秒}^{-1}.
>$$
>最近的测量给出 $\Gamma = 7.994 \pm .011 \, \text{纳秒}^{-1}$；0.5%的差异由辐射修正解释。

>[!question] (b)
>计算更高轨道角动量（$l$）电子偶素态的衰变速率有些困难；在这个问题的其余部分，我们将考虑 $l = 1$ 的情况。首先，计算出 $e^+ e^- \to 2\gamma$ 振幅中与3-动量一次幂成正比的项。（为简单起见，在质心系中工作。）由于
>$$
>\int \frac{d^3p}{(2\pi)^3} p^i \psi(\mathbf{p}) = i \frac{\partial}{\partial x^i} \psi(\mathbf{x}) \bigg|_{\mathbf{x}=0},
>$$
>振幅的这一部分与 $P$ 波束缚态有重叠。证明 $S = 1$ 的态可以衰变成2个光子，但 $S = 0$ 的态不行。这又是 $C$ 宇称的结果。

>[!question] (c)
>为了计算这些 $P$ 波态的衰变速率，我们需要适当归一化的态矢量。将三个 $P$ 态波函数表示为
>$$
>\psi_i = x^i f(|\mathbf{x}|), \quad \text{归一化到} \quad \int d^3x \psi_i^*(x)\psi_j(x) = \delta_{ij},
>$$
>它们的傅里叶变换为 $\psi_i(\mathbf{p})$。证明
>$$
>|B(\mathbf{k})\rangle = \sqrt{2M} \int \frac{d^3p}{(2\pi)^3} \psi_i(\mathbf{p}) a_{\mathbf{p}+\mathbf{k}/2}^\dagger \Sigma^i b_{-\mathbf{p}+\mathbf{k}/2}^\dagger |0\rangle
>$$
>是一个正确归一化的束缚态矢量，如果 $\Sigma^i$ 表示一组三个 $2 \times 2$ 矩阵，归一化为
>$$
>\sum_i \text{tr}(\Sigma^i \Sigma^{i\dagger}) = 1.
>$$
>要构建 $S = 1$ 态，我们应该让每个 $\Sigma^i$ 包含一个泡利$\sigma$矩阵。通常，自旋-轨道耦合会根据总角动量 $J$ 分裂 $S = 1$，$L = 1$ 态的多重态。确定 $J$ 的态由下式给出：
>$$
>J = 0: \quad \Sigma^i = \frac{1}{\sqrt{6}} \sigma^i,
>$$
>$$
>J = 1: \quad \Sigma^i = \frac{1}{2} \epsilon^{ijk} n^j \sigma^k,
>$$
>$$
>J = 2: \quad \Sigma^i = \frac{1}{\sqrt{3}} h^{ij} \sigma^j,
>$$
>其中 $\mathbf{n}$ 是满足 $|\mathbf{n}|^2 = 1$ 的极化矢量，$h^{ij}$ 是一个无迹张量，其典型值可能是 $h^{12} = 1$ 而所有其他分量为零。

>[!question] (d)
>使用(b)部分推导的 $e^+ e^- \to 2\gamma$ 振幅的展开形式，以及(c)部分找到的 $S = 1$，$L = 1$，确定 $J$ 的电子偶素态的具体形式，计算每个 $J$ 的态衰变成两个光子的衰变速率。

---

# 题5.5
>[!note] **大质量矢量玻色子的物理**。
>在QED中加入一个质量为 $M$ 的大质量光子场 $B_\mu$，它通过以下方式与电子耦合：
>$$
>\Delta \mathcal{L} = g \bar{\psi} \gamma^\mu \psi B_\mu.
>$$
>处于初态或末态的大质量光子具有三种可能的物理极化，对应于玻色子静止系中的三个类空间单位矢量。这些可以不变地用玻色子的4-动量 $k^\mu$ 来表征，即满足以下条件的三个矢量 $\epsilon_\mu^{(i)}$：
>$$
>\epsilon^{(i)} \cdot \epsilon^{(j)} = -\delta^{ij}, \quad k \cdot \epsilon^{(i)} = 0.
>$$
>四个矢量 $(k_\mu / M, \epsilon_\mu^{(i)})$ 构成一个完备的正交归一基。因为 $B_\mu$ 耦合到守恒流 $\bar{\psi} \gamma^\mu \psi$，Ward恒等式意味着 $k_\mu$ 点乘 $B$ 产生振幅给出零；因此我们可以替换：
>$$
>\sum_i \epsilon_\mu^{(i)} \epsilon_{\nu}^{(i)*} \to -g_{\mu\nu}.
>$$
>这给出了光子极化矢量的费曼技巧对大质量玻色子的推广，并简化了 $B$ 产生截面的计算。（警告：这个技巧对“非阿贝尔规范场”不（如此简单）起作用。）让我们使用忽略电子质量的近似来做其中的一些计算。

>[!question] (a)
>计算过程 $e^+e^- \to B$ 的截面。计算 $B$ 的寿命，假设它只衰变到电子。验证关系式
>$$
>\sigma(e^+e^- \to B) = \frac{12\pi^2}{M} \Gamma(B \to e^+e^-)\delta(M^2 - s)
>$$
>如5.3节所讨论。

$$\mathcal{L}_{\text{int}} = g\bar{\psi}\gamma^{\mu}\psi B_{\mu} $$
费曼图概括为
$$e^{-}(p_{1}) + e^{+}(p_{2}) \to B(p_{1}+p_{2}) $$
$$i\mathcal{M} = g\bar{v}(p_{2})\gamma^{\mu}u(p_{1})\varepsilon_{\mu}(p_{1}+p_{2}) $$

对入射电子自旋和出射“光子”极化求和得到散射振幅为
$$\begin{align}
\sum_{\text{spin,pol}} |\mathcal{M}|^{2} &= g^{2} \sum_{\text{pol}} \varepsilon_{\mu}\varepsilon_{\nu}^{*}\mathrm{Tr}[\not{ \! p_{1} }\gamma^{\mu}\not{ \! p_{2} }\gamma^{\nu}] \\
&= g^{2}\cdot(-g_{\mu \nu}) \mathrm{Tr}[\not{ \! p_{1} }\gamma^{\mu}\not{ \! p_{2} }\gamma^{\nu}] \\
&= g^{2}\cdot(8p_{1}\cdot p_{2}) \\
&= 8g^{2}p_{1}\cdot p_{2}
\end{align} $$
在 $B$ 的静止系中
$$p_{1}=(E,\mathbf{p}),\quad p_{2}=(E,-\mathbf{p}) $$
$$p_{1}\cdot p_{2} = E^{2} + p^{2} = \frac{M^{2}}{2} $$
$$\sum|\mathcal{M}| = 4g^{2}M^{2} $$

对于二体衰变，相宽度为
$$\Gamma = \frac{1}{2M} \int \mathrm{d\Phi_{2}} \sum_{\text{spin,pol}}|\mathcal{M}|^{2} $$
其中由于末态粒子无质量所以 $d\Phi_{2} = \frac{1}{8\pi}$ 所以
$$\Gamma = \frac{g^{2}M}{12\pi} $$


>[!question] (b)
>在质心系中，计算过程 $e^+e^- \to \gamma + B$ 的微分截面。（这个计算几乎可以不加修改地应用于实际过程 $e^+e^- \to \gamma + Z^0$；这允许人们测量 $Z^0$ 衰变到未观测末态的数量，而这个数量又与中微子种类数目成正比。）

现在还要考虑QED了，所以相互作用项是
$$\mathcal{L}_{\text{int}} = e\bar{\psi}\gamma^{\mu}\psi A_{\mu} + g\bar{\psi}\gamma^{\nu}\psi B_{\nu} $$
过程有两个
$$e^{-}(k_{1}) \to \gamma(p_{1},\varepsilon_{\mu}) + e^{-}(k_{1}-p_{1}) \to B(p_{2},\varepsilon_{\nu}) + e^{+}(k_{2}) $$
$$e^{-}(k_{1}) \to B(p_{2},\varepsilon_{\nu}) + e^{+}(k_{1}-p_{2}) \to \gamma(p_{1},\varepsilon_{\mu}) + e^{+}(k_{2}) $$

所以散射振幅是
$$\begin{align}
i\mathcal{M} &= \bar{v}(k_{1})(ig\gamma^{\mu}\varepsilon^{*}_{\mu}) \frac{i(\not{ \! k_{1}}-\not{ \! p_{1} })}{(k_{1}-p_{1})^{2}} (ie\gamma^{\nu}e^{*}_{\nu})u(k_{2}) \\
&\quad + \bar{v}(k_{1})(ie\gamma^{\nu}e^{*}_{\nu}) \frac{i(\not{ \! k_{1} }-\not{ \! p_{2} })}{(k_{1}-p_{2})^{2}}(ig\gamma^{\mu}\varepsilon^{*}_{\mu})u(k_{2}) \\
&= eg\bar{v}(k_{1})\left[  \gamma^{\mu} \frac{i(\not{ \! k_{1} }-\not{ \! p_{1} })}{(k_{1}-p_{1})^{2}} \gamma^{\nu} + \gamma^{\nu} \frac{i(\not{ \! k_{1} }-\not{ \! p_{2} })}{(k_{1}-p_{2})^{2}} \gamma^{\mu} \right] u(k_{2}) \varepsilon^{*}_{\mu}e^{*}_{\nu} \\
&= eg \varepsilon^{*}_{\mu}e^{*}_{\nu} \bar{v}(k_{1})\Gamma^{\mu \nu}u(k_{2})
\end{align} $$
对自旋极化求和，首先对于光子和 B 玻色子对极化态求和有
$$\begin{gather}
\sum_{\lambda} \varepsilon^{*}_{\mu}\varepsilon_{\rho} = -g_{\mu \rho} \\
\sum_{\lambda} e^{*}_{\nu} e_{\sigma} = -g_{\nu \sigma}
\end{gather} $$
对于电子自旋求和有
$$\begin{gather}
\sum_{\sigma} u(k_{2})\bar{u}(k_{2}) = \not{ \! k_{2} } \\
\sum_{\sigma} u(k_{1})\bar{u}(k_{1}) = \not{ \! k_{1} }
\end{gather} $$
于是
$$\begin{align}
\frac{1}{4}\sum_{\text{spin}} |i\mathcal{M}|^{2} &= \frac{e^{2}g^{2}}{4} (-g_{\mu \rho})(-g_{\nu \sigma}) [\bar{v}(k_{1})\Gamma^{\mu \nu}u(k_{2})][\bar{v}(k_{1})\Gamma^{\rho \sigma}u(k_{2})]^{\dagger} \\
&= \frac{e^{2}g^{2}}{4} (-g_{\mu \rho})(-g_{\nu \sigma}) \mathrm{Tr}[\not{ \! k_{1} }\Gamma^{\mu \nu}\not{ \! k_{2} }\bar{\Gamma}^{\rho \sigma}] \\
&= \frac{e^{2}g^{2}}{4} \mathrm{Tr}[ \not{ \! k_{1} } \Gamma^{\mu \nu} \not{ \! k_{2} } \gamma^{0} (\Gamma_{\mu \nu})^{\dagger} \gamma^{0} ] \\
\end{align} $$
其中
$$\begin{align}
&\quad \mathrm{Tr}\left[  \not{\! k_{1}} \gamma^{\mu}\frac{i(\not{\! k_{1}}-\not{\! p_{1}})}{(k_{1}-p_{1})^{2}}\gamma^{\nu} \not{\! k_{2}} \gamma_{\nu} \frac{i(\not{\! k_{1}}-\not{\! p_{1}})}{(k_{1}-p_{1})^{2}} \gamma_{\mu}  \right] \\
&= \frac{1}{t^{2}} \mathrm{Tr}[ \not{\! k_{1}} \gamma^{\mu}(\not{\! k_{1}}-\not{\! p_{1}})\gamma^{\nu}\not{\! k_{2}} \gamma_{\nu} (\not{\! k_{1}}-\not{\! p_{1}}) \gamma_{\nu} ]
\end{align} $$
其中我们使用这几个方法
- $\gamma^{\mu}\not{\! a}\gamma_{\mu} \equiv-2\not{\! a}$
- trace 只对偶数个旋量不为零
- $\mathrm{Tr}[\not{\! a}\not{\! b}\not{\! c}\not{\! d}]=4(a\cdot bc\cdot d-a\cdot b c\cdot d + a\cdot db\cdot c)$
所以化简出来
$$\begin{align}
&= \frac{8}{t^{2}} \mathrm{Tr}[\not{\! k_{1}}(\not{\! k_{1}}-\not{\! p_{1}})\not{\! k_{2}}(\not{\! k_{1}-\not{\! p_{1}}})] \\
&= \frac{32}{t^{2}}  
\end{align} $$


>[!question] (c)
>注意(b)部分的截面在 $\theta \to 0$ 或 $\pi$ 时发散。让我们分析 $\theta$ 接近0的区域。在这个区域，主要贡献来自 $t$ 道图，并且直观地对应于在 $e^+e^-$ 湮灭成 $B$ 之前从电子线发射光子。让我们重新排列公式以支持这种解释。首先，注意 $\theta \to 0$ 的发散被电子质量截断：设电子动量为 $p^\mu = (E, 0, 0, k)$，其中 $k = (E^2 - m_e^2)^{1/2}$，光子动量为 $k^\mu = (xE, xE\sin\theta, 0, xE\cos\theta)$。证明传播子的分母从不小于 $O(m_e^2/s)$。现在对(b)部分的截面在小角度区域积分，将 $\theta$ 积分在 $\theta^2 \sim (m_e^2/s)$ 处截断，只保留领头对数项，即正比于 $\log(s/m_e^2)$ 的项。证明，在这个近似下，向前光子发射的截面可以写成
>$$
>\sigma(e^+e^- \to \gamma + B) \approx \int dx f(x) \cdot \sigma(e^+e^- \to B \text{ at } E_{\text{cm}}^2 = (1-x)s),
>$$
>其中湮灭截面是针对能量为 $E'$ 的正电子和能量为 $(1 - x)E$ 的电子的碰撞进行评估的，而函数 $f(x)$，即Weizsacker-Williams分布函数，由下式给出：
>$$
>f(x) = \frac{\alpha}{2\pi} \frac{1 + (1 - x)^2}{x} \cdot \log\left(\frac{s}{m_e^2}\right).
>$$
>这个函数普遍出现在光子从电子线共线发射的过程中，与后续动力学无关。我们将在另一个上下文中，在问题6.2中再次遇到它。

---

# 题5.6
>[!note] 这个问题将问题5.3的旋量积技术扩展到外光子。

>[!question] (a)
>设 $k$ 是光子的动量，设 $p$ 是另一个类光矢量，选择使得 $p \cdot k \neq 0$。设 $u_R(p)$, $u_L(p)$ 是具有类光动量 $p$ 的费米子的确定螺旋性的旋量，根据问题5.3的约定定义。将光子极化矢量定义如下：
>$$
>\epsilon^{\mu}_+(k) = \frac{1}{\sqrt{4p \cdot k}} \bar{u}_R(k) \gamma^\mu u_R(p), \quad \epsilon^{\mu}_-(k) = \frac{1}{\sqrt{4p \cdot k}} \bar{u}_L(k) \gamma^\mu u_L(p).
>$$
>使用恒等式
>$$
>u_L(p) \bar{u}_L(p) + u_R(p) \bar{u}_R(p) = \not p
>$$
>计算极化求和
>$$
>\epsilon^{\mu}_- \epsilon^{\nu*}_+ + \epsilon^{\mu}_+ \epsilon^{\nu*}_- = -g^{\mu\nu} + \frac{k^\mu p^\nu + k^\nu p^\mu}{p \cdot k}.
>$$
>右边的第二项与任何光子发射振幅 $M^{\mu}$ 点乘时给出零，所以我们有
>$$
>|\epsilon_+ \cdot M|^2 + |\epsilon_- \cdot M|^2 = M^{\mu} M^{\nu*} (-g_{\mu\nu});
>$$
>因此，我们可以使用矢量 $\epsilon_+, \epsilon_-$ 来计算光子极化求和。

>[!question] (b)
>使用刚刚定义的极化矢量，以及问题5.3中的旋量积和Fierz恒等式，计算一个无质量电子和正电子湮灭成2个光子的微分截面。证明结果与(5.107)中导出的无质量极限一致：
>$$
>\frac{d\sigma}{d\cos\theta} = \frac{2\pi\alpha^2}{s} \left( \frac{1 + \cos^2\theta}{\sin^2\theta} \right)
>$$
>在质心系中。从(a)部分的结果可以得出，这个答案与用于定义极化矢量的特定矢量 $p$ 无关；但是，通过取这个矢量为初始电子4-矢量，计算大大简化。

---
