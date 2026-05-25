---
up:
  - "[[写题]]"
---
# 习题 2.1

>[!question]
>一个点电荷 $q$ 被放置在距离无限大零电势导体平面 $d$ 远处. 使用镜像法, 求:
>
>(a) 平面上感应出的面电荷密度, 并绘图;
>(b) 通过电荷与其镜像之间的库仑定律求平面与电荷之间的力;
>(c) 通过对整个平面积分 $\sigma^2/2\epsilon_0$ 来计算作用在平面上的总力;
>(d) 将电荷 $q$ 从其位置移到无穷远所需的功;
>(e) 电荷 $q$ 与其镜像之间的势能 [与(d)的答案比较并讨论];
>(f) 对于最初距离表面 1 埃的电子, 求(d)的答案, 以电子伏特为单位.

## (a) 平面上的感应面电荷密度

使用镜像法, 在平面另一侧对称位置放置镜像电荷 $-q$. 在导体平面上, 电势为零. 在柱坐标系中, 面电荷密度为: 
$$\sigma(\rho) = -\frac{q d}{2\pi (\rho^2 + d^2)^{3/2}}$$
其中 $\rho^2 = x^2 + y^2$.

绘图略. 
## (b) 平面与电荷之间的力

电荷 $q$ 与其镜像 $-q$ 之间的距离为 $2d$. 根据库仑定律: 
$$F = \frac{1}{4\pi\epsilon_0} \frac{q(-q)}{(2d)^2} = -\frac{1}{4\pi\epsilon_0} \frac{q^2}{4d^2}$$
负号表示吸引力, 方向垂直于平面. 

## (c) 作用在平面上的总力

单位面积上的力为 $\sigma^2/(2\epsilon_0)$, 方向垂直于平面. 总力为: 
$$F = \int \frac{\sigma^2}{2\epsilon_0}  dA = \frac{1}{2\epsilon_0} \int_0^\infty \left[ -\frac{q d}{2\pi (\rho^2 + d^2)^{3/2}} \right]^2 2\pi\rho  d\rho = \frac{q^2}{16\pi\epsilon_0 d^2}$$
方向垂直于平面, 与(b)中力大小相等, 方向相反, 符合牛顿第三定律.

## (d) 将电荷移到无穷远所需的功

将电荷从 $d$ 移到无穷远所需的功为: 
$$W = \int_d^\infty -F(z)  dz = \int_d^\infty \frac{q^2}{16\pi\epsilon_0 z^2}  dz = \frac{q^2}{16\pi\epsilon_0 d}$$

## (e) 电荷与镜像之间的势能

电荷 $q$ 与镜像电荷 $-q$ 相距 $2d$, 它们的势能为: 
$$U = \frac{1}{4\pi\epsilon_0} \frac{q(-q)}{2d} = -\frac{q^2}{8\pi\epsilon_0 d}$$
与(d)比较: $|U| = 2W$. 这是因为在移动电荷 $q$ 时, 导体平面上的感应电荷分布也在变化. 系统的总能量变化等于外力做的功 $W$, 而点电荷与镜像电荷的势能 $U$ 只考虑了固定镜像电荷的情况.

这事很有意思, 因为它说明了体系变化过程中不止有这个外力做了功, 实际上由于这个无限大的平面板是接地的, 换言之是连接了电源的, 所以过程中外电源是做了功的, 并且滑稽的是它的存在使外力做了一份功, 那么它就会做两倍的异号的功给系统, 最终系统的能量反而上升了. 

## (f) 电子情况的功计算

对于电子, $q = e = 1.602 \times 10^{-19}$ C, $d = 1$ Å $= 10^{-10}$ m. 
$$W = \frac{e^2}{16\pi\epsilon_0 d} = \frac{(1.602 \times 10^{-19})^2}{16\pi (8.854 \times 10^{-12}) (10^{-10})} \approx 3.60 \times 10^{-19}  \text{J} = 3.60  \text{eV}$$
因此, 将电子从距离表面 1 埃处移到无穷远需要约 3.60 电子伏特的功.


# 习题 2.2

>[!question]
>使用镜像法讨论一个点电荷 $q$ 在半径为 $a$ 的空心接地导体球内的问题. 求:
>
>(a) 球内的电势;
>(b) 感应面电荷密度;
>(c) 作用在 $q$ 上的力的大小和方向.
>
>(d) 如果球被保持在固定电势 $V$ 上, 解是否会改变? 如果球的内外表面带有总电荷 $Q$ 呢?

## (a) 球内的电势

设点电荷 $q$ 位于球内距球心距离为 $d$ ($d < a$) 的位置. 根据镜像法, 需要在球外距离球心 $b = a^2/d$ 处放置一个镜像电荷 $q' = -qa/d$.

