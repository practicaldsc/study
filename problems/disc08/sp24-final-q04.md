# BEGIN PROB

Consider the vectors $\vec{u}$ and $\vec{v}$, defined below.

$$\vec{u} = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} \qquad \vec{v} = \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}$$

We define $X \in \mathbb{R}^{3 \times 2}$ to be the matrix whose first
column is $\vec u$ and whose second column is $\vec v$.

# BEGIN SUBPROB

In this part only, let
$\vec{y} = \begin{bmatrix} -1 \\ k \\ 252 \end{bmatrix}$.

Find a scalar $k$ such that $\vec{y}$ is in
$\text{span}(\vec u, \vec v)$. Give your answer as a constant with no
variables.

# BEGIN SOLUTION

$252$.

Vectors in $\text{span}(\vec u, \vec v)$ must have an equal 2nd and 3rd component, and the third component is 252, so the second must be as well.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Show that:
$$(X^TX)^{-1}X^T = \begin{bmatrix} 1 & 0 & 0 \\ 0 & \frac{1}{2} & \frac{1}{2} \end{bmatrix}$$

_Hint: If $A = \begin{bmatrix} a_1 & 0 \\ 0 & a_2 \end{bmatrix}$, then
$A^{-1} = \begin{bmatrix} \frac{1}{a_1} & 0 \\ 0 & \frac{1}{a_2} \end{bmatrix}$._

# BEGIN SOLUTION

We can construct the following series of matrices to get $(X^TX)^{-1}X^T$.

- $X = \begin{bmatrix} 1 & 0 \\ 0 & 1 \\ 0 & 1 \end{bmatrix}$
- $X^T = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 1 \end{bmatrix}$
- $X^TX = \begin{bmatrix} 1 & 0 \\ 0 & 2 \end{bmatrix}$
- $(X^TX)^{-1} = \begin{bmatrix} 1 & 0 \\ 0 & \frac{1}{2} \end{bmatrix}$
- $(X^TX)^{-1}X^T = \begin{bmatrix} 1 & 0 & 0 \\ 0 & \frac{1}{2} & \frac{1}{2} \end{bmatrix}$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

In parts (c) and (d) only, let
$\vec{y} = \begin{bmatrix} 4 \\ 2 \\ 8 \end{bmatrix}$.

Find scalars $a$ and $b$ such that $a \vec u + b \vec v$ is the vector
in $\text{span}(\vec u, \vec v)$ that is as close to $\vec{y}$ as
possible. Give your answers as constants with no variables.

# BEGIN SOLUTION

$a = 4$, $b = 5$.

The result from the part (b) implies that when using the normal equations to find coefficients for $\vec u$ and $\vec v$ – which we know from lecture produce an error vector whose length is minimized – the coefficient on $\vec u$ must be $y_1$ and the coefficient on $\vec v$ must be $\frac{y_2 + y_3}{2}$. This can be shown by taking the result from part (b), $\begin{bmatrix} 1 & 0 & 0 \\ 0 & \frac{1}{2} & \frac{1}{2} \end{bmatrix}$, and multiplying it by the vector $\vec y = \begin{bmatrix} y_1 \\ y_2 \\ y_3 \end{bmatrix}$.

Here, $y_1 = 4$, so $a = 4$. We also know $y_2 = 2$ and $y_3 = 8$, so $b = \frac{2+8}{2} = 5$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Let $\vec{e} = \vec{y} - (a \vec u + b \vec v)$, where $a$ and $b$ are
the values you found in part (c).

What is $\lVert \vec{e} \rVert$?

( ) $0$
( ) $3 \sqrt{2}$
( ) $4 \sqrt{2}$
( ) $6$
( ) $6 \sqrt{2}$
( ) $2\sqrt{21}$

# BEGIN SOLUTION

$3 \sqrt{2}$.

The correct value of $a \vec u + b \vec v = \begin{bmatrix} 4 \\ 5 \\ 5\end{bmatrix}$. Then, $\vec{e} = \begin{bmatrix} 4 \\ 2 \\ 8 \end{bmatrix} - \begin{bmatrix} 4 \\ 5 \\ 5 \end{bmatrix} = \begin{bmatrix} 0 \\ -3 \\ 3 \end{bmatrix}$, which has a length of $\sqrt{0^2 + (-3)^2 + 3^2} = 3\sqrt{2}$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Is it true that, for any vector $\vec{y} \in \mathbb{R}^3$, we can find
scalars $c$ and $d$ such that the sum of the entries in the vector
$\vec{y} - (c \vec u + d \vec v)$ is 0?

( ) Yes, because $\vec{u}$ and $\vec{v}$ are linearly independent.
( ) Yes, because $\vec{u}$ and $\vec{v}$ are orthogonal.
( ) Yes, but for a reason that isn't listed here.
( ) No, because $\vec{y}$ is not necessarily in
$\text{span}(\vec{u}, \vec{v})$.
( ) No, because neither $\vec{u}$ nor $\vec{v}$ is equal to the vector
$\begin{bmatrix} 1 & 1 & 1 \end{bmatrix}^T$.
( ) No, but for a reason that isn't listed here.

# BEGIN SOLUTION

Yes, but for a reason that isn't listed here.

Here's the full reason:

1. We can use the normal equations to find $c$ and $d$, no matter what $\vec{y}$ is.
2. The error vector $\vec e$ that results from using the normal equations is such that $\vec e$ is orthogonal to the span of the columns of $X$.
3. The columns of $X$ are just $\vec u$ and $\vec v$. So, $\vec e$ is orthogonal to any linear combination of $\vec u$ and $\vec v$.
4. One of the many linear combinations of $\vec u$ and $\vec v$ is $\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$.
5. This means that the vector $\vec e$ is orthogonal to $\begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$, which means that $\vec{1}^T \vec{e} = 0 \implies \sum_{i = 1}^3 e_i = 0$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose that $Q \in \mathbb{R}^{100 \times 12}$,
$\vec{s} \in \mathbb{R}^{100}$, and $\vec{f} \in \mathbb{R}^{12}$. What
are the dimensions of the following product?

$$\vec{s}^T Q \vec{f}$$

( ) scalar  
( ) $12 \times 1$ vector  
( ) $100 \times 1$ vector
( ) $100 \times 12$ matrix  
( ) $12 \times 12$ matrix  
( ) $12 \times 100$ matrix
( ) undefined

# BEGIN SOLUTION

Correct: Scalar.

- $\vec{s}^T$: 1 x 100
- $Q$: 100 x 12.
- $\vec{f}$: 12 x 1.

The inner dimensions of 100 and 12 cancel, and so
$\vec{s}^T Q \vec{f}$ is of shape 1 x 1.

# END SOLUTION

# END SUBPROB

# END PROB
