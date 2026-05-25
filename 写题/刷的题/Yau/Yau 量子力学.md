---
up:
  - "[[写题]]"
related:
date: 2026-03-11
tags:
  - 量子力学
  - 习题
---
# 24 年

Consider a 1-dim quantum-mechanical harmonic oscillator with mass $m$ and resonance frequency $ω$. The oscillator initially (at $t → −∞$) is in its ground state. It is then subjected to a transient perturbation $∆H = F(t)x$ with $F(t → ±∞) → 0$

(a) Write down the Hamiltonian $\hat{H}$ of the perturbed oscillator described above in terms of the usual ladder operators $\hat{a}$ and $\hat{a}^{\dagger}$ , and solve their equations of motion in the Heisenberg picture. Show that the Hamiltonian at $t → ±∞$ takes the form
$$\hat{H} = \hbar \omega\left( \hat{a}^{\dagger}_{\pm \infty}\hat{a}_{\pm \infty} + \frac{1}{2} \right) \tag{1} $$
and determine the relation between $a_{+\infty}$ and $a_{-\infty}$.

>[!S]
>引入
>$$x = \sqrt{ \frac{\hbar}{2m\omega} }(a+a^{\dagger}) , \quad p = i\sqrt{ m\hbar \frac{\omega}{2} }(a^{\dagger}-a) $$
>则自由谐振子的哈密顿量 $H_{0}=\frac{p^{2}}{2m}+\frac{1}{2}m\omega^{2}x^{2}$ 可表达为
>$$H_{0} = \hbar \omega\left( a^{\dagger}a + \frac{1}{2} \right) $$
>现有扰动 $\Delta H = F(t)x$ 于是
>$$\Delta H = F(t)\sqrt{ \frac{\hbar}{2m\omega} }(a+a^{\dagger}) := f(t)(a+a^{\dagger}) $$
>$$H = H_{0}+\Delta H = \hbar \omega\left( a^{\dagger}a+\frac{1}{2} \right)+f(t)(a+a^{\dagger}) $$
>由于扰动在 $t\to \pm \infty$ 时趋于零，哈密顿量回归自由谐振子，所以
>$$H = \hbar \omega\left( \hat{a}^{\dagger}_{\pm \infty}\hat{a}_{\pm \infty} + \frac{1}{2} \right)$$
>由海森堡运动方程
>$$\dot{a} = \frac{i}{\hbar}[H,a] = \hbar \omega(-a)-f(t) \implies \dot{a} + i\omega a = -\frac{i}{\hbar}f(t) $$
>$$a = a(-\infty)e^{ -i\omega t } - \frac{i}{\hbar} e^{ -i\omega t } \int_{-\infty}^{t} f(\tau)e^{ -i\omega \tau } d\tau $$
>$$a_{+\infty} - a_{-\infty} = -\frac{i}{\hbar} \int_{-\infty}^{+\infty} f(t)e^{ i\omega t }dt = -i \sqrt{ \frac{1}{2m\hbar \omega} } \int_{-\infty}^{+\infty} F(t)dt $$
>

>[!yellow]
>本质是说外源作用会导致真空成为相干态

(b) At $t → ±∞$, the ladder operators act on the state $\ket{n_{\pm \infty}} = (1/\sqrt{ n! })(\hat{a}^{\dagger}_{\pm \infty})^{n}\ket{0_{\pm \infty}}$. Here $\ket{0_{\pm \infty}}$ denote the vacuum with respect to $\hat{a}_{\pm \infty}$ and $\hat{a}^{\dagger}_{\pm \infty}$. Determine the probabilities $|c_{n}|^{2}$ that the oscillator has undergone a transition from the initial ground state to the n-th excited state at the end of the time evolution.

