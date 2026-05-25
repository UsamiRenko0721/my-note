---
up:
  - "[[写题]]"
related:
date:
tags:
  - 量子场论
  - 习题
---
# 2.1 经典电磁场

经典电磁学（无源）的作用量为

$$S = \int d^4x \left( -\frac{1}{4} F_{\mu\nu} F^{\mu\nu} \right)$$

其中 $F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$。

---
## **(a)** 
将分量 $A_\mu(x)$ 视为动力学变量，推导该作用量的欧拉-拉格朗日方程作为麦克斯韦方程。通过定义 $E^i = -F^{0i}$ 和 $\epsilon^{ijk} B^k = -F^{ij}$，将方程写成标准形式。


我们知道 $A^{\mu}$ 和 $\partial_{\mu}A_{\nu}$ 是独立变量
$$\frac{\partial F_{\mu \nu}}{\partial(\partial_{\rho}A_{\sigma})} = \frac{\partial(\partial_{\mu}A_{\nu} - \partial_{\nu}A_{\mu})}{\partial(\partial_{\rho}A_{\sigma})} = \delta^{\rho}_{\mu}\delta^{\sigma}_{\nu} - \delta^{\rho}_{\nu}\delta^{\sigma}_{\mu} , \quad \frac{\partial F_{\mu \nu}}{\partial A_{\rho}} = \frac{\partial(\partial_{\mu}A_{\nu} - \partial_{\nu}A_{\mu})}{\partial A_{\rho}} = 0 $$
$$\frac{\partial\mathcal L}{\partial(\partial_{\rho}A_{\sigma})} = -\frac{2}{4} ( \delta^{\rho}_{\mu}\delta^{\sigma}_{\nu} - \delta^{\rho}_{\nu}\delta^{\sigma}_{\mu} ) F^{\mu \nu} = -\frac{1}{2}( F^{\rho \sigma} - F^{\sigma \rho} ) = -F^{\rho \sigma} , \quad \frac{\partial\mathcal L}{\partial A_{\mu}} = 0 $$
有欧拉-拉格朗日方程得到
$$ 0 = \partial_{\mu}\left(  \frac{\partial\mathcal L}{\partial(\partial_{\mu}A_{\nu})}  \right) - \frac{\partial\mathcal L}{\partial A_{\nu}} = -\partial_{\mu}F^{\mu \nu} = 0 $$
所以麦克斯韦方程就是
$$\partial_{\mu}F^{\mu \nu} = 0 $$
考虑到 $E^{i}=F^{i 0}$ , $\varepsilon^{ijk}B^{k} =-F^{ij}$ 代入得到
$$\begin{gather}
\partial_{i}F^{i 0} = \nabla \cdot \mathbf{E} = 0 \\
\partial_{i}F^{ij} = \nabla \cdot \mathbf{B} = 0  \\
\varepsilon^{ijk}\partial_{j}B^{k} - \partial_{0}E^{i} = 0 , \quad \mathbf{\dot{E}} = \nabla \times \mathbf{B} \\
\varepsilon^{ijk} \partial_{j}E^{k} = 0,\quad\nabla \times \mathbf{E} = 0
\end{gather} $$

---

## **(b)** 
构造该理论的能量-动量张量。注意，通常的程序不会得到一个对称的张量。为了修正这一点，我们可以在 $T^{\mu\nu}$ 上添加一个形如 $\partial_\lambda K^{\lambda\mu\nu}$ 的项，其中 $K^{\lambda\mu\nu}$ 在其前两个指标上是反对称的。这样的对象自动是无散度的，因此

$$\hat{T}^{\mu\nu} = T^{\mu\nu} + \partial_\lambda K^{\lambda\mu\nu}$$

是一个同样有效的能量-动量张量，具有相同的整体守恒能量和动量。证明当取

$$K^{\lambda\mu\nu} = F^{\mu\lambda} A^\nu$$

