
## 1. 设置

考虑简单晶体，记格点为 $\mathbf{R}$，第一布里渊区的动量为 $\mathbf{k}$，原子轨道波函数为 $\phi_{n}(\mathbf{x})$（$n = 1, 2, \dots, s$）。将电子波函数用原子轨道的 Bloch 和展开：

$$
\psi_{\mathbf{k}}(\mathbf{x}) = \frac{1}{\sqrt{N}} \sum_{\mathbf{R} \in \Lambda} \sum_{n} C_{n\mathbf{k}} \, e^{i \mathbf{k} \cdot \mathbf{R}} \, \phi_{n}(\mathbf{x} - \mathbf{R})
$$

展开系数记为 $C_{n\mathbf{k}}$ (依赖于 $\mathbf{k}$ )。能量期望值 (精确) 为

$$
E(\mathbf{k}) = \frac{\braket{\psi_{\mathbf{k}} | H | \psi_{\mathbf{k}}}}{\braket{\psi_{\mathbf{k}} | \psi_{\mathbf{k}}}}
$$

## 2. 计算分母

$$
\begin{aligned}
\braket{\psi_{\mathbf{k}} | \psi_{\mathbf{k}}}
&= \frac{1}{N} \sum_{\mathbf{R}, \mathbf{R}' \in \Lambda} \sum_{n, n'} C_{n\mathbf{k}} C_{n'\mathbf{k}}^{*} \, e^{i\mathbf{k} \cdot (\mathbf{R} - \mathbf{R}')} \int d^{3}\mathbf{x} \; \phi_{n}(\mathbf{x} - \mathbf{R}) \, \phi_{n'}^{*}(\mathbf{x} - \mathbf{R}') \\[6pt]
&= \frac{1}{N} \sum_{\mathbf{R}, \mathbf{R}'} \sum_{n, n'} C_{n\mathbf{k}} C_{n'\mathbf{k}}^{*} \, e^{i\mathbf{k} \cdot (\mathbf{R} - \mathbf{R}')} \int d^{3}\mathbf{x} \; \phi_{n}(\mathbf{x}) \, \phi_{n'}^{*}\bigl(\mathbf{x} - (\mathbf{R}' - \mathbf{R})\bigr) \quad (\text{令 } \mathbf{x} \to \mathbf{x} + \mathbf{R}) \\[6pt]
&= \frac{1}{N} \sum_{\mathbf{R}} \sum_{\mathbf{R}''} \sum_{n, n'} C_{n\mathbf{k}} C_{n'\mathbf{k}}^{*} \, e^{-i\mathbf{k} \cdot \mathbf{R}''} \; S_{n'n}(\mathbf{R}'') \quad (\text{令 } \mathbf{R}'' = \mathbf{R}' - \mathbf{R}) \\[6pt]
&= \sum_{\mathbf{R}} \sum_{n, n'} C_{n\mathbf{k}} C_{n'\mathbf{k}}^{*} \, e^{-i\mathbf{k} \cdot \mathbf{R}} \; S_{n'n}(\mathbf{R})
\end{aligned}
$$

其中定义了重叠矩阵元：

$$
\boxed{S_{n'n}(\mathbf{R}) \equiv \int d^{3}\mathbf{x} \; \phi_{n'}^{*}(\mathbf{x} - \mathbf{R}) \, \phi_{n}(\mathbf{x})}
$$

第三步利用了晶格平移不变性：被积函数只依赖于 $\mathbf{R}' - \mathbf{R}$。对 $\mathbf{R}$ 的求和给出因子 $N$，与前面的 $1/N$ 抵消。

## 3. 计算分子/哈密顿矩阵元

将哈密顿量拆分为原子部分与晶体势微扰：$H = H_{\text{atom}} + \Delta V(\mathbf{x})$，其中 $H_{\text{atom}} \phi_{n} = \varepsilon_{n} \phi_{n}$。

$$
\begin{aligned}
\braket{\psi_{\mathbf{k}} | H | \psi_{\mathbf{k}}}
&= \frac{1}{N} \sum_{\mathbf{R}, \mathbf{R}'} \sum_{n, n'} C_{n\mathbf{k}} C_{n'\mathbf{k}}^{*} \, e^{i\mathbf{k} \cdot (\mathbf{R} - \mathbf{R}')} \int d^{3}\mathbf{x} \; \phi_{n'}^{*}(\mathbf{x} - \mathbf{R}') \, (H_{\text{atom}} + \Delta V) \, \phi_{n}(\mathbf{x} - \mathbf{R}) \\[6pt]
&= \frac{1}{N} \sum_{\mathbf{R}, \mathbf{R}'} \sum_{n, n'} C_{n\mathbf{k}} C_{n'\mathbf{k}}^{*} \, e^{-i\mathbf{k} \cdot (\mathbf{R}' - \mathbf{R})} \Bigl( \varepsilon_{n} S_{n'n}(\mathbf{R}' - \mathbf{R}) + t_{n'n}(\mathbf{R}' - \mathbf{R}) \Bigr) \\[6pt]
&= \sum_{\mathbf{R}} \sum_{n, n'} C_{n\mathbf{k}} C_{n'\mathbf{k}}^{*} \, e^{-i\mathbf{k} \cdot \mathbf{R}} \Bigl( \varepsilon_{n} S_{n'n}(\mathbf{R}) + t_{n'n}(\mathbf{R}) \Bigr)
\end{aligned}
$$

