---
title: "The Weyl and Wigner transforms"
date: 2012-12-13
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).

Today I'd like to try to understand better how deformation quantization is related to the usual canonical quantization, and especially how the latter might be used to deduce the former, i.e., given an honest quantization (in the sense of operators), how might be reproduce the formula for the Moyal star product?


We'll fix our symplectic manifold once and for all to be $\mathbb{R}^2$ with its standard symplectic structure, with Darboux coordinates $x$ and $p$. Let $\mathcal{A}$ be the algebra of observables on $\mathbb{R}^2$. For technical reasons, we'll restrict to those smooth functions that are polynomially bounded in the momentum coordinate (but of course the star product makes sense in general). Let $\mathcal{D}$ be the algebra of pseudodifferential operators on $\mathbb{R}$. We want to define a quantization map

$$ \Psi: \mathcal{A} \to \mathcal{D} $$

such that

$$ \Psi(x) = x \in \mathcal{D} $$

$$ \Psi(p) = -i\hbar \partial $$

Out of thin air, let us define

$$ \langle q| \Psi(f) |q' \rangle = \int e^{ik(q-q')} f(\frac{q+q'}{2}, k) dk $$

This is the Weyl transform. Its inverse is the Wigner transform, given by

$$ \Phi(A, q, k) = \int e^{-ikq'} \left\langle q+\frac{q'}{2} \right| A \left| q - \frac{q'}{2} \right\rangle dq' $$

Note: I am (intentionally) ignoring all factors of $2\pi$ involved. It's not hard to work out what they are, but annoying to keep track of them in calculations, so I won't.


Theorem For suitably well-behaved $f$, we have $ \Phi(\Psi(f)) = f$.


Proof Using the "ignore $2\pi$" conventions, we have the formal identities

$$ \int e^{ikx} dx = \delta(k), \ \ \int e^{ikx} dk = \delta(x). $$

The theorem is a formal result of these:

\\begin{align} \Phi(\Psi(f))(q, k) &= \int e^{-ikq'} \left\langle q + \frac{q'}{2} \right| \Psi(f) \left| q - \frac{q'}{2} \right\rangle \\\

&= \int e^{-ikq'} e^{ik'q'} f(q, k) dk' dq' \\\

&= f(q,k).

\\end{align}


One may easily check that $\Psi(x) = x$ and $Psi(k) = -i\partial$, so this certainly gives a quantization. But why is it particularly natural? To see this, let $Q$ be the operator of multiplication by $x$, and let $P$ be the operator $-i\partial$. We'd like to take $f(q,p)$ and replace it by $f(Q, P)$, but we can't literally substitute like this due to order ambiguity. However, we could work formally as follows:

\\begin{align}

f(Q, P) &= \int \delta(Q-q) \delta(P - p) f(q,p) dq dp \\\

&= \int e^{ik(Q-q) + iq'(P-p)} f(q,p) dq dq' dp dk.

\\end{align}

In this last expression, there is no order ambiguity in the argument of the exponential (since it is a sum and not a product), and furthermore the expression itself make sense since it is the exponential of a skew-adjoint operator. So let's check that this agrees with the Weyl transform. Using a special case of the Baker-Campbell-Hausdorff formula for the Heisenberg algebra, we have

$$ e^{ik(Q-q) + iq'(P-p)} = e^{ik(Q-q)} e^{iq'(P-p)} e^{-ikq'/2} $$

Let us compute the matrix element:

\\begin{align}

\langle q_1 | P | q_2 \rangle &= \int \langle q_1 | p_1 \rangle

\langle p_1 | P | p_2 \rangle \langle p_2 | q_2 \rangle dp_1 dp_2 \\\

&= \int e^{iq_1p_1 - iq_2 p_2} p_2 \delta(p_2 - p_1) dp_1 dp_2 \\\

&= \int e^{i p(q_1-q_2)} p dp.

\\end{align}

Hence we find that the matrix element for the exponential is

\\begin{align} \langle q_1 |e^{ik(Q-q) + iq'(P-p)} | q_2 \rangle

&= e^{-ikq'/2 + ik(q_1-q)} \langle q_1 | e^{iq'(P-p)} | q_2 \rangle \\\

&=  \int e^{-ikq'/2 + ik(q_1-q) -iq'p} e^{iq'p'' + ip''(q_1-q_2)} dp'' \\\

&= \delta(q' + q_1 - q_2)  e^{-ikq'/2 + ik(q_1-q) -iq'p}

\\end{align}

Plugging this back into the expression for $f(Q, P)$ we find

\\begin{align}

 \langle q_1 | f(Q. P) | q_2 \rangle &= \int \delta(q' + q_1 - q_2)  e^{-ikq'/2 + ik(q_1-q) -iq'p}

f(q,p) dq dq' dp dk \\\

&= \int  e^{ ik(q_1/2 +q_2/2-q) -ip(q_1-q_2)} f(q,p) dq dp dk \\\

&= \int e^{ip(q_1-q_2)} f(\frac{q_1+q_2}{2}, p) dp,

\\end{align}

which is the original expression we gave for the Weyl transform.