>[!S]
>有上一问知
>$$a_{-\infty}\ket{0_{-\infty}} = 0 , \quad a_{-\infty} = a_{+\infty} + \alpha  $$
>$$a_{+\infty}\ket{0_{-\infty}} = \alpha \ket{0_{-\infty}}   $$
>即初态是 $a_{+\infty}$ 的本征态，即它是一个相干态，对于相干态可以展开
>$$\ket{0_{-\infty}} = e^{ -|\alpha|^{2}/2 } \sum_{n=0}^{\infty} \frac{\alpha^{n}}{\sqrt{ n! }} \ket{n_{+\infty}}  $$
>所以
>$$c_{n} = e^{ -|\alpha|^{2}/2 } \frac{\alpha^{n}}{\sqrt{ n! }} $$
>$$|c_{n}|^{2} = e^{ -|\alpha|^{2} } \frac{|\alpha|^{2n}}{n!} $$
>

(c) What is the expectation value of the energy at the end of the time evolution?

>[!S]
>由上一问知，末态哈密顿量及能级为
>$$H = \hbar \omega\left( a_{+\infty}^{\dagger}a_{+\infty} + \frac{1}{2} \right) ,\quad E_{n} = \hbar \omega\left( n+\frac{1}{2} \right) $$
>而在 $n$ 能级的概率为
>$$P_{n} = |c_{n}|^{2} = e^{ -|\alpha|^{2} }  \frac{|\alpha|^{2n}}{n!} $$
>于是末态期望能量为
>$$\langle E\rangle = \sum_{n=0}^{\infty} P_{n}E_{n} = \sum_{n=0}^{\infty} e^{ -|\alpha|^{2} }  \frac{|\alpha|^{2n}\left( n+\frac{1}{2} \right)}{n
!} \hbar \omega $$
>其中
>$$\begin{align}
\sum_{n=0}^{\infty} \frac{a^{n}}{n!} = e^{ a }
\end{align} $$
>$$\begin{align}
\sum_{n=0}^{\infty} \frac{na^{n}}{n!} = a \frac{d}{da}\sum_{n=0}^{\infty} \frac{a^{n}}{n!} = ae^{ a }
\end{align} $$
>于是
>$$\langle E\rangle = \frac{\hbar \omega}{2} + \hbar \omega|\alpha|^{2} $$

(d) Now assume that $F(t) = F_{0}e^{ -t^{2}/(2\sigma_{t}^{2}) }$, with $F_{0} = \eta\hbar \omega/l$ where $η$ is a dimensionless parameter, and $l = \sqrt{ \hbar /(m\omega) }$ is the harmonicoscillator length. For short pulses with $\sigma_{t}\omega\ll 1$, determine the maximum pulse strength $η$ for which less that 1% of the population gets lost from the ground state. Show explicitly that in the limit $\sigma_{t}\omega\ll1$, losses can be suppressed for any given value of $η$ 

>[!S]
>基态概率
>$$P_{0} = e^{ -|\alpha|^{2} } $$
>现要求 $1-P_{0}<0.01$ 所以 $|\alpha|^{2}<0.01$ 而题目给定了外力形式可以计算 $\alpha$
>$$\begin{align}
\alpha  & = -i \sqrt{ \frac{1}{2m\hbar \omega} } \int_{-\infty}^{+\infty} F(t)dt \\ & = -i \sqrt{ \frac{1}{2m\hbar \omega} } \int_{-\infty}^{+\infty} F_{0}e^{ -t^{2}/(2\sigma_{t}^{2}) } dt \\ & = -i \sqrt{ \frac{1}{2m\hbar \omega} }F_{0} \sqrt{ 2\pi } \sigma_{t} e^{ -\omega^{2}\sigma_{t}^{2}/2 }
\end{align} $$
>$$|\alpha|^{2} = \pi \eta^{2}\omega^{2}\sigma_{t}^{2}e^{ -\omega^{2}\sigma_{t}^{2} } < 0.01 $$
>$$\eta < \frac{0.056}{\omega \sigma_{t}} $$


---

# 23 年

