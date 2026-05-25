---
up:
  - "[[写题]]"
related:
date: 2026-03-15
tags:
  - 广相
  - 习题
---


# 25 年

In this problem, we study the gravitational waves emitted from a binary system of two black holes. As a simplifying assumption, we treat black holes as point masses. For all parts except (5), please give your answers in analytical expressions in terms of quantities provided in the problem and fundamental constants such as the speed of light c and Newton’s constant G.

(a) For a point mass m moving near the origin in the $(x, y)$ plane along a trajectory $x = x(t), y =y(t)$, general relativity predicts that the gravitational waves emitted by $m$ have the following amplitudes $h$ at distance $L$ from the origin with inclination angle $θ$:
$$h_{+} = \frac{1}{L} \frac{G}{c^{4}} \frac{1+\cos ^{2}\theta}{2} m\left( \frac{d^{2}}{dt^{2}}(x^{2}-y^{2}) \right) ,\quad h_{\times} = \frac{1}{L} \frac{G}{c^{4}} \cos \theta m\left( \frac{d^{2}}{dt^{2}}(xy) \right) $$
where $h_{+}$ and $h_{\times}$ represent the two independent polarization modes. For two black holes with masses $m_{1}$ and $m_{2}$ separated by $r$, forming a circular orbit under Newtonian gravity with their center-of-mass at the origin (figure 1), please derive $h_{+}$ and $h_{\times}$. What is the gravitational wave frequency $f$?

>[!solution]-
>这两个黑洞绕质心做圆周运动，设 $x=L\cos \Omega t,y=L\sin \Omega t$ 于是由开普勒定律
>$$\Omega = \sqrt{ \frac{G(m_{1}+m_{2})}{r^{3}} } $$
>$$\frac{d^{2}}{dt^{2}}(x^{2}-y^{2}) = -L^{2}\Omega^{2}\cos 2\Omega t ,\quad \frac{d^{2}}{dt^{2}}(xy) = -L^{2}\Omega^{2}\sin 2\Omega t $$
>$$h_{+} = -\frac{GL\Omega^{2}m}{c^{4}} \frac{1+\cos ^{2}\theta}{2}\cos 2\Omega t ,\quad h_{\times} = -\frac{GL\Omega^{2}m}{c^{4}} \cos \theta \sin 2\Omega t $$
>注意到 $\Omega$ 是黑洞的轨道运动角频率，在一个周期内引力波相位变化两次，于是引力波频率为
>$$f= \frac{2\Omega}{2\pi} = \frac{1}{\pi}\sqrt{ \frac{G(m_{1}+m_{2})}{r^{3}} } $$

(b) Gravitational waves carry energy. The power per solid angle radiated outward at distance $L$ is given by
$$p = \frac{c^{3}L^{2}}{16\pi G}\left[  \left( \frac{\partial h_{+}}{\partial t} \right)^{2} + \left( \frac{\partial h_{\times}}{\partial t} \right)^{2} \right] $$
Please find the average power $P$ radiated by the above black hole binary over all directions and averaged over one orbital period.

>[!solution]-
>由上一问，继续对时间求导即可得到
>$$\frac{\partial h_{+}}{\partial t} = \frac{2GL\Omega^{3}m}{c^{4}} \frac{1+\cos ^{2}\theta}{2}\sin 2\Omega t ,\quad \frac{\partial h_{\times}}{\partial t} = -\frac{2GL\Omega^{3}m}{c^{4}}\cos \theta \cos 2\Omega t $$
>$$p = \frac{c^{3}L^{2}}{16\pi G}\left( \frac{2GL\Omega^{3}m}{c^{4}} \right)^{2}\left[  \left( \frac{1+\cos ^{2}\theta}{2} \right)^{2}\sin ^{2}2\Omega t + \cos ^{2}\theta \cos ^{2}2\Omega t  \right] $$
>对时间平均得到
>$$\braket{ p }_{T} = \frac{c^{3}L^{2}}{16\pi G}\left( \frac{2GL\Omega^{3}m}{c^{4}} \right)^{2}\left[ \left( \frac{1+\cos ^{2}\theta}{2} \right)^{2} \frac{1}{2}+ \cos ^{2}\theta \frac{1}{2}  \right] $$
>对全方向平均得到
>$$\begin{align}P & = \frac{c^{3}L^{2}}{32\pi G}\left( \frac{2GL\Omega^{3}m}{c^{4}} \right)^{2}\int\left[  \frac{1}{4}\cos ^{4}\theta +\cos ^{2}\theta + \frac{1}{4} \right]d\Omega \\ & = \frac{GL^{4}\Omega^{6}m^{2}}{8\pi c^{5}} \cdot 2\pi \int_{0}^{\pi}\left( \frac{1}{4}\cos ^{4}\theta + \cos ^{2}\theta + \frac{1}{4} \right)\sin \theta d\theta \\ & = \frac{32GL^{4}\Omega^{6}m^{2}}{5c^{5}} \end{align}$$

