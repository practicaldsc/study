# BEGIN PROB

# BEGIN SUBPROB

What is the type of the following expression?

```py
(survey
 .sort_values(by="Class Standing")
)
```

( ) int or float       
( ) list or array    
( ) Boolean
( ) Series
( ) string
( ) DataFrame  

# BEGIN SOLUTION

**Answer**: DataFrame

The method `.sort_values(by="Class Standing")` sorts the `survey` DataFrame by the `"Class Standing"` column and returns a new DataFrame (without modifying the original one). The resulting DataFrame will be sorted by class standing in ascending order unless specified otherwise by providing the `ascending=False` argument.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What is the type of the following expression?

```py
(survey
 .sort_values(by="Class Standing")
 .value_counts("College")
)
```

( ) int or float       
( ) list or array    
( ) Boolean
( ) Series
( ) string
( ) DataFrame      

# BEGIN SOLUTION

**Answer**: DataFrame

The method `.sort_values(by="Class Standing")` sorts the `survey` DataFrame based on the entries in the `"Class Standing"` column and produces a new DataFrame. Following this, `.value_counts("College")` organizes the sorted DataFrame by grouping entries using the `"College"` column and yields the number of rows for each `"College"`. The result is a DataFrame whose index contains the unique values in `"College"` and whose columns all contain the same values – the number of rows in `survey.sort_values(by="Class Standing")` for each `"College"`.

Note that if we didn't sort before grouping – that is, if our expression was just `survey.value_counts("College")` – the resulting DataFrame would be the same! That's because the order of the rows in `survey` does not impact the number of rows in `survey` that belong to each `"College"`.

# END SOLUTION

# END SUBPROB


# BEGIN SUBPROB

What is the type of the following expression?

```py
(survey
 .sort_values(by="Class Standing")
 .groupby("College").count()
 .get("IG Followers")
)
```

( ) int or float       
( ) list or array    
( ) Boolean
( ) Series
( ) string
( ) DataFrame     
 
 # BEGIN SOLUTION

**Answer**: Series

The above expression, before `.get("IG Followers")`, is the same as in the previous subpart. We know that

```py
survey.sort_values(by="Class Standing").groupby("College").count()
```
is a DataFrame indexed by `"College"` with multiple columns, each of which contain the number of rows in `survey.sort_values(by="Class Standing")` for each `"College"`. Then, using `.get("IG Followers")` extracts just the `"IG Followers"` column from the aforementioned counts DataFrame, and we know that columns are stored as Series. We know that this column exists, because `survey.sort_values(by="Class Standing").groupby("College").count()` will have the same columns as `survey`, minus `"College"`, which was moved to the index.

# END SOLUTION

# END SUBPROB


# BEGIN SUBPROB

What is the type of the following expression?

```py
(survey
 .sort_values(by="Class Standing")
 .groupby("College").count()
 .get("IG Followers")
 .iloc[0]
)
```

( ) int or float       
( ) list or array    
( ) Boolean
( ) Series
( ) string
( ) DataFrame     

# BEGIN SOLUTION

**Answer**: int or float

In the previous subpart, we saw that

```py
survey.sort_values(by="Class Standing").groupby("College").count().get("IG Followers")
```

is a Series whose index contains the unique names of `"College"`s and whose values are the number of rows in `survey.sort_values(by="Class Standing")` for each college. The number of rows in `survey.sort_values(by="Class Standing")` for any particular college – say, `"Sixth"` – is a number, and so the values in this Series are all numbers. As such, the answer is int or float.

# END SOLUTION

# END SUBPROB


# BEGIN SUBPROB

What **value** does the following expression evaluate to? If you believe
the expression errors, provide a one sentence explanation of why.

For example, if you think the expression evaluates to an int, don't
write "int\" or "the largest value in the `"IG Followers"` column\",
write the specific int, like "23\".

*Hint: You have enough information to answer the problem; don't forget
to look at the data description page.*

```py
(survey
.sort_values(by="Class Standing")
.groupby("College").count()
.get("IG Followers")
.index[0]
)
```

# BEGIN SOLUTION

**Answer**: `"ERC"`

From the previous subpart, we saw that

```py
survey
.sort_values(by="Class Standing")
.groupby("College").count()
.get("IG Followers")
```

is a Series, indexed by `"College"`, whose values contain the number of rows in `survey.sort_values(by="Class Standing")` for each `"College"`. When we group by `"College"`, the resulting DataFrame (and hence, our Series) is sorted in ascending order by `"College"`. This means that the index of our Series is sorted alphabetically by `"College"` names. Of the `"College"` names mentioned in the data description (`"ERC"`, `"Marshall"`, `"Muir"`, `"Revelle"`, `"Seventh"`, `"Sixth"`, and `"Warren"`), the first name alphabetically is `"ERC"`, so using `.index[0]` on the above index gives us `"ERC"`.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Consider again the expression from 1.5. Suppose we remove the piece

```py
.sort_values(by="Class Standing")
```

but keep all other parts the same. Does this change the value the
expression evaluates to?

( ) Yes, this changes the value the expression evaluates to.
( ) No, this does not change the value the expression evaluates to.

# BEGIN SOLUTION

**Answer**: No, this does not change the value the expression evaluates to.

We addressed this in the second subpart of the problem: "_Note that if we didn't sort before grouping – that is, if our expression was just `survey.groupby("College").count()` – the resulting DataFrame would be the same! That's because the order of the rows in `survey` does not impact the number of rows in `survey` that belong to each `"College"`._"

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What **value** does the following expression evaluate to? If you believe
the expression errors, provide a one sentence explanation of why.

For example, if you think the expression evaluates to an int, don't
write "int" or "the largest value in the `"IG Followers"` column",
write the specific int, like "23".

*Hint: You have enough information to answer the problem; don't forget
to look at the data description page.*

```py
(survey
 .sort_values(by="Class Standing")
 .groupby("College").count()
 .get("IG Followers")
 .loc[0]
)
```

# BEGIN SOLUTION

**Answer**: The code produces an error because, after the grouping operation, the resulting Series uses the unique college names as indices, and there isn't a college named `0`.

In the previous few subparts, we've established that

```py
survey
.sort_values(by="Class Standing")
.groupby("College").count()
.get("IG Followers")
```

is a Series, indexed by `"College"`, whose values contain the number of rows in `survey.sort_values(by="Class Standing")` for each `"College"`.

The `.loc` accessor is used to extract a value from a Series given its label, or index value. However, since the index values in the aforementioned Series are `"College"` names, there is no value whose index is `0`, so this throws an error.

# END SOLUTION

# END SUBPROB

# END PROB