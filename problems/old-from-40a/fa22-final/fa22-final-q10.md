# BEGIN PROB

<!-- \[ **Roulette Game**\]\[13 Points\] Conditional Probabilitiy-->

Consider a roulette wheel that has 36 numbers colored red (R) or black
(B) according to the following pattern:

::: array
cccccccccccccccccc $1$ & $2$ & $3$ & $4$ & $5$& $6$& $7$& $8$& $9$&
$10$& $11$& $12$& $13$& $14$& $15$& $16$& $17$& $18$\
R & R& R& R& R& B & B & B & B & R & R & R & R & B & B & B& B & B\
$36$ & $35$& $34$& $33$& $32$& $31$& $30$& $29$& $28$& $27$& $26$& $25$&
$24$& $23$& $22$& $21$& $20$& $19$\
:::

(For example, this means the color of number $2$ is red or the color of
number $27$ is black.)

Define the following three events:

-   Let A be the event that a spin of the wheel yields a RED number,
    $$A = \{1, 2, 3, 4, 5, 10, 11, 12, 13, 24, 25, 26, 27, 32, 33, 34, 35, 36
    \}.$$

-   Let B be the event that a spin of the wheel yields an EVEN number,
    $$B= 
    \{2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36
    \}
    .$$

-   Let C be the event that a spin of the wheel yields a number no
    greater than $18$, $$C= 
    \{1, 2 ,3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17,18 \}.$$

# BEGIN SUBPROB

\[6 Points\] Are the events A, B, and C \"pairwise independent?\" That
is, is event A independent of event B; event A independent of event C;
and B independent of event C?

Hint: You can start by computing the probability of intersctions between
each pair of these events. 

# BEGIN SOLUTION

One can verify that
$$P(A)=\frac{18}{36}=\frac{1}{2}, \quad P(B)=\frac{18}{36}=\frac{1}{2}, \quad  P(C)=\frac{18}{36}=\frac{1}{2},$$
and,
$$P(A \cap B)=\frac{9}{36}=\frac{1}{4}, \quad P(B \cap C)=\frac{9}{36}=\frac{1}{4}, \quad  P(C)=\frac{9}{36}=\frac{1}{4}.$$

Hence $P(A \cap B)=P(A)P(B)$, $P(B \cap C)=P(B)P(C)$, and,
$P(C \cap A)=P(C)P(A)$. Therefore $A, B, C$ are pairwise independent.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

\[3 Points\] Is $P(A \cap B \cap C)= P(A)P(B)P(C)$?

# BEGIN SOLUTION

No.
$$P(A \cap B \cap C)= \frac{|A \cap B \cap C|}{|S|}=\frac{4}{36}=\frac{1}{9} \neq P(A)P(B)P(C)=\frac{1}{8}$$

# END SOLUTION 

# END SUBPROB 

# BEGIN SUBPROB

\[4 Points\] Are the events $A$ and $B$ conditionally independent
conditioned on $C$?

# BEGIN SOLUTION

No. Note that by using the definition of conditional probability one can
write
$$P(A \cap B| C)=\frac{P(A \cap B \cap C)}{P(C)}=\frac{1/9}{1/2}=\frac{2}{9},$$
by using the results derived from part a) and b). Note also that
$P(A\cap B)=\frac{1}{4} \neq \frac{2}{9}=P(A \cap B| C)$. therefore,
they are not conditionally independent.

# END SOLUTION

# END SUBPROB 

# END PROB