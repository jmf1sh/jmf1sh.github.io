---
title: "Geometry of curved spacetime, part 3"
date: 2012-02-04
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Today, some numerology. The Riemann curvature tensor is a tensor \(R_{abcd}\) satisfying the identities:


1. \(R_{abcd} = -R_{bacd}.\)


2. \(R_{abcd} = R_{cdba}. \)


3. \(R_{abcd} + R_{acdb} + R_{adbc} = 0. \) (First Bianchi)


4. \(R_{abcd|e} + R_{acec|d} + R_{abde|c} = 0. \) (Second Bianchi)


By 1, the number of independent \(ab\) indices is \(N = n(n-1)/2\), and similarly for \(cd\). By 2, the number of independent pairs of indices is \(N(N+1)/2\). Now the cyclic constraint 3 can be written as

\[ R_{[abcd]} = 0, \]

and thus constitutes \({n \choose 4}\) equations. So the number of independent components is

\begin{align}

 N(N+1)/2 - {n \choose 4} &amp;= \frac{n(n-1)((n(n-1)/2+1)}{4} - \frac{n(n-1)(n-2)(n-3)}{24} \\

&amp;= \frac{(n^2-n)(n^2-n+2)}{8} - \frac{(n^2-n)(n^2-5n+6}{24} \\

&amp;= \frac{n^4-2n^3+3n^2+2n}{8} - \frac{n^4-6n^3+11n^2-6n}{24} \\

&amp;= \frac{2n^4-2n^2}{24} \\

&amp;= \frac{n^4-n^2}{12} \\

&amp;= \frac{n^2(n^2-1)}{12}

\end{align}


Now consider the Weyl tensor \(C_{abcd}\) which is defined as the completely trace-free part of the Rienmann tensor. The trace is determined by the Ricci tensor \(R_{ab}\) which as \(n(n+1)/2\) indepdendent components, so the Weyl tensor has

\[ \frac{n^2(n^2-1)}{12} - \frac{n^2-n}{2} = \frac{n^4-7n^2+6n}{12} \]

independent components. Now, for \(n = 1\) we see that \(R_{abcd}\) has no independent components, i.e. it vanishes identically. In \(n=2\), it has only 1 independent component, and so the scalar curvature determines everything. In \(n=3\), it has 6 independent components. Note that in this case, the Weyl tensor has no independent components, i.e. it is identically 0. So we see that in \(n = 2, 3\) every Riemannian manifold is conformally flat. So things only start to get really interesting in \(n=4\), where the Riemann tensor has 20 independent components, and the Weyl tensor has 10.