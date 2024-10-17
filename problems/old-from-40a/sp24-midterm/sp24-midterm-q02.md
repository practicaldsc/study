# BEGIN PROB

<i>Source: [Spring 2024 Midterm](../sp24-midterm/index.html), Problem 1b-e</i>

Consider the vectors $\vec{c}$ and $\vec{d}$, defined below.

$$\vec{c} = \begin{bmatrix} 1 \\ 7 \end{bmatrix} \qquad \vec{d} = \begin{bmatrix} -2 \\ 1 \end{bmatrix}$$

The next few parts ask you to write various vectors as scalar multiples of either $\vec{c}$, $\vec{c_f}$, $\vec{d}$, or $\vec{d_f}$, where $\vec{c_f}$ and $\vec{d_f}$ are the friends of $\vec{c}$ and $\vec{d}$, respectively. In each part, write \textbf{one number} in the box, and fill in \textbf{one bubble}.

<br>

Here is an example:

A vector in span($\vec d$) that is twice as long as $\vec d$.

$2 \times \vec d$

# BEGIN SUBPROB

The projection of $\vec{c}$ onto $\text{span}(\vec{d})$.

\_\_\_\_\_ $\times$

( ) $\vec c$
( ) $\vec c_f$
( ) $\vec d$
( ) $\vec d_f$

# BEGIN SOLUTION

$1 \times \vec d$

Recall the span($\vec x$) is the set of all scalar multiples of $\vec x$ (like $w\vec x$). The closest vector to $\vec y \in \mathbb{R}^n$ is the vector $w * \vec x$ where $w^* = \frac{\vec x \cdot \vec y}{\vec x \cdot \vec x}$.

The problem is asking us to find $w$, put it inside of the blank, and multiply it by $\vec c$.

We know we are trying to find the projection of $\vec c$ onto $\text{span}(\vec{d})$, so it will be our $y$ in this situation, which makes $\vec d$ our $\vec x$. We can now calculate $w^*$.

I would recommend calculating the dot product first and then plugging it into our equation. $$\vec d \cdot \vec c = \begin{bmatrix} -2 \\ 1 \end{bmatrix} \cdot \begin{bmatrix} 1 \\ 7 \end{bmatrix} = (-2)*(1) + (1)*(7) = 5$$
$$\vec d \cdot \vec d = \begin{bmatrix} -2 \\ 1 \end{bmatrix} \cdot \begin{bmatrix} -2 \\ 1 \end{bmatrix} = (-2)*(-2) + (1)*(1) = 5$$

$$
w^* = \frac{\vec d \cdot \vec c}{\vec d \cdot \vec d} = \frac{5}{5} = 1
$$

Since we are trying to find the span($\vec d$) our vector is $\vec d$.

<average>66</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The error vector of the projection of $\vec{c}$ onto $\text{span}(\vec{d})$.

\_\_\_\_\_ $\times$

( ) $\vec c$
( ) $\vec c_f$
( ) $\vec d$
( ) $\vec d_f$

# BEGIN SOLUTION

$-3 \times \vec d_f$

Using what we learned in part 1 of this problem ($w$) we are able to utilize the error vector equation $\vec e = \vec y - w * \vec x$. Recall we are trying to find the projection of $\vec c$ onto $\text{span}(\vec{d})$, so it will be our $y$ in this situation, which makes $\vec d$ our $\vec x$. We learned that $w$ from part 1 is $1$, so our equation is $\vec e = \vec c - 1 * \vec d$.

$$
\vec e = \begin{bmatrix} 1 \\ 7 \end{bmatrix} - \begin{bmatrix} -2 \\ 1 \end{bmatrix} = \begin{bmatrix} 3 \\ 6 \end{bmatrix}
$$

We can now try and find a scalar that when multiplied by one of our multiple choice vectors gives us $\begin{bmatrix} 3 \\ 6 \end{bmatrix}$.

Recall our choices are:

- $\vec c = \begin{bmatrix} 1 \\ 7 \end{bmatrix}$
- $\vec d = \begin{bmatrix} -2 \\ 1 \end{bmatrix}$
- $\vec c_f = \begin{bmatrix} -7 \\ 1 \end{bmatrix}$
- $\vec d_f = \begin{bmatrix} -1 \\ -2 \end{bmatrix}$

