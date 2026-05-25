---
up:
  - "[[写题]]"
related:
  - "[[电动力学知识点]]"
date: 2026-04-05
tags:
  - 电动力学
  - 习题
---

# 25 年

Consider a wave packet with a transverse profile $E_{o}(x,y)$ propagating in the $z$ direction (see eq (3) for a complete specification of $\mathbf{E}$ and $\mathbf{B}$). Although the precise form of $E_{o}(x,y)$ is not needed below, for definiteness you may assume that the wave packet has a Gaussian profile for
$$E_{o}(x,y) = \mathcal{A}e^{-\frac{x^{2} + y^{2}}{4\sigma^{2}}}, \quad (1)$$
and is infinitely broad in the $z$ direction. The following integrals may be useful:
$$\begin{array}{l}\int_{-\infty}^{\infty}due^{-\alpha u^2} = \sqrt{\frac{\pi}{\alpha}},\\ \displaystyle \int_{-\infty}^{\infty}due^{-\alpha u^2}e^{iku} = \sqrt{\pi} e^{-\frac{k^2}{4\alpha}}. \end{array} \quad (2)$$

(a) When all derivatives of $E_{o}(x,y)$ are neglected, show that in Gaussian (Heaviside-Lorentz) units
$$\begin{array}{l}\mathbf{E}^{(0)}(t,\mathbf{r}) = E_{o}(x,y)e^{i(kz - \omega t)}\frac{\hat{\mathbf{x}} + i\hat{\mathbf{y}}}{\sqrt{2}},\\ \mathbf{B}^{(0)}(t,\mathbf{r}) = \hat{\mathbf{z}}\times \mathbf{E}^{(0)}, \end{array} \quad (3)$$
is a solution to the Maxwell equations for $\omega = ck$. Here $\mathbf{x}$, $\mathbf{y}$ and $\mathbf{z}$ are unit vectors in $x$, $y$, $z$ directions.

>[!solution]- 
>$$\mathbf{E} = E_{0}(x,y)e^{ i(kz-\omega t) }\mathbf{e} ,\quad \mathbf{e} = \frac{\hat{x}+i\hat{y}}{\sqrt{ 2 }} ,\quad \mathbf{B} = \hat{z}\times \mathbf{E} $$
>Firstly $\nabla\cdot \mathbf{E}=0$:
>$$\begin{align} \nabla\cdot \mathbf{E} & = \nabla\cdot(E_{0}(x,y)e^{ i(kz-\omega t) }\mathbf{e}) \\ & = (\nabla E_{0})\cdot \mathbf{e}e^{ i(kz-\omega t) } + E_{0}(\nabla e^{ i(kz-\omega t) })\cdot \mathbf{e} \\ & \approx E_{0}(ike^{ i(kz-\omega t) }\hat{z})\cdot \mathbf{e} \\ & = 0 \end{align} $$
>where i used the condition *all derivatives of $E_{o}(x,y)$ are neglected*. Next $\nabla\cdot \mathbf{B}=0$:
>$$\begin{align} \nabla\cdot \mathbf{B} & = \nabla\cdot(\hat{z}\times \mathbf{E})\\ & = \nabla\cdot(E_{x}\hat{y} - E_{y}\hat{x}) \\ & = \frac{1}{\sqrt{ 2 }}e^{ i(kz-\omega t) }\left( \frac{\partial E_{0}}{\partial y} - i \frac{\partial E_{0}}{\partial x} \right) \\ & \approx 0 \end{align} $$
>Next $\nabla \times \mathbf{E} = -\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t}$ :
>$$\begin{align} \nabla \times \mathbf{E} & = \nabla \times(E_{0}e^{ i(kz-\omega t) }\mathbf{e}) \\ & = e^{ i(kz-\omega t) }(\nabla E_{0} + ikE_{0}\hat{z})\times \mathbf{e} \\ & \approx e^{ i(kz-\omega t) }ik\hat{z}\times(E_{0}\mathbf{e}) \\ & = ik\mathbf{B} \\ & = \frac{i\omega}{c} E_{0}e^{ i(kz-\omega t) }\hat{z}\times \mathbf{e} \\ & = -\frac{1}{c}\frac{\partial }{\partial t}(E_{0}e^{ i(kz-\omega t) }\hat{z}\times \mathbf{e}) \\ & = -\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t} \end{align} $$
>Finaly $\nabla \times \mathbf{B} = \frac{1}{c}\frac{\partial \mathbf{E}}{\partial t}$:
>$$\begin{align} \nabla \times \mathbf{B} & = \nabla \times(\hat{z}\times \mathbf{E}) \\ & = \hat{z}(\nabla\cdot \mathbf{E}) - (\hat{z}\cdot \nabla)\mathbf{E} \\ & = -\partial_{z}(E_{0}e^{ i(kz-\omega t) }\mathbf{e})\\ & = -ikE_{0}e^{ i(kz-\omega t) }\mathbf{e} \\ & = -\frac{i\omega}{c} E_{0}e^{ i(kz-\omega t) }\mathbf{e} \\ & = \frac{1}{c}\frac{\partial }{\partial t}(E_{0}e^{ i(kz-\omega t) }\mathbf{e}) \\ & = \frac{1}{c}\frac{\partial \mathbf{E}}{\partial t} \end{align} $$
>$$\text{QED.} $$

