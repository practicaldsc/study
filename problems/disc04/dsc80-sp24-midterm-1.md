# BEGIN PROB

The `h` table records addresses within San Diego. Only 50 addresses are recorded. The index of the DataFrame contains the numbers 1-50 as unique integers.

- `"number" (int)`: Street address number
- `"street" (str)`: Street name

<center><img src="../assets/images/disc04/h.png" width=400></center>

Fill in the Python code to create a DataFrame containing the proportion of 4-digit address numbers for each unique street in `h`.

```python
def foo(x):
    lengths = __(a)__
    return (lengths == 4).mean()

h.groupby(__(b)__).__(c)__(foo)
```

# BEGIN SOLN

**Answer:** 

(a): `x.astype(str).str.len()`

(b): `'street'`

(c): `agg`

# END SOLN


# END PROB