---
up:
  - "[[写题]]"
related:
date: 2026-04-20
---

## 8.1 Hellmann 定理证明

设量子系统的束缚态能级和归一化能量本征态分别为 $E_{n}$ 和 $\ket{\psi_{n}}$ 设 $\lambda$ 是 $H$ 含有的任何一个参数，证明
$$\frac{\partial E_{n}}{\partial \lambda} = \braket{ \psi_{n} |\frac{\partial H}{\partial \lambda}| \psi_{n} }  $$

>[!S]
>本征方程
>$$(H-E_{n})\ket{\psi_{n}} = 0 \implies \langle\psi_{n}|(H-E_{n}) = 0 $$
>对 $\lambda$ 求导得到
>$$\frac{\partial H}{\partial \lambda}\ket{\psi_{n}} + (H-E_{n})\frac{\partial }{\partial \lambda}\ket{\psi_{n}} = 0 $$
>$$\braket{ \psi_{n} |\frac{\partial H}{\partial \lambda} - \frac{\partial E_{n}}{\partial \lambda}| \psi_{n} } + \braket{ \psi_{n} | (H-E_{n})\frac{\partial }{\partial \lambda}| \psi_{n} }  = 0  $$
>其中 $\langle\psi_{n}|(H-E_{n}) = 0$  故
>$$\braket{ \psi_{n} |\frac{\partial H}{\partial \lambda} - \frac{\partial E_{n}}{\partial \lambda}| \psi_{n} } = 0  $$
>$$ \braket{ \psi_{n} |\frac{\partial H}{\partial \lambda}| \psi_{n} } = \braket{ \psi_{n} | \frac{\partial E_{n}}{\partial \lambda}| \psi_{n} }  = \frac{\partial E_{n}}{\partial \lambda} \braket{ \psi_{n} | \psi_{n} }  = \frac{\partial E_{n}}{\partial \lambda} $$



## 8.2 Virial 定理

设哈密顿算符为
$$H = \frac{\mathbf{p}^{2}}{2\mu} + V(\mathbf{r}) $$
设 $\ket{n}$ 为归一化的束缚态，证明
$$\braket{ n | \frac{\mathbf{p}^{2}}{2\mu}| n } = \frac{1}{2} \braket{ n | \mathbf{r}\cdot \nabla V(\mathbf{r})| n }  $$

>[!S]
>考虑标度变换 $U(\lambda)$ 
>$$\mathbf{r}\to \lambda^{-1} \mathbf{r},\quad \mathbf{p}\to \lambda \mathbf{p} ,\quad \ket{\psi} \to U(\lambda)\ket{\psi}  $$
>于是
>$$E(\lambda) = \braket{ n' | H | n' } = \braket{ n | U^{\dagger}HU| n } = \frac{1}{2\mu}\braket{ n | U^{\dagger}\mathbf{p}^{2}U| n } + \braket{ n | U^{\dagger}VU| n }  = \lambda^{2}\braket{ T } + \braket{ V(\lambda^{-1}\mathbf{r}) }   $$
>而由变分原理，束缚态能量应该取变分的极小值，所以
>$$\frac{\partial E}{\partial \lambda} = 0 \implies 2\lambda\braket{ T } -  \frac{1}{\lambda^{2}}\braket{ \mathbf{r}\cdot \nabla V(\lambda^{-1}\mathbf{r}) } = 0 $$
>代入真正的束缚态能级时的 $\lambda=1$ 得到
>$$2 \braket{ T } = \braket{ \mathbf{r}\cdot \nabla V(\mathbf{r}) } $$
>证毕。当 $V(\mathbf{r})$ 是 $\mathbf{r}$ 的 $\nu$ 次齐次函数时，由欧拉齐次定理
>$$\mathbf{r}\cdot \nabla V(\mathbf{r}) = \nu V(\mathbf{r}) $$
>于是
>$$2\braket{ T } = \nu \braket{ V }  $$

>[!S]
>在坐标表象中
>$$H = -\frac{\hbar^{2}}{2\mu} \nabla^{2} + V(\mathbf{r}) $$
>视 $\hbar$ 为参数使用 Hellmann 定理
>$$\frac{\partial H}{\partial \hbar} = -\frac{\hbar}{\mu}\nabla^{2} \implies \frac{\partial E_{n}}{\partial \hbar} = \frac{2}{\hbar}\braket{ \frac{\mathbf{p}^{2}}{2\mu} }  $$
>而在动量表象下
>$$H = \frac{\mathbf{p}^{2}}{2\mu} + V\left( i\hbar \frac{\partial }{\partial \mathbf{p}} \right) $$
>此时可得
>$$\frac{\partial H}{\partial \hbar} = \frac{\partial V}{\partial \hbar} = \frac{\mathbf{r}}{\hbar}\cdot \nabla V(\mathbf{r}) \implies \frac{\partial E_{n}}{\partial \hbar} = \frac{1}{\hbar}\braket{ \mathbf{r}\cdot \nabla V(\mathbf{r}) }  $$
>于是联立得到
>$$\braket{ n | \frac{\mathbf{p}^{2}}{2\mu}| n } = \frac{1}{2} \braket{ n | \mathbf{r}\cdot \nabla V(\mathbf{r})| n }  $$


