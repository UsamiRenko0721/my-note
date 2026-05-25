---
up:
  - "[[写题]]"
related:
  - "[[Yau 理论力学]]"
  - "[[Yau 电动力学]]"
  - "[[Yau 统计力学]]"
  - "[[Yau 量子力学]]"
  - "[[Yau 广义相对论]]"
  - "[[Yau 量子场论]]"
date: 2026-05-06
---

# Preface

This manuscript is a lecture-style solution guide to the Mathematical Physics individual problems from the S.-T. Yau College Student Mathematics Contests, covering the years 2022-2025. It is written as a set of mathematical physics notes rather than as a list of short answers. Each problem is stated explicitly, followed by a detailed solution and a short paragraph labelled Higher viewpoint. explaining the structural idea behind the computation. 

The recommended way to use the manuscript is to attempt each problem first, then compare the calculation with the written solution. The emphasis is on reusable mechanisms: symmetry and Noether conservation laws, perturbation theory, ladder operators, Maxwell potentials, effective potentials, black-hole and de Sitter metrics, conformal transformations, large- $N$ counting, and one-loop renormalization. 

# Chapter 1 -2022 Mathematical Physics

## 1.1 Problem 1: Time reversal and anti-unitarity

Problem statement. A symmetry transformation in quantum mechanics is represented by a unitary or anti-unitary operator on a Hilbert space. The time-reversal transformation $\Theta$ relates the wave function at time $t$ to the wave function at time $-t$ . 

(a) Prove that $\Theta$ is anti-unitary. 

(b) Let $|\psi \rangle$ be a state, let $\psi(x) = \langle x|\psi\rangle$ , and assume $\Theta|x\rangle = |x\rangle$ . Prove that the position-space wave function of $\Theta|\psi\rangle$ is $\psi(x)^*$ . 

(c) If the one-dimensional Hamiltonian satisfies $\Theta H = H\Theta$ and an energy eigenstate has no degeneracy, prove that the position-space energy eigenfunction may be chosen real. 

Solution. For a time-independent Hamiltonian, the time-evolution operator is 

$$
U (t) = \mathrm {e} ^ {- \mathrm {i} H t / \hbar}.
$$

Time reversal should transform forward evolution into backward evolution: 

$$
\Theta U (t) \Theta^ {- 1} = U (- t) = \mathrm {e} ^ {\mathrm {i} H t / \hbar}.
$$

If $\Theta$ were unitary and commuted with a time-reversal-invariant Hamiltonian, then it would leave the scalar $i$ fixed and would give 

$$
\Theta \mathrm {e} ^ {- \mathrm {i} H t / \hbar} \Theta^ {- 1} = \mathrm {e} ^ {- \mathrm {i} H t / \hbar},
$$

not $U(-t)$ . The operation must therefore conjugate complex scalars, in particular $\Theta \mathrm{i}\Theta^{-1} = -\mathrm{i}$ . By Wigner's theorem, a symmetry preserving transition probabilities is either unitary or anti-unitary. The preceding sign reversal of $\mathrm{i}$ forces the anti-unitary case. 

Now assume $\Theta |x\rangle = |x\rangle$ . Since $\Theta$ is anti-linear, for any state 

$$
| \psi \rangle = \int \psi (x) | x \rangle \mathrm {d} x
$$

one has 

$$
\Theta | \psi \rangle = \int \psi (x) ^ {*} \Theta | x \rangle \mathrm {d} x = \int \psi (x) ^ {*} | x \rangle \mathrm {d} x.
$$

Thus the position-space wave function of $\Theta |\psi \rangle$ is 

$$
\langle x | \Theta \psi \rangle = \psi (x) ^ {*}.
$$

Finally, suppose $H|\psi \rangle = E|\psi \rangle$ and the eigenspace for $E$ is one-dimensional. Since $H\Theta = \Theta H$ , we get 

$$
H (\Theta | \psi \rangle) = \Theta H | \psi \rangle = E \Theta | \psi \rangle .
$$

Therefore $\Theta |\psi \rangle$ lies in the same one-dimensional eigenspace, so 

$$
\Theta | \psi \rangle = c | \psi \rangle , \qquad | c | = 1.
$$

Multiplying $|\psi \rangle$ by a phase $\mathrm{e}^{\mathrm{i}\alpha}$ changes $c$ to $\mathrm{e}^{-2\mathrm{i}\alpha}c$ . Choose $\alpha$ so that the new constant is 1. Then $\Theta |\psi \rangle = |\psi \rangle$ , and in position space 

$$
\psi (x) ^ {*} = \psi (x).
$$

Thus the eigenfunction may be chosen real. 

Equivalent inner-product argument. The anti-unitarity can also be detected without referring first to the exponential of the Hamiltonian. Let the Schrodinger equation be 

$$
\mathrm {i} \hbar \partial_ {t} | \psi (t) \rangle = H | \psi (t) \rangle .
$$

If time reversal maps a solution to another solution by $|\psi(t)\rangle \mapsto \Theta |\psi(-t)\rangle$ , then 

$$
\mathrm {i} \hbar \partial_ {t} \Theta | \psi (- t) \rangle = - \mathrm {i} \hbar \Theta \partial_ {t} | \psi (- t) \rangle
$$

only if $\Theta$ conjugates the scalar i. Otherwise the sign change from $t\mapsto -t$ cannot be compensated. Anti-linearity is precisely the rule 

$$
\Theta \left(c _ {1} | \psi_ {1} \rangle + c _ {2} | \psi_ {2} \rangle\right) = c _ {1} ^ {*} \Theta | \psi_ {1} \rangle + c _ {2} ^ {*} \Theta | \psi_ {2} \rangle .
$$

Together with preservation of transition probabilities, 

$$
| \langle \phi | \psi \rangle | ^ {2} = | \langle \Theta \phi | \Theta \psi \rangle | ^ {2},
$$

this is the anti-unitary alternative in Wigner's theorem. Thus the position-space complex conjugation in part (b) is not an extra assumption; it is the coordinate realization of the same anti-linear structure. 

**Higher viewpoint.** Time reversal is the prototype of an anti-unitary symmetry. Ordinary spatial symmetries act by reshuffling basis vectors while leaving complex scalars untouched; time reversal must also reverse the sign of the quantum phase generator $\mathrm{i}\partial_{t}$ . In a real one-dimensional nondegenerate bound-state problem this anti-linearity explains why the eigenfunction can be chosen real. The statement is special to the absence of degeneracy: when a time-reversed partner belongs to a distinct state, the symmetry may instead organize states into pairs, as in Kramers degeneracy. 

## 1.2 Problem 2: Two harmonic oscillators and the Schwinger representation

Problem statement. Consider two decoupled harmonic oscillators 

$$
H _ {0} = \frac {p _ {1} ^ {2}}{2 m} + \frac {1}{2} m \omega^ {2} x _ {1} ^ {2} + \frac {p _ {2} ^ {2}}{2 m} + \frac {1}{2} m \omega^ {2} x _ {2} ^ {2}.
$$

(a) Compute the eigenstates and eigenvalues. 

(b) With creation and annihilation operators $a_i^\dagger, a_i$ , define 

$$
J _ {+} = a _ {1} ^ {\dagger} a _ {2}, \qquad J _ {-} = a _ {2} ^ {\dagger} a _ {1}, \qquad J _ {z} = \frac {1}{2} (a _ {1} ^ {\dagger} a _ {1} - a _ {2} ^ {\dagger} a _ {2}).
$$

Prove $[J_z, J_{\pm}] = \pm J_{\pm}$ and $[J_+, J_-] = 2J_z$ . For the energy level $n_1 + n_2 = n$ , prove that the eigenspace is an irreducible $\mathfrak{su}(2)$ -representation and compute the spin. 

(c) For $H = H_0 + \lambda x_1^2 p_2^2$ , compute the first-order correction to the energy level $n_1 + n_2 = 2$ . 

Solution. The two oscillators have basis 

$$
\left| n _ {1}, n _ {2} \right\rangle = \frac {\left(a _ {1} ^ {\dagger}\right) ^ {n _ {1}} \left(a _ {2} ^ {\dagger}\right) ^ {n _ {2}}}{\sqrt {n _ {1} ! n _ {2} !}} \left| 0, 0 \right\rangle ,
$$

and 

$$
H _ {0} | n _ {1}, n _ {2} \rangle = \hbar \omega (n _ {1} + n _ {2} + 1) | n _ {1}, n _ {2} \rangle .
$$

Thus the level $n_1 + n_2 = n$ has energy 

$$
E _ {n} = \hbar \omega (n + 1)
$$

and degeneracy $n + 1$ 

Using $[a_i, a_j^\dagger] = \delta_{ij}$ and the number operators $N_i = a_i^\dagger a_i$ , one has 

$$
\left[ N _ {1}, J _ {+} \right] = J _ {+}, \qquad \left[ N _ {2}, J _ {+} \right] = - J _ {+},
$$

so $[J_z, J_+] = J_+$ . Similarly $[J_z, J_-] = -J_-$ . Moreover 

$$
[ J _ {+}, J _ {-} ] = a _ {1} ^ {\dagger} a _ {2} a _ {2} ^ {\dagger} a _ {1} - a _ {2} ^ {\dagger} a _ {1} a _ {1} ^ {\dagger} a _ {2} = N _ {1} (N _ {2} + 1) - N _ {2} (N _ {1} + 1) = N _ {1} - N _ {2} = 2 J _ {z}.
$$

On the subspace $n_1 + n_2 = n$ , the weights of $J_{z}$ are 

$$
m _ {z} = \frac {1}{2} (n _ {1} - n _ {2}) = - \frac {n}{2}, - \frac {n}{2} + 1, \dots , \frac {n}{2}.
$$

The operators $J_{+}$ and $J_{-}$ move between adjacent weights and connect the whole space. Hence the representation is the irreducible spin 

$$
j = \frac {n}{2}
$$

representation of dimension $2j + 1 = n + 1$ . 

For the perturbation, use 

$$
x = \sqrt {\frac {\hbar}{2 m \omega}} (a + a ^ {\dagger}), \qquad p = \mathrm {i} \sqrt {\frac {m \hbar \omega}{2}} (a ^ {\dagger} - a).
$$

Inside the degenerate subspace with basis 

$$
| 2,   0 \rangle , \quad | 1,   1 \rangle , \quad | 0,   2 \rangle ,
$$

the matrix of $x_{1}^{2}p_{2}^{2}$ is 

$$
\frac {\hbar^ {2}}{4} \left( \begin{array}{c c c} 5 & 0 & - 2 \\ 0 & 9 & 0 \\ - 2 & 0 & 5 \end{array} \right).
$$

Indeed, $x^{2}$ and $p^2$ only change oscillator occupation number by 0 or $\pm 2$ . The eigenvalues of this matrix are 

$$
\frac {\hbar^ {2}}{4} \cdot 3, \qquad \frac {\hbar^ {2}}{4} \cdot 7, \qquad \frac {\hbar^ {2}}{4} \cdot 9.
$$

Therefore the first-order shifts of the $n_1 + n_2 = 2$ level are 

$$
\Delta E ^ {(1)} = \lambda \frac {\hbar^ {2}}{4} \{3, 7, 9 \}.
$$

Matrix diagonalization of the perturbation. For completeness we record the actual degenerate perturbation step. The useful one-dimensional matrix elements are 

$$
\langle n | x ^ {2} | n \rangle = \frac {\hbar}{2 m \omega} (2 n + 1), \qquad \langle n + 2 | x ^ {2} | n \rangle = \frac {\hbar}{2 m \omega} \sqrt {(n + 1) (n + 2)},
$$

while 

$$
\langle n | p ^ {2} | n \rangle = \frac {m \hbar \omega}{2} (2 n + 1), \qquad \langle n + 2 | p ^ {2} | n \rangle = - \frac {m \hbar \omega}{2} \sqrt {(n + 1) (n + 2)}.
$$

Tensoring the two oscillator factors gives the displayed $3 \times 3$ matrix. The vector $(1,0,1)$ has eigenvalue $3\hbar^2 /4$ , the vector $(1,0,-1)$ has eigenvalue $7\hbar^2 /4$ , and $(0,1,0)$ has eigenvalue $9\hbar^2 /4$ . This also identifies which linear combinations of the original degenerate states are selected at first order. 

**Higher viewpoint.** The Schwinger representation converts a two-oscillator degeneracy problem into angular-momentum representation theory. The perturbation then asks for an operator to be diagonalized inside a fixed irreducible $\mathfrak{su}(2)$ -module. This is the standard strategy behind many oscillator degeneracy problems: first identify the hidden symmetry algebra, then diagonalize the perturbation on the finite-dimensional symmetry multiplet rather than in the full Hilbert space. 

## 1.3 Problem 3: Killing fields and conserved momenta

Problem statement. A Killing vector field $k^{\mu}\partial_{\mu}$ satisfies 

$$
k ^ {\lambda} \partial_ {\lambda} g _ {\mu \nu} + \partial_ {\mu} k ^ {\lambda} g _ {\lambda \nu} + \partial_ {\nu} k ^ {\lambda} g _ {\lambda \mu} = 0.
$$

(a) Prove $D_{\mu}k_{\nu} + D_{\nu}k_{\mu} = 0$ 

(b) For a free-falling particle with momentum $P_{\mu} = mg_{\mu \nu}\mathrm{d}x^{\nu} / \mathrm{d}\tau$ , prove that $k^{\mu}P_{\mu}$ is conserved. Solution. Since $k_{\nu} = g_{\nu \lambda}k^{\lambda}$ , metric compatibility gives 

