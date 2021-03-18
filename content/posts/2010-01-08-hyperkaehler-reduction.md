---
title: "Hyperkahler reduction"
date: 2010-01-08
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Yesterday I gave a talk on hyperkahler reduction--my first invited talk ever. I thought I should summarize it here.


A hyperkahler manifold is just a Kahler manifold $ (M, g, I)$ together with two additional integrable complex structures $J,K$ such that $I,J,K$ satisfy the quaternion relations, and $J$ and $K$ are compatible with the metric. Hyperkahler manifolds are modeled on $\mathbb{H}^n$, analogous to the way that Kahler manifolds are modeled on $\mathbb{C}^n$


When $G$ acts on a Kahler manifold $M$ preserving the Kahler structure, then (under relatively weak

hypotheses) a momentum map exists and we can use this to define a quotient $M//G$, which turns out to be Kahler. Similarly, if $M$ is hyperkahler and $G$ preserves the hyperkahler structure, then we have a hyperkahler quotient $M///G$.


So far I haven't said anything interesting. There are two basic questions: (1) do any interesting manifolds actually arise in this way? and (2) what theorems about symplectic/Kahler quotients have analogues in hyperkahler quotients?


It turns out that question (1) is related to the Yang-Mills equations over $\mathbb{R}^4$. (Of course, $\mathbb{R}^4 = \mathbb{H}$, so maybe this is not that surprising, since moduli spaces love to inherit geometry from their parents). Depending on choices of Lagrangian, base manifold, etc. you get different moduli spaces of solutions. In general, these moduli spaces are given as quotients of infinite dimensional spaces of connections by the action of some infinite dimensional Lie group of gauge transformations. In 4-dimensions, this frequently turns out to be an infinite-dimensional hyperkahler quotient! In fact, it turns out that the Yang-Mills functional is very closely related to the momentum map for the action of the gauge transformations. Even more surprisingly, there are cases where this infinite-dimensional quotient can be expressed as a finite-dimensional quotient (see, e.g., the ADHM construction). In the case of the ADHM construction, the space you get is actually just the quotient of $\mathbb{H}^n$ by a linear action (i.e. a group of matrices). So it turns out that even mere linear actions give you lots of interesting geometry, and lots of questions about these are still open.


Question (2) is close to my own research interests. The hyperkahler quotient is similar to but different from the symplectic quotient. In symplectic quotients, the most basic tool we have is Morse theory using the momentum map. In hyperkahler geometry, we have 3 moment maps, and it's not obvious what to do with them. Frequently, we encode them as a pair $(\mu_\mathbb{R}, \mu_\mathbb{C})$, where

$$ \mu_\mathbb{R} = \mu_1 $$

$$ \mu_\mathbb{C} = \mu_2 + i \mu_3 $$

It turns out that $\mu_\mathbb{C}$ is holomorphic, and the corresponding form $\omega_\mathbb{C} = \omega_2 + i \omega_3$ is holomorphic symplectic. It's not really clear what the best way of packaging the momentum maps is, and this is an important question because we would like to do Morse theory in some way using the momentum maps.


This leads to one possible way of bypassing these problems. Penrose introduced the idea of twistor spaces. A hyperkahler manifold has a lot of data: $g, I, J, K, \omega_1, \omega_2, \omega_3$ with lots of relations. But there is an interesting symmetry: if $(x_1, x_2, x_3) \in S^2$, then $I_x = x_1 I + x_2 J + x_3 K$ turns out to be another integrable complex structure. So in fact we have an $S^2$ family of Kahler structures. But $S^2 = \mathbb{CP}^1$, which is complex (and in fact Kahler), so we have a Kahler family of Kahler structures. Since everything in question is complex, why not try to encode our data holomorphically?


The twisor construction does just that. For $Z = M \times \mathbb{CP}^1$. Give it the (almost) complex structure $I = (I_x, I_0)$ where $I_0$ is the complex structure on $\mathbb{CP}^1$. One can check (using the Newlander-Nirenberg theorem) that $I$ is integrable, so $Z$ is a complex manifold (and, importantly, is not just the product $M \times \mathbb{CP}^1$ as a complex manifold). Now we need to put some holomorphic data on $Z$.


First, we have the projection $p: Z \to \mathbb{CP}^1$. This is holomorphic and makes $Z$ a fiber bundle over $\mathbb{CP}^1$.


Second, we need the symplectic forms. Let $T_F$ be the vertical subbundle of the tangent bundle to $Z$. Let $\zeta$ be a complex coordinate on $\mathbb{CP}^1$ Now define

$$ \omega = (\omega_2 + i\omega_3) + 2\zeta \omega_1 - \zeta^2 (\omega_2 - i\omega_3).$$

This definition makes sense at least locally, and it makes sense globally thinking of $\omega$ as a holomorphic seciton of $\Lambda^2 T_F^\ast \otimes p^\ast O(2)$. It is also symplectic along the fibers.


The third piece of data we need are the "twistor lines". Given a point $m \in M$, the map $\zeta \mapsto (m, \zeta)$ is a holomorphic section of $Z$. The normal bundle to any such section turns out to be holomorphically equivalent to $\mathbb{C}^{2n} \otimes O(1)$.


The last piece of data is a real structure $\tau$ on $Z$. We can define it by $\tau(m,\zeta) = (m, \bar{\zeta}^{-1})$. This is an antiholomorphic involution. It is also compatible with 1-3 in a sense that I won't describe.


It is a theorem that these 4 pieces of data are all we need to recover M and its hyperkahler structure. (For proof, see Hitchin et al., "Hyperkahler metrics and supersymmetry".) This might seem like a convoluted construction, but the essential point is that the hyperkahler structure is encoded as holomorphic data on $Z$(the only piece data which is not holomorphic is the real structure $\tau$), and holomorphic things are very rigid and easier to work with.


In the twistor language, hyperkahler quotients correspond to a kind of twistor holomorphic symplectic quotient. Maybe this is the right way to think about things. Who knows?
