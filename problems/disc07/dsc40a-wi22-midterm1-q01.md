# BEGIN PROB

<!-- <i>Source: [Winter 2022 Midterm 1](../wi22-midterm1/index.html), Problem 1</i> -->

Define the extreme mean ($EM$) of a dataset to be the average of its largest and smallest values. Let
$$f(x)=-3x+4.$$
Show that for any dataset $x_1\leq x_2 \leq \dots \leq x_n$,
$$EM(f(x_1), f(x_2), \dots, f(x_n)) = f(EM(x_1, x_2, \dots, x_n)).$$

# BEGIN SOLUTION

This linear transformation reverses the order of the data because if $a<b$, then $-3a>-3b$ and so adding four to both sides gives $f(a)>f(b)$. Since $x_1\leq x_2 \leq \dots \leq x_n$, this means that the smallest of $f(x_1), f(x_2), \dots, f(x_n)$ is $f(x_n)$ and the largest is $f(x_1)$. Therefore,

$$\begin{aligned} EM(f(x_1), f(x_2), \dots, f(x_n)) &= \dfrac{f(x_n) + f(x_1)}{2} \\ &= \dfrac{-3x_n+4-3x_1+4}{2} \\ &= \dfrac{-3x_n-3x_1}{2} + 4\\ &= -3\left(\dfrac{x_1+x_n}{2}\right) + 4 \\ &= -3EM(x_1, x_2, \dots, x_n)+ 4\\ &= f(EM(x_1, x_2, \dots, x_n)). \end{aligned}$$

# END SOLUTION

# END PROB
