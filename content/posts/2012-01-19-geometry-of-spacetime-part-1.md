---
title: "Geometry of curved spacetime, part 1"
date: 2012-01-19
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


I'm TAing a course on general relativity this semester, and I'm covering some of the geometry background in tutorials. Since I need to prepare some material for these, I thought there was no harm in putting it up on this blog. So here we go.


Throughout, we'll let \(M\) be a smooth manifold equipped with a metric \(g\). Whenever it makes life easier, I'll assume that \(g\) is positive definite (rather than Lorentzian). For a point \(p \in M\), denote its tangent space by \(T_p M\).


Theorem 1 For any \(p \in M\), there exist a neighborhood \(U\) of 0 in \(T_p M\) and a neighborhood \(V\) of \(p\) in \(M\), and a diffeomorphism \(\exp_p: U \to V\) called exponential map. This map takes lines through the origin in \(T_p M\) to geodesics in \(M\) passing through \(p\).


Theorem 2 In exponential coordinates, the components of the metric are

\[ g_{ij} = \delta_{ij} + O(|x|^2) \]


Corollary 3 In exponential coordinates, the Christoffel symbols vanish at \(p\).


Corollary 4 The Christoffel symbols are not the components of a tensor.


Corollary 5 Not all metrics are equivalent: there is a local invariant, called the curvature.


Construction of exponential map. The metric on \(M\) induces a (constant) metric \(g_{ij}\) on \(T_p M\). By a linear change of coordinates on \(T_p M\), we can assume that this induced metric is just \(g_{ij} = \delta_{ij}\). Now the geodesic equation on \(M\) is a 2nd order ODE which has a unique solution once we specify an initial condition. An initial condition is just a pair \((p,v)\) consisting of a point \(p \in M\) and tangent vector \(v \in T_p M\). Since we have fixed \(p\), each \(v \in T_p M\) gives a unique geodesic through \(p\). Call it \(\gamma_v(t)\). Then define the exponential map as follows:

\[ \exp_p(v) := \gamma_v(1) \]

The fact that this map is well-defined, smooth, and 1-1 (at least locally) follows from the standard existence and uniqueness theorem for ODEs. So to see that it is a diffeomorphism near \(0\), we can just compute its differential and apply the inverse function theorem.


The easy way out. By construction, every geodesic through 0 is of the form \(\gamma_v(t) = tv\). Plugging this into the geodesic equation,

\[ \dot{v} + \Gamma(x)^i_{jk} v^j v^k = 0 \]

we see that at 0, \(\Gamma^i_{jk}\) vanishes, and in particular, the first partial derivatives of the metric vanish.


The hard way: the differential of \(exp\) at 0. First, taylor expand the velocity of a geodesic, and evaluate at time \(t = 1\):

\[ v(t) = v + \dot{v} + \frac{1}{2} \ddot{v} + \cdots \]

Now, by the geodesic equation, \(\dot{v}\) is \(O(v^2)\). Similarly, by differentiating the geodesic equation, we find that all of the higher time derivatives are also \(O(v^2)\). So we find that the exponential map is just the identity + \(O(v^2)\), and hence its differential at 0 is just the identity.


Now, we have argued that in exponential coordinates, the Christoffel symbols vanish at 0. Recall that for any tensor \(T\), if the components of \(T\) vanish at some point \(p\) in one coordinate system, then \(T\) is identically 0 at that point (i.e. its components vanish at that point in all coordinate systems). If the Christoffel symbols were a tensor, then, the above shows that they must be identically zero at all points in \(M\), in all coordinate systems. But this is absolutely not the case--even in flat \(\mathbb{R}^n\), we can pick coordinates so that the Christoffel symbols do not vanish. Hence they are not a tensor.


Aside Though the Christoffel symbols are not a tensor, they are the components of something which does have a coordinate indepdendent definition: a connection 1-form. A connection 1-form is not a tensor but rather a section of a certain associated bundle. More on this in future posts.


Claim Suppose \(\gamma\) is a curve in \(M\) with tangent vector \(T\), and suppose \(V\) is a vector field defined on \(\gamma\). Then \(\nabla_T V\) is well-defined, independent of the smooth extension of \(V\).


Proof Suppose \(V\) and \(W\) are two smooth vector field that agree on \(\gamma\). We would like to show that

\[ \nabla_T V = \nabla_T W \]

i.e., this directional derivative depends only on their restriction to \(\gamma\). It suffices to prove this pointwise. In coordinates, we have

\[ \nabla_T V = T^k \frac{\partial V^i}{\partial x^k} + \Gamma^i_{jk} V^j T^k \]

and similarly for \(W\). The terms involving Christoffel symbols do not depend on derivatives of \(V\) or \(W\), so they agree by assumption. If \(T\) is zero at a point, there is nothing to show. So assume that \(T\) is nonzero at some point. Then near this point, we can choose coordinates \(x^i\) such that

\[ \gamma(t) = (t, 0) \]

so that

\[ T = (1, 0) \]

Then \(V\) and \(W\) agree when \(x^i = 0\) for \(i \geq 2\), and hence their partials agree. We have

\[ T^k \frac{\partial V^i}{\partial x^k} = \frac{V^i}{\partial x^1} = T^k \frac{\partial W^i}{\partial x^k} \]


Explicit Formulas for Christoffel Symbols. Using properties of covariant derivatives, we find

\[ 0 = \nabla_k g_{ij} = \frac{\partial g_{ij}}{\partial x^k} - \Gamma^l_{ki} g_{lj} - \Gamma^l_{kj} g_{il} \]

So

\[ \Gamma_{kij} + \Gamma_{kji} = g_{ij,k} \]

\[ \Gamma_{ijk} + \Gamma_{ikj} = g_{jk,i} \]

\[ \Gamma_{jki} + \Gamma_{jik} = g_{ki,j} \]

Taking (2) + (3) - (1) gives

\[ 2\Gamma_{ijk} = g_{jk,i} + g_{ki,j} - g_{ij,k} \]

Hence

\[ \Gamma_{ij}^k = \frac{g^{kl}}{2}\left(g_{jl,i} + g_{li,j} - g_{ij,l} \right) \]