$$
D _ {\mu} k _ {\nu} + D _ {\nu} k _ {\mu} = \partial_ {\mu} k _ {\nu} + \partial_ {\nu} k _ {\mu} - 2 \Gamma_ {\mu \nu} ^ {\lambda} k _ {\lambda}.
$$

Expanding $k_{\nu} = g_{\nu \lambda}k^{\lambda}$ and inserting the Christoffel formula, the expression becomes exactly 

$$
k ^ {\lambda} \partial_ {\lambda} g _ {\mu \nu} + \partial_ {\mu} k ^ {\lambda} g _ {\lambda \nu} + \partial_ {\nu} k ^ {\lambda} g _ {\lambda \mu},
$$

which vanishes by the Killing equation. 

Let $u^{\mu} = \mathrm{d}x^{\mu} / \mathrm{d}\tau$ . Along a geodesic, $u^{\nu}D_{\nu}u^{\mu} = 0$ . Then 

$$
\frac {\mathrm {d}}{\mathrm {d} \tau} (k ^ {\mu} P _ {\mu}) = m u ^ {\nu} D _ {\nu} (k _ {\mu} u ^ {\mu}) = m u ^ {\nu} u ^ {\mu} D _ {\nu} k _ {\mu} + m k _ {\mu} u ^ {\nu} D _ {\nu} u ^ {\mu}.
$$

The second term is zero by the geodesic equation. The first term is zero because $u^{\nu}u^{\mu}$ is symmetric while $D_{\nu}k_{\mu}$ is antisymmetric in its symmetric part: 

$$
u ^ {\nu} u ^ {\mu} D _ {\nu} k _ {\mu} = \frac {1}{2} u ^ {\nu} u ^ {\mu} (D _ {\nu} k _ {\mu} + D _ {\mu} k _ {\nu}) = 0.
$$

Thus $k^{\mu}P_{\mu}$ is conserved. 

Noether derivation from the particle action. The same conservation law follows directly from the action 

$$
I = \frac {m}{2} \int g _ {\mu \nu} (x) \dot {x} ^ {\mu} \dot {x} ^ {\nu} \mathrm {d} \tau .
$$

An infinitesimal transformation generated by $k$ , namely $\delta x^{\mu} = \varepsilon k^{\mu}(x)$ , changes the Lagrangian by 

$$
\delta L = \frac {m}{2} (\mathcal {L} _ {k} g) _ {\mu \nu} \dot {x} ^ {\mu} \dot {x} ^ {\nu}.
$$

The Killing condition is exactly $\mathcal{L}_k g = 0$ , so the action is invariant. Noether's theorem gives 

$$
Q = \frac {\partial L}{\partial \dot {x} ^ {\mu}} \delta x ^ {\mu} / \varepsilon = m g _ {\mu \nu} \dot {x} ^ {\nu} k ^ {\mu} = k ^ {\mu} P _ {\mu},
$$

which is therefore constant along the geodesic. This proof is often shorter in applications because one only needs to check that the metric coefficients are invariant under the corresponding coordinate displacement. 

**Higher viewpoint.** A Killing field is the infinitesimal form of an isometry. The equality $D_{(\mu}k_{\nu)} = 0$ says that the metric has zero first-order deformation along the flow of $k$ . For geodesic motion, this metric symmetry becomes a conserved linear momentum $k^{\mu}P_{\mu}$ . Time translations give energy, rotations give angular momentum, and spatial translations give ordinary linear momentum; all are the same theorem written in different coordinate systems. 

## 1.4 Problem 4: The horizon generator of an Eddington-Finkelstein metric

Problem statement. Consider 

$$
\mathrm {d} s ^ {2} = - \left(1 - \frac {2 M}{r}\right) \mathrm {d} v ^ {2} + \mathrm {d} r \mathrm {d} v + r ^ {2} \mathrm {d} \Omega^ {2}.
$$

Let $S = r - 2M = 0$ and let 

$$
l = \widetilde {f} (x) (g ^ {\mu \nu} \partial_ {\nu} S) \partial_ {\mu}
$$

with $\widetilde{f} \neq 0$ . Prove that $l$ is normal to $S$ , that $l^2 = 0$ on $S$ , and that $\partial_v$ is a Killing vector field. Solution. The normal covector to the hypersurface $S = 0$ is 

$$
n _ {\mu} = \partial_ {\mu} S = \partial_ {\mu} r.
$$

The vector $l^{\mu} = \widetilde{fg}^{\mu \nu}n_{\nu}$ is the metric dual of this normal covector, so it is normal to the hypersurface. 

The squared norm is 

$$
l ^ {2} = g _ {\mu \nu} l ^ {\mu} l ^ {\nu} = \widetilde {f} ^ {2} g ^ {\mu \nu} \partial_ {\mu} S \partial_ {\nu} S.
$$

Since $S = r - 2M$ , this is $\widetilde{f}^2 g^{rr}$ . For the Eddington-Finkelstein form, $g^{rr}$ is proportional to $1 - 2M / r$ , hence 

$$
\left. l ^ {2} \right| _ {r = 2 M} = 0.
$$

Thus the hypersurface is null and $l$ is a null normal there. 

Finally, every component of the metric is independent of $v$ . Hence 

$$
\mathcal {L} _ {\partial_ {v}} g _ {\mu \nu} = \partial_ {v} g _ {\mu \nu} = 0,
$$

so $\partial_v$ is a Killing vector field. 

Explicit inverse-metric computation. Let 

$$
F (r) = 1 - \frac {2 M}{r}.
$$

The $(v,r)$ -part of the metric is, up to the convention implicit in the cross term, 

$$
g _ {a b} = \left( \begin{array}{c c} - F & 1 / 2 \\ 1 / 2 & 0 \end{array} \right) \quad \text {or , if the cross term is written as }2\mathrm{d}r\mathrm{d}v, \quad g _ {a b} = \left( \begin{array}{c c} - F & 1 \\ 1 & 0 \end{array} \right).
$$

In either convention the inverse has $g^{rr}$ proportional to $F$ . Since $S = r - 2M$ , one has $\partial_{\nu}S = \delta_{\nu}^{r}$ and hence 

$$
l ^ {\mu} = \widetilde {f} g ^ {\mu r}.
$$

Therefore 

$$
l ^ {2} = \widetilde {f} ^ {2} g ^ {r r} = C \widetilde {f} ^ {2} \left(1 - \frac {2 M}{r}\right)
$$

with a nonzero convention-dependent constant $C$ . The value at $r = 2M$ is zero independently of this harmless normalization. Thus the argument does not depend on whether the mixed term is normalized as $\mathrm{d}r\mathrm{d}v$ or $2\mathrm{d}r\mathrm{d}v$ ; only the vanishing of $F$ at the horizon matters. 

**Higher viewpoint.** A null hypersurface is geometrically unlike a spacelike or timelike hypersurface: its normal vector is also tangent to it. The surface $r = 2M$ is singled out by the vanishing of the inverse radial component $g^{rr}$ , which makes the normal dr null after raising the index. This is why a horizon can be generated by null curves lying inside the horizon itself. The Killing field $\partial_v$ reflects stationarity, while the null normal captures the causal character of the horizon. 

## 1.5 Problem 5: Scale and conformal currents

Problem statement. Let $\theta^{\mu \nu}$ be a symmetric conserved energy-momentum tensor. Define 

$$
s ^ {\mu} = x _ {\nu} \theta^ {\mu \nu}, K ^ {\lambda \mu} = x ^ {2} \theta^ {\lambda \mu} - 2 x ^ {\lambda} x _ {\rho} \theta^ {\rho \mu}.
$$

(a) Compute $\partial_{\mu}s^{\mu}$ and $\partial_{\mu}K^{\lambda \mu}$ , and determine when these currents are conserved. 

(b) A scalar $\sigma$ transforms as $\delta \sigma = x^{\lambda}\partial_{\lambda}\sigma +f^{-1}$ , while $\delta \phi = (1 + x^{\lambda}\partial_{\lambda})\phi$ . Prove that 

$$
\mathcal {L} = \mathcal {L} _ {s} - \frac {\mu_ {0} ^ {2}}{2} \phi^ {2} \mathrm {e} ^ {2 f \sigma} + \frac {1}{2 f ^ {2}} \partial_ {\mu} \mathrm {e} ^ {f \sigma} \partial^ {\mu} \mathrm {e} ^ {f \sigma}
$$

is scale invariant if $\mathcal{L}_s$ is scale invariant. 

(c) Explain why classical scale invariance may fail quantum mechanically. 

Solution. Using $\partial_{\mu}\theta^{\mu \nu} = 0$ and symmetry, 

$$
\partial_ {\mu} s ^ {\mu} = \partial_ {\mu} (x _ {\nu} \theta^ {\mu \nu}) = \theta_ {\mu} ^ {\mu}.
$$

Similarly, 

$$
\begin{array}{l} \partial_ {\mu} K ^ {\lambda \mu} = \partial_ {\mu} (x ^ {2} \theta^ {\lambda \mu} - 2 x ^ {\lambda} x _ {\rho} \theta^ {\rho \mu}) \\ = 2 x _ {\mu} \theta^ {\lambda \mu} - 2 x _ {\rho} \theta^ {\rho \lambda} - 2 x ^ {\lambda} \theta_ {\mu} ^ {\mu} \\ = - 2 x ^ {\lambda} \theta_ {\mu} ^ {\mu}. \\ \end{array}
$$

Thus the scale and special conformal currents are conserved when the stress tensor is traceless: 

$$
\theta_ {\mu} ^ {\mu} = 0.
$$

Let 

$$
\chi = \mathrm {e} ^ {f \sigma}.
$$

The transformation of $\sigma$ gives 

$$
\delta \chi = f \chi \delta \sigma = x ^ {\lambda} \partial_ {\lambda} \chi + \chi ,
$$

so $\chi$ has scale dimension 1, just like $\phi$ . Hence the product $\phi^2\chi^2$ has dimension 4, and the kinetic term $(\partial \chi)^2$ also has dimension 4. Since the spacetime measure has dimension $-4$ , the action is scale invariant whenever $\mathcal{L}_s$ is. 

Quantum mechanically, regularization introduces a scale. Couplings run with the renormalization scale, and the trace of the quantum stress tensor may acquire an anomalous contribution. Thus the classical condition $\theta_{\mu}^{\mu} = 0$ can become 

$$
\langle \theta_ {\mu} ^ {\mu} \rangle \neq 0.
$$

This is the scale or trace anomaly. 

Dimensional check of the dilaton compensation. A useful way to read the second part is to introduce $\chi = \mathrm{e}^{f\sigma}$ . Under an infinitesimal scale transformation, $\chi$ transforms as a field of engineering dimension one: 

$$
\delta \chi = x ^ {\lambda} \partial_ {\lambda} \chi + \chi .
$$

Thus the apparently dimensionful parameter $\mu_0$ is effectively replaced by $\mu_0\chi$ . The term $\mu_0^2\phi^2\chi^2$ has total dimension four if $\phi$ and $\chi$ both have dimension one, and the kinetic term for $\chi$ also has dimension four. Hence the integrand scales exactly oppositely to $\mathrm{d}^4 x$ . This is the standard compensator construction: a dimensionful parameter is made compatible with scale invariance by coupling it to a field whose vacuum value would later set the scale. 

**Higher viewpoint.** The trace of the stress tensor is the local diagnostic for scale and conformal symmetry. Classically, a traceless stress tensor implies conservation of the dilatation current and, for a suitably improved stress tensor, the special conformal currents. The dilaton construction shows how a scale can be hidden inside a field rather than inserted as a fixed number. Quantum theory changes the situation because choosing a regulator and renormalization scale breaks the naive scaling relation, producing the trace anomaly. 

## 1.6 Problem 6: Large- $N$ counting in an $O(N)$ scalar model

Problem statement. Consider 

$$
\mathcal {L} = \frac {1}{2} \partial_ {\mu} \phi^ {a} \partial^ {\mu} \phi^ {a} - \frac {1}{2} \mu_ {0} ^ {2} \phi^ {a} \phi^ {a} - \frac {1}{8} \lambda_ {0} (\phi^ {a} \phi^ {a}) ^ {2}, \qquad a = 1, \ldots , N.
$$

(a) Write down the propagator, the interaction vertex, and the four-point diagrams up to one loop. 

(b) Define $g_0 = \lambda_0 N$ . Compute the order in $g_0$ and $N$ of these diagrams and identify the leading diagrams as $N \to \infty$ with $g_0$ fixed. 

Solution. In momentum space the propagator is 

$$
\frac {\mathrm {i} \delta^ {a b}}{p ^ {2} - \mu_ {0} ^ {2} + \mathrm {i} \varepsilon}
$$

in Lorentzian convention. The quartic vertex has the $O(N)$ tensor structure 

$$
- \mathrm {i} \lambda_ {0} \left(\delta^ {a b} \delta^ {c d} + \delta^ {a c} \delta^ {b d} + \delta^ {a d} \delta^ {b c}\right)
$$

up to the normalization convention for the factor $1/8$ in the Lagrangian. Four-point diagrams up to one loop consist of the tree-level quartic vertex and the three one-loop bubble diagrams in the $s-$ , $t-$ , and $u$ -channels. 

