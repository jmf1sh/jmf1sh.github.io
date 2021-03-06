+++
title = "Santalo Formula"
date = 2015-09-15
draft = false
categories = ["geometry"]
tags = ["inverse-problems"]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).

Let \\(M\\) be a simple Riemannian manifold with boundary \\(\partial M\\). For \\((x,v) \in SM\\), let \\(\tau(x,v)\\) denote the exit time of the geodesic starting at \\(x\\) with tangent vector \\(v\\), i.e. \\(\tau(x,v)\\) is the (necessarily unique, and finite) time at which \\(\exp_x(tv) \in \partial M\\).


We let \\(\partial_+(SM)\\) denote the set

\\[ \partial_+(SM) = \{ (x,v) \in SM \ | \ x \in \partial M, \langle v, \nu\rangle &gt; 0 \} \\]

where \\(\nu\\) denotes the inward unit normal to \\(\partial M\\) in \\(M\\). The exponential map identifies \\(SM\\) with the set

\\[ \Omega = \{ (x,v,t) \in \partial_+(SM) \times \mathbf{R} \ | \ 0 \leq t \leq \tau(x,v)  \}, \\]

via \\((x,v,t) \mapsto \exp_x(tv)\\). Let \\(\Phi: \Omega \to M\\) denote this diffeomorphism. Then we have, for all \\(f \in C^\infty(SM)\\)

\\[ \\begin{aligned}
\int_{SM} f dvol(SM) &= \int_\Omega (\Phi^\ast f) (\Phi^\ast dvol(SM)) \cr
&= \int_{\partial_+(SM)} \int_0^{\tau(x,v)} f(\phi_t(x,v)) \Phi^\ast dvol(SM).
\\end{aligned} \\]

Therefore, we can compute integrals of functions over \\(SM\\) by integrating along geodesics, provided that we can cmopute \\(\Phi^\ast dvol(SM)\\). This is the content of the Santalo formula.

Theorem (Santalo formula). For all \\(f \in C^\infty(SM)\\), we have

\\[ \int_{SM} f dvol(SM) = \int_{\partial_+(SM)} \int_0^{\tau(x,v)} f(\phi_t(x,v)) \langle v, \nu\rangle dt dvol(\partial(SM)) \\]


Proof. Necessarily, we must have

\\[ \Phi^\ast(dvol(SM)) = a(x,v) dt \wedge dvol(\partial(SM))), \\]

for some function \\(a(x,v)\\). The reason we can assume that \\(a\\) is independent of \\(t\\) is that \\(\Phi\\) is defined via geodesic flow, and geodesic flow preserves the volume form on \\(SM\\). To compute the factor \\(a(x,v)\\), we just need to compute

\\[ i_{\partial / \partial t} \Phi^\ast(dvol(SM)) = \Phi^\ast(i_{\Phi_\ast(\partial / \partial t)} dvol(SM)) \\]

From the definition of \\(\Phi\\), we have that \\(\Phi_\ast(\partial / \partial t)\\) is the Reeb vector field on \\(SM\\), i.e. the vector field generating geodesic flow. Therefore, \\(\Phi_\ast(\partial / \partial t)\\) is equal, at a point \\((x,v)\\) to the horizontal lift of the vector \\(v\\). Therefore, using the definition of the induced volume form on a hypersurface of a Riemannian manifold, we find

\\[ i_{\partial / \partial t} \Phi^\ast(dvol(SM)) = \langle v, \nu \rangle dvol(\partial(SM)) \\]

where \\(\nu\\) is the inward pointing unit normal to \\(\partial(SM)\\) in \\(SM\\). This shows that \\(a(x,v) = \langle v, \nu \rangle\\) and completes the proof.