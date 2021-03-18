---
title: "The Index Form"
date: 2015-09-11
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Let $f: [0,T] \times (-\epsilon, \epsilon) \to M$ be a family of parametrized curves in a Riemannian manifold $(M, g)$. To simplify this calculation, we assume that $f(0,s) = p, f(T, s) = q$ for some $p,q \in M$ and all $s \in (-\epsilon, \epsilon)$. (This assumption is not necessary, but without it our variational formulae will have additional boundary terms.)


For convenience, set $\dot f = \partial f / \partial t$ and $f' = \partial f / \partial s$. For each $s \in (-\epsilon, \epsilon)$ we define the energy functional $E = E(s)$ to be

$$ E(s) = \frac{1}{2} \int_0^T |\dot f|^2 dt. $$

The first variation is

\\begin{align}

\frac{dE}{ds} &= \int_0^T \langle \nabla_{f'} \dot f, \dot f \rangle dt \\\

&= \int_0^T \langle \nabla_{\dot f} f', \dot f \rangle dt \\\

&= -\int_0^T \langle f', \nabla_{\dot f}\dot f \rangle dt

\\end{align}


Set $\gamma(t) := f(t,0)$ and $X(t) = f'(t)$ (thought of as a vector field supported on $\gamma$). Evaluating the above at $s=0$ we obtain

$$ \left.\frac{dE}{ds}\right|_{s=0} = -\int_0^T \langle X, \nabla_{\dot \gamma} \dot \gamma \rangle dt, $$

which shows immediately that


Theorem. $\gamma$ is a critical point of the energy functional if and only if $\nabla_{\dot \gamma} \dot \gamma = 0$.



The second variation is

\\begin{align}

\frac{d^2 E}{ds^2}

&= -\int_0^T \langle \nabla_{f'}f', \nabla_{\dot f}\dot f \rangle

 + \langle f', \nabla_{f'}\nabla_{\dot f}\dot f \rangle dt \\\

&= -\int_0^T \langle \nabla_{f'}f', \nabla_{\dot f}\dot f \rangle

 + \langle f', \nabla_{\dot f}\nabla_{f'}\dot f \rangle dt

 + \langle f', R(f', \dot f)\dot f \rangle dt \\\

&= -\int_0^T \langle \nabla_{f'}f', \nabla_{\dot f}\dot f \rangle

 - \langle \nabla_{\dot f}f', \nabla_{f'}\dot f \rangle dt

 + \langle f', R(f', \dot f)\dot f \rangle dt \\\ &= -\int_0^T \langle \nabla_{f'}f', \nabla_{\dot f}\dot f \rangle

 - \langle \nabla_{\dot f} f', \nabla_{\dot f} f'\rangle dt

 + \langle f', R(f', \dot f)\dot f \rangle dt

\\end{align}


Assume now that $\gamma$ is a geodesic, i.e. $\nabla_{\dot \gamma} \dot \gamma = 0$. Then evaluating the above at $s=0$, we obtain

$$ \frac{d^2 E}{ds^2} = \int_0^T |\nabla_{\dot \gamma} X|^2 - \langle X, R(X, \dot \gamma) \dot \gamma \rangle dt. $$


Definition. Let $\gamma$ be a geodesic. The index form associated to variations $X,Y$ of $\gamma$ is

\\begin{align} I(X,Y) &= \int_0^T \langle \nabla_{\dot \gamma} X, \nabla_{\dot \gamma} Y \rangle dt

 - \langle Y, R(X, \dot \gamma) \dot \gamma \rangle \\\

&= -\int_0^T \langle Y, \nabla_{\dot \gamma}^2 X + R(X, \dot\gamma)\dot \gamma \rangle

\\end{align}

It follows from symmetries of the Riemann tensor that $I(X,Y) = I(Y, X)$ and also $I(X,X) = E''$ as above.


Theorem. Suppose that $X$ is the infinitesimal variation of a family of affine geodesics about a fixed geodesic $\gamma$. Then

$$ \nabla_{\dot \gamma}^2 X + R(X, \dot\gamma)\dot\gamma = 0. $$

In particular, $I(X, -) = 0$.


Proof. Let $f(t,s)$ denote the family as above. By hypothesis, we have that $\nabla_{\dot f} \dot f = 0$ for all $s$, so that

$$ \nabla_{f'} \nabla_{\dot f} \dot f = 0. $$

Commuting the derivatives using the curvature tensor, we have

$$ 0 = \nabla_{\dot f} \nabla_{f'} \dot f + R(f', \dot f) \dot f. $$

Now use $\nabla_{\dot f} f' = \nabla_{f'} \dot f$ and evaluate at $s=0$ to obtain

$$ 0 = \nabla_{\dot \gamma}^2 X + R(X, \dot \gamma)\dot\gamma. $$