(c) The binary orbit changes slowly due to the gravitational wave radiation. Let the gravitational wave frequency be f0 at the initial time $t = t_{0}$. Please determine $f(t)$.

>[!solution]-
>双星系统的能量是
>$$E = -\frac{Gm_{1}m_{2}}{2r} $$
>引力波辐射能量，于是
>$$\frac{dE}{dt} = -P $$
>即
>$$\frac{Gm_{1}m_{2}}{2r^{2}} \frac{dr}{dt} = - \frac{32G\Omega^{6}m_{1}^{2}m_{2}^{2}}{5c^{5}(m_{1}+m_{2})}r^{4} ,\quad \Omega = \sqrt{ \frac{G(m_{1}+m_{2})^{2}}{r^{3}} } $$
>$$\frac{dr}{dt} = -\frac{64G^{3}m_{1}^{2}m_{2}^{2}(m_{1}+m_{2})}{5c^{5}} \frac{1}{r^{5}} $$
>记作 $\frac{dr}{dt}=-\frac{A}{r^{5}}$ 其中
>$$A = \frac{64G^{3}m_{1}^{2}m_{2}^{2}(m_{1}+m_{2})}{5c^{5}} $$
>分离变量积分：
>$$r^{5}dr = -A\, dt \;\implies\; \frac{r^{6}}{6} = -A(t-t_{0}) + C $$
>由初始条件 $r(t_{0})=r_{0}$ 得 $C = r_{0}^{6}/6$，于是
>$$r^{6} = r_{0}^{6} - 6A(t-t_{0}) $$
>由 Kepler 定律及引力波频率与轨道频率的关系 $f = \Omega/\pi$：
>$$\Omega^{2} = \frac{G(m_{1}+m_{2})}{r^{3}} ,\quad f = \frac{1}{\pi}\sqrt{ \frac{G(m_{1}+m_{2})}{r^{3}} } $$
>$$\implies r^{3} = \frac{G(m_{1}+m_{2})}{\pi^{2}f^{2}} ,\quad r^{6} = \frac{G^{2}(m_{1}+m_{2})^{2}}{\pi^{4}f^{4}} $$
>代入 $r^{6}$ 的演化方程：
>$$\frac{G^{2}(m_{1}+m_{2})^{2}}{\pi^{4}f^{4}} = \frac{G^{2}(m_{1}+m_{2})^{2}}{\pi^{4}f_{0}^{4}} - 6A(t-t_{0}) $$
>$$f^{-4} = f_{0}^{-4} - \frac{6\pi^{4}A}{G^{2}(m_{1}+m_{2})^{2}}(t-t_{0}) $$
>代入 $A$ 的表达式：
>$$\frac{6\pi^{4}A}{G^{2}(m_{1}+m_{2})^{2}} = \frac{384\pi^{4}G\,m_{1}^{2}m_{2}^{2}}{5c^{5}(m_{1}+m_{2})} $$
>最终得到频率演化：
>$$\boxed{f(t) = f_{0}\left[ 1 - \frac{384\pi^{4}G\,m_{1}^{2}m_{2}^{2}f_{0}^{4}}{5c^{5}(m_{1}+m_{2})}(t-t_{0}) \right]^{-1/4}} $$
>若用啁啾质量 $\mathcal{M} = (m_{1}m_{2})^{3/5}/(m_{1}+m_{2})^{1/5}$ 表示，则化为标准形式：
>$$f(t)^{-\frac{8}{3}} = f_{0}^{-\frac{8}{3}} - \frac{96}{5}\pi^{\frac{8}{3}}\left( \frac{G\mathcal{M}}{c^{3}} \right)^{\frac{5}{3}}(t-t_{0}) $$

(d) Eventually, the black holes merge as the orbital radius shrinks. Let the initial separation be $r_{0}$. Please find the coalescence time $T_{C}$

>[!solution]-
>合并时 $r \to 0$，由 $r^{6} = r_{0}^{6} - 6A(t-t_{0})$ 令 $r=0$，设 $T_{C}$ 为从 $t_{0}$ 到合并的时间：
>$$r_{0}^{6} = 6A\,T_{C} \;\implies\; \boxed{T_{C} = \frac{r_{0}^{6}}{6A} = \frac{5c^{5}r_{0}^{6}}{384\,G^{3}m_{1}^{2}m_{2}^{2}(m_{1}+m_{2})}}$$
>或用初始引力波频率 $f_{0}$ 表示：
>$$\boxed{T_{C} = \frac{5c^{5}(m_{1}+m_{2})}{384\pi^{4}G\,m_{1}^{2}m_{2}^{2}f_{0}^{4}}}$$
>用啁啾质量 $\mathcal{M} = (m_{1}m_{2})^{3/5}/(m_{1}+m_{2})^{1/5}$ 表示的标准形式：
>$$T_{C} = \frac{5}{256}\left( \frac{c^{3}}{G\mathcal{M}} \right)^{\frac{5}{3}}\frac{1}{\pi^{\frac{8}{3}}f_{0}^{\frac{8}{3}}}$$

