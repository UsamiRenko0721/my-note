---
up:
  - "[[随笔]]"
related:
date: 2026-05-03
---
## 前言

在无质量的相对论场论中，我们常常会遇到很多棘手的问题，比如 QED 中光子到底有没有质量是直接影响体系的自由度的，即使场的自旋都是 1，有质量的 W 玻色子的螺旋态就是 3 个，而光子就是 2 个。为了语言上的便利，我们选择一个合适的坐标系——光锥坐标，来描述体系。可以看到在这个坐标系下，我们甚至可以避免鬼场的引入。


## QED

在QED中，我们的光子场的拉式量是

$$\mathcal{L} = -\frac{1}{4}F^{\mu \nu}F_{\mu \nu} + \frac{1}{2}\bar{\psi}(i\not{\!\!D}-m)\psi $$

我们引入光锥坐标

$$x^{+} = \frac{x^{0}+x^{3}}{2} ,\quad x^{-}=\frac{x^{0}-x^{3}}{2},\quad \mu = (+,-,i),i=1,2 $$

这样度规变为

$$ds^{2} = -2dx^{+}dx^{-} + dx^{i}dx^{i} $$
$$g_{\mu \nu} = \text{diag}\left(\begin{pmatrix}
0 & -1 \\
-1 & 0
\end{pmatrix} , 1 , 1\right) $$

于是导数，作为协变矢量

$$\partial_{\pm} = \frac{\partial_{0}\pm \partial_{3}}{\sqrt{ 2 }} ,\quad \partial_{i}=\partial_{i} $$

在这种坐标系下，矢量场的坐标分量记为

$$\mathbf{A}=(A^{+},A^{-},A^{1},A^{2}) $$

现在我们选择规范 $A^{+}=0$ ，类似轴向规范，只是我们是在光锥坐标系下选择的而已。在这种规范选择和坐标系选择下

$$F^{ij} = \partial^{i}A^{j} - \partial^{j}A^{i} ,\quad i,j=1,2 $$
$$F^{+i} = \partial^{+}A^{i} , \quad F^{-i}= \partial^{-}A^{i} - \partial^{i}A^{-} ,\quad F^{+ -} = \partial^{+}A^{-} $$

于是

$$\begin{align}
F^{\mu \nu}F_{\mu \nu} & = -2F^{+ -}F^{+ -} + F^{11}F^{11} + F^{22}F^{22} \\
 & = -2(\partial^{+}A^{-})^{2} + F^{11}F^{11} + F^{22}F^{22}
\end{align} $$

由欧拉拉格朗日方程可得

$$\partial_{\mu}F^{\mu \nu} = 0 $$

我们考虑 $\nu=+$ 的方向，由于 $A^{+}=0$ 所以
$$\partial_{\mu}F^{\mu+} = 0  $$
$$A^{-} = (\partial^{+})^{-1}(\partial^{i}A^{i}) $$

其中 $\partial^{+}= \frac{\partial }{\partial x^{-}}$ 而 $(\partial^{+})^{-1}$ 是这个微分算符的逆。可见其实 $A^{-}$ 是必须满足上面这个方程的，被 $A^{1},A^{2}$ 完全决定，不是独立的动力学变量。


我们进一步的旋转坐标系，选取螺旋态基底

$$A^{(\pm)} = \frac{A^{1}\pm iA^{2}}{\sqrt{ 2 }} $$

那么这个基底在 $SO(2)$ 下由变换关系

$$A^{(\pm)} \to e^{ \pm i\theta }A^{(\pm)} $$

正好对应了螺旋数 $h=\pm 1$ 