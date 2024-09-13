# BEGIN PROB

The DataFrame `items` describes various items available to collect or purchase using bells, the currency used in the game _Animal Crossing: New Horizons_.

For each item, we have:

- `"Item" (str)`: The name of the item.
- `"Cost" (int)`: The cost of the item in bells. Items that cost 0 bells cannot be purchased and must be collected through other means (such as crafting).
- `"Location" (str)`: The store or action through which the item can be obtained.


The first 6 rows of `items` are below, though `items` has more rows than are shown here.

<center><img src="../assets/images/disc03/dsc10-fa23-quiz2-items.md.png" width=300></center>


The DataFrame `keepers` has 5 rows, each of which represent a different
shopkeeper in the *Animal Crossing: New Horizons* universe.

`keepers` is shown below in its entirety.

<center><img src="../../assets/images/disc03/dsc10-fa23-quiz2-2.md.png" width=200></center>

<br>

How many rows are in the following DataFrame? Give your answer as an
integer.

```py
keepers.merge(items.take(np.arange(6)), 
              left_on="Store", 
              right_on="Location")
```

# BEGIN SOLUTION

# END SOLUTION

# END PROB