时，此构造导出的能量-动量张量 $\hat{T}$ 是对称的，并给出电磁能量密度和动量密度的标准公式：

$$\mathcal{E} = \frac{1}{2} (E^2 + B^2)$$

$$\mathbf{S} = \mathbf{E} \times \mathbf{B}.$$

对于正常的能动张量，使用诺顿原理
$$T^{\mu \nu} = \frac{\partial\mathcal L}{\partial(\partial_{\mu}A_{\rho})}\partial^{\nu}A_{\rho} - g^{\mu \nu}\mathcal L = - F^{\mu \rho}\partial^{\nu}A_{\rho} + \frac{1}{4}g^{\mu \nu} F^{\sigma \eta}F_{\sigma \eta} $$
此时
$$\begin{align}
\hat{T}^{\nu \mu} &= - F^{\mu \rho}\partial^{\nu}A_{\rho} + \frac{1}{4}g^{\nu \mu} F^{\sigma \eta}F_{\sigma \eta} + \partial_{\lambda}(F^{\nu \lambda}A^{\mu})  \\
&= - F^{\mu \rho}\partial^{\nu}A_{\rho} + A^{\mu} \partial_{\lambda}F^{\nu \lambda} + F^{\nu \lambda} \partial_{\lambda}A^{\mu} + \frac{1}{4}g^{\mu \nu} F^{\sigma \eta}F_{\sigma \eta} \\
&= F^{\nu \lambda} F_{\lambda}^{~~\mu} + \frac{1}{4} g^{\mu \nu} F^{\sigma \eta}F_{\sigma \eta} \\
&= F^{\mu \lambda} F_{\lambda}^{~~\nu} + \frac{1}{4} g^{\mu \nu} F^{\sigma \eta}F_{\sigma \eta} \\
&= \hat{T}^{\mu \nu}
\end{align} $$
可见新定义的能动张量是对称的。我们知道能动张量的 $00$ 分量是空间能量密度
$$\mathcal E = \hat{T}^{00} = g_{0\mu}F^{0\lambda}F^{\lambda \mu} + \frac{1}{4}g^{00} F^{\mu \nu}F_{\mu \nu} = F^{0\lambda}F^{0\lambda} - \sum F^{0\lambda}F^{0i} + \frac{1}{4}(|\mathbf{E}|^{2} + |\mathbf{B}|^{2}) = \frac{1}{2}( |\mathbf{E}|^{2} + |\mathbf{B}|^{2} ) $$
$$S^{i} = \hat{T}^{0i} = \dots = \varepsilon^{ijk}E_{j}B_{k} =(\mathbf{E}\times \mathbf{B})^{i} $$


---

# 2.2 复标量场

考虑服从克莱因-戈登方程的复值标量场的场论。该理论的作用量为

$$
S = \int d^4x \, (\partial_\mu \phi^* \partial^\mu \phi - m^2 \phi^* \phi).
$$

将 $\phi(x)$ 和 $\phi^*(x)$ 视为基本的动力学变量。

### (a) 正则量子化

求 $\phi(x)$ 和 $\phi^*(x)$ 的共轭动量及正则对易关系。证明哈密顿量为

$$
H = \int d^3 x (\pi^* \pi + \nabla \phi^* \cdot \nabla \phi + m^2 \phi^* \phi).
$$

计算 $\phi(x)$ 的海森堡运动方程，并证明它确实是克莱因-戈登方程。


