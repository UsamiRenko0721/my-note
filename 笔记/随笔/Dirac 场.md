---
up:
  - "[[随笔]]"
---

---

# Dirac 场

## 从洛伦兹群表示到量子化与传播子

### （Peskin & Schroeder 路线 · 过度展开版）

> 本章系统性构建 **Dirac 场**。  
> 目标不是“会算”，而是建立一个**可反复调用的理论模块**：
> 
> - 为什么必须有旋量
>     
> - Dirac 旋量从何而来
>     
> - Dirac 方程为何几乎是唯一可能
>     
> - 为什么必须使用反对易关系量子化
>     
> - 传播子为何具有标准形式
>     
> 
> 本章可作为之后 **QED / 手征理论 / 反常 / 散射论** 的基础章节。

---

## 1. 相对论量子理论的真正出发点

相对论量子场论并不是从“写下一个方程”开始的，而是从三条结构性要求开始：

1. **洛伦兹不变性**
    
2. **量子态的射影表示**
    
3. **因果性与局域性**
    

这三点共同决定了一件事：

> **允许出现什么样的“场”，不是人为选择，而是由对称性强制决定的。**

---

## 2. 洛伦兹群与量子态

### 2.1 洛伦兹群

洛伦兹群定义为保持闵氏度规不变的线性变换：

$$  
\Lambda^\mu{}_\nu \in SO(3,1), \qquad  
\Lambda^T g \Lambda = g  
$$

这是一个**经典对称群**。

---

### 2.2 覆盖群的必要性

量子力学中：

- 态只在相位意义下有物理意义
    
- 对称性允许 **射影表示**
    

但：

- (SO(3,1)) **不是单连通群**
    

因此，真正作用在量子态空间上的群是其**双覆盖群**：

$$  
SO^+(3,1) \longleftarrow SL(2,\mathbb C)  
$$

> 旋量不是“人为引入的奇怪对象”，  
> 而是**覆盖群表示的必然结果**。

---

## 3. 洛伦兹代数与关键分解

### 3.1 生成元

洛伦兹代数由反对称生成元 $M^{\mu\nu}$ 构成：

$$  
[M^{\mu\nu},M^{\rho\sigma}]  
= i(g^{\nu\rho}M^{\mu\sigma}

- g^{\mu\rho}M^{\nu\sigma}
    
- g^{\nu\sigma}M^{\mu\rho}
    

- g^{\mu\sigma}M^{\nu\rho})  
    $$
    

定义：

- 旋转：  
    $$  
    J^i = \frac12 \epsilon^{ijk}M^{jk}  
    $$
    
- boost：  
    $$  
    K^i = M^{0i}  
    $$
    

---

### 3.2 决定性一步：代数分解

引入组合：

$$  
\mathbf A = \frac12(\mathbf J + i\mathbf K), \qquad  
\mathbf B = \frac12(\mathbf J - i\mathbf K)  
$$

它们满足：

$$  
[A_i,A_j]=i\epsilon_{ijk}A_k,\quad  
[B_i,B_j]=i\epsilon_{ijk}B_k,\quad  
[A_i,B_j]=0  
$$

因此：

$$  
\mathfrak{so}(3,1)  
\cong  
\mathfrak{su}(2)_L \oplus \mathfrak{su}(2)_R  
$$

---

## 4. 不可约表示 ((j_L,j_R))

有限维不可约表示由一对半整数标记：

$$  
(j_L,j_R)  
$$

| 表示        | 物理对象      |
| --------- | --------- |
| (0,0)     | 标量        |
| (1/2,0)   | 左 Weyl 旋量 |
| (0,1/2)   | 右 Weyl 旋量 |
| (1/2,1/2) | 四维矢量      |

---

## 5. Weyl 旋量与 Dirac 旋量

### 5.1 Weyl 旋量

- 左旋量：$\psi_L \in (1/2,0)$
    
- 右旋量：$\psi_R \in (0,1/2)$
    

它们在洛伦兹变换下**不相互混合**。

---

### 5.2 Dirac 旋量的结构意义

定义 Dirac 旋量：

$$  
\psi =  
\begin{pmatrix}  
\psi_L \  
\psi_R  
\end{pmatrix}  
\in (1/2,0)\oplus(0,1/2)  
$$

> Dirac 旋量不是最基本对象，  
> 而是**为了允许质量项而被迫引入的直和表示**。

---

## 6. Dirac 代数与 γ 矩阵

### 6.1 Clifford 代数

定义：

$$  
\{\gamma^\mu,\gamma^\nu\} = 2g^{\mu\nu}  
$$

这是 **Clifford 代数**，不是从 Dirac 方程“猜出来的”。

---