(e) For $m_{1}=m_{2}=10M$ (where M is solar mass), please estimate the maximum initial separation $r_{0}$ (in astronomical unit (au), namely the mean distance between the sun and the earth) allowing coalescence within the age of the universe ($T\simeq 10^{10}$ years). Order-of-magnitude estimation suffices.

>[!solution]-
>取 $m_{1}=m_{2}=10M_{\odot}$，$T_{C} \sim 10^{10}\,\mathrm{yr} \sim 3\times 10^{17}\,\mathrm{s}$。由 (d)：
>$$r_{0}^{6} = \frac{384}{5}\frac{G^{3}}{c^{5}}\,m_{1}^{2}m_{2}^{2}(m_{1}+m_{2})\,T_{C}$$
>代入数值：
>$$m_{1}^{2}m_{2}^{2}(m_{1}+m_{2}) = 100M_{\odot}^{2}\cdot 100M_{\odot}^{2}\cdot 20M_{\odot} = 2\times 10^{5}M_{\odot}^{5}$$
>量纲估算。太阳的施瓦西半径之半：
>$$\frac{GM_{\odot}}{c^{2}} \approx 1.5\times 10^{3}\,\mathrm{m}$$
>$$\frac{G^{3}M_{\odot}^{5}}{c^{5}} = M_{\odot}\left( \frac{GM_{\odot}}{c^{2}} \right)^{3}c \sim (2\times 10^{30})\cdot(3.4\times 10^{9})\cdot(3\times 10^{8}) \sim 7\times 10^{47}\,\mathrm{m^{3}\!\cdot\!s}$$
>$$\begin{align}
>r_{0}^{6} &\sim \frac{384}{5}\cdot 2\times 10^{5}\cdot 7\times 10^{47}\cdot 3\times 10^{17} \\
>&\sim 1.5\times 10^{2}\cdot 2\times 10^{5}\cdot 2\times 10^{65} \sim 6\times 10^{72}\,\mathrm{m^{6}}
>\end{align}$$
>$$r_{0} \sim (6\times 10^{72})^{1/6} \sim (6^{1/6})\times 10^{12} \sim 1.3\times 10^{12}\,\mathrm{m}$$
>$1\,\mathrm{au} \approx 1.5\times 10^{11}\,\mathrm{m}$，故：
>$$\boxed{r_{0} \sim \frac{1.3\times 10^{12}}{1.5\times 10^{11}} \sim 10\,\mathrm{au}}$$
>量级上 $r_{0}\sim 10\,\mathrm{au}$，与太阳系尺度相当。


# 24 年

Let $ds^{2}=-(dx^{0})^{2} + \sum_{i=1}^{n}(dx^{i})^{2}$ be the Minkowski metric of $\mathbb{R}^{1,n}$ . The de Sitter space $dS_{n}$ is the submanifold of $\mathbb{R}^{1,n}$ defined by the following equation
$$-(x^{0})^{2} + \sum_{i=1}^{n} (x^{i})^{2} = \alpha^{2} $$
where $\alpha$ is a nonzero real constant. Define the static coordinates $(t, r, z^{2} , · · · , z^{n})$ as
$$\begin{gather}
x^{0} = \sqrt{ \alpha^{2} - r^{2} } \sinh(t /\alpha) \\
x^{1} = \sqrt{ \alpha^{2} - r^{2} } \cosh(t /\alpha) \\
x^{i} = rz^{i} ,\quad i = 2 ,3 ,\dots ,n
\end{gather} $$
where $z_{i}$ ’s are coordinates of an $(n − 2)$-sphere with radius 1 in $\mathbb{R}^{n-1}$ ( $\sum_{i=2}^{n} (z_{i})^{2}=1$ )

(a) Show that $(t, r, z^{2} , · · · , z^{n})$ is a set of local coordinates of $dS_{n}$.

>[!S]
>首先证明 $(t,r,z^{2},\dots z^{n})$ 落在 $dS_{n}$ 上，$dS_{n}$ 被定义为
>$$-(x^{0})^{2} + \sum_{i=1}^{n}(x^{i})^{2} = \alpha^{2} $$
>的子流形，进行坐标变换后
>$$\begin{align}
LHS & =-(\alpha^{2}-r^{2})\sinh^2\left( \frac{t}{\alpha} \right) + (\alpha^{2}-r^{2})\cosh^2\left( \frac{t}{\alpha} \right) + \sum_{i=2}^{n}(rz^{i})^{2} \\ & =(\alpha^{2}-r^{2})\left(  \cosh^2 \frac{t}{\alpha} - \sinh^2 \frac{t}{\alpha} \right) + r^{2} \sum_{i=2}^{n}(z_{i})^{2} \\ & =\alpha^{2} - r^{2} + r^{2} \\ & =\alpha^{2} = RHS
\end{align} $$
>所以这个坐标确实落在子流形上。然后证明这是局部同胚的，要找到坐标变换的逆变换
>$$r^{2} = \sum_{i=2}^{n} (x_{i})^{2} \implies r = \sqrt{ \sum_{i=2}^{n}(x^{i})^{2} } $$
>$$z^{i} = \frac{x^{i}}{r} = \frac{x^{i}}{\sqrt{ \sum_{i=2}^{n}(x^{i})^{2} }} $$
>$$t = \alpha \tanh^{-1}\left( \frac{x^{0}}{x^{1}} \right) $$
>

