# BEGIN PROB

Suppose we want to fit a hypothesis function of the form: $$H(x) = w_0 + w_1 x^{(1)} + w_2 x^{(2)} + w_3 (x^{(1)})^2 + w_4 (x^{(1)} x^{(2)})^2$$
\vspace{-0.3cm}
Our dataset looks like this: 

| $x^{(1)}$ | $x^{(2)}$ | $y$ |
|-----------|------------|-----|
| 1         | 6          | 7   |
| -3        | 8          | 2   |
| 4         | 1          | 9   |
| -2        | 7          | 5   |
| 0         | 4          | 6   |

# BEGIN SUBPROB

Suppose we found $w_2^* = 15.6$ using multiple linear regression. Now, suppose we rescaled our data so feature vector $\vec{x^{(2)}}$ became $\left[60,\  80,\  10,\  70,\  40\right]^T$, and performed multiple linear regression in the same setting. What would the new value of $w_2^*$ (the weight on feature $x^{(2)}$ in $H(x)$) be? You do not need to simplify your answer.

# BEGIN SOLUTION

$w_2^* = 1.56$

# END SOLUTION
    


# END SUBPROB


# BEGIN SUBPROB

Suppose we found $w_4^* = 72$ using multiple linear regression. Now, suppose we rescaled our data so feature vector $\vec{x^{(1)}}$ became $\left[ \frac{1}{2},\  -\frac{3}{2},\  2,\  -1,\  0 \right]$ and $\vec{x^{(2)}}$ now became $\left[36, \ 48, \   6, \ 42, \ 24\right]^T$, and performed multiple linear regression in the same setting. What would the new value of $w_4^*$ (the weight on feature $(x^{(1)} x^{(2)})^2$ in $H(x)$) be? You do not need to simplify your answer.

# BEGIN SOLUTION

$w_4^* = \frac{72}{(\frac{6}{2})^2}$

# END SOLUTION



# END SUBPROB

# BEGIN SUBPROB

Suppose we found $w_0^* = 4.47$ using multiple linear regression. Now, suppose our observation vector $\vec{y}$ now became $\left[12, \ 7, \ 14, \ 10, \ 11\right]^T$, and performed multiple linear regression in the same setting. What would the new value of $w_0^*$ be? You do not need to simplify your answer.

# BEGIN SOLUTION

$w_0^* = 9.47$

# END SOLUTION



# END SUBPROB

# BEGIN SUBPROB

Suppose we found $w_1^* = 0.428$ using multiple linear regression. Now, suppose our observation vector $\vec{y}$ now became $\left[12, \ 7, \ 14, \ 10, \ 11\right]^T$, and performed multiple linear regression in the same setting. What would the new value of $w_1^*$ (the weight on feature $x^{(1)}$ in $H(x)$) be? You do not need to simplify your answer.

# BEGIN SOLUTION

$w_1^* = 0.428$

# END SOLUTION



# END SUBPROB
    

# END PROB