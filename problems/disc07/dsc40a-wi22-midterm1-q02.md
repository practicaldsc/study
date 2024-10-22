# BEGIN PROB

Consider a new loss function,
$$L(h, y) = e^{(h-y)^2}.$$
Given a dataset $y_1, y_2, \dots, y_n$, let $R(h)$ represent the empirical risk for the dataset using this loss function.

# BEGIN SUBPROB

For the dataset $\{1, 3, 4\}$, calculate $R(2).$ Simplify your answer as much as possible without a calculator.

# BEGIN SOLUTION

$$R(2) = \frac13 (2e+e^4)$$

We need to calculate the loss for each data point then average the losses. That is, we need to calculate
$$R(2) = \dfrac{1}{3} \sum_{i=1}^{3} e^{(2-y_i)^2}.$$
The table below records the necessary information:

| $y_i$           | 1   | 3   | 4     |
| :-------------- | :-- | :-- | :---- |
| $2-y_i$         | 1   | -1  | -2    |
| $(2-y_i)^2$     | 1   | 1   | 4     |
| $e^{(2-y_i)^2}$ | $e$ | $e$ | $e^4$ |

<br>

This means:
$$\begin{aligned} R(2) &= \dfrac{1}{3} \sum_{i=1}^{3} e^{(2-y_i)^2} \\ &= \frac13 (e+e+e^4) \\ &= \frac13 (2e+e^4)  \end{aligned}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

For the same dataset $\{1, 3, 4\}$, perform one iteration of gradient descent on $R(h)$, starting at an initial prediction of $h_0=2$ with a step size of $\alpha=\frac{1}{2}$. Show your work and simplify your answer.

# BEGIN SOLUTION

$$h_1 = 2 + \frac{2e^4}{3}$$

First, we calculate the derivative of $R(h)$. Using the chain rule, we have

$$
\begin{align*} R(h) &= \dfrac1n \sum_{i=1}^n e^{(h-y_i)^2} \\
R'(h) &= \dfrac1n \sum_{i=1}^n e^{(h-y_i)^2}\cdot 2(h-y_i) \\
\end{align*}
$$

To apply the gradient descent update rule, we next have to calculate $R'(h_0)$ or $R'(2)$.
Plugging in $h=2$ to the derivative we calculated above gives:

$$
\begin{align*}
R'(2) &= \dfrac1n \sum_{i=1}^n e^{(2-y_i)^2}\cdot 2(2-y_i) \end{align*}
$$

The table below records the necessary information (note
that we've done most of the work already).

<div>
|          $y_i$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;      |  1    |   3    |    4    |
|--------------------------|------|-------|---------|
|         $2-y_i$           |  1    |  -1    |   -2    |
|       $(2-y_i)^2$         |  1    |   1    |    4    |
|     $e^{(2-y_i)^2}$       | $e$   |  $e$   |  $e^4$  |
| $e^{(2-y_i)^2}\cdot 2(2-y_i)$  | $2e$  | $-2e$  | $-4e^4$ |
</div>

<br>

Therefore:
$$\begin{aligned} R'(2) &= \dfrac{1}{3} \sum_{i=1}^{3} e^{(2-y_i)^2\cdot 2(2-y_i)} \\ &= \frac13 (2e - 2e -4e^4) \\ &= \frac{-4e^4}{3}. \end{aligned}$$
Applying the gradient descent update rule gives:
$$\begin{aligned} h_1 &= h_0 - \alpha\cdot R'(h_0) \\ &= 2 - \frac{1}{2}\cdot \frac{-4e^4}{3} \\ &= 2 + \frac{2e^4}{3} \end{aligned}$$

# END SOLUTION

# END SUBPROB

# END PROB