A particle of mass $m$ in 2 dimensions is confined by an isotropic harmonic oscillator potential of frequency $ω$, while subject to a weak and anisotropic perturbation of strength $\alpha\ll 1$. The total Hamiltonian of the particle is
$$H = H_{0} + V = \frac{p_{x}^{2}}{2m} + \frac{p_{y}^{2}}{2m} + \frac{1}{2}m\omega^{2}(x^{2}+y^{2}) + \alpha m\omega^{2}xy \tag{1} $$
(a) When $α = 0$, what are the energies and degeneracies of the three lowest-lying unperturbed states?

>[!S]
>$\alpha=0$ 时 $H=H_{x}+H_{y}$ 可以利用产生湮灭算符将哈密顿量写为
>$$H_{i} = \frac{p_{i}^{2}}{2m} + \frac{1}{2}m\omega^{2}x_{i}^{2} = \hbar \omega\left( a^{\dagger}_{i}a_{i} + \frac{1}{2} \right) ,\quad i=x,y $$
>则系统的能量为
>$$E_{n} = (n+1)\hbar \omega , \quad n = n_{x} + n_{y} $$
>基态 $\ket{0,0}$
>$$E_{0} = \hbar \omega ,\quad g=1 $$
>第一激发态 $\ket{0,1}=\ket{1,0}$
>$$E_{1} = 2\hbar \omega , \quad g=2 $$
>第二激发态 $\ket{2,0}=\ket{1,1}=\ket{0,2}$
>$$E_{2} = 3\hbar \omega , \quad g=3 $$
>
>

(b) Use perturbation theory to correct the energies of the above three states to the first order in $α$

>[!S]
>相互作用用产生湮灭算符写
>$$\begin{align}
V  & = \frac{\alpha \hbar \omega}{2} (a_{x}+a_{x}^{\dagger})(a_{y}+a_{y}^{\dagger})\\ & =\frac{\alpha \hbar \omega }{2}(a_{x}a_{y} + a_{x}a_{y}^{\dagger} + a_{x}^{\dagger}a_{y} + a_{x}^{\dagger}a_{y}^{\dagger}) 
\end{align}$$
>基态一阶修正
>$$\Delta E^{(1)} = \braket{ 0,0 |V|0,0  } = 0  $$
>第一激发态一阶修正
>$$\braket{ 1,0 |V|1,0  } = \braket{ 0,1 |V|0,1  } =0 $$
>$$\braket{ 1,0 |V| 0,1 } = \braket{ 0,1 |V| 1,0 } = \frac{\alpha \hbar \omega}{2}  $$
>$$V = \frac{\alpha \hbar \omega}{2} \begin{pmatrix}
0 & 1 \\ 1 & 0
\end{pmatrix} $$
>有特征值 $\lambda=\pm \dfrac{\alpha \hbar \omega}{2}$ 所以
>$$\Delta E^{(1)} = \pm \frac{\alpha \hbar \omega}{2} ,\quad E = 2\hbar \omega \pm \frac{\alpha \hbar \omega}{2} $$
>第二激发态一阶修正
>$$V = \frac{\alpha \hbar \omega}{\sqrt{ 2 }} \begin{pmatrix}
0 & 1 & 0 \\1 & 0 & 1 \\ 0 & 1 & 0
\end{pmatrix} $$
>$$\Delta E^{(1)} = 0 ,\pm \alpha \hbar \omega ,\quad E = 3\hbar \omega , 3\hbar \omega\pm \alpha \hbar \omega $$

(c) Find the exact spectrum of $H$. (Hint: you may want to rotate $x$ and $y$ into a new coordinates)

