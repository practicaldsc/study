# BEGIN PROB

Suppose we’d like to use gradient descent to minimize the function $f(x) = x^3 + x^2$. Suppose we choose a learning rate of $\alpha = \frac{1}{4}$.

# BEGIN SUBPROB

Suppose $x^{(t)}$ is our guess of the minimizing input $x^{*}$ at timestep $t$, i.e. $x^{(t)}$ is the result of performing $t$ iterations of gradient descent, given some initial guess. Write an expression for $x^{(t+1)}$. Your answer should be an expression involving $x^{(t)}$ and some constants.

# BEGIN SOLUTION

In general, the update rule for gradient descent is:
$$x^{(t+1)} = x^{(t)} - \alpha \nabla f(x^{(t)}) = x^{(t)} - \alpha \frac{df}{dx}(x^{(t)}),$$
where $\alpha$ is the learning rate or step size. 
We know that the derivative of $f$ is as follows: 
$$\frac{df}{dx} = f'(x) = 3x^2 + 2x,$$ thus the update
rule can be written down as:
$$x^{(t+1)} = x^{(t)} - \alpha(3x^{(t)^2} + 2x^{(t)}) = -\frac{3}{4}x^{(t)^2} + \frac{1}{2}x^{(t)}.$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose $x^{(0)} = -1$.

 -  What is the value of $x^{(1)}$?

 -  Will gradient descent eventually converge, given the initial guess $x^{(0)} = -1$ and step size $\alpha = \frac{1}{4}$?

# BEGIN SOLUTION

We have $$f'(x^{(0)}) = f'(-1) = 3(-1)^2 + 2(-1) = 1 > 0,$$ so we go **left**,
and $$x^{(1)} = x^{(0)} - \alpha f'(x^{(0)}) = -1 - \frac{1}{4} = -\frac{5}{4}.$$
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
$x = 0$. If the gradient descent starts at $x^{(0)} = -1$ and it always goes
left then it will never meet the local minimum at $x = 0$, and it will
go left infinitely. We say the gradient descent cannot converge, or is
divergent.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose $x^{(0)} = 1$.

 -  What is the value of $x^{(1)}$?

 -  Will gradient descent eventually converge, given the initial guess $x^{(0)} = 1$ and step size $\alpha = \frac{1}{4}$?

# BEGIN SOLUTION

We have $$f'(x^{(0)}) = f'(-1) = 3 \cdot 1^2 + 2 \cdot 1 = 5 > 0,$$ so we go
**left**, and 
$$x^{(1)} = x^{(0)} - \alpha f'(x^{(0)}) = 1 - \frac{1}{4} \cdot 5 = -\frac{1}{4}.$$

From the previous part, function $f$ has a local minimum at $x = 0$, so
the gradient descent **can converge** (given appropriate step size) at this
local minimum.

# END SOLUTION

# END SUBPROB


# END PROB