---
up:
  - "[[写题]]"
---
# 3.1

>[!question] 3.1
>(a) 试从方程 (3.2.14) 和 (3.2.35) 出发，推导出公式 (3.2.36)。  
>(b) 试从方程 (3.2.37) 和 (3.2.38) 出发，推导出公式 (3.2.39) 和 (3.2.40)。

(a)
直接计算即可
$$\begin{align}
\braket{ (\Delta n)^{2} } & = \braket{ (n-\braket{ n } )^{2} } = \braket{ n^{2} } -\braket{ n }^{2} \\ & =\left[  \left.\frac{1}{\Gamma}\left( \omega_{r}\frac{\partial }{\partial \omega_{r}} \right)^{2}\Gamma\right|_{\omega_{r}=1}  \right] - \left[ \left.\left( \omega_{r}\frac{\partial }{\partial \omega_{r}} \right)\ln \Gamma\right|_{_{\omega_{r}=1}} \right]^{2} \\ & = \frac{1}{\Gamma}\left( \omega_{r}\frac{\partial }{\partial \omega_{r}} \right)\left( \omega_{r}\frac{\partial \Gamma}{\partial \omega_{r}} \right) + \left( \frac{\omega_{r}}{\Gamma}\frac{\partial \Gamma}{\partial \omega_{r}} \right)^{2} \\ & = \frac{\omega_{r}}{\Gamma}\left(  \frac{\partial \Gamma}{\partial \omega_{r}} + \omega_{r}\frac{\partial^{2}\Gamma}{\partial \omega_{r}^{2}}  \right) + \frac{\omega_{r}^{2}}{\Gamma^{2}}\left( \frac{\partial \Gamma}{\partial \omega_{r}} \right)^{2} \\ & = \frac{\omega_{r}}{\Gamma}\frac{\partial \Gamma}{\partial \omega_{r}} - \frac{\omega_{r}^{2}}{\Gamma^{2}}\left( \frac{\partial \Gamma}{\partial \omega_{r}} \right)^{2} + \frac{\omega_{r}^{2}}{\Gamma} \frac{\partial^{2} \Gamma }{\partial \omega_{r}^{2}} \\ & = \left( \omega_{r}\frac{\partial }{\partial \omega_{r}}\left( \frac{\omega_{r}}{\Gamma} \frac{\partial \Gamma}{\partial \omega_{r}} \right) \right) \\ & = \left.\left( \omega_{r}\frac{\partial }{\partial \omega_{r}} \right)^{2}\ln \Gamma \right|_{\omega_{r}=1} 
\end{align} $$
ps. 中间不想反复写 $\omega_{r}=1$ 条件了

(b)
对于等式
$$U = \frac{\sum_{r}E_{r}\omega_{r}\exp(-\beta E_{r})}{\sum_{r}\omega_{r}\exp(-\beta E_{r})} \implies U\sum_{r}\omega_{r}\exp(-\beta E_{r}) = \sum_{r}E_{r}\omega_{r}\exp(-\beta E_{r}) $$
其中对于 $U$ 要最后取 $\omega_{r}=1$ 这里先让其自由以求得偏导，而 $E_{r}$ 是参数，变量为 $\omega_{r},U,\beta$ ，两边微分
$$\begin{align}
&\quad \left( \sum_{r}\omega_{r}e^{ -\beta E_{r} } \right)dU + \sum_{r}(-E_{r}U\omega_{r}e^{ - \beta E_{r} })d\beta + \sum_{r}(Ue^{ -\beta E_{r} })d\omega_{r} \\ &  = \sum_{r}(E_{r}e^{ -\beta E_{r} })d\omega_{r} + \sum_{r}(-E_{r}^{2}\omega_{r}e^{ -\beta E_{r} })d\beta
\end{align}$$
于是
$$\left( \frac{\partial \beta}{\partial \omega_{r}} \right)_{U} = \frac{(U-E_{r})e^{ -\beta E_{r} }}{\sum_{s}(U-E_{s})E_{s}\omega_{s}e^{ -\beta E_{s} }} $$
$$\left.\left( \frac{\partial \beta}{\partial \omega_{r}} \right)_{U} \right|_{\omega_{s}=1} = \frac{(U-E_{r})e^{ -\beta E_{r} }}{\sum_{s}(U-E_{s})E_{s}e^{ -\beta E_{s} }} = \frac{U - E_{r}}{\braket{ E_{r}^{2} } - U^{2} } \frac{e^{ -\beta E_{r} }}{\sum_{s}\exp(-\beta E_{s})} = \frac{U-E_{r}}{\braket{ E_{r}^{2} } - U^{2} } \frac{\braket{ n_{r} }}{N}  $$


对于 (3.2.37) 其左边的项
$$\omega_{r}\frac{\partial }{\partial \omega_{r}} \frac{\omega_{r}\exp(-\beta E_{r})}{\sum_{s}\omega_{s}\exp(-\beta E_{s})} = \frac{\omega_{r}\exp(-\beta E_{r})}{\sum_{s}\omega_{s}\exp(-\beta E_{s})} \overset{\omega_{r}=1}\to \frac{\braket{ n_{r} }}{N}  $$
对于右边的项
$$\omega_{r}\frac{\partial }{\partial \omega_{r}}\left[  \left( U - \frac{\sum_{r}\omega_{r}E_{r}e^{ -\beta E_{r} }}{\sum_{r}\omega_{r}e^{ -\beta E_{r} }} \right) \omega_{r}\frac{\partial \beta}{\partial \omega_{r}} \right] $$
不妨记
$$Z(\beta,\omega) := \sum_{r}\omega_{r}e^{ -\beta E_{r} } $$
$$\frac{\partial }{\partial \omega_{r}}\left(  \frac{\sum_{r}\omega_{r}E_{r}e^{ -\beta E_{r} }}{\sum_{r}\omega_{r}e^{ -\beta E_{r} }} \right) = \frac{e^{ -\beta E_{r} }}{Z}(E_{r} - \braket{ E_{r} } ) - ( \braket{ E_{r}^{2} } - \braket{ E_{r} }^{2}  )\frac{\partial \beta}{\partial \omega_{r}} $$
于是
$$a_{1} = \omega_{r}^{2}\left[  \frac{e^{ -\beta E_{r} }}{Z}(E_{r} - \braket{ E_{r} } ) - ( \braket{ E_{r}^{2} } - \braket{ E_{r} }^{2}  )\frac{\partial \beta}{\partial \omega_{r}} \right] \frac{\partial \beta}{\partial \omega_{r}} $$
$$a_{2}=\omega_{r}(U-\braket{ E }_{\omega_{r}} )\frac{\partial \beta}{\partial \omega_{r}} $$
$$a_{3} = \omega_{r}^{2}(U-\braket{ E }_{\omega_{r}} )\frac{\partial^{2}\beta}{\partial \omega_{r}^{2}} $$
其中
$$\frac{\partial^{2}\beta}{\partial \omega_{r}^{2}} = \frac{1}{\braket{ E_{r}^{2} } - \braket{ E_{r} }^{2}  }[  ] $$
---
# 3.2

