---
up:
  - "[[写题]]"
related:
date: 2026-04-18
---

# 习题 7.1

通过考虑占有数 $\langle n_\epsilon \rangle$ 的数量级，试证明：如果我们将求和式 **(7.1.2)** $$N = \sum_{\varepsilon} \langle n_\varepsilon \rangle = \sum_{\varepsilon} \frac{1}{z^{-1}e^{\beta\varepsilon} - 1}$$ 中有限个 ($\epsilon \neq 0$) 的项与 **(7.1.6)** 式中的基态项部分 $$\frac{1}{V} \frac{z}{1-z}$$ （注：该式源自 $\frac{N}{V} = \frac{2\pi}{h^3}(2m)^{3/2} \int_{0}^{\infty} \frac{\varepsilon^{1/2} d\varepsilon}{z^{-1}e^{\beta\varepsilon} - 1} + \frac{1}{V} \frac{z}{1-z}$）合并，或是将这些项包括到对 $\epsilon$ 的积分中，两种做法不会造成 7.1 节最终结果的差异。

>[!S]
>总粒子数是
>$$N = N_{0} + \sum \braket{ n_{\varepsilon} }  $$
>其中
>$$N_{0} = \frac{z}{1-z} ,\quad \braket{ n_{\varepsilon} } = \frac{1}{z^{-1}e^{ \beta\varepsilon } - 1} $$
>在 $z=1$ 的BEC极限下 $N_{0}=\mathcal{O}(N)$ $\frac{N_{0}}{V}=\mathcal{O}(1)$ 而 $N_{e}=\int_{0}^{\infty}g(\varepsilon)d\varepsilon=\int_{0}^{\infty}V\sqrt{ \varepsilon }d\varepsilon=\mathcal{O}(V)$ 于是 $\frac{N_{e}}{V}=\mathcal{O}(1)$ 二者的量级一样。现在考虑有限个特定的低激发态能级 $\varepsilon_1, \varepsilon_2, \dots, \varepsilon_k \neq 0$。对于任意固定的 $\varepsilon_i \neq 0$，即使在凝聚发生时 $z \to 1$，其占有数 $\langle n_{\varepsilon_i} \rangle$ 仍然是一有限值
>
>当 $\varepsilon_i > 0$ 且 $\beta \varepsilon_i \ll 1$ 时，$\langle n_{\varepsilon_i} \rangle \approx \frac{1}{z^{-1}(1+\beta \varepsilon_i) - 1} \approx \frac{1}{\beta \varepsilon_i}$，这是一个与系统尺寸 $V$ 无关的 $O(1)$ 量；若 $\varepsilon_i$ 较大，$\langle n_{\varepsilon_i} \rangle$ 随指数衰减，更是 $O(1)$ 或更小。
>
>因此，这有限个项的总和为
>$$\sum \braket{ n_{e} } = \mathcal{O}(1) ,\quad \frac{1}{V}\sum \braket{ n_{e} }  = \mathcal{O}\left( \frac{1}{V} \right) \to 0 $$
>将这有限个 $O(1)$ 的项与基态项 $\frac{z}{1-z}$（$O(V)$ 量级）合并。由于 $O(1) \ll O(V)$，在计算密度 $\frac{N}{V}$ 并取热力学极限时，这些项的贡献为 $O(1/V)$，趋于零，不会改变基态密度的极限值；将这些项包含在激发态的积分 $\int g(\varepsilon) \langle n_\varepsilon \rangle d\varepsilon$ 中。积分的量级为 $O(V)$，有限个能级的离散求和修正相对于连续积分是 $O(1)$ 的误差。在除以 $V$ 后，这个误差对密度的贡献也是 $O(1/V) \to 0$ 
>
>所以无论是将这些项合并道基态，还是包含到积分中都不会对结果产生影响。

# 习题 7.2

试从 **(7.1.7)** 和 **(7.1.8)** 式： $$\frac{P}{kT} = \frac{1}{\lambda^3} g_{5/2}(z) \quad \text{和} \quad \frac{N}{V} = \frac{1}{\lambda^3} g_{3/2}(z)$$ 推导出位力展开式 **(7.1.13)**： $$\frac{Pv}{kT} = \sum_{l=1}^{\infty} a_l \left(\frac{\lambda^3}{v}\right)^{l-1}$$ 并验证书中所引用的位力系数 $a_l$ 的具体数值。