(b) Calculate the time averaged energy per length in the wave packet, $\langle U \rangle$.

>[!solution]-
>The energy density with time avrange is
>$$\braket{ u } = \frac{1}{4}(\braket{ \mathbf{E} }^{2} + \braket{ \mathbf{B} }^{2}  ) = \frac{1}{2}|E_{0}|^{2} $$
>So the averaged energy per length in the wave packet is
>$$\begin{align} \braket{ U } & = \iint_{\mathbb{R}^{2}} \frac{A^{2}}{2}\exp\left( -\frac{x^{2}+y^{2}}{2\sigma^{2}} \right)dxdy \\ & = \frac{A^{2}}{2}\left( \int_{\mathbb{R}} \exp\left( -\frac{x^{2}}{2\sigma^{2}} \right)dx \right)^{2} \\ & = \frac{A^{2}}{2}(\sqrt{ 2\pi }\sigma)^{2} \\ & = \pi \sigma^{2}A^{2} \end{align} $$

(c) When the derivatives of $E_{o}(x,y)$ are not neglected, eq (3) is not a solution to the Maxwell equations. Determine the corrections to $\mathbf{E}^{(0)}$ and $\mathbf{B}^{(0)}$ to first order in gradients for $k\sigma \gg 1$.

   Hint: try a solution for $\mathbf{E}$ (and analogously for $\mathbf{B}$) of the form
	$$\mathbf{E}(t,\mathbf{r}) = \mathbf{E}^{(0)} + \mathbf{E}^{(1)}(x,y)e^{i(kx - \omega t)}\hat{\mathbf{z}}, \quad (4)$$
	and determine the correction $\mathbf{E}^{(1)}(x,y)$ in terms of $E_{o}(x,y)$ and its derivatives.

>[!solution]-
>Set $\mathbf{E}=\mathbf{E}^{(0)}+\mathbf{E}^{(1)}$ , for the $\nabla\cdot \mathbf{E}=0$ 
>$$\nabla\cdot \mathbf{E}^{(0)} \equiv -\frac{A(\mathbf{x}+\mathbf{y})\cdot \mathbf{e}}{2\sigma^{2}}\exp\left( -\frac{x^{2}+y^{2}}{4\sigma^{2}} \right)e^{ i(kz-\omega t) } $$
>we still think $\mathbf{E}^{(1)}=\psi(x,y)e^{ i(kz-\omega t) }\hat{z}$ and all derivatives of $\psi(x,y)$ are neglected
>$$\nabla\cdot \mathbf{E}^{(1)} = ik\psi e^{ i(kz-\omega t) } $$
>so
>$$\psi = \frac{i}{\sqrt{ 2 }k}(\nabla E_{0}) = -\frac{i}{\sqrt{ 2 }k}\cdot \frac{x+y}{2\sigma^{2}}E_{0} $$
>and
>$$\mathbf{B}^{(1)} = \left( \frac{1}{ik}\nabla \times \mathbf{E}^{(1)} \right) = -\frac{1}{\sqrt{ 2 }k}\left(  \frac{x+iy}{2\sigma^{2}}  \right)E_{0}e^{ i(kz-\omega t) }\hat{z}  $$

