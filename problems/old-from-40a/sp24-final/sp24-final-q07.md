# BEGIN PROB

<i>Source: [Spring 2024 Final](../sp24-final/index.html), Problem 7</i>

Delta has released a line of trading cards. Each trading card has a
picture of a plane and a color. There are 12 plane types, and for each
plane type there are three possible colors (gold, silver, and platinum),
meaning there are 36 trading cards total.

After your next flight, a pilot hands you a set of **6** cards, drawn at
random **without replacement** from the set of 36 possible cards. The
order of cards in a set does not matter.

In this question, you may leave your answers unsimplified, in terms of
fractions, exponents, the permutation formula $P(n, k)$, and the
binomial coefficient ${n \choose k}$.

# BEGIN SUBPROB

How many sets of 6 cards are there in total?

# BEGIN SOLUTION

${36 \choose 6} = \frac{36!}{6!30!} = \frac{36 \cdot 35 \cdot 34 \cdot 33 \cdot 32 \cdot 31}{6!} = \frac{P(36, 6)}{6!}$. Any of these answers, or anything equivalent to them, are correct.

There are 36 cards, and we must choose of 6 of them at random without replacement such that order matters.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

How many sets of 6 cards have exactly 6 unique plane types?

# BEGIN SOLUTION

${12 \choose 6} \cdot 3^6$. Anything equivalent to this answer is also correct.

Since we're asking for the number of hands with unique types, we first pick 6 different types, which can be done ${12 \choose 6}$ ways. Then, for each chosen type, there are ${3 \choose 1} = 3$ ways of selecting the color. So, the colors can be chosen in $3 \cdot 3 \cdot ... \cdot 3 = 3^6$ ways.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

How many sets of 6 cards have exactly 2 unique plane types?

# BEGIN SOLUTION

${12 \choose 2} = 66$. Anything equivalent to this answer is also correct.

Once we pick 2 unique plane types, we need to choose 3 different colors per type, out of a set of 3 possibilities. This can be done, for each type, in ${3 \choose 3} = 1$ way.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

How many sets of 6 cards have exactly 3 unique plane types, such that
each plane type appears twice?


# BEGIN SOLUTION

${12 \choose 3} \cdot  {3 \choose 2}^3 = {12 \choose 3} 3^3$. Anything equivalent to this answer is also correct.

First, we choose 3 distinct types, which can be done in $${12 \choose 3}$ ways. Then, for each type, we choose 2 colors, which can be done in ${3 \choose 2}$ ways per type.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

How many sets of 6 cards have exactly 3 unique plane types? 

*Hint: You'll need to consider multiple cases, one of which you
addressed in part (d).*

# BEGIN SOLUTION

${12 \choose 3} \cdot {3 \choose 2}^3 + {12 \choose 1}{11 \choose 1}{3 \choose 2}{10 \choose 1}{3 \choose 1}$. Anything equivalent to this answer is also correct.

If we select 6 cards and end up with 3 unique plane types, there are two possibilities:
- We get 2 of each type (e.g. xx yy zz). This is the case in part (d), so the total number of sets of 6 cards that fall here are ${12 \choose 3} \cdot {3 \choose 2}^3$.
- We get 3 of one type, 2 of another, and 1 of the last one (e.g. xxx yy z).
  - xxx: There are 12 options for the type that appears 3 times, so that can be selected in ${12 \choose 1}$ ways. We must take all 3 of that types colors, which can be done in ${3 \choose 3} = 1$ way.
  - yy: There are now 11 options for the type that appears 2 times, and for that type, we must take 2 of its three colors, so there are ${11 \choose 1}{3 \choose 2}$ options.
  - z: There are now 10 options for the type that appears once, and for that type, we must take 1 of its three colors, so there are ${10 \choose 1}{3 \choose 1}$ options.
  - So, the total number of options for this case is ${12 \choose 1}{11 \choose 1}{3 \choose 2}{10 \choose 1}{3 \choose 1} = P(12, 3) 3^2 = {12 \choose 3} 3^3 \cdot 2$.

So, the total number of options is ${12 \choose 3} \cdot {3 \choose 2}^3 + {12 \choose 1}{11 \choose 1}{3 \choose 2}{10 \choose 1}{3 \choose 1}$, which can be simplified in various ways, including to ${12 \choose 3}3^4$. Any of these ways received full credit, as long as they showed all work and logic.

# END SOLUTION

# END SUBPROB

# END PROB