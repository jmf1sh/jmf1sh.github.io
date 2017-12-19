---
title: "Geometry of curved spacetime, part 2"
date: 2012-01-26
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Disclaimer: as before, these are (incredibly) rough notes intended for a tutorial. I may clean them up a bit later but for now it will seem like a lot of unmotivated equations (with typos!!).


The Energy Functional

\[ S = \int_0^T |\dot{\gamma}|^2 dt \]

Letting \(V^i = \dot{\gamma}^i\), this is 

\[ S = \int_0^T g_{ij}(\gamma(t)) V^i V^j dt = \int_0^T L dt \]

where the Lagrangian \(L\) is

\[ L = g_{ij} V^i V^j \]

Now, 

\[ \frac{\partial L}{\partial x^k} = (\partial_k g_{ij}) V^i V^j \]

and 

\[ \frac{\partial L}{\partial V^k} = g_{ij} \delta^i_k V^j + g_{ij} V^i \delta^i_k = 2 g_{jk} V^j \]

Now, 

\[ \frac{d}{dt} \frac{\partial L}{\partial V^k} = 2 (\partial_i g_{jk}) V^i V^j + 2 g_{jk} \dot{V}^j \]

Plugging these expressions into the Euler-Lagrange equations, we have

\[ 2 g_{jk} \dot{V}^j + \left(\partial_i g_{jk} + \partial_j g_{ik}- \partial_k g_{ij}\right) V^i V^j = 0 \]

Multiplying by the inverse metric, we have

\[ \dot{V}^k + \frac{g^{kl}}{2} \left( \partial_i g_{jl} + \partial_j g_{il} - \partial_l g_{ij} \right) V^i V^j = 0 \]

Which is the geodesic equation (recall the formula for the Christoffel symbols).


Orthonormal Frames (Lorentzian and Riemannian) (tetrads, vielbeins, vierbeins, ...)

Locally, we can find an orthonormal basis of vector fields \(e^\mu_i\). Greek indicates coordinates, whereas Latin indicates label in the basis. These necessarily satisfy

\[ g_{\mu\nu} e^\mu_i e^\nu_j = \eta_{ij} \]

where \(\eta_{ij}\) is the flat/constant metric (of whatever signature we are working in).


Methods for Computing Curvature (from Wald)

0. Getting the Christoffel symbols from the geodesic equation.

See e.g. sphere or spherical coordinates.


1. Coordinates. By definition,

\[ \nabla_a \nabla_b \omega_c = \nabla_b \nabla_a \omega_c + {R_{abc}}^d \omega_d \]

Writing things explicitly, this gives

\[ R_{abc}^d = \partial_b \Gamma^d_{ac} - \partial_a \Gamma^d_{bc}\]

\[+\Gamma^e_{ac}\Gamma^d_{be} - \Gamma^e_{bc}\Gamma^d_{ae}\]

(todo: fix typesetting.)


Do this for eg unit sphere in \(\mathbb{R}^3\).


2. Curvature in Frames (equivalent to coordinates but totally different flavor)

(note: Misner-Thorne-Wheeler seems much better than Wald for this stuff).

 Using MTW notation. Fix a frame \(\mathbf{e_\mu}\) and a dual frame \(\omega^\mu\). The connection 1-forms are defined by

\[ 0 = d\omega^\mu + \alpha^\mu_\nu \wedge \omega^\nu \]

We also have

\[ dg_{\mu\nu} = \omega_{\mu\nu} + \omega_{\nu\mu}\]

So metric compatibility yields

\[ \omega_{\mu\nu} = -\omega_{\nu\mu}\]

Antisymmetry means fewer independent components. In this language, the curvature 2-form is given by

\[ R^\mu_\nu = d\alpha^\mu_\nu + \alpha^\mu_\sigma \wedge \alpha^\sigma_\nu \]



Gaussian Coordinates

Via Wald. Suppose \(S \subset M\) is a codimension 1 submanifold. If \(S\) is not null, we can find a normal vector field \(n^a\) which is everywhere orthogonal to \(S\) and has unit length. (Probably also need orientation to make it unique!) We can pick any coordinates \(x^1, \cdots, x^{n-1}\) on \(S\), and we pick the last coordinate to be the distance to \(S\), measured along a geodesic with initial tangent vector \(n^a\) (i.e. we use exponential coordinates in the normal direction). 


Once we pick these coordinates, we obtain a family of hypersurfaces \(S_t\) given by

\(x^n = t\). These have the property that they are orthogonal to the normal geodesics through \(S\). Proof: (X are vector fields which are tangent to \(S_t\))

\[ n^b \nabla_b (n_a X^a) = n_a n^b \nabla_b X^a \] 

\[= n_a X^b \nabla_b n^a \] 

\[= \frac{1}{2}X^b \nabla_b (n^a n_a) = 0 \]

(first: geodesic, second: they lie-commute since they are coordinate vector fields).


Jacobi Fields, Focusing and Growth, Conjugate Points

Geodesic deviation. Suppose we have a 1-parameter family of geodesics \(\gamma_s\) with tangent \(T^a\) and deviation \(X^a\). (draw pictures!) By the geodesic equation, we have

\[ T^a \nabla_a T^b = 0 \]

What can we say about \(X^a\)? By change of affine parameter if necessary, we can assume that \(T^a\) and \(X^a\) are coordinate vector fields, and in particular they commute. So

\[ X^a \nabla_a T^b = T^a \nabla_a X^b \]

Then it is easy to see that \(X^a T_a\) is constant, and so (again by change of parameter if necessary) we can assume that it is 0. Now set \(v^a = T^b \nabla_b X^a\). We interpret this as the relative velocity of nearby geodesics. Similarly, we have the acceleration

\[ a^a = T^c \nabla_c v^a = T^b \nabla_b (T^c \nabla_c X^a) \]

Some manipulation shows that

\[ a^a = -R_{cbd}^a X^b T^c T^d \]

This is the geodesic deviation equation. (Positive curvature -&gt; focus, negative curvature -&gt;growth.)


Now we can work this in reverse. Suppose I have a single geodesic with tangent \(T^a\). If I have some vector field \(X^a\) on the geodesic, under what conditions will it integrate to give me a family of geodesics? The above shows that we must have

\[ T^a \nabla_a (T^b \nabla_b X^c) = -R_{abd}^c X^b T^a T^d \]

Solutions to this equation are called Jacobi vector fields.


Definition Points p, q on a geodesic are said to be conjugate if there exists a Jacobi field on the geodesics which vanishes at p and q. (Picture time!)


Definition (Cut Locus in Riemannian Signature) For \(p \in M\), we define the cut locus in \(T_p M\) to be those vectors \(v \in T_p M\) for which \(\exp(tv)\) is length minimizing on \([0,1]\) but fails to be length-minimizing on \([0,1+\epsilon]\) for and \(\epsilon\). The cut locus in M is the image of the cut locus in \(T_p M\) under the exponential map.


eg. Sphere, antipodes.



