# BEGIN PROB

For a given dataset $\{y_1, y_2, \dots, y_n\}$, let $M_{abs}(h)$ represent the **median** absolute error of the constant prediction $h$ on that dataset (as opposed to the mean absolute error $R_{abs}(h)$).

# BEGIN SUBPROB

For the dataset $\{4, 9, 10, 14, 15\}$, what is $M_{abs}(9)$?

# BEGIN SOLUTION

$5$

The first step is to calculate the absolute errors ($|y_i - h|$).

$$
\begin{align*}
\text{Absolute Errors} &= \{|4-9|, |9-9|, |10-9|, |14-9|, |15-9|\} \\
\text{Absolute Errors} &= \{|-5|, |0|, |1|, |5|, |6|\} \\
\text{Absolute Errors} &= \{5, 0, 1, 5, 6\}
\end{align*}
$$

Now we have to order the values inside of the absolute errors: $\{0, 1, 5, 5, 6\}$. We can see the median is $5$, so $M_{abs}(9) =5$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

For the same dataset $\{4, 9, 10, 14, 15\}$, find another integer $h$ such that $M_{abs}(9) = M_{abs}(h)$.

# BEGIN SOLUTION

$5$ or $15$

Our goal is to find another number that will give us the same median of absolute errors as in part (a).

One way to do this is to plug in a number and guess. Another way requires noticing you can modify $10$ (the middle element) to become $5$ in either direction (negative or positive) because of the absolute value.

We can solve this equation to get $|10-x| = 5 \rightarrow x = 15 \text{ and } x = 5$.

We can then test this by following the same steps as we did in part (a).

**For $x = 15$:**

$$
\begin{align*}
\text{Absolute Errors} &= \{|4-15|, |9-15|, |10-15|, |14-15|, |15-15|\} \\
\text{Absolute Errors} &= \{|-11|, |-6|, |-5|, |-1|, |0|\} \\
\text{Absolute Errors} &= \{11, 6, 5, 1, 0\}
\end{align*}
$$

Then we order the elements to get the absolute errors: $\{0, 1, 5, 6, 11\}$. We can see the median is $5$, so $M_{abs}(15) =5$.

**For $x = 5$:**

$$
\begin{align*}
\text{Absolute Errors} &= \{|4-5|, |9-5|, |10-5|, |14-5|, |15-5|\} \\
\text{Absolute Errors} &= \{|-1|, |4|, |5|, |9|, |10|\} \\
\text{Absolute Errors} &= \{1, 4, 5, 9, 10\}
\end{align*}
$$

We do not have to re-order the elements because they are in order already. We can see the median is $5$, so $M_{abs}(5) =5$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Based on your answers to parts (a) and (b), discuss in **at most two sentences** what is problematic about using the median absolute error to make predictions.

# BEGIN SOLUTION

The numbers $5$ and $15$ are clearly bad predictions (close to the extreme values in the dataset), yet they are considered just as good a prediction by this metric as the number $9$, which is roughly in the center of the dataset. Intuitively, $9$ is a much better prediction, but this way of measuring the quality of a prediction does not recognize that.

# END SOLUTION

# END SUBPROB

# END PROB