<i>Note that we are applying the same transformation as in Problem 1.</i>

We can easily see $-3 * \begin{bmatrix} -1 \\ -2 \end{bmatrix} = \begin{bmatrix} 3 \\ 6 \end{bmatrix}$!

<average>27</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The projection of $\vec{d}$ onto $\text{span}(\vec{c})$.

\_\_\_\_\_ $\times$

( ) $\vec c$
( ) $\vec c_f$
( ) $\vec d$
( ) $\vec d_f$

# BEGIN SOLUTION

$\frac{1}{10} \times \vec c$

Once again the problem is asking us to find $w$, put it inside of the blank, and multiply it by $\vec c$.

We know we are trying to find the projection of $\vec d$ onto $\text{span}(\vec{c})$, so it will be our $y$ in this situation, which makes $\vec c$ our $\vec x$. We can now calculate $w^*$.

I would recommend calculating the dot product first and then plugging it into our equation.
$$\vec c \cdot \vec d = \begin{bmatrix} 1 \\ 7 \end{bmatrix} \cdot \begin{bmatrix} -2 \\ 1 \end{bmatrix} = (1)*(7) + (-2)*(1) = 5$$
$$\vec c \cdot \vec c = \begin{bmatrix} 1 \\ 7 \end{bmatrix} \cdot \begin{bmatrix} 1 \\ 7 \end{bmatrix} = (1)*(1) + (7)*(7) = 50$$

$$
w^* = \frac{\vec c \cdot \vec d}{\vec c \cdot \vec c} = \frac{5}{50} = \frac{1}{10}
$$

Since we are trying to find the span($\vec c$) our vector is $\vec c$.

<average>53</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The error vector of the projection of $\vec{d}$ onto $\text{span}(\vec{c})$.

\_\_\_\_\_ $\times$

( ) $\vec c$
( ) $\vec c_f$
( ) $\vec d$
( ) $\vec d_f$

# BEGIN SOLUTION

$\frac{3}{10} \times \vec c_f$

Using what we learned in part 3 of this problem ($w$) we are able to utilize the error vector equation $\vec e = \vec y - w * \vec x$. Recall we are trying to find the projection of $\vec d$ onto $\text{span}(\vec{d})$, so it will be our $y$ in this situation, which makes $\vec c$ our $\vec x$. We learned that $w$ from part 1 is $1$, so our equation is $\vec e = \vec d - \frac{1}{10} * \vec c$.

\begin{align*}
\vec e &= \begin{bmatrix} -2 \\ 1 \end{bmatrix} - \frac{1}{10} * \begin{bmatrix} 1 \\ 7 \end{bmatrix} \\
&= \begin{bmatrix} -2 \\ 1 \end{bmatrix} - \begin{bmatrix} \frac{1}{10} \\ \frac{7}{10} \end{bmatrix}\\
&= \begin{bmatrix} \frac{-20}{10} \\ \frac{10}{10} \end{bmatrix} - \begin{bmatrix} \frac{1}{10} \\ \frac{7}{10} \end{bmatrix}\\
&= \begin{bmatrix} \frac{-21}{10} \\ \frac{3}{10} \end{bmatrix}
\end{align*}

We can now try and find a scalar, $s$, that when multiplied by one of our multiple choice vectors gives us $\begin{bmatrix} \frac{-21}{10} \\ \frac{3}{10} \end{bmatrix}$.

Recall our choices are:

- $\vec c = \begin{bmatrix} 1 \\ 7 \end{bmatrix}$
- $\vec d = \begin{bmatrix} -2 \\ 1 \end{bmatrix}$
- $\vec c_f = \begin{bmatrix} -7 \\ 1 \end{bmatrix}$
- $\vec d_f = \begin{bmatrix} -1 \\ -2 \end{bmatrix}$

<i>Note that we are applying the same transformation as in Problem 1.</i>

It might be a bit hard to see the answer here, but we want a negative in our first element of our matrix and a positive one in the denominator, which means we want to look at one of the friend vectors.

From here we can see $c_f$ multiplied by $3$ will give us the numerators of our goal ($\begin{bmatrix} \frac{-21}{10} \\ \frac{3}{10} \end{bmatrix}$). The only thing we need to do is divide by $10$, so our $w^* = \frac{3}{10}$.

<average>21</average>

# END SOLUTION

# END SUBPROB

# END PROB