(d) Write the solution to the last question as a linear superposition of the plane wave solutions to the Maxwell equations. First use the superposition to qualitatively explain why there is the correction to the electric field parallel to $\hat{\mathbf{z}}$, and then use the superposition to precisely reproduce this correction.

>[!solution]-
>将 $\mathbf{E}$ 表示为单色平面波的角谱叠加
>$$\mathbf{E} = \iint \frac{dk_{x}dk_{y}}{(2\pi)^{2}} \mathbf{A}(k_{x},k_{y})e^{ i(k_{x}x+k_{y}y+k_{z}z) } $$
>其中 $k_{z}=\sqrt{ k^{2}-k_{x}^{2}-k_{y}^{2} },k=\omega /c$ 振幅 $\mathbf{A}$ 满足横波条件 $\mathbf{A}\cdot \mathbf{k}=0$ 在 $z=0$ 平面有
>$$E_{t}=E_{0} \mathbf{e}\implies \tilde{E}_{0} = \iint \frac{dxdy}{(2\pi)^{2}} E_{0}(x,y)e^{ -i(k_{x}x+k_{y}y) } $$
>故对比可取
>$$\mathbf{A} = \tilde{E}_{0}(k_{x},k_{y})\left[  \mathbf{e} - \frac{k_{x}\hat{x}+k_{y}\hat{y}}{\sqrt{ 2 }}\cdot \frac{k_{x}+ik_{y}}{\sqrt{ 2 }}  \right] $$
>在傍轴条件下 $k\sigma\gg 1$ 有 $k_{x,y}\sim \frac{1}{\sigma}\ll k$ 于是
>$$k_{z} = k\sqrt{ 1 - \frac{k_{x}^{2}+k_{y}^{2}}{k^{2}} } \approx k - \frac{k_{x}^{2}+k_{y}^{2}}{2k^{2}} $$
>$$\begin{align}\mathbf{E} & = \iint \frac{dk_{x}dk_{y}}{(2\pi)^{2}} \tilde{E}_{0}(k_{x},k_{y})\left[  \mathbf{e} - \frac{k_{x}\hat{x}+k_{y}\hat{y}}{\sqrt{ 2 }}\cdot \frac{k_{x}+ik_{y}}{\sqrt{ 2 }}  \right] e^{ i(k_{x}x+k_{y}y) }\exp\left(  -i \frac{k_{x}^{2}+k_{y}^{2}}{2k^{2}}z  \right) \\ E_{z} & \approx -e^{ -ikz } \iint \frac{dk_{x}dk_{y}}{(2\pi)^{2}} \tilde{E}_{0} \frac{k_{x}+ik_{y}}{k}e^{ ik_{x}x + ik_{y}y } \\ & = -\frac{e^{ -ikz }}{z}\cdot i\left( \frac{\partial }{\partial x} + \frac{\partial }{\partial y} \right)E_{0}(x,y) \\ & = \frac{i}{k\sqrt{ 2 }} e^{ ikz }\left(  \frac{\partial E_{0}}{\partial x} + i\frac{\partial E_{0}}{\partial y} \right)
\end{align} $$ 

(e) Calculate the $z$-component of the time averaged angular momentum per length in the wave packet, $\langle L^z \rangle$, to the lowest non-trivial order in $k\sigma$.