>[!S]
>由这两个式子知道
>$$\frac{Pv}{kT} = \frac{g_{\frac{5}{2}}(z)}{g_{\frac{3}{2}}(z)}  $$
>欲使它等于 $\displaystyle\sum_{l=1}^{\infty}a_{l}\left( \frac{\lambda^{3}}{v} \right)^{l-1}=\sum_{l=1}^{\infty}a_{l}\left( g_{\frac{3}{2}}(z) \right)^{l-1}$ 则就是把右边按照 $g_{\frac{3}{2}}(z)$ 的幂级数展开，为此将 $z$ 按 $g_{\frac{3}{2}}$ 反演展开
>$$x = g_{\frac{3}{2}}(z) = z + 2^{-3/2}z^{2} + 3^{-3/2}z^{3} + 4^{-3/2}z^{4} + \dots $$
>设 $z=x+c_{2}x^{2}+\dots$ 则
>$$\begin{gather} 1 = 1 & x_{1} \\  0 = c_{2} + 2^{-3/2} & x_{2} \\ 0 = c_{3} + 2\cdot 2^{-3/2}c_{2} - 3^{-3/2}c_{1} & x_{3} \\ 0 = c_{4} + 2^{-3/2}(c_{2}^{2} + 2c_{3}) + 3\cdot 3^{-3/2}c_{2} + 4^{-3/2} & x_{4} \\ \dots \end{gather} $$
>$$c_{2} = -2^{-3/2} ,\quad c_{3} = \frac{1}{4} - \frac{1}{3\sqrt{ 3 }} ,\quad c_{4} = 0.083 ,\quad \dots $$
>以及
>$$\begin{align} g_{\frac{5}{2}}(z) & = z + 2^{-5/2}z^{2} + 3^{-5/2}z^{3} + 4^{-5/2}z^{4} + \dots \\ & = x + (c_{2} + 2^{-5/2})x^{2} + (c_{3} + 2\cdot 2^{-5/2}c_{2} + 3^{-5/2})x^{3} + \dots \end{align} $$
>于是
>$$\frac{Pv}{kT} = \frac{g_{\frac{5}{2}}(z)}{x} = 1 + (c_{2} + 2^{-5/2})x + (c_{3} + 2\cdot 2^{-5/2}c_{2} + 3^{-5/2})x^{2} + \dots  $$
>所以位力系数是
>$$a_{1} = 1 ,\quad a_{2} = \frac{1}{8} - \frac{2}{9\sqrt{ 3 }} ,\quad a_{3} = 0.0001 ,\quad \dots $$
>

# 习题 7.3

比较 **(7.1.24)** 式 $$T_c = \frac{h^2}{2\pi mk} \left( \frac{N}{V \zeta(3/2)} \right)^{2/3}$$ 和 **(7.1.26)** 式 $$g_{3/2}(z) = \frac{\lambda^3}{v} = \zeta(3/2) \left( \frac{T_c}{T} \right)^{3/2}$$ 并利用附录 D 中 (D.9) 式的头两项，试证明：当 $T$ 从上方趋近临界温度 $T_c$ 时，理想玻色气体的参量 $\alpha (= -\ln z)$ 可采用如下渐近形式： $$\alpha \simeq \frac{1}{\pi} \left[ \frac{\zeta(3/2)}{2} \right]^2 \left( \frac{T - T_c}{T_c} \right)^2 \quad$$

>[!S]
>取前两项
>$$g_{\frac{3}{2}}(e^{ -\alpha }) = \zeta\left( \frac{3}{2} \right) - 2\sqrt{ \pi \alpha } + \mathcal{O}(\alpha^{2}) = \zeta\left( \frac{3}{2} \right)\left( \frac{T_{c}}{T} \right)^{3/2} \simeq \zeta\left( \frac{3}{2} \right)\left( 1- \frac{3}{2} \frac{T-T_{c}}{T_{c}} \right) $$
>于是
>$$\alpha \simeq \frac{9}{16\pi}\zeta^{2}\left( \frac{3}{2} \right)\left( \frac{T-T_{c}}{T_{c}} \right)^{2} $$
>

# 习题 7.4

试证明：对于理想玻色气体，有 $$\left( \frac{\partial z}{\partial T} \right)_P = -\frac{5 g_{5/2}(z)}{2T g_{3/2}(z)}$$ 将这个结果与 **(7.1.36)** 式： $$\left( \frac{\partial z}{\partial T} \right)_V = -\frac{3 g_{3/2}(z)}{2T g_{1/2}(z)}$$ 进行比较。然后证明： $$\gamma \equiv \frac{C_P}{C_V} = \frac{(\partial z / \partial T)_P}{(\partial z / \partial T)_V} = \frac{5}{3} \frac{g_{5/2}(z) g_{1/2}(z)}{{g_{3/2}(z)}^2}$$ 并验证它与 **(7.1.48b)** 式： $$\gamma = \frac{C_P}{C_V} = \frac{5}{3} \frac{g_{5/2}(z) g_{1/2}(z)}{{g_{3/2}(z)}^2}$$ 一致。并检验当 $T$ 从上方趋近 $T_c$ 时，$\gamma$ 和 $C_P$ 两者是否都如 $(T - T_c)^{-1}$ 那样发散。

