
---
title: "What is generalized geometry?"
date: 2015-01-29
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


The following are my notes for a short introductory talk. References below are not intended to be comprehensive!


Math references:
* Courant,  Dirac manifolds
* Hitchin, Generalized Calabi-Yau manifolds
* Gualtieri, Generalized complex geometry
* Cavalcanti, New aspects of the ddc-lemma
* Cavalcanti and Gualtieri, Generalized complex geometry and T-duality
* Bailey and Gualtieri, Local analytic geometry of generalized complex structures



Physics references:
* Dijkgraaf, Gukov, Neitzke, Vafa, Topological M-theory as unification of form theories of gravity
* Grana, Flux compactifications in string theory: a comprehensive review


What is geometry?
-------------------------------------------------------------------------------

Before trying to define generalized geometry, we should first decide what we mean by ordinary geometry. Of course, this question doesn't have a unique answer, so there are many ways to generalize the classical notions of manifolds and varieties. The viewpoint taken in generalized geometry is the following: the distinguishing feature of smooth manifolds is the existence of a tangent bundle

\\[ TM \to M \\]

which satisfies some nice axioms. The basic idea of generalized geometry is to replace the tangent bundle with some other vector bundle \\(L \to M\\), again satisfying some nice axioms. Different generalized geometries on \\(M\\) will correspond to different choices of bundle \\(L \to M\\), as well as auxiliary data compatible with \\(L\\) in some appropriate sense.


Definition. A Lie algebroid over \\(M\\) is a smooth vector bundle \\(L \to M\\) together with a vector bundle map \\(a: L \to TM\\) called the anchor map and a bracket \\([\cdot, \cdot]: H^0(M, L) \otimes H^0(M, L) \to H^0(M, L)\\) satisfying the following axioms:

* \\([\cdot,\cdot]\\) is  a Lie bracket on \\(H^0(M, L)\\)
* \\([X, fY] = f[X,Y] + a(X)f \cdot Y\\) for \\(X,Y \in H^0(M,L)\\) and \\(f \in H^0(M, \mathcal{O}_M)\\)

Note that we can take \\(L\\) to be either a real or complex vector bundle. In the latter case the anchor map should map to the complexified tangent bundle.


Example 1. We can take \\(L\\) to be \\(TM\\) with anchor map the identity.


Example 2. Let \\(\sigma\\) be a Poisson tensor on \\(M\\). Then we define a bracket by \\([X,Y] = \sigma(X,Y)\\) and an anchor by \\(X \mapsto \sigma(X, \cdot)\\). This makes \\(T^\ast M\\) into a Lie algebroid.


Example 3. Let \\(M\\) be a complex manifold of and let \\(L \subset TM \otimes \mathbf{C}\\) be the sub-bundle of vectors spanned by \\(\{\partial / \partial z_1, \dots, \partial / \partial z_n\}\\) in local holomorphic coordinates. Then \\(L \to M\\) is a (complex) Lie algebroid.



Courant Bracket
-------------------------------------------------------------------------------

We'd like to try to fit the preceding examples into a common framework. Let \\(\mathbf{T}M = TM \oplus T^\ast M\\). This bundle has a natural symmetric bilinear pairing given by

\\[ \langle X \oplus \alpha, Y \oplus \beta \rangle = \frac{1}{2} \alpha(Y) + \frac{1}{2} \beta(X) \\]

Note that this bilinear form is of split signature \\((n,n)\\). We define a bracket on sections of \\(\mathbf{T}M\\) by

\\[ [X\oplus \alpha, Y\oplus \beta] = [X,Y] \oplus \left(L_X \beta + \frac{1}{2}(d \alpha(Y))- L_Y \alpha -\frac{1}{2} d( \beta(X)) \right ) \\]

Note that this bracket is not a Lie bracket. We also have an anchor map \\(a: \mathbf{T}M \to TM\\) which is just the projection.


 Let \\(B\\) be a 2-form on \\(M\\). Define an action of \\(B\\) on sections of \\(\mathbf TM\\) by

\\[ X + \alpha \mapsto X + \alpha + i_X B \\]


Proposition. This action preserves the Courant bracket if and only if \\(B\\) is closed.


This shows that the diffeomorphisms of \\(M\\) as a generalized manifold are large than the ordinary diffeomorphisms of \\(M\\). In fact is is the semidirect product of the diffeomorphism group of \\(M\\) with the vector space of closed 2-forms.


Dirac Structures
-------------------------------------------------------------------------------

Definition. A Dirac structure on \\(M\\) is an Lagrangian sub-bundle \\(L \subset \mathbf{T}M\\) which is closed under the Courant bracket.


Theorem (Courant). A Lagrangian sub-bundle \\(L \subset \mathbf{T} M\\) is a Dirac structure if and only if \\(L \to M\\) is a Lie algebroid over \\(M\\), with bracket induced by the Courant bracket and anchor given by projection.


Example 1. \\(TM \subset \mathbf{T}M\\).


Example 2. Take \\(L\\) to be the graph of a Poisson tensor.


Example 3. Take \\(L\\) to be the graph of a closed 2-form.


Admissible Functions
-------------------------------------------------------------------------------

We now let \\(L \to M\\) be a Dirac structure on \\(M\\).


Definition. A smooth function \\(f\\) on \\(M\\) is called admissible if there exists a vector field \\(X_f\\) such that \\((X_f, df)\\) is a section of \\(L\\).


The Poisson bracket is defined as follows. If \\(f,g\\) are admissible, then define

