# BEGIN PROB

<!-- Probability -->

We have three boxes containing white
and black balls. The first box has 3 white and 2 black balls, the second
box has 2 white and 3 black balls, and, the third box has 4 white and 1
black balls. We pick a box uniformly at random and pick a ball from it.
We observe that the ball is white. What is the probability that it came
from the third box, i.e., what is the probability of the third box was
picked at the beginning?

![image](BlackandWhiteballs.pdf)

# BEGIN SOLUTION

Let 
\begin{align*}
A:& \text{ event that the chosen ball is white}\\
E_1:& \text{ event that the  ball is chosen from the first box}\\
E_2:& \text{ event that the  ball is chosen from the second box}\\
E_3:& \text{ event that the  ball is chosen from the third box}.
\end{align*}

Note that $P(E_1)=P(E_2)=P(E_3)=\frac{1}{3}$. Also, $P(A|E_1)=\frac{3}{5}$, $P(A|E_2)=\frac{2}{5}$, and, $P(A|E_3)=\frac{4}{5}$.

By using the Bayes' theorem
$$
P(E_3|A)=\frac{P(A|E_3)P(E_3)}{P(A|E_1)P(E_1)+P(A|E_2)P(E_2)+P(A|E_3)P(E_3)}= \frac{4/5 \times 1/3 }{3/5 \times 1/3+2/5 \times 1/3+4/5 \times 1/3}= \frac{4}{9}.
$$

# END SOLUTION

# END PROB