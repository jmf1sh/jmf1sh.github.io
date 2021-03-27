+++
title = "Clifford algebras and spinors, part 2: spin structures and Dirac operators"
date = 2014-03-06
draft = false
categories = ["geometry"]
tags = ["clifford-algebras"]
+++

[Other articles in this series]({{< ref "2014-03-05-clifford-algebras-part-0.md" >}})

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).



A very good reference for today's material is Dan Freed's (unpublished) notes on Dirac operators, available here.


Spin(n)

Consider the Clifford algebra \\(Cl(\mathbb E^n)\\) as constructed in yesterday's post. Define maps \\(t, \beta: Cl(\mathbb E^n) \to Cl(\mathbb E^n)\\) via

\\[ (e_1 \cdots e_k)^t = e_k \cdots e_1, \ \beta(e_1 \dots e_k) = (-1)^k e_k \dots e_2 e_1 \\]

 There is a natural inclusion \\(\mathbb E^n \hookrightarrow Cl(\mathbb E^n)\\). Given \\(x \in Cl(\mathbb E^n)\\) and \\(v \in \mathbb E^n\\), we can consider the product \\(x v x^t\\). In general, this might not be contained in \\(\mathbb E^n \subset Cl(\mathbb E^n)\\).


Definition. We define the group \\(Pin(n)\\) to consist of all those \\(g \in Cl(\mathbb E^n)\\) such that

\\[ g \beta(g) = 1, \ \ g v \beta(g) \subset \mathbb E^n \ \forall\ v \in \mathbb E^n. \\]

Similarly, we define the group \\(Spin(n)\\) to be the subgroup of \\(Pin(n)\\) such that \\(gg^t = 1\\).


Theorem. The natural action of \\(Pin(n)\\) on \\(\mathbb E^n\\) is by othogonal transformations, giving a natural map \\(Pin(n) \to O(n)\\). This map is a double cover. Similarly, \\(Spin(n)\\) is a double cover of \\(SO(n)\\). If \\(n \geq 2\\), \\(Spin(n)\\) is simply connected.


The importance of the spin groups is due to the following basic fact. Suppose that \\(G\\) is a Lie group with Lie algebra \\(\mathfrak{g}\\). Any representation of \\(G\\) induces a representation of \\(\mathfrak{g}\\). However,  given a representation of \\(\mathfrak{g}\\), it is not always possible to integrate it to a representation of \\(G\\). But it is always possible to integrate a representation of \\(\mathfrak{g}\\) to produce a representation of the universal cover of \\(G\\). For \\(n \geq 2\\), \\(Spin(n)\\) is the universal cover of \\(SO(n)\\).


Spin Structures

Let \\((M^n, g)\\) be a Riemannian manifold. Recall that the frame bundle \\(O(M)\\) is the manifold consisting of pairs \\((x, \mathbb{e})\\) where \\(x \in M\\) and \\(\mathbb{e} = \{e_1, \dots, e_n\}\\) is an orthonormal frame in \\(T_x M\\). Since the orthogonal group \\(O(n)\\) acts on the set of orthonormal frames, this makes \\(F(M)\\) into a principal \\(O(n)\\) bundle over \\(M\\). Let us assume that \\(M\\) is oriented, so that we may reduce its structure group to \\(SO(n)\\).


Suppose that \\(V\\) is a representation of \\(SO(n)\\). Then we may form the associated bundle \\(SO(M) \times_{SO(n)} V\\), which is a vector bundle over \\(M\\) with structure group \\(SO(n)\\). If we take the defining representation then we obtain the tangent bundle, but of course there are many others. Unfortunately, since \\(SO(n)\\) is not simply connected, not every representation of \\(\mathfrak{so}_n\\) can be integrated to a representation of \\(SO(n)\\). At the level of geometry, this means that in a certain sense there are certain vector bundles over \\(M\\) that are "missing"! Even more disturbing, is that these "missing" bundles appear to be necessary to describe many of the fundamental particles that appear in the standard model--so this has real world consequences. The solution is to equip \\(M\\) with a spin structure.


Definition. A spin structure on \\(M\\) is a principal \\(Spin(n)\\)-bundle \\(Spin(M)\\) over \\(M\\) together with a bundle morphism \\(Spin(M) \to SO(M)\\) which is a reduction of structure (i.e., satisfies the obvious axioms).


As you might expect, not every manifold admits a spin structure, and spin structures may not be unique. Loosely speaking, a spin structure is a slightly stronger notion of orientability. Spin structures may always be chosen locally, and the obstruction to consistent gluing is not too difficult to characters as a certain \\(\mathbb Z_2\\) cohomology class, called the second Stiefel-Whitney class.



Spin Connection and Dirac Operators

The reduction of structure \\(Spin(M) \to SO(M)\\) allows us to pull back the Levi-Civita connection on \\(SO(M)\\) to obtain a connection on \\(Spin(M)\\), called the spin connection. Let \\(S_0\\) be the spinor module described in the previous post. Then we may construct the associated bundle

\\[ S = Spin(M) \times_{Spin(n)} S_0 \\]

which is called the spinor bundle. Moreover, since \\(S_0\\) is a Clifford module, there is well-defined notion of Clifford multiplication on sections of \\(S\\). We may then define the Dirac operator \\(\mathcal{D}\\) by

\\[ \mathcal{D} = \sum_{a=1}^n c(e_a) \nabla_{e_a} \\]

where \\(\{e_a\}\\) is any orthonormal frame, \\(\nabla\\) is the spin connection, and \\(c\\) denotes Clifford multiplication.


Next time: the Weitzenböck formula, and maybe a vanishing theorem.
