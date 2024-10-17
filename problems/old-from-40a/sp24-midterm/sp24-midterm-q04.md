# BEGIN PROB

<i>Source: [Spring 2024 Midterm](../sp24-midterm/index.html), Problem 3</i>

Consider a dataset of $n$ values, $y_1, y_2, ..., y_n$, where $y_1 < y_2 < ... < y_n$. Let $R_\text{abs}(h)$ be the mean absolute error of a constant prediction $h$ on this dataset of $n$ values.

Suppose that we introduce a new value to the dataset, $\alpha$. Let $S_\text{abs}(h)$ be the mean absolute error of a constant prediction $h$ on this new dataset of $n + 1$ values.

We're given that:

-  $n > 5$
-  $\alpha$ is not equal to any of $y_1, y_2, ..., y_n$. 
-  All values of $h$ between 7 and 9 minimize $S_\text{abs}(h)$.
-  The slope of $S_\text{abs}(h)$ on the line segment immediately to the right of $\alpha$ is $\frac{5-n}{1 + n}$.

# BEGIN SUBPROB

In the problem statement, we were told that ``all values between 7 and 9 minimize $S_\text{abs}(h)$." More specifically, what interval of values $h$ minimize $S_\text{abs}(h)$? 

( ) $7 < h < 9$
( ) $7 \leq h < 9$ 
( ) $7 < h \leq 9$ 
( ) $7 \leq h \leq 9$

# BEGIN SOLUTION

$7 \leq h \leq 9$

Remeber that when the minimizer of $R_\text{abs}(h)$ is a range that imples that you have dataset with an even number of elements (in this problem that means $n+1$ is even, so $n$ is odd). Now we know that any point in between 7 and 9 minimizes $S_\text{abs}(h)$. Algebraically, if x is a point between 7 and 9, then $S_\text{abs}(x)$ looks like this

\begin{align*}
S_\text{abs}(x) &= |y_1 - x| + ... + |7 - x| + |9 - x| + ... + |y_\text{n} -x| \\
\end{align*}

Now let's say that $\gamma = |7-x|$ , and $\beta = 2-\gamma = |9-x|$. Then we can see that 

\begin{align*}
S_\text{abs}(7) &= (|y_1 - x| - \gamma) + ... + (|7 - x| - \gamma) + (|9 - x| + \gamma) + ... + (|y_\text{n} - x| + \gamma)\\
S_\text{abs}(7) &= |y_1 - x| + ... + |7 - x| + |9 - x| + ... + |y_\text{n} - x| + \frac{n+1}{2}(\gamma) + \frac{n+1}{2}(-\gamma)\\
S_\text{abs}(7) &= S_\text{abs}(x)
\end{align*}

Similarly

\begin{align*}
S_\text{abs}(9) &= (|y_1 - x| + \beta) + ... + (|7 - x| + \beta) + (|9 - x| - \beta) + ... + (|y_\text{n} - x| - \beta)\\
S_\text{abs}(9) &= |y_1 - x| + ... + |7 - x| + |9 - x| + ... + |y_\text{n} - x| + \frac{n+1}{2}(-\beta) + \frac{n+1}{2}(\beta)\\
S_\text{abs}(9) &= S_\text{abs}(x)
\end{align*}

Therefore both 7 and 9 minimize $S_\text{abs}(h)$.

**Note:** Even though the equations end at $y_n$, remember that there's an element $\alpha$ somewhere on the dataset, making $n+1$ elements in total. In particular, there must be $\frac{n+1}{2}$ elements before and including  7, and $\frac{n+1}{2}$ after and including  9.

<average>59</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Which value(s) minimize $R_\text{abs}(h)$? Give your answer(s) as integer(s) with no variables. Show your work.

<i>Hint: Don't start by trying to expand $\frac{1}{n} \sum_{i = 1}^n |y_i - h|$ --- instead, think about what removing $\alpha$ does.</i>

# BEGIN SOLUTION

9

We now that the minimizer of $R_\text{abs}(h)$ must be the median, which we know it must be either 7 or 9, and it all depends on where on the dataset was $\alpha$ added. Assuming we added $\alpha$ on the first half of the dataset, our dataset  should look like this
\begin{align*}
y_1,...,\alpha,...7,9,...,y_\text{n+1}
\end{align*}
Now if we remove $\alpha$, the dataset becomes
\begin{align*}
y_1,...,7,9,...,y_\text{n+1}
\end{align*}
which means that now there's only $\frac{n+1}{2} - 1$ elements from $y_1$ to $7$, and $\frac{n+1}{2}$ elements from $9$ to $y_\text{n}$. Thus 9 is the new median since there would be $\frac{n+1}{2} - 1$ elements before and after 9.
Using a similar reasoning you can show that if $\alpha$
is on the second half of the dataset then 7 would be the new median and minimizer.

Now we only need to find the placement of $\alpha$ on our data. Remember that the slope of $S_\text{abs}(h)$ at a point p can be calculated as
\begin{align*}
\frac{\text{number of points before p} - \text{number of points after p}}{n+1} \\
\end{align*}
Which means that if the slope of $S_\text{abs}(h)$ is negative near $\alpha$ then $\alpha$ is in the first halft, otherwise $\alpha$ is in the second half.

Since we know that the slope of $S_\text{abs}(h)$ on the line segment immediately to the right of $\alpha$ is $\frac{5-n}{1 + n}$ , and since $n > 5$ then the slope is negative, meaning that $\alpha$ is on the first half, making 9 the minimizer.

<average>39</average>

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What is the slope of $S_\text{abs}(h)$ on the line segment immediately to the left of $\alpha$? Give your answer in the form of an expression involving $n$. Show your work.

# BEGIN SOLUTION
$\frac{3-n}{1 + n}$

Remember that the slope of $S_\text{abs}(h)$ at a point p can be calculated as
\begin{align*}
\frac{\text{number of points before p} - \text{number of points after p}}{n+1} \\
\end{align*}

Whenever we transition from the right of $\alpha$ to the left of $\alpha$, then alpha becomes a new point after p and we also lose a point that was before p, therefore looking at the formula above we can get the slope of the segment to the left of $\alpha$ by subtracting 2 to the numerator of the slope to the right of $\alpha$.

Since we know that the slope of $S_\text{abs}(h)$ on the line segment immediately to the right of $\alpha$ is $\frac{5-n}{1 + n}$, then the answer must be $\frac{3-n}{1 + n}$.

<average>32</average>

# END SOLUTION

# END SUBPROB

# END PROB