---
up:
  - "[[写题]]"
related:
date: 2026-03-10
tags:
  - 理论力学
  - 习题
---


--- 
# 24年

Consider the motion of a particle of mass **m** in an attractive central potential of the form
$$V(r) = \alpha r^{k} \tag{1}$$
where **k** and **α** are real constants of the same sign (both positive or both negative).

(a) Write down the Lagrangian using polar coordinates $(r, φ)$.

>[!S]
>$$\begin{align}
L &= \frac{1}{2}m\mathbf{\dot{r}}^{2} - V\\&= \frac{1}{2}m(\dot{r}^{2} + r^{2}\dot{\varphi}^{2}) - \alpha r^{k}
\end{align}$$

(b) Using conservation of the angular momentum, reduce the problem of determining the radial motion to an effective one-dimensional problem (write down the effective Lagrangian).

>[!S]
>考虑到势为中心势，粒子角动量 $I=mr^{2}\dot{\varphi}$ 守恒，
>$$\dot{\varphi} = \frac{I}{mr^{2}} $$
>将拉式量对 $\varphi$ 做勒让德变换
>$$\begin{align}
R &= \dot{\varphi}I - L \\ &= -\frac{1}{2}m \dot{r}^{2} + \alpha r^{k} + \frac{I^{2}}{2mr^{2}} \end{align} $$
>取有效拉式量和有效势为
>$$L_{\text{eff}} = \frac{1}{2}m \dot{r}^{2} - V_{\text{eff}} ,\quad V_{\text{eff}} = \alpha r^{k} + \frac{I^{2}}{2mr^{2}} $$

(c) Determine the radius and period of the circular orbits.

>[!S]
>对于圆形轨道
>$$\frac{d}{dr}V_{\text{eff}} = 0 \implies r_{c} = \left( \frac{I^{2}}{\alpha km} \right)^{1/(k+2)} $$
>由角动量守恒得
>$$\dot{\varphi}_{c} = \frac{I}{mr_{c}^{2}} = \sqrt{ \frac{\alpha k}{m} r^{k} } $$
>周期为
>$$T = \frac{2\pi}{\dot{\varphi}} = 2\pi \sqrt{ \frac{m}{\alpha k} r^{-k} } $$

(d) For which values of k is the circular orbit stable?

>[!S]
>考虑有效势二阶导
>$$\frac{d^{2}}{dr^{2}} V_{\text{eff}} = \alpha k(k-1)r^{k-2} + \frac{3I^{2}}{mr^{4}} $$
>$$V_{\text{eff}}''(r_{c}) = \alpha k(k+2)r_{e}^{k-2} $$
>对于稳定轨道要求
>$$V_{\text{eff}}''(r_{c}) >0\implies k>-2 $$

(e) Assuming that the circular orbit is stable, consider a small perturbation around it. Find the period of the small oscillations. In the approximation of small oscillations, for which values of k will the orbit close?

>[!S]
>对于有效拉式量可导出其径向运动方程
>$$\frac{\partial L}{\partial r} = -\alpha kr^{k-1} - \frac{I^{2}}{mr^{3}} , \quad \frac{d}{dt} \frac{\partial L}{\partial \dot{r}} = m  \ddot{r} $$
>$$m  \ddot{r} = \frac{I^{2}}{mr^{3}} + \alpha kr^{k-1} $$
>考虑在稳定轨道附近的一个微小扰动 $r(t) = r_{c}(t) + \varepsilon(t),\varepsilon\ll r_{c}$ 则
>$$m\ddot{\varepsilon} = -\alpha k(k+2)r_{c}^{k-2}\varepsilon $$
>所以径向振动频率为
>$$\omega_{r} = \sqrt{ \frac{\alpha k(k+2)r_{c}^{k-2}}{m} } = \sqrt{ k+2 } \dot{\varphi} $$
>$$T_{r} = \frac{T_{\varphi}}{\sqrt{ k+2 }} $$
>若想轨道是封闭的，那么径向与角向的振动频率之比为有理数，即
>$$\sqrt{ k+2 } \in \mathbb{Q} $$


(f) Go back to the full 2d problem for r and φ (the polar coordinates in the plane of the orbit). Eliminate the time dependence and write a diffferential equation for the orbit.

