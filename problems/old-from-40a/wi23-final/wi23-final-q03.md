# BEGIN PROB

<!-- **Gradient Descent** Problem -->

<i>Source: [Winter 2023 Final](../wi23-final/index.html), Problem 3</i>

Let $(x,y)$ be a sample where $x$ is the feature and $y$ denotes the
class. Consider the following loss function, known as Hinge loss, for a
predictor $z$ of $y$: \begin{aligned}
        L(z)=\max(0,1-yz).
    
\end{aligned}

**For all the following questions assume $y=1$.**

# BEGIN SUBPROB

Plot $L(z)$.

# BEGIN SOLUTION

<center><img src="../assets/images/wi23-final/maxgraph.jpg" width="500"></center>

The plot should have a y-intercept at $(0,1)$ with slope of $-1$ until $(1,0)$, where it plateaus to
zero.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Consider the following smoothed version of Hinge loss. \begin{aligned}
    L_s(z)=\begin{cases}
    0 & \text{ if } z\geq 1\\
    \frac12(1-z)^2 & \text{ if } 0<z< 1\\
    0.5-z & \text{ if } z\leq 0
    \end{cases}.
    
\end{aligned}

Is the global minima of $L_s(z)$ unique?

# BEGIN SOLUTION

The minima is not unique since the minimum value is 0 and any
$z\geq 1$ achieves $L(z)=0$.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

Perform two steps of gradient descent with step size
$\alpha=1$ for $L_s(z)$ starting from the point $z_0=-0.5$.

# BEGIN SOLUTION

For $z_0=-0.5$, our point lies on the linear part of the function ($L_s(z)=0.5-z$), therefore ${L'}_s(z)=-1$. Our update is then:
$$z_1=z_0 - \alpha {L'}_s(z_0)=-0.5+1=0.5$$

For $z_1=0.5$, our point lies on the quadratic part of the function
($L_s(z)=0.5(1-z)^2$), therefore ${L'}_s(z)=-(1-z)$. The update is then
$$z_2=z_1 - \alpha {L'}_s(z_1)=0.5+(1-0.5)=1$$

# END SOLUTION

# END SUBPROB

# END PROB