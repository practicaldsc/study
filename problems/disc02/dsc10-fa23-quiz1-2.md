# BEGIN PROB

Consider the following four assignment statements.

```py
bass = "5"
tuna = 2
sword = ["4.0", 5, 12.5, -10, "2023"]
gold = [4, "6", "CSE", "doc"]
```

# BEGIN SUBPROB

What is the value of the expression `bass * tuna`?

# BEGIN SOLUTION

**Answer**: `"55"`

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Which of the following expressions results in an error?

( ) `int(sword[0])`
( ) `float(sword[1])`   
( ) `int(sword[2])`
( ) `int(sword[3])`    
( ) `float(sword[4])`                          


# BEGIN SOLUTION

**Answer**: `int(sword[0])`

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Which of the following expressions evaluates to `"DSC10"`?

( ) `gold[3].replace("o", "s").title() + str(gold[0] + gold[1])`
( ) `gold[3].replace("o", "s").upper() + str(gold[0] + int(gold[1]))`
( ) `gold[3].replace("o", "s").upper() + str(gold[1] + int(gold[0]))`
( ) `gold[3].replace("o", "s").title() + str(gold[0] + int(gold[1]))`

# BEGIN SOLUTION

**Answer**: `gold[3].replace("o", "s").upper() + str(gold[0] + int(gold[1]))`

# END SOLUTION

# END SUBPROB

# END PROB