>[!solution]-
>$$\braket{ \mathbf{l} } = \frac{1}{2c}\mathbf{r}\times \mathrm{Re}(\mathbf{E}\times \mathbf{B}^{*}) $$
>$$\braket{ l_{z} } = \frac{1}{2c}[ x\mathrm{Re}(\mathbf{E}\times \mathbf{B}^{*})_{z} - z\mathrm{Re}(\mathbf{E}\times \mathbf{B}^{*})_{x} ] $$
>Form (c)
>$$\mathbf{E} = \mathbf{E}^{(0)} + \mathbf{E}^{(1)} ,\quad \mathbf{B} = \mathbf{B}^{(0)} + \mathbf{B}^{(1)} $$
>$$\begin{gather} \mathbf{E}^{(0)} = E_{0}e^{ i(kz-\omega t) }\mathbf{e}  & , & \mathbf{B}^{(0)} = \hat{z}\times \mathbf{E}^{(0)} \\ \mathbf{E}^{(1)} = \psi e^{ i(kz-\omega t) }\hat{z} & , & \mathbf{B}^{(1)} = \chi e^{ i(kz-\omega t) }\hat{z} \\ \psi(x,y) = \frac{i}{k\sqrt{ 2 }}(\partial_{x}+i\partial_{y})E_{0} & , & \chi(x,y) = \frac{1}{k\sqrt{ 2 }}(\partial_{x}+i\partial_{y})E_{0} \end{gather} $$
>So $\mathbf{B} = -i\mathbf{E}$ that
>$$\mathbf{E}\times \mathbf{B}^{*}= \mathbf{E}\times(i\mathbf{E}^{*}) = -iE_{0}^{2}\hat{z} + iE_{0}(\psi^{*}\mathbf{e} + \psi \mathbf{e}^{*}) $$
>$$\braket{ l_{z} } = \frac{1}{2c}\left[  -\frac{E_{0}}{k}(x\partial_{x}+y\partial_{y})E_{0} \right] $$
>$$\begin{align} \braket{ L_{z} } & = \iint dxdy\ \braket{ l_{z} } = -\frac{1}{2ck}\iint E_{0}(x\partial_{x}+y\partial_{y})E_{0} \ dxdy \\ & = -\frac{1}{4ck} \iint (x\partial_{x} + y\partial_{y}) E_{0}^{2}\ dxdy \\ & = \frac{1}{4ck} \iint E_{0}^{2}\ dxdy \\ & = \frac{\braket{ U }}{ck} = \frac{\braket{ U }}{\omega}  \end{align} $$

(f) Determine the ratio $\langle L^z \rangle / \langle U \rangle$. Interpret the result using photons.

>[!solution]-
>As the (e) said 
>$$\frac{\braket{ L_{z} }}{\braket{ U } } = \omega  $$
>For the photos, it has $L_{z}=\hbar$ and $E=\hbar \omega$ , so the above means that each photos gives the system $L_{z}=\hbar$ and $E=\hbar \omega$ , absolutly the system will show 
>$$\frac{\braket{ L_{z} }}{\braket{ U } } = \omega  $$

---

# 24 年

Consider an ohmic metal with high (but not infinite) conductivity $\sigma$ and magnetic permeability $\mu = 1$ in Heaviside-Lorentz units ($\mu = \mu_0$ in SI units).

(a) Show that for harmonic time dependence, and high conductivity ($\sigma \gg \omega$ in Heaviside-Lorentz units; $\frac{\sigma}{\epsilon_0} \gg \omega$ in SI units), that damped wave-like solutions propagating in $z$-direction in the metal take the approximate form

$$\mathbf{H}(t,z) = \mathbf{H}_c e^{-i\omega t + ik_c z} \quad (3)$$

where

$$k_c = \frac{1 + i}{\sqrt{2}}\frac{\sqrt{\sigma\omega}}{c} \quad (4)$$

in Heaviside-Lorentz units, or

$$k_c = \frac{1 + i}{\sqrt{2}}\frac{\sqrt{\sigma\omega / \epsilon_0}}{c} \quad (5)$$

in SI units.

