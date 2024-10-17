# BEGIN PROB

<!-- \[ **Linear regeression**\]\[13 Points\] -->

Given a $2\times 2$ matrix
$$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}.$$ Its inverse (if
exists) is given by:
$$A^{-1} = \frac{1}{ad - bc}\begin{pmatrix} d & -b \\ -c & a \end{pmatrix}.$$
**Hint:** This matrix inversion formula is useful for this question.

# BEGIN SUBPROB

\[2 Points\] Suppose we are given data of 4 samples
$$\mathcal{D} = \{(x_i, y_i)\}_{i = 1}^n = \{(0, 1), (2, 2), (4, 3), (6, 4)\}.$$
We have our linear regression: $$X\vec{w} = \vec{y}.$$ Write down the
dimensions of $X$, $\vec{w}$ and $\vec{y}$ in general (i.e. $n$ samples,
$d$ features), and for this data. Write down $X$ and $\vec{y}$
explicitly for this data.\

# BEGIN SOLUTION

For this data, we have the following dimensions:
$X \in \mathbb{R}^{4 \times 2}$, $\vec{w} \in \mathbb{R}^2$, and
$\vec{y} \in \mathbb{R}^4$. It is also fine to write
$\vec{w} \in \mathbb{R}^{2 \times 1}$ and
$\vec{y} \in \mathbb{R}^{4 \times 1}$ (i.e. matrix with a single
column).\
\
In general, with $n$ samples and the number of features as $d$, the
dimensions are: $X \in \mathbb{R}^{n \times (d + 1)}$,
$\vec{w} \in \mathbb{R}^{d + 1}$, and $\vec{y} \in \mathbb{R}^n$.\
\
For this data:
$$X = \begin{pmatrix} 1 & 0 \\ 1 & 2 \\ 1 & 4 \\ 1 & 6 \end{pmatrix}, \ \ \ \ \vec{w} = \begin{pmatrix} w_0 \\ w_1 \end{pmatrix}, \ \ \ \ \vec{y} = \begin{pmatrix} 1 \\ 2 \\ 3 \\ 4 \end{pmatrix}.$$

# END SOLUTION


# END SUBPROB

# BEGIN SUBPROB

\[1 Point\] Write down the closed-form solution for $\vec{w}$ in matrix
form.



# BEGIN SOLUTION

The closed-form solution (i.e. matrix form) is given by:
$$\vec{w} = (X^TX)^{-1}X^T\vec{y},$$ where $(X^TX)^{-1}X^T$ is called
the pseudo-inverse of $X$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[4 Points\] Now, show step-by-step details of your calculation for
$\vec{w}$ with matrix operations.

# BEGIN SOLUTION

First, we compute the covariance matrix $X^TX$:
$$X^TX = \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 2 & 4 & 6 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 1 & 2 \\ 1 & 4 \\ 1 & 6 \end{pmatrix} = \begin{pmatrix} 4 & 12 \\ 12 & 56 \end{pmatrix}.$$
Now, we compute the inverse of the covariance matrix $(X^TX)^{-1}$ using
the formula we have just proved in part a):
$$(X^TX)^{-1} = \frac{1}{4 \cdot 56 - 12 \cdot 12} \begin{pmatrix} 56 & -12 \\ -12 & 4 \end{pmatrix} = \frac{1}{80} \begin{pmatrix} 56 & -12 \\ -12 & 4 \end{pmatrix} = \frac{1}{20} \begin{pmatrix} 14 & -3 \\ -3 & 1 \end{pmatrix}.$$
We can calculate the pseudo-inverse now:
$$(X^TX)^{-1}X^T = \frac{1}{20} \begin{pmatrix} 14 & -3 \\ -3 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 2 & 4 & 6 \end{pmatrix} = \frac{1}{20} \begin{pmatrix} 14 & 8 & 2 & -4 \\ -3 & -1 & 1 & 3 \end{pmatrix}$$
Finally, we have our solution:
$$\vec{w} = (X^TX)^{-1}X^T\vec{y} = \frac{1}{20} \begin{pmatrix} 14 & 8 & 2 & -4 \\ -3 & -1 & 1 & 3 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \\ 3 \\ 4 \end{pmatrix} = \frac{1}{20} \begin{pmatrix} 20 \\ 10 \end{pmatrix} = \begin{pmatrix} 1 \\ 0.5 \end{pmatrix}.$$
The bias/intercept $w_0 = 1$ and the slope $w_1 = 0.5$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[3 Points\] Instead of the matrix form, solve the linear regression
with the following scheme:\
$\bar x = \phantom{\hspace{.5in}}$\
$\bar y = \phantom{\hspace{.5in}}$\
$w_1^* =$\
$w_0^* =$

