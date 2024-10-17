# BEGIN PROB

<i>Source: [Spring 2023 Final Part 1](../sp23-final-pt1/index.html), Problem 4</i>

In simple linear regression, our goal was to fit a
prediction rule of the form $H(x) = w_0 + w_1x$. We found many
equivalent formulas for the slope of the regression line:

$$w_1^* =\displaystyle\frac{\displaystyle\sum_{i=1}^n (x_i - \overline x)(y_i - \overline y)}{\displaystyle\sum_{i=1}^n (x_i - \overline x)^2}
= \displaystyle\frac{\displaystyle\sum_{i=1}^n (x_i - \overline x)y_i}{\displaystyle\sum_{i=1}^n (x_i - \overline x)^2}
= r \cdot \displaystyle\frac{\sigma_y}{\sigma_x}$$

Show that any one of the above formulas is equivalent to the formula
below.

$$\displaystyle\frac{\displaystyle\sum_{i=1}^n (x_i - \overline x)(y_i + 2)}{\displaystyle\sum_{i=1}^n (x_i - \overline x)^2}$$

In other words, this is yet another formula for $w_1^*$.

# BEGIN SOLUTION

We'll show the equivalence to the middle formula above. Since the
denominators are the same, we just need to show
$$\begin{align*}
     \displaystyle\sum_{i=1}^n (x_i - \overline x)(y_i + 2) &= \displaystyle\sum_{i=1}^n (x_i - \overline x)y_i.\\
     \displaystyle\sum_{i=1}^n (x_i - \overline x)(y_i + 2) &= \displaystyle\sum_{i=1}^n (x_i - \overline x)y_i + \displaystyle\sum_{i=1}^n (x_i - \overline x)\cdot2 \\
     &= \displaystyle\sum_{i=1}^n (x_i - \overline x)y_i + 2\cdot\displaystyle\sum_{i=1}^n (x_i - \overline x) \\
    &= \displaystyle\sum_{i=1}^n (x_i - \overline x)y_i + 2\cdot0 \\
    &= \displaystyle\sum_{i=1}^n (x_i - \overline x)y_i\\
\end{align*}$$

This proof uses a fact we've already seen, that $\displaystyle\sum_{i=1}^n (x_i - \overline x) = 0$. It is not necesary to re-prove this fact when answering this question.

# END SOLUTION

# END PROB