\\[ \\{f, g\\} = X_f g. \\]

It is easy to check from the definitions that the bracket on admissible functions is well-defined (independent of choice of \\(X_f\\)) and skew-symmetric. With a little bit of calculation, we find the following.


Proposition. The vector space of admissible functions is naturally a Poisson algebra, and moreover the natural bracket satisfies the Leibniz rule.



Generalized Complex Structures
-------------------------------------------------------------------------------


Definition. A generalized complex structure is a skew endomorphism \\(J\\) of \\(\mathbf T M\\) such that \\(J^2 = -1\\) and such that the \\(+i\\)-eigenbundle is involutive under the Courant bracket.


Equivalently: A generalized complex structure is a (complex) Dirac structure \\(L \subset \mathbf TM\\) satisfying the condition \\(L \cap \overline L = 0\\).


Example 1. Let \\(J\\) be an ordinary complex structure on \\(M\\). Then the endomorphism

\\[ \\begin{bmatrix} -J & 0 \cr 0 & J^\ast \\end{bmatrix} \\]

defines a generalized complex structure on \\(M\\).


Example 2. Let \\(\omega\\) be a symplectic form on \\(M\\). Then the endomorphism

\\[ \\begin{bmatrix} 0 & -\omega^{-1} \cr \omega & 0 \\end{bmatrix} \\]

defines a generalized complex structure on \\(M\\).


Thus, generalized geometry gives a common framework for both complex geometry and symplectic geometry. Such a connection is exactly what is conjectured by mirror symmetry.


Example 3. Let \\(J\\) be a complex structure on \\(M\\) and let \\(\sigma\\) be a holomorphic Poisson tensor. Consider the subbundle \\(L \subset \mathbf TM\\) defined as the span of

\\[ \frac{\partial}{\partial \bar z_1}, \dots, \frac{\partial}{\partial \bar z_n}, dz_1 - \sigma(dz_1), \dots, dz_n - \sigma(dz_n) \\]

Then \\(L\\) defines a generalized complex structure on \\(M\\).


The last example shows that deformations of \\(M\\) as a generalized  complex manifold contain non-commutative deformations of the structure sheaf.  We also have the following theorem, which shows that there is an intimate relation between generalized complex geometry and holomorphic Poisson geometry.


Theorem (Bailey). Near any point of a generalized complex manifold, \\(M\\) is locally isomorphic to the product of a holomorphic Poisson manifold with a symplectic manifold.



Generalized Kähler Manifolds
-------------------------------------------------------------------------------

Let \\((g, J, \omega)\\) be a Kähler triple. The Kähler property requires that

\\[ \omega = g J. \\]

Let \\(I_1\\) denote the generalized complex structure induced by \\(J\\), and let \\(I_1\\) denote the generalized complex structure induced by the symplectic form \\(\omega\\). We have

\\[ I_1 I_2 =
\\begin{bmatrix} - J & 0 \cr 0 & J^\ast \\end{bmatrix}
\\begin{bmatrix} 0 & -\omega^{-1} \cr \omega & 0 \\end{bmatrix}
= \\begin{bmatrix} 0 & g^{-1} \cr g & 0 \\end{bmatrix} = I_2 I_1 \\]


 Definition. A generalized Kähler manifold is a manifold with two commuting generalized complex structure \\(I_1, I_2\\) such that the bilinear pairing \\((I_1 I_2 u, v)\\) is positive definite.


Theorem (Gualtieri). A generalized Kähler structure on \\(M\\) induces a Riemannian metric \\(g\\), two integrable almost complex structures \\(J_\pm\\) Hermitian with respect to \\(g\\), and two affine connections \\(\nabla_\pm\\) with skew-torsion \\(\pm H\\) which preserve the metric and complex structure \\(J_\pm\\). Conversely, these data determine a generalized Kähler structure which is unique up to a B-field transformation.


Thus the notion of generalized Kähler manifold recovers the bihermitian geometry investigated by physicists in the context of susy non-linear \\(\sigma\\)-models.




Generalized Calabi-Yau Manifolds
-------------------------------------------------------------------------------

Definition. A generalized Calabi-Yau manifold is a manifold \\(M\\) together with a complex-valued differential form \\(\phi\\), which is either purely even or purely odd, which is a pure spinor for the action of \\(Cl(\mathbf TM)\\) and satisfies the non-degeneracy condition \\((\phi, \bar \phi) \neq 0\\).


Note that (by definition) \\(\phi\\) is pure if its annihilator is a maximal isotropic subspace. Let \\(L \subset \mathbf TM\\) be its annihilator. Then it is not hard to see that \\(L\\) defines a generalized complex structure on \\(M\\), so indeed a generalized Calabi-Yau manifold is in particular a generalized complex manifold.


Example. If \\(M\\) is a complex manifold with a nowhere vanishing holomorphic \\((n,0)\\) form, then it is generalized Calabi-Yau.


Example. If \\(M\\) is symplectic with symplectic form \\(\omega\\), then \\(\phi = \exp(i\omega)\\) gives \\(M\\) the structure of a generalized Calabi-Yau manifold.


If \\((M, \phi)\\) is generalized Calabi-Yau, then so is \\((M, \exp(B) \phi)\\) for any closed real 2-form \\(B\\). In the symplectic case, we obtain

\\[ \phi = \exp(B+i\omega) \\]

This explains the appearance of the \\(B\\)-field (or "complexified Kähler form") in discussions of mirror symmetry.
