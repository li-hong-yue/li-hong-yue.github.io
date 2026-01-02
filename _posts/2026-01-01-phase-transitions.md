---
title: "Phase Transitions"
date: 2026-01-01
permalink: /study/phase-transitions/
categories: study
---


If we vary temperature and pressure, a liquid can turn into a gas, with an accompanying change in density. This phenomenon is called a **phase transition**.  

## Ising Model

Consider the Ising model in $d$ dimensions on a hypercubic lattice of
side length $L$, with $$N = L^d$$ lattice sites. At each site $i$ there
is a spin variable $$s_i \in \{+1, -1\}.$$

The Hamiltonian is
$$H = -J \sum_{\langle i j \rangle} s_i s_j - B \sum_i s_i ,$$ where:

-   $\langle i j \rangle$ denotes nearest-neighbor pairs,

-   $B$ is the external magnetic field.

The partition function is $$Z = \sum_{\{s_i\}} e^{-\beta H(\{s_i\})}.$$

Here $$\beta = \frac{1}{k_B T}$$ is the inverse temperature.

The average magnetization per site is
$$m = \langle s_i \rangle = \frac{1}{N} \sum_i \langle s_i \rangle .$$

The Ising model has a global $\mathbb{Z}_2$ symmetry corresponding to
$$s_i \rightarrow -s_i \quad \forall i .$$


## Landau–Ginzburg Theory

We model the system with a coarse-grained field $m(x)$ that encodes
information about the spins $s_i$ in a neighborhood of position $x$.

The local free-energy functional consistent with $\mathbb{Z}_2$ symmetry
is $$F[m(\mathbf{x})]
=
\int d^d x
\left[
\frac{1}{2}\,\gamma(T)\, (\partial_\mu m)^2
+ \frac{1}{2}\,\alpha_2(T)\, m^2
+ \frac{1}{4}\,\alpha_4(T)\, m^4
\right],$$ with $\alpha_4(T) > 0$ required for stability.

\## Mean-Field Approximation

Assume that fluctuations are small, so that $$m(x) = m$$ is spatially
uniform.

In Landau theory, the free energy can then be written as
$$F(T,m) = F_0(T) + a(T)m^2 + b(T)m^4 + \cdots .$$

The equilibrium condition $$\frac{\partial F}{\partial m} = 0$$ gives
$$2a(T)m + 4b(T)m^3 = 0 .$$

-   If $a(T) > 0$, the only solution is $$m = 0 ,$$ corresponding to the
    symmetric phase.

-   If $a(T) < 0$, there are two symmetry-related solutions
    $$m = \pm m_0,
    \qquad
    m_0 = \sqrt{\frac{-a(T)}{2b(T)}} .$$

Define the critical temperature $T_c$ by $$a(T_c) = 0 .$$ This defines a
\*second-order phase transition\*.

\### Second-Order Phase Transition

Substituting the equilibrium magnetization into the free energy gives
$$F(T) =
\begin{cases}
F_0(T), & T > T_c, \\[6pt]
F_0(T) - \dfrac{a(T)^2}{4b(T)}, & T < T_c .
\end{cases}$$

Thus, $F(T)$ is continuous at $T = T_c$.

The entropy is $$S(T) = -\frac{\partial F}{\partial T}.$$

Since $a(T_c) = 0$, the entropy is also continuous at $T = T_c$.

The heat capacity is $$C(T) = T \frac{\partial S}{\partial T}
= -T \frac{\partial^2 F}{\partial T^2}.$$

Because $F(T)$ has different second derivatives above and below $T_c$,
the heat capacity has a finite discontinuity at $T = T_c$, which is the
hallmark of a second-order phase transition.

\### Critical Exponent

Assume $$a(T) = a_0 (T - T_c),
\qquad
b(T) = b_0 > 0 .$$

Then for $T < T_c$, $$m_0 = \sqrt{\frac{a_0}{2b_0}} (T_c - T)^{1/2}.$$

Thus, Landau theory predicts the critical exponent
$$\beta = \frac{1}{2}.$$

\## Correlation Functions

Mean-field theory does not capture spatial fluctuations. These
fluctuations are described by correlation functions
$$\langle \phi(x_1)\phi(x_2)\cdots\phi(x_n)\rangle ,$$ where we switch
notation from the magnetization $m$ to a scalar field $\phi$ to
emphasize the connection with quantum field theory.

Consider the Gaussian free energy in the presence of an external source
$J(x)$ (identified with the magnetic field): $$F_0[\phi]
=
\int d^d x
\left[
\frac{\gamma}{2} (\partial_\mu \phi)^2
+
\frac{\mu^2}{2} \phi^2
-
J(x)\phi(x)
\right].$$

By Fourier transforming and completing the square in the Gaussian
functional integral, the generating functional is $$Z_0[J]
=
\int \mathcal D\phi \, e^{-\beta F_0[\phi]}
=
Z_0[0]\,
\exp\!\left[
\frac{\beta}{2}
\int d^d x\, d^d y\;
J(x)\, D_F(x-y)\, J(y)
\right].$$

The propagator $D_F(x-y)$ is $$D_F(r)
=
\frac{1}{\gamma}
\int \frac{d^d k}{(2\pi)^d}
\frac{e^{i k \cdot r}}{k^2 + \xi^{-2}},
\qquad
r = x-y,$$ where $$\xi \equiv \sqrt{\frac{\gamma}{\mu^2}}$$ is the
correlation length.

By construction, $$\mu^2(T) \propto T - T_c,
\qquad
\xi \sim (T - T_c)^{-\nu},
\quad
\nu = \frac{1}{2}.$$

Arbitrary correlation functions are obtained by functional
differentiation: $$\langle \phi(x)\phi(y)\rangle
=
\frac{1}{\beta^2}
\left.
\frac{\delta^2 \log Z_0[J]}
{\delta J(x)\,\delta J(y)}
\right|_{J=0}
=
\frac{1}{\beta}\, D_F(x-y).$$

Using saddle-point analysis and properties of Bessel functions, the
asymptotic behavior is $$\langle \phi(x)\phi(y)\rangle
\sim
\begin{cases}
\dfrac{1}{r^{\,d-2}}, & r \ll \xi, \\[8pt]
\dfrac{e^{-r/\xi}}{r^{(d-1)/2}}, & r \gg \xi,
\end{cases}
\qquad
r = |x-y|.$$

At distances $r \gg \xi$, correlations decay exponentially, indicating
short-range order. At distances $r \ll \xi$, correlations decay
algebraically, reflecting scale-invariant behavior.

Thus, the correlation length $\xi$ sets the characteristic length scale
of fluctuations in the system.
