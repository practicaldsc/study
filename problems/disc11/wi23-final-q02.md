# BEGIN PROB

<!-- Convexity Problem -->

Let $f(x):\mathbb{R}\to\mathbb{R}$ be a convex function. $f(x)$ is not
necessarily differentiable. Use the definition of
convexity to prove the following: \begin{aligned}
            2f(2) \leq f(1)+f(3)
\end{aligned}

# BEGIN SOLUTION

Here is the definition of convexity:

$$f(tx_{1}+(1-t)x_{2})\leq tf(x_{1})+(1-t)f(x_{2})$$ 

Since $f(x)$ is a convex function, we know that this inequality is satisfied for all choices of $x_1$ and $x_2$ on the real number line and all choices of $t \in [0, 1]$. This problem boils down to finding a choice of $x_1$, $x_2$, and $t$ to morph the definition of convexity into our desired inequality.

One such successful combination is $x_1=1$, $x_2=3$, and $t=0.5$. This makes $tx_{1}+(1-t)x_{2}=0.5\cdot 1 + (1 - 0.5)\cdot 3=2$. Therefore:
$$f(tx_{1}+(1-t)x_{2})=f(2) \leq 0.5f(x_{1})+f(x_{2})=0.5 (f(1)+f(3))$$
$$2f(2) \leq f(1)+f(3)$$.

The strategy for these variable choices boils down to trying to make the left side of the definition of convexity "look more" like the left side of our desired inequality, and trying to make the right side of the definition of convexity "look more" like the right side of our desired inequality.

# END SOLUTION

# END PROB
