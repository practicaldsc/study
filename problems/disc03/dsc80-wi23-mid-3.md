# BEGIN PROB
In this problem, we will work with the DataFrame `tv`, which contains information about various TV shows available to watch on streaming services. For each TV show, we have:

-  `"Title" (object)`: The title of the TV show.
-  `"Year" (int)`: The year in which the TV show was first released. (For instance, the show _How I Met Your Mother_ ran from 2005 to 2014; there is only one row for _How I Met Your Mother_ in `tv`, and its `"Year"` value is 2005.)
-  `"Age" (object)`: The age category for the TV show. If not missing, `"Age"` is one of `"all"`, `"7+"`, `"13+"`, `"16+"`, or `"18+"`. (For instance, `"all"` means that the show is appropriate for all audiences, while `"18+"} means that the show contains mature content and viewers should be at least 18 years old.)
-  `"IMDb" (float)`: The TV show's rating on IMDb (between 0 and 10).
-  `"Rotten Tomatoes" (int)`: The TV show's rating on Rotten Tomatoes (between 0 and 100).
-  `"Netflix" (int)`: 1 if the show is available for streaming on Netflix and 0 otherwise. The `"Hulu"`, `"Prime Video"`, and `"Disney+"` columns work the same way.

The first few rows of `tv` are shown below (though `tv` has many more rows than are pictured here).

<center><img src='../assets/images/disc03/data-info-wi23-mt.png' width=65%></center>

As you see in the first few rows of `tv`, some TV shows are available
for streaming on multiple streaming services. Fill in the blanks so that
the two expressions below, Expression 1 and Expression 2, **both**
evaluate to the `"Title"` of the TV show that is available for streaming
on the **greatest number of streaming services**. Assume there are no
ties and that the `"Title"` column contains unique values.

Expression 1:

```py
tv.set_index("Title").loc[__(a)__].T.sum(axis=0).idxmax()
```

Expression 2:

```py
    (
        tv.assign(num_services=tv.iloc[__(b)__].sum(__(c)__))
            .sort_values("num_services")
            .iloc[__(d)__]
    )
```

***Hint***: `.T` transposes the rows and columns of a DataFrame --- the
indexes of `df` are the columns of `df.T` and vice versa.

What goes in the blanks?

# BEGIN SOLN
**Answers**: 

- (a) `:, "Netflix":` or some variation of that
- (b) `:, 5:` or some variation of that
- (c) `axis=1`
- (d) `-1, 0`

In Expression 1, keep in mind that `idxmax()` is a Series method returns the index of the row with the maximum value. As such, we can infer that Expression 1 sums the service-specific indicator columns (that is, the columns `"Netflix"`, `"Hulu"`, `"Prime Video"`, and `"Disney+"`) for each row and returns the index of the row with the greatest sum.  To do this, we need the `loc` accessor to select all the service-specific indicator columns, which we can do using `loc[:, "Netflix":]` or `loc[:, ["Netflix", "Hulu", "Prime Video", "Disney+"]]`.

When looking at Expression 2, we can split the problem into two parts: the code inside the `assign` statement and the code outside of it. 

- Glancing at the code inside of the `assign` statement, (and also noticing the variable `num_services`), we realize that we, once again, want to sum up the values in the service-specific indicator columns. We do this by first selecting the last four columns, using `.iloc[:, 5:]` (notice the `iloc`), and then summing over `axis=1`. We use `axis=1` (different from `axis=0` in Expression 1), because unlike Expression 1, we're summing over each row, instead of each column. If there had not been a `.T` in the code for Expression 1, we would've also used `axis=1` in Expression 1.
- Finally, we need to select the `"Title"` of the last row in DataFrame in Expression 2, because `sort_values` sorts in ascending order by default. The last row has an integer position of -1, and the `"Title"` column has an integer position of 0, so we use `iloc[-1, 0]`.

# END SOLN

# END PROB