>[!S]
>对于径向方程，考虑代换 $u = \frac{1}{r}$ 则
>$$\dot{r} = \frac{dr}{dt} = \frac{du}{d\varphi} \frac{dr}{du} \dot{\varphi} = -\frac{I}{m} \frac{du}{d\varphi} $$
>$$\ddot{r} = \frac{d}{dt}\left( -\frac{I}{m} \frac{du}{d\varphi} \right) = \frac{I^{2}u^{2}}{m^{2}} \frac{d^{2}u}{d\varphi^{2}} $$
>于是得到比奈方程
>$$m\ddot{r}=\frac{I^{2}}{mr^{3}} + \alpha kr^{k-1} \implies u'' = \frac{\alpha km}{I^{2}} u^{-(k+1)} - u $$
>

---
# 23年

Consider the Lagrangian
$$L(x,\dot{x},y,\dot{y}) = \frac{1}{2} \frac{\dot{x}^{2}+\dot{y}^{2}+2(x\dot{y}-y\dot{x})}{x^{2}+y^{2}} \tag{1} $$
(a) Compute the Hamiltonian $H(x, y, p_{x}, p_{y})$, and show the final form can be written as
$$\frac{1}{2}f(x,y)[(p_{x}-A_{x}(x,y))^{2} + (p_{y}-A_{y}(x,y))^{2}] \tag{2} $$
for some $f, A_{x}, A_{y}$. Find the vector potential $\vec{A}$ and then compute the corresponding magnetic field away from the origin. (Hint: recall that $\vec{B} = \text{curl} \vec{A} = \nabla \times \vec{A}$)

>[!S]
>$$p_{x} = \frac{\partial L}{\partial \dot{x}} = \frac{\dot{x}-y}{x^{2}+y^{2}} ,\quad p_{y} = \frac{\partial L}{\partial \dot{y}} = \frac{\dot{y}+x}{x^{2}+y^{2}} $$
>于是
>$$\dot{x} = (x^{2}+y^{2})p_{x} + y,\quad \dot{y} = (x^{2}+y^{2})p_{y} - x$$
>勒让德变换得到哈密顿量
>$$\begin{align}
H &= \dot{x}p_{x} + \dot{y}p_{y} - L \\ & = \frac{1}{2} \frac{2\dot{x}^{2} - 2y\dot{x} + 2\dot{y}^{2} + 2x\dot{y} - \dot{x}^{2} - \dot{y}^{2} - 2x\dot{y} + 2y\dot{x}}{x^{2}+y^{2}} \\ & = \frac{1}{2} \frac{\dot{x}^{2} + \dot{y}^{2}}{x^{2}+y^{2}} \\ & = \frac{1}{2} (x^{2}+y^{2})\left[  \left( p_{x} + \frac{y}{x^{2}+y^{2}} \right)^{2} + \left( p_{y} - \frac{x}{x^{2}+y^{2}} \right)^{2}  \right]
\end{align} $$
>于是
>$$f(x,y) = x^{2}+y^{2} ,\quad A_{x} = -\frac{y}{x^{2}+y^{2}} , \quad A_{y} = \frac{x}{x^{2}+y^{2}} $$
>与之相关的磁场有
>$$\mathbf{B} = \nabla \times \mathbf{A} = \frac{\partial A_{x}}{\partial y} - \frac{\partial A_{y}}{\partial x} = 0 $$

(b) Prove that the Lagrangian $L(x, y, \dot{x}, \dot{y})$ is invariant under two symmetries: rotations and scale transformations.

