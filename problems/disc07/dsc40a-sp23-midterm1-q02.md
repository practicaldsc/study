# BEGIN PROB

<!-- <i>Source: [Spring 2023 Midterm 1](../sp23-midterm1/index.html), Problem 2</i> -->

Let $R_{sq}(h)$ represent the mean squared error of a constant prediction $h$ for a given dataset. Find a dataset $\{y_1, y_2\}$ such that the graph of $R_{sq}(h)$ has its minimum at the point $(7,16)$.

# BEGIN SOLUTION

The dataset is {$3, 11$}.

We've already learned that $R_{sq}(h)$ is minimized at the mean of the data, and the minimum value of $R_sq(h)$ is the variance of the data. So we need to provide a dataset of two points with a mean of $7$ and a variance of $16$. Recall that the variance is the average squared distance of each data point to the mean. Since we want a variance of $16$, we can make each point $4$ units away from the mean. Therefore, our data set can be $y_1 = 3, y_2 = 11.$ In fact, this is the only solution.

A more calculative approach uses the formulas for mean and variance and solves a system of two equations:

$$\begin{aligned} \frac{y_1+y_2}{2} &= 7 \\ \frac12 \left((y_1 - 7)^2 + (y_2 - 7)^2 \right) &= 16 \end{aligned}$$

# END SOLUTION

# END PROB
