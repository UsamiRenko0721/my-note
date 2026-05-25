---
up:
  - "[[写题]]"
related:
date: 2026-03-30
---
# 1

试证明处于热平衡态下的理想气体的熵在玻色子的情况下为：
$$S = k \sum_{\epsilon} [(\langle n_{\epsilon} \rangle + 1) \ln(\langle n_{\epsilon} \rangle + 1) - \langle n_{\epsilon} \rangle \ln \langle n_{\epsilon} \rangle]$$
而在费米子的情况下为：
$$S = k \sum_{\epsilon} [- (1 - \langle n_{\epsilon} \rangle) \ln(1 - \langle n_{\epsilon} \rangle) - \langle n_{\epsilon} \rangle \ln \langle n_{\epsilon} \rangle]$$
并验证这些结果与一般公式 $S = -k \sum_{\epsilon} \sum_{n} p_{\epsilon}(n) \ln p_{\epsilon}(n)$ 的一致

>[]
>对于玻色子
>$$p_{\varepsilon}(n) = \frac{(ze^{ -\beta\varepsilon })^{n}}{1-ze^{ -\beta\varepsilon }} ,\quad \braket{ n_{\varepsilon} } = \frac{ze^{ -\beta\varepsilon }}{1-ze^{ -\beta\varepsilon }}  $$
>所以
>$$ze^{ -\beta\varepsilon } = \frac{\braket{ n_{\varepsilon} }}{1-\braket{ n_{\varepsilon} } } ,\quad  p_{\varepsilon}(n) = \frac{\braket{ n_{\varepsilon} }^{n}}{(1+\braket{ n_{\varepsilon} } )^{n+1}}  $$
>$$\begin{align}
S_{\text{B.E.}} & = -k\sum_{\varepsilon}\sum_{n}p_{\varepsilon}(n)\ln p_{\varepsilon}(n) = -k\sum_{\varepsilon}\sum_{n} p_{\varepsilon}(n)[ n\ln \braket{ n_{\varepsilon} }  - (n+1)\ln(1+\braket{ n_{\varepsilon} } ) ] \\ & =-k\sum_{\varepsilon} [ \braket{ n_{\varepsilon} }\ln \braket{ n_{\varepsilon} } -(\braket{ n_{\varepsilon} } + 1 )\ln(1+\braket{ n_{\varepsilon} } )  ] \\
&= k \sum_{\epsilon} [(\langle n_{\epsilon} \rangle + 1) \ln(\langle n_{\epsilon} \rangle + 1) - \langle n_{\epsilon} \rangle \ln \langle n_{\epsilon} \rangle]
\end{align}$$
>对于费米子
>$$p_{\varepsilon}(0) = \frac{1}{1+ze^{ -\beta\varepsilon }} ,\quad p_{\varepsilon}(1) = \frac{ze^{ -\beta\varepsilon }}{1+ze^{ -\beta\varepsilon }} ,\quad \braket{ n_{\varepsilon} } = \frac{ze^{ -\beta\varepsilon }}{1+ze^{ -\beta\varepsilon }}  $$
>类似的
>$$ze^{ -\beta\varepsilon } = \frac{\braket{ n_{\varepsilon} }}{1+\braket{ n_{\varepsilon} } }   $$
>$$\begin{align}
S_{\text{F.D.}} & = -k\sum_{\varepsilon}\sum_{n}p_{\varepsilon}(n)\ln p_{\varepsilon}(n) \\  & = -k\sum_{\varepsilon} [  ]
\end{align} $$
>

---
# 2

对于所有三种统计法，试从各自的概率 $p_{\epsilon}(n)$ 表达式推导量 $\langle n_{\epsilon}^2 \rangle - \langle n_{\epsilon} \rangle^2$ 的有关表达式。进而证明，有相当一般的关系式：
$$\langle n_{\epsilon}^2 \rangle - \langle n_{\epsilon} \rangle^2 = kT \left( \frac{\partial \langle n_{\epsilon} \rangle}{\partial \mu} \right)_{T,V}$$
并将上述结果与巨正则系综里的系统的相应结果进行比较


---
# 3

参考 6.2 节并试证明，如果限定能级 $\epsilon$ 的占有数 $n_{\epsilon}$ 取值为 $0, 1, \dots, l$，则该能级的平均占有数为：
$$\langle n_{\epsilon} \rangle = \frac{1}{z^{-1}e^{\beta\epsilon} - 1} - \frac{l+1}{(z^{-1}e^{\beta\epsilon})^{l+1} - 1}$$
验证当 $l=1$ 时会得到 $\langle n_{\epsilon} \rangle_{F.D.}$，$l \to \infty$ 时则会得到 $\langle n_{\epsilon} \rangle_{B.E.}$


---
# 4

