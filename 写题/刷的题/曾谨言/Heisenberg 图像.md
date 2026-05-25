---
up:
  - "[[写题]]"
related:
date: 2026-04-22
---

## 10.1

给定能量算符 $H(\mathbf{r},\mathbf{p})$ 以 $E_{n},\ket{n}$ 表示其本征系统，按照海森堡运动方程
$$\frac{dA}{dt} = \frac{1}{i\hbar}[A,H] $$
记
$$A_{kn} = \braket{ k | A| n }  $$
证明
$$\left( \frac{dA}{dt} \right)_{kn} = i\omega_{kn}A_{kn} $$
其中 $\omega_{kn}=\frac{E_{k} - E_{n}}{\hbar}$ 

>[!S]
>$$\begin{align} \braket{ k |\frac{dA}{dt}| n } & = \frac{1}{i\hbar} \braket{ k |[A,H]| n } \\ & = \frac{1}{i\hbar }\braket{ k |AH-HA|n  } \\ & = \frac{1}{i\hbar} (\braket{ k | A|n } E_{n} - E_{k}\braket{ k | A|n } ) \\  & = i\omega_{kn}A_{kn} \end{align} $$


## 10.2

设 $H = \frac{\mathbf{p}^{2}}{2\mu} + V(\mathbf{r})$ 证明
$$\sum_{n}(E_{n}-E_{k})|x_{nk}|^{2} = \frac{\hbar^{2}}{2\mu} $$

>[!S]
>考虑到 Hellmann 定理
>$$\frac{\partial E_{k}}{\partial \mu} = \braket{ k |\frac{\partial H}{\partial \mu}| k } = -\frac{1}{2\mu^{2}}\braket{ k |\mathbf{p}^{2}| k }  $$
>而有海森堡运动方程
>$$\frac{dx}{dt} = \frac{1}{i\hbar}[x,H] = \frac{p_{x}}{\mu}$$
>故
>$$\mathbf{p}^{2} = \mu^{2}\left( \frac{dx}{dt} \right)^{2} $$
>$$\braket{ k |\left( \frac{dx}{dt} \right)^{2}|k  } =  \sum_{n}\braket{ k | \frac{dx}{dt}| n }\braket{ n | \frac{dx}{dt}| k } = \sum_{n} \left( \frac{dx}{dt} \right)_{kn}\left( \frac{dx}{dt} \right)_{nk} $$
>由上一题知 $\left( \frac{dx}{dt} \right)_{nk} = i\omega_{nk}x_{nk}$ 所以
>$$\braket{ k | \mathbf{p}^{2}| k } = \mu^{2}\sum_{n} i\omega_{nk}i\omega_{kn}|x_{nk}|^{2} = \mu^{2}\sum_{n}(E_{n}-E_{k})|x_{nk}|^{2} $$



## 10.5

对于任意算符 $F(\mathbf{r},\mathbf{p})$ 及其共轭 $F^{\dagger}$ 有
$$(F_{kn})^{*} = (\braket{ k | F | n } )^{*} = \braket{ n | F^{\dagger} | k } = (F^{\dagger})_{nk}  $$
试证明其在能量表象下有
$$\sum_{n}(E_{n} - E_{k})(|F_{nk}|^{2} + |F_{kn}|^{2}) = \braket{ k | [F^{\dagger},[H,F]]| k }  $$

>[!S]
>$$\begin{align} RHS & = \braket{ k | F^{\dagger}HF - F^{\dagger}FH - HFF^{\dagger} + FHF^{\dagger} | k } \\ & = \sum_{n}\braket{ k | F^{\dagger} | n } \braket{ n | HF| k }  - \sum_{n}\braket{ k | F^{\dagger}| n } \braket{ n | FH| k } \\ & \quad -\sum_{n}\braket{ k | HF| n } \braket{ n | F^{\dagger}|k }  + \sum_{n}\braket{ k | F|n } \braket{ n | HF^{\dagger}|k } \\ & = \sum_{n}E_{n}(F^{\dagger})_{kn}F_{nk} - E_{k}\sum_{n} (F^{\dagger})_{kn}F_{nk} - E_{k}\sum F_{kn}(F^{\dagger})_{nk} + \sum_{n}E_{n}F_{kn}(F^{\dagger})_{nk} \\ & = \sum_{n}(E_{n }|F_{nk}|^{2} - E_{k}|F_{nk}|^{2}-E_{k}|F_{kn}|^{2} + E_{n}|F_{kn}|^{2}) \\ & = \sum_{n}(E_{n}-E_{k})(|F_{nk}|^{2} + |F_{kn}|^{2}) \\ & =LHS \end{align} $$


## 10.9

对一维运动，设
$$H = \frac{p^{2}}{2\mu} + V(x) $$
证明
$$\sum_{n}(E_{k}-E_{n})^{2}|x_{kn}|^{2} = -2\hbar^{2} \frac{\partial E_{k}}{\partial \mu} $$

