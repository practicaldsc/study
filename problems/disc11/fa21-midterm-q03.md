# BEGIN PROB

Suppose we want to minimize the function

$$R(h) = e^{(h + 1)^2}$$

# BEGIN SUBPROB

Without using gradient descent or calculus, what is the
value $h^*$ that minimizes $R(h)$?

# BEGIN SOLUTION

$$h^* = -1$$

The minimum possible value of the exponent is $0$, since anything
squared is non-negative. The exponent is 0 when $(x+1)^2 = 0$, i.e. when
$x = -1$. Since $e^{(x+1)^2}$ gets larger as $(x+1)^2$ gets larger, the
minimizing input $h^*$ is $-1$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Now, suppose we want to use gradient descent to minimize
$R(h)$. Assume we use an initial guess of $h^{(0)} = 0$. What is $h^{(1)}$? Give
your answer in terms of a generic step size, $\alpha$, and other
constants. ($e$ is a constant.)

# BEGIN SOLUTION

$$h^{(1)} = -\alpha \cdot 2e$$

First, we find $\frac{dR}{dh}(h)$:

$$\frac{dR}{dh}(h) = 2(h+1) e^{(h+1)^2}$$

Then, we know that

$$h^{(1)} = h^{(0)} - \alpha \frac{dR}{dh}(h^{(0)}) = 0 - \alpha \frac{dR}{dh}(0)$$

In our case, $\frac{dR}{dh}(0) = 2(0 + 1) e^{(0+1)^2} = 2e$, so

$$h^{(1)} = -\alpha \cdot 2e$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Using your answers from the previous two parts, what
should we set the value of $\alpha$ to be if we want to ensure that
gradient descent finds $h^*$ after just one iteration?

# BEGIN SOLUTION

$$\alpha = \frac{1}{2e}$$

We know from the part 2 that $h^{(1)} = -\alpha \cdot 2e$, and we know from part
1 that $h^* = -1$. If gradient descent converges in one iteration, that
means that $h^{(1)} = h^*$; solving this yields

$$-\alpha \cdot 2e = -1 \implies \alpha = \frac{1}{2e}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Below is a graph of $R(h)$ with no axis labels.

<!-- TODO -->

<center><img src="../assets/images/disc11/graph.png" width="500" height="350"></center>

True or False: Given an appropriate choice of step size, $\alpha$,
gradient descent is guaranteed to find the minimizer of $R(h)$.

# BEGIN SOLUTION

True.

$R(h)$ is convex, since the graph is bowl shaped. (It can also
be proved that $R(h)$ is convex using the second derivative test.) It is
also differentiable, as we saw in part 2. As a result, since it's both
convex and differentiable, gradient descent is guaranteed to be able to
minimize it given an appropriate choice of step size.

# END SOLUTION

# END SUBPROB

# END PROB