(b) Compute the metric on $dS_{n}$ induced from the Minkowski metric of $\mathbb{R}^{1,n}$ (Hint: you may use the above coordinates).

>[!S]
>对于闵式度规下
>$$ds^{2} = -(dx^{0})^{2} + \sum_{i=1}^{n} (dx^{i})^{2} $$
>代入坐标变换
>$$dx^{0} = \frac{r}{\sqrt{ \alpha^{2}-r^{2} }}\sinh(t /\alpha)dr + \frac{\sqrt{ \alpha^{2}-r^{2} }}{\alpha}\cosh(t /\alpha)dt $$
>$$dx^{1} = \frac{r}{\sqrt{ \alpha^{2}-r^{2} }}\cosh(t /\alpha)dr + \frac{\sqrt{ \alpha^{2}-r^{2} }}{\alpha}\sinh(t /\alpha)dt $$
>$$dx^{i} = z^{i}dr + r dz^{i} $$
>于是
>$$\begin{align}
-(dx^{0})^{2} + (dx^{1})^{2} = - \frac{\alpha^{2}-r^{2}}{\alpha^{2}} dt^{2} + \frac{r^{2}}{\alpha^{2}-r^{2}}dr^{2}
\end{align} $$
> $$ds^{2} = -(dx^{0})^{2} + \sum_{i=1}^{n} (dx^{i})^{2} = -\left( 1-\frac{r^{2}}{\alpha^{2}} \right)dt^{2} + \left( 1-\frac{r^{2}}{\alpha^{2}} \right)^{-1}dr^{2} + r^{2}d\Omega^{2}_{n-2} $$


(c) Let n = 3, compute the Ricci tensor $R_{\mu \nu}$ and scalar curvature $R$ of $dS_{3}$. Is $dS_{3}$ an Einstein metric?

>[!S]
>对于 de Sitter 空间
>$$R_{\mu \nu \rho \sigma} = \frac{1}{\alpha^{2}}(g_{\mu \rho}g_{\nu \sigma} - g_{\mu \sigma}g_{\nu \rho}) $$
>$$R_{\mu \nu} = \frac{n-1}{\alpha^{2}}g_{\mu \nu} $$
>$$R = \frac{n(n-1)}{\alpha^{2}} $$
>代入 $n=3$ 的
>$$R_{\mu \nu} = \frac{2}{\alpha^{2}}g_{\mu \nu} ,\quad R = \frac{6}{\alpha^{2}} $$


(d) Are $\partial_{t}$ and $\partial_{\phi}$ killing vector fields in static coordinates when n = 3? Prove your answer.

