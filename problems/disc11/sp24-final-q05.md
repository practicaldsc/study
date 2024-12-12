# BEGIN PROB

Let $\vec{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$. Consider the
function $g(\vec{x}) = (x_1 - 3)^2 + (x_1^2 - x_2)^2$.

# BEGIN SUBPROB

Find $\nabla g(\vec{x})$, the gradient of $g(\vec{x})$, and use it to
show that
$\nabla g\left( \begin{bmatrix} -1 \\ 1 \end{bmatrix} \right) = \begin{bmatrix} -8 \\ 0 \end{bmatrix}$.

# BEGIN SOLUTION

$$\nabla g(\vec{x}) = \begin{bmatrix} 2x_1 -6 + 4x_1(x_1^2 - x_2) \\ -2(x_1^2 - x_2) \end{bmatrix}$$

We can find $\nabla g(\vec{x})$ by finding the partial derivatives of $g(\vec{x})$:

$$\frac{\partial g}{\partial x_1} = 2(x_1 - 3) + 2(x_1^2 - x_2)(2 x_1)$$
$$\frac{\partial g}{\partial x_2} = 2(x_1^2 - x_2)(-1)$$
$$\nabla g(\vec{x}) = \begin{bmatrix} 2(x_1 - 3) + 2(x_1^2 - x_2)(2 x_1) \\ 2(x_1^2 - x_2)(-1) \end{bmatrix}$$
$$\nabla g\left(\begin{bmatrix} - 1 \\ 1 \end{bmatrix}\right) = \begin{bmatrix} 2(-1 - 4) + 2((-1)^2 - 1)(2(-1)) \\ 2((-1)^2 - 1) \end{bmatrix} = \begin{bmatrix} -8 \\ 0 \end{bmatrix}$$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

We'd like to find the vector $\vec{x}^*$ that minimizes $g(\vec{x})$
using gradient descent. Perform one iteration of gradient descent by
hand, using the initial guess
$\vec{x}^{(0)} = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$ and the learning
rate $\alpha = \frac{1}{2}$. In other words, what is $\vec{x}^{(1)}$?

# BEGIN SOLUTION

$$\vec x^{(1)} = \begin{bmatrix} 3 \\ 1 \end{bmatrix}$$

Here's the general form of gradient descent:
$$\vec x^{(1)} = \vec{x}^{(0)} - \alpha \nabla g(\vec{x}^{(0)})$$

We can substitute $\alpha = \frac{1}{2}$ and $x^{(0)} = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$ to get:
$$\vec x^{(1)} = \begin{bmatrix} -1 \\ 1 \end{bmatrix} - \frac{1}{2} \nabla g(\vec x ^{(0)})$$
$$\vec x^{(1)} = \begin{bmatrix} -1 \\ 1 \end{bmatrix} - \frac{1}{2} \begin{bmatrix} -8 \\ 0 \end{bmatrix}$$

$$\vec{x}^{(1)} = \begin{bmatrix} -1 \\ 1 \end{bmatrix} - \frac{1}{2} \begin{bmatrix} -8 \\ 0 \end{bmatrix} = \begin{bmatrix} 3 \\ 1 \end{bmatrix}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Consider the function $f(t) = (t - 3)^2 + (t^2 - 1)^2$. Select the true
statement below.

( ) $f(t)$ is convex and has a global minimum.
( ) $f(t)$ is not convex, but has a global minimum.
( ) $f(t)$ is convex, but doesn't have a global minimum.
( ) $f(t)$ is not convex and doesn't have a global minimum.

# BEGIN SOLUTION

$f(t)$ is not convex, but has a global minimum.

It is seen that $f(t)$ isn't convex, which can be verified using the second derivative test:
$$f'(t) = 2(t - 3) + 2(t^2 - 1) 2t = 2t - 6 + 4t^3 - 4t = 4t^3 - 2t - 6$$
$$f''(t) = 12t^2 - 2$$

Clearly, $f''(t) < 0$ for many values of $t$ (e.g. $t = 0$), so $f(t)$ is not always convex.

However, $f(t)$ does have a global minimum – its output is never less than 0. This is because it can be expressed as the sum of two squares, $(t - 3)^2$ and $(t^2 - 1)^2$, respectively, both of which are greater than or equal to 0.

# END SOLUTION

# END SUBPROB

# END PROB
