# BEGIN PROB

Consider the dataset shown below.

::: center
  $x^{(1)}$   $x^{(2)}$   $x^{(3)}$   $y$
  ----------- ----------- ----------- -----
  0           6           8           -5
  3           4           5           7
  5           -1          -3          4
  0           2           1           2
:::

# BEGIN SUBPROB

We want to use multiple regression to fit a prediction rule
of the form
$$H(x_i^{(1)}, x_i^{(2)}, x_i^{(3)}) = w_0 + w_1 x_i^{(1)} x_i^{(3)} + w_2 (x_i^{(2)} - x_i^{(3)})^2.$$
Write down the design matrix $X$ and observation vector $\vec{y}$ for
this scenario. No justification needed.

# BEGIN SOLUTION

The design matrix $X$ and observation vector $\vec{y}$ are given by:

$$
X = 
\begin{bmatrix}
1 & 0 & 4\\
1 & 15 & 1\\
1 & -15 & 4\\
1 & 0 & 1
\end{bmatrix}
$$

$$
\vec{y} = 
\begin{bmatrix}
-5\\
7\\
4\\
2
\end{bmatrix}
$$

The observation vector $\vec{y}$ contains the target values from the dataset.

For the design matrix $X$, each row corresponds to one data point in our dataset, where $x_i^{(1)}$, $x_i^{(2)}$, and $x_i^{(3)}$ represent three separate features for the $i$-th data point. Each row of $X$ has the form $\begin{bmatrix}1 & x_i^{(1)}x_i^{(3)} & (x_i^{(2)}-x_i^{(3)})^2\end{bmatrix}$. The first column consists of all 1's for the bias term $w_0$, which is not affected by the feature values.
# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

For the $X$ and $\vec{y}$ that you have written down, let $\vec{w}$ be the optimal parameter vector, which comes from solving the normal equations $X^TX\vec{w}=X^T\vec{y}$. Let $\vec{e} = \vec{y} - X \vec{w}$ be the error vector, and let $e_i$ be the $i$th component of this error vector. Show that $$4e_1+e_2+4e_3+e_4=0.$$

# BEGIN SOLUTION

The key to this problem is the fact that the error vector, $\vec{e}$, is orthogonal to the columns of the design matrix, $X$. As a refresher, if $\vec{w^*}$ satisfies the normal equations, then:

We can rewrite the normal equation ($X^TX\vec{w}=X^T\vec{y}$) to allow substitution for $\vec{e} = \vec{y} - X \vec{w}$.


$$X^TX\vec{w}=X^T\vec{y}$$
$$0 = X^T\vec{y} - X^TX\vec{w}$$
$$0 = X^T(\vec{y}-X\vec{w})$$
$$0 = X^T\vec{e}$$

The first step is to find $X^T$, which is easy because we found $X$ above:
$$
\begin{bmatrix}
1 & 1 & 1 & 1 \\ 0 & 15 & -15 & 0 \\ 4 & 1 & 4 & 1
\end{bmatrix}
$$

And now we can plug $X^T$ and $\vec e$ into our equation $0 = X^T\vec{e}$. It might be easiest to find the right side first:

$$X^T\vec{e} = \begin{bmatrix} 1 & 1 & 1 & 1 \\ 0 & 15 & -15 & 0 \\ 4 & 1 & 4 & 1 \end{bmatrix} \cdot \begin{bmatrix} e_1 \\ e_2 \\ e_3 \\ e_4\end{bmatrix}$$

$$= \begin{bmatrix} e_1 + e_2 + e_3 + e_4 \\ 15e_2 - 15e_3 \\ 4e_1 + e_2 + 4e_3 + e_4\end{bmatrix}$$

Finally, we set it equal to zero!
$$0 = e_1 + e_2 + e_3 + e_4$$
$$0 = 15e_2 - 15e_3$$
$$0 = 4e_1 + e_2 + 4e_3 + e_4$$

With this we have shown that $4e_1+e_2+4e_3+e_4=0$.

# END SOLUTION

# END SUBPROB

# END PROB