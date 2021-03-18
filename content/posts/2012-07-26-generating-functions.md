---
title: "Generating functions"
date: 2012-07-26
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


 Method of Generating Functions


Let $X$ and $Y$ be two smooth manifolds, and let $M = T^\ast X, N = T^\ast Y$ with corresponding symplectic forms $\omega_M$ and $\omega_N$.


Question: How can we produce symplectomorphisms $\phi: M \to N$?


The most important construction from classical mechanics is the method of generating functions. I will outline this method, shameless stolen from Ana Cannas da Silva's lecture notes.


Suppose we have a smooth function $f \in C^\infty(X \times Y)$. Then its graph $\Gamma$ is a submanifold of $M \times N$: $ \Gamma = \{ (x,y, df_{x,y}) \in M \times N \}$. Since $M \times N$ is a product, we have projections $\pi_M, \pi_N$, and this allows us to write the graph as

$$ \Gamma = \{ (x, y, df_x, df_y) \}$$

Now there is a not-so-obvious trick: we consider the twisted graph $\Gamma^\sigma$ given by

$$ \Gamma^\sigma =  \{(x,y, df_x, -df_y) \} $$

Note the minus sign.


Proposition If $\Gamma^\sigma$ is the graph of a diffeomorphism $\phi: M \to N$, then $\phi$ is a symplectomorphism.


Proof By construction, $\Gamma^\sigma$ is a Lagrangian submanifold of $M \times N$ with respect to the twisted symplectic form $\pi_M^\ast \omega_M - \pi_N^\ast \omega_N$. It is a standard fact that a diffeomorphism is a symplectomorphism iff its graph is Lagrangian with respect to the twisted symplectic form, so we're done.


Now we have:


Modified question: Given $f \in C^\infty(M \times N)$, when is its graph the graph of a diffeomorphism $\phi: M \to N$?


Pick coordinates $x$ on $X$ and $y$ on $Y$, with corresponding momenta $\xi$ and $\eta$. Then if $\phi(x,\xi) = (y,\eta)$, we obtain

$$ \xi = d_x f, \ \eta = -d_y f $$

Note the simlarity to Hamilton's equations. By the implicit function theorem, we can construct a (local) diffeomorphism $\phi$ as long as $f$ is sufficiently non-degenerate.


Different Types of Generating Functions

We now concentrate on the special case of $M = T^\ast \mathbb{R} = \mathbb{R} \times \mathbb{R}^\ast$. Note that this is a cotangent bundle in two ways: $T^\ast \mathbb{R} \cong T^\ast \mathbb{R}^\ast$. Hence we can construct local diffeomorphisms $T^\ast \mathbb{R} \to T^\ast \mathbb{R}$ in four ways, by taking functions of the forms

$$ f(x_1, x_2), \ f(x_1, p_2), \ f(p_1, x_2), \ f(p_1, p_2) $$
Origins from the Action Principle, and Hamilton-Jacobi

Suppose that we have two actions

$$ S_1 = \int p_1 \dot{q}_1 - H_1 dt, \ S_2 = \int p_2 \dot{q}_2 - H_2 dt $$

which give rise to the same dynamics. Then the Lagrangians must differ by a total derivative, i.e.

$$ p_1 \dot{q}_1 - H_1 = p_2 \dot{q}_2 - H_2  + \frac{d f}{dt} $$

Suppose that $f = -q_2 p_2 + g(q_1, p_2, t)$. Then we have

$$ p_1 \dot{q}_1 - H_1 = -q_2 \dot{p}_2 - H_2 + \frac{\partial g}{\partial t} + \frac{\partial g}{\partial q_1}\dot{q}_1 + \frac{\partial g}{\partial p_2} \dot{p_2} $$

Comparing coefficients, we find

$$ p_1 = \frac{\partial g}{\partial q_1}, \ q_2 = \frac{\partial g}{\partial p_2}, \ H_2 = H_1 + \frac{\partial g}{\partial t} $$


Now suppose that the coordinates $(q_2, p_2)$ are chosen so that Hamilton's equations become

$$ \dot{q_2} = 0, \ \dot{p}_2 = 0 $$

Then we must have $H_2 = 0$, i.e.

$$ H_1 + \frac{\partial g}{\partial t} = 0 $$

Now we also have $\partial H_2 / \partial p_2 = 0$, so this tells us that $g$ is independent of $p_2$, i.e. $g = g(q_1, t)$. Since $p_1 = \partial g / \partial q_1$, we obtain

$$ \frac{\partial g}{\partial t} + H_1(q_1, \frac{\partial g}{\partial q_1}) = 0 $$

This is the Hamilton-Jacobi equation, usually written as

$$ \frac{\partial S}{\partial t} + H(x, \frac{\partial S}{\partial x}) = 0 $$

Note the similarity to the Schrodinger equation! In fact, one can derive the Hamilton-Jacobi equation from the Schrodinger equation by taking a wavefunction of the form

$$ \psi(x,t) = A(x,t) \exp({\frac{i}{\hbar} S(x,t)}) $$

and expanding in powers of $\hbar$. This also helps to motivate the path integral formulation of quantum theory.
