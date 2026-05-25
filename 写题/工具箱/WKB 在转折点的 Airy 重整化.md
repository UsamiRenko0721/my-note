---
up:
  - "[[元例子]]"
related:
date: 2026-02-11
---

# 问题背景

>[!example]
>考虑一维薛定谔方程 (取 $\hbar=1$)
>$$- \frac{d^{2}\psi}{dx^{2}} + V(x)\psi = E\psi $$
>WKB 方法在 **classically allowed** 区
>$$\psi(x) \approx \frac{1}{\sqrt{ p(x) }} \exp\left( \pm \int_{0}^{x} p(x') dx' \right)$$
>在 **classically forbidden** 区
>$$\psi(x) \approx \frac{1}{\sqrt{ p(x) }} \exp\left( -\int_{0}^{x} p(x')dx' \right) $$
>其中 $p(x)=\sqrt{ E-V(x) }$ 

问题出在转折点处即 $E=V(x_{0})$ 此时 $p(x)=0$ 在分母位置上于是波函数发散，这是不物理的。

> 这里就是经典 WKB 的 “secular divergence” 的 analog


# 问题根源

WKB 方法的使用前提是

$$\frac{1}{p} \frac{dV}{dx} \ll 1 $$

也就是说势的变化趋势远远小于粒子的波长。但是在 $E=V(x_{0})$ 处由于粒子的波长无穷长，必然与变化势无法相容 (常势不考虑) 。局部波长短于势变化尺度失效。这个发散是原变量尺度与局部解尺度不匹配造成的假发散，为了消除它我们做坐标重标定
$$\xi = \alpha(x-x_{0}) ,\quad \alpha[V'(x_{0})]^{1/3} $$
在此时我们再展开
$$E-V = V'\xi + \mathcal{O}(\xi^{2}) $$
$$-\frac{d^{2}\psi}{d\xi^{2}} + \xi \psi = 0 $$

# 问题解决

