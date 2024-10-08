# BEGIN PROB

Billina Records, a new record company focused on creating new TikTok audios, has its offices on the 23rd floor of a skyscraper with 75 floors (numbered 1 through 75). The owners of the building promised that 10 different random floors will be selected to be renovated.

Below, fill in the blanks to complete a simulation that will estimate the probability that Billina Records' floor will be renovated. 

```py
total = 0
repetitions = 10000
for i in np.arange(repetitions):
    choices = np.random.choice(__(a)__, 10, __(b)__)
    if __(c)__:
        total = total + 1
prob_renovate = total / repetitions
```

What goes in blank (a)?

( ) `np.arange(1, 75)`
( ) `np.arange(10, 75)`
( ) `np.arange(0, 76)`
( ) `np.arange(1, 76)`

What goes in blank (b)?

( ) `replace=True`
( ) `replace=False`

What goes in blank (c)?

( ) `choices == 23`
( ) `choices is 23`
( ) `np.count_nonzero(choices == 23) > 0`
( ) `np.count_nonzero(choices) == 23`
( ) `choices.str.contains(23)`

# BEGIN SOLN

**Answer:** `np.arange(1, 76)`, `replace=False`, `np.count_nonzero(choices == 23) > 0`

Here, the idea is to randomly choose 10 **different** floors repeatedly, and each time, check if floor 23 was selected.

Blank (a): The first argument to `np.random.choice` needs to be an array/list containing the options we want to choose from, i.e. an array/list containing the values 1, 2, 3, 4, ..., 75, since those are the numbers of the floors. `np.arange(a, b)` returns an array of integers spaced out by 1 starting from `a` and ending at `b-1`. As such, the correct call to `np.arange` is `np.arange(1, 76)`.

Blank (b): Since we want to select 10 different floors, we need to specify `replace=False` (the default behavior is `replace=True`).

Blank (c): The `if` condition needs to check if 23 was one of the 10 numbers that were selected, i.e. if 23 is in `choices`. It needs to evaluate to a single Boolean value, i.e. `True` (if 23 was selected) or `False` (if 23 was not selected). Let's go through each incorrect option to see why it's wrong:

- Option 1, `choices == 23`, does not evaluate to a single Boolean value; rather, it evaluates to an array of length 10, containing multiple `True`s and `False`s.
- Option 2, `choices is 23`, does not evaluate to what we want – it checks to see if the array `choices` is the same Python object as the number 23, which it is not (and will never be, since an array cannot be a single number).
- Option 4, `np.count_nonzero(choices) == 23`, does evaluate to a single Boolean, however it is not quite correct. `np.count_nonzero(choices)` will always evaluate to 10, since `choices` is made up of 10 integers randomly selected from 1, 2, 3, 4, ..., 75, none of which are 0. As such, `np.count_nonzero(choices) == 23` is the same as `10 == 23`, which is always False, regardless of whether or not 23 is in `choices`.
- Option 5, `choices.str.contains(23)`, errors, since `choices` is not a Series (and `.str` can only follow a Series). If `choices` were a Series, this would still error, since the argument to `.str.contains` must be a string, not an int.

By process of elimination, Option 3, `np.count_nonzero(choices == 23) > 0`, must be the correct answer. Let's look at it piece-by-piece:

- As we saw in Option 1, `choices == 23` is a Boolean array that contains `True` each time the selected floor was floor 23 and `False` otherwise. (Since we're sampling without replacement, floor 23 can only be selected at most once, and so `choices == 23` can only contain the value `True` at most once.)
- `np.count_nonzero(choices == 23)` evaluates to the number of `True`s in `choices == 23`. If it is positive (i.e. 1), it means that floor 23 was selected. If it is 0, it means floor 23 was not selected.
- Thus, `np.count_nonzero(choices == 23) > 0` evaluates to `True` if (and only if) floor 23 was selected.

# END SOLN

# END PROB