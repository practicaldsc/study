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

The answer is `equal to`.

Note that we can just re-scale our weights accordingly. Any model we can get with $m_1$ we can also get with $m_2$ (and vice versa).

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

The answer is `3`.

Note that the column **c** = intercept column −$\frac{1}{3}$**a** + $\frac{1}{2}$**b**. Hence, there is a linear dependence relationship, meaning that one of the columns is redundant and that the rank of the new design matrix is 3.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose we divide our sampling frame into three clusters of people, numbered 1, 2, and 3. After we survey people, along with our survey results, we save their cluster number as a new feature in our design matrix. Before training a model, what should we do with the cluster column? (Note: This part is independent of parts a and b.)

( ) Leave as is
( ) One-hot encode it
( ) Normalize it
( ) Use bag of words

# BEGIN SOLUTION

**Answers:**

The cluster number is a categorical variable, so it should be one-hot encoded.

# END SOLUTION

# END SUBPROB

# END PROB