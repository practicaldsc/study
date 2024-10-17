# BEGIN PROB

<i>Source: [Winter 2022 Midterm 2](../wi22-midterm2/index.html), Problem 7</i>

Recall in the game Stringle, players try to guess a randomly generated string. There is a new Stringle string available each day.

Each day's Stringle string is a **six-letter string**, where each letter is chosen uniformly at random, **with replacement**, from among the 26 letters of the English alphabet. This means Stringle strings can have repeated letters, and they do not need to have any meaning as an English word.

For this problem, we'll say that there are six vowels: A, E, I, O, U, and Y. Consider the following three events:

-   $A$ is the event that today's Stringle string starts with a vowel.

-   $B$ is the event that today's Stringle string starts with a letter in the first half of the alphabet (A through M, inclusive).

-   $C$ is the event that today's Stringle string does not start with a Z.

Which of the following is true?

( ) $A$ and $B$ are independent. $A$ and $B$ are conditionally
independent given $C$.\
( ) $A$ and $B$ are independent. $A$ and $B$ are conditionally dependent
given $C$.\
( ) $A$ and $B$ are dependent. $A$ and $B$ are conditionally independent
given $C$.\
( ) $A$ and $B$ are dependent. $A$ and $B$ are conditionally dependent
given $C$.\
( ) None of the above.

# BEGIN SOLUTION

Bubble 1: $A$ and $B$ are independent. $A$ and $B$ are conditionally dependent given $C$.

We can test if $A$ and $B$ are independent by using the equation: $\mathbb{P}(A \cap B) = \mathbb{P}(A) \cdot \mathbb{P}(B)$.

- We know $\mathbb{P}(A) = \frac{6}{26}$ because there are six vowels the Stringle string can start with out of $26$ letters in the alphabet.
- We know $\mathbb{P}(B) = \frac{13}{26} = \frac{1}{2}$ because the letters A through M is numbered $1$ to $13$, so there are $13$ possible letters out of $26$.
- We know $\mathbb{P}(A \cap B) = \frac{3}{26}$ because the letters A, E, and I are between A and M and are also vowels out of all $26$ letters.

When plugging these values into the equation we get:
$$
\begin{align*}
\mathbb{P}(A \cap B) &= \mathbb{P}(A) \cdot \mathbb{P}(B) \\
\frac{3}{26} &= \frac{6}{26} \cdot \frac{1}{2} \\
\frac{3}{26} &= \frac{3}{26}
\end{align*}
$$

This proves that $A$ and $B$ are independent.

Recall we can test if something is conditionally independent by doing $\mathbb{P}(A \cap B|C) = \mathbb{P}(A|C) \cdot \mathbb{P}(B|C)$.

- We know there are $25$ letters in the alphabet that are not equal to Z.
- We can calculate $\mathbb{P}(A|C) = \frac{6}{25}$ because there are six vowels out of the $25$ non-Z letters.
- We can calculate $\mathbb{P}(B|C) = \frac{13}{25}$ because there are $13$ letters out of the $25$ non-Z letters.
- We can calculate $\mathbb{P}(A \cap B|C) = \frac{3}{25}$ because the letters A, E, and I are between A and M and are also vowels out of $25$ non-Z letters.

When plugging these values into the equation we get:
$$
\begin{align*}
\mathbb{P}(A \cap B|C) &= \mathbb{P}(A|C) \cdot \mathbb{P}(B|C) \\
\frac{3}{25} &= \frac{6}{25} \cdot \frac{13}{25} \\
\frac{3}{25} &\neq \frac{78}{625}
\end{align*}
$$

Since $\mathbb{P}(A \cap B|C) \neq \mathbb{P}(A|C) \cdot \mathbb{P}(B|C)$ this means that $A$ and $B$ are conditionally dependent given $C$.

# END SOLUTION

# END PROB