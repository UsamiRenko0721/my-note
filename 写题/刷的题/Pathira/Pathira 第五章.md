---
up:
  - "[[写题]]"
related:
date: 2026-03-28
---
# 5.1

试计算在取 $\sigma_{x}$ 为对角元的表象中一个电子自旋的密度矩阵 $\rho_{nm}$ 其次，试证明由此表象所得到的 $\braket{ \sigma_{z} }$ 值恰好与第 5.3 节得到的结果相同

>[!S]
>在以 $\sigma_{x}$ 为对角的表象，相较 $\sigma_{z}$ 为对角的表象，只需进行幺正变换
>$$U = \frac{1}{\sqrt{ 2 }}\begin{pmatrix}
1 & 1 \\ -1 & 1
\end{pmatrix} $$
>于是
>$$\rho^{(x)} = U^{\dagger}\rho^{(z)}U = \frac{1}{2}\begin{pmatrix}
1 & \tanh(\beta \mu_{B}B) \\ \tanh(\beta \mu_{B}B) & 1
\end{pmatrix} $$
>$$\sigma^{(x)}_{z} = U^{\dagger}\sigma^{(z)}_{z}U = \begin{pmatrix}
0 & 1 \\ 1 & 0
\end{pmatrix} $$
>于是
>$$\braket{ \sigma_{z} } = \mathrm{Tr}(\sigma^{(z)}_{z}\rho^{(z)}) = \frac{1}{2}\mathrm{Tr}[{\begin{pmatrix}
0 & 1 \\1 & 0
\end{pmatrix}\begin{pmatrix}
1 & \tanh(\beta \mu_{B}B)\\ \tanh(\beta \mu_{B}B) & 1
\end{pmatrix}}] = \tanh(\beta \mu_{B}B) $$
>与在 $\sigma_{z}$ 对角的表象中得到的结果一致


# 5.2

试求证
$$\braket{ q |e^{ -\beta H }| q' } = \exp\left[ -\beta H\left( -i\hbar \frac{\partial }{\partial q} ,q \right) \right]\delta(q-q') $$
其中 $H\left( -i\hbar \frac{\partial }{\partial q},q \right)$ 是 $q$ 表象中系统的哈密顿算符，它形式地作用于狄拉克 $\delta$ 函数上。试以适宜的形式写出 $\delta$ 函数并利用这个结果到以下两种情形：
	(1) 一个自由粒子
	(2)一个线性谐振子

>[!S]
>由于 $H$ 作用在位置本征态 $\ket{q}$ 上所以动量部分视为对坐标的求导
>$$\braket{ q |e^{ -\beta H }| q' } = \braket{ q |\sum \frac{(-\beta)^{n}}{n!}H^{n} | q' } = \sum \frac{(-\beta)^{n}}{n!} H^{n}(p,q) \braket{ q | q' } = \exp[-\beta H]\braket{ q | q' }  $$
>而 $\braket{ q | q' }=\delta(q-q')$ 所以
>$$ \braket{ q |e^{ -\beta H }| q' } = \exp\left[ -\beta H\left( -i\hbar \frac{\partial }{\partial q} ,q \right) \right]\delta(q-q')  $$
>对于 delta 函数，一个可以用坐标表达的方式是
>$$\delta(q-q') = \frac{1}{2\pi \hbar} \int_{-\infty}^{\infty} \exp\left( \frac{ip(q-q')}{\hbar} \right) dp $$
>(1)
>对于自由粒子
>$$H = \frac{p^{2}}{2m} \to -\frac{\hbar^{2}}{2m} \frac{\partial^{2}}{\partial q^{2}} $$
>$$\begin{align}
\braket{ q |e^{ -\beta h }| q' } & = \frac{1}{2\pi \hbar} \exp\left( -\frac{\beta \hbar^{2}}{2m} \frac{\partial^{2}}{\partial q^{2}} \right)\int_{-\infty}^{+\infty} \exp\left( \frac{ip(q-q')}{\hbar} \right)dp \\ & =\frac{1}{2\pi \hbar}\int_{-\infty}^{+\infty} \exp\left( -\frac{\beta p^{2}}{2m} \right)e^{ ip(q-q')/\hbar }dp \\ & =\sqrt{ \frac{m}{2\pi \hbar^{2}\beta} } \exp\left( -\frac{m(q-q')^{2}}{2\hbar^{2}\beta} \right)
\end{align}$$
>(2)
>对于一维谐振子
>$$H = \frac{p^{2}}{2m} + \frac{1}{2}m\omega^{2}q^{2} \to -\frac{\hbar^{2}}{2m}\frac{\partial^{2}}{\partial q^{2}} + \frac{1}{2}m\omega^{2}q^{2} $$
>$$\begin{align}
\braket{ q |e^{ -\beta h }| q' } & = \frac{1}{2\pi \hbar} \exp\left( -\frac{\beta \hbar^{2}}{2m} \frac{\partial^{2}}{\partial q^{2}} + \frac{1}{2}m\omega^{2}q^{2} \right)\int_{-\infty}^{+\infty} \exp\left( \frac{ip(q-q')}{\hbar} \right)dp 
\end{align} $$