>[!S]
>旋转变换：
>$$R: \begin{pmatrix}
x \\y
\end{pmatrix} \to \begin{pmatrix}
\cos \theta & \sin \theta \\ -\sin \theta & \cos \theta
\end{pmatrix}\begin{pmatrix}
x \\ y
\end{pmatrix} $$
>则
>$$\dot{x}' = \cos \theta \dot{x} + \sin \theta \dot{y} ,\quad \dot{y}'=-\sin \theta \dot{x} + \cos \theta \dot{y} $$
>由于旋转变换是幺正的，保模长所以 $x^{2}+y^{2}=x'^{2}+y'^{2}$ 速度类似
>$$\begin{align}
L\to L' & = \frac{1}{2} \frac{\dot{x}'^{2}+\dot{y}'^{2}+2(x'\dot{y}'-y'\dot{x}')}{x'^{2}+y'^{2}} \\ & = \frac{1}{2} \frac{\dot{x}^{2}+\dot{y}^{2} + 2\{ (\cos \theta x+\sin \theta y)(-\sin \theta \dot{x}+\cos \theta \dot{y}) - (x\leftrightarrow y) \}}{x^{2}+y^{2}} \\ & = \frac{1}{2} \frac{\dot{x}^{2}+\dot{y}^{2} + 2\{ (-\cos \theta \sin \theta x \dot{x} + \cos ^{2}\theta x\dot{y}-\sin ^{2}y\dot{x}+\sin \theta \cos \theta y\dot{y}) + \dots \}}{x^{2}+y^{2}} \\ & = \frac{1}{2} \frac{\dot{x}^{2}+\dot{y}^{2}+2(x\dot{y}-y\dot{x})}{x^{2}+y^{2}}\\ & =L
\end{align} $$
>可见拉式量在旋转变换下保持不变
>
>标度变换：
>$$D: \begin{pmatrix}
x\\ y
\end{pmatrix} \to \lambda \begin{pmatrix}
x \\ y
\end{pmatrix} $$
>则 $\dot{x}'=\lambda \dot{x},\dot{y}'=\lambda \dot{y}$ 于是
>$$\begin{align}
L\to L' & = \frac{1}{2} \frac{(\lambda \dot{x})^{2}+(\lambda \dot{y})^{2}+2(\lambda^{2}x\dot{y}-\lambda^{2}y\dot{x})}{(\lambda x)^{2}+(\lambda y)^{2}} \\ & = \frac{1}{2} \frac{\dot{x}^{2}+\dot{y}^{2}+2(x\dot{y}-y\dot{x})}{x^{2}+y^{2}} \\  & =L
\end{align} $$
>可见拉式量在标度变换下也保持不变

(c) Derive the conserved quantities for both symmetries

>[!S]
>旋转变换：
>坐标无穷小变换为
>$$\delta x = y\delta \theta ,\quad \delta y = -x\delta \theta $$
>于是对应的守恒荷是
>$$Q_{R} = \frac{\partial L}{\partial x}\delta x + \frac{\partial L}{\partial y}\delta y = (yp_{x}-xp_{y})\delta \theta $$
>守恒量是
>$$L = yp_{x} - xp_{y} $$
>
>标度变换：
>坐标无穷小变换为
>$$\delta x = \varepsilon x , \quad \delta y = \varepsilon y $$
>$$Q_{D} = \frac{\partial L}{\partial x}\delta x + \frac{\partial L}{\partial y}\delta y = \varepsilon(xp_{x} + yp_{y}) $$
>$$D = xp_{x} + yp_{y} $$

(d) Rewrite the Lagrangian in polar coordinates, write down the Euler-Lagrange equations and solve them.

>[!S]
>极坐标下
>$$x = r\cos \theta , \quad y = r\sin \theta , \quad \dot{x} = \dot{r}\cos \theta - r\dot{\theta}\sin \theta , \quad \dot{y} = \dot{r}\sin \theta + r\dot{\theta}\cos \theta $$
>于是
>$$L = \frac{1}{2}\left( \frac{\dot{r}^{2}}{r^{2}} + \dot{\theta}^{2} + 2\dot{\theta} \right) $$
>对于 $\theta$ :
>$$\frac{\partial L}{\partial \theta} = 0 ,\quad \frac{d}{dt} \frac{\partial L}{\partial \dot{\theta}} = \ddot{\theta} $$
>$$\ddot{\theta} = 0 \implies \theta = At + B $$
>对于 $r$ :
>$$\frac{\partial L}{\partial r} = -\frac{\dot{r}^{2}}{r^{3}} , \quad \frac{d}{dt}\frac{\partial L}{\partial\dot{r}} = \frac{d}{dt}\left( \frac{\dot{r}}{r^{2}} \right) = \frac{\ddot{r}}{r^{2}} - \frac{2\dot{r}^{2}}{r^{3}} $$
>$$\frac{\ddot{r}}{r^{2}} - \frac{2\dot{r}^{2}}{r^{3}} + \frac{\dot{r}^{2}}{r^{3}} = 0 \implies r \ddot{r} = \dot{r}^{2} $$
>由于
>$$r \frac{d}{dt}(\dot{r}) = r \frac{d}{dr}(\dot{r}) \frac{dt}{dr} $$
>所以
>$$\frac{1}{\dot{r}^{3}} \frac{d\dot{r}}{dr} = \frac{1}{r^{2}} \implies  \dot{r} = Cr \implies r = De^{ Ct } $$

---
# 22年

