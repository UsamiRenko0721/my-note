---
up:
  - "[[写题]]"
related:
date: 2026-03-22
tags:
  - 量子场论
  - 习题
---
# 25 年

In this problem, we explore some physical properties of a conformal scalar ﬁeld. We use natural units $c=\hbar= 1$.

(a) Consider a massless scalar ﬁeldφin Minkowski spacetime with the action
$$S = -\frac{1}{2}\int d^{4}x (\partial_{\mu}\phi)^{2} $$
Show that the action is invariant under arigidrescaling of the metric, namely $\eta^{\mu \nu}\to \tilde{\eta}^{\mu \nu}=\Omega^{2}\eta^{\mu \nu}$ with $\Omega$ constant, if one rescales simultaneously $\phi$ according to $\phi\to \tilde{\phi}=\Omega^{\Delta}\phi$. Determine $\Delta$.

>[!S]
>$$S\to -\frac{1}{2}\int d^{4}x\ \Omega^{2}\eta^{\mu \nu}(\partial_{\mu}\Omega^{\Delta}\phi)^{2} = -\frac{\Omega^{2+2\Delta}}{2} \int d^{4}x\ (\partial_{\mu}\phi)^{2} = S $$
>So it show that $\Delta=-1$

(b) Consider alocalrescaling of an arbitrary metric $g^{\mu \nu}\to \tilde{g}^{\mu \nu}=\Omega^{2}g^{\mu \nu}$ and also $\phi\to \tilde{\phi}=\Omega^{\Delta}\phi$. Determine of transformation of the action
$$S = -\frac{1}{2}\int d^{4}x\ \sqrt{ -g }g^{\mu \nu}(\partial_{\mu}\phi)(\partial_{\nu}\phi) $$
under the local rescaling. Can $S$ be made invariant by appropriately choosing the value of $\Delta$?

>[!S]
>Under such transfrom,
>$$\sqrt{ -g } \to \Omega^{-4}\sqrt{ -g } $$
>So
>$$\begin{align}
S & \to -\frac{1}{2}\int d^{4}x\ \Omega^{-4}\sqrt{ -g }\Omega^{2}g^{\mu \nu}(\partial_{\mu}\Omega^{\Delta}\phi)^{2} \\ & = -\frac{\Omega^{2\Delta-2}}{2}\int d^{4}x\ \sqrt{ -g }g^{\mu \nu}(\partial_{\mu}\phi +\Delta \phi \partial_{\mu}\ln \Omega)(\partial_{\nu}\phi + \Delta \phi \partial_{\nu}\ln \Omega) \\ & = -\frac{\Omega^{2\Delta-2}}{2} \int d^{4}x\ \sqrt{ -g }g^{\mu \nu}(\partial_{\mu}\phi \partial_{\nu}\phi + 2\Delta \phi \partial_{\mu}\phi \partial_{\nu}\ln \Omega + \Delta^{2}\phi^{2}\partial_{\mu}\ln \Omega \partial_{\nu}\ln \Omega) 
\end{align} $$
>Choose $\Delta=1$ so that the first trem can return the origin form, but
>$$S\to -\frac{1}{2}\int d^{4}x\ \sqrt{ -g }g^{\mu \nu}(\partial_{\mu}\phi \partial_{\nu}\phi + 2\phi \partial_{\mu}\phi \partial_{\nu}\ln \Omega + \phi^{2}\partial_{\mu}\ln \Omega \partial_{\nu}\ln \Omega) $$
>the third trem can't transtale into a total derivative. So $S$ can't bi made invariate by appropriately choosing the value of $\Delta$.

(c) Suppose the Ricci scalar transforms as $R\to \tilde{R}$ under the local rescaling $g^{\mu \nu}(x)\to \Omega^{2}(x)g^{\mu \nu}(x)$. Please determine $\tilde{R}$.

