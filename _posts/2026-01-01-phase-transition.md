---
title: "Phase Transition"
date: 2026-01-01
permalink: /study/phase-transition/
categories: study
---


If we vary temperature and pressure, a liquid can turn into a gas, with an accompanying change in density. This phenomenon is called a **phase transition**.  

## Ising Model

Consider the Ising model in $d$ dimensions on a hypercubic lattice of
side length $L$, with $$N = L^d$$ lattice sites. At each site $i$ there
is a spin variable $$s_i \in \{+1, -1\}.$$

The Hamiltonian is

$$H = -J \sum_{\langle i j \rangle} s_i s_j - B \sum_i s_i ,$$ 

where $\langle i j \rangle$ denotes nearest-neighbor pairs, $B$ is the external magnetic field.

The partition function is $$Z = \sum_{\{s_i\}} e^{-\beta H(\{s_i\})}.$$

Here $$\beta = \frac{1}{k_B T}$$ is the inverse temperature.

The average magnetization per site is
$$m = \langle s_i \rangle = \frac{1}{N} \sum_i \langle s_i \rangle .$$

The Ising model has a global $\mathbb{Z}_2$ symmetry corresponding to
$$s_i \rightarrow -s_i.$$


## Landau–Ginzburg Theory

We model the system with a coarse-grained field $m(x)$ that encodes
information about the spins $s_i$ in a neighborhood of position $x$.

The local free-energy functional consistent with $\mathbb{Z}_2$ symmetry
is 

$$F[m(\mathbf{x})]=\int d^d x\left[\frac{1}{2}\,\gamma(T)\, (\partial_\mu m)^2+ \frac{1}{2}\,\alpha_2(T)\, m^2+ \frac{1}{4}\,\alpha_4(T)\, m^4\right],$$ 

with $\alpha_4(T) > 0$ required for stability.

## Mean-Field Approximation

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

Define the *critical temperature* $T_c$ by $$a(T_c) = 0 .$$ This defines a
*second-order phase transition*.

### Second-Order Phase Transition

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

### Critical Exponent

Assume $$a(T) = a_0 (T - T_c),
\qquad
b(T) = b_0 > 0 .$$

Then for $T < T_c$, $$m_0 = \sqrt{\frac{a_0}{2b_0}} (T_c - T)^{\beta},\quad \beta = \frac{1}{2}.$$

Thus, mean field theory predicts the critical exponent
$$\beta = \frac{1}{2}.$$

## Correlation Functions

Mean-field theory does not capture spatial fluctuations. These
fluctuations are described by correlation functions
$$\langle \phi(x_1)\phi(x_2)\cdots\phi(x_n)\rangle ,$$ where we switch
notation from the magnetization $m$ to a scalar field $\phi$ to
emphasize the connection with quantum field theory.

Consider the Gaussian free energy in the presence of an external source
$J(x)$ (identified with the magnetic field): 

$$F_0[\phi]=\int d^d x\left[\frac{\gamma}{2} (\partial_\mu \phi)^2+\frac{\mu^2}{2}\phi^2-J(x)\phi(x)\right].$$

By Fourier transforming and completing the square in the Gaussian
functional integral, the generating functional is 

$$Z_0[J]=\int \mathcal D\phi \, e^{-\beta F_0[\phi]}=Z_0[0]\,\exp\!\left[\frac{\beta}{2}\int d^d x\, d^d y\;J(x)\, D_F(x-y)\, J(y)\right]$$

here the propagator is 

$$D_F(r)=\frac{1}{\gamma}\int \frac{d^d k}{(2\pi)^d}\frac{e^{i k \cdot r}}{k^2 + \xi^{-2}},\qquad r = x-y,$$ 

where $$\xi \equiv \sqrt{\frac{\gamma}{\mu^2}}$$ is the
*correlation length*.

By construction, $$\mu^2(T) \propto T - T_c$$,
this defines another critical exponent
$$\xi \sim (T - T_c)^{-\nu},
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

- At distances $r \gg \xi$, correlations decay exponentially, indicating
short-range order. 

- At distances $r \ll \xi$, correlations decay
algebraically, reflecting scale-invariant behavior.

