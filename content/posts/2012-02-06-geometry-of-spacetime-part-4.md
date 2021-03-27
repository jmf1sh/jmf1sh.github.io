+++
title = "Geometry of curved spacetime, part 4"
date = 2012-02-06
draft = false
categories = ["geometry", "physics"]
tags = ["general-relativity"]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Today I had to try to explain connections and curvature in local frames (as opposed to coordinates), and I really feel that Wald's treatment of this is just awful (this is one of the few complaints I have with an otherwise classic textbook). It is particularly baffling since the treatment in Misner, Thorne, and Wheeler is just perfect. What follows is the modern math (as opposed to physics) point of view. This is more abstract than any introductory GR (or even Riemannian geometry) text I've seen, but in this case the abstraction absolutely clarifies and simplifies things.


Let \\(M\\) be a smooth manifold and suppose \\(E\\) is a smooth vector bundle over \\(M\\). A connection on \\(E\\) is a map \\(\nabla\\) taking sections of \\(E\\) to sections of \\(T^\ast M \otimes E\\), \\(\mathbb{R}\\)-linear and satisfying the Leibniz rule

\\[ \nabla(f\sigma) = df \otimes \sigma + f \nabla \sigma. \\]


Now consider the sheaf of \\(E\\)-valued \\(p\\)-forms on \\(M\\). Call it \\(\Omega^p(E)\\). Then we can extend the connection to a map

\\[ \nabla: \Omega^p(E) \to \Omega^{p+1}(E) \\]

via the Leibniz rule:

\\[ \nabla(\eta \otimes \sigma) = d\eta \otimes \sigma + (-1)^p \eta \wedge \nabla \sigma. \\]

Let us define the curvature \\(F\\) associated to a connection \\(\nabla\\) by the composition

\\[ F = \nabla^2: \Omega^p(E) \to \Omega^{p+2}(E). \\]


Claim \\(F\\) is \\(C^\infty\\)-linear, i.e. it is tensorial.


Proof

\\[ \\begin{aligned}
\nabla(\nabla(f \sigma)) &= \nabla( df \otimes \sigma + f \nabla \sigma) \cr
&= d^2 f \otimes \sigma - df \wedge \nabla \sigma + df \wedge \nabla \sigma + f \nabla^2 \sigma \cr
&= f \nabla^2 \sigma.
\\end{aligned} \\]


So far we have not made any additional choices (beyond \\(\nabla\\)). In order to
actually compute something locally, we have to make some choices. Let
\\(\hat{e}_a\\) be a frame, i.e. a local basis of sections of \\(E\\). Then
\\(\nabla \hat{e}_a\\) is an \\(E\\)-valued 1-form, hence it can be expressed as a sum

\\[ \nabla \hat{e}_a = \sum_b \omega_a^b \otimes \hat{e}_b \\]

where the coefficients \\(\omega_a^b\\) are 1-forms, often called the connection
1-forms. Let \\(\Omega\\) denote the matrix of 1-forms whose entries are exactly
\\(\omega_a^b\\).


Claim Let \\(\sigma = \sigma^a \hat{e}_a\\). Then we have

\\[ \nabla \sigma = d\sigma + \Omega \sigma. \\]


Proof The coefficients \\(\sigma^a\\) are functions (i.e. scalars), so
\\(\nabla \sigma^a = d\sigma^a\\). Using the Leibniz rule we have

\\[ \\begin{aligned}
\nabla(\sigma^a \hat{e}_a) &= (\nabla \sigma^a) \hat{e}_a + \sigma^a \nabla \hat{e}_a \cr
&= d\sigma^a \hat{e}_a + \sigma^a \omega_a^b \hat{e}_b \cr
&= d\sigma^a \hat{e}_a + \omega_c^a \sigma^c \hat{e}_a \cr
&= (d\sigma + \Omega \sigma)^a \hat{e}_a.
\\end{aligned} \\]


Claim The curvature satisfies \\(F = d\Omega - \Omega \wedge \Omega\\).


Proof Just apply the above formula twice using Leibniz.


Connection 1-forms from Christoffel symbols. Suppose now that we are in the
Riemannian setting and we already know the Christoffel symbols in some
coordinates. Then we can express our frame \\(\hat{e}_a\\) in terms of coordinate
vector fields, i.e.
\\[ \hat{e}_a = \hat{e}_a^i \frac{\partial}{\partial x^i} \\]
Then we have that
\\[
\nabla_j \hat{e}\_a^i = \frac{\partial \hat{e}\_a^i }{\partial x^j} + \Gamma^i\_{jk} \hat{e}\_a^k
\\]

So, as a vector-valued 1-form, we have
\\[
\nabla \hat{e} = \frac{\partial \hat{e}\_a^i}{\partial x^j} dx^j \otimes \frac{\partial}{\partial x^i} + \Gamma^i\_{jk} \hat{e}\_a^k dx^j \otimes \frac{\partial}{\partial x^i}.
\\]

Juggling things a bit using the metric, we find
\\[
\nabla \hat{e}\_a = \frac{\partial \hat{e}\_a^i}{\partial x^j} \hat{e}^b\_i dx^j \otimes \hat{e}\_b + \Gamma^i\_{jk} \hat{e}\_a^k \hat{e}\_i^b dx^j \otimes \hat{e}\_b.
\\]

So the connection 1-forms are given by
\\[
\omega\_a^b = \frac{\partial \hat{e}\_a^i}{\partial x^j} \hat{e}^b\_i dx^j + \Gamma^i\_{jk} \hat{e}\_a^k \hat{e}\_i^b dx^j.
\\]


To come later (if I ever get around to it): some explicit computations.