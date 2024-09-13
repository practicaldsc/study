# BEGIN PROB

Define `small_students` to be the DataFrame with 8 rows and 2 columns
shown directly below, and define `districts` to be the DataFrame
with 3 rows and 2 columns shown below `small_students`.

<center><img src='../assets/images/disc03/dsc80-sp22-midterm-small_students.png' width=30%></center>
<center><img src='../assets/images/disc03/dsc80-sp22-midterm-districts.png' width=30%></center>

Consider the DataFrame `merged`, defined below.

```py
merged = small_students.merge(districts, 
                                left_on="High School", 
                                right_on="school", 
                                how="outer")
```

How many total `NaN` values does `merged` contain? Give your answer as
an integer.

# BEGIN SOLN

**Answer: **4

`merged` is shown below.

<center><img src='../assets/images/disc03/dsc80-sp22-midterm-merge-ans-1.png' width=45%></center>

# END SOLN

# END PROB