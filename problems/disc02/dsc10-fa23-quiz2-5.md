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

**Answer**: -4. 

`np.arange(crossing)` will evaluate to `[0,1,2,3,4,5,6,7]`. Thus, the code contained within the loop `for nook in np.arange(crossing)` will execute a total of 8 times and go into the `if` statement code 4 times and the `else` statement code 4 times. After this execution, the final value of `bells` comes out to -4.

# END SOLUTION

# END PROB