---
up:
related:
date: 2026-03-16
---
# 1. 何时需要 Cartan 结构方程

在广义相对论的计算中，我们常常遇到需要解出来度规的情况，丘赛考了很多遍 [[Yau 广义相对论]] . 但是问题是我们按照定义来计算这个过程的时候无非是这样的过程

1. 由度规 $g_{\mu \nu}$ 计算出联络 $\Gamma^{\mu}_{\nu \rho}$
   $$\Gamma_{\rho \mu \nu} = \frac{1}{2}(\partial_{\mu}g_{\rho \nu} + \partial_{\nu}g_{\rho \mu} - \partial_{\rho}g_{\mu \nu}) $$
2. 由度规 $\Gamma^{\rho}_{\mu \nu}$ 计算出里奇张量 $R_{\mu \nu}$
   $${R^{\mu}}_{\nu \rho \sigma} = \partial_{\rho}{\Gamma^{\mu}}_{\nu \sigma} + \partial_{\sigma}{\Gamma^{\mu}}_{\nu \rho} - \Gamma^{\alpha}_{\nu \sigma}\Gamma^{\mu}_{\alpha \rho} - \Gamma^{\alpha}_{\nu \rho}\Gamma^{\mu}_{\nu \sigma} $$
   $$R_{\mu \nu} = {R^{\rho}}_{\mu \nu \rho} $$
3. 由爱因斯坦场方程得 $R_{\mu \nu}=0$  得到方程组

但是问题是这里涉及的计算很多，而且很容易算错。我们常常选取坐标基 $\partial_{\mu}$ 它对于度规 $g_{\mu \nu}$ 但是还可以考虑局域正交系：
$$ds^{2} = \eta_{ab}e^{a}e^{b} ,\quad \eta=\text{diag(1,-1,-1,-1)} $$

# 2. 结构方程

结构方程有两个，第一个可以通过坐标基 $e^{a}$ 来求自旋联络：

$$de^{a} + {\omega^{a}}_{b}\wedge e^{b} = 0 $$

其中的 $e^{a}$ 是基的 1-from

第二个是通过自旋联络来直接计算曲率：

$${\Omega^{a}}_{b} = d{\omega^{a}}_{b} + {\omega^{a}}_{c}\wedge {\omega^{c}}_{b} $$

这个曲率和里奇曲率的关系是
$${\Omega^{a}}_{b} = \frac{1}{2}{R^{a}}_{bcd} e^{c}\wedge e^{d} $$

# 3. 例

