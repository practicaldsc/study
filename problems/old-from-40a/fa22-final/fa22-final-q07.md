# BEGIN PROB

<!-- \[**Combinatorics**\]\[9 Points\] -->

# BEGIN SUBPROB

\[3 Points\] We toss a fair coin $6$ times and get a sequence of Heads
(H) and Tails (T). How many sequences have at least $2$ heads?

# BEGIN SOLUTION

It is easier to count the number of possible outcomes in the complement
event. Therefore, we should count the total number of sequences with
**exactly** $0$ or $1$ Heads. We pick $i$ locations that represent the
locations of Heads first for $i=0,1$. The only choice for other
locations is Tails. So, $$\begin{aligned}
    &\text{# sequences with \textbf{
 exactly} $0$ Heads}= {6\choose 0}\\
  &\text{# sequences with \textbf{
 exactly} $1$ Heads}= {6\choose 1}
\end{aligned}$$ Also, the total number of sequences is $2^6$. Then, the
total number of sequences with **at least** $2$ Heads is equal to
$2^6- {6\choose 0}-{6\choose 1}=64- 1-6=57$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[3 Points\] We have a standard deck of $52$ cards. How many hands of
$6$ cards are there that have a four-of-a-kind and $3$ cards of the same
suit?

# BEGIN SOLUTION

We have $13$ choices for a four-of-a-kind hand. Also, there are $4$
different suits, and $12$ cards from each suit is left. We should choose
a suit and pick two remaining cards from that suit. We can do this in
$4 \times {12\choose 2}$ ways. Then, we can pick such hands in
$13 \times 4 \times  {12\choose 2}$ different ways.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

\[3 Points\] How many ways are there of rolling a $6$-sided die $6$
times in a row such that there are **exactly four** $3$s in a row
somewhere, i.e., there are exactly four $3$s **and** they are in a row?

# BEGIN SOLUTION

There are exactly $3$ possibilities for the location of four $3$s in a
row.

Case 1: $$3 \quad 3 \quad 3 \quad 3 \quad  - \quad -$$

Case 2: $$- \quad 3 \quad 3 \quad 3 \quad 3 \quad  -$$

Case 3: $$- \quad - \quad 3 \quad 3 \quad 3 \quad 3$$

In all above cases, there are $5$ possibilities for the blanl spaces.
Then we have $5 \times 5 =25$ possibilities in each case that result in
$3 \times 25 =75$ total ossibilities.

# END SOLUTION

# END SUBPROB

# END PROB