$$\mathcal L = \partial_{\mu} \phi^{*} \partial^{\mu}\phi - m^{2} \phi^{*}\phi $$
$$\pi(x) = \frac{\partial\mathcal L}{\partial(\partial_{0}\phi)} = \partial_{0}\phi^{*} , \quad \pi^{*}(x) = \frac{\partial\mathcal L}{\partial(\partial_{0}\phi^{*})} = \partial_{0}\phi $$
$$\mathcal{H} = \pi^{*}\partial_{0}\phi^{*} + \pi \partial_{0}\phi - \mathcal{L} = 2\partial_{0}\phi \partial_{0}\phi^{*} - (\partial_{0}\phi \partial_{0}\phi^{*} - \nabla \phi^{*}\cdot \nabla \phi - m^{2}\phi^{*}\phi) = \pi^{*}\pi + \nabla \phi^{*}\cdot \nabla \phi + m^{2}\phi^{*}\phi $$
$$H = \int \mathrm{d^{3}x} \, \mathcal{H} = \int \mathrm{d^{3}x} \, ( \pi^{*}\pi + \nabla \phi^{*}\cdot \nabla \phi + m^{2}\phi^{*}\phi )  $$
使用欧拉-拉格朗日方程
$$\begin{gather}
\frac{\partial \mathcal{L}}{\partial \phi} = m^{2}\phi^{*},\quad \frac{\partial \mathcal{L}}{\partial(\partial_{\mu}\phi)} = \partial^{\mu}\phi^{*} \\
\partial_{\mu}\left(  \frac{\partial \mathcal{L}}{\partial(\partial_{\mu}\phi)}  \right) = \Box\phi^{*} \\
(\Box - m^{2})\phi^{*} = 0
\end{gather} $$
同理
$$(\Box - m^{2})\phi = 0 $$

---
### (b) 对角化哈密顿量

引入产生和湮灭算符对角化 $H$。证明该理论包含两组质量为 $m$ 的粒子。


将场用平面波展开
$$\begin{gather}
\phi(x) = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} ( a_{\mathbf{p}} e^{ -ip\cdot x } + b^{\dagger}_{\mathbf{p}} e^{ ip\cdot x } ) \\
\phi^{*}(x) = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }}( b_{\mathbf{p}} e^{ -ip\cdot x } + a^{\dagger}_{\mathbf{p}} e^{ ip\cdot x } ) 
\end{gather} $$
于是

$$\begin{align}
\pi^{*}\pi &= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} E_{\mathbf{p}}( -b_{\mathbf{p}}e^{ -ip\cdot x } + a^{\dagger}_{\mathbf{p}}e^{ ip\cdot x } ) E_{\mathbf{q}}( -a_{\mathbf{q}} e^{ -iq\cdot x } + b^{\dagger}_{\mathbf{q}} e^{ iq\cdot x } ) \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} E_{\mathbf{p}}E_{\mathbf{q}} ( b_{\mathbf{p}}a_{\mathbf{q}} e^{ -i(p+q)\cdot x } + a^{\dagger}_{\mathbf{p}} b^{\dagger}_{\mathbf{q}} e^{ i(p+q)\cdot x } - b_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} e^{ -i(p-q)\cdot x } - a^{\dagger}_{\mathbf{p}} a_{\mathbf{q}} e^{ i(p-q)\cdot x } ) \\
&\to \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} E_{\mathbf{p}}E_{\mathbf{q}}  ( b_{\mathbf{p}}a_{\mathbf{q}} e^{ -2iE_{\mathbf{p}}t } \delta^{(3)}(\mathbf{p}+\mathbf{q}) - a^{\dagger}_{\mathbf{p}} b^{\dagger}_{\mathbf{q}} e^{ 2iE_{\mathbf{p}}t } \delta^{(3)}(\mathbf{p}+\mathbf{q}) - b_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} \delta^{(3)}(\mathbf{p}-\mathbf{q}) + a^{\dagger}_{\mathbf{p}} a_{\mathbf{q}} \delta^{(3)}(\mathbf{p}-\mathbf{q}) )(2\pi)^{3} \\
&= \int \frac{\mathrm{d^{3}\mathbf{p}}}{(2\pi)^{3}{ 2E_{\mathbf{p}} }} E_{\mathbf{p}}^{2}( b_{\mathbf{p}}a_{-\mathbf{p}} e^{ -2iE_{\mathbf{p}}t } - a^{\dagger}_{\mathbf{p}}b^{\dagger}_{-\mathbf{p}} e^{ 2iE_{\mathbf{p}}t } + b_{\mathbf{p}}b^{\dagger}_{\mathbf{p}} + a^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} )
\end{align} $$

