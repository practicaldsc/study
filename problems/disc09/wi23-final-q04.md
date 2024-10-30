# BEGIN PROB

<!-- Regression Question -->

<i>Source: [Winter 2023 Final](../wi23-final/index.html), Problem 4</i>

Reggie and Essie are given a dataset of real features
$x_i \in \mathbb{R}$ and observations $y_i$. Essie proposes the
following linear prediction rule:
$$H_1(\alpha_0,\alpha_1) = \alpha_0 + \alpha_1 x_i.$$ and Reggie
proposes to use $v_i=(x_i)^2$ and the prediction rule
$$H_2(\gamma_0,\gamma_1) = \gamma_0 + \gamma_1 v_i.$$

# BEGIN SUBPROB

Give an example of a dataset $\{(x_i,y_i)\}_{i=1}^n$ for
which minimum MSE$(H_2) <$ minimum MSE$(H_1)$. Explain.

# BEGIN SOLUTION
Example: If the datapoints follow a quadratic form
$y_i=x_i^2$ for all $i$, then the $H_2$ prediction rule will achieve a
zero error while $H_1>0$ since the data do not follow a linear form.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Give an example of a dataset $\{(x_i,y_i)\}_{i=1}^n$ for
which minimum MSE$(H_2) =$ minimum MSE$(H_1)$. Explain.


# BEGIN SOLUTION

Example 1: If the response variables are constant $y_i=c$ for all $i$,
then for both prediciton rules by setting $\alpha_0=\gamma_0=c$ and
$\alpha_1=\gamma_1=0$, both predictors will achieve MSE=0.

Example 2: when every single value of the features $x_i$ and $x^2_
i$ coincide in the dataset (this occurs when $x = 0$ or $x = 1$), the
parameters of both prediction rules will be the same, as will the MSE.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

A new feature $z$ has been added to the dataset.

Essie proposes a linear regression model using two predictor variables
$x,z$ as $$H_3(w_0,w_1,w_2) = w_0 + w_1 x_i +w_2 z_i.$$

Explain if the following statement is **True or False** (prove or provide
counter-example).

Reggie claims that having more features will lead to a smaller error,
therefore the following prediction rule will give a smaller MSE:
$$H_4(\alpha_0,\alpha_1,\alpha_2,\alpha_3) = \alpha_0 + \alpha_1 x_i +\alpha_2 z_i + \alpha_3 (2x_i-z_i)$$

# BEGIN SOLUTION

$H_4$ can be rewritten as
$$H_4(\alpha_0,\alpha_1,\alpha_2,\alpha_3) = \alpha_0 + (\alpha_1+2\alpha_3) x_i +(\alpha_2 - \alpha_3)z_i$$
By setting $\tilde{\alpha}_1=\alpha_1+2\alpha_3$ and
$\tilde{\alpha_2}= \alpha_2 - \alpha_3$ then

$$H_4(\alpha_0,\alpha_1,\alpha_2,\alpha_3) = H_4(\alpha_0,\tilde{\alpha}_1,\tilde{\alpha}_2) = \alpha_0 + \tilde{\alpha_1} x_i +\tilde{\alpha}_2 z_i$$

Thus $H_4$ and $H_3$ have the same normal equations and therefore the
same minimum MSE.

# END SOLUTION

# END SUBPROB

# END PROB