# BEGIN PROB

Now we solve the normal equations and find the solution to be
\begin{aligned}
            \vec{w}^* &= \begin{bmatrix} w_0^* \\ w_1^* \\ w_2^* \end{bmatrix}
\end{aligned}
Define a new vector:
\begin{aligned}
            \vec{w}^{\circ} &= \begin{bmatrix} w_0^{\circ} \\ w_1^{\circ} \\ w_2^{\circ} \end{bmatrix} = \begin{bmatrix} w_0^*+3 \\ w_1^*-4 \\ w_2^*-6 \end{bmatrix}
            
\end{aligned}

and consider the two prediction rules

\begin{aligned}
        H^*(\text{cells, lines, max iterations, variables}) &=  w_0^* + w_1^* \cdot \text{cells} \cdot \text{lines} + w_2^* \cdot (\text{max iterations})^{\text{variables} - 10}\\
        H^{\circ}(\text{cells, lines, max iterations, variables}) &=  w_0^{\circ} + w_1^{\circ} \cdot \text{cells} \cdot \text{lines} + w_2^{\circ} \cdot (\text{max iterations})^{\text{variables} - 10}
        
\end{aligned}

Let $\text{MSE}$ represent the mean squared error of a prediction
rule, and let $\text{MAE}$ represent the mean absolute error of a prediction
rule. Select the symbol that should go in each blank.

# BEGIN SUBPROB

$\text{MSE}(H^*)$ ___ $\text{MSE}(H^{\circ})$

( ) $\leq$
( ) $\geq$
( ) $=$

# BEGIN SOLUTION

$\leq$


It is given that $\vec{w}^*$ is the optimal parameter vector. Here's one thing we know about the optimal parameter vector $\vec{w}^*$: it is optimal, which means that any *changes* made to it will, at best, keep our predictions of the exact same quality, and, at worst, reduce the quality of our predictions and **increase our error**. And since $\vec{w} \degree$ is just the optimal parameter vector but with some small *changes* to the weights, it stands that $\vec{w} \degree$ is liable to create equal or greater error!

In other words, $\vec{w} \degree$ is a slightly worse version of $\vec{w}^*$, meaning that $H \degree(x)$ is a slightly worse version of $H^*(x)$. So, $H \degree(x)$ will have equal or higher error than $H^*(x)$.

Hence: $\text{MSE}(H^*) \leq \text{MSE}(H^{\circ})$

<!-- Recall the equation for mean squared error: $\text{MSE}(H(x_i)) = \frac{1}{n}\sum_{i=1}^n(y_i-H(x_i))^2$. We can figure out which is bigger by subtracting  $\text{MSE}(H^{\circ})$ from $\text{MSE}(H^*)$. The difference between the squared differences is:
$$(y_i-H^*(x_i))^2-(y_i-H^{\circ}(x_i))^2$$Notice there is a squared element, which means that the differences of $w^*_0 - w^{\circ}_0$, $w^*_1 - w^{\circ}_1$, and $w^*_2 - w^{\circ}_2$ will appear as squared terms, which are always positive! This means adding these squared differences to $H^*$ will make it at least as large as the squared difference for $H^{\circ}$. -->

# END SOLUTION

# END SUBPROB

<!-- Commented out this subproblem for now, solution is wack. To uncomment, highlight from "BEGIN SUBPROB" to "..other way around" -->

<!-- # BEGIN SUBPROB

$(\text{MAE}(H^{\circ}))^2$ ___ $\text{MSE}(H^{\circ})$

( ) $\leq$
( ) $\geq$
( ) $=$

# BEGIN SOLUTION

$\geq$

The formula for mean absolute error is: $\text{MAE}(H(x_i)) = \frac{1}{n}\sum_{i=1}^n|y_i-H(x_i)|$ \
The formula for mean squared error is: $\text{MSE}(H(x_i)) = \frac{1}{n}\sum_{i=1}^n(y_i-H(x_i))^2$

We can substitute these two formulas into our comparison and recieve:
$(\frac{1}{n}\sum_{i=1}^n|y_i-H(x_i)|)^2$ ___ $\frac{1}{n}\sum_{i=1}^n(y_i-H(x_i))^2$

It is now clear that our comparison boils down to this question: "Which is greater? If I take the absolute errors, square them, and then sum them up... *or* if I take the absolute errors, sum them up, and then square them?"

Rules from algebra tell us that summing the absolute errors up *before* squaring them will always produce a greater result than the other way around (this holds when all of our values are positive, which they are in this case thanks to dealing with *absolute* errors)! It's a good exercise to think about why this is the case, but a basic example is if I have two positive values $a$ and $b$: $(a + b)^2 = a^2 + b^2 + 2ab \geq a^2 + b^2$, since $2ab$ is a non-negative term.

Bringing this altogether, we should conclude that $\text{MAE}(H(x_i))^2  \geq \text{MSE}(H(x_i))$, since summing up the errors before squaring them is greater than the other way around!

Old Solution Below:

This equation looks very similar to the mean squared error! We can actually take the square root of each sides of this equation to learn more about which side is larger:
$$
\begin{align*}
(\text{MAE}(H^\circ))^2 &\_\_\_ \text{MSE}(H^\circ) \\
\sqrt{(\text{MAE}(H^\circ))^2} &\_\_\_ \sqrt{\text{MSE}(H^\circ)} \\
\text{MAE}(H^\circ) &\_\_\_ \sqrt{\text{MSE}(H^\circ)}
\end{align*}
$$

The square root of $\text{MSE}$ is equal to $\text{MAE}$! These two elements are basically the same because squaring a value will lead to non-negatives and then it will be square rooted to match the absolute value from $\text{MAE}$. However the $\text{MSE}$ being square rooted also allows for it to be smaller than the $\text{MSE}$ making the correct symbol $\geq$.

# END SOLUTION

# END SUBPROB -->

# END PROB