$$\begin{align}
\nabla \phi^{*}\cdot \nabla \phi &= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} ( -\mathbf{p}b_{\mathbf{p}}e^{ -ip\cdot x } + \mathbf{p}a^{\dagger}_{\mathbf{p}} e^{ ip\cdot x } )( -\mathbf{q}a_{\mathbf{q}}e^{ -iq\cdot x } + \mathbf{q}b^{\dagger}_{\mathbf{q}}e^{ iq\cdot x } ) \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} ( \mathbf{p}\cdot \mathbf{q} b_{\mathbf{p}}a_{\mathbf{q}}e^{ -i(p+q)\cdot x } - \mathbf{p}\cdot \mathbf{q} b_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} e^{ -i(p-q)\cdot x } - \mathbf{p}\cdot \mathbf{q}a^{\dagger}_{\mathbf{p}}a_{\mathbf{q}}e^{ i(p-q)\cdot x } + \mathbf{p}\cdot \mathbf{q}a^{\dagger}_{\mathbf{p}}b^{\dagger}_{\mathbf{q}}e^{ i(p+q)\cdot x } ) \\
&\to  \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} ( -\mathbf{p}\cdot \mathbf{q} b_{\mathbf{p}}a_{\mathbf{q}} e^{ -2iE_{\mathbf{p}}t }\delta^{(3)}(\mathbf{p}+\mathbf{q}) - \mathbf{p}\cdot \mathbf{q} b_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} \delta^{(3)}(\mathbf{p}-\mathbf{q}) + \mathbf{p}\cdot \mathbf{q}a^{\dagger}_{\mathbf{p}}a_{\mathbf{q}}\delta^{(3)}(\mathbf{p}-\mathbf{q}) + \mathbf{p}\cdot \mathbf{q} a^{\dagger}_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} e^{ 2iE_{\mathbf{p}}t }\delta^{(3)}(p+\mathbf{q}) )(2\pi)^{2} \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}{ 2E_{\mathbf{p}} }} (-|\mathbf{p}|^{2} b_{\mathbf{p}}a_{-\mathbf{p}}e^{ -2iE_{\mathbf{p}}t } + |\mathbf{p}|^{2} b_{\mathbf{p}}b^{\dagger}_{\mathbf{p}} + |\mathbf{p}|^{2}a^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} - |\mathbf{p}|^{2}a^{\dagger}_{\mathbf{p}}b^{\dagger}_{-\mathbf{p}}e^{ 2iE_{\mathbf{p}}t })
\end{align}
$$

$$\begin{align}
m^{2} \phi^{*}\phi &= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} m^{2}( b_{\mathbf{p}} e^{ -ip\cdot x } + a^{\dagger}_{\mathbf{p}} e^{ ip\cdot x } )( a_{\mathbf{q}} e^{ -ip\cdot x } + b^{\dagger}_{\mathbf{q}} e^{ ip\cdot x } ) \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} m^{2} ( b_{\mathbf{p}}a_{\mathbf{q}} e^{ -i(p+q)\cdot x } + a^{\dagger}_{\mathbf{p}} b^{\dagger}_{\mathbf{q}} e^{ i(p+q)\cdot x } + b_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} e^{ -i(p-q)\cdot x } + a^{\dagger}_{\mathbf{p}} a_{\mathbf{q}} e^{ i(p-q)\cdot x } ) \\
&\to \int \frac{\mathrm{d^{3}\mathbf{p}}}{(2\pi)^{3}{ 2E_{\mathbf{p}} }} m^{2}( -b_{\mathbf{p}}a_{-\mathbf{p}} e^{ -2iE_{\mathbf{p}}t } - a^{\dagger}_{\mathbf{p}}b^{\dagger}_{-\mathbf{p}} e^{ 2iE_{\mathbf{p}}t } + b_{\mathbf{p}}b^{\dagger}_{\mathbf{p}} + a^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} )
\end{align} $$


