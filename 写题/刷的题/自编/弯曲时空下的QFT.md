---
up:
  - "[[写题]]"
related:
  - "[[QFT]]"
  - "[[弯曲时空]]"
  - "[[Unruh效应]]"
  - "[[Rindler坐标]]"
  - "[[做题总结-弯曲时空中的量子场论]]"
date: 2026-05-03
tags:
  - APHO
  - QFT
  - curved-spacetime
  - problem
---

# APHO 模拟题：弯曲时空中的量子场论 —— Unruh 效应

**总分：100 分 | 建议时间：3 小时**

> **命题思路说明：** 本题从普通量子场论出发，逐步引入弯曲时空（Rindler 坐标），最后将两者结合导出 Unruh 效应。每个部分都设有引导性子问题，帮助建立从 flat spacetime QFT 到 curved spacetime QFT 的桥梁。

---

## 第 I 部分：Minkowski 时空中的标量场（35 分）

### 背景

考虑 $1+1$ 维 Minkowski 时空中的**无质量**实标量场 $\phi(t,x)$，度规为 $\eta_{\mu\nu} = \operatorname{diag}(1, -1)$。采用自然单位制 $\hbar = c = k_B = 1$。

---

### I.1 经典理论（6 分）

**(a)** 写出该标量场的 Lagrangian 密度 $\mathcal{L}$，并利用 Euler-Lagrange 方程导出运动方程（即无质量 Klein-Gordon 方程）。
$$\mathcal{L} = \frac{1}{2} \eta^{\mu\nu} \partial_\mu \phi \,\partial_\nu \phi$$

**(b)** 验证：平面波 $\phi(t,x) = f(x \pm t)$（其中 $f$ 为任意光滑函数）是运动方程的解。这体现了无质量场在 $1+1$ 维中的什么特殊性质？

>[!S]-
>$$\mathcal{L} = \frac{1}{2}\eta^{\mu \nu}\partial_{\mu}\phi \partial_{\nu}\phi = \frac{1}{2}(\partial_{0}\phi \partial_{0}\phi - \partial_{1}\phi \partial_{1}\phi) $$
>则
>$$\frac{\partial \mathcal{L}}{\partial \phi}=0 ,\quad \frac{\partial \mathcal{L}}{\partial(\partial_{\mu}\phi)} = \frac{1}{2}\eta^{\mu \nu}\partial_{\nu}\phi $$
>由欧拉-拉格朗日方程得到
>$$\frac{1}{2}\eta^{\mu \nu}\partial_{\mu}\partial_{\nu}\phi = 0 $$
>故得到运动方程
>$$\partial^{2}\phi = 0 $$
>这是一个波动方程，所以考虑到 $u=t+x,v=t-x$ 时
>$$\partial_{0} = \frac{1}{2}\partial_{u} + \frac{1}{2}\partial_{v} ,\quad \partial_{1} = \frac{1}{2}\partial_{u} - \frac{1}{2}\partial_{v} $$
>代入得到
>$$\partial^{2}\phi = (\partial_{0}\partial_{0} - \partial_{1}\partial_{1})\phi = \partial_{u}\partial_{v}\phi = 0 $$
>$$\implies \partial_{v}\phi = f(v) \implies \phi = f(v) + g(u) $$
>即，方程的解为任意函数 $f,g$ 的如下组合
>$$\phi(t,x) = f(t+x) + g(t-x) $$
>这说明无质量标量场在 $1+1$ 维中是波动无衰减的。

---

### I.2 正则量子化（10 分）