>[!S]
>度规不含 $t,\phi$ 故 $\partial_{t},\partial_{\phi}$ 必然是 killing 矢量场，下验证之。
>
>先验证 $\xi = \partial_{t}$。在静态坐标下度规为：
>$$ds^{2} = -\left(1-\frac{r^{2}}{\alpha^{2}}\right)dt^{2} + \left(1-\frac{r^{2}}{\alpha^{2}}\right)^{-1}dr^{2} + r^{2}(d\theta^{2}+\sin^{2}\theta\,d\phi^{2})$$
>度规分量均与 $t$ 无关：$\partial_{t}g_{\mu\nu}=0$。
>Killing 方程：$\nabla_{\mu}\xi_{\nu} + \nabla_{\nu}\xi_{\mu} = \partial_{\mu}\xi_{\nu} + \partial_{\nu}\xi_{\mu} - 2\Gamma^{\lambda}_{\mu\nu}\xi_{\lambda} = 0$。
>对 $\xi^{\mu} = (1,0,0,0)$，$\xi_{\mu} = g_{\mu t} = (-f(r),0,0,0)$ 其中 $f(r)=1-r^{2}/\alpha^{2}$。
>仅有 $\xi_{t}\neq 0$，且 $\partial_{\mu}\xi_{\nu}$ 仅当 $\mu=r,\nu=t$ 时非零（为 $-f'$），$\partial_{\nu}\xi_{\mu}$ 仅当 $\nu=r,\mu=t$ 时非零：
>$$\nabla_{t}\xi_{r} + \nabla_{r}\xi_{t} = (\partial_{t}\xi_{r} - \Gamma^{\lambda}_{tr}\xi_{\lambda}) + (\partial_{r}\xi_{t} - \Gamma^{\lambda}_{rt}\xi_{\lambda}) = 0 - \Gamma^{t}_{tr}\xi_{t} - f' - \Gamma^{t}_{rt}\xi_{t}$$
>由 $\Gamma^{t}_{tr} = \frac{f'}{2f}$，$\xi_{t} = -f$：
>$$= -\frac{f'}{2f}(-f) - f' - \frac{f'}{2f}(-f) = \frac{f'}{2} - f' + \frac{f'}{2} = 0$$
>其余分量显然为零，故 $\partial_{t}$ 是 Killing 矢量。
>
>再验证 $\eta = \partial_{\phi}$。$\eta^{\mu} = (0,0,0,1)$，$\eta_{\mu} = (0,0,0,r^{2}\sin^{2}\theta)$。度规均不含 $\phi$。
>仅有 $\eta_{\phi}\neq 0$，非零导数为 $\partial_{r}\eta_{\phi} = 2r\sin^{2}\theta$，$\partial_{\theta}\eta_{\phi} = 2r^{2}\sin\theta\cos\theta$。
>相关 Christoffel 符号：$\Gamma^{\phi}_{r\phi} = 1/r$，$\Gamma^{\phi}_{\theta\phi} = \cot\theta$。
>验证 $\nabla_{\mu}\eta_{\nu} + \nabla_{\nu}\eta_{\mu}$：
>$$\begin{align}
>\nabla_{r}\eta_{\phi} + \nabla_{\phi}\eta_{r} &= (\partial_{r}\eta_{\phi} - \Gamma^{\lambda}_{r\phi}\eta_{\lambda}) + (\partial_{\phi}\eta_{r} - \Gamma^{\lambda}_{\phi r}\eta_{\lambda}) \\
>&= (2r\sin^{2}\theta - \Gamma^{\phi}_{r\phi}\eta_{\phi}) + (0 - \Gamma^{\phi}_{\phi r}\eta_{\phi}) \\
>&= 2r\sin^{2}\theta - \frac{1}{r}\cdot r^{2}\sin^{2}\theta - \frac{1}{r}\cdot r^{2}\sin^{2}\theta = 0
>\end{align}$$
>$$\begin{align}
>\nabla_{\theta}\eta_{\phi} + \nabla_{\phi}\eta_{\theta} &= (\partial_{\theta}\eta_{\phi} - \Gamma^{\lambda}_{\theta\phi}\eta_{\lambda}) + (\partial_{\phi}\eta_{\theta} - \Gamma^{\lambda}_{\phi\theta}\eta_{\lambda}) \\
>&= (2r^{2}\sin\theta\cos\theta - \Gamma^{\phi}_{\theta\phi}\eta_{\phi}) + (0 - \Gamma^{\phi}_{\phi\theta}\eta_{\phi}) \\
>&= 2r^{2}\sin\theta\cos\theta - 2\cot\theta\cdot r^{2}\sin^{2}\theta = 0
>\end{align}$$
>其余分量均为零。综上，$\partial_{t}$ 与 $\partial_{\phi}$ 均为 de Sitter 空间静态坐标下的 Killing 矢量场。

---
# 23 年

Consider the vacuum Einstein’s equation in four dimensional spacetime with a cosmo-logical constant
$$R_{\mu \nu} - \frac{1}{2}g_{\mu \nu}R + g_{\mu \nu}\Lambda = 0 $$
(a) Proof that $R_{\mu \nu} = kg_{\mu \nu}$ and find out the value of $k$.

>[!S]
>$$g^{\mu \nu}\left( R_{\mu \nu} - \frac{1}{2}g_{\mu \nu}R + g_{\mu \nu}\Lambda \right) = R - \frac{1}{2}\cdot 4R + 4\Lambda = 0 \implies R = 4\Lambda $$
>于是
>$$R_{\mu \nu} - \frac{1}{2}g_{\mu \nu}\cdot{4}\Lambda + g_{\mu \nu}\Lambda = 0 \implies R_{\mu \nu} = \Lambda g_{\mu \nu} $$
>所以 $k=\Lambda$

(b) Now start with an ansatz of a metric in the following form
$$ds^{2} = -f(r)dt^{2} + \frac{1}{f(r)}dr^{2} + r^{2}(d\theta^{2} + \sin^2\theta d\phi^{2}) $$
where $f(r)$ is a polynomial in $r$. Compute non zero components of the Ricci tensor $R_{\mu \nu}$ and scalar curvature $R$ of this metric.

>[!S]
>度规及其逆是
>$$g_{\mu \nu} = \begin{pmatrix}
-f(r) & 0 & 0 & 0 \\
0 & \frac{1}{f(r)} & 0 & 0 \\
0 & 0 & r^{2} & 0 \\
0 & 0 & 0 & r^{2}\sin^2\theta
\end{pmatrix} ,\quad g^{\mu \nu} = \begin{pmatrix}
-\frac{1}{f(r)} & 0 & 0 & 0 \\
0 & f(r) & 0 & 0 \\
0 & 0 & \frac{1}{r^{2}} & 0 \\
0 & 0 & 0 & \frac{1}{r^{2}\sin^2\theta}
\end{pmatrix} $$
>按照定义计算克里斯托菲斯符号
>$${\Gamma}_{\rho \mu \nu} = \frac{1}{2}(\partial_{\mu}g_{\rho \nu} + \partial_{\nu}g_{\rho \mu} - \partial_{\rho}g_{\mu \nu}) $$
>由于度规是对角的，且与 $t,\phi$ 无关所以计算
>$${\Gamma^{t}}_{tr} = \frac{1}{2}g^{tt}\partial_{r}g_{tt} = \frac{f'}{2f} $$
>由对称性 ${\Gamma^{t}}_{rt}=f' /2f$ 同理可得
>$$\begin{gather}
{\Gamma^{r}}_{tt} = \frac{1}{2}ff' ,\quad {\Gamma^{r}}_{rr} = -\frac{f'}{2f} ,\quad {\Gamma^{r}}_{\theta \theta} = -rf ,\quad {\Gamma^{r}}_{\phi \phi} = -rf\sin^2\theta  \\
{\Gamma^{\theta}}_{r\theta} = {\Gamma^{\theta}}_{\theta r} = \frac{1}{r} ,\quad {\Gamma^{\theta}}_{\phi \phi} = -\sin \theta \cos \theta ,\quad {\Gamma^{\phi}}_{r\phi} = {\Gamma^{\phi}}_{\phi r} = \frac{1}{r} ,\quad {\Gamma^{\phi}}_{\theta \phi} = {\Gamma^{\phi}}_{\phi \theta} = \cot \theta 
\end{gather} $$
>代入里奇张量定义
>$$R_{\mu \nu} = \partial_{\lambda}{\Gamma^{\lambda}}_{\mu \nu} - \partial_{\nu}{\Gamma^{\lambda}}_{\mu \lambda} + {\Gamma^{\lambda}}_{\lambda \sigma}{\Gamma^{\sigma}}_{\mu \nu} - {\Gamma^{\lambda}}_{\mu \sigma}{\Gamma^{\sigma}}_{\nu \lambda} $$
>计算得到
>$$\begin{gather}
R_{tt} = \frac{1}{2}ff'' + \frac{1}{r}ff' ,\quad R_{rr} = -\frac{f''}{2f} + \frac{f'}{rf} \\
R_{\theta \theta} = 1 - f - rf' ,\quad R_{\phi \phi} = (1-f-rf')\sin^2\theta
\end{gather} $$
>由此标量曲率为
>$$\begin{align}
R & = g^{\mu \nu}R_{\mu \nu}\\ & =-\left( \frac{1}{2}f'' + \frac{f'}{r} \right) + \left( -\frac{1}{2}f'' + \frac{f'}{r} \right) + \frac{1-f-rf'}{r^{2}} \\ & \quad + \frac{1-f-rf'}{r^{2}} \\ & =-f'' - \frac{4f'}{r} + \frac{2(1-f)}{r^{2}}
\end{align} $$

(c) Assuming that the above ansatz is a solution of the vacuum Einstein equation with cosmological constant $\Lambda$, solve $f(r)$.

>[!S]
>由 (a) 中的方程代入得到
>$$\begin{gather}
\frac{1}{2}ff'' + \frac{1}{r}ff' = -\Lambda f \\
-\frac{f''}{2f} + \frac{f'}{rf} = \frac{\Lambda}{f} \\
1-f-rf' = \Lambda r^{2} \\
(1-f-rf')\sin^2\theta = \Lambda r^{2}\sin^2\theta
\end{gather} $$
>整理得
>$$\begin{gather}
\frac{1}{2}rf'' + f' = -\Lambda \\
f + rf' = 1 - \Lambda r^{2}
\end{gather} $$
>解得
>$$f(r) = 1 - \frac{\Lambda}{3}r^{2} - \frac{2M}{r} $$
>其中 $M$ 是质量参数

(d) Prove that $\partial_{t}$ and $\partial_{\phi}$ are Killing vector fields.

>[!S]
>Killing 矢量场满足 Killing 方程
>$$\nabla_{\mu}\xi_{\nu} + \nabla_{\nu}\xi_{\mu} = 0 $$
>其中 $\nabla_{\mu}\xi_{\nu} = \partial_{\mu}\xi_{\nu} - {\Gamma^{\lambda}}_{\mu \nu}\xi_{\lambda}$ 先证明 $\xi^{\mu}=(\partial_{t})^{\mu}$ 是 Killing 矢量场，其在坐标基底下的分量是 $\xi^{\mu}=(1,0,0,0)$ 协变分量为 $\xi_{\mu}=(-f,0,0,0)$ 于是只有 $\xi_{t}\neq 0$ 所以秩序计算取 $\lambda=t$ 而 $\nu$ 取遍四个指标。
>$$\begin{align}
\nabla_{\mu}\xi_{\nu} + \nabla_{\nu}\xi_{\mu} & = \nabla_{t}\xi_{\nu} + \nabla_{\nu}\xi_{t} \\ & = (\partial_{t}\xi_{\nu} - \Gamma^{\mu}_{t\nu}\xi_{\mu}) + (\partial_{\nu}\xi_{t} - \Gamma^{\mu}_{\nu t}\xi_{\mu}) \\ & = (0 - \Gamma^{t}_{t\nu}\xi_{t}) + (\partial_{\nu}\xi_{t} - \Gamma^{t}_{\nu t}\xi_{t}) \\ & = -\frac{f'}{2f}f + f' - \frac{f'}{2f}f \\ & = 0
\end{align} $$
>再验证 $\xi^{\mu}=(\partial_{\phi})^{\mu}$ 其再坐标基底下的分量是 $\xi^{\mu}=(0,0,0,1)$ 协变分量是 $\xi_{\mu}=(0,0,0,r^{2}\sin^2\theta)$ 于是
>$$\begin{align}
\nabla_{\mu}\xi_{\nu} + \nabla_{\nu}\xi_{\mu} & = \nabla_{\phi}\xi_{\nu} + \nabla_{\nu}\xi_{\phi} \\ & =(\partial_{\phi}\xi_{\nu}-\Gamma^{\mu}_{\phi \nu}\xi_{\mu}) + (\partial_{\nu}\xi_{\phi} - \Gamma^{\mu}_{\nu \phi}\xi_{\mu}) \\ & = (0 - \Gamma^{\phi}_{\phi r}\xi_{\phi} - \Gamma^{\phi}_{\phi \theta}\xi_{\phi}) + (\partial_{r}\xi_{\phi} + \partial_{\theta}\xi_{\phi} - \Gamma^{\phi}_{\phi r}\xi_{\phi} - \Gamma^{\phi}_{\phi \theta}\xi_{\phi}) \\ & = -2\left( \frac{1}{r} + \cot \theta \right) r^{2}\sin^2\theta + 2r\sin^2\theta + 2r^{2}\sin \theta \cos \theta \\ & = 0
\end{align} $$
>所以 $\partial_{t}$ 和 $\partial_{\phi}$ 是killing矢量场


---

# 22 年

A Killing vector field $k^{\mu}\frac{\partial }{\partial x^{\mu}}$ satisfies the equation $k^{\lambda}\partial_{\lambda}g_{\mu \nu} + \partial_{\mu}k^{\lambda}g_{\lambda \nu}+\partial_{\nu}k^{\lambda}g_{\mu \lambda}=0$ 

(a) Prove: $D_{\mu}k_{\nu} + D_{\nu}k_{\mu} = 0$, here $D_{\mu}$ is the covariant derivative.

>[!S]-
>$$D_{\mu}k_{\nu} + D_{\nu}k_{\mu} = \partial_{\mu}k_{\nu} + \partial_{\nu}k_{\mu} - (\Gamma^{\lambda}_{\mu \nu} + \Gamma^{\lambda}_{\nu \mu})k_{\lambda} $$
>where
>$$\partial_{\mu}k_{\nu} = \partial_{\mu}(g_{\lambda \nu}k^{\lambda}) = k^{\lambda}\partial_{\mu}g_{\nu \lambda} + g_{\lambda \nu}\partial_{\mu}k^{\lambda} $$
>$$\Gamma^{\lambda}_{\mu \nu} = \frac{1}{2}g^{\lambda \sigma}(\partial_{\mu}g_{\sigma \nu} + \partial_{\nu}g_{\sigma \mu} - \partial_{\sigma}g_{\mu \nu}) $$
>$$\begin{align}D_{\mu}k_{\nu} + D_{\nu}k_{\mu} & = (\partial_{\mu}g_{\nu \rho} + \partial_{\nu}g_{\mu \rho})k^{\rho} + g_{\nu \rho}\partial_{\mu}k^{\rho} + g_{\mu \rho}\partial_{\nu}k^{\rho} - (\Gamma^{\lambda}_{\mu \nu} + \Gamma^{\lambda}_{\nu \mu})k_{\lambda} \\ & = (\partial_{\mu}g_{\nu \rho} + \partial_{\nu}g_{\mu \rho})k^{\rho} + g_{\nu \rho}\partial_{\mu}k^{\rho} + g_{\mu \rho}\partial_{\nu}k^{\rho} - k^{\rho}(\partial_{\mu}g_{\rho \nu} + \partial_{\nu}g_{\rho \mu}-\partial_{\rho}g_{\mu \nu}) \\ & = k^{\rho}\partial_{\rho}g_{\mu \nu} + g_{\rho \nu}\partial_{\mu }k^{\rho} + g_{\rho \mu}\partial_{\nu}k^{\rho}\end{align}$$
>As the killing equation said $k^{\lambda}\partial_{\lambda}g_{\mu \nu} + \partial_{\mu}k^{\lambda}g_{\lambda \nu}+\partial_{\nu}k^{\lambda}g_{\mu \lambda}=0$ so taht
>$$D_{\mu}k_{\nu} + D_{\nu}k_{\mu} = 0 $$
>

(b) For a moving particle in gravitational background with a Killing vector field, Prove: $k _{\mu}P^{\mu}$ is a conserved quantity, Here $P_{\mu} = m \frac{dx^{\nu}}{d\tau}g_{\mu \nu}$ is the momentum for the free falling particle with trajectory $x^{\nu}(\tau)$.

>[!S]-
>$$\frac{DP^{\mu}}{d\tau} = \frac{dP^{\mu}}{d\tau} + \Gamma^{\mu}_{\nu \rho}P^{\nu}u^{\rho} = 0 $$
>$$\begin{align}\frac{d}{d\tau}(k_{\mu}P^{\mu}) & = \frac{dk_{\mu}}{d\tau}P^{\mu} + k_{\mu} \frac{dP^{\mu}}{d\tau} = (\partial_{\nu}k_{\mu})u^{\nu}P^{\mu} + k_{\mu}( -\Gamma^{\mu}_{\nu \rho}P^{\nu}u^{\rho} ) \\ & = u^{\nu}P^{\mu}\partial_{\nu}k_{\mu}- \Gamma^{\mu}_{\nu \rho}k_{\mu}P^{\nu}u^{\rho} \\ & = u^{\nu}P^{\mu}(\nabla_{\nu}k_{\mu} + \Gamma_{\mu \nu}^{\rho}k_{\rho}) - \Gamma^{\mu}_{\nu \rho}k_{\mu}P^{\nu}u^{\rho} \\ & = u^{\nu}P^{\mu}\nabla_{\nu}k_{\mu} + \Gamma^{\rho}_{\mu \nu}k_{\rho}u^{\nu}P^{\mu} - \Gamma^{\rho}_{\mu \nu} k_{\rho}P^{\mu}u^{\nu} \\ & = u^{\nu}P^{\mu}\nabla_{\nu}k_{\mu} \\ & = m u^{\mu}u^{\nu}\nabla_{\nu}k_{\mu} \end{align} $$
>Similarly
>$$\frac{d}{d\tau}(k_{\mu}P^{\mu}) = mu^{\nu}u^{\mu}\nabla_{\mu}k_{\nu} $$
>$$2 \frac{d}{d\tau}(k_{\mu}P^{\mu}) = m u^{\mu}u^{\nu}(\nabla_{\nu}k_{\mu}+\nabla_{\mu}k_{\nu}) = 0 $$
>So $k _{\mu}P^{\mu}$ is a conserved quantity
>

---

# 22 年

Consider following metric
$$ds^{2} = -\left( 1-\frac{2M}{r} \right)dv^{2} + dr dv + r^{2}d\Omega^{2} $$
Here $d\Omega^{2}$ is the standard metric on two sphere. Consider the hypersurface defined by $S = r − 2M = 0$, and a vector field $l = \tilde{f}(x)(g^{\mu \nu}\partial_{\nu}S)\frac{\partial }{\partial x^{\mu}}$, here $\tilde{f}(x)$ is a non-zero function. Prove:

(a) $l$ is normal to the surface $S$.

>[!S?]-
>$$\partial_{\mu}S = \delta^{r}_{\mu} \implies g^{\mu \nu}\partial_{\nu}S = g^{\mu r} \implies l = \tilde{f}(x)\partial^{r} $$

(b) $l^{2} = 0$ on the surface $S$.

>[!S]-
>$$l^{2} = \tilde{f}^{2}(x)g_{\mu \nu}g^{\mu r}g^{\nu r}\partial^{r}\partial^{r} = \tilde{f}^{2}(x)g^{rr}\partial^{r}\partial^{r} $$
>where
>$$g^{rr} = 4\left( 1-\frac{2M}{r} \right) $$
>on the surface S, $r-2M=0$ thus $g^{rr}=0$ so
>$$l^{2} = 0 $$

(c) $\frac{\partial }{\partial v}$ is a Killing vector field.

>[!S]-
>Absolutly $g_{\mu \nu}$ only have non-zero compoment
>$$g_{vv} = -\left( 1-\frac{2M}{r} \right),\quad g_{rv}=g_{vr} = \frac{1}{2} ,\quad g_{(\Omega)}=r^{2} $$
>all of them are independ with $v$ , so
>$$\frac{\partial }{\partial v}g_{\mu \nu} = 0 $$
>satisified killing equation, so the $\frac{\partial }{\partial v}$ is a killing vector field.