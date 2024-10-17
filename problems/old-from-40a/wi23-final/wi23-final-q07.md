# BEGIN PROB

<!-- **Probability and Counting** -->

<i>Source: [Winter 2023 Final](../wi23-final/index.html), Problem 7</i>

# BEGIN SUBPROB

There is one box of bolts that contains some long and some
short bolts. A manager is unable to open the box at present, so she asks
her employees what is the composition of the box. One employee says that
it contains 60 long bolts and 40 short bolts. Another says that it
contains 10 long bolts and 20 short bolts. Unable to reconcile these
opinions, the manager decides that each of the employees is correct with
probability $\frac{1}{2}$. Let $B_1$ be the event that the box contains 60 long
and 40 short bolts, and let $B_2$ be the event that the box contains 10
long and 20 short bolts. What is the probability that the first bolt
selected is long?

# BEGIN SOLUTION 

$$P(\text{long}) = \frac{7}{15}$$

We are given that:
$$P(B_1)=P(B_2)=\frac{1}{2}$$ $$P(\text{long}|B_1) = \frac{60}{60 + 40} = \frac{3}{5}$$ $$P(\text{long}|B_2) = \frac{10}{10 + 20} = \frac{1}{3}$$

Using the law of total probability:

$$P(\text{long})=P(\text{long}|B_1) \cdot P(B_1)+P(\text{long}|B_2) \cdot P(B_2)
= \frac{3}{5} \cdot \frac{1}{2} + \frac{1}{3} \cdot \frac{1}{2} = \frac{7}{15}$$

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

How many ways can one arrange the letters $A$, $B$, $C$, $D$, $E$ such
that $A$, $B$, and $C$ are all together (in any order)?

# BEGIN SOLUTION

There are $3! \cdot 3!$ permutations.


We can treat the group of $A$, $B$, and $C$ (in any order) as a single block of letters which we can call $X$. This will gurantee that any permutation we find will satisfy our condition of having $A$, $B$, and $C$ being all together.

Our problem now has $3! = 6$ permutations of our new letter bank: $X$, $D$, and $E$.

$$XDE$$
$$XED$$
$$DXE$$
$$EXD$$
$$DEX$$
$$EDX$$

Let's call these 6 permutations "structures". For each of these structures, there are $3! = 6$ rearrangements of the letters $A$, $B$, and $C$ *inside* of $X$.

So, with $3!$ different arrangements of $D$, $E$ and our block of letters ($X$), and with each of those arrangements individually having $3!$ ways to re-order the group of $ABC$, the overall number of permutations of $ABCDE$ where $ABC$ are all together, in any order, is $3! \cdot 3!$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Two chess players $A$ and $B$ play a series of chess matches
against each other until one of them wins 3 matches. Every match ends
when one of the players *wins* against the other, that is, the game does not ever
end in draw/tie. For example, one series of matches ends when the outcomes of the
first four games are: $A$ wins, $A$ wins, $B$ wins, $A$ wins. In how many different ways can
the series occur?

# BEGIN SOLUTION

There are $20$ ways the series can be won.

The series ends when the last game in the series is the third win by
either player. Overall, there must be at least 3 games to end a series (all wins by the same player) and at most 5 games to end a series (each player has two wins, and then a final win by either player) before either player wins 3 games. Let's assume player $A$ always wins, and then we'll multiply the number of options by two to account for the possibilities where player $B$ wins instead.

Breaking it down:

-   For a series that ends in 3 games - there is a single option (all wins by player $A$).

-   For a series that ends in 4 games, we've assumed the last game is a player $A$ win to end the series, therefore the 3 preceding games have ${3 \choose 2}$ options for player $A$ winning 2 of the 3 preceding games.

-   For a series that ends in 5 games, we've assumed the last game is a player $A$ win to end the series, therefore the 4 preceding games have ${4 \choose 2}$ options for player $A$ winning 2 of the 4 preceding games.

Overall, the number of ways the series can occur is: $2 \cdot (1 + {3 \choose 2} + {4 \choose 2}) = 20$

# END SOLUTION

# END SUBPROB

# END PROB