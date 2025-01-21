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

# BEGIN SUBPROB

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

# END SUBPROB

In the following subparts, consider the variable `double_count`, defined
below.

```py
double_count = tv["Title"].value_counts().value_counts()
```

# BEGIN SUBPROB

What is `type(double_count)`?

( ) Series 
( ) SeriesGroupBy 
( ) DataFrame 
( ) DataFrameGroupBy

# BEGIN SOLN

**Answer**: Series

The `.value_counts()` method, when called on a Series `s`, produces a new Series in which

- the index contains all unique values in `s`.
- the values are the frequencies of the unique values in `s`.

Since `tv["Title"]` is a Series, `tv["Title"].value_counts()` is a Series, and so is `tv["Title"].value_counts.value_counts()`. We provide an interpretation of each of these Series in the solution to the next subpart.


# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Which of the following statements are true? Select all that apply.

[ ] The only case in which it would make sense to set the index of `tv` to `"Title"` is if `double_count.iloc[0] == 1` is `True`. 
[ ] The only case in which it would make sense to set the index of `tv` to `"Title"` is if `double_count.loc[1] == tv.shape[0]` is `True`. 
[ ] If `double_count.loc[2] == 5` is `True`, there are 5 TV shows that all share the same `"Title"`. 
[ ] If `double_count.loc[2] == 5` is `True`, there are 5 pairs of 2 TV shows such that each pair shares the same `"Title"`. 
[ ] None of the above.

# BEGIN SOLN

**Answers**:

- The only case in which it would make sense to set the index of `tv` to `"Title"` is if `double_count.loc[1] == tv.shape[0]` is `True`. 
- If `double_count.loc[2] == 5` is `True`, there are 5 pairs of 2 TV shows such that each pair shares the same `"Title"`.

To answer, we need to understand what each of `tv["Title"]`, `tv["Title"].value_counts()`, and `tv["Title"].value_counts().value_counts()` contain. To illustrate, let's start with a basic, unrelated example. Suppose `tv["Title"]` looks like:

```py
0    A
1    B
2    C
3    B
4    D
5    E
6    A
dtype: object
```

Then, `tv["Title"].value_counts()` looks like:

```py
A    2
B    2
C    1
D    1
E    1
dtype: int64
```

and `tv["Title"].value_counts().value_counts()` looks like:

```py
1    3
2    2
dtype: int64
```

Back to our actual dataset. `tv["Title"]`, as we know, contains the name of each TV show. `tv["Title"].value_counts()` is a Series whose index is a sequence of the unique TV show titles in `tv["Title"]`, and whose values are the frequencies of each title. `tv["Title"].value_counts()` may look something like the following:

```py
Breaking Bad                             1
Fresh Meat                               1
Doctor Thorne                            1
                                       ...
Styling Hollywood                        1
Vai Anitta                               1
Fearless Adventures with Jack Randall    1
Name: Title, Length: 5368, dtype: int64
```

Then, `tv["Title"].value_counts().value_counts()` is a Series whose index is a sequence of the unique values in the above Series, and whose values are the frequencies of each value above. In the case where all titles in `tv["Title"]` are unique, then `tv["Title"].value_counts()` will only have one unique value, 1, repeated many times. Then, `tv["Title"].value_counts().value_counts()` will only have one row total, and will look something like:

```py
1    5368
Name: Title, dtype: int64
```

This allows us to distinguish between the first two answer choices. The key is remembering that **in order to set a column to the index, the column should only contain unique values**, since the goal of the index is to provide a "name" (more formally, a label) for each row.

- The first answer choice, "The only case in which it would make sense to set the index of `tv` to `"Title"` is if `double_count.iloc[0] == 1` is `True`", is false. As we can see in the example above, all titles are unique, but `double_count.iloc[0]` is something other than 1.
- The second answer choice, "The only case in which it would make sense to set the index of `tv` to `"Title"` is if `double_count.loc[1] == tv.shape[0]` is `True`", is true. If `double_count.loc[1] == tv.shape[0]`, it means that all values in `tv["Title"].value_counts()` were 1, meaning that `tv["Title"]` consisted solely of unique values, which is the only case in which it makes sense to set `"Title"` to the index.

Now, let's look at the second two answer choices. If `double_counts.loc[2] == 5`, it would mean that 5 of the values in `tv["Title"].value_counts()` were 2. This would mean that there were 5 pairs of titles in `tv["Title"]` that were the same. 

- This makes the fourth answer choice, "If `double_count.loc[2] == 5` is `True`, there are 5 pairs of 2 TV shows such that each pair shares the same `"Title"`", correct. 
- The third answer choice, "If `double_count.loc[2] == 5` is `True`, there are 5 TV shows that all share the same `"Title"`", is incorrect; if there were 5 TV shows with the same title, then `double_count.loc[5]` would be at least 1, but we can't make any guarantees about `double_counts.loc[2]`.


# END SOLN

# END SUBPROB

# END PROB