$$\begin{align}
H &= \int \mathrm{d^{3}x} \, ( \dot{\phi}^{*}\dot{\phi} + \nabla \phi^{*}\cdot \nabla \phi + m^{2}\phi^{*}\phi ) \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}{ 2E_{\mathbf{p}} }} [ (E_{\mathbf{p}}^{2}-|\mathbf{p}|^{2}-m^{2})b_{\mathbf{p}}a_{-\mathbf{p}}e^{ -2iE_{\mathbf{p}}t } - ( E_{\mathbf{p}}^{2} - |\mathbf{p}|^{2} + m^{2} )a^{\dagger}_{\mathbf{p}}b^{\dagger}_{-\mathbf{p}}e^{ 2iE_{\mathbf{p}}t } + (E_{\mathbf{p}}^{2} + |\mathbf{p}|^{2}+m^{2})(a^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} + b_{\mathbf{p}}b^{\dagger}_{\mathbf{p}})] \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}{ 2E_{\mathbf{p}} }} 2E_{\mathbf{p}}^{2}( a_{\mathbf{p}}^{\dagger}a_{\mathbf{p}} + b_{\mathbf{p}}b^{\dagger}_{\mathbf{p}} ) \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} E_{\mathbf{p}}( a^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} + b^{\dagger}_{\mathbf{p}}b_{\mathbf{p}} ) + \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} E_{\mathbf{p}} (2\pi)^{3} \delta^{(3)}(\mathbf{0})
\end{align} $$

 其中 $E_{\mathbf{p}}=\sqrt{ |\mathbf{p}|^{2} + m^{2} }$ 所以这两套产生湮灭算符对应粒子的质量是一样的，经过正规序可以消去零点能 $\int \mathrm{d^{3}p} \, E_{\mathbf{p}} \delta^{(3)}(\mathbf{0})$ 此时可以看到哈密顿量是对角化的


---


### (c) 守恒荷

用产生和湮灭算符重写守恒荷

$$
Q = \int d^3 x \frac{i}{2} (\phi^* \pi^* - \pi \phi),
$$

并计算每种类型粒子的电荷。


$$\begin{align}
\phi^{*}\pi^{*} &= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} (-iE_{\mathbf{q}}) ( b_{\mathbf{p}} e^{ -ip\cdot x } + a^{\dagger}_{\mathbf{p}} e^{ ip\cdot x } )( a_{\mathbf{q}} e^{ -iq\cdot x } - b^{\dagger}_{\mathbf{q}} e^{ iq\cdot x } )  \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} (-iE_{\mathbf{q}}) ( b_{\mathbf{p}}a_{\mathbf{q}} e^{ -i(p+q)\cdot x } - b_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} e^{ -i(p-q)\cdot x } + a^{\dagger}_{\mathbf{p}}a_{\mathbf{q}} e^{ i(p-q)\cdot x } - a^{\dagger}_{\mathbf{p}}b^{\dagger}_{\mathbf{q}}e^{ i(p+q)\cdot x } )  \\
&\to \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} (-iE_{\mathbf{q}}) \left(  b_{\mathbf{p}}a_{\mathbf{q}} (2\pi)^{3} e^{ -2iE_{\mathbf{p}}t } \delta^{(3)}(\mathbf{p}+\mathbf{q}) - b_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} (2\pi)^{3}\delta^{(3)}(p-\mathbf{q}) - a^{\dagger}_{\mathbf{p}}a_{\mathbf{q}} (2\pi)^{3} \delta^{(3)}\left( \mathbf{p}-\mathbf{q} \right) + a^{\dagger}_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} (2\pi)^{3}\delta^{(3)} e^{ 2iE_{\mathbf{p}}t } (\mathbf{p}+\mathbf{q})  \right) \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} \frac{-i}{2} ( b_{\mathbf{p}}a_{-\mathbf{p}}e^{ -2iE_{\mathbf{p}}t } - b_{\mathbf{p}}b^{\dagger}_{\mathbf{p}} - a^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} + a^{\dagger}_{\mathbf{p}} b^{\dagger}_{-\mathbf{p}}e^{ 2iE_{\mathbf{p}}t } )
\end{align} $$

