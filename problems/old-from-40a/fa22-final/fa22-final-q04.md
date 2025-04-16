# BEGIN PROB

Consider the following dataset of $n=6$ points in $d=2$ dimensions.

::: center
   $x^{(1)}$   $x^{(2)}$
  ----------- -----------
    -8         -6
    -6         -2
    -4         -6
     2          0
     4          4
     6          0
:::

We'd like to use $k$-means clustering to cluster the data into $k=2$ clusters.

# BEGIN SUBPROB

Plot out the data. What are the optimal locations for the centroids, $\vec \mu_1$ and $\vec \mu_2$? Write
down the coordinates.

# BEGIN SOLUTION

**Answer**:

<center><img src="../assets/images/disc13/q1-sol-graph.png" width="500" alt="hello"></center>

$$\vec \mu_1 = \left( -6, -\frac{14}{3} \right)$$
$$\vec \mu_2 = \left( 4, \frac{4}{3} \right)$$

$\vec \mu_1$ is the average of 3
points on the bottom left, and $\vec \mu_2$ is the average of 3 points on the
top right.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Remember, if our data is high-dimensional, we won't be able to visualize it to determine our centroids. Instead, we'll need to run the $k$-means clustering algorithm.

Perform three iterations of the $k$-means algorithm by hand. Assume that we initialize the centroids at $\vec \mu_1 = \left( 2, 1 \right)$ and $\vec \mu_2 = \left( 3, 4 \right)$. In each iteration:

1. Write down the closest centroid (1 or 2) to each point in Table 1.
2. Then, write down the updated locations of the centroids in Table 2.


::: center
Table 1:

   $x^{(1)}$   $x^{(2)}$   **Iter 1**   **Iter 2**   **Iter 3**
  ----------- ----------- ------------ ------------ ------------
    -8        -6                     
    -6        -2                 
    -4        -6        
     2         0         
     4         4         
     6         0         
:::

::: center
Table 2:

                   $\vec \mu_1$       $\vec \mu_2$
  ------------ --------------- ------------
   **Iter 0**     $(2, 1)$       $(3, 4)$
   **Iter 1**      
   **Iter 2**   
   **Iter 3**   
:::


***Note***: You don't have to calculate the distances explicitly (i.e.
you can use your intuition in determining which points belong to which
clusters).

# BEGIN SOLUTION

**Answer**:

::: center
Table 1:

   $x^{(1)}$   $x^{(2)}$   **Iter 1**   **Iter 2**   **Iter 3**
  ----------- ----------- ------------ ------------ ------------
    -8        -6           1            1            1
    -6        -2           1            1            1
    -4        -6           1            1            1
     2         0           1            2            2
     4         4           2            2            2
     6         0           1            2            2     
:::

::: center
Table 2:

                   $\vec \mu_1$       $\vec \mu_2$
  ------------ --------------- ------------
   **Iter 0**     $(2, 1)$       $(3, 4)$
   **Iter 1**   $(-2, -14/5)$    $(4, 4)$
   **Iter 2**   $(-6,-14/3)$    $(4, 4/3)$
   **Iter 3**   $(-6, -14/3)$   $(4, 4/3)$
:::
       

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Depending on our initial centroids, $k$-means may "converge"
to a clustering that does **not** actually have the lowest possible
inertia. In other words, like gradient descent, $k$-means can get caught in a local minimum. What are possible solutions to this issue?

# BEGIN SOLUTION

**Possible answers**:

-   Run $k$-means several times, each with different randomly chosen initial centroids. Keep track of the inertia of the final result in each attempt. Choose the attempt with the lowest inertia.

- Choose one initial centroid at random, and choose the remaining
    initial centroids by maximizing distance from all other centroids. This is the strategy behind $k$-means++.

# END SOLUTION

# END SUBPROB

# END PROB