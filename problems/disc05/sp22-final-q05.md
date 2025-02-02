# BEGIN PROB

The DataFrame `random_10` contains the `"track_name"` and `"genre"` of
10 randomly-chosen songs in Spotify's Top 200 today, along with their
`"genre_rank"`, which is their rank in the Top 200 **among songs in
their `"genre"`**. For instance, "the real slim shady\" is the
20th-ranked Hip-Hop/Rap song in the Top 200 today. `random_10` is shown
below in its entirety.

<center><img src='../assets/images/disc05/imp-with-nan.png' width=35%></center>

The `"genre_rank"` column of `random_10` contains missing values. Below,
we provide four different imputed `"genre_rank"` columns, each of which
was created using a different imputation technique. On the next page,
match each of the four options to the imputation technique that was used
in the option.

<center><img src='../assets/images/disc05/imp-options-grid.png' width=80%></center>

Note that each option (A, B, C, D) should be used exactly once between
parts (a) and (d).

# BEGIN SUBPROB

In which option was unconditional mean imputation used?

# BEGIN SOLN

**Answer: ** Option B

Explanation given in part d) below

<average>99</average>

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

In which option was mean imputation conditional on `"genre"`
used?

# BEGIN SOLN

**Answer: ** Option D

Explanation given in part d) below

<average>96</average>

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

In which option was unconditional probabilistic imputation
used?

# BEGIN SOLN

**Answer: ** Option C

Explanation given in part d) below

<average>92</average>

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

In which option was probabilistic imputation conditional on
`"genre"` used?

# BEGIN SOLN

**Answer: ** Option A

-   First, note that in Option B, all three missing values are filled in
    with the same number, 7. The mean of the observed values in
    `random_10["genre rank"]` is 7, so we must have performed
    unconditional mean imputation in Option B. (Technically, it's
    possible for Option B to be the result of unconditional
    probabilistic imputation, but we stated that each option could only
    be used once, and there is another option that can only be
    unconditional probabilistic imputation.)

-   Then note that in Option C, the very last missing value (in the
    `"Pop"` `"genre"`) is filled in with a 7, which is not the mean of
    the observed `"Pop"` values, but rather a value from the
    `"Alternative"` `"genre"`. This must mean that unconditional
    probabilistic imputation was used in Option C, since that's the only
    way a value from a different group can be used for imputation (if we
    are not performing some sort of mean imputation).

-   This leaves Option A and Option D. The last two missing values (the
    two in the `"Pop"` `"genre"`) are both filled in with the same
    value, 2 in Option A and 5 in Option D. The mean of the observed
    values for the `"Pop"` `"genre"` is $\frac{9+2+4}{3} = 5$, so mean
    imputation conditional on `"genre"` must have been used in Option D
    and thus probabilistic imputation conditional on `"genre"` must have
    been used in Option A.

<average>92</average>

# END SOLN

# END SUBPROB

In parts (e) and (f), suppose we want to run a permutation test to
determine whether the missingness of `"genre rank"` depends on
`"genre"`.

# END PROB