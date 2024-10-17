# BEGIN PROB

<!-- \[**Bayes theorem**\] -->

<i>Source: [Winter 2023 Final](../wi23-final/index.html), Problem 8</i>

Let's say $1\%$ of the population has a certain genetic defect.

# BEGIN SUBPROB

A test has been developed such that $90\%$ of administered
tests accurately detect the gene (true positives). What needs to be the
false positive rate (probability that the administered test is positive even though the
patient doesn't have a genetic defect) such that the probability
that a patient having the genetic defect given a positive result is $90\%$?

# BEGIN SOLUTION

The false positive rate should be  $\approx 0.001$ to satisfy this condition.

Let $A$ be the event a patient has a genetic defect.
Let $B$ be the event a patient got a positive test result.

We know:

-   $P(A) = 0.01$

-   The true positive rate (probability of a positive test result given someone has
    the genetic defect) can be modeled by $P(B|A)=0.9$

-   The false positive rate (probability of positive test result given someone
    doesn't have the genetic defect) can be modeled by $P(B|\bar{A}) = p$

We want:

- The probability that a patient having the genetic defect given a positive result ($P(A|B)$) is $90\%$

Let's set up a relationship between what we know and what we want by using Bayes' Theorem:

$$\begin{aligned}
P(A|B) &= \frac{ P(B|A)P(A)}{P(B)} \\
&=\frac{ P(B|A)P(A)}{P(B|A)P(A)+ P(B|\bar{A})P(\bar{A})}\\
&=\frac{0.9 \cdot 0.01}{0.9 \cdot 0.01 + p \cdot 0.99} =0.9
\end{aligned}$$

Rearranging the terms:

$$\begin{aligned}
0.9 \cdot 0.01 & = 0.9 \cdot (0.9 \cdot 0.01 + p \cdot 0.99)\\
0.1 \cdot 0.9 \cdot 0.01 & = 0.9 \cdot p \cdot 0.99 \\ 
p = P(B|\bar{A}) &=\frac{0.1 \cdot 0.01}{0.99} \approx 0.001
\end{aligned}$$

We've found that the probability of a false positive (positive result for someone who
doesn't have the genetic defect) needs to be $\approx 0.001$ to satisfy our condition.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

A test has been developed such that $1\%$ of administered
tests are positive when the patient doesn't have the genetic defect (false
positives). What needs to be the true positive probability so that the
the probability a patient has the genetic defect
given a positive result is $50\%$?

# BEGIN SOLUTION

The probability of a true positive needs to be $0.99$ to satisfy our condition.

Let $A$ be the event a patient has a genetic defect.
Let $B$ be the event a patient got a positive test result.

We know:

-   $P(A) = 0.01$

-   The true positive rate (probability of positive test result if someone has
    the genetic defect) can be modeled by $P(B|A) = p$

-   The false positive rate (probability of positive test result if someone
    doesn't have the genetic defect) can be modeled by $P(B|\bar{A}) = 0.01$

We can set up Bayes' Theorem again to gain more information:

$$\begin{aligned}
P(A|B)  &= \frac{ P(B|A)P(A)}{P(B|A)P(A)+ P(B|\bar{A})P(\bar{A})}\\
&=\frac{p \cdot 0.01}{p \cdot 0.01 + 0.01 \cdot 0.99} \\
&=\frac{p}{p  + 0.99} = 0.5
\end{aligned}$$

Rearranging the terms:
$$\begin{aligned}
p  & = 0.5 \cdot (p  + 0.99)\\
0.5 \cdot p  & = 0.5 \cdot  0.99 \\ 
p = P(B|{A}) &=0.99
\end{aligned}$$

We find that the probability of a true positive needs to be $0.99$ to satisfy our condition.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

$1\%$ of administered tests are positive when the patient doesn't have the gene
(false positives). Show that there is no true positive probability such
that the probability of a patient having the genetic defect given a
positive result can be $90\%$. 

<!-- (Hint: remember a
probability $p$ needs to fulfill $0 \leq p \leq 1$.) -->

# BEGIN SOLUTION

Let $A$ be the event a patient has a genetic defect.
Let $B$ be the event a patient got a positive test result.

We know:

-   $P(A) = 0.01$

-   The true positive rate (probability of positive test result if someone has
    the genetic defect) can be modeled by $P(B|A) = p$

-   The false positive rate (probability of positive test result if someone
    doesn't have the genetic defect) can be modeled by $P(B|\bar{A}) = 0.01$

Let's try solving as before:

$$\begin{aligned}
P(A|B)  &=\frac{ P(B|A)P(A)}{P(B|A)P(A)+ P(B|\bar{A})P(\bar{A})}\\
&=\frac{p \cdot 0.01}{p \cdot 0.01 + 0.01 \cdot 0.99} \\
&=\frac{p}{p + 0.99} = 0.9
\end{aligned}$$

Rearranging the terms:
$$\begin{aligned}
p  & = 0.9 \cdot (p  + 0.99)\\
0.1 \cdot p  & = 0.9 \cdot  0.99 \\ 
p = P(B|{A}) &= \frac{0.99 \cdot 0.9}{0.1} = 8.91 > 1
\end{aligned}$$

We have found that $p$, a probability value, must be greater than 1, which is impossible!

Given the rate of false positives, we cannot find a true positive rate
such that the probability of a patient having the genetic defect given a
positive result is 0.9.

# END SOLUTION

# END SUBPROB

# END PROB