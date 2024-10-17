# BEGIN PROB

<i>Source: [Spring 2024 Final](../sp24-final/index.html), Problem 9</i>

Delta's flight operations center keeps track of weather conditions, as
they tend to impact whether or not flights are late. For each flight,
Delta keeps track of:

-   Whether or not there was **precipitation** --- i.e., rain, snow, or
    hail.

-   The **wind conditions** --- either no winds, light winds, moderate
    winds, or heavy winds.

-   The flight's **status** --- whether it was early, on time, or late.

Information about 100 flights is summarized in the table below.

<center><img src='../assets/images/sp24-final/naive-bayes.png' width=900></center>

For instance, we're told that 6 flights in moderate winds and no
precipitation landed late, and that there were 13 total flights in heavy
winds and precipitation.

Delta would like to use this information to predict whether a new flight
will be early, on time, or late, given the weather conditions.

# BEGIN SUBPROB

**Without smoothing**, what is:

$$\mathbb{P}(\text{heavy winds} \: | \: \text{early})$$

( ) $\frac{2}{7}$ 
( ) $\frac{5}{7}$ 
( ) $\frac{3}{8}$ 
( ) $\frac{3}{10}$
( ) $\frac{14}{15}$ 
( ) $\frac{3}{28}$ 
( ) $\frac{5}{28}$

# BEGIN SOLUTION

$\frac{2}{7}$.

There are $28$ flights that landed early, and of those, $5 + 3 = 8$ were in heavy winds, which means our estimate is $\frac{8}{28} = \frac{2}{7}$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

**With smoothing**, what is:

$$\mathbb{P}(\text{heavy winds} \: | \: \text{early})$$

( ) $\frac{1}{3}$ 
( ) $\frac{3}{8}$ 
( ) $\frac{3}{11}$ 
( ) $\frac{9}{29}$ 
( ) $\frac{9}{32}$ 
( ) $\frac{31}{101}$ 
( ) $\frac{31}{104}$

# BEGIN SOLUTION

$\frac{9}{32}$.

There are $28$ flights that landed early, and of those, $5 + 3 = 8$ were in heavy winds, which means our estimate is $\displaystyle\frac{8+1}{28+4} = \frac{9}{32}$. (The denominator is 28 + 4 since there are 4 possible wind conditions – none, light, moderate, and heavy.)

# END SOLUTION

# END SUBPROB

For your convenience, the table from the previous page is repeated again
below.

<center><img src='../assets/images/sp24-final/naive-bayes.png' width=900></center>

# BEGIN SUBPROB

An airline's late-to-early ratio, given a set of weather conditions, is
defined as:

$$\frac{\mathbb{P}(\text{late} \: | \: \text{conditions})}{\mathbb{P}(\text{early} \: | \: \text{conditions})}$$

Using the assumptions of the Naïve Bayes classifier **without
smoothing**, show that Delta's late-early ratio for flights in **heavy
winds and precipitation** is $\bf{\frac{7}{5}}$.

*Hint: You'll end up needing to compute 6 probabilities, one of which
you already found in **part (a)**.*


# BEGIN SOLUTION

We can recognize that:

$$\displaystyle\frac{P(\text{late | conditions})}{P(\text{early | conditions})} \\ = \displaystyle\frac{P(\text{late}) \cdot P(\text{heavy winds | late}) \cdot P(\text{precipitation | late})}{P(\text{early}) \cdot P(\text{heavy winds | early}) \cdot P(\text{precipitation | early})}$$

and compute the following:

- $P(\text{late}) = \frac{32}{100}$
- $P(\text{heavy winds | late}) = \frac{8}{32}$
- $P(\text{precipitation | late}) = \frac{16}{32}$

- $P(\text{early}) = \frac{28}{100}$
- $P(\text{heavy winds | early}) = \frac{8}{28}$
- $P(\text{precipitation | early}) = \frac{10}{28}$

which gives:

$$\displaystyle\frac{\displaystyle\frac{32}{100} \cdot \displaystyle\frac{8}{32} \cdot \displaystyle\frac{16}{32}}{\displaystyle\frac{28}{100} \cdot \displaystyle\frac{8}{28} \cdot \displaystyle\frac{10}{28}} = \displaystyle\frac{\displaystyle\frac{1}{35}}{\displaystyle\frac{1}{25}} = \displaystyle\frac{7}{5}$$.

# END SOLUTION

# END SUBPROB

# END PROB