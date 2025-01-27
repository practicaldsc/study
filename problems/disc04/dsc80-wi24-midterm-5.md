The DataFrame `dogs`, contains one row for every registered pet dog in Zurich, Switzerland in 2017.

The first few rows of `dogs` are shown below, but `dogs` has many more rows than are shown.

<center><img src="../assets/images/disc04/df.png" width=750></center>

<br>

- `"owner_id" (int)`: A unique ID for each owner. Note that, for example, there are two rows in the preview for `4215`, meaning that owner has at least 2 dogs. **Assume that if an `"owner_id"` appears in `dogs` multiple times, the corresponding `"owner_age"`, `"owner_sex"`, and `"district"` are always the same.**
- `"owner_age" (str)`: The age group of the owner; either `"11-20"`, `"21-30"`, ..., or `"91-100"` (9 possibilities in total).
- `"owner_sex" (str)`: The birth sex of the owner; either `"m"` (male) or `"f"` (female).
- `"district" (int)`: The city district the owner lives in; a positive integer between `1` and `12` (inclusive).
- `"primary_breed" (str)`: The primary breed of the dog.
- `"secondary_breed" (str)`: The secondary breed of the dog. If this column is not null, the dog is a "mixed breed" dog; otherwise, the dog is a "purebred" dog.
- `"dog_sex" (str)`: The birth sex of the dog; either `"m"` (male) or `"f"` (female).
- `"birth_year" (int)`: The birth year of the dog.



# BEGIN PROB

In this question, assume that there are more than 12 districts in `dogs`.

Suppose we merge the `dogs` DataFrame with itself as follows.

```py
# on="x" is the same as specifying both left_on="x" and right_on="x".
double = dogs.merge(dogs, on="district")

# sort_index sorts a Series in increasing order of its index.
square = double["district"].value_counts().value_counts().sort_index()
```

The first few rows of `square` are shown below.

```py
1     5500
4      215
9       40
```

# BEGIN SUBPROB

In `dogs`, there are 12 rows with a `"district"` of `8`. How many rows
of `double` have a `"district"` of `8`? Give your answer as a positive
integer.

# BEGIN SOLUTION

**Answer**: $144$

When we merge `dogs` with `dogs` on `"district"`, each `8` in the first `dogs` DataFrame will be combined with each `8` in the second `dogs` DataFrame. Since there are 12 in the first and 12 in the second, there are $12 \cdot 12 = 144$ combinations.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What does the following expression evaluate to? Give your answer as a
positive integer.

```py
dogs.groupby("district").filter(lambda df: df.shape[0] == 3).shape[0]
```

*Hint: Unlike in 5.1, your answer to 5.2 depends on the values
in `square`.*

# BEGIN SOLUTION

**Answer**: $120$

`square` is telling us that:

- There are 5500 districts that appeared just 1x in `dogs`.
- There are 215 districts that appeared 2x in `dogs` (2x, not 4x, because of the logic explained in the 5a rubric item).
- There are 40 districts that appeared 3x in `dogs`.

The expression given in this question is keeping all of the rows corresponding to districts that appear 3 times. There are 40 districts that appear 3 times. So, the total number of rows in this DataFrame is $40 \cdot 3 = 120$.

# END SOLUTION

# END SUBPROB

# END PROB