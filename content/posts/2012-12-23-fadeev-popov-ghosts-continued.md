+++
title = "Fadeev-Popov ghosts, continued"
date = 2012-12-23
draft = false
categories = ["uncategorized"]
tags = []
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Last time I sketched how we can represent an integral over a submanifold \\(M \subset \mathbb{R}^n\\) by an integral of the form

\\[ \int_{\mathbb{R}^n} f(x) \delta(G(x)) \exp\left(\bar{\eta}G(x+\eta) \right) d\eta d\bar{\eta} dx. \\]

Here, \\(\eta, \bar{\eta}\\) are Fermionic variables called Fadeev-Popov ghosts, which are introduced to cancel an unwanted determinant factor. The function \\(G(x)\\) singles out the submanifold \\(M\\) as \\(M = G^{-1}(0)\\).


Now suppose that we start with a vector (or affine) space \\(V\\), which is acted on by a group \\(H\\). We would like to undstand integrals over the quotient \\(V / H\\) in terms of integrals over \\(V\\). Suppose there is some function \\(G(x)\\) on \\(V\\) satisfying the following property:

* For each level \\(w\\) of \\(G\\), the subspace \\(M_w := G^{-1}(w)\\) intersects the orbits transversely, and furthermore every \\(H\\)-orbit intersects \\(M_w\\) exactly once. (*)

We call such a function a gauge-fixing function, and a level \\(w\\) a gauge-fixing. By assumption, we have \\(V/H \cong M_w\\) for any \\(w\\). Hence using the integral we derived last time, we can integrate over \\(M_w\\) for any particular choice of \\(w\\), and this ought to be the same as integrating over \\(V/H\\). The problem, however, is that in the QFT setting it's not clear what the Feynman rules should be for such a path integral. The final trick is that since the answer should be independent of \\(w\\), and by integrating over all possible \\(w\\) we obtain a Lagrangian from which we can derive sensible Feynman rules.


We have some integral


\\[Z = \int \delta(G(x) - w) \exp\left\\{\frac{i}{\hbar}S(x) + \bar{\eta}dG \eta\right\\} dx d\eta d\bar{\eta} \\]

which is independent of \\(w\\). So we add a Gaussian weight an integrate over \\(w\\):

\\[ \\begin{aligned}
Z' &= \int \delta(G(x) -w) \exp\left\\{\frac{i}{\hbar}S(x) + \bar{\eta}dG \eta - \frac{1}{2\xi} |w|^2\right\\}
 dx dw d\eta d\bar{\eta}\cr
&= \int \exp\left\\{\frac{i}{\hbar}S(x) + \bar{\eta}dG \eta - \frac{1}{2\xi} |G(x)|^2 \right\\} dx d\eta d\bar{\eta}.
\\end{aligned} \\]

Here, \\(\xi\\) is an arbitrary real positive constant, and we denote the new integral by \\(Z'\\) to indicate that it differs from the old path integral \\(Z\\) by (at most) an overall constant. Now the important thing is that the new action appear in the integrand of \\(Z'\\) is gauge-fixed and hence there is no problem whatsoever in deriving sensible, meaningful Feynman rules. The gauge-fixing term \\(|G(x)|^2\\) serves to make the action non-degenerate, so that propagators are well-defined, while the term involving the Fermions \\(\eta, \bar{\eta}\\) generates new Feynman rules that "cancel" the superfluous degrees of freedom due to gauge redundancy.


The question remains, what if we choose some other gauge-fixing function? i.e., what happens if we perturb \\(G(x)\\) to some new function satisfying property (*)? We'll answer this using the BRST formalism.
