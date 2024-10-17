# BEGIN PROB

Consider a dataset of $n$ values, $y_1, y_2, \dots, y_n$, all of which are non-negative. We are interested in fitting a constant model, $H(x) = h$, to the data using the ``Jack" loss function, defined as:

$L_{\text{Jack}}(y_i, h) =
\begin{cases} 
\alpha \cdot (y_i - h)^2 & \text{if } y_i \geq h, \\
\beta \cdot |y_i - h|^3 & \text{if } y_i < h,
\end{cases}$

where $\alpha$ and $\beta$ are positive constants that weight the squared and cubic loss components differently depending on whether the prediction $h$ underestimates or overestimates the true value $y_i$.

# BEGIN SUBPROB

Find $\frac{d L_\text{Jack}}{d h}$, the derivative of the Jack loss function with respect to $h$. Show your work, and put a $\boxed{\text{box}}$ around your final answer.

\textit{Hint: The derivative of a piecewise function is also a piecewise function.}

# BEGIN SOLUTION

$\frac{L_{\text{Jack}}}{\partial h} =
\begin{cases} 
-2 \alpha(y_i = h) & \text{if } y_i \geq h, \\
3 \beta |h - y_i|^2 & \text{if } y_i < h,
\end{cases}$

Looking at the loss function (displayed again for your convenience), we can start by taking the derivative of the first case, when $y_i \geq h$:

$$L_{\text{Jack}}(y_i, h) =
\begin{cases} 
\alpha \cdot (y_i - h)^2 & \text{if } y_i \geq h, \\
\beta \cdot |y_i - h|^3 & \text{if } y_i < h,
\end{cases}$$

To find the derivative of the first case we will use chain rule. Chain rule states $F'(x) = f'(g(x)) \times g'(x)$. We start with $\frac{\partial}{\partial h} \alpha(y_i - h)^2$ and treat $f(x) = x^2$ and $g(x) = (y_i - h)$. We can easily find $f'(x) = 2$ and $g'(x) = -1$. When combining all of these parts we get

$$\frac{\partial}{\partial h} \alpha(y_i - h)^2 \rightarrow -2 \alpha(y_i = h)$$

We can now look at the second case, when $y_i < h$. Once again we will use the chain rule. We start with $\frac{\partial}{\partial h} \beta \cdot |y_i - h|^3$ and treat $f(x) = x^3$ and $g(x) = |y_i - h|$. We can easily find $f'(x) = 3$, but $g'(x)$ is a bit trickier.

This requires you to know when $h = y_i$ the line is undefined. This means we have a piecewise function.

$$g'(x) = \begin{cases} 
1 & \text{if } y_i > h, \\
\text{undefined} & \text{if } y_i = h\\
-1 & \text{if } y_i < h,
\end{cases}$$

Since we only care about when $y_i > h$ we can replace $g'(x)$ with $1$! This means we have

$$\frac{\partial}{\partial h} \beta \cdot |y_i - h|^3 \rightarrow 3 \beta |h - y_i|^2$$

$$\boxed{\frac{L_{\text{Jack}}}{\partial h} =
\begin{cases} 
-2 \alpha(y_i = h) & \text{if } y_i \geq h, \\
3 \beta |h - y_i|^2 & \text{if } y_i < h,
\end{cases}}$$

# END SOLUTION
    


# END SUBPROB


# BEGIN SUBPROB

Prove that for the constant prediction $h^*$ minimizing empirical risk for the Jack loss function, the following quantities sum to 0:

1) the sum of the derivatives of the losses for the overestimated values (when $h^* > y_i$), and
2) the sum of the derivatives of the losses for the underestimated values (when $h^* \leq y_i$).

_Hint: You do not need to solve for the optimal value of $h^*$. Instead, walk through the general process of minimizing a risk function, and think about the equations you come across._

# BEGIN SOLUTION

Once again, recall Jack loss:

$$L_{\text{Jack}}(y_i, h) =
\begin{cases} 
\alpha \cdot (y_i - h)^2 & \text{if } y_i \geq h, \\
\beta \cdot |y_i - h|^3 & \text{if } y_i < h,
\end{cases}$$

We can rewrite this to say:

$$L_{\text{Jack}}(y_i, h) =
\alpha \cdot (y_i - h)^2 +
\beta \cdot |y_i - h|^3 $$

From here we can now set up the equation for risk. We are told in the hint to go through the motions of finding $h^*$ without doing all of the calculations. Recall risk follows the equation: $R_{\text{f(x)}} = \frac{1}{n} \sum_{i = 1}^{n} f(x)$. Once we have this equation we take the derivative and set it equal to zero to solve for $h^*$.

\begin{align*}
R_{L_{\text{Jack}}} &= \frac{1}{n} \sum_{i = 1}^{n} \alpha \cdot (y_i - h)^2 + \beta \cdot |y_i - h|^3\\
&=\frac{1}{n} (\sum_{\text{if }y_i \geq h} \alpha \cdot (y_i - h)^2 + \sum_{\text{if }y_i < h} \beta \cdot |y_i - h|^3)\\
&\text{To get the derivative use part a!}\\
&= \frac{1}{n} (\sum_{\text{if }y_i \geq h} -2 \alpha(y_i - h) + \sum_{\text{if }y_i < h} 3 \beta |h - y_i|^2)\\
\end{align*}

From here we can set $R_{L_{\text{Jack}}}$ to zero.

\begin{align*}
0 &= R_{L_{\text{Jack}}} \\
0 &= \frac{1}{n} (\sum_{\text{if }y_i \geq h} -2 \alpha(y_i - h) + \sum_{\text{if }y_i <> h} 3 \beta |h - y_i|^2) \\
0 &= -2 \alpha \sum_{\text{if }y_i \geq h} (y_i - h) + 3 \beta \sum_{\text{if }y_i < h} |h - y_i|^2
\end{align*}

We know $h^*$ minimizes empirical risk and makes it 0, so $h^*$ will make the sum of these two derivative parts sum up to zero.


# END SOLUTION



# END SUBPROB

# BEGIN SUBPROB

For any set of values $y_1, y_2, ..., y_n$ in sorted order $y_1 \leq y_2 \leq ... \leq y_n$, evaluate $h^*$ when $\alpha = 0$.

( ) 0
( ) Median({$y_i$})
( ) Any number $\leq y_1$
( ) Any number $\geq y_n$
( ) $\overline y$
( ) Impossible to tell

# BEGIN SOLUTION

Any number $\leq y_1$

# END SOLUTION



# END SUBPROB

# BEGIN SUBPROB

For any set of values $y_1, y_2, ..., y_n$ in sorted order $y_1 \leq y_2 \leq ... \leq y_n$, evaluate $h^*$ when $\beta = 0$.

( ) 0
( ) Median({$y_i$})
( ) Any number $\leq y_1$
( ) Any number $\geq y_n$
( ) $\overline y$
( ) Impossible to tell

# BEGIN SOLUTION

Any number $\geq y_n$

# END SOLUTION



# END SUBPROB
    

# END PROB