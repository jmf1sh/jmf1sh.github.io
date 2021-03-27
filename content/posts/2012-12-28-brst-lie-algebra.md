---
title: "BRST and Lie algebra cohomology"
date: 2012-12-28
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


We saw in previous posts that gauge-fixing is intimately related to BRST cohomology. Today I want to explain the underlying mathematical formalism, as it is actually something very well-known: Lie algebra cohomology. Let \\(\mathfrak{g}\\) be a Lie algebra and \\(M\\) a \\(\mathfrak{g}\\)-module. We will construct a cochain complex that computes the Lie algebra cohomology with values in \\(M\\), \\(H^i(\mathfrak{g}, M)\\). Out of thin air, we define

\\[ C^\ast(\mathfrak{g}, M) = M \otimes \wedge^\ast \mathfrak{g}^\ast. \\]

The grading is just the grading induced by the grading on \\(\wedge^\ast \mathfrak{g}^\ast\\), which we identify with the BRST ghost number. Let \\(e_i\\) be a basis for \\(M\\) and \\(T_a\\) be a basis for \\(\mathfrak{g}\\), with canonical dual basis \\(S^a\\). The differential is defined on generators to be

\\[ d e_i = \rho(T_a) e_i \otimes S^a \\]

\\[ d S^a = \frac{1}{2} f^a_{bc} S^b \wedge S^c \\]

where \\(\rho: \mathfrak{g} \to \mathrm{End}(M)\\) is the representation and \\(f^a_{bc}\\) are the structure constants of the group. This differential is then extended to satisfy the graded Leibniz rule, and is easily verified to satisfy \\(d^2 = 0\\) (this is just the Jacobi identity). The Lie algebra cohomology is just the cohomology of this cochain complex. Essentially by definition, we see that

\\[ H^0(\mathfrak{g}, M) = \{m \in M \ | \ \xi \cdot m = 0 \ \forall \ \xi \in \mathfrak{g} \}, \\]

i.e. \\(H^0(\cdot) = (\cdot)^\mathfrak{g}\\) is the invariants functor. In fact, this can be taken to be the defining property of Lie algebra cohomology:


Theorem \\(H^k(\mathfrak{g}, M) = R^k (M)^\mathfrak{g}\\).


Returning to field theory, we see (modulo some hard technicalities!) that, roughly, \\(\mathfrak{g}\\) is the Lie algebra of infinitesimal gauge transformations, and \\(M\\) is the algebra of functions on the space of all connections. The ghost and anti-ghost fields can then be seen to be the multiplication and contraction operators. To wit, we can take \\(c^a\\) to be the operator

\\[ c^a: f \mapsto S^a \wedge f \\]

and take \\(\bar{c}^a\\) to be the operator

\\[ \bar{c}^a: f \mapsto \frac{\partial}{\partial S^a} f  = T_a \lrcorner f.\\]

Then we have

\\[ [c^a, \bar{c}^b] = \delta^{ab} \\]

so that \\(\bar{c}\\) is indeed the antifield of \\(c\\).