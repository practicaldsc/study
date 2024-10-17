# BEGIN PROB

<i>Source: [Spring 2024 Final](../sp24-final/index.html), Problem 2</i>

Consider a dataset of 3 values, $y_1 < y_2 < y_3$, with a mean of 2. Let
$Y_\text{abs}(h) = \frac{1}{3} \sum_{i = 1}^3 |y_i - h|$ represent the
mean absolute error of a constant prediction $h$ on this dataset of 3
values.

Similarly, consider another dataset of 5 values,
$z_1 < z_2 < z_3 < z_4 < z_5$, with a mean of 12. Let
$Z_\text{abs}(h) = \frac{1}{5} \sum_{i = 1}^5 |z_i - h|$ represent the
mean absolute error of a constant prediction $h$ on this dataset of 5
values.

Suppose that $y_3 < z_1$, and that $T_\text{abs}(h)$ represents the mean
absolute error of a constant prediction $h$ on the combined dataset of 8
values, $y_1, ..., y_3, z_1, ..., z_5$.

# BEGIN SUBPROB

Fill in the blanks:

**"{ i } minimizes $Y_\text{abs}(h)$, { ii } minimizes $Z_\text{abs}(h)$, and
{ iii } minimizes $T_\text{abs}(h)$."**


1.  What goes in blank { i }?

( ) $y_1$
( ) any value between $y_1$ and $y_2$ (inclusive)
( ) $y_2$
( ) $y_3$
( ) $z_1$

2.  What goes in blank { ii }?

( ) $z_1$
( ) $z_2$
( ) any value between $z_2$ and $z_3$ (inclusive)
( ) any value between $z_2$ and $z_4$ (inclusive)
( ) $z_3$

3.  What goes in blank { iii }?

( ) $y_2$
( ) $y_3$
( ) any value between $y_3$ and $z_1$ (inclusive)
( ) any value between $z_1$ and $z_2$ (inclusive)
( ) any value between $z_2$ and $z_3$ (inclusive)

# BEGIN SOLUTION

The values of the three blanks are: $y_2$, $z_3$, and any value between $z_1$ and $z_2$ (inclusive).

For the first blank, we know the median of the y-dataset minimizes mean absolute error of a constant prediction on the y-dataset. Since $y_1 < y_2 < y_3$, $y_2$ is the unique minimizer.

For the second blank, we can also use the fact that the median of the z-dataset minimizes mean absolute error of a constant prediction on the z-dataset. Since $z_1 < z_2 < z_3 < z_4 < z_5$, $z_3$ is the unique minimizer.

For the third blank, we know that when there are an odd number of data points in a dataset, any values between the middle two (inclusive) minimize mean absolute error. Here, the middle two in the full dataset of 8 are $z_1$ and $z_2$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

For any $h$, it is true that:

$$T_\text{abs}(h) = \alpha Y_\text{abs}(h) + \beta Z_\text{abs}(h)$$

for some constants $\alpha$ and $\beta$. What are the values of $\alpha$
and $\beta$? Give your answers as integers or simplified fractions with
no variables.

# BEGIN SOLUTION

$\alpha = \frac{3}{8}$, $\beta = \frac{5}{8}$.

To find $\alpha$ and $\beta$, we need to construct a similar-looking equation to the one above. We can start by looking at our equation for $T_\text{abs}(h)$:

$$T_\text{abs}(h) = \frac{1}{8} \sum_{i = 1}^8 |t_i - h|$$

Now, we can split the sum on the right hand side into two sums, one for our $y$ data points and one for our $z$ data points:

$$T_\text{abs}(h) = \frac{1}{8} \left(\sum_{i = 1}^3 |y_i - h| + \sum_{i = 1}^5 |z_i - h|\right)$$

Each of these two mini sums can be represented in terms of $Y_\text{abs}(h)$ and $Z_\text{abs}(h)$:

$$T_\text{abs}(h) = \frac{1}{8} \left(3 \cdot Y_\text{abs}(h) + 5 \cdot Z_\text{abs}(h)\right)$$
$$T_\text{abs}(h) = \frac38 \cdot Y_\text{abs}(h) + \frac58 \cdot Z_\text{abs}(h)$$