Put $\lambda_0 = g_0 / N$ . Each quartic vertex contributes $g_0 / N$ , while each closed internal index loop contributes a factor $N$ . A one-loop bubble with two vertices and one independent closed $O(N)$ index loop has size 

$$
\left(\frac {g _ {0}}{N}\right) ^ {2} N = \frac {g _ {0} ^ {2}}{N}.
$$

The tree four-point vertex has size $g_0 / N$ . More generally, a chain of $L$ bubbles has $L + 1$ vertices and $L$ index loops, so it scales as 

$$
\left(\frac {g _ {0}}{N}\right) ^ {L + 1} N ^ {L} = \frac {g _ {0} ^ {L + 1}}{N}.
$$

Therefore the leading connected four-point diagrams at large $N$ are the bubble-chain diagrams, all of order $1 / N$ after resummation in powers of $g_0$ . 

Double-line intuition for vector models. Although the model is a vector model rather than a matrix model, the counting principle is the same: every summed internal $O(N)$ index produces one factor of $N$ . At fixed $g_0 = \lambda_0N$ , a quartic vertex costs one factor $1/N$ . A diagram is therefore favored when its vertices create as many closed index sums as possible. Bubble chains do exactly this: adding one more bubble adds one vertex and one closed index loop, so the net order remains $1/N$ . By contrast, diagrams whose index contractions fail to create a new closed index loop acquire additional powers of $1/N$ and are subleading. This explains why the leading large- $N$ answer is a resummation, not a single low-order graph. 

**Higher viewpoint.** Large- $N$ perturbation theory reorganizes Feynman diagrams by index combinatorics rather than by the number of loops alone. Keeping $g_{0} = \lambda_{0}N$ fixed makes the interaction weak at each vertex but compensates it through many internal components. The leading four-point function is therefore obtained from an infinite bubble-chain family. This mechanism is the vector-model analogue of the planar-diagram selection familiar from matrix large- $N$ limits. 

# Chapter 2 -2023 Mathematical Physics

## 2.1 Problem 1: A charged particle on the punctured plane

Problem statement. Consider 

$$
L (x, y, \dot {x}, \dot {y}) = \frac {1}{2} (\dot {x} ^ {2} + \dot {y} ^ {2}) + \frac {2 (x \dot {y} - y \dot {x})}{x ^ {2} + y ^ {2}}.
$$

Compute the Hamiltonian in magnetic form, prove rotational and scale symmetries, derive their conserved quantities, and solve the Euler-Lagrange equations in polar coordinates. 

Solution. The canonical momenta are 

$$
p _ {x} = \dot {x} - \frac {2 y}{r ^ {2}}, \qquad p _ {y} = \dot {y} + \frac {2 x}{r ^ {2}}, \qquad r ^ {2} = x ^ {2} + y ^ {2}.
$$

Thus 

$$
\dot {x} = p _ {x} + \frac {2 y}{r ^ {2}}, \quad \dot {y} = p _ {y} - \frac {2 x}{r ^ {2}}.
$$

The Hamiltonian is 

$$
H = \frac {1}{2} \left(p _ {x} + \frac {2 y}{r ^ {2}}\right) ^ {2} + \frac {1}{2} \left(p _ {y} - \frac {2 x}{r ^ {2}}\right) ^ {2}.
$$

Equivalently, 

$$
H = \frac {1}{2} [ (p _ {x} - A _ {x}) ^ {2} + (p _ {y} - A _ {y}) ^ {2} ]
$$

with 

$$
A _ {x} = - \frac {2 y}{r ^ {2}}, \qquad A _ {y} = \frac {2 x}{r ^ {2}}.
$$

Away from the origin, 

$$
B _ {z} = \partial_ {x} A _ {y} - \partial_ {y} A _ {x} = 0.
$$

The vector potential is locally pure gauge but has nontrivial circulation around the origin. 

In polar coordinates, 

$$
x = r \cos \varphi , y = r \sin \varphi ,
$$

and 

$$
x \dot {y} - y \dot {x} = r ^ {2} \dot {\varphi}.
$$

Hence 

$$
L = \frac {1}{2} (\dot {r} ^ {2} + r ^ {2} \dot {\varphi} ^ {2}) + 2 \dot {\varphi}.
$$

Rotation $\varphi \mapsto \varphi +\alpha$ is a symmetry. The conserved angular momentum is 

$$
p _ {\varphi} = r ^ {2} \dot {\varphi} + 2 = \ell .
$$

The action is also invariant under the nonrelativistic scaling 

$$
r \mapsto \lambda r, \qquad t \mapsto \lambda^ {2} t,
$$

for which the conserved Noether charge is 

$$
D = r p _ {r} - 2 t H.
$$

The Euler-Lagrange equations are 

$$
\frac {\mathrm {d}}{\mathrm {d} t} (r ^ {2} \dot {\varphi} + 2) = 0, \qquad \ddot {r} = r \dot {\varphi} ^ {2}.
$$

Using $r^2\dot{\varphi} = \ell -2\eqqcolon L_0$ , the energy is 

$$
E = \frac {1}{2} \dot {r} ^ {2} + \frac {L _ {0} ^ {2}}{2 r ^ {2}}.
$$

For $E > 0$ and $L_0 \neq 0$ , 

$$
r ^ {2} (t) = 2 E (t - t _ {0}) ^ {2} + \frac {L _ {0} ^ {2}}{2 E},
$$

and 

$$
\varphi (t) = \varphi_ {0} + \arctan {\frac {2 E (t - t _ {0})}{L _ {0}}}.
$$

This gives the full classical motion. 

Geometric interpretation of the polar solution. Since the magnetic field is zero away from the origin, the local acceleration is that of a free particle. The nontrivial term $2\dot{\phi}$ is a total derivative locally, because $2\dot{\phi} = \frac{\mathrm{d}}{\mathrm{d}t}(2\phi)$ . It therefore does not change the local Euler-Lagrange equations on a simply connected patch. Its effect is global: $\phi$ is multivalued on the punctured plane, and the circulation 

$$
\oint A \cdot \mathrm {d} \boldsymbol {r} = \int_ {0} ^ {2 \pi} 2 \mathrm {d} \phi = 4 \pi
$$

remains detectable. The solution written in terms of $r(t)$ and $\phi (t)$ is consequently a free straight-line trajectory expressed in polar coordinates, but with the canonical angular momentum shifted by the topological term. 

**Higher viewpoint.** This system separates local dynamics from global topology. Locally, the vector potential is pure gauge and the particle feels no magnetic force on the punctured plane. Globally, the removed origin prevents the gauge potential from being single-valued, so the angular momentum is shifted by a circulation term. This is the classical counterpart of the Aharonov-Bohm mechanism: the field strength may vanish where the particle moves, while the topology of the configuration space still affects conserved quantities and phases. 

## 2.2 Problem 2: Degenerate perturbation theory for an anisotropic oscillator

Problem statement. A two-dimensional harmonic oscillator is perturbed by 

$$
H = \frac {p _ {x} ^ {2} + p _ {y} ^ {2}}{2 m} + \frac {1}{2} m \omega^ {2} (x ^ {2} + y ^ {2}) + \alpha m \omega^ {2} x y, \qquad \alpha \ll 1.
$$

Find the low unperturbed levels, first-order perturbative corrections, the exact spectrum by rotation, and compare the two. 

Solution. For $\alpha = 0$ 

$$
E _ {N} ^ {(0)} = \hbar \omega (N + 1), \qquad N = n _ {x} + n _ {y},
$$

with degeneracy $N + 1$ . Thus the three lowest levels are 

$$
N = 0: E = \hbar \omega , \qquad N = 1: E = 2 \hbar \omega , \qquad N = 2: E = 3 \hbar \omega ,
$$

with degeneracies 1,2,3. 

Write 

$$
x = \sqrt {\frac {\hbar}{2 m \omega}} (a _ {x} + a _ {x} ^ {\dagger}), \qquad y = \sqrt {\frac {\hbar}{2 m \omega}} (a _ {y} + a _ {y} ^ {\dagger}).
$$

Then 

$$
V = \alpha m \omega^ {2} x y = \frac {\alpha \hbar \omega}{2} (a _ {x} + a _ {x} ^ {\dagger}) (a _ {y} + a _ {y} ^ {\dagger}).
$$

For $N = 0$ , the first-order correction is zero. For $N = 1$ , in the basis $|1,0\rangle$ , $|0,1\rangle$ , the perturbation matrix is 

$$
\frac {\alpha \hbar \omega}{2} \left( \begin{array}{c c} 0 & 1 \\ 1 & 0 \end{array} \right),
$$

so the shifts are 

$$
\Delta E = \pm \frac {\alpha \hbar \omega}{2}.
$$

For $N = 2$ , in the basis $|2,0\rangle, |1,1\rangle, |0,2\rangle$ , the matrix is 

$$
\frac {\alpha \hbar \omega}{2} \left( \begin{array}{c c c} 0 & \sqrt {2} & 0 \\ \sqrt {2} & 0 & \sqrt {2} \\ 0 & \sqrt {2} & 0 \end{array} \right),
$$

whose eigenvalues are 

$$
0, \quad \pm \alpha \hbar \omega .
$$

For the exact spectrum, rotate coordinates: 

$$
u = \frac {x + y}{\sqrt {2}}, \qquad v = \frac {x - y}{\sqrt {2}}.
$$

Then 

$$
x ^ {2} + y ^ {2} = u ^ {2} + v ^ {2}, \quad x y = \frac {1}{2} (u ^ {2} - v ^ {2}),
$$

so 

$$
H = \frac {p _ {u} ^ {2} + p _ {v} ^ {2}}{2 m} + \frac {1}{2} m \omega^ {2} (1 + \alpha) u ^ {2} + \frac {1}{2} m \omega^ {2} (1 - \alpha) v ^ {2}.
$$

Thus 

$$
E _ {n _ {u}, n _ {v}} = \hbar \omega \sqrt {1 + \alpha} \left(n _ {u} + \frac {1}{2}\right) + \hbar \omega \sqrt {1 - \alpha} \left(n _ {v} + \frac {1}{2}\right).
$$

Expanding $\sqrt{1\pm\alpha} = 1\pm \alpha /2 + \mathcal{O}(\alpha^2)$ reproduces the perturbative shifts above. 

Normal-mode method as the exact solution. The exact diagonalization also gives the perturbative answer without constructing each finite-dimensional matrix separately. Since 

$$
x y = \frac {1}{2} (u ^ {2} - v ^ {2}), \qquad x ^ {2} + y ^ {2} = u ^ {2} + v ^ {2},
$$

the Hamiltonian is a sum of two independent oscillators with frequencies 

$$
\omega_ {u} = \omega \sqrt {1 + \alpha}, \quad \omega_ {v} = \omega \sqrt {1 - \alpha}.
$$

Hence 

$$
E _ {n _ {u}, n _ {v}} = \hbar \omega \left[ (n _ {u} + n _ {v} + 1) + \frac {\alpha}{2} (n _ {u} - n _ {v}) + O (\alpha^ {2}) \right].
$$

For a fixed total number $N = n_u + n_v$ , the first-order splitting is therefore proportional to $n_u - n_v$ . For $N = 1$ this gives $\pm \alpha \hbar \omega /2$ , and for $N = 2$ it gives $-\alpha \hbar \omega,0, + \alpha \hbar \omega$ , agreeing with the degenerate perturbation calculation. 

**Higher viewpoint.** Degenerate perturbation theory is the infinitesimal form of normal-mode diagonalization. The perturbation $xy$ does not introduce an essentially new interaction; it says that the chosen coordinate axes are not principal axes of the quadratic potential. The finite-dimensional perturbation matrices are therefore the first-order shadows of an exact rotation of coordinates. This problem is a useful model for recognizing when perturbation theory is hiding a simple change of variables. 

## 2.3 Problem 3: Gauge potentials and radiation fields

Problem statement. Express electromagnetic fields in terms of potentials $A^{\mu} = (\phi, \mathbf{A})$ , prove gauge invariance and the automatic Maxwell equations, derive the Lorenz-gauge wave equations, and use the retarded Green function to find the far-field nonrelativistic potentials of a moving charge. 

Solution. The fields are 

$$
\mathbf {E} = - \nabla \phi - \partial_ {t} \mathbf {A}, \quad \mathbf {B} = \nabla \times \mathbf {A}.
$$

Under 

$$
\phi \mapsto \phi + \partial_ {t} f, \quad \mathbf {A} \mapsto \mathbf {A} - \nabla f,
$$

one has 

$$
\mathbf {E} \mapsto - \nabla (\phi + \partial_ {t} f) - \partial_ {t} (\mathbf {A} - \nabla f) = \mathbf {E},
$$

and $\mathbf{B}$ is unchanged because $\nabla \times \nabla f = 0$ 

The two homogeneous Maxwell equations are automatic: 

$$
\nabla \cdot \mathbf {B} = \nabla \cdot (\nabla \times \mathbf {A}) = 0,
$$

and 

$$
\partial_ {t} \mathbf {B} + \nabla \times \mathbf {E} = \partial_ {t} (\nabla \times \mathbf {A}) + \nabla \times (- \nabla \phi - \partial_ {t} \mathbf {A}) = 0.
$$

In Lorenz gauge, 

$$
\frac {1}{c ^ {2}} \partial_ {t} \phi + \nabla \cdot {\bf A} = 0
$$

(up to the convention-dependent power of $c$ ), the remaining Maxwell equations become wave equations 

