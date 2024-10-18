# BEGIN PROB

<!-- <i>Source: [Fall 2021 Final Exam](../fa21-final/index.html), Problem 4</i> -->

You may find the following properties of logarithms helpful in this question. Assume that all logarithms in this question are natural logarithms, i.e. of base $e$.

- $e^{\log(x)} = x$
- $\log(a) + \log(b) = \log(a \cdot b)$
- $\log(a) - \log(b) = \log \left( \frac{a}{b} \right)$
- $\log(a^c) = c \log (a)$
- $\frac{d}{dx} \log x = \frac{1}{x}$

Billy is trying his hand at coming up with loss functions. He comes up with the Billy loss, $L_B(y_i, h)$, defined as follows:

$$L_B(y_i, h) = \left[ \log \left( \frac{y_i}{h} \right) \right]^2$$

Throughout this problem, assume that all $y_i$s are positive.

# BEGIN SUBPROB

Show that: $$\frac{d}{dh} L_B(y_i, h) = - \frac{2}{h} \log \left( \frac{y_i}{h} \right)$$

# BEGIN SOLN

$$
\begin{align*}
    \frac{d}{dh} L_B(y_i, h) &= \frac{d}{dh} \left[ \log \left( \frac{y_i}{h} \right) \right]^2 \\
    &= 2 \cdot \log \left( \frac{y_i}{h} \right) \cdot \frac{d}{dh} \log \left( \frac{y_i}{h} \right) \\
    &= 2 \cdot \log \left( \frac{y_i}{h} \right) \cdot \frac{d}{dh} \left( \log(y) - \log(h) \right) \\
    &= 2 \cdot \log \left( \frac{y_i}{h} \right) \cdot \left( - \frac{1}{h} \right) \\
    &= -\frac{2}{h} \log \left( \frac{y_i}{h} \right)
\end{align*}
$$

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Show that the constant prediction $h^*$ that minimizes average Billy loss for the constant model is:

$$h^* = \left(y_1 \cdot y_2 \cdot ... \cdot y_n \right)^{\frac{1}{n}}$$

You do not need to perform a second derivative test, but otherwise you must show your work.

_Hint: To confirm that you're interpreting the result correctly, $h^*$ for the dataset 3, 5, 16 is $(3 \cdot 5 \cdot 16)^{\frac{1}{3}} = 240^{\frac{1}{3}} \approx 6.214$._

# BEGIN SOLN

$$
\begin{align*}
    R_B(h) &= \frac{1}{n} \sum_{i = 1}^n \left[ \log \left( \frac{y_i}{h} \right) \right]^2 \\
\frac{d}{dh} R_B(h) &= \frac{1}{n} \sum_{i = 1}^n \frac{d}{dh} \left[ \log \left( \frac{y_i}{h} \right) \right]^2 \\
&= \frac{1}{n} \sum_{i = 1}^n -\frac{2}{h} \log \left( \frac{y_i}{h} \right) \\
&= -\frac{2}{nh} \sum_{i = 1}^n \log \left( \frac{y_i}{h} \right) = 0 \\
0 &= \sum_{i = 1}^n \log \left( \frac{y_i}{h} \right) = \sum_{i = 1}^n \left( \log(y_i) - \log(h)\right) \\
0 &= \sum_{i = 1}^n \log(y_i) - \log(h) \sum_{i = 1}^n 1 \\
0 &= \left( \log(y_1) + \log(y_2) + ... + \log(y_n) \right) - n \log(h) \\
\log(h^n) &= \log(y_1 \cdot y_2 \cdot ... \cdot y_n) \\
h^n &= y_1 \cdot y_2 \cdot ... \cdot y_n \\
h^* &= (y_1 \cdot y_2 \cdot ... \cdot y_n)^{\frac{1}{n}}
\end{align*}
$$

# END SOLN

# END SUBPROB

# END PROB