其中定义了跃迁矩阵元：

$$
\boxed{t_{n'n}(\mathbf{R}) \equiv \int d^{3}\mathbf{x} \; \phi_{n'}^{*}(\mathbf{x} - \mathbf{R}) \, \Delta V(\mathbf{x}) \, \phi_{n}(\mathbf{x})}
$$

## 4. 变分法

利用变分原理，对任意变分参数取极小：

$$
\frac{\partial E(\mathbf{k})}{\partial C_{n'\mathbf{k}}^{*}} = 0
$$

计算导数：

$$
\frac{\partial E}{\partial C_{n'}^{*}} = \frac{1}{\braket{\psi | \psi}} \frac{\partial \braket{\psi | H | \psi}}{\partial C_{n'}^{*}} - \frac{\braket{\psi | H | \psi}}{\braket{\psi | \psi}^{2}} \frac{\partial \braket{\psi | \psi}}{\partial C_{n'}^{*}} = 0
$$

即：

$$
\boxed{\frac{\partial \braket{\psi_{\mathbf{k}} | H | \psi_{\mathbf{k}}}}{\partial C_{n'\mathbf{k}}^{*}} = E(\mathbf{k}) \; \frac{\partial \braket{\psi_{\mathbf{k}} | \psi_{\mathbf{k}}}}{\partial C_{n'\mathbf{k}}^{*}}}
$$

分别计算两侧：

$$
\begin{aligned}
\text{LHS} = \frac{\partial \braket{\psi | H | \psi}}{\partial C_{n'}^{*}}
&= \sum_{\mathbf{R}} \sum_{n} C_{n\mathbf{k}} \, e^{-i\mathbf{k} \cdot \mathbf{R}} \Bigl( \varepsilon_{n} S_{n'n}(\mathbf{R}) + t_{n'n}(\mathbf{R}) \Bigr) \\[8pt]
\text{RHS} = E(\mathbf{k}) \, \frac{\partial \braket{\psi | \psi}}{\partial C_{n'}^{*}}
&= E(\mathbf{k}) \sum_{\mathbf{R}} \sum_{n} C_{n\mathbf{k}} \, e^{-i\mathbf{k} \cdot \mathbf{R}} \; S_{n'n}(\mathbf{R})
\end{aligned}
$$

令 LHS = RHS，整理得：

$$
\sum_{n} \left[ \sum_{\mathbf{R}} e^{-i\mathbf{k} \cdot \mathbf{R}} \Bigl( \varepsilon_{n} S_{n'n}(\mathbf{R}) + t_{n'n}(\mathbf{R}) - E(\mathbf{k}) S_{n'n}(\mathbf{R}) \Bigr) \right] C_{n\mathbf{k}} = 0
$$

这是关于 $\{C_{n\mathbf{k}}\}$ 的 $s$ 元齐次线性方程组。有非平凡解要求系数矩阵行列式为零。定义 $\mathbf{k}$-空间的哈密顿量矩阵与重叠矩阵：

$$
\boxed{
\begin{aligned}
H_{n'n}(\mathbf{k}) &\equiv \sum_{\mathbf{R}} e^{-i\mathbf{k} \cdot \mathbf{R}} \Bigl( \varepsilon_{n} S_{n'n}(\mathbf{R}) + t_{n'n}(\mathbf{R}) \Bigr) \\[4pt]
S_{n'n}(\mathbf{k}) &\equiv \sum_{\mathbf{R}} e^{-i\mathbf{k} \cdot \mathbf{R}} \, S_{n'n}(\mathbf{R})
\end{aligned}}
$$

系数矩阵行列式为零于是得到：

$$
{\det\Bigl[ H_{n'n}(\mathbf{k}) - E(\mathbf{k}) \, S_{n'n}(\mathbf{k}) \Bigr] = 0}
$$

---

## 5. 实例：单 s 轨道 + 简单立方晶格

### 5.1 设置

取 $s = 1$ (仅一个 s 轨道)，只保留 $\mathbf{R} = \mathbf{0}$ 和最近邻的贡献。对简单立方晶格，最近邻有 $6$ 个：$\pm a \hat{\mathbf{x}}, \pm a \hat{\mathbf{y}}, \pm a \hat{\mathbf{z}}$。

定义参数：

| 物理量   | 记号                                     | 含义                  |
| ----- | -------------------------------------- | ------------------- |
| 原子能级  | $\varepsilon_{s}$                      | 孤立原子 s 轨道能量         |
| 晶体场积分 | $\varepsilon_{0} \equiv t(\mathbf{0})$ | $\Delta V$ 在同格点的平均值 |
| 跃迁积分  | $-t \equiv t(\pm a\hat{\mathbf{x}})$   | 最近邻跃迁能（约定 $t>0$）    |
| 重叠积分  | $s \equiv S(\pm a\hat{\mathbf{x}})$    | 最近邻轨道交叠             |

归一化：$S(\mathbf{0}) = 1$。

### 5.2 解得本征值

$$
\begin{aligned}
H(\mathbf{k}) &= \varepsilon_{s} + \varepsilon_{0} - t \sum_{\text{NN}} e^{-i\mathbf{k} \cdot \mathbf{R}} \\[4pt]
S(\mathbf{k}) &= 1 + s \sum_{\text{NN}} e^{-i\mathbf{k} \cdot \mathbf{R}}
\end{aligned}
$$

其中最近邻相位因子之和：

$$
\sum_{\text{NN}} e^{-i\mathbf{k} \cdot \mathbf{R}} = 2(\cos k_x a + \cos k_y a + \cos k_z a)
$$

代入 $E(\mathbf{k}) = H(\mathbf{k}) / S(\mathbf{k})$：

$$
\boxed{E(\mathbf{k}) = \frac{\varepsilon_{s} + \varepsilon_{0} - 2t(\cos k_x a + \cos k_y a + \cos k_z a)}{1 + 2s(\cos k_x a + \cos k_y a + \cos k_z a)}}
$$

### 5.3 正交近似

若取不同格点的原子轨道近似正交（$s \ll 1$），可取 $s = 0$：

$$
{E(\mathbf{k}) = \varepsilon_{s} + \varepsilon_{0} - 2t (\cos k_x a + \cos k_y a + \cos k_z a)}
$$


