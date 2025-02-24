# BEGIN PROB

The DataFrame `flights` contains information about recent flights, with each row representing a specific flight and the following columns:

- `"flight num" (str)`: The unique code of the flight, consisting of a two-character airline designator followed by 1 to 4 digits (e.g., `"UA1989"`).
- `"airline" (str)`: The airline name (e.g., `"United"`).
- `"departure" (str)`: The code for the airport from which the flight departs (e.g., `"SAN"`).
- `"arrival" (str)`: The code for the airport at which the flight arrives (e.g., `"LAX"`).


Suppose we have another DataFrame `more_flights` which contains the same
columns as `flights`, but different rows. Define `merged` as follows.
```py
        merged = flights.merge(more_flights, on = "airline")
```
Suppose that in `merged`, there are 108 flights where the airline is
`"United"`, and in `more_flights`, there are 12 flights where the
airline is `"United"`. If `flights` has 15 rows in total, how many of
these rows are **not** for `"United"` flights? Give your answer as an
integer.


# BEGIN SOLUTION

**Answer:** 6

We are merging DataFrames `flights` and `more_flights` according to the airline each flight belongs to. All the `"United"` flights in `more_flights` will be merged with all the `"United"` flights in `flights`, which we know gives us 108 total flights. We also know that there are 12 `"United"` flights in `more_flights`. To find the number of `"United"` flights in `flights`, we simply need to divide the total number of `"United"` flights in `merged` by the number of `"United"` flights in `more_flights`, which is 108/12 = 9. If `flights` has a total of 15 rows, then the total number of non-United rows is equal to 15 - 9 = 6.

# END SOLUTION

# END PROB