# BEGIN PROB

<!-- **Gradient Descent** Problem -->

Consider the following function $f(x)$ defined below \begin{aligned}
f(x)=\max(0,1-x).

\end{aligned}

# BEGIN SUBPROB

Plot $f(x)$.

# BEGIN SOLUTION

<center><img src="../assets/images/disc11/plot.png" width="500"></center>

The plot should have a y-intercept at $(0,1)$ with slope of $-1$ until $(1,0)$, where it plateaus to
zero.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Consider the following smoothed version of $f(x)$. \begin{aligned}
f_s(x)=\begin{cases}
0 & \text{ if } x\geq 1\\
\frac12(1-x)^2 & \text{ if } 0 < x < 1\\
0.5-x & \text{ if } x\leq 0
\end{cases}.

\end{aligned}

Is the global minima of $f_s(x)$ unique?

# BEGIN SOLUTION

The minima is not unique since the minimum value is 0 and any
$x \geq 1$ achieves $f_s(x)=0$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Perform two steps of gradient descent with step size
$\alpha=1$ for $f_s(x)$ starting from the point $x_0=-0.5$.

# BEGIN SOLUTION

For $x_0=-0.5$, our point lies on the linear part of the function ($f_s(x)=0.5-x$), therefore ${f'}_s(x)=-1$. Our update is then:
$$x_1=x_0 - \alpha {f'}_s(x_0)=-0.5+1=0.5$$

For $x_1=0.5$, our point lies on the quadratic part of the function
($f_s(x)=0.5(1-x)^2$), therefore ${f'}_s(x)=-(1-x)$. The update is then
$$x_2=x_1 - \alpha {f'}_s(x_1)=0.5+(1-0.5)=1$$

# END SOLUTION

# END SUBPROB

# END PROB