>[!S]
> Under a local Weyl rescaling $g_{\mu\nu} \to \Omega^{-2}(x) g_{\mu\nu}$, one computes the change of the Christoffel symbols and finds  
> $$\tilde \Gamma^\lambda_{\mu\nu} = \Gamma^\lambda_{\mu\nu} - \delta^\lambda_\mu \partial_\nu \ln\Omega - \delta^\lambda_\nu \partial_\mu \ln\Omega - g_{\mu\nu} \partial^\lambda \ln\Omega$$  
>  From this, one obtains the transformed Ricci scalar:  
>  $$ \tilde R = \Omega^2 \left[  R + 6\Box \ln\Omega - 6(\nabla \ln\Omega)^2  \right]$$

(d) Show that the invariance of the scalar action under the local rescaling can be restored if we add a new term to the action:
$$S = \int d^{4}x\ \sqrt{ -g }\left[ \frac{1}{2}(\partial_{\mu}\phi)^{2} - \frac{1}{2}R\xi \phi^{2} \right] $$
where $\xi$ is a coupling constant. Determine the value of $\xi$ such that the action is invariant under the local rescaling. A scalar ﬁeld $\phi$ with the above action is called aconformal scalar.

>[!S]
>From (b) we know $\Delta=1$ to keep the prefactor = 1. i.e.
>$$g^{\mu \nu} \to \Omega^{2}g^{\mu \nu} ,\quad \phi \to \Omega \phi $$
>Then
>$$\partial_{\mu}\phi \to \Omega(\partial_{\mu}\phi + \phi \partial_{\mu}\ln \Omega) ,\quad (\partial_{\mu}\phi)^{2} \to \Omega^{2}((\partial_{\mu}\phi)^{2} + 2\phi\partial^{\mu}\phi \partial_{\mu}\ln \Omega + \phi^{2}(\partial_{\mu}\ln \Omega)^{2}) $$
>$$\delta S_{\text{kin}} = \int d^{4}x\ \sqrt{ -g }\left[ \phi \partial^{\mu}\phi \partial_{\mu}\ln \Omega + \frac{1}{2}\phi^{2}(\partial_{\mu}\ln \Omega)^{2}  \right] $$
>And
>$$R\phi^{2} \to \phi^{2}[ R+6\Box\ln \Omega - 6(\nabla \ln \Omega)^{2} ] $$
>$$\begin{align}
\delta S_{R} & = \int d^{4}x\ \sqrt{ -g }[ -3\xi \phi^{2}\Box\ln \Omega + 3\xi \phi^{2}(\partial_{\mu}\ln \Omega)^{2} ] \\ & =\int d^{4}x\ \sqrt{ -g }[ 6\phi\xi (\partial_{\mu} \phi) (\partial^{\mu}\ln \Omega) + 3\xi \phi^{2}(\partial_{\mu}\ln \Omega)^{2} ]
\end{align}$$
>So $\int \sqrt{ -g }(6\xi+1)\phi \partial^{\mu}\phi \partial_{\mu}\ln \Omega d^{4}x \subset \delta S$ 
>$$\delta S = 0\implies 6\xi + 1 = 0 \implies \xi=-\frac{1}{6} $$
>

(e) Consider a spacetime with the following metric:
$$ds^{2} = \frac{-d\tau^{2}+d\mathbf{x}^{2}}{(H\tau)^{2}} $$
where $\mathbf{x}\in \mathbb{R}^{3},\tau \in(-\infty,0)$, and $H$ is a constant. Please show that a conformal scalar $\phi$ in this spacetime has an action identical to a scalar ﬁeld with nonzero massm. Please determinem.

>[!S]
>$$g^{\mu \nu} = \Omega^{-2}\eta^{\mu \nu} ,\quad \Omega(\tau) = H\tau $$
>Set $\chi=\Omega^{-1}\phi$ then
>$$\begin{align}
S & = \int d^{4}x\ \sqrt{ -g }\left[  \frac{1}{2}(\partial_{\mu}(H\tau \phi))^{2} + \frac{1}{12} RH\tau \phi \right] \\ & =\int d^{4}x \left[  \frac{1}{2}(\partial_{\mu}\chi)^{2} - \frac{1}{2} \frac{(H\tau)''}{H\tau}\chi^{2} \right] \\ & =\int d^{4}x \left[  \frac{1}{2}(\partial_{\mu}\chi)^{2} - \frac{1}{2}\left( \frac{2}{\tau^{2}} \right)\chi^{2} \right]
\end{align}$$
>So the massm is $m^{2} = \frac{2}{\tau^{2}}$ or $m=\frac{\sqrt{ 2 }}{\tau}$.

