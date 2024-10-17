# BEGIN PROB

<!-- Empirical Risk Minimization Problem -->

<i>Source: [Winter 2023 Final](../wi23-final/index.html), Problem 1</i>

For each of the loss functions below, **find the constant prediction $h^*$** which minimizes the
corresponding empirical risk with respect to the data
$y_1 = -3, y_2 = 2, y_3 = 2, y_4 = -2$, $y_5 = -6$ .

# BEGIN SUBPROB

The **$\alpha$-absolute** loss is defined as follows:
$$L_{\alpha-\text{abs} }(h, y) = |h - (y-\alpha) |.$$

Use $\alpha=3$. 

<!-- Bonus \[2 points\]: What is the empirical risk
$R_{\alpha-\text{abs}} (h^*)$? -->

# BEGIN SOLUTION

$h^*=-2-3=-5$

This is equivalent to the absolute loss on the same dataset shifted
by $\alpha$. Therefore the optimal solution that minimizes this loss is
the median (-2) shifted by $-\alpha$ (-3).


# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The **$\beta$-zero-one** loss is defined as follows:
\begin{aligned}
                L_{\beta -01}(h,y) = \begin{cases}
                    0,& \text{$h = y\mathbf{\beta} $},\\
                    1,& \text{$h \neq y\mathbf{\beta} $}.
                \end{cases}
            
\end{aligned}

Use $\beta=2$. Hint: plot the empirical risk function for $y\in[-6, 3]$.

<!-- Bonus \[2 points\]: What is the empirical risk $R_{\beta- 01} (h^*)$? -->

# BEGIN SOLUTION

$h^*=2 \cdot 2=4$.

This is equivalent to the absolute loss on the same dataset scaled
by $\beta$. Therefore the optimal solution that minimizes this loss is
the mode scaled by $\beta$.

# END SOLUTION

# END SUBPROB

# END PROB