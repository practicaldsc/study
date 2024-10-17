# BEGIN PROB

Fill in the blanks for each set of vectors below to accurately describe their relationship and span.

$$\vec{a} = \begin{bmatrix} 1 \\ 3 \end{bmatrix} \qquad \vec{b} = \begin{bmatrix} -2 \\ 1 \end{bmatrix}$$

"$\vec{a}$ and $\vec{b}$ are \_\_(i)\_\_, meaning they span a \_\_(ii)\_\_. The vector  $\vec{c} = \begin{bmatrix} -6 \\ 11 \end{bmatrix}$  \_\_(iii)\_\_ in the span of $\vec{a}$ and $\vec{b}$. $\vec{a}$ and $\vec{b}$ are  \_\_(iv)\_\_, meaning the angle between them is  \_\_(v)\_\_"

# BEGIN SUBPROB

What goes in \_\_(i)\_\_?

( ) linearly independent
( ) linearly dependent

# BEGIN SOLUTION

Linearly Independent

Vectors $\vec{a}$ and $\vec{b}$ are linearly independent because they aren't multiples of each other. They each point in different directions, so we can't express either vector as a scalar multiple of the other.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What goes in \_\_(ii)\_\_?

( ) line
( ) plane
( ) cube
( ) unknown

# BEGIN SOLUTION

Plane

Any two linearly independent vectors must span a plane. Geometrically, we can think of all scalar multiples of a single vector to lie along a single line. Then, linear combinations of any two vectors pointing in different directions must lie on the same plane.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What goes in \_\_(iii)\_\_?

( ) is
( ) is not
( ) may be

# BEGIN SOLUTION

is

We can check if $\vec{c}$ lies in the span of $\vec{a}$ and $\vec{b}$ if there exists some constants $c_1$ and $c_2$ such that $c_1 \vec{a} + c_2 \vec{b} = \vec{c}$. Plugging in what we know: $$c_1 \begin{bmatrix} 1 \\ 3 \end{bmatrix} + c_2 \begin{bmatrix} -2 \\ 1 \end{bmatrix} = \begin{bmatrix} -6 \\ 11 \end{bmatrix}$$ 
This gives us the system of equations:
$$c_1 (1) + c_2 (-2) = -6$$ 
$$c_1 (3) + c_2 (1) = 11$$
Solving this system gives us $c_1 = \frac{16}{7}$, $c_2 = \frac{29}{7}$, which means $\vec{c}$ does lie in the span of $\vec{a}$ and $\vec{b}$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What goes in \_\_(iv)\_\_?

( ) orthogonal
( ) collinear
( ) neither orthogonal nor collinear

# BEGIN SOLUTION

neither orthogonal nor collinear

The vectors $\vec{a}$ and $\vec{b}$ are orthogonal if $\vec{a} \cdot \vec{b} = 0$. We can compute $\vec{a} \cdot \vec{b} = (1)(-2) + (3)(1) = 1 \neq 0$, so $\vec{a}$ and $\vec{b}$ are not orthogonal.

The vectors $\vec{a}$ and $\vec{b}$ are collinear if we can write one vector as a scalar multiple of the other. But we already know $\vec{a}$ and $\vec{b}$ are linearly independent, so they don't lie along the same line and aren't collinear.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What goes in \_\_(v)\_\_?

( ) 0 or 180 degrees
( ) something else
( ) 90 degrees

# BEGIN SOLUTION

something else

If two vectors are orthogonal, the angle between them is 90 degrees. If two vectors are collinear, the angle between them is 0 or 180 degrees. Since $\vec{a}$ and $\vec{b}$ are neither of these, then the angle between them must be something else.

# END SOLUTION

# END SUBPROB

# END PROB