$$
\left(\frac {1}{c ^ {2}} \partial_ {t} ^ {2} - \nabla^ {2}\right) \phi = \rho , \qquad \left(\frac {1}{c ^ {2}} \partial_ {t} ^ {2} - \nabla^ {2}\right) \mathbf {A} = \frac {1}{c} \mathbf {J}
$$

in Heaviside-Lorentz units. 

For a point charge $e$ on trajectory $\mathbf{R}(t)$ 

$$
\rho (t, \mathbf {r}) = e \delta^ {3} (\mathbf {r} - \mathbf {R} (t)), \qquad \mathbf {J} (t, \mathbf {r}) = e \mathbf {v} (t) \delta^ {3} (\mathbf {r} - \mathbf {R} (t)).
$$

Using the retarded Green function gives the retarded potentials. In the far-field and nonrelativistic approximation, 

$$
\phi (\mathbf {r}, t) = \frac {e}{4 \pi | \mathbf {r} - \mathbf {R} (t _ {r}) |} = \frac {e}{4 \pi r} + \mathcal {O} (r ^ {- 2}),
$$

and 

$$
\mathbf {A} (\mathbf {r}, t) = \frac {e \mathbf {v} (t _ {r})}{4 \pi c r} + \mathcal {O} (r ^ {- 2}, v ^ {2} / c ^ {2}), \qquad t _ {r} = t - \frac {r}{c}.
$$

Covariant formulation. In four-vector notation define 

$$
F _ {\mu \nu} = \partial_ {\mu} A _ {\nu} - \partial_ {\nu} A _ {\mu}.
$$

Gauge transformations $A_{\mu} \mapsto A_{\mu} + \partial_{\mu}f$ leave $F_{\mu \nu}$ unchanged because mixed partial derivatives commute. The homogeneous Maxwell equations become the Bianchi identity 

$$
\partial_ {[ \lambda} F _ {\mu \nu ]} = 0.
$$

The inhomogeneous equations are 

$$
\partial_ {\mu} F ^ {\mu \nu} = J ^ {\nu}.
$$

Substituting $F_{\mu \nu}$ gives 

$$
\square A ^ {\nu} - \partial^ {\nu} \left(\partial_ {\mu} A ^ {\mu}\right) = J ^ {\nu}.
$$

In Lorenz gauge $\partial_{\mu}A^{\mu} = 0$ , this reduces to the wave equation $\square A^{\nu} = J^{\nu}$ . The retarded Green function is then the causal inverse of $\square$ , which is why the potentials are evaluated at the retarded time. 

**Higher viewpoint**. Gauge theory separates redundant description from physical field strength. The potentials are not unique, but they make causality and wave propagation transparent once a gauge condition is imposed. In Lorenz gauge, Maxwell's equations become hyperbolic wave equations for $A^{\mu}$ , while the fields $E$ and $B$ remain gauge-invariant derivatives. The far-zone radiation field is governed by the source motion at the retarded time, reflecting propagation along the light cone. 

## 2.4 Problem 4: One-dimensional heat capacity of bosons and fermions

Problem statement. A one-dimensional gas of free massless bosons has dispersion $E_{k} = \hbar v|k|$ and chemical potential $\mu = 0$ . Compute the heat capacity per unit length. Repeat for massive spinless fermions with $E_{k} = \hbar^{2}k^{2} / (2m)$ and $\mu$ far above the band bottom. 

Solution. For bosons, 

$$
\frac {U}{L} = \int_ {- \infty} ^ {\infty} \frac {\mathrm {d} k}{2 \pi} \frac {\hbar v | k |}{\mathrm {e} ^ {\beta \hbar v | k |} - 1} = \frac {1}{\pi} \int_ {0} ^ {\infty} \frac {\hbar v k \mathrm {d} k}{\mathrm {e} ^ {\beta \hbar v k} - 1}.
$$

Set $x = \beta \hbar vk$ . Since 

$$
\int_ {0} ^ {\infty} \frac {x \mathrm {d} x}{\mathrm {e} ^ {x} - 1} = \frac {\pi^ {2}}{6},
$$

we get 

$$
\frac {U}{L} = \frac {\pi}{6} \frac {(k _ {B} T) ^ {2}}{\hbar v}, \qquad \frac {C}{L} = \frac {\partial}{\partial T} \frac {U}{L} = \frac {\pi}{3} \frac {k _ {B} ^ {2} T}{\hbar v}.
$$

For spinless massive fermions in one dimension, only excitations near the two Fermi points contribute at low temperature. The density of states per unit length at the Fermi energy is 

$$
\rho (\mu) = \frac {1}{\pi \hbar v _ {F}}, \qquad v _ {F} = \frac {\hbar k _ {F}}{m}.
$$

The Sommerfeld expansion gives 

$$
\frac {C}{L} = \frac {\pi^ {2}}{3} k _ {B} ^ {2} T \rho (\mu) = \frac {\pi}{3} \frac {k _ {B} ^ {2} T}{\hbar v _ {F}}.
$$

Conformal low-energy derivation. Both systems may also be read from the universal low-temperature energy density of a one-dimensional gapless mode. A single bosonic branch 

with velocity $v$ has thermal energy density proportional to $T^2 / v$ , and the two directions $k > 0, k < 0$ give 

$$
\frac {U}{L} = \frac {\pi}{6} \frac {(k _ {B} T) ^ {2}}{\hbar v}.
$$

For spinless fermions, the filled Fermi sea contributes a temperature-independent ground-state energy. Thermal corrections come from linearizing the dispersion near the two Fermi points: 

$$
E _ {k} - \mu \simeq \pm \hbar v _ {F} (k \mp k _ {F}).
$$

Thus the low-energy theory again consists of right- and left-moving gapless modes, now with velocity $v_{F}$ . The same $T^{2}$ energy correction gives a heat capacity linear in $T$ . 

**Higher viewpoint.** The detailed microscopic statistics differ, but the low-temperature answer is controlled by the same one-dimensional gapless structure. Linear dispersion near the relevant low-energy points gives a constant density of states per energy, so the thermal energy scales as $T^2$ and the heat capacity as $T$ . The only model-dependent parameter that remains is the propagation velocity: $v$ for the boson and $v_{F}$ for the fermion. 

## 2.5 Problem 5: Schwarzschild-de Sitter geometry

Problem statement. Consider the vacuum Einstein equation with cosmological constant 

$$
R _ {\mu \nu} - \frac {1}{2} g _ {\mu \nu} R + \Lambda g _ {\mu \nu} = 0.
$$

Show that $R_{\mu \nu} = kg_{\mu \nu}$ and find $k$ . For 

$$
\mathrm {d} s ^ {2} = - f (r) \mathrm {d} t ^ {2} + \frac {\mathrm {d} r ^ {2}}{f (r)} + r ^ {2} (\mathrm {d} \theta^ {2} + \sin^ {2} \theta \mathrm {d} \varphi^ {2}),
$$

compute the Ricci tensor and solve for $f(r)$ . Prove that $\partial_t$ and $\partial_\varphi$ are Killing fields. 

Solution. Taking the trace in four dimensions gives 

$$
R - 2 R + 4 \Lambda = 0,
$$

so $R = 4\Lambda$ . Substitution gives 

$$
R _ {\mu \nu} = \Lambda g _ {\mu \nu},
$$

so $k = \Lambda$ 

For the static spherically symmetric ansatz, the nonzero Ricci components are 

$$
R _ {t t} = f \left(\frac {1}{2} f ^ {\prime \prime} + \frac {f ^ {\prime}}{r}\right),
$$

$$
R _ {r r} = - \frac {1}{f} \left(\frac {1}{2} f ^ {\prime \prime} + \frac {f ^ {\prime}}{r}\right),
$$

$$
R _ {\theta \theta} = 1 - f - r f ^ {\prime}, R _ {\varphi \varphi} = \sin^ {2} \theta (1 - f - r f ^ {\prime}).
$$

The scalar curvature is 

$$
R = - f ^ {\prime \prime} - \frac {4 f ^ {\prime}}{r} + \frac {2 (1 - f)}{r ^ {2}}.
$$

The equation $R_{\mu \nu} = \Lambda g_{\mu \nu}$ implies 

$$
1 - f - r f ^ {\prime} = \Lambda r ^ {2}.
$$

Thus 

$$
(r f) ^ {\prime} = 1 - \Lambda r ^ {2},
$$

and hence 

$$
f (r) = 1 - \frac {2 M}{r} - \frac {\Lambda r ^ {2}}{3}
$$

for an integration constant $M$ . Since the metric coefficients are independent of $t$ and $\varphi$ , both $\partial_t$ and $\partial_{\varphi}$ are Killing vector fields. 

Solving from the angular equation first. The angular component already contains the essential ordinary differential equation. Since $R_{\theta \theta} = 1 - f - rf'$ and $g_{\theta \theta} = r^2$ , the Einstein condition gives 

$$
1 - f - r f ^ {\prime} = \Lambda r ^ {2}.
$$

This can be rewritten as 

$$
(r f) ^ {\prime} = 1 - \Lambda r ^ {2}.
$$

After integration, 

$$
r f = r - \frac {\Lambda r ^ {3}}{3} + C,
$$

so 

$$
f (r) = 1 + \frac {C}{r} - \frac {\Lambda r ^ {2}}{3}.
$$

Writing $C = -2M$ gives the standard form. The remaining $tt$ and $rr$ equations are then automatically consistent with this solution, reflecting the reduced freedom imposed by spherical symmetry and the Bianchi identities. 

**Higher viewpoint.** The Schwarzschild-de Sitter metric is determined by symmetry plus the Einstein condition. Spherical symmetry reduces a nonlinear tensor equation to a single radial equation for $f(r)$ . The integration constant is interpreted as the mass parameter, while the cosmological constant supplies the quadratic de Sitter term. The Killing fields $\partial_t$ and $\partial_{\phi}$ are visible directly because the metric coefficients do not depend on $t$ or $\phi$ . 

## 2.6 Problem 6: One-loop self-energy in $\phi^3$ theory

Problem statement. In four-dimensional Minkowski spacetime, consider 

$$
\mathcal {L} = - \frac {1}{2} \partial_ {\mu} \phi \partial^ {\mu} \phi - \frac {1}{2} m ^ {2} \phi^ {2} - \frac {1}{6} g \phi^ {3}.
$$

Write the propagator and vertex, compute the one-loop self-energy using dimensional regularization, and determine the mass counterterm needed to make it finite. 

Solution. The momentum-space propagator is 

$$
\frac {\mathrm {i}}{p ^ {2} + m ^ {2} - \mathrm {i} \varepsilon}
$$

with the sign convention corresponding to metric $(-, +, +, +)$ . The cubic vertex is $-\mathrm{i}g$ . 

The one-loop two-point graph is 

$$
\mathrm {i} \Pi (p ^ {2}) = \frac {1}{2} (- \mathrm {i} g) ^ {2} \int \frac {\mathrm {d} ^ {d} k}{(2 \pi) ^ {d}} \frac {\mathrm {i}}{k ^ {2} + m ^ {2} - \mathrm {i} \varepsilon} \frac {\mathrm {i}}{(k + p) ^ {2} + m ^ {2} - \mathrm {i} \varepsilon}.
$$

Using a Feynman parameter and shifting the loop momentum gives 

$$
\Pi (p ^ {2}) = \frac {g ^ {2}}{2} \int_ {0} ^ {1} \mathrm {d} x \int \frac {\mathrm {d} ^ {d} \ell}{(2 \pi) ^ {d}} \frac {1}{(\ell^ {2} + \Delta - \mathrm {i} \varepsilon) ^ {2}},
$$

where 

$$
\Delta = m ^ {2} + x (1 - x) p ^ {2}.
$$

In $d = 4 - \varepsilon$ dimensions, 

$$
\Pi (p ^ {2}) = \frac {g ^ {2}}{3 2 \pi^ {2}} \int_ {0} ^ {1} \mathrm {d} x \left[ \frac {2}{\varepsilon} - \gamma + \log 4 \pi - \log \frac {\Delta}{\mu^ {2}} + \mathcal {O} (\varepsilon) \right]
$$

up to the overall sign convention of the two-point function. The divergence is momentum-independent, so it is removed by a mass counterterm 

$$
\delta m ^ {2} = - \frac {g ^ {2}}{3 2 \pi^ {2}} \left(\frac {2}{\varepsilon} - \gamma + \log 4 \pi\right)
$$

in the convention where the renormalized self-energy is $\Pi +\delta m^2$ . In minimal subtraction one keeps only the pole part. 

Power counting and the structure of the counterterm. Before evaluating the integral, one can predict the type of divergence. The one-loop two-point integral behaves at large loop momentum as 

$$
\int^ {\Lambda_ {\mathrm {U V}}} \frac {\mathrm {d} ^ {4} k}{(2 \pi) ^ {4}} \frac {1}{k ^ {4}},
$$

so it is logarithmically divergent. Since the leading ultraviolet part is independent of the external momentum $p$ , the pole is a local mass-type divergence. Dimensional regularization refines this estimate by replacing the logarithm with a pole at $d = 4$ : 

$$
\Gamma \left(2 - \frac {d}{2}\right) = \Gamma \left(\frac {\varepsilon}{2}\right) = \frac {2}{\varepsilon} - \gamma + O (\varepsilon).
$$

Thus the counterterm must be proportional to $\phi^2$ . Momentum-dependent finite terms remain in the renormalized self-energy, but the ultraviolet subtraction has the same local form predicted by power counting. 

