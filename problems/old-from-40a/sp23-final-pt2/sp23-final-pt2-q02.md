# BEGIN PROB

<i>Source: [Spring 2023 Final Part 2](../sp23-final-pt2/index.html), Problem 2</i>

You roll a 12-sided die 8 times.

# BEGIN SUBPROB

What is the probability you roll 8 distinct values?

# BEGIN SOLUTION

$\dfrac{{12 \choose 8}\cdot8!}{12^8} = \dfrac{12}{12}\cdot\dfrac{11}{12}\cdot\dfrac{10}{12}\cdot\dots\cdot\dfrac{5}{12}$

There's two ways you can think of this problem.

The numerator ${12 \choose 8}\cdot8!$ is the number of total possible permutations of 8 distinct values; ${12 \choose 8}$ possible sets of 8 distinct values times $8!$ orderings, because the die could roll the same set of distinct values in $8!$ different ways. The denominator $12^8$ is the number of total possible outcomes. Altogether, dividing the numerator by the denominator gives us the probability of rolling 8 distinct values.

We can also solve this problem differently by realizing that the rolls are independent. In the first roll the probability of getting a new number is 1 (since any number would be new), now in the second roll the probability of getting a new number is $\frac{11}{12}$ since we've only rolled one number so rolling any of the other 11 numbers would be rolling a new number.If you keep doing this for each roll, and multiply the independent probabilities of getting a new number in each of the rolls you'll get
$\dfrac{12}{12}\cdot\dfrac{11}{12}\cdot\dfrac{10}{12}\cdot\dots\cdot\dfrac{5}{12}$
# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

What is the probability you roll exactly 7 distinct values?

# BEGIN SOLUTION

$\dfrac{{8 \choose 2}\cdot{12 \choose 7}\cdot7!}{12^8}$

Again, I'm going to show you two different ways you can think of this problem. We can get the total number of outcomes that get you exactly 7 distinct values by doing the following, first choose 7 from the 12 possible numbers (there's ${12 \choose 7}$ ways to do it), then choose a number to duplicate (there's ${7 \choose 1}$ ways to do that), lastly you need to order them. From the 8 possible places you have availible you need to choose 2 for the repeated value (there's ${8 \choose 2}$ ways to do that), then once you chose a placement for your reapeted value you need to choose one for each of the remaing 6 values(there's $6!$ ways to do that). Finally just multiply the different ways you can perform each of those actions and you'll get the number of ways you can roll 7 different values
\begin{align*}
{12 \choose 7}\cdot{7 \choose 1}\cdot{8 \choose 2}\cdot6! = {8 \choose 2}\cdot{12 \choose 7}\cdot7!
\end{align*}

lastly, just divide by the total number of possible outcomes and you get 
$\dfrac{{8 \choose 2}\cdot{12 \choose 7}\cdot7!}{12^8}$

You could also find the number of rolls with exactly 7 different values by doing the following. First, select an ordered string of size 7 from the 12 possible values (there's ${12 \choose 7}\cdot7!$ ways to do that), then take the first value of the string as the duplicated value and keep the others as they are, now you only need to place 2 copies of the repeated value somewhere on your string of 6 numbers (there's ${8 \choose 2}$ ways to do that), multiply this the ways you can do these two actions and divide by total number of outcomes and you'll get 
$\dfrac{{8 \choose 2}\cdot{12 \choose 7}\cdot7!}{12^8}$
This solution is faster but less intuitive.

# END SOLUTION

# END SUBPROB

# END PROB