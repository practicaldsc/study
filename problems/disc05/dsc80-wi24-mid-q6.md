# BEGIN PROB

Suppose we have a DataFrame, `dogs`, in which each row corresponds to a different dog owned by someone in Ann Arbor. There are several columns in the DataFrame, including `"birth_year"` (the dog's year of birth) and `"Breed"` (the dog's breed).

Using the `"birth_year"` column in `dogs`, Tahseen computes the age of
each dog and stores it a new `"age"` column of `dogs`. He also
categorizes dogs into three "breed classes" based on their breed – `"Retriever"`, `"Terrier"`, or `"Other"` – and stores these
in a new `"class"` column of `dogs`.

The following bar chart shows the distribution of breed classes by
missingness of age:

<center><img src="../../assets/images/disc05/dist-missingness.png" width=400></center>

The following bar chart shows the mean observed
age for each breed class:

<center><img src="../../assets/images/disc05/mean-ages.png" width=400></center>


# BEGIN SUBPROB

Let $O$ be the mean of the observed ages in `dogs`, that is, the mean of
the ages that aren't missing. Let $T$ be the true mean of the ages in
`dogs`, that is, the mean we'd compute if none of the ages were missing.

What is the relationship between $O$ and $T$?

( ) $O < T$
( ) $O \approx T$
( ) $O = T$
( ) $O > T$

# BEGIN SOLUTION

**Answer**: $O < T$

In the ages we get to observe (that is, when age is not missing), we have way fewer terrier values than in the ages we don't get to observe. Terriers are older on average than the other breed classes. This means we're missing values that are larger, so when we take the average of the values we have access to, it'll be lower than the true mean.

# END SOLUTION

# END SUBPROB

Consider the following strategy for imputing missing ages.

```py
def fill_missing(dogs):
  return dogs.assign(
    age=dogs.groupby("class")["age"]
            .transform(lambda x: x.fillna(x.value_counts().idxmax()))
  )
```

# BEGIN SUBPROB

In one sentence, describe this imputation strategy.

# BEGIN SOLUTION

**Answer**: This is filling in missing ages in each breed class with the most common observed age in that breed class.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

`small_dogs` is a subset of `dogs` shown in its entirety below.

<center><img src="../../assets/images/disc05/with-miss.png" width=200></center>

If we call `fill_missing` on `small_dogs`, what values would the four
null values in the `"age"` column of `small_dogs` be replaced with?

- row 2: ___
- row 3: ___
- row 4: ___
- row 7: ___

# BEGIN SOLUTION

**Answer**:

- row 2: 5. The most common observed age for the `"Other"` breed class is 5.
- row 3: 5. The most common observed age for the `"Other"` breed class is 5.
- row 4: 12. The most common observed age for the `"Terrier"` breed class is 12.
- row 7: 7. The most common observed age for the `"Retriever"` breed class is 7.

# END SOLUTION

# END SUBPROB

# END PROB