**Higher viewpoint.** The calculation illustrates the logic of perturbative renormalization. Power counting identifies the possible local counterterms, and dimensional regularization computes the precise pole coefficient. In this $\phi^3$ two-point graph the ultraviolet divergence is logarithmic and momentum-independent at leading order, so it renormalizes the mass. The nonlocal dependence on $p^2$ is physical after subtraction and cannot be removed by a local counterterm. 

# Chapter 3 -2024 Mathematical Physics

## 3.1 Problem 1: Central power-law potentials and closed near-circular orbits

Problem statement. A particle of mass $m$ moves in an attractive central potential 

$$
V (r) = \alpha r ^ {k},
$$

where $k$ and $\alpha$ have the same sign. Derive the polar-coordinate Lagrangian, reduce the radial problem, find circular orbits and their stability, compute the small-oscillation period, determine when the approximate orbit closes, and derive the orbit equation. 

Solution. In polar coordinates, 

$$
L = \frac {1}{2} m (\dot {r} ^ {2} + r ^ {2} \dot {\varphi} ^ {2}) - \alpha r ^ {k}.
$$

The angular momentum 

$$
\ell = m r ^ {2} \dot {\varphi}
$$

is conserved. The radial motion is governed by 

$$
L _ {\mathrm {e f f}} = \frac {1}{2} m \dot {r} ^ {2} - V _ {\mathrm {e f f}} (r), \qquad V _ {\mathrm {e f f}} (r) = \frac {\ell^ {2}}{2 m r ^ {2}} + \alpha r ^ {k}.
$$

A circular orbit of radius $r_0$ satisfies 

$$
V _ {\mathrm {e f f}} ^ {\prime} (r _ {0}) = 0,
$$

that is 

$$
- \frac {\ell^ {2}}{m r _ {0} ^ {3}} + \alpha k r _ {0} ^ {k - 1} = 0.
$$

Thus 

$$
r _ {0} ^ {k + 2} = \frac {\ell^ {2}}{m \alpha k}.
$$

The angular frequency is 

$$
\Omega_ {\varphi} = \frac {\ell}{m r _ {0} ^ {2}} = \sqrt {\frac {\alpha k}{m} r _ {0} ^ {k - 2}},
$$

and the circular period is 

$$
T _ {\varphi} = 2 \pi \sqrt {\frac {m}{\alpha k}} r _ {0} ^ {(2 - k) / 2}.
$$

The second derivative of the effective potential is 

$$
V _ {\mathrm {e f f}} ^ {\prime \prime} (r _ {0}) = \alpha k (k + 2) r _ {0} ^ {k - 2}.
$$

Since the force is attractive, $\alpha k > 0$ . Hence the circular orbit is stable exactly when 

$$
k > - 2.
$$

For stable circular orbits, the radial small-oscillation frequency is 

$$
\Omega_ {r} = \sqrt {\frac {1}{m} V _ {\mathrm {e f f}} ^ {\prime \prime} (r _ {0})} = \sqrt {k + 2} \Omega_ {\varphi}.
$$

The orbit closes in the small-oscillation approximation when the ratio of angular and radial periods is rational, equivalently when 

$$
\sqrt {k + 2} \in \mathbb {Q}.
$$

Finally, with $u = 1 / r$ , Binet's equation is 

$$
\frac {\mathrm {d} ^ {2} u}{\mathrm {d} \varphi^ {2}} + u = \frac {m \alpha k}{\ell^ {2}} u ^ {- k - 1}.
$$

Binet-equation linearization. The same frequency ratio follows directly from Binet's equation. Let $u = u_0 + \eta$ , where $u_0 = 1 / r_0$ corresponds to the circular orbit. Since 

$$
u _ {0} = \frac {m \alpha k}{\ell^ {2}} u _ {0} ^ {- k - 1},
$$

linearizing 

$$
u ^ {\prime \prime} + u = \frac {m \alpha k}{\ell^ {2}} u ^ {- k - 1}
$$

gives 

$$
\eta^ {\prime \prime} + \eta = - (k + 1) \eta ,
$$

and hence 

$$
\eta^ {\prime \prime} + (k + 2) \eta = 0.
$$

Thus the radial oscillation as a function of polar angle has angular frequency $\sqrt{k + 2}$ . A near-circular orbit closes when the radial oscillation and the angular motion are commensurable, again giving $\sqrt{k + 2} \in \mathbb{Q}$ . 

**Higher viewpoint.** Central-force problems are governed by two equivalent reductions: an effective radial potential in time and Binet's equation in polar angle. Stability is the positivity of the second variation of the effective potential, while precession is encoded in the mismatch between radial and angular frequencies. The exceptional Kepler and oscillator potentials are distinguished because their frequency ratios make all bounded orbits close, not merely selected near-circular ones. 

## 3.2 Problem 2: A forced harmonic oscillator and coherent-state transitions

Problem statement. A harmonic oscillator initially in its ground state is subjected to a transient perturbation $\Delta H = F(t)x$ with $F(t\to \pm \infty)\rightarrow 0$ . Solve the Heisenberg equations, find transition probabilities, the final energy, and evaluate the Gaussian pulse case. 

Solution. Write 

$$
x = \sqrt {\frac {\hbar}{2 m \omega}} (a + a ^ {\dagger}).
$$

The Hamiltonian is 

$$
H = \hbar \omega \left(a ^ {\dagger} a + \frac {1}{2}\right) + F (t) \sqrt {\frac {\hbar}{2 m \omega}} (a + a ^ {\dagger}).
$$

The Heisenberg equation is 

$$
\dot {a} = - \mathrm {i} \omega a - \frac {\mathrm {i}}{\hbar} F (t) \sqrt {\frac {\hbar}{2 m \omega}}.
$$

Thus 

$$
\frac {\mathrm {d}}{\mathrm {d} t} (\mathrm {e} ^ {\mathrm {i} \omega t} a (t)) = - \frac {\mathrm {i}}{\sqrt {2 m \hbar \omega}} F (t) \mathrm {e} ^ {\mathrm {i} \omega t}.
$$

Consequently 

$$
a _ {+ \infty} = a _ {- \infty} + \beta , \qquad \beta = - \frac {\mathrm {i}}{\sqrt {2 m \hbar \omega}} \int_ {- \infty} ^ {\infty} F (t) \mathrm {e} ^ {\mathrm {i} \omega t} \mathrm {d} t.
$$

The initial vacuum is a coherent state for the final annihilation operator. Hence 

$$
| c _ {n} | ^ {2} = \mathrm {e} ^ {- | \beta | ^ {2}} \frac {| \beta | ^ {2 n}}{n !}.
$$

The final mean energy is 

$$
\langle H \rangle_ {+ \infty} = \hbar \omega \left(| \beta | ^ {2} + \frac {1}{2}\right).
$$

For 

$$
F (t) = F _ {0} \mathrm {e} ^ {- t ^ {2} / (2 \sigma_ {t} ^ {2})}, \qquad F _ {0} = \eta \frac {\hbar \omega}{l}, \qquad l = \sqrt {\frac {\hbar}{m \omega}},
$$

we have 

$$
\int F (t) \mathrm {e} ^ {\mathrm {i} \omega t} \mathrm {d} t = F _ {0} \sqrt {2 \pi} \sigma_ {t} \mathrm {e} ^ {- \omega^ {2} \sigma_ {t} ^ {2} / 2},
$$

and therefore 

$$
| \beta | ^ {2} = \pi \eta^ {2} (\omega \sigma_ {t}) ^ {2} \mathrm {e} ^ {- \omega^ {2} \sigma_ {t} ^ {2}}.
$$

The ground-state survival probability is $\mathrm{e}^{-|\beta|^2}$ . Requiring less than $1\%$ loss gives 

$$
| \beta | ^ {2} <   - \log (0. 9 9).
$$

For short pulses $\omega \sigma_{t}\ll 1$ 

$$
\eta <   \frac {\sqrt {- \log (0 . 9 9)}}{\sqrt {\pi} \omega \sigma_ {t}}.
$$

For long pulses $\omega \sigma_{t} \gg 1$ , the factor $\mathrm{e}^{-\omega^{2}\sigma_{t}^{2}}$ suppresses transitions for any fixed $\eta$ . Interaction-picture derivation. In the interaction picture, 

$$
V _ {I} (t) = F (t) \sqrt {\frac {\hbar}{2 m \omega}} \left(a \mathrm {e} ^ {- \mathrm {i} \omega t} + a ^ {\dagger} \mathrm {e} ^ {\mathrm {i} \omega t}\right).
$$

