# BEGIN PROB

Suppose we create a DataFrame called `midwest` containing Nishant's flights departing from DTW, ORD, and MKE. `midwest` has 10 rows; the bar chart below shows how many of these 10 flights departed from each airport.

<center><img src='../assets/images/disc04_new/midwest.png' width=30%></center>
<br>

Consider the DataFrame that results from merging `midwest` with itself, as follows:

```py
double_merge = midwest.merge(midwest, left_on='FROM', right_on='FROM')
```

How many rows does `double_merge` have?

# BEGIN SOLUTION

**Answer: ** 38

There are two flights from DTW. When we merge `midwest` with itself on the `'FROM'` column, each of these flights gets paired up with each of these flights, for a total of four rows in the output. That is, the first flight from DTW gets paired with both the first and second flights from DTW. Similarly, the second flight from DTW gets paired with both the first and second flights from DTW.

Following this logic, each of the five flights from ORD gets paired with each of the five flights from ORD, for an additional 25 rows in the output. For MKE, there will be 9 rows in the output. The total is therefore $2^2 + 5^2 + 3^2 = 4 + 25 + 9 = 38$ rows.

# END SOLUTION

# END PROB
