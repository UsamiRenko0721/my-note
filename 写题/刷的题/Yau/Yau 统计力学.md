---
up:
  - "[[写题]]"
related:
date: 2026-04-09
tags:
  - 热统
  - 习题
---
# 25 年

The Ising model on a triangle is described by the energy:
$$E = -J(\sigma_{1}\sigma_{2} + \sigma_{2}\sigma_{3}+\sigma_{3}\sigma_{1}) - h(\sigma_{1} + \sigma_{2} + \sigma_{3}) $$
Here J and h are known parameters: exchange energy and external magnetic field, respectively. The Ising spins $\sigma_{1,2,3}$ are the only degrees of freedom in the problem and they are taking values ±1. Assume that the temperature of the system is $T$. You may work in the units such that $k_{B} = 1$.

(a) Compute the partition function of the model.

>[!S]
>Let $A=\sigma_{1}+\sigma_{2}+\sigma_{3},B=\sigma_{1}\sigma_{2}\sigma_{3}$ then
>$$E = -BJ-Ah $$
>$A=3,B=1$ , $E =-3J-3h$ , 1 state; $A=1,B=-1$ , $E=J-h$ , 3 state; $A=-1,B=1$ , $E =J+h$ , 3 state; $A=-3,B=-1$ , $E =-3J+3h$ , 1 state. So the partion function of the model is 
>$$Z = e^{ \beta(3J+3h) } + 3e^{ \beta(-J+h) } + 3e^{ -\beta(J+h) } + e^{ -\beta(3J-3h) } $$

(b) Compute the free energy and the entropy of the model.

>[!S]
>$$A = -T\ln Z = -T\ln[ 2e^{ 3\beta J }\cosh(3\beta h) + 6e^{ -\beta J }\cosh(\beta h) ] $$
>$$\begin{align}
S & = -\frac{\partial A}{\partial T} = \ln[ 2e^{ 3\beta J }\cosh(3\beta h) + 6e^{ -\beta J }\cosh(\beta h) ] \\ &  - \frac{ (3J+3h)e^{ \beta(3J+3h) } + 3(-J+h)e^{ \beta(-J+h) } - 3(J+h)e^{ -\beta(J+h) } - (3J+3h)e^{ -\beta(3J-3h) } }{T(2e^{ 3\beta J }\cosh(3\beta h) + 6e^{ -\beta J }\cosh(\beta h))} 
\end{align} $$

(c) Compute the specific heat at temperature $T$ and $h = 0$. What does the specific heat look like when $T \ll J$ and $T \gg J$.

>[!S]
>When $h=0$ we have $Z=2e^{ 3J/T }+6e^{ -J/T }$ so
>$$U = \frac{\partial \ln Z}{\partial \beta} = -J \frac{6e^{ 3\beta J }-6e^{ -\beta J }}{2e^{ 3\beta J }+6e^{ -\beta J }} = -J \frac{3e^{ 4\beta J }-3}{2e^{ 4\beta J } + 3} $$
>$$C = \frac{\partial U}{\partial T} = \frac{12J^{2}}{T^{2}} \frac{e^{ \beta J }}{(e^{ 4\beta J }+3)^{2}} $$
>When $T\ll J$, $e^{ -\beta J }\approx 0$ 
>$$C = \frac{12J^{2}}{T^{2}} \frac{e^{ -4\beta J }}{(3e^{ -4\beta J }+1)^{2}} \approx \frac{12J^{2}}{T^{2}} \cdot e^{ -4J/T } $$>when $T\gg J$ , $e^{ -\beta J }\approx 1-\beta J$ 
>$$C = \frac{12J^{2}}{T^{2}} \frac{e^{ -4\beta J }}{(3e^{ -4\beta J }+1)^{2}} \approx \frac{12J^{2}}{T^{2}}\cdot \frac{1 - 2J /T}{16} $$

(d) Compute the magnetization $M = \braket{ \sigma } ≡ \braket{ \sigma_{1} + \sigma_{2} + \sigma_{3} }$ at given $h$ and $T \ll J$. What is the behavior of the magnetic susceptibility $\chi = \left. \frac{\partial M}{\partial h} \right|_{h=0}$ at low temperature ($T \ll J$)?

