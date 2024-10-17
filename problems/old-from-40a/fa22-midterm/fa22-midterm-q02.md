# BEGIN PROB

<i>Source: [Fall 2022 Midterm](../fa22-midterm/index.html), Problem 2</i>

Calculate $w_1^*$ and $w_0^*$ of the linear regression line 
for the following dataset, $\mathcal{D}$. 
You may use the fill-in-the-blanks and the table below to organize your work.

$\mathcal{D} = \{(0, 0), (4, 2), (5, 1)\}$.

$\bar x = \phantom{\hspace{.5in}}$
$\bar y = \phantom{\hspace{.5in}}$

<div style="text-align:center; border-width:10px; border-color:black">
| $x_i$ | $y_i$ | $(x_i - \bar x)$ | $(y_i - \bar y)$ | $(x_i - \bar x)(y_i - \bar y)$ | $(x_i - \bar x)^2$ |
|-------|-------|------------------|------------------|--------------------------------|--------------------|
| $0$     | $0$     |                |               |                               |                   |
| $4$     | $2$     |                |                 |                              |                   |
| $5$     | $1$     |                |                 |                               |                  |
</div>

 <!-- \begin{center}
    \begin{tabular}{llllll}\toprule
        $x_i$ & $y_i$ & $(x_i - \bar x)$ & $(y_i - \bar y)$ & $(x_i - \bar x)(y_i - \bar y)$ & $(x_i - \bar x)^2$
        \\\midrule
        0 & 0 & -3 & -1 & 3 & 9 \\
        4 & 2 & 1 & 1 & 1 & 1 \\
        5 & 1 & 2 & 0 & 0 & 4 \\
        \bottomrule
    \end{tabular} \\
\end{center}  -->

<!-- <table style="border-collapse: collapse; border: 2px solid black; width: 100%;">
  <thead>
    <tr>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$x_i$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$y_i$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(x_i - \bar{x})$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(y_i - \bar{y})$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(x_i - \bar{x})(y_i - \bar{y})$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(x_i - \bar{x})^2$</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">0</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">0</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">4</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">2</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">5</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">1</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;"></td>
    </tr>
  </tbody>
</table> -->

<!-- Come back to this later, table formatting -->

$w_1^* =$\
$w_0^* =$

Finally, what can we say about the correlation $r$ and the slope for
this dataset (mathematically)?

# BEGIN SOLUTION

$\bar{x} = \frac{1}{3}(0 + 4 + 5) = 3$
$\quad \quad\bar{y} = \frac{1}{3}(0 + 2 + 1) = 1$ \
<br>

<div style="text-align:center; border-width:10px; border-color:black">
|$x_i$|$y_i$|$(x_i - \bar x)$|$(y_i - \bar y)$|$(x_i - \bar x)(y_i - \bar y)$|$(x_i - \bar x)^2$|
|-------|-------|------------------|------------------|--------------------------------|--------------------|
| $0$     | $0$     | $-3$               | $-1$               | $3$                              | $9$                  |
| $4$     | $2$     | $1$                | $1$                | $1$                              | $1$                  |
| $5$     | $1$     | $2$                | $0$                | $0$                              | $4$                  |
</div>


<!-- \begin{center}
    \begin{tabular}{llllll}\toprule
        $x_i$ & $y_i$ & $(x_i - \bar x)$ & $(y_i - \bar y)$ & $(x_i - \bar x)(y_i - \bar y)$ & $(x_i - \bar x)^2$
        \\\midrule
        0 & 0 & -3 & -1 & 3 & 9 \\
        4 & 2 & 1 & 1 & 1 & 1 \\
        5 & 1 & 2 & 0 & 0 & 4 \\
        \bottomrule
    \end{tabular} \\
\end{center}  -->

<!-- <table style="border-collapse: collapse; border: 2px solid black; width: 100%;">
  <thead>
    <tr>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$x_i$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$y_i$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(x_i - \bar{x})$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(y_i - \bar{y})$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(x_i - \bar{x})(y_i - \bar{y})$</th>
      <th style="border: 1px solid black; background-color: #f2f2f2; padding: 8px; text-align: left;">$(x_i - \bar{x})^2$</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">0</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">0</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">-3</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">-1</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">3</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">9</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">4</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">2</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">1</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">1</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">1</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">1</td>
    </tr>
    <tr>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">5</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">1</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">2</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">0</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">0</td>
      <td style="border: 1px solid black; padding: 8px; text-align: left;">4</td>
    </tr>
  </tbody>
</table> -->

<br>

$w_1^* = \displaystyle
\frac{\sum_{i=1}^n (x_i - \bar{x})(y_i - \bar{y})}{\sum_{i=1}^n (x_i - \bar{x})^2}
= \frac{3 + 1 + 0}{9 + 1 + 4} = \frac{4}{14} = \frac{2}{7}$\

$w_0^* = \bar{y} - w_1^* \bar{x} = 1 - \frac{2}{7} \cdot 3 = 1 - \frac{6}{7} = \frac{1}{7}$


Because $w_1^* = r \frac{\sigma_y}{\sigma_x}$ where the standard deviations $\sigma_y$ and $\sigma_x$ are non-negative, and $w_1^* = 2/7 > 0$, **the correlation $r$ is positive and the slope is positive**.

# END SOLUTION

# END PROB