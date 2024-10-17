# BEGIN PROB

<i>Source: [Spring 2024 Final](../sp24-final/index.html), Problem 8</i>

Delta has released a line of trading cards. Each trading card has a
picture of a plane and a color. There are 12 plane types, and for each
plane type there are three possible colors (gold, silver, and platinum),
meaning there are 36 trading cards total.

Now, suppose that each time you board a flight, a pilot hands you 1 card
drawn at random from the set of possible cards. You fly 9 times, which
gives you **9** cards drawn at random **with replacement** from the set
of possible cards.

In this question, you may leave your answers unsimplified, in terms of
fractions, exponents, the permutation formula $P(n, k)$, and the
binomial coefficient ${n \choose k}$.

# BEGIN SUBPROB

Given that you receive a gold-colored card at least once, what is the
probability that you receive a gold-colored card exactly 5 times? Show
your work, and put a $\boxed{\text{box}}$ around your final answer.


# BEGIN SOLUTION

$\displaystyle\frac{{9 \choose 5} \left( \frac{1}{3} \right)^5 \left( \frac{2}{3} \right)^4}{1 - \left( \frac{2}{3} \right)^9}$. Anything equivalent to this answer received full credit.

This boils down to recognizing that $P(\text{exactly 5 gold cards | at least one gold card}) = \frac{P(\text{exactly 5 gold cards})}{P(\text{at least one gold card})}$, then breaking down the numerator and denominator.

The numerator, $P(\text{exactly 5 gold cards})$, is equal to ${9 \choose 5} \left( \frac{1}{3} \right)^5 \left( \frac{2}{3} \right)^4$.

The denominator, $P(\text{at least one gold card})$, is equal to $1 - P(\text{no gold cards}) = 1 - \left( \frac{2}{3} \right)^9$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The *Airbus A350*, the *Boeing 767*, and the *Airbus A330* are 3 of the
12 plane types that Delta made trading cards for.

What is the probability that you receive 2 *Airbus A350* cards, 4
*Boeing 767* cards, and 3 *Airbus A330* cards? Show your work, and put a
$\boxed{\text{box}}$ around your final answer.


# BEGIN SOLUTION

$\displaystyle\frac{9!}{2!4!3!} (\frac{1}{12})^9$. Anything equivalent to this answer received full credit, such as ${9 \choose 4}{5 \choose 2}{3 \choose 3} (\frac{1}{12})^9 $ or ${9 \choose 3}{6 \choose 4} (\frac{1}{12})^9$.

On one individual draw, the probability of receiving one particular plane type is $\frac{3}{36} = \frac{1}{12}$, so the probability of seeing a particular sequence of 9 plane types – like A350, B767, A330, A330, B767, A350, A330, B767, B767 – is $(\frac{1}{12})^9$.

But, we need to account for the number of ways we can arrange 2 A350, 4 B767, and 3 A330 cards, which is $\frac{9!}{2!4!3!} = {9 \choose 2} {7 \choose 4}{3 \choose 3}$ (which can also be expressed a few other ways, too).

# END SOLUTION

# END SUBPROB

# END PROB