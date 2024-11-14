# BEGIN PROB

Suppose there is a dataset contains four values: $-2$, $-1$,
$2$, $4$. You would like to use gradient descent to minimize the mean square
error over this dataset.

# BEGIN SUBPROB

Write down the expression of mean square error and its derivative given this dataset.

# BEGIN SOLUTION

$$R_{sq}(h) = \dfrac{1}{4}\sum_{i=1}^{4}(y_i-h)^2$$

Recall the equation for $R_{sq}(h) = \frac{1}{n}\sum_{i=1}^{n}(y_i-h)^2$, so we simply need to replace $n$ with $4$ because there are $4$ elements in our dataset.

$\frac{dR_{sq}(h)}{dh} = \frac{1}{2}\sum_{i=1}^{4}(h-y_i)$

Since we have the equation for $R_{sq}(h)$ we can calculate the derivative:

$$
\begin{align*}
\frac{dR_{sq}(h)}{dh} &= \frac{dR_{sq}(h)}{dh}(\frac{1}{4}\sum_{i=1}^{4}(y_i-h)^2) \\
&= \frac{1}{4}\sum_{i=1}^{4}\frac{dR_{sq}(h)}{dh}((y_i-h)^2) \\
\end{align*}
$$
We can use the chain rule to find the derivative of $(y_i-h)^2$.
Recall the chain rule is: $\frac{df(x)}{dx}[(f(x))^n] = n(f(x))^{n-1} \cdot f'(x)$.

$$
\begin{align*}
&= \frac{1}{4}\sum_{i=1}^{4}2(y_i-h) \cdot -1 \\
&= \frac{1}{4}\sum_{i=1}^{4} 2(h - y_i) \\
&= \frac{1}{2}\sum_{i=1}^{4} (h-y_i)
\end{align*}
$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose you choose the initial position to be $h_0$ and the
learning rate to be $\frac{1}{4}$. After two gradient descent steps,
$h_2=\frac{1}{4}$. What is the value of $h_0$?

# BEGIN SOLUTION

$$h_{0} = -\frac{5}{4}$$

The gradient descent equation is given by: $$\begin{aligned}
    h_i = h_{i-1} - \alpha \frac{dR_{sq}(h_{i-1})}{dh}
\end{aligned}$$ Recall the learning rate is equal to $\alpha$. We can plug in $\alpha = \frac{1}{4}$, $h_2 = \frac{1}{4}$, and $i=2$,
in that case we obtain: $$\begin{aligned}
    \frac{1}{4} &= h_{1} - \alpha \frac{dR_{sq}(h_{1})}{dh}\\
    &= h_{1} - \alpha \frac{1}{2}\sum_{i=1}^{4}(h_1-y_i)\\
        &= h_{1} - \frac{1}{8}(h_{1} + 2 + h_{1} + 1 + h_{1} - 2 + h_{1} - 4)\\
        &= h_{1} - \frac{1}{8}(4h_{1} -3)\\
\end{aligned}$$ Solving this equation, we obtain that
$h_{1} = -\frac{1}{4}$. We can then repeat this step once more to obtain
$h_0$: $$\begin{aligned}
    -\frac{1}{4} &= h_{0} - \alpha \frac{dR_{sq}(h_{0})}{dh}\\
        &= h_{0} - \frac{1}{4}(h_{0} + 2 + h_{0} + 1 + h_{0} - 2 + h_{0} - 4)\\
        &= h_{0} - \frac{1}{8}(4h_{0} -3)\\
\end{aligned}$$ Solving this equation, we obtain that
$h_{0} = -\frac{5}{4}$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Given that we set the tolerance of gradient descent to be
$0.1$. How many **additional steps** beyond $h_2$ do we need to take to
reach convergence?

( ) 0
( ) 1
( ) 2
( ) 3
( ) 4
( ) It will never converge

# BEGIN SOLUTION

$2$ or $3$ additional steps (both are correct).

The gradient descent equation is given by: $$\begin{aligned}
    h_i = h_{i-1} - \alpha \frac{dR_{sq}(h_{i-1})}{dh}
\end{aligned}$$ Now we start from $\alpha = \frac{1}{4}$, $h_2 = \frac{1}{4}$, and
$i=2$, in that case we obtain: $$\begin{aligned}
    h_{3} &= h_{2} - \alpha \frac{dR_{sq}(h_{2})}{dh}\\
    &= h_{2} - \frac{1}{8}(4h_{2} -3)\\
    &= \frac{1}{4} - \frac{1}{8}(1 -3)\\
    &= \frac{1}{2}\\
\end{aligned}$$ Iteratively, we have: $$\begin{aligned}
    h_{4} &= h_{3} - \alpha \frac{dR_{sq}(h_{3})}{dh}\\
    &= h_{3} - \frac{1}{8}(4h_{3} -3)\\
    &= \frac{1}{2} - \frac{1}{8}(2 -3)\\
    &= \frac{5}{8}\\
\end{aligned}$$ $$\begin{aligned}
    h_{5} &= h_{4} - \alpha \frac{dR_{sq}(h_{4})}{dh}\\
    &= h_{3} - \frac{1}{8}(4h_{4} -3)\\
    &= \frac{5}{8} - \frac{1}{8}(\frac{5}{2}-3)\\
    &= \frac{11}{16}\\
\end{aligned}$$ from $h_4$ to $h_5$, the change is smaller than the
tolerance. That means we need additional $2$ or $3$ steps to reach
convergence (depending on if you actually perform $h_4$ to $h_5$, so
both $2$ and $3$ are considered correct answer).

# END SOLUTION

# END SUBPROB

# END PROB