$$\begin{align}
\pi \phi &= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }}  \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} (-iE_{\mathbf{p}}) (-a_{\mathbf{p}}e^{ -ip\cdot x } + b^{\dagger}_{\mathbf{p}}e^{ ip\cdot x })(a_{\mathbf{q}}e^{ -iq\cdot x } + b^{\dagger}_{\mathbf{q}}e^{ iq\cdot x })  \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }}  \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} (-iE_{\mathbf{p}}) ( -a_{\mathbf{p}}a_{\mathbf{q}} e^{ -i(p+q)\cdot x } - a_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} e^{ -i(p-q)\cdot x } + b^{\dagger}_{\mathbf{p}}a_{\mathbf{q}}e^{ i(p-q)\cdot x } + b^{\dagger}_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} e^{ i(p+q)\cdot x } ) \\
&\to \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }}  \frac{\mathrm{d^{3}q}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{q}} }} (-iE_{\mathbf{p}}) ( -a_{\mathbf{p}}a_{\mathbf{q}} e^{ -2iE_{\mathbf{p}}t } \delta^{(3)}(\mathbf{p}+\mathbf{q}) - a_{\mathbf{p}}b^{\dagger}_{\mathbf{q}} \delta^{(3)}(\mathbf{p}-\mathbf{q}) -  b^{\dagger}_{\mathbf{p}}a_{\mathbf{q}}  \delta^{(3)}(\mathbf{p}-\mathbf{q}) - b^{\dagger}_{\mathbf{p}}b^{\dagger}_{\mathbf{q}}e^{ 2iE_{\mathbf{p}}t } \delta^{(3)}(\mathbf{p}+\mathbf{q})   ) (2\pi)^{3} \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} \frac{-i}{2} ( -a_{\mathbf{p}}a_{-\mathbf{p}} e^{ -2iE_{\mathbf{p}}t } - a_{\mathbf{p}}b^{\dagger}_{\mathbf{p}}  - b^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} - b^{\dagger}_{\mathbf{p}} b^{\dagger}_{-\mathbf{p}} e^{ 2iE_{\mathbf{p}}t } )
\end{align}
$$

$$Q =\int d^3 x \frac{i}{2} (\phi^* \pi^* - \pi \phi) = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} ( a^{\dagger}_{\mathbf{p}}a_{\mathbf{p}} - b^{\dagger}_{\mathbf{p}}b_{\mathbf{p}} ) $$

可见场 $\phi$ 的电荷是正的，$\phi^{*}$ 的电荷是负的

---

### (d) 多场情形

考虑两个具有相同质量的复杂克莱因-戈登场的情况。将场标记为 $\phi_a(x)$，其中 $a = 1, 2$。证明现在有四个守恒荷，其中一个由 (c) 部分的推广给出，另外三个由下式给出：

$$
Q^i = \int d^3 x \frac{i}{2} (\phi^*_a(\sigma^i)_{ab} \pi^*_b - \pi_a(\sigma^i)_{ab} \phi_b),
$$

其中 $\sigma^i$ 是泡利西格玛矩阵。证明这三个荷具有角动量 ($SU(2)$) 的对易关系。将这些结果推广到 $n$ 个相同复标量场的情况。


