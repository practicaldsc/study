# BEGIN PROB

Suppose that we are given $f(x) = x^3 + x^2$ and learning rate
$\alpha = 1/4$.

# BEGIN SUBPROB

Write down the updating rule for gradient
descent in general, then write down the updating rule for gradient descent for the function $f(x)$.

# BEGIN SOLUTION

In general, the updating rule for gradient descent is:
$$x_{i + 1} = x_i - \alpha \nabla f(x_i) = x_i - \alpha \frac{\partial f}{\partial x}(x_i),$$
where $\alpha \in \mathbb{R}_+$ is the learning rate or step size. For
this function, since $f$ is a single-variable function, we can write
down the updating rule as:
$$x_{i + 1} = x_i - \alpha \frac{df}{dx}(x_i) = x_i - \alpha f'(x_i).$$
We also have: $$\frac{df}{dx} = f'(x) = 3x^2 + 2x,$$ thus the updating
rule can be written down as:
$$x_{i + 1} = x_i - \alpha(3x_i^2 + 2x_i) = -\frac{3}{4} x_i^2 + \frac{1}{2}x_i.$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

If we start at $x_0 = -1$, should we go left or right? Can
you verify this mathematically? What is $x_1$? Can gradient descent converge?
If so, where it might converge to, given appropriate step size? 

# BEGIN SOLUTION

We have $$f'(x_0) = f'(-1) = 3(-1)^2 + 2(-1) = 1 > 0,$$ so we go **left**,
and $$x_1 = x_0 - \alpha f'(x_0) = -1 - \frac{1}{4} = -\frac{5}{4}.$$
Intuitively, the gradient descent **cannot converge in this case** because
$$\text{lim}_{x \rightarrow -\infty} f(x) = -\infty,$$ 

We need to find
all local minimums and local maximums. First, we solve the equation
$f'(x) = 0$ to find all critical points. 

We have:
$$f'(x) = 0 \Leftrightarrow 3x^2 + 2x = 0 \Leftrightarrow x = -\frac{2}{3} \ \ \text{and} \ \ x = 0.$$

Now, we consider the second-order derivative:
$$f''(x) = \frac{d^2f}{dx^2} = 6x + 2.$$ 

We have $f''(x) = 0$ only when $x = -1/3$. Thus, for $x < -1/3$, 
$f''(x)$ is negative or the slope $f'(x)$ decreases; and for $x > -1/3$,
$f''(x)$ is positive or the slope $f'(x)$ increases. Keep in mind that 
$-1 < -2/3 < -1/3 < 0 < 1$.

Therefore, $f$ has a local maximum at $x = -2/3$ and a local minimum at
$x = 0$. If the gradient descent starts at $x_0 = -1$ and it always goes
left then it will never meet the local minimum at $x = 0$, and it will
go left infinitely. We say the gradient descent cannot converge, or is
divergent.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

If we start at $x_0 = 1$, should we go left or right? Can
you verify this mathematically? What is $x_1$? Can gradient descent converge?
If so, where it might converge to, given appropriate step size?

# BEGIN SOLUTION

We have $$f'(x_0) = f'(-1) = 3 \cdot 1^2 + 2 \cdot 1 = 5 > 0,$$ so we go
**left**, and 
$$x_1 = x_0 - \alpha f'(x_0) = 1 - \frac{1}{4} \cdot 5 = -\frac{1}{4}.$$

From the previous part, function $f$ has a local minimum at $x = 0$, so
the gradient descent **can converge** (given appropriate step size) at this
local minimum.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Write down $1$ condition to terminate the gradient descent
algorithm (in general).

# BEGIN SOLUTION

There are several ways to terminate the gradient descent algorithm:

-   If the change in the optimization objective is too small, i.e.
    $|f(x_i) - f(x_{i + 1})| < \epsilon$ where $\epsilon$ is a small
    constant,

-   If the gradient is close to zero or the norm of the gradient is very
    small, i.e. $\|\nabla f(x_i)\| < \lambda$ where $\lambda$ is a small
    constant.

# END SOLUTION

# END SUBPROB

# END PROB