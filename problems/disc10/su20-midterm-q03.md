# BEGIN PROB

Consider the least squares regression model, $\vec{h} = X \vec{w}$. Assume that $X$ and $\vec{h}$ refer to the design matrix and hypothesis vector for our training data, and $\vec y$ is the true observation vector.

Let $\vec{w}_\text{OLS}^*$ be the parameter vector that minimizes mean squared error without regularization. Specifically:

$\vec{w}_\text{OLS}^*$ = $\arg\underset{\vec{w}}{\min} \frac{1}{n} \| \vec{y} - X \vec{w} \|^2_2$

Let $\vec{w}_\text{ridge}^*$ be the parameter vector that minimizes mean squared error with $L_2$ regularization, using a non-negative regularization hyperparameter $\lambda$ (i.e. ridge regression). Specifically:

$\vec{w}_\text{ridge}^*$ = $\arg\underset{\vec{w}}{\min} \frac{1}{n} \| \vec y - X \vec{w} \|^2_2 + \lambda \sum_{j=1}^{p} w_j^2$

For each of the following problems, fill in the blank.

# BEGIN SUBPROB

If we set $\lambda$ = 0, then $\Vert \vec{w}_\text{OLS}^* \Vert^2_2$ is **\_\_\_\_** $\Vert \vec{w}_\text{ridge}^* \Vert^2_2$

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

For each of the remaining parts, you can assume that $\lambda$ is set such that the predicted response vectors for our two models ($\vec{h} = X \vec{w}_\text{OLS}^*$ and $\vec{h} = X \vec{w}_\text{ridge}^*$) is different.

The **training** MSE of the model $\vec{h} = X \vec{w}_\text{OLS}^*$ is **\_\_\_\_** than the model $\vec{h} = X \vec{w}_\text{ridge}^*$.

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

The **test** MSE of the model $\vec{h} = X \vec{w}_\text{OLS}^*$ is **\_\_\_\_** than the model $\vec{h} = X \vec{w}_\text{ridge}^*$.

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

Assume that our design matrix $X$ contains a column of all ones. The sum of the
residuals of our model $\vec{h} = X \vec{w}_\text{ridge}^*$ **\_\_\_\_**.

( ) equal to 0
( ) not necessarily equal to 0

# BEGIN SOLUTION

**Answers:**

not necessarily equal to 0

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

As we increase $\lambda$, the bias of the model $\vec{h} = X \vec{w}_\text{ridge}^*$ tends to **\_\_\_\_**.

( ) increase
( ) stay the same
( ) decrease

# BEGIN SOLUTION

**Answers:**

increase

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

As we increase $\lambda$, the model variance of the model $\vec{h} = X \vec{w}_\text{ridge}^*$ tends to **\_\_\_\_**.

( ) increase
( ) stay the same
( ) decrease

# BEGIN SOLUTION

**Answers:**

decrease

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

As we increase $\lambda$, the observation variance of the model $\vec{h} = X \vec{w}_\text{ridge}^*$ tends to **\_\_\_\_**.

( ) increase
( ) stay the same
( ) decrease

# BEGIN SOLUTION

**Answers:**

stay the same

# END SOLUTION

# END SUBPROB

# END PROB
