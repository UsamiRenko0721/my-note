---
up:
  - "[[随笔]]"
related:
date: 2026-02-19
---
# 引子

#### 极坐标积分

>[!example]
>我们考虑一个二维平面上的积分
>$$\int_{D} \mathrm{d}^{2}x $$
>其中 $D=\{ (x,y)\mid x^{2}+y^{2}\leq{1} \}$

显然使用极坐标是极好的，我们很快的写下：
$$I = \int r drd{\theta} = \pi $$
很简单，这里我们略写了积分区间为 $(r,\theta)\in[0,1]\times[0,2\pi]$ 但是如果有笨蛋把 $\theta$ 的积分区间写为了 $[0,\infty)$ 的话会导致积分发散的。因为它对同一个点积分了无穷次 $0,2\pi,4\pi,\dots$ 其实是同一个点，但是它重复的在这积分，自然就发散了。

被积函数在 $\theta$ 方向上是不变了，$\theta$ 不是新的物理的方向，是坐标的冗余方向。


#### 多变量函数积分

>[!example]
>我们有一个依赖于 $n+m$ 个变量 (它们的定义域都是整个实数轴) 的函数
>$$F(z_{1},z_{2}, \dots ,z_{n+m}) $$
>这些变量可以如下分类
>$$\begin{gather} x_{r}=\{ z_{1},z_{2} , \dots z_{n} \}, & r=1,\dots,n \\
y_{s}=\{ z_{n+1},\dots,z_{n+m} \}, & s=1,\dots,m \end{gather} $$
>现在 $F$ 只依赖于 $x_{r}$ 
>$$F(z_{1},\dots z_{n+m})=F(x_{r}),\qquad \frac{\partial F}{\partial y_{s}} =0 $$
>考虑这两个积分间的关系，哪个积分能描述 ”将函数在全空间上积分“
>$$I = \int \prod_{r=1}^{n} \mathrm{d}x_{r} \, F(x_{r}) $$
>$$J = \int \prod_{i=1}^{n+m} \mathrm{d}z_{i} \, F(z_{i}) $$

显然对于下面那个积分是发散的，因为我们知道可以写为
$$J = \int \prod_{s=1}^{m} \mathrm{d}y_{s}\, I $$
然后就像在极坐标中的例子一样，其实不同的 $y_{s}$ 们对应是同一个物理点，这样积分必然导致发散。所以下面那个积分虽然看起来很符合 ”对其变量在全空间上积分“ 的意义，但是实际上它的 $y_{s}$ 们不能描述一个真实的物理点，不应该是积分对象。

那么如何改造下面的积分呢，一个很显然的做法是：插入一些 $\delta$ 函数来固定住 $y_{s}$ 
$$I = \int \prod_{i=1}^{m+n} F(z_{i}) \prod_{s=1}^{m} \delta(y_{s}) $$
当然我们也可以选取 $y_{s}$ 不止在平面 $y_{s}=0$ 上，可以限制在 $y_{s}=f_{s}(x_{1},\dots,x_{r})$ 所描述的曲面上，反正 $y_{s}$ 是多少和积分没关系。
$$I = \int \prod_{i=1}^{m+n} \mathrm{d}z_{i} \, F(z_{i}) \prod_{s=1}^{m}\delta(y_{s}-f_{s}) $$
如果使用隐函数来描述这个 $y_{s}$ 的取值曲面 $G_{b}(x_{r},y_{s})=0$ 那么完全等价的
$$I = \int \prod_{a=1}^{m+n} \mathrm{d}z_{a} \, F(z_{i}) \prod_{b=1}^{m}\delta(G_{b})\det\left( \frac{\partial G_{b}}{\partial y_{c}} \right)  $$

> 我们在全空间积分时看似有很多的积分对象，但是只有一部分是真正得积分的，还有一部分是描述冗余的不应该参与积分，为了形式上的同一仍然对所有变量积分，但是对于那些冗余的对象就加上delta函数来固定它们，固定它们就像选择了一种规范的描述方式


# QED

## 规范变换

在 QED 中，我们有一组场，在由 $\chi$ 参数化的规范变换下以各种方式变换：
$$\begin{align}
A^{\mu} & \to A^{\mu} + \partial^{\mu} \chi \\
\psi & \to \mathrm{e}^{ -ie\chi }\psi \\
\bar{\psi} & \to \bar{\psi}\mathrm{e}^{ ie\chi }
\end{align} $$
这些变换描述的是物理上等价的情况：给定任何历史 $(A_\mu, \psi, \bar{\psi} \dots)$ 作为时空函数，如果我施加一个规范变换，就会得到一组新的函数，它们描述的是同一个历史。记 $\boldsymbol{\Phi}=(A_{\mu},\psi,\bar{\psi},\dots)$ 那么一个规范不变的作用量应当有
$$S[\boldsymbol{\Phi}] \to S'[\boldsymbol{\Phi}'] = S[\boldsymbol{\Phi}] $$

## 常见规范选择

- **库仑规范 (Coulomb gauge)**：
  $$\nabla\cdot \mathbf{A}=0 $$
  一旦采用该条件，只要假设 $A$ 在无穷远处消失，就没有进一步进行规范变换的自由