>[!S]
>$$Z = 2e^{ 3\beta J }\cosh(3\beta h)\left[  1 + 3e^{ -4\beta J } \frac{\cosh(\beta h)}{\cosh(3\beta h)} + \dots \right] $$
>$$M = \frac{\partial \ln Z}{\partial(\beta h)} = 3\tanh(3\beta h) + 3e^{ -4\beta J } \frac{\sinh(\beta h)\cosh(3\beta h)-3\cosh(\beta h)\sinh(3\beta h)}{\cosh^2(\beta h)} + \dots$$
>$$\chi = \frac{\partial M}{\partial h} = 9\beta\left( 1 - \frac{8}{3}e^{ -4\beta J } + \dots \right)$$
>At $T\ll J$ , we have
>$$\chi \sim \frac{9}{T} $$

(e) Find the fluctuation of magnetization $\braket{ (\sigma-M)^{2} }$ at $T\ll J$.

>[!S]
>$$\braket{ (\sigma-M)^{2} } = \braket{ \sigma^{2} } - \braket{ \sigma }^{2}  $$
>where
>$$\braket{ \sigma }^{2} = M^{2} = 9\tanh^2(3\beta h) + \mathcal{O}(e^{ -4\beta J }) $$
>$$\begin{align}
\braket{ \sigma^{2} } & = \frac{\sum(\sigma^{2}e^{ -\beta E })}{Z} \\ & = \frac{18e^{ 3\beta J }\cosh(3\beta h) + 6e^{ -\beta J }\cosh(\beta h)}{2e^{ 3\beta J }\cosh(3\beta h) + 6e^{ -\beta J }\cosh(\beta h)} \\ & = 9 - 24e^{ -4\beta J } \frac{\cosh(\beta h)}{\cosh(3\beta h)} + \mathcal{O}(e^{ -8\beta J })
\end{align} $$
>So
>$$(\Delta \sigma)^{2} = 9(1-\tanh^2(3\beta h)) + \mathcal{O}(e^{ -4\beta J }) $$
>When $T\ll J$
>$$(\Delta \sigma)^{2} = \frac{9}{\cosh^2(3\beta h)} $$

---
# 24 年

Consider the Ising model on $N$ spins $\sigma_i = \pm 1$ in an external magnetic field $h$. Within the mean field approximation, its Hamiltonian can be written as
$$
H_{\text{MF}} = \frac{1}{2} N J m^2 - (J m + h) \sum_i \sigma_i,
$$
where the coordination number of the lattice has been absorbed into the coupling constant $J$ and $m$ is the magnetization.

The magnetization, specific heat and magnetic susceptibility are defined, respectively, as
$$
m = \frac{\partial f}{\partial h}, \quad C = \frac{\partial U}{\partial T}, \quad \chi = \frac{\partial m}{\partial h},
$$
where $T$ is the temperature, $U$ the internal energy, and $f$ the free energy per site.

(a) Derive the (mean field) partition function following from $H_{\text{MF}}$ and hence calculate the free energy of the system.

>[!S]
>The partition function is
>$$Z = \sum_{\{ \sigma_{i} \}} \exp(-\beta H_{\text{MF}}) = e^{ -1/2 \beta NJm^{2} } \sum_{\{ \sigma_{i} \}} \exp(\beta\left( Jm+h)\sum_{i}\sigma_{i} \right) $$
>where because the spins are independed, the sum farctorizes
>$$\sum_{\{ \sigma_{i} \}}\prod_{i=1}^{N} e^{ \beta(Jm+h)\sigma_{i} } = \left[  \sum_{\sigma_{i}=\pm 1} e^{ \beta(Jm+h)\sigma_{i} }  \right]^{N} = 2^{N}\cosh^N(\beta(Jm+h)) $$
>So
>$$Z = 2^{N}e^{ -\beta NJm^{2}/2 } \cosh^N[\beta(Jm+h)] $$
>Hence the free energy of the system is
>$$A = -kT\ln Z = -NkT\ln 2 + \frac{1}{2}NJm^{2} + NkT\ln \cosh[\beta(Jm+h)] $$