先平面波展开
$$\begin{gather}
\phi_{a} = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} ( a_{a,\mathbf{p}}e^{ -ip\cdot x } + b^{\dagger}_{a,\mathbf{p}} e^{ ip\cdot x } ) \\
\phi_{a}^{*} = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} ( b_{a,\mathbf{p}} e^{ -ip\cdot x } + a^{\dagger}_{a,\mathbf{p}} e^{ ip\cdot x } ) \\
\pi_{a} = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} (-iE_{\mathbf{p}}) ( a_{a,\mathbf{p}}e^{ -ip\cdot x } - b^{\dagger}_{a,\mathbf{p}} e^{ ip\cdot x } ) \\
\pi_{a}^{*} = \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}\sqrt{ 2E_{\mathbf{p}} }} (-iE_{\mathbf{p}}) ( b_{a,\mathbf{p}} e^{ -ip\cdot x } - a^{\dagger}_{a,\mathbf{p}} e^{ ip\cdot x } )
\end{gather} $$
然后直接带进去就好啦♥
$$\phi^{*}_{a}(\sigma^{i})_{ab}\pi^{*}_{b} = (\sigma^{i})_{ab} \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} \frac{-i}{2} ( b_{a,\mathbf{p}}a_{b,-\mathbf{p}}e^{ -2iE_{\mathbf{p}}t } - b_{a,\mathbf{p}}b^{\dagger}_{b,\mathbf{p}} - a^{\dagger}_{a,\mathbf{p}}a_{b,\mathbf{p}} + a^{\dagger}_{a,\mathbf{p}} b^{\dagger}_{b,-\mathbf{p}}e^{ 2iE_{\mathbf{p}}t } ) $$
$$\pi_{a}(\sigma^{i})_{ab}\phi_{b} = (\sigma^{i})_{ab} \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} \frac{-i}{2} ( -a_{a,\mathbf{p}}a_{b,-\mathbf{p}} e^{ -2iE_{\mathbf{p}}t } - a_{a,\mathbf{p}}b^{\dagger}_{b,\mathbf{p}}  - b^{\dagger}_{a,\mathbf{p}}a_{b,\mathbf{p}} - b^{\dagger}_{a,\mathbf{p}} b^{\dagger}_{b,-\mathbf{p}} e^{ 2iE_{\mathbf{p}}t } ) $$
$$Q^{i} = (\sigma^{i})_{ab} \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} ( a^{\dagger}_{a,\mathbf{p}}a_{b,\mathbf{p}} - b^{\dagger}_{a,\mathbf{p}}b_{b,\mathbf{p}} ) $$
$SU(2)$ 的对易关系是说我得证明 $[Q^{i},Q^{j}]=i\varepsilon^{ijk}Q^{k}$ 首先知道泡利矩阵的李代数是 $[\sigma^{i},\sigma^{j}]=2i\varepsilon^{ijk}\sigma^{k}$ 不同的场对易，不妨记 $Q^{i}=\frac{1}{2}(A^{i}-B^{i})$ 则
$$[Q^{i},Q^{j}] = \frac{1}{4} [ A^{i}-B^{i} , A^{j} - B^{j} ] = \frac{1}{4} [A^{i} , A^{j}] + \frac{1}{4} [ B^{i} , B^{j}] $$
$$\begin{align}
[A^{i} , A^{j}] &= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}} (\sigma^{i})_{ab} (\sigma^{j})_{cd} [ a^{\dagger}_{a,\mathbf{p}}a_{b,\mathbf{p}} , a^{\dagger}_{c,\mathbf{q}}a_{d,\mathbf{q}} ] \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}} \frac{\mathrm{d^{3}q}}{(2\pi)^{3}} (\sigma^{i})_{ab} (\sigma^{j})_{cd}  \big[ (2\pi)^{3}\delta _{bc} \delta^{(3)}(\mathbf{p}-\mathbf{q}) a^{\dagger}_{a,\mathbf{p}}a_{d,\mathbf{q}} - (2\pi)^{3} \delta_{ad}\delta^{(3)}(\mathbf{p}-\mathbf{q}) a^{\dagger}_{c,\mathbf{q}}a_{b,\mathbf{p}} \big] \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}}  (\sigma^{i})_{ab} (\sigma^{j})_{cd} \big[ \delta_{bc} a^{\dagger}_{a,\mathbf{p}}a_{d,\mathbf{p}} - \delta_{ad} a^{\dagger}_{c,\mathbf{p}}a_{b,\mathbf{p}}  \big] \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}}  \big[ (\sigma^{i})_{ab} (\sigma^{j})_{bd} a^{\dagger}_{a,\mathbf{p}}a_{d,\mathbf{p}} - (\sigma^{i})_{ab} (\sigma^{j})_{ca} a^{\dagger}_{c,\mathbf{p}} a_{b,\mathbf{p}} \big] \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}}  \big[ (\sigma^{i}\sigma^{j})_{ad} a^{\dagger}_{a,\mathbf{p}}a_{d,\mathbf{p}} - (\sigma^{i}\sigma^{j})_{cb} a^{\dagger}_{c,\mathbf{p}} a_{b,\mathbf{p}} \big]  \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}}  \big[ (\sigma^{i}\sigma^{j})_{ad} a^{\dagger}_{a,\mathbf{p}}a_{d,\mathbf{p}} - (\sigma^{j}\sigma^{a})_{ad} a^{\dagger}_{a,\mathbf{p}} a_{d,\mathbf{p}} \big] \\
&= \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}}  a^{\dagger}_{a,\mathbf{p}} [ \sigma^{i} , \sigma^{j} ]_{ad} a_{d,\mathbf{p}} \\
&= 2i\varepsilon^{ijk} \int \frac{\mathrm{d^{3}p}}{(2\pi)^{3}}  a^{\dagger}_{a,\mathbf{p}} (\sigma^{k})_{ad} a_{d,\mathbf{p}} \\
&= 2i\varepsilon^{ijk} A^{k}
\end{align} $$
同理 $[B^{i},B^{j}]=2i\varepsilon^{ijk}B^{k}$ 于是
$$[Q^{i},Q^{j}] = \frac{i}{2}\varepsilon^{ijk}( A^{k} - B^{k} ) = i\varepsilon^{ijk}Q^{k} $$
证毕

