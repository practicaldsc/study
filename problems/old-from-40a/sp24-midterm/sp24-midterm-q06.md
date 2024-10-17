# BEGIN PROB

<i>Source: [Spring 2024 Midterm](../sp24-midterm/index.html), Problem 4d</i>

Consider the following four hypothesis functions:


-  $H_1(x) = H(x) = w_0 + w_1 x^2$
-  $H_2(x) = w_0$
-  $H_3(x) = w_0 + w_1 x$
-  $H_4(x) = w_0 + w_1x + w_2x^2$


Let $H_1^*$, $H_2^*$, $H_3^*$, and $H_4^*$ be the versions of all four hypothesis functions that are using optimal parameters. In the subparts below, fill in the blanks.

# BEGIN SUBPROB

The mean squared error of $H_1^*$ is \_\_\_\_ the mean squared error of $H_2^*$.

( ) Greater than
( ) Greater than or equal to
( ) Equal to
( ) Less than
( ) Less than or equal to
( ) Impossible to tell

# BEGIN SOLUTION

Less than or equal to

$H_1^*$ is a more flexible version of $H_2^*$ – anything $H_2^*$ can do, $H_1^*$ can also do, so $H_1^*$ can't have a higher MSE than $H_1^*$.

Another way to think about this is in $H_1^*$ we have more information to make an educated guess in comparison to $H_2^*$ because of $x^2$. If we have more information, assuming it is useful, then the error will at least be equal to $H_2^*$, but would probably decrease the error. Making the MSE of $H_1^*$ is less than or equal to the MSE of $H_2^*$.

<average>56</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The mean squared error of $H_1^*$ is \_\_\_\_ the mean squared error of $H_3^*$.

( ) Greater than
( ) Greater than or equal to
( ) Equal to
( ) Less than
( ) Less than or equal to
( ) Impossible to tell

# BEGIN SOLUTION

Impossible to tell

$H_1^*$ has a different set of features than $H_2^*$ and vice versa, which makes it impossible to tell – this is not a situation like in (a) or (c), where one hypothesis function has a superset of the features of the other.

<average>36</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The mean squared error of $H_1^*$ is \_\_\_\_ the mean squared error of $H_4^*$.

( ) Greater than
( ) Greater than or equal to
( ) Equal to
( ) Less than
( ) Less than or equal to
( ) Impossible to tell

# BEGIN SOLUTION

Greater than or equal to.

$H_1^*$ is a less flexible version of $H_4^*$, which has the same features as $H_1^*$ but with an added linear term. So, $H_4^*$ can fit all of the same patterns that $H_1^*$ can, but more.

Again, think about adding more information. In $H_4^*$ we can, at best, make a better guess by adding more $x$ variables. At worst it will be the same as $H_1^*$.

<average>45</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

In \_\_\_\_ of the hypothesis functions $H_1^*$,$H_2^*$, $H_3^*$, and $H_4^*$, the sum of the residuals of the function's predictions is 0.

( ) None
( ) $1$
( ) $2$
( ) $3$
( ) All $4$

# BEGIN SOLUTION

All $4$

All $4$ hypothesis functions have intercept terms, which, as we saw in lecture, creates a column of all 1s in their design matrices, which enables the sum of residuals to be $0$.

<average>53</average>

# END SOLUTION

# END SUBPROB

# END PROB