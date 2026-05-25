---
up:
  - "[[写题]]"
---

# 习题 3.1

>[!question] 习题 3.1
>两个同心球面，半径分别为 $a$、$b$（$b > a$），每个球面均被同一水平面分割为两个半球面。内球的上半球面和外球的下半球面保持电势 $V$，另一半球面电势为零。
>
>将区域 $a \leq r \leq b$ 中的电势以勒让德多项式级数形式表示。至少包含直至 $l = 4$ 的项。在极限情况 $b \to \infty$ 和 $a \to 0$ 下，将你的解与已知结果进行对比。

问题有轴对称性, 电势可以表达为:
$$\Phi(r,\theta) = \sum_{l=0}^{\infty} [ A_{l}r^{l} + B_{l}r^{-l-1} ] P_{l}(\cos \theta)  $$
边界条件是:
$$\Phi\left( a , 0\le \theta \le \frac{\pi}{2} \right) = \Phi\left( b, \frac{\pi}{2} \le \theta \le \pi \right) = V , \quad \Phi\left( a, \frac{\pi}{2} \le \theta \le \pi \right) = \Phi\left( b,0\le \theta \le \frac{\pi}{2} \right)=0 $$
于是
$$\Phi(a,\theta) = \sum_{l=0}^{\infty} [A_{l}a^{l} + B_{l}a^{-l-1}] P_{l}(\cos \theta) = f_{a}(\theta) $$
$$A_{l}a^{l} + B_{l}a^{-l-1} = \frac{2l+1}{2}\int_{-1}^{1} f_{a}(x)P_{l}(x)dx = \frac{2l+1}{2}V \int_{0}^{1}P_{l}(x)dx \tag{a}$$
而
$$I_{l}=\int_{0}^{1}P_{l}(x)dx = \left\{ \begin{gather}
1 & l=0 \\
\frac{(-1)^{(l-1)/2}(l-1)!}{2^{l}\left( \frac{l-1}{2} \right)^{2}\left( \frac{l+1}{2} \right)^{2}}  & l \text{ odd} \\
0 & l \text{ even}
\end{gather} \right. \tag{!}$$
另一方面 
$$\Phi(b,\theta) = \sum_{l=0}^{\infty} [A_{l}b^{l} + B_{l}b^{-l-1}]P_{l}(\cos \theta) = f_{b}(\theta) $$
$$A_{l}b^{l} + B_{l}b^{-l-1} = \frac{2l+1}{2}V \int_{-1}^{0}P_{l}(x)dx = \frac{2l+1}{2}V(-1)^{n}\int_{0}^{1}P_{l}(x) dx \tag{b}$$
由 $(a),(b),(!)$ 可以解得: 
$$\begin{gather}
A_{0}=\frac{V}{2}, & A_{1}=-\frac{3V}{4} \frac{a^{2}+b^{2}}{b^{3}-a^{3}}, & A_{2}=0, & A_{3}=-\frac{7V}{16} \frac{a^{4}+b^{4}}{a^{7}-b^{7}}, & A_{4}=0, & \dots \\
B_{0}=0, & B_{1}=\frac{3V}{4} \frac{a^{2}b^{2}(a+b)}{b^{3}-a^{3}} , & B_{2}=0, & B_{3}=\frac{7V}{16} \frac{a^{4}b^{4}(a^{3}+b^{3})}{a^{7}-b^{7}}, & B_{4}=0, & \dots
\end{gather} $$
于是 $b\to \infty$ 时
$$\Phi = \frac{V}{2} + \frac{3V}{4} \frac{a^{2}}{r^{2}}\cos \theta - \frac{7V}{16} \frac{a^{4}}{r^{4}} \frac{5\cos^{3}\theta - 3\cos \theta}{2} + \dots $$
 $a\to \infty$ 时
 $$\Phi = \frac{V}{2} - \frac{3V}{4} \frac{r}{b}\cos \theta + \frac{7V}{16} \frac{r^{3}}{b^{3}} \frac{5\cos^3\theta-3\cos \theta}{2} + \dots $$

# 习题 3.2

>[!question] 习题 3.2
>一个半径为 $R$ 的球面，电荷均匀分布在其表面上，密度为 $Q/4\pi R^2$，除了北极的一个球形帽，定义为圆锥 $\theta = \alpha$。
>
>(a) 证明球内的电势可以表示为
>
>$$\Phi = \frac{Q}{8\pi\epsilon_0} \sum_{l=0}^{\infty} \frac{1}{2l+1} \left[ P_{l+1}(\cos\alpha) - P_{l-1}(\cos\alpha) \right] \frac{r^l}{R^{l+1}} P_l(\cos\theta)$$
>
>其中，对于 $l = 0$，$P_{l-1}(\cos\alpha) = -1$。球外的电势是多少？
>
>(b) 求原点处电场的大小和方向。
>
>(c) 讨论当球形帽（1）非常小，和（2）如此之大以至于带电荷区域变为南极的一个非常小的帽时，电势（部分 a）和电场（部分 b）的极限形式。

## (a) 电势表达

边界条件有点棘手, 考虑格林函数法
$$\sigma(\theta) = \left\{ \begin{gather}
0 & 0<\theta<\alpha \\
\frac{Q}{4\pi R^{2}}  & \alpha<\theta<\pi
\end{gather} \right. $$
$$\Phi(r,\theta) = \frac{1}{4\pi\varepsilon_{0}} \int \sigma(\theta')G(r,\theta;r',\theta') dS = \frac{1}{4\pi\varepsilon_{0}} \int \frac{\sigma(\theta')}{|\mathbf{x}-\mathbf{x}'|} R^{2}\sin \theta' d\theta' d\phi' $$
其中当 $r<R$ 时
$$\frac{1}{|\mathbf{x}-\mathbf{x}'|} = \sum_{l=0}^{\infty} \frac{r^{l}}{R^{l+1}}P_{l}(\cos \gamma) $$
再使用加法公式 $\int_{0}^{2\pi}P_{l}(\cos \gamma)d\phi'=2\pi P_{l}(\cos \theta)P_{l}(\cos \theta')$ 就得到了
$$\Phi(r,\theta) = \frac{Q}{8\pi\varepsilon_{0}}\sum_{l=0}^{\infty} \frac{r^{l}}{R^{l+1}}P_{l}(\cos \theta) \int_{-1}^{\cos \alpha} P_{l}(x)dx $$
考虑勒让德多项式的递推公式
$$P_{l}(x) = \frac{P'_{l+1}(x)-P'_{l-1}(x)}{2l+1} $$
$$\int_{-1}^{\cos\alpha} P_{l}(x)dx = \frac{P_{l+1}(\cos \alpha)-P_{l-1}(\cos \alpha)}{2l+1} $$
所以球内的电势为: 
$$\Phi(r<R,\theta) = \frac{Q}{8\pi\epsilon_0} \sum_{l=0}^{\infty} \frac{1}{2l+1} \left[ P_{l+1}(\cos\alpha) - P_{l-1}(\cos\alpha) \right] \frac{r^l}{R^{l+1}} P_l(\cos\theta)$$
对于球外的情况, 由于
$$\frac{1}{|\mathbf{x}-\mathbf{x}'|} = \sum_{l=0}^{\infty} \frac{R^{l}}{r^{l+1}}P_{l}(\cos \gamma) $$
可见只是把 $r^{l} / R^{l+1}$ 替换为了 $R^{l} / r^{l+1}$ 所以球外的电势表达为: 
$$\Phi(r>R,\theta) = \frac{Q}{8\pi\epsilon_0} \sum_{l=0}^{\infty} \frac{1}{2l+1} \left[ P_{l+1}(\cos\alpha) - P_{l-1}(\cos\alpha) \right] \frac{R^l}{r^{l+1}} P_l(\cos\theta) $$

## (b) 球心处电场

实际上我们可以考虑将电势按 $r$ 级数展开: 
$$\Phi = \frac{Q}{8\pi\varepsilon_{0}}(\cos \alpha+1) - \frac{Q\sin^2\alpha}{16\pi \varepsilon_{0}R^{2}}r\cos \theta + \mathcal O(r^{2}) $$
$$\mathbf{E} = -\nabla \Phi = \frac{Q\sin ^{2}\alpha}{16\pi\varepsilon_{0}R^{2}} \hat{\mathbf{z}} + \mathcal O(r) $$
于是在球心处
$$\mathbf{E} = \frac{Q\sin ^{2}\alpha}{16\pi\varepsilon_{0}R^{2}} \hat{\mathbf{z}} $$

## (c) 南北极极限

当 $\alpha\to 0$ 时 $\cos \alpha\to 1$ 于是
$$P_{l+1}(\cos \alpha) - P_{l-1}(\cos \alpha) = \left(  1 - \frac{(l+1)(l+2)}{2}\alpha^{2} \right) - \left(  1 - \frac{(l-1)l}{2}\alpha  \right) + \mathcal o(\alpha^{3}) \sim - \frac{2l+1}{2}\alpha^{2} $$
所以
$$\Phi\sim \frac{Q}{8\pi\varepsilon_{0}} \sum_{l=0}^{\infty} \left( -\frac{\alpha^{2}}{2} \right) \frac{r^{l}}{R^{l+1}} P_{l}(\cos \theta) = -\frac{Q}{16\pi\varepsilon_{0}R} \frac{1}{\sqrt{ R^{2} + r^{2} - 2Rr\cos \theta }} \alpha^{2} $$
$$\mathbf{E} \sim \frac{Q}{16\pi\varepsilon_{0}R^{2}}\alpha^{2} \hat{\mathbf{z}} $$
当 $\alpha\to \pi$ 时实际上等效于将上面的情况的电荷符号反转然后再均匀的铺一层 $\sigma$ 最后将球倒过来(注意这里进行了一次宇称操作所以电场方向反转一次), 所以
$$\Phi \sim \frac{Q}{16\pi\varepsilon_{0}R} \frac{1}{\sqrt{ R^{2} + r^{2} - 2Rr\cos \theta }} (\pi-\alpha)^{2} $$
$$\mathbf{E} \sim \frac{Q}{16\pi \varepsilon_{0}R^{2}}(\pi-\alpha)^{2} \hat{\mathbf{z}} $$
实际上纯粹从数学上也不难推导, 当 $\alpha\to \pi$ 时 $\cos \alpha\to-1$ 再考虑到 $P_{l}(-x) = (-1)^{l}P_{l}(x)$ 就得到一样的结果了. 


# 习题 3.3

>[!question] 习题 3.3
>一个半径为 $R$ 的薄平导电圆盘位于 $x-y$ 平面，中心在原点，并保持固定电势 $V$。已知固定电势下圆盘上的电荷密度与 $(R^2 - \rho^2)^{-1/2}$ 成正比，其中 $\rho$ 是从圆盘中心向外的距离，
>
>(a) 证明当 $r > R$ 时，电势为
>
>$$\Phi(r, \theta, \phi) = \frac{2V}{\pi} \frac{R}{r} \sum_{l=0}^{\infty} \frac{(-1)^l}{2l+1} \left( \frac{R}{r} \right)^{2l} P_{2l}(\cos \theta)$$
>
>(b) 求 $r < R$ 时的电势。
>
>(c) 圆盘的电容是多少？

## (a)(b) 电势表达

设 $\sigma(\rho)=\frac{CV}{\sqrt{ R^{2} - \rho^{2} }}$ 则
$$V = \Phi(0,\theta) = \frac{1}{4\pi\varepsilon_{0}} \int \frac{\sigma(\rho)}{|\mathbf{x}-\mathbf{x}'|} dS = \frac{CV}{4\pi\varepsilon_{0}} \int_{\rho<R} \frac{1}{\sqrt{ R^{2} - \rho^{2} }\rho} \cdot \rho d\rho d\phi = \frac{\pi CV}{4\varepsilon_{0}}  $$
$$\sigma(\rho) = \frac{4\varepsilon_{0}V}{\pi} \frac{1}{\sqrt{ R^{2} - \rho^{2} }} $$
由格林函数
$$\Phi(r,\theta) = \frac{1}{4\pi\varepsilon_{0}} \int \frac{\sigma(\rho')}{|\mathbf{x}-\mathbf{x}'|} dS $$
$$\frac{1}{|\mathbf{x}-\mathbf{x}'|} = \sum_{l=0}^{\infty} \frac{r_{<}^{l}}{r_{>}^{l+1}} P_{l}(\cos \gamma) = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} \frac{4\pi}{2l+1} \frac{r_{<}^{l}}{r_{>}^{l+1}} Y^{*}_{lm}(\theta,\phi) Y_{lm}(\theta',\phi') $$
其中 $\cos \gamma = \cos \theta \cos \theta' +\sin \theta \sin \theta'\cos(\phi-\phi')$ 由于对 $\phi'$ 积分一圈第二项的贡献为零, 盘在赤道上所以 $\cos \theta'=0$ 于是只用考虑 $m=0$ 时的贡献
$$\frac{1}{|\mathbf{x}-\mathbf{x}'|} = \sum_{l=0}^{\infty} 2\pi \cdot \frac{r_{<}^{l}}{r_{>}^{l+1}} P_{l}(\cos \theta) P_{l}(0) $$

当 $r>R$ 时
$$\begin{align}
\Phi(r,\theta) &= \frac{1}{4\pi\varepsilon_{0}}  \int_{0}^{R} \frac{4\varepsilon_{0}V}{\pi} \frac{1}{\sqrt{ R^{2} - \rho'^{2} }} \rho'd\rho' \sum_{l=0}^{\infty} 2\pi \cdot  \frac{\rho'^{l}}{r^{l+1}}  P_{l}(\cos \theta) P_{l}(0)  \\
&= \frac{2V}{\pi} \sum_{l=0}^{\infty} P_{l}(\cos \theta) P_{l}(0) \frac{1}{r^{l+1}} \int_{0}^{R} \frac{\rho^{l+1}}{\sqrt{ R^{2} - \rho^{2} }} d\rho 
\end{align}$$
其中设 $\rho=R\sin p$ 则
$$\begin{align}
I = \int_{0}^{\pi/2} \frac{\sin^{l+1}p}{\cos p}\cdot \cos pdp = \int_{0}^{\pi/2} \sin^{l+1} p dp = \frac{\Gamma\left( \frac{l+2}{2} \right)\Gamma\left( \frac{1}{2} \right)}{2\Gamma\left( \frac{l+3}{2} \right)}
\end{align} $$
考虑到只有当 $l$ 为偶数时 $P_{l}(0)\not= 0$ (其实是系统对称性要求) 所以
$$\Phi(r,\theta) = \frac{2V}{\pi} \frac{R}{r} \sum_{l=0}^{\infty} P_{2l}(0) \left( \int_{0}^{\pi/2} \sin^{2l+1}pdp \right)  \left( \frac{R}{r} \right)^{2l} P_{2l}(\cos \theta) $$
其中
$$P_{2l}(0) = \frac{(-1)^{l}(2l+1)!!}{(2l+1)(2l)!!} = \frac{(-1)^{l}(2l)!}{2^{2l}(l!)^{2}}  $$
$$\int_{0}^{\pi/2} \sin^{2l+1}xdx = \frac{(2l)!!}{(2l+1)!!} = \frac{4^{l}(l!)^{2}}{(2l+1)!} $$
$$ P_{2l}(0) \left( \int_{0}^{\pi/2} \sin^{2l+1}pdp \right) = \frac{(-1)^{l}(2l)!}{2^{2l}(l!)^{2}} \cdot \frac{4^{l}(l!)^{2}}{(2l+1)!} = \frac{(-1)^{l}}{2l+1} $$
所以
$$\Phi(r,\theta) = \frac{2V}{\pi} \frac{R}{r} \sum_{l=0}^{\infty} \frac{(-1)^{l}}{2l+1} \left( \frac{R}{r} \right)^{2l} P_{2l}(\cos \theta) $$

当 $r<R$ 时
$$\Phi(r,\theta) = \frac{1}{4\pi\varepsilon_{0}} \int_{0}^{R} \frac{4\varepsilon_{0}V}{\pi} \frac{1}{\sqrt{ R^{2} - \rho^{2} }}\rho d\rho \sum_{l=0}^{\infty} 2\pi \frac{r^{l}}{\rho^{l+1}} P_{l}(\cos \theta) P_{l}(0) $$
可见唯一的区别是 $\rho^{l} / r^{l+1}\to r^{l} / \rho^{l+1}$ 所以对应的有
$$\Phi(r,\theta) = \frac{2V}{\pi} \sum_{l=0}^{\infty} P_{2l}(0) \left(  \int_{0}^{\pi/2} \sin^{2l+1} xdx \right) \left( \frac{r}{R} \right)^{2l} P_{2l}(\cos \theta) $$
所以答案是
$$\Phi(r,\theta) = \frac{2V}{\pi} \sum_{l=0}^{\infty} \frac{(-1)^{l}}{2l+1} \left( \frac{R}{r} \right)^{2l} P_{2l}(\cos \theta) $$

## (c) 电容

先算带电量
$$Q = 2\pi\int_{0}^{R} \frac{4\varepsilon_{0}V}{\pi} \frac{1}{\sqrt{ R^{2} - \rho^{2} }} \rho d\rho = 8\varepsilon_{0}RV $$
$$C = \frac{Q}{V} = 8\varepsilon_{0}R $$



# 习题 3.4

>[!question] 习题 3.4
>一个内半径为 $a$ 的空心导电球面被一组平面分割成偶数个相等的部分；这些平面的交线是 $z$ 轴，且在角度 $\phi$ 上均匀分布。（这些部分就像苹果楔形块上的皮，或者像地球表面上相邻经线之间的区域。）这些部分交替地保持固定电势 $\pm V$。
>
>(a) 对于一般的 $2n$ 个部分的情况，建立球内电势的级数表示，并将系数的计算推进到足以精确确定哪些系数不为零。对于非零项，将系数表示为关于 $\cos \theta$ 的积分。
>
>(b) 对于 $n = 1$（两个半球）的特殊情况，明确求出包括 $l = 3$ 项在内的电势表达式。通过坐标变换验证这可以简化为第 3.3 节中的结果 (3.36)。

## (a) 电势表达

球内电势展开为: 
$$\Phi(r,\theta,\phi) = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} A_{lm} r^{l} Y_{lm}(\theta,\phi) $$
边界条件为: 
$$\Phi(a,\theta,\phi) = f(\phi) = \frac{4V}{\pi} \sum_{k=0}^{\infty} \frac{1}{2k+1} \sin n(2k+1)\phi $$
$$a^{l} A_{lm} = \int f(\phi) Y_{lm}^{*}(\theta,\phi) d\Omega :=I $$
$$\begin{align}
I_{lm} &= \sum_{k=0}^{\infty} \frac{4V}{\pi} \frac{1}{2k+1} \sqrt{ \frac{2l+1}{4\pi} \frac{(l-m)!}{(l+m)!} } \int_{0}^{\pi} \sin \theta d\theta \int_{0}^{2\pi} \sin n(2k+1)\phi P^{m}_{l}(\cos \theta) e^{ im\phi } d\phi \\
&= \sum_{k=0}^{\infty} \frac{4V}{\pi} \frac{1}{2k+1} \sqrt{ \frac{2l+1}{4\pi} \frac{(l-m)!}{(l+m)!} } \int_{0}^{\pi} P^{m}_{l}(\cos \theta) \sin \theta d\theta \int_{0}^{2\pi} \sin n(2k+1)\phi e^{ im\phi } d\phi 
\end{align} $$
其中只有当 $m$ 为 $n$ 的奇数倍时 $\phi$ 的积分不为零, 换言之只用考虑 $m=n(2k+1)$ 和 $m=-n(2k+1)$ 项, 对于 $m=n(2k+1)$ 
$$A_{l,n(2k+1)} = \frac{1}{a^{l}} \dots\int_{0}^{2\pi} \sin n(2k+1)\phi e^{ in(2k+1)\phi } d\phi = \frac{-i\pi}{na^{l}} \dots  $$
对于 $m=-n(2k+1)$ 由于 $Y_{l,-m} = (-1)^{m}Y^{*}_{lm}$ 所以
$$A_{l,-n(2k+1)} = (-1)^{n(2k+1)} A^{*}_{l,-n(2k+1)} = \frac{(-1)^{n(2k+1)}\pi i}{na^{l}} \dots $$
其中
$$\dots = \frac{4V}{\pi} \frac{1}{2k+1} \sqrt{ \frac{2l+1}{4\pi} \frac{(l-m)!}{(l+m)!} } \int_{0}^{\pi} P^{m}_{l}(\cos \theta) \sin \theta d\theta  $$
于是电势的级数表达为
$$\Phi(r,\theta,\phi) = \sum_{l=0}^{\infty} \sum_{k=0}^{\infty}( A_{l,n(2k+1)} r^{l} Y_{l,n(2k+1)}(\theta,\phi) + cc. ) $$
这里 $cc.$ 表示前面的复共轭

## (b) 3.1 的验证

对于 $n=1$ 的情况, 计算 $l=0,1,2,3$ 的项:

$$A_{l,m} = -\frac{4V}{\pi} \frac{1}{m} \sqrt{ \frac{2l+1}{2} \frac{(l-m)!}{(l+m)!} } \frac{i\pi}{a^{l}} \int_{-1}^{1} P^{m}_{l}(x)dx $$
其中 $m$ 是奇数且 $|m|\le l$ . 此外若 $l+m$ 是奇数则积分值为零, 不用算. 


$l=0$ 时 无满足的指标条件的项所以 $A_{0,0}=0$ 
$l=1$ 时
$$ \int_{-1}^{1} P_{1}^{1}(x)dx = -\frac{\pi}{2} $$
$$A_{1,0}=0 , \quad A_{1,1} = \frac{i}{a} \frac{4V}{1} \frac{1}{3} \sqrt{ \frac{3}{4\pi} \frac{0!}{2!} } \frac{\pi}{2} = \frac{2iV}{a} \sqrt{ \frac{3\pi}{8} }  $$
$$A_{1,1}rY_{1,1} = r\frac{2iV}{a} \sqrt{ \frac{3\pi}{8} } \left(  -\sqrt{ \frac{3}{8\pi} } \sin \theta e^{ i\phi } \right) = -\frac{3iVr}{4a}\sin \theta e^{ i\phi } $$
$$A_{1,1}rY_{1,1} + cc. = \frac{3Vr}{2a}\sin \theta \sin \phi $$
$l=2$ 时
$$\int_{-1}^{1} P_{2}^{1}(x)dx = 0 $$
$$A_{2,0} = A_{2,1} = A_{2,2} = 0 $$
$$\sum_{m} A_{2,m} r^{2} Y_{2,m} +cc. = 0 $$
$l=3$ 时
$$\int_{-1}^{1} P_{3}^{1}(x)dx = -\frac{3\pi}{16} , \quad \int_{-1}^{1} P_{3}^{3}(x)dx = -\frac{45\pi}{8} $$
$$A_{3,0} = A_{3,2} = 0 ,\quad A_{3,1} = \frac{3iV}{4a^{3}} \sqrt{ \frac{7\pi}{48}} ,\quad A_{3,3} = \frac{15iV}{2a^{3}} \sqrt{ \frac{7\pi}{2880} } $$
$$A_{3,1} r^{3} Y_{3,1} + cc. = -\frac{3Vr^{3}}{2a^{3}} \sqrt{ \frac{7\pi}{48}} \frac{3}{2} \sqrt{ \frac{7}{192\pi} } \sin \theta(5\cos^2\theta-1)\sin \phi $$
$$A_{3,3} r^{3} Y_{3,3} = -\frac{15Vr^{3}}{a^{3}} \sqrt{ \frac{7\pi}{2880} } \left( -15 \sqrt{ \frac{7}{2880\pi} } \sin^3\theta \sin \phi \right) $$
$l=4$ 时
$$\int_{-1}^{1} P_{4}^{1}(x)dx = \int P_{4}^{3} dx = 0 $$
$$A_{4,0} = A_{4,1} = A_{4,2 } = A_{4,3} = A_{4,4} = 0 $$
$$\sum_{m} A_{4,m} r^{4} Y_{4,m} = 0 $$
于是电势的前 $l=4$ 项的展开式为:
$$\Phi = \frac{3Vr}{2a}\sin \theta \sin \phi + \frac{21Vr^{3}}{64a^{3}} \sin \theta(5\sin^2\theta-1)\sin \phi + \frac{35Vr^{3}}{64a^{3}}\sin^3\theta \sin \phi + \dots $$


# 习题 3.5

>[!question] 习题 3.5
>一个内半径为 $a$ 的空心球面，其表面电势指定为 $\Phi = V(\theta, \phi)$。证明球内电势的两种解形式的等价性：
>(a) 
$$\Phi(\mathbf{x}) = \frac{a(a^2 - r^2)}{4\pi} \int \frac{V(\theta', \phi')}{(r^2 + a^2 - 2ar \cos \gamma)^{3/2}}  d\Omega'$$
其中 $\cos \gamma = \cos \theta \cos \theta' + \sin \theta \sin \theta' \cos (\phi - \phi')$。
>(b)
$$\Phi(\mathbf{x}) = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} A_{lm} \left( \frac{r}{a} \right)^l Y_{lm}(\theta, \phi)$$
其中 $A_{lm} = \int d\Omega'  Y_{lm}^{*}(\theta', \phi') V(\theta', \phi')$。

## 证明

(a) 就是泊松积分公式:
$$\Phi(\mathbf{x}) = \frac{a^{2} - r^{2}}{4\pi a} \int \frac{V(\theta',\phi')}{|\mathbf{x}-\mathbf{x}'|^{3}} dS = \frac{a(a^{2} - r^{2})}{4\pi} \int \frac{V(\theta',\phi')}{|\mathbf{x}-\mathbf{x}'|^{3}} d\Omega' $$
下试导出 (b) 
记
$$K(\mathbf{x},\mathbf{x}') = \frac{a^{2}-r^{2}}{|\mathbf{x}-\mathbf{x}'|^{3}} $$
考虑
$$G(t,x) := \frac{1}{\sqrt{ t^{2} - 2tx + 1 }} = \sum_{l=0}^{\infty} P_{l}(x) t^{l} $$
$$\frac{\partial G}{\partial t} = \frac{x-t}{(t^{2} - 2tx + 1)^{3/2}} = \sum_{l=0}^{\infty} lP_{l}(x)t^{l-1} $$
$$\sum_{l=0}^{\infty} (2l+1) P_{l}(x) t^{l} = G + 2t \frac{\partial G}{\partial t} = \frac{1 - t^{2}}{(t^{2} - 2tx + 1)^{3/2}} = K(\mathbf{x},\mathbf{x}') $$
则
$$\Phi(\mathbf{x}) = \frac{1}{4\pi} \int_{S} V(\mathbf{x}') K(\mathbf{x},\mathbf{x}') d\Omega' = \frac{1}{4\pi} \int_{S} V(\mathbf{x}') \sum_{l=0}^{\infty} (2l+1)P_{l}(\cos \gamma)\left( \frac{r}{a} \right)^{l} d\Omega' $$
而
$$\int_{S} V(\theta',\phi') P_{l}(\cos \gamma) \frac{d\Omega'}{4\pi} = \sum_{m=-l}^{l} \int_{S} V(\theta',\phi') \frac{4\pi}{2l+1} Y^{*}_{lm}(\theta',\phi') Y_{lm}(\theta,\phi)  \frac{d\Omega'}{4\pi} = \sum_{m=-l}^{l} A_{lm} Y_{lm}(\theta,\phi) $$
于是
$$\Phi(\mathbf{x}) = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} A_{lm} \left( \frac{r}{a} \right)^l Y_{lm}(\theta, \phi)$$
证毕


# 习题 3.6

>[!question] 习题 3.6
>两个点电荷 $q$ 和 $-q$ 分别位于 $z$ 轴上的 $z = +a$ 和 $z = -a$ 处。
>(a) 将静电势展开为球谐函数和 $r$ 的幂级数，分别求出 $r > a$ 和 $r < a$ 时的表达式。
>
>(b) 保持乘积 $qa = p/2$ 不变，取 $a \to 0$ 的极限，求 $r \neq 0$ 时的电势。根据定义，这就是沿 $z$ 轴的偶极子及其电势。
>
>(c) 假设现在 (b) 部分的偶极子被一个半径为 $b$、与原点同心的接地球壳包围。通过线性叠加求出球壳内各处的电势。

## (a) 电势

$$\Phi = \frac{q}{4\pi\varepsilon_{0}} \left(  \frac{1}{|\mathbf{r} - a\hat{\mathbf{z}}|} - \frac{1}{|\mathbf{r} + a\hat{\mathbf{z}}|} \right) $$
其中当 $r>a$ 时
$$\frac{1}{|\mathbf{r}-a\hat{\mathbf{z}}|} = \sum_{l=0}^{\infty} \frac{a^{l}}{r^{l+1}} P_{l}(\cos \theta) , \quad \frac{1}{|\mathbf{r} + a \hat{\mathbf{z}}|} = \sum_{l=0}^{\infty} \frac{a^{l}}{r^{l+1}} (-1)^{l} P_{l}(\cos \theta) $$
于是
$$\Phi = \frac{q}{4\pi\varepsilon_{0}} \sum_{l=0}^{\infty} \frac{r^{l}}{a^{l+1}} (1-(-1)^{l}) P_{l}(\cos \theta) = \frac{q}{4\pi\varepsilon_{0}r} \sum_{l=0}^{\infty} 2 \left( \frac{a}{r} \right)^{2l+1} P_{2l+1}(\cos \theta)  $$
当 $r<a$ 时同理
$$\Phi  = \frac{q}{4\pi\varepsilon_{0}a} \sum_{l=0}^{\infty} 2 \left( \frac{r}{a} \right)^{2l+1} P_{2l+1}(\cos \theta)  $$

## (b) 偶极子极限

保持 $qa=\frac{p}{2}$ 不变当 $a\to 0$ 时 $r>a$ 
$$\Phi = \frac{1}{4\pi\varepsilon_{0}r^{2}} \sum_{l=0}^{\infty} 2qa \left( \frac{a}{r} \right)^{l} P_{l}(\cos \theta) \to \frac{1}{4\pi\varepsilon_{0}} \frac{p\cos \theta}{r^{2}} $$

## (c) 再套一个接地导体球壳

电偶极子
$$\Phi_{0} = \frac{1}{4\pi\varepsilon_{0}} \frac{p\cos \theta}{r^{2}} $$
球壳
$$\Phi_{1} = \sum_{l=0}^{\infty} A_{l} r^{l} P_{l}(\cos \theta) $$
于是 $\Phi=\Phi_{0}+\Phi_{1}$ 边界条件为 $\Phi(b,\theta,\phi)=0$ 所以
$$\sum_{l=0}^{\infty} A_{l} b^{l} P_{l}(\cos \theta) = -\frac{1}{4\pi\varepsilon_{0}} \frac{p\cos \theta}{b^{2}} $$
解得
$$\Phi_{1}=-\frac{1}{4\pi\varepsilon_{0}} \frac{pr\cos \theta}{b^{3}} $$
$$\Phi = \frac{1}{4\pi\varepsilon_{0}}p\cos \theta \left(  \frac{1}{r^{2}} - \frac{r}{b^{3}}  \right) $$


# 习题 3.7

>[!question] 习题 3.7
>三个点电荷 $(q, -2q, q)$ 位于一条直线上，间距为 $a$，中间电荷 $(-2q)$ 位于半径为 $b$ 的接地导电球壳的原点，如图所示。
>
>(a) 写出在没有接地球壳时三个电荷的电势。求当 $a \to 0$，但乘积 $qa^2 = Q$ 保持有限时的电势极限形式。用球坐标写出这个答案。
>
>(b) 半径为 $b$ 的接地球壳的存在改变了 $r < b$ 区域的电势。附加的电势可以看作是由 $r = b$ 处内表面上的感应面电荷密度引起的，或者是由位于 $r > b$ 处的镜像电荷引起的。使用线性叠加来满足边界条件，并求出球内 $r < a$ 和 $r > a$ 处的电势。证明在 $a \to 0$ 的极限下，
>
>$$\Phi(r, \theta, \phi) \to \frac{Q}{2\pi\epsilon_0 r^3} \left(1 - \frac{r^5}{b^5}\right) P_2(\cos\theta)$$

## 解答

### (a) 无接地球壳时的电势及其极限

无球壳时的静电势为:
$$
\Phi(\mathbf{r}) = \frac{1}{4\pi\epsilon_0} \left( \frac{q}{|\mathbf{r} - a\mathbf{e}_z|} + \frac{q}{|\mathbf{r} + a\mathbf{e}_z|} - \frac{2q}{|\mathbf{r}|} \right)
$$
$$
\frac{1}{|\mathbf{r} - \mathbf{r}'|} = \sum_{l=0}^{\infty} \frac{r_<^l}{r_>^{l+1}} P_l(\cos\gamma)
$$
 对于 $r > a$: 
$$
  \frac{1}{|\mathbf{r} - a\mathbf{e}_z|} = \sum_{l=0}^{\infty} \frac{a^l}{r^{l+1}} P_l(\cos\theta), \quad
  \frac{1}{|\mathbf{r} + a\mathbf{e}_z|} = \sum_{l=0}^{\infty} \frac{a^l}{r^{l+1}} (-1)^l P_l(\cos\theta)
  $$
所以
$$
  \Phi(r) = \frac{q}{4\pi\epsilon_0} \sum_{l=0}^{\infty} \frac{a^l}{r^{l+1}} \left[1 + (-1)^l\right] P_l(\cos\theta) - \frac{2q}{4\pi\epsilon_0 r} = \frac{q}{4\pi\epsilon_0} \sum_{m=1}^{\infty} \frac{2a^{2m}}{r^{2m+1}} P_{2m}(\cos\theta)
  $$
保持 $qa^{2}=Q$ 不变取 $a\to 0$ 时 $r>a$  
$$
  \Phi(r) = \frac{Q}{2\pi\epsilon_0 r^3} P_2(\cos\theta) = \frac{Q}{4\pi\epsilon_0 r^3} (3\cos^2\theta - 1)
  $$


### (b) 有接地球壳时的电势及极限

无球壳时的电势近似为: 
$$
\Phi_0(r) = \frac{Q}{4\pi\epsilon_0 r^3} (3\cos^2\theta - 1)
$$
设总电势为 $\Phi(r) = \Phi_0(r) + \Phi_1(r)$, 其中 $\Phi_1(r)$ 在 $r < b$ 内调和, 且满足边界条件 $\Phi_1(b, \theta) = -\Phi_0(b, \theta)$ 
$$\Phi_{1} = \sum_{l=0}^{\infty} A_{l} \frac{r^{l}}{b^{l+1}} P_{l}(\cos \gamma)  $$$$\sum_{l=0}^{\infty} \frac{A_{l}}{b} P_{l}(\cos \theta) = \frac{Q}{4\pi\epsilon_0 b^3} (3\cos^2\theta - 1)
$$ 故
$$
\Phi_1(r) = -\frac{Q}{2\pi\epsilon_0 b^5} r^2 P_2(\cos\theta),
$$
总电势为: 
$$
\Phi(r) = \frac{Q}{2\pi\epsilon_0 r^3} P_2(\cos\theta) - \frac{Q}{2\pi\epsilon_0 b^5} r^2 P_2(\cos\theta) = \frac{Q}{2\pi\epsilon_0 r^3} \left(1 - \frac{r^5}{b^5}\right) P_2(\cos\theta).
$$
此即所求极限形式. 



# 习题 3.8

>[!question] 习题 3.8
>对于沿直径放置均匀带电导线的接地球壳内部的电势解 (3.136)，存在一个令人困惑的方面。非常靠近导线处（即对于 $\rho = r \sin \theta \ll b$），电势应该是均匀带电导线的电势，即
>
>$$\Phi = (Q/4\pi\epsilon_0b)\ln(b/\rho) + \Phi_0$$
>
>但解 (3.136) 并未明确表现出这种行为。
>
>(a) 利用勒让德微分方程 (3.10) 和一些分部积分，证明 $\ln(\cos\alpha \theta)$ 具有适当的球谐函数展开，从而允许将解 (3.136) 改写为以下形式：
>
>$$\Phi(x) = \frac{Q}{4\pi\epsilon_0b} \left\{ \ln\left( \frac{2b}{r \sin \theta} \right) - 1 - \sum_{j=1}^{\infty} \frac{4j+1}{2j(2j+1)} \left( \frac{r}{b} \right)^{2j} P_{2j}(\cos \theta) \right\}$$
>
>在这种形式中，导线附近预期的行为变得明显。请解释常数项 $\Phi_0 = -Q/4\pi\epsilon_0b$ 的含义。注意，在这种形式中，对于任何 $r/b < 1$，勒让德多项式级数在所有角度都快速收敛。
>
>(b) 利用展开式 (3.38) 证明
>
>$$\frac{1}{2} \left( \frac{1}{\sin\theta/2} + \frac{1}{\cos\theta/2} \right) = 2 \sum_{j=0}^{\infty} P_{2j}(\cos\theta)$$
>
>并因此球壳内表面的电荷密度（方程 (3.137)）可以表示为
>
>$$\sigma(\theta) = -\frac{Q}{4\pi b^2} \left\{ \frac{1}{2} \left( \frac{1}{\sin\theta/2} + \frac{1}{\cos\theta/2} \right) - \sum_{j=0}^{\infty} \frac{1}{2j+1} P_{2j}(\cos\theta) \right\}$$
>
>现在，在 $\theta = 0$ 和 $\theta = \pi$ 处的（可积）奇异行为被明确展示出来。该级数在 $\theta \to 0$ 时提供了 $\ln(1/\theta)$ 的修正。

## 解答

### (a) 电势的改写形式

(3.136) 说的是: 
$$\Phi = \frac{Q}{4\pi\varepsilon_{0}b} \left[  \ln \frac{b}{r} + \sum_{j=1}^{\infty} \frac{4j+1}{2j(2j+1)} \left(  1- \left( \frac{r}{b} \right)^{2j}  \right) P_{2j}(\cos \theta) \right] $$
考虑将 $\ln \sin \theta$ 用球谐函数展开, 由于和 $\phi$ 无关, 所以其实是按勒让德多项式展开. 考虑 $f(x)=\ln \sin \theta$ , 其中 $x=\cos \theta$ 则
$$f(x) = \ln \sqrt{ 1-x^{2} } = \frac{1}{2} \ln(1-x^{2}) $$
显然 $f(x)$ 是偶函数, 只有偶数项:
$$f(x) = \sum_{j=0}^{\infty} A_{2j} P_{2j}(x) $$
其中 $P_{0}=1$ 各项系数为:
$$a_{0}=\frac{1}{2} \int_{-1}^{1} \frac{1}{2} \ln(1-x^{2}) dx = \ln{2} -1 $$
$$a_{l} = \frac{2l+1}{2} \int_{-1}^{1} \frac{1}{2}\ln(1-x^{2}) P_{l}(x)dx $$
故需计算积分
$$I_{2j} = \int_{-1}^{1} \ln(1-x^{2}) P_{2j}(x) dx $$
考虑到勒让德多项式满足方程
$$\frac{d}{dx} \left[  (1-x^{2}) \frac{dP_{l}}{dx}  \right] + l(l+1) P_{l} = 0 $$
故
$$\begin{align}
I_{2j} &= -\frac{1}{2j(2j+1)} \int_{-1}^{1} \ln(1-x^{2}) \frac{d}{dx}\left[  (1-x^{2}) \frac{dP_{2j}}{dx}  \right] dx \\
&= -\frac{1}{2j(2j+1)} \int_{-1}^{1} \ln(1-x^{2}) d\left[  (1-x^{2}) \frac{dP_{2j}}{dx}  \right] \\
&= -\frac{1}{2j(2j+1)} \left. \ln(1-x^{2}) (1-x^{2}) \frac{dP_{2j}}{dx}  \right|^{1}_{-1} + \frac{1}{2j(2j+1)} \int_{-1}^{1} (1-x^{2}) \frac{dP_{2j}}{dx} \frac{2x}{1-x^{2}} dx \\
&= \frac{1}{2j(2j+1)} \int_{-1}^{1} 2x dP_{2j} \\
&= \frac{1}{2j(2j+1)} \left. 2xP_{2j}(x) \right|^{1}_{-1} - \frac{1}{2j(2j+1)} \int_{-1}^{1} 2P_{2j}(x)dx \\
&= - \frac{2}{2j(2j+1)}
\end{align} $$
因此
$$f(x) = \ln{2} - 1 - \sum_{j=1}^{\infty} \frac{2}{2j(2j+1)} P_{2j}(x) $$
$$\ln \sin \theta = \ln{2} - 1 - \sum_{j=1}^{\infty} \frac{4j+1}{2j(2j+1)} P_{2j}(\cos \theta) $$
代回 (3.136) 得:
$$\begin{align}
\Phi &= \frac{Q}{4\pi\varepsilon_{0}b} \left[  \ln \frac{b}{r} + \sum_{j=1}^{\infty} \frac{4j+1}{2j(2j+1)} P_{2j}(\cos \theta) - \sum_{j=1}^{\infty} \frac{4j+1}{2j(2j+1)} \left( \frac{r}{b} \right)^{2j} P_{2j}(\cos \theta) \right] \\
&= \frac{Q}{4\pi\varepsilon_{0}b} \left[  \ln \frac{b}{r} + \ln 2 - 1 - \ln \sin \theta - \sum_{j=1}^{\infty} \frac{4j+1}{2j(2j+1)} \left( \frac{r}{b} \right)^{2j} P_{2j}(\cos \theta) \right]  \\
&= \frac{Q}{4\pi\varepsilon_{0}b} \left[  \ln \frac{2b}{r\sin \theta} - 1 - \sum_{j=1}^{\infty} \frac{4j+1}{2j(2j+1)} \left( \frac{r}{b} \right)^{2j} P_{2j}(\cos \theta)  \right]
\end{align} $$
在导线中心附近级数项趋于零于是
$$\Phi \approx \frac{Q}{4\pi\varepsilon_{0}b} \ln \frac{2b}{\rho} - \frac{Q}{4\pi \varepsilon_{0}b} $$
其中常数项是由于球壳接地导致(接电压等效于铺层均匀电荷)


### (b) 电荷密度的表达式

利用勒让德多项式的生成函数:
$$
\frac{1}{\sqrt{1-2t\cos\theta+t^2}} = \sum_{l=0}^{\infty} t^l P_l(\cos\theta)
$$
令 $t = 1$ 和 $t = -1$ :
$$
\frac{1}{2\sin(\theta/2)} = \sum_{l=0}^{\infty} P_l(\cos\theta), \quad \frac{1}{2\cos(\theta/2)} = \sum_{l=0}^{\infty} (-1)^l P_l(\cos\theta)
$$
$$
\frac{1}{2} \left( \frac{1}{\sin\theta/2} + \frac{1}{\cos\theta/2} \right) = \sum_{l=0}^{\infty} [1 + (-1)^l] P_l(\cos\theta) = 2 \sum_{j=0}^{\infty} P_{2j}(\cos\theta)
$$
球壳内表面的电荷密度为: 
$$
\sigma(\theta) = -\epsilon_0 \frac{\partial \Phi}{\partial r} \bigg|_{r=b}
$$
代入改写后的电势表达式, 经计算得: 
$$
\sigma(\theta) = -\frac{Q}{4\pi b^2} \left\{ \frac{1}{2} \left( \frac{1}{\sin\theta/2} + \frac{1}{\cos\theta/2} \right) - \sum_{j=0}^{\infty} \frac{1}{2j+1} P_{2j}(\cos\theta) \right\}
$$



# 习题 3.9

>[!question] 习题 3.9
>一个半径为 $b$ 的空心直圆柱体，其轴线与 $z$ 轴重合，两端位于 $z = 0$ 和 $z = L$。端面的电势为零，而圆柱面上的电势由 $V(\phi, z)$ 给出。使用柱坐标中的适当分离变量法，求出柱体内任意位置电势的级数解。

## 解答

在柱坐标系 $(eho, \phi, z)$ 中,拉普拉斯方程为: 
$$
\nabla^2 \Phi = \frac{1}{\rho} \frac{\partial}{\partial \rho} \left( \rho \frac{\partial \Phi}{\partial \rho} \right) + \frac{1}{\rho^2} \frac{\partial^2 \Phi}{\partial \phi^2} + \frac{\partial^2 \Phi}{\partial z^2} = 0
$$
边界条件为: 在 $z = 0$ 和 $z = L$ 处, $\Phi = 0$; 在 $\rho = b$ 处, $\Phi = V(\phi, z)$ 

设
$$
\Phi(\rho, \phi, z) = R(\rho) \Psi(\phi) Z(z)
$$
 **$Z(z)$ 方程**：
$$
Z'' + k^2 Z = 0
$$
结合边界条件 $Z(0) = Z(L) = 0$, 解得
$$
k_n = \frac{n\pi}{L}, \quad Z_n(z) = \sin\left( \frac{n\pi z}{L} \right), \quad n = 1, 2, 3, \dots
$$
 **$\Psi(\phi)$ 方程**：
$$
\Psi'' + m^2 \Psi = 0
$$

由于 $\phi$ 的周期性, $m$ 为整数, 解为
$$
\Psi_m(\phi) = e^{im\phi}
$$

 **$R(r)$ 方程**：
$$
\rho^{2} R'' + \rho R' - (m^{2} + \mu^{2}\rho^{2})R=0 
$$
其中 $\mu=\frac{n\pi}{L}$ 令 $x=\mu r$ , $R(r)=y(x)$ 则
$$\frac{d^{2}y}{dx^{2}} + \frac{1}{x} \frac{dy}{dx} + \left(  1 - \frac{m^{2}}{x^{2}}  \right)y = 0 $$
这是贝塞尔方程, 其解为贝塞尔函数 $J_m(x)$(已排除 $Y_{m}$ 的发散解). 故
$$R(r) = A_{mn} J_{m}(\mu r) $$
$$\Phi(r,\phi,z) = \sum_{n=1}^{\infty} \sum_{m=-\infty}^{\infty} A_{mn} J_{m}\left(  \frac{n\pi r}{L}  \right) e^{ im\phi } \sin \left(  \frac{n\pi z}{L}  \right) $$
利用边界条件在 $r = b$ 处: 
$$
V(\phi, z) = \sum_{n=1}^{\infty} \sum_{m=-\infty}^{\infty} A_{mn} J_m\left( \frac{n\pi b}{L} \right) e^{im\phi} \sin\left( \frac{n\pi z}{L} \right)
$$
$$
A_{mn} = \frac{1}{\pi L J_m\left( \frac{n\pi b}{L} \right)} \int_0^{2\pi} \int_0^L V(\phi, z) e^{-im\phi} \sin\left( \frac{n\pi z}{L} \right)  dz d\phi
$$


# 习题 3.10

>[!question] 习题 3.10
>对于问题 3.9 中的圆柱体，圆柱面由两个相等的半圆柱体组成，一个电势为 $V$，另一个为 $-V$，因此
>
>$$V(\phi, z) = 
\begin{cases} 
V & \text{for } -\pi/2 < \phi < \pi/2 \\ 
-V & \text{for } \pi/2 < \phi < 3\pi/2 
\end{cases}$$
>
>(a) 求圆柱体内的电势。
>
>(b) 假设 $L \gg b$，考虑 $z = L/2$ 处的电势作为 $\rho$ 和 $\phi$ 的函数，并将其与二维问题 2.13 进行比较。

## 解答

### (a) 圆柱体内的电势

通过柱坐标下的分离变量法(类似3.9)可知:
$$\Phi = R(\rho) \Psi(\phi) Z(z) $$
其中
$$\Psi(\phi) = \frac{4V}{\pi} \sum_{k=1}^{\infty} \frac{(-1)^{k+1}}{2k-1} \cos(2k-1)\phi $$
$$Z(z) = \sum_{n=1}^{\infty} A_{n} \sin \frac{n\pi z}{L}  $$
记 $\mu=\frac{n\pi}{L}$ 则径向的方程为:
$$\rho^{2} R'' + \rho R' - (m^{2} + \mu^{2}\rho^{2})R=0 $$
令 $x=\mu \rho$ 则
$$R(x) = AI_{m}(x) + BK_{m}(x) $$
当 $x\to 0$ 时 $K_{m}(x)\to \infty$ 故排除得到
$$R(\rho) = AI_{m}\left( \frac{n\pi \rho}{L} \right) $$
故解为
$$\Phi = \sum_{n,m=1}^{\infty} C_{nm} I_{2m-1}\left(  \frac{n\pi \rho}{L} \right) \cos(2m-1)\phi \sin \frac{n\pi z}{L}   $$
下求系数

$$\Phi(b,\theta,\phi) = V(\phi,z) $$
$$\int_{0}^{L} V(\phi) \sin \frac{n\pi z}{L} dz = \sum_{n=1}^{\infty} C_{nm} I_{2m-1}\left( \frac{n\pi b}{L} \right) \cos(2m-1)\phi \cdot \frac{2}{L} $$
当 $n$ 为偶数时左边为零 $C_{nm}=0$ 当 $n$ 为奇数时设为 $n=2k-1$ 左边为 $\frac{4V(\phi)}{(2k-1)\pi}$ 而 $V(\phi)$ 的傅里叶展开为:
$$V(\phi) = \frac{4V}{\pi} \sum_{k=1}^{\infty} \frac{(-1)^{k+1}}{2k-1} \cos(2k-1)\phi $$
故
$$C_{kp} = \frac{4V(-1)^{k+1}}{2(2k-1)I_{2k-1}\left( \frac{(2p-1)\pi b}{L} \right)} $$

$$\Phi(\rho,\phi,z) = \frac{4V}{\pi} \sum_{k,p=1}^{\infty} \frac{(-1)^{k+1}}{2k+1} \frac{I_{2k-1}\left( \frac{(2p-1)\pi \rho}{L} \right)}{I_{2k-1}\left( \frac{(2p-1)\pi b}{L} \right)} \cos(2k-1)\phi \sin \frac{(2p-1)\pi z}{L} $$


### (b)  $L \gg b$ 时 $z = L/2$ 处的电势

当 $L \gg b$ 时
$$I_{m}(x) \sim \left( \frac{x}{2} \right)^{m} \frac{1}{m!} $$
$$\frac{I_{2k-1}\left( \frac{(2p-1)\pi \rho}{L} \right)}{I_{2k-1}\left( \frac{(2p-1)\pi b}{L} \right)} \sim \left( \frac{\rho}{b} \right)^{2k-1} $$
在 $z=\frac{L}{2}$ 处
$$\sin \frac{(2p-1)\pi z}{L} = (-1)^{p+1} $$
$$\Phi(\rho, \phi, L/2) \approx \frac{4V}{\pi} \sum_{k=0}^{\infty} \frac{(-1)^k}{2k+1} \left(\frac{\rho}{b}\right)^{2k+1} \cos(2k+1)\phi$$

此表达式与二维问题 2.13 中均匀带电圆柱体的电势解一致, 验证了在远离端面时三维解退化为二维情况.


# 习题 3.11 贝塞尔函数集正交归一完备性

>[!question] 习题 3.11
>在区间 $0 \leq \rho \leq a$ 上，任意函数 $f(\rho)$ 的修正贝塞尔-傅里叶级数可以基于以下"齐次"边界条件建立：
>
>在 $\rho = 0$ 处：$\rho J_\nu(k \rho) \frac{dJ_\nu(k' \rho)}{d\rho} = 0$
>
>在 $\rho = a$ 处：$\frac{d}{d\rho} \ln [J_\nu(k \rho)] = -\frac{\lambda}{a}$（$\lambda$ 为实数）
>
>第一个条件限制了 $\nu$。第二个条件给出本征值 $k = y_{\nu n}/a$，其中 $y_{\nu n}$ 是方程 $x \frac{dJ_\nu(x)}{dx} + \lambda J_\nu(x) = 0$ 的第 $n$ 个正根。
>
>(a) 证明不同本征值的贝塞尔函数按通常方式正交。
>
>(b) 求归一化积分，并证明任意函数 $f(\rho)$ 可以在该区间上展开为修正贝塞尔-傅里叶级数
>
>$$f(\rho) = \sum_{n=1}^\infty A_n J_\nu \left( \frac{y_{\nu n} \rho}{a} \right)$$
>
>其中系数 $A_n$ 由下式给出：
>
>$$A_n = \frac{2}{a^2} \left[ \left( 1 - \frac{\nu^2}{y_{\nu n}^2} \right) J_\nu^2 (y_{\nu n}) + \left( \frac{dJ_\nu(y_{\nu n})}{dy_{\nu n}} \right)^2 \right]^{-1} \int_0^a f(\rho)  \rho  J_\nu \left( \frac{y_{\nu n} \rho}{a} \right)  d\rho$$
>
>在这种形式中，对 $\lambda$ 的依赖是隐含的，但方括号有替代形式：
>
>$$\left[ \left( 1 - \frac{\nu^2}{y_m^2} \right) J_{\nu}^2 (y_m) + \left( \frac{dJ_{\nu} (y_m)}{dy_m} \right)^2 \right] = \left( 1 + \frac{\lambda^2 - \nu^2}{y_m^2} \right) J_{\nu}^2 (y_m)$$
>
>$$= \left( 1 + \frac{y_m^2 - \nu^2}{\lambda^2} \right) \left[ \frac{dJ_{\nu} (y_m)}{dy_m} \right]^2$$
>
>$$= [J_{\nu}^2 (y_m) - J_{\nu-1} (y_m) J_{\nu+1} (y_m)]$$
>
>当 $\lambda \to \infty$ 时，我们恢复 (3.96) 和 (3.97) 的结果。选择 $\lambda = 0$ 是另一个简单的替代方案。

## (a) 不同本征值贝塞尔函数的正交性证明

考虑参数形式的贝塞尔方程
$$\frac{d}{d\rho}\left( k\rho  \frac{dy}{d\rho} \right) + \left( k^{2}\rho - \frac{\nu^{2}}{\rho} \right) y = 0 $$
其解为(已排除奇点解)
$$y=A_{m}J_{\nu}\left(\lambda \rho\right) $$
现在使用边界条件把特征值求出来
$$k\rho J_{\nu}(k\rho)J_{\nu}'(k'\rho)=0,\quad \text{at } \rho=0$$
$$\rho J_{\nu}'(k\rho) + \lambda J_{\nu}(k\rho)=0,\quad \text{at } \rho=a $$
第一个条件限制了 $\nu$ 一定是可以使得 $xJ_{\nu}J_{\nu}'\to 0$ 的.
第二个条件限制了 $k$ 可以使得 $aJ_{\nu}'(ka) + \lambda J_{\nu}(ka)=0$ 做换元 $ka=x$ 则  $xJ'_{\nu}(x) + \lambda J_{\nu}(x)=0$ 此方程有无穷多个根, 于是得到了无穷个本征值 $k_{1},k_{2},k_{3},\dots$ 

下面证明 $J_{\nu}(k_{m}x)$ 构成一个正交函数集, 实际上我们仿照施图姆刘维尔的理论, 将其满足的微分方程写为施图姆刘维尔形式
$$\frac{d}{d\rho}\left( \rho  \frac{dJ_{\nu}(k_{m}x)}{d\rho} \right) + \left( k_{m}^{2}\rho - \frac{\nu^{2}}{\rho} \right)J_{\nu}(k_{m}x) = 0 $$
则(以下简记 $J_{\nu}(k_{n}\rho)=J_{n},J_{\nu}(k_{m}\rho)=J_{m}$ ) 
$$J_{m} \frac{d}{d\rho} \left(  \rho \frac{dJ_{n}}{d\rho} \right) - J_{n} \frac{d}{d\rho} \left(  \rho \frac{dJ_{m}}{d\rho} \right) + (k_{n}^{2} - k_{m}^{2}) \rho J_{n}J_{m} = 0 $$
$$\frac{d}{d\rho}\left[ \rho\left( J_{m}\frac{dJ_{n}}{d\rho} - J_{n}  \frac{dJ_{m}}{d\rho} \right) \right] + ( k_{n}^{2} - k_{m}^{2})\rho J_{n}J_{m} = 0 $$
$$\left. \left[ \rho\left( J_{m}\frac{dJ_{n}}{d\rho} - J_{n}  \frac{dJ_{m}}{d\rho} \right) \right] \right|_{0}^{a} + (k_{n}^{2} - k_{m}^{2})\int_{0}^{a}\rho J_{n}J_{m}d\rho = 0 $$
由第一个边界条件 $\rho=0$ 时的边界项为零, 由第二个边界条件 $\rho=a$ 时
$$J_{m} \frac{dJ_{n}}{d\rho} - J_{n} \frac{dJ_{m}}{d\rho} = J_{n}J_{m}\left( \frac{d}{d\rho}\ln J_{n} - \frac{d}{d\rho}\ln J_{m} \right) = 0 $$
所以也是零于是我们得到
$$(k_{n}^{2} - k_{m}^{2}) \int_{0}^{a}\rho J_{n}J_{m}d\rho = 0 $$
当本征值不同时 $k_{n}\neq k_{m}$ 必有
$$\int_{0}^{a}\rho J_{n}J_{m}d\rho = 0$$
证毕


## (b) 归一化系数和贝塞尔函数展开

归一化系数
$$N_{n} := \int_{0}^{a} \rho [J_{\nu}(k_{n}\rho)]^{2} d\rho $$
依旧参数形式的贝塞尔函数 $J_{\nu}(k\rho)$ 注意这里的 $k$ 不是满足边界条件的特征值. 那么很合理的
$$N_{n} = \lim_{ k \to k_{n} } \int_{0}^{a} \rho J_{\nu}(k_{n}\rho) J_{\nu}(k\rho) d\rho = \lim_{ k \to k_{n} } \frac {\left.\left[ \rho\left( J_{\nu}(k\rho)\frac{dJ_{\nu}(k_{n}\rho)}{d\rho} - J_{\nu}(k_{n}\rho)\frac{dJ_{\nu}(k\rho)}{d\rho} \right) \right] \right|_{0}^{a}}{-k^{2}+k_{n}^{2}} $$
对于分子, 在 $\rho=0$ 时由于自然边界条件(条件1)为零, 下讨论 $\rho=a$ 时的情况混合边界条件(条件2)告诉我们 $\frac{J_{\nu}'(k_{n}a)}{J_{\nu}(k_{n}a)} = -\frac{\lambda}{k_{n}a}$ 这里 $k_{n}$ 应当是某个本征值的, 所以不能写下 $kaJ_{\nu}'(ka)+\lambda J_{\nu}(ka)=0$ 这样的东西. 一个较为合理的做法是直接洛必达
$$E(k) := a[ J_{\nu}(ka) k_{n} J_{\nu}'(k_{n}a) - J_{\nu}(k_{n}a) k J_{\nu}'(ka) ] $$
$$N_{n} = \lim_{ k \to k_{n} } \frac{E'(k)}{-2k}   $$
而
$$\begin{align}
E'(k) &= a( aJ_{\nu}'(ka)J_{\nu}'(k_{n}a) - aJ_{\nu}(k_{n}a)J_{\nu}'(ka) - akJ_{\nu}(k_{n}a)J_{\nu}''(ka) )   \\
&\to a^{2} ( [J_{\nu}'(k_{n}a)]^{2} - J_{\nu}(k_{n}a)J_{\nu}'(k_{n}a) - k_{n}J_{\nu}(k_{n}a)J_{\nu}''(k_{n}a) )
\end{align}$$
其中
$$J_{\nu}''(k_{n}a) = -\frac{1}{k_{n}a}J_{\nu}'(k_{n}a) - \left(  1- \frac{\nu^{2}}{(k_{n}a)^{2}}  \right)J_{\nu}(k_{n}a) $$
于是
$$E'(k_{n}) = a^{2}k_{n}\left(  [J_{\nu}'(k_{n}a)]^{2} + \left(  1-\frac{\nu^{2}}{(k_{n}a)^{2}}  \right)[J_{\nu}(k_{n}a)]^{2}  \right) = \frac{a^{2}k_{n}}{2} [J_{\nu}(k_{n}a)]^{2}\left(  1 + \frac{\lambda^{2} - \nu^{2}}{(k_{n}a)^{2}}  \right) $$
所以
$$N_{n} = \frac{a^{2}}{2} [J_{\nu}(k_{n}a)]^{2}\left(  1 + \frac{\lambda^{2} - \nu^{2}}{(k_{n}a)^{2}}  \right) $$

对于任何一个定义在 $[0,a]$ 上的函数 $f(\rho)$ 均能按函数集 $J_{\nu}(k_{n}\rho)$ 来展开:
$$f(\rho) = \sum_{n=1}^{\infty} A_{n} J_{\nu} \left( \frac{y_{\nu n}\rho}{a} \right) $$
$$A_{n} N_{n} = \int_{0}^{a} \rho f(\rho) J_{\nu}(y_{\nu n}\rho/a) d\rho $$
$$A_{n} = \frac{2}{a^2} \left[ \left( 1 - \frac{\nu^2}{y_{\nu n}^2} \right) J_\nu^2 (y_{\nu n}) + \left( \frac{dJ_\nu(y_{\nu n})}{dy_{\nu n}} \right)^2 \right]^{-1} \int_0^a f(\rho)  \rho  J_\nu \left( \frac{y_{\nu n} \rho}{a} \right)  d\rho $$

## 日后谈——关于边界条件

我们这里使用的边界条件有两个,
- 一个是自然边界条件, 在 $\rho = 0$ 处：$\rho J_\nu(k \rho) \frac{dJ_\nu(k' \rho)}{d\rho} = 0$ 
- 一个是混合边界条件, 在 $\rho = a$ 处：$\frac{d}{d\rho} \ln [J_\nu(k \rho)] = -\frac{\lambda}{a}$ 
第二个为什么是混合边界条件呢? 实际上
$$\frac{J_{\nu}'(k\rho)}{J_{\nu}(k\rho)} = -\frac{\lambda}{a} , \quad aJ_{\nu}'(k\rho) + \lambda J_{\nu}(k\rho) = 0 $$
这正是混合边界条件, 通过调节 $\lambda$ 我们能快速的回归到迪利克雷边界条件和纽曼边界条件

### 第一类边界条件
做换元 $x=ka$ 则
$$xJ'_{\nu}(x) + \lambda J_{\nu}(x)=0 $$
取 $\lambda\to \infty$ 即可得到边界条件为
$$J_{\nu}(x) = 0 $$
此时 $k$ 就是 $J_{\nu}(x)$ 的零点 $\mu_{\nu n}$ 们除以 $a$ 这与顾桥的讨论一致

### 第二类边界条件
做换元 $x=ka$ 则 
$$xJ'_{\nu}(x) + \lambda J_{\nu}(x)=0  $$
取 $\lambda\to 0$ 得到
$$xJ_{\nu}'(x) = 0 $$
此时的本征值 $k$ 就是取 $0$ 和 $J_{\nu}'(x)$ 的零点 $\zeta_{\nu n}$ 们除以 $a$ 



# 习题 3.12

>[!question] 习题 3.12
>一个无限薄的导电平面板上有一个半径为 $a$ 的圆孔。一个由相同材料制成、半径稍小的薄圆盘位于该平面，填充了圆孔，但通过一个非常窄的绝缘环与平板分离。圆盘保持固定电势 $V$，而无限大平板保持零电势。
>
>(a) 使用适当的柱坐标，找到一个涉及贝塞尔函数的积分表达式，表示平面上方任意点的电势。
>
>(b) 证明在圆盘中心正上方垂直距离 $z$ 处的电势为
>
>$$\Phi_0(z) = V \left( 1 - \frac{z}{\sqrt{a^2 + z^2}} \right)$$
>
>(c) 证明在圆盘边缘正上方垂直距离 $z$ 处的电势为
>
>$$\Phi_a(z) = \frac{V}{2} \left[ 1 - \frac{kz}{\pi a} K(k) \right]$$
>
>其中 $k = 2a/(z^2 + 4a^2)^{1/2}$，$K(k)$ 是第一类完全椭圆积分。

## (a) 任一点电势

边界条件为:

- 在 $z=0$ 上：
  - $\Phi = V$ 对于 $\rho < a$（圆盘）
  - $\Phi = 0$ 对于 $\rho > a$（平面）
- 在 $z \to \infty$ 时, $\Phi \to 0$.

在 $z > 0$ 的区域中, 拉普拉斯方程的解可表示为汉克尔变换:
$$
\Phi(\rho, z) = \int_0^\infty A(k) J_0(k\rho) e^{-kz}  dk
$$
在 $z=0$ 处, 有:
$$
\Phi(\rho, 0) = \int_0^\infty A(k) J_0(k\rho)  dk = 
\begin{cases}
V & \text{if } \rho < a \\
0 & \text{if } \rho > a
\end{cases}
$$
$$
A(k) = k \int_0^\infty \Phi(\rho, 0) J_0(k\rho) \rho  d\rho = V k \int_0^a \rho J_0(k\rho)  d\rho
$$
计算积分:
$$
\int_0^a \rho J_0(k\rho)  d\rho = \frac{a}{k} J_1(ka)
$$
$$
A(k) = V a J_1(ka)
$$
代入得电势表达式:
$$
\Phi(\rho, z) = V a \int_0^\infty J_1(ka) J_0(k\rho) e^{-kz}  dk \tag{1}
$$

## (b) 轴线上的电势

在 $\rho = 0$ 处, $J_0(0) = 1$, 因此
$$
\Phi(0, z) = V a \int_0^\infty J_1(ka) e^{-kz}  dk
$$
利用标准积分公式:
$$
\int_0^\infty J_1(ka) e^{-kz}  dk = \frac{1}{a} \left(1 - \frac{z}{\sqrt{a^2 + z^2}}\right)
$$
代入得: 
$$
\Phi_0(z) = V \left(1 - \frac{z}{\sqrt{a^2 + z^2}}\right) \tag{2}
$$

## (c) 边缘上的电势

在 $\rho = a$ 处, 由 (1) 式得:
$$
\Phi(a, z) = V a \int_0^\infty J_1(ka) J_0(ka) e^{-kz}  dk \tag{3}
$$
$$
I := \int_0^\infty J_1(ka) J_0(ka) e^{-kz}  dk
$$
利用恒等式
$$
J_1(x) J_0(x) = -\frac{1}{2a} \frac{d}{dk} \left[J_0(ka)^2\right]
$$
$$
I = -\frac{1}{2a} \int_0^\infty e^{-kz} \frac{d}{dk} \left[J_0(ka)^2\right] dk
$$
于是
$$
I = -\frac{1}{2a} \left[ e^{-kz} J_0(ka)^2 \Big|_0^\infty + z \int_0^\infty e^{-kz} J_0(ka)^2  dk \right]
= \frac{1}{2a} - \frac{z}{2a} \int_0^\infty e^{-kz} J_0(ka)^2  dk \tag{4}
$$
$$
I_1 := \int_0^\infty e^{-kz} J_0(ka)^2  dk
$$
利用恒等式:
$$
J_0(ka)^2 = \frac{1}{\pi} \int_0^\pi J_0(2ka \cos\phi)  d\phi
$$
代入得:
$$
I_1 = \frac{1}{\pi} \int_0^\pi \left[ \int_0^\infty e^{-kz} J_0(2ka \cos\phi)  dk \right] d\phi
= \frac{1}{\pi} \int_0^\pi \frac{d\phi}{\sqrt{z^2 + 4a^2 \cos^2\phi}}
$$
计算该积分得:
$$
I_1 = \frac{2}{\pi \sqrt{z^2 + 4a^2}} K(k), \quad \text{其中 } k = \frac{2a}{\sqrt{z^2 + 4a^2}} \tag{5}
$$

这里 $K(k)$ 是第一类完全椭圆积分.

将 (5) 代入 (4)
$$
I = \frac{1}{2a} - \frac{z}{2a} \cdot \frac{2}{\pi \sqrt{z^2 + 4a^2}} K(k)
= \frac{1}{2a} - \frac{z}{\pi a \sqrt{z^2 + 4a^2}} K(k)
$$
代入 (3) 得
$$
\Phi(a, z) = V a \cdot I = \frac{V}{2} - \frac{V z}{\pi \sqrt{z^2 + 4a^2}} K(k)
= \frac{V}{2} \left[1 - \frac{k z}{\pi a} K(k)\right] \tag{6}
$$
其中 $k = \dfrac{2a}{\sqrt{z^2 + 4a^2}}$.



# 习题 3.13

>[!question] 习题 3.13
>使用文中得到的适当格林函数求解[[Jackson 第3章#习题 3.1]]的电势，并验证通过此方法得到的答案与微分方程的直接解一致。

## 解答

$$\Phi(\mathbf{x}) = -\frac{1}{4\pi} \oint_{S} \Phi(\mathbf{x}') \frac{\partial G}{\partial n'} dS' $$
其中 $S$ 是边界 $r=a,b$ 两个面, $\nabla'^{2}G=-4\pi\delta(\mathbf{x}-\mathbf{x}')$ 且在 $S$ 上 $G=0$ 用勒让德多项式展开格林函数
$$G(\mathbf{x},\mathbf{x}') = \sum_{l=0}^{\infty} \frac{2l+1}{4\pi} g_{l}(r,r') P_{l}(\cos \gamma) $$
则系数满足
$$\begin{gather}
\frac{d}{dr}\left( r^{2} \frac{dg_{l}}{dr} \right) - l(l+1)g_{l} = -4\pi\delta(r-r') \\
g_{l}(r,r^{+}) = g_{l}(r,r^{-}) \\
\frac{\partial g_{l}}{\partial r'}_{+} - \frac{\partial g_{l}}{\partial r'}_{-} = -\frac{4\pi}{r} \\
g_{l}(a,r') = g_{l}(b,r') = 0
\end{gather} $$
通解为
$$g_{l}(r,r') = \left\{  \begin{gather}
A\left( r'^{l} - \frac{a^{2l+1}}{r^{l+1}} \right) & a<r'<r \\
B\left( r'^{l} - \frac{b^{2l+1}}{r'^{l+1}} \right) & r<r'<b
\end{gather} \right. $$
再代入两个连续性条件即可得到
$$g_{l}(r,r') = -\frac{4\pi}{(2l+1)(b^{2l+1} - a^{2l+1})} r_{<}^{l} r_{>}^{l} \left(  1-\left( \frac{a}{r_{<}} \right)^{2l+1}  \right) \left(  1-\left( \frac{b}{r_{>}} \right)^{2l+1}  \right) $$
下计算格林函数在边界上的导数
$$\left. \frac{\partial G}{\partial n'} \right|_{r=a} = \sum_{l=0}^{\infty} \frac{2l+1}{4\pi} \frac{(2l+1)a^{l-1}}{1-(a / b)^{2l+1}} \left(  \frac{1}{a^{l+1}} - \frac{a^{l}}{b^{2l+1}} \right) P_{l}(\cos \gamma)  $$
$$\left. \frac{\partial G}{\partial n'} \right|_{r=b} = \sum_{l=0}^{\infty} \frac{2l+1}{4\pi} \frac{(2l+1)}{1-(a / b)^{2l+1}} \frac{1}{b^{l+2}} \left(  b^{l} - \frac{a^{2l+1}}{b^{l+1}} \right) P_{l}(\cos \gamma)   $$


# 习题 3.14

>[!question] 习题 3.14
>一根长度为 $2d$、总电荷为 $Q$ 的线电荷，其线电荷密度随 $(d^2 - z^2)$ 变化，其中 $z$ 是到中点的距离。一个内半径 $b > d$ 的接地导电球壳以线电荷的中点为球心。
>
>(a) 将球壳内各处的电势表示为勒让德多项式的展开式。
>
>(b) 计算球壳上感应的面电荷密度。
>
>(c) 在 $d \ll b$ 的极限下，讨论你对 (a) 和 (b) 部分的解答。

## (a) 球壳内电势

$$Q = \int_{-d}^{d} K(d^{2}-z^{2})dz  \quad \to \quad K = \dfrac{3Q}{4d^3}   $$

系统具有轴向对称性, 故电势的形式为
$$\Phi(r,\theta,\phi) = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} \left[  A_{lm}r^{l} + \frac{B_{lm}}{r^{l+1}}  \right] Y_{lm}(\theta,\phi) = \sum_{l=0}^{\infty} \left[ A_{l}r^{l} + \frac{B_{l}}{r^{l+1}}  \right] P_{l}(\cos \theta) $$
现在注意到系统其实还关于 $x-y$ 平面对称所以 $l$ 只取偶数, 表达式进一步简化为
$$\Phi(r,\theta) = \sum_{n=0}^{\infty} \left[  A_{2n}r^{2n} + \frac{B_{2n}}{r^{2n+1}}  \right]P_{2n}(\cos \theta) $$
从物理的角度, 电势由带电线和感应电荷共同产生
$$\Phi = \Phi_{\text{line}} + \Phi_{\text{img}} $$
而
$$\begin{align}
\Phi_{\text{line}}(r,\theta) &= \frac{1}{4\pi\varepsilon_{0}} \int_{-d}^{d} \frac{\lambda(z')}{|\mathbf{r}-z' \hat{\mathbf{z}}|} dz' = \frac{1}{4\pi\varepsilon_{0}} \sum_{l=0}^{\infty}\int_{-d}^{d} \lambda(z')  \frac{r_{<}^{l}}{r_{>}^{l+1}}P_{l}(\cos \theta)P_{l}(\cos \theta') dz'  \\
&= \frac{1}{4\pi\varepsilon_{0}} \sum_{n=0}^{\infty} 2P_{2n}(\cos \theta) \int_{-d}^{d} \lambda(z') \frac{r_{<}^{2n}}{r_{>}^{2n+1}} dz' \\
\end{align}$$
将感应电荷产生的电势也展开
$$\Phi_{\text{img}} = \sum_{n=0}^{\infty} C_{2n} r^{2n}P_{2n}(\cos \theta) $$
现在使用边界条件
$$\Phi(b,\theta) = 0 $$
得到
$$\sum_{n=0}^{\infty} C_{2n}b^{2n}P_{2n}(\cos \theta) = - \Phi_{\text{line}}(b,\theta) = \frac{1}{4\pi\varepsilon_{0}}\sum_{n=0}^{\infty} 2P_{2n}(\cos \theta) \frac{1}{b^{2n+1}} \int_{0}^{d} \lambda(z') z'^{2n} dz' $$
$$C_{2n} = -\frac{1}{4\pi\varepsilon_{0}} \frac{2}{b^{4n+1}} \int_{0}^{d} \lambda(z')z'^{2n}dz' = -\frac{1}{4\pi\varepsilon_{0}} \frac{2}{b^{4n+1}} \frac{2Kd^{2n+3}}{(2n+1)(2n+3)} $$
其中 $K = \dfrac{3Q}{4d^3}$ .

总而言之暂且保留 $\lambda(z')$ 的积分表达为
$$
\Phi(r,\theta) = \frac{1}{4\pi\varepsilon_{0}} \sum_{n=0}^{\infty} 2P_{2n}(\cos \theta)\left[  \int_{0}^{d} \lambda(z') \frac{r_{<}^{2n}}{r^{2n+1}_{>}} dz' - \frac{r^{2n}}{b^{4n+1}} \int_{0}^{d} \lambda(z')z'^{2n}dz'  \right] 
$$

## (b) 球壳上感应电荷面密度

在球壳上时 $r>d$ 所以
$$\Phi(r,\theta) = \frac{1}{4\pi\epsilon_0} \sum_{n=0}^{\infty} P_{2n}(\cos\theta) \left[ \frac{2}{r^{2n+1}} \int_0^d \lambda(z) z^{2n}  dz - \frac{2r^{2n}}{b^{4n+1}} \int_0^d \lambda(z) z^{2n}  dz \right] $$
于是
$$\sigma(\theta) = -\varepsilon_{0} \frac{\partial \Phi}{\partial n} = \frac{1}{4\pi b^{2}} \sum_{n=0}^{\infty} P_{2n}(\cos\theta) \left[ \frac{4n+2}{b^{2n}} \int_0^d \lambda(z) z^{2n}  dz + \frac{4n}{b^{2n}} \int_0^d \lambda(z) z^{2n}  dz \right] $$

## (c) 球壳远大于带电线


$$\Phi(r,\theta) = \frac{1}{4\pi\varepsilon_{0}} \sum_{n=0}^{\infty} 2P_{2n}(\cos \theta)\left[  \int_{0}^{d} \lambda(z') \frac{r_{<}^{2n}}{r^{2n+1}_{>}} dz' - \frac{r^{2n}}{b^{4n+1}} \int_{0}^{d} \lambda(z')z'^{2n}dz'  \right] $$
$d\ll b$ 可以简单评估一下
$$\int_{0}^{d} \lambda(z') \frac{r_{<}^{2n}}{r^{2n+1}_{>}} dz' \sim \frac{d^{3}}{r} $$
$$\frac{r^{2n}}{b^{4n+1}} \int_{0}^{d} \lambda(z') z'^{2n} dz' \sim \frac{d^{2n+4}}{b^{4n+1}}r^{2n} = \left( \frac{rd}{b^{2}} \right)^{2n} \frac{d}{b}  \frac{d^{3}}{r}  $$
可见后一项的影响随着 $\frac{d}{b}$ 以指数级别衰减, 同时电势是随着 $\frac{d}{r}$ 也变化明显的

我们考虑 $d\ll r$ 的情况:
当 $n=0$ 时
$$\int_{0}^{d} \frac{K(d^{2}-z'^{2})}{r} dz' = \frac{Q}{2r} $$
$$\int_{0}^{d} K(d^{2}-z'^{2}) dz' = Q $$
$$\Phi^{(0)} = \frac{Q}{4\pi\varepsilon_{0}} \left(  \frac{1}{r} - \frac{1}{b}  \right) $$
可见此时相当于带电线近似为点电荷
当 $n=1$ 时
$$\int_{0}^{d} \frac{K(d^{2}-z'^{2})z'^{2}}{r^{3}} dz' = \frac{Qd^{2}}{10r^{3}} $$
$$\int_{0}^{d} K(d^{2}-z'^{2})z'^{2}dz' = \frac{Qd^{2}}{10} $$
$$\Phi^{(1)} = \frac{1}{4\pi\varepsilon_{0}} \frac{Qd^{2}}{5} P_{2}(\cos \theta) \left(  \frac{1}{r^{3}} - \frac{r^{2}}{d^{5}}  \right) $$
这一项是四级项

# 习题 3.15

>[!question] 习题 3.15
>考虑以下连接外部电路的电池的"球形牛"模型。一个半径为 $a$、电导率为 $\sigma$ 的球体嵌入在电导率为 $\sigma'$ 的均匀介质中。球体内存在一个作用于载流子的均匀（化学）力，方向沿 $z$ 轴；其强度作为进入欧姆定律的有效电场为 $F$。在稳态下，球体内外存在电场，且其表面存在面电荷。
>
>(a) 求空间各处的电场（除 $F$ 外）和电流密度。确定面电荷密度，并证明球的电偶极矩为
>
>$$p = 4\pi\epsilon_0\sigma a^3F/(\sigma + 2\sigma')$$
>
>(b) 证明通过球体上半半球流出的总电流为
>
>$$I = \frac{2\sigma\sigma'}{\sigma + 2\sigma'} \cdot \pi a^2 F$$
>
>计算球外的总功率耗散。使用集总电路关系 $P = I^2 R_e = IV_e$，求有效外部电阻 $R_e$ 和电压 $V_e$。
>
>(c) 求球体内的功率耗散，并推导有效内部电阻 $R_i$ 和电压 $V_i$。
>
>(d) 通过关系 $V_t = (R_e + R_i)I$ 定义总电压，并证明 $V_t = 4aF/3$，以及 $V_e + V_i = V_t$。证明 $IV_t$ 是"化学"力提供的功率。

## (a) 球的偶极矩

在球内有
$$\mathbf{j} = \sigma(\mathbf{E}+\mathbf{F}) $$
在球外有
$$\mathbf{j} = \sigma'\mathbf{E} $$
电势在球外满足拉普拉斯方程 $\nabla^{2}\phi=0$ 连续性条件有两个: 电势连续和电流连续
$$\begin{gather}
\phi_{\text{in}}(a,\theta) = \phi_{\text{out}}(a,\theta) \\
\mathbf{j}_{\text{in}}\cdot \mathbf{n} = \mathbf{j}_{\text{out}}\cdot \mathbf{n}
\end{gather} $$
而 $\mathbf{j}_{\text{in}}=\sigma( -\nabla \phi_{\text{in}} + \mathbf{F}  ),\mathbf{j}_{\text{out}}=-\sigma \nabla \phi_{\text{out}}$ 
系统有轴对称性所以不妨设电势为
$$\begin{gather}
\phi_{\text{in}} = \sum_{n=0}^{\infty} A_{n}r^{n}P_{n}(\cos \theta) \\
\phi_{\text{out}} = \sum_{n=0}^{\infty} \frac{B_{n}}{r^{n+1}} P_{n}(\cos \theta)
\end{gather}$$
代入边界条件得 $A_{n}=B_{n}=0,n\neq 1$
$$\begin{gather}
A_{1}a=\frac{B_{1}}{a^{2}} \\
\sigma A_{1} + 2\sigma'A_{1} = \sigma F \\
\end{gather} $$
所以
$$A_{1} = \frac{\sigma F}{\sigma+2\sigma'},\quad B_{1} = \frac{\sigma Fa^{3}}{\sigma+2\sigma'} $$
$$\begin{gather}
\phi_{\text{in}} = \frac{\sigma F}{\sigma+2\sigma'}r\cos \theta \\
\phi_{\text{out}} = \frac{\sigma Fa^{3}}{(\sigma+2\sigma')r^{2} }\cos \theta
\end{gather} $$
对于球外来说套用偶极子的电势 $\phi = \frac{p\cos \theta}{4\pi\varepsilon_{0}r^{2}}$ 所以等效的偶极矩大小为
$$p= \frac{4\pi\epsilon_0\sigma a^3F}{\sigma + 2\sigma'}$$
## (b) 电流分析

由上可知电场分布为
$$ \mathbf{E} = -\nabla \phi = \left\{ \begin{gather}
-\frac{\sigma F}{\sigma+2\sigma'}\hat{\mathbf{z}} & \text{球内} \\
\frac{\sigma Fa^{3}}{\sigma+2\sigma'}\left(  \frac{2\cos \theta}{r^{3}} \hat{\mathbf{r}} + \frac{\sin \theta}{r^{3}} \hat{\boldsymbol{\theta}}  \right) & \text{球外}
\end{gather} \right. $$
 从而
$$\mathbf{j} = \left\{ \begin{gather}
\frac{2\sigma \sigma'F}{\sigma+2\sigma'}\hat{\mathbf{z}} & \text{球内} \\
\frac{\sigma \sigma' Fa^{3}}{\sigma+2\sigma'}\left(  \frac{2\cos \theta}{r^{3}} \hat{\mathbf{r}} + \frac{\sin \theta}{r^{3}} \hat{\boldsymbol{\theta}}  \right) & \text{球外}
\end{gather} \right. $$
所以从上半球面流出的电流为
$$I = \frac{2\sigma \sigma'F}{\sigma+2\sigma'} \iint \hat{\mathbf{z}} \cdot \hat{\mathbf{n}} dS = \frac{2\sigma \sigma'Fa^{2}}{\sigma+2\sigma'} \int_{0}^{2\pi} d\phi \int_{0}^{\pi/2} \sin \theta\cos \theta d\theta = \frac{2\pi\sigma \sigma'Fa^{2}}{\sigma+2\sigma'} $$

功率是
$$P = \int \mathbf{j}\cdot \mathbf{E} dV = \int_{r<a} \sigma(\mathbf{E}+\mathbf{F})\cdot \mathbf{E} dV + \int_{r>a} \sigma'|\mathbf{E}|^{2} dV $$
分别计算即可
$$\int_{r<a} |\mathbf{E}|^{2} dV = \frac{\sigma^{2} F^{2}}{(\sigma+2\sigma')^{2}} \int_{0}^{2\pi} d\phi \int_{0}^{\pi} \sin \theta d\theta \int_{0}^{a} r^{2}dr = \frac{4\pi\sigma^{2} F^{2}r^{3}}{3(\sigma+2\sigma')^{2}} $$
$$\int_{r>a} |\mathbf{E}|^{2} dV = \frac{\sigma^{2} F^{2}a^{6}}{(\sigma+2\sigma')^{2}} \int_{0}^{2\pi} d\phi \int_{0}^{\pi}(4\cos^2\theta + \sin^2\theta)\sin \theta d\theta \int_{a}^{\infty} \frac{1}{r}dr =  $$
$$\int_{r<a} \mathbf{E}\cdot \mathbf{F} dV = -\frac{\sigma F}{\sigma+2\sigma'} \int_{0}^{2\pi} d\phi \int_{0}^{\pi} \sin \theta \cos \theta d\theta \int_{0}^{a} r^{2}dr = $$
所以
$$P = \frac{8\pi \sigma \sigma'F^{2}a^{3}}{3(\sigma+2\sigma')} $$
而电流大小为 $I=\frac{2\pi\sigma \sigma'Fa^{2}}{\sigma+2\sigma'}$ 所以等效电压为
$$V_{e} = \frac{P}{I} = \frac{8\pi \sigma \sigma'F^{2}a^{3}}{3(\sigma+2\sigma')} \frac{\sigma+2\sigma'}{2\pi\sigma \sigma'Fa^{2}} = \frac{4Fa}{3(\sigma+2\sigma')} $$
等效电阻为
$$R_{e} = \frac{V_{e}}{I} = \frac{4Fa}{3(\sigma+2\sigma')} \frac{\sigma+2\sigma'}{2\pi\sigma \sigma'Fa^{2}} = \frac{2}{3\pi \sigma \sigma'a} $$

## (c) 化学力


# 习题 3.16

>[!question] 习题 3.16
>(a) 从贝塞尔微分方程出发，通过适当的极限过程，验证 (3.108) 式的推广形式：
>
>$$\frac{1}{k} \delta(k - k') = \int_{0}^{\infty} \rho J_{\nu}(k\rho)J_{\nu}(k' \rho)  d\rho$$
>或等价地
>$$\frac{1}{\rho} \delta(\rho - \rho') = \int_{0}^{\infty} k J_{\nu}(k\rho)J_{\nu}(k\rho')  dk$$
>
>其中 $\text{Re}(\nu) > -1$。
>
>(b) 得到以下展开式：
>
>$$\frac{1}{|\mathbf{x} - \mathbf{x}'|} = \sum_{m=-\infty}^{\infty} \int_{0}^{\infty} dk  e^{im(\phi - \phi')} J_{m}(k\rho)J_{m}(k\rho') e^{-k(z_{>}-z_{<})}$$
>
>(c) 通过适当的极限过程证明以下展开式：
>
>$$\frac{1}{\sqrt{\rho^{2} + z^{2}}} = \int_{0}^{\infty} e^{-k|z|} J_{0}(k\rho)  dk$$
>
>$$J_{0}(k\sqrt{\rho^{2} + \rho'^{2}} - 2\rho \rho' \cos \phi) = \sum_{m=-\infty}^{\infty} e^{im\phi} J_{m}(k\rho) J_{m}(k\rho')$$
>
>$$e^{ik\rho \cos \phi} = \sum_{m=-\infty}^{\infty} i^{m} e^{im\phi} J_{m}(k\rho)$$
>
>(d) 从最后一个结果得到贝塞尔函数的积分表示：
>
>$$J_{m}(x) = \frac{1}{2\pi i^{m}} \int_{0}^{2\pi} e^{ix \cos \phi - im\phi}  d\phi$$
>
>与标准积分表示进行比较。


## (a) $\delta$ 函数的贝塞尔函数表达

参数形式的贝塞尔函数满足微分方程
$$\frac{d}{dx}(xy') + \left( k^{2}x-\frac{\nu^{2}}{x} \right)y=0 ,\quad y(x) = J_{\nu}(kx) $$
于是记 $u(x)=J_{\nu}(kx),v(x)=J_{\nu}(k'x)$ 
$$\begin{gather}
\frac{d}{dx}(xu') + \left( k^{2}x - \frac{\nu^{2}}{x} \right)u = 0 \\
\frac{d}{dx}(xv') + \left( k'^{2}x - \frac{\nu^{2}}{x} \right)v = 0
\end{gather} $$
$$v \frac{d}{dx}(xu') - u \frac{d}{dx}(xv') + (k^{2}-k'^{2})xuv = 0 $$
$$\frac{d}{dx}( x(vu' - uv' ) ) + (k^{2}-k'^{2})xuv = 0 $$
所以
$$\int_{0}^{\infty} \rho J_{\nu}(k\rho)J_{\nu}(k'\rho) d\rho = \lim_{ R \to \infty } \frac{R[k'J_{\nu}(kR)J_{\nu}'(k'R) - kJ_{\nu}(k'R)J_{\nu}'(kR)]}{k^{2}-k'^{2}}  $$
考虑到
$$J_{\nu}(x) \sim \sqrt{ \frac{2}{\pi x} } \cos\left( x - \frac{\nu \pi}{2} -\frac{\pi}{4} \right) $$
代入得
$$\int_{0}^{\infty} \rho J_{\nu}(k\rho)J_{\nu}(k'\rho) d\rho  =  \lim_{ R \to \infty } \frac{1}{\pi k} \frac{\sin(k^{2}-k'^{2})R}{k-k'} = \frac{\delta(k-k')}{k} $$
将变量 $k\leftrightarrow \rho$ 即可得到
$$\int_{0}^{\infty} kJ_{\nu}(k\rho)J_{\nu}(k\rho')d\rho = \frac{\delta(\rho-\rho')}{\rho} $$

## (b) 球坐标下点电荷贝塞尔函数展开

显然我们是要展开自由空间的格林函数在柱坐标中
$$G(\mathbf{x},\mathbf{x}') = \frac{1}{|\mathbf{x}-\mathbf{x}'|} $$
其满足泊松方程 $\nabla^{2}G=1-4\pi\delta(\mathbf{x}-\mathbf{x}')$ 分离变量格林函数
$$G(\mathbf{x},\mathbf{x}') = \sum_{m=-\infty}^{\infty} e^{ im(\phi-\phi') } \int_{0}^{\infty} R_{m}(k,\rho,\rho') Z_{m}(k,\rho,\rho') dk $$
实际上 $\delta$ 函数在第一章 [[Jackson 第1章#习题 1.2 (?)]] 中讨论过也可以分离变量
$$\delta(\mathbf{x}-\mathbf{x}') = \frac{\delta(\rho-\rho')\delta(\phi-\phi')\delta(z-z')}{\rho} $$
考虑到
$$\delta(\phi-\phi') = \sum_{m=-\infty}^{\infty} \frac{1}{2\pi}e^{ im(\phi-\phi') } $$
$$\int_{0}^{\infty} kJ_{\nu}(k\rho)J_{\nu}(k\rho')d\rho = \frac{\delta(\rho-\rho')}{\rho} $$
于是我们现在只要匹配一下 $z$ 方向了, 实际上只要验证 $e^{ -k|z-z'| }$ 可以二阶导出 $\delta(z-z')$ 就行, $Z$ 满足的方程:
$$\frac{d^{2}Z}{dz^{2}} = k^{2}Z -2k\delta(z-z') $$
容易验证 $Z = e^{ \pm k|z-z'| }$ 满足方程, 但是又由边界条件(在无穷远处的电势应当趋于零)排除发散解, 于是 $Z = e^{ -k|z-z'| }$ 所以
$$\frac{1}{|\mathbf{x}-\mathbf{x}'|} = \sum_{m=-\infty}^{\infty} \int_{0}^{\infty} dk  e^{im(\phi - \phi')} J_{m}(k\rho)J_{m}(k\rho') e^{-k(z_{>}-z_{<})} $$

## (c) 柱坐标下点电荷贝塞尔函数展开

考虑傅里叶变换
$$F(\mathbf{k},z) = \iint e^{ -i\mathbf{k}\cdot \boldsymbol{\rho} } \frac{1}{\sqrt{ \rho^{2} + z^{2} }} d^{2}\rho $$
则
$$F(\mathbf{k},z) = \int_{0}^{\infty} \int_{0}^{2\pi} e^{ -k\rho \cos(\phi-\phi') } \frac{\rho}{\sqrt{ \rho^{2} + z^{2} }} d\rho d\phi = 2\pi \int_{0}^{\infty} \frac{\rho J_{0}(k\rho)}{\sqrt{ \rho^{2} + z^{2} }} d\rho = \frac{2\pi}{k} e^{ -k|z| } $$
所以
$$f(\boldsymbol{\rho},z) = \frac{1}{(2\pi)^{2}} \int_{0}^{\infty} kdk \int_{0}^{2\pi} e^{ ik\rho \cos(\phi-\phi') } \frac{2\pi}{k} e^{ -k|z| } dz = \int_{0}^{\infty} e^{-k|z|} J_{0}(k\rho)  dk $$

考虑
$$J_{0}(kR) = \frac{1}{2\pi} \int_{0}^{2\pi} e^{ ikR\cos \theta }d\theta $$
其中取 $R\cos \theta =\rho \cos \theta - \rho'\cos(\theta-\phi)$ 则
$$J_{0}(kR) = \frac{1}{2\pi} \int_{0}^{2\pi} \exp[ ik(\rho \cos \theta - \rho'\cos(\theta-\phi)) ]d\theta $$
而 $\exp(iz\cos \psi)=\sum_{m=-\infty}^{+\infty}i^{m}J_{m}(z)e^{ im\psi }$ 则
$$\begin{gather}
e^{ ik\rho \cos \theta } = \sum_{m=-\infty}^{\infty} i^{m} J_{m}(k\rho) e^{ im\theta } \\
e^{ -ik\rho'\cos(\theta-\phi) } = \sum_{n=-\infty}^{\infty} i^{-n} J_{n}(k\rho') e^{ -in(\theta-\phi) }
\end{gather} $$
所以
$$\begin{align}
J_{0}(kR) &= \frac{1}{2\pi} \sum_{m,n=-\infty}^{\infty} i^{m-n} J_{m}(k\rho)J_{n}(k\rho') e^{ im\phi }\int_{0}^{2\pi} e^{ i(m-n)\theta } d\theta  \\
&= \sum_{m,n=-\infty}^{\infty} i^{m-n} J_{m}(k\rho)J_{n}(k\rho')e^{ im\phi }\delta_{mn} \\
&= \sum_{m=-\infty}^{\infty} e^{ im\phi } J_{m}(k\rho)J_{m}(k\rho')
\end{align}$$

考虑傅里叶展开
$$e^{ ik\rho \cos \phi } = \sum_{m=-\infty}^{\infty} c_{m}e^{ im\phi } $$
$$c_{m} = \frac{1}{2\pi} \int_{0}^{2\pi} e^{ ik\rho \cos \phi } e^{ -im\phi } d\phi $$
而
$$J_{m}(z) = \frac{1}{2\pi} \int_{0}^{2\pi} e^{ i(z\sin \theta-m\theta) }d\theta $$
所以
$$c_{m}=i^{m}J_{m}(k\rho) $$
于是
$$e^{ ik\rho \cos \phi } = \sum_{m=-\infty}^{\infty} i^{m}e^{ im\phi } J_{m}(k\rho) $$

## (d) 贝塞尔函数的积分表达

由上面知
$$\int_{0}^{2\pi} e^{ ik\rho \cos \phi } e^{ -im\phi } d\phi =\int_{0}^{2\pi} \sum_{n=-\infty}^{\infty} i^{n} e^{ i(m-n)\phi } J_{n}(k\rho) d\phi= 2\pi i^{m} J_{m}(k\rho) $$
$$ J_{m}(x) = \frac{1}{2\pi i^{m}} \int_{0}^{2\pi} e^{ix \cos \phi - im\phi}  d\phi $$
与标准的积分表达比较:
$$J_{n} = \frac{1}{\pi} \int_{0}^{\pi} \cos(x\sin \theta-n\theta) d\theta $$


# 习题 3.17

>[!question] 习题 3.17
>位于 $z = 0$ 和 $z = L$ 平面之间的无界空间的狄利克雷格林函数，允许我们讨论在电势为零的平行导电平面之间的点电荷或电荷分布。
>
>(a) 使用柱坐标证明格林函数的一种形式为
>$$G(\mathbf{x}, \mathbf{x}^{\prime}) = \frac{4}{L} \sum_{n=1}^{\infty} \sum_{m=-\infty}^{\infty} e^{im(\phi - \phi^{\prime})} \sin\left( \frac{n\pi z}{L} \right) \sin\left( \frac{n\pi z^{\prime}}{L} \right) I_m \left( \frac{n\pi}{L} \rho_< \right) K_m \left( \frac{n\pi}{L} \rho_> \right)$$
>
>(b) 证明格林函数的另一种形式为
>$$G(\mathbf{x}, \mathbf{x}') = 2 \sum_{m=-\infty}^{\infty} \int_{0}^{\infty} dk  e^{im(\phi - \phi')} J_m(k\rho) J_m(k\rho') \frac{\sinh(kz_<) \sinh[k(L - z_>)]}{\sinh(kL)}$$
>其中 $\rho_<$ 和 $\rho_>$ 分别表示 $\rho$ 和 $\rho'$ 中的较小者和较大者，$z_<$ 和 $z_>$ 分别表示 $z$ 和 $z'$ 中的较小者和较大者。

## (a) 柱坐标下格林函数的一种级数形式

格林函数满足
$$\begin{gather}
\nabla^2 G = \frac{1}{\rho} \frac{\partial }{\partial \rho}\left(  \rho  \frac{\partial G}{\partial \rho}  \right) + \frac{1}{\rho^{2}} \frac{\partial^{2}G}{\partial \phi^{2}} + \frac{\partial^{2}G}{\partial z^{2}} = -\frac{4\pi\delta(\rho-\rho')\delta(\phi-\phi')\delta(z-z')}{\rho}  \\
G(\rho,\phi,0) = G(\rho,\phi,L) = 0
\end{gather} $$
分离变量先固定 $(\rho',\phi',z')$, 显然 $G=R(\rho)\Phi(\phi)Z(z)$ 则对于 $z$ 其边界条件和微分方程对应的特征函数是 
$$Z(z) = \sin \frac{n\pi z}{L}, \quad n=0,1,2,\dots \quad k_{n}:=\frac{n\pi}{L} $$
对于 $\phi$ 其自然边界条件和微分方程对应的特征函数是
$$\Phi(\phi) = e^{ im\phi },\quad m=0,\pm 1,\pm 2,\dots $$
于是格林函数可以展开为
$$G(\mathbf{x},\mathbf{x}') = \sum_{n=1}^{\infty} \sum_{m=-\infty}^{\infty} g_{mn}(\rho) \sin \frac{n\pi z}{L} e^{ im\phi } $$
类似的 $\delta$ 函数也有展开
$$\delta(\mathbf{x}-\mathbf{x}') = -\frac{4\pi}{\rho} \delta(\rho-\rho') \frac{2}{L}\left(\sum_{n=0}^{\infty} \sin \frac{n\pi z}{L} \sin \frac{n\pi z'}{L}\right)\left(  \frac{1}{2\pi}\sum_{m=-\infty}^{\infty} e^{ im\phi }e^{ -im\phi' }  \right) $$
重新代回泊松方程
$$\left[  \frac{1}{\rho} \frac{\partial}{\partial \rho}\left(  \rho   \frac{\partial}{\partial \rho}  \right) -\left( k_{n}^{2} + \frac{m^{2}}{\rho^{2}} \right) \right] g_{mn}(\rho) = -\frac{4}{\rho L}\delta(\rho-\rho') \sin \frac{n\pi z'}{L} e^{ -im\phi' }  $$
$$g_{mn}(\rho) := h_{mn}(\rho) \sin \frac{n\pi z'}{L} e^{ -im\phi' } $$
于是
$$\left[  \frac{d}{d\rho}\left( \rho  \frac{d}{d\rho} \right) - \left(  k_{n}^{2}\rho + \frac{m^{2}}{\rho} \right)  \right]h_{mn}(\rho) = -\frac{4}{L}\delta(\rho-\rho') $$
显然必须有 $\rho=0$ 处有限 $r\to \infty$ 处衰减为零, 所以解为当 $\rho<\rho'$ 时 $h_{mn}\sim I_{m}(k_{n}\rho)$ 当 $\rho>\rho'$ 时 $h_{mn}\sim K_{m}(k_{n}\rho)$ 所以 $h_{mn}=AI_{m}(k_{n}\rho_{<})K_{m}(k_{n}\rho_{>})$ 最后代入方程对比系数即可
$$h_{mn}(\rho) = \frac{4}{L}I_{m}(k_{n}\rho_{<})K_{m}(K_{n}\rho_{>}) $$
最终
$$G(\mathbf{x}, \mathbf{x}^{\prime}) = \frac{4}{L} \sum_{n=1}^{\infty} \sum_{m=-\infty}^{\infty} e^{im(\phi - \phi^{\prime})} \sin\left( \frac{n\pi z}{L} \right) \sin\left( \frac{n\pi z^{\prime}}{L} \right) I_m \left( \frac{n\pi}{L} \rho_< \right) K_m \left( \frac{n\pi}{L} \rho_> \right)$$

## (b) 柱坐标下格林函数的一种积分形式

首先格林函数可以展开为
$$G(\mathbf{x},\mathbf{x}') = \sum_{m=-\infty}^{\infty} g_{m}(\rho,z,\rho',z') e^{ im(\phi-\phi') } $$
代入泊松方程
$$\left[  \frac{1}{\rho} \frac{\partial}{\partial \rho}\left( \rho  \frac{\partial}{\partial \rho} \right) - \frac{m^{2}}{\rho^{2}} + \frac{\partial^{2}}{\partial z^{2}}  \right]g_{m} = -\frac{2}{\rho} \delta(\rho-\rho') \delta(z-z') $$
对 $g_{m}$ 进行汉克尔变换
$$\tilde{g}_{m}(k,z) = \int_{0}^{\infty} \rho g_{m}(\rho,z)J_{m}(k\rho) d\rho $$
$$\left[  \frac{\partial^{2}}{\partial z^{2}} -k^{2}  \right]\tilde{g}_{m} = -2J_{m}(k\rho')\delta(z-z') $$
$$\tilde{g}_{m}(k,0) = \tilde{g}_{m}(k,L) = 0 $$
对于 $z$ 这就是一个简单的亥姆霍兹方程, 线性无关解为 $\sinh kz$ , $\sinh k(L-z)$ 当 $z>z'$ 时 $\tilde{g}_{m}\sim \sinh k(L-z)$ 当 $z<z'$ 时 $\tilde{g}_{m}\sim \sinh kz$ 故
$$\tilde{g}_{m}(k,z) = f(k)\sinh kz\sinh k(L-z) $$
显然其满足连续性条件, 下面使用跳跃导数条件导出 $f(k)$ :
$$\left.\frac{d\tilde{g}_{m}}{dz}\right|_{z'^{+}} - \left.\frac{d\tilde{g}_{m}}{dz}\right|_{z'^{-}} = -2J_{m}(k\rho) $$
$$f(k) = \frac{2J_{m}(k\rho)}{k\sinh kL} $$
于是
$$\tilde{g}_{m}(k,z) = \frac{2J_{m}(k\rho)}{k\sinh kL} \sinh kz\sinh k(L-z) $$
$$g_{m}(\rho,z) = \int_{0}^{\infty} \rho\tilde{g}_{m}(k,z)J_{m}(k\rho)dk = 2\int_{0}^{\infty} J_{m}(k\rho)J_{m}(k\rho') \frac{\sinh kz\sinh k(L-z)}{\sin kL} dk $$
$$G(\mathbf{x}, \mathbf{x}') = 2 \sum_{m=-\infty}^{\infty} \int_{0}^{\infty} dk  e^{im(\phi - \phi')} J_m(k\rho) J_m(k\rho') \frac{\sinh(kz_<) \sinh[k(L - z_>)]}{\sinh(kL)} $$


# 习题 3.18

>[!question] 习题 3.18
>对问题 3.12 的配置进行修改，在与带有圆盘插入的平面平行且距离 $L$ 处放置一个保持零电势的导电平面。为明确起见，将接地平面置于 $z = 0$，将带有圆盘中心的另一平面置于 $z = L$ 处的 $z$ 轴上。
>
>(a) 证明两平面之间的电势在柱坐标 $(z, \rho, \phi)$ 下可以写成
>$$\Phi(z, \rho) = V \int_0^\infty d\lambda  J_1(\lambda)J_0(\lambda \rho/a) \frac{\sinh(\lambda z/a)}{\sinh(\lambda L/a)}$$
>
>(b) 证明在 $a \to \infty$ 且 $z$、$\rho$、$L$ 固定的极限下，(a) 部分的解会简化为预期结果。将你的结果视为 $a^{-1}$ 幂级数展开中的最低阶答案，考虑如果 $a$ 远大于 $\rho$ 和 $L$ 但不为无穷大时，对最低阶表达式的修正问题。是否存在困难？你能否获得修正的显式估计？
>
>(c) 考虑 $L \to \infty$ 且 $(L - z)$、$a$ 和 $\rho$ 固定的极限，证明问题 3.12 的结果得以恢复。对于 $L \gg a$ 但不趋于无穷大的情况，修正如何？

## (a) 柱坐标下电势的积分表达

系统轴对称, 电势满足
$$\begin{gather}
\nabla^{2}\Phi = \frac{1}{\rho} \frac{\partial}{\partial \rho}\left( \rho  \frac{\partial \Phi}{\partial \rho} \right) + \frac{\partial^{2}\Phi}{\partial z^{2}} = 0 \\
\Phi(\rho,0) = 0 \\
\Phi(\rho,L) = f(\rho) = \begin{cases}
0, & \rho>a \\
V, & \rho<a
\end{cases}
\end{gather} $$
管您能不能分离变量, 先分离变量, 大不了就积分变换 $\Phi(\rho,z)=R(\rho)Z(z)$ 则
$$\frac{1}{\rho} \frac{d}{d \rho}\left( \rho  \frac{dR}{d \rho} \right) + k^{2}R=0,\quad \frac{d^{2}Z}{dz^{2}} -k^{2}Z=0  $$
$z$ 方向显然解可以表示为
$$Z(z) = A\sinh kz $$
$\rho$ 方向显然解表示为
$$R(\rho) = J_{0}(k\rho) $$
$$\Phi(\rho,z) = \int_{0}^{\infty} A(k)\sinh kzJ_{0}(k\rho)dk $$
于是汉克变换一下
$$\Phi(\rho,L) = \int_{0}^{\infty} A(k)J_{0}(k\rho)\sinh kL dk = f(\rho) $$
$$A(k)\sinh kL = \int_{0}^{\infty} \rho f(\rho)J_{0}(k\rho)d\rho = \frac{Va}{k}J_{1}(ka) $$
所以
$$\Phi(\rho,z) = \int_{0}^{\infty} \frac{Va}{k}J_{1}(ka) J_{0}(k\rho) \frac{\sinh kz}{\sinh kL} dk = V \int_0^\infty d\lambda  J_1(\lambda)J_0(\lambda \rho/a) \frac{\sinh(\lambda z/a)}{\sinh(\lambda L/a)} $$

## (b) $a\to \infty$ 极限

此情况下
$$ J_{0}\left( \frac{\lambda \rho}{a} \right) \sim 1 ,\quad \sinh \frac{\lambda z}{a}\sim \frac{\lambda z}{a},\quad \sinh \frac{\lambda L}{a} \sim \frac{\lambda L}{a} $$
那么
$$\Phi \sim V\int_{0}^{\infty} d\lambda J_{1}(\lambda) \frac{z}{L} = V\cdot \frac{z}{L} $$
实际上这是零级近似, 它表示两板间电势线性变化, 实际上就是平行板电容器. 但是题目要求的是含 $a$ 的一阶近似. 尝试幂级数展开
$$\begin{gather}
J_{0}\left( \frac{\lambda \rho}{a} \right) = 1 - \frac{\lambda^{2}\rho^{2}}{4a^{2}} + \mathcal O\left( \frac{1}{a^{4}} \right) \\
\frac{\sinh(\lambda z /a)}{\sinh(\lambda L /a)} = \frac{z}{L}\left[  1 + \frac{\lambda^{2}}{6a^{2}}(z^{2}-L^{2}) + \mathcal O\left( \frac{1}{a^{4}} \right)  \right]
\end{gather} $$
于是
$$\Phi = \frac{Vz}{L} \int_{0}^{\infty} J_{1}(\lambda)d\lambda + \frac{Vz}{L} \left(  \frac{z^{2}-L^{2}}{6a^{2}} -\frac{\rho^{2}}{4a^{2}} \right) \int_{0}^{\infty} \lambda^{2}J_{1}(\lambda)d\lambda + \mathcal O\left( \frac{1}{a^{4}} \right) $$
然而其中的 $\int \lambda^{2}J_{1}(\lambda )d\lambda$ 是发散的

## (c) $L\to \infty$

此情况下
$$\frac{\sinh(\lambda z / a)}{\sinh(\lambda L /a)} \sim e^{ -\lambda(L-z)/a } - e^{ -\lambda(L+z)/a } + e^{ -\lambda(L-3z)/a } - e^{ -\lambda(L+3z)/a } + \dots $$
可见对比[[Jackson 第3章#习题 3.12]]的解只是将 $z$ 替换为了 $L\pm z,L\pm 3{z},\dots$ 于是可以将解写作
$$\Phi(\rho,z) = \Phi^{*}(\rho,L-z) - \Phi^{*}(\rho,L+z) + \dots $$
其中 $\Phi^{*}$ 是3.12的解(虽然在3.12中我们只求了两个特殊解 $\Phi^{*}(0,z)$ 和 $\Phi^{*}(a,z)$ ) 

# 习题 3.19

>[!question] 习题 3.19
>考虑一个点电荷 $q$ 位于两个电势为零的无限平行导电平面之间。设平面在柱坐标系中位于 $z = 0$ 和 $z = L$ 处，电荷位于 $z$ 轴上的 $z = z_0$ 处，且 $0 < z_0 < L$。使用[[Jackson 第1章#习题 1.12 格林互易定理]]的格林互易定理，以[[Jackson 第3章#习题 3.18]]作为比较问题。
>
>(a) 证明在 $z = L$ 的板上，半径为 $a$、中心在 $z$ 轴上的圆内感应的电荷量为
>$$Q_L (a) = -\frac{q}{V} \Phi (z_0, 0)$$
>其中 $\Phi (z_0, 0)$ 是问题 3.18 中在 $z = z_0$、$\rho = 0$ 处求得的电势。求上板上的总感应电荷。与问题 1.13 的解法（方法和答案）进行比较。
>
>(b) 证明上板上的感应电荷密度可以写成
>$$\sigma (\rho) = -\frac{q}{2\pi} \int_{0}^{\infty} dk \frac{\sinh (kz_0)}{\sinh (kL)} kJ_0 (k\rho)$$
>该积分可以（例如，参见 Gradshteyn and Ryzhik, p. 728, formula 6.666）表示为涉及修正贝塞尔函数 $K_0 (n\pi \rho / L)$ 的无穷级数，表明在大径向距离处感应电荷密度以 $(\rho)^{-1/2} e^{-\pi \rho / L}$ 的形式衰减。
>
>(c) 证明在 $\rho = 0$ 处的电荷密度可以写成级数形式
>$$\sigma (0) = -\frac{q}{2\pi L^2} \sum_{n>0, \, \text{奇}} [(n - z_0/L)^{-2} - (n + z_0/L)^{-2}]$$

## (a) 上板的感应电荷总量

使用格林互易定理考虑两个系统

系统1: 点电荷在轴线上 $z_{0}$ 处, 两个无限大导板接地且位于 $z=0,L$ . 感应电荷分布在半径为 $a$ 中心在轴线上的圆内记为 $Q_{L}(a)$ .

系统2: 两个无限大导板位于 $z=0,L$ , $z=0$ 的板子接地, $z=L$ 的板子在半径为 $a$ 中心在轴线上的圆内保持电势为 $V$ . 其系统的电势为 $\Phi(\rho,z)$, $\Phi(0,z_{0})$ 是系统1中点电荷所在位置的电势.

由格林互易定理
$$q\Phi(0,z_{0}) + Q_{L}(a)V = 0 \quad \to \quad Q_{L}(a) = -\frac{q}{V}\Phi(0,z_{0}) $$
其中的 $\Phi(0,z_{0})$ 可参考[[Jackson 第3章#习题 3.18]]或[[Jackson 第3章#习题 3.12#(b) 轴线上的电势]].

总的感应电荷就是取 $a\to \infty$ 于是可以知道的
$$\Phi(0,z_{0}) \to \frac{Vz_{0}}{L} $$
$$Q_{L\text{ tolta}} = -\frac{qz_{0}}{L} $$

## (b) 上板的感应电荷面密度

直接从 3.17 中借过来电势表达
$$\Phi = 2q \int_{0}^{\infty} \frac{\sinh kz_{0}\sinh k(L-z)}{\sinh kL} J_{0}(k\rho)dk $$
于是
$$\sigma = -\frac{1}{4\pi} \left.\frac{\partial \Phi}{\partial z}\right|_{z=L} = \frac{q}{2\pi} \int_{0}^{\infty} k \frac{\sinh kz_{0}}{\sinh kL} J_{0}(k\rho) dk $$
为什么少一个负号？怎么量纲没对上？

## (c) 中心处的电荷密度

在 $\rho=0$ 时 $J_{0}(k\rho)=1$ 所以我们要去展开
$$\frac{\sinh kz_{0}}{\sinh kL} = (e^{ kz_{0} } - e^{ -kz_{0} })e^{ -kL }\sum_{n=0}^{\infty} e^{ -2kLn } = \sum_{n=0}^{\infty} [ e^{ -k((2n+1)L-z_{0}) } - e^{ -k((2n+1)L-z_{0}) }  ] $$
于是
$$\begin{align}
\sigma(0) &= \frac{q}{2\pi} \sum_{n=0}^{\infty} \int_{0}^{\infty} k[ e^{ -k((2n+1)L-z_{0}) } - e^{ -k((2n+1)L-z_{0}) } ] dk \\ &= \frac{q}{2\pi} \sum_{n=0}^{\infty} \left[  \frac{1}{((2n+1)L-z_{0})^{2}} - \frac{1}{((2n+1)L+z_{0})^{2}}  \right]   \\
&= \frac{q}{2\pi} \sum_{n>0,\text{odd}} \left[  \frac{1}{(nL-z_{0})^{2}} - \frac{1}{(nL+z_{0})^{2}}  \right]
\end{align}$$



# 习题 3.20

>[!question] 习题 3.20
>(a) 根据[[Jackson 第3章#习题 3.17]]的结果或从基本原理出发，证明位于两个电势为零的无限平行导电平面之间的点电荷 $q$ 在某点的电势可表示为
>$$\Phi(z, \rho) = \frac{q}{\pi \epsilon_0 L} \sum_{n=1}^\infty \sin\left(\frac{n\pi z_0}{L}\right) \sin\left(\frac{n\pi z}{L}\right) K_0 \left(\frac{n\pi \rho}{L}\right)$$
>其中平面位于 $z = 0$ 和 $z = L$，电荷位于 $z$ 轴上的点 $z = z_0$ 处。
>
>(b) 计算下板 ($z=0$) 和上板 ($z=L$) 上的感应面电荷密度 $\sigma_0(\rho)$ 和 $\sigma_L(\rho)$。$\sigma_L(\rho)$ 的结果为
>$$\sigma_L(\rho) = \frac{q}{L^2} \sum_{n=1}^\infty (-1)^n n \sin\left( \frac{n\pi z_0}{L} \right) K_0 \left( \frac{n\pi\rho}{L} \right)$$
>讨论此表达式与问题 3.19b 和 3.19c 中表达式的联系。
>
>(c) 根据 (b) 部分的答案，计算 $z = L$ 处板上的总电荷 $Q_L$。通过傅里叶级数求和或其他比较方法，用问题 1.13 的已知表达式检验你的答案 [C. Y. Fong and C. Kittel, Am. J. Phys. **35**, 1091 (1967)]。

## (a) 电势表达

由 3.17 可知系统的格林函数为
$$G(\mathbf{x}, \mathbf{x}^{\prime}) = \frac{4}{L} \sum_{n=1}^{\infty} \sum_{m=-\infty}^{\infty} e^{im(\phi - \phi^{\prime})} \sin\left( \frac{n\pi z}{L} \right) \sin\left( \frac{n\pi z^{\prime}}{L} \right) I_m \left( \frac{n\pi}{L} \rho_< \right) K_m \left( \frac{n\pi}{L} \rho_> \right) $$
取源点为 $\mathbf{x}'=(0,0,z_{0})$ 也就是 $\rho'=0$ , $\phi'$ 任意处. 此时 $I_{m}\left( \frac{n\pi \rho_{<}}{L} \right) =I_{m}(0)=0$ , $I_{0}(0)=1$ .
$$G(\mathbf{x},\mathbf{x}') = \frac{4}{L} \sum_{n=1}^{\infty} \sin \frac{n\pi z}{L} \sin \frac{n\pi z'}{L} K_{0}\left( \frac{n\pi \rho}{L} \right) $$
于是
$$\Phi(\rho ,z) = \frac{1}{4\pi\varepsilon_{0}}G(\mathbf{x},\mathbf{x}')\rho(\mathbf{x}') = \frac{q}{\pi \epsilon_0 L} \sum_{n=1}^\infty \sin\left(\frac{n\pi z_0}{L}\right) \sin\left(\frac{n\pi z}{L}\right) K_0 \left(\frac{n\pi \rho}{L}\right) $$

## (b) 电荷面密度

$$\sigma_{L}(\rho) = -\frac{1}{4\pi}\left. \frac{\partial \Phi}{\partial z}\right|_{z=L} = -\frac{1}{4\pi} \frac{q}{\pi\varepsilon_{0}L} \sum_{n=0}^{\infty} \frac{n\pi}{L} \sin \frac{n\pi z_{0}}{L} \cos n\pi K_{0}\left( \frac{n\pi \rho}{L} \right) $$
证毕

而下板为
$$\sigma_{0}(\rho) = -\frac{1}{4\pi} \frac{q}{\pi\varepsilon_{0}L} \sum_{n=0}^{\infty} \frac{n\pi}{L} \sin \frac{n\pi z_{0}}{L} K_{0}\left( \frac{n\pi \rho}{L} \right) = - \frac{q}{4\pi\varepsilon_{0}L^{2}} \sum_{n=1}^{\infty} n\sin \frac{n\pi z_{0}}{L}K_{0}\left( \frac{n\pi \rho}{L} \right) $$

## (c) 总感应电荷量

$$Q_{L} = 2\pi\int_{0}^{\infty} \rho\sigma(\rho)d\rho = \frac{q}{L^{2}} \sum_{n=1}^{\infty} \int_{0}^{\infty} (-1)^{n}n \sin \frac{n\pi z_{0}}{L}K_{0}\left( \frac{n\pi \rho}{L} \right)\rho d\rho $$
其中
$$\int_{0}^{\infty} \rho K_{0}\left( \frac{n\pi \rho}{L} \right) d\rho = \frac{1}{(n\pi /L)^{2}} $$
所以
$$Q_{L} = q \sum_{n=1}^{\infty} \frac{(-1)^{n}n}{n^{2}\pi^{2}}\sin \frac{n\pi z_{0}}{L} = \frac{2q}{\pi} \sum_{n=1}^{\infty} \frac{(-1)^{n}}{n}\sin \frac{n\pi z_{0}}{L} = -\frac{qz_{0}}{L} $$


# 习题 3.21

>[!question] 习题 3.21
>(a) 通过在 $L \to \infty$ 的极限下使用[[Jackson 第3章#习题 3.17#(b) 柱坐标下格林函数的一种积分形式]]的格林函数，证明位于接地导电平面上方、与之平行且距离为 $d$、半径为 $R$ 的扁平薄导电圆盘的电容由下式给出：
>$$\frac{4\pi \epsilon_0}{C} = \frac{\int_{0}^{\infty} dk(1 - e^{-2kd}) \left[ \int_{0}^{R} \rho J_0(k\rho)\sigma(\rho)  d\rho \right]^2}{\left[ \int_{0}^{R} \rho\sigma(\rho)  d\rho \right]^2}$$
>其中 $\sigma(\rho)$ 是圆盘上的电荷密度。
>
>(b) 将 (a) 部分的表达式用作 $C^{-1}$ 的变分或平稳原理，并假设 $\sigma(\rho) =$ 常数。明确证明当 $d \ll R$ 时，你得到正确的 $C^{-1}$ 极限值。确定孤立圆盘 ($d \gg R$) 的 $C^{-1}$ 近似值，并将其与精确结果 $4\pi \epsilon_0/C = (\pi/2)R^{-1}$ 的比值求值。
>
>(c) 作为 $\sigma(\rho)$ 的更好试验形式，考虑常数和 $(R^2 - \rho^2)^{-1/2}$ 的线性组合，后者是孤立圆盘的正确形式。
>
>对于 (b) 部分，以下积分可能有用：
>$$\int_{0}^{\infty} dt \left[ \frac{J_1(t)}{t} \right]^2 = \frac{4}{3\pi}, \quad \int_{0}^{\infty} \frac{dt  J_1^2(t)}{t} = \frac{1}{2}$$

## (a) 电容

格林函数是
$$G(\mathbf{x}, \mathbf{x}') = 2 \sum_{m=-\infty}^{\infty} \int_{0}^{\infty} dk  e^{im(\phi - \phi')} J_m(k\rho) J_m(k\rho') \frac{\sinh(kz_<) \sinh[k(L - z_>)]}{\sinh(kL)}   $$
当 $L\to \infty$ 时
$$\frac{\sinh k(L-z_{>})}{\sinh kL}\to e^{ -kz_{>} } $$
在圆盘上的点 $z=z'=d$
$$\sinh kz_{<} e^{ -kz_{>} } = \frac{1-e^{ -2kd }}{2} $$
$$G(\mathbf{x},\mathbf{x}') = \sum_{m=-\infty}^{\infty} \int_{0}^{\infty} dk e^{ im(\phi-\phi') } J_{m}(k\rho) J_{m}(k\rho') (1-e^{ -2kd }) = \int_{0}^{\infty} dk J_{0}(k|\boldsymbol{\rho}-\boldsymbol{\rho}'|)(1-e^{ -2kd }) $$
最后一步使用了加法公式 $\sum_{m} e^{ im(\phi-\phi') }J_{m}(k\rho)J_{m}(k\rho')=J_{0}(k|\boldsymbol{\rho}-\boldsymbol{\rho}'|)$ 其中 $\boldsymbol{\rho}$ 是二维的坐标矢量

电荷为
$$Q = 2\pi\int_{0}^{R} \rho \sigma(\rho) d\rho $$
系统静电能为
$$W = \frac{1}{8\pi\varepsilon_{0}} \iint \sigma(\mathbf{x}) G(\mathbf{x},\mathbf{x}') \sigma(\mathbf{x}') dSdS' $$
所以
$$\frac{4\pi\varepsilon_{0}}{C} = \frac{\iint \sigma(\mathbf{x})G(\mathbf{x},\mathbf{x}')\sigma(\mathbf{x}')dSdS'}{Q^{2}} $$
所以下面开始计算分子的积分

$$\int_{0}^{\infty} dk(1-e^{ -2kd }) \iint J_{0}(k|\boldsymbol{\rho}-\boldsymbol{\rho}'|) \sigma(\rho)\sigma(\rho') dSdS' $$
其中
$$\begin{align}
\iint &= \int_{0}^{R}\int_{0}^{2\pi}\int_{0}^{R}\int_{0}^{2\pi} \rho \rho' \sigma(\rho)\sigma(\rho')J_{0}(k|\boldsymbol{\rho}-\boldsymbol{\rho}'|) d\rho d\phi d\rho'd\phi' \\
&= \int_{0}^{R}\rho\sigma(\rho)d\rho \int_{0}^{R}\rho'\sigma(\rho')d\rho' \iint_{[0,2\pi]^{2}} J_{0}(k|\boldsymbol{\rho}-\boldsymbol{\rho}'|) d\phi d\phi' \\
&= \int_{0}^{R} \rho \sigma(\rho)d\rho \int_{0}^{R} \rho'\sigma(\rho') d\rho' \cdot (2\pi)^{2} J_{0}(k\rho)J_{0}(k\rho') \\
&= \left(  2\pi \int_{0}^{R} \rho \sigma(\rho)J_{0}(k\rho) d\rho  \right)^{2}
 \end{align} $$
 倒数第二步使用的是加法公式 $J_{0}(k|\boldsymbol{\rho}-\boldsymbol{\rho}'|)=\sum_{m} e^{ im(\phi-\phi') }J_{m}(k\rho)J_{m}(k\rho')$ 然后对 $\phi,\phi'$ 积分就是 $\delta$ 函数 $\int_{9}^{2\pi} e^{ im\phi }d\phi=2\pi\delta_{m0}$ 所以 $\iint J_{0}d\phi d\phi'=(2\pi)^{2}J_{0}(k\rho)J_{0}(k\rho')$ .

## (b) 电荷均匀分布近似

现在 $\sigma(\rho)=\sigma_{0}$ 带进去化简一下
$$\begin{gather}
\text{分子 }= \sigma_{0}^{2} \int_{0}^{\infty} (1-e^{ -2kd }) dk \left(  \int_{0}^{R} \rho J_{0}(k\rho) d\rho \right)^{2} \\
\text{分母 }= \sigma_{0}^{2} \left(  \int_{0}^{R} \rho d\rho  \right)^{2} = \frac{\sigma_{0}^{2}R^{4}}{4}
\end{gather} $$
考虑到
$$\int_{0}^{R} \rho J_{0}(k\rho)d\rho = \frac{R}{k}J_{1}(kR) $$
于是
$$\frac{4\pi\varepsilon_{0}}{C} = \frac{4}{R^{2}} \int_{0}^{\infty} \frac{1-e^{ -2kd }}{k^{2}}J_{1}^{2}(kR)dk = \frac{4}{R} \int_{0}^{\infty} \frac{1-e^{ -\alpha x }}{x^{2}}J_{1}^{2}(x)dx $$
其中 $\alpha=\frac{2d}{R}$ .

当 $d\ll R$ 时 $\alpha\to 0$ 考虑将其展开
$$1-e^{ -\alpha x } = \alpha x - \frac{1}{2}\alpha^{2}x^{2} + \dots $$
$$\int_{0}^{\infty} \frac{\alpha}{x}J_{1}^{2}(x)dx = \frac{\alpha}{2},\quad \int_{0}^{\infty} \frac{\alpha^{2}}{2}J_{1}^{2}(x)dx = \frac{\alpha^{2}}{4} $$
所以
$$\frac{4\pi\varepsilon_{0}}{C} = \frac{4d}{R^{2}}\left(  1- \frac{d}{R} + \mathcal O(\alpha^{2})  \right) $$

当 $d\gg R$ 时 $\alpha\to \infty$ 考虑另一种展开方式
$$1-e^{ -\alpha x } = 1 + \mathcal O\left( \frac{1}{\alpha} \right) $$
$$\int_{0}^{\infty} \frac{1}{x^{2}} J_{1}^{2}(x) dx = \frac{4}{3\pi} $$
所以
$$\frac{4\pi\varepsilon_{0}}{C} = \frac{16}{3\pi R}\left(  1+ \mathcal O\left( \frac{1}{\alpha} \right)  \right) $$
此结果与精确的相比

$$\frac{\left( \frac{4\pi\varepsilon_{0}}{C} \right)_{\text{app}}}{\left( \frac{4\pi\varepsilon_{0}}{C} \right)_{\text{exa}}} = \frac{16 / (3\pi R)}{\pi / (2R)} = 1.081 $$

## (c) 进一步的拟合

意思是取试验的电荷密度为
$$\sigma(\rho) = c_{1} + \frac{c_{2}}{\sqrt{ R^{2} - \rho^{2} }} $$
然后再算一遍, 这里显然 $c_{2}$ 的占比越大结果就越精确. 计算略


# 习题 3.22

>[!question] 习题 3.22
>一个二维势问题的几何结构在极坐标中由曲面 $\phi = 0$、$\phi = \beta$ 和 $\rho = a$ 定义，如图所示。
>![[Pasted image 20251201203524.png]]
>使用极坐标中的分离变量法，证明格林函数可以写成
>$$G(\rho, \phi; \rho', \phi') = \sum_{m=1}^\infty \frac{4}{m} \rho^{m\pi/\beta}_< \left( \frac{1}{\rho^{m\pi/\beta}_>} - \frac{\rho^{m\pi/\beta}_>}{a^{2m\pi/\beta}} \right) \sin \left( \frac{m\pi \phi}{\beta} \right) \sin \left( \frac{m\pi \phi'}{\beta} \right)$$
>
>[[Jackson 第2章#习题 2.25]]可能有用。

## 证明

我重新表述一下问题, 它是说格林函数满足
$$\begin{gather}
\nabla^{2}G = -4\pi\delta(\mathbf{x}-\mathbf{x}') \\
G(\rho,0;\rho'\phi') = G(\rho,\beta;\rho',\phi') = G(a,\phi;\rho',\phi')=0
\end{gather} $$
将 $G$ 按 $\phi$ 的特征函数展开
$$G = \sum_{n=0}^{\infty} R(\rho;\rho',\phi') \sin \frac{n\pi \phi}{\beta} $$
由对称性
$$G = \sum_{n=1}^{\infty} R(\rho,\rho') \sin \frac{n\pi \phi}{\beta} \sin \frac{n\pi \phi'}{\beta} $$
现在径向的方程为
$$\left[\frac{1}{\rho } \frac{d}{d\rho} \left(  \rho  \frac{dR}{d\rho}  \right) - \frac{m^{2}\pi^{2}}{\beta^{2}\rho^{2}} \right] R = -\frac{4\pi}{\rho} \delta(\rho-\rho') $$
即
$$\left[  \frac{d}{d\rho}\left( \rho  \frac{dR}{d\rho} \right)  - \frac{m^{2}\pi^{2}R}{\beta^{2}\rho} \right]  = -4\pi \delta(\rho-\rho') $$
$$R(a,\rho')=0 $$
解是
$$R = \left\{ \begin{gather}
C\rho^{\nu}, & \rho<\rho' \\
D\left( \rho^{\nu} - \frac{a^{2\nu}}{\rho^{\nu}} \right), & \rho>\rho'
\end{gather} \right. $$
其中 $\nu=\frac{m\pi}{\beta}$ . 使用连续性条件即可
$$R = \left\{ \begin{gather}
-\frac{4\pi}{\beta \nu} \left(  \frac{\rho'^{\nu}}{a^{2\nu}} - \frac{1}{\rho'^{\nu}}  \right)  \rho^{\nu}, & \rho<\rho' \\
-\frac{4\pi}{\beta \nu} \frac{\rho'^{\nu}}{a^{2\nu}} \left( \rho^{\nu} - \frac{a^{2\nu}}{\rho^{\nu}} \right), & \rho>\rho'
\end{gather} \right. = \frac{4\pi}{\beta \nu} \left[  \frac{\rho_{<}^{\nu}}{\rho_{>}^{\nu}} - \frac{(\rho_{<}\rho_{>})^{\nu}}{a^{2\nu}}  \right] $$
于是
$$G(\rho, \phi; \rho', \phi') = \sum_{m=1}^\infty \frac{4}{m} \rho^{m\pi/\beta}_< \left( \frac{1}{\rho^{m\pi/\beta}_>} - \frac{\rho^{m\pi/\beta}_>}{a^{2m\pi/\beta}} \right) \sin \left( \frac{m\pi \phi}{\beta} \right) \sin \left( \frac{m\pi \phi'}{\beta} \right)$$



# 习题 3.23

>[!question] 习题 3.23
>一个点电荷 $q$ 位于接地圆柱形盒子内部的点 $(\rho', \phi', z')$，该盒子由曲面 $z = 0$、$z = L$、$\rho = a$ 定义。证明盒子内部的电势可以用以下交替形式表示：
>
>$$\Phi(\mathbf{x}, \mathbf{x}') = \frac{q}{\pi \epsilon_0 a} \sum_{m=-\infty}^{\infty} \sum_{n=1}^{\infty} \frac{e^{im(\phi - \phi')} J_m \left( \frac{x_{mn}\rho}{a} \right) J_m \left( \frac{x_{mn}\rho'}{a} \right)}{x_{mn} J_{m+1}^2 (x_{mn}) \sinh \left( \frac{x_{mn}L}{a} \right)} \times \sinh \left[ \frac{x_{mn}}{a} z_< \right] \sinh \left[ \frac{x_{mn}}{a} (L - z_>) \right]$$
>
>$$\begin{align}
\Phi(\mathbf{x}, \mathbf{x}') = \frac{q}{\pi \epsilon_0 L} \sum_{m=-\infty}^{\infty} \sum_{n=1}^{\infty}& e^{im(\phi - \phi')} \sin \frac{n\pi z}{L}  \sin \frac{n\pi z'}{L}  \frac{I_m \left( \frac{n\pi\rho_<}{L} \right)}{I_m \left( \frac{n\pi a}{L} \right)} \\& \times \left[ I_m \left(\frac{n\pi a}{L} \right) K_m \left( \frac{n\pi\rho_>}{L} \right) - K_m \left( \frac{n\pi a}{L} \right) I_m \left( \frac{n\pi\rho_>}{L} \right) \right]
\end{align}$$
>
>$$\Phi(\mathbf{x}, \mathbf{x}') = \frac{2q}{\pi \epsilon_0 L a^2} \sum_{m=-\infty}^{\infty} \sum_{k=1}^{\infty} \sum_{n=1}^{\infty} \frac{e^{im(\phi - \phi')} \sin \left( \frac{k\pi z}{L} \right) \sin \left( \frac{k\pi z'}{L} \right) J_m \left( \frac{x_{mn}\rho}{a} \right) J_m \left( \frac{x_{mn}\rho'}{a} \right)}{ \left[ \left( \frac{x_{mn}}{a} \right)^2 + \left( \frac{k\pi}{L} \right)^2 \right] J_{m+1}^2 (x_{mn})}$$
>
>讨论最后一个展开式（带有额外的求和）与其他两个展开式的关系。

## 证明

### 第一个形式

格林函数满足
$$\begin{gather}
\nabla^{2}G = -4\pi\delta(\mathbf{x}-\mathbf{x}') \\
G(a,\phi,z;\rho',\phi',z')=G(\rho,\phi,0;\rho',\phi',z')=G(\rho,\phi,L;\rho',\phi',z')=0
\end{gather} $$
将格林函数按 $\phi,\rho$ 展开
$$G = \sum_{m=-\infty}^{\infty} e^{ im(\phi-\phi') } \sum_{n=1}^{\infty} J_{m}(k_{mn}\rho) J_{m}(k_{mn}\rho') g_{mn}(z,z') $$
其中 $k_{mn}=\frac{x_{mn}}{a}$ , $x_{mn}$ 是 $J_{m}(x)$ 的第 $n$ 个根, 类似的
$$\delta(\mathbf{x}-\mathbf{x}') = \frac{1}{2\pi} \sum_{m=-\infty}^{\infty} e^{ im(\phi-\phi') } \sum_{n=1}^{\infty} \frac{2}{a^{2}} \frac{J_{m}(k_{mn}\rho)J_{m}(k_{mn}\rho')}{J_{m+1}^{2}(x_{mn})} \delta(z-z') $$
所以得到 $z$ 的方程
$$\left(  \frac{d^{2}}{dz^{2}} - k_{mn}^{2}  \right) g_{mn} = -\frac{4}{a^{2}J_{m+1}^{2}(x_{mn})} \delta(z-z') $$
$$g_{mn}(0,z')=g_{mn}(L,z')=0 $$
由对称性和连续性容易猜出解为
$$g_{mn}(z,z') = A_{mn} \sinh k_{mn}z_{<} \sinh k_{mn}(L-z_{>}) $$
再利用导数跳跃条件, 可以解得
$$A = \frac{4}{a^{2}k_{mn}J_{m+1}^{2}(x_{mn})\sinh k_{mn}L} $$
于是 $\Phi=\frac{q}{4\pi\varepsilon_{0}}G$ 
$$\Phi(\mathbf{x}, \mathbf{x}') = \frac{q}{\pi \epsilon_0 a} \sum_{m=-\infty}^{\infty} \sum_{n=1}^{\infty} \frac{e^{im(\phi - \phi')} J_m \left( \frac{x_{mn}\rho}{a} \right) J_m \left( \frac{x_{mn}\rho'}{a} \right)}{x_{mn} J_{m+1}^2 (x_{mn}) \sinh \left( \frac{x_{mn}L}{a} \right)}\sinh \left[ \frac{x_{mn}}{a} z_< \right] \sinh \left[ \frac{x_{mn}}{a} (L - z_>) \right] $$

### 第二个形式

类似的, 但这次先按 $\phi,z$ 展开
$$G = \sum_{m=-\infty}^{\infty} e^{ im(\phi-\phi') } \sum_{n=1}^{\infty} \sin \frac{n\pi z}{L} \sin \frac{n\pi z'}{L} g_{mn}(\rho;\rho') $$
剩下的问题全部在二维极坐标下讨论, 所以泊松方程化为
$$ \left[  \frac{d}{d\rho}\left( \rho  \frac{d}{d\rho} \right) - \left(  k_{n}^{2}\rho + \frac{m^{2}}{\rho}  \right) \right] g_{mn} = -\frac{4}{L}\delta(\rho-\rho'),\quad k_{n}=\frac{n\pi}{L} $$
这个玩意的解我们也讨论过, 从对称性和连续性的角度, 解的形式只能是
$$R_{mn}(\rho,\rho') = A_{mn}I_{m}(k_{n}\rho_{<})[ I_{m}(k_{n}\rho_{>})K_{m}(k_{n}a) - K_{m}(k_{n}\rho_{>})I_{m}(k_{n}a) ] $$
再代入导数跳跃条件可以解得
$$A_{mn} = \frac{4}{LI_{m}(k_{n}a)} $$
于是
$$\begin{align}
\Phi(\mathbf{x}, \mathbf{x}') = \frac{q}{\pi \epsilon_0 L} \sum_{m=-\infty}^{\infty} \sum_{n=1}^{\infty}& e^{im(\phi - \phi')} \sin \frac{n\pi z}{L}  \sin \frac{n\pi z'}{L}  \frac{I_m \left( \frac{n\pi\rho_<}{L} \right)}{I_m \left( \frac{n\pi a}{L} \right)} \\& \times \left[ I_m \left(\frac{n\pi a}{L} \right) K_m \left( \frac{n\pi\rho_>}{L} \right) - K_m \left( \frac{n\pi a}{L} \right) I_m \left( \frac{n\pi\rho_>}{L} \right) \right]
\end{align} $$

### 第三个形式

猜都猜得出来, 这个形式就是完全展开了.

对于满足边界条件 $\psi=0$ 在 $z=0,L,\rho=a$ 上满足拉普拉斯方程的的本征函数是
$$\psi_{mnk}(\rho,\phi,z) = e^{ im\phi } J_{m}(k_{mn}\rho) \sin \frac{k\pi z}{L} $$
其中 $k_{n}$ 的定义遵从前面的描述. 它对应的本征值是
$$\lambda_{mnk} = -\left[  k_{mn}^{2} + \left( \frac{k\pi}{L} \right)^{2}  \right] $$
格林函数满足 $\nabla^{2}G = -4\pi\delta(\mathbf{x}-\mathbf{x}')$ 所以可以被本征函数展开为
$$G(\mathbf{x},\mathbf{x}') =\sum_{m,n,k} A_{mnk} \psi_{mnk}(\mathbf{x})\psi^{*}_{mnk}(\mathbf{x}') $$
由于在各个方向上都是正交的, 所以可以同过归一化确定系数
$$A_{mnk} = \sqrt{ \frac{2}{\pi La^{2}J_{m+1}^{2}(x_{mn})} } $$
于是
$$\Phi(\mathbf{x}, \mathbf{x}') = \frac{2q}{\pi \epsilon_0 L a^2} \sum_{m=-\infty}^{\infty} \sum_{k=1}^{\infty} \sum_{n=1}^{\infty} \frac{e^{im(\phi - \phi')} \sin \left( \frac{k\pi z}{L} \right) \sin \left( \frac{k\pi z'}{L} \right) J_m \left( \frac{x_{mn}\rho}{a} \right) J_m \left( \frac{x_{mn}\rho'}{a} \right)}{ \left[ \left( \frac{x_{mn}}{a} \right)^2 + \left( \frac{k\pi}{L} \right)^2 \right] J_{m+1}^2 (x_{mn})}$$

可见三种表达其实是一样的, 第三种表达是完全展开的形式, 为什么要专门强调有这么多的展开方式, 我猜是因为有的级数收敛的更快


# 习题 3.24

>[!question] 习题 3.24
>问题 3.23 中的导电圆柱盒子的所有壁面电势均为零，除了上端的一个圆盘，定义为 $\rho = b < a$，电势为 $V$。
>
>(a) 使用问题 3.23 中得到的格林函数的各种形式，求出圆柱内部电势的三种展开式。
>
>(b) 对于每个级数，假设 $b = L/4 = a/2$，数值计算在 $\rho = 0$、$z = L/2$ 处的电势与圆盘电势的比值。尝试获得至少两位有效数字的精度。是否有一个级数比其他级数收敛得慢？为什么？
>
>（Abramowitz 和 Stegun 有表格；Mathematica 有贝塞尔函数，Press 等人的软件也有。）

## (a) 电势的三种表达

### 第一种表达

$$G = \sum_{m,n} A_{mn}e^{ im(\phi-\phi') } J_{m}(k_{mn}\rho)J_{m}(k_{mn}\rho')\sinh k_{mn}z_{<}\sinh k_{mn}(L-z_{>}) $$
$$\frac{\partial G}{\partial z'} = \frac{4}{a} \sum_{m,n} e^{ im(\phi-\phi') } \frac{J_{m}(k_{mn}\rho)J_{m}(k_{mn}\rho')}{J_{m}^{2}(x_{mn})} \frac{\sinh k_{mn}z\cosh k_{mn}(L-z')}{\sinh k_{mn}L}  $$
在 $z'=L$ 处
$$\frac{\partial G}{\partial z'} = -\frac{4}{a} \sum_{m,n} e^{ im(\phi-\phi') } \frac{J_{m}(k_{mn}\rho)J_{m}(k_{mn}\rho')}{J_{m}^{2}(x_{mn})} \frac{\sinh k_{mn}z}{\sinh k_{mn}L}  $$
于是
$$\Phi(\mathbf{x}) = \frac{V}{4\pi} \int_{0}^{b} \rho'd\rho' \int_{0}^{2\pi} \frac{\partial G}{\partial z'}  d\phi' $$
其中
$$\int_{0}^{2\pi} e^{ im(\phi-\phi') } d\phi' = 2\pi\delta_{m 0} $$
$$\int_{0}^{b} \rho' J_{m}(k_{mn}\rho') d\rho' = \frac{J_{m+1}(k_{mn}b)}{x_{mn}} $$
所以

$$\Phi(\rho,z) = \frac{2Vb}{a} \sum_{n=1}^{\infty} \frac{J_{0}\left( \frac{x_{0n}\rho}{a} \right)J_{1}\left( \frac{x_{0n}b}{a} \right)\sinh\left( \frac{x_{0n}z}{a} \right)}{x_{0n}J_{1}^{2}(x_{0n})\sinh\left( \frac{x_{0n}L}{z} \right)} $$

### 第二种形式

$$G = \frac{4}{L} \sum_{m,n} e^{ im(\phi-\phi') }  \sin \frac{n\pi z}{L} \sin \frac{n\pi z'}{L}  \frac{I_{m}(k_{n}\rho_{<})[ I_{m}(k_{n}\rho_{>})K_{m}(k_{n}a) - K_{m}(k_{n}\rho_{>})I_{m}(k_{n}a) ]}{I_{m}(k_{n}a)}  $$
$$\frac{\partial G}{\partial z'} = \frac{4n\pi}{L^{2}} \sum_{m,n} e^{ im(\phi-\phi') }  \sin \frac{n\pi z}{L} \cos \frac{n\pi z'}{L}  \frac{I_{m}(k_{n}\rho_{<})[ I_{m}(k_{n}\rho_{>})K_{m}(k_{n}a) - K_{m}(k_{n}\rho_{>})I_{m}(k_{n}a) ]}{I_{m}(k_{n}a)} $$
在 $z'=L$ 处
$$\frac{\partial G}{\partial z'} = \frac{4n\pi}{L^{2}} \sum_{m,n} (-1)^{n} e^{ im(\phi-\phi') }  \sin \frac{n\pi z}{L} \frac{I_{m}(k_{n}\rho_{<})[ I_{m}(k_{n}\rho_{>})K_{m}(k_{n}a) - K_{m}(k_{n}\rho_{>})I_{m}(k_{n}a) ]}{I_{m}(k_{n}a)}  $$
故
$$\Phi(\mathbf{x}) = \frac{V}{4\pi} \int_{0}^{b} \rho'd\rho' \int_{0}^{2\pi} \frac{\partial G}{\partial z'}  d\phi'  $$
其中
$$\int_{0}^{2\pi} e^{ im(\phi-\phi') } d\phi' = 2\pi\delta_{m 0} $$
$$\int_{0}^{b} \rho'R(\rho,\rho')d\rho'=\dots  $$

### 第三种形式

$$G(\mathbf{x},\mathbf{x}') =\sum_{m,n,k} A_{mnk} \psi_{mnk}(\mathbf{x})\psi^{*}_{mnk}(\mathbf{x}') $$
$$\psi_{mnk}(\rho,\phi,z) = e^{ im\phi } J_{m}(k_{mn}\rho) \sin \frac{k\pi z}{L}  $$
于是
$$\frac{\partial G}{\partial z'} = \sum_{m,n,k} \frac{k\pi A_{mnk}}{L} \psi(\rho,\phi,z) e^{ -im\phi'} J_{m}(k_{mn}\rho') \cos \frac{k\pi z'}{L} $$
在 $z'=L$ 处
$$\frac{\partial G}{\partial z'} = \sum_{m,n,k} (-1)^{k+1} \frac{k\pi A_{mnk}}{L} \psi(\rho,\phi,z) e^{ -im\phi'} J_{m}(k_{mn}\rho')  $$
$$\Phi(\mathbf{x}) = \frac{V}{4\pi} \int_{0}^{b} \rho'd\rho' \int_{0}^{2\pi} \frac{\partial G}{\partial z'}  d\phi'  $$
其中
$$\int_{0}^{2\pi} e^{ im(\phi-\phi') } d\phi' = 2\pi\delta_{m 0}  $$
$$\int_{0}^{b} \rho' J_{m}(k_{mn}\rho') d\rho' = \frac{J_{m+1}(k_{mn}b)}{x_{mn}} $$
所以
$$\Phi(\rho,\phi) = \frac{4\pi Vb}{aL^{2}} \sum_{n,k=1}^{\infty} (-1)^{k+1} k\sin \frac{k\pi z}{L} \frac{J_{0}\left( \frac{x_{0n}\rho}{a} \right)J_{1}\left( \frac{x_{0n}b}{a} \right)}{x_{0n}J_{1}^{2}(x_{0n})\left[  \left( \frac{x_{0n}}{a} \right)^{2} + \left( \frac{k\pi}{L} \right)^{2} \right]} $$

## (b) 数值计算比较

不想弄

# 习题 3.25

>[!question] 习题 3.25
>考虑[[Jackson 第3章#习题 3.13]]中半径为 $a$ 的圆孔的导电平面问题的面电荷密度。
>
>(a) 证明平面上方和下方（$\rho \geq a$）的面电荷密度为
>$$\sigma_+(\rho) = -\epsilon_0 E_0 + \Delta \sigma(\rho)$$$$\sigma_-(\rho) = \epsilon_0 E_1 + \Delta \sigma(\rho)$$
>其中
>$$\Delta \sigma(\rho) = -\epsilon_0 \frac{(E_0 - E_1)}{\pi} \left[ \frac{a}{\sqrt{\rho^2 - a^2}} - \sin^{-1} \left( \frac{a}{\rho} \right) \right]$$
>$\Delta \sigma(\rho)$ 在大 $\rho$ 时如何表现？对于 $\rho < a$，用 $\Phi^{(1)}$ 定义的 $\Delta \sigma(\rho)$ 是否为零？请解释。
>
>(b) 通过直接积分证明
>$$\lim_{R \to \infty} \left[ 2\pi \int_a^R d\rho  \rho(\sigma_+ + \sigma_-) + 2\pi \epsilon_0 \int_0^R d\rho  \rho(E_0 - E_1) \right] = 0$$
>并解释其含义。

## (a) 电荷面密度

总电势分解为完整平面解与扰动势之和:
$$
\Phi_+ = E_0 z + \psi_+, \quad \Phi_- = E_1 z + \psi_-
$$
其中下标 $\pm$ 分别表示 $z>0$ 和 $z<0$. 扰动势 $\psi_\pm$ 在远处趋于零, 且在 $z=0$ 处满足:
- 当 $\rho > a$ 时 $\psi_\pm = 0$
- 当 $\rho < a$ 时 $\psi_+ = \psi_- = \psi$, 且  
$$\frac{\partial \psi_+}{\partial z} - \frac{\partial \psi_-}{\partial z} = E_1 - E_0$$

问题具有轴对称性, $\psi_\pm$ 与方位角无关. 对 $\psi_\pm$ 进行汉克尔变换
$$
\psi_+(\rho, z) = \int_0^\infty C(k) e^{-kz} J_0(k\rho)  dk, \quad
\psi_-(\rho, z) = \int_0^\infty C(k) e^{kz} J_0(k\rho)  dk
$$
其中 $C(k)$ 待定. 代入边界条件得到
$$
\int_0^\infty C(k) J_0(k\rho)  dk = 0, \quad \rho > a
$$
$$
\int_0^\infty k C(k) J_0(k\rho)  dk = \frac{E_0 - E_1}{2}, \quad \rho < a
$$
该方程的解为
$$
C(k) = \frac{a(E_0 - E_1)}{2k} J_1(ka)
$$
在导体部分 ($\rho > a$), 上表面的电场法向分量为
$$
E_z^+ = -\left.\frac{\partial \Phi_+}{\partial z}\right|_{z=0^+} = -E_0 - \left.\frac{\partial \psi_+}{\partial z}\right|_{z=0^+}
$$
利用汉克尔变换计算
$$
\left.\frac{\partial \psi_+}{\partial z}\right|_{z=0^+} = -\int_0^\infty k C(k) J_0(k\rho)  dk = -\frac{E_0 - E_1}{2} \cdot \frac{2}{\pi} \left[ \frac{a}{\sqrt{\rho^2 - a^2}} - \sin^{-1}\left(\frac{a}{\rho}\right) \right]
$$
代入得
$$
E_z^+ = -E_0 + \frac{E_0 - E_1}{\pi} \left[ \frac{a}{\sqrt{\rho^2 - a^2}} - \sin^{-1}\left(\frac{a}{\rho}\right) \right]
$$
因此. 上表面电荷密度 $\sigma_+ = \epsilon_0 E_z^+$ 为
$$
\sigma_+(\rho) = -\epsilon_0 E_0 + \Delta \sigma(\rho)
$$
其中
$$
\Delta \sigma(\rho) = -\epsilon_0 \frac{E_0 - E_1}{\pi} \left[ \frac{a}{\sqrt{\rho^2 - a^2}} - \sin^{-1}\left(\frac{a}{\rho}\right) \right]
$$
类似地
$$
\sigma_-(\rho) = \epsilon_0 E_1 + \Delta \sigma(\rho)
$$



# 习题 3.26

>[!question] 习题 3.26
>考虑适用于诺伊曼边界条件的格林函数，该边界条件用于由 $r = a$ 和 $r = b$（$a < b$）定义的同心球面之间的体积 $V$。为了能够使用 (1.46) 式求解电势，需施加简单约束 (1.45)。使用如下形式的球谐函数展开：
>$$G(\mathbf{x}, \mathbf{x}') = \sum_{l=0}^{\infty} g_l(r, r') P_l(\cos \gamma)$$
>其中 $g_l(r, r') = r'_< / r^{l+1}_> + f_l(r, r')$。
>
>(a) 证明对于 $l > 0$，径向格林函数具有对称形式：
>$$g_l = \frac{r'_<}{r^{l+1}_>} + \frac{1}{(b^{2l+1} - a^{2l+1})} \left[ \frac{l + 1}{l} (rr')^l + \frac{l}{l + 1} \frac{(ab)^{2l+1}}{(rr')^{l+1}} + a^{2l+1} \left( \frac{r'^l}{r^{l+1}} + \frac{r^l}{r'^{l+1}} \right) \right]$$
>
>(b) 证明对于 $l = 0$：
>$$g_0(r, r') = \frac{1}{r_>} - \left( \frac{a^2}{a^2 + b^2} \right) \frac{1}{r'} + f(r)$$
>其中 $f(r)$ 是任意的。在 (1.46) 式中明确证明电势 $\Phi(\mathbf{x})$ 的答案与 $f(r)$ 无关。[通过适当选择 $f(r)$ 对 $g_0$ 在 $r$ 和 $r'$ 上对称化，可以消除诺伊曼格林函数中的任意性。]



# 习题 3.27

>[!question] 习题 3.27
>将问题 3.26 的诺伊曼格林函数应用于以下情况：外表面 ($r = b$) 的法向电场为 $E_r = -E_0 \cos \theta$，内表面 ($r = a$) 的法向电场为 $E_r = 0$。
>
>(a) 证明体积 $V$ 内的静电势为
>$$\Phi(\mathbf{x}) = E_0 \frac{r \cos \theta}{1 - p^3} \left( 1 + \frac{a^3}{2r^3} \right)$$
>其中 $p = ab$。求电场的分量：
>$$E_r(r, \theta) = -E_0 \frac{\cos \theta}{1 - p^3} \left( 1 - \frac{a^3}{r^3} \right), \quad E_\theta(r, \theta) = E_0 \frac{\sin \theta}{1 - p^3} \left( 1 + \frac{a^3}{2r^3} \right)$$
>
>(b) 计算场的笛卡尔坐标或柱坐标分量 $E_z$ 和 $E_\rho$，并对典型情况 $p = 0.5$ 绘制电力线示意图或计算机图。

