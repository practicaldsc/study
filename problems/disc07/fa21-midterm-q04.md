# BEGIN PROB

Billy decides to take on a part-time job as a waiter at
the Panda Express in Pierpont. For two months, he kept track of
all of the total bills he gave out to customers along with the tips they
then gave him, all in dollars. Below is a scatter plot of Billy's tips
and total bills.

<!-- TODO -->

<center><img src="../assets/images/disc07/dirtybirds.png" width="600" height="330"></center>

Throughout this question, assume we are trying to fit a linear
prediction rule $H(x) = w_0 + w_1x$ that uses total bills to predict
tips, and assume we are finding optimal parameters by minimizing mean
squared error.

# BEGIN SUBPROB

Which of these is the most likely value for $r$, the
correlation between total bill and tips? Why?

::: center
$$-1 \qquad -0.75 \qquad -0.25 \qquad 0 \qquad 0.25 \qquad 0.75 \qquad 1$$
:::

# BEGIN SOLUTION

0.75.

It seems like there is a pretty strong, but not perfect, linear
association between total bills and tips.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The variance of the tip amounts is 2.1. Let $M$ be the mean
squared error of the best linear prediction rule on this dataset (under
squared loss). Is $M$ less than, equal to, or greater than 2.1? How can
you tell?

# BEGIN SOLUTION

$M$ is less than 2.1. The variance is equal to the MSE of the constant
prediction rule.

Note that the MSE of the best linear prediction rule will always be less
than or equal to the MSE of the best constant prediction rule $h$. The
only case in which these two MSEs are the same is when the best linear
prediction rule is a flat line with slope 0, which is the same as a
constant prediction. In all other cases, the linear prediction rule will
make better predictions and hence have a lower MSE than the constant
prediction rule.

In this case, the best linear prediction rule is clearly not flat, so
$M < 2.1$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose we use the formulas from class on Billy's dataset
and calculate the optimal slope $w_1^*$ and intercept $w_0^*$ for this
prediction rule.

Suppose we add the value of 1 to every total bill $x$, effectively
shifting the scatter plot 1 unit to the right. **Note that doing this
does not change the value of $w_1^*$.** What amount should we add to
each tip $y$ so that the value of $w_0^*$ also does not change? Your
answer should involve one or more of $\bar{x}, \bar{y}, w_0^*, w_1^*,$
and any constants.

_Note: To receive full points, you must provide a rigorous explanation,
though this explanation only takes a few lines. However, we will award
partial credit to solutions with the correct answer, and it's possible
to arrive at the correct answer by drawing a picture and thinking
intuitively about what happens._

# BEGIN SOLUTION

We should add $w_1^*$ to each tip $y$.

First, we present the rigorous solution.

Let $\bar{x}_\text{old}$ represent the previous mean of the $x$'s and
$\bar{x}_\text{new}$ represent the new mean of the $x$'s. Then, we know
that $\bar{x}_\text{new} = \bar{x}_\text{old} + 1$.

Also, let $\bar{y}_\text{old}$ and $\bar{y}_\text{new}$ represent the old
and new mean of the $y$'s. We will try and find a relationship between
these two quantities.

We want the two intercepts to be the same. The intercept for the old
line is $\bar{y}_\text{old} - w_1^* \bar{x}_\text{old}$ and the
intercept for the new line is
$\bar{y}_\text{new} - w_1^* \bar{x}_\text{new}$. Setting these equal
yields

$$
\begin{aligned}
    \bar{y}_\text{new} - w_1^* \bar{x}_\text{new} &= \bar{y}_\text{old} - w_1^* \bar{x}_\text{old} \\
     \bar{y}_\text{new} - w_1^* (\bar{x}_\text{old} + 1) &= \bar{y}_\text{old} - w_1^* \bar{x}_\text{old} \\
     \bar{y}_\text{new} &= \bar{y}_\text{old} - w_1^* \bar{x}_\text{old} + w_1^* (\bar{x}_\text{old} + 1) \\
     \bar{y}_{\text{new}} &= \bar{y}_\text{old} + w_1^*
\end{aligned}
$$

Thus, in order for the intercepts to be equal, we need the mean of the
new $y$'s to be $w_1^*$ greater than the mean of the old $y$'s. Since
we're told we're adding the same constant to each $y$ that constant is
$w_1^*$.

Another way to approach the question is as follows: consider any point
that lies directly on a line with slope $w_1^*$ and intercept $w_0^*$.
Consider how the slope between two points on a line is calculated:
$\text{slope} = \frac{y_2 - y_1}{x_2 - x_1}$. If $x_2 - x_1 = 1$, in
order for the slope to remain fixed we must have that
$y_2 - y_1 = \text{slope}$. For a concrete example, think of the line
$y = 5x + 2$. The point $(1, 7)$ is on the line, as is the point
$(1 + 1, 7 + 5) = (2, 12)$.

In our case, none of our points are guaranteed to be **on** the line
defined by slope $w_1^*$ and intercept $w_0^*$. Instead, we just want to
be guaranteed that the points have the same regression line after being
shifted. If we follow the same principle, though, and add 1 to every $x$
and $w_1^*$ to every $y$, the points' relative positions to the line
will not change (i.e. the vertical distance from each point to the line
will not change), and so that will remain the line with the lowest MSE,
and hence $w_0^*$ and $w_1^*$ won't change.

# END SOLUTION

# END SUBPROB

# END PROB