(b) Derive the constraint on magnetization $m$, and graphically solve it for $h = 0$. Discuss the physical nature of the various solutions as a function of the temperature $T$. Identify a critical temperature $T_c$ in terms of the system parameters, and discuss its physical meaning.

>[!S]
>By definition, the magnetization is $m = \langle \sigma_i \rangle$. From the partition function,
>$$m = \frac{1}{N}\sum_{i}\sigma_{i} = \frac{1}{\beta N} \frac{\partial \ln Z}{\partial h} = \tanh[\beta(Jm+h)] $$
>When $h=0$ the equation reduce to
>$$m = \tanh(\beta Jm) $$
>Clearly $m=0$ is a solution of the1equation, we need another non-zero solution, and to fit it requirement, we considier the function $f(x)=x-\tanh(\beta Jx)$ ,which $f'(x)=1-\beta J\cosh^{-2}(\beta Jx)$ . We find that if $\beta J\leq1$ , then it can't have the non-zero solution, if $\beta J>1$ , then it's possible to have an non-zero solution. The critical temperature $T_{c}$ suit
>$$\beta J = 1 \implies T_{c} = J / k_{B} $$
>- $T > T_c$: Paramagnetic phase – thermal fluctuations destroy order, net magnetization vanishes.
>- $T < T_c$: Ferromagnetic phase – spontaneous magnetization appears, symmetry is spontaneously broken.
>- $T = T_c$: Second-order phase transition point; the magnetization grows continuously from zero.
>

(c) Assuming $\beta(J m + h) \ll 1$, derive the expression for the dependence of the magnetization, the specific heat and the magnetic susceptibility on the quantity
$$
t = \frac{T - T_c}{T_c},
$$
where $T_c$ is the critical temperature, and thereby determine the mean-field critical exponents $\alpha_c$, $\beta_c$, and $\gamma_c$ which are defined through the relations
$$
m \sim |T - T_c|^{\beta_c}, \quad C \sim |T - T_c|^{-\alpha_c}, \quad \chi = \left. \frac{\partial m}{\partial h} \right|_{h=0} \sim |T - T_c|^{-\gamma_c}.
$$
For the calculation of the specific heat, note that, within the mean field approximation near the critical point, the internal energy is $U \propto J m^2$.```

>[!S]
>$$T = T_{c}(1+t) $$
>Because $\beta(Jm+h)\ll 1$ expand $\tanh$ to third order
>$$\tanh(\beta(Jm+h)) \approx \beta (Jm+h) - \frac{\beta^{3}(Jm+h)^{3}}{3} $$
>Thus 
>$$m = \beta (Jm+h) - \frac{\beta^{3}(Jm+h)^{3}}{3} \approx \beta Jm + \beta h - \frac{\beta^{3}J^{3}m^{3}}{3} $$
>Insert $\beta J = \frac{1}{1+t} \approx 1 - t$ and $\beta \approx 1/T_c$ (lowest order). To leading order, $(\beta J)^3 \approx 1$. Therefore
>$$m = (1-t)m + \frac{h}{T_{c}} - \frac{1}{3}m^{3} $$
>or
>$$tm + \frac{1}{3}m^{3} = \frac{h}{T_{c}} $$
>Set $h=0$ then $m=\pm \sqrt{ t }$ hence $\beta_{c}=\frac{1}{2}$. Differentiating gives
>$$t \left( \frac{\partial m}{\partial h} \right)_{t} + m^{2}\left( \frac{\partial m}{\partial h} \right)_{t} = \frac{1}{T_{c}} \implies \chi = \frac{1}{T_{c}(t+m^{2})} \sim |t|^{-1} $$
>Hence $\gamma_{c}=1$. Near the critical point the internal energy per spin is $u \propto J m^2$ (as stated in the problem). And $$u = \frac{1}{2} J m^2$$
>Thus
>$$C = \left( \frac{\partial U}{\partial T} \right)_{h} = \frac{Jm}{T_{c}}\left( \frac{\partial m}{\partial t} \right)_{h} = \frac{J}{2T_{c}} $$
>is a finite constant, so a non-diverging heat capacity corresponds to
>$$\alpha_{c}=0 $$