由粒子电荷 $e$ 和粒子数密度 $n(r)$ 所表征的带电粒子系统的势能为：
$$U = \frac{e^2}{2} \int \frac{n(r)n(r')}{|r-r'|} dr dr' + e \int n(r)\phi_{ext}(r) dr$$
其中 $\phi_{ext}(r)$ 是外场的电势。假设系统的熵由 $S = -k \int n(r) \ln n(r) dr$ 给出，试利用这些公式推导平衡态下 $n(r)$ 和总电势 $\phi(r)$ 所满足的方程


---
# 5

试证明在遵循麦克斯韦-玻尔兹曼分布的一个系统中，分子能量 $\epsilon$ 的方均根偏差是其平均值 $\bar{\epsilon}$ 的 $\sqrt{2/3}$ 倍，并同理想气体的结果比较


---
# 6

试证明对于分子速率的任何分布律，不等式 $\langle v \rangle \langle 1/v \rangle \geq 1$ 必成立，并验证对于麦克斯韦分布它的值是 $4 /\pi$

>[!S]
>$$\braket{ v } = \int_{0}^{\infty}vf(v)dv,\quad \braket{ \frac{1}{v} } = \int_{0}^{\infty} \frac{1}{v} f(v)dv $$
>所以
>$$\braket{ v }\braket{ 1 /v } = \left( \int_{0}^{\infty} xf(x)dx \right)\left( \int_{0}^{\infty} \frac{1}{y}f(y)dy \right) \geq \left( \int_{0}^{\infty} \sqrt{ \frac{u}{u}f(u)f(u) } du \right)^{2} = 1  $$
>不等式是柯西不等式。对于麦克斯韦分布
>$$\begin{align}
\braket{ v }\braket{ 1 /v } & = \left( N\int_{0}^{\infty} v\exp\left( -\frac{mv^{2}}{2kT} \right)v^{2} dv \right)\left( N\int_{0}^{\infty} \frac{1}{v}\exp\left( -\frac{mv^{2}}{2kT} \right)v^{2} dv \right) \\ & = \left( \frac{2Nk^{2}T^{2}}{m^{2}} \right) \left( \frac{NkT}{m} \right) \\ & = \frac{2m^{3}}{\pi k^{3}T^{3}}\cdot\frac{2k^{3}T^{3}}{m^{3}} \\ & = \frac{4}{\pi}
\end{align}$$


---
# 7

试证明由于分子运动，炉内高温气体发射的谱线呈现多普勒增宽，其相对强度 $I(\lambda)$ 满足：
$$I(\lambda) \propto \exp\left[ -\frac{mc^2 (\lambda - \lambda_0)^2}{2 \lambda_0^2 kT} \right]$$
其中 $m$ 为分子质量 $c$ 为光速，$\lambda_{0}$ 是谱线平均线长

>[!S]
>考虑开普勒效应，当分子相对观察者以径向速度 $v$ 运动时，发出的光会发生频移
>$$\frac{\lambda-\lambda_{0}}{\lambda_{0}} = \frac{v}{c} $$
>而在高温热平衡时的粒子按运动速度分布满足麦克斯韦分布律
>$$ f(v)dv = A \exp\left( -\frac{mv^{2}}{2kT} \right) dv $$
>其中 $A$ 为归一化常数，显然 $I(\lambda)\propto f(v)$ 因为强度理论上应该和发射光子的粒子数量有关，将其改写为 $\lambda$ 的函数
>$$f(v) = A\exp\left( -\frac{mc^{2}}{2kT}\left( \frac{\lambda-\lambda_{0}}{\lambda_{0}} \right)^{2} \right) $$
>于是
>$$I(\lambda) \propto \exp\left[ -\frac{mc^2 (\lambda - \lambda_0)^2}{2 \lambda_0^2 kT} \right]$$

---
# 8

质量为 $m$ 的 $N$ 个粒子所组成的经典理想气体，置于均匀引力场中，试求其配分函数及热力学性质

>[!S]
>由于是经典理想气体，所以不计相互作用，先考察单粒子的配分函数
>$$H = \frac{p^{2}}{2m} + mgz \implies Z_{1} = \frac{1}{h^{3}} \int e^{ -\beta H }d^{3}pd^{3}r $$
>其中
>$$\int \exp\left( -\frac{p^{2}}{2m} \right) 4\pi p^{2}dp = \frac{1}{\lambda^{3}} $$
>$$\int e^{ -mgz } dxdydz = \frac{S}{\beta mg}( 1 - e^{ -\beta mgH } ) $$
>其中 $\lambda$ 是平均热波长，$S,H$ 是假定粒子处于底面积 $S$ 高 $L$ 的箱内，在其中认为是题设引力均匀的范围。于是
>$$Z_{1} = \frac{1}{\lambda^{3}h^{3}} \frac{S}{\beta mg}(1-e^{ -\beta mH }) $$
>$$Z_{N} = \frac{1}{N!} (Z_{1})^{N} = \frac{1}{\lambda^{3N}h^{3N}N!} \left( \frac{S}{\beta mg} \right)^{N}(1-e^{ -\beta mgH })^{N} $$
>于是可以得到
>$$A = -kT\ln Z_{N} = -NkT\ln \frac{S(1-e^{ -\beta mgH })}{\lambda^{3}h^{3}\beta mg} + kT\ln N! $$
>$$U = -\frac{\partial }{\partial \beta}\ln Z_{N} = \frac{5}{2}NkT - \frac{NmgH}{e^{ mgH /kT } - 1} $$
>$$C_{V} = \left( \frac{\partial U}{\partial T} \right)_{V} = \frac{5}{2}NkT $$

---
# 9

天然铀由两种同位素组成，它们是 $^{238}\text{U}$ 和 $^{235}\text{U}$，所占百分比分别为 99.27% 和 0.72%。如果将六氟化铀 $\text{UF}_6$ 注入内半径为 $R$ 的快速旋转空心金属圆柱体内，由于离心力的作用，气体在内半径处平衡压强达到最大值。轴心与内半径之间同位素的浓度差使得 $^{235}\text{U}$ 的浓度在轴心附近得到浓缩。

**(a) 建模与哈密顿函数证明：** 试写出以角速度 $\omega$ 旋转的柱坐标系中质量为 $m$ 的粒子的拉格朗日函数 $\mathcal{L}({q_k, \dot{q}_k})$，并利用勒让德变换 $\mathcal{H}({q_k, p_k}) = \sum p_k \dot{q}_k - \mathcal{L}$ 证明在该柱坐标系中单粒子哈密顿函数 $H'$ 为： $$H'(r, \theta, z, p_r, p_\theta, p_z) = \frac{p_r^2}{2m} + \frac{(p_\theta - mr^2\omega)^2}{2mr^2} + \frac{p_z^2}{2m} - \frac{1}{2}mr^2\omega^2$$ 由于分子的内部自由度不影响密度（密度是位置的函数），因此我们可以忽略分子内部自由度。试证明：通过在直角坐标系和柱坐标系之间构造相空间积分的雅可比变换，我们可以把单粒子配分函数写作： $$Q_1(V, T) = \frac{1}{h^3} \int_{-\infty}^{\infty} dp_r \int_{-\infty}^{\infty} dp_\theta \int_{-\infty}^{\infty} dp_z \int dr \int d\theta \int dz \exp(-\beta H')$$ 并估算封闭形式的配分函数 $Q_1$，确定这个系统的亥姆霍兹自由能。

>[!S]
>$$\mathcal{L} = \frac{1}{2}m(\dot{r}^{2} + r^{2}(\dot{\theta} + \omega)^{2} + \dot{z}^{2}) $$
>$$p_{r} = \frac{\partial \mathcal{L}}{\partial  \dot{r}} = m \dot{r} ,\quad p_{\theta} = \frac{\partial \mathcal{L}}{\partial \dot{\theta}} = mr^{2}(\dot{\theta}+\omega) ,\quad p_{z} = \frac{\partial \mathcal{L}}{\partial \dot{z}} = m\dot{z}  $$
>$$\mathcal{H} = \sum \dot{q}p - \mathcal{L} = \frac{p_{r}^{2}+p_{z}^{2}}{2m} + \frac{p_{\theta}^{2}}{2mr^{2}} - p_{\theta}\omega = \frac{p_r^2}{2m} + \frac{(p_\theta - mr^2\omega)^2}{2mr^2} + \frac{p_z^2}{2m} - \frac{1}{2}mr^2\omega^2 $$
>
>对于单粒子计算配分函数，选择这个坐标系，在相空间中
>$$Z_{1} = \frac{1}{h^{3}} \int e^{ -\beta H } d^{3}p d^{3}q   $$
>$$\int e^{ -\beta p^{2}_{r}/2m } dp_{r} = \sqrt{ \frac{2\pi m}{\beta} } ,\quad \int e^{ -\beta p_{z}^{2}/2m } dp_{z} = \sqrt{ \frac{2\pi m}{\beta} } $$
>$$\int \exp\left( -\frac{\beta(p_{\theta}-mr^{2}\omega)^{2}}{2m} \right) dp_{\theta} = r\sqrt{ \frac{2\pi m}{\beta} } $$
>$$\iint dzd\theta = 2\pi H ,\quad \int r e^{ \beta mr^{2} /2 } dr = \frac{1}{\beta m\omega^{2}}(e^{ \beta m\omega^{2}R^{2} /2 } - 1) $$
>故
>$$Z_{1} = \frac{2\pi L}{h^{3}} \left( \frac{2\pi m}{\beta} \right)^{3/2} \frac{1}{\beta m\omega^{2}}( e^{ \beta m\omega^{2}R^{2}/2 } - 1 ) = \frac{V}{\lambda^{3}} \frac{2}{\beta m\omega^{2}R^{2}}(e^{ \beta m\omega^{2}R^{2}/2 }  -1) $$
>于是亥姆霍兹自由能是
>$$A = -kT\ln Z_{1} = -kT\ln \frac{V}{\lambda^{3}} -kT \ln\left[  \frac{2}{\beta m\omega^{2}R^{2}}(e^{ \beta m\omega^{2}R^{2}/2 }  -1) \right] $$
>
>

**(b) 空间分布与压强比：** 试确定旋转圆柱体中 $N$ 个气体分子的数密度 $n(r)$ 与距轴心距离 $r$ 之间的函数关系。求证在 $\omega \to 0$ 极限下，密度变成均匀的，其值为 $n = N/(\pi R^2 H)$（其中 $H$ 为圆柱高度）。并试找出圆柱体内半径 $R$ 处的气体压强与圆柱体轴心上的压强之比，该比值应当是 $\omega$ 和 $R$ 的函数。

>[!S]
>考虑实验室系，有离心势能 $u=-\frac{1}{2}m\omega^{2}r^{2}$ 由玻尔兹曼分布，有
>$$n(r) \propto \exp\left( \frac{m\omega^{2}}{2kT} r^{2} \right) $$
>在 $\omega\to 0$ 时显然有 $n(r)=Const$ 密度变为均匀的，由于体积是 $V=\pi R^{2}H$ 所以
>$$n = \frac{N}{\pi R^{2}H} $$
>热平衡时 $P=nkT$ 所以
> $$\frac{P(R)}{P(0)} = \frac{n(R)}{n(0)} = \exp\left( \frac{m\omega^{2}}{2kT} R^{2} \right) $$

**(c) 数值估算与物理分析：** 当线速度 $\omega R = 500 \text{ m/s}$ 时，试估算室温下两种不同同位素的六氟化铀 $\text{UF}_6$ 气体的压强比。证明 $^{238}\text{U}$ 的压强比比 $^{235}\text{U}$ 的压强比大约大 20%，由此说明在轴心附近萃取的气体具有更高的 $^{235}\text{U}$ 浓度。我们可以利用一系列离心机来提高 $^{235}\text{U}$ 浓度，以生产出发电反应堆或核武器所用的裂变级铀。


---
# 10

试证明均匀重力场中经典气体的压强随高度的变化符合气压公式，并讨论绝热大气的情形。


---
# 11

相对论性玻尔兹曼气体：已知能量动量关系为 $\epsilon = c(p^2 + m_0^2 c^2)^{1/2}$，试推导其动量分布，并考查非相对论和极端相对论极限。

>[!S]
>$$\begin{align}
Z & = \frac{1}{h^{3}} \int \exp(-\beta c\sqrt{ p^{2}+m^{2}c^{2} }) d^{3}q d^{3}p = \frac{4\pi V}{h^{3}} \int_{0}^{\infty} \exp(-\beta c\sqrt{ p^{2}+m^{2}c^{2} }) p^{2}dp \\ & = \frac{4\pi V}{h^{3}} m^{3}c^{3} \int_{0}^{\infty} x^{2}e^{ -\alpha \sqrt{ 1+x^{2} } } dx\\ & = \frac{4\pi V}{h^{3}} m^{3}c^{3} \frac{K_{2}(\alpha)}{\alpha}
\end{align}$$
>其中 $\alpha=\beta mc^{2}$ 是无量纲的也。在非相对论时 $\alpha\ll 1$ 
>$$Z \approx \frac{4\pi V}{h^{3}} m^{3}c^{3} \frac{\sqrt{ \frac{\pi}{2\alpha} }e^{ -\alpha }}{\alpha} = \frac{V}{\lambda^{3}} e^{ -mc^{2}/kT } $$
>在极端相对论时 $\alpha\gg 1$  
>$$Z \approx \frac{4\pi V}{h^{3}} m^{3}c^{3} \frac{2}{\alpha^{2}} \frac{1}{\alpha} = \frac{8\pi V(kT)^{3}}{h^{3}c^{3}} $$
>
>

---
# 12

试推导非相对论性和极端相对论性理想气体准静态绝热膨胀的方程式 $PV^\gamma = const$。

>[!S]
>非相对论气体有
>$$Z_{1} = \frac{V}{\lambda^{3}} e^{ -mc^{2}/kT } ,\quad Z_{N} = \frac{1}{N!} (Z_{1})^{N}$$
>故
>$$A = -kT\ln Z_{N} = -NkT\ln \frac{V}{N\lambda^{3}} - NkT ,\quad U = - \frac{\partial \ln Z_{N}}{\partial \beta} = \frac{3}{2}NkT $$
>$$P = -\left( \frac{\partial A}{\partial V} \right)_{N,T} = \frac{NkT}{V} ,\quad S = -\left( \frac{\partial A}{\partial T} \right)_{V,N} = Nk\left[  \ln \frac{V}{N\lambda^{3}} + \frac{5}{2} \right] $$
>对于准静态的绝热过程 $S=Const$ 所以
>$$\frac{V}{N\lambda^{3}} = Const \implies VT^{3/2} = Const \implies PV^{5/3} = Const $$
>极端相对论气体有
>$$Z_{1} = \frac{8\pi V(kT)^{3}}{h^{3}c^{3}} ,\quad Z_{N} = \frac{1}{N!}(Z_{1})^{N} $$
>故
>$$A = -kT\ln Z_{N} = -NkT\ln \frac{8\pi V(kT)^{3}}{h^{3}c^{3}} + kT(N\ln N - N) $$
>$$P = -\left( \frac{\partial A}{\partial V} \right)_{N,T} = \frac{NkT}{V} ,\quad S = -\left( \frac{\partial A}{\partial T} \right)_{N,V} = Nk\left[  \ln \frac{8\pi V(kT)^{3}}{Nh^{3}c^{3}} + 4 \right] $$
>对于准静态绝热过程 $S=Const$ 所以
>$$VT^{3} = Const \implies PV^{4/3} = Const $$


---
# 13


(a) 试确定气体分子在单位时间内对单位面积器壁的碰撞数，已知气体分子入射角处于 $\theta$ 到 $\theta+d\theta$ 之间。

>[!S]
>$$\begin{align}
dN =  nf(v) \ v^{2} \sin \theta dvd\theta d\phi\cdot v\cos \theta
\end{align} $$
>这里药对 $v,\phi$ 积分
>$$dN = n\left( \int_{0}^{\infty} v^{3}f(v) dv \right)\left( \int_{0}^{2\pi} d\phi \right) \sin \theta \cos \theta d\theta = 2n\sqrt{ \frac{kT}{2\pi m} } \sin \theta \cos \theta d\theta $$
>

(b) 试确定气体分子在单位时间内对单位面积器壁的碰撞数，已知气体分子的速度处于 $u$ 和 $u+du$ 之间。

>[!S]
>这里要对 $\phi,\theta$ 积分
>$$dN = nv^{3}f(v)dv\left( \int_{0}^{\pi /2} \sin \theta \cos \theta d\theta \right)\left( \int_{0}^{2\pi} d\phi \right) = 4\pi nv^{3}f(v)dv $$

(c) 如果具有平动能大于 $10^{-19}$ J 的分子 AB 打到一个固态催化剂表面上，则分子 AB 发生离解。试证明：当气体从 300 K 升高到 310 K 时，离解反应 $\text{AB} \to \text{A} + \text{B}$ 的速率增大一倍多。

>[!S]
>反应分子数速度为
>$$\Delta N \propto \sqrt{ T }\int_{v_{0}}^{\infty} v^{3}\exp\left( -\frac{mv^{2}}{2kT} \right) dv \sim \sqrt{ T }e^{ -E_{0}/kT }\left( 1+\frac{E_{0}}{kT} \right) $$
>故反应速率放大倍率为
>$$\sqrt{ \frac{310}{300} } \exp\left( -\frac{E_{0}}{k}\left( \frac{1}{310} - \frac{1}{300} \right) \right) \frac{1+ E_{0} /310k}{1+ E_{0} /300k} = 2.15 $$
>

---
# 14

考虑体积为 $V$ 的容器内的麦克斯韦气体，其分子通过壁上面积为 $a$ 的开孔泻流．

(a) 试证当容器内部分子的平均动能是 $\frac{3}{2}kT$ 时，泻流分子的平均动能是 $2kT$，$T$ 是准静态平衡温度．

>[!S]
>$$\braket{ E } = \frac{ \displaystyle\int_{0}^{\infty} \frac{1}{2}mv^{2}\cdot v^{3}\exp\left( -\frac{mv^{2}}{2kT} \right) dv }{ \displaystyle\int_{0}^{\infty}v^{3}\exp\left( -\frac{mv^{2}}{2kT} \right)dv } = \frac{1}{2}m\frac{ \displaystyle\int_{0}^{\infty} v^{5}\exp\left( -\frac{mv^{2}}{2kT} \right) dv }{ \displaystyle\int_{0}^{\infty}v^{3}\exp\left( -\frac{mv^{2}}{2kT} \right)dv }$$
>其中
>$$\int_{0}^{\infty} v^{n}\exp(-av^{2})dv = \int_{0}^{\infty} \left( \frac{t}{a} \right)^{n/2} \exp(-t) \frac{1}{2a\sqrt{ t }} dt = \frac{\Gamma\left( \frac{n+1}{2} \right)}{2a^{(n+1)/2}} $$
>于是
>$$\braket{ E } = \frac{1}{2}m \frac{\Gamma(3)}{\Gamma(2)} \frac{1}{\frac{m}{2kT}} = 2kT $$
>

(b) 假设泻流过程非常缓慢，因此容器内部气体总是处于准静态平衡状态，试确定气体密度、温度和压强随时间变化的方式．

>[!S]
>每秒系统都会损失 $\Gamma\braket{ E }$ 的能量，其中 $\Gamma = \frac{1}{4}n\braket{ v }$ 是泄流数，于是
>$$\begin{gather}
\frac{dU}{dt} = -\frac{1}{4}an\braket{ v }\braket{ E } = -\frac{1}{4}an \sqrt{ \frac{8kT}{\pi m} } 2kT = -\sqrt{ \frac{2}{\pi m} }an(kT)^{3/2}  \\
V \frac{dn}{dt} = -a\Gamma = -\frac{1}{4}an\sqrt{ \frac{8kT}{\pi m} } 
\end{gather}$$
>而对于系统内的气体有
>$$U = \frac{3}{2}nVkT $$
>所以得到
>$$\frac{3}{2}n \frac{dT}{dt} = -\frac{7}{2} \frac{dn}{dt} \implies T \propto n^{-7/3} $$
>$$\frac{dn}{dt} = -\frac{a}{4} n\sqrt{ \frac{8kT}{\pi m} } = -\frac{a}{4}\sqrt{ \frac{8kT_{0}}{\pi m} } \frac{n^{-1/6}}{n_{0}^{-7/6}} := Kn^{-1/6} $$
>$$n = n_{0}\left( 1 - \frac{7K}{6n_{0}^{4/6}}t \right)^{7/6} $$
>


---
# 15

处在 30,000 m 高度的一个聚乙烯气球用压强为 $10^{-2}$ atm 和温度为 300 K 的氦气充满，球的直径为 10 m，表面有许多直径为 $10^{-5}$ m 的针孔．如果在 1 h 内有 1% 的气体漏出去，则气球表面每 $\text{m}^2$ 有多少个针孔？

>[!S]
>假设泄流速度很慢，气球内近似时刻处于平衡状态，则泄流数是
>$$\Gamma = \frac{1}{4}n\braket{ v } = \frac{1}{4}n \sqrt{ \frac{8kT}{\pi m} } $$
>总的泄流粒子数率是 $\frac{\pi}{4}D^{2} SN\Gamma$ 其中 $N$ 是单位面积上的针孔数量，$D$ 是针孔直径。则可以建立微分方程
>$$\frac{dN}{dt} = -\frac{\pi}{16}D^{2}N_{\text{孔}} \frac{N}{V}\sqrt{ \frac{8kT}{\pi m} } $$
>$$N = N_{0}\exp\left(  -\frac{\frac{\pi}{16}D^{2}N_{\text{孔}}}{V}\sqrt{ \frac{8kT}{\pi m} }  \right) $$
>代入 $t=1\text{h}$ 时 $N=0.99N_{0}$ 得
>$$N_{\text{孔}} = \dots $$


---
# 16
考虑两种玻尔兹曼气体 $A$ 和 $B$, 它们的压强分别为 $P_{A}$ 和 $P_{B}$ ，温度分别为 $T_{A}$ 和 $T_{B}$ ，并处在空间的两个区域中，通过隔壁上狭缝保持两个区域之间的相连通
![[image-1774885257945.webp|400x208]]
试证明建立动力学平衡的两类分子的相互泻流满足条件：$P_A / P_B = \sqrt{m_A T_A / m_B T_B}$。

>[!S]
>平衡时，左右泄流数相同
>$$\frac{1}{4}n_{A}\braket{ v_{A} } = \frac{1}{4} n_{B} \braket{ v_{B} }  $$
>即
>$$\frac{P_{A}}{T_{A}}\sqrt{ \frac{T_{A}}{m_{A}} } = \frac{P_{B}}{T_{B}} \sqrt{ \frac{T_{B}}{m_{B}} } $$
>$$\frac{P_{A}}{P_{B}} = \sqrt{ \frac{m_{A}T_{A}}{m_{B}T_{B}} } $$

---
# 17

具有初始温度为 $T$ 的一个小球被置于温度为 $T_{0}$​ 的玻尔兹曼理想气体中，假设入射到球上的分子首先被吸收，然后以球的温度发射出去，试确定球的温度随时间的变化． ［请注意，球的半径可以假设为远比分子的平均自由程小得多．

>[!S]
>设球得热容是 $C$ 则 $dU =CdT$ 。入射分子的总功率是
>$$\frac{1}{4}n\braket{ v }\cdot 2kT = \frac{1}{2}nkT \sqrt{ \frac{8kT}{\pi m} }  $$
>其中泄流分子平均能量是 $2kT$ 参考 6.14，同理出射分子的总功率是
>$$\frac{1}{4}n\braket{ v } = \frac{1}{2} nkT_{0}\sqrt{ \frac{8kT_{0}}{\pi m} }  $$
>所以球的能量变化率为
>$$\frac{dU}{dt} = \frac{nk}{2}\sqrt{ \frac{8k}{\pi m} }( T^{3/2} - T_{0}^{3/2} ) = C \frac{dT}{dt} $$
>令 $\sqrt{ T } =x, \frac{nk}{2C}\sqrt{ \frac{8k}{\pi m} }=A$ 则方程变为
>$$2x \frac{dx}{dt} = A (x^{3} - x_{0}^{3}) \implies \frac{xdx}{x^{3}-x_{0}^{3}} = \frac{A}{2}dt $$
>$$\frac{1}{3x_{0}}\left[  \ln|x-x_{0}| - \frac{1}{2}\ln(x^{2}+x_{0}x +x_{0}^{2}) +\sqrt{ 3 }\arctan \frac{2x+x_{0}}{\sqrt{ 3}x_{0}} \right] = \frac{A}{2}t + C $$
>取 $t=0$ 时 $x=\sqrt{ T }$ 则 
>$$C = \frac{1}{3\sqrt{ T_{0} }}\left[  \ln|\sqrt{ T } - \sqrt{ T_{0} } | - \frac{1}{2}\ln(T + \sqrt{ TT_{0} } + T_{0}) +\sqrt{ 3 }\arctan \frac{2\sqrt{ T } + \sqrt{ T_{0} }}{\sqrt{ 3T_{0} }} \right] $$
>

---
# 18

试证明麦克斯韦气体中两个分子的相对速率的平均值是一个分子对于器壁的平均速率的 $\sqrt{ 2 }$ 倍． ［请注意，在更普遍的条件下，对于方均根速率（不是平均速率）也有类似的结果．］

>[!S]
>相对速度是 $\mathbf{v}_{\text{rel}}=\mathbf{v}_{1}-\mathbf{v}_{2}$ 其中 $\mathbf{v}_{1},\mathbf{v}_{2}$ 是三维随机变量满足麦克斯韦速度分布律，所以 $\mathbf{v}_{\text{rel}}$ 满足联合概率分布，则它的分布是
>$$g(\mathbf{u}) = \int f(\mathbf{v}_{1})f(\mathbf{u}-\mathbf{v}_{1}) \mathrm{d}\mathbf{v}_{1} = \left( \frac{m}{4\pi kT} \right)^{3/2}\exp\left( -\frac{mu^{2}}{4kT} \right) $$
>所以平均相对速率是
>$$\braket{ u } = \int ug(\mathbf{u})\mathrm{d}\mathbf{u} = \sqrt{ \frac{16kT}{\pi m} } $$

---
# 19

从麦克斯韦气体中随机地取出总能量在 $E$ 到 $E+dE$ 间两个分子的概率是多少？证明其总能量平均值为 $3kT$。

>[!S]
>改写麦克斯韦速率分布为
>$$f(\mathbf{v})d\mathbf{v} = g(\varepsilon)d\varepsilon ,\quad d\varepsilon=m\mathbf{v}\cdot d\mathbf{v} $$
>所以
>$$g(\varepsilon) = \frac{2}{\sqrt{ \pi }} (kT)^{-3/2} \sqrt{ \varepsilon } e^{ -\varepsilon/kT } $$
>对于两个粒子，它们属于能量区间 $\varepsilon\sim \varepsilon+d\varepsilon$ 的概率是独立的，而它们的总能量是 $E$ 所以这是一个联合概率分布，它们总能量为 $E$ 的分布是两分布的卷积
>$$P(E) = \int_{0}^{E} g(\varepsilon)g(E-\varepsilon)d\varepsilon = \frac{E^{2}}{2(kT)^{3}} e^{ -E/kT } $$
>平均能量是
>$$\braket{ E } = \int_{0}^{\infty} EP(E) dE = \frac{1}{2(kT)^{3}} \int_{0}^{\infty} E^{3}e^{ -E/kT } dE = 3kT $$

---
# 20

已知在氮原子最低电子态 $^4S_{3/2}$ 和第一激发态 $^2D_{3/2}$ 之间的能量差为 $159843\text{ cm}^{-1}$。试计算在 $6000\text{ K}$ 温度下氮气中受激原子所占的相对分数。

---
# 21

对于反应： $H_2 + D_2 \rightleftharpoons 2HD$，在温度高到足以对转动取经典近似的条件下，试推导出平衡常数 $K(T)$ 的表达式。并求证 $K(\infty) = 4$。

>[!S]
>定温定压下的化学平衡有
>$$\mu(\pu{ H_{2} }) + \mu(\pu{ D_{2} }) = 2 \mu(\pu{ HD }) $$
>由于温度足够高考虑对转动取经典近似了，所以
>$$\mu = \varepsilon + kT\ln(n\lambda^{3}) - kT\ln j(T) $$
>$$j(T) \approx \frac{T}{\sigma \theta_{r}} = \frac{2IkT}{\sigma \hbar^{2}} $$
>于是化学平衡常数是
>$$K = \frac{n^{2}(HD)}{n(H_{2})n(D_{2})} = \frac{j^{2}(HD)}{j(H_{2})j(D_{2})}\exp\left( -\frac{\Delta\varepsilon}{kT} \right) ,\quad \Delta\varepsilon = 2\varepsilon(HD) - \varepsilon(H_{2}) - \varepsilon(D_{2}) $$
>在高温极限下
>$$K(\infty) = \frac{j^{2}(HD)}{j(H_{2})j(D_{2})} = 4\cdot \frac{\theta(H_{2})\theta(D_{2})}{\theta^{2}(HD)} $$

---
# 22

借助欧拉－麦克劳林公式 (6.5.19)，试推导按公式 (6.5.29) 和 (6.5.30) 所定义的 $\mathcal{V}_{偶}$ 和 $\mathcal{V}_{奇}$ 的高温展开式；并求出按公式 (6.5.39) 所定义的 $C_{偶}$ 和 $C_{奇}$ 的相应的展开式。并将这些结果的数学趋向与图 6.7 中相应曲线的特性进行比较。也研究一下两个比热的低温行为，再次将结果与前述曲线的有关部分进行比较。

>[!S]
>由定义
>$$\begin{gather}
\mathcal{r}_{\text{even}} = \sum_{l\in\text{even}} (2l+1)e^{ -l(l+1)\theta_{r}/T } = \sum_{k=0}^{\infty} (4k+3) e^{ -2(2k+1)(k+1)\theta_{r}/T } \\
\mathcal{r}_{\text{odd}} = \sum_{l\in\text{odd}} (2l+1)e^{ -l(l+1)\theta_{r}/T } = \sum_{k=0}^{\infty} (4k+1)e^{ -2k(2k+1)\theta_{r}/T }
\end{gather} $$
>使用 E-M 化求和为积分有
>$$\mathcal{r}_{\text{odd}} = \int_{0}^{\infty} (4x+1)e^{ -2x(2x+1)\theta_{r}/T } dx + \frac{1}{2} + \dots \approx \frac{T}{2\theta_{r}} $$
>$$\mathcal{r}_{\text{even}} \approx \frac{T}{2\theta_{r}} $$
>所以热容是
>$$C_{\text{odd}} = Nk \frac{\partial }{\partial T}\left[  T^{2} \frac{\partial }{\partial T} \ln \mathcal{r}_{\text{odd}} \right] = Nk $$
>$$C_{\text{even}} = Nk  $$

---
# 23

一个氢分子的原子间的势能由半经验莫尔斯势 $V(r) = V_0 {e^{-2(r-r_0)/a} - 2e^{-(r-r_0)/a}}$ 给出，这里 $V_0 = 7 \times 10^{-12}\text{ erg}$，$r_0 = 8 \times 10^{-9}\text{ cm}$ 和 $a = 5 \times 10^{-9}\text{ cm}$。试计算转动能量量子和振动能量量子，并估算分子的转动模式和振动模式开始对氢气的比热产生贡献时的温度。

>[]
>

---
# 24

试证明由于转动的结果，双原子分子的核间距离平衡值的相对变化量为： $$\frac{\Delta r}{r_0} = 4 \left( \frac{B}{\hbar\omega} \right)^2 J(J+1)$$ 这里，$\omega$ 为分子振动态的角频率。并估算在典型情况中这个分数的数值。

---




**6.25.** 计算 300 K 时原子氧中占据不同 $J$ 能级的原子分数。

**6.26.** 计算 5000 K 时 $O_2$ 分子第一受激电子态对比热的贡献。

**6.27.** 在经典近似下推导多原子分子的转动配分函数。

**6.28.** 确定标准状态下 $CO_2$ 气体的平动、转动和振动对比热和熵的贡献。

**6.29.** 确定 300 K 温度下氨的摩尔比热。

**6.30.** 从平衡条件推导质量作用定律公式。

**6.31.** 确定 $2CO + O_2 \rightleftharpoons 2CO_2$ 反应在不同温度下的平衡常数。

**6.32.** 研究 $N_2 + O_2 \rightleftharpoons 2NO$ 反应的平衡常数与温度的关系。

**6.33.** 分析甲烷燃烧反应中 $CO$ 的残留量。

**6.34.** 试推导电中性等离子体中钠原子的萨哈电离方程。


