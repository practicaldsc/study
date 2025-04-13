# BEGIN PROB

<!-- \[**Clustering**\]\[7 Points\] -->

Given the data on 2-dimensional space:

::: center
   $x_1$   $x_2$
  ------- -------
    -8      -6
    -6      -2
    -4      -6
     2       0
     4       4
     6       0
:::

<!-- ::: center
![image](K-Means.png)
::: -->

We want to apply K-Means to cluster this data. Suppose that $k = 2$ (two
clusters).\

# BEGIN SUBPROB

Where should the centroids converge to intuitively? Write
down the coordinates.

# BEGIN SOLUTION

$$\mu_1^* = \bigg(-6, -\frac{14}{3}\bigg)$$
$$\mu_2^* = \bigg(4, \frac{4}{3}\bigg)$$ $\mu_1$ is the average of 3
points on the bottom left, and $\mu_2$ is the average of 3 points on the
top right.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Explain the K-Means algorithm clearly in words. Remember to
write down a condition to terminate the K-Means algorithm.

# BEGIN SOLUTION


**Lloyd's Algorithm:**

1.  Pick a value of $k$ and randomly initialize $k$ centroids.

2.  Keep the centroids fixed, and update the groups.

    -   Assign each point to the nearest centroid.

3.  Keep the groups fixed, and update the centroids.

    -   Move each centroid to the center of its group by averaging their
        coordinates.

4.  Repeat steps 2 and 3 until the centroids stop changing.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Now, let's show few steps of K-Means by filling out these
following tables. Assume we start with $\mu_1 = (2, 1)$ and
$\mu_2 = (3, 4)$ as the initial centers.

::: center
                $\mu_1$    $\mu_2$
  ------------ ---------- ----------
   **Iter 0**   $(2, 1)$   $(3, 4)$
   **Iter 1**             
   **Iter 2**             
   **Iter 3**             

\
:::

For each step, write down the new centers.

::: center
   $x_1$   $x_2$   **Iter 0**   **Iter 1**   **Iter 2**   **Iter 3**
  ------- ------- ------------ ------------ ------------ ------------
    -8      -6         1                                 
    -6      -2         1                                 
    -4      -6         1                                 
     2       0         1                                 
     4       4         2                                 
     6       0         1                                 

\
:::

For each step, write 1 if the point belongs to cluster 1, and write 2 if
the point belongs to cluster 2. The column for Iter 0 is already filled.


::: center
K-Means at iteration 0.
:::

**Note:** You do not have to calculate the distances explicitly (i.e.
you can use your intuition in determining which points belong to which
clusters). It is also possible that you might not need to use all 3
iterations.

# BEGIN SOLUTION

::: center
                   $\mu_1$       $\mu_2$
  ------------ --------------- ------------
   **Iter 0**     $(2, 1)$       $(3, 4)$
   **Iter 1**   $(-2, -14/5)$    $(4, 4)$
   **Iter 2**   $(-6,-14/3)$    $(4, 4/3)$
   **Iter 3**   $(-6, -14/3)$   $(4, 4/3)$
:::

::: center
   $x_1$   $x_2$   **Iter 0**   **Iter 1**   **Iter 2**   **Iter 3**
  ------- ------- ------------ ------------ ------------ ------------
    -8      -6         1            1            1            1
    -6      -2         1            1            1            1
    -4      -6         1            1            1            1
     2       0         1            2            2            2
     4       4         2            2            2            2
     6       0         1            2            2            2
:::

<!-- ::: center
![image](K-Means_Iter_final.png)
::: -->

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Depending on our initial centroids, K-Means may "converge"
to a clustering that does **not** actually have the lowest possible
inertia. In other words, like gradient descent, K-Means can get caught
in a local minimum. Write down a solution to address this issue.

# BEGIN SOLUTION

Some solutions:

-   Run K-Means several times, each with different randomly chosen
    initial centroids. Keep track of the inertia of the final result in
    each attempt. Choose the attempt with the lowest inertia.

-   Choose one initial centroid at random, and choose the remaining
    initial centroids by maximizing distance from all other centroids.

# END SOLUTION

# END SUBPROB

# END PROB