>[!S]
>$$V = \frac{1}{2}m\omega^{2} \begin{pmatrix}
x & y
\end{pmatrix}\begin{pmatrix}
1 & \alpha \\ \alpha & 1
\end{pmatrix} \begin{pmatrix}
x \\ y
\end{pmatrix} $$
>二次型的本征值为 $\lambda=1\pm \alpha$ 对应有本征矢
>$$\begin{pmatrix}
1 \\ 1
\end{pmatrix} ,\quad \begin{pmatrix}
1 \\ -1
\end{pmatrix} $$
>故考虑旋转变换
>$$X = \frac{x+y}{\sqrt{ 2 }} , \quad Y = \frac{x-y}{\sqrt{ 2 }} $$
>则
>$$H=\frac{P_{X}^{2}}{2m}​​+\frac{1}{2}​m\omega^{2}(1+α)X^{2}+\frac{P_{Y}^{2}}{2m}​​+\frac{1}{2}​m\omega^{2}(1−α)Y^{2}$$
>显然这是两个谐振子，本征频率分别为 $$\omega_{1} = \omega \sqrt{ 1+\alpha } ,\quad\omega_{2}=\omega \sqrt{ 1-\alpha } $$
>于是能级为
>$$E_{n_{1},n_{2}} = \hbar \omega_{1}\left( n_{1}+\frac{1}{2} \right) + \hbar \omega_{2}\left( n_{2}+\frac{1}{2} \right) $$


(d) Check that the perturbative results in part b. are recovered from the exact spectrum.

>[!S]
>对于基态 $n_{1}=n_{2}=0$ 
>$$E_{0} = \frac{\hbar \omega}{2}(\sqrt{ 1+\alpha }+\sqrt{ 1-\alpha }) \approx \hbar \omega $$
>对于第一激发态
>- $n_{1}=1,n_{2}=0$:
>  $$E_{1,0} = \frac{3\hbar \omega \sqrt{ 1+\alpha }}{4} + \frac{\hbar \omega \sqrt{ 1-\alpha }}{2} \approx 2\hbar \omega + \frac{\alpha \hbar \omega}{2} $$
>- $n_{1}=0,n_{2}=1$:
>  $$E_{0,1} = \frac{\hbar \omega \sqrt{ 1+\alpha }}{2} + \frac{3\hbar \omega \sqrt{ 1-\alpha }}{4} \approx 2\hbar \omega - \frac{\alpha \hbar \omega}{2} $$
>对于第二激发态
>- $n_{1}=2,n_{2}=0$:
>  $$E_{2,0} = \frac{5\hbar \omega \sqrt{ 1+\alpha }}{4} + \frac{\hbar \omega \sqrt{ 1-\alpha }}{2} = 3\hbar \omega + \alpha \hbar \omega $$
>- $n_{1}=n_{2}=1$: 
>  $$E_{1,1} = \frac{3\hbar \omega \sqrt{ 1+\alpha }}{4} + \frac{3\hbar \omega \sqrt{ 1-\alpha }}{4} = 3\hbar \omega $$
>- $n_{1}=0,n_{2}=2$: 
>  $$E_{0,2} = 3\hbar \omega-\alpha \hbar \omega $$

---

# 22 年

(a) A symmetry transformation in quantum mechanics is represented by a unitary or anti-unitary operator acting on a Hilbert space. The time reversal transformation $Θ$ relates the wave function at time $t$ to time $−t$. Prove: $Θ$ is an anti-unitary operator.