>[!S]
>由 Hellmann 定理
>$$\frac{\partial E_{k}}{\partial \mu} = \braket{ k |\frac{\partial H}{\partial \mu}| k } = -\frac{1}{2\mu^{2}} \braket{ k |p^{2}| k }  $$
>而
>$$\frac{dx}{dt} = \frac{1}{i\hbar}[x,H] = \frac{p}{\mu} $$
>故
>$$\braket{ k |p^{2}| k } = \mu^{2}\sum_{n}\left( \frac{dx}{dt} \right)_{kn}\left( \frac{dx}{dt} \right)_{nk} = \mu^{2}\sum_{n}i\omega_{kn}x_{kn}\omega_{nk}x_{nk} = \mu^{2}\sum_{n}(E_{k}-E_{n})^{2}|x_{nk}|^{2}  $$
>于是
>$$\sum_{n}(E_{k}-E_{n})^{2}|x_{kn}|^{2} = -2\hbar^{2} \frac{\partial E_{k}}{\partial \mu}  $$


## 10.10

对于中心力场的 s 态和 p 态，证明
$$\sum_{n}(E_{n's}-E_{np})^{2}|z_{n's,np}|^{2} = \frac{2\hbar^{2}}{3\mu} \braket{ \frac{\mathbf{p}^{2}}{2\mu}}_{n's} $$

>[!S]
>考虑
>$$\frac{dz}{dt} = \frac{1}{i\hbar}[z,H] = \frac{p_{z}}{\mu} $$
>$$[H,z][H,z]^{\dagger} = \frac{\hbar^{2}}{\mu^{2}}p_{z}^{2} $$
>所以
>$$LHS = \frac{\hbar^{2}}{\mu^{2}}\braket{ p_{z}^{2} }_{n's}  $$
>考虑到 $\braket{ p_{z}^{2} } = \braket{ p_{x}^{2} }=\braket{ p_{y} }^{2}=\frac{1}{3}\braket{ \mathbf{p}^{2} }$ 所以
>$$LHS = \frac{\hbar^{2}}{3\mu^{2}}\braket{ \mathbf{p}^{2} }_{n's} = RHS $$



## 10.11

对于一维谐振子的 $x,p$ 和它们的升降算符 $a^{\dagger},a$ 求它们在海森堡绘景下的表达

>[!S]
>在薛定谔绘景中 
>$$x = \sqrt{ \frac{\hbar}{2m\omega} }(a^{\dagger}+a) ,\quad p = \sqrt{ \frac{m\omega \hbar}{2} }(a^{\dagger}-a) ,\quad H = \hbar \omega\left( a^{\dagger}a + \frac{1}{2} \right) $$
>转换到海森堡绘景
>$$a^{\mathrm{H}} = e^{ iHt/\hbar }a^{\mathrm{S}}e^{ -iHt/\hbar } \implies \frac{da^{\mathrm{H}}}{dt} = \frac{i}{\hbar}e^{ iHt/\hbar }[H,a^{\mathrm{S}}]e^{ -iHt/\hbar } = -i\omega a^{\mathrm{S}}e^{ -i\omega t } $$
>$$a^{\mathrm{H}} = a^{\mathrm{S}}e^{ -i\omega t } $$
>同理 ${a^{\dagger}}^{\mathrm{H}}={a^{\dagger}}^{S}e^{ i\omega t }$ 于是
>$$x^{\mathrm{H}} = \sqrt{ \frac{\hbar}{2m\omega} }({a^{\dagger}}^{H}+ a^{\mathrm{H}}) = x^{\mathrm{S}}\cos \omega t + \frac{p^{\mathrm{S}}}{m\omega}\sin \omega t $$
>$$p^{\mathrm{H}} = p^{\mathrm{S}}\cos \omega t - x^{\mathrm{S}}m\omega \sin \omega t $$


## 10.12

对于一维谐振子计算 $x(t_{1}),x(t_{2}),p(t_{1}),p(t_{2})$ 间的对易关系

>[!S]
>由上一问，由于这里全是海森堡绘景，略去上标 $\mathrm{H}$ 并对于薛定谔绘景的算符类似的简记
>$$\begin{align}[x(t_{1}),x(t_{2})] & = x(t_{1})x(t_{2}) - x(t_{2})x(t_{1}) \\ & \sim xp\cos \omega t_{1}\sin \omega t_{2} + px\sin \omega t_{1}\cos \omega t_{2} \\ & \quad - xp\cos \omega t_{2}\sin \omega t_{1} - px\sin \omega t_{2}\cos \omega t_{1} \\ & = [x,p](\cos \omega t_{1}\sin \omega t_{2} - \sin \omega t_{1}\cos \omega t_{2}) \\ & = [x,p]\sin \omega(t_{1}-t_{2}) \end{align} $$
>补回量纲
>$$[x(t_{1}),x(t_{2})] = \frac{i\hbar}{m\omega}\sin \omega(t_{1}-t_{2}) $$
>类似的
>$$[p(t_{1}),p(t_{2})] = im\omega \hbar \sin \omega(t_{1}-t_{2}) $$
>$$[x(t_{1}),p(t_{2})] = i\hbar \cos \omega(t_{1}-t_{2}) $$



## 10.13

有一个定域电子，不考虑轨道运动，受到均匀磁场作用，磁相互作用能为
$$H = \hbar \omega \sigma_{x} $$
设 $t=0$ 时，电子自旋“向上”，求 $t>0$ 时的 $\mathbf{s}$ 的期望值

>[!S]
>初始时刻 $\braket{ \mathbf{s} }_{t=0}=\frac{\hbar}{2}\hat{z}$ 由海森堡运动方程
>$$\frac{d\mathbf{s}}{dt} = \frac{1}{i\hbar}[\mathbf{s},H] \implies \frac{ds_{x}}{dt} = 0 ,\quad \frac{ds_{y}}{dt} = -2\omega s_{z},\quad \frac{ds_{z}}{dt} = 2\omega s_{y} $$
>解该微分方程得
>$$\braket{ s_{y} } = -\frac{\hbar}{2}\sin \omega t ,\quad\braket{ s_{z} } = \frac{\hbar}{2}\cos \omega t $$
>这里对方程得解取了一次期望值，因为我们已知得初始条件是关于期望值的

下面使用薛定谔绘景

>[!S]
>初态为 $\ket{\psi}=\ket{\uparrow}$ 时间演化算符是
>$$U = \exp\left( -\frac{iHt}{\hbar} \right) = \exp(-i\omega t\sigma_{x}) = \cos \omega t - i\sin \omega t\sigma_{x} $$
>于是
>$$\ket{\psi} = U\ket{\uparrow} = \cos \omega t\ket{\uparrow} - i\sin \omega t\sigma_{x}\ket{\uparrow} = \cos \omega t\ket{\uparrow} - i\sin \omega t\ket{\downarrow} $$
>于是
>$$\braket{ s_{x} } = 0 ,\quad \braket{ s_{y} } = -\frac{\hbar}{2}\sin \omega t ,\quad \braket{ \sigma_{z} } =\frac{\hbar}{2}\cos \omega t $$


## 10.15

两个自旋 1/2 的定域非全同粒子，不考虑轨道运动，相互作用能为
$$H = A\mathbf{s}_{1}\cdot \mathbf{s}_{2} $$
初始时刻，粒子1自旋向上，粒子2自旋向下。再海森堡绘景中求任意时刻 
(a) 粒子1自旋向上的概率
(b) 粒子1和2自旋均向上的概率
(c) 总自旋 $S=1$ 和 0 的概率
(d) $\mathbf{s}_{1},\mathbf{s}_{2}$ 的期望值

>[!S]
>考虑海森堡方程
>$$\frac{d\mathbf{s}_{1}}{dt} = \frac{1}{i\hbar}[\mathbf{s}_{1},H] = -A\mathbf{s}_{1}\times \mathbf{s}_{2} ,\quad \frac{d\mathbf{s}_{2}}{dt} = A\mathbf{s}_{1}\times \mathbf{s}_{2} $$
>$$\frac{d(\mathbf{s}_{1}+\mathbf{s}_{2})}{dt} = \frac{d\mathbf{S}}{dt} = 0 ,\quad \frac{d(\mathbf{s}_{1}-\mathbf{s}_{2})}{dt} = -2A\mathbf{s}_{1}\times \mathbf{s}_{2} $$
>$$\frac{d(\mathbf{s}_{1}\times \mathbf{s}_{2})}{dt} = A\left[ \mathbf{s}_{1}\times(\mathbf{s}_{1}\times \mathbf{s}_{2}) - (\mathbf{s}_{1}\times \mathbf{s}_{2})\times \mathbf{s}_{2} \right] = \frac{A}{2}(\mathbf{s}_{1}-\mathbf{s}_{2}) $$
>代入初始条件 $\braket{ \mathbf{s}_{1}+\mathbf{s}_{2} }=0,\braket{ \mathbf{s}_{1}-\mathbf{s}_{2} }=\hat{z},\braket{ \mathbf{s}_{1}\times \mathbf{s}_{2} }=0$ 得
>$$\mathbf{S}\equiv 0 ,\quad \braket{ \mathbf{s}_{1}-\mathbf{s}_{2} } = \cos At\hat{z} ,\quad \braket{ \mathbf{s}_{1}\times \mathbf{s}_{2} } = \frac{1}{2}\sin At\hat{z} $$
>进而得到
>$$\braket{ \mathbf{s}_{1} } = \frac{1}{2}\cos At\hat{z},\quad \braket{ \mathbf{s}_{2} } = -\frac{1}{2}\cos At\hat{z} $$
>于是粒子1自旋向上的概率为 $w$ 则
>$$\braket{ s_{1z} } = \frac{1}{2}\cos At = \frac{1}{2}w - \frac{1}{2}(1-w) = w - \frac{1}{2} \implies w= \cos ^{2} \frac{At}{2} $$
>粒子1和粒子而自旋都向上时 $\braket{ \mathbf{S} }=\hat{z}$ 是不可能时间，概率为零。实际上总自旋总是 $\braket{ \mathbf{S} }=1$ 。


