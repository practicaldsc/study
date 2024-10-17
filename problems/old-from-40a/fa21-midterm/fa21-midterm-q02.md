# BEGIN PROB

<i>Source: [Fall 2021 Midterm](../fa21-midterm/index.html), Problem 2</i>

Consider a set of 23 data points $y_1, y_2, y_3, ..., y_{23}$ such that
$y_1 < y_2 < ... < y_{23}$. Let's call this Dataset A.

We create a new dataset, Dataset B, by repeating each point in Dataset A
once. That is, Dataset B is the set of 46 points
$y_1, y_1, y_2, y_2, ..., y_{23}, y_{23}$.

Answer the following questions regarding the relationship between
Dataset A and Dataset B. **Justify your answers.**

# BEGIN SUBPROB

Suppose the minimizer of mean absolute error $R_{abs}(h)$
for Dataset A is 5. What is the minimizer of mean absolute error for
Dataset B? If you believe there are multiple minimizers, specify them
all. If you believe you need more information to answer the question,
state that clearly.

# BEGIN SOLUTION

The minimizer of MAE for Dataset B is still 5. 

Note that when we repeat
each data point, we go from having an odd number of data points (23) to
an even number (46). This means the minimizer is the set of all values
between the middle two values. But the middle two values will now both
be $y_{12}$, and so there are no numbers "in between\" them -- only
$y_{12}$ minimizes MAE.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose the *mean absolute deviation from the median* for
Dataset A is 17. What is the *mean absolute deviation from the median*
for Dataset B? If you believe you need more information to answer the
question, state that clearly.

# BEGIN SOLUTION

The mean absolute deviation from the median for Dataset B is still 17.

As we saw in previous part, the median itself does not change. When adding
together the deviations from the median, each point is repeated twice,
so the sum of all deviations from the median is doubled. However, there
are twice as many data points in Dataset B than there are in Dataset A,
so we divide by $2n$ (46) instead of $n$ (23) in our average.

In short, for Dataset B both the numerator and denominator in the
calculation of mean absolute deviation from the median
$\frac{\sum_{i = 1}^n |y_i - \text{Median}(y)|}{n}$ are double what they
were for Dataset A, so the end result is the same as for Dataset A.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose the function $R_A(h)$ represents mean absolute
error for Dataset A and $R_B(h)$ represents mean absolute error for
Dataset B.

Is it true that $R_A(h) = R_B(h)$ for any real number $h$? (In other
words, are the graphs of $R_A(h)$ and $R_B(h)$ identical?) Explain your
reasoning.

# BEGIN SOLUTION

Yes, $R_{A}(h) = R_{B}(h)$.

Recall that the definition of $R_{abs}(h)$ is:

$$R_{abs}(h) = \frac{1}{n} \sum_{i = 1}^n |y_i - h|$$

For the first dataset, we have:

$$R_{A}(h) = \frac{1}{23} \sum_{i = 1}^{23} |y_i - h|$$

and for the second dataset, we have:

$$\begin{aligned}
R_{B}(h) &= \frac{1}{46} \sum_{i = 1}^{46} \left( |y_1 - h| + |y_1 - h| + |y_2 - h| + |y_2 - h| + ... + |y_{23} - h| + |y_{23} - h| \right) \\
&= \frac{1}{46} \left( 2 \sum_{i = 1}^{23} |y_i - h| \right) \\ &= \frac{1}{23} \sum_{i = 1}^{23} |y_i - h| \\ &= R_{A}(h) 
\end{aligned}$$

# END SOLUTION

# END SUBPROB

# END PROB