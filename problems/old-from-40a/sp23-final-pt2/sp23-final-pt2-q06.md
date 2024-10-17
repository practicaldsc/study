# BEGIN PROB

<i>Source: [Spring 2023 Final Part 2](../sp23-final-pt2/index.html), Problem 6</i>

Suppose UCSD implements a new graduation requirement for
data science majors. All data science majors must submit a list of
English words they can make using the letters of "Halicioglu". When
these lists are collected, it is determined that:

-   $200$ people included the word "hall" on their list.
-   $100$ people included the word "chill" on their list.
-   $25$ people included the word "logical" on their list.
-   $60$ people did not include any of "hall", "chill", or "logical" on
    their list.
-   $80$ people included both "hall" and "chill" on their list.
-   $15$ people included both "chill" and "logical" on their list.
-   $20$ people included both "hall" and "logical" on their list.
-   $10$ people included all three of "hall", "chill", and "logical" on
    their list.

How many data science majors submitted a list?

# BEGIN SOLUTION

$280$

This problem requires us to the the principle of inclusion-exclusion for three sets. For this problem lets define the following sets:

- Let $H$ be the set of people who included "hall" on their list
- Let $C$ be the set of people who included "chill" on their list
- Let $L$ be the set of people who included "logical" on their list

We are told:

- $|H| = 200$
- $|C| = 100$
- $|L| = 25$
- $|H \cap C| = 80$
- $|C \cap L| = 15$
- $|H \cap L| = 20$
- $|H \cap C \cap L| = 10$
- $|H' \cap C' \cap L'| = 60$
    - $H'$ means "not $H$"

Recall the principle of inclusion-exclusion for three sets follows: $$|H \cup C \cup L| = |H| + |C| + |L| - |H \cap C| - |C \cap L| - |H \cap L| + |H \cap C \cap L|$$

We can simply plug and chug into the equation: $|H \cup C \cup L| = 200 + 100 + 25 - 80 - 15 - 20 + 10 = 220$. This means the number of data science majors who submited words "hall, "chill," and "logical" is 220. But this is not all data science majors!

We need to add in the number of data science majors who did not submit any of those words in their list, which we are told is $60$ students. This means the number of data science majors is $220  + 60 = 280$.

# END SOLUTION

# END PROB