球内任意点 $P$ 的电势为: 
$$\Phi(P) = \frac{1}{4\pi\epsilon_0} \left( \frac{q}{r_1} + \frac{q'}{r_2} \right) = \frac{q}{4\pi\varepsilon_{0}} \left( \frac{1}{\sqrt{ r^2 + d^2 - 2rd \cos \theta }} - \frac{a}{d \sqrt{ r^{2} + \left( \frac{a^{2}}{d} \right)^2 - \frac{2ra^2}{d} \cos \theta }} \right) $$
其中: $r$ 是点 $P$ 到球心的距离, $\theta$ 是点 $P$ 与球心连线和点电荷与球心连线间的夹角

## (b) 感应面电荷密度

感应面电荷密度为: 
$$\sigma(\theta) = -\varepsilon_{0} \left. \frac{\partial \Phi}{\partial n} \right|_{r=a} = -\frac{q}{4\pi a^2} \cdot \frac{a^2 - d^2}{(a^2 + d^2 - 2ad\cos\theta)^{3/2}}$$

## (c) 作用在 $q$ 上的力

点电荷 $q$ 受到的力来自镜像电荷 $q'$ 的作用:
$$F = \frac{1}{4\pi\epsilon_0} \frac{qq'}{(d - b)^2} = -\frac{1}{4\pi\epsilon_0} \frac{q^2 a d}{(a^2 - d^2)^2}$$
负号表示吸引力, 方向指向球心.

## (d) 不同边界条件下的解

1. 固定电势 $V$:  
   解会改变. 需要在球心处添加另一个镜像电荷 $q'' = 4\pi\epsilon_0 a V$, 以保持球面电势为 $V$.

2. 带有总电荷 $Q$:  
   解也会改变. 需要在球心处添加另一个镜像电荷 $q''' = Q - q'$, 其中 $q' = -qa/d$ 是原来接地情况下的镜像电荷. 这样球面上的总电荷为 $Q$.

在这两种情况下, 球内的电势表达式需要相应修改, 但基本镜像法的思路仍然适用.

实际上加电势就是等效于在球心加电荷.



# 习题 2.3

>[!question]
>一个具有恒定线电荷密度 $\lambda$ 的直导线电荷垂直于 $x-y$ 平面，位于第一象限的 $(x_0, y_0)$ 处。相交平面 $x=0$, $y\geq 0$ 和 $y=0$, $x\geq 0$ 是保持零电势的导体边界表面。考虑第一象限中的电势、电场和面电荷以及远场下的近似为: 
>$$\Phi = \frac{4\lambda}{\pi\varepsilon_{0}} \frac{x_{0}y_{0}xy}{\rho^4}  $$

## (a) 电势表达式

由电像法显然我们有三个像, 在第二象限 $(-x_{0},y_{0})$ 处有一个 $-\lambda$ , 其余的为: $(-x_{0},-y_{0})\text{ with }\lambda$ , $(x_{0},-y_{0})\text{ with }-\lambda$ . 而我们知道无限长带电直线的势场为(不妨取原点为零势点): 
$$\Phi(x,y) = -\frac{\lambda}{4\pi\varepsilon_{0}} \ln[(x-x_{0})^2+(y-y_{0})^2] $$
所以电势表达式为: 
$$\Phi(x,y) = \frac{\lambda}{4\pi\epsilon_0} \ln\left( \frac{[(x+x_0)^2+(y-y_0)^2][(x-x_0)^2+(y+y_0)^2]}{[(x-x_0)^2+(y-y_0)^2][(x+x_0)^2+(y+y_0)^2]} \right)$$
可以验证的, 这个电势满足一切边界条件. 

## (b) 平面上的面电荷

在平面上的面电荷密度为: 
$$\sigma(x) = -\varepsilon_{0} \left. \frac{\partial \Phi}{\partial y} \right|_{y=0} = -\frac{\lambda}{\pi} y_0 \left[ \frac{1}{(x-x_0)^2+y_0^2} - \frac{1}{(x+x_0)^2+y_0^2} \right]$$
$$\sigma(y) = -\varepsilon_{0} \left. \frac{\partial \Phi}{\partial x} \right|_{x=0} = -\frac{\lambda}{\pi} x_0 \left[ \frac{1}{(y-y_0)^2+x_0^2} - \frac{1}{(y+y_0)^2+z_0^2} \right] $$
平面上每单位长度 $z$ 的总电荷为: 
$$Q_x = -\frac{2}{\pi} \lambda \tan^{-1}\left( \frac{x_0}{y_0} \right)$$
$$Q_y = -\frac{2}{\pi} \lambda \tan^{-1}\left( \frac{y_0}{x_0} \right)$$
且满足 $Q_x + Q_y = -\lambda$，与镜像法一致. 

## (c) 远场渐进行为

当远离原点 ($\rho \gg \rho_0$，其中 $\rho = \sqrt{x^2+y^2}$，$\rho_0 = \sqrt{x_0^2+y_0^2}$) 时: 
$$\rho^2 + \rho_{0}^{2} + 2x_{0}x+2y_{0}y = \rho^{2}\left( 1+\frac{2x_{0}x + 2y_{0}y}{\rho^{2}} + \left( \frac{\rho}{\rho_{0}} \right)^2 \right) $$
$$\begin{align}
\ln(\rho^{2} + \rho_{0}^{2} + 2x_{0}x+2y_{0}y) &= 2\ln \rho + \ln\left( 1+\frac{2x_{0}x + 2y_{0}y}{\rho^{2}} + \left( \frac{\rho}{\rho_{0}} \right)^2 \right) \\
&\approx 2\ln \rho + \frac{\rho_{0}^{2}}{\rho^{2}} + \frac{\rho_{0}^{4}}{\rho^{4}} + \frac{2x_{0}x+2y_{0}y}{\rho^{2}} - \frac{2x_{0}^{2}x^{2} + 2y_{0}^{2}y^{2}}{\rho^{4}} - \frac{4x_{0}y_{0}xy}{\rho^{4}}
\end{align}$$
所以将四部分都加起来就有: 
$$\Phi = \frac{4\lambda}{\pi\varepsilon_{0}} \frac{x_{0}y_{0}xy}{\rho^4} $$

# 习题 2.4

>[!question]
>一个点电荷 $q$ 被放置在距离一个带相同电荷、孤立、半径为 $R$ 的导体球中心 $d > R$ 处。
>
>(a) 在距离球面多远的距离内，点电荷被带电球吸引而不是排斥？
>
>(b) 当点电荷位于距离球面 $a = d - R$ 处，且 $a \ll R$ 时，吸引力的极限值是多少？
>
>(c) 如果球上的电荷是点电荷的两倍（或一半），但符号相同，部分 (a) 和 (b) 的结果是什么？

## (a) 吸引与排斥的临界距离

由电像法, 感应电荷等效一个距球心 $\frac{R^2}{d}$ 电荷 $-\frac{Rq}{d}$ 于是点电荷受力为: 
$$F = \frac{1}{4\pi\varepsilon_{0}} \frac{q^{2}}{d^{2}} + \frac{1}{4\pi\varepsilon_{0}} \left( -\frac{R}{d} \right) \frac{q^{2}}{\left( d - \frac{R^{2}}{d} \right)^2} = \frac{1}{4\pi\varepsilon_{0}} \frac{q^{2}}{d^{2}} \left[ \left( \frac{d}{R} \right)^{-1} \left( 1-\frac{R^{2}}{d^{2}} \right)^{-2} + 1\right] $$
当力为零时, 即为临界点. 计算得到临界距离满足: 
$$\frac{d}{R} - 1 = 0.6178$$
因此, 当点电荷距离球面的距离 $a = d - R < 0.6178 R$ 时, 点电荷被带电球吸引.

## (b) 当 $a \ll R$ 时的吸引力

当 $a \ll R$ 时，点电荷受到的吸引力为: 
$$F = -\frac{q^2}{16\pi\epsilon_0 a^2}$$
负号表示吸引力. 可见在极其接近球表面时就退化到了平面板的情况. 

## (c) 球电荷变化时的结果

如果球上的电荷 $Q$ 是点电荷 $q$ 的两倍（$Q = 2q$）或一半（$Q = q/2$）, 则临界距离改变, 但吸引力极限值不变.
- 对于 $Q = 2q$：$\frac{d}{R} - 1 = 0.4276$
- 对于 $Q = q/2$：$\frac{d}{R} - 1 = 0.8823$
对于部分 (b), 吸引力极限值相同, 即 $F = -\frac{q^2}{16\pi\epsilon_0 a^2}$.


# 习题 2.5

>[!question]
>(a) 证明将电荷 $q$ 从距离 $r > a$ 处移到无穷远对抗接地导体球的力（方程 (2.6)）所做的功为
>
>$$W = \frac{q^2 a}{8 \pi \epsilon_0 (r^2 - a^2)}$$
>
>将此结果与静电势（方程 (2.3)）和第 1.11 节的能量讨论联系起来。
>
>(b) 重复计算将电荷 $q$ 移到无穷远对抗孤立带电导体球的力（方程 (2.9)）所做的功。证明所做的功为
>
>$$W = \frac{1}{4 \pi \epsilon_0} \left[ \frac{q^2 a}{2(r^2 - a^2)} - \frac{q^2 a}{2r^2} - \frac{q Q}{r} \right]$$
>
>将此功与静电势（方程 (2.8)）和第 1.11 节的能量讨论联系起来。

## (a) 接地导体球的情况

对于接地导体球，点电荷 $q$ 在距离 $r$ 处受到的力由镜像法给出。镜像电荷位于 $b = a^2 / r$ 处，大小为 $q' = -q a / r$。点电荷受到的力为：
$$F = \frac{1}{4\pi\epsilon_0} \frac{-q^2 a r}{(r^2 - a^2)^2}$$
将电荷 $q$ 从 $r$ 移到无穷远对抗此力所做的功为：
$$W = \int_r^\infty -F  dr = \int_r^\infty \frac{1}{4\pi\epsilon_0} \frac{q^2 a r}{(r^2 - a^2)^2}  dr$$
计算积分，令 $u = r^2 - a^2$，则 $du = 2r  dr$，有：
$$W = \frac{1}{4\pi\epsilon_0} q^2 a \int_{r^2 - a^2}^\infty \frac{1}{u^2} \cdot \frac{du}{2} = \frac{1}{4\pi\epsilon_0} \frac{q^2 a}{2} \left[ -\frac{1}{u} \right]_{r^2 - a^2}^\infty = \frac{q^2 a}{8 \pi \epsilon_0 (r^2 - a^2)}$$
此结果与静电势方程 (2.3) 相关，该方程描述了点电荷在接地球附近的电势分布。在第 1.11 节的能量讨论中，系统的静电能量为 $U = \frac{1}{2} q \phi$，其中 $\phi$ 是点电荷处由于导体感应电荷产生的电势。在镜像法中，$\phi = \frac{1}{4\pi\epsilon_0} \frac{q'}{r - b}$，代入可得 $U = -\frac{1}{8\pi\epsilon_0} \frac{q^2 a}{r^2 - a^2}$。将电荷移到无穷远时，功等于电势能的变化，即 $W = -U = \frac{q^2 a}{8 \pi \epsilon_0 (r^2 - a^2)}$，与上述结果一致。

## (b) 孤立带电导体球的情况

对于孤立带电导体球（总电荷 $Q$），点电荷 $q$ 在距离 $r$ 处受到的力由镜像法给出。镜像电荷包括 $q' = -q a / r$ 位于 $b = a^2 / r$ 处，和 $q'' = Q + q a / r$ 位于球心。点电荷受到的力为：
$$F = \frac{1}{4\pi\epsilon_0} \left[ -\frac{q^2 a r}{(r^2 - a^2)^2} + \frac{q Q}{r^2} + \frac{q^2 a}{r^3} \right]$$
将电荷 $q$ 从 $r$ 移到无穷远对抗此力所做的功为：
$$W = \int_r^\infty -F  dr = \frac{1}{4\pi\epsilon_0} \int_r^\infty \left[ \frac{q^2 a r}{(r^2 - a^2)^2} - \frac{q Q}{r^2} - \frac{q^2 a}{r^3} \right] dr$$
计算积分：
- $\int_r^\infty \frac{q^2 a r}{(r^2 - a^2)^2} dr = \frac{q^2 a}{2} \frac{1}{r^2 - a^2}$
- $\int_r^\infty -\frac{q Q}{r^2} dr = -\frac{q Q}{r}$
- $\int_r^\infty -\frac{q^2 a}{r^3} dr = -\frac{q^2 a}{2 r^2}$
组合得：
$$W = \frac{1}{4\pi\epsilon_0} \left[ \frac{q^2 a}{2(r^2 - a^2)} - \frac{q Q}{r} - \frac{q^2 a}{2 r^2} \right]$$
此结果与静电势方程 (2.8) 相关，该方程描述了点电荷在孤立带电球附近的电势分布。在第 1.11 节的能量讨论中，系统的静电能量为 $U = \frac{1}{2} Q V + \frac{1}{2} q \phi$，其中 $V$ 是球的电势，$\phi$ 是点电荷处由于球产生的电势。从镜像法可得 $V = \frac{1}{4\pi\epsilon_0} \left( \frac{Q}{a} + \frac{q}{r} \right)$ 和 $\phi = \frac{1}{4\pi\epsilon_0} \left( -\frac{q a}{r^2 - a^2} + \frac{Q}{r} + \frac{q a}{r^2} \right)$。代入能量公式并计算变化，可得功 $W = U(\infty) - U(r)$，与上述结果一致。


# 习题 2.6

>[!question]
>一个孤立带电导体球外有一个点电荷 $q$ 的静电问题等价于三个电荷的问题：原始电荷和另外两个电荷，一个位于球心，另一个（"镜像电荷"）位于现在假想的球内，在连接球心和原始电荷的直线上。
>
>如果点电荷和球被两个半径分别为 $r_a$ 和 $r_b$ 的导体球取代，分别带有总电荷 $Q_a$ 和 $Q_b$，中心间距为 $d > r_a + r_b$，则等价于每个球内有一组无限多个电荷，一个在中心，另一组镜像电荷沿着连接中心的直线。可以通过迭代确定这些电荷及其位置，从第一个球中心的电荷 $q_a(1)$ 和第二个球中心的相应电荷 $q_b(1)$ 开始。电荷 $q_b(1)$ 在第一个球内有一个镜像 $q_a(2)$，反之亦然。然后第一个球内的镜像电荷在第二个球内诱导出另一个镜像，依此类推。每个球内所有电荷的总和必须缩放为等于 $Q_a$ 或 $Q_b$。
>
>球外的静电势、球之间的力等可以通过对所有电荷的贡献求和来找到。
>
>(a) 证明电荷及其位置由以下迭代关系确定：
>
>$$q_a(j) = -r_a q_b(j-1)/d_b(j-1), \quad x_a(j) = r_a^2/d_b(j-1), \quad d_a(j) = d-x_a(j)$$
>
>$$q_b(j) = -r_b q_a(j-1)/d_a(j-1), \quad x_b(j) = r_b^2/d_a(j-1), \quad d_b(j) = d-x_b(j)$$
>
>对于 $j = 2, 3, 4, \ldots$，其中 $d_a(1) = d_b(1) = d$，且 $x_a(1) = x_b(1) = 0$。
>
>(b) 通过合适的计算机程序找到镜像电荷及其位置，以及球上的电势和它们之间的力。[在计算每个球上的电势时，在不同的位置评估它：例如，在赤道平面和相对于另一个球的极点。这允许检查导体的等势性和计算的准确性。]
>
>(c) 作为一个例子，证明对于两个相同半径 $R$ 的等量带电球，当它们几乎接触时，它们之间的力是如果每个球上的所有电荷都集中在球心时得到的值的 0.6189 倍。通过数值和显式级数求和证明，两个相同导体球接触时的电容为 $C/4\pi\epsilon_0R = 1.3863 \cdots [= \ln 4]$。

## (a) 迭代关系的证明

单个球外点电荷的镜像法结果, 如果一个球外距离 $d$ 处有一个点电荷 $q$, 则球内的镜像电荷位于距离球心 $r^2/d$ 处, 电荷为 $-qr/d$ .

迭代关系是显然的, 它就是单个点电荷的成像公式: a 的第 $j$ 个像电荷 $q_{a}(j)$ 成像在 b 上得到第 $j+1$ 个像电荷 $q_{b}(j+1)$ . 最后当 $j=1$ 时就是说零级近似将导体球当作一个点电荷. 

## (b) 编程计算

程序步骤: 

1. 初始化参数：$r_a$, $r_b$, $d$, $Q_a$, $Q_b$
2. 设置迭代次数 $N$ 
3. 初始化数组存储 $q_a$, $x_a$, $q_b$, $x_b$ 
4. 使用迭代关系计算镜像电荷序列
5. 缩放电荷使每个球内的总电荷等于给定值
6. 计算球面上的电势（在赤道平面和极点）
7. 计算球之间的力

## (c) 等大相接导体球系统的电容

对于两个相同半径 $R$ 的等量带电球, 初始条件: 
$$q_{a}(1) = Q,\quad q_{b}(1) = -Q , \quad x_{a}(1) = x_{b}(1) = 0 , \quad r_{a} = r_{b} = R , \quad d=2R $$
迭代条件: 
$$\begin{align}
q_{a}(i) = -R\cdot \frac{q_{b}(i-1)}{d_{b}(i-1)} , \quad d_{a}(i) = 2R - x_{a}(i) = 2R - \frac{R^{2}}{d_{b}(i-1)} \\
q_{b}(i) = -R\cdot \frac{q_{a}(i-1)}{d_{a}(i-1)} , \quad d_{b}(i) = 2R - x_{b}(i) = 2R - \frac{R^{2}}{d_{a}(i-1)}
\end{align} $$
注意到 $q_{a}(i)=q_{b}(i),d_{a}(i)=d_{b}(i)$ 所以本质上这个迭代是单组的:
$$q_{a}(i) = -R\cdot \frac{q_{a}(i-1)}{d_{a}(i-1)} , \quad d_{a}(i) = 2R - \frac{R^{2}}{d_{a}(i-1)} $$
于是可计算得: 
$$d_{a}(n) = \frac{n+1}{n} R , \quad q_{a}(n) = \frac{2\cdot(-1)^{n+1}}{n} Q $$
所以: 
$$V = \frac{1}{4\pi\varepsilon_{0}} \sum_{i=1}^\infty \frac{q_{a}(i)}{R} $$
$$C = \frac{Q}{V} = 4\pi\varepsilon_{0}R \sum_{i=1}^\infty \frac{2(-1)^{n+1}}{n} = 4\pi\varepsilon_{0}R \cdot \ln 4 $$

至于力...我感觉还是交给计算机吧, 它是一个双重求和:
$$F = \frac{1}{4\pi\varepsilon_{0}} \sum_{i,j=1}^\infty \frac{q_{a}(i)q_{b}(j)}{[2R-x_{a}(i) - x_{b}(j)]^2} = -\frac{1}{4\pi\varepsilon_{0}} \sum_{i,j=1}^\infty \frac{q(i)q(j)}{[ d^2(i) + d^2(j) - 2R ]} $$
第二步使用了两个数组的对称性记 $q_{a}(n) = -q_{b}(n) =  q(n),d_{a}(n)=d_{b}(n)=d(n)$ 

# 习题 2.7

>[!question]
>考虑半空间 $z \geq 0$ 中的势问题，在平面 $z = 0$ 上（以及在无穷远处）有狄利克雷边界条件。
>
>(a) 写出相应的格林函数 $G(\mathbf{x}, \mathbf{x}')$。
>
>(b) 如果在平面 $z = 0$ 上，半径为 $a$、中心在原点的圆内电势为 $\Phi = V$，圆外电势为 $\Phi = 0$，求点 $P$（用柱坐标 $(\rho, \phi, z)$ 表示）处电势的积分表达式。
>
>(c) 证明沿圆的轴线 ($\rho = 0$)，电势由下式给出：
>
>$$\Phi = V \left( 1 - \frac{z}{\sqrt{a^2 + z^2}} \right)$$
>
>(d) 证明在远距离处 ($\rho^2 + z^2 \gg a^2$)，电势可以在 $(\rho^2 + z^2)^{-1}$ 的幂级数中展开，并且主导项为：
>
>$$\Phi = \frac{V a^2}{2} \frac{z}{(\rho^2 + z^2)^{3/2}} \left[ 1 - \frac{3a^2}{4(\rho^2 + z^2)} + \frac{5(3\rho^2 a^2 + a^4)}{8(\rho^2 + z^2)^2} + \cdots \right]$$
>
>验证 (c) 和 (d) 的结果在它们的共同有效范围内是一致的。

## (a) 格林函数

对于半空间 $z \geq 0$ 的狄利克雷问题, 格林函数为: 
$$G(\mathbf{x}, \mathbf{x}') = \frac{1}{4\pi} \left[ \frac{1}{|\mathbf{x} - \mathbf{x}'|} - \frac{1}{|\mathbf{x} - \mathbf{x}'_{\text{im}}|} \right]$$
其中 $\mathbf{x}' = (x', y', z')$, 镜像点为 $\mathbf{x}'_{\text{im}} = (x', y', -z')$. 在边界 $z' = 0$ 上，$G = 0$.

## (b) 电势的积分表达式

根据格林函数方法, 电势的积分表达式为:
$$\Phi(\rho, \phi, z) = \frac{V z}{2\pi} \int_{0}^{a} \rho'  d\rho' \int_{0}^{2\pi} \frac{d\phi'}{\left[ \rho^2 + \rho'^2 - 2\rho\rho'\cos(\phi - \phi') + z^2 \right]^{3/2}}$$
其中积分在圆内进行, $\rho'$ 和 $\phi'$ 是源点的柱坐标. 

## (c) 沿轴线的电势

当 $\rho = 0$ 时, 积分简化为:
$$\Phi(0, z) = \frac{V z}{2\pi} \int_{0}^{a} \rho'  d\rho' \int_{0}^{2\pi} \frac{d\phi'}{(\rho'^2 + z^2)^{3/2}} = V z \int_{0}^{a} \frac{\rho'  d\rho'}{(\rho'^2 + z^2)^{3/2}}$$
其中
$$\int_{0}^{a} \frac{\rho'  d\rho'}{(\rho'^2 + z^2)^{3/2}} = \left[ -\frac{1}{\sqrt{\rho'^2 + z^2}} \right]_{0}^{a} = \frac{1}{z} - \frac{1}{\sqrt{a^2 + z^2}}$$因此: 
$$\Phi(0, z) = V z \left( \frac{1}{z} - \frac{1}{\sqrt{a^2 + z^2}} \right) = V \left( 1 - \frac{z}{\sqrt{a^2 + z^2}} \right)$$

## (d) 远场展开

在远场 $R^2 = \rho^2 + z^2 \gg a^2$ 处, 对积分表达式进行级数展开. 首先将被积函数展开为:
$$\frac{1}{[\rho^2 + \rho'^2 - 2\rho\rho'\cos\phi' + z^2]^{3/2}} = \frac{1}{R^3} \left[ 1 - \frac{3}{2} \frac{\rho'^2 - 2\rho\rho'\cos\phi'}{R^2} + \frac{15}{8} \frac{(\rho'^2 - 2\rho\rho'\cos\phi')^2}{R^4} + \cdots \right]$$
对 $\phi'$ 积分后, 得到:
$$\Phi(\rho, z) = \frac{V z}{2\pi} \int_{0}^{a} \rho'  d\rho' \int_{0}^{2\pi} \frac{d\phi'}{R^3} \left[ 1 - \frac{3}{2} \frac{\rho'^2}{R^2} + \frac{15}{8} \frac{\rho'^4 + 4\rho^2\rho'^2\cos^2\phi'}{R^4} + \cdots \right]$$
即$$\Phi(\rho, z) = \frac{V a^2 z}{2 R^3} \left[ 1 - \frac{3a^2}{4R^2} + \frac{5(3\rho^2 a^2 + a^4)}{8R^4} + \cdots \right]$$其中 $R^2 = \rho^2 + z^2$.

## 一致性验证

在轴线 $\rho = 0$ 上, $R = z$，(d) 的结果变为: 
$$\Phi(0, z) = \frac{V a^2}{2 z^2} \left[ 1 - \frac{3a^2}{4z^2} + \frac{5a^4}{8z^4} + \cdots \right]$$
而 (c) 的结果展开为: 
$$\Phi(0, z) = V \left( 1 - \frac{z}{\sqrt{a^2 + z^2}} \right) = V \left[ \frac{a^2}{2z^2} - \frac{3a^4}{8z^4} + \cdots \right] = \frac{V a^2}{2 z^2} \left[ 1 - \frac{3a^2}{4z^2} + \cdots \right]$$
两者一致, 验证了结果的正确性.



# 习题 2.8

>[!question]
>一个二维势问题由两条平行的直线电荷定义，它们之间的距离为 $R$，具有相等相反的线电荷密度 $\lambda$ 和 $-\lambda$。
>
>(a) 通过直接构造证明等势面是一个圆柱面（横截面上是圆），并用 $R$、$\lambda$ 和 $V$ 表示圆柱轴线的坐标和半径。
>
>(b) 使用 (a) 的结果证明两个半径为 $a$ 和 $b$ 的直圆柱导体，相距 $d > a + b$，单位长度的电容 $C$ 为
>
>$$C = \frac{2\pi \epsilon_0}{\cosh^{-1} \left( \frac{d^2 - a^2 - b^2}{2ab} \right)}$$
>
>(c) 验证 $C$ 的结果在适当极限下与习题 1.7 的答案一致，并确定 $a/d$ 和 $b/d$ 幂次中的下一个非零阶修正。
>
>(d) 重复计算两个圆柱相互嵌套（$d < |b-a|$）时的单位长度电容。检查同心圆柱（$d=0$）的结果。

## (a) 等势面的构造

考虑两条线电荷, 正电荷位于 $(0,0)$, 负电荷位于 $(R,0)$. 任意点 $P = (x,y)$ 的电势为:
$$\Phi = \frac{\lambda}{2\pi\epsilon_0} \ln \frac{r_1}{r_2}$$
其中 $r_1 = \sqrt{x^2 + y^2}$，$r_2 = \sqrt{(x-R)^2 + y^2}$. 等势面满足 $\Phi = V$, 即: 
$$\ln \frac{r_1}{r_2} = \frac{2\pi\epsilon_0 V}{\lambda} \Rightarrow \frac{r_1}{r_2} = e^{2\pi\epsilon_0 V/\lambda} = K$$
其中 $K = e^{2\pi\epsilon_0 V/\lambda}$. 代入距离表达式: 
$$x^2 + y^2 = K^2 \left[ (x-R)^2 + y^2 \right]$$
$$(1-K^2)x^2 + (1-K^2)y^2 + 2K^2 R x - K^2 R^2 = 0$$
当 $K \neq 1$ 时( $V\not= 0$ ), 除以 $1-K^2$:
$$x^2 + y^2 + \frac{2K^2 R}{1-K^2} x - \frac{K^2 R^2}{1-K^2} = 0$$
$$\left( x - \frac{K^2 R}{K^2-1} \right)^2 + y^2 = \left( \frac{K R}{|K^2-1|} \right)^2$$
因此, 等势面是圆柱面, 在横截面上的圆的圆心为 $\left( \frac{K^2 R}{K^2-1}, 0 \right)$, 半径为 $\frac{K R}{|K^2-1|}$, 其中 $K = e^{2\pi\epsilon_0 V/\lambda}$.

## (b) 两个圆柱导体的电容

考虑两个圆柱导体, 半径分别为 $a$ 和 $b$, 中心距 $d > a + b$. 它们等价于两个线电荷 $\lambda$ 和 $-\lambda$ 产生的等势面. 设两个圆柱对应的参数分别为 $u_1$ 和 $u_2$, 其中 $u_1 = \frac{2\pi\epsilon_0 V_1}{\lambda}$，$u_2 = \frac{2\pi\epsilon_0 V_2}{\lambda}$. 则几何关系为:
$$a = \frac{R}{2 \sinh u_1}, \quad b = \frac{R}{2 \sinh u_2}, \quad d = \frac{R}{2} (\coth u_1 + \coth u_2)$$
电势差 $\Delta V = V_1 - V_2 = \frac{\lambda}{2\pi\epsilon_0} (u_1 + u_2)$, 电容 $C = \frac{\lambda}{\Delta V} = \frac{2\pi\epsilon_0}{u_1 + u_2}$. 令 $w = u_1 + u_2$, 从几何关系消去 $R$ 和 $u_1, u_2$ 得:
$$\cosh w = \frac{d^2 - a^2 - b^2}{2ab}$$
因此:
$$C = \frac{2\pi\epsilon_0}{\cosh^{-1} \left( \frac{d^2 - a^2 - b^2}{2ab} \right)}$$

## (c) 与习题 1.7 的对比及修正

在习题 1.7 中, 对于两根平行导线（半径相同且 $d \gg a$）, 电容为:
$$C \approx \frac{\pi\epsilon_0}{\ln(d/a)}$$
在本结果中, 设 $a = b$, 则:
$$\cosh w = \frac{d^2 - 2a^2}{2a^2} = \frac{d^2}{2a^2} - 1$$
当 $d \gg a$ 时, $\cosh w \approx \frac{d^2}{2a^2}$, 利用渐近展开 $\cosh^{-1} x \approx \ln(2x)$ 得:
$$w \approx \ln \left( \frac{d^2}{a^2} \right) = 2 \ln \left( \frac{d}{a} \right)$$
因此：
$$C \approx \frac{2\pi\epsilon_0}{2 \ln(d/a)} = \frac{\pi\epsilon_0}{\ln(d/a)}$$
与习题 1.7 一致。

下一步非零阶修正: 令 $D = d/a$, 则: 
$$\cosh w = \frac{D^2}{2} - 1$$
$$w = \ln \left( D^2 - 2 + \sqrt{(D^2-2)^2 - 1} \right) \approx 2 \ln D - \frac{2}{D^2} + O(D^{-4})$$
因此:
$$C \approx \frac{\pi\epsilon_0}{\ln D} \left( 1 + \frac{1}{D^2 \ln D} + \cdots \right)$$
修正项为 $\frac{1}{D^2 \ln D}$ 阶. 

## (d) 圆柱相互嵌套时的电容

对于两个圆柱相互嵌套（$d < |b-a|$）, 电容公式为:
$$C = \frac{2\pi\epsilon_0}{\cosh^{-1} \left( \frac{a^2 + b^2 - d^2}{2ab} \right)}$$
当 $d = 0$ 时（同心圆柱）:
$$\cosh^{-1} \left( \frac{a^2 + b^2}{2ab} \right) = \ln \left( \frac{b}{a} \right)$$
因此:
$$C = \frac{2\pi\epsilon_0}{\ln(b/a)}$$
与同心圆柱电容公式一致.


# 习题 2.10

>[!question]
>一个大型平行板电容器由两个平行导体板组成，间距为 $D$，其中一个板的内表面有一个半径为 $a$ 的小半球形凸起 ($D \gg a$)。带有凸起的导体板保持零电位，另一个导体的电位使得远离凸起时板间的电场为 $E_0$。
>
>(a) 计算平面上和凸起上任意点的面电荷密度，并草图它们随距离（或角度）的变化行为。
>
>(b) 证明凸起上的总电荷大小为 $3\pi \epsilon_0 E_0 a^2$。
>
>(c) 如果另一个导体板被一个点电荷 $q$ 取代，点电荷直接位于半球形凸起上方，距离其中心 $d$，证明凸起上感应的电荷为
>
>$$q' = -q \left[ 1 - \frac{d^2 - a^2}{d\sqrt{d^2 + a^2}} \right]$$

## (a) 面电荷密度

在凸起表面（半球面）上, 面电荷密度为: 
$$\sigma_{\text{boss}} = -3 \epsilon_0 E_0 \cos\theta$$
其中 $\theta$ 是从 $z$ 轴测量的角度. 在凸起顶部 ($\theta=0$), $\sigma_{\text{boss}} = -3 \epsilon_0 E_0$; 在凸起与平面连接处 ($\theta=\pi/2$), $\sigma_{\text{boss}} = 0$.

在平面 ($z=0$) 上, 面电荷密度为: 
$$\sigma_{\text{plane}} = -\epsilon_0 E_0 \left(1 - \frac{a^3}{r^3}\right)$$
其中 $r$ 是到原点的水平距离. 在 $r=a$ 处, $\sigma_{\text{plane}} = 0$; 当 $r \to \infty$ 时，$\sigma_{\text{plane}} \to -\epsilon_0 E_0$.

## (b) 凸起上的总电荷

凸起上的总电荷为: 
$$Q_{\text{boss}} = \int \sigma_{\text{boss}}  dA = \int_0^{2\pi} d\phi \int_0^{\pi/2} (-3 \epsilon_0 E_0 \cos\theta) a^2 \sin\theta  d\theta$$
计算得: 
$$Q_{\text{boss}} = -3 \epsilon_0 E_0 a^2 \cdot 2\pi \cdot \frac{1}{2} = -3\pi \epsilon_0 E_0 a^2$$
因此, 总电荷的大小为 $3\pi \epsilon_0 E_0 a^2$.

## (c) 点电荷引起的感应电荷

当点电荷 $q$ 位于凸起中心上方距离 $d$ 处时, 凸起上感应的电荷为: 
$$q' = -q \left[ 1 - \frac{d^2 - a^2}{d\sqrt{d^2 + a^2}} \right]$$
该结果可通过镜像法推导, 考虑点电荷在接地导体平面和半球凸起上的镜像电荷系统. 


# 习题 2.11

>[!question]
>一个线电荷，线电荷密度为 $\tau$，被放置在与导体圆柱轴平行、距离为 $R$ 的位置。圆柱半径为 $b$，保持固定电压，使得无穷远处电势为零。求：
>
>(a) 镜像电荷的大小和位置；
>(b) 任意点的电势（用极坐标表示，原点在圆柱轴，$x$ 轴从原点指向线电荷），包括远离圆柱的渐近形式；
>(c) 感应面电荷密度，并以 $\tau/2\pi b$ 为单位，绘制 $R/b = 2, 4$ 时面电荷密度随角度的函数；
>(d) 作用在线电荷上单位长度的力。

## (a) 镜像电荷的大小和位置

镜像电荷的大小为 $-\tau$, 位于从圆柱轴出发的同一射线上, 距离圆柱轴为 $a = b^2/R$. 

## (b) 电势表达式

任意点 $(\rho, \phi)$ 的电势为:
$$\Phi(\rho, \phi) = \frac{\tau}{2\pi\epsilon_0} \ln \frac{r_2}{r_1}$$
其中:
- $r_1 = \sqrt{\rho^2 + R^2 - 2\rho R \cos\phi}$ 是观察点到线电荷的距离;
- $r_2 = \sqrt{\rho^2 + a^2 - 2\rho a \cos\phi}$ 是观察点到镜像电荷的距离;
- $a = b^2/R$.

远离圆柱的渐近形式（$\rho \gg R$）:
$$\Phi(\rho, \phi) \approx \frac{\tau}{2\pi\epsilon_0} \frac{R^2 - b^2}{R\rho} \cos\phi$$

## (c) 感应面电荷密度

圆柱表面的感应面电荷密度为:
$$\sigma(\phi) = -\frac{\tau}{2\pi b} \frac{1 - u^2}{1 + u^2 - 2u \cos\phi}$$
其中 $u = b/R$.

以 $\tau/2\pi b$ 为单位, 面电荷密度为:

- 当 $R/b = 2$ ($u = 1/2$) 时:
  $$\sigma(\phi) = -\frac{3}{5 - 4\cos\phi}$$
- 当 $R/b = 4$ ($u = 1/4$) 时:
  $$\sigma(\phi) = -\frac{15}{17 - 8\cos\phi}$$


## (d) 线电荷上的力

作用在线电荷上单位长度的力为:
$$F = -\frac{\tau^2}{2\pi\epsilon_0} \frac{R}{R^2 - b^2}$$
负号表示力指向圆柱轴方向（吸引力）.


# 习题 2.12

>[!question]
>从指定在半径为 $b$ 的圆柱表面电势的二维势问题的级数解 (2.71) 出发，形式地计算系数，代入级数，并求和得到圆柱内部势的泊松积分形式：
>
>$$\Phi(\rho, \phi) = \frac{1}{2\pi} \int_0^{2\pi} \Phi(b, \phi') \frac{b^2 - \rho^2}{b^2 + \rho^2 - 2b\rho \cos(\phi' - \phi)}  d\phi'$$
>
>如果需要求圆柱与无穷远边界之间区域内的势，需要什么修改？

## 圆柱内部势的泊松积分推导

由（2.71）即极坐标系下的二维拉泊松问题, 势函数可展开为级数:
$$\Phi(\rho, \phi) = A_0 + \sum_{n=1}^{\infty} \rho^n (A_n \cos n\phi + B_n \sin n\phi)$$
在边界 $\rho = b$ 上, 势为 $\Phi(b, \phi)$, 因此系数由边界条件决定:
$$A_0 = \frac{1}{2\pi} \int_0^{2\pi} \Phi(b, \phi')  d\phi'$$
$$A_n = \frac{1}{\pi b^n} \int_0^{2\pi} \Phi(b, \phi') \cos n\phi'  d\phi'$$
$$B_n = \frac{1}{\pi b^n} \int_0^{2\pi} \Phi(b, \phi') \sin n\phi'  d\phi'$$
代入级数并交换求和与积分顺序:
$$\Phi(\rho, \phi) = \int_0^{2\pi} \Phi(b, \phi') \left[ \frac{1}{2\pi} + \frac{1}{\pi} \sum_{n=1}^{\infty} \left( \frac{\rho}{b} \right)^n \cos n(\phi' - \phi) \right] d\phi'$$
计算求和部分. 令 $r = \rho/b < 1$ 和 $\theta = \phi' - \phi$, 则: 
$$\frac{1}{2} + \sum_{n=1}^{\infty} r^n \cos n\theta = \frac{1 - r^2}{2(1 - 2r \cos\theta + r^2)}$$
因此:
$$\frac{1}{2\pi} + \frac{1}{\pi} \sum_{n=1}^{\infty} r^n \cos n\theta = \frac{1 - r^2}{2\pi (1 - 2r \cos\theta + r^2)}$$
代入 $r = \rho/b$ 和 $\theta = \phi' - \phi$, 并注意到:
$$1 - 2r \cos\theta + r^2 = \frac{b^2 + \rho^2 - 2b\rho \cos(\phi' - \phi)}{b^2}$$
$$1 - r^2 = \frac{b^2 - \rho^2}{b^2}$$
因此:
$$\frac{1 - r^2}{2\pi (1 - 2r \cos\theta + r^2)} = \frac{b^2 - \rho^2}{2\pi (b^2 + \rho^2 - 2b\rho \cos(\phi' - \phi))}$$
最终得到圆柱内部势的泊松积分:
$$\Phi(\rho, \phi) = \frac{1}{2\pi} \int_0^{2\pi} \Phi(b, \phi') \frac{b^2 - \rho^2}{b^2 + \rho^2 - 2b\rho \cos(\phi' - \phi)}  d\phi'$$

## 圆柱外部势的修改

如果需要求圆柱外部区域（$\rho > b$）的势, 且势在无穷远处为零, 则泊松积分修改为:
$$\Phi(\rho, \phi) = \frac{1}{2\pi} \int_0^{2\pi} \Phi(b, \phi') \frac{\rho^2 - b^2}{b^2 + \rho^2 - 2b\rho \cos(\phi' - \phi)}  d\phi'$$
该表达式满足拉普拉斯方程在 $\rho > b$ 的区域, 并在边界 $\rho = b$ 上等于 $\Phi(b, \phi')$. 当 $\rho \to \infty$ 时, 被积函数趋于 1, 因此 $\Phi(\rho, \phi) \to \frac{1}{2\pi} \int_0^{2\pi} \Phi(b, \phi')  d\phi'$. 为了保证势在无穷远处为零, 必须要求圆柱表面势的平均值为零, 即 $\frac{1}{2\pi} \int_0^{2\pi} \Phi(b, \phi')  d\phi' = 0$. 


# 习题 2.14

>[!question]
>一个长的空心导体圆柱，半径为 $b$，被分成四个相等的部分，交替部分保持在电位 $+V$ 和 $-V$。
>
>(a) 使用级数解 (2.71) 求解，并证明圆柱内部的电位为
>
>$$\Phi(\rho, \phi) = \frac{4V}{\pi} \sum_{n=0}^{\infty} \left( \frac{\rho}{b} \right)^{4n+2} \frac{\sin[(4n + 2)\phi]}{2n + 1}$$
>
>(b) 求和级数，并证明
>
>$$\Phi(\rho, \phi) = \frac{2V}{\pi} \tan^{-1} \left( \frac{2\rho^2 b^2 \sin 2\phi}{b^4 - \rho^4} \right)$$
>
>(c) 草图电场线和等势线。

## (a) 级数解

对于圆柱内部的电位, 拉普拉斯方程在极坐标下的通解为: 
$$\Phi(\rho, \phi) = A_0 + \sum_{n=1}^{\infty} \rho^n (A_n \cos n\phi + B_n \sin n\phi)$$
由于圆柱被分成四个交替电位的部分, 边界条件为: 
$$\Phi(b, \phi) = \begin{cases} 
+V & \text{for } 0 < \phi < \pi/2 \\
-V & \text{for } \pi/2 < \phi < \pi \\
+V & \text{for } \pi < \phi < 3\pi/2 \\
-V & \text{for } 3\pi/2 < \phi < 2\pi
\end{cases}$$
由对称性显然只有正弦项, 计算傅里叶系数:
$$\Phi(b,\phi) = \sum_{n=1}^{\infty} b^nB_{n} \sin n\phi $$
$$b^n B_{n} = \frac{1}{\pi} \int_{0}^{2\pi} \Phi(b,\phi) \sin n\phi d\phi = \frac{2V}{n\pi}\left( 1-\cos \frac{n\pi}{2} + \cos n\pi - \frac{\cos_{3}n\pi}{2} \right) $$
$$b^{n}B_{n} = \frac{8V}{\pi n} \quad \text{for } n = 4k+2$$
因此，内部电位为：
$$\Phi(\rho, \phi) = \sum_{k=0}^{\infty} B_{4k+2} \rho^{4k+2} \sin(4k+2)\phi = \frac{4V}{\pi} \sum_{n=0}^{\infty} \left( \frac{\rho}{b} \right)^{4n+2} \frac{\sin[(4n+2)\phi]}{2n+1}$$

## (b) 级数求和

考虑级数:
$$S = \sum_{n=0}^{\infty} \frac{1}{2n+1} \left( \frac{\rho}{b} \right)^{4n+2} e^{i(4n+2)\phi}$$
令 $r = \rho/b$, 则:
$$S = r^2 e^{i2\phi} \sum_{n=0}^{\infty} \frac{1}{2n+1} (r^4 e^{i4\phi})^n$$
利用反正切双曲函数的级数展开:
$$\tanh^{-1} z = \sum_{n=0}^{\infty} \frac{z^{2n+1}}{2n+1} \quad \text{for } |z| < 1$$
令 $z = r^2 e^{i2\phi}$, 则:
$$\sum_{n=0}^{\infty} \frac{1}{2n+1} (r^4 e^{i4\phi})^n = \frac{1}{r^2 e^{i2\phi}} \tanh^{-1}(r^2 e^{i2\phi})$$
$$S = \tanh^{-1}z$$
电位的级数为上述级数的虚部:
$$\Phi(\rho, \phi) = \frac{4V}{\pi} \text{Im}[S] = \frac{4V}{\pi} \mathrm{Im}[\tanh^{-1}(r^2 e^{i2\phi})]$$
$$\mathrm{Im}[\tanh^{-1}(r^2 e^{i2\phi})] = \frac{1}{2} \arg \left( \frac{1 + r^2 e^{i2\phi}}{1 - r^2 e^{i2\phi}} \right) = \frac{1}{2}\tan^{-1} \frac{2 r^2 \sin 2\phi}{1 - r^4}$$
因此:
$$\Phi(\rho, \phi) = \frac{4V}{\pi} \cdot \frac{1}{2} \tan^{-1} \frac{2 r^2 \sin 2\phi}{1 - r^4} = \frac{2V}{\pi} \tan^{-1} \frac{2 \rho^2 b^2 \sin 2\phi}{b^4 - \rho^4}$$

## (c) 电场线和等势线草图

等势线由方程 $\Phi(\rho, \phi) = \text{常数}$ 给出, 即:
$$\tan^{-1} \frac{2 \rho^2 b^2 \sin 2\phi}{b^4 - \rho^4} = \text{常数}$$
$$\frac{2 \rho^2 b^2 \sin 2\phi}{b^4 - \rho^4} = \text{常数} $$
这表示一系列曲线在圆柱内部. 电场线垂直于等势线, 从正电位段指向负电位段. 

- **等势线**：在靠近正电位段的地方, 等势线密度较高, 电位变化较快. 在圆柱中心附近, 等势线较平滑. 等势线在 $\phi = 0, \pi/2, \pi, 3\pi/2$ 方向有对称性.
- **电场线**：从正电位段发出, 终止于负电位段. 在分段边界处, 电场线密集, 电场强度较大. 电场线在圆柱内部形成闭合曲线, 与等势线正交. 

草图略


# 习题 2.15

>[!question]
>(a) 证明对于二维正方形区域 $0 \leq x \leq 1, 0 \leq y \leq 1$ 的狄利克雷边界条件, 格林函数 $G(x, y; x', y')$ 具有展开式
>
>$$G(x, y; x', y') = 2 \sum_{n=1}^{\infty} g_n(y, y') \sin(n \pi x) \sin(n \pi x')$$
>
>其中 $g_n(y, y')$ 满足
>
>$$\left( \frac{\partial^2}{\partial y'^2} - n^2 \pi^2 \right) g_n(y, y') = -4 \pi \delta(y' - y) \quad \text{和} \quad g_n(y, 0) = g_n(y, 1) = 0$$
>
>(b) 对于 $g_n(y, y')$, 在 $y' < y$ 和 $y' > y$ 两个区域中, 使用 $\sinh(n \pi y')$ 和 $\cosh(n \pi y')$ 的适当线性组合, 根据边界条件和源 delta 函数所需的斜率间断, 证明 $G$ 的显式形式为
>
>$$G(x, y; x', y')
= 8 \sum_{n=1}^{\infty} \frac{1}{n \sinh(n \pi)} \sin(n \pi x) \sin(n \pi x') \sinh(n \pi y_<) \sinh[n \pi (1 - y_>)]$$
>
>其中 $y_<(y_>)$ 是 $y$ 和 $y'$ 中较小(较大)的值.

## (a) 格林函数傅里叶展开

直接代入 $\nabla^{2}G=-4\pi\delta(\mathbf{x}-\mathbf{x}')$ : 
$$\frac{\partial^{2}G}{\partial x'^{2}} = 2\sum_{n=1}^{\infty} -n^{2}\pi^{2} g_{n}(y,y')\sin n\pi x\sin n\pi x' $$
$$\frac{\partial^{2}G}{\partial y'^{2}} = 2\sum_{n=1}^{\infty} \frac{\partial^{2}g_{n}}{\partial y'^{2}} \sin n\pi x\sin n\pi x' $$
所以
$$\nabla^{2}G = 2\sum_{n=1}^{\infty} \left( \frac{\partial^{2}}{\partial y'^{2}} - n^{2}\pi^{2} \right) g_{n}(y,y')\sin n\pi x\sin n\pi x' = -4\pi\delta(\mathbf{x}-\mathbf{x}') = -4\pi\delta(x-x')\delta(y-y') $$
而我们知道
$$\delta(x-x') = 2\sum_{n=1}^{\infty} \sin n\pi x\sin n\pi x' $$
对比一下就知道了:
$$\left( \frac{\partial^{2}}{\partial y'^{2}} - n^{2}\pi^{2} \right) g_{n}(y,y') = -4\pi\delta(y-y') $$
而边界条件是 $G=0$ 在边界上所以 $G(x,y;x',0)=G(x,y;x',1)=0$ 即 $g_{n}(y,0)=g_{n}(y,1)=0$ .

## (b) 格林函数的显式表达

当 $y\not=y'$ 时 
$$\left( \frac{\partial^{2}}{\partial y'^{2}} - n^{2}\pi^{2} \right) g_{n}(y,y') = 0 , \quad g_{n}(y,0) = g_{n}(y,1) = 0 $$
当 $y'<y$ 时可用第一个边界条件得到 $g_{n}(y,y') = A\sinh n\pi y'$ 
当 $y'>y$ 时可用第二个边界条件得到 $g_{n}(y,y') = B\sinh n\pi(1-y')$ 

对于 delta 函数所需的斜率间隔的计算, 考虑在 $y=y'$ 的邻域内积分:
$$ \int_{y+\varepsilon}^{y+\varepsilon} \frac{\partial^{2}g_{n}}{\partial y'^{2}} dy' - \int_{y+\varepsilon}^{y+\varepsilon} n^{2}\pi^{2} g_{n} dy' \to \left. \frac{\partial g_{n}}{\partial y'} \right|_{y'= y^+} - \left. \frac{\partial g_{n}}{\partial y'} \right|_{y'= y^-} = -4\pi \int_{y+\varepsilon}^{y+\varepsilon} \delta(y-y') = -4\pi $$
再加上连续性就有了:
$$g_{n}(y,y^{+}) = g_{n}(y,y^{-}) , \quad \left. \frac{\partial g_{n}}{\partial y'} \right|_{y'= y^+} - \left. \frac{\partial g_{n}}{\partial y'} \right|_{y'= y^-} = -4\pi $$
$$\begin{gather}
A\sinh n\pi y - B\sinh n\pi(1-y) = 0 \\
Bn\pi\cosh n\pi(1-y) + An\pi\cosh n\pi y=4\pi
\end{gather} $$
所以
$$A = \frac{4}{n} \frac{\sinh n\pi(1-y)}{\sinh n\pi} , \quad B = \frac{4}{n} \frac{\sinh n\pi y}{\sinh n\pi} $$
$$g_{n}(y,y') = \left\{ \begin{gather}
\frac{4}{n\sinh n\pi} \sinh n\pi y\sinh n\pi(1-y') & (y'<y) \\
\frac{4}{n\sinh n\pi} \sinh n\pi y'\sinh n\pi(1-y) & (y'>y)
\end{gather} \right. $$
于是令 $y_{<}:=\text{min}\{ y,y' \},y_{>}:=\text{max}\{ y,y' \}$ 即有
$$G(x,y;x',y') = 8 \sum_{n=1}^{\infty} \frac{1}{n \sinh(n \pi)} \sin(n \pi x) \sin(n \pi x') \sinh(n \pi y_<) \sinh[n \pi (1 - y_>)] $$


# 习题 2.16

>[!question]
>一个二维势存在于单位正方形区域（$0 \leq x \leq 1, 0 \leq y \leq 1$）上，边界由保持零电势的“表面”围成。整个正方形上有单位强度的均匀电荷密度（在 $z$ 方向上每单位长度）。使用问题 2.15 中的格林函数，证明解可以写为：
>
>$$\Phi(x, y) = \frac{4}{\pi^3 \epsilon_0} \sum_{m=0}^\infty \frac{\sin[(2m+1)\pi x]}{(2m+1)^3} \left\{ 1 - \frac{\cosh[(2m+1)\pi(y-\frac{1}{2})]}{\cosh[(2m+1)\pi/2]} \right\}$$

## 证明

由格林函数的定义:
$$\Phi(x,y) = \frac{1}{4\pi\epsilon_0} \iint G(x,y;x',y') \rho(x',y')  dx' dy'$$
其中电荷密度为均匀分布, 即 $\rho(x',y') = 1$. 从问题 2.15 中, 格林函数为:
$$G(x,y;x',y') = 8 \sum_{n=1}^{\infty} \frac{1}{n \sinh(n \pi)} \sin(n \pi x) \sin(n \pi x') \sinh(n \pi y_<) \sinh[n \pi (1 - y_>)]$$代入上式:
$$\Phi(x,y) = \frac{1}{4\pi\epsilon_0} \int_0^1 \int_0^1 8 \sum_{n=1}^{\infty} \frac{1}{n \sinh(n \pi)} \sin(n \pi x) \sin(n \pi x') \sinh(n \pi y_<) \sinh[n \pi (1 - y_>)]  dx' dy'$$
下面计算它:
$$\sum_{n=1}^{\infty} \frac{\sin n\pi x}{n\sinh n\pi} \iint_{[0,1]^{2}} \sin n\pi x'\sinh n\pi y_{<}\sinh n\pi(1-y_{>}) dx'dy' $$
其中
$$\begin{align}
I &= \int_{0}^{1} \sin n\pi x'dx' \int_{0}^{1} \sinh n\pi y_{<} \sinh n\pi(1-y_{>}) dy' \\
&= \frac{1-(-1)^{n}}{n\pi}\left(  \int_{0}^{y} \sinh n\pi y' \sinh n\pi(1-y) dy' + \int_{y}^{1} \sinh n\pi y\sinh n\pi(1-y') dy' \right) \\
&= \frac{1-(-1)^{n}}{n\pi} \left( \frac{\sinh n\pi(1-y)}{n \pi} ( \cosh n \pi y - 1 ) + \frac{\sinh n\pi y}{n \pi} ( \cosh n \pi (1 - y) - 1 ) \right) \\
&= \frac{1-(-1)^{n}}{n\pi} \frac{\sinh(n \pi) - \sinh[n \pi (1 - y)] - \sinh(n \pi y)}{n \pi} 
\end{align} $$
当 $n$ 为偶数时 $I=0$ , 当 $n$ 为奇数时
$$I = \frac{2}{n^{2}\pi^{2}}[ \sinh n\pi - \sinh n\pi(1-y) - \sinh n\pi y ] $$
代入 $\Phi(x,y)$ :
$$\Phi(x,y) = \frac{2}{\pi\epsilon_0} \sum_{n=1}^{\infty} \frac{\sin(n \pi x)}{n \sinh(n \pi)} I$$
仅 $n$ 为奇数时贡献，令 $n = 2m+1$ 得通项为:
$$\begin{align}
&\quad \frac{2}{\pi\varepsilon_{0}} \frac{2}{(2m+1)^3\pi^2} \frac{\sin(2m+1)\pi x}{\sinh(2m+1)\pi}[ \sinh(2m+1)\pi - \sinh(2m+1)\pi y - \sinh(2m+1)\pi(1-y) ]  \\
&= \frac{4\sin(2m+1)\pi}{(2m+1)^{3}\pi^{3}\varepsilon_{0}} \left[  1- \frac{\sinh(2m+1)\pi y - \sinh(2m+1)\pi(1-y)}{\sinh(2m+1)\pi}  \right] \\
&= \frac{4\sin(2m+1)\pi}{(2m+1)^{3}\pi^{3}\varepsilon_{0}} \left[  1- \frac{\cosh(2m+1)\pi \left( y-\frac{1}{2} \right)}{\cosh \frac{(2m+1)\pi}{2}}  \right]
\end{align}$$
所以:
$$\Phi(x,y) = \frac{4}{\pi^3 \epsilon_0} \sum_{m=0}^\infty \frac{\sin[(2m+1)\pi x]}{(2m+1)^3} \left\{ 1 - \frac{\cosh[(2m+1)\pi(y-\frac{1}{2})]}{\cosh[(2m+1)\pi/2]} \right\}$$
证毕. 


# 习题 2.17

>[!question]
>(a) 通过对 $1/R$ 在 $(z' - z)$ 上从 $\pm Z$ 积分（其中 $Z$ 取得非常大）来构造二维静电学的自由空间格林函数 $G(x, y; x', y')$。证明除了一个非本质的常数外，格林函数可以交替写成
>$$G(x, y; x', y') = -\ln[(x - x')^2 + (y - y')^2] = -\ln[\rho^2 + \rho'^2 - 2\rho\rho'\cos(\phi - \phi')]$$
>
>(b) 通过极坐标下的变量分离，显式证明格林函数可以表示为方位角的傅里叶级数，
>$$G = \frac{1}{2\pi} \sum_{-\infty}^{\infty} e^{im(\phi - \phi')} g_m(\rho, \rho')$$
>其中径向格林函数满足
>$$\frac{1}{\rho'} \frac{\partial}{\partial \rho'} \left( \rho' \frac{\partial g_m}{\partial \rho'} \right) - \frac{m^2}{\rho'^2} g_m = -4\pi \frac{\delta(\rho - \rho')}{\rho}$$
>注意，对于固定的 $\rho$，$g_m(\rho, \rho')$ 在 $\rho' < \rho$ 和 $\rho' > \rho$ 时是齐次径向方程 (2.68) 的解的不同线性组合，且在 $\rho' = \rho$ 处斜率的间断由源 delta 函数决定。
>
>(c) 完成解并证明自由空间格林函数具有展开式
>$$G(\rho, \phi; \rho', \phi') = -\ln(\rho_>^2) + 2 \sum_{m=1}^{\infty} \frac{1}{m} \left( \frac{\rho_<}{\rho_>} \right)^m \cdot \cos[m(\phi - \phi')]$$
>其中 $\rho_<(\rho_>)$ 是 $\rho$ 和 $\rho'$ 中较小（较大）的值。

## (a) 格林函数的构造

自由空间格林函数为 $G_3(\mathbf{x}, \mathbf{x}') = \frac{1}{4\pi |\mathbf{x} - \mathbf{x}'|}$. 对于二维问题, 通过对 $z'$ 从 $-Z$ 到 $Z$ 积分得到二维格林函数:
$$G_2(x,y; x',y') = \int_{-Z}^{Z} \frac{1}{4\pi \sqrt{(x-x')^2 + (y-y')^2 + (z-z')^2}} dz'$$
不妨设 $z = 0$, 并令 $d = \sqrt{(x-x')^2 + (y-y')^2}$, 则:
$$G_2 = \frac{1}{4\pi} \int_{-Z}^{Z} \frac{dz'}{\sqrt{d^2 + z'^2}} = \frac{1}{4\pi} \left[ \ln \left( z' + \sqrt{d^2 + z'^2} \right) \right]_{-Z}^{Z} = \frac{1}{2\pi} \ln \frac{Z + \sqrt{ d^{2} + Z^{2} }}{d}$$
当 $Z$ 很大时, 计算得:
$$G_{2} = \frac{1}{2\pi} \left( \ln 2Z + \mathcal O\left( \frac{1}{Z} \right) - \ln d \right) \to -\ln d $$
这里忽略掉了有关 $Z$ 的项, 并且忽略系数, 因此二维格林函数可定义为：
$$G(x,y; x',y') = -\ln[(x-x')^2 + (y-y')^2] = -\ln[\rho^2 + \rho'^2 - 2\rho\rho'\cos(\phi - \phi')]$$

## (b) 傅里叶级数表示

在极坐标下, 格林函数 $G(\rho, \phi; \rho', \phi')$ 可展开为傅里叶级数:
$$G = \frac{1}{2\pi} \sum_{m=-\infty}^{\infty} e^{im(\phi - \phi')} g_m(\rho, \rho')$$
代入泊松方程
$$\nabla^{2} G = \frac{1}{2\pi} \frac{1}{\rho'} \frac{\partial}{\partial \rho'}\left( \rho' \frac{\partial (e^{im(\phi-\phi')}g_{m})}{\partial \rho'} \right) - \frac{1}{2\pi} \frac{1}{\rho'^{2}} \frac{\partial^{2}(e^{im(\phi-\phi')}g_{m})}{\partial \phi'^{2}} = -4\pi\delta(\mathbf{x}-\mathbf{x}') = -\frac{4\pi\delta(\rho-\rho')}{\rho} $$
$$\frac{1}{\rho'} \frac{\partial}{\partial \rho'} \left( \rho' \frac{\partial g_m}{\partial \rho'} \right) - \frac{m^2}{\rho'^2} g_m = -4\pi \frac{\delta(\rho - \rho')}{\rho}$$
对于 $\rho' \neq \rho$，$g_m$ 满足齐次方程, 解为 $g_m \sim \rho'^{|m|}$ 或 $\rho'^{-|m|}$. 在 $\rho' = \rho$ 处, 函数值连续而导数有间断, 满足跳跃条件:
$$\int_{U(\rho)} \frac{1}{\rho'} \frac{\partial}{\partial \rho'}\left( \rho'\frac{\partial g_{m}}{\partial \rho'} \right) d\rho' - \int_{U(\rho)} \frac{m^{2}}{\rho'^{2}} g_{m} d\rho' \to \left. \frac{\partial g_m}{\partial \rho'} \right|_{\rho'=\rho^+} - \left. \frac{\partial g_m}{\partial \rho'} \right|_{\rho'=\rho^-} =  -\frac{4\pi}{\rho} $$
$$\left. \frac{\partial g_m}{\partial \rho'} \right|_{\rho'=\rho^+} - \left. \frac{\partial g_m}{\partial \rho'} \right|_{\rho'=\rho^-} = -\frac{4\pi}{\rho}$$

## (c) 格林函数的展开

从部分 (a) 的结果, 格林函数为:
$$G = -\ln[\rho^2 + \rho'^2 - 2\rho\rho'\cos(\phi - \phi')]$$
令 $\rho_<$ 和 $\rho_>$ 分别为 $\rho$ 和 $\rho'$ 中的较小值和较大值, 则:
$$G = -\ln \rho_>^2 - \ln \left[ 1 - 2 \frac{\rho_<}{\rho_>} \cos(\phi - \phi') + \left( \frac{\rho_<}{\rho_>} \right)^2 \right]$$
利用幂级数展开:
$$
\begin{align}
\ln(1-2a\cos \theta + a^{2}) &= \ln(1-ae^{i\theta}) + \ln(1-ae^{-i\theta})  \\
&= -\sum_{k=1}^{\infty} \frac{(ae^{i\theta})^{k}}{k} - \sum_{k=1}^{\infty} \frac{(ae^{-i\theta})^{k}}{k} , \quad\text{when } |a|<1 \\
&=- \sum_{m=1}^{\infty} \frac{a^{m}}{m}(e^{im\theta}+e^{-im\theta}) \\
&= - \sum_{m=1}^{\infty} \frac{a^{m}}{m}\cos m\theta
\end{align}
$$
其中 $a = \frac{\rho_<}{\rho_>}<1$ , $\theta = \phi - \phi'$, 得:
$$G = -\ln \rho_>^2 + 2 \sum_{m=1}^{\infty} \frac{1}{m} \left( \frac{\rho_<}{\rho_>} \right)^m \cos[m(\phi - \phi')]$$
此即所求展开式.


# 习题 2.18

>[!question]
>(a) 通过寻找问题 2.17 部分 (b) 中径向方程的适当解，找到半径为 $b$ 的圆柱内部狄利克雷问题的格林函数 [$g_m(\rho, \rho' = b) = 0$。见 (1.40)]。首先找到类似于问题 2.17 自由空间格林函数的级数展开。然后证明它可以写成闭合形式：
>$$G = \ln \left[ \frac{\rho^2 \rho'^2 + b^4 - 2\rho \rho'b^2 \cos (\phi - \phi')}{b^2 (\rho^2 + \rho'^2 - 2\rho \rho' \cos (\phi - \phi'))} \right]$$
>或
>$$G = \ln \left[ \frac{(b^2 - \rho^2)(b^2 - \rho'^2) + b^2 |\rho - \rho'|^2}{b^2 |\rho - \rho'|^2} \right]$$
>
>(b) 证明拉普拉斯方程的解，在圆柱上给定电势 $\Phi(b, \phi)$，可以表示为问题 2.12 的泊松积分。
>
>(c) 对于外部问题 ($b < \rho < \infty$)，格林函数的傅里叶展开和闭合形式需要什么修改？[注意外部格林函数并不严格正确，因为它不在 $\rho$ 或 $\rho' \to \infty$ 时消失。对于电势随 $\rho \to \infty$ 足够快衰减的情况，使用它不会产生错误。]

## (a) 格林函数的级数展开和闭合形式

对于圆柱内部狄利克雷问题, 格林函数满足 $\nabla^2 G = -4\pi \delta(\mathbf{x} - \mathbf{x}')$ 且在 $\rho = b$ 时 $G = 0$. 格林函数可展开为傅里叶级数:
$$G(\rho, \phi; \rho', \phi') = \frac{1}{2\pi} \sum_{m=-\infty}^{\infty} e^{im(\phi - \phi')} g_m(\rho, \rho')$$
其中径向函数 $g_m(\rho, \rho')$ 满足:
$$\frac{1}{\rho'} \frac{\partial}{\partial \rho'} \left( \rho' \frac{\partial g_m}{\partial \rho'} \right) - \frac{m^2}{\rho'^2} g_m = -4\pi \frac{\delta(\rho - \rho')}{\rho}$$
且边界条件 $g_m(\rho, b) = 0$. 通过求解径向方程, 得到:

- 对于 $m = 0$ : $g_0(\rho, \rho') = 4\pi \ln \left( \frac{b}{\rho_>} \right)$
- 对于 $m \neq 0$ : $g_m(\rho, \rho') = \frac{2\pi}{m} \left[ \left( \frac{\rho_<}{\rho_>} \right)^m - \left( \frac{\rho \rho'}{b^2} \right)^m \right]$

其中 $\rho_< = \min(\rho, \rho')$, $\rho_> = \max(\rho, \rho')$. 代入傅里叶级数并求和, 得到格林函数的级数展开:
$$G(\rho, \phi; \rho', \phi') = 2 \ln \left( \frac{b}{\rho_>} \right) + 2 \sum_{m=1}^{\infty} \frac{1}{m} \left[ \left( \frac{\rho_<}{\rho_>} \right)^m - \left( \frac{\rho \rho'}{b^2} \right)^m \right] \cos[m(\phi - \phi')]$$
下求该级数的和函数, 考虑级数(这次从另一个角度推导)
$$\sum_{m=1}^{\infty} \frac{a^{m}}{m}\cos m\theta = \mathrm{Re}\sum_{m=1}^{\infty} \frac{(ae^{i\theta})^{m}}{m} = \mathrm{Re}(-\ln(1-z)) = -\ln|1-z| = -\ln(1-2a\cos \theta + a^{2}) $$
分别令 $z=\frac{\rho_{<}}{\rho_{>}}e^{i\theta} , \frac{\rho \rho'}{b^{2}}e^{i\theta} , \theta=\phi-\phi'$ 可得:
$$G = \ln \left[ \frac{\rho^2 \rho'^2 + b^4 - 2\rho \rho'b^2 \cos (\phi - \phi')}{b^2 (\rho^2 + \rho'^2 - 2\rho \rho' \cos (\phi - \phi'))} \right]$$
或等价地:
$$G = \ln \left[ \frac{(b^2 - \rho^2)(b^2 - \rho'^2) + b^2 |\rho - \rho'|^2}{b^2 |\rho - \rho'|^2} \right]$$

## (b) 拉普拉斯方程的解与泊松积分

利用格林函数，拉普拉斯方程在圆柱内部的解可表示为:
$$\Phi(\rho, \phi) = \frac{1}{4\pi} \oint_{\text{边界}} \Phi(b, \phi') \frac{\partial G}{\partial n'} dl'$$
其中 $dl' = b d\phi'$, 且 $\frac{\partial G}{\partial n'} = -\frac{\partial G}{\partial \rho'}$ 在 $\rho' = b$ 处. 代入后可得:
$$\Phi(\rho, \phi) = \frac{1}{2\pi} \int_0^{2\pi} \Phi(b, \phi') \frac{b^2 - \rho^2}{b^2 + \rho^2 - 2b\rho \cos(\phi' - \phi)} d\phi'$$
这正是问题 2.12 中的泊松积分形式.

## (c) 外部问题的修改

对于外部问题 ($b < \rho < \infty$), 格林函数需满足在 $\rho = b$ 时 $G = 0$ 且在 $\rho \to \infty$ 时 $G \to 0$. 傅里叶展开中的径向函数 $g_m(\rho, \rho')$ 需修改为:

- 对于 $m = 0$ : $g_0(\rho, \rho') = 4\pi \ln \left( \frac{\rho_<}{b} \right)$
- 对于 $m \neq 0$ : $g_m(\rho, \rho') = \frac{2\pi}{m} \left[ \left( \frac{\rho_<}{\rho_>} \right)^m - \left( \frac{b^2}{\rho \rho'} \right)^m \right]$

类似的格林函数为:
$$G = \ln \left[ \frac{\rho^2 \rho'^2 + b^4 - 2\rho \rho'b^2 \cos (\phi - \phi')}{b^2 (\rho^2 + \rho'^2 - 2\rho \rho' \cos (\phi - \phi'))} \right]$$



# 习题 2.19

>[!question]
>证明对于环形区域 $b \leq \rho \leq c$（同心圆柱）的狄利克雷边界条件，二维格林函数具有展开式：
>
>$$G = \frac{2\ln(\rho_{<} / b)\ln(c / \rho_{>})}{\ln(c / b)} + \sum_{m=1}^\infty \frac{\cos[m(\phi - \phi')]}{m[1 - (b/c)^{2m}]} \left[ \left( \frac{\rho_<}{\rho_>} \right)^m - \left( \frac{b^2}{\rho_< \rho_>} \right)^m \right] \left[ \left( \frac{\rho_>}{c} \right)^{2m} - 1 \right] $$
>
>其中 $\rho_<$ 和 $\rho_>$ 分别是 $\rho$ 和 $\rho'$ 中的较小值和较大值。

## 解答

对于圆柱内部狄利克雷问题, 格林函数满足 $\nabla^2 G = -4\pi \delta(\mathbf{x} - \mathbf{x}')$ 且在 $\rho = b$ 时 $G = 0$. 格林函数可展开为傅里叶级数:
$$G(\rho, \phi; \rho', \phi') = \frac{1}{2\pi} \sum_{m=-\infty}^{\infty} e^{im(\phi - \phi')} g_m(\rho, \rho')$$
其中径向函数 $g_m(\rho, \rho')$ 满足:
$$\frac{1}{\rho'} \frac{\partial}{\partial \rho'} \left( \rho' \frac{\partial g_m}{\partial \rho'} \right) - \frac{m^2}{\rho'^2} g_m = -4\pi \frac{\delta(\rho - \rho')}{\rho}$$
现在边界条件是 $g_{m}(\rho,b) = g_{m}(\rho,c) = 0$ 

对于 $\rho \neq \rho'$ 通解是 $g_{m}\sim \rho^m$ 和 $g_{m}\sim \rho^{-m}$ 当 $m=0$ 时 $g_{0}\sim \ln \rho + C$ . 区域划分为 $\rho<\rho'$ 和 $\rho>\rho'$ 连接条件为:
$$g_{m}(\rho,\rho^{+})=g_{m}(\rho,\rho^{-}) , \quad \left. \frac{\partial g_{m}}{\partial \rho'} \right|_{\rho'=\rho^{+}} - \left. \frac{\partial g_{m}}{\partial \rho'} \right|_{\rho'=\rho^{-}} = -\frac{4\pi}{\rho} $$
开算, 当 $m=0$ 时设
$$g_{0}(\rho,\rho') = \left\{ \begin{gather}
A_{1}\ln \rho' + B_{1} & (\rho'<\rho) \\
A_{2}\ln \rho' + B_{2} & (\rho'>\rho)
\end{gather} \right. $$
$$\left\{ \begin{gather}
A_{1} \ln b+B_{1} = A_{2}\ln c+B_{2}=0 \\
A_{1}\ln \rho + B_{1} = A_{2}\ln \rho +B_{2} \\
\frac{A_{2}}{\rho} - \frac{A_{1}}{\rho} = -\frac{4\pi}{\rho}
\end{gather} \right. $$
$$g_{0}(\rho,\rho') = \left\{ \begin{gather}
\frac{4\pi \ln(\rho' / b)\ln(\rho / c)}{\ln(c / b)} & (\rho'<\rho) \\
\frac{4\pi \ln(\rho / b)\ln(\rho' / c)}{\ln(c / b)} & (\rho'>\rho)
\end{gather} \right. = 4\pi \cdot \frac{\ln(\rho_{<} / b)\ln(c / \rho_{>})}{\ln(c / b)} $$
当 $m\neq 0$ 时设
$$g_{m}(\rho,\rho') = \left\{ \begin{gather}
A_{1}\rho'^{m} + B_{1}\rho'^{-m} & (\rho'<\rho) \\
A_{2}\rho'^{m} + B_{2}\rho'^{-m}  & (\rho'>\rho)
\end{gather} \right. $$
$$\left\{ \begin{gather}
A_{1}b^{m} + B_{1}b^{-m}  = A_{2}c^{m} + B_{2}c^{-m} = 0 \\
A_{1}\rho^{m} + B_{1}\rho^{-m} = A_{2}\rho^{m} +B_{2}\rho^{-m} \\
mA_{2}\rho^{m-1} - mA_{1}\rho^{m-1} - mB_{2}\rho^{-m-1} + mB_{1}\rho^{-m-1} = -\frac{4\pi}{\rho}
\end{gather} \right.  $$
$$
 g_{m}(\rho,\rho') = \frac{1}{1 - (b / c)^{2m}} \frac{1}{m} \left\{ \begin{gather}
\left( \left( \frac{\rho'}{\rho} \right)^{m} - \left( \frac{b^{2}}{\rho \rho'} \right)^{m} \right)\left(  \left( \frac{\rho}{c} \right)^{2m} - 1  \right)  &  (\rho'<\rho) \\
\left( \left( \frac{\rho}{\rho'} \right)^{m} - \left( \frac{b^{2}}{\rho \rho'} \right)^{m} \right)\left(  \left( \frac{\rho'}{c} \right)^{2m} - 1  \right)  &  (\rho'<\rho)
\end{gather} \right.
$$
即
$$g_{m}(\rho,\rho') = \frac{1}{m[1 - (b/c)^{2m}]} \left[ \left( \frac{\rho_<}{\rho_>} \right)^m - \left( \frac{b^2}{\rho_< \rho_>} \right)^m \right] \left[ \left( \frac{\rho_>}{c} \right)^{2m} - 1 \right] $$
于是
$$\sum_{m=1}^{\infty} (g_{m}e^{im\theta} + g_{-m}e^{-im\theta}) = \sum_{m=1}^{\infty} \frac{\cos m\theta}{m[1 - (b/c)^{2m}]} \left[ \left( \frac{\rho_<}{\rho_>} \right)^m - \left( \frac{b^2}{\rho_< \rho_>} \right)^m \right] \left[ \left( \frac{\rho_>}{c} \right)^{2m} - 1 \right] $$
最后组合起来:
$$ G = \frac{2\ln(\rho_{<} / b)\ln(c / \rho_{>})}{\ln(c / b)} + \sum_{m=1}^\infty \frac{\cos[m(\phi - \phi')]}{m[1 - (b/c)^{2m}]} \left[ \left( \frac{\rho_<}{\rho_>} \right)^m - \left( \frac{b^2}{\rho_< \rho_>} \right)^m \right] \left[ \left( \frac{\rho_>}{c} \right)^{2m} - 1 \right] $$


# 习题 2.20

>[!question]
>二维电四极聚焦场用于粒子加速器，可以通过一组四个对称放置的线电荷建模，线电荷密度为 $\pm \lambda$，如左图所示（右图显示电场线）。
>![[Pasted image 20251117234425.png]]
>电荷密度在二维中可以表示为：
>
>$$\sigma(\rho, \phi) = \frac{\lambda}{a} \sum_{n=0}^{3} (-1)^n \delta(\rho - a) \delta(\phi - n\pi/2)$$
>
>(a) 使用问题 2.17c 中的格林函数展开，证明静电势为：
>
>$$\Phi(\rho, \phi) = \frac{\lambda}{\pi \epsilon_0} \sum_{k=0}^{\infty} \frac{1}{2k+1} \left( \frac{\rho_<}{\rho_>} \right)^{4k+2} \cos[(4k+2) \phi]$$
>
>(b) 将部分 (a) 的解与复函数的实部联系起来：
>
>$$w(z) = \frac{2\lambda}{4\pi \epsilon_0} \ln \left[ \frac{(z-ia)(z+ia)}{(z-a)(z+a)} \right]$$
>
>其中 $z = x + iy = \rho e^{i\phi}$。评论与问题 2.3 的连接。
>
>(c) 找到原点附近笛卡尔坐标系中电场的分量表达式，用 $x$ 和 $y$ 表示。保留展开中的 $k = 0$ 和 $k = 1$ 项。对于 $y = 0$，$k = 1$（$2^6$-极）贡献对 $E_x$ 的相对大小与 $k = 0$（$2^2$-极或四极）项相比是多少？

## (a) 静电势的级数展开

$$\sigma(\rho, \phi) = \frac{\lambda}{a} \sum_{n=0}^{3} (-1)^n \delta(\rho - a) \delta(\phi - n\pi/2)$$
$$G(\rho, \phi; \rho', \phi') = -\ln(\rho_>^2) + 2 \sum_{m=1}^{\infty} \frac{1}{m} \left( \frac{\rho_<}{\rho_>} \right)^m \cos[m(\phi - \phi')]$$
$$\Phi(\rho, \phi) = \int G(\rho, \phi; \rho', \phi') \sigma(\rho', \phi')  \rho' d\rho' d\phi' = \lambda \sum_{n=0}^{3} (-1)^n G(\rho, \phi; a, n\pi/2)$$
计算求和:
$$\sum_{n=0}^{3} (-1)^n \cos[m(\phi - n\pi/2)] = 
\begin{cases}
4\cos(m\phi) &  m=4k+2 \\
0 & \text{other}
\end{cases}$$
因此, 电势为:
$$\Phi(\rho, \phi) = \frac{\lambda}{\pi \epsilon_0} \sum_{k=0}^{\infty} \frac{1}{2k+1} \left( \frac{\rho_<}{\rho_>} \right)^{4k+2} \cos[(4k+2) \phi]$$
其中 $\rho_< = \min(\rho, a)$ , $\rho_> = \max(\rho, a)$.

## (b) 与复函数的联系

考虑:
$$w(z) = \frac{2\lambda}{4\pi \epsilon_0} \ln \left[ \frac{(z-ia)(z+ia)}{(z-a)(z+a)} \right] = \frac{\lambda}{2\pi\epsilon_0} \ln \left( \frac{z^2+a^2}{z^2-a^2} \right)$$
对于 $|z| < a$, 展开得:
$$w(z) = \frac{\lambda}{2\pi\epsilon_0} \left[ i\pi + 2 \sum_{k=0}^{\infty} \frac{1}{2k+1} \left( \frac{z}{a} \right)^{4k+2} \right]$$
实部为:
$$\mathrm{Re}~ w(z) = \frac{\lambda}{\pi\epsilon_0} \sum_{k=0}^{\infty} \frac{1}{2k+1} \left( \frac{\rho}{a} \right)^{4k+2} \cos[(4k+2)\phi]$$
这与部分 (a) 中对于 $\rho < a$ 的电势一致.

与问题 2.3 的连接: 问题 2.3 涉及第一象限中的线电荷和导体平面, 使用镜像法. 这里四极对称性类似于在四个象限中使用镜像法. 

## (c) 电场分量及比较

对于 $\rho < a$, 电势为:
$$\Phi(\rho, \phi) = \frac{\lambda}{\pi \epsilon_0} \left[ \left( \frac{\rho}{a} \right)^{2} \cos(2\phi) + \frac{1}{3} \left( \frac{\rho}{a} \right)^{6} \cos(6\phi) + \ldots \right]$$
在笛卡尔坐标中, 使用 $x = \rho\cos\phi$ , $y = \rho\sin\phi$, 有:
$$\cos(2\phi) = \frac{x^2 - y^2}{\rho^2}, \quad \cos(6\phi) = \frac{x^6 - 15x^4y^2 + 15x^2y^4 - y^6}{\rho^6}$$
$$\Phi(x,y) = \frac{\lambda}{\pi \epsilon_0} \left[ \frac{x^2 - y^2}{a^2} + \frac{1}{3a^6} (x^6 - 15x^4y^2 + 15x^2y^4 - y^6) + \ldots \right]$$
电场分量为:
$$E_x = -\frac{\partial \Phi}{\partial x} = -\frac{\lambda}{\pi \epsilon_0} \left[ \frac{2x}{a^2} + \frac{1}{a^6} (2x^5 - 20x^3y^2 + 10x y^4) + \ldots \right]$$
$$E_y = -\frac{\partial \Phi}{\partial y} = -\frac{\lambda}{\pi \epsilon_0} \left[ -\frac{2y}{a^2} + \frac{1}{a^6} (-10x^4y + 20x^2y^3 - 2y^5) + \ldots \right]$$
对于 $y=0$:
$$E_x = -\frac{\lambda}{\pi \epsilon_0} \left[ \frac{2x}{a^2} + \frac{2x^5}{a^6} + \ldots \right]$$
$k=0$（四极）项为 $-\frac{2\lambda}{\pi \epsilon_0} \frac{x}{a^2}$ , $k=1$（$2^6$-极）项为 $-\frac{2\lambda}{\pi \epsilon_0} \frac{x^5}{a^6}$. 相对大小为:
$$\frac{|E_x^{(k=1)}|}{|E_x^{(k=0)}|} = \frac{x^4}{a^4}$$

因此，当 $x \ll a$ 时, 高阶项可忽略.

# 习题 2.21

>[!question]
>使用柯西定理推导泊松积分解。柯西定理指出，如果 $F(z)$ 在由闭合曲线 $C$ 围成的区域 $R$ 内解析，那么  
>$$\frac{1}{2\pi i} \oint_C \frac{F(z')}{z' - z} dz' = \begin{cases} F(z) &  z \in R \\ 0 &  z \not\in R\end{cases}$$  
>您可能希望添加一个与镜像点相关的积分（该积分为零）到圆内点的积分中。

## 推导过程

设 $F(z)$ 在单位圆内解析, 且在边界上连续, 其实部 $u(z) = \mathrm{Re} F(z)$ 在边界上给定为 $u(e^{i\phi})$. 目标是找到单位圆内一点 $z = re^{i\theta}$（其中 $0 \leq r < 1$）处的 $u(z)$ 它得表示为：
$$u(z) = \frac{1}{2\pi} \int_0^{2\pi} u(e^{i\phi}) \frac{1 - r^2}{1 - 2r \cos(\theta - \phi) + r^2} d\phi $$

从柯西定理, 对于圆内点 $z$, 有: 
$$
F(z) = \frac{1}{2\pi i} \oint_{|z'|=1} \frac{F(z')}{z' - z} dz' = \frac{1}{2\pi i} \int_{0}^{2\pi} \frac{F(e^{i\phi})}{e^{i\phi}-re^{i\theta}} ie^{i\phi} d\phi = \frac{1}{2\pi} \int_{0}^{2\pi} \frac{F(e^{i\phi})}{1-re^{i(\theta-\phi)}} d\phi
$$
通过取共轭有
$$\tilde{F}(z) = \frac{1}{2\pi} \int_{0}^{2\pi} \frac{\tilde{F}(e^{i\phi})}{1-re^{-i(\theta-\phi)}} d\phi $$
于是
$$u(z) = \frac{F(z) + \tilde{F}(z)}{2} = \frac{1}{4\pi} \int_{0}^{2\pi} \frac{2u(e^{i\phi}) - r[F(e^{i\phi})e^{-i(\theta-\phi)} + \tilde{F}(e^{i\phi})e^{i(\theta-\phi)}]}{1-2r\cos(\theta-\phi) + r^{2}} d\phi $$
显然我们要想办法将 $F(e^{i\phi})e^{-i(\theta-\phi)} + \tilde{F}(e^{i\phi})e^{i(\theta-\phi)}$ 给化成 $ru(e^{ i\phi })$ 


现在考虑镜像点 $\frac{1}{\bar{z}} = \frac{1}{r} e^{i\theta}$, 该点在单位圆外. 根据柯西定理类似的有:
$$
0 = \frac{1}{2\pi i} \oint_{|z'|=1} \frac{{\tilde{F}(z')}}{z' - \frac{1}{\bar{z}}} dz' = \frac{1}{2\pi} \int_{0}^{2\pi} \frac{\tilde{F}(e^{i\phi})}{1 - \frac{1}{r} e^{i(\theta-\phi)}} d\phi = \frac{1}{2\pi} \int_{0}^{2\pi} \frac{ -\tilde{F}(e^{i\phi}) re^{-i(\theta-\phi)} }{ 1 - re^{-i(\theta-\phi)}} d\phi
$$
所以
$$\int_{0}^{2\pi} \frac{\tilde{F}(e^{i\phi}) e^{-i(\theta-\phi)}}{1-re^{-i(\theta-\phi)}} d\phi = 0 $$
于是
$$\int_{0}^{2\pi} F(e^{i\phi}) e^{i(\theta-\phi)} \frac{1 - re^{ -i(\theta-\phi) }}{1-2r\cos(\theta-\phi) + r^{2}} d\phi = 0  $$
$$ \int_{0}^{2\pi} \frac{F(e^{i\phi})e^{i(\theta-\phi)}}{1-2r\cos(\theta-\phi)+r^{2}}d\phi = \int_{0}^{2\pi} \frac{rF(e^{i\phi})}{1-2r\cos(\theta-\phi) + r^{2}} d\phi $$
取共轭可以得到
$$ \int_{0}^{2\pi} \frac{\tilde{F}(e^{i\phi})e^{-i(\theta-\phi)}}{1-2r\cos(\theta-\phi)+r^{2}}d\phi = \int_{0}^{2\pi} \frac{r\tilde{F}(e^{i\phi})}{1-2r\cos(\theta-\phi) + r^{2}} d\phi  $$
于是 $u(z)$ 积分表达中的相关项化为
$$\begin{align}
\int_{0}^{2\pi} \frac{r[F(e^{i\phi})e^{-i(\theta-\phi)} + \tilde{F}(e^{i\phi})e^{i(\theta-\phi)}]}{1-2r\cos(\theta-\phi)+r^{2}} d\phi &= \int_{0}^{2\pi} \frac{r^{2} [F(e^{i\phi})+\tilde{F}(e^{i\phi})]}{1-2r\cos(\theta-\phi) + r^{2}} d\phi \\ \\
&= \int_{0}^{2\pi} \frac{2r^{2}u(e^{i\phi})}{1-2r\cos(\theta-\phi) + r^{2}} d\phi 
\end{align}$$
所以
$$u(z) = \frac{1}{2\pi} \int_0^{2\pi} u(e^{i\phi}) \frac{1 - r^2}{1 - 2r \cos(\theta - \phi) + r^2} d\phi$$
这就是泊松积分公式. 


# 习题 2.22

>[!question]
>(a) 对于带相反电荷的导电半球壳，中间有微小间隙，如图2.8所示，证明在 $z$ 轴上的内部电势（$r < a$）为
>
>$$\Phi_{\text{in}}(z) = V \frac{a}{z} \left[ 1 - \frac{(a^2 - z^2)}{a\sqrt{a^2 + z^2}} \right]$$
>
>求 $z$ 的幂级数展开的前几项，并证明它们与(2.27)式在适当替换下一致。
>
>(b) 从部分 (a) 和 (2.22) 式的结果，证明在正 $z$ 轴上的径向电场为
>
>$$E_r(z) = \frac{Va^2}{(z^2 + a^2)^{3/2}} \left( 3 + \frac{a^2}{z^2} \right)$$
>
>对于 $z > a$，以及
>
>$$E_r(z) = -\frac{V}{a} \left[ \frac{3 + (a/z)^2}{(1 + (z/a)^2)^{3/2}} - \frac{a^2}{z^2} \right]$$
>
>对于 $|z| < a$。证明第二种形式在原点处是良定义的，值为 $E_r(0) = -3V/2a$。证明在 $z = a$（内部北极）处，值为 $-(\sqrt{2} - 1)V/a$。证明在外部北极处的径向电场值为 $\sqrt{2}  V/a$。
>
>(c) 绘制导电半球壳内部和外部的电场线，并指示方向。绘制从 $z = -2a$ 到 $z = +2a$ 的 $z$ 轴上的径向电场图。

## (a) 内部电势及级数展开

计算方法同在球外
$$\Phi_{\text{in}}(z) = V \frac{a}{z} \left[ 1 - \frac{(a^2 - z^2)}{a\sqrt{a^2 + z^2}} \right]$$
展开 $\frac{1}{\sqrt{a^2+z^2}}$ 为幂级数:
$$\frac{1}{\sqrt{a^2+z^2}} = \frac{1}{a} \left( 1 - \frac{1}{2} \frac{z^2}{a^2} + \frac{3}{8} \frac{z^4}{a^4} - \cdots \right)$$
代入并化简得
$$\Phi_{\text{in}}(z) = \frac{3V}{2a} z - \frac{7V}{8a^3} z^3 + \cdots$$
做替换 $\cos \theta = \frac{z}{a}$ 即可与(2.27)相符

## (b) 径向电场

对于 $z > a$, 径向电场为:
$$E_r(z) = \frac{Va^2}{(z^2 + a^2)^{3/2}} \left( 3 + \frac{a^2}{z^2} \right)$$
对于 $|z| < a$, 径向电场为:
$$E_r(z) = -\frac{V}{a} \left[ \frac{3 + (a/z)^2}{(1 + (z/a)^2)^{3/2}} - \frac{a^2}{z^2} \right]$$
在原点处, 令 $z \to 0$, 展开得:
$$E_r(0) = -\frac{3V}{2a}$$
在 $z = a$ 处（内部北极）, 代入得:
$$E_r(a) = -(\sqrt{2} - 1)\frac{V}{a}$$
在 $z = a$ 处（外部北极）, 代入得:
$$E_r(a) = \sqrt{2} \frac{V}{a}$$

## (c) 电场线及径向电场图

略


# 习题 2.23

>[!question]
>一个空心立方体具有由六个平面定义的导电壁： $x = 0, y = 0, z = 0$ 和 $x = a, y = a, z = a$。壁 $z = 0$ 和 $z = a$ 保持恒定电势 $V$。其他四个壁的电势为零。
>
>(a) 求立方体内任意点处的电势 $\Phi(x, y, z)$。
>
>(b) 数值计算立方体中心处的电势，精确到三位有效数字。需要保留级数中的多少项才能达到此精度？将数值结果与壁上的电势平均值进行比较。参见问题 2.28。
>
>(c) 求表面 $z = a$ 上的面电荷密度。

## (a) 电势的级数表达式

分离变量法
$$\Phi(x,y,z) = X(x)Y(y)Z(z) $$
$$\left\{ \begin{gather}
\frac{1}{X} \frac{d^{2}X}{dx^{2}} = -\alpha^{2} \\
\frac{1}{Y} \frac{d^{2}Y}{dy^{2}} = -\beta^{2} \\
\frac{1}{Z} \frac{d^{2}Z}{dz^{2}} = \gamma^{2} = \alpha^{2} + \beta^{2}
\end{gather} \right.$$
$$\left\{ \begin{gather}
X = A_{1}e^{ i\alpha x } + A_{2}e^{ -i\alpha x } \\
Y = B_{1}e^{ i\beta y } + B_{2}e^{ -i\beta y } \\
Z = C_{1}e^{ \gamma z } + C_{2}e^{ -\gamma z }
\end{gather} \right. $$
代入边界条件知
$$\left\{ \begin{gather}
X = A\sin \alpha x \\
Y=B\sin \beta y \\
Z=C\cosh \gamma \left( z-\frac{a}{2} \right)
\end{gather} \right. $$
且参数满足
$$\alpha_{n} = \frac{n\pi}{a},\quad \beta_{m}=\frac{m\pi}{a} , \quad \gamma_{mn} = \frac{\pi}{a} \sqrt{ n^{2} + m^{2} } $$
故
$$\Phi(x,y,z) = \sum_{m,n=1}^{\infty} A_{mn}\sin \frac{n\pi x}{a}\sin \frac{m\pi y}{a}\cosh \frac{\sqrt{ n^{2} + m^{2} }\pi\left( z-\frac{a}{2} \right)}{a} $$
代入 $z=a$ 得
$$V = \sum_{m,n=1}^{\infty} A_{nm} \sin \frac{n\pi x}{a}\sin \frac{m\pi y}{a}\cosh \frac{\sqrt{ n^{2} + m^{2} }\pi}{2} $$
$$A_{nm} = \frac{4}{a^{2} \cosh \frac{\sqrt{ n^{2} + m^{2} }\pi}{2}} \iint_{[0,a]^{2}} V\sin \frac{n\pi x}{a} \sin \frac{m\pi y}{a} dxdy = \frac{4(1-(-1)^{n})(1-(-1)^{m})}{\pi^{2}nm\cosh \frac{\sqrt{ n^{2} + m^{2} }\pi}{2}} $$
当且仅当 $m,n$ 为奇数时 $A_{nm}$ 非零于是
$$\Phi = \sum_{k,l=1}^{\infty} \frac{16}{\pi^{2}} \frac{1}{mn} \frac{\cosh \frac{\sqrt{ n^{2} + m^{2} }\pi\left( z-\frac{a}{2} \right)}{a}}{\cosh \frac{\sqrt{ m^{2} + n^{2} }\pi}{2}} \sin \frac{n\pi x}{a}\sin \frac{m\pi y}{a} $$
其中 $m=2k+1,n=2l+1$ ,

## (b) 数值计算

取到 $k,l=3$ 即可满足精度, 计算结果约为
$$\Phi\left( \frac{a}{2} , \frac{a}{2} , \frac{a}{2} \right) = 0.1667 V $$

## (c) 面电荷密度

$$\sigma(x,y) = -\varepsilon_{0}\left. \frac{\partial^{2}\Phi}{\partial z^{2}} \right|_{z=a} = -\sum_{k,l=1}^{\infty} \frac{16\varepsilon_{0}}{\pi a} \frac{\sqrt{ m^{2} + n^{2} }}{mn} \frac{\sinh \frac{\sqrt{ n^{2} + m^{2} }\pi\left( z-\frac{a}{2} \right)}{a}}{\cosh \frac{\sqrt{ m^{2} + n^{2} }\pi}{2}} \sin \frac{n\pi x}{a}\sin \frac{m\pi y}{a} $$
其中 $m=2k+1,n=2l+1$ .



# 习题 2.24

>[!question]
>在如图2.12所示的二维区域中，对于在 $\phi = 0$ 和 $\phi = \beta$ 处的狄利克雷边界条件，合适的角函数是 $\Phi(\phi) = A_m \sin(m\pi\phi/\beta)$。证明这些函数的完备性关系是
>
>$$\delta(\phi - \phi') = \frac{2}{\beta} \sum_{m=1}^\infty \sin(m\pi\phi/\beta) \sin(m\pi\phi'/\beta)$$
>
>对于 $0 < \phi, \phi' < \beta$

## 证明

考虑在区间 $[0, \beta]$ 上满足狄利克雷边界条件的函数空间. 函数集 $\left\{ \sin\left(\frac{m\pi\phi}{\beta}\right) \right\}_{m=1}^\infty$ 构成一组完备正交基, 于是对于任意在 $[0, \beta]$ 上满足狄利克雷边界条件的函数 $f(\phi)$，可以展开为傅里叶正弦级数:
$$f(\phi) = \sum_{m=1}^\infty A_m \sin\left(\frac{m\pi\phi}{\beta}\right)$$
其中:
$$A_m = \frac{2}{\beta} \int_0^\beta f(\phi') \sin\left(\frac{m\pi\phi'}{\beta}\right) d\phi'$$
将系数表达式代入展开式:
$$f(\phi) = \frac{2}{\beta} \sum_{m=1}^\infty \left[ \int_0^\beta f(\phi') \sin\left(\frac{m\pi\phi'}{\beta}\right) d\phi' \right] \sin\left(\frac{m\pi\phi}{\beta}\right)$$
交换积分与求和次序:
$$f(\phi) = \int_0^\beta f(\phi') \left[ \frac{2}{\beta} \sum_{m=1}^\infty \sin\left(\frac{m\pi\phi}{\beta}\right) \sin\left(\frac{m\pi\phi'}{\beta}\right) \right] d\phi'$$
由于 $f(\phi)$ 是任意函数, 比较狄拉克 $\delta$ 函数的定义:
$$f(\phi) = \int_0^\beta f(\phi') \delta(\phi - \phi') d\phi'$$
得到完备性关系:
$$\delta(\phi - \phi') = \frac{2}{\beta} \sum_{m=1}^\infty \sin\left(\frac{m\pi\phi}{\beta}\right) \sin\left(\frac{m\pi\phi'}{\beta}\right)$$
证毕.


# 习题 2.25

>[!question]
>两个电势为零的导电平面沿 $z$ 轴相交，它们之间的夹角为 $\beta$，如图2.12所示。一个平行于 $z$ 轴的单位线电荷位于平面之间的位置 $(\rho', \phi')$。
>
>(a) 证明平面之间空间中的电势乘以 $(4\pi\epsilon_0)$，即Dirichlet Green函数 $G(\rho, \phi; \rho', \phi')$，由以下无穷级数给出：
>
>$$G(\rho, \phi; \rho', \phi') = 4 \sum_{m=1}^\infty \frac{1}{m} \rho_<^{m\pi/\beta} \rho_>^{-m\pi/\beta} \sin(m\pi\phi/\beta) \sin(m\pi\phi'/\beta)$$
>
>(b) 通过复变函数技术或其他方法，证明该级数可以求和得到闭合形式：
>
>$$G(\rho, \phi; \rho', \phi') = \ln \left\{ \frac{\rho^{2\pi/\beta} + \rho'^{2\pi/\beta} - 2(\rho\rho')^{\pi/\beta}\cos[\pi(\phi + \phi')/\beta]}{\rho^{2\pi/\beta} + \rho'^{2\pi/\beta} - 2(\rho\rho')^{\pi/\beta}\cos[\pi(\phi - \phi')/\beta]} \right\}$$
>
>(c) 验证当 $\beta = \pi$ 和 $\beta = \pi/2$ 时，你能得到熟悉的结果。

## (a) 级数解

格林函数的泊松方程和边界条件为
$$\nabla^{2}G = -4\pi\delta(\mathbf{r}-\mathbf{r}') = -\frac{4\pi\delta(\rho-\rho')\delta(\phi-\phi')}{\rho} $$
$$G(\rho,0,\rho',\phi') = G(\rho,\beta,\rho',\phi') = 0 $$
分离变量法, 设 $G = R(\rho,\rho')\Theta(\phi,\phi')$ 则
$$\frac{\partial^{2}\Theta}{\partial\phi^{2}} + \lambda\Theta = 0 , \quad \Theta(0) = \Theta(\beta)=0 $$
于是 $\Theta_n(\phi,\phi') = A(\phi')\sin\frac{n\pi\phi}{\beta}$ , $\lambda_n = \left(\frac{n\pi}{\beta}\right)^2$ 由对称性 $\Theta(\phi,\phi') = \sin \frac{n\pi \phi}{\beta}\sin \frac{n\pi \phi'}{\beta}$ 于是径向方程为
$$\frac{\partial}{\partial\rho'}\left( \rho'\frac{\partial R}{\partial\rho'} \right) - \frac{(n\pi / \beta)^{2}}{\rho'}R = -8\pi \delta(\rho-\rho') $$
通解为 $R=A\rho'^{n}+B\rho'^{-n}$ 当 $n=0$ 时不用考虑因为 $\Theta_{0}=0$ 由连续性和导数跳跃条件
$$R(\rho,\rho^{+})=R(\rho,\rho^{-}) , \quad \left.\frac{\partial R}{\partial \rho'}\right|_{\rho'=\rho^{+}} - \left.\frac{\partial R}{\partial \rho'}\right|_{\rho'=\rho^{-}} = -\frac{4\pi\delta(\rho-\rho')}{\rho} $$
于是可以解得
$$R_{n}(\rho,\rho') = \left\{ \begin{gather}
\frac{4}{n}  \left( \frac{\rho}{\rho'} \right)^{n\pi/\beta} & (\rho<\rho') \\
\frac{4}{n}  \left( \frac{\rho'}{\rho} \right)^{n\pi/\beta} & (\rho'<\rho)
\end{gather}\right. = \frac{1}{m} \rho_<^{m\pi/\beta} \rho_>^{-m\pi/\beta} $$
于是
$$G(\rho, \phi; \rho', \phi') = 4 \sum_{m=1}^\infty \frac{1}{m} \rho_<^{m\pi/\beta} \rho_>^{-m\pi/\beta} \sin(m\pi\phi/\beta) \sin(m\pi\phi'/\beta)$$

## (b) 级数的闭合形式

记
$$z= \left( \frac{\rho_{<}}{\rho_{>}} \right)^{\pi/\beta} $$
以及
$$\sin \frac{m\pi \phi}{\beta} \sin \frac{m\pi \phi'}{\beta} = \frac{1}{2}\left[  \cos \frac{m\pi(\phi-\phi')}{\beta} - \cos \frac{m\pi(\phi+\phi')}{\beta}  \right] $$
$$\sum_{m=1}^{\infty} \frac{z^{m}}{m}\cos m\alpha = -\frac{1}{2}\ln(1-2z\cos \alpha + z^{2}) $$
所以
$$G = \ln\left(  \frac{1-2z\cos \frac{\pi(\phi-\phi')}{\beta} + z^{2}}{1-2z\cos \frac{\pi(\phi+\phi')}{\beta} + z^{2}}  \right) $$
即
$$G(\rho, \phi; \rho', \phi') = \ln \left\{ \frac{\rho^{2\pi/\beta} + \rho'^{2\pi/\beta} - 2(\rho\rho')^{\pi/\beta}\cos[\pi(\phi + \phi')/\beta]}{\rho^{2\pi/\beta} + \rho'^{2\pi/\beta} - 2(\rho\rho')^{\pi/\beta}\cos[\pi(\phi - \phi')/\beta]} \right\} $$

## (c) 特殊情况

### $\beta=\pi$ 

此时
$$G = \ln⁡\left( \frac{\rho^{2}+\rho'^{2} - 2\rho \rho'\cos(\phi-\phi')}{\rho^{2}+\rho'^{2}-2\rho \rho'\cos(\phi-\phi')} \right) $$
此与镜像法所得结果一致

### $\beta=\frac{\pi}{2}$

此时
$$G = \ln \left(  \frac{\rho^{4} + \rho'^{4} - 2\rho^{2}\rho'^{2}\cos 2(\phi-\phi')}{\rho^{4} + \rho'^{4} - 2\rho^{2}\rho'^{2}\cos 2(\phi+\phi')}  \right) $$
此与直角边上的导线的电像法所得结果一致



# 习题 2.26

>[!question]
>二维区域 $\rho \geq a$，$0 \leq \phi \leq \beta$ 由位于 $\phi = 0$、$\rho = a$ 和 $\phi = \beta$ 的导电表面围成，这些表面保持零电势，如图中所示。在大的 $\rho$ 处，电势由某个固定电势的电荷和/或导体配置决定。
>![[Pasted image 20251118213953.png]]
>(a) 写出对于有限 $\rho$ 满足边界条件的电势 $\Phi(\rho, \phi)$ 的一个解。
>
>(b) 仅保留最低阶非零项，计算电场分量 $E_\rho$ 和 $E_\phi$ 以及三个边界表面上的面电荷密度 $\sigma(\rho, 0)$、$\sigma(\rho, \beta)$ 和 $\sigma(a, \phi)$。
>
>(c) 考虑 $\beta = \pi$（一个平面上有一个半径为 $a$ 的半圆柱体）。证明在远离半圆柱体处，部分 (b) 的最低阶项给出一个垂直于平面的均匀电场。画出半圆柱体上及其附近的电荷密度示意图。对于远离平面的固定电场强度，证明半圆柱体上的总电荷（实际上是 $z$ 方向每单位长度的电荷）是不存在半圆柱体时宽度为 $2a$ 的条带上的电荷的两倍。证明额外部分来自附近平面区域，因此无论半圆柱体是否存在，宽度远大于 $a$ 的条带上的总电荷是相同的。

## (a) 电势解

边界条件和泊松方程是:
$$\frac{1}{\rho} \frac{\partial}{\partial \rho}\left( \rho \frac{\partial \Phi}{\partial \rho} \right) + \frac{1}{\rho^{2}} \frac{\partial^{2}\Phi}{\partial \phi^{2}} = 0 $$
$$\Phi(\rho,0) = \Phi(\rho,\beta) = \Phi(a,\phi)=0 $$
分离变量设 $\Phi = R(\rho)\sin \frac{n\pi \phi}{\beta}$ 
$$\rho \frac{d}{d\rho}\left(\rho \frac{d R}{d\rho} \right) - \left( \frac{n\pi}{\beta} \right)^{2}R = 0 $$
$$R_{n} = A_{n} \left[ \left( \frac{\rho}{a} \right)^{n\pi/\beta} - \left( \frac{\rho}{a} \right)^{-n\pi/\beta} \right] $$
$$\Phi(\rho,\phi) = \sum_{n=1}^{\infty} A_{n}\left[ \left( \frac{\rho}{a} \right)^{n\pi/\beta} - \left( \frac{\rho}{a} \right)^{-n\pi/\beta} \right]\sin \frac{n\pi \phi}{\beta} $$

## (b) 场强和电荷面密度

在最低阶下记 $k=\frac{\pi}{\beta}$ 使用公式 $\mathbf{E}=-\nabla \Phi , \sigma=-\mathbf{E}\cdot \mathbf{n}$ 计算.
$$\Phi = A \left[  \left( \frac{\rho}{a} \right)^{k} - \left( \frac{\rho}{a} \right)^{-k} \right]\sin k\phi $$$$E_\rho = -\dfrac{\partial \Phi}{\partial \rho} = -\frac{A}{\rho}\left[  \left( \frac{\rho}{a} \right)^{k} - \left( \frac{\rho}{a} \right)^{-k} \right]\sin k\phi $$
$$E_{\phi} = -\dfrac{1}{\rho} \dfrac{\partial \Phi}{\partial \phi} = -\frac{A}{\rho}\left[  \left( \frac{\rho}{a} \right)^{k} - \left( \frac{\rho}{a} \right)^{-k} \right]\cos k\phi  $$
$$\sigma(\rho, 0) = \epsilon_0 A \frac{k}{\rho} \left[ \left( \frac{\rho}{a} \right)^k - \left( \frac{\rho}{a} \right)^{-k} \right]$$
$$\sigma(\rho, \beta) = \epsilon_0 A \frac{k}{\rho} \left[ \left( \frac{\rho}{a} \right)^k - \left( \frac{\rho}{a} \right)^{-k} \right] $$
$$\sigma(a, \phi) = -2 \epsilon_0 A \frac{k}{a} \sin(k\phi) $$
## (c) $\beta=\pi$ 

此时最低阶的项下 $k=1$ 
$$\Phi(\rho, \phi) \approx A \left( \frac{\rho}{a} - \frac{a}{\rho} \right) \sin\phi$$
在远处 $\Phi\approx \frac{A}{a}\rho \sin \phi=\frac{A}{a}z$ 对应均匀电场.

草图略

总电荷计算:
- 半圆柱上的总电荷（每单位长度）:
  $$
  Q_{\text{cyl}} = \int_0^\pi \sigma(a, \phi) a  d\phi = -4 \epsilon_0 A_1
  $$
- 没有半圆柱时，宽度为 $2a$ 的条带上的电荷:
  $$
  Q_{\text{strip}} = \sigma_0 \cdot 2a = -2 \epsilon_0 A_1
  $$
  其中 $\sigma_0 = -\epsilon_0 \dfrac{A_1}{a}$ 是均匀电场下的面电荷密度. 因此 $Q_{\text{cyl}} = 2 Q_{\text{strip}}$. 

# 习题 2.27

>[!question]
>考虑问题 2.26 中的二维楔形区域，其中 $\beta = 2\pi$。这对应于在正 $x$ 轴上从 $x = a$ 到无穷远的半无限薄导体片，其边缘固定了一个半径为 $a$ 的导体圆柱。
>
>(a) 使用最低阶解画出圆柱上以及薄片顶部和底部的面电荷密度示意图。
>
>(b) 计算圆柱上的总电荷，并将其与薄片靠近圆柱处的电荷不足总量进行比较，即假设远离圆柱处的电荷密度相同，比较 $a$ 有限时与 $a = 0$ 时的电荷总量差异。

## (a) 面电荷密度

使用最低阶解 $m=1$, 其中 $\beta = 2\pi$ ,电势为:
$$
\Phi(\rho, \phi) = A_1 \left[ \left( \frac{\rho}{a} \right)^{1/2} - \left( \frac{\rho}{a} \right)^{-1/2} \right] \sin\left( \frac{\phi}{2} \right)
$$
- **圆柱表面$(\rho = a)$**:
  面电荷密度为:
  $$
  \sigma_{\text{cyl}}(\phi) = \varepsilon_0 \frac{A_1}{a} \sin\left( \frac{\phi}{2} \right)
  $$

- **薄片表面（$\phi = 0$ 和 $\phi = 2\pi$）**:  
  面电荷密度为:
$$
  \sigma_{\text{sheet}}(\rho) = \varepsilon_0 \frac{A_1}{\rho} \left[ \left( \frac{\rho}{a} \right)^{1/2} - \left( \frac{\rho}{a} \right)^{-1/2} \right]
  $$

## (b) 电荷计算与比较

- 圆柱上的总电荷:
  $$
  Q_{\text{cyl}} = \int_0^{2\pi} \sigma_{\text{cyl}}(\phi) \, a \, d\phi = \varepsilon_0 A_1 \int_0^{2\pi} \sin\left( \frac{\phi}{2} \right) d\phi = 4 \varepsilon_0 A_1
  $$
- 薄片上的电荷不足:
  假设远处电荷密度相同，当 $a$ 有限时，薄片上的电荷与 $a = 0$ 时相比, 其差值为:
  $$
  \Delta Q_{\text{sheet}} = -Q_{\text{cyl}} = -4 \varepsilon_0 A_1
  $$
  即薄片上的电荷不足等于圆柱上电荷的负值, 两者大小相等.


# 习题 2.28

>[!question]
>一个封闭体积由导电表面围成，这些表面是一个正多面体的各个面（$n = 4, 6, 8, 12, 20$）。这些表面处于不同的电位 $V_i$，$i = 1, 2, \dots, n$。用你能想到的最简单方法证明，在多面体中心的电位是 $n$ 个面电位的平均值。这个问题与问题 2.23b 相关，并且与问题 1.10 的结果有有趣的相似性。

#### 证明

平均电位为:
$$
\bar{V} = \frac{1}{n} \sum_{i=1}^{n} V_i
$$
记 $V_i = \bar{V} + \delta V_i$ , 其中 $\delta V_i$ 为偏差, 则 $\sum_{i=1}^{n} \delta V_i = 0$ .

由叠加原理, 电位 $\Phi$ 可分解为两部分:
$$
\Phi = \Phi_1 + \Phi_2
$$
其中：
- $\Phi_1$ 满足所有面电位为 $\bar{V}$ 的边界条件;
- $\Phi_2$ 满足面电位为 $\delta V_i$ 的边界条件.

对于 $\Phi_1$, 由于所有面电位相同, 由对称性, 体积内每点的电位均为常数 $\bar{V}$, 特别地:
$$
\Phi_1(\text{中心}) = \bar{V}
$$
对于 $\Phi_2$, 边界条件满足 $\sum \delta V_i = 0$. 正多面体具有高度对称性, 其对称群在面上是传递的. 考虑对称群对边界条件的作用, 在中心点的电位 $\Phi_2(\text{中心})$ 必须是边界条件的线性函数, 且在该群作用下不变. 唯一的不变线性函数是平均值的常数倍, 但 $\sum \delta V_i = 0$, 故平均值零, 因此:
$$
\Phi_2(\text{中心}) = 0
$$
综上, 中心点电位为:
$$
\Phi(\text{中心}) = \Phi_1(\text{中心}) + \Phi_2(\text{中心}) = \bar{V}
$$
即多面体中心的电位是各面电位的平均值.



# 习题 2.29

>[!question]
>对于在二维方格 lattice 上的 Galerkin 方法，其中 lattice spacing 为 $h$，验证局部“金字塔”基函数的关系 (2.81)。基函数定义为 $\phi_{ij}(x, y) = (1 - |x|/h)(1 - |y|/h)$，其中 $|x| < h$，$|y| < h$，且 $x$ 和 $y$ 是从站点 $(i, j)$ 测量的。特别验证以下关系：
>
>1. $\int dx \int dy  \phi_{i,j}(x, y) = h^2$
>2. $\int dx \int dy  \nabla \phi_{i,j} \cdot \nabla \phi_{i,j} = \frac{8}{3}$
>3. $\int dx \int dy  \nabla \phi_{i+1,j} \cdot \nabla \phi_{i,j} = -\frac{1}{3}$
>4. $\int dx \int dy  \nabla \phi_{i,j+1} \cdot \nabla \phi_{i,j} = -\frac{1}{3}$
>5. $\int dx \int dy  \nabla \phi_{i+1,j+1} \cdot \nabla \phi_{i,j} = -\frac{1}{3}$

## 验证过程

基函数 $\phi_{ij}(x, y) = f(x) f(y)$，其中 $f(u) = 1 - |u|/h$ 对于 $|u| < h$，否则为 0。积分范围均为 $|x| < h$ 和 $|y| < h$，除非另有说明。

**1. 验证 $\int \int \phi_{i,j}(x, y)  dx  dy = h^2$**

由于 $\phi_{ij}(x, y) = f(x) f(y)$，且积分可分离：
$$
\int_{-h}^{h} f(x)  dx = 2 \int_{0}^{h} \left(1 - \frac{x}{h}\right)  dx = 2 \left[ x - \frac{x^2}{2h} \right]_{0}^{h} = 2 \left( h - \frac{h}{2} \right) = h
$$
同理，$\int_{-h}^{h} f(y)  dy = h$。因此：
$$
\int dx \int dy  \phi_{i,j}(x, y) = h \cdot h = h^2
$$



**2. 验证 $\int \int \nabla \phi_{i,j} \cdot \nabla \phi_{i,j}  dx  dy = \frac{8}{3}$**

首先计算梯度：
$$
\nabla \phi_{ij} = \left( \frac{\partial \phi_{ij}}{\partial x}, \frac{\partial \phi_{ij}}{\partial y} \right) = \left( f'(x) f(y), f(x) f'(y) \right)
$$
其中 $f'(u) = -\frac{\operatorname{sign}(u)}{h}$ 对于 $u \neq 0$。于是：
$$
\nabla \phi_{ij} \cdot \nabla \phi_{ij} = [f'(x) f(y)]^2 + [f(x) f'(y)]^2
$$
由于对称性：
$$
\int \int [f'(x) f(y)]^2  dx  dy = \int f'(x)^2  dx \int f(y)^2  dy
$$
计算：
$$
\int_{-h}^{h} f(u)^2  du = 2 \int_{0}^{h} \left(1 - \frac{u}{h}\right)^2  du = 2 \int_{0}^{h} \left(1 - \frac{2u}{h} + \frac{u^2}{h^2}\right)  du = 2 \left[ u - \frac{u^2}{h} + \frac{u^3}{3h^2} \right]_{0}^{h} = 2 \left( h - h + \frac{h}{3} \right) = \frac{2h}{3}
$$
$$
\int_{-h}^{h} f'(u)^2  du = \int_{-h}^{0} \left(\frac{1}{h}\right)^2  du + \int_{0}^{h} \left(-\frac{1}{h}\right)^2  du = \frac{h}{h^2} + \frac{h}{h^2} = \frac{2}{h}
$$
因此：
$$
\int \int [f'(x) f(y)]^2  dx  dy = \frac{2}{h} \cdot \frac{2h}{3} = \frac{4}{3}
$$
同理：
$$
\int \int [f(x) f'(y)]^2  dx  dy = \frac{4}{3}
$$
所以：
$$
\int \int \nabla \phi_{i,j} \cdot \nabla \phi_{i,j}  dx  dy = \frac{4}{3} + \frac{4}{3} = \frac{8}{3}
$$



**3. 验证 $\int \int \nabla \phi_{i+1,j} \cdot \nabla \phi_{i,j}  dx  dy = -\frac{1}{3}$**

设 $\phi_{00}$ 位于 $(0,0)$，$\phi_{10}$ 位于 $(h,0)$。重叠区域为 $x \in [0, h]$，$y \in [-h, h]$。计算：
$$
\nabla \phi_{10} \cdot \nabla \phi_{00} = f'(x-h) f'(x) [f(y)]^2 + f(x-h) f(x) [f'(y)]^2
$$
在 $x \in [0, h]$ 时：
- $f(x) = 1 - \frac{x}{h}$，$f'(x) = -\frac{1}{h}$
- $f(x-h) = \frac{x}{h}$，$f'(x-h) = \frac{1}{h}$
代入得：
$$
\nabla \phi_{10} \cdot \nabla \phi_{00} = -\frac{1}{h^2} [f(y)]^2 + \frac{x}{h} \left(1 - \frac{x}{h}\right) [f'(y)]^2
$$
积分：
$$
\int_{0}^{h} \int_{-h}^{h} -\frac{1}{h^2} [f(y)]^2  dy  dx = -\frac{1}{h^2} \cdot \frac{2h}{3} \cdot h = -\frac{2}{3}
$$
$$
\int_{0}^{h} \int_{-h}^{h} \frac{x}{h} \left(1 - \frac{x}{h}\right) [f'(y)]^2  dy  dx = \int_{0}^{h} \frac{x}{h} \left(1 - \frac{x}{h}\right)  dx \cdot \int_{-h}^{h} [f'(y)]^2  dy = \frac{h}{6} \cdot \frac{2}{h} = \frac{1}{3}
$$
总和：
$$
-\frac{2}{3} + \frac{1}{3} = -\frac{1}{3}
$$



**4. 验证 $\int \int \nabla \phi_{i,j+1} \cdot \nabla \phi_{i,j}  dx  dy = -\frac{1}{3}$**

由对称性，此积分与第三项相同，结果为 $-\frac{1}{3}$。



**5. 验证 $\int \int \nabla \phi_{i+1,j+1} \cdot \nabla \phi_{i,j}  dx  dy = -\frac{1}{3}$**

设 $\phi_{00}$ 位于 $(0,0)$，$\phi_{11}$ 位于 $(h,h)$。重叠区域为 $x \in [0, h]$，$y \in [0, h]$。计算：
$$
\nabla \phi_{11} \cdot \nabla \phi_{00} = f'(x-h) f'(x) f(y-h) f(y) + f(x-h) f(x) f'(y-h) f'(y)
$$
在 $x \in [0, h]$，$y \in [0, h]$ 时：
- $f(x) = 1 - \frac{x}{h}$，$f'(x) = -\frac{1}{h}$
- $f(x-h) = \frac{x}{h}$，$f'(x-h) = \frac{1}{h}$
- $f(y) = 1 - \frac{y}{h}$，$f'(y) = -\frac{1}{h}$
- $f(y-h) = \frac{y}{h}$，$f'(y-h) = \frac{1}{h}$
代入得：
$$
\nabla \phi_{11} \cdot \nabla \phi_{00} = -\frac{1}{h^2} \left[ \frac{y}{h} \left(1 - \frac{y}{h}\right) + \frac{x}{h} \left(1 - \frac{x}{h}\right) \right]
$$
积分：
$$
\int_{0}^{h} \int_{0}^{h} -\frac{1}{h^2} \left[ \frac{y}{h} \left(1 - \frac{y}{h}\right) + \frac{x}{h} \left(1 - \frac{x}{h}\right) \right]  dx  dy = -\frac{1}{h^2} \left[ 2 \cdot \frac{h^2}{6} \right] = -\frac{1}{h^2} \cdot \frac{2h^2}{6} = -\frac{1}{3}
$$
其中 $\int_{0}^{h} \frac{x}{h} \left(1 - \frac{x}{h}\right)  dx = \frac{h}{6}$，且积分区域对称。


# 习题 2.30

>[!question]
>使用问题 2.29 的结果，将 Galerkin 方法应用于泊松方程的积分等效形式，边界上的电势为零：
>
>$$\int_V dx \, dy [\nabla \phi_{i,j} \cdot \nabla \psi - 4\pi \rho \phi_{i,j}] = 0$$
>
>其中试探函数为：
>
>$$\psi(x, y) = \sum_{i', j'=1}^N \psi_{i', j'} \phi_{i', j'}(x, y)$$
>
>对于问题 1.24 中的格子，具有三个独立的格点。证明你得到三个关于 $\psi_{i,j}$ 值 $(\psi_1, \psi_2, \psi_3)$ 的耦合方程，并求解以找到这些点上的“Galerkin”近似电势。与精确值以及问题 1.24c 的各种迭代结果进行比较。评论。
>
>（注：$\psi = 4\pi \epsilon_0 \Phi$）

#### 解答

考虑问题 1.24 中的格子，假设三个内部点排列为：点 1 在 $(i,j)$，点 2 在 $(i+1,j)$，点 3 在 $(i,j+1)$。基函数 $\phi_{i,j}$ 为“金字塔”函数，满足问题 2.29 中的积分关系。

Galerkin 方法要求残差与每个基函数正交：
$$
\int_V [\nabla \phi_{i,j} \cdot \nabla \psi - 4\pi \rho \phi_{i,j}] dx dy = 0
$$
代入 $\psi = \sum_{i',j'} \psi_{i',j'} \phi_{i',j'}$，得到线性方程组：
$$
\sum_{i',j'} \psi_{i',j'} \int_V \nabla \phi_{i,j} \cdot \nabla \phi_{i',j'} dx dy = 4\pi \int_V \rho \phi_{i,j} dx dy
$$

利用问题 2.29 的结果：
- $\int \nabla \phi_{i,j} \cdot \nabla \phi_{i,j} dx dy = \frac{8}{3}$
- $\int \nabla \phi_{i+1,j} \cdot \nabla \phi_{i,j} dx dy = -\frac{1}{3}$
- $\int \nabla \phi_{i,j+1} \cdot \nabla \phi_{i,j} dx dy = -\frac{1}{3}$
- $\int \nabla \phi_{i+1,j+1} \cdot \nabla \phi_{i,j} dx dy = -\frac{1}{3}$

假设电荷密度 $\rho$ 为常数，则右端项：
$$
b_i = 4\pi \int \rho \phi_i dx dy = 4\pi \rho h^2
$$
令 $b = 4\pi \rho h^2$。

得到线性方程组：
$$
\begin{aligned}
\frac{8}{3} \psi_1 - \frac{1}{3} \psi_2 - \frac{1}{3} \psi_3 &= b \\
-\frac{1}{3} \psi_1 + \frac{8}{3} \psi_2 - \frac{1}{3} \psi_3 &= b \\
-\frac{1}{3} \psi_1 - \frac{1}{3} \psi_2 + \frac{8}{3} \psi_3 &= b
\end{aligned}
$$

乘以 3 得：
$$
\begin{aligned}
8\psi_1 - \psi_2 - \psi_3 &= 3b \\
-\psi_1 + 8\psi_2 - \psi_3 &= 3b \\
-\psi_1 - \psi_2 + 8\psi_3 &= 3b
\end{aligned}
$$

由对称性，$\psi_1 = \psi_2 = \psi_3 = \psi$，代入第一式：
$$
8\psi - \psi - \psi = 6\psi = 3b \implies \psi = \frac{b}{2} = 2\pi \rho h^2
$$

因此，Galerkin 近似为：
$$
\psi_1 = \psi_2 = \psi_3 = 2\pi \rho h^2
$$

与有限差分法比较：有限差分方程同样给出 $\psi_1 = \psi_2 = \psi_3 = 2\pi \rho h^2$，与 Galerkin 方法一致。问题 1.24c 的迭代结果也收敛于此值。
