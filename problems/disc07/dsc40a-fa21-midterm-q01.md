# BEGIN PROB

<!-- <i>Source: [Fall 2021 Midterm](../fa21-midterm/index.html), Problem 1</i> -->

Biff the Wolverine just made an Instagram account and has been keeping track of
the number of likes his posts have received so far.

His first 7 posts have received a mean of 16 likes; the specific like
counts in sorted order are

$$8, 12, 12, 15, 18, 20, 27$$

Biff the Wolverine wants to predict the number of likes his next post will
receive, using a constant prediction rule $h$. For each loss function
$L(y_i, h)$, determine the constant prediction $h^*$ that minimizes
average loss. If you believe there are multiple minimizers, specify
them all. If you believe you need more information to answer the
question or that there is no minimizer, state that clearly. **Give a
brief justification for each answer.**

# BEGIN SUBPROB

$L(y_i, h) = |y_i - h|$

# BEGIN SOLUTION

15.

This is absolute loss, and hence we're looking for the minimizer
of mean absolute error, which is the median, 15.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

$L(y_i, h) = (y_i - h)^2$

# BEGIN SOLUTION

16.

This is squared loss, and hence we're looking for the minimizer
of mean squared error, which is the mean, 16.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

$L(y_i, h) = 4(y_i - h)^2$

# BEGIN SOLUTION

16.

This is squared loss, multiplied by a constant. Note that when
we go to minimize empirical risk for this loss function, we will take
the derivative of empirical risk and set it equal to 0; at that point
the constant factor of 4 can be divided from both sides, so this problem
boils down to minimizing ordinary mean squared error. The only
difference is that the graph of mean squared error will be stretched
vertically by a factor of 4; the minimizing value will be in the same
place.

For more justification, here we consider any general re-scaling
$\alpha (y_i-h)^2$:

$$
\begin{aligned}
    R_{sq}(h) &= \frac{1}{n} \sum_{i = 1}^n \alpha (y_i - h)^2 \\
              &= \alpha \cdot \frac{1}{n} \sum_{i = 1}^n (y_i - h)^2 \\
  \frac{d}{dh} R_{sq}(h) &= \alpha \cdot \frac{1}{n} \sum_{i = 1}^n 2(y_i - h)(-1) = 0\\
  &\implies -\frac{2\alpha}{n}\sum_{i = 1}^n (y_i - h) = 0 \\
  &\implies \sum_{i = 1}^n (y_i - h) = 0 \\
  &\implies h^* = \frac{1}{n} \sum_{i = 1}^n y_i
\end{aligned}
$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

$L(y_i, h) = \begin{cases} 0 & h = y_i \\ 100 & h \neq y_i \end{cases}$

# BEGIN SOLUTION

12.

This is a scaled version of 0-1 loss. We know that empirical risk for
0-1 loss is minimized at the mode, so that also applies here. The mode,
i.e. the most common value, is 12.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

$L(y_i, h) = (3y_i - 4h)^2$

# BEGIN SOLUTION

12.

Note that we can write $(3y - 4h)^2$ as
$\left( 3 \left( y - \frac{4}{3}h \right) \right)^2 = 9 \left( y - \frac{4}{3}h \right)^2$.
As we've seen, the constant factor out front has no impact on the
minimizing value. Using the same principle as in the last part, we can
say that
$$\frac{4}{3} h^* = \bar{x} \implies h^* = \frac{3}{4} \bar{x} = \frac{3}{4} \cdot 16 = 12$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

$L(y_i, h) = (y_i - h)^3$

_Hint: Do not spend too long on this subpart._

# BEGIN SOLUTION

No minimizer.

Note that unlike $|y_i - h|$, $(y_i - h)^2$, and all of the other loss
functions we've seen, $(y_i - h)^3$ tends towards $-\infty$, rather than
having a minimum output of 0. This means that there is no $h$ that
minimizes $\frac{1}{n} \sum_{i = 1}^n (y_i - h)^3$; the larger we make
$h$, the more negative (and hence "smaller\") this empirical risk
becomes.

# END SOLUTION

# END SUBPROB

# END PROB