---

# 5.3

对于下列情形: (i) 一个自由粒子和 (ii) 一个线性谐振子，试推导在动量表象中的密度矩阵 $\rho$；并按照第 5.3 节的思路研究密度矩阵的主要性质

>[!S]
>(i)
>$$\braket{ \mathbf{p} |e^{ -\beta H }| \mathbf{p}' } = \exp\left( -\frac{\beta \mathbf{p}^{2}}{2m} \right) \delta(\mathbf{p}-\mathbf{p}') $$
>单粒子的配分函数是 $Z_{1}(\beta) = \frac{V}{\lambda^{3}}$ 则密度矩阵是
>$$\braket{ \mathbf{p} |\rho| \mathbf{p}' } = \frac{\lambda^{3}}{V}\exp\left( -\frac{\beta \mathbf{p}^{2}}{2m} \right)\delta(\mathbf{p}-\mathbf{p}') $$
>对角元 $\braket{ \mathbf{p} |\rho| \mathbf{p} }$ 代表粒子具有动量 $\mathbf{p}$ 的概率密度，它符合玻尔兹曼-麦克斯韦分布。密度矩阵是完全对角的，所以对于平衡态下的自由粒子，动量是一个确定的统计量，不存在不同动量态之间的干涉效应。在高温下 $\beta\to 0$ 分布变得平坦，和麦克斯韦分布一致
>
>(ii)
>书中给出了
>$$\braket{ q |\rho| q } \propto \exp\left[  -\frac{m\omega q^{2}}{\hbar} \tanh \frac{\beta \hbar \omega}{2}  \right] $$
>考虑傅里叶变换
>$$\begin{align}
\braket{ p |\rho| p } & \propto \iint \exp\left[ \frac{i(pq-pq)}{\hbar} \right] \braket{ q |\rho| p } dqdq' \\ & \propto \exp\left[  -\frac{p^{2}}{m\omega \hbar}\tanh \frac{\beta \hbar \omega}{2}  \right]
\end{align}$$
>

