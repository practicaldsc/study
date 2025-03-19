# BEGIN PROB

Suppose we have one qualitative variable that that we convert to numerical values using one- hot encoding. We’ve shown the first four rows of the resulting design matrix below:

<center><img src='../assets/images/disc10/matrix.png' width=400></center>

# BEGIN SUBPROB

Say we train a linear model $m_1$ on these data. Then, we replace all of the 1 values in column **a** with 3’s and all of the 1 values in column **b** with 2’s and train a new linear model $m_2$. Neither $m_1$ nor $m_2$ have an intercept term. On the training data, the average squared loss for $m_1$ will be ________ that of $m_2$.

( ) greater than
( ) less than
( ) equal to
( ) impossible to tell

# BEGIN SOLUTION

**Answers:**

The answer is equal to. 

Because we can simply adjust the weights in the opposite way that we rescale the one-hot columns, any model obtainable with the original encoding can also be obtained with the rescaled encoding. This guarantees that the training loss remains unchanged.

When one-hot encoding is used, each category is represented by a column that typically contains only 0s and 1s. Rescaling these columns means multiplying the 1s by a constant (for example, turning 1 into 2 or 3). However, if we also adjust the corresponding weights in the model by dividing by that same constant, the product of the rescaled column value and its weight remains the same. Since the model’s predictions are based on these products, the predictions will not change, and as a result, the average squared loss on the training data will also remain unchanged.

For example, let us say we have categorical variable "Color" with three levels: Red, Green, and Blue. We one-hot encode this variable into three columns. For an observation:
- If the color is Red, the encoded values might be: Red = 1, Green = 0, Blue = 0.

Now, suppose we decide to multiply the column for Red by 2. The new value for a Red observation becomes 2 instead of 1. To keep the prediction the same, we can simply use half the weight for this column in the model. This inverse adjustment ensures that the final product (column value multiplied by weight) remains unchanged. Thus, the model's prediction and the average squared loss on the training data stay the same.


# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

To account for the intercept term, we add a column of all ones to our design matrix from part a. That is, the resulting design matrix has four columns: **a** with 3’s instead of 1’s, **b** with 2’s instead of 1’s, **c**, and a column of all ones. What is the rank of the new design matrix with these four columns?

( ) 1
( ) 2
( ) 3
( ) 4

# BEGIN SOLUTION

**Answers:**

The answer is 3.

Note that the column **c** = intercept column −$\frac{1}{3}$**a** + $\frac{1}{2}$**b**. Hence, there is a linear dependence relationship, meaning that one of the columns is redundant and that the rank of the new design matrix is 3.

# END SOLUTION

# END SUBPROB

# END PROB