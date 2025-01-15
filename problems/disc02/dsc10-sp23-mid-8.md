# BEGIN PROB

Suppose we're curious about how often a randomly formed group of three students in Practical DSC will have three different majors. To explore this, we created an array `class_majors`, which is an array of every student's major. For example, `class_majors` could look something like `["DS", "CS", "Stats", "CS", "CE", "CS"]`.

Fill in the blanks below so that `prob_all_unique` is an estimate of the
probability that all three students selected are in different majors.

*Hint: The function `np.unique`, when called on an array, returns an
array with just one copy of each unique element in the input. For
example, if `vals` contains the values `1, 2, 2, 3, 3, 4`,
`np.unique(vals)` contains the values `1, 2, 3, 4`.*

```py
    unique_majors = np.array([])
    for i in np.arange(10000):
        group = np.random.choice(class_majors, 3, __(a)__)
        num_unique_majors = len(__(b)__)
        unique_majors = np.append(unique_majors, num_unique_majors)
        
    prob_all_unique = __(c)__
```

# BEGIN SUBPROB

What goes in blank (a)?

( ) `replace=True`
( ) `replace=False`

# BEGIN SOLUTION

**Answer**: `replace=False`

Since we want to guarantee that the same student cannot be selected twice, we should sample without replacement. 

# END SOLUTION

# END SUBPROB


# BEGIN SUBPROB

What goes in blank (b)?

# BEGIN SOLUTION

**Answer**: `np.unique(group)`

In each iteration of our `for`-loop, we're interested in finding the number of unique majors among the 3 students who were selected. We can tell that this is what we're meant to store in `unique_majors` by looking at the options in the next subpart, which involve checking the proportion of times that the values in `unique_majors` is 3.

The majors of the 3 randomly selected students are stored in `group`, and `np.unique(group)` is an array with the unique values in `group`. Then, `len(np.unique(group))` is the number of unique majors in the group of 3 students selected.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What goes in blank (c)?

[ ] `(unique_majors > 2).mean()`
[ ] `(unique_majors.sum() > 2).mean()`
[ ] `np.count_nonzero(unique_majors > 2).sum() / len(unique_majors > 2)`
[ ] `1 - np.count_nonzero(unique_majors != 3).mean()`
[ ] `unique_majors.mean() - 3 == 0`

# BEGIN SOLUTION

**Answer**: Option 1

Let's break down the code we have so far:

- An empty array named `unique_majors` is initialized to store the number of unique majors in each iteration of the simulation.
- The simulation runs 10,000 times, and in every iteration: Three majors are selected at random from the survey dataset without replacement. This ensures that the same item is not chosen more than once within a single iteration. The `np.unique` function is employed to identify the number of unique majors among the selected three. The result is then appended to the `unique_majors` array.
- Following the simulation, the objective is to determine the fraction of iterations in which all three selected majors were unique. Since the maximum number of unique majors that can be selected in a group of three is 3, the code checks the fraction of times the `unique_majors` array contains a value greater than 2.

Let's look at each option more carefully.

- **Option 1**: `(unique_majors > 2).mean()` will create a Boolean array where each value in `unique_majors` is checked if it's greater than 2. In other words, it'll return `True` for each 3 and `False` otherwise. Taking the mean of this Boolean array will give the proportion of `True` values, which corresponds to the probability that all 3 students selected are in different majors.
- **Option 2**: `(unique_majors.sum() > 2)` will generate a single Boolean value (either `True` or `False`) since you're summing up all values in the `unique_majors` array and then checking if the sum is greater than 2. This is not what you want. `.mean()` on a single Boolean value will raise an error because you can't compute the mean of a single Boolean.
- **Option 3**: `np.count_nonzero(unique_majors > 2).sum() / len(unique_majors > 2)` would work without the `.sum()`. `unique_majors > 2` results in a Boolean array where each value is `True` if the respective simulation yielded 3 unique majors and `False` otherwise. `np.count_nonzero()` counts the number of `True` values in the array, which corresponds to the number of simulations where all 3 students had unique majors. This returns a single integer value representing the count. The `.sum()` method is meant for collections (like arrays or lists) to sum their elements. Since `np.count_nonzero` returns a single integer, calling `.sum()` on it will result in an AttributeError because individual numbers do not have a sum method. `len(unique_majors > 2)` calculates the length of the Boolean array, which is equal to 10,000 (the total number of simulations). Because of the attempt to call `.sum()` on an integer value, the code will raise an error and won't produce the desired result. 
- **Option 4**: `np.count_nonzero(unique_majors != 3)` counts the number of trials where not all 3 students had different majors. When you call `.mean()` on an integer value, which is what `np.count_nonzero` returns, it's going to raise an error.
- **Option 5**: `unique_majors.mean() - 3 == 0` is trying to check if the mean of `unique_majors` is 3. This line of code will return `True` or `False`, and this isn't the right approach for calculating the estimated probability.

# END SOLUTION

# END SUBPROB

# END PROB