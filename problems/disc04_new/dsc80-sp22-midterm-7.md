# BEGIN PROB

Define `small_students` to be the DataFrame with 8 rows and 2 columns
shown directly below, and define `districts` to be the DataFrame
with 3 rows and 2 columns shown below `small_students`.

<!-- <p style="display: flex; justify-content: left; gap: 20px;">
    <img src='../assets/images/disc03/small_students.png' width=30%>
</p>
<p style="display: flex; justify-content: right; gap: 20px;">
    <img src='../assets/images/disc03/districts.png' width=30%>
</p> -->

<p align="center">
    <img src='../assets/images/disc04_new/small_students.png' width=30% style="display:inline-block; margin-right:20px;">
    <img src='../assets/images/disc04_new/districts.png' width=30% style="display:inline-block;">
</p>

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

<center><img src='../assets/images/disc03/merge-ans-1.png' width=45%></center>

# END SOLN

# END PROB