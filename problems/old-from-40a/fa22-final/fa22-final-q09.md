# BEGIN PROB

<!-- Probabilitiy -->

<!-- Split this one with two subprobs into one with four subprobs -->

Two players A and B participate in the following game. There are three
spinners. The first one, $S_1$, lands with equal probability on the
numbers $9$, $5$ and $1$ when spun. The second one, $S_2$, lands with
equal probability on the numbers $7, 6$ and $2$ when spun. The third
one, $S_3$, lands with equal probability on the numbers $8, 4$ and $3$
when spun. Player A chooses one of the three spinners and then player B
chooses one of the remaining two spinners. Both players then spin their
spinners and the one that lands on the higher number is declared the
winner.

![image](Spin.pdf)

# BEGIN SUBPROB

\[9 Points\] Compute the probability that A wins in all of the following
situations.

-   A chooses $S_1$, B chooses $S_2$. 

# BEGIN SOLUTION

    Let $W$ denote the event that player A wins. By using the law of
    total probability $$\begin{aligned}
            P(W)&=P(W|S_2=2)P(S_2=2)+P(W|S_2=6)P(S_2=6)+P(W|S_2=7)P(S_2=7)\\
            &=\frac{2}{3}\times\frac{1}{3}+\frac{1}{3}\times\frac{1}{3}+\frac{1}{3}\times\frac{1}{3}=\frac{4}{9}
           
    \end{aligned}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

-   A chooses $S_2$, B chooses $S_3$. 

# BEGIN SOLUTION

    Similarly by using the law of total probability $$\begin{aligned}
            P(W)&=P(W|S_3=3)P(S_3=3)+P(W|S_3=4)P(S_3=4)+P(W|S_3=8)P(S_3=8)\\
            &=\frac{2}{3}\times\frac{1}{3}+\frac{2}{3}\times\frac{1}{3}+\frac{0}{3}\times\frac{1}{3}=\frac{4}{9}
           
    \end{aligned}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

-   A chooses $S_3$, B chooses $S_1$. 

# BEGIN SOLUTION

    Similarly by using the law of total probability $$\begin{aligned}
            P(W)&=P(W|S_1=1)P(S_1=1)+P(W|S_1=5)P(S_1=5)+P(W|S_1=9)P(S_1=9)\\
            &=\frac{3}{3}\times\frac{1}{3}+\frac{1}{3}\times\frac{1}{3}+\frac{0}{3}\times\frac{1}{3}=\frac{4}{9}
           
    \end{aligned}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[2 Points\] Would you prefer to be player A or Player B? Why? 

# BEGIN SOLUTION

Player B. Because player B can always pick a spinner with probability of
winning $\frac{5}{9}>\frac{1}{2}$.

# END SOLUTION

# END SUBPROB

# END PROB