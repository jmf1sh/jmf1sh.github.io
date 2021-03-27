+++
title = "Path integrals, part 3"
date = 2012-02-04
draft = false
categories = ["uncategorized"]
tags = []
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).



In my previous posts on path integrals, I described (rather tersely) how the path integral, suitably defined and interpreted, can be used to compute the Schwartz kernel of the operators \\(e^{iHt}\\) (Lorentzian signature) and \\(e^{-Ht}\\) (Euclidean signature).


Suppose that we understand the spectrum of \\(H\\) completely (nb: for a given system described by \\(H\\), this is the goal). For example, suppose we know that the spectrum of \\(H\\) consists of discrete eigenvalues \\(E_n, n = 0, \cdots\\) with corresponding eigenvectors \\(|n\rangle\\),

\\[ H|n\rangle = E_n|n\rangle. \\]

(For simplicity, I assume there is no continuous spectrum and that the eigenvalues are nondegenerate.) Then we have

\\[ e^{-iHt} = \sum_n e^{-i E_n t} \langle n|n\rangle \\]

and

\\[ e^{-Ht} = \sum_n e^{-E_n t} \langle n|n\rangle \\]

Now the second expression turns out to be very useful. Assume the eigenvalues are ordered so that

\\[ E_0 &lt; E_1 &lt; \cdots \\]

Then we can write

\\[ e^{-Ht} = e^{-E_0 t} |0\rangle + \sum_{n \geq 1} e^{-(E_n-E_0)t}|n\rangle \\]

Now suppose that \\(v\\) is some vector which is close to the ground state, in the sense that

\\[ \langle v|0\rangle \neq 0 \\]

(This is obviously a generic condition, so if we just pick \\(v\\) randomly we can expect this to be true.) Then we can consider

\\[ e^{-Ht} v = e^{-E_0 t} v_0 |0\rangle + \sum_{n \geq 1} e^{-(E_n-E_0)t} v_n|n\rangle \\]

Now for \\(n \geq 1\\), \\(E_n-E_0\\) is strictly positive, and so for large \\(t\\) all of the higher terms are exponentially damped. So, we have the asymptotic

\\[ e^{-Ht} v \sim e^{-E_0 t }v_0|0\rangle \\]

Next comes the really interesting part. Multiply on the right by a position-representation eigenbra \\(\langle x|\\):

\\[ \langle x|e^{-Ht} v \sim e^{-E_0 t} v_0 \langle x|0\rangle \\]

Now \\(v_0\\) is an irrelevant constant, so we might as well take it to be 1 (rescale \\(v\\) as necessary). The expression \\(\langle x|0\rangle\\) is exactly the ground state wavefunction in the position representation! Call it \\(\psi_0(x)\\). So to conclude: the large-t asymptotic of the expression \\(\langle x|e^{-Ht}v\\) is (up to an overall constant) given by \\(e^{-E_0 t} \psi_0(x)\\), hence we can recover both the ground state energy and the ground state wavefunction. But the value of this expression is exactly given by the Euclidean path integral. So we have a correspondence:


Asymptotics of Euclidean path integral \\(\leftarrow\rightarrow\\) The spectrum of \\(H\\).


Coming next: instantons.