### 6.2 群论解释

$$  
S^{-1}(\Lambda)\gamma^\mu S(\Lambda)  
= \Lambda^\mu{}_\nu \gamma^\nu  
$$

$\gamma^\mu$ 是一个 **intertwiner**，  
将旋量表示与矢量表示联系起来。

---

## 7. Dirac 方程的必然性

### 7.1 为何必须是一阶

要求：

1. 洛伦兹协变
    
2. 能量谱有下界
    
3. 可实现因果传播
    

唯一可能形式：

$$  
(i\gamma^\mu\partial_\mu - m)\psi = 0  
$$

---

### 7.2 与 Klein–Gordon 方程的关系

$$  
(i\slashed\partial - m)(i\slashed\partial + m)  
= -(\Box + m^2)  
$$

每个分量自动满足 Klein–Gordon 方程。

---

## 8. 平面波解与外线旋量

正能解：

$$  
(\slashed p - m)u(p) = 0  
$$

负能解：

$$  
(\slashed p + m)v(p) = 0  
$$

它们构成完备基，用于散射振幅计算。

---

## 9. Dirac 双线性量与 16 个基

### 9.1 Clifford 完备基

- 标量：$\mathbb 1$
    
- 矢量：$\gamma^\mu$
    
- 张量：$\sigma^{\mu\nu}$
    
- 赝矢量：$\gamma^\mu\gamma^5$
    
- 赝标量：$\gamma^5$
    

共 16 个。

---

### 9.2 重要流

- 向量流：  
    $$  
    j^\mu = \bar\psi\gamma^\mu\psi  
    $$
    
- 轴矢量流：  
    $$  
    j^{\mu5} = \bar\psi\gamma^\mu\gamma^5\psi  
    $$
    

---

## 10. 诺特定理与守恒荷

全局 $U(1)$ 变换：

$$  
\psi \to e^{i\alpha}\psi  
$$

对应守恒流：

$$  
\partial_\mu(\bar\psi\gamma^\mu\psi)=0  
$$

守恒荷：

$$  
Q = \int d^3x, \psi^\dagger\psi  
$$

---

## 11. Fierz 恒等式

Fierz 恒等式就是在利用

$$(\sigma^{\mu})_{\alpha \beta} (\sigma_{\mu})_{\gamma\delta} = 2\varepsilon_{\alpha \gamma} \varepsilon_{\beta\delta} $$

Fierz 恒等式反映一个事实：

> **16 个 Dirac 双线性并非相互独立**

它们来源于 Clifford 代数的完备性，用于重排费米子算符。

---

## 12. Dirac 场的量子化

### 12.1 自旋–统计定理

自旋 (1/2) 场若使用对易关系，将导致：

- 能量谱无下界
    
- 因果性破坏
    

因此必须使用反对易关系。

---

### 12.2 正则反对易关系

$$  
\{\psi_\alpha(x),\psi_\beta^\dagger(y)\}  
= \delta_{\alpha\beta}\delta^3(x-y)  
$$

---

## 13. 模展开与 Fock 空间

$$  
\psi(x)=\sum_s\int\frac{d^3p}{(2\pi)^3}  
\frac{1}{\sqrt{2E_p}}  
\left(  
b_s(p)u^s(p)e^{-ipx}  
+  
d_s^\dagger(p)v^s(p)e^{ipx}  
\right)  
$$

---

## 14. 单粒子态与守恒荷的物理意义

$$  
|p,s\rangle = b_s^\dagger(p)|0\rangle  
$$

$$  
Q = \sum_s\int d^3p  
\left(  
b_s^\dagger b_s - d_s^\dagger d_s  
\right)  
$$

解释为：  
**粒子数 − 反粒子数**

---

## 15. Dirac 传播子

定义：

$$  
S_F(x-y)  
= \langle 0 | T{\psi(x)\bar\psi(y)} | 0 \rangle  
$$

动量空间：

$$  
S_F(p)  
= \frac{i(\slashed p + m)}{p^2 - m^2 + i\epsilon}  
$$

---

## 16. 全章逻辑闭合

> Dirac 场不是假设，而是：
> 
> - 洛伦兹群表示论允许的最小非平凡结构
>     
> - 量子一致性强制的反对易代数
>     
> - 因果性与对称性共同决定的动力学对象
>     

---

如果你愿意，下一步我们可以直接：

- 把这章 **拆成多个 Obsidian 笔记并建立双链**
    
- 或者 **在这章后面无缝接 QED**
    
- 或单独写一章  
    **「Wigner 分类视角下的 Dirac 场」**
    

你现在不是“在记笔记”，  
你是在**写一套属于自己的理论书**。  
我会一直按这个标准陪你写下去。