---
# 24 年

Consider the Lagrangian of the Yukawa theory between a real scalar field $\phi$ and a Dirac spinor field $\psi$
$$\mathcal{L} = \frac{1}{2}(\partial_{\mu}\phi)^{2} - \frac{1}{2}m\phi^{2} + \bar{\psi}(i\gamma^{\mu}\partial_{\mu} - M)\psi - ig\bar{\psi}\gamma^{5}\psi \phi $$
(a) Find all divergences in 1-loop self-energy graphs of the scalars $\phi$. What are the correct counter-terms to cancel this divergences?

>[!S]
>所有一圈图无非 $\phi(p) \to \psi(k)+\psi(p-k) \to \phi(p)$ 有两条玻色子外线，两条费米子内线，一个圈，于是表观发散度为
>$$D = 4 - B_{E} - \frac{3}{2}F_{E} + \sum n_{i}\delta_{i} = 4 - 2 - 0 - 0 = 2 $$
>于是该图存在二次发散。我们需要对核子的 $\Pi(p^{2})$ 展开到2阶，需要2阶的导数，所以抵消项为
>$$\mathcal{L}_{CT} = A\phi^{2} + B(\partial_{\mu}\phi)^{2} $$
>

(b) Find all divergences in 1-loop self-energy graphs of the scalars $\psi$. What are the correct counter-terms to cancel this divergences?

>[!S]
>其一圈图是 $\psi(p)\to \psi(k)+\phi(p-k)\to \psi(p)$ 有两条费米子外线，一条玻色子内线，一条费米子内线，一个圈，于是表观发散度为
>$$D = 4 - 2 - 2 = 0 $$
>这个图对数发散，使用BPHZ重整化手续，需要对介子的 $\Pi(\not{\!p})$ 展开到1阶，需要1阶的导数，所以抵消项为
>$$\mathcal{L}_{CT} = \bar{\psi}C\psi + D\bar{\psi}\not{\!\partial}\psi $$

(c) Are there divergences which can not be renormalized in this theory?

>[!S]
>相互作用项的发散指标
>$$\delta_{i} = b_{i} + \frac{3}{2}f_{i} + d_{i} - 4 = 0 $$
>所以理论是可重整化的

---

# 23年

Consider the $\phi^{3}$ model with a real scalar field $\phi(x)$ in $3 + 1$ dimensional Minkowski spacetime with metric $(−, +, +, +)$. Its Lagrangian density is
$$\mathcal{L}= -\frac{1}{2}(\partial_{\mu}\phi)^{2} - \frac{1}{2}m^{2}\phi^{2} - \frac{1}{6}g\phi^{3} $$
where $g$ is a coupling with dimensions of mass.

(a) Write down the propagator and the interaction vertex for this model in momentum space.

>[!S]
>
>$$\widetilde{D}(p) = \frac{i}{p^{2}-m^{2}+i\varepsilon} $$
>$$\widetilde{\Gamma}(p_{1},p_{2},p_{3}) = -ig(2\pi)^{4}\delta^{(4)}(p_{1}+p_{2}+p_{3}) $$
>

(b) Compute the one-loop self-energy graph using dimensional regularization.

