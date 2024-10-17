# BEGIN PROB

<i>Source: [Spring 2023 Final Part 1](../sp23-final-pt1/index.html), Problem 2</i>

Match each dataset with the graph of its mean absolute error, $R_{abs}(h)$.

# BEGIN SUBPROB

<center><img src="../assets/images/sp23-final-pt1/matching.jpg" width="500" height="350"></center>

<br>

$\{4, 7, 9, 10, 11\}$

( ) Graph 1
( ) Graph 2
( ) Graph 3
( ) Graph 4

# BEGIN SOLUTION

Graph 2

The important thing to note here is the y axis is equal to $R_{abs}(h)$ and the x axis is equal to our $h$. The easiest way to figure out which graph belongs to which dataset is to choose some numbers for $h$ and see if a line matches up with the chosen points.

| $h^*$   | $R_{abs}(h)$   |
|---------|---------|
| $0$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-0| = \frac{1}{5} \cdot 41 \approx 8$     |
| $8$  | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-8| = \frac{1}{5} \cdot 11 = 2$  |
| $18$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-18| = \frac{1}{5} \cdot 49 \approx 10$  |

<br>

When looking at these three places we can see that this dataset matches Graph 2.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

<center><img src="../assets/images/sp23-final-pt1/matching.jpg" width="500" height="350"></center>

<br>

$\{-3, 1, 9, 11, 20\}$

( ) Graph 1
( ) Graph 2
( ) Graph 3
( ) Graph 4

# BEGIN SOLUTION

Graph 1

We will use the same approach we used in part (a).

| $h^*$   | $R_{abs}(h)$   |
|---------|---------|
| $0$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-0| = \frac{1}{5} \cdot 44 \approx 9$     |
| $8$  | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-8| = \frac{1}{5} \cdot 34 \approx 7$  |
| $18$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-18| = \frac{1}{5} \cdot 56 \approx 11$  |

<br>

When looking at these three places we can see that this dataset matches Graph 1.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

<center><img src="../assets/images/sp23-final-pt1/matching.jpg" width="500" height="350"></center>

<br>

$\{8, 9, 12, 13, 15\}$

( ) Graph 1
( ) Graph 2
( ) Graph 3
( ) Graph 4

# BEGIN SOLUTION

Graph 3

We will use the same approach we used in the previous parts.

| $h^*$   | $R_{abs}(h)$   |
|---------|---------|
| $0$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-0| = \frac{1}{5} \cdot 44 \approx 11$     |
| $8$  | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-8| = \frac{1}{5} \cdot 17 \approx 3$  |
| $18$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-18| = \frac{1}{5} \cdot 33 \approx 7$  |

<br>

When looking at these three places we can see that this dataset matches Graph 3.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

<center><img src="../assets/images/sp23-final-pt1/matching.jpg" width="500" height="350"></center>

<br>

$\{11, 12, 12, 13, 14\}$

( ) Graph 1
( ) Graph 2
( ) Graph 3
( ) Graph 4

# BEGIN SOLUTION

Graph 4

We will use the same approach we used in the previous parts.

| $h^*$   | $R_{abs}(h)$   |
|---------|---------|
| $0$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-0| = \frac{1}{5} \cdot 62 \approx 12$     |
| $8$  | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-8| = \frac{1}{5} \cdot 22 \approx 4$  |
| $18$   | $\frac{1}{5}\sum_{i = 1}^{5}|y_i-18| = \frac{1}{5} \cdot 28 \approx 6$  |

<br>
When looking at these three places we can see that this dataset matches Graph 4.
Another way would be choosing the only option not chosen in the other parts yet!

# END SOLUTION

# END SUBPROB

# END PROB