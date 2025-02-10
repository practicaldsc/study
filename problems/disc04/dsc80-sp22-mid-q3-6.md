# BEGIN PROB

In this problem, we will be using the following DataFrame `students`, which contains various information about high school students and the university/universities they applied to.

<center><img src='../assets/images/disc04/students.png' width=65%></center>

The columns are:

 - `'Name' (str)`: the name of the student.
 - `'High School' (str)`: the High School that the student attended.
 - `'Email' (str)`: the email of the student.
 - `'GPA' (float)`: the GPA of the student.
 - `'AP' (int)`: the number of AP exams that the student took.
 - `'University' (str)`: the name of the university that the student applied to.
 - `'Admit' (str)`: the acceptance status of the student (where 'Y' denotes that they were accepted to the university and 'N' denotes that they were not).

 The rows of `'student'` are arranged in no particular order. The first eight rows of `'student'` are shown above (though `'student'` has many more rows than pictured here).

# BEGIN SUBPROB

Fill in the blank so that the result evaluates to a Series indexed by
`"Email"` that contains a **list** of the universities that each student
**was admitted to**. If a student wasn't admitted to any universities,
they should have an empty list.

```py
    students.groupby("Email").apply(_____)
```

What goes in the blank?

# BEGIN SOLN

**Answer: ** `lambda df: df.loc[df["Admit"] == "Y", "University"].tolist()`

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Which of the following blocks of code correctly assign `max_AP` to the
maximum number of APs taken by a student who was rejected by UC San
Diego?

Option 1:

```py
cond1 = students["Admit"] == "N"
cond2 = students["University"] == "UC San Diego"
max_AP = students.loc[cond1 & cond2, "APs"].sort_values().iloc[-1]
```

Option 2:

```py
cond1 = students["Admit"] == "N"
cond2 = students["University"] == "UC San Diego"
d3 = students.groupby(["University", "Admit"]).max().reset_index()
max_AP = d3.loc[cond1 & cond2, "APs"].iloc[0]
```

Option 3:

```py
p = students.pivot_table(index="Admit", 
                            columns="University", 
                            values="APs", 
                            aggfunc="max")
max_AP = p.loc["N", "UC San Diego"]
```

Option 4:

```py
# .last() returns the element at the end of a Series it is called on
groups = students.sort_values(["APs", "Admit"]).groupby("University")
max_AP = groups["APs"].last()["UC San Diego"]
```

**Select all that apply.** There is at least one correct option.

[ ] Option 1
[ ] Option 2
[ ] Option 3
[ ] Option 4

# BEGIN SOLN

**Answer: ** Option 1 and Option 3

-   Option 1 works correctly, it is probably the most straightforward
    way of answering the question. `cond1` is `True` for all rows in
    which students were rejected, and `cond2` is `True` for all rows in
    which students applied to UCSD. As such,
    `students.loc[cond1 & cond2]` contains only the rows where students
    were rejected from UCSD. Then,
    `students.loc[cond1 & cond2, "APs"].sort_values()` sorts by the
    number of `"APs"` taken in increasing order, and `.iloc[-1]` gets
    the largest number of `"APs"` taken.

-   Option 2 doesn't work because the lengths of `cond1` and `cond2` are
    not the same as the length of `d3`, so this causes an error. 

-   Option 3 works correctly. For each combination of `"Admit"`
    status (`"Y"`, `"N"`, `"W"`) and `"University"` (including UC San
    Diego), it computes the max number of `"APs"`. The usage of
    `.loc["N", "UC San Diego"]` is correct too.

-   Option 4 doesn't work. It currently returns the maximum number of
    `"APs"` taken by someone who applied to UC San Diego; it does not
    factor in whether they were admitted, rejected, or waitlisted. 

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Currently, `students` has a lot of repeated information --- for
instance, if a student applied to 10 universities, their GPA appears 10
times in `students`.

We want to generate a DataFrame that contains a single row for each
student, indexed by `"Email"`, that contains their `"Name"`,
`"High School"`, `"GPA"`, and `"APs"`.

One attempt to create such a DataFrame is below.

```py
students.groupby("Email").aggregate({"Name": "max",
                                        "High School": "mean",
                                        "GPA": "mean",
                                        "APs": "max"})
```

There is exactly one issue with the line of code above. **In one
sentence**, explain what needs to be changed about the line of code
above so that the desired DataFrame is created.

# BEGIN SOLN

**Answer: ** The problem right now is that aggregating High School by mean doesn't work since you can't aggregate a column with strings using `"mean"`. Thus changing it to something that works for strings like `"max"` or `"min"` would fix the issue.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Consider the following snippet of code.

```py
pivoted = students.assign(Admit=students["Admit"] == "Y") \
                    .pivot_table(index="High School", 
                                columns="University", 
                                values="Admit", 
                                aggfunc="sum")
```

Some of the rows and columns of `pivoted` are shown below.

<center><img src='../assets/images/disc04/pivot_school.png' width=40%></center>

No students from Warren High were admitted to Columbia or Stanford.
However,\
`pivoted.loc["Warren High", "Columbia"]` and
`pivoted.loc["Warren High", "Stanford"]` evaluate to different values.
What is the reason for this difference?

( ) Some students from Warren High applied to Stanford, and some others applied to Columbia, but none applied to both.
( ) Some students from Warren High applied to Stanford but none applied to Columbia.
( ) Some students from Warren High applied to Columbia but none applied to Stanford.
( ) The students from Warren High that applied to both Columbia and Stanford were all rejected from Stanford, but at least one was admitted to Columbia.
( ) When using `pivot_table`, `pandas` was not able to sum strings of the form `"Y"`, `"N"`, and `"W"`, so the values in `pivoted` are unreliable.

# BEGIN SOLN

**Answer: ** Option 3

`pivoted.loc["Warren High", "Stanford"]` is `NaN` because there were no
rows in `students` in which the `"High School"` was `"Warren High"` and
the `"University"` was `"Stanford"`, because nobody from Warren High
applied to Stanford. However, `pivoted.loc["Warren High", "Columbia"]`
is not `NaN` because there was at least one row in `students` in which
the `"High School"` was `"Warren High"` and the `"University"` was
`"Columbia"`. This means that at least one student from Warren High
applied to Columbia.

Option 3 is the only option consistent with this logic.

# END SOLN

# END SUBPROB

# END PROB