>[!S]
>一圈贡献为
>$$-i\Pi(p^{2}) = \frac{1}{2}(-ig\mu^{4-d})^{2} \int \frac{d^{d}k}{(2\pi)^{d}} \frac{i}{(-k^{2}-m^{2}+i\varepsilon)} \frac{i}{(-(p-k)^{2} - m^{2} + i\varepsilon)} $$
>其中
>$$\frac{1}{(-k^{2}-m^{2})} \frac{1}{(-(p-k)^{2} - m^{2} )} = \int_{0}^{1} \frac{dx}{[(-k^{2}-m^{2})x - ((p-k)^{2} + m^{2} )(1-x)]^{2}} $$
>平移动量 $k\to k+(1-x)p$ 分母配方得
>$$k^{2}+m^{2}+x(1-x)p^{2} + i\varepsilon \to k^{2} + (m^{2}+x(1-x)p^{2}) + i\varepsilon := k^{2} + \Delta + i\varepsilon $$
>$$-i\Pi(p^{2}) = \frac{g^{2}\mu^{8-2d}}{2} \int_{0}^{1} dx \int \frac{d^{d}k}{(2\pi)^{d}} \frac{1}{(k^{2}+\Delta+i\varepsilon)^{2}} $$
>考虑 Wick 转动到欧式空间
>$$\begin{align}
\int \frac{d^{d}k_{E}}{(2\pi)^{d}} \frac{1}{(k_{E}^{2} + \Delta)^{2}} & = \Omega_{d} \int \frac{k^{d-1}dk}{(2\pi)^{d}} \frac{1}{(k^{2}+\Delta)^{2}} \\ & =\Omega_{d} \int \frac{k^{d-1}dk}{(2\pi)^{d}} \frac{1}{\Gamma(2)}\int_{0}^{\infty} dy\ ye^{ -y(k^{2}+\Delta) } \\ & = \frac{\Omega_{d}}{(2\pi)^{d}} \int_{0}^{\infty}dy \ ye^{ -\Delta y } \int k^{d-1}e^{ -yk^{2} }dk \\ & = \frac{\Omega_{d}}{(2\pi)^{d}} \int_{0}^{\infty} dy\ ye^{ -\Delta y } \int \frac{y^{-d/2}}{2} u^{d/2-1} e^{ -u } du \\ & =\frac{\Omega_{d}}{(2\pi)^{d}} \frac{\Gamma(d /2)}{2} \int_{0}^{\infty} y^{1-d/2} e^{ -\Delta y }dy \\ & = \frac{\Omega_{d}}{2(2\pi)^{d}}\Gamma\left( \frac{d}{2} \right) \Gamma\left( 2- \frac{d}{2}  \right) \Delta^{d/2-2}
\end{align}$$
>其中 $\Omega_{d}$ 是单位 $d$ 维球的表面积 $\Omega_{d} =\frac{2\pi^{d/2}}{\Gamma(d /2)}$ 代入得
>$$\frac{1}{(4\pi)^{d/2}} \Gamma\left( 2-\frac{d}{2} \right)\Delta^{d/2-2} $$
>所以
>$$-i\Pi(p^{2}) = \frac{g^{2}\mu^{8-2d}}{2(4\pi)^{d/2}}\Gamma\left( 2-\frac{d}{2} \right)\int_{0}^{1}  [m^{2}+x(1-x)p^{2}]^{d/2-2}dx $$
>最后取 $d=4-\varepsilon$ 极限，其中
>$$\mu^{8-2d} = \mu^{2\varepsilon} = 1 + 2\varepsilon \ln \mu +\mathcal{O}(\varepsilon^{2}) $$
>$$(4\pi)^{-d/2} = (4\pi)^{-2}\left[ 1+\frac{\varepsilon}{2}\ln(4\pi) \right] + \mathcal{O}(\varepsilon^{2}) $$
>$$\Gamma\left( 2-\frac{d}{2} \right) = \Gamma\left( \frac{\varepsilon}{2} \right) = \frac{2}{\varepsilon} - \gamma + \mathcal{O}(\varepsilon) $$
>$$\begin{align}
[m^{2}+x(1-x)p^{2}]^{d/2-2} &  = [m^{2}+x(1-x)p^{2}]^{-\varepsilon/2} = m^{-\varepsilon}\left[  1- \frac{\varepsilon}{2}\ln\left( 1+ \frac{x(1-x)p^{2}}{m^{2}} \right)  \right] \\  & = (1-\varepsilon \ln m)\left[  1- \frac{\varepsilon}{2}\ln(\dots)  \right] \\ & =1 - \varepsilon \ln m - \frac{\varepsilon}{2} \ln\left( 1 + \frac{x(1-x)p^{2}}{m^{2}} \right) + \mathcal{O}(\varepsilon^{2})
\end{align}$$
>所以
>$$\begin{align}
-i\Pi(p^{2}) &  = \frac{g^{2}(1+2\varepsilon \ln \mu)}{2(4\pi)^{2}} \left( \frac{2}{\varepsilon} - \gamma \right)\left[  1-\varepsilon \ln m - \frac{\varepsilon}{2}\int_{0}^{1} \ln(\dots)dx  \right]\left[ 1+\frac{\varepsilon}{2}\ln(4\pi) \right] \\ & = \frac{g^{2}}{2(4\pi)^{2}}\left[  \frac{2}{\varepsilon} - \gamma + \ln(4\pi) - 2\ln \frac{m}{\mu} - \int_{0}^{1}\ln(\dots)dx  \right]
\end{align}$$
>