>[!S]
>对于理想玻色气体
>$$\frac{P}{kT} = \frac{1}{\lambda^3} g_{5/2}(z) \implies \frac{P}{k} = \frac{T}{\lambda^{3}}g_{\frac{5}{2}}(z) \propto T^{5/2}g_{\frac{5}{2}}(z) $$
>于是
>$$0 = \frac{5}{2}T^{3/2}g_{\frac{5}{2}}(z) + T^{5/2}g'_{\frac{5}{2}}(z)\left( \frac{\partial z}{\partial T} \right)_{P} $$
>而 $g'_{\nu}(z)=\frac{1}{z}g_{\nu-1}(z)$ 故
>$$\left( \frac{\partial z}{\partial T} \right)_{P} = -\frac{5z}{2T} \frac{g_{\frac{5}{2}}(z)}{g_{\frac{3}{2}}(z)} $$
>在BEC极限下 $z\to 1$ 故
>$$\left( \frac{\partial z}{\partial T} \right)_P = -\frac{5 g_{5/2}(z)}{2T g_{3/2}(z)} $$
>对于热容，考虑到玻色气体在凝聚前仅为 $z$ 的函数所以
>$$
C_{P} = \left( \frac{\partial H}{\partial T} \right)_{P} = T\left( \frac{\partial S}{\partial T} \right)_{P} = T\left( \frac{\partial S}{\partial z} \right)_{N}\left( \frac{\partial z}{\partial T} \right)_{P} $$
>同理 $C_{V}=T\left( \frac{\partial S}{\partial z} \right)_{N}\left( \frac{\partial z}{\partial T} \right)_{V}$ 所以
>$$\gamma \equiv \frac{C_{P}}{C_{V}} = \frac{\left( \frac{\partial z}{\partial T} \right)_{P}}{\left( \frac{\partial z}{\partial T} \right)_{V}} =\frac{5g_{\frac{5}{2}}(z)}{2Tg_{\frac{3}{2}}(z)}\cdot \frac{2Tg_{\frac{1}{2}}(z)}{3g_{\frac{3}{2}}(z)} = \frac{5g_{\frac{5}{2}}(z)g_{\frac{1}{2}}(z)}{3\left( g_{\frac{3}{2}}(z) \right)^{2}} $$
>在 $T\to T_{c}^{-}$ 时 $z\to 1$ 设 $z=e^{ -\alpha }$ 则
>$$g_{\frac{1}{2}}(z) \simeq \zeta\left( \frac{1}{2} \right) + \sqrt{ \frac{\pi}{\alpha} } + \mathcal{O}\left( \sqrt{ \alpha } \right) \sim \sqrt{ \frac{\pi}{\alpha} } \propto \frac{1}{T-T_{c}} $$
>$$g_{\frac{3}{2}}(1) = \zeta\left( \frac{3}{2} \right) ,\quad g_{\frac{5}{2}}(1) = \zeta\left( \frac{5}{2} \right) \quad \text{均不发散} $$
>于是
>$$C_{P} \propto (T-T_{c})^{-1} ,\quad \gamma \propto (T-T_{c})^{-1} $$
>
>

# 习题 7.5

(a) 试证明：理想玻色气体的等温压缩率 $\kappa_T$ 和绝热压缩率 $\kappa_S$ 分别为： $$\kappa_T = \frac{1}{nkT} \frac{g_{1/2}(z)}{g_{3/2}(z)}, \quad \kappa_S = \frac{3}{5nkT} \frac{g_{3/2}(z)}{g_{5/2}(z)}$$ 其中 $n(= N/V)$ 是气体中的粒子密度。注意到当 $z \to 0$ 时，$\kappa_T$ 和 $\kappa_S$ 趋近于它们各自的经典值（即 $1/P$ 和 $1/\gamma P$）。当 $z \to 1$ 时它们的行为如何？ (b) 利用热力学关系 $C_P - C_V = TV \kappa_T (\partial P / \partial T)_V^2$ 和 $C_P / C_V = \kappa_T / \kappa_S$，试导出 **(7.1.48a)** 式 $$\frac{C_P}{Nk} = \frac{25}{4} \frac{g_{5/2}^2(z)}{g_{3/2}(z)g_{1/2}(z)} - \frac{9}{4} \frac{g_{3/2}(z)}{g_{1/2}(z)}$$ 和 **(7.1.48b)** 式 $$\gamma = \frac{5}{3} \frac{g_{5/2}(z) g_{1/2}(z)}{{g_{3/2}(z)}^2} \quad$$