Thus, the correlation length $\xi$ sets the characteristic length scale
of fluctuations in the system.


### upper critical dimension

The mean-field results hold in high dimensions but break down in low dimensions.
Recall the situation for \\(T < T_c\\).
In order to trust the mean-field approximation, these fluctuations must be small
compared to the background around which they fluctuate. 
$$
\langle \phi^2 \rangle \ll \langle \phi \rangle^2 \sim m_0^2 .
$$

To estimate the size of the fluctuations, note that correlations decay beyond the
correlation length \\(\xi\\). We therefore integrate the two-point function over a
ball of radius \\(\xi\\). 

The relevant dimensionless ratio is
$$
R
=
\frac{\displaystyle \int_0^\xi d^d x \, \langle \phi(x)\phi(0) \rangle}
{\displaystyle \int_0^\xi d^d x \, m_0^2}
\sim
\frac{1}{m_0^2 \xi^d}
\int_0^\xi dr \, r^{d-1} \frac{1}{r^{d-2}}
\sim
\frac{\xi^{2-d}}{m_0^2}.
$$

In order for mean-field theory to be reliable, we require
$$
R \ll 1 .
$$
This condition is known as the *Ginzburg criterion*.
As we approach the critical point, the correlation length diverges and the order
parameter vanishes. 

According to mean-field theory,
$$
m_0 \sim |T - T_c|^{1/2},
\qquad
\xi \sim |T - T_c|^{-1/2}.
$$
Substituting these scalings into the expression for \\(R\\), we find

$$
R \sim |T - T_c|^{(d-4)/2}.
$$

As \\(T \to T_c\\), mean-field theory is correct only if
$$
d > d_c = 4 .
$$
The dimension \\(d_c = 4\\) is the *upper critical dimension* for the Ising
universality class.

## Renormalization
The critical exponents we derived from mean-field method are correct for \\(d>4\\).
We are interested in dimension \\(d<4\\).


Consider the free energy functional with $$\phi^4$$ interaction term:

$$
F[\phi]
=
\int d^d x
\left[
\frac{1}{2}(\partial_\mu \phi)^2
+
\frac{1}{2}\mu_0^2 \phi^2
+
g_0 \phi^4
\right],
$$
where \\(\mu_0^2 \propto T - T_c\\) and \\(g_0 > 0\\).

**Mode splitting.**
Introduce an ultraviolet momentum cutoff \\(\Lambda\\).
We split the field into slow
and fast modes by choosing a rescaling factor \\(b>1\\):
$$
\phi(x) = \phi^-(x) + \phi^+(x),
$$
where

- *Slow (long-wavelength) modes*:
$$
\phi^-(x)
=
\int_{|k|<\Lambda/b}
\frac{d^d k}{(2\pi)^d}
\, e^{i k\cdot x} \, \tilde{\phi}(k),
$$
- *Fast (short-wavelength) modes*:
$$
\phi^+(x)
=
\int_{\Lambda/b \le |k| < \Lambda}
\frac{d^d k}{(2\pi)^d}
\, e^{i k\cdot x} \, \tilde{\phi}(k).
$$


Write the free energy as
$$
F[\phi]
=
F_0[\phi] + F_{\text{int}}[\phi],
$$
where
$$
F_0[\phi]
=
\int d^d x
\left[
\frac{1}{2}(\partial_\mu \phi)^2
+
\frac{1}{2}\mu_0^2 \phi^2
\right],
\qquad
F_{\text{int}}[\phi]
=
\int d^d x \, g_0 \phi^4 .
$$

Because \\(F_0\\) is quadratic, it splits additively:
$$
F_0[\phi^- + \phi^+]
=
F_0[\phi^-] + F_0[\phi^+].
$$

The partition function becomes
$
  Z
  =
  \int \mathcal{D}\phi^- \, \mathcal{D}\phi^+
  \exp\!\left[
  - F_0[\phi^-]
  - F_0[\phi^+]
  - F_{\text{int}}[\phi^- + \phi^+]
  \right].
$

