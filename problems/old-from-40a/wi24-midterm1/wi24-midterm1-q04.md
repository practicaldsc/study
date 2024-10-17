# BEGIN PROB

<i>Source: [Winter 2024 Midterm 1](../wi24-midterm1/index.html), Problem 4</i>

Note that we have two simplified closed form expressions for the
estimated slope $w$ in simple linear regression that you have already
seen in discussions and lectures:

$$\begin{align*}
    w &= \frac{\sum_i (x_i - \overline{x}) y_i}{\sum_i (x_i - \overline{x})^2} \\ \\
    w &= \frac{\sum_i (y_i - \overline{y}) x_i }{\sum_i (x_i - \overline{x})^2}
\end{align*}$$ 

where we have dataset
$D = [(x_1,y_1), \ldots, (x_n,y_n)]$ and  sample means &emsp;
$\overline{x} = {1 \over n} \sum_{i} x_i, \quad \overline{y} = {1 \over n} \sum_{i} y_i$.
Without further explanation, $\sum_i$ means $\sum_{i=1}^n$

# BEGIN SUBPROB

Are ($1$) and ($2$) equivalent? That is, is the following equality
true? Prove or disprove it.
$$\sum_i (x_i - \overline{x}) y_i = \sum_i (y_i - \overline{y}) x_i$$

# BEGIN SOLUTION

True. 
$$\begin{align*}
    & \sum_i (x_i - \overline{x}) y_i = \sum_i (y_i - \overline{y}) x_i \\
    & \Leftrightarrow  \sum_i x_i y_i - \overline{x} \sum_i y_i = \sum_i x_i y_i - \overline{y} \sum_i x_i \\
    & \Leftrightarrow   \overline{x} \sum_i y_i = \overline{y} \sum_i x_i \\
    & \Leftrightarrow {1 \over n} \sum_i x_i \sum_i y_i = {1 \over n} \sum_i y_i \sum_i x_i \\
\end{align*}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

True or False: If the dataset shifted right by a constant distance
$a$, that is, we have the new dataset
$D_a = (x_1 + a,y_1), \ldots, (x_n + a,y_n)$, then will the estimated
slope $w$ change or not?

( ) True 
( ) False

# BEGIN SOLUTION

False. By ($1$) in part (a), we can view $w$ as only being affected by $x_i - \overline{x}$,
which is unchanged after shifting horizontally. Therefore, $w$ is unchanged.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

True or False: If the dataset shifted up by a constant distance
$b$, that is, we have the new dataset
$D_b = [(x_1,y_1 + b), \ldots, (x_n,y_n + b)]$, then will the estimated
slope $w$ change or not?

( ) True 
( ) False


# BEGIN SOLUTION

False. By ($2$) in part (a), we can view $w$ as only being affected by $y_i - \overline{y}$,
which is unchanged after shifting vertically. Therefore, $w$ is unchanged.

# END SOLUTION

# END SUBPROB

# END PROB