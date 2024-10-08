# BEGIN PROB

Recall the `evs` DataFrame.

The first few rows of `evs` are shown below (though remember, `evs` has 32 rows total).

<center><img src='../assets/images/disc04/form22.png' width=60%></center>
<br>

Below, we provide the a DataFrame that contains the distribution of "BodyStyle" for all "Brands" in `evs`, other than Nissan.

<center><img src='../assets/images/disc04/midq6.png' width=50%></center>

Suppose we’ve run the following few lines of code.

```py
tesla = evs[evs.get("Brand") == "Tesla"]
bmw = evs[evs.get("Brand") == "BMW"]
audi = evs[evs.get("Brand") == "Audi"]

combo = tesla.merge(bmw, on="BodyStyle").merge(audi, on="BodyStyle")
```

How many rows does the DataFrame `combo` have?

( ) 21
( ) 24
( ) 35
( ) 65
( ) 72
( ) 96

# BEGIN SOLUTION

**Answer:** 35

Let's attempt this problem step-by-step. We'll first determine the number of rows in `tesla.merge(bmw, on="BodyStyle")`, and then determine the number of rows in `combo`. **For the purposes of the solution, let's use `temp` to refer to the first merged DataFrame, `tesla.merge(bmw, on="BodyStyle")`.**

Recall, when we `merge` two DataFrames, the resulting DataFrame contains a single row for every match between the two columns, and rows in either DataFrame without a match disappear. In this problem, the column that we're looking for matches in is `"BodyStyle"`.

To determine the number of rows of `temp`, we need to determine which rows of `tesla` have a `"BodyStyle"` that matches a row in `bmw`. From the DataFrame provided, we can see that the only `"BodyStyle"`s in both `tesla` and `bmw` are SUV and sedan. When we merge `tesla` and `bmw` on `"BodyStyle"`:

- The 4 SUV rows in `tesla` each match the 1 SUV row in `bmw`. This will create 4 SUV rows in `temp`.
- The 3 sedan rows in `tesla` each match the 1 sedan row in `bmw`. This will create 3 sedan rows in `temp`.

So, `temp` is a DataFrame with a total of 7 rows, with 4 rows for SUVs and 3 rows for sedans (in the `"BodyStyle"`) column. Now, when we merge `temp` and `audi` on `"BodyStyle"`:

- The 4 SUV rows in `temp` each match the 8 SUV rows in `audi`. This will create $4 \cdot 8 = 32$ SUV rows in `combo`.
- The 3 sedan rows in `temp` each match the 1 sedan row in `audi`. This will create $3 \cdot 1 = 3$ sedan rows in `combo`.

Thus, the total number of rows in `combo` is $32 + 3 = 35$.

Note: You may notice that 35 is the result of multiplying the `"SUV"` and `"Sedan"` columns in the DataFrame provided, and adding up the results. 

# END SOLUTION

# END PROB
