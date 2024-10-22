# BEGIN PROB

<i>Source: [Fall 2021 Final Exam](../fa21-final/index.html), Problem 5</i>

Suppose we have a dataset of $n$ houses that were recently sold in the San Diego area. For each house, we have its square footage and most recent sale price. The correlation between square footage and price is $r$.

# BEGIN SUBPROB

First, we minimize mean squared error to fit a linear prediction rule that uses square footage to predict price. The resulting prediction rule has an intercept of $w_0^*$ and slope of $w_1^*$. In other words,

$$\text{predicted price} = w_0^* + w_1^* \cdot \text{square footage}$$

We're now interested in minimizing mean squared error to fit a linear prediction rule **that uses price to predict square footage**. Suppose this new regression line has an intercept of $\beta_0^*$ and slope of $\beta_1^*$.

What is $\beta_1^*$? Give your answer in terms of one or more of $n$, $r$, $w_0^*$, and $w_1^*$. Show your work.

# BEGIN SOLN

$$\beta_1^* = \frac{r^2}{w_1^*}$$

Throughout this solution, let $x$ represent square footage and $y$ represent price.

We know that $w_1^* = r \frac{\sigma_y}{\sigma_x}$. But what about $\beta_1^*$?

When we take a rule that predicts price from square footage and transform it into a rule that predicts square footage from price, the roles of $x$ and $y$ have swapped; suddenly, square footage is no longer our independent variable, but our dependent variable, and vice versa for price. This means that the altered dataset we work with when using our new prediction rule has $\sigma_x$ standard deviation for its dependent variable (square footage), and $\sigma_y$ for its independent variable (price). So, we can write the formula for $\beta_1^*$ as follows: $$\beta_1^* = r \frac{\sigma_x}{\sigma_y}$$ 

In essence, swapping the independent and dependent variables of a dataset changes the slope of the regression line from $r \frac{\sigma_y}{\sigma_x}$ to $r \frac{\sigma_x}{\sigma_y}$.

From here, we can use a little algebra to get our $\beta_1^*$ in terms of one or more $n$, $r$, $w_0^*$, and $w_1^*$:

$$\begin{align*}
\beta_1^* &= r \frac{\sigma_x}{\sigma_y} \\
w_1^* \cdot \beta_1^* &= w_1^* \cdot r \frac{\sigma_x}{\sigma_y} \\
w_1^* \cdot \beta_1^* &= ( r \frac{\sigma_y}{\sigma_x}) \cdot r \frac{\sigma_x}{\sigma_y}
\end{align*}$$

The fractions $\frac{\sigma_y}{\sigma_x}$ and $\frac{\sigma_x}{\sigma_y}$ cancel out and we get:

$$\begin{align*}
w_1^* \cdot \beta_1^* &= r^2 \\
\beta_1^* &= \frac{r^2}{w_1^*}
\end{align*}$$

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

**For this part only**, assume that the following quantities hold:

- $n = 100$
- $r = 0.6$
- $w_0^* = 1000$
- $w_1^* = 250$
- The average square footage of homes in the dataset is 2000

Given this information, what is $\beta_0^*$? Give your answer as a constant, rounded to two decimal places. Show your work.

# BEGIN SOLN

$$\beta_0^* = 1278.56$$

We start with the formula for the intercept of the regression line. Note that $x$ and $y$ are opposite what they'd normally be since we're using price to predict square footage.

$$\beta_0^* = \bar{x} - \beta_1^* \bar{y}$$

We're told that the average square footage of homes in the dataset is 2000, so $\bar{x} = 2000$. We also know from part (a) that $\beta_1^* = \frac{r^2}{w_1^*}$, and from the information given in this part this is $\beta_1^* = \frac{r^2}{w_1^*} = \frac{0.6^2}{250}$.

Finally, we need the average price of all homes in the dataset, $\bar{y}$. We aren't given this information directly, but we can use the fact that $(\bar{x}, \bar{y})$ are on the regression line that uses square footage to predict price to find $\bar{y}$. Specifically, we have that $\bar{y} = w_0^* + w_1^* \bar{x}$; we know that $w_0^* = 1000$, $\bar{x} = 2000$, and $w_1^* = 250$, so $\bar{y} = 1000 + 2000 \cdot 250 = 501000$.

Putting these pieces together, we have

$$
\begin{align*}
\beta_0^* &= \bar{x} - \beta_1^* \bar{y} \\
&= 2000 - \frac{0.6^2}{250} \cdot 501000 \\
&= 2000 - 0.6^2 \cdot 2004 \\
&= 1278.56
\end{align*}
$$

# END SOLN

# END SUBPROB

# END PROB