---
up:
  - "[[随笔]]"
related:
  - "[[Wigner-Eckart 定理]]"
date: 2026-04-12
---

## 问题的起源：两个角动量的耦合

考虑两个独立的角动量算符 $\mathbf{J}_1$ 和 $\mathbf{J}_2$，它们满足各自的角动量对易关系且彼此对易：
$$
[\mathbf{J}_1, \mathbf{J}_2] = 0
$$
各自的态空间由本征态 $|j_1, m_1\rangle$ 和 $|j_2, m_2\rangle$ 张成。

当我们把这两个系统放在一起，总角动量定义为：
$$
\mathbf{J} = \mathbf{J}_1 + \mathbf{J}_2
$$
总角动量也满足角动量对易关系，并且 $\mathbf{J}^2$ 和 $J_z$ 与 $\mathbf{J}_1^2$、$\mathbf{J}_2^2$ 对易。因此我们可以选取两组不同的力学量完全集来描述同一复合系统的态：

**1. 无耦合表象（直积基）**  
力学量完全集：$\{\mathbf{J}_1^2, \mathbf{J}_2^2, J_{1z}, J_{2z}\}$  
基矢：$|j_1, m_1\rangle \otimes |j_2, m_2\rangle \equiv |j_1, j_2; m_1, m_2\rangle$ 
维数：$(2j_1+1)(2j_2+1)$

**2. 耦合表象（总角动量基）**  
力学量完全集：$\{\mathbf{J}_1^2, \mathbf{J}_2^2, \mathbf{J}^2, J_z\}$ 
基矢：$|j_1, j_2; j, m\rangle$ 
维数：对固定的 $j_1, j_2$，$j$ 的取值范围为 $|j_1-j_2| \le j \le j_1+j_2$，总维数相同。

这两组基通过一个幺正变换相联系：
$$
|j_1, j_2; j, m\rangle = \sum_{m_1, m_2} |j_1, j_2; m_1, m_2\rangle \langle j_1, j_2; m_1, m_2 | j_1, j_2; j, m\rangle
$$
这里的展开系数就是 **Clebsch-Gordan 系数**，通常记作：
$$
\langle j_1, m_1; j_2, m_2 | j, m \rangle \quad \text{或} \quad C_{j_1 m_1 j_2 m_2}^{j m}
$$

---

## CG 系数的基本性质

#### 1. 非零条件（选择定则）
CG 系数非零当且仅当：
- $m = m_1 + m_2$ （由 $J_z = J_{1z} + J_{2z}$ 保证）
- $|j_1 - j_2| \le j \le j_1 + j_2$ （三角形法则）
- 此外，$m_1 \in [-j_1, j_1]$，$m_2 \in [-j_2, j_2]$，$m \in [-j, j]$

#### 2. 正交归一性
由于基的幺正性：
$$
\sum_{m_1, m_2} \langle j, m | j_1, m_1; j_2, m_2 \rangle \langle j_1, m_1; j_2, m_2 | j', m' \rangle = \delta_{j j'} \delta_{m m'}
$$
$$
\sum_{j, m} \langle j_1, m_1; j_2, m_2 | j, m \rangle \langle j, m | j_1, m_1'; j_2, m_2' \rangle = \delta_{m_1 m_1'} \delta_{m_2 m_2'}
$$

#### 3. 相位约定
通常约定：
- CG 系数为实数。
- 对于最大的 $m = j$，展开系数中 $|j_1, j_1; j_2, j-j_1\rangle$ 项的系数取正号（Condon-Shortley 约定）。

#### 4. 对称性
CG 系数有许多对称关系，常见的有：
$$
\langle j_1, m_1; j_2, m_2 | j, m \rangle = (-1)^{j_1+j_2-j} \langle j_2, m_2; j_1, m_1 | j, m \rangle
$$
以及交换、时间反演等多种对称性（可查表获得）。

#### 5. 递推关系
利用升降算符 $J_\pm = J_{1\pm} + J_{2\pm}$ 作用在 $|j, m\rangle$ 上，可以得到 CG 系数的递推公式。例如：
$$
\begin{align}
 & \quad\sqrt{(j \mp m)(j \pm m + 1)} \langle j_1, m_1; j_2, m_2 | j, m \pm 1 \rangle \\
 & = \sqrt{(j_1 \pm m_1)(j_1 \mp m_1 + 1)} \langle j_1, m_1 \mp 1; j_2, m_2 | j, m \rangle \\ & \quad
+ \sqrt{(j_2 \pm m_2)(j_2 \mp m_2 + 1)} \langle j_1, m_1; j_2, m_2 \mp 1 | j, m \rangle
\end{align}
$$


---

## 实例：两个自旋 1/2 的耦合

令 $j_1 = 1/2$，$j_2 = 1/2$。可能的 $j$ 值为 1 和 0。
$$\frac{1}{2}\otimes  \frac{1}{2} = 0 \oplus  1 $$

#### 对于 $j=1, m=1$：
由选择定则，必须 $m_1=1/2, m_2=1/2$，因此
$$
|1, 1\rangle = |\uparrow\rangle |\uparrow\rangle \quad \Rightarrow \quad \langle \tfrac{1}{2}, \tfrac{1}{2}; \tfrac{1}{2}, \tfrac{1}{2} | 1, 1 \rangle = 1.
$$

