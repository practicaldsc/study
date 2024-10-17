# BEGIN PROB

<i>Source: [Spring 2023 Midterm 2](../sp23-midterm2/index.html), Problem 4</i>

Suppose that there are three possible experience levels
in chess (beginner, intermediate, advanced). Only **10%** of beginner
players beat Avi at a game of chess, while **50%** of intermediate
players and **80%** of advanced players do.

Avi signs up to participate in a certain chess tournament called the
Avocado Cup. Aside from Avi, **50%** of the players in the tournament
are beginners, **40%** are intermediate, and **10%** are advanced.

The tournament proceeds in rounds. In the first round of the tournament,
players are **randomly paired up** for a game of chess.

# BEGIN SUBPROB

What is the probability that Avi wins in the first round of
the tournament?

( ) $33 \%$
( ) $50 \%$
( ) $67 \%$
( ) $83 \%$
( ) None of the above.

# BEGIN SOLUTION

$67 \%$

We know the percentages of players that beat Avi (meaning Avi loses) and the percentages of different types of players inside the Avocado Cup.

We can use the percentage of players that beat Avi to figure out the percentage of times Avi wins by writing $1 - p$.

Avi wins against beginners with a likelihood of $1 - 0.1 = 0.9$, against intermediate players with a likelihood of $1 - 0.4 = 0.6$, and against advanced players with a likelihood of $1 - 0.8 = 0.2$.

Now we can multiply the probabilities of Avi winning with their respective probabilities of different players' types to find the probability Avi that will win in the first round! We can do this because you can imagine we are multiplying the probability Avi wins with the amount of people in the tournament of that level.

$$\begin{align*}
0.9 \cdot 0.5 &= 0.45 \\
0.4 \cdot 0.5 &= 0.2 \\
0.2 \cdot 0.1 &= 0.02 \\
0.45 + 0.2 + 0.02 &= 0.67
\end{align*}$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

It turns out that, sadly, Avi loses to his opponent in the
first round. What is the probability that Avi's opponent is an advanced
player? Choose the **closest answer** among the choices listed.

( ) $15 \%$
( ) $25 \%$
( ) $35 \%$
( ) $45 \%$

# BEGIN SOLUTION

$25 \%$

- Let $P(A)$ be the probability of Avi playing against an advanced player
- Let $P(B)$ be the probability of Avi losing a match
- Let $P(C)$ be the probability of Avi playing against an intermediate player
- Let $P(D)$ be the probability of Avi playing against a beginner player

We can use Bayes' theorem to help us find the probability that Avi lost the match to an advanced player ($P(A|B)$). Recall Bayes' theorem is:

$$
P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
$$

We are given the probability that Avi loses the match against an advanced player $P(B|A) = 0.8$ and the probability of Avi playing against an advanced player $P(A) = 0.1$.

We can calculate the probability of Avi losing a match $P(B)$ with the law of total probability:
$$
P(B) = P(B|A) \cdot P(A) + P(B|C) \cdot P(C) + P(B|D) \cdot P(D)
$$

We know the probability of Avi losing to an intermediate player: $P(B|C) = 0.5$, the probability of Avi losing to a beginner player: $P(B|D) = 0.1$, the probability of an intermediate player being the opponent: $P(C) = 0.4$, and the probability of a beginner player being the opponent: $P(D) = 0.5$

Plugging in what we know into the law of total probability equation we get:
$$\begin{align*}
P(B) &= 0.8 \cdot 0.2 + 0.5 \cdot 0.4 + 0.1 \cdot 0.5 \\
&=0.08 + 0.2 + 0.05 \\
&= 0.33
\end{align*}$$

Or we can calculate $P(B)$ by using what we know in part A ($67 \%$). $1 - 0.67 = 0.33$.

Back to Bayes' theorem we have:
$$\begin{align*}
P(A|B) &= \frac{0.8 \cdot 0.1}{0.33} \\
&= \frac{0.08}{0.33}\\
&= 0.24
\end{align*}$$

$0.24$ is closest to $0.25$, so $25 \%$.

# END SOLUTION

# END SUBPROB

# END PROB