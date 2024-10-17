# BEGIN PROB

<!-- <i>Source: [Spring 2024 Final](../sp24-final/index.html), Problem 3</i> -->

Suppose we're given a dataset of $n$ points,
$(x_1, y_1), (x_2, y_2), ..., (x_n, y_n)$, where $\bar{x}$ is the mean
of $x_1, x_2, ..., x_n$ and $\bar{y}$ is the mean of
$y_1, y_2, ..., y_n$.

Using this dataset, we create a _transformed_ dataset of $n$ points,
$(x_1', y_1'), (x_2', y_2'), ..., (x_n', y_n')$, where:

$$x_i' = 4x_i - 3 \qquad y_i' = y_i + 24$$

That is, the transformed dataset is of the form
$(4x_1 - 3, y_1 + 24), ..., (4x_n - 3, y_n + 24)$.

We decide to fit a simple linear hypothesis function
$H(x') = w_0 + w_1x'$ on the transformed dataset using squared loss. We
find that $w_0^* = 7$ and $w_1^* = 2$, so $H^*(x') = 7 + 2x'$.

# BEGIN SUBPROB

Suppose we were to fit a simple linear hypothesis function through the
original dataset, $(x_1, y_1), (x_2, y_2), ..., (x_n, y_n)$, again using
squared loss. What would the optimal slope be?

( ) $2$
( ) $4$
( ) $6$
( ) $8$
( ) $11$
( ) $12$
( ) $24$

# BEGIN SOLUTION

$8.$

Relative to the dataset with $x'$, the dataset with $x$ has an $x$-variable that's "compressed" by a factor of 4, so the slope increases by a factor of 4 to $2 \cdot 4 = 8$.

Concretely, this can be shown by looking at the formula $2 = r\frac{SD(y')}{SD(x')}$, recognizing that $SD(y') = SD(y)$ since the $y$ values have the same spread in both datasets, and that $SD(x') = 4 SD(x)$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Recall, the hypothesis function $H^*$ was fit on the transformed
dataset,

$(x_1', y_1'), (x_2', y_2'), ..., (x_n', y_n')$. $H^*$ happens to pass
through the point $(\bar{x}, \bar{y})$. What is the value of $\bar{x}$?
Give your answer as an integer with no variables.

# BEGIN SOLUTION

$5$.

The key idea is that the regression line always passes through $(\text{mean } x, \text{mean } y)$ in the dataset we used to fit it. So, we know that: $2 \bar{x'} + 7 = \bar{y'}$. This first equation can be rewritten as: $2 \cdot (4\bar{x} - 3) + 7 = \bar{y} + 24$.

We're also told this line passes through $(\bar{x}, \bar{y})$, which means that it's also true that: $2 \bar{x} + 7 = \bar{y}$.

Now we have a system of two equations:

$\begin{cases}
2 \cdot (4\bar{x} - 3) + 7 = \bar{y} + 24 \\
2 \bar{x} + 7 = \bar{y}
\end{cases}$

$\dots$ and solving our system of two equations gives: $$\bar{x} = 5$$.

# END SOLUTION

# END SUBPROB

# END PROB
