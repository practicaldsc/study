# BEGIN PROB

Consider the following information:

- $\vec{v}$ is an $n$-dimensional vector.
- $M$ is an $m \times n$ matrix.
- $N$ is an $n \times n$ matrix.
- $s$ is a scalar.

Select the dimensionality of each of the objects below:


# BEGIN SUBPROB

$M \vec{v}$

( ) An $n \times n$ matrix.
( ) An $m \times m$ matrix.
( ) An $n \times m$ matrix.
( ) An $m$-dimensional vector.
( ) An $n$-dimensional vector.
( ) A scalar.
( ) Invalid operation.

    
# BEGIN SOLUTION

An $m$-dimensional vector.

We know the following information:

- $M$ is an $m \times n$ matrix.
- $\vec{v}$ is an $n$-dimensional vector.

This means:

$$
M = \left[ \begin{matrix}
\end{matrix} \right]_{m \times n}
\text{ and }
\vec{v} = \left[ \begin{matrix}
\end{matrix} \right]_{n \times 1}
$$

When you multiply $M \vec{v}$ the $n$ will both cancel out leaving you with an object with the size $\left[ \begin{matrix} \end{matrix} \right]_{m \times 1}$, which is an $m$-dimensional vector.


# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

$M^T M$

( ) An $n \times n$ matrix.
( ) An $m \times m$ matrix.
( ) An $n \times m$ matrix.
( ) An $m$-dimensional vector.
( ) An $n$-dimensional vector.
( ) A scalar.
( ) Invalid operation.

# BEGIN SOLUTION

An $n \times n$ matrix.

We know the following information:

- $M$ is an $m \times n$ matrix.

This means:

$$
M^T = \left[ \begin{matrix}
\end{matrix} \right]_{n \times m}
\text{ and }
M = \left[ \begin{matrix}
\end{matrix} \right]_{m \times n}
$$

When you multiply $M^T M$ the $m$ will both cancel out leaving you with an object with the size $\left[ \begin{matrix} \end{matrix} \right]_{n \times n}$, which is an $n \times n$ matrix.

# END SOLUTION
    


# END SUBPROB


# BEGIN SUBPROB

$\vec{v}^T N \vec{v}$

( ) An $n \times n$ matrix.
( ) An $m \times m$ matrix.
( ) An $n \times m$ matrix.
( ) An $m$-dimensional vector.
( ) An $n$-dimensional vector.
( ) A scalar.
( ) Invalid operation.

# BEGIN SOLUTION

A scalar.

We know the following information:

- $\vec{v}$ is an $n$-dimensional vector.
- $N$ is an $n \times n$ matrix.

This means:

$$
\vec{v}^T = \left[ \begin{matrix}
\end{matrix} \right]_{1 \times n}
\text{, }
N = \left[ \begin{matrix}
\end{matrix} \right]_{n \times n}
\text{, and }
\vec{v} = \left[ \begin{matrix}
\end{matrix} \right]_{n \times 1}
$$

When you multiply $\vec{v}^T N$ the $n$ will both cancel out leaving you with an object with the size $\left[ \begin{matrix} \end{matrix} \right]_{1 \times n}$. When you multiply this object by $\vec{v}$ the $n$ will cancel out again leaving you with an object with the size $\left[ \begin{matrix} \end{matrix} \right]_{1 \times 1}$, which is a scalar.

# END SOLUTION
    


# END SUBPROB

# BEGIN SUBPROB

$N \vec{v} + s \vec{v}$

( ) An $n \times n$ matrix.
( ) An $m \times m$ matrix.
( ) An $n \times m$ matrix.
( ) An $m$-dimensional vector.
( ) An $n$-dimensional vector.
( ) A scalar.
( ) Invalid operation.

# BEGIN SOLUTION

An $n$-dimensional vector.

We know the following information:

- $\vec{v}$ is an $n$-dimensional vector.
- $N$ is an $n \times n$ matrix.
- $s$ is a scalar.

This means:

$$
\vec{v} = \left[ \begin{matrix}
\end{matrix} \right]_{n \times 1}
\text{, }
N = \left[ \begin{matrix}
\end{matrix} \right]_{n \times n}
\text{, and }
s = \left[ \begin{matrix}
\end{matrix} \right]_{1 \times 1}
$$

When you multiply $N \vec{v}$ the $n$ will both cancel out leaving you with an object with the size $\left[ \begin{matrix} \end{matrix} \right]_{n \times 1}$. When you multiply $\s \vec{v}$ the dimensions of $\vec{v}$ does not change, so you will have an object with the size $\left[ \begin{matrix} \end{matrix} \right]_{n \times 1}$. When you add these vectors the dimension will not change, so you are left with an $n$-dimensional vector.

# END SOLUTION
    


# END SUBPROB

# BEGIN SUBPROB

$M^T M \vec{v}$

( ) An $n \times n$ matrix.
( ) An $m \times m$ matrix.
( ) An $n \times m$ matrix.
( ) An $m$-dimensional vector.
( ) An $n$-dimensional vector.
( ) A scalar.
( ) Invalid operation.

# BEGIN SOLUTION

An $n$-dimensional vector.

We know the following information:

- $\vec{v}$ is an $n$-dimensional vector.
- $N$ is an $n \times n$ matrix.
- $s$ is a scalar.

This means:

$$
M^T = \left[ \begin{matrix}
\end{matrix} \right]_{n \times m}
\text{, }
M = \left[ \begin{matrix}
\end{matrix} \right]_{m \times n}
\text{, and }
\vec{v} = \left[ \begin{matrix}
\end{matrix} \right]_{n \times 1}
$$

When you multiply $M^T M$ the $m$ will both cancel out leaving you with an object with the size $\left[ \begin{matrix} \end{matrix} \right]_{n \times n}$, which is an $n \times n$ matrix. When you multiply $\left[ \begin{matrix} \end{matrix} \right]_{n \times n} \times \vec{v}_{n \times 1}$ the $n$ will cancel out leaving you with an $n$-dimensional vector.

# END SOLUTION
    


# END SUBPROB


# END PROB