# BEGIN PROB

The hyperbolic cosine function is defined as
$cosh(x) = \frac{1}{2}(e^{x} + e^{-x})$. In this problem, we aim to
prove the convexity of this function using power series expansion.

# BEGIN SUBPROB

Prove that $f(x) = x^{n}$ is convex if n is an even integer.

# BEGIN SOLUTION

Take the second derivative of f: 

$$\begin{align*}
        f'(x) &= nx^{n-1}\\
        f''(x) &= n(n-1)x^{n-2}
\end{align*}$$

If $n$ is even, then $n-2$ must also be even, therefore
$f''(x) = n(n-1)x^{n-2}$ will always be a positive number. This means
the second derivative of $f(x)$ is always larger than $0$ and therefore
passes the second derivative test.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Power series expansion is a powerful tool to analyze
complicated functions. In power series expansion, a function can be
written as an infinite sum of polynomial functions with certain
coefficients. For example, the exponential function can be written as:
$$\begin{align*}
        e^{x} = \sum_{n=0}^{\infty}\frac{x^{n}}{n!} = 1 + x + \frac{x^{2}}{2} + \frac{x^{3}}{6} + \frac{x^{4}}{24} + ...
\end{align*}$$ 

where $n!$ denotes the factorial of $n$, defined as the
product of all positive integers up to $n$, i.e.
$n! = 1\cdot 2\cdot 3\cdot  ... \cdot (n-1)\cdot  n$. Given the power
series expansion of $e^{x}$ above, write the power series expansion of
$e^{-x}$ and explicitly specify the first 5 terms, i.e., similar to the
format of the equation above.
<!-- 
Equation [\[exp_expand\]](#exp_expand){reference-type="ref"
reference="exp_expand"}: -->

# BEGIN SOLUTION

By plugging $-x$ in for each $x$, we get:

$e^{-x} = \displaystyle\sum_{n=0}^{\infty}\frac{(-x)^{n}}{n!}=1-x+\frac{x^{2}}{2} - \frac{x^{3}}{6}+\frac{x^{4}}{24}+ ...$

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

Using the conclusions you reached in part (a) and part (b), prove
that $cosh(x) = \frac{1}{2}(e^{x} + e^{-x})$ is convex.


# BEGIN SOLUTION

Given that: 

$$\begin{align*}
        e^{x} &= \sum_{n=0}^{\infty}\frac{x^{n}}{n!} = 1 + x + \frac{x^{2}}{2} + \frac{x^{3}}{6} + \frac{x^{4}}{24} + ....\\
        e^{-x} &= \sum_{n=0}^{\infty}\frac{(-x)^{n}}{n!} = 1 - x + \frac{x^{2}}{2} - \frac{x^{3}}{6} + \frac{x^{4}}{24} + ....
\end{align*}$$

We can add their power series expansion together, and we
will obtain: 

$$\begin{align*}
        e^{x} + e^{-x} &= \sum_{n=0}^{\infty}\frac{x^{n}}{n!} + \sum_{n=0}^{\infty}\frac{x^{n}}{n!}\\
        &=\sum_{n=0}^{\infty}\frac{(x)^{n} + (-x)^{n}}{n!}
\end{align*}$$ 

Within this infinite sum, if n is even, then the
negative sign in $(-x)^{n}$ will disappear; if n is odd, then the
negative sign in $(-x)^{n}$ will be kept and travel out of the
parenthesis. Therefore we have: 

$$\begin{align*}
        e^{x} + e^{-x} &= \sum_{n=0}^{\infty}\frac{x^{n}+x^{n}}{n!} \mathrm{(for\; even\; n)} + \sum_{n=0}^{\infty}\frac{x^{n}-x^{n}}{n!}\mathrm{(for\; odd\; n)}\\
        &=\sum_{n=0}^{\infty}\frac{2x^{n}}{n!} \mathrm{(for\; even\; n)}
\end{align*}$$

Therefore, $cosh(x)=\displaystyle\frac{e^{x}+e^{-x}}{2}$ is a sum of
$x^{n}$, where $n$ is even. Since we have already proved in part (a) that $x^{n}$
are always convex for even $n$, $cosh(x)$ is an infinite sum of convex
functions and therefore also convex.

# END SOLUTION

# END SUBPROB

# END PROB