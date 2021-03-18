---
title: "Geometry of curved spacetime, part 5"
date: 2012-02-25
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Background


Following last time, we are almost ready to write down the Einstein equations. Before doing any math, let's understand what we're trying to do. Minkowski realized that Einstein's special relativity was best understood by combining space and time into 4-dimensional spacetime, with Lorentzian metric

$$ ds^2 = -dt^2 + dx^2 + dy^2 + dz^2. $$

The spacetime approach works wonderfully and even explains the Lorentz invariance of Maxwell's equations (indeed, it was Maxwell's equations that motivated Einstein to postulate his principle of relativity). However, (for reasons that I may discuss later) gravity is not a "force" but rather the geometry of spacetime itself.


By mass-energy equivalence (which is one of the most basic consequences of relativity), the gravitational field, whatever it is, must couple to the stress-energy tensor $T_{ij}$. I won't get into details, but the stress-energy tensor is a familiar object from physics that roughly tells you what the energy-momentum density/flux is in each direction at every point in spacetime. If the matter is completely static, then it is ok to think of this as measuring the mass density, but for nonstatic matter it also takes things like pressure into account.


Now, as I said above, the gravitational field is just the geometry of spacetime, which is measured by the metric tensor $g_{ij}$. Mass-energy equivalence says that it must couple to the stress-energy tensor $T_{ij}$. The simplest field equation then would be

$$ G_{ij} = c T_{ij} $$

where $G_{ij}$ is some tensor built out of $g_{ij}$ and its derivatives, and $c$ is some constant. The equations of Newtonian gravity are 2nd order in the gravitational field, so if we want these equations to reduce to Newton's in the appropriate limit, $G_{ij}$ should only depend on the metric and its first two derivatives. Now there is an obvious 2nd rank tensor satisfying these constraints: $R_{ij}$, the Ricci tensor. However, this turns out to be completely wrong (except in the vacuum).


Any reasonable matter will satisfy local energy-momentum conservation,

$$ \nabla_j T^{ij} = 0. $$

It turns out that the Ricci tensor does not satisfy this condition in general. So to look for the right tensor $G_{ij}$, we turn to the Bianchi identity.


The Bianchi Identity


As discussed in the previous post, the curvature of a connection is the endomorphism-valued 2-form

$$ F = d\Omega - \Omega \wedge \Omega $$

where $\Omega$ is the matrix of 1-forms telling us how to take the covariant derivative of a frame, i.e.

$$ \nabla_i e_j = \Omega_{ij} \otimes e_j. $$

Since a connection can be extended to all tensor powers in a natural way, we can consider the covariant derivative of the curvature $F$ (thought of as a section of the appropriate bundle). Quick calcluation:

\\begin{align}

\nabla F &= \nabla(d\Omega - \Omega \wedge \Omega) \\\

&= d^2 \Omega - d\Omega \wedge \Omega + \Omega \wedge d\Omega \\\

& \ \ + d\Omega \wedge \Omega - \Omega \wedge \Omega \wedge \Omega \\\

& \ \ - \Omega \wedge d\Omega + \Omega \wedge \Omega \wedge \Omega \\\

&= 0.

\\end{align}

Thus the endomorphism valued 3-form $\nabla F$ is identically 0. Writing $F$ in components as $R_{ijkl}$, this is equivalent to

$$ R_{ijkl|m} +  R_{ijlm|k} + R_{ijmk|l} = 0. $$

Now let's contract:

\\begin{align}

0 &= g^{ik} g^{jl} R_{ijkl|m} + g^{ik} g^{jl} R_{ijlm|k} + g^{ik} g^{jl} R_{ijmk|l}\\\

&= g^{ik} R_{ik|m} - g^{ik}R_{im|k} - g^{jl} R_{jm|l} \\\

&= \nabla_m S - 2 \nabla^k R_{mk}

\\end{align}

So we see that the tensor

$$ G_{ij} = R_{ij} - \frac{S}{2} g_{ij} $$

is divergence free. This yields the Einstein field equations:

$$ R_{ij} - \frac{S}{2} g_{ij} = c T_{ij}. $$

Actually, there is another obvious divergence free tensor: $g_{ij}$ itself. So a more general form is

$$ G_{ij} + \Lambda g_{ij} = c T_{ij} $$

where $\Lambda$ is a constant called the cosmological constant.