# BEGIN PROB

Consider the dataset of four values, $y_1 = -2, y_2 = -1, y_3 = 2, y_4 = 4$. Suppose we’d like to use gradient descent to find the constant prediction, $h^*$, that minimizes mean squared error on this dataset.

# BEGIN SUBPROB

Write down the expression of mean square error and its derivative given this dataset.

# BEGIN SOLUTION

$$R_\text{sq}(h) = \dfrac{1}{4}\sum_{i=1}^{4}(y_i-h)^2$$

Recall the equation for $R_\text{sq}(h) = \frac{1}{n}\sum_{i=1}^{n}(y_i-h)^2$, so we simply need to replace $n$ with $4$ because there are $4$ elements in our dataset.

$\frac{dR_\text{sq}(h)}{dh} = \frac{1}{2}\sum_{i=1}^{4}(h-y_i)$

Since we have the equation for $R_\text{sq}(h)$ we can calculate the derivative:

$$
\begin{align*}
\frac{dR_\text{sq}(h)}{dh} &= \frac{dR_\text{sq}(h)}{dh}(\frac{1}{4}\sum_{i=1}^{4}(y_i-h)^2) \\
&= \frac{1}{4}\sum_{i=1}^{4}\frac{dR_\text{sq}(h)}{dh}((y_i-h)^2) \\
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

Suppose you choose an initial guess of $h^{(0)}$ and a learning rate of $\alpha = \frac{1}{4}$. After two gradient descent steps, $h^{(2)} = \frac{1}{4}$. What is the value of $h^{(0)}$?

# BEGIN SOLUTION

$$h^{(0)} = -\frac{5}{4}$$

The gradient descent equation is given by: 
$$\begin{aligned}
    h^{(t)} &= h^{(t-1)} - \alpha \frac{dR_{sq}(h^{(t-1)})}{dh}
\end{aligned}$$ 

Recall the learning rate is equal to $\alpha$. We can plug in $\alpha = \frac{1}{4}$, $h^{(2)} = \frac{1}{4}$, and $i=2$,
in that case we obtain: 
$$\begin{aligned}
    \frac{1}{4} &= h^{(1)} - \alpha \frac{dR_{sq}(h^{(1)})}{dh}\\
    &= h^{(1)} - \alpha \frac{1}{2}\sum_{i=1}^{4}(h^{(1)}-y^{(i)})\\
    &= h^{(1)} - \frac{1}{4} \cdot \frac{1}{2}(h^{(1)} + 2 + h^{(1)} + 1 + h^{(1)} - 2 + h^{(1)} - 4)\\
    &= h^{(1)} - \frac{1}{8}(4h^{(1)} - 3)\\
\end{aligned}$$ 

Solving this equation, we obtain that $h^{(1)} = -\frac{1}{4}$. We can then repeat this step once more to obtain
$h^{(0)}$: 
$$\begin{aligned}
    -\frac{1}{4} &= h^{(0)} - \alpha \frac{dR_{sq}(h^{(0)})}{dh}\\
    &= h^{(0)} - \frac{1}{4} \cdot \frac{1}{2}(h^{(0)} + 2 + h^{(0)} + 1 + h^{(0)} - 2 + h^{(0)} - 4)\\
    &= h^{(0)} - \frac{1}{8}(4h^{(0)} - 3)\\
\end{aligned}$$ 

Solving this equation, we obtain that $h^{(0)} = -\frac{5}{4}$.

# END SOLUTION

# END SUBPROB

# END PROB
