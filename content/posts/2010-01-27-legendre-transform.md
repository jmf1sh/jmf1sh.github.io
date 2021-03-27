+++
title = "Legendre transform"
date = 2010-01-27
draft = false
categories = ["physics"]
tags = ["classical-mechanics", "calculus-of-variatons"]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Yesterday, I gave an introductory talk on Hamiltonian mechanics and symplectic geometry. The starting point is the Legendre transform. First, begin with a configuration space \\(Q\\). The Lagrangian \\(\mathcal{L}\\) is a smooth function on \\(TQ\\). In local coordinates \\(q^i\\) on \\(Q\\), we have coordinates \\((q_i, v_i)\\) on \\(TQ\\), where the \\(v^i\\) are the components of the tangent vector

\\(v = v_i \partial_i \in T_q Q\\). Typically, the Lagrangian will be of the form

$$ \mathcal{L}(q,v) = \frac{1}{2} g(v,v) - V(q), $$

where \\(g\\) is some metric on \\(Q\\). Now we introduce new coordinates \\(p_i\\) defined by

$$ p_i = \frac{\partial \mathcal{L}}{\partial v^i}. $$

If \\(\mathcal{L}\\) is (strictly?) convex in \\(v\\) then we can solve for \\(v^i\\) as a function of \\((q^i, p_j)\\). It is easy to check that the \\(p_i\\) transform as covectors, and so this gives a diffeomorphism \\(TQ \to T^\ast Q\\)(which depends on \\(\mathcal{L}\\)). For example, in the above Lagrangian,

$$ \frac{\partial \mathcal{L}}{\partial v} = g(v, -), $$

which is just the dual of \\(v\\) with respect to the metric \\(g\\). So for Lagrangians of this form, the map \\(TQ \to T^\ast Q\\) is just the one given by the metric.


Now comes the interesting part. There is a natural way to turn \\(\mathcal{L}\\), which is a function on \\(TQ\\), into a function \\(H\\) on \\(T^\ast Q\\), in such a way that if we repeat this process, we will get back the original function \\(\mathcal{L}\\) on \\(TQ\\). This is the Legendre transform:

$$ \mathcal{H} = pv - L. $$


Now suppose we have a curve \\(q(t), \dot{q}(t) \in TQ\\) that satisfies the Euler-Lagrange equations. Then by the identification \\(TQ = T^\ast Q\\), this gives a curve \\((q(t), p(t)) \in T^\ast Q\\). What equation does it satisfy? We have

$$ \frac{d}{dt} p = \frac{d}{dt} \frac{\partial \mathcal{L}}{\partial v} = \frac{\partial \mathcal{L}}{\partial q} = -\frac{\partial H}{\partial q}, $$

and

$$ \frac{d}{dt}q = v = \frac{\partial H}{\partial p}. $$

These are Hamilton's equations, and they say that the curve \\(\gamma = (q(t), p(t)) \in T^\ast Q\\) is just an integral curve of the symplectic gradient of \\(H\\)! So classical mechanics is really just about flows of Hamiltonian vector fields on symplectic manifolds.
