# BEGIN PROB

<i>Source: [Spring 2024 Midterm](../sp24-midterm/index.html), Problem 5</i>

Consider a dataset of $n$ points, $(x_1, y_1), (x_2, y_2), ..., (x_n, y_n)$ where:

- $x_1 < x_2 < ... < x_n$, and $x_1, x_2, ..., x_n$ have a variance of $\sigma_x^2 = 15$ and a range of 20 (the range of a collection of values is the difference between the largest and smallest value).
- $y_1 > y_2 > ... > y_n$, and $y_1, y_2, ..., y_n$ have a variance of $\sigma_y^2 = 8$ and a range of 6.

We fit two linear hypothesis functions using squared loss:

- One hypothesis function is fit with a ``swapped" version of the dataset, where $x_1$ and $x_n$ are swapped --- that is, it uses the dataset $(x_n, y_1), (x_2, y_2), ..., (x_{n-1}, y_{n-1}), (x_1, y_n)$. Note that only two of the points in this dataset are different than in the original dataset. We'll call the optimal slope and intercept of this hypothesis function $w_1^\text{swap}$ and $w_0^\text{swap}$, respectively.
- Another hypothesis function is fit with the original dataset, 

$(x_1, y_1), (x_2, y_2), ..., (x_{n-1}, y_{n-1}), (x_n, y_n)$. We'll call the optimal slope and intercept of this hypothesis function $w_1^\text{orig}$ and $w_0^\text{orig}$, respectively. 

On the next page, in the space provided, prove that:

$$\displaystyle | w_1^\text{swap} - w_1^\text{orig} | = \frac{8}{n}$$

\textit{Hint: Approach this problem similarly to Problem 2 on Homework 3 (``Shout for Stroud"). Also, think about how you can express $\sum_{i = 1}^n (x_i - \bar{x})^2$ in terms of $n$ and $\sigma_x^2$.}

# BEGIN SOLUTION

Using one of the formulas for $w_1$.

\begin{align*}
\displaystyle | w_1^\text{swap} - w_1^\text{orig} | = | \frac{[\sum_{i=2}^{n-1} (x_i - x_\text{mean})(y_i - y_\text{mean})] + (x_n - x_\text{mean})(y_1 - y_\text{mean}) + (x_1 - x_\text{mean})(y_n - y_\text{mean})}{15n} \\
- \frac{([\sum_{i=2}^{n-1} (x_i - x_\text{mean})(y_i - y_\text{mean})] + (x_1 - x_\text{mean})(y_1 - y_\text{mean}) + (x_n - x_\text{mean})(y_n - y_\text{mean}))}{15n} | \\
\end{align*}

then cancelling the sumations you get
\begin{align*}
\displaystyle | w_1^\text{swap} - w_1^\text{orig} | = | \frac{ (x_n - x_\text{mean})(y_1 - y_\text{mean}) + (x_1 - x_\text{mean})(y_n - y_\text{mean})}{15n} \\
- \frac{((x_1 - x_\text{mean})(y_1 - y_\text{mean}) + (x_n - x_\text{mean})(y_n - y_\text{mean}))}{15n} | \\
= |\frac{(x_n - x_\text{mean})(y_1 - y_n) + (x_1 - x_\text{mean})(y_n - y_1)}{15n}|\\
= |\frac{(x_n - x_\text{mean})(6) + (x_1 - x_\text{mean})(-6)}{15n}| \\
= |\frac{6(x_n - x_\text{mean} - x_1 + x_\text{mean})}{15n}|\\
= |\frac{6(20)}{15n}|
= \frac{8}{n}
\end{align*}

<average>39</average>

# END SOLUTION

# END PROB