## 8.4

质量为 $\mu$ 的粒子在市场 $V_{1}(x)$ 中运动时的束缚态能级为 $E_{n}(1)$ 同理有 $(V_{2}(x),E_{n}(2)),\dots$ 设对于任意的 $x$ 均有
$$V_{1}(x) \leq V_{2}(x) \leq\dots $$
证明
$$E_{n}(1) \leq E_{n}(2) \leq \dots $$

>[!S]
>记 $V_{min}(x)=\text{inf}_{i}(V_{i}(x)),V_{max}=\text{sup}_{i}(V_{i}(x))$ 并构造
>$$V(x;\lambda) = (1-\lambda) V_{min}(x) + \lambda V_{max}(x) $$
>则 $\frac{\partial V}{\partial \lambda} = V_{max}-V_{min}\geq0$ 而对应的
>$$H = -\frac{\hbar^{2}}{2\mu}\nabla^{2} + V(x) $$
>由 Hellmann 定理
>$$\frac{\partial H}{\partial \lambda} = \frac{\partial V}{\partial \lambda} \geq 0 \implies \frac{\partial E_{n}(\lambda)}{\partial \lambda} \geq 0 $$
>所以对于 $V_{1}\leq V_{2}\leq\dots$ 必有 $E_{n}(1)\leq E_{n}(2)\leq \dots$


## 8.5

粒子在势场
$$V(x) = \begin{cases}
\frac{1}{2}kx^{2}, & |x|<b \\
\frac{1}{2}kb^{2}, & |x|>b
\end{cases} $$
中运动，估算束缚态能级的总数的范围

>[!S]
>考虑简谐势和直角势
>$$V_{1} = \frac{1}{2}kx^{2} ,\quad V_{2} = \begin{cases}0, & |x|<b \\ \frac{1}{2}kb^{2}, & |x|>b \end{cases} $$
>则
>$$V_{1}\leq V\le V_{2} $$
>于是由上一问可知束缚态有
>$$E_{n,\text{谐振}} \leq E_{n} \leq E_{n,\text{直角}} $$
>对于谐振势
>$$E_{n}(1) = \hbar \omega\left( n+\frac{1}{2} \right)\leq \frac{1}{2}kb^{2} \implies N_{1} \simeq \frac{kb^{2}}{2\hbar \omega} = \frac{b^{2}}{2\hbar}\sqrt{ k\mu } $$
>对于直角势
>$$N_{2} \simeq \frac{2b^{2}}{\pi \hbar}\sqrt{ k\mu } $$
>于是束缚态数范围为
>$$\frac{1}{2} \sim \frac{2}{\pi} ,\quad\text{单位 } \frac{b^{2}}{\hbar}\sqrt{ k\mu } $$



## 8.13

质量为 $\mu$ 的粒子在中心势场 $V(r)$ 中运动，处于基态。一直 $V(r)$ 是 $r$ 的单调递增的函数。$V(r)$ 于质量无关，证明：在任意给定的球面，半径为 $R$，内粒子出现的概率随粒子质量增加而增加

>[!S]
>径向波函数 $u(r)$ 满足
>$$-\frac{\hbar^2}{2\mu} u'' + V(r) u = E u,\quad u(0)=0,\quad \int_0^\infty u^2 dr =1$$
>其中 $E$ 为基态能量。对 $\mu$ 求导，记 $w = \partial u/\partial\mu$，可得
>$$-\frac{\hbar^2}{2\mu} w'' + (V-E) w = -\frac{1}{\mu}(V-E)u - E' u$$
>其中 $E' = \partial E/\partial\mu$。由 Hellmann 定理，$E'=−⟨T⟩/μ<0$。利用原方程消去高阶项，得到 $w$ 满足的微分方程。分析可知：在 $r=0$ 附近，$u∼cr$，故 $w∼c'r^{3}$ 且 $c'>0$，即 $w>0$ 于小 $r$；当 $r→∞$ 时，$u$ 指数衰减，$w$ 也趋于零且为负（由归一化条件 $∫uw=0$ 及 $u>0$ 保证）。进一步可证 $w$ 在 $(0,∞)$ 内恰有一个零点 $r_{0}$​，且 $w>0$ 当 $r<r_{0}$​，$w<0$ 当 $r>r_{0}$​。
>
>给定半径 $R$，球内概率为
>$$P(R) = \int_0^R u^2 dr$$
>$$\frac{\partial P}{\partial\mu} = 2\int_0^R u w\, dr$$
>由于 $\int_0^\infty u w\, dr = 0$，有
>$$\int_0^{r_0} u w\, dr = -\int_{r_0}^\infty u w\, dr >0$$
>于是
>$$\int_0^R u w\, dr = \begin{cases}\int_0^R u w\, dr >0, & R\le r_0,\\[4pt]\int_0^{r_0} u w\, dr + \int_{r_0}^R u w\, dr \ge \int_0^{r_0} u w\, dr + \int_{r_0}^\infty u w\, dr =0, & R>r_0\end{cases}$$
>等号仅在 $R\to\infty$ 时成立，故对任意有限 $R$ 有 $\partial P/\partial\mu >0$。因此，球内概率随粒子质量增加而严格增加。

