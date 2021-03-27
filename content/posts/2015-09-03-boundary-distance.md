---
title: "Boundary Distance"
date: 2015-09-03
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).



Recently, I've been learning some topics related to machine learning, and especially manifold learning. These both fall under the general notion of inverse problems: given some mathematical object \\(X\\) (it could be a function \\(f: A \to B\\), or a Riemannian manifold \\((M,g)\\), or a probability measure \\(d\mu\\) on a space \\(X\\), etc.), can we effectively reconstruct \\(X\\) given only the information of some auxiliary measurements? What if we can only perform finitely many measurements? What if the measurements are noisy? Can we reconstruct \\(X\\) at least approximately? Can we measure in some precise way, how close our approximate reconstruction is to the unknown object \\(X\\)? And so on, and so forth.


Anyway, this post is about a cute observation, which I was reminded of while reading a paper on the inverse Gel'fand problem. Let \\(M\\) be a compact manifold with smooth boundary \\(\partial M\\). Then with no additional data required, we have a Banach space \\(L^\infty(\partial M)\\) consisting of the essentially bounded measureable functions on the boundary. Since it is a Banach space, it comes with a complete metric \\(d_\infty(f,g) := \|f-g\|_{L^\infty(\partial M)}\\).


Now, suppose that \\(g\\) is a Riemannian metric on \\(M\\). Then we have the Riemannian distance function \\(d_g(x,y)\\) which is defined to be the infimum of arclengths of all smooth paths connecting \\(x\\) and \\(y\\). For any \\(x \in M\\), we obtain a function \\(r_x \in L^\infty(\partial M)\\) defined by

\\[ r_x(z) = d_g(x,z), \forall z \in \partial M. \\]

This gives a map \\(\phi_g: M \to L^\infty(\partial M)\\), defined by \\(x \mapsto r_x\\).


Theorem. Suppose that for any two distinct \\(x,y \in M\\), there is a unique length-minimizing geodesic connecting \\(x\\) and \\(y\\). Then \\(\phi_g: M \to L^\infty(\partial M)\\) is an isometric embedding, i.e. \\(d_g(x,y) = d_\infty(r_x, r_y)\\) for all \\(x,y \in M\\).


Proof. Let \\(x,y\\) be distinct and let \\(\gamma\\) be the unique geodesic from \\(x\\) to \\(y\\). For any point \\(z\\) on the boundary, we have

\\[ |d_g(x,z) - d_g(y,z)| \leq d_g(x,y). \\]

which is the triangle inequality. Now let \\(\gamma\\) be the unique geodesic from \\(x\\) to \\(y\\), and extend \\(\gamma\\) until it hits some boundary point \\(z_\ast\\). Then since \\(x,y,z_\ast\\) all lie on a length-minimizing geodesic, we have

\\[ d_g(x,z_\ast) - d_g(y,z_\ast) = d_g(x,y). \\]

Therefore, the bound above is always saturated, and we find

\\[ \sup_{z \in \partial M} |d_g(x,z) - d_g(y,z)| = d_g(x,y). \\]

But the expression on the left is nothing but the \\(L^\infty(\partial M)\\)-norm of \\(r_x-r_y\\), so the theorem is proved.