---


## 2.3 两点关联函数的计算

计算如下函数（对于类空间隔 $(x-y)$，即 $(x-y)^2 = -r^2$），并明确用贝塞尔函数表示：
$$
\langle 0| \phi(x) \phi(y) | 0 \rangle = D(x - y) = \int \frac{d^3 p}{(2\pi)^3} \frac{1}{2E_{\mathbf{p}}} e^{-ip\cdot (x-y)}.
$$


$$\begin{align}
I &= \int_{0}^{\infty} \frac{p^{2}\mathrm{dp}}{(2\pi)^{3}2E_{\mathbf{p}}} \int_{0}^{2\pi} \mathrm{d\phi} \int_{0}^{\pi} \mathrm{d\theta} \, \sin \theta e^{ -ipr \cos \theta }  \\
&=  \int_{0}^{\infty} \frac{p^{2}\mathrm{dp}}{(2\pi)^{2}2E_{\mathbf{p}}} \int_{-1}^{1} \mathrm{du} \, e^{ -ipr u } \\
&= \int_{0}^{\infty} \frac{p^{2}\mathrm{dp}}{(2\pi)^{2}2E_{\mathbf{p}}} \frac{e^{ ipr } - e^{ -ipr }}{ipr} \\
&= \int_{0}^{\infty} \frac{\mathrm{dp}}{(2\pi)^{2}} \frac{p\sin(pr)}{r\sqrt{ p^{2} + m^{2} }} \\
&= \frac{1}{4\pi^{2}r} \int \mathrm{dp} \frac{p\sin(pr)}{\sqrt{ p^{2} + m^{2} }} \\
&= \frac{m}{4\pi^{2}r} K_{1}(mr)
\end{align} $$
