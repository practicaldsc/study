# BEGIN PROB

Billy's aunt owns a jewellery store, and gives him data on $5000$ of the diamonds in her store. For each diamond, we have:

- **carat**: the weight of the diamond, in carats
- **length**: the length of the diamond, in centimeters
- **width**: the width of the diamond, in centimeters
- **price**: the value of the diamond, in dollars

The first 5 rows of the 5000-row dataset are shown below:

<div>
| carat &emsp;&emsp; | length &emsp;&emsp; | width &emsp;&emsp; | price &emsp;&emsp; |
|-------|--------|-------|-------|
| 0.40  | 4.81   | 4.76  | 1323  |
| 1.04  | 6.58   | 6.53  | 5102  |
| 0.40  | 4.74   | 4.76  | 696   |
| 0.40  | 4.67   | 4.65  | 798   |
| 0.50  | 4.90   | 4.95  | 987   |
</div>

<br>
Billy has enlisted our help in predicting the price of a diamond given various other features.

# BEGIN SUBPROB

Suppose we want to fit a linear prediction rule that uses two features, carat and length, to predict price. Specifically, our prediction rule will be of the form

$$\text{predicted price} = w_0 + w_1 \cdot \text{carat} + w_2 \cdot \text{length}$$

<br>

We will use least squares to find $\vec{w}^* = \begin{bmatrix} w_0^* \\ w_1^* \\ w_2^* \end{bmatrix}$.

Write out the first 5 rows of the design matrix, $X$. Your matrix should not have any variables in it.

# BEGIN SOLN
**Answer**:
$$X = \begin{bmatrix} 1 & 0.40 & 4.81 \\ 1 & 1.04 & 6.58 \\ 1 & 0.40 & 4.74 \\ 1 & 0.40 & 4.67 \\ 1 & 0.50 & 4.90 \end{bmatrix}$$

In this design matrix X - the first column consists of all 1s (for the intercept term $w_0$), the second column contains the carat values (for the coefficient $w_1$), and the third column contains the length values (for the coefficient $w_2$).

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Suppose the optimal parameter vector $\vec{w}^*$ is given by

$$\vec{w}^* = \begin{bmatrix} 2000 \\ 10000 \\ -1000 \end{bmatrix}$$

What is the predicted price of a diamond with 0.65 carats and a length of 4 centimeters? Show your work.

# BEGIN SOLN
**Answer**: The predicted price is $4500$ dollars.

From our optimal parameter vector we know that $w_0^* = 2000$, $w_1^* = 10000$, and $w_2^* = -1000$. We can compute the predicted price using our linear model:

$$\text{predicted price} = \begin{bmatrix} 1 & 0.65 & 4 \end{bmatrix} \cdot \begin{bmatrix} 2000 \\ 10000 \\ -1000 \end{bmatrix}$$

Computing:
$$2000 + 10000 \cdot 0.65 - 1000 \cdot 4 = 2000 + 6500 - 4000 = 4500$$


# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Suppose $\vec{e} = \begin{bmatrix} e_1 \\ e_2 \\ ... \\ e_n \end{bmatrix}$ is the error/residual vector, defined as

$$\vec{e} = \vec{y} - X \vec{w}^*$$

where $\vec{y}$ is the observation vector containing the prices for each diamond.

For each of the following quantities, state whether they are guaranteed to be equal to 0 the scalar, $\vec{0}$ the vector of all 0s, or neither. No justification is necessary.

- $\sum_{i = 1}^n e_i$
- $|| \vec{y} - X \vec{w}^* ||^2$
- $X^TX \vec{w}^*$
- $2X^TX \vec{w}^* - 2X^T\vec{y}$

# BEGIN SOLN
**Answer**:

- $\sum_{i = 1}^n e_i$: **Yes**, this is guaranteed to be 0. This was discussed in Homework 7; it is a consequence of the fact that $X^T (y - X \vec{w}^*) = 0$ and that we have an intercept term in our prediction rule (and hence a column of all 1s in our design matrix, $X$).
- $|| \vec{y} - X \vec{w}^* ||^2$: **No**, this is not guaranteed to be 0. This is the mean squared error of our prediction rule, multiplied by $n$. $\vec{w}^*$ is found by minimizing mean squared error, but the minimum value of mean squared error isn't necessarily 0 --- in fact, this quantity is only 0 if we can write $\vec{y}$ exactly as $X \vec{w}^*$ with no prediction errors.
- $X^TX \vec{w}^*$: **No**, this is not guaranteed to be 0, either.
- $2X^TX \vec{w}^* - 2X^T\vec{y}$: **Yes**, this is guaranteed to be 0. Recall, the optimal parameter vector $\vec{w}^*$ satisfies the normal equations $X^TX\vec{w}^* = X^T \vec{y}$. Subtracting $X^T \vec{y}$ from both sides of this equation and multiplying both sides by 2 yields the desired result.
# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Suppose we introduce two more features:

- width alone, and
- area, which is defined as length times width

Suppose we also decide to remove the intercept term of our prediction rule. With all of these changes, our prediction rule is now

$$\text{predicted price} = w_1 \cdot \text{carat} + w_2 \cdot \text{length} + w_3 \cdot \text{width} + w_4 \cdot (\text{length} \cdot \text{width}) $$

- Write out just the first 2 rows of the design matrix $X$ for this new prediction rule. You do **not** need to simplify the numbers in your matrix, it is fine if they involve the multiplication symbol.
- Is the optimal coefficient for carat, $w_1^*$, for this new prediction rule guaranteed to be equal to 10000, the optimal coefficient for carat in our original prediction rule? No justification is necessary.

# BEGIN SOLN
**Answer**:

- $X = \begin{bmatrix} 0.40 & 4.81 & 4.76 & 4.81 \cdot 4.76 \\ 1.04 & 6.58 & 6.53 & 6.58 \cdot 6.53 \end{bmatrix}$
- No, it's not guaranteed that the $\vec{w}_1^*$ for this new prediction rule is equal to the $\vec{w}_1^*$ for the original prediction rule. The value of $\vec{w}_1^*$ in the new prediction rule will be influenced by the fact that there's no longer an intercept term and that there are two new features (width and area) that weren't previously there.

# END SOLN

# END SUBPROB

# END PROB