# BEGIN PROB

<i>Source: [Winter 2022 Midterm 2](../wi22-midterm2/index.html), Problem 2</i>

Suppose that every day, the Stringle string is chosen without replacement from among the set of all possible valid strings. What is the probability that DSCTEN was the Stringle string for one of the first 100 days after the game's release?

# BEGIN SOLUTION

$$
\dfrac{100}{26^6} = 100\cdot \dfrac{P(26^6-1, 99)}{P(26^6, 100)} = 1 - \dfrac{P(26^6- 1, 100)}{P(26^6, 100)}
$$

Whenever you are thrying to calculated the probability of something happening **at least once** over a series of repeated trials, it is a very good idea to consider the **complement rule** because in most cases calculating the probability of something never happening is easier.

Knowing that, let's calculate the probability of not getting the string DSCTEN in any of the days.  Well, the first part would be figuiring out how many possible strings exists, since there's $26$ letters on the English alphabet, it should be clear that the total number of strings is $26^6$, now the number of ways we can choose 100 of them withouth chossing DSCTEN is ${26^6-1 \choose 100}$, and therefore the probability of DSCTEN not being in our selection of 100 strings is $\frac{26^6-1 \choose 100}{26^6 \choose 100}$. Notice that in this I'm thinking in terms of combinations, but it would be equally valid to think in therms of permutations, and in that case we would do the number of permutations wihtout the string DSCTEN over the total number of permutations ($\dfrac{P(26^6- 1, 100)}{P(26^6, 100)}$).

Now we only need to use the complement rule, and we'll get that the answer is $1 - \frac{26^6-1 \choose 100}{26^6 \choose 100} = 1 - \dfrac{P(26^6- 1, 100)}{P(26^6, 100)}$

**Note: P stands for permutation in this problem**

# END SOLUTION

# END PROB