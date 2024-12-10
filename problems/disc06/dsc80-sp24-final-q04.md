# BEGIN PROB

You want to use regular expressions to extract out the number of ounces from the
5 product names below.

| **Index** | **Product Name**                        | **Expected Output** |
| --------- | --------------------------------------- | ------------------- |
| 0         | Adult Dog Food 18-Count, 3.5 oz Pouches | 3.5                 |
| 1         | Gardetto's Snack Mix, 1.75 Ounce        | 1.75                |
| 2         | Colgate Whitening Toothpaste, 3 oz Tube | 3                   |
| 3         | Adult Dog Food, 13.2 oz. Cans 24 Pack   | 13.2                |
| 4         | Keratin Hair Spray 2!6 oz               | 6                   |

The names are stored in a pandas Series called `names`. For each snippet below, select the indexes for all the product names that **will not** be matched correctly.

# BEGIN SUBPROB

For the snippet below, which indexes correspond to products that will **not** be matched correctly?

```python
regex = r'([\d.]+) oz'
names.str.findall(regex)
```

[ ] 0  
[ ] 1  
[ ] 2  
[ ] 3  
[ ] 4  
[ ] All names will be matched correctly.

# BEGIN SOLN

**Answer:** Only product 1 will **not** be matched; the pattern only looks for "oz" so the "Ounce" is not identified. See this [Regex101 link](https://regex101.com/r/yovYEb/1) for an illustration.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

For the snippet below, which indexes correspond to products that will **not** be matched correctly?

```python
regex = r'(\d+?.\d+) oz|Ounce'
names.str.findall(regex)
```

[ ] 0  
[ ] 1  
[ ] 2  
[ ] 3  
[ ] 4  
[ ] All names will be matched correctly.

# BEGIN SOLN

**Answer:** 1, 2, and 4 are either not matched or done so incorrectly. This pattern matches **either** numbers+any character+numbers+[a space]+"oz" OR "Ounce". However it fails in the following ways:

- For index 1, the pattern matches too little: only "Ounce" when it should match "1.75 Ounce".
- For index 2, "3 oz" is missed entirely, as the number is a single digit.
- For index 4, the pattern matches too much: "2!6 oz" when it should match of "6 oz".

<center><img src="../assets/images/disc06/q5-2.png" width=600></center>

See this [Regex101 link](https://regex101.com/r/ujrwg0/1) for an interactive illustration.

# END SOLN

# END SUBPROB

# END PROB
