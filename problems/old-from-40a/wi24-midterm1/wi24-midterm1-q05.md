# BEGIN PROB

<i>Source: [Winter 2024 Midterm 1](../wi24-midterm1/index.html), Problem 5</i>

Suppose the following information is given for linear regression:

$X = \begin{bmatrix}
1 & 2\\
1 & -1
\end{bmatrix}$


$\vec{y} =
    \begin{bmatrix}
    a\\
    b\\
    \end{bmatrix}$ $\vec{w}^{*} =
    \begin{bmatrix}
    1\\
    2\\
    \end{bmatrix}$


Where $X$ is the design matrix, $\vec{y}$ is the observation vector, and
$\vec{w}^{*}$ is the optimal parameter vector. Solve for parameters $a$ and
$b$ using the normal equations, show your work.

# BEGIN SOLUTION

$$\begin{cases}
       a = 5\\
       b = -1\\ 
\end{cases}$$

Since $\vec{w}^{*}$ is the optimal parameter vector, it must satisfy the
normal equations: 

$$\begin{align*}
        X^{T}X\vec{w} = X^{T}\vec{y}
\end{align*}$$

The left hand side of the equation will read:

\begin{align*}
X^{T}X\vec{w} &=
\begin{bmatrix}
1 & 1\\
2 & -1
\end{bmatrix}

\begin{bmatrix}
1 & 2\\
1 & -1
\end{bmatrix}

\begin{bmatrix}
1\\
2
\end{bmatrix}
\\
&=


\begin{bmatrix}
2 & 1\\
1 & 5
\end{bmatrix}

\begin{bmatrix}
1\\
2
\end{bmatrix}
\\
&=

\begin{bmatrix}
4\\
11
\end{bmatrix}
\end{align*}

The right hand side of the equation is given by:

\begin{align*}
X^{T}\vec{y} &=
\begin{bmatrix}
1 & 1\\
2 & -1
\end{bmatrix}
\begin{bmatrix}
a\\
b
\end{bmatrix}

\\
&=

\begin{bmatrix}
a+b\\
2a-b
\end{bmatrix}
\end{align*}

By setting the left hand side and right hand side equal to each other,
we will obtain the following system of equations:

\begin{align*}
\begin{bmatrix}
4\\
11
\end{bmatrix}

=

\begin{bmatrix}
a+b\\
2a-b
\end{bmatrix}
\end{align*}

$$\begin{cases}
        &4 = a + b\\
        &11 = 2a-b
\end{cases}$$

To solve this equation set, we can add them together:
$$\begin{align*}
       4+11 &= a + b + 2a -b\\
       3a &= 15\\
       \\
       \\
\end{align*}$$

$$\begin{cases}
       a = 5\\
       b = -1\\ 
\end{cases}$$

# END SOLUTION

# END PROB