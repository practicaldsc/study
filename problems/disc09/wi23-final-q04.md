# BEGIN PROB

<!-- Regression Question -->

Reggie and Essie are given a dataset of real features
$x_i \in \mathbb{R}$ and observations $y_i$. Essie proposes the
following hypothesis function:
$$F(x_i) = \alpha_0 + \alpha_1 x_i$$ and Reggie
proposes to the following linear prediction rule:
$$G(x_i) = \gamma_0 + \gamma_1 x_i^2$$

# BEGIN SUBPROB

Let MMSE$(F)$ be the minimum value of mean squared error that $F$ achieves on a given dataset, and let MMSE$(G)$ be the minimum value of mean squared error that $G$ achieves on a given dataset. Give an example of a dataset $(x_1, y_1), (x_2, y_2), …, (x_n, y_n)$ for which MMSE$(F)$ > MMSE$(G)$. 



# BEGIN SOLUTION
Example: If the datapoints follow a quadratic form
$y_i=x_i^2$ for all $i$, then the $G$ prediction rule will achieve a
zero error while $F>0$ since the data do not follow a linear form.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Let MMSE$(F)$ be the minimum value of mean squared error that $F$ achieves on a given dataset, and let MMSE$(G)$ be the minimum value of mean squared error that $G$ achieves on a given dataset. Give an example of a dataset $(x_1, y_1), (x_2, y_2), …, (x_n, y_n)$ for which MMSE$(F)$ = MMSE$(G)$. 


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


Reggie adds a new feature $x^{(2)}$, to his dataset and creates two new hypothesis functions, $J$ and $K$:
$$J(\vec x_i) = w_0 + w_1 x_i^{(1)} + w_2 x_i^{(2)}$$
$$K(\vec x_i) = \beta_0 + \beta_1 x_i^{(1)} + \beta_2 x_i^{(2)} + \beta_3 (2 x_i^{(1)} - x_i^{(2)})$$
Reggie argues that having more features is better, so MMSE($K$) < MMSE($J$). Is Reggie correct? Why or why not?

# BEGIN SOLUTION

$K(\vec x_i)$ can be rewritten as
$$K(\vec x_i) = \beta_0 + (\beta_1+2\beta_3) x_i^{(1)} +(\beta_2 - \beta_3)x_i^{(2)}$$
By setting $\tilde{\beta}_1=\beta_1+2\beta_3$ and
$\tilde{\beta_2}= \beta_2 - \beta_3$ then

$$K(\vec x_i) = K(\beta_0,\tilde{\beta}_1,\tilde{\beta}_2) = \beta_0 + \tilde{\beta_1} x_i^{(1)} +\tilde{\beta}_2 x_i^{(2)}$$

Thus $J$ and $K$ have the same normal equations and therefore the
same minimum MSE.

# END SOLUTION

# END SUBPROB

# END PROB