定义共轭动量 $\pi(t,x) = \partial_t \phi(t,x)$，施加等时正则对易关系：
$$[\phi(t,x), \pi(t,x')] = i\delta(x-x')$$
$$[\phi(t,x), \phi(t,x')] = [\pi(t,x), \pi(t,x')] = 0$$

**(a)** 将场展开为 Fourier 模（注意 $1+1$ 维且 $m=0$ 时 $\omega_k = |k|$）：
$$\phi(t,x) = \int_{-\infty}^{\infty} \frac{dk}{\sqrt{4\pi |k|}} \left[ a_k e^{-i(|k|t - kx)} + a_k^\dagger e^{i(|k|t - kx)} \right]$$

利用对易关系，推导产生/湮灭算符的对易关系：
$$[a_k, a_{k'}^\dagger] = \delta(k - k'), \quad [a_k, a_{k'}] = [a_k^\dagger, a_{k'}^\dagger] = 0$$

*提示：先写出 $\pi(t,x)$ 的模展开，再代入等时对易关系，利用 $\int dx\, e^{i(k-k')x} = 2\pi\delta(k-k')$。*

>[!S]-
>$$\pi(t,x) = \partial_{0}\phi = \int \frac{dk}{\sqrt{ 4\pi|k| }}\cdot i|k|[ -a_{k}e^{ -i(|k|t-kx) } + a^{\dagger}_{k}e^{ i(|k|t-kx) } ] $$
>考虑到我们的对易关系是等时的，最终结果总可以用时间演化算符平移时间，不妨考虑 $t=0$ 时
>$$[\phi(t,x),\pi(t,y)]=U(t,0)[\phi(0,x),\pi(0,y)]$$
>现在我们已知场的对易关系，考虑得到产生湮灭算符的对易关系，考虑将场傅里叶变换：
>$$\begin{align}\int dx\ \phi(x)e^{ -ikx } & = \int dx \int \frac{dp}{\sqrt{ 4\pi|p| }}[ a_{p}e^{ i(p-k)x } +a_{p}^{\dagger}e^{ -i(p+k)x }] \\ &  = \int \frac{dp}{\sqrt{ 4\pi|p| }} [a_{p}\delta(p-k) + a_{p}^{\dagger}\delta(p+k)]\cdot 2\pi \\ & = \frac{2\pi}{\sqrt{ 4\pi|k| }}[a_{k} + a^{\dagger}_{-k}] \end{align} $$
>$$\begin{align} \int dx\ \pi(y)e^{ -ikx }  & = \int dk \int \frac{idp}{\sqrt{ 4\pi| 1 /p| }} [-a_{p}e^{ i(p-k)x }+a^{\dagger}_{p}e^{ -i(p+k)x }]\\ & = \int \frac{idp}{\sqrt{ 4\pi| 1 /p| }}[-a_{p}\delta(p-k) + a_{p}^{\dagger}\delta(p+k)]\cdot 2\pi \\ & = \frac{2i\pi}{\sqrt{ 4\pi| 1 /k| }}[-a_{k} + a^{\dagger}_{-k}] \end{align} $$
>所以
>$$a_{k} + a_{-k}^{\dagger} = \sqrt{ \frac{|k|}{\pi} }A[\phi],\quad -a_{k} + a_{-k}^{\dagger} = \sqrt{ \frac{1}{\pi|k|} }B[\pi] $$
>$$a_{k} = \frac{1}{2\sqrt{ \pi }}\int dx\ e^{ -ikx }\left[  \sqrt{ |k| }\phi(x) + \frac{i}{\sqrt{ |k| }}\pi(x)  \right] $$
>取共轭得
>$$a^{\dagger}_{k} = \frac{1}{2\sqrt{ \pi }}\int dx\ e^{ ikx }\left[  \sqrt{ |k| }\phi(x) - \frac{i}{\sqrt{ |k| }}\pi(x)  \right] $$
>于是
>$$\begin{align}[a_{k},a_{p}] & = \frac{1}{4} \left( {-\frac{1}{\pi}[ A[\phi],B[\pi] ]-\frac{1}{\pi}[B[\pi],A[\phi]]} \right)\\ &  = -\frac{1}{4\pi}\int dxdy ( [\phi(x)e^{ -ikx },\pi(y)e^{ -ipy }] + [\pi(x)e^{ -ikx },\phi(y)e^{ -ipy }] ) \\ & = -\frac{1}{4\pi} \int dxdy ( e^{ -i(kx+py) }\delta(x-y) - e^{ -i(kx+py) }\delta(x-y) ) = 0 \end{align} $$
>$$\begin{align} [a_{k},a_{p}^{\dagger}] & = \frac{1}{4\pi}\int dxdy \ e^{ i(py-kx) } \left[  \sqrt{ |k| }\phi(x) + \frac{i}{\sqrt{ |k| }}\pi(x) , \sqrt{ |p| }\phi(y) - \frac{i}{\sqrt{ |p| }}\pi(y) \right] \\ & = \frac{1}{4\pi}\int dxdy \ e^{ i(py-kx) }\left[  \sqrt{ \frac{|k|}{|p|} } \delta(x-y) + \sqrt{ \frac{|p|}{|k|} }\delta(x-y) \right] \\ & = \frac{1}{4\pi}\int dx \ e^{ i(p-k)x }\left[ \sqrt{ \frac{|k|}{|p|} } + \sqrt{ \frac{|p|}{|k|} }\right] \\ & = \frac{1}{4\pi} 2\pi\delta(p-k) \left[ \sqrt{ \frac{|k|}{|p|} } + \sqrt{ \frac{|p|}{|k|} }\right] \\ & = \delta(p-k) \end{align} $$

**(b)** 定义 **Minkowski 真空** $|0_M\rangle$：$a_k|0_M\rangle = 0$，$\forall k$。Fock 空间中的单粒子态为 $|k\rangle = a_k^\dagger |0_M\rangle$。证明：
$$\langle k|k'\rangle = \delta(k-k')$$
并解释为何此结果保证了单粒子态的正定性和正交性。

>[!S]-
>由题意
>$$\braket{ k | k' } = \braket{ 0_{M} |a_{k}a_{k'}^{\dagger} |0_{M} }  $$
>由上一题可知
>$$a_{k}a_{k'}^{\dagger} - a_{k'}^{\dagger}a_{k} = \delta(k-k') $$
>所以
>$$\delta(k-k') = \braket{ 0_{M} |\delta(k-k')| 0_{M} } = \braket{ 0_{M} |(a_{k}a_{k'}^{\dagger} - a_{k'}^{\dagger}a_{k})| 0_{M} } = \braket{ 0_{M} |a_{k}a_{k'}^{\dagger} |0_{M} } = \braket{ k | k' } $$


---

### I.3 两点函数与因果关系（9 分）

**(a)** 计算 Minkowski 真空中的 **Wightman 函数**（正频两点函数）：
$$G^+(x; x') = \langle 0_M | \phi(t,x) \phi(t',x') | 0_M \rangle$$

在 $1+1$ 维无质量情况下，结果为：
$$G^+(x; x') = -\frac{1}{4\pi} \ln\left[-( \Delta t - i\epsilon)^2 + (\Delta x)^2\right] + \text{常数}$$
其中 $\Delta t = t - t'$，$\Delta x = x - x'$，$\epsilon \to 0^+$ 为正规化参数。

*提示：先代入模展开，利用 $\langle 0_M|a_k a_{k'}^\dagger|0_M\rangle = \delta(k-k')$，再计算积分。*

>[!S]-
>考虑将场算符傅里叶展开
>$$\begin{align} G^{+}(x;x') & = \int \frac{dkdk'}{4\pi\sqrt{ |kk'| }} \braket{ 0_{M} |a_{k}a_{k'}^{\dagger}| 0_{M} }e^{ i((|k|t-|k'|t') + kx-k'y) } \\ & = \int \frac{dkdk'}{4\pi\sqrt{ |kk'| }} \delta(k-k') e^{ i(|k|t-|k'|t' + kx-k'y) } \\ & = \int \frac{dk}{4\pi|k|} e^{ ik(x-y) } e^{ i|k|(t-t') } \end{align} $$
>对于这个积分，考虑留数定理，显然有极点 $k=0$ 在无穷远处函数震荡衰减，取上半平面的半圆围道，则
>$$G^{+}(x,x') = \frac{2\pi i}{4\pi}\text{Res}\left(  \frac{1}{|k|}e^{ ik(x-y) }e^{ i|k|(t-t') } \right) = -\frac{1}{4\pi} \ln[ (x-y)^{2} - (t-t')^{2} ] $$


**(b)** 计算对易子 $[\phi(t,x), \phi(t',x')]$，证明当两点**类空分离**（即 $|\Delta x| > |\Delta t|$）时，对易子为零。这一结果体现了什么物理原理？

$$\phi(t,x) = \int_{-\infty}^{\infty} \frac{dk}{\sqrt{4\pi |k|}} \left[ a_k e^{-i(|k|t - kx)} + a_k^\dagger e^{i(|k|t - kx)} \right] $$

>[!S]-
>考虑场的傅里叶展开得到
>$$\begin{align} [\phi(t,x),\phi(t',x')] & = \int \frac{dkdk'}{4\pi \sqrt{ |kk'| }} [ a_{k}e^{ ikx-i|k|t }+a_{k}^{\dagger}e^{ -ikx+i|k|t } , a_{k'}e^{ ik'x'+i|k'|t' }+a_{k'}^{\dagger}e^{ -ik'x'+i|k'|t' } ] \\ & = \int\dots\delta(k-k')[ e^{ i(kx-k'x') }e^{ -i(|k|t-|k'|t') } - e^{ -i(kx-k'x') }e^{ i(|k|t-|k'|t') } ] \\ & = \int \frac{dk}{4\pi|k|}2i\sin[ k\Delta x - |k|\Delta t ]\end{align} $$
>对于积分 $\int \frac{dk}{|k|}\sin (k\Delta x-|k|\Delta t)$ 我们考虑留数定理，其有极点 $k=0$ 积分在无穷远处震荡衰减
>$$\int_{0}^{+\infty} \frac{dk}{k}\sin(kx - kt) + \int_{-\infty}^{0} \frac{dk}{-k}\sin(kx+kt) = \frac{\pi}{2}\text{sgn}(x-t) - \frac{\pi}{2}\text{sgn}(x+t) $$
>$$[\phi(t,x),\phi(t',x')] = \frac{i}{4}[ \text{sgn}[\Delta x-\Delta t] - \text{sgn}[\Delta x+\Delta t] ] $$
>当类空时
>$$[\phi(t,x),\phi(t',x')] = \frac{i}{4}[ 1-1 ] =0 $$
>这说明当两点类空时，其场算符无关，这体现了相对论因果性：这两点在各自光锥之外，无法相互影响。

---

### I.4 能量-动量张量与真空能（10 分）

**(a)** 标量场的能量-动量张量为：
$$T_{\mu\nu} = \partial_\mu \phi\, \partial_\nu \phi - \frac{1}{2}\eta_{\mu\nu} (\partial^\rho \phi\, \partial_\rho \phi)$$
计算 Hamiltonian 密度 $\mathcal{H} = T_{00}$，并将总 Hamiltonian $H = \int dx\, T_{00}$ 用 $a_k, a_k^\dagger$ 表达。证明：
$$H = \int_{-\infty}^{\infty} dk\, |k| \left( a_k^\dagger a_k + \frac{1}{2}\delta(0) \right)$$

>[!S]-
>$$\mathcal{H} = T_{00} = \partial_{0}\phi \partial_{0}\phi - \frac{1}{2}\partial_{0}\phi \partial_{0}\phi + \frac{1}{2}\partial_{1}\phi \partial_{1}\phi = \frac{1}{2}\pi \pi + \frac{1}{2}\nabla \phi \cdot\nabla \phi $$
>考虑将场傅里叶展开得到
>$$\pi(x,t) = \frac{i}{\sqrt{ 4\pi }} \int dk\sqrt{ |k| }[ -a_{k}e^{ -i(|k|t-kx) } + a^{\dagger}_{k}e^{ i(|k|t-kx) } ] $$
>$$\partial_{x}\phi = \frac{i}{\sqrt{ 4\pi }} \int dk\sqrt{ |k| }\left[ a_k e^{-i(|k|t - kx)} + a_k^\dagger e^{i(|k|t - kx)} \right]\text{sgn}(k) $$
>不妨令 $t=0$ 最后结果使用时间演化算符换到任意时间上即可
>$$\begin{align}\int dx\ \pi^{2} & = -\int dx \int \frac{dkdp}{4\pi}\sqrt{ |kp| }[-a_{k}e^{ ikx } + a_{k}^{\dagger}e^{ -ikx } ][-a_{p}e^{ ipx } + a_{p}^{\dagger}e^{ ipx }] \\ & = -\int \frac{dkdp}{4\pi}\sqrt{ |kp| } \int dx [ a_{k}a_{p}e^{ i(k+p)x } - a_{k}a_{p}^{\dagger} ]e^{ i(k-p)x } - a_{k}^{\dagger}e^{ i(p-k)x } + a^{\dagger}_{k}a^{\dagger}_{p}e^{ -i(k+p)x }\\ & = -\int \frac{dkdp}{4\pi}\sqrt{ |kp| }[ a_{k}a_{p}\delta(k+p) - a_{k}a^{\dagger}_{p}\delta(k-p) - a^{\dagger}_{k}a_{p}\delta(p-k) + a^{\dagger}_{k}a^{\dagger}_{p}\delta(k+p) ]2\pi \\ & = -\int \frac{dk}{2}|k|[a_{k}a_{-k} - a_{k}a^{\dagger}_{k}-a^{\dagger}_{k}a_{k} + a^{\dagger}_{k}a^{\dagger}_{-k}]\end{align} $$
>同理
>$$\int dx (\partial_{x}\phi)^{2} = \frac{1}{2}\int dk|k|(a_{k}a_{-k} + a_{k}a^{\dagger}_{k} + a_{k}^{\dagger}a_{k} + a^{\dagger}_{k}a^{\dagger}_{-k}) $$
>于是
>$$H = \frac{1}{2}\int dk|k|2(a_{k}a^{\dagger}_{k} + a^{\dagger}_{k}a_{k}) = \int dk|k| (a^{\dagger}_{k}a_{k} + \frac{1}{2}\delta(k-k)) $$


**(b)** 解释 $\frac{1}{2}\delta(0)$ 项的来源。为什么它代表真空能的紫外发散？

>[!S]-
>$$\frac{1}{2}\delta(0) = \frac{1}{2}\int \frac{dx}{2\pi} $$
>来自无穷空间体积，$\int dk|k|$ 在大 $k$ 发散是紫外灾难

**(c)** 引入**正规序**（normal ordering）$:H:$：将所有产生算符移到湮灭算符的左边。证明 $:H:|0_M\rangle = 0$，且对于任意单粒子态 $|k\rangle$，有 $:H:|k\rangle = |k|\,|k\rangle$。

*提示：正规序相当于丢弃真空零点能，这是 flat spacetime QFT 中处理真空发散的标准方法。但在 curved spacetime 中，真空能将具有物理效应。*

>[!S]-
>$$:H:\ket{0_{M}} = \frac{1}{2}\int dk|k| :(a_{k}a^{\dagger}_{k} + a^{\dagger}_{k}a_{k}):\ket{0_{M}} = \int dk|k|a^{\dagger}_{k}a_{k}\ket{0_{M}} = 0 $$
>$$:H:\ket{k} = \int dk|k|a^{\dagger}_{k}a_{k}\ket{k} = |k|\ket{k}  $$


---

## 第 II 部分：Rindler 时空 —— 匀加速观测者（30 分）

### 背景

Minkowski 时空中，一个匀加速观测者的世界线是双曲线。描述这类观测者最自然的坐标系是 **Rindler 坐标系**。考虑右 Rindler 楔形区域（$x > |t|$），引入 Rindler 坐标 $(\eta, \xi)$：
$$t = \xi \sinh \eta, \quad x = \xi \cosh \eta$$
其中 $\xi > 0$，$-\infty < \eta < \infty$。

---

### II.1 几何基础（8 分）

**(a)** 写出 Minkowski 线元 $ds^2 = dt^2 - dx^2$ 在 Rindler 坐标下的表达式：
$$ds^2 = \xi^2 d\eta^2 - d\xi^2$$
*提示：直接计算 $dt = \sinh\eta\, d\xi + \xi\cosh\eta\, d\eta$ 等。*

>[!S]-
>$$dt = \sinh \eta d\xi + \xi \cosh \eta d \eta ,\quad dx = \cosh \eta d\xi + \xi \sinh \eta d \eta $$
>$$\begin{align} ds^{2}  & = dt^{2} - dx^{2}\\ & = \sinh ^{2}\eta d\xi^{2} + \xi^{2}\cosh ^{2}\eta d \eta^{2} + 2\xi \sinh \eta \cosh \eta d\xi d \eta \\ & \quad- \cosh ^{2}\eta d\xi^{2} - \xi^{2}\sinh ^{2}\eta d \eta^{2} - 2\xi \sinh \eta \cosh \eta d\xi d \eta \\ & = \xi^{2}d \eta^{2} - d\xi^{2} \end{align} $$

**(b)** Rindler 度规与 Minkowski 度规 **共形等价** 吗？即是否存在函数 $\Omega^2(\xi)$ 使得 $ds^2 = \Omega^2(\xi)(d\eta^2 - d\rho^2)$ 对某个新空间坐标 $\rho$ 成立？如果存在，求出 $\rho(\xi)$ 和 $\Omega^2(\rho)$；如果不存在，解释原因，并说明在什么近似条件下可以视为共形。

>[!S]-
>假设存在这样的函数 $\Omega(\xi)$ 和 $\rho=\rho(\eta,\xi)$ 则
>$$d\rho = \frac{\partial \rho}{\partial \eta}d \eta + \frac{\partial \rho}{\partial \xi}d\xi ,\quad d\rho^{2} = \left( \frac{\partial \rho}{\partial \eta} \right)^{2}d \eta^{2} + \left( \frac{\partial \rho}{\partial \xi} \right)^{2}d\xi^{2} + 2\frac{\partial \rho}{\partial \eta}\cdot \frac{\partial \rho}{\partial \xi}d \eta d\xi $$
>$$\Omega^{2}(d \eta^{2} - d\rho^{2}) = \Omega^{2}\left( 1- \left( \frac{\partial \rho}{\partial \eta} \right)^{2} \right)d \eta^{2} - \Omega^{2}\left( \frac{\partial \rho}{\partial \xi} \right)^{2}d\xi^{2} - 2\Omega^{2}\frac{\partial \rho}{\partial \eta}\cdot \frac{\partial \rho}{\partial \xi}d \eta d\xi $$
>对比系数得
>$$\begin{gather} \Omega^{2}\left( 1- \left( \frac{\partial \rho}{\partial \eta} \right)^{2} \right) = \xi^{2} \\ \Omega^{2}\left( \frac{\partial \rho}{\partial \xi} \right)^{2} = 1 \\ \Omega^{2}\frac{\partial \rho}{\partial \eta}\cdot \frac{\partial \rho}{\partial \xi} = 0 \end{gather} $$
>第三个方程说明 $\rho$ 至多是 $\eta,\xi$ 的一次多项式，不妨设 $\rho=a\eta+b\xi$ 则
>$$\begin{gather} \Omega^{2}\left( 1- a^{2} \right) = \xi^{2} \\ \Omega^{2}b^{2} = 1  \end{gather}  $$
>第一个说明 $\Omega \sim \xi^{-1}$ 而第二个说明 $\Omega=Const$ 矛盾，故这两个度规不是共形的。在 $\xi$ 很大时，$\xi^{-1}$ 近似不变，此时方程可以认为是相容的，即可以视为是共形的。

**(c)** 证明 $\partial_\eta = t\partial_x + x\partial_t$ 是 Minkowski 时空中的一个 **Killing 矢量场**。对于 Rindler 观测者而言，这个 Killing 矢量的物理意义是什么？

>[!S]-
>在 $(t,x)$ 坐标系下
>$$\partial_{\eta}g_{tt} = (t\partial_{x} + x\partial_{t})1 = 0,\quad \partial_{\eta}g_{x x} = (t\partial_{x} + x\partial_{t})(-1) = 0 $$
>其它项也是零，这说明 $\partial_{\eta}$ 确实是一个 killing 矢量场。对于 Rindler 观测者而言，这是说明，在沿着时间方向上，时空结构不变，对应着该坐标系中的能量守恒。

---

### II.2 匀加速观测者（8 分）

**(a)** 考虑一条 $\xi = \xi_0$（常数）的曲线。写出该曲线的参数方程 $t(\eta), x(\eta)$，证明它描述了一个匀加速观测者的世界线。

>[!S]-
>由
>$$t = \xi \sinh \eta, \quad x = \xi \cosh \eta $$
>知
>$$t(\eta) = \xi_{0}\sinh \eta,\quad x(\eta)=\xi_{0}\cosh \eta $$
>于是
>$$ds^{2} = \xi_{0}^{2}d \eta^{2} \implies ds := \xi_{0}d \eta $$
>$$u^{t} = \frac{dt}{ds} = \cosh \eta ,\quad u^{x} = \frac{dx}{ds} = \sinh \eta $$
>$$a^{t} = \frac{du^{t}}{ds} = \frac{1}{\xi_{0}}\sinh \eta ,\quad a^{x} = \frac{du^{x}}{ds} = \frac{1}{\xi_{0}}\cosh \eta $$
>所以
>$$a^{\mu}a_{\mu} = -\frac{1}{\xi_{0}^{2}} $$
>取观测者静止系，则三维加速度大小 $a=\frac{1}{\xi_{0}}$ 所以它描述了一个匀加速观测者的世界线

**(b)** 计算该观测者的**固有加速度** $a$（即在本征参考系中测得的加速度的大小）。证明 $a = 1/\xi_0$。*提示：计算四加速度 $a^\mu = d^2 x^\mu / d\tau^2$，其中 $\tau$ 为本征时。*

>[!S]-
>见上

**(c)** 在 $x$-$t$ 平面上画出右 Rindler 楔形，标明以下特征：
- Rindler 视界（horizon）：$x = |t|$（即 $\xi \to 0$）
- 两条典型的匀加速世界线（$\xi_1, \xi_2$ 为常数）
- 两条 $\eta$ 为常数的直线（代表"空间切片"）
- 与 Minkowski 坐标原点的关系

*只需定性描述即可。*

>[!S]-
>$$\eta\text{ 常值线 } = \text{ 过原点的直线(辐射线) } $$
>$$\xi\text{ 常值线 } = \text{ 双曲线 } $$
>$$\text{ 视界 } : x=\pm t $$

**(d)** 一个静止于 $\xi_0$ 的观测者，其本征时 $\tau$ 与 Rindler 时间 $\eta$ 满足 $\tau = \xi_0 \eta$。若该观测者携带一个频率为 $\omega$ 的光源（共振频率在其本征系中测量），在无穷远处的 Minkowski 观测者测量该光源的频率为 $\omega'$。计算 $\omega'$ 与 $\omega$ 的关系，对应什么经典物理效应？

>[]-
>?

---

### II.3 经典场方程（8 分）

**(a)** 在弯曲时空中，无质量标量场的作用量为：
$$S = -\frac{1}{2} \int d^2 x \sqrt{-g}\, g^{\mu\nu} \partial_\mu \phi\, \partial_\nu \phi$$
在 Rindler 度规下，写出显式的作用量表达式，并导出运动方程：
$$\left( -\frac{1}{\xi^2} \partial_\eta^2 + \frac{1}{\xi} \partial_\xi (\xi \partial_\xi) \right) \phi = 0$$

*提示：$g = \det(g_{\mu\nu}) = -\xi^2$，$\sqrt{-g} = \xi$。*

>[!S]-
>在 Rindler 度规下
>$$g_{\mu \nu} = \text{diag}(\xi^{2},-1) $$
>$$g = -\xi^{2} ,\quad \sqrt{ -g } = \xi $$
>于是
>$$S = -\frac{1}{2} \int d \eta d\xi\ (\xi^{3}(\partial_{\eta}\phi)^{2} - \xi(\partial_{\xi}\phi)^{2}) $$
>故拉式量为
>$$\mathcal{L} = -\frac{1}{2}(\xi^{3}(\partial_{\eta}\phi)^{2} - \xi(\partial_{\xi}\phi)^{2}) $$
>$$\frac{\partial \mathcal{L}}{\partial \phi} = 0 ,\quad \frac{\partial \mathcal{L}}{\partial(\partial_{\eta}\phi)} = -\xi^{3}\partial_{\eta}\phi ,\quad \frac{\partial \mathcal{L}}{\partial(\partial_{\xi}\phi)} = -\xi \partial_{\xi}\phi $$
>由欧拉-拉格朗日方程得到
>$$\partial_{\eta}(\xi^{3}\partial_{\eta}\phi) + \partial_{\xi}(\xi \partial_{\xi}\phi) =0 $$
>即
>$$\left( -\frac{1}{\xi^2} \partial_\eta^2 + \frac{1}{\xi} \partial_\xi (\xi \partial_\xi) \right) \phi = 0 $$

**(b)** 引入新坐标 $\rho = \ln \xi$（$-\infty < \rho < \infty$），证明运动方程化为：
$$\left( -\partial_\eta^2 + \partial_\rho^2 \right) \phi = 0$$
这恰好是 $(\eta, \rho)$ 坐标下的标准波动方程！为什么 Rindler 时空中的场方程可以化为如此简单的形式？这体现了什么几何性质？

>[!S]-
>令 $\rho=\ln \xi$ 得到 $\partial_{\xi}=\frac{\partial }{\partial e^{ \rho }}=e^{ -\rho }\partial_{\rho}$ 于是由上衣问运动方程的微分算子变为
>$$\begin{align} LHS & = -e^{ -2\rho }\partial_{\eta}^{2} + e^{ -\rho }\cdot e^{ -\rho }{\partial_{\rho}(e^{ \rho }\cdot e^{ -\rho }\partial_{\rho})} \\ & = -e^{ -2\rho }\partial_{\eta}^{2} + e^{ -2\rho }\partial_{\rho}^{2} \end{align} $$
>于是运动方程就是
>$$\left( -\partial_\eta^2 + \partial_\rho^2 \right) \phi = 0 $$
>着说明了 Rindler 时空本质是平直时空

**(c)** 写出正频模式解（相对于 Rindler 时间 $\eta$）：
$$\phi_\Omega(\eta, \rho) \propto e^{-i\Omega \eta \pm i\Omega \rho}, \quad \Omega > 0$$
验证该解满足运动方程，并解释为何在 Rindler 坐标中只能有 $\Omega > 0$ 的正频解（相对于原 Minkowski 坐标中的 $|k|$）。

>[!S]-
>将 $e^{ -i\Omega \eta\pm i\Omega \rho }$ 代入波动方程
>$$(-\partial_{\eta}^{2} + \partial_{\rho}^{2})e^{ -i\Omega \eta\pm i\Omega \rho } = (\Omega^{2} - \Omega^{2})e^{ -i\Omega \eta\pm i\Omega \rho } = 0 $$
>

因为 $\rho=\ln \xi$ 是无界的 $\rho \in \mathbb{R}$，Rindler 正频是相对于 $\eta$ 的 $e^{ -i\Omega \eta }$；而 Minkowski 中 $k$ 遍历 $\mathbb{R}$ 是因为 $e^{ ikx }$ 同时编码了左右行波。Rindler 在左右行波已用 $R /L$ 上标显式分离，$\Omega$ 只管频率大小。 

---

### II.4 Rindler 场的量子化（6 分）

**(a)** 在 Rindler 坐标的 $(\eta, \rho)$ 坐标系中，场 $\phi(\eta, \rho)$ 看起来就是普通 $1+1$ 维 Minkowski 空间中的无质量标量场！因此可以独立地进行量子化。写出模展开：
$$\phi(\eta, \rho) = \int_{0}^{\infty} \frac{d\Omega}{\sqrt{4\pi \Omega}} \left[ b_\Omega^R e^{-i\Omega(\eta - \rho)} + b_\Omega^{R\dagger} e^{i\Omega(\eta - \rho)} + b_\Omega^L e^{-i\Omega(\eta + \rho)} + b_\Omega^{L\dagger} e^{i\Omega(\eta + \rho)} \right]$$

定义 **Rindler 真空** $|0_R\rangle$ 满足 $b_\Omega^R |0_R\rangle = b_\Omega^L |0_R\rangle = 0$。

>[!S]-
>验证其满足波动方程
>$$\partial_{\eta }^{2}\phi = \int_{0}^{\infty} \frac{d\Omega}{\sqrt{4\pi \Omega}} \left[ b_\Omega^R e^{-i\Omega(\eta - \rho)} + b_\Omega^{R\dagger} e^{i\Omega(\eta - \rho)} + b_\Omega^L e^{-i\Omega(\eta + \rho)} + b_\Omega^{L\dagger} e^{i\Omega(\eta + \rho)} \right]\cdot(-\Omega^{2}) $$
>$$\partial_{\xi}^{2}\phi = \int_{0}^{\infty} \frac{d\Omega}{\sqrt{4\pi \Omega}} \left[ b_\Omega^R e^{-i\Omega(\eta - \rho)} + b_\Omega^{R\dagger} e^{i\Omega(\eta - \rho)} + b_\Omega^L e^{-i\Omega(\eta + \rho)} + b_\Omega^{L\dagger} e^{i\Omega(\eta + \rho)} \right]\cdot(-\Omega^{2})  $$
>所以
>$$(-\partial_{\eta}^{2} + \partial_{\rho}^{2})\phi = 0 $$
>对易关系：
>$$\begin{gather} \phi(\eta, \rho) = \int_{0}^{\infty} \frac{d\Omega}{\sqrt{4\pi \Omega}} \left[ b_\Omega^R e^{-i\Omega(\eta - \rho)} + b_\Omega^{R\dagger} e^{i\Omega(\eta - \rho)} + b_\Omega^L e^{-i\Omega(\eta + \rho)} + b_\Omega^{L\dagger} e^{i\Omega(\eta + \rho)} \right] \\ \pi(\eta,\rho) = \int_{0}^{\infty} \frac{i\Omega d\Omega}{\sqrt{4\pi \Omega}} \left[ -b_\Omega^R e^{-i\Omega(\eta - \rho)} + b_\Omega^{R\dagger} e^{i\Omega(\eta - \rho)} -b_\Omega^L e^{-i\Omega(\eta + \rho)} + b_\Omega^{L\dagger} e^{i\Omega(\eta + \rho)} \right] \end{gather} $$
>$$\begin{gather} b^{R}_{\Omega} = \int d\rho e^{ -i\Omega \rho }\left[  \sqrt{ \frac{\Omega}{4\pi} }\phi(0,\rho) + \frac{i}{\sqrt{ 4\pi \Omega }} \pi(0,\rho) \right] \\ b^{R\dagger}_{\Omega} = \int d\rho e^{ +i\Omega \rho }\left[  \sqrt{ \frac{\Omega}{4\pi} }\phi(0,\rho) - \frac{i}{\sqrt{ 4\pi \Omega }} \pi(0,\rho) \right] \\ b^{L}_{\Omega} = \int d\rho e^{ +i\Omega \rho }\left[  \sqrt{ \frac{\Omega}{4\pi} }\phi(0,\rho) + \frac{i}{\sqrt{ 4\pi \Omega }} \pi(0,\rho) \right] \\ b^{L\dagger}_{\Omega} = \int d\rho e^{ -i\Omega \rho }\left[  \sqrt{ \frac{\Omega}{4\pi} }\phi(0,\rho) - \frac{i}{\sqrt{ 4\pi \Omega }} \pi(0,\rho) \right]  \end{gather} $$
>于是可以验证
>$$[b^{R}_{\Omega} , b^{R\dagger}_{\Omega'}] = [b^{L}_{\Omega},b^{L\dagger}_{\Omega'}] = \delta(\Omega-\Omega') , \text{ 其它对易子都是零} $$
>所以 $b^{R}_{\Omega},b^{L}_{\Omega}$ 相容，令态 $\ket{0_{R}}$ 是它们的共同本征态，且
>$$b^{R}_{\Omega}\ket{0_{R}} =b^{L}_{\Omega}\ket{0_{R}} =0 $$

**(b)** 关键问题：$|0_R\rangle$ 和 $|0_M\rangle$ 是否是同一个量子态？请从物理直觉出发给出理由。*提示：考虑两个真空的定义依赖于不同的时间坐标（$t$ vs $\eta$），从而正频分解的标准不同。*

>[!S]-
>这两个真空态不应该一样，因为一个是静止参考系，而一个是匀加速运动的参考系，两个系的能量定义都不一样，又怎么能说明二者的态都是时空的最低能量态。

Minkowsi 正频由 $\partial_{t}$ 定义，而 Rindler 正频由 $\partial_{\eta}$ 定义，而 $\partial_{\eta}=t\partial_{x} + x\partial_{\eta}$ 是 Minkowski 的 boost 生成元，这导致了 Minkowski 正频模 $e^{ -i|k|t+ikx }$ 在 Rindler 坐标中同时含有 $e^{ -i\Omega \eta }$ 和 $e^{ i\Omega \eta }$ 分量。

---

## 第 III 部分：Bogoliubov 变换与 Unruh 效应（35 分）

### 背景

同一个量子场 $\phi$ 可以用两套不同的产生/湮灭算符展开。这两套算符之间通过 **Bogoliubov 变换** 联系。正是因为 $\beta$ 系数非零，一个真空在另一个参考系中会表现为热态。

---

### III.1 Bogoliubov 变换（10 分）

**(a)** 两套算符之间的一般关系为：
$$b_\Omega = \int_0^\infty dk \left[ \alpha_{\Omega k}\, a_k + \beta_{\Omega k}\, a_k^\dagger \right]$$
解释 $\alpha_{\Omega k}$ 和 $\beta_{\Omega k}$ 的物理意义。证明 Bogoliubov 系数的归一化条件：
$$\int_0^\infty dk \left[ |\alpha_{\Omega k}|^2 - |\beta_{\Omega k}|^2 \right] = 1$$
*提示：利用 $[b_\Omega, b_{\Omega'}^\dagger] = \delta(\Omega - \Omega')$。*

>[!S]-
>$\alpha_{\Omega k}$ 就是说 Minkovsk 度规中的一个正频 $k$ 的粒子在 Rindler 度规下占能量为 $\Omega$ 的粒子的比例，$\beta_{\Omega k}$ 同理说 Minkowski 反粒子模 $a^{\dagger}_{k}$ 混入 Rindler 粒子湮灭算符 $b_{\Omega}$ 的幅度。
>
>考虑到
>$$\begin{align} [b_{\Omega},b^{\dagger}_{\Omega'}] &  = \int dkdp [ \alpha_{\Omega k}a_{k} + \beta_{\Omega k}a^{\dagger}_{k} , \alpha_{\Omega'p}^{*}a_{p}^{\dagger} + \beta_{\Omega'p}^{*}a_{p} ] \\ & = \int dkdp ( \alpha_{\Omega k}\alpha_{\Omega 'p}[a_{k},a^{\dagger}_{p}] + \beta_{\Omega k}\beta_{\Omega'p}[a^{\dagger}_{k},a_{p}] ) \\ & = \int dkdp ( \alpha_{\Omega k}\alpha_{\Omega 'p}^{*}\delta(k-p) - \beta_{\Omega k}\beta_{\Omega'p}^{*}\delta(p-k) ) \\ & = \int_{0}^{\infty} dk (\alpha_{\Omega k}\alpha_{\Omega'k}^{*} - \beta_{\Omega k}\beta _{\Omega'k}^{*}) \\ & = \delta(\Omega-\Omega') \end{align}$$
>所以
>$$\int_0^\infty dk \left[ |\alpha_{\Omega k}|^2 - |\beta_{\Omega k}|^2 \right] = 1$$

**(b)** 利用上述 Bogoliubov 变换，计算 Minkowski 真空中 Rindler 粒子数的期望值：
$$N_\Omega = \langle 0_M | b_\Omega^\dagger b_\Omega | 0_M \rangle = \int_0^\infty dk\, |\beta_{\Omega k}|^2$$
证明：当且仅当所有 $\beta_{\Omega k} = 0$ 时，$N_\Omega = 0$——即两个真空等价。一般情况下 $N_\Omega \neq 0$。

>[!S]
>$$b_{\Omega}\ket{0_{M}} = \int dk(\alpha_{\Omega k}a_{k}\ket{0_{M}} + \beta_{\Omega k}a^{\dagger}_{k}\ket{0_{M}}) = \int dk\ \beta_{\Omega k}a^{\dagger}_{k}\ket{0_{M}}  $$
>故
>$$\braket{ 0_{M} |b^{\dagger}_{\Omega}b_{\Omega}| 0_{M} } = \int dkdp\ \beta_{\Omega k}\beta_{\Omega p}^{*} \braket{ 0_{M} |a_{p}a^{\dagger}_{k}| 0_{M} } = \int dk\ \beta_{\Omega k}\beta_{\Omega k}^{*} $$
>显然当 $\beta_{\Omega k}=0$ 时 $N_{\Omega}=0$，而当 $N_{\Omega}=0$ 时考虑到 $|\beta_{\Omega k}|^{2}\geq 0$ 故只能有 $|\beta_{\Omega k}|^{2}\equiv 0$ 即 $\beta_{\Omega k}=0$ 



---

### III.2 Bogoliubov 系数的计算（8 分）

**(a)** 为了计算 $\beta_{\Omega k}$，我们可以利用：Minkowski 正频模 $u_k(t,x)$ 构成一组完备基，Rindler 正频模 $v_\Omega(\eta, \rho)$ 也构成一组完备基。Bogoliubov 系数由两者的内积给出：
$$\beta_{\Omega k} = -(v_\Omega, u_k^*)$$
其中 Klein-Gordon 内积定义为：
$$(\phi_1, \phi_2) = -i \int_\Sigma d\Sigma^\mu \left( \phi_1 \partial_\mu \phi_2^* - \phi_2^* \partial_\mu \phi_1 \right)$$
$\Sigma$ 为类空超曲面。这里不要求完整计算，但请论证：**为什么 $\beta_{\Omega k} \neq 0$？** 

*提示：Minkowski 正频模 $u_k \propto e^{-i|k|t + ikx}$ 在 Rindler 坐标中不再是纯正频，因为它同时含有 $e^{-i\Omega\eta}$ 和 $e^{+i\Omega\eta}$ 的 Fourier 分量。类比：一个在时域中严格正频的信号，在做坐标变换后可能包含负频成分。*

>[]
>提示即为解答？

**(b)** 在 Rindler 楔形区域（$x > |t|$）和左 Rindler 楔形（$x < -|t|$）中，Minkowski 正频模的行为不同。事实上，Minkowski 真空 $|0_M\rangle$ 的完整描述需要同时考虑左右两个 Rindler 楔形。利用这一事实，完整的 Bogoliubov 变换应涉及左右两组 Rindler 算符。写出完整的 Bogoliubov 变换形式：
$$a_k = \int_0^\infty d\Omega \left[ \alpha_{\Omega k}^* b_\Omega^R - \beta_{\Omega k}^* b_\Omega^{R\dagger} + \alpha_{\Omega k}^* b_\Omega^L - \beta_{\Omega k}^* b_\Omega^{L\dagger} \right]$$
并解释为什么需要引入左右两组算符。

>[!S]-
>1. **时空覆盖的几何差异**  
   Minkowski 坐标 $(t,x)$ 覆盖整个二维时空，而 Rindler 坐标 $(\eta,\rho)$ 只分别覆盖**右楔形**（$x>|t|$）和**左楔形**（$x<-|t|$）。这两片区域被视界 $x=\pm t$ 分隔，彼此类空，因果独立。一个全局定义的 Minkowski 正频模 $u_k \propto e^{-i|k|t + ikx}$ 在左右两个楔形上都有非零的值，因此仅靠单一区域的 Rindler 模无法完整展开一个全局的场模式。
>
>2. **场算符的完备性**  
   场的 Minkowski 展开为对全空间的积分，而 Rindler 展开则需要同时在左右楔形上进行。等时面 $\Sigma$ 由左右两半组成，场的正交模分解必须包含来自两个区域的独立自由度。左右 Rindler 算符 $b_\Omega^R$ 和 $b_\Omega^L$ 分别对应右楔形与左楔形的正频模，它们的代数是相互独立的（对易子为零）。要把一个 Minkowski 湮灭算符用 Rindler 算符表示，必然要同时用到两者的产生湮灭算符，并保证对易关系的自洽。
>
>3. **量子态的纠缠结构**  
   Minkowski 真空 $|0_M\rangle$ 在 Rindler 福克空间中并不是简单的右楔形真空，而是一个**左右模纠缠的热态**（Thermofield Double State 的连续版本）。具体形式为
   $$|0_M\rangle \propto \exp\left( \int d\Omega\, e^{-\pi\Omega} b_\Omega^{R\dagger} b_\Omega^{L\dagger} \right) |0_R\rangle$$
   其中 $|0_R\rangle$ 是左右 Rindler 真空的张量积。这种纠缠正是导致 Unruh 效应的根源：求迹掉左楔形自由度后，右 Rindler 区域的约化密度矩阵是热态。如果只使用右楔形算符，无法描述这种关联，也无法得到正确的 Bogoliubov 变换归一化条件。

---

### III.3 Unruh 温度（10 分）

**(a)** 经过解析延拓和围道积分（此处不要求计算细节），无质量标量场的关键结果是：
$$|\beta_{\Omega k}|^2 = \frac{1}{e^{2\pi \Omega / a} - 1} \cdot \delta(\Omega - k) \cdot \text{(体积因子)}$$
其中 $a$ 为对应 Rindler 观测者的固有加速度。因此：
$$N_\Omega = \langle 0_M | b_\Omega^\dagger b_\Omega | 0_M \rangle = \frac{1}{e^{2\pi \Omega / a} - 1} \cdot \delta(0)$$
其中 $\delta(0)$ 对应于无穷大空间体积，$\delta(0)^{-1} N_\Omega$ 即为粒子数密度。

**(b)** 上述粒子数分布 $n_\Omega$ 满足什么统计分布？与温度为 $T$ 的黑体辐射的 Planck 分布做比较：
$$n(\omega) = \frac{1}{e^{\omega / T} - 1}$$
导出 **Unruh 温度**：
$$T_U = \frac{a}{2\pi}$$
（恢复单位后：$T_U = \frac{\hbar a}{2\pi k_B c}$）

>[!S]-
>显然
>$$N(\Omega) \propto \frac{1}{\exp(C\Omega) - 1} $$
>这是 Planck 分布，对比可以知道
>$$\frac{1}{kT} = \frac{2\pi}{a} \implies T_{U} = \frac{a}{2\pi} $$

**(c)** 数值估算（4 分）：
- 取 $a = 9.8\text{ m/s}^2$（地球表面重力加速度），计算 $T_U$（单位：K）。
- 取 $a = 10^{21}\text{ m/s}^2$（强激光场中电子的典型加速度），计算 $T_U$（单位：K）。
- 讨论：为什么日常生活中感受不到 Unruh 效应？

*(恢复单位常数：$\hbar = 1.05 \times 10^{-34}\text{ J·s}$，$k_B = 1.38 \times 10^{-23}\text{ J/K}$，$c = 3.0 \times 10^8\text{ m/s}$)*

>[!S]-
>地球表面重力加速度下
>$$T_{U} = \frac{1.05\times 10^{-34}\times9.8}{2\pi \times 1.38\times 10^{-23}\times 3.0\times 10^{8}} = 3.956\times 10^{-20}\text{K} $$
>在 $a=10^{21}\text{m/s}^{2}$ 下
>$$T_{U} = \frac{1.05\times 10^{-34}\times 10^{21}}{2\pi \times 1.38\times 10^{-23}\times 3.0\times 10^{8}} = 4.036\text{K} $$
>计算可知在 $a=10^{21}\text{m/s}^{2}$ 的量级下，才会产生 $4\text{K}$ 的温度，可见该效应的热现象十分小

---

### III.4 物理解释与讨论（7 分）

**(a)** 用你自己的话解释以下"悖论"：一个惯性观测者（Minkowski 观测者）处于 Minkowski 真空中，他测量到的粒子数为零；而一个匀加速观测者（Rindler 观测者）在同样的物理状态中却测量到了热辐射。粒子的概念为何是**观测者依赖**的？（3 分）

>[!S]-
>因为粒子的定义是依赖于正频分解的，也就是说
>$$\phi = \sum(u_{i}a_{i} + u_{i}^{*}a^{\dagger}_{i}) $$
>其中 $u_{i}$ 是关于某个特定时间坐标 $t$ 满足 $i\partial_{t}u=\omega u$ 的 Killing 方程的解，其湮灭算符 $a_{i}$ 作用到单粒子态上定义了“真空态”。
>
>而对于 Minkowski 时空和 Rindler 时空，他们对于时间的定义不同，所以对应的正频模的定义也不同，从而对于粒子的定义也就不相同了。

**(b)** Unruh 效应表明匀加速观测者感受到一个热浴。从等效原理的角度，这一效应暗示了什么关于引力场中量子效应的深刻结论？请简要联系 **Hawking 辐射** 给出说明。（4 分）

*提示：等效原理告诉我们，局部匀加速参考系等价于均匀引力场。Rindler 视界对应于黑洞视界。*

>[!S]-
>Unruh 效应告诉我们，在 Minkowski 真空中匀加速的观测者会感受到一个温度为 $T_{U}=a/2π$ 的热浴。由等效原理，该匀加速观测者所经历的物理，与**静止在一个均匀引力场中的观测者**所经历的物理在局部上是不可区分的。因此我们可以推断：
>
> **在量子场论中，一个静止于均匀引力场中的观测者，即使在惯性真空中，也应当感受到热辐射。**
>
>换句话说，**引力场本身可以使量子真空“加热”**。这不是因为引力场提供了能量，而是因为引力改变了“时间”的定义，从而改变了“粒子”的定义。
>
>匀加速观测者具有一个**事件视界**——Rindler 视界（即光锥 $x=±t$）。加速观测者无法看到视界之外的区域，这种信息的缺失正是其感受到热辐射的根本原因：视界将量子场的模截断，导致观测者只能获取部分信息，从而使得原本的纯态（Minkowski 真空）表现为一个混合热态。
>
>黑洞也具有事件视界。根据等效原理的强形式，**黑洞视界附近的物理应与 Rindler 视界附近的物理本质上相同**。因此，Unruh 效应自然地暗示：
>
> **黑洞视界附近应当产生热辐射，黑洞应当具有温度并可发出辐射。**

---

## 附加思考题（不计分）

> 本题中，我们在 $1+1$ 维 Minkowski 时空中只考虑了右 Rindler 楔形。实际上，Minkowski 真空 $|0_M\rangle$ 可以用左右 Rindler 态的纠缠形式表达为：
> $$|0_M\rangle \propto \prod_\Omega \exp\left( e^{-\pi \Omega / a}\, b_\Omega^{R\dagger} b_\Omega^{L\dagger} \right) |0_R\rangle$$
> 其中 $|0_R\rangle = |0_R^R\rangle \otimes |0_R^L\rangle$。这表明 Minkowski 真空是一个**双模态压缩真空态**。
>
> 1. 从纠缠的角度，解释为什么右 Rindler 观测者（只能访问右 Rindler 楔形）会看到热态（通过求左 Rindler 楔形的偏迹）。
> 2. 这与黑洞信息悖论有什么潜在联系？

---

## 评分标准概览

| 部分 | 题目 | 分值 | 考察能力 |
|------|------|------|----------|
| **I** | 经典场论与正则量子化 | 35 | QFT 基本框架、正则量子化、真空定义 |
| **II** | Rindler 坐标与弯曲时空 | 30 | 度规变换、Killing 矢量、弯曲时空场方程 |
| **III** | Bogoliubov 变换与 Unruh 效应 | 35 | 模混合、真空不等价、量子场论的观测者依赖性 |
| **合计** | | **100** | 从 flat 到 curved spacetime QFT 的完整思维链 |

---

## 参考解答要点

<details>
<summary>点击展开部分关键答案</summary>

**I.2(a):** $[a_k, a_{k'}^\dagger] = \delta(k-k')$

**I.3(b):** 类空分离时对易子为零 → 微观因果性（microcausality）

**II.2(b):** $a = 1/\xi_0$

**II.2(d):** $\omega' = \omega e^{-\eta}$ → 引力红移（或等效原理下的多普勒效应）

**III.3(b):** $T_U = a/2\pi$，恢复单位 $T_U = \hbar a / (2\pi k_B c)$

**III.3(c):** 
- $a = g = 9.8\text{ m/s}^2$: $T_U \approx 4 \times 10^{-20}\text{ K}$
- $a = 10^{21}\text{ m/s}^2$: $T_U \approx 4 \times 10^3\text{ K}$

</details>
