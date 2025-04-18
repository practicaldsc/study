# BEGIN PROB

Suppose we want to fit a hypothesis function of the form:

$$H(x_i) = w_0 + w_1 x_i^2$$

Note that this is _not_ the simple linear regression hypothesis function, $H(x_i) = w_0 + w_1x_i$.

To do so, we will find the optimal parameter vector $\vec{w}^* = \begin{bmatrix} w_0^* \\ w_1^* \end{bmatrix}$ that satisfies the normal equations. The first 5 rows of our dataset are as follows, though note that our dataset has $n$ rows in total.

<!-- | x  | y |
|----|---|
| 2  | 4 |
| -1 | 4 |
| 3  | 4 |
| -7 | 4 |
| 3  | 4 | -->

<table style="border: 1px solid black; border-collapse: collapse; margin: auto; text-align: center;">
  <tr>
    <th style="border: 1px solid black; padding: 8px;">x</th>
    <th style="border: 1px solid black; padding: 8px;">y</th>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">2</td>
    <td style="border: 1px solid black; padding: 8px;">4</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">-1</td>
    <td style="border: 1px solid black; padding: 8px;">4</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">3</td>
    <td style="border: 1px solid black; padding: 8px;">4</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">-7</td>
    <td style="border: 1px solid black; padding: 8px;">4</td>
  </tr>
  <tr>
    <td style="border: 1px solid black; padding: 8px;">3</td>
    <td style="border: 1px solid black; padding: 8px;">4</td>
  </tr>
</table>

Suppose that $x_1, x_2, ..., x_n$ have a mean of $\bar{x} = 2$ and a variance of $\sigma_x^2 = 10$.

# BEGIN SUBPROB

Write out the first 5 rows of the design matrix, $X$.

# BEGIN SOLUTION
**Answer**: $X = \begin{bmatrix} 1 & 4 \\ 1 & 1 \\ 1 & 9 \\ 1 & 49 \\ 1 & 9 \end{bmatrix}$

Recall our hypothesis function is $H(x_i) = w_0 + w_1x_i^2$. Since there is an intercept term present, and $w_0$ is the first parameter, the first column of our design matrix will be all 1s. Our second column should contain $x_1^2, x_2^2, ..., x_n^2$. This means we take each datapoint $x_i$ and square it to form the second column of $X$.



# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose, just in part (b), that after solving the normal equations, we find $\vec{w}^* = \begin{bmatrix} 2 \\ -5 \end{bmatrix}$. What is the predicted $y$ value for $x = 2$? Give your answer as an integer with no variables. Show your work.

# BEGIN SOLUTION
**Answer**: $-18$

$(2)(1)+(-5)(4)=-18$

To find the predicted $y$ value, we plug in $x_i = 2$ into the hypothesis function $H(x_i) = w_0 + w_1x_i^2$, or take the dot product of $\vec{w}^*$ with $\begin{bmatrix}1 \\ 2^2\end{bmatrix}$.

\begin{align*}
&\begin{bmatrix} 2 \\ -5 \end{bmatrix} \cdot \begin{bmatrix} 1 \\ 4 \end{bmatrix}\\
&(2)(1)+(-5)(4)\\
&2 - 20\\
&-18
\end{align*}


# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Let $X_\text{tri} = 3 X$. Using the fact that $\sum_{i = 1}^n x_i^2 = n \sigma_x^2 + n \bar{x}^2$, determine the value of the bottom-left value in the matrix $X_\text{tri}^T X_\text{tri}$, i.e. the value in the second row and first column. Give your answer as an expression involving $n$. Show your work.

# BEGIN SOLUTION
**Answer**: $126n$

$$
X = \begin{bmatrix} 1 & x_1^2 \\ 1 & x_2^2 \\ \vdots & \vdots \\ 1 & x_n^2 \end{bmatrix}
$$

$$
X_{\text{tri}} = \begin{bmatrix} 3 & 3x_1^2 \\ 3 & 3x_2^2 \\ \vdots & \vdots \\ 3 & 3x_n^2 \end{bmatrix}
$$

We want to know what the bottom left value of $X_\text{tri}^T X_\text{tri}$ is. We figure this out with matrix multiplication!

\begin{align*}
X_\text{tri}^T X_\text{tri} &= \begin{bmatrix} 3 & 3 & ... & 3\\ 3x_1^2 & 3x_2^2 & ... & 3x_n^2 \end{bmatrix} \begin{bmatrix} 3 & 3x_1^2 \\ 3 & 3x_2^2 \\ \vdots & \vdots \\ 3 & 3x_n^2 \end{bmatrix}\\
&= \begin{bmatrix} \sum_{i = 1}^n 3(3) & \sum_{i = 1}^n 3(3x_i^2) \\ \sum_{i = 1}^n 3(3x_i^2) & \sum_{i = 1}^n (3x_i^2)(3x_i^2)\end{bmatrix}\\
&= \begin{bmatrix} \sum_{i = 1}^n 9 & \sum_{i = 1}^n 9x_i^2 \\ \sum_{i = 1}^n 9x_i^2 & \sum_{i = 1}^n (3x_i^2)^2 \end{bmatrix}
\end{align*}

We can see that the bottom left element should be $\sum_{i = 1}^n 9x_i^2$.

From here we can use the fact given to us in the directions: $\sum_{i = 1}^n x_i^2 = n \sigma_x^2 + n \bar{x}^2$.

\begin{align*}
\sum_{i = 1}^n 9x_i^2 &= 9\sum_{i = 1}^n x_i^2\\
&= 9(n \sigma_x^2 + n \bar{x}^2)\\
&= 9(10n + 2^2n)\\
&= 9(10n + 4n)\\
&= 9(14n) = 126n
\end{align*}

# END SOLUTION

# END SUBPROB

# END PROB