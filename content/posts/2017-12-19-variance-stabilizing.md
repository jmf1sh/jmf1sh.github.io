+++
title = "Variance Stabilizing Transformations"
date = 2017-12-19T13:49:09+01:00
draft = false
categories = ["statistics"]
tags = ["data-analysis"]
+++

I want to record here a very interesting thing which I recently discovered, [variance-stabilizing transformations](https://en.wikipedia.org/wiki/Variance-stabilizing_transformation). The idea is very simple: suppose we have a random variable $x$, which follows a probability distribution which is parametrized solely by its mean $\mu$, with variance $var(x) = g(\mu)$ a known function of the mean.

Now, suppose we take the new random variable $y = f(x)$, for some yet-to-be-determined function $f$. Assuming that $x$ is reasonably localized about its mean, we can make the approximation

$ f(x) = f(\mu + (x-\mu)) \approx f(\mu) + f'(\mu)(x-\mu). $

Then we have

$$
\\begin{align}
E[y] &\approx f(\mu) \\\\\\
var(y) &\approx f'(\mu)^2 var(x) \\\\\\
 &= f'(\mu)^2 g(\mu)
\\end{align}
$$

Now, suppose we want to choose $f(x)$ so that $var(y) \approx 1$. Using the above approximation, we have $ f'(\mu) = \frac{1}{\sqrt{g(\mu)}} $, which we can solve as

$ f(\mu) = \int \frac{1}{\sqrt{g(\mu)}} d\mu$

Now let's take the special case of the Poisson distrubution, where $var(x) = \mu$. Then $f(\mu) = \int \frac{1}{\sqrt \mu} d\mu = 2\sqrt{\mu}$. This is very nearly the [Anscombe transform](https://en.wikipedia.org/wiki/Anscombe_transform) $x \mapsto 2\sqrt{x+3/8}$. The additional shift by $3/8$ can be understood by doing a more careful analysis of the variance under the transformation.
