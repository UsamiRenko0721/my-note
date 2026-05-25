---
up:
  - "[[随笔]]"
---

# SU(2) 的数学


## SU(2) 既是群又是流形

$SU(2)$ 顾名思义是

$$SU(2) = \{ U \in \mathbb{C}^{2\times 2} \mid U^{\dagger}U = 1 , \det U = 1 \} $$

任意的 $SU(2)$ 可以参数化为

$$U = \begin{pmatrix}
a & b \\
-b^{*} & a^{*}
\end{pmatrix} ,\quad |a|^{2} + |b|^{2} = 1 $$

这说明 $SU(2)$ 在流形上与三维球面 $S^{3}$ 同胚 ( $\mathrm{Re}^{2}(a) + \mathrm{Im}^{2}(a) + \mathrm{Re}^{2}(b) + \mathrm{Im}^{2}(b)=1$ ) 


## SU(2) 的神秘李代数

$SU(2)$ 的李代数 $\mathfrak{su}(2)$ 是所有无迹反厄米矩阵组成（物理中常取厄米形式）。一组方便的基是泡利矩阵：

$$\sigma_{1} = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix} ,\quad \sigma_{2} = \begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix} ,\quad \sigma_{3} = \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix} $$

然后生成元取为 $T^{a}=\frac{\sigma_{a}}{2}$ 满足对易关系：

$$[T^{a} , T^{b}] = f^{abc} T_{c} ,\quad f^{abc} = i\varepsilon^{abc} $$

李代数与李群间有指数映射关系：

$$U(\theta) = \exp(i\theta^{a}T^{a}) ,\quad \theta^{a}\in \mathbb{R} $$

## SU(2) 的表示论

$SU(2)$ 是紧致单李群，其不可约表示由“自旋” $s$ 标记 ( $s=0 , \frac{1}{2} , 1 , \dots$ ) ，维数为 $2s+1$ 

- $s=0$ 对应标量表示 $\text{dim}=1$
- $s=\frac{1}{2}$对应基本表示 $\text{dim}=2$
- $s=1$ 对应三维表示 $\text{dim}=3$

在物理中，$SU(2)$ 自旋表示直接用来描述粒子自旋和角动量叠加规则：
$$\frac{1}{2} \otimes  \frac{1}{2} = 0 \oplus  1 $$

$SU(2)$ 表示也是 $SO(3)$ 表示的“升级”，奇数维对应整数自旋，偶数维对应半整数自旋。