参考 [[Yau 广义相对论#23 年|de Sitter]] 例题，其中
$$ds^{2} = -f(r)dt^{2} + \frac{1}{f(r)}dr^{2} + r^{2}d\theta^{2} + r^{2}\sin^2\theta d\phi^{2} $$

我们取局部正交基为
$$e^{0}=\sqrt{ f }dt ,\quad e^{1} = \frac{1}{\sqrt{ f }}dr ,\quad e^{2}=r d\theta ,\quad e^{3} = r\sin \theta d\phi $$
则
$$\begin{align}
de^{0} = \frac{f'}{2f}e^{1}\wedge e^{0} ,\quad & de^{1} = 0 \\
de^{2} = \frac{\sqrt{ f }}{r} e^{1}\wedge e^{2} ,\quad & de^{3} = \frac{\sqrt{ f }}{r} e^{1}\wedge e^{3} + \frac{\cot \theta}{r} e^{2}\wedge e^{3}
\end{align} $$
于是由第一结构方程立刻看出来，一个楔积一个联络
$$\begin{align}
 & {\omega^{0}}_{1} = \frac{f'}{2f}e^{0} ,\quad {\omega^{0}}_{2} = 0 ,\quad {\omega^{0}}_{3} = 0 \\
 & {\omega^{1}}_{2} = -\frac{\sqrt{ f }}{r}e^{2} ,\quad {\omega^{1}}_{3}  = -\frac{\sqrt{ f }}{r} e^{ 3 } \\
 & {\omega^{2}}_{3} = \frac{\cot \theta}{r}e^{3}
\end{align} $$
其它的按照反对称性易得其它的分量，然后代入道第二节后方程直接得到各个曲率
$$\begin{align}
 & {\Omega^{0}}_{1} = d{\omega^{0}}_{1} + {\omega^{0}}_{a}\wedge{\omega^{a}}_{1} = d\left( \frac{f'}{2f} \right)\wedge e^{ 0 } + \frac{f'}{2f}de^{ 0 } + 0 = \frac{f''}{2}e^{ 1 }\wedge e^{ 0 } \\
 & {\Omega^{0}}_{2} = d{\omega^{0}}_{2} + {\omega^{0}}_{a}\wedge{\omega^{a}}_{2} = 0 + {\omega^{0}}_{1}\wedge{\omega^{1}}_{2} = -\frac{f'}{2f}e^{ 0 }\wedge e^{ 2 } \\
 & {\Omega^{0}}_{3} = d{\omega^{0}}_{3} + {\omega^{0}}_{a}\wedge{\omega^{a}}_{3} = {\omega^{0}}_{1}\wedge{\omega^{1}}_{3} = -\frac{f'}{2f}e^{ 0 }\wedge e^{ 3 } \\
 & {\Omega^{1}}_{2} = d{\omega^{1}}_{2} + {\omega^{1}}_{a}\wedge{\omega^{a}}_{2} = d\left( -\frac{\sqrt{ f }}{r} \right)\wedge e^{ 2 } + -\frac{\sqrt{ f }}{r}de^{ 2 } = -\frac{f'}{2f}e^{ 1 }\wedge e^{ 2 } \\
 & {\Omega^{2}}_{3} = d{\omega^{2}}_{3} + {\omega^{2}}_{a}\wedge{\omega^{a}}_{3} = d\left( \frac{\cot \theta}{r} \right)\wedge e^{ 3 } + \frac{\cot \theta}{r}de^{ 3 } + {\omega^{2}}_{1}\wedge{\omega^{1}}_{3} = \frac{1-f}{r^{2}}e^{ 2 }\wedge e^{ 3 }
\end{align} $$
由 ${\Omega^{a}}_{b} = \frac{1}{2}{R^{a}}_{bcd} e^{c}\wedge e^{d}$ 可瞪出曲率张量
$$\begin{align}
 & {R^{0}}_{110} = f'' \implies{R^{0}}_{101} = -f'' \\
 & {R^{0}}_{220} = \frac{f'}{f} \implies {R^{0}}_{202} = -\frac{f'}{f} \\ 
 & {R^{0}}_{330} = \frac{f'}{f} \implies {R^{0}}_{303} = -\frac{f'}{f} \\
 & {R^{1}}_{221} = \frac{f'}{f} \implies {R^{1}}_{212} = -\frac{f'}{f} \\
 & {R^{2}}_{323} = \frac{2(1-f)}{r^{2}} \implies {R^{2}}_{323} = \frac{2(1-f)}{r^{2}}
\end{align} $$
于是黎曼张量
$$\begin{gather}
R_{0101} = -f'' \\
R_{0202} = R_{0303} = -\frac{f'}{f} \\
R_{1212} = R_{1313} = -\frac{f'}{r} \\
R_{2323} = \frac{2(1-f)}{r}
\end{gather} $$
所以得到里奇张量
$$\begin{gather}
R_{00} = R_{0101} + R_{0202} + R_{0303} = -f'' - \frac{2f'}{r} \\
R_{11} = R_{1010} + R_{1212} + R_{1313} = -f'' - \frac{2f'}{r} \\
R_{22} = R_{2020} + R_{2121} + R_{2323} = -\frac{2f'}{r} + \frac{2(1-f)}{r} \\
R_{33} = R_{3030} + R_{3131} + R_{3232} = -\frac{2f'}{r} + \frac{2(1-f)}{r}
\end{gather} $$
转回到坐标基并由爱因斯坦方程得到
$$\begin{gather}
R_{tt} = \frac{f}{2}\left( f'' + \frac{2f'}{r} \right) = \Lambda g_{tt} = -\Lambda f \\
R_{rr} = -\frac{1}{2f}\left( f'' + \frac{2f'}{r} \right) = \Lambda g_{rr} = \frac{\Lambda}{f} \\
R_{\theta \theta} = 1 -f -rf' = \Lambda g_{\theta \theta} = \Lambda r^{2} \\
R_{\phi \phi} = (1-f-rf')\sin^2\theta = \Lambda g_{\phi \phi} = \Lambda r^{2}\sin^2\theta
\end{gather} $$
直接解得
$$f(r) = 1 -\frac{2M}{r} - \frac{\Lambda}{3}r^{2} $$
