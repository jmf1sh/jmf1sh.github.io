---
title: "Clifford algebras and spinors part 3: Bochner identity"
date: 2014-03-18
draft: false
---

[Other articles in this series]({{< ref "2014-03-05-clifford-algebras-part-0.md" >}})

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Let $M$ be a Riemannian manifold, and let $Cl(M)$ be its Clifford bundle. Let $E \to M$ be any vector bundle with connection, and assume that $C^\infty(M, E)$ is a $Cl(M)$-module. We can define a Dirac operator $\mathcal{D}$ acting on sections of $E$ via the formula

\[ \mathcal{D} \sigma = \sum_{i=1}^n e_i \cdot \nabla_i \sigma \]

for any orthonormal frame $\{e_1, \dots, e_n\}$ on $M$, and where $\cdot$ denotes the Clifford module action. We demand that the connection on $E$ is compatible with Clifford multiplication in the following sense:

\[ \nabla_j (e_i \cdot \sigma) = (\nabla_j e_i) \cdot \sigma + e_i \cdot \nabla_j \sigma. \]


Let $R$ denote the curvature of $E$, i.e. we have

\[ [\nabla_i, \nabla_j] \sigma =  R(e_i, e_j) \sigma+ \nabla_{[e_i, e_j]} \sigma \]


We can define an endomorphism $\mathcal{R}$ on $E$ by

\[ \mathcal{R} = \frac{1}{2} \sum_{ij} R(e_i, e_j). \]


Theorem. We have the identity $\mathcal{D}^2 = -\Delta + \mathcal{R}$.


Proof. We compute

\begin{align}

\mathcal{D}^2 \sigma &amp;= \sum_{ij} e_i \nabla_i \left( e_j \nabla_j \sigma \right) \\

&amp;= \sum_{ij} e_i e_j \nabla_i \nabla_j \sigma + e_i ( \nabla_i e_j ) \nabla_j \sigma \\

&amp;= -\Delta \sigma + \frac{1}{2}\sum_{ij}e_i e_j [\nabla_i, \nabla_j] \sigma + \sum_{ij} e_i ( \nabla_i e_j) \nabla_j \sigma \\

&amp;= -\Delta \sigma + \frac{1}{2}\sum_{ij}e_i e_j R(e_i, e_j) \sigma + \frac{1}{2}\sum_{ij} e_i e_j \nabla_{[e_i, e_j]} \sigma+ \sum_{ij} e_i ( \nabla_i e_j) \nabla_j \sigma \\

&amp;= (-\Delta + \mathcal{R})\sigma + \frac{1}{2} \sum_{ij} \left( e_i e_j \nabla_{[e_i, e_j]}\sigma +  e_i (\nabla_i e_j) \nabla_j + e_j (\nabla_j e_i) \nabla_i \right)\sigma

\end{align}

We will be done provided we can show that the last term vanishes. Notice that it is fully tensorial, since it can be expressed as $\mathcal{D}^2 + \Delta - \mathcal{R}$. On the other hand, the terms $[e_i, e_j]$ and $\nabla_j e_i$ are (by definition!) proportional to Christoffel symbols. Since we can always choose a frame so that these vanish at a point, these terms must vanish identically. Hence we have $0 = \mathcal{D}^2 + \Delta - \mathcal{R}$, as desired.
