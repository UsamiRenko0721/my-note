---
up:
  - "[[写题]]"
---

>[!question] 2.5
>考虑一维势垒 $V(q)$ 中运动的粒子，其能量为 $E$ 并且
>$$m\hbar \left|\frac{dV}{dq} \right| \ll (m(E-V))^{3/2} $$
>证明：该粒子的动量 $p$ 的允许值满足以下式子
>$$\oint pdq =\left( n+\frac{1}{2} \right)h $$

这里考虑 Stockes 定理即可，能量 $E$ 以下的相空间区域
$$\Sigma(E) = \{ (q,p) \mid H(q,p) \leq E \} $$
$$\partial \Sigma(E) = \{ (q,p) \mid H(q,p) = E \} $$
而正则 1-形式为
$$\theta = pdq $$
于是
$$d\theta = dp\wedge dq $$
由 Stockes 定理有
$$ \iint_{\Sigma(E)} dqdp = \iint_{\Sigma(E)} d\theta = \oint_{\partial \Sigma(E)} \theta = \oint_{\partial \Sigma(E)} pdq $$
最后由于 $m\hbar \left|\frac{dV}{dq} \right| \ll (m(E-V))^{3/2}$ 相空间可以被视为局域平直，所以每个量子态占据相空间体积为 $h$ 于是量子态数为
$$N(E) = \frac{1}{h} \oint pdq = n $$
$$\oint pdq = nh $$


>[!question] 2.7
>
>(i) 给定能量 $E$ 在 $N$ 个一维谐振子之间进行分配的方式数的渐近表达式，该振子能量本征值是  
>$$\left( n + \frac{1}{2} \right) \hbar \omega, \, n = 0, 1, 2, \cdots$$
>
>(ii) 这个系统相空间的有关区域“体积”的相应表达式。试建立上述两个结果之间的对应关系，并证明转换因子 $\omega_0$ 精确地等于 $h^N$。

第一问很直接，给定粒子数 $N$ ，总能量 $E$ ，设粒子分配为 $\{ n_{r} \}$ 则
$$\sum_{r=1}^{N} \left( n_{r} + \frac{1}{2} \right)\hbar \omega = E $$
记 $M = E /\hbar \omega$ 则微观态数就说方程的解的个数，于是
$$\Omega = \frac{(M + N /2)!}{(M-N /2)!N!} \approx \frac{M^{N}}{N!} $$

另一边通过计算这个相空间体积
$$H = \sum_{r=1}^{N}\left(  \frac{p_{r}^{2}}{2m} + \frac{1}{2}m_{r}\omega^{2}q_{r}^{2} \right) = \frac{\omega}{2} \sum_{r=1}^{N}(u_{r}^{2} + v
_{r}^{2}) $$
故相空间体积为一个半径为 $R=\sqrt{ 2E /\omega }$ 的 $2N$ 维球体的体积
$$V(E) = \int_{\Sigma\leq E} dqdp =  \frac{\pi^{N}}{N!}R^{2N} = \frac{(2\pi E)^{N}}{n!\omega^{N}} $$ 
于是单个态的相空间体积为

$$\omega_{0} = \frac{\Omega}{V} = h^{N} $$



>[!question] 2.8
>按照附录 C 的方法, 用积分
>$$\int_{0}^{\infty} e^{-r}r^2 dr = 2$$
>替换方程 (C.4), 试证明
>$$V_{3N} = \int \cdots \int \prod_{i=1}^{N} (4\pi r_i^2 dr_i) = (8\pi R^3)^N / (3N)!$$
>利用这个公式, 试计算在三维空间中运动的、由 $N$ 个粒子组成的极端相对论性气体 ($\varepsilon = pc$) 的相空间中有关区域的“体积”. 从而, 导出这个系统的各种热力学性质的表达式. 最后, 将所得的结果与习题 1.7 的结果进行比较.

它这里没知名，积分区域是 $\displaystyle\sum_{k=1}^{n}x_{k}\leq R$ 于是
$$I(\lambda) = \int_{0}^{\infty} 4\pi r^{2}e^{ -\lambda r }dr = \frac{8\pi}{\lambda^{3}} $$
$$[I(\lambda)]^{N} = \left( \frac{8\pi}{\lambda^{3}} \right)^{N} $$
而由余面积公式
$$[I(\lambda)]^{N} = \int_{0}^{\infty} dR\ e^{ -\lambda R } \int_{\sum r_{k}\leq R} \prod_{k=1}^{N}(4\pi r_{k}^{2}dr_{k}) = \int_{0}^{\infty} dR \ e^{ -\lambda R } V_{3N} $$
即
$$\int_{0}^{\infty} e^{ -\lambda R } V_{3N} dR = \left( \frac{8\pi}{\lambda^{3}} \right)^{N},\quad  \int_{0}^{\infty} e^{ -\lambda R } R^{3N} dR = \frac{(3N)!}{\lambda^{3N}} $$
所以
$$V_{3N} = \frac{(8\pi R^{3})^{N}}{(3N)!} $$

在极端相对论下 $E=c|\mathbf{p}|$ 所以总能量由
$$E = c\sum_{k=1}^{N} |\mathbf{p}_{k}| $$
当这 $N$ 个粒子是全同时，微观状态数是
$$\Omega = \frac{V^{N}V_{3N}}{N!h^{3N}} = \frac{V^{N}(8\pi E^{3})^{N}}{N!(3N)!(hc)^{3N}} $$
其中 $V$ 是粒子空间，$V^{N}$ 是 $N$ 个粒子提供的空间因子。由此
$$S = k\ln \Omega = Nk[ \ln V  + 3\ln E - \ln N + C] $$
$$\frac{1}{T} = \frac{\partial S}{\partial E} = \frac{3Nk}{E}\implies E = 3NkT $$



>[!question] 2.9
>(a) 试求积分
>$$\int \cdots \int (dx_1 \cdots dx_{3N}), \quad 0 \leq \sum_{i=1}^{3N} |x_i| \leq R$$
>并利用它确定在一维空间中运动的、由 $3N$ 个粒子组成的极端相对论性气体 ($\varepsilon = pc$) 的相空间中有关区域的“体积”，并确定将给定能量 $E$ 分配给该粒子系统的分配方式数，以及渐近地建立 $\omega_0 = h^{3N}$。
>
>(b) 将这个系统的热力学与习题 2.8 中系统的热力学性质进行比较。

$$V^{(1D)}_{3N} = \frac{(2R)^{3N}}{(3N)!} $$
类似的
$$\Omega = \frac{V^{3N}V^{(1D)}_{3N}}{N!h^{3N}} = \frac{L^{N}(2E)^{3N}}{N!(3N)!(hc)^{3N}}  $$
其中 $L=\sqrt[3]{ V }$ 是由于这是个一维的空间，使用 $L$ 更加合理