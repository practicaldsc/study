# BEGIN PROB

The `laptops` DataFrame contains information on various factors that influence the pricing of laptops. Each row represents a laptop, and the columns are:

- `"Mfr" (str)`: the company that manufactures the laptop, like "Apple" or "Dell".
- `"Model" (str)`: the model name of the laptop, such as "MacBook Pro".
- `"OS" (str)`: the operating system, such as "macOS" or "Windows 11".
- `"Screen Size" (float)`: the diagonal length of the screen, in inches.
- `"Price" (float)`: the price of the laptop, in dollars.

# BEGIN SUBPROB

**Without using `groupby`**, write an expression that evaluates to the
average price of laptops with the `"macOS"` operating system (the same
quantity as above).


# BEGIN SOLUTION

**Answer:** `laptops.loc[laptops["OS"] == "macOS", "Price"].mean()`

# END SOLUTION

# END SUBPROB  

# BEGIN SUBPROB

**Using `groupby`**, write an expression that evaluates to the average
price of laptops with the `"macOS"` operating system.


# BEGIN SOLUTION

**Answer:** `laptops.groupby("OS")["Price"].mean().loc["macOS"]`

# END SOLUTION

# END SUBPROB

# END PROB