>[!solution]-
>在 Lorentz 单位制下 Maxwell 源方程是
>$$\nabla \times \mathbf{B} = \frac{1}{c}\left( \sigma \mathbf{E} + \frac{\partial \mathbf{E}}{\partial t} \right) ,\quad \nabla \times \mathbf{E} = -\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t} $$
>对于谐变场 $\mathbf{E}(t,\mathbf{r})=\mathbf{E}(\mathbf{r})e^{ -i\omega t },\mathbf{H}(t,\mathbf{r})=\mathbf{H}(\mathbf{r})e^{ -i\omega t }$ 时间导数 $\partial_{t}\to -i\omega$ 得到
>$$\nabla \times \mathbf{H} = \frac{\sigma-i\omega}{c}\mathbf{E} ,\quad \nabla \times \mathbf{E} = \frac{i\omega}{c}\mathbf{H} $$
>于是
>$$\nabla \times\left( \frac{c}{i\omega} \nabla \times \mathbf{E} \right) = -\frac{ic}{\omega} [ \nabla(\nabla\cdot \mathbf{E}) - \nabla^{2}\mathbf{E} ] = \frac{ic}{\omega} \nabla^{2}\mathbf{E} = \frac{\sigma-i\omega}{c}\mathbf{E} $$
>$$\nabla^{2}\mathbf{E} + \frac{\omega^{2}}{c^{2}}\left( 1 + \frac{i\sigma}{\omega} \right)\mathbf{E} = 0 $$
>这是一个三维的波动方程，令 $k^{2} = \frac{\omega^{2}}{c^{2}}\left( 1+ \frac{i\sigma}{\omega} \right)$ 则
>$$k = \frac{\omega}{c}\sqrt{ 1+\frac{i\sigma}{\omega} } \approx \frac{\omega}{c}\sqrt{ \frac{i\sigma}{\omega} } = \frac{1 + i}{\sqrt{ 2 }} \frac{\sqrt{ \sigma \omega }}{c} $$
>
>


(b) The electric field obeys a similar equation, $\mathbf{E}(t,z) = \mathbf{E}_c e^{-i\omega t + ik_c z}$. Use the Maxwell equations to express the amplitude of the electric field $\mathbf{E}_c$ in terms of the magnetic field $\mathbf{H}_c$.

>[!solution]-
>$$\mathbf{E}(t,z) = \mathbf{E}_{c}e^{ -i\omega t + ik_{c}z } ,\quad \mathbf{H}(t,z) = \mathbf{H}_{c}e^{ -i\omega t+ik_{zc}c } $$
>由 $\nabla \times \mathbf{E}=-\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t}$ 知
>$$ik_{c}\hat{z}\times \mathbf{E} = \frac{i\omega}{c}\mathbf{H} $$
>$$\mathbf{E} = \frac{\omega}{ck_{c}}\mathbf{H}\times \hat{z} $$
>

(c) Now consider a linearly polarized plane wave in vacuum of frequency $\omega$, which is normally incident upon a semi-infinite metal block with infinite conductivity as shown below.

>[!solution]-
>对于电导率无限的导体，电磁波无法穿透，在表面全反射，垂直入射波可表示为
>$$\mathbf{E}_{i} = E_{0}\hat{x}e^{ -i\omega t+ik_{c}z } ,\quad \mathbf{H}_{i} = H_{0}\hat{y}e^{ -i\omega t+ik_{c}z } $$
>反射波仅仅改变一个相位，于是可以表示为
>$$\mathbf{E}_{r} = -E_{0}\hat{x}e^{ -i\omega t-ik_{c}z } ,\quad \mathbf{H}_{r} = -H_{0}\hat{y}e^{ -i\omega t-ik_{c}z } $$
>两波叠加形成驻波
>$$\begin{gather} \mathbf{E} = \mathbf{E}_{i} + \mathbf{E}_{r} = E_{0}\hat{x}e^{ -i\omega t }(e^{ ik_{c}z } - e^{ -ik_{c}z }) = 2iE_{0} \sin k_{c}z \hat{x} \\ \mathbf{H} = \mathbf{H}_{i} + \mathbf{H}_{r} = H_{0}\hat{x}e^{ -i\omega t }(e^{ ik_{c}z } - e^{ -ik_{c}z }) = 2iH_{0} \sin k_{c}z \hat{x} \end{gather} $$


When the metal has infinite conductivity, the amplitude of the reflected wave equals the amplitude of the incident wave, but the polarization of the reflected wave is inverted. Explain this fact using the appropriate boundary conditions.

(d) Now consider the same reflection problem as in part (c), but this time the metal has a large (but finite) conductivity $\sigma$. Determine the electric and magnetic fields in the metal to leading order in $\omega / \sigma$. Let the amplitude of the incident wave be $E_I$.

