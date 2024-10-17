# BEGIN PROB

<i>Source: [Fall 2022 Midterm](../fa22-midterm/index.html), Problem 3</i>

Mahdi runs a local pastry shop near UCSD and sells traditional desert
called Baklava. He bakes Baklavas every morning to keep his promise of
providing fresh Baklavas to his customers daily. Here is the amount of
Baklava he sold each day during last week in pounds(lb):
$$y_1=100, y_2=110, y_3=75, y_4=90, y_5=105, y_6=90, y_7=25$$

Mahdi needs your help as a data scientist to suggest <u>the best constant
prediction ($h^*$) of daily sales that minimizes the empirical risk using
$L(h,y)$ as the loss function</u>. Answer the following questions and give a
**brief justification** for each part. **This problem has many parts, if
you get stuck, move on and come back later!**

# BEGIN SUBPROB

Let $L(h,y)=|y-h|$. What is $h^*$? (We'll later refer to this
prediction as $h_1^*$).

# BEGIN SOLUTION

As we have seen in lectures, the median minimizes the absolute loss risk
function. $$h^*_1=\text{Median}(y_1, \cdots, y_7).$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Let $L(h,y)=(y-h)^2$. What is $h^*$? (We'll later refer to this
prediction as $h_2^*$).

# BEGIN SOLUTION

As we have seen in lectures, the mean minimizes the square loss risk
function. $$h^*_2=\text{Mean}(y_1, \cdots, y_7).$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

**True** or **False**: Removing $y_1$ and $y_3$ from the
dataset does not change $h_2^*$.

( ) True
( ) False

# BEGIN SOLUTION

False. It changes the mean from $85$ to $84$. (However, the median
is not changed.)

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Mahdi thinks that $y_7$ is an outlier. Hence, he asks you to
remove $y_7$ and update your predictions in parts (a) and (b) accordingly.
Without calculating the new predictions, can you justify which
prediction changes *more*? $h^*_1$ or $h_2^*$?

# BEGIN SOLUTION

Removing $y_7$ affects $h_2^*$ more than $h_1^*$. This is because the mean squared loss is more sensitive to outliers than absolute loss, and removing data changes the mean more. 

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

**True** or **False**: Let $L(y,h)=|y-h|^3$. You can use
the Gradient descent algorithm to find $h^*$. 

( ) True
( ) False

# BEGIN SOLUTION

False. The function $|y-h|^3$ is not differentiable everywhere so we
can not use the gradient descent to find the minimum.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

**True** or **False**: Let $L(y,h)=\sin(y-h)$. The Gradient
descent algorithm is guaranteed to converge, provided that a proper
learning rate is given.\

( ) True
( ) False

# BEGIN SOLUTION

False. The function is not convex, so the gradient descent algorithm
is not guaranteed to converge.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Mahdi has noticed that Baklava daily sale is associated with weather
temperature. So he asks you to incorporate this feature to get a better
prediction. Suppose the last week's daily temperatures are
$x_1, x_2, \cdots, x_7$ in Fahrenheit (F). We know that $\bar x=65$,
$\sigma_x=8.5$ and the best linear prediction that <u>minimizes the mean
squared error</u> is $H^*(x)=-3x+w_0^*$.

What is the correlation coefficient ($r$) between $x$ and
$y$? What does that mean? 

# BEGIN SOLUTION

$r=-0.95$. This means the weather temperature inversely affects Baklava sales, i.e., they
are highly negatively correlated.

We know $w_1^* = \frac{\sigma_y}{\sigma_x}r.$ We know that $\sigma_x=8.5$
and $w_1^*=-3$. We can find $\sigma_y$ as follows: 

$$\begin{aligned}
    \sigma_y^2 =& \frac{1}{n} \sum_{i = 1}^n (y_i - \bar{y})^2\\
    =& \frac{1}{7}[(100-85)^2+(110-85)^2+(75-85)^2+(90-85)^2+(105-85)^2+(90-85)^2+(25-85)^2]\\
    =&\frac{1}{7}[15^2+25^2+10^2+5^2+20^2+5^2+60^2]=714.28
\end{aligned}$$

Then, $\sigma_y=26.7$ which results in $r=-0.95$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

**True** or **False**: The unit of $r$ is $\frac{lb}{F}$
(Pound per Fahrenheit). 

( ) True
( ) False

# BEGIN SOLUTION

False. The correlation coefficient has no unit. (It is always a unitless
number in $[-1,1]$ range.)

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Find $w^*_0$. _(Hint: You'll need to find $\bar y$ for the given dataset)_

# BEGIN SOLUTION

$$w_0^*=280$$

Note that $H(\bar x)=\bar y$. Therefore, 
$$\begin{aligned}
        H(65)=-3\cdot 65 +w_0^*=85 \xrightarrow[]{}w_0^*=280.
\end{aligned}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What would the best linear prediction $H^*(x)$ be if we
multiply all $x_i$'s by $2$? 

# BEGIN SOLUTION

$$H^*(x) = -1.5x + 280$$

The standard deviation scales by a factor of $2$, i.e.,
$\sigma_x'=2\cdot \sigma_x$.<br>
The same is true for the mean, i.e.,
$\bar{x}'=2 \cdot \bar{x}.$ <br>
 The correlation $r$, standard deviation of the y-values $\sigma_y$, and the mean of the y-values $\bar y$ do not change. <br> 
(You can verify these claims by plugging $2x$ in for $x$ in their respective formulas and seeing what happens, but it's faster to _visually_ reason why this happens.)


 Therefore, $w_1'^*=\frac{\sigma_y'}{\sigma_x'}r' = \frac{(\sigma_y)}{(2\cdot\sigma_x)}(r) = \frac{w_1^*}{2} = -1.5$.

We can find $w_0'^*$ as follows:

\begin{align*}
\bar{y}'&=H(\bar{x}')\\&=\frac{w_1^*}{2}(2\bar{x})+w_0'^*\\&=w_1^*\bar{x}+w_0'^* \\
&\downarrow \\
(85) &= -3(65) + w_0'^* \\
w_0'^*&=280
\end{align*}

So, $H^*(x)$ would be $-1.5x + 280$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What would the best linear prediction $H^*(x)$ be if we add
$20$ to all $x_i$'s? 

# BEGIN SOLUTION

$$H^*(x) = -3x + 340$$

All parameters remain unchanged except $\bar{x}'=\bar{x}+20.$ Since $r$,
$\sigma_x$ and $\sigma_y$ are not changed, $w_1^*$ does not change. Then, one
can find $w_0^*$ as follows:

\begin{align*}
\bar{y}'&=H(\bar{x}') \\
&\downarrow \\
(85) &=-3(65+20)+w_0^* \\
w_0^*&=340
\end{align*}

So, $H^*(x)$ would be $-3x + 340$.

# END SOLUTION

# END SUBPROB

# END PROB