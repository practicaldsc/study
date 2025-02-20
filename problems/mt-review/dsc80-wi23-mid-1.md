# BEGIN PROB

For this question, we will work with the DataFrame `tv`, which contains information about various TV shows available to watch on streaming services. For each TV show, we have:

-  `"Title" (object)`: The title of the TV show.
-  `"Year" (int)`: The year in which the TV show was first released. (For instance, the show _How I Met Your Mother_ ran from 2005 to 2014; there is only one row for _How I Met Your Mother_ in `tv`, and its `"Year"` value is 2005.)
-  `"Age" (object)`: The age category for the TV show. If not missing, `"Age"` is one of `"all"`, `"7+"`, `"13+"`, `"16+"`, or `"18+"`. (For instance, `"all"` means that the show is appropriate for all audiences, while `"18+"} means that the show contains mature content and viewers should be at least 18 years old.)
-  `"IMDb" (float)`: The TV show's rating on IMDb (between 0 and 10).
-  `"Rotten Tomatoes" (int)`: The TV show's rating on Rotten Tomatoes (between 0 and 100).
-  `"Netflix" (int)`: 1 if the show is available for streaming on Netflix and 0 otherwise. The `"Hulu"`, `"Prime Video"`, and `"Disney+"` columns work the same way.

The first few rows of `tv` are shown below (though `tv` has many more rows than are pictured here).

<center><img src='../assets/images/disc02/disc02-p4-df.png' width=65%></center>

Assume that we have already run all of the necessary imports.

**Throughout this problem, we will refer to `tv` repeatedly.**

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

# BEGIN SUBPROB

Ethan is an avid Star Wars fan, and the only streaming service he has an
account on is Disney+. (He had a Netflix account, but then Netflix
cracked down on password sharing.)

Fill in the blanks below so that `star_disney_prop` evaluates to the
proportion of TV shows in `tv` with `"Star Wars"` in the title that are
available to stream on Disney+.

```py
star_only = __(a)__
star_disney_prop = __(b)__ / star_only.shape[0]
```

What goes in the blanks?

# BEGIN SOLN

**Answers**:

- Blank (a): `tv[tv["Title"].str.contains("Star Wars")]`
- Blank (b): `star_only["Disney+"].sum()`

We're asked to find the proportion of TV shows with `"Star Wars"` in the title that are available to stream on Disney+. This is a fraction, where:

- The numerator is the number of TV shows that have `"Star Wars"` in the title **and** are available to stream on Disney+.
- The denominator is the number of TV shows that have `"Star Wars"` in the title.

The key is recognizing that `star_only` must be a DataFrame that contains all the rows in which the `"Title"` contains `"Star Wars"`; to create this DataFrame in blank (a), we use `tv[tv["Title"].str.contains("Star Wars")]`. Then, the denominator is already provided for us, and all we need to fill in is the numerator. There are a few possibilities, though they all include `star_only`:

- `star_only["Disney+"].sum()`
- `(star_only["Disney+"] == 1).sum()`
- `star_only[star_only["Disney+"] == 1].shape[0]`

**Common misconception**: Many students calculated the wrong proportion: they calculated the proportion of shows available to stream on Disney+ that have `"Star Wars"` in the title. We asked for the proportion of shows with `"Star Wars"` in the title that are available to stream on Disney+; "proportion of $X$ that $Y$" is always $\frac{\# X \text{ and } Y}{\# X}$.

# END SOLN

# END SUBPROB

# END PROB