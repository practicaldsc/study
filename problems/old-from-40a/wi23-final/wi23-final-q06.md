# BEGIN PROB

<!-- **Probability** -->

<i>Source: [Winter 2023 Final](../wi23-final/index.html), Problem 6</i>

# BEGIN SUBPROB

<center><img src="../assets/images/wi23-final/venn2.png" width="500"></center>

In the above figure, $S$ is the sample space. Two events are denoted by
two circles: $A$ (Red + Blue) and $B$ (Green + Blue). Which area denotes
the event $\bar{A}\cap\bar{B}$?

( )  Orange stripes
( )  Red stripes
( ) Green stripes
( )  Blue stripes

# BEGIN SOLUTION

Orange stripes. 

$\bar{A}$ is the area with green stripes and orange stripes. 
$\bar{B}$ is the area with red stripes and orange stripes.

Therefore $\bar{A}\cap\bar{B}$ is the area with orange stripes.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

Use the law of total probability to prove De Morgan's law:
$P(\bar{A}\cap\bar{B})=1-P(A\cup B)$. You may use the figure above to
visualize the statement, but your proof must use the law of total
probability.

# BEGIN SOLUTION

We can write out the inclusion-exclusion principle. From there, we use the law of total probability to split up event $B$ as the regions $A\cap B$ and $\bar{A}\cap B$ and continue from there:

\begin{align*}
P(A\cup B)&=P({A}) + P({B}) - P(A\cap B)\\
&=P({A}) + \left[ P(A\cap B)+P(\bar{A}\cap B) \right]- P(A\cap B)\\
&=P({A}) + P(\bar{A}\cap B) \\
&=\left[ 1-P(\bar{A}) \right] + P(\bar{A}\cap B) \\
&=1- \left[P(\bar{A}\cap B) + P(\bar{A}\cap \bar{B}) \right] + P(\bar{A}\cap B)\\
&=1-P(\bar{A}\cap\bar{B}) 
\end{align*}

Therefore $P(\bar{A}\cap\bar{B})=1-P(A\cup B)$.

# END SOLUTION

# END SUBPROB

# END PROB