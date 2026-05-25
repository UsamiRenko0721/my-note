
>[!question] 1.4
>1.4. 在粒子直径为 $D$ 的硬球所组成的经典气体中，粒子的空间分布已不再是无关联的。粗略地说，在该系统里由于 $j$ 个粒子的存在，仅仅剩下可供第 $(j+1)$ 个粒子占据的体积为 $(V - jv_0)$。显然，$v_0$ 将正比于 $D^3$。假设 $Nv_0 \ll V$，试确定 $\Omega(N, V, E)$ 对 $V$ 的依存关系（参见（1.4.1）式），并试证明：由于这个结果，在气体定律（1.4.3）式中的 $V$ 要用 $(V - b)$ 代替，其中 $b$ 等于粒子所占据的实际空间体积的四倍。

由题意，原本微观状态数是 $\Omega \propto V^{N}$ 现在就是
$$\Omega \propto V(V-v_{0})(V-2v_{0})\dots(V-Nv_{0}) $$
其中 $v_{0}=\frac{4\pi}{3}D^{3}$ 是单个粒子占据的空间的体积，即在该空间内不能有第二个粒子。而粒子实际空间体积是 $v_{s}=\frac{\pi}{6}D^{3}$ 。
$$\ln \Omega = C + N\ln V+\sum_{k=0}^{N}\ln\left( 1-\frac{kv_{0}}{V} \right) $$
由 $Nv_{0}\ll V$ 知有近似：
$$\begin{align}
\ln\Omega &\approx C + N\ln V + \sum_{k=0}^{N}\left( -\frac{kv_{0}}{V} \right) \\
&\approx C + N\ln V - \frac{N^{2}v_{0}}{2V} \\
 \\
S &= S_{0}(V,E) + kN\ln V - \frac{kN^{2}v_{0}}{2V}
\end{align} $$
于是
$$P = \frac{1}{T} \frac{\partial S}{\partial V} = \frac{NkT}{V}\left(  1+\frac{Nv_{0}}{2V}  \right) \approx \frac{NkT}{V - \frac{Nv_{0}}{2}} $$
$$b= \frac{Nv_{0}}{2} = \frac{2\pi}{3}ND^{3} = 4Nv_{s} $$

>[!question] 1.8
>1.8. 考虑一个微观实体的系统, 其能量本征值为:
>$$\varepsilon(n) = nh\nu; \quad n = 0, 1, 2, \cdots.$$
当给定微观实体总数 $N$ 和总能量 $E$ 时, 试求该系统统计数 $\Omega$ 的渐近表示式。并确定该系统的温度 $T$ 与 $E/N$ 和 $h\nu$ 的函数关系。最后, 试讨论一下在极限 $E/(Nh\nu) \to \infty$ 时的情况。

共有 $N$ 个微观实体，而总能量为 $E$ ，设 $\{ n_{i} \}$ 为微观实体数量配置，则
$$\sum_{i=1}^{N} n_{i}h\nu = E $$
这是一个 $N$ 元的一次方程，解是不定的，解的个数就是微观状态数，记 $M=E /h\nu$ 则
$$\Omega = \frac{(M+N-1)!}{M!(N-1)!} \approx \frac{(M+N)!}{M!N!} \approx \frac{1}{\sqrt{ 2\pi }} \frac{(M+N)^{M+N}}{M^{M}N^{N}} \sqrt{ \frac{M+N}{MN} } $$
于是
$$\frac{1}{kT} = \frac{\partial \ln \Omega}{\partial E} = \frac{1}{h\nu} \frac{\partial \ln \Omega}{\partial M} = \frac{1}{h\nu}\left[  \ln\left( 1+\frac{M}{N} \right) - \frac{M}{2M(M+N)} \right] $$
其中 $\dfrac{N}{M(M+N)}\sim \mathcal{O}\left( \dfrac{N}{E^{2}} \right)\text{ or }\mathcal{O}\left( \dfrac{1}{E} \right)$ 当 $\mathcal{O}(N)<\mathcal{O}(E)$ 时取前者，当 $\mathcal{O}(N)<\mathcal{O}(E)$ 时取后者，无论哪种情况都是对数阶大所以
$$\frac{h\nu}{kT} \approx \ln\left( 1+\frac{N}{M} \right) ,\quad kT = \frac{h\nu}{\ln\left( 1+\dfrac{Nh\nu}{E} \right)} $$
于是
$$\frac{E}{Nh\nu} = \frac{1}{\exp\left( \dfrac{h\nu}{kT} \right) - 1} \to \frac{kT}{h\nu} ,\quad E\approx NkT $$
回归经典情况


>[!question] 1.9
1.9. 利用热力学系统的熵 $S(N, V, E)$ 是广延量的特点，试证明：
$$N \left( \frac{\partial S}{\partial N} \right)_{V,E} + V \left( \frac{\partial S}{\partial V} \right)_{V,E} + E \left( \frac{\partial S}{\partial E} \right)_{N,V} = S$$
注意到，这个结果隐含有：$(-N\mu + PV + E)/T = S$，即 $N\mu = E + PV - TS$，这是热力学中一个著名的关系。

由于 $S$ 是广延量所以考虑 $\lambda$ 个一样的系统 $(N,V,E)$ 将他们合并则 
$$S(\lambda N,\lambda V,\lambda E) = \lambda S(N,V,E) $$
可见 $S$ 是 $N,V,E$ 的一阶齐次函数，所以由欧拉齐次定理有
$$N \frac{\partial S}{\partial N} + V\frac{\partial S}{\partial V} + E\frac{\partial S}{\partial E} = S $$
而有定义
$$ \frac{\partial S}{\partial E} = \frac{1}{T} , \quad \frac{\partial S}{\partial V} = - \frac{P}{T} , \quad\frac{\partial S}{\partial N} = \frac{\mu}{T} $$
所以
$$\mu N = E + PV - TS $$
