---
up:
  - "[[写题]]"
related:
date: 2026-04-11
tags:
  - 量子力学
  - 习题
---
## 5.2

试将三维各向同性的谐振子的径向方程和库伦场中束缚态的径向方程联系起来，用后者的本征解得出前者的本征解。

>[!S]
>谐振子的势为 $V(r)=\lambda r^{2},\lambda>0$ 而 $(H,\mathbf{L}^{2},L_{z})$ 的共同本征函数可以表示为
>$$\psi(r,\theta,\phi) = R(r)Y_{lm}(\theta,\phi) = \frac{u(r)}{r}Y_{lm}(\theta,\phi) $$
>其中 $u(r)$ 满足方程
>$$\frac{\hbar^{2}}{2\mu} \frac{d^{2}u}{dr^{2}} + \left[  E - \lambda r^{2} - l(l+1) \frac{\hbar^{2}}{2\mu r^{2}}  \right]u = 0 \tag{1} $$
>库伦势为 $V'(r)=\lambda' /r,\lambda'<0$ 而 $(H,\mathbf{L}^{2},L_{z})$ 的共同本征函数可以表示为
>$$\psi(r,\theta,\phi) = \frac{w(r)}{r}Y_{lm}(\theta,\phi) $$
>其中 $w(r)$ 满足方程
>$$\frac{\hbar^{2}}{2\mu} \frac{d^{2}w}{dr^{2}} + \left[  E' - \frac{\lambda'}{r} - l(l+1) \frac{\hbar^{2}}{2\mu r^{2}}  \right]w = 0 \tag{2} $$
>取坐标变换：
>$$\boxed{ \rho = r^{2} ,\quad u(r) = \rho^{-1/4}v(\rho) } $$
>于是 $v(\rho)$ 满足方程
>$$\frac{\hbar^{2}}{2\mu} \frac{d^{2}v}{d\rho^{2}} + \left[  E'' - \frac{\lambda''}{\rho} - l'(l'+1) \frac{\hbar^{2}}{2\mu \rho^{2}} \right]v = 0 \tag{3} $$
>其中 $E''=-\lambda /4<0,\lambda''=-E /4<0,l'=l /2 -1 /4$ 可见 $v(r)$ 和 $w(r)$ 有相同的解。对于 $w(r)$ 其本征解有
>$$E' = -\frac{\mu}{2\hbar^{2}}(\lambda')^{2}(n_{r}+l+1)^{-2} $$
>$$w(r) = r^{l+1} F\left(  -n_{r},2l+2, \frac{2\mu|\lambda'|r}{(n_{r}+l+1)\hbar^{2}}  \right)\exp\left[  -\frac{\mu|\lambda'|r}{(n_{r}+l+1)\hbar^{2}}  \right] $$
>于是方程 (3) 的解为
>$$E'' = -\frac{\mu}{2\hbar^{2}}(\lambda'')^{2}(n_{r}+l'+1)^{-2} $$
>$$v(r) = r^{l'+1}F\left( -n_{r},2l'+2,  \frac{2\mu|\lambda''|r}{(n_{r}+l'+1)\hbar^{2}} \right) \exp\left[  -\frac{\mu|\lambda''|r}{(n_{r}+l'+1)\hbar^{2}}  \right] $$
>即
>$$-\frac{\lambda}{4} = -\frac{\mu}{2\hbar^{2}} \left( \frac{E}{4} \right)^{2}\left( n_{r} + \frac{l}{2} + \frac{3}{4} \right)^{-2} \implies E = \sqrt{ \frac{2\hbar^{2}\lambda}{\mu} }\left( l+2n_{r}+ \frac{3}{2} \right) $$


## 5.3

对于中心幂函数型中心势场
$$V(r) = \lambda r^{\nu} ,\quad -2<\nu<\infty $$
寻找变换，将 $\nu>0$ 与 $\nu<0$ 的径向方程联系起来，并加以讨论

>[!S]
>$(H,\mathbf{L},L_{z})$ 的共同本征函数表示为
>$$\psi = R(r)Y_{lm}(\theta,\phi) = \frac{u(r)}{r} Y_{lm}(\theta,\phi) $$
>径向方程为
>$$\frac{\hbar^{2}}{2\mu} \frac{d^{2}u}{dr^{2}} + \left[ E-\lambda r^{\nu}-l(l+1) \frac{\hbar^{2}}{2\mu r^{2}} \right]u =0 $$
>考虑变换
>$$\rho = r^{k} ,\quad u(r) = \rho^{m}v(\rho) $$
>将径向方程变换为
>$$\frac{\hbar^{2}}{2\mu} \frac{d^{2}v}{d\rho^{2}} + \left[  E' - \lambda'\rho^{\nu'} - l'(l'+1) \frac{\hbar^{2}}{2\mu \rho^{2}}  \right]v =0 $$
>则径向方程变为
>$$\frac{d}{dr} = k\rho^{1-1/k} \frac{d}{d\rho} $$
>$$\frac{d^{2}u}{dr^{2}} = k^{2}\rho^{2+m-2/k} \frac{d^{2}v}{d\rho^{2}} + k^{2}\left( 2m+1-\frac{1}{k} \right)\rho^{1+m-2/k} \frac{dv}{d\rho} + k^{2}m\left( m-\frac{1}{k} \right)v $$
>为了使径向方程符合原方程，不应该有一阶导项，故 $m=\frac{1}{2}\left( \frac{1}{k}-1 \right)$ 于是
>$$\frac{d^{2}u}{dr^{2}} = k^{2} \rho^{3/2 - 3/2k} \frac{d^{2}v}{d\rho^{2}} - \frac{k^{2}}{2}\left( \frac{1}{k} -1 \right)\left(  \frac{1}{2k} + \frac{1}{2} \right)v $$
>$$\left[ E-\lambda r^{\nu}-l(l+1) \frac{\hbar^{2}}{2\mu r^{2}} \right]u = \left[ E-\lambda \rho^{\nu/k} -l(l+1) \frac{\hbar^{2}}{2\mu r^{2}} \right]\rho^{1/2k - 1/2}u $$
>取 $k=-\frac{\nu+2}{2}$ 则方程变换为
>$$\frac{\hbar^{2}}{2\mu} \frac{d^{2}v}{d\rho^{2}} + \left[  E' - \lambda'\rho^{\nu'} - l'(l'+1) \frac{\hbar^{2}}{2\mu \rho^{2}}  \right]v = 0 $$
>其中
>$$E' = -\lambda\left( \frac{\nu+2}{2} \right)^{2},\quad \lambda'=-E\left( \frac{\nu+2}{2} \right)^{2},\quad \nu' = -\frac{2\nu}{\nu+2} ,\quad l'= \frac{2l+1}{2+\nu} - \frac{1}{2} $$
>通过这个变换，可以联系起两个势间的关系，对于平方势 $\nu=2$ 其对应 $\nu'=-1$ 也就是 5.2 中讨论的问题。