- **轴向规范 (Axial gauge)**：
  $$A_{3}=0 $$
  这个规范在证明某些定理时方便，但计算上很糟糕；它破坏了理论的显式旋转不变性
- **Lorenz 规范**：
  $$\partial_{\mu}A^{\mu} = 0 $$
## FP配方

我们计算配分函数
$$Z = N \int (d\boldsymbol{\Phi}) \exp \{ iS[\boldsymbol{\Phi}] \} $$
立马会遇到和引子中一样的问题，由于规范冗余这个积分是发散的。为此 Faddeev 和 Popov 指出了这一点，和引子中一样他们并不是重新定义了测度 (积分对象) 他们选择重新定义积分：
$$Z = N \int(d\boldsymbol{\Phi}) \exp \{ iS[\boldsymbol{\Phi}] \} \delta(G)\det\left( \frac{\partial G}{\partial \chi} \right) $$
其中的雅可比行列式中的偏导应该理解为泛函微分。


我以 Lorentz 规范为例来说明他们的配方是怎么消除掉规范冗余的。在 Lorentz 规范下
$$G = \partial_{\mu}A^{\mu} $$
$$A^{\mu} \to A^{\mu} + \partial^{\mu}\chi \implies \partial_{\mu}A^{\mu} \to \partial_{\mu}A^{\mu} + \Box\chi $$
于是
$$\det\left( \frac{\partial G}{\partial \chi} \right) = \det\left( \frac{\delta(\partial_{\mu}A^{\mu})}{\delta \chi} \right) = \det(\Box) $$
对 QED 来说，这个行列式是场独立的常数，可以吸收到归一化 N。所以
$$Z = N \int \mathcal{D}A_{\mu}\mathcal{D}\psi \mathcal{D}\bar{\psi} \exp \{ iS[A,\psi,\bar{\psi}] \} \delta(\partial_{\mu}A^{\mu}) $$

## 进一步推广与鬼场

我们取规范为
$$G(\boldsymbol{\Phi}) = \partial_{\mu}A^{\mu} - f(x) $$
这样
$$A^{\mu} \to A^{\mu} + \partial_{\mu}\delta \chi $$
$$\delta G = \delta(\partial_{\mu}A^{\mu}) = \Box\chi $$
也就是说新加的这个任意函数 $f(x)$ 对雅可比行列式没有任何影响。

这个行列式与场无关也就是说它在积分中是一个常数，哪怕新增了函数 $f(x)$ 。在[[鬼场]]中我们知道，一个行列式可以写为鬼场的高斯型积分 (这将更容易看出其和被积场无关) ，这将方便我们得到费曼规则 (也是目的之一)
$$\det\left( \frac{\delta G}{\delta \chi} \right) = \int (\mathrm{d}\eta)(\mathrm{d}\bar{\eta}) e^{ iS_{FP} },\quad S_{FP} = \int \mathrm{d}^{4}x \, \bar{\eta}\Box\eta = -\int \mathrm{d^{4}}x \, (\partial_{\mu}\bar{\eta})(\partial^{\mu}\eta) $$
于是按照配方，配分函数可以写为
$$Z = N \int (d\boldsymbol{\Phi}) e^{ iS }\delta(\partial_{\mu}A^{\mu}-f) $$
考虑到配分函数和那个函数 $f(x)$ 无关，所以可进一步的写为
$$Z = N\int (d\boldsymbol{\Phi})(df) e^{ iS }\delta(\partial_{\mu}A^{\mu}-f)F[f] = N \int (d\boldsymbol{\Phi}) e^{ iS } F[\partial_{\mu}A^{\mu}] $$
为了得到费曼规则，选取泛函 $F$ 为二次型
$$F[f] = \exp \left\{  -\frac{i}{2\xi} \int d^{4}x \, f^{2} \right\} $$
这样我们就能得到配分函数
$$Z = N \int (d\boldsymbol{\Phi}) e^{ iS_{eff} } ,\quad S_{eff} = \int d^{4}x \, \mathcal{L}_{eff} $$
$$\begin{align}
\mathcal{L}_{eff} &  = \mathcal{L} + \mathcal{L}_{鬼} = -\frac{1}{4}(\partial_{\mu}A_{\nu}-\partial_{\nu}A_{\mu})^{2} + \bar{\psi}(i\gamma^{\mu}\partial_{\mu}-m-e\gamma^{\mu}A_{\mu})\psi - \frac{1}{2\xi} (\partial_{\mu}A^{\mu})^{2}  \\& = \frac{1}{2} A^{\mu}\left[  g_{\mu \nu}\Box - \left( 1-\frac{1}{\xi} \right)\partial_{\mu}\partial_{\nu}  \right]A^{\nu} + \bar{\psi}(i\not{\!\partial}-e\not{\!\!A}-m)\psi
\end{align}$$
这就是我们在某些地方会见到的“规范选择”，他们是天降了这么个 $\xi$ ，这这套方案中我们看到它是出于我们对鬼场的选择、得到费曼规则的目的构造的。从拉式量我们容易读出光子传播子[[如何直接读出费曼规则]]
$$\tilde{D}^{\mu \nu}(k) = \frac{i}{k^{2}+i\varepsilon} \left[  -g^{\mu \nu} + \frac{k^{\mu}k^{\nu}}{k^{2}}  \right] - \frac{i\xi}{k^{2}+i\varepsilon} \frac{k^{\mu}k^{\nu}}{k^{2}} $$
这个传播子就没有发散问题了