>[!question] 3.2
>参看方程 (3.2.25)，试证明 $g''(x_0)$ 等于 $\langle (E-U)^2 \rangle \exp(2\beta)$。由此说明方程 (3.2.28) 物理上等价于方程 (3.6.9)。

$$g(z) = \ln f(z) - \left( U + \frac{1}{N} \right)\ln z ,\quad f(z) = \sum_{r}\omega_{r} z^{E_{r}} $$

$$g''(x_{0}) = \left(  \frac{f''(x_{0})}{f(x_{0})} - \frac{|f'(x_{0})|^{2}}{|f(x_{0})|}  \right) + \frac{NU+1}{Nx_{0}^{2}} $$
---
# 3.3


>[!question] 3.3
>利用 $(1/n!)$ 是函数 $\exp(x)$ 的幂级数展开式中 $x^n$ 的系数这一特点，试通过鞍点积分法推导出这个系数的渐近公式，并将所得结果与对于 $n!$ 的斯特林公式进行比较。

$$\exp(x) = \sum_{n=0}^{\infty} \frac{1}{n!} x^{n} \implies \frac{1}{n!} = \frac{1}{2\pi i} \oint \frac{\exp(x)}{x^{n+1}}dx $$
其中
$$\frac{\exp(x)}{x^{n+1}} = \exp(x-(n+1)\ln x) ,\quad g(x) := x- (n+1)\ln x $$
令 $g'(x)=0$ 得 $x^{*}=n+1$ 此处 $g''(x^{*})=\frac{1}{n+1}$ 于是
$$\frac{1}{n!} \approx \frac{1}{2\pi i} e^{ g(x^{*}) } \int_{-\infty}^{+\infty} \exp\left( \frac{1}{2}g''(x^{*})(x-x^{*})^{2} \right)idx \approx \frac{e^{ g(x^{*}) }}{\sqrt{ 2\pi g''(x^{*}) }} = \frac{\exp\left( (n+1) \ln \frac{n+1}{e} \right)}{\sqrt{ \frac{2\pi}{n+1} }} $$
$$n! \approx \sqrt{ 2\pi(n+1) }\left( \frac{n+1}{e} \right)^{n+1} $$
对比斯特林公式
$$n! = \sqrt{ 2\pi n }\left( \frac{n}{e} \right)^{n} + \mathcal{O}(n^{-1}) $$
在 $n$ 很大时近似有 $n+1\approx n$ 于是两个式子等价

---
# 3.4

>[!question] 3.4
>试验证 $(k/\mathcal{N})\ln\Gamma$ 等于系统的（平均）熵，其中
>$$\Gamma(\mathcal{N}, U) = \sum_{\{n_r\}}' W\{n_r\}.$$
>试证明如果我们只取上述求和中最大的项（即相应于最概然分布集合的项 $W\{n_r\}$），则实质上我们求得了 $\ln\Gamma$ 的相同值。请把这个结果与方程 (3.6.3) 相比较。
>
>［令人惊奇吗？完全不用大惊小怪，请注意以下例子：对于所有的 $N$，对二项式系数 $\binom{N}{r}=N!/[r!(N-r)!]$ 求和给出
>$$\sum_{r=0}^N \binom{N}{r} = 2^N,$$
>因此，
>$$\ln\left(\sum_{r=0}^N \binom{N}{r}\right) = N\ln 2. \tag{a}$$
>现在，求和中的最大项相应于 $r\approx N/2$。因此，对于大的 $N$ 来说，最大项的对数几乎就等于：
>$$\ln\{N!\} - 2\ln\{(N/2)!\} \approx N\ln N - 2\cdot\frac{N}{2}\ln\frac{N}{2} = N\ln 2, \tag{b}$$
>此式与 (a) 是一致的］

---
# 3.5

>[!question] 3.5
>利用热力学系统的亥姆霍兹自由能 $A(N,V,T)$ 必然具有系统的广延性质这一特点，试证明：
>$$N\left(\frac{\partial A}{\partial N}\right)_{V,T} + V\left(\frac{\partial A}{\partial V}\right)_{N,T} = A.$$
>［请注意，这个结果就是众所周知的关系：$N\mu = A + PV \equiv G$。］

考虑两个等温等压等化学势的系统的组合有
$$(N_{1},V_{1},T_{1}) + (N_{2},V_{2},T_{1}) \to (N_{1}+N_{2},V_{1}+V_{2},T_{1}) $$
由于亥姆霍兹自由能有广延性，所以
$$A(N_{1},V_{1},T) + A(N_{2},V_{2},T) = A(N_{1}+N_{2},V_{1}+V_{2},T) $$
同理对于任意的 $\lambda$ 有
$$A(\lambda N,\lambda V,T) = \lambda A(N,V,T) $$
于是
$$\frac{\partial A(\lambda N,\lambda V,T)}{\partial \lambda} = N\left( \frac{\partial A}{\partial N} \right)_{V,T} + V\left( \frac{\partial A}{\partial V} \right)_{N,T} = A(V,N,T) = \frac{\partial (\lambda A(V,N,T))}{\partial \lambda} $$

---
# 3.6

>[!question] 3.6
>(a) 假设一个给定的统计系统的可及状态总数为 $\Omega$，试证明当所有的 $\Omega$ 态都是等概率地出现时，由方程 (3.3.13) 所给出的系统的熵具有最大值。  
>(b) 另一方面，倘若有一个系综，诸系统分享系综的能量（具有平均能量为 $\bar{E}$），试证明：当 $P_r \propto \exp(-\beta E_r)$ 时（其中 $\beta$ 为由给定的 $\bar{E}$ 值所确定的一个常数），由与上述形式上相同的表达式所给出的熵具有最大值。  
>(c) 进一步，倘若我们有一个系综，组成该系综的诸系统不仅分享系综的能量（具有平均能量为 $\bar{E}$），而且分享系综的粒子（具有平均粒子数为 $\bar{N}$），试证明：当 $P_{r,s} \propto \exp(-\alpha N_r - \beta E_s)$ 时（$\alpha$ 和 $\beta$ 分别为由给定的 $\bar{N}$ 和 $\bar{E}$ 所确定的常数），则由上述类似表达式所给出的熵具有最大值。

(a)
$$S = -k\sum_{r}P_{r}\ln P_{r} $$
由于对于任意的分布，必须满足 $\sum_{r}P_{r}=1$ ，考虑使用拉格朗日乘子法
$$L = \sum_{r}P_{r}\ln P_{r} + \lambda\left( \sum_{r}P_{r} - 1 \right) $$
要满足极值必有
$$\frac{\partial L}{\partial P_{r}} = 1+ \ln P_{r} + \lambda = 0 ,\quad \frac{\partial L}{\partial \lambda} = \sum_{r}P_{r} - 1 =0 $$
解得
$$P_{r} = e^{ -\lambda-1 } \implies \Omega e^{ -\lambda-1 } - 1 =  \implies P_{r} = \frac{1}{\Omega} $$
即对于 $P_{r}=\frac{1}{\Omega}$ 的分布，其熵取极值 $S=k\ln \Omega$，令取 $P_{0}=1,P_{r}=0$ 则 $S=0$ ，故当 $P_{r}=\frac{1}{\Omega}$ 时熵取极大值。

(b)
分布满足约束
$$\sum_{r}P_{r} = 1 ,\quad \sum_{r}P_{r}E_{r} = \bar{E} $$
类似的，也是考虑拉格朗日乘数法
$$L = \sum_{r}P_{r} \ln P_{r} + \alpha\left( \sum_{r}P_{r} - 1 \right) + \beta\left( \sum_{r}P_{r}E_{r} - \bar{E} \right)$$
$$\frac{\partial L}{\partial P_{r}} = 1 + \ln P_{r} + \alpha + \beta E_{r} = 0 $$
解得
$$P_{r} = \exp(-\beta E_{r}-\alpha-1) \propto \exp(-\beta E_{r}) $$
由拉格朗日乘子法知，这是 $S$ 取极值的解，由于存在 $S=0$ 的解所以 $P_{r}\propto \exp(-\beta E_{r})$ 一定是极大值解。

(c)
分布满足约束
$$\sum_{r,t}P_{r,t} = 1 , \quad \sum_{r,t}P_{r,t}E_{r} = \bar{E}  ,\quad \sum_{r,t}P_{r,t}N_{t} = \bar{N}$$
类似的当
$$P_{r,t}\propto \exp(-\beta E_{r} - \alpha N_{t}) $$
时系统的熵最大

---
# 3.7

>[!question] 3.7
>试证明，在相当一般的情形下，
>$$C_p - C_V \ge -k\left[ \frac{\partial}{\partial T}\left\{ T\left( \frac{\partial}{\partial T}\left( \frac{P}{kT} \right) \right)_V \right\} \right]_V > 0,$$
>并验证对于理想气体这个量就是 $Nk$。

粒子数不变
$$C_{P} = \left( \frac{\partial H}{\partial T} \right)_{P} = \left( \frac{\partial (U+PV)}{\partial T} \right)_{P} = \left( \frac{\partial U}{\partial T} \right)_{P} + P \left( \frac{\partial V}{\partial T} \right)_{P} $$
$$C_{V} = \left( \frac{\partial U}{\partial T} \right)_{V} $$
而
$$dU = -PdV + TdS $$
所以
$$\left( \frac{\partial U}{\partial T} \right)_{X} = T\left( \frac{\partial S}{\partial T} \right)_{X} - P\left( \frac{\partial V}{\partial T} \right)_{X} $$
$$\left( \frac{\partial U}{\partial T} \right)_{P} = T\left( \frac{\partial S}{\partial T} \right)_{P} - P\left( \frac{\partial V}{\partial T} \right)_{P} $$
$$\left( \frac{\partial U}{\partial T} \right)_{V} = T\left( \frac{\partial S}{\partial T} \right)_{V} $$
于是
$$\begin{align}
C_{P}-C_{V} &= T\left(  \left( \frac{\partial S}{\partial T} \right)_{P} - \left( \frac{\partial S}{\partial T} \right)_{V}  \right)  \\
&= T\left[  \left( \frac{\partial S}{\partial T} \right)_{V} + \left( \frac{\partial S}{\partial V} \right)_{T}\left( \frac{\partial V}{\partial T} \right)_{P} - \left( \frac{\partial S}{\partial T} \right)_{V} \right] \\
&= T\left( \frac{\partial S}{\partial V} \right)_{T}\left( \frac{\partial V}{\partial T} \right)_{P} \\
&= -T \left( \frac{\partial P}{\partial T} \right)_{V} \displaystyle\frac{\left( \frac{\partial P}{\partial T} \right)_{V}}{\left( \frac{\partial P}{\partial V} \right)_{T}}
\end{align}$$
而热力学稳定性要求恒温膨胀降压于是 
$$\left( \frac{\partial P}{\partial V} \right)_{T} <0 \implies C_{P} - C_{V} >0 $$

对于理想气体有
$$PV = NkT $$
$$\left( \frac{\partial P}{\partial T} \right)_{V} = -\frac{NkT}{V^{2}} , \quad \left( \frac{\partial P}{\partial V} \right)_{T} = \frac{Nk}{V} $$
所以
$$C_{P} - C_{V} = Nk $$

---
# 3.8

>[!question] 3.8
>试证明，对于理想气体，
>$$\frac{S}{Nk} = \ln\left( \frac{V}{N} \right) + T\left( \frac{\partial}{\partial T}\left( \frac{\ln Z}{N} \right) \right)_P.$$

$$A = -kT\ln Z $$
$$S = -\left( \frac{\partial A}{\partial T} \right)_{V,N} = k\ln Z + kT\left( \frac{\partial \ln Z}{\partial T} \right)_{V,N} $$
$$\frac{S}{Nk} = \frac{\ln Z}{N} + \frac{T}{N}\left( \frac{\partial \ln Z}{\partial T} \right)_{V,N} $$
对于理想气体
$$Z = \frac{1}{N!}(Z_{1})^{N} ,\quad Z_{1} = \frac{V}{h^{3}}(2\pi mkT)^{3/2} $$
$$\ln Z = N\ln V + N\cdot \frac{3}{2}\ln T - \ln N! + Const $$
$$\frac{\ln Z}{N} = \ln \frac{V}{N} + \frac{3}{2}\ln T - \frac{\ln N!}{N} + \ln N + Const $$
于是
$$\frac{S}{Nk} = \ln \frac{V}{N} + \frac{3}{2}\ln T + T\left( \frac{\partial }{\partial T} \frac{\ln Z}{N} \right)_{V,N} $$

---
# 3.9

>[!question] 3.9
>倘若一个单原子分子理想气体绝热膨胀到其初始体积的两倍，那么最后的压强与初始压强的比值是多少呢？倘若在此过程中给系统加入一定的热量，那么最后的压强将比上述情况下的压强是高还是低呢？试通过推导出 $P_f/P_i$ 比率的有关公式来给出答案。

对于单原子分子理想气体
$$U = \frac{3}{2}NkT ,\quad C_{V} = \frac{3}{2}R , \quad C_{P} = \frac{5}{2}R $$
绝热过程中 $dS = 0$ 满足绝热方程 $PV^{\gamma}=Const$ 于是
$$\frac{P_{f}}{P_{i}} = \left( \frac{V_{i}}{V_{f}} \right)^{\gamma} = \left( \frac{1}{2} \right)^{5/3} $$
若加入一定的热量，则将导致终态温度更高，由能量均分原理压强相较而言更高。

---
# 3.10

>[!question] 3.10
>(a) 抽出圆柱形汽缸中的活塞以增加氦气样品的体积，发现最后的压强 $P_f$ 等于初始压强 $P_i$ 乘以 $(V_i/V_f)^{1.2}$ 倍，其中 $V_i$ 和 $V_f$ 分别为初始体积和最后体积。假设乘积 $PV$ 总是等于 $\frac{2}{3}U$，试求该气体的 (i) 能量和 (ii) 熵在该过程中究竟是增加、保持常量，还是减少呢？  
>(b) 如果过程是可逆的，那么，当气体体积增大一倍时，外界对气体所作的功和气体所吸收的热量是多少？取 $P_i = 1\,\text{atm}$，$V_i = 1\,\text{m}^3$。

---
# 3.11

>[!question] 3.11
>对于按照 $PV^n = \text{常量}$ 的定律而变化的气体，当从体积 $V_1$ 压缩到体积 $V_2$ 时，试确定对气体所作的功和气体所吸收的热量。

$$W = -\int PdV = -\int_{V_{1}}^{V_{2}} \frac{C}{V^{n}} dV = nC\left( \frac{1}{V_{2}^{n+1}} - \frac{1}{V_{1}^{n+1}} \right) = \frac{P_{2}V_{2}-P_{1}V_{1}}{n-1} $$
$$\Delta U = nC_{V}(T_{2}-T_{1}) = \frac{C_{V}}{R}(P_{2}V_{2}-P_{1}V_{1}) $$
$$Q = \Delta U-W = (P_{2}V_{2} - P_{1}V_{1})\left( \frac{C_{V}}{R} - \frac{1}{n-1} \right) $$
---
# 3.12

>[!question] 3.12
>倘若一个经典系统的“自由体积” $v_f$ 由下列方程定义：
>$$v_f^N = \int e^{[\bar{U} - U(q_i)]/kT} \prod_{i=1}^N d^3q_i,$$
>其中，$\bar{U}$ 是系统的平均势能，$U(q_i)$ 是作为分子位形的函数的实际势能，试证明：
>$$S = Nk\left[ \ln\left\{ \frac{v_f}{N}\left( \frac{2\pi m kT}{h^2} \right)^{3/2} \right\} + \frac{5}{2} \right].$$
>在何种意义上才有理由把 $v_f$ 量称为该系统的“自由体积”呢？试通过研究一种特殊情况，即研究硬球气体的情形来证实本题的回答。

---
# 3.13

>[!question] 3.13
>(a) 试计算温度为 $T$，体积为 $V$，并由 $N_1$ 个质量为 $m_1$ 的分子和 $N_2$ 个质量为 $m_2$ 的分子所组成的理想气体的配分函数和主要的热力学性质。假定一个给定类型的分子彼此是不可分辨的，而一种类型的分子与另一种类型的分子之间是可以分辨的。  
>(b) 试把上述结果与由质量为 $m$ 的全部是同种类型的 $(N_1+N_2)$ 个分子所组成的理想气体的结果进行比较，这时 $m(N_1+N_2) = m_1 N_1 + m_2 N_2$。

---
# 3.14

>[!question] 3.14
>考虑 $N$ 个质量为 $m$ 的经典粒子组成的系统，粒子在一个体积为 $V = L^3$ 的立方盒子中运动。粒子之间通过短程对势 $u(r_{ij})$ 进行相互作用，并且每个粒子都与每个器壁通过短程作用势 $u_{\text{壁}}(z)$ 相互作用，这里 $z$ 是粒子与壁的垂直距离。试写出这个模型的拉格朗日函数，并利用勒让德变换确定哈密顿函数 $H$。  
>(a) 试证量 $P = -\left( \frac{\partial H}{\partial V} \right) = \frac{1}{3L^2}\left( \frac{\partial H}{\partial L} \right)$ 明显等于瞬时压强——即每单位面积上对器壁施加的力。  
>(b) 试通过盒子内部粒子的相对位置 $\mathbf{r}_i = L\mathbf{s}_i$ 来重构拉格朗日函数，其中所有变量 $\mathbf{s}_i$ 都处于一个单位立方体内。使用勒让德变换通过这组变量来确定哈密顿函数。  
>(c) 利用哈密顿函数的第二形式重新计算压强。证明现在压强包括三项贡献：  
> (1) 一项正比于动能；  
> (2) 一项与粒子对之间的作用力有关；  
> (3) 一项与作用在器壁上的力有关。  
>试证在热力学极限下，与其他两项相比第三项贡献可忽略不计。请阐释贡献 1 和贡献 2，并与位力物态方程 (3.7.15) 做比较。

(a) 拉式量为
$$L = \sum_{i=1}^{N} \frac{1}{2}m\mathbf{\dot{q}}^{2}_{i} - \sum_{i<j} u(|\mathbf{q}_{i}-\mathbf{q}_{j}|) + \sum_{i,wall} u_{wall}(z_{i}) $$
$$\mathbf{p}_{i} = -\frac{\partial L}{\partial \mathbf{\dot{q}}_{i}} = m\mathbf{\dot{q}}_{i} $$
$$H = \sum_{i} \mathbf{p}_{i}\cdot \mathbf{\dot{q}}_{i} - L = \sum_{i=1}^{N} \frac{\mathbf{\dot{p}}_{i}^{2}}{2m} + \sum_{i<j} u(|\mathbf{q}_{i}-\mathbf{q}_{j}|) - \sum_{i,wall} u_{wall}(z_{i}) $$
压强定义为
$$P = -\frac{\partial H}{\partial V} = \frac{1}{3L^{2}} \frac{\partial H}{\partial L} $$
(b) 按照要求
$$\mathbf{q}_{i} = L\mathbf{s}_{i} ,\quad \mathbf{\dot{q}}_{i} = L\mathbf{\dot{s}}_{i} $$
$$L = \sum_{i=1}^{N} \frac{1}{2}m(L\mathbf{\dot{s}}_{i} )^{2} - \sum_{i<j} u(L|\mathbf{s}_{i}-\mathbf{s}_{j}|) + \sum_{i,wall} u_{wall}(L\mathbf{s}_{i}) $$
$$\mathbf{p}_{i} = \frac{\partial L}{\partial \mathbf{\dot{s}}_{i}} = mL^{2}\mathbf{\dot{s}}_{i} $$
所以
$$H =  $$

(c) 
$$P = -\frac{1}{3L^{2}} \frac{\partial H}{\partial L} = \frac{1}{3V}\sum_{i} m\mathbf{v}_{i}^{2} + \frac{1}{3V}\sum_{i<j}\mathbf{r}_{ij}\cdot \mathbf{f}_{ij} + \frac{1}{3V}\sum $$
---
# 3.15

>[!question] 3.15
>试证明，由能量与动量关系为 $E = pc$（其中 $c$ 为光速）的 $N$ 个单原子分子所组成的极端相对论性气体的配分函数为：
>$$Z_N(V,T) = \frac{1}{N!}\left\{ \frac{8\pi V}{(hc)^3}(kT)^3 \right\}^N.$$
>试研究这个系统的热力学特性，特别是验证：
>$$PV = \frac{1}{3}U,\quad \frac{U}{N}=3kT,\quad \text{和}\quad \gamma = \frac{C_P}{C_V} = \frac{4}{3}.$$
>其次，利用逆公式 (3.4.7)，试推导出这个系统的态密度 $g(E)$ 的表达式。

$$\begin{align}
Z_{1} &= \frac{1}{h^{3}} \int d^{3}xd^{3}p \ e^{ -\beta pc } \\ & = \frac{V}{h^{3}} \int 4\pi p^{2}dp\ e^{ -\beta pc } \\ & = \frac{4\pi V}{(h\beta c)^{3}} \int_{0}^{\infty} x^{3}e^{ -x } dx \\ & = \frac{8\pi V}{(\beta hc)^{3}}
\end{align}$$
忽略分子间的相互作用则
$$Z_{N} = \frac{1}{N!}(Z_{1})^{N} = \frac{1}{N!}\left\{ \frac{8\pi V}{(hc)^3}(kT)^3 \right\}^N $$
$$U = -\frac{\partial }{\partial \beta}\ln Z_{N} = 3NkT $$
$$A = -kT\ln Z_{N} = 3NkT\ln \beta + -NkT\ln V + Const(N) $$
$$P = -\left( \frac{\partial A}{\partial V} \right)_{T,N} = \frac{NkT}{V} $$
所以
$$\frac{U}{N} = 3kT ,\quad PV=\frac{U}{3} $$
而
$$H = U+PV = 4NkT $$
$$C_{P} = \left( \frac{\partial H}{\partial T} \right)_{P,N} = 4Nk,\quad C_{V} = \left( \frac{\partial U}{\partial T} \right)_{V,N} = 3Nk $$
$$\gamma = \frac{C_{P}}{C_{V}} = \frac{4}{3} $$
至于态密度考虑到
$$Z_{N} = \int g(E)e^{ -\beta E } dE = \frac{(8\pi V)^{N}}{N!(hc)^{3N}} \beta^{-3N} $$
由拉普拉斯逆变换得到
$$g(E) = \frac{(8\pi V)^{N}}{N!(hc)^{3N}}\cdot (3N)!E^{-3N/2+1} $$
---
# 3.16

>[!question] 3.16
>试考虑与前一习题相类似的系统，但它是由 $3N$ 个在一维空间中运动的粒子所组成的，试证明在此情况下配分函数为：
>$$Z_{3N}(L,T) = \frac{1}{(3N)!}\left\{ \frac{2L}{hc}(kT) \right\}^{3N},$$
>这里 $L$ 为可资用空间的“长度”。试将这个系统的热力学特性和态密度与前一习题中的系统的相应结果进行比较。

但粒子的配分函数
$$Z_{1} = \frac{1}{h}\int dxdp\ e^{ -\beta pc } = \frac{2L}{\beta hc} $$
所以系统配分函数为
$$Z_{3N}(L,T) = \frac{1}{(3N)!}\left[ 2L \left( \frac{kT}{hc} \right) \right]^{3N} $$
类似的
$$A = -kT\ln Z_{3N} = 3NkT\ln \beta - 3NkT\ln L + Const(N) $$
$$U = -\frac{\partial }{\partial \beta}\ln Z_{3N} = \frac{3N}{\beta} = 3NkT $$
$$P = -\left( \frac{\partial A}{\partial L} \right)_{T,N} = \frac{3NkT}{L} \implies PL = 3NkT = U $$
$$H = U + PL = 6NkT $$
$$C_{V} = \left( \frac{\partial U}{\partial T} \right)_{V} = 3Nk ,\quad C_{P} = \left( \frac{\partial H}{\partial T} \right)_{V} = 6Nk $$
$$\gamma=\frac{C_{P}}{C_{V}} = 2 $$

---
# 3.17

>[!question] 3.17
>倘若我们取 (3.5.3) 式中的 $f(q,p)$ 等于 $\bar{U} - H(q,p)$，则显然有 $\langle f \rangle = 0$。从形式上看，这将意味着：
>$$\int [\bar{U} - H(q,p)] e^{-\beta H(q,p)} d\omega = 0.$$
>试从这个方程求出正则系综中系统的能量涨落表达式 (3.6.3)。

---
# 3.18

>[!question] 3.18
>试求证，对于正则系综中的一个系统而言，
>$$\langle (\Delta E)^3 \rangle = k^2\left\{ T^4\left( \frac{\partial C_V}{\partial T} \right)_V + 2T^3 C_V \right\};$$
>特别是，对于理想气体，
>$$\left\langle \left( \frac{\Delta E}{E} \right)^2 \right\rangle = \frac{2}{3N},\quad \left\langle \left( \frac{\Delta E}{E} \right)^3 \right\rangle = \frac{8}{9N^2}.$$

考虑
$$\langle E\rangle = U = -\frac{\partial \ln Z}{\partial \beta} $$
$$\langle(\Delta E)^{2}\rangle = \langle(E-U)^{2}\rangle = \frac{\partial^{2}\ln Z}{\partial \beta^{2}} = - \frac{\partial U}{\partial \beta} = kT^{2}C_{V} $$
而
$$\langle(\Delta E)^{3}\rangle = \langle(E-U)^{3}\rangle = \frac{\partial^{3}\ln Z}{\partial \beta^{3}} = \frac{\partial \langle(\Delta E)^{2}\rangle}{\partial \beta} = k^{2}\left[  T^{4}\left( \frac{\partial C_{V}}{\partial T} \right)_{V} + 2T^{3}C_{V}  \right] $$
对于理想气体
$$U = \frac{3}{2}NkT , \quad C_{V} = \frac{3}{2}Nk $$
$$\left\langle \left( \frac{\Delta E}{E} \right)^{2} \right\rangle = \frac{\langle(\Delta E)^{2}\rangle}{U^{2}} = \frac{2}{3N} $$
$$\left\langle \left( \frac{\Delta E}{E} \right)^3 \right\rangle = \frac{\langle(\Delta E)^{3}\rangle}{U^{3}} = \frac{8}{9N^{2}}$$

---
# 3.19

>[!question] 3.19
>考虑量 $dG/dt$ 的长时间平均行为，其中 $G = \sum_i \mathbf{q}_i \cdot \mathbf{p}_i$，求证：(3.7.5) 式成立就意味着 (3.7.6) 式也成立，反之亦然。

---
# 3.20

>[!question] 3.20
>假如一个统计系统中，粒子之间的势能 $u(r)$ 是粒子坐标的 $n$ 次齐次函数，试证这个系统的位力为：
>$$\mathcal{V} = -3PV - n\bar{U},$$
>因此，平均动能 $\bar{K}$ 为：
>$$\bar{K} = -\frac{1}{2}\mathcal{V} = \frac{1}{2}(3PV + n\bar{U}) = \frac{1}{n+2}(3PV + nE);$$
>这里 $\bar{U}$ 表示该系统的平均势能，而 $E = \bar{K} + \bar{U}$。请注意，这个结果不仅对经典系统成立，对量子系统也同样成立。

$$\mathcal{V} = \sum {\mathbf{q}}\cdot \mathbf{F} = \sum \mathbf{q}\cdot \mathbf{F}_{边界} -\sum {\mathbf{q}}\cdot \nabla u$$
由欧拉齐次定理
$$\sum \mathbf{q}\cdot \nabla u = n u $$
而
$$\sum \mathbf{q}\cdot \mathbf{F}_{边界} = \sum\oint \mathbf{q}\cdot \mathbf{n}PdS = \sum \int 3PdV = 3PV $$
所以
$$\mathcal{V} = -3PV - n \bar{u} $$
由位力定理
$$\bar{K} = -\frac{1}{2}\mathcal{\bar{V}} = \dots $$
---
# 3.21

>[!question] 3.21
>(a) 试计算在经典力学和量子力学两种情况下，一维谐振子按时间平均的动能和势能，并证明求得的结果与上一题所确立的结果（取 $n=2$）一致。  
>(b) 类似地基于 (i) 玻尔-索末菲模型和 (ii) 薛定谔模型考虑氢原子 ($n = -1$) 情形。  
>(c) 最后，考虑行星围绕太阳运动的两种情形：(i) 沿圆轨道运动；(ii) 沿椭圆轨道运动。

(a)
经典谐振子有
$$ $$
---
# 3.22

>[!question] 3.22
>设一非谐振子的回复力正比于位移的立方，试证其平均动能二倍于平均势能。

$$F = -kx^{3} \implies V = \frac{k}{4}x^{4} $$
由位力定理
$$\langle G\rangle  = 0 \implies 2\langle K\rangle = \langle xF\rangle $$
$$\langle K\rangle = \frac{1}{2} \langle kx^{4}\rangle = 2\langle U\rangle $$
---
# 3.23

>[!question] 3.23
>从经典正则配分函数 (3.5.5) 推导位力物态方程 (3.7.15) 式。试证明在热力学极限下，是粒子之间的项而不是那些来源于粒子与器壁相互作用的项占支配地位。

>[!question] 3.24
>试证明，在相对论情况下，能量均分定理化为：
>$$\left\langle m_0 u^2 \left( 1 - \frac{u^2}{c^2} \right)^{-1/2} \right\rangle = 3kT,$$
>其中 $m_0$ 是粒子的静止质量，$u$ 是粒子的速率。

Lemma. 对于正则变量有
$$\left\langle  x_{i}\frac{\partial H}{\partial x_{i}}  \right\rangle = kT $$

注意到
$$-\beta\int x_{i} \frac{\partial H}{\partial x_{i}} e^{ -\beta H } dx = \int x_{i} \frac{\partial }{\partial x_{i}}e^{ -\beta H } dx = x_{i} e^{ -\beta H }|_{边界} - \int e^{ -\beta H } dx = -1 $$
于是引理显然。代入 $x_{i}=p$ 即可
$$\left\langle  p_{i}\frac{\partial H}{\partial p_{i}}  \right\rangle = kT ,\quad \sum_{i=1}^{3} \left\langle  p_{i}\frac{\partial H}{\partial p_{i}}  \right\rangle = 3kT  $$
而对于相对论性粒子
$$H = \sqrt{ p^{2}c^{2} + m^{2}c^{4} } \implies \frac{\partial H}{\partial p_{i}} = u_{i} $$
$$p_{i} = \frac{mu_{i}}{\sqrt{ 1-u^{2} /c^{2} }} $$
于是
$$\left\langle m_0 u^2 \left( 1 - \frac{u^2}{c^2} \right)^{-1/2} \right\rangle = 3kT $$

>[!question] 3.25
>试提出一种分子运动论的论证方法，以证明 $\sum_i \mathbf{p}_i \cdot \dot{\mathbf{q}}_i$ 正好等于 $3PV$。并由此证明，当不考虑相对论性的情况时，$PV = NkT$。

>[!question] 3.26
>$s$ 维谐振子的能量本征值可写成：
>$$\varepsilon_j = \left( j + \frac{s}{2} \right) \hbar \omega; \quad j = 0, 1, 2, \ldots.$$
>试证明第 $j$ 个能级具有多重性为 $(j+s-1)! / j!(s-1)!$。试求 $N$ 个这样的振子组成的系统的配分函数和主要的热力学性质，并把所得结果与相应的 $sN$ 个一维振子系统的结果进行比较，特别要证明化学势 $\mu_s = s\mu_1$。



>[!question] 3.27
>对于由 $N$ 个量子力学谐振子组成的系统，利用逆公式 (3.4.7) 和配分函数 (3.8.15) 式，试求出 $\ln g(E)$ 的渐近表达式，并由此证明：
>$$\frac{S}{Nk} = \left( \frac{E}{N\hbar\omega} + \frac{1}{2} \right) \ln\left( \frac{E}{N\hbar\omega} + \frac{1}{2} \right) - \left( \frac{E}{N\hbar\omega} - \frac{1}{2} \right) \ln\left( \frac{E}{N\hbar\omega} - \frac{1}{2} \right).$$
>［提示：利用达尔文-福勒方法］

由
$$Z_{N}(\beta) = e^{ -N\beta \hbar \omega/2 } (1-e^{ -\beta \hbar \omega })^{N} $$
$$Z_{N}(\beta) = \int_{0}^{\infty} g(E)e^{ -\beta E }dE $$
由拉普拉斯变换知
$$\begin{align}
g(E) &  = \frac{1}{2\pi i} \int e^{ \beta E }Z_{N}(\beta)d\beta \\ & = \frac{1}{2\pi i} \int \exp\left[ \beta E - N\ln \left( \frac{1}{2\sinh(\beta \hbar \omega /2)} \right) \right]d\beta
\end{align}$$
令 $f(\beta) = \beta E - N\ln\left( 2\sinh\left( \beta \hbar \frac{\omega}{2} \right)^{-1} \right)$ 则鞍点条件为 $f'(\beta)=0$ 
$$E = N\hbar \omega\left[  \frac{1}{2} + \frac{1}{e^{ \beta_{0} \hbar \omega } - 1} \right] $$
令 $x=\frac{E}{N\hbar \omega}$ 则
$$e^{ \beta_{0} \hbar \omega } = \frac{2x+1}{2x-1} $$
$$f(\beta_{0}) = \frac{E}{\hbar \omega}\ln\left( \frac{2x+1}{2x-1} \right) - N\ln\left( \frac{4x^{2} -1}{8x} \right) $$
$$f''(\beta_{0}) = \frac{N}{\cosh^2(\beta_{0} \hbar \omega /2)}\left( \frac{\hbar \omega}{2} \right)^{2} = N\left( \frac{\hbar \omega}{2} \right)^{2}(4x^{2}-1) $$
于是 (参考 [[鞍点法推导分布]])
$$g(E) \approx \frac{1}{2\pi} e^{ -f(\beta_{0}) }\sqrt{ \frac{2\pi}{f''(\beta_{0})} } $$
$$\begin{align}
\ln g &  \approx f(\beta_{0}) - \frac{1}{2}\ln f''(\beta_{0}) + C \\ & = N\left[  \left( x+\frac{1}{2} \right)\ln\left( x+\frac{1}{2} \right) - \left( x-\frac{1}{2} \right) \ln\left( x-\frac{1}{2} \right)  \right] 
\end{align}$$
而 $S=k\ln g$ 所以
$$\begin{align}
\frac{S}{Nk} & =kN\left[  \left( x+\frac{1}{2} \right)\ln\left( x+\frac{1}{2} \right) - \left( x-\frac{1}{2} \right) \ln\left( x-\frac{1}{2} \right)  \right]
\end{align} $$


>[!question] 3.28
>(a) 当具有总能量为 $E$ 的 $N$ 个振子组成的系统处于热平衡态时，试问其中一个给定的振子处在量子态 $n$ 的概率 $P_n$ 是多少？［提示：利用 (3.8.25) 式。］并验证，当 $N \gg 1$，$\bar{n} \gg n$ 时，
>$$P_n \approx \left( \frac{\bar{n}}{1+\bar{n}} \right)^n \frac{1}{(1+\bar{n})^{1+\bar{n}}},$$
>其中 $\bar{n} = E/N\hbar\omega$。  
>(b) 当具有总能量为 $E$ 的 $N$ 个单原子分子组成的理想气体系统处于热平衡态时，试求证一个给定的分子，其能量在 $\varepsilon$ 附近所具有的概率正比于 $\exp(-\beta \varepsilon)$，其中 $\beta = 3N/2E$。［提示：利用 (3.5.16) 式并假设 $N \gg 1$ 和 $E \gg \varepsilon$。］

>[!question] 3.29
>一维经典非谐振子的势能可以写成：
>$$V(q) = c q^2 - g q^3 - f q^4,$$
>这里 $c, g$ 和 $f$ 都是正的常数；当然可以假定 $g$ 和 $f$ 的数值是很小的。试证明非谐项对系统的热容量的一级贡献为：
>$$\frac{3k^2 T}{c^2}\left( 2f + \frac{15g^2}{4c} \right),$$
>而位置坐标 $q$ 的平均值求至相同量级为：
>$$\frac{3g kT}{4 c^2}.$$

>[!question] 3.30
>一个量子力学的一维非谐振子的能级可以近似表示为：
>$$\varepsilon_n = \left( n+\frac{1}{2} \right) \hbar\omega - x \left( n+\frac{1}{2} \right)^2 \hbar\omega, \quad n = 0, 1, 2, \ldots.$$
>通常参数 $x \ll 1$，表示非谐度。试证明，当取 $x$ 到一级和 $u \equiv \hbar\omega/kT$ 到第四级时，则 $N$ 个这样的振子组成的系统的比热为：
>$$C = Nk\left[ (1-4x)\left( \frac{u}{e^u-1} \right)^2 e^u + 4x\left( \frac{u}{e^u-1} \right)^4 e^u (e^u+1) \right].$$
>请注意，修正项随温度而增加。

系统配分函数为
$$\begin{align}
Z &  = \sum_{n=0}^{\infty}\exp\left[ -\beta\left( n+\frac{1}{2} \right)\hbar \omega - x\beta\left( n+\frac{1}{2} \right)^{2}\hbar \omega \right] \\ & \approx \sum_{n=0}^{\infty} \exp\left[ -\beta\left( n+\frac{1}{2} \right)\hbar \omega \right]\left[ 1-x\beta \hbar \omega\left( n+\frac{1}{2} \right)^{2} \right]
\end{align}$$
令 $q=\exp(-\beta \hbar \omega)$ 则
$$\sum_{n=0}^{\infty} \left( n+\frac{1}{2} \right)^{2}q^{n} = \frac{q(1+q)}{(1-q)^{3}} + \frac{q}{(1-q)^{2}} + \frac{1}{4(1-q)} $$
$$\begin{align}
Z & = \sum_{n=0}^{\infty} q^{n+1/2}\left( 1-x\beta \hbar \omega\left( n+\frac{1}{2} \right)^{2} \right) \\ & = \sum_{n=0}^{\infty} q^{n+1/2}\left[  1 - x\beta \hbar \omega\left(  \frac{q(1+q)}{(1-q)^{3}} + \frac{q}{(1-q)^{2}} + \frac{1}{4(1-q)}  \right)  \right] \\ & = \frac{q^{1/2}}{1-q}    - x\beta \hbar \omega q^{1/2}\left(  \frac{q(1+q)}{(1-q)^{3}} + \frac{q}{(1-q)^{2}} + \frac{1}{4(1-q)}  \right)  
\end{align} $$
于是
$$U = -\frac{\partial Z}{\partial \beta} $$
$$C = \frac{\partial U}{\partial T} $$


>[!question] 3.31
>按照第 3.8 节的方法，试研究仅由两个本征值即 $0$ 和 $\varepsilon$ 表征的 $N$ 个“费米振子”组成的系统的统计力学特性。

>[!question] 3.32
>已知给定物理系统可资用的量子态是：  
>(i) 一群具有共同能量值 $\varepsilon_1$ 的 $g_1$ 个等概率的态；  
>(ii) 一群具有共同能量值 $\varepsilon_2$ 的 $g_2$ 个等概率的态，$\varepsilon_2 > \varepsilon_1$。  
>试证明该系统的熵为：
>$$S = -k\left[ p_1 \ln(p_1/g_1) + p_2 \ln(p_2/g_2) \right],$$
>这里 $p_1, p_2$ 分别为该系统处于第 1 群和第 2 群的状态中的概率，且 $p_1 + p_2 = 1$。  
>(a) 假定 $p_i$ 由正则分布给出，试证明：
>$$S = k\left[ \ln g_1 + \ln\{ 1 + (g_2/g_1) e^{-x} \} + \frac{x}{1 + (g_1/g_2) e^x} \right],$$
>这里 $x = (\varepsilon_2 - \varepsilon_1)/kT$，且假定为正值。并将 $g_1 = g_2 = 1$ 的特殊情形与前道习题的费米振子的结果进行比较。  
>(b) 试根据由系统的配分函数推导出来的熵 $S$ 来验证上述表达式的正确性。  
>(c) 试检验当 $T \to 0$ 时，$S \to k\ln g_1$，并阐明这个结果的物理意义。

>[]
>

>[!question] 3.33
>硫酸钆盐服从朗之万的顺磁性理论，直至开氏温度大约几度左右，其分子磁矩为 $7.2 \times 10^{-23}\,\text{A}\cdot\text{m}^2$。试求在磁通量密度为 $2\,\text{Wb/m}^2$ 的磁场中，温度为 $2\,\text{K}$ 下该盐的磁饱和度。

>[!question] 3.34
>氧是一种服从朗之万的顺磁性理论的顺磁性气体，在 $293\,\text{K}$ 和 $1\,\text{atm}$ 下，其每单位体积的磁化率为 $1.80 \times 10^{-5}$ MKS 单位。试求氧的分子磁矩，并把结果与玻尔磁子（约等于 $9.27 \times 10^{-24}\,\text{A}\cdot\text{m}^2$）进行比较。

>[!question] 3.35
>(a) 一个由 $N$ 个无相互作用的双原子分子（每个分子的电偶极矩为 $\mu$）所组成的气体系统，处在强度为 $\mathcal{E}$ 的外电场中，分子的能量将由平动能、转动能，再加上在外场中的取向的势能所组成：
>$$\varepsilon = \frac{\mathbf{p}^2}{2m} + \left\{ \frac{p_\theta^2}{2I} + \frac{p_\phi^2}{2I\sin^2\theta} \right\} - \mu\mathcal{E}\cos\theta,$$
>[89] 这里 $I$ 是分子的转动惯量。试研究包括电极化强度和介电常量在内的系统的热力学性质。假设 (i) 系统是一个经典系统；(ii) $|\mu\mathcal{E}| \ll kT$。  
>(b) $\text{H}_2\text{O}$ 分子的电偶极矩为 $1.85 \times 10^{-18}$（静电单位）。试在上述理论的基础上计算在 $100^\circ\text{C}$ 和 $1\,\text{atm}$ 下水蒸气的介电常数。

>[!question] 3.36
>试考虑取向分别在 $(\theta,\phi)$ 和 $(\theta',\phi')$ 方向的一对电偶极子 $\mu$ 和 $\mu'$；假定它们的中心之间的距离 $R$ 是固定的。在此取向情况下，势能为：
>$$-\frac{\mu\mu'}{R^3}\{ 2\cos\theta\cos\theta' - \sin\theta\sin\theta'\cos(\phi-\phi') \}.$$
>现在，考虑该电偶极子处在热平衡态下，它们的取向由正则分布所支配。试证明在高温下偶极子之间的平均作用力为：
>$$-\frac{2\mu^2\mu'^2}{kT R^7}\hat{\mathbf{R}},$$
>$\hat{\mathbf{R}}$ 是联心线方向的单位矢量。

>[!question] 3.37
>试计算磁偶极子系统的配分函数的高温近似值。求证在一般的情况下，居里常量为：
>$$C_J = \frac{N\mu_{\text{eff}}^2}{3k},$$
>并由此推导公式 (3.9.26)。

>[!question] 3.38
>用积分来代替 (3.9.18) 式中的求和，试求 $Q_1(\beta)$ 的值，并讨论由此得出的热力学量。试把这些结果与从朗之万理论所得出的结果进行比较。

>[!question] 3.39
>设银蒸气原子或平行于外磁场方向排列，或是反平行排列，并且每一个原子都具有磁矩 $\mu_B$ ($g = 2, J = \frac{1}{2}$)，试求在磁通量密度为 $0.1\,\text{Wb/m}^2$ 的磁场中，温度为 $1000\,\text{K}$ 的银蒸气，平行于或反平行于磁场方向的原子各占的份额。

>[!question] 3.40
>(a) 试求证，对于任何可磁化物质在恒定磁场 $H$ 和恒定平均磁化强度 $M$ 时的热容量之间的关系式为：
>$$C_H - C_M = -T\left( \frac{\partial H}{\partial T} \right)_M \left( \frac{\partial M}{\partial T} \right)_H.$$
>(b) 试求证，对于服从居里定律的顺磁性物质，
>$$C_H - C_M = \frac{C H^2}{T^2},$$
>其中方程式右边的 $C$ 表示给定样品的居里常量。

>[!question] 3.41
>将由 $N$ 个自旋所组成并处于负温度 ($E > 0$) 下的系统与一个由 $N'$ 个分子组成的理想气体温度计相接触。试问，它们相互处于平衡状态时的性质会是怎样的？它们的共同温度将会是正值还是负值？它将会以何种方式受到比率 $N'/N$ 的影响？

>[!question] 3.42
>在微正则系综下考虑 3.10 节研究过的 $N$ 个磁偶极子的系统。写出该系统能量为 $E$ 时可能的微观态的数目 $\Omega(N,E)$，计算 $S(N,E)$ 和 $T(N,E)$，并将你的结果与 (3.10.8) 式和 (3.10.9) 式进行比较。

>[!question] 3.43
>考虑一个带电粒子（非偶极子）系统，它遵循经典力学和经典统计。试证明该系统的磁化率恒等于零 (Bohr-van Leeuwen 定理)。  
>［请注意，存在磁场 $\mathbf{H} (= \nabla\times\mathbf{A})$ 时，这个系统的哈密顿函数将是 $\left( \mathbf{p}_j + \frac{e_j}{c}\mathbf{A}(\mathbf{r}_j) \right)^2$ 的函数，而不仅是 $\mathbf{p}_j^2$ 的函数。我们必须证明系统的配分函数与外场无关。］

>[!question] 3.44
>熵 $S$ 的表达式 (3.3.13) 式等价给出了香农所定义的一条消息中所包含的信息：
>$$I = -\sum_r P_r \ln P_r$$
>(Shannon, 1949)，其中 $P_r$ 表示消息 $r$ 的概率。  
>(a) 求证：若所有消息的概率都是相同的，则信息量具有最大值。任何其他的概率分布都导致信息量减少。以英语为例，“e” 比 “z” 更常用，所以 $P_e > P_z$，因此，在英语消息中每个字符的信息量是小于可能达到的最优值的（最优值基于英语文本中所用到的不同字符的数目）。  
>(b) 文本中的信息量也受该文本中字符之间的关联所影响。例如，在英语中，跟在 “q” 的后面的总是 “u”，这样这对字符所包含的信息量就同单独的 “q” 一样。用 $r$ 标识的字符后面紧跟 $r'$ 字符的概率为 $P_{r,r'} = P_r P_{r'} G_{r,r'}$，其中 $G_{r,r'}$ 是字符对关联函数。若一对字符没有关联，则 $G_{r,r'} = 1$。试证明若字符是无关联的，则双字符消息中所包含的信息量两倍于单字符消息的信息量，而关联 ($G_{r,r'} \neq 1$) 会使得信息量减少。［提示：利用不等式 $\ln x \le x-1$。］  
>(c) 试编写一个计算机程序，通过确定单字符的概率 $P_r$ 和字符对的关联 $G_{r,r'}$，来确定文本中每个字符的信息量。计算机通常以每个字符占一个完整的字节的方式来存储信息。由于一个字节能存储 256 个不同的消息，所以每字节所能够包含的信息量是 $\ln 256 = 8\ln 2 \equiv 8$ 比特。试证明你的文本文件中每个字符的信息量比 8 比特要小得多，并解释为什么无损（不牺牲文件所包含的任何信息）减小计算机文件大小的文件压缩算法是可能的。