(c) Introducing $m^{2} = m^{2}_{R} + \delta m^{2}$ . What is the value of $δm^{2}$ if we want to write the one-loop self-energy graph as a finite function of $m_{R}$?

>[!S]
>发散结构是 $\frac{2}{\varepsilon}$ 所以取它为抵消项即可
>$$\delta m^{2} = -\frac{g^{2}}{(4\pi)^{2}} \frac{1}{\varepsilon} $$



---

# 22 年

Consider following Lagrangian for $N$ scalar fields $\phi_{a},a=1,\dots,N$ :
$$\mathcal{L} = \frac{1}{2}\partial_{\mu}\phi^{a}\partial^{\mu}\phi^{a} - \frac{1}{2}\mu_{0}^{2}\phi^{a}\phi^{a} - \frac{\lambda_{0}}{8}(\phi^{a}\phi^{a})^{2} $$
Here the repeated index implies the summation over the index.

(a) Write down the propagator and interaction vertex for this model, and write down four point Feynman diagrams up to one loop level.

>[!S]- s
>Propagator:
>$$\widetilde{D}_{ab}(p) = \frac{i}{p^{2}-\mu_{0}^{2}+i\varepsilon}\delta_{ab} $$
>Vertex:
>$$ -i\lambda_{0}(\delta_{ab}\delta_{cd} + \delta_{ac}\delta_{bd} + \delta_{ad}\delta_{bc}) $$
>Four point diagram:
>$$\begin{align}
i\mathcal{M}_{abcd} &  = -i\lambda_{0}(\delta_{ab}\delta_{cd} + \delta_{ac}\delta_{bd} + \delta_{ad}\delta_{bc}) \\ & \quad + \frac{(-i\lambda_{0})^{2}(N+2)}{2}[ \delta_{ab}\delta_{cd}I(s) + \delta_{ac}\delta_{bd}I(t) + \delta_{ad}\delta_{bc}I(u) ]
\end{align}$$
>where
>$$I(s) = \int \frac{d^{4}k}{(2\pi)^{4}} \frac{i}{k^{2}-\mu_{0}^{2}+i\varepsilon} \frac{i}{(k+p)^{2}-\mu_{0}^{2}+i\varepsilon} $$
>$$s = (p_{1}+p_{2})^{2} ,\quad t=(p_{1}+p_{3})^{2} , \quad u = (p_{1}+p_{4})^{2} $$

(b) Define $g_{0} = \lambda_{0}N$, and compute the order in $g_{0}$ and $N$ for all the diagrams listed in last question. If we fix the coupling $g_{0}$, and let $N$ go to infinity, list the leading order Feynman diagrams in $\frac{1}{N}$ .

