# BEGIN PROB

<i>Source: [Winter 2024 Final Part 2](../wi24-final-pt2/index.html), Problem 1</i>

Consider an experiment where each of $n$ people selects
one piece from their own set of chess pieces, uniformly at random.
A chess set has $32$ pieces. $16$ of these are black and $16$ of these are white. **In each color**, the $16$ pieces are:

- $8$ pawns,
- $2$ bishops,
- $2$ knights,
- $2$ rooks,
- $1$ queen, and 
- $1$ king.

The **result** of the experiment is a description of the **colors and
types** of the pieces each person selected. For example, if $n=3$, one
possible result is:

-   Person 1 selected a white knight.

-   Person 2 selected a black queen.

-   Person 3 selected a black pawn.

# BEGIN SUBPROB

How many results are possible for this experiment with $n$
people?

( ) $2^n$
( ) $6^n$
( ) $12^n$
( ) $16^n$
( ) $32^n$
( ) None of the above.

# BEGIN SOLUTION

$12^n$

To answer this question we must determine how many **different** pieces each person can choose. In a complete chess set we know that there's pawns, knights, bishops, rooks, queens, and kings. Then we also know that each of these pieces can be aither black or white, therefore there's a totoal of $6 \cdot 2 = 12$ different pieces. Notice that a complete chess set has 32 total pieces, but there's multiple duplicates in those 32 pieces that is why we say there's only 12 different pieces on a chess set.

Now since every person has their own chess set, we know that each of them can get any of the 12 pieces, therefore if we do this with one person there would be $12$ possible outcomes, now if we do it with two persons the first person can get any of the 12 pieces, but then for each piece that person 1 can choose person 2 can choose from their 12 pieces, which means that in this case there's $12 \cdot 12$ outcomes. if we keep doing this for n persons we'll get that there's $12 \cdot \dots \cdot 12 = 12^n$.   

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

As $n$ becomes large, what fraction of n people has selected a black pawn? Choose the answer that's closest to the actual fraction.

( ) 1/32
( ) 1/12
( ) 1/4
( ) 1/2
( ) None of the above.

# BEGIN SOLUTION

$\frac{1}{4}$

First, let's calculate the probability of one person choosing a black pawn. We know that the complete chess set has 32 pieces, and out of those 32 there are 8 black pawns, which gives us a probability of $\frac{8}{32} = \frac{1}{4}$ of selecting a black pawn. Now, think about how we interpret probabilities; for example, if we say that the probability of getting heads when flipping a coin is $\frac{1}{2}$ that just means that if we flip a coin over and over, we expect to see heads $\frac{1}{2}$ of the time. Similarly, when we say that the probability of choosing a black pawn is $\frac{1}{4}$, that means that if we were to <u>choose a chess piece over and over</u>, we expect to choose a black pawn $\frac{1}{4}$ of the time. 

As $n$ becomes large, we <u>choose chess pieces over and over $n$ times</u>. Therefore, you still expect to see the black pawn $\frac{1}{4}$ of the time.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

True or False: Having two pawns is **independent** of having two white pieces.

( ) True
( ) False

# BEGIN SOLUTION

False.

We know that two probabilities are independent of each other if $P(A \cap B) = P(A) \cdot P(B)$.

- Let $P(A)$ be the probability of getting a white piece twice in a row.
- Let $P(B)$ be the probability of getting a pawn twice in a row.

We can calculate the probability of getting a white piece twice in a row $P(A) = \frac{16}{32} \cdot \frac{15}{31} = \frac{15}{62}$. We get $\frac{16}{32}$ from the fact there are $16$ white pieces out of the $32$ total pieces. We get $\frac{15}{31}$ from the fact there are now $15$ white pieces out of the $31$ pieces left after taking out a white piece.

We can also calculate the probability of getting a pawn twice in a row. Note that the color of the pawn does not matter! $P(B) = \frac{16}{32} \cdot \frac{15}{31} = \frac{15}{62}$. We get $\frac{16}{32}$ from the fact there are $16$ pawns ($8$ black pawns plus $8$ white pawns) out of the $32$ total pieces. We get $\frac{15}{31}$ from the fact there are now $15$ pawns out of the $31$ pieces left after taking out a pawn.

We can now calculate $P(A) \cdot P(B)$:
$$
\frac{15}{62} \cdot \frac{15}{62} = \frac{225}{3844}
$$

Recall we calculate $P(A \cap B) = P(A) \cdot P(B|A)$.

To find $P(B|A)$, we assume that both pieces are white and imagine the probabilities of getting two pawns from that batch of white pieces. To get the first pawn, the probability is $\frac{8}{16}$ (8 pawns out of 16 white pieces). To get the second pawn, the probability is: $\frac{7}{15}$ (7 remaining pawns out of 15 remaining white pieces). So, the probabilitiy of getting two pawns given we have two white pieces is $P(B|A) = \frac{8}{16} \cdot \frac{7}{15} = \frac{7}{30}$. We also already solved for $P(A)$ above: $\frac{15}{62}$.

$$
\frac{15}{62} \cdot \frac{7}{30} = \frac{7}{124}
$$

We can see that $P(A \cap B) \neq P(A) \cdot P(B)$ because $\frac{7}{124} \neq \frac{225}{3844}$, so the answer is "False."

# END SOLUTION

# END SUBPROB

# END PROB