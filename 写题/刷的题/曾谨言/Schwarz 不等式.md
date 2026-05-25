---
up:
  - "[[写题]]"
related:
date: 2026-04-10
tags:
  - 量子力学
  - 习题
---

## 4.27

对于任意两个态矢量 $\ket{\psi}$ , $\ket{\phi}$ 证明下面的不等式
$$|\braket{ \psi | \phi } |^{2} \leq \braket{ \psi | \psi } \braket{ \phi | \phi }   $$
这被称为 Schwarz 不等式，取等条件是它们代表同一个态。

>[!S]
>记 $\braket{ \psi | \psi }=a$ , $\braket{ \phi | \phi }=b$ , $\braket{ \psi | \phi }=c$ 则 $a,b>0$ 构造
>$$\ket{\chi} = \ket{\psi} + \lambda \ket{\phi} ,\quad \langle \chi| = \langle \psi| + \lambda^{*}\langle \phi| $$
>则
>$$\braket{ \chi | \chi } = a + \lambda c + \lambda^{*}c^{*} + |\lambda|^{2}b $$
>为了证明 $|c|^{2}\leq ab$ 取 $\lambda = -c^{*} /b$ 则
>$$\braket{ \chi | \chi } = a - \frac{|c|^{2}}{b} \geq 0 \implies |c|^{2}\leq ab $$
>取等时显然为 $\ket{\chi}=\ket{\psi}-\frac{c^{*}}{b}\ket{\phi}=0$ 即 $\ket{\psi}\propto \ket{\phi}$ 此时两个态矢量是同一个态


## 4.28

使用 Schwarz 不等式证明不确定性关系。
$$\Delta A\cdot\Delta B \geq \frac{1}{2} |\braket{ AB - BA } | $$

>[!S]
>取态 $\ket{\psi}$ 则
>$$(\Delta A)^{2} = \braket{ \psi |(A-\braket{ A } )^{2}| \psi } := \braket{ a | a } ,\quad \ket{a} = (A-\braket{ A } )\ket{\psi}  $$
>$$(\Delta B)^{2} = \braket{ \psi |(B-\braket{ B } )^{2}| \psi } := \braket{ b | b } ,\quad \ket{b} = (B - \braket{ B } )\ket{\psi}  $$
>$$\braket{ (A-\braket{ A } )(B-\braket{ B } ) } = \braket{ \psi |(A-\braket{ A } )(B-\braket{ B } )| \psi } = \braket{ a | b }  $$
>由 Schwarz 不等式得到
>$$|\braket{ (A-\braket{ A } )(B-\braket{ B } ) }|^{2} \leq (\Delta A)^{2}(\Delta B)^{2} $$
>$$|\braket{ (A-\braket{ A } )(B-\braket{ B } ) }| \leq (\Delta A)(\Delta B) $$
>而
>$$\braket{ (A-\braket{ A } )(B-\braket{ B } ) } = \frac{\braket{ \{ \delta A,\delta B \} } + \braket{ [A,B] }  }{2} $$
>其中 $[A,B]$ 是反厄米的，所以期望值是纯虚的，于是
>$$|\braket{ \delta A\delta B } | \geq \frac{|\braket{ [A,B] }|}{2}  $$
>$$(\Delta A)(\Delta B) \geq |\braket{ \delta A\delta B } | \geq \frac{|\braket{ [A,B] }|}{2} $$
>于是证毕


## 4.29

设 $H$ 是正定的厄米算符，$\ket{\phi},\ket{\psi}$ 是任意的态矢量，证明
$$|\braket{ \psi |H| \phi }|^{2} \leq \braket{ \psi |H| \psi } \braket{ \phi |H| \phi }   $$

>[!S]
>构造态
>$$\ket{\chi} = \ket{\psi} - \lambda \ket{\phi} ,\quad \langle \chi|=\langle \psi|-\lambda^{*}\langle \phi| $$
>则
>$$\braket{ \chi |H| \chi } = \braket{ \psi |H| \psi } + |\lambda|^{2}\braket{ \phi |H| \phi } -\lambda \braket{ \psi |H| \phi } - \lambda^{*}\braket{ \phi |H| \psi } \geq 0  $$
>取 
>$$\lambda= \frac{\braket{ \phi |H| \psi }}{\braket{ \phi |H| \phi } } $$
>则
>$$\braket{ \psi |H| \psi } - \frac{|\braket{ \phi |H| \psi }|^{2}}{\braket{ \phi |H| \phi }}  \geq 0 $$
>证毕

