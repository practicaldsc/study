# BEGIN PROB

<i>Source: [Fall 2022 Midterm](../fa22-midterm/index.html), Problem 4</i>

Consider a dataset that consists of $y_1, \cdots, y_n$. In class, we
used calculus to minimize mean squared error,
$R_{sq}(h) = \frac{1}{n} \sum_{i = 1}^n (h - y_i)^2$. In this problem,
we want you to apply the same approach to a slightly different loss
function defined below:
$$L_{\text{midterm}}(y,h)=(\alpha y - h)^2+\lambda h$$

# BEGIN SUBPROB

Write down the empiricial risk $R_{\text{midterm}}(h)$ by
using the above loss function.

# BEGIN SOLUTION

$$R_{\text{midterm}}(h)=\frac{1}{n}\sum_{i=1}^{n}[(\alpha y_i - h)^2+\lambda h]=[\frac{1}{n}\sum_{i=1}^{n}(\alpha y_i - h)^2] +\lambda h$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The mean of dataset is $\bar{y}$, i.e.
$\bar{y} = \frac{1}{n} \sum_{i = 1}^n y_i$. Find $h^*$ that minimizes
$R_{\text{midterm}}(h)$ using calculus. Your result should be in terms
of $\bar{y}$, $\alpha$ and $\lambda$.

# BEGIN SOLUTION

$$h^*=\alpha \bar{y} - \frac{\lambda}{2}$$

___

<br>

$$
\begin{align*}
\frac{d}{dh}R_{\text{midterm}}(h)&= [\frac{2}{n}\sum_{i=1}^{n}(h- \alpha y_i  )] +\lambda \\
&=2 h-2\alpha \bar{y} + \lambda.
\end{align*}
$$

By setting $\frac{d}{dh}R_{\text{midterm}}(h)=0$ we get
$$2 h^*-2\alpha \bar{y} + \lambda=0 \Rightarrow h^*=\alpha \bar{y} - \frac{\lambda}{2}.$$

# END SOLUTION

# END SUBPROB

# END PROB