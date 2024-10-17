# BEGIN PROB
Prove the following statement or provide a counterexample: 

# BEGIN SUBPROB

If a vector $\vec{v}$ is orthogonal to a vector $\vec{w}$, then $\vec{v}$ is also orthogonal to the projection of an arbitrary vector $\vec{u}$ onto $\vec{w}$.

# BEGIN SOLUTION

The statement above is true.

Let the following information hold:

- $c$ is a scalar.
- $c\vec{w}$ is the projection of $\vec{u}$ onto $\vec{w}$.

When a vector is orthogonal to another their dot product will equal zero. This means $\vec{v} \cdot \vec{w} = 0$.

From lecture we know:
$$c\vec{w} = \frac{\vec{w} \cdot \vec{u}}{\vec{u} \cdot \vec{u}} \cdot \vec{w}$$

So, now we can solve $c\vec{w} \cdot \vec{v} = \frac{\vec{w} \cdot \vec{u} \cdot \vec{w} \cdot \vec{v}}{\vec{u} \cdot \vec{u}}$. The numerator becomes zero because $\vec{v} \cdot \vec{w} = 0$ and anything multiplied by zero will also be zero. This means the projection of $\vec{u}$ onto $\vec{w}$ is orthogonal to $\vec v$.

# END SOLUTION


# END SUBPROB


# BEGIN SUBPROB

If a vector $\vec{v}$ is orthogonal to a vector $\vec{w}$, then $\vec{v}$ is also orthogonal to the projection of $\vec{w}$ onto an arbitrary vector $\vec{u}$.

# BEGIN SOLUTION

TODO

# END SOLUTION
    


# END SUBPROB


# END PROB