>[!solution]-
>对于透射波
>$$\mathbf{E}_{t} = E_{t}e^{ -i\omega t + ik_{c}z }\hat{x} $$
>在边界处场连续
>$$E_{t} = E_{0}(1-i)\sqrt{ \frac{2\omega}{\sigma} } $$
>

---

# 23 年

One can express the electric fields $\vec{E}$ and magnetic fields $\vec{B}$ in terms of the scalar and vector potentials, $A^{\mu} = (\phi ,\vec{A})$.

(a) Write down the expression of $\vec{E}$ and $\vec{B}$ in terms of $(\phi ,\vec{A})$ and show that the result is unchanged under gauge transformation

$$\phi \rightarrow \phi +\frac{\partial}{\partial t} f,\quad \vec{A}\rightarrow \vec{A} -\nabla f, \quad (4)$$

where $f = f(\vec{x},t)$ is a scalar function.

>[!solution]-
>$$\mathbf{E} = -\nabla \phi - \frac{\partial \mathbf{A}}{\partial t} ,\quad \mathbf{B} = \nabla \times \mathbf{A} $$
>under gauge transformation
>$$\mathbf{E} \to -\nabla\left( \phi + \frac{\partial f}{\partial t} \right) - \frac{\partial }{\partial t}(\mathbf{A} - \nabla f) = -\nabla \phi - \frac{\partial \mathbf{A}}{\partial t} - \nabla \partial_{t}f + \partial_{t}\nabla f = \mathbf{E} $$
>$$\mathbf{B} \to \nabla \times(\mathbf{A} - \nabla f) = \mathbf{B} - \nabla \times(\nabla f) = \mathbf{B} $$

(b) Show that two of the 4 Maxwell equations of $\vec{E}$ and $\vec{B}$ are satisfied automatically in terms of $A^{\mu} = (\phi ,\vec{A})$.

>[!solution]-
>1. 
>$$\nabla \times \mathbf{E} = -\nabla \times\left( \nabla \phi - \frac{\partial \mathbf{A}}{\partial t} \right) = \frac{\partial }{\partial t}(\nabla \times \mathbf{A}) = \frac{\partial \mathbf{B}}{\partial t} $$
>2. 
>$$\nabla\cdot \mathbf{B} = \nabla\cdot(\nabla \times \mathbf{A}) = 0$$

(c) Derive the equations for the scalar and vector potentials from the remaining Maxwell equations in Lorentz gauge.

$$\frac{1}{c}\partial_{t}\phi +\nabla \cdot \vec{A} = 0, \quad (5)$$

>[!solution]-
>set $c=1$ 
>$$\nabla\cdot \mathbf{E} = -\nabla\cdot\left( \nabla \phi + \frac{\partial \mathbf{A}}{\partial t} \right) = -\nabla^{2}\phi - \frac{\partial}{\partial t}(\nabla\cdot \mathbf{A}) = -\nabla^{2}\phi - \frac{\partial }{\partial t}\left( \frac{\partial \phi}{\partial t} \right) = \Box\phi = 4\pi\rho$$
>i.e.
>$$\Box\phi=4\pi \rho $$
>Another:
>$$\nabla \times \mathbf{B} = \nabla \times(\nabla \times \mathbf{A}) = \nabla(\nabla\cdot \mathbf{A}) - \nabla^{2}\mathbf{A}  $$
>$$\nabla \times \mathbf{B} + \frac{\partial \mathbf{E}}{\partial t} = \nabla\left( \nabla\cdot \mathbf{A} + \frac{\partial \phi}{\partial t} \right) + \frac{\partial^{2} \mathbf{A}}{\partial t^{2}} - \nabla^{2}\mathbf{A} = \Box\mathbf{A} = 4\pi \mathbf{J} $$
>i.e.
>$$\Box\mathbf{A} = 4\pi \mathbf{J} $$


(d) Recall that the Green's function of the wave equation

$$\left(\frac{1}{c^2}\partial_t^2 -\nabla^2\right)G(t,\vec{r}) = \delta (t)\delta^3 (\vec{r}) \quad (6)$$

is

