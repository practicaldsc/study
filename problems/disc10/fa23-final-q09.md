# BEGIN PROB 

Every week, Pranavi goes to her local grocery store and buys a varying amount of vegetable but always buys exactly one pound of meat (either beef, fish, or chicken). We use a linear regression model to predict her total grocery bill. We've collected a dataset containing the pounds of vegetables bought, the type of meat bought, and the total bill. Below we display the first few rows of the dataset and two plots generated using the entire training set.

<center><img src='../../assets/images/disc10/dsc80_final_q9.png' width=65%></center>

# BEGIN SUBPROB

Determine how each change below affects model bias and variance compared to the model $H(x)$ described at the top of this page. **For each change (i., ii., iii., iv.), choose all of the following that apply: increase bias, decrease bias, increase variance, decrease variance.**

i. Add degree $3$ polynomial features.
ii. Add a feature of numbers chosen at random between $0$ and $1$.
iii. Collect $100$ more points for the training set.
iv. Don't use the `'veg'` feature.

# BEGIN SOLN

- i. **Answer: Decrease bias, increase variance**. Note that adding degree 3 polynomial features will increase the complexity of our model. Increasing model complexity decreases model bias, but increases model variance (because the fitted model will vary more from training set to training set than it would without the degree 3 feature).
- ii. **Answer: Increase variance**. We're adding a new feature that will contribute nothing of quality to our model's predictions, other than make them vary more from training set to training set.
- iii. **Answer: Decrease variance**. Think of our training set as being a sample drawn from some population. The larger our training sets are, the less our model will vary from training set to training set, hence, reducing model variance.
- iv. **Answer: Increase bias, decrease variance**. Removing the $\text{veg}$ feature would reduce the complexity of our model, which would increase model bias but decrease model complexity.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB
Suppose we predict `'total'` from `'veg'` using $8$ models with different degree polynomial features (degrees $0$ through $7$). Which of the following plots display the training and validation errors of these models? Assume that we plot the degree of the polynomial features on the x-axis, mean squared error loss on the y-axis, and the plots share y-axes limits.

<center><img src='../../assets/images/disc10/dsc80_final_plots.png' width=65%></center>

Training Error:

( ) A
( ) B
( ) C
( ) D

Validation Error:

( ) A
( ) B
( ) C
( ) D

# BEGIN SOLN
**Answer**: Training error: C; Validation Error: B

**Training Error**: As we increase the complexity of our model, it will gain the ability to memorize the patterns in our training set to a greater degree, meaning that its performance will get better and better (here, meaning that its MSE will get lower and lower).

**Validation Error**: As we increase the complexity of our model, there will be a point at which it becomes "too complex" and overfits to insignificant patterns in the training set. The second graph from the start of Problem 9 tells us that the relationship between `'total'` and `'veg'` is roughly quadratic, meaning it's best modeled using degree $2$ polynomial features. Using a degree greater than $2$ will lead to overfitting and, therefore, worse validation set performance. Plot B shows MSE decrease until $d = 2$ and increase afterwards, which matches the previous explanation.

# END SOLN
# END SUBPROB

# END PROB