反过来，通过选取不同的 $\xi$ 我们能够取到不同的规范

- 费曼规范 $\xi=1$
  $$\tilde{D}^{\mu \nu}(k) = -\frac{ig^{\mu \nu}}{k^{2}+i\varepsilon} $$
  很适合低阶的费曼图计算
- 朗道规范 $\xi\to{0}$
  $$\tilde{D}^{\mu \nu}(k) = \frac{i}{k^{2}+i\varepsilon}\left[  -g^{\mu \nu} + \frac{k^{\mu}k^{\nu}}{k^{2}}  \right] $$
  特别的它是四维横向的也就是说 $k_{\mu}\tilde{D}^{\mu \nu}(k)=0$ 
- Yennie–Fried 规范 $\xi=3$
  $$\tilde{D}^{\mu \nu}(k) = \frac{i}{k^{2}+i\varepsilon}\left[ -g^{\mu \nu} - \frac{2k^{\mu}k^{\nu}}{k^{2}} \right] $$

# Faddeev–Popov 处方与规范量子化的等价性

只用证明轴向规范 $A_{3}=0$ 的情况是成立的即可，选择这个规范是因为在轴向规范下进行规范量子化非常简单。

对于规范场在[[矢量场]]中我们知道，由于 Proca 方程其实真实的自由变量只有 $\{ A^{i} , F^{0i} \}$ ，进一步的在无质量的情况下自由度会进一步的减少，由于我们选择了轴向规范有 $A_{3}=0$ ，以下的 $i,j=1,2$ 
一如既往，关键是拉氏量的一阶形式：
$$\begin{align}
\mathcal{L}_{1st}  & = \frac{1}{4}F^{\mu \nu}F_{\mu \nu} - \frac{1}{2}F^{\mu \nu}(\partial_{\nu}A_{\mu}-\partial_{\mu}A_{\nu}) + \bar{\psi}(i\not{\!\partial}-e\not{\!\!A}-m)\psi \\
&= \frac{1}{4}F_{ij}F^{ij} - \frac{1}{2} F_{ij}(\partial^{i}A^{j}-\partial^{j}A^{i}) + \frac{1}{2}F^{i 3}F_{i 3} + F_{i 3}(\partial^{3}A^{i}) + \frac{1}{2}F_{i 0}F^{i 0} \\
&\quad -F_{i 0}(\partial^{i}A^{0}-\partial^{0}A^{i}) + \frac{1}{2} F_{03}F^{03} + F_{03}(\partial_{3}A_{0}) + \bar{\psi}(i\not{\!\partial}-e\not{\!\!A}-m)\psi
\end{align} $$
独立变量是两个分量 $A_i$​、它们的规范动量 $F_{0i}$​，以及费米场 $\psi$ 和它的规范动量 $\bar{\psi}$​。其他变量——$F_{ij}$​、$F_{i3}$​、$F_{03}$​ 和 $A_0$​——都是约束的，仅通过独立变量及其空间导数定义。$F_{ij}$​ 和 $F_{i3}$​ 是平凡的约束，可直接由 $A_i$​ 的空间导数给出
$$F_{ij} = \partial_{i}A_{j} - \partial_{j}A_{i} $$
$$F_{i 3} = \partial_{i}A_{3} - \partial_{3}A_{i} $$
分量 $F_{03}$ 可由欧拉–拉格朗日方程确定，并进一步的可以确定 $A_{0}$：
$$\partial_{1}F^{10} + \partial_{2}F^{20} + \partial_{3}F^{30} = e\bar{\psi}\gamma^{0}\psi $$
$$F_{03} = \partial_{3} A_{0}$$
通过规范量子化得到的生成泛函为
$$Z = N \int (dA_{1})(dA_{2})(dF^{01})(dF^{02})(d\psi)(d\bar{\psi}) \exp \{ iS_{H} \} $$
其它变量都是约束变量 (除了 $A_{3}$) ，按照[[约束变量与高斯积分]]我们知道可以加回来这些约束变量，它只改变系数 ($N$ 的变化我没细写)
$$\begin{align}
Z & = N \int \prod_{\mu, \nu} (dF_{\mu \nu})(dA_{0})(dA_{1})(dA_{2})(d\psi)(d\bar{\psi}) \exp \{ iS_{1st} \} \\
&= N\int(dA_{0})(dA_{1})(dA_{2})(d\psi)(d\bar{\psi}) \exp \{ iS_{2st} \} \\
&= N\int(dA_{0})(dA_{1})(dA_{2})(dA_{3})(d\psi)(d\bar{\psi}) \delta(A_{3})\exp \{ iS_{2st} \}
\end{align} $$
而这和FP方案完全一致，所以二者等价