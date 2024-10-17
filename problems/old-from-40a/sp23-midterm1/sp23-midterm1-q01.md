# BEGIN PROB

<i>Source: [Spring 2023 Midterm 1](../sp23-midterm1/index.html), Problem 1</i>

Consider a dataset such that $60 \leq y_1 \leq y_2 \leq \dots \leq y_n$. Let $R_{abs}(h)$ represent the mean absolute error of a constant prediction $h$ on this dataset. Suppose we know that $R_{abs}(27) = 94.$

# BEGIN SUBPROB

Find $\bar y$, or the mean of $\{y_1, y_2, \dots, y_n\}$.

# BEGIN SOLUTION

$\bar{y} = 121$

There are several ways to complete this problem. One way is to interpret mean absolute error of a constant prediction $h$ as the average distance of each data point to $h$. So we are told that the average distance of each data point to $27$ is $94$. That is, the data points are $94$ units away from $27$ on average. Since all the data is at least $60$, they must be $94$ units *more* than $27$, or $121$, on average.


<center><img src="../../assets/images/sp23-midterm1/p1/1a.jpg" width="666" height="166"></center>


You can also arrive at the same answer algebraically using the definition of $R_{abs}(h)$. We have $$\begin{aligned} R_{abs}(h) &= \frac1n \sum_{i=1}^{n}|y_i - h| \\ R_{abs}(27) &= \frac1n \sum_{i=1}^{n}|y_i - 27| \\ &= \frac1n \sum_{i=1}^{n}(y_i - 27) \qquad \text{because each~} y_i\geq 60 \\ &= \frac1n\left( \sum_{i=1}^{n}y_i - \sum_{i=1}^{n}27\right) \\ &= \frac1n\left( n\cdot\bar y - n\cdot27\right) \\ &= \bar y - 27 \end{aligned}$$ 

Since we are told that $R(27) = 94$, we can set $\bar y - 27 = 94$, to find that $\bar y = 121$.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

Find $R_{abs}(58)$.

# BEGIN SOLUTION

$R_{abs}(58) = 63$

Again, we can complete this problem in multiple ways. Interpreting $R_{abs}(h)$ as the average distance of each data point to $h$, we can see that since $58$ is $31$ units closer to each data point than $27$, $R_{abs}(58) = R_{abs}(27) - 31 = 94 - 31 = 63.$

Another way to do this problem uses the answer from part (a). Since the data points average to $121$, their distance to $58$ is $121-58 = 63$, on average.

<center><img src="../../assets/images/sp23-midterm1/p1/1b.jpg" width="666" height="166"></center>

# END SOLUTION 

# END SUBPROB 

# BEGIN SUBPROB

Which of the following *could* be the mean absolute deviation from the median for this dataset? There is only one correct answer.

( ) 18
( ) 62
( ) 94
( ) 102

# BEGIN SOLUTION

Our answer is $18$.

One easy way to do this problem is to recognize that none of these values are too low, but they may be too high. For example, the mean absolute deviation from the median can be as low as $0$, when all the data points are the same. Since we are told there is only one correct answer and we know that no answer choice is too low, that means the correct answer must be the lowest option, $18$.

We can also rule out all the other answer choices to show that they are too high. To do that, we'll show that $62$ is too high, and therefore, both $94$ and $102$ are too high as well. We are told that all data points are at least $60$. By similar logic as we used in part (b), we can see that $R_{abs}(60) = 61$. Since the minimum value of $R_{abs}(h)$ occurs at the median $h^*\geq 60$ and we already know $R_{abs}(60) = 61$, it must be the case that $R(h^*) \leq 61$.

<center><img src="../../assets/images/sp23-midterm1/p1/1c.jpg" width="666" height="166"></center>

# END SOLUTION

# END SUBPROB 

# END PROB