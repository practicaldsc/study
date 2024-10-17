# BEGIN PROB

Suppose we have already fit a multiple regression hypothesis function of the form: $$H(x) = w_0 + w_1 x^{(1)} + w_2 x^{(2)}$$

Now, suppose we add the feature $(x^{(1)} + x^{(2)})$ when performing multiple regression. Below, answer ``Yes/No" to the following questions and rigorously justify why certain behavior will or will not occur. Your answer must mention linear algebra concepts such as rank and linear independence in relation to the design matrix, weight vector $\vec{w^*}$, and hypothesis function $H(x)$.

# BEGIN SUBPROB

Which of the following are true about the new design matrix $X_\text{new}$ with our added feature  $(x^{(1)} + x^{(2)})$?

[ ] The columns of $X_\text{new}$ are linearly independent.
[ ] The columns of $X_\text{new}$ are linearly dependent.
[ ] $\vec{y}$ is orthogonal to all the columns of $X_\text{new}$.
[ ] $\vec{y}$ is orthogonal to all the columns of the original design matrix $X$.
[ ] The columns of $X_\text{new}$ have the same span as the original design matrix $X$.
[ ] $X_\text{new}^TX_\text{new}$ is a full-rank matrix.
[ ] $X_\text{new}^TX_\text{new}$ is not a full-rank matrix.

# BEGIN SOLUTION

The columns of $X_\text{new}$ are linearly dependent.
The columns of $X_\text{new}$ have the same span as the original design matrix $X$.
$X_\text{new}^TX_\text{new}$ is not a full-rank matrix.


# END SOLUTION
    


# END SUBPROB


# BEGIN SUBPROB

Is there more than one optimal weight vector $\vec{w^*}$ that produces the lowest mean squared error hypothesis function $H(x) = w_0^* + w_1^* x^{(1)} + w_2^* x^{(2)} + w_4^*(x^{(1)} + x^{(2)})$? 

( ) Yes
( ) No

Explain your answer.

# BEGIN SOLUTION

Yes

TODO

# END SOLUTION



# END SUBPROB

# BEGIN SUBPROB

Does the best possible mean squared error of the new hypothesis function differ from that of the previous hypothesis function?

( ) Yes
( ) No

Explain your answer.

# BEGIN SOLUTION

No

TODO

# END SOLUTION

# END SUBPROB

# END PROB