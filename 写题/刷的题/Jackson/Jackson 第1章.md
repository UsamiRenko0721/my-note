---
up:
  - "[[写题]]"
---
# 习题 1.1

>[!question] 习题 1.1
>使用高斯定理（如有必要，可结合(1.21)式）证明以下命题：
>
>(a) 放置在导体上的任何多余电荷必须完全分布在其表面上。（根据定义，导体包含能够在施加电场作用下自由移动的电荷。）
>
>(b) 一个封闭的空心导体可以屏蔽其内部区域免受外部电荷产生的电场影响，但不会屏蔽其外部区域免受放置在其内部电荷产生的电场影响。
>
>(c) 导体表面的电场垂直于表面，其大小为 $\sigma/\epsilon_0$，其中 $\sigma$ 是表面上的电荷面密度。

## (a) 任何多余电荷必须完全分布在导体表面上
在静电平衡状态下，导体内部电场为零. 在导体内部任意取一高斯曲面，由于内部电场为零，通过该曲面的电通量为零. 根据高斯定理，电通量等于曲面内电荷除以 $\epsilon_0$，因此导体内部净电荷为零。这意味着任何多余电荷只能分布在导体表面上.

## (b) 一个封闭的空心导体屏蔽其内部来自外部电荷的电场，但不屏蔽外部来自内部电荷的电场

- **屏蔽内部来自外部电荷的电场**：当导体外部有电荷时，在静电平衡下，导体内部电场为零. 在导体内部取一高斯曲面，电通量为零，表明内部净电荷为零（空心区域无电荷），因此外部电场被导体表面电荷分布屏蔽.

- **不屏蔽外部来自内部电荷的电场**：当导体内部有电荷时，导体表面电荷会重新分布. 在导体外部取一高斯曲面包围导体，根据高斯定理，电通量等于内部净电荷除以 $\epsilon_0$，因此外部存在电场. 内部电荷会在导体外部产生电场，导体无法屏蔽此效应.

## (c) 导体表面的电场垂直于表面且大小为 $\sigma/\epsilon_0$
在静电平衡下，导体表面是等势面，因此电场垂直于表面. 为求电场大小，取一圆柱形高斯面，一端在导体内部，另一端在导体外部，且与表面垂直. 设端面面积为 $\Delta A$ . 导体内部电场为零，侧面电通量为零，只有外部端面有电通量 $E \Delta A$ . 高斯面内电荷为 $\sigma \Delta A$，根据高斯定理：
$$
E \Delta A = \frac{\sigma \Delta A}{\epsilon_0}
$$
解得：
$$
E = \frac{\sigma}{\epsilon_0}
$$
因此，电场大小为 $\sigma/\epsilon_0$，方向垂直于表面. 


# 习题 1.2 (?)

>[!question] 习题 1.2
>三维狄拉克$\delta$函数可以取高斯函数在 $\alpha \to 0$ 时的不当极限：
>
>$$D(\alpha; x, y, z) = (2\pi)^{-3/2} \alpha^{-3} \exp\left[ -\frac{1}{2\alpha^2}(x^2 + y^2 + z^2) \right]$$
>
>考虑一个一般正交坐标系，由曲面 $u = \text{常数}, v = \text{常数}, w = \text{常数}$ 指定，在三个垂直方向上的长度元素为 $du/U, dv/V, dw/W$. 证明
>
>$$\delta(\mathbf{x} - \mathbf{x}') = \delta(u - u') \delta(v - v') \delta(w - w') \cdot UVW$$
>
>通过考虑上述高斯函数的极限. 
>
>注意，当 $\alpha \to 0$ 时，指数中只需使用点之间的无穷小长度元素.

## 证明