Because the commutator $[V_I(t), V_I(t')]$ is a scalar, the time-ordered exponential can be evaluated exactly as a displacement operator times a phase: 

$$
U _ {I} (+ \infty , - \infty) = \mathrm {e} ^ {\mathrm {i} \Phi} D (\beta),
$$

with the same 

$$
\beta = - \frac {\mathrm {i}}{\sqrt {2 m \hbar \omega}} \int_ {- \infty} ^ {\infty} F (t) \mathrm {e} ^ {\mathrm {i} \omega t} \mathrm {d} t.
$$

Acting on the vacuum gives a coherent state $D(\beta)|0\rangle$ . Expanding it in number states immediately yields the Poisson distribution $P_{n} = \mathrm{e}^{-|\beta |^{2}}|\beta |^{2n} / n!$ 

**Higher viewpoint.** A linear force does not squeeze or distort a harmonic oscillator state; it translates the state in phase space. Consequently the entire transition problem is determined by a single complex displacement parameter, which is the Fourier component of the force at the oscillator frequency. Slow pulses are adiabatically suppressed, while pulses with spectral weight near $\omega$ efficiently create excitations. The Poisson distribution is the number-state shadow of a coherent final state. 

## 3.3 Problem 3: Skin depth and reflection from a conducting metal

Problem statement. For an ohmic metal of large conductivity $\sigma$ , derive damped harmonic solutions, relate electric and magnetic amplitudes, explain perfect-conductor reflection, and describe the leading finite-conductivity fields in the metal. 

Solution. In Heaviside-Lorentz units, Ohm's law is $\mathbf{J} = \sigma \mathbf{E}$ . For fields proportional to $\mathrm{e}^{-\mathrm{i}\omega t + \mathrm{i}kz}$ , Maxwell's equations give 

$$
\nabla \times \mathbf {H} = \sigma \mathbf {E} - \mathrm {i} \omega \mathbf {E}.
$$

At high conductivity $\sigma \gg \omega$ , this is approximately $\nabla \times \mathbf{H} = \sigma \mathbf{E}$ . Combining with Faraday's law gives the diffusion-wave equation 

$$
k _ {c} ^ {2} \simeq \mathrm {i} \sigma \omega .
$$

With the branch corresponding to decay into the metal, 

$$
k _ {c} = \frac {1 + \mathrm {i}}{\sqrt {2}} \sqrt {\sigma \omega}
$$

in units $c = 1$ , or 

$$
k _ {c} = \frac {1 + \mathrm {i}}{\sqrt {2}} \frac {\sqrt {\sigma \omega}}{c}
$$

with the explicit $c$ convention used in the problem. 

If $\mathbf{H} = H_c\hat{y}\mathrm{e}^{-\mathrm{i}\omega t + \mathrm{i}k_cz}$ , then 

$$
\nabla \times \mathbf {H} = - \mathrm {i} k _ {c} H _ {c} \hat {\mathbf {x}} \mathrm {e} ^ {- \mathrm {i} \omega t + \mathrm {i} k _ {c} z},
$$

so 

$$
\mathbf {E} _ {c} \simeq - \frac {\mathrm {i} k _ {c}}{\sigma} \mathbf {H} _ {c} \times \hat {\boldsymbol {z}}.
$$

Thus $|E_c / H_c| \sim \sqrt{\omega / \sigma} \ll 1$ inside a good conductor. 

For a perfect conductor, the tangential electric field at the surface must vanish. Therefore the reflected wave has electric-field amplitude equal in magnitude and opposite in sign to that of the incident wave. The magnetic fields add so that the surface current supports the discontinuity. 

For large but finite $\sigma$ , the transmitted field inside the metal is a skin-depth field 

$$
\mathbf {E} (z, t) = \mathbf {E} _ {c} \mathrm {e} ^ {- \mathrm {i} \omega t + \mathrm {i} k _ {c} z}, \qquad \mathbf {H} (z, t) = \mathbf {H} _ {c} \mathrm {e} ^ {- \mathrm {i} \omega t + \mathrm {i} k _ {c} z},
$$

with penetration depth 

$$
\delta = \frac {1}{\mathrm {I m} k _ {c}} = \sqrt {\frac {2}{\sigma \omega}}
$$

in $c = 1$ units. Boundary conditions determine $H_{c}$ to be approximately twice the incident magnetic amplitude, while $E_{c}$ is smaller by order $\sqrt{\omega / \sigma}$ . 

Boundary-condition estimate. At a perfect conductor surface the tangential electric field must vanish. If the incident wave has tangential field $E_{i}$ , the reflected wave must therefore satisfy 

$E_{r} = -E_{i}$ at the surface. Since the magnetic field changes sign differently under reflection, the magnetic amplitudes add instead of canceling, so $H_{\mathrm{surface}} \simeq 2H_{i}$ . For large but finite conductivity, this doubled magnetic field penetrates slightly into the conductor and drives a current $J = \sigma E$ . Ampere's law then gives the estimate 

$$
\frac {E _ {c}}{H _ {c}} \sim \frac {k _ {c}}{\sigma} \sim \sqrt {\frac {\omega}{\sigma}},
$$

which is exactly the small parameter found from the complex wave number. Thus the finite-conductivity solution is a boundary layer correction to the perfect-conductor reflection law. 

**Higher viewpoint.** A good conductor converts electromagnetic propagation into diffusion over a short skin depth. The perfect-conductor limit is controlled by the boundary condition $E_{\parallel} = 0$ , while finite conductivity allows a small tangential electric field inside the metal to drive Ohmic current. The complex wave number records both attenuation and phase lag. The skin depth is therefore the penetration length of a dissipative boundary layer, not merely a geometric cutoff. 

## 3.4 Problem 4: Mean-field Ising theory and critical exponents

Problem statement. For the mean-field Hamiltonian 

$$
H _ {\mathrm {M F}} = \frac {1}{2} N J m ^ {2} - (J m + h) \sum_ {i} \sigma_ {i},
$$

derive the partition function, free energy, self-consistency equation, and mean-field exponents for magnetization, heat capacity, and susceptibility. 

Solution. The partition function is 

$$
Z = \sum_ {\{\sigma_ {i} \}} \exp \left[ - \beta \frac {1}{2} N J m ^ {2} + \beta (J m + h) \sum_ {i} \sigma_ {i} \right] = \mathrm {e} ^ {- \beta N J m ^ {2} / 2} (2 \cosh \beta (J m + h)) ^ {N}.
$$

The free energy per spin is 

$$
f (m) = \frac {1}{2} J m ^ {2} - \frac {1}{\beta} \log \left(2 \cosh \beta (J m + h)\right).
$$

Minimizing in $m$ gives 

$$
m = \tanh \beta (J m + h).
$$

For $h = 0$ , the equation $m = \tanh(\beta Jm)$ has only $m = 0$ when $T > T_{c}$ and also two nonzero stable solutions when $T < T_{c}$ , where 

$$
k _ {B} T _ {c} = J.
$$

Near criticality, expand 

$$
\tanh x = x - \frac {x ^ {3}}{3} + \dots .
$$

At $h = 0$ and $T < T_{c}$ , 

$$
m ^ {2} \simeq 3 \frac {T _ {c} - T}{T _ {c}},
$$

so 

$$
m \sim \left| T - T _ {c} \right| ^ {1 / 2}.
$$

Thus $\beta_{c} = 1 / 2$ . The susceptibility follows by differentiating 

$$
m = \tanh  \beta (J m + h).
$$

At $h = 0$ and $T > T_{c}$ , 

$$
\chi = \frac {\beta}{1 - \beta J} \sim | T - T _ {c} | ^ {- 1},
$$

so $\gamma_{c} = 1$ . Since near the critical point the internal energy behaves as $U \propto Jm^{2}$ , the heat capacity has a finite jump but no power-law divergence. Hence 

$$
\alpha_ {c} = 0.
$$

Landau expansion. The same exponents follow from expanding the free energy near $m = 0$ at $h = 0$ . Since 

$$
\log \cosh (\beta J m) = \frac {(\beta J m) ^ {2}}{2} - \frac {(\beta J m) ^ {4}}{1 2} + O (m ^ {6}),
$$

we obtain, up to an irrelevant constant, 

$$
f (m) = \frac {1}{2} J (1 - \beta J) m ^ {2} + \frac {1}{1 2} \beta^ {3} J ^ {4} m ^ {4} + O (m ^ {6}).
$$

The coefficient of $m^2$ changes sign at $T_{c} = J / k_{B}$ , while the quartic coefficient is positive. Minimizing this Landau polynomial gives $m \sim (T_{c} - T)^{1 / 2}$ . Adding a small field contributes $-hm$ , so at $T = T_{c}$ one also obtains the mean-field critical isotherm $m \sim h^{1 / 3}$ , corresponding to $\delta = 3$ . 

**Higher viewpoint.** Mean-field theory is Landau theory in microscopic disguise. The self-consistency equation and the free-energy expansion contain the same information: a quadratic coefficient changes sign while a positive quartic term stabilizes the ordered phase. The resulting exponents are classical because spatial fluctuations have been replaced by an averaged field. In low dimensions the true exponents can differ, but the mean-field calculation remains the baseline mechanism for symmetry breaking. 

## 3.5 Problem 5: Static coordinates on de Sitter space

Problem statement. In Minkowski space $\mathbb{R}^{1,n}$ , de Sitter space is 

$$
- (x ^ {0}) ^ {2} + \sum_ {i = 1} ^ {n} (x ^ {i}) ^ {2} = \alpha^ {2}.
$$

Using the static coordinates 

$$
x ^ {0} = \sqrt {\alpha^ {2} - r ^ {2}} \sinh (t / \alpha), x ^ {1} = \sqrt {\alpha^ {2} - r ^ {2}} \cosh (t / \alpha), x ^ {i} = r z _ {i},
$$

compute the induced metric. For $n = 3$ , compute $R_{\mu \nu}$ and $R$ , and determine whether $\partial_t$ and $\partial_\varphi$ are Killing fields. 

Solution. The coordinates satisfy the defining equation because 

$$
- (x ^ {0}) ^ {2} + (x ^ {1}) ^ {2} = (\alpha^ {2} - r ^ {2}) (\cosh^ {2} (t / \alpha) - \sinh^ {2} (t / \alpha)) = \alpha^ {2} - r ^ {2},
$$

and 

$$
\sum_ {i = 2} ^ {n} (x ^ {i}) ^ {2} = r ^ {2}.
$$

For $0 < r < \alpha$ , they define local coordinates on the static patch. 

A direct computation gives 

$$
\mathrm {d} s ^ {2} = - \left(1 - \frac {r ^ {2}}{\alpha^ {2}}\right) \mathrm {d} t ^ {2} + \left(1 - \frac {r ^ {2}}{\alpha^ {2}}\right) ^ {- 1} \mathrm {d} r ^ {2} + r ^ {2} \mathrm {d} \Omega_ {n - 2} ^ {2}.
$$

For $n = 3$ , this is a three-dimensional Lorentzian space form of positive curvature. Therefore 

$$
R _ {\mu \nu} = \frac {2}{\alpha^ {2}} g _ {\mu \nu}, R = \frac {6}{\alpha^ {2}}.
$$

Thus $dS_{3}$ is Einstein. Since the metric coefficients are independent of $t$ and, in polar coordinates on the sphere factor, independent of $\varphi$ , the fields $\partial_t$ and $\partial_{\varphi}$ are Killing vector fields. 

Curvature from the space-form identity. There is a shorter curvature computation. De Sitter space is the hyperquadric 

$$
- (x ^ {0}) ^ {2} + \sum_ {i = 1} ^ {n} (x ^ {i}) ^ {2} = \alpha^ {2}
$$

embedded in flat Minkowski space. Its second fundamental form is proportional to the induced metric, and the Gauss equation gives constant sectional curvature 

$$
K = \frac {1}{\alpha^ {2}}.
$$

In dimension $n$ , a space form satisfies 

$$
R _ {\mu \nu} = (n - 1) K g _ {\mu \nu}, \qquad R = n (n - 1) K.
$$

For $n = 3$ , this immediately gives 

$$
R _ {\mu \nu} = \frac {2}{\alpha^ {2}} g _ {\mu \nu}, R = \frac {6}{\alpha^ {2}}.
$$

This avoids a component-by-component Christoffel calculation. 

**Higher viewpoint.** The static patch metric is a coordinate expression of a constant-curvature hyperquadric. The horizon at $r = \alpha$ is not a curvature singularity; it is where the static time coordinate ceases to be timelike. The embedding picture explains the curvature immediately, while the coordinate form makes the Killing fields and the horizon structure visible. These are complementary descriptions of the same de Sitter geometry. 

## 3.6 Problem 6: One-loop divergences in pseudoscalar Yukawa theory

Problem statement. Consider 

$$
\mathcal {L} = \frac {1}{2} \partial_ {\mu} \phi \partial^ {\mu} \phi - \frac {1}{2} m ^ {2} \phi^ {2} + \bar {\psi} (\mathrm {i} \not \partial / - M) \psi - \mathrm {i} g \bar {\psi} \gamma^ {5} \psi \phi .
$$

Find the one-loop scalar and fermion self-energy divergences, identify counterterms, and decide whether nonrenormalizable divergences appear. 

Solution. The propagators are 

$$
\frac {\mathrm {i}}{p ^ {2} - m ^ {2} + \mathrm {i} \varepsilon}, \qquad \frac {\mathrm {i} (\not p + M)}{p ^ {2} - M ^ {2} + \mathrm {i} \varepsilon},
$$

and the Yukawa vertex is $g\gamma^5$ up to the convention-dependent factor of i. 

The scalar self-energy at one loop is a fermion loop with two Yukawa vertices: 

$$
\Pi_ {\phi} (p ^ {2}) \sim - g ^ {2} \int \frac {\mathrm {d} ^ {d} k}{(2 \pi) ^ {d}} \mathrm {T r} \left[ \gamma^ {5} \frac {k + M}{k ^ {2} - M ^ {2}} \gamma^ {5} \frac {k + p + M}{(k + p) ^ {2} - M ^ {2}} \right].
$$

Since $\gamma^5 / k\gamma^5 = -k$ and $(\gamma^5)^2 = 1$ , the divergent part contains a term proportional to $p^2$ and a term proportional to $M^2$ . These are canceled by counterterms 

$$
\delta Z _ {\phi} \frac {1}{2} \partial_ {\mu} \phi \partial^ {\mu} \phi - \frac {1}{2} \delta m ^ {2} \phi^ {2}.
$$

The fermion self-energy is 

$$
\Sigma_ {\psi} (p) \sim g ^ {2} \int \frac {\mathrm {d} ^ {d} k}{(2 \pi) ^ {d}} \gamma^ {5} \frac {k + M}{k ^ {2} - M ^ {2}} \gamma^ {5} \frac {1}{(p - k) ^ {2} - m ^ {2}}.
$$

Its divergent part is a linear combination of $\not p$ and $M$ . It is canceled by 

$$
\delta Z _ {\psi} \bar {\psi} \mathrm {i} \partial \psi - \delta M \bar {\psi} \psi .
$$

No new operator of dimension greater than four is required at one loop. The Yukawa interaction is power-counting renormalizable in four dimensions; vertex renormalization may be needed, but it has the same form as the original interaction. 

Power-counting closure. The superficial degree of divergence already predicts which counterterms may occur. In four dimensions the Yukawa coupling is dimensionless, $[g] = 0$ , and the fields have dimensions $[\phi] = 1$ , $[\psi] = 3/2$ . Therefore all divergences generated at one loop must be expressible through local operators of dimension at most four if the theory is renormalizable. The scalar self-energy can only contribute to $\phi^2$ and $(\partial \phi)^2$ ; the fermion self-energy can only contribute to $\bar{\psi}\psi$ and $\bar{\psi}\mathrm{i}\gamma^\mu \partial_\mu \psi$ ; and the vertex graph can only renormalize $\bar{\psi}\gamma^5\psi\phi$ . No operator such as $\phi^6$ or $(\partial \phi)^4$ is forced by the ultraviolet poles at this order. 

**Higher viewpoint.** Renormalizability means closure of the Lagrangian under quantum corrections. The role of the one-loop computation is not only to find pole coefficients but also to verify that the divergent structures match operators already present in the action. The pseudoscalar matrix $\gamma^5$ changes signs inside traces, but it does not alter the dimensional classification of possible counterterms. Thus the theory remains perturbatively renormalizable at one loop. 

# Chapter 4 -2025 Mathematical Physics

## 4.1 Problem 1: A bead on a rotating hoop

Problem statement. A bead of mass $m$ moves without friction on a hoop of radius $R$ rotating with angular velocity $\omega$ about the vertical axis under gravity. Find the Lagrangian, equations of motion, constants of motion, Hamiltonian, equilibria, and small-oscillation frequencies. 

Solution. Let $\theta$ be the angle from the bottom of the hoop. The bead has speed 

$$
v ^ {2} = R ^ {2} \dot {\theta} ^ {2} + \omega^ {2} R ^ {2} \sin^ {2} \theta .
$$

Taking gravitational potential zero at the bottom, 

$$
V = m g R (1 - \cos \theta).
$$

Thus 

$$
L = \frac {1}{2} m R ^ {2} \dot {\theta} ^ {2} + \frac {1}{2} m R ^ {2} \omega^ {2} \sin^ {2} \theta - m g R (1 - \cos \theta).
$$

The equation of motion is 

$$
\ddot {\theta} = \sin \theta \left(\omega^ {2} \cos \theta - \frac {g}{R}\right).
$$

The canonical momentum is $p_{\theta} = mR^{2}\dot{\theta}$ , and the Hamiltonian is 

$$
H = \frac {p _ {\theta} ^ {2}}{2 m R ^ {2}} - \frac {1}{2} m R ^ {2} \omega^ {2} \sin^ {2} \theta + m g R (1 - \cos \theta).
$$

It is conserved because the rotating-frame Lagrangian has no explicit time dependence. The fixed-frame mechanical energy differs by the sign of the rotational kinetic contribution and is not conserved, because the motor maintaining the hoop's rotation can exchange energy with the bead. 

Equilibrium satisfies 

$$
\sin \theta \left(\omega^ {2} \cos \theta - \frac {g}{R}\right) = 0.
$$

Let 

$$
\Omega = \sqrt {\frac {g}{R}}.
$$

For $\omega < \Omega$ , the bottom $\theta = 0$ is stable. For $\omega > \Omega$ , the bottom becomes unstable and two stable equilibria appear at 

$$
\cos \theta_ {0} = \frac {\Omega^ {2}}{\omega^ {2}}.
$$

Small oscillations at the bottom have frequency 

$$
\omega_ {\mathrm {s m a l l}} = \sqrt {\Omega^ {2} - \omega^ {2}} \qquad (\omega <   \Omega).
$$

At the off-bottom equilibria, 

$$
\omega_ {\mathrm {s m a l l}} = \sqrt {\omega^ {2} - \frac {\Omega^ {4}}{\omega^ {2}}}.
$$

Effective-potential derivation of stability. The Hamiltonian can be written as 

$$
H = \frac {p _ {\theta} ^ {2}}{2 m R ^ {2}} + V _ {\mathrm {e f f}} (\theta), \qquad V _ {\mathrm {e f f}} (\theta) = m g R (1 - \cos \theta) - \frac {1}{2} m R ^ {2} \omega^ {2} \sin^ {2} \theta .
$$

Equilibria satisfy $V_{\mathrm{eff}}'(\theta) = 0$ , i.e. 

$$
m R \sin \theta (g - R \omega^ {2} \cos \theta) = 0.
$$

The curvature is 

$$
V _ {\mathrm {e f f}} ^ {\prime \prime} (\theta) = m g R \cos \theta - m R ^ {2} \omega^ {2} (\cos^ {2} \theta - \sin^ {2} \theta).
$$

At the bottom, this is $mR(g - R\omega^2)$ , giving stability only for $\omega^2 < g / R$ . At the off-bottom equilibria $\cos \theta_0 = g / (R\omega^2)$ , the curvature is positive and equals 

$$
m R ^ {2} \left(\omega^ {2} - \frac {g ^ {2}}{R ^ {2} \omega^ {2}}\right),
$$

which yields the displayed small-oscillation frequency after division by the effective inertia $mR^2$ . 

**Higher viewpoint.** The rotating hoop is a concrete pitchfork bifurcation. The angular velocity controls the curvature of the effective potential at the bottom. Below the critical value $\sqrt{g / R}$ , gravity dominates and the bottom is stable. Above it, centrifugal effects destabilize the bottom and create two symmetric stable equilibria. This is the mechanical analogue of a Landau double-well transition, with $\theta$ playing the role of an order parameter. 

## 4.2 Problem 2: Angular momentum of a circularly polarized wave packet

Problem statement. A wave packet with transverse profile $E_0(x,y)$ propagates in the $z$ -direction with circular polarization. Verify the leading Maxwell solution, compute the energy per unit length, find first-gradient corrections for $k\sigma \gg 1$ , represent the correction by plane waves, and compute the ratio of angular momentum to energy. 

Solution. At leading order, 

$$
\mathbf {E} ^ {(0)} = E _ {0} (x, y) \mathrm {e} ^ {\mathrm {i} (k z - \omega t)} \frac {\hat {x} + \mathrm {i} \hat {y}}{\sqrt {2}}, \qquad \mathbf {B} ^ {(0)} = \hat {z} \times \mathbf {E} ^ {(0)},
$$

solves Maxwell's equations when derivatives of $E_0$ are neglected and $\omega = ck$ . 

The time-averaged energy per unit length in Heaviside-Lorentz units is 

$$
\langle U \rangle = \int \mathrm {d} x \mathrm {d} y | E _ {0} (x, y) | ^ {2}
$$

up to the conventional factor fixed by the normalization of complex amplitudes. For the Gaussian profile $E_0 = A\exp \left[-(x^2 +y^2) / (4\sigma^2)\right]$ , 

$$
\langle U \rangle = 2 \pi \sigma^ {2} | A | ^ {2}.
$$

Including first transverse gradients, impose $\nabla \cdot \mathbf{E} = 0$ . Since 

$$
E _ {x} ^ {(0)} = \frac {E _ {0}}{\sqrt {2}} \mathrm {e} ^ {\mathrm {i} (k z - \omega t)}, \qquad E _ {y} ^ {(0)} = \frac {\mathrm {i} E _ {0}}{\sqrt {2}} \mathrm {e} ^ {\mathrm {i} (k z - \omega t)},
$$

we need 

$$
\partial_ {x} E _ {x} ^ {(0)} + \partial_ {y} E _ {y} ^ {(0)} + \mathrm {i} k E _ {z} ^ {(1)} = 0.
$$

Thus 

$$
E _ {z} ^ {(1)} = \frac {\mathrm {i}}{\sqrt {2} k} (\partial_ {x} + \mathrm {i} \partial_ {y}) E _ {0} \mathrm {e} ^ {\mathrm {i} (k z - \omega t)}.
$$

The magnetic correction is obtained similarly from $\mathbf{B} = (1 / \omega)\mathbf{k}\times \mathbf{E}$ mode by mode. 

A plane-wave decomposition writes 

$$
E _ {0} (x, y) = \int \frac {\mathrm {d} ^ {2} q}{(2 \pi) ^ {2}} \widetilde {E} _ {0} (\mathbf {q}) \mathrm {e} ^ {\mathrm {i} (q _ {x} x + q _ {y} y)}.
$$

Each component has wave vector $(q_x, q_y, k_z)$ with $k_z = k - \mathcal{O}(q^2 / k)$ . Transversality $\mathbf{k} \cdot \mathbf{E} = 0$ requires a small longitudinal component 

$$
E _ {z} \simeq - \frac {q _ {x} E _ {x} + q _ {y} E _ {y}}{k},
$$

which is precisely the Fourier transform of the correction above. 

For right circular polarization, the leading angular momentum per unit length is the spin contribution 

$$
\langle L _ {z} \rangle = \frac {1}{\omega} \langle U \rangle .
$$

Thus 

$$
\frac {\langle L _ {z} \rangle}{\langle U \rangle} = \frac {1}{\omega}.
$$

This means that each photon carries angular momentum $\hbar$ and energy $\hbar \omega$ . 

Photon-counting interpretation. The ratio $\langle L_z\rangle /\langle U\rangle$ can also be obtained from the quantum interpretation of a classical circularly polarized wave packet. A right circularly polarized photon of frequency $\omega$ carries spin angular momentum $+\hbar$ along the propagation axis and energy $\hbar \omega$ . For a packet containing $N$ photons in the same helicity state, 

$$
U = N \hbar \omega , \qquad L _ {z} = N \hbar .
$$

Hence 

$$
\frac {L _ {z}}{U} = \frac {1}{\omega}.
$$

The classical field calculation is the large-occupation-number limit of this statement. The longitudinal correction required by $\nabla \cdot E = 0$ ensures that the finite-width packet is a consistent Maxwell field, but it does not change the leading spin-to-energy ratio. 

**Higher viewpoint.** A finite-width electromagnetic beam cannot be exactly transverse in the naive plane-wave sense; transversality forces a small longitudinal component controlled by transverse gradients. Once this consistency condition is imposed, circular polarization carries spin angular momentum whose ratio to energy is $1 / \omega$ . The same result appears both classically, through field angular momentum, and quantum mechanically, through the helicity and energy of photons. 

## 4.3 Problem 3: A shifted harmonic oscillator in an electric field

Problem statement. A charged oscillator has Hamiltonian 

$$
H = \frac {p ^ {2}}{2 m} + \frac {1}{2} m \omega^ {2} x ^ {2} - q E x.
$$

Complete the square using a shift operator, solve the spectrum, express the shift in ladder operators, compute ground-state and excited-state probabilities, and compute the dipole expectation value. 

Solution. Let 

$$
x _ {0} = \frac {q E}{m \omega^ {2}}.
$$

Then 

$$
H = \frac {p ^ {2}}{2 m} + \frac {1}{2} m \omega^ {2} (x - x _ {0}) ^ {2} - \frac {1}{2} m \omega^ {2} x _ {0} ^ {2}.
$$

Let 

$$
A = - \frac {\mathrm {i}}{\hbar} x _ {0} p.
$$

Then $\mathrm{e}^{-A}x\mathrm{e}^{A} = x - x_{0}$ , and therefore 

$$
H = \mathrm {e} ^ {- A} H _ {0} \mathrm {e} ^ {A} + B, \qquad B = - \frac {q ^ {2} E ^ {2}}{2 m \omega^ {2}}.
$$

The spectrum is 

$$
E _ {n} = \hbar \omega \left(n + \frac {1}{2}\right) - \frac {q ^ {2} E ^ {2}}{2 m \omega^ {2}}.
$$

The eigenstates are translated oscillator eigenstates. 

In terms of 

$$
p = \mathrm {i} \sqrt {\frac {m \hbar \omega}{2}} (a ^ {\dagger} - a),
$$

one has 

$$
A = x _ {0} \sqrt {\frac {m \omega}{2 \hbar}} (a ^ {\dagger} - a) = d (a ^ {\dagger} - a), \qquad d = \frac {x _ {0}}{\sqrt {2} l}, \quad l = \sqrt {\frac {\hbar}{m \omega}}.
$$

The dynamics under the shifted oscillator turns the original ground state into a coherent state with amplitude 

$$
\alpha (t) = d (1 - \mathrm {e} ^ {- \mathrm {i} \omega t}).
$$

Therefore the probability of remaining in the original ground state of $H_0$ is 

$$
P _ {0 \rightarrow 0} (t) = \mathrm {e} ^ {- | \alpha (t) | ^ {2}} = \exp [ - 4 d ^ {2} \sin^ {2} (\omega t / 2) ].
$$

This equals 1 when 

$$
t = \frac {2 \pi N}{\omega}, \qquad N \in \mathbb {Z}.
$$

The probability of being in the first excited state of $H_{0}$ is 

$$
P _ {0 \rightarrow 1} (t) = | \alpha (t) | ^ {2} \mathrm {e} ^ {- | \alpha (t) | ^ {2}}.
$$

The probability of being in the ground state of the shifted Hamiltonian is time-independent and equals 

$$
\exp (- d ^ {2}),
$$

because the initial state is a coherent state relative to the shifted oscillator vacuum. 

The dipole operator is 

$$
d _ {\mathrm {o p}} = q x = q \sqrt {\frac {\hbar}{2 m \omega}} (a + a ^ {\dagger}).
$$

Thus 

$$
\langle d _ {\mathrm {o p}} (t) \rangle = q x _ {0} (1 - \cos \omega t).
$$

Classical-center interpretation. The expectation value follows the classical displaced equilibrium motion. The force shifts the equilibrium from 0 to $x_0 = qE / (m\omega^2)$ . If the particle initially sits in the old ground state, then the center of the wave packet has initial expectation $\langle x(0)\rangle = 0$ and $\langle p(0)\rangle = 0$ . The classical equation 

$$
m \ddot {x} + m \omega^ {2} x = q E
$$

with these initial data gives 

$$
\langle x (t) \rangle = x _ {0} (1 - \cos \omega t),
$$

which agrees with the coherent-state calculation. The quantum part of the problem determines the full number-state probability distribution around this moving center. 

**Higher viewpoint.** A constant electric field completes the square rather than changing the oscillator's intrinsic frequency. The spectrum is shifted uniformly downward, and the eigenstates are translated number states. Dynamically, an old ground state is not the new ground state; it is a coherent state relative to the shifted oscillator. The oscillating dipole moment is therefore the quantum expectation-value version of classical motion about the new equilibrium. 

## 4.4 Problem 4: The Ising model on a triangle

Problem statement. Three Ising spins on a triangle have energy 

$$
E = - J (\sigma_ {1} \sigma_ {2} + \sigma_ {2} \sigma_ {3} + \sigma_ {3} \sigma_ {1}) - h (\sigma_ {1} + \sigma_ {2} + \sigma_ {3}).
$$

Compute the partition function, free energy, entropy, specific heat at $h = 0$ , low- and high-temperature limits, magnetization, susceptibility, and low-temperature magnetization fluctuations. 

Solution. There are two fully aligned states with energies 

$$
E _ {+ + +} = - 3 J - 3 h, \quad E _ {- - -} = - 3 J + 3 h.
$$

There are three states with two spins up and one down, with energy $J - h$ , and three with one spin up and two down, with energy $J + h$ . Therefore 

$$
Z = 2 \mathrm {e} ^ {3 \beta J} \cosh (3 \beta h) + 6 \mathrm {e} ^ {- \beta J} \cosh (\beta h).
$$

The free energy is 

$$
F = - T \log Z,
$$

and the entropy is 

$$
S = - \frac {\partial F}{\partial T} = \log Z + T \frac {\partial}{\partial T} \log Z.
$$

At $h = 0$ 

$$
Z = 2 \mathrm {e} ^ {3 \beta J} + 6 \mathrm {e} ^ {- \beta J}.
$$

The mean energy and specific heat are 

$$
\langle E \rangle = \frac {- 6 J \mathrm {e} ^ {3 \beta J} + 6 J \mathrm {e} ^ {- \beta J}}{2 \mathrm {e} ^ {3 \beta J} + 6 \mathrm {e} ^ {- \beta J}},
$$

$$
C = \beta^ {2} (\langle E ^ {2} \rangle - \langle E \rangle^ {2}).
$$

For ferromagnetic $J > 0$ and $T \ll J$ , 

$$
C \sim 4 8 \frac {J ^ {2}}{T ^ {2}} \mathrm {e} ^ {- 4 J / T}.
$$

For $T\gg J$ 

$$
C \sim 3 \frac {J ^ {2}}{T ^ {2}}.
$$

The magnetization is 

$$
M = \left\langle \sigma_ {1} + \sigma_ {2} + \sigma_ {3} \right\rangle = \frac {6 \mathrm {e} ^ {3 \beta J} \sinh (3 \beta h) + 6 \mathrm {e} ^ {- \beta J} \sinh (\beta h)}{Z}.
$$

At low temperature, 

$$
M \simeq 3 \tanh (3 \beta h).
$$

Thus 

$$
\chi = \left. \frac {\partial M}{\partial h} \right| _ {h = 0} \simeq 9 \beta = \frac {9}{T}.
$$

At $h = 0$ and $T \ll J$ , the two ground states $M = \pm 3$ dominate equally, so 

$$
\left\langle \left(M - \langle M \rangle\right) ^ {2} \right\rangle \simeq 9.
$$

Degeneracy-table method. The computation is most transparent if the states are grouped by total magnetization $M = \sigma_{1} + \sigma_{2} + \sigma_{3}$ . The possible values are 

$$
M = 3, - 3, 1, - 1,
$$

with degeneracies 1, 1, 3, 3, respectively. For the aligned states, $\sigma_{1}\sigma_{2} + \sigma_{2}\sigma_{3} + \sigma_{3}\sigma_{1} = 3$ ; for the two-up-one-down and one-up-two-down states, this sum is $-1$ . Thus 

<table><tr><td>M</td><td>degeneracy</td><td>σ1σ2+ σ2σ3+ σ3σ1</td><td>E</td></tr><tr><td>3</td><td>1</td><td>3</td><td>-3J - 3h</td></tr><tr><td>-3</td><td>1</td><td>3</td><td>-3J + 3h</td></tr><tr><td>1</td><td>3</td><td>-1</td><td>J - h</td></tr><tr><td>-1</td><td>3</td><td>-1</td><td>J + h</td></tr></table>

Summing $g(M)\mathrm{e}^{-\beta E(M)}$ over this table immediately gives $Z$ , while differentiating $\log Z$ with respect to $h$ gives $M$ and $\chi$ . 

**Higher viewpoint.** The triangle Ising model is small enough to solve exactly, yet it already contains the key finite-size signature of ferromagnetism. At low temperature the two aligned states dominate, so the average magnetization vanishes at zero field by symmetry but its fluctuations are large. A tiny field selects one of the two sectors, producing a Curie-like susceptibility. The absence of a thermodynamic limit prevents a true singular phase transition. 

## 4.5 Problem 5: Gravitational waves from a binary black-hole system

Problem statement. Two point masses $m_{1}, m_{2}$ move in a circular Newtonian orbit of separation $r$ . Using the quadrupole amplitudes given in the problem, derive $h_{+}$ and $h_{\times}$ , the gravitational-wave frequency, the radiated power, the chirp $f(t)$ , the coalescence time, and estimate the initial separation for two $10M_{\odot}$ black holes to merge within $10^{10}$ years. 

Solution. Let 

$$
M = m _ {1} + m _ {2}, \qquad \mu = \frac {m _ {1} m _ {2}}{M}.
$$

The relative orbit has angular frequency 

$$
\Omega^ {2} = \frac {G M}{r ^ {3}}.
$$

The quadrupole formula gives 

$$
h _ {+} (t) = - \frac {4 G \mu r ^ {2} \Omega^ {2}}{c ^ {4} L} \frac {1 + \cos^ {2} \theta}{2} \cos (2 \Omega t),
$$

$$
h _ {\times} (t) = - \frac {4 G \mu r ^ {2} \Omega^ {2}}{c ^ {4} L} \cos \theta \sin (2 \Omega t),
$$

up to an irrelevant phase convention. The gravitational-wave frequency is 

$$
f = \frac {\Omega}{\pi}.
$$

The angle-averaged power is the standard quadrupole luminosity 

$$
P = \frac {3 2}{5} \frac {G ^ {4}}{c ^ {5}} \frac {\mu^ {2} M ^ {3}}{r ^ {5}}.
$$

Using the orbital energy 

$$
E = - \frac {G m _ {1} m _ {2}}{2 r}
$$

and energy balance $\dot{E} = -P$ , one obtains 

$$
\dot {r} = - \frac {6 4}{5} \frac {G ^ {3} m _ {1} m _ {2} M}{c ^ {5} r ^ {3}}.
$$

Therefore the coalescence time from initial separation $r_0$ is 

$$
T _ {C} = \frac {5 c ^ {5} r _ {0} ^ {4}}{2 5 6 G ^ {3} m _ {1} m _ {2} M}.
$$

Equivalently, in terms of the chirp mass 

$$
\mathcal {M} = \mu^ {3 / 5} M ^ {2 / 5},
$$

the frequency satisfies 

$$
\frac {\mathrm {d} f}{\mathrm {d} t} = \frac {9 6}{5} \pi^ {8 / 3} \left(\frac {G \mathcal {M}}{c ^ {3}}\right) ^ {5 / 3} f ^ {1 1 / 3}.
$$

Thus 

$$
f (t) = \left[ f _ {0} ^ {- 8 / 3} - \frac {2 5 6}{5} \pi^ {8 / 3} \left(\frac {G \mathcal {M}}{c ^ {3}}\right) ^ {5 / 3} (t - t _ {0}) \right] ^ {- 3 / 8}.
$$

For $m_{1} = m_{2} = 10M_{\odot}$ and $T\simeq 10^{10}$ years, 

$$
r _ {0} = \left(\frac {2 5 6 G ^ {3} m _ {1} m _ {2} M T}{5 c ^ {5}}\right) ^ {1 / 4} \simeq 0. 0 9 \mathrm {a u}.
$$

Thus the maximum initial separation is of order $10^{-1}$ astronomical units. 

Direct integration for the merger time. Starting from 

$$
\dot {r} = - \frac {6 4}{5} \frac {G ^ {3} m _ {1} m _ {2} M}{c ^ {5} r ^ {3}} = - \frac {A}{r ^ {3}},
$$

where $A = 64G^{3}m_{1}m_{2}M / (5c^{5})$ , integrate 

$$
r ^ {3} \mathrm {d} r = - A \mathrm {d} t.
$$

If $r(0) = r_0$ and $r(T_C) = 0$ , then 

$$
\frac {r _ {0} ^ {4}}{4} = A T _ {C},
$$

so 

$$
T _ {C} = \frac {r _ {0} ^ {4}}{4 A} = \frac {5 c ^ {5} r _ {0} ^ {4}}{2 5 6 G ^ {3} m _ {1} m _ {2} M}.
$$

The chirp formula follows by combining $f = \Omega / \pi$ with Kepler's law $\Omega^2 = GM / r^3$ , eliminating $r$ in favor of $f$ , and differentiating. This makes explicit why $\dot{f}$ is positive: loss of orbital energy decreases $r$ , and Kepler's law then increases $\Omega$ . 

**Higher viewpoint.** The gravitational-wave chirp is energy balance made observable. The quadrupole luminosity removes orbital binding energy, forcing the separation to decrease. Kepler's law then converts decreasing separation into increasing orbital and wave frequency. The chirp mass is the parameter combination that controls the leading frequency sweep, which is why gravitational-wave observations can measure it so accurately even before detailed modeling of the final merger. 

## 4.6 Problem 6: The conformal scalar field

Problem statement. In natural units, study a massless scalar field under rigid and local Weyl rescalings. Determine the conformal weight, the Ricci scalar transformation, the conformal coupling $\xi$ , and the effective mass in the metric 

$$
\mathrm {d} s ^ {2} = \frac {- \mathrm {d} \tau^ {2} + \mathrm {d} {\bf x} ^ {2}}{(H \tau) ^ {2}}.
$$

Solution. In four dimensions, under a constant metric scaling 

$$
\eta_ {\mu \nu} \mapsto \Omega^ {2} \eta_ {\mu \nu},
$$

we have $\sqrt{-\eta} \mapsto \Omega^4\sqrt{-\eta}$ and $\eta^{\mu \nu} \mapsto \Omega^{-2}\eta^{\mu \nu}$ . If 

$$
\phi \mapsto \widetilde {\phi} = \Omega^ {\Delta} \phi ,
$$

then the kinetic action scales as $\Omega^{4 - 2 + 2\Delta} = \Omega^{2 + 2\Delta}$ . Invariance requires 

$$
\Delta = - 1.
$$

For local $\Omega (x)$ , derivatives of $\Omega$ appear in $\partial_{\mu}(\Omega^{-1}\phi)$ , so the minimally coupled scalar action is not locally Weyl invariant. The Ricci scalar transforms in four dimensions as 

$$
\widetilde {R} = \Omega^ {- 2} \left(R - 6 \square \log \Omega - 6 (\nabla \log \Omega) ^ {2}\right).
$$

The locally Weyl-invariant action is obtained by adding the curvature coupling 

$$
S = \int \mathrm {d} ^ {4} x \sqrt {- g} \left[ \frac {1}{2} g ^ {\mu \nu} \partial_ {\mu} \phi \partial_ {\nu} \phi - \frac {1}{2} \xi R \phi^ {2} \right]
$$

with 

$$
\xi = \frac {1}{6}.
$$

For 

$$
\mathrm {d} s ^ {2} = a ^ {2} (\tau) (- \mathrm {d} \tau^ {2} + \mathrm {d} \mathbf {x} ^ {2}), \qquad a (\tau) = \frac {- 1}{H \tau},
$$

the Ricci scalar is 

$$
R = 1 2 H ^ {2}.
$$

The conformal coupling therefore contributes 

$$
m _ {\mathrm {e f f}} ^ {2} = \xi R = 2 H ^ {2}.
$$

Thus in this background the conformal scalar action may be read as that of a scalar with curvature-induced mass squared 

$$
m ^ {2} = 2 H ^ {2}
$$

with the sign convention of the action above. 

Field redefinition in conformal time. For a conformally flat metric $g_{\mu \nu} = a^{2}(\tau)\eta_{\mu \nu}$ , the conformally coupled massless scalar becomes especially simple after the rescaling 

$$
\chi = a \phi .
$$

When $\xi = 1/6$ , the terms involving $a'' / a$ cancel between the kinetic part and the curvature coupling, leaving the flat-space kinetic action for $\chi$ up to boundary terms. For de Sitter space with $a(\tau) = -1/(H\tau)$ , the curvature scalar is $R = 12H^2$ , so the original $\phi$ -description contains the curvature term $\xi R = 2H^2$ . The $\chi$ -description shows why this is not a genuine breaking of conformal invariance: it is exactly the masslike term required to compensate the expanding conformal factor. 

**Higher viewpoint.** Conformal coupling is not an optional decorative term; it is the unique curvature correction that makes a massless scalar compatible with local Weyl rescalings in four dimensions. In the original curved-space field variable it appears as an effective mass $\xi R$ , but after the conformal field redefinition it cancels the spurious curvature contribution generated by the scale factor. This is the basic reason conformally coupled massless fields in conformally flat backgrounds behave like flat-space fields after rescaling. 

# Chapter 5 -Index of Recurring Theorems and Methods

<table><tr><td>Tool or theorem</td><td>Main locations</td><td>Role in the solutions</td></tr><tr><td>Wigner theorem and anti-unitarity</td><td>2022 Problem 1</td><td>Explains why time reversal conjugates complex scalars.</td></tr><tr><td>Schwinger boson representation</td><td>2022 Problem 2</td><td>Turns oscillator degeneracy into irreducible su(2) representations.</td></tr><tr><td>Noether theorem</td><td>2022 Problems 3,5; 2023 Problem 1; 2024 Problem 1</td><td>Converts spacetime or internal symmetries into conserved quantities.</td></tr><tr><td>Killing equation and geodesic constants</td><td>2022 Problem 3; 2023 Problem 5; 2024 Problem 5</td><td>Produces conserved momenta and identifies spacetime symmetries.</td></tr><tr><td>Effective potentials</td><td>2024 Problem 1; 2025 Problem 1</td><td>Reduces radial or constrained motion to one-dimensional stability analysis.</td></tr><tr><td>Degenerate perturbation theory</td><td>2022 Problem 2; 2023 Problem 2</td><td>Diagonalizes perturbations inside degenerate eigenspaces.</td></tr><tr><td>Coherent states and displacement operators</td><td>2024 Problem 2; 2025 Problem 3</td><td>Solves forced or shifted oscillator dynamics.</td></tr><tr><td>Gauge invariance and Lorenz gauge</td><td>2023 Problem 3</td><td>Derives electromagnetic wave equations from potentials.</td></tr><tr><td>Skin-depth approximation</td><td>2024 Problem 3</td><td>Describes electromagnetic damping in good conductors.</td></tr><tr><td>Mean-field expansion</td><td>2024 Problem 4</td><td>Determines classical Ising critical exponents.</td></tr><tr><td>Dimensional regularization</td><td>2023 Problem 6; 2024 Problem 6</td><td>Extracts one-loop ultraviolet divergences.</td></tr><tr><td>Large-N counting</td><td>2022 Problem 6</td><td>Selects bubble-chain diagrams by index-loop powers.</td></tr><tr><td>Weyl transformations</td><td>2025 Problem 6</td><td>Determines conformal weights and curvature couplings.</td></tr><tr><td>Quadrupole radiation</td><td>2025 Problem 5</td><td>Produces gravitational-wave chirps and coalescence times.</td></tr></table>