::: center
  $x_i$   $y_i$   $(x_i - \bar x)$   $(y_i - \bar y)$   $(x_i - \bar x)(y_i - \bar y)$   $(x_i - \bar x)^2$
  ------- ------- ------------------ ------------------ -------------------------------- --------------------
  0       1                                                                              
  2       2                                                                              
  4       3                                                                              
  6       4                                                                              

\
:::

We should get the same answer as using the matrix form. Finally, what
can we say about the correlation $r$ and the slope for this dataset
(mathematically)?

# BEGIN SOLUTION

$$\bar x = \frac{0 + 2 + 4 + 6}{4} = 3$$
$$\bar y = \frac{1 + 2 + 3 + 4}{4} = \frac{5}{2}$$

::: center
   $x_i$   $y_i$   $(x_i - \bar x)$   $(y_i - \bar y)$   $(x_i - \bar x)(y_i - \bar y)$   $(x_i - \bar x)^2$
  ------- ------- ------------------ ------------------ -------------------------------- --------------------
     0       1           $-3$              $-3/2$                    $9/2$                        9
     2       2           $-1$              $-1/2$                    $1/2$                        1
     4       3            1                $1/2$                     $1/2$                        1
     6       4            3                $3/2$                     $9/2$                        9

\
:::

$$w_1^* =
\frac{
\displaystyle
\sum_{i=1}^n (x_i - \bar x)(y_i - \bar y)
}{
\displaystyle
\sum_{i=1}^n (x_i - \bar x)^2
}
= \frac{9/2 + 1/2 + 1/2 + 9/2}{9 + 1 + 1 + 9} = \frac{1}{2} = 0.5$$
$$w_0^* = \bar y - w_1^* \bar x = \frac{5}{2} - \frac{1}{2} \cdot 3 = 1$$
We get exactly the same result as via the closed-form matrix solution.
Because $w_1^* = r \frac{\sigma_y}{\sigma_x}$ where the standard
deviations $\sigma_y$ and $\sigma_x$ are non-negative, and
$w_1^* = 0.5 > 0$, thus the correlation $r$ is positive and the slope is
positive.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[2 Points\] Given an arbitrary dataset of $n$ samples
$\mathcal{D} = \{(x_i, y_i)\}_{i = 1}^n$:

-   How do the slope and the intercept (bias) change if we add
    $\alpha \in \mathbb{R}$ to each $y_i$? Show an explanation for your
    claim!

-   How does the slope change if we multiply $\beta \in \mathbb{R}$ to
    each $x_i$? Show an explanation for your claim!

# BEGIN SOLUTION

-   If we add $\alpha \in \mathbb{R}$ to each $y_i$:
    $\bar y^{\text{new}} = \bar y + \alpha$ but
    $y_i - \bar y^{\text{new}} = y_i - \bar y$ stays the same. And we do
    not change anything on $x_i$, so the slope $w_1$ stays the same, but
    the new bias is added $\alpha$, i.e.
    ${w_0}^{\text{new}} = w_0 + \alpha$.

-   If we multiply $\beta \in \mathbb{R}$ to each $x_i$, we have:
    $x_i^{\text{new}} = \beta x_i$ and
    $\bar x^{\text{new}} = \beta \bar x$. Thus,
    $x_i^{\text{new}} - \bar x^{\text{new}} = \beta(x_i - \bar x)$. The
    new slope is: $$w_1^{\text{new}} =
    \frac{
    \displaystyle
    \sum_{i=1}^n (x_i^{\text{new}} - \bar x^{\text{new}})(y_i - \bar y)
    }{
    \displaystyle
    \sum_{i=1}^n (x_i^{\text{new}} - \bar x^{\text{new}})^2
    }
    = 
    \frac{
    \displaystyle
    \beta \sum_{i=1}^n (x_i - \bar x)(y_i - \bar y)
    }{
    \displaystyle
    \beta^2 \sum_{i=1}^n (x_i - \bar x)^2
    }
    =
    \frac{1}{\beta} w_1.$$ Therefore, the new slope is $1/\beta$ of the
    old slope.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[1 Point\] Suppose we have the hypothesis $h(x) = w_0e^{w_1x}$. How can
we apply linear regression to find $w_0$ and $w_1$?

# BEGIN SOLUTION

We apply the logarithm transformation to the hypothesis:
$$g(x) = \log(h(x)) = \log(w_0) + w_1x,$$ that is linear with respect to
the parameters. Let $b_0 = \log(w_0)$ and $b_1 = w_1$. We have:
$g(x) = b_1x + b_0$. We also apply the logarithm transformation to all
$y_i$. Then, we apply linear regression to find $b_0^*$ and $b_1^*$ for
the new transformed data $\{(x_i, \log(y_i))\}_{i = 1}^n$. Finally, we
get $w_0^* = e^{b_0^*}$ and $w_1^* = b_1^*$.

# END SOLUTION

# END SUBPROB

# END PROB