+++
title = "Hamilton-Jacobi equation and Riemannian distance"
date = 2015-08-31
draft = false
categories = ["uncategorized"]
tags = []
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Consider the cotangent bundle \\(T^\ast X\\) as a symplectic manifold with canonical symplectic form \\(\omega\\). Consider the Hamilton-Jacobi equation

\\[ \frac{\partial S}{\partial t} + H(x, \nabla S) = 0, \\]

for the classical Hamilton function \\(S(x,t)\\). Setting \\(x=x(t), p(t) = (\nabla S)(x(t), t)\\) one sees immediately from the method of characteristics that this PDE is solved by the classical action

\\[ S(x,t) = \int_0^t (p \dot{x} - H) ds, \\]

where the integral is taken over the solution \\((x(s),p(s))\\) of Hamilton's equations with \\(x(0)=x_0\\) and \\(x(t) = x\\). The choice of basepoint \\(x_0\\) involves an overall additive constant of \\(S\\), and really this solution is only valid in some neighbourhood \\(U\\) of \\(x_0\\). (Reason: \\(S\\) is in general multivalued, as the differential "\\(dS\\)" is closed but not necessarily exact.)


Now consider the case where \\(X\\) is Riemannian, with Hamiltonian \\(H(x,p) = \frac{1}{2} |p|^2\\). The solutions to Hamilton's equations are affinely parametrized geodesics, and by a simple Legendre transform we have

\\[ S(x, t) = \frac{1}{2} \int_0^t |\dot x|^2 ds \\]

where the integral is along the affine geodesic with \\(x(0) = x_0\\) and \\(x(t) = x\\). Since \\(x(s)\\) is a geodesic, \\(|\dot x(s)|\\) is a constant (in \\(s\\)) and therefore

\\[ S(x, t) = \frac{t}{2} |\dot x(0)|^2. \\]

Now consider the path \\(\gamma(s) = x(|\dot x(0)|^{-1}s)\\). This is an affine geodesic with \\(\gamma(0) = x_0\\), \\(\gamma(|\dot x(0)|t) = x\\) and \\(|\dot \gamma| = 1\\). Therefore, the Riemannian distance between \\(x_0\\) and \\(x\\) (provided \\(x\\) is sufficiently close to \\(x_0\\)) is

\\[ d(x_0, x) = |\dot x(0)| t. \\]

Combining this with the previous calculation, we see that

\\[ S(x, t) = \frac{1}{2t} d(x_0, x)^2. \\]

Now insert this back into the Hamilton-Jacobi equation above. With a bit of rearranging, we have the following.


Theorem. Let \\(x_0\\) denote a fixed basepoint of \\(X\\). Then for all \\(x\\) in a sufficiently small neighborhood \\(U\\) of \\(x_0\\), the Riemannian distance function satisfies the Eikonal equation

\\[ |\nabla_x d(x_0, x)|^2 = 1. \\]


Now, for convenience set \\(r(x) = d(x_0, x)\\). Then \\(|\nabla r|^2 = 1\\), from which we obtain (by differentiating twice and contracting)

\\[ g^{ij} g^{kl}\left(\nabla_{lki} r \nabla_j r + \nabla_{ki}r \nabla_{lj} r\right) = 0.\\]

Quick calculation shows that

\\[ \nabla_{lki} r = \nabla_{ilk} r - \left.R_{li}\right.^{b}_k \nabla_b r \\]

Therefore, tracing over \\(l\\) and \\(k\\) we obtain

\\[ g^{lk} \nabla_{lki} r = \nabla_i ( \Delta r) + Rc(\nabla r, -) \\]

Plugging this back into the equation derived above, we have

\\[ \nabla r \cdot \nabla(\Delta r) + Rc(\nabla r, \nabla r) + |Hr|^2 = 0, \\]

where \\(Hr\\) denotes the Hessian of \\(r\\) regarded as a 2-tensor. Now, using \\(r\\) as a local coordinate, it is easy to see that \\(\partial_r = \nabla r\\) (as vector fields). So we can rewrite this identity as

\\[ \partial_r (\Delta r) + Rc(\partial_r, \partial_r) + |Hr|^2 = 0. \\]


Now, we can get a nice result out of this. First, note that the Hessian \\(Hr\\) always has at least one eigenvalue equal to zero, because the Eikonal equation implies that \\(Hr(\partial_r, -)=0\\). Let \\(\lambda_2, \dots, \lambda_n\\) denote the non-zero eigenvalues of \\(Hr\\). We have

\\[ |Hr|^2 = \lambda_2^2 + \dots + \lambda_n^2, \\]

while on the other hand

\\[ |\Delta r|^2 = (\lambda_2 + \dots + \lambda_n)^2 \\]

By Cauchy-Schwarz, we have

\\[ |\Delta r|^2 \leq (n-1)|Hr|^2 \\]


Proposition. Suppose that the Ricci curvature of \\(X\\) satisfies \\(Rc \geq (n-1)\kappa\\), and let \\(u = (n-1)(\Delta r)^{-1}\\). Then

\\[ u' \geq 1 + \kappa u^2. \\]


Proof. From preceding formulas, \\(|Hr|^2\\) can be expressed in terms of the Ricci curvature and the radial derivative of \\(\Delta r\\). On the other hand, \\(|\Delta|^2\\) is bounded above by \\((n-1) |Hr|^2\\). The claimed inequality then follows from simple rearrangement.


Now, the amazing thing is that this deceptively simple inequality is the main ingredient of the Bishop-Gromov comparison theorem. The Bishop-Gromov comparison theorem, in turn, is the main ingredient of the proof of Gromov(-Cheeger) precompactness. I hope to discuss these topics in a future post.
