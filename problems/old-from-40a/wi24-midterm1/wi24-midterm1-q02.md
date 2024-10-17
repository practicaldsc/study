# BEGIN PROB

<i>Source: [Winter 2024 Midterm 1](../wi24-midterm1/index.html), Problem 2</i>

Let $R_{sq}(h)$ represent the mean squared error of a
constant prediction $h$ for a given dataset. For the dataset
$\{3, y_{1}\}$, the graph of $R_{sq}(h)$ has its minimum at the point
$(5,r_{1})$. Find out the value of $y_{1}$ and $r_{1}$

# BEGIN SOLUTION

$$y_1 = 7, r_1 = 4$$

The mean squared error is written as: 
$$\begin{align*}
        R_{sq}(h) = \frac{1}{n}\sum_{i=0}^{n}(y_{i}-h)^2    
\end{align*}$$

Since we only have two data points ($n=2$), the equation
simplifies to: 

$$\begin{align*}
        R_{sq}(h) = \frac{1}{2}((y_{0}-h)^2+ (y_{1}-h)^2)    
\end{align*}$$

Taking the derivative with respect to $h$, we have:
$$\begin{align*}
        \frac{dR_{sq}(h)}{dh} = -(y_{0}-h)- (y_{1}-h)    
\end{align*}$$

We know that the derivative has to be $0$ at the local
minima, therefore at $h=5$, we have: 

$$\begin{align*}
        \frac{dR_{sq}(h)}{dh} = -(3-5)- (y_{1}-5) &= 0\\
        % -2+y_1-5 &=0\\
        y_1 &= 7
\end{align*}$$

So we know that the dataset is $\{3,7\}$. Given all these
information, we can calculate $r_1$ with: 

$$\begin{align*}
        R_{sq}(5) &= \frac{1}{2}((y_{0}-5)^2+ (y_{1}-5)^2)\\
        &=\frac{1}{2}((3-5)^2+ (7-5)^2)\\
        &=\frac{1}{2}(4+4)=4
\end{align*}$$

# END SOLUTION

# END PROB