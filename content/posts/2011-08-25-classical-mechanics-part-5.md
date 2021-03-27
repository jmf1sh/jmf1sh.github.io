+++
title = "Classical mechanics, part 5"
date = 2011-08-25
draft = false
categories = ["phyics"]
tags = ["classical-mechanics"]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/). The original post can be found [here](https://mathphysseminar.blogspot.com/2011/08/classical-mechanics-5-symplectic.html).


As we saw in the previous post, the equations of motion for a mechanical system can be cast into a 1st order form called Hamilton's equations, which are naturally interpreted as describing a path in the phase space \\(T^\ast M\\) associated to the configuration space \\(M\\). Let us investigate the geometry of \\(T^\ast M\\) see why Hamilton's equations are so nice.


Definition The canonical (or sometimes tautological) 1-form on the cotangent bundle \\(T^\ast M\\) is the 1-form \\(\theta\\) defined by

\\[ \theta_{(q,p)}(X) = p(\pi_\ast X), \\]

where \\(\pi_\ast\\) is the pushforward induced by the natural projection \\(\pi: T^\ast M \to TM\\). In other words, the form is defined by

\\[ \theta_{(q,p)} = \pi^\ast p. \\]


Definition The canonical symplectic form on the cotangent bundle \\(T^\ast M\\) is the 2-form \\(\omega\\) defined by

\\[ \omega = -d\theta. \\]


Let \\(\omega_\flat: T M \to T^\ast M\\) be the map given by \\(X \mapsto \iota(X)\omega\\).


Proposition The canonical symplectic form satisfies the following two conditions:

1. It is closed, i.e. \\(d\omega = 0\\).

2. It is nondegenerate, i.e. the map \\(\omega_\flat\\) is invertible with inverse \\(\omega^\sharp: T^\ast M \to TM\\).


Proof The first property follows from \\(d^2 = 0\\). To prove the second, suppose we have local coordinates \\(q^i\\) on \\(M\\) with cotangent coordinates \\(p^i\\). Then it is easily seen that

\\[ \theta = p^i dq^i, \\]

so that

\\[ \omega = dq^i \wedge dp^i, \\]

from which nondegeneracy is obvious.


Definition Any 2-form on a manifold \\(N\\) (not necessarily a cotangent bundle) which satisfies the above two properties will be called symplectic. A pair \\((N, \omega)\\) will be called symplectic if \\(\omega\\) is a symplectic 2-form on \\(N\\).


Definition Given a function \\(H\\) on a symplectic manifold \\((N, \omega)\\), the Hamiltonian vector field associated to \\(H\\) is the vector field \\(X_H\\) uniquely defined by

\\[ dH = \omega_\flat X_H. \\]


Proposition For \\(N = T^\ast M\\) a cotangent bundle with the canonical symplectic form, Hamilton's equations with respect to a Hamiltonian function \\(H\\) describe the flow of the vector field \\(X_H\\).


Proof Again pick local coordinates \\(q\\) and \\(p\\). Then the inverse map \\(\omega^\sharp\\) is given by

\\[ dq \mapsto -\frac{\partial}{\partial p} \\]

\\[ dp \mapsto \frac{\partial}{\partial q} \\]

Since

\\[ dH = \frac{\partial H}{\partial q} dq + \frac{\partial H}{\partial p} dp, \\]

we see that

\\[ X_H = \frac{\partial H}{\partial p} \frac{\partial}{\partial q} - \frac{\partial H}{\partial q} \frac{\partial}{\partial p} \\]

But then the equation describing the flow of \\(X_H\\) is (in components)

\\[ \dot{q} = \frac{\partial H}{\partial p} \\]

\\[ \dot{p} = -\frac{\partial H}{\partial q} \\]

which are exactly Hamilton's equations.
