# BEGIN PROB

<i>Source: [Spring 2023 Final Part 2](../sp23-final-pt2/index.html), Problem 3</i>

Consider three events $A, B,$ and $C$ in the same sample space.

# BEGIN SUBPROB

Which of the following is equivalent to
$P((A\cap B)|(B \cap C))$? **Select all that apply.**

[ ] $P(A|(B \cap C))$
[ ] $P(A \cap B \cap C)$
[ ] $P((B \cap C)|(A \cap B))$
[ ] $P((A \cap C)|(B \cap C))$
[ ] None of the above.

# BEGIN SOLUTION

$P(A|(B \cap C))$ and $P((A \cap C)|(B \cap C))$

Recall the formula for conditional probability is $P(A|B) = \frac{P(A \cap B)}{P(B)}$. We are going to use this fact to figure out which of the following are the same as $P((A\cap B)|(B \cap C))$.

We should first expand $P((A\cap B)|(B \cap C))$ by doing: $P((A\cap B)|(B \cap C)) = \frac{P(A \cap B) \cap P(B \cap C)}{P(B \cap C)}$. We can further simplify the numerator to be $(A \cap B) \cap (B \cap C) \rightarrow A \cap B \cap C$. This means we get $P((A\cap B)|(B \cap C))$ by doing: $P((A\cap B)|(B \cap C)) = \frac{P(A \cap B \cap C)}{P(B \cap C)}$.

Now we can go through each of the options and figure out if, when put inside the formula for conditional probability, we get $\frac{P(A \cap B \cap C)}{P(B \cap C)}$.

<br>

$P(A|(B \cap C))$
$$P(A|(B \cap C)) = \frac{P(A)P(B \cap C)}{P(B \cap C)}= \frac{P(A \cap (B \cap C))}{P(B \cap C)} = \frac{P(A \cap B \cap C)}{P(B \cap C)}$$ This matches $\frac{P(A \cap B \cap C)}{P(B \cap C)}$!

<br>

$P(A \cap B \cap C)$

We can see that there is no way for this to equal $\frac{P(A \cap B \cap C)}{P(B \cap C)}$ because it is missing the denominator.

<br>
$P((B \cap C)|(A \cap B))$

$$P((B \cap C)|(A \cap B)) = \frac{P(B \cap C)P(A \cap B)}{P(A \cap B)}= \frac{P(A \cap B \cap C)}{P(A \cap B)}$$ This does not match $\frac{P(A \cap B \cap C)}{P(B \cap C)}$.

<br>

$P((A \cap C)|(B \cap C))$
$$P((A \cap C)|(B \cap C)) = \frac{P(A \cap C)P(B \cap C)}{P(B \cap C)} = \frac{P(A \cap B \cap C)}{P(B \cap C)}$$ This matches $\frac{P(A \cap B \cap C)}{P(B \cap C)}$!

<br>
Since options 1 and 4 are correct the answer cannot be None of the Above!

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose $P((A \cap B)|C) = P(A|(B \cap C))*P(B)$. Which of the following pairs of events **must be independent**?

( ) $A, B$
( ) $A, C$
( ) $B, C$
( ) None of the above.

# BEGIN SOLUTION

$B, C$

We are going to rewrite the following in the hopes of being able to simplify things later. To do this we will once again use the formula for conditional probability: $P(A|B) = \frac{P(A \cap B)}{P(B)}$

Let's look at the left side of $P((A \cap B)|C) = P(A|(B \cap C))*P(B)$.

$$P((A \cap B)|C) = \frac{P(A \cap B)P(C)}{P(C)} = \frac{P(A \cap B \cap C)}{P(C)}$$

Let's now look at the right side of $P((A \cap B)|C) = P(A|(B \cap C))*P(B)$.

$$P(A|(B \cap C))*P(B) = \frac{P(A)P(B \cap C)}{P(B \cap C)} * P(B) = \frac{P(A \cap B \cap C)}{P(B \cap C)}* P(B) = \frac{P(A \cap B \cap C) * P(B)}{P(B \cap C)}$$

Now we can look at them together! $\frac{P(A \cap B \cap C)}{P(C)} = \frac{P(A \cap B \cap C) * P(B)}{P(B \cap C)}$. We can cross multiply to clear the fractions: $P(A \cap B \cap C) * P(B \cap C) = P(A \cap B \cap C) * P(B) * P(C)$. Assuming that $P(A \cap B \cap C) \neq 0$ we can divide both sides by $P(A \cap B \cap C)$. We end up with $P(B \cap C) = P(B) * P(C)$, which demonstrates to us that $B$ and $C$ are independent of one another.

# END SOLUTION

# END SUBPROB

# END PROB