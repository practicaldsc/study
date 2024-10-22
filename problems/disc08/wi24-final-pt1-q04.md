# BEGIN PROB

Albert collected 400 data points from a radiation detector.
Each data point contains 3 features: feature $A$, feature $B$ and feature $C$.
The true particle energy $E$ is also reported. Albert wants to design a linear
regression algorithm to predict the energy $E$ of each particle, given a combination of one or more of feature $A$, $B$, and $C$. As the first step, Albert
calculated the correlation coefficients among $A$, $B$, $C$ and $E$. He wrote it
down in the following table, where each cell of the table represents the
correlaton of two terms:

<div>
|             | $A$ &emsp;&emsp;| $B$ &emsp;&emsp;| $C$ &emsp;&emsp;| $E$ &emsp;&emsp;|
|-------------|-----------|-----------|-----------|----------|
| $A$   | 1         | -0.99     | 0.13      | 0.8      |
| $B$   | -0.99     | 1         | 0.25      | -0.95    |
| $C$   | 0.13      | 0.25      | 1         | 0.72     |
| $E$    | 0.8       | -0.95     | 0.72      | 1        |
</div>

# BEGIN SUBPROB

Albert wants to start with a simple model: fitting only a single
feature to obtain the true energy (i.e. $y = w_0+w_1 x$). Which feature
should he choose as $x$ to get the lowest mean square error?

( ) $A$
( ) $B$
( ) $C$

# BEGIN SOLUTION

$B$

$B$ is the correct answer, because it has the highest absolute correlation
(0.95), the negative sign in front of $B$ just means it is negatively
correlated to energy, and it can be compensated by a negative sign in the
weight.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Albert wants to add another feature to his linear regression in
part (a) to further boost the model's performance. (i.e.
$y = w_0 + w_1 x + w_2 x_2$) Which feature should he choose as $x_2$ to
make additional improvements?

( ) $A$
( ) $B$
( ) $C$

# BEGIN SOLUTION

$C$

$C$ is the correct answer, because although $A$ has a higher correlation
with energy, it also has an extremely high correlation with $B$ (-0.99),
that means adding $A$ into the fit will not be too useful, since it
provides almost the same information as $B$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Albert further refines his algorithm by fitting a prediction rule of the
form: $$\begin{aligned}
H(A,B,C) = w_0 + w_1 \cdot A\cdot C + w_2 \cdot B^{C-7}
\end{aligned}$$

Given this prediction rule, what are the dimensions of the design
matrix $X$?

$$
\begin{bmatrix}
& & & \\
& & & \\
& & & \\
\end{bmatrix}_{r \times c}
$$

So, what are $r$ and $c$ in $r \text{ rows} \times c \text{ columns}$?

# BEGIN SOLUTION

$400 \text{ rows} \times 3 \text{ columns}$

Recall there are 400 data points, which means there will be 400 rows. There will be 3 columns; one is the bias column of all $1$s, one is for the feature $A\cdot C$, and one is for the feature $B^{C-7}$.

# END SOLUTION

# END SUBPROB

<!-- Commented out the last subproblem, because the solution is weird?? Need to rework. -->

<!-- # BEGIN SUBPROB

Now Albert solves the normal equations and finds the solution to be:
$$\vec{w}^* = \begin{bmatrix} w_0^* \\ w_1^* \\ w_2^*  \end{bmatrix}$$
To improve on this result, Albert decides to modify his design matrix
with the following steps:

1.  Add 1 to every entry to the first column

2.  Swap the second and the third column

Let $X_a$ be the modified design matrix. Let
$\vec{w_a}^* = (X_a^TX_a)^{-1}X_a^T\vec{y}$.

Express the components
$\vec{w_a}^*$ in terms of $w_0^*, w_1^*, w_2^*$, which were the
components of $\vec{w}^*$.

$$\vec{w_a}^* = \begin{bmatrix} ? \\ ? \\ ? \\ \end{bmatrix}$$

# BEGIN SOLUTION

$$\vec{w}^* = \begin{bmatrix} w_0^*/2 \\ w_2^* \\ w_1^*  \end{bmatrix}$$

We should follow the steps Albert did to construct $X$. We will add $1$ to be the first element in each row and then switch the constants attached to $w_1$ ($A \cdot B$) and $w_2$ ($B^{C-7}$):
$$
X_a = \begin{bmatrix}
1 & B^{C-7} & A \\
1 & B^{C-7} & A \\
\vdots & \vdots & \vdots \\
1 & B^{C-7} & A
\end{bmatrix}
$$

We know that $X_\alpha^T X_\alpha$ is the same as an identity matrix. The inverse of an identity matrix is the same as it was before.

This means we are really looking at $X_\alpha^T \vec{y}$:
$$
\begin{align*}
X_\alpha^T \vec{y} &= \begin{bmatrix}
1 & 1 & \cdots & 1 \\
B^{C-7} & B^{C-7} & \cdots & B^{C-7} \\
A & A & \cdots & A
\end{bmatrix} \cdot \begin{bmatrix}
y_1 \\
y_2 \\
\vdots \\
y_{400}
\end{bmatrix} \\
&= \begin{bmatrix}
\sum_{i = 1}^{400}{y_i}\\
\sum_{i = 1}^{400}{B^{C-7} \cdot y_i} \\
\sum_{i = 1}^{400}{A \cdot y_i}
\end{bmatrix}
\end{align*}
$$

The first component of our final matrix, $sum_{i = 1}^{400}{y_i}$, is proportional to $w_0^*$. The second component of our matrix, $\sum_{i = 1}^{400}{B^{C-7} \cdot y_i}$, is proportional to $w_2^*$. Finally, the third component of our matrix, $\sum_{i = 1}^{400}{A \cdot y_i}$, is proportional to $w_1^*$.

# END SOLUTION

# END SUBPROB -->

# END PROB