By looking at this final equation we've built, it is clear that $\alpha = \frac{3}{8}$ and $\beta = \frac{5}{8}$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Show that $Y_\text{abs}(z_1) = z_1 - 2$.

*Hint: Use the fact that you know the mean of $y_1, y_2, y_3$.*

# BEGIN SOLUTION

We can start by plugging $z_1$ into $Y_\text{abs}(h)$: 

$$Y_\text{abs}(z_1) = \frac{1}{3} \left( | z - y_1 | + | z - y_2 | + |z - y_3| \right)$$

Since $$z_1 > y_3 > y_2 > y_1$$, all of the absolute values can be dropped and we can write:

$$Y_\text{abs}(z_1) = \frac{1}{3} \left( (z_1 - y_1) + (z_1 - y_2) + (z_3 - y_3) \right)$$

This can be simplified to:

$$Y_\text{abs}(h) = \frac{1}{3} \left( 3z_1 - (y_1 + y_2 + y_3) \right) = \frac{1}{3} \left( 3z_1 - 3 \cdot \bar{y}\right) = z_1 - \bar{y} = z_1 - 2$$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose the mean absolute deviation from the median in the full dataset
of 8 values is 6. What is the value of $z_1$?

*Hint: You'll need to use the results from earlier parts of this
question.*

( ) $2$ 
( ) $3$ 
( ) $5$ 
( ) $6$ 
( ) $7$ 
( ) $9$ 
( ) $11$

# BEGIN SOLUTION

$3$.

We are given that $T_\text{abs}(\text{median}) = 6$. This means that any value (inclusive) between $z_1$ and $z_2$ minimize $T_\text{abs}(h)$, with the output being always being 6. So, $T_\text{abs}(z_1) = 6$.  Let's see what happens when we plug this into
$T_\text{abs}(h) = \frac{3}{8} Y_\text{abs}(h) + \frac{5}{8} Z_\text{abs}(h)$ from earlier:

$$T_\text{abs}(z_1) = \frac{3}{8} Y_\text{abs}(z_1) + \frac{5}{8} Z_\text{abs}(z_1)$$
$$(6) = \frac{3}{8} Y_\text{abs}(z_1) + \frac{5}{8} Z_\text{abs}(z_1)$$

If we could write $Y_\text{abs}(z_1)$ and $Z_\text{abs}(z_1)$ in terms of $z_1$, we could solve for $z_1$ and our work would be done, so let's do that. $Y_\text{abs}(z_1) = z_1 - 2$ from earlier. $Z_\text{abs}(z_1)$ simplifies as follows (knowing that $\bar{z} = 12$):

$$Z_\text{abs}(z_1) = \frac{1}{5} \sum_{i = 1}^5 |z_i - z_1|$$
$$Z_\text{abs}(z_1) = \frac{1}{5} \left(|z_1 - z_1| + |z_2 - z_1| + |z_3 - z_1| + |z_4 - z_1| + |z_5 - z_1|\right)$$
$$Z_\text{abs}(z_1) = \frac{1}{5} \left(0 + (z_2 + z_3 + z_4 + z_5) - 4z_1\right)$$
$$Z_\text{abs}(z_1) = \frac{1}{5} \left((z_2 + z_3 + z_4 + z_5) - 4z_1 + (z_1 - z_1)\right)$$
$$Z_\text{abs}(z_1) = \frac{1}{5} \left((z_1 + z_2 + z_3 + z_4 + z_5) - 5z_1\right)$$
$$Z_\text{abs}(z_1) = \bar{z} - z_1$$
$$Z_\text{abs}(z_1) = (12) - z_1$$

Subbing back into our main equation:

$$(6) = \frac{3}{8} Y_\text{abs}(z_1) + \frac{5}{8} Z_\text{abs}(z_1)$$
$$6 = \frac{3}{8}(z_1 - 2) + \frac{5}{8}(12 - z_1)$$
$$z_1 = 3$$

# END SOLUTION

# END SUBPROB

# END PROB