# BEGIN PROB

<i>Source: [Winter 2022 Midterm 2](../wi22-midterm2/index.html), Problem 13</i>

Suppose you apply $k$-means clustering to the data in your
family's Stringle score spreadsheet by representing the entries in each
column of the spreadsheet as a vector in $\mathbb{R}^5$. If we run the
algorithm with $k=2$, which of the following is the best description of
what the clusters represent?

( ) One cluster represents the Stringle strings that were easier to guess, and the other represents the Stringle strings that were harder to guess.
( ) One cluster represents the family members who are better Stringle players, and the other represents the family members who not as good.
( ) One cluster represents the Stringle strings that had duplicated letters, and the other represents the Stringle strings that had distinct letters.
( ) One cluster represents the family members who play Stringle more often, and the other represents the family members who do not play as often.

# BEGIN SOLUTION

Bubble 1: One cluster represents the Stringle strings that were easier to guess, and the other represents the Stringle strings that were harder to guess.

The first option is correct. Recall our data is based on Stringle strings, so if they were easier or harder to guess they might cluster together based on the family member's scores.

The second option is incorrect because our data does not represent family members. This means we cannot make an assumption based on an individual player's skills.

The third option is incorrect, but plausible because it would more likely contribute to the first option than being correct on it's own. It is possible having duplicated letters or distinct letters play into how easy or hard a Stringle string was to guess.

For similar reasons to the second option the fourth option cannot be true. The data represents Stringle strings and not the frequency of play for family members.

# END SOLUTION

# END PROB