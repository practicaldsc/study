# BEGIN PROB

<i>Source: [Spring 2023 Midterm 2](../sp23-midterm2/index.html), Problem 1</i>

A set of chess pieces has $32$ pieces. $16$ of these are black and $16$ of these are white. **In each color**, the $16$ pieces are:

- $8$ pawns,
- $2$ bishops,
- $2$ knights,
- $2$ rooks,
- $1$ queen, and 
- $1$ king.

When there are multiple pieces of a given color and type (for example, $8$ white pawns), we will assume they are **indistinguishable** from one another.

Consider an experiment where each of $n$ people selects one piece from their own set of 32 chess pieces, uniformly at random. The **result** of the experiment is a description of the **colors and types** of the pieces each person selected. For example, if $n=3$, one possible result is:

-   Person 1 selected a white knight.

-   Person 2 selected a black queen.

-   Person 3 selected a black pawn.

How many results are possible for this experiment with $n$ people?

( ) $2^n$
( ) $6^n$
( ) $12^n$
( ) $16^n$
( ) $32^n$
( ) None of the above.

# BEGIN SOLUTION

$12^n$.

The key to solving this problem is the note "When there are multiple pieces of a given color and type (for example, $8$ white pawns), we will assume they are **indistinguishable** from one another." This means we count each type of chess piece for the colors black and white. There are $6$ different types of chess pieces: pawn, bishop, knight, rook, queen, and king. There are $2$ possible colors: black and white. This means there are $6 \cdot 2 = 12$ unique colored types of chess pieces.

There are $12$ options for the first person, there are $12$ options for the second person, and so on, for $n$ people, so we can write:

$$12 \cdot 12 \cdot \dots \cdot 12 = 12^n$$

We see there are $12^n$ possible results for this experiment because there are $n$ people in this experiment who can each select 12 unique combinations.

# END SOLUTION

# END PROB