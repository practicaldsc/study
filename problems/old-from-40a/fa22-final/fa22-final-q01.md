# BEGIN PROB

<!-- \[**Empirical Risk Minimization**\]\[15 Points\] -->

Suppose we have a data of $n$ samples:
$$\mathcal{D} = \{(\vec{x}_i, y_i)\}_{i = 1}^n,$$ in which
$\vec{x}_i \in \mathbb{R}^d$ and $y_i \in \mathbb{R}$. We also know that
$y_i$ is in the range of $[-1, 1]$. Our hypothesis is:
$$\hat{y} = h(\vec{x}) = \gamma(\vec{x} \cdot \vec{w} + w_0),$$ where
$\vec{w} \in \mathbb{R}^d$ and $w_0 \in \mathbb{R}$ are the parameters,
$\vec{x} \cdot \vec{w} = \sum_{i = 1}^d x_i w_i$ is the inner product,
and $\gamma: \mathbb{R} \rightarrow \mathbb{R}$ is the hyperbolic
tangent function, i.e.
$$\gamma(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}} = \frac{e^{2z} - 1}{e^{2z} + 1}.$$
Note that we use $\gamma$ to make sure our prediction is in the range
from $-1$ to $1$. Given the square loss function $L(y, h) = (y - h)^2$,
the empirical risk is written as:
$$R(h) = R(\vec{w}, w_0) = \frac{1}{n} \sum_{i = 1}^n L(y_i, h(\vec{x}_i)).$$

# BEGIN SUBPROB

\[5 Points\] Derive for: $$\gamma'(z) = \frac{d\gamma}{dz}.$$
Furthermore, prove that $\gamma$ is an increasing function.\
\
**Hint:** Quotient rule for differentiation:
$$\bigg(\frac{u(x)}{v(x)}\bigg)' = \frac{u'(x)v(x) - u(x)v'(x)}{[v(x)]^2}.$$

# BEGIN SOLUTION

We have:
$$\gamma'(z) = \bigg(\frac{e^{2z} - 1}{e^{2z} + 1}\bigg)' = \frac{(e^{2z} - 1)'(e^{2z} + 1) - (e^{2z} + 1)'(e^{2z} - 1)}{(e^{2z} + 1)^2} = \frac{2e^{2z}(e^{2z} + 1) - 2e^{2z}(e^{2z} - 1) }{(e^{2z} + 1)^2}$$
$$\Leftrightarrow \gamma'(z) = \frac{4e^{2z}}{(e^{2z} + 1)^2} = \bigg(\frac{2e^z}{e^{2z} + 1}\bigg)^2 = \bigg(\frac{2}{e^{z} + e^{-z}}\bigg)^2.$$
Furthermore, we have the hyperbolic cosine function:
$$\cosh z = \frac{e^z + e^{-z}}{2},$$ thus we can write:
$$\gamma'(z) = \frac{1}{\cosh^2 z}.$$ Because $\gamma'(z)$ is square of
$\cosh^{-1} x$, we have $\gamma'(z) > 0$ for all $z$. Thus, $\gamma$ is
an increasing function.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[5 Points\] Derive: $$\frac{dh}{dw_0},$$ and
$$\frac{\partial h}{\partial \vec{w}}.$$

# BEGIN SOLUTION

We have:
$$\frac{dh}{dw_0} = \gamma'(\vec{x} \cdot \vec{w} + w_0) \cdot \frac{\partial}{\partial w_0}(\vec{x} \cdot \vec{w} + w_0) = \gamma'(\vec{x} \cdot \vec{w} + w_0),$$
$$\frac{\partial h}{\partial \vec{w}} = \gamma'(\vec{x} \cdot \vec{w} + w_0) \cdot \frac{\partial}{\partial \vec{w}}(\vec{x} \cdot \vec{w} + w_0) = \gamma'(\vec{x} \cdot \vec{w} + w_0) \cdot \vec{x}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[5 Points\] Derive: $$\frac{dR}{dw_0},$$ and
$$\frac{\partial R}{\partial \vec{w}}.$$


# BEGIN SOLUTION

Given $$R(h) = \frac{1}{n} \sum_{i = 1}^n (y_i - h(\vec{x}_i))^2,$$ we
have:
$$\frac{dR}{dw_0} = -\frac{2}{n} \sum_{i = 1}^n (y_i - h(\vec{x}_i)) \cdot \frac{dh}{dw_0}(\vec{x}_i) = -\frac{2}{n} \sum_{i = 1}^n (y_i - h(\vec{x}_i)) \cdot \gamma'(\vec{x}_i \cdot \vec{w} + w_0),$$
and
$$\frac{\partial R}{\partial \vec{w}} = -\frac{2}{n} \sum_{i = 1}^n (y_i - h(\vec{x}_i)) \cdot \frac{\partial h}{\partial \vec{w}}(\vec{x}_i) = -\frac{2}{n} \sum_{i = 1}^n (y_i - h(\vec{x}_i)) \cdot \gamma'(\vec{x} \cdot \vec{w} + w_0) \cdot \vec{x}_i.$$

# END SOLUTION

# END SUBPROB

# END PROB