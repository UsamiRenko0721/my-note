---
up:
  - "[[随笔]]"
related:
  - "[[球谐函数相关计算]]"
date: 2026-04-12
---
>[!yellow]
>设 $T^{(k)}_{q}$ 是一个 $k$ 阶的、分量为 $q$ 的不可约张量算符，则
>$$\braket{ \alpha',j',m' | T^{(k)}_{q}| \alpha,j,m } = \braket{ j,m;k,q | j',m' } \frac{\braket{ \alpha',j' \| T^{(k)}_{q} \| \alpha,j }}{\sqrt{ 2j'+1 } }  $$
>其中 $\braket{ j,m;k,q | j',m' }$ 是 CG 系数，完全由角动量代数决定，与具体算符和径向波函数无关；$\braket{ \alpha',j' \| T^{(k)}_{q} \| \alpha,j }$ 称为约化矩阵元，与 $m,m',q$ 这些磁量子数无关，只依赖于角动量大小 $j,j'$、张量阶数 $k$ 以及系统的其余量子数 $α,α'$


## 例1

取 [[球谐函数相关计算#6.8]] 中的计算核心
$$\langle  00| \frac{\mathbf{r}}{r}| 1 m \rangle $$
其中 $\frac{\mathbf{r}}{r}$ 就是一个 $k=1$ 的不可约张量 (矢量)，其有三个分量。然后求 $\ket{00}$ 和 $\ket{1m}$ 间的矩阵元，其实就是选定了 $j=0,j'=1$ 而其它的量子数不管。
