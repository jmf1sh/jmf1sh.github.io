+++
title = "Virasoro algebra"
date = 2014-02-23
draft = false
categories = ["uncategorized"]
tags = []
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


 Conformal Invariance in 2D

To begin, recall that in two dimensions, the conformal transformations are generated by holomorphic and anti-holomorphic transformations. At the infinitesimal level, let \\(\ell\_n := -z^{n+1} \partial\_z\\) be a basis of holomorphic vector fields. These satisfy the Witt algebra

\\[ [\ell_m, \ell_n] = (m-n)\ell_{m+n}. \\]

Similarly, we can define \\(\bar{\ell}\_m = -\bar{z}^{n+1} \partial\_{\bar{z}}\\), and in addition to the Witt algebra these new generators satisfy \\([\bar{\ell}\_m, \ell\_n]=0\\).


Now, we could try to define a 2D conformal quantum field theory to be a unitary representation of the Witt algebra (or rather, of two copies of the Witt algebra, since we have both holomorphic and anti-holomorphic vector fields--but nevermind that). But this is too naive.



Central Extensions

Recall that in quantum mechanics, states are represented by vectors in some Hilbert space \\(\mathcal{H}\\). However, the state \\(|\phi\rangle\\) and \\(\alpha|\phi\rangle\\) are physically equivalent for any non-zero complex number \\(\alpha\\). The reason, of course, is that the expectation value of an operator \\(\mathcal{O}\\) is defined to be \\(\langle \phi|\mathcal{O}|\phi\rangle / \langle \phi|\phi\rangle\\), and such expressions are invariant under rescaling in \\(\mathcal{H}\\).


Thus,  a symmetry group \\(G\\) for a theory does not necessarily act via a map \\(G \to U(\mathcal{H})\\). It suffices to have a projective representation \\(G \to PU(\mathcal{H})\\). Let \\(\mathfrak{g}, \mathfrak{pu}\\) be the Lie algebras of \\(G\\) and \\(PU\\), respectively. A projective representation gives a map

\\[ \mathfrak{g} \to \mathfrak{pu}. \\]

Since \\(PU\\) is a quotient of \\(U\\), we have a short exact sequence

\\[ 0 \to \mathbb{C} \to \mathfrak{u} \to \mathfrak{pu} \to 0. \\]

Now let \\(\hat{\mathfrak{g}}\\) be defined as

\\[ \hat{\mathfrak{g}} = \{ (\xi, \eta) \in \mathfrak{u}\oplus\mathfrak{g} \ | \ \pi(\xi) = \rho(\eta) \} \\]

This comes with a natural projection \\(\hat{\mathfrak{g}} \to \mathfrak{g}\\). If we suppose that the projective representation \\(\rho\\) is faithful, then the kernel of this map is exactly \\(\mathbb{C}\\). Hence, a faithful projective representation of \\(\mathfrak{g}\\) yields a short exact sequence of Lie algebras

\\[ 0 \to \mathbb{C} \to \hat{\mathfrak{g}} \to \mathfrak{g} \to 0. \\]

We have obtained a central extension of \\(\mathfrak{g}\\).



Virasoro Algebra

Finally, we can define the Virasoro algebra. It has generators \\(L_n\\) and \\(c\\), with defining relations

\\[ [L_m, L_n] = (m-n) L_{m+n} + \frac{c}{12}(m^3-m) \delta_{m+n,0}, [c, L_n] = 0. \\]

The generator \\(c\\) acts as a scalar in any irreducible representation, and its value is called the central charge. The factor of \\(1/12\\) is entirely conventional. Now, the amazing fact is the following.


Theorem. Up to equivalence, the Virasoro algebra is the unique non-trivial central extension of the Witt algebra.


Proof sketch. This is essentially just a calculation. Any central extension has to be of the form

\\[ [L_m, L_n] = (m-n) L_{m+n} + A(m,n) c \\]

for some function \\(A(m,n)\\). If we make the replacement \\(L_m \mapsto L_m + a_m c\\), then we have

\\[ [L_m, L_n] = (m-n) L_{m+n} + \left( A(m,n) + (m-n) a_{m+n} \right) c \\]

Taking \\(n = 0\\), we have

\\[ [L_m, L_0] = m L_{m} + \left( A(m,0) + m a_{m} \right) c \\]

Hence for \\(m\neq0\\) we can take \\(a_m = m^{-1} A(m,0)\\). Having done this, we are now free to assume that \\(A(m,0) = 0 \\) for all \\(m\\). Then we may apply the Jacobi identity to deduce that \\(A(m,n)=0\\) except possibly for \\(m=-n\\), so that \\(A(m,n)\\) can be written in the form \\(A(m,n) = A_m \delta_{m+n, 0}\\). Finally, another application of the Jacobi identity yields a simple recurrence relation for the coefficients \\(A_m\\), and it is easily seen that every solution of this recurrence is proportional to \\(m^3-m\\).


Now we can take our (preliminary, and still too naive) definition of a quantum conformal field theory to be a unitary representation of the Virasoro algebra.



Stress-Energy Tensor and OPE

The operator \\(L_0\\) behaves like the Hamiltonian of the theory, and the Virasoro relations show that \\(L_n\\) for \\(n&gt;0\\) act as lowering operators. Hence, in a physically sensible representation, the vacuum vector \\(|\Omega\rangle\\) will be annihilated by \\(L_n\\) for all \\(n &gt; 0\\). Unitary requires \\(L_n^\dagger = L_{-n}\\), so additionally we have \\(\langle \Omega|L_n = 0\\) for \\(n &lt; 0\\). Hence

\\[ \langle \Omega | L_m L_n | \Omega \rangle = 0 \ \textrm{unless}\ n \leq 0, m \geq 0 \\]


Now define the stress-energy tensor to be the operator-valued formal power series

\\[ T(z) = \sum_n \frac{L_n}{z^{n+2}} \\]

We can consider the vacuum expectation of the product \\(T(z) T(w)\\). By the above remarks, many terms in the expansion will vanish. In fact, it is a straightforward (but tedious!) exercise to check the following.


Theorem. The stress-energy tensor satisfies the operator product expansion

\\[ T(z) T(w) \sim \frac{c/2}{(z-w)^4} + \frac{2 T(w)}{(z-w)^2} + \frac{\partial_w T(w)}{z-w} \\]

where \\(\sim\\) denotes that the left- and right-hand sides are equal up to the addition of terms with vanishing vev and/or regular as \\(z \to w\\).
