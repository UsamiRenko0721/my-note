---
up:
  - "[[写题]]"
related:
date: 2026-04-09
---

Consider a one-dimensional Ising model with $N$ spins $\sigma_i = \pm 1$, $i = 1, 2, \dots, N$, and periodic boundary conditions $\sigma_{N+1} = \sigma_1$. The Hamiltonian is

$$
H = -J \sum_{i=1}^N \sigma_i \sigma_{i+1} - h \sum_{i=1}^N \sigma_i,
$$

where $J > 0$ is the ferromagnetic coupling and $h$ is an external magnetic field.

---

### (a) Transfer Matrix and Free Energy

Construct the $2 \times 2$ transfer matrix $T$ whose elements are
$$
T_{\sigma, \sigma'} = \exp\!\left[ \beta J \sigma \sigma' + \frac{1}{2} \beta h (\sigma + \sigma') \right].
$$
Show that the partition function is $Z = \operatorname{Tr}(T^N)$, and compute the free energy per spin $f$ in the thermodynamic limit $N \to \infty$.

---

### (b) Magnetization

Using the result of part (a), find the magnetization per spin $m = \langle \sigma_i \rangle$ as a function of $\beta$, $J$, and $h$.

---

### (c) Spin–Spin Correlation Function

Define the two-point correlation function $G(r) = \langle \sigma_i \sigma_{i+r} \rangle - \langle \sigma_i \rangle \langle \sigma_{i+r} \rangle$. Derive an expression for $G(r)$ in terms of the eigenvalues and eigenvectors of the transfer matrix, and show that for large $r$ it decays exponentially as
$$
G(r) \sim e^{-r/\xi},
$$
where $\xi$ is the correlation length. Determine $\xi$ as a function of $\beta$, $J$, and $h$.

---

### (d) Zero-Field Limit and Critical Behavior

Evaluate the correlation length $\xi$ for $h = 0$. How does $\xi$ behave as $T \to 0$? Does the one-dimensional Ising model exhibit a finite-temperature phase transition? Briefly explain the physical reason for your conclusion.

---

## Solution
### (a) Transfer Matrix and Free Energy

The transfer matrix $T$ is defined by its elements between adjacent spin states:
$$
T_{\sigma, \sigma'} = \exp\!\left[ \beta J \sigma \sigma' + \frac{1}{2} \beta h (\sigma + \sigma') \right], \qquad \sigma, \sigma' = \pm 1.
$$
Explicitly,
$$
\begin{aligned}
T_{+,+} &= e^{\beta J + \beta h}, \\
T_{+,-} &= e^{-\beta J}, \\
T_{-,+} &= e^{-\beta J}, \\
T_{-,-} &= e^{\beta J - \beta h}.
\end{aligned}
$$
Thus
$$
T = \begin{pmatrix}
e^{\beta J + \beta h} & e^{-\beta J} \\
e^{-\beta J} & e^{\beta J - \beta h}
\end{pmatrix}.
$$
The partition function for $N$ spins with periodic boundary conditions is
$$
Z = \sum_{\{\sigma_i\}} \prod_{i=1}^N T_{\sigma_i, \sigma_{i+1}} = \operatorname{Tr}(T^N).
$$
Let $\lambda_+$ and $\lambda_-$ be the eigenvalues of $T$, with $\lambda_+ > \lambda_-$. Then $Z = \lambda_+^N + \lambda_-^N$. In the thermodynamic limit $N \to \infty$,
$$
\lim_{N \to \infty} \frac{1}{N} \ln Z = \ln \lambda_+.
$$
The free energy per spin is $f = -\frac{1}{\beta} \ln \lambda_+$.

Diagonalizing $T$:
$$
\lambda_{\pm} = e^{\beta J} \cosh(\beta h) \pm \sqrt{ e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J} }.
$$
Thus
$$
f = -\frac{1}{\beta} \ln\!\left[ e^{\beta J} \cosh(\beta h) + \sqrt{ e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J} } \right].
$$

---

### (b) Magnetization

The magnetization per spin is $m = -\frac{\partial f}{\partial h}$. Differentiating $\lambda_+$ gives
$$
m = \frac{ e^{\beta J} \sinh(\beta h) + \frac{ e^{2\beta J} \sinh(\beta h) \cosh(\beta h) }{ \sqrt{ e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J} } } }{ e^{\beta J} \cosh(\beta h) + \sqrt{ e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J} } }.
$$
Simplifying, one finds the well-known result:
$$
m = \frac{ \sinh(\beta h) }{ \sqrt{ \sinh^2(\beta h) + e^{-4\beta J} } }.
$$

---

### (c) Correlation Function

The correlation function for $r > 0$ can be expressed using the transfer matrix. In the basis where $T$ is diagonal, the two-point function is
$$
\langle \sigma_i \sigma_{i+r} \rangle = \frac{ \operatorname{Tr}( \sigma^z T^r \sigma^z T^{N-r} ) }{ \operatorname{Tr}(T^N) },
$$
where $\sigma^z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$ is the Pauli $z$ matrix. In the thermodynamic limit $N \to \infty$, the dominant contribution comes from the largest eigenvalue $\lambda_+$ and the corresponding eigenvector $|+\rangle$. Let $|-\rangle$ be the eigenvector for $\lambda_-$.

Then
$$
\langle \sigma_i \sigma_{i+r} \rangle \approx \sum_{s = \pm} |\langle + | \sigma^z | s \rangle|^2 \left( \frac{\lambda_s}{\lambda_+} \right)^r.
$$
Since $\langle \sigma_i \rangle = \langle + | \sigma^z | + \rangle$, the connected correlation function is
$$
G(r) = |\langle + | \sigma^z | - \rangle|^2 \left( \frac{\lambda_-}{\lambda_+} \right)^r.
$$
Thus $G(r) \sim e^{-r/\xi}$ with the correlation length
$$
\xi = \frac{1}{\ln(\lambda_+ / \lambda_-)}.
$$
Explicitly,

$$
\frac{\lambda_-}{\lambda_+} = \frac{ e^{\beta J} \cosh(\beta h) - \sqrt{ e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J} } }{ e^{\beta J} \cosh(\beta h) + \sqrt{ e^{2\beta J} \sinh^2(\beta h) + e^{-2\beta J} } }.
$$

---

### (d) Zero-Field Limit and Critical Behavior

For $h = 0$, the eigenvalues simplify to
$$
\lambda_+ = e^{\beta J} + e^{-\beta J} = 2 \cosh(\beta J), \qquad \lambda_- = e^{\beta J} - e^{-\beta J} = 2 \sinh(\beta J).
$$
Thus
$$
\xi = \frac{1}{\ln(\coth(\beta J))}.
$$
As $T \to 0$ ($\beta \to \infty$), $\coth(\beta J) \to 1$, so $\xi \to \infty$, indicating a diverging correlation length. However, at any finite $T > 0$, $\xi$ is finite. Consequently, **there is no finite-temperature phase transition** in the one-dimensional Ising model. The physical reason is that the energy cost of creating a domain wall is constant ($2J$), while the entropy gain is proportional to $\ln N$, making the disordered phase favorable at any $T > 0$. This is a classic example of the Peierls argument in one dimension.

---

### Summary

This problem illustrates the power of the transfer matrix method for one-dimensional classical spin models. The exact solution reveals the absence of a finite-$T$ transition, the exponential decay of correlations, and explicit thermodynamic functions, all of which serve as a benchmark for understanding more complex systems and approximations like mean-field theory.