$$G(t - t_0,\vec{r} -\vec{r}_0) = \frac{\theta(t - t_0)}{4\pi|\vec{r} - \vec{r}_0|}\delta \left(t - t_0 - \frac{|\vec{r} - \vec{r}_0|}{c}\right). \quad (7)$$

Assume a particle of electric charge $e$ moves with trajectory $\vec{R} (t)$ with $\vec{v} (t) = d\vec{R} (t) / dt$. Use the Green's function to derive the potential $\phi (\vec{r},t)$ and $\vec{A} (\vec{r},t)$ of this particle at $(\vec{r},t)$. You may assume that $|\vec{R} (t)|\ll |\vec{r} |$, $|\vec{R} (t)|\ll ct$ and $|\vec{v} (t)|\ll c$ and expand your result up to the order $\mathcal{O}(1 / |\vec{r} |)$ and $\mathcal{O}(|\vec{v} (t)| / c)$. This is also called non-relativistic and far-field approximations.

>[!solution]-
>the solution of wave equation is
>$$\begin{gather} \phi(t,\mathbf{r}) = \int dt'd^{3}r'\ G(t-t',\mathbf{r}-\mathbf{r}')\rho(\mathbf{r}') \\ \mathbf{A}(t,\mathbf{r}) = \int dt'd^{3}r' G(t-t',\mathbf{r}-\mathbf{r}')\mathbf{J}(\mathbf{r}') \end{gather} $$
>the charge's distribution is
>$$\rho(\mathbf{r}',t')= e\delta^{3}(\mathbf{r}-\mathbf{R}(t')) ,\quad \mathbf{J}(\mathbf{r}',t') = e\mathbf{v}(t')\delta^{3}(\mathbf{r}-\mathbf{R}(t')) $$
>put it in and integrate over $\mathbf{r}'$ we get 
>$$\begin{gather} \phi(t',\mathbf{r}') = e\int dt'\ \frac{\theta(t-t')}{4\pi|\mathbf{r}-\mathbf{R(t')}|}\delta(t-t'-|\mathbf{r}-\mathbf{R}(t')|) \\ \mathbf{A}(t',\mathbf{r}') = e\int dt'\ \frac{\mathbf{v}(t')\theta(t-t')}{4\pi|\mathbf{r}-\mathbf{R}(t')|}\delta(t-t'-|\mathbf{r}-\mathbf{R}(t')|) \end{gather} $$
>where
>$$\delta(t-t'-|\mathbf{r}-\mathbf{R}(t')|) = \frac{\delta(t'-t_{res})}{|-1 - \frac{d}{dt'}|\mathbf{r}-\mathbf{R}||} = \frac{\delta(t'-t_{res})}{1 - \mathbf{v}(t')\cdot \mathbf{n}(t')} $$
>$$t_{res} = t - |\mathbf{r}-\mathbf{R}(t_{res})| ,\quad \mathbf{n} = \frac{\mathbf{r}-\mathbf{R}}{|\mathbf{r}-\mathbf{R}|} $$
>Under $|\vec{R} (t)|\ll |\vec{r} |$, $|\vec{R} (t)|\ll ct$ and $|\vec{v} (t)|\ll c$ we get
>$$|\mathbf{r}-\mathbf{R}| = \mathbf{r} - \mathbf{n}\cdot \mathbf{R} + \mathcal{O}\left( \frac{R^{2}}{r} \right) $$
>$$t_{res} = t - r + \mathbf{R}\cdot \mathbf{n} + \mathcal{O}\left( \frac{R}{r} \right) $$
>$$\frac{1}{1-\mathbf{v}\cdot \mathbf{n}} = 1 + \mathbf{v}\cdot \mathbf{n} + \mathcal{O}(v^{2}) $$
>So
>$$\phi(t,\mathbf{r}) = \frac{e}{r}\left( 1 + \mathbf{v}\cdot \mathbf{n} \right) = \frac{e}{r} + \frac{e}{r}\mathbf{v}\cdot \mathbf{n}(t-r) $$
>$$\mathbf{A}(t,\mathbf{r}) = \frac{e\mathbf{v}}{r}(1+\mathbf{v}\cdot \mathbf{n}) = \frac{e}{r}\mathbf{v}(t-r) $$