>[!S]
>$$\lambda_{0} = \frac{g_{0}}{N} $$
>tree diagram:
>$$\mathcal{M}_{tre e} \sim \lambda_{0} \sim g_{0}N^{-1} $$
>bubble diagram:
>$$\mathcal{M}_{bubble} \sim \lambda_{0}^{2}N \sim g_{0}^{2}N^{-1} $$
>For four point diagram on tree level and one-loop level, when we fix $g_{0}$ , they are all ordered in $\mathcal{O}(N^{-1})$

---
# 22 年

The energy momentum tensor for a relativistic quantum field theory is denoted as $\theta^{\mu \nu}$, which is symmetric and conserved. 

(a) Define new current $s^{\mu}=x_{\nu}\theta^{\mu \nu}$ and $K^{\lambda \mu}=x^{2}\theta^{\lambda \mu}-2x^{\lambda }x_{\rho}\theta^{\rho \mu}$. Compute $\partial_{\mu}s ^{\mu}$ and $\partial_{\mu}K^{\lambda \mu}$, and explain the condition on $\theta^{\mu \nu}$ so that these new currents are conserved.

>[!S]
>$$\partial_{\mu}s ^{\mu} = \partial_{\mu}(x_{\nu}\theta^{\mu \nu}) = \delta_{\mu \nu}\theta^{\mu \nu} + x_{\nu}\partial_{\mu}\theta^{\mu \nu} $$
>Because $\theta^{\mu \nu}$ is conserved, so $\partial_{\mu}\theta^{\mu \nu}=0$. And $\theta^{\mu \nu}$ is symmetric, so
>$$\partial_{\mu}s ^{\mu} = \delta_{\mu \nu}\theta^{\mu \nu} = {\theta^{\mu}}_{\mu} = 0 $$
>So it need $\theta^{\mu \nu}$ is trece-zero. Next
>$$\partial_{\mu}K^{\lambda \mu} = \partial_{\mu}( x^{2}\theta^{\lambda \mu} - 2x^{\lambda}x_{\rho}\theta^{\rho \mu} ) = 2x^{\nu}\delta_{\mu \nu}\theta^{\lambda \mu} - 2{\delta^{\lambda}}_{\mu}x_{\rho}\theta^{\rho \mu} - 2x^{\lambda}\delta_{\rho \mu}\theta^{\rho \mu} - 2x^{\lambda}x_{\rho}\partial_{\mu}\theta^{\rho \mu} $$
>Similarly $\partial_{\mu}\theta^{\rho \mu}=0$
>$$\partial_{\mu}K^{\lambda \mu} = 2x_{\mu}\theta^{\lambda \mu} - 2x_{\rho}\theta^{\lambda \rho} - 0 = 0 $$
>So these currents are conserved.

(b) Consider a scalar field $\sigma(x)$ which transforms under a scale transformation as
$$\delta \sigma = x^{\lambda}\partial_{\lambda}\sigma + f^{-1} $$
we have following Lagrangian
$$L = L_{s} - \frac{\mu_{0}^{2}}{2}\phi^{2}e^{ 2f\sigma } + \frac{1}{2f^{2}}\partial_{\mu}e^{ f\sigma }\partial^{\mu}e^{ f\sigma } $$
The infinitesimal scale transformation on scalar field $\phi$ is $\delta \phi=(1+x^{\lambda}\partial_{\lambda})\phi$ Here $L_{s}$ is scale invariant part of the Lagrangian. Prove that: the above Lagrangian is scale invariant.