Integrating out the fast modes defines an effective free energy \\(F'\\) for the
slow modes:
$$
Z
=
\int \mathcal{D}\phi^- \, e^{-F'[\phi^-]},
$$
with
$
  e^{-F'[\phi^-]}
  =
  e^{-F_0[\phi^-]}
  \int \mathcal{D}\phi^+
  \exp\!\left[
  - F_0[\phi^+]
  - F_{\text{int}}[\phi^- + \phi^+]
  \right].
$

Define expectation values with respect to the Gaussian measure
$$
\langle \mathcal{O} \rangle_+
=
\frac{1}{Z_0^+}
\int \mathcal{D}\phi^+ \,
\mathcal{O} \, e^{-F_0[\phi^+]}.
$$

Then
$
  F'[\phi^-]
  =
  F_0[\phi^-]
  -
  \ln \left\langle
  e^{-F_{\text{int}}[\phi^- + \phi^+]}
  \right\rangle_+ .
$

Expanding the logarithm using the cumulant (linked-cluster) expansion,
$
  \ln \left\langle
  e^{-F_{\text{int}}}
  \right\rangle_+
  =
  - \langle F_{\text{int}} \rangle_+
  +
  \frac{1}{2}
  \left(
  \langle F_{\text{int}}^2 \rangle_+
  -
  \langle F_{\text{int}} \rangle_+^2
  \right)
  -
  \frac{1}{3!}
  \langle F_{\text{int}}^3 \rangle_{+,c}
  + \cdots ,
$
where \\(\langle \cdots \rangle_{+,c}\\) denotes connected cumulants.

This expansion generates corrections to the mass, coupling constant, and higher
operators in the effective free energy for the slow modes. Iterating this procedure
leads to the Wilsonian renormalization-group flow.



\medskip
\noindent\textbf{Order \( g_0 \).}

We expand the interaction term:
\[
(\phi^- + \phi^+)^4
=
(\phi^-)^4
+ 4(\phi^-)^3 \phi^+
+ 6(\phi^-)^2 (\phi^+)^2
+ 4 \phi^- (\phi^+)^3
+ (\phi^+)^4 .
\]

\begin{itemize}
    \item \( (\phi^-)^4 \): contributes directly to the quartic coupling of slow modes.
    \item \( 4(\phi^-)^3 \phi^+ \): odd in \( \phi^+ \), vanishes under the Gaussian average.
    \item \( 6(\phi^-)^2 (\phi^+)^2 \): gives a nontrivial correction via contraction of fast modes.
    \item \( 4 \phi^- (\phi^+)^3 \): odd in \( \phi^+ \), vanishes.
    \item \( (\phi^+)^4 \): contributes only a constant shift to the free energy.
\end{itemize}

Thus, the only relevant contribution at order \( g_0 \) is
\[
\langle F_{\text{int}} \rangle_+
=
6 g_0
\int
\prod_{i=1}^4
\frac{d^d k_i}{(2\pi)^d}
\,
\phi^-(k_1)\phi^-(k_2)
\,
\langle \phi^+(k_3)\phi^+(k_4) \rangle_+
\,
(2\pi)^d
\delta^{(d)}\!\left(
\sum_{i=1}^4 k_i
\right).
\]

Using the Gaussian contraction
\[
\langle \phi^+(k)\phi^+(k') \rangle_+
=
(2\pi)^d
\delta^{(d)}(k+k')
\frac{1}{k^2 + \mu_0^2},
\qquad
\Lambda/b \le |k| < \Lambda,
\]

\[
\langle F_{\text{int}} \rangle_+
=
6 g_0
\int_{|k|<\Lambda/b}
\frac{d^d k}{(2\pi)^d}
\,
\phi^-(k)\phi^-(-k)
\int_{\Lambda/b}^{\Lambda}
\frac{d^d q}{(2\pi)^d}
\,
\frac{1}{q^2 + \mu_0^2}.
\]

This contribution renormalizes the mass term. After integrating out the fast modes
and rescaling momenta to restore the cutoff,
\[
k' = b k,
\qquad
\phi'(k') = b^{-(d+2)/2}\,\phi^-(k'/b),
\]
the effective couplings become
\[
\mu^2(b)
=
b^2
\left(
\mu_0^2
+
12 g_0
\int_{\Lambda/b}^{\Lambda}
\frac{d^d q}{(2\pi)^d}
\frac{1}{q^2 + \mu_0^2}
\right),
\]
\[
g(b)
=
b^{4-d} g_0 .
\]

Here the factor of \( b^2 \) arises from the canonical scaling dimension of the mass,
while the factor \( b^{4-d} \) reflects the scaling dimension of the quartic coupling.



\medskip
\noindent\textbf{Order \( g_0^2 \).}

At second order in the coupling, integrating out the fast modes generates
both a correction to the quartic coupling and a wavefunction renormalization.
After rescaling momenta to restore the cutoff,
\[
k' = b k,
\qquad
\phi'(k')
=
b^{-(d+2)/2}
\left(1 - g_0^2 A''(0,\Lambda)\right)^{-1}
\phi^-(k'/b),
\]
where \( A''(0,\Lambda) \) arises from the momentum-dependent part of the
two-loop diagrams.

The renormalized couplings after one RG step are
\[
\mu^2(b)
=
b^2
\left[
\mu_0^2
+
12 g_0
\int_{\Lambda/b}^{\Lambda}
\frac{d^d q}{(2\pi)^d}
\frac{1}{q^2 + \mu_0^2}
\right],
\]
\[
g(b)
=
b^{4-d}
\left[
g_0
-
36 g_0^2
\int_{\Lambda/b}^{\Lambda}
\frac{d^d q}{(2\pi)^d}
\frac{1}{(q^2 + \mu_0^2)^2}
\right].
\]

\medskip
\noindent\textbf{beta functions}

Instead of discrete steps \( \Lambda \to \Lambda/b \), we parametrize the
flow continuously by writing
\[
b = e^{s},
\qquad
\Lambda \to \Lambda e^{-s},
\]
with \( s \ll 1 \).

The scale dependence of the couplings defines the beta functions:
\[
\frac{d \mu^2}{d s} = \beta_{\mu^2}(\mu^2,g),
\qquad
\frac{d g}{d s} = \beta_g(\mu^2,g).
\]



Evaluating the shell integrals for \( d=4 \), one finds
\[
\frac{d \mu^2}{d s}
=
2 \mu^2
+
\frac{3 g}{2\pi^2}
\frac{\Lambda^4}{\Lambda^2 + \mu^2},
\]
\[
\frac{d g}{d s}
=
-\frac{9 g^2}{2\pi^2}
\frac{\Lambda^4}{(\Lambda^2 + \mu^2)^2}.
\]

In dimension \( d \ge 4 \), the RG flow decreases \( g \) and the \( \phi^4 \)
interaction is irrelevant, but for \( d < 4 \) the RG flow increases \( g \)
and the perturbative expansion is no longer valid.

To gain information about dimensions \( d < 4 \), we perform an
\textbf{\(\epsilon\)-expansion} about
\[
d = 4 - \epsilon .
\]
We introduce the dimensionless coupling
\[
\tilde g = \Lambda^{\epsilon} g .
\]

The beta functions become
\[
\frac{d\mu^2}{ds}
\simeq
2\mu^2
+
\frac{3}{2\pi^2}
\frac{\Lambda^4}{\Lambda^2+\mu^2}\,\tilde g ,
\]
\[
\frac{d\tilde g}{ds}
\simeq
\epsilon\,\tilde g
-
\frac{9}{2\pi^2}
\frac{\Lambda^4}{(\Lambda^2+\mu^2)^2}\,\tilde g^{\,2} .
\]
and they have two fixed points:
\begin{itemize}
\item \textbf{Gaussian fixed point:}
\[
\mu^2 = 0,
\qquad
\tilde g = 0 .
\]

\item \textbf{Wilson--Fisher fixed point:}
\[
\mu_*^2
=
-\frac{3}{4\pi^2}
\frac{\Lambda^4}{\Lambda^2+\mu_*^2}\,\tilde g_*,
\qquad
\tilde g_*
=
\frac{2\pi^2}{9}
\frac{(\Lambda^2+\mu_*^2)^2}{\Lambda^4}\,\epsilon .
\]
Since we are working to leading order in \( \epsilon \), this gives
\[
\mu_*^2
=
-\frac{3}{4\pi^2}\,\Lambda^2 \tilde g_* = \frac{-\Lambda^2\epsilon}{6},
\qquad
\tilde g_*
=
\frac{2\pi^2}{9}\,\epsilon .
\]
\end{itemize}

We now linearize near the Wilson--Fisher fixed point by writing
\[
\mu^2 = \mu_*^2 + \delta\mu^2,
\qquad
\tilde g = \tilde g_* + \delta\tilde g .
\]
Linearizing the beta functions yields
\[
\frac{d}{ds}
\begin{pmatrix}
\delta\mu^2 \\
\delta\tilde g
\end{pmatrix}
=
\begin{pmatrix}
2 - \dfrac{\epsilon}{3} &
\dfrac{3\Lambda^2}{2\pi^2 }\left(1+\dfrac{\epsilon}{6}\right) \\[8pt]
0 & -\epsilon
\end{pmatrix}
\begin{pmatrix}
\delta\mu^2 \\
\delta\tilde g
\end{pmatrix}.
\]

The eigenvalues are
\[
\lambda_t = 2 - \frac{\epsilon}{3} + O(\epsilon^2),
\qquad
\lambda_g = -\epsilon + O(\epsilon^2).
\]

Thus, the Wilson--Fisher fixed point has one relevant direction and one
irrelevant direction.

\medskip
\noindent\textbf{Anomalous dimension.}

Mean-field theory predicts the two-point correlation function
\[
\langle \phi(x)\phi(0) \rangle
\sim
\frac{1}{|x|^{\,d-2}}.
\]
By dimensional analysis, this implies the scaling
\[
\phi \sim |x|^{-(d-2)/2}.
\]

In the renormalization group, under a scale transformation
\[
x \;\to\; x/b,
\]
the field rescales (in a complicated way) as
\[
\phi \;\to\; b^{\Delta_\phi}\,\phi,
\]
where
\[
\Delta_\phi = \frac{d-2+\eta}{2}
\]
is the scaling dimension of the field, and \( \eta \) is called the
\emph{anomalous dimension}, which is determined by RG calculation.

This leads to the critical-point correlation function
\[
\langle \phi(x)\phi(0) \rangle
\sim
\frac{1}{|x|^{\,d-2+\eta}}.
\]

From loop corrections in the \( \phi^4 \) theory, the anomalous dimension satisfies
\[
\eta = O(\epsilon^2),
\]
so to leading order we may set \( \eta \approx 0 \).

In dimension \( d = 4 - \epsilon \), the scaling dimension of the field is therefore
\[
\Delta_\phi
=
\frac{d - 2 + \eta}{2}
\approx
1 - \frac{\epsilon}{2}.
\]

\medskip
\noindent\textbf{Critical exponents.}

For \( d = 4 - \epsilon \), define the critical exponent \( \nu \) through the
divergence of the correlation length,
\[
\xi \sim t^{-\nu},
\qquad
t \equiv \frac{T - T_c}{T_c}.
\]
Since \( \xi \) has dimensions of length, under the RG rescaling
\( x \to x/b \) we have
\[
\xi \to \xi/b,
\qquad
\Delta_\xi = -1.
\]
Using \( \Delta_\xi = -\nu\,\Delta_t \), we obtain
\[
\nu = \frac{1}{\Delta_t}
= \frac{1}{2} + \frac{\epsilon}{12} + O(\epsilon^2).
\]

The order-parameter exponent \( \beta \) is defined by
\[
\phi \sim t^{\beta}.
\]
Relating this to scaling dimensions via
\(
\Delta_\phi = \beta\,\Delta_t
\),
we find
\[
\beta
=
\frac{1}{2}
-
\frac{\epsilon}{6}
+
O(\epsilon^2).
\]



Setting \( \epsilon = 1 \) for for $d=3$, we can compare mean-field,
RG (\(\epsilon\)-expansion), and numerical results:

\[
\begin{array}{c|ccc}
\text{Exponent}
& \text{Mean field}
& \text{RG }(\epsilon = 1)
& \text{Numerical} \\ \hline
\nu
& \tfrac{1}{2}
& 0.58
& 0.6300 \\
\beta
& \tfrac{1}{2}
& \tfrac{1}{3}
& 0.3264
\end{array}
\]
