# BEGIN PROB

<!-- \[**Gradient Descent**\]\[5 Points\] -->

Suppose we are given a function $g(x, y) = x^2 + y^2$.

# BEGIN SUBPROB

\[2 Points\] Write down the formula for gradient of $g$.


# BEGIN SOLUTION

The gradient of $g$ is:
$$\nabla g = \begin{pmatrix} \frac{\partial g}{\partial x} \\ \frac{\partial g}{\partial y} \end{pmatrix},$$
in which: $$\frac{\partial g}{\partial x} = 2x,$$
$$\frac{\partial g}{\partial y} = 2y.$$ Indeed, $g$ is a convex
function.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[2 Points\] Start from $(x_0, y_0) = (1, -1)$, with learning rate
$\alpha = 1/4$, show the first 3 steps of gradient descent. Can the
gradient descent converge? If yes, where?

# BEGIN SOLUTION

**Step 0:** $$(x_0, y_0) = (1, -1)$$ $$\nabla g = (2, -2)$$
$$(x_1, y_1) = (x_0, y_0) - \alpha \cdot \nabla g (x_0, y_0) = (1, -1) - \frac{1}{4}(2, -2) = (1/2, -1/2)$$
**Step 1:** $$(x_1, y_1) = (1/2, -1/2)$$ $$\nabla g = (1, -1)$$
$$(x_2, y_2) = (x_1, y_1) - \alpha \cdot \nabla g (x_1, y_1) = (1/2, -1/2) - \frac{1}{4} (1, -1) = (1/4, -1/4)$$
**Step 2:** $$(x_2, y_2) = (1/4, -1/4)$$ $$\nabla g = (1/2, -1/2)$$
$$(x_3, y_3) = (x_2, y_2) - \alpha \cdot \nabla g (x_2, y_2) = (1/4, -1/4) - \frac{1}{4} (1/2, -1/2) = (1/8, -1/8)$$
**Step 3:** $$(x_3, y_3) = (1/8, -1/8)$$ $$\nabla g = (1/4, -1/4)$$
$$(x_4, y_4) = (x_3, y_3) - \alpha \cdot \nabla g (x_3, y_3) = (1/8, -1/8) - \frac{1}{4} (1/4, -1/4) = (1/16, -1/16)$$
In general, at step $k$-th, the gradient descent is at
$(x_k, y_k) = (2^{-k}, -2^{-k})$. The gradient descent converges at
$(x^*, y^*) = (0, 0)$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[1 Point\] Instead of gradient descent, find the global minimum in a
closed-form manner (i.e. solving an equation).

# BEGIN SOLUTION

We solve the equation:
$$\nabla g = \begin{pmatrix} \frac{\partial g}{\partial x} \\ \frac{\partial g}{\partial y} \end{pmatrix} = \begin{pmatrix} 2x \\ 2y \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
$$\Leftrightarrow \begin{cases} 2x = 0 \\ 2y = 0 \end{cases} \Leftrightarrow \begin{cases} x = 0 \\ y = 0 \end{cases}.$$

# END SOLUTION

# END SUBPROB

# END PROB