>[!S]
>(a)
>按照定义
>$$\kappa_{T} = -\frac{1}{v}\left( \frac{\partial v}{\partial P} \right)_{T} ,\quad \kappa_{S} = \frac{1}{v}\left( \frac{\partial v}{\partial P} \right)_{S}  $$
>理想玻色气体的状态方程是
>$$\frac{P}{kT} = \frac{1}{\lambda^3} g_{5/2}(z) \quad \text{和} \quad \frac{N}{V} = \frac{1}{\lambda^3} g_{3/2}(z) $$
>于是
>$$\kappa_{T} = -\frac{1}{v}\left( \frac{\partial v}{\partial P} \right)_{T,N} = \frac{1}{n}\left( \frac{\partial n}{\partial P} \right)_{T,N} =\frac{1}{n}\left( \frac{\partial P}{\partial n} \right)_{T,N}^{-1} $$
>$$\left( \frac{\partial P}{\partial n} \right)_{T,N} = \left( \frac{\partial P}{\partial \mu} \right)_{T,N}\left( \frac{\partial \mu}{\partial n} \right)_{T,N} = n\left( \frac{\partial \mu}{\partial n} \right)_{T,N} = n\left( \frac{\partial n}{\partial \mu} \right)^{-1} = \frac{n\lambda^{3}kT}{g'_{\frac{3}{2}}(z)} $$
>$$\kappa_{T} = \frac{1}{n} \frac{g'_{\frac{3}{2}}(z)}{n\lambda^{3}kT} = \frac{1}{n} \frac{g_{\frac{1}{2}}(z)}{z} \frac{1}{g_{\frac{3}{2}}(z)kT} = \frac{1}{nkTz} \frac{g_{\frac{1}{2}}(z)}{g_{\frac{3}{2}}(z)} $$
>最后取 $z\to 1$ 的极限即可，另一方面单玻色气体粒子的熵为
>$$S = \frac{5}{2}k \frac{g_{\frac{5}{2}}(z)}{g_{\frac{3}{2}}(z)} - k\ln z $$
>可见等熵时逸度保持不变，此时
>$$n \propto T^{3/2} ,\quad P \propto T^{5/2} \implies P \propto n^{5/3} $$
>$$\kappa_{S} = \frac{1}{n} \left( \frac{\partial n}{\partial P} \right)_{S,N} = \frac{3}{5P} = \frac{3}{5nkT} \frac{g_{3/2}(z)}{g_{5/2}(z)} $$
>当 $z\to 1$ 时
>$$\kappa_{T} = \frac{1}{nkT} \frac{\zeta(1 /2)}{\zeta(3 /2)},\quad \kappa_{S} = \frac{3}{5nkT} \frac{\zeta(3 /2)}{\zeta(5 /2)} $$
>(b)
>$$\gamma = \frac{\kappa_{T}}{\kappa_{S}} = \frac{5}{3} \frac{g_{5 /2}(z)g_{1 /2}(z)}{(g_{3 /2}(z))^{2}} $$
>由
>$$\frac{P}{kT} = \frac{1}{\lambda^3} g_{5/2}(z) \quad \text{和} \quad \frac{N}{V} = \frac{1}{\lambda^3} g_{3/2}(z) $$
>得到
>$$P = nkT \frac{g_{5 /2}(z)}{g_{3 /2}(z)} $$
>$$\left( \frac{\partial z}{\partial T} \right)_{V} = -\frac{3}{2} \frac{zg_{3 /2}(z)}{Tg_{1 /2}(z)} $$
>$$\left( \frac{\partial P}{\partial T} \right)_{V} = nk\left[  \frac{5}{2} \frac{g_{5 /2}(z)}{g_{3 /2}(z)} - \frac{3}{2} \frac{g_{3 /2}(z)}{g_{1 /2}(z)}  \right] $$
>$$C_{P}-C_{V}=TV\kappa_{T}\left( \frac{\partial P}{\partial T} \right)_{V}^{2} = Nk\left[  \frac{25}{4} \frac{g_{1 /2}(z)g_{5 /2}^{2}(z)}{g_{3 /2}^{2}(z)} - \frac{15}{2} \frac{g_{5 /2}(z)}{g_{3 /2}(z)} + \frac{9}{4} \frac{g_{3 /2}(z)}{g_{1 /2}(z)} \right] $$
>所以
>$$C_{P} = \frac{\gamma}{\gamma-1}(C_{P}-C_{V}) = Nk \left[ \frac{25}{4} \frac{g_{5/2}^2(z)}{g_{3/2}(z)g_{1/2}(z)} - \frac{9}{4} \frac{g_{3/2}(z)}{g_{1/2}(z)} \right] $$

# 习题 7.6

试证明：对于理想玻色气体，比热 $C_V$ 对温度的导数由下式给出： $$\frac{1}{N k_B} \left( \frac{\partial C_V}{\partial T} \right)_V = \begin{cases} \frac{1}{T} \left( \frac{45 g_{5/2}(z)}{8 g_{3/2}(z)} - \frac{9 g_{3/2}(z)}{4 g_{1/2}(z)} - \frac{27 g_{3/2}(z) g_{-1/2}(z)}{8 {g_{1/2}(z)}^2} \right) & (T > T_c) \\ \frac{45}{4 T_c} \frac{v}{T\lambda^{3}}\zeta\left( \frac{5}{2} \right) & (T < T_c) \end{cases}$$ 利用这个结果和 (D.9) 式，验证 **(7.1.38)** 式关于比热导数不连续性的结论： $$\left( \frac{\partial C_V}{\partial T} \right)_{T=T_c-0} - \left( \frac{\partial C_V}{\partial T} \right)_{T=T_c+0} = \frac{9 Nk}{4 T_c} \frac{[\zeta(3/2)]^2}{\zeta(1/2)} \approx 3.665 \frac{Nk}{T_c} \quad$$

>[!S]
>由上可知
>$$C_{V} = \frac{C_{P} - C_{V}}{\gamma-1} = Nk\left[  \frac{15}{4} \frac{g_{5 /2}(z)}{g_{3 /2}(z)} - \frac{9}{4} \frac{g_{3 /2}(z)}{g_{1 /2}(z)}  \right] ,\quad \left( \frac{\partial z}{\partial T} \right)_{V} = -\frac{3}{2} \frac{zg_{3 /2}(z)}{Tg_{1 /2}(z)}  $$
>于是
>$$\left( \frac{\partial g_{\nu}(z)}{\partial T} \right)_{V} = \frac{g_{\nu-1}(z)}{z} \left( \frac{\partial z}{\partial T} \right)_{V} = -\frac{g_{\nu-1}(z)}{T} \frac{3}{2} \frac{g_{3 /2}(z)}{g_{1 /2}(z)} $$
>所以
>$$ \begin{align}\frac{1}{Nk} \left( \frac{\partial C_{V}}{\partial T} \right)_{V} & = \frac{15}{4} \frac{1}{g_{3 /2}^{2}(z)}\left(  - \frac{3g_{3 /2}(z)g_{3 /2}(z)g_{3 /2}(z)}{2Tg_{1 /2}(z)} + \frac{3g_{5 /2}(z)g_{3 /2}(z)g_{1 /2}(z)}{2Tg_{1 /2}(z)} \right) \\ & \quad -\frac{9}{4} \frac{1}{g_{1 /2}^{2}(z)}\left(  -\frac{3g_{1 /2}(z)g_{3 /2}(z)g_{1 /2}(z)}{2Tg_{1 /2}(z)} + \frac{3g_{3 /2}(z)g_{-1 /2}(z)g_{3 /2}(z)}{2Tg_{1 /2}(z)}  \right) \\ & = \frac{1}{T}\left[  \frac{45}{8} \frac{g_{5 /2}}{g_{3 /2}} - \frac{9}{4} \frac{g_{3 /2}}{g_{1 /2}} - \frac{27}{8} \frac{g_{3 /2}^{2}g_{-1 /2}}{g_{1 /2}^{3}} \right] \end{align} $$
>在BEC发生时 $z=1$ 代入得
>$$\frac{C_{V}}{Nk} = \frac{15}{4} \frac{\zeta(5 /2)}{\zeta(3 /2)}\left( \frac{T}{T_{c}} \right)^{3/2}  $$
>$$\frac{1}{Nk}\left( \frac{\partial C_{V}}{\partial T} \right)_{V} = \frac{45}{8T_{c}} \frac{\zeta(5 /2)}{\zeta(3 /2)}\left( \frac{T}{T_{c}} \right)^{1/2} $$
>于是
>$$\left( \frac{\partial C_V}{\partial T} \right)_{T=T_c-0} - \left( \frac{\partial C_V}{\partial T} \right)_{T=T_c+0} = \frac{9 Nk}{4 T_c} \frac{[\zeta(3/2)]^2}{\zeta(1/2)} \approx 3.665 \frac{Nk}{T_c} \quad $$
>




# 习题 7.7

试估算理想玻色气体的 $(\partial^2 P/\partial T^2)_V$、$(\partial C_V/\partial T)_V$ 和 $(\partial^2 \mu/\partial T^2)_P$ 这些量，并检验你的结果符合热力学关系： $$C_V = VT \left( \frac{\partial^2 P}{\partial T^2} \right)_V - NT \left( \frac{\partial^2 \mu}{\partial T^2} \right)_V \quad \text{和} \quad C_P = -NT \left( \frac{\partial^2 \mu}{\partial T^2} \right)_P$$ 考查当 $T$ 从上方和下方趋近 $T_c$ 时这些量的行为特性。

>[!S]
>$$\left( \frac{\partial P}{\partial T} \right)_{V} = s = \frac{15}{4T^{2}} \frac{P}{T} - nk\ln z $$
>当 $T>T_{c}$ 时
>$$\frac{1}{nk} \frac{\partial^{2}P}{\partial T^{2}} = \frac{15}{4T^{2}} \frac{g_{5 /2}}{g_{3 /2}} - \frac{5}{2T^{2}}\ln z + \frac{3}{T^{2}}\frac{g_{3 /2}}{g_{1 /2}} $$
>当 $T<T_{c}$ 时
>$$\frac{1}{nk}\frac{\partial^{2}P}{\partial T^{2}} = \frac{15}{4T^{2}} \frac{\zeta(5 /2)}{\zeta(3 /2)} $$
>热容见上，当 $T>T_{c}$ 时
>$$\begin{align}\frac{1}{Nk} \left( \frac{\partial C_{V}}{\partial T} \right)_{V} = \frac{1}{T}\left[  \frac{45}{8} \frac{g_{5 /2}}{g_{3 /2}} - \frac{9}{4} \frac{g_{3 /2}}{g_{1 /2}} - \frac{27}{8} \frac{g_{3 /2}^{2}g_{-1 /2}}{g_{1 /2}^{3}} \right] \end{align}$$
>当 $T<T_{c}$ 时
>$$\frac{C_{V}}{Nk} = \frac{15}{4} \frac{\zeta(5 /2)}{\zeta(3 /2)}\left( \frac{T}{T_{c}} \right)^{3/2}$$
>由 $(\partial \mu/\partial T)_P = -S/N = -s$ 及 $C_P = T (\partial S/\partial T)_P$，得
>$$\left( \frac{\partial^{2}\mu}{\partial T^{2}} \right)_{P} = - \frac{C_{P}}{Nk} $$
>热容见上，于是当 $T>T_{c}$ 时
>$$\left( \frac{\partial^{2}\mu}{\partial T^{2}} \right)_P = -\frac{k}{T}\left(\frac{25}{4} \frac{g_{5/2}^2 g_{1/2}}{g_{3/2}^3} - \frac{15}{4} \frac{g_{5/2}}{g_{3/2}}\right) $$
>当 $T<T_{c}$ 时 $\mu \equiv 0$

# 习题 7.8

在流体中声速为 $w = \sqrt{(\partial P/\partial \rho)_S}$，其中 $\rho$ 是流体的质量密度。对于理想玻色气体，试证明： $$w^2 = \frac{5kT}{3m} \frac{g_{5/2}(z)}{g_{3/2}(z)} = \frac{5}{9} \langle u^2 \rangle$$ 其中 $\langle u^2 \rangle$ 是气体中粒子的方均速率。 （注：推导中需利用公式 **(6.4.3)**：$P = \frac{1}{3} n \langle pu \rangle = \frac{2}{3} \frac{U}{V}$）

>[!S]
>对于理想玻色气体，$$\frac{P}{kT} = \frac{1}{\lambda^3} g_{5/2}(z) \quad \text{和} \quad \frac{N}{V} = \frac{1}{\lambda^3} g_{3/2}(z) $$
>等熵时 $z$ 是常数，故
>$$\frac{1}{v} \propto T^{3/2} ,\quad P \propto T^{5/2}\implies P \propto v^{-5/3} \implies P\propto \rho^{5/3} $$
>$$w^{2} = \left( \frac{\partial P}{\partial v} \right)_{S} = \frac{5P}{3\rho} $$
>而由 6.4.3 知 $P=\frac{1}{3}n\braket{ p u }= \frac{2}{3} \frac{U}{V}$ 对于非相对论气体 $p=m u$ 故 $P=\frac{1}{3}mn\braket{ u^{2} }=\frac{1}{3}\rho \braket{ u^{2} }$ 所以
>$$w^{2} = \frac{5}{9}\braket{ u^{2} }  $$ 

# 习题 7.9

试证明：对于理想玻色气体，有： $$\braket{ u } \braket{ \frac{1}{u} } =\frac{4}{\pi} \frac{g_{1}(z)g_{2}(z)}{[g_{3 /2}(z)]^{2}}$$ 其中 $u$ 是一个粒子的速率。请考查并诠释极限情形 $z \to 0$ 和 $z \to 1$，并与 **习题 6.6** 中关于分子速率任何分布律都满足的不等式 ${\langle u \rangle \langle 1/u \rangle} \geq 1$ 进行比较。

>[!S]
>对于理想玻色气体，速率就是能量
>$$\braket{ u } = \sqrt{ \frac{2}{m} }\braket{ \varepsilon^{1/2} } ,\quad \braket{ u^{-1} } = \sqrt{ \frac{m}{2} }\braket{ \varepsilon^{-1/2} }   $$
>其中
>$$\braket{ \varepsilon^{1/2} } = \frac{1}{Z}\int_{0}^{\infty} \frac{\varepsilon^{1/2}}{z^{-1}e^{ \beta\varepsilon }-1}d\varepsilon = \sqrt{ kT } \frac{\Gamma(2)g_{2}(z)}{\Gamma\left( \frac{3}{2} \right)g_{3 /2}(z)} $$
>$$\braket{ \varepsilon^{-1/2} } = \frac{1}{Z}\int_{0}^{\infty} \frac{\varepsilon^{-1/2}}{z^{-1}e^{ \beta\varepsilon }-1}d\varepsilon = \frac{1}{\sqrt{ kT }} \frac{\Gamma(1)g_{1}(z)}{\Gamma\left( \frac{3}{2} \right)g_{3 /2}(z)} $$
>于是
>$$\braket{ u } \braket{ \frac{1}{u} } = \braket{ \varepsilon^{1/2} } \braket{ \varepsilon^{-1/2} } = \frac{\Gamma(1)\Gamma(2)}{\Gamma^{2}(3 /2)} \frac{g_{1}(z)g_{2}(z)}{[g_{3 /2}(z)]^{2}} = \frac{4}{\pi}\frac{g_{1}(z)g_{2}(z)}{[g_{3 /2}(z)]^{2}} $$
>当 $z\to 0$ 时，应当回归经典情况，此时 $g_{\nu}(z)=z+\mathcal{O}(z^{2})$ 于是 $\braket{ u }\braket{ 1 /u }= 4 /\pi\geq 1$ ；当 $z\to 1$ 时，是趋于 $\frac{4}{\pi} \frac{\zeta(1)\zeta(2)}{\zeta^{2}(3 /2)}$  发散的，意思是 $u=0$

# 习题 7.10

考虑加速度为 $g$ 的均匀重力场中的理想玻色气体，试证明该气体发生玻色－爱因斯坦凝聚现象的 $T_c$ 为： $$T_c \simeq T_c^0 \left[ 1 + \frac{8}{9} \frac{\zeta(1/2)}{\zeta(3/2)} \left( \frac{mgL}{kT_c^0} \right)^{1/2} \right]$$其中 $L$ 是容器的高度，并且 $mgL \ll kT_c^0$。同时试证明这里的凝聚伴有气体比热 $C_V$ 的不连续性： $$(\Delta C_V)_{T=T_c} \simeq - \frac{9}{8} Nk \frac{\zeta(3/2)}{\zeta(1/2)} \left( \frac{mgL}{kT_c^0} \right)^{1/2}$$ （注：式中 $T_c^0$ 由 **(7.1.24)** 式给出：$T_c = \frac{h^2}{2\pi mk} \left( \frac{N}{V \zeta(3/2)} \right)^{2/3}$）

>[!S]
>考虑重力场时，单粒子的能量发生改变
>$$\varepsilon = \varepsilon^{0} + mgr $$
>势能在粒子德布罗意波长尺度上变化缓慢，可将空间划分为宏观小、微观大的局域元胞，每个元胞内视为局部均匀的理想玻色气体，具有局域化学势，于是逸度为
>$$z(r) = e^{ \beta(\mu_{g} + \mu gr) } $$
>该局域的粒子数可以分为激发态的基态的 $n(r)=n_{0}(r) +n_{e}(r)$ 其中
>$$\begin{gather} n_{e} = \frac{1}{\lambda^{3}}g_{3 /2}(z) = \frac{1}{\lambda^{3}} g_{3 /2}(e^{ \beta(\mu_{g} + \mu gr) }) \\ n_{0} = \frac{1}{V_{cell}} \frac{z}{1-z} \end{gather} $$
>总激发态粒子数是
>$$N_{ex} = \frac{A}{\lambda^{3}} \int_{0}^{H} g_{3 /2}(e^{ \beta(\mu_{g} + \mu gr) })dr $$
>当BEC发生时，存在局域的逸度 $z=1$ 于是可设此时 $\mu_{g}=0$ 也即在容器底部开始发生凝聚，此时不妨设 $x=\beta mgr,x_{H}=\beta mgH$ 
>$$N_{ex} = \frac{AkT}{\lambda^{3}mg} \int_{0}^{x_{H}} g_{3 /2}(e^{ -x })dx $$
>将玻色爱因斯坦函数展开来取最低非平凡项得到
>$$N_{ex} = \frac{V}{\lambda^{3}} \frac{1}{x_{H}} \int_{0}^{x_{H}} \left[  \zeta\left( \frac{3}{2} \right) - 2\sqrt{ \pi x } + \mathcal{O}(x^{2})  \right]dx = \frac{V}{\lambda^{3}}\left[  \zeta\left( \frac{3}{2} \right) + \frac{\zeta(1 /2)}{2}x_{H} + \dots \right] $$
>令 $T_{c} = T_{c}^{0}(1+\delta)$ 则
>$$x_{H} = \frac{mgH}{kT_{c}} = \frac{mgH}{kT_{c}^{0}}(1-\delta) := x_{0}(1-\delta) $$
>当凝聚刚开始发生时，最大激发态粒子数就是总粒子数，于无重力场时一样于是
>$$\frac{V}{\lambda^{3}}\left[  \zeta\left( \frac{3}{2} \right) + \frac{\zeta(1 /2)}{2}x_{H} \right] = \frac{V}{\lambda_{0}^{3}}\zeta\left( \frac{3}{2} \right) $$
>$$\left( \frac{\lambda}{\lambda_{0}} \right)^{3} = 1 + \frac{\zeta(1 /2)}{2\zeta(3 /2)}x_{H} $$
>而由于 $\lambda \propto T^{-1/2}$ 所以 $(\lambda /\lambda_{0})^{3}=1+ \frac{3}{2}\delta$ 于是
>$$1+\frac{3}{2}\delta = 1 + \frac{\zeta(1 /2)}{2\zeta(3 /2)}x_{0}(1-\delta) $$
>解得
>$$\delta = \frac{8}{9} \frac{\zeta(1/2)}{\zeta(3/2)} \left( \frac{mgL}{kT_c^0} \right)^{1/2} $$
>即
>$$T_c \simeq T_c^0 \left[ 1 + \frac{8}{9} \frac{\zeta(1/2)}{\zeta(3/2)} \left( \frac{mgL}{kT_c^0} \right)^{1/2} \right]$$
>



# 习题 7.11 ?

考虑由具有内部自由度分子组成的理想玻色气体。假定除了基态 $\varepsilon_0 = 0$，只需要考虑内部谱的第一激发态 $\varepsilon_1$，试确定气体的凝聚温度（它是 $\varepsilon_1$ 的函数）。证明对于 $(\varepsilon_1/kT_c) \gg 1$，有 $\frac{T_c - T_c^0}{T_c^0} \simeq - \frac{2}{3} \frac{g_1}{\zeta(3/2)} e^{-\varepsilon_1/kT_c}$；而对于 $(\varepsilon_1/kT_c) \ll 1$，有： $$\frac{T_c}{T_c^0} \simeq \left[ 1 + \frac{2g_1}{g_0 \zeta(3/2)} \left( \frac{\pi kT_c}{\varepsilon_1} \right)^{1/2} \right]^{-2/3}$$ （提示：为了得到最后结果，需要用到附录 D 中关于玻色函数在 $\alpha \to 0$ 时的展开式 **(D.9)**：$g_\nu(e^{-\alpha}) = \frac{\Gamma(1-\nu)}{\alpha^{1-\nu}} + \sum_{i=0}^{\infty} \frac{(-1)^i}{i!} \zeta(\nu-i) \alpha^i$ 的头两项。）

>[]
>由题意，激发态粒子数密度为
>$$n = \frac{1}{\lambda^{3}}( g_{0}\zeta(3 /2) + g_{1}g_{3 /2}(e^{ -\beta\varepsilon_{1} }) ) $$
>凝聚发生时
>$$\frac{1}{\lambda_{c}^{3}}\left[  g_{0}\zeta\left( \frac{3}{2} \right) + g_{1}g_{3 /2}(e^{ -\beta\varepsilon_{1} })  \right] = \frac{N}{V} $$
>而 $(\lambda_{c}^{0})^{3}=(V /N)\zeta(3 /2)$ 于是
>$$\frac{T_{c}}{T_{c}^{0}} = \left( \frac{\lambda_{c}^{0}}{\lambda_{c}} \right)^{2} = \frac{1}{g_{0}^{2/3}}\left[  1 - \frac{V}{N\lambda_{c}^{3}} g_{1}g_{3 /2}(e^{ -\beta\varepsilon_{1} })  \right]^{2/3} $$
>当 $(\varepsilon_1/kT_c) \gg 1$ 时 $g_{3 /2}(e^{ -\beta\varepsilon_{1} })\approx e^{ -\beta\varepsilon_{1} }$ 。设 $T_{c}=T_{c}^{0}(1+\delta)$ 则 $\lambda_{c}=\lambda_{c}^{0}(1-2\delta)$ 代入得
>$$1+\delta = \frac{1}{g_{0}^{2/3}}\left[  1 - \frac{g_{1}g_{3 /2}(e^{ -\beta\varepsilon })}{\zeta(3 /2)}(1+6\delta) \right]^{2 /3} $$
>$$1 + \frac{3}{2}\delta = \frac{1}{g_{0}}\left[ 1 - \frac{g_{1}g_{3 /2}(e^{ -\beta\varepsilon })}{\zeta(3 /2)}(1+6\delta) \right] $$
>可见得取 $g_{0}=1$ 对比系数得
>$$g_{3 /2}(e^{ -\beta\varepsilon_{1} }) = - \frac{3}{2g_{1}}\zeta\left( \frac{3}{2} \right) $$
>

# 习题 7.12

考虑巨正则系综中的理想玻色气体，研究其总粒子数 $N$ 和总能量 $E$ 的涨落，特别讨论当气体变得高度简并时的情况。 （注：参考巨正则系综粒子数涨落的一般公式 **(4.5.3)**：$\langle (\Delta N)^2 \rangle = z \left( \frac{\partial \langle N \rangle}{\partial z} \right)_{T,V} = kT \left( \frac{\partial \langle N \rangle}{\partial \mu} \right)_{T,V}$）



# 习题 7.13

考虑二维中被囚禁在面积 $A$ 内的理想玻色气体。用 $z, T$ 和 $A$ 写出处于激发态的粒子数 $N_e$ 和处于基态的粒子数 $N_0$，并证明只有当 $T \to 0\text{ K}$ 时系统才会发生玻色－爱因斯坦凝聚。 改进你的讨论，试证明：如果固定面积 $A$ 和总粒子数 $N$，并且我们要求 $N_e$ 和 $N_0$ 都是 $N$ 量级，那么当 $$T \simeq \frac{h^2}{mk l^2 \ln N}$$ 时，可以达到凝聚，式中 $l [ \simeq (V/N)^{1/d} ]$ 是系统中粒子间的平均距离。当然，保持 $l$ 固定，如果 $A$ 和 $N \to \infty$，则 $T$ 期望值趋向于零。

# 习题 7.14

试考虑 $n$ 维玻色气体，它的单粒子能量谱 $\varepsilon \propto p^s$，这里 $s$ 为某个正数。试讨论这个系统中玻色－爱因斯坦凝聚现象的发端，特别是该现象对 $n$ 和 $s$ 的依存关系。并研究这个系统的热力学特性的本质。试证明，在很一般的情形下， $$P = \frac{s}{n} \frac{U}{V}, \quad C_V(T \to \infty) = \frac{n}{s} Nk, \quad \text{以及} \quad C_P(T \to \infty) = \left( \frac{n}{s} + 1 \right) Nk$$

# 习题 7.15

当时间 $t = 0$ 时，势能为 $V(x) = \frac{1}{2} m \omega_0^2 x^2$ 的一维量子谐振子的基态波函数是 $$\psi(x, 0) = \left( \frac{m \omega_0}{\pi \hbar} \right)^{1/4} \exp \left( - \frac{m \omega_0 x^2}{2 \hbar} \right)$$ 其中 $a_0 = \sqrt{\frac{\hbar}{m \omega_0}}$。当 $t = 0$ 时，突然移除谐振子势。试利用 $t = 0$ 时波函数的动量表示和含时薛定谔方程，以确定时间 $t > 0$ 时的空间波函数和密度；请与 **(7.2.11)** 式： $$n_0(\mathbf{r}, t) = N_0 |\psi_0(\mathbf{r}, t)|^2 = \frac{N_0}{\pi^{3/2} a_x(t) a_y(t) a_z(t)} \exp \left( - \frac{x^2}{a_x^2(t)} - \frac{y^2}{a_y^2(t)} - \frac{z^2}{a_z^2(t)} \right)$$ 进行比较。

# 习题 7.16

当时间 $t = 0$ 时，三维谐振子势 $V(r) = \frac{1}{2} m \sum_i \omega_i^2 r_i^2$ 中一组经典粒子在温度 $T$ 下处于平衡态。当 $t = 0$ 时，突然移除谐振子势。利用 $t = 0$ 时的动量分布以确定当 $t > 0$ 时的空间密度。试证明这等价于 **(7.2.15)** 式： $$n_{excited}(\mathbf{r}, t) = \frac{1}{\lambda^3} \prod_{i=1}^3 \left( \frac{1}{\sqrt{1 + \omega_i^2 t^2}} \right) g_{3/2} \left[ z \exp \left( - \sum_{i=1}^3 \frac{r_i^2}{a_i^2(1 + \omega_i^2 t^2)} \right) \right]$$ 的高温极限。

# 习题 7.17

如 7.1 节中所证，$n\lambda^3$ 是系统的量子特性的测度。试利用 **(7.2.11)** 式： $$n_0(\mathbf{r}, t) = \frac{N_0}{\pi^{3/2} a_x(t) a_y(t) a_z(t)} \exp \left( - \frac{x^2}{a_x^2(t)} - \frac{y^2}{a_y^2(t)} - \frac{z^2}{a_z^2(t)} \right)$$ 和 **(7.2.15)** 式： $$n_{excited}(\mathbf{r}, t) = \frac{1}{\lambda^3} \prod_{i=1}^3 \left( \frac{1}{\sqrt{1 + \omega_i^2 t^2}} \right) g_{3/2} \left[ z \exp \left( - \sum_{i=1}^3 \frac{r_i^2}{a_i^2(1 + \omega_i^2 t^2)} \right) \right]$$ 以确定 $T = T_c/2$ 时凝聚和非凝聚部分在谐振子势中心处的 $n\lambda^3$。

# 习题 7.18

试证明 **(7.2.15)** 式： $$n_{excited}(\mathbf{r}, t) = \frac{1}{\lambda^3} \prod_{i=1}^3 \left( \frac{1}{\sqrt{1 + \omega_i^2 t^2}} \right) g_{3/2} \left[ z \exp \left( - \sum_{i=1}^3 \frac{r_i^2}{a_i^2(1 + \omega_i^2 t^2)} \right) \right]$$ 中半经典空间密度的积分给出了未凝聚在基态的原子的正确计数。