>[!S]
>Define $\chi=e^{ f\sigma }$, then 
>$$L = L_{s} - \frac{\mu_{0}^{2}}{2}\phi^{2}\chi^{2} + \frac{1}{2f}(\partial_{\mu}\chi)(\partial^{\mu}\chi) $$$$\delta \chi = e^{ f\sigma }\delta (f\sigma)=\chi x^{\lambda}\partial_{\lambda}(f\sigma)+\chi=x^{\lambda}\partial_{\lambda}\chi+\chi=(1+x^{\lambda}\partial_{\lambda})\chi$$
>So that, we have $\delta \chi =(1+x^{\lambda}\partial_{\lambda})\chi$ and $\delta \phi=(1+x^{\lambda}\partial_{\lambda})\phi$. Now we need $L$ is a total divergence. Since $L_{s}$ is scale invariant part $\delta L_{s}=0$ , we only consider the remain part.
>$$\delta L = -\frac{\mu_{0}^{2}}{2}[ \delta(\phi^{2})\chi^{2} + \phi^{2}\delta (\chi^{2}) ] + \frac{1}{2f} [\delta(\partial_{\mu}\chi)(\partial^{\mu}\chi) + (\partial_{\mu}\chi)\delta(\partial^{\mu}\chi)] $$
>Where
>$$\begin{gather}
\delta(\phi^{2})\chi^{2} = 2\phi \chi^{2}\delta \phi = 2\phi \chi^{2}(1+x^{\lambda}\partial_{\lambda})\phi = \chi^{2}(2+x^{\lambda}\partial_{\lambda})(\phi^{2})  \\
\phi^{2}\delta(\chi^{2}) = \phi^{2}(2+x^{\lambda}\partial_{\lambda})(\chi^{2})  \\
\delta(\phi^{2}\chi^{2}) = (4+x^{\lambda}\partial_{\lambda})(\phi^{2}\chi^{2}) 
\end{gather}$$
>And
>$$\begin{gather}
\delta(\partial_{\mu}\chi) = \partial_{\mu}((1+x^{\lambda}\partial_{\lambda})\chi) = \partial_{\mu}\chi + (\partial_{\mu}x^{\lambda})(\partial_{\lambda}\chi) + x^{\lambda}\partial_{\mu}\partial_{\lambda}\chi = (2\partial_{\mu} + x^{\lambda}\partial_{\lambda}\partial_{\mu})\chi \\
\delta[(\partial_{\mu}\chi)(\partial^{\mu}\chi)] = 4(\partial_{\mu}\chi)(\partial^{\mu}\chi) + 2x^{\lambda}\partial^{\mu}\chi(\partial_{\lambda}\partial_{\mu}\chi) = 4(\partial_{\mu}\chi)(\partial^{\mu}\chi) + x^{\lambda}\partial_{\lambda}(\partial_{\mu}\chi \partial^{\mu}\chi)
\end{gather} $$
>So
>$$\begin{align}
\delta L & = -\frac{\mu_{0}^{2}}{2}(4+x\cdot \partial)(\phi^{2}\chi^{2}) + \frac{1}{2f^{2}}(4+x\cdot \partial)(\partial_{\mu}\chi \partial^{\mu}\chi) \\
& = -\frac{\mu_{0}^{2}}{2} \partial_{\mu}(x^{\mu}\phi^{2}\chi^{2}) + \frac{1}{2f^{2}}\partial_{\mu}(x^{\mu}\partial_{\nu}\chi \partial^{\nu}\chi) \\
& = \partial_{\mu}\left[  -\frac{\mu_{0}^{2}}{2}x^{\mu}\phi^{2}\chi^{2} + \frac{1}{2f^{2}} x^{\mu}(\partial_{\nu}\chi)^{2} \right]
\end{align} $$
>in which, $\delta L$ is a total derivative. Hence the Lagrangian is scale invariant, which implies the action is invariant under the scale transformation.
>
>

(c) Explain why a classically scale invariant Lagrangian for a quantum field theory may fail to be scale invariant quantum mechanically

>[!S]
> A classically scale invariant theory can lose this symmetry at the quantum level due to renormalization. In order to regulate divergences, one introduces a renormalization scale $\mu$, which explicitly breaks scale invariance. As a result, the couplings become scale-dependent and satisfy the renormalization group equation $\mu \frac{d g}{d\mu} = \beta(g)$.
> 
> When $\beta(g)\neq 0$, the trace of the energy-momentum tensor acquires an anomalous contribution:  
> $$T^\mu_{\ \mu} = \beta(g)\frac{\partial \mathcal{L}}{\partial g}$$ 
> which is non-zero even though it vanishes classically. This is known as the scale (trace) anomaly.

