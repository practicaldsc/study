# BEGIN PROB

Consider the least squares regression model, $\hat{Y} = X \theta$. Assume that $X$ and $Y$ refer to the design matrix and true response vector for our training data. 

Let $\hat{\gamma}$ be the parameter vector that minimizes mean squared error without regularization. Specifically:

$\hat{\gamma} = \arg\underset{\gamma}{\min} \frac{1}{n} \| Y - X \gamma \|^2_2$

Let $\hat{\beta}$ be the parameter vector that minimizes mean squared error with $L_2$ regularization, using a non-negative regularization hyperparameter $\gamma$ (i.e. ridge regression). Specifically:

$\hat{\beta} = \arg\underset{\beta}{\min} \frac{1}{n} \| Y - X \beta \|^2_2 + \lambda \sum_{j=1}^{p} \beta_j^2$

For each of the following problems, fill in the blank.

# BEGIN SUBPROB

If we set $\gamma$ = 0, then $\Vert \hat{\gamma} \Vert^2_2$ is ________ $\Vert \hat{\beta} \Vert^2_2$

( ) less than 
( ) equal to
( ) greater than 
( ) impossible to tell

# BEGIN SOLUTION

**Answers:**

equal to 

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

For each of the remaining parts, you can assume that $\gamma$ is set such that the predicted response vectors for our two models ($\hat{Y} = X \hat{\gamma}$ and $\hat{Y} = X \hat{\beta}$) is different.

The **training** RMSE of the model $\hat{Y} = X \hat{\gamma}$ is ________ than the model $\hat{Y} = X \hat{\beta}$.

( ) less than 
( ) equal to
( ) greater than 
( ) impossible to tell

# BEGIN SOLUTION

**Answers:**

less than

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Now, assume we’ve fit both models using our training data, and evaluate both models on some unseen testing data.

The **test** RMSE of the model $\hat{Y} = X \hat{\gamma}$ is ________ than the model $\hat{Y} = X \hat{\beta}$.

( ) less than 
( ) equal to
( ) greater than 
( ) impossible to tell

# BEGIN SOLUTION

**Answers:**

impossible to tell

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Assume that our design matrix X contains a column of all ones. The sum of the
residuals of our model $\hat{Y} = X \hat{\beta}$ ________.

( ) equal to 0
( ) not necessarily equal to 0 

# BEGIN SOLUTION

**Answers:**

not necessarily equal to 0 

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

As we increase $\gamma$, the bias of the model $\hat{Y} = X \hat{\beta}$ tends to ________.

( ) increase
( ) stay the same
( ) decrease

# BEGIN SOLUTION

**Answers:**

increase

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

As we increase $\gamma$, the model variance of the model $\hat{Y} = X \hat{\beta}$ tends to ________.

( ) increase
( ) stay the same
( ) decrease

# BEGIN SOLUTION

**Answers:**

decrease

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

As we increase $\gamma$, the observation variance of the model $\hat{Y} = X \hat{\beta}$ tends to ________.

( ) increase
( ) stay the same
( ) decrease

# BEGIN SOLUTION

**Answers:**

stay the same 

# END SOLUTION

# END SUBPROB

# END PROB
