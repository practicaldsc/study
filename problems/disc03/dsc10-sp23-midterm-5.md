# BEGIN PROB

Kyle and Yutong are trying to decide where they'll study on campus and
start flipping a Michigan-themed coin, with a picture of the Michigan Union
on the heads side and a picture of the Shapiro Undergraduate Library (aka
the UgLi) on the tails side.

<center><img src='../assets/images/disc03/michigan_union.png' width=400></center>
<br>

Kyle flips the coin 21 times and sees 13 heads and 8 tails. He stores
this information in a DataFrame named `kyle` that has 21 rows and 2
columns, such that:

- The `"flips"` column contains `"Heads"` 13 times and `"Tails"` 8
  times.

- The `"Markley"` column contains `"Kyle"` 21 times.

Then, Yutong flips the coin 11 times and sees 4 heads and 7 tails. She
stores this information in a DataFrame named `yutong` that has 11 rows
and 2 columns, such that:

- The `"flips"` column contains `"Heads"` 4 times and `"Tails"` 7
  times.

- The `"MoJo"` column contains `"Yutong"` 11 times.

# BEGIN SUBPROB

How many rows are in the following DataFrame? Give your answer as an
integer.

```py
    kyle.merge(yutong, on="flips")
```

_Hint: The answer is less than 200._

# BEGIN SOLUTION

**Answer**: 108

Since we used the argument `on="flips`, rows from `kyle` and `yutong` will be combined whenever they have matching values in their `"flips"` columns.

For the `kyle` DataFrame:

- There are 13 rows with `"Heads"` in the `"flips"` column.
- There are 8 rows with `"Tails"` in the `"flips"` column.

For the `yutong` DataFrame:

- There are 4 rows with `"Heads"` in the `"flips"` column.
- There are 7 rows with `"Tails"` in the `"flips"` column.

The merged DataFrame will also only have the values `"Heads"` and `"Tails"` in its `"flips"` column.

- The 13 `"Heads"` rows from `kyle` will each pair with the 4 `"Heads"` rows from `yutong`. This results in $13 \cdot 4 = 52$ rows with `"Heads"`
- The 8 `"Tails"` rows from `kyle` will each pair with the 7 `"Tails"` rows from `yutong`. This results in $8 \cdot 7 = 56$ rows with `"Tails"`.

Then, the total number of rows in the merged DataFrame is $52 + 56 = 108$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Let $A$ be your answer to the previous part. Now, suppose that:

- `kyle` contains an additional row, whose `"flips"` value is
  `"Total"` and whose `"Markley"` value is 21.

- `yutong` contains an additional row, whose `"flips"` value is
  `"Total"` and whose `"MoJo"` value is 11.

Suppose we again merge `kyle` and `yutong` on the `"flips"` column. In
terms of $A$, how many rows are in the new merged DataFrame?

( ) $A$
( ) $A+1$
( ) $A+2$
( ) $A+4$
( ) $A+231$

# BEGIN SOLUTION

**Answer**: $A+1$

The additional row in each DataFrame has a unique `"flips"` value of `"Total"`. When we merge on the `"flips"` column, this unique value will only create a single new row in the merged DataFrame, as it pairs the `"Total"` from `kyle` with the `"Total"` from `yutong`. The rest of the rows are the same as in the previous merge, and as such, they will contribute the same number of rows, $A$, to the merged DataFrame. Thus, the total number of rows in the new merged DataFrame will be $A$ (from the original matching rows) plus 1 (from the new `"Total"` rows), which sums up to $A+1$.

# END SOLUTION

# END SUBPROB

# END PROB
