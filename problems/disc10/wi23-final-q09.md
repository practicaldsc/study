# BEGIN PROB
One piece of information that may be useful as a feature is the proportion of SAT test takers in a state in a given year that qualify for free lunches in school. The Series `lunch_props` contains 8 values, each of which are either `"low"`, `"medium"`, or `"high"`. Since we can't use strings as features in a model, we decide to encode these strings using the following `Pipeline`:

```py
# Note: The FunctionTransformer is only needed to change the result
# of the OneHotEncoder from a "sparse" matrix to a regular matrix
# so that it can be used with StandardScaler;
# it doesn't change anything mathematically.
pl = Pipeline([
    ("ohe", OneHotEncoder(drop="first")),
    ("ft", FunctionTransformer(lambda X: X.toarray())),
    ("ss", StandardScaler())
])
```

After calling `pl.fit(lunch_props)`, `pl.transform(lunch_props)` evaluates to the following array:

```py
array([[ 1.29099445, -0.37796447],
       [-0.77459667, -0.37796447],
       [-0.77459667, -0.37796447],
       [-0.77459667,  2.64575131],
       [ 1.29099445, -0.37796447],
       [ 1.29099445, -0.37796447],
       [-0.77459667, -0.37796447],
       [-0.77459667, -0.37796447]])
```

and `pl.named_steps["ohe"].get_feature_names()` evaluates to the following array:

```py
array(["x0_low", "x0_med"], dtype=object)
```

Given the above information, we can conclude that `lunch_props` has __(a)__ value(s) equal to `"low"`, __(b)__ value(s) equal to `"medium"`, and __(c)__ value(s) equal to `"high"`. *(Note: Each of (a), (b), and (c) should be positive numbers, such that together, they add to 8.)*


What are (a), (b), and (c)? Give your answers as positive integers. 

# BEGIN SOLN

**Answer: ** 3, 1, 4

The first column of the transformed array corresponds to the standardized one-hot-encoded `low` column. There are 3 values that are positive, which means there are 3 values that were originally `1` in that column pre-standardization. This means that 3 of the values in `lunch_props` were originally `"low"`.

The second column of the transformed array corresponds to the standardized one-hot-encoded `med` column. There is only 1 value in the transformed column that is positive, which means only 1 of the values in `lunch_props` was originally `"medium"`.

The Series `lunch_props` has 8 values, 3 of which were identified as `"low"` in subpart 1, and 1 of which was identified as `"medium"` in subpart 2. The number of values being `"high"` must therefore be $8 - 3 - 1 = 4$.

# END SOLN

# END PROB