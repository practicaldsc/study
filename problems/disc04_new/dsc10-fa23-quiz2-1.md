The DataFrame `items` describes various items available to collect or purchase using bells, the currency used in the game _Animal Crossing: New Horizons_.

For each item, we have:

- `"Item" (str)`: The name of the item.
- `"Cost" (int)`: The cost of the item in bells. Items that cost 0 bells cannot be purchased and must be collected through other means (such as crafting).
- `"Location" (str)`: The store or action through which the item can be obtained.

The first 6 rows of `items` are below, though `items` has more rows than are shown here.

<center><img src="../assets/images/disc04_new/items.png" width=600></center>

# BEGIN PROB

Fill in the blanks so that `count_1` and `count_2` both evaluate to the
number of items in `items` with a `"Cost"` of 0.

```py
count_1 = items.groupby(__(a)__).__(b)__().get("Item").loc[__(c)__]
count_2 = items[__(d)__].shape[0]
```

# BEGIN SOLUTION

**Answer**:

- `a`: `"Cost"`
- `b`: `count`
- `c`: `0`
- `d`: `items.get("Cost") == 0`

# END SOLUTION

# END PROB
