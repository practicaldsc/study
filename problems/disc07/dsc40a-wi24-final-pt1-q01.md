# BEGIN PROB

<i>Source: [Winter 2024 Final Part 1](../wi24-final-pt1/index.html), Problem 1</i>

Suppose there is a dataset containing 10000 integers: 

- 2500 of them are $3$s
- 2500 of them are $5$s
- 4500 of them are $7$s
- 500 of them are $9$s.
# BEGIN SUBPROB

Calculate the median of this dataset.

# BEGIN SOLUTION

$6$

We know there is an even number of integers in this dataset because $10000 \% 2 = 0$. We can find the middle of the dataset as follows: $\frac{10000}{2} = 5000$. This means the element in the 5000th position and 5001st position can give us our median. The element at the 5000th position is a $5$ because $2500 + 2500 = 5000$. The element at the 5001st position is a $7$ because the next number after $5$ is $7$. We can then plug $5$ and $7$ into the equation:
$$\frac{x_{5000} + x_{5001}}{2} = \frac{5 + 7}{2} = 6$$

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

How does the mean of this dataset compared to its median?

( ) The mean is larger than the median
( ) The mean is smaller than the median
( ) The mean and the median are equal

# BEGIN SOLUTION

The mean is smaller than the median.

We can calculate the mean as follows: $$\frac{2500 \cdot  3 + 2500 \cdot  5 + 4500 \cdot  7 + 500 \cdot  9}{10000} = 5.6$$ Using part (a) we know that $5.6 < 6$, which means the mean is smaller than the median.

# END SOLUTION

# END SUBPROB

# END PROB