>[!S]
>若 $\ket{\psi}$ 满足薛定谔方程
>$$ i\hbar \frac{\partial }{\partial t}\ket{\psi} = H\ket{\psi}  $$
>时间反演算符作用后 $\ket{\psi'} = \Theta \ket{\psi(-t)}$ 也应满足薛定谔方程，即
>$$i\hbar \frac{\partial }{\partial t}(\Theta \ket{\psi(-t)} ) = H\Theta\ket{(\psi(-t))}  $$
>设 $\Theta$ 是线性算符则
>$$LHS = i\hbar \Theta \frac{\partial}{\partial t}\ket{\psi(-t)} = -i\hbar \Theta \frac{\partial }{\partial(-t)}\ket{\psi(-t)} := -i\hbar \Theta \frac{\partial }{\partial \tau}\ket{\psi(\tau)}  $$
>而
>$$i\hbar \frac{\partial }{\partial \tau}\ket{\psi(\tau)} = H\ket{\psi(\tau)}  $$
>故
>$$LHS = -\Theta H\ket{\psi(\tau)} = -\Theta H\ket{\psi(-t)} = RHS = H\Theta\ket{\psi(-t)}   $$
>$$H\Theta + \Theta H = 0 $$
>若系统时间反演不变则应有 $[H,\Theta]=0$ 与之矛盾，故 $\Theta$ 不是线性的。故由 Wigner 定理 $\Theta$ 是反线性的。为了保持变换前后的概率不变，要求
>$$|\braket{ \psi |\Theta ^{\dagger}\Theta| \phi }|^{2} = |\braket{ \psi | \phi }|^{2} \implies|\Theta ^{\dagger}\Theta| = 1 $$
>所以 $\Theta$ 是反幺正的。

(b) Consider state vector $\ket{\psi}$ for a quantum system. A time reversal transformation is represented by an anti-unitary operator $Θ$. We now consider position space wavefunction $ψ(x) = \braket{ x | \psi }$ , and $Θ\ket{x} = \ket{x}$ . Prove: the position space wave function for $Θ\ket{\psi}$ is $\psi^{*}(x)$

>[!S]
>在坐标表象下
>$$\ket{\psi} = \int dx\ \psi(x)\ket{x}   $$
>时间反演算符作用上去得到，由于 $\Theta$ 反幺正所以 $\Theta(c\ket{\psi})=c^{*}\Theta \ket{\psi}$ 
>$$\Theta \ket{\psi} = \int dx \ \Theta(\psi(x)\ket{x} ) = \int dx\ \psi^{*}(x)\Theta \ket{x} = \int dx \ \psi^{*}(x)\ket{x}   $$
>所以 $\Theta \ket{\psi}$ 的波函数是 $\psi^{*}(x)$

(c) A one dimensional quantum system is invariant under time reversal transformation, and so its Hamiltonian satisfies $ΘH = HΘ$. If an energy eigenstate $\ket{\psi}$ has no degeneracy, Prove: it is possible to take the position space energy eigenfunction to be real:
$$\psi^{*}(x) = \psi(x) $$

>[!S]
>由于 $\Theta H = H\Theta$ 所以考虑
>$$H(\Theta \ket{\psi} ) = \Theta H\ket{\psi} = E\Theta \ket{\psi}   $$
>所以 $\Theta \ket{\psi}$ 是 $H$ 的本征态，且本征值为 $E$ ，与 $\ket{\psi}$ 的本征值一致，且这个态非简并，所以二者至多差一个相位
>$$\Theta \ket{\psi} = e^{ i\theta }\ket{\psi}   $$
>在坐标表象下
>$$\psi^{*}(x) = \braket{ x |\Theta| \psi } = e^{ i\theta } \braket{ x | \psi } = e^{ i\theta } \psi(x) $$

后面不知道如何消去 $\theta$ 了

---

# 22 年

Consider following quantum Hamiltonian:
$$H = \frac{p_{1}^{2}}{2m} + \frac{1}{2}m\omega^{2}x_{1}^{2} + \frac{p_{2}^{2}}{2m} + \frac{1}{2}m\omega^{2}x_{2}^{2} $$
This is the Hamiltonian for two decoupled harmonic oscillators.

(a) Calculate the eigenstates and eigenvalues for $H_{0}$ (an energy eigenstate could be labeled as $\ket{n_{1},n_{2}}$ ).

>[!S]
>考虑两个阶梯算符
>$$x_{i} = \sqrt{ \frac{\hbar}{2m\omega} } (a_{i} + a_{i}^{\dagger}) ,\quad p_{i} = i\sqrt{ \frac{\hbar m\omega}{2} }(a_{i}^{\dagger} - a_{i}) ,\quad i=1,2 $$
>则可以将哈密顿量改写为
>$$H = \hbar \omega(a_{1}^{\dagger}a_{1} + a_{2}^{\dagger}a_{2} + 1) = H_{1} + H_{2} $$
>其中 $H_{i}=\hbar \omega\left( a_{i}^{\dagger}a_{i} + \frac{1}{2} \right)$ 是一个一维量子谐振子，于是有
>$$H_{i}\ket{n_{i}} = E_{n_{i}}\ket{n_{i}} ,\quad i=1,2 ;\quad E_{n_{i}} = \left( n_{i}+\frac{1}{2} \right)\hbar \omega  $$
>总的来说
>$$E_{n_{1},n_{2}} = E_{n_{1}} + E_{n_{2}} = (n_{1} + n_{2} + 1)\hbar \omega $$
>$$\ket{n_{1},n_{2}} = \ket{n_{1}} \otimes \ket{n_{2}}    $$
>

(b) Assume the creation and annihilation operators for two harmonic oscillators are $a^{\dagger}_{i}$ , $a_{i}$, $i = 1, 2$. Define following operators
$$J_{+}=a_{1}^{\dagger}a_{2} , \quad J_{-}=a_{2}^{\dagger}a_{1} ,\quad J_{z} = \frac{1}{2}(a_{1}^{\dagger}a_{1} - a_{2}^{\dagger}a_{2}) $$
	i. Prove that: $[J_{z},J_{\pm}]=\pm J_{\pm},\quad [J_{+},J_{-}]=2J_{z}$
	ii. Consider one eigenvalue $E_{n}$ of $H_{0}$, (here $n_{1} + n_{2} = n$). Prove that: all eigenstates of $E_{n}$ form an irreducible representation of $su(2)$ Lie algebra, and compute the spin.

>[!S]
>i
>$$\begin{align}
[J_z,J_{+}] & = \frac{1}{2}[a_{1}^{\dagger}a_{1},a_{1}^{\dagger}a_{2}] - \frac{1}{2}[a_{2}^{\dagger}a_{2},a_{1}^{\dagger}a_{2}] \\ & = \frac{1}{2}[a_{1}^{\dagger},a_{1}^{\dagger}a_{2}]a_{1} + \frac{1}{2}a_{1}^{\dagger}[a_{1},a_{1}^{\dagger}a_{2}] - \frac{1}{2}[a_{2}^{\dagger},a_{1}^{\dagger}a_{2}]a_{2} - \frac{1}{2}a_{2}^{\dagger}[a_{2},a_{1}^{\dagger}a_{2}] \\ & =\frac{1}{2}a_{1}^{\dagger}[a_{1}^{\dagger},a_{2}]a_{1} + \frac{1}{2}[a_{1}^{\dagger},a_{1}^{\dagger}]a_{2}a_{1} + \frac{1}{2}a_{1}^{\dagger}a_{1}^{\dagger}[a_{1},a_{2}] + \frac{1}{2}a_{1}^{\dagger}[a_{1},a_{1}^{\dagger}]a_{2} \\ & \quad -\frac{1}{2}a_{1}^{\dagger}[a_{2}^{\dagger},a_{2}]a_{2} - \frac{1}{2}[a_2^{\dagger},a_{1}^{\dagger}]a_{2}a_{2} - \frac{1}{2}a_{2}^{\dagger}a_{1}^{\dagger}[a_{2},a_{2}] - \frac{1}{2}a_{2}^{\dagger}[a_{2},a_{1}^{\dagger}]a_{2} \\ & = \frac{1}{2}a_{1}^{\dagger}a_{2} + \frac{1}{2}a_{1}^{\dagger}a_{2} \\ & =a_{1}^{\dagger}a_{2} = J_{+}
\end{align}$$
>$$\begin{align}
[J_{z},J_{-}] & = \frac{1}{2}[a_{1}^{\dagger}a_{1},a_{2}^{\dagger}a_{1}] - \frac{1}{2}[a_{2}^{\dagger}a_{2},a_{2}^{\dagger}a_{1}] \\ & = \frac{1}{2}[a_{1}^{\dagger},a_{2}^{\dagger}a_{1}]a_{1} + \frac{1}{2}a_{1}^{\dagger}[a_{1},a_{2}^{\dagger}a_{1}] - \frac{1}{2}[a_{2}^{\dagger},a_{2}^{\dagger}a_{1}]a_{2} - \frac{1}{2}a_{2}^{\dagger}[a_{2},a_{2}^{\dagger}a_{1}] \\ & =\frac{1}{2}a_{2}^{\dagger}[a_{1}^{\dagger},a_{1}]a_{1} + \frac{1}{2}[a_{1}^{\dagger},a_{2}^{\dagger}]a_{1}a_{1} + \frac{1}{2}a_{1}^{\dagger}a_{2}^{\dagger}[a_{1},a_{1}] + \frac{1}{2}a_{1}^{\dagger}[a_{1},a_{2}^{\dagger}]a_{1} \\ & \quad -\frac{1}{2}a_{2}^{\dagger}[a_{2}^{\dagger},a_{1}]a_{2} - \frac{1}{2}[a_2^{\dagger},a_{2}^{\dagger}]a_{1}a_{2} - \frac{1}{2}a_{2}^{\dagger}a_{2}^{\dagger}[a_{2},a_{1}] - \frac{1}{2}a_{2}^{\dagger}[a_{2},a_{2}^{\dagger}]a_{1} \\ & = \frac{1}{2}a_{2}^{\dagger}a_{1} + \frac{1}{2}a_{2}^{\dagger}a_{1} \\ & =a_{2}^{\dagger}a_{1} = J_{-}
\end{align}$$
>$$\begin{align}
[J_{+},J_{-}] & = [a_{1}^{\dagger}a_{2},a_{2}^{\dagger}a_{1}] \\ & = a_{1}^{\dagger}[a_{2},a_{2}^{\dagger}a_{1}] + [a_{1}^{\dagger},a_{2}^{\dagger}a_{1}]a_{2} \\ & = a_{1}^{\dagger}a_{2}^{\dagger}[a_{2},a_{1}] + a_{1}^{\dagger}[a_{2},a_{2}^{\dagger}]a_{1} + a_{2}^{\dagger}[a_{1}^{\dagger},a_{1}]a_{2} + [a_{1}^{\dagger},a_{2}^{\dagger}]a_{1}a_{2} \\ & = a_{1}^{\dagger}a_{1} - a_{2}^{\dagger}a_{2} = 2J_{z}
\end{align}$$
>ii
>在固定能量时，状态被固定为 $n_{1}+n_{2}=n$ ，这是一个多重态，简并度是 $n+1$ ，对于其中某个态有
>$$\begin{gather}
J_{+}\ket{n_{1},n_{2}} = a_{1}^{\dagger}a_{2}\ket{n_{1},n_{2}} = \sqrt{ n_{2} }\sqrt{ n_{1}+1 } \ket{n_{1}+1,n_{2}-1}  \\
J_{-}\ket{n_{1}.n_{2}} = a_{2}^{\dagger}a_{1}\ket{n_{1},n_{2}} = \sqrt{ n_{1 }} \sqrt{ n_{2}+1 } \ket{n_{1}-1,n_{2}+1} \\
J_{z}\ket{n_{1},n_{2}} = \frac{1}{2}(a_{1}^{\dagger}a_{1}-a_{2}^{\dagger}a_{2})\ket{n_{1},n_{2}} = \frac{n_{1}-n_{2}}{2}\ket{n_{1},n_{2}}      
\end{gather} $$
>这说明 $\{ J_{\pm},J_{z} \}$ 确实是角动量代数的阶梯算符。下确定其自旋，
>$$J^{2} = J_{z}^{2} + 2(J_{+}J_{-}+J_{-}J_{+}) = \frac{1}{4}(a_{1}^{\dagger}a_{1}-a_{2}^{\dagger}a_{2})^{2} + \frac{1}{2}(2a_{1}^{\dagger}a_1a_{2}^{\dagger}a_{2}+a_{1}^{\dagger}a_{1} + a_{2}^{\dagger}a_{2}) $$
>所以
>$$J^{2}\ket{n_{1},n_{2}} = \left[  \frac{1}{4}(n_{1}-n_{2}) ^{2} + \frac{1}{2}(2n_{1}n_{2} + n_{1} + n_{2}) \right] \ket{n_{1},n_{2}} $$
>$$J^{2}\ket{n} = \left( \frac{n^{2}}{4} + \frac{n}{2} \right)\ket{n} = \frac{n}{2}\left( \frac{n}{2}+1 \right)\ket{n}   $$
>所以自旋为 $\dfrac{n}{2}$

(c) Consider following perturbed Hamiltonian ($λ$ is small)
$$H = H_{0} + \lambda x_{1}^{2}p_{2}^{2} $$
Compute the first order correction to the energy for the energy level $n_{1}+n_{2}=n$.

>[!S]
>由微扰论，一阶修正由矩阵元
>$$\Delta E^{(1)}_{\{ n' \},\{ n \}} = \braket{ n'_{1},n'_{2} |V| n_{1},n_{2} } = \lambda \braket{ n'_{1} ,n'_{2} |x_{1}^{2}p_{2}^{2}| n_{1},n_{2} } = \lambda \braket{ n'_{1} |x_{1}^{2}| n_{1} }\braket{ n'_{2} |p_{2}^{2}| n_{2} }   $$
>给出，代入
>$$x_{1} = \sqrt{ \frac{\hbar}{2m\omega} }(a_{1}^{\dagger} + a_{1}) ,\quad p_{2}=i\sqrt{ \frac{\hbar m\omega}{2} }(a_{2}^{\dagger} - a_{2}) $$
>得
>$$\begin{align}
\braket{ n'_{1} |x_{1}^{2}| n_{1} } &  = \frac{\hbar}{2m\omega} \braket{ n'_{1} |a_{1}^{\dagger}a_{1}^{\dagger} + a_{1}^{\dagger}a_{1} + a_{1} a_{1}^{\dagger} + a_{1}a_{1}| n_{1} } \\ & = \frac{\hbar}{2m\omega}[\sqrt{ n_{1}(n_{1}-1) }\delta_{n_{1}',n_{1}-2} + (2n_{1}+1)\delta_{n_{1}',n_{1}} + \sqrt{ (n_{1}+1)(n_{1}+2) }\delta_{n_{1}',n_{1}+2}]
\end{align}$$
>$$\begin{align}
\braket{ n'_{2} |p_{2}^{2}| n_{2} } &  = - \frac{\hbar m\omega}{2}\braket{ n'_{2} |a_{2}^{\dagger}a_{2}^{\dagger} - a_{2}^{\dagger}a_{2} - a_{2}a_{2}^{\dagger} + a_{2}a_{2}| n_{2} } \\ &  = \frac{\hbar m\omega}{2}[-\sqrt{ n_{2}(n_{2}-1) }\delta_{n_{2}',n_{2}-2} + (2n_{2}+1)\delta_{n_{2}' n_{2}} - \sqrt{ (n_{2}+1)(n_{2}+2) }\delta_{n_{2}',n_{2}+2}] 
\end{align}$$
>于是微扰的表示矩阵是
>$$ \frac{\lambda \hbar^{2}}{4}\begin{pmatrix}
5 & 0 & -2 \\
0 & 9 & 0 \\
-2 & 0 & 5
\end{pmatrix} $$
>它的特征值是 $\frac{7\lambda \hbar^{2}}{4} , \frac{9\lambda \hbar^{2}}{4} , \frac{3\lambda \hbar^{2}}{4}$ 此即一阶修正本征能量值。

---