这里是插入了完备基
$$\braket{ p |\rho|  p' } = \iint dqdq' \braket{ p | q }\braket{ q |\rho| q' }\braket{ q' | p' } = \iint dqdq'\ e^{ -ipq/\hbar }\braket{ q |\rho| q' } e^{ ip'q'/\hbar }  $$

---

# 5.4

试用非对称波函数 (5 .4 .3) 式，去代换对称波函数 (5.5.7) 式，来研究一个自由粒子系统的密度矩阵与配分函数．并证明上述做法既得不出吉布斯修正因子 (1/N!), 也得不出粒子间的空间相关．


---

# 5.5

试证在一级近似的情况下， $N$ 个无相互作用的、不可分辨的粒子系统的配分函数为：
$$Q_{N}(V,\beta) = \frac{1}{N!\lambda^{3N}} Z_{N}(V,T) ,\quad Z_{N} = \int \exp\left( -\beta \sum_{i<j} v_{s}(r_{ij}) \right) d^{3N}r $$
其中 $v_{s}(r_{ij})$ 为统计势。并由此求出该系统的舞台方程的一阶修正。

>[!S]
>对于理想量子气体，$N$ 个全同粒子的正则配分函数可通过对称化密度矩阵得到
>$$Q_{N} = \frac{1}{N!\lambda^{3N}} \int d^{3N}r \sum_{P}(\pm 1)^{P}\exp\left( -\frac{\pi}{\lambda^{2}} \sum_{i=1}^{N} |r_{i} - Pr_{i}|^{2} \right) $$
>在低密度（高温）近似下，仅保留恒等置换 $P=I$ 和两两对换 $P=(ij)$ 的贡献
>$$Q_{N} \approx \frac{1}{N!\lambda^{3N}} \int d^{3N}r \left[  1+ \sum_{i<j} e^{ -2\pi r^{2}_{ij}/\lambda^{2} }  \right] $$
>其中 $r_{ij}=|\boldsymbol{r}_i-\boldsymbol{r}_j|$。该式可等价地写为
>$$Q_{N} = \frac{1}{N!\lambda^{3N}} \int d^{3N}r \exp\left( -\beta \sum_{i<j} v_{s}(r_{ij}) \right) $$
>取 $\exp(-\beta v_{s})=1\pm e^{ -2\pi r^{2}/\lambda^{2} }\approx1\pm(1-2\pi r^{2} /\lambda^{2})$ 即可得到一阶修正。将 $v _s$ 看作是气体间的相互作用则对于物态方程
>$$P = nKT(1 + B_{2}n + \dots) $$
>$$B_{2} = -\frac{1}{2}\int d^{3}r\ (e^{ -\beta v_{s} } - 1) = -\frac{1}{2}\int d^{3}r\ (\pm e^{ -2\pi r^{2}/ \lambda^{2} }) = \mp \frac{\lambda^{3}}{2^{5/2}} $$
>代入得到
>$$P = nKT\left( 1 \mp \frac{n\lambda^{3}}{2^{5/2}} + \dots \right) $$
>
>

---

# 5.6

试求在标准压强与温度下氢、氢和氧的简并性判别式 $n\lambda^{3}$ 的值．对于使此值变成近于 1 从而量子效应变得重要的相应温度范围作出估计

>[!S]
>标准情况 $T=273.15\text{K},P=101325\text{Pa}$ 故分子数密度为 $n=P /(kT)=2.687\times 10^{25}\text{m}^{-1}$ 热波长为 $\lambda=h /\sqrt{ 2\pi mkT }$
>
>对于 $\pu{ H_{2} }$ $m = 3.347 \times 10^{-27}\,\text{kg}$，$\lambda \approx 7.44 \times 10^{-11}\,\text{m}$，$n\lambda^3 \approx 1.1 \times 10^{-5}$
>对于 $\pu{ He }$ $m = 6.646 \times 10^{-27}\,\text{kg}$，$\lambda \approx 5.28 \times 10^{-11}\,\text{m}$，$n\lambda^3 \approx 4.0 \times 10^{-6}$
>对于 $\pu{ O_{2} }$ $m = 5.314 \times 10^{-26}\,\text{kg}$，$\lambda \approx 1.87 \times 10^{-11}\,\text{m}$，$n\lambda^3 \approx 1.8 \times 10^{-7}$
>
>均远小于 $1$ 故量子效应可以忽略。若要使得 $n\lambda^{3}=1$ 则 $\lambda=n^{-1/3} =3.339\times 10^{-9}\text{m}$ 代入数据得
>
>对于 $\pu{ H_{2} }$ $T=2.8\text{K}$
>对于 $\pu{ He }$ $T=1.9\text{K}$
>对于 $\pu{ O_{2} }$ $T=0.54\text{K}$

---

# 5.7

试证明当平均热波长 $\lambda$ 比 (i)粒子间平均距离 $(V /N)^{1/3}$ 和 (ii)粒子间势的特征长度 $r_{0}$ 产小得多时， $N$ 个相互作用粒子系统的量子力学配分函数趋于经典的形式：
$$Z_{N}(V,T) = \frac{1}{N!h^{3N}} \int e^{ -\beta E(q,p) } d^{3N}q d^{3N}p $$

---

# 5.8

试证明佩尔斯提出的下列定理：倘若 $H$ 是一给定物理系统的厄米哈密顿算符，$\{ \phi_{n} \}$是满足问题的对称要求和边界条件的任意正交化波函数集合，则系统的配分函数满足以下不等式：
$$Z_{N}\geq \sum_{n}\exp(-\beta \braket{ \phi_{n} |H| \phi_{n} } ) $$
当 $\{ \phi_{n} \}$ 是哈密顿算符本身的本征函数的一个完全正交归一化集合时，等式成立．

>[!S]
>$$Z_{N}(\beta) = \mathrm{Tr}(e^{ -\beta H }) = \sum_{n} \braket{ \phi_{n} |e^{ -\beta H }| \phi_{n} } = \sum_{n} $$
>考虑到 Jessen 不等式有
>$$\exp\left( -\beta \sum_{i} |c_{ij}|^{2}E_{i} \right) \leq \sum_{i} |c_{ij}|^{2} \exp(-\beta E_{i}) $$
>于是
>$$Z_{N} = \sum_{n}\braket{ \phi_{n} |e^{ -\beta H }| \phi_{n} }  \geq \sum_{n}\exp(-\beta \braket{ \phi_{n} |H| \phi_{n} } ) $$
>