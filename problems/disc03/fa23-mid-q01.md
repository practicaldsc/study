# BEGIN PROB

The `df` table records what people ate in kilograms (kg) on each date in 2023. For example, the first row records that Sam ate 0.2 kg of Ribeye on Jan 1, 2023. 

<center><img src='../assets/images/disc03/data-foods-dsc80.png' width=65%></center>


Find all the rows in `df` where Tina was the person eating.

```py
df.____
```

# BEGIN SOLN
**Answer**: `df.loc[df['name'] == 'Tina']`

We can use the `loc` accessor to select the rows from `df` under a specific condition, where rows satisfying the condition as `True` will be selected. In this case, to get the rows where "Tina was the person eating", our conditional is when a value from the column `df['name']` is equal to the string `'Tina'`.

<average>67</average>

# END SOLN

# END PROB
