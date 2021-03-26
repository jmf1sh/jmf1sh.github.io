---
title: "Fadeev-Popov ghosts"
date: 2012-12-21
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Today I want to review the Fadeev-Popov procedure, with a view toward BRST and eventually BV.


Gauge-Invariance and Gauge-Fixing


First we'll review the Fedeev-Popov method, to motivate the introduction of ghosts. Suppose we have a gauge theory involving a $G$-connection $A$ and some field $\phi$ charged under $G$. Under a gauge transformation $g(x)$, $\phi$ transforms as

$$ \phi \mapsto g \cdot \phi. $$

We would like that the covariant derivative transforms in the same way, i.e.

$$ \nabla \phi \mapsto g \nabla \phi. $$

In terms of the connection 1-form $A$, the covariant derivative is

$$ \nabla = d + A. $$

Let $\nabla'$ denote the gauge-transformed covariant derivative, and $\phi'$ the gauge-transformed field. Then we want

$$ \nabla' \phi' = g \nabla \phi. $$

We compute

\\begin{align}
\nabla' \phi' &= (d + A')(g \phi) \\\\\\
&= dg \phi + g d\phi + A'(g\phi) \\\\\\
&= gg^{-1}dg \phi + gd\phi + g g^{-1} A' g\phi \\\\\\
&= g(d\phi + g^{-1} A' g \phi + g^{-1} dg \phi \\\\\\
&= g(d\phi + A\phi)
\\end{align}

Comparing terms, we see that

$$ A = g^{-1} A' g + g^{-1} dg, $$

so upon re-arranging we have

$$ A' = g A g^{-1} - dg g^{-1} $$


This causes a problem: at critical points of the action, the Hessian of the action is degenerate in directions tangent to the gauge orbits. This means that the propagator is not well-defined, and there is no obvious way to derive the Feynman rules for perturbation theory. The solution is to take the quotient by gauge-transformations. To do this, we pick some gauge-fixing function $G(A)$ which ought to be transverse to the orbits. Then we can restrict to the space $G(A) = 0$, on which the Hessian of the action is non-degenerate, leading to a well-defined propagator. Formally, the path integral is

$$ Z = \int_{\{G(A) = 0\}} \exp{\frac{i}{\hbar} S[A, \phi]} \mathcal{D}A \mathcal{D}\phi  $$

Formally, this suggests that the path integral should be something like

$$ Z = \int \delta(G(A)) \exp{\frac{i}{\hbar} S[A, \phi]} \mathcal{D}A \mathcal{D}\phi, $$

but this is not quite right! To understand the source of the problem, we'll first study the finite-dimensional case and then use this to solve the problem in infinite-dimensions.



The Fadeev-Popov Determinant


Suppose we are on $\mathbb{R}^n$, and we would like to integrate a function $f(x)$ over a submanifold $M$ defined by $M = G^{-1}(0)$ for some smooth function $G: \mathbb{R}^n \to \mathbb{R}^k$. Naively, we might expect that the answer is

$$ \int_M f(x) \stackrel{?}{=} \int f(x) \delta(G(x)) dx. $$

To see why this is not correct, write the delta function as

$$ \delta(G(x)) = \frac{1}{(2\pi)^k}\int e^{ip\cdot G(x)} d^k p. $$

We can regularize this by taking the limit as $\epsilon \to 0$ of

$$ \frac{1}{(2\pi)^k}\int \exp\left\\{ip\cdot G(x) -\frac{\epsilon}{2} |p|^2\right\\} d^k p $$

This integral is Gaussian, so we obtain explicitly

$$ \left(\frac{2\pi}{\epsilon} \right)^{\frac{k}{2}} \exp\left\\{-\frac{1}{2\epsilon} |G(x)|^2 \right\\}. $$

So our original guess becomes

$$ \left(\frac{1}{2\pi \epsilon}\right)^\frac{k}{2} \int f(x) \exp\left\\{ -\frac{1}{2\epsilon} |G(x)|^2 \right\\} dx .$$

As $\epsilon \to 0$, this integral localizes on the locus $\{G(x) = 0\}$, as desired, but does not give the right answer! To see this, let $u$ be a coordinate on $M = G^{-1}(0)$ and $v$ coordinates normal to $M$. Then we have

$$ G(x) = G(u,v) = v^T H(u) v + o(|v|^3) $$

where $H(x)$ is the Hessian of $|G|^2$ at the point $x = (u, 0)$. So the integral becomes (as $\epsilon \to 0$)

\\begin{align}
I_\epsilon &= \left(\frac{1}{2\pi \epsilon}\right)^\frac{k}{2} \int\int
 f(u, v) \exp\left\\{ -\frac{1}{2\epsilon} v^T H(u) v \right\\} du dv \\\\\\
&= \int_M \frac{f(u)}{\sqrt{\det H(u)}} du.
\\end{align}

This is not correct. We have to account for the determinant of the Hessian. Now, the Hessian is given by

\\begin{align}
H_{ij} &= \frac{1}{2} \frac{\partial^2 |G|^2}{\partial v^i \partial v^j} \\\\\\
&= \frac{\partial}{\partial v^i} \left( G^a \partial_j G^a \right) \\\\\\
&=  \left(\partial_i G^a \partial_j G^a + G^a \partial_{ij} G^a \right) \\\\\\
&=  \partial_i G^a \partial_j G^a
\\end{align}

where we have used the fact that $G = 0$ on $x = (u, 0)$. Hence we see that

$$ \det H = (\det A)^2 $$

where $A$ is the $k \times k$ matrix with entries $\partial_i G^a$. Hence

$$ \sqrt{\det H} = \det A. $$

Now there is a straightforward way to eliminate the determinant. We introduce Fermionic coordinates $\eta^i, \theta^i$, $i = 1, \ldots, k$. Then by Berezin integration, we have

$$ \int e^{\eta^i G^i(0, \theta^j)} d\theta d\eta = \det A. $$

So in the end, we find

$$ \int_M f(x) d\mu = \int_{\mathbb{R}^n}
f(x) \delta(G(x)) \exp\left(\eta \cdot G(x+ \theta) \right)
 dx d\theta d\eta. $$
