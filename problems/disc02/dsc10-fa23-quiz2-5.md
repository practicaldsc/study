# BEGIN PROB

Consider the function `tom_nook`, defined below. Recall that if `x` is
an integer, `x % 2` is `0` if `x` is even and `1` if `x` is odd.

```py
def tom_nook(crossing):
    bells = 0
    for nook in np.arange(crossing):
        if nook % 2 == 0:
            bells = bells + 1
        else:
            bells = bells - 2
    return bells
```

What value does `tom_nook(8)` evaluate to?

( ) -6
( ) -4
( ) -2
( ) 0
( ) 2
( ) 4
( ) 6

# BEGIN SOLUTION

**Answer**: -4

# END SOLUTION

# END PROB