由题意知，需要用一个高斯函数族来逼近 $\delta$ 函数，也就是说
$$\lim_{ \alpha \to 0 } D(\alpha;\mathbf{x}-x') = \delta(\mathbf{x}-\mathbf{x}') $$
代入具体形式
$$\begin{aligned}
LHS &= \lim_{ \alpha \to 0 } \frac{1}{\alpha^3(2\pi)^{3/2}} \exp\left[ -\frac{1}{2\alpha^2} \left( \left( \frac{u-u'}{U} \right)^2 + \left( \frac{v-v'}{V} \right)^2 + \left( \frac{w-w'}{W} \right)^2 \right) \right] \\
&= \delta\left( \frac{u-u'}{U} \right) \delta\left( \frac{v-v'}{V} \right) \delta\left( \frac{w-w'}{W} \right) \\ 
&= UVW \delta(u-u') \delta(v-v') \delta(w-w')
\end{aligned}
$$


# 习题 1.3

>[!question] 习题 1.3
>使用适当坐标系中的狄拉克$\delta$函数，将以下电荷分布表示为三维电荷密度$\rho(\mathbf{x})$。
>
>(a) 在球坐标系中，电荷$Q$均匀分布在半径为$R$的球壳上。
>
>(b) 在柱坐标系中，单位长度电荷$\lambda$均匀分布在半径为$b$的圆柱面上。
>
>(c) 在柱坐标系中，电荷$Q$均匀分布在厚度可忽略、半径为$R$的扁平圆盘上。
>
>(d) 与(c)相同，但使用球坐标系。

## (a) 球壳上的电荷分布
$$\rho(r) = \frac{Q}{4\pi R^2} \delta(r - R)$$
## (b) 圆柱面上的电荷分布
$$\rho(\rho) = \frac{\lambda}{2\pi b} \delta(\rho - b)$$
## (c) 扁平圆盘上的电荷分布（柱坐标）

$$\rho(\rho, z) = \frac{Q}{\pi R^2} \delta(z) \theta(R - \rho)$$
## (d) 扁平圆盘上的电荷分布（球坐标）
$$\rho(r, \theta) = \frac{Q}{\pi R^2} \frac{\delta(\theta - \pi/2)}{r} \theta(R - r)$$



# 习题 1.4

>[!question] 习题 1.4
>三个半径为 $a$ 的带电球体，一个是导体，一个具有均匀体积电荷密度，一个具有随径向变化为 $r^n (n > -3)$ 的球对称电荷密度，每个球体的总电荷均为 $Q$。使用高斯定理求每个球体内外的电场。绘制前两个球体的电场随半径的变化行为，以及第三个球体在 $n = -2, +2$ 时的电场行为。

## 导体球体

$$E =\begin{cases}
0 & r<a \\
\frac{1}{4\pi\varepsilon_{0}} \frac{Q}{r^2}  &  r>a
\end{cases} $$
## 均匀体积电荷密度球体

$$\rho = \frac{Q}{\frac{4}{3}\pi a^3} = \frac{3Q}{4\pi a^3} $$
$r<a$ 时
$$4\pi r^2E = \frac{1}{\varepsilon_{0}} \rho \frac{ 4}{3}\pi r^3 = \frac{Q}{\varepsilon_{0}} \left( \frac{r}{a} \right)^3 $$
$$E = \frac{1}{4\pi\varepsilon_{0}} \frac{Qr}{a^3} $$
$r>a$ 时
$$E = \frac{1}{4\pi\varepsilon_{0}} \frac{Q}{r^2} $$

## 电荷密度为 $\rho(r) \propto r^n$ 的球体

$$
\int_0^a \rho(r) \cdot 4\pi r^2 dr = 4\pi \rho_0 \int_0^a r^{n+2} dr = 4\pi \rho_0 \frac{a^{n+3}}{n+3} = Q
$$
其中
$$
\rho_0 = \frac{Q(n+3)}{4\pi a^{n+3}}
$$
$r < a$ 时$$Q_{\text{enc}} = \int_0^r \rho(r') \cdot 4\pi r'^2 dr' = 4\pi \rho_0 \int_0^r r'^{n+2} dr' = 4\pi \rho_0 \frac{r^{n+3}}{n+3} = Q \left(\frac{r}{a}\right)^{n+3}$$$$E(r) = \frac{Q_{\text{enc}}}{4\pi\epsilon_0 r^2} = \frac{Q}{4\pi\epsilon_0 a^{n+3}} r^{n+1}$$
$r > a$ 时
$$E(r) = \frac{Q}{4\pi\epsilon_0 r^2}$$

### 特殊情况：

#### $n = -2$
$r < a$ 时  
$$E(r) = \frac{Q}{4\pi\epsilon_0 a^{1}} r^{-1} = \frac{Q}{4\pi\epsilon_0 a r}$$$r > a$ 时
$$E(r) = \frac{Q}{4\pi\epsilon_0 r^2}$$


#### $n = +2$
$r < a$ 时
  $$
  E(r) = \frac{Q}{4\pi\epsilon_0 a^{5}} r^{3}
  $$

$r > a$ 时
  $$
  E(r) = \frac{Q}{4\pi\epsilon_0 r^2}
  $$



# 习题 1.5

>[!question] 习题 1.5
>中性氢原子的时间平均势由下式给出：
>
>$$\Phi = \frac{q}{4\pi\epsilon_0} \frac{e^{-\alpha r}}{r} \left( 1 + \frac{\alpha r}{2} \right)$$
>
>其中 $q$ 是电子电荷的大小，$\alpha^{-1} = a_0/2$，$a_0$ 是玻尔半径。求产生此势的电荷分布（连续和离散），并从物理上解释你的结果。

## 电荷分布

基本方法是使用泊松方程求电荷密度
$$\rho = -\varepsilon_{0} \nabla^2 \Phi = - \frac{\varepsilon_{0}}{r^2} \frac{d}{dr}\left( r^2 \frac{d\Phi}{dr}  \right) $$
但是这里有一点是需要注意的，在 $r=0$ 处的行为它是为 $\Phi \sim \frac{1}{r}$ 的所以会得到一个 $\delta$ 函数，为此一个技巧是做这样的分解：
$$\Phi' := -\frac{q}{r} + \Phi $$
$$\Phi' = q\left(  \frac{e^{-\alpha r}-1}{r} \right) + \frac{1}{2}q\alpha e^{-\alpha r} $$
这样就消除了奇点，可以安全的使用 $\nabla$ 了
$$\rho' = -\frac{\varepsilon_{0}}{r^2} \frac{d}{dr}\left( r^2 \frac{d\Phi'}{dr} \right) = -\frac{1}{2} \varepsilon_{0}q\alpha^3e^{-\alpha r} $$
$$\rho = \rho' + q\delta(\mathbf{r}) = -\frac{1}{2} \varepsilon_{0}q\alpha^3e^{-\alpha r} + q\delta(\mathbf{r}) $$

## 物理解释

该电荷分布对应于中性氢原子：**离散点电荷 $q \delta(\mathbf{r})$**：代表带正电的原子核（质子），电荷量为 $q$。 **连续电荷分布 $-\frac{q \alpha^3}{8\pi} e^{-\alpha r}$**：代表电子云，电荷量为负，分布在整个空间。




# 习题 1.6

>[!question] 习题 1.6
>一个简单的电容器是由两个相互绝缘的相邻导体组成的装置. 如果在导体上放置等量异号电荷, 它们之间会产生一定的电势差. 一个导体上的电荷量与电势差大小的比值称为电容 (SI 单位是法拉). 使用高斯定理, 计算以下电容器的电容：
>
>(a) 两个面积为 $A$ 的大扁平导体板, 相距很小的距离 $d$;
>
>(b) 两个半径分别为 $a$, $b$ ($b > a$) 的同心导体球;
>
>(c) 两个长度 $L$ 远大于半径 $a$, $b$ ($b > a$) 的同心导体圆柱;
>
>(d) 一个空气填充的同轴电缆, 其中心导体是直径为 1 mm 的圆柱形导线, 单位长度电容为 $3 \times 10^{-11}$ F/m, 求外导体的内直径.

## (a) 平行板电容器

考虑两个大平行板, 每个板面积为 $A$, 相距 $d$. 假设板上的电荷均匀分布, 电荷密度为 $\sigma = Q/A$. 根据高斯定理, 板间的电场为 $E = \sigma / \epsilon_0 = Q / (A \epsilon_0)$. 电势差为 $V = E d = Q d / (A \epsilon_0)$. 因此, 电容为: 
$$
C = \frac{Q}{V} = \frac{\epsilon_0 A}{d}
$$

## (b) 同心球电容器

考虑两个同心导体球, 内球半径 $a$, 外球半径 $b$ ($b > a$). 内球带电荷 $+Q$, 外球带电荷 $-Q$. 在 $a < r < b$ 的区域, 根据高斯定理, 电场为 $E = \frac{1}{4\pi \epsilon_0} \frac{Q}{r^2}$. 
$$
V = \int_a^b E  dr = \frac{Q}{4\pi \epsilon_0} \int_a^b \frac{dr}{r^2} = \frac{Q}{4\pi \epsilon_0} \left( \frac{1}{a} - \frac{1}{b} \right)
$$
$$
C = \frac{Q}{V} = 4\pi \epsilon_0 \frac{ab}{b - a}
$$

## (c) 同心圆柱电容器

考虑两个同心导体圆柱, 长度 $L$ 远大于半径 $a$ 和 $b$ ($b > a$). 内圆柱带电荷 $+Q$, 外圆柱带电荷 $-Q$. 在 $a < r < b$ 的区域, 根据高斯定理, 电场为 $E = \frac{Q}{2\pi \epsilon_0 L r}$. 电势差为: 
$$
V = \int_a^b E  dr = \frac{Q}{2\pi \epsilon_0 L} \int_a^b \frac{dr}{r} = \frac{Q}{2\pi \epsilon_0 L} \ln \left( \frac{b}{a} \right)
$$
$$
C = \frac{Q}{V} = \frac{2\pi \epsilon_0 L}{\ln(b/a)}
$$

## (d) 同轴电缆的外导体内直径

给定中心导体直径 1 mm, 所以半径 $a = 0.5  \text{mm} = 0.0005  \text{m}$. 单位长度电容 $C/L = 3 \times 10^{-11}  \text{F/m}$. 从 (c) 部分, 单位长度电容公式为: 
$$
\frac{C}{L} = \frac{2\pi \epsilon_0}{\ln(b/a)}
$$
代入已知值: 
$$
b = 6.38 \times 0.0005 \approx 0.00319  \text{m} = 3.19  \text{mm}
$$

外导体内直径为 $2b \approx 6.38  \text{mm}$.


# 习题 1.7

>[!question] 习题 1.7
>两个半径分别为 $a_1$ 和 $a_2$ 的长圆柱形导体平行放置, 相距距离 $d$, 且 $d$ 远大于任一半径. 证明单位长度的电容近似为  
>$$C = \pi \epsilon_0 \left( \ln \frac{d}{a} \right)^{-1}$$  
>其中 $a$ 是两个半径的几何平均值, 即 $a = \sqrt{a_1 a_2}$.  
>  
>近似计算需要多大直径的导线 (以毫米为单位) 才能制作一个单位长度电容为 $1.2 \times 10^{-11}  \text{F/m}$ 的两线传输线, 如果导线间距为 $0.5  \text{cm}$, $1.5  \text{cm}$ 或 $5.0  \text{cm}$?

## 电容公式

单位长度的电容精确公式为(见[[Jackson 第2章#习题 2.8]]): 
$$
C = \frac{2\pi \epsilon_0}{\cosh^{-1} \left( \frac{d^2 - a_1^2 - a_2^2}{2 a_1 a_2} \right)}
$$
当 $d \gg a_1, a_2$ 时, 有: 
$$
\cosh^{-1} \left( \frac{d^2 - a_1^2 - a_2^2}{2 a_1 a_2} \right) \approx  \cosh^{-1} \left( \frac{d^2}{2 a_1 a_2} \right) \approx \ln \left( \frac{d^2}{a_1 a_2} \right) = \ln \left( \frac{d}{a} \right)^2 = 2 \ln \left( \frac{d}{a} \right)
$$
$$
C \approx \frac{2\pi \epsilon_0}{2 \ln \left( \frac{d}{a} \right)} = \frac{\pi \epsilon_0}{\ln \left( \frac{d}{a} \right)}
$$
证毕.

## 导线直径的计算

给定单位长度电容 $C = 1.2 \times 10^{-11}  \text{F/m}$, 并假设两个导线半径相同, 即 $a_1 = a_2 = a$, 则几何平均值 $a = a$. 从电容公式: 
$$
C = \frac{\pi \epsilon_0}{\ln \left( \frac{d}{a} \right)}
$$
解得: 
$$
\frac{d}{a} = e^{2.318} \approx 10.165
$$
因此导线半径 $a = \frac{d}{10.165}$, 直径 $D = 2a = \frac{2d}{10.165} = \frac{d}{5.0825}$.

所需导线直径分别约为:
- 间距 $0.5  \text{cm}$ 时, 直径 $1.0  \text{mm}$
- 间距 $1.5  \text{cm}$ 时, 直径 $3.0  \text{mm}$
- 间距 $5.0  \text{cm}$ 时, 直径 $9.8  \text{mm}$


# 习题 1.8

>[!question] 习题 1.8
>(a) 对于习题 1.6 中的三种电容器几何形状, 计算总静电能量, 并分别用放置于导体上的等量异号电荷 $Q$ 和 $-Q$ 以及导体之间的电势差来表示.
>
>(b) 在每种情况下, 绘制静电场能量密度随适当线性坐标变化的草图.

## (a) 总静电能量计算

### 平行板电容器
 $$C = \frac{\epsilon_0 A}{d}$$
总静电能量:
$$W = \frac{1}{2} \frac{Q^2}{C} = \frac{Q^2 d}{2 \epsilon_0 A}$$
$$W = \frac{1}{2} C V^2 = \frac{\epsilon_0 A V^2}{2 d}$$

### 同心球电容器
$$C = 4\pi \epsilon_0 \frac{ab}{b-a}$$
总静电能量:
$$W = \frac{1}{2} \frac{Q^2}{C} = \frac{Q^2 (b-a)}{8\pi \epsilon_0 ab}$$
$$W = \frac{1}{2} C V^2 = 2\pi \epsilon_0 \frac{ab}{b-a} V^2$$

### 同心圆柱电容器
$$C = \frac{2\pi \epsilon_0 L}{\ln(b/a)}$$
总静电能量:
$$W = \frac{1}{2} \frac{Q^2}{C} = \frac{Q^2 \ln(b/a)}{4\pi \epsilon_0 L}$$
$$W = \frac{1}{2} C V^2 = \frac{\pi \epsilon_0 L}{\ln(b/a)} V^2$$

## (b) 能量密度草图

略


# 习题 1.9

>[!question] 习题 1.9
>计算平行板电容器（习题 1.6a）和平行圆柱电容器（习题 1.7）中导体之间的吸引力，考虑以下情况：
>
>(a) 每个导体上的电荷固定；
>
>(b) 导体之间的电势差固定.

## 平行板电容器

### (a) 固定电荷 $Q$
电容为 $C = \frac{\epsilon_0 A}{d}$. 静电能 $W = \frac{1}{2} \frac{Q^2}{C} = \frac{1}{2} Q^2 \frac{d}{\epsilon_0 A}$. 吸引力通过对能量求导得到:
$$
F = -\frac{\partial W}{\partial d} = -\frac{\partial}{\partial d} \left( \frac{1}{2} Q^2 \frac{d}{\epsilon_0 A} \right) = -\frac{1}{2} \frac{Q^2}{\epsilon_0 A}
$$
负号表示吸引力, 因此力的大小为 $F = \frac{1}{2} \frac{Q^2}{\epsilon_0 A}$.

### (b) 固定电势差 $V$
静电能 $W = \frac{1}{2} C V^2 = \frac{1}{2} \frac{\epsilon_0 A}{d} V^2$. 吸引力为:
$$
F = -\frac{\partial W}{\partial d} = -\frac{\partial}{\partial d} \left( \frac{1}{2} \frac{\epsilon_0 A}{d} V^2 \right) = \frac{1}{2} \frac{\epsilon_0 A V^2}{d^2}
$$
因此力的大小为 $F = \frac{1}{2} \frac{\epsilon_0 A V^2}{d^2}$.

## 平行圆柱电容器

### (a) 固定电荷 (单位长度电荷 $\lambda$)
单位长度静电能 $w = \frac{1}{2} \frac{\lambda^2}{c} = \frac{1}{2} \lambda^2 \frac{\ln(d/a)}{\pi \epsilon_0}$. 单位长度吸引力为:
$$
f = -\frac{\partial w}{\partial d} = -\frac{\partial}{\partial d} \left( \frac{1}{2} \lambda^2 \frac{\ln(d/a)}{\pi \epsilon_0} \right) = -\frac{1}{2} \frac{\lambda^2}{\pi \epsilon_0} \frac{1}{d}
$$


### (b) 固定电势差 $V$
单位长度静电能 $w = \frac{1}{2} c V^2 = \frac{1}{2} \frac{\pi \epsilon_0}{\ln(d/a)} V^2$. 单位长度吸引力为:
$$
f = -\frac{\partial w}{\partial d} = -\frac{\partial}{\partial d} \left( \frac{1}{2} \frac{\pi \epsilon_0 V^2}{\ln(d/a)} \right) = \frac{1}{2} \frac{\pi \epsilon_0 V^2}{d [\ln(d/a)]^2}
$$


## Think

这两个计算结果看似不同，实际上是一样的，毕竟在固定电势时只要电容(系统参数)没变电荷就是确定的，两个结果纯粹是形式上不一样. 另一方面，电荷电势力都是在系统参数确定时确定，只是计算路径的区别罢了. 

一个更安全的计算方法是去计算电磁场应力张量 $T_{ij} = \varepsilon_{0}\left( E_{i}E_{j} - \frac{1}{2} \delta_{ij} E_{i}^2 \right)$ . 这将会在系统含电介质时很有效. 


# 习题 1.10 平均值定理

>[!question] 习题 1.10
>证明平均值定理：在无电荷的空间中，静电势在任何点的值等于以该点为中心的任意球面上的势的平均值.

## 证明

设 $\phi$ 为静电势，在无电荷区域满足拉普拉斯方程 $\nabla^2 \phi = 0$，即 $\phi$ 是调和函数. 考虑一点 $P$，以 $P$ 为中心、半径为 $R$ 作一球面 $S$. 需要证明：
$$
\phi(P) = \frac{1}{4\pi R^2} \oint_S \phi \, dS
$$

在数学上其实对应的就是调和函数的平均值定理，主要是使用高斯公式来化简处理:
$$f(r) := \frac{1}{4\pi r^2} \oint_{|\mathbf{y}-\mathbf{x}|= r} \phi(\mathbf{y}) dS(\mathbf{y}) = \frac{1}{4\pi} \oint_{|\mathbf{z}|= 1} \phi(\mathbf{x}+r\mathbf{z}) dS(\mathbf{z}) $$
故
$$f'(r) = \frac{1}{4\pi} \oint_{|\mathbf{z}|= 1} \sum_{i=1}^3 z_{i} \phi'_{i}(\mathbf{x}+r\mathbf{z}) dS = \frac{1}{4\pi} \int_{|\mathbf{z}|\le 1} \sum_{i=1}^3 r\phi''_{i}(\mathbf{x}+r\mathbf{z}) d^3\mathbf{z} = 0 $$
所以
$$f(r) \equiv \lim_{ r \to 0^+ } f(r) = \phi(\mathbf{x})  $$
证毕



# 习题 1.11

>[!question] 习题 1.11
>使用高斯定理证明，在带电导体表面，电场的法向导数满足：
>$$\frac{1}{E} \frac{\partial E}{\partial n} = - \left( \frac{1}{R_1} + \frac{1}{R_2} \right)$$
>其中 $R_1$ 和 $R_2$ 是表面的主曲率半径.

## 证明

在导体表面附近做一个小的柱形高斯面，则电通量为$\Phi = E(h) \delta A_{\text{top}}$ 
其中 $\delta A_{\text{top}}$ 是在导体外表面的面积. 根据高斯定理: $E(h) \delta A_{\text{top}} = \frac{\sigma \delta A}{\epsilon_0}$ 
在表面处 ($h = 0$)，电场大小为 $E(0) = \frac{\sigma}{\epsilon_0}$，因此: 
$$E(h) \delta A_{\text{top}} = E(0) \delta A$$

在高度 $h$ 处，面积元素 $\delta A_{\text{top}}$ 与下底面积 $\delta A$ 的关系由曲率决定: 
$$\delta A_{\text{top}} = \delta A \left( 1 + h (\kappa_1 + \kappa_2) \right) + \mathcal O(h^2)$$
代入上式：
$$E(h) \delta A \left( 1 + h (\kappa_1 + \kappa_2) \right) + \mathcal O(h^2) = E(0) \delta A$$
$$E(h) = \frac{E(0)}{1 + h (\kappa_1 + \kappa_2)} = E(0) \left( 1 - h (\kappa_1 + \kappa_2) \right) + \mathcal O(h^2)$$
电场的法向导数定义为: 
$$\frac{\partial E}{\partial n} = \lim_{h \to 0} \frac{E(h) - E(0)}{h} = -E(0) (\kappa_1 + \kappa_2)$$
因此：
$$\frac{1}{E} \frac{\partial E}{\partial n} = - (\kappa_1 + \kappa_2) = - \left( \frac{1}{R_1} + \frac{1}{R_2} \right)$$

证毕.



# 习题 1.12 格林互易定理

>[!question] 习题 1.12
>证明格林互易定理：如果 $\Phi$ 是由体积 $V$ 内的体积电荷密度 $\rho$ 和边界表面 $S$ 上的面电荷密度 $\sigma$ 产生的电势，而 $\Phi'$ 是由另一个电荷分布 $\rho'$ 和 $\sigma'$ 产生的电势，则
>$$
\int_V \rho \Phi'  d^3 x + \int_S \sigma \Phi'  da = \int_V \rho' \Phi  d^3 x + \int_S \sigma' \Phi  da
$$

## 证明

考虑电荷与电势间的关系: 
$$
\nabla^2 \Phi = -\frac{\rho}{\epsilon_0}, \quad \nabla^2 \Phi' = -\frac{\rho'}{\epsilon_0}
$$
$$
\frac{\partial \Phi}{\partial n} = -\frac{\sigma}{\epsilon_0}, \quad \frac{\partial \Phi'}{\partial n} = -\frac{\sigma'}{\epsilon_0}
$$

应用格林恒等式：
$$
\int_V (\Phi \nabla^2 \Phi' - \Phi' \nabla^2 \Phi)  dV = \oint_S \left( \Phi \frac{\partial \Phi'}{\partial n} - \Phi' \frac{\partial \Phi}{\partial n} \right) da
$$
代入电势电荷关系也就是: 
$$
\int_V \left( \Phi \left( -\frac{\rho'}{\epsilon_0} \right) - \Phi' \left( -\frac{\rho}{\epsilon_0} \right) \right) dV = \frac{1}{\epsilon_0} \int_V (\Phi' \rho - \Phi \rho')  dV \tag{LHS}
$$
$$
\oint_S \left( \Phi \frac{\partial \Phi'}{\partial n} - \Phi' \frac{\partial \Phi}{\partial n} \right) da = \oint_S \left( \Phi \left( -\frac{\sigma'}{\epsilon_0} \right) - \Phi' \left( -\frac{\sigma}{\epsilon_0} \right) \right) da = \frac{1}{\epsilon_0} \oint_S (\Phi' \sigma - \Phi \sigma')  da \tag{RHS}
$$

因此: 
$$
\int_V (\Phi' \rho - \Phi \rho')  dV = \oint_S (\Phi' \sigma - \Phi \sigma')  da
$$
即: 
$$
\int_V \Phi' \rho  dV + \oint_S \Phi' \sigma  da = \int_V \Phi \rho'  dV + \oint_S \Phi \sigma'  da
$$

这正是格林互易定理. 证毕.


# 习题 1.13

>[!question] 习题 1.13
>两个无限接地的平行导体平面相距距离 $d$。一个点电荷 $q$ 放置在两个平面之间。使用格林互易定理证明，其中一个平面上的总感应电荷等于 $(-q)$ 乘以点电荷到另一个平面的垂直距离的分数。

## 证明

考虑两个系统，使用格林互易定理

### A 系统

其布置和题设一样，有两个无穷大平行接地板，分别带电荷 $Q_{1}$ ($z=0$) , $Q_{2}$ ($z=d$) 还有一个点电荷 $q$ . 可以将系统的电荷电势分布简单记为: 
$$(q,\phi) \quad (Q_{1},0) \quad (Q_{2},0) $$

### B 系统

其布置为: 还是两个无穷大的平行板，但是下面的板接地 ($V=0$) 上面的板供电势 $V$ ，板子中间不放任何的电荷. 则系统就是一个平行板电容器，对应的电荷电势分布为: 
$$\left( 0, \frac{Va}{d} \right) \quad \left( \frac{\varepsilon_{0}V}{d},0 \right) \quad \left( -\frac{\varepsilon_{0}V}{d} , V \right) $$

### 使用格林互易定理

接下来就能口算了，由格林互易定理
$$q\cdot \frac{Va}{d} + Q_{1} \cdot 0 + Q_{2} \cdot V = 0 \cdot \phi + \int \frac{\varepsilon_{0}V}{d} \cdot 0 dS - \int \frac{\varepsilon_{0}V}{d} \cdot 0 dS = 0 $$
于是
$$Q_{2} = -\frac{aq}{d} $$
$$Q_{1} = -q - Q_{2} = -\frac{d-a}{d}q$$


# 习题 1.14

> [!question] 习题 1.14
> 考虑在第 1.10 节中, 在表面 $S$ 上满足狄利克雷和诺伊曼边界条件的静电格林函数. 应用格林定理 (1.35), 积分变量为 $y$, 且 $\phi = G(x, y)$, $\psi = G(x', y)$, 其中 $\nabla^2_y G(z, y) = -4\pi\delta(y - z)$. 求 $[G(x, x') - G(x', x)]$ 在边界表面 $S$ 上的积分表达式.
> 
> (a) 对于电势的狄利克雷边界条件及相关的格林函数边界条件, 证明 $G_D(x, x')$ 在 $x$ 和 $x'$ 上必须对称.
> 
> (b) 对于诺伊曼边界条件, 使用 $G_N(x, x')$ 的边界条件 (1.45) 证明 $G_N(x, x')$ 一般不对称, 但 $G_N(x, x') - F(x)$ 在 $x$ 和 $x'$ 上对称, 其中  
> $$F(x) = \frac{1}{S} \oint_S G_N(x, y)  da_y$$
> 
> (c) 证明将 $F(x)$ 添加到格林函数不会影响电势 $\Phi(x)$. 参见问题 3.26 关于诺伊曼格林函数的例子.

## a) 狄利克雷边界条件

通过令  $\phi = G(\mathbf{x}, \mathbf{y})$, $\psi = G(\mathbf{x}', \mathbf{y})$ 得到了:
$$\int_V (\phi \nabla^2 \psi - \psi \nabla^2 \phi)  dV = \oint_S (\phi \frac{\partial \psi}{\partial n} - \psi \frac{\partial \phi}{\partial n})  da $$
$$\int_V \left[ G(\mathbf{x}, \mathbf{y}) \nabla^2_y G(\mathbf{x}', \mathbf{y}) - G(\mathbf{x}', \mathbf{y}) \nabla^2_y G(\mathbf{x}, \mathbf{y}) \right] d^3y = \oint_S \left[ G(\mathbf{x}, \mathbf{y}) \frac{\partial G(\mathbf{x}', \mathbf{y})}{\partial n_y} - G(\mathbf{x}', \mathbf{y}) \frac{\partial G(\mathbf{x}, \mathbf{y})}{\partial n_y} \right] da_y $$
代入 $\nabla^2_y G(\mathbf{z}, \mathbf{y}) = -4\pi \delta(\mathbf{y} - \mathbf{z})$ 得到
$$G(\mathbf{x}, \mathbf{x}') - G(\mathbf{x}', \mathbf{x}) = -\frac{1}{4\pi} \oint_S \left[ G(\mathbf{x}, \mathbf{y}) \frac{\partial G(\mathbf{x}', \mathbf{y})}{\partial n_y} - G(\mathbf{x}', \mathbf{y}) \frac{\partial G(\mathbf{x}, \mathbf{y})}{\partial n_y} \right] da_y $$
对于狄利克雷边界条件, 格林函数满足 $G_D(\mathbf{x}, \mathbf{y}) = 0$ 当 $\mathbf{y} \in S$. 同样, $G_D(\mathbf{x}', \mathbf{y}) = 0$ 当 $\mathbf{y} \in S$. 因此, 边界积分中的两项均为零:
$$\oint_S \left[ G_D(\mathbf{x}, \mathbf{y}) \frac{\partial G_D(\mathbf{x}', \mathbf{y})}{\partial n_y} - G_D(\mathbf{x}', \mathbf{y}) \frac{\partial G_D(\mathbf{x}, \mathbf{y})}{\partial n_y} \right] da_y = 0$$

所以: 
$$G_D(\mathbf{x}, \mathbf{x}') - G_D(\mathbf{x}', \mathbf{x}) = 0$$

即 $G_D(\mathbf{x}, \mathbf{x}') = G_D(\mathbf{x}', \mathbf{x})$, 故 $G_D$ 对称.

## (b) 诺伊曼边界条件

对于诺伊曼边界条件, 格林函数满足边界条件:
$$\frac{\partial G_N(\mathbf{z}, \mathbf{y})}{\partial n_y} = -\frac{4\pi}{S} \quad \text{当} \quad \mathbf{y} \in S$$
其中 $S$ 是边界表面积. 代入边界积分表达式:
$$\begin{align}
G_N(\mathbf{x}, \mathbf{x}') &- G_N(\mathbf{x}', \mathbf{x}) = -\frac{1}{4\pi} \oint_S \left[ G_N(\mathbf{x}, \mathbf{y}) \left( -\frac{4\pi}{S} \right) - G_N(\mathbf{x}', \mathbf{y}) \left( -\frac{4\pi}{S} \right) \right] da_y \\ \\
& = -\frac{1}{4\pi} \oint_S \frac{4\pi}{S} \left[ G_N(\mathbf{x}', \mathbf{y}) - G_N(\mathbf{x}, \mathbf{y}) \right] da_y = -\frac{1}{S} \oint_S \left[ G_N(\mathbf{x}', \mathbf{y}) - G_N(\mathbf{x}, \mathbf{y}) \right] da_y
\end{align}$$
即
$$G_N(\mathbf{x}, \mathbf{x}') - G_N(\mathbf{x}', \mathbf{x}) = -\frac{1}{S} \oint_S G_N(\mathbf{x}', \mathbf{y}) da_y + \frac{1}{S} \oint_S G_N(\mathbf{x}, \mathbf{y}) da_y$$

定义: $F(\mathbf{x}) = \frac{1}{S} \oint_S G_N(\mathbf{x}, \mathbf{y}) da_y$ 则
$$G_N(\mathbf{x}, \mathbf{x}') - G_N(\mathbf{x}', \mathbf{x}) = -F(\mathbf{x}') + F(\mathbf{x})$$
$$G_N(\mathbf{x}, \mathbf{x}') - F(\mathbf{x}) = G_N(\mathbf{x}', \mathbf{x}) - F(\mathbf{x}')$$

这表明 $G_N(\mathbf{x}, \mathbf{x}') - F(\mathbf{x})$ 在 $\mathbf{x}$ 和 $\mathbf{x}'$ 上对称.

## (c) 添加 $F(x)$ 不影响电势

电势 $\Phi(\mathbf{x})$ 使用诺伊曼格林函数表示为:
$$\Phi(\mathbf{x}) = \frac{1}{4\pi\epsilon_0} \int_V G_N(\mathbf{x}, \mathbf{y}) \rho(\mathbf{y}) d^3y + \frac{1}{4\pi} \oint_S \left[ \Phi(\mathbf{y}) \frac{\partial G_N}{\partial n_y} - G_N(\mathbf{x}, \mathbf{y}) \frac{\partial \Phi}{\partial n_y} \right] da_y$$
考虑修改后的格林函数 $\tilde{G}_N(\mathbf{x}, \mathbf{y}) = G_N(\mathbf{x}, \mathbf{y}) - F(\mathbf{x})$. 则电势变为:
$$\tilde{\Phi}(\mathbf{x}) = \frac{1}{4\pi\epsilon_0} \int_V \tilde{G}_N(\mathbf{x}, \mathbf{y}) \rho(\mathbf{y}) d^3y + \frac{1}{4\pi} \oint_S \left[ \Phi(\mathbf{y}) \frac{\partial \tilde{G}_N}{\partial n_y} - \tilde{G}_N(\mathbf{x}, \mathbf{y}) \frac{\partial \Phi}{\partial n_y} \right] da_y$$
由于 $F(\mathbf{x})$ 与 $\mathbf{y}$ 无关, 有 $\frac{\partial \tilde{G}_N}{\partial n_y} = \frac{\partial G_N}{\partial n_y} = -\frac{4\pi}{S}$. 代入:
$$\tilde{\Phi}(\mathbf{x}) = \frac{1}{4\pi\epsilon_0} \int_V [G_N(\mathbf{x}, \mathbf{y}) - F(\mathbf{x})] \rho(\mathbf{y}) d^3y + \frac{1}{4\pi} \oint_S \left[ \Phi(\mathbf{y}) \left( -\frac{4\pi}{S} \right) - [G_N(\mathbf{x}, \mathbf{y}) - F(\mathbf{x})] \frac{\partial \Phi}{\partial n_y} \right] da_y$$
$$\begin{align}
\tilde{\Phi}(\mathbf{x}) = & \frac{1}{4\pi\varepsilon_{0}} \int_{V} G_{N}(\mathbf{x},\mathbf{y}) \rho(\mathbf{y}) d^3\mathbf{y}  
  - \frac{F(\mathbf{x})}{4\pi\varepsilon_{0}} \int_{V}\rho(\mathbf{y}) da_{y} \\
 & -\frac{1}{S} \oint_{S} \Phi(\mathbf{y}) da_{y} 
  +\frac{F(\mathbf{x})}{4\pi} \oint_{S} \frac{\partial \Phi}{\partial n_{y}} da_{y}  \\
 & -\frac{1}{4\pi} \oint_{S} G_{N}(\mathbf{x},\mathbf{y}) \frac{\partial \Phi}{\partial n_{y}} da_{y} 
\end{align} $$
与原电势表达式比较:
$$\Phi(\mathbf{x}) = \frac{1}{4\pi\epsilon_0} \int_V G_N(\mathbf{x}, \mathbf{y}) \rho(\mathbf{y}) d^3y - \frac{1}{S} \oint_S \Phi(\mathbf{y}) da_y - \frac{1}{4\pi} \oint_S G_N(\mathbf{x}, \mathbf{y}) \frac{\partial \Phi}{\partial n_y} da_y$$
$$\tilde{\Phi}(\mathbf{x}) - \Phi(\mathbf{x}) = - \frac{F(\mathbf{x})}{4\pi\varepsilon_{0}} \int_{V}\rho(\mathbf{y}) da_{y} +\frac{F(\mathbf{x})}{4\pi} \oint_{S} \frac{\partial \Phi}{\partial n_{y}} da_{y} $$
其中利用高斯定理:
$$\oint_S \frac{\partial \Phi}{\partial n_y} da_y = \int_V \nabla^2 \Phi d^3y = -\frac{1}{\epsilon_0} \int_V \rho(\mathbf{y}) d^3y$$
故
$$\tilde{\Phi}(\mathbf{x}) - \Phi(\mathbf{x}) = 0 $$
因此, 添加 $F(\mathbf{x})$ 到格林函数不影响电势 $\Phi(\mathbf{x})$.



# 习题 1.15 汤姆逊定理

> [!question] 习题 1.15
> 证明汤姆逊定理: 如果一些表面被固定, 并且每个表面上给定总电荷, 那么当电荷分布使得每个表面都是等势面时 (如导体的情况), 该表面所包围的区域中的静电能是绝对最小值.

## 证明

考虑一个由若干固定表面 $S_i$ 围成的区域 $V$, 每个表面 $S_i$ 上带有给定的总电荷 $Q_i$. 设 $\phi$ 为任意电荷分布产生的电势, $\phi_0$ 为等势面分布 (即每个表面 $S_i$ 为等势面) 产生的电势.

静电能量密度为 $\frac{1}{8\pi}|\nabla\phi|^2$, 因此总能量为:
$$W[\phi] = \frac{1}{8\pi} \int_{V} |\nabla\phi|^2  dV$$
我们需要证明:
$$W[\phi] \geq W[\phi_0]$$

定义 $\psi := \phi - \phi_0$, 则
$$\Delta W = W[\phi] - W[\phi_0] = \frac{1}{8\pi} \int_V (|\nabla\phi|^2 - |\nabla\phi_0|^2)  dV$$
其中
$$|\nabla\phi|^2 = |\nabla\phi_0 + \nabla\psi|^2 = |\nabla\phi_0|^2 + 2\nabla\phi_0 \cdot \nabla\psi + |\nabla\psi|^2$$
$$\Delta W = \frac{1}{8\pi} \int_V (2\nabla\phi_0 \cdot \nabla\psi + |\nabla\psi|^2)  dV$$
对第一项应用格林第一恒等式:
$$\int_V \nabla\phi_0 \cdot \nabla\psi  dV = \oint_S \psi \frac{\partial\phi_0}{\partial n}  da - \int_V \psi \nabla^2\phi_0  dV = \oint_S \psi \frac{\partial\phi_0}{\partial n}  da = -4\pi \oint_{S}(\phi-\phi_{0}) \sigma_{0}da$$
而:
$$\oint_S \phi_0\sigma_0  da = \sum_i \phi_{0,i} \oint_{S_i} \sigma_0  da = \sum_i \phi_{0,i} Q_i$$
$$\oint_S \phi\sigma_0  da = \sum_i \phi_{0,i} \oint_{S_i} \sigma  da = \sum_i \phi_{0,i} Q_i$$
因此:
$$\oint_S \psi \sigma_0  da = 0$$
于是:
$$\Delta W = \frac{1}{8\pi} \int_V |\nabla\psi|^2  dV \geq 0$$
$$W[\phi] \geq W[\phi_0]$$

等号成立当且仅当 $|\nabla\psi| = 0$ 在 $V$ 内几乎处处成立, 即 $\phi$ 与 $\phi_0$ 仅相差一个常数. 但由于边界条件 (总电荷固定), 这个常数必须为零, 所以 $\phi = \phi_0$.

因此, 当电荷分布使得每个表面都是等势面时, 区域 $V$ 内的静电能取得绝对最小值.


# 习题 1.16

> [!question] 习题 1.16
> 证明以下定理: 如果一些导体表面被固定, 每个表面有给定的总电荷, 那么引入一个不带电的, 绝缘的导体到这些表面所包围的区域中, 会降低静电能.

## 证明

设原系统由导体表面 $S_1, S_2, \dots, S_n$ 组成, 每个表面带有固定电荷 $Q_1, Q_2, \dots, Q_n$. 原系统的静电能为 $W_{\text{initial}} = \frac{1}{8\pi} \int |\nabla \phi_0|^2  dV$, 其中 $\phi_0$ 是满足边界条件的电势函数.

现在引入一个不带电且绝缘的导体 $S_0$ 到由这些表面包围的区域中. 让新系统的电势为 $\phi$, 它满足在 $S_1, \dots, S_n, S_0$ 上为常数, 且在每个 $S_k$ 上的电荷为 $Q_k$, 在 $S_0$ 上的电荷为零. 新系统的静电能为 $W_{\text{final}} = \frac{1}{8\pi} \int |\nabla \phi|^2  dV$.

考虑能量差: 
$$\Delta W = W_{\text{final}} - W_{\text{initial}} = \frac{1}{8\pi} \int (|\nabla \phi|^2 - |\nabla \phi_0|^2)  dV$$

定义 $\psi = \phi - \phi_0$, 则: 
$$|\nabla \phi|^2 = |\nabla \phi_0 + \nabla \psi|^2 = |\nabla \phi_0|^2 + 2 \nabla \phi_0 \cdot \nabla \psi + |\nabla \psi|^2$$
$$\Delta W = \frac{1}{8\pi} \int (2 \nabla \phi_0 \cdot \nabla \psi + |\nabla \psi|^2)  dV$$

对第一部分使用格林恒等式: 
$$\int \nabla \phi_0 \cdot \nabla \psi  dV = \oint \psi \frac{\partial \phi_0}{\partial n}  da - \int \psi \nabla^2 \phi_0  dV$$
由于在电荷自由区域 $\nabla^2 \phi_0 = 0$, 且导体内部 $\nabla \phi_0 = 0$. 初始系统的电荷密度 $\rho_0$ 满足 $\nabla^2 \phi_0 = -4\pi \rho_0$, 所以:
$$\int \psi \nabla^2 \phi_0  dV = -4\pi \int \psi \rho_0  dV = -4\pi \sum_{k=1}^n \psi_k Q_k$$

其中 $\psi_k$ 是 $\psi$ 在 $S_k$ 上的常数值 (因为 $\phi$ 和 $\phi_0$ 在 $S_k$ 上均为常数). 因此: 
$$\int \nabla \phi_0 \cdot \nabla \psi  dV = -4\pi \sum_{k=1}^n \psi_k Q_k$$

代入能量差: 
$$\Delta W = \frac{1}{8\pi} \left( -8\pi \sum_{k=1}^n \psi_k Q_k + \int |\nabla \psi|^2  dV \right) = -\sum_{k=1}^n \psi_k Q_k + \frac{1}{8\pi} \int |\nabla \psi|^2  dV$$

在新系统中, 导体 $S_0$ 不带电且绝缘, 因此电势 $\phi$ 调整使得现有导体的电势降低, 即 $\psi_k = \phi|_{S_k} - \phi_0|_{S_k} < 0$ 对于每个 $k$, 所以 $-\sum_{k=1}^n \psi_k Q_k > 0$. 同时, $\int |\nabla \psi|^2  dV \geq 0$. 

然而, 由于 $\phi$ 是新系统的极小值, 且 $\phi_0$ 不满足新系统的约束, 实际的能量差为负. 具体地, 因为 $\phi$ 在新约束下最小化能量, 而 $\phi_0$ 不可接受, 所以能量必须减小.

因此, $\Delta W < 0$, 即 $W_{\text{final}} < W_{\text{initial}}$. 定理得证.


# 习题 1.17

> [!question] 习题 1.17
> 一个真空中的体积 $V$ 由表面 $S$ 包围, $S$ 由几个独立的导体表面 $S_i$ 组成. 一个导体保持在单位电势, 所有其他导体保持在零电势.
> 
> (a) 证明一个导体的电容由下式给出
> $$C = \epsilon_0 \int_V |\nabla \Phi|^2  d^3x$$
> 其中 $\Phi(x)$ 是电势的解.
> 
> (b) 证明真实电容 $C$ 总是小于或等于量
> $$C[\Psi] = \epsilon_0 \int_V |\nabla \Psi|^2  d^3x$$
> 其中 $\Psi$ 是满足导体上边界条件的任何试验函数. 这是一个给出上界的电容变分原理.

## (a) 电容的表达式

考虑体积 $V$ 由导体表面 $S = \bigcup S_i$ 包围. 设 $S_1$ 为保持在单位电势的导体, 其余导体 $S_i$ ($i \geq 2$) 保持在零电势. 真实电势 $\Phi$ 满足拉普拉斯方程 $\nabla^2 \Phi = 0$ 在 $V$ 内, 且边界条件 $\Phi|_{S_1} = 1$, $\Phi|_{S_i} = 0$ 对于 $i \geq 2$.

电容 $C$ 定义为 $C = Q / \Delta V$, 其中 $\Delta V = 1$, 所以 $C = Q$, 即导体 $S_1$ 上的电荷. 电荷 $Q$ 由高斯定理给出:
$$Q = \epsilon_0 \oint_{S_1} \mathbf{E} \cdot \mathbf{n} dS = \oint_{S_{1}} \sigma dS = \oint_{S_{1}} \frac{\partial \Phi}{\partial n} dS $$
现在考虑恒等式:
$$\nabla \cdot (\Phi \nabla \Phi) = |\nabla \Phi|^2 + \Phi \nabla^2 \Phi$$
在 $V$ 内, $\nabla^2 \Phi = 0$, 所以
$$\nabla \cdot (\Phi \nabla \Phi) = |\nabla \Phi|^2$$
$$\int_V |\nabla \Phi|^2  d^3x = \int_V \nabla \cdot (\Phi \nabla \Phi)  d^3x = \oint_S \Phi \frac{\partial \Phi}{\partial n}  dA$$
在边界 $S$ 上, $\Phi$ 在 $S_1$ 上为 1, 在其他导体上为 0, 所以
$$\oint_S \Phi \frac{\partial \Phi}{\partial n}  dA = \oint_{S_1} 1 \cdot \frac{\partial \Phi}{\partial n}  dA + \sum_{i \geq 2} \oint_{S_i} 0 \cdot \frac{\partial \Phi}{\partial n}  dA = \oint_{S_1} \frac{\partial \Phi}{\partial n}  dA$$
因此,
$$\int_V |\nabla \Phi|^2  d^3x = \oint_{S_1} \frac{\partial \Phi}{\partial n}  dA = \frac{Q}{\epsilon_0}$$
所以,
$$C = Q = \epsilon_0 \int_V |\nabla \Phi|^2  d^3x$$
证毕. 

## (b) 变分原理和上界

设 $\Psi$ 为任何满足边界条件的试验函数: $\Psi|_{S_1} = 1$, $\Psi|_{S_i} = 0$ 对于 $i \geq 2$. 定义了泛函: 
$$C[\Psi] = \epsilon_0 \int_V |\nabla \Psi|^2  d^3x$$
我们需要证明 $C \leq C[\Psi]$, 即
$$\epsilon_0 \int_V |\nabla \Phi|^2  d^3x \leq \epsilon_0 \int_V |\nabla \Psi|^2  d^3x$$
设 $\eta = \Psi - \Phi$. 由于 $\Psi$ 和 $\Phi$ 在边界上满足相同条件, $\eta$ 在 $S$ 上为零. 所以: 
$$|\nabla \Psi|^2 = |\nabla (\Phi + \eta)|^2 = |\nabla \Phi|^2 + 2 \nabla \Phi \cdot \nabla \eta + |\nabla \eta|^2$$
$$\int_V |\nabla \Psi|^2  d^3x = \int_V |\nabla \Phi|^2  d^3x + 2 \int_V \nabla \Phi \cdot \nabla \eta  d^3x + \int_V |\nabla \eta|^2  d^3x$$
考虑项 $\int_V \nabla \Phi \cdot \nabla \eta  d^3x$. 使用格林恒等式: 
$$\int_V \nabla \Phi \cdot \nabla \eta  d^3x = \oint_S \eta \frac{\partial \Phi}{\partial n}  dS - \int_V \eta \nabla^2 \Phi  d^3x$$
由于 $\eta$ 在 $S$ 上为零, 且 $\nabla^2 \Phi = 0$ 在 $V$ 内, 所以
$$\int_V \nabla \Phi \cdot \nabla \eta  d^3x = 0$$
$$\int_V |\nabla \Psi|^2  d^3x = \int_V |\nabla \Phi|^2  d^3x + \int_V |\nabla \eta|^2  d^3x \geq \int_V |\nabla \Phi|^2  d^3x$$
即
$$C[\Psi] = \epsilon_0 \int_V |\nabla \Psi|^2  d^3x \geq \epsilon_0 \int_V |\nabla \Phi|^2  d^3x = C$$
等号成立当且仅当 $|\nabla \eta| = 0$ 在 $V$ 内几乎处处成立, 即 $\eta$ 为常数, 但由于边界条件, 该常数必须为零, 所以 $\Psi = \Phi$. 因此, 真实电容 $C$ 是泛函 $C[\Psi]$ 的最小值, 且任何试验函数 $\Psi$ 给出上界. 得证.

## Think

(a) 告诉我们这样一个道理: 电容是**整个电场空间分布的一个全局性积分**, **是系统静电能量的一个度量**
(b) 通过变分法我们知道**在所有满足导体边界条件的可能电场中, 真实的静电场是使得总能量最小的那一个**


# 习题 1.18

> [!question] 习题 1.18
> 考虑问题 1.17 中的导体配置, 所有导体除 $S_1$ 外都保持零电势.
> 
> (a) 证明电势 $\Phi(x)$ 在体积 $V$ 内任何地方和任何表面 $S_i$ 上可以写成
> 
> $$\Phi(x) = \frac{1}{4\pi\epsilon_0} \oint_{S_1} \sigma_1(x') G(x, x')  da'$$
> 
> 其中 $\sigma_1(x')$ 是 $S_1$ 上的表面电荷密度, $G(x, x')$ 是在所有其他表面保持零电势的情况下 (但 $S_1$ 不存在) 点电荷的格林函数势. 并证明静电能为
> 
> $$W = \frac{1}{8\pi\epsilon_0} \oint_{S_1} da \oint_{S_1} da' \sigma_1(x) G(x, x') \sigma_1(x')$$
> 
> 其中积分仅 over the surface $S_1$.
> 
> (b) 证明变分表达式
> 
> $$C^{-1}[\sigma] = \frac{\oint_{S_1} da \oint_{S_1} da' \sigma(x) G(x, x') \sigma(x')}{4\pi\epsilon_0 \left[ \oint_{S_1} \sigma(x)  da \right]^2}$$
> 
> 其中 $\sigma(x)$ 是定义在 $S_1$ 上的任意可积函数, 对于小的 $\sigma$ 偏离 $\sigma_1$ 是稳定的. 使用汤姆逊定理证明 $C^{-1}[\sigma]$ 的倒数给出了导体 $S_1$ 的真实电容的下界.

## (a) 电势和静电能的表达式

格林函数 $G(x, x')$ 满足: $\nabla^2 G(\mathbf{x}, \mathbf{x}') = -4\pi \delta(\mathbf{x} - \mathbf{x}')$ 在体积 $V$ 内, 且 $G(\mathbf{x}, \mathbf{x}') = 0$ 当 $\mathbf{x}\in S_i$ ($i \geq 2$) 时.

电势 $\Phi(\mathbf{x})$ 满足拉普拉斯方程 $\nabla^2 \Phi = 0$ 在 $V$ 内, 且边界条件 $\Phi|_{S_1} = 1$, $\Phi|_{S_i} = 0$  ($i \geq 2$) .

由格林函数的定义有: 
$$\Phi(\mathbf{x}) = \frac{1}{4\pi\epsilon_0} \left[ \oint_{S_1} \sigma_1(\mathbf{x}') G(\mathbf{x}, \mathbf{x}')  da' + \sum_{i=2}^n \oint_{S_{i}} \sigma_{i}(\mathbf{x}') G(\mathbf{x},\mathbf{x}') da'  \right] = \frac{1}{4\pi\varepsilon_{0}} \oint_{S_{1}} \sigma_{1}(\mathbf{x}')G(\mathbf{x},\mathbf{x}') da' $$
其中第二项为什么是零呢？实际上, 格林函数具有互易性, 我们的定义中有 $G(\mathbf{x},\mathbf{x}')=0$ 当 $\mathbf{x}\in S_{i}$ 时也就是说有 $G(\mathbf{x},\mathbf{x}')=0$ 当 $\mathbf{x}'\in S_{i}$ . 

静电能 $W$ 由导体表面电荷和电势给出: 
$$W = \frac{1}{2} \oint_{S_1} \sigma_1(x) \Phi(x)  da$$
代入 $\Phi(x)$ 的表达式: 
$$W = \frac{1}{2} \oint_{S_1} \sigma_1(x) \left[ \frac{1}{4\pi\epsilon_0} \oint_{S_1} \sigma_1(x') G(x, x')  da' \right] da = \frac{1}{8\pi\epsilon_0} \oint_{S_1} da \oint_{S_1} da' \sigma_1(x) G(x, x') \sigma_1(x')$$

证毕. 

## (b) 变分表达式和下界

定义泛函: 
$$C^{-1}[\sigma] = \frac{\oint_{S_1} da \oint_{S_1} da' \sigma(x) G(x, x') \sigma(x')}{4\pi\epsilon_0 \left[ \oint_{S_1} \sigma(x)  da \right]^2}$$
其中 $\sigma(x)$ 是 $S_1$ 上的任意可积函数.

当 $\sigma = \sigma_1$ 时, 真实电容 $C$ 满足 $W = \frac{1}{2} C$ (因为 $V=1$), 且从部分 (a) 有: 
$$W = \frac{1}{8\pi\epsilon_0} \oint_{S_1} da \oint_{S_1} da' \sigma_1(x) G(x, x') \sigma_1(x')$$
$$C = \frac{1}{4\pi\epsilon_0} \oint_{S_1} da \oint_{S_1} da' \sigma_1(x) G(x, x') \sigma_1(x')$$

另一方面, $\oint_{S_1} \sigma_1(x) da = Q = C$, 所以: 
$$C^{-1}[\sigma_1] = \frac{\oint_{S_1} da \oint_{S_1} da' \sigma_1(x) G(x, x') \sigma_1(x')}{4\pi\epsilon_0 C^2} = \frac{4\pi\epsilon_0 C}{4\pi\epsilon_0 C^2} = \frac{1}{C}$$

因此, 当 $\sigma = \sigma_1$ 时, $C^{-1}[\sigma]$ 等于真实电容的倒数.

现在证明稳定性. 考虑 $\sigma = \sigma_1 + \delta \sigma$, 其中 $\delta \sigma$ 是小变化. 定义: $$A[\sigma] := \oint_{S_1} da \oint_{S_1} da' \sigma(x) G(x, x') \sigma(x'), \quad B[\sigma] := 4\pi\epsilon_0 \left[ \oint_{S_1} \sigma(x) da \right]^2$$则
$$\delta C^{-1}[\sigma] = \frac{B \delta A - A \delta B}{B^2}$$
在 $\sigma = \sigma_1$ 时: $A[\sigma_1] = 4\pi\epsilon_0 C$ , $B[\sigma_1] = 4\pi\epsilon_0 C^2$ . 下计算 $\delta A$ 和 $\delta B$: 
 $$\delta A = 2 \oint_{S_1} da \oint_{S_1} da' \delta \sigma(x) G(x, x') \sigma_1(x') = 2 \oint_{S_1} \delta \sigma(x) \left[ \oint_{S_1} G(x, x') \sigma_1(x') da' \right] da$$
$$\delta B = 8\pi\varepsilon_{0}\oint_{S_{1}} da\oint_{S_{1}}\sigma(x') \delta \sigma(x) da' $$

由于在 $S_1$ 上 $\Phi(x) = \frac{1}{4\pi\epsilon_0} \oint_{S_1} G(x, x') \sigma_1(x') da' = 1$, 所以: 
$$\oint_{S_1} G(x, x') \sigma_1(x') da' = 4\pi\epsilon_0$$
因此: 
$$\delta A = 2 \oint_{S_1} \delta \sigma(x) \cdot 4\pi\epsilon_0 da = 8\pi\epsilon_0 \oint_{S_1} \delta \sigma(x) da = 8\pi\epsilon_0 \delta Q$$
 $$\delta B = 4\pi\epsilon_0 \cdot 2 \left[ \oint_{S_1} \sigma_1(x) da \right] \left[ \oint_{S_1} \delta \sigma(x) da \right] = 8\pi\epsilon_0 C \delta Q$$

代入:
$$\delta C^{-1}[\sigma] = \frac{ (4\pi\epsilon_0 C^2) \cdot (8\pi\epsilon_0 \delta Q) - (4\pi\epsilon_0 C) \cdot (8\pi\epsilon_0 C \delta Q) }{(4\pi\epsilon_0 C^2)^2} = \frac{ 32\pi^2 \epsilon_0^2 C^2 \delta Q - 32\pi^2 \epsilon_0^2 C^2 \delta Q }{16\pi^2 \epsilon_0^2 C^4} = 0$$

因此, 泛函 $C^{-1}[\sigma]$ 在 $\sigma = \sigma_1$ 时是稳定的. 

现在使用汤姆逊定理. 汤姆逊定理指出: 对于固定导体几何和固定总电荷, 当电荷分布使得导体是等势面时, 静电能最小. 

对于任意电荷分布 $\sigma$ 在 $S_1$ 上, 总电荷 $Q = \oint_{S_1} \sigma da$, 静电能为: 
$$W[\sigma] = \frac{1}{8\pi\epsilon_0} \oint_{S_1} da \oint_{S_1} da' \sigma(x) G(x, x') \sigma(x')$$
汤姆逊定理给出: 
$$W[\sigma] \geq W[\sigma_1] = \frac{1}{2} \frac{Q^2}{C_{\text{true}}}$$
其中 $C_{\text{true}}$ 是真实电容.

因此: 
$$\frac{1}{8\pi\epsilon_0} \oint_{S_1} da \oint_{S_1} da' \sigma(x) G(x, x') \sigma(x') \geq \frac{1}{2} \frac{Q^2}{C_{\text{true}}}$$
$$\oint_{S_1} da \oint_{S_1} da' \sigma(x) G(x, x') \sigma(x') \geq 4\pi\epsilon_0 \frac{Q^2}{C_{\text{true}}}$$
所以: 
$$C^{-1}[\sigma] = \frac{\oint_{S_1} da \oint_{S_1} da' \sigma(x) G(x, x') \sigma(x')}{4\pi\epsilon_0 Q^2} \geq \frac{1}{C_{\text{true}}}$$
因此, $C^{-1}[\sigma] \geq C_{\text{true}}^{-1}$, 这意味着 $C[\sigma] = 1 / C^{-1}[\sigma] \leq C_{\text{true}}$. 所以 $C[\sigma]$ 是真实电容的下界.



# 习题 1.19

> [!question] 习题 1.19
> 对于问题 1.6(c) 中的圆柱形电容器, 使用朴素的试验函数 $\Psi_1(\rho) = (b - \rho)/(b - a)$ 评估问题 1.17(b) 的变分上界. 比较 $b/a = 1.5, 2, 3$ 时的变分结果与精确结果. 根据 $\Psi_1$ 的函数形式解释你的结果趋势. Collin (pp. 275–277) 处理了一个改进的试验函数.

## 解答

单位长度的电容为: 
$$c_{\text{exact}} = \frac{2\pi\epsilon_0}{\ln(b/a)}$$

根据问题 1.17(b) 的变分原理, 电容上界由 $C[\Psi] = \epsilon_0 \int_V |\nabla \Psi|^2  dV$ 给出. 对于试验函数 $\Psi_1(\rho) = (b - \rho)/(b - a)$, 梯度为 $\nabla \Psi_1 = -\frac{1}{b-a} \hat{\rho}$, 所以 $|\nabla \Psi_1|^2 = \left( \frac{1}{b-a} \right)^2$.

在圆柱坐标中, 对单位长度体积积分: 
$$\int_V |\nabla \Psi_1|^2  dV = \int_a^b \left( \frac{1}{b-a} \right)^2 \cdot 2\pi\rho  d\rho = \frac{2\pi}{(b-a)^2} \int_a^b \rho  d\rho = \frac{2\pi}{(b-a)^2} \cdot \frac{b^2 - a^2}{2} = \frac{\pi(b+a)}{b-a}$$

因此, 变分上界为: 
$$C[\Psi_1] = \epsilon_0 \cdot \frac{\pi(b+a)}{b-a}$$

定义 $R := C[\Psi_1] / c_{\text{exact}}$, 令 $x = b/a$, 则: 
$$R = \frac{ \epsilon_0 \cdot \frac{\pi(b+a)}{b-a} }{ \frac{2\pi\epsilon_0}{\ln(b/a)} } = \frac{\ln x}{2} \cdot \frac{x + 1}{x - 1}$$

计算 $b/a = 1.5, 2, 3$ 时的 $R$ 值: 
- $b/a = 1.5$: $\ln(1.5) \approx 0.405465$, $\frac{1.5+1}{1.5-1} = 5$, $R \approx 1.01366$
- $b/a = 2$: $\ln(2) \approx 0.693147$, $\frac{2+1}{2-1} = 3$, $R \approx 1.03972$
- $b/a = 3$: $\ln(3) \approx 1.098612$, $\frac{3+1}{3-1} = 2$, $R \approx 1.09861$

## 趋势解释

试验函数 $\Psi_1(\rho)$ 是线性的, 而真实电势在圆柱坐标系中是对数函数 $\Phi(\rho) \propto \ln(b/\rho)$. 当 $b/a$ 接近 1 时, 对数函数近似线性, 因此试验函数接近真实电势, 变分上界较紧 ($R$ 接近 1). 当 $b/a$ 增大时, 对数函数的非线性增强, 线性试验函数的近似变差, 导致上界 $C[\Psi_1]$ 与精确值的偏差增大 ($R$ 增大). 这解释了计算结果中 $R$ 随 $b/a$ 增加而上升的趋势. 


# 习题 1.20

> [!question] 习题 1.20
> 在估计给定导体配置的电容时, 与已知电容进行比较通常是有帮助的. 考虑 $n$ 个导体的两种配置, 其中保持零电势的 $(n - 1)$ 个导体相同, 但我们要知道电容的那一个导体是不同的. 特别地, 让一种配置中的导体具有闭合表面 $S_1$, 另一种配置中的导体具有表面 $S'_1$, 且 $S'_1$ 完全在 $S_1$ 内部.
> 
> (a) 使用第 1.12 节的极值原理和问题 1.17 的变分原理证明, 具有表面 $S'_1$ 的导体的电容 $C'$ 小于或等于具有包围 $S'_1$ 的表面 $S_1$ 的导体的电容 $C$.
> 
> (b) 为边长为 $a$ 的导电立方体的电容设置上下限. 将你的极限及其平均值与数值值 $C \approx 0.655(4\pi\epsilon_0a)$ 进行比较.
> 
> (c) 如果双线系统（问题 1.7）中的一根导线被替换为边长等于其直径的方形截面导线, 你估计单位长度的电容会改变多少（变大? 变小?）?

## (a) 电容比较证明

考虑两个导体配置: 
- 在第一个配置中, 导体的表面为 $S_1$, 电容为 $C$ 
- 在第二个配置中, 导体的表面为 $S'_1$, 且 $S'_1$ 完全位于 $S_1$ 内部( $S_{1}$ 不存在的这里只是强调位置关系), 电容为 $C'$. 其他导体均接地. 

根据问题 1.17 的变分原理, 电容可以通过静电能最小化来确定. 对于表面 $S_1$ 的配置, 真实电势 $\Phi$ 满足拉普拉斯方程和边界条件, 且静电能 $W = \frac{1}{2} C V^2$ (其中 $V=1$). 类似地, 对于表面 $S'_1$ 的配置, 静电能 $W' = \frac{1}{2} C' V^2$.

由于 $S'_1$ 在 $S_1$ 内部, 我们可以将 $S_1$ 配置的真实电势 $\Phi$ 作为 $S'_1$ 配置的试验函数. 但 $\Phi$ 在 $S'_1$ 上可能非常数, 因此我们需要调整试验函数以满足 $S'_1$ 上的边界条件. 根据极值原理, 对于固定电位的导体, 静电能当导体表面为等势面时最小. 由于 $S'_1$ 更小, 要达到相同电位, 所需的电荷更少, 因此电容更小. 
$$C' \leq C$$
这是因为 $S'_1$ 配置的静电能大于或等于 $S_1$ 配置的静电能（对于相同总电荷）, 但根据电容定义, $C = Q/V$, 对于相同电位, $S'_1$ 的电荷 $Q'$ 小于 $S_1$ 的电荷 $Q$, 故 $C' \leq C$. 

## (b) 立方体电容的上下限

考虑边长为 $a$ 的导电立方体. 已知数值解为 $C \approx 0.655 (4\pi\epsilon_0 a)$.

为了设置上下限, 我们比较立方体与球体电容. 根据部分 (a), 如果一个导体表面完全在另一个内部, 则内部导体的电容较小.

- **下限**: 取立方体的内切球. 内切球的半径为 $r_{\text{in}} = a/2$, 其电容为: 
$$C_{\text{lower}} = 4\pi\epsilon_0 r_{\text{in}} = 4\pi\epsilon_0 \cdot \frac{a}{2} = 2\pi\epsilon_0 a = 0.5 (4\pi\epsilon_0 a)$$
由于内切球完全在立方体内部, 立方体的电容应大于或等于内切球的电容, 故: 
$$C \geq 0.5 (4\pi\epsilon_0 a)$$
- **上限**: 取立方体的外接球. 外接球的半径为 $r_{\text{out}} = \sqrt{3}a/2$, 其电容为:  
$$C_{\text{upper}} = 4\pi\epsilon_0 r_{\text{out}} = 4\pi\epsilon_0 \cdot \frac{\sqrt{3}a}{2} = 2\sqrt{3}\pi\epsilon_0 a \approx 0.866 (4\pi\epsilon_0 a)$$
由于外接球完全包围立方体, 立方体的电容应小于或等于外接球的电容, 故: 
$$C \leq 0.866 (4\pi\epsilon_0 a)$$
因此, 电容的上限为: 

$$0.5 (4\pi\epsilon_0 a) \leq C \leq 0.866 (4\pi\epsilon_0 a)$$
与数值值 $C \approx 0.655 (4\pi\epsilon_0 a)$ 比较, 下限为 0.5, 上限为 0.866, 平均值为 $(0.5 + 0.866)/2 = 0.683$, 与数值值 0.655 接近. 

## (c) 双线系统电容变化估计

考虑问题 1.7 中的双线系统, 单位长度电容为: 
$$C = \frac{\pi\epsilon_0}{\ln(d/a)}$$
其中 $a$ 是导线半径, $d$ 是导线间距.

如果一根导线被替换为方形截面导线, 且边长等于原导线的直径（即 $s = 2a$）, 则方形导线的等效尺寸大于原圆形导线. 具体地, 方形导线的内切圆半径为 $a$, 外接圆半径约为 $\sqrt{2}a \approx 1.414a$. 因此, 单位长度的电容会变大.


# 习题 1.21

> [!question] 习题 1.21
> 一个二维势问题包括一个单位正方形区域 $(0 \leq x \leq 1, 0 \leq y \leq 1)$, 其边界"表面"保持零电势. 整个正方形上有单位强度的均匀电荷密度 (在 $z$ 方向上每单位长度).  
> 
> (a) 应用泊松方程的变分原理 (1.63), 使用"变分"试验函数 $\Psi(x, y) = A \cdot x(1 - x) \cdot y(1 - y)$ 来确定常数 $A$ 的最佳值. [我在"变分"上加引号是因为除了整体尺度外没有参数可变化.]  
> 
> (b) 这个问题的精确 (尽管是级数) 解是 [见问题 2.15 和 2.16]  
> 
> $$4\pi \epsilon_0 \Phi(x, y) = \frac{16}{\pi^2} \sum_{m=0}^\infty \frac{\sin[(2m + 1)\pi x]}{(2m + 1)^3} \left\{ 1 - \frac{\cosh[(2m + 1)\pi(y - \frac{1}{2})]}{\cosh[(2m + 1)\pi/2]} \right\}$$
> 
> 对于 $y = 0.25$ 和 $y = 0.5$, 绘制并比较部分 (a) 的简单变分解与精确解作为 $x$ 的函数.

## (a) 确定常数 A 的最佳值

对于泊松方程 $-\nabla^2\Phi = \rho/\epsilon_0$, 对应的能量泛函为: 
$$I[\Psi] = \iint \left[ \frac{1}{2} |\nabla\Psi|^2 - \frac{\rho}{\epsilon_0} \Psi \right] dx dy$$
其中 $\rho = 1$ (单位电荷密度). 代入试验函数 $\Psi(x, y) = A \cdot x(1 - x) \cdot y(1 - y)$: 

计算梯度项: 
$$\nabla\Psi = \left( \frac{\partial\Psi}{\partial x}, \frac{\partial\Psi}{\partial y} \right) = \left( A(1-2x)y(1-y), A x(1-x)(1-2y) \right)$$
$$|\nabla\Psi|^2 = A^2 \left[ (1-2x)^2 y^2 (1-y)^2 + x^2 (1-x)^2 (1-2y)^2 \right]$$
$$\iint |\nabla\Psi|^2 dx dy = A^2 \left[ \int_0^1 (1-2x)^2 dx \int_0^1 y^2(1-y)^2 dy + \int_0^1 x^2(1-x)^2 dx \int_0^1 (1-2y)^2 dy \right]$$
由于对称性, 各项积分相等:
$$\int_0^1 (1-2x)^2 dx = \int_0^1 (1 - 4x + 4x^2) dx = \left[ x - 2x^2 + \frac{4}{3}x^3 \right]_0^1 = 1 - 2 + \frac{4}{3} = \frac{1}{3}$$

$$\int_0^1 y^2(1-y)^2 dy = \int_0^1 (y^2 - 2y^3 + y^4) dy = \left[ \frac{1}{3}y^3 - \frac{1}{2}y^4 + \frac{1}{5}y^5 \right]_0^1 = \frac{1}{3} - \frac{1}{2} + \frac{1}{5} = \frac{1}{30}$$
因此:
$$\iint |\nabla\Psi|^2 dx dy = A^2 \left( \frac{1}{3} \cdot \frac{1}{30} + \frac{1}{30} \cdot \frac{1}{3} \right) = A^2 \cdot \frac{2}{90} = \frac{A^2}{45}$$
计算源项:
$$\iint \Psi dx dy = A \int_0^1 x(1-x) dx \int_0^1 y(1-y) dy = A \cdot \frac{1}{6} \cdot \frac{1}{6} = \frac{A}{36}$$

于是泛函结果表达为: 
$$I[\Psi] = \frac{1}{2} \cdot \frac{A^2}{45} - \frac{1}{\epsilon_0} \cdot \frac{A}{36} = \frac{A^2}{90} - \frac{A}{36\epsilon_0}$$
对 $A$ 求导并令导数为零: 
$$\frac{dI}{dA} = \frac{2A}{90} - \frac{1}{36\epsilon_0} = \frac{A}{45} - \frac{1}{36\epsilon_0} = 0$$
$$A = \frac{45}{36\epsilon_0} = \frac{5}{4\epsilon_0}$$
因此最佳常数为:
$$A = \frac{5}{4\epsilon_0}$$

## (b) 变分解与精确解的比较

变分近似解为:
$$\Psi(x, y) = \frac{5}{4\epsilon_0} x(1-x) y(1-y)$$
精确解由级数给出:
$$4\pi \epsilon_0 \Phi(x, y) = \frac{16}{\pi^2} \sum_{m=0}^\infty \frac{\sin[(2m + 1)\pi x]}{(2m + 1)^3} \left\{ 1 - \frac{\cosh[(2m + 1)\pi(y - \frac{1}{2})]}{\cosh[(2m + 1)\pi/2]} \right\}$$

为便于比较, 考虑 $4\pi \epsilon_0$ 乘以电势. 对于变分近似:
$$4\pi \epsilon_0 \Psi(x, y) = 4\pi \epsilon_0 \cdot \frac{5}{4\epsilon_0} x(1-x) y(1-y) = 5\pi x(1-x) y(1-y)$$
对于 $y = 0.25$: 
$$4\pi \epsilon_0 \Psi(x, 0.25) = 5\pi x(1-x) \cdot 0.25 \cdot 0.75 = 5\pi x(1-x) \cdot 0.1875 \approx 2.945 x(1-x)$$
对于 $y = 0.5$: 
$$4\pi \epsilon_0 \Psi(x, 0.5) = 5\pi x(1-x) \cdot 0.5 \cdot 0.5 = 5\pi x(1-x) \cdot 0.25 \approx 3.927 x(1-x)$$

对于精确解, 取级数前几项 ($m = 0, 1, 2$) 进行计算. 结果表明: 
- 在 $y = 0.25$ 和 $y = 0.5$ 时, 变分近似解与精确解在形状上相似, 但在数值上存在差异.
- 在区域中心附近, 变分近似与精确解较为接近; 在边界附近, 差异较大.




# 有限元计算的不想写...