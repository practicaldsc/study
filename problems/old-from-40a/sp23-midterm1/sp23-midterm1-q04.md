# BEGIN PROB

<i>Source: [Spring 2023 Midterm 1](../sp23-midterm1/index.html), Problem 4</i>

Suppose we are given a dataset of points $\{(x_1, y_1), (x_2, y_2), \dots, (x_n, y_n)\}$ and for some reason, we want to make predictions using a prediction rule of the form $$H(x) = 17 + w_1x.$$

# BEGIN SUBPROB

Write down an expression for the mean squared error of a
prediction rule of this form, as a function of the parameter $w_1$.

# BEGIN SOLUTION

$MSE(w_1) = \dfrac1n \displaystyle\sum_{i=1}^n (y_i - (17 + w_1x_i))^2$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Minimize the function $MSE(w_1)$ to find the parameter $w_1^*$ which defines the optimal prediction rule $H^*(x) = 17 + w_1^*x$. Show all your work and explain your steps.

Fill in your final answer below: 

# BEGIN SOLUTION

$$w_1^* = \dfrac{\displaystyle\sum_{i=1}^n x_i(y_i - 17)}{\displaystyle\sum_{i=1}^n x_i^2}$$


To minimize a function of one variable, we need to take the derivative, set it equal to zero, and solve. $$\begin{aligned} MSE(w_1) &= \dfrac1n \displaystyle\sum_{i=1}^n (y_i - 17 - w_1x_i)^2 \\ MSE'(w_1) &= \dfrac1n \displaystyle\sum_{i=1}^n -2x_i(y_i - 17 - w_1x_i)) \qquad \text{using the chain rule} \\ 0 &= \dfrac1n \displaystyle\sum_{i=1}^n -2x_i(y_i - 17) + \dfrac1n \displaystyle\sum_{i=1}^n 2x_i^2w_1 \qquad \text{splitting up the sum} \\ 0 &=  \displaystyle\sum_{i=1}^n -x_i(y_i - 17) +  \displaystyle\sum_{i=1}^n x_i^2w_1 \qquad \text{multiplying through by } \frac{n}{2} \\ w_1 \displaystyle\sum_{i=1}^n x_i^2 &=  \displaystyle\sum_{i=1}^n x_i(y_i - 17)   \qquad \text{rearranging terms and pulling out } w_1 \\ w_1 & = \dfrac{\displaystyle\sum_{i=1}^n x_i(y_i - 17)}{\displaystyle\sum_{i=1}^n x_i^2} \end{aligned}$$


# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

True or False: For an arbitrary dataset, the prediction rule $H^*(x) = 17 + w_1^*x$ goes through the point $(\bar x, \bar y)$.

( ) True 
( ) False

# BEGIN SOLUTION

False.

When we fit a prediction rule of the form $H(x) = w_0+w_1x$ using simple linear regression, the formula for the intercept $w_0$ is designed to make sure the regression line passes through the point $(\bar x, \bar y)$. Here, we don't have the freedom to control our intercept, as it's forced to be $17$. This means we can't guarantee that the prediction rule $H^*(x) = 17 + w_1^*x$ goes through the point $(\bar x, \bar y)$.

A simple example shows that this is the case. Consider the dataset $(-2, 0)$ and $(2, 0)$. The point $(\bar x, \bar y)$ is the origin, but the prediction rule $H^*(x)$ does not pass through the origin because it has an intercept of $17$.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

True or False: For an arbitrary dataset, the mean squared error associated with $H^*(x)$ is greater than or equal to the mean squared error associated with the regression line.

( ) True 
( ) False

# BEGIN SOLUTION

True.

The regression line is the prediction rule of the form $H(x) = w_0+w_1x$ with the smallest mean squared error (MSE). $H^*(x)$ is one example of a prediction rule of that form so unless it happens to be the regression line itself, the regression line will have lower MSE because it was designed to have the lowest possible MSE. This means the MSE associated with $H^*(x)$ is greater than or equal to the MSE associated with the regression line.

# END SOLUTION

# END SUBPROB

# END PROB