#### 用降算符求其他态：
$J_- = J_{1-} + J_{2-}$ 作用在 $|1,1\rangle$：
左边：$J_- |1,1\rangle = \sqrt{2} \hbar |1,0\rangle$  
右边：$(J_{1-}|\uparrow\rangle)|\uparrow\rangle + |\uparrow\rangle(J_{2-}|\uparrow\rangle) = \hbar|\downarrow\rangle|\uparrow\rangle + \hbar|\uparrow\rangle|\downarrow\rangle$ 
所以：
$$
|1,0\rangle = \frac{1}{\sqrt{2}} (|\uparrow\downarrow\rangle + |\downarrow\uparrow\rangle).
$$
由此得到：
$$
\langle \tfrac{1}{2}, \tfrac{1}{2}; \tfrac{1}{2}, -\tfrac{1}{2} | 1, 0 \rangle = \frac{1}{\sqrt{2}}, \quad
\langle \tfrac{1}{2}, -\tfrac{1}{2}; \tfrac{1}{2}, \tfrac{1}{2} | 1, 0 \rangle = \frac{1}{\sqrt{2}}.
$$

再降一次得：
$$
|1, -1\rangle = |\downarrow\rangle|\downarrow\rangle.
$$

#### 对于 $j=0, m=0$：
它是与 $|1,0\rangle$ 正交的归一化态：
$$
|0,0\rangle = \frac{1}{\sqrt{2}} (|\uparrow\downarrow\rangle - |\downarrow\uparrow\rangle).
$$
CG 系数为：
$$
\langle \tfrac{1}{2}, \tfrac{1}{2}; \tfrac{1}{2}, -\tfrac{1}{2} | 0, 0 \rangle = \frac{1}{\sqrt{2}}, \quad
\langle \tfrac{1}{2}, -\tfrac{1}{2}; \tfrac{1}{2}, \tfrac{1}{2} | 0, 0 \rangle = -\frac{1}{\sqrt{2}}.
$$

|              | $\ket{\uparrow\uparrow}$ | $\ket{\uparrow\downarrow}$ | $\ket{\downarrow\uparrow}$ | $\ket{\downarrow\downarrow}$ |
| :----------: | :----------------------: | :------------------------: | :------------------------: | :--------------------------: |
| $\ket{1,1}$  |           $1$            |            $0$             |            $0$             |             $0$              |
| $\ket{1,0}$  |           $0$            |        $1/\sqrt{2}$        |        $1/\sqrt{2}$        |             $0$              |
| $\ket{1,-1}$ |           $0$            |            $0$             |            $0$             |             $1$              |
| $\ket{0,0}$  |           $0$            |        $1/\sqrt{2}$        |       $-1/\sqrt{2}$        |             $0$              |


---

## 实例：自旋-轨道耦合

令 $j_{1}=l,j_{2}=\frac{1}{2}$ 可能的 $j$ 的取值为 $l\pm \frac{1}{2}$

#### 对于 j=l+1/2 , m=j：
有选择定则，必有 $m_{1}=l,m_{2}=\frac{1}{2}$ 所以
$$\ket{l+\frac{1}{2},l+\frac{1}{2}} = \ket{l,l} \otimes \ket{\uparrow} \implies \braket{ l,l;\uparrow | l+\frac{1}{2},l+\frac{1}{2} } =1 $$ 
#### 用降算符得到其它态：
$$LHS:\quad J_{-}\ket{l+\frac{1}{2},l+\frac{1}{2}} = \sqrt{ 2l+1 } \ket{l+\frac{1}{2},l-\frac{1}{2}}  $$
$$RHS: (J_{l-}+J_{s-})\ket{l,l} \otimes \ket{\uparrow} =  \sqrt{ 2l }\ket{l,l-1} \otimes \ket{\uparrow} + \ket{l,l} \otimes \ket{\downarrow}  $$
于是
$$\ket{l+\frac{1}{2},l-\frac{1}{2}} = \sqrt{ \frac{2l}{2l+1} }\ket{l,l-1;\uparrow} + \frac{1}{\sqrt{ 2l+1 }}\ket{l,l;\downarrow} $$
递推可以得到
$$\boxed{\ket{j,m} = \sqrt{ \frac{j+m+ 1 /2}{2l+1} }\ket{l,m-\frac{1}{2}} \otimes \ket{\uparrow} + \sqrt{ \frac{l-m+1 /2}{2l+1} }\ket{l,m + \frac{1}{2}} \otimes  \ket{\downarrow}  }$$
其中 $j=l+\frac{1}{2}$

#### 对于 j=l-1/2：
而 $j=l-\frac{1}{2}$ 由正交归一性
$$\braket{ j=l-\frac{1}{2},m | j=l+\frac{1}{2},m } =0 $$
$$\ket{j=l+\frac{1}{2},m} =C\ket{l,m-\frac{1}{2}} \otimes \ket{\uparrow} +D\ket{l,m+\frac{1}{2}} \otimes \ket{\downarrow}   $$
则
$$AC + BD = 0 ,\quad C^{2} + D^{2} =1 $$
得到
$$\boxed{\ket{j,m} = -\sqrt{ \frac{l-m+ 1 /2}{2l+1} }\ket{l,m-\frac{1}{2}} \otimes \ket{\uparrow} + \sqrt{ \frac{j+m+1 /2}{2l+1} }\ket{l,m + \frac{1}{2}} \otimes  \ket{\downarrow}  }  $$

