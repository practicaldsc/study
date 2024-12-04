# BEGIN PROB

Consider a dataset of $n$ values, $y_1, y_2, ..., y_n$, all of which are non-negative. We're interested in fitting a constant model, $H(x) = h$, to the data, using the new "Wolverine" loss function:

$$L_\text{wolverine}(y_i, h) = w_i \left( y_i^2 - h^2  \right)^2$$

Here, $w_i$ corresponds to the "weight" assigned to the data point $y_i$, the idea being that different data points can be weighted differently when finding the optimal constant prediction, $h^*$.

For example, for the dataset $y_1 = 1, y_2 = 5, y_3 = 2$, we will end up with different values of $h^*$ when we use the weights $w_1 = w_2 = w_3 = 1$ and when we use weights $w_1 = 8, w_2 = 4, w_3 = 3$.

# BEGIN SUBPROB

Find $\frac{\partial L_\text{wolverine}}{\partial h}$, the derivative of the Wolverine loss function with respect to $h$. Show your work.

# BEGIN SOLUTION

$\frac{\partial L}{\partial h} = -4w_ih(y_i^2 -h^2)$

To solve this problem we simply take the derivative of $L_\text{wolverine}(y_i, h) = w_i( y_i^2 - h^2 )^2$.

We can use the chain rule to find the derivative. The chain rule is: $\frac{\partial}{\partial h}[f(g(h))]=f'(g(h))g'(h)$.

Note that $(y_i^2 -h^2)^2$ is the area we care about inside of $L_\text{wolverine}(y_i, h) = w_i( y_i^2 - h^2 )^2$ because that is where $h$ is!. In this case $f(h) = h^2$ and $g(h) = y_i^2 - h^2$. We can then take the derivative of both to get: $f'(h) = 2h$ and $g'(x) = -2h$.

This tells us the derivative is: $\frac{\partial L}{\partial h} = (w_i) * 2(y_i^2 -h^2) * (-2h)$, which can be simplified to $\frac{\partial L}{\partial h} = -4w_ih(y_i^2 -h^2)$.

<average>88</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Prove that the constant prediction that minimizes average loss for the Wolverine loss function is:

$$h^* = \sqrt{\frac{\sum_{i = 1}^n w_i y_i^2}{\sum_{i = 1}^n w_i}}$$

# BEGIN SOLUTION

The recipe for average loss is to find the derivative of the risk function, set it equal to zero, and solve for $h^*$.

We know that average loss follows the equation $R(L(y_i, h)) = \frac{1}{n} \sum_{i=1}^n L(y_i, h)$. This means that $R_\text{wolverine}(h) = \frac{1}{n} \sum_{i = 1}^n w_i (y_i^2 - h^2)^2$.

Recall we have already found the derivative of $L_\text{wolverine}(y_i, h) = w_i ( y_i^2 - h^2)^2$. Which means that $\frac{\partial R}{\partial h}(h) = \frac{1}{n} \sum_{i = 1}^n \frac{\partial L}{\partial h}(h)$. So we can set $\frac{\partial}{\partial h}(h) R_\text{wolverine}(h) = \frac{1}{n} \sum_{i = 1}^n -4hw_i(y_i^2 -h^2)$.

We can now do the last two steps:
\begin{align*}
0 &= \frac{1}{n} \sum_{i = 1}^n -4hw_i(y_i^2 -h^2)\\
0&= \frac{-4h}{n} \sum_{i = 1}^n w_ih(y_i^2 -h^2)\\
0&= \sum_{i = 1}^n w_i(y_i^2 -h^2)\\
0&= \sum_{i = 1}^n w_iy_i^2 -w_ih^2\\
0&= \sum_{i = 1}^n w_iy_i^2 - \sum_{i = 1}^n w_ih^2\\
\sum_{i = 1}^n w_ih^2 &= \sum_{i = 1}^n w_iy_i^2\\
h^2\sum_{i = 1}^n w_i &= \sum_{i = 1}^n w_iy_i^2\\
h^2 &= \frac{\sum_{i = 1}^n w_iy_i^2}{\sum_{i = 1}^n w_i}\\
h^* &= \sqrt{\frac{\sum_{i = 1}^n w_iy_i^2}{\sum_{i = 1}^n w_i}}
\end{align*}

<average>77</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

For a dataset of non-negative values $y_1, y_2, ..., y_n$ with weights $w_1, 1, ..., 1$, evaluate: $$\displaystyle \lim_{w_1 \rightarrow \infty} h^*$$

( ) The maximum of $y_1, y_2, ..., y_n$
( ) The mean of $y_1, y_2, ..., y_{n-1}$
( ) The mean of $y_2, y_3, ..., y_n$
( ) The mean of $y_2, y_3, ..., y_n$, multiplied by $\frac{n}{n-1}$
( ) $y_1$
( ) $y_n$

# BEGIN SOLUTION

$y_1$

Recall from part b $h^* = \sqrt{\frac{\sum_{i = 1}^n w_i y_i^2}{\sum_{i = 1}^n w_i}}$.

The problem is asking us $\lim_{w_1 \rightarrow \infty} \sqrt{\frac{\sum_{i = 1}^n w_i y_i^2}{\sum_{i = 1}^n w_i}}$.

We can further rewrite the problem to get something like this: $\lim_{w_1 \rightarrow \infty} \sqrt{\frac{w_1 y_1^2 + \sum_{i=1}^{n-1}y_i^2}{w_1 + (n-1)}}$. Note that $\frac{\sum_{i=1}^{n-1}y_i^2}{n-1}$ is insignificant because it is a constant. Constants compared to infinity can be ignored. We now have something like $\sqrt{\frac{w_1y_1^2}{w_1}}$. We can cancel out the $w_1$ to get $\sqrt{y_1^2}$, which becomes $y_1$.

<average>48</average>

# END SOLUTION

# END SUBPROB

# END PROB
